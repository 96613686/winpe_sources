# RegenerateUserEnvironment

- ea: `0x180244f80`
- end: `0x1802453ec`
- name: `RegenerateUserEnvironment`
- size: `1132`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180469e34`

## callees

- `0x180089470`
- `0x180123584`
- `0x18013cb8c`
- `0x18016df30`
- `0x180233280`
- `0x1802445dc`
- `0x1802448a0`
- `0x180244920`
- `0x180244b0c`
- `0x180244f80`
- `0x1802454ec`
- `0x180562de0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802450f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802450fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802450f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802450fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18024519c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18024519c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18024522d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180245313`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18024522d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180245313`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180245293`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180245293`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180245308`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180245308`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1802452db`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1802452db`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180245081`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180245081`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x180245200`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x180245200`
- `ntdll!RtlCreateEnvironment` at `0x180245016`
- `ntdll!RtlCreateEnvironment` at `0x180245016`
- `ntdll!RtlSetCurrentEnvironment` at `0x18024539d`
- `ntdll!RtlSetCurrentEnvironment` at `0x18024539d`
- `ntdll!RtlDestroyEnvironment` at `0x1802453ac`
- `ntdll!RtlDestroyEnvironment` at `0x1802453ac`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x1802451e5`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x1802452cc`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x1802451e5`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x1802452cc`

## string_xrefs

- `0x180245068`: `ProgramData`
- `0x180245098`: `COMPUTERNAME`
- `0x180245137`: `HOMEPATH`

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
        if ( !SHQueryValueExW(hkey, off_1806B51F0[2 * i], 0, &pdwType, pvData, &pcbData) )
        {
          SHExpandEnvironmentStringsW(pvData, pszSrc, 2049);
          SetUserEnvironmentVariable(&Environment, off_1806B51F0[2 * i + 1], pszSrc);
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
0x180244f80  mov     [rsp-8+arg_8], rbx
0x180244f85  mov     [rsp-8+arg_10], rsi
0x180244f8a  push    rbp
0x180244f8b  push    rdi
0x180244f8c  push    r12
0x180244f8e  push    r13
0x180244f90  push    r14
0x180244f92  lea     rbp, [rsp-2030h]
0x180244f9a  mov     eax, 2130h
0x180244f9f  call    _alloca_probe
0x180244fa4  sub     rsp, rax
0x180244fa7  mov     rax, cs:__security_cookie
0x180244fae  xor     rax, rsp
0x180244fb1  mov     [rbp+2050h+var_30], rax
0x180244fb8  mov     r14d, edx
0x180244fbb  mov     qword ptr [rcx], 0
0x180244fc2  mov     rsi, rcx
0x180244fc5  mov     [rsp+2150h+Environment], 0
0x180244fce  lea     rdx, [rsp+2150h+Environment]; Environment
0x180244fd3  mov     [rsp+2150h+OldEnvironment], 0
0x180244fdc  xor     ecx, ecx; Inherit
0x180244fde  mov     [rsp+2150h+hMem], 0
0x180244fe7  mov     [rsp+2150h+var_20F8], 0
0x180244ff0  mov     [rsp+2150h+hkey], 0
0x180244ff9  mov     [rbp+2050h+dwDisposition], 0
0x180245000  mov     [rbp+2050h+pdwType], 0
0x180245007  mov     [rsp+2150h+var_20D8], 0
0x18024500f  mov     [rbp+2050h+nSize], 10h
0x180245016  call    cs:__imp_RtlCreateEnvironment
0x18024501c  test    eax, eax
0x18024501e  js      loc_1802453BF
0x180245024  lea     rdx, aSystemroot; "SystemRoot"
0x18024502b  lea     rcx, [rsp+2150h+Environment]
0x180245030  call    CopyVariableToUserEnvironment
0x180245035  lea     rdx, aSystemdrive; "SystemDrive"
0x18024503c  lea     rcx, [rsp+2150h+Environment]
0x180245041  call    CopyVariableToUserEnvironment
0x180245046  lea     rdx, aAllusersprofil; "ALLUSERSPROFILE"
0x18024504d  lea     rcx, [rsp+2150h+Environment]
0x180245052  call    CopyVariableToUserEnvironment
0x180245057  lea     rdx, aPublic; "PUBLIC"
0x18024505e  lea     rcx, [rsp+2150h+Environment]
0x180245063  call    CopyVariableToUserEnvironment
0x180245068  lea     rdx, aProgramdata; "ProgramData"
0x18024506f  lea     rcx, [rsp+2150h+Environment]
0x180245074  call    CopyVariableToUserEnvironment
0x180245079  lea     rdx, [rbp+2050h+nSize]; nSize
0x18024507d  lea     rcx, [rbp+2050h+Buffer]; lpBuffer
0x180245081  call    cs:__imp_GetComputerNameW
0x180245087  mov     r12d, 1
0x18024508d  test    eax, eax
0x18024508f  jz      short loc_1802450A9
0x180245091  mov     r9d, r12d
0x180245094  lea     r8, [rbp+2050h+Buffer]; pszSrc
0x180245098  lea     rdx, aComputername_0; "COMPUTERNAME"
0x18024509f  lea     rcx, [rsp+2150h+Environment]; Environment
0x1802450a4  call    SetUserEnvironmentVariable
0x1802450a9  lea     rdx, [rsp+2150h+var_20F8]
0x1802450ae  lea     rcx, [rsp+2150h+hMem]
0x1802450b3  call    GetUserNameAndDomain
0x1802450b8  test    eax, eax
0x1802450ba  jz      short loc_180245104
0x1802450bc  mov     r8, [rsp+2150h+hMem]; pszSrc
0x1802450c1  lea     rdx, aUsername; "USERNAME"
0x1802450c8  mov     r9d, r12d
0x1802450cb  lea     rcx, [rsp+2150h+Environment]; Environment
0x1802450d0  call    SetUserEnvironmentVariable
0x1802450d5  mov     r8, [rsp+2150h+var_20F8]; pszSrc
0x1802450da  lea     rdx, aUserdomain; "USERDOMAIN"
0x1802450e1  mov     r9d, r12d
0x1802450e4  lea     rcx, [rsp+2150h+Environment]; Environment
0x1802450e9  call    SetUserEnvironmentVariable
0x1802450ee  mov     rcx, [rsp+2150h+hMem]; hMem
0x1802450f3  call    cs:__imp_LocalFree
0x1802450f9  mov     rcx, [rsp+2150h+var_20F8]; hMem
0x1802450fe  call    cs:__imp_LocalFree
0x180245104  lea     rdx, aUserdnsdomain; "USERDNSDOMAIN"
0x18024510b  lea     rcx, [rsp+2150h+Environment]
0x180245110  call    CopyVariableToUserEnvironment
0x180245115  lea     rdx, aHomedrive; "HOMEDRIVE"
0x18024511c  lea     rcx, [rsp+2150h+Environment]
0x180245121  call    CopyVariableToUserEnvironment
0x180245126  lea     rdx, aHomeshare; "HOMESHARE"
0x18024512d  lea     rcx, [rsp+2150h+Environment]
0x180245132  call    CopyVariableToUserEnvironment
0x180245137  lea     rdx, aHomepath; "HOMEPATH"
0x18024513e  lea     rcx, [rsp+2150h+Environment]
0x180245143  call    CopyVariableToUserEnvironment
0x180245148  lea     rdx, aUserprofile; "USERPROFILE"
0x18024514f  lea     rcx, [rsp+2150h+Environment]
0x180245154  call    CopyVariableToUserEnvironment
0x180245159  lea     rdx, aAppdata; "APPDATA"
0x180245160  lea     rcx, [rsp+2150h+Environment]
0x180245165  call    CopyVariableToUserEnvironment
0x18024516a  lea     rdx, aLocalappdata; "LOCALAPPDATA"
0x180245171  lea     rcx, [rsp+2150h+Environment]
0x180245176  call    CopyVariableToUserEnvironment
0x18024517b  lea     rax, [rsp+2150h+hkey]
0x180245180  mov     r9d, 20019h; samDesired
0x180245186  xor     r8d, r8d; ulOptions
0x180245189  mov     [rsp+2150h+phkResult], rax; phkResult
0x18024518e  lea     rdx, aSoftwareMicros_104; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180245195  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18024519c  call    cs:__imp_RegOpenKeyExW
0x1802451a2  test    eax, eax
0x1802451a4  jnz     loc_180245233
0x1802451aa  xor     ebx, ebx
0x1802451ac  lea     r13, off_1806B51F0; "ProgramFilesDir"
0x1802451b3  mov     rcx, [rsp+2150h+hkey]; hkey
0x1802451b8  lea     rax, [rsp+2150h+var_20D8]
0x1802451bd  mov     [rsp+2150h+pcbData], rax; pcbData
0x1802451c2  lea     r9, [rbp+2050h+pdwType]; pdwType
0x1802451c6  lea     rax, [rbp+2050h+pvData]
0x1802451ca  mov     [rsp+2150h+var_20D8], 1002h
0x1802451d2  mov     rdi, rbx
0x1802451d5  mov     [rsp+2150h+phkResult], rax; pvData
0x1802451da  add     rdi, rdi
0x1802451dd  xor     r8d, r8d; pdwReserved
0x1802451e0  mov     rdx, [r13+rdi*8+0]; pszValue
0x1802451e5  call    cs:__imp_SHQueryValueExW
0x1802451eb  test    eax, eax
0x1802451ed  jnz     short loc_18024521F
0x1802451ef  mov     r8d, 801h
0x1802451f5  lea     rdx, [rbp+2050h+pszSrc]
0x1802451fc  lea     rcx, [rbp+2050h+pvData]
0x180245200  call    cs:__imp_SHExpandEnvironmentStringsW
0x180245206  mov     rdx, [r13+rdi*8+8]; pszStr1
0x18024520b  lea     r8, [rbp+2050h+pszSrc]; pszSrc
0x180245212  mov     r9d, r12d
0x180245215  lea     rcx, [rsp+2150h+Environment]; Environment
0x18024521a  call    SetUserEnvironmentVariable
0x18024521f  add     rbx, r12
0x180245222  cmp     rbx, 6
0x180245226  jnz     short loc_1802451B3
0x180245228  mov     rcx, [rsp+2150h+hkey]; hKey
0x18024522d  call    cs:__imp_RegCloseKey
0x180245233  lea     rcx, [rsp+2150h+Environment]; Environment
0x180245238  call    SetSystemEnvironmentVariables
0x18024523d  lea     r8, a1_0; "1"
0x180245244  mov     edx, 2; cchDest
0x180245249  lea     rcx, [rsp+2150h+pszDest]; pszDest
0x18024524e  call    StringCchCopyW
0x180245253  lea     r10, [rbp+2050h+dwDisposition]
0x180245257  xor     r9d, r9d; lpClass
0x18024525a  mov     [rsp+2150h+lpdwDisposition], r10; lpdwDisposition
0x18024525f  lea     rax, [rsp+2150h+hkey]
0x180245264  mov     [rsp+2150h+var_2118], rax; phkResult
0x180245269  lea     rdx, aSoftwareMicros_188; "Software\\Microsoft\\Windows NT\\Curren"...
0x180245270  mov     [rsp+2150h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180245279  xor     r8d, r8d; Reserved
0x18024527c  mov     dword ptr [rsp+2150h+pcbData], 2001Fh; samDesired
0x180245284  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18024528b  mov     dword ptr [rsp+2150h+phkResult], 0; dwOptions
0x180245293  call    cs:__imp_RegCreateKeyExW
0x180245299  test    eax, eax
0x18024529b  jnz     short loc_180245319
0x18024529d  mov     rcx, [rsp+2150h+hkey]; hkey
0x1802452a2  lea     rax, [rsp+2150h+var_20D8]
0x1802452a7  mov     [rsp+2150h+pcbData], rax; pcbData
0x1802452ac  lea     r9, [rbp+2050h+pdwType]; pdwType
0x1802452b0  lea     rax, [rsp+2150h+pszDest]
0x1802452b5  mov     [rsp+2150h+var_20D8], 4
0x1802452bd  xor     r8d, r8d; pdwReserved
0x1802452c0  mov     [rsp+2150h+phkResult], rax; pvData
0x1802452c5  lea     rdx, aParseautoexec; "ParseAutoexec"
0x1802452cc  call    cs:__imp_SHQueryValueExW
0x1802452d2  test    eax, eax
0x1802452d4  jz      short loc_18024530E
0x1802452d6  lea     rcx, [rsp+2150h+pszDest]; lpString
0x1802452db  call    cs:__imp_lstrlenW
0x1802452e1  mov     rcx, [rsp+2150h+hkey]; hKey
0x1802452e6  lea     rdx, aParseautoexec; "ParseAutoexec"
0x1802452ed  mov     r9d, r12d; dwType
0x1802452f0  xor     r8d, r8d; Reserved
0x1802452f3  lea     eax, ds:2[rax*2]
0x1802452fa  mov     dword ptr [rsp+2150h+pcbData], eax; cbData
0x1802452fe  lea     rax, [rsp+2150h+pszDest]
0x180245303  mov     [rsp+2150h+phkResult], rax; lpData
0x180245308  call    cs:__imp_RegSetValueExW
0x18024530e  mov     rcx, [rsp+2150h+hkey]; hKey
0x180245313  call    cs:__imp_RegCloseKey
0x180245319  cmp     [rsp+2150h+pszDest], 31h ; '1'
0x18024531f  jnz     short loc_18024532B
0x180245321  lea     rcx, [rsp+2150h+Environment]; Environment
0x180245326  call    ProcessAutoexec
0x18024532b  lea     rdx, aEnvironment; "Environment"
0x180245332  lea     rcx, [rsp+2150h+Environment]; Environment
0x180245337  call    SetEnvironmentVariables
0x18024533c  lea     rdx, aVolatileEnviro_0; "Volatile Environment"
0x180245343  lea     rcx, [rsp+2150h+Environment]; Environment
0x180245348  call    SetEnvironmentVariables
0x18024534d  lea     rcx, [rsp+2150h+Environment]
0x180245352  call    AppendNTPathWithAutoexecPath
0x180245357  mov     r9, gs:60h
0x180245360  lea     r8, aVolatileEnviro; "Volatile Environment\\%lu"
0x180245367  mov     edx, 21h ; '!'; cchDest
0x18024536c  lea     rcx, [rbp+2050h+var_20A0]; pszDest
0x180245370  mov     r9d, [r9+2C0h]
0x180245377  call    StringCchPrintfW
0x18024537c  test    eax, eax
0x18024537e  js      short loc_18024538E
0x180245380  lea     rdx, [rbp+2050h+var_20A0]
0x180245384  lea     rcx, [rsp+2150h+Environment]; Environment
0x180245389  call    SetEnvironmentVariables
0x18024538e  test    r14d, r14d
0x180245391  jz      short loc_1802453B2
0x180245393  mov     rcx, [rsp+2150h+Environment]; NewEnvironment
0x180245398  lea     rdx, [rsp+2150h+OldEnvironment]; OldEnvironment
0x18024539d  call    cs:__imp_RtlSetCurrentEnvironment
0x1802453a3  test    eax, eax
0x1802453a5  js      short loc_1802453BF
0x1802453a7  mov     rcx, [rsp+2150h+OldEnvironment]; Environment
0x1802453ac  call    cs:__imp_RtlDestroyEnvironment
0x1802453b2  mov     rcx, [rsp+2150h+Environment]
0x1802453b7  mov     eax, r12d
0x1802453ba  mov     [rsi], rcx
0x1802453bd  jmp     short loc_1802453C1
0x1802453bf  xor     eax, eax
0x1802453c1  mov     rcx, [rbp+2050h+var_30]
0x1802453c8  xor     rcx, rsp; StackCookie
0x1802453cb  call    __security_check_cookie
0x1802453d0  lea     r11, [rsp+2150h+var_20]
0x1802453d8  mov     rbx, [r11+38h]
0x1802453dc  mov     rsi, [r11+40h]
0x1802453e0  mov     rsp, r11
0x1802453e3  pop     r14
0x1802453e5  pop     r13
0x1802453e7  pop     r12
0x1802453e9  pop     rdi
0x1802453ea  pop     rbp
0x1802453eb  retn
```
