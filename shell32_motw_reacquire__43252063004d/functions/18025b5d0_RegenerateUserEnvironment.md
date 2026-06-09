# RegenerateUserEnvironment

- ea: `0x18025b5d0`
- end: `0x18025ba9f`
- name: `RegenerateUserEnvironment`
- size: `1231`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18049e004`

## callees

- `0x18008a2a0`
- `0x180131748`
- `0x18014d890`
- `0x18017f768`
- `0x180249490`
- `0x18025aad4`
- `0x18025adf8`
- `0x18025ae80`
- `0x18025b0c8`
- `0x18025b5d0`
- `0x18025bba4`
- `0x1805a3840`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18025b74f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18025b760`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18025b74f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18025b760`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18025b8ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18025b9b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18025b8ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18025b9b3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18025b9a2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18025b9a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18025b804`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18025b804`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18025b917`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18025b917`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18025b96f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18025b96f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18025b6d7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18025b6d7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x18025b874`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x18025b874`
- `ntdll!RtlCreateEnvironment` at `0x18025b666`
- `ntdll!RtlCreateEnvironment` at `0x18025b666`
- `ntdll!RtlSetCurrentEnvironment` at `0x18025ba43`
- `ntdll!RtlSetCurrentEnvironment` at `0x18025ba43`
- `ntdll!RtlDestroyEnvironment` at `0x18025ba58`
- `ntdll!RtlDestroyEnvironment` at `0x18025ba58`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x18025b853`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x18025b95a`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x18025b853`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x18025b95a`

## string_xrefs

- `0x18025b6be`: `ProgramData`
- `0x18025b6f4`: `COMPUTERNAME`
- `0x18025b79f`: `HOMEPATH`

## pseudocode

```c
__int64 __fastcall RegenerateUserEnvironment(PWSTR *a1, int a2)
{
  __int64 i; // rbx
  int v5; // eax
  int v6; // eax
  __int64 result; // rax
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL v9; // [rsp+58h] [rbp-A8h] BYREF
  PWSTR Environment; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hkey; // [rsp+68h] [rbp-98h] BYREF
  PWSTR OldEnvironment; // [rsp+70h] [rbp-90h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp-88h] BYREF
  wchar_t pszDest[2]; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD pdwType; // [rsp+80h] [rbp-80h] BYREF
  DWORD nSize; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  WCHAR Buffer[16]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t v19[40]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE pvData[4112]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t pszSrc[2056]; // [rsp+1110h] [rbp+1010h] BYREF

  *a1 = 0;
  Environment = 0;
  OldEnvironment = 0;
  hMem = 0;
  v9 = 0;
  hkey = 0;
  dwDisposition = 0;
  pdwType = 0;
  pcbData = 0;
  nSize = 16;
  if ( RtlCreateEnvironment(0, &Environment) >= 0 )
  {
    CopyVariableToUserEnvironment(&Environment, L"SystemRoot");
    CopyVariableToUserEnvironment(&Environment, L"SystemDrive");
    CopyVariableToUserEnvironment(&Environment, L"ALLUSERSPROFILE");
    CopyVariableToUserEnvironment(&Environment, L"PUBLIC");
    CopyVariableToUserEnvironment(&Environment, L"ProgramData");
    if ( GetComputerNameW(Buffer, &nSize) )
      SetUserEnvironmentVariable(&Environment, L"COMPUTERNAME", Buffer);
    if ( (unsigned int)GetUserNameAndDomain(&hMem, &v9) )
    {
      SetUserEnvironmentVariable(&Environment, L"USERNAME", (STRSAFE_LPCWSTR)hMem);
      SetUserEnvironmentVariable(&Environment, L"USERDOMAIN", (STRSAFE_LPCWSTR)v9);
      LocalFree(hMem);
      LocalFree(v9);
    }
    CopyVariableToUserEnvironment(&Environment, L"USERDNSDOMAIN");
    CopyVariableToUserEnvironment(&Environment, L"HOMEDRIVE");
    CopyVariableToUserEnvironment(&Environment, L"HOMESHARE");
    CopyVariableToUserEnvironment(&Environment, L"HOMEPATH");
    CopyVariableToUserEnvironment(&Environment, L"USERPROFILE");
    CopyVariableToUserEnvironment(&Environment, L"APPDATA");
    CopyVariableToUserEnvironment(&Environment, L"LOCALAPPDATA");
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion", 0, 0x20019u, &hkey) )
    {
      for ( i = 0; i != 6; ++i )
      {
        pcbData = 4098;
        if ( !SHQueryValueExW(hkey, off_1806F61F0[2 * i], 0, &pdwType, pvData, &pcbData) )
        {
          SHExpandEnvironmentStringsW(pvData, pszSrc, 2049);
          SetUserEnvironmentVariable(&Environment, off_1806F61F0[2 * i + 1], pszSrc);
        }
      }
      RegCloseKey(hkey);
    }
    SetSystemEnvironmentVariables(&Environment);
    StringCchCopyW(pszDest, 2u, L"1");
    if ( !RegCreateKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
            0,
            0,
            0,
            0x2001Fu,
            0,
            &hkey,
            &dwDisposition) )
    {
      pcbData = 4;
      if ( SHQueryValueExW(hkey, L"ParseAutoexec", 0, &pdwType, pszDest, &pcbData) )
      {
        v5 = lstrlenW(pszDest);
        RegSetValueExW(hkey, L"ParseAutoexec", 0, 1u, (const BYTE *)pszDest, 2 * v5 + 2);
      }
      RegCloseKey(hkey);
    }
    if ( pszDest[0] == 49 )
      ProcessAutoexec(&Environment);
    SetEnvironmentVariables(&Environment);
    SetEnvironmentVariables(&Environment);
    AppendNTPathWithAutoexecPath(&Environment);
    if ( StringCchPrintfW(v19, 0x21u, L"Volatile Environment\\%lu", NtCurrentPeb()->SessionId) >= 0 )
      SetEnvironmentVariables(&Environment);
    if ( !a2 )
      goto LABEL_23;
    RtlSetCurrentEnvironment(Environment, &OldEnvironment);
    if ( v6 >= 0 )
    {
      RtlDestroyEnvironment(OldEnvironment);
LABEL_23:
      result = 1;
      *a1 = Environment;
      return result;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18025b5d0  mov     [rsp-8+arg_8], rbx
0x18025b5d5  mov     [rsp-8+arg_10], rsi
0x18025b5da  push    rbp
0x18025b5db  push    rdi
0x18025b5dc  push    r12
0x18025b5de  push    r13
0x18025b5e0  push    r14
0x18025b5e2  lea     rbp, [rsp-2030h]
0x18025b5ea  mov     eax, 2130h
0x18025b5ef  call    _alloca_probe
0x18025b5f4  sub     rsp, rax
0x18025b5f7  mov     rax, cs:__security_cookie
0x18025b5fe  xor     rax, rsp
0x18025b601  mov     [rbp+2050h+var_30], rax
0x18025b608  mov     r14d, edx
0x18025b60b  mov     qword ptr [rcx], 0
0x18025b612  mov     rsi, rcx
0x18025b615  mov     [rsp+2150h+Environment], 0
0x18025b61e  lea     rdx, [rsp+2150h+Environment]; Environment
0x18025b623  mov     [rsp+2150h+OldEnvironment], 0
0x18025b62c  xor     ecx, ecx; Inherit
0x18025b62e  mov     [rsp+2150h+hMem], 0
0x18025b637  mov     [rsp+2150h+var_20F8], 0
0x18025b640  mov     [rsp+2150h+hkey], 0
0x18025b649  mov     [rbp+2050h+dwDisposition], 0
0x18025b650  mov     [rbp+2050h+pdwType], 0
0x18025b657  mov     [rsp+2150h+var_20D8], 0
0x18025b65f  mov     [rbp+2050h+nSize], 10h
0x18025b666  call    cs:__imp_RtlCreateEnvironment
0x18025b66d  nop     dword ptr [rax+rax+00h]
0x18025b672  test    eax, eax
0x18025b674  js      loc_18025BA71
0x18025b67a  lea     rdx, aSystemroot; "SystemRoot"
0x18025b681  lea     rcx, [rsp+2150h+Environment]
0x18025b686  call    CopyVariableToUserEnvironment
0x18025b68b  lea     rdx, aSystemdrive; "SystemDrive"
0x18025b692  lea     rcx, [rsp+2150h+Environment]
0x18025b697  call    CopyVariableToUserEnvironment
0x18025b69c  lea     rdx, aAllusersprofil; "ALLUSERSPROFILE"
0x18025b6a3  lea     rcx, [rsp+2150h+Environment]
0x18025b6a8  call    CopyVariableToUserEnvironment
0x18025b6ad  lea     rdx, aPublic; "PUBLIC"
0x18025b6b4  lea     rcx, [rsp+2150h+Environment]
0x18025b6b9  call    CopyVariableToUserEnvironment
0x18025b6be  lea     rdx, aProgramdata; "ProgramData"
0x18025b6c5  lea     rcx, [rsp+2150h+Environment]
0x18025b6ca  call    CopyVariableToUserEnvironment
0x18025b6cf  lea     rdx, [rbp+2050h+nSize]; nSize
0x18025b6d3  lea     rcx, [rbp+2050h+Buffer]; lpBuffer
0x18025b6d7  call    cs:__imp_GetComputerNameW
0x18025b6de  nop     dword ptr [rax+rax+00h]
0x18025b6e3  mov     r12d, 1
0x18025b6e9  test    eax, eax
0x18025b6eb  jz      short loc_18025B705
0x18025b6ed  mov     r9d, r12d
0x18025b6f0  lea     r8, [rbp+2050h+Buffer]; pszSrc
0x18025b6f4  lea     rdx, aComputername_0; "COMPUTERNAME"
0x18025b6fb  lea     rcx, [rsp+2150h+Environment]; Environment
0x18025b700  call    SetUserEnvironmentVariable
0x18025b705  lea     rdx, [rsp+2150h+var_20F8]
0x18025b70a  lea     rcx, [rsp+2150h+hMem]
0x18025b70f  call    GetUserNameAndDomain
0x18025b714  test    eax, eax
0x18025b716  jz      short loc_18025B76C
0x18025b718  mov     r8, [rsp+2150h+hMem]; pszSrc
0x18025b71d  lea     rdx, aUsername; "USERNAME"
0x18025b724  mov     r9d, r12d
0x18025b727  lea     rcx, [rsp+2150h+Environment]; Environment
0x18025b72c  call    SetUserEnvironmentVariable
0x18025b731  mov     r8, [rsp+2150h+var_20F8]; pszSrc
0x18025b736  lea     rdx, aUserdomain; "USERDOMAIN"
0x18025b73d  mov     r9d, r12d
0x18025b740  lea     rcx, [rsp+2150h+Environment]; Environment
0x18025b745  call    SetUserEnvironmentVariable
0x18025b74a  mov     rcx, [rsp+2150h+hMem]; hMem
0x18025b74f  call    cs:__imp_LocalFree
0x18025b756  nop     dword ptr [rax+rax+00h]
0x18025b75b  mov     rcx, [rsp+2150h+var_20F8]; hMem
0x18025b760  call    cs:__imp_LocalFree
0x18025b767  nop     dword ptr [rax+rax+00h]
0x18025b76c  lea     rdx, aUserdnsdomain; "USERDNSDOMAIN"
0x18025b773  lea     rcx, [rsp+2150h+Environment]
0x18025b778  call    CopyVariableToUserEnvironment
0x18025b77d  lea     rdx, aHomedrive; "HOMEDRIVE"
0x18025b784  lea     rcx, [rsp+2150h+Environment]
0x18025b789  call    CopyVariableToUserEnvironment
0x18025b78e  lea     rdx, aHomeshare; "HOMESHARE"
0x18025b795  lea     rcx, [rsp+2150h+Environment]
0x18025b79a  call    CopyVariableToUserEnvironment
0x18025b79f  lea     rdx, aHomepath; "HOMEPATH"
0x18025b7a6  lea     rcx, [rsp+2150h+Environment]
0x18025b7ab  call    CopyVariableToUserEnvironment
0x18025b7b0  lea     rdx, aUserprofile; "USERPROFILE"
0x18025b7b7  lea     rcx, [rsp+2150h+Environment]
0x18025b7bc  call    CopyVariableToUserEnvironment
0x18025b7c1  lea     rdx, aAppdata; "APPDATA"
0x18025b7c8  lea     rcx, [rsp+2150h+Environment]
0x18025b7cd  call    CopyVariableToUserEnvironment
0x18025b7d2  lea     rdx, aLocalappdata; "LOCALAPPDATA"
0x18025b7d9  lea     rcx, [rsp+2150h+Environment]
0x18025b7de  call    CopyVariableToUserEnvironment
0x18025b7e3  lea     rax, [rsp+2150h+hkey]
0x18025b7e8  mov     r9d, 20019h; samDesired
0x18025b7ee  xor     r8d, r8d; ulOptions
0x18025b7f1  mov     [rsp+2150h+phkResult], rax; phkResult
0x18025b7f6  lea     rdx, aSoftwareMicros_104; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18025b7fd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18025b804  call    cs:__imp_RegOpenKeyExW
0x18025b80b  nop     dword ptr [rax+rax+00h]
0x18025b810  test    eax, eax
0x18025b812  jnz     loc_18025B8B7
0x18025b818  xor     ebx, ebx
0x18025b81a  lea     r13, off_1806F61F0; "ProgramFilesDir"
0x18025b821  mov     rcx, [rsp+2150h+hkey]; hkey
0x18025b826  lea     rax, [rsp+2150h+var_20D8]
0x18025b82b  mov     [rsp+2150h+pcbData], rax; pcbData
0x18025b830  lea     r9, [rbp+2050h+pdwType]; pdwType
0x18025b834  lea     rax, [rbp+2050h+pvData]
0x18025b838  mov     [rsp+2150h+var_20D8], 1002h
0x18025b840  mov     rdi, rbx
0x18025b843  mov     [rsp+2150h+phkResult], rax; pvData
0x18025b848  add     rdi, rdi
0x18025b84b  xor     r8d, r8d; pdwReserved
0x18025b84e  mov     rdx, [r13+rdi*8+0]; pszValue
0x18025b853  call    cs:__imp_SHQueryValueExW
0x18025b85a  nop     dword ptr [rax+rax+00h]
0x18025b85f  test    eax, eax
0x18025b861  jnz     short loc_18025B899
0x18025b863  mov     r8d, 801h
0x18025b869  lea     rdx, [rbp+2050h+pszSrc]
0x18025b870  lea     rcx, [rbp+2050h+pvData]
0x18025b874  call    cs:__imp_SHExpandEnvironmentStringsW
0x18025b87b  nop     dword ptr [rax+rax+00h]
0x18025b880  mov     rdx, [r13+rdi*8+8]; pszStr1
0x18025b885  lea     r8, [rbp+2050h+pszSrc]; pszSrc
0x18025b88c  mov     r9d, r12d
0x18025b88f  lea     rcx, [rsp+2150h+Environment]; Environment
0x18025b894  call    SetUserEnvironmentVariable
0x18025b899  add     rbx, r12
0x18025b89c  cmp     rbx, 6
0x18025b8a0  jnz     loc_18025B821
0x18025b8a6  mov     rcx, [rsp+2150h+hkey]; hKey
0x18025b8ab  call    cs:__imp_RegCloseKey
0x18025b8b2  nop     dword ptr [rax+rax+00h]
0x18025b8b7  lea     rcx, [rsp+2150h+Environment]; Environment
0x18025b8bc  call    SetSystemEnvironmentVariables
0x18025b8c1  lea     r8, a1_0; "1"
0x18025b8c8  mov     edx, 2; cchDest
0x18025b8cd  lea     rcx, [rsp+2150h+pszDest]; pszDest
0x18025b8d2  call    StringCchCopyW
0x18025b8d7  lea     r10, [rbp+2050h+dwDisposition]
0x18025b8db  xor     r9d, r9d; lpClass
0x18025b8de  mov     [rsp+2150h+lpdwDisposition], r10; lpdwDisposition
0x18025b8e3  lea     rax, [rsp+2150h+hkey]
0x18025b8e8  mov     [rsp+2150h+var_2118], rax; phkResult
0x18025b8ed  lea     rdx, aSoftwareMicros_188; "Software\\Microsoft\\Windows NT\\Curren"...
0x18025b8f4  mov     [rsp+2150h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18025b8fd  xor     r8d, r8d; Reserved
0x18025b900  mov     dword ptr [rsp+2150h+pcbData], 2001Fh; samDesired
0x18025b908  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18025b90f  mov     dword ptr [rsp+2150h+phkResult], 0; dwOptions
0x18025b917  call    cs:__imp_RegCreateKeyExW
0x18025b91e  nop     dword ptr [rax+rax+00h]
0x18025b923  test    eax, eax
0x18025b925  jnz     loc_18025B9BF
0x18025b92b  mov     rcx, [rsp+2150h+hkey]; hkey
0x18025b930  lea     rax, [rsp+2150h+var_20D8]
0x18025b935  mov     [rsp+2150h+pcbData], rax; pcbData
0x18025b93a  lea     r9, [rbp+2050h+pdwType]; pdwType
0x18025b93e  lea     rax, [rsp+2150h+pszDest]
0x18025b943  mov     [rsp+2150h+var_20D8], 4
0x18025b94b  xor     r8d, r8d; pdwReserved
0x18025b94e  mov     [rsp+2150h+phkResult], rax; pvData
0x18025b953  lea     rdx, aParseautoexec; "ParseAutoexec"
0x18025b95a  call    cs:__imp_SHQueryValueExW
0x18025b961  nop     dword ptr [rax+rax+00h]
0x18025b966  test    eax, eax
0x18025b968  jz      short loc_18025B9AE
0x18025b96a  lea     rcx, [rsp+2150h+pszDest]; lpString
0x18025b96f  call    cs:__imp_lstrlenW
0x18025b976  nop     dword ptr [rax+rax+00h]
0x18025b97b  mov     rcx, [rsp+2150h+hkey]; hKey
0x18025b980  lea     rdx, aParseautoexec; "ParseAutoexec"
0x18025b987  mov     r9d, r12d; dwType
0x18025b98a  xor     r8d, r8d; Reserved
0x18025b98d  lea     eax, ds:2[rax*2]
0x18025b994  mov     dword ptr [rsp+2150h+pcbData], eax; cbData
0x18025b998  lea     rax, [rsp+2150h+pszDest]
0x18025b99d  mov     [rsp+2150h+phkResult], rax; lpData
0x18025b9a2  call    cs:__imp_RegSetValueExW
0x18025b9a9  nop     dword ptr [rax+rax+00h]
0x18025b9ae  mov     rcx, [rsp+2150h+hkey]; hKey
0x18025b9b3  call    cs:__imp_RegCloseKey
0x18025b9ba  nop     dword ptr [rax+rax+00h]
0x18025b9bf  cmp     [rsp+2150h+pszDest], 31h ; '1'
0x18025b9c5  jnz     short loc_18025B9D1
0x18025b9c7  lea     rcx, [rsp+2150h+Environment]; Environment
0x18025b9cc  call    ProcessAutoexec
0x18025b9d1  lea     rdx, aEnvironment; "Environment"
0x18025b9d8  lea     rcx, [rsp+2150h+Environment]; Environment
0x18025b9dd  call    SetEnvironmentVariables
0x18025b9e2  lea     rdx, aVolatileEnviro_0; "Volatile Environment"
0x18025b9e9  lea     rcx, [rsp+2150h+Environment]; Environment
0x18025b9ee  call    SetEnvironmentVariables
0x18025b9f3  lea     rcx, [rsp+2150h+Environment]
0x18025b9f8  call    AppendNTPathWithAutoexecPath
0x18025b9fd  mov     r9, gs:60h
0x18025ba06  lea     r8, aVolatileEnviro; "Volatile Environment\\%lu"
0x18025ba0d  mov     edx, 21h ; '!'; cchDest
0x18025ba12  lea     rcx, [rbp+2050h+var_20A0]; pszDest
0x18025ba16  mov     r9d, [r9+2C0h]
0x18025ba1d  call    StringCchPrintfW
0x18025ba22  test    eax, eax
0x18025ba24  js      short loc_18025BA34
0x18025ba26  lea     rdx, [rbp+2050h+var_20A0]
0x18025ba2a  lea     rcx, [rsp+2150h+Environment]; Environment
0x18025ba2f  call    SetEnvironmentVariables
0x18025ba34  test    r14d, r14d
0x18025ba37  jz      short loc_18025BA64
0x18025ba39  mov     rcx, [rsp+2150h+Environment]; NewEnvironment
0x18025ba3e  lea     rdx, [rsp+2150h+OldEnvironment]; OldEnvironment
0x18025ba43  call    cs:__imp_RtlSetCurrentEnvironment
0x18025ba4a  nop     dword ptr [rax+rax+00h]
0x18025ba4f  test    eax, eax
0x18025ba51  js      short loc_18025BA71
0x18025ba53  mov     rcx, [rsp+2150h+OldEnvironment]; Environment
0x18025ba58  call    cs:__imp_RtlDestroyEnvironment
0x18025ba5f  nop     dword ptr [rax+rax+00h]
0x18025ba64  mov     rcx, [rsp+2150h+Environment]
0x18025ba69  mov     eax, r12d
0x18025ba6c  mov     [rsi], rcx
0x18025ba6f  jmp     short loc_18025BA73
0x18025ba71  xor     eax, eax
0x18025ba73  mov     rcx, [rbp+2050h+var_30]
0x18025ba7a  xor     rcx, rsp; StackCookie
0x18025ba7d  call    __security_check_cookie
0x18025ba82  lea     r11, [rsp+2150h+var_20]
0x18025ba8a  mov     rbx, [r11+38h]
0x18025ba8e  mov     rsi, [r11+40h]
0x18025ba92  mov     rsp, r11
0x18025ba95  pop     r14
0x18025ba97  pop     r13
0x18025ba99  pop     r12
0x18025ba9b  pop     rdi
0x18025ba9c  pop     rbp
0x18025ba9d  retn
```
