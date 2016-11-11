##UIWebView中使用cookie实现免登陆

*最近帮忙朋友上架一个纯h5的app，就是用原生做了一层壳。
可是发现，每次重新开启app的时候之前登录的信息就不存在了，所以就想到了要需要用刀UIWebView的cookie来获取用户数据实现免登陆。*

###下面贴代码


```Object-C
NSArray*nCookies = [[NSHTTPCookieStorage sharedHTTPCookieStorage]cookies];
    NSHTTPCookie*cookie;
    for(id cookies in nCookies)
    {
        if([cookies isKindOfClass:[NSHTTPCookie class]])
        {
            cookie=(NSHTTPCookie*)cookies;
            if([cookie.name isEqualToString:@"touch_id"]) {
                NSNumber*sessionOnly = [NSNumber numberWithBool:cookie.sessionOnly];
                NSNumber*isSecure = [NSNumber numberWithBool:cookie.isSecure];
                NSArray*cookies = [NSArray arrayWithObjects:cookie.name, cookie.value, sessionOnly, cookie.domain, cookie.path, isSecure,nil];
                [[NSUserDefaults standardUserDefaults]setObject:cookies forKey:@"cookies"];
                
                break;
            }
        }
    }
```