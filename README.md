# Learning Behavior Driven Development

## Basics

- Article: https://dannorth.net/introducing-bdd/

### BDD provides a "uniquitious language" for analysis

```
As a [X]
I want [Y]
so that [Z]
```

- Y is some feature
- X is some person (or role)
- Z is the value of the feature

<br>

- Describe the acceptance criteria of the story in terms of *scenarios*

```
GIVEN some initial context (the givens)
WHEN an event occurs
THEN ensure some outcomes
```

#### Example

*As a* customer
*I want* to withdraw cash from an ATM
*so that* I don't have to wait in line at the bank

- How do we know when we have delivered this story?
- There are several different facets to this story:
    - Account may be in credit
    - Account may be overdrawn but within the overdraft limit
    - Account may be overdrawn beyond the overdraft limit

<br>

- Using the given-when-them template, first two scenarios may look like

+Scenario 1: Account is in credit+
*Given* the account is in credit
*And* the card is valid
*And* the dispender contains cash
*When* the customer requests cash
*Then* ensure the account is debited
*And* ensure the account is debited
*And* ensure the card is returned

<br>

+Scenario 2: Account is overdrawn past the overdraft limit+
*Given* the account is overdrawn
*And* the card is valid
*When* the customer requests cash
*Then* ensure a rejection message is displayed
*And* ensure cash is not dispensed
*And* ensure the card is returned