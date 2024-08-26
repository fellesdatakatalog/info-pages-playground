# Hvordan lage og publisere en datasettbeskrivelse fra A til Å

Denne veiledningen tar deg gjennom alle trinnene som trengs for å komme i mål, fra å finne ut hvilket datasett du vil beskrive, til å få det publisert til data.norge.no! Vi går igjennom:

- 1. Forberedelser og kartlegging.
- 2. Hvordan lage selve datasettbeskrivelsen.
- 3. Hvordan registrere et nettsted/endepunkt som data.norge.no kan hente beskrivelsen fra.
- 4. Hvordan starte en høsting sånn at data.norge.no henter og publiserer beskrivelsen din.

Underveis viser vi konkrete eksempler på hvordan gjøre de ulike stegene basert på datasettet "KI-prosjekter i offentlig sektor" fra Digdir. Disse eksemplene er rammet inn i en sånn boks som denne teksten er i. [TODO: legge til fargekoding].

## Forberedelser
For å kunne fullføre trinn 3 og 4 i prosessen må du ha de riktige tilgangene og rettighetene til data.norge.no sine løsninger, slik at du kan logge inn og bruke løsningene.
Du finner informasjon om hvordan få tilgang på [denne siden](TODO:lenke). Mens du venter på å få tilgang fra den ansvarlige i virksomheten, kan du gjerne fortsette med trinn 1 og 2 i denne veiledningen.


## Kartlegging

> **__Merk:__**
Virksomheten du jobber for følger kanskje [Orden i eget hus-veilederen](TODO:lenke) og du er en del av denne prosessen. Dette er en grundig og nyttig veileder for å få oversikt over hvilke data virksomheten sitter på og som den kan dele med andre. Selv om virksomheten ikke har fullført alle stegene i veilederen kan dere gjerne publisere informasjon om de datasettene dere allerede har kartlagt. Beskrivelsene kan gradvis forbedres og utvides etter hvert som dere kommer videre i arbeidet med Orden i eget hus.

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

> **__Nyttig å vite:__**
Vi må lage beskrivelsen i et strukturert dataformat som data.norge.no sitt system kan forstå. Dette formatet heter RDF (Resource Description Framework) og er i bruk også blant andre europeiske dataportaler og i flere private virksomheter sine datakataloger. RDF kan skrives på flere ulike måter – i eksemplene under bruker vi RDF-formatet som heter Turtle – men du velger selv hvilket du vil bruke. Helt til slutt viser vi et komplett eksempel i JSON-LD som er et annet RDF-format.

> **__Viktig:__**
Du bør bruke et tekstredigeringsprogram som ikke formaterer teksten. Microsoft Word egner seg dårlig, mens Windows Notepad, VS Code eller lignende fungerer bra.

TODO: lenke til introduksjon om RDF


> **__Merk:__**
For å spare plass i eksemplene har vi utelatt de såkalte prefiksene. Men alle eksemplene trenger at prefiksene listet opp rett under er definert for å være gyldig Turtle og RDF. Så bare forestill deg at disse linjene står før hvert eksempel. Til slutt kommer et komplett eksempel hvor vi også inkluderer prefiksene.
```turtle
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix dcat: <http://www.w3.org/ns/dcat#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix vcard: <http://www.w3.org/2006/vcard/ns#> .
```


### Identifikator for beskrivelsen (URI)
Aller først må vi angi en unik identifikator for datasettbeskrivelsen, i form av en URI (Uniform Resource Identifer). Den bør være persistent og unik. URI-en kan peke til en faktisk nettressurs som er tilgjengelig på nett, men det er ikke nødvendig.

For beskrivelsen av KI-prosjekter bruker vi URI-en `https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset`. Denne identifikatoren kan nå brukes av alle systemer overalt for å peke til nøyaktig den samme tingen.

### Tittel og beskrivelse

Vi vil nå legge til tittelen vi har forberedt, både på bokmål, nynorsk og engelsk. Da bruker vi egenskapen `dct:title`, og kan angi språket for teksten med `@nb` for bokmål, `@nn` for nynorsk og `@en` for engelsk. Resultatet blir slik:

```text/turtle
<https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset> rdf:type dcat:Dataset ;
  dct:title "Kunstig intelligens - oversikt over prosjekter i offentlig sektor"@nb ,
            "Kunstig intelligens - oversikt over prosjekt i offentleg sektor"@nn ,
            "Artificial intelligence - overview of projects in the public sector"@en ;
  .
```

Og tilsvarende vil vi legge til beskrivelsen på bokmål, nynorsk og engelsk. Til det bruker vi egenskapen `dct:description`:

```text/turtle
<https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset> rdf:type dcat:Dataset ;
  dct:title "Kunstig intelligens - oversikt over prosjekter i offentlig sektor"@nb ,
            "Kunstig intelligens - oversikt over prosjekt i offentleg sektor"@nn ,
            "Artificial intelligence - overview of projects in the Norwegian public sector"@en ;
  dct:description "En oversikt over kunstig intelligens-prosjekter i offentlig sektor. Oversikten er ikke komplett."@nb ;
                  "Ei oversikt over kunstig intelligens-prosjekt i offentleg sektor. Oversikta er ikkje komplett"@nn ;
                  "An overview of artificial intelligence projects in the public sector. The overview is not complete."@en ;
  .
```

### Utgiver og kontaktpunkt for datasett

> **__Merk:__**
I de følgende eksemplene utelater vi linjene som starter med `@prefix`, men disse må være med for at det skal være en gyldig RDF-fil. Vi viser et komplett eksempel til slutt som er gyldig RDF.

Vi vil nå si at Digitaliseringsdirektoratetet, med organisasjonsnummer 991825827 er utgiver av datasettet. Vi bruker da egenskapen `dct:publisher` og peker til en URI som representerer Digdir: `https://organization-catalogue.fellesdatakatalog.digdir.no/organizations/991825827`. Denne URI-utformingen følger konvensjonen blant datasettbeskrivelser i Norge. Publiserer du for en annen virksomhet kan du bare bytte ut de siste ni sifrene i URI-en med organisasjonsnummeret til virksomheten som er ansvarlig for datasettet du beskriver.

I tillegg vil vi legge til informasjon om hvem som i Digdir som kan kontaktes angående spesifikt dette datasettet. Det gjør vi ved hjelp av et kontakt-kort `vcard:Organization`, og der vil vi oppgi navn og epost med egenskapene `vcard:fn` og `vcard:hasEmail`.

Beskrivelsen vil da se slik ut:

```text/turtle
<https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset> rdf:type dcat:Dataset ;
  # ...tittel og beskrivelse utelatt
  dct:publisher <https://organization-catalogue.fellesdatakatalog.digdir.no/organizations/991825827> ;
  dcat:contactPoint <https://data.digdir.no/contact/aiContactPoint> ;
  .

<https://data.digdir.no/contact/aiContactPoint> rdf:type vcard:Organization ;
  vcard:hasEmail "kunstigintelligens@digdir.no" ;
  vcard:fn "Kunstig Intelligens Digdir" ;
  .
```

#### Ressurser uten navn: Blanke noder

I beskrivelsen over har kontaktinfoen fått en egen identifikator, `<https://data.digdir.no/contact/aiContactPoint>`, noe som egentlig ikke er nødvendig. Det eneste vi trenger er nemlig eposten og navnet på gruppen eller teamet i Digdir som kan kontaktes, kontaktpunktet trenger ikke en egen identifikator. For å unngå dette kan vi opprette en såkalt blank node, eller navnløs ressurs, ved hjelp av hakeparenteser `[...]`. Det vil da se slik ut:


```text/turtle
<https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset> rdf:type dcat:Dataset ;
  # ...tittel og beskrivelse utelatt
  dct:publisher <https://organization-catalogue.fellesdatakatalog.digdir.no/organizations/991825827> ;
  dcat:contactPoint [
    rdf:type vcard:Organization ;
    vcard:hasEmail "kunstigintelligens@digdir.no" ;
    vcard:fn "Kunstig Intelligens Digdir" ;
  ] ;
  .
```

Dette sier akkurat det samme som beskrivelsen over, men her slipper vi å lage en unødvendig URI for kontaktpunktet.


### Nøkkelord og tema

Datasettet kan knyttes til noen nøkkelord, for eksempel "kunstig intelligens" og "offentlig sektor". Vi bruker egenskapen `dct:keyword` og lager tekster på både på bokmål, nynorsk og engelsk.

```text/turtle
<https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset> rdf:type dcat:Dataset ;
  # ...
  dct:keyword "kunstig intelligens"@nb , "kunstig intelligens"@nn , "artificial intelligence"@en,
              "offentlig sektor"@nb , "offentleg sektor"@nn , "public sector"@en ;
  .
```

I tillegg vil vi bruke egenskapen `dcat:theme` for å knytte datasettet til koder fra offentlige kodelister som EU forvalter. Vi vil bruke to koder her: den første er fra kodelisten Data Theme, `http://publications.europa.eu/resource/authority/data-theme/GOVE`, og den andre er fra kodelisten EuroVoc, `http://eurovoc.europa.eu/3030`. Den første sier at datasettet kan tematisk knyttes til offentlig sektor ("Government and public sector"), mens den andre koden peker til begrepet "Artifical Intelligence". Dette vil se ut slik i Turtle:

```text/turtle
<https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset> rdf:type dcat:Dataset ;
  # ...
  dcat:theme <http://publications.europa.eu/resource/authority/data-theme/GOVE>,
             <http://eurovoc.europa.eu/3030> ;
  .
```

Alle datasettbeskrivelser må ha minst ett tema angitt med `dcat:theme`, og temaet må enten peke til kodelisten Data Theme eller kodelisten EuroVoc. I tillegg kan man peke til temaer fra kodelisten LOS som Digdir forvalter.

For å finne aktuelle koder til din beskrivelse kan du se gjennom innholdet i kodelistene på:
- [Oversikt over koder i Data Theme (op.europa.eu)](https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/data-theme)
- [Oversikt over koder i EuroVoc (op.europa.eu)](https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://eurovoc.europa.eu/100141)

I tillegg har vi skrevet en egen [side om hvordan bruke koder](TODO:legg-til-lenke) for å merke datasett tematisk. Ta gjerne en kikk der om du lurer på noe.

### Geografisk avgrensing
Ved hjelp av egenskapen `dct:spatial` og en eksisterende kode som representerer det geografiske området Norge kan vi uttrykket at datasettet er begrenset til Norge:

```text/turtle
<https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset> rdf:type dcat:Dataset ;
  # ...
  dct:spatial <http://publications.europa.eu/resource/authority/country/NOR> ;
  .
```

### Dataopphav og tilgang
Vi vil si at datasettet er basert på innsamling fra tredjeparter, og at datasettet har åpen tilgang. For å beskrive datasettets opphav bruker vi egenskapen `prov:wasGeneratedBy` og peker til en kode som representerer "Innsamlet fra tredjeparter". For å uttrykke at at datasettet er åpent bruker vi egenskapen `dct:accessRights` og peker til eksisterende koder som representerer "Åpen data".

```text/turtle
<https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset> rdf:type dcat:Dataset ;
  # ...
  prov:wasGeneratedBy <https://data.norge.no/vocabulary/provno#collectingFromThirdparty> ;
  dct:accessRights <http://publications.europa.eu/resource/authority/access-right/PUBLIC> ;
  .
```

### Nettsiden

Datasettet har en egen nettside som kan besøkes på <https://data.norge.no/kunstig-intelligens>. Det kan vi legge til i beskrivelsen med egenskapen `foaf:page`.

```text/turtle
<https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset> rdf:type dcat:Dataset ;
  # ...
  foaf:page <https://data.norge.no/kunstig-intelligens> ;
  .
```


### Komplett beskrivelse av datasettet:
TODO: fyll ut

### Tilgjengeliggjøring via distribusjon/filnedlasting

Nå har vi oppgitt ganske mye informasjon *om* datasettet, men vi har fortsatt ikke beskrevet hvordan andre kan få tak i dataen og laste den ned. Siden vi tilbyr dataen som en fil fra Github kan vi beskrive det som en Distribusjon (`dcat:Distribution`) og legge til informasjon om den.

> **__Merk:__**
Vi skiller mellom Datasett, Distribusjon og Datatjeneste/API for å tydeliggjøre at et datasett kan tilgjengeliggjøres på flere måter. I denne sammenhengen er datasett en ganske abstrakt ting, mens de konkrete filene og endepunktene du kan hente dataen fra kalles for distribusjon og datatjeneste.

#### Beskrivelse og utgivelsesdato

#### Lisens og språk

### Format og mediatype

#### Tilgangs-URL og nedlastings-URL


- Datasettet er tilgjengelig som filnedlasting fra [Digdir sin Github-side](https://github.com/Informasjonsforvaltning/ai-project-service/blob/main/ai_projects_norwegian_state%20-%20Oversatt_v1.csv).
- Datasettet tilbys/distribueres som CSV-fil
- Datasettet er åpent og tilgjengelig og lisensiert med Apache-2.0-lisensen.
- Innholdet i datasettet er på bokmål.
- Datasettet ble utgitt 23. februar 2023.

### Tilgjengeliggjøring via API


### Knytte datasettet til en katalog




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