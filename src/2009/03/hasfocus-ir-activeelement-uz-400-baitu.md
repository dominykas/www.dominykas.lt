---
published: 2009-03-07T21:42:16+00:00
tags: eksperimentai, html, html5, javascript, kodas, uzknisantys-dalykai-internete, it-tinklo-kurimas
---

# hasFocus ir activeElement už 400 baitų

<p>Vienas labiausiai internete užknisančių dalykų yra tai, kad kai kurios svetainės visiškai manęs negerbdamos paima ir perrašo įvesties laukų turinį tada kai aš jau ten bandau kažką rašyti. Ši situacija kyla iš to, kad nėra paprasto būdo nustatyti ar (ir kuris) HTML elementas yra fokusuotas ar ne. Internet Exploreris jau senokai turi <code>document.activeElement</code>, bet kas iš to, jeigu tai negalioja kitoms naršyklėms. HTML5 specifikacijoje yra standartizuotos abi -<code>element.hasFocus</code> ir <code>document.activeElement</code> galimybės, tačiau ką daryti šiandien? <a href="https://www.dominykas.lt/2009/03/hasfocus-ir-activeelement-uz-400-baitu.html#galutinis-sprendimas-20090307">Tingiu skaityti – duok galutinį sprendimą</a>.</p>
<p>Aprašytos problemos sprendimo algoritmas yra gana paprastas – prikabinti <dfn title="event handler">įvykių gaudytojus</dfn> prie reikalingų elementų ir pačiam nustatyti reikalingus parametrus. Tačiau jeigu nesusimąstytume – greitas ir paprastas įgyvendimas turėtų kelias problemas.</p>
<p><span id="more-83"></span></p>
<h2>Sprendimo problemos</h2>
<p>Pavyzdys: krauname puslapį, jame yra paieškos laukas, kurio viduje yra tekstas “Paieška”. Fokusuojant lauką tas tekstas turi pradingti. Be abejo, pats “standartinio teksto” <i>patternas</i> yra jau savaime nelabai geras, tačiau kartais be jo tiesiog neįmanoma išsiversti. Taigi, turime du variantus: a) tekstą įrašyti lauke iš anksto (<code>input value="Paieška"</code>), fokusuojant jį ištrinti; b) palikti tuščią lauką, ir užkrovus puslapį tą tekstą įrašyti. Pirmu atveju turime semantikos problemą, o taipogi jis nėra <dfn title="unobtrusive">netrukdantis</dfn>, t.y. tam, kad naudotis lauku, reikalingas įjungtas Javascript. Taip pat, abiem atvejais, neįdėjus papildomų pastangų, perrašymas gali įvykti jau po to kai vartotojas fokusuoja lauką (pvz. dėl lėtai kraunamų Javascript bibliotekų arba IE6 paspaudus <i>refresh</i>, kai kursorius yra viename iš laukų).</p>
<p>Konkrečiam pavyzdžiui yra dar ir trečiasis variantas – naudoti <code>onfocus</code> ir <code>onblur</code> atributus ir Javascript rašyti tiesiog HTML viduje (<i>inline Javascript</i>), tačiau šis būdas tinkamas tik tuo atveju, jeigu nesilaikote <dfn title="HTML - markup">sužymėjimo</dfn> ir <dfn title="Javascript - behaviour">elgsenos</dfn> atskyrimo principo. Be to, jis apkrauna kiekvieną siunčiamą puslapį papildomu kodu, kas nėra pageidautina, ypač jeigu tokių laukų yra ne vienas. Na ir aišku, jis neišsprendžia pagrindės šio įrašo problemos – <code>hasFocus</code> – vieningu, paprastu, universaliu būdu.</p>
<h3>Kodo kiekis ir geriausios praktikos</h3>
<p>Akivaizdu, kad <code>hasFocus</code> simuliavimui reikės kiekviename puslapyje įtraukti gabaliuką Javascript, kuris priešingai negu geriausios praktikos rekomendacijos, turės būti įvykdomas dar prieš galutiniai “nupiešiant” puslapį, t.y. <code>&lt;head&gt;</code> viduje. Tai reiškia, kad pats kodas turi būti minimalus – tiek instrukcijų kiekiu, tiek savo apimtimi, nes kiekvienas persiųstas baitas ir vykdymas <a href="http://glinden.blogspot.com/2006/11/marissa-mayer-at-web-20.html">kainuoja vertingas milisekundes</a> (<a href="http://home.blarg.net/~glinden/StanfordDataMining.2006-11-29.ppt">prezentacija</a>).</p>
<h3>Įvykių burbuliavimas</h3>
<p>Su ankstesniu reikalavimu atsiranda ir kitas – neturime galimybės įvykių gaudyti kiekvienam elementui individualiai. Net jeigu tai ir nebūtų idelaus sprendimas vien dėl apkrovimo priežasčių, tie elementai dar paprasčiausiai neegzistuoja dokumente. Taigi turime rinktis <a href="http://code.google.com/p/reglib/">reglib</a> požiūrį – prikabinti savo funkcijas prie viso dokumento ir jų viduje nustatinėti elementą, kuriame viskas vyksta. Šioje vietoje derėtų paminėti, kad remiantis standartais, <code>focus</code> ir <code>blur</code> įvykiai neburbuliuoja į viršų, t.y. tėvinis elementas teoriškai neturėtų žinoti, kad jo vaikuose vyksta būtent šie įvykiai.</p>
<h3>Naršyklių skirtumai</h3>
<p>Skirtingos naršyklės <i>eventus</i> gaudo skirtingais būdais, taipogi naudoja skirtingą metodiką perduoti susiijusius elementus. Tradiciškai ši problema buvo sprendžiama vykdant skirtingas kodo šakas skirtingoms naršyklėms, tai nustant pagal <code>user-agent</code> eilutę. Tokia metodika yra žalinga ir nėra amžina. Pastaruoju metu tiek jQuery, tiek kitos bibliotekos perėjo prie efektyvesnio būdo – tikrinti ar egzistuoja tam tikros galimybės, o ne tikrinti ar lankytojas naudoja konkrečią naršyklę. <i>Feature sniffing</i> taipogi yra reikalavimas šiai užduočiai.</p>
<h2>Sprendimas pažingsniui</h2>
<ol>
<li>Nusistatom įvykių gaudymo funkciją (<i>f</i>) – IE naudoja <code>attachEvent</code>, padorios naršyklės – <code>addEventListener</code>.
</li><li>Nusistatom įvykių vardus (<i>n</i>). <code>focus</code> ir <code>blur</code> kaip minėjau neturėtų burbuliuoti į viršų, todėl su IE reikia naudoti <code>onfocusin</code> ir <code>onfocusout</code>. Šia tema <a href="http://www.quirksmode.org/dom/events/blurfocus.html">galima pasiskaityti ir daugiau</a>, tačiau šiam sprendimui šito užtenka.</li>
<li>Pagrindinė fokuso nustatymo funkcija (<i>s</i>) ima du parametrus – pirmas nurodo ar fokusą įjungti, ar atjungti, antrasis gi nurodo elementą.</li>
<li>Neesu įsitikinęs, kad čia pats taupiausias variantas, tačiau įdedame dvi funkcijas – viena gaudo <code>focus</code> (<i>i</i>), kita <code>blur</code> (<i>o</i>), ir kviečia pagrindinę funkciją.</li>
<li>Viską sukišame į <code>closure</code> ir sutrumpinę iki minimumo pagaliau prisegame įvykius – <code>d[f](n[0],i,true);</code>.</li>
</ol>
<h2 id="galutinis-sprendimas-20090307">Galutinis sprendimas</h2>
<pre>(function() {
    var d = document,
	s = function(h, t) {
		if (t.tagName) {
			t.hasFocus=h;
			if (a) document.activeElement=t;
		}
	},
	i = function(e) {
		s(true, e.target || e.srcElement); },
	o = function(e) {
		s(false, e.target || e.srcElement); },
	f = d.addEventListener ?
		"addEventListener" : "attachEvent",
	n = typeof d.onfocusin=="object" ?
		['onfocusin','onfocusout'] : ['focus','blur'],
	a = typeof document.activeElement=="object" ?
		false : true;

	d[f](n[0],i,true); d[f](n[1],o,true);
})();
</pre>
<p>Panaikinus bereikalingus tarpus ir <a href="http://developer.yahoo.com/yui/compressor/">suspaudus viską į vieną eilutę</a>, šis sprendimas užimtų vos daugiau nei 400 baitų – pakankamai maža kaina už funkcionalumą. Jeigu netyčia nepalikau kokios klaidos kur nors – viskas turėtų veikti su IE6/7, FF2/3, Opera 9.6 ir Safari 3.x.</p>
<p>Taipogi galite pasižiūrėti <a href="http://code.dominykas.com/js/hasFocus.html">veikiančią demonstraciją</a>. Po dviejų sekundžių nuo užkrovimo gausite iššokantį langą, kuriame bus surašyta kas turi fokusą.</p>