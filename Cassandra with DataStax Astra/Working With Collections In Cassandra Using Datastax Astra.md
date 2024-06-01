
# Collections - SETS 

### 1. create a table named users in Cassandra with a column named emails as a set of text values 

    CREATE TABLE users ( 
    user_id int PRIMARY KEY, 
    fname text, 
    lname text, 
    emails set<text> 
    ); 

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/5f4ed098-28c1-426c-8329-64d96f46997b)


### 2. insert data into the emails set for a user with user_id 1234. 
    INSERT INTO users (user_id, fname, lname, emails) 
    VALUES(1234, 'Frodo', 'Baggins', {'f@baggins.com', 'baggins@gmail.com'}); 

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/1d46d300-546f-4a8e-b347-181412345ae4)


### 3. Retrieve the user_id and emails for the user with user_id 1234. 
    SELECT user_id, emails FROM users WHERE user_id = 1234; 

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/4a3dfcb8-baca-4a9f-a527-6180784f6e19)


### 4. Add the email address 'fb@friendsofmordor.org' to the set of emails for the user with user_id 1234 
    UPDATE users SET emails = emails + {'fb@friendsofmordor.org'} WHERE user_id = 1234; 

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/5025826f-02ec-40ee-afcd-653563dec76c)


### 5. Retrieve the user_id and updated emails for the user with user_id 1234 after adding the new email. 
    SELECT user_id, emails FROM users WHERE user_id = 1234; 

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/12650686-f802-4461-8e6e-96c502385d63)


### 6.Remove the email address 'fb@friendsofmordor.org' from the set of emails for the user with user_id 1234 
    UPDATE users SET emails = emails - {'fb@friendsofmordor.org'} WHERE user_id = 1234; 

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/2ae94e9c-44ac-43cd-a65a-1c30fdcc45c1)


### 7.Remove all email addresses from the set for the user with user_id 1234. 
    UPDATE users SET emails = {} WHERE user_id = 1234; 
    (OR) 
    DELETE emails FROM users WHERE user_id = 1234; 

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/4154bf68-0b4a-43f4-a217-0c34010be725)


# Collections - LISTS 

### 1. Alter the users table to include a column named top_places as a list of text values 
    ALTER TABLE users ADD top_places list<text>; 
![image](https://github.com/mvharsh/Big-Data/assets/111365320/b7430cb5-04ae-4bde-ae5d-bdef7f5936db)

 
### 2. Insert a list of the best places visited into the top_places column for the user with user_id 1234. 
    UPDATE users SET top_places = [ 'rivendell', 'rohan' ] WHERE user_id = 1234; 

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/e995015b-fc2c-48f7-ac78-800d99a5588c)


### 3.Add the place 'mordor' to the end of the list of top_places for the user with user_id 1234
    UPDATE users SET top_places = top_places + [ 'mordor' ] WHERE user_id = 1234; 

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/e102673f-6adb-4832-944c-a9e7fa963eb7)


### 4. Update the second place in the list top_places to 'riddermark' for the user with user_id 1234. 
    UPDATE users SET top_places[1] = 'riddermark' WHERE user_id = 1234; 

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/c63f5c10-37a8-4b54-8b81-55446dc5b153)


### 5.Remove the third place from the top_places list for the user with user_id 1234 
    DELETE top_places[3] FROM users WHERE user_id = 1234; 

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/2e4dbc4e-7c86-41d5-8c28-a5d6af372ec5)


### 6.Remove all occurrences of 'riddermark' from the top_places list for the user with user_id 1234. 
    UPDATE users SET top_places = top_places - ['riddermark'] WHERE user_id = 1234; 
 
![image](https://github.com/mvharsh/Big-Data/assets/111365320/78dd14af-1914-4f8d-90ae-78203b58ea42)


### 7.Retrieve the user_id and top_places list for the user with user_id 1234. 
    SELECT user_id, top_places FROM users WHERE user_id = 1234; 

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/5c04d32d-3ae8-4af2-9af2-f7b4561dc024)


# Collections - MAP 

### 1.Alter the users table to include a column named todo as a map with timestamp keys and text values 
    ALTER TABLE users ADD todo map<timestamp, text>; 

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/61d394fd-84fb-42a3-a83b-c90c72b3df9b)


### 2. Insert tasks into the todo map for the user with user_id 1234. 
    UPDATE users SET todo = { '2012-09-24' : 'enter mordor', '2012-10-02 12:00' : 'throw ring into mount doom' } WHERE user_id = 1234; 

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/b7b6886c-4c80-4b32-ad72-30e0d6a57492)


### 3. Add a task with the timestamp '2012-10-2 12:00' to the todo map for the user with user_id 1234 
    UPDATE users SET todo['2012-10-02 12:00'] = 'throw my precious into mount doom' WHERE user_id = 1234; 

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/93182892-6ec5-4056-b9a3-3ab144281d19)


### 4. Insert tasks into the todo map for the user with user_id 1234 using the INSERT statement. 
    INSERT INTO users (user_id, todo) VALUES ( 1234, { '2013-09-22 12:01' : 'birthday wishes to Bilbo', '2013-10-01 18:00' : 'Check into Inn of Prancing Pony' }); 

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/987f99c9-502a-4066-883d-b4b8c118d3fa)


### 5. Remove the task with the timestamp '2012-9-24' from the todo map for the user with user_id 1234 
    DELETE todo['2012-09-24'] FROM users WHERE user_id = 1234;

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/d9e18cbe-2f8a-4ebd-9c58-09b303dd2f1c)

 
### 6.Retrieve the user_id and todo map for the user with user_id 1234. 
    SELECT user_id, todo FROM users WHERE user_id = 1234; 

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/f785b751-3d6c-4168-a5a9-1138be6874ee)


