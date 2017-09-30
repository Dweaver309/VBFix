# VBFix
Use Visual Basic with Microsoft Visual Studio 2015 and .Net Micro Framework 4.4

How To Use Visual Basic in .Net Micro Framework 4.4

1.	Install Visual Studio 2015  
Note: 2017 doesn’t support with NMF4.4

https://go.microsoft.com/fwlink/?LinkId=532606&clcid=0x409

2.	Install the assemblies:

https://github.com/NETMF/netmf-interpreter/releases/download/v4.4-RTW-20-Oct-2015/MicroFrameworkSDK.MSI

3.	Install the this file to set the Visual Studio 2015 environment for NMF 4.4

https://github.com/NETMF/netmf-interpreter/releases/download/v4.4-RTW-20-Oct-2015/NetMFVS14.vsix

4.	There is a bug in the VS 2015 visual basic emulator

The fix:

From this page:

http://informatix.miloush.net/microframework/Articles/VBinMF44.aspx?_setCulture=cs-CZ






3 easy steps to make Visual Basic working with the legacy compiler
1.	Add "/load:C:\Program Files (x86)\Microsoft .NET Micro Framework\v4.4\Assemblies\le\mscorlib.pe" command line option into the registry (including the quotation marks).
For the standard emulator, you need to create an AdditionalCommandLineOptions string value under the HKLM\SOFTWARE\WOW6432Node\Microsoft\.NETMicroFramework\v4.4\Emulators\Microsoft key.
Key should look like this:
 ![Screenshot](https://github.com/Dweaver309/VBFix/blob/master/Reg.png)


 
2.	Add <VBRuntime>C:\Program Files (x86)\Microsoft .NET Micro Framework\v4.4\Assemblies\le\Microsoft.VisualBasic.dll</VBRuntime> to the project file.

3.	You probably want to modify the .NET Micro Framework targets file instead ("C:\Program Files (x86)\MSBuild\Microsoft\.NET Micro Framework\v4.4\VisualBasic.targets" ) so that all Visual Basic projects work as they are.To the same file, add the explicit runtime reference: <ItemGroup> <Reference Include="Microsoft.VisualBasic"/> </ItemGroup>

Next save a template so  you don’t have to make the project file each time.


How to use the template file

 

The File will be saved here:

C:\Users\User\Documents\Visual Studio 2015\My Exported Templates

To use the template select it here. My templates were called StandardVB and StandardVBConsole.


![Screenshot](https://github.com/Dweaver309/VBFix/blob/master/VS2015.png)
 


My template is here:

https://github.com/Dweaver309/VBFix/blob/master/StandardVB.zip

It’s fixed!
