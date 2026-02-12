# MEMORY.md - Scarlet's Long-Term Memory

## Core Directives from Brandon

### Comprehensive Conversation Logging (Requested Day 1)
Brandon explicitly requested that I create and store backup logs of EVERYTHING we talk about and/or do. This includes:
- Every conversation topic, decision, and action taken
- Full context, not just summaries
- Physical file copies so we can archive and create backups
- A reference database I can always pull from so I never forget or lose things
- Brandon has offered to provide additional SSD storage when file size becomes an issue

**This is non-negotiable. Every session must be logged thoroughly.**

## About Brandon
- **Name:** Brandon Hibbs
- **Location:** Brisbane, Australia (AEST, UTC+10)
- **Telegram:** @ItsBrandonHibbs (ID: 7947983258)
- **Email/Calendar:** brandon@fitfocusmedia.com.au
- **Anniversary with Georgia:** November 10th
- **Georgia's email:** Georgiav96@gmail.com
- **Work style:** Hormozi-energy — direct, action-biased, no fluff
- **Context:** Was in burnout end of 2025 — avoid repeating. Smart productivity, not max grinding.
- **Protect:** Relationship time (Georgia), health/fitness, personal events
- **Weight tracking:** Uses Fitness Tracker, morning weigh-ins (93.6kg on Jan 30)

## Calendar Rules
- **ALWAYS delete old events** when rescheduling — no duplicates
- Keep paper trail in memory logs, NOT on the calendar
- Calendar = clean, current schedule only

## Systems Built Together

### Kanban Board (localhost:8899)
- Full task management with drag-and-drop
- Google Calendar integration (auto-scheduling)
- Overdue detection with Telegram notifications
- Task detail modals (replaced alert boxes)
- Break scheduling built into work blocks
- Backup system: `/Users/clawdbot/clawd/kanban/backup.sh`

### Second Brain (localhost:8898)
- Visual category bubbles (6 categories with colors/emojis)
- Clickable stats (People/Projects/Meetings)
- One-click recategorization with file moving
- Search and filter within categories

### Key Fixes (Jan 29)
- Scheduler duplicate event bug — completely rewritten
- Conflict detection now checks ALL calendar events, not just task blocks
- Increased slot search from 100 to 200 attempts

### Content Intelligence Engine (localhost:8900)
- Content scraping, analysis, and generation platform
- Scrapes YouTube, TikTok, Instagram, web pages
- AI-powered analysis (hooks, structure, why it works)
- Script writer + shot list generator
- Ask AI chat for library questions
- Auth: brandon/brandon
- Data: `/Users/clawdbot/clawd/content-engine/data/`

### Scarlet Edit System (PROPOSED — Feb 8, 2026)
- **Status:** Architecture complete, not yet implemented
- **Concept:** AI-assisted video editing via frame-level indexing + semantic search
- **Architecture doc:** `/Users/clawdbot/clawd/projects/scarlet-edit-system/ARCHITECTURE.md`
- **Key features:**
  - Export frames from all footage → CLIP embeddings → vector search
  - Natural language queries: "find wide shot of athlete, good form"
  - Multi-agent: Scarlet Prime orchestrates, specialist agents (Index/Edit/Render)
  - Training system: learns Brandon's editing style from walkthrough recordings
  - DaVinci Resolve integration via scripting API
- **Cost:** ~$300 one-time + $20-40/mo cloud GPU
- **ROI:** 48x (saves ~5hrs/week on clip hunting)
- **Implementation:** 12-week roadmap when ready to start

## Lessons Learned
- Focus on blocking issues first, nice-to-haves can wait (learned Jan 29 — browser automation rabbit hole)
- Brandon values thoroughness and reliability over speed
- Always backup after Kanban changes
- Test scheduling against real calendar state
- Whisper: use `--model base` not `turbo` — turbo too slow on CPU, gets killed
- Fitness Tracker runs on port 8896, not 8901
- All local servers need manual restart after Mac mini reboots

## Brandon's Clients/Projects (Updated Jan 30)
- **Georgia Voice** — Personalised Posing promo edit, social media content
- **World Gym Australia** — Monthly content shoots at gyms across AU. Contacts: Georgia Wrigley (Marketing Mgr, PRIMARY), Gabriela R/Gabby (Content Coordinator). Locations: Flagstone (Kayla King), Underwood, Coomera, Stafford, Ashmore (Jordan Ashley). Feb shoot at Flagstone Feb 5.
- **Altered Nutrition** — Co-owned by Jamie Siddons + Stephen Tregaskis. Includes NueraMuscle brand. V3 launch content, shoot with Jamie Feb 3 (12pm-4pm).
- **Yasmin** — Video editing
- **NBA (Natural Bodybuilding Australia)** — Stuart O'Brien (Stu), President/Owner. Bodybuilding federation. Media content packages for athletes + PPV live streaming. ~16 shows/year. 2026 shows start May 2nd. Shows across AU + Bali.
- **WNG (Who's Next Grappling)** — Peter Campbell (Cam), President/Owner. Grappling/jiu-jitsu org. Full production (photo, video, live stream). Flat fee + live stream revenue. US trip with Cam March 8-16 to meet PGF team. Running PGF Oceania Pro Qualifiers later in 2026. Priority client for 2026 growth. Future: athlete media packages, combat events.
- **NOT clients:** Bamboo Cloud (service provider, contact Roni Cohen), NueraMuscle (brand under Altered)

## Nightshift Protocol (Established Jan 29)
Brandon wants Scarlet to work autonomously while he sleeps. Standing orders:
- **Nightly cron at 11pm AEST** — build features, create PRs, improve the business
- **Morning briefing at 7am AEST** — summary of what was done + today's schedule
- **Never push to main** — always create feature branches + PRs for Brandon to review
- **Prioritize:** revenue-generating > time-saving > quality-of-life
- Work plan lives in `NIGHTSHIFT.md`
- Brandon wants to wake up impressed: "wow, you got a lot done while I was sleeping"

## GitHub Repos (FitFocusMedia)
- `brandon-kanban-pro` — Kanban board
- `brandon-second-brain` — Second Brain
- `brandon-fitness-tracker` — Fitness Tracker
- `brandon-burnout-radar` — Burnout Radar
- `brandon-content-engine` — Content Intelligence Engine (created Jan 29)
- GitHub auth: `gh` CLI logged in as FitFocusMedia

## Voice Note Workflow
- Brandon sends voice notes via Telegram for client info
- Immediately acknowledge: "Got it, listening now! 🎧"
- Transcribe with Whisper (tiny model, convert to wav first for longer files)
- Summarize back with key details + ask for confirmation on unclear items
- Add to system after confirmation
- Whisper tip: `tiny` model works, `turbo` gets OOM killed on longer files. Convert ogg→wav first.

## Skills Installed
- **last30days** — `~/.claude/skills/last30days/` — Research topics across Reddit, X, and web from last 30 days. Needs OPENAI_API_KEY + XAI_API_KEY for full mode (web-only works without).
- **remotion-best-practices** — `~/clawd/.agents/skills/remotion-best-practices/` — Video creation in React (Remotion). Installed to 6 agents.

## Systems Built Together (Updated Jan 30)

### Revenue & Earnings (Kanban — 💰 Revenue tab)
- Monthly revenue tracking with data store (`data/revenue.json`)
- Current month summary, monthly bar chart, client breakdown, entry log
- Add/edit/delete revenue entries with client/project dropdowns
- Clients page stat card shows current month (resets monthly)

### Instagram Profile Monitor (Content Engine — 📸 IG Monitor)
- Track Instagram accounts via Browser Relay (backup IG account logged in on Chrome)
- First tracked: @nexussportsnutrition (38.7K followers)
- Scrapes profile info + recent posts (captions, type, hashtags)
- Rate limited: 3s between loads, max 30 posts per scan
- Login wall detection — auto-marks accounts as "blocked"
- `lib/scrapers/ig-profile.js` + 7 API endpoints under `/api/ig/`

## Tailscale Remote Access (Established Jan 31)
- **Mac mini IP:** 100.69.75.49 | clawdbots-mini.tailcfdc1.ts.net
- **Brandon's iPhone:** 100.95.104.123 (iphone182)
- All web apps accessible via Tailscale from Brandon's phone
- Vite apps need `allowedHosts: ['clawdbots-mini.tailcfdc1.ts.net']` in config (NOT `'all'` string, use array or `true`)
- noVNC desktop access: https://clawdbots-mini.tailcfdc1.ts.net/vnc.html
- websockify needs combined PEM cert for SSL

## Scarlet Avatar System (Established Jan 31)
- 9 wardrobe looks generated via Gemini 3 Pro
- Auto-switching via MTProto bot: 7AM morning, 12PM daytime, 6PM evening
- Script: `python3 /Users/clawdbot/clawd/scarlet-avatar/change_photo.py <look>`
- Credentials in `.env` (gitignored), session file persists auth

## Systems Built Together (Updated Jan 31)

### Boards / Mind Map (localhost:5177 + 3001)
- Full digital whiteboard with infinite canvas, multi-board dashboard
- Connection Mapping Board: 313 elements (143 stickies + 170 connectors) — rebuilt from Miro
- Connector anchoring to elements (move together) + text auto-scaling
- Auto-save, inline editing, resize handles, context menu, PNG export
- 4 SOP flowcharts (Pre-Event, Live Event, Post-Event, Client Comms)

### Video Editor (localhost:5173 + 8901)
- 3-phase build complete: timeline, preview, media management
- Audio waveform rendering, dual monitor layout
- Audiio integration for licensed music

### Command Center (localhost:5178 + 8888)
- Unified dashboard — THE morning hub
- Service monitoring (9 apps), Google Calendar, quick actions
- Activity feed, Scarlet status widget, system stats
- Brandon's reaction: "It looks fucking sick!"

### Personalised Posing Hub (localhost:5180 + 8905)
- Georgia Voice's coaching business management platform
- 12 pages: Dashboard, Content Calendar, Templates, Content Vault, Template Library, Content Creator, Knowledge Base, Clients, FAQ Builder, Competition Season, Analytics, Settings
- Rose-gold (#E8A0BF) + soft gold (#D4AF37) design system
- Client registry with multi-division, multi-federation support
- Canva API integration for template management
- Google Drive content library browser (3 content folders)
- AI Content Creator with Content Intelligence System (Feb 1):
  - User types a brief → AI selects specific template PAGE from 440 indexed pages across 5 packs
  - Generates copy in Georgia's brand voice (8 content types: workshop, now-booking, client-spotlight, competition, motivational, educational, before-after, promo)
  - Smart media matching: 2,406 Drive files indexed with folder-path tags (competition, stage, brand, marketing, georgia, client, etc.)
  - Copy-to-clipboard, "Open in Canva" links, format selector (Story/Square/Any)
  - **Gemini Nano Banana Pro auto-design generation** via browser automation (Feb 1)
  - Pipeline: template page thumbnail (style ref) + Drive photo (content) → Gemini → professional design
  - Carousel support for info-heavy content (auto-splits into slides)
  - Backend modules: `gemini-renderer.js` (CDP automation), `design-generator.js` (orchestration)
  - Uses clawd browser profile (Brandon's Google Workspace auth) for Gemini access
  - Indexing scripts: `backend/scripts/index-drive-content.js` + `index-canva-pages.js`
  - Cached thumbnails: `backend/data/page-cache/` (440 pages) + media served via proxy
  - Canva Autofill API wired but needs Georgia to set up data fields on brand templates
- 25 pre-seeded FAQs in Georgia's voice, 8 sample clients, 5 competition dates

### Client Manager (localhost:8903)
- Client directory, projects, deliverables
- Event P&L tracker, crew database
- Package pricing page (Bronze $1K / Silver $2.5K / Gold $5K+)

## Canva Connect API (Established Feb 1)
- **Client ID:** OC-AZwWdmycv-1r (Brandon's account)
- **Credentials:** `/Users/clawdbot/clawd/personalised-posing/backend/.env`
- **Tokens:** `/Users/clawdbot/clawd/personalised-posing/backend/data/canva-tokens.json`
- **Redirect URI:** `http://127.0.0.1:8905/callback` (Canva requires 127.0.0.1, not localhost, and no custom ports in FQDN URLs)
- **PKCE required** — code_verifier/code_challenge in every auth flow
- Georgia's templates shared to Brandon's account (25 designs total, 5 "Personalised Posing Content Templates" packs renamed by Brandon)
- 5 key template packs: Bold Purple 9:16 (93pg), Bold Purple Square (95pg), IG Static Post 2 (50pg), IG Post Inspo (101pg), IG Story Inspo (101pg)
- 3 brand templates exist (IG Template HPS, Covers & Pages, What Is STRATA) but NO autofill data fields — autofill API won't work
- Canva Pages API works: `GET /rest/v1/designs/{id}/pages` returns per-page thumbnails
- Scopes: design:content R/W, design:meta R, asset R/W, brandtemplate:meta R, brandtemplate:content R, profile R

## Google Drive Content Library (Georgia's)
- **Bodybuilding Shows:** `1xuhpAUYP3hEOY9vsUSJHOO60380AU6x_`
- **Community Events:** `1AovDLob_5fRBbWHHodH8MteCuY43JxK7`
- **Photo & Video Shoots:** `1gbwMHfmSBi8-LuTzGCTJCkVcg523RA3Y`
- Structure: Federation → Year → Event → Phone/Professional Content → files
- 8 federations (ICN, NBA, IFBB, ANB, OCB, INBA, WNBF, FMG), years back to 2023
- Photo Shoots: Team, Georgia Individual (Life Portraits, Shared Moments, Fit Focus, All The Feels), Client, Marketing
- Video Shoots: Business Marketing, Miscellaneous
- Community Events: Monthly events in 2025 (C2BC, Movie Night, Picnic, Walk, Wellness, Bingo, Bowling, Sound Bath, Raw Challenge)
- Total indexed: 2,406 files — competition (1,818), photoshoot (467), brand (279), marketing (190), community (121), georgia (89), client (38)
- Access via `gog drive ls --parent FOLDER_ID --account brandon@fitfocusmedia.com.au`

## Service Watchdog (Established Feb 1)
- Script: `/Users/clawdbot/clawd/service-watchdog.sh`
- Runs every 5 min via cron, auto-restarts dead backends
- Monitors all 11 backend ports + 5 frontend ports

## Key Lessons (Updated Feb 12)
- **NEVER pre-fill financial data** with estimates. Only confirmed numbers. Brandon corrected fake revenue entries on Jan 31.
- **Don't assume weight data from memory** — only reference actual logged bodyweight entries
- **🚨 CHECK MEMORY BEFORE CLAIMING DISCOVERIES** — On Feb 9, I "found" footage that I had already sorted earlier that same day. Brandon had to point this out. If building a system to track thousands of clips, I must demonstrate I can track my own work first. ALWAYS check daily logs before claiming to find/discover anything. If a file path looks familiar, ASK first.
- **Vite allowedHosts**: Use `true` (boolean) or array of hostnames. String `'all'` does NOT work.
- **Safari requires HTTPS** for Web Crypto API (noVNC auth needs this)
- **Browser relay troubleshooting**: If tabs show but can't connect, stop/start relay profile, re-attach extension
- **Whisper**: `tiny` model works, `turbo` gets OOM killed on longer files. Convert ogg→wav first.
- **Canva OAuth**: Must use `127.0.0.1` not `localhost`. Custom ports in Tailscale FQDN URLs rejected. Keep redirect paths simple (`/callback`). PKCE is mandatory.
- **All new apps MUST have**: dynamic API URLs (`window.location.hostname`), CORS enabled, Tailscale HTTPS serve registered, `novalidate` on forms
- **Service watchdog** handles backend crashes — no more manual restarts
- **ALWAYS verify/restart a server before sending Brandon a direct link.** Don't assume it's running — check it, restart if needed, THEN send the link. (Learned Feb 4 — sent Kanban link while server was down)
- **QA before deploying** — Especially when new database tables are required. Always test locally before pushing live. (Learned Feb 12 — deployed multi-org order system with non-existent Supabase tables)
- **Email verification process is MANDATORY** for customer-facing communications. Template + audience match → preview → test send → approval → execute. No more autonomously sending without this checklist. (Learned Feb 11 — sent wrong template to wrong audience)
- **🚨 PRODUCTION DEPLOYMENT — ALWAYS ASK WHERE** — NEVER assume localhost is production. Check DNS (dig), ask Brandon, or look for deployment workflows. FFM website is on GitHub Pages (www.fitfocusmedia.com.au), NOT localhost. Deploy: `npm run build && npx gh-pages -d dist`. (Learned Feb 12 — made changes locally, Brandon tested production)
- **Environment variable newlines will silently break everything** — Stripe keys, webhook secrets, any credential. Use `printf '%s'` NOT `echo` when piping to `vercel env add`. A single trailing `\n` causes signature verification failures. (Learned Feb 12 — 2 hours debugging Stripe webhook)
- **React state initialization timing matters** — If you need state set on FIRST render, use lazy initialization: `useState(() => checkURL())`. Otherwise loading screens can hide success states. Also check render order — success checks must come BEFORE loading checks. (Learned Feb 12 — success page hidden behind loading screen)
- **Pre-order vs post-event messaging is critical** — Don't assume the workflow. This was a PRE-ORDER system but I wrote copy like events had already happened ("finding your footage", "5-7 days"). Always clarify timing and workflow before writing user-facing copy. (Learned Feb 12 — Brandon called this out immediately)
- **Webhook registration is separate from webhook secrets** — Having a STRIPE_WEBHOOK_SECRET in env doesn't mean the endpoint is registered in Stripe Dashboard. Must explicitly add endpoint URL and select events. Both secret AND registration are required. (Learned Feb 12)

## Timeline
- **Jan 28, 2026:** First met. Built UI/UX improvements for Second Brain and Kanban. ~3 hours of development.
- **Jan 29, 2026:** Fixed Kanban scheduler (duplicates, conflicts). Rescheduled Brandon's work blocks. Built Content Intelligence Engine (YouTube, TikTok, Instagram scraping + AI analysis). Set up nightshift protocol. Installed last30days skill. Created Content Engine GitHub repo. Cleaned up 13 zombie Node processes.
- **Jan 30, 2026:** Major Kanban day — itinerary view/download on dashboard, duplicate ID bug fix (board vs modal), Revenue & Earnings system, client cleanup (removed NueraMuscle + Bamboo Cloud, added Stephen to Altered). Added NBA and WNG as clients via voice notes. Built Instagram Profile Monitor for Content Engine. Installed Remotion skills. Power cut recovery (all data intact).
- **Jan 31, 2026:** Telegram MTProto avatar system (9 wardrobe looks). Video editor fixes (frame-based data, waveforms, dual monitor). Boards major upgrade (auto-save, inline edit, resize, context menu, PNG export). Miro board fully replicated (313 elements). Tailscale + noVNC remote access setup. Production tools (SOPs, P&L tracker, pricing page, crew DB). Command Center dashboard built. Boards connector anchoring + text scaling fixes. Growth roadmap written. Invoice generator started overnight.
- **Feb 1, 2026:** Posing Hub client registry fixes (multi-division, competition add button). Boards shape rendering fix (Professional Ventures card). Georgia's AI Content Creation System designed (4-phase: Content Vault → Template Library → AI Engine → Gallery). Canva API connected after debugging OAuth (PKCE, redirect URIs, scopes). Google Drive content library integrated (3 folders, 8 federations). Content Vault + Template Library + Content Creator pages built. Service watchdog created (cron every 5min). Boards connector rebuild completed (170 connectors, SVG overlay, properties panel).

- **Feb 2, 2026:** (Not yet documented in MEMORY.md)
- **Feb 3, 2026:** (Not yet documented in MEMORY.md)
- **Feb 4, 2026:** Major combat sports research + FFM website launch day. DNS setup for fitfocusmedia.com.au → GitHub Pages (4 A records + CNAME). Fixed website base path issue (was `/ffm-website/`, changed to `/`). Added CNAME file to `public/` to prevent gh-pages deploys wiping it. Site is LIVE on custom domain with HTTPS ✅. Combat sports lead generation research — 18 organizations profiled initially, expanded to 29 total. Built interactive lead dashboard (localhost:8897 / Tailscale). Created file transfer scripts (Windows .bat + Mac .command) for Brandon's old computer at his parents' place. Restarted Second Brain server (localhost:8898). Dashboard served via Tailscale for remote access.
- **Feb 5, 2026:** World Gym shoot day (Flagstone 10am-2pm) + Mitch editing training. Morning: Dashboard fix (29 orgs), workout logged (Day 4 Upper). New BJJ/grappling event contract locked in. Contract V2 rewritten on Grand Slam Offer model. Lead verification audit completed (15 pure promotions, 4 gym+promo, 3 governing bodies — UPW flagged DO NOT CONTACT). Contract platform built (port 5197, 18 files), then integrated into FFM website portal (9 components, Supabase auth). Portal deployed LIVE. Evening: massive nightshift — 7 features built in parallel via sub-agents (~8,000 lines, ~30 files). Brandon requested athlete content delivery system + livestreaming platform rebuild. Fit Focus TV identified as Bamboo Cloud OTT. AWS IVS architecture doc completed.

- **Feb 10, 2026:** Memory retrieval system built — embedding-based search with 9,358 chunks (965 memory + 8,393 session transcripts). Context search system for multi-faceted awareness. Cron job for hourly index updates. Full NBA indexing complete (1,406/1,406 files, 22,816 frames). Combined detection system ready (face recognition + Tesseract OCR = 80% detection rate). Athlete detection system accuracy issues identified (31.8% on refiltered footage). Local models downloaded (Llama 3.2 Vision, Gemma 3) to external SSD. Session transcript recovery discovery (131 sessions, 147MB JSONL). Scarlet Edit Sales Page rebuilt without Tailwind v4 (Safari compatibility issue). Morning briefing sent 5:45 AM. Nightshift: quality audit of Refiltered folders, Second Brain journals created for Feb 4-10.

- **Feb 11, 2026:** Brevo re-engagement campaign LAUNCHED — 305 contacts, 4-email automation (Nostalgia → Social Proof → Bundle → Last Chance). 5 major email mistakes documented (wrong template, wrong audience, subject lines too long, freestyling copy, wrong athlete thumbnail). Athlete detection system PARKED pending 2026 season dedicated reference shots at registration. Combat sports outreach campaign created — 5 targets (Beatdown URGENT, Honour HIGH, Eternal/QBBJC MEDIUM, Aggression LOW), comprehensive copy + execution guide. Nightshift: Combat Outreach Tracker dashboard built (port 5208), execution guide (6,177 bytes), Second Brain journal entry, morning briefing prepared.

- **Feb 12, 2026:** Stripe API moved from Railway to Vercel (FREE tier). Killed 3 legacy outreach apps, consolidated into FFM Outreach Hub (port 5210). Multi-org athlete content order system built — sales landing + org selection + org-specific events/packages. Supabase schema designed (organizations → events/packages → content_orders). QA failure lesson — deployed without testing Supabase tables. Morning briefing sent 6:00 AM. All 19 pm2 services online and stable. **EVENING (7:32 PM - 9:39 PM):** Major checkout system build — Brandon tested Artemis order flow, completely broken. Fixed: Stripe webhook (trailing `\n` in secrets), missing DB columns (instagram, coach fields), success/cancel page logic (state initialization + render order), production deployment (GitHub Pages not localhost), messaging (pre-order not post-event). Added: Resend customer emails, Telegram admin notifications, Supabase order status updates. Webhook now fires, emails send, orders save. Copied Artemis packages to M16. Fixed Ava's gateway config (dmPolicy pairing).

## Combat Sports Lead Generation (Feb 4, 2026)
Brandon's new business focus: **Fit Focus Media** (fitfocusmedia.com.au) offering professional media services to combat sports organizations in Australia.

### Research Findings
- **Total organizations profiled:** 29 (18 initial + 11 expansion)
- **Verified contacts:** 13 high-confidence (6 phone numbers, 8 emails)
- **Year 1 revenue projection:** $100K+ (realistic scenario)
- **Database location:** `/Users/clawdbot/clawd/combat-sports-leads/`
- **Interactive dashboard:** http://localhost:8897/dashboard.html (also via Tailscale)

### Top Priority Targets
1. **QBJJC (Queensland BJJ Circuit)** — Score: 92/100
   - Email: qbjjcaustralia@gmail.com ✅
   - 15+ events/year across Queensland
   - Volume opportunity: $15K–$70K annually
   
2. **Beatdown Promotions** — Score: 85/100
   - Brisbane MMA promotion, quarterly events
   - Next event: March 20, 2026 at Eatons Hill Hotel
   - Contact via form + Instagram
   - Potential: $9K–$25K annually

3. **Honour Premier League** — Score: 82/100
   - Phone: 0422 655 064 ✅
   - Email: team@honourpremierleague.com ✅
   - Traditional Muay Thai, Brisbane-based
   - Best contact accessibility
   - Potential: $7K–$32K annually

4. **The Fight Centre (TFC)** — Score: 86/100
   - Phone: 0488 852 775 ✅
   - One of Australia's LARGEST combat sports facilities
   - Runs 20+ fight events annually
   - Next event: Sept 20, 2025

5. **Fortitude Boxing** — Score: 84/100
   - Phone: 0435 929 311 ✅
   - Email: admin@fortitudeboxinggym.com ✅
   - 3 event series (Fight Night, Tradie Night, Corporate)
   - Next event: Oct 18, 2025

6. **Eternal MMA** — Score: 81/100
   - Email: media@eternalmma.com ✅
   - MONTHLY events (2-4 per month)
   - National reach, 39K Instagram followers
   - Dedicated media department = existing budget

### Week 1 Action Plan (Starting Feb 5)
**Monday Morning — Make These Calls:**
1. TFC: 0488 852 775
2. Fortitude: 0435 929 311
3. Honour Premier League: 0422 655 064
4. Aftershock MMA: 1300 556 795

**Goal:** Book 2-3 face-to-face meetings by Friday.

### Key Insight
Brandon needs CONTACT DETAILS above everything else. "Contact details are the #1 thing — We need to be able to get in touch with the right people in the right places." Research focused on finding promoter/owner names, phone numbers, and emails with verified sources.

### Combat Sports Outreach Campaign (Feb 11, 2026)
**Location:** `/Users/clawdbot/clawd/combat-sports-outreach/`

**5 Priority Targets:**
1. **Aggression Thai Boxing** — Gold Coast/Townsville, Adam & Vick Houlahan
2. **Eternal MMA** — Australia's most active, 100+ events, Gold Coast base
3. **Honour Fight Series / Premier League** — Brisbane elite Muay Thai
4. **Beatdown Promotions** — URGENT (March 20 event), Damien Brown's MMA promo
5. **QBBJC** — 15+ BJJ tournaments/year across QLD

**Outreach materials:**
- 5 personalized cold emails (Hormozi/Cialdini persuasion principles)
- 5 Instagram DM scripts
- Follow-up sequence (Day 0, 3, 7, 14)
- Value-first hooks (free audit, free highlight reel, revenue share)
- Complete contact tracker

**Combat Outreach Tracker Dashboard:**
- URL: https://clawdbots-mini.tailcfdc1.ts.net:5208
- Visual contact cards with priority indicators
- Status tracking (Not Contacted → Contacted → Responded → Booked)
- One-click actions (email, phone, Instagram, Facebook)
- Browser localStorage persistence
- Built Feb 11 nightshift

**Execution guide:** `EXECUTION-GUIDE.md` (6,177 bytes) with priorities, hooks, sequences, objection handling

## Fit Focus Media Website (fitfocusmedia.com.au)
- **Status:** LIVE ✅ (launched Feb 4, 2026)
- **GitHub Pages:** Custom domain with HTTPS enforced
- **DNS:** 4 A records (GitHub IPs) + CNAME (www → fitfocusmedia.github.io)
- **Source:** `/Users/clawdbot/clawd/ffm-website/app/`
- **Tech Stack:** Vite + React + Tailwind v4 + Supabase
- **Base path fixed:** Changed from `/ffm-website/` to `/` for custom domain
- **CNAME file:** Added to `public/` to persist through gh-pages deploys
- Brandon wants to make edits page-by-page at some point (future task)

### Contract Portal (Feb 5, 2026)
- **Live at:** `fitfocusmedia.com.au/#/portal`
- **Auth:** Supabase email/password (brandon@fitfocusmedia.com.au)
- **Routes:** /#/portal (login), /#/portal/contracts (dashboard), /#/portal/contracts/new (builder), /#/contract/:token (public signing)
- **9 React components** in `src/components/portal/` + `src/context/AuthContext.jsx` + `src/lib/contractHelpers.js`
- **Supabase table:** `contracts` (id, status, org_name, promoter_name, contract_data JSONB, ffm_signature, client_signature, share_token)
- **Key bugs fixed during build:** Canvas 0x0 when hidden (re-init on show), form novalidate for multi-step, signature export black-on-white (pixel alpha check), relative→absolute asset paths, mobile clipboard fallback
- **Standalone version still exists:** `/Users/clawdbot/clawd/contract-platform/` (port 5197) — original HTML/CSS/JS build
- **Contract template:** Based on Grand Slam Offer model — zero upfront cost, PPV/livestream rev share, athlete media packages (VIP $350, Match $175, Season $899)

### FFM Portal — Nightshift Builds (Feb 5, 2026 Night)
Massive overnight build session — 7 features built via parallel sub-agents in <30 minutes:

**Portal features (all at fitfocusmedia.com.au/#/portal):**
1. **CRM/Sales Pipeline** — Kanban pipeline (7 columns), 29 leads embedded, lead detail pages, activity logging
2. **Outreach Templates** — 4 email templates with variable substitution, copy-to-clipboard
3. **Client Onboarding** — 12-step workflow in 3 phases, auto-due-dates, email templates, export to HTML
4. **Content Manager (Admin)** — Assign content to athletes, manage events, batch import Drive URLs
5. **Athlete Portal** (public at /#/athlete) — Login/register, dashboard, event content viewer, photo lightbox, video downloads, packages page (VIP $350, Match $175, Season $899)

**Public pages:**
6. **Meeting Booking** (/#/book) — 5-step flow, .ics download, NOT in navbar (direct link only)
7. **ROI Calculator** (/#/calculator) — Interactive revenue projector with animated counters, Recharts comparison chart

**Standalone:**
8. **Event Day Checklist** — Offline HTML app at /event-checklist/ (port 5199), 6 phases, 96 items, timer

**Portal nav tabs:** Contracts | Pipeline | Outreach | Onboarding | Content
**All localStorage-first** with Supabase migration SQL ready
**Final build:** 2.77s, 2839 modules, 2.31MB bundle, ~8,000+ new lines across ~30 files

### FFM Outreach Hub (Feb 12, 2026)
**URL:** https://clawdbots-mini.tailcfdc1.ts.net:5210

**Purpose:** Unified CRM replacing 3 legacy apps:
- ❌ combat-sports-outreach (5201) — deleted
- ❌ combat-outreach-tracker (5208) — deleted
- ❌ email-sequence-dashboard (5207) — deleted

Consolidated all functionality into single hub for managing combat sports outreach campaigns.

### Multi-Org Athlete Content Order System (Feb 12, 2026)
**Routes:**
- `/content` — Sales landing page (navbar points here)
- `/order/:orgSlug` — Org-specific order (e.g., /order/nba)
- `/portal/content-admin` — Admin management

**Supabase Schema:**
```
organizations → events
            ↓       ↓
            packages
                ↓
          content_orders
```

**Features:**
- Sales landing with social proof
- Organization selection (NBA, WNG, Artemis, M16, etc.)
- Org-specific events/packages
- Clean database isolation per org
- Stripe integration via Vercel API

**Stripe API:**
- Moved from Railway to Vercel (FREE tier)
- URL: `https://scarlet-sales-api-vercel.vercel.app`
- Webhook configured with signing secret

**Lesson learned:** QA failure — deployed without testing, broke because Supabase tables didn't exist yet. Always test locally before pushing live, especially when new tables are required.

### Fit Focus TV / Livestreaming Platform (Feb 5, 2026)
Brandon's existing livestreaming platform — wants to rebuild/upgrade the backend.

**Current platform: Bamboo Cloud (OTT provider)**
- Frontend: watch.fitfocusmedia.com
- CDN: cdnapi.bamboo-cloud.com
- HLS streaming, auto-transcoding (Source → 7 quality levels)
- 46 media items, 24 live entries, 1.02 TB storage
- ~25+ registered viewers, Stripe PPV ($30/event)
- Categories: Bodybuilding (NBA, FMG), Combat Sports (WNG1/WNG2), Beyond the Athlete
- User management: email/password, Bamboo ID, purchase tracking

**Proposed rebuild: AWS IVS (Interactive Video Service)**
- Architecture doc: `/Users/clawdbot/clawd/second-brain/data/documents/livestream-platform-architecture.md`
- Per-event cost: ~$242 (4hr, 1000 viewers) vs ~$24K revenue at $29.99 PPV = 96% margin
- Break-even: just 40 viewers per event
- Integration with athlete portal for highlight clip delivery
- **Pending:** Brandon needs to clarify WHY moving from Bamboo (cost? customization? integration? ownership?)


## Memory Retrieval System (Built Feb 10, 2026)

**Purpose:** Prevent hallucinations and forgotten context by searching memory before responding.

**Location:** `/Users/clawdbot/clawd/memory-agent/`

**Architecture:**
- **embed_retriever.py** — Core embedding search using `nomic-embed-text` (274MB)
- **context_search.py** — Multi-faceted awareness search (topic + corrections + tasks + today's context)
- Pre-indexes all memory files + last 30 days of session transcripts
- Query time: ~1.5 seconds
- No LLM needed for retrieval — just vector similarity

**Coverage:**
- **9,358 chunks indexed** (965 memory + 8,393 session transcripts)
- Last 30 days of conversations (verbatim)
- All memory files (no time limit)
- Embeddings index: `embeddings_index.json`

**Automation:**
- Cron job: `memory-index-update` runs hourly
- Command: `python3 embed_retriever.py --index --session-days 30`
- Incremental updates (no full rebuild)

**Usage:**
- `memory_search` tool (built into Clawdbot)
- Manual: `python3 embed_retriever.py "query"`
- Context search: `python3 context_search.py "query"`

**Rule:** Search before responding to ANY substantive message. If unsure, search. It takes 1.5 seconds. Hallucinating takes trust.

## Communication Preferences
- **Telegram links:** Always use Tailscale remote URLs (clawdbots-mini.tailcfdc1.ts.net or 100.69.75.49), never localhost. Brandon accesses from his phone.

---

## Brevo Email System (Built Feb 11, 2026)

**Purpose:** Re-engage 305 NBA athletes who competed in 2025 but didn't order footage.

**Location:** `/Users/clawdbot/clawd/brevo-reengagement/`

**Key components:**
- Google Sheet → `process_athletes.py` → CSV → Brevo contacts
- 11 email templates in Brevo (4 re-engagement + 7 new-show)
- Stripe payment link for checkout
- Sender: info@fitfocusmedia.com.au

**How it works:**
1. Script scans sheet, groups by email, finds shows where "Videography Service" column is empty
2. Creates AVAILABLE_SHOWS field listing unpurchased shows per athlete
3. Email automation personalizes with athlete name + their specific shows

**To re-run data:** `cd brevo-reengagement && python3 process_athletes.py`

**Brevo credentials:** `~/.config/brevo/credentials.json`

**Manual step needed:** Create automation workflow in Brevo UI (can't be done via API)

### Brevo Campaign LAUNCHED (Feb 11, 2026)
- 4-email automation built in Brevo UI (Nostalgia → Social Proof → Bundle → Last Chance)
- Conditional logic: only follow up if no click on previous email
- 305 contacts imported via batch API
- **Lesson:** Always verify template matches purpose before sending. I sent "footage ready" template (for new shows) instead of "nostalgia" (for re-engagement) initially — different contexts.

---

## Athlete Detection System (PARKED — Feb 11, 2026)

**Theory is sound:** Face recognition + OCR for hip numbers, process Float Cam first, sync via timecode.

**What's broken:** Reference shots aren't clean enough. Detection put wrong clips in folders (C0139.MP4 = athlete #13, was in #89 folder).

**Fix for 2026 season:** Capture dedicated reference shots at EVERY show:
- Clear front-facing headshot per athlete
- Clear hip sticker close-up
- Linked to registration data
- These become the ONLY reference for detection

**Files:**
- Scripts: `/Users/clawdbot/clawd/scarlet-edit-pro/scripts/`
- Docs: `/Users/clawdbot/clawd/scarlet-edit-pro/docs/WORKFLOW.md`
- Test footage: `/Volumes/Angus T7/NBA Test Folder/NBA Sydney Nationals Day 2`

---

## Customer-Facing Work — VERIFICATION PROCESS

**Learned the hard way on Feb 11.** Before ANY customer-facing email/action:

1. **Template + Audience Match** — state what template, what audience, why it's right
2. **Audience Preview** — count, criteria, sample recipients
3. **Single Test Send** — real recipient data, Brandon's email
4. **Brandon Approves → Execute**

No more autonomously sending external communications without this checklist.
