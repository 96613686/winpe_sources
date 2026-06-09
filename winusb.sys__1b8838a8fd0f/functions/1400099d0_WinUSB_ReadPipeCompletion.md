# WinUSB_ReadPipeCompletion

- ea: `0x1400099d0`
- end: `0x14000a449`
- name: `WinUSB_ReadPipeCompletion`
- size: `2681`
- prototype: `_UNKNOWN **__fastcall(__int64, __int64, __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x14000193c`
- `0x14000264c`
- `0x140003990`
- `0x1400062f4`
- `0x140006cb0`
- `0x14000866c`
- `0x1400099d0`
- `0x1400106c0`
- `0x140010700`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009cc4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009cc4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009d48`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009def`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009d48`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009def`

## string_xrefs

- `0x14000a3bc`: `onecore\drivers\wdm\usb\driver\winusb\sys\read.c`

## pseudocode

```c
_UNKNOWN **__fastcall WinUSB_ReadPipeCompletion(__int64 a1, __int64 a2, __int64 a3, unsigned int *a4)
{
  int v5; // edx
  __int64 v8; // r15
  __int64 *v9; // r8
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // r14
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rsi
  int v16; // eax
  int *v17; // rdx
  int v18; // r13d
  int v19; // eax
  unsigned int v20; // r12d
  __int64 v21; // rdx
  int v22; // ebx
  unsigned int v23; // r8d
  int v24; // edx
  unsigned int v25; // ecx
  unsigned int v26; // r15d
  int v27; // eax
  int v28; // edx
  char v29; // r15
  char v30; // cl
  int v31; // edx
  __int64 v32; // r8
  int v33; // eax
  int v34; // edx
  KIRQL v35; // cl
  char v36; // cl
  char v37; // cl
  int v38; // ecx
  char v39; // cl
  __int64 v40; // rcx
  char v41; // cl
  __int64 v42; // r14
  _UNKNOWN **result; // rax
  char v44; // cl
  __int64 v45; // r15
  _DWORD *v46; // r9
  unsigned int v47; // r8d
  int v48; // edx
  char v49; // cl
  int v50; // r9d
  char v51; // al
  __int64 v52; // r12
  char v53; // cl
  __int64 v54; // r15
  char v55; // cl
  KIRQL NewIrql; // [rsp+50h] [rbp-69h]
  __int64 v57; // [rsp+58h] [rbp-61h] BYREF
  _BYTE v58[24]; // [rsp+60h] [rbp-59h] BYREF
  int v59; // [rsp+78h] [rbp-41h]
  __int64 v60; // [rsp+80h] [rbp-39h]
  __int64 v61; // [rsp+88h] [rbp-31h]
  __int64 v62; // [rsp+90h] [rbp-29h]
  __int64 v63; // [rsp+98h] [rbp-21h]
  __int128 v64; // [rsp+A0h] [rbp-19h] BYREF
  __int128 v65; // [rsp+B0h] [rbp-9h] BYREF

  v63 = a2;
  v60 = a1;
  v5 = 0;
  v57 = 0;
  v8 = a1;
  v65 = 0;
  v64 = 0;
  memset(v58, 0, sizeof(v58));
  v9 = WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v5) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      1,
      14,
      (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids);
  }
  v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1392))(
          WdfDriverGlobals,
          a2,
          v9);
  v11 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
          WdfDriverGlobals,
          v10,
          off_1400150F0);
  v12 = *((unsigned __int8 *)a4 + 24);
  v13 = 35LL * *((unsigned __int8 *)a4 + 25);
  v14 = *(_QWORD *)(v11 + 136);
  v62 = v11;
  v15 = *(_QWORD *)(v14 + 8 * (v12 + v13) + 24);
  WinUSB_DecrementKeepAliveCount(v11, *(_QWORD *)(v15 + 80));
  v16 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2032))(WdfDriverGlobals, v8);
  v17 = *(int **)(a3 + 24);
  v18 = v16;
  v19 = *v17;
  v20 = v17[4];
  v21 = *((_QWORD *)v17 + 1);
  v59 = v19;
  v22 = 0;
  v61 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 1552))(
          WdfDriverGlobals,
          v21,
          0);
  *(_QWORD *)&v58[12] = 0;
  *(_DWORD *)&v58[20] = 0;
  *(_QWORD *)v58 = 24;
  *(_DWORD *)&v58[8] = 0;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _BYTE *))(WdfFunctions_01015 + 1992))(WdfDriverGlobals, v8, v58);
  v24 = 16;
  v25 = *a4;
  if ( *((_BYTE *)a4 + 12) )
  {
    v25 += v20;
    *a4 = v25;
  }
  else
  {
    v26 = a4[1] - v25;
    if ( v26 >= v20 )
      v26 = v20;
    if ( v26 )
    {
      v27 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01015 + 2144))(
              WdfDriverGlobals,
              *(_QWORD *)(v15 + 80),
              &v57);
      v22 = v27;
      if ( v27 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_53;
        v29 = v12 & 0xF;
        v30 = (v12 & 0xF) + 0x80;
        if ( (v12 & 0x10) == 0 )
          v30 = v12 & 0xF;
        LOBYTE(v28) = 2;
        WPP_RECORDER_SF_dDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v28,
          4,
          15,
          (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
          v30,
          a4[7],
          v27);
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_53;
        if ( (v12 & 0x10) != 0 )
          v29 += 0x80;
        LOBYTE(v31) = 2;
        WPP_RECORDER_SF_dD(
          WPP_GLOBAL_Control->DeviceExtension,
          v31,
          4,
          16,
          (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
          v29,
          a4[7]);
        goto LABEL_49;
      }
      v32 = *a4;
      *((_QWORD *)&v64 + 1) = v26;
      *(_QWORD *)&v64 = v32;
      v33 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64, _QWORD))(WdfFunctions_01015 + 1576))(
              WdfDriverGlobals,
              v57,
              v32,
              v61,
              v26);
      *a4 += v26;
      v22 = v33;
      v25 = *a4;
      v24 = 16;
    }
    if ( v26 < v20 )
    {
      v35 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v15 + 40));
      NewIrql = v35;
      if ( *(_BYTE *)(v15 + 29) )
      {
        if ( !*(_BYTE *)(v15 + 30) )
        {
          *(_BYTE *)(v15 + 64) = 1;
          *(_WORD *)(v15 + 68) = v26;
          *(_WORD *)(v15 + 66) = v20 - v26;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v37 = v12 & 0xF;
            if ( (v12 & 0x10) != 0 )
              v37 += 0x80;
            LOBYTE(v34) = 4;
            WPP_RECORDER_SF_dDd(
              WPP_GLOBAL_Control->DeviceExtension,
              v34,
              4,
              18,
              (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
              v37,
              a4[7],
              v20 - v26);
            v35 = NewIrql;
          }
          *(_BYTE *)(v15 + 65) = v20 < *(_DWORD *)(v15 + 4);
        }
        KeReleaseSpinLock((PKSPIN_LOCK)(v15 + 40), v35);
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v36 = v12 & 0xF;
          if ( (v12 & 0x10) != 0 )
            v36 += 0x80;
          LOBYTE(v34) = 2;
          WPP_RECORDER_SF_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            v34,
            4,
            17,
            (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
            v36,
            a4[7]);
          v35 = NewIrql;
        }
        v22 = -1073741668;
        KeReleaseSpinLock((PKSPIN_LOCK)(v15 + 40), v35);
      }
      goto LABEL_49;
    }
    v8 = v60;
    v22 = 0;
  }
  if ( *(_BYTE *)(v15 + 88) )
  {
    if ( v18 == -1073741823
      && (unsigned int)(v59 + 1073741820) <= 0x12
      && (v38 = 450561, _bittest(&v38, v59 + 1073741820)) )
    {
      v22 = -1073741823;
    }
    else
    {
      v22 = -1073741536;
    }
LABEL_41:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v39 = v12 & 0xF;
      if ( (v12 & 0x10) != 0 )
        v39 += 0x80;
      LOBYTE(v24) = 3;
      WPP_RECORDER_SF_dDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v24,
        4,
        19,
        (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
        v39,
        a4[7],
        v22);
    }
    if ( v22 != -1073741536 && v22 != -1073741667 )
    {
      if ( *((_BYTE *)a4 + 13) )
      {
        *(_DWORD *)(v15 + 96) = v22;
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2200))(
          WdfDriverGlobals,
          v8,
          v20 + *a4);
        v22 = WinUSB_HandlePipeError(v40, v15, v8);
        if ( v22 >= 0 )
          goto LABEL_55;
      }
    }
    goto LABEL_49;
  }
  if ( v18 != -1073741536 )
  {
    v22 = v18;
    if ( v18 < 0 )
      goto LABEL_41;
  }
  v23 = a4[1];
  if ( v25 == v23 )
  {
LABEL_49:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v41 = v12 & 0xF;
      if ( (v12 & 0x10) != 0 )
        v41 += 0x80;
      WPP_RECORDER_SF_dDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        v24,
        v23,
        26,
        (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
        v41,
        a4[7],
        a4[1],
        *a4);
    }
    goto LABEL_53;
  }
  if ( v18 != -1073741536 && v20 < a4[2] && !*((_BYTE *)a4 + 14) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v44 = v12 & 0xF;
      if ( (v12 & 0x10) != 0 )
        v44 += 0x80;
      LOBYTE(v24) = 4;
      WPP_RECORDER_SF_dD(
        WPP_GLOBAL_Control->DeviceExtension,
        v24,
        4,
        20,
        (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
        v44,
        a4[7]);
    }
    goto LABEL_49;
  }
  LODWORD(v45) = *(_DWORD *)(v15 + 112);
  v46 = (_DWORD *)(v15 + 4);
  v47 = v23 - v25;
  if ( v47 <= (unsigned int)v45 )
  {
    if ( !*v46 )
    {
LABEL_78:
      v45 = (unsigned int)*v46;
      v57 = *(_QWORD *)(v15 + 72);
      v51 = 0;
      *((_QWORD *)&v64 + 1) = v45;
      *(_QWORD *)&v64 = 0;
      goto LABEL_79;
    }
    LODWORD(v45) = v47 - v47 % *v46;
  }
  if ( !(_DWORD)v45 )
    goto LABEL_78;
  *((_QWORD *)&v64 + 1) = (unsigned int)v45;
  *(_QWORD *)&v64 = v25;
  v22 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *, _DWORD *))(WdfFunctions_01015 + 2144))(
          WdfDriverGlobals,
          *(_QWORD *)(v15 + 80),
          &v57,
          v46);
  if ( v22 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v49 = v12 & 0xF;
      if ( (v12 & 0x10) != 0 )
        v49 += 0x80;
      v50 = 21;
LABEL_76:
      LOBYTE(v48) = 2;
      WPP_RECORDER_SF_dDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v48,
        4,
        v50,
        (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
        v49,
        a4[7],
        v22);
      goto LABEL_49;
    }
    goto LABEL_53;
  }
  v51 = 1;
LABEL_79:
  v52 = v60;
  *((_BYTE *)a4 + 12) = v51;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _UNKNOWN **(__fastcall *)(__int64, __int64, __int64, unsigned int *), unsigned int *))(WdfFunctions_01015 + 2080))(
    WdfDriverGlobals,
    v52,
    WinUSB_ReadPipeCompletion,
    a4);
  v22 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, __int64, __int128 *))(WdfFunctions_01015 + 2792))(
          WdfDriverGlobals,
          *(_QWORD *)(v15 + 160),
          v52,
          v57,
          &v64);
  if ( v22 >= 0 )
  {
    if ( *((_QWORD *)a4 + 2) )
    {
      *((_QWORD *)&v65 + 1) = *((_QWORD *)a4 + 2);
      *(_QWORD *)&v65 = 0x100000010LL;
      v22 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2096))(WdfDriverGlobals, v52);
      if ( v22 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v49 = v12 & 0xF;
          if ( (v12 & 0x10) != 0 )
            v49 += 0x80;
          v50 = 23;
          goto LABEL_76;
        }
        goto LABEL_53;
      }
    }
    else
    {
      v65 = 0x10u;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v53 = v12 & 0xF;
      if ( (v12 & 0x10) != 0 )
        v53 += 0x80;
      LOBYTE(v48) = 4;
      WPP_RECORDER_SF_dDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v48,
        4,
        24,
        (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
        v53,
        a4[7],
        v45);
    }
    v54 = v62;
    WinUSB_IncrementKeepAliveCount(v62, *(_QWORD *)(v15 + 80));
    if ( (*(unsigned __int8 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int128 *))(WdfFunctions_01015 + 2024))(
           WdfDriverGlobals,
           v52,
           v63,
           &v65) )
    {
      goto LABEL_55;
    }
    v22 = -1073741823;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v55 = v12 & 0xF;
      if ( (v12 & 0x10) != 0 )
        v55 += 0x80;
      LOBYTE(v24) = 2;
      WPP_RECORDER_SF_dDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v24,
        4,
        25,
        (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
        v55,
        a4[7],
        1);
    }
    WinUSB_DecrementKeepAliveCount(v54, *(_QWORD *)(v15 + 80));
    goto LABEL_49;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v49 = v12 & 0xF;
    if ( (v12 & 0x10) != 0 )
      v49 += 0x80;
    v50 = 22;
    goto LABEL_76;
  }
LABEL_53:
  v42 = *(_QWORD *)(v15 + 80);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2200))(WdfDriverGlobals, v42, *a4);
  if ( (*(unsigned int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2048))(WdfDriverGlobals, v42) == -1073741536 )
  {
    *(_DWORD *)(v15 + 96) = v22;
    if ( _InterlockedExchange((volatile __int32 *)(v15 + 92), 1) != 1 )
      goto LABEL_55;
  }
  else
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015 + 1648))(
      WdfDriverGlobals,
      v42,
      0,
      705,
      "onecore\\drivers\\wdm\\usb\\driver\\winusb\\sys\\read.c");
  }
  *(_QWORD *)&v58[12] = 0;
  *(_DWORD *)&v58[20] = 0;
  *(_QWORD *)v58 = 24;
  *(_DWORD *)&v58[8] = 0;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _BYTE *))(WdfFunctions_01015 + 1992))(
    WdfDriverGlobals,
    *(_QWORD *)(v15 + 104),
    v58);
  *(_QWORD *)(v15 + 80) = 0;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2104))(
    WdfDriverGlobals,
    v42,
    (unsigned int)v22);
LABEL_55:
  result = &WPP_RECORDER_INITIALIZED;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v24) = 5;
      return (_UNKNOWN **)WPP_RECORDER_SF_d(
                            WPP_GLOBAL_Control->DeviceExtension,
                            v24,
                            1,
                            27,
                            (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
                            v22);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400099d0  push    rbp
0x1400099d2  push    rbx
0x1400099d3  push    rsi
0x1400099d4  push    rdi
0x1400099d5  push    r12
0x1400099d7  push    r13
0x1400099d9  push    r14
0x1400099db  push    r15
0x1400099dd  lea     rbp, [rsp-1Fh]
0x1400099e2  sub     rsp, 0D8h
0x1400099e9  mov     rax, cs:__security_cookie
0x1400099f0  xor     rax, rsp
0x1400099f3  mov     [rbp+57h+var_50], rax
0x1400099f7  xorps   xmm0, xmm0
0x1400099fa  mov     [rbp+57h+var_78], rdx
0x1400099fe  mov     rsi, rdx
0x140009a01  mov     [rbp+57h+var_90], rcx
0x140009a05  xor     edx, edx
0x140009a07  xorps   xmm1, xmm1
0x140009a0a  xor     eax, eax
0x140009a0c  mov     [rbp+57h+var_B8], rdx
0x140009a10  mov     [rbp+57h+var_A0], rax
0x140009a14  mov     rdi, r9
0x140009a17  mov     rbx, r8
0x140009a1a  mov     r15, rcx
0x140009a1d  movups  [rbp+57h+var_60], xmm0
0x140009a21  movups  [rbp+57h+var_70], xmm0
0x140009a25  movups  [rbp+57h+var_B0], xmm1
0x140009a29  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140009a30  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140009a37  lea     r8, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x140009a3e  jz      short loc_140009A65
0x140009a40  mov     rcx, cs:WPP_GLOBAL_Control
0x140009a47  cmp     [rcx+48h], dx
0x140009a4b  jz      short loc_140009A65
0x140009a4d  mov     rcx, [rcx+40h]
0x140009a51  lea     r9d, [rdx+0Eh]
0x140009a55  mov     [rsp+110h+var_F0], r8
0x140009a5a  lea     r8d, [rdx+1]
0x140009a5e  mov     dl, 5
0x140009a60  call    WPP_RECORDER_SF_
0x140009a65  mov     rax, cs:WdfFunctions_01015
0x140009a6c  mov     rdx, rsi
0x140009a6f  mov     rcx, cs:WdfDriverGlobals
0x140009a76  mov     rax, [rax+570h]
0x140009a7d  call    _guard_dispatch_icall
0x140009a82  mov     rcx, cs:WdfFunctions_01015
0x140009a89  mov     rdx, rax
0x140009a8c  mov     r8, cs:off_1400150F0
0x140009a93  mov     rax, [rcx+650h]
0x140009a9a  mov     rcx, cs:WdfDriverGlobals
0x140009aa1  call    _guard_dispatch_icall
0x140009aa6  movzx   ecx, byte ptr [rdi+19h]
0x140009aaa  movzx   r14d, byte ptr [rdi+18h]
0x140009aaf  imul    rdx, rcx, 23h ; '#'
0x140009ab3  mov     rcx, [rax+88h]
0x140009aba  add     rdx, r14
0x140009abd  mov     [rbp+57h+var_80], rax
0x140009ac1  mov     rsi, [rcx+rdx*8+18h]
0x140009ac6  mov     rcx, rax
0x140009ac9  mov     rdx, [rsi+50h]
0x140009acd  call    WinUSB_DecrementKeepAliveCount
0x140009ad2  mov     rcx, cs:WdfFunctions_01015
0x140009ad9  mov     rdx, r15
0x140009adc  mov     rax, [rcx+7F0h]
0x140009ae3  mov     rcx, cs:WdfDriverGlobals
0x140009aea  call    _guard_dispatch_icall
0x140009aef  mov     rdx, [rbx+18h]
0x140009af3  mov     r13d, eax
0x140009af6  mov     rcx, cs:WdfFunctions_01015
0x140009afd  xor     r8d, r8d
0x140009b00  mov     eax, [rdx]
0x140009b02  mov     r12d, [rdx+10h]
0x140009b06  mov     rdx, [rdx+8]
0x140009b0a  mov     [rbp+57h+var_98], eax
0x140009b0d  mov     rax, [rcx+610h]
0x140009b14  mov     rcx, cs:WdfDriverGlobals
0x140009b1b  call    _guard_dispatch_icall
0x140009b20  mov     rcx, cs:WdfFunctions_01015
0x140009b27  lea     r8, [rbp+57h+var_B0]
0x140009b2b  xor     ebx, ebx
0x140009b2d  mov     [rbp+57h+var_88], rax
0x140009b31  mov     qword ptr [rbp+57h+var_B0+0Ch], rbx
0x140009b35  mov     rdx, r15
0x140009b38  mov     dword ptr [rbp+57h+var_A0+4], ebx
0x140009b3b  mov     qword ptr [rbp+57h+var_B0], 18h
0x140009b43  mov     dword ptr [rbp+57h+var_B0+8], ebx
0x140009b46  mov     rax, [rcx+7C8h]
0x140009b4d  mov     rcx, cs:WdfDriverGlobals
0x140009b54  call    _guard_dispatch_icall
0x140009b59  lea     edx, [rbx+10h]
0x140009b5c  mov     ecx, [rdi]
0x140009b5e  cmp     [rdi+0Ch], bl
0x140009b61  jnz     loc_140009E08
0x140009b67  mov     r15d, [rdi+4]
0x140009b6b  sub     r15d, ecx
0x140009b6e  cmp     r15d, r12d
0x140009b71  cmovnb  r15d, r12d
0x140009b75  test    r15d, r15d
0x140009b78  jz      loc_140009CB4
0x140009b7e  mov     rax, cs:WdfFunctions_01015
0x140009b85  lea     r8, [rbp+57h+var_B8]
0x140009b89  mov     rdx, [rsi+50h]
0x140009b8d  mov     rcx, cs:WdfDriverGlobals
0x140009b94  mov     rax, [rax+860h]
0x140009b9b  call    _guard_dispatch_icall
0x140009ba0  mov     ebx, eax
0x140009ba2  test    eax, eax
0x140009ba4  jns     loc_140009C73
0x140009baa  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140009bb1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140009bb8  jz      loc_140009F5F
0x140009bbe  mov     r15d, r14d
0x140009bc1  movzx   r12d, r14w
0x140009bc5  and     r15d, 0Fh
0x140009bc9  mov     r13d, 10h
0x140009bcf  lea     ecx, [r15+80h]
0x140009bd6  and     r12w, r13w
0x140009bda  jnz     short loc_140009BDF
0x140009bdc  mov     ecx, r15d
0x140009bdf  mov     [rsp+110h+var_D8], eax
0x140009be3  mov     r9d, 0Fh
0x140009be9  mov     eax, [rdi+1Ch]
0x140009bec  mov     dl, 2
0x140009bee  mov     [rsp+110h+var_E0], eax
0x140009bf2  lea     rax, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x140009bf9  mov     [rsp+110h+var_E8], ecx
0x140009bfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140009c04  lea     r8d, [r9-0Bh]
0x140009c08  mov     [rsp+110h+var_F0], rax
0x140009c0d  mov     rcx, [rcx+40h]
0x140009c11  call    WPP_RECORDER_SF_dDd
0x140009c16  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140009c1d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140009c24  jz      loc_140009F5F
0x140009c2a  test    r12w, r12w
0x140009c2e  jz      short loc_140009C34
0x140009c30  sub     r15d, 0FFFFFF80h
0x140009c34  mov     rcx, cs:WPP_GLOBAL_Control
0x140009c3b  lea     r12, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x140009c42  mov     eax, [rdi+1Ch]
0x140009c45  mov     r9d, r13d
0x140009c48  mov     [rsp+110h+var_E0], eax
0x140009c4c  mov     r8d, 4
0x140009c52  mov     [rsp+110h+var_E8], r15d
0x140009c57  mov     dl, 2
0x140009c59  mov     rcx, [rcx+40h]
0x140009c5d  mov     [rsp+110h+var_F0], r12
0x140009c62  call    WPP_RECORDER_SF_dD
0x140009c67  lea     r15, WPP_RECORDER_INITIALIZED
0x140009c6e  jmp     loc_140009F15
0x140009c73  mov     rax, cs:WdfFunctions_01015
0x140009c7a  mov     r8d, [rdi]
0x140009c7d  mov     r9, [rbp+57h+var_88]
0x140009c81  mov     rdx, [rbp+57h+var_B8]
0x140009c85  mov     ecx, r15d
0x140009c88  mov     qword ptr [rbp+57h+var_70+8], rcx
0x140009c8c  mov     qword ptr [rbp+57h+var_70], r8
0x140009c90  mov     rax, [rax+628h]
0x140009c97  mov     [rsp+110h+var_F0], rcx
0x140009c9c  mov     rcx, cs:WdfDriverGlobals
0x140009ca3  call    _guard_dispatch_icall
0x140009ca8  add     [rdi], r15d
0x140009cab  mov     ebx, eax
0x140009cad  mov     ecx, [rdi]
0x140009caf  mov     edx, 10h
0x140009cb4  cmp     r15d, r12d
0x140009cb7  jnb     loc_140009E00
0x140009cbd  lea     r13, [rsi+28h]
0x140009cc1  mov     rcx, r13; SpinLock
0x140009cc4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009ccb  nop     dword ptr [rax+rax+00h]
0x140009cd0  mov     cl, al
0x140009cd2  mov     [rbp+57h+NewIrql], al
0x140009cd5  xor     eax, eax
0x140009cd7  cmp     [rsi+1Dh], al
0x140009cda  jnz     loc_140009D60
0x140009ce0  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140009ce7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140009cee  jz      short loc_140009D37
0x140009cf0  mov     ecx, r14d
0x140009cf3  and     ecx, 0Fh
0x140009cf6  test    r14b, 10h
0x140009cfa  jz      short loc_140009CFF
0x140009cfc  sub     ecx, 0FFFFFF80h
0x140009cff  mov     eax, [rdi+1Ch]
0x140009d02  lea     r12, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x140009d09  mov     [rsp+110h+var_E0], eax
0x140009d0d  mov     r9d, 11h
0x140009d13  mov     [rsp+110h+var_E8], ecx
0x140009d17  mov     dl, 2
0x140009d19  mov     rcx, cs:WPP_GLOBAL_Control
0x140009d20  mov     [rsp+110h+var_F0], r12
0x140009d25  lea     r8d, [r9-0Dh]
0x140009d29  mov     rcx, [rcx+40h]
0x140009d2d  call    WPP_RECORDER_SF_dD
0x140009d32  mov     cl, [rbp+57h+NewIrql]
0x140009d35  jmp     short loc_140009D3E
0x140009d37  lea     r12, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x140009d3e  mov     dl, cl; NewIrql
0x140009d40  mov     ebx, 0C000009Ch
0x140009d45  mov     rcx, r13; SpinLock
0x140009d48  call    cs:__imp_KeReleaseSpinLock
0x140009d4f  nop     dword ptr [rax+rax+00h]
0x140009d54  lea     r15, WPP_RECORDER_INITIALIZED
0x140009d5b  jmp     loc_140009F0F
0x140009d60  cmp     [rsi+1Eh], al
0x140009d63  jnz     short loc_140009DE3
0x140009d65  movzx   eax, r12w
0x140009d69  mov     byte ptr [rsi+40h], 1
0x140009d6d  sub     ax, r15w
0x140009d71  mov     [rsi+44h], r15w
0x140009d76  mov     [rsi+42h], ax
0x140009d7a  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140009d81  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140009d88  jz      short loc_140009DD7
0x140009d8a  mov     ecx, r14d
0x140009d8d  and     ecx, 0Fh
0x140009d90  test    r14b, 10h
0x140009d94  jz      short loc_140009D99
0x140009d96  sub     ecx, 0FFFFFF80h
0x140009d99  movzx   eax, ax
0x140009d9c  mov     r9d, 12h
0x140009da2  mov     [rsp+110h+var_D8], eax
0x140009da6  mov     eax, [rdi+1Ch]
0x140009da9  mov     [rsp+110h+var_E0], eax
0x140009dad  lea     rax, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x140009db4  mov     [rsp+110h+var_E8], ecx
0x140009db8  lea     r8d, [r9-0Eh]
0x140009dbc  mov     rcx, cs:WPP_GLOBAL_Control
0x140009dc3  mov     dl, r8b
0x140009dc6  mov     [rsp+110h+var_F0], rax
0x140009dcb  mov     rcx, [rcx+40h]
0x140009dcf  call    WPP_RECORDER_SF_dDd
0x140009dd4  mov     cl, [rbp+57h+NewIrql]
0x140009dd7  cmp     r12d, [rsi+4]
0x140009ddb  setb    al
0x140009dde  mov     [rsi+41h], al
0x140009de1  jmp     short loc_140009DEA
0x140009de3  lea     r15, WPP_RECORDER_INITIALIZED
0x140009dea  mov     dl, cl; NewIrql
0x140009dec  mov     rcx, r13; SpinLock
0x140009def  call    cs:__imp_KeReleaseSpinLock
0x140009df6  nop     dword ptr [rax+rax+00h]
0x140009dfb  jmp     loc_140009F08
0x140009e00  mov     r15, [rbp+57h+var_90]
0x140009e04  xor     ebx, ebx
0x140009e06  jmp     short loc_140009E0D
0x140009e08  add     ecx, r12d
0x140009e0b  mov     [rdi], ecx
0x140009e0d  cmp     [rsi+58h], bl
0x140009e10  jz      short loc_140009E3F
0x140009e12  mov     ebx, 0C0000001h
0x140009e17  cmp     r13d, ebx
0x140009e1a  jnz     short loc_140009E38
0x140009e1c  mov     eax, [rbp+57h+var_98]
0x140009e1f  add     eax, 3FFFFFFCh
0x140009e24  cmp     eax, 12h
0x140009e27  ja      short loc_140009E38
0x140009e29  mov     ecx, 6E001h
0x140009e2e  bt      ecx, eax
0x140009e31  jnb     short loc_140009E38
0x140009e33  mov     ebx, r13d
0x140009e36  jmp     short loc_140009E58
0x140009e38  mov     ebx, 0C0000120h
0x140009e3d  jmp     short loc_140009E58
0x140009e3f  cmp     r13d, 0C0000120h
0x140009e46  jz      loc_14000A026
0x140009e4c  mov     ebx, r13d
0x140009e4f  test    r13d, r13d
0x140009e52  jns     loc_14000A026
0x140009e58  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140009e5f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140009e66  jz      short loc_140009EAD
0x140009e68  mov     ecx, r14d
0x140009e6b  and     ecx, 0Fh
0x140009e6e  test    dl, r14b
0x140009e71  jz      short loc_140009E76
0x140009e73  sub     ecx, 0FFFFFF80h
0x140009e76  mov     eax, [rdi+1Ch]
0x140009e79  mov     r9d, 13h
0x140009e7f  mov     [rsp+110h+var_D8], ebx
0x140009e83  mov     dl, 3
0x140009e85  mov     [rsp+110h+var_E0], eax
0x140009e89  lea     rax, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x140009e90  mov     [rsp+110h+var_E8], ecx
0x140009e94  mov     rcx, cs:WPP_GLOBAL_Control
0x140009e9b  lea     r8d, [r9-0Fh]
0x140009e9f  mov     [rsp+110h+var_F0], rax
0x140009ea4  mov     rcx, [rcx+40h]
0x140009ea8  call    WPP_RECORDER_SF_dDd
0x140009ead  cmp     ebx, 0C0000120h
0x140009eb3  jz      short loc_140009F01
0x140009eb5  cmp     ebx, 0C000009Dh
0x140009ebb  jz      short loc_140009F01
0x140009ebd  xor     r13d, r13d
0x140009ec0  cmp     [rdi+0Dh], r13b
0x140009ec4  jz      short loc_140009F01
0x140009ec6  mov     [rsi+60h], ebx
0x140009ec9  mov     rdx, r15
  ... truncated ...
```
