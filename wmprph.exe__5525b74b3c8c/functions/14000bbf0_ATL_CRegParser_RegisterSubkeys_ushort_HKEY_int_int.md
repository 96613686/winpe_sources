# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x14000bbf0`
- end: `0x14000c548`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `2392`
- prototype: `__int64 __usercall@<rax>(ATL::CRegParser *__hidden this@<rcx>, unsigned __int16 *@<rdx>, HKEY@<r8>, int@<r9d>, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x14000b808`
- `0x14000bbf0`

## callees

- `0x140001390`
- `0x140009ec8`
- `0x14000af48`
- `0x14000b134`
- `0x14000b6b8`
- `0x14000bbf0`
- `0x14000c774`
- `0x14000ca78`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x14000c22d`
- `ADVAPI32!RegEnumValueW` at `0x14000c22d`
- `ADVAPI32!RegDeleteValueW` at `0x14000be66`
- `ADVAPI32!RegDeleteValueW` at `0x14000be66`
- `ADVAPI32!RegOpenKeyExW` at `0x14000be4b`
- `ADVAPI32!RegOpenKeyExW` at `0x14000bee7`
- `ADVAPI32!RegOpenKeyExW` at `0x14000bf31`
- `ADVAPI32!RegOpenKeyExW` at `0x14000c0ad`
- `ADVAPI32!RegOpenKeyExW` at `0x14000be4b`
- `ADVAPI32!RegOpenKeyExW` at `0x14000bee7`
- `ADVAPI32!RegOpenKeyExW` at `0x14000bf31`
- `ADVAPI32!RegOpenKeyExW` at `0x14000c0ad`
- `ADVAPI32!RegCreateKeyExW` at `0x14000bf90`
- `ADVAPI32!RegCreateKeyExW` at `0x14000bf90`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000c18a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000c1d7`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000c32f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000c18a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000c1d7`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000c32f`
- `ADVAPI32!RegCloseKey` at `0x14000be1b`
- `ADVAPI32!RegCloseKey` at `0x14000be85`
- `ADVAPI32!RegCloseKey` at `0x14000beff`
- `ADVAPI32!RegCloseKey` at `0x14000bf46`
- `ADVAPI32!RegCloseKey` at `0x14000bfa9`
- `ADVAPI32!RegCloseKey` at `0x14000c0c1`
- `ADVAPI32!RegCloseKey` at `0x14000c389`
- `ADVAPI32!RegCloseKey` at `0x14000c3f8`
- `ADVAPI32!RegCloseKey` at `0x14000c40b`
- `ADVAPI32!RegCloseKey` at `0x14000c454`
- `ADVAPI32!RegCloseKey` at `0x14000c471`
- `ADVAPI32!RegCloseKey` at `0x14000c494`
- `ADVAPI32!RegCloseKey` at `0x14000c4b7`
- `ADVAPI32!RegCloseKey` at `0x14000c4da`
- `ADVAPI32!RegCloseKey` at `0x14000be1b`
- `ADVAPI32!RegCloseKey` at `0x14000be85`
- `ADVAPI32!RegCloseKey` at `0x14000beff`
- `ADVAPI32!RegCloseKey` at `0x14000bf46`
- `ADVAPI32!RegCloseKey` at `0x14000bfa9`
- `ADVAPI32!RegCloseKey` at `0x14000c0c1`
- `ADVAPI32!RegCloseKey` at `0x14000c389`
- `ADVAPI32!RegCloseKey` at `0x14000c3f8`
- `ADVAPI32!RegCloseKey` at `0x14000c40b`
- `ADVAPI32!RegCloseKey` at `0x14000c454`
- `ADVAPI32!RegCloseKey` at `0x14000c471`
- `ADVAPI32!RegCloseKey` at `0x14000c494`
- `ADVAPI32!RegCloseKey` at `0x14000c4b7`
- `ADVAPI32!RegCloseKey` at `0x14000c4da`
- `KERNEL32!lstrcpynW` at `0x14000c141`
- `KERNEL32!lstrcpynW` at `0x14000c141`
- `KERNEL32!lstrcmpiW` at `0x14000bc71`
- `KERNEL32!lstrcmpiW` at `0x14000bc84`
- `KERNEL32!lstrcmpiW` at `0x14000bd03`
- `KERNEL32!lstrcmpiW` at `0x14000bd5e`
- `KERNEL32!lstrcmpiW` at `0x14000bd8c`
- `KERNEL32!lstrcmpiW` at `0x14000bfdb`
- `KERNEL32!lstrcmpiW` at `0x14000c350`
- `KERNEL32!lstrcmpiW` at `0x14000bc71`
- `KERNEL32!lstrcmpiW` at `0x14000bc84`
- `KERNEL32!lstrcmpiW` at `0x14000bd03`
- `KERNEL32!lstrcmpiW` at `0x14000bd5e`
- `KERNEL32!lstrcmpiW` at `0x14000bd8c`
- `KERNEL32!lstrcmpiW` at `0x14000bfdb`
- `KERNEL32!lstrcmpiW` at `0x14000c350`
- `USER32!CharNextW` at `0x14000bcd7`
- `USER32!CharNextW` at `0x14000bea2`
- `USER32!CharNextW` at `0x14000bcd7`
- `USER32!CharNextW` at `0x14000bea2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c241`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c24c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c419`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c42f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c47f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c4a2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c4c5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c4e8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c500`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c518`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c241`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c24c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c419`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c42f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c47f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c4a2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c4c5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c4e8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c500`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c518`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000c10a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000c1f9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000c10a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000c1f9`

## string_xrefs

- `0x14000bc77`: `ForceRemove`
- `0x14000bd54`: `NoRemove`
- `0x14000bc67`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  HKEY v5; // rsi
  __int64 result; // rax
  signed int Token; // edi
  _QWORD *v10; // rbx
  int v11; // r13d
  int v12; // r15d
  int v13; // edi
  WCHAR v14; // ax
  const WCHAR *v15; // rcx
  int v16; // eax
  unsigned __int64 v17; // rdx
  int v18; // r15d
  LSTATUS v19; // eax
  HKEY v20; // r15
  LSTATUS v21; // eax
  WCHAR v22; // ax
  const WCHAR *v23; // rcx
  HKEY v24; // rdi
  bool v25; // r15
  LSTATUS v26; // eax
  LSTATUS v27; // eax
  LSTATUS v28; // eax
  __int64 v29; // rax
  int v30; // eax
  LSTATUS v31; // eax
  WCHAR *v32; // r15
  void *v33; // rsp
  _QWORD *v34; // rax
  _WORD *v35; // rdi
  __int64 v36; // rdi
  LSTATUS v37; // eax
  void *v38; // rcx
  void *v39; // rcx
  void *v40; // rcx
  void *v41; // rcx
  void *v42; // rcx
  void *v43; // rcx
  void *v44; // rcx
  void *v45; // rcx
  char v46; // [rsp+40h] [rbp-210h] BYREF
  DWORD dwDisposition; // [rsp+250h] [rbp+0h] BYREF
  HKEY phkResult; // [rsp+258h] [rbp+8h] BYREF
  int v49; // [rsp+260h] [rbp+10h]
  HKEY hKey; // [rsp+268h] [rbp+18h]
  int v51; // [rsp+270h] [rbp+20h]
  LPWSTR lpString1; // [rsp+278h] [rbp+28h]
  HKEY v53; // [rsp+280h] [rbp+30h] BYREF
  __int64 v54; // [rsp+288h] [rbp+38h]
  __int64 v55; // [rsp+290h] [rbp+40h]
  int v56; // [rsp+298h] [rbp+48h]
  _QWORD v57[4]; // [rsp+2A0h] [rbp+50h] BYREF
  WCHAR ValueName[264]; // [rsp+2C0h] [rbp+70h] BYREF

  v49 = a4;
  v5 = 0;
  memset(v57, 0, 24);
  hKey = a3;
  result = ATL::CRegParser::NextToken(this, a2);
  Token = result;
  if ( (int)result < 0 )
    return result;
  v10 = 0;
  lpString1 = 0;
  v11 = a5;
  v56 = a5;
  v51 = 1;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( *a2 == 125 )
        goto LABEL_114;
      v12 = lstrcmpiW(a2, L"Delete");
      if ( !lstrcmpiW(a2, L"ForceRemove") || !v12 )
      {
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_114;
        v13 = 0;
        if ( v49 )
        {
          v14 = *a2;
          v53 = 0;
          v54 = 0;
          v55 = 0;
          if ( !v14 )
            goto LABEL_13;
          v15 = a2;
          do
          {
            if ( v14 == 92 )
            {
              if ( !v15 )
                break;
              if ( v5 )
                RegCloseKey(v5);
              while ( v10 )
              {
                v38 = v10;
                v10 = (_QWORD *)*v10;
                free(v38);
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
              v53 = hKey;
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&v53, a2);
              break;
            }
          }
          if ( !v12 )
          {
            Token = ATL::CRegParser::NextToken(this, a2);
            if ( Token < 0 )
              goto LABEL_114;
            v16 = ATL::CRegParser::SkipAssignment(this, a2);
            goto LABEL_58;
          }
        }
      }
      if ( !lstrcmpiW(a2, L"NoRemove") )
      {
        v51 = 0;
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_114;
      }
      if ( !lstrcmpiW(a2, L"Val") )
      {
        Token = ATL::CRegParser::NextToken(this, ValueName);
        if ( Token < 0 )
          goto LABEL_114;
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_114;
        if ( *a2 != 61 )
        {
          if ( v5 )
            RegCloseKey(v5);
          while ( v10 )
          {
            v40 = v10;
            v10 = (_QWORD *)*v10;
            free(v40);
          }
          return 2147614729LL;
        }
        v18 = v49;
        if ( !v49 )
        {
          if ( v11 )
            goto LABEL_111;
          phkResult = 0;
          v19 = RegOpenKeyExW(hKey, 0, 0, 0x20006u, &phkResult);
          Token = v19;
          if ( v19 )
          {
            if ( v19 > 0 )
              Token = (unsigned __int16)v19 | 0x80070000;
          }
          else
          {
            v20 = phkResult;
            v21 = RegDeleteValueW(phkResult, ValueName);
            Token = v21;
            if ( (v21 & 0xFFFFFFFD) == 0 )
            {
              if ( v20 )
                RegCloseKey(v20);
              goto LABEL_111;
            }
            if ( v21 > 0 )
              Token = (unsigned __int16)v21 | 0x80070000;
            if ( v20 )
              RegCloseKey(v20);
          }
LABEL_114:
          if ( v5 )
            RegCloseKey(v5);
          while ( v10 )
          {
            v45 = v10;
            v10 = (_QWORD *)*v10;
            free(v45);
          }
          return (unsigned int)Token;
        }
        v53 = hKey;
        v54 = 0;
        v55 = 0;
        Token = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)&v53, ValueName, a2, 0);
        if ( Token < 0 )
        {
          if ( v5 )
            RegCloseKey(v5);
          while ( v10 )
          {
            v39 = v10;
            v10 = (_QWORD *)*v10;
            free(v39);
          }
          return (unsigned int)Token;
        }
        goto LABEL_60;
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
            goto LABEL_40;
        }
        if ( v23 )
        {
          if ( v5 )
            RegCloseKey(v5);
          while ( v10 )
          {
            v41 = v10;
            v10 = (_QWORD *)*v10;
            free(v41);
          }
          return 2147614729LL;
        }
      }
LABEL_40:
      if ( !v49 )
        break;
      phkResult = 0;
      v24 = hKey;
      v25 = 0;
      if ( RegOpenKeyExW(hKey, a2, 0, 0xF003Fu, &phkResult) )
        goto LABEL_158;
      v26 = 0;
      if ( v5 )
        v26 = RegCloseKey(v5);
      v5 = phkResult;
      v57[0] = phkResult;
      if ( v26 )
      {
LABEL_158:
        phkResult = 0;
        if ( RegOpenKeyExW(v24, a2, 0, 0x20019u, &phkResult) )
          goto LABEL_159;
        v27 = 0;
        if ( v5 )
          v27 = RegCloseKey(v5);
        v5 = phkResult;
        v57[0] = phkResult;
        if ( v27 )
        {
LABEL_159:
          dwDisposition = 0;
          phkResult = 0;
          if ( RegCreateKeyExW(v24, a2, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition) )
            goto LABEL_140;
          v28 = 0;
          if ( v5 )
            v28 = RegCloseKey(v5);
          v5 = phkResult;
          v57[0] = phkResult;
          if ( v28 )
          {
LABEL_140:
            if ( v5 )
              RegCloseKey(v5);
            while ( v10 )
            {
              v42 = v10;
              v10 = (_QWORD *)*v10;
              free(v42);
            }
            return 2147614729LL;
          }
        }
      }
      if ( ((*a2 - 76) & 0xFFDF) == 0 )
        v25 = lstrcmpiW(a2, L"LocalServer32") == 0;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_114;
      if ( *a2 != 61 )
        goto LABEL_59;
      v16 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)v57, 0, a2, v25);
LABEL_58:
      Token = v16;
      if ( v16 < 0 )
        goto LABEL_114;
LABEL_59:
      v18 = v49;
LABEL_60:
      if ( *a2 == 123 )
      {
        v29 = -1;
        do
          ++v29;
        while ( a2[v29] );
        if ( v29 == 1 )
        {
          Token = ATL::CRegParser::RegisterSubkeys(this, a2, v5, v18, 0);
          if ( Token < 0 )
            goto LABEL_114;
          goto LABEL_65;
        }
      }
    }
    if ( !v11 )
    {
      phkResult = 0;
      if ( RegOpenKeyExW(hKey, a2, 0, 0x20019u, &phkResult) )
        goto LABEL_71;
      v31 = 0;
      if ( v5 )
        v31 = RegCloseKey(v5);
      v5 = phkResult;
      v57[0] = phkResult;
      if ( v31 )
LABEL_71:
        v11 = 1;
    }
    v32 = lpString1;
    if ( lpString1 )
      goto LABEL_80;
    if ( ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)0x208, v17) )
    {
      v33 = alloca(528);
      v32 = (WCHAR *)&v46;
    }
    else
    {
      v34 = malloc(0x218u);
      if ( !v34 )
      {
        v32 = 0;
        lpString1 = 0;
        goto LABEL_79;
      }
      *v34 = v10;
      v32 = (WCHAR *)(v34 + 2);
      v10 = v34;
    }
    lpString1 = v32;
LABEL_79:
    if ( !v32 )
      break;
LABEL_80:
    lstrcpynW(v32, a2, 260);
    if ( !v11 )
    {
      dwDisposition = 0;
      if ( RegQueryInfoKeyW(v5, 0, 0, 0, &dwDisposition, 0, 0, 0, 0, 0, 0, 0) < 0 || !dwDisposition )
      {
        dwDisposition = 0;
        if ( RegQueryInfoKeyW(v5, 0, 0, 0, 0, 0, 0, &dwDisposition, 0, 0, 0, 0) )
          goto LABEL_106;
        if ( dwDisposition == 1 )
        {
          LODWORD(phkResult) = 4096;
          v35 = malloc(0x2000u);
          if ( !v35 )
            goto LABEL_106;
          if ( RegEnumValueW(v5, 0, v35, (LPDWORD)&phkResult, 0, 0, 0, 0) || !*v35 )
          {
            free(v35);
LABEL_106:
            if ( v5 )
            {
              v37 = RegCloseKey(v5);
              v5 = 0;
              v57[0] = 0;
              if ( v37 )
              {
                while ( v10 )
                {
                  v44 = v10;
                  v10 = (_QWORD *)*v10;
                  free(v44);
                }
                return 2147614729LL;
              }
            }
            if ( v51 )
            {
              v53 = hKey;
              v54 = 0;
              v55 = 0;
              ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v53, v32);
            }
            Token = ATL::CRegParser::NextToken(this, a2);
            if ( Token < 0 )
              goto LABEL_114;
LABEL_111:
            v30 = ATL::CRegParser::SkipAssignment(this, a2);
            goto LABEL_112;
          }
          free(v35);
        }
        else if ( !dwDisposition )
        {
          goto LABEL_106;
        }
      }
    }
    Token = ATL::CRegParser::NextToken(this, a2);
    if ( Token < 0 )
      goto LABEL_114;
    Token = ATL::CRegParser::SkipAssignment(this, a2);
    if ( Token < 0 )
      goto LABEL_114;
    if ( *a2 == 123 )
    {
      Token = ATL::CRegParser::RegisterSubkeys(this, a2, v5, 0, v11);
      if ( Token < 0 )
        goto LABEL_114;
      if ( !v11 )
        goto LABEL_100;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_114;
      Token = ATL::CRegParser::SkipAssignment(this, a2);
      if ( Token < 0 )
        goto LABEL_114;
      v11 = v56;
    }
    else if ( !v11 )
    {
LABEL_100:
      dwDisposition = 0;
      if ( RegQueryInfoKeyW(v5, 0, 0, 0, &dwDisposition, 0, 0, 0, 0, 0, 0, 0) < 0 || !dwDisposition )
        goto LABEL_106;
      v36 = 0;
      while ( lstrcmpiW(v32, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v36]) )
      {
        v36 = (unsigned int)(v36 + 1);
        if ( (int)v36 >= 2 )
        {
          ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v57, v32);
          v5 = (HKEY)v57[0];
          break;
        }
      }
LABEL_65:
      v30 = ATL::CRegParser::NextToken(this, a2);
LABEL_112:
      Token = v30;
      if ( v30 < 0 )
        goto LABEL_114;
    }
  }
  if ( v5 )
    RegCloseKey(v5);
  while ( v10 )
  {
    v43 = v10;
    v10 = (_QWORD *)*v10;
    free(v43);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x14000bbf0  push    rbp
0x14000bbf2  push    rbx
0x14000bbf3  push    rsi
0x14000bbf4  push    rdi
0x14000bbf5  push    r12
0x14000bbf7  push    r13
0x14000bbf9  push    r14
0x14000bbfb  push    r15
0x14000bbfd  sub     rsp, 2F8h
0x14000bc04  lea     rbp, [rsp+60h]
0x14000bc09  mov     rax, cs:__security_cookie
0x14000bc10  xor     rax, rbp
0x14000bc13  mov     [rbp+2D0h+var_50], rax
0x14000bc1a  xor     r13d, r13d
0x14000bc1d  mov     [rbp+2D0h+var_2C0], r9d
0x14000bc21  mov     esi, r13d
0x14000bc24  mov     [rbp+2D0h+var_280], r13
0x14000bc28  mov     [rbp+2D0h+var_278], r13
0x14000bc2c  mov     r14, rdx
0x14000bc2f  mov     [rbp+2D0h+var_270], r13
0x14000bc33  mov     r12, rcx
0x14000bc36  mov     [rbp+2D0h+hKey], r8
0x14000bc3a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000bc3f  mov     edi, eax
0x14000bc41  test    eax, eax
0x14000bc43  js      loc_14000C525
0x14000bc49  mov     ebx, r13d
0x14000bc4c  mov     [rbp+2D0h+lpString1], r13
0x14000bc50  mov     r13d, [rbp+2D0h+arg_20]
0x14000bc57  mov     [rbp+2D0h+var_288], r13d
0x14000bc5b  mov     [rbp+2D0h+var_2B0], 1
0x14000bc62  jmp     loc_14000C3E1
0x14000bc67  lea     rdx, aDelete; "Delete"
0x14000bc6e  mov     rcx, r14; lpString1
0x14000bc71  call    cs:__imp_lstrcmpiW
0x14000bc77  lea     rdx, aForceremove; "ForceRemove"
0x14000bc7e  mov     rcx, r14; lpString1
0x14000bc81  mov     r15d, eax
0x14000bc84  call    cs:__imp_lstrcmpiW
0x14000bc8a  xor     edi, edi
0x14000bc8c  test    eax, eax
0x14000bc8e  jz      short loc_14000BC99
0x14000bc90  test    r15d, r15d
0x14000bc93  jnz     loc_14000BD54
0x14000bc99  mov     rdx, r14; unsigned __int16 *
0x14000bc9c  mov     rcx, r12; this
0x14000bc9f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000bca4  mov     edi, eax
0x14000bca6  test    eax, eax
0x14000bca8  js      loc_14000C3EC
0x14000bcae  xor     edi, edi
0x14000bcb0  cmp     [rbp+2D0h+var_2C0], edi
0x14000bcb3  jz      loc_14000BD54
0x14000bcb9  movzx   eax, word ptr [r14]
0x14000bcbd  mov     [rbp+2D0h+var_2A0], rdi
0x14000bcc1  mov     [rbp+2D0h+var_298], rdi
0x14000bcc5  mov     [rbp+2D0h+var_290], rdi
0x14000bcc9  test    ax, ax
0x14000bccc  jz      short loc_14000BCF3
0x14000bcce  mov     rcx, r14; lpsz
0x14000bcd1  cmp     ax, 5Ch ; '\'
0x14000bcd5  jz      short loc_14000BCEA
0x14000bcd7  call    cs:__imp_CharNextW
0x14000bcdd  mov     rcx, rax
0x14000bce0  movzx   eax, word ptr [rax]
0x14000bce3  test    ax, ax
0x14000bce6  jnz     short loc_14000BCD1
0x14000bce8  jmp     short loc_14000BCF3
0x14000bcea  test    rcx, rcx
0x14000bced  jnz     loc_14000C403
0x14000bcf3  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1PAPEBGA; ushort const * near * ATL::CRegParser::rgszNeverDelete
0x14000bcfa  mov     edx, edi
0x14000bcfc  mov     rcx, r14; lpString1
0x14000bcff  mov     rdx, [rax+rdx*8]; lpString2
0x14000bd03  call    cs:__imp_lstrcmpiW
0x14000bd09  test    eax, eax
0x14000bd0b  jz      short loc_14000BD28
0x14000bd0d  inc     edi
0x14000bd0f  cmp     edi, 2
0x14000bd12  jl      short loc_14000BCF3
0x14000bd14  mov     rax, [rbp+2D0h+hKey]
0x14000bd18  lea     rcx, [rbp+2D0h+var_2A0]; this
0x14000bd1c  mov     rdx, r14; unsigned __int16 *
0x14000bd1f  mov     [rbp+2D0h+var_2A0], rax
0x14000bd23  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x14000bd28  xor     edi, edi
0x14000bd2a  test    r15d, r15d
0x14000bd2d  jnz     short loc_14000BD54
0x14000bd2f  mov     rdx, r14; unsigned __int16 *
0x14000bd32  mov     rcx, r12; this
0x14000bd35  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000bd3a  mov     edi, eax
0x14000bd3c  test    eax, eax
0x14000bd3e  js      loc_14000C3EC
0x14000bd44  mov     rdx, r14; unsigned __int16 *
0x14000bd47  mov     rcx, r12; this
0x14000bd4a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x14000bd4f  jmp     loc_14000C025
0x14000bd54  lea     rdx, aNoremove; "NoRemove"
0x14000bd5b  mov     rcx, r14; lpString1
0x14000bd5e  call    cs:__imp_lstrcmpiW
0x14000bd64  test    eax, eax
0x14000bd66  jnz     short loc_14000BD82
0x14000bd68  mov     rdx, r14; unsigned __int16 *
0x14000bd6b  mov     [rbp+2D0h+var_2B0], edi
0x14000bd6e  mov     rcx, r12; this
0x14000bd71  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000bd76  mov     edi, eax
0x14000bd78  test    eax, eax
0x14000bd7a  js      loc_14000C3EC
0x14000bd80  xor     edi, edi
0x14000bd82  lea     rdx, aVal; "Val"
0x14000bd89  mov     rcx, r14; lpString1
0x14000bd8c  call    cs:__imp_lstrcmpiW
0x14000bd92  test    eax, eax
0x14000bd94  jnz     loc_14000BE90
0x14000bd9a  lea     rdx, [rbp+2D0h+ValueName]; unsigned __int16 *
0x14000bd9e  mov     rcx, r12; this
0x14000bda1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000bda6  mov     edi, eax
0x14000bda8  test    eax, eax
0x14000bdaa  js      loc_14000C3EC
0x14000bdb0  mov     rdx, r14; unsigned __int16 *
0x14000bdb3  mov     rcx, r12; this
0x14000bdb6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000bdbb  mov     edi, eax
0x14000bdbd  test    eax, eax
0x14000bdbf  js      loc_14000C3EC
0x14000bdc5  cmp     word ptr [r14], 3Dh ; '='
0x14000bdca  jnz     loc_14000C469
0x14000bdd0  mov     r15d, [rbp+2D0h+var_2C0]
0x14000bdd4  xor     edi, edi
0x14000bdd6  test    r15d, r15d
0x14000bdd9  jz      short loc_14000BE26
0x14000bddb  mov     rax, [rbp+2D0h+hKey]
0x14000bddf  lea     r8, [rbp+2D0h+ValueName]; unsigned __int16 *
0x14000bde3  mov     r9, r14; unsigned __int16 *
0x14000bde6  mov     [rbp+2D0h+var_2A0], rax
0x14000bdea  lea     rdx, [rbp+2D0h+var_2A0]; struct ATL::CRegKey *
0x14000bdee  mov     [rbp+2D0h+var_298], rdi
0x14000bdf2  mov     rcx, r12; this
0x14000bdf5  mov     [rbp+2D0h+var_290], rdi
0x14000bdf9  mov     byte ptr [rsp+330h+phkResult], dil; bool
0x14000bdfe  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)
0x14000be03  xor     ecx, ecx
0x14000be05  mov     edi, eax
0x14000be07  test    eax, eax
0x14000be09  jns     loc_14000C035
0x14000be0f  test    rsi, rsi
0x14000be12  jz      loc_14000C435
0x14000be18  mov     rcx, rsi; hKey
0x14000be1b  call    cs:__imp_RegCloseKey
0x14000be21  jmp     loc_14000C435
0x14000be26  test    r13d, r13d
0x14000be29  jnz     loc_14000C3D0
0x14000be2f  mov     rcx, [rbp+2D0h+hKey]; hKey
0x14000be33  lea     rax, [rbp+2D0h+var_2C8]
0x14000be37  mov     r9d, 20006h; samDesired
0x14000be3d  mov     [rsp+330h+phkResult], rax; phkResult
0x14000be42  xor     r8d, r8d; ulOptions
0x14000be45  mov     [rbp+2D0h+var_2C8], rdi
0x14000be49  xor     edx, edx; lpSubKey
0x14000be4b  call    cs:__imp_RegOpenKeyExW
0x14000be51  mov     edi, eax
0x14000be53  test    eax, eax
0x14000be55  jnz     loc_14000C45C
0x14000be5b  mov     r15, [rbp+2D0h+var_2C8]
0x14000be5f  lea     rdx, [rbp+2D0h+ValueName]; lpValueName
0x14000be63  mov     rcx, r15; hKey
0x14000be66  call    cs:__imp_RegDeleteValueW
0x14000be6c  mov     edi, eax
0x14000be6e  test    eax, 0FFFFFFFDh
0x14000be73  jnz     loc_14000C43F
0x14000be79  test    r15, r15
0x14000be7c  jz      loc_14000C3D0
0x14000be82  mov     rcx, r15; hKey
0x14000be85  call    cs:__imp_RegCloseKey
0x14000be8b  jmp     loc_14000C3D0
0x14000be90  movzx   eax, word ptr [r14]
0x14000be94  test    ax, ax
0x14000be97  jz      short loc_14000BEBE
0x14000be99  mov     rcx, r14; lpsz
0x14000be9c  cmp     ax, 5Ch ; '\'
0x14000bea0  jz      short loc_14000BEB5
0x14000bea2  call    cs:__imp_CharNextW
0x14000bea8  mov     rcx, rax
0x14000beab  movzx   eax, word ptr [rax]
0x14000beae  test    ax, ax
0x14000beb1  jnz     short loc_14000BE9C
0x14000beb3  jmp     short loc_14000BEBE
0x14000beb5  test    rcx, rcx
0x14000beb8  jnz     loc_14000C48C
0x14000bebe  cmp     [rbp+2D0h+var_2C0], edi
0x14000bec1  jz      loc_14000C08B
0x14000bec7  mov     [rbp+2D0h+var_2C8], rdi
0x14000becb  lea     rax, [rbp+2D0h+var_2C8]
0x14000becf  mov     rdi, [rbp+2D0h+hKey]
0x14000bed3  mov     r9d, 0F003Fh; samDesired
0x14000bed9  mov     rcx, rdi; hKey
0x14000bedc  mov     [rsp+330h+phkResult], rax; phkResult
0x14000bee1  xor     r8d, r8d; ulOptions
0x14000bee4  mov     rdx, r14; lpSubKey
0x14000bee7  call    cs:__imp_RegOpenKeyExW
0x14000beed  xor     r15d, r15d
0x14000bef0  test    eax, eax
0x14000bef2  jnz     short loc_14000BF15
0x14000bef4  mov     eax, r15d
0x14000bef7  test    rsi, rsi
0x14000befa  jz      short loc_14000BF05
0x14000befc  mov     rcx, rsi; hKey
0x14000beff  call    cs:__imp_RegCloseKey
0x14000bf05  mov     rsi, [rbp+2D0h+var_2C8]
0x14000bf09  mov     [rbp+2D0h+var_280], rsi
0x14000bf0d  test    eax, eax
0x14000bf0f  jz      loc_14000BFBF
0x14000bf15  lea     rax, [rbp+2D0h+var_2C8]
0x14000bf19  mov     [rbp+2D0h+var_2C8], r15
0x14000bf1d  mov     r9d, 20019h; samDesired
0x14000bf23  mov     [rsp+330h+phkResult], rax; phkResult
0x14000bf28  xor     r8d, r8d; ulOptions
0x14000bf2b  mov     rdx, r14; lpSubKey
0x14000bf2e  mov     rcx, rdi; hKey
0x14000bf31  call    cs:__imp_RegOpenKeyExW
0x14000bf37  test    eax, eax
0x14000bf39  jnz     short loc_14000BF58
0x14000bf3b  mov     eax, r15d
0x14000bf3e  test    rsi, rsi
0x14000bf41  jz      short loc_14000BF4C
0x14000bf43  mov     rcx, rsi; hKey
0x14000bf46  call    cs:__imp_RegCloseKey
0x14000bf4c  mov     rsi, [rbp+2D0h+var_2C8]
0x14000bf50  mov     [rbp+2D0h+var_280], rsi
0x14000bf54  test    eax, eax
0x14000bf56  jz      short loc_14000BFBF
0x14000bf58  lea     rax, [rbp+2D0h+dwDisposition]
0x14000bf5c  mov     [rbp+2D0h+dwDisposition], r15d
0x14000bf60  mov     [rsp+330h+lpdwDisposition], rax; lpdwDisposition
0x14000bf65  xor     r9d, r9d; lpClass
0x14000bf68  lea     rax, [rbp+2D0h+var_2C8]
0x14000bf6c  mov     [rbp+2D0h+var_2C8], r15
0x14000bf70  mov     [rsp+330h+var_2F8], rax; phkResult
0x14000bf75  xor     r8d, r8d; Reserved
0x14000bf78  mov     [rsp+330h+lpSecurityAttributes], r15; lpSecurityAttributes
0x14000bf7d  mov     rdx, r14; lpSubKey
0x14000bf80  mov     [rsp+330h+samDesired], 2001Fh; samDesired
0x14000bf88  mov     rcx, rdi; hKey
0x14000bf8b  mov     dword ptr [rsp+330h+phkResult], r15d; dwOptions
0x14000bf90  call    cs:__imp_RegCreateKeyExW
0x14000bf96  test    eax, eax
0x14000bf98  jnz     loc_14000C4AF
0x14000bf9e  mov     eax, r15d
0x14000bfa1  test    rsi, rsi
0x14000bfa4  jz      short loc_14000BFAF
0x14000bfa6  mov     rcx, rsi; hKey
0x14000bfa9  call    cs:__imp_RegCloseKey
0x14000bfaf  mov     rsi, [rbp+2D0h+var_2C8]
0x14000bfb3  mov     [rbp+2D0h+var_280], rsi
0x14000bfb7  test    eax, eax
0x14000bfb9  jnz     loc_14000C4AF
0x14000bfbf  movzx   eax, word ptr [r14]
0x14000bfc3  mov     ecx, 0FFDFh
0x14000bfc8  sub     ax, 4Ch ; 'L'
0x14000bfcc  test    cx, ax
0x14000bfcf  jnz     short loc_14000BFF0
0x14000bfd1  lea     rdx, aLocalserver32; "LocalServer32"
0x14000bfd8  mov     rcx, r14; lpString1
0x14000bfdb  call    cs:__imp_lstrcmpiW
0x14000bfe1  test    eax, eax
0x14000bfe3  movzx   r15d, r15b
0x14000bfe7  mov     eax, 1
0x14000bfec  cmovz   r15d, eax
0x14000bff0  mov     rdx, r14; unsigned __int16 *
0x14000bff3  mov     rcx, r12; this
0x14000bff6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000bffb  xor     ecx, ecx
0x14000bffd  mov     edi, eax
0x14000bfff  test    eax, eax
0x14000c001  js      loc_14000C3EC
0x14000c007  cmp     word ptr [r14], 3Dh ; '='
0x14000c00c  jnz     short loc_14000C031
0x14000c00e  mov     r9, r14; unsigned __int16 *
0x14000c011  mov     byte ptr [rsp+330h+phkResult], r15b; bool
0x14000c016  xor     r8d, r8d; unsigned __int16 *
0x14000c019  lea     rdx, [rbp+2D0h+var_280]; struct ATL::CRegKey *
0x14000c01d  mov     rcx, r12; this
0x14000c020  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)
0x14000c025  xor     ecx, ecx
0x14000c027  mov     edi, eax
0x14000c029  test    eax, eax
0x14000c02b  js      loc_14000C3EC
0x14000c031  mov     r15d, [rbp+2D0h+var_2C0]
0x14000c035  cmp     word ptr [r14], 7Bh ; '{'
0x14000c03a  jnz     loc_14000C3E1
0x14000c040  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000c044  inc     rax
0x14000c047  cmp     [r14+rax*2], cx
0x14000c04c  jnz     short loc_14000C044
0x14000c04e  cmp     rax, 1
0x14000c052  jnz     loc_14000C3E1
0x14000c058  mov     r9d, r15d; int
  ... truncated ...
```
