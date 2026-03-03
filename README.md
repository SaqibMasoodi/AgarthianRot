# AgarthianRot

A collection of experiments and functional front-end projects built with HTML, CSS, JS, and Backend-as-a-Service (BaaS) platforms.

## Features Included

*   **Notes & Blog:** A live, real-time message board built with **Firebase Firestore**.
*   **Image Gallery:** A public image upload system backed by **Supabase PostgreSQL** and **Supabase Storage**.
*   **3D Embeds:** Spline 3D object rendering.

## Local Setup

To run this project locally, you must provide your own API configurations. 

1. Clone the repository.
2. Create a `firebaseConfig.js` file in the root directory and export your Firebase configuration object.
3. Create a `supabaseConfig.js` file in the root directory and export your Supabase `url` and `anonKey`.
4. Open the site using a local development server (like VS Code Live Server) to prevent CORS errors with ES Modules.

## Deployment Details

This project utilizes Continuous Deployment via **Vercel**. 

To protect API credentials while still providing them to the live environment, the keys are stored remotely as Vercel Environment Variables (`FIREBASE_CONFIG_CONTENT` and `SUPABASE_CONFIG_CONTENT`). The `vercel.json` file handles automatically regenerating the `.js` files securely during the build step.
