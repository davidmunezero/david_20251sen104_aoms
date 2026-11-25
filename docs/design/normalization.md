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
How the raw fields in the dataset map to a target table and column. 

### Staff
| Raw Field | Target Column | Special Note | Type Conversion |
| -------- | -------- | -------- | -------- |
| Col 0 | staff_id | Inferred column name | text to `INT` |
| Col 1 | name | Inferred column name | No conversion |
| Col 2 | department | Inferred column name | No conversion |
| Col 3 | role | Inferred column name | No conversion |
| Col 4 | hire_date | Inferred column name | text to `DATE` |
| Col 5 | shift_start | Inferred column name | text to `TIMESTAMP` |
| Col 6 | shift_end | Inferred column name | text to `TIMESTAMP` |
| Col 7 | terminal  | Inferred column name | No conversion |
| Col 8 | gate  | Inferred column name | No conversion |
| Col 9 | supervisor_id | Inferred column name | text to `INT` |
| Col 10 | shift_hours  | Inferred column name | text to `NUMBER` |
| Col 11 | works_overtime  | Inferred column name | text to `BOOLEAN` |
| Col 12 | N/A | Dropped because it was empty | N/A |
| Col 13 | N/A | Did not make sense to keep | N/A |
| Col 14 | language | Inferred column name | No conversion |

### Equipment
| Raw Field | Target Column | Special Note | Type Conversion |
| -------- | -------- | -------- | -------- |
| asset_id | equipment_id | Direct mapping | text to  `INT` |
| equipment | name | Direct mapping | No conversion |
| category | category | Direct mapping | No conversion |
| location | location | Direct mapping | No conversion |
| status | status | Direct mapping | No conversion |
| last_inspection | last_inspection | Direct mapping (derived attribute) | 
| details | details | Direct mapping | No conversion |
| notes | N/A | Dropped due to redundancy (maintenance logs mention faults) | N/A |
| technician | N/A | Dropped because it does not relate to equipment details | N/A |

### Runway
| Raw Field | Target Column | Special Note | Type Conversion |
| -------- | -------- | -------- | -------- |
| objectid | runway_id | Direct mapping | text to `INT` |
| runway_ide | identifier | Direct mapping | No conversion |
| runway_len | length | Direct mapping | text to `NUMBER` |
| runway_wid | width | Direct mapping | text to `NUMBER` |
| airport_id | N/A | Dropped because no airport table exists | N/A |
| surface_ty | surface_type | Direct mapping | No conversion |
| edge_light | edge_light | Direct mapping | No conversion |
| shape__length | shape_length | Direct mapping | text to `NUMBER` |

### Maintenance Log
| Raw Field | Target Column | Special Note | Type Conversion |
| -------- | -------- | -------- | -------- |
| Col 0 | maintenance_id | Inferred column name | text to `INT` | 
| Col 1 | equipment_id | Inferred column name | text to `INT` | 
| Col 2 | N/A | Dropped due to ambiguity | N/A | 
| Col 3 | maintenance_type | Inferred column name | No conversion | 
| Col 4 | technician_id | Inferred column name | text to `INT` | 
| Col 5 | start_time | Inferred column name | text to `TIMESTAMP` | 
| Col 6 | end_time | Inferred column name | text to `TIMESTAMP` | 
| Col 7 | priority | Inferred column name | text to `INT` | 
| Col 8 | N/A | Dropped due to ambiguity | N/A | 
| Col 9 | fault_type | Inferred column name | No conversion | 
| Col 10 | N/A | Dropped due to ambiguity | N/A | 
| Col 11 | N/A | Dropped due to ambiguity | N/A | 
| Col 12 | approved_by | Inferred column name | text to `INT` | 
| Col 12 | N/A | Dropped due to ambiguity | N/A | 
| Col 13 | is_completed | Inferred column name | text to `BOOLEAN` | 
| Col 14 | N/A | Dropped because all field values are empty | N/A | 

### Inspection
| Raw Field | Target Column | Special Note | Type Conversion |
| -------- | -------- | -------- | -------- |
| OperatorControlNumber | inspector_ide | Direct mapping | No conversion |  
| DifficultyDate | inspection_date | Direct mapping | text to `DATE` |
| AircraftSerialNumber | equipment_id | Direct mapping | text to `INT` |
| NatureOfConditionA | result | Direct mapping | No conversion |

**Note:** The rest of the raw fields in inspections.csv were dropped due to a mismatch with the intended inspection schema.
