# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000a50c`
- end: `0x18000aca9`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1949`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18000a1b8`
- `0x18000a50c`

## callees

- `0x180008624`
- `0x180008c7c`
- `0x180008c94`
- `0x1800090fc`
- `0x1800096e4`
- `0x18000a068`
- `0x18000a50c`
- `0x18000b568`
- `0x18001a210`
- `0x18001a2d0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000a9e3`
- `msvcrt!wcsncpy_s` at `0x18000a9e3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000a5ef`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000a7b6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000a5ef`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000a7b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000ab0a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000aba3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000ab0a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000aba3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000a76c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000a76c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a74f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a7fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a846`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a991`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a74f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a7fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a846`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a991`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a785`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a811`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a85a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a8bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a9ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000abc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ac21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ac5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ac6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a785`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a811`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a85a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a8bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a9ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000abc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ac21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ac5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ac6d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a8a4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a8a4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a58a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a59d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a61b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a684`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a6b2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ab31`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a58a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a59d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a61b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a684`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a6b2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ab31`

## string_xrefs

- `0x18000a590`: `ForceRemove`
- `0x18000a674`: `NoRemove`
- `0x18000a580`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(LPCWSTR *this, unsigned __int16 *a2, HKEY a3, int a4, int a5)
{
  HKEY v5; // rbx
  int v6; // r12d
  HKEY v7; // r15
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
  errno_t v29; // eax
  __int64 v30; // rdx
  unsigned int v31; // r8d
  __int64 v32; // rax
  int v33; // r14d
  int v34; // r14d
  LSTATUS v35; // eax
  unsigned int v36; // ecx
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v38; // [rsp+68h] [rbp-98h]
  HKEY v39; // [rsp+70h] [rbp-90h]
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  HKEY v41[3]; // [rsp+80h] [rbp-80h] BYREF
  HKEY v42; // [rsp+98h] [rbp-68h] BYREF
  __int64 v43; // [rsp+A0h] [rbp-60h]
  __int64 v44; // [rsp+A8h] [rbp-58h]
  wchar_t Destination[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR ValueName[4096]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v38 = a4;
  v5 = 0;
  v39 = a3;
  memset(v41, 0, sizeof(v41));
  v6 = a4;
  v7 = a3;
  result = ATL::CRegParser::NextToken(this, a2);
  Token = result;
  if ( (int)result < 0 )
    return result;
  if ( *a2 == 125 )
    return (unsigned int)Token;
  while ( 1 )
  {
    v12 = lstrcmpiW(a2, L"Delete");
    if ( !lstrcmpiW(a2, L"ForceRemove") || !v12 )
    {
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_112;
      v13 = 0;
      if ( v6 )
      {
        v14 = *a2;
        v42 = 0;
        v43 = 0;
        v44 = 0;
        if ( !v14 )
          goto LABEL_13;
        v15 = a2;
        do
        {
          if ( v14 == 92 )
          {
            if ( !v15 )
              break;
            goto LABEL_118;
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
            v42 = v7;
            ATL::CRegKey::RecurseDeleteKey(&v42, a2);
            break;
          }
        }
        if ( !v12 )
        {
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            goto LABEL_112;
          Token = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
          if ( Token < 0 )
            goto LABEL_112;
LABEL_61:
          if ( *a2 != 123 )
            goto LABEL_93;
          v26 = -1;
          do
            ++v26;
          while ( a2[v26] );
          if ( v26 != 1 )
            goto LABEL_93;
          Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, a2, v5, v6, 0);
          if ( Token < 0 )
            goto LABEL_112;
          v21 = ATL::CRegParser::NextToken(this, a2);
          goto LABEL_35;
        }
      }
    }
    v16 = 1;
    if ( !lstrcmpiW(a2, L"NoRemove") )
    {
      v16 = 0;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_112;
    }
    if ( !lstrcmpiW(a2, L"Val") )
    {
      Token = ATL::CRegParser::NextToken(this, ValueName);
      if ( Token < 0 )
        goto LABEL_112;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_112;
      if ( *a2 != 61 )
        break;
      if ( v38 )
      {
        v43 = 0;
        v44 = 0;
        v42 = v7;
        v17 = ATL::CRegParser::AddValue((ATL::CRegParser *)this, &v42, ValueName, a2);
LABEL_59:
        Token = v17;
        if ( v17 < 0 )
          goto LABEL_112;
        goto LABEL_60;
      }
      if ( !a5 && v16 )
      {
        hKey = 0;
        v18 = RegOpenKeyExW(v7, 0, 0, 0x20006u, &hKey);
        if ( v18 )
          goto LABEL_110;
        v19 = hKey;
        v20 = RegDeleteValueW(hKey, ValueName);
        if ( (v20 & 0xFFFFFFFD) != 0 )
        {
          Token = ATL::AtlHresultFromWin32(v20);
          if ( v19 )
            RegCloseKey(v19);
          goto LABEL_112;
        }
        if ( v19 )
          RegCloseKey(v19);
      }
      v21 = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
LABEL_35:
      Token = v21;
      if ( v21 < 0 )
        goto LABEL_112;
      goto LABEL_93;
    }
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
        break;
    }
LABEL_43:
    if ( v38 )
    {
      hKey = 0;
      if ( RegOpenKeyExW(v7, a2, 0, 0x2001Fu, &hKey) )
        goto LABEL_128;
      v24 = 0;
      if ( v5 )
        v24 = RegCloseKey(v5);
      v5 = hKey;
      v41[0] = hKey;
      if ( v24 )
      {
LABEL_128:
        hKey = 0;
        if ( RegOpenKeyExW(v7, a2, 0, 0x20019u, &hKey) )
          goto LABEL_129;
        v25 = 0;
        if ( v5 )
          v25 = RegCloseKey(v5);
        v5 = hKey;
        v41[0] = hKey;
        if ( v25 )
        {
LABEL_129:
          LODWORD(hKey) = 0;
          phkResult = 0;
          v18 = RegCreateKeyExW(v7, a2, 0, 0, 0, 0x2001Fu, 0, &phkResult, (LPDWORD)&hKey);
          if ( v18 )
            goto LABEL_110;
          v18 = 0;
          if ( v5 )
            v18 = RegCloseKey(v5);
          v5 = phkResult;
          v41[0] = phkResult;
          if ( v18 )
          {
LABEL_110:
            v36 = v18;
            goto LABEL_111;
          }
        }
      }
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_112;
      if ( *a2 == 61 )
      {
        v17 = ATL::CRegParser::AddValue((ATL::CRegParser *)this, v41, 0, a2);
        v5 = v41[0];
        goto LABEL_59;
      }
LABEL_60:
      v6 = v38;
      goto LABEL_61;
    }
    if ( a5 )
    {
      v27 = 2;
    }
    else
    {
      phkResult = 0;
      v27 = RegOpenKeyExW(v7, a2, 0, 0x20019u, &phkResult);
      if ( !v27 )
      {
        v27 = 0;
        if ( v5 )
          v27 = RegCloseKey(v5);
        v5 = phkResult;
        v41[0] = phkResult;
      }
    }
    v28 = 1;
    if ( !v27 )
      v28 = a5;
    v29 = wcsncpy_s(Destination, 0x104u, a2, 0xFFFFFFFFFFFFFFFFuLL);
    if ( v29 )
    {
      if ( v29 == 12 )
        ATL::AtlThrowImpl(-2147024882, v30, v31);
      if ( v29 == 22 || v29 == 34 )
        ATL::AtlThrowImpl(-2147024809, v30, v31);
      if ( v29 != 80 )
        ATL::AtlThrowImpl(-2147467259, v30, v31);
    }
    Token = ATL::CRegParser::NextToken(this, a2);
    if ( Token < 0 )
      goto LABEL_112;
    Token = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
    if ( Token < 0 )
      goto LABEL_112;
    if ( *a2 == 123 )
    {
      v32 = -1;
      do
        ++v32;
      while ( a2[v32] );
      if ( v32 == 1 )
      {
        Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, a2, v5, 0, v28);
        if ( Token < 0 && !v28 )
          goto LABEL_112;
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_112;
      }
    }
    if ( v27 == 2 )
      goto LABEL_92;
    if ( v27 )
    {
      if ( a5 )
      {
LABEL_92:
        v7 = v39;
        goto LABEL_93;
      }
      v36 = v27;
LABEL_111:
      Token = ATL::AtlHresultFromWin32(v36);
LABEL_112:
      if ( v5 )
        RegCloseKey(v5);
      return (unsigned int)Token;
    }
    if ( a5 )
    {
      LODWORD(hKey) = 0;
      if ( !RegQueryInfoKeyW(v5, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      {
        if ( (_DWORD)hKey )
        {
          v33 = 0;
          while ( lstrcmpiW(Destination, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v33]) )
          {
            if ( ++v33 >= 12 )
            {
              if ( v16 )
              {
                ATL::CRegKey::RecurseDeleteKey(v41, Destination);
                v5 = v41[0];
              }
              goto LABEL_92;
            }
          }
          goto LABEL_92;
        }
      }
    }
    LODWORD(hKey) = 0;
    v34 = 0;
    if ( !RegQueryInfoKeyW(v5, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      LOBYTE(v34) = (_DWORD)hKey != 0;
    if ( v5 )
    {
      v35 = RegCloseKey(v5);
      v41[0] = 0;
      v5 = 0;
      if ( v35 )
        return ATL::AtlHresultFromWin32(v35);
    }
    if ( !v16 )
      goto LABEL_92;
    v7 = v39;
    if ( !v34 )
    {
      v43 = 0;
      v44 = 0;
      v42 = v39;
      v18 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v42, Destination);
      if ( v18 )
        goto LABEL_110;
    }
LABEL_93:
    if ( *a2 == 125 )
      goto LABEL_112;
    v6 = v38;
  }
LABEL_118:
  if ( v5 )
    RegCloseKey(v5);
  return 2147614729LL;
}

```

## disassembly

```asm
0x18000a50c  push    rbp
0x18000a50e  push    rbx
0x18000a50f  push    rsi
0x18000a510  push    rdi
0x18000a511  push    r12
0x18000a513  push    r13
0x18000a515  push    r14
0x18000a517  push    r15
0x18000a519  lea     rbp, [rsp-21D8h]
0x18000a521  mov     eax, 22D8h
0x18000a526  call    _alloca_probe
0x18000a52b  sub     rsp, rax
0x18000a52e  mov     rax, cs:__security_cookie
0x18000a535  xor     rax, rsp
0x18000a538  mov     [rbp+2210h+var_50], rax
0x18000a53f  xor     r14d, r14d
0x18000a542  mov     [rsp+2310h+var_22A8], r9d
0x18000a547  mov     ebx, r14d
0x18000a54a  mov     [rsp+2310h+var_22A0], r8
0x18000a54f  mov     [rbp+2210h+var_2290], rbx
0x18000a553  mov     r12d, r9d
0x18000a556  mov     r15, r8
0x18000a559  mov     [rbp+2210h+var_2288], r14
0x18000a55d  mov     rsi, rdx
0x18000a560  mov     [rbp+2210h+var_2280], r14
0x18000a564  mov     r13, rcx
0x18000a567  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000a56c  mov     edi, eax
0x18000a56e  test    eax, eax
0x18000a570  js      loc_18000AC29
0x18000a576  cmp     word ptr [rsi], 7Dh ; '}'
0x18000a57a  jz      loc_18000AC27
0x18000a580  lea     rdx, String2; "Delete"
0x18000a587  mov     rcx, rsi; lpString1
0x18000a58a  call    cs:__imp_lstrcmpiW
0x18000a590  lea     rdx, aForceremove; "ForceRemove"
0x18000a597  mov     rcx, rsi; lpString1
0x18000a59a  mov     r14d, eax
0x18000a59d  call    cs:__imp_lstrcmpiW
0x18000a5a3  xor     edi, edi
0x18000a5a5  test    eax, eax
0x18000a5a7  jz      short loc_18000A5B2
0x18000a5a9  test    r14d, r14d
0x18000a5ac  jnz     loc_18000A674
0x18000a5b2  mov     rdx, rsi; unsigned __int16 *
0x18000a5b5  mov     rcx, r13; this
0x18000a5b8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000a5bd  mov     edi, eax
0x18000a5bf  test    eax, eax
0x18000a5c1  js      loc_18000AC19
0x18000a5c7  xor     edi, edi
0x18000a5c9  test    r12d, r12d
0x18000a5cc  jz      loc_18000A674
0x18000a5d2  movzx   eax, word ptr [rsi]
0x18000a5d5  mov     [rbp+2210h+var_2278], rdi
0x18000a5d9  mov     [rbp+2210h+var_2270], rdi
0x18000a5dd  mov     [rbp+2210h+var_2268], rdi
0x18000a5e1  test    ax, ax
0x18000a5e4  jz      short loc_18000A60B
0x18000a5e6  mov     rcx, rsi; lpsz
0x18000a5e9  cmp     ax, 5Ch ; '\'
0x18000a5ed  jz      short loc_18000A602
0x18000a5ef  call    cs:__imp_CharNextW
0x18000a5f5  mov     rcx, rax
0x18000a5f8  movzx   eax, word ptr [rax]
0x18000a5fb  test    ax, ax
0x18000a5fe  jnz     short loc_18000A5E9
0x18000a600  jmp     short loc_18000A60B
0x18000a602  test    rcx, rcx
0x18000a605  jnz     loc_18000AC65
0x18000a60b  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x18000a612  mov     edx, edi
0x18000a614  mov     rcx, rsi; lpString1
0x18000a617  mov     rdx, [rax+rdx*8]; lpString2
0x18000a61b  call    cs:__imp_lstrcmpiW
0x18000a621  test    eax, eax
0x18000a623  jz      short loc_18000A63C
0x18000a625  inc     edi
0x18000a627  cmp     edi, 0Ch
0x18000a62a  jl      short loc_18000A60B
0x18000a62c  mov     rdx, rsi; unsigned __int16 *
0x18000a62f  mov     [rbp+2210h+var_2278], r15
0x18000a633  lea     rcx, [rbp+2210h+var_2278]; this
0x18000a637  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000a63c  xor     edi, edi
0x18000a63e  test    r14d, r14d
0x18000a641  jnz     short loc_18000A674
0x18000a643  mov     rdx, rsi; unsigned __int16 *
0x18000a646  mov     rcx, r13; this
0x18000a649  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000a64e  mov     edi, eax
0x18000a650  test    eax, eax
0x18000a652  js      loc_18000AC19
0x18000a658  mov     rdx, rsi; unsigned __int16 *
0x18000a65b  mov     rcx, r13; this
0x18000a65e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000a663  xor     edx, edx
0x18000a665  mov     edi, eax
0x18000a667  test    eax, eax
0x18000a669  js      loc_18000AC19
0x18000a66f  jmp     loc_18000A917
0x18000a674  lea     rdx, aNoremove; "NoRemove"
0x18000a67b  mov     rcx, rsi; lpString1
0x18000a67e  mov     r12d, 1
0x18000a684  call    cs:__imp_lstrcmpiW
0x18000a68a  test    eax, eax
0x18000a68c  jnz     short loc_18000A6A8
0x18000a68e  mov     rdx, rsi; unsigned __int16 *
0x18000a691  mov     rcx, r13; this
0x18000a694  mov     r12d, edi
0x18000a697  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000a69c  mov     edi, eax
0x18000a69e  test    eax, eax
0x18000a6a0  js      loc_18000AC19
0x18000a6a6  xor     edi, edi
0x18000a6a8  lea     rdx, aVal; "Val"
0x18000a6af  mov     rcx, rsi; lpString1
0x18000a6b2  call    cs:__imp_lstrcmpiW
0x18000a6b8  test    eax, eax
0x18000a6ba  jnz     loc_18000A7A5
0x18000a6c0  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x18000a6c7  mov     rcx, r13; this
0x18000a6ca  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000a6cf  mov     edi, eax
0x18000a6d1  test    eax, eax
0x18000a6d3  js      loc_18000AC19
0x18000a6d9  mov     rdx, rsi; unsigned __int16 *
0x18000a6dc  mov     rcx, r13; this
0x18000a6df  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000a6e4  xor     edx, edx; lpSubKey
0x18000a6e6  mov     edi, eax
0x18000a6e8  test    eax, eax
0x18000a6ea  js      loc_18000AC19
0x18000a6f0  cmp     word ptr [rsi], 3Dh ; '='
0x18000a6f4  jnz     loc_18000AC65
0x18000a6fa  cmp     [rsp+2310h+var_22A8], edx
0x18000a6fe  jz      short loc_18000A727
0x18000a700  mov     [rbp+2210h+var_2270], rdx
0x18000a704  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x18000a70b  mov     [rbp+2210h+var_2268], rdx
0x18000a70f  mov     r9, rsi; unsigned __int16 *
0x18000a712  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x18000a716  mov     [rbp+2210h+var_2278], r15
0x18000a71a  mov     rcx, r13; this
0x18000a71d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000a722  jmp     loc_18000A906
0x18000a727  cmp     [rbp+2210h+arg_20], edx
0x18000a72d  jnz     short loc_18000A78B
0x18000a72f  test    r12d, r12d
0x18000a732  jz      short loc_18000A78B
0x18000a734  lea     rax, [rsp+2310h+hKey]
0x18000a739  mov     [rsp+2310h+hKey], rdx
0x18000a73e  mov     r9d, 20006h; samDesired
0x18000a744  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000a749  xor     r8d, r8d; ulOptions
0x18000a74c  mov     rcx, r15; hKey
0x18000a74f  call    cs:__imp_RegOpenKeyExW
0x18000a755  test    eax, eax
0x18000a757  jnz     loc_18000AC10
0x18000a75d  mov     r14, [rsp+2310h+hKey]
0x18000a762  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x18000a769  mov     rcx, r14; hKey
0x18000a76c  call    cs:__imp_RegDeleteValueW
0x18000a772  test    eax, 0FFFFFFFDh
0x18000a777  jnz     loc_18000AC4C
0x18000a77d  test    r14, r14
0x18000a780  jz      short loc_18000A78B
0x18000a782  mov     rcx, r14; hKey
0x18000a785  call    cs:__imp_RegCloseKey
0x18000a78b  mov     rdx, rsi; unsigned __int16 *
0x18000a78e  mov     rcx, r13; this
0x18000a791  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000a796  mov     edi, eax
0x18000a798  test    eax, eax
0x18000a79a  js      loc_18000AC19
0x18000a7a0  jmp     loc_18000AAAE
0x18000a7a5  movzx   eax, word ptr [rsi]
0x18000a7a8  test    ax, ax
0x18000a7ab  jz      short loc_18000A7D2
0x18000a7ad  mov     rcx, rsi; lpsz
0x18000a7b0  cmp     ax, 5Ch ; '\'
0x18000a7b4  jz      short loc_18000A7C9
0x18000a7b6  call    cs:__imp_CharNextW
0x18000a7bc  mov     rcx, rax
0x18000a7bf  movzx   eax, word ptr [rax]
0x18000a7c2  test    ax, ax
0x18000a7c5  jnz     short loc_18000A7B0
0x18000a7c7  jmp     short loc_18000A7D2
0x18000a7c9  test    rcx, rcx
0x18000a7cc  jnz     loc_18000AC65
0x18000a7d2  cmp     [rsp+2310h+var_22A8], edi
0x18000a7d6  jz      loc_18000A967
0x18000a7dc  lea     rax, [rsp+2310h+hKey]
0x18000a7e1  mov     [rsp+2310h+hKey], rdi
0x18000a7e6  mov     r14d, 2001Fh
0x18000a7ec  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000a7f1  mov     r9d, r14d; samDesired
0x18000a7f4  xor     r8d, r8d; ulOptions
0x18000a7f7  mov     rdx, rsi; lpSubKey
0x18000a7fa  mov     rcx, r15; hKey
0x18000a7fd  call    cs:__imp_RegOpenKeyExW
0x18000a803  test    eax, eax
0x18000a805  jnz     short loc_18000A828
0x18000a807  mov     eax, edi
0x18000a809  test    rbx, rbx
0x18000a80c  jz      short loc_18000A817
0x18000a80e  mov     rcx, rbx; hKey
0x18000a811  call    cs:__imp_RegCloseKey
0x18000a817  mov     rbx, [rsp+2310h+hKey]
0x18000a81c  mov     [rbp+2210h+var_2290], rbx
0x18000a820  test    eax, eax
0x18000a822  jz      loc_18000A8D3
0x18000a828  lea     rax, [rsp+2310h+hKey]
0x18000a82d  mov     [rsp+2310h+hKey], rdi
0x18000a832  mov     r9d, 20019h; samDesired
0x18000a838  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000a83d  xor     r8d, r8d; ulOptions
0x18000a840  mov     rdx, rsi; lpSubKey
0x18000a843  mov     rcx, r15; hKey
0x18000a846  call    cs:__imp_RegOpenKeyExW
0x18000a84c  test    eax, eax
0x18000a84e  jnz     short loc_18000A86D
0x18000a850  mov     eax, edi
0x18000a852  test    rbx, rbx
0x18000a855  jz      short loc_18000A860
0x18000a857  mov     rcx, rbx; hKey
0x18000a85a  call    cs:__imp_RegCloseKey
0x18000a860  mov     rbx, [rsp+2310h+hKey]
0x18000a865  mov     [rbp+2210h+var_2290], rbx
0x18000a869  test    eax, eax
0x18000a86b  jz      short loc_18000A8D3
0x18000a86d  lea     rax, [rsp+2310h+hKey]
0x18000a872  mov     dword ptr [rsp+2310h+hKey], edi
0x18000a876  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x18000a87b  xor     r9d, r9d; lpClass
0x18000a87e  lea     rax, [rsp+2310h+var_2298]
0x18000a883  mov     [rsp+2310h+var_2298], rdi
0x18000a888  mov     [rsp+2310h+var_22D8], rax; phkResult
0x18000a88d  xor     r8d, r8d; Reserved
0x18000a890  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000a895  mov     rdx, rsi; lpSubKey
0x18000a898  mov     [rsp+2310h+samDesired], r14d; samDesired
0x18000a89d  mov     rcx, r15; hKey
0x18000a8a0  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x18000a8a4  call    cs:__imp_RegCreateKeyExW
0x18000a8aa  test    eax, eax
0x18000a8ac  jnz     loc_18000AC10
0x18000a8b2  mov     eax, edi
0x18000a8b4  test    rbx, rbx
0x18000a8b7  jz      short loc_18000A8C2
0x18000a8b9  mov     rcx, rbx; hKey
0x18000a8bc  call    cs:__imp_RegCloseKey
0x18000a8c2  mov     rbx, [rsp+2310h+var_2298]
0x18000a8c7  mov     [rbp+2210h+var_2290], rbx
0x18000a8cb  test    eax, eax
0x18000a8cd  jnz     loc_18000AC10
0x18000a8d3  mov     rdx, rsi; unsigned __int16 *
0x18000a8d6  mov     rcx, r13; this
0x18000a8d9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000a8de  xor     edx, edx
0x18000a8e0  mov     edi, eax
0x18000a8e2  test    eax, eax
0x18000a8e4  js      loc_18000AC19
0x18000a8ea  cmp     word ptr [rsi], 3Dh ; '='
0x18000a8ee  jnz     short loc_18000A912
0x18000a8f0  mov     r9, rsi; unsigned __int16 *
0x18000a8f3  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x18000a8f7  xor     r8d, r8d; unsigned __int16 *
0x18000a8fa  mov     rcx, r13; this
0x18000a8fd  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000a902  mov     rbx, [rbp+2210h+var_2290]
0x18000a906  xor     edx, edx
0x18000a908  mov     edi, eax
0x18000a90a  test    eax, eax
0x18000a90c  js      loc_18000AC19
0x18000a912  mov     r12d, [rsp+2310h+var_22A8]
0x18000a917  cmp     word ptr [rsi], 7Bh ; '{'
0x18000a91b  jnz     loc_18000AAAE
0x18000a921  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a925  inc     rax
0x18000a928  cmp     [rsi+rax*2], dx
0x18000a92c  jnz     short loc_18000A925
0x18000a92e  cmp     rax, 1
0x18000a932  jnz     loc_18000AAAE
0x18000a938  mov     dword ptr [rsp+2310h+phkResult], edx; int
0x18000a93c  mov     r9d, r12d; int
0x18000a93f  mov     rdx, rsi; unsigned __int16 *
0x18000a942  mov     r8, rbx; HKEY
0x18000a945  mov     rcx, r13; this
0x18000a948  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000a94d  mov     edi, eax
0x18000a94f  test    eax, eax
0x18000a951  js      loc_18000AC19
0x18000a957  mov     rdx, rsi; unsigned __int16 *
0x18000a95a  mov     rcx, r13; this
0x18000a95d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000a962  jmp     loc_18000A796
0x18000a967  mov     edi, [rbp+2210h+arg_20]
0x18000a96d  xor     eax, eax
0x18000a96f  test    edi, edi
  ... truncated ...
```
