# feudal_networks
An implementation of FeUdal Networks for Hierarchical Learning as published : https://arxiv.org/abs/1703.01161

Implementation and training framework derived from the OpenAI starter agent: https://github.com/openai/universe-starter-agent

## Acknowledgements

Used the FuN from https://github.com/dmakian/feudal_networks. 

## Instructions for Use

1. Identify your training environment, directory for saving files, and other passed parameters (see train.py). Ensure you are also in the correct virtualenv.
2. If you've installed a custom environment, import the package in the file scripts >> training >> envs.py. If you'd like to render the environment during training, leave in env.render() in policy_optimizer.py (otherwise, remove the render).
3. Run the following command

```
python train.py -e [ENV_NAME] -l [LOG_DIRECTORY]
```
4. This will automatically start a tmux session with three different tabs and Tensorboard at __localhost:12345__

5. Helpful tmux commands

  * *tmux a* to see all tmux tabs
  * *CTRL-B d* to exit tmux
  * *CTRL-B [Number]* to switch to a specific tab
  * *CTRL-B [* to go to scroll through output


## Notes

1. scripts >> training >> envs.py has a variable OVERRIDE. This switches the normal environment behavior to instead simply make the provided environment name. This only seems to affect Atari games. 

## Current To-dos
  * In feudal_policy.py and lstm_policy.py, need to replace tf.summary.image with a generic matrix saver (the state representation will often not simply be pixels)
  * Potentially rework code in policy_optimizer to programmatically take in a render statement
  * Create a benchmark run