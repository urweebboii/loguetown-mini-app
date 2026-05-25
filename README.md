# Loguetown Mini App

Public static hosting repo for the Loguetown Telegram Mini App.

The frontend is a plain static `index.html`. It calls the live Supabase API at:

```text
https://naoqksnzfculcajjxgiu.supabase.co/functions/v1/mini-app
```

## GitHub Pages

1. Create a public GitHub repo named `loguetown-mini-app`.
2. Push this repo to `main`.
3. In GitHub, open `Settings -> Pages` and set source to `GitHub Actions`.
4. The app URL should be:

```text
https://urweebboii.github.io/loguetown-mini-app/
```

After the page is live, set the Supabase secret:

```powershell
.\node_modules\.bin\supabase.cmd secrets set MINI_APP_URL=https://urweebboii.github.io/loguetown-mini-app/ --project-ref naoqksnzfculcajjxgiu
.\node_modules\.bin\supabase.cmd functions deploy telegram-poll --project-ref naoqksnzfculcajjxgiu
```

## Sync From Bot Repo

From `D:\loguetown-shop-bot`, run:

```powershell
Copy-Item -LiteralPath .\supabase\functions\mini-app\static\index.html -Destination .\mini-app-public\index.html -Force
```
