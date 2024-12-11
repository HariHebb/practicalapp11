# practicalapp11
The practical assignment 11.1 PCAIML
# Context
In this application, you will explore a dataset from kaggle. The original dataset contained information on 3 million used cars. The provided dataset contains information on 426K cars to ensure speed of processing. Your goal is to understand what factors make a car more or less expensive. As a result of your analysis, you should provide clear recommendations to your client -- a used car dealership -- as to what consumers value in a used car.

# Data Exploration and Analysis
  ## Basic Exploration
    The dataset had ~426K rows with 18 columns as can be inferred in the info() call. The dataset had 4 numerical columnsand the rest were categorical. The column list is as mentioned below 
       **Data columns (total 18 columns):
       
       0   id            426880 non-null  int64  
       1   region        426880 non-null  object 
       2   price         426880 non-null  int64  
       3   year          425675 non-null  float64
       4   manufacturer  409234 non-null  object 
       5   model         421603 non-null  object 
       6   condition     252776 non-null  object 
       7   cylinders     249202 non-null  object 
       8   fuel          423867 non-null  object 
       9   odometer      422480 non-null  float64
       10  title_status  418638 non-null  object 
       11  transmission  424324 non-null  object 
       12  VIN           265838 non-null  object 
       13  drive         296313 non-null  object 
       14  size          120519 non-null  object 
       15  type          334022 non-null  object 
       16  paint_color   296677 non-null  object 
       17  state         426880 non-null  object **
       
  ## Outliers Handling
      Use IQR for determining the outliers. Judiciously modify the data frame to get rid of the outliers in the data.
      Please find attached the histograms depicting how the distribution is better after removing the outliers
      ![image](https://github.com/user-attachments/assets/10c413de-03ad-44fc-858a-198c00b046bf)

  ## Null Values Analysis
    When Verifying percentage of Null Value spread across columns in the dataset . Here are some Key Observations
    - Region, Price, State and ID are compulsively populated
    - Year, Model,fuel,odometer. title status, transmission are available for the vast majority of records
    - Type,Paint Color and drive are populated for ~60-65% of records
    - The rest of the columns have large number of records which are NaN or NULL
     For the statistically inclined , below tables presents the % of NULL columns by feature/column
    **id               0.000000
      region           0.000000
      price            0.000000
      year             0.282281
      manufacturer     4.133714
      model            1.236179
      condition       40.785232
      cylinders       41.622470
      fuel             0.705819
      odometer         1.030735
      title_status     1.930753
      transmission     0.598763
      VIN             37.725356
      drive           30.586347
      size            71.767476
      type            21.752717
      paint_color     30.501078
      state            0.000000**
      
      We decided to discard the columns with greater than 40 pct of the values NULL from our Training and Test data set
      leveraged for training the model
   
    
    
