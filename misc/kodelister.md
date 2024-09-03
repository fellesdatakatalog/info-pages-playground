# Kodelister og hvordan bruke dem

For flere av feltene i [DCAT-AP-NO](https://data.norge.no/specification/dcat-ap-no) må du peke til en kode fra et kontrollert vokabular. Når du skal angi tema for et datasett `dcat:theme` må du for eksempel velge en kode fra EU sitt vokabular _Data Theme_. Kodene er organisert i lister eller hierarkiske strukturer, og er navngitt med en URI som en hvilken som helst RDF-ressurs.

> **Tips:**
> Standarden gir en fullstendig oversikt over hvilke kontrollerte vokabularer som [**skal** brukes](https://data.norge.no/specification/dcat-ap-no#Kontrollerte-vokabularer-som-skal-brukes), og hvilke som [**bør** og **kan** brukes](https://data.norge.no/specification/dcat-ap-no#Kontrollerte-vokabularer-som-b%C3%B8r-og-kan-brukes).

## Hvordan angi tema

Datasett og Datatjeneste bruker egenskapen `dcat:theme`.

For datasett **skal** man angi en kode fra et av EU sine vokubular, _Data Theme_ eller _EuroVoc_.
Man **bør** også angi kode fra LOS.

### Data Theme

| Informasjon om DataTheme                                                                                                                             |  Oversikt over alle kodene                                                                                                                                    | URI du skal bruke i beskrivelsen din                               |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| [Gå til op.europa.eu](https://op.europa.eu/en/web/eu-vocabularies/dataset/-/resource?uri=http://publications.europa.eu/resource/dataset/data-theme)  |  [Gå til op.europa.eu](https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/data-theme) | `http://publications.europa.eu/resource/authority/data-theme/XXXX` |

Dette er en relativt liten kodeliste som inneholder noen svært generelle temaer.

**Eksempler på noen koder fra Data Theme**

| Kode | Forklaring                     | URI til bruk i beskrivelse                                         |
| ---- | ------------------------------ | ------------------------------------------------------------------ |
| ECON | *Economy and finance*          | `http://publications.europa.eu/resource/authority/data-theme/ECON` |
| EDUC | _Education, culture and sport_ | `http://publications.europa.eu/resource/authority/data-theme/EDUC` |
| TECH | *Science and technology*       | `http://publications.europa.eu/resource/authority/data-theme/TECH` |

#### Eksempler på bruk

```turtle
@prefix rdf:    <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix dct:    <http://purl.org/dc/terms/> .
@prefix dcat:   <http://www.w3.org/ns/dcat#> .

# Datasett som handler om økonomi og finans
<https://example.org/datasett1> rdf:type dcat:Dataset ;
    dcat:theme <http://publications.europa.eu/resource/authority/data-theme/ECON> .

# Datasett som handler om utdanning
<https://example.org/datasett2> rdf:type dcat:Dataset ;
    dcat:theme <http://publications.europa.eu/resource/authority/data-theme/EDUC> .

# Datasett som handler om utdanning og teknologi
<https://example.org/datasett3> rdf:type dcat:Dataset ;
    dcat:theme  <http://publications.europa.eu/resource/authority/data-theme/EDUC> ,
                <http://publications.europa.eu/resource/authority/data-theme/TECH> .
```

### EuroVoc

EuroVoc er en stor Thesauri (et hierarki) med svært mange koder organisert i en hierarkisk struktur.

| Informasjon om EuroVoc                                                                                                                            |  Oversikt over alle kodene                                                                                                        | URI du skal bruke i beskrivelsen din |
| ------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| [Gå til op.europa.eu](https://op.europa.eu/en/web/eu-vocabularies/dataset/-/resource?uri=http://publications.europa.eu/resource/dataset/eurovoc)  |  [Gå til op.europa.eu](https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://eurovoc.europa.eu/100141) | `http://eurovoc.europa.eu/XXXX`      |

**Eksempler på noen koder fra EuroVoc**

| Kode       | Forklaring                 | URI til bruk i beskrivelse            |
| ---------- | -------------------------- | ------------------------------------- |
| 4522       | *Maritime transport*       | `http://eurovoc.europa.eu/4522`       |
| 2312       | _Energy supply_            | `http://eurovoc.europa.eu/2312`       |
| 854        | *Equivalence of diplomas*  | `http://eurovoc.europa.eu/854`        |
| c_61b6fae1 | *urban statistics*         | `http://eurovoc.europa.eu/c_61b6fae1` |

#### Eksempler på bruk

For informasjon om koden "deep-sea fishing" se [denne siden (op.europa.eu)](https://op.europa.eu/en/web/eu-vocabularies/concept/-/resource?uri=http://eurovoc.europa.eu/2306&lang=en).

```turtle
@prefix rdf:    <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix dct:    <http://purl.org/dc/terms/> .
@prefix dcat:   <http://www.w3.org/ns/dcat#> .

# Datasett som handler om dypvannsfiske
<https://example.org/datasett1> rdf:type dcat:Dataset ;
    dcat:theme <http://eurovoc.europa.eu/2306> .
```

### LOS

[Dokumentasjon for LOS](https://data.norge.no/docs/los-dokumentasjon)

## Spatial

## Lisens

## Format

## Språk
