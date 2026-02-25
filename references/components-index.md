# Components Index

SkipUI supports many SwiftUI components on Android. Below is a short index; for detailed behavior and samples, see the official Skip docs component pages. When this skill includes a dedicated `references/component-*.md` file, use it for that component.

## Layout and structure

- **Stack** (VStack, HStack, ZStack) — `references/component-stack.md` if present
- **List** — `references/component-list.md` if present
- **Grid** — Grid layouts
- **ScrollView** — Scrolling
- **Form** — Form grouping
- **Frame** — Sizing and alignment
- **Spacer** — Flexible space
- **Divider** — Separator
- **SafeArea** — Safe area insets

## Controls and input

- **Button** — `references/component-button.md` if present
- **TextField**, **SecureField** — Text input
- **Toggle** — Switch
- **Picker** — Picker
- **Slider** — Slider
- **DatePicker** — Date selection
- **Menu** — Menus
- **ProgressView** — Progress indicator

## Presentation

- **Sheet** — Modal sheets
- **Alert**, **ConfirmationDialog** — Alerts and dialogs
- **TabView** — Tabs
- **NavigationStack** — Navigation
- **Overlay** — Overlay content

## Content

- **Text** — Text
- **Label** — Label with icon
- **Image** — Images
- **AsyncImage** — Async image (Coil on Android)
- **Icon**, **Symbol** — Icons and SF Symbols
- **Link** — Links
- **Color**, **ColorScheme** — Color and theme
- **Background**, **Border**, **Shadow**, **Shape**, **Gradient** — Styling

## Other

- **Gesture** — Gestures
- **Animation**, **Transition** — Animation
- **State**, **Observable** — State management
- **Localization** — Localized strings
- **Accessibility** — Accessibility
- **VideoPlayer**, **Audio** — Media
- **Toolbar** — Toolbars
- **Searchable** — Search
- **Timer** — Timers
- **Table** — Tables
- **ZIndex** — Z-order
- **Offset**, **OffsetPosition** — Positioning
- **Pasteboard**, **ShareLink** — Sharing and pasteboard
- **HapticFeedback** — Haptics
- **Keyboard** — Keyboard
- **Modifier** — Custom modifiers
- **ScenePhase** — Scene lifecycle
- **Storage** — App storage
- **GeometryReader** — Geometry

For any component not listed in a dedicated `references/component-*.md`, rely on the SkipUI “Supported SwiftUI” list and the official component docs; use `#if os(Android)` and ComposeView when a SwiftUI API is not yet supported.
