---
info_en: Page about "Getting started - Publishing descriptions"
info_no: Side om "Komme i gang - Publisere beskrivelser/kataloger via høsteadmin-grensesnittet"
description: Skal gi overordnet informasjon om hvordan publisere beskrivelser/kataloger til data.norge.no
url: https://data.norge.no/getting-started/publishing/howto
---

# Hvordan publisere beskrivelser

Har du brukt registreringsløsningen til å lage beskrivelser, og publisert dem derifra, blir katalogen automatisk lagt til for høsting.

Ønsker du å starte en høsting av beskrivelsene dine manuelt, gjør du det fra [administrasjons-grensesnittet for høsting](https://admin.fellesdatakatalog.digdir.no/data-sources).
Du må først tilgjengeliggjøre beskrivelsen i RDF-format på nettet, og registrere endepunktet i administrasjonsgrensesnittet. Slik gjør du det:

## Registrere høsteendepunkt

**Før du begynner:**

- Høsteendepunktet må være tilgjengelig på nettet (eventuelt sikret med en API-nøkkel).
- Dataen som returneres må være i et av [formatene data.norge.no støtter]().
- Du må ha de nødvendige tilgangene for å bruke løsningen.

Les mer om [hvordan skrive databeskrivelser]() og [hvordan få tilgang]().

### Steg 1: Logg inn og legg til datakilde

Logg inn i [admin-grensesnittet for høsting](https://admin.fellesdatakatalog.digdir.no/data-sources) og klikk på knappen «Legg til datakilde».

![Legg til datakilde](image.png)

### Steg 2: Fyll ut skjemaet

Fyll ut alle de obligatoriske feltene i skjemaet.

Det valgte formatet må samsvare med RDF-formatet beskrivelsen er i.

"Navn på datakilde" brukes kun i oversiktsvisningen i administrasjonsgrensesnittet og vises ingen andre steder.

![Skjema](image-1.png)

Klikk på knappen «Lagre». Den nye datakilden skal nå vises i administrasjonsløsningen.

### Steg 3: Start høsting

Klikk på knappen «Høst».

![Høst](image-3.png)

En melding vises om at høsteforespørselen er sendt.

![Melding](image-4.png)

Det kan ta noe tid, avhengig av størrelsen på katalogen din, før resultatet blir publisert og kan sees på [data.norge.no](https://data.norge.no).

Takk for at du deler data!
