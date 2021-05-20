# Contracts

There are currently 2 tokens in the Alchemist DeFiVerse, and as such there are 2 contracts. One for MIST and another for AURUM. 

There are 3 contract types, Token, Masterchef and Timelock. Below is a description

_**Token Contract**_

This contract is the creator of the MIST token, the contract creates new MIST tokens and also controls the transfer process.  The token contract itself is owned by the MIST Masterchef, which means that only the masterchef can now mint new tokens. 

{% hint style="info" %}
_Always make sure when you interact with the project that you check the token contract ID. Scammers can easily create tokens that look like the original and trick you into buying fake tokens._ 
{% endhint %}

_**Masterchef Contract**_

The masterchef contract is the core of the functionality that is provided by the project. It controls emmission rates, minting, pools, deposit fees etc. As this contract owns the Token contract, it can mint new MIST based on the emission paramaters outlined in the contract configuration. The masterchef is owned by the timelock, which means that all major changes to the masterchef need to go through the timelock first. 

{% hint style="info" %}
_When doing your own research, check to confirm that the masterchef is the owner of the token, and that the masterchef is owned by the timelock contract. You can also check and confirm the dev wallet and fee address in the masterchef._ 
{% endhint %}

_**Timelock Contract**_

A timelock contract serves one function, that is to ensure that changes being made to the masterchef have to be staged and executed before they come into effect. The minimum time set for this timelock is technically 6 hours, but our project mandate is to run 8 hour updates. 

{% hint style="info" %}
_Timelock contracts have 3 main functions. Queue, Execute and Cancel. These functions are used to interact with the masterchef. In order for a change to be made the owner of the timelock contract has to "queue" a change first. Then wait for the time listed in the epochtime to complete before the execute function can be called._ 
{% endhint %}

| Contract | _**Address**_ |
| :--- | :--- |
| MIST Token | [0x6f8fe12cc34398d15b7d5a5ba933e550da1d099f](https://bscscan.com/address/0x6f8fe12cc34398d15b7d5a5ba933e550da1d099f) |
| MIST Masterchef | [0x43404359bB38F5135aB8e25c62902015a49A0074](https://bscscan.com/address/0x43404359bB38F5135aB8e25c62902015a49A0074) |
| MIST TimeLock | [0x5aa13aA7dCB8cb6D23e1Eb3424160BDD1323bBCE](https://bscscan.com/address/0x5aa13aA7dCB8cb6D23e1Eb3424160BDD1323bBCE) |
| AURUM Token | [0x49207baa3a7332f0716788aa57b088d499bcc104](https://bscscan.com/address/0x49207baa3a7332f0716788aa57b088d499bcc104) |
| AURUM Masterchef | [0x193765551a49ead3aa8c693f19c4501710cd874d](https://bscscan.com/address/0x193765551a49ead3aa8c693f19c4501710cd874d) |
| AURUM Timelock | [0x21780bb8baf30598dc70c48d7b74ffad1268bde3](https://bscscan.com/address/0x21780bb8baf30598dc70c48d7b74ffad1268bde3) |

