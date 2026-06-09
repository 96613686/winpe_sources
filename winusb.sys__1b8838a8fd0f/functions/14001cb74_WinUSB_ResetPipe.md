# WinUSB_ResetPipe

- ea: `0x14001cb74`
- end: `0x14001cf1f`
- name: `WinUSB_ResetPipe`
- size: `939`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x140004740`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x1400013d0`
- `0x1400014bc`
- `0x140001840`
- `0x1400106c0`
- `0x140010700`
- `0x14001cb74`

## pseudocode

```c
__int64 __fastcall WinUSB_ResetPipe(__int64 a1, __int64 a2, __int64 a3, _BYTE *a4)
{
  int v7; // eax
  int v8; // edx
  unsigned int v9; // ebx
  int v10; // r9d
  int v11; // edx
  __int64 v12; // r8
  int v13; // r9d
  __int64 v14; // rdi
  int v15; // edx
  int v16; // eax
  int v17; // edx
  int v18; // r9d
  int v19; // eax
  int v20; // edx
  char v22; // [rsp+28h] [rbp-38h]
  char *v23; // [rsp+40h] [rbp-20h] BYREF
  __int128 v24; // [rsp+48h] [rbp-18h] BYREF

  v23 = 0;
  v24 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      140,
      (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids);
  *a4 = 1;
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, char **))(WdfFunctions_01015 + 2152))(
         WdfDriverGlobals,
         a3,
         2,
         &v23);
  v9 = v7;
  if ( v7 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v9;
    v10 = 141;
    v22 = v7;
    goto LABEL_7;
  }
  v8 = (int)v23;
  v12 = (unsigned __int8)*v23;
  if ( (unsigned __int8)v12 >= *(_BYTE *)(a1 + 128) )
  {
    v9 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v9;
    v10 = 142;
    goto LABEL_11;
  }
  LOBYTE(v8) = v23[1];
  v13 = (unsigned __int8)((v8 & 0xF) + 16);
  if ( (v8 & 0x80u) == 0 )
    v13 = v8 & 0xF;
  if ( (_BYTE)v13 )
  {
    v14 = *(_QWORD *)(*(_QWORD *)(a1 + 136) + 8 * ((unsigned __int8)v13 + 35 * v12) + 24);
    if ( !v14 )
    {
      v9 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v9;
      WPP_RECORDER_SF_DDd(WPP_GLOBAL_Control->DeviceExtension, v8, v12, v13, 0, v13, *v23);
      goto LABEL_34;
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01015 + 1376))(
      WdfDriverGlobals,
      *(_QWORD *)(v14 + 160),
      1);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v15) = 4;
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        v15,
        2,
        145,
        (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
        *(_QWORD *)(v14 + 160));
    }
    v24 = 0x400000010uLL;
    v16 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, __int128 *))(WdfFunctions_01015 + 2808))(
            WdfDriverGlobals,
            *(_QWORD *)(v14 + 160),
            0,
            &v24);
    if ( v16 >= 0 )
    {
      v24 = 0x400000010uLL;
      v16 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, __int128 *))(WdfFunctions_01015 + 2824))(
              WdfDriverGlobals,
              *(_QWORD *)(v14 + 160),
              0,
              &v24);
      if ( v16 >= 0 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_29:
        v19 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1368))(
                WdfDriverGlobals,
                *(_QWORD *)(v14 + 160));
        v9 = v19;
        if ( v19 >= 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            return v9;
          LOBYTE(v20) = 4;
          WPP_RECORDER_SF_q(
            WPP_GLOBAL_Control->DeviceExtension,
            v20,
            2,
            149,
            (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
            *(_QWORD *)(v14 + 160));
        }
        else
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            return v9;
          LOBYTE(v20) = 2;
          WPP_RECORDER_SF_qd(
            WPP_GLOBAL_Control->DeviceExtension,
            v20,
            2,
            148,
            (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
            *(_QWORD *)(v14 + 160),
            v19);
        }
        goto LABEL_34;
      }
      v18 = 147;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_29;
      v18 = 146;
    }
    LOBYTE(v17) = 2;
    WPP_RECORDER_SF_qd(
      WPP_GLOBAL_Control->DeviceExtension,
      v17,
      2,
      v18,
      (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
      *(_QWORD *)(v14 + 160),
      v16);
    goto LABEL_29;
  }
  v9 = -1073741811;
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return v9;
  v10 = 143;
LABEL_11:
  v22 = 13;
LABEL_7:
  LOBYTE(v8) = 2;
  WPP_RECORDER_SF_d(
    WPP_GLOBAL_Control->DeviceExtension,
    v8,
    2,
    v10,
    (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
    v22);
LABEL_34:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v11) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      1,
      150,
      (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
      v9);
  }
  return v9;
}

```

## disassembly

```asm
0x14001cb74  push    rbp
0x14001cb76  push    rbx
0x14001cb77  push    rsi
0x14001cb78  push    rdi
0x14001cb79  push    r12
0x14001cb7b  push    r14
0x14001cb7d  push    r15
0x14001cb7f  mov     rbp, rsp
0x14001cb82  sub     rsp, 60h
0x14001cb86  mov     rax, cs:__security_cookie
0x14001cb8d  xor     rax, rsp
0x14001cb90  mov     [rbp+var_8], rax
0x14001cb94  xor     r12d, r12d
0x14001cb97  xorps   xmm0, xmm0
0x14001cb9a  mov     [rbp+var_20], r12
0x14001cb9e  mov     rsi, r9
0x14001cba1  movups  [rbp+var_18], xmm0
0x14001cba5  mov     rbx, r8
0x14001cba8  mov     rdi, rcx
0x14001cbab  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001cbb2  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14001cbb9  lea     r15, WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids
0x14001cbc0  jz      short loc_14001CBEB
0x14001cbc2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cbc9  cmp     [rcx+48h], r12w
0x14001cbce  jz      short loc_14001CBEB
0x14001cbd0  mov     rcx, [rcx+40h]
0x14001cbd4  lea     r8d, [r12+1]
0x14001cbd9  mov     r9d, 8Ch
0x14001cbdf  mov     [rsp+60h+var_40], r15
0x14001cbe4  mov     dl, 5
0x14001cbe6  call    WPP_RECORDER_SF_
0x14001cbeb  mov     byte ptr [rsi], 1
0x14001cbee  lea     r9, [rbp+var_20]
0x14001cbf2  mov     rax, cs:WdfFunctions_01015
0x14001cbf9  mov     esi, 2
0x14001cbfe  mov     rcx, cs:WdfDriverGlobals
0x14001cc05  mov     r8d, esi
0x14001cc08  mov     rdx, rbx
0x14001cc0b  mov     [rsp+60h+var_40], r12
0x14001cc10  mov     rax, [rax+868h]
0x14001cc17  call    _guard_dispatch_icall
0x14001cc1c  mov     ebx, eax
0x14001cc1e  test    eax, eax
0x14001cc20  jns     short loc_14001CC59
0x14001cc22  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14001cc29  jz      loc_14001CF01
0x14001cc2f  mov     r9d, 8Dh
0x14001cc35  mov     dword ptr [rsp+60h+var_38], eax
0x14001cc39  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cc40  mov     r8d, esi
0x14001cc43  mov     dl, sil
0x14001cc46  mov     [rsp+60h+var_40], r15
0x14001cc4b  mov     rcx, [rcx+40h]
0x14001cc4f  call    WPP_RECORDER_SF_d
0x14001cc54  jmp     loc_14001CECA
0x14001cc59  mov     rdx, [rbp+var_20]
0x14001cc5d  movzx   r8d, byte ptr [rdx]
0x14001cc61  cmp     r8b, [rdi+80h]
0x14001cc68  jb      short loc_14001CC88
0x14001cc6a  mov     ebx, 0C000000Dh
0x14001cc6f  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14001cc76  jz      loc_14001CF01
0x14001cc7c  mov     r9d, 8Eh
0x14001cc82  mov     dword ptr [rsp+60h+var_38], ebx
0x14001cc86  jmp     short loc_14001CC39
0x14001cc88  mov     dl, [rdx+1]
0x14001cc8b  mov     ebx, 10h
0x14001cc90  mov     al, dl
0x14001cc92  and     al, 0Fh
0x14001cc94  movzx   ecx, al
0x14001cc97  test    dl, dl
0x14001cc99  lea     eax, [rbx+rcx]
0x14001cc9c  movzx   r9d, al
0x14001cca0  cmovns  r9d, ecx
0x14001cca4  test    r9b, r9b
0x14001cca7  jnz     short loc_14001CCC3
0x14001cca9  mov     ebx, 0C000000Dh
0x14001ccae  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14001ccb5  jz      loc_14001CF01
0x14001ccbb  mov     r9d, 8Fh
0x14001ccc1  jmp     short loc_14001CC82
0x14001ccc3  imul    rcx, r8, 23h ; '#'
0x14001ccc7  movzx   eax, r9b
0x14001cccb  add     rcx, rax
0x14001ccce  mov     rax, [rdi+88h]
0x14001ccd5  mov     rdi, [rax+rcx*8+18h]
0x14001ccda  test    rdi, rdi
0x14001ccdd  jnz     short loc_14001CD13
0x14001ccdf  mov     ebx, 0C000000Dh
0x14001cce4  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14001cceb  jz      loc_14001CF01
0x14001ccf1  movzx   ecx, r9b
0x14001ccf5  mov     [rsp+60h+var_30], r8d
0x14001ccfa  mov     dword ptr [rsp+60h+var_38], ecx
0x14001ccfe  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cd05  mov     rcx, [rcx+40h]
0x14001cd09  call    WPP_RECORDER_SF_DDd
0x14001cd0e  jmp     loc_14001CECA
0x14001cd13  mov     rax, cs:WdfFunctions_01015
0x14001cd1a  mov     r8d, 1
0x14001cd20  mov     rdx, [rdi+0A0h]
0x14001cd27  mov     rcx, cs:WdfDriverGlobals
0x14001cd2e  mov     rax, [rax+560h]
0x14001cd35  call    _guard_dispatch_icall
0x14001cd3a  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14001cd41  jz      short loc_14001CD6F
0x14001cd43  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cd4a  mov     r9d, 91h
0x14001cd50  mov     rax, [rdi+0A0h]
0x14001cd57  mov     r8d, esi
0x14001cd5a  mov     [rsp+60h+var_38], rax
0x14001cd5f  mov     dl, 4
0x14001cd61  mov     [rsp+60h+var_40], r15
0x14001cd66  mov     rcx, [rcx+40h]
0x14001cd6a  call    WPP_RECORDER_SF_q
0x14001cd6f  mov     rax, cs:WdfFunctions_01015
0x14001cd76  lea     r9, [rbp+var_18]
0x14001cd7a  mov     rcx, cs:WdfDriverGlobals
0x14001cd81  xor     r8d, r8d
0x14001cd84  mov     qword ptr [rbp+var_18+8], r12
0x14001cd88  mov     dword ptr [rbp+var_18], ebx
0x14001cd8b  mov     dword ptr [rbp+var_18+4], 4
0x14001cd92  mov     rax, [rax+0AF8h]
0x14001cd99  mov     rdx, [rdi+0A0h]
0x14001cda0  call    _guard_dispatch_icall
0x14001cda5  test    eax, eax
0x14001cda7  jns     short loc_14001CDBA
0x14001cda9  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14001cdb0  jz      short loc_14001CE2E
0x14001cdb2  mov     r9d, 92h
0x14001cdb8  jmp     short loc_14001CE03
0x14001cdba  mov     rax, cs:WdfFunctions_01015
0x14001cdc1  lea     r9, [rbp+var_18]
0x14001cdc5  mov     rcx, cs:WdfDriverGlobals
0x14001cdcc  xor     r8d, r8d
0x14001cdcf  mov     qword ptr [rbp+var_18+8], r12
0x14001cdd3  mov     dword ptr [rbp+var_18], ebx
0x14001cdd6  mov     dword ptr [rbp+var_18+4], 4
0x14001cddd  mov     rax, [rax+0B08h]
0x14001cde4  mov     rdx, [rdi+0A0h]
0x14001cdeb  call    _guard_dispatch_icall
0x14001cdf0  test    eax, eax
0x14001cdf2  jns     short loc_14001CE2E
0x14001cdf4  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14001cdfb  jz      short loc_14001CE2E
0x14001cdfd  mov     r9d, 93h
0x14001ce03  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ce0a  mov     r8d, esi
0x14001ce0d  mov     [rsp+60h+var_30], eax
0x14001ce11  mov     dl, sil
0x14001ce14  mov     rax, [rdi+0A0h]
0x14001ce1b  mov     [rsp+60h+var_38], rax
0x14001ce20  mov     rcx, [rcx+40h]
0x14001ce24  mov     [rsp+60h+var_40], r15
0x14001ce29  call    WPP_RECORDER_SF_qd
0x14001ce2e  mov     rax, cs:WdfFunctions_01015
0x14001ce35  mov     rdx, [rdi+0A0h]
0x14001ce3c  mov     rcx, cs:WdfDriverGlobals
0x14001ce43  mov     rax, [rax+558h]
0x14001ce4a  call    _guard_dispatch_icall
0x14001ce4f  mov     ebx, eax
0x14001ce51  test    eax, eax
0x14001ce53  jns     short loc_14001CE95
0x14001ce55  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14001ce5c  jz      loc_14001CF01
0x14001ce62  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ce69  mov     r9d, 94h
0x14001ce6f  mov     [rsp+60h+var_30], eax
0x14001ce73  mov     r8d, esi
0x14001ce76  mov     rax, [rdi+0A0h]
0x14001ce7d  mov     dl, sil
0x14001ce80  mov     [rsp+60h+var_38], rax
0x14001ce85  mov     rcx, [rcx+40h]
0x14001ce89  mov     [rsp+60h+var_40], r15
0x14001ce8e  call    WPP_RECORDER_SF_qd
0x14001ce93  jmp     short loc_14001CECA
0x14001ce95  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14001ce9c  jz      short loc_14001CF01
0x14001ce9e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cea5  mov     r9d, 95h
0x14001ceab  mov     rax, [rdi+0A0h]
0x14001ceb2  mov     r8d, esi
0x14001ceb5  mov     [rsp+60h+var_38], rax
0x14001ceba  mov     dl, 4
0x14001cebc  mov     [rsp+60h+var_40], r15
0x14001cec1  mov     rcx, [rcx+40h]
0x14001cec5  call    WPP_RECORDER_SF_q
0x14001ceca  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14001ced1  jz      short loc_14001CF01
0x14001ced3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ceda  cmp     [rcx+48h], r12w
0x14001cedf  jz      short loc_14001CF01
0x14001cee1  mov     rcx, [rcx+40h]
0x14001cee5  mov     r9d, 96h
0x14001ceeb  mov     dword ptr [rsp+60h+var_38], ebx
0x14001ceef  mov     r8d, 1
0x14001cef5  mov     dl, 5
0x14001cef7  mov     [rsp+60h+var_40], r15
0x14001cefc  call    WPP_RECORDER_SF_d
0x14001cf01  mov     eax, ebx
0x14001cf03  mov     rcx, [rbp+var_8]
0x14001cf07  xor     rcx, rsp; StackCookie
0x14001cf0a  call    __security_check_cookie
0x14001cf0f  add     rsp, 60h
0x14001cf13  pop     r15
0x14001cf15  pop     r14
0x14001cf17  pop     r12
0x14001cf19  pop     rdi
0x14001cf1a  pop     rsi
0x14001cf1b  pop     rbx
0x14001cf1c  pop     rbp
0x14001cf1d  retn
```
