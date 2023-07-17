# Hunting for Polysemantic Neurons
Analysis on whether neurons in a deep neural net are activated by multiple sets of meaning. Inspired by work from Neel Nanda &amp; Anthropic.



# Summary: 
The softmax linear unit developed by Anthropic is an exciting breakthrough to begin understanding the mystery behind what happens within the MLP in transformer based architectures. However we are approaching a dangerous world as more companies race towards the future focusing more on capabilities than comprehension. Which is why I am excited to dive into the world of mechanistic interpretability as a graduate student. In this work I perform two main experiments searching for polysemantic neurons in a four layer SoLU network downloaded from Neuroscope(Thank you Neel Nanda). Both experiments are systematic approaches to understand how each neuron is activated from human readable features, and then subsequent experiments are run for further understanding. I found a series of rather interesting neurons, however I can’t say for certain if they are polysemantic. Even though the results appear good at first glance diving deeper only opens up more questions if they representing different semantic information.


# Experiments
In my 2nd attempt, I decided to reduce the number of features, but instead make them extremely different in terms of content, and increase their size so that the network would indeed be activated on the contents of the input features. My new input features were texts made up of Fortran code, Spanish poetry, medical cellular text, & gibberish. Upon running the same code, and peering into which neurons were activated on exactly 2 features I found some interesting results. Specifically that a neuron that was being activated on Fortran and medical text was only due to the period in the medical text. This is a big lesson in the final check of the input dataset. However the most promising neuron which can be seen in Neuron 18 in Section Solu: 2nd run, lights up for both Spanish and Fortran code. However a lot of the tokens that were activated within the Fortran code were also base words in Spanish, and there was a high amount of activation in the entire Spanish text. The last experiment I ran was a heatmap on the Fortran code which can be seen at the bottom of the report in order to understand token activation better. Overall, while it is easy to jump to conclusions and call victory, I need to run further experiments understanding if these neurons indeed are polysemantic.

# Visuals

Below is the heatmap over all the different neurals within the input Neural netowrk. It tracks the activations across all the differnt input text strings.


<img src="/images/polysemantic_heatmap.png" width="75%">
