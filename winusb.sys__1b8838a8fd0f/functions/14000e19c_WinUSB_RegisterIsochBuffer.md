# WinUSB_RegisterIsochBuffer

- ea: `0x14000e19c`
- end: `0x14000e62c`
- name: `WinUSB_RegisterIsochBuffer`
- size: `1168`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x14000d750`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x1400014bc`
- `0x14000193c`
- `0x140001a4c`
- `0x140001c30`
- `0x14000e19c`
- `0x140010700`
- `0x14001a464`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e472`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e52b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e472`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e52b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e4ad`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e55d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e4ad`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e55d`

## pseudocode

```c
__int64 __fastcall WinUSB_RegisterIsochBuffer(__int64 a1, __int64 a2, __int64 a3, _BYTE *a4)
{
  int v7; // eax
  int v8; // edx
  int v9; // r8d
  unsigned int v10; // ebx
  __int64 v11; // r8
  unsigned __int8 v12; // cl
  __int64 v13; // rdi
  int v14; // eax
  unsigned __int16 v15; // r9
  KSPIN_LOCK *v16; // r14
  KIRQL v17; // al
  __int64 *v18; // rdi
  __int64 v19; // rdx
  _QWORD *v20; // rcx
  unsigned int v21; // eax
  int v22; // edx
  KIRQL v23; // al
  __int64 v24; // r9
  _QWORD *v25; // r8
  __int64 v27; // [rsp+28h] [rbp-58h]
  int v28; // [rsp+28h] [rbp-58h]
  int v29; // [rsp+30h] [rbp-50h]
  __int64 v30; // [rsp+40h] [rbp-40h] BYREF
  __int128 v31; // [rsp+48h] [rbp-38h] BYREF
  __int128 v32; // [rsp+58h] [rbp-28h]
  __int128 v33; // [rsp+68h] [rbp-18h]
  __int64 *v34; // [rsp+78h] [rbp-8h]
  __int64 v35; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v36; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v37; // [rsp+D8h] [rbp+58h] BYREF

  v35 = 0;
  LODWORD(v34) = 0;
  v30 = 0;
  v37 = 0;
  v36 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      1u,
      0x19u,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
  *a4 = 1;
  v35 = 0;
  if ( !*(_DWORD *)(a1 + 404) )
  {
    *(_DWORD *)(a1 + 404) = 1;
    WinUSB_UpdateSqmInfo(a1);
  }
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64 *, __int64 *))(WdfFunctions_01015 + 2152))(
         WdfDriverGlobals,
         a3,
         16,
         &v35,
         &v30);
  v10 = v7;
  if ( v7 >= 0 )
  {
    v11 = *(unsigned __int8 *)(v35 + 8);
    if ( (unsigned __int8)v11 >= *(_BYTE *)(a1 + 128) )
    {
      v10 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v10;
      WPP_RECORDER_SF_ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        v11,
        27,
        (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
        v11,
        *(_BYTE *)(v35 + 9));
      goto LABEL_37;
    }
    v12 = (*(_BYTE *)(v35 + 9) & 0xF) + 16;
    if ( *(char *)(v35 + 9) >= 0 )
      v12 = *(_BYTE *)(v35 + 9) & 0xF;
    v13 = *(_QWORD *)(*(_QWORD *)(a1 + 136) + 8 * (35 * v11 + v12) + 24);
    if ( !v13 || *(_DWORD *)(v13 + 12) != 2 )
    {
      v10 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v10;
      v29 = -1073741811;
      v28 = *(unsigned __int8 *)(v35 + 9);
      WPP_RECORDER_SF_dD(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        2u,
        3u,
        0x1Cu,
        (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
        v28,
        v29);
      goto LABEL_37;
    }
    v14 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 2176))(
            WdfDriverGlobals,
            a3,
            &v37);
    v10 = v14;
    if ( v14 >= 0 )
    {
      *(_QWORD *)&v32 = 0;
      *((_QWORD *)&v32 + 1) = 0x100000001LL;
      v34 = off_140015018;
      v31 = 0;
      LODWORD(v31) = 56;
      v33 = 0;
      v14 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *, __int64 *))(WdfFunctions_01015 + 1624))(
              WdfDriverGlobals,
              a3,
              &v31,
              &v36);
      v10 = v14;
      if ( v14 >= 0 )
      {
        v16 = (KSPIN_LOCK *)(v13 + 216);
        *(_QWORD *)(v36 + 8) = *(_QWORD *)v35;
        *(_QWORD *)(v36 + 16) = *(_QWORD *)(v37 + 32) + *(unsigned int *)(v37 + 44);
        *(_DWORD *)(v36 + 24) = *(_DWORD *)(v37 + 40);
        *(_QWORD *)(v36 + 32) = v37;
        *(_QWORD *)v36 = v13;
        v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v13 + 216));
        v18 = (__int64 *)(v13 + 176);
        v19 = *v18;
        if ( *(__int64 **)(*v18 + 8) != v18 )
          goto LABEL_34;
        v20 = (_QWORD *)(v36 + 48);
        *(_QWORD *)(v36 + 56) = v18;
        *v20 = v19;
        *(_QWORD *)(v19 + 8) = v20;
        *v18 = (__int64)v20;
        KeReleaseSpinLock(v16, v17);
        v21 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 (__fastcall *)()))(WdfFunctions_01015
                                                                                                + 3144))(
                WdfDriverGlobals,
                a3,
                WinUSB_RegisterIsochBufferCancel);
        v10 = v21;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(v22) = 5;
          WPP_RECORDER_SF_qd(
            WPP_GLOBAL_Control->DeviceExtension,
            v22,
            3,
            31,
            (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
            v36,
            v21);
        }
        if ( (v10 & 0x80000000) == 0 )
        {
          *a4 = 0;
          goto LABEL_37;
        }
        v23 = KeAcquireSpinLockRaiseToDpc(v16);
        v24 = *(_QWORD *)(v36 + 48);
        if ( *(_QWORD *)(v24 + 8) != v36 + 48 || (v25 = *(_QWORD **)(v36 + 56), *v25 != v36 + 48) )
LABEL_34:
          __fastfail(3u);
        *v25 = v24;
        *(_QWORD *)(v24 + 8) = v25;
        KeReleaseSpinLock(v16, v23);
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return v10;
        v15 = 32;
        LODWORD(v27) = v10;
        goto LABEL_20;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v10;
      v15 = 30;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v10;
      v15 = 29;
    }
    LODWORD(v27) = v14;
LABEL_20:
    WPP_RECORDER_SF_d(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      2u,
      3u,
      v15,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
      v27);
    goto LABEL_37;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return v10;
  LOBYTE(v8) = 2;
  WPP_RECORDER_SF_did(
    WPP_GLOBAL_Control->DeviceExtension,
    v8,
    v9,
    26,
    (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
    16,
    v30,
    v7);
LABEL_37:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LODWORD(v27) = v10;
    WPP_RECORDER_SF_d(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      1u,
      0x21u,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
      v27);
  }
  return v10;
}

```

## disassembly

```asm
0x14000e19c  mov     [rsp-38h+arg_10], rbx
0x14000e1a1  mov     [rsp-38h+arg_8], rdx
0x14000e1a6  push    rbp
0x14000e1a7  push    rsi
0x14000e1a8  push    rdi
0x14000e1a9  push    r12
0x14000e1ab  push    r13
0x14000e1ad  push    r14
0x14000e1af  push    r15
0x14000e1b1  mov     rbp, rsp
0x14000e1b4  sub     rsp, 80h
0x14000e1bb  xor     r12d, r12d
0x14000e1be  xorps   xmm0, xmm0
0x14000e1c1  xor     eax, eax
0x14000e1c3  mov     [rbp+arg_0], r12
0x14000e1c7  mov     dword ptr [rbp+var_8], eax
0x14000e1ca  mov     r15, r9
0x14000e1cd  mov     rsi, r8
0x14000e1d0  mov     [rbp+var_40], r12
0x14000e1d4  mov     rdi, rcx
0x14000e1d7  mov     [rbp+arg_18], r12
0x14000e1db  mov     [rbp+arg_8], r12
0x14000e1df  movups  [rbp+var_38], xmm0
0x14000e1e3  movups  [rbp+var_28], xmm0
0x14000e1e7  movups  [rbp+var_18], xmm0
0x14000e1eb  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000e1f2  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000e1f9  lea     r14, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000e200  lea     ebx, [rax+1]
0x14000e203  jz      short loc_14000E22B
0x14000e205  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e20c  cmp     [rcx+48h], r12w
0x14000e211  jz      short loc_14000E22B
0x14000e213  mov     rcx, [rcx+40h]
0x14000e217  lea     r9d, [r12+19h]
0x14000e21c  mov     r8d, ebx
0x14000e21f  mov     [rsp+80h+var_60], r14
0x14000e224  mov     dl, 5
0x14000e226  call    WPP_RECORDER_SF_
0x14000e22b  mov     [r15], bl
0x14000e22e  mov     [rbp+arg_0], r12
0x14000e232  cmp     [rdi+194h], r12d
0x14000e239  jnz     short loc_14000E249
0x14000e23b  mov     rcx, rdi
0x14000e23e  mov     [rdi+194h], ebx
0x14000e244  call    WinUSB_UpdateSqmInfo
0x14000e249  mov     rax, cs:WdfFunctions_01015
0x14000e250  lea     rcx, [rbp+var_40]
0x14000e254  mov     [rsp+80h+var_60], rcx
0x14000e259  lea     r9, [rbp+arg_0]
0x14000e25d  mov     rcx, cs:WdfDriverGlobals
0x14000e264  mov     r8d, 10h
0x14000e26a  mov     rdx, rsi
0x14000e26d  mov     rax, [rax+868h]
0x14000e274  call    _guard_dispatch_icall
0x14000e279  mov     ebx, eax
0x14000e27b  test    eax, eax
0x14000e27d  jns     short loc_14000E2C3
0x14000e27f  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14000e286  jz      loc_14000E60E
0x14000e28c  mov     rcx, [rbp+var_40]
0x14000e290  mov     r9d, 1Ah
0x14000e296  mov     [rsp+80h+var_48], eax
0x14000e29a  mov     dl, 2
0x14000e29c  mov     [rsp+80h+var_50], rcx
0x14000e2a1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e2a8  mov     dword ptr [rsp+80h+var_58], 10h
0x14000e2b0  mov     [rsp+80h+var_60], r14
0x14000e2b5  mov     rcx, [rcx+40h]
0x14000e2b9  call    WPP_RECORDER_SF_did
0x14000e2be  jmp     loc_14000E5D9
0x14000e2c3  mov     rax, [rbp+arg_0]
0x14000e2c7  movzx   r8d, byte ptr [rax+8]
0x14000e2cc  cmp     r8b, [rdi+80h]
0x14000e2d3  jb      short loc_14000E314
0x14000e2d5  mov     ebx, 0C000000Dh
0x14000e2da  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14000e2e1  jz      loc_14000E60E
0x14000e2e7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e2ee  mov     r9d, 1Bh
0x14000e2f4  movzx   eax, byte ptr [rax+9]
0x14000e2f8  mov     dword ptr [rsp+80h+var_50], eax
0x14000e2fc  mov     dword ptr [rsp+80h+var_58], r8d
0x14000e301  mov     rcx, [rcx+40h]
0x14000e305  mov     [rsp+80h+var_60], r14
0x14000e30a  call    WPP_RECORDER_SF_ddd
0x14000e30f  jmp     loc_14000E5D9
0x14000e314  movzx   r9d, byte ptr [rax+9]
0x14000e319  mov     al, r9b
0x14000e31c  and     al, 0Fh
0x14000e31e  movzx   edx, al
0x14000e321  test    r9b, r9b
0x14000e324  lea     eax, [rdx+10h]
0x14000e327  movzx   ecx, al
0x14000e32a  mov     rax, [rdi+88h]
0x14000e331  cmovns  ecx, edx
0x14000e334  movzx   edx, cl
0x14000e337  imul    rcx, r8, 23h ; '#'
0x14000e33b  add     rdx, rcx
0x14000e33e  mov     rdi, [rax+rdx*8+18h]
0x14000e343  test    rdi, rdi
0x14000e346  jz      loc_14000E59F
0x14000e34c  cmp     dword ptr [rdi+0Ch], 2
0x14000e350  jnz     loc_14000E59F
0x14000e356  mov     rax, cs:WdfFunctions_01015
0x14000e35d  lea     r8, [rbp+arg_18]
0x14000e361  mov     rcx, cs:WdfDriverGlobals
0x14000e368  mov     rdx, rsi
0x14000e36b  mov     rax, [rax+880h]
0x14000e372  call    _guard_dispatch_icall
0x14000e377  mov     ebx, eax
0x14000e379  test    eax, eax
0x14000e37b  jns     short loc_14000E3B6
0x14000e37d  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14000e384  jz      loc_14000E60E
0x14000e38a  mov     r9d, 1Dh
0x14000e390  mov     dword ptr [rsp+80h+var_58], eax
0x14000e394  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e39b  mov     r8d, 3
0x14000e3a1  mov     dl, 2
0x14000e3a3  mov     [rsp+80h+var_60], r14
0x14000e3a8  mov     rcx, [rcx+40h]
0x14000e3ac  call    WPP_RECORDER_SF_d
0x14000e3b1  jmp     loc_14000E5D9
0x14000e3b6  mov     rcx, cs:WdfDriverGlobals
0x14000e3bd  lea     r9, [rbp+arg_8]
0x14000e3c1  xorps   xmm0, xmm0
0x14000e3c4  lea     r8, [rbp+var_38]
0x14000e3c8  movups  [rbp+var_28], xmm0
0x14000e3cc  mov     eax, 1
0x14000e3d1  mov     rdx, rsi
0x14000e3d4  mov     dword ptr [rbp+var_28+8], eax
0x14000e3d7  mov     dword ptr [rbp+var_28+0Ch], eax
0x14000e3da  mov     rax, cs:off_140015018
0x14000e3e1  mov     [rbp+var_8], rax
0x14000e3e5  mov     rax, cs:WdfFunctions_01015
0x14000e3ec  movups  [rbp+var_38], xmm0
0x14000e3f0  mov     dword ptr [rbp+var_38], 38h ; '8'
0x14000e3f7  movups  [rbp+var_18], xmm0
0x14000e3fb  mov     rax, [rax+658h]
0x14000e402  call    _guard_dispatch_icall
0x14000e407  mov     ebx, eax
0x14000e409  test    eax, eax
0x14000e40b  jns     short loc_14000E425
0x14000e40d  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14000e414  jz      loc_14000E60E
0x14000e41a  mov     r9d, 1Eh
0x14000e420  jmp     loc_14000E390
0x14000e425  mov     rax, [rbp+arg_0]
0x14000e429  lea     r14, [rdi+0D8h]
0x14000e430  mov     rcx, [rax]
0x14000e433  mov     rax, [rbp+arg_8]
0x14000e437  mov     [rax+8], rcx
0x14000e43b  mov     rax, [rbp+arg_18]
0x14000e43f  mov     ecx, [rax+2Ch]
0x14000e442  add     rcx, [rax+20h]
0x14000e446  mov     rax, [rbp+arg_8]
0x14000e44a  mov     [rax+10h], rcx
0x14000e44e  mov     rax, [rbp+arg_18]
0x14000e452  mov     ecx, [rax+28h]
0x14000e455  mov     rax, [rbp+arg_8]
0x14000e459  mov     [rax+18h], ecx
0x14000e45c  mov     rax, [rbp+arg_8]
0x14000e460  mov     rcx, [rbp+arg_18]
0x14000e464  mov     [rax+20h], rcx
0x14000e468  mov     rcx, r14; SpinLock
0x14000e46b  mov     rax, [rbp+arg_8]
0x14000e46f  mov     [rax], rdi
0x14000e472  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e479  nop     dword ptr [rax+rax+00h]
0x14000e47e  add     rdi, 0B0h
0x14000e485  mov     rdx, [rdi]
0x14000e488  cmp     [rdx+8], rdi
0x14000e48c  jnz     loc_14000E598
0x14000e492  mov     rcx, [rbp+arg_8]
0x14000e496  add     rcx, 30h ; '0'
0x14000e49a  mov     [rcx+8], rdi
0x14000e49e  mov     [rcx], rdx
0x14000e4a1  mov     [rdx+8], rcx
0x14000e4a5  mov     dl, al; NewIrql
0x14000e4a7  mov     [rdi], rcx
0x14000e4aa  mov     rcx, r14; SpinLock
0x14000e4ad  call    cs:__imp_KeReleaseSpinLock
0x14000e4b4  nop     dword ptr [rax+rax+00h]
0x14000e4b9  mov     rax, cs:WdfFunctions_01015
0x14000e4c0  lea     r8, WinUSB_RegisterIsochBufferCancel
0x14000e4c7  mov     rcx, cs:WdfDriverGlobals
0x14000e4ce  mov     rdx, rsi
0x14000e4d1  mov     rax, [rax+0C48h]
0x14000e4d8  call    _guard_dispatch_icall
0x14000e4dd  mov     ebx, eax
0x14000e4df  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14000e4e6  jz      short loc_14000E524
0x14000e4e8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e4ef  cmp     [rcx+48h], r12w
0x14000e4f4  jz      short loc_14000E524
0x14000e4f6  mov     rcx, [rcx+40h]
0x14000e4fa  mov     r9d, 1Fh
0x14000e500  mov     dword ptr [rsp+80h+var_50], eax
0x14000e504  mov     dl, 5
0x14000e506  mov     rax, [rbp+arg_8]
0x14000e50a  mov     [rsp+80h+var_58], rax
0x14000e50f  lea     rax, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000e516  lea     r8d, [r9-1Ch]
0x14000e51a  mov     [rsp+80h+var_60], rax
0x14000e51f  call    WPP_RECORDER_SF_qd
0x14000e524  test    ebx, ebx
0x14000e526  jns     short loc_14000E58C
0x14000e528  mov     rcx, r14; SpinLock
0x14000e52b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e532  nop     dword ptr [rax+rax+00h]
0x14000e537  mov     rdx, [rbp+arg_8]
0x14000e53b  add     rdx, 30h ; '0'
0x14000e53f  mov     r9, [rdx]
0x14000e542  cmp     [r9+8], rdx
0x14000e546  jnz     short loc_14000E598
0x14000e548  mov     r8, [rdx+8]
0x14000e54c  cmp     [r8], rdx
0x14000e54f  jnz     short loc_14000E598
0x14000e551  mov     [r8], r9
0x14000e554  mov     dl, al; NewIrql
0x14000e556  mov     rcx, r14; SpinLock
0x14000e559  mov     [r9+8], r8
0x14000e55d  call    cs:__imp_KeReleaseSpinLock
0x14000e564  nop     dword ptr [rax+rax+00h]
0x14000e569  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14000e570  jz      loc_14000E60E
0x14000e576  mov     r9d, 20h ; ' '
0x14000e57c  mov     dword ptr [rsp+80h+var_58], ebx
0x14000e580  lea     r14, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000e587  jmp     loc_14000E394
0x14000e58c  mov     [r15], r12b
0x14000e58f  lea     r14, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000e596  jmp     short loc_14000E5D9
0x14000e598  mov     ecx, 3
0x14000e59d  int     29h; Win8: RtlFailFast(ecx)
0x14000e59f  mov     ebx, 0C000000Dh
0x14000e5a4  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14000e5ab  jz      short loc_14000E60E
0x14000e5ad  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e5b4  mov     eax, r9d
0x14000e5b7  mov     r9d, 1Ch
0x14000e5bd  mov     dword ptr [rsp+80h+var_50], ebx
0x14000e5c1  mov     dword ptr [rsp+80h+var_58], eax
0x14000e5c5  mov     dl, 2
0x14000e5c7  mov     [rsp+80h+var_60], r14
0x14000e5cc  mov     rcx, [rcx+40h]
0x14000e5d0  lea     r8d, [r9-19h]
0x14000e5d4  call    WPP_RECORDER_SF_dD
0x14000e5d9  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14000e5e0  jz      short loc_14000E60E
0x14000e5e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e5e9  cmp     [rcx+48h], r12w
0x14000e5ee  jz      short loc_14000E60E
0x14000e5f0  mov     rcx, [rcx+40h]
0x14000e5f4  mov     r9d, 21h ; '!'
0x14000e5fa  mov     dword ptr [rsp+80h+var_58], ebx
0x14000e5fe  mov     dl, 5
0x14000e600  mov     [rsp+80h+var_60], r14
0x14000e605  lea     r8d, [r9-20h]
0x14000e609  call    WPP_RECORDER_SF_d
0x14000e60e  mov     eax, ebx
0x14000e610  mov     rbx, [rsp+80h+arg_10]
0x14000e618  add     rsp, 80h
0x14000e61f  pop     r15
0x14000e621  pop     r14
0x14000e623  pop     r13
0x14000e625  pop     r12
0x14000e627  pop     rdi
0x14000e628  pop     rsi
0x14000e629  pop     rbp
0x14000e62a  retn
```
