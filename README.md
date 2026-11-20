# Novara Healthcare: Sugar Land TMS landing page

Google Ads landing page for TMS therapy at Novara Healthcare, Sugar Land, TX.

- `lp/tms/index.php`: landing page
- `lp/tms/thank-you.php`: thank-you page (fires the `lp_lead` conversion event)
- `lp/tms/_partials.php`: shared config (address, hours, GTM ID), header and footer
- `lp/tms/img/`: real clinic photos
- `build-lp.php`: renders the pages to static HTML in `dist-lp/`

## Build and preview

    php build-lp.php                     # → dist-lp/ and dist-lp.zip
    php -S 127.0.0.1:8090 -t dist-lp     # preview at http://127.0.0.1:8090/

Netlify runs `php build-lp.php` and publishes `dist-lp/` (see `netlify.toml`).
The enquiry form uses Netlify Forms (form name `tms-lp`).

## Tracking

Set `'gtm' => 'GTM-XXXXXXX'` in `lp/tms/_partials.php` to load Google Tag Manager with
Consent Mode v2 and the cookie banner. Use conversion tracking only, no remarketing
(Google doesn't allow remarketing audiences from mental-health pages).
