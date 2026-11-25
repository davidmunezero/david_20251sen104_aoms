# DATA DICTIONARY FOR AOMS DATABASE

## 1. Table: STAFF

**Description:**  
Stores information about staff at the airport.

| Column Name | Description | Constraint(s) |
|---|---|---|
| Staff_ID | Unique identifier for each staff member. | PK |
| Name | Name of staff member. | Required |
| Department | Department staff member works in. | Optional |
| Terminal | Terminal staff member is assigned to. | Optional |
| Gate | Gate staff member is assigned to. | Optional |
| Works_Overtime | Boolean flag confirming whether staff member can work overtime. | Required |
| Language | Primary language spoken by staff member. | Required |
| Hire_Date | Date staff member was hired by the management team. | Optional |
| Role | Specialized role of staff member at the airport. | Required |
| Shift_Start | Time staff member's shift starts. | Optional |
| Shift_End | Time staff member's shift ends. | Optional |
| Supervisor_ID | Number corresponding to the ID of a staff member who supervises the current staff member. | Optional, FK |

## 2. Table: ATC

**Description:**  
Stores additional details about specialized staff who are air traffic controllers.

| Column Name | Description | Constraint(s) |
|---|---|---|
| Control_ID | Unique identifier for ATC specialized staff, corresponding to the staff member's identity. | PK, FK |
| Assigned_Space | Space the air traffic controller is assigned to work in. | Required |

## 3. Table: MANAGER

**Description:**  
Stores additional information and identification for managers who are staff members.

| Column Name | Description | Constraint(s) |
|---|---|---|
| Manager_ID | Unique identifier for a manager who is a staff member. | PK, FK |

## 4. Table: TECHNICIAN

**Description:**  
Stores additional information and identification for technicians who are specialized staff members.

| Column Name | Description | Constraint(s) |
|---|---|---|
| Technician_ID | Unique identifier for a technician who is a specialized staff member. | PK, FK |

## 5. Table: RUNWAY

**Description:**  
Stores information about airport runways.

| Column Name | Description | Constraint(s) |
|---|---|---|
| Runway_ID | Unique identifier and sequential surrogate key for a runway. | PK |
| Identifier | Meaningful runway designation that is unique within the airport context. | Required, Unique |
| Length | Physical runway length. | Required |
| Width | Physical runway width. | Required |
| Surface_Type | Type of runway surface. | Required |
| Edge_Light | Type of lights on the runway edge. | Optional |
| Shape_Length | Length of the runway using geometric measurements (GIS geometry). | Optional |

## 6. Table: MAINTENANCE

**Description:**  
Stores maintenance records and activities performed on airport equipment.

| Column Name | Description | Constraint(s) |
|---|---|---|
| Maintenance_ID | Unique identifier for a maintenance record. | PK |
| Maintenance_Type | Type of maintenance carried out. | Required |
| Start_Time | Start time of maintenance. | Required |
| End_Time | End time of maintenance. | Required |
| Priority | Priority level of maintenance performed. | Required |
| Fault_Type | Type of fault the equipment had before maintenance. | Required |
| Completed | Boolean flag indicating whether maintenance fully repaired the fault. | Required |
| Equipment_ID | References the equipment being maintained. | Required, FK |
| Technician_ID | Identifies the staff member performing maintenance. | Required, FK |
| Approved_By | References the manager who approved the technician to perform maintenance. | Required, FK |

## 7. Table: EQUIPMENT

**Description:**  
Stores information about aircraft and ground-support equipment based at the airport.

| Column Name | Description | Constraint(s) |
|---|---|---|
| Equipment_ID | Unique identifier for equipment. | PK |
| Name | Name of equipment. | Required |
| Category | Category of equipment, such as aircraft or ground-support equipment. | Required |
| Location | Location of equipment within the airport. | Required |
| Status | Service condition of equipment. | Required |
| Last_Inspection | Date of the last inspection. | Optional |
| Next_Inspection | Date of the next inspection. | Optional |
| Details | Additional equipment details. | Optional |

## 8. Table: INSPECTION

**Description:**  
Stores inspection records for aircraft and ground-support equipment.

| Column Name | Description | Constraint(s) |
|---|---|---|
| Inspector_ID | Identifier of the inspector who conducted the inspection. | Required |
| Inspection_Date | Date of inspection. | Required |
| Equipment_ID | References the equipment being inspected. | Required, FK |
| Inspector_Org | Identifier of the organization the inspector works for. | Optional |
| Result | Inspection result as recorded by the inspector. | Required |

---

# RELATIONSHIP DICTIONARY

| Parent Table | Child Table | Relationship | Foreign Key |
|---|---|---|---|
| Staff | ATC | One-to-One (1:1) | ATC.Controller_ID |
| Staff | Manager | One-to-One (1:1) | Manager.Manager_ID |
| Staff | Technician | One-to-One (1:1) | Technician.Technician_ID |
| Equipment | Maintenance | One-to-Many (1:M) | Maintenance.Equipment_ID |
| Equipment | Inspection | One-to-Many (1:M) | Inspection.Equipment_ID |
| Manager | Maintenance | One-to-Many (1:M) | Maintenance.Approved_By |
| Technician | Maintenance | One-to-Many (1:M) | Maintenance.Technician_ID |
| Staff (Supervisor) | Staff (Supervisee) | One-to-Many (1:M) | Staff.Supervisor_ID |

## Relationship Summary

- Total relationships: **8**
- One-to-One relationships: **3**
- One-to-Many relationships: **5**
