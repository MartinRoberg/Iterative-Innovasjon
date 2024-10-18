# Iterasjon 2

Vekk med FHIR

---

## Fast Healthcare Interoperability Resources (FHIR)

> FHIR er en standard som beskriver dataformater og elementer og en API Application Programming Interface () for å utveksle
> elektronisk helseinformasjon.
>
> \- Ehelse

Note:

---

## En vakker dag

Note:
Etter en leveranse som igjen gikk på overtid, tok vi en retrospekt.
Det var en fantastisk dag.
Jeg tror ikke jeg har sett et rom mennesker være mer
enig om hva som skaper stress og hat i livet dems.
Vi bestemte oss for at FHIR staging databasen var problemet og måtte vekk.

---

## Løsningen

Note:
HL7 er det formatet vi leverer.
Det bør være det formatet vi lagrer data på.
Vi valgte da å bygge våre egen staging database på akkurat det formatet vi selv ønsket.
Der lagret vi dataen på den måten som passet oss best.
Noen ganger er det faktisk bedre å gjøre ting på din helt egen måte.

---

## Resultatet

- Mye mindre kompleksitet <!-- .element: class="fragment fade-up" data-fragment-index="1" -->
- Optimalisering og validering <!-- .element: class="fragment fade-up" data-fragment-index="2" -->
- Mer tid til det som betyr noe <!-- .element: class="fragment fade-up" data-fragment-index="3" -->
- 3 uker -> 1 helg <!-- .element: class="fragment fade-up" data-fragment-index="4" -->

Note:
Den nye staging var mye bedre og enklere å jobbe i.
Vi kunne optimalisere mange steg i prossesen, siden prossesen plutselig ble mye enklere.
Det ga oss også muligheten til å validere dataen som kom inn fra kommunene.
Da spesielt pasient info / person info.
Vi fikk mer tid til å bruke med kommunene, og på å passe på at dataen ble levert med integiritet.
Vi gikk fra at utvikling tok mest tid for hver kommune / kildesystem, til at vi brukte mest tid på analyse og kommunikasjon.
Innsetting av nye utvikler var også ekstremt mye enklere og tok mye kortere tid.

---

## Iterasjon 2

<img src="/Iterative-Innovasjon/Iter_2.svg">

Note:
Sånn ble arkitekturen til slutt i iterasjon 2.
En mye forenklet og mye bedre versjon, selv om det ikke er åpenbart fra skissen.
Men her var det også forbedringspotensiale.
Og det potensiale fantes i selve ETL delen.
