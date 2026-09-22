# Safe Z Aesthetics - Landing Page

Single-page marketing site for Safe Z Aesthetics (Skin | Hair | Aesthetic | PMU
clinic, Coimbatore) with an embedded Salesforce Web-to-Lead form.

Plain HTML/CSS/JS - no build step, no framework, no dependencies to install.

## Structure

```
index.html        Main landing page (hero, services, why-us, lead form)
thank-you.html     Shown after a successful lead form submission
css/style.css      All styling
js/script.js       Mobile nav toggle + footer year
assets/favicon.svg Site icon
```

## Run locally

```bash
npx serve .
```

## ⚠️ Before you go live - 2 things to fix

1. **Replace the reCAPTCHA test key.** The form currently uses Salesforce's
   placeholder site key (`"test"`) in two places in `index.html`:
   - `<input type="hidden" name="captcha_settings" value='{"keyname":"test",...}'>`
   - `<div class="g-recaptcha" data-sitekey="test">`

   This will not reliably protect the form (or may not render at all) on a
   real domain. Get a real reCAPTCHA v2 ("I'm not a robot" checkbox) site key
   from [google.com/recaptcha/admin](https://www.google.com/recaptcha/admin),
   register your live domain, and swap both `"test"` values for your real
   site key.

2. **Fill in real contact details.** Search `index.html` for:
   - `Add your clinic phone number here` (appears twice)
   - `Add your clinic email here`
   - `Add your working hours here`

   Replace with your real numbers/hours. The address is filled in from the
   JustDial listing (Opp. Annapoorna, Saibaba Colony, Coimbatore) - double
   check it's exact.

## What the lead form does

It's your original Salesforce Web-to-Lead form (org ID, field names, and
`captcha_settings` untouched) restyled to match the site and wrapped with
better labels. One change: `retURL` now points to `thank-you.html` on this
site instead of your Instagram profile, so visitors get a proper "thank you"
page after submitting. Update the domain in `retURL` once deployed if it
changes from `safez-aesthetics.vercel.app`.

## Deploy

Static site, deploys anywhere (Vercel, Netlify, GitHub Pages). For Vercel:
push to GitHub, import the repo at [vercel.com/new](https://vercel.com/new),
framework preset "Other", no build command - deploy.
