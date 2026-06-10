# Hyperscape-extractor
Can gaussian splats  be extracted from Meta Quest Hyperscape? Officially not... but maybe yes.

In case you succeed in extracting a "suspicious" file from Meta Quest (in com.meta.HyperscapeHmdCapture folder  or something like that) , try submitting it to [this page](https://jumpjack.github.io/Hyperscape-extractor/splat-extractor-google.html) or[ this new page](https://jumpjack.github.io/Hyperscape-extractor/splat-extractor-new.html) for analysis and SPZ extraction.

You can also try this procedure (no tested) to extract files from Quest using a PC:

- Enable developer mode on Quest;
- Connect your Quest 3 to PC via USB (note: with Sidequest it is also possible WiFi connection for ADB debugging);
- Launch Hyperscape Capture;
- Open one of your splats;
- From your PC, run "adb bugreport" connected via USB (you can use commandline from DOS windows, or SideQuest graphical interface); 
- A report  will be generated; inside the report you will find a txt file with the name of the bugreport;
- Inside the txt file, search for your world name in a line like _"HorizonWorldsApp: Event: Successfully fetched world metadata for world id: **33905429**....."_ ;
- Search the id with an underscore upfront and you should find a line  like _"HorizonWorldsApp: Asset: Registering asset loader 'CdnContainer_World_33905429...' (priority=0, assetContext=339054369..., hasNonDefaultAssetLoader=true)"_; in the next line there is the link to **download your splat** (valid only for you and only for this session), like _"HorizonWorldsApp: Worlds: Starting load of blob stream from https://scontent-ham3-1.xx.fbcdn.net/m1/v/t0.88647-6/An8vuxsKcVa203bnk6v-9-48h-mGsXD..... and range of size 320"_;
- Open the downloaded raw splat in [this page](https://jumpjack.github.io/Hyperscape-extractor/splat-extractor-google.html) to extract the .spz file in it;
- Load the .spz file in a desktop splat viewer like [https://scaniverse.8thwall.app/model-viewer/](https://scaniverse.8thwall.app/model-viewer/) by Scaniverse, or in [this one](https://wakufactory.jp/wxr/splats/splatview.html) which also runs on Quest itself.


Example output:
<img width="1329" height="857" alt="image" src="https://github.com/user-attachments/assets/d77b0f10-296b-4fba-a36c-d1894078afeb" />

Start offset of the chunk 14 containing the SPZ file should be always available (to be confirmed) at offset 0x010c of raw file downloaded from Quest device:

- 0x0100 00 03 3A 8E 76 E9 5A E6 00 00 00 00 **00 04 BF 1F**

End offset can be calculated from offset of next chunk stored at 0x012c:

- 0x0120 00 04 85 67 9C BF 7D 2C 00 00 00 00 **00 72 70 29**


Besides the SPZ files there are many other files and data inside the raw file, yet to be decoded.

----------------

- Splat editor: [https://superspl.at/editor](https://superspl.at/editor)
- Splat viewer: [https://www.wakufactory.jp/wxr/splats/splatview.html](https://www.wakufactory.jp/wxr/splats/splatview.html)

