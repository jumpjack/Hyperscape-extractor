# Hyperscape-extractor
Can gaussian splats  be extracted from Meta Quest Hyperscape? Officially not... but maybe yes.

In case you succeed in extracting a "suspicious" file from Meta Quest (in com.meta.HyperscapeHmdCapture folder  or something like that) , try submitting it to [this page](https://jumpjack.github.io/Hyperscape-extractor/splat-extractor-google.html) for analysis and SPZ extraction.

Example output:
<img width="1329" height="857" alt="image" src="https://github.com/user-attachments/assets/d77b0f10-296b-4fba-a36c-d1894078afeb" />

Start offset of the chunk 14 containing the SPZ file should be always available (to be confirmed) at offset 0x010c of raw file downloaded from Quest device:

- 0x0100 00 03 3A 8E 76 E9 5A E6 00 00 00 00 **00 04 BF 1F**

End offset can be calculated from offset of next chunk stored at 0x012c:

- 0x0120 00 04 85 67 9C BF 7D 2C 00 00 00 00 **00 72 70 29**


Besides the SPZ files there are many other files and data inside the raw file, yet to be decoded.
