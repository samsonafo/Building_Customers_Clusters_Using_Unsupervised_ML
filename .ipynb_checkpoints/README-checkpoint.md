![Building Cusomer Clusters](./img/cover_img.png)

### Aim: 
The Aim of this project is to build an un-supervised machine learning model to segment customers into different groups.

#### Language Used : Python --version: 3.8.11

### Repo Contents
1. data - contains all csv data files.
2. img - contains all img files used in repo
3. requirements.txt
4. model_development.ipynb -  Jupyter notebook containing all case solutions and model development.

### Data
1. customers : data containing customer details such as 'customer_ID', 'sex', 'registration_date', 'first_rent_date' and 'customer_age'
2. rentals: data containing rental details of customers over a given time period.


### Approach
- I built and compared 2 Unsupervised clustering model.

1. KMeans clustering (with 5 clusters)
2. MiniBatch KMeans clustering (with 5 clusters).

**  The number of clusters was randomly selected. (We also discuss how to find the optimal number of clusters to build.)

- Features Used
    - 'Gender': gender of the customer, either male, female or unknown
    - 'Age_Years': age in years of the customer
    - 'monthly_rent_average' : customer monthly rent average.
    - 'mean_monthly_rental_revenue', : the mean revenue generated from each customer.
    - 'registration_to_rental_days' : days between registration and first rent.
    - 'mean_monthly_rental_duration' : the mean rental duration of each customer.

- Preprocessing
    - For the model development, I encoded the 'Gender' column using the OrdinalEncoder.
    - Normalizer for the 'Age_Years', 'mean_monthly_rental_revenue', 'registration_to_rental_days'.
    
- Models/Pipelines
    - K-Means clustering.
    - Mini-Batch K-means clustering.
    
#### Observations (from Model development)
Note: (**group numbers in the statement below might vary due to model re-build but group dynamics are consistent)
- The highest mean 'monthly_rent_average' is that of group 5 with about 5.49 and the lowest being group 1 with 0.52.
- Although Group 3 and Group 4 are close in monthly_rent_average, they differ in that the customers in group 4 tend to take longer between their registration to their First_Rental.
- Group 1 is our Highest monthly rental revenue group but group 0 and group 5 gives an higher certainty of the average mean revenue of 5.37 and 5.66 respectively.
- Group 1 also has the highest mean monthly rental duration (but with a high standard deviation) while group 0 and group 2 have the lowest mean duration but with a lot higher certainty. (This can help with fleet planning).

#### Further Work
- Explore possible Age categories/groups of each customer groups.
- Exlore possible model locations of each customer groups
    

#### Notes from Model Development
- I Tried creating a cluster from the Shift Mean cluster algorithm, but it was a bit slow.
- We could also create more columns as features like 'modal location of rent per customer', 'modal rental type per customer' etc.


### To Run

1. Read the README.md file
2. create a conda environment
3. `pip install -r requirements.txt`
4. run jupyter lab
5. run the jupyter Notebook (solutions.ipynb,spark_test.ipynb etc.)

**Note: spark_test.ipynb requires a pyspark installation. Read More here: https://bit.ly/3NHy9BM


### Possible Problems
** In case of problems installing matplotlib on a new environment, pls see this: https://stackoverflow.com/questions/21784641/installation-issue-with-matplotlib-python

or try `conda install matplotlib` and then run `pip install -r requirements.txt` again.

** Incase there any challenges with viewing the plotly charts, pls use jupyter notebook in place of Jupyter Lab.
