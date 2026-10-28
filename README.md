# Reeturid

A party version of the Traitors game. Guests scan a QR code, get a secret role on their phone, and vote at round tables; the TV runs the show.

- **Play:** https://rolandsade-mvp.github.io/reeturid/
- **Host / TV screen:** https://rolandsade-mvp.github.io/reeturid/?host (open it on the laptop that is shared to the TV)

The game data lives in Supabase. The page only calls the game's own `reeturid_*` functions; roles are never sent to anyone else's phone or to the TV.
The database script is kept in the `claudefun` repository under `reeturid/supabase.sql`.
