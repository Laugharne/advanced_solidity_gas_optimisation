https://www.udemy.com/course/advanced-solidity-understanding-and-optimizing-gas-costs/learn/lecture/31856000#overview


To help you get a better intuition about what all of those gas prices are from the smart contract interactions we looked at earlier in terms of dollars.

Let's look at the formula again and calculate the transaction fee.

So the amount in dollars that you are going to pay for a particular Ethereum transaction will be the gas cost times the gas price times the ether price and divided by 1 billion.

And remember, we got this gas cost by looking at etherscan.

We got this gas price just by well, looking at what the gas price was at the time of the transaction.

But if we want to know what it is right now, we can just look it up on a website that provides the information like here.

And we can see that it's about 27 to 29 gwei right now.

So the ether price is something we can look up on our favorite financial website, whatever that is.

And let's see how much these transactions would cost if we were to execute them right now.

So right now, Ethereum is roughly $3,000 and the gas price is 29 gwei.

So if I was to do an ether transaction at the moment that prices were these values, then it would cost 1.80 $0.03.

Minting NFT like the board ape would cost $15 and using one of these defi applications would cost between nine and $85.

Now, at sometime in late 2021, when Ethereum was around $4,000 and the network was under heavy use

and could sometimes hit 200 gwei pretty commonly the prices looked more like this.

And these may be numbers that some of you are familiar with.

Oh, yes, I remember minting and left for $100 or so.

That makes sense, right?

And if you've been using a theory for a long time and remember the days when it only costs $200 and gas price was, let's say, maybe 20 gwei or so, then the Ethereum transfer would cost $0.08.

So that's how you can see where these numbers are coming from.

The gas cost of Ethereum transfer hasn't changed.

It's been 21,000 this whole time, but the transaction fee changes pretty dramatically depending on what the demand for gas is at the time and with the Ethereum prices.

So look, when Ethereum price goes from 200 to let's say 2000, then the transaction fee goes from $0.08 to $0.84.

And during a time of congestion, when this area of network can hit 100 gwei pretty easily, then it goes from $0.84 to $4.

In my experience, this gas price is the most volatile variable of all of them because it can be as low as 15 gwei at nighttime when people are not using it to as high as 200 or so.

And that causes, well, let's see, the before and after.

So during a calm period, it's about 15 gwei.

So even at, let's say, current prices, it can cost less than a dollar to transfer Ethereum.

But if there's a network surge, then that's going to jump from the ether.

Transfer will jump from $1 and the cost from $7 all the way up to $12 and $100.

But that's not to undermine the purpose of this course.

We can't just hope that the gas prices lower if hope is not a strategy.

Right.

We want to look at how can we make these numbers lower because this can still lead to a lot of savings for our users.

Let's say we're under a congested period and we have an NFT contract that costs 173 guestimate.

Well, what if we could lower it to 100 gas, which is quite doable.

Then the transaction fee would drop from $104.

It was $60.

That's $40 of savings, which is quite substantial.

