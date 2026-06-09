# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x1800049ec`
- end: `0x180005189`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1949`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180004698`
- `0x1800049ec`

## callees

- `0x1800030f4`
- `0x180003858`
- `0x180003870`
- `0x180003ce8`
- `0x180003fe0`
- `0x180004548`
- `0x1800049ec`
- `0x180005364`
- `0x18001bf40`
- `0x18001c000`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180004ec3`
- `msvcrt!wcsncpy_s` at `0x180004ec3`
- `KERNEL32!lstrcmpiW` at `0x180004a6a`
- `KERNEL32!lstrcmpiW` at `0x180004a7d`
- `KERNEL32!lstrcmpiW` at `0x180004afb`
- `KERNEL32!lstrcmpiW` at `0x180004b64`
- `KERNEL32!lstrcmpiW` at `0x180004b92`
- `KERNEL32!lstrcmpiW` at `0x180005011`
- `KERNEL32!lstrcmpiW` at `0x180004a6a`
- `KERNEL32!lstrcmpiW` at `0x180004a7d`
- `KERNEL32!lstrcmpiW` at `0x180004afb`
- `KERNEL32!lstrcmpiW` at `0x180004b64`
- `KERNEL32!lstrcmpiW` at `0x180004b92`
- `KERNEL32!lstrcmpiW` at `0x180005011`
- `USER32!CharNextW` at `0x180004acf`
- `USER32!CharNextW` at `0x180004c96`
- `USER32!CharNextW` at `0x180004acf`
- `USER32!CharNextW` at `0x180004c96`
- `ADVAPI32!RegCloseKey` at `0x180004c65`
- `ADVAPI32!RegCloseKey` at `0x180004cf1`
- `ADVAPI32!RegCloseKey` at `0x180004d3a`
- `ADVAPI32!RegCloseKey` at `0x180004d9c`
- `ADVAPI32!RegCloseKey` at `0x180004e8c`
- `ADVAPI32!RegCloseKey` at `0x1800050a2`
- `ADVAPI32!RegCloseKey` at `0x180005101`
- `ADVAPI32!RegCloseKey` at `0x18000513d`
- `ADVAPI32!RegCloseKey` at `0x18000514d`
- `ADVAPI32!RegCloseKey` at `0x180004c65`
- `ADVAPI32!RegCloseKey` at `0x180004cf1`
- `ADVAPI32!RegCloseKey` at `0x180004d3a`
- `ADVAPI32!RegCloseKey` at `0x180004d9c`
- `ADVAPI32!RegCloseKey` at `0x180004e8c`
- `ADVAPI32!RegCloseKey` at `0x1800050a2`
- `ADVAPI32!RegCloseKey` at `0x180005101`
- `ADVAPI32!RegCloseKey` at `0x18000513d`
- `ADVAPI32!RegCloseKey` at `0x18000514d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180004fea`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005083`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180004fea`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005083`
- `ADVAPI32!RegOpenKeyExW` at `0x180004c2f`
- `ADVAPI32!RegOpenKeyExW` at `0x180004cdd`
- `ADVAPI32!RegOpenKeyExW` at `0x180004d26`
- `ADVAPI32!RegOpenKeyExW` at `0x180004e71`
- `ADVAPI32!RegOpenKeyExW` at `0x180004c2f`
- `ADVAPI32!RegOpenKeyExW` at `0x180004cdd`
- `ADVAPI32!RegOpenKeyExW` at `0x180004d26`
- `ADVAPI32!RegOpenKeyExW` at `0x180004e71`
- `ADVAPI32!RegCreateKeyExW` at `0x180004d84`
- `ADVAPI32!RegCreateKeyExW` at `0x180004d84`
- `ADVAPI32!RegDeleteValueW` at `0x180004c4c`
- `ADVAPI32!RegDeleteValueW` at `0x180004c4c`

## string_xrefs

- `0x180004a70`: `ForceRemove`
- `0x180004b54`: `NoRemove`
- `0x180004a60`: `Delete`

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
0x1800049ec  push    rbp
0x1800049ee  push    rbx
0x1800049ef  push    rsi
0x1800049f0  push    rdi
0x1800049f1  push    r12
0x1800049f3  push    r13
0x1800049f5  push    r14
0x1800049f7  push    r15
0x1800049f9  lea     rbp, [rsp-21D8h]
0x180004a01  mov     eax, 22D8h
0x180004a06  call    _alloca_probe
0x180004a0b  sub     rsp, rax
0x180004a0e  mov     rax, cs:__security_cookie
0x180004a15  xor     rax, rsp
0x180004a18  mov     [rbp+2210h+var_50], rax
0x180004a1f  xor     r14d, r14d
0x180004a22  mov     [rsp+2310h+var_22A8], r9d
0x180004a27  mov     ebx, r14d
0x180004a2a  mov     [rsp+2310h+var_22A0], r8
0x180004a2f  mov     [rbp+2210h+var_2290], rbx
0x180004a33  mov     r12d, r9d
0x180004a36  mov     r15, r8
0x180004a39  mov     [rbp+2210h+var_2288], r14
0x180004a3d  mov     rsi, rdx
0x180004a40  mov     [rbp+2210h+var_2280], r14
0x180004a44  mov     r13, rcx
0x180004a47  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004a4c  mov     edi, eax
0x180004a4e  test    eax, eax
0x180004a50  js      loc_180005109
0x180004a56  cmp     word ptr [rsi], 7Dh ; '}'
0x180004a5a  jz      loc_180005107
0x180004a60  lea     rdx, String2; "Delete"
0x180004a67  mov     rcx, rsi; lpString1
0x180004a6a  call    cs:__imp_lstrcmpiW
0x180004a70  lea     rdx, aForceremove; "ForceRemove"
0x180004a77  mov     rcx, rsi; lpString1
0x180004a7a  mov     r14d, eax
0x180004a7d  call    cs:__imp_lstrcmpiW
0x180004a83  xor     edi, edi
0x180004a85  test    eax, eax
0x180004a87  jz      short loc_180004A92
0x180004a89  test    r14d, r14d
0x180004a8c  jnz     loc_180004B54
0x180004a92  mov     rdx, rsi; unsigned __int16 *
0x180004a95  mov     rcx, r13; this
0x180004a98  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004a9d  mov     edi, eax
0x180004a9f  test    eax, eax
0x180004aa1  js      loc_1800050F9
0x180004aa7  xor     edi, edi
0x180004aa9  test    r12d, r12d
0x180004aac  jz      loc_180004B54
0x180004ab2  movzx   eax, word ptr [rsi]
0x180004ab5  mov     [rbp+2210h+var_2278], rdi
0x180004ab9  mov     [rbp+2210h+var_2270], rdi
0x180004abd  mov     [rbp+2210h+var_2268], rdi
0x180004ac1  test    ax, ax
0x180004ac4  jz      short loc_180004AEB
0x180004ac6  mov     rcx, rsi; lpsz
0x180004ac9  cmp     ax, 5Ch ; '\'
0x180004acd  jz      short loc_180004AE2
0x180004acf  call    cs:__imp_CharNextW
0x180004ad5  mov     rcx, rax
0x180004ad8  movzx   eax, word ptr [rax]
0x180004adb  test    ax, ax
0x180004ade  jnz     short loc_180004AC9
0x180004ae0  jmp     short loc_180004AEB
0x180004ae2  test    rcx, rcx
0x180004ae5  jnz     loc_180005145
0x180004aeb  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180004af2  mov     edx, edi
0x180004af4  mov     rcx, rsi; lpString1
0x180004af7  mov     rdx, [rax+rdx*8]; lpString2
0x180004afb  call    cs:__imp_lstrcmpiW
0x180004b01  test    eax, eax
0x180004b03  jz      short loc_180004B1C
0x180004b05  inc     edi
0x180004b07  cmp     edi, 0Ch
0x180004b0a  jl      short loc_180004AEB
0x180004b0c  mov     rdx, rsi; unsigned __int16 *
0x180004b0f  mov     [rbp+2210h+var_2278], r15
0x180004b13  lea     rcx, [rbp+2210h+var_2278]; this
0x180004b17  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180004b1c  xor     edi, edi
0x180004b1e  test    r14d, r14d
0x180004b21  jnz     short loc_180004B54
0x180004b23  mov     rdx, rsi; unsigned __int16 *
0x180004b26  mov     rcx, r13; this
0x180004b29  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004b2e  mov     edi, eax
0x180004b30  test    eax, eax
0x180004b32  js      loc_1800050F9
0x180004b38  mov     rdx, rsi; unsigned __int16 *
0x180004b3b  mov     rcx, r13; this
0x180004b3e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180004b43  xor     edx, edx
0x180004b45  mov     edi, eax
0x180004b47  test    eax, eax
0x180004b49  js      loc_1800050F9
0x180004b4f  jmp     loc_180004DF7
0x180004b54  lea     rdx, aNoremove; "NoRemove"
0x180004b5b  mov     rcx, rsi; lpString1
0x180004b5e  mov     r12d, 1
0x180004b64  call    cs:__imp_lstrcmpiW
0x180004b6a  test    eax, eax
0x180004b6c  jnz     short loc_180004B88
0x180004b6e  mov     rdx, rsi; unsigned __int16 *
0x180004b71  mov     rcx, r13; this
0x180004b74  mov     r12d, edi
0x180004b77  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004b7c  mov     edi, eax
0x180004b7e  test    eax, eax
0x180004b80  js      loc_1800050F9
0x180004b86  xor     edi, edi
0x180004b88  lea     rdx, aVal; "Val"
0x180004b8f  mov     rcx, rsi; lpString1
0x180004b92  call    cs:__imp_lstrcmpiW
0x180004b98  test    eax, eax
0x180004b9a  jnz     loc_180004C85
0x180004ba0  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180004ba7  mov     rcx, r13; this
0x180004baa  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004baf  mov     edi, eax
0x180004bb1  test    eax, eax
0x180004bb3  js      loc_1800050F9
0x180004bb9  mov     rdx, rsi; unsigned __int16 *
0x180004bbc  mov     rcx, r13; this
0x180004bbf  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004bc4  xor     edx, edx; lpSubKey
0x180004bc6  mov     edi, eax
0x180004bc8  test    eax, eax
0x180004bca  js      loc_1800050F9
0x180004bd0  cmp     word ptr [rsi], 3Dh ; '='
0x180004bd4  jnz     loc_180005145
0x180004bda  cmp     [rsp+2310h+var_22A8], edx
0x180004bde  jz      short loc_180004C07
0x180004be0  mov     [rbp+2210h+var_2270], rdx
0x180004be4  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180004beb  mov     [rbp+2210h+var_2268], rdx
0x180004bef  mov     r9, rsi; unsigned __int16 *
0x180004bf2  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180004bf6  mov     [rbp+2210h+var_2278], r15
0x180004bfa  mov     rcx, r13; this
0x180004bfd  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180004c02  jmp     loc_180004DE6
0x180004c07  cmp     [rbp+2210h+arg_20], edx
0x180004c0d  jnz     short loc_180004C6B
0x180004c0f  test    r12d, r12d
0x180004c12  jz      short loc_180004C6B
0x180004c14  lea     rax, [rsp+2310h+hKey]
0x180004c19  mov     [rsp+2310h+hKey], rdx
0x180004c1e  mov     r9d, 20006h; samDesired
0x180004c24  mov     [rsp+2310h+phkResult], rax; phkResult
0x180004c29  xor     r8d, r8d; ulOptions
0x180004c2c  mov     rcx, r15; hKey
0x180004c2f  call    cs:__imp_RegOpenKeyExW
0x180004c35  test    eax, eax
0x180004c37  jnz     loc_1800050F0
0x180004c3d  mov     r14, [rsp+2310h+hKey]
0x180004c42  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x180004c49  mov     rcx, r14; hKey
0x180004c4c  call    cs:__imp_RegDeleteValueW
0x180004c52  test    eax, 0FFFFFFFDh
0x180004c57  jnz     loc_18000512C
0x180004c5d  test    r14, r14
0x180004c60  jz      short loc_180004C6B
0x180004c62  mov     rcx, r14; hKey
0x180004c65  call    cs:__imp_RegCloseKey
0x180004c6b  mov     rdx, rsi; unsigned __int16 *
0x180004c6e  mov     rcx, r13; this
0x180004c71  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180004c76  mov     edi, eax
0x180004c78  test    eax, eax
0x180004c7a  js      loc_1800050F9
0x180004c80  jmp     loc_180004F8E
0x180004c85  movzx   eax, word ptr [rsi]
0x180004c88  test    ax, ax
0x180004c8b  jz      short loc_180004CB2
0x180004c8d  mov     rcx, rsi; lpsz
0x180004c90  cmp     ax, 5Ch ; '\'
0x180004c94  jz      short loc_180004CA9
0x180004c96  call    cs:__imp_CharNextW
0x180004c9c  mov     rcx, rax
0x180004c9f  movzx   eax, word ptr [rax]
0x180004ca2  test    ax, ax
0x180004ca5  jnz     short loc_180004C90
0x180004ca7  jmp     short loc_180004CB2
0x180004ca9  test    rcx, rcx
0x180004cac  jnz     loc_180005145
0x180004cb2  cmp     [rsp+2310h+var_22A8], edi
0x180004cb6  jz      loc_180004E47
0x180004cbc  lea     rax, [rsp+2310h+hKey]
0x180004cc1  mov     [rsp+2310h+hKey], rdi
0x180004cc6  mov     r14d, 2001Fh
0x180004ccc  mov     [rsp+2310h+phkResult], rax; phkResult
0x180004cd1  mov     r9d, r14d; samDesired
0x180004cd4  xor     r8d, r8d; ulOptions
0x180004cd7  mov     rdx, rsi; lpSubKey
0x180004cda  mov     rcx, r15; hKey
0x180004cdd  call    cs:__imp_RegOpenKeyExW
0x180004ce3  test    eax, eax
0x180004ce5  jnz     short loc_180004D08
0x180004ce7  mov     eax, edi
0x180004ce9  test    rbx, rbx
0x180004cec  jz      short loc_180004CF7
0x180004cee  mov     rcx, rbx; hKey
0x180004cf1  call    cs:__imp_RegCloseKey
0x180004cf7  mov     rbx, [rsp+2310h+hKey]
0x180004cfc  mov     [rbp+2210h+var_2290], rbx
0x180004d00  test    eax, eax
0x180004d02  jz      loc_180004DB3
0x180004d08  lea     rax, [rsp+2310h+hKey]
0x180004d0d  mov     [rsp+2310h+hKey], rdi
0x180004d12  mov     r9d, 20019h; samDesired
0x180004d18  mov     [rsp+2310h+phkResult], rax; phkResult
0x180004d1d  xor     r8d, r8d; ulOptions
0x180004d20  mov     rdx, rsi; lpSubKey
0x180004d23  mov     rcx, r15; hKey
0x180004d26  call    cs:__imp_RegOpenKeyExW
0x180004d2c  test    eax, eax
0x180004d2e  jnz     short loc_180004D4D
0x180004d30  mov     eax, edi
0x180004d32  test    rbx, rbx
0x180004d35  jz      short loc_180004D40
0x180004d37  mov     rcx, rbx; hKey
0x180004d3a  call    cs:__imp_RegCloseKey
0x180004d40  mov     rbx, [rsp+2310h+hKey]
0x180004d45  mov     [rbp+2210h+var_2290], rbx
0x180004d49  test    eax, eax
0x180004d4b  jz      short loc_180004DB3
0x180004d4d  lea     rax, [rsp+2310h+hKey]
0x180004d52  mov     dword ptr [rsp+2310h+hKey], edi
0x180004d56  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180004d5b  xor     r9d, r9d; lpClass
0x180004d5e  lea     rax, [rsp+2310h+var_2298]
0x180004d63  mov     [rsp+2310h+var_2298], rdi
0x180004d68  mov     [rsp+2310h+var_22D8], rax; phkResult
0x180004d6d  xor     r8d, r8d; Reserved
0x180004d70  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180004d75  mov     rdx, rsi; lpSubKey
0x180004d78  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180004d7d  mov     rcx, r15; hKey
0x180004d80  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x180004d84  call    cs:__imp_RegCreateKeyExW
0x180004d8a  test    eax, eax
0x180004d8c  jnz     loc_1800050F0
0x180004d92  mov     eax, edi
0x180004d94  test    rbx, rbx
0x180004d97  jz      short loc_180004DA2
0x180004d99  mov     rcx, rbx; hKey
0x180004d9c  call    cs:__imp_RegCloseKey
0x180004da2  mov     rbx, [rsp+2310h+var_2298]
0x180004da7  mov     [rbp+2210h+var_2290], rbx
0x180004dab  test    eax, eax
0x180004dad  jnz     loc_1800050F0
0x180004db3  mov     rdx, rsi; unsigned __int16 *
0x180004db6  mov     rcx, r13; this
0x180004db9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004dbe  xor     edx, edx
0x180004dc0  mov     edi, eax
0x180004dc2  test    eax, eax
0x180004dc4  js      loc_1800050F9
0x180004dca  cmp     word ptr [rsi], 3Dh ; '='
0x180004dce  jnz     short loc_180004DF2
0x180004dd0  mov     r9, rsi; unsigned __int16 *
0x180004dd3  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x180004dd7  xor     r8d, r8d; unsigned __int16 *
0x180004dda  mov     rcx, r13; this
0x180004ddd  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180004de2  mov     rbx, [rbp+2210h+var_2290]
0x180004de6  xor     edx, edx
0x180004de8  mov     edi, eax
0x180004dea  test    eax, eax
0x180004dec  js      loc_1800050F9
0x180004df2  mov     r12d, [rsp+2310h+var_22A8]
0x180004df7  cmp     word ptr [rsi], 7Bh ; '{'
0x180004dfb  jnz     loc_180004F8E
0x180004e01  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004e05  inc     rax
0x180004e08  cmp     [rsi+rax*2], dx
0x180004e0c  jnz     short loc_180004E05
0x180004e0e  cmp     rax, 1
0x180004e12  jnz     loc_180004F8E
0x180004e18  mov     dword ptr [rsp+2310h+phkResult], edx; int
0x180004e1c  mov     r9d, r12d; int
0x180004e1f  mov     rdx, rsi; unsigned __int16 *
0x180004e22  mov     r8, rbx; HKEY
0x180004e25  mov     rcx, r13; this
0x180004e28  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180004e2d  mov     edi, eax
0x180004e2f  test    eax, eax
0x180004e31  js      loc_1800050F9
0x180004e37  mov     rdx, rsi; unsigned __int16 *
0x180004e3a  mov     rcx, r13; this
0x180004e3d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004e42  jmp     loc_180004C76
0x180004e47  mov     edi, [rbp+2210h+arg_20]
0x180004e4d  xor     eax, eax
0x180004e4f  test    edi, edi
  ... truncated ...
```
