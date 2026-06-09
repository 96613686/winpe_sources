# WinUSB_ForwardIsochRequest

- ea: `0x14000ca60`
- end: `0x14000ced1`
- name: `WinUSB_ForwardIsochRequest`
- size: `1137`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1400026d0`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x14000193c`
- `0x140001c30`
- `0x14000ca60`
- `0x140010700`

## pseudocode

```c
__int64 __fastcall WinUSB_ForwardIsochRequest(__int64 a1, __int64 a2, __int64 a3, int a4, bool *a5)
{
  int v8; // eax
  int v9; // edx
  int v10; // r8d
  int v11; // ebx
  int v12; // r9d
  unsigned int v13; // r10d
  __int64 v14; // r11
  unsigned __int16 v15; // r9
  unsigned __int8 v16; // cl
  __int64 v17; // rdi
  unsigned int v18; // ecx
  unsigned __int16 v19; // r9
  int v20; // esi
  __int64 v21; // rax
  unsigned int v22; // r8d
  unsigned int i; // edx
  __int64 v24; // rax
  __int64 v25; // rcx
  int v26; // eax
  __int64 v28; // [rsp+28h] [rbp-40h]
  char v29; // [rsp+28h] [rbp-40h]
  int v30; // [rsp+28h] [rbp-40h]
  char v31; // [rsp+30h] [rbp-38h]
  char v32; // [rsp+38h] [rbp-30h]
  __int64 v33; // [rsp+40h] [rbp-28h] BYREF
  __int64 v34; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v35[3]; // [rsp+50h] [rbp-18h] BYREF
  unsigned __int8 *v36; // [rsp+B8h] [rbp+50h] BYREF

  v36 = 0;
  v33 = 0;
  v34 = 0;
  v35[0] = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      1u,
      0x4Au,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
  v36 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      1u,
      0x4Bu,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, unsigned __int8 **, __int64 *))(WdfFunctions_01015 + 2152))(
         WdfDriverGlobals,
         a3,
         40,
         &v36,
         &v33);
  v11 = v8;
  if ( v8 >= 0 )
  {
    v13 = *((_DWORD *)v36 + 5);
    if ( !v13 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          2u,
          3u,
          0x4Du,
          (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
LABEL_14:
      v11 = -1073741789;
      goto LABEL_56;
    }
    v14 = *v36;
    if ( (unsigned __int8)v14 >= *(_BYTE *)(a1 + 128) )
    {
      v11 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_56;
      v15 = 78;
      goto LABEL_54;
    }
    v16 = (v36[1] & 0xF) + 16;
    if ( (v36[1] & 0x80u) == 0 )
      v16 = v36[1] & 0xF;
    v17 = *(_QWORD *)(*(_QWORD *)(a1 + 136) + 8 * (35 * v14 + v16) + 24);
    v18 = *(_DWORD *)(v17 + 168);
    if ( !v18 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_24:
        v11 = -1073741811;
        goto LABEL_56;
      }
      v19 = 79;
LABEL_23:
      WPP_RECORDER_SF_(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        2u,
        3u,
        v19,
        (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
      goto LABEL_24;
    }
    if ( *(_DWORD *)(v17 + 12) == 2 )
    {
      v20 = a4 - 55574646;
      if ( v20 )
      {
        if ( v20 != 4 )
        {
          v11 = -1073741637;
          goto LABEL_56;
        }
        if ( *(char *)(v17 + 8) >= 0 )
        {
          v11 = -1073741811;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_56;
          v15 = 82;
          goto LABEL_54;
        }
        if ( v13 % v18 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_dD(
              (__int64)WPP_GLOBAL_Control->DeviceExtension,
              2u,
              3u,
              0x53u,
              (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
              *((_DWORD *)v36 + 5),
              *(_DWORD *)(v17 + 168));
          goto LABEL_14;
        }
        v21 = *((unsigned int *)v36 + 8);
        if ( (unsigned int)v21 > 0x15555555 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_d(
              (__int64)WPP_GLOBAL_Control->DeviceExtension,
              2u,
              3u,
              0x54u,
              (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
              v21);
          goto LABEL_24;
        }
        v11 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64 *, _QWORD *))(WdfFunctions_01015 + 2160))(
                WdfDriverGlobals,
                a3,
                12 * v21,
                &v34,
                v35);
        if ( v11 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_56;
          v12 = 85;
          v32 = v11;
          v31 = v33;
          v9 = 12 * *((_DWORD *)v36 + 8);
          v29 = v9;
          goto LABEL_10;
        }
        v22 = *((_DWORD *)v36 + 5) / *(_DWORD *)(v17 + 168);
        if ( *((_DWORD *)v36 + 8) != v22 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_24;
          v19 = 86;
          goto LABEL_23;
        }
        for ( i = 0; i < v22; *(_DWORD *)(v34 + 4 * v25 + 8) = -1073610752 )
        {
          v24 = i++;
          v25 = 3 * v24;
          *(_DWORD *)(v34 + 4 * v25 + 4) = 0;
        }
LABEL_46:
        v26 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2248))(
                WdfDriverGlobals,
                a3,
                *(_QWORD *)(v17 + 192));
        v11 = v26;
        if ( v26 >= 0 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_56;
        v15 = 87;
        v30 = v26;
LABEL_55:
        WPP_RECORDER_SF_d(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          2u,
          3u,
          v15,
          (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
          v30);
        goto LABEL_56;
      }
      if ( *(char *)(v17 + 8) >= 0 )
        goto LABEL_46;
      v11 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_56;
      v15 = 81;
    }
    else
    {
      v11 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_56;
      v15 = 80;
    }
LABEL_54:
    v30 = -1073741811;
    goto LABEL_55;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v12 = 76;
    v32 = v8;
    v31 = v33;
    v29 = 40;
LABEL_10:
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_did(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      v10,
      v12,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
      v29,
      v31,
      v32);
  }
LABEL_56:
  *a5 = v11 < 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LODWORD(v28) = v11;
    WPP_RECORDER_SF_d(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      1u,
      0x58u,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
      v28);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14000ca60  mov     [rsp-40h+arg_8], rdx
0x14000ca65  push    rbp
0x14000ca66  push    rbx
0x14000ca67  push    rsi
0x14000ca68  push    rdi
0x14000ca69  push    r12
0x14000ca6b  push    r13
0x14000ca6d  push    r14
0x14000ca6f  push    r15
0x14000ca71  mov     rbp, rsp
0x14000ca74  sub     rsp, 68h
0x14000ca78  xor     r15d, r15d
0x14000ca7b  mov     esi, r9d
0x14000ca7e  mov     [rbp+arg_8], r15
0x14000ca82  mov     r14, r8
0x14000ca85  mov     [rbp+var_28], r15
0x14000ca89  mov     rdi, rcx
0x14000ca8c  mov     [rbp+var_20], r15
0x14000ca90  mov     [rbp+var_18], r15
0x14000ca94  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000ca9b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000caa2  lea     r13, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000caa9  jz      short loc_14000CAD1
0x14000caab  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cab2  cmp     [rcx+48h], r15w
0x14000cab7  jz      short loc_14000CAD1
0x14000cab9  mov     rcx, [rcx+40h]
0x14000cabd  lea     r9d, [r15+4Ah]
0x14000cac1  lea     r8d, [r15+1]
0x14000cac5  mov     [rsp+68h+var_48], r13
0x14000caca  mov     dl, 5
0x14000cacc  call    WPP_RECORDER_SF_
0x14000cad1  mov     [rbp+arg_8], r15
0x14000cad5  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000cadc  jz      short loc_14000CB06
0x14000cade  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cae5  cmp     [rcx+48h], r15w
0x14000caea  jz      short loc_14000CB06
0x14000caec  mov     rcx, [rcx+40h]
0x14000caf0  mov     r9d, 4Bh ; 'K'
0x14000caf6  mov     dl, 5
0x14000caf8  mov     [rsp+68h+var_48], r13
0x14000cafd  lea     r8d, [r9-4Ah]
0x14000cb01  call    WPP_RECORDER_SF_
0x14000cb06  mov     rax, cs:WdfFunctions_01015
0x14000cb0d  lea     rcx, [rbp+var_28]
0x14000cb11  mov     [rsp+68h+var_48], rcx
0x14000cb16  lea     r9, [rbp+arg_8]
0x14000cb1a  mov     rcx, cs:WdfDriverGlobals
0x14000cb21  mov     r8d, 28h ; '('
0x14000cb27  mov     rdx, r14
0x14000cb2a  mov     rax, [rax+868h]
0x14000cb31  call    _guard_dispatch_icall
0x14000cb36  mov     ebx, eax
0x14000cb38  test    eax, eax
0x14000cb3a  jns     short loc_14000CB80
0x14000cb3c  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000cb43  jz      loc_14000CE7D
0x14000cb49  mov     rcx, [rbp+var_28]
0x14000cb4d  mov     r9d, 4Ch ; 'L'
0x14000cb53  mov     dword ptr [rsp+68h+var_30], eax
0x14000cb57  mov     [rsp+68h+var_38], rcx
0x14000cb5c  mov     dword ptr [rsp+68h+var_40], 28h ; '('
0x14000cb64  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cb6b  mov     dl, 2
0x14000cb6d  mov     [rsp+68h+var_48], r13
0x14000cb72  mov     rcx, [rcx+40h]
0x14000cb76  call    WPP_RECORDER_SF_did
0x14000cb7b  jmp     loc_14000CE7D
0x14000cb80  mov     r9, [rbp+arg_8]
0x14000cb84  mov     r10d, [r9+14h]
0x14000cb88  test    r10d, r10d
0x14000cb8b  jnz     short loc_14000CBBF
0x14000cb8d  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000cb94  jz      short loc_14000CBB5
0x14000cb96  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cb9d  lea     r9d, [r10+4Dh]
0x14000cba1  lea     r8d, [r10+3]
0x14000cba5  mov     [rsp+68h+var_48], r13
0x14000cbaa  mov     dl, 2
0x14000cbac  mov     rcx, [rcx+40h]
0x14000cbb0  call    WPP_RECORDER_SF_
0x14000cbb5  mov     ebx, 0C0000023h
0x14000cbba  jmp     loc_14000CE7D
0x14000cbbf  movzx   r11d, byte ptr [r9]
0x14000cbc3  cmp     r11b, [rdi+80h]
0x14000cbca  jb      short loc_14000CBE9
0x14000cbcc  mov     ebx, 0C000000Dh
0x14000cbd1  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000cbd8  jz      loc_14000CE7D
0x14000cbde  mov     r9d, 4Eh ; 'N'
0x14000cbe4  jmp     loc_14000CE5C
0x14000cbe9  mov     r8b, [r9+1]
0x14000cbed  mov     al, r8b
0x14000cbf0  and     al, 0Fh
0x14000cbf2  movzx   edx, al
0x14000cbf5  test    r8b, r8b
0x14000cbf8  lea     eax, [rdx+10h]
0x14000cbfb  movzx   ecx, al
0x14000cbfe  mov     rax, [rdi+88h]
0x14000cc05  cmovns  ecx, edx
0x14000cc08  movzx   edx, cl
0x14000cc0b  imul    rcx, r11, 23h ; '#'
0x14000cc0f  add     rdx, rcx
0x14000cc12  mov     rdi, [rax+rdx*8+18h]
0x14000cc17  mov     ecx, [rdi+0A8h]
0x14000cc1d  test    ecx, ecx
0x14000cc1f  jnz     short loc_14000CC55
0x14000cc21  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000cc28  jz      short loc_14000CC4B
0x14000cc2a  lea     r9d, [rcx+4Fh]
0x14000cc2e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cc35  mov     r8d, 3
0x14000cc3b  mov     dl, 2
0x14000cc3d  mov     [rsp+68h+var_48], r13
0x14000cc42  mov     rcx, [rcx+40h]
0x14000cc46  call    WPP_RECORDER_SF_
0x14000cc4b  mov     ebx, 0C000000Dh
0x14000cc50  jmp     loc_14000CE7D
0x14000cc55  cmp     dword ptr [rdi+0Ch], 2
0x14000cc59  jnz     loc_14000CE48
0x14000cc5f  sub     esi, 3500076h
0x14000cc65  jz      loc_14000CE2C
0x14000cc6b  cmp     esi, 4
0x14000cc6e  jz      short loc_14000CC7A
0x14000cc70  mov     ebx, 0C00000BBh
0x14000cc75  jmp     loc_14000CE7D
0x14000cc7a  cmp     [rdi+8], r15b
0x14000cc7e  jl      short loc_14000CC9D
0x14000cc80  mov     ebx, 0C000000Dh
0x14000cc85  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000cc8c  jz      loc_14000CE7D
0x14000cc92  mov     r9d, 52h ; 'R'
0x14000cc98  jmp     loc_14000CE5C
0x14000cc9d  xor     edx, edx
0x14000cc9f  mov     eax, r10d
0x14000cca2  div     ecx
0x14000cca4  test    edx, edx
0x14000cca6  jz      short loc_14000CCE4
0x14000cca8  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000ccaf  jz      loc_14000CBB5
0x14000ccb5  mov     dword ptr [rsp+68h+var_38], ecx
0x14000ccb9  mov     r9d, 53h ; 'S'
0x14000ccbf  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ccc6  mov     dl, 2
0x14000ccc8  mov     dword ptr [rsp+68h+var_40], r10d
0x14000cccd  mov     [rsp+68h+var_48], r13
0x14000ccd2  lea     r8d, [r9-50h]
0x14000ccd6  mov     rcx, [rcx+40h]
0x14000ccda  call    WPP_RECORDER_SF_dD
0x14000ccdf  jmp     loc_14000CBB5
0x14000cce4  mov     eax, [r9+20h]
0x14000cce8  cmp     eax, 15555555h
0x14000cced  jbe     short loc_14000CD26
0x14000ccef  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000ccf6  jz      loc_14000CC4B
0x14000ccfc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cd03  mov     r9d, 54h ; 'T'
0x14000cd09  mov     dword ptr [rsp+68h+var_40], eax
0x14000cd0d  mov     dl, 2
0x14000cd0f  mov     [rsp+68h+var_48], r13
0x14000cd14  mov     rcx, [rcx+40h]
0x14000cd18  lea     r8d, [r9-51h]
0x14000cd1c  call    WPP_RECORDER_SF_d
0x14000cd21  jmp     loc_14000CC4B
0x14000cd26  lea     r8, [rax+rax*2]
0x14000cd2a  mov     rdx, r14
0x14000cd2d  mov     rax, cs:WdfFunctions_01015
0x14000cd34  lea     rcx, [rbp+var_18]
0x14000cd38  mov     [rsp+68h+var_48], rcx
0x14000cd3d  lea     r9, [rbp+var_20]
0x14000cd41  mov     rcx, cs:WdfDriverGlobals
0x14000cd48  shl     r8, 2
0x14000cd4c  mov     rax, [rax+870h]
0x14000cd53  call    _guard_dispatch_icall
0x14000cd58  mov     ebx, eax
0x14000cd5a  test    eax, eax
0x14000cd5c  jns     short loc_14000CD94
0x14000cd5e  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000cd65  jz      loc_14000CE7D
0x14000cd6b  mov     rax, [rbp+arg_8]
0x14000cd6f  mov     r9d, 55h ; 'U'
0x14000cd75  mov     dword ptr [rsp+68h+var_30], ebx
0x14000cd79  mov     ecx, [rax+20h]
0x14000cd7c  mov     rax, [rbp+var_28]
0x14000cd80  mov     [rsp+68h+var_38], rax
0x14000cd85  lea     edx, [rcx+rcx*2]
0x14000cd88  shl     edx, 2
0x14000cd8b  mov     dword ptr [rsp+68h+var_40], edx
0x14000cd8f  jmp     loc_14000CB64
0x14000cd94  mov     rcx, [rbp+arg_8]
0x14000cd98  xor     edx, edx
0x14000cd9a  mov     eax, [rcx+14h]
0x14000cd9d  div     dword ptr [rdi+0A8h]
0x14000cda3  mov     r8d, eax
0x14000cda6  cmp     [rcx+20h], eax
0x14000cda9  jz      short loc_14000CDC3
0x14000cdab  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000cdb2  jz      loc_14000CC4B
0x14000cdb8  mov     r9d, 56h ; 'V'
0x14000cdbe  jmp     loc_14000CC2E
0x14000cdc3  mov     edx, r15d
0x14000cdc6  test    r8d, r8d
0x14000cdc9  jz      short loc_14000CDED
0x14000cdcb  mov     eax, edx
0x14000cdcd  inc     edx
0x14000cdcf  lea     rcx, [rax+rax*2]
0x14000cdd3  mov     rax, [rbp+var_20]
0x14000cdd7  mov     [rax+rcx*4+4], r15d
0x14000cddc  mov     rax, [rbp+var_20]
0x14000cde0  mov     dword ptr [rax+rcx*4+8], 0C0020000h
0x14000cde8  cmp     edx, r8d
0x14000cdeb  jb      short loc_14000CDCB
0x14000cded  mov     rax, cs:WdfFunctions_01015
0x14000cdf4  mov     rdx, r14
0x14000cdf7  mov     r8, [rdi+0C0h]
0x14000cdfe  mov     rcx, cs:WdfDriverGlobals
0x14000ce05  mov     rax, [rax+8C8h]
0x14000ce0c  call    _guard_dispatch_icall
0x14000ce11  mov     ebx, eax
0x14000ce13  test    eax, eax
0x14000ce15  jns     short loc_14000CE7D
0x14000ce17  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000ce1e  jz      short loc_14000CE7D
0x14000ce20  mov     r9d, 57h ; 'W'
0x14000ce26  mov     dword ptr [rsp+68h+var_40], eax
0x14000ce2a  jmp     short loc_14000CE60
0x14000ce2c  cmp     [rdi+8], r15b
0x14000ce30  jge     short loc_14000CDED
0x14000ce32  mov     ebx, 0C000000Dh
0x14000ce37  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000ce3e  jz      short loc_14000CE7D
0x14000ce40  mov     r9d, 51h ; 'Q'
0x14000ce46  jmp     short loc_14000CE5C
0x14000ce48  mov     ebx, 0C000000Dh
0x14000ce4d  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000ce54  jz      short loc_14000CE7D
0x14000ce56  mov     r9d, 50h ; 'P'
0x14000ce5c  mov     dword ptr [rsp+68h+var_40], ebx
0x14000ce60  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ce67  mov     r8d, 3
0x14000ce6d  mov     dl, 2
0x14000ce6f  mov     [rsp+68h+var_48], r13
0x14000ce74  mov     rcx, [rcx+40h]
0x14000ce78  call    WPP_RECORDER_SF_d
0x14000ce7d  mov     rax, [rbp+arg_20]; __annotation("TMF:",
0x14000ce81  mov     ecx, ebx
0x14000ce83  shr     ecx, 1Fh
0x14000ce86  mov     [rax], cl
0x14000ce88  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000ce8f  jz      short loc_14000CEBD
0x14000ce91  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ce98  cmp     [rcx+48h], r15w
0x14000ce9d  jz      short loc_14000CEBD
0x14000ce9f  mov     rcx, [rcx+40h]
0x14000cea3  mov     r9d, 58h ; 'X'
0x14000cea9  mov     dword ptr [rsp+68h+var_40], ebx
0x14000cead  mov     dl, 5
0x14000ceaf  mov     [rsp+68h+var_48], r13
0x14000ceb4  lea     r8d, [r9-57h]
0x14000ceb8  call    WPP_RECORDER_SF_d
0x14000cebd  mov     eax, ebx
0x14000cebf  add     rsp, 68h
0x14000cec3  pop     r15
0x14000cec5  pop     r14
0x14000cec7  pop     r13
0x14000cec9  pop     r12
0x14000cecb  pop     rdi
0x14000cecc  pop     rsi
0x14000cecd  pop     rbx
0x14000cece  pop     rbp
0x14000cecf  retn
```
