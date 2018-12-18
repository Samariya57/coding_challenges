# Background
At **Company** we do a lot of data integration. A simplified example: product specifications might come from one data source, product pricing from another, and product reviews from a third. A major challenge in working with all this data is determining when two pieces of information from disparate data sources are actually talking about the same product. In academic circles this problem is sometimes called Record Linkage, Entity Resolution, Reference Reconciliation, or a host of other fancy terms. We describe this problem very technically as “matching.”

# Challenge

We’ll provide you with a set of products and a set of price listings matching some of those products. The task is to match each listing to the correct product. Precision is critical. We much prefer missed matches (lower recall) over incorrect matches, so try hard to avoid false positives. A single price listing may match at most one product.
Be careful not to tie your logic too tightly to the input data. We will run your solution against both the listings provided in the challenge, and a different set of listings that you don’t get to see ahead of time. No giant if statements tailored exactly to the test data, please!

# How to enter

Complete the challenge in whatever language you like (bonus points for Scala, but not required)
Make sure your output is valid JSON and conforms to our spec
Put the source code for your solution up on your github account
Make it easy for us to run your solution (ideally on Linux)
e.g. “clone my repository and run go.sh”
e.g. If your solution requires Windows, zip up an executable that we can run (one-click, ideally)

# What we are looking for
* Simple and elegant code (readability, maintainability)
* We’ll compare your results to our results
* Precision – do you make (m)any false matches?
* Recall – how many correct matches did you make?
* Efficiency (data structure and algorithm choices)

# Details
The inputs and outputs for the challenge are all text files. Each file has one JSON object per line. The following section describes what those objects look like. 

# Data objects

**Product**
```
{ 
  "product_name": String // A unique id for the product 
  "manufacturer": String 
  "family": String // optional grouping of products 
  "model": String 
  "announced-date": String // ISO-8601 formatted date string, e.g. 2011-04-28T19:00:00.000-05:00 
} 
```

**Listing**

```
{ 
  "title": String // description of product for sale 
  "manufacturer": String // who manufactures the product for sale 
  "currency": String // currency code, e.g. USD, CAD, GBP, etc. 
  "price": String // price, e.g. 19.99, 100.00 
}
```
