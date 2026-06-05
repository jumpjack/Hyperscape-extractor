- raw file: [link](https://github.com/jumpjack/Hyperscape-extractor/blob/main/splats/001/An9xFUJb0SYNbWJbclQak_CMHIBwr91i6xjHHKJU3hzhRtJuEEoyjyHmBb-zgkXOg3lR-xONoIzoNjA_Ei3Sf2bDz_ekrKfokOwo_6Dn97uv9zVSrO8N4xV3gYHAn7kd)
- Taken from this post: https://stackoverflow.com/questions/79874128/how-to-open-convert-a-gaussian-splatting-file-of-unknown-type
- Further discussion: https://www.reddit.com/r/GaussianSplatting/comments/1tnkj5f/comment/oos14if/?context=1
- Original filename: An9xFUJb0SYNbWJbclQak_CMHIBwr91i6xjHHKJU3hzhRtJuEEoyjyHmBb-zgkXOg3lR-xONoIzoNjA_Ei3Sf2bDz_ekrKfokOwo_6Dn97uv9zVSrO8N4xV3gYHAn7kd2ZpyRdfcsGM  (add .bin extension to open it in my script)
- **Extraction method: unknown**
- Number of splats declared: 313611
- Number of splats found in the spz file: 313611

SPZ file viewed in [online viewer](https://scaniverse.8thwall.app/model-viewer/):

<img width="424" height="633" alt="image" src="https://github.com/user-attachments/assets/14084c83-2b95-405b-b540-773d08be365c" />


Splat preview in Meta Quest:
<img width="1100" height="618" alt="image" src="https://github.com/user-attachments/assets/db552e2f-20bc-45c6-9961-1a1780e32e24" />

Analysis:

| #   | Offset (Hex) | Found by | Marker / ID           | Length (dec) | Magic number | Description | Notes |
|-----|--------------|-----------|-----------------------|-------------:|--------------|-------------|-------|
| 000 | 0x00000140   | HEADER    | ID_0                  |           31 | 00 03 38 01  | . | . |
| 001 | 0x0000015F   | SCAN      | ZXSHPHSM3             |           81 | 5A 58 53 48  | Reversed: 3MSHPHSXZ | |
| 002 | 0x000001B0   | SCAN      | NZRHLPMT              |           80 | 4E 5A 52 48  | Reversed: TMPLHRZN | Template Horizon? |
| 003 | 0x00000200   | SCAN      | NZRHLPMT              |           80 | 4E 5A 52 48  | Reversed: TMPLHRZN | Template Horizon? |
| 004 | 0x00000250   | SCAN      | ALPSTNEC              |           80 | 41 4C 50 53  | Reversed: CENTSPLAT | Center Splat? |
| 005 | 0x000002A0   | SCAN      | DNERRTXT              |           80 | 44 4E 45 52  | Reversed: TXTRREND | Texture Render? |
| 006 | 0x000002F0   | SCAN      | ALPSXYLP              |           80 | 41 4C 50 53  | Reversed: PLYXSPLA | PLY X Splat? |
| 007 | 0x00000340   | SCAN      | ALPSKSAM              |           48 | 41 4C 50 53  | Reversed: MASKSPLA | Mask for splat? |
| 008 | 0x00000370   | OFFSET    | ID_0                  |          257 | 7B 20 62 75  | Small JSON file | |
| 009 | 0x00000471   | OFFSET    | ZSTD magic number     |        65288 | 28 B5 2F FD  | Compressed in ZSTD format; starts with "SEBD" (53 45 42 44) | 3MSHPHSXZ chunk? |
| 010 | 0x00010379   | OFFSET    | ZSTD magic number     |         1121 | 28 B5 2F FD  | JSON compressed in ZSTD format; refers to `horizon:: platform_api:: WorldPlayerConfigPlatformComponent` | TMPLHRZN chunk? |
| 011 | 0x000107DA   | OFFSET    | ZSTD magic number     |          648 | 28 B5 2F FD  | JSON compressed in ZSTD format; refers to `HyperscapePlayer` and `horizon:: platform_api:: PlayerPlatformComponent` | TMPLHRZN chunk? |
| 012 | 0x00010A62   | OFFSET    | ZSTD magic number     |         2077 | 28 B5 2F FD  | JSON compressed in ZSTD format; contains `splat_count` and `views`; appears to be a clone of `cluster_centroids.json` from `xxxx_visibility_clusters` | CENTSPLAT chunk? |
| 013 | 0x0001127F   | OFFSET    | TXTR                  |       240800 | 2C 00 00 00  | Unknown; starts with `2C 00 00 00 54 58 54 52`, followed by many zeros and then `C0 AB 03 00` | TXTRREND chunk? |
| 014 | 0x0004BF1F   | OFFSET    | none                  |      7188746 | 1F 8B 08 00  | **Gaussian splat in SPZ format** | PLYXSPLA chunk? |
| 015 | 0x00727029   | OFFSET    | ZSTD magic number     |       693071 | —            | Alpha mask for splat? | MASKSPLA chunk? |
| 016 | 0x007D0378   | SCAN      | Malformed ZSTD magic number |    771981 | 28 B5 2F B4 | Malformed ZSTD chunk; unknown | |



