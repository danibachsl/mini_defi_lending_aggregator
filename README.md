### Mini DeFi lending aggregator

## What it does?
1. **We start swapping 1 ETH token for DAI Stablecoin on Uniswap**
2. **The bot scans the supply APY for DAI tokens on AAVE & Compound Finance**
3. **Then it deposits all DAI tokens on the one having the highest supply APY available**
4. **This way we know we get the best yield available on our savings**

## 📃 Instructions to run
0. **Install dependencies in project directory(working with node v12.10.)**
</br>```npm i```
1. **Install ganache-cli (globaly)**
</br>```npm i -g ganache-cli```
2. **In 1st terminal window fork mainnet with ganache-cli**
</br>```ganache-cli -p 7545 -f <https://YOUR_ETH_PROVIDER>```
3. **(in 2nd window) Run script to get DAI from UniswapV2**
</br>```trufle exec script/0_get_dai.js```
4. **Run script to check DAI APY and allocated accordingly**
</br>```trufle exec script/1_deposit.js```
5. **Run script to again check DAI APY and reallocate funds if there will be a difference**
</br>```trufle exec script/2_rebalance.js```
</br>
</br>Todo, add script for withdraw/end supplying
</br>!Note: To reset data, restart ganache-cli