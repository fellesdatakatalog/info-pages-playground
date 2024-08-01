---
info_en: Page about "Getting started - Creating descriptions"
info_no: Side om "Komme i gang - beskrive data/lage beskrivelser selv"
description: Skal gi overordnet informasjon om hvordan lage beskrivelser
url: https://data.norge.no/getting-started/describing-data
---

# Lage beskrivelser selv

På denne siden lærer du hvordan lage beskrivelser du forvalter selv, slik at de kan publiseres til Data.norge.no. Du må da [sette opp høsting](TODO:lenke-til-side) i høsteløsningen til Data.norge.no for å publisere beskrivelsene.

## Hvordan lage RDF-grafer

Bruk disse guidene for å lære mer om hvordan lage datasettbeskrivelser:

- [Veileder for beskrivelse av datasett, datatjenester og datakataloger](https://informasjonsforvaltning.github.io/veileder-beskrivelse-av-datasett/#beskrivelse-av-datasett)
- [Veileder for orden i eget hus - Steg 5: Beskrive](https://www.digdir.no/informasjonsforvaltning/steg-5-beskrive/2724)
- [Kursmateriell til workshop i RDF og datasettbeskrivelser](https://github.com/fellesdatakatalog/sikt-workshop/blob/main/ressurshefte/ressurshefte.md)

Beskrivelsene som lages må være i et RDF-format og i henhold til spesifikasjonen for ressurstypen som beskrives.

Se [Om spesifikasjonene](TODO:lenke-til-siden-om-spesifikasjon) for mer informasjon om de ulike spesifikasjonene Data.norge.no baserer seg på.

For de andre type ressursene (begrep, informasjonsmodeller, tjenester og hendelser) fins det eksempler på beskrivelser på [Data.norge.no sitt "Showroom"](https://data.norge.no/showroom/overview). Man kan også støtte seg på den aktuelle spesifikasjonen og eksemplene i den. De fleste av eksemplene er skrevet i RDF-formatet kalt Turtle og har overføringsverdi til de andre ressurstypene.

Forvalter du beskrivelsen selv og setter opp høsting, vil høsteløsningen høste og ta vare på alle data i beskrivelsen. Felt som foreløpig ikke er støttet vil dermed bli vist etter hvert som Data.norge.no legger til støtte for visning av feltene.

[Flere relevante ressurser](TODO:lenke-til-side)

### Viktig å tenke på med URI-er og ved navngivning av ressurser

Ressurser som beskrives i RDF navngis ved hjelp av en unik, global identifikator, en såkalt URI ("Uniform Resource Identifier"). URI-er skal være unike og varige, og ideelt sett peke til ressurser som faktisk er tilgjengelig på nettet. Mer informasjon om utforming av URI-er finner du her:

- Mer om URI-er (Data.norge.no)[TODO:lenke-til-side-om-urier]
- [Peikarar til offentlege ressursar på nett (Digdir)](https://www.digdir.no/standarder/peikarar-til-offentlege-ressursar-pa-nett/1492)
- [10 Rules for Persistent URIs (Interoperable Europe)](https://joinup.ec.europa.eu/collection/semic-support-centre/document/10-rules-persistent-uris)
- [Cool URIs for the Semantic Web (W3C)](https://www.w3.org/TR/cooluris/#semweb)

## Støttede RDF-formater

Beskrivelsene du lager må være i et RDF-format som støttes av Data.norge.no:

- [Turtle](https://www.w3.org/TR/turtle/)
- [RDF/XML](https://www.w3.org/TR/rdf-syntax-grammar/)
- [RDF/JSON](https://www.w3.org/TR/rdf-json/)
- [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [N-Triples](https://www.w3.org/TR/n-triples/)
- ([Notation3/N3](https://www.w3.org/TeamSubmission/n3/) som synonym for Turtle)

## Validering av beskrivelser

Når du har laget en beskrivelse kan du validere den med Data.norge.no sin [validator](https://data.norge.no/validator), som gir beskjed om eventuelle feil og mangler.

Du kan publisere en beskrivelse som har korrekt syntaks men innholdsmessige mangler i henhold til spesifikasjonen. Den vil bare vises som mangelfull på nettsidene til Data.norge.no. Inneholder derimot beskrivelsen/RDF-grafen syntaktiske feil vil høstingen mislykkes og beskrivelsen vil ikke vises på Data.norge.no.
