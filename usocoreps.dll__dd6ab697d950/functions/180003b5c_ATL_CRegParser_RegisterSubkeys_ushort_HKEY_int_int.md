# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180003b5c`
- end: `0x1800042f3`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x1800037e8`
- `0x180003b5c`

## callees

- `0x180001510`
- `0x18000271c`
- `0x180002f18`
- `0x180002f30`
- `0x180003054`
- `0x1800031f4`
- `0x180003698`
- `0x180003b5c`
- `0x18000430c`
- `0x180004e40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000403a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000403a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003da2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003e50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003e99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003fe8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003da2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003e50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003e99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003fe8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003dd8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003e64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003ead`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003f0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004003`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000421a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004274`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800042b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800042c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003dd8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003e64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003ead`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003f0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004003`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000421a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004274`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800042b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800042c0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003ef7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003ef7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180003dbf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180003dbf`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180004166`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800041fc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180004166`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800041fc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003c3e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003e09`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003c3e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003e09`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180003bd9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180003bec`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180003c6a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180003cd3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180003d01`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004189`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180003bd9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180003bec`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180003c6a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180003cd3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180003d01`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004189`

## string_xrefs

- `0x180003be2`: `ForceRemove`
- `0x180003cc9`: `NoRemove`
- `0x180003bcf`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(LPCWSTR *this, unsigned __int16 *a2, HKEY a3, int a4, int a5)
{
  int v5; // r12d
  HKEY v6; // r15
  HKEY v9; // rbx
  __int64 result; // rax
  int Token; // edi
  int v12; // r14d
  int v13; // edi
  WCHAR v14; // ax
  const WCHAR *v15; // rcx
  int v16; // r12d
  HRESULT v17; // eax
  DWORD v18; // eax
  HKEY v19; // r14
  LSTATUS v20; // eax
  int v21; // eax
  WCHAR v22; // ax
  const WCHAR *v23; // rcx
  LSTATUS v24; // eax
  LSTATUS v25; // eax
  __int64 v26; // rax
  LSTATUS v27; // r14d
  int v28; // r15d
  int v29; // eax
  __int64 v30; // rax
  int v31; // r14d
  int v32; // ecx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v35; // [rsp+68h] [rbp-98h]
  HKEY v36; // [rsp+70h] [rbp-90h]
  HKEY v37; // [rsp+78h] [rbp-88h] BYREF
  HKEY v38[3]; // [rsp+80h] [rbp-80h] BYREF
  HKEY v39; // [rsp+98h] [rbp-68h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-60h]
  __int64 v41; // [rsp+A8h] [rbp-58h]
  WCHAR String1[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR ValueName[4096]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v5 = a4;
  v35 = a4;
  v6 = a3;
  v36 = a3;
  v9 = 0;
  memset(v38, 0, sizeof(v38));
  result = ATL::CRegParser::NextToken(this, a2);
  Token = result;
  if ( (int)result < 0 )
    return result;
  if ( *a2 == 125 )
    goto LABEL_111;
  while ( 1 )
  {
    v12 = lstrcmpiW(a2, L"Delete");
    if ( !lstrcmpiW(a2, L"ForceRemove") || !v12 )
    {
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_111;
      v13 = 0;
      if ( v5 )
      {
        v39 = 0;
        v40 = 0;
        v41 = 0;
        v14 = *a2;
        if ( !*a2 )
          goto LABEL_13;
        v15 = a2;
        do
        {
          if ( v14 == 92 )
          {
            if ( !v15 )
              break;
            goto LABEL_117;
          }
          v15 = CharNextW(v15);
          v14 = *v15;
        }
        while ( *v15 );
LABEL_13:
        while ( lstrcmpiW(a2, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v13]) )
        {
          if ( ++v13 >= 12 )
          {
            v39 = v6;
            ATL::CRegKey::RecurseDeleteKey(&v39, a2);
            break;
          }
        }
        if ( !v12 )
        {
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            goto LABEL_111;
          Token = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
          if ( Token < 0 )
            goto LABEL_111;
          goto LABEL_61;
        }
      }
    }
    v16 = 1;
    if ( !lstrcmpiW(a2, L"NoRemove") )
    {
      v16 = 0;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_111;
    }
    if ( !lstrcmpiW(a2, L"Val") )
      break;
    v22 = *a2;
    if ( *a2 )
    {
      v23 = a2;
      while ( v22 != 92 )
      {
        v23 = CharNextW(v23);
        v22 = *v23;
        if ( !*v23 )
          goto LABEL_43;
      }
      if ( v23 )
        goto LABEL_117;
    }
LABEL_43:
    if ( v35 )
    {
      hKey = 0;
      if ( RegOpenKeyExW(v6, a2, 0, 0x2001Fu, &hKey) )
        goto LABEL_126;
      v24 = 0;
      if ( v9 )
        v24 = RegCloseKey(v9);
      v9 = hKey;
      v38[0] = hKey;
      if ( v24 )
      {
LABEL_126:
        hKey = 0;
        if ( RegOpenKeyExW(v6, a2, 0, 0x20019u, &hKey) )
          goto LABEL_127;
        v25 = 0;
        if ( v9 )
          v25 = RegCloseKey(v9);
        v9 = hKey;
        v38[0] = hKey;
        if ( v25 )
        {
LABEL_127:
          LODWORD(hKey) = 0;
          v37 = 0;
          v18 = RegCreateKeyExW(v6, a2, 0, 0, 0, 0x2001Fu, 0, &v37, (LPDWORD)&hKey);
          if ( v18 )
            goto LABEL_109;
          v18 = 0;
          if ( v9 )
            v18 = RegCloseKey(v9);
          v9 = v37;
          v38[0] = v37;
          if ( v18 )
            goto LABEL_109;
        }
      }
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_111;
      if ( *a2 == 61 )
      {
        v17 = ATL::CRegParser::AddValue(this, v38, 0, a2);
        Token = v17;
        v9 = v38[0];
        goto LABEL_59;
      }
LABEL_60:
      v5 = v35;
LABEL_61:
      if ( *a2 != 123 )
        goto LABEL_93;
      v26 = -1;
      do
        ++v26;
      while ( a2[v26] );
      if ( v26 != 1 )
        goto LABEL_93;
      Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, a2, v9, v5, 0);
      if ( Token < 0 )
        goto LABEL_111;
      v21 = ATL::CRegParser::NextToken(this, a2);
LABEL_35:
      Token = v21;
      if ( v21 < 0 )
        goto LABEL_111;
      goto LABEL_93;
    }
    if ( a5 )
    {
      v27 = 2;
    }
    else
    {
      v37 = 0;
      v27 = RegOpenKeyExW(v6, a2, 0, 0x20019u, &v37);
      if ( !v27 )
      {
        v27 = 0;
        if ( v9 )
          v27 = RegCloseKey(v9);
        v9 = v37;
        v38[0] = v37;
      }
    }
    v28 = 1;
    if ( !v27 )
      v28 = a5;
    v29 = _o_wcsncpy_s(String1, 260, a2, -1, phkResult);
    if ( v29 )
    {
      if ( v29 == 12 )
        ATL::AtlThrowImpl(-2147024882);
      if ( v29 == 22 || v29 == 34 )
        ATL::AtlThrowImpl(-2147024809);
      if ( v29 != 80 )
        ATL::AtlThrowImpl(-2147467259);
    }
    Token = ATL::CRegParser::NextToken(this, a2);
    if ( Token < 0 )
      goto LABEL_111;
    Token = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
    if ( Token < 0 )
      goto LABEL_111;
    if ( *a2 == 123 )
    {
      v30 = -1;
      do
        ++v30;
      while ( a2[v30] );
      if ( v30 == 1 )
      {
        Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, a2, v9, 0, v28);
        if ( Token < 0 && !v28 )
          goto LABEL_111;
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_111;
      }
    }
    if ( v27 == 2 )
      goto LABEL_92;
    if ( v27 )
    {
      if ( a5 )
      {
LABEL_92:
        v6 = v36;
        goto LABEL_93;
      }
      v32 = v27;
LABEL_110:
      Token = ATL::AtlHresultFromWin32(v32);
      goto LABEL_111;
    }
    v31 = 0;
    if ( a5 )
    {
      LODWORD(hKey) = 0;
      if ( !RegQueryInfoKeyW(v9, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      {
        if ( (_DWORD)hKey )
        {
          while ( lstrcmpiW(String1, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v31]) )
          {
            if ( ++v31 >= 12 )
            {
              if ( v16 )
              {
                ATL::CRegKey::RecurseDeleteKey(v38, String1);
                v9 = v38[0];
              }
              goto LABEL_92;
            }
          }
          goto LABEL_92;
        }
      }
    }
    LODWORD(hKey) = 0;
    if ( !RegQueryInfoKeyW(v9, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      LOBYTE(v31) = (_DWORD)hKey != 0;
    if ( v9 )
    {
      v18 = RegCloseKey(v9);
      v9 = 0;
      v38[0] = 0;
      if ( v18 )
      {
LABEL_109:
        v32 = v18;
        goto LABEL_110;
      }
    }
    if ( !v16 || v31 )
      goto LABEL_92;
    v40 = 0;
    v41 = 0;
    v6 = v36;
    v39 = v36;
    v18 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v39, String1);
    if ( v18 )
      goto LABEL_109;
LABEL_93:
    if ( *a2 == 125 )
      goto LABEL_111;
    v5 = v35;
  }
  Token = ATL::CRegParser::NextToken(this, ValueName);
  if ( Token < 0 )
    goto LABEL_111;
  Token = ATL::CRegParser::NextToken(this, a2);
  if ( Token < 0 )
    goto LABEL_111;
  if ( *a2 != 61 )
  {
LABEL_117:
    if ( v9 )
      RegCloseKey(v9);
    return 2147614729LL;
  }
  if ( v35 )
  {
    v40 = 0;
    v41 = 0;
    v39 = v6;
    v17 = ATL::CRegParser::AddValue(this, &v39, ValueName, a2);
    Token = v17;
LABEL_59:
    if ( v17 < 0 )
      goto LABEL_111;
    goto LABEL_60;
  }
  if ( a5 || !v16 )
  {
LABEL_34:
    v21 = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
    goto LABEL_35;
  }
  hKey = 0;
  v18 = RegOpenKeyExW(v6, 0, 0, 0x20006u, &hKey);
  if ( v18 )
    goto LABEL_109;
  v19 = hKey;
  v20 = RegDeleteValueW(hKey, ValueName);
  if ( (v20 & 0xFFFFFFFD) == 0 )
  {
    if ( v19 )
      RegCloseKey(v19);
    goto LABEL_34;
  }
  Token = ATL::AtlHresultFromWin32(v20);
  if ( v19 )
    RegCloseKey(v19);
LABEL_111:
  if ( v9 )
    RegCloseKey(v9);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x180003b5c  push    rbp
0x180003b5e  push    rbx
0x180003b5f  push    rsi
0x180003b60  push    rdi
0x180003b61  push    r12
0x180003b63  push    r13
0x180003b65  push    r14
0x180003b67  push    r15
0x180003b69  lea     rbp, [rsp-21D8h]
0x180003b71  mov     eax, 22D8h
0x180003b76  call    _alloca_probe
0x180003b7b  sub     rsp, rax
0x180003b7e  mov     rax, cs:__security_cookie
0x180003b85  xor     rax, rsp
0x180003b88  mov     [rbp+2210h+var_50], rax
0x180003b8f  mov     r12d, r9d
0x180003b92  mov     [rsp+2310h+var_22A8], r9d
0x180003b97  mov     r15, r8
0x180003b9a  mov     [rsp+2310h+var_22A0], r8
0x180003b9f  mov     rsi, rdx
0x180003ba2  mov     r13, rcx
0x180003ba5  xor     eax, eax
0x180003ba7  mov     ebx, eax
0x180003ba9  mov     [rbp+2210h+var_2290], rax
0x180003bad  mov     [rbp+2210h+var_2288], rax
0x180003bb1  mov     [rbp+2210h+var_2280], rax
0x180003bb5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003bba  mov     edi, eax
0x180003bbc  test    eax, eax
0x180003bbe  jns     short loc_180003BC5
0x180003bc0  jmp     loc_18000427C
0x180003bc5  cmp     word ptr [rsi], 7Dh ; '}'
0x180003bc9  jz      loc_18000426C
0x180003bcf  lea     rdx, String2; "Delete"
0x180003bd6  mov     rcx, rsi; lpString1
0x180003bd9  call    cs:__imp_lstrcmpiW
0x180003bdf  mov     r14d, eax
0x180003be2  lea     rdx, aForceremove; "ForceRemove"
0x180003be9  mov     rcx, rsi; lpString1
0x180003bec  call    cs:__imp_lstrcmpiW
0x180003bf2  xor     edi, edi
0x180003bf4  test    eax, eax
0x180003bf6  jz      short loc_180003C01
0x180003bf8  test    r14d, r14d
0x180003bfb  jnz     loc_180003CC3
0x180003c01  mov     rdx, rsi; unsigned __int16 *
0x180003c04  mov     rcx, r13; this
0x180003c07  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003c0c  mov     edi, eax
0x180003c0e  test    eax, eax
0x180003c10  js      loc_18000426C
0x180003c16  xor     edi, edi
0x180003c18  test    r12d, r12d
0x180003c1b  jz      loc_180003CC3
0x180003c21  mov     [rbp+2210h+var_2278], rdi
0x180003c25  mov     [rbp+2210h+var_2270], rdi
0x180003c29  mov     [rbp+2210h+var_2268], rdi
0x180003c2d  movzx   eax, word ptr [rsi]
0x180003c30  test    ax, ax
0x180003c33  jz      short loc_180003C5A
0x180003c35  mov     rcx, rsi; lpsz
0x180003c38  cmp     ax, 5Ch ; '\'
0x180003c3c  jz      short loc_180003C51
0x180003c3e  call    cs:__imp_CharNextW
0x180003c44  mov     rcx, rax
0x180003c47  movzx   eax, word ptr [rax]
0x180003c4a  test    ax, ax
0x180003c4d  jnz     short loc_180003C38
0x180003c4f  jmp     short loc_180003C5A
0x180003c51  test    rcx, rcx
0x180003c54  jnz     loc_1800042B8
0x180003c5a  mov     edx, edi
0x180003c5c  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180003c63  mov     rdx, [rax+rdx*8]; lpString2
0x180003c67  mov     rcx, rsi; lpString1
0x180003c6a  call    cs:__imp_lstrcmpiW
0x180003c70  test    eax, eax
0x180003c72  jz      short loc_180003C8B
0x180003c74  inc     edi
0x180003c76  cmp     edi, 0Ch
0x180003c79  jl      short loc_180003C5A
0x180003c7b  mov     [rbp+2210h+var_2278], r15
0x180003c7f  mov     rdx, rsi; unsigned __int16 *
0x180003c82  lea     rcx, [rbp+2210h+var_2278]; this
0x180003c86  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180003c8b  xor     edi, edi
0x180003c8d  test    r14d, r14d
0x180003c90  jnz     short loc_180003CC3
0x180003c92  mov     rdx, rsi; unsigned __int16 *
0x180003c95  mov     rcx, r13; this
0x180003c98  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003c9d  mov     edi, eax
0x180003c9f  test    eax, eax
0x180003ca1  js      loc_18000426C
0x180003ca7  mov     rdx, rsi; unsigned __int16 *
0x180003caa  mov     rcx, r13; this
0x180003cad  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180003cb2  mov     edi, eax
0x180003cb4  xor     ecx, ecx
0x180003cb6  test    eax, eax
0x180003cb8  js      loc_18000426C
0x180003cbe  jmp     loc_180003F6A
0x180003cc3  mov     r12d, 1
0x180003cc9  lea     rdx, aNoremove; "NoRemove"
0x180003cd0  mov     rcx, rsi; lpString1
0x180003cd3  call    cs:__imp_lstrcmpiW
0x180003cd9  test    eax, eax
0x180003cdb  jnz     short loc_180003CF7
0x180003cdd  mov     r12d, edi
0x180003ce0  mov     rdx, rsi; unsigned __int16 *
0x180003ce3  mov     rcx, r13; this
0x180003ce6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003ceb  mov     edi, eax
0x180003ced  test    eax, eax
0x180003cef  js      loc_18000426C
0x180003cf5  xor     edi, edi
0x180003cf7  lea     rdx, aVal; "Val"
0x180003cfe  mov     rcx, rsi; lpString1
0x180003d01  call    cs:__imp_lstrcmpiW
0x180003d07  test    eax, eax
0x180003d09  jnz     loc_180003DF8
0x180003d0f  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180003d16  mov     rcx, r13; this
0x180003d19  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003d1e  mov     edi, eax
0x180003d20  test    eax, eax
0x180003d22  js      loc_18000426C
0x180003d28  mov     rdx, rsi; unsigned __int16 *
0x180003d2b  mov     rcx, r13; this
0x180003d2e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003d33  mov     edi, eax
0x180003d35  test    eax, eax
0x180003d37  js      loc_18000426C
0x180003d3d  cmp     word ptr [rsi], 3Dh ; '='
0x180003d41  jnz     loc_1800042B8
0x180003d47  xor     edi, edi
0x180003d49  cmp     [rsp+2310h+var_22A8], edi
0x180003d4d  jz      short loc_180003D78
0x180003d4f  mov     [rbp+2210h+var_2270], rdi
0x180003d53  mov     [rbp+2210h+var_2268], rdi
0x180003d57  mov     [rbp+2210h+var_2278], r15
0x180003d5b  mov     r9, rsi; unsigned __int16 *
0x180003d5e  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180003d65  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180003d69  mov     rcx, r13; this
0x180003d6c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180003d71  mov     edi, eax
0x180003d73  jmp     loc_180003F5B
0x180003d78  cmp     [rbp+2210h+arg_20], edi
0x180003d7e  jnz     short loc_180003DDE
0x180003d80  test    r12d, r12d
0x180003d83  jz      short loc_180003DDE
0x180003d85  mov     [rsp+2310h+hKey], rdi
0x180003d8a  lea     rax, [rsp+2310h+hKey]
0x180003d8f  mov     [rsp+2310h+phkResult], rax; phkResult
0x180003d94  mov     r9d, 20006h; samDesired
0x180003d9a  xor     r8d, r8d; ulOptions
0x180003d9d  xor     edx, edx; lpSubKey
0x180003d9f  mov     rcx, r15; hKey
0x180003da2  call    cs:__imp_RegOpenKeyExW
0x180003da8  test    eax, eax
0x180003daa  jnz     loc_180004263
0x180003db0  mov     r14, [rsp+2310h+hKey]
0x180003db5  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x180003dbc  mov     rcx, r14; hKey
0x180003dbf  call    cs:__imp_RegDeleteValueW
0x180003dc5  test    eax, 0FFFFFFFDh
0x180003dca  jnz     loc_18000429F
0x180003dd0  test    r14, r14
0x180003dd3  jz      short loc_180003DDE
0x180003dd5  mov     rcx, r14; hKey
0x180003dd8  call    cs:__imp_RegCloseKey
0x180003dde  mov     rdx, rsi; unsigned __int16 *
0x180003de1  mov     rcx, r13; this
0x180003de4  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180003de9  mov     edi, eax
0x180003deb  test    eax, eax
0x180003ded  js      loc_18000426C
0x180003df3  jmp     loc_180004105
0x180003df8  movzx   eax, word ptr [rsi]
0x180003dfb  test    ax, ax
0x180003dfe  jz      short loc_180003E25
0x180003e00  mov     rcx, rsi; lpsz
0x180003e03  cmp     ax, 5Ch ; '\'
0x180003e07  jz      short loc_180003E1C
0x180003e09  call    cs:__imp_CharNextW
0x180003e0f  mov     rcx, rax
0x180003e12  movzx   eax, word ptr [rax]
0x180003e15  test    ax, ax
0x180003e18  jnz     short loc_180003E03
0x180003e1a  jmp     short loc_180003E25
0x180003e1c  test    rcx, rcx
0x180003e1f  jnz     loc_1800042B8
0x180003e25  cmp     [rsp+2310h+var_22A8], edi
0x180003e29  jz      loc_180003FBE
0x180003e2f  mov     [rsp+2310h+hKey], rdi
0x180003e34  lea     rax, [rsp+2310h+hKey]
0x180003e39  mov     [rsp+2310h+phkResult], rax; phkResult
0x180003e3e  mov     r14d, 2001Fh
0x180003e44  mov     r9d, r14d; samDesired
0x180003e47  xor     r8d, r8d; ulOptions
0x180003e4a  mov     rdx, rsi; lpSubKey
0x180003e4d  mov     rcx, r15; hKey
0x180003e50  call    cs:__imp_RegOpenKeyExW
0x180003e56  test    eax, eax
0x180003e58  jnz     short loc_180003E7B
0x180003e5a  mov     eax, edi
0x180003e5c  test    rbx, rbx
0x180003e5f  jz      short loc_180003E6A
0x180003e61  mov     rcx, rbx; hKey
0x180003e64  call    cs:__imp_RegCloseKey
0x180003e6a  mov     rbx, [rsp+2310h+hKey]
0x180003e6f  mov     [rbp+2210h+var_2290], rbx
0x180003e73  test    eax, eax
0x180003e75  jz      loc_180003F26
0x180003e7b  mov     [rsp+2310h+hKey], rdi
0x180003e80  lea     rax, [rsp+2310h+hKey]
0x180003e85  mov     [rsp+2310h+phkResult], rax; phkResult
0x180003e8a  mov     r9d, 20019h; samDesired
0x180003e90  xor     r8d, r8d; ulOptions
0x180003e93  mov     rdx, rsi; lpSubKey
0x180003e96  mov     rcx, r15; hKey
0x180003e99  call    cs:__imp_RegOpenKeyExW
0x180003e9f  test    eax, eax
0x180003ea1  jnz     short loc_180003EC0
0x180003ea3  mov     eax, edi
0x180003ea5  test    rbx, rbx
0x180003ea8  jz      short loc_180003EB3
0x180003eaa  mov     rcx, rbx; hKey
0x180003ead  call    cs:__imp_RegCloseKey
0x180003eb3  mov     rbx, [rsp+2310h+hKey]
0x180003eb8  mov     [rbp+2210h+var_2290], rbx
0x180003ebc  test    eax, eax
0x180003ebe  jz      short loc_180003F26
0x180003ec0  mov     dword ptr [rsp+2310h+hKey], edi
0x180003ec4  mov     [rsp+2310h+var_2298], rdi
0x180003ec9  lea     rax, [rsp+2310h+hKey]
0x180003ece  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180003ed3  lea     rax, [rsp+2310h+var_2298]
0x180003ed8  mov     [rsp+2310h+var_22D8], rax; phkResult
0x180003edd  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180003ee2  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180003ee7  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x180003eeb  xor     r9d, r9d; lpClass
0x180003eee  xor     r8d, r8d; Reserved
0x180003ef1  mov     rdx, rsi; lpSubKey
0x180003ef4  mov     rcx, r15; hKey
0x180003ef7  call    cs:__imp_RegCreateKeyExW
0x180003efd  test    eax, eax
0x180003eff  jnz     loc_180004263
0x180003f05  mov     eax, edi
0x180003f07  test    rbx, rbx
0x180003f0a  jz      short loc_180003F15
0x180003f0c  mov     rcx, rbx; hKey
0x180003f0f  call    cs:__imp_RegCloseKey
0x180003f15  mov     rbx, [rsp+2310h+var_2298]
0x180003f1a  mov     [rbp+2210h+var_2290], rbx
0x180003f1e  test    eax, eax
0x180003f20  jnz     loc_180004263
0x180003f26  mov     rdx, rsi; unsigned __int16 *
0x180003f29  mov     rcx, r13; this
0x180003f2c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003f31  mov     edi, eax
0x180003f33  xor     ecx, ecx
0x180003f35  test    eax, eax
0x180003f37  js      loc_18000426C
0x180003f3d  cmp     word ptr [rsi], 3Dh ; '='
0x180003f41  jnz     short loc_180003F65
0x180003f43  mov     r9, rsi; unsigned __int16 *
0x180003f46  xor     r8d, r8d; unsigned __int16 *
0x180003f49  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x180003f4d  mov     rcx, r13; this
0x180003f50  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180003f55  mov     edi, eax
0x180003f57  mov     rbx, [rbp+2210h+var_2290]
0x180003f5b  test    eax, eax
0x180003f5d  js      loc_18000426C
0x180003f63  xor     ecx, ecx
0x180003f65  mov     r12d, [rsp+2310h+var_22A8]
0x180003f6a  cmp     word ptr [rsi], 7Bh ; '{'
0x180003f6e  jnz     loc_180004105
0x180003f74  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003f78  inc     rax
0x180003f7b  cmp     [rsi+rax*2], cx
0x180003f7f  jnz     short loc_180003F78
0x180003f81  cmp     rax, 1
0x180003f85  jnz     loc_180004105
0x180003f8b  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x180003f93  mov     r9d, r12d; int
0x180003f96  mov     r8, rbx; HKEY
0x180003f99  mov     rdx, rsi; unsigned __int16 *
0x180003f9c  mov     rcx, r13; this
0x180003f9f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180003fa4  mov     edi, eax
0x180003fa6  test    eax, eax
0x180003fa8  js      loc_18000426C
0x180003fae  mov     rdx, rsi; unsigned __int16 *
0x180003fb1  mov     rcx, r13; this
0x180003fb4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003fb9  jmp     loc_180003DE9
  ... truncated ...
```
