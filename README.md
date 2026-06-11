# OmniBoard

OmniBoard is a single-file interactive whiteboard application built with React, HTML Canvas, and Tailwind CSS. It supports freehand drawing, geometric shapes, text, element selection, resizing, panning, zooming, and multiple saved boards.

## Features

- Infinite-style canvas with pan and zoom controls
- Freehand pen with optional shape recognition
- Rectangles, circles, cubes, lines, arrows, and text labels
- Select, move, resize, erase, and delete elements
- Adjustable colors, stroke widths, and shape fills
- Grid, dot, and blank canvas backgrounds
- Multiple named whiteboards
- Automatic saving
- Browser `localStorage` support for standalone use
- Optional Firebase Authentication and Firestore synchronization
- Mouse, touch, and keyboard input

## Run Locally

No build process is required.

1. Open `infinite_interactive_whiteboard.html` in a modern web browser.
2. Start drawing using the toolbar.

The page loads React, Babel, Tailwind CSS, and Firebase modules from public CDNs, so an internet connection is required when the application first loads.

For a more reliable browser environment, serve the directory with a local HTTP server:

```powershell
npx serve .
```

Then open the address printed in the terminal.

## Storage

When Firebase credentials are not provided, OmniBoard automatically stores boards in the browser's `localStorage`. Data remains available in the same browser and origin.

When valid Firebase configuration is supplied through the expected environment variables, the application uses anonymous authentication and Firestore for cloud storage.

Supported global configuration values:

```js
__firebase_config
__initial_auth_token
__app_id
```

## Controls

| Action | Control |
| --- | --- |
| Select tool | `V` |
| Pen tool | `P` |
| Rectangle tool | `R` |
| Circle tool | `O` |
| Delete selected element | `Delete` or `Backspace` |
| Clear selection | `Escape` |
| Pan canvas | Select tool + `Shift` drag, middle mouse drag, or pan tool |
| Rename board | Click the board name |
| Add text | Select the text tool, click the canvas, type, and press `Enter` |

## Project Structure

```text
.
|-- infinite_interactive_whiteboard.html
`-- README.md
```

All interface styles, React components, canvas drawing logic, persistence, and Firebase integration are contained in `infinite_interactive_whiteboard.html`.

## Technology

- React 18
- HTML Canvas API
- Tailwind CSS
- Babel Standalone
- Firebase Authentication
- Cloud Firestore
- Browser Local Storage

## Notes

- Cloud collaboration requires a valid Firebase project and suitable Firestore security rules.
- Local boards are specific to the browser and site origin used to open the application.
- Clearing browser storage removes locally saved boards.
