# Paranoja: HTML5

<p>Vakar pagaliau prisiverčiau atidžiai perskaityti prieš kelias savaites paskelbto HTML5 juodraščio skyrių apie <a href="http://www.w3.org/html/wg/html5/diff/">skirtumus nuo HTML4</a>. Skaičiau ir norėjau verkti. Kažko pastaruoju metu <a href="https://www.dominykas.lt/2008/01/kas-kaltas.html">dažnai taip nutinka</a> skaitant ką nors apie technologijas – matyt ištižėlis pasidariau… Arba tiesiog <a href="http://www.visitmalta.com/">trūksta atostogų</a>.<br>
<span id="more-34"></span><br>
O dėl verkimo, tai jis turi kelias labai konkrečias priežastis:</p>
<ul>
<li><strong>Džiaugsmas</strong>, dėl tobulėjimo, naujų galimybių, semantiškumo;</li>
<li><strong>Nusivylimas</strong>, kad tai kas aprašyta specifikacijoje, turėsime (su implementacija) tik po, geriausiu atveju, penkių, jeigu ne penkiasdešimties, metų;</li>
<li><strong>Pyktis</strong> su klausimu “koks idiotas sugalvojo, kad tai yra reikalinga”;</li>
<li><strong>Tragiška panika</strong>, kad naujasis HTML5 suteiks galimybę Microsoft padaryti dar daugiau klaidų Internet Exploreryje….</li>
</ul>
<h2>Žingsnis į priekį</h2>
<p><a href="http://www.ibm.com/developerworks/library/x-html5/">Pirmą kartą skaitydamas</a> apie tuos skirtumus atkreipiau dėmesį tik į naujus elementus. Labiausiai džiaugiuosi struktūriniais <code>&lt;section&gt;, &lt;article&gt;, &lt;header&gt;, &lt;footer&gt;, &lt;aside&gt;</code> elementais – jie bus <strong>labai naudingi SEO požiūriu</strong>. Didžioji dalis kitų naujų tag’ų taipogi nėra blogi iš esmės – jie visi turi savo pritaikymą.</p>
<h2>Du žingsniai atgal</h2>
<p>Na, dėl žengimo atgal gal per daug griežtai pasakyta, tačiau kai kurie dalykai atrodo mažų mažiausiai keisti. Labiausiai mane <strong>neramina esminiai pasikeitimai formose</strong>. Aš tikrai nepeikiu tų idėjų, netgi atvirkščiai – džiaugiuosi jomis, tačiau didysis klausimas yra <strong>ar šioms naujovėms vieta HTML standarte</strong>?</p>
<p>Nepaisant to, kad <code>&lt;input&gt;</code> elemento tipas <code>datetime</code> yra tikrai reikalingas, tereikia tinkamai apibrėžti siuntimo standartus į serverį (nes atvaizdavimo formatas skirtingas priklausomai nuo vartotojo lokalės), jis sukelia <strong>neigiamą postūmį tinklo kūrėjams</strong>.</p>
<h2>HTML mokymosi kreivė</h2>
<p>Daugiau nei pusė “PHP programuotojų”, kurie ateidavo pas mane į pokalbius dėl darbo, nežinojo arba <strong>nesugebėdavo apibrėžti kas yra “SQL injection”</strong>. Natūralus klausimas yra ar tie programuotojai suvoks kad <code>email</code> lauke įvestus duomenis reikia vistiek tikrinti ir server-side? Nemanau. Be abejo, galimi kažkokie priverstiniai sprendimai, kad ir reikalavimas kartu su siunčiama forma perduoti metaduomenis apie laukų tipus. juos automatiškai patikrintų, kad ir tas pats PHP – tačiau tam gali prireikti ir pakeitimų HTTP standarte – kas sukuria tik <strong>dar didesnį sniego kamuolį</strong>, besiritantį žemyn nuo kalno.</p>
<p>Be abejo, galimas kontra-argumentas yra tai, kad <strong>svetaines turėtų kurti profesionalai</strong>, bet juk HTML visada buvo standartas, kurio mokymosi kreivė nėra labai stati, be to idėja prieštarauja <i>user-generated content</i> principui. Kažkada žaidžiant žaidimus, teko susidurti su penkiasdešitmetėmis mamytėmis, kurios prižiūrėdamus vaikus, be didelio vargo tvarkydavo savo sritį žaidėjų aliansų svetainėse. Profesionalūs programuotojai jau beveik išmoko <strong>“teisingo HTML” taisykles</strong> – tačiau didžioji dauguma žmonių, kuriems teks susidurti su tuo, <strong>niekada nevargs dėl jų</strong>, bet puslapius tvarkyti norės. Tokie žmonės visada galvos <q>“Štai įdedu čia <code>number</code> lauką ir jis automatiškai išsisaugo duomenų bazėje – puiku! Paprasta! Dabar pradėsiu profesionalią tinklo kūrėjo karjerą!”</q></p>
<h2>Daugiau medžių</h2>
<p>HTML5 specifikacija gan neblogai atspindi tam tikras Web 2.0 tendencijas, o ypač – AJAX paplitimą. Tai ryškiai matosi iš tokių naujų atributų kaip <code>contenteditable, contextmenu, draggable, ping</code> ar elementų <code>&lt;menu&gt;, &lt;progress&gt;</code>. Vėlgi – beprotiškai džiaugiuosi didžiąją jų dalimi. Kasdieniame darbe ne kartą apie juos teko pasvajoti (tol kol nepradėjau žaisti su <a href="http://code.google.com/webtoolkit/">GWT</a> – JavaScript nėra pati dėkingiausia programavimo kalba).</p>
<p>Tačiau <strong>ar tikrai HTML yra ta kalba, kuria derėtų aprašinėti turinio <em>valdymo</em> sistemas</strong>? Kiek pamenu, HTML buvo sukurta tam, kad sužymėti hiper-tekstą – tai yra dokumentą su išorinėmis nuorodomis. Evoliucija link semantiško HTML yra natūrali. Tačiau realybėje tinklas išsiplėtė ir “interneto svetainė”, dabar gali reikšti ir “tinkle veikiantis programinis paketas” (think: Google Apps). Lyg ir nebūtų problemos tame, tačiau tą evoliuciją griauna esminis rudimentas:</p>
<blockquote><p>To keep the authoring language relatively simple <strong>for authors</strong> several elements and attributes <strong>are not included</strong> &lt;..&gt; <strong>User agents</strong>, however, will always <strong>have to support</strong> these older elements.</p>
</blockquote>
<p>Ši frazė iš esmės reiškia, kad kūrėjas neturi teisės naudoti tam tikrų senų elementų, bet naršyklės privalo juos palaikyti. Sakyčiau visiškas absurdas. Panašiai kaip ir su greičio limitais. Mieste lyg ir 50km/h, bet Vilniuje visi važiuoja 70km/h ar greičiau. Tai kur gi dingo ta aktyviai W3C propaguojama semantika? Iš vienos pusės jie nori suteikti kuo daugiau lankstumo, tačiau tuo <strong>sukelia absoliutų chaosą</strong> savo diegiamoje tvarkoje. Iš vienos pusės jie skatina naudoti CSS turinio formatavimui, tačiau iš kitos – bando palikti meniu iš “tipinio interfeiso”. Tiesa, neįsivaizduoju kaip galima būtų su CSS aprašyti iššokantį kalendorių (kurį sukuria naršyklė, pagal OS standartus). Nors… ne bėda juk. &lt;SELECT&gt;’ų po IE neina formatuoti – matyt teks gyventi šiame pragare ir toliau…</p>
<h2>Šaunam į kiškius</h2>
<p>Kaip ten bebūtų – pagrindinė <strong>W3C problema kuriant HTML5 yra siekimas patenkinti visus</strong>. Tiek naršyklių kūrėjus, tiek tinklo kūrėjus. Tiek patyrusius HTML ekspertus, tiek entuziastiškus mėgėjus. O juk jie galėtų atsižvelgti į vieną elementarią usability taisyklę – ekspertai nepyksta, kai dalykai yra pritaikyti <del>kvailesniems</del> mažiau patyrusiems už juos ir todėl yra nesudėtingi.</p>
<p>Juk galima vos vos pataisyti esamą HTML standartą, iš jo pašalinant kelis “per sudėtingus” elementus bei neįtraukiant naujovių ir publikuoti tai kaip <i>HTML5 basic</i>. O visus sudėtinguosius dalykus perkelti į <i>HTML5 strict</i> standartą, kuriame vertinimas būtų daug griežtesnis. Panašiai jau yra padaryta su HTML4, tačiau svarbiausias dalykas kurio reikia – norint naudoti pažangius dalykus, privalu naudoti <em>strict</em> standartą. Tai yra, mamytė kovinio alianso žaidime vadovė ir toliau gali naudoti paprastą HTML, o komanda, kurianti corporate level web programą būtų <strong>priversta <em>pilnai</em> laikytis standartų, nes kitaip aplikacija neveiktų išvis</strong>.</p>
<p>Labiausiai paguodžiantis, tačiau tuo pačiu virkdantis dalykas visame dokumente yra ši eilutė:</p>
<blockquote><p>The HTML 5 specification will not be considered finished before there are at least two complete implementations of the specification.</p>
</blockquote>
<p>Paguodžia todėl, kad jeigu Microsoft nesugebės to įdiegti 19.5 IE versijoje be klaidų – jie atsiliks. Virkdo dėl dviejų priežasčių. Pirma – Microsoft pasakys, kad standartas yra tai, kaip klaidos veikia 19.5 IE versijoje, o antra – tinklo kūrėjai pirmo žingsnio diegiant standartus negalės žengti, o naršyklių kūrėjai gali gerokai užtrukti priiminėdami sprendimus, nes visi kabės ore dėl galimų pasikeitimų standarto specifikacijoje.</p>