# Odoo-Database-Restoration Guide

This guide provides step-by-step instructions to restore a PostgreSQL database from a dump file.

## Prerequisites
- Ensure PostgreSQL is installed on your system.
- Have a valid database dump file (`dump.sql`).
- Have access to the PostgreSQL user with the required permissions.

## Steps to Restore the Database

### 1. Open Terminal
Open the terminal on your system and run the following command to access PostgreSQL:

```
sudo -u postgres psql -p 5432
```

You will be prompted to enter your password. Provide the correct password to proceed.

### 2. Create a New Database
Once inside PostgreSQL, create a new database to restore the data into:

```
CREATE DATABASE db_name;
```

Exit PostgreSQL by typing:

```
\q
```

### 3. Navigate to the Database Dump Location
Go to the folder where your database dump (`dump.sql`) is located. Right-click inside the folder and select **Open Terminal**.

### 4. Restore the Database
Run the following command to restore the database from the dump file:

```
psql -f dump.sql -d db_name
```

## Verification
After restoring, you can verify the database restoration by connecting to PostgreSQL and checking the tables:

```
sudo -u postgres psql -d db_name
```

Then, list tables with:

```
\dt
```

## Notes
- Replace `db_name` with your actual database name.
- Ensure `dump.sql` is in the correct directory before running the restore command.
- If you encounter permission issues, run the commands with the appropriate user privileges.

## Your data is your treasure—protect it, back it up, and restore it wisely. Happy Coding 🧑‍💻

