---
published: 2008-11-17T23:59:53+00:00
tags: ateitis, idėjos, semantinis tinklas, geekiška filosofija
---

# Kontrolės inversija socialiniame semantiniame tinkle

<p>Ilgas laikas nėra rašymas. Statistika: pradėjau šį įrašą prieš gerus keturis mėnesius (ša, žinau, kad kitą pradėjau prieš beveik metus), todėl gavosi kiek per ilgas… Pradžia – ganėtinai techniška ir apie programavimą, bet pats įrašas iš tikro tėra apie idėją ir svajonę. <strong>Kodėl įvairiose svetainėse turiu registruotis aš, o ne svetainės registruojasi pas mane?</strong> <em>Neaušink burnos, man neįdomu – <a href="/2008/11/kontroles-inversija-socialiniame-semantiniame-tinkle.html#20081117-santrauka">duok santrauką</a>.</em></p>
<p><span id="more-66"></span></p>
<h2>Kontrolės inversija</h2>
<p>Vienas iš objektinio programavimo principų – klasės ir objektai turi būti sukurti taip, kad būtų lengvai perkeliami į kitą kontekstą, o jų vidinis veikimas turėtų būti niekam neaktualus. Tradiciškai, įvairūs programavimo varikliukai (<i>framework</i>) būdavo funkcijų bibliotekos. Programuotojas atsirinkdavo ir iškviesdavo reikalingus varikliuko elementus. Nesigilinant į smulkmenas, toks būdas dažnu atveju gali būti kiek suoptimizuotas – mano manymu, <strong>geras variklis yra ne funkcijų rinkinys, o programavimo taisyklių (<i>coding conventions</i>) kodeksas</strong>, kurio laikantis dalykai “įvyksta” automatiškai. Wikipedija <a href="http://en.wikipedia.org/wiki/Inversion_of_control">Inversion of Control</a> apibūdina labai gražiu “Holivudo principu”: <strong>neskambinkite mums, mes paskambinsime jums</strong> (angliškai šis žodžių žaismas programavimo kontekste skamba geriau). Pvz. vietoj to, kad konkrečią užduotį vykdantis kodas susirinktų duomenis pats, visą informaciją jam surenka ir paduoda variklis, nes to reikalaujanti klasė yra aprašyta (sukurta) taip, kad variklis atpažintų kokie duomenys yra reikalingi (<a href="http://en.wikipedia.org/wiki/Dependency_injection">dependency injection</a>).</p>
<p>Apvertus kontrolę ir daugiau darbo atidavus užkulisinėms jėgoms, perkeliamumo principas gali būti įgyvendintas efektyviau – konkrečią užduotį atliekantis kodo gabalas (klasė) yra rašomas taip, kad atliktų <em>tik</em> savo užduotį, nepriklausomai nuo variklio. Laikantis tokios filosofijos yra kuriamas <a href="http://www.springframework.org/">Spring Framework</a>. Iš jos išplaukia ir daugiau patogumų, kaip kad programavimas tiesiog nurodant kas yra kas (<a href="http://en.wikipedia.org/wiki/Declarative_programming">declarative programming</a>). Tokie metodai leidžia valdyti kodą ir kurti sprendimus daug greičiau ir efektyviau. Verslo klausimo, per kiek laiko atsiperka <i>frameworko</i> kūrimas, šiuo atveju nenagrinėju.</p>
<h2>Online bendruomenių ypatumai</h2>
<p>Viskas paprasta kaip trys kart aštuoni ir galioja ne tik internete – bet kurioje bendruomenėje išryškėja lyderiai, o ten kur yra lyderiai – yra ir nepatenkintų. Kai kurios bendruomenės yra sukurtos taip, kad jos įkūrėjas turi aukščiausią balsą, kitose galioja “demokratija”. Nepaisant visko – ilgainiui vistiek išsiveržia asmenybės ego, kad bendruomenė turi elgtis taip, kaip atrodo kažkuriam (kiekvienam) individualiam nariui.</p>
<p>Kalbant apie forumus arba pažinčių svetaines, gana lengva pastebėti, kad kažkodėl <strong>atsiranda narių, kurie mano, kad tai yra <em>jų</em> nuosavybė</strong>. Šitas veiksnys priklauso nuo lyderių vaidmens ir bendruomenės dydžio, tačiau natūralus instinktas yra galvoti “vat jeigu aš čia būčiau vadas, tai padaryčiau tvarką”.</p>
<h2>Semantinis tinklas į pagalbą</h2>
<p>Grįžtam prie pradinio klausimo (scrollink į viršų ir pasikartok). Atsakymai paprasti:</p>
<ul>
<li>stagnuojantys verslininkai bijo, kad technologijų, kurios tai leis, tobulinimas yra negrįžtama investicija</li>
<li>stagnuojantys verslininkai bijo, kad “jų” klientai tokiu būdu gali nutekėti pas konkurentus</li>
<li>neišspręsta potencialių spam-cialinių tinklų problema</li>
<li>techninis barjeras kol kas dar nėra įveikiamas eiliniam Jonui</li>
</ul>
<p>Kalbant apie technologijas – sprendimas jau iš esmės yra surastas – reikalinga tik protinga integracija tarp <a href="http://openid.net/">OpenID</a>, <a href="http://www.foaf-project.org/">FOAF</a>, protingų socialinių tinklų kūrimo <i>agentų</i> ir laisvai prieinamos bei privatumo nepažeidžiančios neutralios terpės, kurioje ta integracija gyventų. Štai jums modelis:</p>
<ol>
<li>Protingas agentas ateina į mane aprašantį resursą (terpė mano atveju turbūt būtų mano blog’as, kitų žmonių atveju – tegul ir Facebook ar pazintys.lt anketa – jokio skirtumo)</li>
<li>Protingas agentas randa mane aprašantį <a href="http://wiki.openid.net/Delegation">OpenID tag’ą</a>, taipogi viešą informaciją apie mane ir paprašo leidimo gauti daugiau informacijos – <strong>kontrolės inversija įvyksta būtent čia</strong></li>
<li>Atėjęs į savo informacijos valdymo erdvę, aš randu, kad protingas agentas buvo apsilankęs ir susidomėjo manimi – pagal tai aš nusprendžiu kokio tipo informaciją aš noriu jam rodyti – visus “draugus”; draugus, kurie jau yra mano LinkedIn; jokių draugų – tik merginas; tik tuos, su kuriais susirašinėju per GTalk; tik vyresnius nei 18 pažįstamus, iš mažo, giliai paslėpto forumo; tik <i>(įrašyk pats)</i></li>
<li>Protingas agentas, gavęs mano leidimą, kaupia informaciją ir naudoja ją savo tikslams, tuo pačiu man pranešdamas apie mano draugus ir draugų draugus atgal į mano asmeninę konsolę</li>
<li>Aš niekada nesilankau protingo agento svetainėje, nes neturiu jokio noro ten eiti, tačiau jeigu nuspręsčiau ten eiti – identifikuočiausi su tuo pačiu savo OpenID</li>
</ol>
<p>Panašiu principu duomenis apie mane jau kaupia <a href="http://www.pipl.com/">Pipl</a> – skirtumas tik tas, kad jie manęs neprašė jokio leidimo. Todėl ir neturi daugiau duomenų apie mane, o jų robotas nors ir veikia gana įspūdingai, gūglinti ir daryti rimtų išvadų apie mano alternatyvias personas dar nemoka. <i>Side note</i>: jei kas paaiškintų ką ten reiškia tag’ai “Gio” ir “Iya” prie mano profilio, būčiau labai dėkingas…</p>
<p>Apie kovą su spam’u aš išmanau nedaug, tačiau jeigu last.fm sugeba rekomenduoti muziką, ir daryti tai daugiau mažiau taikliai, tai lygiai tokiu pačiu principu gali veikti “socialinių tinklų/protingų agentų” rekomendacijos – viskas atsiremia į elementarų pasitikėjimo-karmos reitingą tarp “mano draugų”.</p>
<p>Apie kovą už privatumą kalbėti manau jau nebeverta – aš turbūt visiškai nebesigėdyčiau nurodyti visus savo socialinius kontaktus ir darykit jūs kokias norit išvadas apie mane. Visi daro klaidų, visi turi istorijas. Visų istorijos surandamos per Google. Galbūt kai kandidatuosiu į prezidentus man tai ir atsirūgs, bet tai bus ne anksčiau kaip po kokių 20 metų, tai tada ir žiūrėsim ką su visu tuo daryti (<em>agile</em>!)</p>
<h2>Verslo modeliai</h2>
<ul>
<li>Įmonė, kuri kuria “protingus agentus” ir parduoda jas <i>corporate</i> klientams, pvz. Omnitel galėtų nusipirkti tokį agentą ir prisijungti prie one.lt duombazės, arba AirBaltic galėtų prisijungti prie Delfi komentarų. Kam jiems to reikia? Ogi tam, kad palaikyti ryšį – vienintelis mano ideologinis reikalavimas – infomacija, kuri kaupiama, turi būti naudojama paslaugų gerinimui ir derinimui, o ne tiesioginiams pardavinimas (t.y. speminis skambininimas telefonu man tiesiogiai) Tokiu būdu aš kaip klientas, galėčiau nesunkiai išreikšti savo nuomonę apie jų produktus savo pageidaujamame portale, o jie tą informaciją gautų.</li>
<li>Vertikalios svetainės bet kuria tema, pvz. svetainė A apie siuvinėjimą galėtų automatiškai perduoti mano žinutę, kurią parašiau svetainėje B, mano draugams iš svetainės C. Nepaisant to, kad žinutė skaitoma svetainėje B, taigi svetainės A ir C lyg ir prarastų “klientų”, tačiau realiai jos įgautų lygiai tas pačias galimybes pritraukti klientus iš kitur, o be to vistiek išliktų lyderiais savo specifinėje sferoje.</li>
<li><a href="http://friendfeed.com/">FriendFeed</a> tipo agregatoriai, tik geresni ir vėlgi – su savo vertikaliomis specializacijoms (kartais kas tinka viskam, netinka niekam)</li>
<li>Saugumo/pasitikėjimo autoritetai (Verisign, anyone?)</li>
<li>Teisininkai, kurie galėtų paduoti visas aukščiau paminėtas svetaines į teismą, už patentų ar įsivaizduojamų teisių pažeidimus</li>
</ul>
<p>Bet kokiu atveju, tokią “ekosistemą” aš įsivaizduočiau tik paremtą atvirais standartais ir sąžiningumu. Pirmas reikalavimas yra grynai tam, kad “pasitikėjimo” sprendimai nebūtų koncentruoti į vieną įmonę (labas rytas, Google!), o pats “pasitikėjimo sprendimų” tinklas būtų išsibarstęs taip kaip TPC/IP ir pageidautina paremtas P2P – atkirtus vieną šaką, kitos gali išgyventi, o galutinė kontrolė ir lankstumas grįžta vartotojui, o ne paslaugų tiekėjui.</p>
<p>Sąžiningumo kriterijų įgyvendinti yra kiek sunkiau… Tačiau vistiek principas “nekąsk į tave maitinančią ranką” turėtų paimti viršų. Jeigu pavyktų tai pasiekti – tai būtų galutinė e-mail spamo mirtis. Jau dabar visi žmonės, kuriuos aš pažįstu, mane suranda kitais kanalais, o aš jų adresų net nežinau. Ir nenoriu žinoti.</p>
<h2 id="20081117-santrauka">Santrauka</h2>
<ul>
<li>Apverčiam kontrolę: ne aš registruojuosi, bet mane suranda</li>
<li>Apverčiam kontrolę: ne kažkas kaupia mano duomenis, o aš padarau juos viešai prieinamais ir leidžiu arba neleidžiu jais naudotis, o manęs klausoma</li>
<li>Apverčiam kontrolę: ne pardavimų vadybininkai man pudrina smegenis, o aš jiems perduodu, ko aš noriu</li>
<li>Apverčiam kontrolę: ne aš atsitiktinai atrandu, kad <a href="http://www.moby.com/journal">Moby rašo blog’ą</a>, o <a href="http://last.fm">last.fm</a> perduoda į mano naujienų skaityklę, kad vienas iš mano mėgstamų atlikėjų turi RSS; tuo tarpu <a href="http://www.manobalsas.lt/">svetainė, kuri padeda įsivertinti savo politines pažiūras</a>, nuspėja, kad Moby ir mano idėjos kartais sutampa; todėl <em>mano draugo</em> Wordpress administracijos įžanginiame puslapyje atsiranda naujų rekomendacijų. Ir jokio taginimo ar kalbos analizės!</li>
</ul>
<p>PS žmogau, kuris viename socialiniame tinkle teigia, kad jo vardas ir pavardė yra lygiai tokie patys kaip mano – pakviesk mane alaus. Apverčiau kontrolę – buvo nulis, liko nulis.</p>