
# Outputs

As hinted in the previous section, outputs define where the bitcoins are actually going. We must have at least one output and can have lots of outputs. An exchange may batch transactions, for example, and pay out a lot of people at once instead of generating a single transaction for every single person that requests Bitcoins.

Outputs each have two fields: amount and ScriptPubKey. Amount is the amount of bitcoin being assigned and is specified in satoshis, or 1/100,000,000th of a Bitcoin. This allows us to divide Bitcoin very finely, down to 1/100th of a penny in USD terms as of this writing.

ScriptPubKey is much like ScriptSig in that it has to do with Bitcoin's smart contract language SCRIPT. Think of ScriptPubKey as the lock box that can only be opened by the holder of the key. A one-way safe that can receive deposits from anyone, but can only be opened by the owner of the safe.

### Test Driven Exercise

Parse the transaction outputs.


```python
from tx import TxOut

class TxOut(TxOut):
    
    @classmethod
    def parse(cls, s):
        '''Takes a byte stream and parses the tx_output at the start
        return a TxOut object
        '''
        # s.read(n) will return n bytes
        # amount is 8 bytes, little endian, interpret as int
        # script_pubkey is a variable field (length followed by the data)
        # get the length by using read_varint(s)
        # return an instance of the class (cls(...))
        pass

```
