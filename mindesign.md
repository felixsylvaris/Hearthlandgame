# Hearthland (Prototype)

## Overview

This is a simplified version of **Hearthland**, a strategy board game inspired by colonial empires, resource management, and trade networks.

The player expands from a homeland, develops colonies, extracts resources, builds industries, and maintains a global shipping network. Every turn the empire becomes slightly harder to manage, so balancing expansion, economy, and morale is essential.

## Objective

### Victory

Win by:

* Controlling **6 territories**.
* Every controlled territory must have sufficient troops and an unbroken sea connection to the homeland.
* Finish with **Churchill Mood at 9 or higher**.

### Defeat

Lose when **Churchill Mood reaches 0**.

Churchill Mood decreases by **1 each turn**.

It can be restored by consuming luxury goods:

* Tobacco: +1 Mood
* Whiskey: +2 Mood

---

# Map

The world consists of a **3×3 grid** of territories.

```
O — O — O
|   |   |
O — O — O
|   |   |
O — O — O
```

* 9 nodes (territories)
* 12 connections (sea lanes)

The center territory is the player's homeland.

---

# Territories (Nodes)

Each territory is represented by an object that may later contain:

* Population
* Resources
* Buildings
* Troops
* Production assignments
* Ownership
* Other gameplay properties

### Population

Each territory has a population value between **1 and 9**.

* Homeland always starts at **9 population**.
* Other territories are randomized between **1 and 9**.

### Occupation Requirement

Every territory requires a minimum number of troops to function.

* Homeland: 1 troop
* Other territories: 1–3 troops

Only sufficiently garrisoned territories generate income and produce resources.

---

# Connections (Sea Lanes)

Connections have maintenance costs.

* Inner cross connections: cost **1–5**
* Outer ring connections: cost **5–7**

Sea lanes connect colonies back to the homeland.

A colony only functions if it has an uninterrupted sea route to the homeland.

Ships may be returned to the homeland at any time, avoiding maintenance until redeployed.

---

# Resources

The prototype contains three raw resources:

* Grain
* Timber
* Tobacco

Each territory randomly generates resource deposits.

### Maximum deposits

* Grain: 2–7
* Timber: 1–5
* Tobacco: 1–3

These values represent the maximum possible extraction from the territory.

### Homeland

Starts with:

* 3 Grain deposits
* 2 Farms already built
* 2 Population assigned to farming

This produces **2 Grain per turn**.

---

# Population & Production

Population must be assigned to buildings.

Each assigned population produces **1 resource per turn**, provided:

* the correct building exists,
* deposits remain available,
* the territory is operational.

---

# Buildings

| Building   | Cost               | Production                             |
| ---------- | ------------------ | -------------------------------------- |
| Farm       | 1 Coin             | 1 Grain                                |
| Sawmill    | 1 Coin             | 1 Timber                               |
| Plantation | 2 Grain + 1 Coin   | 1 Tobacco                              |
| Brewery    | 2 Timber + 2 Coins | Converts Grain and Timber into Whiskey |

### Brewery Recipe

Consumes:

* 2 Grain
* 2 Timber

Produces:

* 2 Whiskey

---

# Economy

Coins are the main currency.

They are used to:

* construct buildings,
* recruit troops,
* build ships,
* maintain the empire.

Controlled territories generate tax income equal to their population.

A territory only pays taxes if:

* sufficient troops are present,
* it has a valid sea connection to the homeland.

---

# World Market

Resources may be traded with the global market.

| Resource | Buy | Sell |
| -------- | --: | ---: |
| Grain    |   2 |    1 |
| Timber   |   3 |    1 |
| Tobacco  |   4 |    2 |
| Whiskey  |   5 |    3 |

Initial world supply:

* Grain: 8
* Timber: 8
* Tobacco: 1
* Whiskey: 1

Maximum world stock for every resource is **10**.

---

# Military

The player starts with:

* 2 Troops

Recruitment cost:

* 2 Grain
* 1 Coin

Maintenance:

* 1 Grain each turn

If Grain is unavailable:

* Pay 1 Coin instead.

If neither Grain nor Coins are available:

* Churchill Mood decreases by 1.

Troops may instantly move between territories that:

* are under player control, and
* are connected by an active sea network.

If sea connections are lost, troops may become isolated.

---

# Ships

The player starts with:

* 1 Ship

Construction cost:

* 2 Timber
* 1 Coin

Ships are assigned to sea lanes.

Multiple ships may occupy the same connection, although only one is required.

Each occupied sea lane costs Coins every turn equal to its maintenance value.

Ships may be recalled to the homeland to eliminate maintenance costs until needed again.

---

# Expansion

The player is not required to occupy every territory.

It is possible to skip territories and control only strategically valuable ones.

Each territory tracks two important states:

* `sufficientTroops`
* `seaConnection`

Only territories where both values are **true**:

* generate taxes,
* produce resources.

Capturing a territory does not automatically produce resources.

Buildings must still be constructed and population assigned.

---

# Turn Sequence

Press **End Turn** to resolve:

* Resource production
* Brewery production
* Tax income
* Ship maintenance
* Troop upkeep
* Churchill Mood decrease
* Trade
* Victory and defeat checks

Resources are stored in a single global stockpile and may be used anywhere in the empire.

---

# Starting Conditions

The player begins with:

* 1 Homeland (center territory)
* 1 Ship
* 2 Troops
* 10 Coins

Homeland:

* Population: 9
* Required Troops: 1
* Grain Deposits: 3
* Farms Built: 2
* Population Working Farms: 2

Initial production:

* 2 Grain per turn.
