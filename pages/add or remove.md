crate AddClass() and RemoveClass() to replace jquery's.
===============================================================

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        html {
            font-size: 20px;
        }
        .font_size {
            font-size: 40px;
        }
        .font_color {
            color: yellow;
            background-color: black;
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="ac">==========ADD CLASS=============</div>
    <script>
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
                }
            }

            function removeClass(obj, classname) {
                if (hasClass(obj, classname) >= 0) {
                   obj.className = obj.className.replace(classname, '');
                }
            }

            var fc = document.querySelector('.ac');
            addClass(fc,'font_size');
            console.log(fc.className);
            addClass(fc,'font_color');
            console.log(fc.className);
            removeClass(fc,'font_size');
            console.log(fc.className);
        }());
    </script>
</body>
</html>
```
