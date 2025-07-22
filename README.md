# 10–7.org

> **“Education is the kindling of a flame, not the filling of a vessel.”** — *Plutarch*
> 
> 10–7.org embraces this idea: it uses AI to spark understanding and compassion around the events of **Saturday, October 7, 2023** and the ongoing hostage crisis.  
>
> By weaving together verified facts, personal stories and data‑driven insights, the project aims to **illuminate dark corners of ignorance and hatred** and empower visitors to take meaningful action.

## Demo

The live application is available at **[10‑7.org](https://10-7.org)**.  
Feel free to explore the interactive timeline, AI educator and resource hub before diving into the codebase.

## Features

### 🎓 AI Educator

At the heart of 10–7.org is an **interactive ChatGPT‑powered assistant**.  
Visitors can select a role (student, parent, activist, etc.), describe a challenge or ask a custom question, and the AI returns trauma‑sensitive advice, historical context and calls to action tailored to their needs.  
Behind the scenes the frontend sends prompts to a server‑side API backed by OpenAI using a project API key and organisation ID.

### 📈 Impact Simulator

The “Allies Educated” calculator invites users to **visualise the ripple effect of education**.  
Adjust sliders for daily outreach and share‑forward rate, and watch as a monthly impact figure updates in real time.  
This playful tool conveys the exponential power of sharing knowledge.

### 💛 Hostage Advocacy

A dedicated section offers **actionable steps to support hostage families** – from wearing yellow ribbons to contacting representatives.  
The platform emphasises solidarity and provides clear ways for anyone to help.

### 📚 Educational Resources

Curated **lesson plans, teaching guides, videos and statistics** help educators and learners deepen their understanding.  
Resources cite organisations like the Anti‑Defamation League (ADL) and American Jewish Committee (AJC), and all materials are carefully vetted for accuracy and sensitivity.

### 🧭 Regional Antisemitism Insights

Users can enter a city or state to get **location‑specific data on antisemitic incidents**, coupled with suggestions for community action.  
This feature underscores that combating hate requires both global awareness and local engagement.

### 📄 Document Analysis

A secure upload form lets visitors submit PDFs, Word documents or plain text for **AI‑powered summarisation and historical context**.  
No files are stored; they are analysed on‑the‑fly and discarded.

### ⏱️ October 7th Timeline

An expandable timeline narrates key moments from the October 7th attack, pairing facts with educational prompts.  
Users can move at their own pace, exploring as much detail as they’re comfortable with.

### 📊 A/B Testing & Conversion Tracking

The site experiments with different call‑to‑action phrases and colours to **optimise engagement**.  
An internal `actionTracker` records anonymous events (without storing personal data) and could be wired to an analytics backend in production.

### 🧠 Accessible Design

From screen‑reader‑only labels to high‑contrast colour palettes and gentle scroll animations, accessibility is built into every page.  
The JavaScript includes debounced input handling, ARIA attributes and error states to guide users gracefully.

## Technology

- **Frontend:** vanilla HTML5/CSS3 with modern JavaScript.  Animations are powered by [Anime.js](https://animejs.com).  The site is fully static and can be served from any HTTP server.  
- **AI Integration:** The project uses the OpenAI API via a server‑side endpoint.  Environment variables (`OPENAI_API_KEY` and `OPENAI_ORG_ID`) keep credentials out of the client code.  
- **Serverless Functions:** Endpoints under `/api/` handle tasks like hostage count retrieval, latest news scraping, chat completion and CTA generation.  They can be run in a Node.js environment or deployed to serverless platforms (e.g. Vercel, Netlify or Cloudflare Workers).  
- **Analytics & A/B Testing:** A simple event tracker records actions and call‑to‑action variants using `localStorage`/`sessionStorage`.  In production you can connect this data to services like Google Analytics or PostHog.

## Getting Started

### Prerequisites

- **Node.js ≥ 18** and **npm** installed on your development machine.
- An **OpenAI API key** and **organisation ID** (create a free account at [openai.com](https://openai.com)).
- Optional: API keys for hostage news and antisemitism data if you intend to refresh those counters.

### Clone & install

```bash
# Clone your fork of the repository
$ git clone https://github.com/nnlevy/10-7-dot-org.git
$ cd 10-7-dot-org

# Install dependencies (if any)
$ npm install
