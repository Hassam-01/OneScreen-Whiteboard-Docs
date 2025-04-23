# OneScreen Whiteboard: Custom Toolbar

This document explains how to disable the default Flat Whiteboard toolbar, add your custom toolbar (main, left, and right), and where to find implementation details.

---

## Table of Contents

1. [Disabling the Default Toolbar](#disabling-the-default-toolbar)  
2. [Adding the Custom Toolbar](#adding-the-custom-toolbar)  
3. [Toolbar Folder Structure](#toolbar-folder-structure)  
4. [Configuration & Props](#configuration--props)  
5. [Styling](#styling)  
6. [Detailed Documentation](#detailed-documentation)  

---

## Disabling the Default Toolbar

In `WhiteBoardFrontEnd/service-providers/fastboard/src/index.ts`, disable the built‑in toolbar:

```ts
config: {
  toolbar: {
    enable: false,
    apps: { enable: true },      // keep apps panel if needed
  },
  redo_undo:    { enable: false },
  page_control: { enable: false },
  zoom_control: { enable: false },
},
```
This removes the left‑side default toolbar so you can inject your own.
Adding the Custom Toolbar

All custom toolbar components are mounted in:

WhiteBoardFrontEnd/packages/flat-pages/src/components/Whiteboard.tsx

Notice how <CustomToolbarMain> and <CustomToolbarRight> receive the whiteboardStore prop:
```bash
<CustomToolbarMain whiteboardStore={whiteboardStore} />
<CustomToolbarLeft /* no store needed */ />
<CustomToolbarRight whiteboardStore={whiteboardStore} />
```

    Main: Hosts global actions and tools

    Left: App launcher and auxiliary controls

    Right: Page navigation & app‑specific panels

Toolbar Folder Structure
```ts
WhiteBoardFrontEnd
└── packages
    └── flat-pages
        └── src
            └── components
                └── CustomTool
                    ├── CustomToolbarMain.tsx
                    ├── CustomToolbarLeft.tsx
                    ├── CustomToolbarRight.tsx
```

Styling

All positioning, colors, and responsive behavior live in(not internal styling of toolbar):

WhiteBoardFrontEnd/packages/flat-pages/src/components/Whiteboard.less

Adjust .toolbar-main, .toolbar-left, and .toolbar-right classes to tweak layout, z‑index, and theming.
Detailed Documentation

    Main Toolbar
    Read the full spec and API here:
    https://github.com/Hassam-01/OneScreen-Whiteboard-Docs/blob/main/ReadMeCustomToolbarMain.md

    Left Toolbar
    Details & examples:
    https://github.com/Hassam-01/OneScreen-Whiteboard-Docs/blob/main/ReadMeCustomToolbarLeft.md

    Right Toolbar
    Page control, apps, notes:
    https://github.com/Hassam-01/OneScreen-Whiteboard-Docs/blob/main/ReadMeCustomToolbarRight.md
