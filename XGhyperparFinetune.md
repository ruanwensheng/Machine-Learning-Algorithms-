3 METHODS TO FINETUNE THE HYPERPARAMETERS WITH XGBOOST

HYPERPARAMETERS: are input parameters to a ML model, set by the programmer, they cant be learned by the algo
HYPERPARAMETERS TUNING: come up with the configuration that are ideal for the problem ~ a meta algo

LOOK AT 5 parameters:
- Number of weak learners (n_estimators)
- Learning rate
- Max depth
- L1 regularization
- L2 regularization

1. Number of weak learners


2. Learning rate
determine how fast we update the model parameters during training 

3. Max depth
maximum depth of our trees. For each constituent tree in our ensemble, we can define how complex each one of those tree can get 

4. L1
<img width="306" height="75" alt="image" src="https://github.com/user-attachments/assets/3696cd7c-7ff0-455c-8b3b-38523fab65e4" />
the effect of L1 is to penalize very sparse features in the features set
L1 feature selection, remove non informative feature, simply the overall ML model

6. L2
<img width="281" height="71" alt="image" src="https://github.com/user-attachments/assets/08064c65-b81c-4d3e-a9da-199ca8edd2a3" />
try to minimize model complexity
generalize the model

METHOD 1: GRID SEARCH
- Grid search: exhaustive search over all combinations of parameter values
- First, we define a set of possible values we want to investigate then loop over
- Downside: computational time
METHOD 2: Randomized Search
- random sampling of parameter value, from either input lists or a defined probability distribution
METHOD 3: Bayesian Optimization
- whenever you select out a new set of parameters, we dont just do that at random, it takes into account the previous iteration to inform what should be the right value
- fast
