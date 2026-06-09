# ATL::CRegParser::RegisterSubkeys(char *,HKEY__ *,int,int)

- ea: `0x180011b0c`
- end: `0x1800122d9`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEADPEAUHKEY__@@HH@Z`
- size: `1997`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, char *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18001167c`
- `0x180011b0c`

## callees

- `0x180003b70`
- `0x18000f804`
- `0x180010074`
- `0x180010e78`
- `0x180011060`
- `0x180011538`
- `0x180011b0c`
- `0x180012af8`
- `0x180014270`
- `0x180014300`

## import_xrefs

- `msvcrt!strncpy_s` at `0x180011fd7`
- `msvcrt!strncpy_s` at `0x180011fd7`
- `USER32!CharNextA` at `0x180011be6`
- `USER32!CharNextA` at `0x180011db2`
- `USER32!CharNextA` at `0x180011be6`
- `USER32!CharNextA` at `0x180011db2`
- `KERNEL32!lstrcmpiA` at `0x180011b85`
- `KERNEL32!lstrcmpiA` at `0x180011b98`
- `KERNEL32!lstrcmpiA` at `0x180011c10`
- `KERNEL32!lstrcmpiA` at `0x180011c77`
- `KERNEL32!lstrcmpiA` at `0x180011ca5`
- `KERNEL32!lstrcmpiA` at `0x18001213c`
- `KERNEL32!lstrcmpiA` at `0x180011b85`
- `KERNEL32!lstrcmpiA` at `0x180011b98`
- `KERNEL32!lstrcmpiA` at `0x180011c10`
- `KERNEL32!lstrcmpiA` at `0x180011c77`
- `KERNEL32!lstrcmpiA` at `0x180011ca5`
- `KERNEL32!lstrcmpiA` at `0x18001213c`
- `ADVAPI32!RegCreateKeyExA` at `0x180011e9e`
- `ADVAPI32!RegCreateKeyExA` at `0x180011e9e`
- `ADVAPI32!RegOpenKeyExA` at `0x180011d4f`
- `ADVAPI32!RegOpenKeyExA` at `0x180011df7`
- `ADVAPI32!RegOpenKeyExA` at `0x180011e40`
- `ADVAPI32!RegOpenKeyExA` at `0x180011f8b`
- `ADVAPI32!RegOpenKeyExA` at `0x180011d4f`
- `ADVAPI32!RegOpenKeyExA` at `0x180011df7`
- `ADVAPI32!RegOpenKeyExA` at `0x180011e40`
- `ADVAPI32!RegOpenKeyExA` at `0x180011f8b`
- `ADVAPI32!RegQueryInfoKeyA` at `0x18001211a`
- `ADVAPI32!RegQueryInfoKeyA` at `0x1800121ce`
- `ADVAPI32!RegQueryInfoKeyA` at `0x18001211a`
- `ADVAPI32!RegQueryInfoKeyA` at `0x1800121ce`
- `ADVAPI32!RegCloseKey` at `0x180011d85`
- `ADVAPI32!RegCloseKey` at `0x180011e0b`
- `ADVAPI32!RegCloseKey` at `0x180011e54`
- `ADVAPI32!RegCloseKey` at `0x180011eb6`
- `ADVAPI32!RegCloseKey` at `0x180011fa0`
- `ADVAPI32!RegCloseKey` at `0x1800121ec`
- `ADVAPI32!RegCloseKey` at `0x180012251`
- `ADVAPI32!RegCloseKey` at `0x18001228d`
- `ADVAPI32!RegCloseKey` at `0x18001229d`
- `ADVAPI32!RegCloseKey` at `0x180011d85`
- `ADVAPI32!RegCloseKey` at `0x180011e0b`
- `ADVAPI32!RegCloseKey` at `0x180011e54`
- `ADVAPI32!RegCloseKey` at `0x180011eb6`
- `ADVAPI32!RegCloseKey` at `0x180011fa0`
- `ADVAPI32!RegCloseKey` at `0x1800121ec`
- `ADVAPI32!RegCloseKey` at `0x180012251`
- `ADVAPI32!RegCloseKey` at `0x18001228d`
- `ADVAPI32!RegCloseKey` at `0x18001229d`
- `ADVAPI32!RegDeleteValueA` at `0x180011d6c`
- `ADVAPI32!RegDeleteValueA` at `0x180011d6c`

## string_xrefs

- `0x180011b8b`: `ForceRemove`
- `0x180011c67`: `NoRemove`
- `0x180011b7b`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(ATL::CRegParser *this, char *a2, HKEY a3, int a4, int a5)
{
  HKEY v5; // rbx
  int v6; // r12d
  HKEY v7; // r15
  __int64 result; // rax
  int Token; // edi
  int v12; // r14d
  int v13; // edi
  CHAR v14; // al
  const CHAR *v15; // rcx
  int v16; // r12d
  int v17; // eax
  LSTATUS v18; // eax
  HKEY v19; // r14
  LSTATUS v20; // eax
  int v21; // eax
  CHAR v22; // al
  const CHAR *v23; // rcx
  LSTATUS v24; // eax
  LSTATUS v25; // eax
  __int64 v26; // rax
  LSTATUS v27; // r14d
  int v28; // r15d
  errno_t v29; // eax
  __int64 v30; // rax
  __int64 v31; // r14
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
  char Destination[272]; // [rsp+B0h] [rbp-50h] BYREF
  CHAR ValueName[4096]; // [rsp+1C0h] [rbp+C0h] BYREF

  v5 = 0;
  v36 = a4;
  memset(v39, 0, sizeof(v39));
  v6 = a4;
  v7 = a3;
  v37 = a3;
  result = ATL::CRegParser::NextToken(this, a2);
  Token = result;
  if ( (int)result < 0 )
    return result;
  if ( *a2 == 125 )
    return (unsigned int)Token;
  while ( 1 )
  {
    v12 = lstrcmpiA(a2, "Delete");
    if ( !lstrcmpiA(a2, "ForceRemove") || !v12 )
    {
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_112;
      v13 = 0;
      if ( v6 )
      {
        v14 = *a2;
        v40 = 0;
        v41 = 0;
        v42 = 0;
        if ( !v14 )
          goto LABEL_13;
        v15 = a2;
        do
        {
          if ( v14 == 92 )
          {
            if ( !v15 )
              break;
            goto LABEL_118;
          }
          v15 = CharNextA(v15);
          v14 = *v15;
        }
        while ( *v15 );
LABEL_13:
        while ( lstrcmpiA(a2, (LPCSTR)(&ATL::CRegParser::rgszNeverDelete)[v13]) )
        {
          if ( ++v13 >= 12 )
          {
            v40 = v7;
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
LABEL_61:
          if ( *a2 != 123 )
            goto LABEL_93;
          v26 = -1;
          do
            ++v26;
          while ( a2[v26] );
          if ( v26 != 1 )
            goto LABEL_93;
          Token = ATL::CRegParser::RegisterSubkeys(this, a2, v5, v6, 0);
          if ( Token < 0 )
            goto LABEL_112;
          v21 = ATL::CRegParser::NextToken(this, a2);
          goto LABEL_35;
        }
      }
    }
    v16 = 1;
    if ( !lstrcmpiA(a2, "NoRemove") )
    {
      v16 = 0;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_112;
    }
    if ( !lstrcmpiA(a2, "Val") )
    {
      Token = ATL::CRegParser::NextToken(this, ValueName);
      if ( Token < 0 )
        goto LABEL_112;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_112;
      if ( *a2 != 61 )
        break;
      if ( v36 )
      {
        v41 = 0;
        v42 = 0;
        v40 = v7;
        v17 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)&v40, ValueName, a2);
LABEL_59:
        Token = v17;
        if ( v17 < 0 )
          goto LABEL_112;
        goto LABEL_60;
      }
      if ( !a5 && v16 )
      {
        hKey = 0;
        v18 = RegOpenKeyExA(v7, 0, 0, 0x20006u, &hKey);
        if ( v18 )
          goto LABEL_110;
        v19 = hKey;
        v20 = RegDeleteValueA(hKey, ValueName);
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
LABEL_35:
      Token = v21;
      if ( v21 < 0 )
        goto LABEL_112;
      goto LABEL_93;
    }
    v22 = *a2;
    if ( *a2 )
    {
      v23 = a2;
      while ( v22 != 92 )
      {
        v23 = CharNextA(v23);
        v22 = *v23;
        if ( !*v23 )
          goto LABEL_43;
      }
      if ( v23 )
        break;
    }
LABEL_43:
    if ( v36 )
    {
      hKey = 0;
      if ( RegOpenKeyExA(v7, a2, 0, 0x2001Fu, &hKey) )
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
        if ( RegOpenKeyExA(v7, a2, 0, 0x20019u, &hKey) )
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
          v18 = RegCreateKeyExA(v7, a2, 0, 0, 0, 0x2001Fu, 0, &phkResult, (LPDWORD)&hKey);
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
        goto LABEL_59;
      }
LABEL_60:
      v6 = v36;
      goto LABEL_61;
    }
    if ( a5 )
    {
      v27 = 2;
    }
    else
    {
      phkResult = 0;
      v27 = RegOpenKeyExA(v7, a2, 0, 0x20019u, &phkResult);
      if ( !v27 )
      {
        if ( v5 )
          v27 = RegCloseKey(v5);
        v5 = phkResult;
        v39[0] = phkResult;
      }
    }
    v28 = 1;
    if ( !v27 )
      v28 = a5;
    v29 = strncpy_s(Destination, 0x104u, a2, 0xFFFFFFFFFFFFFFFFuLL);
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
        v7 = v37;
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
      if ( !RegQueryInfoKeyA(v5, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      {
        if ( (_DWORD)hKey )
        {
          v31 = 0;
          while ( lstrcmpiA(Destination, (LPCSTR)(&ATL::CRegParser::rgszNeverDelete)[v31]) )
          {
            v31 = (unsigned int)(v31 + 1);
            if ( (int)v31 >= 12 )
            {
              if ( v16 )
              {
                ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v39, Destination);
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
    if ( !RegQueryInfoKeyA(v5, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      LOBYTE(v32) = (_DWORD)hKey != 0;
    if ( v5 )
    {
      v33 = RegCloseKey(v5);
      v5 = 0;
      v39[0] = 0;
      if ( v33 )
        return ATL::AtlHresultFromWin32(v33);
    }
    if ( !v16 )
      goto LABEL_92;
    v7 = v37;
    if ( !v32 )
    {
      v41 = 0;
      v42 = 0;
      v40 = v37;
      v18 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v40, Destination);
      if ( v18 )
        goto LABEL_110;
    }
LABEL_93:
    if ( *a2 == 125 )
      goto LABEL_112;
    v6 = v36;
  }
LABEL_118:
  if ( v5 )
    RegCloseKey(v5);
  return 2147614729LL;
}

```

## disassembly

```asm
0x180011b0c  push    rbp
0x180011b0e  push    rbx
0x180011b0f  push    rsi
0x180011b10  push    rdi
0x180011b11  push    r12
0x180011b13  push    r13
0x180011b15  push    r14
0x180011b17  push    r15
0x180011b19  lea     rbp, [rsp-10D8h]
0x180011b21  mov     eax, 11D8h
0x180011b26  call    _alloca_probe
0x180011b2b  sub     rsp, rax
0x180011b2e  mov     rax, cs:__security_cookie
0x180011b35  xor     rax, rsp
0x180011b38  mov     [rbp+1110h+var_50], rax
0x180011b3f  xor     ebx, ebx
0x180011b41  mov     [rsp+1210h+var_11A8], r9d
0x180011b46  mov     [rbp+1110h+var_1190], rbx
0x180011b4a  mov     r12d, r9d
0x180011b4d  mov     [rbp+1110h+var_1188], rbx
0x180011b51  mov     r15, r8
0x180011b54  mov     [rbp+1110h+var_1180], rbx
0x180011b58  mov     rsi, rdx
0x180011b5b  mov     [rsp+1210h+var_11A0], r8
0x180011b60  mov     r13, rcx
0x180011b63  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x180011b68  mov     edi, eax
0x180011b6a  test    eax, eax
0x180011b6c  js      loc_180012259
0x180011b72  cmp     byte ptr [rsi], 7Dh ; '}'
0x180011b75  jz      loc_180012257
0x180011b7b  lea     rdx, String2; "Delete"
0x180011b82  mov     rcx, rsi; lpString1
0x180011b85  call    cs:__imp_lstrcmpiA
0x180011b8b  lea     rdx, aForceremove; "ForceRemove"
0x180011b92  mov     rcx, rsi; lpString1
0x180011b95  mov     r14d, eax
0x180011b98  call    cs:__imp_lstrcmpiA
0x180011b9e  xor     edi, edi
0x180011ba0  test    eax, eax
0x180011ba2  jz      short loc_180011BAD
0x180011ba4  test    r14d, r14d
0x180011ba7  jnz     loc_180011C67
0x180011bad  mov     rdx, rsi; char *
0x180011bb0  mov     rcx, r13; this
0x180011bb3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x180011bb8  mov     edi, eax
0x180011bba  test    eax, eax
0x180011bbc  js      loc_180012249
0x180011bc2  xor     edi, edi
0x180011bc4  test    r12d, r12d
0x180011bc7  jz      loc_180011C67
0x180011bcd  mov     al, [rsi]
0x180011bcf  mov     [rbp+1110h+var_1178], rdi
0x180011bd3  mov     [rbp+1110h+var_1170], rdi
0x180011bd7  mov     [rbp+1110h+var_1168], rdi
0x180011bdb  test    al, al
0x180011bdd  jz      short loc_180011C00
0x180011bdf  mov     rcx, rsi; lpsz
0x180011be2  cmp     al, 5Ch ; '\'
0x180011be4  jz      short loc_180011BF7
0x180011be6  call    cs:__imp_CharNextA
0x180011bec  mov     rcx, rax
0x180011bef  mov     al, [rax]
0x180011bf1  test    al, al
0x180011bf3  jnz     short loc_180011BE2
0x180011bf5  jmp     short loc_180011C00
0x180011bf7  test    rcx, rcx
0x180011bfa  jnz     loc_180012295
0x180011c00  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBDB; char const * const near * const ATL::CRegParser::rgszNeverDelete
0x180011c07  mov     edx, edi
0x180011c09  mov     rcx, rsi; lpString1
0x180011c0c  mov     rdx, [rax+rdx*8]; lpString2
0x180011c10  call    cs:__imp_lstrcmpiA
0x180011c16  test    eax, eax
0x180011c18  jz      short loc_180011C31
0x180011c1a  inc     edi
0x180011c1c  cmp     edi, 0Ch
0x180011c1f  jl      short loc_180011C00
0x180011c21  mov     rdx, rsi; char *
0x180011c24  mov     [rbp+1110h+var_1178], r15
0x180011c28  lea     rcx, [rbp+1110h+var_1178]; this
0x180011c2c  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBD@Z; ATL::CRegKey::RecurseDeleteKey(char const *)
0x180011c31  xor     edi, edi
0x180011c33  test    r14d, r14d
0x180011c36  jnz     short loc_180011C67
0x180011c38  mov     rdx, rsi; char *
0x180011c3b  mov     rcx, r13; this
0x180011c3e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x180011c43  mov     edi, eax
0x180011c45  test    eax, eax
0x180011c47  js      loc_180012249
0x180011c4d  mov     rdx, rsi; char *
0x180011c50  mov     rcx, r13; this
0x180011c53  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::SkipAssignment(char *)
0x180011c58  mov     edi, eax
0x180011c5a  test    eax, eax
0x180011c5c  js      loc_180012249
0x180011c62  jmp     loc_180011F0C
0x180011c67  lea     rdx, aNoremove; "NoRemove"
0x180011c6e  mov     rcx, rsi; lpString1
0x180011c71  mov     r12d, 1
0x180011c77  call    cs:__imp_lstrcmpiA
0x180011c7d  test    eax, eax
0x180011c7f  jnz     short loc_180011C9B
0x180011c81  mov     rdx, rsi; char *
0x180011c84  mov     rcx, r13; this
0x180011c87  mov     r12d, edi
0x180011c8a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x180011c8f  mov     edi, eax
0x180011c91  test    eax, eax
0x180011c93  js      loc_180012249
0x180011c99  xor     edi, edi
0x180011c9b  lea     rdx, aVal; "Val"
0x180011ca2  mov     rcx, rsi; lpString1
0x180011ca5  call    cs:__imp_lstrcmpiA
0x180011cab  test    eax, eax
0x180011cad  jnz     loc_180011DA5
0x180011cb3  lea     rdx, [rbp+1110h+ValueName]; char *
0x180011cba  mov     rcx, r13; this
0x180011cbd  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x180011cc2  mov     edi, eax
0x180011cc4  test    eax, eax
0x180011cc6  js      loc_180012249
0x180011ccc  mov     rdx, rsi; char *
0x180011ccf  mov     rcx, r13; this
0x180011cd2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x180011cd7  mov     edi, eax
0x180011cd9  test    eax, eax
0x180011cdb  js      loc_180012249
0x180011ce1  cmp     byte ptr [rsi], 3Dh ; '='
0x180011ce4  jnz     loc_180012295
0x180011cea  cmp     [rsp+1210h+var_11A8], 0
0x180011cef  jz      short loc_180011D20
0x180011cf1  mov     r9, rsi; char *
0x180011cf4  mov     [rbp+1110h+var_1170], 0
0x180011cfc  lea     r8, [rbp+1110h+ValueName]; char *
0x180011d03  mov     [rbp+1110h+var_1168], 0
0x180011d0b  lea     rdx, [rbp+1110h+var_1178]; struct ATL::CRegKey *
0x180011d0f  mov     [rbp+1110h+var_1178], r15
0x180011d13  mov     rcx, r13; this
0x180011d16  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBDPEAD@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,char const *,char *)
0x180011d1b  jmp     loc_180011EFD
0x180011d20  cmp     [rbp+1110h+arg_20], 0
0x180011d27  jnz     short loc_180011D8B
0x180011d29  test    r12d, r12d
0x180011d2c  jz      short loc_180011D8B
0x180011d2e  lea     rax, [rsp+1210h+hKey]
0x180011d33  mov     [rsp+1210h+hKey], 0
0x180011d3c  mov     r9d, 20006h; samDesired
0x180011d42  mov     [rsp+1210h+phkResult], rax; phkResult
0x180011d47  xor     r8d, r8d; ulOptions
0x180011d4a  xor     edx, edx; lpSubKey
0x180011d4c  mov     rcx, r15; hKey
0x180011d4f  call    cs:__imp_RegOpenKeyExA
0x180011d55  test    eax, eax
0x180011d57  jnz     loc_180012240
0x180011d5d  mov     r14, [rsp+1210h+hKey]
0x180011d62  lea     rdx, [rbp+1110h+ValueName]; lpValueName
0x180011d69  mov     rcx, r14; hKey
0x180011d6c  call    cs:__imp_RegDeleteValueA
0x180011d72  test    eax, 0FFFFFFFDh
0x180011d77  jnz     loc_18001227C
0x180011d7d  test    r14, r14
0x180011d80  jz      short loc_180011D8B
0x180011d82  mov     rcx, r14; hKey
0x180011d85  call    cs:__imp_RegCloseKey
0x180011d8b  mov     rdx, rsi; char *
0x180011d8e  mov     rcx, r13; this
0x180011d91  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::SkipAssignment(char *)
0x180011d96  mov     edi, eax
0x180011d98  test    eax, eax
0x180011d9a  js      loc_180012249
0x180011da0  jmp     loc_18001209E
0x180011da5  mov     al, [rsi]
0x180011da7  test    al, al
0x180011da9  jz      short loc_180011DCC
0x180011dab  mov     rcx, rsi; lpsz
0x180011dae  cmp     al, 5Ch ; '\'
0x180011db0  jz      short loc_180011DC3
0x180011db2  call    cs:__imp_CharNextA
0x180011db8  mov     rcx, rax
0x180011dbb  mov     al, [rax]
0x180011dbd  test    al, al
0x180011dbf  jnz     short loc_180011DAE
0x180011dc1  jmp     short loc_180011DCC
0x180011dc3  test    rcx, rcx
0x180011dc6  jnz     loc_180012295
0x180011dcc  cmp     [rsp+1210h+var_11A8], edi
0x180011dd0  jz      loc_180011F5F
0x180011dd6  lea     rax, [rsp+1210h+hKey]
0x180011ddb  mov     [rsp+1210h+hKey], rdi
0x180011de0  mov     r14d, 2001Fh
0x180011de6  mov     [rsp+1210h+phkResult], rax; phkResult
0x180011deb  mov     r9d, r14d; samDesired
0x180011dee  xor     r8d, r8d; ulOptions
0x180011df1  mov     rdx, rsi; lpSubKey
0x180011df4  mov     rcx, r15; hKey
0x180011df7  call    cs:__imp_RegOpenKeyExA
0x180011dfd  test    eax, eax
0x180011dff  jnz     short loc_180011E22
0x180011e01  mov     eax, edi
0x180011e03  test    rbx, rbx
0x180011e06  jz      short loc_180011E11
0x180011e08  mov     rcx, rbx; hKey
0x180011e0b  call    cs:__imp_RegCloseKey
0x180011e11  mov     rbx, [rsp+1210h+hKey]
0x180011e16  mov     [rbp+1110h+var_1190], rbx
0x180011e1a  test    eax, eax
0x180011e1c  jz      loc_180011ECD
0x180011e22  lea     rax, [rsp+1210h+hKey]
0x180011e27  mov     [rsp+1210h+hKey], rdi
0x180011e2c  mov     r9d, 20019h; samDesired
0x180011e32  mov     [rsp+1210h+phkResult], rax; phkResult
0x180011e37  xor     r8d, r8d; ulOptions
0x180011e3a  mov     rdx, rsi; lpSubKey
0x180011e3d  mov     rcx, r15; hKey
0x180011e40  call    cs:__imp_RegOpenKeyExA
0x180011e46  test    eax, eax
0x180011e48  jnz     short loc_180011E67
0x180011e4a  mov     eax, edi
0x180011e4c  test    rbx, rbx
0x180011e4f  jz      short loc_180011E5A
0x180011e51  mov     rcx, rbx; hKey
0x180011e54  call    cs:__imp_RegCloseKey
0x180011e5a  mov     rbx, [rsp+1210h+hKey]
0x180011e5f  mov     [rbp+1110h+var_1190], rbx
0x180011e63  test    eax, eax
0x180011e65  jz      short loc_180011ECD
0x180011e67  lea     rax, [rsp+1210h+hKey]
0x180011e6c  mov     dword ptr [rsp+1210h+hKey], edi
0x180011e70  mov     [rsp+1210h+lpdwDisposition], rax; lpdwDisposition
0x180011e75  xor     r9d, r9d; lpClass
0x180011e78  lea     rax, [rsp+1210h+var_1198]
0x180011e7d  mov     [rsp+1210h+var_1198], rdi
0x180011e82  mov     [rsp+1210h+var_11D8], rax; phkResult
0x180011e87  xor     r8d, r8d; Reserved
0x180011e8a  mov     [rsp+1210h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180011e8f  mov     rdx, rsi; lpSubKey
0x180011e92  mov     [rsp+1210h+samDesired], r14d; samDesired
0x180011e97  mov     rcx, r15; hKey
0x180011e9a  mov     dword ptr [rsp+1210h+phkResult], edi; dwOptions
0x180011e9e  call    cs:__imp_RegCreateKeyExA
0x180011ea4  test    eax, eax
0x180011ea6  jnz     loc_180012240
0x180011eac  mov     eax, edi
0x180011eae  test    rbx, rbx
0x180011eb1  jz      short loc_180011EBC
0x180011eb3  mov     rcx, rbx; hKey
0x180011eb6  call    cs:__imp_RegCloseKey
0x180011ebc  mov     rbx, [rsp+1210h+var_1198]
0x180011ec1  mov     [rbp+1110h+var_1190], rbx
0x180011ec5  test    eax, eax
0x180011ec7  jnz     loc_180012240
0x180011ecd  mov     rdx, rsi; char *
0x180011ed0  mov     rcx, r13; this
0x180011ed3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x180011ed8  mov     edi, eax
0x180011eda  test    eax, eax
0x180011edc  js      loc_180012249
0x180011ee2  cmp     byte ptr [rsi], 3Dh ; '='
0x180011ee5  jnz     short loc_180011F07
0x180011ee7  mov     r9, rsi; char *
0x180011eea  lea     rdx, [rbp+1110h+var_1190]; struct ATL::CRegKey *
0x180011eee  xor     r8d, r8d; char *
0x180011ef1  mov     rcx, r13; this
0x180011ef4  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBDPEAD@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,char const *,char *)
0x180011ef9  mov     rbx, [rbp+1110h+var_1190]
0x180011efd  mov     edi, eax
0x180011eff  test    eax, eax
0x180011f01  js      loc_180012249
0x180011f07  mov     r12d, [rsp+1210h+var_11A8]
0x180011f0c  cmp     byte ptr [rsi], 7Bh ; '{'
0x180011f0f  jnz     loc_18001209E
0x180011f15  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011f19  inc     rax
0x180011f1c  cmp     byte ptr [rsi+rax], 0
0x180011f20  jnz     short loc_180011F19
0x180011f22  cmp     rax, 1
0x180011f26  jnz     loc_18001209E
0x180011f2c  mov     r9d, r12d; int
0x180011f2f  mov     dword ptr [rsp+1210h+phkResult], 0; int
0x180011f37  mov     r8, rbx; HKEY
0x180011f3a  mov     rdx, rsi; char *
0x180011f3d  mov     rcx, r13; this
0x180011f40  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEADPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(char *,HKEY__ *,int,int)
0x180011f45  mov     edi, eax
0x180011f47  test    eax, eax
0x180011f49  js      loc_180012249
0x180011f4f  mov     rdx, rsi; char *
0x180011f52  mov     rcx, r13; this
0x180011f55  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x180011f5a  jmp     loc_180011D96
0x180011f5f  mov     edi, [rbp+1110h+arg_20]
0x180011f65  test    edi, edi
0x180011f67  jnz     short loc_180011FB4
0x180011f69  lea     rax, [rsp+1210h+var_1198]
0x180011f6e  mov     [rsp+1210h+var_1198], 0
0x180011f77  mov     r9d, 20019h; samDesired
0x180011f7d  mov     [rsp+1210h+phkResult], rax; phkResult
  ... truncated ...
```
