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
      Use IQR for determining the outliers. Judiciously modify the data frame to get rid of the outliers in the data.Please find attached the histograms depicting how the distribution is better after removing the outliers
      
![Histogramwithoutlier](https://github.com/user-attachments/assets/5d645782-94a4-48bc-982c-91fa126f3125)

![HistogramWithoutOutliers](https://github.com/user-attachments/assets/94611d68-34a3-454b-b98c-bb3281639809)

  ## Null Values Analysis
    When Verifying percentage of Null Value spread across columns in the dataset . 
    Here are some Key Observations
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
      
      We decided to discard the columns with greater than 40 pct of the values NULL from 
      our Training and Test data set leveraged for training the model. So the columns 
      condition, cylinders,size will not be considered to be a part of the training and test
      
  ## Discard Categorical Columns
  
     We leverage the value_counts() function to identify the number of distinct values for each   
    categorical column. Any categorical column with more than 20 unqiue values was discarded 
    from the   training set with the exception of manufacturer( based on the knowledge that the 
    brand of the car could   have a say in the price of the car)    
   
  ## Handling Duplicate/Multiplicate VINS
  
      It was observed that the Vehichle Identification Number, a unque number to identify a vehichle 
      was repated across multiple records. For the majority of the records the price across records 
      was the same and so was majority of other columns except region. This redundant data would be 
      of no imminent use to the model and as a part of the data cleanup care was taken to ensure 
      that only one of the VIN record was retained and the rest were deleted from the data set 

  ## Generate Boxplot and Countplots for all columns


    ![Box_and_count_splot_categorical](https://github.com/user-attachments/assets/5d1c245c-a6a1-4ff4-833b-2c016e26a3b6)

    
    
