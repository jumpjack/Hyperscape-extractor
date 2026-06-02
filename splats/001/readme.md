- raw file: [link](https://github.com/jumpjack/Hyperscape-extractor/blob/main/splats/001/An9xFUJb0SYNbWJbclQak_CMHIBwr91i6xjHHKJU3hzhRtJuEEoyjyHmBb-zgkXOg3lR-xONoIzoNjA_Ei3Sf2bDz_ekrKfokOwo_6Dn97uv9zVSrO8N4xV3gYHAn7kd)
- Taken from this post: https://stackoverflow.com/questions/79874128/how-to-open-convert-a-gaussian-splatting-file-of-unknown-type
- Further discussion: https://www.reddit.com/r/GaussianSplatting/comments/1tnkj5f/comment/oos14if/?context=1
- Original filename: An9xFUJb0SYNbWJbclQak_CMHIBwr91i6xjHHKJU3hzhRtJuEEoyjyHmBb-zgkXOg3lR-xONoIzoNjA_Ei3Sf2bDz_ekrKfokOwo_6Dn97uv9zVSrO8N4xV3gYHAn7kd2ZpyRdfcsGM  (add .bin extension to open it in my script)
- **Extraction method: unknown**
- Number of splats declared: 313611
- Number of splats found in the spz file: 313611

SPZ file viewed in online viewer:

<img width="424" height="633" alt="image" src="https://github.com/user-attachments/assets/14084c83-2b95-405b-b540-773d08be365c" />


Splat preview in Meta Quest:
<img width="1100" height="618" alt="image" src="https://github.com/user-attachments/assets/db552e2f-20bc-45c6-9961-1a1780e32e24" />

Analysis:

|   # | Offset (Hex) | Origin  | Marker / ID | Length | Header (4B)  | |
| --: | :----------- | :------ | :---------- | --------: | :---------- | ----
| 000 | 0x00000140   | HEADER  | ID_0        |        31 | 00 03 38 01 |
| 001 | 0x0000015F   | SCAN    | ZXSHPHSM3   |        81 | 5a 58 53 48 |
| 002 | 0x000001B0   | SCAN    | NZRHLPMT    |        80 | 4e 5a 52 48 |
| 003 | 0x00000200   | SCAN    | NZRHLPMT    |        80 | 4e 5a 52 48 |
| 004 | 0x00000250   | SCAN    | ALPSTNEC    |        80 | 41 4c 50 53 |
| 005 | 0x000002A0   | SCAN    | DNERRTXT    |        80 | 44 4e 45 52 |
| 006 | 0x000002F0   | SCAN    | ALPSXYLP    |        80 | 41 4c 50 53 |
| 007 | 0x00000340   | SCAN    | ALPSKSAM    |        48 | 41 4c 50 53 |
| 008 | 0x00000370   | HEADER  | ID_0        |       257 | 7b 20 62 75 | small JSON file
| 009 | 0x00000471   | HEADER  | ZSTD_DATA   |     65288 | 28 b5 2f fd | Compressed in ZSTD format, starts by "SEBD" (53 45 42 44)
| 010 | 0x00010379   | HEADER  | ZSTD_DATA   |      1121 | 28 b5 2f fd | Long JSON files, refers to horizon::platform_api::WorldPlayerConfigPlatformComponent
| 011 | 0x000107DA   | HEADER  | ZSTD_DATA   |       648 | 28 b5 2f fd | Long json file, refers to HyperscapePlayer and horizon::platform_api::PlayerPlatformComponent
| 012 | 0x00010A62   | HEADER  | ZSTD_DATA   |      2077 | 28 b5 2f fd | Small json files, contains splat_count and views; clone of cluster_centroids.json found in C:\Users\cassi\Downloads\hyperscape-hack\com.meta.HyperscapeHmdCapture\files\xxxx_visibility_clusters on device?
| 013 | 0x0001127F   | HEADER  | TXTR        |    240800 | 2c 00 00 00 | Unknown, starts by 2C 00 00 00 54 58 54 52 followed by many zeros and then C0 AB 03 00
| 014 | 0x0004BF1F   | HEADER  | ID_33A8E    |   7188746 | 1f 8b 08 00 | **Gaussian splat in SPZ format**
| 015 | 0x00727029   | HEADER  | ZSTD_DATA   |        6_ |             | Malformed zstd chunk; unkwnown.
