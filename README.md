# HexaEight Tokens Installable
This Repository contains the links to the Latest Release of HexaEight Tokens along with HexaEight Issued Certificates


### HexaEight Tokens is currently available for the following Platforms

#### [Windows (64 bit version)](https://www.hexaeight.com/downloads/win_x64/HexaEight_Token_Issuer_winx64.zip)

>The zip file contains an executable for Windows Platform. 
>
>The zip file also contains the [HexaEight Issued Certificate (.hic) file](https://github.com/HexaEightTeam/HexaEight_Tokens/blob/main/win_x64/HexaEight_Token_Issuer.hic) which is tied to this executable
>
>The current HexaEight Verified hash (Not the same as the File hash) of Windows x64 Executable is  c92e3d93f871f7a69ca9cf78c697a5ee99bbb9dab1258eedfe9523b10f02cc14280256422104aa9357f234afe8aa258da237dfc3110d572b84096a923dfc6873
>
  
  
#### Linux (64 bit version) - Link should be available soon

#### Osx (64 bit version) - Link should be available soon

#### ARM (Raspberry pi version) - Link should be available soon


In order to run HexaEight Tokens on your machine you need a certficate file issued by HexaEight also known as HexaEight Issued Certificates (HIC)

### What Are HIC Files:

HexaEight Releases are NOT digitally signed using Code certificates.  As such they may be prone to modifications.  Hence we have introduced HexaEight Certificates which are an alternative to Code signing certificates for quick verification.

HexaEight Issued Certificates uses Authenticated Encryption Technlogy to establish the authenticty of the Executable. While HexaEight Issued Certificates DOES NOT prevent an attacker from tampering with the executable, it does help in verifying the AUTHENTICITY of executable prior to execution.

**NOTE: HexaEight Executables protected by HIC are not allowed to change the name of the executable under normal conditions, the executable wont run if the name of the executable is changed.**

### Sample output of the executable.

```
c:\tokens>HexaEight_Token_Issuer.exe --help

HexaEight_Token_Issuer 1.6.801
(c) HexaEight.com All Rights Reserved

  -a, --apikey                 Set Rapid API Key

  -s, --setresourceowner       Set Resource Owner

  -g, --generatemachinecode    Generate Machine Code

  -o, --showowner              Displays Current Resource Owner

  -c, --clientid               Register and Generate a New Client ID For an App

  -f, --fetchcert              This is used Internally by HexaEight Team

  -h, --filehash               Show the SHA512 Hash of this file

  -v, --verifycert             Use this to Verify the Authencity of this Software

  --help                       Display this help screen.

  --version                    Display version information.
  
  ```
  
 
 ### How to verify the AUTHENTICITY of the executable ?
 
 ### Method 1: Visit Our [E-Verification Web Page](https://e-verify.hexaeight.com) to instantly verify the certificate.
 
  1.  Copy the contents of [HexaEight_Token_Issuer.hic file](https://github.com/HexaEightTeam/HexaEight_Tokens/blob/main/win_x64/HexaEight_Token_Issuer.hic) and paste it in the box titled "Paste HexaEight Issued Certificate Token Below"
  
  2.  Get the Hash of the Executable using a tool or use powershell command annd Paste It in the box titled "Paste your File Hash".
    
```
PS C:\tokens> Get-FileHash .\HexaEight_Token_Issuer.exe -Algorithm SHA512 | Format-List

Algorithm : SHA512
Hash      : xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
Path      : C:\tokens\HexaEight_Token_Issuer.exe
```

  3. Click the "Validate Certificate" Button.

You will see a message which will confirm if the file is safe to execute in your environment. Remove the file if the verification fails.


### METHOD 2: The old fashioned way of validating the hash manully without the HIC file. 
 
a) Get the Hash of the Executable File using a tool or use powershell commannd 
    
```
PS C:\tokens> Get-FileHash .\HexaEight_Token_Issuer.exe -Algorithm SHA512 | Format-List

Algorithm : SHA512
Hash      : xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
Path      : C:\tokens\HexaEight_Token_Issuer.exe
```

b) Get the Version Propeties of the Executable file by using the following command
    
```
PS C:\tokens> Get-ItemProperty .\HexaEight_Token_Issuer.exe |  Format-list -Property VersionInfo

VersionInfo : File:             C:\Data\tokens\HexaEight_Token_Issuer.exe
              InternalName:     HexaEight_Token_Issuer.dll
              OriginalFilename: HexaEight_Token_Issuer.dll
              FileVersion:      1.6.801.0
              FileDescription:  HexaEight_Token_Issuer
              Product:          HexaEight Token Issuer Service
              ProductVersion:   1.6.801
              Debug:            False
              Patched:          False
              PreRelease:       False
              PrivateBuild:     False
              SpecialBuild:     False
              Language:         Language Neutral
```

In order to verify the hash, you need to take four properties from the file: 

1. File name of Executable : HexaEight_Token_Issuer.exe
2. File Hash of Executable : (whatever was obtained in step 1) XXXXXXXXXXXXXXXXx
3. Product shown in Version info followed by a space and Fileversion: HexaEight Token Issuer Service 1.6.801.0

HexaEight_Token_Issuer.exe213176019588..................CB106370BHexaEight Token Issuer Service 1.6.801.0

There should be no leading or trailing spaces. Paste this in an online tool https://sha512.online/ and click on the generate hash button. You will see a generated  hash that should match with the VerifiedHash. If the hash matches, the executable is safe.

```
-----------------------------------------------------------
FileName : HexaEight_Token_Issuer.exe
VerifiedHash : c92e3d93f871f7a69ca9cf78c697a5ee99bbb9dab1258eedfe9523b10f02cc14280256422104aa9357f234afe8aa258da237dfc3110d572b84096a923dfc6873
HashAlgorithm : SHA512
Description : HexaEight Token Issuer Service 1.6.801.0
Publisher : AUTH.HEXAEIGHT.COM
Issuer : AUTH.HEXAEIGHT.COM
Certificate Issued At : 27528087
Certificate Expiry At : 27787275
AuthenticData : This File or Sofware [HexaEight_Token_Issuer.exe] has been verified successfully.

The Hash can also be manually verified by combining the following properties below:
FILENAME followed By HASHOFTHISFILE followed by DESCRIPTION
The above SHA512 Hash should match with c92e3d93f871f7a69ca9cf78c697a5ee99bbb9dab1258eedfe9523b10f02cc14280256422104aa9357f234afe8aa258da237dfc3110d572b84096a923dfc6873

Note: This message wont be displayed if this File or Software was altered or tampered.
This is a Software Publisher Certificate Published by AUTH.HEXAEIGHT.COM and Certified by AUTH.HEXAEIGHT.COM
This message was generated at 5/5/2022 1:12:09 PM
-----------------------------------------------------------
```

### METHOD 3: Run the program with the verifycert option to validate the executable using the HIC file. (You can use this option after Method #1 succeeds to re-verify the executable multiple times)

You should see a message that contains the authenticated encrypted information from the HIC file which was decrypted using the Hash of the File which would prove the authenticity of the executable.

```
c:\tokens>HexaEight_Token_Issuer.exe --verifycert

-----------------------------------------------------------
FileName : HexaEight_Token_Issuer.exe
VerifiedHash : c92e3d93f871f7a69ca9cf78c697a5ee99bbb9dab1258eedfe9523b10f02cc14280256422104aa9357f234afe8aa258da237dfc3110d572b84096a923dfc6873
HashAlgorithm : SHA512
Description : HexaEight Token Issuer Service 1.6.801.0
Publisher : AUTH.HEXAEIGHT.COM
Issuer : AUTH.HEXAEIGHT.COM
Certificate Issued At : 27528087
Certificate Expiry At : 27787275
AuthenticData : This File or Sofware [HexaEight_Token_Issuer.exe] has been verified successfully.

The Hash can also be manually verified by combining the following properties below:
FILENAME followed By HASHOFTHISFILE followed by DESCRIPTION
The above SHA512 Hash should match with c92e3d93f871f7a69ca9cf78c697a5ee99bbb9dab1258eedfe9523b10f02cc14280256422104aa9357f234afe8aa258da237dfc3110d572b84096a923dfc6873

Note: This message wont be displayed if this File or Software was altered or tampered.
This is a Software Publisher Certificate Published by AUTH.HEXAEIGHT.COM and Certified by AUTH.HEXAEIGHT.COM
This message was generated at 5/5/2022 1:12:09 PM
-----------------------------------------------------------
```



 
