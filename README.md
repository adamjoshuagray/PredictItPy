# PredictItPy
This is a very light wrapper around the PredictIt.org market data api.

## Example

```python

market = get_market('DNOM16')
sanders = get_contract(market, 'SANDERS.DNOM16')
clinton = get_contract(market, 'CLINTON.DNOM16')

timestamp = get_timestamp(market)
```

`get_market` will return a dict which contains data on all contracts in the given market. Then `get_contract` 
will extract the data for a given contract. `get_timestamp` will get a datetime.datetime of the timestamp
associated with the market data.

You should expect `get_market` to return a dict which looks like:
```python
    {
        u'Status': u'Open',
        u'Name': u'Who will win the 2016 Democratic presidential nomination?', 
        u'URL': u'...', 
        u'TimeStamp': u'2016-04-06T11:52:07.2347221', 
        u'Image': u'...', 
        u'Contracts': [ ... ]
    }
```

and you should expect `get_contract` to return a dict which looks like:
```python
    {
        u'Status': u'Open', 
        u'Name': u'Hillary Clinton', 
        u'URL': u'...', 
        u'Image': u'...', 
        u'LastTradePrice': 0.83, 
        u'BestBuyYesCost': 0.84, 
        u'BestBuyNoCost': 0.17, 
        u'BestSellYesCost': 0.83, 
        u'DateEnd': u'2016-09-15T00:00:00', 
        u'BestSellNoCost': 0.16, 
        u'LongName': u'Will Hillary Clinton win the 2016 Democratic presidential nomination? ', 
        u'ShortName': u'Clinton', 
        u'ID': 435, 
        u'TickerSymbol': u'CLINTON.DNOM16', 
        u'LastClosePrice': 0.82
    }
```

## Installation

```
    pip install predictitpy
```