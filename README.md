# Perfect-Information Game Analysis: Two-Player Blackjack Model

## Overview
This repository contains an academic project devoted to the analysis of a **perfect-information sequential game** using **backward induction**.

The project models a simplified Blackjack-type game with two players and a dealer, where all actions, card values, and outcomes are known in advance. The main goal is to determine optimal strategies for all participants and identify the subgame perfect equilibrium.

The analysis demonstrates how rational decision-making unfolds in multi-player sequential games with deterministic outcomes.

---

## Project Description
The game is designed as a **perfect-information game**, meaning:
- All players observe all previous actions
- There is no hidden information
- There is no randomness in outcomes
- The deck order is fixed and known in advance

The game is represented as a **rooted directed tree**, and the solution concept is **backward induction**.

---

## Players
- **Player 1 (P1)** – moves first
- **Player 2 (P2)** – reacts to Player 1
- **Dealer (D)** – moves last and minimizes players’ payoff

---

## Game Rules
- Card values: integers from 1 to 10
- Target sum: **15**
- Objective: reach a sum as close as possible to 15 without exceeding it
- All cards are face-up
- Available actions:
  - **Hit** – take the next card
  - **Stand** – stop drawing cards
- Game ends when all players stand or someone exceeds 15

---

## Payoff Structure
At the end of the game, each player is compared with the dealer:
- Player busts (>15): payoff = -1
- Dealer busts: all non-busted players get +1
- No busts: the player closer to 15 wins
- Tie: payoff = 0

Total payoff is computed relative to the dealer.

---

## Simplified Scenario
Initial configuration:
- Deck: [3, 4, 5]
- Player 1 initial sum: 5
- Player 2 initial sum: 4
- Dealer initial sum: 3

This reduced setting allows full enumeration of the game tree and explicit payoff comparison.

---

## Methodology
- Construction of the full **game tree**
- Identification of decision and terminal nodes
- Computation of payoffs at terminal nodes
- Application of the **backward induction algorithm**:
  1. Dealer minimizes total payoff
  2. Player 2 maximizes payoff given dealer’s response
  3. Player 1 maximizes payoff anticipating Player 2 and dealer

The equilibrium is obtained by recursively eliminating suboptimal actions.

---

## Backward Induction Results
The backward induction analysis yields the following optimal strategies:
- Player 1: **Hit**
- Player 2: **Hit**
- Dealer: **Hit**

Final outcome:
- Player 1 = 8
- Player 2 = 8
- Dealer = 8
- Equilibrium payoff = **0**

Despite the presence of high-payoff terminal outcomes, rational play prevents players from achieving a positive payoff.

---

## Modified Game: Cooperative Bonus
An extension of the model introduces a **cooperative bonus**:
- If both players beat the dealer, each receives an additional +0.5 payoff

After recomputing payoffs and reapplying backward induction, the equilibrium **remains unchanged**.

### Key Insight
The dealer’s minimizing strategy blocks the cooperative bonus, making it theoretically visible but strategically unattainable.

---

## Key Findings
- Perfect information does not guarantee favorable outcomes
- Optimal opponent play neutralizes potential advantages
- Backward induction provides a clear and systematic equilibrium solution
- Not all rule modifications affect equilibrium behavior

---

## Repository Structure
