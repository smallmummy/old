---
layout:     post
title:      Cryptocurrency Triangle Arbitrage
subtitle:   seek the arbitrage chances between 3 pairs of trading
date:       2018-04-01
author:     Vincent C
header-img: img/post-bg-hacker.jpg
catalog: true
stickie: true
tags:
    - cryptocurrency
    - arbitrage
---  
  
# Cryptocurrency Triangle Arbitrage

## Foreword

No matter in traditional markets or cryptocurrency exchanges, this isnt new things. The concept is simple, however the actual difficulties are in the implementation.

This article just clarify the mechanism and list some formulas to demonstrate the whole process instead of listing the process and code of implementation.

## 1. Brief of the mechanism

### 1.1 Gist

The chances of arbitrage were casued by the unreasonable quotation. 

That's what we need to seek in the markets.

### 1.2 Portal
if you want to skip the wordy deduction process, [click here to teleport to Final Model](#model) 

### 1.3 Similar Sample

To clarify the mechanism distinctly, I use a similar sample as a analogy, and I know there is somethings looks weird in the sample, but just please focus the key points to process. So dont ask me where you can buy such big watermelon using 1 USD, I dont know neither.

We assume there is a "Weird Markets" like this:

![](https://cl.ly/abf2f7600fb7/Image%2525202019-08-17%252520at%2525203.13.20%252520%2525E4%2525B8%25258B%2525E5%25258D%252588.png)
<center><div style="border-bottom: 1px solid #d9d9d9;display: inline-block;color: #999;">
Figure: Weird Markets</div></center>
<br/>

There are 3 stalls which could exchange things by two-ways:

1. Tomato Stall: you can buy 4 tomatoes with 1 USD, also you can sell 4 tomatoes with 1 USD.
1. Melon Stall: you can buy 1 melon with 1 USD, and same to sell.
1. No Cash Stall: there is no cash trading in this stall. But you can exchange 4 tomatoes and 1 melon with each other.

One day, the owner of Tomato Stall changes the price: now you can buy or sell 4 tomatoes with 1 USD. That caused the unreasonable quotation. Assuming you found it and begin to perform the arbitrage with 1 USD following the process:

![](https://cl.ly/06c2bd36ee84/Image%2525202019-08-17%252520at%2525203.14.10%252520%2525E4%2525B8%25258B%2525E5%25258D%252588.png)
<center><div style="border-bottom: 1px solid #d9d9d9;display: inline-block;color: #999;">
Figure: simple positive arbitrage</div></center>
<br/>

1. Buy a melon with 1 USD in Melon Stall
1. Exchanges 4 tomatoes with a melon in No Cash Stall
1. Sell 4 tomatoes with 2 USD in Tomato Stall

We can call this arbitrage process as positive arbitrage, as the direction of arrows in the above figure went in clock-wise.

Might you already think out there is inverse arbitrage as well, as the arrows goes in anti clock-wise. Here is it:

![](https://cl.ly/8bb66d005374/Image%2525202019-08-17%252520at%2525203.14.47%252520%2525E4%2525B8%25258B%2525E5%25258D%252588.png)
<center><div style="border-bottom: 1px solid #d9d9d9;display: inline-block;color: #999;">
Figure: process of inverse arbitrage</div></center>
<br/>

In this time, the owner who change the price of one Melon to 2 USD caused the unreasonable quotation. Then we can:

1. Buy 4 tomatoes with 1 USD in Tomato Stall
1. Exchange a melon with 4 tomatoes in No Cash Stall
1. Sell a melon with 2 USD in Melon Stall


**Note:**

* The name of "positive arbitrage" and "inverse arbitrage", which just differ the process on the name, doesnt matter with the actual process. You also can call the anti clock-wise as positive arbitrage, if you want.

### 1.4 Sample of cryptocurrency

As we changes those 3 stall in the above sample to real trading pair, such as "BTC / USD", "ETH / USD" and "BTC / ETH", the actual model was shown as:

![](https://cl.ly/be4ecb96b34f/Image%2525202019-08-17%252520at%2525203.12.34%252520%2525E4%2525B8%25258B%2525E5%25258D%252588.png)
<center><div style="border-bottom: 1px solid #d9d9d9;display: inline-block;color: #999;">
Figure: sample of cryptocurrency markets</div></center>
<br/>

The trading pairs like stalls in above sample and the cryptocurrencies like the goods in the stalls. Regarding the mapping, it's up to you. You can regards the USD as the money what you final gain after arbitrage, either BTC or ETH, that depends on your arbitrage process and your initial capital.

Back to the gist, the chances were casued by the unreasonable quotation. Hence, we need focus on those bid price and ask price of different trading pairs, to seek a chance, maybe within a nanosecond.

![](https://cl.ly/69866e3f4bf0/Image%2525202019-08-14%252520at%2525209.23.19%252520%2525E4%2525B8%25258B%2525E5%25258D%252588.png)
<center><div style="border-bottom: 1px solid #d9d9d9;display: inline-block;color: #999;">
Figure: price and amount in the order</div></center>
<br/>

## 2. Seeking unreasonable quotation

### 2.1 Variables impact to unreasonable quotation

The prices and amounts of each trading pair obviously are the key variables which definitely impact to unreasonable quotation. 

In the common, there are many gears for each trading pairs in most exchanges, some are  10 gears, while some are up to 50 gears. However, we needn't too much gear but the the first, that's because the price of first gear is nearest with dealmaker price. So for the distinct demonstration, we use the first price and amount of each trading paris to calculate.

**Note:**

for the perfect consideration, we can't only use the price and amount of first gear to process. Especially in the case when the price of first gear is suitable and the amount is too small to deal, but the price of second gear is suitable as well. I will discuss this case in the later part.

![](https://cl.ly/f6ed9361fb08/Image%2525202019-08-17%252520at%2525203.53.11%252520%2525E4%2525B8%25258B%2525E5%25258D%252588.png)
<center><div style="border-bottom: 1px solid #d9d9d9;display: inline-block;color: #999;">
Figure: Variables impact to unreasonable quotation</div></center>
<br/>

### 2.2 Positive Arbitrage

#### 2.2.1 Flow Chart

![](https://cl.ly/b1fb3cef0832/Image%2525202019-08-18%252520at%2525204.26.49%252520%2525E4%2525B8%25258B%2525E5%25258D%252588.png)
<center><div style="border-bottom: 1px solid #d9d9d9;display: inline-block;color: #999;">
Figure: Flow Chart of Positive Arbitrage</div></center>
<br/>

#### 2.2.2 Background

1. you have keep a certain quantity of Mid Currency as initial capital to start the arbitrage.
1. Though the initial capitial is Mid Currency, the initial variable which can define the quantitative currency to initiate is the amount of Base Currency, instead of how much Mid Currency you have. The reason is that would be easy to calcuate, which will be mentioned in later part.
1. in the arbitrage process, we trade as taker instead of maker, so means there is a certain fee during the trade following the convention of most of exchanges. In most of exchanges, the fee for maker is same for all trading pair. However some exchanges gave low or even free free for a certain trading pair, so it's better for us to remarked separately as: 
$$ Fee_{base\_mid} , Fee_{base\_quote} , Fee_{quote\_mid} $$


#### 2.2.3 Process

1. To buy Base Currency, the amount is \\(Base\\_amt\\). the Cost is selling \\(Mid\\_amt\\_init\\) Mid Currency
1. Selling all Base Currency which you bought in previous step, then you gain some Quote Currency, the amount is \\(Quote\\_amt\\)
1. Selling all Quote Currency which you gained in previous step, then you retrieve the Mid Currency, the amount is \\(Mid\\_amt\\_final\\)

#### 2.2.4 Threshold 
As long as the \\(Mid\\_amt\\_final\\) is greater than \\(Mid\\_amt\\_init\\), that's the unreasonable quotation we shoulld garb.

#### 2.2.5 Formula

initial variable: how much we should trade the Base Currency, which is remarked by:

$$ Base\_amt $$

the cost in step 1 after you sell the Mid Currency, which means how much Mid Currency you spend to buy Base Currency:

$$ Mid\_amt\_init = \frac{Base\_amt * Base\_Mid_{sell\_price}}{1-Fee_{base\_mid}} $$

the amount of Quote Currency after you sold the Base Currency in step 2:

$$ Quote\_amt = Base\_amt * Base\_Quote_{buy\_price} * (1-Fee_{base\_quote}) $$

the amount of Mid Currency you retrieved in step 3:

$$ Mid\_amt\_final = Quote\_amt * Quote\_Mid_{buy\_price} * (1-Fee_{quote\_mid})  $$

the profit after one circulation:

$$ Profit =  Mid\_amt\_final - Mid\_amt\_init $$

substitue all variables and get the final expression:

$$ Profit = Base\_amt * [ Base\_Quote_{buy\_price} * Quote\_Mid_{buy\_price} * (1-Fee_{base\_quote}) * (1-Fee_{quote\_mid}) - \frac{Base\_Mid_{sell\_price}}{1-Fee_{base\_mid}} ] $$

Threshold which makes profit:

$$ Base\_Quote_{buy\_price} * Quote\_Mid_{buy\_price} * (1-Fee_{base\_quote}) * (1-Fee_{quote\_mid}) - \frac{Base\_Mid_{sell\_price}}{1-Fee_{base\_mid}} > 0 $$

#### 2.2.6 Limit of amount in trade

From the above formula of profit, you may realize the value of \\( Base\\_amt \\) is the limit which impact the final profit we gain. So in this part, let's find out what's the value of  \\( Base\\_amt \\).

##### 2.2.6.1 the stock how much you can take

For analogy, let's back to the weird stall: after you detect the unreasonable quotation, in this time, you plan to use 2 USD as initial capital, so you could make 2 USD to 4 USD. However when you're ready to buy 2 melon using 2 USD in Melon Stall, there is just 1 melon in stock. so the limit of amount during the whole process emerges, which might be your initial capital, either the stock in a certain stall (the amount in the order of certain trading pair)

![](https://cl.ly/a624a2f9fc97/Image%2525202019-08-18%252520at%2525208.22.07%252520%2525E4%2525B8%25258B%2525E5%25258D%252588.png)
<center><div style="border-bottom: 1px solid #d9d9d9;display: inline-block;color: #999;">
Figure: the stock might impact the whole process</div></center>
<br/>

the stock in the above fruit stall equals the amount hang out in bid and ask order. I already mentioned that we just focus on the first gear of each trading pair, that means the amount of first gear is the limit, because that's the all we can take from that order. If we taker more, then the excessive part will be charged in the different price.

in the positive arbitrage, we measured the initial variable is \\( Base\\_amt \\). so later we ought to standardize on the amount of Base Currency. 

check the following figure, there 3 limits amount in 3 trading pairs:

![](https://cl.ly/4b9aec39f349/Image%2525202019-08-18%252520at%2525208.45.00%252520%2525E4%2525B8%25258B%2525E5%25258D%252588.png)
<center><div style="border-bottom: 1px solid #d9d9d9;display: inline-block;color: #999;">
Figure: limit of variables impact to positive arbitrage (Part 1)</div></center>
<br/>

1. \\( Base\\\_Mid_{sell\\\_amt} \\)

	this's the amount of Base Currency, no need convert.

2. \\( Base\\\_Quote_{buy\\\_amt} \\)

	this's the amount of Base Currency, no need convert.

3. \\( Quote\\\_Mid_{buy\\\_amt} \\)
	this's the amount of Quote Currency, so need to covert to the amount of Base Currency:
	
	$$ \frac{Quote\_Mid_{buy\_amt}}{Base\_Quote_{sell\_price}} $$


##### 2.2.6.2 the money in wallet how much you can use

if you process the 3 transaction of those 3 trading pairs one by one to accomplish arbitrage, the limit define the money how much you can use is only the initial capital. Because they are in sequence, the initial capital will ensure the amount of each cryptocurrency in each trading pair.

However, there is a truth not only in traditional market, but cryptocurrency: the order hang out in the board is changing in every nanosecond, might it was dealed, either withdrew. To grab the chances, we need take all 3 transactions as quick as possible. Hence we have to process them in parallel, instead of in sequence.

Since all the 3 transactions were processed in the same time, we need prepare the certain amount of each kind of cryptocurrency: Base, Mid and Quote Currency, which will impact the limit of trading amount in the arbitrage.

There are another 3 limits under this parallel architecture:

![](https://cl.ly/80794e919f05/Image%2525202019-08-19%252520at%2525202.45.07%252520%2525E4%2525B8%25258B%2525E5%25258D%252588.png)
<center><div style="border-bottom: 1px solid #d9d9d9;display: inline-block;color: #999;">
Figure: limit of variables impact to positive arbitrage (Part 2)</div></center>
<br/>


1. balance in wallet of Mid Currency: \\( Bal_{mid}\\)

	this's the amount of Mid Currency, so need to convert to Base Currency:
	
	$$ \frac{Bal_{mid}}{Base\_Mid_{sell\_price}}$$

1. balance in wallet of Base Currency: \\( Bal_{base}\\)

	this is the amount of Base Currency, no need to convert.

1. balance in wallet of Quote Currency: \\( Bal_{quote}\\)
	
	this's the amount of Quote Currency, so need to convert to Base Currency:
	
	$$ \frac{Bal_{quote}}{Base\_Quote_{sell\_price}} $$


##### 2.2.6.3 the value of  \\( Base\\\_amt \\)

From the preceding description, there are 6 limits which will impact to the value of  \\( Base\\\_amt \\). They are like 6 pieces of board in a bucket, the value of  \\( Base\\\_amt \\) is the volumn of that bucket. Namely the lenghth of shortest board will decide the volumn, so:

$$ Base\_amt = min(Base\_Mid_{sell\_amt} , Base\_Quote_{buy\_amt} , \frac{Quote\_Mid_{buy\_amt}}{Base\_Quote_{sell\_price}} , \frac{Bal_{mid}}{Base\_Mid_{sell\_price}} , Bal_{base} , \frac{Bal_{quote}}{Base\_Quote_{sell\_price}}) $$

#### 2.2.7 the limit set by exchages
Normally, every exchange would set the minimum trading amount of each trading pair. here we simpyly remark it as \\( MinEx_{base}\\). It wouldn't be allowed if your trading amount is less than this threshold. So later in program, this judgement should be add before arbitrage: 

$$ Base\_amt > MinEx_{base} $$





### 2.3 Inverse Arbitrage

#### 2.3.1 Flow Chart

![](https://cl.ly/2dde1552a145/Image%2525202019-08-18%252520at%2525204.27.28%252520%2525E4%2525B8%25258B%2525E5%25258D%252588.png)
<center><div style="border-bottom: 1px solid #d9d9d9;display: inline-block;color: #999;">
Figure: Flow Chart of Inverse Abritrage</div></center>
<br/>

#### 2.3.2 Background

some with positive arbitrage

#### 2.3.3 Process

1. To buy Quote Currency, the amount is \\(Quote\\\_amt\\). the Cost is selling \\(Mid\\\_amt\\\_init\\) Mid Currency
1. Selling all Quote Currency which you bought in previous step, then you gain some Base Currency, the amount is \\(Base\\\_amt\\)
1. Selling all Base Currency which you gained in previous step, then you retrieve the Mid Currency, the amount is \\(Mid\\\_amt\\\_final\\)

#### 2.3.4 Threshold 
As long as the \\(Mid\\\_amt\\\_final\\) is greater than \\(Mid\\\_amt\\\_init\\), that's the unreasonable quotation we shoulld garb.

#### 2.3.5 Formula

initial variable: how much we should trade the Base Currency, which is remarked by:
$$ Base\_amt $$

the cost in step 1 after you sell the Mid Currency, which means how much Mid Currency you spend to buy Quote Currency:

$$ Mid\_amt\_init = \frac{Quote\_amt * Quote\_Mid_{sell\_price}}{1-Fee_{quote\_mid}} $$

the amount of Base Currency after you sold the Quote Currency in step 2:

$$ Base\_amt = \frac{Quote\_amt * (1-Fee_{base\_quote})}{Base\_Quote_{sell\_price}} $$

the amount of Mid Currency you retrieved in step 3:

$$ Mid\_amt\_final = Base\_amt * Base\_Mid_{buy\_price} * (1-Fee_{base\_mid})  $$

the profit after one circulation:

$$ Profit =  Mid\_amt\_final - Mid\_amt\_init $$

substitue all variables and get the final expression:

$$ Profit =  Quote\_amt * [\frac{Base\_Mid_{buy\_price} * (1-Fee_{base\_mid})* (1-Fee_{base\_quote})}{Base\_Quote_{sell\_price}}  - \frac{Quote\_Mid_{sell\_price}}{1-Fee_{quote\_mid}}] $$

Threshold which makes profit:

$$ \frac{Base\_Mid_{buy\_price} * (1-Fee_{base\_mid})* (1-Fee_{base\_quote})}{Base\_Quote_{sell\_price}}  - \frac{Quote\_Mid_{sell\_price}}{1-Fee_{quote\_mid}} > 0  $$


#### 2.3.6 Limit of amount in trade

From the above formula of profit, you may realize the value of \\( Quote\\\_amt \\) is the limit which impact the final profit we gain. So in this part, let's find out what's the value of  \\( Quote\\\_amt \\).

##### 2.3.6.1 the stock how much you can take

the analysis of inverse arbitrage is similar with that of positive arbitrage.

in the inverse arbitrage, we measured the initial variable is \\( Quote\\\_amt \\). so later we ought to standardize on the amount of Quote Currency. 

check the following figure, there 3 limits amount in 3 trading pairs:

![](https://cl.ly/c40f43c2be64/Image%2525202019-08-19%252520at%2525203.54.36%252520%2525E4%2525B8%25258B%2525E5%25258D%252588.png)
<center><div style="border-bottom: 1px solid #d9d9d9;display: inline-block;color: #999;">
Figure: limit of variables impact to inverse arbitrage (Part 1)</div></center>
<br/>

1. \\( Quote\\\_Mid_{sell\\\_amt} \\)

	this's the amount of Quote Currency, no need to convert.

2. \\( Base\\\_Quote_{sell\\\_amt} \\)

	this's the amount of Base Currency, so need to convert the amount of Quote Currency:
	
	$$ Base\_Quote_{sell\_amt} * Base\_Quote_{buy\_price} $$
	

3. \\( Base\\\_Mid_{buy\\\_amt} \\)
	this's the amount of Base Currency, so need to covert to the amount of Base Currency:
	
	$$ Base\_Mid_{buy\_amt} * Base\_Quote_{buy\_price} $$


##### 2.3.6.2 the money in wallet how much you can use

the analysis of inverse arbitrage is similar with that of positive arbitrage.

There are another 3 limits under this parallel architecture:

![](https://cl.ly/f7fb81a9f09e/Image%2525202019-08-19%252520at%2525203.57.11%252520%2525E4%2525B8%25258B%2525E5%25258D%252588.png)
<center><div style="border-bottom: 1px solid #d9d9d9;display: inline-block;color: #999;">
Figure: limit of variables impact to inverse arbitrage (Part 2)</div></center>
<br/>

1. balance in wallet of Mid Currency: \\( Bal_{mid}\\)

	this's the amount of Mid Currency, so need to convert to Quote Currency:
	
	$$ \frac{Bal_{mid}}{Quote\_Mid_{sell\_price}}$$

1. balance in wallet of Base Currency: \\( Bal_{base}\\)

	this is the amount of Quote Currency, so need to convert to Quote Currency:
	
	$$ Bal_{base} * Base\_Quote_{buy\_price} $$

1. balance in wallet of Quote Currency: \\( Bal_{quote}\\)
	
	this's the amount of Quote Currency, so no need to convert.


##### 2.3.6.3 the value of  $ Quote\\\_amt $

The analysis of inverse arbitrage is similar with that of positive arbitrage, so:

$$ Quote\_amt = min(Quote\_Mid_{sell\_amt} , Base\_Quote_{sell\_amt} * Base\_Quote_{buy\_price} , Base\_Mid_{buy\_amt} * Base\_Quote_{buy\_price} , \frac{Bal_{mid}}{Quote\_Mid_{sell\_price}} , Bal_{base} * Base\_Quote_{buy\_price} , Bal_{quote}) $$

#### 2.3.7 the limit set by exchages
Normally, every exchange would set the minimum trading amount of each trading pair. here we simpyly remark it as \\( MinEx_{quote}\\). It wouldn't be allowed if your trading amount is less than this threshold. So later in program, this judgement should be add before arbitrage: 

$$ Quote\_amt > MinEx_{quote} $$



## 3. <span id = "model">Final Model</span>

### 3.1 Model for positive arbitrage

#### 3.1.1 Occasion
When the following expression is ture, we can perform positive arbitrage:

$$ Base\_Quote_{buy\_price} * Quote\_Mid_{buy\_price} * (1-Fee_{base\_quote}) * (1-Fee_{quote\_mid}) - \frac{Base\_Mid_{sell\_price}}{1-Fee_{base\_mid}} > 0 $$

#### 3.1.2 Profit
The profit after positive arbitrage is:

$$ Profit = Base\_amt * [ Base\_Quote_{buy\_price} * Quote\_Mid_{buy\_price} * (1-Fee_{base\_quote}) * (1-Fee_{quote\_mid}) - \frac{Base\_Mid_{sell\_price}}{1-Fee_{base\_mid}} ] $$

#### 3.1.3 Propelled Quantity of Base Currency 
the value of \\( Base\\\_amt \\) among the above expression is:

$$ Base\_amt = min(Base\_Mid_{sell\_amt} , Base\_Quote_{buy\_amt} , \frac{Quote\_Mid_{buy\_amt}}{Base\_Quote_{sell\_price}} , \frac{Bal_{mid}}{Base\_Mid_{sell\_price}} , Bal_{base} , \frac{Bal_{quote}}{Base\_Quote_{sell\_price}}) $$

#### 3.1.4 Exception when should skip
However here is the exception, which you should skip this time, when:

$$ Base\_amt < MinEx_{base} $$

### 3.2 Model for inverse abritrage

#### 3.2.1 Occasion
when the following expression is ture, we can perform inverse arbitrage:

$$ \frac{Base\_Mid_{buy\_price} * (1-Fee_{base\_mid})* (1-Fee_{base\_quote})}{Base\_Quote_{sell\_price}}  - \frac{Quote\_Mid_{sell\_price}}{1-Fee_{quote\_mid}} > 0 $$

#### 3.2.2 Profit
the profit after inverse arbitrage is:

$$ Profit =  Quote\_amt * [\frac{Base\_Mid_{buy\_price} * (1-Fee_{base\_mid})* (1-Fee_{base\_quote})}{Base\_Quote_{sell\_price}}  - \frac{Quote\_Mid_{sell\_price}}{1-Fee_{quote\_mid}}] $$

#### 3.2.3 Propelled Quantity of Quote Currency
the value of \\( Quote\\\_amt \\) among the above expression is:

$$ Quote\_amt = min(Quote\_Mid_{sell\_amt} , Base\_Quote_{sell\_amt} * Base\_Quote_{buy\_price} , Base\_Mid_{buy\_amt} * Base\_Quote_{buy\_price} , \frac{Bal_{mid}}{Quote\_Mid_{sell\_price}} , Bal_{base} * Base\_Quote_{buy\_price} , Bal_{quote}) $$

#### 3.2.4 Exception when should skip
However here is the exception, which you should skip this time, when:

$$ Quote\_amt < MinEx_{quote} $$



