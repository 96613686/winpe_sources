# ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)

- ea: `0x1800126ec`
- end: `0x180012e83`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(LPCWSTR *this, wchar_t *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180012378`
- `0x1800126ec`

## callees

- `0x1800020e0`
- `0x180010410`
- `0x180010c0c`
- `0x180011478`
- `0x180011958`
- `0x180011ca0`
- `0x180012228`
- `0x1800126ec`
- `0x1800130bc`
- `0x180014400`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180012bca`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180012bca`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800127ce`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180012999`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800127ce`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180012999`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180012cf6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180012d8c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180012cf6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180012d8c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180012a87`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180012a87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012932`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800129e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012a29`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012b78`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012932`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800129e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012a29`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012b78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012968`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800129f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012a3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012a9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012b93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012daa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012e04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012e40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012e50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012968`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800129f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012a3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012a9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012b93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012daa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012e04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012e40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012e50`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001294f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001294f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180012769`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001277c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800127fa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180012863`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180012891`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180012d19`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180012769`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001277c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800127fa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180012863`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180012891`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180012d19`

## string_xrefs

- `0x180012772`: `ForceRemove`
- `0x180012859`: `NoRemove`
- `0x18001275f`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(LPCWSTR *this, wchar_t *a2, HKEY a3, int a4, int a5)
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
  unsigned int v32; // ecx
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
0x1800126ec  push    rbp
0x1800126ee  push    rbx
0x1800126ef  push    rsi
0x1800126f0  push    rdi
0x1800126f1  push    r12
0x1800126f3  push    r13
0x1800126f5  push    r14
0x1800126f7  push    r15
0x1800126f9  lea     rbp, [rsp-21D8h]
0x180012701  mov     eax, 22D8h
0x180012706  call    _alloca_probe
0x18001270b  sub     rsp, rax
0x18001270e  mov     rax, cs:__security_cookie
0x180012715  xor     rax, rsp
0x180012718  mov     [rbp+2210h+var_50], rax
0x18001271f  mov     r12d, r9d
0x180012722  mov     [rsp+2310h+var_22A8], r9d
0x180012727  mov     r15, r8
0x18001272a  mov     [rsp+2310h+var_22A0], r8
0x18001272f  mov     rsi, rdx
0x180012732  mov     r13, rcx
0x180012735  xor     eax, eax
0x180012737  mov     ebx, eax
0x180012739  mov     [rbp+2210h+var_2290], rax
0x18001273d  mov     [rbp+2210h+var_2288], rax
0x180012741  mov     [rbp+2210h+var_2280], rax
0x180012745  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001274a  mov     edi, eax
0x18001274c  test    eax, eax
0x18001274e  jns     short loc_180012755
0x180012750  jmp     loc_180012E0C
0x180012755  cmp     word ptr [rsi], 7Dh ; '}'
0x180012759  jz      loc_180012DFC
0x18001275f  lea     rdx, String2; "Delete"
0x180012766  mov     rcx, rsi; lpString1
0x180012769  call    cs:__imp_lstrcmpiW
0x18001276f  mov     r14d, eax
0x180012772  lea     rdx, aForceremove; "ForceRemove"
0x180012779  mov     rcx, rsi; lpString1
0x18001277c  call    cs:__imp_lstrcmpiW
0x180012782  xor     edi, edi
0x180012784  test    eax, eax
0x180012786  jz      short loc_180012791
0x180012788  test    r14d, r14d
0x18001278b  jnz     loc_180012853
0x180012791  mov     rdx, rsi; wchar_t *
0x180012794  mov     rcx, r13; this
0x180012797  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001279c  mov     edi, eax
0x18001279e  test    eax, eax
0x1800127a0  js      loc_180012DFC
0x1800127a6  xor     edi, edi
0x1800127a8  test    r12d, r12d
0x1800127ab  jz      loc_180012853
0x1800127b1  mov     [rbp+2210h+var_2278], rdi
0x1800127b5  mov     [rbp+2210h+var_2270], rdi
0x1800127b9  mov     [rbp+2210h+var_2268], rdi
0x1800127bd  movzx   eax, word ptr [rsi]
0x1800127c0  test    ax, ax
0x1800127c3  jz      short loc_1800127EA
0x1800127c5  mov     rcx, rsi; lpsz
0x1800127c8  cmp     ax, 5Ch ; '\'
0x1800127cc  jz      short loc_1800127E1
0x1800127ce  call    cs:__imp_CharNextW
0x1800127d4  mov     rcx, rax
0x1800127d7  movzx   eax, word ptr [rax]
0x1800127da  test    ax, ax
0x1800127dd  jnz     short loc_1800127C8
0x1800127df  jmp     short loc_1800127EA
0x1800127e1  test    rcx, rcx
0x1800127e4  jnz     loc_180012E48
0x1800127ea  mov     edx, edi
0x1800127ec  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEB_WB; wchar_t const * const near * const ATL::CRegParser::rgszNeverDelete
0x1800127f3  mov     rdx, [rax+rdx*8]; lpString2
0x1800127f7  mov     rcx, rsi; lpString1
0x1800127fa  call    cs:__imp_lstrcmpiW
0x180012800  test    eax, eax
0x180012802  jz      short loc_18001281B
0x180012804  inc     edi
0x180012806  cmp     edi, 0Ch
0x180012809  jl      short loc_1800127EA
0x18001280b  mov     [rbp+2210h+var_2278], r15
0x18001280f  mov     rdx, rsi; wchar_t *
0x180012812  lea     rcx, [rbp+2210h+var_2278]; this
0x180012816  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x18001281b  xor     edi, edi
0x18001281d  test    r14d, r14d
0x180012820  jnz     short loc_180012853
0x180012822  mov     rdx, rsi; wchar_t *
0x180012825  mov     rcx, r13; this
0x180012828  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001282d  mov     edi, eax
0x18001282f  test    eax, eax
0x180012831  js      loc_180012DFC
0x180012837  mov     rdx, rsi; wchar_t *
0x18001283a  mov     rcx, r13; this
0x18001283d  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x180012842  mov     edi, eax
0x180012844  xor     ecx, ecx
0x180012846  test    eax, eax
0x180012848  js      loc_180012DFC
0x18001284e  jmp     loc_180012AFA
0x180012853  mov     r12d, 1
0x180012859  lea     rdx, aNoremove; "NoRemove"
0x180012860  mov     rcx, rsi; lpString1
0x180012863  call    cs:__imp_lstrcmpiW
0x180012869  test    eax, eax
0x18001286b  jnz     short loc_180012887
0x18001286d  mov     r12d, edi
0x180012870  mov     rdx, rsi; wchar_t *
0x180012873  mov     rcx, r13; this
0x180012876  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001287b  mov     edi, eax
0x18001287d  test    eax, eax
0x18001287f  js      loc_180012DFC
0x180012885  xor     edi, edi
0x180012887  lea     rdx, aVal; "Val"
0x18001288e  mov     rcx, rsi; lpString1
0x180012891  call    cs:__imp_lstrcmpiW
0x180012897  test    eax, eax
0x180012899  jnz     loc_180012988
0x18001289f  lea     rdx, [rbp+2210h+ValueName]; wchar_t *
0x1800128a6  mov     rcx, r13; this
0x1800128a9  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800128ae  mov     edi, eax
0x1800128b0  test    eax, eax
0x1800128b2  js      loc_180012DFC
0x1800128b8  mov     rdx, rsi; wchar_t *
0x1800128bb  mov     rcx, r13; this
0x1800128be  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800128c3  mov     edi, eax
0x1800128c5  test    eax, eax
0x1800128c7  js      loc_180012DFC
0x1800128cd  cmp     word ptr [rsi], 3Dh ; '='
0x1800128d1  jnz     loc_180012E48
0x1800128d7  xor     edi, edi
0x1800128d9  cmp     [rsp+2310h+var_22A8], edi
0x1800128dd  jz      short loc_180012908
0x1800128df  mov     [rbp+2210h+var_2270], rdi
0x1800128e3  mov     [rbp+2210h+var_2268], rdi
0x1800128e7  mov     [rbp+2210h+var_2278], r15
0x1800128eb  mov     r9, rsi; wchar_t *
0x1800128ee  lea     r8, [rbp+2210h+ValueName]; wchar_t *
0x1800128f5  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x1800128f9  mov     rcx, r13; this
0x1800128fc  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x180012901  mov     edi, eax
0x180012903  jmp     loc_180012AEB
0x180012908  cmp     [rbp+2210h+arg_20], edi
0x18001290e  jnz     short loc_18001296E
0x180012910  test    r12d, r12d
0x180012913  jz      short loc_18001296E
0x180012915  mov     [rsp+2310h+hKey], rdi
0x18001291a  lea     rax, [rsp+2310h+hKey]
0x18001291f  mov     [rsp+2310h+phkResult], rax; phkResult
0x180012924  mov     r9d, 20006h; samDesired
0x18001292a  xor     r8d, r8d; ulOptions
0x18001292d  xor     edx, edx; lpSubKey
0x18001292f  mov     rcx, r15; hKey
0x180012932  call    cs:__imp_RegOpenKeyExW
0x180012938  test    eax, eax
0x18001293a  jnz     loc_180012DF3
0x180012940  mov     r14, [rsp+2310h+hKey]
0x180012945  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x18001294c  mov     rcx, r14; hKey
0x18001294f  call    cs:__imp_RegDeleteValueW
0x180012955  test    eax, 0FFFFFFFDh
0x18001295a  jnz     loc_180012E2F
0x180012960  test    r14, r14
0x180012963  jz      short loc_18001296E
0x180012965  mov     rcx, r14; hKey
0x180012968  call    cs:__imp_RegCloseKey
0x18001296e  mov     rdx, rsi; wchar_t *
0x180012971  mov     rcx, r13; this
0x180012974  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x180012979  mov     edi, eax
0x18001297b  test    eax, eax
0x18001297d  js      loc_180012DFC
0x180012983  jmp     loc_180012C95
0x180012988  movzx   eax, word ptr [rsi]
0x18001298b  test    ax, ax
0x18001298e  jz      short loc_1800129B5
0x180012990  mov     rcx, rsi; lpsz
0x180012993  cmp     ax, 5Ch ; '\'
0x180012997  jz      short loc_1800129AC
0x180012999  call    cs:__imp_CharNextW
0x18001299f  mov     rcx, rax
0x1800129a2  movzx   eax, word ptr [rax]
0x1800129a5  test    ax, ax
0x1800129a8  jnz     short loc_180012993
0x1800129aa  jmp     short loc_1800129B5
0x1800129ac  test    rcx, rcx
0x1800129af  jnz     loc_180012E48
0x1800129b5  cmp     [rsp+2310h+var_22A8], edi
0x1800129b9  jz      loc_180012B4E
0x1800129bf  mov     [rsp+2310h+hKey], rdi
0x1800129c4  lea     rax, [rsp+2310h+hKey]
0x1800129c9  mov     [rsp+2310h+phkResult], rax; phkResult
0x1800129ce  mov     r14d, 2001Fh
0x1800129d4  mov     r9d, r14d; samDesired
0x1800129d7  xor     r8d, r8d; ulOptions
0x1800129da  mov     rdx, rsi; lpSubKey
0x1800129dd  mov     rcx, r15; hKey
0x1800129e0  call    cs:__imp_RegOpenKeyExW
0x1800129e6  test    eax, eax
0x1800129e8  jnz     short loc_180012A0B
0x1800129ea  mov     eax, edi
0x1800129ec  test    rbx, rbx
0x1800129ef  jz      short loc_1800129FA
0x1800129f1  mov     rcx, rbx; hKey
0x1800129f4  call    cs:__imp_RegCloseKey
0x1800129fa  mov     rbx, [rsp+2310h+hKey]
0x1800129ff  mov     [rbp+2210h+var_2290], rbx
0x180012a03  test    eax, eax
0x180012a05  jz      loc_180012AB6
0x180012a0b  mov     [rsp+2310h+hKey], rdi
0x180012a10  lea     rax, [rsp+2310h+hKey]
0x180012a15  mov     [rsp+2310h+phkResult], rax; phkResult
0x180012a1a  mov     r9d, 20019h; samDesired
0x180012a20  xor     r8d, r8d; ulOptions
0x180012a23  mov     rdx, rsi; lpSubKey
0x180012a26  mov     rcx, r15; hKey
0x180012a29  call    cs:__imp_RegOpenKeyExW
0x180012a2f  test    eax, eax
0x180012a31  jnz     short loc_180012A50
0x180012a33  mov     eax, edi
0x180012a35  test    rbx, rbx
0x180012a38  jz      short loc_180012A43
0x180012a3a  mov     rcx, rbx; hKey
0x180012a3d  call    cs:__imp_RegCloseKey
0x180012a43  mov     rbx, [rsp+2310h+hKey]
0x180012a48  mov     [rbp+2210h+var_2290], rbx
0x180012a4c  test    eax, eax
0x180012a4e  jz      short loc_180012AB6
0x180012a50  mov     dword ptr [rsp+2310h+hKey], edi
0x180012a54  mov     [rsp+2310h+var_2298], rdi
0x180012a59  lea     rax, [rsp+2310h+hKey]
0x180012a5e  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180012a63  lea     rax, [rsp+2310h+var_2298]
0x180012a68  mov     [rsp+2310h+var_22D8], rax; phkResult
0x180012a6d  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180012a72  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180012a77  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x180012a7b  xor     r9d, r9d; lpClass
0x180012a7e  xor     r8d, r8d; Reserved
0x180012a81  mov     rdx, rsi; lpSubKey
0x180012a84  mov     rcx, r15; hKey
0x180012a87  call    cs:__imp_RegCreateKeyExW
0x180012a8d  test    eax, eax
0x180012a8f  jnz     loc_180012DF3
0x180012a95  mov     eax, edi
0x180012a97  test    rbx, rbx
0x180012a9a  jz      short loc_180012AA5
0x180012a9c  mov     rcx, rbx; hKey
0x180012a9f  call    cs:__imp_RegCloseKey
0x180012aa5  mov     rbx, [rsp+2310h+var_2298]
0x180012aaa  mov     [rbp+2210h+var_2290], rbx
0x180012aae  test    eax, eax
0x180012ab0  jnz     loc_180012DF3
0x180012ab6  mov     rdx, rsi; wchar_t *
0x180012ab9  mov     rcx, r13; this
0x180012abc  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180012ac1  mov     edi, eax
0x180012ac3  xor     ecx, ecx
0x180012ac5  test    eax, eax
0x180012ac7  js      loc_180012DFC
0x180012acd  cmp     word ptr [rsi], 3Dh ; '='
0x180012ad1  jnz     short loc_180012AF5
0x180012ad3  mov     r9, rsi; wchar_t *
0x180012ad6  xor     r8d, r8d; wchar_t *
0x180012ad9  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x180012add  mov     rcx, r13; this
0x180012ae0  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x180012ae5  mov     edi, eax
0x180012ae7  mov     rbx, [rbp+2210h+var_2290]
0x180012aeb  test    eax, eax
0x180012aed  js      loc_180012DFC
0x180012af3  xor     ecx, ecx
0x180012af5  mov     r12d, [rsp+2310h+var_22A8]
0x180012afa  cmp     word ptr [rsi], 7Bh ; '{'
0x180012afe  jnz     loc_180012C95
0x180012b04  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012b08  inc     rax
0x180012b0b  cmp     [rsi+rax*2], cx
0x180012b0f  jnz     short loc_180012B08
0x180012b11  cmp     rax, 1
0x180012b15  jnz     loc_180012C95
0x180012b1b  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x180012b23  mov     r9d, r12d; int
0x180012b26  mov     r8, rbx; HKEY
0x180012b29  mov     rdx, rsi; wchar_t *
0x180012b2c  mov     rcx, r13; this
0x180012b2f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x180012b34  mov     edi, eax
0x180012b36  test    eax, eax
0x180012b38  js      loc_180012DFC
0x180012b3e  mov     rdx, rsi; wchar_t *
0x180012b41  mov     rcx, r13; this
0x180012b44  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180012b49  jmp     loc_180012979
  ... truncated ...
```
