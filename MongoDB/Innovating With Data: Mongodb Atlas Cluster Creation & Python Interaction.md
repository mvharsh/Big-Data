# A) Create Free Cluster, User with Privilege, Database, Collection(Table), Document(Record)

  •	Visit the MongoDB Atlas website and sign up or log in.  
  •	Click on "Try Free" to create a new MongoDB account.  
  •	Access the MongoDB cloud dashboard or MongoDB Atlas dashboard.  
  •	Build a cluster by selecting the desired options (e.g., cloud provider, region, cluster tier).  
  •	Go to the security tab and add a new database user.  
  •	Click on "Add New User".  
  •	Create a user with username 'test' and password 'test'.  
  •	Select the privilege option "Read and Write to any database" and add the user.  
  ![image](https://github.com/mvharsh/Big-Data/assets/111365320/ac00c7f6-ec33-46ba-9bdb-07801607a255)
 
  •	Configure IP whitelist to allow interaction from anywhere.  
  ![image](https://github.com/mvharsh/Big-Data/assets/111365320/814282e4-82f0-486a-92bb-dd3f495546a5)
  
  •	Verify the completion of the cluster setup by checking the "Overview" section. 
  ![image](https://github.com/mvharsh/Big-Data/assets/111365320/2117025f-1c34-46a6-aed9-93f67404ae7d)
  
  •	In the sandbox environment, navigate to "Collections" and create a new database named "Student_db" with the first collection named "students_records".  
  ![image](https://github.com/mvharsh/Big-Data/assets/111365320/1a8fe55d-8e8b-4d78-b34a-3b33d543d301)

  •	Create a new document within the "students_records" collection by clicking on "Insert Document" and inputting data in JSON format.  
  •	Utilize the filter option to display the required details. 
  
![image](https://github.com/mvharsh/Big-Data/assets/111365320/40385d70-c37a-4d78-a126-5187af5f27f5)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/f5c1400f-20fc-4ee6-8170-24863af64813)

# B) Interacting with the MongoDB Cluster using Python Code 

#### 1. Install the pymongo library for interacting with MongoDB. 
      pip install pymongo

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/573acd4e-a488-4683-99a5-3ee637d8dd0f)

#### 2. Import MongoClient from the pymongo library in your Python code. 
      from pymongo import MongoClient 

#### 3. Connect to the "Student_db" database using its connection string obtained from MongoDB Atlas. 
      client = MongoClient("Connection String") 
      db = client.Student_db 
![image](https://github.com/mvharsh/Big-Data/assets/111365320/cb8d2a7a-e6b8-4974-804f-dbb413991543)
       

#### 4. Perform the following operations 

#### i) Count documents 
      document_count = db.students_records.count_documents({}) 
      print("Total documents:", document_count) 
![image](https://github.com/mvharsh/Big-Data/assets/111365320/e8376362-eff1-4ef3-89dc-949b57e5dffb)
 
#### ii) Create a new document 
      new_document = {"name": "John Doe", "age": 25, "grade": "A"}
      db.students_records.insert_one(new_document) 
![image](https://github.com/mvharsh/Big-Data/assets/111365320/d009fd9e-2014-4930-9b5a-4a03f3d0f222)

#### iii) Insert single and multiple documents: 

##### For Insert Single document: 
      new_document = {"name": "John Doe", "age": 25, "grade": "A"}
      db.students_records.insert_one(new_document) 
![image](https://github.com/mvharsh/Big-Data/assets/111365320/1d455328-c716-444b-bd96-f524aac1ba7b)

##### For Insert Multiple documents: 
      multiple_documents = [ 
      {"name": "Alice", "age": 22, "grade": "B"}, 
      {"name": "Bob", "age": 24, "grade": "B"}, 
      {"name": "Charlie", "age": 23, "grade": "C"} 
      ] 
      db.students_records.insert_many(multiple_documents) 

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/6132f81d-62e8-45eb-8b98-22fe017b80ec)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/f80de0ae-770b-4937-ac09-9079e4f516ae)

#### iv) Find documents 
      results = db.students_records.find({"grade": "A"})
      for result in results: 
      print(result) 
![image](https://github.com/mvharsh/Big-Data/assets/111365320/026274e7-8499-428e-8ada-a962a2ea8113)

#### v) Update documents: 
      db.students_records.update_one({"name": "John Doe"}, {"$set": {"age": 26}}) 
![image](https://github.com/mvharsh/Big-Data/assets/111365320/64420f36-eb54-4143-b6c7-a3c08b7021e3)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/36762002-698c-4fce-8a57-63741b45aedf)

 
 
#### vi) Delete documents 
      db.students_records.delete_one({"name": "Alice"})
![image](https://github.com/mvharsh/Big-Data/assets/111365320/9f899f01-87be-4f47-8452-0b6dd89b08ef)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/273f06c7-4200-4726-ad5a-ebb3a181d06a)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/de9ba031-67b8-4432-8c22-ce3d47592b90)
