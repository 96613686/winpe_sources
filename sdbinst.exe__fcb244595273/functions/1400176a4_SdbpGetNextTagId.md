# SdbpGetNextTagId

- ea: `0x1400176a4`
- end: `0x140017729`
- name: `SdbpGetNextTagId`
- size: `133`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140015e14`
- `0x140016070`

## callees

- `0x14001008c`
- `0x140013738`
- `0x140013938`
- `0x14001415c`
- `0x1400176a4`

## string_xrefs

- `0x1400176c6`: `Reading from unfinished tag`

## pseudocode

```c
__int64 __fastcall SdbpGetNextTagId(__int64 a1, __int64 a2)
{
  unsigned int v2; // esi
  int TagDataSize; // ebx
  int TagHeadSize; // eax

  v2 = a2;
  TagDataSize = SdbGetTagDataSize(a1, a2);
  if ( TagDataSize == 0x20000000 )
  {
    AslLogCallPrintf(1, "SdbpGetNextTagId", 3074, "Reading from unfinished tag");
    return *(unsigned int *)(a1 + 20);
  }
  TagHeadSize = SdbpGetTagHeadSize(a1, v2);
  if ( TagHeadSize )
  {
    if ( (*(_BYTE *)(a1 + 2608) & 1) == 0 )
      TagDataSize = (TagDataSize + 1) & 0xFFFFFFFE;
    return v2 + TagDataSize + TagHeadSize;
  }
  else
  {
    if ( !(unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
      return *(unsigned int *)(a1 + 20);
    return 0x10000000;
  }
}

```

## disassembly

```asm
0x1400176a4  mov     [rsp+arg_0], rbx
0x1400176a9  mov     [rsp+arg_8], rsi
0x1400176ae  push    rdi
0x1400176af  sub     rsp, 20h
0x1400176b3  mov     esi, edx
0x1400176b5  mov     rdi, rcx
0x1400176b8  call    SdbGetTagDataSize
0x1400176bd  mov     ebx, eax
0x1400176bf  cmp     eax, 20000000h
0x1400176c4  jnz     short loc_1400176E9
0x1400176c6  lea     r9, aReadingFromUnf; "Reading from unfinished tag"
0x1400176cd  mov     r8d, 0C02h
0x1400176d3  lea     rdx, aSdbpgetnexttag_0; "SdbpGetNextTagId"
0x1400176da  mov     ecx, 1
0x1400176df  call    AslLogCallPrintf
0x1400176e4  mov     eax, [rdi+14h]
0x1400176e7  jmp     short loc_140017719
0x1400176e9  mov     edx, esi
0x1400176eb  mov     rcx, rdi
0x1400176ee  call    SdbpGetTagHeadSize
0x1400176f3  test    eax, eax
0x1400176f5  jnz     short loc_140017707
0x1400176f7  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x1400176fc  test    eax, eax
0x1400176fe  jz      short loc_1400176E4
0x140017700  mov     eax, 10000000h
0x140017705  jmp     short loc_140017719
0x140017707  test    byte ptr [rdi+0A30h], 1
0x14001770e  jnz     short loc_140017715
0x140017710  inc     ebx
0x140017712  and     ebx, 0FFFFFFFEh
0x140017715  add     eax, ebx
0x140017717  add     eax, esi
0x140017719  mov     rbx, [rsp+28h+arg_0]
0x14001771e  mov     rsi, [rsp+28h+arg_8]
0x140017723  add     rsp, 20h
0x140017727  pop     rdi
0x140017728  retn
```
