# PfXpGetBootLoaderNlsFileNames

- ea: `0x1800943e0`
- end: `0x18009464b`
- name: `PfXpGetBootLoaderNlsFileNames`
- size: `619`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180093a8c`

## callees

- `0x18001a400`
- `0x1800943e0`
- `0x180094d70`
- `0x180095ba0`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800945fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009460c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009461c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800945fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009460c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009461c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094450`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009447c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800944a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094450`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009447c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800944a8`

## pseudocode

```c
__int64 __fastcall PfXpGetBootLoaderNlsFileNames(__int64 a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rdi
  __int64 v4; // r8
  __int64 v5; // r8
  DWORD v7[2]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v10; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t pszSrc[264]; // [rsp+260h] [rbp+160h] BYREF

  v7[0] = 0;
  v7[1] = 0;
  hKey = 0;
  phkResult = 0;
  v10 = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Nls", 0, 0x20019u, &hKey);
  if ( !v2 )
  {
    v2 = RegOpenKeyExW(hKey, L"CodePage", 0, 0x20019u, &phkResult);
    if ( !v2 )
    {
      v2 = RegOpenKeyExW(hKey, L"Language", 0, 0x20019u, &v10);
      if ( !v2 )
      {
        v3 = -1;
        if ( (unsigned int)PfXpQueryNlsFileName(phkResult, v7) )
          goto LABEL_29;
        if ( (unsigned int)PfXpLocateNlsFile(pszSrc, FileName) )
          goto LABEL_29;
        v4 = -1;
        do
          ++v4;
        while ( FileName[v4] );
        v2 = PfXpAddToPathList(a1);
        if ( !v2 )
        {
LABEL_29:
          if ( (unsigned int)PfXpQueryNlsFileName(phkResult, v7) )
            goto LABEL_28;
          if ( (unsigned int)PfXpLocateNlsFile(pszSrc, FileName) )
            goto LABEL_28;
          v5 = -1;
          do
            ++v5;
          while ( FileName[v5] );
          v2 = PfXpAddToPathList(a1);
          if ( !v2 )
          {
LABEL_28:
            if ( (unsigned int)PfXpQueryNlsFileName(v10, v7) || (unsigned int)PfXpLocateNlsFile(pszSrc, FileName) )
              goto LABEL_18;
            do
              ++v3;
            while ( FileName[v3] );
            v2 = PfXpAddToPathList(a1);
            if ( !v2 )
LABEL_18:
              v2 = 0;
          }
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v10 )
    RegCloseKey(v10);
  return v2;
}

```

## disassembly

```asm
0x1800943e0  mov     [rsp-8+arg_8], rbx
0x1800943e5  mov     [rsp-8+arg_10], rsi
0x1800943ea  push    rbp
0x1800943eb  push    rdi
0x1800943ec  push    r14
0x1800943ee  lea     rbp, [rsp-380h]
0x1800943f6  sub     rsp, 480h
0x1800943fd  mov     rax, cs:__security_cookie
0x180094404  xor     rax, rsp
0x180094407  mov     [rbp+390h+var_20], rax
0x18009440e  xor     r14d, r14d
0x180094411  lea     rax, [rsp+490h+hKey]
0x180094416  mov     rsi, rcx
0x180094419  mov     [rsp+490h+var_460], r14d
0x18009441e  mov     edi, 20019h
0x180094423  mov     [rsp+490h+var_45C], r14d
0x180094428  mov     r9d, edi; samDesired
0x18009442b  mov     [rsp+490h+hKey], r14
0x180094430  xor     r8d, r8d; ulOptions
0x180094433  mov     [rsp+490h+var_450], r14
0x180094438  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\Nls"
0x18009443f  mov     [rsp+490h+var_448], r14
0x180094444  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009444b  mov     [rsp+490h+phkResult], rax; phkResult
0x180094450  call    cs:__imp_RegOpenKeyExW
0x180094456  mov     ebx, eax
0x180094458  test    eax, eax
0x18009445a  jnz     loc_1800945F2
0x180094460  mov     rcx, [rsp+490h+hKey]; hKey
0x180094465  lea     rax, [rsp+490h+var_450]
0x18009446a  mov     r9d, edi; samDesired
0x18009446d  mov     [rsp+490h+phkResult], rax; phkResult
0x180094472  xor     r8d, r8d; ulOptions
0x180094475  lea     rdx, aCodepage; "CodePage"
0x18009447c  call    cs:__imp_RegOpenKeyExW
0x180094482  mov     ebx, eax
0x180094484  test    eax, eax
0x180094486  jnz     loc_1800945F2
0x18009448c  mov     rcx, [rsp+490h+hKey]; hKey
0x180094491  lea     rax, [rsp+490h+var_448]
0x180094496  mov     r9d, edi; samDesired
0x180094499  mov     [rsp+490h+phkResult], rax; phkResult
0x18009449e  xor     r8d, r8d; ulOptions
0x1800944a1  lea     rdx, aLanguage; "Language"
0x1800944a8  call    cs:__imp_RegOpenKeyExW
0x1800944ae  mov     ebx, eax
0x1800944b0  test    eax, eax
0x1800944b2  jnz     loc_1800945F2
0x1800944b8  mov     rcx, [rsp+490h+var_450]; hKey
0x1800944bd  lea     rax, [rsp+490h+var_460]
0x1800944c2  lea     r8, [rbp+390h+pszSrc]
0x1800944c9  mov     [rsp+490h+phkResult], rax; LPDWORD
0x1800944ce  lea     rdx, aAcp; "ACP"
0x1800944d5  call    PfXpQueryNlsFileName
0x1800944da  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800944de  test    eax, eax
0x1800944e0  jnz     short loc_180094525
0x1800944e2  lea     r9, [rsp+490h+var_45C]
0x1800944e7  lea     rdx, [rsp+490h+FileName]; lpFileName
0x1800944ec  lea     rcx, [rbp+390h+pszSrc]; pszSrc
0x1800944f3  call    PfXpLocateNlsFile
0x1800944f8  test    eax, eax
0x1800944fa  jnz     short loc_180094525
0x1800944fc  lea     rax, [rsp+490h+FileName]
0x180094501  mov     r8, rdi
0x180094504  inc     r8
0x180094507  cmp     [rax+r8*2], r14w
0x18009450c  jnz     short loc_180094504
0x18009450e  lea     rdx, [rsp+490h+FileName]
0x180094513  mov     rcx, rsi
0x180094516  call    PfXpAddToPathList
0x18009451b  mov     ebx, eax
0x18009451d  test    eax, eax
0x18009451f  jnz     loc_1800945F2
0x180094525  mov     rcx, [rsp+490h+var_450]; hKey
0x18009452a  lea     rax, [rsp+490h+var_460]
0x18009452f  lea     r8, [rbp+390h+pszSrc]
0x180094536  mov     [rsp+490h+phkResult], rax; LPDWORD
0x18009453b  lea     rdx, aOemcp; "OEMCP"
0x180094542  call    PfXpQueryNlsFileName
0x180094547  test    eax, eax
0x180094549  jnz     short loc_18009458A
0x18009454b  lea     r9, [rsp+490h+var_45C]
0x180094550  lea     rdx, [rsp+490h+FileName]; lpFileName
0x180094555  lea     rcx, [rbp+390h+pszSrc]; pszSrc
0x18009455c  call    PfXpLocateNlsFile
0x180094561  test    eax, eax
0x180094563  jnz     short loc_18009458A
0x180094565  lea     rax, [rsp+490h+FileName]
0x18009456a  mov     r8, rdi
0x18009456d  inc     r8
0x180094570  cmp     [rax+r8*2], r14w
0x180094575  jnz     short loc_18009456D
0x180094577  lea     rdx, [rsp+490h+FileName]
0x18009457c  mov     rcx, rsi
0x18009457f  call    PfXpAddToPathList
0x180094584  mov     ebx, eax
0x180094586  test    eax, eax
0x180094588  jnz     short loc_1800945F2
0x18009458a  mov     rcx, [rsp+490h+var_448]; hKey
0x18009458f  lea     rax, [rsp+490h+var_460]
0x180094594  lea     r8, [rbp+390h+pszSrc]
0x18009459b  mov     [rsp+490h+phkResult], rax; LPDWORD
0x1800945a0  lea     rdx, aDefault; "Default"
0x1800945a7  call    PfXpQueryNlsFileName
0x1800945ac  test    eax, eax
0x1800945ae  jnz     short loc_1800945EF
0x1800945b0  lea     r9, [rsp+490h+var_45C]
0x1800945b5  lea     rdx, [rsp+490h+FileName]; lpFileName
0x1800945ba  lea     rcx, [rbp+390h+pszSrc]; pszSrc
0x1800945c1  call    PfXpLocateNlsFile
0x1800945c6  test    eax, eax
0x1800945c8  jnz     short loc_1800945EF
0x1800945ca  lea     rax, [rsp+490h+FileName]
0x1800945cf  inc     rdi
0x1800945d2  cmp     [rax+rdi*2], r14w
0x1800945d7  jnz     short loc_1800945CF
0x1800945d9  mov     r8d, edi
0x1800945dc  lea     rdx, [rsp+490h+FileName]
0x1800945e1  mov     rcx, rsi
0x1800945e4  call    PfXpAddToPathList
0x1800945e9  mov     ebx, eax
0x1800945eb  test    eax, eax
0x1800945ed  jnz     short loc_1800945F2
0x1800945ef  mov     ebx, r14d
0x1800945f2  mov     rcx, [rsp+490h+hKey]; hKey
0x1800945f7  test    rcx, rcx
0x1800945fa  jz      short loc_180094602
0x1800945fc  call    cs:__imp_RegCloseKey
0x180094602  mov     rcx, [rsp+490h+var_450]; hKey
0x180094607  test    rcx, rcx
0x18009460a  jz      short loc_180094612
0x18009460c  call    cs:__imp_RegCloseKey
0x180094612  mov     rcx, [rsp+490h+var_448]; hKey
0x180094617  test    rcx, rcx
0x18009461a  jz      short loc_180094622
0x18009461c  call    cs:__imp_RegCloseKey
0x180094622  mov     eax, ebx
0x180094624  mov     rcx, [rbp+390h+var_20]
0x18009462b  xor     rcx, rsp; StackCookie
0x18009462e  call    __security_check_cookie
0x180094633  lea     r11, [rsp+490h+var_10]
0x18009463b  mov     rbx, [r11+28h]
0x18009463f  mov     rsi, [r11+30h]
0x180094643  mov     rsp, r11
0x180094646  pop     r14
0x180094648  pop     rdi
0x180094649  pop     rbp
0x18009464a  retn
```
