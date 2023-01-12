# ScannerConnect
 
A C# interface for the TWAIN image capture API, that also includes a toolkit layer, a diagnostic application and a sample application.

Features
Runs on Windows (.NET or Mono)
Runs on Linux and Mac OS X (Mono)
32bit and 64bit support
Follows TWAIN "best practices"

## Using the new twaindsm.dll
By default NTwain will use the newer [data source manager](http://sourceforge.net/projects/twain-dsm/files/TWAIN%20DSM%202%20Win/)
(twaindsm.dll) if available. To override this behavior set the PlatformInfo's PreferNewDSM flag to false. This is necessary due to some older sources not working with the newer dsm.

If not, download twaindsm.dll at link "https://sourceforge.net/projects/twain-dsm/" -> Unzip the file, we have:
![image](https://user-images.githubusercontent.com/89172440/212000198-e90000b6-a642-4e45-936a-df47468fb6ed.png)
-> Paste at the path "C:\Windows"
```
#!c#
// go back to using twain_32.dll under windows,
// do this once at app startup.
NTwain.PlatformInfo.Current.PreferNewDSM = false;

```


If the application process is going to be running in 64-bit then this flag will have no effect and you will 
always need to have the twaindsm installed. 

If the scanner's TWAIN driver is still 32-bit then you'll have need to compile the application exe in x86 or you won't see the driver.
