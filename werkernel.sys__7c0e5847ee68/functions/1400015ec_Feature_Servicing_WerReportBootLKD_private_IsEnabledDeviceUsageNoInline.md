# Feature_Servicing_WerReportBootLKD__private_IsEnabledDeviceUsageNoInline

- ea: `0x1400015ec`
- end: `0x140001621`
- name: `Feature_Servicing_WerReportBootLKD__private_IsEnabledDeviceUsageNoInline`
- size: `53`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000e464`
- `0x14000e83c`

## callees

- `0x1400015ec`
- `0x140001628`

## pseudocode

```c
__int64 Feature_Servicing_WerReportBootLKD__private_IsEnabledDeviceUsageNoInline()
{
  if ( (Feature_Servicing_WerReportBootLKD__private_featureState & 0x10) != 0 )
    return Feature_Servicing_WerReportBootLKD__private_featureState & 1;
  else
    return Feature_Servicing_WerReportBootLKD__private_IsEnabledFallback(
             (unsigned int)Feature_Servicing_WerReportBootLKD__private_featureState,
             3);
}

```

## disassembly

```asm
0x1400015ec  sub     rsp, 28h
0x1400015f0  mov     eax, cs:Feature_Servicing_WerReportBootLKD__private_featureState
0x1400015f6  mov     [rsp+28h+arg_0], 0
0x1400015ff  mov     dword ptr [rsp+28h+arg_0], eax
0x140001603  test    al, 10h
0x140001605  jz      short loc_14000160C
0x140001607  and     eax, 1
0x14000160a  jmp     short loc_14000161B
0x14000160c  mov     rcx, [rsp+28h+arg_0]
0x140001611  mov     edx, 3
0x140001616  call    Feature_Servicing_WerReportBootLKD__private_IsEnabledFallback
0x14000161b  add     rsp, 28h
0x14000161f  retn
```
