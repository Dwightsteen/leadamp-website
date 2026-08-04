# Opdracht: LEAD AMP wordt DE BOUWVERSTERKER

Volledige merkomzetting van `index.html`: naam, kleuren, lettertypen, logo en favicon. De site is tweetalig — NL staat in de HTML, FR in het `FR`-woordenboek onderaan het script. **Elke tekstwijziging gebeurt in beide talen.**

Commit voor je begint. Werk de vijf delen in volgorde af en rapporteer per deel.

---

## Deel 0 — Werkwijze

Dit is één samenhangende opdracht. Werk hem in één doorloop af, niet stap voor stap met tussentijdse vragen.

**Gebruik je eigen Read-, Edit- en Grep-tools voor alles in dit bestand.** Geen shell-commando's om te lezen, te zoeken of te tellen — geen `grep`, geen `stat`, geen `Select-String`, geen PowerShell. Die vragen elk om toestemming en onderbreken het werk. De shell is hier alleen nodig voor `git`.

**Batch de bewerkingen.** Meerdere vervangingen in hetzelfde bestand horen in één bewerking, niet in twintig losse. Lees het bestand één keer volledig in voor je begint.

**Vraag niets tussentijds.** De opdracht hieronder is volledig. Kom je iets tegen dat er niet in staat, kies dan de meest voor de hand liggende oplossing, voer hem uit, en meld het aan het eind onder "afwijkingen".

Rapporteer pas op het eind, in één overzicht.

---

## Deel 1 — De naam

| | |
|---|---|
| Merknaam | **De Bouwversterker** |
| Zonder lidwoord | **Bouwversterker** (waar dat vlotter loopt) |
| Tagline NL | **Meer aanvragen. Minder papierwerk.** |
| Tagline FR | **Plus de demandes. Moins de paperasse.** |
| Domein | `bouwversterker.be` |
| E-mail | `info@bouwversterker.be` |

**Schrijfwijze:** in lopende tekst altijd één woord — *Bouwversterker*, nooit *Bouw Versterker*. Alleen in het logo wordt de naam opgesplitst (zie deel 4).

**Geen toevoegingen achter de naam.** Niet Agency, niet AI, niet Marketing.

### De omschrijving moet weg

Op vier plaatsen staat nu **"digital advertising agency"** of **"digital advertising voor de bouw"**. Dat dekt nog maar de helft van het aanbod.

- NL → **groei en opvolging voor bouwbedrijven**
- FR → **croissance et suivi pour les entreprises de construction**

Na afloop mag *advertising*, *marketing* en *agency* nergens meer in zichtbare tekst voorkomen. In HTML-commentaar over techniek mag het blijven.

### Concrete plaatsen

| Regel | Wordt |
|---|---|
| 6 · `<title>` NL | `De Bouwversterker — meer aanvragen, minder papierwerk voor bouwbedrijven` |
| 7, 23 · `meta.desc` NL | `De Bouwversterker zorgt dat er aanvragen binnenkomen uit jouw regio én dat elke aanvraag beantwoord, ingepland en opgevolgd wordt. Vast maandbedrag, maandelijks opzegbaar.` |
| 20 · `og:site_name` | `De Bouwversterker` |
| 21 · `og:url` | `https://bouwversterker.be/` |
| 24 · `og:image` | `https://bouwversterker.be/og-image.jpg` |
| 11 · commentaar | adres bijwerken |
| 35, 37 · commentaar | naam bijwerken |
| 480 · `aria-label` | `De Bouwversterker` |
| 550, 646 · `alt` | `van De Bouwversterker` |
| 671 / FR 1241 | `wij zijn De Bouwversterker` |
| 673 · `.sign` | `DE BOUWVERSTERKER · meer aanvragen, minder papierwerk` |
| 1029, 1072, 1146 | `hallo@leadamp.be` → `info@bouwversterker.be` |
| 1167 · commentaar | `bv. BOUWVERSTERKER BV` |
| 1177 / FR 1356 · `foot.copy` | `© 2026 De Bouwversterker — groei en opvolging voor bouwbedrijven` (FR: `croissance et suivi pour les entreprises de construction`) |
| 1399, 1405 · localStorage | `'leadamp-lang'` → `'bouwversterker-lang'` |

Het placeholder-telefoonnummer `+32470123456` en het BTW-nummer blijven staan.

---

## Deel 2 — Kleur

Vervang de waarden in `:root` (regels 50–67). **Houd de variabelenamen ongewijzigd** — dan erft de hele stylesheet de nieuwe huisstijl automatisch. Voeg de drie nieuwe onderaan toe.

```css
:root{
  /* De Bouwversterker — huisstijl v1
     Kleuren komen uit het materiaal van de klant:
     bitumen (dakbedekking), krijtblauw (slaglijn),
     meetgeel (rolmeter), kalk (mortel), beton, voeg. */
  --paper:#F4F2ED;            /* kalk — pagina-ondergrond */
  --paper-warm:#EBE8E0;       /* diepere band voor afwisselende secties */
  --ink:#14171C;              /* bitumen — alle donkere tekst */
  --ink-soft:#232830;
  --muted:#5A5F68;
  --muted-dim:#8A8F97;
  --navy:#14171C;             /* donkere secties = bitumen, niet blauw */
  --blue:#1E4FD8;             /* krijtblauw — enige actiekleur */
  --blue-soft:#E7EDFC;
  --gold:#9A6B08;             /* meetgeel, donker genoeg voor tekst */
  --gold-soft:#FDF2DA;
  --green:#0C8A48;            /* blijft: uitsluitend WhatsApp */
  --line:rgba(20,23,28,0.13);
  --line-soft:rgba(20,23,28,0.07);
  --r:0;                      /* metselwerk is recht — geen ronde hoeken */

  /* nieuw */
  --meet:#F5B72C;             /* meetgeel als vlak of accent, nooit als tekst */
  --beton:#B7B4AC;
  --krijt-licht:#5E86EE;      /* blauw op donkere ondergrond */
}
```

**Let op bij `--r:0`.** De site gebruikt nu afgeronde hoeken van 16 px. Alles wordt recht. Loop na of ergens een `border-radius` hard gecodeerd staat in plaats van via `var(--r)` en zet die ook op 0. Uitzondering: ronde profielfoto's blijven rond.

**Verhouding om te bewaken:** ongeveer 60% kalk, 25% bitumen, 10% beton en lijnen, 4% krijtblauw, 1% meetgeel. Blauw is schaars — zodra elke kop blauw is, wijst niets meer. Groen komt **uitsluitend** op de WhatsApp-knop voor.

---

## Deel 3 — Lettertypen

Vervang de Google Fonts-link op regel 32 door:

```html
<link href="https://fonts.googleapis.com/css2?family=Archivo:wdth,wght@75..125,400;75..125,600;75..125,700;75..125,800&family=IBM+Plex+Mono:wght@400;500;600&family=IBM+Plex+Sans:wght@400;500;600&display=swap" rel="stylesheet">
```

Voeg deze variabelen toe aan `:root` en vervang daarna **alle** hard gecodeerde lettertypenamen in de stylesheet:

```css
--disp:'Archivo',Helvetica,Arial,sans-serif;
--body:'IBM Plex Sans',system-ui,sans-serif;
--mono:'IBM Plex Mono',ui-monospace,monospace;
```

| Nu | Wordt |
|---|---|
| `'Bricolage Grotesque'` | `var(--disp)` |
| `'Manrope'` | `var(--body)` |
| `'JetBrains Mono'` | `var(--mono)` |

**Aanpassing per rol:**

- **Koppen** (`h1,h2,h3`, regel 87): `font-weight:800`, `font-stretch:110%`, `letter-spacing:-0.035em`, `text-transform:uppercase` **alleen voor h1**. H2 en h3 blijven in zinsvorm met `font-weight:700` en `letter-spacing:-0.02em`.
- **Broodtekst**: `font-size:16.5px`, `line-height:1.65`.
- **Mono**: labels en eyebrows blijven zoals ze zijn. Bedragen en cijfers krijgen `font-variant-numeric:tabular-nums`, zodat ze in kolommen uitlijnen.

---

## Deel 4 — Logo en favicon

### Het beeldmerk

Vier metselwerkpijlers die oplopen; de vierde staat in krijtblauw en loopt één laag verder dan de rest. Voegen van 2 eenheden tussen de lagen. Gebruik deze SVG letterlijk — vervang het huidige logo op regel 480:

```html
<svg viewBox="0 0 64 48" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="De Bouwversterker">
  <g fill="currentColor">
    <rect x="3" y="38" width="10" height="6"/><rect x="3" y="30" width="10" height="6"/>
    <rect x="19" y="38" width="10" height="6"/><rect x="19" y="30" width="10" height="6"/><rect x="19" y="22" width="10" height="6"/>
    <rect x="35" y="38" width="10" height="6"/><rect x="35" y="30" width="10" height="6"/><rect x="35" y="22" width="10" height="6"/><rect x="35" y="14" width="10" height="6"/>
  </g>
  <g fill="var(--blue)">
    <rect x="51" y="38" width="10" height="6"/><rect x="51" y="30" width="10" height="6"/><rect x="51" y="22" width="10" height="6"/><rect x="51" y="14" width="10" height="6"/><rect x="51" y="6" width="10" height="6"/>
  </g>
</svg>
```

Op donkere ondergrond wordt de blauwe groep `var(--krijt-licht)`.

**Nooit:** uitrekken, kantelen, schaduw of verloop toevoegen, of een andere pijler inkleuren dan de vierde. Vrije ruimte rondom van minstens één pijlerbreedte. Minimumhoogte 20 px.

### Het woordmerk

De naam wordt in het logo op twee regels gezet — dat is typografie, geen spelling:

```
DE BOUW          ← klein, hoofdletters, letter-spacing 0.4em, kleur var(--beton)
VERSTERKER       ← groot, hoofdletters, weight 800, letter-spacing -0.03em
```

De bestaande klassen `.brand-name` en `.brand-sub` (regels 147 en 150) doen dit al bijna. Pas ze aan naar deze verhouding in plaats van nieuwe klassen te maken.

### De tagline

Nieuwe i18n-sleutel `brand.tagline`. Plaats hem op **twee** plekken:

- in de header, klein onder het woordmerk
- in de footer, direct onder de merknaam (regel 1118)

**Niet in de hero.** Daar staat al de H1 *"Méér aanvragen. En geen enkele die verloren gaat."* — twee varianten van dezelfde belofte vlak boven elkaar verzwakt allebei.

### Favicon

Vervang de data-URI op regel 29 door dezelfde vier pijlers zonder afronding, in bitumen met de vierde in krijtblauw. Zonder de `rx`-attributen die er nu in staan. Gebruik `viewBox='0 0 64 46'` zodat het vierkant vult.

---

## Deel 5 — Controleren

Gebruik je Grep-tool, niet de shell. Rapporteer per punt het aantal treffers:

1. `lead ?amp|leadamp` → moet 0 zijn
2. `advertising|marketing|agency` in zichtbare tekst → moet 0 zijn
3. `Bricolage|Manrope|JetBrains` → moet 0 zijn
4. Elke `data-i18n`-sleutel in de HTML heeft een tegenhanger in het FR-object
5. Pagina laadt zonder console-fouten; taalwisselen werkt beide richtingen
6. Header op 375 px breed: de tagline breekt niet over twee regels en verdringt het logo niet
7. Contrast: `--gold` op `--paper` en `--muted` op `--paper` halen minstens 4,5:1
8. Zoek naar overgebleven `border-radius` met een andere waarde dan 0 of 50%

---

## Niet doen

- Geen secties toevoegen of verwijderen — dit is een huisstijlomzetting, geen herschrijving
- De inhoudelijke teksten ongemoeid laten, behalve waar hierboven genoemd
- Bestandsnaam `index.html` behouden
- Telefoonnummer en BTW-nummer niet aanraken

---

Commit met: `De Bouwversterker — merknaam, huisstijl en logo doorgevoerd, NL en FR`
