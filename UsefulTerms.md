# Introduction
![Reinforcement Learning Paradigm](https://www.kdnuggets.com/images/reinforcement-learning-fig1-700.jpg "Reinforcement Learning Paradigm")

Reinforcement Learning is a paradigm for teaching computers to make a sequence of decisions. An [agent](#agent) makes decision within an [environment](#environment). Every [timestep](#timestep), the agent observes the current [state](#state), and chooses an [action](#action) using its [policy](#policy). The agent then receives a [reward](#reward) and the environment transitions to the next state. The goal of the agent is to learn a policy that maximize expected total reward.

# Some Useful Terms
### Action
Every [timestep](#timestep), the [agent](#agent) observes the current [state](#state) and chooses an action. In some environments, the action could be discrete (e.g. go up, go down, go left, go right) or continuous (e.g. go up at 1 m/s, go up at 1.001 m/s, go up at 1.002 m/s, ...)

### Agent
The decisions-making entity. For example, an autonomous, wheeled robot would be considered an agent, since it needs to decide how it wants to apply power to its motor.

### Environment
The world that the [agent](#agent) lives in. For example, the environment of a wheeled robot would consist of the region in which it could move. The dynamics of an environment determine how things change from one moment to the next. If the robot applies power to its motor, the robot will move forward. The robot's acceleration is determined by the environment dynamics

### Experience Replay Dataset
A number of Reinforcement Learning algorithms collect experiences. That is, every [timestep](#timestep), the [agent](#agent) observes the current [state](#state), takes an [action](#action), receives a [reward](#reward), and the environment transitions to the next state. The agent will put the state, action, reward, and next state into a database it can then use to learn from.

### Multi-task learning / Multi-objective Learning
If, instead of one [reward](#reward), the agent is given a bunch of rewards. For example, if you want to get home, you can either get home quickly (minimize travel time) or get home inexpensively (minimize cost). The agent can be given those two objectives and depending on which is more important, the solution will be different (minimize travel time --> take a taxi, minimize cost --> take a bus)

### Off Policy / On Policy
On-Policy Reinforcement Learning algorithms work by using a policy to interact with the environment (i.e. to make decisions) and trying to improve that same policy. The agent will use its policy to make a decision, it will receive a reward, and then it will try to improve its policy.

Off-Policy Reinforcement Learning algorithms use two different policies. The agent uses the _behaviour policy_ to make decisions, and then tries to improve the _target policy_. The agent will use the behaviour policy to make a decision, it will receive a reward, and then it will try to improve its target policy. Note that the behaviour policy typically stays the same throughout the learning.

### Policy
A policy is a way of making decisions. Given a [state](#state), a policy will output an [action](#a#tion). For example, if you're nearing a stoplight, one possible policy would be

| State | Action |
| --- | --- |
| red light | go |
| yellow light | go |
| green light | go |

which is a valid policy, since it's a mapping from states to actions.
If the [reward](#reward) function is to survive as long as possible, though, then the optimal policy would probably be

| State | Action |
| --- | --- |
| red light | stop |
| yellow light | slow |
| green light | go |

### Reward
The designers of the problem want the [agent](#agent) to do something. How do they tell it what to do? Via the reward. The goal of the agent is to maximize reward, so if the reward aligns with the goals of the designers, then the agent will learn to do the right thing.

Every [timestep](#timestep), the agent chooses an [action](#action) and receives a reward.

### Reinforcement Learning (RL)
Teaching an [agent](#agent) to make a sequence of decisions that will maximize a reward.

### State
Also known as observation.
The state consists of all the information about the [environment](#environment) at the current moment. The state of a simple wheeled robot might consist of the current position of the robot and the current velocity of the robot. If you're sitting at a stop light and the only question is whether to go or not, the state would consist of the color of the light. 

### Timestep
Typically, in RL, we assume that time moves in discrete steps. Every timestep, the [agent](#agent) can decide what it wants to do and the environment will react.

### Value Function
The expected total amount of [reward](#reward) the agent will receive if it starts from a given [state](#state). 
