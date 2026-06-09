# WPP_SF_sqq_guid_d

- ea: `0x140001fec`
- end: `0x140002077`
- name: `WPP_SF_sqq_guid_d`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140011ab4`

## callees

- `0x1400025c0`

## string_xrefs

- `0x14000204f`: `TmpTxActionDoRollback`

## pseudocode

```c
__int64 __fastcall WPP_SF_sqq_guid_d(__int64 a1)
{
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *))pfnWppTraceMessage)(
           a1,
           43,
           WPP_49ed135d36c7359d33070dea67dc05c0_Traceguids);
}

```

## disassembly

```asm
0x140001fec  mov     r11, rsp
0x140001fef  sub     rsp, 88h
0x140001ff6  mov     qword ptr [r11-18h], 0
0x140001ffe  lea     rax, [r11+40h]
0x140002002  mov     qword ptr [r11-20h], 4
0x14000200a  lea     r8, WPP_49ed135d36c7359d33070dea67dc05c0_Traceguids
0x140002011  mov     [r11-28h], rax
0x140002015  mov     r9d, 13h
0x14000201b  mov     rax, [rsp+88h+arg_30]
0x140002023  mov     qword ptr [r11-30h], 10h
0x14000202b  mov     [r11-38h], rax
0x14000202f  lea     rax, [r11+30h]
0x140002033  lea     edx, [r9-0Bh]
0x140002037  mov     [r11-40h], rdx
0x14000203b  mov     [r11-48h], rax
0x14000203f  lea     rax, [r11+28h]
0x140002043  mov     [r11-50h], rdx
0x140002047  lea     edx, [r9+18h]
0x14000204b  mov     [r11-58h], rax
0x14000204f  lea     rax, aTmptxactiondor; "TmpTxActionDoRollback"
0x140002056  mov     qword ptr [r11-60h], 16h
0x14000205e  mov     [r11-68h], rax
0x140002062  mov     rax, cs:pfnWppTraceMessage
0x140002069  call    _guard_dispatch_icall
0x14000206e  add     rsp, 88h
0x140002075  retn
```
