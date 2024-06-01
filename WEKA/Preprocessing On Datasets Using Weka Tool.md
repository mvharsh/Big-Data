# a) Loading the Data  

Open the WEKA Explorer. Navigate to the "Preprocess" tab.  Use the "Open" button to load a predefined dataset. Specify the directory and select a dataset such as  "weather.numeric.arff," or "weather.nominal.arff." 


![image](https://github.com/mvharsh/Big-Data/assets/111365320/d5e2ff90-9aac-413e-888f-49cd9e51267a)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/f58008ce-a067-4166-9293-54926be7f111)

Inspect the left panel in the "Preprocess" tab to confirm the recognized attributes. Verify that the base relation and current working relation are initially the same.  

![image](https://github.com/mvharsh/Big-Data/assets/111365320/238ffa3c-882f-488b-b2b1-3974808814eb)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/20af9c2c-911c-47f3-a1ca-c4b59380491b)

Click on any attribute in the left panel to view basic statistics. 

1.	For categorical attributes, check the frequency of each attribute value.  
2.	For continuous attributes, note statistics such as min, max, mean, standard deviation, etc. 

Select an attribute (e.g., "temperature" in "weather.numeric.arff") and visualize its basic statistics.  Choose another attribute (e.g., "play" in "weather.nominal.arff") and visualize its basic statistics.  

![image](https://github.com/mvharsh/Big-Data/assets/111365320/9aae87ef-ed4c-41e5-889d-11cb9bd7bbe0)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/7346f3b4-59ef-4df5-b0c1-0547d37c96e1)

Explore the visualization in the right bottom panel, which is a form of cross-tabulation across two attributes.  For example, understand the default cross-tabulation of "humidity" with "play." Using the drop-down list, select another attribute for cross-tabulation (e.g.,"outlook") and observe the changes

![image](https://github.com/mvharsh/Big-Data/assets/111365320/56d82f4c-6c80-45c2-8e87-94af707944fd)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/69924f7f-216a-44af-a9ea-daf9a6f2b636)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/b7a24ee5-9792-4b96-8eef-8de2c9ebdc8a)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/f6a1ec50-29b5-4cfb-8209-c79ae64f7fb2)
    
# b) Selecting or Filtering Attributes  

Load a dataset with multiple attributes (e.g., "labor.arff" or "weather.nominal.arff"). Navigate to the "Filter" panel and explore various attribute filters available.                                                                                   

![image](https://github.com/mvharsh/Big-Data/assets/111365320/41df0385-93bc-4c41-9df7-df54fa537fc9)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/343ba81a-8cf0-4333-8ffd-1f78b4fdec53)

Implement the "weka.filters.unsupervised.attribute.Remove" filter to remove a specific attribute. Mention the correct attribute name to remove (e.g., "windy").  

![image](https://github.com/mvharsh/Big-Data/assets/111365320/905c2154-3625-42c9-a23a-1a4b75ab93bc)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/29d539a5-1226-4e67-8fea-4a0e53f94210)

Apply the "weka.filters.unsupervised.attribute.Add" filter to add a new attribute with appropriate values. Specify the correct attribute name and values.  
  
![image](https://github.com/mvharsh/Big-Data/assets/111365320/47a23e12-c66c-493d-b944-effc5496a810)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/e133bd44-6964-4348-a713-e07ec7d461fd)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/72a0dd5d-9a5f-4f34-9d9d-b4483f732771)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/cb4de335-0273-4658-af0e-6d17b191f48c)

Try the "weka.filters.unsupervised.attribute.Normalize" filter to normalize numeric attributes. Specify the correct numeric attribute names.  

![image](https://github.com/mvharsh/Big-Data/assets/111365320/95a6962a-9da6-4f88-b8c2-e8e7ab57dcd7)
 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/cf974209-e9a9-4d85-b7b0-7a539560e00d)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/90c13e04-38fe-453e-95b8-38fd8db11a00)

Experiment with the "weka.filters.supervised.attribute.AttributeSelection" filter to select relevant attributes. Specify the correct attribute selection options.  
![image](https://github.com/mvharsh/Big-Data/assets/111365320/27359beb-c452-4335-bfc6-088e9dfd3879)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/54a8a522-228a-49c5-9cc3-c9f5282b4fd4)

Save the modified dataset after each filter operation.
![image](https://github.com/mvharsh/Big-Data/assets/111365320/22102c6d-4cde-4d6e-8257-255ab32ba036)

# c) Discretization 

## Numeric to Nominal Discretization:  

Load the "weather.numeric.arff" dataset.  Go to the "Preprocess" tab.  In the "Filter" section, click "Choose" and select "weka.filters.unsupervised.attribute. Discretize." Click the box next to "Choose" to configure the Discretize filter.  
Select the numeric attributes you want to discretize (e.g., "temperature," "humidity").  Set the number of bins or configure other options.  Click "OK" to close the configuration.  

![image](https://github.com/mvharsh/Big-Data/assets/111365320/8455bf6d-b3ce-47b4-9460-2cc777bfde15)
   

Click "Apply" to apply the Discretize filter.  
Save the new dataset as "weather-nominal-discretized.arff." 

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/dbf6056b-06fd-40c7-b7a5-ffd53f231e48)
 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/79dcf09b-a203-4181-a4e0-e735e2c8b908)
  

## Nominal to Numeric Discretization:  

Open WEKA Explorer.  Load the "weather.nominal.arff" dataset.  Go to the "Preprocess" tab.  In the "Filter" section, click "Choose" and select "weka.filters.unsupervised.attribute.Discretize."  Click the box next to "Choose" to configure the Discretize filter.  Select the nominal attributes you want to discretize (e.g., "temperature," "humidity").  Set the number of bins or configure other options.  Click "OK" to close the configuration.  Click "Apply" to apply the Discretize filter.  Save the new dataset as "weather-numeric-discretized.arff."
   
![image](https://github.com/mvharsh/Big-Data/assets/111365320/0bb455d8-5e81-4d9e-ae15-148232d49320)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/ea674a60-8d49-4324-b38e-e96134ddb9f8)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/c33dc41e-7592-4853-8f60-343b1a1cbea1)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/26c402b9-4d84-4b4f-b632-4b6bdf9e6f73)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/e6009db9-f3ff-4cf4-b30d-921c75a5a533)

# d)  Handling Missing Values  

Load "weather.numeric.arff."  
Check for missing values in attributes.  
Introduce missing values in "outlook" (Nominal) and "temperature" (Numeric).  Note max count label in "outlook" and mean of "temperature."  

![image](https://github.com/mvharsh/Big-Data/assets/111365320/1c665fd0-5330-41dc-8a84-eadc90176ba5)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/cc5c5c44-42b6-4c5a-8859-e5a15b007919)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/04767e67-4e1d-4d88-ac18-7fa0ab139739)


Apply "ReplaceMissingValues" filter.  Examine data for replacement.  
Edit "weather.numeric.arff" with a text editor, replace some data with '?' and save as "weather-numeric-missing.arff."  Load "weather-numeric-missing.arff" in WEKA, observe data. 

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/aa905ffe-0aa9-4026-89f3-5ab672ba1e78)




