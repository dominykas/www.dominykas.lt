# Kaip HTML5 įsisenėjusį skaudulį nuėmė

<p>Jau kokius du su puse metų vis ruošiausi parašyti įrašą apie <code>h1</code>-<code>h6</code> žymų naudojimą ir jų nepakankamumą. Gerai, kad tingėjau – dabar nebereikia net sukti dėl to galvos.<br>
<span id="more-117"></span></p>
<h2>Antraščių problema HTML 4.01</h2>
<p>HTML4 specifikacija <a href="http://www.w3.org/TR/html401/struct/global.html#h-7.5.5">apie <code>h?</code> antraštes</a> kalba gana abstrakčiai. Jų esmė – pristatyti toliau einačios dokumento dalies turinį. Paminėta, kad <code>h1</code> yra svarbiau negu <code>h6</code>, taipogi, kad iš to galima sukurti dokumento “apžvalgą” ar “turinio rodyklę”. Dar rašoma, kad “kai kurie žmonės” laiko, kad “peršokti” lygius (t.y. <code>h1 h3 h5</code>) yra neteisinga, tačiau neteikia jokių rekomendacijų šiuo klausimu.</p>
<p>Be jau paminėto komentaro pačioje specifikacijoje, toks aprašymas palieka begalybę kitų klausimų, kad ir pvz. kiek puslapyje gali būti <code>h1</code> žymų? Kaip atskirti skirtingą jų kontekstą? Viena iš SEO strategijų (kol robotai nebuvo to išmokę pažinti), buvo sukišti vos ne visą puslapio turinį į <code>h1</code>, taip raktažodžiams suteikiant papildomą vertę. Kita problema buvo, kad ir tai, kad pvz. dokumento skiltis skirta navigacijai (blog’o <i>sidebar</i>) taipogi buvo suskirstyta į dalis – tokiu atveju norėtųsi atskirti, kad <i>sidebar</i> poskyriai (pažymėti <code>h3</code>) nėra vienos iš įrašo pastraipų (pažymėtų <code>h2</code>) dalis.</p>
<h3>Interpretacija: <code>h1</code> yra svarbiausias ir vienintelis</h3>
<p></p><aside>Vis pamirštu, kad HTML4 reikia naudoti būtuoju laiku</aside><p></p>
<p>Negana to, mano asmeniniu požiūriu, puslapyje <del>derėtų</del> derėjo naudoti tik vieną <code>h1</code> tipo elementą (<a href="http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/H42">WCAG rekomendacija</a>) – tą, kuris daugiau mažiau sutaptų su puslapio pavadinimu, nurodytu <code>title</code>. Taigi titulinis eilinio blog’o puslapis atrodytų maždaug taip:</p>
<ul>
<li><code>h1</code>: blog’o pavadinimas
<ul>
<li><code>h2</code>: navigacija
<ul>
<li><code>h3</code>: <i>sidebar</i> skiltis</li>
<li><code>h3</code>: <i>sidebar</i> skiltis</li>
</ul>
</li>
<li><code>h2</code>: įrašas
<ul>
<li><code>h3</code>: įrašo pastraipa</li>
<li><code>h3</code>: įrašo pastraipa</li>
</ul>
</li>
<li><code>h2</code>: įrašas
<ul>
<li><code>h3</code>: įrašo pastraipa</li>
<li><code>h3</code>: įrašo pastraipa</li>
</ul>
</li>
</ul>
</li>
</ul>
<h3>Ką daryti kai antraštės “šokinėja”?</h3>
<p>Aukštesnis suskirstymas tinka tik pirmąjam puslapiui. Jeigu kalbame apie individualaus įrašo puslapio sužymėjimą, tai situacija lyg ir keistųsi – <em>blog’o pavadinimas jau nebėra <code>h1</code> svarbos</em>, nes svarbiausia antraštė tokiu atveju yra <em>įrašo</em> pavadinimas! Įrašo pastraipos taipogi turėtų kylti lygiu aukščiau – iki <code>h2</code>. Kas tokiu atveju atsitinka su <i>sidebar</i> skiltimis? Nežinau.</p>
<p>Taip iki galo ir neišsprendžiau tos problemos, nors ir labai norėjosi. Viena iš minčių buvo išvis atsisakyti pašalinės navigacijos. Lankytojų tai per daug nenuskriaustų – pagal mano duomenis didžioji dalis lankytojų iš Google patekę tiesiai į konkretų įrašą arba tiesiog išeidavo (aš gal rašyt nemoku?), arba po to keliaudavo į titulinį puslapį (o gal vistik moku?), o ne tiesiogiai į kitus įrašus.</p>
<h2>HTML5 dokumento skilčių apibrėžimai į pagalbą!</h2>
<p>Nepaisant to, kad iš aukščiau apibrėžtos problemos grafomanas išspaustų tris įrašus, o internetas pilnas <a href="http://www.h1debate.com/">nesibaigiančių diskusijų</a>, man tai nebėra aktualu! HTML5 apibrėžia dokumento skiltis – joms sužymėti galima naudoti <code>section</code>, <code>nav</code> ir <code>article</code> elementus (<code>aside</code> taipogi laikoma atskiru, susijusiu poskyriu). Visi šie elementai gali turėti savo antraštes ir paraštes (<code>header</code> ir <code>footer</code>). Tokiu atveju, kiekviena antraštė įgauna savo individualų kontekstą (<code>body</code> viduje esanti antraštė aprašo puslapį, gi tuo tarpu <code>article</code> viduje – tik tą įrašą) ir savo individualią hierarchiją.</p>
<p>Nepaisant to, kad specifikacijoje gana daug teksto yra skiriama <a href="http://dev.w3.org/html5/spec/Overview.html#outlines">rodyklės (<i>outline</i>) formavimo algoritmui</a>, paprastam blog’ui, o turbūt ir daugeliui kitų svetainių, tai yra neaktualu, nes antraščių hierarchija visada gaunasi elementari – praktiškai bet kurios dokumento dalies antraštės apsirašo tiesiog <code>&lt;header&gt;&lt;h1&gt; pavadinimas &lt;/h1&gt;&lt;/header&gt;</code>, t.y. <code>h1</code> šiuo atveju nebereiškia tiesiog “svarbiausia antraštė”, o interpretuotina kaip “svarbiausia antraštė šioje dokumento dalyje”. Naudojant tokią logiką, individualus įrašo puslapis jau nebeturi kitokio globalaus antraščių lygmenų išsidėstymo, nei sąrašuose – dabar aš drąsiai galiu savo įrašų poskilčius žymėti tiesiog <code>h2</code>.</p>
<h2>Desertas</h2>
<ul>
<li>HTML5 neberiboja antraščių gilumo (anksčiau buvo maks. 6) – nors ir nelabai žinau kam to gali prireikti</li>
<li><code>hgroup</code> elementas leidžia grupuoti antraštes su paantraštėm, kaip pvz. aš esu padaręs su blog’o pavadinimu – <i>View source</i> naudoti mokat?</li>
<li><a href="http://www.w3.org/TR/wai-aria/#banner">ARIA <code>banner</code> rolė</a> leidžia atskirti “svetainės” ir “dokumento” pavadinimus – apie ARIA apskritai dar reiktų daugiau man pasiskaityti…</li>
</ul>
<h2>Papildomas skaitymas</h2>
<ul>
<li><a href="http://blog.whatwg.org/this-week-in-html-5-episode-32#hgroup">Introducing the <code>&lt;hgroup&gt;</code> element</a></li>
<li><a href="http://www.brucelawson.co.uk/2009/headings-in-html-5-and-accessibility/">Headings in HTML 5 and accessibility</a></li>
<li><a href="http://www.youtube.com/watch?v=GIn5qJKU8VM">More than one H1 on a page: good or bad?</a></li>
</ul>
<p>PS neturiu laiko ieškoti, bet gal kas turit pasiūlymą, kaip WordPress priversti nedėti <code>aside</code> į <code>p</code>?</p>