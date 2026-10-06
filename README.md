# Crown Logix 

Monorepo for the Crown Logix / Dzunani dispatch platform. Three independently
deployed projects share this repo.

| Folder | What it is | Deploys to |
|---|---|---|
| [`dispatch-edition/`](dispatch-edition/) | Dispatch + company/driver web portal (static HTML/CSS/JS). Supabase backend (project `fskttrjaonymqbscqhzw`). | Netlify (static drag-and-drop / static host) |
| [`dzunani-driver-app/`](dzunani-driver-app/) | Driver mobile app (Capacitor to Android). Wraps the web driver UI + native GPS/camera. | Android build (`.apk`) |
| [`tracker-gateway/`](tracker-gateway/) | GT06 hardware GPS tracker to Supabase `apex_locations` bridge. Zero-dependency Node TCP server. | Contabo VPS (systemd service `crown-tracker`) |

## Secrets

No secrets live in this repo. Each project reads them from the environment:

- `tracker-gateway/` — copy `.env.example` to `.env` and fill in the Supabase
  **service-role** key + `TRACKER_MAP`. The `.env` is git-ignored.
- Supabase edge functions read their secrets from the Supabase platform.




