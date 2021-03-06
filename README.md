# Online Fast Adaptation and Knowledge Accumulation:
# a New Approach to Continual Learning 

official code for the paper: https://arxiv.org/abs/2003.05856 


## (key) Requirements 
- Python 3.6
- Pytorch 1.2 or higher

`pip install -r requirements.txt`

## Structure

    ├── Data
        ├── omniglot.py           # fetches the dataset      
        ├── tiered_imagenet.py    # fetches the dataset
    ├── MAML           
        ├── metalearner
            ├── maml.py           # defines the models, in particular their CL strategy
        ├── model.py              # defines the backbone neural networks
        ├── utils.py              # some utils    
    ├── Utils
        ├── bgd_lib
            ├── ...         # files for BGD      
    ├── main.py             # main file
    ├── dataloaders.py      # defines the experiment setting, constructs the dataloaders    
    ├── args.py             # arguments
    ├── template.py         # main file template (if you dont want to use pytorch)
   


## Running Experiments


example (in verbose mode):  </br>

`python main.py -v`

some notable args:  </br>

```
python main.py --prob_statio 0.98 --num_epochs 0 --cl_strategy always_retrain --meta_lr 0.1 --learn_step_size --per_parameter_step_size -v 
```

to try different baselines in ['online_sgd', 'fine_tuning', 'MetaCOG', 'MetaBGD', 'MAML','ANIL', 'BGD']  </br>

`python main.py --model_name <baseline_name>`



## Logging

Logging is done with [Weights & Biases](https://www.wandb.com/) and can be turned on like this: </br>
`python main.py --wandb <workspace_name>`

## TODO

- [ ] code to reproduce experiments

## Acknowledgements

MAML code comes from https://github.com/tristandeleu/pytorch-maml

## Contact

massimo.p.caccia at gmail.com





