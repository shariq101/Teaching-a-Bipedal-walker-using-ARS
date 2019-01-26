NEWTONS METHOD OF FINITE DIFFERENCES

The goal of reinforcement learning is to get an agent to learn something and similar to how deep reinforcement learning algorithms use gradient descent to optimize weights and reduce the cost function, ARS uses the method of finite differences to adjust its weights and learn how to perform a task.

The Process

To update the weights effectively, the agent takes a random matrix of tiny values and adds them to the weights. The AI then adds the exact same matrix, but these same values, but this time with negative weights. It then repeats this many times and the end result is an agent trying to perform a task with slightly different weights.

We get rewards for each configuration of weights from the environment and some are higher than others. What ARS does it that it adjusts those weights according to the weight configurations that it gave the best rewards. The higher the reward, the more the weights were adjusted, the lower the reward, the lesser the weights were adjusted.
This is the equation that helps calculate this.

This picture shows 4 different weight configurations with the coefficient being the difference between the positive configuration of that weight and the negative configuration of that weight. The greater the difference between the rewards, or in other words, the better the reward, the bigger the coefficient will be for that specific configuration of weights, meaning it will influence the weights more.
One of the additional modifications to the above equation is that the researchers discarded low rewards immediately. They only used the top k configurations with the highest reward. Intuitively this makes sense because why would we keep pursuing and experimenting with weights that give a low reward? By taking them out, we save time and computational power!
ARS also does things a little bit differently than other algorithms by exploring policy spaces instead of action spaces. Basically, this means that instead of analyzing the rewards it gets after each action, it analyzes the reward after a series of actions to determine if that set of actions led to a higher reward.

Take away from this :

ARS uses a perceptron instead of a deep neural network.

ARS randomly adds tiny values to the weights along with the negative of that value to figure out if they help the agent get a bigger reward.

The bigger the reward from a specific weight configuration, the bigger its influence on the adjustment of the weights.
