# C# loader that copies a chunk at the time of the shellcode in memory of a suspended process, rather that all at once

Based on the Process Hollowing technique

Uses p/invoke to copy an encoded shellcode in memory in a suspended process and to decode it byte by byte afterwards

`ProgramAmsiEtwPatch` also patches `AmsiScanBuffer` and `EtwEventWrite`

Yes the code is shit, but meh so what - not like I have the whole day to write good pocs

Tested with Meterpreter staged rev HTTPS payload (`encode_shellcode.cs` or py version is the code I used to encode the raw one)

ProgramAmsiEtwPatch.cs against SentinelOne (used Babel .net obfuscator - free version - twice on the resulting exe)

![Windowz](https://github.com/clod81/loader_process_hollow_copy_in_chunk/blob/main/3.png?raw=true "Windowz")

![Meterpreter](https://github.com/clod81/loader_process_hollow_copy_in_chunk/blob/main/4.png?raw=true "Meterpreter")

![AntiScan.Me](https://antiscan.me/images/result/6gG5mDTAn1GD.png "AntiScan.Me")

Program.cs against Defender

![Windowz](https://github.com/clod81/loader_process_hollow_decode_after_initial_write/blob/main/1.png?raw=true "Windowz")

![Meterpreter](https://github.com/clod81/loader_process_hollow_decode_after_initial_write/blob/main/2.png?raw=true "Meterpreter")
