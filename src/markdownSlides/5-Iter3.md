# Iterasjon 3

Pure-SQL

---

## SQL-Server Integration Services <br/>(SSIS)

Note:
Low-code løsning til microsoft.
Man setter opp dataflyter for å transformere og flytte data fra a til b.

---

## Problemene

1. Unødvendig kompleksitet
2. Vanskelig med Code-review
3. Skjuler det som skjer (black box)

Note:
Det var unødvendig kompleksitet.
Vi måtte tvinge det til å fungere på en måte det nesten ikke var designet for.
Det var veldig vanskelig å gjøre code-review på det, siden ssis lagrer dataflytene sine i XML filer.
Det foresaket at en viktig sql endring som ble gjort i flyten ble skjult av de andre 50 urelvenate endringene som ssis gjorde av seg selv.
Man skulle tro motsatt med en lowcode løsning, men det endte også opp med å skjule den faktiske prossesen bak mange "svarte bokser".

---

## Den etterlengtede løsningen

Note:
Dette var ikke et nytt problem fra iterasjon 2. Det fantes fra iterasjon 1.
Derimot siden vi hadde løsninger rettet mot FHIR-staging i iter 1, så ville det tatt for mye tid å endre det.
Dette er... fram til iter 2.
I iterasjon 2 byttet vi jo ut staging, og reduserte kompleksiteten knyttet til den betraktlig.
Det la grunnlaget for endre til den løsning vi hadde diskutert lenge.

---

## Pure-SQL

Note:
Løsningen vi ønsket var pure-sql.
Hva menner jeg med det?
Jo, vi kastet ut visual studio prosjektet, med masse ssis dataflyter og kompleksitet.
Og vi byttet det ut med en rekke sql-filer, som vi kunne laste inn som stored procedures rett inn i staging databasen.
Dette gjorde at vi kunne ha all logikk på ett og samme sted, i ett og samme verktøy.
For at dette skulle funke så som sagt måtte vi utvikle vårt eget software for å håndtere kompleksiteten rundt sql filene.
Dette fikset teamets designerte magiker, og lagde et inhouse verktøy for å håndtere alt dette.
Det verktøyet videretutvikler de fortsatt idag inhouse, og forenkler prossesen mer og mer.

---

## Resultatet

- Enda mer tid til det viktige (for mye tid...) <!-- .element: class="fragment fade-up" data-fragment-index="1" -->
- No more black box <!-- .element: class="fragment fade-up" data-fragment-index="2" -->
- Code-review er enkelt <!-- .element: class="fragment fade-up" data-fragment-index="3" -->
- Kode-kvalitet går opp <!-- .element: class="fragment fade-up" data-fragment-index="4" -->
- Leveranse tid går ned <!-- .element: class="fragment fade-up" data-fragment-index="5" -->

Note:
Forklar punktene
For mye tid, for vi hadde egentlig for lite å gjøre fra før av.
Black box no more.
Det var plutselig kun endringer der det faktisk var en endring.
Kode kvalitet gikk opp, debugging var enklere, og dermed var det mindre problemer under leveranser.
Og leveranse tiden gikk ned til 4 timer.
