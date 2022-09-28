# Cardano Leader Slot
Scheduled Block Checker for Cardano Stakepool Operators. 
*Warning: At the moment these scriptis are just working for the currents epochs.*

Lightweight and Portable Scheduled Blocks Checker for Next, Current and Previous Epochs.
No cardano-node required, data is taken from blockfrost.io and armada-alliance.com

Note: This is a reworking of old python script ScheduledBlocks.py 
available on https://github.com/papacarp/pooltool.io.git , Ouroboros TPraos version: https://github.com/asnakep/ScheduledBlocks and using Ouroboros Praos updated code from https://github.com/dostrelith678/cardano-leader-logs


## Prerequisites:
- Python 3.8
- pip (Python package installer)
- libsodium library

## Setup:

# Koios API version:
- clone this repository using git: ``` git clone https://github.com/QuixoteSystems/cardano-leader-slot.git ```
- execute inside the newly cloned directory: ```pip install -r pip_requirements.txt   ```  to install all needed python package requirements
- make sure you can access your vrf.skey file (you can copy in it a path of your choice) and remember to keep it as read only ``` chmod 400 vrf.skey ```

- Set Variables on lines 31-33 of leaderslot_blockfrost.py:

```
PoolTicker = "YOUT_POOL_TICKER"
VrfKeyFile = ('YOUR_VRF_FILE_PATH')
pool_id_bech32 = "YOUR_POOL_ID:_pool1..."
```


# Blockfrost API version (It will be remove from this project):
- clone this repository using git: ``` git clone https://github.com/QuixoteSystems/cardano-leader-slot.git ```
- execute inside the newly cloned directory: ```pip install -r pip_requirements.txt   ```  to install all needed python package requirements
- get a project id on blockfrost.io
- make sure you can access your vrf.skey file (you can copy in it a path of your choice) and remember to keep it as read only ``` chmod 400 vrf.skey ```

- Set Variables on lines 26-34 of leaderslot_blockfrost.py:
```
### Set your own timezone -----------------------------------------###

local_tz = pytz.timezone('')

### Set These Variables ###

BlockFrostId = "YOUR_IP"

PoolId = "YOUR_POOL_ID_HEX

PoolTicker = "YOUR_POOL_TICKER"

VrfKeyFile = ('YOUR_VRF_FILE_PATH')

### -------------------------------------------------------------- ###
```


## Usage:
``` python3 leaderslot.py ```

## Output: 
- a *console output* with all the slots assigned for next, current and previous Epochs
