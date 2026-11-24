# Database Normalization

## Entities
1. Staff
2. ATC
3. Equipment
4. Runway
5. Maintenance Log
6. Inspection

## Normalization Process
UNF -> 1NF -> 2NF -> 3NF 

## Field Mapping
How every raw field maps to a target table and column. 

### Staff
| Raw Field | Target Column | Special Note |
| -------- | -------- | -------- |
| Col 0 | staff_id | Inferred column name |
| Col 1 | name | Inferred column name |
| Col 2 | department | Inferred column name |
| Col 3 | role | Inferred column name |
| Col 4 | hire_date | Inferred column name |
| Col 5 | shift_start | Inferred column name |
| Col 6 | shift_end | Inferred column name |
| Col 7 | terminal  | Inferred column name |
| Col 8 | gate  | Inferred column name |
| Col 9 | supervisor_id | Inferred column name |
| Col 10 | shift_hours  | Inferred column name |
| Col 11 | works_overtime  | Inferred column name |
| Col 12 | N/A | Dropped because it was empty |
| Col 13 | N/A | Did not make sense to keep |
| Col 14 | language | Inferred column name |

### Equipment
| Raw Field | Target Column | Special Note |
| -------- | -------- | -------- |
| asset_id | equipment_id | Direct mapping | 
| equipment | name | Direct mapping | 
| category | category | Direct mapping | 
| location | location | Direct mapping | 
| status | status | Direct mapping | 
| last_inspection | last_inspection | Direct mapping (derived attribute) | 
| details | details | Direct mapping | 
| notes | N/A | Dropped due to redundancy (maintenance logs mention faults) | 
| technician | N/A | Dropped because it does not relate to equipment details |

### Runway
| Raw Field | Target Column | Special Note |
| -------- | -------- | -------- |
| objectid | runway_id | Direct mapping | 
| runway_ide | identifier | Direct mapping |
| runway_len | length | Direct mapping |
| runway_wid | width | Direct mapping |
| airport_id | N/A | Dropped as it did not  |
| surface_ty | surface_type | Direct mapping |
| edge_light | edge_light | Direct mapping |
| shape__length | shape_length | Direct mapping |

### Maintenance Log
Table 

### Inspection
Table
