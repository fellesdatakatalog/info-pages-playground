---
info_en: Page about "Getting started - Creating descriptions"
info_no: Side om "Komme i gang - beskrive data/lage beskrivelser"
description: Skal gi overordnet informasjon om hvordan lage beskrivelser
url: https://data.norge.no/getting-started/describing-data
---

# Beskrive data

1. [Du lager beskrivelsen selv i RDF-format](#1-lage-beskrivelserrdf-grafer-selv)
2. [Du bruker registreringsløsningen til Data.norge.no](#2-registreringsløsning)

## Forarbeid: Rammeverk for informasjonsforvaltning og Orden i eget hus

Uavhengig av hvilke metode du går for bør virksomheten få oversikt over hvilke data den sitter på. Digdir har laget en egen veileder, [Orden i eget hus](https://www.digdir.no/informasjonsforvaltning/veileder-orden-i-eget-hus/2716), for hvordan få til dette.

## Spesifikasjoner/standarder

Data.norge.no baserer seg på flere spesifikasjoner og standarder:

- Datasett, datatjenester og datakataloger: [DCAT-AP-NO](https://data.norge.no/specification/dcat-ap-no)
- Begrep: [SKOS-AP-NO](https://data.norge.no/specification/skos-ap-no-begrep)
- Informasjonsmodeller: [ModellDCAT-AP-NO](https://data.norge.no/specification/modelldcat-ap-no)
- Tjenester og hendelser: [CPSV-AP-NO](https://data.norge.no/specification/cpsv-ap-no)

Beskrivelsene som lages må være i et RDF-format og i henhold til spesifikasjonene.
Registreringsløsningen på Data.norge.no genererer RDF-grafer/beskrivelser i henhold til spesifikasjonen, men løsningen støtter ikke alle feltene som fins i spesifikasjonene.

## 1. Lage beskrivelser/RDF-grafer selv

Bruk disse guidene for å lære mer om hvordan lage datasettbeskrivelser:

- [Veileder for beskrivelse av datasett, datatjenester og datakataloger](https://informasjonsforvaltning.github.io/veileder-beskrivelse-av-datasett/#beskrivelse-av-datasett)
- [Veileder for orden i eget hus - Steg 5: Beskrive](https://www.digdir.no/informasjonsforvaltning/steg-5-beskrive/2724)
- [Kursmateriell til workshop i RDF og datasettbeskrivelser](https://github.com/fellesdatakatalog/sikt-workshop/blob/main/ressurshefte/ressurshefte.md)

For de andre type ressursene (begrep, informasjonsmodeller, tjenester og hendelser) fins det eksempler på beskrivelser på [Data.norge.no sitt "Showroom"](https://data.norge.no/showroom/overview). Man kan også støtte seg på den aktuelle spesifikasjonen og eksemplene i den. De fleste av eksemplene er skrevet i RDF-formatet kalt Turtle og har overføringsverdi til de andre typene.

Flere relevante ressurser er listet opp nederst på denne siden.

### Støttede RDF-formater

Når du lager beskrivelsene selv må du gjøre det i et RDF-format som støttes av Data.norge.no:

- [Turtle](https://www.w3.org/TR/turtle/)
- [RDF/XML](https://www.w3.org/TR/rdf-syntax-grammar/)
- [RDF/JSON](https://www.w3.org/TR/rdf-json/)
- [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [N-Triples](https://www.w3.org/TR/n-triples/)
- ([Notation3/N3](https://www.w3.org/TeamSubmission/n3/) som synonym for Turtle)

### Validering av beskrivelser

Når du har laget en beskrivelse kan du validere den med [data.norge.no sin validator](https://data.norge.no/validator), som gir beskjed om eventuelle feil og mangler i beskrivelsen.

Du kan publisere en beskrivelse som har korrekt syntaks men innholdsmessige mangler i henhold til spesifikasjonen. Den vil bare vises som mangelfull på nettsidene til Data.norge.no. En RDF-graf som derimot inneholder syntaktiske feil vil feile ved høsting og ikke vises.

### Viktig å tenke på med URI-er og ved navngivning av ressurser

Ressurser som beskrives i RDF navngis ved hjelp av en unik, global identifikator, en såkalt URI ("Uniform Resource Identifier"). URI-er skal være unike og varige, og ideelt sett peke til faktiske nettressurser. Mer om utforming av URI-er:

- [Peikarar til offentlege ressursar på nett (Digdir)](https://www.digdir.no/standarder/peikarar-til-offentlege-ressursar-pa-nett/1492)
- [10 Rules for Persistent URIs (Interoperable Europe)](https://joinup.ec.europa.eu/collection/semic-support-centre/document/10-rules-persistent-uris)
- [Cool URIs for the Semantic Web (W3C)](https://www.w3.org/TR/cooluris/#semweb)

## 2. Registreringsløsning

For å registrere beskrivelser i Data.norge.no sin [registreringsløsning](https://registrering.fellesdatakatalog.digdir.no) må du

- være logget inn via ID-porten, og
- ha de riktige tilgangene (minimum «Felles datakatalog - alle kataloger - skrivetilgang»).

Velg deretter den ressurstypen du ønsker å beskrive, og opprett en ny beskrivelse.

Du kan velge om du vil publisere beskrivelsen til Data.norge.no, eller beholde den som utkast for videre arbeid. Publiserte endringer høstes ca. en gang i timen til Data.norge.no.

## Når du bør velge hvilken fremgangsmåte?

Dette fins det ikke et endelig svar på, men vi kan gi noen grunner til å velge det ene fremfor det andre.

### Grunner til å lage og forvalte beskrivelsene selv:

- Virksomheten er stor og forvaltningen av beskrivelsene er delegert ut til flere enkelt-team/enkeltpersoner.
- Generering av RDF-grafene/beskrivelsene er del av et automatisert løp.
- Det er mange som gjør hyppige endringer på beskrivelsene.
- Beskrivelsene skal tilgjengeliggjøres for flere enn bare publisering til Data.norge.no.
- Dere trenger å bruke felter i spesifikasjonene som ikke er støttet i registreringsløsningen.
- Metadataen kan forvaltes nærmere der selve dataen befinner seg, noe som senker terskelen for å holde den oppdatert og korrekt.

### Grunner til å velge registreringsløsningen:

- Virksomheten er liten og sitter på lite data.
- Virksomheten har ikke anledning til å sette opp endepunkt Data.norge.no kan høste fra.
- De ansvarlige i virksomheten ønsker en lavterskel måte å lage beskrivelser uten å sette seg inn i RDF.

## Ressurser

- [Showroom på data.norge.no](https://data.norge.no/showroom/overview) med eksempler på beskrivelser og sammenhengene mellom dem.
- [Mal for en datasettbeskrivelse i Turtle-format (Data.norge.no på Github)](https://github.com/fellesdatakatalog/sikt-workshop/blob/main/example-template.ttl).
- [Materiell til workshop om RDF og datasettbeskrivelser](https://github.com/fellesdatakatalog/sikt-workshop/blob/860e9b5b3d1596c2e97496d535056fc61115a4e5/ressurshefte/ressurshefte.md)
- [Eksempel på datasettbeskrivelse i Turtle (Data.norge.no på Github)](https://github.com/Informasjonsforvaltning/dcat-ap-no/blob/4d09617568f0f353b336ddd966b2228dc35f084e/examples/test.ttl)
- [Veileder for Orden i eget hus](https://www.digdir.no/informasjonsforvaltning/veileder-orden-i-eget-hus/2716)
- [DCAT-AP 3](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#DataService) fra EU som DCAT-AP-NO er basert på.
- [DCAT 3](https://www.w3.org/TR/vocab-dcat-3/) fra W3C som DCAT-AP er basert på.
- [Online trainings (SEMIC Support Centre)](https://joinup.ec.europa.eu/collection/semic-support-centre/online-trainings), kurs i vokabularene og spesifikasjonene fra EU.

## Verktøy Data.norge.no tilbyr

Data.norge.no har flere åpne biblioteker og verktøy som kan hjelpe i arbeidet med å lage beskrivelser.

Kommer du over feil eller mangler i disse, opprett gjerne et issue i repoet eller send oss en e-post på <fellesdatakatalog@digdir.no>.

- [datacatalogtordf](https://github.com/Informasjonsforvaltning/datacatalogtordf): Python-bibliotek som mapper datakataloger til en RDF-graf i henhold til DCAT-AP-NO.
- [concepttordf](https://github.com/Informasjonsforvaltning/concepttordf): Python-bibliotek som mapper begrepskataloger til en RDF-graf i henhold til SKOS-AP-NO.
- [modelldcatnotordf](https://github.com/Informasjonsforvaltning/modelldcatnotordf): Python-bibliotek som mapper informasjonsmodellkataloger til RDF-graf i henhold til ModellDCAT-AP-NO.
- [servicecatalogtordf](https://github.com/Informasjonsforvaltning/servicecatalogtordf): Python-bibliotek som mapper tjeneste- og/eller hendelseskataloger til en RDF-graf i henhold til CPSV-AP-NO.
- [oastodcat](https://github.com/Informasjonsforvaltning/oastodcat): Python-bibliotek som transformerer en OpenAPI-spesifikasjon til instans(er) av dcat:DataService (DCAT-AP-NO).
- [jsonschematordf](https://github.com/Informasjonsforvaltning/jsonschematordf): Python-bibliotek som mapper fra JSON Schema til en RDF-graf i henhold til ModellDCAT-AP-NO.
- [Valideringsverktøy](https://data.norge.no/validator): Validerer datasettbeskrivelser (DCAT-AP-NO), begrepsbeskrivelser (SKOS-AP-NO) og tjeneste- og hendelsesbeskrivelser (CPSV-AP-NO) i RDF-format.
- [SPARQL-brukergrensesnitt](https://data.norge.no/sparql): Verktøy som lar deg gjøre SPARQL-spørringer på innholdet i Data.norge.no.
