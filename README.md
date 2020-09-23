# Simplifying Hamiltonian and Lagrangian Neural Networks via Explicit Constraints


![CHNN_perf_summary](https://user-images.githubusercontent.com/12687085/94081992-e75d5d00-fdcd-11ea-9df0-576af6909944.PNG)
![chaotic_2pendulum](https://user-images.githubusercontent.com/12687085/94081997-e9bfb700-fdcd-11ea-8ca1-ce7ce1cdc717.PNG)
![systems](https://user-images.githubusercontent.com/12687085/94081999-eb897a80-fdcd-11ea-8e29-c676d4e25f64.PNG)

# Appendix
The appendix is in this directory as `Appendix.pdf`


# Code
Our code in the `biases` directory relies on some publically available codebases which we package together
as a conda environment.

## Installation instructions
1. Install anaconda or miniconda
2. Create a conda environment with `conda env create -f conda_env.yml`
3. Install our codebase with `pip install ./` while in the current directory
4. Create a wandb account for experiment tracking

## Train
We have implemented a variety of challenging benchmarks for modeling physical dynamical systems such as ``ChainPendulum``, ``CoupledPendulum``,``MagnetPendulum``,``Gyroscope``,``Rotor`` which can be selected with the ``--body-class`` argument.
<p align="center">
  <img src="https://user-images.githubusercontent.com/12687085/94081999-eb897a80-fdcd-11ea-8e29-c676d4e25f64.PNG" width=800>
</p>
You can run our models ``CHNN`` and ``CLNN`` as well as the baseline ``NN`` (NeuralODE), ``DeLaN``, and ``HNN`` models with the ``network-class`` argument as shown below.

```
python pl_trainer.py --network-class CHNN --body-class Gyroscope --wandb-project "YOUR WANDB PROJECT"
python pl_trainer.py --network-class CLNN --body-class Gyroscope --wandb-project "YOUR WANDB PROJECT"
python pl_trainer.py --network-class HNN --body-class Gyroscope --wandb-project "YOUR WANDB PROJECT"
python pl_trainer.py --network-class DeLaN --body-class Gyroscope --wandb-project "YOUR WANDB PROJECT"
python pl_trainer.py --network-class NN --body-class Gyroscope --wandb-project "YOUR WANDB PROJECT"
```

Our explicitly constrained ``CHNN`` and ``CLNN`` outperform the competing methods by several orders of magnitude across the different benchmarks.
<p align="center">
  <img src="https://user-images.githubusercontent.com/12687085/94081992-e75d5d00-fdcd-11ea-9df0-576af6909944.PNG" width=800>
</p>



