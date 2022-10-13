# FAQ

## Why do I want to use Bondii?

It allows you to buy your favourite DeFi tokens at a discounted rate. Besides, you are helping the protocol to [accumulate their own liquidity](https://docs.olympusdao.finance/pro/#benefits-of-olympus-pro-for-protocols) in the process. This keeps your goal and the protocol's aligned.

## What is the relationship between Bondii and Nahmii?

Bondii is a service offered by [Nahmii](https://nahmii.io/). Nahmii provides infrastructure, expertise, and exposure to other protocols by setting up the bond mechanism in exchange for a fee.

### &#x20;<a href="#do-i-receive-ohm-from-olympus-pro-bonds" id="do-i-receive-ohm-from-olympus-pro-bonds"></a>

You do not receive OHM from Olympus Pro bonds. Instead, you get the native governance token the protocol offers. For example, protocol X would reward bonds in X instead of OHM.

### &#x20;<a href="#why-is-the-bond-roi-negative" id="why-is-the-bond-roi-negative"></a>

At times, you'll see that the bond discount turns negative, meaning you'd pay a premium from the market in order to bond. **You should not bond during this time**, as you can buy the same tokens but at a cheaper price from the market. As time goes on, the discount will slowly increase, until it reaches a positive discount again. The negative discount can be caused by different factors:

1.  1\.

    **High demands for bonds:** Bonds offer users the ability to purchase tokens at a market discount. However, this price is dependent on the demands of bonds. When there is a high demand, the bond price goes up, and vice versa. The demand may be so high that it may cause the bond price to inflate above the market price.
2.  2\.

    **Sharp decreases in price:** At times, when a token experiences a sharp decrease in price, it takes time for the bond price to decrease to match the new token price. This causes a temporary negative discount, until the bond price matches the market value again.

### &#x20;<a href="#how-is-the-bond-price-discount-determined" id="how-is-the-bond-price-discount-determined"></a>

The bond discount is determined by the following formula:

bondDiscount=(marketPrice−bondPrice) / marketPricebondDiscount = (marketPrice - bondPrice)\ /\ marketPrice

The bond price is determined by the debt ratio of the system and a scaling variable called the Bond Control Variable ([BCV](https://docs.olympusdao.finance/references/glossary#bcv)). This allows us to control the rate at which the bond price increases. Note that the bond price is independent of the market price, as no data from price oracles are used when determining the bond price.

bondPrice=debtRatio∗BCVbondPrice = debtRatio \* BCV

The debt ratio is the amount of reward tokens owed to the bonders by the protocol, divided by the total supply of the reward tokens. A higher debt ratio implies a huge demand for bonds, resulting in a higher bond price, and vice versa.

debtRatio=tokenOwed / tokenSupplydebtRatio = tokenOwed\ /\ tokenSupply

### &#x20;<a href="#what-is-the-catch-buying-tokens-at-a-discount-sounds-too-good-to-be-true." id="what-is-the-catch-buying-tokens-at-a-discount-sounds-too-good-to-be-true."></a>

Tokens purchased through a bond are not released to the bonder all at once. Instead, they vest linearly over time. This prevents the bonder from selling their tokens all at once for a quick profit.

### &#x20;<a href="#what-parameters-can-be-adjusted" id="what-parameters-can-be-adjusted"></a>

BCV directly affects the bond price - the higher the BCV, the higher the bond price. As a higher bond price makes bonds less attractive, the protocol can adjust this value to tune the bond capacity.

This controls the maximum amount of reward tokens a user can purchase through a bond. It is set as a percentage of the total supply and typically ranges between 0.03-0.05% of the total supply.

A bond vests linearly to the bonder over a length of time, called the bond vesting term. This means the bonder can claim a portion of the reward tokens each day, with all rewards being claimable at the end of the term.

Why do I want to use Olympus Pro?

What is the relationship between Olympus Pro and OlympusDAO?

Do I receive OHM from Olympus Pro bonds?

Why is the Bond ROI negative?

How is the bond price/discount determined?

What is the catch? Buying tokens at a discount sounds too good to be true.

What parameters can be adjusted?
