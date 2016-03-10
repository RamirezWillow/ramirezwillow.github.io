crate AddClass() and RemoveClass() to replace jquery's.
===============================================================

```
(function () {
            function hasClass(obj,classname){
                var judge = obj.indexOf(classname);
                if(judge<0){
                    return -1;
                }else {
                    return 1;
                }
            }
            function addClass(obj,classname){
                if(hasClass(obj,classname)<0){
                    obj.className += ' '+classname;
                }
            }
            function removeClass(obj,classname){
                if(hasClass(obj,classname)>=0){
                     return obj.replace(classname,'');
                }
            }
        }());
```
