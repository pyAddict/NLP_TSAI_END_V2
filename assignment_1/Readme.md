# Session 1 Assignment

**What is a neural network neuron?**

A neural network neuron is a memory storage that is intended to mimic the biological neuron present in brains. Once the network receives an input, it gets scaled up according to a(n) (initially) random weights and then after adding bias into it , we pass the value through an activation function and finally the activated value gets stored into the neuron. The output of each neuron is used as an input for subsequent layers until we reach the last layer, in which the outputs are the output of the neural network itself.

**What is the use of the learning rate?**

The learning rate determined how much the gradient is to be scaled while updating the weights during backpropagation. The choice of learning rate (LR) affects how quickly we want our model to achieve the minimum error/loss. A larger LR means the model will reach convergence earlier but the solution might be suboptimal whereas a smaller learning rate might lead us to an optimal solution but the convergence time would be much larger and it might feel like that our training gets stuck. One possible solution to handle this tradeoff is, as we approach convergence, we want to reduce the LR so as not to ‘jump’ across the minima (i.e. prevent oscillating around the minima). Typically, optimizers use an adaptive learning rate while training the model.

**How are weights initialized?**

Weights are ‘randomly’ initialized from a normal distribution - albeit with small numbers. One must be careful about the initialization because if we initialize weights that are quite large we might face exploding gradient problems and similarly for relatively smaller weights we might face vanishing gradient problems. Although there exists advanced initialization techniques like He/Xavier that try to normalize the weight such that for normalized weights both of the above problems will no longer exist. Researchers have done extensive studies on which type of initialization yields the best result according to the activation function(viz He for Relu and Xavier for Tanh etc) Weights are not initialized with equal values (including 0 or any random value). This is because all the neurons will tend to ‘learn’ the same parameter, and the entire layer will behave like a single neuron. By having different values, we break the learning symmetry and yield a well-trained neural network. A very nice visualization can be seen at https://www.deeplearning.ai/ai-notes/initialization/.

**What is "loss" in a neural network?**

The loss is the error between the actual (expected) output and the predicted (calculated) output. Ideally, when training is complete, the loss should be 0. But during the training, the loss decreases as the neural network ‘learns’. The loss value is used to determine the gradients which in turn quantitatively describes how each weight in the previous layers need to be updated.

**What is the "chain rule" in gradient flow?**

The chain rule is used to compute derivatives of composite functions. Since our cost function is always a composite function hence we use chain rule to compute the gradient. The name ‘chain’ comes from the fact that the derivatives (intermediate) are linked (chained) together. Please refer this table to visualize the chain rule-
![Alt text](chain_rule.png?raw=true "Chain Rule Diagram")

