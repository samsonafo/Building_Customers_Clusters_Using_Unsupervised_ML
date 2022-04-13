![Building Cusomer Clusters](./img/cover_img.png)

### Aim: 
The Aim of this project is to build an un-supervised machine learning model to segment customers into different groups.

Meduim Article link: https://bit.ly/3M7doOt

#### Language Used : Python --version: 3.8.11

### Repo Contents
1. data - contains all csv data files.
2. img - contains all img files used in repo
3. requirements.txt
4. model_development.ipynb -  Jupyter notebook containing all case solutions and model development.

### Data
1. customers : data containing customer details such as 'customer_ID', 'sex', 'registration_date', 'first_rent_date' and 'customer_age'
2. rentals: data containing rental details of customers over a given time period.


Data Exploration/Dashboard: https://bit.ly/3M0dEib

![Dashboard](./img/dashboard.png)

### Approach
- I built and compared 2 Unsupervised clustering model.

1. KMeans clustering (with 5 clusters)
2. MiniBatch KMeans clustering (with 5 clusters).

**  The number of clusters was randomly selected. (We also discuss how to find the optimal number of clusters to build.)

- Features Used
    - 'sex': gender of the customer, either male, female or unknown
    - 'customer_age': age in years of the customer
    - 'monthly_rent_average' : customer monthly rent average.
    - 'mean_monthly_rental_revenue', : the mean revenue generated from each customer.
    - 'registration_to_rental_days' : days between registration and first rent.
    - 'mean_monthly_rental_duration' : the mean rental duration of each customer.

- Preprocessing
    - For the model development, I encoded the 'sex' column using the OrdinalEncoder.
    - Normalizer for the 'customer_age','mean_monthly_rental_revenue','mean_monthly_rental_duration','registration_to_rental_days'.
    
- Models/Pipelines
    - K-Means clustering.
    - Mini-Batch K-means clustering.
    
    
#### Observations (from Model development)
Note: (**group numbers in the statement below might vary due to model re-build but group dynamics are consistent)
- Group 0 contains customers with less ride frequency but with the highest mean monthly rental revenue.
- Group 4 contains who ride often(to work,school) but possibly for short distances.
- While Group 1 and Group 3 seem similar in both the mean_monthly_rental_avenue & monthly_rent_average.

#### Deciding the Optimal Number Clusters
- Elbow Method
- Silhouette Coefficient
- Calinski-Harabasz Index

#### Further Work
- Explore possible Age categories/groups of each customer groups.
- Exlore possible model locations of each customer groups
- Recommender System for rent packages based on customer similarities.
    





### To Run

1. Read the README.md file
2. create a conda environment
3. `pip install -r requirements.txt`
4. run jupyter lab
5. run the jupyter Notebook (solutions.ipynb,spark_test.ipynb etc.)
