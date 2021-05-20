# Timelock

A Timelock is a smart contract that is used to ensure that developers and project owners cannot make quick changes to token and masterchef contracts. They provide a delay mechasim which requires the changes to be queued and then executed after the required time has passed.

This allows the community to ensure that the they are aware of upcoming changes.

We have 2 timelock contracts, one for each of the token contracts \(MIST and AURUM\)

### Timelock Address' Below 

**MIST Timelock Address** :  [0x5aa13aA7dCB8cb6D23e1Eb3424160BDD1323bBCE](https://bscscan.com/address/0x5aa13aA7dCB8cb6D23e1Eb3424160BDD1323bBCE#readContract)

**AURUM Timelock Address** : [0x21780Bb8BaF30598Dc70c48d7b74Ffad1268BdE3](https://bscscan.com/address/0x21780bb8baf30598dc70c48d7b74ffad1268bde3)

**Delay** :6 hours. 

When doing your own research, you can validate project mechanics by checking the following:

1\) Is the token owned by a developer wallet or a masterchef? It should be owned by a masterchef so that a developer cannot just call the mint function

2\) Is the masterchef owned by a developer wallet or a timelock. - It should be owned by a timelock, that way all major changes to pools have to be made via the timelock. 

