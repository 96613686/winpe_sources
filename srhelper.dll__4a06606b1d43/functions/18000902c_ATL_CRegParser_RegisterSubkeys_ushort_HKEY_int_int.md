# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000902c`
- end: `0x180009780`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1876`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180008ce8`
- `0x18000902c`

## callees

- `0x180007534`
- `0x180007c18`
- `0x180008308`
- `0x180008700`
- `0x180008b98`
- `0x18000902c`
- `0x1800098b4`
- `0x1800157f0`
- `0x180015880`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180009503`
- `msvcrt!wcsncpy_s` at `0x180009503`
- `KERNEL32!lstrcmpiW` at `0x1800090aa`
- `KERNEL32!lstrcmpiW` at `0x1800090bd`
- `KERNEL32!lstrcmpiW` at `0x18000913b`
- `KERNEL32!lstrcmpiW` at `0x1800091a4`
- `KERNEL32!lstrcmpiW` at `0x1800091d2`
- `KERNEL32!lstrcmpiW` at `0x180009629`
- `KERNEL32!lstrcmpiW` at `0x1800090aa`
- `KERNEL32!lstrcmpiW` at `0x1800090bd`
- `KERNEL32!lstrcmpiW` at `0x18000913b`
- `KERNEL32!lstrcmpiW` at `0x1800091a4`
- `KERNEL32!lstrcmpiW` at `0x1800091d2`
- `KERNEL32!lstrcmpiW` at `0x180009629`
- `USER32!CharNextW` at `0x18000910f`
- `USER32!CharNextW` at `0x1800092d6`
- `USER32!CharNextW` at `0x18000910f`
- `USER32!CharNextW` at `0x1800092d6`
- `ADVAPI32!RegDeleteValueW` at `0x18000928c`
- `ADVAPI32!RegDeleteValueW` at `0x18000928c`
- `ADVAPI32!RegCreateKeyExW` at `0x1800093c4`
- `ADVAPI32!RegCreateKeyExW` at `0x1800093c4`
- `ADVAPI32!RegOpenKeyExW` at `0x18000926f`
- `ADVAPI32!RegOpenKeyExW` at `0x18000931d`
- `ADVAPI32!RegOpenKeyExW` at `0x180009366`
- `ADVAPI32!RegOpenKeyExW` at `0x1800094b1`
- `ADVAPI32!RegOpenKeyExW` at `0x18000926f`
- `ADVAPI32!RegOpenKeyExW` at `0x18000931d`
- `ADVAPI32!RegOpenKeyExW` at `0x180009366`
- `ADVAPI32!RegOpenKeyExW` at `0x1800094b1`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180009602`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000969b`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180009602`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000969b`
- `ADVAPI32!RegCloseKey` at `0x1800092a5`
- `ADVAPI32!RegCloseKey` at `0x180009331`
- `ADVAPI32!RegCloseKey` at `0x18000937a`
- `ADVAPI32!RegCloseKey` at `0x1800093dc`
- `ADVAPI32!RegCloseKey` at `0x1800094cc`
- `ADVAPI32!RegCloseKey` at `0x1800096ba`
- `ADVAPI32!RegCloseKey` at `0x180009719`
- `ADVAPI32!RegCloseKey` at `0x180009755`
- `ADVAPI32!RegCloseKey` at `0x180009765`
- `ADVAPI32!RegCloseKey` at `0x1800092a5`
- `ADVAPI32!RegCloseKey` at `0x180009331`
- `ADVAPI32!RegCloseKey` at `0x18000937a`
- `ADVAPI32!RegCloseKey` at `0x1800093dc`
- `ADVAPI32!RegCloseKey` at `0x1800094cc`
- `ADVAPI32!RegCloseKey` at `0x1800096ba`
- `ADVAPI32!RegCloseKey` at `0x180009719`
- `ADVAPI32!RegCloseKey` at `0x180009755`
- `ADVAPI32!RegCloseKey` at `0x180009765`

## string_xrefs

- `0x1800090b0`: `ForceRemove`
- `0x180009194`: `NoRemove`
- `0x1800090a0`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(LPCWSTR *this, unsigned __int16 *a2, HKEY a3, int a4, int a5)
{
  HKEY v5; // rbx
  int v6; // r13d
  HKEY v7; // r15
  __int64 result; // rax
  int Token; // edi
  int v12; // r14d
  int v13; // edi
  WCHAR v14; // ax
  const WCHAR *v15; // rcx
  int v16; // r13d
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
  __int64 v29; // rax
  int v30; // r14d
  int v31; // r14d
  LSTATUS v32; // eax
  unsigned int v33; // ecx
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v35; // [rsp+68h] [rbp-98h]
  HKEY v36; // [rsp+70h] [rbp-90h]
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  HKEY v38[3]; // [rsp+80h] [rbp-80h] BYREF
  HKEY v39; // [rsp+98h] [rbp-68h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-60h]
  __int64 v41; // [rsp+A8h] [rbp-58h]
  wchar_t Destination[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR ValueName[4096]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v35 = a4;
  v5 = 0;
  v36 = a3;
  memset(v38, 0, sizeof(v38));
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
        goto LABEL_107;
      v13 = 0;
      if ( v6 )
      {
        v14 = *a2;
        v39 = 0;
        v40 = 0;
        v41 = 0;
        if ( !v14 )
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
            v39 = v7;
            ATL::CRegKey::RecurseDeleteKey(&v39, a2);
            break;
          }
        }
        if ( !v12 )
        {
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            goto LABEL_107;
          Token = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
          if ( Token < 0 )
            goto LABEL_107;
LABEL_61:
          if ( *a2 != 123 )
            goto LABEL_88;
          v26 = -1;
          do
            ++v26;
          while ( a2[v26] );
          if ( v26 != 1 )
            goto LABEL_88;
          Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, a2, v5, v6, 0);
          if ( Token < 0 )
            goto LABEL_107;
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
        goto LABEL_107;
    }
    if ( !lstrcmpiW(a2, L"Val") )
    {
      Token = ATL::CRegParser::NextToken(this, ValueName);
      if ( Token < 0 )
        goto LABEL_107;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_107;
      if ( *a2 != 61 )
        break;
      if ( v35 )
      {
        v40 = 0;
        v41 = 0;
        v39 = v7;
        v17 = ATL::CRegParser::AddValue((ATL::CRegParser *)this, &v39, ValueName, a2);
LABEL_59:
        Token = v17;
        if ( v17 < 0 )
          goto LABEL_107;
        goto LABEL_60;
      }
      if ( !a5 && v16 )
      {
        hKey = 0;
        v18 = RegOpenKeyExW(v7, 0, 0, 0x20006u, &hKey);
        if ( v18 )
          goto LABEL_105;
        v19 = hKey;
        v20 = RegDeleteValueW(hKey, ValueName);
        if ( (v20 & 0xFFFFFFFD) != 0 )
        {
          Token = ATL::AtlHresultFromWin32(v20);
          if ( v19 )
            RegCloseKey(v19);
          goto LABEL_107;
        }
        if ( v19 )
          RegCloseKey(v19);
      }
      v21 = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
LABEL_35:
      Token = v21;
      if ( v21 < 0 )
        goto LABEL_107;
      goto LABEL_88;
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
    if ( v35 )
    {
      hKey = 0;
      if ( RegOpenKeyExW(v7, a2, 0, 0x2001Fu, &hKey) )
        goto LABEL_120;
      v24 = 0;
      if ( v5 )
        v24 = RegCloseKey(v5);
      v5 = hKey;
      v38[0] = hKey;
      if ( v24 )
      {
LABEL_120:
        hKey = 0;
        if ( RegOpenKeyExW(v7, a2, 0, 0x20019u, &hKey) )
          goto LABEL_121;
        v25 = 0;
        if ( v5 )
          v25 = RegCloseKey(v5);
        v5 = hKey;
        v38[0] = hKey;
        if ( v25 )
        {
LABEL_121:
          LODWORD(hKey) = 0;
          phkResult = 0;
          v18 = RegCreateKeyExW(v7, a2, 0, 0, 0, 0x2001Fu, 0, &phkResult, (LPDWORD)&hKey);
          if ( v18 )
            goto LABEL_105;
          v18 = 0;
          if ( v5 )
            v18 = RegCloseKey(v5);
          v5 = phkResult;
          v38[0] = phkResult;
          if ( v18 )
          {
LABEL_105:
            v33 = v18;
            goto LABEL_106;
          }
        }
      }
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_107;
      if ( *a2 == 61 )
      {
        v17 = ATL::CRegParser::AddValue((ATL::CRegParser *)this, v38, 0, a2);
        v5 = v38[0];
        goto LABEL_59;
      }
LABEL_60:
      v6 = v35;
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
        v38[0] = phkResult;
      }
    }
    v28 = 1;
    if ( !v27 )
      v28 = a5;
    wcsncpy_s(Destination, 0x104u, a2, 0xFFFFFFFFFFFFFFFFuLL);
    Token = ATL::CRegParser::NextToken(this, a2);
    if ( Token < 0 )
      goto LABEL_107;
    Token = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
    if ( Token < 0 )
      goto LABEL_107;
    if ( *a2 == 123 )
    {
      v29 = -1;
      do
        ++v29;
      while ( a2[v29] );
      if ( v29 == 1 )
      {
        Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, a2, v5, 0, v28);
        if ( Token < 0 && !v28 )
          goto LABEL_107;
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_107;
      }
    }
    if ( v27 == 2 )
      goto LABEL_87;
    if ( v27 )
    {
      if ( a5 )
      {
LABEL_87:
        v7 = v36;
        goto LABEL_88;
      }
      v33 = v27;
LABEL_106:
      Token = ATL::AtlHresultFromWin32(v33);
LABEL_107:
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
          v30 = 0;
          while ( lstrcmpiW(Destination, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v30]) )
          {
            if ( ++v30 >= 12 )
            {
              if ( v16 )
              {
                ATL::CRegKey::RecurseDeleteKey(v38, Destination);
                v5 = v38[0];
              }
              goto LABEL_87;
            }
          }
          goto LABEL_87;
        }
      }
    }
    LODWORD(hKey) = 0;
    v31 = 0;
    if ( !RegQueryInfoKeyW(v5, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      LOBYTE(v31) = (_DWORD)hKey != 0;
    if ( v5 )
    {
      v32 = RegCloseKey(v5);
      v38[0] = 0;
      v5 = 0;
      if ( v32 )
        return ATL::AtlHresultFromWin32(v32);
    }
    if ( !v16 )
      goto LABEL_87;
    v7 = v36;
    if ( !v31 )
    {
      v40 = 0;
      v41 = 0;
      v39 = v36;
      v18 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v39, Destination);
      if ( v18 )
        goto LABEL_105;
    }
LABEL_88:
    if ( *a2 == 125 )
      goto LABEL_107;
    v6 = v35;
  }
LABEL_113:
  if ( v5 )
    RegCloseKey(v5);
  return 2147614729LL;
}

```

## disassembly

```asm
0x18000902c  push    rbp
0x18000902e  push    rbx
0x18000902f  push    rsi
0x180009030  push    rdi
0x180009031  push    r12
0x180009033  push    r13
0x180009035  push    r14
0x180009037  push    r15
0x180009039  lea     rbp, [rsp-21D8h]
0x180009041  mov     eax, 22D8h
0x180009046  call    _alloca_probe
0x18000904b  sub     rsp, rax
0x18000904e  mov     rax, cs:__security_cookie
0x180009055  xor     rax, rsp
0x180009058  mov     [rbp+2210h+var_50], rax
0x18000905f  xor     r14d, r14d
0x180009062  mov     [rsp+2310h+var_22A8], r9d
0x180009067  mov     ebx, r14d
0x18000906a  mov     [rsp+2310h+var_22A0], r8
0x18000906f  mov     [rbp+2210h+var_2290], rbx
0x180009073  mov     r13d, r9d
0x180009076  mov     r15, r8
0x180009079  mov     [rbp+2210h+var_2288], r14
0x18000907d  mov     rsi, rdx
0x180009080  mov     [rbp+2210h+var_2280], r14
0x180009084  mov     r12, rcx
0x180009087  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000908c  mov     edi, eax
0x18000908e  test    eax, eax
0x180009090  js      loc_180009721
0x180009096  cmp     word ptr [rsi], 7Dh ; '}'
0x18000909a  jz      loc_18000971F
0x1800090a0  lea     rdx, aDelete; "Delete"
0x1800090a7  mov     rcx, rsi; lpString1
0x1800090aa  call    cs:__imp_lstrcmpiW
0x1800090b0  lea     rdx, aForceremove; "ForceRemove"
0x1800090b7  mov     rcx, rsi; lpString1
0x1800090ba  mov     r14d, eax
0x1800090bd  call    cs:__imp_lstrcmpiW
0x1800090c3  xor     edi, edi
0x1800090c5  test    eax, eax
0x1800090c7  jz      short loc_1800090D2
0x1800090c9  test    r14d, r14d
0x1800090cc  jnz     loc_180009194
0x1800090d2  mov     rdx, rsi; unsigned __int16 *
0x1800090d5  mov     rcx, r12; this
0x1800090d8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800090dd  mov     edi, eax
0x1800090df  test    eax, eax
0x1800090e1  js      loc_180009711
0x1800090e7  xor     edi, edi
0x1800090e9  test    r13d, r13d
0x1800090ec  jz      loc_180009194
0x1800090f2  movzx   eax, word ptr [rsi]
0x1800090f5  mov     [rbp+2210h+var_2278], rdi
0x1800090f9  mov     [rbp+2210h+var_2270], rdi
0x1800090fd  mov     [rbp+2210h+var_2268], rdi
0x180009101  test    ax, ax
0x180009104  jz      short loc_18000912B
0x180009106  mov     rcx, rsi; lpsz
0x180009109  cmp     ax, 5Ch ; '\'
0x18000910d  jz      short loc_180009122
0x18000910f  call    cs:__imp_CharNextW
0x180009115  mov     rcx, rax
0x180009118  movzx   eax, word ptr [rax]
0x18000911b  test    ax, ax
0x18000911e  jnz     short loc_180009109
0x180009120  jmp     short loc_18000912B
0x180009122  test    rcx, rcx
0x180009125  jnz     loc_18000975D
0x18000912b  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180009132  mov     edx, edi
0x180009134  mov     rcx, rsi; lpString1
0x180009137  mov     rdx, [rax+rdx*8]; lpString2
0x18000913b  call    cs:__imp_lstrcmpiW
0x180009141  test    eax, eax
0x180009143  jz      short loc_18000915C
0x180009145  inc     edi
0x180009147  cmp     edi, 0Ch
0x18000914a  jl      short loc_18000912B
0x18000914c  mov     rdx, rsi; unsigned __int16 *
0x18000914f  mov     [rbp+2210h+var_2278], r15
0x180009153  lea     rcx, [rbp+2210h+var_2278]; this
0x180009157  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000915c  xor     edi, edi
0x18000915e  test    r14d, r14d
0x180009161  jnz     short loc_180009194
0x180009163  mov     rdx, rsi; unsigned __int16 *
0x180009166  mov     rcx, r12; this
0x180009169  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000916e  mov     edi, eax
0x180009170  test    eax, eax
0x180009172  js      loc_180009711
0x180009178  mov     rdx, rsi; unsigned __int16 *
0x18000917b  mov     rcx, r12; this
0x18000917e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180009183  xor     edx, edx
0x180009185  mov     edi, eax
0x180009187  test    eax, eax
0x180009189  js      loc_180009711
0x18000918f  jmp     loc_180009437
0x180009194  lea     rdx, aNoremove; "NoRemove"
0x18000919b  mov     rcx, rsi; lpString1
0x18000919e  mov     r13d, 1
0x1800091a4  call    cs:__imp_lstrcmpiW
0x1800091aa  test    eax, eax
0x1800091ac  jnz     short loc_1800091C8
0x1800091ae  mov     rdx, rsi; unsigned __int16 *
0x1800091b1  mov     rcx, r12; this
0x1800091b4  mov     r13d, edi
0x1800091b7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800091bc  mov     edi, eax
0x1800091be  test    eax, eax
0x1800091c0  js      loc_180009711
0x1800091c6  xor     edi, edi
0x1800091c8  lea     rdx, aVal; "Val"
0x1800091cf  mov     rcx, rsi; lpString1
0x1800091d2  call    cs:__imp_lstrcmpiW
0x1800091d8  test    eax, eax
0x1800091da  jnz     loc_1800092C5
0x1800091e0  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x1800091e7  mov     rcx, r12; this
0x1800091ea  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800091ef  mov     edi, eax
0x1800091f1  test    eax, eax
0x1800091f3  js      loc_180009711
0x1800091f9  mov     rdx, rsi; unsigned __int16 *
0x1800091fc  mov     rcx, r12; this
0x1800091ff  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009204  xor     edx, edx; lpSubKey
0x180009206  mov     edi, eax
0x180009208  test    eax, eax
0x18000920a  js      loc_180009711
0x180009210  cmp     word ptr [rsi], 3Dh ; '='
0x180009214  jnz     loc_18000975D
0x18000921a  cmp     [rsp+2310h+var_22A8], edx
0x18000921e  jz      short loc_180009247
0x180009220  mov     [rbp+2210h+var_2270], rdx
0x180009224  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x18000922b  mov     [rbp+2210h+var_2268], rdx
0x18000922f  mov     r9, rsi; unsigned __int16 *
0x180009232  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180009236  mov     [rbp+2210h+var_2278], r15
0x18000923a  mov     rcx, r12; this
0x18000923d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180009242  jmp     loc_180009426
0x180009247  cmp     [rbp+2210h+arg_20], edx
0x18000924d  jnz     short loc_1800092AB
0x18000924f  test    r13d, r13d
0x180009252  jz      short loc_1800092AB
0x180009254  lea     rax, [rsp+2310h+hKey]
0x180009259  mov     [rsp+2310h+hKey], rdx
0x18000925e  mov     r9d, 20006h; samDesired
0x180009264  mov     [rsp+2310h+phkResult], rax; phkResult
0x180009269  xor     r8d, r8d; ulOptions
0x18000926c  mov     rcx, r15; hKey
0x18000926f  call    cs:__imp_RegOpenKeyExW
0x180009275  test    eax, eax
0x180009277  jnz     loc_180009708
0x18000927d  mov     r14, [rsp+2310h+hKey]
0x180009282  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x180009289  mov     rcx, r14; hKey
0x18000928c  call    cs:__imp_RegDeleteValueW
0x180009292  test    eax, 0FFFFFFFDh
0x180009297  jnz     loc_180009744
0x18000929d  test    r14, r14
0x1800092a0  jz      short loc_1800092AB
0x1800092a2  mov     rcx, r14; hKey
0x1800092a5  call    cs:__imp_RegCloseKey
0x1800092ab  mov     rdx, rsi; unsigned __int16 *
0x1800092ae  mov     rcx, r12; this
0x1800092b1  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800092b6  mov     edi, eax
0x1800092b8  test    eax, eax
0x1800092ba  js      loc_180009711
0x1800092c0  jmp     loc_1800095A6
0x1800092c5  movzx   eax, word ptr [rsi]
0x1800092c8  test    ax, ax
0x1800092cb  jz      short loc_1800092F2
0x1800092cd  mov     rcx, rsi; lpsz
0x1800092d0  cmp     ax, 5Ch ; '\'
0x1800092d4  jz      short loc_1800092E9
0x1800092d6  call    cs:__imp_CharNextW
0x1800092dc  mov     rcx, rax
0x1800092df  movzx   eax, word ptr [rax]
0x1800092e2  test    ax, ax
0x1800092e5  jnz     short loc_1800092D0
0x1800092e7  jmp     short loc_1800092F2
0x1800092e9  test    rcx, rcx
0x1800092ec  jnz     loc_18000975D
0x1800092f2  cmp     [rsp+2310h+var_22A8], edi
0x1800092f6  jz      loc_180009487
0x1800092fc  lea     rax, [rsp+2310h+hKey]
0x180009301  mov     [rsp+2310h+hKey], rdi
0x180009306  mov     r14d, 2001Fh
0x18000930c  mov     [rsp+2310h+phkResult], rax; phkResult
0x180009311  mov     r9d, r14d; samDesired
0x180009314  xor     r8d, r8d; ulOptions
0x180009317  mov     rdx, rsi; lpSubKey
0x18000931a  mov     rcx, r15; hKey
0x18000931d  call    cs:__imp_RegOpenKeyExW
0x180009323  test    eax, eax
0x180009325  jnz     short loc_180009348
0x180009327  mov     eax, edi
0x180009329  test    rbx, rbx
0x18000932c  jz      short loc_180009337
0x18000932e  mov     rcx, rbx; hKey
0x180009331  call    cs:__imp_RegCloseKey
0x180009337  mov     rbx, [rsp+2310h+hKey]
0x18000933c  mov     [rbp+2210h+var_2290], rbx
0x180009340  test    eax, eax
0x180009342  jz      loc_1800093F3
0x180009348  lea     rax, [rsp+2310h+hKey]
0x18000934d  mov     [rsp+2310h+hKey], rdi
0x180009352  mov     r9d, 20019h; samDesired
0x180009358  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000935d  xor     r8d, r8d; ulOptions
0x180009360  mov     rdx, rsi; lpSubKey
0x180009363  mov     rcx, r15; hKey
0x180009366  call    cs:__imp_RegOpenKeyExW
0x18000936c  test    eax, eax
0x18000936e  jnz     short loc_18000938D
0x180009370  mov     eax, edi
0x180009372  test    rbx, rbx
0x180009375  jz      short loc_180009380
0x180009377  mov     rcx, rbx; hKey
0x18000937a  call    cs:__imp_RegCloseKey
0x180009380  mov     rbx, [rsp+2310h+hKey]
0x180009385  mov     [rbp+2210h+var_2290], rbx
0x180009389  test    eax, eax
0x18000938b  jz      short loc_1800093F3
0x18000938d  lea     rax, [rsp+2310h+hKey]
0x180009392  mov     dword ptr [rsp+2310h+hKey], edi
0x180009396  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x18000939b  xor     r9d, r9d; lpClass
0x18000939e  lea     rax, [rsp+2310h+var_2298]
0x1800093a3  mov     [rsp+2310h+var_2298], rdi
0x1800093a8  mov     [rsp+2310h+var_22D8], rax; phkResult
0x1800093ad  xor     r8d, r8d; Reserved
0x1800093b0  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800093b5  mov     rdx, rsi; lpSubKey
0x1800093b8  mov     [rsp+2310h+samDesired], r14d; samDesired
0x1800093bd  mov     rcx, r15; hKey
0x1800093c0  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x1800093c4  call    cs:__imp_RegCreateKeyExW
0x1800093ca  test    eax, eax
0x1800093cc  jnz     loc_180009708
0x1800093d2  mov     eax, edi
0x1800093d4  test    rbx, rbx
0x1800093d7  jz      short loc_1800093E2
0x1800093d9  mov     rcx, rbx; hKey
0x1800093dc  call    cs:__imp_RegCloseKey
0x1800093e2  mov     rbx, [rsp+2310h+var_2298]
0x1800093e7  mov     [rbp+2210h+var_2290], rbx
0x1800093eb  test    eax, eax
0x1800093ed  jnz     loc_180009708
0x1800093f3  mov     rdx, rsi; unsigned __int16 *
0x1800093f6  mov     rcx, r12; this
0x1800093f9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800093fe  xor     edx, edx
0x180009400  mov     edi, eax
0x180009402  test    eax, eax
0x180009404  js      loc_180009711
0x18000940a  cmp     word ptr [rsi], 3Dh ; '='
0x18000940e  jnz     short loc_180009432
0x180009410  mov     r9, rsi; unsigned __int16 *
0x180009413  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x180009417  xor     r8d, r8d; unsigned __int16 *
0x18000941a  mov     rcx, r12; this
0x18000941d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180009422  mov     rbx, [rbp+2210h+var_2290]
0x180009426  xor     edx, edx
0x180009428  mov     edi, eax
0x18000942a  test    eax, eax
0x18000942c  js      loc_180009711
0x180009432  mov     r13d, [rsp+2310h+var_22A8]
0x180009437  cmp     word ptr [rsi], 7Bh ; '{'
0x18000943b  jnz     loc_1800095A6
0x180009441  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009445  inc     rax
0x180009448  cmp     [rsi+rax*2], dx
0x18000944c  jnz     short loc_180009445
0x18000944e  cmp     rax, 1
0x180009452  jnz     loc_1800095A6
0x180009458  mov     dword ptr [rsp+2310h+phkResult], edx; int
0x18000945c  mov     r9d, r13d; int
0x18000945f  mov     rdx, rsi; unsigned __int16 *
0x180009462  mov     r8, rbx; HKEY
0x180009465  mov     rcx, r12; this
0x180009468  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000946d  mov     edi, eax
0x18000946f  test    eax, eax
0x180009471  js      loc_180009711
0x180009477  mov     rdx, rsi; unsigned __int16 *
0x18000947a  mov     rcx, r12; this
0x18000947d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009482  jmp     loc_1800092B6
0x180009487  mov     edi, [rbp+2210h+arg_20]
0x18000948d  xor     eax, eax
0x18000948f  test    edi, edi
  ... truncated ...
```
