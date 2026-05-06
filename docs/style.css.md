# style.css

> **Source File:** [style.css](https://github.com/test-company-prowiz/Note-Summerizer/blob/main/style.css)
> **Repository:** `Note-Summerizer`
> **Branch:** `main`

# style.css

### Overview
This file serves as the primary stylesheet for the application's user interface. It defines the visual presentation, layout, and responsiveness of various components, including global typography, color themes, chat messages, a prompt input area, and interactive elements.

### Architecture & Role
Architecturally, `style.css` is a core part of the frontend's presentation layer. It directly influences the user experience by defining how HTML elements are rendered in the browser. It implements a two-theme system (light and dark) and handles responsive adjustments for different screen sizes, acting as the single source of truth for the application's visual design.

### Key Components
*   **CSS Variables**:
    *   `--text-color`, `--subheading-color`, `--placeholder-color`, `--primary-color`, `--secondary-color`, `--secondary-hover-color`, `--scrollbar-color`: Define the application's color palette, dynamically switching between default (dark) and `light-theme` variants.
*   **Global Selectors**:
    *   `*`: Resets default browser margins, paddings, and sets `box-sizing` and `font-family`.
    *   `body`, `html`: Establishes base font colors, background, and ensures full viewport height.
*   **Layout & Container Elements**:
    *   `.container`: Manages the main scrollable content area's dimensions and internal padding.
    *   `.app-header`: Styles the main application title and subtitle, including a gradient text effect.
    *   `.suggestions`: Styles a horizontal, scrollable list of interactive prompt suggestions.
*   **Chat Interface Components**:
    *   `.chats-container`: Organizes individual chat messages.
    *   `.message`: Base style for chat messages, including avatar and text.
    *   `.bot-message`, `.user-message`: Specific styles for bot and user messages, handling alignment, background, and content like image/file attachments.
*   **Prompt Input Section**:
    *   `.prompt-container`: Fixed footer area for user input.
    *   `.prompt-form`: Styles the input field and associated action buttons.
    *   `.prompt-input`: The text input field itself.
    *   `.file-upload-wrapper`: Manages file attachment UI states (add, display, cancel).
*   **State-Dependent Classes**:
    *   `body.light-theme`: Activates the light color scheme by overriding CSS variables.
    *   `body.chats-active`: Controls visibility of the header and suggestions when a chat is active.
    *   `body.bot-responding`: Manages visibility of "stop response" button and file upload elements during bot processing.
    *   `.prompt-form .prompt-input:valid~.prompt-actions #send-prompt-btn`: Controls the visibility of the send button based on input validity.

### Execution Flow / Behavior
When the application loads, `style.css` is parsed by the browser.
1.  Global resets and base styles are applied.
2.  CSS variables from `:root` establish the default (dark) theme.
3.  If the `body` element has the `light-theme` class, the corresponding CSS variables override the defaults, changing the color scheme.
4.  Content within `.container` is styled for overflow and scrollability.
5.  UI elements like `.app-header`, `.suggestions`, `.chats-container`, and `.prompt-container` receive their respective layouts and visual properties.
6.  The display of certain elements (e.g., header/suggestions) is dynamically controlled by the presence of `body.chats-active`.
7.  The prompt input area's functionality, such as the visibility of the "send" button or file attachment UI, changes based on input validity or classes like `file-upload-wrapper.active` and `body.bot-responding`.
8.  Media queries adapt the layout and element sizing for screen widths up to 768px, ensuring responsiveness.

### Dependencies
*   **External**:
    *   `https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600&display=swap`: Imports the Poppins font from Google Fonts, which is used throughout the application for typography.
*   **Internal**:
    *   Relies on a specific HTML structure to apply styles correctly (e.g., `.container`, `.app-header`, `.prompt-container`).
    *   Assumes JavaScript will add/remove classes like `light-theme`, `chats-active`, `bot-responding`, and manage input validity to trigger dynamic styling.

### Design Notes
*   **Theming**: The extensive use of CSS variables in `:root` and `body.light-theme` facilitates a clear, maintainable dark/light theme implementation.
*   **Responsive Design**: A single media query at `max-width: 768px` provides adjustments for smaller screens, simplifying the responsive layout logic.
*   **Semantic Naming**: Class names generally reflect their purpose (e.g., `app-header`, `suggestions-item`, `prompt-container`), contributing to code readability.
*   **Dynamic UI States**: Styles are tightly coupled with specific `body` classes and pseudo-classes (`:valid`, `:hover`) to manage complex UI states (e.g., chat activity, bot response, file attachment preview).
*   **Performance**: `scrollbar-width: none` and `scrollbar-color` are used for custom scrollbar styling, though `scrollbar-width: none` is non-standard and may only apply to Firefox.

### Diagram
None significant.