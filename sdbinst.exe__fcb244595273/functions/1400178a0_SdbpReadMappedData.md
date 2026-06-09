# SdbpReadMappedData

- ea: `0x1400178a0`
- end: `0x140017922`
- name: `SdbpReadMappedData`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x140013938`
- `0x14001415c`
- `0x1400142e0`
- `0x140015cbc`
- `0x140016148`
- `0x140016198`
- `0x140017730`
- `0x140017cf4`

## callees

- `0x140002206`
- `0x14001008c`
- `0x1400178a0`

## string_xrefs

- `0x1400178bd`: `SdbpReadMappedData`
- `0x1400178f9`: `SdbpReadMappedData`
- `0x1400178f2`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`

## pseudocode

```c
__int64 __fastcall SdbpReadMappedData(__int64 a1, unsigned int a2, void *a3, unsigned int a4)
{
  if ( a2 + a4 < a4 )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      855,
      "Offset and region size add up to cause an integer overflow or underflow");
    return 0;
  }
  if ( *(_DWORD *)(a1 + 20) < a2 + a4 )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      860,
      "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
      a2,
      a4,
      *(_DWORD *)(a1 + 20));
    return 0;
  }
  memcpy_0(a3, (const void *)(*(_QWORD *)(a1 + 8) + a2), a4);
  return 1;
}

```

## disassembly

```asm
0x1400178a0  sub     rsp, 48h
0x1400178a4  lea     r10d, [rdx+r9]
0x1400178a8  mov     r11, r8
0x1400178ab  cmp     r10d, r9d
0x1400178ae  jnb     short loc_1400178D2
0x1400178b0  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x1400178b7  mov     r8d, 357h
0x1400178bd  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x1400178c4  mov     ecx, 1
0x1400178c9  call    AslLogCallPrintf
0x1400178ce  xor     eax, eax
0x1400178d0  jmp     short loc_14001791D
0x1400178d2  mov     eax, [rcx+14h]
0x1400178d5  cmp     eax, r10d
0x1400178d8  jnb     short loc_140017907
0x1400178da  mov     [rsp+48h+var_18], eax
0x1400178de  mov     r8d, 35Ch
0x1400178e4  mov     [rsp+48h+var_20], r9d
0x1400178e9  mov     ecx, 1
0x1400178ee  mov     [rsp+48h+var_28], edx
0x1400178f2  lea     r9, aAttemptToReadP; "Attempt to read past the end of the dat"...
0x1400178f9  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x140017900  call    AslLogCallPrintf
0x140017905  jmp     short loc_1400178CE
0x140017907  mov     edx, edx
0x140017909  add     rdx, [rcx+8]; Src
0x14001790d  mov     rcx, r11; void *
0x140017910  mov     r8d, r9d; Size
0x140017913  call    memcpy_0
0x140017918  mov     eax, 1
0x14001791d  add     rsp, 48h
0x140017921  retn
```
