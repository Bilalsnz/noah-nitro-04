Build a complete, polished, mobile-first web application named WorkSlip. This is a real working product, not a landing page. It is a digital job book for independent tradespeople and small workshops: welders, electricians, mechanics, plumbers, phone repairers, and other hands-on workers.

PRODUCT PROMISE
"Every job. Every cost. Every payment. Under control."
Help a worker track jobs, costs, payments, profit, and customer commitments without needing a spreadsheet.

VISUAL DIRECTION
Make the UX exceptional and product-led. Premium dark workshop aesthetic, warm off-white surfaces for cards, deep ink background, electric lime accent, restrained orange for overdue/warnings, subtle grid/blueprint details, crisp typography, generous spacing, tactile buttons, elegant charts, smooth transitions, and excellent empty states. Avoid generic SaaS gradients, template-looking cards, excessive glassmorphism, and a marketing landing page. Use a coherent icon set if available. Make it feel like a serious tool a real tradesperson would open every day.
Mobile-first, responsive on Android-sized screens, also excellent on desktop. Use a persistent mobile bottom navigation and a desktop sidebar/top bar where appropriate. Respect accessible contrast, visible focus states, reduced motion, and readable type.

APP SHELL / NAVIGATION
Create these real screens:
1. Overview
2. Jobs
3. New Job flow
4. Job Detail
5. Money
6. Customers
7. Settings / data tools

CORE FUNCTIONALITY, MUST ACTUALLY WORK
- Persist all user-created data locally across refreshes using localStorage or the platform's available persistence. No paid API, no mandatory login, no backend requirement for the MVP.
- Seed a small set of clearly marked demo jobs on first launch, with a way to clear demo data. Make the demo immediately useful and visually rich, but distinguish demo data from the user's own entries.
- Create, edit, delete, search, and filter jobs.
- Job fields: job title, customer name, phone (optional), job category, description, agreed labor/service price, estimated materials cost, due date, priority, status, and optional notes.
- Statuses: Quote, Confirmed, In Progress, Waiting, Completed, Cancelled.
- Job detail shows an activity timeline, cost breakdown, payments, remaining balance, notes, and progress status.
- Add individual expenses to a job with label, category (materials, transport, labor, other), amount, date, optional note. Recalculate totals immediately.
- Record partial or full customer payments, method (cash, transfer, other), date, note. Remaining balance must never go below zero; warn if payment exceeds the balance.
- Financial calculations: total job revenue = agreed price; total expenses = estimated materials + logged expenses (avoid double counting if estimate is replaced by actual materials expense; make the distinction explicit); net expected profit = revenue minus expenses; outstanding = revenue minus payments. Clearly label estimates versus actuals.
- Overview cards: active jobs, money received this month, outstanding balance, estimated net profit. Include an attractive cash-flow / job-status visualization if feasible.
- Money screen: received payments, outstanding invoices/balances, expenses, totals, filter by date or job.
- Customer screen: group jobs by customer and show lifetime job count, revenue, outstanding balance, recent work. Customer search.
- Generate a clean, printable/shareable job receipt or work order with customer, work description, agreed price, expenses (optional/private toggle), payments, balance due, dates, and a clear print button. Use browser print to save as PDF. Do not expose private internal notes or expenses by default.
- Provide a one-tap WhatsApp share action using a prefilled text message, with a graceful fallback if WhatsApp is unavailable. Do not pretend to send messages automatically.
- Add CSV export of jobs, payments and expenses; include import/export backup as JSON if practical.
- Empty, loading, validation, success, and error states must be designed, not forgotten.
- Confirm before destructive actions. Use friendly toast/snackbar feedback.
- Form validation: required job title and customer; monetary values must be nonnegative and parse safely; date inputs should work on mobile.
- Include Nigerian Naira (₦) as default currency, with a currency setting if practical. Format numbers cleanly.
- Never fabricate AI-generated prices or material quantities. If an AI helper is available, make it optional and explain that quotes require the worker's own material prices and measurements. Do not add a fake AI button.

KEY USER FLOWS TO DEMONSTRATE
A. Create a job for "Security gate fabrication", add customer and agreed price, save, and see it appear in Overview/Jobs.
B. Open job, add material and transport expenses, record a partial payment, and watch profit and balance update correctly.
C. Change status to Completed.
D. Generate a customer-facing receipt and use print / WhatsApp share.
E. Refresh the page and confirm data persists.
F. Export a backup or CSV.

OVERVIEW DESIGN
Top greeting: "Good morning" or a time-neutral greeting, with a small date label and a prominent "New job" CTA.
Lead with an editorial dashboard, not a generic grid. Strong balance/receivables figure, four compact stat cards, a visual jobs pipeline, and a focused "Needs your attention" section for overdue jobs or unpaid balances. Then recent jobs with status chips and clear actions.
Make the main action usable one-handed on mobile. Bottom navigation: Home, Jobs, Money, Customers, with a central prominent + New Job action if possible.

DATA / ENGINEERING
- Implement actual functional interactions, not static mockups.
- Use well-structured components and reliable data calculations.
- If React/Next is supported, use it. Otherwise use the platform's native supported stack.
- Do not depend on paid services, external APIs, wallet connections, blockchain, or environment secrets for core functionality.
- Keep all data local and include a clear privacy note that data is stored on this device/browser unless exported.
- Add robust demo seed/reset behavior, unique IDs, date-safe calculations, and responsive layout.
- Include app name and a simple custom WorkSlip mark/icon.
- Make the first screen immediately useful and make every visible button work.
- Do not stop at a landing page, mockup, or incomplete scaffold. Finish the core product loop before adding extra features.

QUALITY BAR
Before finishing, manually verify the flows A-F above. Fix broken buttons, mobile overflow, incorrect calculations, and unreadable contrast. Prioritize reliability and thoughtful UX over adding more features.