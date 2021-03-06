---
published: 2008-05-27T00:18:12+00:00
tags: css, eksperimentai, html, kodas, tinklo kūrimas
---

# Horizontalus centravimas

<p>Šitas įrašas yra visai ne apie tai, kas būtų jeigu Sabonis žaistų krepšinį gulėdamas ant grindų (tiesa, esu įsitikinęs, kad jis tai darytų puikiai). Ir tikiuosi iš pirmojo sakinio supratote, kad nesusipainiojau ir (beveik) neketinu kartotis <a href="http://www.jakpsatweb.cz/css/css-vertical-center-solution.html">vertikalaus centravimo</a> tema.</p>
<p>Dažniausiai norint nežinomo pločio elementą išcentruoti horizontaliai kitame elemente problemų nekyla – užtenka tiesiog paprasto <code>text-align:center;</code> ar kiek sudėtingesnio <code>display:block; margin-left: auto; margin-right: auto;</code>. Šie abu variantai netinka tuo atveju, kai vidinis elementas yra platesnis negu išorinis. Jeigu tas vidinis elementas yra paveiksliukas, jį galima perkelti į foną ir uždėti <code>background-position: 50% 50%;</code>, tačiau kartais tiesiog nėra techninės galimybės nenaudoti <code>&lt;img&gt;</code>, o galbūt kai kam kiltų noro ir žaisti su kitokiais elementais.</p>
<p><span id="more-62"></span></p>
<p>Alternatyvus variantas, be abejo, yra naudoti tam JavaScript, tačiau pritaikom Auksinę Gero Tinklo Taisyklę: HTML naudojamas aprašymui (<i>mark-up</i>), CSS atvaizdavimui (<i>presentation</i>), o JS elgsenai/veikimui (<i>behavior</i>)- centravimas yra atvaizdavimas, taigi JS netinka.</p>
<h2>Praktinė užduotis</h2>
<p>Turime didelę duomenų bazę, kurioje sukauptas kalnas sumažintų paveiksliukų (<i>thumbnails</i>). Dauguma jų yra 150px pločio, tačiau pasitaiko ir kitokių. Kaip juos visus “apkarpyti” parodant tik vidurinę dalį 100px pločio rėmelyje? Galima naudotis tik CSS ir <code>&lt;img&gt;</code> dėl <i>accessibility</i>.</p>
<h2>Sprendimas: kaip centruoti nežinomo pločio vidinį elementą</h2>
<p><em>Nustok man kvaršinti galvą ir duok <a href="http://code.dominykas.com/css/centering/">pilną sprendimą</a>.</em></p>
<p>Jeigu turime fiksuoto pločio išorinį rėmelį, ir visiškai nežinomo pločio (platesnį arba siauresnį) vidinį elementą, tenka šiek tiek pavargti. Matematika atrodytų paprasta – kažkokiu būdu pastumti vidinį elementą per pusę išorinio elemento pločio, ir patraukti atgal per pusę vidinio elemento pločio, taip sulygiuojant jų centrines linijas. Lengviau pasakyti, negu padaryti…</p>
<h3>Pirmas žingsnis – pastumiam į šoną</h3>
<p>Išoriniam elementui <code>.frame</code> uždedame fiksuotą plotį ir <code>overflow: hidden;</code>, kad jokie išsiplėtę vidiniai elementai jo nepakeistų. Tada sukuriame pirmą vidinį rėmelį perkėlimui – <code>.shiftLeft</code>, kuris paprasčiausiai turi papildomą paraštę, kurios plotis yra pusė išorinio rėmelio. Sprendime naudoju pikselius, bet manau, kad turėtų veikti ir procentai.</p>
<h3>Antras žingsnis – patraukiam atgal</h3>
<p>Patraukti vidinį elementą per pusę jo paties pločio atgal yra kiek sudėtingiau – panaudoti neigiamos paraštės negalima, nes <strong>paraščių procentiniai pločiai</strong>, pagal standartus, <strong>yra skaičiuojami nuo tėvinio elemento pločio</strong>. Šią problemėlę galima išspręsti, jeigu vidinis elementas yra <i>“plaukiojantis”</i>. Kadangi kai kurios naršyklės <em>(ghkhmz)</em> tai palaiko ne visai tiksliai – tenka naudoti du elementus – vienam jų (<code>.floatToFix</code>) uždėti <code>float</code> ir užfiksuoti plotį, o su kitu (<code>.unshift</code>) traukti atgal. Į <code>.unshift</code> vidų jau galime įdėti neapibrėžto pločio paveiksliuką – nerekomenduočiau jam pačiam taikyti patraukimo atgal klasės…</p>
<h3>Trečias žingsnis – sprendžiam problemas</h3>
<p>Gana dažnai dėl klaidos kode (<i>double margin bug</i>) tam tikra naršyklė <em>(ghkhmz)</em> pritaiko dvigubą plotį plaukiančių elementų paraštėms – tai galima spręsti su <code>display: inline;</code>, tačiau šiuo atveju vistik tenka traukimo veiksmą pakeisti iš paraščių į santykinį pozicionavimą ir panaudoti tiesiog neigiamą <code>left: -50%;</code>. Su tuo santykiniu patraukimu atsiranda kita problema (toje pačioje, tam tikroje, naršyklėje <em>(ghkhmz)</em>) – vidinis elementas išlipa į viršų ir nebepaiso <code>overflow</code>. Tai galima išspręsti nustatant <code>position: relative;</code> ir visiems tėviniams elementams.</p>
<h2>Galutinis sprendimas</h2>
<p>Kažkodėl pažvelgus į jo kodą, atrodo, kad viskas taip elementaru, tačiau teko gerokai paeksperimentuoti, kol pasiekiau <a href="http://code.dominykas.com/css/centering/">veikiantį variantą</a>. Kas keisčiausia, vos vos jį pakeitus viskas sugriūna! Panašu, kad galutinė versija veikia teisingai su:</p>
<ul>
<li>Internet Explorer 6</li>
<li>Internet Explorer 7</li>
<li>Firefox 2</li>
<li>Opera 9.26</li>
<li>Safari 3.1</li>
</ul>
<p>Su Safari, tiesa, kartais atsiranda gana keistas perpiešimo efektas – dalis vidinio elemento pradingsta, tačiau pakeitus lango dydį viskas sugrįžta į vietas. Jeigu kas galite patikrinti su kitomis naršyklėmis – būtų malonu išgirsti rezultatus, o šiaip jeigu prireiks šio sprendimo – naudokit į sveikatą ir neminėkit piktuoju, jeigu kas nors neveiks. Bandysiu pritaikyti ir vertikalų centravimą, tačiau bijau, kad aukštesniems elementams jis neveiks… Todėl eksperimento rezultatuose yra variantas, kuris pakeičia vidinio paveikslėlio aukštį – darant tai naršyklėje vaizdas kiek sugenda, tačiau galbūt geriau negu nieko?</p>