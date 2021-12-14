## 2021 Models for Complex Systems course on DIKU
- Made in colaboration with Lars Kæraa Lücke, Hróbjartur Höskuldsson, Johannes Brøns Christensen, Sara Denner Vincent Larsen.
- Data consist of recordings of spikes for neurons on a time preriod. The recordings are summarized by counting the number of spikes at each timestep, t, for each neuron, n, giving n × t data points.
- A neuron shows a certain pattern when attending a certain stimuli: uncoupled or coupled. The task is to build a Bayesian network in the form of a Hidden Markov Model, which can capture both cases.

## Keywords
- Probabilistic Graphical Models
- Hidden Markov Model
- Simulation of data
- Inference: Variable elimination, Message passing
- Hard-assignment EM algorithm

## Description of project
- The description of the HMM was given.
- A forward simulation algorithm for the data was implemented.
- A logistic regression model was made as a baseline. 
- An inference algorithm was developed to predict hidden varibles, which could be viewed as either a variable elimination or message passing algorithm.
- An EM algorithm was created with the inference algorithm as expectation step, since the inference algorithm requires unknown latent parameters to predict correctly. 

![alt text](https://github.com/tschiolborg/ModComp/blob/main/hmm.png?raw=true)
