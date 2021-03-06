---
published: 2011-03-07T02:45:26+00:00
tags: css3, html5, javascript, mobilus tinklas, tinklo kūrimas
---

# Savaitgalio eksperimentas: Login 2011 programa, pritaikyta mobiliems telefonams

<p>Per paskutinius kelis metus perskaičiau šimtus blogų, apie tai, kaip internetus reikia kurti galvojant apie nešiojamus įrenginius mažais ekranais, ir kaip gražiai viskas galėtų veikti, jeigu laikytis standartų. Deja – šio savaitgalio eksperimentas parodė, kad tokiai filosofijai dar kiek per anksti.</p>
<p>Bendrai paėmus, kadangi investavau tik pusantros dienos darbo, rezultatas visai patenkinamas – <a href="http://dominykas.net/login/">“mobili” Login 2011 programa</a>. Informaciją nukopijavau iš <a href="http://www.login.lt/">oficialios svetainės</a> – tikiuosi savininkai nesupyks.<br>
<span id="more-355"></span><br>
Žvaigždutės veikia ir turėtų atsiminti nustatymus iš <code>localStorage</code>, taipogi turėtų veikti ir offline, jeigu išsisaugoti “darbastalyje” (bent jau su Android 2.2). <i>Back</i> mygtukui sutvarkyti laiko pritrūkau, taipogi vietomis matosi animacijos šokčiojimai ir trūkčiojimai.</p>
<p>Pirmojoje versijoje, kurią išmečiau, bandžiau viską pasiekti apskritai be Javascript, <a href="http://webdesignernotebook.com/css/the-css3-target-pseudo-class-and-css-animations/"><code>:target</code> pseudo-selektoriaus</a> pagalba, tačiau rezultatas gavosi gerokai prastesnis negu galutinis variantas.</p>
<p>Taipogi peržvelgiau akimis <a href="http://www.phonegap.com/tools">Phonegap rekomenduojamus įrankius</a>, tačiau panašu, kad visi jie kenčia nuo tų pačių problemų – mobilios naršyklės labai jautriai reaguoja į ekrano pločio/aukščio pasikeitimus kai tenka animuoti perėjimus iš vieno ekrano į kitą, o išsprendus šią problemą kiek griežtesniais išdėstymo apribojimais, vistiek lieka <i>scrollinimo</i> problema – sugrąžinti vartotoją į tą pačią ekrano vietą be ekrano mirksėjimo ir šokinėjimo yra neįmanoma.</p>