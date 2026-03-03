# Project Learnings: AgarthianRot

## 1. Vercel Deployment
- **Goal:** Host static HTML/CSS/JS files for free.
- **Process:** Link Vercel account to GitHub repository.
- **Result:** Vercel automatically deploys the `main` branch to a live URL (`.vercel.app`).

## 2. CI/CD (Continuous Integration / Continuous Deployment)
- **Concept:** Automating the deployment process.
- **Workflow:** 
  1. Write code locally.
  2. `git push` to GitHub.
  3. Vercel detects the push and automatically rebuilds/redeploys the live site.
- **Benefit:** No manual server uploads or FTP needed. Code changes go live instantly.

## 3. Firebase (Notes & Blog)
- **Use Case:** simple, real-time NoSQL database (Firestore).
- **Setup:**
  - Create project & Firestore database (Test Mode).
  - Get SDK configuration (`firebaseConfig`).
- **Implementation:**
  - Import Firebase modules via CDN.
  - Use `addDoc()` to save data to a collection (`notes`).
  - Use `onSnapshot()` to fetch and display data in real-time.
- **Security:** Placed config in an external file (`firebaseConfig.js`) and added it to `.gitignore` to keep API keys off GitHub.

## 4. Supabase (Image Gallery)
- **Use Case:** Relational PostgreSQL database + File Storage.
- **Setup:**
  - Database: Created `gallery` table (`id`, `title`, `image_url`, `created_at`).
  - Storage: Created a **public** bucket `gallery-images`.
- **Implementation:**
  1. **Upload:** Send image file to Storage bucket -> get `Public URL`.
  2. **Database:** Save the image title and the `Public URL` to the `gallery` table.
  3. **Read:** Query the table and inject `<img>` tags.
- **Security (RLS):** By default, Supabase blocks uploads. Created a Storage Policy allowing `INSERT` access for all (`true`) to allow public gallery uploads.
