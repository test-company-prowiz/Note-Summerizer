# style.css

> **Source File:** [style.css](https://github.com/test-company-prowiz/Note-Summerizer/blob/main/style.css)
> **Repository:** `Note-Summerizer`
> **Branch:** `main`

# style.css

### Overview
This file defines the visual presentation and layout for a web application, providing styles for various UI components, typography, colors, and responsive adjustments. It includes support for a light/dark theme and manages specific layout states for different application views.

### Architecture & Role
This CSS file operates within the presentation layer of the frontend architecture. Its role is to dictate the styling rules that a browser applies to the HTML structure, rendering the user interface according to the defined visual design. It is a core component for the application's aesthetic and user experience.

### Key Components
*   **CSS Custom Properties (`:root`, `body.light-theme`)**: Defines a set of CSS variables for colors, enabling easy theme switching between dark (default) and light modes.
*   **Global Resets (`*`)**: Standardizes `margin`, `padding`, `box-sizing`, and `font-family` across all elements.
*   **Layout Containers (`.container`, `.prompt-container`)**: Styles the main content area and the fixed prompt input section.
*   **Header (`.app-header`)**: Styles the application's main heading and subheading, including a gradient text effect.
*   **Suggestions (`.suggestions`, `.suggestions-item`)**: Styles a horizontally scrollable list of interactive suggestion items with distinct icons.
*   **Chat Interface (`.chats-container`, `.message`, `.bot-message`, `.user-message`)**: Provides styles for displaying chat messages, including avatars, text bubbles, and various attachment types (image, file).
*   **Prompt Input (`.prompt-wrapper`, `.prompt-form`, `.prompt-input`, `prompt-actions`)**: Styles the user input area for submitting prompts, including input field, file upload buttons, and send/cancel actions.
*   **Video Background (`.video-container`)**: Implements a fullscreen background video.
*   **Theming Classes (`body.light-theme`, `body.chats-active`, `body.bot-responding`)**: Modifies styles dynamically based on the active theme or application state.
*   **Media Queries (`@media (max-width: 768px)`)**: Adjusts layout and font sizes for smaller screen devices to ensure responsiveness.

### Execution Flow / Behavior
The browser parses this CSS file and applies its rules to the corresponding HTML elements. Styles are statically applied unless overridden by specific class additions or user interactions.
*   Initial load sets default dark theme variables.
*   Adding `light-theme` class to `body` element switches to light theme variables.
*   Adding `chats-active` class to `body` hides initial header and suggestions.
*   Adding `bot-responding` class to `body` hides the file upload wrapper and shows a 'stop response' button.
*   The `.message.loading` class triggers a rotation animation for the avatar.
*   The `prompt-input:valid` pseudo-class controls the display of the send button.
*   Media queries automatically adjust styles when the viewport width is below 768px.

### Dependencies
*   **External**:
    *   `https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600&display=swap"`: Imports the "Poppins" font family from Google Fonts for typography.
*   **Internal**:
    *   **HTML Structure**: Relies on specific class names and element hierarchies (e.g., `body`, `.container`, `.app-header`, etc.) to apply styles correctly.
    *   **JavaScript (Implicit)**: Assumes JavaScript is used to dynamically add/remove classes like `light-theme`, `chats-active`, `bot-responding`, `loading`, `active`, `img-attached`, `file-attached` to control theme, view state, and interactive elements.

### Design Notes
*   **Theming with CSS Variables**: The use of CSS custom properties in `:root` and `body.light-theme` allows for a centralized and maintainable way to manage color schemes, enabling a seamless dark/light mode transition via a single class toggle.
*   **Responsive Design**: Media queries are implemented to adapt the UI for mobile devices, ensuring usability across various screen sizes.
*   **Scroll Customization**: Custom scrollbar styling is applied within the `.container` to match the application's aesthetic. Horizontal scrolling with `scroll-snap-type` is used for the suggestions list.
*   **Gradient Text**: The `background-clip: text` and `-webkit-text-fill-color: transparent` properties are used to achieve a visually appealing gradient effect on the main heading.
*   **Fixed Background Video**: A fullscreen video background provides an immersive visual element, positioned behind other content using `z-index: -1` and `object-fit: cover`.

### Diagram
None significant.