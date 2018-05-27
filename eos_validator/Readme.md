# eos_onchain_validator.py 
#### is used to validate the balances by the snapshot.cvs and the legitimacy of the contracts on EOSIO blockchain.

#### Requirements
This tool use Python 2.7 and with several packages, install with: pip install --upgrade xxx
```
simplejson
requests
argparse
```

### Usage:
```
usage: eos_onchain_validator.py [-h] --action ACTION --config CONFIG

EOSIO onchain validator tool.

optional arguments:
  -h, --help       show this help message and exit
  --action ACTION  contract_validate|chain_validate
  --config CONFIG  validator.json config file path
```

### validator.json 
```
snapshot_csv: the absolute path of snapshot.csv
nodeosd_host: ip:host for the noedeosd ip and http port, for example 127.0.0.1:8888
test_time: when you want to test validate balance speed, you can set into your favorite number, defalut 1.
```

### Validate the balances
```
python eos_onchain_validator.py --action chain_validate --config validator.json
```

### Others
 - The validation of snapshot.cvs
    - this can be done by query the ETH fullnode, and it need to build the fullnode by yourself. I prefer to use the version which get the most consensus from the community.
 - Test the validate balance speed
    - just use a little snapshot.csv and change the TEST_TIME value to your favorite number

### TODO:
 - find another way to decrease HTTP request times. 
    - keepalive to nodeosd has been tried, nodeosd will close the conntection