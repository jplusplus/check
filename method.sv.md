Det här är Journalism++ metod för faktagranskning i datadrivna projekt. Den har kommit till genom inspiration av bland annat Jennifer LaFleurs [A Guide to Bulletproofing Your Data](https://github.com/propublica/guides/blob/master/data-bulletproofing.md) och Chris Groskopfs [Sixteen solutions for data-driven projects](https://docs.google.com/presentation/d/18KE-VO9T6V1I_aGyekdDtFhYP4K0Saph7aBuBS3N8tc/edit#slide=id.ga85f0df1a_049).

Den [engelska versionen](method.en.md) av det här dokumentet följer [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt), så att det är tydligt vilka delar av metoden som alltid behöver följas, vilka som kan frångås.

## Disputation

_Vad?_<br/>
En person i redaktionen ska hållas helt utanför researchen. Hen är vår ”opponent”. Opponenten kallar till ett slags intern disputation i slutet av projektet.

_Varför?_<br>
Med en disputation upptäcker vi fler svagheter själva.

_Hur?_<br>
Opponenten ska:
 * Följa flödet från data till analys, steg för steg-
 * Ifrågasätta definitioner
 * Kontrollera mot [dataregistret](#dataregister) att rätt data används till rätt sak
 * Fråga hur uträkningar gjorts
 * Bedöma om slutsatserna är rimliga
 * Göra _flera_ stickprov
 * Göra en formmässig korrläsning: sifferformat, enheter, skalor etc.


## <span id="dataregister">Centralt register med ursprungsdata</span>

_Vad?_<br/>
I början av varje projekt ska all urspungsdata samlas på ett ställe. Ursprungsdata ändras aldrig. 

_Varför?_<br>
Med ett centralt dataregister undviker vi att data om- och feldefinieras på vägen.

_Hur?_
 * All originaldata samlas (och skrivskyddas) i en mapp
 * Där ska också finnas en textfil med källförteckning
 * Notera gärna antalet rader (eller relationer, eller motsvarande beroende på datatyp) för varje dataset i textfilen, för att kunna dubbelkolla att ingen data trunkerats under projektets gång
 * Alla nya datakällor som tillkommer ska föras in här


## Inledande datakoll

_Vad?_<br/>
När projektet inleds och när ny data hämtas in, ska det finnas tid avsatt att kontrollera datakvaliteten.

_Varför?_<br>
Med en inledande datakoll kan vi upptäcka export- och importfel, och fel som begåtts av avsändaren.

_Hur?_
 * Pivotera på nyckelkolumner för att se att där inte finns olika stavningar av samma namn.
 * Kontrollera att alla [kommuner/länder/personer/sjukdomar/etc] finns med.
 * Kontrollera nollvärden. Ska det vara 0, eller är det tomma rutor som blivit kodade som nollor på vägen?
 * Kontrollera tomma rutor. Ska de vara tomma?
 * Är radantalet rimligt? Se upp för radantal som 5 000 eller 32 768 vid
 databasuttag.
 * Är värdena rimliga?
 * Visualisera, för att få syn på märkliga mönster, extremt avvikande punkter etc.


## Versionshantering

_Vad?_<br/>
För att kunna spåra eventuella fel måste man kunna se exakt vilka bearbetningar som gjorts av data, och av vem.

_Varför?_<br>
Med versionshantering blir det enklare att upptäcka fel och spåra följdeffekterna.

_Hur?_
 * Sträva efter att göra all databearbetning i kod.
 * Om databearbetning görs i kalkylprogram eller liknande, spara varje ny version under ett nytt namn. Varje datafil får en egen mapp, som döps efter originaldatafilen. Versionsfilerna namnges sedan enligt konventionen `YYMMDDxx - ändringsbeskrivning` där `xx` är ett löpnummer om man gör flera ändringar under samma dag. Till exempel:  `sverigekarta/2015060401 - Lade till postnummergränser.shp`
 * Men ännu hellre versionshanterar vi med Git.
 * När vi samarbetar med andra, kan vi arbeta med en Dropbox-mapp, synkad till Github, eller testa någon av alla lösningar för att synka Google Docs med Github.


## Standardformat för data på fil

_Vad?_<br/>
Vi använder alltid samma format för data på fil.

_Varför?_<br>
Enhetliga filformat minskar risken för att fel införs i samband med konverteringar. Filformatet signalerar också vilken typ av data filen innehåller.

_Hur?_
 * CSV-filer för tabeller (kommaseparerade kolumner, citattecken som strängcontainer)
 * XLSX-filer för tabeller med formler
 * JSON för hierarkisk data
 * Shapefiler för geodata
 * ...och alltid UTF-8


## Line-by-line för artiklar

_Vad?_<br/>
Artikeltexter faktagranskas påstående för påstående.

_Hur?_
 * Den som inte själv varit aktiv i research leder line-by-line-läsningen av artiklar.
 * Tänk på att påståenden inte bara finns i text, utan också i illustrationer. Även en koroplet-karta är en utsaga!


## Öppenhet

_Vad?_<br/>
Fundera i varje projekt på vad vi kan bjuda kollegor och andra intresserade på, som hjälper oss att få fler ögon på datan. Har vi tagit fram något unikt, som andra är intresserade av? Bjussa på det!

_Varför?_<br>
Med öppenhet upptäcker vi svagheterna tidigare.

_Hur?_
 * Ge projektet ett öppet Github-repo, så ofta det går.
 * ...med en README-fil som förklarar vad projektet handlar om.
 * Github-repot ska om möjligt innehålla originaldata.
 * Identifiera något i projektet som andra kan ha nytta av, och dela det. För delning av kalkylarks använder vi i första hand Google Sheets.
