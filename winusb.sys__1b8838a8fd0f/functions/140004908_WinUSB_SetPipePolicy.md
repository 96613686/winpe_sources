# WinUSB_SetPipePolicy

- ea: `0x140004908`
- end: `0x140004e9c`
- name: `WinUSB_SetPipePolicy`
- size: `1428`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1400026d0`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x14000193c`
- `0x140001c30`
- `0x140001d24`
- `0x140004908`
- `0x140010700`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004a9a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004a9a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004e40`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004e40`

## pseudocode

```c
__int64 __fastcall WinUSB_SetPipePolicy(__int64 a1, __int64 a2, __int64 a3, _BYTE *a4)
{
  __int64 v7; // rax
  PWDF_DRIVER_GLOBALS v8; // rcx
  int v9; // eax
  __int64 v10; // rdx
  int v11; // r8d
  unsigned int v12; // edi
  int v13; // edx
  __int64 v14; // r8
  int v15; // r9d
  __int64 v16; // rdx
  __int64 v17; // rbx
  KIRQL v18; // al
  int v19; // edx
  KIRQL v20; // r14
  int v21; // r8d
  int v22; // r9d
  int v23; // ecx
  char v24; // al
  int v25; // r9d
  unsigned __int8 v26; // cl
  char v28; // [rsp+28h] [rbp-18h]
  char v29; // [rsp+28h] [rbp-18h]
  unsigned __int64 v30; // [rsp+88h] [rbp+48h] BYREF
  char *v31; // [rsp+98h] [rbp+58h] BYREF

  v31 = 0;
  v30 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      76,
      (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids);
  v7 = WdfFunctions_01015;
  v8 = WdfDriverGlobals;
  *a4 = 1;
  v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, char **))(v7 + 2152))(v8, a3, 12, &v31);
  v12 = v9;
  if ( v9 >= 0 )
  {
    v14 = (unsigned __int8)*v31;
    if ( (unsigned __int8)v14 >= *(_BYTE *)(a1 + 128) )
    {
      v12 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v12;
      v15 = 78;
      v28 = *v31;
      goto LABEL_10;
    }
    v16 = (v31[1] & 0xF) + 16LL;
    if ( v31[1] >= 0 )
      v16 = v31[1] & 0xF;
    v10 = 35 * v14 + v16;
    v17 = *(_QWORD *)(*(_QWORD *)(a1 + 136) + 8 * v10 + 24);
    if ( !v17 )
    {
      v12 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v12;
      v15 = 79;
      v28 = v31[1];
LABEL_10:
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_dD(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        3,
        v15,
        (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
        v28,
        13);
      goto LABEL_88;
    }
    v18 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v17 + 40));
    v19 = (int)v31;
    v20 = v18;
    v21 = *((_DWORD *)v31 + 1);
    if ( v21 == 1 )
    {
      v24 = v30;
      if ( v30 < 0xD )
      {
        v12 = -1073741811;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_87;
        v25 = 80;
        goto LABEL_34;
      }
      v23 = *(_DWORD *)(v17 + 12);
      if ( (unsigned int)(v23 - 3) <= 1 )
      {
        *(_BYTE *)(v17 + 20) = v31[12] != 0;
        goto LABEL_87;
      }
      v12 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_87;
      v22 = 81;
      goto LABEL_30;
    }
    if ( *((_DWORD *)v31 + 1) == 2 )
    {
      v23 = *(_DWORD *)(v17 + 12);
      if ( (unsigned int)(v23 - 3) <= 1 )
      {
        v24 = v30;
        if ( v30 >= 0xD )
        {
          *(_BYTE *)(v17 + 21) = v31[12] != 0;
          goto LABEL_87;
        }
        v12 = -1073741811;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_87;
        v25 = 83;
        goto LABEL_34;
      }
      v12 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_87;
      v22 = 82;
      goto LABEL_30;
    }
    if ( *((_DWORD *)v31 + 1) == 3 )
    {
      if ( *(_DWORD *)(v17 + 12) == 2 )
      {
        v12 = -1073741811;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_87;
        v22 = 84;
        v29 = 2;
        goto LABEL_26;
      }
      v24 = v30;
      if ( v30 >= 0x10 )
      {
        *(_DWORD *)(v17 + 24) = *((_DWORD *)v31 + 3);
        goto LABEL_87;
      }
      v12 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_87;
      v25 = 85;
      goto LABEL_34;
    }
    if ( *((_DWORD *)v31 + 1) != 4 )
    {
      switch ( *((_DWORD *)v31 + 1) )
      {
        case 5:
          v23 = *(_DWORD *)(v17 + 12);
          if ( (unsigned int)(v23 - 3) > 1 )
          {
            v12 = -1073741811;
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_87;
            v22 = 88;
            goto LABEL_30;
          }
          v24 = v30;
          if ( v30 < 0xD )
          {
            v12 = -1073741811;
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_87;
            v25 = 89;
            goto LABEL_34;
          }
          v26 = v31[12];
          *(_BYTE *)(v17 + 29) = v26 != 0;
          break;
        case 6:
          v23 = *(_DWORD *)(v17 + 12);
          if ( (unsigned int)(v23 - 3) > 1 )
          {
            v12 = -1073741811;
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_87;
            v22 = 90;
            goto LABEL_30;
          }
          v24 = v30;
          if ( v30 < 0xD )
          {
            v12 = -1073741811;
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_87;
            v25 = 91;
            goto LABEL_34;
          }
          v26 = v31[12];
          *(_BYTE *)(v17 + 30) = v26 != 0;
          break;
        case 7:
          v23 = *(_DWORD *)(v17 + 12);
          if ( (unsigned int)(v23 - 3) <= 1 )
          {
            v24 = v30;
            if ( v30 >= 0xD )
            {
              *(_BYTE *)(v17 + 31) = v31[12] != 0;
              goto LABEL_87;
            }
            v12 = -1073741811;
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_87;
            v25 = 93;
            goto LABEL_34;
          }
          v12 = -1073741811;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_87;
          v22 = 92;
LABEL_30:
          v29 = v23;
          goto LABEL_26;
        case 9:
          v23 = *(_DWORD *)(v17 + 12);
          if ( (unsigned int)(v23 - 3) > 1 )
          {
            v12 = -1073741811;
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_87;
            v22 = 94;
            goto LABEL_30;
          }
          v24 = v30;
          if ( v30 >= 0xD )
          {
            *(_BYTE *)(v17 + 32) = v31[12] != 0;
            goto LABEL_87;
          }
          v12 = -1073741811;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_87;
          v25 = 95;
LABEL_34:
          WPP_RECORDER_SF_id(WPP_GLOBAL_Control->DeviceExtension, (_DWORD)v31, v21, v25, (unsigned int)&v30, v24);
          goto LABEL_87;
        default:
          v12 = -1073741811;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v22 = 96;
            v29 = v21;
LABEL_26:
            LOBYTE(v19) = 2;
            WPP_RECORDER_SF_dD(
              WPP_GLOBAL_Control->DeviceExtension,
              v19,
              3,
              v22,
              (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
              v29,
              13);
          }
LABEL_87:
          KeReleaseSpinLock((PKSPIN_LOCK)(v17 + 40), v20);
          goto LABEL_88;
      }
      if ( !v26 )
        *(_BYTE *)(v17 + 64) = 0;
      goto LABEL_87;
    }
    v23 = *(_DWORD *)(v17 + 12);
    if ( (unsigned int)(v23 - 3) <= 1 )
    {
      v24 = v30;
      if ( v30 >= 0xD )
      {
        *(_BYTE *)(v17 + 28) = v31[12] != 0;
        goto LABEL_87;
      }
      v12 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_87;
      v25 = 87;
      goto LABEL_34;
    }
    v12 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_87;
    v22 = 86;
    goto LABEL_30;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return v12;
  LOBYTE(v10) = 2;
  WPP_RECORDER_SF_did(
    WPP_GLOBAL_Control->DeviceExtension,
    v10,
    v11,
    77,
    (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
    12,
    v30,
    v9);
LABEL_88:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v13) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      1,
      97,
      (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
      v12);
  }
  return v12;
}

```

## disassembly

```asm
0x140004908  mov     [rsp-38h+arg_0], rbx
0x14000490d  mov     [rsp-38h+arg_8], rdx
0x140004912  push    rbp
0x140004913  push    rsi
0x140004914  push    rdi
0x140004915  push    r12
0x140004917  push    r13
0x140004919  push    r14
0x14000491b  push    r15
0x14000491d  mov     rbp, rsp
0x140004920  sub     rsp, 40h
0x140004924  xor     r12d, r12d
0x140004927  mov     rdi, r9
0x14000492a  mov     [rbp+arg_18], r12
0x14000492e  mov     rsi, r8
0x140004931  mov     [rbp+arg_8], r12
0x140004935  mov     rbx, rcx
0x140004938  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000493f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140004946  lea     r13, WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids
0x14000494d  jz      short loc_140004977
0x14000494f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004956  cmp     [rcx+48h], r12w
0x14000495b  jz      short loc_140004977
0x14000495d  mov     rcx, [rcx+40h]
0x140004961  lea     r9d, [r12+4Ch]
0x140004966  lea     r8d, [r12+1]
0x14000496b  mov     [rsp+40h+var_20], r13
0x140004970  mov     dl, 5
0x140004972  call    WPP_RECORDER_SF_
0x140004977  mov     rax, cs:WdfFunctions_01015
0x14000497e  lea     rcx, [rbp+arg_8]
0x140004982  mov     [rsp+40h+var_20], rcx
0x140004987  lea     r9, [rbp+arg_18]
0x14000498b  mov     rcx, cs:WdfDriverGlobals
0x140004992  mov     r14d, 0Ch
0x140004998  mov     r8d, r14d
0x14000499b  mov     byte ptr [rdi], 1
0x14000499e  mov     rax, [rax+868h]
0x1400049a5  mov     rdx, rsi
0x1400049a8  call    _guard_dispatch_icall
0x1400049ad  mov     edi, eax
0x1400049af  test    eax, eax
0x1400049b1  jns     short loc_1400049F2
0x1400049b3  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400049ba  jz      loc_140004E81
0x1400049c0  mov     rcx, [rbp+arg_8]
0x1400049c4  lea     r9d, [r14+41h]
0x1400049c8  mov     [rsp+40h+var_8], eax
0x1400049cc  mov     dl, 2
0x1400049ce  mov     [rsp+40h+var_10], rcx
0x1400049d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400049da  mov     dword ptr [rsp+40h+var_18], r14d
0x1400049df  mov     [rsp+40h+var_20], r13
0x1400049e4  mov     rcx, [rcx+40h]
0x1400049e8  call    WPP_RECORDER_SF_did
0x1400049ed  jmp     loc_140004E4C
0x1400049f2  mov     rax, [rbp+arg_18]
0x1400049f6  movzx   r8d, byte ptr [rax]
0x1400049fa  cmp     r8b, [rbx+80h]
0x140004a01  jb      short loc_140004A46
0x140004a03  mov     edi, 0C000000Dh
0x140004a08  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140004a0f  jz      loc_140004E81
0x140004a15  mov     dword ptr [rsp+40h+var_10], edi
0x140004a19  mov     r9d, 4Eh ; 'N'
0x140004a1f  mov     dword ptr [rsp+40h+var_18], r8d
0x140004a24  mov     rcx, cs:WPP_GLOBAL_Control
0x140004a2b  mov     r8d, 3
0x140004a31  mov     dl, 2
0x140004a33  mov     [rsp+40h+var_20], r13
0x140004a38  mov     rcx, [rcx+40h]
0x140004a3c  call    WPP_RECORDER_SF_dD
0x140004a41  jmp     loc_140004E4C
0x140004a46  movzx   ecx, byte ptr [rax+1]
0x140004a4a  mov     r10d, ecx
0x140004a4d  mov     eax, r10d
0x140004a50  and     eax, 0Fh
0x140004a53  test    cl, cl
0x140004a55  lea     rdx, [rax+10h]
0x140004a59  cmovns  rdx, rax
0x140004a5d  mov     rax, [rbx+88h]
0x140004a64  imul    rcx, r8, 23h ; '#'
0x140004a68  add     rdx, rcx
0x140004a6b  mov     rbx, [rax+rdx*8+18h]
0x140004a70  test    rbx, rbx
0x140004a73  jnz     short loc_140004A96
0x140004a75  mov     edi, 0C000000Dh
0x140004a7a  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140004a81  jz      loc_140004E81
0x140004a87  mov     dword ptr [rsp+40h+var_10], edi
0x140004a8b  lea     r9d, [rbx+4Fh]
0x140004a8f  mov     dword ptr [rsp+40h+var_18], r10d
0x140004a94  jmp     short loc_140004A24
0x140004a96  lea     rcx, [rbx+28h]; SpinLock
0x140004a9a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004aa1  nop     dword ptr [rax+rax+00h]
0x140004aa6  mov     rdx, [rbp+arg_18]
0x140004aaa  mov     r14b, al
0x140004aad  mov     r8d, [rdx+4]
0x140004ab1  mov     ecx, r8d
0x140004ab4  sub     ecx, 1
0x140004ab7  jz      loc_140004DE8
0x140004abd  sub     ecx, 1
0x140004ac0  jz      loc_140004D91
0x140004ac6  sub     ecx, 1
0x140004ac9  jz      loc_140004D30
0x140004acf  sub     ecx, 1
0x140004ad2  jz      loc_140004CD2
0x140004ad8  sub     ecx, 1
0x140004adb  jz      loc_140004C76
0x140004ae1  sub     ecx, 1
0x140004ae4  jz      loc_140004C0B
0x140004aea  sub     ecx, 1
0x140004aed  jz      loc_140004BB3
0x140004af3  cmp     ecx, 2
0x140004af6  jz      short loc_140004B3B
0x140004af8  mov     edi, 0C000000Dh
0x140004afd  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140004b04  jz      loc_140004E39
0x140004b0a  mov     dword ptr [rsp+40h+var_10], edi
0x140004b0e  mov     r9d, 60h ; '`'
0x140004b14  mov     dword ptr [rsp+40h+var_18], r8d
0x140004b19  mov     rcx, cs:WPP_GLOBAL_Control
0x140004b20  mov     r8d, 3
0x140004b26  mov     dl, 2
0x140004b28  mov     [rsp+40h+var_20], r13
0x140004b2d  mov     rcx, [rcx+40h]
0x140004b31  call    WPP_RECORDER_SF_dD
0x140004b36  jmp     loc_140004E39
0x140004b3b  mov     ecx, [rbx+0Ch]
0x140004b3e  lea     eax, [rcx-3]
0x140004b41  cmp     eax, 1
0x140004b44  jbe     short loc_140004B68
0x140004b46  mov     edi, 0C000000Dh
0x140004b4b  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140004b52  jz      loc_140004E39
0x140004b58  mov     r9d, 5Eh ; '^'
0x140004b5e  mov     dword ptr [rsp+40h+var_10], edi
0x140004b62  mov     dword ptr [rsp+40h+var_18], ecx
0x140004b66  jmp     short loc_140004B19
0x140004b68  mov     rax, [rbp+arg_8]
0x140004b6c  cmp     rax, 0Dh
0x140004b70  jnb     short loc_140004BA4
0x140004b72  mov     edi, 0C000000Dh
0x140004b77  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140004b7e  jz      loc_140004E39
0x140004b84  mov     r9d, 5Fh ; '_'
0x140004b8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004b91  mov     [rsp+40h+var_18], rax
0x140004b96  mov     rcx, [rcx+40h]
0x140004b9a  call    WPP_RECORDER_SF_id
0x140004b9f  jmp     loc_140004E39
0x140004ba4  cmp     [rdx+0Ch], r12b
0x140004ba8  setnz   al
0x140004bab  mov     [rbx+20h], al
0x140004bae  jmp     loc_140004E39
0x140004bb3  mov     ecx, [rbx+0Ch]
0x140004bb6  lea     eax, [rcx-3]
0x140004bb9  cmp     eax, 1
0x140004bbc  jbe     short loc_140004BD8
0x140004bbe  mov     edi, 0C000000Dh
0x140004bc3  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140004bca  jz      loc_140004E39
0x140004bd0  mov     r9d, 5Ch ; '\'
0x140004bd6  jmp     short loc_140004B5E
0x140004bd8  mov     rax, [rbp+arg_8]
0x140004bdc  cmp     rax, 0Dh
0x140004be0  jnb     short loc_140004BFC
0x140004be2  mov     edi, 0C000000Dh
0x140004be7  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140004bee  jz      loc_140004E39
0x140004bf4  mov     r9d, 5Dh ; ']'
0x140004bfa  jmp     short loc_140004B8A
0x140004bfc  cmp     [rdx+0Ch], r12b
0x140004c00  setnz   al
0x140004c03  mov     [rbx+1Fh], al
0x140004c06  jmp     loc_140004E39
0x140004c0b  mov     ecx, [rbx+0Ch]
0x140004c0e  lea     eax, [rcx-3]
0x140004c11  cmp     eax, 1
0x140004c14  jbe     short loc_140004C33
0x140004c16  mov     edi, 0C000000Dh
0x140004c1b  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140004c22  jz      loc_140004E39
0x140004c28  mov     r9d, 5Ah ; 'Z'
0x140004c2e  jmp     loc_140004B5E
0x140004c33  mov     rax, [rbp+arg_8]
0x140004c37  cmp     rax, 0Dh
0x140004c3b  jnb     short loc_140004C5A
0x140004c3d  mov     edi, 0C000000Dh
0x140004c42  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140004c49  jz      loc_140004E39
0x140004c4f  mov     r9d, 5Bh ; '['
0x140004c55  jmp     loc_140004B8A
0x140004c5a  mov     cl, [rdx+0Ch]
0x140004c5d  test    cl, cl
0x140004c5f  setnz   al
0x140004c62  mov     [rbx+1Eh], al
0x140004c65  test    cl, cl
0x140004c67  jnz     loc_140004E39
0x140004c6d  mov     [rbx+40h], r12b
0x140004c71  jmp     loc_140004E39
0x140004c76  mov     ecx, [rbx+0Ch]
0x140004c79  lea     eax, [rcx-3]
0x140004c7c  cmp     eax, 1
0x140004c7f  jbe     short loc_140004C9E
0x140004c81  mov     edi, 0C000000Dh
0x140004c86  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140004c8d  jz      loc_140004E39
0x140004c93  mov     r9d, 58h ; 'X'
0x140004c99  jmp     loc_140004B5E
0x140004c9e  mov     rax, [rbp+arg_8]
0x140004ca2  cmp     rax, 0Dh
0x140004ca6  jnb     short loc_140004CC5
0x140004ca8  mov     edi, 0C000000Dh
0x140004cad  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140004cb4  jz      loc_140004E39
0x140004cba  mov     r9d, 59h ; 'Y'
0x140004cc0  jmp     loc_140004B8A
0x140004cc5  mov     cl, [rdx+0Ch]
0x140004cc8  test    cl, cl
0x140004cca  setnz   al
0x140004ccd  mov     [rbx+1Dh], al
0x140004cd0  jmp     short loc_140004C65
0x140004cd2  mov     ecx, [rbx+0Ch]
0x140004cd5  lea     eax, [rcx-3]
0x140004cd8  cmp     eax, 1
0x140004cdb  jbe     short loc_140004CFA
0x140004cdd  mov     edi, 0C000000Dh
0x140004ce2  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140004ce9  jz      loc_140004E39
0x140004cef  mov     r9d, 56h ; 'V'
0x140004cf5  jmp     loc_140004B5E
0x140004cfa  mov     rax, [rbp+arg_8]
0x140004cfe  cmp     rax, 0Dh
0x140004d02  jnb     short loc_140004D21
0x140004d04  mov     edi, 0C000000Dh
0x140004d09  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140004d10  jz      loc_140004E39
0x140004d16  mov     r9d, 57h ; 'W'
0x140004d1c  jmp     loc_140004B8A
0x140004d21  cmp     [rdx+0Ch], r12b
0x140004d25  setnz   al
0x140004d28  mov     [rbx+1Ch], al
0x140004d2b  jmp     loc_140004E39
0x140004d30  cmp     dword ptr [rbx+0Ch], 2
0x140004d34  jnz     short loc_140004D5F
0x140004d36  mov     edi, 0C000000Dh
0x140004d3b  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140004d42  jz      loc_140004E39
0x140004d48  mov     dword ptr [rsp+40h+var_10], edi
0x140004d4c  mov     r9d, 54h ; 'T'
0x140004d52  mov     dword ptr [rsp+40h+var_18], 2
0x140004d5a  jmp     loc_140004B19
0x140004d5f  mov     rax, [rbp+arg_8]
0x140004d63  cmp     rax, 10h
0x140004d67  jnb     short loc_140004D86
0x140004d69  mov     edi, 0C000000Dh
0x140004d6e  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140004d75  jz      loc_140004E39
0x140004d7b  mov     r9d, 55h ; 'U'
0x140004d81  jmp     loc_140004B8A
0x140004d86  mov     eax, [rdx+0Ch]
0x140004d89  mov     [rbx+18h], eax
0x140004d8c  jmp     loc_140004E39
0x140004d91  mov     ecx, [rbx+0Ch]
0x140004d94  lea     eax, [rcx-3]
0x140004d97  cmp     eax, 1
0x140004d9a  jbe     short loc_140004DB9
0x140004d9c  mov     edi, 0C000000Dh
0x140004da1  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140004da8  jz      loc_140004E39
0x140004dae  mov     r9d, 52h ; 'R'
0x140004db4  jmp     loc_140004B5E
0x140004db9  mov     rax, [rbp+arg_8]
0x140004dbd  cmp     rax, 0Dh
0x140004dc1  jnb     short loc_140004DDC
0x140004dc3  mov     edi, 0C000000Dh
0x140004dc8  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140004dcf  jz      short loc_140004E39
0x140004dd1  mov     r9d, 53h ; 'S'
0x140004dd7  jmp     loc_140004B8A
0x140004ddc  cmp     [rdx+0Ch], r12b
0x140004de0  setnz   al
0x140004de3  mov     [rbx+15h], al
0x140004de6  jmp     short loc_140004E39
0x140004de8  mov     rax, [rbp+arg_8]
0x140004dec  cmp     rax, 0Dh
0x140004df0  jnb     short loc_140004E0B
0x140004df2  mov     edi, 0C000000Dh
0x140004df7  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140004dfe  jz      short loc_140004E39
0x140004e00  mov     r9d, 50h ; 'P'
0x140004e06  jmp     loc_140004B8A
0x140004e0b  mov     ecx, [rbx+0Ch]
0x140004e0e  lea     eax, [rcx-3]
0x140004e11  cmp     eax, 1
0x140004e14  jbe     short loc_140004E2F
0x140004e16  mov     edi, 0C000000Dh
  ... truncated ...
```
