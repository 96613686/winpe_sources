# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000c254`
- end: `0x18000c9a8`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1876`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x18000bcbc`
- `0x18000c254`

## callees

- `0x180009234`
- `0x180009918`
- `0x18000aa78`
- `0x18000b130`
- `0x18000b718`
- `0x18000c254`
- `0x18000d3c4`
- `0x180021740`
- `0x1800217d0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000c72b`
- `msvcrt!wcsncpy_s` at `0x18000c72b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000c337`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000c4fe`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000c337`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000c4fe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c5ec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c5ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c4cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c559`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c5a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c604`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c6f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c8e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c941`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c97d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c98d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c4cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c559`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c5a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c604`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c6f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c8e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c941`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c97d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c98d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000c82a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000c8c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000c82a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000c8c3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000c4b4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000c4b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c497`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c545`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c58e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c6d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c497`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c545`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c58e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c6d9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c2d2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c2e5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c363`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c3cc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c3fa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c851`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c2d2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c2e5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c363`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c3cc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c3fa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c851`

## string_xrefs

- `0x18000c2d8`: `ForceRemove`
- `0x18000c3bc`: `NoRemove`
- `0x18000c2c8`: `Delete`

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
0x18000c254  push    rbp
0x18000c256  push    rbx
0x18000c257  push    rsi
0x18000c258  push    rdi
0x18000c259  push    r12
0x18000c25b  push    r13
0x18000c25d  push    r14
0x18000c25f  push    r15
0x18000c261  lea     rbp, [rsp-21D8h]
0x18000c269  mov     eax, 22D8h
0x18000c26e  call    _alloca_probe
0x18000c273  sub     rsp, rax
0x18000c276  mov     rax, cs:__security_cookie
0x18000c27d  xor     rax, rsp
0x18000c280  mov     [rbp+2210h+var_50], rax
0x18000c287  xor     r14d, r14d
0x18000c28a  mov     [rsp+2310h+var_22A8], r9d
0x18000c28f  mov     ebx, r14d
0x18000c292  mov     [rsp+2310h+var_22A0], r8
0x18000c297  mov     [rbp+2210h+var_2290], rbx
0x18000c29b  mov     r13d, r9d
0x18000c29e  mov     r15, r8
0x18000c2a1  mov     [rbp+2210h+var_2288], r14
0x18000c2a5  mov     rsi, rdx
0x18000c2a8  mov     [rbp+2210h+var_2280], r14
0x18000c2ac  mov     r12, rcx
0x18000c2af  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000c2b4  mov     edi, eax
0x18000c2b6  test    eax, eax
0x18000c2b8  js      loc_18000C949
0x18000c2be  cmp     word ptr [rsi], 7Dh ; '}'
0x18000c2c2  jz      loc_18000C947
0x18000c2c8  lea     rdx, String2; "Delete"
0x18000c2cf  mov     rcx, rsi; lpString1
0x18000c2d2  call    cs:__imp_lstrcmpiW
0x18000c2d8  lea     rdx, aForceremove; "ForceRemove"
0x18000c2df  mov     rcx, rsi; lpString1
0x18000c2e2  mov     r14d, eax
0x18000c2e5  call    cs:__imp_lstrcmpiW
0x18000c2eb  xor     edi, edi
0x18000c2ed  test    eax, eax
0x18000c2ef  jz      short loc_18000C2FA
0x18000c2f1  test    r14d, r14d
0x18000c2f4  jnz     loc_18000C3BC
0x18000c2fa  mov     rdx, rsi; unsigned __int16 *
0x18000c2fd  mov     rcx, r12; this
0x18000c300  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000c305  mov     edi, eax
0x18000c307  test    eax, eax
0x18000c309  js      loc_18000C939
0x18000c30f  xor     edi, edi
0x18000c311  test    r13d, r13d
0x18000c314  jz      loc_18000C3BC
0x18000c31a  movzx   eax, word ptr [rsi]
0x18000c31d  mov     [rbp+2210h+var_2278], rdi
0x18000c321  mov     [rbp+2210h+var_2270], rdi
0x18000c325  mov     [rbp+2210h+var_2268], rdi
0x18000c329  test    ax, ax
0x18000c32c  jz      short loc_18000C353
0x18000c32e  mov     rcx, rsi; lpsz
0x18000c331  cmp     ax, 5Ch ; '\'
0x18000c335  jz      short loc_18000C34A
0x18000c337  call    cs:__imp_CharNextW
0x18000c33d  mov     rcx, rax
0x18000c340  movzx   eax, word ptr [rax]
0x18000c343  test    ax, ax
0x18000c346  jnz     short loc_18000C331
0x18000c348  jmp     short loc_18000C353
0x18000c34a  test    rcx, rcx
0x18000c34d  jnz     loc_18000C985
0x18000c353  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x18000c35a  mov     edx, edi
0x18000c35c  mov     rcx, rsi; lpString1
0x18000c35f  mov     rdx, [rax+rdx*8]; lpString2
0x18000c363  call    cs:__imp_lstrcmpiW
0x18000c369  test    eax, eax
0x18000c36b  jz      short loc_18000C384
0x18000c36d  inc     edi
0x18000c36f  cmp     edi, 0Ch
0x18000c372  jl      short loc_18000C353
0x18000c374  mov     rdx, rsi; unsigned __int16 *
0x18000c377  mov     [rbp+2210h+var_2278], r15
0x18000c37b  lea     rcx, [rbp+2210h+var_2278]; this
0x18000c37f  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000c384  xor     edi, edi
0x18000c386  test    r14d, r14d
0x18000c389  jnz     short loc_18000C3BC
0x18000c38b  mov     rdx, rsi; unsigned __int16 *
0x18000c38e  mov     rcx, r12; this
0x18000c391  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000c396  mov     edi, eax
0x18000c398  test    eax, eax
0x18000c39a  js      loc_18000C939
0x18000c3a0  mov     rdx, rsi; unsigned __int16 *
0x18000c3a3  mov     rcx, r12; this
0x18000c3a6  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000c3ab  xor     edx, edx
0x18000c3ad  mov     edi, eax
0x18000c3af  test    eax, eax
0x18000c3b1  js      loc_18000C939
0x18000c3b7  jmp     loc_18000C65F
0x18000c3bc  lea     rdx, aNoremove; "NoRemove"
0x18000c3c3  mov     rcx, rsi; lpString1
0x18000c3c6  mov     r13d, 1
0x18000c3cc  call    cs:__imp_lstrcmpiW
0x18000c3d2  test    eax, eax
0x18000c3d4  jnz     short loc_18000C3F0
0x18000c3d6  mov     rdx, rsi; unsigned __int16 *
0x18000c3d9  mov     rcx, r12; this
0x18000c3dc  mov     r13d, edi
0x18000c3df  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000c3e4  mov     edi, eax
0x18000c3e6  test    eax, eax
0x18000c3e8  js      loc_18000C939
0x18000c3ee  xor     edi, edi
0x18000c3f0  lea     rdx, aVal; "Val"
0x18000c3f7  mov     rcx, rsi; lpString1
0x18000c3fa  call    cs:__imp_lstrcmpiW
0x18000c400  test    eax, eax
0x18000c402  jnz     loc_18000C4ED
0x18000c408  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x18000c40f  mov     rcx, r12; this
0x18000c412  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000c417  mov     edi, eax
0x18000c419  test    eax, eax
0x18000c41b  js      loc_18000C939
0x18000c421  mov     rdx, rsi; unsigned __int16 *
0x18000c424  mov     rcx, r12; this
0x18000c427  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000c42c  xor     edx, edx; lpSubKey
0x18000c42e  mov     edi, eax
0x18000c430  test    eax, eax
0x18000c432  js      loc_18000C939
0x18000c438  cmp     word ptr [rsi], 3Dh ; '='
0x18000c43c  jnz     loc_18000C985
0x18000c442  cmp     [rsp+2310h+var_22A8], edx
0x18000c446  jz      short loc_18000C46F
0x18000c448  mov     [rbp+2210h+var_2270], rdx
0x18000c44c  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x18000c453  mov     [rbp+2210h+var_2268], rdx
0x18000c457  mov     r9, rsi; unsigned __int16 *
0x18000c45a  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x18000c45e  mov     [rbp+2210h+var_2278], r15
0x18000c462  mov     rcx, r12; this
0x18000c465  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000c46a  jmp     loc_18000C64E
0x18000c46f  cmp     [rbp+2210h+arg_20], edx
0x18000c475  jnz     short loc_18000C4D3
0x18000c477  test    r13d, r13d
0x18000c47a  jz      short loc_18000C4D3
0x18000c47c  lea     rax, [rsp+2310h+hKey]
0x18000c481  mov     [rsp+2310h+hKey], rdx
0x18000c486  mov     r9d, 20006h; samDesired
0x18000c48c  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000c491  xor     r8d, r8d; ulOptions
0x18000c494  mov     rcx, r15; hKey
0x18000c497  call    cs:__imp_RegOpenKeyExW
0x18000c49d  test    eax, eax
0x18000c49f  jnz     loc_18000C930
0x18000c4a5  mov     r14, [rsp+2310h+hKey]
0x18000c4aa  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x18000c4b1  mov     rcx, r14; hKey
0x18000c4b4  call    cs:__imp_RegDeleteValueW
0x18000c4ba  test    eax, 0FFFFFFFDh
0x18000c4bf  jnz     loc_18000C96C
0x18000c4c5  test    r14, r14
0x18000c4c8  jz      short loc_18000C4D3
0x18000c4ca  mov     rcx, r14; hKey
0x18000c4cd  call    cs:__imp_RegCloseKey
0x18000c4d3  mov     rdx, rsi; unsigned __int16 *
0x18000c4d6  mov     rcx, r12; this
0x18000c4d9  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000c4de  mov     edi, eax
0x18000c4e0  test    eax, eax
0x18000c4e2  js      loc_18000C939
0x18000c4e8  jmp     loc_18000C7CE
0x18000c4ed  movzx   eax, word ptr [rsi]
0x18000c4f0  test    ax, ax
0x18000c4f3  jz      short loc_18000C51A
0x18000c4f5  mov     rcx, rsi; lpsz
0x18000c4f8  cmp     ax, 5Ch ; '\'
0x18000c4fc  jz      short loc_18000C511
0x18000c4fe  call    cs:__imp_CharNextW
0x18000c504  mov     rcx, rax
0x18000c507  movzx   eax, word ptr [rax]
0x18000c50a  test    ax, ax
0x18000c50d  jnz     short loc_18000C4F8
0x18000c50f  jmp     short loc_18000C51A
0x18000c511  test    rcx, rcx
0x18000c514  jnz     loc_18000C985
0x18000c51a  cmp     [rsp+2310h+var_22A8], edi
0x18000c51e  jz      loc_18000C6AF
0x18000c524  lea     rax, [rsp+2310h+hKey]
0x18000c529  mov     [rsp+2310h+hKey], rdi
0x18000c52e  mov     r14d, 2001Fh
0x18000c534  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000c539  mov     r9d, r14d; samDesired
0x18000c53c  xor     r8d, r8d; ulOptions
0x18000c53f  mov     rdx, rsi; lpSubKey
0x18000c542  mov     rcx, r15; hKey
0x18000c545  call    cs:__imp_RegOpenKeyExW
0x18000c54b  test    eax, eax
0x18000c54d  jnz     short loc_18000C570
0x18000c54f  mov     eax, edi
0x18000c551  test    rbx, rbx
0x18000c554  jz      short loc_18000C55F
0x18000c556  mov     rcx, rbx; hKey
0x18000c559  call    cs:__imp_RegCloseKey
0x18000c55f  mov     rbx, [rsp+2310h+hKey]
0x18000c564  mov     [rbp+2210h+var_2290], rbx
0x18000c568  test    eax, eax
0x18000c56a  jz      loc_18000C61B
0x18000c570  lea     rax, [rsp+2310h+hKey]
0x18000c575  mov     [rsp+2310h+hKey], rdi
0x18000c57a  mov     r9d, 20019h; samDesired
0x18000c580  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000c585  xor     r8d, r8d; ulOptions
0x18000c588  mov     rdx, rsi; lpSubKey
0x18000c58b  mov     rcx, r15; hKey
0x18000c58e  call    cs:__imp_RegOpenKeyExW
0x18000c594  test    eax, eax
0x18000c596  jnz     short loc_18000C5B5
0x18000c598  mov     eax, edi
0x18000c59a  test    rbx, rbx
0x18000c59d  jz      short loc_18000C5A8
0x18000c59f  mov     rcx, rbx; hKey
0x18000c5a2  call    cs:__imp_RegCloseKey
0x18000c5a8  mov     rbx, [rsp+2310h+hKey]
0x18000c5ad  mov     [rbp+2210h+var_2290], rbx
0x18000c5b1  test    eax, eax
0x18000c5b3  jz      short loc_18000C61B
0x18000c5b5  lea     rax, [rsp+2310h+hKey]
0x18000c5ba  mov     dword ptr [rsp+2310h+hKey], edi
0x18000c5be  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x18000c5c3  xor     r9d, r9d; lpClass
0x18000c5c6  lea     rax, [rsp+2310h+var_2298]
0x18000c5cb  mov     [rsp+2310h+var_2298], rdi
0x18000c5d0  mov     [rsp+2310h+var_22D8], rax; phkResult
0x18000c5d5  xor     r8d, r8d; Reserved
0x18000c5d8  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000c5dd  mov     rdx, rsi; lpSubKey
0x18000c5e0  mov     [rsp+2310h+samDesired], r14d; samDesired
0x18000c5e5  mov     rcx, r15; hKey
0x18000c5e8  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x18000c5ec  call    cs:__imp_RegCreateKeyExW
0x18000c5f2  test    eax, eax
0x18000c5f4  jnz     loc_18000C930
0x18000c5fa  mov     eax, edi
0x18000c5fc  test    rbx, rbx
0x18000c5ff  jz      short loc_18000C60A
0x18000c601  mov     rcx, rbx; hKey
0x18000c604  call    cs:__imp_RegCloseKey
0x18000c60a  mov     rbx, [rsp+2310h+var_2298]
0x18000c60f  mov     [rbp+2210h+var_2290], rbx
0x18000c613  test    eax, eax
0x18000c615  jnz     loc_18000C930
0x18000c61b  mov     rdx, rsi; unsigned __int16 *
0x18000c61e  mov     rcx, r12; this
0x18000c621  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000c626  xor     edx, edx
0x18000c628  mov     edi, eax
0x18000c62a  test    eax, eax
0x18000c62c  js      loc_18000C939
0x18000c632  cmp     word ptr [rsi], 3Dh ; '='
0x18000c636  jnz     short loc_18000C65A
0x18000c638  mov     r9, rsi; unsigned __int16 *
0x18000c63b  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x18000c63f  xor     r8d, r8d; unsigned __int16 *
0x18000c642  mov     rcx, r12; this
0x18000c645  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000c64a  mov     rbx, [rbp+2210h+var_2290]
0x18000c64e  xor     edx, edx
0x18000c650  mov     edi, eax
0x18000c652  test    eax, eax
0x18000c654  js      loc_18000C939
0x18000c65a  mov     r13d, [rsp+2310h+var_22A8]
0x18000c65f  cmp     word ptr [rsi], 7Bh ; '{'
0x18000c663  jnz     loc_18000C7CE
0x18000c669  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c66d  inc     rax
0x18000c670  cmp     [rsi+rax*2], dx
0x18000c674  jnz     short loc_18000C66D
0x18000c676  cmp     rax, 1
0x18000c67a  jnz     loc_18000C7CE
0x18000c680  mov     dword ptr [rsp+2310h+phkResult], edx; int
0x18000c684  mov     r9d, r13d; int
0x18000c687  mov     rdx, rsi; unsigned __int16 *
0x18000c68a  mov     r8, rbx; HKEY
0x18000c68d  mov     rcx, r12; this
0x18000c690  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000c695  mov     edi, eax
0x18000c697  test    eax, eax
0x18000c699  js      loc_18000C939
0x18000c69f  mov     rdx, rsi; unsigned __int16 *
0x18000c6a2  mov     rcx, r12; this
0x18000c6a5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000c6aa  jmp     loc_18000C4DE
0x18000c6af  mov     edi, [rbp+2210h+arg_20]
0x18000c6b5  xor     eax, eax
0x18000c6b7  test    edi, edi
  ... truncated ...
```
