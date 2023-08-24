https://www.udemy.com/course/advanced-solidity-understanding-and-optimizing-gas-costs/learn/lecture/31856142?start=0#overview


Each of the OP codes that we just looked at is defined inside of the Etherium Yellow Paper.


https://ethereum.github.io/yellowpaper/paper.pdf

And you can see some of the familiar ones here.

We talked about addition and what is this delta and alpha value?

Well, what it's saying is it's going to remove two items from the stack and add one.

Well, it's going to look at the top two values.

When we were adding three and one, take them off of the stack and replace them with the sum.

Another opcode that we saw in our earlier example A s load.

So it took looked at the location on memory and removed it and then replaced it with the value.

I'm sorry.

In storage.

It looked at a location in storage.

Remove that address from the stack and replaced it with the value stored there.

We also saw the push.

Operation Push doesn't remove anything from the stack, it just adds one to them.

Now, this yellow paper is, of course, a little bit hard to read.

You can get a little bit of a lighter version if you look on this page.


https://ethereum.org/en/developers/docs/evm/opcodes/

And here you can see the codes labeled it were the names of the codes given again, the initial stack, the top two items on the stack, A and B and what it gets replaced with in this column.

There's also a column over here that tells us how much each gas operation costs.

So an `ADD` costs **three gas**, a `PUSH` will cost **three gas** and a `SLOAD` actually is a bit **complicated** and we'll get into this later because this cost will vary depending on what you are trying to do.

But if we want to look here, we can say we can see that it will cost either **100 gas** or **2100 gas**.

[evm-opcodes/gas.md at main · wolflo/evm-opcodes · GitHub](https://github.com/wolflo/evm-opcodes/blob/main/gas.md#a6-sload)

In our circumstance, it's actually going to cost 2100 gas and _I'll explain why later_.

But the gist of it is because it's the first time accessing the variable in that transaction.

It's a cold, cold access, so you have to pay extra for it.

A significant amount of the gas cost of an ethereal transaction is simply the sum of all of the OP codes that you execute within that transaction.

So the more OP codes that you execute, the more expensive the gas is going to be.

Remember that time when we were hashing things over and over again?

Well, if we look for the **keccak256** opcode, where is it?

No shot was listed as shot three.

Over here we can see that gas cost is going to be 30 gas plus how much data you're hashing and you can carry out this formula, but you can see 30 is much, much bigger than three.

`gas_cost = 30 + 6 * data_size_words + mem_expansion_costs`



Right.

And then we were doing it inside of a loop.

So that's why when we looked at the **heavy** and the **light functions** from the smart contract earlier, we can see why the heavy was more gas than the light one and put a quantitative number to it.

