# WinUSB_ControlTransfer

- ea: `0x140001e04`
- end: `0x1400024c7`
- name: `WinUSB_ControlTransfer`
- size: `1731`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400026d0`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x14000193c`
- `0x140001a4c`
- `0x140001e04`
- `0x14000264c`
- `0x140003990`
- `0x140003dc8`
- `0x1400106c0`
- `0x140010700`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400021a4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400021a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400021ba`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400021ba`

## pseudocode

```c
__int64 __fastcall WinUSB_ControlTransfer(__int64 a1, __int64 a2, __int64 a3, _BYTE *a4)
{
  __int16 v4; // r15
  int v8; // eax
  int v9; // edx
  int v10; // r8d
  unsigned int v11; // ebx
  int v12; // edx
  unsigned __int8 *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // r9
  __int64 v16; // r13
  unsigned __int8 *v17; // r15
  unsigned __int8 v18; // dl
  char *v19; // rbx
  char v20; // al
  int v21; // r11d
  unsigned __int8 v22; // bl
  int v23; // edx
  unsigned __int8 v24; // r8
  unsigned int v25; // r10d
  KIRQL v26; // al
  __int64 v27; // r12
  int v28; // eax
  int v29; // edx
  int v30; // eax
  int v31; // edx
  int v32; // r9d
  __int64 v33; // r13
  __int64 v34; // rax
  __int64 v35; // rax
  unsigned __int8 *v37; // [rsp+40h] [rbp-59h] BYREF
  __int64 v38; // [rsp+48h] [rbp-51h] BYREF
  __int64 v39; // [rsp+50h] [rbp-49h] BYREF
  __int64 v40; // [rsp+58h] [rbp-41h]
  __int64 v41; // [rsp+60h] [rbp-39h]
  _BYTE *v42; // [rsp+68h] [rbp-31h]
  __int128 v43; // [rsp+70h] [rbp-29h] BYREF
  __int128 v44; // [rsp+80h] [rbp-19h] BYREF
  __int128 v45; // [rsp+90h] [rbp-9h]
  __int64 v46; // [rsp+A0h] [rbp+7h]

  v4 = 0;
  v41 = a2;
  v38 = 0;
  v37 = 0;
  v46 = 0;
  v42 = a4;
  v39 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      126,
      (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids);
  }
  *a4 = 1;
  v46 = 0;
  v44 = 0;
  LOWORD(v44) = 40;
  v45 = 0;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01015 + 2128))(
    WdfDriverGlobals,
    a3,
    &v44);
  v40 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
          WdfDriverGlobals,
          a3,
          off_140015040);
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, unsigned __int8 **, __int64 *))(WdfFunctions_01015 + 2152))(
         WdfDriverGlobals,
         a3,
         9,
         &v37,
         &v39);
  v11 = v8;
  if ( v8 >= 0 )
  {
    if ( DWORD2(v44) > 0x1000 )
    {
      v11 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v11;
      WPP_RECORDER_SF_ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        v10,
        128,
        (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
        SBYTE8(v44),
        0);
      goto LABEL_53;
    }
    v13 = v37;
    v14 = *v37;
    if ( (unsigned __int8)v14 >= *(_BYTE *)(a1 + 128) )
    {
      v11 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v11;
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_dD(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        3,
        129,
        (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
        v14,
        13);
      goto LABEL_53;
    }
    v15 = *(_QWORD *)(a1 + 136);
    v16 = *(_QWORD *)(280 * v14 + v15 + 24);
    if ( !v16 )
    {
      v11 = -1073741436;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v11;
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        6,
        130,
        (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
        132);
      goto LABEL_53;
    }
    v17 = v37 + 1;
    v18 = v37[1];
    v19 = (char *)(v37 + 5);
    if ( (v18 & 3) == 1 )
    {
      v20 = *(_BYTE *)(280 * v14 + v15);
      if ( *v19 != v20 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v9) = 4;
          WPP_RECORDER_SF_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            v9,
            6,
            131,
            (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
            *v19,
            v20);
          v18 = *v17;
          v13 = v37;
        }
        *v19 = *(_BYTE *)(280LL * *v13 + *(_QWORD *)(a1 + 136));
      }
    }
    if ( (v18 & 3) == 2 )
    {
      v21 = (unsigned __int8)*v19;
      v22 = *(_BYTE *)(a1 + 128);
      v23 = v21;
      if ( !v22 )
      {
LABEL_28:
        v11 = -1073741811;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return v11;
        LOBYTE(v23) = 2;
        WPP_RECORDER_SF_dD(
          WPP_GLOBAL_Control->DeviceExtension,
          v23,
          6,
          132,
          (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
          v21,
          13);
        v4 = 0;
        goto LABEL_53;
      }
      v24 = 0;
      while ( 1 )
      {
        v25 = (v21 & 0xF) + 16;
        if ( (v21 & 0x80u) == 0 )
          v25 = v21 & 0xF;
        if ( *(_QWORD *)(*(_QWORD *)(a1 + 136) + 8 * (v25 + 35LL * v24) + 24) )
          break;
        if ( ++v24 >= v22 )
          goto LABEL_28;
      }
    }
    if ( (unsigned __int8)WinUSB_IsBlockedControlTransfer(v17) )
    {
      v4 = 0;
      v11 = 0;
      goto LABEL_53;
    }
    v26 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v16 + 40));
    v27 = *(unsigned int *)(v16 + 24);
    KeReleaseSpinLock((PKSPIN_LOCK)(v16 + 40), v26);
    if ( *((_QWORD *)&v44 + 1) )
    {
      v28 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 2144))(
              WdfDriverGlobals,
              a3,
              &v38);
      v11 = v28;
      if ( v28 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return v11;
        LOBYTE(v29) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v29,
          6,
          133,
          (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
          v28);
        v4 = 0;
        goto LABEL_53;
      }
    }
    v30 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, unsigned __int8 *, __int64, _QWORD))(WdfFunctions_01015 + 2672))(
            WdfDriverGlobals,
            *(_QWORD *)(a1 + 8),
            a3,
            v17,
            v38,
            0);
    v4 = 0;
    v11 = v30;
    if ( v30 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v11;
      v32 = 134;
      goto LABEL_39;
    }
    v33 = v40;
    v4 = -10000 * v27;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 (__fastcall *)(), __int64))(WdfFunctions_01015 + 2080))(
      WdfDriverGlobals,
      a3,
      WinUSB_ControlTransferCompletion,
      v40);
    *(_BYTE *)(v33 + 24) = 0;
    if ( -10000 * v27 )
    {
      *(_QWORD *)&v43 = 0x100000010LL;
      *((_QWORD *)&v43 + 1) = -10000 * v27;
      v30 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2096))(WdfDriverGlobals, a3);
      v4 = 0;
      v11 = v30;
      if ( v30 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return v11;
        v32 = 135;
LABEL_39:
        LOBYTE(v31) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v31,
          6,
          v32,
          (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
          v30);
        goto LABEL_53;
      }
    }
    else
    {
      v43 = 0x10u;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v31) = 5;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v31,
        6,
        136,
        (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
        *(_DWORD *)(v33 + 28));
    }
    WinUSB_IncrementKeepAliveCount(a1, a3);
    v34 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1256))(WdfDriverGlobals, v41);
    v35 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 336))(WdfDriverGlobals, v34);
    if ( (*(unsigned __int8 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int128 *))(WdfFunctions_01015 + 2024))(
           WdfDriverGlobals,
           a3,
           v35,
           &v43) )
    {
      *v42 = 0;
    }
    else
    {
      v11 = -1073741823;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          6,
          137,
          (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
          1);
      }
      WinUSB_DecrementKeepAliveCount(a1, a3);
    }
    goto LABEL_53;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return v11;
  LOBYTE(v9) = 2;
  WPP_RECORDER_SF_d(
    WPP_GLOBAL_Control->DeviceExtension,
    v9,
    3,
    127,
    (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
    v8);
LABEL_53:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) != v4 )
  {
    LOBYTE(v12) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      1,
      138,
      (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
      v11);
  }
  return v11;
}

```

## disassembly

```asm
0x140001e04  push    rbp
0x140001e06  push    rbx
0x140001e07  push    rsi
0x140001e08  push    rdi
0x140001e09  push    r12
0x140001e0b  push    r13
0x140001e0d  push    r14
0x140001e0f  push    r15
0x140001e11  lea     rbp, [rsp-1Fh]
0x140001e16  sub     rsp, 0B8h
0x140001e1d  mov     rax, cs:__security_cookie
0x140001e24  xor     rax, rsp
0x140001e27  mov     [rbp+57h+var_48], rax
0x140001e2b  xor     r15d, r15d
0x140001e2e  mov     [rbp+57h+var_90], rdx
0x140001e32  xorps   xmm1, xmm1
0x140001e35  mov     [rbp+57h+var_A8], r15
0x140001e39  xor     eax, eax
0x140001e3b  mov     [rbp+57h+var_B0], r15
0x140001e3f  mov     rbx, r9
0x140001e42  mov     [rbp+57h+var_50], rax
0x140001e46  xorps   xmm0, xmm0
0x140001e49  mov     [rbp+57h+var_88], rbx
0x140001e4d  mov     r14, r8
0x140001e50  mov     [rbp+57h+var_A0], r15
0x140001e54  mov     rsi, rcx
0x140001e57  movups  [rbp+57h+var_80], xmm0
0x140001e5b  movups  [rbp+57h+var_70], xmm1
0x140001e5f  movups  [rbp+57h+var_60], xmm1
0x140001e63  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140001e6a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140001e71  lea     rdi, WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids
0x140001e78  jz      short loc_140001EA0
0x140001e7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140001e81  cmp     [rcx+48h], r15w
0x140001e86  jz      short loc_140001EA0
0x140001e88  mov     rcx, [rcx+40h]
0x140001e8c  lea     r9d, [r15+7Eh]
0x140001e90  lea     r8d, [r15+1]
0x140001e94  mov     [rsp+0F0h+var_D0], rdi
0x140001e99  mov     dl, 5
0x140001e9b  call    WPP_RECORDER_SF_
0x140001ea0  xor     eax, eax
0x140001ea2  mov     byte ptr [rbx], 1
0x140001ea5  mov     rcx, cs:WdfDriverGlobals
0x140001eac  lea     r8, [rbp+57h+var_70]
0x140001eb0  mov     [rbp+57h+var_50], rax
0x140001eb4  xorps   xmm0, xmm0
0x140001eb7  movups  [rbp+57h+var_70], xmm0
0x140001ebb  mov     eax, 28h ; '('
0x140001ec0  mov     rdx, r14
0x140001ec3  mov     word ptr [rbp+57h+var_70], ax
0x140001ec7  mov     rax, cs:WdfFunctions_01015
0x140001ece  movups  [rbp+57h+var_60], xmm0
0x140001ed2  mov     rax, [rax+850h]
0x140001ed9  call    _guard_dispatch_icall
0x140001ede  mov     rax, cs:WdfFunctions_01015
0x140001ee5  mov     rdx, r14
0x140001ee8  mov     r8, cs:off_140015040
0x140001eef  mov     rcx, cs:WdfDriverGlobals
0x140001ef6  mov     rax, [rax+650h]
0x140001efd  call    _guard_dispatch_icall
0x140001f02  mov     rcx, cs:WdfFunctions_01015
0x140001f09  lea     r9, [rbp+57h+var_B0]
0x140001f0d  mov     [rbp+57h+var_98], rax
0x140001f11  mov     r8d, 9
0x140001f17  mov     rdx, r14
0x140001f1a  mov     rax, [rcx+868h]
0x140001f21  lea     rcx, [rbp+57h+var_A0]
0x140001f25  mov     [rsp+0F0h+var_D0], rcx
0x140001f2a  mov     rcx, cs:WdfDriverGlobals
0x140001f31  call    _guard_dispatch_icall
0x140001f36  mov     ebx, eax
0x140001f38  test    eax, eax
0x140001f3a  jns     short loc_140001F7A
0x140001f3c  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140001f43  jz      loc_1400024A4
0x140001f49  mov     rcx, cs:WPP_GLOBAL_Control
0x140001f50  mov     r9d, 7Fh
0x140001f56  mov     dword ptr [rsp+0F0h+var_C8], eax
0x140001f5a  mov     dl, 2
0x140001f5c  mov     [rsp+0F0h+var_D0], rdi
0x140001f61  mov     rcx, [rcx+40h]
0x140001f65  lea     r8d, [r9-7Ch]
0x140001f69  call    WPP_RECORDER_SF_d
0x140001f6e  lea     r12, WPP_RECORDER_INITIALIZED
0x140001f75  jmp     loc_14000246D
0x140001f7a  mov     eax, dword ptr [rbp+57h+var_70+8]
0x140001f7d  mov     ecx, 1000h
0x140001f82  cmp     eax, ecx
0x140001f84  jbe     short loc_140001FBD
0x140001f86  mov     ebx, 0C000000Dh
0x140001f8b  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140001f92  jz      loc_1400024A4
0x140001f98  mov     [rsp+0F0h+var_C0], ecx
0x140001f9c  mov     r9d, 80h
0x140001fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x140001fa9  mov     dword ptr [rsp+0F0h+var_C8], eax
0x140001fad  mov     [rsp+0F0h+var_D0], rdi
0x140001fb2  mov     rcx, [rcx+40h]
0x140001fb6  call    WPP_RECORDER_SF_ddd
0x140001fbb  jmp     short loc_140001F6E
0x140001fbd  mov     rcx, [rbp+57h+var_B0]
0x140001fc1  movzx   eax, byte ptr [rcx]
0x140001fc4  cmp     al, [rsi+80h]
0x140001fca  jb      short loc_14000200C
0x140001fcc  mov     ebx, 0C000000Dh
0x140001fd1  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140001fd8  jz      loc_1400024A4
0x140001fde  mov     rcx, cs:WPP_GLOBAL_Control
0x140001fe5  mov     r9d, 81h
0x140001feb  mov     [rsp+0F0h+var_C0], ebx
0x140001fef  mov     dl, 2
0x140001ff1  mov     dword ptr [rsp+0F0h+var_C8], eax
0x140001ff5  mov     [rsp+0F0h+var_D0], rdi
0x140001ffa  mov     rcx, [rcx+40h]
0x140001ffe  lea     r8d, [r9-7Eh]
0x140002002  call    WPP_RECORDER_SF_dD
0x140002007  jmp     loc_140001F6E
0x14000200c  mov     r9, [rsi+88h]
0x140002013  imul    r8, rax, 118h
0x14000201a  mov     r13, [r8+r9+18h]
0x14000201f  test    r13, r13
0x140002022  jnz     short loc_140002067
0x140002024  mov     ebx, 0C0000184h
0x140002029  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140002030  jz      loc_1400024A4
0x140002036  mov     rcx, cs:WPP_GLOBAL_Control
0x14000203d  lea     r8d, [r13+6]
0x140002041  mov     r9d, 82h
0x140002047  mov     dword ptr [rsp+0F0h+var_C8], ebx
0x14000204b  mov     dl, 2
0x14000204d  mov     [rsp+0F0h+var_D0], rdi
0x140002052  mov     rcx, [rcx+40h]
0x140002056  call    WPP_RECORDER_SF_d
0x14000205b  lea     r12, WPP_RECORDER_INITIALIZED
0x140002062  jmp     loc_140002466
0x140002067  lea     r15, [rcx+1]
0x14000206b  mov     edi, 6
0x140002070  mov     dl, [r15]
0x140002073  lea     rbx, [r15+4]
0x140002077  mov     al, dl
0x140002079  and     al, 3
0x14000207b  cmp     al, 1
0x14000207d  jnz     short loc_1400020E1
0x14000207f  movzx   r10d, byte ptr [rbx]
0x140002083  movzx   eax, byte ptr [r8+r9]
0x140002088  cmp     r10b, al
0x14000208b  jz      short loc_1400020E1
0x14000208d  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140002094  jz      short loc_1400020CB
0x140002096  mov     rcx, cs:WPP_GLOBAL_Control
0x14000209d  lea     r9d, [rdi+7Dh]
0x1400020a1  mov     [rsp+0F0h+var_C0], eax
0x1400020a5  mov     r8d, edi
0x1400020a8  lea     rax, WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids
0x1400020af  mov     dword ptr [rsp+0F0h+var_C8], r10d
0x1400020b4  mov     dl, 4
0x1400020b6  mov     [rsp+0F0h+var_D0], rax
0x1400020bb  mov     rcx, [rcx+40h]
0x1400020bf  call    WPP_RECORDER_SF_dD
0x1400020c4  mov     dl, [r15]
0x1400020c7  mov     rcx, [rbp+57h+var_B0]
0x1400020cb  movzx   eax, byte ptr [rcx]
0x1400020ce  imul    rcx, rax, 118h
0x1400020d5  mov     rax, [rsi+88h]
0x1400020dc  mov     cl, [rcx+rax]
0x1400020df  mov     [rbx], cl
0x1400020e1  and     dl, 3
0x1400020e4  cmp     dl, 2
0x1400020e7  jnz     loc_140002189
0x1400020ed  movzx   r11d, byte ptr [rbx]
0x1400020f1  mov     bl, [rsi+80h]
0x1400020f7  mov     edx, r11d
0x1400020fa  test    bl, bl
0x1400020fc  jz      short loc_140002140
0x1400020fe  mov     r12, [rsi+88h]
0x140002105  xor     r8b, r8b
0x140002108  mov     r9d, edx
0x14000210b  and     r9d, 0Fh
0x14000210f  lea     r10d, [r9+10h]
0x140002113  test    r11b, r11b
0x140002116  js      short loc_14000211B
0x140002118  mov     r10d, r9d
0x14000211b  movzx   eax, r8b
0x14000211f  imul    rcx, rax, 23h ; '#'
0x140002123  mov     eax, r10d
0x140002126  add     rcx, rax
0x140002129  cmp     qword ptr [r12+rcx*8+18h], 0
0x14000212f  jnz     short loc_140002189
0x140002131  inc     r8b
0x140002134  cmp     r8b, bl
0x140002137  jb      short loc_14000210F
0x140002139  lea     r12, WPP_RECORDER_INITIALIZED
0x140002140  mov     ebx, 0C000000Dh
0x140002145  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000214c  jz      loc_1400024A4
0x140002152  mov     rcx, cs:WPP_GLOBAL_Control
0x140002159  lea     rax, WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids
0x140002160  mov     [rsp+0F0h+var_C0], ebx
0x140002164  mov     r9d, 84h
0x14000216a  mov     dword ptr [rsp+0F0h+var_C8], edx
0x14000216e  mov     r8d, edi
0x140002171  mov     dl, 2
0x140002173  mov     [rsp+0F0h+var_D0], rax
0x140002178  mov     rcx, [rcx+40h]
0x14000217c  call    WPP_RECORDER_SF_dD
0x140002181  xor     r15d, r15d
0x140002184  jmp     loc_14000205B
0x140002189  mov     rcx, r15
0x14000218c  call    WinUSB_IsBlockedControlTransfer
0x140002191  test    al, al
0x140002193  jz      short loc_1400021A0
0x140002195  xor     r15d, r15d
0x140002198  mov     ebx, r15d
0x14000219b  jmp     loc_14000205B
0x1400021a0  lea     rcx, [r13+28h]; SpinLock
0x1400021a4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400021ab  nop     dword ptr [rax+rax+00h]
0x1400021b0  mov     r12d, [r13+18h]
0x1400021b4  lea     rcx, [r13+28h]; SpinLock
0x1400021b8  mov     dl, al; NewIrql
0x1400021ba  call    cs:__imp_KeReleaseSpinLock
0x1400021c1  nop     dword ptr [rax+rax+00h]
0x1400021c6  cmp     qword ptr [rbp+57h+var_70+8], 0
0x1400021cb  jbe     short loc_14000223B
0x1400021cd  mov     rax, cs:WdfFunctions_01015
0x1400021d4  lea     r8, [rbp+57h+var_A8]
0x1400021d8  mov     rcx, cs:WdfDriverGlobals
0x1400021df  mov     rdx, r14
0x1400021e2  mov     rax, [rax+860h]
0x1400021e9  call    _guard_dispatch_icall
0x1400021ee  mov     ebx, eax
0x1400021f0  test    eax, eax
0x1400021f2  jns     short loc_14000223B
0x1400021f4  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400021fb  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002202  jz      loc_1400024A4
0x140002208  mov     rcx, cs:WPP_GLOBAL_Control
0x14000220f  mov     r9d, 85h
0x140002215  mov     dword ptr [rsp+0F0h+var_C8], eax
0x140002219  mov     r8d, edi
0x14000221c  lea     rax, WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids
0x140002223  mov     dl, 2
0x140002225  mov     [rsp+0F0h+var_D0], rax
0x14000222a  mov     rcx, [rcx+40h]
0x14000222e  call    WPP_RECORDER_SF_d
0x140002233  xor     r15d, r15d
0x140002236  jmp     loc_140002466
0x14000223b  mov     rcx, [rbp+57h+var_A8]
0x14000223f  mov     r9, r15
0x140002242  mov     rax, cs:WdfFunctions_01015
0x140002249  mov     r8, r14
0x14000224c  mov     rdx, [rsi+8]
0x140002250  mov     [rsp+0F0h+var_C8], 0
0x140002259  mov     [rsp+0F0h+var_D0], rcx
0x14000225e  mov     rax, [rax+0A70h]
0x140002265  mov     rcx, cs:WdfDriverGlobals
0x14000226c  call    _guard_dispatch_icall
0x140002271  xor     r15d, r15d
0x140002274  mov     ebx, eax
0x140002276  test    eax, eax
0x140002278  jns     short loc_1400022BE
0x14000227a  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140002281  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002288  jz      loc_1400024A4
0x14000228e  mov     r9d, 86h
0x140002294  mov     rcx, cs:WPP_GLOBAL_Control
0x14000229b  mov     r8d, edi
0x14000229e  mov     dword ptr [rsp+0F0h+var_C8], eax
0x1400022a2  mov     dl, 2
0x1400022a4  lea     rax, WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids
0x1400022ab  mov     [rsp+0F0h+var_D0], rax
0x1400022b0  mov     rcx, [rcx+40h]
0x1400022b4  call    WPP_RECORDER_SF_d
0x1400022b9  jmp     loc_140002466
0x1400022be  mov     rax, cs:WdfFunctions_01015
0x1400022c5  lea     r8, WinUSB_ControlTransferCompletion
0x1400022cc  mov     r13, [rbp+57h+var_98]
0x1400022d0  mov     rdx, r14
0x1400022d3  mov     rcx, cs:WdfDriverGlobals
0x1400022da  mov     r9, r13
0x1400022dd  imul    r15, r12, 0FFFFFFFFFFFFD8F0h
0x1400022e4  mov     rax, [rax+820h]
0x1400022eb  call    _guard_dispatch_icall
0x1400022f0  mov     byte ptr [r13+18h], 0
0x1400022f5  test    r15, r15
0x1400022f8  jz      short loc_140002351
0x1400022fa  mov     rax, cs:WdfFunctions_01015
0x140002301  mov     rdx, r14
0x140002304  mov     rcx, cs:WdfDriverGlobals
0x14000230b  mov     dword ptr [rbp+57h+var_80], 10h
0x140002312  mov     dword ptr [rbp+57h+var_80+4], 1
0x140002319  mov     qword ptr [rbp+57h+var_80+8], r15
0x14000231d  mov     rax, [rax+830h]
0x140002324  call    _guard_dispatch_icall
0x140002329  xor     r15d, r15d
0x14000232c  mov     ebx, eax
0x14000232e  test    eax, eax
0x140002330  jns     short loc_14000235D
  ... truncated ...
```
