Custom Toolbar

We’ve replaced the default Flat Whiteboard toolbar (which was disabled via config) with a fully bespoke toolbar split into three sections: Main, Left, and Right.
⚙️ Disabling the Default Toolbar

The default toolbar (and undo/redo, page control, zoom) is disabled in:

// path: service-providers/fastboard/src/index.ts
config: {
  toolbar:     { enable: false, apps: { enable: true } },
  redo_undo:   { enable: false },
  page_control:{ enable: false },
  zoom_control:{ enable: false },
},

🧩 Custom Toolbar Structure

All custom-toolbar components live under:

WhiteBoardFrontEnd/
└── packages/
    └── flat-pages/
        └── src/
            └── components/
                └── CustomTool/

    Main Toolbar

        Core whiteboard actions (select, pen, shapes, etc.)

        Docs & props: ReadMeCustomToolbarMain.md

    Left Toolbar

        Redo and undo

        Docs & props: ReadMeCustomToolbarLeft.md

    Right Toolbar

        Add pages, preview, page navigation

        Docs & props: ReadMeCustomToolbarRight.md

Integration in Whiteboard

The custom toolbars are injected in:

WhiteBoardFrontEnd/
└── packages/
    └── flat-pages/
        └── src/
            └── components/
                └── Whiteboard.tsx

Here, whiteboardStore is passed down to the Main and Right toolbars for managing apps and page controls—details live in each toolbar’s README.
🎨 Styling

All positioning, sizing, and color styles for the custom toolbar live in:

WhiteBoardFrontEnd/
└── packages/
    └── flat-pages/
        └── src/
            └── styles/
                └── whiteboard.less
