# JvN29 Turing Machine
A project to built a complete turing machine in JvN29

## Contents
 * [What is JvN29?](#What-is-JvN29)
 * [The rules of JvN29](#The-rules-of-JvN29)
   * [The states](#The-states)
   * [The rules](#The-rules)
 * [The JvN29TM project](#The-JvN29TM-project)

## What is JvN29?
Back in the 1940s, [John von Neumann](https://en.wikipedia.org/wiki/John_von_Neumann), a mathematician, physicist, and engineer, wanted to create a replicator. He abandoned his original, physical approach after he found it difficult to formalize. His friend, [Stanislaw Ulam](https://en.wikipedia.org/wiki/Stanislaw_Ulam), suggested to use a square grid of cells. Von Neumann decided on the following rules:
 * A cell can be in one of 29 states
 * Each tick, a cell updates its own state according to the states of itself and its five neighbors.
This led to the invention of Cellular Automata.

## The rules of JvN29
### The states
The twenty-nine states are the following:
 * a **ground** state **U**
 * the **transition** or **sensitised** states (in 8 substates)
   * **S** (newly sensitised)
   * **S<sub>0</sub>** – (sensitised, having received no input for one cycle) 
   * **S<sub>00</sub>** – (sensitised, having received no input for two cycles) 
   * **S<sub>000</sub>** – (sensitised, having received no input for three cycles) 
   * **S<sub>01</sub>** – (sensitised, having received no input for one cycle and then an input for one cycle) 
   * **S<sub>1</sub>** – (sensitised, having received an input for one cycle) 
   * **S<sub>10</sub>** – (sensitised, having received an input for one cycle and then no input for one cycle) 
   * **S<sub>11</sub>** – (sensitised, having received input for two cycles) 
 * the **confluent** states (in 4 states of excitation) 
   * **C<sub>00</sub>** – quiescent (and will also be quiescent next cycle) 
   * **C<sub>01</sub>** – next-excited (now quiescent, but will be excited next cycle) 
   * **C<sub>10</sub>** – excited (but will be quiescent next cycle) 
   * **C<sub>11</sub>** – excited next-excited (currently excited and will be excited next cycle) 
 * the **ordinary transmission** states (in 4 directions, excited or quiescent, making 8 states)
   * North-directed (excited and quiescent) 
   * South-directed (excited and quiescent) 
   * West-directed (excited and quiescent) 
   *# East-directed (excited and quiescent) 
 * the **special transmission** states (in 4 directions, excited or quiescent, making 8 states)
   * North-directed (excited and quiescent)
   * South-directed (excited and quiescent)
   * West-directed (excited and quiescent)
   * East-directed (excited and quiescent)

Here are the icons in [Golly](https://golly.sourceforge.net):
![29 States of JvN29](assets/states.png)
The first group is the newly sensitized **S**. The second group consists of the other sensitized states. The third and fourth groups are the quiescent and excited ordinary transmission states, respectively. The fifth and sixth are the special transmission states. Finally, the last group is made of the confluent states.

### The rules
JvN29 is mostly a wire rule. As the arrows in the icons suggest, the wires are all one-way. For the ordinary transmission states, the confluent states act as splitters. The confluent states also allow signals to transfer between ordinary and special transmission states. However, when a special transmission state signal hits a confluent state, it is destroyed.

When a signal reaches the end of a wire, it can do multiple things. First, depending on the sequence of excited and quiescent signals, it will create either a quiescent transmission state or the quiescent confluent state. When a signal from a ordinary transmission state tries to transfer into a special transmission state without a confluent state to assist, the special transmission state will be destroyed and vice versa.

## The JvN29TM project
The **JvN29TM Project** is a project to build a complete working [Turing machine](https://en.wikipedia.org/wiki/Turing_machine) in the JvN29 ruleset.

Please join the project!<br />
Members:
 * @EZLiang