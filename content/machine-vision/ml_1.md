+++
date = "2016-03-24T01:30:32+05:30"
title = "Machine Learning"
header = "RR Blog"
slug = "1"
Draft = true

tags = [ "ai", "artificial_intelligence", "machine_learning" ]

categories = [
  "machine-learning",
  "machine-vision"
]

+++

# Artificial Neural Network
### introduction
* An Artificial Neural Network (ANN) is an information processing paradigm that is inspired by the way biological nervous systems, such as the brain, process information. 
* It is composed of a large number of highly interconnected processing elements (neurones) working in unison to solve specific problems. ANNs, like people, learn by example.
* Learning in biological systems involves adjustments to the synaptic connections that exist between the neurones. This is true of ANNs as well. 
* Neural networks, with their remarkable ability to derive meaning from complicated or imprecise data, can be used to extract patterns and detect trends that are too complex to be noticed by either humans or other computer techniques. 
* A trained neural network can be thought of as an "expert" in the category of information it has been given to analyse.

### history
* The first artificial neuron was produced in 1943 by the neurophysiologist Warren McCulloch and the logician Walter Pits. But the technology available at that time did not allow them to do too much. 
* More [history](https://www.doc.ic.ac.uk/~nd/surprise_96/journal/vol4/cs11/report.html#Appendix%20A%20-%20Historical%20background%20in%20detail)
* Neural network simulations appear to be a recent development. However, this field was established before the advent of computers, and has survived at least one major setback and several eras. 

### how human brain works 
Much is still unknown about how the brain trains itself to process information, so theories abound. In the human brain, a typical neuron collects signals from others through a host of fine structures called dendrites. The neuron sends out spikes of electrical activity through a long, thin stand known as an axon, which splits into thousands of branches. At the end of each branch, a structure called a synapse converts the activity from the axon into electrical effects that inhibit or excite activity from the axon into electrical effects that inhibit or excite activity in the connected neurones. When a neuron receives excitatory input that is sufficiently large compared with its inhibitory input, it sends a spike of electrical activity down its axon. Learning occurs by changing the effectiveness of the synapses so that the influence of one neuron on another changes.

## Neuron 
The previous neuron doesn't do anything that conventional conventional computers don't do already. A more sophisticated neuron (figure 2) is the McCulloch and Pitts model (MCP). The difference from the previous model is that the inputs are 'weighted', the effect that each input has at decision making is dependent on the weight of the particular input. The weight of an input is a number which when multiplied with the input gives the weighted input. These weighted inputs are then added together and if they exceed a pre-set threshold value, the neuron fires. In any other case the neuron does not fire.

![Alt text](https://www.doc.ic.ac.uk/~nd/surprise_96/journal/vol4/cs11/report.mcp_neuron.jpg "Optional title")


In mathematical terms, the neuron fires if and only if;

X1W1 + X2W2 + X3W3 + ... > T

The addition of input weights and of the threshold makes this neuron a very flexible and powerful one. The MCP neuron has the ability to adapt to a particular situation by changing its weights and/or threshold. Various algorithms exist that cause the neuron to 'adapt'; the most used ones are the Delta rule and the back error propagation. The former is used in feed-forward networks and the latter in feedback networks. 

## Perceptron
The most influential work on neural nets in the 60's went under the heading of 'perceptrons' a term coined by Frank Rosenblatt. The perceptron (figure 4.4) turns out to be an MCP model ( neuron with weighted inputs ) with some additional, fixed, pre--processing. Units labelled A1, A2, Aj , Ap are called association units and their task is to extract specific, localised featured from the input images. Perceptrons mimic the basic idea behind the mammalian visual system. They were mainly used in pattern recognition even though their capabilities extended a lot more.

![Alt text](https://www.doc.ic.ac.uk/~nd/surprise_96/journal/vol4/cs11/report.perceptron.jpg "Optional title")

In 1969 Minsky and Papert wrote a book in which they described the limitations of single layer Perceptrons. The impact that the book had was tremendous and caused a lot of neural network researchers to loose their interest. The book was very well written and showed mathematically that single layer perceptrons could not do some basic pattern recognition operations like determining the parity of a shape or determining whether a shape is connected or not. What they did not realised, until the 80's, is that given the appropriate training, multilevel perceptrons can do these operations. 







## The back-propagation Algorithm - a mathematical approach
Units are connected to one another. Connections correspond to the edges of the underlying directed graph. There is a real number associated with each connection, which is called the weight of the connection. We denote by Wij the weight of the connection from unit ui to unit uj. It is then convenient to represent the pattern of connectivity in the network by a weight matrix W whose elements are the weights Wij. Two types of connection are usually distinguished: excitatory and inhibitory. A positive weight represents an excitatory connection whereas a negative weight represents an inhibitory connection. The pattern of connectivity characterises the architecture of the network.
![Alt text](https://www.doc.ic.ac.uk/~nd/surprise_96/journal/vol4/cs11/report.neural1.jpg "Optional title")

A unit in the output layer determines its activity by following a two step procedure.
* First, it computes the total weighted input xj, using the formula:
![Alt text](https://www.doc.ic.ac.uk/~nd/surprise_96/journal/vol4/cs11/report.equ1.jpg "Optional title")

* where yi is the activity level of the jth unit in the previous layer and Wij is the weight of the connection between the ith and the jth unit.


* Next, the unit calculates the activity yj using some function of the total weighted input. Typically we use the sigmoid function:
![Alt text](https://www.doc.ic.ac.uk/~nd/surprise_96/journal/vol4/cs11/report.equ2.jpg "Optional title")

* Once the activities of all output units have been determined, the network computes the error E, which is defined by the expression:
![Alt text](https://www.doc.ic.ac.uk/~nd/surprise_96/journal/vol4/cs11/report.equ3.jpg "Optional title")
* where yj is the activity level of the jth unit in the top layer and dj is the desired output of the jth unit.



## The back-propagation algorithm consists of four steps:

1. Compute how fast the error changes as the activity of an output unit is changed. This error derivative (EA) is the difference between the actual and the desired activity.
![Alt text](https://www.doc.ic.ac.uk/~nd/surprise_96/journal/vol4/cs11/report.equ4.jpg "Optional title")

2. Compute how fast the error changes as the total input received by an output unit is changed. This quantity (EI) is the answer from step 1 multiplied by the rate at which the output of a unit changes as its total input is changed.
![Alt text](https://www.doc.ic.ac.uk/~nd/surprise_96/journal/vol4/cs11/report.equ5.jpg "Optional title")

3. Compute how fast the error changes as a weight on the connection into an output unit is changed. This quantity (EW) is the answer from step 2 multiplied by the activity level of the unit from which the connection emanates.
![Alt text](https://www.doc.ic.ac.uk/~nd/surprise_96/journal/vol4/cs11/report.equ6.jpg "Optional title")

4. Compute how fast the error changes as the activity of a unit in the previous layer is changed. This crucial step allows back propagation to be applied to multilayer networks. When the activity of a unit in the previous layer changes, it affects the activites of all the output units to which it is connected. So to compute the overall effect on the error, we add together all these seperate effects on output units. But each effect is simple to calculate. It is the answer in step 2 multiplied by the weight on the connection to that output unit.
![Alt text](https://www.doc.ic.ac.uk/~nd/surprise_96/journal/vol4/cs11/report.equ7.jpg "Optional title")

By using steps 2 and 4, we can convert the EAs of one layer of units into EAs for the previous layer. This procedure can be repeated to get the EAs for as many previous layers as desired. Once we know the EA of a unit, we can use steps 2 and 3 to compute the EWs on its incoming connections.

