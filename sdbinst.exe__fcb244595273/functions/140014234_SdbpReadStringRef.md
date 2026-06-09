# SdbpReadStringRef

- ea: `0x140014234`
- end: `0x1400142da`
- name: `SdbpReadStringRef`
- size: `166`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140013898`

## callees

- `0x14001008c`
- `0x140014234`
- `0x1400142e0`
- `0x140016148`

## string_xrefs

- `0x14001427a`: `SdbpReadStringRef`
- `0x1400142ba`: `SdbpReadStringRef`
- `0x1400142ad`: `Error reading data`

## pseudocode

```c
__int64 __fastcall SdbpReadStringRef(__int64 a1, __int64 a2)
{
  unsigned int v2; // ebx
  unsigned __int16 TagFromTagID; // ax
  unsigned int v6; // [rsp+50h] [rbp+18h] BYREF

  v2 = a2;
  v6 = 0;
  if ( (SdbGetTagFromTagID(a1, a2) & 0xF000) != 0x6000 )
  {
    TagFromTagID = SdbGetTagFromTagID(a1, v2);
    AslLogCallPrintf(1, "SdbpReadStringRef", 634, "TagID 0x%08X, Tag %04X not STRINGREF type", v2, TagFromTagID);
    return 0;
  }
  if ( !(unsigned int)SdbpReadTagData(a1, v2, &v6, 4u) )
  {
    AslLogCallPrintf(1, "SdbpReadStringRef", 639, "Error reading data");
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x140014234  mov     [rsp+arg_0], rbx
0x140014239  push    rdi
0x14001423a  sub     rsp, 30h
0x14001423e  mov     ebx, edx
0x140014240  mov     [rsp+38h+arg_10], 0
0x140014248  mov     rdi, rcx
0x14001424b  call    SdbGetTagFromTagID
0x140014250  mov     ecx, 0F000h
0x140014255  mov     edx, ebx
0x140014257  and     ax, cx
0x14001425a  mov     ecx, 6000h
0x14001425f  cmp     ax, cx
0x140014262  mov     rcx, rdi
0x140014265  jz      short loc_140014299
0x140014267  call    SdbGetTagFromTagID
0x14001426c  movzx   eax, ax
0x14001426f  lea     r9, aTagid0x08xTag0; "TagID 0x%08X, Tag %04X not STRINGREF ty"...
0x140014276  mov     [rsp+38h+var_10], eax
0x14001427a  lea     rdx, aSdbpreadstring; "SdbpReadStringRef"
0x140014281  mov     r8d, 27Ah
0x140014287  mov     [rsp+38h+var_18], ebx
0x14001428b  mov     ecx, 1
0x140014290  call    AslLogCallPrintf
0x140014295  xor     eax, eax
0x140014297  jmp     short loc_1400142CF
0x140014299  mov     r9d, 4
0x14001429f  lea     r8, [rsp+38h+arg_10]
0x1400142a4  call    SdbpReadTagData
0x1400142a9  test    eax, eax
0x1400142ab  jnz     short loc_1400142CB
0x1400142ad  lea     r9, aErrorReadingDa; "Error reading data"
0x1400142b4  mov     r8d, 27Fh
0x1400142ba  lea     rdx, aSdbpreadstring; "SdbpReadStringRef"
0x1400142c1  lea     ecx, [rax+1]
0x1400142c4  call    AslLogCallPrintf
0x1400142c9  jmp     short loc_140014295
0x1400142cb  mov     eax, [rsp+38h+arg_10]
0x1400142cf  mov     rbx, [rsp+38h+arg_0]
0x1400142d4  add     rsp, 30h
0x1400142d8  pop     rdi
0x1400142d9  retn
```
