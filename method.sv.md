## Disputation

_vad?_<br/>
En person i redaktionen ska hållas helt utanför researchen. Hen är vår ”opponent”. Opponenten kallar till ett slags intern disputation i slutet av projektet.

_varför?_<br>
Med en disputation upptäcker vi fler svagheter själva.

_hur?_<br>
Opponenten ska:
 * Ifrågasätta definitioner
 * Kontrollera mot [dataregistret](#dataregister) att rätt data används till rätt sak
 * Fråga hur uträkningar gjorts
 * Bedöma om slutsatserna är rimliga
 * Göra _flera_ stickprov
 * Göra en formmässig korrläsning: sifferformat, enheter, skalor etc


## <span id="dataregister">Centralt register med ursprungsdata</span>

_vad?_<br/>
I början av varje projekt ska all originaldata samlas på ett ställe.

_varför?_<br>
Med ett centralt dataregister undviker vi att data om- och feldefinieras på vägen.

_hur?_
 * All originaldata samlas (och skrivskyddas) i en mapp
 * Där ska också finnas en textfil med källförteckning
 * Notera gärna antalet rader (eller relationer, eller motsvarande beroende på datatyp) för varje dataset i textfilen, för att kunna dubbelkolla att ingen data trunkerats under projektets gång.
 * Alla nya datakällor som tillkommer ska föras in här.


## Inledande datakoll

_vad?_<br/>
När projektet inleds, och när ny data hämtas in, ska det finnas tid avsatt att kontrollera datavaliteten.

_varför?_<br>
Med en inledande datakoll kan upptäcka export- och importfel, och fel som begåtts av avsändaren

_hur?_
 * Pivotera på nyckelkolumner för att se att där inte finns olika stavningar av samma namn.
 * Kontrollera att alla [kommuner/länder/personer/sjukdomar/etc] finns med. 
 * Kontrollera nollvärden. Ska det vara 0, eller är det tomma rutor som blivit kodade som nollor på vägen?
 * Kontrollera tomma rutor. Ska de vara tomma?
 * Är värdena rimliga?
 * Visualisera, för att få syn på märkliga mönster, extremt avvikande punkter, etc.


## Versionshantering

_vad?_<br/>
För att kunna spåra eventuella fel måste man kunna följa med vilka bearbetningar som gjorts av data, och av vem.

_varför?_<br>
Med versionshantering upptäcker vi misstag enklare<br>
Med versionshantering ser vi enklare om ett fel fått följdeffekter<br>

_hur?_
 * Sträva efter att göra all databearbetning i kod.
 * Om databearbetning görs i kalkylprogram eller liknande, spara varje ny version under ett nytt namn. Varje datafil får en egen mapp, som döps efter originaldatafilen. Versionsfilerna namnges sedan enligt konventionen `YYMMDDxx - ändringsbeskrivning`. Till exempel: `sverigekarta/15060401 - Lade till postnummergränser.shp`
 * Eller versionshantera ännu hellre med Git + Github.
 * När vi samarbetar med andra, kan vi arbeta med en Dropbox-mapp, synkad till Github, eller testa någon av alla lösningar för att synka Google Docs med Github.


## Standardformat för data på fil

_vad?_<br/>
Vi använder alltid samma format för data på fil.

_varför?_<br>
Enhetliga filformat minskar risken för att fel införs i samband med konverteringar.

_hur?_
 * CSV-filer för tabeller (kommaseparerade kolumner, citattecken som strängcontainer)
 * XLSX-filer for tabeller med formler
 * JSON för hierarkisk data
 * Shapefiler för geodata
 * ...och alltid UTF-8


## Line-by-line för artiklar

_hur?_<br>
 * Den som inte själv varit aktiv i research leder line-by-line-läsningen av artiklar.
 * Tänk på att påståenden inte bara finns i text, utan också i illustrationer. Även en koroplet-karta är en utsaga!


## Öppenhet

Ett öppet Github-repo är i sig ingen garant för att någon kommer att gå in och granska vår data. Fundera i varje projekt på vad vi kan bjuda kollegor och andra intresserade på, som hjälper oss att få fler ögon på datan. Har vi tagit fram något unikt, som andra är intresserade av? Bjussa på det!

_varför?_<br>
Med öppenhet upptäcker vi svagheterna tidigare

_hur?_<br>
 * Öppet Github-repo, så ofta det går
 * ...med en README-fil som dokumenterar
 * Identifiera något i projektet som andra kan ha nytta av, och dela det, i första hand via Google Sheets
 * Github-repot ska om möjligt innehålla originaldata

## Inspiration
*[A Guide to Bulletproofing Your Data, Jennifer LaFleur, ProPublica](https://github.com/propublica/guides/blob/master/data-bulletproofing.md)
*[Sixteen solutions for data-driven projects](https://docs.google.com/presentation/d/18KE-VO9T6V1I_aGyekdDtFhYP4K0Saph7aBuBS3N8tc/edit#slide=id.ga85f0df1a_049)