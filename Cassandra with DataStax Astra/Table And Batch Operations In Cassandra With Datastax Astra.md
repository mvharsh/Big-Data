# Objectives:
- To understand the basic operations related to tables in Cassandra.
- To practice batch operations for efficient data manipulation.
- To gain proficiency in querying and updating data in Cassandra tables.

# Experiment:

### 1. Display the set of key spaces
    select * from system.schema_keyspaces;
    (OR)
    describe keyspaces;

![image](https://github.com/mvharsh/Big-Data/assets/111365320/0c52c563-693d-4bc7-a7af-ade2b7f0b6c0)


### 2. Connect with 'default_keyspace' key space
    use default_keyspace;

![image](https://github.com/mvharsh/Big-Data/assets/111365320/c31435ce-e18f-426e-a763-5955c2a7e35b)


### 3. Create a table named users with columns for user_id, fname, and lname.
    CREATE TABLE users (user_id int PRIMARY KEY,fname text,lname text);

![image](https://github.com/mvharsh/Big-Data/assets/111365320/d41c7de0-8f3c-4014-9625-902609233498)


### 4. Insert data into the users table one by one
    INSERT INTO users (user_id, fname, lname) VALUES (1745, 'John', 'Smith');
    INSERT INTO users (user_id, fname, lname) VALUES (1746, 'Jane', 'Doe');
    INSERT INTO users (user_id, fname, lname) VALUES (1747, 'Alice', 'Johnson');
    INSERT INTO users (user_id, fname, lname) VALUES (1748, 'Michael', 'Brown');
    INSERT INTO users (user_id, fname, lname) VALUES (1749, 'Emily', 'Davis');
    INSERT INTO users (user_id, fname, lname) VALUES (1750, 'William', 'Wilson');
    INSERT INTO users (user_id, fname, lname) VALUES (1751, 'Sophia', 'Martinez');
    INSERT INTO users (user_id, fname, lname) VALUES (1752, 'James', 'Taylor');

![image](https://github.com/mvharsh/Big-Data/assets/111365320/36b19df4-b1cf-4548-9b8a-09e2e5cf2911)


### 5. Insert multiple rows into the users table in Cassandra using a batch operation.
    BEGIN BATCH
    INSERT INTO users (user_id, fname, lname) VALUES (1753, 'Emma', 'Johnson');
    INSERT INTO users (user_id, fname, lname) VALUES (1754, 'Michael', 'Williams');
    APPLY BATCH;

![image](https://github.com/mvharsh/Big-Data/assets/111365320/aad91cbb-70f8-4f0e-b4ec-a884c0e196c1)


### 6. Display all data from the users table.
    SELECT * FROM users;

![image](https://github.com/mvharsh/Big-Data/assets/111365320/44f1b9ca-e40b-4e0c-81f6-de87917bccd0)


### 7. Display only the user_id and fname columns from the users table
    SELECT user_id, fname FROM users;

![image](https://github.com/mvharsh/Big-Data/assets/111365320/ad6e6578-e449-461e-a84d-e5cf4a628636)


### 8. Display data from the users table where lname is 'Smith'.
    SELECT * FROM users WHERE lname = 'Smith';



### 9.Display data from the users table sorted by lname in descending order.

    CREATE TABLE user (
      user_id int,
      fname text,
      lname text,
      PRIMARY KEY (lname, fname, user_id)
    ) WITH CLUSTERING ORDER BY (fname ASC, user_id ASC);
    
    SELECT * FROM user WHERE lname = ‘Johnson’ ORDER BY fname ASC, user_id ASC;
    
    or
    
    SELECT * FROM users ORDER BY lname DESC;




### 10.Display the first two rows from the users table.
    SELECT * FROM users LIMIT 2;



### 11.Count the number of users with the same lname.
    SELECT lname, COUNT(*) as count FROM user GROUP BY lname;




### 12. Display unique last names from the users table.
    SELECT DISTINCT lname FROM user;



### 13. Update the telephone field for the user with user_id = 1745 to '21212121'.
    UPDATE users SET telephone = '21212121' WHERE user_id = 1745;



### 14.Update both fname and lname of the user with user_id 1746.
    UPDATE users SET fname = 'Jane', lname = 'Smith' WHERE user_id = 1746;


### 15. Increment the login_attempts counter for the user with user_id 1747 by 1.
    UPDATE users SET login_attempts = login_attempts + 1 WHERE user_id = 1747;
    (or)
    UPDATE userss SET login_attempts = login_attempts + 1 WHERE lname = 'Johnson' AND fname = 'Alice' AND user_id = 1747;




### 16.Update the email of the user with user_id 1748 only if it's currently null.
    UPDATE users SET email = 'example@example.com' WHERE user_id = 1748 IF email IS NULL;


### 17.Update the password of the user with user_id 1745 only if the current password matches a specific value.
    UPDATE users SET password = 'new_password' WHERE user_id = 1745 IF password = 'old_password';




### 18. Use different types of data modification operations within a single batch operation in Cassandra.

    BEGIN BATCH
    INSERT INTO users (user_id, fname, lname) VALUES (1755, James, 'Smith');
    UPDATE users SET fname = 'Jonathan' WHERE user_id = 1746;
    DELETE FROM users WHERE user_id = 1747;
    APPLY BATCH;






### 19.Update multiple rows in a batch operation.

    BEGIN BATCH
    UPDATE users SET status = 'active' WHERE user_id = 1745;
    UPDATE users SET status = 'inactive' WHERE user_id = 1746;
    APPLY BATCH;



### 20. Perform conditional updates on multiple rows using a batch operation

    BEGIN BATCH
    UPDATE users SET fname = 'Jonathan' WHERE user_id = 1745 IF lname = 'Smith';
    UPDATE users SET lname = 'Doe' WHERE user_id = 1746 IF fname = 'Jane';
    APPLY BATCH;
    
    (or)
    
    BEGIN BATCH
    UPDATE userr SET fname = 'Jonathan' WHERE user_id = 1745 AND lname = 'Smith';
    UPDATE userr SET fname = 'Jane' WHERE user_id = 1746 AND lname = 'Smith';
    APPLY BATCH;





### 21. Add a new field named telephone to the users table.
    ALTER TABLE users ADD telephone text;


### 22.Delete the user with user_id 1745 from the users table.
    DELETE FROM users WHERE user_id = 1745;


### 23. Delete the email column value for the user with user_id 1746.
    DELETE email FROM users WHERE user_id = 1746;



### 24.Delete multiple users in a batch operation.
    BEGIN BATCH
    DELETE FROM users WHERE user_id = 1747;
    DELETE FROM users WHERE user_id = 1748;
    APPLY BATCH;




### 25. Remove the users table.
    DROP TABLE users;


### 26. Remove all data from the users table.
    TRUNCATE users;


### 27. Create a table with a composite key
    CREATE TABLE tab2 ( id1 int, id2 int, first_name varchar, last_name varchar, PRIMARY KEY(id1, id2) );


