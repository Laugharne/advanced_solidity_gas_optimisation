
What I've done here is take the op codes from the contract and copy them into this spreadsheet.

So you would be able to see those over here.

And I can copy it and put it over there.

Again, I'm skipping the constructor portion of the OP codes and just looking at the execution part.

**So remember, not all of the OP codes we got actually get executed because for the successful case, the revert up code and those leading up to it are not actually executed.**

![](2023-08-03-14-42-34.png)

So what I'm going to do is just go through the debugger again and see the options that are executed.

And I've pre-populated this with the gas cost that you can get from **Remix** or from the **specifications on Etherium**.

So we have a `PUSH1 80`, `PUSH1 40` and `MSTORE`, `PUSH1 4`, check the `call data size` `less than (LT)` push a possible location to jump to.

Don't jump to it.

Push zero.

Call data.

Load.

Basically, load up the function selector and check that it is equal.

And if it is, then we will go to the function location and stop.

These are the ones that actually get executed.

You can work this out yourself if you care to, but I don't want to do too much accounti  ng on a video because that's not very exciting to watch.

If we add this up, we get **65**, which at this point in time doesn't make sense because we know it costs **21,000 gas** to start a transaction.

And that means we would expect the total gas cost to be **21,065**.

But it isn't.

We've been seeing (in etherscan) that it's **21,138**.

So we have to account for how much missing gas we have to do.

**73** gas that is unaccounted for.

Now, there are actually two reasons this is not adding up.

- One is you'll note that this information that is on **Etherscan**, this is **stored on the blockchain forever**.  When we send this transaction.
So we **need to pay a fee** for storing it.

- And the other thing that we're going to be looking at, is these memory instructions from earlier, the `PUSH1 80, PUSH1 40, MSTORE`.

So this is actually using some **memory** on the **VM clients** and **we have to pay for** that.

We'll calculate the exact cost for those in the following videos.