# Series

	  
1.	Series From List 
      
	  ```
	  names = ["scorpion", "subzero" , "venom"]
      mortalkombat = pd.Series(names)
	  ```
2.  Series From Dictionary

      ```
	  rank = { "sam" : 1 , "rose" : 2 , "jack" :3 }
      pd.Series(rank)
	  
	  
	  fruits = [ "apple" , "orange" , "plum" , "grapes" , "blueberry" , "repeated"]
      weekdays = ["Mon" , "Tue" , "Wed", "Thurs" , "Fri" , "Mon"]

	  another_sample= pd.Series( data=fruits, index = weekdays)
	  ```   

3.  Attrbutes -[ index  values dtype ] 
    
	  ```
	  about_me = ["smart", "humble" ,"charming" , "handsome"]
	  s1 = pd.Series(about_me)
	  s1.values
	  s1.index
	  s1.dtype
      ```

4.  Methods [ sum product  mean]

      ```
	  prices = [ 1.23, 2.34 , 3.45]
	  p = pd.Series(prices)
	  p.sum()
	  p.product()
	  p.mean()
      ```	
	
5.  Series from Csv 
    
      ```
      pokemonSeries = pd.read_csv("pandas/pokemon.csv", usecols=["Pokemon"], squeeze = True)
      googleStockSeries = pd.read_csv("pandas/google_stock_price.csv" , usecols=["Stock Price"] , squeeze = True)	 
      ```	

6.  The .head() and .tail() Methods

      ```
	  pokemonSeries.head(2)
	  pokemonSeries.tail(2)
      ```	

7.  Built-In Functions 	[len type dir sorted list dict min max]  
    
	  ```
	  pokemon = pd.read_csv("pokemon.csv", usecols = ["Pokemon"], squeeze = True)
      google = pd.read_csv("google_stock_price.csv", squeeze = True)
	  
	  1. len(google)
	  2. type(pokemon) -> available methods and attributes 
	  3. sorted(pokemon)
	  4. list(pokemon)
	  5. dict(google)
	  6. max(google)
	  7. min(google)
	  ```
	  
	  
8.  More Series Attribute [is_unique ndim shape size name]

      ```
	  pokemon.is_unique    -> true if values are unique
      google.is_unique
	 
	  pokemon.ndim
      google.ndim
	 
	  pokemon.shape        -> rows*col
      google.shape
	 
	  pokemon.size         -> includes nulls , None
      google.size
	 
	  pokemon.name
      google.name
	  ```
	 
	  ```
	  pokemon.name = "Pocket Monsters"
	  pokemon.head()
	 
	  0     Bulbasaur
	  1       Ivysaur
	  2      Venusaur
	  3    Charmander
      4    Charmeleon
      Name: Pocket Monsters, dtype: object
	  ```
	  
9.  The .sort_values() Method

      ```
      pokemon = pd.read_csv("pandas/pokemon.csv", usecols = ["Pokemon"], squeeze = True)
      google = pd.read_csv("pandas/google_stock_price.csv", squeeze = True)
	  
	  
	  pokemon.sort_values().head()
	  pokemon.sort_values(ascending = False).tail()
	  google.sort_values(ascending = False).head(1)
	  
      ```	  

10. The inplace Parameter
    
      ```
	  google = pd.read_csv("google_stock_price.csv", squeeze = True)
	  google.head(3)
	  
	  11    49.95
	  9     50.07
	  0     50.12
      Name: Stock Price, dtype: float64
    
	  google.sort_values(ascending = False, inplace = True)
	  google.head(3)
	  

      3011    782.22
      2859    776.60
      3009    773.18
      Name: Stock Price, dtype: float64
      ```	  
	  
	  
	  
		
