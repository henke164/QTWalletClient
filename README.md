# QTWalletClient
Simple client to communicate with qt-wallets.

Example usage:

Set up QT wallet configfile:
```conf
rpcuser=Administrator
rpcpassword=SuperSecretPassword1336
rpcport=9050   
```

Communicate with wallet:
```C#
var client = new WalletClient(new WalletSettings {
    IpAddress = "http://localhost:9050",
    UserName = "Administrator",
    Password = "SuperSecretPassword1336"
});

// Get block count
var blockCountResponse = client.SendCommand(WalletCommands.GetBlockCount);
var blockCount = blockCountResponse.Result;
Console.WriteLine(blockCount);

// Get a new wallet address with alias "someAlias"
var addressResponse = client.SendCommand(WalletCommands.GetNewAddress, "someAlias");
var newAddress = addressResponse.Result;
Console.WriteLine(newAddress);
```
