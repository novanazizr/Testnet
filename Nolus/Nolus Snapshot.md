# Testnet


## Services 
* Validator : [Click Here](https://nolus.explorers.guru/validator/nolusvaloper1e2al5nyvp22mhz0c4x4l5mq9796z2amfmzxtcf)
* Dashboard : [Click Here](https://dashboard.nolus.ultramannode.my.id/)
#### Chain ID : nolus-rila | Latest Version Tag : v0.1.43 | Snapshot Date : 04-Mar-2023 12:26

## Public Endpoints 

* api : https://api.nolus.ultramannode.my.id
* rpc : https://rpc.nolus.ultramannode.my.id
* grpc : https://grpc.nolus.ultramannode.my.id
* grpc-web : https://grpc-web.nolus.ultramannode.my.id

## Snapshot Instructions

## Stop service and reset data 
```bash
sudo systemctl stop nolusd
cp $HOME/.nolus/data/priv_validator_state.json $HOME/.nolus/priv_validator_state.json.backup
rm -rf $HOME/.nolus/data
```

## Download latest snapshot
```bash
curl -L http://snapshot.nolus.ultramannode.my.id/nolus/nolus-snapshot-20230304.tar.lz4 | tar -Ilz4 -xf - -C $HOME/.nolus
mv $HOME/.nolus/priv_validator_state.json.backup $HOME/.nolus/data/priv_validator_state.json
```

## Restart service and check logs
```bash
sudo systemctl start nolusd && sudo journalctl -u nolusd -f --no-hostname -o cat
```
