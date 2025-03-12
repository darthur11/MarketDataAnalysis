# MarketDataAnalysis


## Task 1
Link: [Analysis](Analysis.ipynb).

Please find provided three price series for the same underlying instrument from three different sources. Analyse these price series and provide an assessment as to which source is better for a broker to use. The analysis should have a clear and structured explanation of the methodology/metrics used for your comparison, as well as reasoning why you have chosen this/these methodology/methodologies and the results of the analysis. 


## Task 2
Link: [Model](Final_model.ipynb).

Using the same price series provided create a new synthetic mid-price series that improves/tries to deal with the issues identified. Your methodology should only use data available as of that point in time (no forward-looking bias). Implement your model using an event driven approach. Show how the model improves the metrics you defined above

For example the below pseudo code could be used to calculate the simple mean between the three sources based on the latest available data: 

class Model: 
    prices = [None, None, None]

    def on_tick(self, provider, tick) -> float: 
         self.prices[provider] = (tick.ask + tick.bid) / 2.
         return mean(self.prices)

## Task 3
Link: [Statistics](Statistics.ipynb).

### №1
X,Y are a Rundom Variables taken from Normal Distribution: ```X ~ N(e1,q1^2) , Y ~ N(e2,q2^2)```

```
corr(X,Y) = p
S = aX + bY (a and b - const)
(a+b = 1 , 0<=a<=1, 0<=b<=1 )
```
What 'a' and 'b' should be chosen in order to minimise var[S] ?

Write analytical AND numerical solutions to this problem using Jupyter Notebook

### №2
Write a Monte-Carlo Algorithm for price simulation

Option parameters:

Strike = 1000
Implied Volatility = 0.3
Time to Expiration = Half a Year
interest rate = 0
Monte-Carlo parameters:

Start Spot price = 1000
Realised Volatility = 0.2
Number of Paths = 50000
Number of Steps = N days untill the expiration
Use the generated paths for numerical pricing of option using Delta Hedging (ignorring the commisions) and estimate the PNL from purchasing the above option and Delta Hedging it untill the expiration at each step of the path. The final solution should include generated paths, PNL and time of execution of the above procedures, all of which should be in one cell.

P.S Prioritize the correctnes of the calculations over speed, but the faster the algo the better.

### №3
You are given random variables from a Normal Distribution : ```X ~ N(mu,s), mu= 0 , s - ?```

Suppose that random variables are equivalent to daily log-returns of the stock

Mean Average Deviation of X = 1%

what is the yearly Standard Deviation of X ?