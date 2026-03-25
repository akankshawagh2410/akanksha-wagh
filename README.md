# Akanksha Wagh — Personal Portfolio with Embedded AI Agent
 
🌐 **Live Site:** [My portfolio with AI-powered personal assistant](https://akankshawagh2410.github.io/akanksha-wagh/)

✍️ **Blog:** [I Built an AI Version of Myself and Added It to My Portfolio — Here’s How](https://medium.com/@akankshawagh/i-built-an-ai-version-of-myself-and-added-it-to-my-portfolio-heres-how-417468e9f30c)

🤖 **Try the AI Agent:** Open the site and click the **AW** button in the bottom right corner! 

---
 
## What is this?
 
This is my personal portfolio website — but with a twist. Instead of making visitors scroll through walls of text, I trained an AI agent on my entire profile and embedded it directly into the site. Visitors can just **ask it anything** about my experience, projects, skills, or education and get a real, conversational answer in seconds.
 
Oh, and there's a hidden game. Type **"play"** in the chat.
 
---
 
## Features
 
- **AI Chat Agent** — powered by Claude API, trained on my resume, projects, experience, and personality
- **2 Truths & 1 Lie Game** — interactive game with confetti for winners 🎉
- **Polaroid Photo Wall** — pinned graduation photos in the education section
- **Resume Download** — one-click PDF download
- **Scrolling Marquee** — tech stack and achievements strip
- **Custom Cursor** — navy dot with follower animation
- **Fully Responsive** — works on mobile and desktop
- **Scroll Animations** — fade-up reveals on scroll
 
---
 
## Tech Stack
 
| Layer | Technology |
|-------|-----------|
| Frontend | HTML, CSS, JavaScript (vanilla) |
| AI Agent | Anthropic Claude API (claude-sonnet) |
| Backend Proxy | Vercel Serverless Functions |
| Hosting | GitHub Pages |
| Fonts | Google Fonts (Playfair Display, DM Sans) |
 
---
 
## Architecture
 
```
GitHub Pages (Frontend)
        ↓
User asks a question in the chat
        ↓
Fetch call → Vercel Serverless Function (/api/chat.js)
        ↓
Vercel securely calls Anthropic Claude API
(API key never exposed in frontend code)
        ↓
Response returned to user in chat
```
 
### Why Vercel for the backend?
 
GitHub Pages only serves static files — it cannot store secrets or run server-side code. If the Claude API key is hardcoded directly in the HTML, GitHub's secret scanning detects it and Anthropic automatically deactivates it within seconds.
 
Vercel solves this by acting as a secure serverless backend. The API key lives in Vercel's environment variables (never in the code), and the frontend calls Vercel's endpoint instead of Anthropic directly. Safe, free, and takes about 10 minutes to set up.
 
---
 
## Project Structure
 
```
akanksha-wagh/
├── index.html              ← entire frontend (single file)
├── Akanksha_Wagh_Resume.pdf ← downloadable resume
├── photo.jpg               ← hero profile photo
├── grad1.jpg               ← polaroid photos (education section)
├── grad2.jpg
├── grad3.jpg
├── grad4.jpg
├── grad5.jpg
├── grad6.jpg
├── vercel.json             ← Vercel configuration + CORS headers
├── api/
    └── chat.js             ← Vercel serverless function (API proxy)

```
 
---
 
## Deploying Your Own Version
 
### Step 1 — Fork this repo
 
### Step 2 — Set up Vercel
1. Go to [vercel.com](https://vercel.com) and sign in with GitHub
2. Import your forked repo
3. Go to **Settings → Environment Variables**
4. Add `ANTHROPIC_API_KEY` = your Claude API key from [console.anthropic.com](https://console.anthropic.com)
 
### Step 3 — Update the fetch URL
In `index.html`, find the fetch call and replace the Vercel URL with your own deployment URL:
```javascript
const r = await fetch('https://YOUR-PROJECT.vercel.app/api/chat', {
```
 
### Step 4 — Enable GitHub Pages
Go to your repo → **Settings → Pages → Deploy from branch → main**
 
### Step 5 — Customize the AI agent
Find the `const CTX` variable in `index.html` and replace all of Akanksha's information with yours!
 
---
 
## Customizing the AI Agent
 
The AI agent's knowledge lives in the `CTX` constant in `index.html`. It includes:
 
- **WHO** — basic info, location, contact details
- **EDUCATION** — degrees, courses, awards
- **EXPERIENCE** — detailed descriptions of each role
- **PROJECTS** — all GitHub projects with descriptions
- **SKILLS** — full tech stack
- **PRESET ANSWERS** — specific answers for common questions (optional)
 
To make it yours, just replace the content in each section with your own information!
 
---
 
## Color Palette
 
| Name | Hex | Used For |
|------|-----|---------|
| Navy | `#213767` | Primary color, buttons, text |
| Lemon | `#fbedb0` | Accents, highlights |
| Gold | `#c8a94a` | Italic headings, links |
| Cream | `#fef9ec` | Page background |
| Lemon Pale | `#fffbee` | Hero background |
 
---
 
## Contact
 
- 📧 Email: [awagh2410@gmail.com](mailto:awagh2410@gmail.com)
- 💼 LinkedIn: [linkedin.com/in/akanksha-wagh-1963a722a](https://www.linkedin.com/in/akanksha-wagh-1963a722a/)
- ⌨️ GitHub: [github.com/akankshawagh2410](https://github.com/akankshawagh2410)
- ✍️ Medium: [akankshawagh.medium.com](https://akankshawagh.medium.com)
 
---
 
*Feel free to share any feedback or suggestions for improvement.*
