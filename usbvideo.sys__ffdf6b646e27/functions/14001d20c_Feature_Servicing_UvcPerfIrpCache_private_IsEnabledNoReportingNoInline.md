# Feature_Servicing_UvcPerfIrpCache__private_IsEnabledNoReportingNoInline

- ea: `0x14001d20c`
- end: `0x14001d23e`
- name: `Feature_Servicing_UvcPerfIrpCache__private_IsEnabledNoReportingNoInline`
- size: `50`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1400156a0`
- `0x14001d244`
- `0x14001fcb0`
- `0x14001fdf0`

## callees

- `0x14001d1f0`
- `0x14001d20c`

## pseudocode

```c
__int64 Feature_Servicing_UvcPerfIrpCache__private_IsEnabledNoReportingNoInline()
{
  if ( (WPP_MAIN_CB.SectorSize & 2) != 0 )
    return WPP_MAIN_CB.SectorSize & 1;
  else
    return Feature_Servicing_UvcPerfIrpCache__private_IsEnabledFallback(*(unsigned int *)&WPP_MAIN_CB.SectorSize, 0);
}

```

## disassembly

```asm
0x14001d20c  sub     rsp, 28h
0x14001d210  mov     eax, dword ptr cs:WPP_MAIN_CB.SectorSize
0x14001d216  mov     [rsp+28h+arg_0], 0
0x14001d21f  mov     dword ptr [rsp+28h+arg_0], eax
0x14001d223  test    al, 2
0x14001d225  jz      short loc_14001D22C
0x14001d227  and     eax, 1
0x14001d22a  jmp     short loc_14001D238
0x14001d22c  mov     rcx, [rsp+28h+arg_0]
0x14001d231  xor     edx, edx
0x14001d233  call    Feature_Servicing_UvcPerfIrpCache__private_IsEnabledFallback
0x14001d238  add     rsp, 28h
0x14001d23c  retn
```
