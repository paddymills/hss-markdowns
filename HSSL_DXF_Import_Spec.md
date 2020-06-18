# Preamble

The following spec outlines the format for which High Steel Structures LLC will expect to receive .dxf part files in.

---

# Layers

Entities are to be grouped into the following layers:

| Layer Name | Description | Examples |
| ---: | --- | --- |
| **CUT** | Profile Entities | part perimeter, holes, cut-outs |
| **MARK** | Marked entities | work points, set lines |
| **DETAIL** | Reference entities | direction-of-roll constraints |
| **PARDATA** | Part attributes | grade, thickness, drawing |

---

# Key: Value pairs
Text attributes on the PARTDATA layer are to be organized into KEY: VALUE pairs. For example, material grade of A709-50 would result in the string `MATERIAL: A709-50`. Part attributes can be inside or outside the contour of the part, unless part file has multiple parts in it.

| KEY | Value Description | Format | Example(s) |
| ---: | --- | --- | --- |
| **PARTNAME** | Part name | [job]\_[mark] | 1200018A_x1a |
| **MATERIAL** | Material grade | [spec]-[grade][test?] | A709-50T2 or A709-50 |
| **THICKNESS** | Part Thickness (plate items) | integer or decimal | 1.375 |
| **DRAWING** | Drawing number | alphanumeric | 1 or X1 |

---

# Direction-of-rolling constraing

For parts where there is a requirement of direction of mill rolling, an arrow should be placed on the DETAIL layer in the center of the part.
This can be a two line arrow or three line arrow. Only lines are needed. Dimensions and points are for reference.
![two-line arrow](https://github.com/paddymills/hss-markdowns/raw/master/img/dxf_arrow2_small.png) ![three-line arrow](https://github.com/paddymills/hss-markdowns/raw/master/img/dxf_arrow3_small.png)

---

# Example Layout
![example](https://github.com/paddymills/hss-markdowns/raw/master/img/dxf_example.png)