STARS INFOTECH IT CLASSES - STATIC WEBSITE

Files:
- index.html
- courses.html
- contact.html
- css/style.css

LOCAL TEST:
1. Extract ZIP.
2. Open index.html.
3. Test Home, Courses and Contact.
4. Contact form is demo only and does not save data.

AWS EC2 + IIS:
1. Launch a Windows Server EC2 instance using an instance type currently shown as Free Tier eligible for your AWS account.
2. Allow inbound TCP 80 for HTTP.
3. Allow RDP 3389 only from your own public IP (/32).
4. Install IIS:
   Install-WindowsFeature -Name Web-Server -IncludeManagementTools
5. Create C:\Sites\StarsInfotech
6. Copy all website files into that folder.
7. IIS Manager -> Sites -> Add Website
   Site name: StarsInfotech
   Physical path: C:\Sites\StarsInfotech
   Binding: http, Port 80
8. Browse http://EC2-PUBLIC-IP

TROUBLESHOOTING:
Get-Service W3SVC
Test-NetConnection localhost -Port 80
Invoke-WebRequest http://localhost
netstat -ano | findstr :80
nslookup YOUR-DOMAIN

COMMON SCENARIOS:
- EC2 stopped
- IIS service stopped
- IIS site stopped
- Port 80 blocked
- Windows Firewall blocking HTTP
- HTTP 404 missing page
- HTTP 403 IIS configuration/permissions
- Old content after deployment
- DNS pointing to wrong server
- High CPU / slow website

NOTE: This is a static website. The enquiry form is only a demo. For MSSQL-backed login/registration, use the separate ASP.NET Core project.
