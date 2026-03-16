# Converting CAD files for GitHub viewing

GitHub’s web UI can render `.stl` files (and some other mesh formats) directly in the browser, but it cannot render STEP/BREP files (`.step`, `.stp`, `.f3d`). To get the STEP model in a viewable form, you need to export a mesh format (such as STL) using CAD software.

## Recommended workflow (Fusion 360)
1. Open the `.step` or Fusion 360 design in Fusion 360.
2. In the **Model** workspace, select the body or component you want to export.
3. Right-click and choose **Save as Mesh**.
4. Choose **STL** as the output format, then set the refinement/quality to **High**.
5. Save the resulting `.stl` file into `cad_files/exports/` alongside the STEP file.

## Alternative: FreeCAD CLI conversion
If you prefer an open-source tool, FreeCAD can convert STEP → STL from the command line.

### Install (Windows)
1. Download and install FreeCAD: https://www.freecad.org/downloads.php

### Convert with FreeCAD command line
```powershell
& "C:\Program Files\FreeCAD 0.21\bin\FreeCADCmd.exe" -c "import Mesh, Part; doc=Part.open('cad_files/exports/STEP Version Hydra_v1.step'); part=doc.getObjectsByLabel('Part')[0]; Mesh.export(part, 'cad_files/exports/STEP Version Hydra_v1.stl')"
```

> Tip: Adjust the path to `FreeCADCmd.exe` and the object name if needed.

## Improving PNG quality (renders)
The best way to improve PNG quality is to re-export/render at a higher resolution from your CAD software:
- In Fusion 360, use the **Render** workspace and increase output resolution (e.g., 4K or larger).
- Export the result as PNG with a higher pixel count.

### Quick (non-CAD) option: upscale with ImageMagick
If you just want to increase pixel dimensions (without improving detail), you can use ImageMagick (if installed):
```powershell
magick images/renders/your_image.png -resize 400% images/renders/your_image@4x.png
```

> Note: Upscaling does not add new detail; it only increases pixel count.
