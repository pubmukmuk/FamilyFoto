


# step 1. initial raw files
<pre>
[08/25/25 09:54:07] INFO     summarizes files:                          summary_utils.py:59
                             P:\dev.mukmuk\FamilyFoto\inbox                                
                  📊 Media File Summary                   
┏━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━┓
┃    Folder    ┃       Camera        ┃ File Type ┃ Count ┃
┡━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━┩
│ lindsey-2019 │       Unknown       │   .heic   │   7   │
│ lindsey-2019 │       Unknown       │   .mov    │  16   │
│ lindsey-2019 │      iPhone 7       │   .jpg    │   1   │
│ lindsey-2019 │      iPhone 8       │   .jpeg   │   2   │
│ lindsey-2019 │      iPhone 8       │   .jpg    │   7   │
│ lindsey-2020 │ Canon EOS REBEL SL1 │   .jpeg   │   3   │
│ lindsey-2020 │       Unknown       │   .heic   │  203  │
│ lindsey-2020 │       Unknown       │   .jpeg   │   2   │
│ lindsey-2020 │       Unknown       │   .jpg    │  13   │
│ lindsey-2020 │       Unknown       │   .mov    │  233  │
│ lindsey-2020 │       Unknown       │   .png    │  100  │
│ lindsey-2020 │  iPhone 11 Pro Max  │   .jpg    │   1   │
│ lindsey-2020 │      iPhone 6s      │   .jpg    │   2   │
│ lindsey-2020 │      iPhone 7       │   .jpg    │   1   │
│ lindsey-2020 │    iPhone 7 Plus    │   .jpeg   │   1   │
│ lindsey-2020 │      iPhone 8       │   .jpg    │   8   │
│ lindsey-2020 │    iPhone 8 Plus    │   .jpeg   │   2   │
│ lindsey-2020 │      iPhone XR      │   .jpeg   │   7   │
│ lindsey-2021 │       Unknown       │   .heic   │ 2135  │
│ lindsey-2021 │       Unknown       │   .jpg    │  88   │
│ lindsey-2021 │       Unknown       │   .mov    │ 1769  │
│ lindsey-2021 │       Unknown       │   .png    │  777  │
│ lindsey-2021 │         iOS         │   .jpg    │   4   │
│ lindsey-2021 │      iPhone 11      │   .jpeg   │   8   │
│ lindsey-2021 │      iPhone 11      │   .jpg    │  36   │
│ lindsey-2021 │    iPhone 11 Pro    │   .jpg    │   1   │
│ lindsey-2021 │      iPhone 12      │   .jpg    │   2   │
│ lindsey-2021 │      iPhone 7       │   .jpg    │   1   │
│ lindsey-2021 │    iPhone 7 Plus    │   .jpeg   │   7   │
│ lindsey-2021 │    iPhone 7 Plus    │   .jpg    │   2   │
│ lindsey-2021 │      iPhone 8       │   .jpg    │  44   │
│ lindsey-2021 │    iPhone 8 Plus    │   .jpeg   │   1   │
│ lindsey-2021 │      iPhone XR      │   .jpeg   │  11   │
│ lindsey-2021 │      iPhone XR      │   .jpg    │   6   │
└──────────────┴─────────────────────┴───────────┴───────┘

</pre>

# step 2. convert approx. 2345 heic  files to jpg - delete original
<br>(.venv) 
<br>Mike@Charlie MINGW64 /p/dev.mukmuk/FamilyFoto (main)
<br>$ python -m tools.convert_inbox_heic --delete-original
<br>start: 10:00 AM
<br>end: approx. 0+30+00 minutes, 10:20 AM
<br>[  ] no logger...
<br>[  ] all output to console...

<pre>
✅ Converted: f0dd156062ab5797-photo.HEIC → f0dd156062ab5797-photo.jpg
🗑️ Deleted original: P:\dev.mukmuk\FamilyFoto\inbox\lindsey-2020\12 - Dec\f29b6b22375a2f8e2-photo.HEIC
✅ Converted: f29b6b2375a2f8e2-photo.HEIC → f29b6b2375a2f8e2-photo.jpg
🗑️ Deleted original: P:\dev.mukmuk\FamilyFoto\inbox\lindsey-2020\12 - Dec\f5ee3acc93c05b6d2-photo.HEIC
✅ Converted: f5ee3ac93c05b6d2-photo.HEIC → f5ee3ac93c05b6d2-photo.jpg
🗑️ Deleted original: P:\dev.mukmuk\FamilyFoto\inbox\lindsey-2020\12 - Dec\f5ffba77e2d368bd9-photo.HEIC
✅ Converted: f5ffba7e2d368bd9-photo.HEIC → f5ffba7e2d368bd9-photo.jpg
🗑️ Deleted original: P:\dev.mukmuk\FamilyFoto\inbox\lindsey-2020\12 - Dec\fb89d5ddf04cec250-photo.HEIC
✅ Converted: fb89d5df04cec250-photo.HEIC → fb89d5df04cec250-photo.jpg
🗑️ Deleted original: P:\dev.mukmuk\FamilyFoto\inbox\lindsey-2020\12 - Dec\fc221577d4c92e6ba-photo.HEIC
✅ Converted: fc22157d4c92e6ba-photo.HEIC → fc22157d4c92e6ba-photo.jpg
🗑️ Deleted original: P:\dev.mukmuk\FamilyFoto\inbox\lindsey-2020\12 - Dec\fd768588d97b3a75c-photo.HEIC
✅ Converted: fd76858d97b3a75c-photo.HEIC → fd76858d97b3a75c-photo.jpg
🗑️ Deleted original: P:\dev.mukmuk\FamilyFoto\inbox\lindsey-2020\12 - Dec\ff015d66ee0f6ccce-photo.HEIC
✅ Converted: ff015d6ee0f6ccce-photo.HEIC → ff015d6ee0f6ccce-photo.jpg
🗑️ Deleted original: P:\dev.mukmuk\FamilyFoto\inbox\lindsey-2019\08 - Aug\a35b2799c2139188f-photo.HEIC
✅ Converted: a35b279c2139188f-photo.HEIC → a35b279c2139188f-photo.jpg
🗑️ Deleted original: P:\dev.mukmuk\FamilyFoto\inbox\lindsey-2019\08 - Aug\ff655c66142bcd415-photo.HEIC
✅ Converted: ff655c6142bcd415-photo.HEIC → ff655c6142bcd415-photo.jpg
🗑️ Deleted original: P:\dev.mukmuk\FamilyFoto\inbox\lindsey-2019\09 - Sep\f7205555af5c28a32-photo.HEIC
✅ Converted: f720555af5c28a32-photo.HEIC → f720555af5c28a32-photo.jpg
🗑️ Deleted original: P:\dev.mukmuk\FamilyFoto\inbox\lindsey-2019\10 - Oct\940345771546ac57b-photo.HEIC
✅ Converted: 94034571546ac57b-photo.HEIC → 94034571546ac57b-photo.jpg
🗑️ Deleted original: P:\dev.mukmuk\FamilyFoto\inbox\lindsey-2019\10 - Oct\b4f46477625ca6a03-photo.HEIC
✅ Converted: b4f4647625ca6a03-photo.HEIC → b4f4647625ca6a03-photo.jpg
🗑️ Deleted original: P:\dev.mukmuk\FamilyFoto\inbox\lindsey-2019\11 - Nov\00c5b944407bad226-photo.HEIC
✅ Converted: 00c5b94407bad226-photo.HEIC → 00c5b94407bad226-photo.jpg
🗑️ Deleted original: P:\dev.mukmuk\FamilyFoto\inbox\lindsey-2019\12 - Dec\3c494911da5f74784-photo.HEIC
✅ Converted: 3c49491da5f74784-photo.HEIC → 3c49491da5f74784-photo.jpg

🧾 Done. Converted: 2345, Skipped: 0, Failed: 0
</pre>

post heic conversion...

<pre>

                             P:\dev.mukmuk\FamilyFoto\inbox                      
                  📊 Media File Summary                   
┏━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━┓
┃    Folder    ┃       Camera        ┃ File Type ┃ Count ┃
┡━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━┩
│ lindsey-2019 │       Unknown       │   .mov    │  16   │
│ lindsey-2019 │      iPhone 7       │   .jpg    │   1   │
│ lindsey-2019 │      iPhone 8       │   .jpeg   │   2   │
│ lindsey-2019 │      iPhone 8       │   .jpg    │  14   │
│ lindsey-2020 │ Canon EOS REBEL SL1 │   .jpeg   │   3   │
│ lindsey-2020 │       Unknown       │   .jpeg   │   2   │
│ lindsey-2020 │       Unknown       │   .jpg    │  13   │
│ lindsey-2020 │       Unknown       │   .mov    │  233  │
│ lindsey-2020 │       Unknown       │   .png    │  100  │
│ lindsey-2020 │  iPhone 11 Pro Max  │   .jpg    │   1   │
│ lindsey-2020 │      iPhone 6s      │   .jpg    │   2   │
│ lindsey-2020 │      iPhone 7       │   .jpg    │   1   │
│ lindsey-2020 │    iPhone 7 Plus    │   .jpeg   │   1   │
│ lindsey-2020 │      iPhone 8       │   .jpg    │  211  │
│ lindsey-2020 │    iPhone 8 Plus    │   .jpeg   │   2   │
│ lindsey-2020 │      iPhone XR      │   .jpeg   │   7   │
│ lindsey-2021 │       Unknown       │   .jpg    │  88   │
│ lindsey-2021 │       Unknown       │   .mov    │ 1769  │
│ lindsey-2021 │       Unknown       │   .png    │  777  │
│ lindsey-2021 │         iOS         │   .jpg    │   4   │
│ lindsey-2021 │      iPhone 11      │   .jpeg   │   8   │
│ lindsey-2021 │      iPhone 11      │   .jpg    │  191  │
│ lindsey-2021 │    iPhone 11 Pro    │   .jpg    │   1   │
│ lindsey-2021 │      iPhone 12      │   .jpg    │   2   │
│ lindsey-2021 │      iPhone 7       │   .jpg    │   1   │
│ lindsey-2021 │    iPhone 7 Plus    │   .jpeg   │   7   │
│ lindsey-2021 │    iPhone 7 Plus    │   .jpg    │   2   │
│ lindsey-2021 │      iPhone 8       │   .jpg    │ 1941  │
│ lindsey-2021 │    iPhone 8 Plus    │   .jpeg   │   1   │
│ lindsey-2021 │      iPhone XR      │   .jpeg   │  11   │
│ lindsey-2021 │      iPhone XR      │   .jpg    │  89   │
└──────────────┴─────────────────────┴───────────┴───────┘

</pre>


# step 3 - attemp to rename a specific folder

<pre>
[08/25/25 10:52:33] INFO     summarizes files:                summary_utils.py:59
                             P:\dev.mukmuk\FamilyFoto\inbox\l                    
                             indsey-2019                                         
           📊 Media File Summary           
┏━━━━━━━━━━┳━━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━┓
┃  Folder  ┃  Camera  ┃ File Type ┃ Count ┃
┡━━━━━━━━━━╇━━━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━┩
│ 04 - Apr │ iPhone 8 │   .jpg    │   1   │
│ 06 - Jun │ Unknown  │   .mov    │   1   │
│ 08 - Aug │ Unknown  │   .mov    │   6   │
│ 08 - Aug │ iPhone 8 │   .jpeg   │   2   │
│ 08 - Aug │ iPhone 8 │   .jpg    │   4   │
│ 09 - Sep │ Unknown  │   .mov    │   2   │
│ 09 - Sep │ iPhone 7 │   .jpg    │   1   │
│ 09 - Sep │ iPhone 8 │   .jpg    │   2   │
│ 10 - Oct │ Unknown  │   .mov    │   4   │
│ 10 - Oct │ iPhone 8 │   .jpg    │   4   │
│ 11 - Nov │ Unknown  │   .mov    │   2   │
│ 11 - Nov │ iPhone 8 │   .jpg    │   2   │
│ 12 - Dec │ Unknown  │   .mov    │   1   │
│ 12 - Dec │ iPhone 8 │   .jpg    │   1   │
└──────────┴──────────┴───────────┴───────┘

Press Enter to continue...

📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
[08/25/25 10:54:21] INFO     31183 rows - city                    fotonamer.py:52
                    INFO     12 rows - street                     fotonamer.py:55
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
[08/25/25 10:54:23] INFO     ✅ Renamed                          fotonamer.py:175
                             169295f9da5dea82-photo.JPG →                        
                             2019-04-20_RUNNOV_1705.jpg                          
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
[08/25/25 10:54:24] INFO     ✅ Renamed                          fotonamer.py:175
                             12bf5990282e68cd-photo-full.jpg →                   
                             2019-08-24_LAKETI_0957.jpg                          
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
[08/25/25 10:54:25] INFO     ♻️ 12bf5990282e68cd-photo.jpeg:      fotonamer.py:135
                             Already renamed, updating metadata                  
                    INFO     🔁 Renamed                          fotonamer.py:150
                             12bf5990282e68cd-photo.jpeg →                       
                             2019-08-24_LAKETI_0957.jpeg                         
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📸 Renaming photos... ━━━━╸━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  12% 0:00:10      
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
[08/25/25 10:54:27] INFO     ✅ Renamed                          fotonamer.py:175
                             254cf65b60158cf2-photo-full.jpg →                   
                             2019-08-24_LAKETI_1124.jpg                          
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
[08/25/25 10:54:28] INFO     ♻️ 254cf65b60158cf2-photo.jpeg:      fotonamer.py:135
                             Already renamed, updating metadata                  
                    INFO     🔁 Renamed                          fotonamer.py:150
                             254cf65b60158cf2-photo.jpeg →                       
                             2019-08-24_LAKETI_1124.jpeg                         
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
[08/25/25 10:54:29] INFO     ✅ Renamed                          fotonamer.py:175
                             a35b279c2139188f-photo.jpg →                        
                             2019-08-26_LAKETI_0741.jpg                          
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
                    INFO     ✅ Renamed                          fotonamer.py:175
                             ff655c6142bcd415-photo.jpg →                        
                             2019-08-26_LAKETI_0741_1.jpg                        
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
[08/25/25 10:54:30] INFO     ✅ Renamed                          fotonamer.py:175
                             0337b774dd34ab95-photo.JPG →                        
                             2019-09-20_OLYMTI_1955.jpg                          
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
[08/25/25 10:54:31] INFO     ✅ Renamed                          fotonamer.py:175
                             f720555af5c28a32-photo-full.jpg →                   
                             2019-09-21_LAKETI_1502.jpg                          
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
[08/25/25 10:54:33] INFO     ✅ Renamed                          fotonamer.py:175
                             f720555af5c28a32-photo.jpg →                        
                             2019-09-21_LAKETI_1502_1.jpg                        
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
                    INFO     ✅ Renamed                          fotonamer.py:175
                             94034571546ac57b-photo-full.jpg →                   
                             2019-10-03_LAKETI_1419.jpg                          
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
[08/25/25 10:54:35] INFO     ✅ Renamed                          fotonamer.py:175
                             94034571546ac57b-photo.jpg →                        
                             2019-10-03_LAKETI_1419_1.jpg                        
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
[08/25/25 10:54:36] INFO     ✅ Renamed                          fotonamer.py:175
                             b4f4647625ca6a03-photo-full.jpg →                   
                             2019-10-30_LAKETI_2105.jpg                          
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
                    INFO     ✅ Renamed                          fotonamer.py:175
                             b4f4647625ca6a03-photo.jpg →                        
                             2019-10-30_LAKETI_2105_1.jpg                        
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
[08/25/25 10:54:37] INFO     ✅ Renamed                          fotonamer.py:175
                             00c5b94407bad226-photo-full.jpg →                   
                             2019-11-14_LAKETI_1143.jpg                          
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
[08/25/25 10:54:38] INFO     ✅ Renamed                          fotonamer.py:175
                             00c5b94407bad226-photo.jpg →                        
                             2019-11-14_LAKETI_1143_1.jpg                        
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
[08/25/25 10:54:39] INFO     ✅ Renamed                          fotonamer.py:175
                             3c49491da5f74784-photo.jpg →                        
                             2019-12-04_LAKETI_1732.jpg                          
📂 Using config: C:\Users\Mike\.familyfoto\config\photo.config
📸 Renaming photos... ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 100% 0:00:18      

Press Enter to continue...
</pre>


# step 4 - move files - remaing files are the paired .mov files...

<pre>

[08/25/25 10:55:34] INFO     summarizes files:                summary_utils.py:59
                             P:\dev.mukmuk\FamilyFoto\inbox\l                    
                             indsey-2019                                         
          📊 Media File Summary           
┏━━━━━━━━━━┳━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━┓
┃  Folder  ┃ Camera  ┃ File Type ┃ Count ┃
┡━━━━━━━━━━╇━━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━┩
│ 06 - Jun │ Unknown │   .mov    │   1   │
│ 08 - Aug │ Unknown │   .mov    │   6   │
│ 09 - Sep │ Unknown │   .mov    │   2   │
│ 10 - Oct │ Unknown │   .mov    │   4   │
│ 11 - Nov │ Unknown │   .mov    │   2   │
│ 12 - Dec │ Unknown │   .mov    │   1   │
└──────────┴─────────┴───────────┴───────┘

Press Enter to continue...

</pre>


# step 5 - count remaining files...

<pre>
[08/25/25 12:34:40] INFO     summarizes files:                   summary_utils.py:59
                             P:\dev.mukmuk\FamilyFoto\inbox                         
                      📊 Media File Summary                      
┏━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━┓
┃       Folder        ┃       Camera        ┃ File Type ┃ Count ┃
┡━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━┩
│ lindsey-2019-250825 │       Unknown       │   .mov    │  16   │
│ lindsey-2020-250825 │ Canon EOS REBEL SL1 │   .jpeg   │   3   │
│ lindsey-2020-250825 │       Unknown       │   .jpeg   │   2   │
│ lindsey-2020-250825 │       Unknown       │   .jpg    │  13   │
│ lindsey-2020-250825 │       Unknown       │   .mov    │  233  │
│ lindsey-2020-250825 │       Unknown       │   .png    │  100  │
│ lindsey-2020-250825 │  iPhone 11 Pro Max  │   .jpg    │   1   │
│ lindsey-2020-250825 │      iPhone 7       │   .jpg    │   1   │
│ lindsey-2020-250825 │    iPhone 7 Plus    │   .jpeg   │   1   │
│ lindsey-2020-250825 │      iPhone 8       │   .jpg    │  18   │
│ lindsey-2021-250825 │       Unknown       │   .jpg    │  88   │
│ lindsey-2021-250825 │       Unknown       │   .mov    │ 1769  │
│ lindsey-2021-250825 │       Unknown       │   .png    │  777  │
│ lindsey-2021-250825 │         iOS         │   .jpg    │   4   │
│ lindsey-2021-250825 │      iPhone 11      │   .jpeg   │   7   │
│ lindsey-2021-250825 │      iPhone 11      │   .jpg    │  48   │
│ lindsey-2021-250825 │      iPhone 12      │   .jpg    │   2   │
│ lindsey-2021-250825 │      iPhone 7       │   .jpg    │   1   │
│ lindsey-2021-250825 │    iPhone 7 Plus    │   .jpeg   │   7   │
│ lindsey-2021-250825 │    iPhone 7 Plus    │   .jpg    │   2   │
│ lindsey-2021-250825 │      iPhone 8       │   .jpg    │  115  │
│ lindsey-2021-250825 │    iPhone 8 Plus    │   .jpeg   │   1   │
│ lindsey-2021-250825 │      iPhone XR      │   .jpeg   │   1   │
│ lindsey-2021-250825 │      iPhone XR      │   .jpg    │   3   │
└─────────────────────┴─────────────────────┴───────────┴───────┘

Press Enter to continue...

[08/25/25 12:37:02] INFO     street:                                 fotomenu.py:164
                             P:\dev.mukmuk\FamilyFoto\data\streets.c                
                             sv                                                     
                    INFO     city:                                   fotomenu.py:165
                             P:\dev.mukmuk\FamilyFoto\data\uscities.                
                             csv                                                    

🔍 Summarizing files in: P:\dev.mukmuk\FamilyFoto\data\streets.csv

        🛣️  Streets per City        
┏────────────┳━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━┓
┃ City ID    ┃ City, State          ┃ Count ┃
┡────────────╇━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━┩
│ 1840013121 │ Conway, FL           │     2 │
│ 1840014043 │ Edgewater, FL        │     1 │
│ 1840014076 │ Merritt Island, FL   │     2 │
│ 1840015068 │ Daytona Beach, FL    │     3 │
│ 1840015073 │ New Smyrna Beach, FL │     2 │
│ 1840015089 │ Oviedo, FL           │    10 │
│ 1840015092 │ Cocoa, FL            │     1 │
│ 1840015099 │ Orlando, FL          │     4 │
│ 1840015962 │ Titusville, FL       │    34 │
│ 1840020135 │ Ogden, UT            │     1 │
│ 1840020145 │ Layton, UT           │     7 │
│ 1840020230 │ Grand Junction, CO   │     7 │
│ 1840021352 │ Syracuse, UT         │     3 │
│ 1840029102 │ Alafaya, FL          │     1 │
│ 1840073852 │ University, FL       │     3 │
└────────────┴──────────────────────┴───────┘

Press Enter to continue...


</pre>