# 🍱 TiffinBox — Complete Gemini Frontend Prompts
**MVP v1.0 · Pure HTML + Tailwind CSS + Vanilla JS · All Pages Organized**

---

## 🎨 GLOBAL DESIGN SYSTEM (Read Before Every Prompt)

> **Paste this block at the START of every Gemini prompt as context:**

```
GLOBAL DESIGN SYSTEM FOR TIFFINBOX:
- Stack: Pure HTML + Tailwind CSS CDN + Vanilla JS (no frameworks)
- Fonts: Google Fonts — Syne (headings/display) + Outfit (body). Add via <link> tag.
- Primary accent: Amber #F5A623
- User app theme: Dark (#0D0D0D base, #1A1A1A cards, #2A2A2A elevated cards)
- Cook app theme: Light (#F9FAFB base, white cards)
- Admin panel theme: Neutral (#F3F4F6 base, white cards)
- Responsive breakpoints: mobile-first (375px+), tablet (768px+), desktop (1024px+)
- All pages must be fully responsive across mobile, tablet, and desktop
- Tailwind CDN: <script src="https://cdn.tailwindcss.com"></script>
- Custom colors via Tailwind config in <script> tag
- No external component libraries — only Tailwind + custom CSS in <style> tags
- Every page = one complete self-contained HTML file
- Include realistic placeholder content (Indian names, dishes like Rajma Chawal, Dal Makhani, ₹ prices)
```

---

## 📁 SECTION 1: USER-FACING APP (Dark Theme)
*10 main screens + sub-pages/modals*

---

### PROMPT 1.1 — Landing Page

```
You are a senior UI/UX developer. Build a complete, production-ready, single HTML file for the TiffinBox landing page.

GLOBAL DESIGN SYSTEM:
[Paste the global design system block above]

PAGE PURPOSE:
Convert first-time visitors into sign-ups. Must answer in <5 seconds: What is this? Is it near me? Can I trust it?

COMPLETE PAGE SECTIONS (build all of these):

1. NAVBAR
   - Logo left: "🍱 TiffinBox" in Syne font, amber color
   - Nav links center (desktop): How It Works, Browse Food, For Cooks
   - Right: "Sign In" (ghost button) + "Get Started" (amber filled button)
   - Mobile: hamburger menu that slides in a full-screen overlay nav
   - Sticky on scroll with subtle backdrop blur

2. HERO SECTION
   - Full viewport height
   - Dark background #0D0D0D with an amber radial glow emanating from center-behind the headline
   - Headline in Syne: "Home food. Daily." — very large (clamp 48px–96px)
   - Subheadline in Outfit: "Subscribe to verified home cooks near you."
   - Location search bar (large, rounded-full): placeholder "Enter your locality or area..." with a "Find Cooks →" amber button
   - Trust bar below search: "340+ verified cooks · Pause anytime · From ₹80/day" in small muted caps with dot separators
   - Background: subtle noise texture overlay, very faint

3. FEATURED FOOD CARDS STRIP
   - Section heading: "Trending near you"
   - Horizontally scrollable row of 4 food cards (hide scrollbar)
   - Each card (280px wide): large food photo (use gradient placeholder), dish name bold, cuisine + diet tag, cook name small muted, ★4.8 rating, ₹2,800/mo price, "View Plan" amber button
   - Card dark background #1A1A1A, rounded-2xl, hover lift effect

4. HOW IT WORKS
   - Section: 3 numbered steps in a row (stack on mobile)
   - Step 1: 🔍 Discover — "Browse verified home cooks near you"
   - Step 2: 📋 Subscribe — "Choose a weekly or monthly plan"
   - Step 3: 🚀 Receive — "Fresh home food at your door, daily"
   - Each step has large number (amber), icon, title, description

5. SOCIAL PROOF — TESTIMONIALS
   - Section heading: "Loved by 2,000+ subscribers"
   - 3 testimonial cards in a grid (1 col mobile, 3 col desktop)
   - Each: star rating (5 stars amber), quote text, name + city, avatar circle with initials
   - Dark cards with slight border

6. STATS STRIP
   - Full-width dark band: 4 stats in a row
   - "340+ Verified Cooks" | "12,000+ Meals Delivered" | "4.8★ Avg Rating" | "₹80/day Starting Price"

7. COOK CTA SECTION
   - Two-column layout (stacked mobile): left text, right illustration/mockup
   - Headline: "Are you a home cook?"
   - Subtext: "Turn your cooking skills into stable monthly income. Join 340+ cooks on TiffinBox."
   - Button: "Start Earning →" amber outline
   - Background: slightly lighter dark #1A1A1A section

8. FOOTER
   - Logo + tagline
   - Links: About, How It Works, Browse Food, Become a Cook, Privacy, Terms
   - Social icons (placeholder circles)
   - Copyright

INTERACTIONS (JavaScript):
- Hamburger menu toggle (mobile)
- Location search: on Enter or button click, show a toast "Searching for cooks near you..." then redirect simulation
- Navbar background changes on scroll (transparent → dark with blur)
- Smooth scroll for anchor links
- Fade-in animation for sections on scroll (IntersectionObserver)

DESIGN DETAILS:
- Amber glow: radial-gradient(ellipse at 50% 40%, rgba(245,166,35,0.15) 0%, transparent 70%)
- Cards have subtle amber border on hover: border-amber-500/30
- All CTAs use amber: bg-[#F5A623] text-black font-semibold
- Ghost buttons: border border-amber-500 text-amber-500 hover:bg-amber-500 hover:text-black
- Typography scale: display 96px, h1 64px, h2 48px, h3 32px, body 16px
- All sections have generous padding: py-20 on desktop, py-12 on mobile
- Smooth transitions: transition-all duration-300

Make it production-ready, beautiful, and pixel-perfect. One complete self-contained HTML file. Use realistic Indian content (localities like Koramangala, Baner, Andheri; dishes like Rajma Chawal, Dal Makhani, Chole Bhature; names like Sunita Sharma, Priya Mehta).
```

---

### PROMPT 1.2 — Sign Up / Login Page

```
You are a senior UI/UX developer. Build a complete, production-ready, single HTML file for the TiffinBox Sign Up / Login screen.

GLOBAL DESIGN SYSTEM: [Paste global block]

PAGE PURPOSE:
Zero-friction OTP-based authentication. No passwords. Phone number is identity.

THIS FILE CONTAINS 3 STATES (shown/hidden with JS):

STATE 1 — PHONE NUMBER ENTRY
- Full-screen dark centered layout (#0D0D0D background)
- Logo top center: "🍱 TiffinBox"
- Headline: "Enter your phone number"
- Subtext: "We'll send you a 6-digit OTP. No passwords needed."
- Single input field (large, centered, 100% width max-w-sm): +91 prefix chip + phone number input
- "Send OTP →" amber button (full width)
- Below: "By continuing, you agree to our Terms & Privacy Policy" — muted small text

STATE 2 — OTP ENTRY
- Same centered layout
- Back arrow top left
- Headline: "Enter the 6-digit OTP"
- Subtext: "Sent to +91 98765 43210" (show masked number)
- 6 separate input boxes in a row (each ~52px wide, dark border, amber focus ring)
- Auto-focus advances box on digit entry
- Auto-submit when all 6 filled
- Resend OTP link: disabled for 30 seconds with countdown "Resend in 0:24"
- After 30s: "Resend OTP" clickable link + "Get OTP on WhatsApp" alternative
- "Verify →" amber button

STATE 3 — NEW USER ONBOARDING (only for new accounts)
- Headline: "Almost there! Tell us about yourself"
- Name field: "Your full name"
- Address field: "Your delivery address" (large textarea-style with location pin icon)
- "Save & Continue →" amber button

INTERACTIONS:
- State transitions with fade animation
- OTP box: backspace goes to previous box
- Auto-advance to next box on digit input
- Countdown timer JS (30 seconds)
- Show error state (red border + error message) for wrong OTP
- "Wrong OTP. 2 attempts remaining." warning message
- After 3 wrong attempts: "Locked for 10 minutes" state with countdown

EDGE CASES TO SHOW (as different visual states using buttons to toggle for demo):
- OTP lock state
- WhatsApp fallback prompt

DESIGN:
- Center card: max-w-sm mx-auto, dark card #1A1A1A, rounded-3xl, p-8
- Amber gradient glow behind the card
- OTP boxes: border-2 border-gray-700 focus:border-amber-500, text-center text-2xl font-bold
- Smooth fade transitions between states

One complete self-contained HTML file with all 3 states + toggle buttons for demo.
```

---

### PROMPT 1.3 — Browse Food / Discover Page

```
You are a senior UI/UX developer. Build a complete, production-ready, single HTML file for the TiffinBox Browse Food page.

GLOBAL DESIGN SYSTEM: [Paste global block]

PAGE PURPOSE:
Food discovery engine. Users browse verified home cooks by location. Food photos are the hero of every card — cook name is secondary attribution only.

LAYOUT STRUCTURE:

STICKY TOP BAR:
- Location indicator: "📍 Koramangala, Bangalore" with a "Change" link (amber)
- Search input: "Search cuisine or dish..." with search icon
- Fixed to top on scroll

FILTER CHIPS ROW (horizontally scrollable, hide scrollbar):
- All (active/amber) · Veg 🌿 · Non-veg 🍗 · Lunch · Dinner · Lunch & Dinner · 4★+ · Under ₹100/day
- Active chip: bg-amber-500 text-black
- Inactive chip: dark border, dark bg, white text

SORT + RESULTS COUNT BAR:
- Left: "14 cooks available"
- Right: Sort dropdown — "Nearest ↕" (dark dropdown)

COOK CARDS LIST (full width on mobile, 2-col tablet, 2-col desktop):

Each cook card must contain:
1. Large food photo area (16:9 ratio) — use CSS gradient as placeholder (different color per card)
   - "✓ Verified" badge top-left (amber bg, dark text, small pill)
   - "2 spots left" badge top-right (red bg, white text) — show on some cards only
2. Cuisine + diet line: "North Indian · Veg" (amber dots separator)
3. Cook attribution: "by Sunita Sharma" — small, muted gray
4. Rating: ⭐ 4.8 (142 reviews) · 📍 1.2 km
5. Delivery timing: 🕐 Lunch by 1 PM · Dinner by 8 PM
6. Price: "₹2,800/mo" large + "₹93/day" small below
7. "View Plan" button — amber, full width on mobile

CREATE 8 COOK CARDS with varied content:
- Different cuisines: North Indian, South Indian, Rajasthani, Bengali, Punjabi
- Different ratings: 4.9, 4.7, 4.5, New cook badge (no stars)
- Different distances: 0.8 km, 1.2 km, 2.4 km, 3.1 km
- One card: "Currently Full" label (grey overlay, "Join Waitlist" button)
- One card: "New Cook" badge instead of stars

EMPTY STATE (show via JS toggle button):
- Illustration area (CSS-drawn bowl with X)
- "No cooks match your filters"
- "Try removing some filters" with "Reset Filters" amber button

INTERACTIONS:
- Filter chips: click to toggle active state, multiple can be active (except "All" resets others)
- Cards: hover state with lift + amber border glow
- "View Plan" → simulate navigation (console log + toast)
- "Change" location → small modal with a text input (simulate)
- Sort dropdown: functional (re-order cards by simulated sort)
- Infinite scroll loader (show loading spinner at bottom)

BOTTOM MOBILE NAV BAR (visible on mobile only):
- 4 icons: 🏠 Home · 🔍 Discover (active) · 📋 My Plans · 👤 Profile
- Active item in amber

One complete self-contained HTML file.
```

---

### PROMPT 1.4 — Food Menu / Cook Profile Page

```
You are a senior UI/UX developer. Build a complete, production-ready, single HTML file for the TiffinBox Food Menu Page (Cook's subscription profile page).

GLOBAL DESIGN SYSTEM: [Paste global block]

PAGE PURPOSE:
Most critical conversion page. Food photos and menu drive the subscribe decision. Cook is a trusted verified supplier — secondary to the food.

LAYOUT (scroll from top to bottom):

1. BACK NAVIGATION
   - "← Browse" link top left

2. HERO SECTION
   - Full-width food photo (1:1 mobile, 16:9 desktop) — use CSS gradient warm colors
   - Dark gradient overlay bottom 40%
   - Overlaid on photo (bottom):
     - Featured dish name large: "Dal Makhani + Butter Naan" in Syne
     - "by Sunita Sharma · Verified Cook" smaller below (muted)
   - Verified badge pill top-left of photo

3. STAT PILLS ROW (4 pills, scrollable on mobile)
   - ⭐ 4.8 Rating | 📝 142 Reviews | 👥 18 Subscribers | ✅ 97% On-time

4. CUISINE TAGS ROW
   - "North Indian" · "Veg" · "Lunch & Dinner" — amber bordered pills

5. TRUST SIGNALS STRIP (dark card #1A1A1A)
   - 4 items in a 2x2 grid (mobile) or 4-col row (desktop):
     - 🪪 ID Verified
     - 🧹 Kitchen Checked (Jan 2025)
     - ⚡ Replies within 2 hrs
     - 📅 Member since Aug 2023

6. THIS WEEK'S MENU (most important section)
   - Section heading: "This Week's Menu" with "Updated 2 days ago" badge
   - Horizontally scrollable week strip: Mon · Tue · Wed · Thu · Fri · Sat · Sun
   - Selected day shows highlighted in amber
   - Below strip: two cards for Lunch and Dinner for selected day
   - Each card: meal icon + dish name + description (brief)
   - Sunday shows "Off" state (muted)
   - JS: clicking each day updates the menu display below

7. SUBSCRIPTION PLANS
   - Section heading: "Choose a Plan"
   - Two cards side-by-side (stacked on mobile):
     - Weekly Plan: ₹700/week · ₹100/day · Lunch only
     - Monthly Plan: ₹2,800/mo · ₹93/day · Lunch only · "Best Value" badge (amber)
   - Meal type tabs above: Lunch | Dinner | Both (clicking updates prices)
   - Subscriber Protection box: amber left border, dark bg — "If your cook misses a delivery, you get a wallet credit or a backup meal within 2 hours."

8. REVIEWS SECTION
   - Section heading: "What subscribers say"
   - 5 review cards:
     - Star rating (amber stars)
     - "Rahul M. · 3 days ago"
     - Review text (2-3 lines)
   - "Load more reviews" link (amber)

9. DELIVERY INFORMATION
   - Dark card with 3 items:
     - 📍 Delivers within 3 km of Koramangala
     - 🕐 Lunch by 1:00 PM · Dinner by 8:00 PM
     - 📦 Leak-proof stainless containers

10. STICKY BOTTOM BAR (always visible)
    - Dark background with top border
    - Left: Plan info "Monthly · Lunch — ₹2,800/mo"
    - Right: "Subscribe Now →" amber button (rounded-full, px-8)
    - Auto-updates based on selected plan (JS)

MODAL — EDGE CASES (toggle with small demo buttons):
- "Cook is Full" state: sticky bar shows "Join Waitlist" instead
- "Cook on Leave" banner: amber top banner "Sunita is on leave until March 5. You can subscribe for after that date."
- "No Reviews" state: "Be the first to try and review" prompt

INTERACTIONS:
- Day selector: JS to switch menu display
- Plan selector (Lunch/Dinner/Both): updates prices everywhere
- Weekly/Monthly toggle: updates sticky bar and plan cards
- Sticky bar: on scroll, shows/hides smoothly
- "Subscribe Now" → scroll to top to show subscribe flow or simulate

One complete self-contained HTML file with demo toggle buttons for edge cases.
```

---

### PROMPT 1.5 — Subscribe Flow (3-Step Checkout)

```
You are a senior UI/UX developer. Build a complete, production-ready, single HTML file for the TiffinBox 3-Step Subscribe Flow.

GLOBAL DESIGN SYSTEM: [Paste global block]

PAGE PURPOSE:
Convert profile interest into paid subscription. Minimal friction, no distractions, 3 clear steps.

LAYOUT:
- Dark background, centered card (max-w-lg mx-auto)
- Progress bar at top: 3 steps shown as connected dots/line

STEP 1 — CHOOSE YOUR PLAN (shown by default)

Progress: Step 1 of 3 — "Choose Plan"

Cook summary card (top, compact):
- Small food photo + "Sunita Sharma · North Indian · Veg" + ★4.8

Meal Type Selector (3 cards in a row):
- Lunch 🌞 | Dinner 🌙 | Both 🌞🌙
- Each: icon + label + price indicator
- Active card: amber border + amber tint background

Duration Selector (2 cards side by side):
- Weekly ₹700 | Monthly ₹2,800 (pre-selected, "Save ₹0 vs weekly" or "Best Value" badge)

Start Date Selector (3 options as chips):
- Tomorrow | Next Monday | Pick a date 📅
- "Pick a date" opens a simple date picker

Pause Policy callout box:
- amber left-border, dark bg
- "You can pause up to 4 days per month. Skipped days become wallet credits."

"Continue →" amber button (full width)

---

STEP 2 — DELIVERY ADDRESS (hidden initially)

Progress: Step 2 of 3 — "Delivery Address"

Saved address card:
- Address display: "Flat 302, Prestige Towers, Koramangala 5th Block, Bangalore - 560095"
- Edit pencil icon
- Validation badge: "✓ Within Sunita's delivery radius" (green) — or "✗ Outside delivery area" (red)

Add new address button (amber outline)

Delivery instructions (optional):
- Text input: "Gate code, flat number, landmark..."

Back + Continue buttons

---

STEP 3 — PAYMENT (hidden initially)

Progress: Step 3 of 3 — "Pay & Subscribe"

Order Summary card (dark #1A1A1A):
- Cook: Sunita Sharma
- Plan: Monthly · Lunch
- Start: Tomorrow (date)
- Duration: 30 days
- Price: ₹2,800
- Platform fee: ₹0
- Total: ₹2,800

Payment Method (radio cards):
- UPI (default selected): show UPI app icons row (GPay, PhonePe, Paytm — use text logos)
  - UPI ID input field appears
- Debit/Credit Card: card number, expiry, CVV fields
- TiffinBox Wallet: "₹140 credits available"

Auto-renewal toggle:
- Toggle switch (green when on)
- Label: "Auto-renews on March 25, 2025. Cancel anytime."

"Subscribe & Pay ₹2,800" amber button (large, full width)

---

STEP 4 — SUCCESS STATE (after clicking pay)

Success animation: centered amber checkmark circle (CSS pulse animation once)
Large text: "You're subscribed! 🎉"
Subtext: "First meal arrives tomorrow by 1:00 PM. Sunita's lunch plan is active."
Three action buttons:
- "Add to Calendar" (outline)
- "Share with a friend" (outline)
- "Go to Dashboard →" (amber filled, primary)

---

INTERACTIONS:
- Step progress (1→2→3→success) via JS
- Progress bar animates on each step
- Meal type selection updates price in real-time
- Payment method switch shows/hides relevant fields
- Form validation (show red error states)
- Back button goes to previous step

EDGE CASES (demo toggle buttons):
- Payment failure state: "Payment failed. Try again or use a different method." red error card
- Address outside radius: block Step 3 with red warning
- Cook just became full: show "Cook just filled up — you're on the waitlist" state

One complete self-contained HTML file.
```

---

### PROMPT 1.6 — User Dashboard (Home Screen)

```
You are a senior UI/UX developer. Build a complete, production-ready, single HTML file for the TiffinBox User Dashboard.

GLOBAL DESIGN SYSTEM: [Paste global block]

PAGE PURPOSE:
Daily-use home screen. User opens at 12:45 PM to check if food is coming. Answer that question immediately, then surface every useful action within 1 tap.

LAYOUT STRUCTURE:

TOP NAVIGATION BAR:
- Left: "🍱 TiffinBox" logo
- Center: "Good afternoon, Rahul 👋" (Outfit font, warm)
- Right: notification bell icon with amber badge "3"
- Below navbar: date strip "Wednesday, 25 Feb 2025"

TODAY'S MEAL CARD (Hero — most prominent element):
- Dark card #1A1A1A, rounded-3xl, p-6, subtle amber shadow
- Label top: "TODAY'S LUNCH" in small amber caps
- Dish name: "Rajma Chawal + Green Salad" in Syne, large bold
- Small: "by Sunita Sharma" muted
- Expected time: "Expected by 1:00 PM" with clock icon
- 
- DELIVERY STATUS PROGRESS BAR (4 steps):
  - Confirmed ✓ → Preparing ✓ → Out for Delivery (pulsing amber) → Delivered
  - Completed steps: amber filled circle with check
  - Current step: amber circle with CSS pulse ring animation
  - Future steps: dark grey circle
  - Connector lines between circles (amber for completed, grey for pending)
  - Timestamp below each completed step (e.g., "11:24 AM")
-  
- Three quick action chips below:
  - "Skip Tomorrow" | "Rate Yesterday" | "Report Issue"
  - Dark chips with icons, amber text on hover

THIS WEEK PREVIEW STRIP (horizontally scrollable):
- 7 day-cards in a row
- Each card: Day name (Mon, Tue...) + Dish name truncated + status dot
  - Green dot = active
  - Grey X = skipped/paused
  - Amber outline = today
- Clickable (opens pause manager)

ACTIVE SUBSCRIPTIONS:
- Section heading: "My Subscriptions"
- 2 subscription cards (show user has 2 active):
  Card 1: "Sunita Sharma · Lunch" | "28 days left" | ★4.8 | "Manage" link
  Card 2: "Ramesh Kumar · Dinner" | "15 days left" | ★4.6 | "Manage" link
- "+ Find more cooks" amber outlined button

QUICK ACTION GRID (2x2):
- "📅 Pause Days" → Pause Manager
- "🔍 Find Cooks" → Browse
- "💰 Wallet & Credits" → Wallet
- "🆘 Get Help" → Support
- Dark cards, amber icon, hover lift effect

RENEWAL BANNER (show between sections):
- Amber-tinted banner: "⚠️ Your plan renews in 3 days — ₹2,800 will be charged on Feb 28"
- "View Details" link

BOTTOM MOBILE NAV:
- 🏠 Home (active) · 🔍 Discover · 📋 My Plans · 👤 Profile
- Active = amber

EDGE CASE STATES (toggle with buttons for demo):
- "Meal Skipped Today": today's card shows "You skipped today · ₹93 credit earned"
- "No Subscription": hero shows "Start your first subscription" with CTA
- "Cook Missed Delivery": red/amber alert card with "Report Missed Delivery" CTA
- "Delivery Running Late": yellow banner "Running 20 mins late — cook has been notified"

INTERACTIONS:
- Pulse animation on current delivery step (CSS keyframes)
- Quick action grid hover effects
- Week strip horizontal scroll
- Edge case toggles (demo buttons)
- Notification bell opens a dropdown with 3 notifications

One complete self-contained HTML file.
```

---

### PROMPT 1.7 — Pause & Skip Manager

```
You are a senior UI/UX developer. Build a complete, production-ready, single HTML file for the TiffinBox Pause & Skip Manager.

GLOBAL DESIGN SYSTEM: [Paste global block]

PAGE PURPOSE:
Let users pause/skip individual delivery days. This prevents cancellations — users who can pause stay longer.

LAYOUT:

HEADER:
- Back arrow + "Manage Your Days"
- Subscription name below: "Sunita Sharma · Lunch Plan · Monthly"

CREDITS SUMMARY CARD (amber-tinted, dark bg):
- "₹186 in pause credits this month"
- Progress bar: "2 of 4 pause days used"
- Small text: "2 remaining this month"
- Breakdown: ₹93/day credit per skip

SUBSCRIPTION SELECTOR (if user has multiple):
- Dropdown/tabs: "Sunita - Lunch" | "Ramesh - Dinner"

FULL MONTHLY CALENDAR (February 2025):
- Standard calendar grid (Sun-Sat headers)
- Color coding (use distinct backgrounds):
  - Dark green subtle bg = active delivery day (future) — clickable
  - Amber subtle bg = skipped by user (credit earned)
  - Dark grey bg = past date (not clickable, show historical)
  - White/light border only = past active (delivered)
  - Amber ring/border = today
  - No bg = non-delivery day (weekends if applicable)
- Each day shows:
  - Date number
  - Small dish name (truncated, 1 line)
  - Status indicator dot
- Tapping future active day: confirmation tooltip "Skip this day? You'll earn ₹93 credit."
  - Confirm / Cancel in the tooltip

PAUSE A RANGE BUTTON (full width, amber outline):
- Opens date range picker modal (see modal below)
- "Pause a range of days (e.g., for travel)"

PAUSE POLICY INFO BOX:
- Dark card with bullet points (use check icons):
  - Max 4 skip days per monthly cycle
  - Skip before 10:00 PM the night before
  - Skipped days earn pro-rated wallet credits
  - Credits auto-apply to next billing cycle

---

MODAL 1 — DATE RANGE PICKER:
- Title: "Select days to pause"
- Two date inputs: "From" and "To"
- Preview: "Pausing 5 days — exceeds limit" or "Pausing 3 days — ₹279 credit"
- Confirm / Cancel buttons

MODAL 2 — SKIP CONFIRMATION:
- "Skip Thursday, Feb 27?"
- "You'll earn ₹93 wallet credit for this day."
- "Confirm Skip" amber + "Cancel" grey

EDGE CASE STATES (demo buttons):
- Max pauses reached: amber warning "You've used all 4 pause days. Need more time off? Consider cancelling."
- Too late to skip: "It's past 10 PM. You can skip the day after tomorrow."
- Cook confirmed delivery: "Too late — your cook has started preparing. Contact support."

INTERACTIONS:
- Calendar day click toggles skipped/active state
- Running total of credits updates live
- Range picker validates against 4-day limit
- Confirmation modal before any skip

One complete self-contained HTML file.
```

---

### PROMPT 1.8 — Delivery Tracker Page

```
You are a senior UI/UX developer. Build a complete, production-ready, single HTML file for the TiffinBox Delivery Tracker.

GLOBAL DESIGN SYSTEM: [Paste global block]

PAGE PURPOSE:
Answer "Where is my food?" in real time. Simple 4-step status tracker.

LAYOUT:

HEADER:
- Back arrow + "Today's Delivery"
- Date: "Wednesday, 25 Feb · Lunch"

MEAL INFO CARD (dark, rounded):
- Food photo placeholder (gradient)
- "Rajma Chawal + Green Salad"
- "by Sunita Sharma" muted
- Expected time prominently: "Expected by 1:00 PM" — amber, large
- "Running late" banner (shown in late state demo)

DELIVERY STATUS TIMELINE (vertical, centered on page):
Each step as a large vertical timeline item:

Step 1 — CONFIRMED ✓
- Large amber filled circle with ✓ check
- "Confirmed" bold label
- "Your subscription is active for today" description
- Timestamp: "11:00 AM"

Step 2 — PREPARING ✓
- Large amber filled circle with ✓ check
- "Preparing" bold label
- "Sunita has started cooking your meal"
- Timestamp: "11:24 AM"

Step 3 — OUT FOR DELIVERY (CURRENT — pulsing)
- Amber circle with CSS pulse ring animation (two rings expanding outward)
- "Out for Delivery" bold label (amber text)
- "On the way to your address" description
- "Live since 12:45 PM"

Step 4 — DELIVERED (pending — grey)
- Grey circle (not yet)
- "Delivered" label (grey)
- "You'll get a notification on delivery"

Vertical connector lines:
- Amber for completed connections
- Dashed grey for pending connections

COOK INFO STRIP (below timeline):
- "Sunita Sharma" + cook avatar initials circle
- Star rating: ★4.8
- "Report an issue" link (subtle)

HISTORY STRIP (today's and yesterday's):
- "Yesterday: Dal Makhani · Delivered 12:58 PM ★5" — green check
- "Today: Rajma Chawal · Out for Delivery..."

POST-DELIVERY STATE (separate demo):
- All 4 steps completed (amber)
- "Delivered at 1:02 PM" shown
- Rating prompt appears below timeline:
  - "How was today's meal?"
  - 5 large star buttons in a row
  - Tag chips: "Loved it" · "Great portion" · "Arrived on time"
  - "Rate Later" dismiss link

EDGE CASE STATES (demo toggle buttons):
- "Running Late" (past expected time): step 3 turns amber/yellow, banner "Running 22 mins late — Sunita has been notified"
- "Issue Reported": step shows orange "Issue Reported" state with support CTA

INTERACTIONS:
- CSS keyframe pulse animation on current step
- State switching via demo buttons
- Post-delivery star rating: click stars, chips appear below
- Selecting chips highlights them in amber

One complete self-contained HTML file.
```

---

### PROMPT 1.9 — Feedback & Rating Page

```
You are a senior UI/UX developer. Build a complete, production-ready, single HTML file for the TiffinBox Feedback & Rating screen.

GLOBAL DESIGN SYSTEM: [Paste global block]

PAGE PURPOSE:
Collect meal ratings with minimum friction. One tap to rate, optional elaboration.

LAYOUT:

HEADER:
- "Rate Today's Meal"
- Subtitle: "Your feedback helps Sunita improve and helps others decide"

MEAL SUMMARY CARD (compact, top):
- Small gradient food image
- "Rajma Chawal + Green Salad" — Sunita Sharma
- "Delivered at 1:02 PM · Today"

RATING STARS (hero element):
- 5 very large star buttons (64px each), centered
- Stars: grey by default, amber when selected
- Hover: scale-up effect on star
- Click one: that star and all before turn amber
- Label below: "Good" / "Very Good" / "Excellent" etc. based on star count

CONDITIONAL CONTENT (JS based on star selection):

IF 4-5 STARS — Positive chips:
- Heading: "What did you love? (optional)"
- Tag chips: "Loved it 😍" · "Great portion 🍽️" · "Arrived on time ⏰" · "Good packaging 📦" · "Perfect taste 🔥"
- Multiple selectable, amber when selected

IF 1-3 STARS — Issue chips:
- Heading: "What went wrong? (optional)"
- Tag chips: "Late delivery ⏰" · "Cold food 🥶" · "Less quantity 📉" · "Taste issue 😕" · "Packaging problem 📦"
- Multiple selectable, red tint when selected
- Note: "We'll review this feedback and follow up."

TEXT COMMENT (optional, always shown):
- Textarea: "Tell Sunita what you think — it helps her improve (optional)"
- 200 char limit with counter

SUBMIT BUTTON:
- "Submit Rating" — amber, full width

SUCCESS STATE (after submit):
- Large amber checkmark circle animation
- "Thanks for rating! 🙌"
- Meal streak counter: "You've rated 8 meals in a row! Keep it up 🔥"
- Streak progress bar (8/10 to next badge)
- "Back to Dashboard" button

SKIP OPTION:
- "Rate Later" link below submit button (grey, small)

INTERACTIONS:
- Star hover/click effects
- Dynamic chip content based on stars selected
- Character counter for text area
- Submit animates to success state
- Skip goes back to dashboard

One complete self-contained HTML file.
```

---

### PROMPT 1.10 — Complaints & Support Page

```
You are a senior UI/UX developer. Build a complete, production-ready, single HTML file for the TiffinBox Complaints & Support page.

GLOBAL DESIGN SYSTEM: [Paste global block]

PAGE PURPOSE:
When something goes wrong, users need to feel heard and see action quickly. Slow resolution = churn.

LAYOUT:

HEADER:
- Back arrow + "Report an Issue"

ACTIVE SUBSCRIPTION SELECTOR:
- "For which subscription?" — dropdown or tab pills
- "Sunita · Lunch" | "Ramesh · Dinner"

ISSUE CATEGORY SELECTION (tap to select, one at a time):
8 issue cards in a 2-col grid (full width on mobile):
Each card: large icon + label
- 📦 Meal not delivered
- ⏰ Meal arrived very late
- 🤢 Food quality issue
- ❌ Wrong meal delivered
- 📉 Insufficient quantity
- 💳 Billing / payment issue
- 📵 Cook is unresponsive
- 💬 Other

Active card: amber border + amber tint bg

DESCRIPTION FIELD (appears after category selected):
- "Tell us more (optional)"
- Textarea, 300 char limit
- "📎 Attach a photo" button (shows file picker placeholder)

RESOLUTION TIMELINE PREVIEW (shown after category selected):
- Based on category, show expected resolution:
  - Delivery issues: "4 hours"
  - Billing: "24 hours"
  - Hygiene: "Immediate investigation"
- Small info card with clock icon

RESOLUTION POLICY (collapsible section):
- "What happens next?" — expand/collapse
- Content:
  - Missed delivery → full day credit to wallet
  - Late delivery (>30 min) → 50% credit
  - Hygiene complaint → immediate admin investigation
  - Billing dispute → resolved in 24 hours

SUBMIT BUTTON:
- "Submit Complaint" amber, full width

SUCCESS STATE (after submit):
- Ticket reference: "Ticket #TB-20250225-4821"
- "We've received your complaint"
- "Expected resolution: within 4 hours"
- "We'll notify you via push + in-app message"
- Timeline visual: Created → Under Review → Resolved

MY TICKETS TAB (secondary tab at top):
- List of past tickets:
  - "#TB-001 · Meal not delivered · Feb 20 · ✅ Resolved"
  - "#TB-002 · Late delivery · Feb 22 · 🕐 In Progress"
- Status badges: Resolved (green), In Progress (amber), Under Review (grey)

INTERACTIONS:
- Category card selection (single select)
- Conditional content based on category
- Photo attachment simulation
- Submit → success state animation
- Tab switching (New Issue / My Tickets)

One complete self-contained HTML file.
```

---

### PROMPT 1.11 — Wallet & Credits Page

```
You are a senior UI/UX developer. Build a complete, production-ready, single HTML file for the TiffinBox Wallet & Credits page.

GLOBAL DESIGN SYSTEM: [Paste global block]

LAYOUT:

HEADER:
- Back arrow + "Wallet & Credits"

BALANCE CARD (hero, dark gradient card):
- "Total Balance" label (muted small caps)
- "₹340" — very large, Syne font, white
- Two sub-amounts below:
  - "₹240 Pause Credits" (amber)
  - "₹100 Referral Credits" (green)
- Card background: dark with subtle amber gradient edge

HOW CREDITS WORK (info strip):
- 3 icons in a row: 📅 Skip = credit · 👥 Refer = credit · ✅ Applied automatically
- Credits auto-apply at next renewal — no manual action

TRANSACTION HISTORY:
- Section: "Transaction History"
- Filter chips: All · Credits Earned · Credits Used
- List of transactions (most recent first):
  - ✅ +₹93 · Skipped lunch (Feb 22) · Pause Credit
  - ✅ +₹100 · Referral: Arjun K joined · Referral Credit
  - ✅ +₹93 · Skipped lunch (Feb 18) · Pause Credit
  - 🔻 -₹186 · Applied to renewal (Feb 1) · Credit Used
  - ✅ +₹93 · Skipped dinner (Jan 28) · Pause Credit
- Each item: icon · amount (green+, red-) · description · date · type badge

REFER & EARN SECTION:
- Heading: "Earn ₹100 per referral"
- Subtext: "Your friend gets ₹50 off their first month too"
- Referral code box: "RAHUL2025" with copy button (copies to clipboard)
- Share options: WhatsApp · Copy Link (icon buttons)
- "3 referrals completed · ₹300 earned"

One complete self-contained HTML file.
```

---

### PROMPT 1.12 — My Subscriptions Page

```
You are a senior UI/UX developer. Build a complete, production-ready, single HTML file for the TiffinBox My Subscriptions page.

GLOBAL DESIGN SYSTEM: [Paste global block]

LAYOUT:

HEADER:
- Back arrow + "My Subscriptions"

TABS:
- Active (2) | Past (3)

ACTIVE SUBSCRIPTIONS:

Each subscription card (dark #1A1A1A, rounded-2xl):
- Top row: Food photo (small square) + "Sunita Sharma" + "North Indian · Veg" + ★4.8
- Plan info: "Monthly · Lunch · Auto-renews Feb 28"
- Progress bar: "14 of 30 days completed" with amber progress
- Days remaining: "16 days left in this cycle"
- Quick stats row: "₹93/day · Delivered 12 of 14 days · 0 skips used"
- Action buttons row:
  - "Manage Days" (pause manager)
  - "Track Today" (delivery tracker)
  - "⋯" more (dropdown: View Menu, Cancel, Contact Cook)

RENEWAL ALERT (on card near renewal):
- "Renews in 3 days · ₹2,800" — amber banner within card

PAUSE STATE indicator (show on one card):
- "⏸ Paused · Resumes March 5" — amber badge

PAST SUBSCRIPTIONS (Past tab):
- Simpler cards: cook name + dates + plan + "Expired" badge
- "₹2,800 total paid · 28 days delivered · ★4.8 avg rating"
- "Resubscribe" button (amber outline)

+ ADD SUBSCRIPTION BUTTON:
- Floating amber button bottom right: "+ Find More Cooks"

MODAL — CANCEL SUBSCRIPTION:
- "Cancel Subscription?"
- "Your current cycle ends Feb 28. You won't be charged after that."
- Warning: "You'll lose your spot — Sunita only has 1 spot remaining"
- Reasons dropdown (optional): Moving · Too expensive · Quality issues · Other
- "Keep Subscription" (primary, amber) + "Confirm Cancel" (grey outline)

One complete self-contained HTML file with tabs + cancel modal.
```

---

### PROMPT 1.13 — Profile & Settings Page

```
You are a senior UI/UX developer. Build a complete, production-ready, single HTML file for the TiffinBox User Profile & Settings page.

GLOBAL DESIGN SYSTEM: [Paste global block]

LAYOUT:

HEADER:
- Back arrow + "Profile & Settings"

PROFILE SECTION (top card):
- Avatar circle (large, initials "R.V.", amber bg)
- "Rahul Verma" — Syne font
- "+91 98765 43210" — muted
- "Edit Profile" link (amber)
- Member since: "Feb 2024" · Total meals: "142"

SETTINGS SECTIONS (accordion or listed sections with dividers):

1. DELIVERY ADDRESSES
   - Primary: "Flat 302, Prestige Towers, Koramangala 5th Block" (Home tag)
   - Secondary: "WeWork, HSR Layout" (Work tag)
   - "+ Add new address" amber link

2. NOTIFICATION PREFERENCES
   - Toggle list:
     - 🍽️ Delivery status updates — On
     - ⭐ Rating reminders — On
     - 💳 Renewal reminders — On
     - 📢 New cooks near you — Off
     - 🎉 Offers & promotions — Off
   - Each row: label + Tailwind toggle switch

3. PAYMENT METHODS
   - Saved: GPay UPI (rahul@okaxis) — Default badge
   - "Manage payment methods" link

4. ACCOUNT
   - Change phone number
   - Download my data
   - Delete account (red text)

5. HELP & SUPPORT
   - FAQ
   - Contact support
   - Report a bug

6. ABOUT
   - Privacy Policy
   - Terms of Service
   - App version: v1.0.2

LOG OUT BUTTON (full width, red outline, bottom):
- "Log Out"

MODAL — EDIT PROFILE:
- Name field (editable)
- Phone (read-only, "Change" link separately)
- Save Changes button

One complete self-contained HTML file with modals.
```

---

## 📁 SECTION 2: COOK-FACING APP (Light Theme)
*5 main cook screens*

---

### PROMPT 2.1 — Cook Onboarding Wizard

```
You are a senior UI/UX developer. Build a complete, production-ready, single HTML file for the TiffinBox Cook Onboarding wizard.

GLOBAL DESIGN SYSTEM: [Paste global block]
THEME OVERRIDE: Light theme — bg-gray-50 base, white cards, dark text. Still use amber #F5A623 as accent.
PURPOSE: Register a new cook. Multi-step wizard. Simple as WhatsApp. Cooks not tech-savvy.

STEP INDICATOR:
- Top: "Step X of 9" with a progress bar (amber fill)

STEP 1 — PHONE + OTP
- Same as user login (phone input + OTP)

STEP 2 — PERSONAL DETAILS
- Full name input
- Profile photo upload (large dashed upload area: click to upload, shows preview)
- "Years of cooking experience" — number stepper (1–30+)

STEP 3 — KITCHEN DETAILS
- Kitchen address (with Google Maps autocomplete placeholder)
- Kitchen type: "Home Kitchen" | "Small Commercial" — radio cards
- FSSAI number: "Optional for now — required in Phase 2" — with info tooltip

STEP 4 — CUISINE & DIET
- Cuisine multi-select (checkboxes as pill chips):
  North Indian · South Indian · Chinese · Bengali · Rajasthani · Continental · Gujarati
- Diet type: Veg only | Non-veg | Both — radio cards with icons

STEP 5 — MEAL TYPES & TIMINGS
- Toggle: Lunch | Dinner | Both
- Lunch delivery time: time picker (select from dropdown: 11:30 AM – 2:00 PM)
- Dinner delivery time: time picker (6:30 PM – 9:00 PM)

STEP 6 — DELIVERY RADIUS
- 4 option cards: 1 km | 2 km | 3 km | 5 km
- Map preview area (grey placeholder with circle overlay showing coverage)
- "Wider radius = more customers, more travel"

STEP 7 — CAPACITY
- "Max subscribers you can serve per meal type"
- Stepper input: 10 / 15 / 20 / 25 / Custom
- Info: "You can adjust this anytime from settings"

STEP 8 — PRICING
- Platform shows suggested range: "₹2,400–3,200/month for Lunch in Koramangala"
- Monthly Lunch price input (₹)
- Monthly Dinner price input (₹)
- Monthly Both price input (auto-calculated, editable)
- Per-day equivalent auto-shown below each

STEP 9 — SAMPLE MENU
- Weekly grid: 7 days × 2 meals (Lunch row, Dinner row)
- Each cell = text input "Enter dish name"
- Minimum 3 days required to submit
- "Copy last week" button (shows in light grey on first use)

STEP 10 — BANK DETAILS
- Account holder name
- Account number
- IFSC code
- Bank name (auto-fetch from IFSC placeholder)
- Security note: "🔒 Stored securely. Used only for monthly payouts."

SUBMIT STATE:
- "Submit for Review" amber button
- After submit: "Application Submitted! ✅"
  - "Our team will review in 24–48 hours"
  - "You'll receive an SMS + notification on approval"
  - Checklist of what happens next

INTERACTIONS:
- Step-by-step navigation (Next/Back)
- Progress bar animates per step
- Form validation per step before advancing
- Photo upload shows preview
- IFSC auto-fetch simulation

One complete self-contained HTML file.
```

---

### PROMPT 2.2 — Cook Dashboard

```
You are a senior UI/UX developer. Build a complete, production-ready, single HTML file for the TiffinBox Cook Dashboard.

GLOBAL DESIGN SYSTEM: [Paste global block]
THEME: Light (#F9FAFB background, white cards, dark text, amber accent)

PAGE PURPOSE:
Cook's command centre. Opened every morning. Must show everything needed to fulfil today's orders without navigating away.

LAYOUT:

TOP BAR:
- Left: "🍱 TiffinBox Cook" logo (smaller)
- Right: Cook name "Sunita Sharma" + avatar

DATE + STATUS ROW:
- "Tuesday, 25 Feb 2025" large heading (Syne)
- STATUS TOGGLE (right side, prominent):
  - Pill toggle: "🟢 Open for new subscribers" | "⭕ Closed"
  - Large, easy to tap

TODAY'S SUMMARY CARD (amber-tinted, white card):
- Large number: "12 meals to deliver today"
- Progress: "3 of 12 delivered" — progress bar (amber fill)
- Two sub-items: "9 Lunch · 3 Dinner"

EARNINGS CARDS ROW (3 cards):
- Today: ₹1,116
- This month: ₹24,800
- Next payout: March 1 · ₹22,400

ALERT CARDS (if any — show examples):
- 🟡 "Priya S. joined! 1 new subscriber (Lunch)" — green alert
- 🔴 "Complaint raised by Rahul V. — Food quality issue" — red, "Respond →" button
- 🟠 "Menu not updated for 5 days — update to keep subscribers" — amber

QUICK NAVIGATION GRID (2x2):
- 📋 Today's Orders (with badge: 9 pending)
- 🍽️ Menu Manager
- 👥 Subscribers (18 total)
- 💰 Earnings & Payouts

SUBSCRIBER TREND MINI CHART:
- Simple CSS bar chart or line (last 4 weeks subscriber count)
- "18 subscribers · +3 this month" stat

RECENT ACTIVITY FEED:
- Compact list of last 5 activities:
  - "Priya S. rated 5 stars · 2h ago"
  - "Rahul V. skipped tomorrow · 3h ago"
  - "Aarav M. renewed subscription · Yesterday"
  - "Sunita's menu updated · 2 days ago"

COOK SIDE NAV (desktop: left sidebar / mobile: bottom bar):
- Today's Orders · Menu · Subscribers · Earnings · Profile

One complete self-contained HTML file.
```

---

### PROMPT 2.3 — Cook: Today's Orders

```
You are a senior UI/UX developer. Build a complete, production-ready, single HTML file for the TiffinBox Cook Today's Orders screen.

GLOBAL DESIGN SYSTEM: [Paste global block]
THEME: Light

PAGE PURPOSE:
Most-used cook screen. Complete delivery list with one-tap status updates. Simple as a checklist.

LAYOUT:

HEADER:
- Back arrow + "Today's Orders — Tuesday, 25 Feb"
- Completion summary: "3 of 12 delivered" — amber progress pill

MEAL TYPE TABS:
- "Lunch (9)" | "Dinner (3)" — switch between lists

BULK ACTION BAR (top of list):
- "Mark all as Delivered" — amber button (show confirmation modal)
- "Filter: All | Pending | Delivered"

SUBSCRIBER ORDER LIST:
Show 12 items total. Each list item (white card, subtle shadow):

Row layout:
- Left: Number badge + subscriber name "Rahul Verma" (large, readable)
- Below name: Full delivery address "Flat 302, Prestige Towers, Koramangala 5th Block"
- Meal type chip: "Lunch" green | "Dinner" blue
- Right side: 3-step status buttons:
  [ Preparing ] → [ Out for Delivery ] → [ Delivered ]
  Current active step: amber filled, others: grey outline
- Phone icon: tap to call (masked number indicator)

SPECIAL STATES in the list:
- One item: "⏸ Skipped today" — grey out entire row, no status buttons needed, "Paused" muted badge
- One item: "New subscriber · First delivery" — small green "NEW" badge
- One item: Already "Delivered ✓" — green check, timestamp "12:58 PM"

FLOATING "Mark All Delivered" BUTTON (bottom, amber):
- Visible when on list, tap opens confirmation modal

CONFIRMATION MODAL — Mark All Delivered:
- "Mark all 9 remaining as delivered?"
- "This will notify all subscribers and complete today's deliveries."
- "Yes, Mark All Delivered" (amber) + "Cancel" (grey)

EDGE CASE STATES:
- Complaint raised: one item has orange border + "⚠️ Complaint — Food quality issue" below address + "View →" link

INTERACTIONS:
- Status button tap: advances status (Preparing → Out for Delivery → Delivered)
- Delivering 1 item: "12:47 PM" timestamp appears
- Completion summary updates in real-time
- Filter tabs switch content

One complete self-contained HTML file.
```

---

### PROMPT 2.4 — Cook: Menu Manager

```
You are a senior UI/UX developer. Build a complete, production-ready, single HTML file for the TiffinBox Cook Menu Manager.

GLOBAL DESIGN SYSTEM: [Paste global block]
THEME: Light

PAGE PURPOSE:
Update weekly menu easily. Minimal effort — simpler than filling a WhatsApp form.

LAYOUT:

HEADER:
- Back arrow + "Menu Manager"
- Status badge: "⚠️ Not updated this week" (orange) or "✅ Updated 2 days ago" (green)

WEEK SELECTOR:
- "< Feb 24 – Mar 2 >" navigation arrows
- Current week highlighted

SHORTCUTS ROW:
- "📋 Copy Last Week" button — pre-fills all cells
- "🔁 Same Dish Every Day" — per-meal shortcut

WEEKLY MENU GRID:
- Mobile: Scrollable horizontal cards per day
- Desktop: Full 7×2 table grid

Each day column (Mon through Sun):
- Day header: "Mon 24", "Tue 25" etc.
- Lunch cell: text input "Enter lunch dish..." — short, single line
- Dinner cell: text input "Enter dinner dish..."
- "Off" toggle per day: greyed out when toggled off (Sunday off by default)

Pre-filled realistic content:
- Mon Lunch: "Rajma Chawal" | Mon Dinner: "Palak Paneer"
- Tue Lunch: "Chole Bhature" | Tue Dinner: "Dal Makhani"
- Wed Lunch: "Mix Veg Thali" | Wed Dinner: "Paneer Butter Masala"
- etc.

SUBSCRIBERS NOTIFICATION PREVIEW:
- "Publishing will notify 18 subscribers via push notification"
- Preview of notification text: "Sunita updated her menu for this week! Tap to see."

PUBLISH BUTTON:
- "📢 Publish Menu — Notify Subscribers" — amber, full width
- Disabled state: "Fill at least 5 days to publish"
- Enabled state: ready to click

SUCCESS STATE (after publish):
- "✅ Menu Published!"
- "18 subscribers notified"
- Last updated timestamp

INTERACTIONS:
- Each cell: click to type
- Day "Off" toggle: grey out that column
- "Copy Last Week": fills all inputs (animate)
- Publish: validates 5+ days filled, shows success
- Week navigation arrows

One complete self-contained HTML file.
```

---

### PROMPT 2.5 — Cook: Earnings & Payouts

```
You are a senior UI/UX developer. Build a complete, production-ready, single HTML file for the TiffinBox Cook Earnings & Payouts page.

GLOBAL DESIGN SYSTEM: [Paste global block]
THEME: Light

PAGE PURPOSE:
Financial transparency. Clear as a bank statement. Builds trust → cooks stay.

LAYOUT:

HEADER:
- Back arrow + "Earnings & Payouts"

BALANCE HERO CARD (amber gradient, rounded-3xl):
- "Amount Ready for Payout"
- "₹22,400" — huge Syne font, white text
- "Next payout: March 1, 2025"
- Sub-detail: "₹2,400 on hold (1 complaint pending)"

NEXT PAYOUT CARD:
- "March 1 · ₹22,400 to HDFC ****4521"
- Progress bar: 6 days until payout

EARNINGS PERIOD TOGGLE:
- "This Month" | "Last Month" | "All Time" — tab pills

EARNINGS BREAKDOWN CARD (for selected period):
- Gross earnings: ₹28,000
- Platform commission (15%): -₹4,200
- Refunds/disputes: -₹1,400
- Net earnings: ₹22,400 (bold, amber)

PER-SUBSCRIBER TABLE:
- Table heading: "Earnings per subscriber — February 2025"
- Columns: Subscriber Name | Plan | Days Delivered | Amount
- Rows (10 rows):
  "Rahul V. · Monthly Lunch · 18/28 days · ₹1,680"
  "Priya S. · Monthly Lunch+Dinner · 18/28 days · ₹3,360"
  etc.
- Scroll-able on mobile (horizontal)

PAYOUT COMMISSION INFO:
- "TiffinBox takes 15% per subscription. You keep 85%."
- Amber left-border info box

TRANSACTION HISTORY:
- Chronological list:
  - ✅ "Rahul V. renewed" · Feb 1 · +₹2,800
  - ✅ "Priya S. new subscription" · Feb 3 · +₹5,600
  - 🔻 "Payout to HDFC ****4521" · Feb 1 · -₹19,800
  - 🔒 "Held: complaint #TB-002" · Feb 22 · -₹93
- Amount: green+ for credits, red- for debits/holds

BANK ACCOUNT SECTION:
- "HDFC Bank · ****4521 · Sunita Sharma" displayed
- "Update Bank Account" link

One complete self-contained HTML file.
```

---

## 📁 SECTION 3: ADMIN PANEL (Neutral/Light Theme, Desktop-First)

---

### PROMPT 3.1 — Admin: Cook Approvals Queue

```
You are a senior UI/UX developer. Build a complete, production-ready, single HTML file for the TiffinBox Admin Cook Approvals Queue.

GLOBAL DESIGN SYSTEM: [Paste global block]
THEME: Admin — neutral light (#F3F4F6 bg, white cards, dark text, amber accents)
LAYOUT: Desktop-first (sidebar + main content). Still responsive for tablet.

ADMIN SIDEBAR (left, fixed):
- "🍱 TiffinBox Admin" branding
- Nav items (icons + labels):
  - 👤 Cook Approvals (active, amber)
  - 🚨 Complaints
  - 💰 Payouts
  - 📊 Quality Dashboard
  - 📈 Analytics
  - ⚙️ Settings
- Collapse button

MAIN CONTENT:

HEADER BAR:
- "Cook Approvals" h1
- Stats row: "8 Pending · 3 Approved today · 1 Rejected today"
- Sort: "Oldest first" dropdown

APPROVAL QUEUE (list of cards):
Show 5 cook application cards:

Each card:
- Left: Cook photo (initials avatar)
- Center: Name, city, submission date, cuisines offered
- Completeness score (progress bar): "80% complete — Missing: bank details"
  - 5 checkboxes: Photo ✓ | Bank details ✗ | Menu ✓ | Radius ✓ | Pricing ✓
- Right: "Review →" amber button | "Reject" grey button
- Submission date: "Submitted 2 days ago"
- Priority badge: "New" (green) or "Resubmission" (blue)

COOK APPLICATION DETAIL (full-page side panel or separate page — show as expandable panel):

Panel sections:
1. Personal: Name, photo, phone, experience
2. Kitchen: Address, type, FSSAI, map preview
3. Cuisine & Capacity: selected cuisines, max subscribers, delivery radius
4. Pricing: Lunch ₹2,800, Dinner ₹2,200, Both ₹4,500
5. Sample Menu: Week grid (read-only view)
6. Bank Details: "HDFC ****4521 — Verified" or "Pending verification"
7. Admin Notes: free text field

APPROVAL ACTIONS (bottom of panel):
- "✅ Approve & Go Live" — amber button
- "❌ Reject with reason" — opens rejection reason modal
- "📋 Request more info" — sends message to cook

REJECTION MODAL:
- "Select reason:" dropdown with options
- Additional notes text area
- "Send Rejection" button

INTERACTIONS:
- Queue list: click any card to open side panel
- Panel slides in from right
- Approve: removes from queue, shows success toast
- Reject: opens modal → sends rejection → removes from queue
- Tab: Pending | Approved | Rejected (with counts)

One complete self-contained HTML file.
```

---

### PROMPT 3.2 — Admin: Complaints & Dispute Resolution

```
You are a senior UI/UX developer. Build a complete, production-ready, single HTML file for the TiffinBox Admin Complaints & Disputes panel.

GLOBAL DESIGN SYSTEM: [Paste global block]
THEME: Admin light

PAGE: Admin complaints resolution workflow

HEADER:
- "Complaints & Disputes"
- Stats: "12 Open · 3 Urgent · 28 Resolved this week"
- Priority filter: All | Urgent | High | Normal

COMPLAINT QUEUE (sortable table + cards on mobile):
Each complaint item:
- Complaint ID: #TB-20250225-4821
- Priority badge: 🔴 Urgent | 🟡 High | 🟢 Normal
- Issue type: "Meal not delivered"
- User: "Rahul Verma"
- Cook: "Sunita Sharma"
- Date raised: "25 Feb · 2h ago"
- Days open: "0 days" or "3 days" (red if >1 day)
- Status: "Open" | "In Review" | "Awaiting Cook Response"
- "Resolve →" button

Show complaints of different types:
- 🔴 Urgent: "Hygiene complaint — Priya S. found hair in food"
- 🔴 Urgent: "Meal not delivered — 3rd time in a row (Ramesh K.)"
- 🟡 High: "Billing issue — double charged"
- 🟢 Normal: "Late delivery (22 mins)"

DETAIL PANEL (slide-in from right):
Sections:
1. Complaint details: category, description, photo (if attached)
2. Order details: subscription, delivery date, expected time
3. Delivery logs: cook's status updates with timestamps
4. Both sides' accounts: user report + cook response (if any)
5. Cook's response area: text from cook (or "Awaiting response" if not replied)

RESOLUTION ACTIONS (bottom of panel):
- "💰 Issue wallet credit" — opens amount input
- "💳 Issue refund" — opens amount input
- "⚠️ Send warning to cook" — opens template message
- "🚩 Flag cook for review"
- "🚫 Remove cook from platform" — confirmation needed
- "✅ Close as resolved" — add resolution note
- "⬆️ Escalate" — to senior admin

Admin resolution note (text area): "Add internal note..."

ESCALATION TIMER:
- Auto SLA: "3h 22m until SLA breach" — amber countdown for urgent complaints

INTERACTIONS:
- Priority sort, filter by type
- Complaint card → opens detail panel
- Resolution actions show confirmation prompts
- Resolved complaints move to Resolved tab
- Search by user name or cook name

One complete self-contained HTML file.
```

---

### PROMPT 3.3 — Admin: Payout Management

```
You are a senior UI/UX developer. Build a complete, production-ready, single HTML file for the TiffinBox Admin Payout Management page.

GLOBAL DESIGN SYSTEM: [Paste global block]
THEME: Admin light

PAGE PURPOSE:
Monthly payout batch review and approval.

HEADER:
- "Payout Management — March 2025 Batch"
- Payout date: "Scheduled: March 1, 2025"
- Status: "🟡 Pending Approval" — amber badge

BATCH SUMMARY CARD (top):
- Total cooks in batch: 28
- Total payout amount: ₹4,82,000
- On hold: ₹8,400 (4 disputes)
- Ready to pay: ₹4,73,600
- "Approve Batch Payout" amber button (large)
- "Review all before approving" warning

PAYOUT TABLE:
Columns: Cook Name | Bank | Earned | Deductions | Net Payout | Status | Hold Reason

Rows (show 10):
- "Sunita Sharma · HDFC ****4521 · ₹28,000 · ₹4,200 · ₹23,800 · ✅ Ready · —"
- "Ramesh Kumar · SBI ****8823 · ₹18,500 · ₹2,775 · ₹15,725 · 🔒 Held · Pending complaint"
- "Kavitha R. · ICICI ****2291 · ₹32,000 · ₹4,800 · ₹27,200 · ✅ Ready · —"
- (more rows)

Row actions:
- "Hold" button (for ready items)
- "Release" button (for held items)

APPROVE BATCH MODAL:
- "Approve ₹4,73,600 payout to 26 cooks?"
- Confirmation: type "APPROVE" to confirm
- "Initiate via Razorpay Route" amber button

PAYOUT HISTORY TAB:
- Past payout batches: Feb 1 · ₹4,12,000 · 24 cooks · ✅ Completed
- Each with download report link

One complete self-contained HTML file.
```

---

### PROMPT 3.4 — Admin: Quality Dashboard

```
You are a senior UI/UX developer. Build a complete, production-ready, single HTML file for the TiffinBox Admin Quality Dashboard.

GLOBAL DESIGN SYSTEM: [Paste global block]
THEME: Admin light, data-dense

PAGE PURPOSE:
Real-time quality monitoring. Surface problem cooks immediately.

LAYOUT:

HEADER:
- "Quality Dashboard"
- Last updated: "Live · Refreshes every 5 min" with pulsing green dot

PLATFORM HEALTH METRICS (KPI cards row — 4 cards):
- "4.7 ⭐ Avg Platform Rating (30 days)"
- "96.2% Delivery Completion Rate"
- "4.8% Complaint Rate per 100 deliveries"
- "81% Cook Retention (3 months)"

COLOR CODING: Green if good, amber if borderline, red if critical

FLAGGED COOKS SECTION (most important):
- "Cooks Needing Attention" — red header
- Table: Cook name | Subscribers | Avg Rating | Complaints | Issues
- Pre-fill with 3 flagged entries:
  - "Ravi K. · 8 subscribers · ★3.2 · 4 complaints · ⚠️ Rating below 4.0"
  - "Arun S. · 12 subscribers · ★3.8 · 3 unresolved complaints"
  - "Neha P. · 5 subscribers · ★4.1 · Late delivery >20% of orders"
- Each row: "View Profile" + "Flag for Review" + "Contact" actions

TOP PERFORMING COOKS:
- Table: Cook name | Subscribers | Rating | Delivery % | This Month's Revenue
- 5 rows, sorted by subscriber count

RATING TREND CHART (CSS/JS bar chart):
- Platform average rating per week (last 8 weeks)
- Simple bar chart using div heights
- Trend line (CSS)

DELIVERY COMPLETION TABLE:
- Cook-wise completion rates for this month
- Color coded: >98% green, 95-98% amber, <95% red

One complete self-contained HTML file.
```

---

### PROMPT 3.5 — Admin: Analytics Dashboard

```
You are a senior UI/UX developer. Build a complete, production-ready, single HTML file for the TiffinBox Admin Analytics Dashboard.

GLOBAL DESIGN SYSTEM: [Paste global block]
THEME: Admin light

PAGE PURPOSE:
Key business metrics — weekly/monthly trends. For operators and stakeholders.

LAYOUT:

HEADER:
- "Analytics"
- Period selector: "This Week" | "This Month" | "Last Month" — tabs

NORTH STAR METRIC (hero card, amber):
- "Monthly Recurring Subscribers"
- Large number: "1,284"
- "+127 from last month" — green arrow up
- Sparkline (CSS mini-chart)

KPI GRID (2x3 on desktop, stacked mobile):
1. New subscriptions this month: 187 (+12% vs last month)
2. Churn rate: 8.3% (target <10%) — green
3. Gross Transaction Value: ₹36,12,000
4. Platform Revenue (commissions): ₹5,41,800
5. Avg subscription duration: 2.8 months
6. Complaint rate: 4.8 per 100 deliveries

SUBSCRIBER GROWTH CHART:
- Large area/bar chart (pure CSS or Canvas)
- 12 weeks of data
- Green bars for new subscriptions, red for churned
- Net growth line

COOK SUPPLY METRICS:
- Active cooks: 28
- Pending approval: 5
- Suspended: 2
- Avg subscribers per cook: 18.4

CHURN REASONS (donut-style chart using CSS):
- Moving away: 32%
- Quality issues: 28%
- Price: 22%
- Personal reasons: 18%

TOP COOKS BY REVENUE TABLE:
- Cook | Subscribers | GTV | Rating
- 5 rows

EXPORT BUTTON:
- "Download CSV Report" — outline button

One complete self-contained HTML file.
```

---

## 📁 SECTION 4: SHARED / UTILITY PAGES

---

### PROMPT 4.1 — How It Works Page

```
Build a complete, production-ready HTML page for TiffinBox "How It Works" — a public explainer page for new visitors.

GLOBAL DESIGN SYSTEM: [Paste global block]
THEME: Dark (user app)

SECTIONS:
1. Hero: "Designed for people who deserve good food, daily" — headline + subtext
2. For Users: 5 steps with illustrations (CSS icons), numbered
3. For Cooks: 4 steps similarly
4. Subscription explained: Pause/skip/credits explained visually
5. Trust & safety section: 4 trust signals
6. FAQ accordion: 8 common questions (JS accordion)
7. CTA: "Find cooks near you" + "Become a cook"

Include realistic FAQs about pausing, cancelling, delivery, quality, payment.
Full responsive, complete HTML file.
```

---

### PROMPT 4.2 — Notifications Center

```
Build a complete, production-ready HTML page for TiffinBox Notifications Center.

GLOBAL DESIGN SYSTEM: [Paste global block]
THEME: Dark (user app)

LAYOUT:
- Header: "Notifications" + "Mark all read" link
- Filter tabs: All | Deliveries | Subscriptions | Promotions
- Notification list (grouped by date: Today, Yesterday, Earlier):

Show 12 notifications of various types:
- 🍽️ "Your lunch is out for delivery!" — 12:45 PM · Unread (amber dot)
- ⭐ "Rate yesterday's meal from Sunita" — 1:30 PM
- 💳 "Plan renews in 3 days · ₹2,800" — Yesterday
- ✅ "Subscription confirmed — Ramesh's dinner plan" — Yesterday
- 🎉 "You earned ₹93 credit for skipping today" — 2 days ago
- 📢 "New cook near you: Kavitha R. (South Indian)" — 3 days ago

Each notification: icon + title + body + timestamp + unread dot
Tapping each = navigates (simulate with alert/console)
Swipe to dismiss (JS)
Full complete HTML file.
```

---

### PROMPT 4.3 — Empty States & Error Pages

```
Build a complete, production-ready HTML file showing all TiffinBox empty states and error pages.

GLOBAL DESIGN SYSTEM: [Paste global block]
THEME: Dark

Show all these states as separate sections on one page (with section headers):

1. No cooks in area — bowl illustration (CSS), "We're not in your area yet", email capture
2. No active subscriptions — fork illustration, "Find your first cook"
3. No notifications — bell illustration, "You're all caught up"
4. No past orders — calendar illustration
5. Search no results — magnifier illustration, "No cooks match" + reset
6. 404 page — TiffinBox branded, "Page not found", back to home
7. Payment failed — card illustration, retry options
8. Cook unavailable — "Cook is on leave" state
9. Network error — wifi icon, retry button
10. App maintenance — "We'll be back shortly"

Each state: illustration (CSS-drawn or emoji-based), headline, subtext, CTA button.
All on one file with clear section separators.
```

---

## 📋 PROMPT USAGE GUIDE

> **How to use these prompts effectively with Gemini:**

**Order to follow:**
1. Start with PROMPT 1.1 (Landing Page) — establishes the design language
2. Do PROMPT 1.2 (Auth) next — simple, quick win
3. Then 1.3 → 1.4 → 1.5 (the core user journey)
4. Then 1.6 → 1.7 → 1.8 (daily use screens)
5. Then 1.9 → 1.10 → 1.11 → 1.12 → 1.13 (supporting screens)
6. Cook app: 2.1 → 2.2 → 2.3 → 2.4 → 2.5
7. Admin: 3.1 → 3.2 → 3.3 → 3.4 → 3.5
8. Utility: 4.1 → 4.2 → 4.3

**Tips:**
- Always paste the Global Design System at the top of each prompt
- If Gemini drifts from the design style, remind it: "Keep the dark theme (#0D0D0D), amber #F5A623, Syne + Outfit fonts"
- For modals: always include them in the same file with JS toggle
- For edge cases: include demo toggle buttons so you can preview all states
- Request "one complete self-contained HTML file" at the end of every prompt

**Total Pages to Build:**
- User App: 13 pages/screens
- Cook App: 5 pages/screens  
- Admin Panel: 5 pages
- Utility/Shared: 3 pages
- **Total: 26 complete HTML files**
