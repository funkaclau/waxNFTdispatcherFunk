# waxNFTdispatcher

This library will help you to transfer or to mint NFTs in the WAX blockchain. It relies on the library 
pyntelope for blockchain interaction and on the library loguru for beautiful logs.


## Installation
```poetry add waxNFTdispatcher```

or

```pip install waxNFTdispatcher```

## Usage

```python
from waxNFTdispatcher import AssetSender
import os

private_key = os.environ["PRIVATE_KEY"]
collection_wallet = "mywallet.wam"
collection = "pixeltycoons"
recipient = "recipient.wam"
INPUT = (("rawmaterials", 318738), ("magmaterials", 416529))

# Create object
assetsender = AssetSender(collection, collection_wallet, private_key)

# Try to find assets in the collection wallet to send them.
# If not all needed assets were in the collection wallet, the script will mint the rest.
assetsender.send_or_mint_assets(INPUT, recipient)

# Send assets with given asset ID to the given wallet
assetsender.send_assets(("1099543811405", "1099543811406"), recipient)

# Mint given number of same assets
assetsender.mint_assets("rawmaterials", 318738, "recipient.wam", 5)
```

## Contribution
Contribution is highly welcome. Please send your pull requests or create issues with found bugs and suggestions. 
In your pull requests please use Black formatting.