# _ReadPolicies(void *,ulong *,_tagEASPolicy * *)

- ea: `0x18001a344`
- end: `0x18001a782`
- name: `?_ReadPolicies@@YAJPEAXPEAKPEAPEAU_tagEASPolicy@@@Z`
- size: `1086`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned int *, struct _tagEASPolicy **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019e3c`

## callees

- `0x18001a154`
- `0x18001a22c`
- `0x18001a344`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18001a5ab`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18001a5ab`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001a590`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001a590`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001a3e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001a3e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a745`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a753`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a745`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a753`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a44c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a49c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a4df`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a44c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a49c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a4df`

## string_xrefs

- `0x18001a421`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x18001a516`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x18001a5cb`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x18001a625`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x18001a6dd`: `onecore\ds\security\eas\policyengine\common.cpp`

## pseudocode

```c
__int64 __fastcall _ReadPolicies(HKEY hKey, unsigned int *a2, struct _tagEASPolicy **a3)
{
  unsigned int v3; // r12d
  struct _tagEASPolicy *v4; // r14
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  __int64 v7; // r8
  SIZE_T v8; // rdx
  WCHAR *v9; // r15
  BYTE *v10; // r13
  __int64 v11; // xmm6_8
  DWORD i; // ecx
  LSTATUS v13; // eax
  int v14; // ecx
  int v15; // r12d
  __int16 v16; // ax
  __int64 v17; // rax
  LPDWORD lpcSubKeys; // [rsp+28h] [rbp-79h]
  LPDWORD lpcSubKeysa; // [rsp+28h] [rbp-79h]
  const wchar_t *lpcbMaxSubKeyLen; // [rsp+30h] [rbp-71h]
  unsigned int v22; // [rsp+68h] [rbp-39h]
  DWORD cValues; // [rsp+6Ch] [rbp-35h] BYREF
  DWORD cbMaxValueLen; // [rsp+70h] [rbp-31h] BYREF
  DWORD cchValueName; // [rsp+74h] [rbp-2Dh] BYREF
  DWORD cbData; // [rsp+78h] [rbp-29h] BYREF
  DWORD Type; // [rsp+7Ch] [rbp-25h] BYREF
  DWORD v28; // [rsp+80h] [rbp-21h]
  int v29; // [rsp+84h] [rbp-1Dh]
  __int128 v30; // [rsp+88h] [rbp-19h]
  __int64 v31; // [rsp+98h] [rbp-9h]
  DWORD cbMaxValueNameLen; // [rsp+120h] [rbp+7Fh] BYREF

  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  v22 = 0;
  v3 = 0;
  v31 = 0;
  v4 = 0;
  *a2 = 0;
  *a3 = 0;
  v30 = 0;
  if ( !hKey )
    goto LABEL_2;
  v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  v5 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0xC0070000;
    v7 = v5;
    lpcbMaxSubKeyLen = L"RegQueryInfoKey";
    LODWORD(lpcSubKeys) = 496;
    goto LABEL_7;
  }
  if ( !cValues )
  {
LABEL_2:
    v5 = 0;
    goto LABEL_47;
  }
  v4 = (struct _tagEASPolicy *)LocalAlloc(0, 32LL * cValues);
  if ( !v4 )
  {
    v7 = 3221225495LL;
    lpcbMaxSubKeyLen = L"LocalAlloc";
    v5 = -1073741801;
    LODWORD(lpcSubKeys) = 510;
LABEL_7:
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      v7,
      L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
      lpcSubKeys,
      lpcbMaxSubKeyLen,
      &pszPassword);
    goto LABEL_47;
  }
  v8 = 2LL * ++cbMaxValueNameLen;
  v9 = (WCHAR *)LocalAlloc(0x40u, v8);
  if ( !v9 )
  {
    v5 = -1073741801;
    LODWORD(lpcSubKeys) = 519;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      3221225495LL,
      L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
      lpcSubKeys,
      L"LocalAlloc",
      &pszPassword);
    goto LABEL_47;
  }
  v10 = (BYTE *)LocalAlloc(0x40u, cbMaxValueLen);
  if ( !v10 )
  {
    v5 = -1073741801;
    LODWORD(lpcSubKeys) = 527;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      3221225495LL,
      L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
      lpcSubKeys,
      L"LocalAlloc",
      &pszPassword);
    goto LABEL_45;
  }
  v11 = v31;
  for ( i = 0; ; i = v28 + 1 )
  {
    v28 = i;
    if ( i >= cValues )
    {
      *a2 = v3;
      *a3 = v4;
      v4 = 0;
      v5 = 0;
      goto LABEL_45;
    }
    Type = 0;
    LOWORD(v30) = 0;
    cchValueName = cbMaxValueNameLen;
    cbData = cbMaxValueLen;
    v13 = RegEnumValueW(hKey, i, v9, &cchValueName, 0, &Type, v10, &cbData);
    v5 = v13;
    if ( v13 )
      break;
    v9[cchValueName] = 0;
    v29 = _o__wtoi(v9);
    v14 = v29;
    if ( v29 <= 0 )
    {
      LODWORD(lpcSubKeysa) = 560;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        3221225485LL,
        L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
        lpcSubKeysa,
        L"Invalid policy id",
        v9);
      continue;
    }
    if ( cbData )
    {
      if ( Type != 4 )
      {
        v15 = -2147024809;
        LODWORD(lpcSubKeysa) = 433;
        DbgPrintfW(
          1u,
          L"(0x%08x) %ws:%u : %ws:%ws\n",
          2147942487LL,
          L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
          lpcSubKeysa,
          L"invalid type",
          &pszPassword);
        v14 = v29;
        goto LABEL_27;
      }
      LOWORD(v30) = 19;
      DWORD2(v30) = *(_DWORD *)v10;
    }
    v15 = 0;
LABEL_27:
    v5 = 0;
    if ( v15 )
      v5 = v15 | 0x40000000;
    if ( v5 == -1073282985 )
    {
      v3 = v22;
    }
    else
    {
      if ( v5 )
      {
        LODWORD(lpcSubKeysa) = 574;
        DbgPrintfW(
          1u,
          L"(0x%08x) %ws:%u : %ws:%ws\n",
          v5,
          L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
          lpcSubKeysa,
          L"_RegValueToVariant",
          v9);
        v3 = v22;
        goto LABEL_45;
      }
      if ( v14 == 5 || v14 == 8 )
      {
        LOWORD(v30) = 11;
        if ( DWORD2(v30) )
          v16 = -1;
        else
          v16 = 0;
        WORD4(v30) = v16;
      }
      v17 = 32LL * v22;
      *(_OWORD *)((char *)v4 + v17 + 8) = v30;
      *(_DWORD *)((char *)v4 + v17) = v14;
      *(_QWORD *)((char *)v4 + v17 + 24) = v11;
      v3 = v22 + 1;
      LOWORD(v30) = 0;
      ++v22;
    }
  }
  if ( v13 > 0 )
    v5 = (unsigned __int16)v13 | 0xC0070000;
  LODWORD(lpcSubKeysa) = 552;
  DbgPrintfW(
    1u,
    L"(0x%08x) %ws:%u : %ws:%ws\n",
    v5,
    L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
    lpcSubKeysa,
    L"RegEnumValue",
    &pszPassword);
LABEL_45:
  LocalFree(v9);
  if ( v10 )
    LocalFree(v10);
LABEL_47:
  _FreePolicies(v3, v4);
  return v5;
}

```

## disassembly

```asm
0x18001a344  mov     rax, rsp
0x18001a347  mov     [rax+18h], r8
0x18001a34b  mov     [rax+10h], rdx
0x18001a34f  mov     [rax+8], rcx
0x18001a353  push    rbp
0x18001a354  push    rbx
0x18001a355  push    rsi
0x18001a356  push    rdi
0x18001a357  push    r12
0x18001a359  push    r13
0x18001a35b  push    r14
0x18001a35d  push    r15
0x18001a35f  lea     rbp, [rax-5Fh]
0x18001a363  sub     rsp, 0B8h
0x18001a36a  xor     esi, esi
0x18001a36c  movaps  xmmword ptr [rax-58h], xmm6
0x18001a370  mov     rax, rcx
0x18001a373  mov     [rbp+57h+cValues], esi
0x18001a376  xor     ecx, ecx
0x18001a378  mov     [rbp+57h+cbMaxValueNameLen], esi
0x18001a37b  mov     [rbp+57h+cbMaxValueLen], esi
0x18001a37e  xorps   xmm0, xmm0
0x18001a381  mov     [rbp+57h+var_90], esi
0x18001a384  mov     r12d, esi
0x18001a387  mov     [rbp+57h+var_60], rcx
0x18001a38b  mov     r14d, esi
0x18001a38e  mov     [rdx], esi
0x18001a390  mov     [r8], rsi
0x18001a393  movups  [rbp+57h+var_70], xmm0
0x18001a397  test    rax, rax
0x18001a39a  jnz     short loc_18001A3A3
0x18001a39c  mov     ebx, esi
0x18001a39e  jmp     loc_18001A759
0x18001a3a3  mov     [rsp+58h], rsi; lpftLastWriteTime
0x18001a3a8  lea     rcx, [rbp+57h+cbMaxValueLen]
0x18001a3ac  mov     [rsp+0F0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18001a3b1  xor     r9d, r9d; lpReserved
0x18001a3b4  mov     [rsp+0F0h+lpcbMaxValueLen], rcx; lpcbMaxValueLen
0x18001a3b9  xor     r8d, r8d; lpcchClass
0x18001a3bc  lea     rcx, [rbp+57h+cbMaxValueNameLen]
0x18001a3c0  xor     edx, edx; lpClass
0x18001a3c2  mov     [rsp+0F0h+lpcbMaxValueNameLen], rcx; lpcbMaxValueNameLen
0x18001a3c7  lea     rcx, [rbp+57h+cValues]
0x18001a3cb  mov     [rsp+0F0h+lpcValues], rcx; lpcValues
0x18001a3d0  mov     rcx, rax; hKey
0x18001a3d3  mov     [rsp+0F0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x18001a3d8  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x18001a3dd  mov     [rsp+0F0h+lpcSubKeys], rsi; lpcSubKeys
0x18001a3e2  call    cs:__imp_RegQueryInfoKeyW
0x18001a3e8  mov     ebx, eax
0x18001a3ea  test    eax, eax
0x18001a3ec  jz      short loc_18001A439
0x18001a3ee  jle     short loc_18001A3F9
0x18001a3f0  movzx   ebx, ax
0x18001a3f3  or      ebx, 0C0070000h
0x18001a3f9  lea     rsi, pszPassword
0x18001a400  mov     r8d, ebx
0x18001a403  mov     [rsp+0F0h+lpcbMaxClassLen], rsi
0x18001a408  lea     rax, aRegqueryinfoke; "RegQueryInfoKey"
0x18001a40f  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax
0x18001a414  mov     dword ptr [rsp+0F0h+lpcSubKeys], 1F0h
0x18001a41c  mov     ecx, 1; unsigned int
0x18001a421  lea     r9, aOnecoreDsSecur; "onecore\\ds\\security\\eas\\policyengin"...
0x18001a428  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18001a42f  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18001a434  jmp     loc_18001A759
0x18001a439  mov     eax, [rbp+57h+cValues]
0x18001a43c  test    eax, eax
0x18001a43e  jz      loc_18001A39C
0x18001a444  mov     edx, eax
0x18001a446  xor     ecx, ecx; uFlags
0x18001a448  shl     rdx, 5; uBytes
0x18001a44c  call    cs:__imp_LocalAlloc
0x18001a452  mov     r14, rax
0x18001a455  test    rax, rax
0x18001a458  jnz     short loc_18001A485
0x18001a45a  lea     rsi, pszPassword
0x18001a461  mov     r8d, 0C0000017h
0x18001a467  mov     [rsp+0F0h+lpcbMaxClassLen], rsi
0x18001a46c  lea     rcx, aLocalalloc; "LocalAlloc"
0x18001a473  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rcx
0x18001a478  mov     ebx, r8d
0x18001a47b  mov     dword ptr [rsp+0F0h+lpcSubKeys], 1FEh
0x18001a483  jmp     short loc_18001A41C
0x18001a485  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18001a488  mov     edi, 1
0x18001a48d  add     eax, edi
0x18001a48f  mov     edx, eax
0x18001a491  add     rdx, rdx; uBytes
0x18001a494  mov     [rbp+57h+cbMaxValueNameLen], eax
0x18001a497  lea     ebx, [rdi+3Fh]
0x18001a49a  mov     ecx, ebx; uFlags
0x18001a49c  call    cs:__imp_LocalAlloc
0x18001a4a2  mov     r15, rax
0x18001a4a5  test    rax, rax
0x18001a4a8  jnz     short loc_18001A4DA
0x18001a4aa  lea     rcx, aLocalalloc; "LocalAlloc"
0x18001a4b1  mov     r8d, 0C0000017h
0x18001a4b7  lea     rsi, pszPassword
0x18001a4be  mov     ebx, r8d
0x18001a4c1  mov     [rsp+0F0h+lpcbMaxClassLen], rsi
0x18001a4c6  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rcx
0x18001a4cb  mov     ecx, edi
0x18001a4cd  mov     dword ptr [rsp+0F0h+lpcSubKeys], 207h
0x18001a4d5  jmp     loc_18001A421
0x18001a4da  mov     edx, [rbp+57h+cbMaxValueLen]; uBytes
0x18001a4dd  mov     ecx, ebx; uFlags
0x18001a4df  call    cs:__imp_LocalAlloc
0x18001a4e5  mov     r13, rax
0x18001a4e8  test    rax, rax
0x18001a4eb  jnz     short loc_18001A530
0x18001a4ed  lea     rsi, pszPassword
0x18001a4f4  mov     r8d, 0C0000017h
0x18001a4fa  mov     [rsp+0F0h+lpcbMaxClassLen], rsi
0x18001a4ff  lea     rcx, aLocalalloc; "LocalAlloc"
0x18001a506  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rcx
0x18001a50b  mov     ebx, r8d
0x18001a50e  mov     dword ptr [rsp+0F0h+lpcSubKeys], 20Fh
0x18001a516  lea     r9, aOnecoreDsSecur; "onecore\\ds\\security\\eas\\policyengin"...
0x18001a51d  mov     ecx, edi; unsigned int
0x18001a51f  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18001a526  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18001a52b  jmp     loc_18001A742
0x18001a530  movsd   xmm6, [rbp+57h+var_60]
0x18001a535  mov     ecx, esi
0x18001a537  lea     rsi, pszPassword
0x18001a53e  mov     [rbp+57h+var_78], ecx
0x18001a541  cmp     ecx, [rbp+57h+cValues]
0x18001a544  jnb     loc_18001A72F
0x18001a54a  xor     eax, eax
0x18001a54c  mov     [rbp+57h+Type], 0
0x18001a553  mov     word ptr [rbp+57h+var_70], ax
0x18001a557  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18001a55b  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18001a55e  mov     edx, ecx; dwIndex
0x18001a560  mov     rcx, [rbp+57h+hKey]; hKey
0x18001a564  mov     r8, r15; lpValueName
0x18001a567  mov     [rbp+57h+cchValueName], eax
0x18001a56a  mov     eax, [rbp+57h+cbMaxValueLen]
0x18001a56d  mov     [rbp+57h+cbData], eax
0x18001a570  lea     rax, [rbp+57h+cbData]
0x18001a574  mov     [rsp+0F0h+lpcValues], rax; lpcbData
0x18001a579  lea     rax, [rbp+57h+Type]
0x18001a57d  mov     [rsp+0F0h+lpcbMaxClassLen], r13; lpData
0x18001a582  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax; lpType
0x18001a587  mov     [rsp+0F0h+lpcSubKeys], 0; lpReserved
0x18001a590  call    cs:__imp_RegEnumValueW
0x18001a596  mov     ebx, eax
0x18001a598  test    eax, eax
0x18001a59a  jnz     loc_18001A703
0x18001a5a0  mov     ecx, [rbp+57h+cchValueName]
0x18001a5a3  mov     [r15+rcx*2], ax
0x18001a5a8  mov     rcx, r15
0x18001a5ab  call    cs:__imp__o__wtoi
0x18001a5b1  mov     [rbp+57h+var_74], eax
0x18001a5b4  mov     ecx, eax
0x18001a5b6  test    eax, eax
0x18001a5b8  jg      short loc_18001A5F3
0x18001a5ba  lea     rax, aInvalidPolicyI; "Invalid policy id"
0x18001a5c1  mov     [rsp+0F0h+lpcbMaxClassLen], r15
0x18001a5c6  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax
0x18001a5cb  lea     r9, aOnecoreDsSecur; "onecore\\ds\\security\\eas\\policyengin"...
0x18001a5d2  mov     r8d, 0C000000Dh
0x18001a5d8  mov     dword ptr [rsp+0F0h+lpcSubKeys], 230h
0x18001a5e0  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18001a5e7  mov     ecx, edi; unsigned int
0x18001a5e9  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18001a5ee  jmp     loc_18001A6C2
0x18001a5f3  cmp     [rbp+57h+cbData], 0
0x18001a5f7  jz      short loc_18001A64D
0x18001a5f9  cmp     [rbp+57h+Type], 4
0x18001a5fd  jz      short loc_18001A63D
0x18001a5ff  mov     ecx, 80070057h
0x18001a604  mov     [rsp+0F0h+lpcbMaxClassLen], rsi
0x18001a609  lea     rax, aInvalidType; "invalid type"
0x18001a610  mov     r12d, ecx
0x18001a613  mov     r8d, ecx
0x18001a616  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax
0x18001a61b  mov     ecx, edi; unsigned int
0x18001a61d  mov     dword ptr [rsp+0F0h+lpcSubKeys], 1B1h
0x18001a625  lea     r9, aOnecoreDsSecur; "onecore\\ds\\security\\eas\\policyengin"...
0x18001a62c  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18001a633  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18001a638  mov     ecx, [rbp+57h+var_74]
0x18001a63b  jmp     short loc_18001A650
0x18001a63d  mov     eax, 13h
0x18001a642  mov     word ptr [rbp+57h+var_70], ax
0x18001a646  mov     eax, [r13+0]
0x18001a64a  mov     dword ptr [rbp+57h+var_70+8], eax
0x18001a64d  xor     r12d, r12d
0x18001a650  xor     ebx, ebx
0x18001a652  mov     eax, r12d
0x18001a655  bts     eax, 1Eh
0x18001a659  test    r12d, r12d
0x18001a65c  cmovnz  ebx, eax
0x18001a65f  cmp     ebx, 0C0070057h
0x18001a665  jz      short loc_18001A6BE
0x18001a667  test    ebx, ebx
0x18001a669  jnz     short loc_18001A6CC
0x18001a66b  cmp     ecx, 5
0x18001a66e  jz      short loc_18001A675
0x18001a670  cmp     ecx, 8
0x18001a673  jnz     short loc_18001A68F
0x18001a675  cmp     dword ptr [rbp+57h+var_70+8], 0
0x18001a679  mov     eax, 0Bh
0x18001a67e  mov     word ptr [rbp+57h+var_70], ax
0x18001a682  jz      short loc_18001A689
0x18001a684  or      eax, 0FFFFFFFFh
0x18001a687  jmp     short loc_18001A68B
0x18001a689  xor     eax, eax
0x18001a68b  mov     word ptr [rbp+57h+var_70+8], ax
0x18001a68f  mov     r12d, [rbp+57h+var_90]
0x18001a693  movups  xmm0, [rbp+57h+var_70]
0x18001a697  mov     eax, r12d
0x18001a69a  shl     rax, 5
0x18001a69e  movups  xmmword ptr [rax+r14+8], xmm0
0x18001a6a4  mov     [rax+r14], ecx
0x18001a6a8  movsd   qword ptr [rax+r14+18h], xmm6
0x18001a6af  xor     eax, eax
0x18001a6b1  add     r12d, edi
0x18001a6b4  mov     word ptr [rbp+57h+var_70], ax
0x18001a6b8  mov     [rbp+57h+var_90], r12d
0x18001a6bc  jmp     short loc_18001A6C2
0x18001a6be  mov     r12d, [rbp+57h+var_90]
0x18001a6c2  mov     ecx, [rbp+57h+var_78]
0x18001a6c5  add     ecx, edi
0x18001a6c7  jmp     loc_18001A53E
0x18001a6cc  lea     rax, aRegvaluetovari; "_RegValueToVariant"
0x18001a6d3  mov     [rsp+0F0h+lpcbMaxClassLen], r15
0x18001a6d8  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax
0x18001a6dd  lea     r9, aOnecoreDsSecur; "onecore\\ds\\security\\eas\\policyengin"...
0x18001a6e4  mov     r8d, ebx
0x18001a6e7  mov     dword ptr [rsp+0F0h+lpcSubKeys], 23Eh
0x18001a6ef  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18001a6f6  mov     ecx, edi; unsigned int
0x18001a6f8  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18001a6fd  mov     r12d, [rbp+57h+var_90]
0x18001a701  jmp     short loc_18001A742
0x18001a703  jle     short loc_18001A70E
0x18001a705  movzx   ebx, ax
0x18001a708  or      ebx, 0C0070000h
0x18001a70e  mov     [rsp+0F0h+lpcbMaxClassLen], rsi
0x18001a713  lea     rax, aRegenumvalue; "RegEnumValue"
0x18001a71a  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax
0x18001a71f  mov     r8d, ebx
0x18001a722  mov     dword ptr [rsp+0F0h+lpcSubKeys], 228h
0x18001a72a  jmp     loc_18001A516
0x18001a72f  mov     rax, [rbp+57h+arg_8]
0x18001a733  mov     [rax], r12d
0x18001a736  mov     rax, [rbp+57h+arg_10]
0x18001a73a  mov     [rax], r14
0x18001a73d  xor     r14d, r14d
0x18001a740  xor     ebx, ebx
0x18001a742  mov     rcx, r15; hMem
0x18001a745  call    cs:__imp_LocalFree
0x18001a74b  test    r13, r13
0x18001a74e  jz      short loc_18001A759
0x18001a750  mov     rcx, r13; hMem
0x18001a753  call    cs:__imp_LocalFree
0x18001a759  mov     rdx, r14; struct _tagEASPolicy *
0x18001a75c  mov     ecx, r12d; unsigned int
0x18001a75f  call    ?_FreePolicies@@YAXKPEAU_tagEASPolicy@@@Z; _FreePolicies(ulong,_tagEASPolicy *)
0x18001a764  movaps  xmm6, [rsp+0F0h+var_58+8]
0x18001a76c  mov     eax, ebx
0x18001a76e  add     rsp, 0B8h
0x18001a775  pop     r15
0x18001a777  pop     r14
0x18001a779  pop     r13
0x18001a77b  pop     r12
0x18001a77d  pop     rdi
0x18001a77e  pop     rsi
0x18001a77f  pop     rbx
0x18001a780  pop     rbp
0x18001a781  retn
```
