# NX DXF Export Specification

# Layer Mapping

| Object Class | Object Type | Layer Assignment | Category Name |
| --- | --- | --- | --- |
| **Model Geometry** | Solid Geometry | 1-20 | SOLIDS |
|  | Inter-part Modeling | 15-20 | LINKED_OBJECTS |
|  | Sketch Geometry | 21-40 | SKETCHES |
|  | Curve Geometry | 41-60 | CURVES |
|  | Reference Geometry | 61-80 | DATUMS |
|  | Sheet Bodies | 81-100 | SHEETS |
| **Drafting Objects** | Drawing Borders | 101-110 | FORMATS |
| **Engineering Disciplines** | Mechanism Tools | 121-130 | MECH |
|  | Finite Element Meshes and Engr. Tools | 121-130 | CAE |
|  | Manufacturing | 121-130 | MFG |
|  | Quality Tools | 121-130 | QA |

# Import Layer Mapping
- Specific layers will import, others will be excluded from export
- Annotations need to be PMI mapped? (dimensions do)

| Object Type | Object | Exports | SigmaNest Process | Layer(s) |
| --- | --- | --- | --- | --- |
| **Solids** | Profile | Yes | Kerf Cut | 1-5 |
|  | Internal Contours | Yes | Kerf Cut | 1-5 |
|  | Holes | Yes | Kerf Cut | 6-10* |
| **Sketches** | Work Points | Yes | Marking | 21-25 |
|  | Zinc lines | Yes | Marking | 21-25 |
|  | Direction of roll | Yes | No Cut | 26-30 |
|  | Weld splices | Yes | No Cut | 26-30 |
| **Annotations** | Part attributes | Yes | Detail | PMI |
|  | Dimensions | Yes | Detail | PMI |
| **Drawings** | DXF Export | Yes | Kerf Cut | 101 |
|  | All other | No | - | 102-110 |

*if mapping holes as drill/punch, will need to map `{drill: 6..9, punch: 10}` (requires punch logic `!T && thk <= punch_thk`)

## Todo
- [ ] Consolidate layer groups?
- [ ] Wildcard and range layers enhancement in SigmaNest
- [ ] PMI evaluation


---
### Ideas

- Autoprocess recognizes extra material for milling? (geometry recognition or part attribute)
- Hole process mapping (punch process?)
- PMI?