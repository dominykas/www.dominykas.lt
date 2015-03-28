---
published: 2009-07-14T23:30:16+00:00
tags: javascript, usability, uzknisantys-dalykai-internete, it-tinklo-kurimas
---

# Formų validacija: netrukdyk man!

<p><cite>Alanas Cooperis</cite> savo knygose pastoviai kartoja, kad blogiausias dalykas, kurį galima padaryti vartotojui, tai priversti jį jaustis kvailu. Bene lengviausia šį “tikslą” pasiekti yra validacijoje – kiekvienas bereikalingas klaidos pranešimas ir kiekviena sistema, kuri man trukdo daryti dalykus mano būdu, tiesiog ir verčia mane daužyti galvą į sieną su klausimu “<i>Nu</i>, kodėl šito reikia?” Šiandien aptikau puikų to pavyzdį:</p>
<pre>function isNumberKey(evt)
{
     var charCode = (evt.which) ? evt.which : event.keyCode
     if (charCode &gt; 31 &amp;&amp; (charCode &lt; 48 || charCode &gt; 57))
        return false;

     return true;
}</pre>
<p><span id="more-139"></span><br>
Ši funkcija naudojama kaip <code>onkeypress</code> <i>event handler</i>. Ką ji daro iš tikro? Kai įvesties lauke paspaudžiamas klavišas, kuris nėra skaičius, ir nėra vienas iš kontrolinių klavišų (<kbd>Enter</kbd>, <kbd>Backspace</kbd> ir tt), klavišo paspaudimas yra sustabdomas ir ignoruojamas. Konkrečiu atveju, man reikėjo įvesti svetainėje savo 8 skaitmenų prisijungimo kodą, na ir lyg būtų logiška, kad man nereikia spausti kitų klavišų, tik skaičius, ir po to <kbd>Tab</kbd>, kad įvesti slaptažodį. <strong>Netiesa!</strong></p>
<p>Visiškai galima kombinacija, kurią galiu įvesti yra <kbd>Ctrl+V</kbd>. Nes paprasčiausiai naudojuosi konkrečia svetaine kartą per metus, todėl prisijungimo vardą, kuris yra generuojamas automatiškai, galiu surasti tik el. pašto archyve. Ar tai veiks? Be abejo ne (išskyrus Chrome – nesigilinau kodėl), nes tokio paspaudimo atveju <code>charCode</code> bus lygus 118, t.y. “v” raidės ASCII kodas, ir mano <i>Paste</i> veiksmas bus sustabdytas.</p>
<h2>Patarimas: leisk vartotojui elgtis kaip jis įpratęs</h2>
<p>Galima, be abejo sakyti, kad prisijungimo formoje tokia validacija išvis nereikalinga, nes įvedus neteisingą vartotojo vardą (pvz. <code>' OR ''='</code>), prisijungti tiesiog nepavyks, su pranešimu “Neteisingas vartotojo vardas ir/arba slaptažodis”. Tačiau lygiai taip pat galima teigti, kad siekiama vartotoją apsaugoti nuo to klaidos pranešimo, arba, kad toks validacijos veikimas kai kuriais atvejais gali būti pageidautinas. <strong>Netiesa!</strong></p>
<h2>Patarimas: nepasikliauk naršyklės API</h2>
<p>Javascript palaikymas interneto naršyklėse yra labai ribotas. Jis negali suteikti standartinių OS galimybių, kaip pvz. garsinis signalas paspaudus netinkamą klavišą. Negana to, konkrečioje formoje nėra suteikiama jokių užuominų, kad “leidžiama įvesti tik skaičius” (tuo atveju galima būtų tiesiog keikti programuotoją, už neteisingą vykdymą). Tačiau net jeigu viso to implementacija būtų teisinga, o puslapis pateiktų visas užuominas apie tai, ką galima daryti ir ko negalima, vistiek aš pasisakyčiau prieš tokį dalyką, ir ne vien tik todėl, kad <a href="http://www.quirksmode.org/blog/archives/2009/03/testing_mobile_1.html#link10">Nokia telefonai neteisingai perduoda <code>keyCode</code></a>.</p>
<p>Dar vienas pavyzdys būtų validacijos vykdymas, kai nuspaudžiamas <kbd>Enter</kbd> klavišas – ši problema mane nervuoja pragare, kuris vadinamas <a href="http://www.o2.ie">o2.ie</a> kasdien. Kodėl? Ogi tiek Firefox, tiek Chrome (su Opera svetainė neveikia išvis) <i>autocomplete</i> pasirinkus reikšmę, ir paspaudus <kbd>Enter</kbd>, įvykis perduodamas į Javascript, todėl pasirinkęs iš sąrašo savo telefoną, gaunu malonų pranešimą, kad neįvedžiau slaptažodžio, nors dar net nespėjau prieiti iki to žingsnio!</p>
<h2>Patarimas: nedėk apribojimų ten, kur jie visiškai nereikalingi</h2>
<p>Problema slypi tame, kad ribojama mano veiksmų laisvė. Neverta to daryti. Štai pvz. <code>textarea</code> elementas neturi <code>maxlength</code> atributo – galima to palaikymą sukurti su JS, bet daug geresnis variantas yra tiesiog parodyti kiek yra likę galimų įvesti simbolių, o <strong>klaidos pranešimą rodyti tik tada, kai klaida yra <em>tikrai</em> padaryta</strong>. Įsivaizduokite, jei Twitter neleistų įvesti daugiau negu 140 simbolių ir nesuteiktų galimybės redaguoti tekstą tol, kol jis telpa į juos.</p>
<p>Lygiai taip ir šiuo validacijos atveju, derėtų leisti vartotojui spausti tuos klavišus, kuriuos jis nori spausti, o įvestus duomenis tikrinti tik tada, kai vartotojas pasako “taip, aš žinau, kad noriu tokius duomenis išsiųsti”, t.y. <code>onsubmit</code> įvykio metu, arba tiesiog <i>server-side</i>.</p>