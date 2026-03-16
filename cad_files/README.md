<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" crossorigin="anonymous" referrerpolicy="no-referrer" />

# <i class="fas fa-cube" style="color:#2b6cb0"></i> CAD Files

This folder is intended for Fusion 360 design artifacts and exported CAD files that support the 2025 FTC robotics season.

## <i class="fas fa-layer-group" style="color:#2b6cb0"></i> Current contents

- `Hydra v1.stl` – STL export of the robot assembly for GitHub web rendering.

## <i class="fas fa-tools" style="color:#2b6cb0"></i> Best practices

- Include a brief `README.md` or `meta.json` alongside key models describing the part/assembly purpose.
- Preserve revision history by using clear filenames (e.g., `drivebase_v1.f3d`, `intake_v2.step`).
- Keep `fusion/` files in sync with `exports/` exports used for manufacturing or simulation.
- Use `assemblies/` to capture build intent (exploded views, drawings) rather than dumping all components in one folder.
- Favor descriptive, consistent naming and include the year/season in major revisions (e.g., `2025_drivebase_v2.f3d`).
