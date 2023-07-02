# Binance-Trading
Theory and Practice on Crypto Trading

To connect to Binance via Python, you can use the Binance API, which provides a comprehensive set of methods for interacting with the Binance exchange. Here's a step-by-step guide to help you get started:

1. Install the `python-binance` library by running the following command in your terminal:
   ```
   pip install python-binance
   ```

2. Import the necessary libraries and initialize the Binance API client:

```python
from binance.client import Client

# Replace API_KEY and API_SECRET with your own credentials
api_key = 'YOUR_API_KEY'
api_secret = 'YOUR_API_SECRET'

client = Client(api_key, api_secret)
```

3. Start using the Binance API methods. Here are a few examples to get you started:

- Get the latest price of a symbol:

```python
symbol = 'BTCUSDT'  # Replace with the symbol you're interested in
ticker = client.get_symbol_ticker(symbol=symbol)
latest_price = ticker['price']
print(f"Latest price of {symbol}: {latest_price}")
```

- Get account information:

```python
account_info = client.get_account()
balances = account_info['balances']

print("Account Balances:")
for balance in balances:
    asset = balance['asset']
    free = balance['free']
    locked = balance['locked']
    print(f"{asset}: Free: {free}, Locked: {locked}")
```

- Place a market order:

```python
symbol = 'BTCUSDT'  # Replace with the symbol you want to trade
side = 'BUY'  # or 'SELL'
quantity = 0.001  # Replace with the quantity you want to trade

order = client.create_order(
    symbol=symbol,
    side=side,
    type=Client.ORDER_TYPE_MARKET,
    quantity=quantity
)

print(f"Placed {side} order for {quantity} {symbol}")
```

These are just a few examples of what you can do with the Binance API using Python. Refer to the Binance API documentation for more details on available methods and their parameters: https://binance-docs.github.io/apidocs/spot/en/

Remember to handle exceptions and error cases appropriately in your code. Additionally, make sure to keep your API credentials secure and never share them publicly.

