Stop service

```
sudo systemctl stop nolusd
```

reset data

```
cp $HOME/.nolus/data/priv_validator_state.json $HOME/.nolus/priv_validator_state.json.backup
```
```
rm -rf $HOME/.nolus/data
```

Download Snapshot nolus

```
curl -L https://snapshots.garznode.xyz/nolus-testnet/snapshot_latest.tar.lz4 | tar -Ilz4 -xf - -C $HOME/.nolus
```

```
mv $HOME/.nolus/priv_validator_state.json.backup $HOME/.nolus/data/priv_validator_state.json
```

Restart service

```
sudo systemctl restart nolusd
```

Check Logs

```
sudo journalctl -u nolusd -f --no-hostname -o cat
```