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
The following are commands i used to Login to my oracle and Creation of the pluggable database named
"Mu_pdb_27823" as it was asked.
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
And here is the screenshots that shows it
<img src="
