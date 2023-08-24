In this video, we're going to be looking at how much the data portion of a transaction costs in terms of gas.

When we do a simple transaction that has no data inside of it, it will cost us 21,000 gas.

So in here, over here.

I just sent some ether to myself.

Now, remember that data field I was filling out from earlier?

If I were to put **one byte** of all zeros (`0x00`) in there, the gas cost actually goes up to **21,004 gas**.

Let's look at another situation.

I'm going to send Ether to myself again, but put a **byte of one** (`0x01`) in there and that costs **16 gas** just by way of review.

This is how we would do it.

I would just send it to myself and let's get that out from there and send it.

And I can just do something like this, like this, and send it.

This is what I was doing last time when I was trying to interact with the smart contract.

**So how come a zero byte cost for gas and a non-zero byte cost 16 gas?**

Well, that's what's given in the **yellow paper**.
https://ethereum.github.io/yellowpaper/paper.pdf
  
Now, I don't want to go over the yellow paper too much because it's frankly quite hard to read.

But sometimes you can pick out the pieces of information that are relevant when you really need to dive into something.

So this is from transaction data.

![](2023-08-03-15-20-35.png)

If it's a **zero**, we're **going to pay for gas**.

If it's **non-zero**, it's **16 gas**.

So when we are sending that function from earlier here, we're sending **four bytes** and **four** times **16** is **64**.

And we can see that here.

Remember, the up codes cost us 65 gas and the transaction costs 21,000 gas and the transaction data is 64 gas.

So now we're closer to our target that we measured in **Remix** and on **Etherscan**.

This is **21,129 gas**.

It's not quite where we need to be.

There's still nine more missing gas, but we're getting close.

The way we computed the gas costs that are attributed to the data portion of a transaction will actually give you a hint about how you can save gas that way.

But that's a topic for a later section.

In the next video, we're going to figure out where that missing line gas is.