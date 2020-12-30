---
title: "BeanCount"
date: "2019-07-04"
template: "post"
draft: false
slug: "/posts/BeanCount/"
tags:
  - "accounting"
category: Finance 
layout: layouts/post.njk
description: "PlainTextAccounting.org is amazing.  I'm going to try starting with BeanCount and Fava"
---


## Getting Started
1. `python3 -m venv BCenv`
2. `source BCenv/bin/activate`
3. `pip install fava`


```
(env) mpayne@Payne:/mnt/c/Users/Payne/BeanCount$ nl ledger.beancount
     1  option "title" "Matt Learning Beancount"
     2  option "operating_currency" "USD"
     3  2014-01-01 open Assets:Checking
     4  2014-01-01 open Equity:Opening-Balances

     5  2014-01-02 * "Deposit"
     6    Assets:Checking           100.00 USD
     7    Equity:Opening-Balances
(env) mpayne@Payne:/mnt/c/Users/Payne/BeanCount$
```
```



