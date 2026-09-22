# J SafeZ Aesthetics - Lead Form Page

A single-purpose lead capture page: their real logo, real tagline, real
contact details, and the Salesforce Web-to-Lead form. Nothing invented -
branding and copy are pulled directly from their existing site
(safez-aesthetics-clinic.netlify.app, linked from their Instagram bio).

Plain HTML/CSS/JS - no build step, no framework.

## Structure

```
index.html        The consultation-request page (logo, tagline, lead form)
thank-you.html     Shown after a successful submission
css/style.css      Styling (colors/fonts matched to their existing site)
js/script.js       Footer year
assets/logo.jpeg   Their real logo, pulled from their existing site
```

## Run locally

```bash
npx serve .
```

## ⚠️ Before going live - reCAPTCHA

The form uses Salesforce's placeholder site key (`"test"`) in two spots in
`index.html` (search for `"test"`). This shows an "Invalid site key" error
on any real domain. Get a real reCAPTCHA v2 site key from
[google.com/recaptcha/admin](https://www.google.com/recaptcha/admin)
registered to your live domain, and swap both `"test"` values for it.

## What's real vs. what changed

- Logo, colors (cream/dark-brown/gold), fonts (Cormorant Garamond +
  Montserrat), address, email, WhatsApp number, and working hours are all
  copied directly from their existing site - not invented.
- The "Interested Treatment" field is now a dropdown using their real
  service categories (Skin Care, Hair Treatment, Laser Treatment, PMU,
  General Consultation, Other) - same list as their existing site's form.
- The only intentional change from the original snippet: `retURL` points to
  `thank-you.html` on this site instead of their Instagram profile, so
  submitters get a proper thank-you page. Update the domain in `retURL`
  once deployed if it differs from `safez-aesthetics.vercel.app`.

## Deploy

Static site - push to GitHub, import at
[vercel.com/new](https://vercel.com/new), framework preset "Other", no
build command, deploy.
