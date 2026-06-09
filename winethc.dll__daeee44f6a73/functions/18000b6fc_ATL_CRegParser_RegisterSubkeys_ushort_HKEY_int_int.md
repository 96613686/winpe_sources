# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000b6fc`
- end: `0x18000bf36`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `2106`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18000b374`
- `0x18000b6fc`

## callees

- `0x180003b40`
- `0x1800041e0`
- `0x1800041f8`
- `0x180004724`
- `0x18000a924`
- `0x18000b204`
- `0x18000b6fc`
- `0x18000c82c`
- `0x180012db0`
- `0x180012e40`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000bc3f`
- `msvcrt!wcsncpy_s` at `0x18000bc3f`
- `KERNEL32!lstrcmpiW` at `0x18000b77a`
- `KERNEL32!lstrcmpiW` at `0x18000b793`
- `KERNEL32!lstrcmpiW` at `0x18000b81d`
- `KERNEL32!lstrcmpiW` at `0x18000b88c`
- `KERNEL32!lstrcmpiW` at `0x18000b8c0`
- `KERNEL32!lstrcmpiW` at `0x18000bd99`
- `KERNEL32!lstrcmpiW` at `0x18000b77a`
- `KERNEL32!lstrcmpiW` at `0x18000b793`
- `KERNEL32!lstrcmpiW` at `0x18000b81d`
- `KERNEL32!lstrcmpiW` at `0x18000b88c`
- `KERNEL32!lstrcmpiW` at `0x18000b8c0`
- `KERNEL32!lstrcmpiW` at `0x18000bd99`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000bd6c`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000be11`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000bd6c`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000be11`
- `ADVAPI32!RegOpenKeyExW` at `0x18000b963`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ba29`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ba7e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000bbe1`
- `ADVAPI32!RegOpenKeyExW` at `0x18000b963`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ba29`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ba7e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000bbe1`
- `ADVAPI32!RegCreateKeyExW` at `0x18000bae8`
- `ADVAPI32!RegCreateKeyExW` at `0x18000bae8`
- `ADVAPI32!RegDeleteValueW` at `0x18000b986`
- `ADVAPI32!RegDeleteValueW` at `0x18000b986`
- `ADVAPI32!RegCloseKey` at `0x18000b9a5`
- `ADVAPI32!RegCloseKey` at `0x18000ba43`
- `ADVAPI32!RegCloseKey` at `0x18000ba98`
- `ADVAPI32!RegCloseKey` at `0x18000bb06`
- `ADVAPI32!RegCloseKey` at `0x18000bc02`
- `ADVAPI32!RegCloseKey` at `0x18000be36`
- `ADVAPI32!RegCloseKey` at `0x18000be9b`
- `ADVAPI32!RegCloseKey` at `0x18000bede`
- `ADVAPI32!RegCloseKey` at `0x18000bef4`
- `ADVAPI32!RegCloseKey` at `0x18000b9a5`
- `ADVAPI32!RegCloseKey` at `0x18000ba43`
- `ADVAPI32!RegCloseKey` at `0x18000ba98`
- `ADVAPI32!RegCloseKey` at `0x18000bb06`
- `ADVAPI32!RegCloseKey` at `0x18000bc02`
- `ADVAPI32!RegCloseKey` at `0x18000be36`
- `ADVAPI32!RegCloseKey` at `0x18000be9b`
- `ADVAPI32!RegCloseKey` at `0x18000bede`
- `ADVAPI32!RegCloseKey` at `0x18000bef4`
- `USER32!CharNextW` at `0x18000b7eb`
- `USER32!CharNextW` at `0x18000b9dc`
- `USER32!CharNextW` at `0x18000b7eb`
- `USER32!CharNextW` at `0x18000b9dc`

## string_xrefs

- `0x18000b786`: `ForceRemove`
- `0x18000b87c`: `NoRemove`
- `0x18000b770`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
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
  int v17; // eax
  LSTATUS v18; // eax
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
  __int64 v30; // rax
  int v31; // r14d
  int v32; // r14d
  LSTATUS v33; // eax
  unsigned int v34; // ecx
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+68h] [rbp-98h]
  HKEY v37; // [rsp+70h] [rbp-90h]
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v39[3]; // [rsp+80h] [rbp-80h] BYREF
  HKEY v40; // [rsp+98h] [rbp-68h] BYREF
  __int64 v41; // [rsp+A0h] [rbp-60h]
  __int64 v42; // [rsp+A8h] [rbp-58h]
  wchar_t Destination[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR ValueName[4096]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v36 = a4;
  v5 = 0;
  v37 = a3;
  memset(v39, 0, sizeof(v39));
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
        v40 = 0;
        v41 = 0;
        v42 = 0;
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
            v40 = v7;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&v40, a2);
            break;
          }
        }
        if ( !v12 )
        {
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            goto LABEL_112;
          Token = ATL::CRegParser::SkipAssignment(this, a2);
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
          Token = ATL::CRegParser::RegisterSubkeys(this, a2, v5, v6, 0);
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
      if ( v36 )
      {
        v41 = 0;
        v42 = 0;
        v40 = v7;
        v17 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)&v40, ValueName, a2);
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
      v21 = ATL::CRegParser::SkipAssignment(this, a2);
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
    if ( v36 )
    {
      hKey = 0;
      if ( RegOpenKeyExW(v7, a2, 0, 0x2001Fu, &hKey) )
        goto LABEL_128;
      v24 = 0;
      if ( v5 )
        v24 = RegCloseKey(v5);
      v5 = hKey;
      v39[0] = hKey;
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
        v39[0] = hKey;
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
          v39[0] = phkResult;
          if ( v18 )
          {
LABEL_110:
            v34 = v18;
            goto LABEL_111;
          }
        }
      }
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_112;
      if ( *a2 == 61 )
      {
        v17 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)v39, 0, a2);
        v5 = (HKEY)v39[0];
        goto LABEL_59;
      }
LABEL_60:
      v6 = v36;
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
        v39[0] = phkResult;
      }
    }
    v28 = 1;
    if ( !v27 )
      v28 = a5;
    v29 = wcsncpy_s(Destination, 0x104u, a2, 0xFFFFFFFFFFFFFFFFuLL);
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
      goto LABEL_112;
    Token = ATL::CRegParser::SkipAssignment(this, a2);
    if ( Token < 0 )
      goto LABEL_112;
    if ( *a2 == 123 )
    {
      v30 = -1;
      do
        ++v30;
      while ( a2[v30] );
      if ( v30 == 1 )
      {
        Token = ATL::CRegParser::RegisterSubkeys(this, a2, v5, 0, v28);
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
        v7 = v37;
        goto LABEL_93;
      }
      v34 = v27;
LABEL_111:
      Token = ATL::AtlHresultFromWin32(v34);
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
          v31 = 0;
          while ( lstrcmpiW(Destination, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v31]) )
          {
            if ( ++v31 >= 12 )
            {
              if ( v16 )
              {
                ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v39, Destination);
                v5 = (HKEY)v39[0];
              }
              goto LABEL_92;
            }
          }
          goto LABEL_92;
        }
      }
    }
    LODWORD(hKey) = 0;
    v32 = 0;
    if ( !RegQueryInfoKeyW(v5, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      LOBYTE(v32) = (_DWORD)hKey != 0;
    if ( v5 )
    {
      v33 = RegCloseKey(v5);
      v39[0] = 0;
      v5 = 0;
      if ( v33 )
        return ATL::AtlHresultFromWin32(v33);
    }
    if ( !v16 )
      goto LABEL_92;
    v7 = v37;
    if ( !v32 )
    {
      v41 = 0;
      v42 = 0;
      v40 = v37;
      v18 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v40, Destination);
      if ( v18 )
        goto LABEL_110;
    }
LABEL_93:
    if ( *a2 == 125 )
      goto LABEL_112;
    v6 = v36;
  }
LABEL_118:
  if ( v5 )
    RegCloseKey(v5);
  return 2147614729LL;
}

```

## disassembly

```asm
0x18000b6fc  push    rbp
0x18000b6fe  push    rbx
0x18000b6ff  push    rsi
0x18000b700  push    rdi
0x18000b701  push    r12
0x18000b703  push    r13
0x18000b705  push    r14
0x18000b707  push    r15
0x18000b709  lea     rbp, [rsp-21D8h]
0x18000b711  mov     eax, 22D8h
0x18000b716  call    _alloca_probe
0x18000b71b  sub     rsp, rax
0x18000b71e  mov     rax, cs:__security_cookie
0x18000b725  xor     rax, rsp
0x18000b728  mov     [rbp+2210h+var_50], rax
0x18000b72f  xor     r14d, r14d
0x18000b732  mov     [rsp+2310h+var_22A8], r9d
0x18000b737  mov     ebx, r14d
0x18000b73a  mov     [rsp+2310h+var_22A0], r8
0x18000b73f  mov     [rbp+2210h+var_2290], rbx
0x18000b743  mov     r12d, r9d
0x18000b746  mov     r15, r8
0x18000b749  mov     [rbp+2210h+var_2288], r14
0x18000b74d  mov     rsi, rdx
0x18000b750  mov     [rbp+2210h+var_2280], r14
0x18000b754  mov     r13, rcx
0x18000b757  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b75c  mov     edi, eax
0x18000b75e  test    eax, eax
0x18000b760  js      loc_18000BEA9
0x18000b766  cmp     word ptr [rsi], 7Dh ; '}'
0x18000b76a  jz      loc_18000BEA7
0x18000b770  lea     rdx, aDelete; "Delete"
0x18000b777  mov     rcx, rsi; lpString1
0x18000b77a  call    cs:__imp_lstrcmpiW
0x18000b781  nop     dword ptr [rax+rax+00h]
0x18000b786  lea     rdx, aForceremove; "ForceRemove"
0x18000b78d  mov     rcx, rsi; lpString1
0x18000b790  mov     r14d, eax
0x18000b793  call    cs:__imp_lstrcmpiW
0x18000b79a  nop     dword ptr [rax+rax+00h]
0x18000b79f  xor     edi, edi
0x18000b7a1  test    eax, eax
0x18000b7a3  jz      short loc_18000B7AE
0x18000b7a5  test    r14d, r14d
0x18000b7a8  jnz     loc_18000B87C
0x18000b7ae  mov     rdx, rsi; unsigned __int16 *
0x18000b7b1  mov     rcx, r13; this
0x18000b7b4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b7b9  mov     edi, eax
0x18000b7bb  test    eax, eax
0x18000b7bd  js      loc_18000BE93
0x18000b7c3  xor     edi, edi
0x18000b7c5  test    r12d, r12d
0x18000b7c8  jz      loc_18000B87C
0x18000b7ce  movzx   eax, word ptr [rsi]
0x18000b7d1  mov     [rbp+2210h+var_2278], rdi
0x18000b7d5  mov     [rbp+2210h+var_2270], rdi
0x18000b7d9  mov     [rbp+2210h+var_2268], rdi
0x18000b7dd  test    ax, ax
0x18000b7e0  jz      short loc_18000B80D
0x18000b7e2  mov     rcx, rsi; lpsz
0x18000b7e5  cmp     ax, 5Ch ; '\'
0x18000b7e9  jz      short loc_18000B804
0x18000b7eb  call    cs:__imp_CharNextW
0x18000b7f2  nop     dword ptr [rax+rax+00h]
0x18000b7f7  mov     rcx, rax
0x18000b7fa  movzx   eax, word ptr [rax]
0x18000b7fd  test    ax, ax
0x18000b800  jnz     short loc_18000B7E5
0x18000b802  jmp     short loc_18000B80D
0x18000b804  test    rcx, rcx
0x18000b807  jnz     loc_18000BEEC
0x18000b80d  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x18000b814  mov     edx, edi
0x18000b816  mov     rcx, rsi; lpString1
0x18000b819  mov     rdx, [rax+rdx*8]; lpString2
0x18000b81d  call    cs:__imp_lstrcmpiW
0x18000b824  nop     dword ptr [rax+rax+00h]
0x18000b829  test    eax, eax
0x18000b82b  jz      short loc_18000B844
0x18000b82d  inc     edi
0x18000b82f  cmp     edi, 0Ch
0x18000b832  jl      short loc_18000B80D
0x18000b834  mov     rdx, rsi; unsigned __int16 *
0x18000b837  mov     [rbp+2210h+var_2278], r15
0x18000b83b  lea     rcx, [rbp+2210h+var_2278]; this
0x18000b83f  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000b844  xor     edi, edi
0x18000b846  test    r14d, r14d
0x18000b849  jnz     short loc_18000B87C
0x18000b84b  mov     rdx, rsi; unsigned __int16 *
0x18000b84e  mov     rcx, r13; this
0x18000b851  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b856  mov     edi, eax
0x18000b858  test    eax, eax
0x18000b85a  js      loc_18000BE93
0x18000b860  mov     rdx, rsi; unsigned __int16 *
0x18000b863  mov     rcx, r13; this
0x18000b866  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000b86b  xor     edx, edx
0x18000b86d  mov     edi, eax
0x18000b86f  test    eax, eax
0x18000b871  js      loc_18000BE93
0x18000b877  jmp     loc_18000BB67
0x18000b87c  lea     rdx, aNoremove; "NoRemove"
0x18000b883  mov     rcx, rsi; lpString1
0x18000b886  mov     r12d, 1
0x18000b88c  call    cs:__imp_lstrcmpiW
0x18000b893  nop     dword ptr [rax+rax+00h]
0x18000b898  test    eax, eax
0x18000b89a  jnz     short loc_18000B8B6
0x18000b89c  mov     rdx, rsi; unsigned __int16 *
0x18000b89f  mov     rcx, r13; this
0x18000b8a2  mov     r12d, edi
0x18000b8a5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b8aa  mov     edi, eax
0x18000b8ac  test    eax, eax
0x18000b8ae  js      loc_18000BE93
0x18000b8b4  xor     edi, edi
0x18000b8b6  lea     rdx, aVal; "Val"
0x18000b8bd  mov     rcx, rsi; lpString1
0x18000b8c0  call    cs:__imp_lstrcmpiW
0x18000b8c7  nop     dword ptr [rax+rax+00h]
0x18000b8cc  test    eax, eax
0x18000b8ce  jnz     loc_18000B9CB
0x18000b8d4  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x18000b8db  mov     rcx, r13; this
0x18000b8de  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b8e3  mov     edi, eax
0x18000b8e5  test    eax, eax
0x18000b8e7  js      loc_18000BE93
0x18000b8ed  mov     rdx, rsi; unsigned __int16 *
0x18000b8f0  mov     rcx, r13; this
0x18000b8f3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b8f8  xor     edx, edx; lpSubKey
0x18000b8fa  mov     edi, eax
0x18000b8fc  test    eax, eax
0x18000b8fe  js      loc_18000BE93
0x18000b904  cmp     word ptr [rsi], 3Dh ; '='
0x18000b908  jnz     loc_18000BEEC
0x18000b90e  cmp     [rsp+2310h+var_22A8], edx
0x18000b912  jz      short loc_18000B93B
0x18000b914  mov     [rbp+2210h+var_2270], rdx
0x18000b918  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x18000b91f  mov     [rbp+2210h+var_2268], rdx
0x18000b923  mov     r9, rsi; unsigned __int16 *
0x18000b926  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x18000b92a  mov     [rbp+2210h+var_2278], r15
0x18000b92e  mov     rcx, r13; this
0x18000b931  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000b936  jmp     loc_18000BB56
0x18000b93b  cmp     [rbp+2210h+arg_20], edx
0x18000b941  jnz     short loc_18000B9B1
0x18000b943  test    r12d, r12d
0x18000b946  jz      short loc_18000B9B1
0x18000b948  lea     rax, [rsp+2310h+hKey]
0x18000b94d  mov     [rsp+2310h+hKey], rdx
0x18000b952  mov     r9d, 20006h; samDesired
0x18000b958  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000b95d  xor     r8d, r8d; ulOptions
0x18000b960  mov     rcx, r15; hKey
0x18000b963  call    cs:__imp_RegOpenKeyExW
0x18000b96a  nop     dword ptr [rax+rax+00h]
0x18000b96f  test    eax, eax
0x18000b971  jnz     loc_18000BE8A
0x18000b977  mov     r14, [rsp+2310h+hKey]
0x18000b97c  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x18000b983  mov     rcx, r14; hKey
0x18000b986  call    cs:__imp_RegDeleteValueW
0x18000b98d  nop     dword ptr [rax+rax+00h]
0x18000b992  test    eax, 0FFFFFFFDh
0x18000b997  jnz     loc_18000BECD
0x18000b99d  test    r14, r14
0x18000b9a0  jz      short loc_18000B9B1
0x18000b9a2  mov     rcx, r14; hKey
0x18000b9a5  call    cs:__imp_RegCloseKey
0x18000b9ac  nop     dword ptr [rax+rax+00h]
0x18000b9b1  mov     rdx, rsi; unsigned __int16 *
0x18000b9b4  mov     rcx, r13; this
0x18000b9b7  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000b9bc  mov     edi, eax
0x18000b9be  test    eax, eax
0x18000b9c0  js      loc_18000BE93
0x18000b9c6  jmp     loc_18000BD10
0x18000b9cb  movzx   eax, word ptr [rsi]
0x18000b9ce  test    ax, ax
0x18000b9d1  jz      short loc_18000B9FE
0x18000b9d3  mov     rcx, rsi; lpsz
0x18000b9d6  cmp     ax, 5Ch ; '\'
0x18000b9da  jz      short loc_18000B9F5
0x18000b9dc  call    cs:__imp_CharNextW
0x18000b9e3  nop     dword ptr [rax+rax+00h]
0x18000b9e8  mov     rcx, rax
0x18000b9eb  movzx   eax, word ptr [rax]
0x18000b9ee  test    ax, ax
0x18000b9f1  jnz     short loc_18000B9D6
0x18000b9f3  jmp     short loc_18000B9FE
0x18000b9f5  test    rcx, rcx
0x18000b9f8  jnz     loc_18000BEEC
0x18000b9fe  cmp     [rsp+2310h+var_22A8], edi
0x18000ba02  jz      loc_18000BBB7
0x18000ba08  lea     rax, [rsp+2310h+hKey]
0x18000ba0d  mov     [rsp+2310h+hKey], rdi
0x18000ba12  mov     r14d, 2001Fh
0x18000ba18  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000ba1d  mov     r9d, r14d; samDesired
0x18000ba20  xor     r8d, r8d; ulOptions
0x18000ba23  mov     rdx, rsi; lpSubKey
0x18000ba26  mov     rcx, r15; hKey
0x18000ba29  call    cs:__imp_RegOpenKeyExW
0x18000ba30  nop     dword ptr [rax+rax+00h]
0x18000ba35  test    eax, eax
0x18000ba37  jnz     short loc_18000BA60
0x18000ba39  mov     eax, edi
0x18000ba3b  test    rbx, rbx
0x18000ba3e  jz      short loc_18000BA4F
0x18000ba40  mov     rcx, rbx; hKey
0x18000ba43  call    cs:__imp_RegCloseKey
0x18000ba4a  nop     dword ptr [rax+rax+00h]
0x18000ba4f  mov     rbx, [rsp+2310h+hKey]
0x18000ba54  mov     [rbp+2210h+var_2290], rbx
0x18000ba58  test    eax, eax
0x18000ba5a  jz      loc_18000BB23
0x18000ba60  lea     rax, [rsp+2310h+hKey]
0x18000ba65  mov     [rsp+2310h+hKey], rdi
0x18000ba6a  mov     r9d, 20019h; samDesired
0x18000ba70  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000ba75  xor     r8d, r8d; ulOptions
0x18000ba78  mov     rdx, rsi; lpSubKey
0x18000ba7b  mov     rcx, r15; hKey
0x18000ba7e  call    cs:__imp_RegOpenKeyExW
0x18000ba85  nop     dword ptr [rax+rax+00h]
0x18000ba8a  test    eax, eax
0x18000ba8c  jnz     short loc_18000BAB1
0x18000ba8e  mov     eax, edi
0x18000ba90  test    rbx, rbx
0x18000ba93  jz      short loc_18000BAA4
0x18000ba95  mov     rcx, rbx; hKey
0x18000ba98  call    cs:__imp_RegCloseKey
0x18000ba9f  nop     dword ptr [rax+rax+00h]
0x18000baa4  mov     rbx, [rsp+2310h+hKey]
0x18000baa9  mov     [rbp+2210h+var_2290], rbx
0x18000baad  test    eax, eax
0x18000baaf  jz      short loc_18000BB23
0x18000bab1  lea     rax, [rsp+2310h+hKey]
0x18000bab6  mov     dword ptr [rsp+2310h+hKey], edi
0x18000baba  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x18000babf  xor     r9d, r9d; lpClass
0x18000bac2  lea     rax, [rsp+2310h+var_2298]
0x18000bac7  mov     [rsp+2310h+var_2298], rdi
0x18000bacc  mov     [rsp+2310h+var_22D8], rax; phkResult
0x18000bad1  xor     r8d, r8d; Reserved
0x18000bad4  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000bad9  mov     rdx, rsi; lpSubKey
0x18000badc  mov     [rsp+2310h+samDesired], r14d; samDesired
0x18000bae1  mov     rcx, r15; hKey
0x18000bae4  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x18000bae8  call    cs:__imp_RegCreateKeyExW
0x18000baef  nop     dword ptr [rax+rax+00h]
0x18000baf4  test    eax, eax
0x18000baf6  jnz     loc_18000BE8A
0x18000bafc  mov     eax, edi
0x18000bafe  test    rbx, rbx
0x18000bb01  jz      short loc_18000BB12
0x18000bb03  mov     rcx, rbx; hKey
0x18000bb06  call    cs:__imp_RegCloseKey
0x18000bb0d  nop     dword ptr [rax+rax+00h]
0x18000bb12  mov     rbx, [rsp+2310h+var_2298]
0x18000bb17  mov     [rbp+2210h+var_2290], rbx
0x18000bb1b  test    eax, eax
0x18000bb1d  jnz     loc_18000BE8A
0x18000bb23  mov     rdx, rsi; unsigned __int16 *
0x18000bb26  mov     rcx, r13; this
0x18000bb29  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000bb2e  xor     edx, edx
0x18000bb30  mov     edi, eax
0x18000bb32  test    eax, eax
0x18000bb34  js      loc_18000BE93
0x18000bb3a  cmp     word ptr [rsi], 3Dh ; '='
0x18000bb3e  jnz     short loc_18000BB62
0x18000bb40  mov     r9, rsi; unsigned __int16 *
0x18000bb43  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x18000bb47  xor     r8d, r8d; unsigned __int16 *
0x18000bb4a  mov     rcx, r13; this
0x18000bb4d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000bb52  mov     rbx, [rbp+2210h+var_2290]
0x18000bb56  xor     edx, edx
0x18000bb58  mov     edi, eax
0x18000bb5a  test    eax, eax
0x18000bb5c  js      loc_18000BE93
0x18000bb62  mov     r12d, [rsp+2310h+var_22A8]
0x18000bb67  cmp     word ptr [rsi], 7Bh ; '{'
0x18000bb6b  jnz     loc_18000BD10
0x18000bb71  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bb75  inc     rax
0x18000bb78  cmp     [rsi+rax*2], dx
0x18000bb7c  jnz     short loc_18000BB75
0x18000bb7e  cmp     rax, 1
0x18000bb82  jnz     loc_18000BD10
  ... truncated ...
```
