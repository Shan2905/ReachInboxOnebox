# ReachInbox Onebox - Design Guidelines

## Design Approach: Design System (Linear/Superhuman-Inspired)

**Selected Approach**: Modern email dashboard inspired by Linear's clarity and Superhuman's efficiency  
**Justification**: This is a utility-focused productivity tool where information density, scannability, and task efficiency are paramount. Users need to quickly process emails, not be impressed by marketing visuals.

**Core Principles**:
- Information hierarchy over decoration
- Instant scanability for rapid email triage
- Clear visual categorization for AI labels
- Minimal cognitive load through consistent patterns

---

## Color Palette

**Dark Mode (Primary)**:
- Background: 15 8% 10% (deep charcoal)
- Surface: 15 8% 15% (elevated panels)
- Border: 15 8% 25% (subtle separation)
- Text Primary: 0 0% 95%
- Text Secondary: 0 0% 60%

**Category Colors**:
- Interested: 142 70% 45% (vibrant green)
- Follow-up: 38 95% 55% (warm amber)
- Not Interested: 0 0% 45% (neutral gray)

**Accent**: 217 91% 60% (bright blue for actions/links)

**Light Mode** (if needed):
- Background: 0 0% 100%
- Surface: 0 0% 98%
- Border: 0 0% 88%
- Text Primary: 0 0% 10%
- Text Secondary: 0 0% 40%

---

## Typography

**Font Stack**: `Inter, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif` (via Google Fonts CDN)

**Scale**:
- Email Subject: 15px, font-medium (600)
- Email Sender: 14px, font-normal (400)
- Email Preview: 13px, font-normal (400), text-secondary
- Timestamps: 12px, font-normal (400), text-secondary
- Category Labels: 11px, font-semibold (600), uppercase tracking-wide
- Sidebar Nav: 14px, font-medium (500)
- Page Headers: 24px, font-semibold (600)

---

## Layout System

**Spacing Primitives**: Tailwind units of 2, 4, 6, 8, 12, 16 (p-2, p-4, m-6, gap-8, etc.)

**Layout Structure**:
- Three-column layout: Sidebar (256px) | Email List (400px flexible) | Email Detail (remainder)
- Sidebar: Fixed navigation, account switcher, folder tree
- Email List: Scrollable list, search bar at top, filters below
- Detail Pane: Full email content with action toolbar

**Responsive Behavior**:
- Desktop (>1024px): Three-column layout
- Tablet (768-1024px): Two-column (hide detail pane, show on selection)
- Mobile (<768px): Single column stack with slide-over detail

---

## Component Library

**Navigation Sidebar**:
- Account selector dropdown at top (with avatar/icon)
- Folder list: Inbox, Sent, Drafts with unread counts
- Use icons from Heroicons (outline style)
- Active state: subtle background highlight (surface + 5% lightness)

**Email List Item**:
- Compact row: 60px height, px-4 py-3
- Left: Checkbox (hidden until hover)
- Avatar/Initial circle (40px) for sender
- Center: Sender name (bold if unread), Subject line, Preview snippet (truncated)
- Right: Timestamp, Category badge
- Hover state: background surface color
- Unread indicator: bold text + subtle left border accent

**Category Badges**:
- Pill shape: rounded-full px-3 py-1
- Semi-transparent background: bg-[category-color]/10
- Bold text: text-[category-color] font-semibold
- Small size: text-xs

**Search Bar**:
- Full width in email list header
- Height: 40px with rounded-lg
- Magnifying glass icon (Heroicons) on left
- Placeholder: "Search emails..."
- Border on focus: accent color

**Filter Dropdowns**:
- Minimal button style with chevron icon
- Dropdown menu: surface background, subtle shadow
- Options with checkboxes for multi-select
- Apply/Clear buttons at bottom

**Email Detail Pane**:
- Header: Subject (large), sender info, timestamp
- Action toolbar: Reply, Forward, Archive, Delete (icon buttons)
- Body: max-width prose for readability, preserve formatting
- Bottom: Category selector (three buttons for AI categories)

**Action Buttons**:
- Primary: bg-accent text-white rounded-md px-4 py-2
- Secondary: border border-border text-primary rounded-md px-4 py-2
- Icon-only: p-2 rounded-md hover:bg-surface

---

## Interactions & States

**Animations**: Use sparingly
- List item hover: instant background color (no transition)
- Dropdowns: simple fade-in (150ms)
- Panel transitions: slide (200ms ease-out) when switching views
- Avoid unnecessary motion to maintain productivity focus

**Loading States**:
- Email list: skeleton placeholders (3-4 rows)
- Detail pane: subtle spinner, centered
- Search: inline spinner in search bar

**Empty States**:
- Center-aligned icon + text for empty folders
- "No results" message for failed searches
- Helpful copy: "All caught up!" for empty inbox

---

## Data Visualization

**Unread Counts**: Numeric badges next to folder names (bg-accent, rounded-full, px-2, text-xs)

**Search Highlights**: Matching text in yellow background (bg-yellow-200/20) in search results

**Status Indicators**: Small colored dots for account status (online/syncing)

---

## Images

**No hero images needed** - this is a dashboard application

**Avatar/Profile Images**:
- Sender avatars in email list (32px circles)
- Account selector avatar (40px circle)
- Use initials with colored backgrounds if no image available
- Color generation: hash email address to pick from preset palette

---

## Professional Polish

- Consistent 8px border-radius for all panels and buttons
- Subtle box-shadow on elevated panels: `shadow-sm`
- 1px borders using border-border color for clear separation
- Maintain 24px padding around main content areas
- Email list max-width: 600px for optimal scanning
- Detail pane: max-width prose (65ch) for email body readability