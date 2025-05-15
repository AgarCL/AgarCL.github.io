---
hide-toc: true
firstpage:
lastpage:
---

```{figure} _static/img/agarcl_logo.png
:alt: AgarCL Logo
:width: 300
```

# AgarCL 

A research platform for continual RL that allows for a progression of increasingly sophisticated behaviour.


```{figure} _static/img/game_description-1.png
   :alt: AgarCL description
   :width: 500
```

**AgarCL is based on the game Agar.io.** It's a non-episodic, high-dimensional problem featuring stochastic, ever-evolving dynamics, continuous actions, and partial observability:

```{code-block} python
import gymnasium as gym

# Initialise the environment
env = gym.make("agario-grid-v0", render_mode="human")

# Reset the environment to generate the first observation
observation = env.reset()
for _ in range(1000):
    # this is where you would insert your policy
    action_space = gym.spaces.Box(low=-1, high=1, shape=(2,))
    action = (action_space.sample(), np.random.randint(0, 3))

    # step (transition) through the environment with the action
    # receiving the next observation, reward and if the episode has terminated or truncated
    observation, reward, terminated, truncated, info = env.step(action)

    # If the episode has ended then we can reset to start a new episode
    if terminated or truncated:
        observation = env.reset()

env.close()
```

The GitHub repository for the platform is available [here](https://github.com/AgarCL/AgarCL), and the repository for the agents can be found [here](https://github.com/AgarCL/AgarCL-Benchmark).


```{toctree}
:hidden:
:caption: Introduction

introduction/basic_usage
introduction/installation_instructions
introduction/environment_details

```

<!-- introduction/train_agent -->


```{toctree}
:hidden:
:caption: Development

Github: the platform <https://github.com/AgarCL/AgarCL>
Github: the agents <https://github.com/AgarCL/AgarCL-Benchmark>
```
