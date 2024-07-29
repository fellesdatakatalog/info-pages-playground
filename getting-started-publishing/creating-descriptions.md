---
info_en: Page about "Getting started - Creating descriptions"
info_no: Side om "Komme i gang - beskrive data/lage beskrivelser"
description: Skal gi overordnet informasjon om hvordan lage beskrivelser
url: https://data.norge.no/getting-started/publishing/describing-data
---

# Beskrive data

I hovedsak er det to måter å lage databeskrivelser som kan publiseres til data.norge.no:

1. Du lager beskrivelsen selv i RDF-format og tilgjengeliggjør dem på nett.
2. Du bruker registreringsløsningen til data.norge.no.

## Forarbeid: Orden i eget hus og Rammeverk for informasjonsforvaltning

Uavhengig av hvilke metode du går for bør virksomheten få oversikt over hvilke data den sitter på og som skal publiseres.
Følger dere hele eller deler av veilederen [Orden i eget hus](https://www.digdir.no/informasjonsforvaltning/veileder-orden-i-eget-hus/2716),
får dere en god oversikt over hvilke data virksomheten har. (??? Sirkulær, Orden i eget hus inneholder en veileder for databeskrivelser.)

## Spesifikasjonene/standardene vi basererer oss på

For at informasjonen vi høster fra virksomhetens endepunkt skal vises på data.norge.no må beskrivelsen være i henhold til spesifikasjonene.
De respektive spesifikasjonene er, for

- datasett, datatjenester og datakataloger: [DCAT-AP-NO](https://data.norge.no/specification/dcat-ap-no)
- begrep: [SKOS-AP-NO](https://data.norge.no/specification/skos-ap-no-begrep)
- informasjonsmodeller: [ModellDCAT-AP-NO](https://data.norge.no/specification/modelldcat-ap-no)
- tjenester og hendelser: [CPSV-AP-NO](https://data.norge.no/specification/cpsv-ap-no)

Registreringsløsningene genererer RDF-grafer/beskrivelser i henhold til spesifikasjonen, men løsningen støtter ikke alle feltene som fins i spesifikasjonene.

## Lage beskrivelser/RDF-grafer selv

Når du lager beskrivelsene selv må du gjøre det i et RDF-format som støttes av data.norge.no:

- [Turtle](https://www.w3.org/TR/turtle/)
- [RDF/XML](https://www.w3.org/TR/rdf-syntax-grammar/)
- [RDF/JSON](https://www.w3.org/TR/rdf-json/)
- [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [N-Triples](https://www.w3.org/TR/n-triples/)
- ([Notation3/N3](https://www.w3.org/TeamSubmission/n3/) som synonym for Turtle)

Sjekk ut disse guidene for hvordan lage datasettbeskrivelser:

- [Veileder for beskrivelse av datasett, datatjenester og datakataloger](https://informasjonsforvaltning.github.io/veileder-beskrivelse-av-datasett/#beskrivelse-av-datasett)
- [Kursmateriell til workshop i RDF og datasettbeskrivelser](https://github.com/fellesdatakatalog/sikt-workshop/blob/main/ressurshefte/ressurshefte.md)

### Viktig å tenke på med URI-er og ved navngivning av ressurser

Ressurser som beskrives i RDF navngis ved hjelp av en unik, global identifikator, en såkalt URI ("Uniform Resource Identifier").
Strengt tatt bruker man IRI-er ("Internationalized Resource Identifier") i RDF, men begrepene URI og IRI brukes ofte om hverandre som synonymer.

Du bør tenke på at URI-er ideelt sett skal være peke til faktiske nettressurser og være varige og permanente.
Navnerommet til en ressurs bør være avgrenset til et område virksomheten har styring på, og ideelt sett ikke bundet opp til navnet på virksomheten eller andre flyktige begrep.
`https://data.norge.no` er et eksempel på en varig URI med et generisk navn, mens `https://data.digdir.no` eller `https://data.difi.no` er eksempler på navn som kan bli foreldet eller allerede er foreldet.

Når du lager datasettbeskrivelser kan spørsmålet dukke opp, hva URI-en egentlig er navnet til; er det navnet på selve dataen, sånn at om jeg besøker URI-en så kommer jeg til den fysiske lokasjonen for datasettet?
Eller er det navnet på beskrivelsen i seg selv? Konsensus per nå er sistnevnte, at en URI til en datasettbeskrivelse peker til beskrivelsen og ikke til dataen i seg selv. Datasettbeskrivelser har andre måter å peke til den fysiske og faktiske dataen på.

For begreper er det motsatte tilfellet. Der vil URI-en peke til begrepet, eller konseptet, i seg selv. Dette kan virke litt rart, men i begrepskatalogen er det jo beskrivelsene som er selve dataen, mens i datasettkatalogen er beskrivelsen metadata over datasettet.

Mer om URI-er

- [Peikarar til offentlege ressursar på nett (Digdir)](https://www.digdir.no/standarder/peikarar-til-offentlege-ressursar-pa-nett/1492)
- [10 Rules for Persistent URIs (Interoperable Europe)](https://joinup.ec.europa.eu/collection/semic-support-centre/document/10-rules-persistent-uris)
- [Cool URIs for the Semantic Web (W3C)](https://www.w3.org/TR/cooluris/#semweb)

Alle kataloger og ressurser må ha en Unik global identifikator (URI). En Uniform Resource Identifier (URI) er en kompakt streng med tegn
for å identifisere en abstrakt eller fysisk ressurs. Kort om URI: Kilde: http://www.faqs.org/rfcs/rfc2396.html.
Andre mulige kilder: https://www.w3.org/TR/cooluris/#semweb, https://www.w3.org/2001/09/rdfprimer/section2.html#ref-uri

### Validering av beskrivelser

Når du har laget en beskrivelse kan validere den med [data.norge.no sin validator](https://data.norge.no/validator), som gir beskjed om eventuelle feil og mangler i beskrivelsen.

Du kan publisere en beskrivelse som har korrekt syntaks men mangler i henhold til spesifikasjonen. Den vil bare vises som mangelfull på nettsidene til data.norge.no.
En RDF-graf som derimot inneholder syntaktiske feil vil feile ved høsting.

## Registreringsløsning

For å registrere beskrivelser i data.norge.no sin [registreringsløsning](https://registrering.fellesdatakatalog.digdir.no) må du

- være logget inn via ID-porten, og
- ha de riktige tilgangene (minimum «Felles datakatalog - alle kataloger - skrivetilgang»).

Velg deretter den ressurstypen du ønsker å beskrive, og opprett en ny beskrivelse.

Du kan velge om du vil publisere beskrivelsen til data.norge.no, eller beholde den som utkast for videre arbeid. Publiserte endringer høstes ca. en gang i timen til data.norge.no.

## Når du bør velge hva?

Dette fins det ikke et endelig svar på, men vi kan gi noen pekepinner.

Noen grunner til å lage og forvalte beskrivelsene selv:

- Virksomheten er stor og forvaltningen av beskrivelsene er delegert ut til flere enkelt-team/enkeltpersoner.
- Generering av RDF-grafene/beskrivelsene er del av et automatisert løp.
- Dere er mange som gjør hyppige endringer på beskrivelsene.
- Beskrivelsene skal tilgjengeliggjøres for flere enn bare publisering til data.norge.no.
- Dere trenger å bruke felter i spesifikasjonene som ikke er støttet i registreringsløsningen enda.

Grunner til å velge registreringsløsningen:

- Virksomheten er liten og sitter på lite data.
- De ansvarlige i virksomheten ønsker en lavterskel måte å lage beskrivelser uten å sette seg inn i RDF.

### Ressurser

- TODO: Lenke til RDF-ressurser og eksempler på beskrivelser

## Verktøy
