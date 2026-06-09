# HUBFDO_CompleteGetDescriptorRequest

- ea: `0x14000ca70`
- end: `0x14000cbab`
- name: `HUBFDO_CompleteGetDescriptorRequest`
- size: `315`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000b3ac`
- `0x14002adb0`
- `0x14002af00`
- `0x14007afe0`

## callees

- `0x1400024b8`
- `0x14000ca70`
- `0x14000f304`
- `0x140045530`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall HUBFDO_CompleteGetDescriptorRequest(__int64 a1, int a2, __int64 a3, int a4, unsigned int a5)
{
  int v7; // ebp
  __int64 v9; // rcx
  __int64 v10; // r8
  int v11; // eax
  __int64 v13; // [rsp+20h] [rbp-48h]
  __int64 v14; // [rsp+28h] [rbp-40h]
  __int128 v15; // [rsp+30h] [rbp-38h] BYREF

  v15 = 0;
  v7 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(a1 + 2536),
      a2,
      3,
      71,
      (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids,
      a4,
      v15);
  }
  if ( (byte_14006ED41 & 4) != 0 )
  {
    v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2280))(WdfDriverGlobals, a3);
    v11 = g_IoGetActivityIdIrp ? g_IoGetActivityIdIrp(v9, &v15, v10) : -1073741275;
    if ( (byte_14006ED41 & 4) != 0 )
    {
      LODWORD(v14) = a4;
      LODWORD(v13) = v7;
      McTemplateK0pqq_EtwWriteTransfer(
        v9,
        (const EVENT_DESCRIPTOR *)USBHUB3_ETW_EVENT_HUB_IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION_COMPLETE,
        (const GUID *)((unsigned __int64)&v15 & -(__int64)(v11 >= 0)),
        *(_QWORD *)(a1 + 248),
        v13,
        v14);
    }
  }
  if ( a4 >= 0 )
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64))(WdfFunctions_01015 + 2120))(
             WdfDriverGlobals,
             a3,
             (unsigned int)a4,
             a5 + 12LL);
  else
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2104))(
             WdfDriverGlobals,
             a3,
             (unsigned int)a4);
}

```

## disassembly

```asm
0x14000ca70  mov     [rsp+arg_8], rbx
0x14000ca75  push    rbp
0x14000ca76  push    rsi
0x14000ca77  push    rdi
0x14000ca78  sub     rsp, 50h
0x14000ca7c  mov     rax, cs:__security_cookie
0x14000ca83  xor     rax, rsp
0x14000ca86  mov     [rsp+68h+var_28], rax
0x14000ca8b  xorps   xmm0, xmm0
0x14000ca8e  mov     ebx, r9d
0x14000ca91  movups  [rsp+68h+var_38], xmm0
0x14000ca96  mov     rdi, r8
0x14000ca99  mov     ebp, edx
0x14000ca9b  mov     rsi, rcx
0x14000ca9e  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000caa5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000caac  jz      short loc_14000CAD6
0x14000caae  mov     rcx, [rcx+9E8h]
0x14000cab5  lea     rax, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x14000cabc  mov     r9d, 47h ; 'G'
0x14000cac2  mov     dword ptr [rsp+68h+var_40], ebx
0x14000cac6  mov     dl, 4
0x14000cac8  mov     [rsp+68h+var_48], rax
0x14000cacd  lea     r8d, [r9-44h]
0x14000cad1  call    WPP_RECORDER_SF_d
0x14000cad6  test    cs:byte_14006ED41, 4
0x14000cadd  jz      short loc_14000CB52
0x14000cadf  mov     rax, cs:WdfFunctions_01015
0x14000cae6  mov     rdx, rdi
0x14000cae9  mov     rcx, cs:WdfDriverGlobals
0x14000caf0  mov     rax, [rax+8E8h]
0x14000caf7  call    _guard_dispatch_icall
0x14000cafc  mov     rcx, rax
0x14000caff  mov     rax, cs:g_IoGetActivityIdIrp
0x14000cb06  test    rax, rax
0x14000cb09  jnz     short loc_14000CB12
0x14000cb0b  mov     eax, 0C0000225h
0x14000cb10  jmp     short loc_14000CB1C
0x14000cb12  lea     rdx, [rsp+68h+var_38]
0x14000cb17  call    _guard_dispatch_icall
0x14000cb1c  test    cs:byte_14006ED41, 4
0x14000cb23  jz      short loc_14000CB52
0x14000cb25  mov     r9, [rsi+0F8h]
0x14000cb2c  lea     rdx, USBHUB3_ETW_EVENT_HUB_IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION_COMPLETE
0x14000cb33  shr     eax, 1Fh
0x14000cb36  xor     al, 1
0x14000cb38  mov     dword ptr [rsp+68h+var_40], ebx
0x14000cb3c  neg     al
0x14000cb3e  mov     dword ptr [rsp+68h+var_48], ebp
0x14000cb42  lea     rax, [rsp+68h+var_38]
0x14000cb47  sbb     r8, r8
0x14000cb4a  and     r8, rax
0x14000cb4d  call    McTemplateK0pqq_EtwWriteTransfer
0x14000cb52  mov     rax, cs:WdfFunctions_01015
0x14000cb59  mov     r8d, ebx
0x14000cb5c  mov     rcx, cs:WdfDriverGlobals
0x14000cb63  mov     rdx, rdi
0x14000cb66  test    ebx, ebx
0x14000cb68  jns     short loc_14000CB78
0x14000cb6a  mov     rax, [rax+838h]
0x14000cb71  call    _guard_dispatch_icall
0x14000cb76  jmp     short loc_14000CB90
0x14000cb78  mov     r9d, [rsp+68h+arg_20]
0x14000cb80  mov     rax, [rax+848h]
0x14000cb87  add     r9, 0Ch
0x14000cb8b  call    _guard_dispatch_icall
0x14000cb90  mov     rcx, [rsp+68h+var_28]
0x14000cb95  xor     rcx, rsp; StackCookie
0x14000cb98  call    __security_check_cookie
0x14000cb9d  mov     rbx, [rsp+68h+arg_8]
0x14000cba2  add     rsp, 50h
0x14000cba6  pop     rdi
0x14000cba7  pop     rsi
0x14000cba8  pop     rbp
0x14000cba9  retn
```
