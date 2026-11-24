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
| Col 13 | Dropped  | Did not make sense to keep |
| Col 14 | language | Inferred column name |

### Equipment
Table

### Runway
Table

### Maintenance Log
Table 

### Inspection
Table
