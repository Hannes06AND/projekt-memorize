# Dokumentation projekt
====================
## 2025/04/07
Förra veckan gjorde jag en ny textfil till spelet 'maze' alltså en ny karta. Efter allt som jag tidigare har gjort, har jag ett par uppgifter kvar i python-filen, men dessa har jag gjort tidigare. Till exempel att lägga till score eller visa ett meddelande. Jag kanske vill lägga till dörrar eller 'portaler' så att spelaren kan teleportera sig tvärs över kartan. Bortsett från detta känner jag mig färdig med 'maze.py'. Efter dagens tillfälle har jag fått teleportering att fungera i spelet. Jag valde ut en bild på en öppen dörr som ska representera en portal i spelet från Rikards repository. Sedan laddade jag in bilden i python-filen som vanligt, skapade en lista för dörrar och kompletterade min if-sats med kod som ska leta efter bokstaven 'd' och sedan ladda in en dörr. Sedan lade jag in ett 'd' i varje hörn av textfilen. Dörrarna ska fungera som portaler, om man går igenom den ena dörren, kommer man ut ur den andra och tvärtom. Ett problem som uppstod var att spelaren flimrade fram och tillbaka mellan dörrarna eftersom spelaren hamnade i en loop av teleportering. Detta berodde på att spelaren hela tiden kolliderade med en dörr. Därför behövde jag implementera någon form av 'cooldown' då teleportering inte fungerar för att man ska kunna gå ur dörren. Däremot när cooldown = 0 fungerar if-satsen med kollision mellan dörr och spelare. Med detta klart, känner jag mig nog nöjd med detta spel.
## 2025/03/25
Jag har fortsatt med uppgiften 'maze.py' men jag valde att hoppa över att lägga till 'score' tills vidare eftersom jag har gjort det innan. Jag har istället lagt in monster som rör sig i labyrinten. Jag gjorde på liknande sätt som med kristallerna, jag laddade in bilden för 'ogre' och skapade en lista som kallas 'monsters'. Filen letar sedan upp bokstaven 'm' som jag lägger till i textfilen som representerar monster som ska dyka upp. Jag importerar och använder random för att få alla monster att byta riktning slumpmässigt och använder en 'for-slinga' där jag anger alternativen för rörelserna. Antingen rör de sig bakåt, framåt, uppåt eller nedåt. Detta anger jag i x och y led med antingen 1 eller -1. Ett problem som uppstod var att monstret som jag lade in, rörde sig orimligt fort vilket gjorde det nästan omöjligt att plocka upp alla kristaller. Antagligen rörde den sig i samma hastighet som skärmen uppdateras. Jag fick sedan skapa en egenskap för hastighet som multipliceras med riktningen för monstret i if-satsen för kollisioner med väggar. Jag lade till tre monster totalt som är utspridda i labyrinten. Eventuellt ska jag göra en större karta i 'maze.txt' med fler monster och kristaller vilket kanske kommer göra spelet lite roligare. Kanske vill jag även experimentera med hastigheten för alla monster så att även hastigheten varieras slumpmässigt. Jag lade dessutom märke till att chansen för att ett monster går igenom ett hål i väggen är ganska låg vilket jag nog kommer ändra.
## 2025/03/24
Nu har jag felsökt problemet med "items" som spelaren ska plocka upp. Eftersom "while"-slingan specificerar att där "o" finns i textfilen, ska det läggas in en kristall. Jag hade missat att lägga till "o" på de ställen där jag ville ha kristallerna. Jag trodde att koden skulle lägga till bokstäverna i filen och sedan rita upp bilderna.
## 2025/03/18
Vid detta tillfälle har jag fortsatt med "maze.py" och uppgifterna. Jag har lagt till bild-filerna för spelaren och objekten som spelaren ska plocka upp. Spelaren kan nu röra sig i alla riktningar, detta gjorde jag på ungefär samma sätt som i tidigare spel. Jag kommenterade ut "else-satsen" som fanns i den första if-satsen då den verkade motverka effekten av tangenterna och skjuta spelaren tillbaka i rutnätet. Spelaren stoppas även när den kommer i kontakt med väggarna. Sedan skapade jag en lista för att skapa "items" som spelaren skulle plocka upp och laddade in bilden till objekten. Jag försökte att rita upp föremålen på skärmen efter att väggarna ritas ut men hittills har det inte fungerat.
## 2025/03/11
Idag har jag lagt till en tegelsten som faller tillsammans med plommonen. Jag använde koden för "plums" som referens och ändrade sannolikheten för att de ska ritas på skärmen. När man träffas av tegelstenen så avslutas spelet. Möjligtvis borde jag lägga till en sluttext istället. Jag ville även öka hastigheten på ormen till vänster och höger när man dubbelklickar på tangenterna. Jag ville nesta en if-sats under den if-sats som påverkade rörelsen då man trycker på tangenten. Tanken var att efter att man har tryckt ner tangenten och sedan trycker ner den igen, ska hastigheten öka. Problemet är att if-satsen gäller då man håller in tangenten, vilket gör att hastigheten ökar till den högsta direkt.
## 2025/03/03
Idag har jag fortsatt med orm-spelet. Jag har idag lagt till en text för poäng som visas på skärmen. Jag ritade upp rutorna liknande som jag gjorde i den föregående uppgiften, med funktioner från pygame. Jag lade till 1 till variabeln "points" i if-satsen där ormen kolliderar med frukterna. Och sedan uppdateras textrutan med dom nya poängen. Jag översatte även från integer till string då den visas som text. Jag fick sedan pilla med att flytta runt kod-raden som rensar skärmen för att texten ska kunna synas.
## 2025/02/25
Idag har jag lagt till en "Game Over!"-text till "pong"-spelet när man hamnar utanför rutan. Spelet avslutas senare tills man kryssar ner det. Jag har även börjat med uppgiften "droppings" från Rikards repository. Jag har kodat rörelserna för ormen i x-led och skapat en variabel för poäng.
## 2025/02/18
Idag har jag mer eller mindre färdigställt min version av ett "pong"-spel med en studsande kvadrat som går att styra. Jag har tagit bort de if-satser som gör studsen mot sidorna möjliga. Jag har istället ersatt dessa med en if-sats som omvandlar hastigheten i y-led till det motsatta om kvadraten kommer längst ned i fönstret eller högst upp. Sedan använde jag den existerande funktionen för kollisioner med rektangeln från pygame (colliderect) för att få kvadraten att studsa när den kommer i kontakt med någon av "padsen", vid kollisionen kommer hastigheten i x-led omvandlas till den motsatta. Därefter ville jag försvåra spelet lite ytterligare och ökade förändringsfaktorn för varje studs till -1.05 som gör att kvadraten rör sig snabbare och snabbare för varje kollision i x-led. Jag fick även öka förändringsfaktorn för hastigheten i y-led fast positivt (1.05). Däremot gick detta att motverka om man byter riktning på kvadraten med pil-tangenterna, eftersom hastigheten fick ett statiskt värde varje gång en tangent trycks ned. Detta löste jag genom att importera "math" och genom att använda funktionen "fabs" för att skriva att hastigheten ska bestämmas genom absolutbeloppet av hastighetens variabel i både x- och y-led. Därmed kommer hastigheten bibehållas även om man byter riktning på kvadraten efter ett antal kollisioner. Med detta klart, ska jag antingen jobba med något annat i pygame eller påbörja ett annat projekt.
## 2025/02/17
Idag har jag animerat två "pads" på varje sida i terminalen som rör sig med konstant hastighet upp och ned längs kanten. Det som återstår är att ändra studs-animeringen och få rektangeln att studsa tillbaka när den träffar någon av "padsen". För att animera mina "pads" skapade jag nya variabler för hastigheten i y-led, eftersom de inte ska röra sig i sidled. Jag har sedan tidigare ritat "padsen" på liknande sätt som jag ritade rektangeln/kvadraten genom pygame (pygame.draw.rect). Jag satte sedan statiska hastigheter på dessa genom ett värde på deras variabler. Sedan studsar "padsen" genom en if-sats som multiplicerar hastigheten med -1 för att få den motsatta hastigheten när de kommer till slutet av terminalen.
## 2025/02/04
Idag har jag fortsatt med animeringen av rektangeln. Jag har nu lagt in tangent-input. Nu kan jag alltså styra rektangeln med pilarna och ändra riktning. Jag funderar på att göra ett slags ping-pong spel där man istället
har statiska "pads" som rör sig upp och ned på vardera sida av fönstret som man ska försöka träffa med rektangeln. Problemet är däremot att jag inte kan återanvända variabler som berör hastigheten eftersom de redan används av rektangeln.
## 2025/02/03
Idag har jag bytt från att använda Windows till Linux eftersom Git varken går att använda eller ominstallera i Windows. Sedan förra veckan har jag fått VSCodium att fungera i Linux, så när detta numera fungerar har jag nu fått installera pygame igen fast på Linux. Jag har nu fått rektangeln i python att studsa i fönstret. Jag funderar över om jag ska fortsätta arbeta med den här uppgiften och göra några ändringar i koden eller om jag ska byta spel från pygame, alternativt börjar jag med ett annat mindre projekt.
## Summering moment memory-projekt:
- Klart: Slumpmässigt skapa en sekvens med siffror i en string (istället för lista)
- Klart: Nedräkning (samt rensning av konsolen)
- Inte klart: Spara poäng i en variabel (detta var onödigt eftersom spelet helt enkelt fortsätter om du svarar rätt)
## 2025/01/28
Idag känner jag mig mer eller mindre färdig med det första projektet, dvs memory-spelet. Jag testade dock att göra en mer optimerad version med funktioner och while-slingor, detta gjorde att det krävdes mindre kod och att spelet faktiskt fungerade felfritt. Jag tog hjälp av ChatGPT för att justera koden efter min ursprungliga kod som referens. Jag förstod koden men det fanns däremot vissa komponenter som jag inte var bekant med. Jag vill ändå påstå att jag begriper koden men jag hade troligen inte kunnat slutföra spelet på egen hand. Idag har jag installerat pygame och skapat en ny python-fil för en animerings-uppgift med en rektangel som ska studsa i fönstret.
## 2025/01/14
Idag har jag gjort det mesta i spelet. Jag har skapat en string för varje siffersekvens där de ökar i antal. Värden i form av ental slumpas fram som sedan sparas i varje text. Jag valde att spara siffersekvensen i "strings" istället för listor för att slippa konverta mellan datatyper när man ska gissa siffrorna. För att få det att fungera fick jag importera "random". Jag importerar även "sleep" från "time" för att kunna göra en nedräkning i programmet. Till sist importerade jag "os" för att kunna rensa konsolen i Windows. Jag skapade sedan en variablel för antalet sekunder det tar innan skärmen rensas. Därefter använde jag while-slingor för dra bort 1 från variabeln tills seconds=0. Sedan efter 5 sekunder rensas skärmen och man behöver gissa siffersekvensen. Om ditt svar är samma som textslingan får du rätt. Till detta använde jag if-satser. Till nästkommande fråga insåg jag att jag behövde skriva ett nytt värde för "seconds" eftersom variabeln blev nollställd i den föregående nedräkningen. Problemet som kvarstår är däremot att jag inte får rätt utskrift om svaret är fel, dessa lägger jag i "else" men de verkar inte appliceras. Det blir även ganska många nestade if-satser vilket gör koden svår att arbeta med. En annan förbättringsåtgärd, hade varit att göra koden lite mer övergripande dvs att spelet i teorin bör kunna fortsätta i all oändlighet. Jag skulle alltså kunna göra koden lite mer effektiv så att jag inte behöver upprepa kod till exempel.
## Mål för projekt
Målet med detta projekt är att skapa ett memory-spel. I konsolen ska det slumpas fram 
en siffersekvens som sedan blir längre och längre för varje gång du svarar rätt. Det måste även finnas 
någon form av tidsbegränsning innan siffersekvensen försvinner och då man måste gissa. Det finns alltså vissa delmål med detta projekt för att slutresultatet ska bli som ett slags spel.
## Delmål för projekt
- Slumpmässigt skapa en sekvens med siffor i en lista
- Spara poäng i en variabel?
- Nedräkning