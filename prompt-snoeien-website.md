# Opdracht: de website terugbrengen van 2.650 naar ±700 woorden

Werk in `index.html`. Dit is een **snoei-opdracht**, geen herschrijving. De teksten die blijven staan zijn goed — er staan er alleen veel te veel.

Commit voor je begint.

---

## Deel 0 — Werkwijze

Werk in één doorloop af. Gebruik je eigen Read-, Edit- en Grep-tools; geen shell-commando's om te lezen of te tellen. De shell is alleen nodig voor `git`.

**Elke wijziging gebeurt in beide talen.** Verwijder je een sectie in de HTML, verwijder dan ook de bijbehorende sleutels uit het `FR`-woordenboek onderaan het script. Laat geen weesvertalingen achter.

Vraag niets tussentijds. Kom je iets tegen dat hieronder niet beschreven staat, kies dan de meest voor de hand liggende oplossing en meld het aan het eind onder "afwijkingen".

---

## Waarom dit moet

De pagina telt nu 2.653 woorden — ongeveer elf minuten lezen. De bezoeker is een zelfstandige aannemer die de link op zijn gsm opent, vaak in zijn bestelwagen, en er veertig seconden aan geeft.

De site hoeft niet te verkopen. Dat doet het telefoongesprek. **De site moet bewijzen dat we bestaan, duidelijk maken wat we doen, en één actie aanbieden.**

Alles wat hieronder geschrapt wordt, is bewaard in `sales-pitch-informatie.md`. Het is niet verloren — het verhuist naar het gesprek.

---

## Deel 1 — Volledig verwijderen

### 1.1 · Het `amp·li·fy` woordenboekblok

Het definitieblok met de fonetische uitspraak en de uitleg over "versterken, vergroten, luider maken". Dat hoorde bij de oude naam LEAD AMP. De naam is nu De Bouwversterker, dus dit slaat nergens meer op.

Verwijder het blok en alle bijbehorende i18n-sleutels, NL en FR.

### 1.2 · De lopende balk met vaknamen

De marquee met `Dakwerken · Renovatie · Aannemers · Schrijnwerk · …`. Beweging zonder inhoud, en ze leidt af van de sectie eronder. Verwijder het element, de CSS-animatie en de keyframes die alleen daarvoor gebruikt worden.

### 1.3 · De sectie "Dagelijkse opvolging" (`#opvolging`)

Vier kaarten over hoe wij campagnes dagelijks bijsturen. Dit gaat over **ons werk**, niet over **zijn probleem** — daarom mag het weg.

Verwijder de hele sectie, plus de link ernaar in het footermenu.

### 1.4 · De uitleg over exclusiviteit in de aanpaksectie

In `#aanpak` staat een blok "Eén aanvraag, één bouwbedrijf" met drie opsommingen en een afsluitende alinea over wat exclusief precies betekent. Samen ruim 300 woorden over één punt dat elders al drie keer gemaakt wordt.

Vervang het hele blok door één zin:

> **Wie jouw formulier invult, vraagt naar jou.** Die aanvraag gaat naar jou en naar niemand anders — nooit doorverkocht, nooit gedeeld.

De rest van `#aanpak` (Meta versus Google) blijft, maar ingekort volgens deel 2.

### 1.5 · Drie van de vier lege bewijsplekken

In de bewijssectie staan nu vier placeholders: "Videoreactie komt hier", "Schermafbeelding komt hier", "Cijfers komen hier" en "Klantenlogo's komen hier". Vier keer *komt hier* leest als: wij hebben niets.

Houd er **één** over — de schermafbeelding van binnenkomende aanvragen in WhatsApp, want die kan er binnenkort echt staan. Verwijder de andere drie.

Het pilotblok ("Nog één plaats in de pilot") blijft.

---

## Deel 2 — Inkorten, niet verwijderen

### 2.1 · De FAQ

Zeven vragen worden er **vier**. Behoud, in deze volgorde:

1. Zit het advertentiebudget in jullie maandbedrag?
2. Wie bezit het advertentieaccount en de gegevens?
3. Wat als het niet werkt — kan ik stoppen?
4. Moet ik zelf nog iets doen?

Verwijder: *Hoe snel komen de eerste aanvragen binnen*, *In welke regio's werken jullie*, *Krijg ik een factuur en is dit aftrekbaar*.

Kort daarnaast het blok erboven in — de twee genummerde uitlegvakken "1 · Ons werk" en "2 · Je advertentiebudget" — tot samen maximaal 80 woorden. De inhoud staat toch in vraag 1.

### 2.2 · De sectie "Na de aanvraag" (`#na-de-aanvraag`)

Blijft staan — dit is het onderscheid met andere bureaus. Maar kort elke van de vier alinea's in tot **maximaal 25 woorden**. Nu zijn het er 40 tot 50.

De koppen blijven ongewijzigd.

### 2.3 · De sectie "De stille agenda" (`#stille-agenda`)

Vier kaarten blijven, maar elke tekst naar **maximaal 20 woorden**.

### 2.4 · De aanbodsectie (`#aanbod`)

De twee helften Méér en Béter blijven precies zoals ze zijn. Dit is het hart van de pagina. **Niet aanraken.**

### 2.5 · Meta versus Google

Behoud de twee blokken, maar breng elk terug tot twee zinnen.

---

## Deel 3 — Ritme doorbreken

Het grootste visuele probleem is niet de lengte maar de **eentonigheid**: zes secties na elkaar met exact dezelfde opbouw — eyebrow, kop, alinea, rij van vier genummerde kaarten.

Na het snoeien blijven er drie genummerde rijen over: `#stille-agenda`, `#na-de-aanvraag` en `#plan`.

Geef er twee een andere vorm:

- **`#stille-agenda`** → geen kaarten meer, maar een eenvoudige lijst met vier korte regels onder elkaar, gescheiden door een dunne lijn. Geen nummers.
- **`#plan`** → houd de nummers 01–03, want dit is écht een volgorde in de tijd. Zet ze horizontaal naast elkaar in plaats van als kaarten.
- **`#na-de-aanvraag`** → behoudt de genummerde kaarten. Zo blijft er één rij over, en die valt dan ook op.

Gebruik hiervoor bestaande CSS-klassen waar mogelijk. Voeg geen nieuwe kleuren of lettertypen toe.

---

## Deel 4 — Controleren

Rapporteer per punt:

1. Woordenaantal van de zichtbare tekst → doel **650 tot 800**
2. `grep -i "amp·li·fy\|amplify"` → moet 0 zijn
3. Elke `data-i18n`-sleutel in de HTML heeft nog een tegenhanger in het FR-object, en omgekeerd staan er geen ongebruikte FR-sleutels meer
4. Alle ankerlinks in de navigatie en de footer wijzen nog naar bestaande secties — `#opvolging` moet overal weg zijn
5. Pagina laadt zonder console-fouten, taalwisselen werkt in beide richtingen
6. Controleer op 375 px breed of er geen lege ruimte is ontstaan waar een sectie verwijderd werd

---

## Niet doen

- De aanbodsectie met Méér en Béter niet inkorten
- Geen nieuwe secties toevoegen
- Kleuren, lettertypen en logo niet aanraken — die zijn vorige ronde vastgelegd
- Telefoonnummer en BTW-nummer niet aanraken
- Bestandsnaam `index.html` behouden

---

Commit met: `website gesnoeid van 2650 naar ±700 woorden, NL en FR`
