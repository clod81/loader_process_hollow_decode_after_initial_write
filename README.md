# C# loader that copies a chunk at the time of the shellcode in memory of a suspended process, rather that all at once

Based on the Process Hollowing technique

Uses p/invoke to copy an encoded shellcode in memory in a suspended process and to decode it byte by byte afterwards

Yes the code is shit, but meh so what - not like I have the whole day to write good pocs

Tested with Meterpreter staged rev HTTPS payload (`encode_shellcode.cs` is the code I used to encode the raw one)

![Windowz](https://github.com/clod81/loader_process_hollow_decode_after_initial_write/blob/main/1.png?raw=true "Windowz")

![Meterpreter](https://github.com/clod81/loader_process_hollow_decode_after_initial_write/blob/main/2.png?raw=true "Meterpreter")
