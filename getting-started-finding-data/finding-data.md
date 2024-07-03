---
info_en: Page about "Getting started - Finding data"
info_no: Side om "Komme i gang - finne data"
description: Skal gi overordnet informasjon om hvordan finne dataen og metadataen man søker, og de ulike søkene.
url: https://data.norge.no/getting-started/finding-data
---

# Finne data

Felles datakatalog (FDK) gir en omfattende oversikt over datasett, begreper, API-er, informasjonsmodeller, tjenester og hendelser i offentlig sektor, inkludert data med juridiske begrensninger som taushetsplikt eller personopplysninger. For å finne frem blant alle beskrivelsene, tilbyr FDK forskjellige måter å søke på. Dersom du ikke finner dataen du leter etter, kan du etterspørre dem. Det angis om dataene er en autoritativ kilde, og det vises om dataene har "allmenn tilgang" eller om det kreves hjemmel eller samtykke for å ta de i bruk.

## Søk

Felles datakatalog tilbyr tre forskjellige måter å søke etter data på: standard tekstsøk med filtrering, KI-søk og SPARQL-spørring.

### Kunstig intelligens-søk

KI-søket bruker metadata fra data.norge.no og gjør det enkelt å finne datasett. Ved å bruke naturlig språk kan du søke fritt uten å måtte kjenne til spesifikke datasettnavn, fagtermer eller tekniske formater.
Prøv f.eks. "Hvilke områder i Norge er vernet?"
Mer teknisk informasjon om KI-søket finner du [her](https://github.com/Informasjonsforvaltning/fdk-llm-search-service).

### Standard søk med filter

På data.norge.no/search-all finner du et tekstsøk med muligheter for filtrering. Her kan du søke etter titler, beskrivelser og nøkkelord i databeskrivelsene. For å finne de dataene du leter etter, kan du bruke ulike filtre, inkludert filtrering etter ressurstype. Du velger ressurstype ved å bruke fanene under søkefeltet.

### SPARQL

[SPARQL-tjenesten](https://data.norge.no/sparql) er det mest fleksible og kraftigste verktøyet for å søke i katalogen. Dette er et verktøy hvor du kan utføre egne spørringer i SPARQL på RDF-grafene til Felles datakatalog. Her kan du spørre etter datasett, begreper, API-er og informasjonsmodeller. Du kan også gjøre spørringer direkte til endepunktet, det finner du her: https://sparql.fellesdatakatalog.digdir.no/.

#### Hva er SPARQL?

[SPARQL](https://www.w3.org/TR/rdf-sparql-query/) er et spørrespråk som brukes til å hente data lagret i RDF-format (Resource Description Framework), som er en standardmodell for å beskrive data og ressurser på semantisk web. Les mer om RDF her(lenke).

#### Eksempel på bruk av SPARQL

Kopiert fra developers handbook, vet ikke om det er et eksempel som passer bedre

Få oversikt over hvilke egenskaper som finnes:

```sparql
PREFIX dcat: <http://www.w3.org/ns/dcat#>
SELECT *
WHERE {
	?dataset a dcat:Dataset .
    ?dataset ?prop ?value.
}
```

Deretter plukke og velge egenskaper:

```sparql
PREFIX dcat: <http://www.w3.org/ns/dcat#>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX purl: <http://purl.org/dc/terms/>
SELECT *
WHERE {​​​​​​​​​​​​​​
 ?dataset a dcat:Dataset .
 ?dataset purl:title ?title.
 ?dataset rdf:type ?type.
# Velg nye egenskaper ved: ?dataset <ønsket egenskap> ?egenskapsverdi
}
```

For flere eksempler og informasjon om hvordan du skriver SPARQL-spørringer, kan du lese [her](https://www.w3.org/TR/rdf-sparql-query/#basicpatterns).

## Finner du ikke det du leter etter?

Vet du ikke om data du ser etter finnes? Er det data du trenger som ikke er delt enda? Hvis datasettet ikke er beskrevet i felles datakatalog eller på tilbyders nettsider, bør du gå i dialog med de som tilbyr dem.

### Datalandsbyen: Etterspørre datasett og API-er

Datalandsbyen er et nettforum dedikert til dialog mellom tilbydere og konsumenter av data. Her kan du etterlyse datasett og API-er du ønsker tilgang til eller har spørsmål om. Du kan også be om utvidelser av eksisterende datasett og API-er, for eksempel mer tilgjengelig data eller endringer i API-funksjonalitet. Besøk brukerforumet [Datalandsbyen](https://datalandsbyen.norge.no/category/6/ettersp%C3%B8r-datasett-og-api-er) for å legge inn din etterspørsel. En veiledning om hvordan du går frem finner du [her](https://datalandsbyen.norge.no/topic/56/ettersp%C3%B8rr-data-og-api).

FDK tilbyr en oversikt over alle [publiserte etterspørsler i Datalandsbyen](https://data.norge.no/requests).

#### Om datalandsbyen

Digdir, Datafabrikken og Statens vegvesen har lansert nettforumet [Datalandsbyen](https://datalandsbyen.norge.no) for å fremme åpen og datadreven innovasjon gjennom samarbeid, dialog og kunnskapsdeling. Dette forumet fungerer som en felles møteplass for alle interesserte i å lære mer om dataforvaltning og ønsker å engasjere seg med både datakonsumenter og datatilbydere.

I Datalandsbyen kan ulike brukergrupper inspirere hverandre med nyttige tips og spørsmål, diskutere bruken av data og API-er, samt etterlyse spesifikke datasett de ønsker tilgang til. Forumet gir også mulighet til å vise eksempler på hvordan data benyttes i tjenester og applikasjoner, samt å dele relevante arrangementer.

Datalandsbyen er åpen for alle, men for å delta aktivt må man registrere seg. Målet er å fremme verdiskapende bruk av data for samfunnet gjennom økt kunnskap, åpenhet og innovasjon.

### Datajegeren: Finn og få tilgang til offentlige datasett

Datajegeren er en tjeneste som hjelper deg med å finne og få tilgang til datasett fra offentlig sektor. Selv om mange datasett er tilgjengelige via Felles Datakatalog, er den ikke komplett. Datajegeren trer inn for å hjelpe bedrifter med å finne og få tilgang til spesifikke datasett.

Ved å besøke tjenesten får du tilgang til et enkelt [kontaktskjema](https://data.norge.no/forms/nb/data-hunter). Her kan du beskrive hva du leter etter, med noen felt som er obligatoriske og noen for å spesifisere forespørselen din. Når skjemaet sendes, går det direkte til ansatte i Digitaliseringsdirektoratet som undersøker hvilken etat som eier dataene og tar seg av den nødvendige kontakten for å skaffe dem.

## Hvem har ansvar for hva på data.norge.no

[Skrive noe om hvilken type informasjon virksomhetene er ansvarlig for, og hvilken informasjon Digdir ved data.norge.no er ansvarlig for].

I Felles datakatalog - data.norge.no ligger de fleste datasett som er tilgjengelige fra offentlige virksomheter. I denne katalogen skal du finne alt du trenger for å oppdage, vurdere og ta i bruk data.

Usikker på denne delen, dette står allerede i "om fdk" 👇

Innholdet i Felles datakatalog leveres av ulike offentlige og private virksomheter. Digitaliseringsdirektoratet er ansvarlig for drift og utvikling av nettstedet.

#

Les mer om å [finne og vurdere data](https://www.digdir.no/datadeling/finne-og-vurdere-data/2256#hvor_kan_du_finne_dataene) på Digitaliseringsdirektoratets nettsider.
