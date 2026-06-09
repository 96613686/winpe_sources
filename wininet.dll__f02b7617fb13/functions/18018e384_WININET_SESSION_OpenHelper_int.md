# WININET_SESSION::OpenHelper(int)

- ea: `0x18018e384`
- end: `0x18018e6bb`
- name: `?OpenHelper@WININET_SESSION@@AEAAHH@Z`
- size: `823`
- prototype: `__int64 __fastcall(WININET_SESSION *__hidden this, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18018e288`

## callees

- `0x18012ad4c`
- `0x18014a7a0`
- `0x18018d35c`
- `0x18018e384`
- `0x1801e1790`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18018e668`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18018e681`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18018e692`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18018e668`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18018e681`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18018e692`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18018e5bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18018e5ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18018e5bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18018e5ff`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18018e3fe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18018e452`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18018e48b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18018e4df`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18018e531`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18018e585`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18018e3fe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18018e452`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18018e48b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18018e4df`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18018e531`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18018e585`

## pseudocode

```c
__int64 __fastcall WININET_SESSION::OpenHelper(WININET_SESSION *this, int a2)
{
  HKEY *phkResult; // r15
  int v5; // ebp
  unsigned int Key; // eax
  HKEY *v7; // r14
  unsigned int v8; // eax
  const WCHAR *v9; // rdi
  unsigned int v10; // eax
  unsigned int v11; // edi
  HKEY v12; // rcx
  int v13; // esi
  __int64 v14; // rax
  HKEY v15; // rcx
  HKEY v16; // rcx
  DWORD cbData; // [rsp+50h] [rbp-58h] BYREF
  DWORD Type; // [rsp+54h] [rbp-54h] BYREF

  cbData = 2048;
  Type = 0;
  phkResult = (HKEY *)((char *)this + 528);
  v5 = IsProcessLessThanMediumIL();
  Key = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Passport",
          0,
          0,
          0,
          0x2001Fu,
          0,
          phkResult,
          0);
  if ( Key )
  {
    if ( (BYTE1(xmmword_180266B50) & 4) != 0 )
      WPP_SF_d(522, 36, WPP_88e9b8d46a55322969ac94ecd507bd70_Traceguids, Key);
    RegCreateKeyExW(
      HKEY_LOCAL_MACHINE,
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Passport",
      0,
      0,
      0,
      0x20019u,
      0,
      (PHKEY)this + 66,
      0);
  }
  v7 = (HKEY *)((char *)this + 536);
  v8 = RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Passport",
         0,
         0,
         0,
         0x2001Fu,
         0,
         (PHKEY)this + 67,
         0);
  if ( v8 )
  {
    if ( (BYTE1(xmmword_180266B50) & 4) != 0 )
      WPP_SF_d(522, 37, WPP_88e9b8d46a55322969ac94ecd507bd70_Traceguids, v8);
    RegCreateKeyExW(
      HKEY_CURRENT_USER,
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Passport",
      0,
      0,
      0,
      0x20019u,
      0,
      (PHKEY)this + 67,
      0);
  }
  if ( *v7 )
  {
    v9 = L"LowDAMap";
    if ( !v5 )
      v9 = L"DAMap";
    v10 = RegCreateKeyExW(*v7, v9, 0, 0, 0, 0x2001Fu, 0, (PHKEY)this + 68, 0);
    if ( v10 )
    {
      if ( (BYTE1(xmmword_180266B50) & 4) != 0 )
        WPP_SF_d(522, 38, WPP_88e9b8d46a55322969ac94ecd507bd70_Traceguids, v10);
      RegCreateKeyExW(*v7, v9, 0, 0, 0, 0x20019u, 0, (PHKEY)this + 68, 0);
    }
  }
  v11 = 1;
  if ( *v7 && !RegQueryValueExW(*v7, L"LoginServerUrl", 0, &Type, (LPBYTE)this + 552, &cbData)
    || (v12 = *phkResult, v13 = 0, cbData = 2048, v12)
    && !RegQueryValueExW(v12, L"LoginServerUrl", 0, &Type, (LPBYTE)this + 552, &cbData) )
  {
    v13 = 1;
    *((_WORD *)this + ((unsigned __int64)cbData >> 1) + 276) = 0;
  }
  if ( !a2 )
  {
    if ( !v13 )
      goto LABEL_36;
    v14 = -1;
    do
      ++v14;
    while ( *((_WORD *)this + v14 + 276) );
    if ( !v14 )
    {
LABEL_36:
      if ( !(unsigned int)WININET_SESSION::GetDAInfoFromPPNexus(this, 0, 0, 0, 0, 0) )
      {
        v15 = (HKEY)*((_QWORD *)this + 68);
        v11 = 0;
        if ( v15 )
        {
          RegCloseKey(v15);
          *((_QWORD *)this + 68) = 0;
        }
        v16 = (HKEY)*((_QWORD *)this + 67);
        if ( v16 )
        {
          RegCloseKey(v16);
          *v7 = 0;
        }
        if ( *phkResult )
        {
          RegCloseKey(*phkResult);
          *phkResult = 0;
        }
      }
    }
  }
  return v11;
}

```

## disassembly

```asm
0x18018e384  push    rbx
0x18018e386  push    rbp
0x18018e387  push    rsi
0x18018e388  push    rdi
0x18018e389  push    r12
0x18018e38b  push    r13
0x18018e38d  push    r14
0x18018e38f  push    r15
0x18018e391  sub     rsp, 68h
0x18018e395  mov     rax, cs:__security_cookie
0x18018e39c  xor     rax, rsp
0x18018e39f  mov     [rsp+0A8h+var_50], rax
0x18018e3a4  xor     r13d, r13d
0x18018e3a7  mov     [rsp+0A8h+cbData], 800h
0x18018e3af  mov     [rsp+0A8h+Type], r13d
0x18018e3b4  mov     r12d, edx
0x18018e3b7  mov     rbx, rcx
0x18018e3ba  call    IsProcessLessThanMediumIL
0x18018e3bf  mov     [rsp+0A8h+lpdwDisposition], r13; lpdwDisposition
0x18018e3c4  lea     r15, [rbx+210h]
0x18018e3cb  mov     [rsp+0A8h+phkResult], r15; phkResult
0x18018e3d0  lea     rdi, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18018e3d7  mov     [rsp+0A8h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18018e3dc  mov     r14, 0FFFFFFFF80000002h
0x18018e3e3  mov     [rsp+0A8h+samDesired], 2001Fh; samDesired
0x18018e3eb  xor     r9d, r9d; lpClass
0x18018e3ee  xor     r8d, r8d; Reserved
0x18018e3f1  mov     [rsp+0A8h+dwOptions], r13d; dwOptions
0x18018e3f6  mov     rdx, rdi; lpSubKey
0x18018e3f9  mov     rcx, r14; hKey
0x18018e3fc  mov     ebp, eax
0x18018e3fe  call    cs:__imp_RegCreateKeyExW
0x18018e404  mov     esi, 20019h
0x18018e409  test    eax, eax
0x18018e40b  jz      short loc_18018E458
0x18018e40d  test    byte ptr cs:xmmword_180266B50+1, 4
0x18018e414  jz      short loc_18018E42E
0x18018e416  lea     edx, [r13+24h]
0x18018e41a  mov     ecx, 20Ah
0x18018e41f  mov     r9d, eax
0x18018e422  lea     r8, WPP_88e9b8d46a55322969ac94ecd507bd70_Traceguids
0x18018e429  call    WPP_SF_d
0x18018e42e  mov     [rsp+0A8h+lpdwDisposition], r13; lpdwDisposition
0x18018e433  xor     r9d, r9d; lpClass
0x18018e436  mov     [rsp+0A8h+phkResult], r15; phkResult
0x18018e43b  xor     r8d, r8d; Reserved
0x18018e43e  mov     [rsp+0A8h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18018e443  mov     rdx, rdi; lpSubKey
0x18018e446  mov     [rsp+0A8h+samDesired], esi; samDesired
0x18018e44a  mov     rcx, r14; hKey
0x18018e44d  mov     [rsp+0A8h+dwOptions], r13d; dwOptions
0x18018e452  call    cs:__imp_RegCreateKeyExW
0x18018e458  mov     [rsp+0A8h+lpdwDisposition], r13; lpdwDisposition
0x18018e45d  lea     r14, [rbx+218h]
0x18018e464  mov     [rsp+0A8h+phkResult], r14; phkResult
0x18018e469  xor     r9d, r9d; lpClass
0x18018e46c  mov     [rsp+0A8h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18018e471  xor     r8d, r8d; Reserved
0x18018e474  mov     [rsp+0A8h+samDesired], 2001Fh; samDesired
0x18018e47c  mov     rdx, rdi; lpSubKey
0x18018e47f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18018e486  mov     [rsp+0A8h+dwOptions], r13d; dwOptions
0x18018e48b  call    cs:__imp_RegCreateKeyExW
0x18018e491  test    eax, eax
0x18018e493  jz      short loc_18018E4E5
0x18018e495  test    byte ptr cs:xmmword_180266B50+1, 4
0x18018e49c  jz      short loc_18018E4B7
0x18018e49e  mov     edx, 25h ; '%'
0x18018e4a3  lea     r8, WPP_88e9b8d46a55322969ac94ecd507bd70_Traceguids
0x18018e4aa  mov     ecx, 20Ah
0x18018e4af  mov     r9d, eax
0x18018e4b2  call    WPP_SF_d
0x18018e4b7  mov     [rsp+0A8h+lpdwDisposition], r13; lpdwDisposition
0x18018e4bc  xor     r9d, r9d; lpClass
0x18018e4bf  mov     [rsp+0A8h+phkResult], r14; phkResult
0x18018e4c4  xor     r8d, r8d; Reserved
0x18018e4c7  mov     [rsp+0A8h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18018e4cc  mov     rdx, rdi; lpSubKey
0x18018e4cf  mov     [rsp+0A8h+samDesired], esi; samDesired
0x18018e4d3  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18018e4da  mov     [rsp+0A8h+dwOptions], r13d; dwOptions
0x18018e4df  call    cs:__imp_RegCreateKeyExW
0x18018e4e5  mov     rcx, [r14]; hKey
0x18018e4e8  test    rcx, rcx
0x18018e4eb  jz      loc_18018E58B
0x18018e4f1  mov     [rsp+0A8h+lpdwDisposition], r13; lpdwDisposition
0x18018e4f6  lea     rax, aDamap; "DAMap"
0x18018e4fd  test    ebp, ebp
0x18018e4ff  lea     rsi, [rbx+220h]
0x18018e506  mov     [rsp+0A8h+phkResult], rsi; phkResult
0x18018e50b  lea     rdi, aLowdamap; "LowDAMap"
0x18018e512  cmovz   rdi, rax
0x18018e516  mov     [rsp+0A8h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18018e51b  mov     rdx, rdi; lpSubKey
0x18018e51e  mov     [rsp+0A8h+samDesired], 2001Fh; samDesired
0x18018e526  xor     r9d, r9d; lpClass
0x18018e529  mov     [rsp+0A8h+dwOptions], r13d; dwOptions
0x18018e52e  xor     r8d, r8d; Reserved
0x18018e531  call    cs:__imp_RegCreateKeyExW
0x18018e537  test    eax, eax
0x18018e539  jz      short loc_18018E58B
0x18018e53b  test    byte ptr cs:xmmword_180266B50+1, 4
0x18018e542  jz      short loc_18018E55D
0x18018e544  mov     edx, 26h ; '&'
0x18018e549  lea     r8, WPP_88e9b8d46a55322969ac94ecd507bd70_Traceguids
0x18018e550  mov     ecx, 20Ah
0x18018e555  mov     r9d, eax
0x18018e558  call    WPP_SF_d
0x18018e55d  mov     rcx, [r14]; hKey
0x18018e560  xor     r9d, r9d; lpClass
0x18018e563  mov     [rsp+0A8h+lpdwDisposition], r13; lpdwDisposition
0x18018e568  xor     r8d, r8d; Reserved
0x18018e56b  mov     [rsp+0A8h+phkResult], rsi; phkResult
0x18018e570  mov     rdx, rdi; lpSubKey
0x18018e573  mov     [rsp+0A8h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18018e578  mov     [rsp+0A8h+samDesired], 20019h; samDesired
0x18018e580  mov     [rsp+0A8h+dwOptions], r13d; dwOptions
0x18018e585  call    cs:__imp_RegCreateKeyExW
0x18018e58b  mov     rcx, [r14]; hKey
0x18018e58e  mov     edi, 1
0x18018e593  test    rcx, rcx
0x18018e596  jz      short loc_18018E5C7
0x18018e598  lea     rdx, [rsp+0A8h+cbData]
0x18018e59d  xor     r8d, r8d; lpReserved
0x18018e5a0  mov     qword ptr [rsp+0A8h+samDesired], rdx; lpcbData
0x18018e5a5  lea     rax, [rbx+228h]
0x18018e5ac  lea     rdx, aLoginserverurl; "LoginServerUrl"
0x18018e5b3  mov     qword ptr [rsp+0A8h+dwOptions], rax; lpData
0x18018e5b8  lea     r9, [rsp+0A8h+Type]; lpType
0x18018e5bd  call    cs:__imp_RegQueryValueExW
0x18018e5c3  test    eax, eax
0x18018e5c5  jz      short loc_18018E609
0x18018e5c7  mov     rcx, [r15]; hKey
0x18018e5ca  mov     esi, r13d
0x18018e5cd  mov     [rsp+0A8h+cbData], 800h
0x18018e5d5  test    rcx, rcx
0x18018e5d8  jz      short loc_18018E61B
0x18018e5da  lea     r8, [rsp+0A8h+cbData]
0x18018e5df  mov     qword ptr [rsp+0A8h+samDesired], r8; lpcbData
0x18018e5e4  lea     rax, [rbx+228h]
0x18018e5eb  xor     r8d, r8d; lpReserved
0x18018e5ee  mov     qword ptr [rsp+0A8h+dwOptions], rax; lpData
0x18018e5f3  lea     r9, [rsp+0A8h+Type]; lpType
0x18018e5f8  lea     rdx, aLoginserverurl; "LoginServerUrl"
0x18018e5ff  call    cs:__imp_RegQueryValueExW
0x18018e605  test    eax, eax
0x18018e607  jnz     short loc_18018E61B
0x18018e609  mov     ecx, [rsp+0A8h+cbData]
0x18018e60d  mov     esi, edi
0x18018e60f  shr     rcx, 1
0x18018e612  mov     [rbx+rcx*2+228h], r13w
0x18018e61b  test    r12d, r12d
0x18018e61e  jnz     short loc_18018E69B
0x18018e620  test    esi, esi
0x18018e622  jz      short loc_18018E63B
0x18018e624  or      rax, 0FFFFFFFFFFFFFFFFh
0x18018e628  inc     rax
0x18018e62b  cmp     [rbx+rax*2+228h], r13w
0x18018e634  jnz     short loc_18018E628
0x18018e636  test    rax, rax
0x18018e639  jnz     short loc_18018E69B
0x18018e63b  mov     qword ptr [rsp+0A8h+samDesired], r13; unsigned int *
0x18018e640  xor     r9d, r9d; unsigned int *
0x18018e643  xor     r8d, r8d; unsigned __int16 *
0x18018e646  mov     qword ptr [rsp+0A8h+dwOptions], r13; unsigned __int16 *
0x18018e64b  xor     edx, edx; int
0x18018e64d  mov     rcx, rbx; this
0x18018e650  call    ?GetDAInfoFromPPNexus@WININET_SESSION@@QEAAHHPEAGPEAK01@Z; WININET_SESSION::GetDAInfoFromPPNexus(int,ushort *,ulong *,ushort *,ulong *)
0x18018e655  test    eax, eax
0x18018e657  jnz     short loc_18018E69B
0x18018e659  mov     rcx, [rbx+220h]; hKey
0x18018e660  mov     edi, r13d
0x18018e663  test    rcx, rcx
0x18018e666  jz      short loc_18018E675
0x18018e668  call    cs:__imp_RegCloseKey
0x18018e66e  mov     [rbx+220h], r13
0x18018e675  mov     rcx, [rbx+218h]; hKey
0x18018e67c  test    rcx, rcx
0x18018e67f  jz      short loc_18018E68A
0x18018e681  call    cs:__imp_RegCloseKey
0x18018e687  mov     [r14], r13
0x18018e68a  mov     rcx, [r15]; hKey
0x18018e68d  test    rcx, rcx
0x18018e690  jz      short loc_18018E69B
0x18018e692  call    cs:__imp_RegCloseKey
0x18018e698  mov     [r15], r13
0x18018e69b  mov     eax, edi
0x18018e69d  mov     rcx, [rsp+0A8h+var_50]
0x18018e6a2  xor     rcx, rsp; StackCookie
0x18018e6a5  call    __security_check_cookie
0x18018e6aa  add     rsp, 68h
0x18018e6ae  pop     r15
0x18018e6b0  pop     r14
0x18018e6b2  pop     r13
0x18018e6b4  pop     r12
0x18018e6b6  pop     rdi
0x18018e6b7  pop     rsi
0x18018e6b8  pop     rbp
0x18018e6b9  pop     rbx
0x18018e6ba  retn
```
