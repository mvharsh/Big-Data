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

![image](https://github.com/mvharsh/Big-Data/assets/111365320/712ce16c-5a37-40e1-8ef2-718343a01ae7)


### 9.Display data from the users table sorted by lname in descending order.

    CREATE TABLE user (
      user_id int,
      fname text,
      lname text,
      PRIMARY KEY (lname, fname, user_id)
    ) WITH CLUSTERING ORDER BY (fname ASC, user_id ASC);
    
    SELECT * FROM user WHERE lname = ‘Johnson’ ORDER BY fname ASC, user_id ASC;
    
![image](https://github.com/mvharsh/Big-Data/assets/111365320/61c02244-2682-40c4-8566-0e14e2e892f9)

### 10.Display the first two rows from the users table.
    SELECT * FROM users LIMIT 2;

![image](https://github.com/mvharsh/Big-Data/assets/111365320/e34e8d17-62b1-4570-bdc2-85bdaf30f40e)

### 11.Count the number of users with the same lname.
    SELECT lname, COUNT(*) as count FROM user GROUP BY lname;

![image](https://github.com/mvharsh/Big-Data/assets/111365320/245282db-bf07-4327-914d-620a16d008e3)

### 12. Display unique last names from the users table.
    SELECT DISTINCT lname FROM user;

![image](https://github.com/mvharsh/Big-Data/assets/111365320/8673d435-65d3-4989-9e2b-10beedddd389)

### 13. Update the telephone field for the user with user_id = 1745 to '21212121'.
    UPDATE users SET telephone = '21212121' WHERE user_id = 1745;

![image](https://github.com/mvharsh/Big-Data/assets/111365320/ded3755b-89d9-4210-9957-f69e34215ffa)

### 14.Update both fname and lname of the user with user_id 1746.
    UPDATE users SET fname = 'Jane', lname = 'Smith' WHERE user_id = 1746;
![image](https://github.com/mvharsh/Big-Data/assets/111365320/70d38317-8bc5-47e3-ae2d-cee410374829)

### 15. Increment the login_attempts counter for the user with user_id 1747 by 1.

    UPDATE userss SET login_attempts = login_attempts + 1 WHERE lname = 'Johnson' AND fname = 'Alice' AND user_id = 1747;

![image](https://github.com/mvharsh/Big-Data/assets/111365320/046f8a02-55dc-4a03-a3fe-4967c8cc163b)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/9b8cad32-a4e1-4599-af2b-cddba852cd13)



### 16.Update the email of the user with user_id 1748 only if it's currently null.
    UPDATE users SET email = 'example@example.com' WHERE user_id = 1748 IF email IS NULL;
![image](https://github.com/mvharsh/Big-Data/assets/111365320/4350f5cb-f700-4f81-9664-11eea5b08c9f)


### 17.Update the password of the user with user_id 1745 only if the current password matches a specific value.
    UPDATE users SET password = 'new_password' WHERE user_id = 1745 IF password = 'old_password';

![image](https://github.com/mvharsh/Big-Data/assets/111365320/6c6cf619-d28c-40a2-8ca6-05a40f6d9f1f)

### 18. Use different types of data modification operations within a single batch operation in Cassandra.

    BEGIN BATCH
    INSERT INTO users (user_id, fname, lname) VALUES (1755, James, 'Smith');
    UPDATE users SET fname = 'Jonathan' WHERE user_id = 1746;
    DELETE FROM users WHERE user_id = 1747;
    APPLY BATCH;

![image](https://github.com/mvharsh/Big-Data/assets/111365320/137d9a23-7a48-44c1-8ca8-9bfc7ac56ed6)

### 19.Update multiple rows in a batch operation.

    BEGIN BATCH
    UPDATE users SET status = 'active' WHERE user_id = 1745;
    UPDATE users SET status = 'inactive' WHERE user_id = 1746;
    APPLY BATCH;

![image](https://github.com/mvharsh/Big-Data/assets/111365320/3acf82fc-f795-4989-bf36-5b1a9c7fb56d)


### 20. Perform conditional updates on multiple rows using a batch operation
    
    BEGIN BATCH
    UPDATE userr SET fname = 'Jonathan' WHERE user_id = 1745 AND lname = 'Smith';
    UPDATE userr SET fname = 'Jane' WHERE user_id = 1746 AND lname = 'Smith';
    APPLY BATCH;

![image](https://github.com/mvharsh/Big-Data/assets/111365320/1e9aac49-00b9-4764-9ffb-03c2829bea4d)

### 21. Add a new field named telephone to the users table.
    ALTER TABLE users ADD telephone text;
![image](https://github.com/mvharsh/Big-Data/assets/111365320/a3cb3871-5a01-487e-95d9-f7ced510d939)


### 22.Delete the user with user_id 1745 from the users table.
    DELETE FROM users WHERE user_id = 1745;
![image](https://github.com/mvharsh/Big-Data/assets/111365320/430761ce-40fd-4479-b87c-3955eb7fafe7)


### 23. Delete the email column value for the user with user_id 1746.
    DELETE email FROM users WHERE user_id = 1746;
![image](https://github.com/mvharsh/Big-Data/assets/111365320/0538a554-06c6-45f4-bdac-465218648d95)

### 24.Delete multiple users in a batch operation.
    BEGIN BATCH
    DELETE FROM users WHERE user_id = 1747;
    DELETE FROM users WHERE user_id = 1748;
    APPLY BATCH;

![image](https://github.com/mvharsh/Big-Data/assets/111365320/82948966-a383-4251-9295-4666a1b9cc9c)

### 25. Remove the users table.
    DROP TABLE users;
![image](https://github.com/mvharsh/Big-Data/assets/111365320/5273ce6b-b20c-455f-90a7-4f7376ef1594)


### 26. Remove all data from the users table.
    TRUNCATE users;
![image](https://github.com/mvharsh/Big-Data/assets/111365320/c7e3c838-7c53-485e-ba29-903b90b96e90)


### 27. Create a table with a composite key
    CREATE TABLE tab2 ( id1 int, id2 int, first_name varchar, last_name varchar, PRIMARY KEY(id1, id2) );

![image](https://github.com/mvharsh/Big-Data/assets/111365320/c4b09bc7-2d5a-42d1-8627-10f76872b103)
