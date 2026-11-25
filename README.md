# Personal PDF Suite — Android Edition (Native Kotlin + Jetpack Compose)

A clean, touch-first native Android PDF application built with **Kotlin**, **Jetpack Compose**, and **Material 3**, compiled via **GitHub Actions** and debugged directly over **USB ADB (`adb install` + `adb logcat`)**.

## Platform Feature Scope (Optimized for Mobile Stability)
On Android, fragile desktop-style MS-Word multi-page paragraph reflow is intentionally omitted in favor of rock-solid mobile features:
- **View & Read**: High-DPI native `PdfRenderer` page viewing, pinch-to-zoom, continuous scroll, dark/light themes, document outline & search.
- **Annotate & Markup**: Touch/stylus Freehand Pen, Highlighter, Sticky Notes, Geometric Shapes, Text Markups, Eraser, and Floating Text Boxes.
- **Fill & Sign**: Draw, Type, or Upload Signature (with adaptive paper background removal), Stamps, and Form Flattening.
- **Organize & Protect**: Reorder, Rotate, Delete, Split by range, Merge, Watermarks, Bates numbering, Whiteout, Redaction, AES-256 encryption.
- **Native Storage**: Android Storage Access Framework (`OpenDocument` / `CreateDocument`) and native Android Share/Print.

## Cloud Build & USB ADB Debugging Workflow
1. Push changes to GitHub (`main`).
2. GitHub Actions (`.github/workflows/build-android.yml`) compiles the signed APK in the cloud (0 GB Android SDK / Emulator required locally).
3. Download the `.apk` artifact and test directly on a connected phone:
   ```cmd
   adb install -r app-debug.apk
   adb logcat -s PersonalPDFSuite:V AndroidRuntime:E
   ```
