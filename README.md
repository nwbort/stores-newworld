# Scheduled scraper

For New World store locations, via https://api-prod.newworld.co.nz/v1/edge/store
(the Foodstuffs API behind the store finder on https://www.newworld.co.nz/).

The script first gets an anonymous access token from
https://www.newworld.co.nz/api/user/get-current-user, then one request returns
every store with its address, coordinates, opening hours and online shopping
settings, so `fetch_stores.py` writes everything in a single daily run:

- `api-prod.newworld.co.nz-stores.json` — raw API response
- `newworld.co.nz-stores.json` — summary list (id, name, storeCode, region, city)
- `store-details/{id}.json` — one file per store
- `newworld.co.nz-store-details.json` — all store details combined
