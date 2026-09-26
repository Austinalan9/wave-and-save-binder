# Wave and Save · Binder

You tapped a 3D-printed keychain and it brought you here. That means it hasn't been set up yet. Setting it up takes about 15 minutes and you do all of it yourself. When
you're done, tapping the keychain opens **your** card collection instead of this page.

## 1. Copy this template (2 min)

1. Sign in to GitHub (free account is fine).
2. At the top of this page click **Use this template → Create a new repository**.
   Name it `binder`, keep it **Public**, click **Create repository**.
3. In your new repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: the only one listed (usually `main`), folder `/ (root)` → Save**.
4. Wait a minute, then open `https://<your-username>.github.io/binder/` on your phone.
   You'll see a sample binder. That's your page.

## 2. Put your cards in (as long as you want)

Everything on the page comes from **`cards.json`**. Edit it right here on GitHub (click the
file → pencil icon → Commit changes). One entry per card, grouped into pages of nine; `null`
is an empty pocket.

```json
{
  "phone": "",
  "pages": [
    { "game": "pokemon", "set": "Scarlet & Violet", "label": "Set 1 of 3",
      "cards": [
        { "name": "Charizard ex", "type": "fire", "set": "Scarlet & Violet",
          "num": "054/198", "cond": "NM", "price": 42.00,
          "holo": true, "photo": "cards/charizard-054.jpg" },
        null, null, null, null, null, null, null, null
      ] }
  ],
  "trades": { "have": [], "want": [] }
}
```

- `game`: `pokemon` or `palworld` — picks the tab.
- `type`: only chooses placeholder colors when a card has no photo: `fire water grass dark gold stone lightning psychic`.
- `holo: true` adds the shimmer. `price` shows on the card's detail sheet only; leave it out to hide prices.
- `phone`: optional. If filled, the Trades tab shows a "text me" box with it.
- **Photos:** upload to the `cards/` folder (**Add file → Upload files**), about 800 px on the
  long side, and reference them as `cards/<file>.jpg`. Filenames are case-sensitive.
- The page never shows a total for the binder. Anyone who taps sees cards, not what it's worth.

## 3. Point the binder at your page (3 min)

1. Install **NFC Tools** (free, Android or iPhone).
2. **Write → Add a record → URL** → paste your page address → **Write**, holding the phone
   flat against the binder's front cover (the tag is under the label).
3. Tap-test. Then **Other → Lock tag**. Locked means nobody can rewrite it; your page address
   never changes, so it costs nothing.

## 4. Adding cards later

Edit `cards.json`, upload photos, commit. The page updates in about a minute. The binder never changes.

## Optional: live prices

The Pokémon TCG API (pokemontcg.io, free key) returns TCGplayer market prices by set and card
number; a scheduled GitHub Action can refresh the `price` fields daily. Palworld cards have no
free price feed yet.

## If a tap doesn't read

- Android: NFC on (Settings → Connected devices). Hold the middle of the phone's back to the cover, slowly.
- iPhone: hold the top edge to the cover; tap the banner. Needs iPhone XS or newer.
- Thick or metal cases block NFC; try without the case once.

---
The binder, the page and this template are original work; the cards on your page are yours.
