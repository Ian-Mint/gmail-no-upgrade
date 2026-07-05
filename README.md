# gmail-no-upgrade

Firefox extension that hides the **"Upgrade"** button in the Gmail header.

It's a content-script CSS rule — no JavaScript, no background page, no
permissions beyond running on `mail.google.com`. The rule matches stable
attributes (`data-pep-id`, `data-action-behavior`) rather than Gmail's
obfuscated, rotating CSS class names, so it keeps working across Gmail
updates and locales.

## Install (temporary, for testing)

1. Open `about:debugging#/runtime/this-firefox`
2. **Load Temporary Add-on** → select `manifest.json`

Temporary add-ons are removed when Firefox restarts.

## Install (permanent)

Install the signed build from addons.mozilla.org, or self-distribute a
signed `.xpi` (see below).

## Building / publishing

```sh
zip -q gmail-no-upgrade.zip manifest.json hide-upgrade.css
```

Submit `gmail-no-upgrade.zip` at https://addons.mozilla.org/developers/
(Developer Hub → Submit a New Add-on), or sign non-interactively:

```sh
npx web-ext sign --api-key=<AMO_JWT_ISSUER> --api-secret=<AMO_JWT_SECRET>
```
