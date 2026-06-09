# SdbpGetTagHeadSize

- ea: `0x14001415c`
- end: `0x14001422d`
- name: `SdbpGetTagHeadSize`
- size: `209`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140013f74`
- `0x1400142e0`
- `0x1400176a4`

## callees

- `0x14001008c`
- `0x140013738`
- `0x14001415c`
- `0x1400178a0`

## string_xrefs

- `0x140014179`: `Error reading tag`

## pseudocode

```c
__int64 __fastcall SdbpGetTagHeadSize(__int64 a1, __int64 a2)
{
  int v3; // ecx
  unsigned __int16 v4; // [rsp+50h] [rbp+18h] BYREF

  v4 = 0;
  if ( !(unsigned int)SdbpReadMappedData(a1, a2, &v4, 2) )
  {
    AslLogCallPrintf(1, "SdbpGetTagHeadSize", 100, "Error reading tag");
    return 0;
  }
  if ( !(unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
    return (v4 & 0xF000u) < 0x7000 ? 2 : 6;
  v3 = v4 & 0xF000;
  if ( (unsigned int)(v3 - 4096) <= 0x5000 && (((_WORD)v3 - 4096) & 0xFFF) == 0 )
    return 2;
  if ( ((v3 - 28672) & 0xFFFFCFFF) != 0 || v3 == 40960 )
  {
    AslLogCallPrintf(1, "SdbpGetTagHeadSize", 121, "Invalid TAG_TYPE encountered. TAG: [%x]", v4);
    return 0;
  }
  return 6;
}

```

## disassembly

```asm
0x14001415c  sub     rsp, 38h
0x140014160  xor     eax, eax
0x140014162  lea     r8, [rsp+38h+arg_10]
0x140014167  mov     [rsp+38h+arg_10], ax
0x14001416c  lea     r9d, [rax+2]
0x140014170  call    SdbpReadMappedData
0x140014175  test    eax, eax
0x140014177  jnz     short loc_14001419A
0x140014179  lea     r9, aErrorReadingTa_0; "Error reading tag"
0x140014180  lea     r8d, [rax+64h]
0x140014184  lea     rdx, aSdbpgettaghead; "SdbpGetTagHeadSize"
0x14001418b  lea     ecx, [rax+1]
0x14001418e  call    AslLogCallPrintf
0x140014193  xor     eax, eax
0x140014195  jmp     loc_140014228
0x14001419a  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x14001419f  mov     edx, 0F000h
0x1400141a4  test    eax, eax
0x1400141a6  jz      short loc_140014210
0x1400141a8  movzx   r8d, [rsp+38h+arg_10]
0x1400141ae  mov     ecx, r8d
0x1400141b1  and     ecx, edx
0x1400141b3  lea     edx, [rcx-1000h]
0x1400141b9  cmp     edx, 5000h
0x1400141bf  ja      short loc_1400141D0
0x1400141c1  test    edx, 0FFFh
0x1400141c7  jnz     short loc_1400141D0
0x1400141c9  mov     eax, 2
0x1400141ce  jmp     short loc_140014228
0x1400141d0  lea     eax, [rcx-7000h]
0x1400141d6  test    eax, 0FFFFCFFFh
0x1400141db  jnz     short loc_1400141EC
0x1400141dd  cmp     ecx, 0A000h
0x1400141e3  jz      short loc_1400141EC
0x1400141e5  mov     eax, 6
0x1400141ea  jmp     short loc_140014228
0x1400141ec  mov     [rsp+38h+var_18], r8d
0x1400141f1  lea     r9, aInvalidTagType; "Invalid TAG_TYPE encountered. TAG: [%x]"
0x1400141f8  mov     r8d, 79h ; 'y'
0x1400141fe  lea     rdx, aSdbpgettaghead; "SdbpGetTagHeadSize"
0x140014205  lea     ecx, [r8-78h]
0x140014209  call    AslLogCallPrintf
0x14001420e  jmp     short loc_140014193
0x140014210  movzx   eax, [rsp+38h+arg_10]
0x140014215  mov     ecx, 7000h
0x14001421a  and     ax, dx
0x14001421d  cmp     ax, cx
0x140014220  sbb     eax, eax
0x140014222  and     eax, 0FFFFFFFCh
0x140014225  add     eax, 6
0x140014228  add     rsp, 38h
0x14001422c  retn
```
