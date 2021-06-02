# Internship

### 30/05/2021 - first_network.py
I read PyNest official tutorials (https://nest-simulator.readthedocs.io/en/nest-2.20.1/tutorials/index.html) and, using those info, I want to build a simple network where 2 excitatory populations receive the same input and spike on 1 inhibitory, trying to see how the competition takes place. <br>
Below you can find a scheme of the network.

![alt text](https://github.com/Igor10798/Internship/blob/master/images/01.png)


###### 1. Basic level
I build the network with deterministic connections and synapses, I expect the same behavior from the excitatory populations
###### 2. Aleatory connectivity
I build the network with aleatory connections but without synaptic plasticity, one network may be stronger than the other
###### 3. STDP synapses
I build the network with aleatory connections and synaptic plasticity, I expect different behavior depending on what population fires firstly on the inhibitory one.
###### Description of procedure
I used info from the tutorial linked above and I look at some examples online for setting some parameter (e.g. https://www.nest-simulator.org/py_sample/brunel_delta_nest/ && https://www.nest-simulator.org/py_sample/structural_plasticity/).<br>
I did not observe the expected behavior (I guess it is because the logic works if they are single neuron and not populations of neurons (?) || because of the exteral inputs), so I played with some parameters to see how the network answered to modifications (I changed inputs, both in the model of the neuron and with external device, randomization of V_m, delays and tau_syn) I changed also some parameters for connections (probability of bernoulli distribution) and for synapses (weight and alpha). <br>
I looked at the documentation for the meaning of the parameters and for the list of all of them, and I got them even from the code through nest.GetStatus && nest.GetDefault.

I differentiated the inputs during the simulation because in this way I could see the different effect they had on the inhibitori population (with weaker inputs the inhibitory effect is stronger). I don't know what kind of parameter is realistic, I sacrificed realism in setting them in order to obtain certain behaviors.


### 31/05/2021 - structural_plasticity.py
I looked at a structural plasticity network (https://www.nest-simulator.org/py_sample/structural_plasticity/) and I want to use that class with some modifications in order to build a small network where structural plasticity is enabled. <br>
I looked in the docs the functions I did not know and I used the chance to look at the functions related to the simulation in the docs (https://nest-simulator.readthedocs.io/en/nest-2.20.1/ref_material/pynest_apis.html?highlight=resetkernel#module-nest.lib.hl_api_simulation), implementing them in the first_project.py file in order to run multiple simulations.

I added a function to the class that should let you to add connection and insert that plastic network in a bigger one.
###### Comments
I could not find in the docs the property "synaptic_elements" for the "iaf_psc_alpha" object, so I could not understand how it works... Maybe I can add new properties to neurons (?)
