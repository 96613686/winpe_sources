# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000459c`
- end: `0x180004dd7`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `2107`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18000420c`
- `0x18000459c`

## callees

- `0x1800015b0`
- `0x180002c98`
- `0x180003344`
- `0x18000335c`
- `0x1800037ec`
- `0x180003a70`
- `0x18000409c`
- `0x18000459c`
- `0x180004fe0`
- `0x18000cbb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180004ae5`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180004ae5`
- `KERNEL32!lstrcmpiW` at `0x18000461d`
- `KERNEL32!lstrcmpiW` at `0x180004636`
- `KERNEL32!lstrcmpiW` at `0x1800046bb`
- `KERNEL32!lstrcmpiW` at `0x180004732`
- `KERNEL32!lstrcmpiW` at `0x180004766`
- `KERNEL32!lstrcmpiW` at `0x180004c33`
- `KERNEL32!lstrcmpiW` at `0x18000461d`
- `KERNEL32!lstrcmpiW` at `0x180004636`
- `KERNEL32!lstrcmpiW` at `0x1800046bb`
- `KERNEL32!lstrcmpiW` at `0x180004732`
- `KERNEL32!lstrcmpiW` at `0x180004766`
- `KERNEL32!lstrcmpiW` at `0x180004c33`
- `ADVAPI32!RegDeleteValueW` at `0x180004830`
- `ADVAPI32!RegDeleteValueW` at `0x180004830`
- `ADVAPI32!RegCreateKeyExW` at `0x180004993`
- `ADVAPI32!RegCreateKeyExW` at `0x180004993`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180004c0d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180004cb2`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180004c0d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180004cb2`
- `ADVAPI32!RegCloseKey` at `0x18000484f`
- `ADVAPI32!RegCloseKey` at `0x1800048ee`
- `ADVAPI32!RegCloseKey` at `0x180004943`
- `ADVAPI32!RegCloseKey` at `0x1800049b1`
- `ADVAPI32!RegCloseKey` at `0x180004aa8`
- `ADVAPI32!RegCloseKey` at `0x180004cd7`
- `ADVAPI32!RegCloseKey` at `0x180004d3c`
- `ADVAPI32!RegCloseKey` at `0x180004d7f`
- `ADVAPI32!RegCloseKey` at `0x180004d95`
- `ADVAPI32!RegCloseKey` at `0x18000484f`
- `ADVAPI32!RegCloseKey` at `0x1800048ee`
- `ADVAPI32!RegCloseKey` at `0x180004943`
- `ADVAPI32!RegCloseKey` at `0x1800049b1`
- `ADVAPI32!RegCloseKey` at `0x180004aa8`
- `ADVAPI32!RegCloseKey` at `0x180004cd7`
- `ADVAPI32!RegCloseKey` at `0x180004d3c`
- `ADVAPI32!RegCloseKey` at `0x180004d7f`
- `ADVAPI32!RegCloseKey` at `0x180004d95`
- `ADVAPI32!RegOpenKeyExW` at `0x18000480d`
- `ADVAPI32!RegOpenKeyExW` at `0x1800048d4`
- `ADVAPI32!RegOpenKeyExW` at `0x180004929`
- `ADVAPI32!RegOpenKeyExW` at `0x180004a87`
- `ADVAPI32!RegOpenKeyExW` at `0x18000480d`
- `ADVAPI32!RegOpenKeyExW` at `0x1800048d4`
- `ADVAPI32!RegOpenKeyExW` at `0x180004929`
- `ADVAPI32!RegOpenKeyExW` at `0x180004a87`
- `USER32!CharNextW` at `0x18000468c`
- `USER32!CharNextW` at `0x180004883`
- `USER32!CharNextW` at `0x18000468c`
- `USER32!CharNextW` at `0x180004883`

## string_xrefs

- `0x180004629`: `ForceRemove`
- `0x180004728`: `NoRemove`
- `0x18000460d`: `Delete`

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
  HKEY v6; // r15
  __int64 result; // rax
  int Token; // edi
  int v11; // r13d
  int v12; // r14d
  WCHAR v13; // ax
  const WCHAR *v14; // rcx
  LPCWSTR *v15; // rdi
  int v16; // r14d
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
  int v29; // eax
  __int64 v30; // rax
  LPCWSTR *v31; // r14
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
  WCHAR String1[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR ValueName[4096]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v36 = a4;
  v5 = 0;
  v37 = a3;
  memset(v39, 0, sizeof(v39));
  v6 = a3;
  result = ATL::CRegParser::NextToken(this, a2);
  Token = result;
  if ( (int)result < 0 )
    return result;
  if ( *a2 == 125 )
    return (unsigned int)Token;
  while ( 1 )
  {
    v11 = 1;
    v12 = lstrcmpiW(a2, L"Delete");
    if ( !lstrcmpiW(a2, L"ForceRemove") || !v12 )
    {
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_112;
      if ( v36 )
      {
        v13 = *a2;
        v14 = a2;
        v40 = 0;
        v41 = 0;
        v42 = 0;
        while ( v13 )
        {
          if ( v13 == 92 )
          {
            if ( v14 )
              goto LABEL_118;
            break;
          }
          v14 = CharNextW(v14);
          v13 = *v14;
        }
        v15 = (LPCWSTR *)&ATL::CRegParser::rgszNeverDelete;
        while ( lstrcmpiW(a2, *v15) )
        {
          if ( (__int64)++v15 >= (__int64)&`CWdsSimpleDeviceController::_GetEntries'::`2'::_entries )
          {
            v40 = v6;
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
          v16 = v36;
          goto LABEL_61;
        }
      }
    }
    if ( !lstrcmpiW(a2, L"NoRemove") )
    {
      v11 = 0;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_112;
    }
    if ( !lstrcmpiW(a2, L"Val") )
      break;
    v22 = *a2;
    v23 = a2;
    while ( v22 )
    {
      if ( v22 == 92 )
      {
        if ( v23 )
          goto LABEL_118;
        break;
      }
      v23 = CharNextW(v23);
      v22 = *v23;
    }
    v16 = v36;
    if ( v36 )
    {
      hKey = 0;
      if ( RegOpenKeyExW(v6, a2, 0, 0x2001Fu, &hKey) )
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
        if ( RegOpenKeyExW(v6, a2, 0, 0x20019u, &hKey) )
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
          v18 = RegCreateKeyExW(v6, a2, 0, 0, 0, 0x2001Fu, 0, &phkResult, (LPDWORD)&hKey);
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
        goto LABEL_60;
      }
LABEL_61:
      if ( *a2 == 123 )
      {
        v26 = -1;
        do
          ++v26;
        while ( a2[v26] );
        if ( v26 == 1 )
        {
          Token = ATL::CRegParser::RegisterSubkeys(this, a2, v5, v16, 0);
          if ( Token < 0 )
            goto LABEL_112;
          v21 = ATL::CRegParser::NextToken(this, a2);
          goto LABEL_36;
        }
      }
      goto LABEL_93;
    }
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
        if ( v5 )
          v27 = RegCloseKey(v5);
        v5 = phkResult;
        v39[0] = phkResult;
      }
    }
    v28 = 1;
    if ( !v27 )
      v28 = a5;
    v29 = _o_wcsncpy_s(String1, 260, a2, -1);
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
        v6 = v37;
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
          v31 = (LPCWSTR *)&ATL::CRegParser::rgszNeverDelete;
          while ( lstrcmpiW(String1, *v31) )
          {
            if ( (__int64)++v31 >= (__int64)&`CWdsSimpleDeviceController::_GetEntries'::`2'::_entries )
            {
              if ( v11 )
              {
                ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v39, String1);
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
    if ( !v11 )
      goto LABEL_92;
    v6 = v37;
    if ( !v32 )
    {
      v41 = 0;
      v42 = 0;
      v40 = v37;
      v18 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v40, String1);
      if ( v18 )
        goto LABEL_110;
    }
LABEL_93:
    if ( *a2 == 125 )
      goto LABEL_112;
  }
  Token = ATL::CRegParser::NextToken(this, ValueName);
  if ( Token < 0 )
    goto LABEL_112;
  Token = ATL::CRegParser::NextToken(this, a2);
  if ( Token < 0 )
    goto LABEL_112;
  if ( *a2 == 61 )
  {
    v16 = v36;
    if ( !v36 )
    {
      if ( !a5 && v11 )
      {
        hKey = 0;
        v18 = RegOpenKeyExW(v6, 0, 0, 0x20006u, &hKey);
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
LABEL_36:
      Token = v21;
      if ( v21 < 0 )
        goto LABEL_112;
      goto LABEL_93;
    }
    v41 = 0;
    v42 = 0;
    v40 = v6;
    v17 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)&v40, ValueName, a2);
LABEL_60:
    Token = v17;
    if ( v17 < 0 )
      goto LABEL_112;
    goto LABEL_61;
  }
LABEL_118:
  if ( v5 )
    RegCloseKey(v5);
  return 2147614729LL;
}

```

## disassembly

```asm
0x18000459c  push    rbp
0x18000459e  push    rbx
0x18000459f  push    rsi
0x1800045a0  push    rdi
0x1800045a1  push    r12
0x1800045a3  push    r13
0x1800045a5  push    r14
0x1800045a7  push    r15
0x1800045a9  lea     rbp, [rsp-21D8h]
0x1800045b1  mov     eax, 22D8h
0x1800045b6  call    _alloca_probe
0x1800045bb  sub     rsp, rax
0x1800045be  mov     rax, cs:__security_cookie
0x1800045c5  xor     rax, rsp
0x1800045c8  mov     [rbp+2210h+var_50], rax
0x1800045cf  xor     r14d, r14d
0x1800045d2  mov     [rsp+2310h+var_22A8], r9d
0x1800045d7  mov     ebx, r14d
0x1800045da  mov     [rsp+2310h+var_22A0], r8
0x1800045df  mov     [rbp+2210h+var_2290], rbx
0x1800045e3  mov     r15, r8
0x1800045e6  mov     rsi, rdx
0x1800045e9  mov     [rbp+2210h+var_2288], r14
0x1800045ed  mov     r12, rcx
0x1800045f0  mov     [rbp+2210h+var_2280], r14
0x1800045f4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800045f9  mov     edi, eax
0x1800045fb  test    eax, eax
0x1800045fd  js      loc_180004D4A
0x180004603  cmp     word ptr [rsi], 7Dh ; '}'
0x180004607  jz      loc_180004D48
0x18000460d  lea     rdx, String2; "Delete"
0x180004614  mov     rcx, rsi; lpString1
0x180004617  mov     r13d, 1
0x18000461d  call    cs:__imp_lstrcmpiW
0x180004624  nop     dword ptr [rax+rax+00h]
0x180004629  lea     rdx, aForceremove; "ForceRemove"
0x180004630  mov     rcx, rsi; lpString1
0x180004633  mov     r14d, eax
0x180004636  call    cs:__imp_lstrcmpiW
0x18000463d  nop     dword ptr [rax+rax+00h]
0x180004642  xor     edi, edi
0x180004644  test    eax, eax
0x180004646  jz      short loc_180004651
0x180004648  test    r14d, r14d
0x18000464b  jnz     loc_180004728
0x180004651  mov     rdx, rsi; unsigned __int16 *
0x180004654  mov     rcx, r12; this
0x180004657  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000465c  mov     edi, eax
0x18000465e  test    eax, eax
0x180004660  js      loc_180004D34
0x180004666  xor     edi, edi
0x180004668  cmp     [rsp+2310h+var_22A8], edi
0x18000466c  jz      loc_180004728
0x180004672  movzx   eax, word ptr [rsi]
0x180004675  mov     rcx, rsi
0x180004678  mov     [rbp+2210h+var_2278], rdi
0x18000467c  mov     [rbp+2210h+var_2270], rdi
0x180004680  mov     [rbp+2210h+var_2268], rdi
0x180004684  jmp     short loc_18000469E
0x180004686  cmp     ax, 5Ch ; '\'
0x18000468a  jz      short loc_1800046A5
0x18000468c  call    cs:__imp_CharNextW
0x180004693  nop     dword ptr [rax+rax+00h]
0x180004698  mov     rcx, rax; lpsz
0x18000469b  movzx   eax, word ptr [rax]
0x18000469e  test    ax, ax
0x1800046a1  jnz     short loc_180004686
0x1800046a3  jmp     short loc_1800046AE
0x1800046a5  test    rcx, rcx
0x1800046a8  jnz     loc_180004D8D
0x1800046ae  lea     rdi, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x1800046b5  mov     rdx, [rdi]; lpString2
0x1800046b8  mov     rcx, rsi; lpString1
0x1800046bb  call    cs:__imp_lstrcmpiW
0x1800046c2  nop     dword ptr [rax+rax+00h]
0x1800046c7  test    eax, eax
0x1800046c9  jz      short loc_1800046EB
0x1800046cb  add     rdi, 8
0x1800046cf  lea     rax, ?_entries@?1??_GetEntries@CWdsSimpleDeviceController@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CWdsSimpleDeviceController::_GetEntries(void)'::`2'::_entries
0x1800046d6  cmp     rdi, rax
0x1800046d9  jl      short loc_1800046B5
0x1800046db  mov     rdx, rsi; unsigned __int16 *
0x1800046de  mov     [rbp+2210h+var_2278], r15
0x1800046e2  lea     rcx, [rbp+2210h+var_2278]; this
0x1800046e6  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800046eb  xor     edi, edi
0x1800046ed  test    r14d, r14d
0x1800046f0  jnz     short loc_180004728
0x1800046f2  mov     rdx, rsi; unsigned __int16 *
0x1800046f5  mov     rcx, r12; this
0x1800046f8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800046fd  mov     edi, eax
0x1800046ff  test    eax, eax
0x180004701  js      loc_180004D34
0x180004707  mov     rdx, rsi; unsigned __int16 *
0x18000470a  mov     rcx, r12; this
0x18000470d  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180004712  xor     edx, edx
0x180004714  mov     edi, eax
0x180004716  test    eax, eax
0x180004718  js      loc_180004D34
0x18000471e  mov     r14d, [rsp+2310h+var_22A8]
0x180004723  jmp     loc_180004A0D
0x180004728  lea     rdx, aNoremove; "NoRemove"
0x18000472f  mov     rcx, rsi; lpString1
0x180004732  call    cs:__imp_lstrcmpiW
0x180004739  nop     dword ptr [rax+rax+00h]
0x18000473e  test    eax, eax
0x180004740  jnz     short loc_18000475C
0x180004742  mov     rdx, rsi; unsigned __int16 *
0x180004745  mov     rcx, r12; this
0x180004748  mov     r13d, edi
0x18000474b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004750  mov     edi, eax
0x180004752  test    eax, eax
0x180004754  js      loc_180004D34
0x18000475a  xor     edi, edi
0x18000475c  lea     rdx, aVal; "Val"
0x180004763  mov     rcx, rsi; lpString1
0x180004766  call    cs:__imp_lstrcmpiW
0x18000476d  nop     dword ptr [rax+rax+00h]
0x180004772  test    eax, eax
0x180004774  jnz     loc_180004875
0x18000477a  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180004781  mov     rcx, r12; this
0x180004784  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004789  mov     edi, eax
0x18000478b  test    eax, eax
0x18000478d  js      loc_180004D34
0x180004793  mov     rdx, rsi; unsigned __int16 *
0x180004796  mov     rcx, r12; this
0x180004799  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000479e  xor     edx, edx; lpSubKey
0x1800047a0  mov     edi, eax
0x1800047a2  test    eax, eax
0x1800047a4  js      loc_180004D34
0x1800047aa  cmp     word ptr [rsi], 3Dh ; '='
0x1800047ae  jnz     loc_180004D8D
0x1800047b4  mov     r14d, [rsp+2310h+var_22A8]
0x1800047b9  test    r14d, r14d
0x1800047bc  jz      short loc_1800047E5
0x1800047be  mov     [rbp+2210h+var_2270], rdx
0x1800047c2  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x1800047c9  mov     [rbp+2210h+var_2268], rdx
0x1800047cd  mov     r9, rsi; unsigned __int16 *
0x1800047d0  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x1800047d4  mov     [rbp+2210h+var_2278], r15
0x1800047d8  mov     rcx, r12; this
0x1800047db  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800047e0  jmp     loc_180004A01
0x1800047e5  cmp     [rbp+2210h+arg_20], edx
0x1800047eb  jnz     short loc_18000485B
0x1800047ed  test    r13d, r13d
0x1800047f0  jz      short loc_18000485B
0x1800047f2  lea     rax, [rsp+2310h+hKey]
0x1800047f7  mov     [rsp+2310h+hKey], rdx
0x1800047fc  mov     r9d, 20006h; samDesired
0x180004802  mov     [rsp+2310h+phkResult], rax; phkResult
0x180004807  xor     r8d, r8d; ulOptions
0x18000480a  mov     rcx, r15; hKey
0x18000480d  call    cs:__imp_RegOpenKeyExW
0x180004814  nop     dword ptr [rax+rax+00h]
0x180004819  test    eax, eax
0x18000481b  jnz     loc_180004D2B
0x180004821  mov     r14, [rsp+2310h+hKey]
0x180004826  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x18000482d  mov     rcx, r14; hKey
0x180004830  call    cs:__imp_RegDeleteValueW
0x180004837  nop     dword ptr [rax+rax+00h]
0x18000483c  test    eax, 0FFFFFFFDh
0x180004841  jnz     loc_180004D6E
0x180004847  test    r14, r14
0x18000484a  jz      short loc_18000485B
0x18000484c  mov     rcx, r14; hKey
0x18000484f  call    cs:__imp_RegCloseKey
0x180004856  nop     dword ptr [rax+rax+00h]
0x18000485b  mov     rdx, rsi; unsigned __int16 *
0x18000485e  mov     rcx, r12; this
0x180004861  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180004866  mov     edi, eax
0x180004868  test    eax, eax
0x18000486a  js      loc_180004D34
0x180004870  jmp     loc_180004BB6
0x180004875  movzx   eax, word ptr [rsi]
0x180004878  mov     rcx, rsi
0x18000487b  jmp     short loc_180004895
0x18000487d  cmp     ax, 5Ch ; '\'
0x180004881  jz      short loc_18000489C
0x180004883  call    cs:__imp_CharNextW
0x18000488a  nop     dword ptr [rax+rax+00h]
0x18000488f  mov     rcx, rax; lpsz
0x180004892  movzx   eax, word ptr [rax]
0x180004895  test    ax, ax
0x180004898  jnz     short loc_18000487D
0x18000489a  jmp     short loc_1800048A5
0x18000489c  test    rcx, rcx
0x18000489f  jnz     loc_180004D8D
0x1800048a5  mov     r14d, [rsp+2310h+var_22A8]
0x1800048aa  test    r14d, r14d
0x1800048ad  jz      loc_180004A5D
0x1800048b3  lea     rax, [rsp+2310h+hKey]
0x1800048b8  mov     [rsp+2310h+hKey], rdi
0x1800048bd  mov     r13d, 2001Fh
0x1800048c3  mov     [rsp+2310h+phkResult], rax; phkResult
0x1800048c8  mov     r9d, r13d; samDesired
0x1800048cb  xor     r8d, r8d; ulOptions
0x1800048ce  mov     rdx, rsi; lpSubKey
0x1800048d1  mov     rcx, r15; hKey
0x1800048d4  call    cs:__imp_RegOpenKeyExW
0x1800048db  nop     dword ptr [rax+rax+00h]
0x1800048e0  test    eax, eax
0x1800048e2  jnz     short loc_18000490B
0x1800048e4  mov     eax, edi
0x1800048e6  test    rbx, rbx
0x1800048e9  jz      short loc_1800048FA
0x1800048eb  mov     rcx, rbx; hKey
0x1800048ee  call    cs:__imp_RegCloseKey
0x1800048f5  nop     dword ptr [rax+rax+00h]
0x1800048fa  mov     rbx, [rsp+2310h+hKey]
0x1800048ff  mov     [rbp+2210h+var_2290], rbx
0x180004903  test    eax, eax
0x180004905  jz      loc_1800049CE
0x18000490b  lea     rax, [rsp+2310h+hKey]
0x180004910  mov     [rsp+2310h+hKey], rdi
0x180004915  mov     r9d, 20019h; samDesired
0x18000491b  mov     [rsp+2310h+phkResult], rax; phkResult
0x180004920  xor     r8d, r8d; ulOptions
0x180004923  mov     rdx, rsi; lpSubKey
0x180004926  mov     rcx, r15; hKey
0x180004929  call    cs:__imp_RegOpenKeyExW
0x180004930  nop     dword ptr [rax+rax+00h]
0x180004935  test    eax, eax
0x180004937  jnz     short loc_18000495C
0x180004939  mov     eax, edi
0x18000493b  test    rbx, rbx
0x18000493e  jz      short loc_18000494F
0x180004940  mov     rcx, rbx; hKey
0x180004943  call    cs:__imp_RegCloseKey
0x18000494a  nop     dword ptr [rax+rax+00h]
0x18000494f  mov     rbx, [rsp+2310h+hKey]
0x180004954  mov     [rbp+2210h+var_2290], rbx
0x180004958  test    eax, eax
0x18000495a  jz      short loc_1800049CE
0x18000495c  lea     rax, [rsp+2310h+hKey]
0x180004961  mov     dword ptr [rsp+2310h+hKey], edi
0x180004965  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x18000496a  xor     r9d, r9d; lpClass
0x18000496d  lea     rax, [rsp+2310h+var_2298]
0x180004972  mov     [rsp+2310h+var_2298], rdi
0x180004977  mov     [rsp+2310h+var_22D8], rax; phkResult
0x18000497c  xor     r8d, r8d; Reserved
0x18000497f  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180004984  mov     rdx, rsi; lpSubKey
0x180004987  mov     [rsp+2310h+samDesired], r13d; samDesired
0x18000498c  mov     rcx, r15; hKey
0x18000498f  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x180004993  call    cs:__imp_RegCreateKeyExW
0x18000499a  nop     dword ptr [rax+rax+00h]
0x18000499f  test    eax, eax
0x1800049a1  jnz     loc_180004D2B
0x1800049a7  mov     eax, edi
0x1800049a9  test    rbx, rbx
0x1800049ac  jz      short loc_1800049BD
0x1800049ae  mov     rcx, rbx; hKey
0x1800049b1  call    cs:__imp_RegCloseKey
0x1800049b8  nop     dword ptr [rax+rax+00h]
0x1800049bd  mov     rbx, [rsp+2310h+var_2298]
0x1800049c2  mov     [rbp+2210h+var_2290], rbx
0x1800049c6  test    eax, eax
0x1800049c8  jnz     loc_180004D2B
0x1800049ce  mov     rdx, rsi; unsigned __int16 *
0x1800049d1  mov     rcx, r12; this
0x1800049d4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800049d9  xor     edx, edx
0x1800049db  mov     edi, eax
0x1800049dd  test    eax, eax
0x1800049df  js      loc_180004D34
0x1800049e5  cmp     word ptr [rsi], 3Dh ; '='
0x1800049e9  jnz     short loc_180004A0D
0x1800049eb  mov     r9, rsi; unsigned __int16 *
0x1800049ee  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x1800049f2  xor     r8d, r8d; unsigned __int16 *
0x1800049f5  mov     rcx, r12; this
0x1800049f8  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800049fd  mov     rbx, [rbp+2210h+var_2290]
0x180004a01  xor     edx, edx
0x180004a03  mov     edi, eax
0x180004a05  test    eax, eax
0x180004a07  js      loc_180004D34
0x180004a0d  cmp     word ptr [rsi], 7Bh ; '{'
0x180004a11  jnz     loc_180004BB6
0x180004a17  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004a1b  inc     rax
0x180004a1e  cmp     [rsi+rax*2], dx
0x180004a22  jnz     short loc_180004A1B
0x180004a24  cmp     rax, 1
0x180004a28  jnz     loc_180004BB6
0x180004a2e  mov     dword ptr [rsp+2310h+phkResult], edx; int
  ... truncated ...
```
