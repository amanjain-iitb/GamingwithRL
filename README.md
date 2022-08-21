# Learning Agents with RL

## Requirements:
 * tensorflow
 * keras
 * OpenAI Gym
 * pytorch
 * numpy,pandas,matplotlib
 
## Environments:
  * Snake Game
  * Ms.Pacman
  
## Algorithms:
* DQN implemented for the snake game environment
* DQN implemented for Ms.Pacman
* Sarsa(lambda) and Actor Critic Policy Gradient for Ms.Pacman

## Results:

### DQN on Snake Game for 100 iterations:
  * Score achieved:
  * Graph:
  
  
### DQN on Ms.Pacman for 500 iterations:
  * Score achieved:
  * Graph:
  
  
### Sarsa(𝝀) on Ms.Pacman for 500 iterations

**Backward-view**

* Policy evaluation
    * ![](http://latex.codecogs.com/gif.latex?Q%28s%2C%20a%29%20%5Cleftarrow%20Q%28s%2C%20a%29%20&plus;%20%5Calpha%28R%20&plus;%20%5Cgamma%20Q%28s%27%2C%20a%27%29%20-%20Q%28s%2C%20a%29%29*E_t%28s%2C%20a%29)
    * Accumulating eligibility trace: ![](http://latex.codecogs.com/gif.latex?E_t%28s%2C%20a%29%20%3D%5Cgamma%5Clambda%20E_%7Bt-1%7D%28s%2C%20a%29%20&plus;%201%28S_t%20%3D%20s%2C%20A_t%20%3D%20a%29)
* Policy improvement: 𝜀-greedy with 𝜀 decay
* Q-value function approximation: A fully connected layer (input layer and output layer with no hidden layer)

### Actor-Critic for Ms.Pacman 500 iterations:

* Actor
  * Softmax policy with a fc layer
  * Use advantage function to estimate ![](http://latex.codecogs.com/gif.latex?Q_%5Cpi%28s%2C%20a%29): ![](http://latex.codecogs.com/gif.latex?%5Ctriangledown_%5Ctheta%20J%28%5Ctheta%29%20%3D%20E_%5Cpi%5B%5Ctriangledown_%5Ctheta%5Clog%5Cpi%28s%2C%20a%29A_%5Cpi%28s%2C%20a%29%29%5D%20%3D%20E_%5Cpi%5B%5Ctriangledown_%5Ctheta%5Clog%5Cpi%28s%2C%20a%29%5Cdelta_%5Cpi%5D), where ![](http://latex.codecogs.com/gif.latex?A_%5Cpi%28s%2C%20a%29%20%3D%20Q_%5Cpi%28s%2C%20a%29%20-%20V_%5Cpi%28s%29)

* Critic
  * TD policy evaluation ![](http://latex.codecogs.com/gif.latex?V_%5Cpi%28s%29%20%5Cleftarrow%20V_%5Cpi%28s%29%20&plus;%20%5Calpha%5Cdelta_%5Cpi)
  * ![](http://latex.codecogs.com/gif.latex?%5Cdelta_%5Cpi%20%3D%20R%20&plus;%20%5Cgamma%20V_%5Cpi%28s%27%29%20-%20V_%5Cpi%28s%29)
  * Value function approximation: a fully connected layer (input layer and output layer with no hidden layer)

Incase you have any improvements in the code, feel free to suggest them!

  
  
