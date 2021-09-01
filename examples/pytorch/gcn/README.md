# GCN(Graph Convolutional Network)

## Introduction
Sampling-based GCN based on pyG.

We first use GSL 1-hop full neighbor sampling to get the 1-hop neighbor 
of nodes, and then implement an induce_func to convert the GSL results
to a list of pyG `Data` objects. Then, we use the `PyGDataLoader` to merge the list 
of `Data` to pyG `Batch` object. Finally, we implement the sampling-based 
`GCN` based on pyG `GCNConv`.


## Script arguments (partial)

| Args       | Description                                                        | Default      |
| ---------- | ------------------------------------------------------------------ | ------------ |
| client_num | Set to value bigger than zero to enable multi-processing dataload. | 0 (int)      |
| local_mode | Graph learn init use $PWD/tracker_path                             | False (bool) |

## How to run
### Supervised node classification.
1. Prepare data
    - cora for supervised model.
    ```shell script
    cd ../../data/
    python cora.py
    ```
2. Train and evaluate

    - supervised: 
    ```shell script
    cd ../pytorch/gcn/
    python train.py
    ```