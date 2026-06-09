# WinUsb_GetCurrentFrameNumberAndQpcForTimeSync

- ea: `0x140007b3c`
- end: `0x140007eff`
- name: `WinUsb_GetCurrentFrameNumberAndQpcForTimeSync`
- size: `963`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1400026d0`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x1400015d8`
- `0x140006504`
- `0x140007b3c`
- `0x140010700`

## pseudocode

```c
__int64 __fastcall WinUsb_GetCurrentFrameNumberAndQpcForTimeSync(_QWORD *a1, __int64 a2, __int64 a3, _BYTE *a4)
{
  unsigned int v6; // ebx
  unsigned __int16 v7; // r9
  int v8; // edx
  int v9; // r8d
  unsigned __int16 v10; // r9
  char v11; // cl
  int v12; // r9d
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v16; // [rsp+28h] [rbp-58h]
  __int128 v17; // [rsp+50h] [rbp-30h] BYREF
  __int64 v18; // [rsp+60h] [rbp-20h]
  __int128 v19; // [rsp+68h] [rbp-18h] BYREF
  __int64 v20; // [rsp+78h] [rbp-8h]
  __int64 *v21; // [rsp+B0h] [rbp+30h] BYREF
  unsigned __int64 v22; // [rsp+B8h] [rbp+38h] BYREF
  _QWORD *v23; // [rsp+C8h] [rbp+48h] BYREF

  *a4 = 1;
  LODWORD(v20) = 0;
  v19 = 0;
  LODWORD(v18) = 0;
  v17 = 0;
  v21 = 0;
  v23 = 0;
  v22 = 0;
  if ( !a1[53] )
  {
    v6 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v7 = 67;
LABEL_4:
      WPP_RECORDER_SF_(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        2u,
        3u,
        v7,
        (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids);
      return v6;
    }
    return v6;
  }
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _QWORD **))(WdfFunctions_01015 + 2160))(
         WdfDriverGlobals,
         a3,
         60,
         &v23);
  if ( (v6 & 0x80000000) != 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v6;
    v10 = 68;
LABEL_8:
    WPP_RECORDER_SF_d(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      2u,
      3u,
      v10,
      (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
      v6);
    return v6;
  }
  v11 = v22;
  if ( v22 < 0x3C )
  {
    v6 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v6;
    v12 = 69;
LABEL_12:
    WPP_RECORDER_SF_ii(WPP_GLOBAL_Control->DeviceExtension, v8, v9, v12, (unsigned int)&v22, v11, 60);
    return v6;
  }
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64 **))(WdfFunctions_01015 + 2152))(
         WdfDriverGlobals,
         a3,
         60,
         &v21);
  if ( (v6 & 0x80000000) != 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v6;
    v10 = 70;
    goto LABEL_8;
  }
  v11 = v22;
  if ( v22 < 0x3C )
  {
    v6 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v6;
    v12 = 71;
    goto LABEL_12;
  }
  v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 336))(WdfDriverGlobals, *a1);
  if ( !v13 )
  {
    v6 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v6;
    v7 = 72;
    goto LABEL_4;
  }
  v14 = *v21;
  if ( *v21 == a1[54] )
  {
    *v21 = a1[53];
    *((_QWORD *)&v19 + 1) = v21;
    *((_QWORD *)&v17 + 1) = v23;
    *(_QWORD *)&v19 = 1;
    v20 = 60;
    *(_QWORD *)&v17 = 1;
    v18 = 60;
    v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, __int128 *, __int128 *, _QWORD, unsigned __int64 *))(WdfFunctions_01015 + 1488))(
           WdfDriverGlobals,
           v13,
           0,
           2229368,
           &v19,
           &v17,
           0,
           &v22);
    *v23 = a1[54];
    if ( (v6 & 0x80000000) == 0 )
    {
      if ( v22 == 60 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            (__int64)WPP_GLOBAL_Control->DeviceExtension,
            4u,
            3u,
            0x4Au,
            (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids);
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2200))(
          WdfDriverGlobals,
          a3,
          60);
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v16) = v6;
          WPP_RECORDER_SF_d(
            (__int64)WPP_GLOBAL_Control->DeviceExtension,
            4u,
            3u,
            0x4Bu,
            (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
            v16);
        }
        return (unsigned int)-1073741811;
      }
    }
  }
  else
  {
    v6 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_qq(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        3,
        73,
        (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
        *v21,
        a1[54]);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x140007b3c  mov     [rsp-28h+arg_8], rdx
0x140007b41  push    rbp
0x140007b42  push    rbx
0x140007b43  push    rsi
0x140007b44  push    rdi
0x140007b45  push    r14
0x140007b47  mov     rbp, rsp
0x140007b4a  sub     rsp, 80h
0x140007b51  xor     eax, eax
0x140007b53  mov     byte ptr [r9], 1
0x140007b57  xorps   xmm0, xmm0
0x140007b5a  mov     rsi, r8
0x140007b5d  mov     rdi, rcx
0x140007b60  mov     dword ptr [rbp+var_8], eax
0x140007b63  movups  [rbp+var_18], xmm0
0x140007b67  mov     dword ptr [rbp+var_20], eax
0x140007b6a  movups  [rbp+var_30], xmm0
0x140007b6e  mov     [rbp+arg_0], rax
0x140007b72  mov     [rbp+arg_18], rax
0x140007b76  mov     [rbp+arg_8], rax
0x140007b7a  cmp     [rcx+1A8h], rax
0x140007b81  jnz     short loc_140007BCB
0x140007b83  mov     ebx, 0C000000Dh
0x140007b88  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140007b8f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007b96  jz      loc_140007EEE
0x140007b9c  mov     r9d, 43h ; 'C'
0x140007ba2  mov     rcx, cs:WPP_GLOBAL_Control
0x140007ba9  lea     rax, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x140007bb0  mov     r8d, 3
0x140007bb6  mov     [rsp+80h+var_60], rax
0x140007bbb  mov     dl, 2
0x140007bbd  mov     rcx, [rcx+40h]
0x140007bc1  call    WPP_RECORDER_SF_
0x140007bc6  jmp     loc_140007EEE
0x140007bcb  mov     rax, cs:WdfFunctions_01015
0x140007bd2  lea     rcx, [rbp+arg_8]
0x140007bd6  mov     [rsp+80h+var_60], rcx
0x140007bdb  lea     r9, [rbp+arg_18]
0x140007bdf  mov     rcx, cs:WdfDriverGlobals
0x140007be6  mov     r14d, 3Ch ; '<'
0x140007bec  mov     r8d, r14d
0x140007bef  mov     rdx, rsi
0x140007bf2  mov     rax, [rax+870h]
0x140007bf9  call    _guard_dispatch_icall
0x140007bfe  mov     ebx, eax
0x140007c00  test    eax, eax
0x140007c02  jns     short loc_140007C49
0x140007c04  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140007c0b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007c12  jz      loc_140007EEE
0x140007c18  lea     r9d, [r14+8]
0x140007c1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140007c23  lea     rax, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x140007c2a  mov     dword ptr [rsp+80h+var_58], ebx
0x140007c2e  mov     r8d, 3
0x140007c34  mov     dl, 2
0x140007c36  mov     [rsp+80h+var_60], rax
0x140007c3b  mov     rcx, [rcx+40h]
0x140007c3f  call    WPP_RECORDER_SF_d
0x140007c44  jmp     loc_140007EEE
0x140007c49  mov     rcx, [rbp+arg_8]
0x140007c4d  cmp     rcx, r14
0x140007c50  jnb     short loc_140007C90
0x140007c52  mov     ebx, 0C000000Dh
0x140007c57  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140007c5e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007c65  jz      loc_140007EEE
0x140007c6b  mov     r9d, 45h ; 'E'
0x140007c71  mov     [rsp+80h+var_50], r14
0x140007c76  mov     [rsp+80h+var_58], rcx
0x140007c7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140007c82  mov     rcx, [rcx+40h]
0x140007c86  call    WPP_RECORDER_SF_ii
0x140007c8b  jmp     loc_140007EEE
0x140007c90  mov     rax, cs:WdfFunctions_01015
0x140007c97  lea     rcx, [rbp+arg_8]
0x140007c9b  mov     [rsp+80h+var_60], rcx
0x140007ca0  lea     r9, [rbp+arg_0]
0x140007ca4  mov     rcx, cs:WdfDriverGlobals
0x140007cab  mov     r8, r14
0x140007cae  mov     rdx, rsi
0x140007cb1  mov     rax, [rax+868h]
0x140007cb8  call    _guard_dispatch_icall
0x140007cbd  mov     ebx, eax
0x140007cbf  test    eax, eax
0x140007cc1  jns     short loc_140007CE2
0x140007cc3  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140007cca  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007cd1  jz      loc_140007EEE
0x140007cd7  mov     r9d, 46h ; 'F'
0x140007cdd  jmp     loc_140007C1C
0x140007ce2  mov     rcx, [rbp+arg_8]
0x140007ce6  cmp     rcx, r14
0x140007ce9  jnb     short loc_140007D0F
0x140007ceb  mov     ebx, 0C000000Dh
0x140007cf0  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140007cf7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007cfe  jz      loc_140007EEE
0x140007d04  mov     r9d, 47h ; 'G'
0x140007d0a  jmp     loc_140007C71
0x140007d0f  mov     rax, cs:WdfFunctions_01015
0x140007d16  mov     rdx, [rdi]
0x140007d19  mov     rcx, cs:WdfDriverGlobals
0x140007d20  mov     rax, [rax+150h]
0x140007d27  call    _guard_dispatch_icall
0x140007d2c  mov     r10, rax
0x140007d2f  test    rax, rax
0x140007d32  jnz     short loc_140007D56
0x140007d34  mov     ebx, 0C000000Dh
0x140007d39  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140007d40  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007d47  jz      loc_140007EEE
0x140007d4d  lea     r9d, [r10+48h]
0x140007d51  jmp     loc_140007BA2
0x140007d56  mov     r8, [rbp+arg_0]
0x140007d5a  mov     rcx, [rdi+1B0h]
0x140007d61  mov     rdx, [r8]
0x140007d64  cmp     rdx, rcx
0x140007d67  jz      short loc_140007DB9
0x140007d69  mov     ebx, 0C000000Dh
0x140007d6e  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140007d75  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007d7c  jz      loc_140007EEE
0x140007d82  mov     [rsp+80h+var_50], rcx
0x140007d87  lea     rax, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x140007d8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140007d95  mov     r9d, 49h ; 'I'
0x140007d9b  mov     [rsp+80h+var_58], rdx
0x140007da0  mov     dl, 2
0x140007da2  mov     [rsp+80h+var_60], rax
0x140007da7  mov     rcx, [rcx+40h]
0x140007dab  lea     r8d, [r9-46h]
0x140007daf  call    WPP_RECORDER_SF_qq
0x140007db4  jmp     loc_140007EEE
0x140007db9  mov     rax, [rdi+1A8h]
0x140007dc0  lea     rcx, [rbp+arg_8]
0x140007dc4  mov     [r8], rax
0x140007dc7  mov     r9d, 220478h
0x140007dcd  mov     rax, [rbp+arg_0]
0x140007dd1  xor     r8d, r8d
0x140007dd4  mov     [rsp+80h+var_48], rcx
0x140007dd9  mov     rdx, r10
0x140007ddc  mov     qword ptr [rbp+var_18+8], rax
0x140007de0  lea     rcx, [rbp+var_30]
0x140007de4  mov     rax, [rbp+arg_18]
0x140007de8  mov     qword ptr [rbp+var_30+8], rax
0x140007dec  mov     rax, cs:WdfFunctions_01015
0x140007df3  mov     [rsp+80h+var_50], 0
0x140007dfc  mov     [rsp+80h+var_58], rcx
0x140007e01  lea     rcx, [rbp+var_18]
0x140007e05  mov     qword ptr [rbp+var_18], 1
0x140007e0d  mov     [rbp+var_8], r14
0x140007e11  mov     qword ptr [rbp+var_30], 1
0x140007e19  mov     [rbp+var_20], r14
0x140007e1d  mov     rax, [rax+5D0h]
0x140007e24  mov     [rsp+80h+var_60], rcx
0x140007e29  mov     rcx, cs:WdfDriverGlobals
0x140007e30  call    _guard_dispatch_icall
0x140007e35  mov     rcx, [rdi+1B0h]
0x140007e3c  mov     ebx, eax
0x140007e3e  mov     rax, [rbp+arg_18]
0x140007e42  mov     [rax], rcx
0x140007e45  test    ebx, ebx
0x140007e47  js      loc_140007EEE
0x140007e4d  cmp     [rbp+arg_8], r14
0x140007e51  jnz     short loc_140007EAD
0x140007e53  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140007e5a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007e61  jz      short loc_140007E8B
0x140007e63  mov     rcx, cs:WPP_GLOBAL_Control
0x140007e6a  lea     rax, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x140007e71  mov     r9d, 4Ah ; 'J'
0x140007e77  mov     [rsp+80h+var_60], rax
0x140007e7c  mov     dl, 4
0x140007e7e  mov     rcx, [rcx+40h]
0x140007e82  lea     r8d, [r9-47h]
0x140007e86  call    WPP_RECORDER_SF_
0x140007e8b  mov     rax, cs:WdfFunctions_01015
0x140007e92  mov     r8, r14
0x140007e95  mov     rcx, cs:WdfDriverGlobals
0x140007e9c  mov     rdx, rsi
0x140007e9f  mov     rax, [rax+898h]
0x140007ea6  call    _guard_dispatch_icall
0x140007eab  jmp     short loc_140007EEE
0x140007ead  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140007eb4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007ebb  jz      short loc_140007EE9
0x140007ebd  mov     rcx, cs:WPP_GLOBAL_Control
0x140007ec4  lea     rax, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x140007ecb  mov     r9d, 4Bh ; 'K'
0x140007ed1  mov     dword ptr [rsp+80h+var_58], ebx
0x140007ed5  mov     dl, 4
0x140007ed7  mov     [rsp+80h+var_60], rax
0x140007edc  mov     rcx, [rcx+40h]
0x140007ee0  lea     r8d, [r9-48h]
0x140007ee4  call    WPP_RECORDER_SF_d
0x140007ee9  mov     ebx, 0C000000Dh
0x140007eee  mov     eax, ebx
0x140007ef0  add     rsp, 80h
0x140007ef7  pop     r14
0x140007ef9  pop     rdi
0x140007efa  pop     rsi
0x140007efb  pop     rbx
0x140007efc  pop     rbp
0x140007efd  retn
```
