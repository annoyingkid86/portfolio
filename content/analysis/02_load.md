---
Title: Prestanda-analys och användbarhet
Description: Prestanda-analys och användbarhet
---

Prestanda-analys och användbarhet
=================================

Uppgiften handlar om att analysera hemsidors prestanda genom att mäta inladdningstiden och även minnesmängden som hämtas!

Urval
-----------------------

Den här gången har jag valt CDON, Webhallen samt Komplett som mål att undersöka! 
Min motivering kring dessa val handlar om att samtliga sidor sysslar med e-handel, och just CDON var i princip obrukbar under stora delar av Black Friday i år!
Detta tycker jag är intressant, och vill undersöka noggrannare!

Metod
-----------------------

För att analysera sidornas prestanda, använder jag mig av webbläsarens "Devtools"! Här går det att mäta laddningstiden på hemsidan, 
samt presentera mängden data som överförs på hemsidan! Dessa mätningar utför jag under flera olika scenarior, 
givna exempel är genom att simulera en sämre uppkoppling samt olika storlekar på fönstrets upplösning!
Vidare, undersöker jag om bilderna på hemsidan verkligen är responsiva! Byts källfilen verkligen ut mot ett alternativ med lägre upplösning,
eller används bara originalet och skalas ner via stylingen?
Jag använder mig av PageSpeed Insights för att få en poängbedömning på sidorna samt förslag för att optimera dem!

Slutligen, utför jag några experiment via min privata server för att undersöka hur mycket tid som förloras genom att skapa ett galleri med högupplösta bilder!
Går det att få ner tiden genom att dela upp arbetet via flera lokala servrar? 
Hur stor blir prestandaökningen om källfilen byts ut mot alternativ som har lägre upplösning?
Hjälper det optimeringen ytterligare om arbetet fördelas mellan olika servrar?

Resultat: CDON
----------------------

<div class="grid-two-column">
<a href="%assets_url%/img/cdon_1.png">
<img src="%assets_url%/img/cdon_1.png" alt="CDON:s hemsida, bild 1">
</a>
<a href="%assets_url%/img/cdon_2.png">
<img src="%assets_url%/img/cdon_2.png" alt="CDON:s hemsida, bild 2">
</a>
</div>

Direkt när man når hemsidan nås man av en massiv bakgrundsbild i headern! Det behöver ju inte vara fel, men hur optimerad är den egentligen?
I snapshoten ser man att det finns lite bilder med olika priskategorier! Inga problem i sig, och är utvecklaren klok laddas dessa in responsivt och texten appliceras med css!
Men detta görs inte alls! Istället är det separata bilder för varje kategori, och de laddas in med 1200x1200 i storlek! Hur detta kan påverka prestandan diskuterar vi i analysen!

Det är möjligt att det här ligger utanför uppgiftens ämne, men jag kände att det var intressant att ta upp!
I konsolen går det att utläsa många varningar, och det kan ju inte vara bra! Som utvecklare skulle jag nog sett till att minimera dessa så mycket som möjligt!

<div class="grid-two-column">
<a href="%assets_url%/img/cdon_3.png">
<img src="%assets_url%/img/cdon_3.png" alt="CDON:s hemsida, bild 3">
</a>
<a href="%assets_url%/img/cdon_4.png">
<img src="%assets_url%/img/cdon_4.png" alt="CDON:s hemsida, bild 4">
</a>
</div>

Ojdå! Det här hade jag inte riktigt förväntat mig! Man kan ju tycka att CDON, som är en så pass stor marknadsplats, borde ha en välutvecklad och responsiv hemsida!
Betyget för desktop-sidan är lite högre, men fortfarande relativt lågt! Det visar på att sidan skulle kunna optimeras betydligt bättre än vad den gör i nuläget!

Resultat: Webhallen
-------------------

<div class="grid-two-column">
<a href="%assets_url%/img/webhallen_1.png">
<img src="%assets_url%/img/webhallen_1.png" alt="Webhallens hemsida, bild 1">
</a>
<a href="%assets_url%/img/webhallen_2.png">
<img src="%assets_url%/img/webhallen_2.png" alt="Webhallens hemsida, bild 2">
</a>
</div>

Även här möts man av en större bild, som utannonserar rabatterade produkter! Det går att läsa av ett mönster kring hur e-handelssidor fungerar och är designade!
Sidan har många kvadratiska bilder för att visa upp produkter, samt klickbara banners för att nå ytterligare erbjudanden! Även här är detta baserat på årets tidpunkt, 
vilket vi sett de senaste veckorna med alltifrån Black Friday till Cyber Monday och nu julklappstips! Det råder inget tvivel om att mellandagsrean dyker upp efter julafton!

Om man undersöker lite närmre i nätverksöverföringarna, upptäcker man att Webhallen använder sig utav mycket javascript! Bilderna skalas om innan de hämtas! Detta är en acceptabel lösning, men det krävs fortfarande resurser för omskalningen! 
Skulle det varit bättre optimerat med färdigrenderade bilder i olika upplösningar?
I övrigt så dyker det upp varningar, och även felmeddelanden i konsolen! Detta borde man kanske korrigera som utvecklare?

<div class="grid-two-column">
<a href="%assets_url%/img/webhallen_3.png">
<img src="%assets_url%/img/webhallen_3.png" alt="Webhallens hemsida, bild 3">
</a>
<a href="%assets_url%/img/webhallen_4.png">
<img src="%assets_url%/img/webhallen_4.png" alt="Webhallens hemsida, bild 4">
</a>
</div>

Prestandan på hemsidan när man använder en mobil enhet är låg! Varför har man inte försökt optimera sidan för mobila enheter?

Även prestandan då sidan är i desktop-läge är låg, prestandan är snarlik i båda fall! 
Förslagsvis är det något annat än bildinläsningen som är flaskhalsen!

Resultat: Komplett
-------------------

<div class="grid-two-column">
<a href="%assets_url%/img/komplett_1.png">
<img src="%assets_url%/img/komplett_1.png" alt="Webhallens hemsida, bild 1">
</a>
<a href="%assets_url%/img/komplett_2.png">
<img src="%assets_url%/img/komplett_2.png" alt="Webhallens hemsida, bild 2">
</a>
</div>

Komplett har en bra och tydlig sida! Dessutom laddas det in olika bilder beroende på enhetens upplösning! Bildinläsningen görs via javascript!
Än en gång lite varningar! Samtliga sidor har haft meddelande i konsolen! Vissa av varningarna verkar ju inte heller vara någon större sak att ordna upp!

<div class="grid-two-column">
<a href="%assets_url%/img/komplett_3.png">
<img src="%assets_url%/img/komplett_3.png" alt="Webhallens hemsida, bild 3">
</a>
<a href="%assets_url%/img/komplett_4.png">
<img src="%assets_url%/img/komplett_4.png" alt="Webhallens hemsida, bild 4">
<a/>
</div>

Med tanke på att hemsidan har så pass god responsivitet, hade jag förväntat mig ett högre betyg! Den låga poängen var lite överraskande!
När man når sidan via en desktop, så ges plötsligt ett högt betyg istället! Sidan är alltså väldigt nära att nå 90 poäng!

Resultat: Prestandamätning
--------------------------

<div class="spreadsheet-container">
    <iframe src="https://docs.google.com/spreadsheets/d/e/2PACX-1vTjU5Cp8ch_ECCXPGx9YOP2DZtObaeI9cjvUD26l61rHr7-pJ1UJrAyIdMpfSKul1PdxDmIHFKdJ3tj/pubhtml?gid=0&amp;single=true&amp;widget=true&amp;headers=false"></iframe>
</div>

Jag simulerade inladdningshastigheter via olika scenarior, allt ifrån väldigt dålig uppkoppling(GPRS) till optimal uppkoppling(bredband)!
Dessutom gör jag tester med olika upplösningar på enheten, detta för att testa responsiviteten!
Här kan man se exempel på när sidorna fungerar bra, och när de inte alls fungerar!

Resultat: Egen server
---------------------

<div class="grid-two-column">
<a href="%assets_url%/img/egen_server_1.webp">
<img src="%assets_url%/img/egen_server_1.webp" alt="Egen server, bild 1">
</a>
<a href="%assets_url%/img/egen_server_2.webp">
<img src="%assets_url%/img/egen_server_2.webp" alt="Egen server, bild 2">
<a/>
</div>

Jag skapade en egen sida, som jag placerade på min privata server för att göra egna prestandatester!
Detta mest för eget intresse samt för att få en ökad förståelse kring informationen man presenteras i utvecklarläget!
Sidan i sig är väldigt enkel, en grid med några bilder som agerar responsivt vid lägre upplösningar!
Jag har använt mig av 4 scenarior! 
Det handlar främst om en dåligt optimerad sida(bilderna laddas in högupplöst) jämfört med en optimerad sida(det laddas in olika optimerade bilder baserat på upplösningen)!
Därtill, testar jag att ladda in hälften av bilderna via min sekundära server(kan nås lokalt i samma nätverk), den är länkad via NFS! Kommer det göra någon skillnad i prestandan?

<div class="grid-four-column">
<a href="%assets_url%/img/egen_server_3.webp">
    <img src="%assets_url%/img/egen_server_3.webp" alt="Egen server, bild 3">
</a>
<a href="%assets_url%/img/egen_server_4.webp">
<img src="%assets_url%/img/egen_server_4.webp" alt="Egen server, bild 4">
</a>
<a href="%assets_url%/img/egen_server_5.webp">
<img src="%assets_url%/img/egen_server_5.webp" alt="Egen server, bild 5">
</a>
<a href="%assets_url%/img/egen_server_6.webp">
<img src="%assets_url%/img/egen_server_6.webp" alt="Egen server, bild 6">
</a>
</div>

Här görs jämförelser mellan olika förfaranden, med en låg upplösning vilket simulerar en mobil enhet! Det är en stor skillnad mellan en dåligt optimerad sida, och en bra!
Skillnaden i data är stor, 51,15 MB jämfört med 361 kb!
Här är hastigheten mellan att köra på en enskild server och dela resurserna med en sekundär försumbar! 
Testerna gjordes utan begränsad hastighet, kommer det vara någon skillnad vid en lägre uppkopplingshasighet?

<div class="grid-four-column">
<a href="%assets_url%/img/egen_server_10.webp">
    <img src="%assets_url%/img/egen_server_10.webp" alt="Egen server, bild 10">
</a>
<a href="%assets_url%/img/egen_server_9.webp">
<img src="%assets_url%/img/egen_server_9.webp" alt="Egen server, bild 9">
</a>
<a href="%assets_url%/img/egen_server_11.webp">
<img src="%assets_url%/img/egen_server_11.webp" alt="Egen server, bild 11">
</a>
<a href="%assets_url%/img/egen_server_12.webp">
<img src="%assets_url%/img/egen_server_12.webp" alt="Egen server, bild 12">
</a>
</div>

På den dåligt optimerade hemsidan gav PageSpeed ett inte så smickrande resultat, och det var ju väntat! 
Intressant ändå att notera är att poängen för en mobil enhet hade en skillnad på 39 mot 50, och 77 mot 57 för en desktop i jämförelsen kring fördelade resurser eller inte!

<div class="grid-four-column">
<a href="%assets_url%/img/egen_server_13.webp">
    <img src="%assets_url%/img/egen_server_13.webp" alt="Egen server, bild 13">
</a>
<a href="%assets_url%/img/egen_server_14.webp">
<img src="%assets_url%/img/egen_server_14.webp" alt="Egen server, bild 14">
</a>
<a href="%assets_url%/img/egen_server_15.webp">
<img src="%assets_url%/img/egen_server_15.webp" alt="Egen server, bild 15">
</a>
<a href="%assets_url%/img/egen_server_16.webp">
<img src="%assets_url%/img/egen_server_16.webp" alt="Egen server, bild 16">
</a>
</div>

På den optimerade sidan blev det betydligare trevligare resultat! Ändock verkar det som att man förlorar prestanda på att hämta resurser ifrån en länkad server!

För mobila enheter blev resultatet 83 gentemot 79! På desktop-enheter är resultatet 97 mot 70!
Det finns fortfarande rum för ytterligare förbättringar!

## Bildhantering: CDON

Om vi ska analysera vidare, ser vi att CDON faktiskt använder sig av webp och avif-formaten! Men varför hämtas både en desktop och mobil-version? 
Varför är desktop-versionen betydligt högre upplösning än själva enhetens upplösning? Redan här ser vi att CDON slarvar med optimeringen! 
Det ser inte ut att vara hela världen, då själva storleken på filen bara ligger på 268 kb! Men om en sida använder väldigt många bilder, 
då blir det en rätt stor skillnad i sänd data när man kikar på helheten!

Visserligen använder sig CDON av srcset, men det är inga förrenderade bilder som används! Det är bara originalbilden som används och komprimeras i realtid!

## Bildhantering: Webhallen

Vi har tidigare sett att Webhallen använder sig av javascript för att bestämma bilder och design på sidan! Detta är betydligt bättre än att ladda in en bild i full upplösning, 
men frågan är om detta behöver göras idag! srcset kan användas för att redan i html-dokumentet bestämma en källfil!
Som bildformat används främst webp, och det är klokt!

## Bildhantering: Komplett

Komplett använder sig främst av webp och avif, för större bilder! Visserligen används också png och jpg, men det är bara för mindre bilder!
Sidan använder sig utav srcset på ett korrekt sätt, och detta märks faktiskt på prestandamätningarna!

Här upptäckte jag lazy-img samt lazy-imageset!
Detta är tydligen metoder för att prioritera bild och video-inläsning för element som syns först på hemsidan, och sedan läsa in resterande då elementen hamnar i synfältet!
Man lär sig alltid något nytt!

Här är det skillnad kring hur mycket data som överförs baserat på enheten, tack vare srcset!

Analys
-----------------------

Diskutera och analysera de resultaten du fann.

<div class="spreadsheet-container">
    <iframe src="https://docs.google.com/spreadsheets/d/e/2PACX-1vTjU5Cp8ch_ECCXPGx9YOP2DZtObaeI9cjvUD26l61rHr7-pJ1UJrAyIdMpfSKul1PdxDmIHFKdJ3tj/pubhtml?gid=0&amp;single=true&amp;widget=true&amp;headers=false"></iframe>
</div>

Om vi kikar igen på dokumentet ifrån tidigare, så kan vi se att det står två olika data-värden! 
Efter att ha kört tester på mina experiment, kan jag bekräfta mina teorier; samtliga hemsidor skickar upp data efter att inladdningen är färdig!
Detta är allmänt känt, att e-handelssidorna samlar in och säljer ens data! Det finns ett samband kring att produkter man är ute efter presenteras i andra sammanhang!

## Vilken uppkopplingshastighet har hemsidorna satt som gräns?

Genom en analys av olika simulerade begränsningar, kan vi se att det finns ett samband kring en acceptabel lägsta överföringstid! 
Det går att urskilja att en 3G-uppkoppling ger brukbara hemsidor, medan en lägre inte funkar bra! Just 3G är standarden Sverige generellt har på sitt mobilnät! 
Självklart finns det områden med dålig täckning, där hastigheten är låg! Dessa sidor är svåra att nå i den situationen!
Det går att konstatera att företagen har satt sin gräns till 8 sekunder! Rent generellt brukar en användare använda sig av en snabb uppkoppling, och då tar det inte mer än 2-4 sekunder för sidan att ladda in!

## Hur är sidorna anpassade för mobila enheter?

### CDON

Det kan konstateras att sidan använder sig av lazy-img, men minnesmängderna är höga!
Om man vill undersöka det själv så är det viktigt att inte glömma bort de scrollande ikonerna på sidan!

### Webhallen

Webhhallen har exakt samma layout, oavsett sidan används på en mobil enhet eller desktop!
Intressant nog är minnesmängden nästan snarlik oavsett upplösning! 

### Komplett

Komplett byter layout vid några tillfällen, då den anpassas utefter enhetens upplösning!
Komplett har den bäst optimerade sidan! Orsaken till detta kan vara att startsidan är minimalistisk, med en översikt per datorkomponenter eller övriga objekt!
Vill man som konsument få en översyn på ett större utbud inom komponentgruppen, ges alltså en länk för att göra just detta!

## Förslag för att optimera sidorna

### CDON

Med tanke på upplösningarna, så borde det gå att dra ner datamängden till minst 30% istället med hjälp av ett antal tekniker!
Tidigare iakttagelser har visat på att CDON använder sig av erbjudande-bilder som om de vore ikoner! Bakgrunden är exakt samma i varenda en, 
och här skulle man kunnat spara data genom att läsa in samma bild och applicera text via css istället! Bilden blir ju då cache:ad och läses inte in igen!
Eftersom CDON använder sig av väldigt många av dessa liknande bilderna under julperioden, skulle man kunnat spara mycket prestanda här!

### Webhallen

Det första man kan fundera på är om bildhanteringen kanske kan hanteras bättre! Som noterat tidigare, används javascript för att bestämma vilken källfil som ska användas! Kan ren HTML-kodning för denna processen istället förbättra prestandan?
Det används små animerade figurer och andra ikoner högst upp i sidan! Är detta nödvändigt? Går det att få snabbare inladdning på sidan om detta skulle gå att avaktivera?

### Komplett

Komplett har som konstaterat tidigare redan en bra desktop-sida! Det är för enheter med lägre upplösning som det blir lite svårare!

Rent allmänt för samtliga sidor är att man skulle kunna lösa prestandaproblemen på mobila enheter genom att minimera datan som skickas!
Detta är naturligtvis ingen tänkbar lösning, då sidorna faktiskt fokuserar på att sälja produkter! Då vill man ju presentera så mycket artiklar som möjligt!

## Förslag ifrån PageSpeed Insight

<div class="grid-four-column">
<a href="%assets_url%/img/cdon_pagespeed.webp">
<div class="imageborder">
<img src="%assets_url%/img/cdon_pagespeed.webp" alt="CDON, tips ifrån PageSpeed">
<p>CDON</p>
</div>
</a>
<a href="%assets_url%/img/webhallen_pagespeed.webp">
<div class="imageborder">
<img src="%assets_url%/img/webhallen_pagespeed.webp" alt="Webhallen, tips ifrån PageSpeed">
<p>Webhallen</p>
</div>
</a>
<a href="%assets_url%/img/komplett_pagespeed.webp">
<div class="imageborder">
<img src="%assets_url%/img/komplett_pagespeed.webp" alt"Komplett, tips ifrån PageSpeed">
<p>Komplett</p>
</div>
</a>
<a href="%assets_url%/img/egen_sida_pagespeed.webp">
<div class="imageborder">
<img src="%assets_url%/img/egen_sida_pagespeed.webp" alt="Egen sida, tips ifrån PageSpeed">
<p>Egen sida</p>
</div>
</a>
</div>

Genom att kika på analysen och diagnostiseringen Pagespeed Insights ger oss, går det att anta att de största förbättringsmöjligheterna är följande:

* Minska arbetsbelastningen på modertråden
* Skicka statiska tillgångar med en effektiv cachelagringspolicy
* Minska körningstiden för JavaScript
* Undvik ett onödigt stort DOM-träd
* Minska påverkan från tredjepartskod

Mätningarna ger olika resultat per sida, vilket alltså ger oss att företagen har skillnader i förfarande i deras kod som kan förbättra prestandan!

## Varför uppdaterar företagen inte sina hemsidor?

Dessa hemsidor har funnits i många, många år! Långt före mobiltelefoner med en stor pekskärm var standard!
Det kan finnas många anledningar till att man undviker att uppdatera och optimera sidan!

* Det kan vara så att det blir en onödig kostnad om det är så att sidan fungerar någorlunda väl, och att målgruppen sitter på desktop-datorer med en väldigt snabb uppkoppling!
* Även standarden för mobila uppkopplingar blir bättre hela tiden, både själva anslutningshastigheten och datamängden! 5G är på gång inom kort!
* Det kan helt enkelt vara så att trafiken till hemsidan är för låg och att det bara är vid större högtider det blir problem! I vanliga fall är det alltså hanterbart!

Sammanfattningsvis går det att spekulera i att företagen inte riktigt bryr sig om att optimera sina sidor, då det inte lönar sig i längden jämfört med att låta det vara som det är!
Vilket kan förändras om det blir en förändring kring trafiken till sidan!

## Rangordning

### Plats 3: CDON

Detta var inget svårt val! CDON:s hemsida är utan tvekan den med sämst optimering, både på mobil och desktop! Detta går att referera till Speedpage-resultatet!

### Plats 2: Webhallen

Det som gör att Webhallen får en högre placering än CDON är för att mobil-sidan fick ett högre betyg, och det bör premieras!

### Plats 1: Komplett

Vad som gjorde att Kompletts hemsida fick första plats är är att desktop-sidan nästan nådde 90 poäng, baserat på Speedpage-resultatet! Visserligen fick den ett sämre resultat på mobil-sidan, men det goda resultatet för desktop visar att företaget är på rätt väg!

Referenser
-----------------------

- [CDON][CDON]
- [Webhallen][Webhallen]
- [Komplett][Komplett]
- [PageSpeed Insights][PageSpeed]

Övrigt
-----------------------

Analysuppgiften gav en väldigt stor inblick i vikten kring att lägga fokus på hemsidans prestanda! Den visade även på hur de större företagen faktiskt slarvar lite med det!

Författare: Martin Jönsson

[CDON]: https://cdon.se/
[Webhallen]: https://www.webhallen.com/
[Komplett]: https://www.komplett.se/
[PageSpeed]: https://pagespeed.web.dev/