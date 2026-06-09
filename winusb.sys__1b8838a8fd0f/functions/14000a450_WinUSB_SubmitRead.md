# WinUSB_SubmitRead

- ea: `0x14000a450`
- end: `0x14000ad7b`
- name: `WinUSB_SubmitRead`
- size: `2347`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x14000193c`
- `0x14000264c`
- `0x140003990`
- `0x14000866c`
- `0x1400087a0`
- `0x140008aa4`
- `0x14000a450`
- `0x1400106c0`
- `0x140010700`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a7bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a7bd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a848`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a875`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a848`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a875`

## string_xrefs

- `0x14000ac0b`: `onecore\drivers\wdm\usb\driver\winusb\sys\read.c`
- `0x14000ad45`: `onecore\drivers\wdm\usb\driver\winusb\sys\read.c`

## pseudocode

```c
_UNKNOWN **__fastcall WinUSB_SubmitRead(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, int a5)
{
  __int64 v6; // r13
  __int64 v8; // rax
  __int64 v9; // rsi
  __int64 v10; // rbx
  int v11; // eax
  int v12; // edx
  int v13; // r8d
  int v14; // r9d
  int v15; // r14d
  unsigned int v16; // eax
  int v17; // edx
  _UNKNOWN **result; // rax
  char v19; // r12
  unsigned __int8 v20; // cl
  __int64 v21; // r8
  __int64 v22; // rcx
  __int64 v23; // rsi
  __int64 v24; // r9
  unsigned int v25; // edi
  int v26; // edx
  unsigned int *v27; // rbx
  __int64 v28; // rdx
  KIRQL v29; // al
  int v30; // edx
  KIRQL v31; // di
  int v32; // r9d
  int v33; // edx
  int v34; // r9d
  unsigned int v35; // edi
  char v36; // dl
  __int64 v37; // rax
  unsigned __int16 v38; // ax
  __int64 v39; // rdi
  unsigned int v40; // ecx
  unsigned int v41; // r8d
  __int64 v42; // r8
  __int64 v43; // rdx
  char v44; // cl
  int v45; // edx
  __int64 v46; // rdi
  char v47; // [rsp+40h] [rbp-51h]
  char v48; // [rsp+41h] [rbp-50h]
  char v49; // [rsp+42h] [rbp-4Fh]
  unsigned __int8 *v50; // [rsp+48h] [rbp-49h] BYREF
  __int64 v51; // [rsp+50h] [rbp-41h] BYREF
  unsigned int v52; // [rsp+58h] [rbp-39h]
  __int64 v53; // [rsp+60h] [rbp-31h]
  __int64 v54; // [rsp+68h] [rbp-29h]
  __int64 v55; // [rsp+70h] [rbp-21h] BYREF
  int v56; // [rsp+78h] [rbp-19h]
  __int64 v57; // [rsp+7Ch] [rbp-15h]
  int v58; // [rsp+84h] [rbp-Dh]
  __int128 v59; // [rsp+88h] [rbp-9h] BYREF
  __int128 v60; // [rsp+98h] [rbp+7h] BYREF

  v59 = 0;
  v50 = 0;
  v51 = 0;
  v6 = a2;
  v60 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      51,
      (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids);
  }
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1256))(WdfDriverGlobals, a1);
  v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         v8,
         off_1400150F0);
  v53 = v9;
  v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
          WdfDriverGlobals,
          v6,
          off_140015040);
  v11 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, unsigned __int8 **))(WdfFunctions_01015 + 2152))(
          WdfDriverGlobals,
          v6,
          2,
          &v50);
  v15 = v11;
  if ( v11 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_dD(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        3,
        52,
        (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
        *(_DWORD *)(v10 + 28),
        v11);
    }
    goto LABEL_7;
  }
  v19 = v50[1];
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_dDi(WPP_GLOBAL_Control->DeviceExtension, v12, v13, v14, 0, v19, *(_DWORD *)(v10 + 28), a3);
  v20 = (v19 & 0xF) + 16;
  if ( v19 >= 0 )
    v20 = v19 & 0xF;
  v21 = v20;
  *(_BYTE *)(v10 + 24) = v20;
  v54 = v20;
  *(_BYTE *)(v10 + 25) = *v50;
  v22 = v53;
  v23 = *(_QWORD *)(*(_QWORD *)(v9 + 136) + 8 * (v21 + 35LL * *v50) + 24);
  v24 = *(_QWORD *)(v23 + 160);
  *(_QWORD *)(v23 + 80) = v6;
  *(_BYTE *)(v23 + 88) = 0;
  v25 = *(_DWORD *)(v10 + 28);
  WinUSB_CreateActivityIdSubRequest(*(_QWORD *)(v22 + 8), v6, v23 + 104, v24);
  v27 = (unsigned int *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01015 + 1616))(
                          WdfDriverGlobals,
                          *(_QWORD *)(v23 + 104),
                          off_140015040);
  v27[7] = v25;
  if ( a5 == 55590984 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v26) = 4;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v26,
        4,
        54,
        (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
        v19);
    }
    *(_BYTE *)(v23 + 64) = 0;
    goto LABEL_21;
  }
  v29 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v23 + 40));
  v31 = v29;
  if ( !a3 )
  {
    if ( *(_BYTE *)(v23 + 29) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v32 = 55;
        goto LABEL_30;
      }
LABEL_31:
      v15 = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)(v23 + 40), v31);
      goto LABEL_21;
    }
    if ( *(_BYTE *)(v23 + 64) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v32 = 56;
LABEL_30:
        LOBYTE(v30) = 4;
        WPP_RECORDER_SF_dD(
          WPP_GLOBAL_Control->DeviceExtension,
          v30,
          4,
          v32,
          (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
          v19,
          v27[7]);
        goto LABEL_31;
      }
      goto LABEL_31;
    }
  }
  v47 = *(_BYTE *)(v23 + 28);
  v49 = *(_BYTE *)(v23 + 21);
  v52 = *(_DWORD *)(v23 + 24);
  KeReleaseSpinLock((PKSPIN_LOCK)(v23 + 40), v29);
  if ( a3 )
  {
    v15 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *, _QWORD))(WdfFunctions_01015 + 2144))(
            WdfDriverGlobals,
            v6,
            &v51,
            0);
    if ( v15 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_21;
      v34 = 57;
      goto LABEL_36;
    }
  }
  *v27 = 0;
  if ( *(_BYTE *)(v23 + 64) )
  {
    v35 = *(unsigned __int16 *)(v23 + 66);
    v36 = *(_BYTE *)(v23 + 65);
    v48 = v36;
    if ( a3 <= v35 )
      LOWORD(v35) = a3;
    if ( (_WORD)v35 )
    {
      v37 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, _QWORD))(WdfFunctions_01015 + 1552))(
              WdfDriverGlobals,
              *(_QWORD *)(v23 + 72),
              0,
              0);
      v15 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, _QWORD))(WdfFunctions_01015 + 1576))(
              WdfDriverGlobals,
              v51,
              0,
              v37 + *(unsigned __int16 *)(v23 + 68),
              (unsigned __int16)v35);
      if ( v15 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_21;
        v34 = 58;
        goto LABEL_36;
      }
      v36 = v48;
    }
    *v27 = (unsigned __int16)v35;
    v38 = *(_WORD *)(v23 + 66);
    if ( (unsigned __int16)v35 >= v38 )
    {
      *(_BYTE *)(v23 + 64) = 0;
    }
    else
    {
      *(_WORD *)(v23 + 68) += v35;
      *(_WORD *)(v23 + 66) = v38 - v35;
    }
    if ( (unsigned __int16)v35 == a3 || v36 && !v47 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v33) = 4;
        WPP_RECORDER_SF_dDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v33,
          4,
          59,
          (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
          v19,
          v27[7],
          a3);
      }
      goto LABEL_21;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v33) = 4;
      WPP_RECORDER_SF_dDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v33,
        4,
        60,
        (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
        v19,
        v27[7],
        a3);
    }
  }
  LODWORD(v39) = *(_DWORD *)(v23 + 112);
  v40 = a3 - *v27;
  if ( v40 < (unsigned int)v39 )
  {
    v41 = *(_DWORD *)(v23 + 4);
    if ( !v41 )
      goto LABEL_60;
    LODWORD(v39) = v40 - v40 % v41;
  }
  if ( (_DWORD)v39 )
  {
    *((_BYTE *)v27 + 12) = 1;
    *((_QWORD *)&v60 + 1) = (unsigned int)v39;
    *(_QWORD *)&v60 = *v27;
    goto LABEL_63;
  }
LABEL_60:
  v39 = *(unsigned int *)(v23 + 4);
  if ( (_DWORD)v39 )
    v51 = *(_QWORD *)(v23 + 72);
  *((_QWORD *)&v60 + 1) = v39;
  *(_QWORD *)&v60 = 0;
  *((_BYTE *)v27 + 12) = 0;
LABEL_63:
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _UNKNOWN **(__fastcall *)(__int64, __int64, __int64, unsigned int *), unsigned int *))(WdfFunctions_01015 + 2080))(
    WdfDriverGlobals,
    *(_QWORD *)(v23 + 104),
    WinUSB_ReadPipeCompletion,
    v27);
  v15 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, __int64, __int128 *))(WdfFunctions_01015 + 2792))(
          WdfDriverGlobals,
          *(_QWORD *)(v23 + 160),
          *(_QWORD *)(v23 + 104),
          v51,
          &v60);
  if ( v15 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_21;
    v34 = 61;
    goto LABEL_36;
  }
  v43 = -10000LL * v52;
  *((_BYTE *)v27 + 24) = v54;
  v44 = *v50;
  *((_BYTE *)v27 + 14) = v47;
  *((_BYTE *)v27 + 25) = v44;
  v27[1] = a3;
  v27[2] = v39;
  *((_QWORD *)v27 + 2) = v43;
  *((_BYTE *)v27 + 13) = v49;
  if ( v43 )
  {
    *(_QWORD *)&v59 = 0x100000010LL;
    *((_QWORD *)&v59 + 1) = v43;
    v15 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, _QWORD))(WdfFunctions_01015 + 2096))(
            WdfDriverGlobals,
            *(_QWORD *)(v23 + 104),
            v42,
            0);
    if ( v15 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_21;
      v34 = 62;
LABEL_36:
      LOBYTE(v33) = 2;
      WPP_RECORDER_SF_dD(
        WPP_GLOBAL_Control->DeviceExtension,
        v33,
        3,
        v34,
        (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
        v27[7],
        v15);
      goto LABEL_21;
    }
  }
  else
  {
    v59 = 0x10u;
  }
  *(_DWORD *)(v23 + 92) = 0;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015 + 1640))(
    WdfDriverGlobals,
    v6,
    0,
    1821,
    "onecore\\drivers\\wdm\\usb\\driver\\winusb\\sys\\read.c");
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 (__fastcall *)()))(WdfFunctions_01015 + 2040))(
    WdfDriverGlobals,
    v6,
    WinUSB_CancelRead);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v45) = 4;
    WPP_RECORDER_SF_dDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v45,
      4,
      63,
      (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
      v19,
      v27[7],
      v39);
  }
  v46 = v53;
  WinUSB_IncrementKeepAliveCount(v53, v6);
  if ( !(*(unsigned __int8 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, __int128 *))(WdfFunctions_01015 + 2024))(
          WdfDriverGlobals,
          *(_QWORD *)(v23 + 104),
          *(_QWORD *)(v23 + 160),
          &v59) )
  {
    WinUSB_DecrementKeepAliveCount(v46, v6);
    v15 = -1073741536;
    if ( (*(unsigned int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2048))(
           WdfDriverGlobals,
           v6) != -1073741536 )
    {
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015 + 1648))(
        WdfDriverGlobals,
        v6,
        0,
        1874,
        "onecore\\drivers\\wdm\\usb\\driver\\winusb\\sys\\read.c");
      v15 = -1073741823;
      goto LABEL_21;
    }
    if ( _InterlockedExchange((volatile __int32 *)(v23 + 92), 1) == 1 )
    {
LABEL_21:
      v28 = *(_QWORD *)(v23 + 104);
      v57 = 0;
      v58 = 0;
      v55 = 24;
      v56 = 0;
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1992))(
        WdfDriverGlobals,
        v28,
        &v55);
      *(_QWORD *)(v23 + 80) = 0;
      if ( v15 >= 0 )
      {
        v16 = *v27;
        goto LABEL_8;
      }
LABEL_7:
      v16 = 0;
LABEL_8:
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, _QWORD))(WdfFunctions_01015 + 2120))(
        WdfDriverGlobals,
        v6,
        (unsigned int)v15,
        v16);
    }
  }
  result = &WPP_RECORDER_INITIALIZED;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v17) = 5;
      return (_UNKNOWN **)WPP_RECORDER_SF_d(
                            WPP_GLOBAL_Control->DeviceExtension,
                            v17,
                            1,
                            64,
                            (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
                            v15);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000a450  mov     [rsp-8+arg_18], rbx
0x14000a455  push    rbp
0x14000a456  push    rsi
0x14000a457  push    rdi
0x14000a458  push    r12
0x14000a45a  push    r13
0x14000a45c  push    r14
0x14000a45e  push    r15
0x14000a460  lea     rbp, [rsp-1Fh]
0x14000a465  sub     rsp, 0B0h
0x14000a46c  mov     rax, cs:__security_cookie
0x14000a473  xor     rax, rsp
0x14000a476  mov     [rbp+4Fh+var_38], rax
0x14000a47a  xorps   xmm0, xmm0
0x14000a47d  xor     edi, edi
0x14000a47f  movups  [rbp+4Fh+var_58], xmm0
0x14000a483  mov     [rbp+4Fh+var_98], rdi
0x14000a487  mov     r15, r8
0x14000a48a  mov     [rbp+4Fh+var_90], rdi
0x14000a48e  mov     r13, rdx
0x14000a491  movups  [rbp+4Fh+var_48], xmm0
0x14000a495  mov     rbx, rcx
0x14000a498  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000a49f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000a4a6  lea     rax, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x14000a4ad  jz      short loc_14000A4D4
0x14000a4af  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a4b6  cmp     [rcx+48h], di
0x14000a4ba  jz      short loc_14000A4D4
0x14000a4bc  mov     rcx, [rcx+40h]
0x14000a4c0  lea     r9d, [rdi+33h]
0x14000a4c4  lea     r8d, [rdi+1]
0x14000a4c8  mov     [rsp+0E0h+var_C0], rax
0x14000a4cd  mov     dl, 5
0x14000a4cf  call    WPP_RECORDER_SF_
0x14000a4d4  mov     rax, cs:WdfFunctions_01015
0x14000a4db  mov     rdx, rbx
0x14000a4de  mov     rcx, cs:WdfDriverGlobals
0x14000a4e5  mov     rax, [rax+4E8h]
0x14000a4ec  call    _guard_dispatch_icall
0x14000a4f1  mov     rcx, cs:WdfFunctions_01015
0x14000a4f8  mov     rdx, rax
0x14000a4fb  mov     r8, cs:off_1400150F0
0x14000a502  mov     r9, [rcx+650h]
0x14000a509  mov     rcx, cs:WdfDriverGlobals
0x14000a510  mov     rax, r9
0x14000a513  call    _guard_dispatch_icall
0x14000a518  mov     rcx, cs:WdfFunctions_01015
0x14000a51f  mov     rsi, rax
0x14000a522  mov     r8, cs:off_140015040
0x14000a529  mov     rdx, r13
0x14000a52c  mov     [rbp+4Fh+var_80], rax
0x14000a530  mov     rax, [rcx+650h]
0x14000a537  mov     rcx, cs:WdfDriverGlobals
0x14000a53e  call    _guard_dispatch_icall
0x14000a543  mov     rcx, cs:WdfFunctions_01015
0x14000a54a  lea     r9, [rbp+4Fh+var_98]
0x14000a54e  mov     rbx, rax
0x14000a551  mov     [rsp+0E0h+var_C0], rdi
0x14000a556  mov     r8d, 2
0x14000a55c  mov     rdx, r13
0x14000a55f  mov     rax, [rcx+868h]
0x14000a566  mov     rcx, cs:WdfDriverGlobals
0x14000a56d  call    _guard_dispatch_icall
0x14000a572  mov     r14d, eax
0x14000a575  test    eax, eax
0x14000a577  jns     loc_14000A646
0x14000a57d  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000a584  lea     r15, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x14000a58b  jz      short loc_14000A5B9
0x14000a58d  mov     ecx, [rbx+1Ch]
0x14000a590  mov     r9d, 34h ; '4'
0x14000a596  mov     [rsp+0E0h+var_B0], eax
0x14000a59a  mov     dl, 2
0x14000a59c  mov     [rsp+0E0h+var_B8], ecx
0x14000a5a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a5a7  lea     r8d, [r9-31h]
0x14000a5ab  mov     [rsp+0E0h+var_C0], r15
0x14000a5b0  mov     rcx, [rcx+40h]
0x14000a5b4  call    WPP_RECORDER_SF_dD
0x14000a5b9  mov     eax, edi
0x14000a5bb  mov     rcx, cs:WdfDriverGlobals
0x14000a5c2  mov     r8d, r14d
0x14000a5c5  mov     r9d, eax
0x14000a5c8  mov     rdx, r13
0x14000a5cb  mov     rax, cs:WdfFunctions_01015
0x14000a5d2  mov     rax, [rax+848h]
0x14000a5d9  call    _guard_dispatch_icall
0x14000a5de  xor     r9d, r9d
0x14000a5e1  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000a5e8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000a5ef  jz      short loc_14000A61E
0x14000a5f1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a5f8  cmp     [rcx+48h], r9w
0x14000a5fd  jz      short loc_14000A61E
0x14000a5ff  mov     rcx, [rcx+40h]
0x14000a603  mov     r9d, 40h ; '@'
0x14000a609  mov     [rsp+0E0h+var_B8], r14d
0x14000a60e  mov     dl, 5
0x14000a610  mov     [rsp+0E0h+var_C0], r15
0x14000a615  lea     r8d, [r9-3Fh]
0x14000a619  call    WPP_RECORDER_SF_d
0x14000a61e  mov     rcx, [rbp+4Fh+var_38]
0x14000a622  xor     rcx, rsp; StackCookie
0x14000a625  call    __security_check_cookie
0x14000a62a  mov     rbx, [rsp+0E0h+arg_18]
0x14000a632  add     rsp, 0B0h
0x14000a639  pop     r15
0x14000a63b  pop     r14
0x14000a63d  pop     r13
0x14000a63f  pop     r12
0x14000a641  pop     rdi
0x14000a642  pop     rsi
0x14000a643  pop     rbp
0x14000a644  retn
0x14000a646  mov     rax, [rbp+4Fh+var_98]
0x14000a64a  movzx   r12d, byte ptr [rax+1]
0x14000a64f  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000a656  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000a65d  jz      short loc_14000A680
0x14000a65f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a666  mov     eax, [rbx+1Ch]
0x14000a669  mov     [rsp+0E0h+var_A8], r15
0x14000a66e  mov     [rsp+0E0h+var_B0], eax
0x14000a672  mov     rcx, [rcx+40h]
0x14000a676  mov     [rsp+0E0h+var_B8], r12d
0x14000a67b  call    WPP_RECORDER_SF_dDi
0x14000a680  mov     al, r12b
0x14000a683  and     al, 0Fh
0x14000a685  movzx   edx, al
0x14000a688  test    r12b, r12b
0x14000a68b  lea     eax, [rdx+10h]
0x14000a68e  movzx   ecx, al
0x14000a691  cmovns  ecx, edx
0x14000a694  movzx   r8d, cl
0x14000a698  mov     [rbx+18h], r8b
0x14000a69c  mov     rax, [rbp+4Fh+var_98]
0x14000a6a0  mov     [rbp+4Fh+var_78], r8
0x14000a6a4  mov     cl, [rax]
0x14000a6a6  mov     [rbx+19h], cl
0x14000a6a9  mov     rax, [rbp+4Fh+var_98]
0x14000a6ad  movzx   ecx, byte ptr [rax]
0x14000a6b0  mov     rax, [rsi+88h]
0x14000a6b7  imul    rdx, rcx, 23h ; '#'
0x14000a6bb  mov     rcx, [rbp+4Fh+var_80]
0x14000a6bf  add     rdx, r8
0x14000a6c2  mov     rsi, [rax+rdx*8+18h]
0x14000a6c7  mov     rdx, r13
0x14000a6ca  mov     r9, [rsi+0A0h]
0x14000a6d1  lea     r8, [rsi+68h]
0x14000a6d5  mov     [rsi+50h], r13
0x14000a6d9  mov     [rsi+58h], dil
0x14000a6dd  mov     rcx, [rcx+8]
0x14000a6e1  mov     edi, [rbx+1Ch]
0x14000a6e4  call    WinUSB_CreateActivityIdSubRequest
0x14000a6e9  mov     rax, cs:WdfFunctions_01015
0x14000a6f0  mov     r8, cs:off_140015040
0x14000a6f7  mov     rdx, [rsi+68h]
0x14000a6fb  mov     rcx, cs:WdfDriverGlobals
0x14000a702  mov     rax, [rax+650h]
0x14000a709  call    _guard_dispatch_icall
0x14000a70e  cmp     [rbp+4Fh+arg_20], 3504048h
0x14000a715  mov     rbx, rax
0x14000a718  mov     [rax+1Ch], edi
0x14000a71b  jnz     loc_14000A7B9
0x14000a721  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000a728  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000a72f  jz      short loc_14000A75F
0x14000a731  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a738  lea     rax, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x14000a73f  mov     r9d, 36h ; '6'
0x14000a745  mov     [rsp+0E0h+var_B8], r12d
0x14000a74a  mov     [rsp+0E0h+var_C0], rax
0x14000a74f  mov     rcx, [rcx+40h]
0x14000a753  lea     r8d, [r9-32h]
0x14000a757  mov     dl, r8b
0x14000a75a  call    WPP_RECORDER_SF_d
0x14000a75f  xor     r9d, r9d
0x14000a762  mov     [rsi+40h], r9b
0x14000a766  lea     r15, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x14000a76d  mov     rax, cs:WdfFunctions_01015
0x14000a774  lea     r8, [rbp+4Fh+var_70]
0x14000a778  mov     rdx, [rsi+68h]
0x14000a77c  mov     rcx, cs:WdfDriverGlobals
0x14000a783  mov     [rbp+4Fh+var_64], r9
0x14000a787  mov     [rbp+4Fh+var_5C], r9d
0x14000a78b  mov     [rbp+4Fh+var_70], 18h
0x14000a793  mov     [rbp+4Fh+var_68], r9d
0x14000a797  mov     rax, [rax+7C8h]
0x14000a79e  call    _guard_dispatch_icall
0x14000a7a3  xor     edi, edi
0x14000a7a5  mov     [rsi+50h], rdi
0x14000a7a9  test    r14d, r14d
0x14000a7ac  js      loc_14000A5B9
0x14000a7b2  mov     eax, [rbx]
0x14000a7b4  jmp     loc_14000A5BB
0x14000a7b9  lea     rcx, [rsi+28h]; SpinLock
0x14000a7bd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000a7c4  nop     dword ptr [rax+rax+00h]
0x14000a7c9  mov     dil, al
0x14000a7cc  test    r15d, r15d
0x14000a7cf  jnz     loc_14000A85C
0x14000a7d5  cmp     [rsi+1Dh], r15b
0x14000a7d9  jnz     short loc_14000A7F7
0x14000a7db  cmp     [rsi+40h], r15b
0x14000a7df  jz      short loc_14000A85C
0x14000a7e1  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000a7e8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000a7ef  jz      short loc_14000A83E
0x14000a7f1  lea     r9d, [r15+38h]
0x14000a7f5  jmp     short loc_14000A80D
0x14000a7f7  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000a7fe  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000a805  jz      short loc_14000A83E
0x14000a807  mov     r9d, 37h ; '7'
0x14000a80d  mov     eax, [rbx+1Ch]
0x14000a810  mov     r8d, 4
0x14000a816  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a81d  mov     dl, r8b
0x14000a820  mov     [rsp+0E0h+var_B0], eax
0x14000a824  lea     rax, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x14000a82b  mov     [rsp+0E0h+var_B8], r12d
0x14000a830  mov     [rsp+0E0h+var_C0], rax
0x14000a835  mov     rcx, [rcx+40h]
0x14000a839  call    WPP_RECORDER_SF_dD
0x14000a83e  lea     rcx, [rsi+28h]; SpinLock
0x14000a842  mov     dl, dil; NewIrql
0x14000a845  xor     r14d, r14d
0x14000a848  call    cs:__imp_KeReleaseSpinLock
0x14000a84f  nop     dword ptr [rax+rax+00h]
0x14000a854  xor     r9d, r9d
0x14000a857  jmp     loc_14000A766
0x14000a85c  mov     al, [rsi+1Ch]
0x14000a85f  lea     rcx, [rsi+28h]; SpinLock
0x14000a863  mov     [rbp+4Fh+var_A0], al
0x14000a866  mov     dl, dil; NewIrql
0x14000a869  mov     al, [rsi+15h]
0x14000a86c  mov     [rbp+4Fh+var_9E], al
0x14000a86f  mov     eax, [rsi+18h]
0x14000a872  mov     [rbp+4Fh+var_88], eax
0x14000a875  call    cs:__imp_KeReleaseSpinLock
0x14000a87c  nop     dword ptr [rax+rax+00h]
0x14000a881  xor     r9d, r9d
0x14000a884  test    r15d, r15d
0x14000a887  jz      short loc_14000A906
0x14000a889  mov     rax, cs:WdfFunctions_01015
0x14000a890  lea     r8, [rbp+4Fh+var_90]
0x14000a894  mov     rcx, cs:WdfDriverGlobals
0x14000a89b  mov     rdx, r13
0x14000a89e  mov     rax, [rax+860h]
0x14000a8a5  call    _guard_dispatch_icall
0x14000a8aa  xor     r9d, r9d
0x14000a8ad  mov     r14d, eax
0x14000a8b0  test    eax, eax
0x14000a8b2  jns     short loc_14000A906
0x14000a8b4  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000a8bb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000a8c2  jz      loc_14000A766
0x14000a8c8  mov     r9d, 39h ; '9'
0x14000a8ce  lea     r15, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x14000a8d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a8dc  mov     r8d, 3
0x14000a8e2  mov     eax, [rbx+1Ch]
0x14000a8e5  mov     dl, 2
0x14000a8e7  mov     [rsp+0E0h+var_B0], r14d
0x14000a8ec  mov     [rsp+0E0h+var_B8], eax
0x14000a8f0  mov     rcx, [rcx+40h]
0x14000a8f4  mov     [rsp+0E0h+var_C0], r15
0x14000a8f9  call    WPP_RECORDER_SF_dD
0x14000a8fe  xor     r9d, r9d
0x14000a901  jmp     loc_14000A76D
0x14000a906  mov     [rbx], r9d
0x14000a909  cmp     [rsi+40h], r9b
0x14000a90d  jz      loc_14000AA37
0x14000a913  movzx   edi, word ptr [rsi+42h]
0x14000a917  mov     dl, [rsi+41h]
0x14000a91a  mov     [rbp+4Fh+var_9F], dl
0x14000a91d  cmp     r15d, edi
0x14000a920  ja      short loc_14000A926
0x14000a922  movzx   edi, r15w
0x14000a926  test    di, di
0x14000a929  jz      loc_14000A9B4
0x14000a92f  mov     rax, cs:WdfFunctions_01015
0x14000a936  xor     r8d, r8d
0x14000a939  mov     rdx, [rsi+48h]
0x14000a93d  mov     rcx, cs:WdfDriverGlobals
0x14000a944  mov     rax, [rax+610h]
0x14000a94b  call    _guard_dispatch_icall
0x14000a950  movzx   r9d, word ptr [rsi+44h]
0x14000a955  xor     r8d, r8d
0x14000a958  mov     rdx, [rbp+4Fh+var_90]
0x14000a95c  add     r9, rax
0x14000a95f  mov     rax, cs:WdfFunctions_01015
0x14000a966  movzx   ecx, di
0x14000a969  mov     [rsp+0E0h+var_C0], rcx
0x14000a96e  mov     rcx, cs:WdfDriverGlobals
0x14000a975  mov     rax, [rax+628h]
0x14000a97c  call    _guard_dispatch_icall
0x14000a981  xor     r9d, r9d
0x14000a984  mov     r14d, eax
  ... truncated ...
```
