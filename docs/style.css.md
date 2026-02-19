# style.css

### Overview
This file serves as the primary stylesheet for a web application, defining its visual presentation, layout, and user interface elements. It establishes global styles, implements a theming system, and styles various components such as headers, suggestion cards, chat messages, and the user prompt input area.

### Architecture & Role
This stylesheet operates at the presentation layer of the application's client-side architecture. Its role is to dictate the visual appearance of HTML elements, ensuring a consistent user experience and responsive design across different screen sizes. It is a static asset loaded by the browser to apply styles to the Document Object Model (DOM).

### Key Components
*   **Global Resets & Base Styles**: Universal `margin`, `padding`, `box-sizing`, and `font-family` are set for all elements, along with base `body` colors.
*   **CSS Custom Properties (`:root`, `body.light-theme`)**: Defines a set of variables for colors (text, primary, secondary, etc.) to support both a default (dark) theme and a `light-theme` variant activated by a class on the `body` element.
*   **`.container`**: The main scrollable content area, managing internal padding and scrollbar appearance.
*   **`.app-header`**: Contains the main `heading` with a gradient text effect and a `sub-heading`.
*   **`.suggestions`**: A horizontally scrollable list of interactive `.suggestions-item` cards, each with text and an icon, providing initial user prompts or actions.
*   **`.video-container`**: Styles for a fixed, full-screen background video element.
*   **`.chats-container`**: Manages the display of individual `.message` elements, differentiating between `.bot-message` and `.user-message` with specific styling for avatars, text, image, and file attachments.
*   **`.prompt-container`**: A fixed bottom section housing the user `prompt-form`, `prompt-input`, and associated `prompt-actions` like file upload and send buttons.
*   **Animation (`@keyframes rotate`)**: Defines a rotation animation used for loading states, specifically on bot message avatars.
*   **Media Queries**: Provides responsive adjustments for smaller screen sizes, modifying font sizes, spacing, and element dimensions.

### Execution Flow / Behavior
Upon page load, global styles and the default (dark) theme defined in `:root` are applied. If the `body` element acquires the `light-theme` class, the corresponding CSS custom properties override the default values, switching the application's color scheme.

The display of certain UI elements is dynamically controlled by classes on the `body`:
*   `body.chats-active`: Hides the `.app-header` and `.suggestions` elements, typically when a chat session begins.
*   `body.bot-responding`: Hides the file upload wrapper and displays a "stop response" button within the prompt area.

User interaction with the prompt input:
*   The `#send-prompt-btn` is hidden by default and becomes visible when the `.prompt-input` contains valid (non-empty) text, using the `:valid` pseudo-class.
*   The `.file-upload-wrapper` changes its appearance and visible controls based on the `active`, `img-attached`, or `file-attached` classes, managing the display of the file attachment button, image preview, file icon, and cancel button.
*   The `loading` class on a message triggers an avatar rotation animation.

### Dependencies
*   **External**: The stylesheet imports the "Poppins" font family from Google Fonts via `@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600&display=swap");`.
*   **Internal**: It relies heavily on a specific HTML structure and class naming conventions to correctly apply styles to the intended elements. Changes to HTML structure or class names would break the associated styling.

### Design Notes
*   **Theming System**: Utilizes CSS custom properties to implement a robust dark/light mode, centralizing color definitions and simplifying theme switching by toggling a single class on the `body` element.
*   **Responsive Design**: Employs media queries to adapt the layout and typography for various screen sizes, ensuring usability on mobile devices.
*   **Component-Based Styling**: Styles are organized around distinct UI components (e.g., `app-header`, `suggestions`, `chats-container`, `prompt-container`), promoting modularity and maintainability.
*   **Visual Feedback**: Includes hover states for interactive elements (e.g., `suggestions-item`, buttons) and a loading animation for bot responses, enhancing user experience.
*   **Accessibility**: The use of `overflow-x: auto` and `scroll-snap-type` for suggestions suggests an intent for horizontal scrolling with defined snap points, which can aid navigation.

### Diagram (Optional)
None significant.