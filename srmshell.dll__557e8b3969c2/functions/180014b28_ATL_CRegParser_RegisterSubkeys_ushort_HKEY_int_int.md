# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180014b28`
- end: `0x180015379`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `2129`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x1800147c0`
- `0x180014b28`

## callees

- `0x1800065bc`
- `0x1800126ec`
- `0x180012e40`
- `0x180013e88`
- `0x180014050`
- `0x180014668`
- `0x180014b28`
- `0x180015580`
- `0x18001b420`
- `0x18001b4e0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180015045`
- `msvcrt!wcsncpy_s` at `0x180015045`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180014c0b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180014e02`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180014c0b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180014e02`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014efa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014efa`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001516c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180015207`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001516c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180015207`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014dcd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014e5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014eac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014f12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015007`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015226`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001528c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800152b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800152ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800152ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015324`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014dcd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014e5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014eac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014f12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015007`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015226`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001528c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800152b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800152ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800152ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015324`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180014db2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180014db2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014d90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014e49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014e98`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014fec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014d90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014e49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014e98`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014fec`
- `KERNEL32!lstrcmpiW` at `0x180014ba6`
- `KERNEL32!lstrcmpiW` at `0x180014bb9`
- `KERNEL32!lstrcmpiW` at `0x180014c37`
- `KERNEL32!lstrcmpiW` at `0x180014ca8`
- `KERNEL32!lstrcmpiW` at `0x180014cd6`
- `KERNEL32!lstrcmpiW` at `0x180015193`
- `KERNEL32!lstrcmpiW` at `0x180014ba6`
- `KERNEL32!lstrcmpiW` at `0x180014bb9`
- `KERNEL32!lstrcmpiW` at `0x180014c37`
- `KERNEL32!lstrcmpiW` at `0x180014ca8`
- `KERNEL32!lstrcmpiW` at `0x180014cd6`
- `KERNEL32!lstrcmpiW` at `0x180015193`

## string_xrefs

- `0x180014baf`: `ForceRemove`
- `0x180014c9e`: `NoRemove`
- `0x180014b9c`: `Delete`

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
  HKEY v18; // r14
  LSTATUS v19; // eax
  int v20; // eax
  WCHAR v21; // ax
  const WCHAR *v22; // rcx
  LSTATUS v23; // eax
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
  DWORD v34; // eax
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+68h] [rbp-98h]
  HKEY v37; // [rsp+70h] [rbp-90h]
  HKEY v38[3]; // [rsp+78h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  HKEY v40; // [rsp+98h] [rbp-68h]
  __int64 v41; // [rsp+A0h] [rbp-60h]
  __int64 v42; // [rsp+A8h] [rbp-58h]
  HKEY v43[3]; // [rsp+B0h] [rbp-50h] BYREF
  HKEY v44[3]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v45[4]; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t Destination[264]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR ValueName[4096]; // [rsp+310h] [rbp+210h] BYREF

  v5 = a4;
  v36 = a4;
  v6 = a3;
  v37 = a3;
  v9 = 0;
  memset(v38, 0, sizeof(v38));
  result = ATL::CRegParser::NextToken(this, a2);
  Token = result;
  if ( (int)result < 0 )
    return result;
  if ( *a2 == 125 )
  {
LABEL_126:
    if ( v9 )
      goto LABEL_127;
    return (unsigned int)Token;
  }
  while ( 1 )
  {
    v12 = lstrcmpiW(a2, L"Delete");
    if ( !lstrcmpiW(a2, L"ForceRemove") || !v12 )
    {
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_126;
      v13 = 0;
      if ( v5 )
      {
        memset(v43, 0, sizeof(v43));
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
            goto LABEL_113;
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
            v43[0] = v6;
            ATL::CRegKey::RecurseDeleteKey(v43, a2);
            v43[0] = 0;
            break;
          }
        }
        if ( !v12 )
        {
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            goto LABEL_126;
          Token = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
          if ( Token < 0 )
            goto LABEL_126;
          goto LABEL_63;
        }
      }
    }
    v16 = 1;
    if ( !lstrcmpiW(a2, L"NoRemove") )
    {
      v16 = 0;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_126;
    }
    if ( !lstrcmpiW(a2, L"Val") )
    {
      Token = ATL::CRegParser::NextToken(this, ValueName);
      if ( Token < 0 )
        goto LABEL_126;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_126;
      if ( *a2 != 61 )
      {
        if ( v9 )
        {
LABEL_114:
          RegCloseKey(v9);
          v38[0] = 0;
        }
        return 2147614729LL;
      }
      if ( v36 )
      {
        v44[1] = 0;
        v44[2] = 0;
        v44[0] = v6;
        v17 = ATL::CRegParser::AddValue(this, v44, ValueName, a2);
        Token = v17;
        v44[0] = 0;
LABEL_61:
        if ( v17 < 0 )
          goto LABEL_126;
        goto LABEL_62;
      }
      if ( !a5 && v16 )
      {
        v18 = 0;
        v40 = 0;
        v41 = 0;
        v42 = 0;
        hKey = 0;
        v19 = RegOpenKeyExW(v6, 0, 0, 0x20006u, &hKey);
        if ( !v19 )
          v18 = hKey;
        v40 = v18;
        if ( v19 || (v19 = RegDeleteValueW(v18, ValueName), (v19 & 0xFFFFFFFD) != 0) )
        {
          Token = ATL::AtlHresultFromWin32(v19);
          if ( v18 )
          {
            RegCloseKey(v18);
            v40 = 0;
          }
          goto LABEL_126;
        }
        if ( v18 )
        {
          RegCloseKey(v18);
          v40 = 0;
        }
      }
      v20 = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
      goto LABEL_37;
    }
    v21 = *a2;
    if ( *a2 )
    {
      v22 = a2;
      while ( v21 != 92 )
      {
        v22 = CharNextW(v22);
        v21 = *v22;
        if ( !*v22 )
          goto LABEL_45;
      }
      if ( v22 )
      {
LABEL_113:
        if ( v9 )
          goto LABEL_114;
        return 2147614729LL;
      }
    }
LABEL_45:
    if ( v36 )
      break;
    if ( a5 )
    {
      v27 = 2;
    }
    else
    {
      phkResult = 0;
      v27 = RegOpenKeyExW(v6, a2, 0, 0x20019u, &phkResult);
      if ( !v27 )
      {
        v27 = 0;
        if ( v9 )
        {
          v27 = RegCloseKey(v9);
          v38[0] = 0;
        }
        v9 = phkResult;
        v38[0] = phkResult;
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
      goto LABEL_126;
    Token = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
    if ( Token < 0 )
      goto LABEL_126;
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
          goto LABEL_126;
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_126;
      }
    }
    if ( v27 == 2 )
      goto LABEL_94;
    if ( v27 )
    {
      if ( !a5 )
      {
        Token = ATL::AtlHresultFromWin32(v27);
        goto LABEL_126;
      }
      goto LABEL_94;
    }
    if ( a5 )
    {
      LODWORD(hKey) = 0;
      if ( !RegQueryInfoKeyW(v9, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
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
                ATL::CRegKey::RecurseDeleteKey(v38, Destination);
                v9 = v38[0];
              }
              break;
            }
          }
LABEL_94:
          v6 = v37;
          goto LABEL_95;
        }
      }
    }
    LODWORD(hKey) = 0;
    v32 = 0;
    if ( !RegQueryInfoKeyW(v9, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      LOBYTE(v32) = (_DWORD)hKey != 0;
    if ( v9 )
    {
      v33 = RegCloseKey(v9);
      v9 = 0;
      v38[0] = 0;
      if ( v33 )
        return ATL::AtlHresultFromWin32(v33);
    }
    if ( !v16 || v32 )
      goto LABEL_94;
    v45[1] = 0;
    v45[2] = 0;
    v6 = v37;
    v45[0] = v37;
    v34 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v45, Destination);
    v45[0] = 0;
    if ( v34 )
    {
      Token = ATL::AtlHresultFromWin32(v34);
      goto LABEL_126;
    }
LABEL_95:
    if ( *a2 == 125 )
      goto LABEL_126;
    v5 = v36;
  }
  hKey = 0;
  if ( !RegOpenKeyExW(v6, a2, 0, 0x2001Fu, &hKey) )
  {
    v23 = 0;
    if ( v9 )
    {
      v23 = RegCloseKey(v9);
      v38[0] = 0;
    }
    v9 = hKey;
    v38[0] = hKey;
    if ( !v23 )
      goto LABEL_58;
  }
  hKey = 0;
  if ( !RegOpenKeyExW(v6, a2, 0, 0x20019u, &hKey) )
  {
    v24 = 0;
    if ( v9 )
    {
      v24 = RegCloseKey(v9);
      v38[0] = 0;
    }
    v9 = hKey;
    v38[0] = hKey;
    if ( !v24 )
      goto LABEL_58;
  }
  LODWORD(hKey) = 0;
  phkResult = 0;
  v25 = RegCreateKeyExW(v6, a2, 0, 0, 0, 0x2001Fu, 0, &phkResult, (LPDWORD)&hKey);
  if ( !v25 )
  {
    v25 = 0;
    if ( v9 )
    {
      v25 = RegCloseKey(v9);
      v38[0] = 0;
    }
    v9 = phkResult;
    v38[0] = phkResult;
    if ( !v25 )
    {
LABEL_58:
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_126;
      if ( *a2 == 61 )
      {
        v17 = ATL::CRegParser::AddValue(this, v38, 0, a2);
        Token = v17;
        v9 = v38[0];
        goto LABEL_61;
      }
LABEL_62:
      v5 = v36;
LABEL_63:
      if ( *a2 != 123 )
        goto LABEL_95;
      v26 = -1;
      do
        ++v26;
      while ( a2[v26] );
      if ( v26 != 1 )
        goto LABEL_95;
      Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, a2, v9, v5, 0);
      if ( Token < 0 )
        goto LABEL_126;
      v20 = ATL::CRegParser::NextToken(this, a2);
LABEL_37:
      Token = v20;
      if ( v20 < 0 )
        goto LABEL_126;
      goto LABEL_95;
    }
  }
  Token = ATL::AtlHresultFromWin32(v25);
  if ( !v9 )
    return (unsigned int)Token;
LABEL_127:
  RegCloseKey(v9);
  v38[0] = 0;
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x180014b28  push    rbp
0x180014b2a  push    rbx
0x180014b2b  push    rsi
0x180014b2c  push    rdi
0x180014b2d  push    r12
0x180014b2f  push    r13
0x180014b31  push    r14
0x180014b33  push    r15
0x180014b35  lea     rbp, [rsp-2228h]
0x180014b3d  mov     eax, 2328h
0x180014b42  call    _alloca_probe
0x180014b47  sub     rsp, rax
0x180014b4a  mov     rax, cs:__security_cookie
0x180014b51  xor     rax, rsp
0x180014b54  mov     [rbp+2260h+var_50], rax
0x180014b5b  mov     r12d, r9d
0x180014b5e  mov     [rsp+2360h+var_22F8], r9d
0x180014b63  mov     r15, r8
0x180014b66  mov     [rsp+2360h+var_22F0], r8
0x180014b6b  mov     rsi, rdx
0x180014b6e  mov     r13, rcx
0x180014b71  xor     eax, eax
0x180014b73  mov     ebx, eax
0x180014b75  mov     [rsp+2360h+var_22E8], rax
0x180014b7a  mov     [rbp+2260h+var_22E0], rax
0x180014b7e  mov     [rbp+2260h+var_22D8], rax
0x180014b82  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180014b87  mov     edi, eax
0x180014b89  test    eax, eax
0x180014b8b  jns     short loc_180014B92
0x180014b8d  jmp     loc_180015335
0x180014b92  cmp     word ptr [rsi], 7Dh ; '}'
0x180014b96  jz      loc_18001531C
0x180014b9c  lea     rdx, String2; "Delete"
0x180014ba3  mov     rcx, rsi; lpString1
0x180014ba6  call    cs:__imp_lstrcmpiW
0x180014bac  mov     r14d, eax
0x180014baf  lea     rdx, aForceremove; "ForceRemove"
0x180014bb6  mov     rcx, rsi; lpString1
0x180014bb9  call    cs:__imp_lstrcmpiW
0x180014bbf  xor     edi, edi
0x180014bc1  test    eax, eax
0x180014bc3  jz      short loc_180014BCE
0x180014bc5  test    r14d, r14d
0x180014bc8  jnz     loc_180014C98
0x180014bce  mov     rdx, rsi; unsigned __int16 *
0x180014bd1  mov     rcx, r13; this
0x180014bd4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180014bd9  mov     edi, eax
0x180014bdb  test    eax, eax
0x180014bdd  js      loc_18001531C
0x180014be3  xor     edi, edi
0x180014be5  test    r12d, r12d
0x180014be8  jz      loc_180014C98
0x180014bee  mov     [rbp+2260h+var_22B0], rdi
0x180014bf2  mov     [rbp+2260h+var_22A8], rdi
0x180014bf6  mov     [rbp+2260h+var_22A0], rdi
0x180014bfa  movzx   eax, word ptr [rsi]
0x180014bfd  test    ax, ax
0x180014c00  jz      short loc_180014C27
0x180014c02  mov     rcx, rsi; lpsz
0x180014c05  cmp     ax, 5Ch ; '\'
0x180014c09  jz      short loc_180014C1E
0x180014c0b  call    cs:__imp_CharNextW
0x180014c11  mov     rcx, rax
0x180014c14  movzx   eax, word ptr [rax]
0x180014c17  test    ax, ax
0x180014c1a  jnz     short loc_180014C05
0x180014c1c  jmp     short loc_180014C27
0x180014c1e  test    rcx, rcx
0x180014c21  jnz     loc_180015284
0x180014c27  mov     edx, edi
0x180014c29  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180014c30  mov     rdx, [rax+rdx*8]; lpString2
0x180014c34  mov     rcx, rsi; lpString1
0x180014c37  call    cs:__imp_lstrcmpiW
0x180014c3d  test    eax, eax
0x180014c3f  jz      short loc_180014C60
0x180014c41  inc     edi
0x180014c43  cmp     edi, 0Ch
0x180014c46  jl      short loc_180014C27
0x180014c48  mov     [rbp+2260h+var_22B0], r15
0x180014c4c  mov     rdx, rsi; unsigned __int16 *
0x180014c4f  lea     rcx, [rbp+2260h+var_22B0]; this
0x180014c53  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180014c58  xor     edi, edi
0x180014c5a  mov     [rbp+2260h+var_22B0], rdi
0x180014c5e  jmp     short loc_180014C62
0x180014c60  xor     edi, edi
0x180014c62  test    r14d, r14d
0x180014c65  jnz     short loc_180014C98
0x180014c67  mov     rdx, rsi; unsigned __int16 *
0x180014c6a  mov     rcx, r13; this
0x180014c6d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180014c72  mov     edi, eax
0x180014c74  test    eax, eax
0x180014c76  js      loc_1800152A1
0x180014c7c  mov     rdx, rsi; unsigned __int16 *
0x180014c7f  mov     rcx, r13; this
0x180014c82  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180014c87  mov     edi, eax
0x180014c89  xor     edx, edx
0x180014c8b  test    eax, eax
0x180014c8d  js      loc_18001531C
0x180014c93  jmp     loc_180014F74
0x180014c98  mov     r12d, 1
0x180014c9e  lea     rdx, aNoremove; "NoRemove"
0x180014ca5  mov     rcx, rsi; lpString1
0x180014ca8  call    cs:__imp_lstrcmpiW
0x180014cae  test    eax, eax
0x180014cb0  jnz     short loc_180014CCC
0x180014cb2  mov     r12d, edi
0x180014cb5  mov     rdx, rsi; unsigned __int16 *
0x180014cb8  mov     rcx, r13; this
0x180014cbb  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180014cc0  mov     edi, eax
0x180014cc2  test    eax, eax
0x180014cc4  js      loc_18001531C
0x180014cca  xor     edi, edi
0x180014ccc  lea     rdx, aVal; "Val"
0x180014cd3  mov     rcx, rsi; lpString1
0x180014cd6  call    cs:__imp_lstrcmpiW
0x180014cdc  test    eax, eax
0x180014cde  jnz     loc_180014DF1
0x180014ce4  lea     rdx, [rbp+2260h+ValueName]; unsigned __int16 *
0x180014ceb  mov     rcx, r13; this
0x180014cee  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180014cf3  mov     edi, eax
0x180014cf5  test    eax, eax
0x180014cf7  js      loc_18001531C
0x180014cfd  mov     rdx, rsi; unsigned __int16 *
0x180014d00  mov     rcx, r13; this
0x180014d03  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180014d08  mov     edi, eax
0x180014d0a  xor     edx, edx
0x180014d0c  test    eax, eax
0x180014d0e  js      loc_18001531C
0x180014d14  cmp     word ptr [rsi], 3Dh ; '='
0x180014d18  jnz     loc_1800152C2
0x180014d1e  cmp     [rsp+2360h+var_22F8], edx
0x180014d22  jz      short loc_180014D57
0x180014d24  mov     [rbp+2260h+var_2298], rdx
0x180014d28  mov     [rbp+2260h+var_2290], rdx
0x180014d2c  mov     [rbp+2260h+var_2288], rdx
0x180014d30  mov     [rbp+2260h+var_2298], r15
0x180014d34  mov     r9, rsi; unsigned __int16 *
0x180014d37  lea     r8, [rbp+2260h+ValueName]; unsigned __int16 *
0x180014d3e  lea     rdx, [rbp+2260h+var_2298]; struct ATL::CRegKey *
0x180014d42  mov     rcx, r13; this
0x180014d45  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180014d4a  mov     edi, eax
0x180014d4c  xor     edx, edx
0x180014d4e  mov     [rbp+2260h+var_2298], rdx
0x180014d52  jmp     loc_180014F67
0x180014d57  cmp     [rbp+2260h+arg_20], edx
0x180014d5d  jnz     short loc_180014DD7
0x180014d5f  test    r12d, r12d
0x180014d62  jz      short loc_180014DD7
0x180014d64  mov     r14, rdx
0x180014d67  mov     [rbp+2260h+var_22C8], rdx
0x180014d6b  mov     [rbp+2260h+var_22C0], rdx
0x180014d6f  mov     [rbp+2260h+var_22B8], rdx
0x180014d73  mov     [rsp+2360h+hKey], rdx
0x180014d78  lea     rax, [rsp+2360h+hKey]
0x180014d7d  mov     [rsp+2360h+phkResult], rax; phkResult
0x180014d82  mov     r9d, 20006h; samDesired
0x180014d88  xor     r8d, r8d; ulOptions
0x180014d8b  xor     edx, edx; lpSubKey
0x180014d8d  mov     rcx, r15; hKey
0x180014d90  call    cs:__imp_RegOpenKeyExW
0x180014d96  test    eax, eax
0x180014d98  cmovz   r14, [rsp+2360h+hKey]
0x180014d9e  mov     [rbp+2260h+var_22C8], r14
0x180014da2  jnz     loc_1800152A3
0x180014da8  lea     rdx, [rbp+2260h+ValueName]; lpValueName
0x180014daf  mov     rcx, r14; hKey
0x180014db2  call    cs:__imp_RegDeleteValueW
0x180014db8  test    eax, 0FFFFFFFDh
0x180014dbd  jnz     loc_1800152A3
0x180014dc3  xor     edi, edi
0x180014dc5  test    r14, r14
0x180014dc8  jz      short loc_180014DD7
0x180014dca  mov     rcx, r14; hKey
0x180014dcd  call    cs:__imp_RegCloseKey
0x180014dd3  mov     [rbp+2260h+var_22C8], rdi
0x180014dd7  mov     rdx, rsi; unsigned __int16 *
0x180014dda  mov     rcx, r13; this
0x180014ddd  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180014de2  mov     edi, eax
0x180014de4  test    eax, eax
0x180014de6  js      loc_18001531C
0x180014dec  jmp     loc_180015110
0x180014df1  movzx   eax, word ptr [rsi]
0x180014df4  test    ax, ax
0x180014df7  jz      short loc_180014E1E
0x180014df9  mov     rcx, rsi; lpsz
0x180014dfc  cmp     ax, 5Ch ; '\'
0x180014e00  jz      short loc_180014E15
0x180014e02  call    cs:__imp_CharNextW
0x180014e08  mov     rcx, rax
0x180014e0b  movzx   eax, word ptr [rax]
0x180014e0e  test    ax, ax
0x180014e11  jnz     short loc_180014DFC
0x180014e13  jmp     short loc_180014E1E
0x180014e15  test    rcx, rcx
0x180014e18  jnz     loc_180015284
0x180014e1e  cmp     [rsp+2360h+var_22F8], edi
0x180014e22  jz      loc_180014FC4
0x180014e28  mov     [rsp+2360h+hKey], rdi
0x180014e2d  lea     rax, [rsp+2360h+hKey]
0x180014e32  mov     [rsp+2360h+phkResult], rax; phkResult
0x180014e37  mov     r14d, 2001Fh
0x180014e3d  mov     r9d, r14d; samDesired
0x180014e40  xor     r8d, r8d; ulOptions
0x180014e43  mov     rdx, rsi; lpSubKey
0x180014e46  mov     rcx, r15; hKey
0x180014e49  call    cs:__imp_RegOpenKeyExW
0x180014e4f  test    eax, eax
0x180014e51  jnz     short loc_180014E7A
0x180014e53  mov     eax, edi
0x180014e55  test    rbx, rbx
0x180014e58  jz      short loc_180014E68
0x180014e5a  mov     rcx, rbx; hKey
0x180014e5d  call    cs:__imp_RegCloseKey
0x180014e63  mov     [rsp+2360h+var_22E8], rdi
0x180014e68  mov     rbx, [rsp+2360h+hKey]
0x180014e6d  mov     [rsp+2360h+var_22E8], rbx
0x180014e72  test    eax, eax
0x180014e74  jz      loc_180014F2E
0x180014e7a  mov     [rsp+2360h+hKey], rdi
0x180014e7f  lea     rax, [rsp+2360h+hKey]
0x180014e84  mov     [rsp+2360h+phkResult], rax; phkResult
0x180014e89  mov     r9d, 20019h; samDesired
0x180014e8f  xor     r8d, r8d; ulOptions
0x180014e92  mov     rdx, rsi; lpSubKey
0x180014e95  mov     rcx, r15; hKey
0x180014e98  call    cs:__imp_RegOpenKeyExW
0x180014e9e  test    eax, eax
0x180014ea0  jnz     short loc_180014EC5
0x180014ea2  mov     eax, edi
0x180014ea4  test    rbx, rbx
0x180014ea7  jz      short loc_180014EB7
0x180014ea9  mov     rcx, rbx; hKey
0x180014eac  call    cs:__imp_RegCloseKey
0x180014eb2  mov     [rsp+2360h+var_22E8], rdi
0x180014eb7  mov     rbx, [rsp+2360h+hKey]
0x180014ebc  mov     [rsp+2360h+var_22E8], rbx
0x180014ec1  test    eax, eax
0x180014ec3  jz      short loc_180014F2E
0x180014ec5  mov     dword ptr [rsp+2360h+hKey], edi
0x180014ec9  mov     [rbp+2260h+var_22D0], rdi
0x180014ecd  lea     rax, [rsp+2360h+hKey]
0x180014ed2  mov     [rsp+2360h+lpdwDisposition], rax; lpdwDisposition
0x180014ed7  lea     rax, [rbp+2260h+var_22D0]
0x180014edb  mov     [rsp+2360h+var_2328], rax; phkResult
0x180014ee0  mov     [rsp+2360h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180014ee5  mov     [rsp+2360h+samDesired], r14d; samDesired
0x180014eea  mov     dword ptr [rsp+2360h+phkResult], edi; dwOptions
0x180014eee  xor     r9d, r9d; lpClass
0x180014ef1  xor     r8d, r8d; Reserved
0x180014ef4  mov     rdx, rsi; lpSubKey
0x180014ef7  mov     rcx, r15; hKey
0x180014efa  call    cs:__imp_RegCreateKeyExW
0x180014f00  test    eax, eax
0x180014f02  jnz     loc_1800152DB
0x180014f08  mov     eax, edi
0x180014f0a  test    rbx, rbx
0x180014f0d  jz      short loc_180014F1D
0x180014f0f  mov     rcx, rbx; hKey
0x180014f12  call    cs:__imp_RegCloseKey
0x180014f18  mov     [rsp+2360h+var_22E8], rdi
0x180014f1d  mov     rbx, [rbp+2260h+var_22D0]
0x180014f21  mov     [rsp+2360h+var_22E8], rbx
0x180014f26  test    eax, eax
0x180014f28  jnz     loc_1800152DB
0x180014f2e  mov     rdx, rsi; unsigned __int16 *
0x180014f31  mov     rcx, r13; this
0x180014f34  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180014f39  mov     edi, eax
0x180014f3b  xor     edx, edx
0x180014f3d  test    eax, eax
0x180014f3f  js      loc_18001531C
0x180014f45  cmp     word ptr [rsi], 3Dh ; '='
0x180014f49  jnz     short loc_180014F6F
0x180014f4b  mov     r9, rsi; unsigned __int16 *
0x180014f4e  xor     r8d, r8d; unsigned __int16 *
0x180014f51  lea     rdx, [rsp+2360h+var_22E8]; struct ATL::CRegKey *
0x180014f56  mov     rcx, r13; this
0x180014f59  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180014f5e  mov     edi, eax
0x180014f60  xor     edx, edx
0x180014f62  mov     rbx, [rsp+2360h+var_22E8]
0x180014f67  test    eax, eax
0x180014f69  js      loc_18001531C
0x180014f6f  mov     r12d, [rsp+2360h+var_22F8]
0x180014f74  cmp     word ptr [rsi], 7Bh ; '{'
0x180014f78  jnz     loc_180015110
0x180014f7e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014f82  inc     rax
0x180014f85  cmp     [rsi+rax*2], dx
  ... truncated ...
```
