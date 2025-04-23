Save Annotations

The Save Annotations feature lets users persist everything they’ve drawn on the whiteboard and include it in exports.
📦 Supported Export Formats

    PDF

    PPTX

    IWB (Whiteboard file)

🛠️ External Libraries

    pptxgenjs — generate PowerPoint (.pptx) slides

    jszip — bundle multiple files into a single archive

    jspdf — create PDF documents

✂️ Exclude Pages from Export

Users can remove individual annotation pages before exporting. Each saved page in the annotation modal has a Delete button—clicking it will exclude that page from any future export.
File Location

All related code lives at:

WhiteBoardFrontEnd/
└── packages/
    └── flat-components/
        └── src/
            └── components/
                └── SaveAnnotationModal/
                    └── index.tsx

Usage

    Open the Save Annotations modal from the toolbar.

    Review your saved pages.

    (Optional) Delete any page you don’t want to include.

    Click Export and choose your desired format: PDF, PPTX, or IWB.
