# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x140004954`
- end: `0x1400050c4`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1904`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x1400043a8`
- `0x140004954`

## callees

- `0x140001490`
- `0x140002424`
- `0x140002a3c`
- `0x140003298`
- `0x1400033b4`
- `0x140003698`
- `0x140003d78`
- `0x140004258`
- `0x140004954`
- `0x1400051e0`
- `0x140006640`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140004de3`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140004de3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004b99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004c45`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004c8c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004d90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004b99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004c45`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004c8c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004d90`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140004bb6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140004bb6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140004f0a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140004fa5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140004f0a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140004fa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004bcf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004c5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004ca1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004dab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004fc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005024`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005060`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005070`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004bcf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004c5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004ca1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004dab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004fc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005024`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005060`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005070`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140004a36`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140004c00`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140004a36`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140004c00`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1400049d3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1400049e6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140004a66`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140004acd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140004afc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140004f31`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1400049d3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1400049e6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140004a66`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140004acd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140004afc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140004f31`

## string_xrefs

- `0x1400049d9`: `ForceRemove`
- `0x140004abd`: `NoRemove`
- `0x1400049c9`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(LPCWSTR *this, unsigned __int16 *a2, HKEY a3, int a4, int a5)
{
  HKEY v5; // rdi
  int v6; // r13d
  HKEY v7; // r15
  __int64 result; // rax
  int Token; // ebx
  int v12; // r14d
  WCHAR v13; // ax
  const WCHAR *v14; // rcx
  int v15; // ebx
  int v16; // r13d
  HRESULT v17; // eax
  DWORD v18; // eax
  HKEY v19; // r14
  LSTATUS v20; // eax
  int v21; // eax
  WCHAR v22; // ax
  const WCHAR *v23; // rcx
  LSTATUS v24; // eax
  unsigned __int16 *v25; // r9
  LSTATUS v26; // eax
  int v27; // eax
  __int64 v28; // rax
  LSTATUS v29; // r14d
  int v30; // r15d
  int v31; // eax
  __int64 v32; // rax
  int v33; // r14d
  int v34; // r14d
  LSTATUS v35; // eax
  int v36; // ecx
  HKEY v37; // rcx
  int v38; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v41; // [rsp+68h] [rbp-98h]
  HKEY v42; // [rsp+70h] [rbp-90h]
  HKEY v43[3]; // [rsp+78h] [rbp-88h] BYREF
  HKEY v44; // [rsp+90h] [rbp-70h] BYREF
  __int64 v45; // [rsp+98h] [rbp-68h]
  __int64 v46; // [rsp+A0h] [rbp-60h]
  WCHAR String1[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR ValueName[4096]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v41 = a4;
  v5 = 0;
  memset(v43, 0, sizeof(v43));
  v6 = a4;
  v7 = a3;
  v42 = a3;
  result = ATL::CRegParser::NextToken(this, a2);
  Token = result;
  if ( (int)result < 0 )
    return result;
  if ( *a2 == 125 )
    return (unsigned int)Token;
  while ( 1 )
  {
    v12 = lstrcmpiW(a2, L"Delete");
    if ( lstrcmpiW(a2, L"ForceRemove") && v12 )
      goto LABEL_21;
    Token = ATL::CRegParser::NextToken(this, a2);
    if ( Token < 0 )
      goto LABEL_111;
    if ( !v6 )
      goto LABEL_21;
    v13 = *a2;
    v44 = 0;
    v45 = 0;
    v46 = 0;
    if ( v13 )
    {
      v14 = a2;
      while ( v13 != 92 )
      {
        v14 = CharNextW(v14);
        v13 = *v14;
        if ( !*v14 )
          goto LABEL_13;
      }
      if ( v14 )
        break;
    }
LABEL_13:
    v15 = 0;
    while ( lstrcmpiW(a2, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v15]) )
    {
      if ( ++v15 >= 12 )
      {
        v44 = v7;
        ATL::CRegKey::RecurseDeleteKey(&v44, a2);
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
      goto LABEL_60;
    }
LABEL_21:
    v16 = 1;
    if ( !lstrcmpiW(a2, L"NoRemove") )
    {
      v16 = 0;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_111;
    }
    if ( !lstrcmpiW(a2, L"Val") )
    {
      Token = ATL::CRegParser::NextToken(this, ValueName);
      if ( Token < 0 )
        goto LABEL_111;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_111;
      if ( *a2 != 61 )
        break;
      if ( v41 )
      {
        v45 = 0;
        v46 = 0;
        v44 = v7;
        v17 = ATL::CRegParser::AddValue((ATL::CRegParser *)this, &v44, ValueName, a2);
LABEL_58:
        Token = v17;
        if ( v17 < 0 )
          goto LABEL_111;
        goto LABEL_59;
      }
      if ( !a5 && v16 )
      {
        hKey = 0;
        v18 = RegOpenKeyExW(v7, 0, 0, 0x20006u, &hKey);
        if ( v18 )
          goto LABEL_109;
        v19 = hKey;
        v20 = RegDeleteValueW(hKey, ValueName);
        if ( (v20 & 0xFFFFFFFD) != 0 )
        {
          Token = ATL::AtlHresultFromWin32(v20);
          if ( v19 )
            RegCloseKey(v19);
LABEL_111:
          if ( !v5 )
            return (unsigned int)Token;
          v37 = v5;
LABEL_113:
          RegCloseKey(v37);
          return (unsigned int)Token;
        }
        if ( v19 )
          RegCloseKey(v19);
      }
      v21 = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
      goto LABEL_36;
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
          goto LABEL_44;
      }
      if ( v23 )
        break;
    }
LABEL_44:
    if ( v41 )
    {
      hKey = 0;
      if ( RegOpenKeyExW(v7, a2, 0, 0x2001Fu, &hKey) )
        goto LABEL_130;
      v24 = 0;
      if ( v5 )
        v24 = RegCloseKey(v5);
      v5 = hKey;
      v43[0] = hKey;
      if ( v24 )
      {
LABEL_130:
        hKey = 0;
        if ( RegOpenKeyExW(v7, a2, 0, 0x20019u, &hKey) )
          goto LABEL_53;
        v26 = 0;
        if ( v5 )
          v26 = RegCloseKey(v5);
        v5 = hKey;
        v43[0] = hKey;
        if ( v26 )
        {
LABEL_53:
          v27 = ATL::CRegKey::Create(v43, v7, a2, v25, (unsigned int)phkResult);
          if ( !v27 )
          {
            v5 = v43[0];
            goto LABEL_55;
          }
          v38 = ATL::AtlHresultFromWin32(v27);
          v37 = v43[0];
          Token = v38;
          if ( v43[0] )
            goto LABEL_113;
          return (unsigned int)Token;
        }
      }
LABEL_55:
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_111;
      if ( *a2 == 61 )
      {
        v17 = ATL::CRegParser::AddValue((ATL::CRegParser *)this, v43, 0, a2);
        v5 = v43[0];
        goto LABEL_58;
      }
LABEL_59:
      v6 = v41;
LABEL_60:
      if ( *a2 != 123 )
        goto LABEL_92;
      v28 = -1;
      do
        ++v28;
      while ( a2[v28] );
      if ( v28 != 1 )
        goto LABEL_92;
      Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, a2, v5, v6, 0);
      if ( Token < 0 )
        goto LABEL_111;
      v21 = ATL::CRegParser::NextToken(this, a2);
LABEL_36:
      Token = v21;
      if ( v21 < 0 )
        goto LABEL_111;
      goto LABEL_92;
    }
    if ( a5 )
    {
      v29 = 2;
    }
    else
    {
      hKey = 0;
      v29 = RegOpenKeyExW(v7, a2, 0, 0x20019u, &hKey);
      if ( !v29 )
      {
        v29 = 0;
        if ( v5 )
          v29 = RegCloseKey(v5);
        v5 = hKey;
        v43[0] = hKey;
      }
    }
    v30 = 1;
    if ( !v29 )
      v30 = a5;
    v31 = _o_wcsncpy_s(String1, 260, a2, -1, phkResult);
    if ( v31 )
    {
      if ( v31 == 12 )
        ATL::AtlThrowImpl(-2147024882);
      if ( v31 == 22 || v31 == 34 )
        ATL::AtlThrowImpl(-2147024809);
      if ( v31 != 80 )
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
      v32 = -1;
      do
        ++v32;
      while ( a2[v32] );
      if ( v32 == 1 )
      {
        Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, a2, v5, 0, v30);
        if ( Token < 0 && !v30 )
          goto LABEL_111;
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_111;
      }
    }
    if ( v29 == 2 )
      goto LABEL_91;
    if ( v29 )
    {
      if ( !a5 )
      {
        v36 = v29;
        goto LABEL_110;
      }
LABEL_91:
      v7 = v42;
      goto LABEL_92;
    }
    if ( a5 )
    {
      LODWORD(hKey) = 0;
      if ( !RegQueryInfoKeyW(v5, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      {
        if ( (_DWORD)hKey )
        {
          v33 = 0;
          while ( lstrcmpiW(String1, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v33]) )
          {
            if ( ++v33 >= 12 )
            {
              if ( v16 )
              {
                ATL::CRegKey::RecurseDeleteKey(v43, String1);
                v5 = v43[0];
              }
              goto LABEL_91;
            }
          }
          goto LABEL_91;
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
      v43[0] = 0;
      v5 = 0;
      if ( v35 )
        return ATL::AtlHresultFromWin32(v35);
    }
    if ( !v16 )
      goto LABEL_91;
    v7 = v42;
    if ( !v34 )
    {
      v45 = 0;
      v46 = 0;
      v44 = v42;
      v18 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v44, String1);
      if ( v18 )
      {
LABEL_109:
        v36 = v18;
LABEL_110:
        Token = ATL::AtlHresultFromWin32(v36);
        goto LABEL_111;
      }
    }
LABEL_92:
    if ( *a2 == 125 )
      goto LABEL_111;
    v6 = v41;
  }
  if ( v5 )
    RegCloseKey(v5);
  return 2147614729LL;
}

```

## disassembly

```asm
0x140004954  push    rbp
0x140004956  push    rbx
0x140004957  push    rsi
0x140004958  push    rdi
0x140004959  push    r12
0x14000495b  push    r13
0x14000495d  push    r14
0x14000495f  push    r15
0x140004961  lea     rbp, [rsp-21D8h]
0x140004969  mov     eax, 22D8h
0x14000496e  call    _alloca_probe
0x140004973  sub     rsp, rax
0x140004976  mov     rax, cs:__security_cookie
0x14000497d  xor     rax, rsp
0x140004980  mov     [rbp+2210h+var_50], rax
0x140004987  xor     r14d, r14d
0x14000498a  mov     [rsp+2310h+var_22A8], r9d
0x14000498f  mov     edi, r14d
0x140004992  mov     [rsp+2310h+var_2298], r14
0x140004997  mov     [rbp+2210h+var_2290], r14
0x14000499b  mov     r13d, r9d
0x14000499e  mov     [rbp+2210h+var_2288], r14
0x1400049a2  mov     r15, r8
0x1400049a5  mov     [rsp+2310h+var_22A0], r8
0x1400049aa  mov     rsi, rdx
0x1400049ad  mov     r12, rcx
0x1400049b0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1400049b5  mov     ebx, eax
0x1400049b7  test    eax, eax
0x1400049b9  js      loc_14000502C
0x1400049bf  cmp     word ptr [rsi], 7Dh ; '}'
0x1400049c3  jz      loc_14000502A
0x1400049c9  lea     rdx, String2; "Delete"
0x1400049d0  mov     rcx, rsi; lpString1
0x1400049d3  call    cs:__imp_lstrcmpiW
0x1400049d9  lea     rdx, aForceremove; "ForceRemove"
0x1400049e0  mov     rcx, rsi; lpString1
0x1400049e3  mov     r14d, eax
0x1400049e6  call    cs:__imp_lstrcmpiW
0x1400049ec  test    eax, eax
0x1400049ee  jz      short loc_1400049F9
0x1400049f0  test    r14d, r14d
0x1400049f3  jnz     loc_140004ABD
0x1400049f9  mov     rdx, rsi; unsigned __int16 *
0x1400049fc  mov     rcx, r12; this
0x1400049ff  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140004a04  xor     edx, edx
0x140004a06  mov     ebx, eax
0x140004a08  test    eax, eax
0x140004a0a  js      loc_14000501C
0x140004a10  test    r13d, r13d
0x140004a13  jz      loc_140004ABD
0x140004a19  movzx   eax, word ptr [rsi]
0x140004a1c  mov     [rbp+2210h+var_2280], rdx
0x140004a20  mov     [rbp+2210h+var_2278], rdx
0x140004a24  mov     [rbp+2210h+var_2270], rdx
0x140004a28  test    ax, ax
0x140004a2b  jz      short loc_140004A54
0x140004a2d  mov     rcx, rsi; lpsz
0x140004a30  cmp     ax, 5Ch ; '\'
0x140004a34  jz      short loc_140004A4B
0x140004a36  call    cs:__imp_CharNextW
0x140004a3c  mov     rcx, rax
0x140004a3f  xor     edx, edx
0x140004a41  movzx   eax, word ptr [rax]
0x140004a44  test    ax, ax
0x140004a47  jnz     short loc_140004A30
0x140004a49  jmp     short loc_140004A54
0x140004a4b  test    rcx, rcx
0x140004a4e  jnz     loc_140005068
0x140004a54  mov     ebx, edx
0x140004a56  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x140004a5d  mov     edx, ebx
0x140004a5f  mov     rcx, rsi; lpString1
0x140004a62  mov     rdx, [rax+rdx*8]; lpString2
0x140004a66  call    cs:__imp_lstrcmpiW
0x140004a6c  test    eax, eax
0x140004a6e  jz      short loc_140004A87
0x140004a70  inc     ebx
0x140004a72  cmp     ebx, 0Ch
0x140004a75  jl      short loc_140004A56
0x140004a77  mov     rdx, rsi; unsigned __int16 *
0x140004a7a  mov     [rbp+2210h+var_2280], r15
0x140004a7e  lea     rcx, [rbp+2210h+var_2280]; this
0x140004a82  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x140004a87  test    r14d, r14d
0x140004a8a  jnz     short loc_140004ABD
0x140004a8c  mov     rdx, rsi; unsigned __int16 *
0x140004a8f  mov     rcx, r12; this
0x140004a92  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140004a97  mov     ebx, eax
0x140004a99  test    eax, eax
0x140004a9b  js      loc_14000501C
0x140004aa1  mov     rdx, rsi; unsigned __int16 *
0x140004aa4  mov     rcx, r12; this
0x140004aa7  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x140004aac  xor     edx, edx
0x140004aae  mov     ebx, eax
0x140004ab0  test    eax, eax
0x140004ab2  js      loc_14000501C
0x140004ab8  jmp     loc_140004D18
0x140004abd  lea     rdx, aNoremove; "NoRemove"
0x140004ac4  mov     rcx, rsi; lpString1
0x140004ac7  mov     r13d, 1
0x140004acd  call    cs:__imp_lstrcmpiW
0x140004ad3  xor     r14d, r14d
0x140004ad6  test    eax, eax
0x140004ad8  jnz     short loc_140004AF2
0x140004ada  mov     rdx, rsi; unsigned __int16 *
0x140004add  mov     rcx, r12; this
0x140004ae0  mov     r13d, r14d
0x140004ae3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140004ae8  mov     ebx, eax
0x140004aea  test    eax, eax
0x140004aec  js      loc_14000501C
0x140004af2  lea     rdx, aVal; "Val"
0x140004af9  mov     rcx, rsi; lpString1
0x140004afc  call    cs:__imp_lstrcmpiW
0x140004b02  test    eax, eax
0x140004b04  jnz     loc_140004BEF
0x140004b0a  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x140004b11  mov     rcx, r12; this
0x140004b14  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140004b19  mov     ebx, eax
0x140004b1b  test    eax, eax
0x140004b1d  js      loc_14000501C
0x140004b23  mov     rdx, rsi; unsigned __int16 *
0x140004b26  mov     rcx, r12; this
0x140004b29  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140004b2e  xor     edx, edx; lpSubKey
0x140004b30  mov     ebx, eax
0x140004b32  test    eax, eax
0x140004b34  js      loc_14000501C
0x140004b3a  cmp     word ptr [rsi], 3Dh ; '='
0x140004b3e  jnz     loc_140005068
0x140004b44  cmp     [rsp+2310h+var_22A8], edx
0x140004b48  jz      short loc_140004B71
0x140004b4a  mov     [rbp+2210h+var_2278], rdx
0x140004b4e  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x140004b55  mov     [rbp+2210h+var_2270], rdx
0x140004b59  mov     r9, rsi; unsigned __int16 *
0x140004b5c  lea     rdx, [rbp+2210h+var_2280]; struct ATL::CRegKey *
0x140004b60  mov     [rbp+2210h+var_2280], r15
0x140004b64  mov     rcx, r12; this
0x140004b67  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x140004b6c  jmp     loc_140004D07
0x140004b71  cmp     [rbp+2210h+arg_20], edx
0x140004b77  jnz     short loc_140004BD5
0x140004b79  test    r13d, r13d
0x140004b7c  jz      short loc_140004BD5
0x140004b7e  lea     rax, [rsp+2310h+hKey]
0x140004b83  mov     [rsp+2310h+hKey], rdx
0x140004b88  mov     r9d, 20006h; samDesired
0x140004b8e  mov     [rsp+2310h+phkResult], rax; phkResult
0x140004b93  xor     r8d, r8d; ulOptions
0x140004b96  mov     rcx, r15; hKey
0x140004b99  call    cs:__imp_RegOpenKeyExW
0x140004b9f  test    eax, eax
0x140004ba1  jnz     loc_140005013
0x140004ba7  mov     r14, [rsp+2310h+hKey]
0x140004bac  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x140004bb3  mov     rcx, r14; hKey
0x140004bb6  call    cs:__imp_RegDeleteValueW
0x140004bbc  test    eax, 0FFFFFFFDh
0x140004bc1  jnz     loc_14000504F
0x140004bc7  test    r14, r14
0x140004bca  jz      short loc_140004BD5
0x140004bcc  mov     rcx, r14; hKey
0x140004bcf  call    cs:__imp_RegCloseKey
0x140004bd5  mov     rdx, rsi; unsigned __int16 *
0x140004bd8  mov     rcx, r12; this
0x140004bdb  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x140004be0  mov     ebx, eax
0x140004be2  test    eax, eax
0x140004be4  js      loc_14000501C
0x140004bea  jmp     loc_140004EAE
0x140004bef  movzx   eax, word ptr [rsi]
0x140004bf2  test    ax, ax
0x140004bf5  jz      short loc_140004C1C
0x140004bf7  mov     rcx, rsi; lpsz
0x140004bfa  cmp     ax, 5Ch ; '\'
0x140004bfe  jz      short loc_140004C13
0x140004c00  call    cs:__imp_CharNextW
0x140004c06  mov     rcx, rax
0x140004c09  movzx   eax, word ptr [rax]
0x140004c0c  test    ax, ax
0x140004c0f  jnz     short loc_140004BFA
0x140004c11  jmp     short loc_140004C1C
0x140004c13  test    rcx, rcx
0x140004c16  jnz     loc_140005068
0x140004c1c  cmp     [rsp+2310h+var_22A8], r14d
0x140004c21  jz      loc_140004D68
0x140004c27  lea     rax, [rsp+2310h+hKey]
0x140004c2c  mov     [rsp+2310h+hKey], r14
0x140004c31  mov     r9d, 2001Fh; samDesired
0x140004c37  mov     [rsp+2310h+phkResult], rax; phkResult
0x140004c3c  xor     r8d, r8d; ulOptions
0x140004c3f  mov     rdx, rsi; lpSubKey
0x140004c42  mov     rcx, r15; hKey
0x140004c45  call    cs:__imp_RegOpenKeyExW
0x140004c4b  test    eax, eax
0x140004c4d  jnz     short loc_140004C6E
0x140004c4f  mov     eax, r14d
0x140004c52  test    rdi, rdi
0x140004c55  jz      short loc_140004C60
0x140004c57  mov     rcx, rdi; hKey
0x140004c5a  call    cs:__imp_RegCloseKey
0x140004c60  mov     rdi, [rsp+2310h+hKey]
0x140004c65  mov     [rsp+2310h+var_2298], rdi
0x140004c6a  test    eax, eax
0x140004c6c  jz      short loc_140004CD2
0x140004c6e  lea     rax, [rsp+2310h+hKey]
0x140004c73  mov     [rsp+2310h+hKey], r14
0x140004c78  mov     r9d, 20019h; samDesired
0x140004c7e  mov     [rsp+2310h+phkResult], rax; unsigned int
0x140004c83  xor     r8d, r8d; ulOptions
0x140004c86  mov     rdx, rsi; lpSubKey
0x140004c89  mov     rcx, r15; hKey
0x140004c8c  call    cs:__imp_RegOpenKeyExW
0x140004c92  test    eax, eax
0x140004c94  jnz     short loc_140004CB5
0x140004c96  mov     eax, r14d
0x140004c99  test    rdi, rdi
0x140004c9c  jz      short loc_140004CA7
0x140004c9e  mov     rcx, rdi; hKey
0x140004ca1  call    cs:__imp_RegCloseKey
0x140004ca7  mov     rdi, [rsp+2310h+hKey]
0x140004cac  mov     [rsp+2310h+var_2298], rdi
0x140004cb1  test    eax, eax
0x140004cb3  jz      short loc_140004CD2
0x140004cb5  mov     r8, rsi; unsigned __int16 *
0x140004cb8  lea     rcx, [rsp+2310h+var_2298]; this
0x140004cbd  mov     rdx, r15; HKEY
0x140004cc0  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x140004cc5  test    eax, eax
0x140004cc7  jnz     loc_14000507D
0x140004ccd  mov     rdi, [rsp+2310h+var_2298]
0x140004cd2  mov     rdx, rsi; unsigned __int16 *
0x140004cd5  mov     rcx, r12; this
0x140004cd8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140004cdd  xor     edx, edx
0x140004cdf  mov     ebx, eax
0x140004ce1  test    eax, eax
0x140004ce3  js      loc_14000501C
0x140004ce9  cmp     word ptr [rsi], 3Dh ; '='
0x140004ced  jnz     short loc_140004D13
0x140004cef  mov     r9, rsi; unsigned __int16 *
0x140004cf2  lea     rdx, [rsp+2310h+var_2298]; struct ATL::CRegKey *
0x140004cf7  xor     r8d, r8d; unsigned __int16 *
0x140004cfa  mov     rcx, r12; this
0x140004cfd  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x140004d02  mov     rdi, [rsp+2310h+var_2298]
0x140004d07  xor     edx, edx
0x140004d09  mov     ebx, eax
0x140004d0b  test    eax, eax
0x140004d0d  js      loc_14000501C
0x140004d13  mov     r13d, [rsp+2310h+var_22A8]
0x140004d18  cmp     word ptr [rsi], 7Bh ; '{'
0x140004d1c  jnz     loc_140004EAE
0x140004d22  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004d26  inc     rax
0x140004d29  cmp     [rsi+rax*2], dx
0x140004d2d  jnz     short loc_140004D26
0x140004d2f  cmp     rax, 1
0x140004d33  jnz     loc_140004EAE
0x140004d39  mov     dword ptr [rsp+2310h+phkResult], edx; int
0x140004d3d  mov     r9d, r13d; int
0x140004d40  mov     rdx, rsi; unsigned __int16 *
0x140004d43  mov     r8, rdi; HKEY
0x140004d46  mov     rcx, r12; this
0x140004d49  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x140004d4e  mov     ebx, eax
0x140004d50  test    eax, eax
0x140004d52  js      loc_14000501C
0x140004d58  mov     rdx, rsi; unsigned __int16 *
0x140004d5b  mov     rcx, r12; this
0x140004d5e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140004d63  jmp     loc_140004BE0
0x140004d68  mov     ebx, [rbp+2210h+arg_20]
0x140004d6e  test    ebx, ebx
0x140004d70  jnz     short loc_140004DC0
0x140004d72  lea     rax, [rsp+2310h+hKey]
0x140004d77  mov     [rsp+2310h+hKey], r14
0x140004d7c  mov     r9d, 20019h; samDesired
0x140004d82  mov     [rsp+2310h+phkResult], rax; phkResult
0x140004d87  xor     r8d, r8d; ulOptions
0x140004d8a  mov     rdx, rsi; lpSubKey
0x140004d8d  mov     rcx, r15; hKey
0x140004d90  call    cs:__imp_RegOpenKeyExW
0x140004d96  mov     r14d, eax
0x140004d99  xor     eax, eax
0x140004d9b  test    r14d, r14d
0x140004d9e  jnz     short loc_140004DC6
0x140004da0  mov     r14d, eax
0x140004da3  test    rdi, rdi
0x140004da6  jz      short loc_140004DB4
0x140004da8  mov     rcx, rdi; hKey
0x140004dab  call    cs:__imp_RegCloseKey
0x140004db1  mov     r14d, eax
0x140004db4  mov     rdi, [rsp+2310h+hKey]
  ... truncated ...
```
