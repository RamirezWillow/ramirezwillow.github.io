JavaScript实现对账号加星号
=======================

**今天没事随手写了一个对账户号码中间进行星号遮掩的方法，没有考虑太多，要是有朋友觉得可以提高的地方可以在github上帮忙！**

```javascript
  (function () {
    var tel = "173 0212 9629";
    var bankCard = "3453 5343 5347 6575 091";
    
    var asterisksCard = function (account) {
        //区分手机号和银行卡号条件:卡号首位是否为1
        account = account.replace(/\s/g, '');
        var aLength = account.length;
        if (account[0] === '1') {
            //手机号码
            return account.substr(0, 3) + "****" + account.substring(7, 11);
        } else {
            //银行卡号
            var asterisks = "";
            var tail = aLength % 4;
            var sLenght = 0;
            var start = 0;
            if (tail != 0) {
                sLenght = aLength - 4 - tail;
                start = aLength - tail;
            } else {
                sLenght = aLength - 8;
                start = aLength - 4;
            }
            for (var i = 0; i < sLenght; i++) {
                asterisks += '*';
            }
            return account.substr(0, 4) + asterisks + account.substring(start, aLength);
        }
    };
    
    asterisksCard(tel);
    asterisksCard(bankCard);
}());
```
