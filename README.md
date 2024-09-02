# **Q-Learning for Blackjack**

This repository contains an implementation of the Q-Learning algorithm applied to the Blackjack game. The purpose of this project is to explore the effectiveness of Q-Learning in learning optimal strategies for decision-making in Blackjack, comparing it with other approaches such as random action selection and the basic strategy outlined in "Beat the Dealer".

## Overview

### Q-Learning

Q-Learning is a model-free reinforcement learning algorithm used to find the optimal policy for decision-making problems. It estimates the value of action-state pairs and updates these estimates based on the agent's interactions with the environment. The goal is to maximize the cumulative reward over time by learning the best actions to take in various states.

Key components of Q-Learning:
- **Q-Value (Q(s, a))**: Represents the expected utility of taking action `a` in state `s` and following the optimal policy thereafter.
- **Bellman Equation**: The core of Q-Learning, used to update Q-values:
  \[
  Q(s,a) \leftarrow Q(s,a) + \alpha \left[ r + \gamma \max_{a'} Q(s', a') - Q(s, a) \right]
  \]
  - \(\alpha\): Learning rate
  - \(\gamma\): Discount factor
  - \(r\): Reward received
  - \(s'\): New state after action \(a\)

### Blackjack Environment

The Q-Learning algorithm is applied in a Blackjack environment with the following workflow:

1. **Initialization**: Q-values for all state-action pairs are set to zero, and parameters such as learning rate (\(\alpha\)), discount factor (\(\gamma\)), and exploration rate (\(\epsilon\)) are initialized.
2. **Exploration and Exploitation**: The agent uses an \(\epsilon\)-greedy policy to balance between exploring new actions and exploiting known actions. The exploration rate \(\epsilon\) decays over time.
3. **Interaction with the Environment**: The agent selects an action based on its policy, executes the action, and updates Q-values based on the observed reward and new state.
4. **Updating Q-values**: Q-values are updated iteratively using the Bellman equation across numerous episodes to converge towards the optimal policy.
5. **Learning and Policy Improvement**: Over time, the agent's policy improves as Q-values become more accurate, leading to better decision-making in the Blackjack environment.

### Q-Value Updation

The Q-value table is central to the Q-Learning algorithm and is updated as follows:
1. **Action Selection**: The agent selects an action based on the current policy.
2. **Execute Action**: The selected action results in a new state and a reward.
3. **Q-Value Update**: The Q-value for the state-action pair is updated using the observed reward and estimated future rewards.
4. **Repeat**: The process repeats over multiple episodes to refine the policy.

## Experiments

The following experiments were conducted to evaluate the performance of Q-Learning and compare it with other strategies:

- ⭐ **Random Action Selection Comparison without Q-Learning vs. with Q-Learning**
  - This experiment compares the performance of an agent using random action selection versus Q-Learning in a standard Blackjack environment. The impact of reinforcement learning was analyzed through comparative graphs.

- ⭐ **Basic Strategy Comparison without Q-Learning vs. with Q-Learning vs. SARSA**
  - This experiment involves comparing the performance of basic strategy without Q-Learning, with Q-Learning, and with SARSA. The results indicate that Q-Learning outperforms SARSA in implementing basic strategies.

- ⭐ **Complete Point Count Strategy**
  - This experiment evaluates the performance of the complete point count strategy from "Beat the Dealer" in a Blackjack environment, examining its effectiveness compared to other strategies.

- ⭐ **Basic Strategy with Variations: Double Down and Soft Hand 17**
  - In this experiment, variations such as the "Double Down" action and the "Soft Hand 17" condition were introduced to the Blackjack environment. The effectiveness of the basic strategy with these variations was analyzed.

- ⭐ **Complete Point Count Strategy with Variations: Double Down and Soft Hand 17**
  - This experiment extends the complete point count strategy to include variations like "Double Down" and "Soft Hand 17," evaluating its performance under these modified conditions.

- ⭐ **Complete Point Count Strategy with Variations with Different Number of Decks**
  - The performance of the complete point count strategy was examined across different numbers of decks (1, 2, 3) in the Blackjack environment, providing insights into how the number of decks affects the effectiveness of the strategy.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- "Beat the Dealer" by Edward O. Thorp for the basic strategy and point count techniques.
- Reinforcement Learning literature for foundational concepts and algorithms.
