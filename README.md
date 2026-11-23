# IPO India Hub - Community IPO Calendar, SEBI Lottery Calculator & MegaThread Manager

## App Overview (For Community Members & Moderators)

**What the app does:**  
**IPO India Hub** is an informational reference and moderation utility built for Indian stock market discussion communities such as `r/IPO_India`. It provides an interactive, neutral public-data dashboard inside a pinned Reddit post where community members can inspect Indian Mainboard and SME Initial Public Offering (IPO) schedules, live subscription multiples (QIB, NII, Retail), mathematical SEBI lottery allotment odds, exchange circuit-limit bands, post-listing EOD price curves, and historical listing performance without leaving Reddit. It also helps subreddit moderators organize recurring discussion threads (Weekly Discussion, combined Weekly P&L / Profit Booking / Hold-Sell / Mandates & Refunds, Allotment Night, Listing Day, and unpinned Monthly Recap MegaThreads) so repetitive one-line posts do not clutter the community feed.

**Who it is for:**  
1. **Redditors in `r/IPO_India`:** Anyone researching open, upcoming, or recently listed Indian IPOs who wants to calculate their statistical lottery allotment probability under SEBI Mainboard and SME rules, check T+3 ASBA fund unblock timelines across NSE trading holidays, simulate post-tax listing gains, compare active IPOs side-by-side, or track personal application history.
2. **Subreddit Moderators:** Moderators who need an in-app dashboard (`Mod Tools` tab) to preview, edit, publish, or remove MegaThreads, manage IPO and DRHP calendar entries, review user data correction reports, parse Basis of Allotment screenshots, and redirect repetitive posts in one click.

**Critical Operational & Compliance Notes:**
- **Strictly Informational & Educational (No Financial Transactions):** This app is a mathematical calculator and public-data schedule reference only. It does **not** facilitate financial transactions, brokerage orders, payments, cryptocurrency activity, or SEBI-regulated investment advice.
- **Reddit-Native UI & Official SEBI RTA Portals Only in MegaThreads:** The in-app hub UI never links to external websites (internal navigation opens only `reddit.com/r/...` discussion threads). Automated `Allotment Night` and `Weekly P&L` text MegaThreads link exclusively to official SEBI-registered Registrar portals (such as MUFG Intime, KFinTech, and Bigshare) so members can check allotment status safely.
- **No Subscription Gating or Forced User Actions:** All core tools are available without requiring users to subscribe, post, or comment. Public poll voting and price predictions apply basic Reddit account maturity checks (`48h` account age and `10` combined karma) to deter spam and troll skewing.
- **Privacy, 30-Day Sliding Expiration & 1-Click Data Deletion:** The app never asks for or stores PAN numbers, Demat BOIDs, or bank details. Optional community poll votes, price predictions, and Scorecard logs are stored under your internal Reddit `userId` in Devvit Redis with an automatic **30-day sliding inactivity TTL** (reset whenever you visit or log an update). Users can copy/restore JSON Scorecard backups locally, delete individual entries, or erase 100% of stored app data at any time via **Delete All My App Data** in **FAQ -> Terms, Privacy & Data Controls**.

---

## How to Configure, Deploy & Use the App

### 1. Deploying & Creating the Interactive Hub Post (Moderators)
1. Install the app on your subreddit (`devvit install <subreddit>`).
2. Open your subreddit moderation menu and click **[IPO Hub] Publish / Refresh Slot 1 Hub Post** to publish the interactive **IPO India Hub** post and pin it as the last fallback slot in Community Highlights.
3. Optional settings in **Subreddit Settings -> Installed Apps -> IPO India Hub**:
   - **Enable `!ipo` / `!odds` / `!gmp` / `!registrar` / `!calendar` Comment Bot:** Toggle on or off at any time (automatically disabled on the Slot 1 Hub post so Live Chat stays clutter-free).
   - **Enable Allotment Night Duplicate Post Flood Shield:** Redirects repetitive one-line *"Is allotment out?"* posts when an active Allotment Night thread is open.
4. Optional Global App Secret (`settings.global`):
   - **Gemini API Key (Optional):** Used strictly by moderators in `Mod Tools -> Screenshot Parser` to extract structured numbers from uploaded Basis of Allotment, Subscription, or Anchor screenshots.

### 2. Interacting With the App (Community Members)
- **Inline Feed Card (`Home` | `Live Chat`):** Defaults to **Home**, showing active Mainboard and SME IPOs with dates, issue size, minimum lot cost, subscription multiples, unofficial GMP, and 1-lot retail odds (`Pending` when bidding has not started). Toggle **Live Chat** at the top right to jump straight into live comment-backed IPO Chat from the feed, or click **Open IPO Hub** to launch the full experience.
- **Tab 1 - Pipeline:** Browse active IPOs or switch to **Watchlist**, toggle Application-Wise vs Share-Wise multiples, star personal watchlist issues, jump straight to **Discuss in Chat** (with an automatic private `/ipo` snapshot) or active Allotment/Listing MegaThreads (`reddit.com/r/...`), compare 2 to 3 IPOs side-by-side (`Compare IPOs`), vote **Applying** vs **Skipping** (aggregate split stays hidden until 10+ votes), submit blind **Listing Price Predictions**, or flag inaccurate figures via **Report Data**.
- **Tab 2 - Live Chat:** Real-time Discord-style comment-backed chat on the weekly Slot 1 Hub post with Indian PII protection, private `/ipo`, `/gmp`, `/odds`, `/unblock`, `/registrar`, `/calendar`, and `/help` slash commands, 1-tap Mod Queue reporting, and an in-chat Settings drawer (flair toggles, compact mode, muted users, plus opt-in `MOD` badge and quick controls for moderators). Public `!` bot replies are disabled inside Hub Chat.
- **Tab 3 - Allotment Odds:** Select active or recent 35-day IPOs (plus Search All) and enter family PAN counts across Retail, sHNI, bHNI, Shareholder, Employee, and SME 2-lot minimum rules to compute combined SEBI lottery allotment probabilities and expected lots.
- **Tab 4 - Listing Gain:** Simulate gross profit, `20.8%` effective STCG + cess (with Section 87A rebate notice), brokerage/statutory charges, NSE/BSE circuit bands (`±5%` SME, `±20%` Mainboard, `-20%/+90%` SME call-auction cap), and Free-Shares breakeven math.
- **Tab 5 - Community:** Track live Crowd vs GMP sentiment divergence, opt-in **Top Predictors** accuracy leaderboard (ranked by MAPE across settled listings), and **Allotment Night / Listing Day Pulse** polls.
- **Tab 6 - Analysis:** Switch across **Current Year**, **All Time**, **Last 90d**, and **Last 30d** cohorts across our verified 2026+ Mainboard and SME database. Explore **GMP vs Crowd Prediction vs Actual** accuracy charts, search **Post-Listing Prices** with EOD trajectory curves, compare **Mainboard vs SME**, inspect **Sector vs Sector**, or use the **Custom Screener** to export filtered subsets as CSV or markdown Report Cards.
- **Tab 7 - Calendar:** Inspect the monthly IPO grid (Today highlighted in blue, weekends tinted subtle red, built-in + live-synced NSE trading holidays visibly badged without hiding IPO or Anchor Unlock dates, plus event/segment filters and a 14-day action timeline), run the **Capital Unblock Checker**, follow DRHP Watchlist filings, or click **+ Submit Missing IPO**.
- **Tab 8 - Scorecard (`BETA`):** Log personal applications (`Pending`, `Still Holding` with live CMP Unrealized MTM, `Listing Exit`, or `Sold @ Custom Price`), view your Cumulative P&L curve, Luck Index, Mainboard vs SME breakdown, paginated history (`10 per page`), **Year-End IPO Wrapped** shareable screenshot card, and **Prediction Accuracy Rank**, plus copy/restore local JSON backups across 30-day inactivity expirations.
- **Tab 9 - FAQ & Data Controls:** Read plain-English guides on ASBA netbanking vs UPI cutoffs, SEBI SME 2-lot rules, CDSL TPIN / DDPI, STCG/LTCG taxation, Live Chat rules, and privacy, or erase all stored app data under **FAQ -> Terms, Privacy & Delete My Data**.

### 3. Using Moderator Tools (`Mod Tools` Tab - Subreddit Moderators Only)
- **MegaThreads & Schedule:** Preview, customize, publish, or remove Highlights (`Listing Day -> Allotment Night -> Weekly Discussion -> Weekly P&L -> Hub`; Monthly Recap & Year-End IPO Wrapped MegaThread post as regular unpinned community threads). The Slot 1 Hub rotates weekly on Sunday night (unpinning & locking previous Hub posts that have chat comments so history stays intact).
- **Live Chat Settings:** Configure strictness presets (`Relaxed` / `Standard` / `Strict - Allotment Night`), slow mode, minimum account age & karma, emergency read-only lock, sticky chat banner, Indian PII shield, external link/scam blocking, custom blocked words, and configurable auto-hide report threshold (`0` to `10`, default `3`, forwarding every report directly to Reddit Mod Queue). Moderators can also run `/pin`, `/unpin`, `/slowmode`, `/mode`, `/lock`, `/unlock`, `/timeout`, and `/untimeout` right inside Live Chat.
- **Add / Edit IPOs & Screenshot Parser:** Manage Mainboard/NSE Emerge/BSE SME records (`Terms Only` vs `All Fields` manual lock modes, protected slug rename), parse screenshots via Gemini Vision directly into an IPO draft, and review **Community Missing-IPO Submissions** or **Community Data Correction Reports** alongside `ipo_feed.json` uploads under **Submissions & Reports / Backup**.

---

## Fetch Domains
The following domain is declared in `devvit.json` exclusively for optional server-side moderator screenshot parsing (zero Reddit user IDs, usernames, comments, or PII ever leave Reddit):
- `generativelanguage.googleapis.com` - Globally allowlisted Google Gemini API used solely when a moderator runs `Mod Tools -> Screenshot Parser` to extract structured public IPO subscription, Basis of Allotment, or Anchor figures into an editable draft.

*(Public IPO schedules, GMP snapshots, subscription multiples, NSE holidays, and NSE EOD Bhavcopy quotes are loaded locally by moderators using the single-file `ipo_feed.json` uploader in `Mod Tools -> Backup & Audit Log` rather than polling unapproved external scrapers or cloud storage buckets from Devvit servers.)*

## Legal Documents & Support
- Terms of Service: [`TERMS.md`](./TERMS.md)
- Privacy Policy: [`PRIVACY.md`](./PRIVACY.md)
- Contact / Data Inquiries: Message subreddit moderators via **r/IPO_India Modmail** (also accessible under **FAQ -> Terms, Privacy & Data Controls**).
