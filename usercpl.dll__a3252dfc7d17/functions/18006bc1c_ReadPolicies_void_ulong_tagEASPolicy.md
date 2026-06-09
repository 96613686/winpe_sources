# _ReadPolicies(void *,ulong *,_tagEASPolicy * *)

- ea: `0x18006bc1c`
- end: `0x18006c067`
- name: `?_ReadPolicies@@YAJPEAXPEAKPEAPEAU_tagEASPolicy@@@Z`
- size: `1099`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned int *, struct _tagEASPolicy **)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011988`
- `0x180069bf0`
- `0x180069de8`

## callees

- `0x18006a608`
- `0x18006b660`
- `0x18006bc1c`

## import_xrefs

- `msvcrt!_wtoi` at `0x18006be83`
- `msvcrt!_wtoi` at `0x18006be83`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006bd24`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006bd74`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006bdb7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006bd24`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006bd74`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006bdb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bfc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bfd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bfc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bfd5`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18006be68`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18006be68`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006bcba`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006bcba`

## string_xrefs

- `0x18006bcf9`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x18006bdee`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x18006bea3`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x18006befd`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x18006c015`: `onecore\ds\security\eas\policyengine\common.cpp`

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
  DWORD v11; // ecx
  __int64 v12; // xmm6_8
  LSTATUS v13; // eax
  int v14; // ecx
  int v15; // r12d
  __int16 v16; // ax
  unsigned int v17; // r12d
  __int64 v18; // rax
  LPDWORD lpcSubKeys; // [rsp+28h] [rbp-79h]
  LPDWORD lpcSubKeysa; // [rsp+28h] [rbp-79h]
  const wchar_t *lpcbMaxSubKeyLen; // [rsp+30h] [rbp-71h]
  DWORD cValues; // [rsp+68h] [rbp-39h] BYREF
  unsigned int v24; // [rsp+6Ch] [rbp-35h]
  DWORD cbMaxValueLen; // [rsp+70h] [rbp-31h] BYREF
  DWORD cchValueName; // [rsp+74h] [rbp-2Dh] BYREF
  DWORD cbData; // [rsp+78h] [rbp-29h] BYREF
  DWORD Type; // [rsp+7Ch] [rbp-25h] BYREF
  DWORD v29; // [rsp+80h] [rbp-21h]
  int v30; // [rsp+84h] [rbp-1Dh]
  __int128 v31; // [rsp+88h] [rbp-19h]
  __int64 v32; // [rsp+98h] [rbp-9h]
  DWORD cbMaxValueNameLen; // [rsp+120h] [rbp+7Fh] BYREF

  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  v24 = 0;
  v3 = 0;
  v32 = 0;
  v4 = 0;
  *a2 = 0;
  *a3 = 0;
  v31 = 0;
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
    goto LABEL_43;
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
      &Class);
    goto LABEL_43;
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
      &Class);
    goto LABEL_43;
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
      &Class);
    goto LABEL_41;
  }
  v11 = 0;
  v29 = 0;
  if ( !cValues )
  {
LABEL_40:
    v5 = 0;
    *a2 = v3;
    *a3 = v4;
    v4 = 0;
    goto LABEL_41;
  }
  v12 = v32;
  while ( 1 )
  {
    Type = 0;
    LOWORD(v31) = 0;
    cchValueName = cbMaxValueNameLen;
    cbData = cbMaxValueLen;
    v13 = RegEnumValueW(hKey, v11, v9, &cchValueName, 0, &Type, v10, &cbData);
    v5 = v13;
    if ( v13 )
      break;
    v9[cchValueName] = 0;
    v30 = _wtoi(v9);
    v14 = v30;
    if ( v30 <= 0 )
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
      goto LABEL_39;
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
          &Class);
        v14 = v30;
        goto LABEL_27;
      }
      LOWORD(v31) = 19;
      DWORD2(v31) = *(_DWORD *)v10;
    }
    v15 = 0;
LABEL_27:
    v5 = 0;
    if ( v15 )
      v5 = v15 | 0x40000000;
    if ( v5 == -1073282985 )
    {
      v3 = v24;
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
        v3 = v24;
        goto LABEL_41;
      }
      if ( v14 == 5 || v14 == 8 )
      {
        LOWORD(v31) = 11;
        if ( DWORD2(v31) )
          v16 = -1;
        else
          v16 = 0;
        WORD4(v31) = v16;
      }
      v17 = v24;
      v18 = 32LL * v24;
      *(_OWORD *)((char *)v4 + v18 + 8) = v31;
      *(_DWORD *)((char *)v4 + v18) = v14;
      *(_QWORD *)((char *)v4 + v18 + 24) = v12;
      v3 = v17 + 1;
      LOWORD(v31) = 0;
      v24 = v3;
    }
LABEL_39:
    v11 = v29 + 1;
    v29 = v11;
    if ( v11 >= cValues )
      goto LABEL_40;
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
    &Class);
LABEL_41:
  LocalFree(v9);
  if ( v10 )
    LocalFree(v10);
LABEL_43:
  _FreePolicies(v3, v4);
  return v5;
}

```

## disassembly

```asm
0x18006bc1c  mov     rax, rsp
0x18006bc1f  mov     [rax+18h], r8
0x18006bc23  mov     [rax+10h], rdx
0x18006bc27  mov     [rax+8], rcx
0x18006bc2b  push    rbp
0x18006bc2c  push    rbx
0x18006bc2d  push    rsi
0x18006bc2e  push    rdi
0x18006bc2f  push    r12
0x18006bc31  push    r13
0x18006bc33  push    r14
0x18006bc35  push    r15
0x18006bc37  lea     rbp, [rax-5Fh]
0x18006bc3b  sub     rsp, 0B8h
0x18006bc42  xor     esi, esi
0x18006bc44  movaps  xmmword ptr [rax-58h], xmm6
0x18006bc48  mov     rax, rcx
0x18006bc4b  mov     [rbp+57h+cValues], esi
0x18006bc4e  xor     ecx, ecx
0x18006bc50  mov     [rbp+57h+cbMaxValueNameLen], esi
0x18006bc53  mov     [rbp+57h+cbMaxValueLen], esi
0x18006bc56  xorps   xmm0, xmm0
0x18006bc59  mov     [rbp+57h+var_8C], esi
0x18006bc5c  mov     r12d, esi
0x18006bc5f  mov     [rbp+57h+var_60], rcx
0x18006bc63  mov     r14d, esi
0x18006bc66  mov     [rdx], esi
0x18006bc68  mov     [r8], rsi
0x18006bc6b  movups  [rbp+57h+var_70], xmm0
0x18006bc6f  test    rax, rax
0x18006bc72  jnz     short loc_18006BC7B
0x18006bc74  mov     ebx, esi
0x18006bc76  jmp     loc_18006BFDB
0x18006bc7b  mov     [rsp+58h], rsi; lpftLastWriteTime
0x18006bc80  lea     rcx, [rbp+57h+cbMaxValueLen]
0x18006bc84  mov     [rsp+0F0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18006bc89  xor     r9d, r9d; lpReserved
0x18006bc8c  mov     [rsp+0F0h+lpcbMaxValueLen], rcx; lpcbMaxValueLen
0x18006bc91  xor     r8d, r8d; lpcchClass
0x18006bc94  lea     rcx, [rbp+57h+cbMaxValueNameLen]
0x18006bc98  xor     edx, edx; lpClass
0x18006bc9a  mov     [rsp+0F0h+lpcbMaxValueNameLen], rcx; lpcbMaxValueNameLen
0x18006bc9f  lea     rcx, [rbp+57h+cValues]
0x18006bca3  mov     [rsp+0F0h+lpcValues], rcx; lpcValues
0x18006bca8  mov     rcx, rax; hKey
0x18006bcab  mov     [rsp+0F0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x18006bcb0  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x18006bcb5  mov     [rsp+0F0h+lpcSubKeys], rsi; lpcSubKeys
0x18006bcba  call    cs:__imp_RegQueryInfoKeyW
0x18006bcc0  mov     ebx, eax
0x18006bcc2  test    eax, eax
0x18006bcc4  jz      short loc_18006BD11
0x18006bcc6  jle     short loc_18006BCD1
0x18006bcc8  movzx   ebx, ax
0x18006bccb  or      ebx, 0C0070000h
0x18006bcd1  lea     rsi, Class
0x18006bcd8  mov     r8d, ebx
0x18006bcdb  mov     [rsp+0F0h+lpcbMaxClassLen], rsi
0x18006bce0  lea     rax, aRegqueryinfoke; "RegQueryInfoKey"
0x18006bce7  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax
0x18006bcec  mov     dword ptr [rsp+0F0h+lpcSubKeys], 1F0h
0x18006bcf4  mov     ecx, 1; unsigned int
0x18006bcf9  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x18006bd00  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006bd07  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006bd0c  jmp     loc_18006BFDB
0x18006bd11  mov     eax, [rbp+57h+cValues]
0x18006bd14  test    eax, eax
0x18006bd16  jz      loc_18006BC74
0x18006bd1c  mov     edx, eax
0x18006bd1e  xor     ecx, ecx; uFlags
0x18006bd20  shl     rdx, 5; uBytes
0x18006bd24  call    cs:__imp_LocalAlloc
0x18006bd2a  mov     r14, rax
0x18006bd2d  test    rax, rax
0x18006bd30  jnz     short loc_18006BD5D
0x18006bd32  lea     rsi, Class
0x18006bd39  mov     r8d, 0C0000017h
0x18006bd3f  mov     [rsp+0F0h+lpcbMaxClassLen], rsi
0x18006bd44  lea     rcx, aLocalalloc; "LocalAlloc"
0x18006bd4b  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rcx
0x18006bd50  mov     ebx, r8d
0x18006bd53  mov     dword ptr [rsp+0F0h+lpcSubKeys], 1FEh
0x18006bd5b  jmp     short loc_18006BCF4
0x18006bd5d  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18006bd60  mov     edi, 1
0x18006bd65  add     eax, edi
0x18006bd67  mov     edx, eax
0x18006bd69  add     rdx, rdx; uBytes
0x18006bd6c  mov     [rbp+57h+cbMaxValueNameLen], eax
0x18006bd6f  lea     ebx, [rdi+3Fh]
0x18006bd72  mov     ecx, ebx; uFlags
0x18006bd74  call    cs:__imp_LocalAlloc
0x18006bd7a  mov     r15, rax
0x18006bd7d  test    rax, rax
0x18006bd80  jnz     short loc_18006BDB2
0x18006bd82  lea     rcx, aLocalalloc; "LocalAlloc"
0x18006bd89  mov     r8d, 0C0000017h
0x18006bd8f  lea     rsi, Class
0x18006bd96  mov     ebx, r8d
0x18006bd99  mov     [rsp+0F0h+lpcbMaxClassLen], rsi
0x18006bd9e  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rcx
0x18006bda3  mov     ecx, edi
0x18006bda5  mov     dword ptr [rsp+0F0h+lpcSubKeys], 207h
0x18006bdad  jmp     loc_18006BCF9
0x18006bdb2  mov     edx, [rbp+57h+cbMaxValueLen]; uBytes
0x18006bdb5  mov     ecx, ebx; uFlags
0x18006bdb7  call    cs:__imp_LocalAlloc
0x18006bdbd  mov     r13, rax
0x18006bdc0  test    rax, rax
0x18006bdc3  jnz     short loc_18006BE08
0x18006bdc5  lea     rsi, Class
0x18006bdcc  mov     r8d, 0C0000017h
0x18006bdd2  mov     [rsp+0F0h+lpcbMaxClassLen], rsi
0x18006bdd7  lea     rcx, aLocalalloc; "LocalAlloc"
0x18006bdde  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rcx
0x18006bde3  mov     ebx, r8d
0x18006bde6  mov     dword ptr [rsp+0F0h+lpcSubKeys], 20Fh
0x18006bdee  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x18006bdf5  mov     ecx, edi; unsigned int
0x18006bdf7  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006bdfe  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006be03  jmp     loc_18006BFC4
0x18006be08  mov     ecx, esi
0x18006be0a  mov     [rbp+57h+var_78], ecx
0x18006be0d  cmp     [rbp+57h+cValues], esi
0x18006be10  jbe     loc_18006BFB1
0x18006be16  movsd   xmm6, [rbp+57h+var_60]
0x18006be1b  lea     rsi, Class
0x18006be22  xor     eax, eax
0x18006be24  mov     [rbp+57h+Type], 0
0x18006be2b  mov     word ptr [rbp+57h+var_70], ax
0x18006be2f  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18006be33  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18006be36  mov     edx, ecx; dwIndex
0x18006be38  mov     rcx, [rbp+57h+hKey]; hKey
0x18006be3c  mov     r8, r15; lpValueName
0x18006be3f  mov     [rbp+57h+cchValueName], eax
0x18006be42  mov     eax, [rbp+57h+cbMaxValueLen]
0x18006be45  mov     [rbp+57h+cbData], eax
0x18006be48  lea     rax, [rbp+57h+cbData]
0x18006be4c  mov     [rsp+0F0h+lpcValues], rax; lpcbData
0x18006be51  lea     rax, [rbp+57h+Type]
0x18006be55  mov     [rsp+0F0h+lpcbMaxClassLen], r13; lpData
0x18006be5a  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax; lpType
0x18006be5f  mov     [rsp+0F0h+lpcSubKeys], 0; lpReserved
0x18006be68  call    cs:__imp_RegEnumValueW
0x18006be6e  mov     ebx, eax
0x18006be70  test    eax, eax
0x18006be72  jnz     loc_18006C03B
0x18006be78  mov     ecx, [rbp+57h+cchValueName]
0x18006be7b  mov     [r15+rcx*2], ax
0x18006be80  mov     rcx, r15; String
0x18006be83  call    cs:__imp__wtoi
0x18006be89  mov     [rbp+57h+var_74], eax
0x18006be8c  mov     ecx, eax
0x18006be8e  test    eax, eax
0x18006be90  jg      short loc_18006BECB
0x18006be92  lea     rax, aInvalidPolicyI; "Invalid policy id"
0x18006be99  mov     [rsp+0F0h+lpcbMaxClassLen], r15
0x18006be9e  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax
0x18006bea3  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x18006beaa  mov     r8d, 0C000000Dh
0x18006beb0  mov     dword ptr [rsp+0F0h+lpcSubKeys], 230h
0x18006beb8  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006bebf  mov     ecx, edi; unsigned int
0x18006bec1  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006bec6  jmp     loc_18006BF9E
0x18006becb  cmp     [rbp+57h+cbData], 0
0x18006becf  jz      short loc_18006BF25
0x18006bed1  cmp     [rbp+57h+Type], 4
0x18006bed5  jz      short loc_18006BF15
0x18006bed7  mov     ecx, 80070057h
0x18006bedc  mov     [rsp+0F0h+lpcbMaxClassLen], rsi
0x18006bee1  lea     rax, aInvalidType; "invalid type"
0x18006bee8  mov     r12d, ecx
0x18006beeb  mov     r8d, ecx
0x18006beee  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax
0x18006bef3  mov     ecx, edi; unsigned int
0x18006bef5  mov     dword ptr [rsp+0F0h+lpcSubKeys], 1B1h
0x18006befd  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x18006bf04  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006bf0b  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006bf10  mov     ecx, [rbp+57h+var_74]
0x18006bf13  jmp     short loc_18006BF28
0x18006bf15  mov     eax, 13h
0x18006bf1a  mov     word ptr [rbp+57h+var_70], ax
0x18006bf1e  mov     eax, [r13+0]
0x18006bf22  mov     dword ptr [rbp+57h+var_70+8], eax
0x18006bf25  xor     r12d, r12d
0x18006bf28  xor     ebx, ebx
0x18006bf2a  mov     eax, r12d
0x18006bf2d  bts     eax, 1Eh
0x18006bf31  test    r12d, r12d
0x18006bf34  cmovnz  ebx, eax
0x18006bf37  cmp     ebx, 0C0070057h
0x18006bf3d  jz      short loc_18006BF9A
0x18006bf3f  test    ebx, ebx
0x18006bf41  jnz     loc_18006C004
0x18006bf47  cmp     ecx, 5
0x18006bf4a  jz      short loc_18006BF51
0x18006bf4c  cmp     ecx, 8
0x18006bf4f  jnz     short loc_18006BF6B
0x18006bf51  cmp     dword ptr [rbp+57h+var_70+8], 0
0x18006bf55  mov     eax, 0Bh
0x18006bf5a  mov     word ptr [rbp+57h+var_70], ax
0x18006bf5e  jz      short loc_18006BF65
0x18006bf60  or      eax, 0FFFFFFFFh
0x18006bf63  jmp     short loc_18006BF67
0x18006bf65  xor     eax, eax
0x18006bf67  mov     word ptr [rbp+57h+var_70+8], ax
0x18006bf6b  mov     r12d, [rbp+57h+var_8C]
0x18006bf6f  movups  xmm0, [rbp+57h+var_70]
0x18006bf73  mov     eax, r12d
0x18006bf76  shl     rax, 5
0x18006bf7a  movups  xmmword ptr [rax+r14+8], xmm0
0x18006bf80  mov     [rax+r14], ecx
0x18006bf84  movsd   qword ptr [rax+r14+18h], xmm6
0x18006bf8b  xor     eax, eax
0x18006bf8d  add     r12d, edi
0x18006bf90  mov     word ptr [rbp+57h+var_70], ax
0x18006bf94  mov     [rbp+57h+var_8C], r12d
0x18006bf98  jmp     short loc_18006BF9E
0x18006bf9a  mov     r12d, [rbp+57h+var_8C]
0x18006bf9e  mov     ecx, [rbp+57h+var_78]
0x18006bfa1  add     ecx, edi
0x18006bfa3  mov     [rbp+57h+var_78], ecx
0x18006bfa6  cmp     ecx, [rbp+57h+cValues]
0x18006bfa9  jb      loc_18006BE22
0x18006bfaf  xor     esi, esi
0x18006bfb1  mov     rax, [rbp+57h+arg_8]
0x18006bfb5  mov     ebx, esi
0x18006bfb7  mov     [rax], r12d
0x18006bfba  mov     rax, [rbp+57h+arg_10]
0x18006bfbe  mov     [rax], r14
0x18006bfc1  mov     r14, rsi
0x18006bfc4  mov     rcx, r15; hMem
0x18006bfc7  call    cs:__imp_LocalFree
0x18006bfcd  test    r13, r13
0x18006bfd0  jz      short loc_18006BFDB
0x18006bfd2  mov     rcx, r13; hMem
0x18006bfd5  call    cs:__imp_LocalFree
0x18006bfdb  mov     rdx, r14; struct _tagEASPolicy *
0x18006bfde  mov     ecx, r12d; unsigned int
0x18006bfe1  call    ?_FreePolicies@@YAXKPEAU_tagEASPolicy@@@Z; _FreePolicies(ulong,_tagEASPolicy *)
0x18006bfe6  movaps  xmm6, [rsp+0F0h+var_58+8]
0x18006bfee  mov     eax, ebx
0x18006bff0  add     rsp, 0B8h
0x18006bff7  pop     r15
0x18006bff9  pop     r14
0x18006bffb  pop     r13
0x18006bffd  pop     r12
0x18006bfff  pop     rdi
0x18006c000  pop     rsi
0x18006c001  pop     rbx
0x18006c002  pop     rbp
0x18006c003  retn
0x18006c004  lea     rax, aRegvaluetovari; "_RegValueToVariant"
0x18006c00b  mov     [rsp+0F0h+lpcbMaxClassLen], r15
0x18006c010  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax
0x18006c015  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x18006c01c  mov     r8d, ebx
0x18006c01f  mov     dword ptr [rsp+0F0h+lpcSubKeys], 23Eh
0x18006c027  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006c02e  mov     ecx, edi; unsigned int
0x18006c030  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006c035  mov     r12d, [rbp+57h+var_8C]
0x18006c039  jmp     short loc_18006BFC4
0x18006c03b  jle     short loc_18006C046
0x18006c03d  movzx   ebx, ax
0x18006c040  or      ebx, 0C0070000h
0x18006c046  mov     [rsp+0F0h+lpcbMaxClassLen], rsi
0x18006c04b  lea     rax, aRegenumvalue; "RegEnumValue"
0x18006c052  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax
0x18006c057  mov     r8d, ebx
0x18006c05a  mov     dword ptr [rsp+0F0h+lpcSubKeys], 228h
0x18006c062  jmp     loc_18006BDEE
```
