# emma-oracle-pdb-lab
# Oracle Database Lab — PDB Creation, Deletion, and OEM Configuration

**Student Name:** IZA KURADUSENGE Emma Lise 
**Student ID:** *28246*  
**Course:** Database Development with PL/SQL  
**Date:** *October 6, 2025*  

---

## Overview
During this lab, I completed work with Oracle’s Multitenant Architecture, which enables multiple pluggable databases (PDBs) to exist within a single container database (CDB).
The goal was to create, manage, and delete PDBs in addition to setting up and accessing Oracle Enterprise Manager (OEM) to monitor the PDBs.

Through this hands-on experience, I better learned how PDBs work, how to manage database containers using SQL commands, and how to use OEM for administration and monitoring.
## Task 1 — Creating a New Pluggable Database (PDB)

### Objective
To create a new PDB using the required naming convention and assign an admin user who will store all classwork.
![screenshot](https://github.com/Emmalise1/emma-oracle-pdb-lab/blob/main/Create%20a%20pluggable%20db.PNG?raw=true)

## Error Encountered

When trying to open the new pluggable database:

```sql
ALTER PLUGGABLE DATABASE li_pdb_28246 OPEN;
ORA-01031: insufficient privileges
```
## Cause of the Error

The error occurred because the user executing the command lacked **SYSDBA privileges**, which are required for administrative operations such as opening or closing pluggable databases.  
Even though the user had the **DBA role**, it was not sufficient to execute system-level commands.

---

## Solution Implemented

1. Reconnected to the database as a SYSDBA user:
   ```sql
   CONNECT sys/your_sys_password AS SYSDBA;
   ```
Re-ran the open command:
```sql
 ALTER PLUGGABLE DATABASE li_pdb_28246 OPEN;
```

The pluggable database opened successfully.

## Verification

To confirm that the database was open and active:
 ```sql
SELECT NAME, OPEN_MODE FROM V$PDBS;
```
## Task 2 — Creating and Deleting Another PDB

### Objective
To practice creating another PDB and then deleting it correctly to confirm understanding of PDB lifecycle management.

---
![screenshot](https://github.com/Emmalise1/emma-oracle-pdb-lab/blob/main/Task2.PNG?raw=true)

## Error Encountered

No actual error occurred during this task.

## Task 3 — Oracle Enterprise Manager (OEM) Configuration

### Objective
To configure and verify **Oracle Enterprise Manager (OEM)**, ensuring it displays the created PDBs and user credentials clearly.

---

### Steps Performed

1. **Accessed OEM using the browser:**
   ```bash
   https://localhost:5500/em
    ```
2. **Logged in with: **

Username: lise_plsqlauca_28246
Password: lise1
Container Name: li_pdb_28246

![screenshot](


