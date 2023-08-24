We are now ready to discuss the optimizer.

Now, I'm sure you are already familiar with the optimizer and have likely used it before, but to really cover all of its nuances, we needed to cover all of the material that we've covered so far.

![](2023-08-15-15-34-09.png)

The optimizer will do one of two things, depending on what you optimize for.

- One is the **deployment size** of the contract, and
- The other one is how expensive it will be to **run a particular function** after the contract is deployed.

Here's the relevant part from the solidity documentation.

The **number of runs** specifies roughly how often each opcode of the deployed contract will be executed across the lifetime of the contract.
  
This means it is a **tradeoff** parameter between **code size** and **code execution cost**.

A "runs" parameter of **1** will produce **short but expensive code**.

In contrast, a larger "runs" parameter will produce longer but more gas efficient code.

The **maximum value** for the parameter is **2 power to 32 minus one** (**2³² - 1**).

First, let's understand what is meant by the deploy cost.

A smart contract on the Etherium is really just a **long sequence of bits**.

![](2023-08-15-15-39-45.png)

And on the screen here, it's represented as **hexadecimal**.

This is the `DoNothing()` function from earlier.

So remember when we were looking at `push1 0x80`, `push1 0x40` and `mstore` `pus1h` for `calldatasize`.

![](2023-08-15-15-43-18.png)

But what's actually stored on the blockchain is this we can actually see that this

![](2023-08-15-15-45-31.png)

`60` corresponds to `push1` this `80` corresponds to this `0x80` over here.

And this `40` corresponds to the `0x40` over here.

And `52` corresponds to `mstore`.

![](2023-08-15-15-48-00.png)

So remember this table saying `mstore` has the **opcode** of `52`.

![](2023-08-15-15-49-50.png)

So the **more opcodes** that you have, the **longer** that this this byte string is going to be and the **more expensive** it is going **to be to deploy it**.

**So let's see that cost in action with the help of the optimizer**.

I've created a coin named after myself over here that I'm going to deploy.

![](2023-08-15-15-50-46.png)

**First**, I'm going to **turn off** the **optimizer**.

![](2023-08-15-15-51-36.png)

Then I'm going to compile the contract.

And then I'm going to deploy it.

But I'm not.

I'm going to attempt to deploy it to the **Rinkeby Test Network** so that **Metamask** will tell me how big it actually is.

So when I hit deploy.

![](2023-08-15-15-53-52.png)

And I look at the data that's actually being sent, it says that there are **6160 bytes** that would be stored on the blockchain if we were to deploy this **ERC20 token**.

Okay, that's a lot of bytes and we have to pay gas for each one.

So you can imagine that deploying a smart contract can be quite expensive.

I'm sure you know this from experience.

**Now** let's turn the **optimizer on** and set it to **200**.

![](2023-08-15-16-10-28.png)

This is the **default value** actually. So I compile and then I deploy.

And now I see that the bytes has dropped all the way down to **2919 bytes**.

Well, that's a lot of savings.

Whatever the gas costs it was earlier, this is **less than half** of it.

Okay, that's pretty cool.

Well, what will happen if I set the optimizer to **10,000** ?

![](2023-08-15-16-11-37.png)

Now it's going to be **3587 bytes**.

The interesting thing here is that when **we increased the optimizer runs** the size of the smart contract, the **deployment size** actually **went up**.

That is because the more runs you set for the optimizer, **it's optimizing for execution cost** and **not for code size**, which would be the deploy cost.

Okay.

If it costs us more to deploy with 10,000 runs instead of 200 runs, why would we ever pick 10,000 runs?

Well, there's the **deployment cost** and then there's the **execution cost**.

Let's see how much a **ERC20 transfer** is going to cost us **under** each of these **three circumstances**.

So for that, I'm just going to deploy it to the local environment and I'm going to turn off the optimizer.

So I compile and I deploy.

Now this is **programmed to mint 100 coins** to the address that deployed it.

So when I actually try to interact with the smart contract, what I'm going to do here is transfer.

Well, first of all, let's get my account balance so that I know how much to transfer.

I have this many remember that there's 18 decimals after this.

So that's why this number looks like it's a lot more than **100**.

So I'm going to transfer it.

I'm sorry.

I'm going to set the amount to this, and then I'm going to pick another address that I can transfer to.

And then I'm going to transfer the gas cost.

Here was **47,605**.

So for transfer with no optimization, it's this cost.

Okay.

Now, let's look at the circumstance where we enable optimization.

But set it to **200**.

So we compile this and we deploy it and we get our balance.

We'll get the other address and put it in here.

In this situation, it costs us **46,814 gas**.

So that's an improvement to speed things up.

I'm just going to copy these values and redeploy this contract so that we can see what happens when the optimizer is set to 10,000.

Okay, set the optimizer to **10,000**.

Compile it, get rid of the old one, deploy and transfer to the other address for this amount.

In this situation, we can see that the gas cost went down again.

With **10,000 runs**, we saved a little **over 100 gas**.

![](2023-08-15-16-18-48.png)

Now, what you should do when you're deploying your own contracts is figure out how high you can go until this number stops improving **for the relevant functions for a very heavily used DeFi app that has a lot of code in it**.

Suddenly optimizer quite high can be very beneficial.

So this is the **Uniswap V3 router** and you can see that they've **set** it to **1 million**.

![](2023-08-15-16-21-42.png)

That's because they correctly predicted that it would be used **5 million times** or **millions of times**.

![](2023-08-15-16-22-27.png)

So the higher you set the number, the better.

By default, most software like **HardHat** or **Remix** sets the **default to 200**, which it's reasonable if you want to cut down on the deployment costs.

But your users are going to be less happy because you're making your deployment cost cheaper, but making the long term cost for your users more expensive.

So it's actually a pretty **sad state of the blockchain**.

That 200 is the default because there's a lot of gas that could otherwise have been saved that isn't being saved just because the wrong default is being supplied, in my opinion.

So the take away from this is set the optimizer level as high as possible until you start seeing improvement and you should really only set it to a lower value if you're very sensitive to the deployment cost.