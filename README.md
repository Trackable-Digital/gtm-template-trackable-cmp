# Trackable CMP: Google Tag Manager template

The web tag template for [Trackable CMP](https://trackable.digital/cmp), a cookie banner with
Google Consent Mode v2.

## What it does

Fire it on **Consent Initialization - All Pages**. Before any other tag it:

1. sets the Consent Mode default for each region in your table, plus a default for everywhere else
   (nothing in the table: everything denied);
2. for a returning visitor, sends their saved choice as the only default, then the same state as an
   update;
3. sets Microsoft UET consent, and optionally ads data redaction, URL passthrough and the developer ID;
4. in US rows, starts analytics and marketing as denied: GTM cannot read Global Privacy Control, so the banner allows them a moment later for visitors who do not send it;
5. loads the Trackable CMP banner, which records every choice and sends each change to Google.

If the Trackable CMP snippet is already in the page's `<head>`, the tag does nothing.

## Setting it up

1. In the Trackable CMP dashboard, open **Install → Use Google Tag Manager**. The one-click option
   adds this template, the tag and the triggers to a new workspace for you.
2. To set it up by hand instead, add the template from the Community Template Gallery, create a tag,
   and paste the **Loader address** from the dashboard
   (`https://cmp.trackable.digital/l/<your-site-key>.js`, with `?so=1` if your site routes `/_tc/`
   to Trackable CMP).
3. Copy your default consent table from the dashboard (Settings → Before a visitor chooses) into
   **Default consent by region**.
4. Publish, then check in Tag Assistant's Consent tab.

## Privacy

The tag reads one cookie, `tc_consent` (the visitor's saved choice) and writes nothing to the
device. Its only request is the banner script from `cmp.trackable.digital`; the banner stores a
choice only once the visitor makes one.

## Licence

Copyright 2026 Trackable (trackable.digital). Apache 2.0, see `LICENSE`.
