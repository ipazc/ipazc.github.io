---
layout: page
title: Nanoblocks
description: A Python Package for Easy Access to NANO Cryptocurrency
img: assets/img/nanoblocks.png
importance: 1
category: Cryptocurrencies
featured: true
---


[nanoblocks](https://nanoblocks.readthedocs.io/en/latest/) is an **unofficial** Python package designed to simplify access to [NANO cryptocurrency](https://nano.org/). It provides an easy interface for developers to interact with the Nano Network, enabling common Nano operations such as creating new wallets and accounts, checking account information, making transactions, and more.

## Installation

`nanoblocks` can be installed via pip:

```bash
pip install nanoblocks
```

## Getting Started

To access the Nano network, follow these steps:

```python
from nanoblocks.network import NanoNetwork

network = NanoNetwork()
network
```

By default, the package uses a public Nano RPC server (mynano.ninja) as the backend, allowing for easy out-of-the-box usage. However, it is highly recommended to run your own Nano node.

You can access accounts on the network as follows:

```python
account = network.accounts["nano_39a73oy5ungrhxy5z5oao1xso4zo7dmgpjd4u74xcrx3r1w6rtazuouw6qfi"]
account  # The Account object contains operations for visualizing information or managing the content
```

Blocks from the ledger can also be accessed:

```python
block = network.blocks["4FEC4BDD078C741F599221C67C8BE6493C872EF9B30968BBF4991640FFF42DA2"]
block  # The Block object is useful to display information of the published block
```

And it also contains a easy-to-use interface to handle wallets:

```python
# To create a new wallet
wallet = network.wallets.create()

# To access an existing wallet by using the 64-Bytes seed:
wallet = network.wallets["7F632A80ECCC54A058602CD64A81D23A6B4D7320562E4767C9EB0BBB1151CDF2"]

# Alternatively, access it with the BIP-39 24 words:
wallet = network.wallets[['legal', 'bone', 'parent', 'sunset', 'shed', 'expand', 'ghost', 'airport', 'stone', 'favorite', 'innocent', 'inquiry', 'regular', 'ridge', 'life', 'shift', 'electric', 'dinner', 'kiss', 'blast', 'rain', 'pottery', 'daughter', 'execute']]

# Wallet information can be printed out
print(wallet.seed)
print(wallet.mnemonic)
```

The package allows to easily interact with the network and publish new blocks in a straight forward way. More information at [readthedocs](https://nanoblocks.readthedocs.io/en/latest/).

## REFERENCES

You can find this project's website at the following links:

 * Source code: [GitHub](https://github.com/ipazc/nanoblocks/)
 * PyPI Package: [PyPI](https://pypi.org/project/nanoblocks/)
 * ReadTheDocs: [readthedocs](https://nanoblocks.readthedocs.io/en/latest/)
 
