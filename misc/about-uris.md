---
note: ekstra notater om URI-er som ble kuttet.
---

# Om URI-er i RDF

Ressurser som beskrives i RDF navngis ved hjelp av en unik, global identifikator, en såkalt URI ("Uniform Resource Identifier").
Strengt tatt bruker man IRI-er ("Internationalized Resource Identifier") i RDF, men begrepene URI og IRI brukes ofte om hverandre som synonymer.

Ofte vil URI-er til en ressurs være automatisk opprettet, slik at du slipper å gjøre dette selv. Dere bør tenke på at URI-er ideelt sett skal være unike og varige, og ideelt sett peke til faktiske nettressurser.
Navnerommet til en ressurs bør være avgrenset til et område virksomheten har styring på, og ideelt sett ikke bundet opp til navnet på virksomheten eller andre flyktige begrep.
`https://data.norge.no` er et eksempel på en varig URI med et generisk navn, mens `https://data.digdir.no` eller `https://data.difi.no` er eksempler på navn som kan bli foreldet eller allerede er foreldet.

Når du lager datasettbeskrivelser kan spørsmålet dukke opp, hva URI-en egentlig er navnet til; er det navnet på selve dataen, sånn at om jeg besøker URI-en så kommer jeg til den fysiske lokasjonen for datasettet?
Eller er det navnet på beskrivelsen i seg selv? Konsensus per nå er sistnevnte, at en URI til en datasettbeskrivelse peker til beskrivelsen og ikke til dataen i seg selv. Datasettbeskrivelser har andre måter å peke til den fysiske og faktiske dataen på.

For begreper er det motsatte tilfellet. Der vil URI-en peke til begrepet, eller konseptet, i seg selv. Dette kan virke litt rart, men i begrepskatalogen er det jo beskrivelsene som er selve dataen, mens i datasettkatalogen er beskrivelsen metadata om datasettet.

Mer om URI-er:

- [Peikarar til offentlege ressursar på nett (Digdir)](https://www.digdir.no/standarder/peikarar-til-offentlege-ressursar-pa-nett/1492)
- [10 Rules for Persistent URIs (Interoperable Europe)](https://joinup.ec.europa.eu/collection/semic-support-centre/document/10-rules-persistent-uris)
- [Cool URIs for the Semantic Web (W3C)](https://www.w3.org/TR/cooluris/#semweb)
