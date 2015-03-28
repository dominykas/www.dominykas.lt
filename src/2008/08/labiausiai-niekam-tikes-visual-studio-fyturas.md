---
published: 2008-08-28T22:24:01+00:00
tags: aspnet, microsoft, visual-studio, it
---

# Labiausiai niekam tikęs Visual Studio fyturas

<p>Kad ir kaip aš nemėgčiau tam tikros įmonės, už tai, kad ji griauna Tinklą, turiu pripažinti, kad kai kuriuos dalykus jie sugeba padaryti visai neblogai. Visual Studio 2008 yra beveik neblogas įrankis kai jį prisijaukini (nors man dar iki to toli). Tik va, be abejo, jis nelabai tinka tinklo kūrimui… Ir tai kas parašyta toliau – tik viena iš smulkmenų.<br>
<span id="more-65"></span><br>
ASP.NET, naudojant teisingai, taipogi nėra <em>visiškas</em> blogis. Neskaitant kreivos defaultinės formų (one form per page?!) implementacijos, daugybės nestandartinių pribumbasų ir apskritai pačio fakto, kad Microsoft neskatina tinklo kūrimo pagal standartus. Pačio ASP kodo redagavimas su Visual Studio net jeigu ir nėra didžiausias malonumas, galėtų būti kur kas baisesnis. Tačiau vienas ypatumas redagavimo procese yra absoliučiai juokingas…</p>
<p><strong>Kam reikalinga, kad darant copy/paste visi tag’ai, kurie turi atributą <code>runat="server"</code>, automatiškai įgautų ID atributą</strong>, kuris sugeneruojamas pagal TagoPavadinimas + skaičius?</p>
<p>ID atributas gryname HTML kode yra reikalingas tik išskirtiniais atvejais, JavaScript’ui jis reikalingas tik tada kai ketini manipuliuoti elementu. Kalbant apie tai, daug naudingiau (tiek CSS, tiek JS) yra naudoti klases, nes laikui bėgant per daug dažnai nutinka taip, kad puslapyje atsiranda keli elementai su vienodu ID… Ką ASP.NET sprendžia automatiškai išplėsdami tuos atributus prefiksais, kas tik dar labiau išpučia kodą.</p>
<p><i>Code behind</i> ID atributai vėlgi reikalingi tik tada kai norime manipuliuoti tam tikrais elementais, tačiau kas nors man atsakykite – koks programuotojas dirba su kintamaisais, kurie vadinasi “Div1″ ar “Li5″? Į didžiąją dalį tokių elementų dažniausiai niekada netenka kreiptis, o kai norime kreiptis – visada tenka juos pervadinti, nes nepervadinę gauname elementariai blogą programavimo praktiką… Ar čia gal Microsoft bando įteigti, kad copy/paste kodas yra absoliutus blogis? Man asmeniškai tokiu būdu įkelti <code>&lt;manoNS:manoWidgetas runat="server"/&gt;</code> daug lengviau… Ir šiukšlių savo kode aš tikrai nepageidauju.</p>
<p>Ko aš siekiau šitu įrašu… Pamiršau… A! Gal kas žinote kur tai atjungti?..</p>