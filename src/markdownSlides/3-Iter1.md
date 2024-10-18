# Iterasjon 1

Når en god tanke blir dårlig

Note:
Siden de ikke viste hvilken leverandør man fikk, så visste man da heller ikke formatet dataen skulle ha.
Hva gjør man når man skal lage en ETL prosses som får masse ulik data til å passe på samme format...

Når man ikke vet hvilket format man trenger det på? _Spør ut i salen_
Jo, man gjør antagelser.

---

<img src="/Iterative-Innovasjon/Iter_1.svg">
Note:
Forklar bildet.
Kommunene leverer db. Vi har en ETL prosess som flytter dataen inn i en FHIR staging.
En til ETL flytter dataen inn i HP.
Håpet her var at begge ETL-ene skulle være simple og enkle å vedlikeholde.
Det var de ikke.

---

## Feil antagelsen

1. FHIR <!-- .element: class="fragment fade-up" data-fragment-index="1" -->
2. FHIR <!-- .element: class="fragment fade-up" data-fragment-index="2" -->
3. FHIR for all <!-- .element: class="fragment fade-up" data-fragment-index="3" -->

Note:
Teamet gjorde 3. antagelser.

1. De antok at man kunne levere data på FHIR-formatet
2. De antok at alle kommunene kom til å levere dataene sine på FHIR-formatet istedenfor rene database-kopier.
3. De antok også at det holdt med en felles staging database for alle kildesystemene/kommunene. I FHIR selvfølgelig

Så de bygde en prosses rundt dette.
Alle disse antagelsene viste seg senere å være feil.
Skal forklare hva FHIR er etterpå.

---

## Virkheligheten

1. Epic forventer HL7
2. Kommunene sa nei
3. Altfor komplekst å ha alt i samme staging

---

## Resultatet

Note:

1. Veldig komplekse ETL-er
2. Lang utviklingstid -> Lite tid til det som betyr noe
3. Leveranser blir lange
   Forklar punktene.
   ETL-ene var ekstremt komplekse å vedlikeholde, siden man måtte om formatere data to ganger.
   Vi brukte mer tid på å krangle med staging databasen en vi brukte på å sikre at dataen kom fram på en god måte.
   Leveransene var fulle av problemer og uforutsigbarhet. Overseinding av data tok lang tid, og planlagte helg-leveranser ble levert over 3 uker istedet.
