# FAQ

## Why do I want to use Bondii?

It allows you to buy your favourite DeFi tokens at a discounted rate. Besides, you are helping the protocol to accumulate their own liquidity in the process. This keeps your goal and the protocol's aligned.

## What is the relationship between Bondii and Nahmii?

Bondii is a service offered by [Nahmii](https://nahmii.io/). Nahmii provides infrastructure, expertise, and exposure to other protocols by setting up the bond mechanism in exchange for a fee.

## Do I receive Nii from Olympus Pro bonds?

You do not receive Nii from Bondii bonds. Instead, you get the native governance token the protocol offers. For example, protocol X would reward bonds in X instead of Nii.

## Why is the Bond ROI negative?&#x20;

At times, you'll see that the bond discount turns negative, meaning you'd pay a premium from the market in order to bond. **You should not bond during this time**, as you can buy the same tokens but at a cheaper price from the market. As time goes on, the discount will slowly increase, until it reaches a positive discount again. The negative discount can be caused by different factors:

1. **High demands for bonds:** Bonds offer users the ability to purchase tokens at a market discount. However, this price is dependent on the demands of bonds. When there is a high demand, the bond price goes up, and vice versa. The demand may be so high that it may cause the bond price to inflate above the market price.
2. **Sharp decreases in price:** At times, when a token experiences a sharp decrease in price, it takes time for the bond price to decrease to match the new token price. This causes a temporary negative discount, until the bond price matches the market value again.

## How is the bond price/discount determined?

The bond discount is determined by the following formula:

&#x20;                    _bondDiscount=(marketPrice−bondPrice) / marketPrice_

The bond price is determined by the debt ratio of the system and a scaling variable called the Bond Control Variable (BCV). This allows us to control the rate at which the bond price increases. Note that the bond price is independent of the market price, as no data from price oracles are used when determining the bond price.

&#x20;                   _bondPrice = debtRatio \* BCV_

The debt ratio is the amount of reward tokens owed to the bonders by the protocol, divided by the total supply of the reward tokens. A higher debt ratio implies a huge demand for bonds, resulting in a higher bond price, and vice versa.

&#x20;                 _debtRatio = tokenOwed / tokenSupply_

## What is the catch? Buying tokens at a discount sounds too good to be true.

Tokens purchased through a bond are not released to the bonder all at once. Instead, they vest linearly over time. This prevents the bonder from selling their tokens all at once for a quick profit.

## What parameters can be adjusted?

### BCV

BCV directly affects the bond price - the higher the BCV, the higher the bond price. As a higher bond price makes bonds less attractive, the protocol can adjust this value to tune the bond capacity.

### Maximum Bond Size

This controls the maximum amount of reward tokens a user can purchase through a bond. It is set as a percentage of the total supply and typically ranges between 0.03-0.05% of the total supply.

### Bond Vesting Term

A bond vests linearly to the bonder over a length of time, called the bond vesting term. This means the bonder can claim a portion of the reward tokens each day, with all rewards being claimable at the end of the term.

