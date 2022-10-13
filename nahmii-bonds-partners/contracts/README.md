# Contracts

OlympusDAO uses this factory contract to deploy both CustomTreasury and CustomBond contracts that play the central roles of the bond mechanism.

The CustomTreasury contract is deployed from OlympusDAO's factory contract, [OlympusProFactory](broken-reference). It manages the inflow and outflow of the bond payout tokens and bond revenue.

Each partner would have a unique CustomTreasury contract. Check out the respective partner page for the exact contract address.

The CustomBond contract is deployed from OlympusDAO's factory contract, [OlympusProFactory](broken-reference). It takes cares of the bonding mechanism such as bond purchase and the redemption of payout tokens.

Each partner would have a unique CustomBond contract. Check out the respective partner page for the exact contract address.
