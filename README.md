# Auction-Discount-Index

## Abstract
Housing Market Indicator: Forecasts future housing market movements from median property auction discounts. Discount is defined as final bid price of auctioned property divided by its estimated worth on the conventional market.

The
Essential Information Group (EIG) supplied property auction data for all
properties sold on UK auction houses since 1991. Using the ARME valuation model ([details found in my UK House-Price-Models repository](https://github.com/arashid9-1/UK-House-Price-Models))
property valuations, reflecting potential sale prices on the conventional market at the time of auction, can be estimated for properties in the EIG dataset. Consequently, the Auction Discount Index (ADI) was calculated from 149,000 discount estimates over 324 months.

Toda and Yamamoto’s (1995) Augmented Granger-causality test affirms ADI leads Land Registry's UK HPI by seven months.

***

## Theoretical Background

The Auction Discount Index (ADI) was first conceptualised in a paper from Fathom Consulting (Brigden, 2009). The idea is to map the median discount or premium of auctioned property over time and compare this to movements in the ‘conventional' housing market. The theory predicts that shocks to the value of auctioned property
will foreshadow the trends in the conventional market. Here, the properties that make up the conventional market are bought and sold by private individuals using
estate agents as an intermediary. The key difference between the selling of properties
on the conventional market or by auction is the speed of sale. Auction sellers are
generally either lenders holding repossessed properties or households facing financial
distress [(Corder M., 2010)](https://www.bankofengland.co.uk/-/media/boe/files/quarterly-bulletin/2010/residential-property-auction-prices.pdf). These sellers are willing to sell the property below its
value (at a discount) to get a quick sale. By contrast, conventional property sales may take
months for a transaction to be registered due to buying chains or mortgage approvals
for example. Sellers on the conventional market, not as desperate as auction sellers,
want to maximise their sale price, resulting in a reluctance to readjust their
reservation price to the current market conditions. Therefore, prices adjust faster to
current market conditions on the auction market than the conventional market

The following figure visualises housing market price rigidity. Suppose a negative shock to demand:

![](Figure%201.png)

_Source: Fathom Consulting (2009)_

1.	Housing market at equilibrium point A, where Demand0 meets Supply
2.	Demand shock results in the demand curve shifting inwards from Demand0 to Demand1.
3.	Sellers however initially are unwilling or unable to appropriately adjust prices to market-clearing levels, drying up transactions and resulting in reaching disequilibrium point B.
4.	Eventually sellers are forced to drop the price level, resulting demand meeting the long-run supply curve once again at equilibrium point C.


Hence, properties sales can take months to finalise. Conversely, the price of a property sold at auction is determined at the fall of the hammer. Auction sales proxy the “mark-to-market” price, the value of the property if it was to sell today. As a result, the auction market adjusts faster to market conditions than the conventional property market. If the logic is sound, relative auction market price movements should lead conventional housing market movements.


Hence, properties sales can take months to finalise. Conversely, The price of a property sold atauction is determined at the fall of the hammer. Auction sales proxy the
“mark-to-market” price, the value of the property if it was to sell today. As a result,
the auction market adjusts faster to market conditions than the conventional
property market. If the logic is sound, relative auction market price movements
should lead conventional housing market movements.

***

## The ADI

The Auction Discount Index (ADI) is defined by the monthly median auction
discount from 1996 to 2023. Details on ADI contruction is found in [Section 6.1 of the report](ARME_and_ADI_report.pdf), with the code at the [bottom of supplied the jupyter notebook](appendix_testing_adi.ipynb).  A Five-month moving average was added for
visual tractability. The auction discount generally hovers around 0.75 and 0.8 over
the period shown. 
Looking from left to right, the index steadily rises to peak at 94% in 2004 and 92% in
mid-2007. ADI increases are bullish market signals. Investors, expecting high future
house market returns, flood property auctions to quickly build their portfolios. The
higher demand pushes up auction bids, reducing the relative auction discount. The
Auction Discount Index then plummets to 74% in 2009. Similarly, ADI drops are
bearish signals. As more sellers fail to sell their properties conventionally, the more
properties enter auction houses. The increased supply and seller desperation results
in auction discounts to increase further. From 2009 to 2023 the ADI varies between
0.74 and 0.81.

![](ADI%20image.png)

## Granger-causality

[Toda and Yamamoto's (1995) Granger-causality](https://www.sciencedirect.com/science/article/abs/pii/0304407694016168) test was used to test if lagged values of the ADI can help predict future housing market movements. Details on the full procedure, including the reasons as to why this method was prefered over the standard Granger-causality test can be found in [sections 6.2 and 7.2 of the full report](ARME_and_ADI_report.pdf). UK Land Registry's highly stylised UK HPI is generally seen as the most robust index for investigating national house price levels, and hence was used to measure market movements. 

![](Screenshot%202024-04-01%20at%2007.54.34.png)

Information criterion suggested 7 lags (months) were the most appropriate for conducting the test. Test 1 overwhelmingly rejects the null hypothesis at the 0.01 significance level,
concluding that past values of the ADI, up to 7 months previously, can help predict
future values of HPI. The reverse however is not true looking the results of Test 2.
The results confirm our hypothesis.

Hence, the ADI predicts the current value of UK HPI better than when only
using lags of UK HPI.

## Limitations and Future Research

1. The ARME model can only estimate the worth of properties listed in the HM Land Registry Price
Paid dataset, a dataset that records all UK property sales on the conventional market since 1996. Most auction sellers probably tried and failed to sell the
property on the conventional market. Therefore, the type of properties sold at
auction are likely distinctly different from those listed on the dataset. 
2. The findings show that the ADI can help forecast future HPI movements but does not quantify the extent of its predictive power.

***
## Contributions 
Eloise Morrison-Clare (Co-Author - University of Bath)

Andrew Brigden (Project Supervisor - Fathom Consulting)
