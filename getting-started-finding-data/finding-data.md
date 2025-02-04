---
info_en: Page about "Getting started - Finding data"
info_no: Side om "Komme i gang - finne data"
description: Skal gi overordnet informasjon om hvordan finne dataen og metadataen man søker, og de ulike søkene.
url: https://data.norge.no/getting-started/finding-data
---

# Finne data

Data.norge.no gir en omfattende oversikt over datasett, begreper, API-er, informasjonsmodeller, tjenester og hendelser i offentlig sektor, inkludert data med juridiske begrensninger som taushetsplikt eller personopplysninger. Hensikten med denne oversikten er å gjøre det lettere for deg å finne, forstå og ta i bruk data fra offentlig sektor. For å finne frem blant alle beskrivelsene, tilbyr Data.norge.no forskjellige måter å søke på. Dersom du ikke finner dataen du leter etter, kan du [registrere en etterspørsel](https://data.norge.no/requests).

## Søk

Data.norge.no tilbyr tre forskjellige måter å søke etter data på: Standard tekstsøk med filtrering, kunstig intelligens-søk og SPARQL-spørring.

### Kunstig intelligens-søk (KI-søk)

KI-søket bruker metadata fra Data.norge.no og hjelper deg med å finne datasett. Ved å bruke naturlig språk kan du søke fritt uten å måtte kjenne til spesifikke datasettnavn, fagtermer eller tekniske formater.
Prøv f.eks. "Hvilke områder i Norge er vernet?"

[Du kan lese teknisk informasjon om KI-søket på data.norge.no her](https://github.com/Informasjonsforvaltning/fdk-llm-search-service).

### Standard søk med filter

På [data.norge.no/search-all](data.norge.no/search-all) finner du et tekstsøk med muligheter for filtrering. Her kan du søke etter titler, beskrivelser og søkeord i databeskrivelsene. For å avgrense søket ditt, kan du bruke ulike filtre. Hvilke filtre som tilbys avhenger av ressurstype. Du velger ressurstype ved å bruke fanene under søkefeltet. Resultatet kan sorteres etter relevans eller publiseringsdato.

### SPARQL

[SPARQL-tjenesten](https://data.norge.no/sparql) er det kraftigste og mest fleksible verktøyet for å søke i katalogen. Dette er et verktøy hvor du kan utføre egne spørringer i SPARQL på RDF-grafene til data.norge.no. Her kan du spørre etter datasett, begreper, API-er og informasjonsmodeller. Du kan også gjøre spørringer direkte til [SPARQL-endepunktet for data.norge.no](https://sparql.fellesdatakatalog.digdir.no/).

#### Hva er SPARQL?

[SPARQL](https://www.w3.org/TR/rdf-sparql-query/) er et spørrespråk som brukes til å hente data lagret i RDF-format. RDF Resource Description Framework) er en standardmodell for å beskrive data og ressurser på semantisk web. [Du kan lese mer om RDF her](https://www.w3.org/RDF).

#### Eksempel på bruk av SPARQL

Få oversikt over hvilke egenskaper som finnes:

```sparql
PREFIX dcat: <http://www.w3.org/ns/dcat#>
SELECT *
WHERE {
	?dataset a dcat:Dataset.
    ?dataset ?prop ?value.
}
```

Deretter plukke og velge egenskaper:

```sparql
PREFIX dcat: <http://www.w3.org/ns/dcat#>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX dct: <http://purl.org/dc/terms/>
SELECT *
WHERE {​​​​​​​​​​​​​​
 ?dataset a dcat:Dataset .
 ?dataset dct:title ?title.
 ?dataset rdf:type ?type.
# Velg nye egenskaper ved: ?dataset <ønsket egenskap> ?egenskapsverdi
}
```

[Her finner du flere eksempler og informasjon om hvordan du skriver SPARQL-spørringer](https://www.w3.org/TR/rdf-sparql-query/#basicpatterns).

## Finner du ikke det du leter etter?

Vet du ikke om data du ser etter finnes eller er det data du trenger som ikke er delt ennå? Hvis datasettet ikke er beskrevet på Data.norge.no eller på dataeiers nettsider, bør du gå i dialog med de som tilbyr dem og oppfordre dem til å dele. Du kan bruke Digdirs tjenester til dette, ved å spørre [Datajegeren](https://data.norge.no/forms/nb/data-hunter) eller etterspørre datasett og API-er i [Datalandsbyen](https://datalandsbyen.norge.no).

### Datajegeren: Finn og få tilgang til offentlige datasett

Datajegeren er en tjeneste som hjelper deg med å finne og få tilgang til datasett fra offentlig sektor. Selv om mange datasett er tilgjengelige via data.norge.no, er ikke katalogen komplett.

[Du kan be Datajegeren om hjelp via et enkelt kontaktskjema](https://data.norge.no/forms/nb/data-hunter). Her kan du beskrive hva du leter etter. Noen felt er obligatoriske og noen kan du velge å bruke for å spesifisere forespørselen din. Når skjemaet sendes inn, går det direkte til ansatte i Digitaliseringsdirektoratet som undersøker hvilken etat som eier dataene og tar seg av den nødvendige kontakten for å skaffe dem.

### Datalandsbyen: Etterspørre datasett og API-er

Datalandsbyen er et nettforum dedikert til dialog mellom tilbydere og konsumenter av data. Her kan du etterlyse datasett og API-er du ønsker tilgang til eller har spørsmål om. Du kan også be om utvidelser av eksisterende datasett og API-er, for eksempel mer tilgjengelig data eller endringer i API-funksjonalitet. Besøk brukerforumet [Datalandsbyen](https://datalandsbyen.norge.no/category/6/ettersp%C3%B8r-datasett-og-api-er) for å legge inn din etterspørsel. Se [veileder for hvordan etterspørre data i Datalandsbyen](https://datalandsbyen.norge.no/topic/56/ettersp%C3%B8rr-data-og-api).

[Data.norge.no tilbyr en oversikt over alle publiserte etterspørsler i Datalandsbyen](https://data.norge.no/requests).

#### Om datalandsbyen

Hensikten med nettforumet [Datalandsbyen](https://datalandsbyen.norge.no) er å fremme åpen og datadreven innovasjon gjennom samarbeid, dialog og kunnskapsdeling. Dette forumet fungerer som en felles møteplass for alle som er interesserte i å lære mer om dataforvaltning og ønsker å snakke med både datakonsumenter og datatilbydere.

I Datalandsbyen kan ulike brukergrupper inspirere hverandre med nyttige tips og spørsmål, diskutere bruken av data og API-er, samt etterlyse spesifikke datasett de ønsker tilgang til. Forumet gir også mulighet til å vise eksempler på hvordan data benyttes i tjenester og applikasjoner, samt å dele relevante arrangementer.

Datalandsbyen er åpen for alle, men for å delta aktivt må man registrere seg. Målet er å fremme verdiskapende bruk av data for samfunnet gjennom økt kunnskap, åpenhet og innovasjon.

## Hvem har ansvar for hva på data.norge.no

### Datatilbyderne

Virksomhetene som eier dataene som er beskrevet på data.norge.no har ansvar for selve innholdet i beskrivelsene og for at dataene du får tilgang til stemmer overens med beskrivelsene.

Hvis du finner noe feil med beskrivelsene eller tilgangen til dataene, kan du kontakte virksomheten som eier beskrivelsen direkte. Kontaktinformasjon vil som regel være knyttet til beskrivelsen. Hvis du er logget inn i Datalandsbyen, kan du også legge igjen en kommentar på selve beskrivelsen på data.norge.no. Denne kommentaren vil vises både på data.norge.no og i Datalandsbyen. Slike kommentarer og påfølgende diskusjon kan være nyttig for andre brukere som trenger de samme dataene som deg.

### Digitaliseringsdirektoratet

Digitaliseringsdirektoratet har ansvar for informasjon om når beskrivelser ble publisert på data.norge.no, metadatakvalitet, Datajegeren, KI-oversikt, informasjonssider og at de tekniske løsningene på data.norge.no og Datalandsbyen fungerer som de skal. Digitaliseringsdirektoratet følger også opp kommentarer i Datalandsbyen og purrer på virksomheter som ikke svarer opp kommentarer knyttet til beskrivelser i katalogen.

#

[Du kan lese mer om å finne og vurdere data på Digitaliseringsdirektoratets nettsider.](https://www.digdir.no/datadeling/finne-og-vurdere-data/2256#hvor_kan_du_finne_dataene)
