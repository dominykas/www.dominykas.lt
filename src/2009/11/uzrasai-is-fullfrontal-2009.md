# Užrašai iš FullFrontal 2009

<p>Prėjusį penktadienį Brighton’e vyko FullFrontal 2009 JavaScript konferencija, kurioje turėjau progą apsilankyti. Tikrai nenusivyliau!</p>
<p>Šiame blogo įraše susidėjau tai, ką pasižymėjau pats sau beklausydamas kalbėtojų. Pačių kalbų tikrai neketinu aprašinėti – tai puikiai padarė Ajaxian (nuorodas pateikiu), o skaidrės taipogi prieinamos viešai.</p>
<p>Jeigu kažkuris punktas sudomino – palikit komentarą – išplėsiu!<br>
<span id="more-193"></span></p>
<h2><a href="http://www.wait-till-i.com/">Christian Heilmann</a> – Frontloaded and zipped up – do loose types sink ships</h2>
<p><a href="http://ajaxian.com/archives/full-frontal-09-chris-heilmann-on-javascript-security">Ajaxian santrauka</a>; <a href="http://www.wait-till-i.com/2009/11/21/frontloaded-and-zipped-up-the-full-frontal-2009-keynote/">skaidrės</a>; <a href="http://www.archive.org/download/FrontloadedAndZippedUp-FullFrontalJavascriptConference2009/FrontloadedAndZippedUp-FullFrontalConference2009.mp3">garso įrašas</a>.</p>
<ul>
<li>Apie “AJAX” programuotojus kalbama žymiai pagarbiau negu apie “JavaScript” programuotojus. <i>Abydna, vienok.</i></li>
<li>JS nėra programavimo kalba skirta kiekvienam – ir ne kiekvienas save vadinantis “tinklo kūrėju” turėtu ja užsiimti.</li>
<li>JS egzistavo gerokai prieš jQuery.</li>
<li>Naudojant JS kalbą, reikėtų ją naudoti taip, kaip ji buvo suplanuota – gana kurti įvairias abstrakcijas pagal tradicinius OO modelius. JS turi savo stilių – privalu jį išnaudoti ir įsisavinti.</li>
<li>Saugumo skylės (XSS, XSRF ir t.t.) yra <i>server-side</i> problema – JS dažniausiai yra nekaltas (nors ir išnaudojamas)</li>
<li>Nepamiršti: http-only sausainiukai sesijoms</li>
<li>Bet kuris API yra iš esmės saugumo skylė – Firefox greičiausiai yra pati nesaugiausia naršyklė būtent dėl savo plėtinių architektūros. Priminė kažkieno sakinį, kad mash-up’ai yra XSS atakos prieš save patį.</li>
<li>Išbandyti: dažnos ir paprastos apklausėlės kaip mokymosi metodas komandoje</li>
<li>Pasidomėti: adsafe.org saugumo rekomendacijos</li>
<li>Pasidomėti: <a href="http://code.google.com/p/google-caja/">Google Caja</a> (yra informacijos <a href="http://developer.yahoo.com/yap/guide/caja-support.html">ir YDN</a>)
<ul>
<li>Kas per saugumo skylė IE su <code>radio</code> mygtukais?</li>
<li>Kodėl <code><a href="http://www.positioniseverything.net/easyclearing.html">clearfix</a></code> nevartotinas pagal Caja?</li>
<li>Kodėl tiek daug CSS apribojimų?</li>
</ul>
</li>
<li><code>javascript:void(0)</code> turi mirti (žiauria ir negarbina mirtimi)!</li>
<li><a href="http://ejohn.org/">John Resig</a> yra, lyg ir, pažadėjęs, kad jeigu pakankamai žmonių to reikalaus – jQuery pritaikys Caja rekomendacijas</li>
<li>Pasidomėti: ar įmanoma padaryti <i>YQL injection</i>?</li>
<li>Pasidomėti: jau egzistuoja OAuth implementacija vien su JS</li>
</ul>
<h2><a href="http://robertnyman.com/">Robert Nyman</a> – JavaScript: from birth to closure</h2>
<p><a href="http://ajaxian.com/archives/full-frontal-09-robert-nyman-on-the-javascript-language">Ajaxian santrauka</a>; <a href="http://www.slideshare.net/robnyman/javascript-from-birth-to-closure">skaidrės</a>.</p>
<ul>
<li>Kas čia per įprotis, tikrinti ar dižiąjame ekrane bėgantis Twitter srautas yra cenzūruojamas? Įdomus kultūrinis pokrypis, besivystant technologijoms…
</li><li>Nepamiršt: skaityti <a href="http://dmitry.baranovskiy.com/">Dmitry Baranovskiy’o</a> blogą</li>
<li>Pasikartot: <code>typeof kint == 'undefined'</code> naudojimas</li>
<li>Pasidomėt: Koks yra globalus <code>this</code> Rhino variklyje (t.y. <code>window</code> atitikmuo naršyklėse)?</li>
<li>Pasidomėt: <a href="http://yuiblog.com/blog/2007/06/12/module-pattern/">YAHOO Module Pattern</a></li>
</ul>
<h2><a href="http://www.quirksmode.org/">Peter-Paul Koch</a> – W3C Widgets</h2>
<p><a href="http://ajaxian.com/archives/full-frontal-09-ppk-on-mobile-quirks-and-practices">Ajaxian santrauka</a>; <a href="http://www.quirksmode.org/blog/archives/2009/11/presentations_t.html">skaidrės</a>.</p>
<ul>
<li>Pasidomėt: Ar Nokia N900 naršyklė yra fennec? (Atsakymas: taip)</li>
<li>Mobilaus telefono naudojimas interneto naršymui yra puikus būdas pasimokyti – visos vartojiškumo pamokos gali būti pritaikytos eilinėms naršyklėms</li>
<li>Ar <code>@media</code> kartu su iPhone’o <code>&lt;meta name="viewport" /&gt;</code> galėtų išspręsti problemą, kad <i>user-agentai</i> savaip interpretuoja pločius kai svetainė yra <i>išzoominta</i>? (Prie alaus PPK patvirtino, kad ketina tą patikrinti artimiausiu metu)</li>
<li>Kai kuriuose aukšto DPI telefonuose kartais būna sunku paspausti tą vietą kurią nori – ar gali spaudimo jautrumo DPI ir ekrano DPI gali būti skirtingi?</li>
<li>Nejaugi mobilūs telefonai neturi “ilgai trunkančio skripto” perspėjimų?</li>
<li>Dėl greičio problemų, rekomenduojama nenaudoti <code>iframe</code> mobiliems telefonams skirtose svetainėse – kaip įgyventi AJAX-išką naršyklės istoriją (<i>back/forward</i>)?</li>
<li>Dingstantis ryšys yra problema – ir <code>online/offline</code> įvykiai jos visiškai nepadeda spręsti</li>
<li>Mobilių telefonų kešas yra ~200kb – būtina dar protingiau optimizuoti kodą</li>
<li>W3C specifikacijos <i>widgetai</i> leidžia tik vieną HTML puslapį – potenciali problema?</li>
<li>Dalintis <i>widgetais</i> per Bluetooth yra pavojinga</li>
<li>Animacijos efektai mobiliuose telefonuose veikia lėtai. Iš patirties – ne viskas taip jau blogai, bet optimizuoti ir apskritai elgtis protingai privalu</li>
</ul>
<h2><a href="http://www.kryogenix.org/">Stuart Langridge</a> – New things that HTML5 provides to JavaScript hackers</h2>
<p><a href="http://ajaxian.com/archives/full-frontal-09-stuart-langridge-on-html5-features">Ajaxian santrauka</a></p>
<ul>
<li>Pasidomėti: <a href="http://documentcloud.github.com/underscore/">underscore.js</a></li>
<li>Internetas jau nebėra “programų rašymo platforma”. Tavo <em>svetainė</em> gali būti ta platforma, jeigu atidarysi savo API. Ir net jeigu neatidarysi – yra GreaseMonkey. Reikia tam būti pasiruošus!</li>
<li>Idėja: naršyklių gamintojai, galėtų turėti standartinį būdą palaikymo tikrinimui, t.y. jeigu tu rašai savo kodą laikydamasis <i>progressive enhancement</i> principo, kartais turi paprastus būdus patikrinti, ar kažkas veiks – o kartais ne (pvz. Operos <code>&lt;event-source/&gt;</code>). O galėtų būti kas nors paprasto, pvz. <code>window.navigator.supports("event-source");</code></li>
</ul>
<h2><a href="http://twitter.com/toddkloots">Todd Kloots</a> – More accessible user interfaces with ARIA</h2>
<p><a href="http://ajaxian.com/archives/full-frontal-09-todd-kloots-on-aria-and-acessibility">Ajaxian santrauka</a>, <a href="http://www.yuiblog.com/blog/2009/11/23/video-kloots-yuiconf2009-a11y/">video įrašas</a> ta pačia tema iš YUI konferencijos</p>
<ul>
<li>Idėja: YUI3 šiuo moment palaiko ARIA pridėdami roles ir atributus elementams, su kuriais dirba, pvz. sukuriant YUI meniu JS, susiiję elementai yra teisingai pažymimi. Ar neturėtų viskas būti atvirkščiai? T.y. rolės ir atributai nustatomi tiesiai HTML dar serveryje, o YUI (ar kita biblioteka) inicializuojasi jau naudodami tas roles.</li>
<li>Toddas kalbėjo apie tai, kaip galima “uždėti ARIA sluoksnį savo sistemoje”. Bet argi nebūtų paprasčiau laikytis “ARIA palaikymo” kaip pagrindinio principo, t.y. tai yra kažkas tokio, ką tiesiog darai natūraliai, negu tai, ką darai pabaigoje, ant viršaus? Lygiai taip, kaip kažkada reikėjo pakeisti mastymą rašant HTML ir CSS, bei išmokti naudoti <i>progressive enhancement</i>, o ne <i>graceful degradation</i>.</li>
<li>YUI2 palaiko <i>“<a href="http://yuiblog.com/blog/2007/01/17/event-plan/">event delegation</a>“</i>? Čia nuo kada? (Atsakymas: pasirodo, nuo YUI 2.8 – pamiršęs buvau… <i>“event delegation”</i> valdo!)</li>
<li>Žmonės su normaliu regėjimu, turbūt savo protiniuose modeliuose (kaip išversti <i>mental model</i>?) turbūt be problemų priima, kad meniu dažnai eina iš kairės į dešinę. Kaip tai suvokia aklieji? T.y. kaip jų modeliai susitvarko su tuo, kad meniu navigacija vykdoma “kairė/dešinė” mygtukais, o ne “viršus/apačia”, kai naudojamos ekrano skaityklės?</li>
<li>Pasidomėti: ar ARIA turi kokį nors “fokusuotos grupės” apibrėžimą, o ne vien tik “fokusuoto elemento”?</li>
<li>Pasidomėti: <i>accessibility</i> šiuo metu dažniausiai siejasi su pele ir klaviatūra, kaip įvesties įrenginiais – kokie modeliai naudojami kitiems įrenginiams?</li>
<li>Pasidomėti: ką HTML5 specifikacija sako apie <code>&lt;section/&gt;</code> <i>web application</i> kontekste?</li>
<li>Pasidomėti: klaviatūros greitųjų klavišų atrandamumas lankytojams su <em>normalia</em> rega</li>
</ul>
<h2><a href="http://twitter.com/jaffathecake">Jake Archibald</a> – Optimising where it hurts</h2>
<p><a href="http://ajaxian.com/archives/full-frontal-09-jake-archibald-on-performance-optimisation">Ajaxian santrauka</a>; <a href="http://www.jakearchibald.co.uk/jsperformance/">tyrimas ir skaidrės</a></p>
<ul>
<li>Ar jis čia skaidres varto su savo WII kontroleriu? Geras!</li>
<li>Niekada nenaudoti <code>eval()</code>, ypač <i>closure</i> viduje – tai iš esmės nužudo visas JS variklių (V8, TraceMonkey ir t.t.) optimizacijas, nes <code>eval()</code> gali nesunkiai pakeisti kintamųjų aprėptį (kaip išversti <i>scope</i>?)</li>
<li>Nenaudoti <i>closure</i> per dideliam gyliui, jeigu galima to išvengti</li>
<li><em>Niekada nenaudoti</em> eilučių sujungimo, kai jos rašomos į <code>innerHTML</code>, t.y. ne <code>el.innerHTML="&lt;div&gt;"+kint+"&lt;/div&gt;"</code>, o <code>var s="&lt;div&gt;"+kint+"&lt;/div&gt;"; el.innerHTML=s;</code></li>
<li>Vengti <code>window.onunload</code> naudojimo, nes nužudomas kešinimas (jQuery jau turi šią problemą – bet ketina išspręsti)</li>
<li>Švarus ir paprastas HTML, neturintis bereikalingų tagų, pats savaime paspartina selektorių darbą (nes reikia perfiltruoti mažesnį kiekį elementų). Žodžiu, rašyti didelį kiekį nesemantinio HTML (ar tai būtų nereikalingi <code>div</code>, ar <code>table</code>) yra blogai!</li>
<li>Kiekvienas turėtų pasimokyti pats rašyti vykdymo greičio testus (tik reikia nepamiršti apie “<a href="http://ejohn.org/blog/accuracy-of-javascript-time/">16ms problemą</a> JS”)</li>
<li>“Optimizuok ten kur skauda” iš tikro tereiškia “nebūk durnas” – visos diskusijos, apie tai kuris ciklas optimalesnis (<code>for</code> prieš <code>while</code>) yra bevertės (nes sutaupo 0.002 <em>mili</em>sekundės). Iš tikro reikia izoliuoti tą dalį, kuri veikia lėčiausiai, ir tvarkyti būtent ją. Vargti stengiantis rašyti “teisingą kodą” iš anksto yra beprasmiška – žinot istoriją su “priešlaikine optimizacija”, ar ne?</li>
</ul>
<h2><a href="http://simonwillison.net/">Simon Willison</a> – Beating server side engineers in their own game</h2>
<p><a href="http://ajaxian.com/archives/full-frontal-09-simon-willison-on-server-side-javascript-and-node-js">Ajaxian santrauka</a>; <a href="http://simonwillison.net/2009/Nov/23/node/">autoriaus santrauka</a></p>
<ul>
<li>Pasidomėti plačiau apie <a href="http://en.wikipedia.org/wiki/ECMAScript_for_XML">E4X</a></li>
<li>Mac’ų vartotojai elgiasi… kitaip. Tiesiog kitaip ir tiek.</li>
<li>Ar eitų NodeJS panaudoti kaip <i>unit testų</i> konsolę? Integruoti į <i>continuous build’us</i>?</li>
<li>JS nėra “strongly typed” kalba – tai natūraliai yra sunkiau dirbant komandoje. Pasidomėti: kaip tai galima spręsti</li>
<li><a href="http://nodejs.org/">NodeJS</a> ir <a href="http://couchdb.apache.org/">CouchDB</a> yra labai labai <i>seksi</i>! Kiekvienas turėtų pasidomėti kaip jie veikia, kaip optimizuoja procesus ir kokiais principais yra paremti!</li>
</ul>