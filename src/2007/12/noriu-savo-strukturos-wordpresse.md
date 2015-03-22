# Noriu savo struktūros WordPress’e

<p><a href="http://code.dominykas.com/php/wordpress/canonizer/">Nustok burną aušint, Dominykai, ir duok <i>source’ą</i></a>.</p>
<p>Sugalvojus <a href="https://www.dominykas.lt/2007/12/noriu-padorios-adresu-strukturos.html">pricipą</a>, išplėtojus <a href="https://www.dominykas.lt/2007/12/noriu-pastovios-adresu-ir-turinio-strukturos.html">idėją</a> ir apibrėžus <a href="https://www.dominykas.lt/2007/12/noriu-blogo-adresu-strukturos.html">taisykles</a> galima žiūrėti dar konkrečiau. Turint omeny mano visus princesiškus įgeidžius, WordPress šiaip jau nėra bloga sistema, nors kodo kiekis skirtas adresų generavimui ir jų apdorojimui yra stulbinantis (ir netgi isteriškai juokingas). Tačiau čia jau jų pačių problema, kylanti iš to, kad siekiama patenkinti kuo didesnį vartotojų ratą. Tačiau liaudies išmintis teigia ką kitą – <em>kartais kas tinka viskam – netinka niekam</em>. Na bent jau man tikrai <strong>netinka masinio vartojimo produktas</strong>, kuris netenkina mano poreikių. Tačiau WP yra atviro kodo ir šiaip jau tiesiog <strong>prašosi laužomas</strong> ir “pritaikomas” – kaina viso to be abejo yra tai, kad ateityje mano “perrašymai” gali nebeveikti ir teks prie jų padirbėti sulig kiekvienu WP relyzu, tačiau vieną kartą pasidarius taip kaip aš noriu – turėčiau būti patenkintas gana ilgai, net su sena WP versija – don’t fix it, if it ain’t broken.<br>
<span id="more-10"></span></p>
<h2>Užduotis</h2>
<p>Mano tikslas yra priversti WP atpažinti adresus, pagal mano struktūrą, priversti jį generuoti adresus pagal mano struktūrą ir priversti jį padaryti 301 redirektą, kai adresas netenkina struktūros. Kadangi nežinau iki galo visų galimybių, kurias naudosiu, be to ir laikas ribotas – kol kas užteks sutvarkyti šitaip:</p>
<ul>
<li><b>Turinys (content):</b>
<ul>
<li><b>/2007/</b> – mėnesių sąrašas [Archyvas, 2007]
<ul>
<li><b>01-12/</b> – post’ų sąrašas [Archyvas, 2007, mėnuo]
<ul>
<li>postas-numeris-vienas.html</li>
<li>postas-numeris-vienas.(rss|atom|rdf|rss2).xml</li>
<li>postas-numeris-vienas.trackback</li>
</ul>
</li>
</ul>
</li>
<li><b>/pavadinimas.html</b> – paprastas puslapis (analogiškai postams – rss ir tb)</li>
<li><b>/attachments/2007/11/pavadinimas.html</b> – prisegto failo aprašymas (analogiškai postams – rss ir tb)</li>
</ul>
</li>
<li><b>Archyvai:</b>
<ul>
<li><b>kategorijos/</b> – kategorijų sąrašas
<ul>
<li>pavadinimas[/subpavadinimas].html – paskutiniai X įrašų kategorijoje</li>
<li>pavadinimas[/subpavadinimas].(rss|atom|rdf|rss2).xml – kategorijos feed’as</li>
</ul>
</li>
<li><b>tagai/</b> – tagų debesėlis
<ul>
<li>pavadinimas.html</li>
<li>pavadinimas.(rss|atom|rdf|rss2).xml</li>
</ul>
</li>
</ul>
</li>
<li><b>Visa kita</b> – filtruojasi per standartinius WP GET parametrus, kreipiantis į /search. Visą /search tuo pačiu įdedame į noindex, nes ten bus dinamiškas, pasikartojantis ir visaip kitaip paieškos robotams nenaudingas turinys – pažangūs vartotojai patys susigaudys kaip išgauti tai ko nori.</li>
</ul>
<h2>Kur ieškoti?</h2>
<p>WordPress filosofija <a href="http://codex.wordpress.org/Plugin_API/Filter_Reference">leidžia filtruoti</a> beveik visą įmanomą išvedimą – tai bene labiausiai palengvina mano darbą. Problema aišku ta, kad visi tie filtrai gana prastai dokumentuoti ir nėra patogios <i>naming convention</i>, todėl teks verstis su elementaria paieška kode.</p>
<p>Perrašymas susideda iš trijų dalių – turinio atpažinimo iš URL, nuorodų generavimo ir nuorodų kanonizavimo. Atpažinimą susitvarkyti gana paprasta – reikia detaliai išsianalizuoti <code>wp-includes/rewrite.php</code> failą ir ką jis veikia, po to sukurti savo <i>regular expressions</i>. Nuorodų generavime beveik visur (išskyrus puslapiavimą paieškoje ir pan.) yra naudojami <code>apply_filter</code> – per visą WP <i>source’ą</i> paleidus paieškas <code>_link(</code> ir <code>_url(</code>, po to truputį padirbėjus galima susirinkti visus reikalingus filtrus (nes dokumentacija pasitikėti kažko sunku).</p>
<p>Kanonizavimas yra iš esmės paprastas – jeigu rodomas objektas (puslapis, archyvas, pan.) yra kviečiamas ne su kanonine nuorodą – darom 301 redirektą. Panašiai elgiasi standartinė WP kanonizacija (<code>wp-includes/canonical.php</code>), tačiau ji neveikia su <i>feed’ais</i> ir (pagal mano reikalavimus) neperkelia lankytojų į “/search” neindeksuojamą sritį – teks jį išjungti ir daryti savo.</p>
<h2>Rezultatas</h2>
<p>12 valandų galvos trankymo į sieną, eureka šūksnių, keiksmų, verkimo, testas su <a href="http://www.arnebrachhold.de/projects/wordpress-plugins/google-xml-sitemaps-generator/">Google Sitemaps pluginu</a>, pergalės šokis ir <a href="http://code.dominykas.com/php/wordpress/canonizer/">canonizer plugin’as paruoštas</a>. Iš esmės niekam nerekomenduoju jo naudoti – tačiau peržvelgti kodą, pažiūrėti kaip veikia mano blog’as ir galbūt dalį to pritaikyti sau – visada prašom. Į egzistuojantį blog’ą jo kelti nederėtų dėl jau minėtos adresų pasikeitimo priežasties – nesivarginau daryti <i>backwards compatibility</i> su visomis įmanomomis WP instaliacijomis, todėl jūsų senos nuorodos gali paprasčiausiai nustoti veikti. Be to plugin’as tikisi keletos nustatymų – visų pirma permalink struktūra turėtų būti <code>/%year%/%monthnum%/%postname%.html</code>; taipogi pirmasis puslapis turėtų būti įrašų sąrašas (netikrinau ar veikia kitu atveju). Na ir šiaip jis nėra pakankamai ištestuotas – laikas parodys.</p>
<p>Nepaisant to, kas yra skonio reikalas, svarbiausios veikimo detalės:</p>
<ul>
<li><code>add_action('init',array('Dominykas_Canonizer','init'));</code>
<p>Užsikraunam, pasileidžiam, važiuojam, žiūrim į klasės <code>init()</code> metodą</p>
</li>
<li><code>init()</code> viduje nematome nieko ypatingo – inicializuojami keli kintamieji ir nustatomi filtrai:
<ul>
<li><code>f_rr_*()</code> – filtruojam perrašymo taisykles. Grąžinam asiociatyvų masyvą, kurį naudoja <code>$wp_rewrite</code>. <code>f_rr()</code> tuo pačiu dar šiek tiek pravalo tai kas man neįdomu.</li>
<li><code>f_url_*()</code> – filtruojam sugeneruotus adresus. Kiekviena funkcija labai skirtinga ir su skirtingais parametrais – bet galbūt vieną dieną WP viduje įsivyraus tvarka ir gyventi bus paprasčiau… <code>f_url()</code> ištaiso puslapiavimą (kabinamės ant <code>clean_url</code>, nes kito būdo nėra) – šitą funkciją reikės perrašyti, kai apsispręsiu dėl gražios puslapių struktūros (tinkamos SEO).</li>
<li><code>redirect_canonical</code> – perkeliam lankytoją į Teisingą Adresą</li>
</ul>
</li>
<li>Dar viduje randame keletą pagalbiniu funkcijų:
<ul>
<li><code>query_allowed_only()</code> – sutikrinam ar turime tiksliai tokius ir tik tokius parametrus kaip reikalinga kanoniniam adresui</li>
<li><code>rebuild_url()</code> – quick-n-dirty hackas atstatyti adresą, kurį sugriovėme su <code>parse_url()</code></li>
</ul>
</li></ul>
<p>Dalis funkcijų dokumentuota, dalis gimė copy-paste būdu, o Windows kažkodėl ištrina visus komentarus iš clipboard’o (tikrai tikrai!)</p>
<h2>Kas toliau?</h2>
<p>Galbūt vieną dieną WP išaugs į padorų OO dizainą. Galbūt vieną dieną visas nuorodų generavimas bus viename faile. Tada bus galima tiesiog pakeisti $wp_rewrite ir pvz. $wp_links objektus į savo parašytus/išplėstus ir nukris dalis vargo (performance’o atžvilgiu turėtų tikrai būti efektyviau, nei du kartus atlikinėti tą patį darbą). Artimiausias dalykas though – sutvarkyti į padorią PHP5 objektinę sintaksę (static funkcijos), bei sutvarkyti, kad nuorodų atpažinimo regexpų kešas nebūtų generuojamas kas kartą (<code>$wp_rewrite-&gt;flush_rules();</code>. Vėliau jau bus galima žiūrėti šiek tiek plačiau, kad padengti daugiau WP funkcijų ir pritaikyti didesniam ratui lankytojų. Pirmas žingsnis į išleidimą viešumon, būtų permalink nustatymų pakeitimas, t.y. WP options turėtų būti galima pasirinkti ar naudoti WP permalinkus, ar naudoti šio plugino sistemą – tada jau tektų kurti ir konfigūracijos opcijas. Jeigu kas nors norite tuo užsiimti – prašau! Kodo turbūt nerašysiu, bet į klausimus kiek sugebėsiu – atsakysiu.</p>
<p>O tęsiant WP hackinimo temą, natūralus posūkis yra link skinų laužymo ir templeitų pritaikymo.</p>