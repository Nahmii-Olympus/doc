---
description: >-
  This guide aims to help onboard protocol developers into the Olympus Pro bonds
  marketplace.
---

# Getting Started

## Supplying Information to Nahmii

Fill up this [notion form](https://notionforms.io/forms/olympus-pro-application) to register your interest in becoming a partner of Olympus Pro.

1. Total pilot emissions (e.g. 1,000,000 ABC token or USD equivalent).
2. Token contract address
3. Token LP contract address

## Launching the Bond Program

Nahmii will work with you to set up the necessary contracts to start the bond program. The following are the high-level action items required by both parties:

**By Nahmii:**

1\. Nahmii will deploy the factory contract, [~~OlympusProFactory~~](https://etherscan.io/address/0xb1F69deCb09D8490E3872FE26D27a7b83493cd65).

2\. Nahmii will use the factory contract to deploy Nahmii Bonds `Custom Treasury` and Nahmii Bonds `Custom Bond` contracts, with the `owner` set to your **multisig address**.

{% hint style="info" %}
At this point, you are in full control of the Custom Treasury and Custom Bond contracts.
{% endhint %}

**By Partners:**

1\. You will call `toggleBondContract` in the Custom Treasury contract and pass in the `Custom Bond` contract address.

2\. You will set the vesting block of the `Custom Bond` contract by calling `setBondTerms`. 46,200 is approximately 7 days.

<figure><img src="../.gitbook/assets/setbondterms.png" alt=""><figcaption><p>The first parameter should be set to 0</p></figcaption></figure>

3\. You will transfer your **payout tokens** to the `Custom Treasury` contract. You may send one week or the full term of emissions to your custom treasury.

4\. You will initialise the `Custom Bond` contract. **Initialising the bond will allow bond purchases - this function is only called once.**

| Parameter       | Overview                                        |
| --------------- | ----------------------------------------------- |
| controlVariable | Controls bond price and capacity                |
| vestingTerm     | Vesting term (typically 7 days)                 |
| minimumPrice    | Minimum price of the bond                       |
| maxPayout       | Max payout as a % of total supply               |
| maxDebt         | Ceiling on how many bonds can be outstanding    |
| initialDebt     | Initial debt used for initializing the contract |

<figure><img src="../.gitbook/assets/initbond.png" alt=""><figcaption><p>Nahmii will supply the initialisation parameters</p></figcaption></figure>

5\. A policy team member from Nahmii will suggest BCV and other relevant parameters to be used. The next section will give you an overview of the adjustments.

{% hint style="info" %}
Once the Custom Bond contract is initialised, users can start purchasing&#x20;
{% endhint %}

## Adjusting Bond Control Variables (BCV)

Through a weekly policy meeting with our team, we may suggest changes to the BCV parameter that controls the bond capacity. For example, a higher BCV value translates to a higher bond price, which has an effect of reducing the bond capacity.

Because the partner owns the `Custom Bond` contract, they need to apply the changes themselves. The Nahmii team will provide guidance on the appropriate parameters to use.

To adjust the BCV, call `setAdjustment` function and pass in the appropriate arguments.

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption><p>setAdjustment function from the Custom Bond contract</p></figcaption></figure>

Overview of the parameters:

| Parameters | Overview                                    |
| ---------- | ------------------------------------------- |
| addition   | Addition/subtraction boolean                |
| increment  | Increment/decrement step of BCV             |
| target     | Target BCV                                  |
| buffer     | Buffer between changes (in Ethereum blocks) |

## Adding New Bond Types

When adding new bond types there are two options:

1\. Create a new `Custom Bond` contract and use the existing treasury. This will only work **if the same payout token is used**.

2\. Create another set of `Custom Bond` and `Custom Treasury` contracts.

If you decide to go with option 1, it is as simple as calling `toggleBondContract` from the `Custom Treasury` contract and passing in the new `Custom Bond` contract address. As before, the bond will have to be initialised. A Nahmii policy member will assist in this as well.

{% hint style="info" %}
Olympus will create the new `Custom Bond` contract via [~~OlympusProFactory~~](broken-reference)~~~~
{% endhint %}

For option 2, you will just follow the steps as outlined in [Launching the Bond Program](getting-started.md#launching-the-bond-program) section.
