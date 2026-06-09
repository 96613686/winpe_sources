# CDevicesDB::OpenRegKeyForRead(ATL::CRegKey &,ushort const *)

- ea: `0x140007b94`
- end: `0x140007fbc`
- name: `?OpenRegKeyForRead@CDevicesDB@@AEAAJAEAVCRegKey@ATL@@PEBG@Z`
- size: `1064`
- prototype: `int(CDevicesDB *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x140009070`
- `0x14000e20c`
- `0x14000e3c8`
- `0x14000efe4`
- `0x140011594`

## callees

- `0x140007020`
- `0x140007b94`
- `0x140008eac`
- `0x140015230`
- `0x1400396dc`
- `0x14003e5f4`
- `0x14003f17c`
- `0x140046c32`
- `0x140046d00`
- `0x1400476ac`
- `0x14004a79c`
- `0x14009ad10`
- `0x14009ad1c`
- `0x14009e010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140007d89`
- `ADVAPI32!RegOpenKeyExW` at `0x140007d89`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007c22`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007df4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007f68`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007c22`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007df4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007f68`

## pseudocode

```c
__int64 __fastcall CDevicesDB::OpenRegKeyForRead(CDevicesDB *this, struct ATL::CRegKey *a2, const unsigned __int16 *a3)
{
  const unsigned __int16 *v3; // r12
  ATL::CRegKey *v4; // r13
  _WORD *v6; // rsi
  __int64 v7; // rax
  WCHAR *v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r15
  WCHAR *v11; // rbx
  unsigned __int64 v12; // r15
  const wchar_t *v13; // r14
  int v14; // edi
  unsigned __int64 v15; // rsi
  wchar_t *v16; // rcx
  __int64 v17; // rsi
  unsigned __int64 v18; // r15
  unsigned __int64 v19; // r14
  int v20; // edi
  size_t v21; // r8
  WCHAR *v22; // rcx
  unsigned int v23; // edi
  PVOID *v24; // r10
  __int64 v26; // rdi
  unsigned __int64 v27; // r13
  __int64 v28; // r14
  unsigned __int64 v29; // rcx
  LPCWSTR lpSubKey; // [rsp+70h] [rbp+40h] BYREF
  struct ATL::CRegKey *v31; // [rsp+78h] [rbp+48h]

  v31 = a2;
  v3 = a3;
  v4 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 156, &WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids, a3);
  }
  v6 = (_WORD *)(*(__int64 (__fastcall **)(CDevicesDB *))(*(_QWORD *)this + 80LL))(this);
  v7 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  v10 = v7 + 24;
  v11 = (WCHAR *)(v7 + 24);
  lpSubKey = (LPCWSTR)(v7 + 24);
  if ( !v6 )
    goto LABEL_3;
  if ( (unsigned __int64)v6 < 0x10000 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::LoadStringW(
      &lpSubKey,
      (unsigned __int16)v6);
    goto LABEL_4;
  }
  v26 = -1;
  do
    ++v26;
  while ( v6[v26] );
  if ( !(_DWORD)v26 )
  {
LABEL_3:
    ATL::CSimpleStringT<unsigned short,0>::Empty(&lpSubKey);
LABEL_4:
    v11 = (WCHAR *)lpSubKey;
    goto LABEL_9;
  }
  v27 = *(unsigned int *)(v7 + 8);
  if ( (int)((*(_DWORD *)(v7 + 12) - v26) | (1 - *(_DWORD *)(v7 + 16))) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&lpSubKey, (unsigned int)v26);
    v11 = (WCHAR *)lpSubKey;
  }
  v28 = (int)v26;
  if ( v28 * 2 )
  {
    v29 = ((__int64)v6 - v10) >> 1;
    if ( v29 > v27 )
    {
      if ( v11 )
      {
        memcpy_0(v11, v6, 2LL * (int)v26);
        goto LABEL_6;
      }
LABEL_5:
      *(_DWORD *)_o__errno(v29, v8, v9) = 22;
      invalid_parameter_noinfo();
      goto LABEL_6;
    }
    if ( !v11 )
      goto LABEL_5;
    v8 = &v11[v29];
    if ( !v8 )
      goto LABEL_5;
    memmove_0(v11, v8, 2LL * (int)v26);
  }
LABEL_6:
  if ( (int)v26 < 0 || (int)v26 > *((_DWORD *)v11 - 3) )
LABEL_64:
    ATL::AtlThrowImpl(-2147024809);
  v4 = v31;
  *((_DWORD *)v11 - 4) = v26;
  v11[v28] = 0;
LABEL_9:
  if ( !v3 )
    goto LABEL_32;
  v12 = *((unsigned int *)v11 - 4);
  v13 = L"\\";
  v14 = v12 + 1;
  v15 = L"\\" - v11;
  if ( (((*((_DWORD *)v11 - 3) - (v12 + 1)) | (1 - *((_DWORD *)v11 - 2))) & 0x80000000) != 0LL )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&lpSubKey, (unsigned int)v14);
    v11 = (WCHAR *)lpSubKey;
  }
  if ( v15 <= v12 )
    v13 = &v11[v15];
  v16 = &v11[v12];
  if ( !v16 )
    goto LABEL_38;
  if ( !v13 )
  {
    *v16 = 0;
LABEL_38:
    *(_DWORD *)_o__errno(v16, v8, v9) = 22;
    invalid_parameter_noinfo();
    goto LABEL_17;
  }
  *v16 = *v13;
LABEL_17:
  if ( v14 < 0 || v14 > *((_DWORD *)v11 - 3) )
    goto LABEL_64;
  v17 = -1;
  *((_DWORD *)v11 - 4) = v14;
  v11[v14] = 0;
  do
    ++v17;
  while ( v3[v17] );
  v18 = *((unsigned int *)v11 - 4);
  v19 = v3 - v11;
  v20 = v18 + v17;
  if ( (((*((_DWORD *)v11 - 3) - (v18 + v17)) | (1 - *((_DWORD *)v11 - 2))) & 0x80000000) != 0LL )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&lpSubKey, (unsigned int)v20);
    v11 = (WCHAR *)lpSubKey;
  }
  if ( v19 <= v18 )
    v3 = &v11[v19];
  v21 = 2LL * (int)v17;
  if ( v21 )
  {
    v22 = &v11[v18];
    if ( v22 )
    {
      if ( v3 )
      {
        memcpy_0(v22, v3, v21);
        goto LABEL_29;
      }
      memset_0(v22, 0, v21);
    }
    *(_DWORD *)_o__errno(v22, v8, v21) = 22;
    invalid_parameter_noinfo();
  }
LABEL_29:
  if ( v20 < 0 || v20 > *((_DWORD *)v11 - 3) )
    goto LABEL_64;
  *((_DWORD *)v11 - 4) = v20;
  v11[v20] = 0;
LABEL_32:
  lpSubKey = 0;
  v23 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0x20119u, (PHKEY)&lpSubKey);
  if ( !v23 )
  {
    v23 = ATL::CRegKey::Close(v4);
    *(_QWORD *)v4 = lpSubKey;
  }
  v24 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        157,
        (unsigned int)&WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids,
        (_DWORD)v11,
        v23);
      v24 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v24 != &WPP_GLOBAL_Control
      && (*((_BYTE *)v24 + 28) & 1) != 0
      && *((unsigned __int8 *)v24 + 25) >= (unsigned int)(v23 != 0 ? 2 : 5) )
    {
      WPP_SF_d(v24[2], 158, &WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids, v23);
    }
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v11 - 3) + 8LL))(*((_QWORD *)v11 - 3));
  return v23;
}

```

## disassembly

```asm
0x140007b94  mov     [rsp-38h+arg_10], rbx
0x140007b99  mov     [rsp-38h+arg_8], rdx
0x140007b9e  push    rbp
0x140007b9f  push    rsi
0x140007ba0  push    rdi
0x140007ba1  push    r12
0x140007ba3  push    r13
0x140007ba5  push    r14
0x140007ba7  push    r15
0x140007ba9  mov     rbp, rsp
0x140007bac  sub     rsp, 30h
0x140007bb0  mov     r12, r8
0x140007bb3  mov     r13, rdx
0x140007bb6  mov     rbx, rcx
0x140007bb9  mov     rcx, cs:WPP_GLOBAL_Control
0x140007bc0  lea     rax, WPP_GLOBAL_Control
0x140007bc7  cmp     rcx, rax
0x140007bca  jnz     loc_140007EF1
0x140007bd0  mov     rax, [rbx]
0x140007bd3  mov     rcx, rbx
0x140007bd6  mov     rax, [rax+50h]
0x140007bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007bdf  mov     rcx, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140007be6  mov     rsi, rax
0x140007be9  mov     rax, [rcx+18h]
0x140007bed  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140007bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007bf9  xor     r9d, r9d
0x140007bfc  lea     r15, [rax+18h]
0x140007c00  mov     rbx, r15
0x140007c03  mov     [rbp+lpSubKey], rbx
0x140007c07  test    rsi, rsi
0x140007c0a  jnz     loc_140007F22
0x140007c10  lea     rcx, [rbp+lpSubKey]
0x140007c14  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x140007c19  mov     rbx, [rbp+lpSubKey]
0x140007c1d  xor     r9d, r9d
0x140007c20  jmp     short loc_140007C53
0x140007c22  call    cs:__imp__o__errno
0x140007c28  mov     dword ptr [rax], 16h
0x140007c2e  call    _invalid_parameter_noinfo
0x140007c33  xor     r9d, r9d
0x140007c36  test    edi, edi
0x140007c38  js      loc_140007F7E
0x140007c3e  cmp     edi, [rbx-0Ch]
0x140007c41  jg      loc_140007F7E
0x140007c47  mov     r13, [rbp+arg_8]
0x140007c4b  mov     [rbx-10h], edi
0x140007c4e  mov     [r14+rbx], r9w
0x140007c53  test    r12, r12
0x140007c56  jz      loc_140007D69
0x140007c5c  mov     r15d, [rbx-10h]
0x140007c60  lea     r14, asc_1400A283C; "\\"
0x140007c67  mov     eax, [rbx-0Ch]
0x140007c6a  mov     rsi, r14
0x140007c6d  sub     rsi, rbx
0x140007c70  mov     ecx, 1
0x140007c75  sub     ecx, [rbx-8]
0x140007c78  lea     edi, [r15+1]
0x140007c7c  sar     rsi, 1
0x140007c7f  sub     eax, edi
0x140007c81  or      ecx, eax
0x140007c83  jge     short loc_140007C97
0x140007c85  mov     edx, edi
0x140007c87  lea     rcx, [rbp+lpSubKey]
0x140007c8b  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x140007c90  mov     rbx, [rbp+lpSubKey]
0x140007c94  xor     r9d, r9d
0x140007c97  cmp     rsi, r15
0x140007c9a  jbe     loc_140007F45
0x140007ca0  lea     rcx, [rbx+r15*2]
0x140007ca4  test    rcx, rcx
0x140007ca7  jz      loc_140007DF4
0x140007cad  test    r14, r14
0x140007cb0  jz      loc_140007F4E
0x140007cb6  movzx   eax, word ptr [r14]
0x140007cba  mov     [rcx], ax
0x140007cbd  test    edi, edi
0x140007cbf  js      loc_140007F7E
0x140007cc5  cmp     edi, [rbx-0Ch]
0x140007cc8  jg      loc_140007F7E
0x140007cce  movsxd  rcx, edi
0x140007cd1  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140007cd5  mov     [rbx-10h], edi
0x140007cd8  mov     [rbx+rcx*2], r9w
0x140007cdd  inc     rsi
0x140007ce0  cmp     [r12+rsi*2], r9w
0x140007ce5  jnz     short loc_140007CDD
0x140007ce7  mov     r15d, [rbx-10h]
0x140007ceb  mov     r14, r12
0x140007cee  mov     eax, [rbx-0Ch]
0x140007cf1  sub     r14, rbx
0x140007cf4  mov     ecx, 1
0x140007cf9  sar     r14, 1
0x140007cfc  sub     ecx, [rbx-8]
0x140007cff  lea     edi, [r15+rsi]
0x140007d03  sub     eax, edi
0x140007d05  or      ecx, eax
0x140007d07  jge     short loc_140007D1B
0x140007d09  mov     edx, edi
0x140007d0b  lea     rcx, [rbp+lpSubKey]
0x140007d0f  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x140007d14  mov     rbx, [rbp+lpSubKey]
0x140007d18  xor     r9d, r9d
0x140007d1b  cmp     r14, r15
0x140007d1e  jbe     loc_140007F58
0x140007d24  movsxd  r8, esi
0x140007d27  add     r8, r8; Size
0x140007d2a  jz      short loc_140007D4D
0x140007d2c  lea     rcx, [rbx+r15*2]; void *
0x140007d30  test    rcx, rcx
0x140007d33  jz      loc_140007F68
0x140007d39  test    r12, r12
0x140007d3c  jz      loc_140007F61
0x140007d42  mov     rdx, r12; Src
0x140007d45  call    memcpy_0
0x140007d4a  xor     r9d, r9d
0x140007d4d  test    edi, edi
0x140007d4f  js      loc_140007F7E
0x140007d55  cmp     edi, [rbx-0Ch]
0x140007d58  jg      loc_140007F7E
0x140007d5e  movsxd  rcx, edi
0x140007d61  mov     [rbx-10h], edi
0x140007d64  mov     [rbx+rcx*2], r9w
0x140007d69  mov     [rbp+lpSubKey], r9
0x140007d6d  lea     rax, [rbp+lpSubKey]
0x140007d71  mov     r9d, 20119h; samDesired
0x140007d77  mov     [rsp+30h+phkResult], rax; phkResult
0x140007d7c  xor     r8d, r8d; ulOptions
0x140007d7f  mov     rdx, rbx; lpSubKey
0x140007d82  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140007d89  call    cs:__imp_RegOpenKeyExW
0x140007d8f  mov     edi, eax
0x140007d91  test    eax, eax
0x140007d93  jnz     short loc_140007DA7
0x140007d95  mov     rcx, r13; this
0x140007d98  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140007d9d  mov     edi, eax
0x140007d9f  mov     rax, [rbp+lpSubKey]
0x140007da3  mov     [r13+0], rax
0x140007da7  mov     r10, cs:WPP_GLOBAL_Control
0x140007dae  lea     rsi, WPP_GLOBAL_Control
0x140007db5  cmp     r10, rsi
0x140007db8  jnz     short loc_140007E0D
0x140007dba  lea     rdx, [rbx-18h]
0x140007dbe  or      eax, 0FFFFFFFFh
0x140007dc1  lock xadd [rdx+10h], eax
0x140007dc6  sub     eax, 1
0x140007dc9  jg      short loc_140007DDA
0x140007dcb  mov     rcx, [rdx]
0x140007dce  mov     rax, [rcx]
0x140007dd1  mov     rax, [rax+8]
0x140007dd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007dda  mov     rbx, [rsp+30h+arg_10]
0x140007de2  mov     eax, edi
0x140007de4  add     rsp, 30h
0x140007de8  pop     r15
0x140007dea  pop     r14
0x140007dec  pop     r13
0x140007dee  pop     r12
0x140007df0  pop     rdi
0x140007df1  pop     rsi
0x140007df2  pop     rbp
0x140007df3  retn
0x140007df4  call    cs:__imp__o__errno
0x140007dfa  mov     dword ptr [rax], 16h
0x140007e00  call    _invalid_parameter_noinfo
0x140007e05  xor     r9d, r9d
0x140007e08  jmp     loc_140007CBD
0x140007e0d  test    byte ptr [r10+1Ch], 2
0x140007e12  jnz     loc_140007F89
0x140007e18  cmp     r10, rsi
0x140007e1b  jz      short loc_140007DBA
0x140007e1d  test    byte ptr [r10+1Ch], 1
0x140007e22  jz      short loc_140007DBA
0x140007e24  movzx   edx, byte ptr [r10+19h]
0x140007e29  mov     eax, edi
0x140007e2b  neg     eax
0x140007e2d  sbb     ecx, ecx
0x140007e2f  and     ecx, 0FFFFFFFDh
0x140007e32  add     ecx, 5
0x140007e35  cmp     edx, ecx
0x140007e37  jb      short loc_140007DBA
0x140007e39  mov     rcx, [r10+10h]
0x140007e3d  lea     r8, WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids
0x140007e44  mov     edx, 9Eh
0x140007e49  mov     r9d, edi
0x140007e4c  call    WPP_SF_d
0x140007e51  jmp     loc_140007DBA
0x140007e56  inc     rdi
0x140007e59  cmp     [rsi+rdi*2], r9w
0x140007e5e  jnz     short loc_140007E56
0x140007e60  test    edi, edi
0x140007e62  jz      loc_140007C10
0x140007e68  mov     eax, [r15-0Ch]
0x140007e6c  mov     ecx, 1
0x140007e71  sub     ecx, [r15-8]
0x140007e75  sub     eax, edi
0x140007e77  or      ecx, eax
0x140007e79  mov     r13d, [r15-10h]
0x140007e7d  jge     short loc_140007E91
0x140007e7f  mov     edx, edi
0x140007e81  lea     rcx, [rbp+lpSubKey]
0x140007e85  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x140007e8a  mov     rbx, [rbp+lpSubKey]
0x140007e8e  xor     r9d, r9d
0x140007e91  movsxd  rax, edi
0x140007e94  lea     r14, [rax+rax]
0x140007e98  test    r14, r14
0x140007e9b  jz      loc_140007C36
0x140007ea1  mov     rcx, rsi
0x140007ea4  sub     rcx, r15
0x140007ea7  sar     rcx, 1
0x140007eaa  cmp     rcx, r13
0x140007ead  jbe     short loc_140007ECB
0x140007eaf  test    rbx, rbx
0x140007eb2  jz      loc_140007C22
0x140007eb8  mov     r8, r14; Size
0x140007ebb  mov     rdx, rsi; Src
0x140007ebe  mov     rcx, rbx; void *
0x140007ec1  call    memcpy_0
0x140007ec6  jmp     loc_140007C33
0x140007ecb  test    rbx, rbx
0x140007ece  jz      loc_140007C22
0x140007ed4  lea     rdx, [rbx+rcx*2]; Src
0x140007ed8  test    rdx, rdx
0x140007edb  jz      loc_140007C22
0x140007ee1  mov     r8, r14; Size
0x140007ee4  mov     rcx, rbx; void *
0x140007ee7  call    memmove_0
0x140007eec  jmp     loc_140007C33
0x140007ef1  test    byte ptr [rcx+1Ch], 1
0x140007ef5  jz      loc_140007BD0
0x140007efb  cmp     byte ptr [rcx+19h], 5
0x140007eff  jb      loc_140007BD0
0x140007f05  mov     rcx, [rcx+10h]
0x140007f09  lea     r8, WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids
0x140007f10  mov     edx, 9Ch
0x140007f15  mov     r9, r12
0x140007f18  call    WPP_SF_S
0x140007f1d  jmp     loc_140007BD0
0x140007f22  cmp     rsi, 10000h
0x140007f29  jnb     short loc_140007F3C
0x140007f2b  movzx   edx, si
0x140007f2e  lea     rcx, [rbp+lpSubKey]
0x140007f32  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::LoadStringW(uint)
0x140007f37  jmp     loc_140007C19
0x140007f3c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140007f40  jmp     loc_140007E56
0x140007f45  lea     r14, [rbx+rsi*2]
0x140007f49  jmp     loc_140007CA0
0x140007f4e  xor     eax, eax
0x140007f50  mov     [rcx], ax
0x140007f53  jmp     loc_140007DF4
0x140007f58  lea     r12, [rbx+r14*2]
0x140007f5c  jmp     loc_140007D24
0x140007f61  xor     edx, edx; Val
0x140007f63  call    memset_0
0x140007f68  call    cs:__imp__o__errno
0x140007f6e  mov     dword ptr [rax], 16h
0x140007f74  call    _invalid_parameter_noinfo
0x140007f79  jmp     loc_140007D4A
0x140007f7e  mov     ecx, 80070057h; int
0x140007f83  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140007f89  cmp     byte ptr [r10+19h], 4
0x140007f8e  jb      loc_140007E18
0x140007f94  mov     rcx, [r10+10h]
0x140007f98  lea     r8, WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids
0x140007f9f  mov     edx, 9Dh
0x140007fa4  mov     dword ptr [rsp+30h+phkResult], edi
0x140007fa8  mov     r9, rbx
0x140007fab  call    WPP_SF_Sd
0x140007fb0  mov     r10, cs:WPP_GLOBAL_Control
0x140007fb7  jmp     loc_140007E18
```
