# HUBHTX_CompleteGetPortStatusWithPortStatusResult

- ea: `0x140003394`
- end: `0x140003599`
- name: `HUBHTX_CompleteGetPortStatusWithPortStatusResult`
- size: `517`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400089b0`

## callees

- `0x1400024b8`
- `0x140003394`
- `0x140045530`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall HUBHTX_CompleteGetPortStatusWithPortStatusResult(_QWORD *a1)
{
  __int64 v1; // rbx
  __int64 v2; // rdx
  int v4; // ebx
  int v5; // eax
  int v6; // edx
  int v7; // edi
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  __int64 v10; // rdx
  int v12; // [rsp+28h] [rbp-50h]
  __int64 v13; // [rsp+38h] [rbp-40h] BYREF
  __int128 v14; // [rsp+40h] [rbp-38h] BYREF
  __int128 v15; // [rsp+50h] [rbp-28h]
  __int64 v16; // [rsp+60h] [rbp-18h]

  v1 = a1[325];
  v2 = a1[318];
  v16 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v4 = *(_DWORD *)(v1 + 184);
  v5 = *(_DWORD *)(*(_QWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2280))(
                                 WdfDriverGlobals,
                                 v2)
                             + 184)
                 + 24LL);
  if ( v5 == 2228240 )
  {
    v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01015 + 2144))(
           WdfDriverGlobals,
           a1[318],
           &v13);
    if ( v7 >= 0 )
    {
      *(_WORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 1552))(
                   WdfDriverGlobals,
                   v13,
                   0)
               + 4) = v4;
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01015 + 2200))(
        WdfDriverGlobals,
        a1[318],
        8);
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v12 = v7;
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_d(a1[317], v6, 3, 114, (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids, v12);
    }
  }
  else if ( v5 == 2228243 )
  {
    v8 = a1[318];
    v16 = 0;
    v14 = 0;
    LOWORD(v14) = 40;
    v15 = 0;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01015 + 2128))(
      WdfDriverGlobals,
      v8,
      &v14);
    v9 = (_DWORD *)*((_QWORD *)&v14 + 1);
    v10 = v15;
    if ( (v4 & 1) != 0 )
    {
      v7 = 0;
      **((_DWORD **)&v14 + 1) |= 2u;
    }
    else
    {
      v7 = -1073741810;
    }
    if ( (v4 & 2) != 0 )
    {
      if ( (*(_DWORD *)(v10 + 32) & 0x2000) != 0 )
        _InterlockedAnd((volatile signed __int32 *)(v10 + 32), 0xFFFFDFFF);
      else
        *v9 |= 1u;
    }
    if ( (v4 & 0x10000) != 0 )
      v7 = -1073741810;
  }
  else
  {
    v7 = -1073741630;
  }
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2104))(
           WdfDriverGlobals,
           a1[318],
           (unsigned int)v7);
}

```

## disassembly

```asm
0x140003394  push    rbp
0x140003396  push    rbx
0x140003397  push    rsi
0x140003398  push    rdi
0x140003399  mov     rbp, rsp
0x14000339c  sub     rsp, 78h
0x1400033a0  mov     rax, cs:__security_cookie
0x1400033a7  xor     rax, rsp
0x1400033aa  mov     [rbp+var_10], rax
0x1400033ae  mov     rbx, [rcx+0A28h]
0x1400033b5  xor     eax, eax
0x1400033b7  mov     rdx, [rcx+9F0h]
0x1400033be  xorps   xmm0, xmm0
0x1400033c1  mov     [rbp+var_18], rax
0x1400033c5  mov     rsi, rcx
0x1400033c8  mov     rax, cs:WdfFunctions_01015
0x1400033cf  mov     rcx, cs:WdfDriverGlobals
0x1400033d6  mov     [rbp+var_40], 0
0x1400033de  movups  [rbp+var_38], xmm0
0x1400033e2  movups  [rbp+var_28], xmm0
0x1400033e6  mov     ebx, [rbx+0B8h]
0x1400033ec  mov     rax, [rax+8E8h]
0x1400033f3  mov     [rbp+var_48], ebx
0x1400033f6  call    _guard_dispatch_icall
0x1400033fb  mov     rcx, [rax+0B8h]
0x140003402  mov     eax, [rcx+18h]
0x140003405  cmp     eax, 220010h
0x14000340a  jnz     loc_1400034CD
0x140003410  mov     rax, cs:WdfFunctions_01015
0x140003417  lea     r8, [rbp+var_40]
0x14000341b  mov     rdx, [rsi+9F0h]
0x140003422  mov     rcx, cs:WdfDriverGlobals
0x140003429  mov     rax, [rax+860h]
0x140003430  call    _guard_dispatch_icall
0x140003435  mov     edi, eax
0x140003437  test    eax, eax
0x140003439  jns     short loc_14000347C
0x14000343b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140003442  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003449  jz      loc_14000355F
0x14000344f  mov     rcx, [rsi+9E8h]
0x140003456  lea     rax, WPP_70469c384dd13630d566350a6f2705ad_Traceguids
0x14000345d  mov     r9d, 72h ; 'r'
0x140003463  mov     [rsp+78h+var_50], edi
0x140003467  mov     dl, 2
0x140003469  mov     [rsp+78h+var_58], rax
0x14000346e  lea     r8d, [r9-6Fh]
0x140003472  call    WPP_RECORDER_SF_d
0x140003477  jmp     loc_14000355F
0x14000347c  mov     rax, cs:WdfFunctions_01015
0x140003483  xor     r8d, r8d
0x140003486  mov     rdx, [rbp+var_40]
0x14000348a  mov     rcx, cs:WdfDriverGlobals
0x140003491  mov     rax, [rax+610h]
0x140003498  call    _guard_dispatch_icall
0x14000349d  mov     r8d, 8
0x1400034a3  mov     [rax+4], bx
0x1400034a7  mov     rax, cs:WdfFunctions_01015
0x1400034ae  mov     rdx, [rsi+9F0h]
0x1400034b5  mov     rcx, cs:WdfDriverGlobals
0x1400034bc  mov     rax, [rax+898h]
0x1400034c3  call    _guard_dispatch_icall
0x1400034c8  jmp     loc_14000355F
0x1400034cd  cmp     eax, 220013h
0x1400034d2  jnz     loc_14000355A
0x1400034d8  mov     rdx, [rsi+9F0h]
0x1400034df  lea     r8, [rbp+var_38]
0x1400034e3  mov     rcx, cs:WdfDriverGlobals
0x1400034ea  xor     eax, eax
0x1400034ec  mov     [rbp+var_18], rax
0x1400034f0  xorps   xmm0, xmm0
0x1400034f3  movups  [rbp+var_38], xmm0
0x1400034f7  mov     eax, 28h ; '('
0x1400034fc  mov     word ptr [rbp+var_38], ax
0x140003500  mov     rax, cs:WdfFunctions_01015
0x140003507  movups  [rbp+var_28], xmm0
0x14000350b  mov     rax, [rax+850h]
0x140003512  call    _guard_dispatch_icall
0x140003517  mov     rcx, qword ptr [rbp+var_38+8]
0x14000351b  mov     r8d, 0C000000Eh
0x140003521  mov     rdx, qword ptr [rbp+var_28]
0x140003525  test    bl, 1
0x140003528  jz      short loc_140003531
0x14000352a  xor     edi, edi
0x14000352c  or      dword ptr [rcx], 2
0x14000352f  jmp     short loc_140003534
0x140003531  mov     edi, r8d
0x140003534  test    bl, 2
0x140003537  jz      short loc_14000354F
0x140003539  test    dword ptr [rdx+20h], 2000h
0x140003540  jz      short loc_14000354C
0x140003542  lock and dword ptr [rdx+20h], 0FFFFDFFFh
0x14000354a  jmp     short loc_14000354F
0x14000354c  or      dword ptr [rcx], 1
0x14000354f  test    byte ptr [rbp+var_48+2], 1
0x140003553  jz      short loc_14000355F
0x140003555  mov     edi, r8d
0x140003558  jmp     short loc_14000355F
0x14000355a  mov     edi, 0C00000C2h
0x14000355f  mov     rax, cs:WdfFunctions_01015
0x140003566  mov     r8d, edi
0x140003569  mov     rdx, [rsi+9F0h]
0x140003570  mov     rcx, cs:WdfDriverGlobals
0x140003577  mov     rax, [rax+838h]
0x14000357e  call    _guard_dispatch_icall
0x140003583  mov     rcx, [rbp+var_10]
0x140003587  xor     rcx, rsp; StackCookie
0x14000358a  call    __security_check_cookie
0x14000358f  add     rsp, 78h
0x140003593  pop     rdi
0x140003594  pop     rsi
0x140003595  pop     rbx
0x140003596  pop     rbp
0x140003597  retn
```
