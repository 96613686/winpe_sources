# HUBPDO_BillboardCleanup

- ea: `0x14007ee54`
- end: `0x14007f04c`
- name: `HUBPDO_BillboardCleanup`
- size: `504`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140014f80`
- `0x140081bb0`

## callees

- `0x1400024b8`
- `0x14000c84c`
- `0x140045570`
- `0x14007ee54`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x14007efa5`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14007efa5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007eff8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f023`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007eff8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f023`

## pseudocode

```c
void __fastcall HUBPDO_BillboardCleanup(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rax
  int v4; // eax
  int v5; // edx
  __int64 v6; // r9
  int v7; // eax
  int v8; // edx
  int updated; // eax
  int v10; // edx
  void *v11; // rcx
  void *v12; // rcx
  _QWORD v13[5]; // [rsp+40h] [rbp-28h] BYREF

  if ( *(_QWORD *)(a1 + 2656) )
  {
    v2 = *(_QWORD *)(a1 + 16);
    v13[1] = DEVPKEY_Device_UsbBillboardInfo;
    v13[0] = 24;
    v13[2] = 0;
    v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, v2);
    v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *, __int64, _DWORD, _QWORD))(WdfFunctions_01015 + 3480))(
           WdfDriverGlobals,
           v3,
           v13,
           4099,
           0,
           0);
    if ( v4 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
        v5,
        2,
        94,
        (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
        v4);
    }
    LOBYTE(v6) = *(_BYTE *)(a1 + 2672);
    v7 = HUBFDO_CleanupDeviceInterfaceForBillboard(
           *(_QWORD *)a1,
           *(unsigned __int16 *)(*(_QWORD *)(a1 + 16) + 48LL),
           *(_QWORD *)(a1 + 2664),
           v6);
    if ( v7 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
        v8,
        2,
        95,
        (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
        v7);
    }
    updated = ZwUpdateWnfStateData(&WNF_USB_BILLBOARD_CHANGE, 0, 0, 0, 0, 0, 0);
    if ( updated < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
        v10,
        2,
        96,
        (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
        updated);
    }
    v11 = **(void ***)(a1 + 2656);
    if ( v11 )
      ExFreePoolWithTag(v11, 0x68334855u);
    **(_QWORD **)(a1 + 2656) = 0;
    v12 = *(void **)(a1 + 2656);
    if ( v12 )
      ExFreePoolWithTag(v12, 0x68334855u);
    *(_QWORD *)(a1 + 2656) = 0;
  }
}

```

## disassembly

```asm
0x14007ee54  mov     r11, rsp
0x14007ee57  mov     [r11+8], rbx
0x14007ee5b  mov     [r11+10h], rbp
0x14007ee5f  push    r14
0x14007ee61  sub     rsp, 60h
0x14007ee65  cmp     qword ptr [rcx+0A60h], 0
0x14007ee6d  mov     rbx, rcx
0x14007ee70  jz      loc_14007F03A
0x14007ee76  mov     rdx, [rcx+10h]
0x14007ee7a  lea     rax, DEVPKEY_Device_UsbBillboardInfo
0x14007ee81  mov     rcx, cs:WdfDriverGlobals
0x14007ee88  mov     [r11-20h], rax
0x14007ee8c  mov     rax, cs:WdfFunctions_01015
0x14007ee93  mov     qword ptr [r11-28h], 18h
0x14007ee9b  mov     qword ptr [r11-18h], 0
0x14007eea3  mov     rax, [rax+660h]
0x14007eeaa  call    _guard_dispatch_icall
0x14007eeaf  mov     rcx, cs:WdfFunctions_01015
0x14007eeb6  lea     r8, [rsp+68h+var_28]
0x14007eebb  mov     rdx, rax
0x14007eebe  mov     [rsp+68h+var_40], 0
0x14007eec7  mov     r9d, 1003h
0x14007eecd  mov     dword ptr [rsp+68h+var_48], 0
0x14007eed5  mov     r10, [rcx+0D98h]
0x14007eedc  mov     rcx, cs:WdfDriverGlobals
0x14007eee3  mov     rax, r10
0x14007eee6  call    _guard_dispatch_icall
0x14007eeeb  lea     r14, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x14007eef2  lea     rbp, WPP_RECORDER_INITIALIZED
0x14007eef9  test    eax, eax
0x14007eefb  jns     short loc_14007EF2C
0x14007eefd  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14007ef04  jz      short loc_14007EF2C
0x14007ef06  mov     rcx, [rbx+8]
0x14007ef0a  mov     r9d, 5Eh ; '^'
0x14007ef10  mov     dword ptr [rsp+68h+var_40], eax
0x14007ef14  mov     [rsp+68h+var_48], r14
0x14007ef19  mov     rcx, [rcx+598h]
0x14007ef20  lea     r8d, [r9-5Ch]
0x14007ef24  mov     dl, r8b
0x14007ef27  call    WPP_RECORDER_SF_d
0x14007ef2c  mov     rdx, [rbx+10h]
0x14007ef30  mov     r9b, [rbx+0A70h]
0x14007ef37  mov     r8, [rbx+0A68h]
0x14007ef3e  mov     rcx, [rbx]
0x14007ef41  movzx   edx, word ptr [rdx+30h]
0x14007ef45  call    HUBFDO_CleanupDeviceInterfaceForBillboard
0x14007ef4a  test    eax, eax
0x14007ef4c  jns     short loc_14007EF7D
0x14007ef4e  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14007ef55  jz      short loc_14007EF7D
0x14007ef57  mov     rcx, [rbx+8]
0x14007ef5b  mov     r9d, 5Fh ; '_'
0x14007ef61  mov     dword ptr [rsp+68h+var_40], eax
0x14007ef65  mov     [rsp+68h+var_48], r14
0x14007ef6a  mov     rcx, [rcx+598h]
0x14007ef71  lea     r8d, [r9-5Dh]
0x14007ef75  mov     dl, r8b
0x14007ef78  call    WPP_RECORDER_SF_d
0x14007ef7d  mov     [rsp+68h+var_38], 0
0x14007ef85  lea     rcx, WNF_USB_BILLBOARD_CHANGE
0x14007ef8c  mov     dword ptr [rsp+68h+var_40], 0
0x14007ef94  xor     r9d, r9d
0x14007ef97  xor     r8d, r8d
0x14007ef9a  mov     [rsp+68h+var_48], 0
0x14007efa3  xor     edx, edx
0x14007efa5  call    cs:__imp_ZwUpdateWnfStateData
0x14007efac  nop     dword ptr [rax+rax+00h]
0x14007efb1  test    eax, eax
0x14007efb3  jns     short loc_14007EFE4
0x14007efb5  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14007efbc  jz      short loc_14007EFE4
0x14007efbe  mov     rcx, [rbx+8]
0x14007efc2  mov     r9d, 60h ; '`'
0x14007efc8  mov     dword ptr [rsp+68h+var_40], eax
0x14007efcc  mov     [rsp+68h+var_48], r14
0x14007efd1  mov     rcx, [rcx+598h]
0x14007efd8  lea     r8d, [r9-5Eh]
0x14007efdc  mov     dl, r8b
0x14007efdf  call    WPP_RECORDER_SF_d
0x14007efe4  mov     rax, [rbx+0A60h]
0x14007efeb  mov     rcx, [rax]; P
0x14007efee  test    rcx, rcx
0x14007eff1  jz      short loc_14007F004
0x14007eff3  mov     edx, 68334855h; Tag
0x14007eff8  call    cs:__imp_ExFreePoolWithTag
0x14007efff  nop     dword ptr [rax+rax+00h]
0x14007f004  mov     rax, [rbx+0A60h]
0x14007f00b  mov     qword ptr [rax], 0
0x14007f012  mov     rcx, [rbx+0A60h]; P
0x14007f019  test    rcx, rcx
0x14007f01c  jz      short loc_14007F02F
0x14007f01e  mov     edx, 68334855h; Tag
0x14007f023  call    cs:__imp_ExFreePoolWithTag
0x14007f02a  nop     dword ptr [rax+rax+00h]
0x14007f02f  mov     qword ptr [rbx+0A60h], 0
0x14007f03a  mov     rbx, [rsp+68h+arg_0]
0x14007f03f  mov     rbp, [rsp+68h+arg_8]
0x14007f044  add     rsp, 60h
0x14007f048  pop     r14
0x14007f04a  retn
```
