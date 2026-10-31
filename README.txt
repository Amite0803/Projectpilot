ProjectPilot Offline Tool
=========================

How to use:
1. Double-click "index.html" to open it in your web browser (Chrome, Edge, Firefox all work).
2. No internet connection is required — the Excel export library (xlsx.full.min.js) is
   bundled in this folder, so keep index.html and xlsx.full.min.js together.
3. Your data auto-saves in the browser (localStorage) as you type, so you can close the
   tab and reopen index.html later without losing work — as long as you use the same
   browser on the same computer.
4. To move your project to another computer, or keep a permanent backup, click
   "Save Project File As..." (top right, or on the Dashboard tab) to choose a filename
   and folder for a .json file (in Chrome/Edge this opens a normal "Save As" dialog; other
   browsers save it to your default Downloads folder). Use "Load Project File" to re-open
   it later, on any computer, in this same tool.
5. Use "Export to Excel" (on the Pricing & Planned Budget or Pricing Summary tab, or "Export Full
   Excel Report" on the Dashboard tab) to get a multi-sheet .xlsx workbook with Pricing,
   Pricing by Section/Unit, Budget Plan vs Actual, and Dashboard/P&L data.

Tabs:
1. Pricing & Planned Budget   — build your WBS line items, apply risk factors, contingency and
                       profit margin to calculate the price. This becomes your Plan
                       baseline. Choose your currency (US$, €, ₪) here too.
2. Pricing Summary  — a consolidated report: total sum, pricing by category, a summary
                       for each category headline (section), and a pricing-by-unit table
                       including contingency and profit.
3. Budget — Plan vs Actual — track actual quantities/costs against the plan as work
                       progresses, see variance and % used per line and by category.
4. Income & Revenue — log income/revenue milestones, each linked to a WBS code from the
                       Pricing & Planned Budget tab. Track planned amount/date vs. actual amount/date
                       received per milestone, plus totals and % collected.
5. Dashboard & P&L  — KPIs, Estimate to Complete (ETC), forecast cost at completion,
                       gross margin vs revenue, and a Cash Flow section (cash in vs cash
                       out, net cash position, outstanding receivables, and a chart of
                       cumulative planned vs. actual cash received over time).

Budget timelines & cash flow analysis (Budget tab):
Under the budget table, "Budget Timeline — Planned vs Actual" lets you enter a planned
start/end and an actual start/end date for every budget line. Each line's cost is spread
evenly by day across its period (planned cost over the planned dates, actual cost over the
actual dates) and summed by month. Shortcuts: "Fill empty planned dates from project
period" (set Project Start/End first) and "Copy planned dates to empty actual dates".
If a line has actual cost but no actual dates it is placed on its planned dates; an actual
start with no end date runs through today. The schedule column shows days early/late.
"Expense Timeline & Cash Flow Analysis" then shows: a monthly planned-vs-actual expense
bar chart, cumulative cash flow (planned/actual cash in vs cost), the net cash position,
peak funding need and break-even month, and a monthly table. Cash in comes from the dated
milestones on the Income & Revenue tab. The Dashboard cash flow chart uses the same data,
and the Excel export adds "Budget - Timeline" and "Cash Flow - Monthly" sheets.

Schedule (Gantt) tab:
A Gantt chart built from your budget items, grouped by section headline or by budget
category (switch with "Group by"). Blue bars are planned dates, green bars are actual dates
(red when finished after plan; a bar with an actual start but no end runs to today), and a
dark span shows each section/category. A red dashed line marks today. Zoom controls the width.
- Milestones: "+ Add Milestone" for key dates (diamonds on the chart, orange = open, green =
  done). Link one to a task and tick "follows task end" to keep it on that task's planned
  finish automatically.
- Dependencies: in "Task Dates & Dependencies" add predecessors to any task (finish-to-start).
  Arrows run from the predecessor's finish to the successor's start; red arrows are conflicts
  (the task starts before a predecessor finishes). "Fix dependency conflicts" shifts those tasks
  later, keeping their duration. Circular links are blocked.
- Auto schedule: the "Auto schedule" button proposes planned start and end dates for every
  task. Task length is estimated from quantity and unit (8 hours = 1 day, 1 month = 21 working
  days, days/shifts/sessions as entered, other units 5 days). Sections and sub-sections run one
  after another, tasks inside a section run in parallel, and your dependencies are always
  respected. Options: project start (and optional end date to fit the schedule to), apply to
  only tasks without dates or to all tasks, skip weekends, keep existing durations, and add a
  milestone at the end of each phase. Budget-only lines span the whole project. A preview table
  shows every proposed date before you press Apply, and "Undo auto schedule" restores the
  previous dates and milestones.
- Planned dates are shared with the Budget tab, so editing them in either place updates both,
  along with the expense and cash flow charts. The Excel export adds "Schedule - Dependencies"
  and "Schedule - Milestones" sheets.

Income & Revenue milestones:
Add milestones on the Income & Revenue tab and link each one to a WBS code via the
dropdown (populated from WBS codes you entered on the Pricing & Planned Budget tab). Once you add
at least one milestone, the sum of their Planned Amounts automatically replaces the
manual "Contract / Revenue Value" field on the Budget tab everywhere revenue is used
(Dashboard KPIs, P&L). Actual Amounts (with an Actual Date) feed the Cash Flow section
and its chart on the Dashboard. If you never add milestones, the manual Contract/Revenue
Value field keeps working exactly as before.

Category headlines, WBS levels and numbering:
On the Pricing & Planned Budget tab the line items form a WBS hierarchy. A headline is
level 1, a subcategory is level 2, a sub-subcategory level 3, and so on (up to 6); line items
sit beneath the headline they belong to. WBS numbers are generated automatically from the
levels (1, 1.1, 1.1.1 ...) and renumber themselves whenever you add, delete, move or change
the level of a row, so the number always follows the level.
- "+ Add Category Headline" adds a level-1 headline; "+ Add Subcategory" adds a headline one
  level below the previous one. "+ Add Item" adds a line under the last row.
- Use the ◀ ▶ buttons to promote/demote a row. Demoting or promoting a headline takes its
  sub-rows with it (like an outline), and following rows can become part of it, so check the
  numbers after a change. A row can only go one level deeper than the row above it, and a line
  item cannot have children.
- Use ▲ ▼ to move a row; moving a headline moves everything beneath it.
- Headline subtotals roll up through all levels. The Budget tab shows the Level column and the
  same hierarchy with rolled-up Plan and Actual totals on each headline row. The Pricing Summary
  "Summary by Section" table lists every headline with its WBS number and level. Budget-only
  lines you add on the Budget tab keep a manually typed WBS number; their level follows the
  number of dots (9.1 = level 2).
- Income milestones are linked to a WBS row (headline or item), not to a typed number, so links
  survive renumbering. Older project files are converted automatically on load (headlines
  become level 1, line items level 2; any custom WBS numbers are replaced by generated ones).

Layout and design:
The tool is a responsive web page: it adapts from phones to wide desktop screens. The tab bar
stays pinned at the top while you scroll (it scrolls sideways on narrow screens; arrow keys
switch tabs), and a key-figures strip under it always shows total price, planned budget, actual
cost and net cash. On wide screens the Assumptions and Pricing Summary stay in view next to the
line items. Wide tables scroll sideways inside their card instead of stretching the page. The
Pricing Summary tab adds a "how the price builds up" bar and a cost-by-category donut chart.
It needs no internet connection and no server, and it prints cleanly (the tab bar, buttons and
key-figures strip are hidden on paper).

Information box and project notes:
The "i" button next to the "Pricing & Planned Budget" heading opens an explanation of
estimated budget, price proposal, planned budget and budget baseline, with your current
figures. Project Information also has two free-text boxes: "Project description & details"
and "Budget notes". They are saved with the project, cleared by Clear All, and included in
the Excel "Pricing - Summary" sheet.

Clear All:
The "🗑️ Clear All" button on the Pricing & Planned Budget tab resets everything on that tab back
to a blank slate: all items and category headlines are removed, Project Information
(name, client, prepared by, date, currency) is cleared, and Assumptions (risk factors,
contingency, profit margin) are reset to their defaults. It asks for confirmation first
and cannot be undone — save a project file beforehand if you want to keep a copy.

Sample file:
"Sample - Kosovo Water Source Project.json" is a ready-made example, rebuilt from the
attached Sample-pricing.xlsx workbook (Kosovo water source project). It shows 9 category
headlines (Professional services, Field surveys assistance, GIS software licenses and
database development, Digital platform development and maintenance, Transportation and
accommodation, Preparation/publication of reports, Training workshops, Administrative
expenses, Unexpected) with all of the original line items, quantities and unit costs.
Open index.html and click "Load Project File" to try it.

Nothing in this tool is sent to any server — everything runs locally in your browser.
