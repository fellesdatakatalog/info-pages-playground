# Hvordan lage og publisere en datasettbeskrivelse fra A til Å

Denne veiledningen tar deg gjennom alle trinnene som trengs for å komme i mål, fra å finne ut hvilket datasett du vil beskrive til å få det publisert til data.norge.no! Disse inkluderer:

- 1. Kartlegging og forberedelser.
- 2. Hvordan lage selve datasettbeskrivelsen.
- 3. Hvordan registrere et nettsted/endepunkt som data.norge.no kan hente beskrivelsen fra.
- 4. Hvordan starte en høsting sånn at data.norge.no henter og publiserer beskrivelsen din.

Underveis viser vi konkrete eksempler på hvordan gjøre de ulike stegene basert på datasettet "KI-prosjekter i offentlig sektor" fra Digdir. Disse eksemplene er rammet inn i en sånn boks som denne teksten er i. [TODO: legge til fargekoding].

## Forberedelser
For å kunne fullføre trinn 3 og 4 i prosessen må du ha de riktige tilgangene og rettighetene til data.norge.no sine løsninger, sånn at du kan logge inn i og bruke løsningene.
Du finner informasjon om hvordan få tilgang på [denne siden](TODO:lenke). Mens du venter på å få tilgang fra den ansvarlige i virksomheten, kan du gjerne fortsette med trinn 1 og 2 i denne veiledningen.


## Kartlegging

> **__Merk:__**
Virksomheten du jobber for følger kanskje [Orden i eget hus-veilederen](TODO:lenke) og du er en del av denne prosessen. Dette er en oversiktlig og nyttig veileder for å få oversikt over hvilke data virksomheten sitter på og som den kan dele med andre. Selv om virksomheten ikke har fullført alle stegene i veilederen kan dere gjerne publisere informasjon om de datasettene dere allerede har kartlagt. Beskrivelsene kan gradvis forbedres og utvides etter hvert som dere kommer videre i arbeidet med Orden i eget hus.

Aller først må du vite hvilke data du vil beskrive, og informasjon som kan være nyttig å ha klart er:
- Hva tittel på datasettet skal være.
- Hvordan du tekstlig vil beskrive datasettet.
- Oversettelser av tittel og beskrivelse, sånn at det er tilgjengelig på bokmål, nynorsk og engelsk.
- Hvilken virksomhet som eier og utgir datasettet og virksomhetens organisasjonsnummer.
- Kontaktinformasjon (epost) til de som er ansvarlig for datasettet.
- Om datasettet skal tilbys åpent
  - og i så fall, om det er tilgjengelig via filnedlasting eller API

> **__Merk:__**
Spørsmål om hvorvidt datasettet skal tilbys åpent eller være lukket, og hvilke lisenser som skal brukes er ofte mat for jurister. Mens dere gjør disse avklaringene kan du fortsatt publisere all den andre informasjonen. Når dere har blitt enig om hvorvidt datasettet skal være åpent, hvordan det skal tilgjengeliggjøres og hvilke lisenser som gjelder, kan du utvide beskrivelsen med denne informasjonen.

### Eksempel på kartlegging: KI-prosjekter i offentlig sektor
Digdir tilbyr et datasett med oversikt over KI-prosjekter i offentlig sektor. I beskrivelsen av dette datasettet vil vi ha med i alle fall følgende informasjon:

- Tittelen er "Kunstig intelligens - oversikt over prosjekter i offentlig sektor".
- Bokmålsbeskrivelsen er "En oversikt over kunstig intelligens-prosjekter i offentlig sektor. Oversikten er ikke komplett."
  - Oversettelse til nynorsk og engelsk legger vi til etterpå.
- Utgiveren er Digitaliseringsdirektoratet, med organisasjonsnummer 991825827.
- De ansvarlige for datasettet i Digdir kan kontaktes på eposten <kunstigintelligens@digdir.no>
- At datasettet kan knyttes til temaet "offentlig forvaltning", ved hjelp av en kode fra en felles kodeliste.
  - Hvordan dette gjøres viser vi senere i veiledningen.

Dette er all informasjonen som trengs for å dekke de obligatoriske feltene for en datasettbeskrivelse. Det er i tillegg et par andre ting vi ønsker å ta med for at datasettet skal være enkelt å finne og ta i bruk for andre:

- Datasettet har en egen nettside: <https://data.norge.no/kunstig-intelligens>
- Datasettet er tilgjengelig som filnedlasting fra [Digdir sin Github-side](https://github.com/Informasjonsforvaltning/ai-project-service/blob/main/ai_projects_norwegian_state%20-%20Oversatt_v1.csv).
- Datasettet tilbys/distribueres som CSV-fil
- Datasettet er åpent og tilgjengelig og lisensiert med Apache-2.0-lisensen.
- Innholdet i datasettet er på bokmål.
- Datasettet ble utgitt 23. februar 2023.
- Datasettet kan knyttes til nøkkelordene "kunstig intelligens" og "offentlig sektor".
- Datasettet er basert på innsamling av informasjon fra tredjeparter.


> **__Merk:__**
Når vi bruker felles koder og nøkkelord blir datasettet enklere å søke opp.




## Lage beskrivelsen
Da er du klar til å lage beskrivelsen i riktig format, sånn at det kan publiseres til data.norge.no. Det er her moroa begynner!

> **__Merk:__**
Vi må lage beskrivelsen i et strukturert dataformat som data.norge.no kan forstå maskinelt. Dette formatet heter RDF (Resource Description Framework) og er i bruk også blant andre europeiske dataportaler og i flere private virksomheter sine datakataloger. RDF har ulike serialiseringsformater, som betyr at vi kan skrive RDF på ulike måter. I eksemplene under bruker vi RDF-formatet som heter Turtle, men du velger selv hvilket du vil bruke. Til slutt viser vi også et komplett eksempel i JSON-LD som er et annet RDF-format.

> **__Merk:__**
Vi skiller mellom Datasett, Distribusjon og Datatjeneste/API for å tydeliggjøre at et datasett kan tilgjengeliggjøres på flere måter. I denne sammenhengen er "datasett" en ganske abstrakt ting, mens de konkrete filene og endepunktene du kan hente dataen fra kalles for distribusjon og datatjeneste.


Lage beskrivelsen (Katalog + Ressurser)
Hva er RDF
Eksempel på beskrivelse med obligatoriske felter (trinn for trinn)
Eksempel på bruk av kodeliste + ofte brukte kodelister
Komplett eksempel

Sette opp endepunkt som tjener beskrivelsen
raw.github.com
Egen-hosted tjeneste
Content-negotiation text/turtle
Ev. med API-nøkkel

Registrere endepunkt i administrasjonsløsning for høsting
Bilder, gjennomgang av skjema

Trigge høsting