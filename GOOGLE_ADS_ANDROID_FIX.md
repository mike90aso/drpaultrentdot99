# Google Ads “Destination not working” (Android) — What to try

The site returns **HTTP 200** for both desktop and Android (and for Google AdsBot). If Google Ads still shows “Destination not working” on Android, try these in order.

---

## 1. Use this Final URL instead of the homepage

In your ad, set **Final URL** to:

**`https://sandiegodot.com/dot-physical`**

This path is set up to serve the same page with a 200 response. Many advertisers get approved when they use a path like this instead of the root URL.

---

## 2. Remove tracking template (temporarily)

- In Google Ads: **Ads & assets** → your ad → **Edit**.
- Check **Final URL**, **Tracking template**, and **Final URL suffix** at ad, ad group, campaign, and **account** level (Settings → Account settings → Tracking).
- If you use a **Tracking template** anywhere, remove it temporarily so the **Expanded URL** is the same as the Final URL.
- Save and wait for re-review. If the ad approves, the issue is likely the tracking URL; you can then reintroduce tracking step by step.

---

## 3. Use the exact URL format Google expects

Try **one** of these as the only Final URL (no extra parameters):

- `https://sandiegodot.com/dot-physical`
- `https://sandiegodot.com/dot-physical/`
- `https://sandiegodot.com/`

No `http://`, no `www`, no query strings. Use the one that matches how your site is set up (with or without trailing slash).

---

## 4. Confirm campaign type

- If this is an **App** campaign (app installs or app engagement), “Destination” and “Android” refer to the **app** and its store listing, not the website. The website URL is not the main destination.
- For **Search** or **Display** (website traffic), the destination is the web Final URL. Use the steps above.

---

## 5. Request a manual review (appeal)

If the destination is clearly working (e.g. you can open it on an Android phone in Chrome):

1. In Google Ads, open the ad with the disapproval.
2. Hover over the “Destination not working” status and note any **sub-reason** (e.g. redirect, 4xx, timeout).
3. Go to **Policy manager** (or the link in the disapproval) → find the violation → **Request review** / **Appeal**.
4. In the appeal, state that:
   - The URL returns HTTP 200 on desktop and Android.
   - You have tried the Final URL `https://sandiegodot.com/dot-physical` (or `https://sandiegodot.com/`).
   - You have removed tracking templates so Expanded URL = Final URL.
   - You request a manual check for the Android destination.

Re-review can take a few business days.

---

## 6. Check Netlify (optional)

- **Netlify dashboard** → your site → **Domain management**: ensure the custom domain is `sandiegodot.com` and HTTPS is enabled.
- **Build & deploy**: ensure the latest deploy (with `netlify.toml` and any redirects/rewrites) is **Published**.
- Do **not** enable “Bot protection” or similar features that might block or alter Google’s crawler.

---

## Summary

1. Set **Final URL** to **`https://sandiegodot.com/dot-physical`**.
2. Remove **Tracking template** (and optional **Final URL suffix**) until the ad approves.
3. If it still fails, **Request review** and mention that the URL returns 200 on desktop and Android.
