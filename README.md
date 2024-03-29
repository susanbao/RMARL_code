# RMARL_code
This is the code for our paper "What is the Solution? A Robust Agent Policy for State Adversarial Multi-Agent Reinforcement Learning". We implement the Robust Multi-Agent Reinforcement Learning (RMARL) algorithm in file "rmarl". The code is modified from https://github.com/openai/maddpg. Here we also include the source code of MADDPG from https://github.com/openai/maddpg and M3DDPG from https://github.com/dadadidodi/m3ddpg.

For Multi-Agent Particle Environments (MPE) installation, we add some new scenarios to the MPE and include them here. The origin MPE code is from https://github.com/openai/multiagent-particle-envs.

- To run the code, `cd` into the `experiments` directory of the corresponding algorithm file and run `train.py`:

``python train.py --scenario simple``

- You can replace `simple` with any environment in the MPE you'd like to run.

### Command-line options

#### Environment options

- `--scenario`: defines which environment in the MPE is to be used (default: `"simple"`)

- `--max-episode-len` maximum length of each episode for the environment (default: `25`)

- `--num-episodes` total number of training episodes (default: `60000`)

- `--num-adversaries`: number of adversaries in the environment (default: `0`)

- `--good-policy`: algorithm used for the 'good' (non adversary) policies in the environment
(default: `"rmaddpg"`; options: {`"rmaddpg"`, `"maddpg"`, `"ddpg"`})

- `--adv-policy`: algorithm used for the adversary policies in the environment
(default: `"rmaddpg"`; options: {`"rmaddpg"`, `"maddpg"`, `"ddpg"`})

#### Core training parameters

- `--lr`: learning rate (default: `1e-2`)

- `--gamma`: discount factor (default: `0.95`)

- `--batch-size`: batch size (default: `1024`)

- `--num-units`: number of units in the MLP (default: `64`)

- `--gda-step`: number of steps to do gradient descent ascent algorithm (default: `20`)

- `--d-value`: a radius denoting how large the perturbation set is (default: `1.0`)

### Train example

#### RMARL
cd ./rmarl/experiments

python train.py --gda-step 20 --d-value 1.0  --save-dir models/ --scenario simple --exp-name simple

#### MADDPG
cd ./maddpg/experiments

python train.py --save-dir models/ --scenario simple --exp-name simple

#### M3DDPG
cd ./m3ddpg/experiments

python train.py --save-dir models/ --scenario simple --exp-name simple

## Citation:
If you find this repo useful in your research, please consider citing:
```bibtex
@article{Han22Whatis,
      author = {Han, Songyang and Su, Sanbao and He, Sihong and Han, Shuo and Yang, Haizhao and Miao, Fei},
      title = {What is the Solution for State-Adversarial Multi-Agent Reinforcement Learning?},
      eprint={2212.02705},
      archivePrefix={arXiv}
      year = {2022},
}
```
