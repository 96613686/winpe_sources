# SdbGetTagFromTagID

- ea: `0x140016148`
- end: `0x14001618f`
- name: `SdbGetTagFromTagID`
- size: `71`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `28`
- callee_count: `3`
- tags: ``

## callers

- `0x140013824`
- `0x140013898`
- `0x140013938`
- `0x140013b84`
- `0x140013c14`
- `0x140013cb8`
- `0x140013dc0`
- `0x140013e60`
- `0x140013ff8`
- `0x140014234`
- `0x140014380`
- `0x1400143d8`
- `0x14001443c`
- `0x140014b64`
- `0x140015538`
- `0x140015e14`
- `0x140016070`
- `0x140018840`
- `0x140018cb4`
- `0x140018d48`
- `0x140019410`
- `0x14001a24c`
- `0x14001b2f0`
- `0x14001c730`
- `0x14001cd7c`
- `0x14001d494`
- `0x14001d808`
- `0x14002b138`

## callees

- `0x14001008c`
- `0x140016148`
- `0x1400178a0`

## string_xrefs

- `0x140016165`: `Error reading data`

## pseudocode

```c
__int64 __fastcall SdbGetTagFromTagID(__int64 a1, __int64 a2)
{
  unsigned __int16 v3; // [rsp+40h] [rbp+18h] BYREF

  v3 = 0;
  if ( (unsigned int)SdbpReadMappedData(a1, a2, &v3, 2) )
    return v3;
  AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
  return 0;
}

```

## disassembly

```asm
0x140016148  sub     rsp, 28h
0x14001614c  xor     eax, eax
0x14001614e  lea     r8, [rsp+28h+arg_10]
0x140016153  mov     [rsp+28h+arg_10], ax
0x140016158  lea     r9d, [rax+2]
0x14001615c  call    SdbpReadMappedData
0x140016161  test    eax, eax
0x140016163  jnz     short loc_140016185
0x140016165  lea     r9, aErrorReadingDa; "Error reading data"
0x14001616c  mov     r8d, 0BDFh
0x140016172  lea     rdx, aSdbgettagfromt; "SdbGetTagFromTagID"
0x140016179  lea     ecx, [rax+1]
0x14001617c  call    AslLogCallPrintf
0x140016181  xor     eax, eax
0x140016183  jmp     short loc_14001618A
0x140016185  movzx   eax, [rsp+28h+arg_10]
0x14001618a  add     rsp, 28h
0x14001618e  retn
```
