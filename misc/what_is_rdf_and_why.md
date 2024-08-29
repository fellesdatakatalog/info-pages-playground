### Resource Description Framework (RDF) og lenkede data

- "Alt" består av navn (URI-er) eller verdier ("Literals")
- En URI ("Uniform Resource Identifier") er et navn som peker til en ressurs.
  - URI-en er en global, unik identifikator.
  - _Kan_ peke til en faktisk ressurs på nettet, men må ikke.
- Byggeklossen i en RDF-graf: subjekt, predikat, objekt
  - _Trippel_
  - **Fakta** eller **utsagn**
- (Forenklet) huskeregel:
  - Subjekt: URI
  - Predikat: URI
  - Objekt: URI eller verdi.

Med disse byggeklossene kan vi lage rettede grafer som består av ting og relasjonene mellom tingene.

![Rettet graf](./content/rdf/graph_example1.svg)

### Hvorfor RDF?

- Maskinlesbart.
- Samhandlingsevne/interoperabilitet:
  - Har et globalt navnerom: betyr at vi kan snakke om de samme tingene på tvers av systemer og domener.
  - Ulike datasett kan enklere knyttes sammen (lenkede data).
  - Tilrettelegger for gjenbruk av vokabularer og egenskaper på tvers av systemer og løsninger.
- Semantikken følger med dataen når man bruker definerte egenskaper; dataen blir selvforklarende.
- Håndterer kompleks data som er vanskelig å definere i tabellform.
- Distribuerte spørringer.
- En stor verktøykasse er tilgjengelig (for modellering, validering, spørringer, distribuert data, med mer).

Viktig antakelse: åpent verdenssyn (Open world assumption).

Se hva W3C selv [skriver om bruksområder for RDF](https://www.w3.org/TR/rdf11-primer/#section-use-cases).

#### RDF-serialiseringer/syntakser

Det fins flere ulike måter å uttrykke RDF-grafer. I tabellen under har vi listet noen av de vanligste syntaksene for å serialisere RDF. Du trenger ikke kunne alle, bare å kjenne til at de fins.

RDF-verktøy og biblioteker kan lese til og skrive fra en eller flere av disse syntaksene. De facto standard er RDF/XML, men Turtle støttes også av de aller fleste verktøy.

| Navn      | Mediatype               | File extension |
| --------- | ----------------------- | -------------- |
| Turtle    | `text/turtle`           | `.ttl`         |
| RDF/XML   | `application/rdf+xml`   | `.rdf`         |
| JSON-LD   | `application/ld+json`   | `.jsonld`      |
| N-Triples | `application/n-triples` | `.nt`          |
| N-Quads   | `application/n-quads`   | `.nq`          |
| TriG      | `application/trig`      | `.trig`        |
| Notation3 | `text/n3;charset=utf-8` | `.n3`          |

### Modellere Ada Lovelace

AdaLovelace type Person

AdaLovelace navn Ada Lovelace

AdaLovelace født 10.12.1815

AdaLovelace kjenner CharlesBabbage

AdaLovelace interesse Programmering

![Ada Lovelace](./content/rdf/ada_lovelace_graph.svg)

### Turtle - en RDF-syntaks

- En URI skrives med "<" og ">", slik: `<https://example.org>`
- Tekstverdier skrives med anførselstegn: `"en tekst"`
- Man kan angi typen til en verdi, f.eks. heltall: `"1"^^<http://www.w3.org/2001/XMLSchema#integer>`, eller dato: `"2024-06-05"^^<http://www.w3.org/2001/XMLSchema#date>`
- Du kan angi språket til teksten: `"An english text"@en` eller `"En tekst på bokmål"@nb`.

Vi bruker ressurser som allerede er definert av andre, f.eks. RDF, Schema.org eller Friend of a friend (FOAF). Vi kan da uttrykke grafen som beskriver Ada Lovelace i RDF:

```turtle
<https://example.org/people/adaLovelace>   <http://www.w3.org/1999/02/22-rdf-syntax-ns#type>   <http://xmlns.com/foaf/0.1/Person> .
<https://example.org/people/adaLovelace>   <http://xmlns.com/foaf/0.1/name>                    "Ada Lovelace" .
<https://example.org/people/adaLovelace>   <https://schema.org/birthDate>                      "1815-12-10"^^<http://www.w3.org/2001/XMLSchema#date> .
<https://example.org/people/adaLovelace>   <https://schema.org/knows>                          <https://example.org/people/charlesBabbage> .
<https://example.org/people/adaLovelace>   <https://schema.org/knowsAbout>                     "Programmering"@nb .
```

#### Prefikser/navnerom

Med prefikser (forkortelser) kan vi erstatte URL-ene med prefiksen vi har definert.
F.eks. kan vi skrive `foaf` i stedet for `<http://xmlns.com/foaf/0.1/>`.

Og om vi vil bruke egenskapen "navn", `<http://xmlns.com/foaf/0.1/name>` trenger vi kun skrive `foaf:name`.

Kjente og ofte brukte navnerom (+ noen vi trenger til datasettbeskrivelser):

```turtle
@prefix rdf:    <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix rdfs:   <http://www.w3.org/2000/01/rdf-schema#> .
@prefix foaf:   <http://xmlns.com/foaf/0.1/> .
@prefix xsd:    <http://www.w3.org/2001/XMLSchema#> .
@prefix dct:    <http://purl.org/dc/terms/> .
@prefix owl:    <http://www.w3.org/2002/07/owl#> .
@prefix schema: <https://schema.org/> .

@prefix cv:     <http://data.europa.eu/m8g/> .
@prefix dcat:   <http://www.w3.org/ns/dcat#> .
@prefix dcatap: <http://data.europa.eu/r5r> .
@prefix dcatno: <https://data.norge.no/vocabulary/dcatno#> .

# Egendefinert prefiks for eksemplene her
@prefix people: <https://example.org/people/> .
```

#### ...forenklet beskrivelse

Med dette kan vi forenkle beskrivelsen av Ada Lovelace

```turtle
@prefix rdf:    <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix foaf:   <http://xmlns.com/foaf/0.1/> .
@prefix xsd:    <http://www.w3.org/2001/XMLSchema#> .
@prefix schema: <https://schema.org/> .

@prefix people: <https://example.org/people/> .


people:adaLovelace rdf:type               foaf:Person .
people:adaLovelace foaf:name              "Ada Lovelace" .
people:adaLovelace schema:birthDate       "1815-12-10"^^xsd:date .
people:adaLovelace schema:knows           people:charlesBabbage .
people:adaLovelace schema:knowsAbout      "Programmering"@nb .
```

Fortsatt på formen subjekt, predikat, objekt

#### ... enda mer forenklet

Når vi gjentar subjektet kan det skrives om til

```turtle
people:adaLovelace    rdf:type               foaf:Person ;
                      foaf:name              "Ada Lovelace" ;
                      schema:birthDate       "1815-12-10"^^xsd:date ;
                      schema:knows           people:charlesBabbage ;
                      schema:knowsAbout      "Programmering"@nb .
```

Hvert utsagn som gjenbruker subjektet avsluttes med `;`. Vi avslutter med `.` som vanlig.

#### Med flere verdier på samme predikat

```turtle
people:adaLovelace  rdf:type  foaf:Person ;
          # ... kommentert vekk
          schema:knowsAbout   "litteratur"@nb ;
          schema:knowsAbout   "matematikk"@nb ;
          schema:knowsAbout   "programmering"@nb .
```

Når vi gjentar [ subjekt predikat ] kan vi skrive det om til

```turtle
people:adaLovelace   rdf:type        foaf:Person ;
          # ... kommentert vekk
          schema:knowsAbout "musikk"@nb , "matematikk"@nb , "programmering"@nb .
```

Hvert utsagn som gjenbruk subjekt+predikat avsluttes med `,`.

### DCAT-AP (Data Catalog Vocabulary – Application Profile)

Spesifikasjon for hvordan beskrive datasett og API-er.

Gjeldende versjon: https://data.norge.no/specification/dcat-ap-no

- Forteller hvilke ting som _må_, _bør_ og _kan_ beskrives.
- Viser hvilke etablerte vokabularer og kodelister som skal brukes.
- Angir multiplisitet for feltene (0..1, 1..1, 1..n)

### Datasettkatalogen: dcat:Catalog

En katalog er en samling av datasett. I de fleste av oppgavene under har vi for enkelhetsskyld utelatt `dcat:Catalog`, men for å lage en fullstendig beskrivelse som kan høstes til https://data.norge.no må du knytte alle datasettene til en katalog:

```turtle
@prefix dcat: <http://www.w3.org/ns/dcat#> .

<https://data.digdir.no/catalog/workshop-katalog> a dcat:Catalog ;
    # ...
    dcat:dataset <https://data.digdir.no/dataset/workshop-datasett1> ,
                 <https://data.digdir.no/dataset/workshop-datasett2> ;
    .

<https://data.digdir.no/dataset/workshop-datasett1> a dcat:Dataset ;
    # ...
    .

<https://data.digdir.no/dataset/workshop-datasett2> a dcat:Dataset ;
    # ...
    .
```
