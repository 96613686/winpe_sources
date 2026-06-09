# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x140004190`
- end: `0x140004902`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1906`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140003e1c`
- `0x140004190`

## callees

- `0x1400014f0`
- `0x1400028bc`
- `0x140002fec`
- `0x140003004`
- `0x140003124`
- `0x1400031b0`
- `0x140003784`
- `0x140003ccc`
- `0x140004190`
- `0x1400049f8`
- `0x140007570`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14000461e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14000461e`
- `ADVAPI32!RegCloseKey` at `0x14000440a`
- `ADVAPI32!RegCloseKey` at `0x140004495`
- `ADVAPI32!RegCloseKey` at `0x1400044dc`
- `ADVAPI32!RegCloseKey` at `0x1400045e6`
- `ADVAPI32!RegCloseKey` at `0x1400047ff`
- `ADVAPI32!RegCloseKey` at `0x14000485f`
- `ADVAPI32!RegCloseKey` at `0x14000489b`
- `ADVAPI32!RegCloseKey` at `0x1400048ab`
- `ADVAPI32!RegCloseKey` at `0x14000440a`
- `ADVAPI32!RegCloseKey` at `0x140004495`
- `ADVAPI32!RegCloseKey` at `0x1400044dc`
- `ADVAPI32!RegCloseKey` at `0x1400045e6`
- `ADVAPI32!RegCloseKey` at `0x1400047ff`
- `ADVAPI32!RegCloseKey` at `0x14000485f`
- `ADVAPI32!RegCloseKey` at `0x14000489b`
- `ADVAPI32!RegCloseKey` at `0x1400048ab`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140004745`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1400047e0`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140004745`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1400047e0`
- `ADVAPI32!RegOpenKeyExW` at `0x1400043d4`
- `ADVAPI32!RegOpenKeyExW` at `0x140004480`
- `ADVAPI32!RegOpenKeyExW` at `0x1400044c7`
- `ADVAPI32!RegOpenKeyExW` at `0x1400045cb`
- `ADVAPI32!RegOpenKeyExW` at `0x1400043d4`
- `ADVAPI32!RegOpenKeyExW` at `0x140004480`
- `ADVAPI32!RegOpenKeyExW` at `0x1400044c7`
- `ADVAPI32!RegOpenKeyExW` at `0x1400045cb`
- `ADVAPI32!RegDeleteValueW` at `0x1400043f1`
- `ADVAPI32!RegDeleteValueW` at `0x1400043f1`
- `KERNEL32!lstrcmpiW` at `0x14000420e`
- `KERNEL32!lstrcmpiW` at `0x140004221`
- `KERNEL32!lstrcmpiW` at `0x1400042a1`
- `KERNEL32!lstrcmpiW` at `0x140004308`
- `KERNEL32!lstrcmpiW` at `0x140004337`
- `KERNEL32!lstrcmpiW` at `0x14000476c`
- `KERNEL32!lstrcmpiW` at `0x14000420e`
- `KERNEL32!lstrcmpiW` at `0x140004221`
- `KERNEL32!lstrcmpiW` at `0x1400042a1`
- `KERNEL32!lstrcmpiW` at `0x140004308`
- `KERNEL32!lstrcmpiW` at `0x140004337`
- `KERNEL32!lstrcmpiW` at `0x14000476c`
- `USER32!CharNextW` at `0x140004271`
- `USER32!CharNextW` at `0x14000443b`
- `USER32!CharNextW` at `0x140004271`
- `USER32!CharNextW` at `0x14000443b`

## string_xrefs

- `0x140004217`: `ForceRemove`
- `0x1400042fe`: `NoRemove`
- `0x140004204`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  int v5; // r13d
  HKEY v6; // r15
  HKEY v9; // rdi
  __int64 result; // rax
  int Token; // ebx
  int v12; // r14d
  WCHAR v13; // ax
  const WCHAR *v14; // rcx
  int v15; // ebx
  int v16; // r13d
  int v17; // eax
  LSTATUS v18; // eax
  HKEY v19; // r14
  LSTATUS v20; // eax
  int v21; // eax
  WCHAR v22; // ax
  const WCHAR *v23; // rcx
  LSTATUS v24; // eax
  unsigned __int16 *v25; // r9
  LSTATUS v26; // eax
  unsigned int v27; // eax
  __int64 v28; // rax
  LSTATUS v29; // r14d
  int v30; // r15d
  int v31; // eax
  __int64 v32; // rax
  int v33; // r14d
  int v34; // r14d
  LSTATUS v35; // eax
  unsigned int v36; // ecx
  HKEY v37; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int lpcbMaxSubKeyLen; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *lpcbMaxClassLen; // [rsp+30h] [rbp-D0h]
  unsigned int *lpcValues; // [rsp+38h] [rbp-C8h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v43; // [rsp+68h] [rbp-98h]
  HKEY v44; // [rsp+70h] [rbp-90h]
  _QWORD v45[3]; // [rsp+78h] [rbp-88h] BYREF
  HKEY v46; // [rsp+90h] [rbp-70h] BYREF
  __int64 v47; // [rsp+98h] [rbp-68h]
  __int64 v48; // [rsp+A0h] [rbp-60h]
  WCHAR String1[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR ValueName[4096]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v5 = a4;
  v43 = a4;
  v6 = a3;
  v44 = a3;
  v9 = 0;
  memset(v45, 0, sizeof(v45));
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
      if ( v5 )
      {
        v46 = 0;
        v47 = 0;
        v48 = 0;
        v13 = *a2;
        if ( *a2 )
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
            goto LABEL_117;
        }
LABEL_13:
        v15 = 0;
        while ( lstrcmpiW(a2, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v15]) )
        {
          if ( ++v15 >= 12 )
          {
            v46 = v6;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&v46, a2);
            break;
          }
        }
        if ( !v12 )
        {
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            goto LABEL_111;
          Token = ATL::CRegParser::SkipAssignment(this, a2);
          if ( Token < 0 )
            goto LABEL_111;
          goto LABEL_60;
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
    {
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
      if ( !v43 )
      {
        if ( !a5 && v16 )
        {
          hKey = 0;
          v18 = RegOpenKeyExW(v6, 0, 0, 0x20006u, &hKey);
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
            if ( v9 )
            {
              v37 = v9;
              goto LABEL_113;
            }
            return (unsigned int)Token;
          }
          if ( v19 )
            RegCloseKey(v19);
        }
        v21 = ATL::CRegParser::SkipAssignment(this, a2);
LABEL_36:
        Token = v21;
        if ( v21 < 0 )
          goto LABEL_111;
        goto LABEL_92;
      }
      v47 = 0;
      v48 = 0;
      v46 = v6;
      v17 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)&v46, ValueName, a2);
      goto LABEL_58;
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
        goto LABEL_117;
    }
LABEL_44:
    if ( v43 )
      break;
    if ( a5 )
    {
      v29 = 2;
    }
    else
    {
      hKey = 0;
      v29 = RegOpenKeyExW(v6, a2, 0, 0x20019u, &hKey);
      if ( !v29 )
      {
        v29 = 0;
        if ( v9 )
          v29 = RegCloseKey(v9);
        v9 = hKey;
        v45[0] = hKey;
      }
    }
    v30 = 1;
    if ( !v29 )
      v30 = a5;
    v31 = _o_wcsncpy_s(String1, 260, a2, -1);
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
    Token = ATL::CRegParser::SkipAssignment(this, a2);
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
        Token = ATL::CRegParser::RegisterSubkeys(this, a2, v9, 0, v30);
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
      goto LABEL_91;
    }
    if ( a5 )
    {
      LODWORD(hKey) = 0;
      if ( !RegQueryInfoKeyW(v9, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
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
                ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v45, String1);
                v9 = (HKEY)v45[0];
              }
              break;
            }
          }
LABEL_91:
          v6 = v44;
          goto LABEL_92;
        }
      }
    }
    LODWORD(hKey) = 0;
    v34 = 0;
    if ( !RegQueryInfoKeyW(v9, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      LOBYTE(v34) = (_DWORD)hKey != 0;
    if ( v9 )
    {
      v35 = RegCloseKey(v9);
      v9 = 0;
      v45[0] = 0;
      if ( v35 )
        return ATL::AtlHresultFromWin32(v35);
    }
    if ( !v16 )
      goto LABEL_91;
    v6 = v44;
    if ( !v34 )
    {
      v47 = 0;
      v48 = 0;
      v46 = v44;
      v18 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v46, String1);
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
    v5 = v43;
  }
  hKey = 0;
  if ( !RegOpenKeyExW(v6, a2, 0, 0x2001Fu, &hKey) )
  {
    v24 = 0;
    if ( v9 )
      v24 = RegCloseKey(v9);
    v9 = hKey;
    v45[0] = hKey;
    if ( !v24 )
      goto LABEL_55;
  }
  hKey = 0;
  if ( !RegOpenKeyExW(v6, a2, 0, 0x20019u, &hKey) )
  {
    v26 = 0;
    if ( v9 )
      v26 = RegCloseKey(v9);
    v9 = hKey;
    v45[0] = hKey;
    if ( !v26 )
    {
LABEL_55:
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_111;
      if ( *a2 != 61 )
      {
LABEL_59:
        v5 = v43;
LABEL_60:
        if ( *a2 != 123 )
          goto LABEL_92;
        v28 = -1;
        do
          ++v28;
        while ( a2[v28] );
        if ( v28 != 1 )
          goto LABEL_92;
        Token = ATL::CRegParser::RegisterSubkeys(this, a2, v9, v5, 0);
        if ( Token < 0 )
          goto LABEL_111;
        v21 = ATL::CRegParser::NextToken(this, a2);
        goto LABEL_36;
      }
      v17 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)v45, 0, a2);
      v9 = (HKEY)v45[0];
LABEL_58:
      Token = v17;
      if ( v17 < 0 )
        goto LABEL_111;
      goto LABEL_59;
    }
  }
  v27 = ATL::CRegKey::Create((ATL::CRegKey *)v45, v6, a2, v25, phkResult, lpcbMaxSubKeyLen, lpcbMaxClassLen, lpcValues);
  if ( !v27 )
  {
    v9 = (HKEY)v45[0];
    goto LABEL_55;
  }
  Token = ATL::AtlHresultFromWin32(v27);
  v37 = (HKEY)v45[0];
  if ( v45[0] )
LABEL_113:
    RegCloseKey(v37);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x140004190  push    rbp
0x140004192  push    rbx
0x140004193  push    rsi
0x140004194  push    rdi
0x140004195  push    r12
0x140004197  push    r13
0x140004199  push    r14
0x14000419b  push    r15
0x14000419d  lea     rbp, [rsp-21D8h]
0x1400041a5  mov     eax, 22D8h
0x1400041aa  call    _alloca_probe
0x1400041af  sub     rsp, rax
0x1400041b2  mov     rax, cs:__security_cookie
0x1400041b9  xor     rax, rsp
0x1400041bc  mov     [rbp+2210h+var_50], rax
0x1400041c3  mov     r13d, r9d
0x1400041c6  mov     [rsp+2310h+var_22A8], r9d
0x1400041cb  mov     r15, r8
0x1400041ce  mov     [rsp+2310h+var_22A0], r8
0x1400041d3  mov     rsi, rdx
0x1400041d6  mov     r12, rcx
0x1400041d9  xor     eax, eax
0x1400041db  mov     edi, eax
0x1400041dd  mov     [rsp+2310h+var_2298], rax
0x1400041e2  mov     [rbp+2210h+var_2290], rax
0x1400041e6  mov     [rbp+2210h+var_2288], rax
0x1400041ea  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1400041ef  mov     ebx, eax
0x1400041f1  test    eax, eax
0x1400041f3  jns     short loc_1400041FA
0x1400041f5  jmp     loc_140004867
0x1400041fa  cmp     word ptr [rsi], 7Dh ; '}'
0x1400041fe  jz      loc_140004857
0x140004204  lea     rdx, String2; "Delete"
0x14000420b  mov     rcx, rsi; lpString1
0x14000420e  call    cs:__imp_lstrcmpiW
0x140004214  mov     r14d, eax
0x140004217  lea     rdx, aForceremove; "ForceRemove"
0x14000421e  mov     rcx, rsi; lpString1
0x140004221  call    cs:__imp_lstrcmpiW
0x140004227  test    eax, eax
0x140004229  jz      short loc_140004234
0x14000422b  test    r14d, r14d
0x14000422e  jnz     loc_1400042F8
0x140004234  mov     rdx, rsi; unsigned __int16 *
0x140004237  mov     rcx, r12; this
0x14000423a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000423f  mov     ebx, eax
0x140004241  xor     edx, edx
0x140004243  test    eax, eax
0x140004245  js      loc_140004857
0x14000424b  test    r13d, r13d
0x14000424e  jz      loc_1400042F8
0x140004254  mov     [rbp+2210h+var_2280], rdx
0x140004258  mov     [rbp+2210h+var_2278], rdx
0x14000425c  mov     [rbp+2210h+var_2270], rdx
0x140004260  movzx   eax, word ptr [rsi]
0x140004263  test    ax, ax
0x140004266  jz      short loc_14000428F
0x140004268  mov     rcx, rsi; lpsz
0x14000426b  cmp     ax, 5Ch ; '\'
0x14000426f  jz      short loc_140004286
0x140004271  call    cs:__imp_CharNextW
0x140004277  mov     rcx, rax
0x14000427a  movzx   eax, word ptr [rax]
0x14000427d  xor     edx, edx
0x14000427f  test    ax, ax
0x140004282  jnz     short loc_14000426B
0x140004284  jmp     short loc_14000428F
0x140004286  test    rcx, rcx
0x140004289  jnz     loc_1400048A3
0x14000428f  mov     ebx, edx
0x140004291  mov     edx, ebx
0x140004293  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x14000429a  mov     rdx, [rax+rdx*8]; lpString2
0x14000429e  mov     rcx, rsi; lpString1
0x1400042a1  call    cs:__imp_lstrcmpiW
0x1400042a7  test    eax, eax
0x1400042a9  jz      short loc_1400042C2
0x1400042ab  inc     ebx
0x1400042ad  cmp     ebx, 0Ch
0x1400042b0  jl      short loc_140004291
0x1400042b2  mov     [rbp+2210h+var_2280], r15
0x1400042b6  mov     rdx, rsi; unsigned __int16 *
0x1400042b9  lea     rcx, [rbp+2210h+var_2280]; this
0x1400042bd  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1400042c2  test    r14d, r14d
0x1400042c5  jnz     short loc_1400042F8
0x1400042c7  mov     rdx, rsi; unsigned __int16 *
0x1400042ca  mov     rcx, r12; this
0x1400042cd  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1400042d2  mov     ebx, eax
0x1400042d4  test    eax, eax
0x1400042d6  js      loc_140004857
0x1400042dc  mov     rdx, rsi; unsigned __int16 *
0x1400042df  mov     rcx, r12; this
0x1400042e2  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1400042e7  mov     ebx, eax
0x1400042e9  xor     edx, edx
0x1400042eb  test    eax, eax
0x1400042ed  js      loc_140004857
0x1400042f3  jmp     loc_140004553
0x1400042f8  mov     r13d, 1
0x1400042fe  lea     rdx, aNoremove; "NoRemove"
0x140004305  mov     rcx, rsi; lpString1
0x140004308  call    cs:__imp_lstrcmpiW
0x14000430e  xor     r14d, r14d
0x140004311  test    eax, eax
0x140004313  jnz     short loc_14000432D
0x140004315  mov     r13d, r14d
0x140004318  mov     rdx, rsi; unsigned __int16 *
0x14000431b  mov     rcx, r12; this
0x14000431e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140004323  mov     ebx, eax
0x140004325  test    eax, eax
0x140004327  js      loc_140004857
0x14000432d  lea     rdx, aVal; "Val"
0x140004334  mov     rcx, rsi; lpString1
0x140004337  call    cs:__imp_lstrcmpiW
0x14000433d  test    eax, eax
0x14000433f  jnz     loc_14000442A
0x140004345  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x14000434c  mov     rcx, r12; this
0x14000434f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140004354  mov     ebx, eax
0x140004356  test    eax, eax
0x140004358  js      loc_140004857
0x14000435e  mov     rdx, rsi; unsigned __int16 *
0x140004361  mov     rcx, r12; this
0x140004364  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140004369  mov     ebx, eax
0x14000436b  xor     edx, edx; lpSubKey
0x14000436d  test    eax, eax
0x14000436f  js      loc_140004857
0x140004375  cmp     word ptr [rsi], 3Dh ; '='
0x140004379  jnz     loc_1400048A3
0x14000437f  cmp     [rsp+2310h+var_22A8], edx
0x140004383  jz      short loc_1400043AC
0x140004385  mov     [rbp+2210h+var_2278], rdx
0x140004389  mov     [rbp+2210h+var_2270], rdx
0x14000438d  mov     [rbp+2210h+var_2280], r15
0x140004391  mov     r9, rsi; unsigned __int16 *
0x140004394  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x14000439b  lea     rdx, [rbp+2210h+var_2280]; struct ATL::CRegKey *
0x14000439f  mov     rcx, r12; this
0x1400043a2  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1400043a7  jmp     loc_140004542
0x1400043ac  cmp     [rbp+2210h+arg_20], edx
0x1400043b2  jnz     short loc_140004410
0x1400043b4  test    r13d, r13d
0x1400043b7  jz      short loc_140004410
0x1400043b9  mov     [rsp+2310h+hKey], rdx
0x1400043be  lea     rax, [rsp+2310h+hKey]
0x1400043c3  mov     [rsp+2310h+phkResult], rax; phkResult
0x1400043c8  mov     r9d, 20006h; samDesired
0x1400043ce  xor     r8d, r8d; ulOptions
0x1400043d1  mov     rcx, r15; hKey
0x1400043d4  call    cs:__imp_RegOpenKeyExW
0x1400043da  test    eax, eax
0x1400043dc  jnz     loc_14000484E
0x1400043e2  mov     r14, [rsp+2310h+hKey]
0x1400043e7  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x1400043ee  mov     rcx, r14; hKey
0x1400043f1  call    cs:__imp_RegDeleteValueW
0x1400043f7  test    eax, 0FFFFFFFDh
0x1400043fc  jnz     loc_14000488A
0x140004402  test    r14, r14
0x140004405  jz      short loc_140004410
0x140004407  mov     rcx, r14; hKey
0x14000440a  call    cs:__imp_RegCloseKey
0x140004410  mov     rdx, rsi; unsigned __int16 *
0x140004413  mov     rcx, r12; this
0x140004416  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x14000441b  mov     ebx, eax
0x14000441d  test    eax, eax
0x14000441f  js      loc_140004857
0x140004425  jmp     loc_1400046E9
0x14000442a  movzx   eax, word ptr [rsi]
0x14000442d  test    ax, ax
0x140004430  jz      short loc_140004457
0x140004432  mov     rcx, rsi; lpsz
0x140004435  cmp     ax, 5Ch ; '\'
0x140004439  jz      short loc_14000444E
0x14000443b  call    cs:__imp_CharNextW
0x140004441  mov     rcx, rax
0x140004444  movzx   eax, word ptr [rax]
0x140004447  test    ax, ax
0x14000444a  jnz     short loc_140004435
0x14000444c  jmp     short loc_140004457
0x14000444e  test    rcx, rcx
0x140004451  jnz     loc_1400048A3
0x140004457  cmp     [rsp+2310h+var_22A8], r14d
0x14000445c  jz      loc_1400045A3
0x140004462  mov     [rsp+2310h+hKey], r14
0x140004467  lea     rax, [rsp+2310h+hKey]
0x14000446c  mov     [rsp+2310h+phkResult], rax; phkResult
0x140004471  mov     r9d, 2001Fh; samDesired
0x140004477  xor     r8d, r8d; ulOptions
0x14000447a  mov     rdx, rsi; lpSubKey
0x14000447d  mov     rcx, r15; hKey
0x140004480  call    cs:__imp_RegOpenKeyExW
0x140004486  test    eax, eax
0x140004488  jnz     short loc_1400044A9
0x14000448a  mov     eax, r14d
0x14000448d  test    rdi, rdi
0x140004490  jz      short loc_14000449B
0x140004492  mov     rcx, rdi; hKey
0x140004495  call    cs:__imp_RegCloseKey
0x14000449b  mov     rdi, [rsp+2310h+hKey]
0x1400044a0  mov     [rsp+2310h+var_2298], rdi
0x1400044a5  test    eax, eax
0x1400044a7  jz      short loc_14000450D
0x1400044a9  mov     [rsp+2310h+hKey], r14
0x1400044ae  lea     rax, [rsp+2310h+hKey]
0x1400044b3  mov     [rsp+2310h+phkResult], rax; unsigned int
0x1400044b8  mov     r9d, 20019h; samDesired
0x1400044be  xor     r8d, r8d; ulOptions
0x1400044c1  mov     rdx, rsi; lpSubKey
0x1400044c4  mov     rcx, r15; hKey
0x1400044c7  call    cs:__imp_RegOpenKeyExW
0x1400044cd  test    eax, eax
0x1400044cf  jnz     short loc_1400044F0
0x1400044d1  mov     eax, r14d
0x1400044d4  test    rdi, rdi
0x1400044d7  jz      short loc_1400044E2
0x1400044d9  mov     rcx, rdi; hKey
0x1400044dc  call    cs:__imp_RegCloseKey
0x1400044e2  mov     rdi, [rsp+2310h+hKey]
0x1400044e7  mov     [rsp+2310h+var_2298], rdi
0x1400044ec  test    eax, eax
0x1400044ee  jz      short loc_14000450D
0x1400044f0  mov     r8, rsi; unsigned __int16 *
0x1400044f3  mov     rdx, r15; HKEY
0x1400044f6  lea     rcx, [rsp+2310h+var_2298]; this
0x1400044fb  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x140004500  test    eax, eax
0x140004502  jnz     loc_1400048B8
0x140004508  mov     rdi, [rsp+2310h+var_2298]
0x14000450d  mov     rdx, rsi; unsigned __int16 *
0x140004510  mov     rcx, r12; this
0x140004513  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140004518  mov     ebx, eax
0x14000451a  xor     edx, edx
0x14000451c  test    eax, eax
0x14000451e  js      loc_140004857
0x140004524  cmp     word ptr [rsi], 3Dh ; '='
0x140004528  jnz     short loc_14000454E
0x14000452a  mov     r9, rsi; unsigned __int16 *
0x14000452d  xor     r8d, r8d; unsigned __int16 *
0x140004530  lea     rdx, [rsp+2310h+var_2298]; struct ATL::CRegKey *
0x140004535  mov     rcx, r12; this
0x140004538  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x14000453d  mov     rdi, [rsp+2310h+var_2298]
0x140004542  xor     edx, edx
0x140004544  test    eax, eax
0x140004546  mov     ebx, eax
0x140004548  js      loc_140004857
0x14000454e  mov     r13d, [rsp+2310h+var_22A8]
0x140004553  cmp     word ptr [rsi], 7Bh ; '{'
0x140004557  jnz     loc_1400046E9
0x14000455d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004561  inc     rax
0x140004564  cmp     [rsi+rax*2], dx
0x140004568  jnz     short loc_140004561
0x14000456a  cmp     rax, 1
0x14000456e  jnz     loc_1400046E9
0x140004574  mov     dword ptr [rsp+2310h+phkResult], edx; int
0x140004578  mov     r9d, r13d; int
0x14000457b  mov     r8, rdi; HKEY
0x14000457e  mov     rdx, rsi; unsigned __int16 *
0x140004581  mov     rcx, r12; this
0x140004584  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x140004589  mov     ebx, eax
0x14000458b  test    eax, eax
0x14000458d  js      loc_140004857
0x140004593  mov     rdx, rsi; unsigned __int16 *
0x140004596  mov     rcx, r12; this
0x140004599  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000459e  jmp     loc_14000441B
0x1400045a3  mov     ebx, [rbp+2210h+arg_20]
0x1400045a9  test    ebx, ebx
0x1400045ab  jnz     short loc_1400045FB
0x1400045ad  mov     [rsp+2310h+hKey], r14
0x1400045b2  lea     rax, [rsp+2310h+hKey]
0x1400045b7  mov     [rsp+2310h+phkResult], rax; phkResult
0x1400045bc  mov     r9d, 20019h; samDesired
0x1400045c2  xor     r8d, r8d; ulOptions
0x1400045c5  mov     rdx, rsi; lpSubKey
0x1400045c8  mov     rcx, r15; hKey
0x1400045cb  call    cs:__imp_RegOpenKeyExW
0x1400045d1  mov     r14d, eax
0x1400045d4  xor     eax, eax
0x1400045d6  test    r14d, r14d
0x1400045d9  jnz     short loc_140004601
0x1400045db  mov     r14d, eax
0x1400045de  test    rdi, rdi
0x1400045e1  jz      short loc_1400045EF
0x1400045e3  mov     rcx, rdi; hKey
0x1400045e6  call    cs:__imp_RegCloseKey
0x1400045ec  mov     r14d, eax
  ... truncated ...
```
