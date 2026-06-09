# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x1800038f0`
- end: `0x18000425d`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `2413`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x1800034f0`
- `0x1800038f0`

## callees

- `0x180001470`
- `0x180002164`
- `0x180002cf8`
- `0x180002f30`
- `0x180003398`
- `0x1800038f0`
- `0x180004380`
- `0x180004730`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003ef8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003f03`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004123`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000413b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000418c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800041b3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800041d7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800041fb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004215`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000422d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003ef8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003f03`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004123`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000413b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000418c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800041b3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800041d7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800041fb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004215`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000422d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003dbd`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003eb0`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003dbd`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003eb0`
- `KERNEL32!lstrcpynW` at `0x180003df8`
- `KERNEL32!lstrcpynW` at `0x180003df8`
- `KERNEL32!lstrcmpiW` at `0x18000397e`
- `KERNEL32!lstrcmpiW` at `0x180003991`
- `KERNEL32!lstrcmpiW` at `0x180003a10`
- `KERNEL32!lstrcmpiW` at `0x180003a6d`
- `KERNEL32!lstrcmpiW` at `0x180003a9b`
- `KERNEL32!lstrcmpiW` at `0x180003ced`
- `KERNEL32!lstrcmpiW` at `0x180004007`
- `KERNEL32!lstrcmpiW` at `0x18000397e`
- `KERNEL32!lstrcmpiW` at `0x180003991`
- `KERNEL32!lstrcmpiW` at `0x180003a10`
- `KERNEL32!lstrcmpiW` at `0x180003a6d`
- `KERNEL32!lstrcmpiW` at `0x180003a9b`
- `KERNEL32!lstrcmpiW` at `0x180003ced`
- `KERNEL32!lstrcmpiW` at `0x180004007`
- `USER32!CharNextW` at `0x1800039e4`
- `USER32!CharNextW` at `0x180003bb4`
- `USER32!CharNextW` at `0x1800039e4`
- `USER32!CharNextW` at `0x180003bb4`
- `ADVAPI32!RegCloseKey` at `0x180003b26`
- `ADVAPI32!RegCloseKey` at `0x180003b8c`
- `ADVAPI32!RegCloseKey` at `0x180003c11`
- `ADVAPI32!RegCloseKey` at `0x180003c58`
- `ADVAPI32!RegCloseKey` at `0x180003cbb`
- `ADVAPI32!RegCloseKey` at `0x180003d74`
- `ADVAPI32!RegCloseKey` at `0x180004044`
- `ADVAPI32!RegCloseKey` at `0x180004100`
- `ADVAPI32!RegCloseKey` at `0x180004114`
- `ADVAPI32!RegCloseKey` at `0x180004160`
- `ADVAPI32!RegCloseKey` at `0x18000417d`
- `ADVAPI32!RegCloseKey` at `0x1800041a4`
- `ADVAPI32!RegCloseKey` at `0x1800041c8`
- `ADVAPI32!RegCloseKey` at `0x1800041ec`
- `ADVAPI32!RegCloseKey` at `0x180003b26`
- `ADVAPI32!RegCloseKey` at `0x180003b8c`
- `ADVAPI32!RegCloseKey` at `0x180003c11`
- `ADVAPI32!RegCloseKey` at `0x180003c58`
- `ADVAPI32!RegCloseKey` at `0x180003cbb`
- `ADVAPI32!RegCloseKey` at `0x180003d74`
- `ADVAPI32!RegCloseKey` at `0x180004044`
- `ADVAPI32!RegCloseKey` at `0x180004100`
- `ADVAPI32!RegCloseKey` at `0x180004114`
- `ADVAPI32!RegCloseKey` at `0x180004160`
- `ADVAPI32!RegCloseKey` at `0x18000417d`
- `ADVAPI32!RegCloseKey` at `0x1800041a4`
- `ADVAPI32!RegCloseKey` at `0x1800041c8`
- `ADVAPI32!RegCloseKey` at `0x1800041ec`
- `ADVAPI32!RegOpenKeyExW` at `0x180003b53`
- `ADVAPI32!RegOpenKeyExW` at `0x180003bf9`
- `ADVAPI32!RegOpenKeyExW` at `0x180003c43`
- `ADVAPI32!RegOpenKeyExW` at `0x180003d60`
- `ADVAPI32!RegOpenKeyExW` at `0x180003b53`
- `ADVAPI32!RegOpenKeyExW` at `0x180003bf9`
- `ADVAPI32!RegOpenKeyExW` at `0x180003c43`
- `ADVAPI32!RegOpenKeyExW` at `0x180003d60`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003e41`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003e8e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003fe6`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003e41`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003e8e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003fe6`
- `ADVAPI32!RegEnumValueW` at `0x180003ee4`
- `ADVAPI32!RegEnumValueW` at `0x180003ee4`
- `ADVAPI32!RegCreateKeyExW` at `0x180003ca2`
- `ADVAPI32!RegCreateKeyExW` at `0x180003ca2`
- `ADVAPI32!RegDeleteValueW` at `0x180003b71`
- `ADVAPI32!RegDeleteValueW` at `0x180003b71`

## string_xrefs

- `0x180003987`: `ForceRemove`
- `0x180003a63`: `NoRemove`
- `0x180003974`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(LPCWSTR *this, unsigned __int16 *a2, HKEY a3, int a4, int a5)
{
  _QWORD *v7; // rbx
  HKEY v8; // rsi
  __int64 result; // rax
  int Token; // edi
  int v11; // r13d
  int v12; // r15d
  int v13; // edi
  WCHAR v14; // ax
  const WCHAR *v15; // rcx
  int v16; // eax
  LSTATUS v17; // eax
  HKEY v18; // r15
  LSTATUS v19; // eax
  int v20; // eax
  WCHAR v21; // ax
  const WCHAR *v22; // rcx
  HKEY v23; // rdi
  bool v24; // r15
  LSTATUS v25; // eax
  LSTATUS v26; // eax
  LSTATUS v27; // eax
  LSTATUS v28; // eax
  WCHAR *v29; // r15
  void *v30; // rsp
  _QWORD *v31; // rax
  _WORD *v32; // rdi
  __int64 v33; // rdi
  LSTATUS v34; // eax
  __int64 v35; // rax
  void *v36; // rcx
  void *v37; // rcx
  void *v38; // rcx
  void *v39; // rcx
  void *v40; // rcx
  void *v41; // rcx
  void *v42; // rcx
  void *v43; // rcx
  char v44; // [rsp+40h] [rbp-210h] BYREF
  DWORD dwDisposition; // [rsp+250h] [rbp+0h] BYREF
  HKEY phkResult; // [rsp+258h] [rbp+8h] BYREF
  int v47; // [rsp+260h] [rbp+10h]
  HKEY hKey; // [rsp+268h] [rbp+18h]
  int v49; // [rsp+270h] [rbp+20h]
  LPWSTR lpString1; // [rsp+278h] [rbp+28h]
  HKEY v51; // [rsp+280h] [rbp+30h] BYREF
  __int64 v52; // [rsp+288h] [rbp+38h]
  __int64 v53; // [rsp+290h] [rbp+40h]
  int v54; // [rsp+298h] [rbp+48h]
  HKEY v55[3]; // [rsp+2A0h] [rbp+50h] BYREF
  _QWORD *v56; // [rsp+2B8h] [rbp+68h]
  __int64 v57; // [rsp+2C0h] [rbp+70h]
  WCHAR ValueName[264]; // [rsp+2D0h] [rbp+80h] BYREF

  v57 = -2;
  v47 = a4;
  hKey = a3;
  v7 = 0;
  v56 = 0;
  v8 = 0;
  memset(v55, 0, sizeof(v55));
  result = ATL::CRegParser::NextToken(this, a2);
  Token = result;
  if ( (int)result < 0 )
    return result;
  lpString1 = 0;
  v49 = 1;
  v11 = a5;
  v54 = a5;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( *a2 == 125 )
        goto LABEL_117;
      v12 = lstrcmpiW(a2, L"Delete");
      if ( !lstrcmpiW(a2, L"ForceRemove") || !v12 )
      {
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_117;
        v13 = 0;
        if ( v47 )
        {
          v51 = 0;
          v52 = 0;
          v53 = 0;
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
              if ( v8 )
                RegCloseKey(v8);
              while ( v7 )
              {
                v36 = v7;
                v7 = (_QWORD *)*v7;
                free(v36);
              }
              return 2147614729LL;
            }
            v15 = CharNextW(v15);
            v14 = *v15;
          }
          while ( *v15 );
LABEL_13:
          while ( lstrcmpiW(a2, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v13]) )
          {
            if ( ++v13 >= 2 )
            {
              v51 = hKey;
              ATL::CRegKey::RecurseDeleteKey(&v51, a2);
              break;
            }
          }
          if ( !v12 )
          {
            Token = ATL::CRegParser::NextToken(this, a2);
            if ( Token < 0 )
              goto LABEL_117;
            v16 = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
            Token = v16;
            goto LABEL_107;
          }
        }
      }
      if ( !lstrcmpiW(a2, L"NoRemove") )
      {
        v49 = 0;
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_117;
      }
      if ( lstrcmpiW(a2, L"Val") )
        break;
      Token = ATL::CRegParser::NextToken(this, ValueName);
      if ( Token < 0 )
        goto LABEL_117;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_117;
      if ( *a2 != 61 )
      {
        if ( v8 )
          RegCloseKey(v8);
        while ( v7 )
        {
          v38 = v7;
          v7 = (_QWORD *)*v7;
          free(v38);
        }
        return 2147614729LL;
      }
      if ( v47 )
      {
        v52 = 0;
        v53 = 0;
        v51 = hKey;
        Token = ATL::CRegParser::AddValue((ATL::CRegParser *)this, &v51, ValueName, a2, 0);
        if ( Token < 0 )
        {
          if ( v8 )
            RegCloseKey(v8);
          while ( v7 )
          {
            v37 = v7;
            v7 = (_QWORD *)*v7;
            free(v37);
          }
          return (unsigned int)Token;
        }
LABEL_108:
        if ( v47 )
        {
          if ( *a2 == 123 )
          {
            v35 = -1;
            do
              ++v35;
            while ( a2[v35] );
            if ( v35 == 1 )
            {
              Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, a2, v8, v47, 0);
              if ( Token < 0 )
                goto LABEL_117;
              goto LABEL_114;
            }
          }
        }
      }
      else
      {
        if ( !v11 )
        {
          phkResult = 0;
          v17 = RegOpenKeyExW(hKey, 0, 0, 0x20006u, &phkResult);
          Token = v17;
          if ( v17 )
          {
            if ( v17 > 0 )
              Token = (unsigned __int16)v17 | 0x80070000;
          }
          else
          {
            v18 = phkResult;
            v19 = RegDeleteValueW(phkResult, ValueName);
            Token = v19;
            if ( (v19 & 0xFFFFFFFD) == 0 )
            {
              if ( v18 )
                RegCloseKey(v18);
              goto LABEL_35;
            }
            if ( v19 > 0 )
              Token = (unsigned __int16)v19 | 0x80070000;
            if ( v18 )
              RegCloseKey(v18);
          }
LABEL_117:
          if ( v8 )
            RegCloseKey(v8);
          while ( v7 )
          {
            v43 = v7;
            v7 = (_QWORD *)*v7;
            free(v43);
          }
          return (unsigned int)Token;
        }
LABEL_35:
        v20 = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
LABEL_115:
        Token = v20;
        if ( v20 < 0 )
          goto LABEL_117;
      }
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
          goto LABEL_42;
      }
      if ( v22 )
      {
        if ( v8 )
          RegCloseKey(v8);
        while ( v7 )
        {
          v39 = v7;
          v7 = (_QWORD *)*v7;
          free(v39);
        }
        return 2147614729LL;
      }
    }
LABEL_42:
    if ( v47 )
    {
      phkResult = 0;
      v23 = hKey;
      v24 = 0;
      if ( RegOpenKeyExW(hKey, a2, 0, 0xF003Fu, &phkResult) )
        goto LABEL_169;
      v25 = 0;
      if ( v8 )
        v25 = RegCloseKey(v8);
      v8 = phkResult;
      v55[0] = phkResult;
      if ( v25 )
      {
LABEL_169:
        phkResult = 0;
        if ( RegOpenKeyExW(v23, a2, 0, 0x20019u, &phkResult) )
          goto LABEL_170;
        v26 = 0;
        if ( v8 )
          v26 = RegCloseKey(v8);
        v8 = phkResult;
        v55[0] = phkResult;
        if ( v26 )
        {
LABEL_170:
          dwDisposition = 0;
          phkResult = 0;
          if ( RegCreateKeyExW(v23, a2, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition) )
            goto LABEL_148;
          v27 = 0;
          if ( v8 )
            v27 = RegCloseKey(v8);
          v8 = phkResult;
          v55[0] = phkResult;
          if ( v27 )
          {
LABEL_148:
            if ( v8 )
              RegCloseKey(v8);
            while ( v7 )
            {
              v40 = v7;
              v7 = (_QWORD *)*v7;
              free(v40);
            }
            return 2147614729LL;
          }
        }
      }
      if ( ((*a2 - 76) & 0xFFDF) == 0 )
        v24 = lstrcmpiW(a2, L"LocalServer32") == 0;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_117;
      if ( *a2 != 61 )
        goto LABEL_108;
      v16 = ATL::CRegParser::AddValue((ATL::CRegParser *)this, v55, 0, a2, v24);
      goto LABEL_106;
    }
    if ( !v11 )
    {
      phkResult = 0;
      if ( RegOpenKeyExW(hKey, a2, 0, 0x20019u, &phkResult) )
        goto LABEL_65;
      v28 = 0;
      if ( v8 )
        v28 = RegCloseKey(v8);
      v8 = phkResult;
      v55[0] = phkResult;
      if ( v28 )
LABEL_65:
        v11 = 1;
    }
    v29 = lpString1;
    if ( !lpString1 )
      break;
LABEL_74:
    lstrcpynW(v29, a2, 260);
    if ( !v11 )
    {
      dwDisposition = 0;
      if ( RegQueryInfoKeyW(v8, 0, 0, 0, &dwDisposition, 0, 0, 0, 0, 0, 0, 0) < 0 || !dwDisposition )
      {
        dwDisposition = 0;
        if ( RegQueryInfoKeyW(v8, 0, 0, 0, 0, 0, 0, &dwDisposition, 0, 0, 0, 0) )
          goto LABEL_100;
        if ( dwDisposition == 1 )
        {
          LODWORD(phkResult) = 4096;
          v32 = malloc(0x2000u);
          if ( !v32 )
            goto LABEL_100;
          if ( RegEnumValueW(v8, 0, v32, (LPDWORD)&phkResult, 0, 0, 0, 0) || !*v32 )
          {
            free(v32);
            goto LABEL_100;
          }
          free(v32);
        }
        else if ( !dwDisposition )
        {
          goto LABEL_100;
        }
      }
    }
    Token = ATL::CRegParser::NextToken(this, a2);
    if ( Token < 0 )
      goto LABEL_117;
    Token = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
    if ( Token < 0 )
      goto LABEL_117;
    if ( *a2 == 123 )
    {
      Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, a2, v8, 0, v11);
      if ( Token < 0 )
        goto LABEL_117;
      if ( !v11 )
      {
LABEL_94:
        dwDisposition = 0;
        if ( RegQueryInfoKeyW(v8, 0, 0, 0, &dwDisposition, 0, 0, 0, 0, 0, 0, 0) >= 0 && dwDisposition )
        {
          v33 = 0;
          while ( lstrcmpiW(v29, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v33]) )
          {
            v33 = (unsigned int)(v33 + 1);
            if ( (int)v33 >= 2 )
            {
              ATL::CRegKey::RecurseDeleteKey(v55, v29);
              v8 = v55[0];
              break;
            }
          }
LABEL_114:
          v20 = ATL::CRegParser::NextToken(this, a2);
          goto LABEL_115;
        }
LABEL_100:
        if ( v8 )
        {
          v34 = RegCloseKey(v8);
          v8 = 0;
          v55[0] = 0;
          if ( v34 )
          {
            while ( v7 )
            {
              v42 = v7;
              v7 = (_QWORD *)*v7;
              free(v42);
            }
            return 2147614729LL;
          }
        }
        if ( v49 )
        {
          v52 = 0;
          v53 = 0;
          v51 = hKey;
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v51, v29);
        }
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_117;
        v16 = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
LABEL_106:
        Token = v16;
LABEL_107:
        if ( v16 < 0 )
          goto LABEL_117;
        goto LABEL_108;
      }
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_117;
      Token = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
      if ( Token < 0 )
        goto LABEL_117;
      v11 = v54;
    }
    else if ( !v11 )
    {
      goto LABEL_94;
    }
  }
  if ( ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)0x208) )
  {
    v30 = alloca(528);
    v29 = (WCHAR *)&v44;
  }
  else
  {
    v31 = malloc(0x218u);
    if ( !v31 )
    {
      v29 = 0;
      lpString1 = 0;
      goto LABEL_73;
    }
    *v31 = v7;
    v7 = v31;
    v56 = v31;
    v29 = (WCHAR *)(v31 + 2);
  }
  lpString1 = v29;
LABEL_73:
  if ( v29 )
    goto LABEL_74;
  if ( v8 )
    RegCloseKey(v8);
  while ( v7 )
  {
    v41 = v7;
    v7 = (_QWORD *)*v7;
    free(v41);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800038f0  push    rbp
0x1800038f2  push    rbx
0x1800038f3  push    rsi
0x1800038f4  push    rdi
0x1800038f5  push    r12
0x1800038f7  push    r13
0x1800038f9  push    r14
0x1800038fb  push    r15
0x1800038fd  sub     rsp, 308h
0x180003904  lea     rbp, [rsp+60h]
0x180003909  mov     [rbp+2E0h+var_270], 0FFFFFFFFFFFFFFFEh
0x180003911  mov     rax, cs:__security_cookie
0x180003918  xor     rax, rbp
0x18000391b  mov     [rbp+2E0h+var_50], rax
0x180003922  mov     [rbp+2E0h+var_2D0], r9d
0x180003926  mov     [rbp+2E0h+hKey], r8
0x18000392a  mov     r14, rdx
0x18000392d  mov     r12, rcx
0x180003930  xor     r13d, r13d
0x180003933  mov     ebx, r13d
0x180003936  mov     [rbp+2E0h+var_278], rbx
0x18000393a  mov     esi, r13d
0x18000393d  mov     [rbp+2E0h+var_290], r13
0x180003941  mov     [rbp+2E0h+var_288], r13
0x180003945  mov     [rbp+2E0h+var_280], r13
0x180003949  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000394e  mov     edi, eax
0x180003950  test    eax, eax
0x180003952  jns     short loc_180003959
0x180003954  jmp     loc_18000423A
0x180003959  mov     [rbp+2E0h+lpString1], r13
0x18000395d  mov     [rbp+2E0h+var_2C0], 1
0x180003964  mov     r13d, [rbp+2E0h+arg_20]
0x18000396b  mov     [rbp+2E0h+var_298], r13d
0x18000396f  jmp     loc_1800040ED
0x180003974  lea     rdx, aDelete; "Delete"
0x18000397b  mov     rcx, r14; lpString1
0x18000397e  call    cs:__imp_lstrcmpiW
0x180003984  mov     r15d, eax
0x180003987  lea     rdx, aForceremove; "ForceRemove"
0x18000398e  mov     rcx, r14; lpString1
0x180003991  call    cs:__imp_lstrcmpiW
0x180003997  xor     edi, edi
0x180003999  test    eax, eax
0x18000399b  jz      short loc_1800039A6
0x18000399d  test    r15d, r15d
0x1800039a0  jnz     loc_180003A63
0x1800039a6  mov     rdx, r14; unsigned __int16 *
0x1800039a9  mov     rcx, r12; this
0x1800039ac  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800039b1  mov     edi, eax
0x1800039b3  test    eax, eax
0x1800039b5  js      loc_1800040F8
0x1800039bb  xor     edi, edi
0x1800039bd  cmp     [rbp+2E0h+var_2D0], edi
0x1800039c0  jz      loc_180003A63
0x1800039c6  mov     [rbp+2E0h+var_2B0], rdi
0x1800039ca  mov     [rbp+2E0h+var_2A8], rdi
0x1800039ce  mov     [rbp+2E0h+var_2A0], rdi
0x1800039d2  movzx   eax, word ptr [r14]
0x1800039d6  test    ax, ax
0x1800039d9  jz      short loc_180003A00
0x1800039db  mov     rcx, r14; lpsz
0x1800039de  cmp     ax, 5Ch ; '\'
0x1800039e2  jz      short loc_1800039F7
0x1800039e4  call    cs:__imp_CharNextW
0x1800039ea  mov     rcx, rax
0x1800039ed  movzx   eax, word ptr [rax]
0x1800039f0  test    ax, ax
0x1800039f3  jnz     short loc_1800039DE
0x1800039f5  jmp     short loc_180003A00
0x1800039f7  test    rcx, rcx
0x1800039fa  jnz     loc_18000410C
0x180003a00  mov     edx, edi
0x180003a02  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1PAPEBGA; ushort const * near * ATL::CRegParser::rgszNeverDelete
0x180003a09  mov     rdx, [rax+rdx*8]; lpString2
0x180003a0d  mov     rcx, r14; lpString1
0x180003a10  call    cs:__imp_lstrcmpiW
0x180003a16  test    eax, eax
0x180003a18  jz      short loc_180003A35
0x180003a1a  inc     edi
0x180003a1c  cmp     edi, 2
0x180003a1f  jl      short loc_180003A00
0x180003a21  mov     rax, [rbp+2E0h+hKey]
0x180003a25  mov     [rbp+2E0h+var_2B0], rax
0x180003a29  mov     rdx, r14; unsigned __int16 *
0x180003a2c  lea     rcx, [rbp+2E0h+var_2B0]; this
0x180003a30  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180003a35  xor     edi, edi
0x180003a37  test    r15d, r15d
0x180003a3a  jnz     short loc_180003A63
0x180003a3c  mov     rdx, r14; unsigned __int16 *
0x180003a3f  mov     rcx, r12; this
0x180003a42  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003a47  mov     edi, eax
0x180003a49  test    eax, eax
0x180003a4b  js      loc_180004133
0x180003a51  mov     rdx, r14; unsigned __int16 *
0x180003a54  mov     rcx, r12; this
0x180003a57  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180003a5c  mov     edi, eax
0x180003a5e  jmp     loc_180004099
0x180003a63  lea     rdx, aNoremove; "NoRemove"
0x180003a6a  mov     rcx, r14; lpString1
0x180003a6d  call    cs:__imp_lstrcmpiW
0x180003a73  test    eax, eax
0x180003a75  jnz     short loc_180003A91
0x180003a77  mov     [rbp+2E0h+var_2C0], edi
0x180003a7a  mov     rdx, r14; unsigned __int16 *
0x180003a7d  mov     rcx, r12; this
0x180003a80  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003a85  mov     edi, eax
0x180003a87  test    eax, eax
0x180003a89  js      loc_1800040F8
0x180003a8f  xor     edi, edi
0x180003a91  lea     rdx, aVal; "Val"
0x180003a98  mov     rcx, r14; lpString1
0x180003a9b  call    cs:__imp_lstrcmpiW
0x180003aa1  test    eax, eax
0x180003aa3  jnz     loc_180003BA2
0x180003aa9  lea     rdx, [rbp+2E0h+ValueName]; unsigned __int16 *
0x180003ab0  mov     rcx, r12; this
0x180003ab3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003ab8  mov     edi, eax
0x180003aba  test    eax, eax
0x180003abc  js      loc_1800040F8
0x180003ac2  mov     rdx, r14; unsigned __int16 *
0x180003ac5  mov     rcx, r12; this
0x180003ac8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003acd  mov     edi, eax
0x180003acf  test    eax, eax
0x180003ad1  js      loc_1800040F8
0x180003ad7  cmp     word ptr [r14], 3Dh ; '='
0x180003adc  jnz     loc_180004175
0x180003ae2  xor     edi, edi
0x180003ae4  cmp     [rbp+2E0h+var_2D0], edi
0x180003ae7  jz      short loc_180003B32
0x180003ae9  mov     [rbp+2E0h+var_2A8], rdi
0x180003aed  mov     [rbp+2E0h+var_2A0], rdi
0x180003af1  mov     rax, [rbp+2E0h+hKey]
0x180003af5  mov     [rbp+2E0h+var_2B0], rax
0x180003af9  mov     byte ptr [rsp+340h+phkResult], dil; bool
0x180003afe  mov     r9, r14; unsigned __int16 *
0x180003b01  lea     r8, [rbp+2E0h+ValueName]; unsigned __int16 *
0x180003b08  lea     rdx, [rbp+2E0h+var_2B0]; struct ATL::CRegKey *
0x180003b0c  mov     rcx, r12; this
0x180003b0f  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)
0x180003b14  mov     edi, eax
0x180003b16  test    eax, eax
0x180003b18  jns     loc_18000409D
0x180003b1e  test    rsi, rsi
0x180003b21  jz      short loc_180003B2D
0x180003b23  mov     rcx, rsi; hKey
0x180003b26  call    cs:__imp_RegCloseKey
0x180003b2c  nop
0x180003b2d  jmp     loc_180004141
0x180003b32  test    r13d, r13d
0x180003b35  jnz     short loc_180003B92
0x180003b37  mov     [rbp+2E0h+var_2D8], rdi
0x180003b3b  lea     rax, [rbp+2E0h+var_2D8]
0x180003b3f  mov     [rsp+340h+phkResult], rax; phkResult
0x180003b44  mov     r9d, 20006h; samDesired
0x180003b4a  xor     r8d, r8d; ulOptions
0x180003b4d  xor     edx, edx; lpSubKey
0x180003b4f  mov     rcx, [rbp+2E0h+hKey]; hKey
0x180003b53  call    cs:__imp_RegOpenKeyExW
0x180003b59  mov     edi, eax
0x180003b5b  test    eax, eax
0x180003b5d  jnz     loc_180004168
0x180003b63  mov     r15, [rbp+2E0h+var_2D8]
0x180003b67  lea     rdx, [rbp+2E0h+ValueName]; lpValueName
0x180003b6e  mov     rcx, r15; hKey
0x180003b71  call    cs:__imp_RegDeleteValueW
0x180003b77  mov     edi, eax
0x180003b79  test    eax, 0FFFFFFFDh
0x180003b7e  jnz     loc_18000414B
0x180003b84  test    r15, r15
0x180003b87  jz      short loc_180003B92
0x180003b89  mov     rcx, r15; hKey
0x180003b8c  call    cs:__imp_RegCloseKey
0x180003b92  mov     rdx, r14; unsigned __int16 *
0x180003b95  mov     rcx, r12; this
0x180003b98  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180003b9d  jmp     loc_1800040E7
0x180003ba2  movzx   eax, word ptr [r14]
0x180003ba6  test    ax, ax
0x180003ba9  jz      short loc_180003BD0
0x180003bab  mov     rcx, r14; lpsz
0x180003bae  cmp     ax, 5Ch ; '\'
0x180003bb2  jz      short loc_180003BC7
0x180003bb4  call    cs:__imp_CharNextW
0x180003bba  mov     rcx, rax
0x180003bbd  movzx   eax, word ptr [rax]
0x180003bc0  test    ax, ax
0x180003bc3  jnz     short loc_180003BAE
0x180003bc5  jmp     short loc_180003BD0
0x180003bc7  test    rcx, rcx
0x180003bca  jnz     loc_18000419C
0x180003bd0  cmp     [rbp+2E0h+var_2D0], edi
0x180003bd3  jz      loc_180003D3E
0x180003bd9  mov     [rbp+2E0h+var_2D8], rdi
0x180003bdd  lea     rax, [rbp+2E0h+var_2D8]
0x180003be1  mov     [rsp+340h+phkResult], rax; phkResult
0x180003be6  mov     r9d, 0F003Fh; samDesired
0x180003bec  xor     r8d, r8d; ulOptions
0x180003bef  mov     rdx, r14; lpSubKey
0x180003bf2  mov     rdi, [rbp+2E0h+hKey]
0x180003bf6  mov     rcx, rdi; hKey
0x180003bf9  call    cs:__imp_RegOpenKeyExW
0x180003bff  xor     r15d, r15d
0x180003c02  test    eax, eax
0x180003c04  jnz     short loc_180003C27
0x180003c06  mov     eax, r15d
0x180003c09  test    rsi, rsi
0x180003c0c  jz      short loc_180003C17
0x180003c0e  mov     rcx, rsi; hKey
0x180003c11  call    cs:__imp_RegCloseKey
0x180003c17  mov     rsi, [rbp+2E0h+var_2D8]
0x180003c1b  mov     [rbp+2E0h+var_290], rsi
0x180003c1f  test    eax, eax
0x180003c21  jz      loc_180003CD1
0x180003c27  mov     [rbp+2E0h+var_2D8], r15
0x180003c2b  lea     rax, [rbp+2E0h+var_2D8]
0x180003c2f  mov     [rsp+340h+phkResult], rax; phkResult
0x180003c34  mov     r9d, 20019h; samDesired
0x180003c3a  xor     r8d, r8d; ulOptions
0x180003c3d  mov     rdx, r14; lpSubKey
0x180003c40  mov     rcx, rdi; hKey
0x180003c43  call    cs:__imp_RegOpenKeyExW
0x180003c49  test    eax, eax
0x180003c4b  jnz     short loc_180003C6A
0x180003c4d  mov     eax, r15d
0x180003c50  test    rsi, rsi
0x180003c53  jz      short loc_180003C5E
0x180003c55  mov     rcx, rsi; hKey
0x180003c58  call    cs:__imp_RegCloseKey
0x180003c5e  mov     rsi, [rbp+2E0h+var_2D8]
0x180003c62  mov     [rbp+2E0h+var_290], rsi
0x180003c66  test    eax, eax
0x180003c68  jz      short loc_180003CD1
0x180003c6a  mov     [rbp+2E0h+dwDisposition], r15d
0x180003c6e  mov     [rbp+2E0h+var_2D8], r15
0x180003c72  lea     rax, [rbp+2E0h+dwDisposition]
0x180003c76  mov     [rsp+340h+lpdwDisposition], rax; lpdwDisposition
0x180003c7b  lea     rax, [rbp+2E0h+var_2D8]
0x180003c7f  mov     [rsp+340h+var_308], rax; phkResult
0x180003c84  mov     [rsp+340h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180003c89  mov     [rsp+340h+samDesired], 2001Fh; samDesired
0x180003c91  mov     dword ptr [rsp+340h+phkResult], r15d; dwOptions
0x180003c96  xor     r9d, r9d; lpClass
0x180003c99  xor     r8d, r8d; Reserved
0x180003c9c  mov     rdx, r14; lpSubKey
0x180003c9f  mov     rcx, rdi; hKey
0x180003ca2  call    cs:__imp_RegCreateKeyExW
0x180003ca8  test    eax, eax
0x180003caa  jnz     loc_1800041C0
0x180003cb0  mov     eax, r15d
0x180003cb3  test    rsi, rsi
0x180003cb6  jz      short loc_180003CC1
0x180003cb8  mov     rcx, rsi; hKey
0x180003cbb  call    cs:__imp_RegCloseKey
0x180003cc1  mov     rsi, [rbp+2E0h+var_2D8]
0x180003cc5  mov     [rbp+2E0h+var_290], rsi
0x180003cc9  test    eax, eax
0x180003ccb  jnz     loc_1800041C0
0x180003cd1  movzx   eax, word ptr [r14]
0x180003cd5  sub     ax, 4Ch ; 'L'
0x180003cd9  mov     ecx, 0FFDFh
0x180003cde  test    cx, ax
0x180003ce1  jnz     short loc_180003D02
0x180003ce3  lea     rdx, aLocalserver32; "LocalServer32"
0x180003cea  mov     rcx, r14; lpString1
0x180003ced  call    cs:__imp_lstrcmpiW
0x180003cf3  movzx   r15d, r15b
0x180003cf7  test    eax, eax
0x180003cf9  mov     eax, 1
0x180003cfe  cmovz   r15d, eax
0x180003d02  mov     rdx, r14; unsigned __int16 *
0x180003d05  mov     rcx, r12; this
0x180003d08  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003d0d  mov     edi, eax
0x180003d0f  test    eax, eax
0x180003d11  js      loc_1800040F8
0x180003d17  cmp     word ptr [r14], 3Dh ; '='
0x180003d1c  jnz     loc_18000409D
0x180003d22  mov     byte ptr [rsp+340h+phkResult], r15b; bool
0x180003d27  mov     r9, r14; unsigned __int16 *
0x180003d2a  xor     r8d, r8d; unsigned __int16 *
0x180003d2d  lea     rdx, [rbp+2E0h+var_290]; struct ATL::CRegKey *
0x180003d31  mov     rcx, r12; this
0x180003d34  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)
0x180003d39  jmp     loc_180004097
0x180003d3e  test    r13d, r13d
0x180003d41  jnz     short loc_180003D8C
0x180003d43  mov     [rbp+2E0h+var_2D8], rdi
0x180003d47  lea     rax, [rbp+2E0h+var_2D8]
0x180003d4b  mov     [rsp+340h+phkResult], rax; phkResult
0x180003d50  mov     r9d, 20019h; samDesired
0x180003d56  xor     r8d, r8d; ulOptions
0x180003d59  mov     rdx, r14; lpSubKey
  ... truncated ...
```
