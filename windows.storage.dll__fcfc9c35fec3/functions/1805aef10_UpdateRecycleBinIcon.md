# UpdateRecycleBinIcon

- ea: `0x1805aef10`
- end: `0x1805af514`
- name: `UpdateRecycleBinIcon`
- size: `1540`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1805ae890`

## callees

- `0x180133f50`
- `0x1801720f0`
- `0x1803b1f60`
- `0x1805ad220`
- `0x1805ae6ac`
- `0x1805aef10`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x1805af474`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x1805af474`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrRChrW` at `0x1805af45c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrRChrW` at `0x1805af45c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805af095`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805af11d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805af1ac`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805af27f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805af36c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805af422`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805af095`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805af11d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805af1ac`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805af27f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805af36c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805af422`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1805af4ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1805af4e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1805af4ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1805af4e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1805af04b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1805af0d2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1805af161`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1805af1f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1805af235`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1805af2dc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1805af321`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1805af3df`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1805af04b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1805af0d2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1805af161`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1805af1f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1805af235`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1805af2dc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1805af321`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1805af3df`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1805af39a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1805af39a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1805af43f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1805af43f`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x1805aef80`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x1805aefb6`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x1805aeffd`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x1805aef80`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x1805aefb6`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x1805aeffd`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_LookupBackIconIndex` at `0x1805af492`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_LookupBackIconIndex` at `0x1805af492`

## pseudocode

```c
void __fastcall UpdateRecycleBinIcon(int a1)
{
  __int64 v2; // rbx
  const WCHAR *v3; // rdi
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  PWSTR v9; // rax
  PWSTR v10; // rdi
  unsigned int v11; // eax
  int v12; // ebx
  int v13; // eax
  HKEY handle; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type[3]; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int16 Data[260]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v19; // [rsp+258h] [rbp+158h]
  WCHAR pszStart[264]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR String2[264]; // [rsp+470h] [rbp+370h] BYREF
  WCHAR String1[264]; // [rsp+680h] [rbp+580h] BYREF

  cbData = 0;
  Type[0] = 0;
  hKey = 0;
  handle = 0;
  if ( (int)SHRegGetCLSIDKey(&CLSID_RecycleBin, L"DefaultIcon", 0, 0, 1, &hKey) >= 0 )
  {
    v2 = -1;
    v3 = L"Full";
    if ( (int)SHRegGetCLSIDKey(&CLSID_RecycleBin, L"DefaultIcon", 1, 0, 3, &handle) < 0 )
    {
      if ( (int)SHRegGetCLSIDKey(&CLSID_RecycleBin, L"DefaultIcon", 1, 1, 3, &handle) < 0 )
        goto LABEL_33;
      _SetLowRightsSACL(handle);
      cbData = 520;
      v19 = 0;
      if ( RegQueryValueExW(hKey, 0, 0, Type, (LPBYTE)Data, &cbData) )
        goto LABEL_33;
      v4 = -1;
      do
        ++v4;
      while ( Data[v4] );
      RegSetValueExW(handle, 0, 0, Type[0], (const BYTE *)Data, 2 * v4 + 2);
      cbData = 520;
      v19 = 0;
      if ( RegQueryValueExW(hKey, L"Full", 0, Type, (LPBYTE)Data, &cbData) )
        goto LABEL_33;
      v5 = -1;
      do
        ++v5;
      while ( Data[v5] );
      RegSetValueExW(handle, L"Full", 0, Type[0], (const BYTE *)Data, 2 * v5 + 2);
      cbData = 520;
      v19 = 0;
      if ( RegQueryValueExW(hKey, L"Empty", 0, Type, (LPBYTE)Data, &cbData) )
        goto LABEL_33;
      v6 = -1;
      do
        ++v6;
      while ( Data[v6] );
      RegSetValueExW(handle, L"Empty", 0, Type[0], (const BYTE *)Data, 2 * v6 + 2);
    }
    cbData = 520;
    v19 = 0;
    if ( RegQueryValueExW(handle, 0, 0, Type, (LPBYTE)Data, &cbData) )
    {
      cbData = 520;
      v19 = 0;
      if ( RegQueryValueExW(hKey, 0, 0, Type, (LPBYTE)Data, &cbData) )
        goto LABEL_33;
      v7 = -1;
      do
        ++v7;
      while ( Data[v7] );
      RegSetValueExW(handle, 0, 0, Type[0], (const BYTE *)Data, 2 * v7 + 2);
    }
    StringCchCopyW(String2, 0x105u, Data);
    cbData = 520;
    v19 = 0;
    if ( !a1 )
      v3 = L"Empty";
    if ( RegQueryValueExW(handle, v3, 0, Type, (LPBYTE)Data, &cbData) )
    {
      cbData = 520;
      v19 = 0;
      if ( RegQueryValueExW(hKey, v3, 0, Type, (LPBYTE)Data, &cbData) )
        goto LABEL_33;
      v8 = -1;
      do
        ++v8;
      while ( Data[v8] );
      RegSetValueExW(handle, v3, 0, Type[0], (const BYTE *)Data, 2 * v8 + 2);
    }
    StringCchCopyW(String1, 0x105u, Data);
    if ( lstrcmpiW(String1, String2) )
    {
      cbData = 520;
      v19 = 0;
      if ( !RegQueryValueExW(handle, v3, 0, Type, (LPBYTE)Data, &cbData) )
      {
        do
          ++v2;
        while ( Data[v2] );
        RegSetValueExW(handle, 0, 0, Type[0], (const BYTE *)Data, 2 * v2 + 2);
      }
      if ( (unsigned int)SHExpandEnvironmentStringsW(String2, pszStart, 261) )
      {
        v9 = StrRChrW(pszStart, 0, 0x2Cu);
        v10 = v9;
        if ( v9 )
        {
          v11 = StrToIntW(v9 + 1);
          *v10 = 0;
          v12 = v11;
          v13 = SHELL32_LookupBackIconIndex(pszStart, v11, 0);
          SHUpdateImageW(pszStart, v12, 0, v13);
          SHChangeNotify(0, 0x1000u, 0, 0);
        }
      }
    }
  }
LABEL_33:
  if ( hKey )
    RegCloseKey(hKey);
  if ( handle )
    RegCloseKey(handle);
}

```

## disassembly

```asm
0x1805aef10  push    rbp
0x1805aef12  push    rbx
0x1805aef13  push    rsi
0x1805aef14  push    rdi
0x1805aef15  push    r12
0x1805aef17  push    r13
0x1805aef19  push    r14
0x1805aef1b  push    r15
0x1805aef1d  lea     rbp, [rsp-7A8h]
0x1805aef25  sub     rsp, 8A8h
0x1805aef2c  mov     rax, cs:__security_cookie
0x1805aef33  xor     rax, rsp
0x1805aef36  mov     [rbp+7E0h+var_50], rax
0x1805aef3d  xor     r14d, r14d
0x1805aef40  lea     rax, [rsp+8E0h+hKey]
0x1805aef45  mov     esi, ecx
0x1805aef47  mov     [rsp+8E0h+lpcbData], rax
0x1805aef4c  lea     r13, c_szDefaultIcon; "DefaultIcon"
0x1805aef53  mov     [rsp+8E0h+cbData], r14d
0x1805aef58  xor     r9d, r9d
0x1805aef5b  mov     [rsp+8E0h+Type], r14d
0x1805aef60  lea     r15d, [r14+1]
0x1805aef64  mov     [rsp+8E0h+hKey], r14
0x1805aef69  xor     r8d, r8d
0x1805aef6c  mov     dword ptr [rsp+8E0h+lpData], r15d
0x1805aef71  mov     rdx, r13
0x1805aef74  mov     [rsp+8E0h+handle], r14
0x1805aef79  lea     rcx, CLSID_RecycleBin
0x1805aef80  call    cs:__imp_SHRegGetCLSIDKey
0x1805aef87  nop     dword ptr [rax+rax+00h]
0x1805aef8c  test    eax, eax
0x1805aef8e  js      loc_1805AF4C4
0x1805aef94  lea     rax, [rsp+8E0h+handle]
0x1805aef99  xor     r9d, r9d
0x1805aef9c  mov     [rsp+8E0h+lpcbData], rax
0x1805aefa1  lea     rcx, CLSID_RecycleBin
0x1805aefa8  mov     r8d, r15d
0x1805aefab  mov     dword ptr [rsp+8E0h+lpData], 3
0x1805aefb3  mov     rdx, r13
0x1805aefb6  call    cs:__imp_SHRegGetCLSIDKey
0x1805aefbd  nop     dword ptr [rax+rax+00h]
0x1805aefc2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1805aefc6  lea     rdi, aFull; "Full"
0x1805aefcd  mov     r12d, 208h
0x1805aefd3  test    eax, eax
0x1805aefd5  jns     loc_1805AF1BA
0x1805aefdb  lea     rax, [rsp+8E0h+handle]
0x1805aefe0  mov     r9d, r15d
0x1805aefe3  mov     [rsp+8E0h+lpcbData], rax
0x1805aefe8  lea     rcx, CLSID_RecycleBin
0x1805aefef  mov     r8d, r15d
0x1805aeff2  mov     dword ptr [rsp+8E0h+lpData], 3
0x1805aeffa  mov     rdx, r13
0x1805aeffd  call    cs:__imp_SHRegGetCLSIDKey
0x1805af004  nop     dword ptr [rax+rax+00h]
0x1805af009  test    eax, eax
0x1805af00b  js      loc_1805AF4C4
0x1805af011  mov     rcx, [rsp+8E0h+handle]; handle
0x1805af016  call    ?_SetLowRightsSACL@@YAJPEAUHKEY__@@@Z; _SetLowRightsSACL(HKEY__ *)
0x1805af01b  mov     rcx, [rsp+8E0h+hKey]; hKey
0x1805af020  lea     rax, [rsp+8E0h+cbData]
0x1805af025  mov     [rsp+8E0h+lpcbData], rax; lpcbData
0x1805af02a  lea     r9, [rsp+8E0h+Type]; lpType
0x1805af02f  lea     rax, [rsp+8E0h+Data]
0x1805af034  mov     [rsp+8E0h+cbData], r12d
0x1805af039  xor     r8d, r8d; lpReserved
0x1805af03c  mov     [rsp+8E0h+lpData], rax; lpData
0x1805af041  xor     edx, edx; lpValueName
0x1805af043  mov     [rbp+7E0h+var_688], r14w
0x1805af04b  call    cs:__imp_RegQueryValueExW
0x1805af052  nop     dword ptr [rax+rax+00h]
0x1805af057  test    eax, eax
0x1805af059  jnz     loc_1805AF4C4
0x1805af05f  lea     rcx, [rsp+8E0h+Data]
0x1805af064  mov     rax, rbx
0x1805af067  inc     rax
0x1805af06a  cmp     [rcx+rax*2], r14w
0x1805af06f  jnz     short loc_1805AF067
0x1805af071  mov     r9d, [rsp+8E0h+Type]; dwType
0x1805af076  lea     eax, ds:2[rax*2]
0x1805af07d  mov     rcx, [rsp+8E0h+handle]; hKey
0x1805af082  xor     r8d, r8d; Reserved
0x1805af085  mov     dword ptr [rsp+8E0h+lpcbData], eax; cbData
0x1805af089  xor     edx, edx; lpValueName
0x1805af08b  lea     rax, [rsp+8E0h+Data]
0x1805af090  mov     [rsp+8E0h+lpData], rax; lpData
0x1805af095  call    cs:__imp_RegSetValueExW
0x1805af09c  nop     dword ptr [rax+rax+00h]
0x1805af0a1  mov     rcx, [rsp+8E0h+hKey]; hKey
0x1805af0a6  lea     rax, [rsp+8E0h+cbData]
0x1805af0ab  mov     [rsp+8E0h+lpcbData], rax; lpcbData
0x1805af0b0  lea     r9, [rsp+8E0h+Type]; lpType
0x1805af0b5  lea     rax, [rsp+8E0h+Data]
0x1805af0ba  mov     [rsp+8E0h+cbData], r12d
0x1805af0bf  xor     r8d, r8d; lpReserved
0x1805af0c2  mov     [rsp+8E0h+lpData], rax; lpData
0x1805af0c7  mov     rdx, rdi; lpValueName
0x1805af0ca  mov     [rbp+7E0h+var_688], r14w
0x1805af0d2  call    cs:__imp_RegQueryValueExW
0x1805af0d9  nop     dword ptr [rax+rax+00h]
0x1805af0de  test    eax, eax
0x1805af0e0  jnz     loc_1805AF4C4
0x1805af0e6  lea     rcx, [rsp+8E0h+Data]
0x1805af0eb  mov     rax, rbx
0x1805af0ee  inc     rax
0x1805af0f1  cmp     [rcx+rax*2], r14w
0x1805af0f6  jnz     short loc_1805AF0EE
0x1805af0f8  mov     r9d, [rsp+8E0h+Type]; dwType
0x1805af0fd  lea     eax, ds:2[rax*2]
0x1805af104  mov     rcx, [rsp+8E0h+handle]; hKey
0x1805af109  xor     r8d, r8d; Reserved
0x1805af10c  mov     dword ptr [rsp+8E0h+lpcbData], eax; cbData
0x1805af110  mov     rdx, rdi; lpValueName
0x1805af113  lea     rax, [rsp+8E0h+Data]
0x1805af118  mov     [rsp+8E0h+lpData], rax; lpData
0x1805af11d  call    cs:__imp_RegSetValueExW
0x1805af124  nop     dword ptr [rax+rax+00h]
0x1805af129  mov     rcx, [rsp+8E0h+hKey]; hKey
0x1805af12e  lea     rax, [rsp+8E0h+cbData]
0x1805af133  mov     [rsp+8E0h+lpcbData], rax; lpcbData
0x1805af138  lea     r13, aEmpty_0; "Empty"
0x1805af13f  lea     rax, [rsp+8E0h+Data]
0x1805af144  mov     [rsp+8E0h+cbData], r12d
0x1805af149  lea     r9, [rsp+8E0h+Type]; lpType
0x1805af14e  mov     [rsp+8E0h+lpData], rax; lpData
0x1805af153  xor     r8d, r8d; lpReserved
0x1805af156  mov     [rbp+7E0h+var_688], r14w
0x1805af15e  mov     rdx, r13; lpValueName
0x1805af161  call    cs:__imp_RegQueryValueExW
0x1805af168  nop     dword ptr [rax+rax+00h]
0x1805af16d  test    eax, eax
0x1805af16f  jnz     loc_1805AF4C4
0x1805af175  lea     rcx, [rsp+8E0h+Data]
0x1805af17a  mov     rax, rbx
0x1805af17d  inc     rax
0x1805af180  cmp     [rcx+rax*2], r14w
0x1805af185  jnz     short loc_1805AF17D
0x1805af187  mov     r9d, [rsp+8E0h+Type]; dwType
0x1805af18c  lea     eax, ds:2[rax*2]
0x1805af193  mov     rcx, [rsp+8E0h+handle]; hKey
0x1805af198  xor     r8d, r8d; Reserved
0x1805af19b  mov     dword ptr [rsp+8E0h+lpcbData], eax; cbData
0x1805af19f  mov     rdx, r13; lpValueName
0x1805af1a2  lea     rax, [rsp+8E0h+Data]
0x1805af1a7  mov     [rsp+8E0h+lpData], rax; lpData
0x1805af1ac  call    cs:__imp_RegSetValueExW
0x1805af1b3  nop     dword ptr [rax+rax+00h]
0x1805af1b8  jmp     short loc_1805AF1C1
0x1805af1ba  lea     r13, aEmpty_0; "Empty"
0x1805af1c1  mov     rcx, [rsp+8E0h+handle]; hKey
0x1805af1c6  lea     rax, [rsp+8E0h+cbData]
0x1805af1cb  mov     [rsp+8E0h+lpcbData], rax; lpcbData
0x1805af1d0  lea     r9, [rsp+8E0h+Type]; lpType
0x1805af1d5  lea     rax, [rsp+8E0h+Data]
0x1805af1da  mov     [rsp+8E0h+cbData], r12d
0x1805af1df  xor     r8d, r8d; lpReserved
0x1805af1e2  mov     [rsp+8E0h+lpData], rax; lpData
0x1805af1e7  xor     edx, edx; lpValueName
0x1805af1e9  mov     [rbp+7E0h+var_688], r14w
0x1805af1f1  call    cs:__imp_RegQueryValueExW
0x1805af1f8  nop     dword ptr [rax+rax+00h]
0x1805af1fd  test    eax, eax
0x1805af1ff  jz      loc_1805AF28B
0x1805af205  mov     rcx, [rsp+8E0h+hKey]; hKey
0x1805af20a  lea     rax, [rsp+8E0h+cbData]
0x1805af20f  mov     [rsp+8E0h+lpcbData], rax; lpcbData
0x1805af214  lea     r9, [rsp+8E0h+Type]; lpType
0x1805af219  lea     rax, [rsp+8E0h+Data]
0x1805af21e  mov     [rsp+8E0h+cbData], r12d
0x1805af223  xor     r8d, r8d; lpReserved
0x1805af226  mov     [rsp+8E0h+lpData], rax; lpData
0x1805af22b  xor     edx, edx; lpValueName
0x1805af22d  mov     [rbp+7E0h+var_688], r14w
0x1805af235  call    cs:__imp_RegQueryValueExW
0x1805af23c  nop     dword ptr [rax+rax+00h]
0x1805af241  test    eax, eax
0x1805af243  jnz     loc_1805AF4C4
0x1805af249  lea     rcx, [rsp+8E0h+Data]
0x1805af24e  mov     rax, rbx
0x1805af251  inc     rax
0x1805af254  cmp     [rcx+rax*2], r14w
0x1805af259  jnz     short loc_1805AF251
0x1805af25b  mov     r9d, [rsp+8E0h+Type]; dwType
0x1805af260  lea     eax, ds:2[rax*2]
0x1805af267  mov     rcx, [rsp+8E0h+handle]; hKey
0x1805af26c  xor     r8d, r8d; Reserved
0x1805af26f  mov     dword ptr [rsp+8E0h+lpcbData], eax; cbData
0x1805af273  xor     edx, edx; lpValueName
0x1805af275  lea     rax, [rsp+8E0h+Data]
0x1805af27a  mov     [rsp+8E0h+lpData], rax; lpData
0x1805af27f  call    cs:__imp_RegSetValueExW
0x1805af286  nop     dword ptr [rax+rax+00h]
0x1805af28b  mov     r15d, 105h
0x1805af291  lea     r8, [rsp+8E0h+Data]; unsigned __int16 *
0x1805af296  mov     edx, r15d; unsigned __int64
0x1805af299  lea     rcx, [rbp+7E0h+String2]; unsigned __int16 *
0x1805af2a0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1805af2a5  mov     rcx, [rsp+8E0h+handle]; hKey
0x1805af2aa  lea     rax, [rsp+8E0h+cbData]
0x1805af2af  mov     [rsp+8E0h+lpcbData], rax; lpcbData
0x1805af2b4  lea     r9, [rsp+8E0h+Type]; lpType
0x1805af2b9  lea     rax, [rsp+8E0h+Data]
0x1805af2be  mov     [rsp+8E0h+cbData], r12d
0x1805af2c3  test    esi, esi
0x1805af2c5  mov     [rbp+7E0h+var_688], r14w
0x1805af2cd  mov     [rsp+8E0h+lpData], rax; lpData
0x1805af2d2  cmovz   rdi, r13
0x1805af2d6  xor     r8d, r8d; lpReserved
0x1805af2d9  mov     rdx, rdi; lpValueName
0x1805af2dc  call    cs:__imp_RegQueryValueExW
0x1805af2e3  nop     dword ptr [rax+rax+00h]
0x1805af2e8  test    eax, eax
0x1805af2ea  jz      loc_1805AF378
0x1805af2f0  mov     rcx, [rsp+8E0h+hKey]; hKey
0x1805af2f5  lea     rax, [rsp+8E0h+cbData]
0x1805af2fa  mov     [rsp+8E0h+lpcbData], rax; lpcbData
0x1805af2ff  lea     r9, [rsp+8E0h+Type]; lpType
0x1805af304  lea     rax, [rsp+8E0h+Data]
0x1805af309  mov     [rsp+8E0h+cbData], r12d
0x1805af30e  xor     r8d, r8d; lpReserved
0x1805af311  mov     [rsp+8E0h+lpData], rax; lpData
0x1805af316  mov     rdx, rdi; lpValueName
0x1805af319  mov     [rbp+7E0h+var_688], r14w
0x1805af321  call    cs:__imp_RegQueryValueExW
0x1805af328  nop     dword ptr [rax+rax+00h]
0x1805af32d  test    eax, eax
0x1805af32f  jnz     loc_1805AF4C4
0x1805af335  lea     rcx, [rsp+8E0h+Data]
0x1805af33a  mov     rax, rbx
0x1805af33d  inc     rax
0x1805af340  cmp     [rcx+rax*2], r14w
0x1805af345  jnz     short loc_1805AF33D
0x1805af347  mov     r9d, [rsp+8E0h+Type]; dwType
0x1805af34c  lea     eax, ds:2[rax*2]
0x1805af353  mov     rcx, [rsp+8E0h+handle]; hKey
0x1805af358  xor     r8d, r8d; Reserved
0x1805af35b  mov     dword ptr [rsp+8E0h+lpcbData], eax; cbData
0x1805af35f  mov     rdx, rdi; lpValueName
0x1805af362  lea     rax, [rsp+8E0h+Data]
0x1805af367  mov     [rsp+8E0h+lpData], rax; lpData
0x1805af36c  call    cs:__imp_RegSetValueExW
0x1805af373  nop     dword ptr [rax+rax+00h]
0x1805af378  lea     r8, [rsp+8E0h+Data]; unsigned __int16 *
0x1805af37d  mov     rdx, r15; unsigned __int64
0x1805af380  lea     rcx, [rbp+7E0h+String1]; unsigned __int16 *
0x1805af387  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1805af38c  lea     rdx, [rbp+7E0h+String2]; lpString2
0x1805af393  lea     rcx, [rbp+7E0h+String1]; lpString1
0x1805af39a  call    cs:__imp_lstrcmpiW
0x1805af3a1  nop     dword ptr [rax+rax+00h]
0x1805af3a6  test    eax, eax
0x1805af3a8  jz      loc_1805AF4C4
0x1805af3ae  mov     rcx, [rsp+8E0h+handle]; hKey
0x1805af3b3  lea     rax, [rsp+8E0h+cbData]
0x1805af3b8  mov     [rsp+8E0h+lpcbData], rax; lpcbData
0x1805af3bd  lea     r9, [rsp+8E0h+Type]; lpType
0x1805af3c2  lea     rax, [rsp+8E0h+Data]
0x1805af3c7  mov     [rsp+8E0h+cbData], r12d
0x1805af3cc  xor     r8d, r8d; lpReserved
0x1805af3cf  mov     [rsp+8E0h+lpData], rax; lpData
0x1805af3d4  mov     rdx, rdi; lpValueName
0x1805af3d7  mov     [rbp+7E0h+var_688], r14w
0x1805af3df  call    cs:__imp_RegQueryValueExW
0x1805af3e6  nop     dword ptr [rax+rax+00h]
0x1805af3eb  test    eax, eax
0x1805af3ed  jnz     short loc_1805AF42E
0x1805af3ef  lea     rax, [rsp+8E0h+Data]
0x1805af3f4  inc     rbx
0x1805af3f7  cmp     [rax+rbx*2], r14w
0x1805af3fc  jnz     short loc_1805AF3F4
0x1805af3fe  mov     r9d, [rsp+8E0h+Type]; dwType
0x1805af403  lea     eax, ds:2[rbx*2]
0x1805af40a  mov     rcx, [rsp+8E0h+handle]; hKey
0x1805af40f  xor     r8d, r8d; Reserved
0x1805af412  mov     dword ptr [rsp+8E0h+lpcbData], eax; cbData
0x1805af416  xor     edx, edx; lpValueName
0x1805af418  lea     rax, [rsp+8E0h+Data]
0x1805af41d  mov     [rsp+8E0h+lpData], rax; lpData
0x1805af422  call    cs:__imp_RegSetValueExW
0x1805af429  nop     dword ptr [rax+rax+00h]
0x1805af42e  mov     r8d, r15d
0x1805af431  lea     rdx, [rbp+7E0h+pszStart]
0x1805af438  lea     rcx, [rbp+7E0h+String2]
0x1805af43f  call    cs:__imp_SHExpandEnvironmentStringsW
0x1805af446  nop     dword ptr [rax+rax+00h]
0x1805af44b  test    eax, eax
0x1805af44d  jz      short loc_1805AF4C4
0x1805af44f  xor     edx, edx; pszEnd
0x1805af451  lea     rcx, [rbp+7E0h+pszStart]; pszStart
0x1805af458  lea     r8d, [rdx+2Ch]; wMatch
0x1805af45c  call    cs:__imp_StrRChrW
0x1805af463  nop     dword ptr [rax+rax+00h]
0x1805af468  mov     rdi, rax
0x1805af46b  test    rax, rax
0x1805af46e  jz      short loc_1805AF4C4
0x1805af470  lea     rcx, [rax+2]; pszSrc
0x1805af474  call    cs:__imp_StrToIntW
0x1805af47b  nop     dword ptr [rax+rax+00h]
0x1805af480  xor     r8d, r8d
0x1805af483  mov     [rdi], r14w
  ... truncated ...
```
