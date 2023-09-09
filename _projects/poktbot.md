---
layout: page
title: PoktBot
description: A Telegram bot for tracking Pocket Network nodes and staking rewards
img: assets/img/poktbot_logo.png
importance: 1
category: Cryptocurrencies
featured: true
---

PoktBot is a Telegram bot designed to help with the daily tracking of Pocket Network nodes and their staking rewards. It offers extensive configurability, allowing users to monitor multiple nodes simultaneously, generate reward graphs/reports, and receive notifications based on detected errors and status changes, among other features.

## Features

* Provides an easy way to monitor Pocket Network validator nodes' status.
  * Error monitoring and notifications.
  ![Cert-expiration](https://raw.githubusercontent.com/cryptonglab/poktbot/v0.1.3/docs/images/certificate_expiration_min.png)
  * Staking monitoring and notifications.
  ![Begin-unstake](https://raw.githubusercontent.com/cryptonglab/poktbot/v0.1.3/docs/images/begin_unstake_min.png)

* Offers useful stats about node rewards and performance.
  * Daily rewards.
  * Monthly rewards.
  * Graph of rewards evolution.
  ![Stats-result](https://raw.githubusercontent.com/cryptonglab/poktbot/v0.1.3/docs/images/stats.png)

* Supports multi-node and multi-user access.
  * Provides average stats for all configured nodes.
  * Implements a robust RBAC system with two user levels:
    * Investor, with access to view statistics of validators.
    * Admin, with the same permissions as an Investor plus the ability to add/remove admins, investors, and nodes.

* Generates economic reports for tracking node economics or tax filing.
  ![Balances](https://raw.githubusercontent.com/cryptonglab/poktbot/v0.1.3/docs/images/balances.png)

* Fully configurable behavior. Every aspect of the bot is customizable with a configuration file, and some options are configurable through the bot interface itself.


## REFERENCES

You can find this project's website at the following links:

 * Source code: [GitHub](https://github.com/cryptonglab/poktbot/)
 * PyPI Package: [PyPI](https://pypi.org/project/poktbot/)
