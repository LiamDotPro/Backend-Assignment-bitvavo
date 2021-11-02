## Welcome to your backend assignment

In this assignment you will be working on creating quotes for the most popular cryptocurrency on the planet Bitcoin. Alongside creating the functionality to find the current up to date prices you will be working with the bitvavo websocket api and an orderbook.

Before we give you the requirements for the functionality it's important to look at which technologies we are expecting you to use:

- Typescript (If this is your first time, we're not expecting anything advanced)
- A database of your choice (SQL, NoSQL) (We suggest including a docker-compose that makes this simple to run or using inmemory)

- Serverless Framework & plugins (We suggest using `serverless-offline` for developing locally, https://www.serverless.com/)
or
- Kubernetes Cluster (Should be runnable using a local cluster)


We're expecting most candidates to be comfortable using REST, although projects which use graphql will be weighted higher.

Other than the above technologies that are a hard requirements you may also use other libraries too make the job simpler, though we will ask you to justify there use later.

When construing your solution we expect minimal comments, your code should be formatted in a simple to read manner (maybe consider a linter) and be simple to understand from just following the code through. Please make sure you only submit code which you consider to be production ready, code which has obvious flaws will work directly against you, less code which is written well is simpler for us to review and makes you look better.

#### Requirements

1# Endpoint

name: getQuote 

method: Get/Query

data:
```
marketName=BTC-EUR | market identifer
buyOrSell=Buy | Buy or sell in euros
amount=100 | Amount in euros
```

The `getQuote` endpoint should perform a market order on either side of the book passed (Buy/Sell). Following calculating the price, the quote should be saved to the database for endpoint 2.

To make this assignment simple we will always consider the amount passed too the endpoint too be in euros, so if we are buying BTC we are buying 100 euros of btc and selling 100 euros of btc.

here's a checklist, This endpoint should perform the following functionality:

- [] Should gather the latest order book
- [] Should calculate the correct value given a market, side and amount
- [] Should save the quote to a database for later (market, buy, amount, quoteAmount, timeCreated)
- [] Should work for other markets listed on the bitvavo website (https://bitvavo.com/en/markets)
- [] Should return the correct amount in either crypto or fiat.

Optionally projects which incorporate the correct fee of 0.25% into the quote calculation will be scored higher.

Api Link:
https://docs.bitvavo.com/#tag/Market-Data/paths/~1{market}~1book/get

----

2# Endpoint

name: listRecentQuotes

method: Post/Mutation

data:
```
timeAfter=1635866270 | A unix timestamp representing time to filter by
```

The `listRecentQuotes` endpoint should return a list representing all the quotes in the database when queried without any additional data. When a user passes the `timeAfter` in we should only return quotes that come after this date and time.

here's a checklist, This endpoint should perform the following functionality:

- [] Should return all quotes when no data is passed to the endpoint
- [] Should return all data after the timestamp passed in with `timeAfter`

## Conclusion

To conclude if you have any issues during this assignment or something isn't working please let us know, and we will do our best to help you out. Furthermore, if you choose to make use of other technologies other than the ones mentioned above can you please write some notes justifying there use and why they make your soloution better.

Once you are happy that your solution provides all the functionality mentioned above and can be run please send over a link to liam@bitvavo.com alongside instructions for running the project, and we will review your solution.

Thanks for taking the time to complete our assignment 🚀