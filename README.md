### bitcoin_tools
---
https://github.com/sr-gi/bitcoin_tools

```py
from bitcoin_tools.core.keys import generate_keys, store_keys
from bitcoin_tools.wallet import generate_wif, generate_btc_addr

sk, pk = generate_keys()

btc_addr = generate_btc_addr(pk)

store_keys(sk.to_pem(), pk.to_pem(), btc_addr)

generate_wif(btc_addr, sk)


from bitcoin_tools.core.keys import load_keys
from bitcoin_tools.core.transaction import TX

btc_addr = "xxx"
sk, pk = load_keys(btc_addr)

prev_tx_id = "xxx"
prev_out_index = 0

value = 6163910
fee = 230 * 240

destination_btc_addr = "xxx"

tx = Tx.build_from_io(prev_tx_id, prev_out_index, value - fee, destination_btc_addr)
tx.sign(sk, 0)

print "hex: " + tx.serialize()

tx.display()


from bitcoin_tools.core.transaction import TX

hex_tx = "xxx"
tx = TX.deserialize(hex_tx)

tx.display()


from bitcoin_tools.analysis.status.data_dump import utxo_dump
from bitcoin_tools.analysis.status.utils import parse_ldb

f_utxos = "decoded_utxos.txt"
f_parsed_utxos = "parsed_utxos.txt"

coin = 'bitcoin'

parse_ldb(f_utxos)
utxo_dump(f_utxos, f_parsed_utxos, coin)
```

```
```

```
```


