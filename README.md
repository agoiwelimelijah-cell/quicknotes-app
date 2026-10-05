# QuickNotes

QuickNotes is a lightweight, responsive note-taking web application engineered with vanilla HTML5, CSS3, and modern JavaScript (ES6+). It enables users to quickly capture ideas, categorise them across Personal, Work, and Study contexts, filter through thoughts in real time, and persist their note database across browser sessions without relying on third-party dependencies.

## Features

- **Categorised Note Taking**: Organise thoughts under Personal, Work, and Study categories with distinctive visual color-coded borders and badges.
- **Client-Side Validation**: Ensures notes cannot be submitted blank or exceed the 200-character limit, with clear inline error messaging.
- **Live Search Filtering**: Instant, case-insensitive keyword search that dynamically updates the note list as you type, complete with empty-state indicators.
- **Persistent Storage**: Automatic synchronisation with browser `localStorage` using `JSON.stringify` and `JSON.parse` to retain data upon refresh.
- **Safe DOM Manipulation**: Built exclusively with `document.createElement()` and `textContent` to eliminate XSS (Cross-Site Scripting) vectors.
- **Dynamic Note Counter**: Accurately reports zero, singular, and plural note counts (`You have no notes yet.`, `You have 1 note.`, `You have N notes.`).
- **Responsive Flexbox Design**: Optimized for seamless interaction across mobile, tablet, and desktop screens with a vertical form stack on narrow viewports ($\le 600\text{px}$).
- **Bonus Feature**: Interactive "Clear all" button with native `confirm()` modal protection.

## How to Run Locally

You can run this project locally without any package managers or build tools:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/quicknotes-app.git
   cd quicknotes-app
   ```

2. **Open in your browser:**
   - On macOS:
     ```bash
     open index.html
     ```
   - On Linux:
     ```bash
     xdg-open index.html
     ```
   - On Windows:
     ```cmd
     start index.html
     ```
   - Or simply drag and drop `index.html` into Google Chrome, Firefox, or Safari.

3. *(Optional)* **Serve via a local HTTP server:**
   ```bash
   # Using Python 3
   python3 -m http.server 8000

   # Or using Node.js npx
   npx serve .
   ```
   Navigate to `http://localhost:8000` in your web browser.

## What I Learned

1. **Defensive DOM Rendering & Security**: Implementing a `render()` function strictly utilizing `document.createElement()` and `textContent` rather than `innerHTML` reinforced how modern web applications prevent Cross-Site Scripting (XSS) when handling untrusted user input.
2. **State & LocalStorage Synchronization**: Managing application state in a single source of truth array (`notes = [...]`) and decoupling state modification from view re-rendering provided clear architecture patterns and made serializing to `localStorage` with `JSON.stringify()` trivial and robust.
3. **Responsive Form Layouts with Flexbox**: Designing a Flexbox-based form that sits inline on desktop displays while gracefully collapsing into an accessible vertical column on mobile devices using `@media (max-width: 600px)` improved understanding of mobile-first and fluid layout principles.
4. **Accessible Form & Error Feedback**: Linking form inputs and labels with explicit `for`/`id` bindings and utilizing ARIA attributes (`role="alert"` and `aria-live="polite"`) ensured the validation messages are immediately comprehensible for assistive technologies.
