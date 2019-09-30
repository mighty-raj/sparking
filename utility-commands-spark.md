
To clear all that cached at once ... 

    spark.catalog.clearCache()  

To estimate size of a dataframe for broadcasting...    
    
    import org.apache.spark.util.SizeEstimator
    SizeEstimator.estimate(<DATAFRAME-NAME>)
    
