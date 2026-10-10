# QSHIELD

The quantum security network for Solana. Static site: no build step.

## Structure

```
index.html      the site (HTML, CSS and JS in one file)
config.js       runtime settings (Solana RPC URL)
assets/         logo, favicon, social preview image
vercel.json     Vercel headers and clean URLs
```

## Run locally

Any static server works:

```
npx serve .
```

Then open http://localhost:3000. Wallet extensions (Phantom, Solflare, Backpack) need http://localhost or https, not file://.

## Deploy to Vercel

1. Push this folder to a GitHub repo.
2. In Vercel, click **Add New → Project** and import the repo.
3. Framework preset: **Other**. Leave build command and output directory empty.
4. Deploy.

Or from the terminal: `npx vercel --prod`.

## Production RPC

The public endpoint `api.mainnet-beta.solana.com` is rate-limited and may reject browser traffic under load. Put a dedicated RPC URL in `config.js` before launch. Lock that key to your domain in your RPC provider's dashboard, since anything in `config.js` is public.

## Social preview

`og:image` uses a relative path. After you have a domain, change it in `index.html` to the full URL (for example `https://qshield.xyz/assets/og.png`) so X and Telegram pick it up.
