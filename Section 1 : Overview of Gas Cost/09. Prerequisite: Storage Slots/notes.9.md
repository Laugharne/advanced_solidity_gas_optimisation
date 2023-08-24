https://www.udemy.com/course/advanced-solidity-understanding-and-optimizing-gas-costs/learn/lecture/31856134#overview


I want to give you an intuition about how storage addresses are determined in Etherium.

Now, this is not going to be a complete tutorial.

It's just going to be enough information so that we can keep going and get an intuition about how to understand the up codes that are generated from the smart contract.

![](2023-08-01-15-34-20.png)

We have a storage variable that we are curious about the address of and the storage, and we're going to get the slot location and return it.

Now, regular solidity can't do this.

You have to use a dialect of solidity called that's not really a dialect of solidity, but it's a programming

language that developed by a theorem that's designed to be pretty close to the assembly of codes.

It's actually not technically assembly.

I do think that this tag is a little bit misleading, but it's pretty close.

What it's going to do is just look at a and get the slot of it so you can read through the documentation if you're curious about how this works.

But I'll just look at the variable and get the slot and store that inside of the variable slot location and then return that.

So let's run it.

When I execute this, I get zero back as a result.

Now let's try to get an intuition around where the zero comes from.

What would happen if I added another variable?

Be up here and deploy and rerun this contract.

Well, now I get one.

Okay, let's do this.

Had a third variable.

Deploy that and I get two.

Now you can think very roughly that the storage slot will be how many variables down it is, but that's not quite accurate.

However, the important thing you want to come away from here is that the storage location doesn't change.

These variables don't get moved around.

So once you allocate a particular storage slot to belong to a certain variable, it does not get altered later on.

![](2023-08-01-15-34-37.png)

The reason why these addresses or slots matter is because this is how the Etherium virtual machine knows which value to access.

When you say return CB or A, that makes sense from a human perspective, but from the machine perspective,

it doesn't understand whatever you named your variable, it only understands the location of that variable.

So if we say get at slot zero, then it's going to return 99 because in the zero with slot we have 99.

If we enter one, then we're going to see 13 come back.

So that's the same as if we had said return B, but the compiler is going to turn return B into return whatever is stored at slot one.

And the same thing will happen here.

If we put two in, then we're going to get the storage value at two, which is two.


