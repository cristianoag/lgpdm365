# lgpdm365
M365 DLP rule package to support Brazilian LGPD personal information detection

This is a set of rules to improve detection of personal information in compliance to the Brazilian LGPD requirements.

To install the package, follow the steps below:

1. Connect to the M365 tenant using the following commands

$UserCredential = Get-Credential
$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $Session -DisableNameChecking

2. Save the LGPDRulePackage.xml file in your hard drive
3. Import the file using the following command

New-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "LGPDRulePackage.xml" -Encoding Byte -ReadCount 0))

4. Create the DLP detection rule using the detection types created

Brazil Legal Entity Number (CNPJ)
Brazil General Address
Brazil Zip Code
Brazil Phone Numbers
Brazil Email Address
Brazil CPF Number
Brazil National ID Card (RG)
