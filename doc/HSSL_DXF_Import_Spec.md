# High Steel Structures<sup>LLC</sup> DXF File Specification
<!-- uncomment line below if not using markdown-pdf vscode extension (and fix the date!) -->
<!-- ##### Version: 2.1 (1/11/2022) -->

### Prelude

This specification outlines the format for which High Steel Structures<sup>LLC</sup> will expect to receive .dxf part files.

### Part Names

Part files should be named using the [job]_[mark]-[revision] format. For example: part `x1a` for job `1200018A` with revision `0` would be named `1200018A_x1a-R0`

### Part Orientation

The orientation of all parts/components in the dxf file should match the orientation of the part/component as shown on the shop drawing.

### Layers

Entities are to be grouped into the following layers:

| Layer Name | Description | Examples |
| ---: | --- | --- |
| **CUT** | Profile Entities | profile, holes, interior contours |
| **MARK** | Marked entities | work points, set lines |
| **DETAIL** | Reference entities | direction-of-roll constraints |
| **PARTDATA** | Part attributes | grade, thickness, drawing |

### Key: Value pairs
Text attributes on the PARTDATA layer are to be organized into KEY: VALUE pairs. For example, material grade of A709-50 would result in the string `MATERIAL: A709-50`. Part attributes can be inside or outside the contour of the part.

| KEY | Value Description | Format | Example(s) |
| ---: | --- | --- | --- |
| **PARTNAME** | Part name | [job]\_[mark] | 1200018A_x1a |
| **MATERIAL** | Material grade | [spec]-[grade][test?] | A709-50T2 |
| **THICKNESS** | Part Thickness (plate items) | integer or decimal | 1.375 |
| **DRAWING** | Drawing number | alphanumeric | 1 or X1 |
| **REVISION** | Revision number | alphanumeric | 0 |

<div style="page-break-after: always;"></div>

### Holes

- RA holes will match the subsize diameter
- All other holes will match the final diameter
- Countersunk or DTE holes do not need to be in the DXF file

### Bent Plates

DXF files are not required for bent plates with a bend 45° or higher and holes on both sides of the bend.
All other bent plates should have DXF files supplied. Bent plate lengths are to be calculated along the radius at the mid-thickness of the plate. **DXF files for bent plates must be in the flattened form.**

### Beveled, Tapered and Chamfered plates

- Beveled plates, or plates that have a thickness taper, should have their thickness noted as the thickest point on the plate.
- Edge bevels/chamfers do not need to be in the DXF file.

<div style="page-break-after: always;"></div>

### Direction-of-rolling constraint

For parts where there is a requirement of direction of mill rolling, an arrow should be placed on the DETAIL layer in the center of the part.
This can be a two line arrow or three line arrow. Only lines are needed. Dimensions and points are for reference.
![Alt text][arrow2] ![Alt text][arrow3]

<div style="page-break-after: always;"></div>

### Example

![Alt text][example]

[comment]: <> (links)
[arrow2]: ./img/dxf_arrow2_small.png "two-line arrow"
[arrow3]: ./img/dxf_arrow3_small.png "three-line arrow"
[example]: ./img/dxf_example.png "example"