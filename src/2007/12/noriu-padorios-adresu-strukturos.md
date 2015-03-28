---
published: 2007-12-07T09:40:03+00:00
tags: blogo-pradzia, geekiska-filosofija, semantinis-tinklas, semantiskas-tinklas, url, it-tinklo-kurimas
---

# Noriu padorios adresų struktūros

<p>Renkantis bet kokią web turinio valdymo sistemą vienas iš pagrindinių klausimų yra jos pritaikomumas SEO. Kaip žinia, gana svarbus to faktorius yra URL optimizacija. Kas yra optimalus URL galima diskutuoti daug, tačiau mano asmeniniai kriterijai yra šie:</p>
<ul>
<li>URL, kaip failų sistemos atspindys, reiškia failą</li>
<li>URL identifikuoja failo vietą – direktoriją, kurioje jis guli</li>
<li>URL identifikuoja failo turinį (failo pavadinimas – turinio pavadinimas)</li>
<li>URL identifikuoja failo tipą (pagal išplėtimą)</li>
<li>URL padeda indetifikuoti failo statiškumą/dinamiškumą</li>
</ul>
<p><span id="more-4"></span></p>
<h2>URL identifikuoja failą</h2>
<p>
Pati URL sąvoka reiškia būtent tai, kad jis yra <strong>nuoroda į kažkokį resursą</strong>. Jeigu kalbėti apie web svetaines – senų senovėje HTTP metodas GET reikšdavo “atsiųsk man šitą hipertekstinį failą, iš anos direktorijos, iš to serverio”. Tai be abejo tiko statiškam turiniui, ir atsiradus visokiai dinamikai tai nustojo šiek tiek galioti.
</p>
<h2>URL identifikuoja failo vietą</h2>
<p>
Aš esu per jaunas, kad atsiminti vienos dimensijos failų sistemas, nors ir teko naudotis santakomis, kurios užsikraudavo iš kasečių. Bet kuri padori <strong>failų sistema yra hierarchija</strong> suskirstyta į direktorijų medį, su failais juose. Bet kuri didesnė web svetainė taipogi turi savo struktūrą – dažniausiai užtenka elementaraus medžio. Kalbant apie blog’us – to pakanka.
</p>
<h2>URL identifikuoja failo turinį</h2>
<p>
Šitą principą jau seniai įsikando visi optimizuotojai ir dauguma turinio valdymo sistemų jam yra pritaikytos. Paprastais žodžiais kalbant – puslapio/įrašo <strong>turinys privalo sutapti su tuo, ką matome adrese</strong>, t.y. iš esmės su jo pavadinimu.
</p>
<h2>URL identifikuoja failo tipą</h2>
<p>
Žiūrint iš vartotojo pusės, jeigu adrese nesimato turinio formos – turinys gali būti pavojingas. Iš dalies, tai yra optinė apgaulė (hell – sandros papai ir panašūs virusai būtent remiasi tuo, kad vartotojas matydamas .jpg išplėtimą tikisi .jpg failo), tačiau aš visiškai nemėgstu spausti nuorodos ir ten netikėtai rasti PDF dokumentą. Ši taisyklė šiek tiek gadina reikalą, jeigu kalbame apie <i>mobile content</i>, nes priklausomai nuo aparato/naršyklės tenka keisti failo tipą (WML &lt;-&gt; cHTML, etc.), tačiau kol kas tą ketinu ignoruoti, nes pradžioje mano turinys vistiek nebus pritaikytas WAP’ui.
</p>
<h2>URL identifikuoja turinio statiškumą</h2>
<p>
Kaip jau minėjau aukščiau, atsiradus dinamiškam turiniui tinkle, šiek tiek nustojo galioti principas, kad URL rodo į failą. Mano nuomone, dinamiškumas turi būti atspindėtas <dfn title="paieškos parametrų eilutė?">query string</dfn> (elementariaus pavyzdys – paieškos filtras ir jo parametrai adrese). Jeigu kalbėti apie blog’us ir šiaip didžiąją dalį svetainių – <strong>turime gana statiškų resursų rinkinį</strong> (t.y. nekeičiančių savo prasmės ir turinio) – daug įrašų, kurie iš esmės tėra HTML failai, gulintys savo vietoje. Tam ir yra skirti <i>permalinks</i>.
</p>
<h2>URL ir SEO yra skirti žmogui</h2>
<p>
<a href="http://www.google.com/support/webmasters/bin/answer.py?hl=en&amp;answer=35769">Google savo nurodymuose</a> teigia, kad nereikėtų rūpintis puslapio optimizavimu robotams – reikia rūpintis vartotojais. Net jeigu dalis iš mano išvardintų reikalvimų adresui neturi jokios reikšmės paieškos robotams, jie yra svarbūs lankytojui. Gera nuoroda lengva dalintis, be to ji gerai atrodo ir <dfn title="Search Engine Results Page">SERP</dfn>. Šiuolaikiniame internete, paieškos robotai privalo prisitaikyti prie žmogaus ir prie internetinės realybės (t.y. didelio <i>bardako</i>), tačiau aš mėgstu tvarką ir prasmę. Adresas <code>/2007/12/noriu-padorios-adresu-strukturos.rss2.xml</code> man yra tiesiog malonesnis ir prasmingesnis už <code>/2007/12/noriu-padorios-adresu-strukturos/feed/</code> ar tuo labiau už <code>/index.php?p=4&amp;feed=rss2</code>
</p>
<p>Šiame įraše paminėjau tik esminius meta reikalavimus URL struktūrai – tačiau vien to geram adresui negana. Turint plačias galimybes, galima nesunkiai viską sugadinti, o be to žvelgiant iš SEO perspektyvos – yra ir keletas papildomų reikalavimų, kuriuos dera apžvelgti atskirai.</p>