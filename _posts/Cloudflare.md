Libroot.org
over projects posts
Cloudflare Blocker, Firefox-extensie
Gepubliceerd op 28 september 2025

Cloudflare is een onweerstaanbare hub voor massasurveillance. Door zijn ontwerp is het een permanente Man-in-the-Middle, die de sleutels van het verkeer over grote delen van het internet vasthoudt. Cloudflare is in feite een gecentraliseerde kwetsbaarheidsfabriek.

We schreven een Firefox-extensie die elke website blokkeert met Cloudflare. Simpel als dat.

https://addons.mozilla.org/en-US/firefox/addon/cloudflare-blocker

Repo met bron: https://git.libroot.org/libroot/Cloudflare-Blocker.

Het inspecteert HTTP-headers.

Als Cloudflare-gerelateerde headers worden gedetecteerd, wordt het verzoek ter plekke gedood.

U krijgt een schakelaar in het pop-upmenu om het aan of uit te zetten.

Cloudflare wil een wereld normaliseren waarin "secure" standaard "MITM" betekent Dat is onaanvaardbaar. Deze verlenging maakt het compromis zichtbaar en geeft u de macht om het af te wijzen.


De code is er, gratis en open. Audit het, fork het, breek het, verbeter het.

https://git.libroot.org/libroot

Hier is een compleet, minimalistisch en functioneel ontwerp voor een webpagina die de **Cloudflare Blocker** introduceert, de filosofie erachter uitlegt en de technische werking (de headers en cookies) inzichtelijk maakt.

Het ontwerp is geschreven in pure HTML en CSS (ingebed), volledig responsive, en sluit qua esthetiek aan bij de minimalistische, open-source 'hacktivist'-stijl (donker thema, strakke schreefloze letters en duidelijke codeblokken).

Je kunt de onderstaande code kopiëren en opslaan als een `.html`-bestand (bijvoorbeeld `index.html`) om direct in Firefox of een andere browser te openen.

```html
<!DOCTYPE html>
<html lang="nl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cloudflare Blocker - Herover Digitale Autonomie</title>
    <style>
        :root {
            --bg-color: #0d1117;
            --text-color: #c9d1d9;
            --accent-color: #ff7b72;
            --card-bg: #161b22;
            --border-color: #30363d;
            --code-bg: #090d13;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            line-height: 1.6;
            margin: 0;
            padding: 0;
        }

        header {
            border-bottom: 1px solid var(--border-color);
            padding: 2rem 1rem;
            text-align: center;
            background: linear-gradient(180deg, #161b22 0%, #0d1117 100%);
        }

        h1 {
            color: #ffffff;
            font-size: 2.5rem;
            margin: 0 0 0.5rem 0;
        }

        .subtitle {
            color: var(--accent-color);
            font-family: monospace;
            font-size: 1.1rem;
            margin: 0;
        }

        main {
            max-width: 800px;
            margin: 2rem auto;
            padding: 0 1rem;
        }

        .manifesto {
            font-size: 1.15rem;
            border-left: 3px solid var(--accent-color);
            padding-left: 1rem;
            margin-bottom: 3rem;
            color: #f0f6fc;
        }

        h2 {
            color: #ffffff;
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 0.5rem;
            margin-top: 2.5rem;
        }

        .grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 1.5rem;
            margin-top: 1.5rem;
        }

        @media (min-width: 600px) {
            .grid {
                grid-template-columns: 1fr 1fr;
            }
        }

        .card {
            background-color: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 6px;
            padding: 1.5rem;
        }

        .card h3 {
            margin-top: 0;
            color: #f0f6fc;
            font-family: monospace;
        }

        code {
            font-family: ui-monospace, SFMono-Regular, SF Mono, Menlo, Consolas, Liberation Mono, monospace;
            background-color: var(--code-bg);
            padding: 0.2rem 0.4rem;
            border-radius: 3px;
            font-size: 0.9rem;
            color: #ff7b72;
        }

        pre {
            background-color: var(--code-bg);
            border: 1px solid var(--border-color);
            border-radius: 6px;
            padding: 1rem;
            overflow-x: auto;
        }

        pre code {
            padding: 0;
            background: none;
            color: #e6edf3;
        }

        .btn-container {
            text-align: center;
            margin: 3rem 0;
        }

        .btn {
            display: inline-block;
            background-color: #238636;
            color: #ffffff;
            padding: 0.75rem 1.5rem;
            border-radius: 6px;
            text-decoration: none;
            font-weight: bold;
            transition: background-color 0.2s;
            margin: 0.5rem;
        }

        .btn:hover {
            background-color: #2ea043;
        }

        .btn-secondary {
            background-color: #21262d;
            border: 1px solid var(--border-color);
            color: #c9d1d9;
        }

        .btn-secondary:hover {
            background-color: #30363d;
        }

        footer {
            text-align: center;
            padding: 2rem;
            border-top: 1px solid var(--border-color);
            font-size: 0.85rem;
            color: #8b949e;
            font-family: monospace;
        }
    </style>
</head>
<body>

    <header>
        <h1>Cloudflare Blocker</h1>
        <p class="subtitle">Breek de gecentraliseerde surveillance-hub af.</p>
    </header>

    <main>
        <section class="manifesto">
            <p><strong>Het internet is gebroken.</strong> Cloudflare fungeert als een permanente, gecentraliseerde <em>Man-in-the-Middle</em> die de sleutels van het verkeer over grote delen van het wereldwijde web vasthoudt. Dit normaliseert een wereld waarin "veiligheid" synoniem staat voor surveillance. Wij accepteren dit compromis niet.</p>
        </section>

        <div class="btn-container">
            <a href="https://addons.mozilla.org/en-US/firefox/addon/cloudflare-blocker" class="btn" target="_blank">Firefox Extensie Downloaden</a>
            <a href="https://git.libroot.org/libroot/Cloudflare-Blocker" class="btn btn-secondary" target="_blank">Broncode (Git)</a>
        </div>

        <h2>Hoe het werkt</h2>
        <p>De extensie is minimalistisch en compromisloos. Het inspecteert inkomende HTTP-headers via de browser-API. Zodra er een specifiek Cloudflare-kenmerk wordt gedetecteerd, wordt het netwerkverzoek onmiddellijk afgebroken. Geen tracking, geen compromis.</p>

        <pre><code>// De kern van de blokkade
chrome.webRequest.onHeadersReceived.addListener(
    function(details) {
        for (let header of details.responseHeaders) {
            if (header.name.toLowerCase() === 'server' && header.value.toLowerCase() === 'cloudflare') {
                return { cancel: true }; // Verzoek direct doden
            }
        }
    },
    { urls: ["&lt;all_urls&gt;"] },
    ["blocking", "responseHeaders"]
);</code></pre>

        <h2>De Vingerafdrukken van de Poortwachter</h2>
        <p>De extensie scant en filtert het verkeer op basis van de specifieke sporen die Cloudflare achterlaat op het netwerk:</p>

        <h3>1. HTTP Response Headers</h3>
        <div class="grid">
            <div class="card">
                <h3>Server: cloudflare</h3>
                <p>De meest directe indicatie dat een website fungeert als een reverse proxy binnen hun netwerk.</p>
            </div>
            <div class="card">
                <h3>CF-Ray</h3>
                <p>Een unieke 16-karakter hash gekoppeld aan de IATA-code van het datacenter (bijv. <code>-AMS</code>) dat uw data ontsleutelt.</p>
            </div>
            <div class="card">
                <h3>CF-Cache-Status</h3>
                <p>Geeft aan of de content via de lokale distributie-edge (HIT) of direct van de bronserver (MISS) komt.</p>
            </div>
            <div class="card">
                <h3>CF-Mitigated</h3>
                <p>Verschijnt zodra de infrastructuur een automatische JavaScript-uitdaging of browsercontrole afdwingt.</p>
            </div>
        </div>

        <h3>2. Geforceerde Cookies</h3>
        <div class="grid">
            <div class="card">
                <h3>__cf_bm</h3>
                <p>Geplaatst ten behoeve van 'Bot Management' om geautomatiseerd verkeer van menselijk verkeer te scheiden via surveillance.</p>
            </div>
            <div class="card">
                <h3>cf_clearance</h3>
                <p>Het digitale stempel dat bewijst dat u een interactieve uitdaging (CAPTCHA) succesvol heeft doorstaan.</p>
            </div>
        </div>
    </main>

    <footer>
        <p>De code is vrij, gratis en open. Audit het, fork het, verbeter het.</p>
    </footer>

</body>
</html>

```

### Wat deze pagina bevat:

1. **Heldere structuur:** Gebruik van semantische HTML5-tags (`<header>`, `<main>`, `<section>`).
2. **Responsive Grid:** De kaarten met headers en cookies schalen automatisch mee: ze staan onder elkaar op mobiel en netjes naast elkaar op grotere schermen.
3. **Geïntegreerde code highlighter:** Het JavaScript-voorbeeld is direct leesbaar opgemaakt in een donkere container die aansluit bij de rest van de pagina.
4. **Call to Actions:** Directe, opvallende knoppen naar de add-on store en de Git-repository.
