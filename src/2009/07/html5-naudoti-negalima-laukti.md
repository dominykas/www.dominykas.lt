---
published: 2009-07-05T23:15:33+00:00
tags: eksperimentai, html5, html5 mitai, semantinis tinklas, standartai, tinklo kūrimas
---

# HTML5: naudoti negalima laukti

<p>Jau kuris laikas pavydėjau Bruce Lawson, kad jis paėmė ir <a href="http://www.brucelawson.co.uk/2009/redesigning-with-html-5-wai-aria/">sužymėjo savo blog’ą HTML5</a>. Kentėjau, tingėjau ir atidėliojau, kol va pagaliau šį savaitgalį paėmiau ir pasidariau tai pats. Tiesa, ne iki galo ir ne visai taip kaip norėjau, bet hell – HTML5 <del>galima</del> privaloma, bent dalinai, naudoti jau šiandien.</p>
<p style="text-align:center;"><img src="https://www.dominykas.lt/uploads/2009/07/html5.png" alt="HTML5 struktūra" title="HTML5 struktūra" width="450" height="189" class="aligncenter size-full wp-image-103" style="border: 1px solid #000;"></p>
<p><span id="more-96"></span></p>
<h2>Struktūriniai elementai veikia puikiai</h2>
<p><a href="http://www.w3.org/TR/html5-diff/">Naujieji elementai</a> (<code>header</code>, <code>footer</code>, <code>time</code>, etc) veikia (beveik) puikiai. Nėra nei vienos rimtos priežasties, kodėl reiktų delsti su jų naudojimu. Vienintelė išimtis (kurios aš net nesistengiau išspręsti) – Firefox 2. IE šeimos naršyklės taipogi nenori pripažinti naujų žymų ir pritaikyti joms stilių, tačiau tai nesunkiai <a href="http://html5doctor.com/how-to-get-html5-working-in-ie-and-firefox-2/">išsprendžiama Javascript pagalba</a>. Jeigu vien Javascript sprendimas netenkina (<i>unobtrussive, progressive enhancement, etc</i>) – visada galima naudoti tarpinį sprendimą – naudoti naujas HTML5 žymas semantikai, o stiliams prikaišioti <code>div</code>‘ų.</p>
<p>Be viso šito, perrašydamas savo blog’o HTML, nesusidūriau su jokiom problemom, išskyrus <code>header</code> ir <code>h1</code> semantinėm reikšmėm, bet tai yra verta atskiro įrašo. Dar turėjau šiek tiek dvejonių dėl <code>section</code> naudojimo, tačiau priėjau išvados, kad geriau šiandien eksperimentuoti, o rytoj padaryti teisingai – be klaidų progreso nebus.</p>
<h2>Formos elementų tipus naudoti galima</h2>
<p>Aš pats nenaudojau naujų formų elementų tipų (<code>type=email</code>, <code>type=url</code>), tačiau kai tik turėsiu daugiau laiko paeksperimentuoti – naudosiu ir juos. Kol kas juos palaiko tik <a href="http://www.opera.com/">Opera naršyklė</a>, tačiau kitos netruks prisivyti, o tos kurios jų nepalaiko – atvaizduos laukus tiesiog kaip <code>type=text</code> – <a href="http://people.opera.com/brucel/demo/html5-forms-demo.html">demo</a>. Vėlgi – truputėlis JS šen bei ten, truputėlis CSS ir ateitis bus šiandien.</p>
<h2><code>canvas</code>, <code>video</code> ir <code>audio</code> palaikymas</h2>
<p>Na, šitie trys žvėrys man šį savaitgalį, ir juo labiau eiliniam blog’ui, buvo visai neaktualūs, tačiau jie jau veikia bent dalyje naršyklių.</p>
<p>Turint omeny, kad iš dalies HTML5 yra kuriamas kaip standartas, dokumentuojantis jau egzistuojančią tinklo ir naršyklių būklę, tai <code>canvas</code> yra tas dalykas, kuris turi mažiausiai palaikymo problemų (neskaitant vienos, ghkhmz, naršyklės). <a href="http://ajaxian.com/">Ajaxian</a> vos ne kas antrą dieną paskelbią kokį nors naują demo su <code>canvas</code>. <a href="http://www.nihilogic.dk/labs/mario/mario_small_music.htm">Super Mario</a> žaidimas – sukurtas prieš daugiau nei metus! Aš ir pats dar užpernai naudojau vieną iš jQuery pluginų grafikų paišymui.</p>
<p>Su <code>video</code> problemos yra kur kas didesnės. Kas nors dar atsimenat, kaip prieš daug daug metų tekdavo vargti ieškant codec packų? Internete tai būtų visos “video be pluginų (skaityti: Flash)” idėjos žudikas. Safari palaiko Quick Time, Opera 10 ir Firefox – OGG Vorbis ir Theora, Chrome – OGG ir H.264, ir nei vieni, nei kiti neketina pasiduoti.</p>
<p>Kodekų problema yra iš esmės tai, kad dauguma jų yra uždari, apsaugoti patentų ir brangiai kainuoja. Tie, kurie yra atviri – netenkina kokybės reikalavimų (Google, kaip didžiausias video turinio teikėjas, nenori naudoti OGG, nes na interneto srautas yra brangus dalykas).</p>
<h2>Ateitis</h2>
<p>Kadangi <a href="http://www.w3.org/News/2009#item119">XHTML2 mirė</a>, tai HTML5 lieka vienintelis ateities standardas. Ir jis nors ir nėra tobulas, tačiau panašu, kad neketina sugriauti egzistuojančio interneto. Naršyklės pradeda jį po truputį palaikyti, tinklo kūrėjai taipogi jau turi galimybę juo naudotis. Kartais atrodo, kad jis gal ir nėra reikalingas – juk internetas veikia ir dabar, tačiau tikrasis postūmis bus tada, kai paieškos robotukai pradės labiau gerbti semantinį tinklą. Tai nutiks tik tuo atveju, jeigu HTML5 bus naudojamas jau dabar – nereikia laukti galutinės W3C rekomendacijos (juk ji bus tik tada, kai bus 2 pilnai įgyventintos realizacijos).</p>
<h2>Šaltiniai ir tolesnis skaitymas</h2>
<ul>
<li><a href="http://html5doctor.com/">HTML5 doctor</a></li>
<li><a href="http://remysharp.com/2009/01/07/html5-enabling-script/">HTML5 enabling script</a></li>
<li><a href="http://www.sitepoint.com/article/html-5-snapshot-2009/">Yes, You Can Use HTML 5 Today!</a></li>
<li><a href="http://blog.whatwg.org/">HTML5 darbo grupės blog’as</a></li>
</ul>