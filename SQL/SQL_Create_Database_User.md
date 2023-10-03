# SQL_Create_Database_User

## Create SQL Login for the user:
``` sql
-- ==========================================
-- Create Login For User template
-- ==========================================

CREATE LOGIN [user_name]
    WITH PASSWORD = 'DamnThisIsAGoodPassword!!;)';
```

## Create the user in the database:
``` sql
-- ===================================
-- Create User in datatabase you want to give access to
-- ===================================
USE <database_name, sysname, AdventureWorks>
GO

-- Add the user to the database using their login name and the user name
CREATE USER [user_name]
	FOR LOGIN [user_name]
	WITH DEFAULT_SCHEMA = [dbo]
GO

```

## Grant user rights or access:
``` sql
-- ===================================
-- select thedatatabase you want to give access to
-- ===================================
USE <database_name, sysname, AdventureWorks>
GO

-- Add user to db_datareader role
ALTER ROLE [db_datareader]
ADD MEMBER [user_name]
GO

-- Grant specific access rights to use based on Schema
GRANT 
	DELETE, 
	EXECUTE, 
	INSERT, 
	SELECT, 
	UPDATE, 
	VIEW DEFINITION 
ON SCHEMA::[<default_schema, sysname, Production>] 
	TO [user_name]
GO
```
