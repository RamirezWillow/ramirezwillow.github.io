```
(function () {
        var _Cookie = {
            createCookie: function (name, value,days,path,domain,secure) {
                //设置cookie有效天数
                if(days){
                    var date = new Date();
                    date.setTime(date.getTime()+days*24*60*60*1000);
                    var expires = date.toUTCString();
                }else {
                    var expires = "";
                }
                //value编码避免非法字符
                var cookieString = name +"="+escape(value);
                if(expires)cookieString+="; expires="+expires;
                if(path)cookieString+="; path="+escape(path);
                if(domain)cookieString+="; domain"+escape(domain);
                if(secure)cookieString+="; secure";
                document.cookie = cookieString;
            },
            getCookie: function (name) {
                var nameEquals = name+"=";
                var crumbs = document.cookie.split(';');
                for(var i=0;i<crumbs.length;i++){
                    var crumb = crumbs[i];
                    if(crumb.indexOf(nameEquals)==0){
                        return unescape(crumb.substring(nameEquals.length,crumb.length));
                    }
                }
                return null;
            },
            deleteCookie: function (name) {
                createCookie(name,'',-1);
            }
        };
    }());
```