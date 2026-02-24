# style.css

> **Source File:** [style.css](https://github.com/Note-Summerizer/blob/main/style.css)  
> **Repository:** `Note-Summerizer`  
> **Branch:** `main`

### Overview
This file defines the global styling for a web application, including base typography, color schemes, responsive layouts, and visual presentation for various UI components. It establishes a default dark theme and supports a light theme variant through CSS variables.

### Architecture & Role
This CSS file operates at the presentation layer of the application's frontend. It dictates the visual rendering of HTML elements, responding to global states (like theme changes or chat activity) and user interactions to provide a consistent and responsive user experience. It is designed to be loaded early in the page lifecycle to ensure immediate styling.

### Key Components
*   **Global Reset (`*`)**: Sets `margin: 0`, `padding: 0`, `box-sizing: border-box`, and a default `font-family` (Poppins).
*   **CSS Variables (`:root`, `body.light-theme`)**: Defines a comprehensive set of custom properties for colors (`--text-color`, `--primary-color`, etc.) to support both dark (default) and light themes.
*   **Typography**: Imports "Poppins" from Google Fonts and applies it globally. Defines distinct styles for headings and subheadings.
*   **Layout Classes**:
    *   `.container`: Manages the main content area, including scrolling behavior and padding.
    *   `.app-header`: Styles the main application title and subtitle.
    *   `.suggestions`: Styles a horizontally scrollable list of suggestion items.
    *   `.chats-container`: Styles the message display area for chat interactions.
    *   `.prompt-container`: Styles the fixed input area at the bottom of the screen.
*   **Theming**: The `body.light-theme` class overrides default CSS variables to switch the entire application's color scheme.
*   **State-Dependent Styling**:
    *   `body.chats-active`: Hides the app header and suggestions when a chat is active.
    *   `body.bot-responding`: Hides file upload functionality and shows a "stop response" button in the prompt.
    *   `.prompt-input:valid`: Controls the visibility of the send button based on input content.
    *   `.file-upload-wrapper.active`: Manages visibility of file attachment elements.
    *   `.message.loading`: Applies a rotation animation to avatars for loading states.
*   **Responsive Design**: Utilizes `@media (max-width: 768px)` queries to adjust layouts, font sizes, and component dimensions for smaller screens.
*   **Animations (`@keyframes rotate`)**: Defines a simple 360-degree rotation animation for loading indicators.
*   **Background Video (`.video-container`)**: Positions a full-screen background video element behind the main content.

### Execution Flow / Behavior
Upon page load, the browser interprets and applies the styles defined in this CSS file.
1.  **Initial Render**: Global resets, font imports, and default `:root` CSS variables are applied, establishing the initial dark theme and base layout.
2.  **Theme Switching**: If the `body` element dynamically receives the `light-theme` class (presumably via JavaScript interaction), the associated CSS variables override the default ones, visually transforming the application to the light theme.
3.  **UI State Transitions**:
    *   When a chat session begins, adding `chats-active` to `body` will hide initial UI elements like the app header and suggestions.
    *   During bot responses, `bot-responding` on `body` modifies the prompt area, showing a stop button and hiding file upload options.
    *   User input in the prompt field enables/disables the send button through `:valid` pseudo-class styling.
    *   Attachment of a file dynamically applies `.img-attached` or `.file-attached` classes to the `.file-upload-wrapper`, controlling the display of attachment previews and cancel buttons.
    *   Loading messages apply a `rotate` animation to the avatar.
4.  **Responsiveness**: The defined media queries automatically adjust the layout and sizing of elements when the viewport width falls below 768 pixels, providing an optimized experience for mobile devices.

### Dependencies
*   **External**:
    *   `https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600&display=swap`: Imports the "Poppins" font family from Google Fonts for consistent typography.
*   **Internal**:
    *   **HTML Structure**: This CSS file is heavily dependent on specific class names (e.g., `.container`, `.app-header`, `.prompt-wrapper`) and a structured HTML document hierarchy to correctly apply its styles.

### Design Notes
*   **Theming**: The use of CSS custom properties (`--*`) provides a robust and easily maintainable system for theme management, allowing for simple theme switching by toggling a single class on the `body` element.
*   **Modularity**: Styles are grouped logically by component (e.g., `.suggestions`, `.chats-container`, `.prompt-container`), which aids in understanding and maintenance.
*   **Responsiveness**: Media queries ensure a usable experience across different screen sizes. More detailed breakpoint management might be considered for complex layouts.
*   **Accessibility**: While some basic interactive states are handled (e.g., `:hover`), further consideration for accessibility, such as focus states for keyboard navigation and sufficient color contrast, would enhance usability.
*   **Background Visuals**: The `video-container` positions a background video using `object-fit: cover`, ensuring it fills the screen while maintaining aspect ratio, which is a common design pattern for immersive landing pages.

### Diagram (Optional)
None significant.