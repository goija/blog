Hier is een concept voor een blogpost die uw fascinerende vraagstuk vertaalt naar een praktisch, technisch en filosofisch betoog. Dit stuk slaat de brug tussen de abstracte theorie van het ORS-raamwerk en de harde logica van het Semantic Web.

# Van Filosofie naar Code: Hoe we Autonome AI Classificeren met de CPST-Ontologie en OWL

De discussie rondom de governance van kunstmatige intelligentie (AI) zit vaak muurvast in een verouderd filosofisch dualisme. We zien een AI ofwel als een stuk gereedschap (een hamer van code), ofwel we vermenselijken het systeem volkomen onterecht. Zoals het academische Onto-Relational-Sophic (ORS) framework stelt, dekt onze traditionele ontologie de realiteit niet meer.

Om fenomenen zoals LLM's en *grief bots* juridisch en ethisch te kunnen duiden, introduceert het ORS-raamwerk de Cyber-Physical-Social-Thinking (CPST) ontologie. Maar een ontologie is pas écht krachtig als ze machinaal leesbaar is, precies zoals het Jabes-raamwerk (van J.A. Karman) dicteert voor bedrijfsdata.

In deze blog duiken we in de techniek: hoe formaliseren we deze CPST-ontologie in de Web Ontology Language (OWL) met behulp van Protégé? En nog belangrijker, hoe kunnen we formele logica gebruiken om een *reasoner* automatisch te laten bepalen of een AI-model een passief **"Gereedschap"** is, of de complexe status van een **"Relational Companion"** heeft bereikt?

---

## 1. De Fundering in Protégé: Klassen en Relaties

Voordat een reasoner conclusies kan trekken, moeten we de wereld modelleren. In Protégé bouwen we eerst de taxonomie (de hiërarchie van concepten) op basis van de vier CPST-dimensies.

**De Hoofdklassen (Classes):**

* `AI_Instantie` (Het daadwerkelijke systeem in kwestie)
* `Cyber_Component` (De architectuur, bijv. Transformer)
* `Fysieke_Component` (Servers, sensoren)
* `Sociale_Integratie` (De rol in de menselijke maatschappij)
* `Denk_Capaciteit` (Cognitieve functies)

Vervolgens definiëren we **Object Properties** (de relaties) die de `AI_Instantie` verbinden met zijn CPST-dimensies:

* `hasCyber`
* `hasPhysical`
* `hasSocial`
* `hasThinking`

Om onderscheid te kunnen maken tussen een simpel script en een LLM, creëren we subklassen voor de *Social* en *Thinking* attributen. Bijvoorbeeld: `PassiveExecution` versus `AutonomousReasoning` (voor Thinking) en `UserToolInteraction` versus `RelationalDependency` (voor Social).

---

## 2. De Magie van Description Logics (DL)

Hier wordt het écht interessant. In OWL gebruiken we *Description Logics* (DL) om formele definities te schrijven. We vertellen de reasoner (zoals HermiT of Pellet in Protégé) niet expliciet wat een specifieke AI is; we definiëren enkel de *voorwaarden* waaraan een concept moet voldoen. De reasoner leidt de rest zelf af.

Laten we twee kernconcepten definiëren in formele logica:

### A. Het Passieve Gereedschap (Passive Tool)

Een AI wordt juridisch gezien als een stuk gereedschap als het slechts passieve taken uitvoert en geen complexe, inter-afhankelijke sociale relaties aangaat. In DL-notatie ziet dit er als volgt uit:

$PassiveTool \equiv AI\_Instantie \sqcap \forall hasThinking.PassiveExecution \sqcap \forall hasSocial.UserToolInteraction$

*Vertaling:* Een `PassiveTool` is exact gelijk aan een `AI_Instantie` waarbij **alle** denkprocessen louter passieve executie zijn, en **alle** sociale integraties beperkt blijven tot een standaard gereedschap-gebruiker interactie.

### B. De Relationele Metgezel (Relational Companion)

Een digitale tweeling (zoals een *grief bot*) overstijgt de status van gereedschap wanneer het autonoom redeneert en interageert alsof het een sociale actor is. Dit definiëren we zo:

$RelationalCompanion \equiv AI\_Instantie \sqcap \exists hasThinking.AutonomousReasoning \sqcap \exists hasSocial.RelationalDependency$

*Vertaling:* Een `RelationalCompanion` is een `AI_Instantie` die **minstens één** denkproces heeft dat autonoom redeneert, én **minstens één** sociale relatie heeft die leidt tot relationele afhankelijkheid of diepe interactiviteit.

---

## 3. De Reasoner in de Praktijk: Automatische Classificatie

Stel, een techbedrijf lanceert **"GriefBot_v2"**. In onze Protégé-ontologie voeren we dit systeem als een *Individual* (een instantie) in. We weten (op basis van de technische documentatie en het datagebruik) het volgende over deze bot:

1. GriefBot_v2 `hasThinking` *LLM_Diagnostisch_Redeneren* (wat we eerder geclassificeerd hebben als een vorm van `AutonomousReasoning`).
2. GriefBot_v2 `hasSocial` *Autonoom_Berichten_Sturen_Naar_Nabestaanden* (wat we hebben geclassificeerd onder `RelationalDependency`).

Wanneer we nu de reasoner in Protégé aanzetten, gebeurt er iets spectaculairs. We hebben "GriefBot_v2" nergens expliciet het label `RelationalCompanion` gegeven. Echter, de reasoner scant de DL-axioma's, vergelijkt deze met de eigenschappen van de bot en **infereert automatisch** dat "GriefBot_v2" onder de klasse `RelationalCompanion` valt.

---

## Conclusie: Interoperabiliteit voor AI Governance

Wat Karman voorstelde voor het Jabes-raamwerk—het borgen van onmiskenbare administratieve feiten in een open, formele standaard—doen we hier voor de juridische en ethische status van AI.

Door de CPST-ontologie van het ORS-raamwerk te formaliseren in OWL, elimineren we de ambiguïteit in regelgeving. Toezichthouders en juridische systemen kunnen via een API direct bevragen of een systeem de grens van "Gereedschap" naar "Metgezel" is gepasseerd. Zodra de reasoner de classificatie `RelationalCompanion` afleidt, kunnen we in de software of in het rechtssysteem direct specifieke regels rondom *data-soevereiniteit*, *consent* en de menselijke waardigheid machinaal afdwingen.

De toekomst van AI-governance is niet slechts een kwestie van wetten schrijven op papier; het is een kwestie van de realiteit nauwkeurig, logisch en machinaal leesbaar modelleren. En daarvoor is een ijzersterke ontologie onmisbaar.
