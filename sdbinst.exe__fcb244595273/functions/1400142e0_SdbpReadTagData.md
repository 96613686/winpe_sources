# SdbpReadTagData

- ea: `0x1400142e0`
- end: `0x140014378`
- name: `SdbpReadTagData`
- size: `152`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x140013b84`
- `0x140013c14`
- `0x140013cb8`
- `0x140013dc0`
- `0x140013e60`
- `0x140014234`

## callees

- `0x14001008c`
- `0x140013938`
- `0x14001415c`
- `0x1400142e0`
- `0x1400178a0`

## string_xrefs

- `0x140014316`: `SdbpReadTagData`
- `0x140014357`: `SdbpReadTagData`
- `0x14001434a`: `Error reading tag data`

## pseudocode

```c
__int64 __fastcall SdbpReadTagData(__int64 a1, __int64 a2, void *a3, unsigned int a4)
{
  unsigned int v6; // esi
  unsigned int TagDataSize; // eax
  unsigned int v9; // ebx
  int TagHeadSize; // eax

  v6 = a2;
  TagDataSize = SdbGetTagDataSize(a1, a2);
  v9 = TagDataSize;
  if ( TagDataSize > a4 )
  {
    AslLogCallPrintf(1, "SdbpReadTagData", 439, "Buffer too small. Avail: %d, Need: %d", a4, TagDataSize);
    return 0;
  }
  TagHeadSize = SdbpGetTagHeadSize(a1, v6);
  if ( !(unsigned int)SdbpReadMappedData(a1, v6 + TagHeadSize, a3, v9) )
  {
    AslLogCallPrintf(1, "SdbpReadTagData", 446, "Error reading tag data");
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1400142e0  push    rbx
0x1400142e2  push    rbp
0x1400142e3  push    rsi
0x1400142e4  push    rdi
0x1400142e5  push    r14
0x1400142e7  sub     rsp, 30h
0x1400142eb  mov     edi, r9d
0x1400142ee  mov     r14, r8
0x1400142f1  mov     esi, edx
0x1400142f3  mov     rbp, rcx
0x1400142f6  call    SdbGetTagDataSize
0x1400142fb  mov     ebx, eax
0x1400142fd  cmp     eax, edi
0x1400142ff  jbe     short loc_14001432B
0x140014301  mov     [rsp+58h+var_30], eax
0x140014305  lea     r9, aBufferTooSmall; "Buffer too small. Avail: %d, Need: %d"
0x14001430c  mov     r8d, 1B7h
0x140014312  mov     [rsp+58h+var_38], edi
0x140014316  lea     rdx, aSdbpreadtagdat; "SdbpReadTagData"
0x14001431d  mov     ecx, 1
0x140014322  call    AslLogCallPrintf
0x140014327  xor     eax, eax
0x140014329  jmp     short loc_14001436D
0x14001432b  mov     edx, esi
0x14001432d  mov     rcx, rbp
0x140014330  call    SdbpGetTagHeadSize
0x140014335  mov     r9d, ebx
0x140014338  mov     r8, r14
0x14001433b  mov     rcx, rbp
0x14001433e  lea     edx, [rsi+rax]
0x140014341  call    SdbpReadMappedData
0x140014346  test    eax, eax
0x140014348  jnz     short loc_140014368
0x14001434a  lea     r9, aErrorReadingTa; "Error reading tag data"
0x140014351  mov     r8d, 1BEh
0x140014357  lea     rdx, aSdbpreadtagdat; "SdbpReadTagData"
0x14001435e  lea     ecx, [rax+1]
0x140014361  call    AslLogCallPrintf
0x140014366  jmp     short loc_140014327
0x140014368  mov     eax, 1
0x14001436d  add     rsp, 30h
0x140014371  pop     r14
0x140014373  pop     rdi
0x140014374  pop     rsi
0x140014375  pop     rbp
0x140014376  pop     rbx
0x140014377  retn
```
