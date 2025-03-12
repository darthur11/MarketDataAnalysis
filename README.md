# MarketDataAnalysis


## Task 1
Please find provided three price series for the same underlying instrument from three different sources. Analyse these price series and provide an assessment as to which source is better for a broker to use. The analysis should have a clear and structured explanation of the methodology/metrics used for your comparison, as well as reasoning why you have chosen this/these methodology/methodologies and the results of the analysis. 

## Task 2
Using the same price series provided create a new synthetic mid-price series that improves/tries to deal with the issues identified. Your methodology should only use data available as of that point in time (no forward-looking bias). Implement your model using an event driven approach. Show how the model improves the metrics you defined above

For example the below pseudo code could be used to calculate the simple mean between the three sources based on the latest available data: 

class Model: 
    prices = [None, None, None]

    def on_tick(self, provider, tick) -> float: 
         self.prices[provider] = (tick.ask + tick.bid) / 2.
         return mean(self.prices)

Code must be included with your submitted response that produces the computational output of your analysis. 

## Task 3