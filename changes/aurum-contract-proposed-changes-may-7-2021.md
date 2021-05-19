---
description: Page listing all the proposed changes to the AURUM Masterchef contract.
---

# Aurum Contract - Changes May 7 2021

**Time Frame** : Proposed changes to be fully implemented by 7th May 2021 - Complete

For a reference of terms and understanding, please read the ["Terms and Glossary"](../help-and-faq/terms-and-glossary.md) section

All Changes need to, and will be going through the alchemist Timelock. Meaning there will be a set of changes posted to the Timelock in the Queue phase with a execute time delay set to 8 hours ahead. After the 8 hours have been hit, there will be an Execute Transaction.

Rollout plan

* ~~New Pools and LP's being added to the Masterchef will first be added to the Masterchef with a 1 ALLOCPOINT, which means the multiplier for that pool will be 0.01X. The reason for this is to ensure the pools can be added and the front end can be tested to be working \(in our developement environment\). This will require 8 hours lead time first, and then some time to develop the front end to ensure it can handled pools on the AURUM contract.~~
  * ~~Queue Transaction completed~~ 
  * ~~Execute Transaction complete~~d
  * ~~Testing found a bug with the BTCB pool, as such this pool will not be included.~~
  * ~~New QueueTransaction Created to remove BTCB \(set to 0 alloc\)~~
* Once testing is complete and front end is built a new set of queue transactions will be set to update all the new pools to the final ALLOCPOINT figures. In addition a number of queue transactions will be set to update the existing pools as per the proposed changes listed below. This is to update ALLOCPOINTS to their new figures and also set the pools that we are removing to 0 ALLOCPOINTS.

  We will then update the front end website to show the new pools for everyone to use stake their LP's against the pools. 

**Contracts + Functions to be interacted with** 

Aurum Timelock Contract - 0x49207BAA3a7332F0716788aa57B088D499bcc104

* QueueTransaction 
* ExecuteTranscation

Aurum Masterchef Contract  \(through the timelock only\) - 0x193765551a49eAD3aA8C693F19C4501710cD874d

* add - used to add all new pools to the masterchef
* set - used for all updates to the pools

{% hint style="info" %}
Important to note. The developers are not calling the functions add and set on the masterchef contract directly. This will be executed through the timelock. You can verify this to confirm that the caller of the function is the timelock address and not the dev wallet address. 
{% endhint %}

**Summary of changes to be made.  Check both tabs.** 

{% tabs %}
{% tab title="Pool Changes" %}
| **Change** | Token Name | Weight \(Alloc\) | Deposit Fee  \(depostiFeeBP |
| :--- | :--- | :--- | :--- |
| add | MIST Pool | 25x \(2500\) | 2% \(200\) |
| add | AURUM Pool | 10x \(1000\) | 2% \(200\) |
| ~~add~~ | ~~BTCB Pool~~ | ~~0.5X \(50\)~~ | ~~9% \(900\)~~ |
| add | BNB Pool | 1X \(100\) | 9% \(900\) |
| add | Cake Pool | 1x \(100\) | 9% \(900\) |
{% endtab %}

{% tab title="LP Changes" %}
| Change | LP Name | Weight \(Alloc\) | Deposit Fee |
| :--- | :--- | :--- | :--- |
| add | MIST-AURUM | 100x \(10000\) | 0% \(0\) |
| add | MIST-BNB | 50x \(5000\) | 2% \(200\) |
| update | AURUM-BUSD | 35x \(3500\) | 2% \(200\) |
| update | MIST-BUSD | 10x \(1000\) | 2% \(200\) |
| remove | AURUM-BNB | 0x \(0\) | 0% \(0\) |
| remove | BNB-BUSD | 0x \(0\) | 0% \(0\) |
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Setting a pools ALLOCPOINTS to 0 effectively disables the pool on the front end. \(it shows under the inactive section\). Users can always withdraw from the pool even after it has been set to 0. The only difference is that pool/lp will not earn any rewards
{% endhint %}

Below is a link to a google sheet in read only mode which has more details to the pool values themselves and can also be used to validate what the expected APRs would change to. Very important to understand that APR is based on the number of tokens staked in a pool as such it is very hard to estimate exactly how the APR's will be. In the sheet below we have used rough pool and LP balances to estimate the APR's but it gives a good idea how the multipliers will effect the overall APR's. Please ping an admin in the [Discord/Telegram](../community/socials.md) if you have any questions. 

[Link to Google Sheet for Calculations](https://docs.google.com/spreadsheets/d/1Y2Kn1ehd6yjN0oX6MtivfG8hNmTb-fpVWobr2DftUDU/edit?usp=sharing)

There are 3 tabs in the document listed above. Aurum, Mist and Proposed changes.   
Aurum / Mist can be used to compare against the current values in the pools

**AurumPoolCalcs\_ProsposedChanges \(07/05/2021\)** - Proposed changes, and what the pools will look like after the changes

