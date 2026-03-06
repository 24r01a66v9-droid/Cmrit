<div align="center">
<img width="1200" height="475" alt="GHBanner" src="https://github.com/user-attachments/assets/0aa67016-6eaf-458a-adb2-6e31a0763ed6" />
</div>

# Run and deploy your AI Studio app

This contains everything you need to run your app locally.

View your app in AI Studio: https://ai.studio/apps/6d864116-f8d5-4a11-bda0-701b5cc5e8f3

## Run Locally

**Prerequisites:**  Node.js

1. Install dependencies:
   `npm install`
2. Set the `GEMINI_API_KEY` in [.env.local](.env.local) to your Gemini API key
3. Run the app:
   `npm run dev`

## Deploy on Render

1. Push this repo to GitHub and connect it to [Render](https://render.com).
2. Create a **Web Service**. If the app lives in a subfolder (e.g. `Cmrit`), set **Root Directory** to that folder.
3. Use:
   - **Build Command:** `npm install && npm run build`
   - **Start Command:** `npm start`
4. In **Environment** add:
   - `NODE_ENV` = `production`
   - `JWT_SECRET` = a long random string (required for auth)
   - `GEMINI_API_KEY` = your Gemini API key (if the app uses it)
   - Optional (for persistent DB/storage): `SUPABASE_URL`, `SUPABASE_ANON_KEY`
5. Deploy. The app will be available at the URL Render provides.

**Note:** On Render’s free tier, the SQLite file and `uploads/` folder are ephemeral (data can be lost when the service sleeps). For persistence, configure Supabase and set the env vars above.
