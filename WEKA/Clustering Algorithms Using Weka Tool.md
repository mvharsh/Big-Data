
# 1.	Data Preparation:

•	Launch the WEKA Tool on your computer.
•	Load the Iris dataset into the WEKA environment.

# 2.	Selection of Clustering Algorithms:

•	Navigate to the clustering algorithms section in the WEKA Tool.
•	Select K-Means, CONWEB, Canopy, and Hierarchical clustering algorithms for comparison.

# 3.	Parameter Configuration:

•	Set the parameters for each clustering algorithm:

## a) K-Means:

<b>Number of clusters:</b> This parameter depends on the dataset and the desired granularity of clustering. For the Iris dataset, a common choice is 3 clusters since there are three distinct classes in the dataset.
![image](https://github.com/mvharsh/Big-Data/assets/111365320/2f10cc1b-4fac-4b90-b230-c9bf7f1e9e98)

##### Output:
![image](https://github.com/mvharsh/Big-Data/assets/111365320/7aa6070d-2e1d-445f-a75f-5a8d1f1470da)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/fee80fdd-7c58-4788-8945-e4b618dc2612)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/e5e8c1d2-7209-4981-b6bf-2c1eac13ae3a)

 
## b) COBWEB (COnstrained Nearest NEighBor):

<b>COBWEB</b> is a constrained clustering algorithm that requires specific constraints. In the absence of specific constraints, default parameters may not be applicable. However, you can leave the parameters as default if no specific constraints are provided.
![image](https://github.com/mvharsh/Big-Data/assets/111365320/36351b47-8dd1-4942-86b6-3830dd0f2d25)

 

##### Output:
![image](https://github.com/mvharsh/Big-Data/assets/111365320/8fa95d11-df5a-4903-8f54-8242d5b86819)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/1ec5ad7f-2c01-4565-ba11-64aec4c56b44)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/94b05a9b-fdf9-41ab-a9d2-11eb5f22f21d)


## c) Canopy:

<b>T1:</b> The distance threshold for the canopy to start including points.

<b>T2:</b> The distance threshold for the canopy to stop including points.

These thresholds depend on the dataset and should be set empirically. For the Iris dataset, a common choice could be T1 = 1.0 and T2 = 0.5.
![image](https://github.com/mvharsh/Big-Data/assets/111365320/b0e6042e-7f22-42e7-b1e3-adc07ac3c118)


##### Output:
![image](https://github.com/mvharsh/Big-Data/assets/111365320/868c636a-a861-42d3-a859-9570e2beb62b)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/1ddc15e0-e795-476f-a7ed-e81173467c69)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/0fc90baa-7f42-4389-b73d-9a1a1cdaa4eb)

 
## d) Hierarchical:

•	<b>Linkage method:</b> Choose between single, complete, average, or Ward's method based on the characteristics of the dataset. For the Iris dataset, Ward's method is often a good choice.

• <b>Distance measure:</b> Euclidean distance is a common choice for measuring the distance between points in hierarchical clustering.
![image](https://github.com/mvharsh/Big-Data/assets/111365320/663321cb-5da0-48b2-9c33-0175e8d5aff7)

##### Output:
![image](https://github.com/mvharsh/Big-Data/assets/111365320/64642503-035e-4dd1-843b-d870cdedefac)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/e0ee09bd-a41f-4580-9ff5-9dd09d875960)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/b2bb299e-0496-4d75-a251-8ac205b5158d)

 

 

 

