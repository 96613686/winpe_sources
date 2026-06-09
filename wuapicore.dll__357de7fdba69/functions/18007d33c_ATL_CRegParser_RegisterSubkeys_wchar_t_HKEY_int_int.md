# ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)

- ea: `0x18007d33c`
- end: `0x18007da82`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z`
- size: `1862`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18007d33c`
- `0x18007da88`

## callees

- `0x180004d50`
- `0x18007c60c`
- `0x18007c71c`
- `0x18007cd4c`
- `0x18007ce08`
- `0x18007cf08`
- `0x18007d06c`
- `0x18007d17c`
- `0x18007d190`
- `0x18007d33c`
- `0x18009b00c`
- `0x18009b050`
- `0x1800a18f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18007d5b1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18007d5b1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007d905`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007d99b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007d905`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007d99b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d5ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d6c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d6ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d9ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007da45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d5ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d6c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d6ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d9ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007da45`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007d6aa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007d6aa`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007d41e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007d5ee`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007d41e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007d5ee`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007d3bd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007d3cf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007d447`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007d4b6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007d4e4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007d924`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007d3bd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007d3cf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007d447`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007d4b6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007d4e4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007d924`

## string_xrefs

- `0x18007d3c5`: `ForceRemove`
- `0x18007d4ac`: `NoRemove`
- `0x18007d3b3`: `Delete`
- `0x18007d455`: `RegOpenKeyTransactedW`
- `0x18007d936`: `RegOpenKeyTransactedW`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(ATL::CRegParser *this, wchar_t *a2, HKEY a3, int a4, int a5)
{
  HKEY v5; // r14
  wchar_t *v6; // rdi
  ATL::CRegParser *v7; // r12
  HKEY v8; // r15
  int Token; // eax
  int v10; // ebx
  int v11; // r13d
  int v12; // esi
  LPWSTR v13; // rcx
  WCHAR i; // ax
  LPCWSTR *v15; // rbx
  int v16; // esi
  int v17; // eax
  unsigned int v18; // eax
  HKEY v19; // rsi
  LSTATUS v20; // eax
  LPWSTR v21; // rcx
  WCHAR j; // ax
  unsigned int v23; // r9d
  LSTATUS v24; // eax
  unsigned int v25; // ecx
  __int64 v27; // rax
  int v28; // esi
  int v29; // r14d
  int v30; // eax
  __int64 v31; // rax
  LPCWSTR *v32; // rsi
  int v33; // esi
  HKEY v34; // rcx
  wchar_t *dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int samDesired; // [rsp+28h] [rbp-D8h]
  unsigned int lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  struct _SECURITY_ATTRIBUTES *phkResult; // [rsp+38h] [rbp-C8h]
  HKEY hKey[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v42; // [rsp+80h] [rbp-80h]
  HKEY v43[2]; // [rsp+88h] [rbp-78h] BYREF
  ATL::CAtlTransactionManager *v44; // [rsp+98h] [rbp-68h]
  HKEY v45; // [rsp+A0h] [rbp-60h] BYREF
  DWORD dwDisposition; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR String1[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR ValueName[4096]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v5 = a3;
  v6 = a2;
  v7 = this;
  v8 = 0;
  v43[0] = 0;
  v43[1] = 0;
  v44 = 0;
  while ( 1 )
  {
    Token = ATL::CRegParser::NextToken(this, a2);
LABEL_3:
    v10 = Token;
    if ( Token < 0 )
      break;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v6 == 125 )
          goto LABEL_58;
        v11 = 1;
        v12 = lstrcmpiW(v6, L"Delete");
        if ( !lstrcmpiW(v6, L"ForceRemove") || !v12 )
        {
          v10 = ATL::CRegParser::NextToken(v7, v6);
          if ( v10 < 0 )
            goto LABEL_58;
          if ( a4 )
          {
            hKey[1] = 0;
            hKey[0] = 0;
            v42 = 0;
            v13 = v6;
            for ( i = *v6; i; i = *v13 )
            {
              if ( i == 92 )
              {
                if ( v13 )
                  goto LABEL_118;
                break;
              }
              v13 = CharNextW(v13);
            }
            v15 = (LPCWSTR *)&ATL::CRegParser::rgszNeverDelete;
            while ( lstrcmpiW(v6, *v15) )
            {
              if ( (__int64)++v15 >= (__int64)"RegOpenKeyTransactedW" )
              {
                hKey[0] = v5;
                ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, v6);
                break;
              }
            }
            if ( !v12 )
            {
              v10 = ATL::CRegParser::NextToken(v7, v6);
              if ( v10 < 0 )
                goto LABEL_58;
              v10 = ATL::CRegParser::SkipAssignment(v7, v6);
              if ( v10 < 0 )
                goto LABEL_58;
              v16 = a4;
              goto LABEL_66;
            }
          }
        }
        if ( !lstrcmpiW(v6, L"NoRemove") )
        {
          v11 = 0;
          v10 = ATL::CRegParser::NextToken(v7, v6);
          if ( v10 < 0 )
            goto LABEL_58;
        }
        if ( !lstrcmpiW(v6, L"Val") )
        {
          v10 = ATL::CRegParser::NextToken(v7, ValueName);
          if ( v10 < 0 )
            goto LABEL_58;
          v10 = ATL::CRegParser::NextToken(v7, v6);
          if ( v10 < 0 )
            goto LABEL_58;
          if ( *v6 != 61 )
          {
LABEL_118:
            v10 = -2147352567;
            goto LABEL_58;
          }
          v16 = a4;
          if ( !a4 )
          {
            if ( !a5 && v11 )
            {
              hKey[1] = 0;
              hKey[0] = 0;
              v42 = 0;
              v18 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, v5, 0, 0x20006u);
              if ( v18 )
              {
                v10 = ATL::AtlHresultFromWin32(v18);
                v34 = hKey[0];
                if ( !hKey[0] )
                  goto LABEL_58;
              }
              else
              {
                v19 = hKey[0];
                v20 = RegDeleteValueW(hKey[0], ValueName);
                if ( (v20 & 0xFFFFFFFD) == 0 )
                {
                  if ( v19 )
                    RegCloseKey(v19);
                  goto LABEL_37;
                }
                v10 = ATL::AtlHresultFromWin32(v20);
                if ( !v19 )
                  goto LABEL_58;
                v34 = v19;
              }
              RegCloseKey(v34);
              goto LABEL_58;
            }
LABEL_37:
            Token = ATL::CRegParser::SkipAssignment(v7, v6);
            goto LABEL_3;
          }
          hKey[0] = v5;
          hKey[1] = 0;
          v42 = 0;
          v17 = ATL::CRegParser::AddValue(v7, (struct ATL::CRegKey *)hKey, ValueName, v6);
          v10 = v17;
          goto LABEL_65;
        }
        v21 = v6;
        for ( j = *v6; j; j = *v21 )
        {
          if ( j == 92 )
          {
            if ( v21 )
              goto LABEL_118;
            break;
          }
          v21 = CharNextW(v21);
        }
        v16 = a4;
        if ( a4 )
          break;
        if ( a5 )
        {
          v28 = 2;
        }
        else
        {
          v28 = ATL::CRegKey::Open((ATL::CRegKey *)v43, v5, v6, 0x20019u);
          v8 = v43[0];
        }
        v29 = 1;
        if ( !v28 )
          v29 = a5;
        v30 = o_wcsncpy_s_0(String1, 260, v6, -1);
        if ( v30 )
        {
          if ( v30 == 12 )
            ATL::AtlThrowImpl(-2147024882);
          if ( v30 == 22 || v30 == 34 )
            ATL::AtlThrowImpl(-2147024809);
          if ( v30 != 80 )
            ATL::AtlThrowImpl(-2147467259);
        }
        v10 = ATL::CRegParser::NextToken(v7, v6);
        if ( v10 < 0 )
          goto LABEL_58;
        v10 = ATL::CRegParser::SkipAssignment(v7, v6);
        if ( v10 < 0 )
          goto LABEL_58;
        if ( *v6 == 123 )
        {
          v31 = -1;
          do
            ++v31;
          while ( v6[v31] );
          if ( v31 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v7, v6, v8, 0, v29);
            if ( v10 < 0 && !v29 )
              goto LABEL_58;
            v10 = ATL::CRegParser::NextToken(v7, v6);
            if ( v10 < 0 )
              goto LABEL_58;
          }
        }
        if ( v28 == 2 )
          goto LABEL_94;
        if ( v28 )
        {
          if ( !a5 )
          {
            v25 = v28;
            goto LABEL_57;
          }
          goto LABEL_94;
        }
        if ( a5 )
        {
          dwDisposition = 0;
          if ( !RegQueryInfoKeyW(v8, 0, 0, 0, &dwDisposition, 0, 0, 0, 0, 0, 0, 0) )
          {
            if ( dwDisposition )
            {
              v32 = (LPCWSTR *)&ATL::CRegParser::rgszNeverDelete;
              while ( lstrcmpiW(String1, *v32) )
              {
                if ( (__int64)++v32 >= (__int64)"RegOpenKeyTransactedW" )
                {
                  if ( v11 )
                  {
                    ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v43, String1);
                    v8 = v43[0];
                  }
                  goto LABEL_94;
                }
              }
              goto LABEL_94;
            }
          }
        }
        dwDisposition = 0;
        v33 = 0;
        if ( !RegQueryInfoKeyW(v8, 0, 0, 0, &dwDisposition, 0, 0, 0, 0, 0, 0, 0) )
          LOBYTE(v33) = dwDisposition != 0;
        v24 = 0;
        if ( v8 )
        {
          v24 = RegCloseKey(v8);
          v8 = 0;
          v43[0] = 0;
        }
        LODWORD(v43[1]) = 0;
        if ( v24 )
        {
LABEL_56:
          v25 = v24;
LABEL_57:
          v10 = ATL::AtlHresultFromWin32(v25);
          goto LABEL_58;
        }
        if ( v11 )
        {
          v5 = a3;
          if ( !v33 )
          {
            hKey[1] = 0;
            hKey[0] = a3;
            v42 = 0;
            v24 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)hKey, String1);
            if ( v24 )
              goto LABEL_56;
          }
        }
        else
        {
LABEL_94:
          v5 = a3;
        }
      }
      if ( ATL::CRegKey::Open((ATL::CRegKey *)v43, v5, v6, 0x2001Fu)
        && ATL::CRegKey::Open((ATL::CRegKey *)v43, v5, v6, 0x20019u) )
      {
        dwDisposition = 0;
        v45 = 0;
        if ( v44 )
          v24 = ATL::CAtlTransactionManager::RegCreateKeyExW(
                  v44,
                  v5,
                  v6,
                  v23,
                  dwOptions,
                  samDesired,
                  lpSecurityAttributes,
                  phkResult,
                  &v45,
                  &dwDisposition);
        else
          v24 = RegCreateKeyExW(v5, v6, 0, 0, 0, 0x2001Fu, 0, &v45, &dwDisposition);
        if ( v24 )
        {
          v8 = v43[0];
        }
        else
        {
          v24 = 0;
          if ( v43[0] )
            v24 = RegCloseKey(v43[0]);
          v8 = v45;
          v43[0] = v45;
          LODWORD(v43[1]) = 0;
        }
        if ( v24 )
          goto LABEL_56;
      }
      else
      {
        v8 = v43[0];
      }
      v10 = ATL::CRegParser::NextToken(v7, v6);
      if ( v10 < 0 )
        goto LABEL_58;
      if ( *v6 == 61 )
      {
        v17 = ATL::CRegParser::AddValue(v7, (struct ATL::CRegKey *)v43, 0, v6);
        v10 = v17;
        v8 = v43[0];
LABEL_65:
        if ( v17 < 0 )
          goto LABEL_58;
      }
LABEL_66:
      if ( *v6 == 123 )
      {
        v27 = -1;
        do
          ++v27;
        while ( v6[v27] );
        if ( v27 == 1 )
          break;
      }
    }
    v10 = ATL::CRegParser::RegisterSubkeys(v7, v6, v8, v16, 0);
    if ( v10 < 0 )
      break;
    a2 = v6;
    this = v7;
  }
LABEL_58:
  if ( v8 )
    RegCloseKey(v8);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18007d33c  push    rbp
0x18007d33e  push    rbx
0x18007d33f  push    rsi
0x18007d340  push    rdi
0x18007d341  push    r12
0x18007d343  push    r13
0x18007d345  push    r14
0x18007d347  push    r15
0x18007d349  lea     rbp, [rsp-21D8h]
0x18007d351  mov     eax, 22D8h
0x18007d356  call    _alloca_probe
0x18007d35b  sub     rsp, rax
0x18007d35e  mov     rax, cs:__security_cookie
0x18007d365  xor     rax, rsp
0x18007d368  mov     [rbp+2210h+var_50], rax
0x18007d36f  mov     [rsp+2310h+var_22B0], r9d
0x18007d374  mov     r14, r8
0x18007d377  mov     [rsp+2310h+var_22A8], r8
0x18007d37c  mov     rdi, rdx
0x18007d37f  mov     r12, rcx
0x18007d382  xorps   xmm0, xmm0
0x18007d385  xor     eax, eax
0x18007d387  movups  xmmword ptr [rbp+2210h+var_2288], xmm0
0x18007d38b  mov     r15d, eax
0x18007d38e  mov     [rbp+2210h+var_2288], rax
0x18007d392  mov     dword ptr [rbp+2210h+var_2288+8], eax
0x18007d395  mov     [rbp+2210h+var_2278], rax
0x18007d399  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18007d39e  mov     ebx, eax
0x18007d3a0  test    eax, eax
0x18007d3a2  js      loc_18007D6E7
0x18007d3a8  jmp     loc_18007D8B0
0x18007d3ad  mov     r13d, 1
0x18007d3b3  lea     rdx, aDelete; "Delete"
0x18007d3ba  mov     rcx, rdi; lpString1
0x18007d3bd  call    cs:__imp_lstrcmpiW
0x18007d3c3  mov     esi, eax
0x18007d3c5  lea     rdx, aForceremove; "ForceRemove"
0x18007d3cc  mov     rcx, rdi; lpString1
0x18007d3cf  call    cs:__imp_lstrcmpiW
0x18007d3d5  test    eax, eax
0x18007d3d7  jz      short loc_18007D3E1
0x18007d3d9  test    esi, esi
0x18007d3db  jnz     loc_18007D4AC
0x18007d3e1  mov     rdx, rdi; wchar_t *
0x18007d3e4  mov     rcx, r12; this
0x18007d3e7  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18007d3ec  mov     ebx, eax
0x18007d3ee  xor     edx, edx
0x18007d3f0  test    eax, eax
0x18007d3f2  js      loc_18007D6E7
0x18007d3f8  cmp     [rsp+2310h+var_22B0], edx
0x18007d3fc  jz      loc_18007D4AC
0x18007d402  mov     [rsp+2310h+hKey+8], rdx
0x18007d407  mov     [rsp+2310h+hKey], rdx
0x18007d40c  mov     [rbp+2210h+var_2290], rdx
0x18007d410  mov     rcx, rdi
0x18007d413  movzx   eax, word ptr [rdi]
0x18007d416  jmp     short loc_18007D42A
0x18007d418  cmp     ax, 5Ch ; '\'
0x18007d41c  jz      short loc_18007D431
0x18007d41e  call    cs:__imp_CharNextW
0x18007d424  mov     rcx, rax; lpsz
0x18007d427  movzx   eax, word ptr [rax]
0x18007d42a  test    ax, ax
0x18007d42d  jnz     short loc_18007D418
0x18007d42f  jmp     short loc_18007D43A
0x18007d431  test    rcx, rcx
0x18007d434  jnz     loc_18007DA50
0x18007d43a  lea     rbx, ?rgszNeverDelete@CRegParser@ATL@@1QBQEB_WB; wchar_t const * const near * const ATL::CRegParser::rgszNeverDelete
0x18007d441  mov     rdx, [rbx]; lpString2
0x18007d444  mov     rcx, rdi; lpString1
0x18007d447  call    cs:__imp_lstrcmpiW
0x18007d44d  test    eax, eax
0x18007d44f  jz      short loc_18007D473
0x18007d451  add     rbx, 8
0x18007d455  lea     rax, aRegopenkeytran; "RegOpenKeyTransactedW"
0x18007d45c  cmp     rbx, rax
0x18007d45f  jl      short loc_18007D441
0x18007d461  mov     [rsp+2310h+hKey], r14
0x18007d466  mov     rdx, rdi; wchar_t *
0x18007d469  lea     rcx, [rsp+2310h+hKey]; this
0x18007d46e  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x18007d473  test    esi, esi
0x18007d475  jnz     short loc_18007D4AC
0x18007d477  mov     rdx, rdi; wchar_t *
0x18007d47a  mov     rcx, r12; this
0x18007d47d  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18007d482  mov     ebx, eax
0x18007d484  test    eax, eax
0x18007d486  js      loc_18007D6E7
0x18007d48c  mov     rdx, rdi; wchar_t *
0x18007d48f  mov     rcx, r12; this
0x18007d492  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x18007d497  mov     ebx, eax
0x18007d499  xor     edx, edx
0x18007d49b  test    eax, eax
0x18007d49d  js      loc_18007D6E7
0x18007d4a3  mov     esi, [rsp+2310h+var_22B0]
0x18007d4a7  jmp     loc_18007D755
0x18007d4ac  lea     rdx, aNoremove; "NoRemove"
0x18007d4b3  mov     rcx, rdi; lpString1
0x18007d4b6  call    cs:__imp_lstrcmpiW
0x18007d4bc  xor     ecx, ecx
0x18007d4be  test    eax, eax
0x18007d4c0  jnz     short loc_18007D4DA
0x18007d4c2  mov     r13d, ecx
0x18007d4c5  mov     rdx, rdi; wchar_t *
0x18007d4c8  mov     rcx, r12; this
0x18007d4cb  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18007d4d0  mov     ebx, eax
0x18007d4d2  test    eax, eax
0x18007d4d4  js      loc_18007D6E7
0x18007d4da  lea     rdx, aVal; "Val"
0x18007d4e1  mov     rcx, rdi; lpString1
0x18007d4e4  call    cs:__imp_lstrcmpiW
0x18007d4ea  test    eax, eax
0x18007d4ec  jnz     loc_18007D5E0
0x18007d4f2  lea     rdx, [rbp+2210h+ValueName]; wchar_t *
0x18007d4f9  mov     rcx, r12; this
0x18007d4fc  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18007d501  mov     ebx, eax
0x18007d503  test    eax, eax
0x18007d505  js      loc_18007D6E7
0x18007d50b  mov     rdx, rdi; wchar_t *
0x18007d50e  mov     rcx, r12; this
0x18007d511  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18007d516  mov     ebx, eax
0x18007d518  xor     edx, edx
0x18007d51a  test    eax, eax
0x18007d51c  js      loc_18007D6E7
0x18007d522  cmp     word ptr [rdi], 3Dh ; '='
0x18007d526  jnz     loc_18007DA50
0x18007d52c  mov     esi, [rsp+2310h+var_22B0]
0x18007d530  test    esi, esi
0x18007d532  jz      short loc_18007D569
0x18007d534  xorps   xmm0, xmm0
0x18007d537  movups  xmmword ptr [rsp+2310h+hKey], xmm0
0x18007d53c  mov     [rsp+2310h+hKey], r14
0x18007d541  mov     dword ptr [rsp+2310h+hKey+8], edx
0x18007d545  mov     [rbp+2210h+var_2290], rdx
0x18007d549  mov     r9, rdi; wchar_t *
0x18007d54c  lea     r8, [rbp+2210h+ValueName]; wchar_t *
0x18007d553  lea     rdx, [rsp+2310h+hKey]; struct ATL::CRegKey *
0x18007d558  mov     rcx, r12; this
0x18007d55b  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x18007d560  mov     ebx, eax
0x18007d562  xor     edx, edx
0x18007d564  jmp     loc_18007D751
0x18007d569  cmp     [rbp+2210h+arg_20], edx
0x18007d56f  jnz     short loc_18007D5D0
0x18007d571  test    r13d, r13d
0x18007d574  jz      short loc_18007D5D0
0x18007d576  mov     [rsp+2310h+hKey+8], rdx
0x18007d57b  mov     [rsp+2310h+hKey], rdx
0x18007d580  mov     [rbp+2210h+var_2290], rdx
0x18007d584  mov     r9d, 20006h; unsigned int
0x18007d58a  xor     r8d, r8d; wchar_t *
0x18007d58d  mov     rdx, r14; HKEY
0x18007d590  lea     rcx, [rsp+2310h+hKey]; this
0x18007d595  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18007d59a  test    eax, eax
0x18007d59c  jnz     loc_18007DA2E
0x18007d5a2  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x18007d5a9  mov     rsi, [rsp+2310h+hKey]
0x18007d5ae  mov     rcx, rsi; hKey
0x18007d5b1  call    cs:__imp_RegDeleteValueW
0x18007d5b7  test    eax, 0FFFFFFFDh
0x18007d5bc  jnz     loc_18007DA17
0x18007d5c2  test    rsi, rsi
0x18007d5c5  jz      short loc_18007D5D0
0x18007d5c7  mov     rcx, rsi; hKey
0x18007d5ca  call    cs:__imp_RegCloseKey
0x18007d5d0  mov     rdx, rdi; wchar_t *
0x18007d5d3  mov     rcx, r12; this
0x18007d5d6  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x18007d5db  jmp     loc_18007D39E
0x18007d5e0  mov     rcx, rdi
0x18007d5e3  movzx   eax, word ptr [rdi]
0x18007d5e6  jmp     short loc_18007D5FA
0x18007d5e8  cmp     ax, 5Ch ; '\'
0x18007d5ec  jz      short loc_18007D601
0x18007d5ee  call    cs:__imp_CharNextW
0x18007d5f4  mov     rcx, rax; lpsz
0x18007d5f7  movzx   eax, word ptr [rax]
0x18007d5fa  test    ax, ax
0x18007d5fd  jnz     short loc_18007D5E8
0x18007d5ff  jmp     short loc_18007D60A
0x18007d601  test    rcx, rcx
0x18007d604  jnz     loc_18007DA50
0x18007d60a  mov     esi, [rsp+2310h+var_22B0]
0x18007d60e  test    esi, esi
0x18007d610  jz      loc_18007D7A0
0x18007d616  mov     r15d, 2001Fh
0x18007d61c  mov     r9d, r15d; unsigned int
0x18007d61f  mov     r8, rdi; wchar_t *
0x18007d622  mov     rdx, r14; HKEY
0x18007d625  lea     rcx, [rbp+2210h+var_2288]; this
0x18007d629  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18007d62e  xor     ebx, ebx
0x18007d630  test    eax, eax
0x18007d632  jz      loc_18007D71A
0x18007d638  lea     r9d, [r15-6]; unsigned int
0x18007d63c  mov     r8, rdi; wchar_t *
0x18007d63f  mov     rdx, r14; HKEY
0x18007d642  lea     rcx, [rbp+2210h+var_2288]; this
0x18007d646  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18007d64b  test    eax, eax
0x18007d64d  jz      loc_18007D71A
0x18007d653  mov     [rbp+2210h+dwDisposition], ebx
0x18007d656  mov     [rbp+2210h+var_2270], rbx
0x18007d65a  mov     rcx, [rbp+2210h+var_2278]; this
0x18007d65e  lea     rax, [rbp+2210h+dwDisposition]
0x18007d662  test    rcx, rcx
0x18007d665  jz      short loc_18007D682
0x18007d667  mov     [rsp+2310h+lpcbMaxValueLen], rax; unsigned int *
0x18007d66c  lea     rax, [rbp+2210h+var_2270]
0x18007d670  mov     [rsp+2310h+lpdwDisposition], rax; HKEY *
0x18007d675  mov     r8, rdi; wchar_t *
0x18007d678  mov     rdx, r14; HKEY
0x18007d67b  call    ?RegCreateKeyExW@CAtlTransactionManager@ATL@@QEAAJPEAUHKEY__@@PEB_WKPEA_WKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU3@PEAK@Z; ATL::CAtlTransactionManager::RegCreateKeyExW(HKEY__ *,wchar_t const *,ulong,wchar_t *,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)
0x18007d680  jmp     short loc_18007D6B0
0x18007d682  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x18007d687  lea     rax, [rbp+2210h+var_2270]
0x18007d68b  mov     [rsp+2310h+phkResult], rax; phkResult
0x18007d690  mov     [rsp+2310h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18007d695  mov     [rsp+2310h+samDesired], r15d; samDesired
0x18007d69a  mov     [rsp+2310h+dwOptions], ebx; dwOptions
0x18007d69e  xor     r9d, r9d; lpClass
0x18007d6a1  xor     r8d, r8d; Reserved
0x18007d6a4  mov     rdx, rdi; lpSubKey
0x18007d6a7  mov     rcx, r14; hKey
0x18007d6aa  call    cs:__imp_RegCreateKeyExW
0x18007d6b0  xor     edx, edx
0x18007d6b2  test    eax, eax
0x18007d6b4  jnz     short loc_18007D6D6
0x18007d6b6  mov     eax, edx
0x18007d6b8  mov     rcx, [rbp+2210h+var_2288]; hKey
0x18007d6bc  test    rcx, rcx
0x18007d6bf  jz      short loc_18007D6C9
0x18007d6c1  call    cs:__imp_RegCloseKey
0x18007d6c7  xor     edx, edx
0x18007d6c9  mov     r15, [rbp+2210h+var_2270]
0x18007d6cd  mov     [rbp+2210h+var_2288], r15
0x18007d6d1  mov     dword ptr [rbp+2210h+var_2288+8], edx
0x18007d6d4  jmp     short loc_18007D6DA
0x18007d6d6  mov     r15, [rbp+2210h+var_2288]
0x18007d6da  test    eax, eax
0x18007d6dc  jz      short loc_18007D71E
0x18007d6de  mov     ecx, eax; unsigned int
0x18007d6e0  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18007d6e5  mov     ebx, eax
0x18007d6e7  test    r15, r15
0x18007d6ea  jz      short loc_18007D6F5
0x18007d6ec  mov     rcx, r15; hKey
0x18007d6ef  call    cs:__imp_RegCloseKey
0x18007d6f5  mov     eax, ebx
0x18007d6f7  mov     rcx, [rbp+2210h+var_50]
0x18007d6fe  xor     rcx, rsp; StackCookie
0x18007d701  call    __security_check_cookie
0x18007d706  add     rsp, 22D8h
0x18007d70d  pop     r15
0x18007d70f  pop     r14
0x18007d711  pop     r13
0x18007d713  pop     r12
0x18007d715  pop     rdi
0x18007d716  pop     rsi
0x18007d717  pop     rbx
0x18007d718  pop     rbp
0x18007d719  retn
0x18007d71a  mov     r15, [rbp+2210h+var_2288]
0x18007d71e  mov     rdx, rdi; wchar_t *
0x18007d721  mov     rcx, r12; this
0x18007d724  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18007d729  mov     ebx, eax
0x18007d72b  xor     edx, edx
0x18007d72d  test    eax, eax
0x18007d72f  js      short loc_18007D6E7
0x18007d731  cmp     word ptr [rdi], 3Dh ; '='
0x18007d735  jnz     short loc_18007D755
0x18007d737  mov     r9, rdi; wchar_t *
0x18007d73a  xor     r8d, r8d; wchar_t *
0x18007d73d  lea     rdx, [rbp+2210h+var_2288]; struct ATL::CRegKey *
0x18007d741  mov     rcx, r12; this
0x18007d744  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x18007d749  mov     ebx, eax
0x18007d74b  xor     edx, edx
0x18007d74d  mov     r15, [rbp+2210h+var_2288]
0x18007d751  test    eax, eax
0x18007d753  js      short loc_18007D6E7
0x18007d755  cmp     word ptr [rdi], 7Bh ; '{'
0x18007d759  jnz     loc_18007D8B0
0x18007d75f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007d763  inc     rax
0x18007d766  cmp     [rdi+rax*2], dx
0x18007d76a  jnz     short loc_18007D763
0x18007d76c  cmp     rax, 1
0x18007d770  jnz     loc_18007D8B0
0x18007d776  mov     [rsp+2310h+dwOptions], edx; int
0x18007d77a  mov     r9d, esi; int
  ... truncated ...
```
