

# De Illusie van Veiligheid: Hoe we de Regie Over Onze Data Vrijwillig Weggeven

We leven in een digitaal tijdperk waarin termen als *Security-by-Design* en *Privacy-by-Design* de beleidsnota’s sieren. Overheden en organisaties overbieden elkaar in beloften over databescherming en digitale soevereiniteit. Maar wie onder de motorkap van het moderne internet kijkt, ziet een heel andere, verontrustende realiteit. We hebben cybersecurity platgeslagen tot een gemakscultuur. In ruil voor bescherming tegen DDoS-aanvallen en server-overbelasting hebben we een monster gecreëerd: de normalisatie van de permanente **Man-in-the-Middle (MITM)**.

De architectuur die bedoeld was om ons te beschermen, is veranderd in een gecentraliseerde kwetsbaarheidsfabriek. En de overheid? Die staat vooraan in de rij om aan te sluiten.

---

## 1. De Mythe van 'Zero-Knowledge' en het Sleutelprobleem

Het fundamentele probleem begint bij de vraag: **wie beheert de sleutels van de voordeur?** Neem de discussies rondom de e-maildienst Zivver, een platform dat door menig overheidsinstantie (en zelfs de Kiesraad) wordt gebruikt voor "veilige communicatie". De marketing belooft *zero-knowledge encryption*. Maar kritische experts stelden de enige vraag die er echt toe doet: *Waar worden de encryptiesleutels gegenereerd en beheerd?*

Het antwoord legt de pijnlijke waarheid bloot. Dit gebeurt op de servers van de dienstverlener zelf, draaiend op de infrastructuur van Amazon Web Services (AWS). Zodra een Amerikaanse techgigant de infrastructuur beheert en de sleutels beheerd worden door een derde partij, vervalt de claim 'zero-knowledge'. Onder wetgeving zoals de Amerikaanse **CLOUD Act** kunnen deze partijen via juridische weg worden gedwongen om toegang te verlenen tot data of sleutels.

Wanneer we een *trusted third party* tussen onze communicatie laten zitten, is er geen sprake meer van end-to-end beveiliging. Het is een gecentraliseerd risico, verpakt als een veilige oplossing.

---

## 2. De Ironie van de Poortwachter: Overheidsinformatie Achter Slot en Grendel

Hoe ver deze afhankelijkheid gaat, blijkt wel uit de praktijk van onze eigen vitale infrastructuur. Cloudflare, de grootste content delivery network (CDN) en DDoS-beveschermer ter wereld, functioneert vandaag de dag als de de facto poortwachter van het internet. Al het verkeer naar een website die Cloudflare gebruikt, wordt daar ontsleuteld, geïnspecteerd en opnieuw versleuteld. Een schoolvoorbeeld van een MITM-opzet.

De ironie wordt pijnlijk tastbaar wanneer we kijken naar de **Informatiebeveiligingsdienst (IBD)** van de Nederlandse gemeenten—de instantie die nota bene handreikingen schrijft over hoe gemeenten hun cybersecurity (zoals ENSIA) moeten inrichten. Wat blijkt? Hun eigen website leunt op de infrastructuur van Cloudflare.

Het resultaat? Burgers en professionals die legitiem toegang zoeken tot openbare overheidsinformatie worden regelmatig geconfronteerd met de beruchte Cloudflare-muur:

> *"Attention Required! | Cloudflare [...] Sorry, you have been blocked."*

Een commercieel, Amerikaans techbedrijf beslist hier dus autonoom of een Nederlandse burger toegang krijgt tot informatie van de Nederlandse overheid. Dit is geen incidentele fout; dit is een fundamenteel verlies van digitale soevereiniteit.

---

## 3. De Tegenbeweging: Decentralisatie en Digitale Autonomie

Het accepteren van "secure = MITM" is een gevaarlijk compromis. Gelukkig groeit het besef dat het anders moet. We zien een parallelle beweging ontstaan waarin soevereiniteit weer centraal staat:

* **Het Fediverse & Mastodon:** Grote media-instanties, zoals het NRC, en overheden experimenteren met eigen Mastodon-servers. Het doel? Losbreken van de algoritmes en de infrastructuur van Big Tech, om weer zélf de regie te voeren over data en bereik.
* **Individuele Weerbaarheid:** Initiatieven zoals Firefox-extensies die Cloudflare-interceptie simpelweg blokkeren of omzeilen, zijn geen uitingen van internet-anarchisme. Het zijn digitale noodremsen. Ze geven de gebruiker de macht terug om te zeggen: *ik ga niet akkoord met een verplichte derde partij tussen mijn verbinding.*

---

## Conclusie: Tijd voor een Echte Digitale Soevereiniteit

De overheid en de IT-sector moeten stoppen met het belijden van *Privacy-by-Design* met de mond, terwijl ze in de praktijk kiezen voor het gemak van gecentraliseerde clouddiensten. Als we de controle over onze encryptiesleutels en ons dataverkeer uitbesteden aan partijen buiten onze eigen jurisdictie, beschermen we onszelf niet. We maken onszelf juist chantabel en kwetsbaar op één centrale plek.

Het is tijd om de architectuur van ons digitale huis te heroverwegen. Echte veiligheid vereist dat we de sleutels in eigen zak houden.
