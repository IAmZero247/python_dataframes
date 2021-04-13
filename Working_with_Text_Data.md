# Text Files

	  
1.	Preparing Input 
      ```
	  chicago = pd.read_csv("pandas/chicago.csv").dropna(how= "all")
	  chicago.info()
          # memory usage =1.2+  MB
      chicago["Department"] = chicago["Department"].astype("category")
      chicago.head(3)
      chicago.tail(3)
	  chicago.info()
          # memory usage =1.0+  MB
	  ```
	  
2.	Getting Unique

      ```
	  chicago["Department"].nunique()
	  chicago["Department"].count()
	  chicago.nunique()
	  ``` 	

3.	String Methods - lower() upper() title() len()  
    
	  ```
	  # Format department using title()
	  chicago["Position Title"] =chicago["Position Title"].str.title()


	  # Ex:
      chicago["Position Title"].str.len()
      chicago["Position Title"].str.lower()
      chicago["Position Title"].str.upper()
	  ```

4.  String Method - Replace

     ```
     chicago["Department"] = chicago["Department"].str.replace("MGMNT" , "MANAGEMENT")
     chicago["Employee Annual Salary"] = chicago["Employee Annual Salary"].str.replace("$" , "").astype(float)
     
	 #some aggregate operation 
	 chicago["Employee Annual Salary"].sum()
	 chicago["Employee Annual Salary"].mean()
	 chicago["Employee Annual Salary"].std()
	 chicago["Employee Annual Salary"].nlargest(10)
	 ```
5.  Filtering Using String methods
    
      ```
      # Filter for "water"
	  mask = chicago["Position Title"].str.lower().str.contains("water")

	  # mask = chicago["Position Title"].str.lower().str.startswith("water")
	  # mask = chicago["Position Title"].str.lower().str.endswith("specialist")
	  chicago[mask]
      ```
6.  Removing White Spaces From String [ lstrip() rstrip() strip()]
     
      ```
      chicago["Position Title"] = chicago["Position Title"].str.strip()
      chicago["Department"] = chicago["Department"].str.strip()
      ```	  
7.  String Methods on Dataframe Index And Columns Headers

      ```
	  chicago_with_string_index = pd.read_csv("pandas/chicago.csv" , index_col= "Name").dropna(how= "all")
      chicago_with_string_index.info()
	  
	  chicago_with_string_index.index = chicago_with_string_index.index.str.strip().str.title()
	  chicago_with_string_index.columns = chicago_with_string_index.columns.str.upper()
      chicago_with_string_index
      ```	 
8.  Split Method [Returns Series]
       
	  ```
	  chicago["LName"] = chicago["Name"].str.split(",").str.get(0).str.title()
	  chicago["FName"] = chicago["Name"].str.split(",").str.get(1).str.strip().str.split(" ").str.get(0).str.title()
	  chicago
	  # most common last names and first names 
	  chicago["LName"].value_counts().head()
	  chicago["FName"].value_counts().head()
	  ```	

9.  Split Method With Expand and Max Split Setting [Returns Dataframe]	  
	 
      ```
	  chicago[["First Name", "Last Name"]] = chicago["Name"].str.split(",", expand= True , n=1)
      ```	  
		
