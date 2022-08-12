# Credit_card-fraud-detection
An anomaly detection model by using self organizing maps (SOM) .

### **Preprocessing**
* First, we install the Minisom package. 
* we import the necessary libraries. 
* we load the CSV file then divide it into two parts the X which will be trained and then y just for adding markers for visualisation which will tell if the credit card was approved or not for specific winning nodes.
* we apply feature scaling by using min Max scaler i.e, normalisation. 

### **Training the SOM**

* we assign a variable Som to create an object of mini Som class we are creating a 10X10 size unit size of map, input length is 15 because there are 14 features plus one customer_id column. Sigma is the radius of BMU (best matching unit i.e node/neuron).

* Then randomly initialize weights, then we train our self-organising map 
now we will visualise the map.


### **Visualizing the results**

* bone adds Window on which map will be shown.
* Som.distance gives mean interneuron distance (MIDS) as a matrix and pcolor plots those MIDs on the graph/plot/map.

* Now we will iterate through every applicant in the data set, 
  * Then, we will find the coordinates of the winning node with the help of .winner method and then add a marker at the specific node according to the applicant’s card approval. 
 
 *Each small boxes int the plot are nodes/neurons each has specific MIDs (mean inter-neuron distance).* 
 *White BMUs are outliers because their inter neuron distance are larger so they are the ones that are anomalies.* 

### **Finding the frauds**

* Win_map method gives all the customers in each winning node.
* The white nodes, outline winning nodes have all the outliers. So mapping[(1,1)] and mapping[(4,1)] gives a list of all the outlier customers. 
* Then we reverse the feature scaling by using inverse_transform.
* The frauds variable is given in as an array of lists of customers’ features.
* Finally, we print the fraudulent ids which is present in the intial (0) column of the array.
