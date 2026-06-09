# HUBMISC_CreateNewDSM

- ea: `0x14002e514`
- end: `0x14002f0ac`
- name: `HUBMISC_CreateNewDSM`
- size: `2968`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140012250`

## callees

- `0x140001f94`
- `0x1400024b8`
- `0x1400067ac`
- `0x14001da68`
- `0x14002e514`
- `0x140045570`
- `0x140045940`

## import_xrefs

- `ntoskrnl!ExAllocateTimer` at `0x14002ea4e`
- `ntoskrnl!ExAllocateTimer` at `0x14002ea4e`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002e9ba`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002effe`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002e9ba`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002effe`
- `ntoskrnl!KeInitializeEvent` at `0x14002ebba`
- `ntoskrnl!KeInitializeEvent` at `0x14002ebd2`
- `ntoskrnl!KeInitializeEvent` at `0x14002ebea`
- `ntoskrnl!KeInitializeEvent` at `0x14002ebba`
- `ntoskrnl!KeInitializeEvent` at `0x14002ebd2`
- `ntoskrnl!KeInitializeEvent` at `0x14002ebea`
- `ntoskrnl!EtwActivityIdControl` at `0x14002e6db`
- `ntoskrnl!EtwActivityIdControl` at `0x14002e6db`
- `ntoskrnl!ExDeleteTimer` at `0x14002ee98`
- `ntoskrnl!ExDeleteTimer` at `0x14002ee98`

## string_xrefs

- `0x14002e63c`: `DSM Create Tag`

## pseudocode

```c
__int64 __fastcall HUBMISC_CreateNewDSM(__int64 *a1)
{
  int v2; // eax
  int v3; // edx
  __int64 v4; // rcx
  int v5; // ebx
  __int64 v6; // rdi
  NTSTATUS v7; // r13d
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rax
  _QWORD *v13; // r12
  int v14; // eax
  int v15; // r9d
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 Timer; // rax
  int v21; // edx
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rax
  int v25; // eax
  __int64 v26; // r8
  unsigned int v27; // ebx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v31; // [rsp+28h] [rbp-61h]
  __int128 v32; // [rsp+40h] [rbp-49h] BYREF
  __int128 v33; // [rsp+50h] [rbp-39h]
  __int64 v34; // [rsp+60h] [rbp-29h]
  __int128 v35; // [rsp+68h] [rbp-21h] BYREF
  __int64 (__fastcall *v36)(__int64); // [rsp+78h] [rbp-11h]
  __int64 v37; // [rsp+80h] [rbp-9h]
  __int128 v38; // [rsp+88h] [rbp-1h]
  __int64 *v39; // [rsp+98h] [rbp+Fh]
  __int64 v40; // [rsp+F8h] [rbp+6Fh] BYREF

  LODWORD(v34) = 0;
  v40 = 0;
  v36 = 0;
  v39 = off_14006B1A8;
  v35 = 0;
  LODWORD(v35) = 56;
  v32 = 0;
  v37 = 0x100000001LL;
  v33 = 0;
  v38 = 0;
  *(_QWORD *)&v38 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64 *))(WdfFunctions_01015 + 1632))(
                      WdfDriverGlobals,
                      a1);
  LODWORD(v37) = 2;
  v36 = HUBMISC_EvtDsmDestroy;
  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int64 *))(WdfFunctions_01015 + 1656))(
         WdfDriverGlobals,
         &v35,
         &v40);
  v5 = v2;
  if ( v2 < 0 )
  {
    v6 = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = 2;
      WPP_RECORDER_SF_d(a1[179], v3, 4, 46, (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids, v2);
    }
    v40 = 0;
    goto LABEL_33;
  }
  v7 = -1073741823;
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64 *))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, a1);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *))(WdfFunctions_01015 + 1640))(
    WdfDriverGlobals,
    v8,
    "DSM Create Tag",
    6962,
    "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubmisc.c");
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         v40,
         off_14006B1A8);
  memset((void *)v6, 0, 0xAB0u);
  if ( (*(_DWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
                      WdfDriverGlobals,
                      WdfDriverGlobals->Driver,
                      off_14006B2C0)
                  + 4)
      & 0x1000) != 0 )
    v7 = EtwActivityIdControl(3u, (LPGUID)(v6 + 1524));
  *(_QWORD *)(v6 + 8) = a1;
  *(_QWORD *)v6 = *a1;
  *(_WORD *)(v6 + 2720) = 0;
  *(_DWORD *)(v6 + 2724) = 259;
  *(_DWORD *)(v6 + 2728) = 0x40000000;
  v9 = *((unsigned int *)a1 + 51);
  if ( (v9 & 1) != 0 )
    _InterlockedAnd((volatile signed __int32 *)(v6 + 1640), 0xFFFFFFDF);
  else
    _InterlockedOr((volatile signed __int32 *)(v6 + 1640), 0x20u);
  if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 0x40) != 0 )
    McTemplateK0pq_EtwWriteTransfer(
      v9,
      USBHUB3_ETW_EVENT_DEVICE_ENUMERATION_START,
      v6 + 1524,
      *(_QWORD *)(*(_QWORD *)v6 + 248LL),
      *((unsigned __int16 *)a1 + 100));
  v39 = 0;
  v36 = 0;
  v37 = 0x100000001LL;
  v35 = 0;
  LODWORD(v35) = 56;
  v38 = 0;
  v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64 *))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, a1);
  v11 = *a1;
  *(_QWORD *)&v38 = v10;
  v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 336))(
          WdfDriverGlobals,
          *(_QWORD *)(v11 + 16));
  v13 = (_QWORD *)(v6 + 256);
  v14 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int64, __int64))(WdfFunctions_01015 + 1976))(
          WdfDriverGlobals,
          &v35,
          v12,
          v6 + 256);
  v5 = v14;
  if ( v14 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_16:
      *v13 = 0;
LABEL_33:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v31) = v5;
        LOBYTE(v3) = 2;
        WPP_RECORDER_SF_d(a1[179], v3, 4, 53, (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids, v31);
      }
      if ( Microsoft_Windows_USB_USBHUB3EnableBits < 0 )
      {
        if ( v6 )
          v26 = v6 + 1524;
        else
          v26 = 0;
        McTemplateK0pq_EtwWriteTransfer(
          v4,
          USBHUB3_ETW_EVENT_DEVICE_ENUMERATION_FAILED,
          v26,
          *(_QWORD *)(*a1 + 248),
          v5);
      }
      v27 = 3009;
      if ( v6 )
      {
        if ( *(_QWORD *)(v6 + 256) )
        {
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, const char *, __int64, const char *))(WdfFunctions_01015 + 1648))(
            WdfDriverGlobals,
            *(_QWORD *)(v6 + 256),
            "DSM Tag",
            7395,
            "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubmisc.c");
          *(_QWORD *)(v6 + 256) = 0;
        }
        v28 = *(_QWORD *)(v6 + 424);
        if ( v28 )
        {
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, const char *, __int64, const char *))(WdfFunctions_01015 + 1648))(
            WdfDriverGlobals,
            *(_QWORD *)(v6 + 424),
            "DSM Tag",
            7395,
            "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubmisc.c");
          *(_QWORD *)(v6 + 424) = 0;
        }
        v29 = *(_QWORD *)(v6 + 1552);
        if ( v29 )
        {
          LOBYTE(v28) = 1;
          ExDeleteTimer(v29, v28, 0, 0);
          *(_QWORD *)(v6 + 1552) = 0;
        }
        if ( *(_QWORD *)(v6 + 2424) )
        {
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, const char *, __int64, const char *))(WdfFunctions_01015 + 1648))(
            WdfDriverGlobals,
            *(_QWORD *)(v6 + 2424),
            "DSM Tag",
            7395,
            "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubmisc.c");
          *(_QWORD *)(v6 + 2424) = 0;
        }
        if ( *(_QWORD *)(v6 + 440) )
        {
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, const char *, __int64, const char *))(WdfFunctions_01015 + 1648))(
            WdfDriverGlobals,
            *(_QWORD *)(v6 + 440),
            "DSM Tag",
            7395,
            "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubmisc.c");
          *(_QWORD *)(v6 + 440) = 0;
        }
        if ( *(_QWORD *)(v6 + 1504) )
        {
          (*(void (**)(void))(*(_QWORD *)v6 + 512LL))();
          *(_QWORD *)(v6 + 1504) = 0;
        }
        if ( v40 )
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
      }
      return v27;
    }
    v15 = 47;
LABEL_15:
    LOBYTE(v3) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
      v3,
      5,
      v15,
      (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids,
      v14);
    goto LABEL_16;
  }
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, const char *, __int64, const char *))(WdfFunctions_01015 + 1640))(
    WdfDriverGlobals,
    *v13,
    "DSM Tag",
    7022,
    "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubmisc.c");
  *(_QWORD *)(v6 + 272) = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2280))(
                            WdfDriverGlobals,
                            *v13);
  v39 = 0;
  v36 = 0;
  v37 = 0x100000001LL;
  v35 = 0;
  LODWORD(v35) = 56;
  v38 = 0;
  v16 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64 *))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, a1);
  v17 = *a1;
  *(_QWORD *)&v38 = v16;
  v18 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 336))(
          WdfDriverGlobals,
          *(_QWORD *)(v17 + 16));
  v13 = (_QWORD *)(v6 + 424);
  v14 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int64, __int64))(WdfFunctions_01015 + 1976))(
          WdfDriverGlobals,
          &v35,
          v18,
          v6 + 424);
  v5 = v14;
  if ( v14 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_16;
    v15 = 48;
    goto LABEL_15;
  }
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, const char *, __int64, const char *))(WdfFunctions_01015 + 1640))(
    WdfDriverGlobals,
    *v13,
    "DSM Tag",
    7058,
    "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubmisc.c");
  *(_QWORD *)(v6 + 432) = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2280))(
                            WdfDriverGlobals,
                            *v13);
  *(_WORD *)(v6 + 2048) = 1033;
  KeInitializeSpinLock((PKSPIN_LOCK)(v6 + 1352));
  *(_DWORD *)(v6 + 1392) = 0;
  *(_DWORD *)(v6 + 1364) = 4000;
  *(_DWORD *)(v6 + 1496) = 4000;
  v19 = *(_QWORD *)v6;
  *(_QWORD *)(v6 + 1488) = DSMStateTable;
  *(_QWORD *)(v6 + 1480) = HUBSM_AddDsmEvent;
  *(_DWORD *)(v6 + 1464) = 0;
  *(_QWORD *)(v6 + 1472) = v6;
  *(_QWORD *)(v6 + 1544) = *(_QWORD *)(v19 + 248);
  *(_QWORD *)(v6 + 1512) = v19;
  *(_QWORD *)(v6 + 2608) = v6 + 2616;
  *(_DWORD *)(v6 + 2600) = 288;
  Timer = ExAllocateTimer(HUBMISC_DsmEventTimer, v6, 4);
  *(_QWORD *)(v6 + 1552) = Timer;
  if ( Timer )
  {
    v39 = 0;
    v36 = 0;
    v35 = 0;
    LODWORD(v35) = 56;
    v38 = 0;
    v37 = 0x100000001LL;
    v13 = (_QWORD *)(v6 + 2424);
    *(_QWORD *)&v38 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64 *))(WdfFunctions_01015 + 1632))(
                        WdfDriverGlobals,
                        a1);
    LODWORD(v37) = 2;
    v34 = 0;
    v33 = 0;
    LODWORD(v33) = 0;
    *((_QWORD *)&v32 + 1) = HUBPDO_EvtOutOfBandwidthTimer;
    *(_QWORD *)&v32 = 40;
    BYTE4(v33) = 1;
    DWORD2(v33) = 0;
    v14 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int128 *, __int64))(WdfFunctions_01015 + 2544))(
            WdfDriverGlobals,
            &v32,
            &v35,
            v6 + 2424);
    v5 = v14;
    if ( v14 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_16;
      v15 = 50;
      goto LABEL_15;
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, const char *, __int64, const char *))(WdfFunctions_01015 + 1640))(
      WdfDriverGlobals,
      *v13,
      "DSM Tag",
      7153,
      "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubmisc.c");
    KeInitializeEvent((PRKEVENT)(v6 + 1592), NotificationEvent, 0);
    KeInitializeEvent((PRKEVENT)(v6 + 1616), NotificationEvent, 0);
    KeInitializeEvent((PRKEVENT)(v6 + 480), NotificationEvent, 0);
    v22 = *(_QWORD *)v6;
    v23 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 248))(
            WdfDriverGlobals,
            *(_QWORD *)(*(_QWORD *)v6 + 16LL));
    v24 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(v22 + 504))(*(_QWORD *)(v22 + 248), v23, 1);
    *(_QWORD *)(v6 + 1504) = v24;
    if ( !v24 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v3) = 2;
        WPP_RECORDER_SF_(
          *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
          v3,
          5,
          51,
          (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids);
      }
      v5 = -1073741670;
      goto LABEL_33;
    }
    v39 = 0;
    v36 = 0;
    v37 = 0x100000001LL;
    v35 = 0;
    LODWORD(v35) = 56;
    v38 = 0;
    *(_QWORD *)&v38 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64 *))(WdfFunctions_01015 + 1632))(
                        WdfDriverGlobals,
                        a1);
    v25 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int64, __int64, __int64, __int64, _QWORD))(WdfFunctions_01015 + 1536))(
            WdfDriverGlobals,
            &v35,
            512,
            1681082453,
            96,
            v6 + 440,
            0);
    v5 = v25;
    if ( v25 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v31) = v25;
        LOBYTE(v3) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
          v3,
          5,
          52,
          (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids,
          v31);
      }
      goto LABEL_33;
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, const char *, __int64, const char *))(WdfFunctions_01015 + 1640))(
      WdfDriverGlobals,
      *(_QWORD *)(v6 + 440),
      "DSM Tag",
      7211,
      "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubmisc.c");
    KeInitializeSpinLock((PKSPIN_LOCK)(v6 + 40));
    a1[166] = v6;
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v21) = 2;
    WPP_RECORDER_SF_(
      *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
      v21,
      3,
      49,
      (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids);
  }
  if ( v7 >= 0 )
  {
    if ( g_IoSetActivityIdIrp )
    {
      g_IoSetActivityIdIrp(*(_QWORD *)(v6 + 272), v6 + 1524);
      if ( g_IoSetActivityIdIrp )
        g_IoSetActivityIdIrp(*(_QWORD *)(v6 + 432), v6 + 1524);
    }
    _InterlockedOr((volatile signed __int32 *)(v6 + 1644), 0x40u);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v21) = 4;
    WPP_RECORDER_SF_qq(
      *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
      v21,
      4,
      54,
      (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids,
      (char)a1,
      v6);
  }
  return 3013;
}

```

## disassembly

```asm
0x14002e514  push    rbp
0x14002e516  push    rbx
0x14002e517  push    rsi
0x14002e518  push    rdi
0x14002e519  push    r12
0x14002e51b  push    r13
0x14002e51d  push    r14
0x14002e51f  push    r15
0x14002e521  lea     rbp, [rsp-1Fh]
0x14002e526  sub     rsp, 0A8h
0x14002e52d  xor     eax, eax
0x14002e52f  xorps   xmm0, xmm0
0x14002e532  mov     dword ptr [rbp+57h+var_80], eax
0x14002e535  mov     r14, rcx
0x14002e538  mov     [rbp+57h+arg_8], rax
0x14002e53c  mov     rdx, rcx
0x14002e53f  mov     rcx, cs:WdfDriverGlobals
0x14002e546  lea     esi, [rax+38h]
0x14002e549  mov     rax, cs:off_14006B1A8
0x14002e550  movups  [rbp+57h+var_68], xmm0
0x14002e554  mov     [rbp+57h+var_48], rax
0x14002e558  mov     rax, cs:WdfFunctions_01015
0x14002e55f  movups  [rbp+57h+var_78], xmm0
0x14002e563  mov     dword ptr [rbp+57h+var_78], esi
0x14002e566  movups  [rbp+57h+var_A0], xmm0
0x14002e56a  mov     dword ptr [rbp+57h+var_68+8], 1
0x14002e571  movups  [rbp+57h+var_90], xmm0
0x14002e575  mov     dword ptr [rbp+57h+var_68+0Ch], 1
0x14002e57c  movups  [rbp+57h+var_58], xmm0
0x14002e580  mov     rax, [rax+660h]
0x14002e587  call    _guard_dispatch_icall
0x14002e58c  mov     rcx, cs:WdfDriverGlobals
0x14002e593  lea     r8, [rbp+57h+arg_8]
0x14002e597  mov     qword ptr [rbp+57h+var_58], rax
0x14002e59b  lea     rdx, [rbp+57h+var_78]
0x14002e59f  lea     rax, HUBMISC_EvtDsmDestroy
0x14002e5a6  mov     dword ptr [rbp+57h+var_68+8], 2
0x14002e5ad  mov     qword ptr [rbp+57h+var_68], rax
0x14002e5b1  mov     rax, cs:WdfFunctions_01015
0x14002e5b8  mov     rax, [rax+678h]
0x14002e5bf  call    _guard_dispatch_icall
0x14002e5c4  lea     r12, aOnecoreDrivers_4; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x14002e5cb  mov     ebx, eax
0x14002e5cd  lea     r15, WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids
0x14002e5d4  test    eax, eax
0x14002e5d6  jns     short loc_14002E612
0x14002e5d8  xor     edi, edi
0x14002e5da  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002e5e1  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002e5e8  jz      short loc_14002E609
0x14002e5ea  mov     rcx, [r14+598h]
0x14002e5f1  lea     r9d, [rdi+2Eh]
0x14002e5f5  mov     dword ptr [rsp+0E0h+var_B8], eax
0x14002e5f9  lea     r8d, [rdi+4]
0x14002e5fd  mov     dl, 2
0x14002e5ff  mov     [rsp+0E0h+var_C0], r15
0x14002e604  call    WPP_RECORDER_SF_d
0x14002e609  mov     [rbp+57h+arg_8], rdi
0x14002e60d  jmp     loc_14002ED51
0x14002e612  mov     rax, cs:WdfFunctions_01015
0x14002e619  mov     rdx, r14
0x14002e61c  mov     rcx, cs:WdfDriverGlobals
0x14002e623  mov     r13d, 0C0000001h
0x14002e629  mov     rax, [rax+660h]
0x14002e630  call    _guard_dispatch_icall
0x14002e635  mov     rcx, cs:WdfFunctions_01015
0x14002e63c  lea     r8, DsmCreateTag; "DSM Create Tag"
0x14002e643  mov     rdx, rax
0x14002e646  mov     [rsp+0E0h+var_C0], r12
0x14002e64b  mov     r9d, 1B32h
0x14002e651  mov     r10, [rcx+668h]
0x14002e658  mov     rcx, cs:WdfDriverGlobals
0x14002e65f  mov     rax, r10
0x14002e662  call    _guard_dispatch_icall
0x14002e667  mov     rax, cs:WdfFunctions_01015
0x14002e66e  mov     r8, cs:off_14006B1A8
0x14002e675  mov     rdx, [rbp+57h+arg_8]
0x14002e679  mov     rcx, cs:WdfDriverGlobals
0x14002e680  mov     rax, [rax+650h]
0x14002e687  call    _guard_dispatch_icall
0x14002e68c  xor     edx, edx; Val
0x14002e68e  mov     r8d, 0AB0h; Size
0x14002e694  mov     rcx, rax; void *
0x14002e697  mov     rdi, rax
0x14002e69a  call    memset
0x14002e69f  mov     rcx, cs:WdfFunctions_01015
0x14002e6a6  mov     r8, cs:off_14006B2C0
0x14002e6ad  mov     rax, [rcx+650h]
0x14002e6b4  mov     rcx, cs:WdfDriverGlobals
0x14002e6bb  mov     rdx, [rcx]
0x14002e6be  call    _guard_dispatch_icall
0x14002e6c3  lea     rbx, [rdi+5F4h]
0x14002e6ca  test    dword ptr [rax+4], 1000h
0x14002e6d1  jz      short loc_14002E6EA
0x14002e6d3  mov     rdx, rbx; ActivityId
0x14002e6d6  mov     ecx, 3; ControlCode
0x14002e6db  call    cs:__imp_EtwActivityIdControl
0x14002e6e2  nop     dword ptr [rax+rax+00h]
0x14002e6e7  mov     r13d, eax
0x14002e6ea  mov     [rdi+8], r14
0x14002e6ee  mov     rcx, [r14]
0x14002e6f1  mov     [rdi], rcx
0x14002e6f4  mov     word ptr [rdi+0AA0h], 0
0x14002e6fd  mov     dword ptr [rdi+0AA4h], 103h
0x14002e707  mov     dword ptr [rdi+0AA8h], 40000000h
0x14002e711  mov     ecx, [r14+0CCh]
0x14002e718  test    cl, 1
0x14002e71b  jz      short loc_14002E727
0x14002e71d  lock and dword ptr [rdi+668h], 0FFFFFFDFh
0x14002e725  jmp     short loc_14002E72F
0x14002e727  lock or dword ptr [rdi+668h], 20h
0x14002e72f  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, 40h
0x14002e736  jz      short loc_14002E75D
0x14002e738  mov     r9, [rdi]
0x14002e73b  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_ENUMERATION_START
0x14002e742  movzx   eax, word ptr [r14+0C8h]
0x14002e74a  mov     r8, rbx
0x14002e74d  mov     dword ptr [rsp+0E0h+var_C0], eax
0x14002e751  mov     r9, [r9+0F8h]
0x14002e758  call    McTemplateK0pq_EtwWriteTransfer
0x14002e75d  mov     rcx, cs:WdfDriverGlobals
0x14002e764  xor     eax, eax
0x14002e766  xorps   xmm0, xmm0
0x14002e769  mov     [rbp+57h+var_48], rax
0x14002e76d  mov     rax, cs:WdfFunctions_01015
0x14002e774  mov     rdx, r14
0x14002e777  movups  [rbp+57h+var_68], xmm0
0x14002e77b  mov     dword ptr [rbp+57h+var_68+8], 1
0x14002e782  movups  [rbp+57h+var_78], xmm0
0x14002e786  mov     dword ptr [rbp+57h+var_78], esi
0x14002e789  movups  [rbp+57h+var_58], xmm0
0x14002e78d  mov     dword ptr [rbp+57h+var_68+0Ch], 1
0x14002e794  mov     rax, [rax+660h]
0x14002e79b  call    _guard_dispatch_icall
0x14002e7a0  mov     rdx, [r14]
0x14002e7a3  mov     rcx, cs:WdfDriverGlobals
0x14002e7aa  mov     qword ptr [rbp+57h+var_58], rax
0x14002e7ae  mov     rax, cs:WdfFunctions_01015
0x14002e7b5  mov     rdx, [rdx+10h]
0x14002e7b9  mov     rax, [rax+150h]
0x14002e7c0  call    _guard_dispatch_icall
0x14002e7c5  mov     rcx, cs:WdfFunctions_01015
0x14002e7cc  lea     r12, [rdi+100h]
0x14002e7d3  mov     r8, rax
0x14002e7d6  lea     rdx, [rbp+57h+var_78]
0x14002e7da  mov     r9, r12
0x14002e7dd  mov     r10, [rcx+7B8h]
0x14002e7e4  mov     rcx, cs:WdfDriverGlobals
0x14002e7eb  mov     rax, r10
0x14002e7ee  call    _guard_dispatch_icall
0x14002e7f3  mov     ebx, eax
0x14002e7f5  test    eax, eax
0x14002e7f7  jns     short loc_14002E83D
0x14002e7f9  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002e800  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002e807  jz      short loc_14002E830
0x14002e809  mov     r9d, 2Fh ; '/'
0x14002e80f  mov     rcx, [rdi+8]
0x14002e813  mov     r8d, 5
0x14002e819  mov     dword ptr [rsp+0E0h+var_B8], eax
0x14002e81d  mov     dl, 2
0x14002e81f  mov     [rsp+0E0h+var_C0], r15
0x14002e824  mov     rcx, [rcx+598h]
0x14002e82b  call    WPP_RECORDER_SF_d
0x14002e830  mov     qword ptr [r12], 0
0x14002e838  jmp     loc_14002ED4A
0x14002e83d  mov     rax, cs:WdfFunctions_01015
0x14002e844  lea     rsi, aOnecoreDrivers_4; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x14002e84b  mov     rdx, [r12]
0x14002e84f  lea     r8, DsmTag; "DSM Tag"
0x14002e856  mov     rcx, cs:WdfDriverGlobals
0x14002e85d  mov     r9d, 1B6Eh
0x14002e863  mov     [rsp+0E0h+var_C0], rsi
0x14002e868  mov     rax, [rax+668h]
0x14002e86f  call    _guard_dispatch_icall
0x14002e874  mov     rax, cs:WdfFunctions_01015
0x14002e87b  mov     rdx, [r12]
0x14002e87f  mov     rcx, cs:WdfDriverGlobals
0x14002e886  mov     rax, [rax+8E8h]
0x14002e88d  call    _guard_dispatch_icall
0x14002e892  mov     [rdi+110h], rax
0x14002e899  xorps   xmm0, xmm0
0x14002e89c  mov     rcx, cs:WdfDriverGlobals
0x14002e8a3  xor     eax, eax
0x14002e8a5  mov     [rbp+57h+var_48], rax
0x14002e8a9  mov     rdx, r14
0x14002e8ac  movups  [rbp+57h+var_68], xmm0
0x14002e8b0  mov     eax, 1
0x14002e8b5  mov     dword ptr [rbp+57h+var_68+8], eax
0x14002e8b8  mov     dword ptr [rbp+57h+var_68+0Ch], eax
0x14002e8bb  mov     rax, cs:WdfFunctions_01015
0x14002e8c2  movups  [rbp+57h+var_78], xmm0
0x14002e8c6  mov     dword ptr [rbp+57h+var_78], 38h ; '8'
0x14002e8cd  movups  [rbp+57h+var_58], xmm0
0x14002e8d1  mov     rax, [rax+660h]
0x14002e8d8  call    _guard_dispatch_icall
0x14002e8dd  mov     rdx, [r14]
0x14002e8e0  mov     rcx, cs:WdfDriverGlobals
0x14002e8e7  mov     qword ptr [rbp+57h+var_58], rax
0x14002e8eb  mov     rax, cs:WdfFunctions_01015
0x14002e8f2  mov     rdx, [rdx+10h]
0x14002e8f6  mov     rax, [rax+150h]
0x14002e8fd  call    _guard_dispatch_icall
0x14002e902  mov     rcx, cs:WdfFunctions_01015
0x14002e909  lea     r12, [rdi+1A8h]
0x14002e910  mov     r8, rax
0x14002e913  lea     rdx, [rbp+57h+var_78]
0x14002e917  mov     r9, r12
0x14002e91a  mov     r10, [rcx+7B8h]
0x14002e921  mov     rcx, cs:WdfDriverGlobals
0x14002e928  mov     rax, r10
0x14002e92b  call    _guard_dispatch_icall
0x14002e930  mov     ebx, eax
0x14002e932  test    eax, eax
0x14002e934  jns     short loc_14002E955
0x14002e936  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002e93d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002e944  jz      loc_14002E830
0x14002e94a  mov     r9d, 30h ; '0'
0x14002e950  jmp     loc_14002E80F
0x14002e955  mov     rax, cs:WdfFunctions_01015
0x14002e95c  lea     r8, DsmTag; "DSM Tag"
0x14002e963  mov     rdx, [r12]
0x14002e967  mov     r9d, 1B92h
0x14002e96d  mov     rcx, cs:WdfDriverGlobals
0x14002e974  mov     [rsp+0E0h+var_C0], rsi
0x14002e979  mov     rax, [rax+668h]
0x14002e980  call    _guard_dispatch_icall
0x14002e985  mov     rax, cs:WdfFunctions_01015
0x14002e98c  mov     rdx, [r12]
0x14002e990  mov     rcx, cs:WdfDriverGlobals
0x14002e997  mov     rax, [rax+8E8h]
0x14002e99e  call    _guard_dispatch_icall
0x14002e9a3  lea     rcx, [rdi+548h]; SpinLock
0x14002e9aa  mov     [rdi+1B0h], rax
0x14002e9b1  mov     word ptr [rdi+800h], 409h
0x14002e9ba  call    cs:__imp_KeInitializeSpinLock
0x14002e9c1  nop     dword ptr [rax+rax+00h]
0x14002e9c6  mov     ecx, 0FA0h
0x14002e9cb  mov     dword ptr [rdi+570h], 0
0x14002e9d5  mov     [rdi+554h], ecx
0x14002e9db  lea     rax, DSMStateTable
0x14002e9e2  mov     [rdi+5D8h], ecx
0x14002e9e8  mov     r8d, 4
0x14002e9ee  mov     rcx, [rdi]
0x14002e9f1  mov     rdx, rdi
0x14002e9f4  mov     [rdi+5D0h], rax
0x14002e9fb  lea     rax, HUBSM_AddDsmEvent
0x14002ea02  mov     [rdi+5C8h], rax
0x14002ea09  mov     dword ptr [rdi+5B8h], 0
0x14002ea13  mov     [rdi+5C0h], rdi
0x14002ea1a  mov     rax, [rcx+0F8h]
0x14002ea21  mov     [rdi+608h], rax
0x14002ea28  lea     rax, [rdi+0A38h]
0x14002ea2f  mov     [rdi+5E8h], rcx
0x14002ea36  lea     rcx, HUBMISC_DsmEventTimer
0x14002ea3d  mov     [rdi+0A30h], rax
0x14002ea44  mov     dword ptr [rdi+0A28h], 120h
0x14002ea4e  call    cs:__imp_ExAllocateTimer
0x14002ea55  nop     dword ptr [rax+rax+00h]
0x14002ea5a  mov     [rdi+610h], rax
0x14002ea61  lea     r15, WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids
0x14002ea68  lea     rsi, WPP_RECORDER_INITIALIZED
0x14002ea6f  test    rax, rax
0x14002ea72  jnz     short loc_14002EAA5
0x14002ea74  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14002ea7b  jz      loc_14002F011
0x14002ea81  mov     rcx, [rdi+8]
0x14002ea85  lea     r9d, [rax+31h]
0x14002ea89  lea     r8d, [rax+3]
0x14002ea8d  mov     [rsp+0E0h+var_C0], r15
0x14002ea92  mov     dl, 2
0x14002ea94  mov     rcx, [rcx+598h]
0x14002ea9b  call    WPP_RECORDER_SF_
0x14002eaa0  jmp     loc_14002F011
0x14002eaa5  mov     rcx, cs:WdfDriverGlobals
0x14002eaac  xor     eax, eax
0x14002eaae  xorps   xmm0, xmm0
0x14002eab1  mov     [rbp+57h+var_48], rax
0x14002eab5  movups  [rbp+57h+var_68], xmm0
0x14002eab9  mov     rdx, r14
0x14002eabc  lea     ebx, [rax+1]
0x14002eabf  mov     rax, cs:WdfFunctions_01015
0x14002eac6  movups  [rbp+57h+var_78], xmm0
0x14002eaca  mov     dword ptr [rbp+57h+var_78], 38h ; '8'
0x14002ead1  movups  [rbp+57h+var_58], xmm0
0x14002ead5  mov     dword ptr [rbp+57h+var_68+8], ebx
0x14002ead8  mov     dword ptr [rbp+57h+var_68+0Ch], ebx
0x14002eadb  mov     rax, [rax+660h]
0x14002eae2  call    _guard_dispatch_icall
0x14002eae7  mov     rcx, cs:WdfDriverGlobals
0x14002eaee  lea     r12, [rdi+978h]
0x14002eaf5  mov     qword ptr [rbp+57h+var_58], rax
0x14002eaf9  lea     r8, [rbp+57h+var_78]
0x14002eafd  xor     eax, eax
0x14002eaff  mov     dword ptr [rbp+57h+var_68+8], 2
0x14002eb06  mov     [rbp+57h+var_80], rax
0x14002eb0a  lea     rdx, [rbp+57h+var_A0]
0x14002eb0e  xorps   xmm0, xmm0
0x14002eb11  lea     rax, HUBPDO_EvtOutOfBandwidthTimer
  ... truncated ...
```
