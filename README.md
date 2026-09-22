<div align="center">
<img width="1200" height="475" alt="GHBanner" src="https://ai.google.dev/static/site-assets/images/share-ais-513315318.png" />
</div>

# JAMB / UTME 2027 Master Prep Platform

A full-featured React + Gemini AI study platform for Nigerian UTME candidates covering Mathematics, Physics, Chemistry and Use of English.

View your app in AI Studio: https://ai.studio/apps/ffb7957e-0705-4b31-a59e-28d1cdf05dff

## Recent mature upgrades (2026-09)

- **Real progress calculation** — subject & topic mastery now derived from actual attempts, CBT results and open mistakes (no more hard-coded percentages).
- **Full attempt history** — every practice answer is stored (localStorage, last 2000) and drives readiness scores.
- **Expanded Chemistry syllabus** — 6 additional pillars (Periodic Table, Bonding, Gas Laws, Acids/Bases, Electrochemistry, Rates & Equilibrium) with lessons, traps and notes.
- **Larger question bank** — 44+ curated questions with step-by-step solutions, trap analysis and tags across all four subjects.
- **Chemistry Formula Vault & Traps** — mole relations, Ideal Gas Equation, pH, Faraday’s law + critical exam traps.
- **Cleaner baseline stats** — new users start at realistic zero so progress feels earned.

## Run Locally

**Prerequisites:** Node.js (18+)

1. Install dependencies:
   ```bash
   npm install --legacy-peer-deps
   ```
2. Copy `.env.example` → `.env.local` and set your `GEMINI_API_KEY`
3. Run the app:
   ```bash
   npm run dev
   ```

## Architecture notes

- Frontend: React 19 + Vite + Tailwind 4 + Motion
- Backend (dev): Express + `tsx` serving both API and Vite middleware
- AI: Google Gemini via `@google/genai` with model fallback chain
- Persistence: localStorage keys under `jamb2027_*` (stats, attempts, mistakes, CBT results, flashcards, bookmarks, plan)

## Key data files

| File | Purpose |
|------|---------|
| `src/data/subjects.ts` | Subject shells + Math/English topics |
| `src/data/physicsTopics.ts` | Full Physics syllabus pillars |
| `src/data/chemistryTopics.ts` | Full Chemistry syllabus pillars |
| `src/data/questions.ts` | Core verified + JAMB-style question bank |
| `src/data/topicQuestionBank.ts` | Hard-logic topic-specific questions |
| `src/data/formulas.ts` | Formula Vault |
| `src/data/traps.ts` | Common JAMB traps catalogue |
| `src/context/AppContext.tsx` | Global state, progress engines, persistence |

## Next recommended upgrades

1. Grow the question bank to 300–500+ items (or wire bulk AI generation more aggressively).
2. Flesh out remaining Mathematics & English topics to the same depth as Physics/Chemistry.
3. Real spaced-repetition scheduling in the Revision Centre.
4. Cloud sync / optional accounts so progress survives browser clears.
