# ridehc.com — the RideHC site

Static pages for the App Store listing (task 1.12 in the app repo's
`docs/build-plan.md`): a landing page, the privacy policy and support.
Served by GitHub Pages at `https://ridehc.com/` (the `CNAME` file). No
build step, no framework: three HTML files and the brand badge.

## Publishing (once)

1. **GitHub:** create an empty public repository `ridehc-site` under the
   `d8cq6m7ywb-commits` account, then from this folder:
   `git remote add origin https://github.com/d8cq6m7ywb-commits/ridehc-site.git`
   and `git push -u origin main`.
2. **Pages:** repository Settings → Pages → Source "Deploy from a branch",
   branch `main`, folder `/ (root)`. Custom domain `ridehc.com`; tick
   "Enforce HTTPS" once the certificate is issued (a few minutes after DNS
   resolves).
3. **DNS at Name.com** for `ridehc.com`: replace the parking records with
   four `A` records at the apex — `185.199.108.153`, `185.199.109.153`,
   `185.199.110.153`, `185.199.111.153` — and a `CNAME` for `www` →
   `d8cq6m7ywb-commits.github.io`. GitHub documents these addresses under
   "Managing a custom domain for your GitHub Pages site".
4. Check `https://ridehc.com/privacy/` and `https://ridehc.com/support/`
   load over HTTPS; those two URLs go into App Store Connect.

## Before publishing

The contact address on both pages is `info@ridehc.com` (Name.com email
forwarding, set up 2026-10-25). The privacy page's "Last updated" date and
version line should match the release.

## Rules

The privacy page must describe what the shipped app does. If a version
adds any network feature (the Grepiac link, cloud sync, analytics), update
the page **before** that version is released and bump its date — and
change the App Privacy answers in App Store Connect to match.
