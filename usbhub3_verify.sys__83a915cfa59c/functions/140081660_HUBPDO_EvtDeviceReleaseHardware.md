# HUBPDO_EvtDeviceReleaseHardware

- ea: `0x140081660`
- end: `0x140081996`
- name: `HUBPDO_EvtDeviceReleaseHardware`
- size: `822`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140001f94`
- `0x1400083b4`
- `0x14000a520`
- `0x1400336a8`
- `0x1400449ac`
- `0x140045530`
- `0x140045570`
- `0x140081660`
- `0x1400858d8`
- `0x14008ec78`
- `0x140091750`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x140081812`
- `ntoskrnl!KeClearEvent` at `0x140081812`
- `ntoskrnl!EtwActivityIdControl` at `0x1400816f8`
- `ntoskrnl!EtwActivityIdControl` at `0x1400816f8`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x140081746`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x140081746`

## string_xrefs

- `0x14008182e`: `Device PDORemoved`

## pseudocode

```c
__int64 __fastcall HUBPDO_EvtDeviceReleaseHardware(__int64 a1)
{
  __int64 v2; // rbx
  __int64 *v3; // rdi
  __int64 v4; // rcx
  __int64 v5; // rsi
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rcx
  int v11; // eax
  _BYTE v13[8]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v14; // [rsp+38h] [rbp-30h] BYREF

  v14 = 0;
  v13[0] = 0;
  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006B1D0);
  v3 = *(__int64 **)(v2 + 24);
  if ( (*(_DWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
                      WdfDriverGlobals,
                      WdfDriverGlobals->Driver,
                      off_14006B2C0)
                  + 4)
      & 0x1000) != 0
    && EtwActivityIdControl(3u, (LPGUID)(v3 + 273)) >= 0 )
  {
    v14 = *(_OWORD *)(v3 + 273);
    _InterlockedOr((volatile signed __int32 *)v3 + 411, 0x80u);
  }
  if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 2) != 0 )
    McTemplateK0p_EtwWriteTransfer(v4, USBHUB3_ETW_EVENT_DEVICE_RELEASE_HARDWARE_START, &v14, v3[3]);
  if ( *(_QWORD *)(v2 + 392) )
  {
    SleepstudyHelper_UnregisterComponent();
    *(_QWORD *)(v2 + 392) = 0;
  }
  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006B1D0);
  *(_BYTE *)v5 = 1;
  _InterlockedAnd((volatile signed __int32 *)v3 + 411, 0xFFFFBFFF);
  v13[0] = 0;
  v6 = *v3;
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, *v3);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *))(WdfFunctions_01015 + 1640))(
    WdfDriverGlobals,
    v7,
    "ControllerPowerReference Tag",
    94,
    "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\ucx.h");
  (*(void (__fastcall **)(_QWORD, _BYTE *))(v6 + 568))(*(_QWORD *)(v6 + 248), v13);
  KeClearEvent((PRKEVENT)(v3 + 199));
  HUBSM_AddDsmEvent(v3, 4099);
  HUBMISC_WaitForSignal(v3 + 199);
  v8 = *v3;
  (*(void (__fastcall **)(_QWORD, _BYTE *))(*v3 + 576))(*(_QWORD *)(*v3 + 248), v13);
  v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, v8);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *))(WdfFunctions_01015 + 1648))(
    WdfDriverGlobals,
    v9,
    "ControllerPowerReference Tag",
    130,
    "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\ucx.h");
  v11 = *(_DWORD *)(v5 + 32);
  if ( (v11 & 0x400) != 0 )
  {
    _InterlockedAnd((volatile signed __int32 *)(v5 + 32), 0xFFFFFBFF);
  }
  else
  {
    if ( (v11 & 0x800) != 0 )
    {
      _InterlockedAnd((volatile signed __int32 *)(v5 + 32), 0xFFFFF7FF);
      HUBREG_DeleteUxdSettings(*(_QWORD *)(v5 + 24), 1);
    }
    if ( (v3[205] & 0x40000) != 0 )
    {
      HUBWNF_PublishUsbPartnerDualRoleFeatures(*(_QWORD *)(v3[1] + 1416), 0, 0);
      _InterlockedAnd((volatile signed __int32 *)v3 + 410, 0xFFFBFFFF);
    }
    if ( (*((_DWORD *)v3 + 413) & 0x4000000) != 0 )
      DereferenceDeviceResetInterface((void *)(v5 + 456));
    v10 = v3[1];
    if ( _bittest((const signed __int32 *)(v10 + 204), 0xBu) && ((*((_DWORD *)v3 + 683) - 2) & 0xFFFFFFFD) == 0 )
      TUNNEL_ReleaseUsb4HostPowerReferenceForPort();
  }
  if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 2) != 0 )
    McTemplateK0pq_EtwWriteTransfer(v10, USBHUB3_ETW_EVENT_DEVICE_RELEASE_HARDWARE_COMPLETE, &v14, v3[3], 0);
  _InterlockedAnd((volatile signed __int32 *)v3 + 411, 0xFFFFFF7F);
  return 0;
}

```

## disassembly

```asm
0x140081660  mov     [rsp+arg_8], rbx
0x140081665  mov     [rsp+arg_10], rbp
0x14008166a  push    rsi
0x14008166b  push    rdi
0x14008166c  push    r14
0x14008166e  sub     rsp, 50h
0x140081672  mov     rax, cs:__security_cookie
0x140081679  xor     rax, rsp
0x14008167c  mov     [rsp+68h+var_20], rax
0x140081681  mov     rax, cs:WdfFunctions_01015
0x140081688  xorps   xmm0, xmm0
0x14008168b  mov     r8, cs:off_14006B1D0
0x140081692  mov     rbp, rcx
0x140081695  movups  [rsp+68h+var_30], xmm0
0x14008169a  mov     [rsp+68h+var_38], 0
0x14008169f  mov     rdx, rcx
0x1400816a2  mov     rax, [rax+650h]
0x1400816a9  mov     rcx, cs:WdfDriverGlobals
0x1400816b0  call    _guard_dispatch_icall
0x1400816b5  mov     rcx, cs:WdfFunctions_01015
0x1400816bc  mov     rbx, rax
0x1400816bf  mov     r8, cs:off_14006B2C0
0x1400816c6  mov     rdi, [rax+18h]
0x1400816ca  mov     rax, [rcx+650h]
0x1400816d1  mov     rcx, cs:WdfDriverGlobals
0x1400816d8  mov     rdx, [rcx]
0x1400816db  call    _guard_dispatch_icall
0x1400816e0  test    dword ptr [rax+4], 1000h
0x1400816e7  jz      short loc_14008171C
0x1400816e9  lea     rsi, [rdi+888h]
0x1400816f0  mov     ecx, 3; ControlCode
0x1400816f5  mov     rdx, rsi; ActivityId
0x1400816f8  call    cs:__imp_EtwActivityIdControl
0x1400816ff  nop     dword ptr [rax+rax+00h]
0x140081704  test    eax, eax
0x140081706  js      short loc_14008171C
0x140081708  movups  xmm0, xmmword ptr [rsi]
0x14008170b  movdqu  [rsp+68h+var_30], xmm0
0x140081711  lock or dword ptr [rdi+66Ch], 80h
0x14008171c  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, 2
0x140081723  jz      short loc_14008173A
0x140081725  mov     r9, [rdi+18h]
0x140081729  lea     r8, [rsp+68h+var_30]
0x14008172e  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_RELEASE_HARDWARE_START
0x140081735  call    McTemplateK0p_EtwWriteTransfer
0x14008173a  mov     rcx, [rbx+188h]
0x140081741  test    rcx, rcx
0x140081744  jz      short loc_14008175D
0x140081746  call    cs:__imp_SleepstudyHelper_UnregisterComponent
0x14008174d  nop     dword ptr [rax+rax+00h]
0x140081752  mov     qword ptr [rbx+188h], 0
0x14008175d  mov     rax, cs:WdfFunctions_01015
0x140081764  mov     rdx, rbp
0x140081767  mov     r8, cs:off_14006B1D0
0x14008176e  mov     rcx, cs:WdfDriverGlobals
0x140081775  mov     rax, [rax+650h]
0x14008177c  call    _guard_dispatch_icall
0x140081781  mov     rsi, rax
0x140081784  mov     byte ptr [rax], 1
0x140081787  lock and dword ptr [rdi+66Ch], 0FFFFBFFFh
0x140081792  mov     rcx, cs:WdfFunctions_01015
0x140081799  mov     [rsp+68h+var_38], 0
0x14008179e  mov     rbx, [rdi]
0x1400817a1  mov     rdx, rbx
0x1400817a4  mov     rax, [rcx+660h]
0x1400817ab  mov     rcx, cs:WdfDriverGlobals
0x1400817b2  call    _guard_dispatch_icall
0x1400817b7  mov     rcx, cs:WdfFunctions_01015
0x1400817be  lea     r14, aOnecoreDrivers_2; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x1400817c5  mov     rdx, rax
0x1400817c8  mov     [rsp+68h+var_48], r14
0x1400817cd  mov     r9d, 5Eh ; '^'
0x1400817d3  lea     r8, ControllerPowerReferenceTag; "ControllerPowerReference Tag"
0x1400817da  mov     r10, [rcx+668h]
0x1400817e1  mov     rcx, cs:WdfDriverGlobals
0x1400817e8  mov     rax, r10
0x1400817eb  call    _guard_dispatch_icall
0x1400817f0  mov     rax, [rbx+238h]
0x1400817f7  lea     rdx, [rsp+68h+var_38]
0x1400817fc  mov     rcx, [rbx+0F8h]
0x140081803  call    _guard_dispatch_icall
0x140081808  lea     rbx, [rdi+638h]
0x14008180f  mov     rcx, rbx; Event
0x140081812  call    cs:__imp_KeClearEvent
0x140081819  nop     dword ptr [rax+rax+00h]
0x14008181e  mov     edx, 1003h
0x140081823  mov     rcx, rdi
0x140081826  call    HUBSM_AddDsmEvent
0x14008182b  mov     r8, rbp
0x14008182e  lea     rdx, aDevicePdoremov; "Device PDORemoved"
0x140081835  mov     rcx, rbx; Object
0x140081838  call    HUBMISC_WaitForSignal
0x14008183d  mov     rbx, [rdi]
0x140081840  lea     rdx, [rsp+68h+var_38]
0x140081845  mov     rax, [rbx+240h]
0x14008184c  mov     rcx, [rbx+0F8h]
0x140081853  call    _guard_dispatch_icall
0x140081858  mov     rax, cs:WdfFunctions_01015
0x14008185f  mov     rdx, rbx
0x140081862  mov     rcx, cs:WdfDriverGlobals
0x140081869  mov     rax, [rax+660h]
0x140081870  call    _guard_dispatch_icall
0x140081875  mov     rcx, cs:WdfFunctions_01015
0x14008187c  lea     r8, ControllerPowerReferenceTag; "ControllerPowerReference Tag"
0x140081883  mov     rdx, rax
0x140081886  mov     [rsp+68h+var_48], r14
0x14008188b  mov     r9d, 82h
0x140081891  mov     r10, [rcx+670h]
0x140081898  mov     rcx, cs:WdfDriverGlobals
0x14008189f  mov     rax, r10
0x1400818a2  call    _guard_dispatch_icall
0x1400818a7  mov     eax, [rsi+20h]
0x1400818aa  bt      eax, 0Ah
0x1400818ae  jnb     short loc_1400818BD
0x1400818b0  lock and dword ptr [rsi+20h], 0FFFFFBFFh
0x1400818b8  jmp     loc_140081940
0x1400818bd  bt      eax, 0Bh
0x1400818c1  jnb     short loc_1400818D9
0x1400818c3  lock and dword ptr [rsi+20h], 0FFFFF7FFh
0x1400818cb  mov     rcx, [rsi+18h]
0x1400818cf  mov     edx, 1
0x1400818d4  call    HUBREG_DeleteUxdSettings
0x1400818d9  test    dword ptr [rdi+668h], 40000h
0x1400818e3  jz      short loc_140081905
0x1400818e5  mov     rcx, [rdi+8]
0x1400818e9  xor     r8d, r8d
0x1400818ec  xor     edx, edx
0x1400818ee  mov     rcx, [rcx+588h]
0x1400818f5  call    HUBWNF_PublishUsbPartnerDualRoleFeatures
0x1400818fa  lock and dword ptr [rdi+668h], 0FFFBFFFFh
0x140081905  test    dword ptr [rdi+674h], 4000000h
0x14008190f  jz      short loc_14008191D
0x140081911  lea     rcx, [rsi+1C8h]; void *
0x140081918  call    DereferenceDeviceResetInterface
0x14008191d  mov     rcx, [rdi+8]
0x140081921  bt      dword ptr [rcx+0CCh], 0Bh
0x140081929  jnb     short loc_140081940
0x14008192b  mov     eax, [rdi+0AACh]
0x140081931  sub     eax, 2
0x140081934  test    eax, 0FFFFFFFDh
0x140081939  jnz     short loc_140081940
0x14008193b  call    TUNNEL_ReleaseUsb4HostPowerReferenceForPort
0x140081940  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, 2
0x140081947  jz      short loc_140081966
0x140081949  mov     r9, [rdi+18h]
0x14008194d  lea     r8, [rsp+68h+var_30]
0x140081952  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_RELEASE_HARDWARE_COMPLETE
0x140081959  mov     dword ptr [rsp+68h+var_48], 0
0x140081961  call    McTemplateK0pq_EtwWriteTransfer
0x140081966  lock and dword ptr [rdi+66Ch], 0FFFFFF7Fh
0x140081971  xor     eax, eax
0x140081973  mov     rcx, [rsp+68h+var_20]
0x140081978  xor     rcx, rsp; StackCookie
0x14008197b  call    __security_check_cookie
0x140081980  lea     r11, [rsp+68h+var_18]
0x140081985  mov     rbx, [r11+28h]
0x140081989  mov     rbp, [r11+30h]
0x14008198d  mov     rsp, r11
0x140081990  pop     r14
0x140081992  pop     rdi
0x140081993  pop     rsi
0x140081994  retn
```
