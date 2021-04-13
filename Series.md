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

7.  Built-In Functions 	  
	  
	  
		
