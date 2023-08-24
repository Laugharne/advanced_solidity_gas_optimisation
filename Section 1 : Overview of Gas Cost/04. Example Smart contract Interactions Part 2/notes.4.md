https://www.udemy.com/course/advanced-solidity-understanding-and-optimizing-gas-costs/learn/lecture/31856280#overview

Martin to note that the same transaction on the same smart contract will not always have exactly the same gas cost.

I'm looking again here at the Usdc coin erc20 smart contract.

And in this particular example, it cost 65,000 gas to execute a transfer.

In the previous video, it cost 60,000 gas.

Now I'm going to look again at the open see smart contract.

And in a previous video, we saw a purchase that cost 240,000 gas and in this video costs 194,000 gas.

Why do these variations happen?

Well, this is something I'm obviously going to explain later in the course.

But when you are conducting a transaction on Etherium, even if it's with the same method, on the same smart contract, the exact computation that is carried out is not 100% identical all of the time.

The same protocol, but a different implementation will often have a different cost.

Over here I'm looking at the Xen NFT and in this example it costs 104,000 gas to mint.

We saw in the previous video that bought a yacht club another 721 cost 174,000 gas payment.

In this case, it's because the implementation of minting in these smart contracts is quite different.


```
And in a previous video, we saw a purchase that cost 240,000 gas and in this video costs 194,000 gas.
Why do these variations happen?
Well, this is something I'm obviously going to explain later in the course.
```
