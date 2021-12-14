## 2021 Models for Complex Systems course on DIKU
- Made in colaboration with Lars Kæraa Lücke, Hróbjartur Höskuldsson, Johannes Brøns Christensen, Sara Denner Vincent Larsen.
- Data consist of recordings of spikes for neurons on a time preriod. The recordings are summarized by counting the number of spikes at each timestep, t, for each neuron, n, giving n × t data points.
- A neuron shows a certain pattern when attending a certain stimuli. The task is to build a Bayesian network in the form of a Hidden Markov Model, which can capture both cases.

## Keywords
- Probabilistic Graphical Models
- Hidden Markov Model
- Simulation of data
- Inference: Variable elimination, Message passing
- Hard-assignment EM algorithm

## Summary of project
- The description of the HMM was given.
- A forward simulation algorithm for the data was implemented.
- A logistic regression model was made as a baseline. 
- An inference algorithm was developed to predict hidden varibles, which could be viewed as either a variable elimination or message passing algorithm.
- An EM algorithm was created with the inference algorithm as expectation step, since the inference algorithm requires unknown latent parameters to predict correctly. 

## The hidden markov model:
![alt text](https://github.com/tschiolborg/ModComp/blob/main/hmm.png?raw=true)
Where *X<sub>t,i</sub>* is observed and indicates number of observed spikes in time interval *t* for neuron *i* (time interval *t* being from time *50 * (t-1) ms* to time *50 * t ms*). 

*Z<sub>t,i</sub>* is either 0 or 1 and unobserved. It indicates which of the two stimuli neuron *i* is attending at time *i*. Depending on the stimuli the neuron either more or less active.

*C<sub>t</sub>* is either 0, 1 or and unobserved. When 2 it indicates parallel processing, meaning each neuron has probability 1/2 of attending stimuli one and prob. 1/2 of attending stimuli two. When 0 or 1 it indicates serial processing, where most neurons are either attending to respectivly stimuli 0 or 1.

The goal is to capture both forms of processing. Look at the *Reduced_version.ipynb* Notebook for more details of the project. The data can be represented in the figure below. The solid blue points represents mean value of *X* at time *t* (time is 1st-axis), meaning that for each time step we have computed the mean value of spikes among all neurons. The transparent points represents *Z* and *C* at each time step, such that when the points on the 2nd-axis is 0, then the mean value of *X* indicates *Z=0*, while when the points are >0 then the mean value of *X* indicates *Z=1*. The points are colored according to the value of *C*.
![alt text](https://github.com/tschiolborg/ModComp/blob/main/example_data.png?raw=true)

