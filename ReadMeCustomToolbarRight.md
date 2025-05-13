
Custom Toolbar Right - Readme
Overview

This component handles whiteboard page navigation and management, including:

    Preview (thumbnail view of all pages)

    Page Navigation (next/previous page)

    Page Jump (direct navigation to a specific page)

    Page Management (add/delete pages)

Features
Page Preview

    Displays thumbnails of all whiteboard pages

    Uses the existing getSaveAnnotationImages() method from whiteboardStore to fetch page previews:
    typescript

    const images = whiteboardStore.getSaveAnnotationImages();  

    Clicking a thumbnail jumps to the corresponding page.

Page Navigation

    Next Page → Moves to the next page in sequence.

    Previous Page → Moves to the previous page.

    Page Jump → Directly navigates to a selected page using:
    typescript

    app.jumpPage(index);  

Page Management

    Add Page → Inserts a new blank page.

    Delete Page → Removes the current page after confirming its index:
    typescript

    app.removePage(index);  

Dependencies

    whiteboardStore (passed from whiteboard.tsx) → Provides page preview images.

    Fastboard App (app) → Handles page navigation and modifications.

Implementation Notes

    Preview Generation: Reuses the getSaveAnnotationImages() method for simplicity.

    Page Deletion: Ensures correct indexing before removal.

    Navigation: Uses app.jumpPage() for direct page access.
