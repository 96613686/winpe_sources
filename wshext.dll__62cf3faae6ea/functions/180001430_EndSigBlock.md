# EndSigBlock

- ea: `0x180001430`
- end: `0x180001457`
- name: `EndSigBlock`
- size: `39`
- prototype: `const wchar_t *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001810`
- `0x1800024f0`
- `0x180008f7c`

## callees

- `0x180001430`

## pseudocode

```c
const wchar_t *__fastcall EndSigBlock(int a1)
{
  if ( a1 == 2 )
    return L"\r\n// SIG // End signature block\r\n";
  if ( a1 == 3 )
    return L"\r\n</signature>\r\n";
  return L"\r\n'' SIG '' End signature block\r\n";
}

```

## disassembly

```asm
0x180001430  cmp     ecx, 2
0x180001433  jnz     short loc_18000143D
0x180001435  lea     rax, aSigEndSignatur_0; "\r\n// SIG // End signature block\r\n"
0x18000143c  retn
0x18000143d  sub     ecx, 1
0x180001440  jnz     short loc_18000144A
0x180001442  lea     rax, aSigEndSignatur; "\r\n'' SIG '' End signature block\r\n"
0x180001449  retn
0x18000144a  cmp     ecx, 2
0x18000144d  jnz     short loc_180001442
0x18000144f  lea     rax, aSignature_0; "\r\n</signature>\r\n"
0x180001456  retn
```
