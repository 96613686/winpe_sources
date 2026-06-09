# WinUSB_SubmitIsochRequests

- ea: `0x14000eff0`
- end: `0x14000fbe1`
- name: `WinUSB_SubmitIsochRequests`
- size: `3057`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000c948`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x1400014bc`
- `0x14000193c`
- `0x140001c30`
- `0x14000bd48`
- `0x14000be88`
- `0x14000c17c`
- `0x14000d5b8`
- `0x14000ea0c`
- `0x14000eff0`
- `0x14000fbe8`
- `0x1400106c0`
- `0x140010700`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f0d9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f6ce`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f0d9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f6ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f130`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f18a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f71e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f783`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f130`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f18a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f71e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f783`

## pseudocode

```c
void __fastcall WinUSB_SubmitIsochRequests(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  __int64 v3; // r14
  bool v4; // cc
  unsigned int v5; // esi
  KIRQL v6; // al
  __int64 v7; // rdx
  KIRQL v8; // bl
  int v9; // ebx
  int v10; // eax
  int v11; // edx
  int v12; // r8d
  int v13; // edx
  __int64 v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // r12d
  unsigned int v17; // r15d
  int v18; // ecx
  char v19; // al
  unsigned int v20; // ecx
  unsigned int v21; // esi
  int v22; // eax
  int v23; // edx
  int v24; // r9d
  __int64 v25; // rcx
  int v26; // edx
  int v27; // ebx
  __int64 v28; // r8
  int v29; // eax
  int v30; // edx
  unsigned int v31; // esi
  int IsochChildRequests; // eax
  int v33; // edx
  int v34; // ebx
  KIRQL v35; // si
  int v36; // eax
  int v37; // edx
  unsigned int v38; // r14d
  int v39; // eax
  int v40; // edx
  unsigned int v41; // esi
  int v42; // eax
  int v43; // r9d
  __int64 *v44; // [rsp+20h] [rbp-E0h]
  char v45; // [rsp+28h] [rbp-D8h]
  char v46; // [rsp+28h] [rbp-D8h]
  char v47; // [rsp+30h] [rbp-D0h]
  char v48; // [rsp+38h] [rbp-C8h]
  __int64 v49; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v50; // [rsp+58h] [rbp-A8h]
  __int64 v51; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v52; // [rsp+68h] [rbp-98h] BYREF
  int v53; // [rsp+70h] [rbp-90h] BYREF
  __int64 v54; // [rsp+78h] [rbp-88h] BYREF
  __int64 v55; // [rsp+80h] [rbp-80h] BYREF
  __int64 v56; // [rsp+88h] [rbp-78h] BYREF
  __int128 v57; // [rsp+90h] [rbp-70h] BYREF
  __int128 v58; // [rsp+A0h] [rbp-60h]
  __int128 v59; // [rsp+B0h] [rbp-50h]
  __int64 *v60; // [rsp+C0h] [rbp-40h]
  __int64 v61; // [rsp+C8h] [rbp-38h]
  _BYTE v62[20]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v63; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v64; // [rsp+F8h] [rbp-8h]
  __int64 v65; // [rsp+108h] [rbp+8h]

  v61 = a1;
  v52 = 0;
  v56 = 0;
  LODWORD(v60) = 0;
  v2 = a2;
  v3 = a1;
  v65 = 0;
  v57 = 0;
  v49 = 0;
  v58 = 0;
  v54 = 0;
  v59 = 0;
  v55 = 0;
  memset(v62, 0, sizeof(v62));
  v53 = 0;
  v63 = 0;
  v64 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      91,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
  }
  v4 = *(_DWORD *)(v2 + 200) < 200;
  v5 = 0;
  v52 = 0;
  v49 = 0;
  v54 = 0;
  v55 = 0;
  if ( !v4 )
    goto LABEL_86;
  while ( 1 )
  {
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 232));
    v7 = *(_QWORD *)(v2 + 224);
    v8 = v6;
    if ( !v7 )
      break;
    v49 = *(_QWORD *)(v2 + 224);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015 + 1640))(
      WdfDriverGlobals,
      v7,
      0,
      2011,
      "onecore\\drivers\\wdm\\usb\\driver\\winusb\\sys\\isoch.c");
    KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 232), v8);
    WinUSB_SubmitChildIsochTransfer(v49, v3, v2);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015 + 1648))(
      WdfDriverGlobals,
      v49,
      0,
      2020,
      "onecore\\drivers\\wdm\\usb\\driver\\winusb\\sys\\isoch.c");
LABEL_56:
    if ( *(int *)(v2 + 200) >= 200 )
      goto LABEL_86;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 232), v6);
  v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01015 + 1264))(
         WdfDriverGlobals,
         *(_QWORD *)(v2 + 192),
         &v49);
  if ( v9 < 0 )
    goto LABEL_86;
  v50 = ++v5;
  if ( v5 <= 0x12C )
  {
    v44 = &v56;
    v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64 *))(WdfFunctions_01015 + 2152))(
            WdfDriverGlobals,
            v49,
            40,
            &v52);
    v9 = v10;
    if ( v10 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_83;
      v48 = v10;
      v43 = 93;
      v47 = v56;
      v46 = 40;
      goto LABEL_92;
    }
    v65 = 0;
    v63 = 0;
    LOWORD(v63) = 40;
    v64 = 0;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01015 + 2128))(
      WdfDriverGlobals,
      v49,
      &v63);
    if ( DWORD2(v64) == 55574650 )
    {
      v14 = *(unsigned int *)(v52 + 32);
      if ( (unsigned int)v14 > 0x15555555 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v13) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v13,
            3,
            94,
            (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
            v14);
        }
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2104))(
          WdfDriverGlobals,
          v49,
          3221225485LL);
        goto LABEL_56;
      }
      v44 = &v55;
      v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64 *))(WdfFunctions_01015 + 2160))(
             WdfDriverGlobals,
             v49,
             12 * v14,
             &v54);
      if ( v9 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_83;
        v43 = 95;
        v48 = v9;
        v47 = v56;
        v12 = 12 * *(_DWORD *)(v52 + 32);
        v46 = v12;
LABEL_92:
        LOBYTE(v11) = 2;
        WPP_RECORDER_SF_did(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          v12,
          v43,
          (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
          v46,
          v47,
          v48);
        goto LABEL_83;
      }
    }
    v15 = *(_QWORD *)(v2 + 160);
    v16 = *(_DWORD *)(v52 + 20);
    *(_OWORD *)&v62[4] = 0;
    *(_DWORD *)v62 = 20;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _BYTE *))(WdfFunctions_01015 + 2728))(
      WdfDriverGlobals,
      v15,
      v62);
    v17 = v16 / *(_DWORD *)(v2 + 168) + 1;
    if ( !(v16 % *(_DWORD *)(v2 + 168)) )
      v17 = v16 / *(_DWORD *)(v2 + 168);
    if ( (*(_DWORD *)(v3 + 32) & 4) != 0 )
    {
      switch ( v62[9] )
      {
        case 1:
          v18 = 1;
          break;
        case 2:
          v18 = 2;
          break;
        case 3:
          v18 = 4;
          break;
        default:
          v18 = 8;
          break;
      }
      v19 = v18 * v17;
      v20 = (v18 * v17) >> 3;
      v21 = v20 + 1;
      if ( (v19 & 7) == 0 )
        v21 = v20;
    }
    else
    {
      v21 = v17;
    }
    v22 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, int *))(WdfFunctions_01015 + 2656))(
            WdfDriverGlobals,
            *(_QWORD *)(v3 + 8),
            &v53);
    v9 = v22;
    if ( v22 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v23) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v23,
          3,
          96,
          (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
          v22);
      }
      goto LABEL_83;
    }
    v25 = v52;
    v26 = v53;
    if ( *(_BYTE *)(v52 + 24) == 1 )
    {
      v27 = *(_DWORD *)(v2 + 204);
      if ( *(_BYTE *)(v52 + 25) != 1 )
      {
        if ( (unsigned int)(v53 - v27 - 1) >= 0x7FFFFFFF )
          v27 += 5;
        else
          v27 = v53 + 5;
      }
    }
    else
    {
      v27 = *(_DWORD *)(v52 + 28);
    }
    *(_DWORD *)(v2 + 204) = v21 + v27;
    if ( (unsigned int)(v26 - v27 - 1) >= 0x7FFFFFFF )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qlldd(
          WPP_GLOBAL_Control->DeviceExtension,
          v26,
          1,
          v24,
          (_DWORD)v44,
          v49,
          *(_BYTE *)(v25 + 24),
          *(_BYTE *)(v25 + 25),
          v26,
          v27);
      v51 = 0;
      *(_QWORD *)&v58 = 0;
      *((_QWORD *)&v58 + 1) = 0x100000001LL;
      v57 = 0;
      LODWORD(v57) = 56;
      v59 = 0;
      if ( v21 <= 0x32 )
      {
        v60 = off_140015068;
        v36 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *, __int64 *))(WdfFunctions_01015 + 1624))(
                WdfDriverGlobals,
                v49,
                &v57,
                &v51);
        v38 = v36;
        if ( v36 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v37) = 2;
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v37,
              3,
              103,
              (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
              v36);
          }
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2104))(
            WdfDriverGlobals,
            v49,
            v38);
          v3 = v61;
          goto LABEL_55;
        }
        v3 = v61;
        *(_QWORD *)(v51 + 24) = *(_QWORD *)(v52 + 8);
        *(_DWORD *)(v51 + 108) = *(_DWORD *)(v52 + 16);
        *(_QWORD *)(v51 + 80) = v54;
        *(_QWORD *)(v51 + 88) = v55;
        *(_DWORD *)(v51 + 120) = v16;
        *(_QWORD *)v51 = v2;
        *(_DWORD *)(v51 + 40) = v21;
        v39 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, _QWORD, __int64, _QWORD))(WdfFunctions_01015 + 3392))(
                WdfDriverGlobals,
                *(_QWORD *)(v3 + 8),
                0,
                v17,
                v51 + 8,
                0);
        v41 = v39;
        if ( v39 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v40) = 2;
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v40,
              3,
              104,
              (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
              v39);
          }
          v28 = v41;
          goto LABEL_41;
        }
        v42 = WinUSB_SubmitIsochTransfer(v49, v17, v27, *(_QWORD *)(v51 + 8), (__int64)WinUSB_IsochTransferComplete);
        v34 = v42;
        if ( v42 >= 0 )
          goto LABEL_55;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a2) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            a2,
            3,
            105,
            (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
            v42);
        }
      }
      else
      {
        v60 = off_1400150C0;
        v29 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *, __int64 *))(WdfFunctions_01015 + 1624))(
                WdfDriverGlobals,
                v49,
                &v57,
                &v51);
        v31 = v29;
        if ( v29 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v30) = 2;
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v30,
              3,
              99,
              (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
              v29);
          }
          v28 = v31;
          goto LABEL_41;
        }
        *(_QWORD *)(v51 + 8) = *(_QWORD *)(v52 + 8);
        *(_DWORD *)(v51 + 44) = *(_DWORD *)(v52 + 16);
        *(_QWORD *)(v51 + 24) = v54;
        *(_QWORD *)(v51 + 32) = v55;
        *(_DWORD *)(v51 + 72) = v27;
        WinUSB_InitializeParentRequest(v3, v49, v16, v2, (__int64)v62, v17);
        IsochChildRequests = WinUSB_AllocateIsochChildRequests(v49, v3, v2, *(unsigned int *)(v51 + 64));
        v34 = IsochChildRequests;
        if ( IsochChildRequests >= 0 )
        {
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015 + 1640))(
            WdfDriverGlobals,
            v49,
            0,
            2267,
            "onecore\\drivers\\wdm\\usb\\driver\\winusb\\sys\\isoch.c");
          WinUSB_SubmitChildIsochTransfer(v49, v3, v2);
          v35 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 232));
          if ( *(_BYTE *)(v51 + 137) == 1 )
          {
            (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015
                                                                                                + 1648))(
              WdfDriverGlobals,
              v49,
              0,
              2277,
              "onecore\\drivers\\wdm\\usb\\driver\\winusb\\sys\\isoch.c");
            KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 232), v35);
            goto LABEL_55;
          }
          v34 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 (__fastcall *)()))(WdfFunctions_01015
                                                                                                  + 3144))(
                  WdfDriverGlobals,
                  v49,
                  WinUSB_ParentIsochRequestCancel);
          if ( v34 >= 0 )
            *(_BYTE *)(v51 + 138) = 1;
          KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 232), v35);
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015 + 1648))(
            WdfDriverGlobals,
            v49,
            0,
            2292,
            "onecore\\drivers\\wdm\\usb\\driver\\winusb\\sys\\isoch.c");
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(a2) = 4;
            WPP_RECORDER_SF_qd(
              WPP_GLOBAL_Control->DeviceExtension,
              a2,
              3,
              101,
              (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
              v49,
              v34);
          }
          if ( v34 >= 0 )
            goto LABEL_55;
          if ( v34 != -1073741536 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(a2) = 2;
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              a2,
              3,
              102,
              (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
              v34);
          }
          if ( (unsigned __int8)WinUSB_CancelChildRequests(v49) != 1 )
            goto LABEL_55;
        }
        else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v33) = 2;
          WPP_RECORDER_SF_qd(
            WPP_GLOBAL_Control->DeviceExtension,
            v33,
            3,
            100,
            (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
            v49,
            IsochChildRequests);
        }
      }
      v28 = (unsigned int)v34;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v45 = v26;
        LOBYTE(v26) = 2;
        WPP_RECORDER_SF_dD(
          WPP_GLOBAL_Control->DeviceExtension,
          v26,
          3,
          97,
          (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
          v45,
          v27);
      }
      v28 = 3221225485LL;
    }
LABEL_41:
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2104))(
      WdfDriverGlobals,
      v49,
      v28);
LABEL_55:
    v5 = v50;
    goto LABEL_56;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      92,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
  }
LABEL_83:
  if ( v49 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2104))(
      WdfDriverGlobals,
      v49,
      (unsigned int)v9);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 (__fastcall *)(), _QWORD))(WdfFunctions_01015 + 1320))(
    WdfDriverGlobals,
    *(_QWORD *)(v2 + 192),
    WinUSB_IsochPurgeComplete,
    0);
LABEL_86:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        106,
        (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x14000eff0  mov     [rsp-8+arg_10], rbx
0x14000eff5  push    rbp
0x14000eff6  push    rsi
0x14000eff7  push    rdi
0x14000eff8  push    r12
0x14000effa  push    r13
0x14000effc  push    r14
0x14000effe  push    r15
0x14000f000  lea     rbp, [rsp-20h]
0x14000f005  sub     rsp, 120h
0x14000f00c  mov     rax, cs:__security_cookie
0x14000f013  xor     rax, rsp
0x14000f016  mov     [rbp+50h+var_40], rax
0x14000f01a  xor     r12d, r12d
0x14000f01d  mov     [rbp+50h+var_88], rcx
0x14000f021  xorps   xmm0, xmm0
0x14000f024  mov     [rsp+150h+var_E8], r12
0x14000f029  xor     eax, eax
0x14000f02b  mov     [rbp+50h+var_C8], r12
0x14000f02f  mov     dword ptr [rbp+50h+var_90], eax
0x14000f032  mov     rdi, rdx
0x14000f035  mov     [rbp+50h+var_70], eax
0x14000f038  mov     r14, rcx
0x14000f03b  mov     [rbp+50h+var_48], rax
0x14000f03f  movups  [rbp+50h+var_C0], xmm0
0x14000f043  mov     [rsp+150h+var_100], r12
0x14000f048  movups  [rbp+50h+var_B0], xmm0
0x14000f04c  mov     [rsp+150h+var_D8], r12
0x14000f051  movups  [rbp+50h+var_A0], xmm0
0x14000f055  mov     [rbp+50h+var_D0], r12
0x14000f059  movups  [rbp+50h+var_80], xmm0
0x14000f05d  mov     [rsp+150h+var_E0], r12d
0x14000f062  movups  [rbp+50h+var_68], xmm0
0x14000f066  movups  [rbp+50h+var_58], xmm0
0x14000f06a  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000f071  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000f078  lea     rbx, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000f07f  jz      short loc_14000F0A9
0x14000f081  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f088  cmp     [rcx+48h], r12w
0x14000f08d  jz      short loc_14000F0A9
0x14000f08f  mov     rcx, [rcx+40h]
0x14000f093  lea     r9d, [r12+5Bh]
0x14000f098  lea     r8d, [r12+1]
0x14000f09d  mov     [rsp+150h+var_130], rbx
0x14000f0a2  mov     dl, 5
0x14000f0a4  call    WPP_RECORDER_SF_
0x14000f0a9  cmp     dword ptr [rdi+0C8h], 0C8h
0x14000f0b3  mov     esi, r12d
0x14000f0b6  mov     [rsp+150h+var_E8], r12
0x14000f0bb  mov     [rsp+150h+var_100], r12
0x14000f0c0  mov     [rsp+150h+var_D8], r12
0x14000f0c5  mov     [rbp+50h+var_D0], r12
0x14000f0c9  jge     loc_14000FB03
0x14000f0cf  lea     r13, [rdi+0E8h]
0x14000f0d6  mov     rcx, r13; SpinLock
0x14000f0d9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f0e0  nop     dword ptr [rax+rax+00h]
0x14000f0e5  mov     rdx, [rdi+0E0h]
0x14000f0ec  mov     bl, al
0x14000f0ee  test    rdx, rdx
0x14000f0f1  jz      loc_14000F185
0x14000f0f7  mov     rcx, cs:WdfFunctions_01015
0x14000f0fe  mov     r9d, 7DBh
0x14000f104  mov     [rsp+150h+var_100], rdx
0x14000f109  xor     r8d, r8d
0x14000f10c  mov     rax, [rcx+668h]
0x14000f113  lea     rcx, aOnecoreDrivers_1
0x14000f11a  mov     [rsp+150h+var_130], rcx
0x14000f11f  mov     rcx, cs:WdfDriverGlobals
0x14000f126  call    _guard_dispatch_icall
0x14000f12b  mov     dl, bl; NewIrql
0x14000f12d  mov     rcx, r13; SpinLock
0x14000f130  call    cs:__imp_KeReleaseSpinLock
0x14000f137  nop     dword ptr [rax+rax+00h]
0x14000f13c  mov     rcx, [rsp+150h+var_100]
0x14000f141  mov     r8, rdi
0x14000f144  mov     rdx, r14
0x14000f147  call    WinUSB_SubmitChildIsochTransfer
0x14000f14c  mov     rax, cs:WdfFunctions_01015
0x14000f153  lea     rcx, aOnecoreDrivers_1
0x14000f15a  mov     rdx, [rsp+150h+var_100]
0x14000f15f  mov     r9d, 7E4h
0x14000f165  mov     [rsp+150h+var_130], rcx
0x14000f16a  xor     r8d, r8d
0x14000f16d  mov     rcx, cs:WdfDriverGlobals
0x14000f174  mov     rax, [rax+670h]
0x14000f17b  call    _guard_dispatch_icall
0x14000f180  jmp     loc_14000F735
0x14000f185  mov     dl, bl; NewIrql
0x14000f187  mov     rcx, r13; SpinLock
0x14000f18a  call    cs:__imp_KeReleaseSpinLock
0x14000f191  nop     dword ptr [rax+rax+00h]
0x14000f196  mov     rax, cs:WdfFunctions_01015
0x14000f19d  lea     r8, [rsp+150h+var_100]
0x14000f1a2  mov     rdx, [rdi+0C0h]
0x14000f1a9  mov     rcx, cs:WdfDriverGlobals
0x14000f1b0  mov     rax, [rax+4F0h]
0x14000f1b7  call    _guard_dispatch_icall
0x14000f1bc  mov     ebx, eax
0x14000f1be  test    eax, eax
0x14000f1c0  js      loc_14000FAFC
0x14000f1c6  inc     esi
0x14000f1c8  mov     [rsp+150h+var_F8], esi
0x14000f1cc  cmp     esi, 12Ch
0x14000f1d2  ja      loc_14000FBA7
0x14000f1d8  mov     rax, cs:WdfFunctions_01015
0x14000f1df  lea     rcx, [rbp+50h+var_C8]
0x14000f1e3  mov     rdx, [rsp+150h+var_100]
0x14000f1e8  lea     r9, [rsp+150h+var_E8]
0x14000f1ed  mov     [rsp+150h+var_130], rcx
0x14000f1f2  mov     r8d, 28h ; '('
0x14000f1f8  mov     rcx, cs:WdfDriverGlobals
0x14000f1ff  mov     rax, [rax+868h]
0x14000f206  call    _guard_dispatch_icall
0x14000f20b  mov     ebx, eax
0x14000f20d  test    eax, eax
0x14000f20f  js      loc_14000FB5C
0x14000f215  mov     rdx, [rsp+150h+var_100]
0x14000f21a  lea     r8, [rbp+50h+var_68]
0x14000f21e  mov     rcx, cs:WdfDriverGlobals
0x14000f225  xor     eax, eax
0x14000f227  mov     [rbp+50h+var_48], rax
0x14000f22b  xorps   xmm0, xmm0
0x14000f22e  movups  [rbp+50h+var_68], xmm0
0x14000f232  mov     eax, 28h ; '('
0x14000f237  mov     word ptr [rbp+50h+var_68], ax
0x14000f23b  mov     rax, cs:WdfFunctions_01015
0x14000f242  movups  [rbp+50h+var_58], xmm0
0x14000f246  mov     rax, [rax+850h]
0x14000f24d  call    _guard_dispatch_icall
0x14000f252  cmp     dword ptr [rbp+50h+var_58+8], 350007Ah
0x14000f259  jnz     loc_14000F30D
0x14000f25f  mov     rax, [rsp+150h+var_E8]
0x14000f264  mov     ecx, [rax+20h]
0x14000f267  cmp     ecx, 15555555h
0x14000f26d  jbe     short loc_14000F2CE
0x14000f26f  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14000f276  jz      short loc_14000F2A4
0x14000f278  mov     dword ptr [rsp+150h+var_128], ecx
0x14000f27c  lea     rax, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000f283  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f28a  mov     r9d, 5Eh ; '^'
0x14000f290  mov     dl, 2
0x14000f292  mov     [rsp+150h+var_130], rax
0x14000f297  mov     rcx, [rcx+40h]
0x14000f29b  lea     r8d, [r9-5Bh]
0x14000f29f  call    WPP_RECORDER_SF_d
0x14000f2a4  mov     rax, cs:WdfFunctions_01015
0x14000f2ab  mov     r8d, 0C000000Dh
0x14000f2b1  mov     rdx, [rsp+150h+var_100]
0x14000f2b6  mov     rcx, cs:WdfDriverGlobals
0x14000f2bd  mov     rax, [rax+838h]
0x14000f2c4  call    _guard_dispatch_icall
0x14000f2c9  jmp     loc_14000F735
0x14000f2ce  mov     rax, cs:WdfFunctions_01015
0x14000f2d5  lea     r8, [rcx+rcx*2]
0x14000f2d9  mov     rdx, [rsp+150h+var_100]
0x14000f2de  lea     rcx, [rbp+50h+var_D0]
0x14000f2e2  mov     [rsp+150h+var_130], rcx
0x14000f2e7  lea     r9, [rsp+150h+var_D8]
0x14000f2ec  mov     rcx, cs:WdfDriverGlobals
0x14000f2f3  mov     rax, [rax+870h]
0x14000f2fa  shl     r8, 2
0x14000f2fe  call    _guard_dispatch_icall
0x14000f303  mov     ebx, eax
0x14000f305  test    eax, eax
0x14000f307  js      loc_14000FA35
0x14000f30d  mov     rax, [rsp+150h+var_E8]
0x14000f312  lea     r8, [rbp+50h+var_80]
0x14000f316  mov     rdx, [rdi+0A0h]
0x14000f31d  xorps   xmm0, xmm0
0x14000f320  mov     rcx, cs:WdfDriverGlobals
0x14000f327  mov     r12d, [rax+14h]
0x14000f32b  mov     rax, cs:WdfFunctions_01015
0x14000f332  movdqu  [rbp+50h+var_80+4], xmm0
0x14000f337  mov     dword ptr [rbp+50h+var_80], 14h
0x14000f33e  mov     rax, [rax+0AA8h]
0x14000f345  call    _guard_dispatch_icall
0x14000f34a  xor     edx, edx
0x14000f34c  mov     eax, r12d
0x14000f34f  div     dword ptr [rdi+0A8h]
0x14000f355  test    edx, edx
0x14000f357  lea     r15d, [rax+1]
0x14000f35b  cmovz   r15d, eax
0x14000f35f  mov     eax, [r14+20h]
0x14000f363  test    al, 4
0x14000f365  jz      short loc_14000F3AC
0x14000f367  movzx   ecx, byte ptr [rbp+50h+var_80+9]
0x14000f36b  sub     ecx, 1
0x14000f36e  jz      short loc_14000F392
0x14000f370  sub     ecx, 1
0x14000f373  jz      short loc_14000F38B
0x14000f375  sub     ecx, 1
0x14000f378  jz      short loc_14000F384
0x14000f37a  cmp     ecx, 1
0x14000f37d  mov     ecx, 8
0x14000f382  jmp     short loc_14000F397
0x14000f384  mov     ecx, 4
0x14000f389  jmp     short loc_14000F397
0x14000f38b  mov     ecx, 2
0x14000f390  jmp     short loc_14000F397
0x14000f392  mov     ecx, 1
0x14000f397  mov     eax, r15d
0x14000f39a  imul    eax, ecx
0x14000f39d  mov     ecx, eax
0x14000f39f  shr     ecx, 3
0x14000f3a2  test    al, 7
0x14000f3a4  lea     esi, [rcx+1]
0x14000f3a7  cmovz   esi, ecx
0x14000f3aa  jmp     short loc_14000F3AF
0x14000f3ac  mov     esi, r15d
0x14000f3af  mov     rax, cs:WdfFunctions_01015
0x14000f3b6  lea     r8, [rsp+150h+var_E0]
0x14000f3bb  mov     rdx, [r14+8]
0x14000f3bf  mov     rcx, cs:WdfDriverGlobals
0x14000f3c6  mov     rax, [rax+0A60h]
0x14000f3cd  call    _guard_dispatch_icall
0x14000f3d2  mov     ebx, eax
0x14000f3d4  test    eax, eax
0x14000f3d6  js      loc_14000FA6B
0x14000f3dc  mov     rcx, [rsp+150h+var_E8]
0x14000f3e1  mov     r8d, 1
0x14000f3e7  mov     edx, [rsp+150h+var_E0]
0x14000f3eb  cmp     [rcx+18h], r8b
0x14000f3ef  jnz     short loc_14000F415
0x14000f3f1  mov     ebx, [rdi+0CCh]
0x14000f3f7  cmp     [rcx+19h], r8b
0x14000f3fb  jz      short loc_14000F418
0x14000f3fd  mov     eax, edx
0x14000f3ff  sub     eax, ebx
0x14000f401  sub     eax, r8d
0x14000f404  cmp     eax, 7FFFFFFFh
0x14000f409  jnb     short loc_14000F410
0x14000f40b  lea     ebx, [rdx+5]
0x14000f40e  jmp     short loc_14000F418
0x14000f410  add     ebx, 5
0x14000f413  jmp     short loc_14000F418
0x14000f415  mov     ebx, [rcx+1Ch]
0x14000f418  mov     eax, ebx
0x14000f41a  add     eax, esi
0x14000f41c  mov     [rdi+0CCh], eax
0x14000f422  mov     eax, edx
0x14000f424  sub     eax, ebx
0x14000f426  sub     eax, r8d
0x14000f429  cmp     eax, 7FFFFFFFh
0x14000f42e  jnb     short loc_14000F49D
0x14000f430  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000f437  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000f43e  jz      short loc_14000F470
0x14000f440  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f447  lea     rax, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000f44e  mov     r9d, 61h ; 'a'
0x14000f454  mov     dword ptr [rsp+150h+var_120], ebx
0x14000f458  mov     dword ptr [rsp+150h+var_128], edx
0x14000f45c  mov     dl, 2
0x14000f45e  mov     [rsp+150h+var_130], rax
0x14000f463  mov     rcx, [rcx+40h]
0x14000f467  lea     r8d, [r9-5Eh]
0x14000f46b  call    WPP_RECORDER_SF_dD
0x14000f470  mov     r8d, 0C000000Dh
0x14000f476  mov     rax, cs:WdfFunctions_01015
0x14000f47d  mov     rdx, [rsp+150h+var_100]
0x14000f482  mov     rcx, cs:WdfDriverGlobals
0x14000f489  mov     rax, [rax+838h]
0x14000f490  call    _guard_dispatch_icall
0x14000f495  xor     r12d, r12d
0x14000f498  jmp     loc_14000F731
0x14000f49d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000f4a4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000f4ab  jz      short loc_14000F4E5
0x14000f4ad  movzx   eax, byte ptr [rcx+19h]
0x14000f4b1  movzx   ecx, byte ptr [rcx+18h]
0x14000f4b5  mov     [rsp+150h+var_108], ebx
0x14000f4b9  mov     [rsp+150h+var_110], edx
0x14000f4bd  mov     dword ptr [rsp+150h+var_118], eax
0x14000f4c1  mov     rax, [rsp+150h+var_100]
0x14000f4c6  mov     dword ptr [rsp+150h+var_120], ecx
0x14000f4ca  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f4d1  mov     [rsp+150h+var_128], rax
0x14000f4d6  mov     rcx, [rcx+40h]
0x14000f4da  call    WPP_RECORDER_SF_qlldd
0x14000f4df  mov     r8d, 1
0x14000f4e5  mov     rdx, [rsp+150h+var_100]
0x14000f4ea  xorps   xmm0, xmm0
0x14000f4ed  mov     rcx, cs:WdfDriverGlobals
0x14000f4f4  lea     r9, [rsp+150h+var_F0]
0x14000f4f9  mov     [rsp+150h+var_F0], 0
0x14000f502  movups  [rbp+50h+var_B0], xmm0
0x14000f506  mov     dword ptr [rbp+50h+var_B0+8], r8d
0x14000f50a  mov     dword ptr [rbp+50h+var_B0+0Ch], r8d
0x14000f50e  lea     r8, [rbp+50h+var_C0]
0x14000f512  movups  [rbp+50h+var_C0], xmm0
0x14000f516  mov     dword ptr [rbp+50h+var_C0], 38h ; '8'
0x14000f51d  movups  [rbp+50h+var_A0], xmm0
0x14000f521  cmp     esi, 32h ; '2'
0x14000f524  jbe     loc_14000F857
0x14000f52a  mov     rax, cs:off_1400150C0
0x14000f531  mov     [rbp+50h+var_90], rax
0x14000f535  mov     rax, cs:WdfFunctions_01015
  ... truncated ...
```
