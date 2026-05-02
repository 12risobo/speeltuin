---
marp: true
theme: uncover
paginate: true
size: 16:9
style: |
  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&family=Playfair+Display:wght@700&display=swap');

  :root {
    --color-green-dark: #2d5016;
    --color-green: #4a7c28;
    --color-green-light: #7cb342;
    --color-green-pale: #e8f5e9;
    --color-sand: #f5f0e8;
    --color-sand-dark: #e8dcc8;
    --color-warm: #ff8f00;
    --color-warm-light: #fff3e0;
    --color-text: #2c2c2c;
    --color-text-light: #5a5a5a;
    --color-accent-blue: #1565c0;
    --color-accent-purple: #6a1b9a;
    --color-accent-red: #c62828;
  }

  section {
    font-family: 'Inter', system-ui, sans-serif;
    background: var(--color-sand);
    color: var(--color-text);
    padding: 50px 70px;
    justify-content: flex-start;
  }

  section::after {
    content: attr(data-marpit-pagination) ' / ' attr(data-marpit-pagination-total);
    font-size: 0.55em;
    color: var(--color-text-light);
    position: absolute;
    bottom: 25px;
    right: 40px;
  }

  h1 {
    font-family: 'Playfair Display', serif;
    color: var(--color-green-dark);
    font-size: 2.2em;
    margin-bottom: 0.2em;
    border-bottom: 3px solid var(--color-green-light);
    padding-bottom: 8px;
  }

  h2 {
    font-family: 'Playfair Display', serif;
    color: var(--color-green);
    font-size: 1.5em;
    margin-bottom: 0.3em;
  }

  h3 {
    color: var(--color-green-dark);
    font-weight: 600;
    font-size: 1.1em;
    margin-bottom: 0.2em;
  }

  p, li {
    font-size: 0.78em;
    line-height: 1.5;
    color: var(--color-text);
  }

  ul { margin: 0.3em 0; }
  li { margin: 0.15em 0; }

  strong { color: var(--color-green-dark); }
  em { color: var(--color-text-light); font-style: italic; }

  table {
    font-size: 0.68em;
    border-collapse: collapse;
    width: 100%;
    margin: 0.5em 0;
  }

  th {
    background: var(--color-green);
    color: white;
    padding: 8px 12px;
    text-align: left;
    font-weight: 600;
  }

  td {
    padding: 6px 12px;
    border-bottom: 1px solid var(--color-sand-dark);
  }

  tr:nth-child(even) td {
    background: rgba(124, 179, 66, 0.08);
  }

  blockquote {
    background: var(--color-green-pale);
    border-left: 4px solid var(--color-green-light);
    padding: 12px 20px;
    margin: 0.5em 0;
    border-radius: 0 8px 8px 0;
    font-size: 0.8em;
  }

  blockquote p { margin: 0; color: var(--color-green-dark); }

  code {
    background: var(--color-sand-dark);
    padding: 2px 6px;
    border-radius: 4px;
    font-size: 0.85em;
  }

  img {
    border-radius: 8px;
    box-shadow: 0 2px 12px rgba(0,0,0,0.1);
  }

  /* Title slide */
  section.title {
    background: linear-gradient(135deg, var(--color-green-dark) 0%, var(--color-green) 60%, var(--color-green-light) 100%);
    color: white;
    justify-content: center;
    text-align: center;
    padding: 60px 80px;
  }
  section.title h1 {
    font-size: 2.8em;
    color: white;
    border-bottom: 3px solid rgba(255,255,255,0.4);
    margin-bottom: 0.3em;
  }
  section.title p {
    color: rgba(255,255,255,0.85);
    font-size: 1.1em;
  }
  section.title::after { color: rgba(255,255,255,0.4); }

  /* Section divider */
  section.divider {
    background: linear-gradient(135deg, var(--color-green) 0%, var(--color-green-light) 100%);
    color: white;
    justify-content: center;
    text-align: center;
  }
  section.divider h1 {
    color: white;
    border-bottom: 3px solid rgba(255,255,255,0.3);
    font-size: 2.6em;
  }
  section.divider p { color: rgba(255,255,255,0.8); font-size: 1em; }
  section.divider::after { color: rgba(255,255,255,0.4); }

  /* Variant slides */
  section.variant-a { border-top: 6px solid var(--color-accent-purple); }
  section.variant-a h1 { color: var(--color-accent-purple); border-color: var(--color-accent-purple); }

  section.variant-b { border-top: 6px solid var(--color-green); }

  section.variant-c { border-top: 6px solid var(--color-warm); }
  section.variant-c h1 { color: #e65100; border-color: var(--color-warm); }

  section.variant-d { border-top: 6px solid var(--color-accent-red); }
  section.variant-d h1 { color: var(--color-accent-red); border-color: var(--color-accent-red); }

  /* Comparison slide */
  section.compare table th { font-size: 0.75em; }
  section.compare table td { font-size: 0.65em; padding: 5px 8px; }

  /* Two column layout */
  .columns { display: flex; gap: 40px; }
  .col { flex: 1; }

  /* Badge */
  .badge {
    display: inline-block;
    background: var(--color-green-light);
    color: white;
    padding: 3px 10px;
    border-radius: 12px;
    font-size: 0.7em;
    font-weight: 600;
  }
  .badge-var {
    background: var(--color-warm);
  }

  /* Highlight box */
  .highlight {
    background: var(--color-warm-light);
    border: 1px solid var(--color-warm);
    border-radius: 8px;
    padding: 10px 16px;
    margin: 0.4em 0;
    font-size: 0.8em;
  }

  /* Compact slides — verklein basis font-size voor garantie op witruimte onderin */
  section.compact {
    font-size: 22px;
    padding: 30px 55px 80px;
  }
  section.compact h1 { font-size: 1.6em; margin-bottom: 0.2em; padding-bottom: 5px; }
  section.compact h2 { font-size: 1.15em; }
  section.compact h3 { font-size: 1em; margin-top: 0.55em; margin-bottom: 0.2em; }
  section.compact p, section.compact li { font-size: 0.85em; line-height: 1.35; }
  section.compact table { font-size: 0.78em; margin: 0.3em 0; }
  section.compact th { padding: 4px 8px; }
  section.compact td { padding: 3px 8px; }
  section.compact blockquote { font-size: 0.82em; padding: 6px 14px; margin: 0.3em 0; }
  section.compact ul { margin: 0.15em 0; }
  section.compact li { margin: 0.08em 0; }

  /* Plattegrond slides — afbeelding vult bijna hele sheet */
  section.plattegrond {
    padding: 30px 50px 50px;
    justify-content: flex-start;
  }
  section.plattegrond h1 { font-size: 1.6em; margin-bottom: 0.3em; padding-bottom: 5px; }
  section.plattegrond img {
    display: block;
    margin: 0 auto;
    max-height: 78vh;
    max-width: 95%;
    box-shadow: 0 4px 20px rgba(0,0,0,0.12);
  }
---

<!-- _class: title -->
<!-- _paginate: skip -->

# Samenspeelplek Karel Doormanstraat

Variantenstudie — ter bespreking kernteam

Nijkerk, april 2026

---

<!-- _class: compact -->

# Waar staan we?

<div class="columns">
<div class="col">

### Traject tot nu toe
- Enquete gehouden (63 respondenten, 236 adressen)
- Gesprek met gemeente en Samenspeelfonds
- Kernteam gevormd (8 betrokkenen)
- Wachten op groen licht gemeente

### Het terrein
- **~1.200 m²** (ca. 50m x 25m)
- Begrensd door Piet Heinlaan, Tromplaan, De Ruyterstraat en Karel Doormanstraat

</div>
<div class="col">

### Budget
| Bron | Bedrag |
|---|---|
| Gemeente | ~€70.000 |
| Samenspeelfonds | €50.000 (mits stichting) |
| Overige fondsen | €15.000 - €30.000 |
| **Totaal beschikbaar** | **€150.000 - €170.000** |

> 75% van het Samenspeelfonds wordt vooraf uitbetaald — dit is het startkapitaal

</div>
</div>

---

<!-- _class: compact -->

# Wat wil de buurt?

<div class="columns">
<div class="col">

### Meest gevraagde toestellen

| Toestel | Score |
|---|---|
| Glijbaan | **75%** |
| Klimtoestel | **73%** |
| Schommel | **71%** |
| Peuterzone | **60%** |
| Kabelbaan | 46% |
| Waterspeelplek | 41% |
| Sporttoestellen | 32% |
| Creatieve opties | 24% |

</div>
<div class="col">

### Belangrijkste waarden

| Waarde | Score |
|---|---|
| Inclusiviteit | **35%** |
| Uitdagend spelen | 19% |
| Veiligheid | 18% |
| Veel groen | 13% |
| Ontmoeting | 10% |

### Huidige beoordeling
**68%** geeft de huidige speeltuin een **1 of 2** op 5

**0%** wil niet meehelpen — iedereen staat open voor betrokkenheid

</div>
</div>

---

<!-- _class: compact -->

# Hoe werkt deze variantenstudie?

<div class="columns">
<div class="col">

### Vaste basis <span class="badge">€131.000</span>
Alles met **>60% steun** staat vast in elke variant:

- Klimtoestel met RVS glijbaan *(Robinia)*
- 3 schommels *(incl. vogelnest — inclusief)*
- Kabelbaan ~20m
- Peuterzone *(afgeschermd, zandbak, glijbaan)*
- Waterspeelplek *(compact)*
- Verharde slingerpaden
- Basisgroen en bankjes
- Installatie, keuring en ontwerp

</div>
<div class="col">

### Variabel budget <span class="badge badge-var">~€15.000</span>
Het verschil tussen de varianten zit in hoe dit budget wordt besteed.

**Vier varianten, vier karakters:**

| | Variant | Karakter |
|---|---|---|
| **A** | Avontuur & Sport | Fysieke uitdaging |
| **B** | Groen & Natuur | Natuurlijk spelen |
| **C** | Ontmoeting & Creativiteit | Samen zijn |
| **D** | Buurt Beslist Later | Participatie |

> Geen variant is "beter" — het gaat om: **wat voor plek willen we zijn?**

</div>
</div>

---

<!-- _class: divider -->
<!-- _paginate: skip -->

# De vier varianten

---

<!-- _class: variant-a compact -->

# Variant A — Avontuur & Sport

> *"Een plek waar je jezelf uitdaagt"*

<div class="columns">
<div class="col">

### Extra elementen <span class="badge badge-var">variabel</span>

| Element | Budget |
|---|---|
| Sporttoestel / calisthenics | €7.000 |
| Basketbalpaal dubbel | €3.000 |
| Draaitoestel | €3.000 |
| Extra grondverzet | €2.000 |
| **Subtotaal variabel** | **€15.000** |
| **Totaal variant A** | **~€146.000** |

</div>
<div class="col">

### Sterk punt
- Trekt ook **tieners en volwassenen** — minder "hangplek"-risico
- Sporttoestel telt als **inclusief element** (extra subsidie SSF)

### Aandachtspunt
- Minder groen
- Mogelijke geluidsoverlast basketbal

</div>
</div>

---

<!-- _class: variant-a plattegrond -->

# Variant A — Plattegrond

![](../Attachments/plattegrond-variant-a.svg)

---

<!-- _class: variant-b compact -->

# Variant B — Groen & Natuur

> *"Een plek die leeft en meegroeit"*

<div class="columns">
<div class="col">

### Extra elementen <span class="badge badge-var">variabel</span>

| Element | Budget |
|---|---|
| Heuvel met tunnel + glijbaan | €6.000 |
| Wilgentunnel (NL Doet) | €800 |
| Uitbreiding waterspeelplek | €3.000 |
| Fruitbomen + kruidentuin | €2.000 |
| Boomstammen, keien | €1.500 |
| Insectenhotel | €700 |
| Wilde bloemen | €2.000 |
| **Subtotaal variabel** | **€16.000** |
| **Totaal variant B** | **~€147.000** |

</div>
<div class="col">

### Sterk punt
- **Sterkste fondsen-verhaal** (SSF, VSBfonds, Springzaad)
- Bouwdagen leveren **cofinanciering** op (vrijwilligersuren a €30/u)
- Laagste onderhoudskosten lange termijn

</div>
</div>

---

<!-- _class: variant-b plattegrond -->

# Variant B — Plattegrond

![](../Attachments/plattegrond-variant-b.svg)

---

<!-- _class: variant-c compact -->

# Variant C — Ontmoeting & Creativiteit

> *"Een plek waar je elkaar vindt"*

<div class="columns">
<div class="col">

### Extra elementen <span class="badge badge-var">variabel</span>

| Element | Budget |
|---|---|
| Buitenmuziekinstrumenten (4x) | €5.000 |
| Draaitoestel / carrousel | €3.000 |
| Extra picknicktafels (2x) | €2.500 |
| Extra bankjes (4x) | €2.000 |
| Schaduwbomen (2 extra) | €1.500 |
| Speelpanelen (educatief) | €2.000 |
| **Subtotaal variabel** | **€16.000** |
| **Totaal variant C** | **~€147.000** |

</div>
<div class="col">

### Sterk punt
- Muziek **overstijgt taalgrenzen** — past bij multiculturele buurt
- Sterkste **sociale functie**: ouders en grootouders verblijven langer
- Uniek in Nijkerk

</div>
</div>

---

<!-- _class: variant-c plattegrond -->

# Variant C — Plattegrond

![](../Attachments/plattegrond-variant-c.svg)

---

<!-- _class: variant-d compact -->

# Variant D — Buurt Beslist Later

> *"Samen bouwen, stap voor stap"*

<div class="columns">
<div class="col">

### Aanpak

| Fase | Wat | Budget |
|---|---|---|
| **Fase 1** | Vaste basis realiseren | €131.000 |
| *3-6 mnd* | *Ervaring opdoen* | |
| **Fase 2** | Buurt kiest invulling | €15.000 |
| **Totaal** | | **~€146.000** |

### Sterk punt
- **Maximale participatie** — buurt beslist echt mee
- Twee "momenten" voor publiciteit en fondswerving

</div>
<div class="col">

### Optiemenu fase 2 (buurt kiest)
- Sporttoestel + basketbal (~€10K)
- Heuvel met tunnel (~€6K)
- Muziekpanelen (~€5K)
- Wilgentunnel + fruitbomen (~€4,5K)
- Extra zitplekken (~€4,5K)

</div>
</div>

---

<!-- _class: variant-d plattegrond -->

# Variant D — Plattegrond

![](../Attachments/plattegrond-variant-d.svg)

---

<!-- _class: compare compact -->

# Vergelijking in een oogopslag

| | **A: Avontuur & Sport** | **B: Groen & Natuur** | **C: Ontmoeting** | **D: Buurt Beslist** |
|---|---|---|---|---|
| **Accent** | Fysieke uitdaging | Natuurlijk spelen | Samen & expressie | Participatie |
| **Totaal** | ~€146K | ~€147K | ~€147K | ~€146K |
| **Uniek** | Calisthenics + basketbal | Heuvel + wilgentunnel | Muziekinstrumenten | Gereserveerd budget |
| **Doelgroep extra** | Tieners, volwassenen | Natuur-minded gezinnen | Multicultureel, ouderen | Hele buurt kiest |
| **Fondsen-verhaal** | Sport & preventie | Groen & participatie | Inclusie & leefbaarheid | Co-creatie |
| **Risico** | Geluidsoverlast | Groeitijd groen | Geluidsoverlast muziek | Twee bouwfases |

> Combineren kan ook — bv. het groene karakter van B met muziekpanelen uit C, of variant D met een groen accent in fase 1.

---

<!-- _class: compact -->

# Vervolgstappen

<div class="columns">
<div class="col">

### Na keuze kernteam
1. Gekozen richting voorleggen aan bredere groep
2. Eventueel stemming (online + fysiek)
3. Definitieve variant meenemen in professioneel ontwerp

### Na groen licht gemeente
4. Stichting formeel oprichten
5. Samenspeelfonds-aanvraag indienen
6. Fondswervingsplan uitwerken
7. Offertes aanvragen bij leveranciers

</div>
<div class="col">

### Realisatie
8. Bouwdag(en) organiseren *(NL Doet / Burendag)*
9. Professionele installatie toestellen
10. Veiligheidskeuring (WAS)
11. **Opening!**

### Leveranciers om te benaderen
- **Robinia / natuurlijk:** Acacia-Robinia, Goede Speelprojecten
- **Breed:** Nijha, Kompan, IJslander, Lappset
- **Kennis:** Jantje Beton, Stichting Springzaad

> Vraag minimaal 3 offertes per categorie

</div>
</div>

---

<!-- _class: title -->
<!-- _paginate: skip -->

# Welke plek willen we zijn?

Laten we het gesprek voeren.

Samenspeelplek Karel Doormanstraat — Nijkerk
