# WinUSB_RawIoRead

- ea: `0x140008df0`
- end: `0x1400093d6`
- name: `WinUSB_RawIoRead`
- size: `1510`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x14000193c`
- `0x14000264c`
- `0x140003990`
- `0x14000866c`
- `0x140008df0`
- `0x1400106c0`
- `0x140010700`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000901d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000901d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000903a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000903a`

## pseudocode

```c
_UNKNOWN **__fastcall WinUSB_RawIoRead(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  __int64 v4; // rax
  __int64 v5; // r14
  __int64 v6; // rdi
  int v7; // eax
  _UNKNOWN **v8; // rdx
  unsigned int v9; // ebx
  int v10; // r9d
  unsigned __int8 *v11; // r8
  char v12; // r12
  unsigned __int8 v13; // cl
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // r15
  KIRQL v18; // al
  __int64 v19; // r13
  unsigned int v20; // r14d
  unsigned int v21; // ecx
  _UNKNOWN **v22; // rdx
  unsigned int v23; // ecx
  int v24; // eax
  _UNKNOWN **v25; // rdx
  int v26; // r9d
  __int64 v27; // r13
  unsigned __int8 v28; // cl
  int v29; // eax
  _UNKNOWN **v30; // rdx
  __int64 v31; // rdi
  int v32; // edx
  _UNKNOWN **v33; // rdx
  _UNKNOWN **result; // rax
  int v35; // [rsp+28h] [rbp-69h]
  char v36; // [rsp+30h] [rbp-61h]
  char v37; // [rsp+40h] [rbp-51h]
  unsigned __int8 *v38; // [rsp+48h] [rbp-49h] BYREF
  __int64 v39; // [rsp+50h] [rbp-41h] BYREF
  __int64 v40; // [rsp+58h] [rbp-39h]
  __int64 v41; // [rsp+60h] [rbp-31h]
  __int128 v42; // [rsp+68h] [rbp-29h] BYREF
  __int128 v43; // [rsp+78h] [rbp-19h] BYREF
  __int128 v44; // [rsp+88h] [rbp-9h]
  __int64 v45; // [rsp+98h] [rbp+7h]

  v38 = 0;
  v45 = 0;
  v2 = a2;
  v39 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      38,
      (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids);
  }
  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1256))(WdfDriverGlobals, a1);
  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         v4,
         off_1400150F0);
  v41 = v5;
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         v2,
         off_140015040);
  v45 = 0;
  v43 = 0;
  LOWORD(v43) = 40;
  v44 = 0;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01015 + 2128))(
    WdfDriverGlobals,
    v2,
    &v43);
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, unsigned __int8 **, _QWORD))(WdfFunctions_01015 + 2152))(
         WdfDriverGlobals,
         v2,
         2,
         &v38,
         0);
  v9 = v7;
  if ( v7 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_36:
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, _QWORD))(WdfFunctions_01015 + 2120))(
        WdfDriverGlobals,
        v2,
        v9,
        0);
      goto LABEL_37;
    }
    v10 = 39;
    v36 = v7;
    v35 = *(_DWORD *)(v6 + 28);
LABEL_7:
    LOBYTE(v8) = 2;
    WPP_RECORDER_SF_dD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v8,
      3,
      v10,
      (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
      v35,
      v36);
    goto LABEL_36;
  }
  v11 = v38;
  v12 = v38[1];
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v8) = 4;
    WPP_RECORDER_SF_dD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v8,
      4,
      40,
      (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
      v12,
      *(_DWORD *)(v6 + 28));
    v11 = v38;
  }
  v13 = (v12 & 0xF) + 16;
  if ( v12 >= 0 )
    v13 = v12 & 0xF;
  v14 = v13;
  v15 = 35LL * *v11;
  v16 = *(_QWORD *)(v5 + 136);
  v40 = v14;
  v17 = *(_QWORD *)(v16 + 8 * (v14 + v15) + 24);
  v18 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v17 + 40));
  v19 = *(unsigned int *)(v17 + 24);
  v37 = *(_BYTE *)(v17 + 21);
  KeReleaseSpinLock((PKSPIN_LOCK)(v17 + 40), v18);
  v20 = DWORD2(v43);
  *(_DWORD *)v6 = 0;
  v21 = *(_DWORD *)(v17 + 112);
  if ( v20 > v21 )
  {
    v9 = -1073741808;
    v22 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v22) = 3;
      WPP_RECORDER_SF_dD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v22,
        3,
        41,
        (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
        v21,
        16);
    }
    goto LABEL_36;
  }
  if ( !v20 || (v23 = *(_DWORD *)(v17 + 4)) == 0 || v20 % v23 )
  {
    v9 = -1073741808;
    v33 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v33) = 3;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v33,
        3,
        42,
        (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
        16);
    }
    goto LABEL_36;
  }
  v24 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 2144))(
          WdfDriverGlobals,
          v2,
          &v39);
  v9 = v24;
  if ( v24 < 0 )
  {
    v25 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_36;
    v26 = 43;
LABEL_21:
    LOBYTE(v25) = 2;
    WPP_RECORDER_SF_dD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v25,
      3,
      v26,
      (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
      *(_DWORD *)(v6 + 28),
      v24);
    goto LABEL_36;
  }
  v24 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, __int64, _QWORD))(WdfFunctions_01015 + 2792))(
          WdfDriverGlobals,
          *(_QWORD *)(v17 + 160),
          v2,
          v39,
          0);
  v9 = v24;
  if ( v24 < 0 )
  {
    v25 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_36;
    v26 = 44;
    goto LABEL_21;
  }
  v27 = -10000 * v19;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 (__fastcall *)(), __int64))(WdfFunctions_01015 + 2080))(
    WdfDriverGlobals,
    v2,
    WinUSB_RawIoReadCompletion,
    v6);
  *(_BYTE *)(v6 + 24) = v40;
  v28 = *v38;
  *(_BYTE *)(v6 + 13) = v37;
  *(_BYTE *)(v6 + 25) = v28;
  *(_DWORD *)(v6 + 4) = v20;
  *(_DWORD *)(v6 + 8) = v20;
  *(_BYTE *)(v6 + 14) = 0;
  if ( v27 )
  {
    *(_QWORD *)&v42 = 0x100000010LL;
    *((_QWORD *)&v42 + 1) = v27;
    v29 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2096))(WdfDriverGlobals, v2);
    v9 = v29;
    if ( v29 < 0 )
    {
      v8 = &WPP_RECORDER_INITIALIZED;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_36;
      v36 = v29;
      v10 = 45;
      v35 = *(_DWORD *)(v6 + 28);
      goto LABEL_7;
    }
  }
  else
  {
    v42 = 0x10u;
  }
  v30 = &WPP_RECORDER_INITIALIZED;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v30) = 4;
    WPP_RECORDER_SF_dDd(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v30,
      4,
      46,
      (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
      v12,
      *(_DWORD *)(v6 + 28),
      v20);
  }
  v31 = v41;
  WinUSB_IncrementKeepAliveCount(v41, v2);
  if ( !(*(unsigned __int8 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int128 *))(WdfFunctions_01015 + 2024))(
          WdfDriverGlobals,
          v2,
          *(_QWORD *)(v17 + 160),
          &v42) )
  {
    v9 = -1073741823;
    WinUSB_DecrementKeepAliveCount(v31, v2);
    goto LABEL_36;
  }
LABEL_37:
  result = &WPP_RECORDER_INITIALIZED;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v32) = 5;
      return (_UNKNOWN **)WPP_RECORDER_SF_d(
                            WPP_GLOBAL_Control->DeviceExtension,
                            v32,
                            1,
                            47,
                            (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
                            v9);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140008df0  mov     [rsp-8+arg_10], rbx
0x140008df5  push    rbp
0x140008df6  push    rsi
0x140008df7  push    rdi
0x140008df8  push    r12
0x140008dfa  push    r13
0x140008dfc  push    r14
0x140008dfe  push    r15
0x140008e00  lea     rbp, [rsp-1Fh]
0x140008e05  sub     rsp, 0B0h
0x140008e0c  mov     rax, cs:__security_cookie
0x140008e13  xor     rax, rsp
0x140008e16  mov     [rbp+4Fh+var_40], rax
0x140008e1a  xor     r13d, r13d
0x140008e1d  xorps   xmm0, xmm0
0x140008e20  xor     eax, eax
0x140008e22  mov     [rbp+4Fh+var_98], r13
0x140008e26  mov     [rbp+4Fh+var_48], rax
0x140008e2a  mov     rsi, rdx
0x140008e2d  mov     rbx, rcx
0x140008e30  mov     [rbp+4Fh+var_90], r13
0x140008e34  movups  [rbp+4Fh+var_78], xmm0
0x140008e38  movups  [rbp+4Fh+var_68], xmm0
0x140008e3c  movups  [rbp+4Fh+var_58], xmm0
0x140008e40  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140008e47  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140008e4e  lea     r12, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x140008e55  jz      short loc_140008E7D
0x140008e57  mov     rcx, cs:WPP_GLOBAL_Control
0x140008e5e  cmp     [rcx+48h], r13w
0x140008e63  jz      short loc_140008E7D
0x140008e65  mov     rcx, [rcx+40h]
0x140008e69  lea     r9d, [r13+26h]
0x140008e6d  lea     r8d, [r13+1]
0x140008e71  mov     [rsp+0E0h+var_C0], r12
0x140008e76  mov     dl, 5
0x140008e78  call    WPP_RECORDER_SF_
0x140008e7d  mov     rax, cs:WdfFunctions_01015
0x140008e84  mov     rdx, rbx
0x140008e87  mov     rcx, cs:WdfDriverGlobals
0x140008e8e  mov     rax, [rax+4E8h]
0x140008e95  call    _guard_dispatch_icall
0x140008e9a  mov     rcx, cs:WdfFunctions_01015
0x140008ea1  mov     rdx, rax
0x140008ea4  mov     r8, cs:off_1400150F0
0x140008eab  mov     r9, [rcx+650h]
0x140008eb2  mov     rcx, cs:WdfDriverGlobals
0x140008eb9  mov     rax, r9
0x140008ebc  call    _guard_dispatch_icall
0x140008ec1  mov     rcx, cs:WdfFunctions_01015
0x140008ec8  mov     r14, rax
0x140008ecb  mov     r8, cs:off_140015040
0x140008ed2  mov     rdx, rsi
0x140008ed5  mov     [rbp+4Fh+var_80], rax
0x140008ed9  mov     rax, [rcx+650h]
0x140008ee0  mov     rcx, cs:WdfDriverGlobals
0x140008ee7  call    _guard_dispatch_icall
0x140008eec  mov     rcx, cs:WdfFunctions_01015
0x140008ef3  lea     r8, [rbp+4Fh+var_68]
0x140008ef7  mov     rdi, rax
0x140008efa  xorps   xmm0, xmm0
0x140008efd  xor     eax, eax
0x140008eff  mov     rdx, rsi
0x140008f02  mov     [rbp+4Fh+var_48], rax
0x140008f06  mov     eax, 28h ; '('
0x140008f0b  movups  [rbp+4Fh+var_68], xmm0
0x140008f0f  mov     word ptr [rbp+4Fh+var_68], ax
0x140008f13  movups  [rbp+4Fh+var_58], xmm0
0x140008f17  mov     rax, [rcx+850h]
0x140008f1e  mov     rcx, cs:WdfDriverGlobals
0x140008f25  call    _guard_dispatch_icall
0x140008f2a  mov     rax, cs:WdfFunctions_01015
0x140008f31  lea     r9, [rbp+4Fh+var_98]
0x140008f35  mov     rcx, cs:WdfDriverGlobals
0x140008f3c  mov     r8d, 2
0x140008f42  mov     rdx, rsi
0x140008f45  mov     [rsp+0E0h+var_C0], r13
0x140008f4a  mov     rax, [rax+868h]
0x140008f51  call    _guard_dispatch_icall
0x140008f56  mov     ebx, eax
0x140008f58  test    eax, eax
0x140008f5a  jns     short loc_140008F9C
0x140008f5c  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140008f63  jz      loc_14000934F
0x140008f69  mov     ecx, [rdi+1Ch]
0x140008f6c  mov     r9d, 27h ; '''
0x140008f72  mov     dword ptr [rsp+0E0h+var_B0], eax
0x140008f76  mov     [rsp+0E0h+var_B8], ecx
0x140008f7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008f81  mov     r8d, 3
0x140008f87  mov     dl, 2
0x140008f89  mov     [rsp+0E0h+var_C0], r12
0x140008f8e  mov     rcx, [rcx+40h]
0x140008f92  call    WPP_RECORDER_SF_dD
0x140008f97  jmp     loc_14000934F
0x140008f9c  mov     r8, [rbp+4Fh+var_98]
0x140008fa0  movzx   r12d, byte ptr [r8+1]
0x140008fa5  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140008fac  jz      short loc_140008FE7
0x140008fae  mov     eax, [rdi+1Ch]
0x140008fb1  mov     r9d, 28h ; '('
0x140008fb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140008fbe  mov     dword ptr [rsp+0E0h+var_B0], eax
0x140008fc2  lea     rax, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x140008fc9  mov     [rsp+0E0h+var_B8], r12d
0x140008fce  lea     r8d, [r9-24h]
0x140008fd2  mov     [rsp+0E0h+var_C0], rax
0x140008fd7  mov     rcx, [rcx+40h]
0x140008fdb  mov     dl, r8b
0x140008fde  call    WPP_RECORDER_SF_dD
0x140008fe3  mov     r8, [rbp+4Fh+var_98]
0x140008fe7  mov     al, r12b
0x140008fea  and     al, 0Fh
0x140008fec  movzx   edx, al
0x140008fef  test    r12b, r12b
0x140008ff2  lea     eax, [rdx+10h]
0x140008ff5  movzx   ecx, al
0x140008ff8  movzx   eax, byte ptr [r8]
0x140008ffc  cmovns  ecx, edx
0x140008fff  movzx   edx, cl
0x140009002  imul    rcx, rax, 23h ; '#'
0x140009006  mov     rax, [r14+88h]
0x14000900d  add     rcx, rdx
0x140009010  mov     [rbp+4Fh+var_88], rdx
0x140009014  mov     r15, [rax+rcx*8+18h]
0x140009019  lea     rcx, [r15+28h]; SpinLock
0x14000901d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009024  nop     dword ptr [rax+rax+00h]
0x140009029  mov     cl, [r15+15h]
0x14000902d  mov     dl, al; NewIrql
0x14000902f  mov     r13d, [r15+18h]
0x140009033  mov     [rbp+4Fh+var_A0], cl
0x140009036  lea     rcx, [r15+28h]; SpinLock
0x14000903a  call    cs:__imp_KeReleaseSpinLock
0x140009041  nop     dword ptr [rax+rax+00h]
0x140009046  mov     r14d, dword ptr [rbp+4Fh+var_68+8]
0x14000904a  mov     dword ptr [rdi], 0
0x140009050  mov     ecx, [r15+70h]
0x140009054  cmp     r14d, ecx
0x140009057  jbe     short loc_1400090AA
0x140009059  mov     eax, 0C0000010h
0x14000905e  mov     ebx, eax
0x140009060  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140009067  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14000906e  lea     r12, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x140009075  jz      loc_14000934C
0x14000907b  mov     dword ptr [rsp+0E0h+var_B0], eax
0x14000907f  mov     r9d, 29h ; ')'
0x140009085  mov     [rsp+0E0h+var_B8], ecx
0x140009089  mov     rcx, cs:WPP_GLOBAL_Control
0x140009090  mov     [rsp+0E0h+var_C0], r12
0x140009095  lea     r8d, [r9-26h]
0x140009099  mov     dl, r8b
0x14000909c  mov     rcx, [rcx+40h]
0x1400090a0  call    WPP_RECORDER_SF_dD
0x1400090a5  jmp     loc_14000934C
0x1400090aa  test    r14d, r14d
0x1400090ad  jz      loc_140009308
0x1400090b3  mov     ecx, [r15+4]
0x1400090b7  test    ecx, ecx
0x1400090b9  jz      loc_140009308
0x1400090bf  xor     edx, edx
0x1400090c1  mov     eax, r14d
0x1400090c4  div     ecx
0x1400090c6  test    edx, edx
0x1400090c8  jnz     loc_140009308
0x1400090ce  mov     rax, cs:WdfFunctions_01015
0x1400090d5  lea     r8, [rbp+4Fh+var_90]
0x1400090d9  mov     rcx, cs:WdfDriverGlobals
0x1400090e0  mov     rdx, rsi
0x1400090e3  mov     rax, [rax+860h]
0x1400090ea  call    _guard_dispatch_icall
0x1400090ef  mov     ebx, eax
0x1400090f1  test    eax, eax
0x1400090f3  jns     short loc_140009143
0x1400090f5  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400090fc  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140009103  lea     r12, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x14000910a  jz      loc_14000934C
0x140009110  mov     r9d, 2Bh ; '+'
0x140009116  mov     rcx, cs:WPP_GLOBAL_Control
0x14000911d  mov     r8d, 3
0x140009123  mov     dword ptr [rsp+0E0h+var_B0], eax
0x140009127  mov     dl, 2
0x140009129  mov     eax, [rdi+1Ch]
0x14000912c  mov     [rsp+0E0h+var_B8], eax
0x140009130  mov     rcx, [rcx+40h]
0x140009134  mov     [rsp+0E0h+var_C0], r12
0x140009139  call    WPP_RECORDER_SF_dD
0x14000913e  jmp     loc_14000934C
0x140009143  mov     rax, cs:WdfFunctions_01015
0x14000914a  mov     r8, rsi
0x14000914d  mov     r9, [rbp+4Fh+var_90]
0x140009151  mov     rdx, [r15+0A0h]
0x140009158  mov     rcx, cs:WdfDriverGlobals
0x14000915f  mov     rax, [rax+0AE8h]
0x140009166  mov     [rsp+0E0h+var_C0], 0
0x14000916f  call    _guard_dispatch_icall
0x140009174  mov     ebx, eax
0x140009176  test    eax, eax
0x140009178  jns     short loc_1400091A0
0x14000917a  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140009181  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140009188  lea     r12, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x14000918f  jz      loc_14000934C
0x140009195  mov     r9d, 2Ch ; ','
0x14000919b  jmp     loc_140009116
0x1400091a0  mov     rax, cs:WdfFunctions_01015
0x1400091a7  lea     r8, WinUSB_RawIoReadCompletion
0x1400091ae  mov     rcx, cs:WdfDriverGlobals
0x1400091b5  mov     r9, rdi
0x1400091b8  mov     rdx, rsi
0x1400091bb  imul    r13, 0FFFFFFFFFFFFD8F0h
0x1400091c2  mov     rax, [rax+820h]
0x1400091c9  call    _guard_dispatch_icall
0x1400091ce  mov     rax, [rbp+4Fh+var_88]
0x1400091d2  mov     [rdi+18h], al
0x1400091d5  mov     rax, [rbp+4Fh+var_98]
0x1400091d9  mov     cl, [rax]
0x1400091db  mov     al, [rbp+4Fh+var_A0]
0x1400091de  mov     [rdi+0Dh], al
0x1400091e1  mov     [rdi+19h], cl
0x1400091e4  mov     [rdi+4], r14d
0x1400091e8  mov     [rdi+8], r14d
0x1400091ec  mov     byte ptr [rdi+0Eh], 0
0x1400091f0  test    r13, r13
0x1400091f3  jz      short loc_14000925C
0x1400091f5  mov     rax, cs:WdfFunctions_01015
0x1400091fc  mov     rdx, rsi
0x1400091ff  mov     rcx, cs:WdfDriverGlobals
0x140009206  mov     dword ptr [rbp+4Fh+var_78], 10h
0x14000920d  mov     dword ptr [rbp+4Fh+var_78+4], 1
0x140009214  mov     qword ptr [rbp+4Fh+var_78+8], r13
0x140009218  mov     rax, [rax+830h]
0x14000921f  call    _guard_dispatch_icall
0x140009224  xor     r13d, r13d
0x140009227  mov     ebx, eax
0x140009229  test    eax, eax
0x14000922b  jns     short loc_140009268
0x14000922d  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140009234  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14000923b  lea     r12, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x140009242  jz      loc_14000934F
0x140009248  mov     dword ptr [rsp+0E0h+var_B0], eax
0x14000924c  lea     r9d, [r13+2Dh]
0x140009250  mov     eax, [rdi+1Ch]
0x140009253  mov     [rsp+0E0h+var_B8], eax
0x140009257  jmp     loc_140008F7A
0x14000925c  mov     qword ptr [rbp+4Fh+var_78+8], r13
0x140009260  mov     qword ptr [rbp+4Fh+var_78], 10h
0x140009268  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000926f  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140009276  jz      short loc_1400092B4
0x140009278  mov     rcx, cs:WPP_GLOBAL_Control
0x14000927f  mov     r9d, 2Eh ; '.'
0x140009285  mov     eax, [rdi+1Ch]
0x140009288  mov     [rsp+0E0h+var_A8], r14d
0x14000928d  mov     dword ptr [rsp+0E0h+var_B0], eax
0x140009291  mov     rcx, [rcx+40h]
0x140009295  lea     r8d, [r9-2Ah]
0x140009299  mov     [rsp+0E0h+var_B8], r12d
0x14000929e  mov     dl, r8b
0x1400092a1  lea     r12, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x1400092a8  mov     [rsp+0E0h+var_C0], r12
0x1400092ad  call    WPP_RECORDER_SF_dDd
0x1400092b2  jmp     short loc_1400092BB
0x1400092b4  lea     r12, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x1400092bb  mov     rdi, [rbp+4Fh+var_80]
0x1400092bf  mov     rdx, rsi
0x1400092c2  mov     rcx, rdi
0x1400092c5  call    WinUSB_IncrementKeepAliveCount
0x1400092ca  mov     rax, cs:WdfFunctions_01015
0x1400092d1  lea     r9, [rbp+4Fh+var_78]
0x1400092d5  mov     r8, [r15+0A0h]
0x1400092dc  mov     rdx, rsi
0x1400092df  mov     rcx, cs:WdfDriverGlobals
0x1400092e6  mov     rax, [rax+7E8h]
0x1400092ed  call    _guard_dispatch_icall
0x1400092f2  test    al, al
0x1400092f4  jnz     short loc_140009372
0x1400092f6  mov     rdx, rsi
0x1400092f9  mov     rcx, rdi
0x1400092fc  mov     ebx, 0C0000001h
0x140009301  call    WinUSB_DecrementKeepAliveCount
0x140009306  jmp     short loc_14000934F
0x140009308  mov     eax, 0C0000010h
0x14000930d  mov     ebx, eax
0x14000930f  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140009316  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14000931d  lea     r12, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x140009324  jz      short loc_14000934C
0x140009326  mov     rcx, cs:WPP_GLOBAL_Control
0x14000932d  mov     r9d, 2Ah ; '*'
0x140009333  mov     [rsp+0E0h+var_B8], eax
0x140009337  mov     [rsp+0E0h+var_C0], r12
0x14000933c  mov     rcx, [rcx+40h]
0x140009340  lea     r8d, [r9-27h]
0x140009344  mov     dl, r8b
0x140009347  call    WPP_RECORDER_SF_d
0x14000934c  xor     r13d, r13d
  ... truncated ...
```
