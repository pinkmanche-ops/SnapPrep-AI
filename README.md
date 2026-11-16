# Snap Prep AI — deployable website

An independently built Snap Prep-style student study app, based on the visible screenshot and feature descriptions. It is **not** the original creator's source code or an exact copy. The interface works right away; AI responses need a Gemini key on Vercel.

## Deploy on Vercel (recommended)

1. Unzip this folder. Upload the **folder's contents** to a new GitHub repository (your own repo, not the original author's).
2. At https://vercel.com/new choose **Import Git Repository**, select the repo and click **Deploy**. Leave framework preset at **Other** and root directory as the repo root. No build command needed.
3. Go to **Vercel Project → Settings → Environment Variables**. Add `GEMINI_API_KEY` with a Gemini API key from https://aistudio.google.com/apikey. Enable Production (and Preview if desired).
4. In **Deployments**, redeploy after adding the key. Open the *.vercel.app URL.

Do **not** put API keys in index.html, the repository, or any browser-facing code. This app sends prompts/photos to your server endpoint which calls Gemini. Image uploads are not stored by this code. The **Saved** tab stores data only in that browser (localStorage) and is not account-based.

## Features

- Solver: camera/file upload, direct answer, hint, step-by-step explanation
- AI Unit: conversational tutoring
- Cards: AI-generated flashcards
- Quizzes: practice questions and answer key
- Saved: local saved results
- Pricing: preview Free/Pro/Premium cards **only**; no charges, Stripe, authentication, subscription enforcement, or multiuser saved records. Do not advertise paid accounts as functional until implemented.

## Important before public launch

Set usage limits, abuse protection/rate limiting, server-side account authentication, a database, consent/privacy terms and costs/billing safeguards before distributing widely or enabling subscription charges. Review the project with the original app's owner before using their trademarks or protected branding.

## Test

Open index.html directly to inspect the interface. AI requests will only work after deploying because `/api/generate` is server-side. Use the AI features on the Vercel URL after adding the key.

## New welcome flow / logo

On first visit, students answer four onboarding questions and choose Free ($0), Pro ($3.99/mo), or Premium ($7.99/mo). These preferences are stored locally in that browser. The plan selector is demonstrational only: it **does not** bill, verify subscriptions, or give users paid entitlements. Click the plan badge to view plans again. The supplied Snap Prep AI logo is included with a transparent background.
