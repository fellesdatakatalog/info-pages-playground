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

> **Merk:**
> Virksomheten du jobber for følger kanskje [Orden i eget hus-veilederen](TODO:lenke) og du er en del av denne prosessen. Dette er en grundig og nyttig veileder for å få oversikt over hvilke data virksomheten sitter på og som den kan dele med andre. Selv om virksomheten ikke har fullført alle stegene i veilederen kan dere gjerne publisere informasjon om de datasettene dere allerede har kartlagt. Beskrivelsene kan gradvis forbedres og utvides etter hvert som dere kommer videre i arbeidet med Orden i eget hus.

Aller først må du vite hvilke data du vil beskrive, og informasjon som kan være nyttig å ha klart er:

- Hva tittel på datasettet skal være.
- Hvordan du tekstlig vil beskrive datasettet.
- Oversettelser av tittel og beskrivelse, sånn at det er tilgjengelig på bokmål, nynorsk og engelsk.
- Hvilken virksomhet som eier og utgir datasettet og virksomhetens organisasjonsnummer.
- Kontaktinformasjon (epost) til de som er ansvarlig for datasettet.
- Om datasettet skal tilbys åpent
  - og i så fall, om det er tilgjengelig via filnedlasting eller API

> **Merk:**
> Spørsmål om hvorvidt datasettet skal tilbys åpent eller være lukket, og hvilke lisenser som skal brukes er ofte mat for jurister. Mens dere gjør disse avklaringene kan du fortsatt publisere all den andre informasjonen. Når dere har blitt enig om hvorvidt datasettet skal være åpent, hvordan det skal tilgjengeliggjøres og hvilke lisenser som gjelder, kan du utvide beskrivelsen med denne informasjonen.

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

> **Merk**
> Når vi bruker felles koder og nøkkelord blir datasettet enklere å søke opp.

## Lage beskrivelsen

Da er du klar til å lage beskrivelsen i riktig format, sånn at det kan publiseres til data.norge.no. Det er her moroa begynner!

> **Nyttig å vite:**
> Vi må lage beskrivelsen i et strukturert dataformat som data.norge.no sitt system kan forstå. Dette formatet heter RDF (Resource Description Framework) og er i bruk også blant andre europeiske dataportaler og i flere private virksomheter sine datakataloger. RDF kan skrives på flere ulike måter – i eksemplene under bruker vi RDF-formatet som heter Turtle – men du velger selv hvilket du vil bruke. Helt til slutt viser vi et komplett eksempel i JSON-LD som er et annet RDF-format.

> **Viktig:**
> Du bør bruke et tekstredigeringsprogram som ikke formaterer teksten. Microsoft Word egner seg dårlig, mens Windows Notepad, VS Code eller lignende fungerer bra.

TODO: lenke til introduksjon om RDF

> **Merk**
> For å spare plass i eksemplene har vi utelatt de såkalte prefiksene. Men alle eksemplene trenger at prefiksene listet opp rett under er definert for å være gyldig Turtle og RDF. Så bare forestill deg at disse linjene står før hvert eksempel. Til slutt kommer et komplett eksempel hvor vi også inkluderer prefiksene.

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

> **Merk**
> I de følgende eksemplene utelater vi linjene som starter med `@prefix`, men disse må være med for at det skal være en gyldig RDF-fil. Vi viser et komplett eksempel til slutt som er gyldig RDF.

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

Hele beskrivelsen av datasettet i Turtle-format vil så langt se slik ut:

```
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix dcat: <http://www.w3.org/ns/dcat#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix vcard: <http://www.w3.org/2006/vcard/ns#> .

<https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset> a dcat:Dataset ;
    dct:title "Kunstig intelligens - oversikt over prosjekter i offentlig sektor"@nb ,
            "Kunstig intelligens - oversikt over prosjekt i offentleg sektor"@nn ,
            "Artificial intelligence - overview of projects in the public sector"@en ;
    dct:description "En oversikt over kunstig intelligens-prosjekter i offentlig sektor. Oversikten er ikke komplett."@nb ;
                    "Ei oversikt over kunstig intelligens-prosjekt i offentleg sektor. Oversikta er ikkje komplett"@nn ;
                    "An overview of artificial intelligence projects in the public sector. The overview is not complete."@en ;
    dct:publisher <https://organization-catalogue.fellesdatakatalog.digdir.no/organizations/991825827> ;
    dcat:contactPoint [
      rdf:type vcard:Organization ;
      vcard:hasEmail "kunstigintelligens@digdir.no" ;
      vcard:fn "Kunstig Intelligens Digdir" ;
    ] ;
    dct:keyword "kunstig intelligens"@nb , "kunstig intelligens"@nn , "artificial intelligence"@en,
                "offentlig sektor"@nb , "offentleg sektor"@nn , "public sector"@en ;
    dcat:theme <http://publications.europa.eu/resource/authority/data-theme/GOVE>,
               <http://eurovoc.europa.eu/3030> ;
    dct:spatial <http://publications.europa.eu/resource/authority/country/NOR> ;
    prov:wasGeneratedBy provno:collectingFromThirdparty ;
    dct:accessRights <http://publications.europa.eu/resource/authority/access-right/PUBLIC> ;
    foaf:page <https://data.norge.no/kunstig-intelligens> ;
    .
```

Du kan kopiere denne teksten og validere at det er gyldig Turtle på <https://www.easyrdf.org/converter>.

### Tilgjengeliggjøring via distribusjon/filnedlasting

Nå har vi oppgitt ganske mye informasjon _om_ datasettet, men vi har fortsatt ikke beskrevet hvordan andre kan få tak i dataen og laste den ned. Siden vi tilbyr dataen som en fil fra Github kan vi beskrive det som en Distribusjon (`dcat:Distribution`) og legge til informasjon om den.

> **Merk**
> Vi skiller mellom Datasett, Distribusjon og Datatjeneste/API for å tydeliggjøre at et datasett kan tilgjengeliggjøres på flere måter. I denne sammenhengen er datasett en ganske abstrakt ting, mens de konkrete filene og endepunktene du kan hente dataen fra kalles for distribusjon og datatjeneste.

Vi må først si at datasettet **har** en distribusjon, til det bruker vi `dcat:distribution` som skal peke til en Distribusjonsressurs vi beskriver under.

```text/turtle
<https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset> rdf:type dcat:Dataset ;
  # ...
  dcat:distribution <https://data.digdir.no/datasets/ai_projects_norwegian_state_distribution> ;
  .

<https://data.digdir.no/datasets/ai_projects_norwegian_state_distribution> rdf:type dcat:Distribution .
```

Her har vi definert en ny ressurs som vi gir URI `https://data.digdir.no/datasets/ai_projects_norwegian_state_distribution` og sier at er av typen `dcat:Distribution`.

#### Tilgangs-URL og nedlastings-URL

Datasettet er tilgjengelig som filnedlasting fra Digdir sin Github-side, `https://github.com/Informasjonsforvaltning/ai-project-service/blob/main/ai_projects_norwegian_state%20-%20Oversatt_v1.csv`, og vi kan peke til denne med egenskapen `dcat:accessURL`. Dette er den eneste obligatoriske egenskapen for en distribusjonsbeskrivelse.

Men vi vil også legge til noe mer informasjon, f.eks. direktelenken til filen: `https://raw.githubusercontent.com/Informasjonsforvaltning/ai-project-service/main/ai_projects_norwegian_state%20-%20Oversatt_v1.csv`, den kan vi peke til med `dcat:downloadURL`. Distribusjon-beskrivelsen vil da se slik ut:

```text/turtle
<https://data.digdir.no/datasets/ai_projects_norwegian_state_distribution> rdf:type dcat:Distribution ;
  dcat:accessURL <https://github.com/Informasjonsforvaltning/ai-project-service/blob/main/ai_projects_norwegian_state%20-%20Oversatt_v1.csv> ;
  dcat:downloadURL <https://raw.githubusercontent.com/Informasjonsforvaltning/ai-project-service/main/ai_projects_norwegian_state%20-%20Oversatt_v1.csv> ;
  .
```

#### Beskrivelse og utgivelsesdato

Vi legger til en tekstlig beskrivelse av distribusjonen, og når den ble utgitt, og bruker feltene `dct:description` og `dct:issued` til det:

```text/turtle
<https://data.digdir.no/datasets/ai_projects_norwegian_state_distribution> rdf:type dcat:Distribution ;
  dct:description "CSV-fil med oversikt over kunstig intelligens-prosjekter i offentlig sektor"@nb ;
  dct:issued "2023-02-23"^^xsd:date ;
  .
```

#### Lisens

Distribusjonen har en Apache 2.0-lisens, som vi angir med egenskapen `dct:license`. Denne egenskapen _skal_ peke til et kontrollert vokabular/kodeliste fra EU.

```text/turtle
<https://data.digdir.no/datasets/ai_projects_norwegian_state_distribution> rdf:type dcat:Distribution ;
  dct:license <http://publications.europa.eu/resource/authority/licence/APACHE_2_0> ;
  .
```

Eksempler på noen andre lisenser fra EUs kodeliste er:

- `http://publications.europa.eu/resource/authority/licence/APACHE_2_0`
- `http://publications.europa.eu/resource/authority/licence/CC0`
- `http://publications.europa.eu/resource/authority/licence/CC_BY_4_0`

### Format og språk

Vi vil oppgi formatet til filen, som i vårt tilfelle er en CSV-fil; til det bruker vi egenskapen `dct:format` og peker til en kode i EU sitt vokabular "File Type" som representerer CSV.
I tillegg er innholdet i datasett på norsk - bokmål. Vi angår det med egenskapen `dct:language` og peker til koden fra EU sitt vokabular som angir norsk - bokmål:

```text/turtle
<https://data.digdir.no/datasets/ai_projects_norwegian_state_distribution> rdf:type dcat:Distribution ;
  dct:format <http://publications.europa.eu/resource/authority/file-type/CSV> ;
  dct:language <http://publications.europa.eu/resource/authority/language/NOB> ;
  .
```

### Kompett beskrivelse av distribusjon

Hele distribusjons-beskrivelsen vil da se slik ut:

```text/turtle
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix dcat: <http://www.w3.org/ns/dcat#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix vcard: <http://www.w3.org/2006/vcard/ns#> .

<https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset> rdf:type dcat:Dataset ;
  # ...
  dcat:distribution <https://data.digdir.no/datasets/ai_projects_norwegian_state_distribution> ;
  .

<https://data.digdir.no/datasets/ai_projects_norwegian_state_distribution> rdf:type dcat:Distribution ;
  dcat:accessURL <https://github.com/Informasjonsforvaltning/ai-project-service/blob/main/ai_projects_norwegian_state%20-%20Oversatt_v1.csv> ;
  dcat:downloadURL <https://raw.githubusercontent.com/Informasjonsforvaltning/ai-project-service/main/ai_projects_norwegian_state%20-%20Oversatt_v1.csv> ;
  dct:description "CSV-fil med oversikt over kunstig intelligens-prosjekter i offentlig sektor"@nb ;
  dct:issued "2023-02-23"^^xsd:date ;
  dct:license <http://publications.europa.eu/resource/authority/licence/APACHE_2_0> ;
  dct:format <http://publications.europa.eu/resource/authority/file-type/CSV> ;
  dct:language <http://publications.europa.eu/resource/authority/language/NOB> ;
  .
```

### Tilgjengeliggjøring via API

Vårt datasett er for øyeblikket ikke tilgjengelig via API, men vi kan forestille oss at det hadde vært det. Vi kan da bruke Datatjeneste-klassen (`dcat:DataService`) for å beskrive API-et.
Mye av informasjonen er tilsvarende som for Distribusjonen, men Datatjeneste har i tillegg noen flere obligatoriske felter.

For å si at datatjenesten tilbyr dataen for datasettet vi har beskrevet bruker vi egenskapen `dcat:servesDataset`. Merk at denne peker _fra_ Datatjenesten _til_ Datasettet:

```text/turtle
<https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset> rdf:type dcat:Dataset ;
  # ...
  .

<https://data.digdir.no/datasets/ai_projects_norwegian_state_api> rdf:type dcat:DataService ;
  dcat:servesDataset <https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset> ;
  .
```

### Endepunkts-URL, kontaktpunkt, tittel og utgiver

Egenskapen `dcat:endpointURL` angir endepunktet API-et er tilgjengelig på; den er obligatorisk. I tillegg er egenskapene `dcat:contactPoint`, `dct:title` og `dct:publisher` obligatorisk.
Her kan vi bruke gjenbruke noe av informasjonen for Datasettet, siden i dette tilfellet er det samme utgiver og samme kontaktpunkt for både datasett og API-et.
Dette må du undersøke om er tilfellet for datasettet du skal beskrive.

```text/turtle
<https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset> rdf:type dcat:Dataset ;
  # ...
  .

<https://data.digdir.no/datasets/ai_projects_norwegian_state_api> rdf:type dcat:DataService ;
  dcat:servesDataset <https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset> ;
  dcat:endpointURL <https://data.digdir.no/api/ai_projects_norwegian_state> ; # fiktiv URL, fungerer ikke
  dct:title "API for oversikt over KI-prosjekter i offentlig sektor"@nb ;
  dct:publisher <https://organization-catalogue.fellesdatakatalog.digdir.no/organizations/991825827> ;
  dcat:contactPoint [
    rdf:type vcard:Organization ;
    vcard:hasEmail "kunstigintelligens@digdir.no" ;
    vcard:fn "Kunstig Intelligens Digdir" ;
  ] ;
  .
```

### Lisens og format

Vi vil igjen si her at datasettet er tilgjengelig med Apache-2.0-lisens. I tillegg tilbyr det fiktive API-et vårt dataen i XML- og JSON-format.

```text/turtle
<https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset> rdf:type dcat:Dataset ;
  # ...
  .

<https://data.digdir.no/datasets/ai_projects_norwegian_state_api> rdf:type dcat:DataService ;
  dcat:servesDataset <https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset> ;
  # ...
  dct:license <http://publications.europa.eu/resource/authority/licence/APACHE_2_0> ;
  dct:format <http://publications.europa.eu/resource/authority/file-type/XML> ,
             <http://publications.europa.eu/resource/authority/file-type/JSON> ;
  .
```

### Kompett beskrivelse av datatjeneste

Hele beskrivelsen av Datatjenesten/API-et ser da slik ut:

```text/turtle
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix dcat: <http://www.w3.org/ns/dcat#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix vcard: <http://www.w3.org/2006/vcard/ns#> .

<https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset> rdf:type dcat:Dataset ;
  # ...
  .

<https://data.digdir.no/datasets/ai_projects_norwegian_state_api> rdf:type dcat:DataService ;
  dcat:servesDataset <https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset> ;
  dcat:endpointURL <https://data.digdir.no/api/ai_projects_norwegian_state> ; # fiktiv URL, fungerer ikke
  dct:title "API for oversikt over KI-prosjekter i offentlig sektor"@nb ;
  dct:publisher <https://organization-catalogue.fellesdatakatalog.digdir.no/organizations/991825827> ;
  dcat:contactPoint [
    rdf:type vcard:Organization ;
    vcard:hasEmail "kunstigintelligens@digdir.no" ;
    vcard:fn "Kunstig Intelligens Digdir" ;
  ] ;
  dct:license <http://publications.europa.eu/resource/authority/licence/APACHE_2_0> ;
  dct:format <http://publications.europa.eu/resource/authority/file-type/XML> ,
             <http://publications.europa.eu/resource/authority/file-type/JSON> ;
  .
```

### Knytte datasettet til en katalog

Helt til slutt må vi knytte datasettene vi har beskrevet til en katalog, katalogen er obligatorisk. Noen virksomheter har én felles datakatalog for alle beskrivelsene de sitter på, mens andre virksomheter vil ha flere kataloger.

I eksemplet her antar vi at Digdir har én datakatalog (`dcat:Catalog`) som inneholder alle datasettene Digdir har publisert informasjon om, og at URI-en til katalogen er `https://data.digdir.no/catalog/1` .

Den komplette beskrivelsen ser da slik ut:

```text/turtle
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix dcat: <http://www.w3.org/ns/dcat#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix vcard: <http://www.w3.org/2006/vcard/ns#> .

<https://data.digdir.no/catalog/1> a dcat:Catalog ;
  dcat:dataset <https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset> ;
  .

<https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset> a dcat:Dataset ;
    dct:title "Kunstig intelligens - oversikt over prosjekter i offentlig sektor"@nb ,
            "Kunstig intelligens - oversikt over prosjekt i offentleg sektor"@nn ,
            "Artificial intelligence - overview of projects in the public sector"@en ;
    dct:description "En oversikt over kunstig intelligens-prosjekter i offentlig sektor. Oversikten er ikke komplett."@nb ;
                    "Ei oversikt over kunstig intelligens-prosjekt i offentleg sektor. Oversikta er ikkje komplett"@nn ;
                    "An overview of artificial intelligence projects in the public sector. The overview is not complete."@en ;
    dct:publisher <https://organization-catalogue.fellesdatakatalog.digdir.no/organizations/991825827> ;
    dcat:contactPoint [
      rdf:type vcard:Organization ;
      vcard:hasEmail "kunstigintelligens@digdir.no" ;
      vcard:fn "Kunstig Intelligens Digdir" ;
    ] ;
    dct:keyword "kunstig intelligens"@nb , "kunstig intelligens"@nn , "artificial intelligence"@en,
                "offentlig sektor"@nb , "offentleg sektor"@nn , "public sector"@en ;
    dcat:theme <http://publications.europa.eu/resource/authority/data-theme/GOVE>,
               <http://eurovoc.europa.eu/3030> ;
    dct:spatial <http://publications.europa.eu/resource/authority/country/NOR> ;
    prov:wasGeneratedBy provno:collectingFromThirdparty ;
    dct:accessRights <http://publications.europa.eu/resource/authority/access-right/PUBLIC> ;
    foaf:page <https://data.norge.no/kunstig-intelligens> ;
    .

<https://data.digdir.no/datasets/ai_projects_norwegian_state_distribution> rdf:type dcat:Distribution ;
  dcat:accessURL <https://github.com/Informasjonsforvaltning/ai-project-service/blob/main/ai_projects_norwegian_state%20-%20Oversatt_v1.csv> ;
  dcat:downloadURL <https://raw.githubusercontent.com/Informasjonsforvaltning/ai-project-service/main/ai_projects_norwegian_state%20-%20Oversatt_v1.csv> ;
  dct:description "CSV-fil med oversikt over kunstig intelligens-prosjekter i offentlig sektor"@nb ;
  dct:issued "2023-02-23"^^xsd:date ;
  dct:license <http://publications.europa.eu/resource/authority/licence/APACHE_2_0> ;
  dct:format <http://publications.europa.eu/resource/authority/file-type/CSV> ;
  dct:language <http://publications.europa.eu/resource/authority/language/NOB> ;
  .

<https://data.digdir.no/datasets/ai_projects_norwegian_state_api> rdf:type dcat:DataService ;
  dcat:servesDataset <https://data.digdir.no/datasets/ai_projects_norwegian_state_dataset> ;
  dcat:endpointURL <https://data.digdir.no/api/ai_projects_norwegian_state> ; # fiktiv URL, fungerer ikke
  dct:title "API for oversikt over KI-prosjekter i offentlig sektor"@nb ;
  dct:publisher <https://organization-catalogue.fellesdatakatalog.digdir.no/organizations/991825827> ;
  dcat:contactPoint [
    rdf:type vcard:Organization ;
    vcard:hasEmail "kunstigintelligens@digdir.no" ;
    vcard:fn "Kunstig Intelligens Digdir" ;
  ] ;
  .
```

## Sette opp endepunkt som tjener beskrivelsen

Når vi nå har den fullstendige beskrivelsen må vi tilby den fra et endepunkt som er tilgjengelig. Endepunktet må serve filen som et gyldig RDF-format, f.eks. Turtle.

Vi laster opp eksempel-filen med beskrivelse av KI-oversikten til Github.com.

## Registrere endepunktet i administrasjonsløsningen for høsting (data.norge.no)

For at data.norge.no skal publisere beskrivelsen din må det vite hvor det skal hente beskrivelsen fra. Det kan du registrere i administrasjonsløsningen til data.norge.no (TODO:legg-til-lenke)

### Registrere endepunkt og fylle ut felter

- Registrere endepunkt i administrasjonsløsning for høsting
- Bilder, gjennomgang av skjema

## Starte høsting

Når vi har registrert endepunktet kan vi starte en høsting, slik at data.norge.no henter siste versjon av beskrivelsen din fra endepunktet.
