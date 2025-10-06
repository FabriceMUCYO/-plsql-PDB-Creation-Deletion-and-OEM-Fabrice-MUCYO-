# Assignment 2: Database Creation, Deletion & OEM

---

### Name: MUCYO Fabrice
### ID: 27823
### Group: C

---

# Introduction:
This practical focused on working with Oracle which includes the creation, opening, saving and deletion 
of Pluggable Databases (PDBs) and accessing them using Oracle Enterprise Manager (OEM)

# Task 1: Create a New Pluggable Database
The following are commands i used to get connected to my oracle as SYSDBA and Creat a new pluggable database named
"Mu_pdb_27823"  and save it as it was asked.
```sql
sqlplus / as sysdba

CREATE PLUGGABLE DATABASE Mu_pdb_27823 
ADMIN USER Mucyo_plsqlauca_27823 IDENTIFIED BY "16083"
FILE_NAME_CONVERT = (
'C:\app\HP\product\21c\oradata\XE\pdbseed',
'C:\app\HP\product\21c\oradata\XE\Mu_pdb_27823'
);

ALTER PLUGGABLE DATABASE Mu_pdb_27823 OPEN;
SHOW PDBS;

ALTER PLUGGABLE DATABASE Mu_pdb_27823 SAVE STATE;
```

### And here is the screenshots that shows it

<img src="https://github.com/FabriceMUCYO/-plsql-PDB-Creation-Deletion-and-OEM-Fabrice-MUCYO-/blob/main/Pdb%20screenshot/Login%20to%20sql.png" width=700>
<img src="https://github.com/FabriceMUCYO/-plsql-PDB-Creation-Deletion-and-OEM-Fabrice-MUCYO-/blob/main/Pdb%20screenshot/Create%20Pdb.png" width=700>
<img src="https://github.com/FabriceMUCYO/-plsql-PDB-Creation-Deletion-and-OEM-Fabrice-MUCYO-/blob/main/Pdb%20screenshot/Open%20pdb.png" width=700>

---

# Task 2: Create and Delete a PDB
Before creating another pdb i switched to root container in order to avoid error because oracle 
only allows you to create or drop PDBs from the CDB root container not from inside another one as it follows here:
```sql
ALTER SESSION SET CONTAINER=CDB$ROOT;

CREATE PLUGGABLE DATABASE Mu_to_delete_pdb_27823 
ADMIN USER Mucyo_plsqlauca_27823 IDENTIFIED BY "16083"
FILE_NAME_CONVERT = (
'C:\app\HP\product\21c\oradata\XE\pdbseed',
'C:\app\HP\product\21c\oradata\XE\Mu_to_delete_pdb_27823'
);

ALTER PLUGGABLE DATABASE Mu_to_delete_pdb_27823 OPEN;
SHOW PDBS;

ALTER PLUGGABLE DATABASE Mu_to_delete_pdb_27823 CLOSE IMMEDIATE;
DROP PLUGGABLE DATABASE Mu_to_delete_pdb_27823 INCLUDING DATAFILES;
```

### here is the screenshot





