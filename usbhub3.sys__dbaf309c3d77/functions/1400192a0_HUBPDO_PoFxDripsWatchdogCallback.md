# HUBPDO_PoFxDripsWatchdogCallback

- ea: `0x1400192a0`
- end: `0x140019610`
- name: `HUBPDO_PoFxDripsWatchdogCallback`
- size: `880`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400024b8`
- `0x1400192a0`
- `0x14001c704`
- `0x140045570`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140019304`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140019304`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400195a3`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400195a3`

## pseudocode

```c
void __fastcall HUBPDO_PoFxDripsWatchdogCallback(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  NTSTATUS v4; // eax
  int v5; // edx
  _UNKNOWN **v6; // rcx
  __int64 v7; // r9
  __int64 v8; // rax
  int v9; // eax
  int v10; // edx
  _UNKNOWN **v11; // rcx
  __int64 v12; // r9
  __int64 v13; // rax
  __int128 v14; // [rsp+40h] [rbp-9h] BYREF
  __int64 v15; // [rsp+50h] [rbp+7h]
  __int128 v16; // [rsp+58h] [rbp+Fh] BYREF
  __int128 v17; // [rsp+68h] [rbp+1Fh]
  __int128 v18; // [rsp+78h] [rbp+2Fh]
  __int64 *v19; // [rsp+88h] [rbp+3Fh]
  __int64 v20; // [rsp+B8h] [rbp+6Fh] BYREF

  v2 = *(_QWORD *)(a2 + 64);
  LODWORD(v19) = 0;
  LODWORD(v15) = 0;
  v20 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v14 = 0;
  v4 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 424), "DRIPS SR Tag", File, 1u, 0x20u);
  if ( v4 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, v2);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *))(WdfFunctions_01015 + 1640))(
      WdfDriverGlobals,
      v8,
      "DRIPS SR Tag",
      11669,
      "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubpdo.c");
    *(_QWORD *)&v17 = 0;
    v19 = off_14006B298;
    v16 = 0;
    LODWORD(v16) = 56;
    v18 = 0;
    *((_QWORD *)&v17 + 1) = 0x100000001LL;
    *(_QWORD *)&v18 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(
                        WdfDriverGlobals,
                        v2);
    v15 = 1;
    *(_QWORD *)&v14 = 24;
    *((_QWORD *)&v14 + 1) = HUBPDO_EvtWorkItemDripsWatchDogCallback;
    v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int128 *, __int64 *))(WdfFunctions_01015 + 3032))(
           WdfDriverGlobals,
           &v14,
           &v16,
           &v20);
    if ( v9 >= 0 )
    {
      *(_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                   WdfDriverGlobals,
                   v20,
                   off_14006B298) = a2;
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 3040))(WdfDriverGlobals, v20);
    }
    else
    {
      v11 = &WPP_RECORDER_INITIALIZED;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 24) + 8LL) + 1432LL),
          v10,
          2,
          168,
          (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
          v9);
      }
      if ( (byte_14006ED43 & 2) != 0 )
      {
        v12 = *(_QWORD *)(v2 + 24);
        McTemplateK0pqhhh_EtwWriteTransfer(
          (_DWORD)v11,
          (unsigned int)USBHUB3_ETW_EVENT_DEVICE_DRIPS_WATCHDOG_COMPLETE,
          v12 + 1524,
          *(_QWORD *)(v12 + 24),
          10,
          *(_WORD *)(v12 + 2004),
          *(_WORD *)(v12 + 2006),
          *(_WORD *)(v12 + 2008));
      }
      v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, v2);
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *))(WdfFunctions_01015
                                                                                                + 1648))(
        WdfDriverGlobals,
        v13,
        "DRIPS SR Tag",
        11697,
        "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubpdo.c");
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 424), "DRIPS SR Tag", 0x20u);
    }
  }
  else
  {
    v6 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 24) + 8LL) + 1432LL),
        v5,
        2,
        167,
        (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
        v4);
    }
    if ( (byte_14006ED43 & 2) != 0 )
    {
      v7 = *(_QWORD *)(v2 + 24);
      McTemplateK0pqhhh_EtwWriteTransfer(
        (_DWORD)v6,
        (unsigned int)USBHUB3_ETW_EVENT_DEVICE_DRIPS_WATCHDOG_COMPLETE,
        v7 + 1524,
        *(_QWORD *)(v7 + 24),
        9,
        *(_WORD *)(v7 + 2004),
        *(_WORD *)(v7 + 2006),
        *(_WORD *)(v7 + 2008));
    }
  }
}

```

## disassembly

```asm
0x1400192a0  mov     [rsp-8+arg_0], rbx
0x1400192a5  mov     [rsp-8+arg_10], rsi
0x1400192aa  push    rbp
0x1400192ab  push    rdi
0x1400192ac  push    r13
0x1400192ae  lea     rbp, [rsp-47h]
0x1400192b3  sub     rsp, 90h
0x1400192ba  mov     rbx, [rdx+40h]
0x1400192be  lea     r8, File; File
0x1400192c5  xor     eax, eax
0x1400192c7  mov     [rsp+0A0h+RemlockSize], 20h ; ' '; RemlockSize
0x1400192cf  xorps   xmm0, xmm0
0x1400192d2  mov     dword ptr [rbp+57h+var_18], eax
0x1400192d5  mov     rdi, rdx
0x1400192d8  mov     dword ptr [rbp+57h+var_50], eax
0x1400192db  lea     rsi, [rbx+1A8h]
0x1400192e2  mov     [rbp+57h+arg_8], rax
0x1400192e6  mov     rcx, rsi; RemoveLock
0x1400192e9  lea     r9d, [rax+1]; Line
0x1400192ed  lea     rdx, DripsWatchDogTag; "DRIPS SR Tag"
0x1400192f4  movups  [rbp+57h+var_48], xmm0
0x1400192f8  movups  [rbp+57h+var_38], xmm0
0x1400192fc  movups  [rbp+57h+var_28], xmm0
0x140019300  movups  [rbp+57h+var_60], xmm0
0x140019304  call    cs:__imp_IoAcquireRemoveLockEx
0x14001930b  nop     dword ptr [rax+rax+00h]
0x140019310  test    eax, eax
0x140019312  jns     loc_1400193B7
0x140019318  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001931f  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140019326  jz      short loc_14001935B
0x140019328  mov     rcx, [rbx+18h]
0x14001932c  mov     r8d, 2
0x140019332  mov     [rsp+0A0h+var_78], eax
0x140019336  mov     r9d, 0A7h
0x14001933c  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x140019343  mov     dl, r8b
0x140019346  mov     qword ptr [rsp+0A0h+RemlockSize], rax
0x14001934b  mov     rcx, [rcx+8]
0x14001934f  mov     rcx, [rcx+598h]
0x140019356  call    WPP_RECORDER_SF_d
0x14001935b  test    cs:byte_14006ED43, 2
0x140019362  jz      loc_1400195F7
0x140019368  mov     r9, [rbx+18h]
0x14001936c  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_DRIPS_WATCHDOG_COMPLETE
0x140019373  movzx   eax, word ptr [r9+7D8h]
0x14001937b  lea     r8, [r9+5F4h]
0x140019382  mov     [rsp+0A0h+var_68], ax
0x140019387  movzx   eax, word ptr [r9+7D6h]
0x14001938f  mov     [rsp+0A0h+var_70], ax
0x140019394  movzx   eax, word ptr [r9+7D4h]
0x14001939c  mov     r9, [r9+18h]
0x1400193a0  mov     word ptr [rsp+0A0h+var_78], ax
0x1400193a5  mov     [rsp+0A0h+RemlockSize], 9
0x1400193ad  call    McTemplateK0pqhhh_EtwWriteTransfer
0x1400193b2  jmp     loc_1400195F7
0x1400193b7  mov     rax, cs:WdfFunctions_01015
0x1400193be  mov     rdx, rbx
0x1400193c1  mov     rcx, cs:WdfDriverGlobals
0x1400193c8  mov     rax, [rax+660h]
0x1400193cf  call    _guard_dispatch_icall
0x1400193d4  mov     rcx, cs:WdfFunctions_01015
0x1400193db  lea     r13, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x1400193e2  mov     rdx, rax
0x1400193e5  mov     qword ptr [rsp+0A0h+RemlockSize], r13
0x1400193ea  mov     r9d, 2D95h
0x1400193f0  lea     r8, DripsWatchDogTag; "DRIPS SR Tag"
0x1400193f7  mov     r10, [rcx+668h]
0x1400193fe  mov     rcx, cs:WdfDriverGlobals
0x140019405  mov     rax, r10
0x140019408  call    _guard_dispatch_icall
0x14001940d  mov     rax, cs:off_14006B298
0x140019414  xorps   xmm0, xmm0
0x140019417  mov     rcx, cs:WdfDriverGlobals
0x14001941e  mov     rdx, rbx
0x140019421  movups  [rbp+57h+var_38], xmm0
0x140019425  mov     [rbp+57h+var_18], rax
0x140019429  mov     rax, cs:WdfFunctions_01015
0x140019430  movups  [rbp+57h+var_48], xmm0
0x140019434  mov     dword ptr [rbp+57h+var_48], 38h ; '8'
0x14001943b  movups  [rbp+57h+var_28], xmm0
0x14001943f  mov     dword ptr [rbp+57h+var_38+8], 1
0x140019446  mov     dword ptr [rbp+57h+var_38+0Ch], 1
0x14001944d  mov     rax, [rax+660h]
0x140019454  call    _guard_dispatch_icall
0x140019459  mov     rcx, cs:WdfDriverGlobals
0x140019460  lea     r9, [rbp+57h+arg_8]
0x140019464  mov     qword ptr [rbp+57h+var_28], rax
0x140019468  lea     r8, [rbp+57h+var_48]
0x14001946c  xor     eax, eax
0x14001946e  lea     rdx, [rbp+57h+var_60]
0x140019472  mov     [rbp+57h+var_50], rax
0x140019476  xorps   xmm0, xmm0
0x140019479  movups  [rbp+57h+var_60], xmm0
0x14001947d  lea     rax, HUBPDO_EvtWorkItemDripsWatchDogCallback
0x140019484  mov     dword ptr [rbp+57h+var_60], 18h
0x14001948b  mov     qword ptr [rbp+57h+var_60+8], rax
0x14001948f  mov     rax, cs:WdfFunctions_01015
0x140019496  mov     byte ptr [rbp+57h+var_50], 1
0x14001949a  mov     rax, [rax+0BD8h]
0x1400194a1  call    _guard_dispatch_icall
0x1400194a6  test    eax, eax
0x1400194a8  jns     loc_1400195B1
0x1400194ae  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400194b5  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400194bc  jz      short loc_1400194F1
0x1400194be  mov     rcx, [rbx+18h]
0x1400194c2  mov     r8d, 2
0x1400194c8  mov     [rsp+0A0h+var_78], eax
0x1400194cc  mov     r9d, 0A8h
0x1400194d2  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x1400194d9  mov     dl, r8b
0x1400194dc  mov     qword ptr [rsp+0A0h+RemlockSize], rax
0x1400194e1  mov     rcx, [rcx+8]
0x1400194e5  mov     rcx, [rcx+598h]
0x1400194ec  call    WPP_RECORDER_SF_d
0x1400194f1  test    cs:byte_14006ED43, 2
0x1400194f8  jz      short loc_140019544
0x1400194fa  mov     r9, [rbx+18h]
0x1400194fe  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_DRIPS_WATCHDOG_COMPLETE
0x140019505  movzx   eax, word ptr [r9+7D8h]
0x14001950d  lea     r8, [r9+5F4h]
0x140019514  mov     [rsp+0A0h+var_68], ax
0x140019519  movzx   eax, word ptr [r9+7D6h]
0x140019521  mov     [rsp+0A0h+var_70], ax
0x140019526  movzx   eax, word ptr [r9+7D4h]
0x14001952e  mov     r9, [r9+18h]
0x140019532  mov     word ptr [rsp+0A0h+var_78], ax
0x140019537  mov     [rsp+0A0h+RemlockSize], 0Ah
0x14001953f  call    McTemplateK0pqhhh_EtwWriteTransfer
0x140019544  mov     rax, cs:WdfFunctions_01015
0x14001954b  mov     rdx, rbx
0x14001954e  mov     rcx, cs:WdfDriverGlobals
0x140019555  mov     rax, [rax+660h]
0x14001955c  call    _guard_dispatch_icall
0x140019561  mov     r9, cs:WdfFunctions_01015
0x140019568  lea     r8, DripsWatchDogTag; "DRIPS SR Tag"
0x14001956f  mov     rcx, cs:WdfDriverGlobals
0x140019576  mov     rdx, rax
0x140019579  mov     qword ptr [rsp+0A0h+RemlockSize], r13
0x14001957e  mov     r10, [r9+670h]
0x140019585  mov     r9d, 2DB1h
0x14001958b  mov     rax, r10
0x14001958e  call    _guard_dispatch_icall
0x140019593  mov     r8d, 20h ; ' '; RemlockSize
0x140019599  lea     rdx, DripsWatchDogTag; "DRIPS SR Tag"
0x1400195a0  mov     rcx, rsi; RemoveLock
0x1400195a3  call    cs:__imp_IoReleaseRemoveLockEx
0x1400195aa  nop     dword ptr [rax+rax+00h]
0x1400195af  jmp     short loc_1400195F7
0x1400195b1  mov     rax, cs:WdfFunctions_01015
0x1400195b8  mov     r8, cs:off_14006B298
0x1400195bf  mov     rdx, [rbp+57h+arg_8]
0x1400195c3  mov     rcx, cs:WdfDriverGlobals
0x1400195ca  mov     rax, [rax+650h]
0x1400195d1  call    _guard_dispatch_icall
0x1400195d6  mov     [rax], rdi
0x1400195d9  mov     rax, cs:WdfFunctions_01015
0x1400195e0  mov     rdx, [rbp+57h+arg_8]
0x1400195e4  mov     rcx, cs:WdfDriverGlobals
0x1400195eb  mov     rax, [rax+0BE0h]
0x1400195f2  call    _guard_dispatch_icall
0x1400195f7  lea     r11, [rsp+0A0h+var_10]
0x1400195ff  mov     rbx, [r11+20h]
0x140019603  mov     rsi, [r11+30h]
0x140019607  mov     rsp, r11
0x14001960a  pop     r13
0x14001960c  pop     rdi
0x14001960d  pop     rbp
0x14001960e  retn
```
