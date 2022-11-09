# Natural Number Game

By Xue Han and Xiyu Zhai

Adapted from the Lean version by Kevin Buzzard and Mohammad Pedramfar.

What is this game?

Welcome to the natural number game -- a part-book part-game which shows the power of induction. Blue nodes on the graph are ones that you are ready to enter. Grey nodes you should stay away from -- a grey node turns blue when all nodes above it are complete. Green nodes are completed. (Actually you can try any level at any time, but you might not know enough to complete it if it's grey).

In this game, you get own version of the natural numbers, called mynat, in an interactive theorem prover called Lean. Your version of the natural numbers satisfies something called the principle of mathematical induction, and a couple of other things too (Peano's axioms). Unfortunately, nobody has proved any theorems about these natural numbers yet! For example, addition will be defined for you, but nobody has proved that x + y = y + x yet. This is your job. You're going to prove mathematical theorems using the Lean theorem prover. In other words, you're going to solve levels in a computer game.

You're going to prove these theorems using tactics. The introductory world, Tutorial World, will take you through some of these tactics. During your proofs, your "goal" (i.e. what you're supposed to be proving) will be displayed with a ⊢ symbol in front of it. If the top right hand box reports "Theorem Proved!", you have closed all the goals in the level and can move on to the next level in the world you're in. When you've finished a world, hit "main menu" in the top left to get back here.

For more info, see the FAQ.

What's new in v1.3?
The game now saves your progress! Thanks to everyone who asked for it, and to Mohammad for making it happen :-)

Cute little clipboard to copy your solutions.