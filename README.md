Just copy and paste the line in the .ps1 file onto powershell terminal:

PS C:\Users\XXXX> netsh wlan show profiles | foreach {If ($_.Contains("    All User Profile     :")) {$_.Substring($_.indexof(':')+2)}} | % {netsh wlan show profiles name=$_ key=clear} | findstr -I "Key SSID"
