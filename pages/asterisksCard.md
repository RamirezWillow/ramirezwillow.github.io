JavaScript实现对账号加星号
=======================

**今天没事随手写了一个对账户号码中间进行星号遮掩的方法，没有考虑太多，要是有朋友觉得可以提高的地方可以在github上帮忙！**

```javascript
(function () {
    function hasClass(obj, classname) {
        var judge = obj.className.indexOf(classname);
        if (judge < 0) {
            return -1;
        } else {
            return 1;
        }
    }

    function addClass(obj, classname) {
        if (hasClass(obj, classname) < 0) {
            obj.className += ' ' + classname;
        }else {
            console.log("The object has already contained the class name!");
        }
    }

    function removeClass(obj, classname) {
        if (hasClass(obj, classname) >= 0) {
            obj.className = obj.className.replace(classname, '');
        }else {
            console.log("The object doesn't contain the class name!");
        }
    }

    var fc = document.querySelector('.ac');
    addClass(fc,'font_size');
    addClass(fc,'font_size');
    addClass(fc,'font_color');
    removeClass(fc,'fontsize');
}());
```
