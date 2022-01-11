# High Steel Structures^LLC^ DXF File Specification
##### Version: 2.1 (1/11/2022)

### Prelude

This specification outlines the format for which High Steel Structures^LLC^ will expect to receive .dxf part files.

### Part Names

Part files should be named using the [job]_[mark]-[revision] format. For example: part `x1a` for job `1200018A` with revision `0` would be named `1200018A_x1a-R0`

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

### Holes

- RA holes will match the subsize diameter
- All other holes will match the final diameter
- Countersunk or DTE holes do not need to be in the DXF file

### Bent Plates

Bent plates with holes on both sides of the bend line do not require DXF files (HSS will create models as they require special modeling). All other bent plates should have DXF files supplied. Bent plate lengths are to be calculated along the radius at the mid-thickness of the plate. **DXF files for bent plates must be in the flattened form.**

### Beveled, Tapered and Chamfered plates

- Beveled plates, or plates that have a thickness taper, should have their thickness noted as the thickest point on the plate.
- Edge bevels/chamfers do not need to be in the DXF file.

### Direction-of-rolling constraint

For parts where there is a requirement of direction of mill rolling, an arrow should be placed on the DETAIL layer in the center of the part.
This can be a two line arrow or three line arrow. Only lines are needed. Dimensions and points are for reference.
![Alt text][arrow2] ![Alt text][arrow3]

### Example

![Alt text][example]

[comment]: <> (links)
[arrow2]: https://github.com/paddymills/hss-markdowns/raw/master/img/dxf_arrow2_small.png "two-line arrow"
[arrow3]: https://github.com/paddymills/hss-markdowns/raw/master/img/dxf_arrow3_small.png "three-line arrow"
[example]: https://github.com/paddymills/hss-markdowns/raw/master/img/dxf_example.png "example"