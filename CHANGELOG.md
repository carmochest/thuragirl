# Changelog

ThuraGirl prototype iterations. Newest first.

---

## v20.1 — 2026-08-13 · POLISH PASS

### Changed

- **Settings gear toggles**: clicking the gear while in Settings takes
  you back to wherever you came from (it remembers the last page).
- **Design unification, round 2**: the sort row above every list is now
  pixel-identical across Contacts / Files / People — same padding
  (py-2.5), same bottom border, same label weight and colour. The
  column-header bands share one dark background (#1b1f26), and the
  People taxes table header matches too.
- **Pro tips removed**: the Contacts tip banner is gone.
- **Sort defaults to A–Z**: Contacts and People open sorted A–Z (option
  listed first); Files opens sorted by Name.
- **Chat, smoothest possible**:
  - The panel's overflow clip now releases the moment the open
    animation settles, so its shadow renders fully — no more flat
    "shadow cutoff" line at the wrapper edge.
  - The sheet now *rises* out of the composer: the inner card animates
    on transform (translate + micro-scale) while the wrapper height
    tweens on Apple's sheet curve (0.34s, cubic-bezier(.32,.72,0,1))
    with the fade running slightly faster — reads as one fluid motion.
  - The fade seam above the composer is taller (56px) and uses a
    smoothstep-style multi-stop gradient instead of a two-stop linear —
    cards melt into the composer band with no visible gradient edge.

---

## v20 — 2026-08-13 · ONE DESIGN LANGUAGE

### Changed

- **Comfort icon**: custom horizon-sun glyph (lucide's Sunset arrow cut).
- **Advanced toggle mirrors state**: 2×2 grid = simple, 3×3 = advanced.
- **Chat band fixed**: custom WebKit scrollbars consume layout space
  (Safari ignores scrollbar-gutter), shifting the content column off
  the composer's centre — the main scroll area now hides its scrollbar
  entirely, so both columns centre identically in every browser. Cards
  fade softly into the composer band (gradient seam) instead of
  hard-clipping — the "invisible grey band" is gone.
- **Shared design system pieces**:
  - `SortPills` — the ONE sort control (segmented gray track, white
    active pill), now identical on Contacts, People, and Files
    ("Sort by" left, pills right, same position atop each list).
  - `AddButton` — the ONE "+" (neutral 36px, quiet ring, no teal),
    used on Contacts (menu: customers → New quote / New invoice;
    vendors → New PO), People (wired: opens an onboard-employee chat
    draft — it was dead before), and Files (opens the attach sheet).
- **Money toolbar** matches the others (period picker size sm).

---

## v19.2 — 2026-08-13

### Changed

- **Sign-in logo**: now renders Chet's "TG-VERTICAL-LOGO.svg" verbatim
  (viewBox cropped to content, ids namespaced, wordmark themed via
  currentColor). Replaces the hand-composed stack that was misaligned.
- **Advanced mode** (grid toggle, top right): People / Contacts / Files
  leave the Settings archive. Off = the two-tab shell; on = five tabs
  (Dashboard, Money, People, Contacts, Files) on desktop pills and
  mobile bottom tabs. Choice persists; landing on one of the three
  routes flips it on automatically. Archive card and back-to-Settings
  links removed.

---

## v19.1 — 2026-08-10

### Changed

- **Chat embedded, not floating**: the conversation panel now lives in
  the page column — expanding it squeezes the content above instead of
  overlaying it. Composer alignment fixed via scrollbar-gutter
  both-edges (the scrollbar was shifting the content column).
- **Attach sheet**: "Create invoice" removed — pure iOS-style picker.
- **Comfort theme icon**: Sunset (was SunDim).
- **Back to Settings** links added to Files and People (Contacts had it).
- **Share icon**: iOS-style up-arrow Share (was the 3-node Share2).
- **Contacts**: chat actions inside the edit sheet close the sheet
  first — no more blurred chat behind the backdrop.
- **People**: Team list sortable (A–Z / role / pay / status); the
  both-edges gutter also kills the tab-switch card shift.

---

## v19 — 2026-08-10 · THE BIG POLISH

Fourteen-point round. Three subagents swept Contacts, Files, and
People+Onboard in parallel.

### Changed

- **Dashboard**: snapshot subtitle cut; criticality is now explicit —
  critical = overdue / due today / due ≤2 days / blocking sign-off due
  ≤7 days (a sign-off due in 9 days is Scheduled); "Done this week"
  shows 3 with a Show-all expander and a "resets Monday" note.
- **Calendar**: Apply/Cancel were being clipped by the snapshot card's
  overflow — fixed; the Custom pill highlights when a range is active.
- **฿ everywhere**: formatTHB now renders ฿1,842,300 (matches axes).
- **Chat = floating composer**: Claude-style rounded card, centred and
  exactly as wide as the content column; "Write a message…"; mic
  button (mock capture pulse); arrow-up send. Panel floats above it.
- **Comfort theme**: warm low-contrast in-between mode; toggle cycles
  light → comfort → dark (Sun / SunDim / Moon).
- **Settings**: notifications = one switch; Billing full-width with a
  Standard/฿2,900 ↔ Premium/฿4,900 plan picker, inline payment form,
  per-invoice view (print) + download; invoices fit without scroll.
- **Contacts**: back-to-Settings link; click-to-edit sheet (fields +
  save, plus "edit via chat"); sort by value/A–Z/category/transactions;
  alignment pass.
- **Files**: vault actually locks/unlocks with permission note;
  sortable aligned columns; icon-only view/share; upload is a single
  "+" opening the iOS attach sheet (banner removed).
- **People**: "+" replaces Onboard button; payroll/team tab-switch and
  leave-mode layout shifts pinned; number-input caret fixed; bottom
  approve-payroll control removed (Dashboard task owns approval).
- **Onboard**: full visual cleanup to current design language — serif
  headings gone (incl. "Let's get you set up"), teal-gradient primary
  buttons, lucide icons instead of emoji, dark parity, full i18n.
- **Login**: stacked lockup (gradient mascot over wordmark), all text
  under the logo removed.
- Typography stragglers normalized (16px semibold card titles).

---

## v18.1 — 2026-08-10

### Changed

- **Mascot lives again**: blink every ~4s (closed-smile arcs added to
  the final mark via `eyesClosed`), gentle idle float in the chat bar
  and panel header, and a playful hover lift + tilt wherever she
  appears. Success state holds the smile.
- **Receivables / Payables**: explanation subtitles removed — just the
  titles and numbers.

---

## v18 — 2026-08-10 · THE DEEP CLEAN

Twelve-point feedback round. Three parallel translation passes +
settings functionality sweep were delegated to subagents.

### Changed

- **Mascot unified**: MascotAvatar now renders the final gradient
  mascot everywhere (chat bar, bubbles, onboarding). Per-instance
  gradient ids fix the display:none-defs bug that muddied small sizes.
- **Chat**: suggestion chips and rotating placeholder subjects removed —
  one static "Ask ThuraGirl…" placeholder. The + still opens the
  iOS-style attach sheet (photo / scan / file / invoice).
- **Custom calendar**: native date inputs replaced with a month-grid
  range picker (tap start, tap end, teal band, quick ranges kept).
- **Expenses icon** unified (CreditCard on Dashboard and Money).
- **Pulse ring**: deep-dive container releases overflow after expanding
  so click-through highlights aren't clipped.
- **Thai complete**: 300+ new keys — contacts, files, people pages,
  money leftovers (rows, deductibles, chart tooltips, print export),
  and all of settings. TH Money KPI terms aligned with Dashboard
  (รายรับ/รายจ่าย).
- **Settings regrouped & functional**: Account group (Account+Prefs,
  Security, Billing) and Company group (Company, Shareholders,
  Directors, Team, Integrations). Notifications & language are toggle
  rows inside Account. Billing invoices fit without horizontal scroll;
  Cancel → Cancel subscription with working state. Every control now
  responds: sessions sign-out, CSV export, backup codes download,
  passkey add, password validation, add shareholder/director,
  integrations connect/sync, team invite/role cycling, edit flows
  persist. Archive hint text removed.

---

## v17 — 2026-08-10 · CHET'S FIFTH PASS

### Changed

- **Top bar is logo-only.** Company tile + name removed (the rail says
  which company you're in). Mobile keeps switching via a small company
  avatar on the right of the top bar.
- **Tax card back to the v12 palette**: white body, gray filing-status
  row, teal-tinted Potential-savings sub-card.
- **Money KPIs**: labels back to Cash balance / Revenue / Expenses /
  Profit, and the tiles are interactive again — hover lifts the card,
  click scrolls to its breakdown (auto-opening "The full picture" for
  revenue / expenses / P&L) with the teal pulse ring.
- **Custom date fields**: value now vertically centred (appearance-none
  + inner-edit flexbox), larger touch-friendly height, teal focus ring.
- **Settings restored to the full v12 page**: Account / Security /
  Notifications / Preferences + Workspace group (Company, Shareholders,
  Directors, Team, Billing, Integrations incl. LINE connect), with the
  Archive card (Contacts / Files / People) appended at the bottom.

---

## v16 — 2026-08-10 · TRANSLATE, DARKEN, SHRINK, SHARE

Six-point quality pass from Chet's "anything else?" round.

### Changed

- **Thai everywhere**: ~90 new i18n keys (dash2.*, money2.*) cover the
  restored v12 chrome — snapshot, KPI labels, receivables/payables,
  cash flow, the full tax card, revenue mix, expense breakdown, P&L.
  PeriodPicker presets now render via period.* keys (วันนี้/เดือนนี้/…).
- **Dark mode parity** across every Money card (guarded regex pass:
  bg/border/text dark variants). Logo wordmark uses currentColor so it
  flips with the theme.
- **Brand assets**: favicon.svg/.ico, favicon-16/32/48, apple-touch-icon,
  icon-192/512 regenerated from the final gradient mascot; manifest
  paths made relative (basePath-safe). Login hero + wordmark and
  onboard header now use the final lockup. New ThuraGirlMark export.
- **Chat housekeeping**: delete button on recents rows (hover-reveal on
  desktop, always visible on touch); chats you never typed in are
  auto-discarded when you move on; deleting the last chat reseeds a
  fresh greeting.
- **Mobile**: mark-only logo under sm so long company names fit the
  top bar; verified 390px layouts for Dashboard, Money, tax expansion
  and chat.
- **Share with accountant**: button on the P&L card opens a print-ready
  statement (new window + print dialog → Save as PDF). No PDF library;
  works in the static export.

---

## v15 — 2026-08-10 · POLISH & THE FULL PICTURE

Chet's second feedback round on the walk-back.

### Changed

- **Top bar**: final logo lockup (from "ThuraGirl Final Logos.svg",
  new `components/brand/thuragirl-logo.tsx`) · thin divider · company
  chip (color tile + name). "ThuraGirl handles the rest" tagline cut.
- **Company rail**: unmistakable active state — 3px teal side bar,
  teal ring + offset halo on the active tile, inactive tiles dimmed
  and desaturated until hover.
- **"Home" renamed "Dashboard"** (desktop pill + mobile tab; existing
  `nav.dashboard` i18n key reused).
- **Chat header**: New-chat and Recents are icon-only (tooltips +
  aria-labels keep them discoverable).
- **Tax card** (Money): "Ask why" removed. The card itself now expands
  into the full v12 tax snapshot — filing status (PP.30/PND.3/PND.1/SSO),
  VAT output/input/net tiles, deductibles with bars, potential-savings
  callout, per-tax breakdown.
- **"The full picture"** (Money): new disclosure row, collapsed by
  default, that unfolds into the v12 analytics an owner still wants:
  revenue mix (channel/product/customer lenses), expense breakdown,
  and the full P&L statement with margin chips. Feature audit vs v12:
  everything else that was cut stays cut (reconciliation, inbox,
  global search, ⌘K, breadcrumbs, attention feed, focus hero).

---

## v14 — 2026-08-10 · THE WALK-BACK

Chet's verdict on v13: too simplified. v14 keeps the cutback's spirit
(no jargon destinations, chat-first) but restores the surfaces that
earned their place.

### Changed

- **Home restored to the v12 dashboard**: Today's-focus hero, Snapshot
  card (period picker, 4 KPIs, revenue-vs-expenses chart), Attention
  feed, and the Critical / Scheduled / Done task board. Inbox links
  now point at the on-page task board (`#tasks`).
- **Money restored to the v12 page** minus bank reconciliation
  (cut per Chet — jargon, low use). Copy that referenced Inbox now
  says Home.
- **Company rail is back** (Slack-style left bar): switch between
  companies, add a new one. Mobile: tap the company name in the top
  bar for the bottom-sheet picker.
- **Contacts / Files / People are an Archive**: real pages again, but
  reachable only from Settings → Archive. Inbox stays gone.
- **Chat: conversations + recents.** Threads are now titled
  conversations persisted per company (localStorage). New-chat and
  Recents buttons in the panel header; a fresh chat greets you with
  tappable suggestions; Esc collapses. Continue any past chat from
  Recents.
- Shell container back to 1180px; Settings constrains itself to 680px.

### Build

- Fonts self-hosted via @fontsource (Google Fonts unreachable in the
  build sandbox). Static export with basePath /thuragirl for GitHub
  Pages.

---

## v13 — 2026-08-10 · THE CUTBACK

Aggressive simplification pass. Target user: someone who has never
heard the words "reconcile", "withholding", or "HR" — they buy things
and sell things, and want the rest to feel like signing up for
Facebook (reference: firstbase.io). The engine keeps every capability;
the interfaces exposing it are removed.

The five filters applied to every screen, field, and label:
jargon test · verb test (Approve / Fix / Ask only) · Facebook test ·
zero-entry test · "do I need this to get paid, pay someone, or stay
legal this week?"

### Changed

- **Navigation: 7 destinations → 3 surfaces.** Home, Money, and the
  persistent chat bar. Desktop gets two pills in the top bar; mobile
  gets two bottom tabs. Settings survives as a small page behind the
  top-bar gear — it is not in the nav.
- **Home rewritten** (`(app)/page.tsx`): one cash number with a quiet
  hand-drawn 7-day line; "Needs your yes" — max 3 plain-language cards
  with one primary button each; "{n} more can wait" collapsed;
  "Done for you" as a single expandable line. Period pickers, 4-KPI
  grid, recharts, Attention feed, and the 3-zone task board are gone.
  Form codes (PP.30 / PND.3 / PND.1) now only exist inside "Ask why"
  fine print — never in a title.
- **Money rewritten** (`money/page.tsx`): "May so far" in/out in two
  numbers and one sentence; two big buttons — "Get paid" (reuses
  `openCreateInvoiceModal`) and "I paid for something" (reuses
  `openUploadModal`); "Still waiting" receivables as sentences with a
  Remind button (reuses `openSendViaLine`); one chronological
  plain-sentence activity list. P&L card, revenue mix, tax position,
  VAT tiles, and the reconciliation section are out of the UI.
- **Settings rewritten**: six rows — business, bank, language,
  notifications, invite-my-accountant, log out. Tabs, shareholders,
  directors, fiscal year, integrations, roles: gone. Footer points to
  chat for everything else.
- **Chat suggestions** now teach the escape-hatch model: "Who still
  owes me money?", "Can I afford ฿50,000?", "Show the Makro receipt
  from last week".
- Layout: single-column `max-w-[680px]` feed. Company rail + switcher,
  collapsible sidebar, global search, ⌘K palette, and breadcrumbs
  removed from the shell (one business is the normal case).

### Removed (phase 1: hidden, not deleted)

- `/inbox`, `/contacts`, `/files`, `/people` now redirect to `/`.
  Their jobs live in Home cards, Money rows, and chat. Component
  files remain on disk, unwired; delete in phase 2 once chat traffic
  confirms nothing is missed.

### i18n

- Full EN + TH copy for the new shell (`nav.home`, `home.*`,
  `money.*`, `when.*`, `settings2.*`). ThuraGirl speaks first-person
  Thai (หนู) about work she has done.

---

## v12.2 — 2026-05-10

Real create-invoice flow from the chat-bar `+` and ⌘K. Replaces the
legacy upload-banner hero modal that used to ship people through the
“drop a receipt” marketing screen when they tapped “Create invoice”.

### Changed

- **Chat-bar `+` → “Create invoice”** now opens a real invoice
  creation modal instead of the upload hero banner. Same modal
  is wired to the ⌘K palette’s “New invoice” action (was
  routing to `/onboard?step=first-invoice`, which dropped users
  at the start of onboarding).
- New `components/create-invoice-modal.tsx` exposes
  `openCreateInvoiceModal({ customer? })`. Two-state flow
  (form → result with invoice preview, PromptPay QR, three Send
  options, mascot celebrate). Bottom-sheet on `<md`,
  centered modal (`max-w-[600px]`) on `md+`. Backdrop click +
  Esc to close. Dark-mode parity. Persists to existing
  `thuragirl.firstInvoice` key plus a growing
  `thuragirl.invoices` array. Dispatches `thuragirl:invoice-created`
  on Done so any listening surface can refresh.
- Refactor: `InvoicePreview` and `SendOption` extracted from
  `app/onboard/page.tsx` into `components/invoice-preview.tsx`.
  Onboard step + new modal both import from there. No duplicated
  i18n keys (`onboard.first.*` reused). Two new keys:
  `onboard.first.done` and `onboard.first.modalTitle`.

---

## v12 — 2026-05-10

"The big one." Eight items per Chet's V12 feedback: power-user
palette, real-win onboarding, deep TH polish, mobile audit,
mascot-as-assistant, LINE prototype, PromptPay everywhere, bank
reconciliation. Dark-mode parity throughout. Lint held at v11
baseline (30 errors / 8 warnings).

### Added

- **⌘K command palette (item 1).** New `components/command-palette.tsx`
  built on `cmdk`. Opens with ⌘K / Ctrl-K (or click the top-bar
  "Search" button); mobile gets a full-screen sheet with a Mic
  button (browser-native `webkitSpeechRecognition`, locale-aware).
  Groups: Actions → Recent → Pages → Contacts → Employees → Files
  → Invoices. Top result auto-selected; Esc closes. Recent items
  persisted to `localStorage` (cap 5). Footer shortcuts hint on
  desktop. Custom `cmdk-item` styles in `globals.css` give
  full dark-mode parity and ≥44px tap targets on mobile.
- **First-invoice onboarding step (item 2).** Final step before
  `done`. Two fields (Customer name, Amount), pre-filled VAT 7%
  + line item "Services" + auto-incrementing `INV-2026-001`.
  Result screen shows a real-looking invoice preview, a
  scannable PromptPay QR (real EMV payload), three Send options
  (LINE / Email / PDF), and a 30-second mascot celebrate moment.
  First invoice persists to `localStorage` for the dashboard to
  ingest in future versions. Existing onboarding paths (new vs
  already-running) both end here.
- **Bilingual quality pass (item 3).** New `lib/format.ts` with
  `formatTHB`, `formatTHBProse`, `formatDate`, `formatDateNumeric`,
  `formatDateBE`, `formatMonth`, `formatDay`, `taxFormLabel`,
  `timeGreeting`. Decisions baked in (DECISIONS.md): CE years by
  default with explicit BE helper, dotted month abbreviations,
  polite imperative voice, hand-translated strings (no Google
  translate). Backwards-compat re-exports from `@/lib/utils`.
  ~80 new TH/EN i18n keys for the V12 surfaces.
- **Mobile audit (item 4).** People → Taxes per-person table now
  renders as a stacked card list at <md (avatar + name + role +
  net pay headline + 3-up Salary/PND.1/SSO grid + TIN status pill).
  Mobile bottom nav gets dark-mode parity and `min-w-[44px]` tap
  targets. (app)/layout root: `overflow-x-hidden`. Top bar
  hard-coded white → dark-mode parity. Login inputs bumped to
  h-12. New buttons across V12 use min-h-44 (primary) / 36 (icon).
- **Mascot as assistant (item 5).** New `lib/mascot-copy.ts`
  centralizes ThuraGirl one-liners with EN+TH variants per
  surface and a stable-seed picker so repeats don't shimmer.
  Tone rules in the file's header. Wired into Login (time-aware
  greeting tagline), onboarding first-invoice celebrate banner,
  reconciliation result banner, and the Today's focus hero (now
  signs "ThuraGirl says · today").
- **LINE integration prototype (item 6).** New `components/line-integration.tsx`:
  a `LineConnectCard` (settings tile, mock OAuth modal, persisted
  `connected` + `handle` state) and a global `LineSendModalHost`
  driven by `openSendViaLine({ invoice, amount, defaultCustomer })`.
  Wired surfaces: settings/integrations (featured at top), money
  receivables ("Remind via LINE" on every overdue row), inbox
  (3 mock inbound LINE messages with Mark paid / Reply quick
  actions). Send modal shows a faithful LINE-style preview
  bubble; the message is i18n'd via `line.send.message`.
- **PromptPay QR (item 7).** New `lib/promptpay.ts` builds the
  EMVCo + Thai MAI payload string by hand (CRC-16/CCITT-FALSE).
  New `components/promptpay-qr.tsx` renders the SVG via
  `qrcode.react` with a bilingual scan caption and a copy-link
  button. Recipient resolution: 13-digit tax ID by default,
  fallback to Thai mobile (`0066XXXXXXXXX`). Mounted on the
  onboarding first-invoice result screen; LINE send modal embeds
  a deep-link to the same payment URL.
- **Bank reconciliation (item 8).** New `components/reconciliation.tsx`
  mounted as a `#reconciliation` anchor section under Money
  Receivables/Payables (cmdk action `Open bank reconciliation`
  links here). Three columns: Matched (auto-confirmed),
  Suggested (one-click confirm or reject), Unmatched (manual
  invoice-picker dropdown). Confidence ladder: high (amount +
  ref/desc match), medium (amount within ±0.50 THB only), low
  (no candidate). Bank format auto-detected by header sniff
  (K-Bank, SCB, BBL); permissive CSV parser with column-alias
  detection. "Mark all matched as paid" CTA fires a mascot
  celebrate banner. New `public/sample-kbank-statement.csv`
  ships an 8-row sample (4 of which match outstanding
  receivables) so users can try the flow without their real
  data.

### Status

| # | Item | Status |
|---|------|--------|
| 1 | ⌘K command palette | ✅ shipped |
| 2 | Onboarding ends with first invoice | ✅ shipped |
| 3 | Bilingual quality pass (helpers + ~80 keys) | ✅ shipped |
| 4 | Mobile audit | ✅ shipped (people taxes, bottom nav, top bar dark, root overflow-x-hidden) |
| 5 | Mascot as assistant | ✅ shipped (login, today-focus, onboard, recon) |
| 6 | LINE integration prototype | ✅ shipped (connect card, send modal, inbox messages, money remind) |
| 7 | PromptPay QR | ✅ shipped (lib + component, on onboarding first-invoice + LINE send link) |
| 8 | Bank reconciliation | ✅ shipped (3-column view, sample CSV, confidence ladder) |

### Files

New:
- `src/lib/format.ts` — locale-aware date/currency helpers
- `src/lib/promptpay.ts` — EMVCo PromptPay payload generator
- `src/lib/mascot-copy.ts` — mascot lines (en/th, variants)
- `src/components/command-palette.tsx`
- `src/components/promptpay-qr.tsx`
- `src/components/line-integration.tsx`
- `src/components/reconciliation.tsx`
- `public/sample-kbank-statement.csv`

Updated:
- `src/lib/i18n.tsx` (~80 keys), `src/lib/utils.ts` (re-exports)
- `src/app/(app)/layout.tsx` (palette mount, send-line host, top-bar dark, overflow-x-hidden)
- `src/components/global-search.tsx` (became palette trigger)
- `src/components/mobile-bottom-nav.tsx` (dark parity, tap targets)
- `src/app/login/page.tsx` (mascot greeting, full i18n, h-12)
- `src/app/onboard/page.tsx` (first-invoice step before done)
- `src/app/(app)/page.tsx` (today-focus signed by ThuraGirl)
- `src/app/(app)/inbox/page.tsx` (LINE messages mock)
- `src/app/(app)/money/page.tsx` (LINE remind on overdue, recon section)
- `src/app/(app)/people/page.tsx` (mobile stacked card on taxes)
- `src/app/(app)/settings/page.tsx` (LineConnectCard at top of integrations)
- `src/app/globals.css` (cmdk styles, sheet animation, top-bar chrome dark)
- `package.json` (cmdk, qrcode.react)

### Constraints met

- `npm run build`: clean, 0 TypeScript errors.
- `npm run lint`: 30 errors / 8 warnings (= v11 baseline; no regression).
- Dark mode: parity for every new/changed surface.
- Routes: all v11 routes still 200; no new routes added (recon
  lives at `/money#reconciliation` to keep the surface count
  stable).
- Brand kit / mascot / B2 system unchanged; pink stays mascot-only.

### Deviations from spec

- Bank reconciliation lives as an anchored section on `/money`
  rather than as a dedicated `/money/reconciliation` route.
  Spec said "new page or new top-level under Money" — keeping
  it on the same page preserves the existing periodic context
  (period picker, snapshot) and means the cmdk action is a
  hash-link rather than a route. Trivial to split if desired.
- TH localization is comprehensive on V12 surfaces (cmdk, login,
  onboard.first, line, recon, promptpay, mascot) and on the
  pre-existing high-traffic surfaces, but the onboard wizard's
  v7 "Brand new" path strings (DBD search, e-sign step, status
  spinner) remain English-only. Acceptable: that path is
  used once per company and deferred to V13.
- PromptPay QR is shown on the onboarding first-invoice result
  screen and via the LINE send link; we did not also add a QR
  to every existing invoice in `/files` (no current invoice
  detail page — would require new routes). The infrastructure
  (`<PromptPayQR>` component) is ready for that V13 surfacing.

---

## v11 — 2026-05-10

Layout-fit + simplification pass per Chet's V11 feedback. Theme:
"Sections by frequency, not equality. Fit the layout. Align the
chrome. Always make it simpler." Four items shipped. Dark-mode
parity throughout.

### Changed

- **Files page — frequency grouping.** `DOCUMENT_FOLDERS` reordered
  to `Invoices → Receipts → Tax Filings → HR → Contracts → Legal`
  in `src/lib/mock-data.ts`. Two new exported zones
  (`DOCUMENT_FOLDERS_FREQUENT`, `DOCUMENT_FOLDERS_OCCASIONAL`) drive
  the UI split. Desktop sidebar renders the two groups under
  uppercase "Frequent" / "Occasional" dividers; Frequent rows are
  taller with bolder count badges, Occasional rows are denser and
  lower-contrast. Mobile pill row keeps the same order with a thin
  vertical spacer between Tax Filings and HR. "All files" stays at
  the top of both surfaces.
- **Money P&L + Tax row — grid fix.** Was `lg:grid-cols-3` with
  only two cards (phantom third column, both narrower than they
  should be). Now P&L spans `lg:col-span-2` (2/3) and Tax stays in
  the remaining 1/3, applied via `AnchorTile` (now accepts a
  `className`). Both inner cards are `h-full flex flex-col` so
  bottom edges align. Removed the stale inner `lg:col-span-2` on
  ProfitLossCard's outer div (was a no-op once AnchorTile wrapped
  it, but confusing).
- **Settings sidebar alignment.** Aside lost `self-start`, grid
  uses `items-start`, and the sticky/max-height now lives on the
  inner panel: `lg:sticky lg:top-16 lg:max-h-[calc(100vh-5rem)]
  lg:overflow-y-auto`. Result: no more rail floating below short
  tab bodies (Notifications, Preferences, Security), and on tall
  bodies the rail still sticks but stays within the viewport.

### Added

- **Today's focus hero (idea A).** New mascot-delivered card at the
  top of the dashboard with a single sentence summarizing the one
  thing the user should do today. Derived from
  `pickTodayFocus(critical, scheduled, fin)`: prioritizes blocking
  sign-offs → most-overdue → next due → cash-thin warning → calm
  fallback. Click-through CTA deep-links to `/inbox` (or `/money`
  for the cash case). Tone-aware surface (warn / info / calm).
- **Auto-categorize uploads (idea D).** `suggestFolderForFilename`
  helper in `mock-data.ts` maps filename patterns to folders
  (INV-* → Invoices; *receipt|makro|lazada* → Receipts;
  PND/PP30/SSO → Tax Filings; *payslip|payroll|handbook* → HR;
  *contract|lease|MSA|NDA* → Contracts; *articles|resolution* →
  Legal). `UploadModalHost` captures the picked filename and forwards
  it to `UploadFlow`. The flow surfaces the suggested folder as a
  teal sparkle pill ("Filing to: <Folder>") during processing and
  reflects it in the booked summary. The "unsure category"
  clarification branch pre-selects the matching choice so confirm is
  one click instead of a fresh decision.
- **Smart period defaults (idea F).** Dashboard's initial
  `PeriodValue` is derived from today's date: `mtd` if it's the
  5th-or-later, otherwise `qtd` (the closest existing preset that
  still includes the freshly-closed previous month — we don't have
  a `lastMonth` preset and didn't restructure the picker for v11).

### Notes

- Build clean (`npm run build` — 0 TS errors, lint baseline
  unchanged at 30 / 8).
- All 14 routes prerendered (`/`, `/money`, `/files`, `/people`,
  `/contacts`, `/inbox`, `/settings`, `/brand-kit`, `/brand`,
  `/login`, `/onboard`, etc.).
- Pink stays mascot-only. No new gradients introduced.
- Deferred from V11 (logged in DECISIONS.md): idea B (⌘K command
  bar), idea C (Files↔Inbox merge), idea E (inline-edit Contacts),
  idea G (swipe/drag actions on tasks).

---

## v10 — 2026-05-08

Structural cleanup pass per Chet's V10 feedback. Goal: "Strip the
redundant chrome. Trust the nav. Polish what's left." Eight items
shipped. Dark-mode parity from day one for everything new.

### Added

- **`PageToolbar` component** (`src/components/page-toolbar.tsx`).
  Slim per-page controls strip that replaces the old big page
  heading. Optional `sticky` mode pins it just under the top bar on
  mobile so tabs/search stay reachable while scrolling.
- **`TopBarBreadcrumb`** (`src/components/top-bar-breadcrumb.tsx`).
  Desktop-only dim-text echo of the current section, sitting where
  the company name lived in v9.
- **`GlobalSearch`** (`src/components/global-search.tsx`). Slim
  search input in the desktop top bar. On focus or Enter it hands
  off to the persistent chat with the typed value as the draft —
  keeps the "all queries via chat" decision intact while giving
  users the search-shaped affordance they expect.
- **`EmptyState` component** (`src/components/empty-state.tsx`).
  One restrained pattern shared across surfaces. Supports a
  mascot variant (Inbox, People) and an icon variant (Money,
  Files, Contacts) with optional CTA.
- **`TaskZone` (Dashboard)**. Stack-ranked Critical / Scheduled /
  Done-this-week zones with kicker labels, breathing room, and a
  red animated dot on Critical. "Done this week" pulls from the
  existing autoHandled tasks (dim'd to match lower priority).
- **Money KPI chevron-down affordance.** Each clickable Money KPI
  tile now shows a 12px Lucide `ChevronDown` at its bottom-right
  corner (teal-500/40 light, teal-300/40 dark, brightens on hover).
  Tells the user "click for breakdown" without a label.
- **Files page search input.** Lifted into the new toolbar; filters
  by file name / folder / type.
- **Empty states** for Inbox (mascot), Money (zero-data period),
  Files (empty folder + upload CTA), Contacts (customers + vendors
  with chat-driven add CTA), People (mascot + invite CTA).
- **i18n keys** for `topbar.searchPlaceholder`, `tasks.zone.*`,
  `empty.*`, `nav.brandKit`, `files.searchPlaceholder` (en + th).

### Changed

- **All `/(app)` page headings removed** (item 1). Affected:
  Dashboard, Inbox, Contacts, Files, People, Money, Settings.
  Page-level controls (period picker, tab switcher, search, CTAs)
  lifted into the `PageToolbar`. Login, onboard, and brand-kit
  keep their headings (those aren't main-nav routes).
- **Top bar slim** (item 2). Desktop drops the serif company
  name; the left company rail already conveys current company.
  New layout: hamburger/collapse toggle → dim breadcrumb →
  global search → theme toggle. Mobile keeps the company
  switcher button (rail is desktop-only); the icon-variant
  theme toggle stays in the top right on both viewports.
- **Sidebar footer empty.** The theme toggle moved to the top
  bar; the sidebar bottom slot is now intentionally empty for a
  cleaner rail.
- **Inbox sign-off cards calmed down** (item 3). White / dark
  surface, no teal gradient wash, no halo, no floating-mascot
  artifact in the corner. Teal accent kept only on the
  "Sign off" pill and the primary `Sign off & file` button.
  Compiled-file row uses a neutral `[#fafafa]` surface instead
  of a teal-tinted one.
- **Dashboard Tasks restructured** (item 4). Was a flat 4-row
  list; now three labeled zones with extra breathing room and a
  per-zone empty fallback line.
- **Settings restructured** (item 6). 10 flat tabs grouped:
  Top (Account / Security / Notifications / Preferences) +
  Workspace (Company / Shareholders / Directors / Team /
  Billing / Integrations). Desktop renders a split sidebar
  inside Settings (3-col nav + 9-col body). Mobile renders a
  pill-row for top tabs + a collapsible Workspace accordion;
  the accordion auto-expands when a workspace tab is active.
  Decision logged in `docs/DECISIONS.md`.
- **Payroll: single state-aware button** (item 7). The two
  stacked buttons on the Next Payroll Run card are gone.
  Replaced with one `PayrollActionButton`:
  - pre-confirm: amber outline + "Confirm leave data"
  - post-confirm: teal solid + "Approve payroll"
  Smooth label/color transition via Framer Motion's
  `AnimatePresence` so the button itself never jumps.
  Approval triggers a one-shot alert (still mocked).

### Decisions

Three non-obvious calls logged in `docs/DECISIONS.md`:

1. Page heading removal across (app) routes.
2. Top bar slim (drop company switcher, add breadcrumb +
   global search + theme toggle).
3. Settings restructure (split sidebar inside Settings on
   desktop; pill row + accordion on mobile).

### Notes

- Brand kit, mascot, B2 system, and pink-as-mascot-only rule are
  untouched (locked).
- Pre-existing recharts width(-1)/height(-1) warnings during
  static generation persist; not introduced or worsened by v10.

---

## v9 — 2026-05-08

Visual + structural cleanup pass per Chet's V9 feedback. Goal: cut
redundancy, less time in the app, dark-mode parity from day one.
Four items shipped.

### Added

- **Custom date-range picker** (`PeriodPicker`). Drop-in replacement
  for the previous Tabs-based period toggle. Adds a "Custom" pill
  that opens a Framer-Motion popover with from / to date inputs and
  three quick presets (Last 7d / 30d / 90d). Wired into Snapshot
  (Dashboard) and Money page period state. Custom selections compute
  a deterministic snapshot from the day-span via the new
  `financialsForRange(from, to)` helper in `lib/mock-data.ts` — KPIs,
  series, breakdowns, and tax position all scale linearly off MTD
  with a stable seeded wobble per range. Dark-mode parity from day
  one.
- **Snapshot KPI deep-links.** The four dashboard KPI tiles (Cash /
  Revenue / Expenses / Profit) are now `<Link>`s to
  `/money#card-{cash|revenue|expenses|profit}`. Money page reads the
  hash on mount, smooth-scrolls into view (with `scroll-mt-24` offset
  for the top bar), and pulses a teal `ring-2` highlight on the
  matching tile for 1.5s. Hover lift on the dashboard tiles signals
  they're clickable.
- **Anchored KPI tiles on Money** (`#card-cash`, `#card-revenue`,
  `#card-expenses`, `#card-profit`).
- **Per-row Share button** in the Company Vault. Sits next to View /
  Download. Click copies a share link to the clipboard and shows a
  brief "Link copied" toast in the corner of the vault card.
- **`scroll-behavior: smooth`** on `<html>`, gated by
  `prefers-reduced-motion`.

### Changed

- **Money: filing status folded into Tax position card.** The
  previous standalone Tax tracker row at the top of the Money page is
  gone; the same 4-form chip grid (PND.1 / PND.3 / PP.30 / SSO) now
  lives inside the Tax position card as a collapsible "Filing
  status" subsection (default closed, caret + summary pill showing
  overdue / pending count). One tax surface on the page, less
  redundancy.
- **Money: Receivables and Payables collapsed by default.** Each
  side now shows a summary header (total + count + "X overdue" pill)
  with a "Show N invoices / bills" expand button. Click to slide the
  inline table open with a Framer-Motion height animation.
- **Dashboard: Attention card demoted.** Smaller header (kicker-style
  "ATTENTION" + count), smaller icons (3x3), tighter rows,
  truncated body text, no halo, no gradient. Tasks card stays the
  prominent dashboard surface. See `docs/DECISIONS.md`
  ("Attention vs Tasks — demote, don't merge") for the call.
- **PERIODS now polymorphic** at the call site: pages hold a
  `PeriodValue` discriminated union (`{kind: "preset", key} | {kind:
  "custom", from, to}`) and route through `FINANCIALS[key]` or
  `financialsForRange(from, to)` accordingly.

### Fixed

- Recharts `width(-1) height(-1)` warnings during static generation
  remain pre-existing (unchanged from v8) — they don't affect runtime
  rendering.

---

## v8.0.1 — 2026-05-08

### Added

- **Light / Dark / System theme toggle.** Lives in the sidebar bottom-left
  slot (where the FY/industry chip lived in v7, removed in v8). Three-state
  segmented control with sun / moon / monitor icons. Persists to
  `localStorage["thuragirl.theme"]`. System mode follows
  `prefers-color-scheme` and reacts live to OS-level changes. Mobile gets
  a compact icon-only variant in the top bar that cycles on tap.
- **Full dark theme.** New `.dark` design tokens (background, card,
  section, border, text). Dark variants for every gradient surface
  utility (`surface-teal/warm/cool/violet/card`), KPI tile gradients,
  card halos, and Apple shadows. Recharts tooltips + axis labels +
  grid lines auto-adapt via CSS overrides. No-flash inline script in
  `<head>` paints the dark class before React hydrates.
- **`@custom-variant dark` directive** in `globals.css` so Tailwind v4
  `dark:` modifiers work against `.dark` on `<html>`.
- **Global CSS overrides for dark mode.** Rather than touching every
  hardcoded hex in 50+ components, attribute-selectors flip the
  dominant patterns (`.bg-white`, `.text-[#0a0a0a]`, `.border-[#ececef]`,
  tinted chip backgrounds, hover states) under `.dark *`. Components
  needing custom dark looks still win via `dark:` variants.
- **Per-tone KPI gradient tiles** (`kpi-tile-teal/emerald/amber/violet/rose`).
  Dashboard and Money KPIs now have semantic gradient personalities
  instead of four identical grey blocks (cash=teal, revenue=emerald,
  expenses=amber, profit=violet, tax=rose).
- **Card halo utility** (`card-halo-teal/amber/violet`). Soft radial
  bloom in the top-right corner of important sections. Used on
  Dashboard Snapshot (teal) and Attention (amber) cards to create
  visual hierarchy without dominating.
- **`tone` prop on `KpiTile`** for opt-in per-metric gradients.

### Changed

- **Dashboard Snapshot card** now uses `surface-teal` + teal halo so
  the primary section reads warmer than flat white. Inner chart panel
  has dark-aware gradient stops.
- **Dashboard Attention card** uses `surface-cool` + amber halo to
  visually balance the Snapshot card on the left.
- **Sidebar active nav state** now bright in both themes (was nearly
  invisible in dark). Active label is now full-foreground colored with
  a teal-tinted gradient pill behind it.
- **`text-[#9ca3af]` in dark** lifted from `#7a808b` to `#8a909b` for
  legibility on small labels.
- **Money page KPIs** opt into per-tone gradients (cash/revenue/profit
  etc. each tinted).

### Fixed

- **Chat bar click no longer opens the panel.** The v8 toggle change
  over-corrected: clicking the (closed) input fired `onFocus` →
  `setExpanded(true)` and then immediately `onClick` saw
  `expanded && empty draft` and closed it back. Net effect: the bar
  appeared dead. Fix: capture the input's pre-click focus state on
  `onMouseDown`. Toggle-close now only fires when the input was
  *already* focused before the click started. Behavior matrix now:
  - closed → click → opens & focuses
  - open (not focused) + empty → click → focuses, stays open
  - open + focused + empty → click → closes (the v8 toggle)
  - open + non-empty draft → click → stays open (never discards typed
    text)
- **Unicode escape leakage in JSX text.** Several v8 strings were
  written as their `\uXXXX` source-form escapes inside JSX text
  children rather than as real characters. JSX renders those
  literally, so the live UI was showing things like
  `Today at a glance \u2014 what needs you` and
  `Revenue \u00b7 expenses \u00b7 cash trend`.
  Globally converted `\u2014`, `\u00b7`, `\u2192`, `\u201c\u201d`,
  `\u0e3f`, surrogate-pair emoji escapes, and a handful of related
  glyphs to their real characters across `src/**/*.{ts,tsx}`.
  Touched: dashboard page, files page, mobile-bottom-nav.
  Skipped: `persistent-chat-bar.tsx` (escapes there are inside a
  regex char-class range and are correct as written).

---

## v8 — 2026-05-08

Visual polish + UX cleanup pass per Chet's V8 feedback. Goal: get from
"feels backend" to "feels delightful." 18 items shipped.

### Added

- **Mobile bottom-tab navigation** (`mobile-bottom-nav.tsx`). Six thumb-friendly
  tabs (Dashboard / Inbox / Contacts / Files / People / Money). Sidebar
  hides on mobile; bottom nav appears. Chat bar lifts above the tabs.
- **Gradient surface utilities** in `globals.css`: `surface-teal`,
  `surface-warm`, `surface-cool`, `surface-violet`, `surface-card`,
  `bg-gradient-teal`, `bg-gradient-teal-soft`, `gradient-text-teal`,
  `ring-glow-teal`. Tasteful, low-saturation gradients used to add
  warmth and direction. Pink stays reserved for mascot.
- **Files page** (`/files`) replacing `/documents`. Designed Upload
  button (gradient + sparkle), per-row View/Download visible by
  default, drag-and-drop hint card on the desktop folder rail.
- **Company Vault** (renamed from Foundational Vault). Warm gradient
  surface, lock badge, per-doc View/Download on hover.
- **Per-item Attention deep-links** on the Dashboard. Each
  notification routes to the most specific record we can infer
  (overdue invoice → Contacts, payroll → People, etc.).
- **Settings: Account, Security, Notifications** — three new tabs.
  Security stack: 2FA toggle, password change with show/hide,
  active sessions list with sign-out-all-others, login alerts (email
  / push / unrecognised-device), recovery email with verified state,
  audit log with CSV export. Plus a "posture" hero card surfacing
  current account-security state at a glance.
- **Contacts CTAs designed**: New quote / New invoice / New PO are
  now real designed buttons (gradient + shimmer for primary,
  teal-on-hover for outline). Clicking opens the persistent chat
  with a pre-filled draft so creation flows conversationally.
- **Payroll: leave-data status indicator** + **Confirm final leave
  data** button on the Next Payroll Run card. Status pill flips
  amber → emerald once confirmed; payroll-approve button is gated
  until leave is confirmed.
- **P&L card rebuild**: real revenue/expense breakdown across two
  columns, per-line bar viz, gross/operating/net profit blocks,
  margin chips, estimated tax line. Card now fills its space.

### Changed

- **Section icon family refreshed** across sidebar + new mobile bottom
  tabs: LayoutGrid (was LayoutDashboard), IdCard (was Contact),
  FolderOpen (was FolderClosed). Stroke widths tuned per active state
  (1.8 default / 2.2 active) for a tighter rhythm.
- **"Documents" → "Files"** everywhere (i18n, nav, route, internal
  labels, upload-flow success state, mock task titles).
- **Sidebar footer chip removed** (the FY/industry "restaurant FY Jan–Dec"
  block at the bottom of the sidebar).
- **Tax tracker sort order**: now Overdue → Pending → Filed
  (urgency-first) on the Money page.
- **Per-person tax "Total" row** redesigned. Old `<tfoot>` looked
  like a stray table row; replaced with a 4-tile summary block
  (Total salary / PND.1 / SSO / Net pay) on a gradient surface.
- **Dashboard Snapshot card**: small sparkline replaced with a richer
  ComposedChart (revenue area + expense bars). Card fills its
  vertical space; KPI tiles now use a subtle accent on Cash.
- **Dashboard Attention card**: internal scroll (max 360px) so long
  lists never blow out the row height.
- **Chat bar toggle**: clicking the type-fill while the panel is
  open and the input is empty now closes the panel back down. No
  need to reach for the chevron.
- **Payroll number input vertical alignment** (the "cursor cuts
  through 0" glitch). Bumped height from h-8 to h-9 with leading-none
  so the caret stays on-glyph.
- **Contacts header CTAs** wired to the chat with sensible drafts.

### Removed

- Old `/documents` route directory.
- Unused `ExpandablePLRow`, `AnimatePresenceLite`, and `PLRow`
  helpers from the Money page (replaced by the new P&L breakdown).
- Legacy sidebar footer chip (FY + industry).

### Notes

- Pre-existing recharts "width(-1) height(-1)" warnings during static
  generation are unchanged — not introduced in v8.
- Brand kit, mascot, and B2 system are untouched per spec.

---

## v7 — 2026-05-07

Major scope expansion: pre-login, onboarding wizard, vendors/customers,
notifications, receivables/payables, payroll leave handling, payslips,
contract expiry, vault docs, tax tracker.

### Added

- **`/login`** — pre-login screen. Centered mascot, simple form, accepts
  any email/password (prototype). Routes to dashboard on submit.
- **`/onboard`** — multi-step onboarding wizard.
  - Path picker: Brand new business vs Already running.
  - Steps (new): Type → DBD name search → Auto-filled form → e-Sign →
    Filing status animation → Integrations → VAT/SSO → Done.
  - Steps (existing): Type → Integrations → VAT/SSO → Done.
- **`/contacts`** — combined Customers + Vendors page.
  - Per-row: avatar, category, payment terms, 12-month rollup.
  - Side-sheet detail: tax ID, contact info, rollup, action buttons.
  - Top CTAs: New invoice / New quote (Customers), New PO (Vendors).
  - Banner explains chat-driven creation flow.
- **Foundational Vault** at top of `/documents`. 4 groups:
  Registration / Tax IDs / Licences / Other. 8 mock docs including
  DBD certificate, Articles of Association, BOJ-5, VAT Phor.Por.20,
  restaurant licence, food safety cert, TIN, bank account opening.
- **Receivables & Payables tracker** on `/money`. Side-by-side cards
  with overdue/upcoming flags, last-reminder dates, totals.
- **Tax tracker** always visible at top of `/money`.
  Four cards: PND.1, PND.3, PP.30, SSO. Status pills (Filed / Pending
  / Overdue), period, due date.
- **Notifications card** ("Attention") on Dashboard. Five mock items:
  deadlines, alerts, milestones, reminders. Color-coded icons,
  click-through links.
- **Add-company picker modal** on Company Rail "+". Routes to /onboard.
- **Payroll leave-data uploader** on People > Payroll tab.
  - Toggle: "Fill per person" (number inputs per employee) or
    "Upload file" (CSV / XLSX / PDF drop).
  - Banner: "ThuraGirl recalculated payroll based on N leave days".
- **Payslips per employee**. Side panel section listing recent payslips
  with View + Download (mocked). Net / PND.1 / SSO breakdown per slip.
- **Contract expiry tracker**. Per-employee block in detail sheet.
  Type / start / end. ≤90 days to expiry → amber warning + "Renew
  contract" / "Convert to permanent" actions.
- **Integration last-sync time** on Settings > Integrations. Live /
  Slow / Connection-status pill + "Sync now" button per integration.
- **Upload error/uncertainty handling** in `upload-flow.tsx`.
  Random ~25% of uploads now branch to:
  - "Couldn't read it" (blurry/cropped) — retry / manual entry / skip
  - "Need a hand" (low confidence on category) — confirms via chips,
    then files.

### Changed

- **Dashboard rename**: page header "Tasks" → "Dashboard". Layout
  reordered: Snapshot + Attention top row, Tasks below.
- **Sidebar nav**: added "Contacts" entry between Inbox and Documents.

---

## v6.2 — 2026-05-07

### Fixed

- **Mobile chat bar visibility**. Was clipped below visible viewport on
  mobile Safari/Chrome (URL bar takes height). Switched layout from
  `h-screen` to `100dvh` + `viewportFit: cover` + `env(safe-area-inset-bottom)`
  padding so the bar always sits cleanly above iOS home indicator.

---

## v6.1 — 2026-05-07

### Added

- **Tasks/items translate to Thai**. Full task titles, descriptions,
  due-labels (Due today / Overdue 14 days / Due in N days), and
  category badges (ภาษี / ใบกำกับ / เงินเดือน / กฎระเบียบ / ใบเสร็จ).
- **Document chat lookup**. Type "find my tax filing" / "where's the
  Makro receipt" / "show invoice 041" — chat returns matching files
  inline as cards with View + Download.
- **Sidebar collapse toggle**. Left of company name, persists to
  localStorage. Doesn't touch the company switcher rail.
- **Noto Sans Thai** font fallback for proper Thai glyphs.

### Fixed

- **Right-shift on filter/tab change** (Inbox, Documents, People).
  Root cause: scrollbar appearing/disappearing on content height
  change. Fixed with `scrollbar-gutter: stable` globally + on the
  scroll container. Inbox detail panel converted to slide-in overlay
  so list never reflows.
- **Font weight too heavy**. Switched Geist → **Manrope** (lighter at
  same numeric weight). Tracking relaxed to -0.012em.

---

## v6 — 2026-05-07

### Added

- **In-place expanding chat bar**. Typing in the chat bar grows it
  upward into a 56vh message panel anchored to bottom. No more
  sidebar drawer (`ThuraChatPanel` removed from layout). Bubbles +
  typing dots + chevron to collapse.
- **EN / TH language toggle** in Settings > Preferences.
  Persists in localStorage. Natural Thai (สวัสดี / ภาษีอากร / รายได้).
- **Money: expandable Profit & Loss**. Revenue / CoGS / Operating
  expenses tap to expand into sub-categories with progress bars.
- **Money: Revenue Mix toggle**. Channels / Products / Customers
  lens — Customers shows Walk-in / Shopee / GrabFood / LINE MAN /
  TikTok Shop / Corporate split.
- **Settings > Company tab Edit button**. Read-only by default, tap
  Edit → fields become inputs, Cancel / Save changes appear.
- **Native file picker on action-sheet uploads**. Take photo /
  Choose photo / Scan document / Scan text / Attach file all
  trigger the OS picker directly, with appropriate `accept` + `capture`
  hints, then the post-upload progress modal.

### Changed

- **Top header chevron removed** next to company name.
- **Inbox tax repetition fixed**. Right-side detail panel no longer
  auto-selects first task (which was always the Tax sign-off).
- **Font** switched to Geist; later replaced by Manrope in v6.1.
- **People tab name**: "Per-person tax" → "Taxes" (per-person
  breakdown is what shows up inside).

---

## v5 — 2026-05-07

### Added

- **EN / TH toggle infrastructure** (i18n provider + dictionaries).
- **Documents redesign**: list table layout, no thumbnails. Compact
  rows: icon + filename + folder + type/size + date + category badge.
- **Inbox Sign-off cards: compiled file attachment** per package.
  Single bundled artifact with View + Download.
- **Money tax card rebuilt**. Estimated tax owed → VAT in/out tiles
  → 5-category deductibles with progress bars → "Potential savings"
  callout → breakdown rows → "View full tax report →".
- **People > Onboard CTA** — gradient teal hot button with shine
  sweep on hover.
- **Per-person Tax tab** in People (separate from Inbox compiled
  filing). Per-employee PND.1, SSO, net pay, Tax ID Missing flags.

### Changed

- **Tasks: distinct category chips vs urgency pills**.
  Categories: Invoice = teal, Receipt = amber, Tax = purple,
  Payroll = indigo, Compliance = rose. Urgency: 🔴 overdue
  (animated dot), 🟠 due today/soon, ⚪ upcoming. "Most urgent"
  pill removed.
- **Action sheet context-aware**. Task uploads use `mode:"task"`
  (no "Create invoice"). Chatbar plus uses `mode:"full"`.
- **Sidebar plus icon**: dashed border removed, clean ring-1.
- **Inbox**: search bar removed (queries route to chat).
- **People > Team**: "/ month" inline on one row.
- **Top header**: search icon removed; company name in
  Instrument Serif display font.
- **Chat bar flicker fix**: rebuilt placeholder rotator with
  opacity-only crossfade (stacked spans, no remount, no y-translate).

---

## v4 — 2026-05-06

(Initial design pass before this changelog. See `git log` for raw
commits and `memory/2026-05-07.md` in the workspace for the
day-of summary.)

Highlights:

- App-wide branding tokens (teal #0fbfb6, mascot pink #ec4899).
- Multi-company architecture (Slack-style rail + bottom-sheet on mobile).
- Phantom-style top bar (blur on scroll, tight padding).
- Persistent chat bar with task context.
- 6 main pages (Dashboard, Inbox, Documents, People, Money, Settings).
- Mascot variations: A1/A2 (clerky), B1/B2/B3 (cute + competent).

---

## v1 — 2026-05-06

Initial scaffold. Backed up at
`~/.openclaw/workspace/projects/thuragirl-prototype.backup-v1`.

---

_Maintained by Garlic 🧄 (`agent=main`)._
