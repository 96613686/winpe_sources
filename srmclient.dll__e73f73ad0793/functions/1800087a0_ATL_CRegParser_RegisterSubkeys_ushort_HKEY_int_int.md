# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x1800087a0`
- end: `0x180008ff1`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `2129`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180008430`
- `0x1800087a0`

## callees

- `0x18000445c`
- `0x180004df4`
- `0x180004ec8`
- `0x180006268`
- `0x180007a34`
- `0x1800082d8`
- `0x1800087a0`
- `0x180009728`
- `0x1800b07d0`
- `0x1800b0890`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180008cbd`
- `msvcrt!wcsncpy_s` at `0x180008cbd`
- `USER32!CharNextW` at `0x180008883`
- `USER32!CharNextW` at `0x180008a7a`
- `USER32!CharNextW` at `0x180008883`
- `USER32!CharNextW` at `0x180008a7a`
- `KERNEL32!lstrcmpiW` at `0x18000881e`
- `KERNEL32!lstrcmpiW` at `0x180008831`
- `KERNEL32!lstrcmpiW` at `0x1800088af`
- `KERNEL32!lstrcmpiW` at `0x180008920`
- `KERNEL32!lstrcmpiW` at `0x18000894e`
- `KERNEL32!lstrcmpiW` at `0x180008e0b`
- `KERNEL32!lstrcmpiW` at `0x18000881e`
- `KERNEL32!lstrcmpiW` at `0x180008831`
- `KERNEL32!lstrcmpiW` at `0x1800088af`
- `KERNEL32!lstrcmpiW` at `0x180008920`
- `KERNEL32!lstrcmpiW` at `0x18000894e`
- `KERNEL32!lstrcmpiW` at `0x180008e0b`
- `ADVAPI32!RegCreateKeyExW` at `0x180008b72`
- `ADVAPI32!RegCreateKeyExW` at `0x180008b72`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180008de4`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180008e7f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180008de4`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180008e7f`
- `ADVAPI32!RegCloseKey` at `0x180008a45`
- `ADVAPI32!RegCloseKey` at `0x180008ad5`
- `ADVAPI32!RegCloseKey` at `0x180008b24`
- `ADVAPI32!RegCloseKey` at `0x180008b8a`
- `ADVAPI32!RegCloseKey` at `0x180008c7f`
- `ADVAPI32!RegCloseKey` at `0x180008e9e`
- `ADVAPI32!RegCloseKey` at `0x180008f04`
- `ADVAPI32!RegCloseKey` at `0x180008f2c`
- `ADVAPI32!RegCloseKey` at `0x180008f42`
- `ADVAPI32!RegCloseKey` at `0x180008f66`
- `ADVAPI32!RegCloseKey` at `0x180008f9c`
- `ADVAPI32!RegCloseKey` at `0x180008a45`
- `ADVAPI32!RegCloseKey` at `0x180008ad5`
- `ADVAPI32!RegCloseKey` at `0x180008b24`
- `ADVAPI32!RegCloseKey` at `0x180008b8a`
- `ADVAPI32!RegCloseKey` at `0x180008c7f`
- `ADVAPI32!RegCloseKey` at `0x180008e9e`
- `ADVAPI32!RegCloseKey` at `0x180008f04`
- `ADVAPI32!RegCloseKey` at `0x180008f2c`
- `ADVAPI32!RegCloseKey` at `0x180008f42`
- `ADVAPI32!RegCloseKey` at `0x180008f66`
- `ADVAPI32!RegCloseKey` at `0x180008f9c`
- `ADVAPI32!RegOpenKeyExW` at `0x180008a08`
- `ADVAPI32!RegOpenKeyExW` at `0x180008ac1`
- `ADVAPI32!RegOpenKeyExW` at `0x180008b10`
- `ADVAPI32!RegOpenKeyExW` at `0x180008c64`
- `ADVAPI32!RegOpenKeyExW` at `0x180008a08`
- `ADVAPI32!RegOpenKeyExW` at `0x180008ac1`
- `ADVAPI32!RegOpenKeyExW` at `0x180008b10`
- `ADVAPI32!RegOpenKeyExW` at `0x180008c64`
- `ADVAPI32!RegDeleteValueW` at `0x180008a2a`
- `ADVAPI32!RegDeleteValueW` at `0x180008a2a`

## string_xrefs

- `0x180008827`: `ForceRemove`
- `0x180008916`: `NoRemove`
- `0x180008814`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
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
  int v17; // eax
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
  unsigned int v34; // eax
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+68h] [rbp-98h]
  HKEY v37; // [rsp+70h] [rbp-90h]
  _QWORD v38[3]; // [rsp+78h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  HKEY v40; // [rsp+98h] [rbp-68h]
  __int64 v41; // [rsp+A0h] [rbp-60h]
  __int64 v42; // [rsp+A8h] [rbp-58h]
  _QWORD v43[3]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v44[3]; // [rsp+C8h] [rbp-38h] BYREF
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
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v43, a2);
            v43[0] = 0;
            break;
          }
        }
        if ( !v12 )
        {
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            goto LABEL_126;
          Token = ATL::CRegParser::SkipAssignment(this, a2);
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
        v17 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)v44, ValueName, a2);
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
      v20 = ATL::CRegParser::SkipAssignment(this, a2);
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
    Token = ATL::CRegParser::SkipAssignment(this, a2);
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
        Token = ATL::CRegParser::RegisterSubkeys(this, a2, v9, 0, v28);
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
                ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v38, Destination);
                v9 = (HKEY)v38[0];
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
        v17 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)v38, 0, a2);
        Token = v17;
        v9 = (HKEY)v38[0];
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
      Token = ATL::CRegParser::RegisterSubkeys(this, a2, v9, v5, 0);
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
0x1800087a0  push    rbp
0x1800087a2  push    rbx
0x1800087a3  push    rsi
0x1800087a4  push    rdi
0x1800087a5  push    r12
0x1800087a7  push    r13
0x1800087a9  push    r14
0x1800087ab  push    r15
0x1800087ad  lea     rbp, [rsp-2228h]
0x1800087b5  mov     eax, 2328h
0x1800087ba  call    _alloca_probe
0x1800087bf  sub     rsp, rax
0x1800087c2  mov     rax, cs:__security_cookie
0x1800087c9  xor     rax, rsp
0x1800087cc  mov     [rbp+2260h+var_50], rax
0x1800087d3  mov     r12d, r9d
0x1800087d6  mov     [rsp+2360h+var_22F8], r9d
0x1800087db  mov     r15, r8
0x1800087de  mov     [rsp+2360h+var_22F0], r8
0x1800087e3  mov     rsi, rdx
0x1800087e6  mov     r13, rcx
0x1800087e9  xor     eax, eax
0x1800087eb  mov     ebx, eax
0x1800087ed  mov     [rsp+2360h+var_22E8], rax
0x1800087f2  mov     [rbp+2260h+var_22E0], rax
0x1800087f6  mov     [rbp+2260h+var_22D8], rax
0x1800087fa  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800087ff  mov     edi, eax
0x180008801  test    eax, eax
0x180008803  jns     short loc_18000880A
0x180008805  jmp     loc_180008FAD
0x18000880a  cmp     word ptr [rsi], 7Dh ; '}'
0x18000880e  jz      loc_180008F94
0x180008814  lea     rdx, String2; "Delete"
0x18000881b  mov     rcx, rsi; lpString1
0x18000881e  call    cs:__imp_lstrcmpiW
0x180008824  mov     r14d, eax
0x180008827  lea     rdx, aForceremove; "ForceRemove"
0x18000882e  mov     rcx, rsi; lpString1
0x180008831  call    cs:__imp_lstrcmpiW
0x180008837  xor     edi, edi
0x180008839  test    eax, eax
0x18000883b  jz      short loc_180008846
0x18000883d  test    r14d, r14d
0x180008840  jnz     loc_180008910
0x180008846  mov     rdx, rsi; unsigned __int16 *
0x180008849  mov     rcx, r13; this
0x18000884c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008851  mov     edi, eax
0x180008853  test    eax, eax
0x180008855  js      loc_180008F94
0x18000885b  xor     edi, edi
0x18000885d  test    r12d, r12d
0x180008860  jz      loc_180008910
0x180008866  mov     [rbp+2260h+var_22B0], rdi
0x18000886a  mov     [rbp+2260h+var_22A8], rdi
0x18000886e  mov     [rbp+2260h+var_22A0], rdi
0x180008872  movzx   eax, word ptr [rsi]
0x180008875  test    ax, ax
0x180008878  jz      short loc_18000889F
0x18000887a  mov     rcx, rsi; lpsz
0x18000887d  cmp     ax, 5Ch ; '\'
0x180008881  jz      short loc_180008896
0x180008883  call    cs:__imp_CharNextW
0x180008889  mov     rcx, rax
0x18000888c  movzx   eax, word ptr [rax]
0x18000888f  test    ax, ax
0x180008892  jnz     short loc_18000887D
0x180008894  jmp     short loc_18000889F
0x180008896  test    rcx, rcx
0x180008899  jnz     loc_180008EFC
0x18000889f  mov     edx, edi
0x1800088a1  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x1800088a8  mov     rdx, [rax+rdx*8]; lpString2
0x1800088ac  mov     rcx, rsi; lpString1
0x1800088af  call    cs:__imp_lstrcmpiW
0x1800088b5  test    eax, eax
0x1800088b7  jz      short loc_1800088D8
0x1800088b9  inc     edi
0x1800088bb  cmp     edi, 0Ch
0x1800088be  jl      short loc_18000889F
0x1800088c0  mov     [rbp+2260h+var_22B0], r15
0x1800088c4  mov     rdx, rsi; unsigned __int16 *
0x1800088c7  lea     rcx, [rbp+2260h+var_22B0]; this
0x1800088cb  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800088d0  xor     edi, edi
0x1800088d2  mov     [rbp+2260h+var_22B0], rdi
0x1800088d6  jmp     short loc_1800088DA
0x1800088d8  xor     edi, edi
0x1800088da  test    r14d, r14d
0x1800088dd  jnz     short loc_180008910
0x1800088df  mov     rdx, rsi; unsigned __int16 *
0x1800088e2  mov     rcx, r13; this
0x1800088e5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800088ea  mov     edi, eax
0x1800088ec  test    eax, eax
0x1800088ee  js      loc_180008F19
0x1800088f4  mov     rdx, rsi; unsigned __int16 *
0x1800088f7  mov     rcx, r13; this
0x1800088fa  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800088ff  mov     edi, eax
0x180008901  xor     edx, edx
0x180008903  test    eax, eax
0x180008905  js      loc_180008F94
0x18000890b  jmp     loc_180008BEC
0x180008910  mov     r12d, 1
0x180008916  lea     rdx, aNoremove; "NoRemove"
0x18000891d  mov     rcx, rsi; lpString1
0x180008920  call    cs:__imp_lstrcmpiW
0x180008926  test    eax, eax
0x180008928  jnz     short loc_180008944
0x18000892a  mov     r12d, edi
0x18000892d  mov     rdx, rsi; unsigned __int16 *
0x180008930  mov     rcx, r13; this
0x180008933  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008938  mov     edi, eax
0x18000893a  test    eax, eax
0x18000893c  js      loc_180008F94
0x180008942  xor     edi, edi
0x180008944  lea     rdx, aVal; "Val"
0x18000894b  mov     rcx, rsi; lpString1
0x18000894e  call    cs:__imp_lstrcmpiW
0x180008954  test    eax, eax
0x180008956  jnz     loc_180008A69
0x18000895c  lea     rdx, [rbp+2260h+ValueName]; unsigned __int16 *
0x180008963  mov     rcx, r13; this
0x180008966  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000896b  mov     edi, eax
0x18000896d  test    eax, eax
0x18000896f  js      loc_180008F94
0x180008975  mov     rdx, rsi; unsigned __int16 *
0x180008978  mov     rcx, r13; this
0x18000897b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008980  mov     edi, eax
0x180008982  xor     edx, edx
0x180008984  test    eax, eax
0x180008986  js      loc_180008F94
0x18000898c  cmp     word ptr [rsi], 3Dh ; '='
0x180008990  jnz     loc_180008F3A
0x180008996  cmp     [rsp+2360h+var_22F8], edx
0x18000899a  jz      short loc_1800089CF
0x18000899c  mov     [rbp+2260h+var_2298], rdx
0x1800089a0  mov     [rbp+2260h+var_2290], rdx
0x1800089a4  mov     [rbp+2260h+var_2288], rdx
0x1800089a8  mov     [rbp+2260h+var_2298], r15
0x1800089ac  mov     r9, rsi; unsigned __int16 *
0x1800089af  lea     r8, [rbp+2260h+ValueName]; unsigned __int16 *
0x1800089b6  lea     rdx, [rbp+2260h+var_2298]; struct ATL::CRegKey *
0x1800089ba  mov     rcx, r13; this
0x1800089bd  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800089c2  mov     edi, eax
0x1800089c4  xor     edx, edx
0x1800089c6  mov     [rbp+2260h+var_2298], rdx
0x1800089ca  jmp     loc_180008BDF
0x1800089cf  cmp     [rbp+2260h+arg_20], edx
0x1800089d5  jnz     short loc_180008A4F
0x1800089d7  test    r12d, r12d
0x1800089da  jz      short loc_180008A4F
0x1800089dc  mov     r14, rdx
0x1800089df  mov     [rbp+2260h+var_22C8], rdx
0x1800089e3  mov     [rbp+2260h+var_22C0], rdx
0x1800089e7  mov     [rbp+2260h+var_22B8], rdx
0x1800089eb  mov     [rsp+2360h+hKey], rdx
0x1800089f0  lea     rax, [rsp+2360h+hKey]
0x1800089f5  mov     [rsp+2360h+phkResult], rax; phkResult
0x1800089fa  mov     r9d, 20006h; samDesired
0x180008a00  xor     r8d, r8d; ulOptions
0x180008a03  xor     edx, edx; lpSubKey
0x180008a05  mov     rcx, r15; hKey
0x180008a08  call    cs:__imp_RegOpenKeyExW
0x180008a0e  test    eax, eax
0x180008a10  cmovz   r14, [rsp+2360h+hKey]
0x180008a16  mov     [rbp+2260h+var_22C8], r14
0x180008a1a  jnz     loc_180008F1B
0x180008a20  lea     rdx, [rbp+2260h+ValueName]; lpValueName
0x180008a27  mov     rcx, r14; hKey
0x180008a2a  call    cs:__imp_RegDeleteValueW
0x180008a30  test    eax, 0FFFFFFFDh
0x180008a35  jnz     loc_180008F1B
0x180008a3b  xor     edi, edi
0x180008a3d  test    r14, r14
0x180008a40  jz      short loc_180008A4F
0x180008a42  mov     rcx, r14; hKey
0x180008a45  call    cs:__imp_RegCloseKey
0x180008a4b  mov     [rbp+2260h+var_22C8], rdi
0x180008a4f  mov     rdx, rsi; unsigned __int16 *
0x180008a52  mov     rcx, r13; this
0x180008a55  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180008a5a  mov     edi, eax
0x180008a5c  test    eax, eax
0x180008a5e  js      loc_180008F94
0x180008a64  jmp     loc_180008D88
0x180008a69  movzx   eax, word ptr [rsi]
0x180008a6c  test    ax, ax
0x180008a6f  jz      short loc_180008A96
0x180008a71  mov     rcx, rsi; lpsz
0x180008a74  cmp     ax, 5Ch ; '\'
0x180008a78  jz      short loc_180008A8D
0x180008a7a  call    cs:__imp_CharNextW
0x180008a80  mov     rcx, rax
0x180008a83  movzx   eax, word ptr [rax]
0x180008a86  test    ax, ax
0x180008a89  jnz     short loc_180008A74
0x180008a8b  jmp     short loc_180008A96
0x180008a8d  test    rcx, rcx
0x180008a90  jnz     loc_180008EFC
0x180008a96  cmp     [rsp+2360h+var_22F8], edi
0x180008a9a  jz      loc_180008C3C
0x180008aa0  mov     [rsp+2360h+hKey], rdi
0x180008aa5  lea     rax, [rsp+2360h+hKey]
0x180008aaa  mov     [rsp+2360h+phkResult], rax; phkResult
0x180008aaf  mov     r14d, 2001Fh
0x180008ab5  mov     r9d, r14d; samDesired
0x180008ab8  xor     r8d, r8d; ulOptions
0x180008abb  mov     rdx, rsi; lpSubKey
0x180008abe  mov     rcx, r15; hKey
0x180008ac1  call    cs:__imp_RegOpenKeyExW
0x180008ac7  test    eax, eax
0x180008ac9  jnz     short loc_180008AF2
0x180008acb  mov     eax, edi
0x180008acd  test    rbx, rbx
0x180008ad0  jz      short loc_180008AE0
0x180008ad2  mov     rcx, rbx; hKey
0x180008ad5  call    cs:__imp_RegCloseKey
0x180008adb  mov     [rsp+2360h+var_22E8], rdi
0x180008ae0  mov     rbx, [rsp+2360h+hKey]
0x180008ae5  mov     [rsp+2360h+var_22E8], rbx
0x180008aea  test    eax, eax
0x180008aec  jz      loc_180008BA6
0x180008af2  mov     [rsp+2360h+hKey], rdi
0x180008af7  lea     rax, [rsp+2360h+hKey]
0x180008afc  mov     [rsp+2360h+phkResult], rax; phkResult
0x180008b01  mov     r9d, 20019h; samDesired
0x180008b07  xor     r8d, r8d; ulOptions
0x180008b0a  mov     rdx, rsi; lpSubKey
0x180008b0d  mov     rcx, r15; hKey
0x180008b10  call    cs:__imp_RegOpenKeyExW
0x180008b16  test    eax, eax
0x180008b18  jnz     short loc_180008B3D
0x180008b1a  mov     eax, edi
0x180008b1c  test    rbx, rbx
0x180008b1f  jz      short loc_180008B2F
0x180008b21  mov     rcx, rbx; hKey
0x180008b24  call    cs:__imp_RegCloseKey
0x180008b2a  mov     [rsp+2360h+var_22E8], rdi
0x180008b2f  mov     rbx, [rsp+2360h+hKey]
0x180008b34  mov     [rsp+2360h+var_22E8], rbx
0x180008b39  test    eax, eax
0x180008b3b  jz      short loc_180008BA6
0x180008b3d  mov     dword ptr [rsp+2360h+hKey], edi
0x180008b41  mov     [rbp+2260h+var_22D0], rdi
0x180008b45  lea     rax, [rsp+2360h+hKey]
0x180008b4a  mov     [rsp+2360h+lpdwDisposition], rax; lpdwDisposition
0x180008b4f  lea     rax, [rbp+2260h+var_22D0]
0x180008b53  mov     [rsp+2360h+var_2328], rax; phkResult
0x180008b58  mov     [rsp+2360h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180008b5d  mov     [rsp+2360h+samDesired], r14d; samDesired
0x180008b62  mov     dword ptr [rsp+2360h+phkResult], edi; dwOptions
0x180008b66  xor     r9d, r9d; lpClass
0x180008b69  xor     r8d, r8d; Reserved
0x180008b6c  mov     rdx, rsi; lpSubKey
0x180008b6f  mov     rcx, r15; hKey
0x180008b72  call    cs:__imp_RegCreateKeyExW
0x180008b78  test    eax, eax
0x180008b7a  jnz     loc_180008F53
0x180008b80  mov     eax, edi
0x180008b82  test    rbx, rbx
0x180008b85  jz      short loc_180008B95
0x180008b87  mov     rcx, rbx; hKey
0x180008b8a  call    cs:__imp_RegCloseKey
0x180008b90  mov     [rsp+2360h+var_22E8], rdi
0x180008b95  mov     rbx, [rbp+2260h+var_22D0]
0x180008b99  mov     [rsp+2360h+var_22E8], rbx
0x180008b9e  test    eax, eax
0x180008ba0  jnz     loc_180008F53
0x180008ba6  mov     rdx, rsi; unsigned __int16 *
0x180008ba9  mov     rcx, r13; this
0x180008bac  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008bb1  mov     edi, eax
0x180008bb3  xor     edx, edx
0x180008bb5  test    eax, eax
0x180008bb7  js      loc_180008F94
0x180008bbd  cmp     word ptr [rsi], 3Dh ; '='
0x180008bc1  jnz     short loc_180008BE7
0x180008bc3  mov     r9, rsi; unsigned __int16 *
0x180008bc6  xor     r8d, r8d; unsigned __int16 *
0x180008bc9  lea     rdx, [rsp+2360h+var_22E8]; struct ATL::CRegKey *
0x180008bce  mov     rcx, r13; this
0x180008bd1  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180008bd6  mov     edi, eax
0x180008bd8  xor     edx, edx
0x180008bda  mov     rbx, [rsp+2360h+var_22E8]
0x180008bdf  test    eax, eax
0x180008be1  js      loc_180008F94
0x180008be7  mov     r12d, [rsp+2360h+var_22F8]
0x180008bec  cmp     word ptr [rsi], 7Bh ; '{'
0x180008bf0  jnz     loc_180008D88
0x180008bf6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008bfa  inc     rax
0x180008bfd  cmp     [rsi+rax*2], dx
  ... truncated ...
```
