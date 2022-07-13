# CAD to CAM workflow -- Onshape --> Fusion360 --> [machineX]

## Design Part in OnShape

- export from Onshape as SVG or DXF for laser cut, waterjet
- export from Onshape as STEP for CNC router, milling, 3D printer
- save export to USB drive or file on [Gizmo | your] computer

## Use Fusion360 to Generate NumericControl (NC) Code For Your [machineX]

- [ ] open Fusion360, login, create [or open existing] Project, and [create | use existing] folder for this part
- [ ] in Design mode, Upload your file, save Project
- [ ] in Manufacturing mode, make new Setup
- [ ] configure Setup panel tabs:  machine, stock, post proc.
  - select model / part if >1 listed; set WCS, stock size, axes
- [ ] make 2D/3D tool paths: typically facing, rough clearing, finishing, cut out edge
- make facing path, specify Path tabs
  - tool
  - feed rate
  - geometry
  - height
  - pass
  - link (turn on Action/Automatic InProcess Stock)
  - view path --> simulate, set options, play controls to view / correct
- make rough cut tool path, set option tabs, simulate, view / correct
- make finishing tool path, set option tabs, simulate, view / correct
- make tool path to cut out part border, contour or other - simulate, view, fix error

- [ ] For each tool path, make distinct output file for manufacturing machineX:
  - Setup/ create NC program, name, specify machine, post type, select operations using same tool, simulate
    - if error --> edit operation
    - if OK --> post process, view g-code file, save it to USB drive
- repeat for each operation using same tool

- [ ] Print Setup Sheet
