# Opdracht: merknaam omzetten van LEAD AMP naar VERSTERKER

Werk in `index.html`. De site is tweetalig (NL in de HTML, FR in het `FR`-woordenboek onderaan het script). **Elke tekstwijziging moet in beide talen gebeuren** — een `data-i18n`-sleutel die je in de HTML aanpast, moet ook in het FR-object bijgewerkt worden.

Commit voor je begint, zodat er een terugvalpunt is.

---

## 1. De nieuwe identiteit

| | |
|---|---|
| Naam | **VERSTERKER** — altijd in hoofdletters in logo en headers, in lopende tekst gewoon "Versterker" |
| Tagline NL | **Meer aanvragen. Minder papierwerk.** |
| Tagline FR | **Plus de demandes. Moins de paperasse.** |
| Domein | `versterker.be` |
| E-mail | `hallo@versterker.be` |

**Geen toevoegingen achter de naam.** Niet "Agency", niet "AI", niet "Marketing". De naam staat alleen; de tagline doet het uitlegwerk.

---

## 2. Belangrijk: de omschrijving klopt niet meer

Op meerdere plaatsen staat nu **"digital advertising agency"** of **"digital advertising voor de bouw"**. Die omschrijving dekt nog maar de helft van wat we aanbieden en moet overal weg.

Vervang door:

- NL: **groei en opvolging voor bouwbedrijven**
- FR: **croissance et suivi pour les entreprises de construction**

Het woord *marketing*, *advertising* of *agency* mag nergens meer in zichtbare tekst voorkomen. In HTML-commentaar mag het blijven staan als het over de techniek gaat.

---

## 3. Concrete vervangingen

### Metadata (regels 6–24)

- `<title>` NL → `VERSTERKER — meer aanvragen, minder papierwerk voor bouwbedrijven`
- `<title>` FR → `VERSTERKER — plus de demandes, moins de paperasse pour les entreprises de construction`
- `meta.desc` NL → `Versterker zorgt dat er aanvragen binnenkomen uit jouw regio én dat elke aanvraag beantwoord, ingepland en opgevolgd wordt. Vast maandbedrag, maandelijks opzegbaar.`
- `meta.desc` FR → `Versterker fait en sorte que les demandes arrivent de votre région et que chacune soit traitée, planifiée et suivie. Montant mensuel fixe, résiliable chaque mois.`
- `og:site_name` → `VERSTERKER`
- `og:url` → `https://versterker.be/`
- `og:image` → `https://versterker.be/og-image.jpg`
- Commentaar op regel 11: adres bijwerken

### Zichtbare tekst

| Regel | Nu | Wordt |
|---|---|---|
| 480 | `aria-label="LEAD AMP"` | `aria-label="VERSTERKER"` |
| 550, 646 | `alt="[Naam] en [Naam] van LEAD AMP"` | `van VERSTERKER` |
| 671 / FR 1241 | `wij zijn LEAD AMP` | `wij zijn Versterker` |
| 673 | `LEAD AMP · digital advertising voor de bouw` | `VERSTERKER · meer aanvragen, minder papierwerk` |
| 1177 / FR 1356 | `© 2026 LEAD AMP — digital advertising agency` | `© 2026 VERSTERKER — groei en opvolging voor bouwbedrijven` (FR: `croissance et suivi pour les entreprises de construction`) |
| 1167 | commentaar `bv. LEAD AMP BV` | `bv. VERSTERKER BV` |

### E-mail en contact

- Regel 1146 en het commentaar op 1029 en 1072: `hallo@leadamp.be` → `hallo@versterker.be`
- Laat het placeholder-telefoonnummer `+32470123456` voorlopig staan; dat volgt in een aparte ronde.

### Taalvoorkeur in localStorage (regels 1399, 1405)

`'leadamp-lang'` → `'versterker-lang'`

Dit wist de opgeslagen taalkeuze van bestaande bezoekers eenmalig. Dat is aanvaardbaar; de standaard is toch NL.

### Commentaarblok bovenaan (regels 35–37)

Werk de naam bij in het uitlegblok over de zes beats.

---

## 4. Nieuw: de tagline een plek geven

De tagline staat nu nergens. Voeg hem toe op twee plaatsen:

**A. In de header, onder of naast het logo** (rond regel 480). Klein, in de bestaande stijl — geen nieuw kleurgebruik. Gebruik een nieuwe i18n-sleutel `brand.tagline`.

**B. In de footer**, direct onder de merknaam, met dezelfde sleutel.

Zet hem **niet** in de hero. Daar staat al de H1 *"Méér aanvragen. En geen enkele die verloren gaat."* — twee varianten van dezelfde belofte vlak boven elkaar verzwakt allebei.

---

## 5. Controleren na afloop

Voer deze checks uit en rapporteer het resultaat:

1. `grep -ci "lead ?amp\|leadamp"` → moet 0 zijn
2. `grep -ci "advertising\|marketing\|agency"` in zichtbare tekst → moet 0 zijn
3. Elke `data-i18n`-sleutel in de HTML heeft een tegenhanger in het FR-object
4. De pagina laadt zonder console-fouten en het taalwisselen werkt in beide richtingen
5. Bekijk de header op een schermbreedte van 375px — de tagline mag daar niet over twee regels breken of het logo verdringen

---

## 6. Niet doen

- Geen kleuren, lettertypen of layout wijzigen
- Geen secties toevoegen of verwijderen
- De bestandsnaam `index.html` ongemoeid laten
- Het placeholder-telefoonnummer en BTW-nummer niet aanraken

---

Commit aan het eind met de boodschap: `merknaam VERSTERKER doorgevoerd, NL en FR`
