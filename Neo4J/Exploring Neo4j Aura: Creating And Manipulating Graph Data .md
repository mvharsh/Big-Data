# a) Login Procedure   

  •	Open the Neo4j Aura website using the link: Neo4j Aura Graph Database.  
  •	Login with the "Get Started Free" option.  
  •	Create a new free instance. 
  •	Copy the generated password and click on "Download and Continue" option.  
  •	Once the 'Instance01' is created, open it.  
  •	In the "Connection to Instance" dialog box, enter the password and click "Connect".  
  •	Navigate to the Query Console by selecting the "Learn the basics" option. 
 
# b) Query Operations  

#### 1.  Create a single node named 'sample' without a caption and display it. 
    CREATE (sample);  
    MATCH (n) RETURN n;   
![image](https://github.com/mvharsh/Big-Data/assets/111365320/dbcf9750-10ce-48c2-9e1d-e82618b5b266)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/f2c357ab-9b9a-408c-80fe-d531a5074b0a)

#### 2.  Delete the single node created with the name 'sample'. 
     MATCH (sample)
     DELETE sample; 
![image](https://github.com/mvharsh/Big-Data/assets/111365320/07d89ace-28bc-4a21-b049-a0dfed6f90a9)


#### 3.  Create two single nodes named 'Raja' and 'Ravi' without a caption and display them. 
    CREATE (Raja);   
    CREATE (Ravi);   
    MATCH (n) RETURN n;  

![image](https://github.com/mvharsh/Big-Data/assets/111365320/1eb2b236-c82a-4742-a445-bec4f0c768cf)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/034729d0-9251-4f15-8107-2159a04ae570)

#### 4.  Delete the nodes created above using their IDs. 
    MATCH (n) 
    WHERE id(n) = 0 
    DELETE n 
    --------------- 
    MATCH (n) 
    WHERE id(n) = 1
    DELETE n 
![image](https://github.com/mvharsh/Big-Data/assets/111365320/9d58ccc7-6a00-4946-83e6-63cada5dc92f)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/4902b6c9-788c-4368-bfd1-5d7b41a0392c)

#### 5.  Delete all nodes created so far. 
    MATCH (n) 
    DELETE n 
![image](https://github.com/mvharsh/Big-Data/assets/111365320/60590931-bd57-4cd3-a1cd-85bf66e6c3df)

#### 6. Create a single node named 'Dhoni' with the caption 'player' and display it. 
    CREATE (Dhoni:player);  
    MATCH (n) RETURN n; 
![image](https://github.com/mvharsh/Big-Data/assets/111365320/3ffd9245-8dd3-47f8-a18c-4dcd9abf8dfa)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/63812990-8427-4c6d-8ff7-06f731a40b85)

#### 7. Create a node named 'Dhawan' with multiple labels 'person' and 'player' and display  it. 

     CREATE (Dhawan:person:player) 
     MATCH (n) RETURN n;   

![image](https://github.com/mvharsh/Big-Data/assets/111365320/eae802e6-f823-4278-be46-4ad559ba4737)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/7b8baf26-3fa2-4df9-9730-e562a5e800e8)

#### 8. Create a node named 'Sachin' with the caption 'player' and properties like name,  year of birth (YOB), and place of birth (POB). 
 
     CREATE (Sachin:player{name: "Sachin Tendulkar", YOB: 1985, POB: "Delhi"})  
     MATCH (n) RETURN n;  
![image](https://github.com/mvharsh/Big-Data/assets/111365320/f63d8c6c-c549-4677-bfe6-896bc869d635)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/2dc57ea1-19eb-4c79-9414-f353c349dc13)

#### 9. Create a node named 'Ravinder' with the caption 'player' and properties like name, year of birth (YOB), and place of birth (POB), and return the node without using the MATCH statement. 

    CREATE (Ravinder:player{name: "Ravinder Jadeja", YOB: 1985, POB: "Delhi"}) RETURN Ravinder   
![image](https://github.com/mvharsh/Big-Data/assets/111365320/2c3a1c31-5c67-4134-b16b-0f670e7c257e)

#### 10. Create multiple nodes with properties like name, year of birth (YOB), and place of birth (POB). 
 
    CREATE  
    (Sachin:player {name: "Sachin Tendulkar", YOB: 1985, POB: "Delhi"}), 
    (Virat:player {name: "Virat Kohli", YOB: 1988, POB: "Delhi"}), 
    (Rohit:player {name: "Rohit Sharma", YOB: 1987, POB: "Nagpur"}) 
    MATCH (n) RETURN n  

![image](https://github.com/mvharsh/Big-Data/assets/111365320/ddff7b33-cf52-4674-b57a-ec6d66df8327)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/bf41d3b2-f8cc-4e30-b3f3-60a888606443)

#### 11. Create nodes 'Dhawan' and 'Ind' and establish a relationship 'BATSMAN_OF' between them. 
 
    CREATE (Dhawan:player {name: "Shikar Dhawan", YOB: 1985, POB: "Delhi"})  
    CREATE (Ind:Country {name: "India"}) 
    CREATE (Dhawan)-[r:BATSMAN_OF]->(Ind)  

![image](https://github.com/mvharsh/Big-Data/assets/111365320/4cc055ed-29d6-4a40-bd99-f7c9f0f0afa7)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/f68bf377-a963-46c8-889d-613a001134e8)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/93bf4936-9435-4eaa-8288-3f0471e2ec6a)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/8f641e10-93f2-4487-9dac-77e180e8b95c)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/8953a82a-1f16-4cf6-b1a3-6c363f8f11d9)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/ed69a2a9-431c-4ff1-8e8d-a5ec8fc00da0)

#### 12. Establish a relationship between the player node labeled 'Shikar Dhawan' and the country node labeled 'India'. Include details such as the number of matches played (5) and the batting average (90.75).     
 
    MATCH (a:player), (b:Country)  
    WHERE a.name = "Shikar Dhawan" AND b.name = "India"  
    CREATE (a)-[r:BATSMAN_OF {Matches:5, Avg:90.75}]->(b)   
    RETURN a, b 

![image](https://github.com/mvharsh/Big-Data/assets/111365320/45aac523-5ea9-4b50-bb8d-2525013b355c)
 
#### 13. Create a player node for Mahendra Singh Dhoni, born in Ranchi in 1981. Describe the characteristics of the newly created node and then remove the property 'POB' and label 'player' using the REMOVE statement. 
 
##### Step: 1 (Create Node) 
    CREATE (Dhoni:player {name: "MahendraSingh Dhoni", YOB: 1981, POB: "Ranchi"}) 

![image](https://github.com/mvharsh/Big-Data/assets/111365320/65f932a9-97b5-483a-8f64-4d9b1e49dea7)

##### Step: 2 (Remove Property) 
    MATCH (Dhoni:player {name: "MahendraSingh Dhoni", YOB: 1981, POB: "Ranchi"})  
    REMOVE Dhoni.POB  
    RETURN Dhoni  

![image](https://github.com/mvharsh/Big-Data/assets/111365320/86133c6f-8516-4798-8354-c8f8b84969a9)

##### Step: 3 (Remove Label) 
    MATCH (Dhoni:player {name: "MahendraSingh Dhoni", YOB: 1981, POB: "Ranchi"})  
    REMOVE Dhoni:player  
    RETURN Dhoni  
![image](https://github.com/mvharsh/Big-Data/assets/111365320/dba5f198-874b-4b0c-a525-5c29a86069d1)

#### 14. Create a player node for Shikhar Dhawan, born in Delhi in 1985. After creating the player node, find the node representing Shikhar Dhawan, update its property to reflect his highest score of 187, and return the updated node. 
 
##### Step: 1  
    CREATE (Dhawan:player{name: "shikar Dhawan", YOB: 1985, POB: "Delhi"})  
 
![image](https://github.com/mvharsh/Big-Data/assets/111365320/b8f1a4e6-b05a-4105-b866-b4636802cbb5)

##### Step: 2  
    MATCH (Dhawan:player{name: "shikar Dhawan", YOB: 1985, POB: "Delhi"})  
    SET Dhawan.highestscore = 187  
    RETURN Dhawan 
![image](https://github.com/mvharsh/Big-Data/assets/111365320/0f5b90c4-8918-4ab2-aceb-2940c62ca095)
