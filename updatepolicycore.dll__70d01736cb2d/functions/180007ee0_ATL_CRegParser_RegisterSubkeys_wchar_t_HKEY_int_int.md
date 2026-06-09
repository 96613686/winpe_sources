# ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)

- ea: `0x180007ee0`
- end: `0x180008626`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z`
- size: `1862`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180007ee0`
- `0x18000862c`

## callees

- `0x18000714c`
- `0x18000728c`
- `0x1800078c8`
- `0x1800078f0`
- `0x1800079ac`
- `0x180007aac`
- `0x180007c10`
- `0x180007d20`
- `0x180007d34`
- `0x180007ee0`
- `0x18002ffa4`
- `0x18002ffd0`
- `0x1800369a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180008155`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180008155`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000824e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000824e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800084a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000853f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800084a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000853f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000816e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008265`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008293`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000855e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800085e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000816e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008265`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008293`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000855e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800085e9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007fc2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008192`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007fc2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008192`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007f61`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007f73`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007feb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000805a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008088`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800084c8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007f61`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007f73`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007feb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000805a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008088`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800084c8`

## string_xrefs

- `0x180007f57`: `Delete`
- `0x180007f69`: `ForceRemove`
- `0x180008050`: `NoRemove`
- `0x180007ff9`: `RegOpenKeyTransactedW`
- `0x1800084da`: `RegOpenKeyTransactedW`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(LPCWSTR *this, wchar_t *a2, HKEY a3, int a4, int a5)
{
  HKEY v5; // r14
  wchar_t *v6; // rdi
  LPCWSTR *v7; // r12
  HKEY v8; // r15
  int Token; // eax
  int v10; // ebx
  int v11; // r13d
  int v12; // esi
  LPWSTR v13; // rcx
  WCHAR i; // ax
  LPCWSTR *v15; // rbx
  int v16; // esi
  HRESULT v17; // eax
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
              v10 = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)v7, v6);
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
            Token = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)v7, v6);
            goto LABEL_3;
          }
          hKey[0] = v5;
          hKey[1] = 0;
          v42 = 0;
          v17 = ATL::CRegParser::AddValue(v7, hKey, ValueName, v6);
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
        v10 = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)v7, v6);
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
            v10 = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)v7, v6, v8, 0, v29);
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
      if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v43, v5, v6, 0x2001Fu)
        && (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v43, v5, v6, 0x20019u) )
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
        v17 = ATL::CRegParser::AddValue(v7, v43, 0, v6);
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
    v10 = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)v7, v6, v8, v16, 0);
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
0x180007ee0  push    rbp
0x180007ee2  push    rbx
0x180007ee3  push    rsi
0x180007ee4  push    rdi
0x180007ee5  push    r12
0x180007ee7  push    r13
0x180007ee9  push    r14
0x180007eeb  push    r15
0x180007eed  lea     rbp, [rsp-21D8h]
0x180007ef5  mov     eax, 22D8h
0x180007efa  call    _alloca_probe
0x180007eff  sub     rsp, rax
0x180007f02  mov     rax, cs:__security_cookie
0x180007f09  xor     rax, rsp
0x180007f0c  mov     [rbp+2210h+var_50], rax
0x180007f13  mov     [rsp+2310h+var_22B0], r9d
0x180007f18  mov     r14, r8
0x180007f1b  mov     [rsp+2310h+var_22A8], r8
0x180007f20  mov     rdi, rdx
0x180007f23  mov     r12, rcx
0x180007f26  xorps   xmm0, xmm0
0x180007f29  xor     eax, eax
0x180007f2b  movups  xmmword ptr [rbp+2210h+var_2288], xmm0
0x180007f2f  mov     r15d, eax
0x180007f32  mov     [rbp+2210h+var_2288], rax
0x180007f36  mov     dword ptr [rbp+2210h+var_2288+8], eax
0x180007f39  mov     [rbp+2210h+var_2278], rax
0x180007f3d  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180007f42  mov     ebx, eax
0x180007f44  test    eax, eax
0x180007f46  js      loc_18000828B
0x180007f4c  jmp     loc_180008454
0x180007f51  mov     r13d, 1
0x180007f57  lea     rdx, aDelete; "Delete"
0x180007f5e  mov     rcx, rdi; lpString1
0x180007f61  call    cs:__imp_lstrcmpiW
0x180007f67  mov     esi, eax
0x180007f69  lea     rdx, aForceremove; "ForceRemove"
0x180007f70  mov     rcx, rdi; lpString1
0x180007f73  call    cs:__imp_lstrcmpiW
0x180007f79  test    eax, eax
0x180007f7b  jz      short loc_180007F85
0x180007f7d  test    esi, esi
0x180007f7f  jnz     loc_180008050
0x180007f85  mov     rdx, rdi; wchar_t *
0x180007f88  mov     rcx, r12; this
0x180007f8b  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180007f90  mov     ebx, eax
0x180007f92  xor     edx, edx
0x180007f94  test    eax, eax
0x180007f96  js      loc_18000828B
0x180007f9c  cmp     [rsp+2310h+var_22B0], edx
0x180007fa0  jz      loc_180008050
0x180007fa6  mov     [rsp+2310h+hKey+8], rdx
0x180007fab  mov     [rsp+2310h+hKey], rdx
0x180007fb0  mov     [rbp+2210h+var_2290], rdx
0x180007fb4  mov     rcx, rdi
0x180007fb7  movzx   eax, word ptr [rdi]
0x180007fba  jmp     short loc_180007FCE
0x180007fbc  cmp     ax, 5Ch ; '\'
0x180007fc0  jz      short loc_180007FD5
0x180007fc2  call    cs:__imp_CharNextW
0x180007fc8  mov     rcx, rax; lpsz
0x180007fcb  movzx   eax, word ptr [rax]
0x180007fce  test    ax, ax
0x180007fd1  jnz     short loc_180007FBC
0x180007fd3  jmp     short loc_180007FDE
0x180007fd5  test    rcx, rcx
0x180007fd8  jnz     loc_1800085F4
0x180007fde  lea     rbx, ?rgszNeverDelete@CRegParser@ATL@@1QBQEB_WB; wchar_t const * const near * const ATL::CRegParser::rgszNeverDelete
0x180007fe5  mov     rdx, [rbx]; lpString2
0x180007fe8  mov     rcx, rdi; lpString1
0x180007feb  call    cs:__imp_lstrcmpiW
0x180007ff1  test    eax, eax
0x180007ff3  jz      short loc_180008017
0x180007ff5  add     rbx, 8
0x180007ff9  lea     rax, aRegopenkeytran; "RegOpenKeyTransactedW"
0x180008000  cmp     rbx, rax
0x180008003  jl      short loc_180007FE5
0x180008005  mov     [rsp+2310h+hKey], r14
0x18000800a  mov     rdx, rdi; wchar_t *
0x18000800d  lea     rcx, [rsp+2310h+hKey]; this
0x180008012  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x180008017  test    esi, esi
0x180008019  jnz     short loc_180008050
0x18000801b  mov     rdx, rdi; wchar_t *
0x18000801e  mov     rcx, r12; this
0x180008021  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180008026  mov     ebx, eax
0x180008028  test    eax, eax
0x18000802a  js      loc_18000828B
0x180008030  mov     rdx, rdi; wchar_t *
0x180008033  mov     rcx, r12; this
0x180008036  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x18000803b  mov     ebx, eax
0x18000803d  xor     edx, edx
0x18000803f  test    eax, eax
0x180008041  js      loc_18000828B
0x180008047  mov     esi, [rsp+2310h+var_22B0]
0x18000804b  jmp     loc_1800082F9
0x180008050  lea     rdx, aNoremove; "NoRemove"
0x180008057  mov     rcx, rdi; lpString1
0x18000805a  call    cs:__imp_lstrcmpiW
0x180008060  xor     ecx, ecx
0x180008062  test    eax, eax
0x180008064  jnz     short loc_18000807E
0x180008066  mov     r13d, ecx
0x180008069  mov     rdx, rdi; wchar_t *
0x18000806c  mov     rcx, r12; this
0x18000806f  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180008074  mov     ebx, eax
0x180008076  test    eax, eax
0x180008078  js      loc_18000828B
0x18000807e  lea     rdx, aVal; "Val"
0x180008085  mov     rcx, rdi; lpString1
0x180008088  call    cs:__imp_lstrcmpiW
0x18000808e  test    eax, eax
0x180008090  jnz     loc_180008184
0x180008096  lea     rdx, [rbp+2210h+ValueName]; wchar_t *
0x18000809d  mov     rcx, r12; this
0x1800080a0  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800080a5  mov     ebx, eax
0x1800080a7  test    eax, eax
0x1800080a9  js      loc_18000828B
0x1800080af  mov     rdx, rdi; wchar_t *
0x1800080b2  mov     rcx, r12; this
0x1800080b5  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800080ba  mov     ebx, eax
0x1800080bc  xor     edx, edx
0x1800080be  test    eax, eax
0x1800080c0  js      loc_18000828B
0x1800080c6  cmp     word ptr [rdi], 3Dh ; '='
0x1800080ca  jnz     loc_1800085F4
0x1800080d0  mov     esi, [rsp+2310h+var_22B0]
0x1800080d4  test    esi, esi
0x1800080d6  jz      short loc_18000810D
0x1800080d8  xorps   xmm0, xmm0
0x1800080db  movups  xmmword ptr [rsp+2310h+hKey], xmm0
0x1800080e0  mov     [rsp+2310h+hKey], r14
0x1800080e5  mov     dword ptr [rsp+2310h+hKey+8], edx
0x1800080e9  mov     [rbp+2210h+var_2290], rdx
0x1800080ed  mov     r9, rdi; wchar_t *
0x1800080f0  lea     r8, [rbp+2210h+ValueName]; wchar_t *
0x1800080f7  lea     rdx, [rsp+2310h+hKey]; struct ATL::CRegKey *
0x1800080fc  mov     rcx, r12; this
0x1800080ff  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x180008104  mov     ebx, eax
0x180008106  xor     edx, edx
0x180008108  jmp     loc_1800082F5
0x18000810d  cmp     [rbp+2210h+arg_20], edx
0x180008113  jnz     short loc_180008174
0x180008115  test    r13d, r13d
0x180008118  jz      short loc_180008174
0x18000811a  mov     [rsp+2310h+hKey+8], rdx
0x18000811f  mov     [rsp+2310h+hKey], rdx
0x180008124  mov     [rbp+2210h+var_2290], rdx
0x180008128  mov     r9d, 20006h; unsigned int
0x18000812e  xor     r8d, r8d; wchar_t *
0x180008131  mov     rdx, r14; HKEY
0x180008134  lea     rcx, [rsp+2310h+hKey]; this
0x180008139  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18000813e  test    eax, eax
0x180008140  jnz     loc_1800085D2
0x180008146  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x18000814d  mov     rsi, [rsp+2310h+hKey]
0x180008152  mov     rcx, rsi; hKey
0x180008155  call    cs:__imp_RegDeleteValueW
0x18000815b  test    eax, 0FFFFFFFDh
0x180008160  jnz     loc_1800085BB
0x180008166  test    rsi, rsi
0x180008169  jz      short loc_180008174
0x18000816b  mov     rcx, rsi; hKey
0x18000816e  call    cs:__imp_RegCloseKey
0x180008174  mov     rdx, rdi; wchar_t *
0x180008177  mov     rcx, r12; this
0x18000817a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x18000817f  jmp     loc_180007F42
0x180008184  mov     rcx, rdi
0x180008187  movzx   eax, word ptr [rdi]
0x18000818a  jmp     short loc_18000819E
0x18000818c  cmp     ax, 5Ch ; '\'
0x180008190  jz      short loc_1800081A5
0x180008192  call    cs:__imp_CharNextW
0x180008198  mov     rcx, rax; lpsz
0x18000819b  movzx   eax, word ptr [rax]
0x18000819e  test    ax, ax
0x1800081a1  jnz     short loc_18000818C
0x1800081a3  jmp     short loc_1800081AE
0x1800081a5  test    rcx, rcx
0x1800081a8  jnz     loc_1800085F4
0x1800081ae  mov     esi, [rsp+2310h+var_22B0]
0x1800081b2  test    esi, esi
0x1800081b4  jz      loc_180008344
0x1800081ba  mov     r15d, 2001Fh
0x1800081c0  mov     r9d, r15d; unsigned int
0x1800081c3  mov     r8, rdi; wchar_t *
0x1800081c6  mov     rdx, r14; HKEY
0x1800081c9  lea     rcx, [rbp+2210h+var_2288]; this
0x1800081cd  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x1800081d2  xor     ebx, ebx
0x1800081d4  test    eax, eax
0x1800081d6  jz      loc_1800082BE
0x1800081dc  lea     r9d, [r15-6]; unsigned int
0x1800081e0  mov     r8, rdi; wchar_t *
0x1800081e3  mov     rdx, r14; HKEY
0x1800081e6  lea     rcx, [rbp+2210h+var_2288]; this
0x1800081ea  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x1800081ef  test    eax, eax
0x1800081f1  jz      loc_1800082BE
0x1800081f7  mov     [rbp+2210h+dwDisposition], ebx
0x1800081fa  mov     [rbp+2210h+var_2270], rbx
0x1800081fe  mov     rcx, [rbp+2210h+var_2278]; this
0x180008202  lea     rax, [rbp+2210h+dwDisposition]
0x180008206  test    rcx, rcx
0x180008209  jz      short loc_180008226
0x18000820b  mov     [rsp+2310h+lpcbMaxValueLen], rax; unsigned int *
0x180008210  lea     rax, [rbp+2210h+var_2270]
0x180008214  mov     [rsp+2310h+lpdwDisposition], rax; HKEY *
0x180008219  mov     r8, rdi; wchar_t *
0x18000821c  mov     rdx, r14; HKEY
0x18000821f  call    ?RegCreateKeyExW@CAtlTransactionManager@ATL@@QEAAJPEAUHKEY__@@PEB_WKPEA_WKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU3@PEAK@Z; ATL::CAtlTransactionManager::RegCreateKeyExW(HKEY__ *,wchar_t const *,ulong,wchar_t *,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)
0x180008224  jmp     short loc_180008254
0x180008226  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x18000822b  lea     rax, [rbp+2210h+var_2270]
0x18000822f  mov     [rsp+2310h+phkResult], rax; phkResult
0x180008234  mov     [rsp+2310h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180008239  mov     [rsp+2310h+samDesired], r15d; samDesired
0x18000823e  mov     [rsp+2310h+dwOptions], ebx; dwOptions
0x180008242  xor     r9d, r9d; lpClass
0x180008245  xor     r8d, r8d; Reserved
0x180008248  mov     rdx, rdi; lpSubKey
0x18000824b  mov     rcx, r14; hKey
0x18000824e  call    cs:__imp_RegCreateKeyExW
0x180008254  xor     edx, edx
0x180008256  test    eax, eax
0x180008258  jnz     short loc_18000827A
0x18000825a  mov     eax, edx
0x18000825c  mov     rcx, [rbp+2210h+var_2288]; hKey
0x180008260  test    rcx, rcx
0x180008263  jz      short loc_18000826D
0x180008265  call    cs:__imp_RegCloseKey
0x18000826b  xor     edx, edx
0x18000826d  mov     r15, [rbp+2210h+var_2270]
0x180008271  mov     [rbp+2210h+var_2288], r15
0x180008275  mov     dword ptr [rbp+2210h+var_2288+8], edx
0x180008278  jmp     short loc_18000827E
0x18000827a  mov     r15, [rbp+2210h+var_2288]
0x18000827e  test    eax, eax
0x180008280  jz      short loc_1800082C2
0x180008282  mov     ecx, eax; unsigned int
0x180008284  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180008289  mov     ebx, eax
0x18000828b  test    r15, r15
0x18000828e  jz      short loc_180008299
0x180008290  mov     rcx, r15; hKey
0x180008293  call    cs:__imp_RegCloseKey
0x180008299  mov     eax, ebx
0x18000829b  mov     rcx, [rbp+2210h+var_50]
0x1800082a2  xor     rcx, rsp; StackCookie
0x1800082a5  call    __security_check_cookie
0x1800082aa  add     rsp, 22D8h
0x1800082b1  pop     r15
0x1800082b3  pop     r14
0x1800082b5  pop     r13
0x1800082b7  pop     r12
0x1800082b9  pop     rdi
0x1800082ba  pop     rsi
0x1800082bb  pop     rbx
0x1800082bc  pop     rbp
0x1800082bd  retn
0x1800082be  mov     r15, [rbp+2210h+var_2288]
0x1800082c2  mov     rdx, rdi; wchar_t *
0x1800082c5  mov     rcx, r12; this
0x1800082c8  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800082cd  mov     ebx, eax
0x1800082cf  xor     edx, edx
0x1800082d1  test    eax, eax
0x1800082d3  js      short loc_18000828B
0x1800082d5  cmp     word ptr [rdi], 3Dh ; '='
0x1800082d9  jnz     short loc_1800082F9
0x1800082db  mov     r9, rdi; wchar_t *
0x1800082de  xor     r8d, r8d; wchar_t *
0x1800082e1  lea     rdx, [rbp+2210h+var_2288]; struct ATL::CRegKey *
0x1800082e5  mov     rcx, r12; this
0x1800082e8  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x1800082ed  mov     ebx, eax
0x1800082ef  xor     edx, edx
0x1800082f1  mov     r15, [rbp+2210h+var_2288]
0x1800082f5  test    eax, eax
0x1800082f7  js      short loc_18000828B
0x1800082f9  cmp     word ptr [rdi], 7Bh ; '{'
0x1800082fd  jnz     loc_180008454
0x180008303  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008307  inc     rax
0x18000830a  cmp     [rdi+rax*2], dx
0x18000830e  jnz     short loc_180008307
0x180008310  cmp     rax, 1
0x180008314  jnz     loc_180008454
0x18000831a  mov     [rsp+2310h+dwOptions], edx; int
0x18000831e  mov     r9d, esi; int
  ... truncated ...
```
