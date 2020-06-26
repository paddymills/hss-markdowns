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
 
## Todo
- [ ] Consolidate layer groups?
- 


---
### Ideas

- Autoprocess recognizes extra material for milling?
- Hole process mapping (punch process?)
- PMI?