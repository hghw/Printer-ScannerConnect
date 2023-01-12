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

RUN: 
1. run project
![image](https://user-images.githubusercontent.com/89172440/212001971-d557d3d1-0edc-4e67-87ac-4ecbf491d2a8.png)
2. setup (choose location file save):
![image](https://user-images.githubusercontent.com/89172440/212002295-03d0eb43-46b3-4c32-8791-f7626babaad3.png)
3. select shortcut setting and click Scan:
![image](https://user-images.githubusercontent.com/89172440/212002470-85c9f584-283d-4202-b53a-94200c653129.png)
4. done: 
![image](https://user-images.githubusercontent.com/89172440/212002580-3f96019f-505b-4f4f-8daa-46e81fb422bb.png)


