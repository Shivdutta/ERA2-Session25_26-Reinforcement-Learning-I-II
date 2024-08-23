# ERA2-Session25_26-Reinforcement-Learning-I-II

# Gridworld

## Pre requisites:
- Env : python 2.7

## Psuedo Code Understanding

1. __init__
    - This finction intializes q values(self.qvalues) of system to empty dictionary

2. getQValue
    - This function returns the state and action of q values.
    - If self.qvalues is not none then it returns self.qvalues else 0.0

3. computeValueFromQValue
    - This function returns value of state where action is maximum for all q values in that state considering all possible actions 
    - It first gets all possible actions for q values
    - if it is allowed then we check if action is in self.getLegalActions(state)
    - If above is true, then maximum of q values is computeValueFromQValue and same is returned. 
    - If there is no possible actions which can be taken them computeValueFromQValue = 0.0 and same is turned

4. computeActionFromQValues
    - This function returns an action can be taken which gives maximum q values for particular given state
    - This starts with finding first best q value which is value of the state where action = V from computeValueFromQValue
    - This is followed by finding all possible actions in that state found using actions in self.getLegalActions(state)
    - Next is to find which of these actions gives the maximum q value from getQValue(state, action)
    - if there are multiple actions found which gives the maximum q value then we take any one action randomly from the list of actions and return
    - if there are no possible actions found then nothing is returned. 

5. getAction
    - The action taken at any state is determined by policy and epsilon (which adds randomness to the process)
    - if random probability is less than epsilon, then we chose a random action from all possible available actions in that state
    - Otherwise, we go with the action dictated by the policy using self.getPolicy(state)

6. update
    - This function updates the q values during q learning. state, action, nextState, reward
    - The new qvalue_new is set as = qvalue + alpha * (reward + disc * next_value - qvalue)
      where alpha is same as to learning rate, reward is set by environment,  discount factor is discounts for future rewards.

## Running program:
    After activating environment the program can be run by
    python Gridworld.py -k 100 -a q -s 2000

## Gridworld Output
    https://github.com/Shivdutta/ERA2-Session25_26-Reinforcement-Learning-I-II/blob/main/Gridworld.png

## Car Simulation 
    Youtube link: [https://youtu.be/R9vKHr1zBeI]([https://www.youtube.com/watch?v=dQw4w9WgXcQ](https://youtu.be/R9vKHr1zBeI))

## Pre requisites:
- Env : python 3.6.9 and can run till python 3.9
- pip install kivy

## Environment Creation and running program:
- From google map I have taken the are where I live.
- Cropped the image from the satellite map by  making labels off.
- Using Libre Offie Draw(Ubuntu) oe MS Paint(windows), all navigation path are created.
- This includes drawing path for main roads and sub roads etc. 
- The main image is removed and drawn image is saved as MASK.png
- The same image is 90 degree rotated and and saved as MASK1.png.
- The program is run from command line using :
  python map.py
- sand,pnd is generates as programs learns during training

## Demo

TBD

## Questions

Q1. What happens when "boundary-signal" is weak when compared to the last reward?

Answer: When the "boundary-signal" is weak relative to the last reward, the car tends to stuck at the boundary. It struggles to return to the road or to reach its goal set.

Q2. What happens when Temperature is reduced?

Answer: The car movement was fluctuating very rapidly in sthe stimulation. The temperature controls the "exploration-exploitation trade-off". With lower temperature can led to reduced exploration and increased exploitation.

Q3. What is the effect of reducing gamma? 

Answer: By reducing the gamma value  can have averse results in overall result. The agent may not focus to reach the goal but be happy in staying on roads by getting current rewards.

