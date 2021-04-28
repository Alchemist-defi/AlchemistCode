# Contracts

The project currently has 2 tokens, and as such there are 2 contracts. One for MIST and another for AURUM. 

There are 3 contract types, Token, Masterchef and Timelock. Below is a description

_**Token Contract**_

This contract is the creator of the MIST token, it is what is used to MINT new mist and controls the transfer process.  The token contract itself is owned by the MIST Masterchef, which means that only the masterchef can now MINT new tokens. 

{% hint style="info" %}
_Always make sure when you interact with the project that you check the token contract ID. Scammers can easily create tokens that look like the original and trick you into buying fake tokens._ 
{% endhint %}

_**Masterchef Contract**_

The masterchef contract is the core of the functionality that is provided by the project. It controls emmision rates, minting, pools, deposit fees and referalls. As this contract owns the Token contract, it can misnt new mist based on the emissions paramaters outlined in the contract configuration. The masterchef is owned by the timelock, which means that all major changes to the masterchef need to go through the timelock first. 

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
| Mist Token | [0x6f8fe12cc34398d15b7d5a5ba933e550da1d099f](https://bscscan.com/address/0x6f8fe12cc34398d15b7d5a5ba933e550da1d099f) |
| Mist Masterchef | [0x43404359bB38F5135aB8e25c62902015a49A0074](https://bscscan.com/address/0x43404359bB38F5135aB8e25c62902015a49A0074) |
| Mist TimeLock | [0x5aa13aA7dCB8cb6D23e1Eb3424160BDD1323bBCE](https://bscscan.com/address/0x5aa13aA7dCB8cb6D23e1Eb3424160BDD1323bBCE) |
| Aurum Token | [0x49207baa3a7332f0716788aa57b088d499bcc104](https://bscscan.com/address/0x49207baa3a7332f0716788aa57b088d499bcc104) |
| Aurum Masterchef | [0x193765551a49ead3aa8c693f19c4501710cd874d](https://bscscan.com/address/0x193765551a49ead3aa8c693f19c4501710cd874d) |
| Aurum Timelock | [0x21780bb8baf30598dc70c48d7b74ffad1268bde3](https://bscscan.com/address/0x21780bb8baf30598dc70c48d7b74ffad1268bde3) |

