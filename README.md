# Maximum Entropy Population-Based Training for Zero-Shot Human-AI Coordination

This is the code for our paper "Maximum Entropy Population-Based Training for Zero-Shot Human-AI Coordination".

The current version of the paper is accepted by 2021 NeurIPS (NIPS) Cooperative AI Workshop.  

The link of the paper: https://arxiv.org/abs/2112.11701  

The final version of the paper is accepted by AAAI 2023.  

Our code is based on the Overcooked game environment codebase, which is available at https://github.com/HumanCompatibleAI/human_aware_rl/tree/neurips2019. \
Please follow the installation instructions of the aforementioned link, then merge this codebase to that one.

To train a maximum entropy population, you can use the following command:
```
export PBT_DATA_DIR="pbt_data_dir/" && python pbt/pbt_model_pool_entropy_parallel.py with fixed_mdp layout_name="simple" EX_NAME="pbt_simple" TOTAL_STEPS_PER_AGENT=1.1e7 REW_SHAPING_HORIZON=5e6 LR=8e-4 GPU_ID=0 POPULATION_SIZE=5 SEEDS="[9015]" NUM_SELECTION_GAMES=6 VF_COEF=0.5 MINIBATCHES=10 TIMESTAMP_DIR=False ENTROPY_POOL=0.01 ENT_VERSION=3
```
To train the AI agent using the learning progress-based prioritized sampling, you can run the command:  
```
export PBT_DATA_DIR="pbt_data_dir_2/" && python pbt/pbt_model_pool.py with fixed_mdp layout_name="simple" EX_NAME="pbt_simple" TOTAL_STEPS_PER_AGENT=1.1e7 REW_SHAPING_HORIZON=5e6 LR=8e-4 GPU_ID=0 POPULATION_SIZE=N SEEDS="[8015]" NUM_SELECTION_GAMES=6 VF_COEF=0.5 MINIBATCHES=10 TIMESTAMP_DIR=False ENTROPY_POOL=0.0 PRIORITIZED_SAMPLING=True ALPHA=3.0 METRIC=1.0 LOAD_FOLDER_LST="path_1/:/path_2:...:/path_n"
```

## Citation

Citation of the paper:

```
@article{zhao2021maximum,
  title={Maximum Entropy Population-Based Training for Zero-Shot Human-AI Coordination},
  author={Zhao, Rui and Song, Jinming and Yuan, Yufeng and Haifeng, Hu and Gao, Yang and Wu, Yi and Sun, Zhongqian and Wei, Yang},
  journal={arXiv preprint arXiv:2112.11701},
  year={2021}
}
```

## Licence

MIT
