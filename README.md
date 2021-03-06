# CartPole
![CartPole Random Guessing Algorithm GIF](https://i.imgur.com/2m28e15.gif)

## What is this?
This is my walk through of the [CartPole problem][1] as described in the [OpenAI Requests for Research][2].

## What is the problem?
The Cartpole environment is one of the simplest MDPs. It is extremely low dimensional, with a four-dimensional observation space and only two actions. The goal of this exercise is to implement several RL algorithm in order to get practical experience with such methods.

The small size and simplicity of this environment makes it is possible to run very quick experiments, which is essential when learning the basics.

Start with a simple linear model (that has only four parameters), and use the sign of the weighted sum to choose between the two actions.

  * The random guessing algorithm: generate 10,000 random configurations of the model's parameters, and pick the one that achieves the best cumulative reward. It is important to choose the distribution over the parameters correctly.

  * The hill-climbing algorithm: Start with a random setting of the parameters, add a small amount of noise to the parameters, and evaluate the new parameter configuration. If it performs better than the old configuration, discard the old configuration and accept the new one. Repeat this process for some number of iterations. How long does it take to achieve perfect performance?

  * Policy gradient algorithm: here, instead of choosing the action as a deterministic function of the sign of the weighted sum, make it so that action is chosen randomly, but where the distribution over actions (of which there are two) depends on the numerical output of the inner product. Policy gradient prescribes a principled parameter update rule [1, 2]. Your goal is to implement this algorithm for the simple linear model, and see how long it takes to converge.

What happens to the above algorithm when the policy is a neural network with tens of thousands of parameters?

## Why?
It looked like a good entry point/``"hello world"`` RL problem.


[1]: https://openai.com/requests-for-research/#cartpole
[2]: https://openai.com/requests-for-research/
