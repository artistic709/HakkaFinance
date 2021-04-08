# Hakka staking model

## Usage
#### stake HAKKA token to get:
- voting power (untransferable)
- wHAKKA ERC20 token

#### repay wHAKKA to redeem HAKKA

## Vault
Each user can have multiple vaults. A vault contains 3 infos: `hakkaAmount`, `wAmount`, and `unlockTime`.

## Staking rate model
While the main staking contract is immutable, the math model can be changed.

## Staking rate
The amount of voting power and wHAKKA received per HAKKA locked is determined by staking rate, which depends on lockup period.

### current implementation
There's a underlying variable `stakingRateMax`, which is `1` by default and grows gradually (2x every year).

### rate
staking rate = `stakingRateMax * timeFactor`
- lock 360 days to get max rate(1x)
- lock 180 days to get 1/2 rate
- lock 90 days to get 1/4 rate
- lock 30 days to get 1/12 rate
