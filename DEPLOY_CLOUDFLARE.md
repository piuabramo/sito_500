Guida rapida per pubblicare il sito su Cloudflare Pages

Opzioni possibili:

1) Cloudflare Pages (più semplice, hosting statico)
2) Cloudflare Workers + Wrangler (se vuoi più controllo / funzioni serverless)

A) Deploy su Cloudflare Pages (raccomandato per sito statico)
- Crea un account su https://dash.cloudflare.com se non l'hai già.
- Vai a Pages -> Create a Project -> Connect a Git repository (GitHub/GitLab/Bitbucket) e segui i passaggi.
- Branch: `main` (o scegli il branch corretto).
- Build settings: Per sito statico senza build, imposta:
  - Framework: "None"
  - Build command: (vuoto)
  - Build output directory: `/` o lascia vuoto a seconda del collegamento; puoi anche caricare direttamente i file tramite l'interfaccia.
- Conferma e deploya.

B) Deploy con Wrangler (Cloudflare Workers Sites)
- Installare Wrangler (Node.js richiesto):
  - `npm install -g wrangler`
- Accedere con il tuo account Cloudflare:
  - `wrangler login`
- Creare `wrangler.toml` (esempio fornito in questo repo).
- Eseguire `wrangler publish` dalla cartella del progetto.

Note su credenziali e DNS
- Per collegare un dominio personalizzato imposta il dominio in Pages o configura i record DNS nel pannello Cloudflare.
- Non includere token API o secret nel repository: usa le variabili d'ambiente/secret di Pages o Wrangler.

Esempio rapido (Cloudflare Pages): carica il repo su GitHub, connetti il repo a Pages e avvia il deploy; per modifiche future basta pushare sul branch configurato.

Se vuoi, posso:
- aggiungere un `wrangler.toml` esempio precompilato;
- creare un `package.json` con script di deploy via Wrangler;
- guidarti passo-passo nel collegare il repo GitHub al tuo account Cloudflare.
