---
title: epsilon-NFA
---

# NFA with $epsilon$-Transitions

- make a transition from one state to another state without consuming any of the input string

## Formally. An $epsilon$-NFA is a tuple $(Q, sigma, delta, q0, f)$

- While everything except $delta$ is as for NFA's
- $delta : Q x (sigma union {epsolon}) -> set Q [ epsilon notin sigma]$

## $epsolon$-closure of states

- Given $epsilon$-NFA A = $(Q, sigma, delta, q0, f)$
- Eclose(q) = the set of states that we can reach from q using $epsilon$-transitions only
- $epsilon$ transition is a transition that does not consume any input

## $Eclose(q)$ is defined as

- contains the set q
- if $p in Eclose(q)$, and $r in delta$(p,$epsilon$) then $r in Eclose(q)$ and no other states

## Extended transition function

- $hat delta (q, epsilon) = Eclose(q)$
- $hat delta (q, xa) = p in hat delta (q,x) union  Eclose(delta(p,a))$
  + where x is a string and a is letter

## Language of an $epsilon$-NFA

- Same as NFA

## Theorem. For every $epsilon$-NFA A there is a DFA D such that L(A) = L(D).

- let A = $(Q, sigma, delta, q0, f)$ be given.
- Construct DFA D = $(Q_D, sigma, delta_D, q_D, f_D)$
  + $Q_D = P(Q)$ power set of Q
  + $Q_D = Eclose(q_0)$
  + $F_D = {delta <= Q : delta union F =/ null}$
  + $delta_D(S, a)
    * S is a state

# Regular Expressions

- EF, L(EF) -> L(E)L(F) -- Concatenation
- + is or

## Operations on languages
  
- if L and M are languages (L, M in sigma **), then LM

## Formal Proof

- case r = EF
- E loses its final states

- case r = $E**$
- start state becomes final state
