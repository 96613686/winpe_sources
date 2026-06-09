# CUtils::DebugBreakIfAskedEx(ushort *,ushort *)

- ea: `0x1800a0f8c`
- end: `0x1800a12a0`
- name: `?DebugBreakIfAskedEx@CUtils@@SAXPEAG0@Z`
- size: `788`
- prototype: `void __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180048510`

## callees

- `0x180016558`
- `0x180033f60`
- `0x180034e64`
- `0x1800a0f8c`
- `0x1800a2c54`

## import_xrefs

- `ntdll!DbgPrint` at `0x1800a1196`
- `ntdll!DbgPrint` at `0x1800a1263`
- `ntdll!DbgPrint` at `0x1800a127b`
- `ntdll!DbgPrint` at `0x1800a1196`
- `ntdll!DbgPrint` at `0x1800a1263`
- `ntdll!DbgPrint` at `0x1800a127b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a115f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a115f`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800a11f9`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800a11f9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a10a5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a10e0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a1247`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a10a5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a10e0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a1247`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a10be`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a10be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1217`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1228`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1217`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1228`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1034`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a107b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1122`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1034`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a107b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1122`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a10cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a10cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a0ff0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a0ff0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a123b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a123b`

## string_xrefs

- `0x1800a1209`: `TERMSRV:*-----------------* TERMSRV:CreateProcess failed *-----------------*\n`
- `0x1800a1274`: `TERMSRV:*-----------------* Could not open termsrv registry *-----------------*\n`

## pseudocode

```c
void __fastcall CUtils::DebugBreakIfAskedEx(unsigned __int16 *a1, unsigned __int16 *a2)
{
  DWORD CurrentProcessId; // eax
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-98h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  WCHAR CommandLine[256]; // [rsp+F0h] [rbp-10h] BYREF
  BYTE v10[512]; // [rsp+2F0h] [rbp+1F0h] BYREF

  hKey = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"DebugTS", 0, &Type, Data, &cbData) || Type != 4 )
    {
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"BreakOnRCMStart", 0, &Type, Data, &cbData) || Type != 4 )
        goto LABEL_12;
    }
    if ( *(_DWORD *)Data != 1 )
    {
      if ( *(_DWORD *)Data == 2 )
      {
        if ( !IsDebuggerPresent() )
        {
          cbData = 256;
          if ( RegQueryValueExW(hKey, L"Debugger", 0, &Type, v10, &cbData) || Type != 1 )
          {
            DbgPrint("TERMSRV:*-----------------* Did not find the debugger entry. *-----------------*\n");
          }
          else
          {
            memset(&ProcessInformation, 0, sizeof(ProcessInformation));
            memset_0(&StartupInfo, 0, sizeof(StartupInfo));
            CurrentProcessId = GetCurrentProcessId();
            if ( (int)StringCchPrintfW(CommandLine, 0x100u, L"ntsd -d -G -x -p %d", CurrentProcessId) >= 0 )
            {
              DbgPrint("TERMSRV:*-----------------* Executing:<%ws> *-----------------*\n", CommandLine);
              memset_0(&StartupInfo.cb + 1, 0, 0x64u);
              StartupInfo.cb = 104;
              if ( CreateProcessW(0, CommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
              {
                CloseHandle(ProcessInformation.hProcess);
                CloseHandle(ProcessInformation.hThread);
                while ( !IsDebuggerPresent() )
                  Sleep(0x1F4u);
              }
              else
              {
                DbgPrint("TERMSRV:*-----------------* TERMSRV:CreateProcess failed *-----------------*\n");
              }
            }
          }
          goto LABEL_12;
        }
LABEL_11:
        DebugBreak();
        goto LABEL_12;
      }
      if ( *(_DWORD *)Data != 3 )
      {
LABEL_12:
        RegCloseKey(hKey);
        return;
      }
    }
    if ( !IsDebuggerPresent() && !(unsigned int)CUtils::IsKernelDebuggerAttached() )
      goto LABEL_12;
    goto LABEL_11;
  }
  DbgPrint("TERMSRV:*-----------------* Could not open termsrv registry *-----------------*\n");
}

```

## disassembly

```asm
0x1800a0f8c  push    rbp
0x1800a0f8e  lea     rbp, [rsp-400h]
0x1800a0f96  sub     rsp, 500h
0x1800a0f9d  mov     rax, cs:__security_cookie
0x1800a0fa4  xor     rax, rsp
0x1800a0fa7  mov     [rbp+400h+var_10], rax
0x1800a0fae  lea     rax, [rsp+500h+hKey]
0x1800a0fb3  mov     [rsp+500h+hKey], 0
0x1800a0fbc  mov     r9d, 20019h; samDesired
0x1800a0fc2  mov     [rsp+500h+phkResult], rax; phkResult
0x1800a0fc7  xor     r8d, r8d; ulOptions
0x1800a0fca  mov     dword ptr [rsp+500h+Data], 0
0x1800a0fd2  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x1800a0fd9  mov     [rsp+500h+Type], 0
0x1800a0fe1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a0fe8  mov     [rsp+500h+cbData], 0
0x1800a0ff0  call    cs:__imp_RegOpenKeyExW
0x1800a0ff7  nop     dword ptr [rax+rax+00h]
0x1800a0ffc  test    eax, eax
0x1800a0ffe  jnz     loc_1800A1274
0x1800a1004  mov     rcx, [rsp+500h+hKey]; hKey
0x1800a1009  lea     rax, [rsp+500h+cbData]
0x1800a100e  mov     [rsp+500h+lpcbData], rax; lpcbData
0x1800a1013  lea     r9, [rsp+500h+Type]; lpType
0x1800a1018  lea     rax, [rsp+500h+Data]
0x1800a101d  mov     [rsp+500h+cbData], 4
0x1800a1025  xor     r8d, r8d; lpReserved
0x1800a1028  mov     [rsp+500h+phkResult], rax; lpData
0x1800a102d  lea     rdx, aDebugts; "DebugTS"
0x1800a1034  call    cs:__imp_RegQueryValueExW
0x1800a103b  nop     dword ptr [rax+rax+00h]
0x1800a1040  test    eax, eax
0x1800a1042  jnz     short loc_1800A104B
0x1800a1044  cmp     [rsp+500h+Type], 4
0x1800a1049  jz      short loc_1800A1092
0x1800a104b  mov     rcx, [rsp+500h+hKey]; hKey
0x1800a1050  lea     rax, [rsp+500h+cbData]
0x1800a1055  mov     [rsp+500h+lpcbData], rax; lpcbData
0x1800a105a  lea     r9, [rsp+500h+Type]; lpType
0x1800a105f  lea     rax, [rsp+500h+Data]
0x1800a1064  mov     [rsp+500h+cbData], 4
0x1800a106c  xor     r8d, r8d; lpReserved
0x1800a106f  mov     [rsp+500h+phkResult], rax; lpData
0x1800a1074  lea     rdx, aBreakonrcmstar; "BreakOnRCMStart"
0x1800a107b  call    cs:__imp_RegQueryValueExW
0x1800a1082  nop     dword ptr [rax+rax+00h]
0x1800a1087  test    eax, eax
0x1800a1089  jnz     short loc_1800A10CA
0x1800a108b  cmp     [rsp+500h+Type], 4
0x1800a1090  jnz     short loc_1800A10CA
0x1800a1092  mov     eax, dword ptr [rsp+500h+Data]
0x1800a1096  sub     eax, 1
0x1800a1099  jz      short loc_1800A10A5
0x1800a109b  sub     eax, 1
0x1800a109e  jz      short loc_1800A10E0
0x1800a10a0  cmp     eax, 1
0x1800a10a3  jnz     short loc_1800A10CA
0x1800a10a5  call    cs:__imp_IsDebuggerPresent
0x1800a10ac  nop     dword ptr [rax+rax+00h]
0x1800a10b1  test    eax, eax
0x1800a10b3  jnz     short loc_1800A10BE
0x1800a10b5  call    ?IsKernelDebuggerAttached@CUtils@@SAHXZ; CUtils::IsKernelDebuggerAttached(void)
0x1800a10ba  test    eax, eax
0x1800a10bc  jz      short loc_1800A10CA
0x1800a10be  call    cs:__imp_DebugBreak
0x1800a10c5  nop     dword ptr [rax+rax+00h]
0x1800a10ca  mov     rcx, [rsp+500h+hKey]; hKey
0x1800a10cf  call    cs:__imp_RegCloseKey
0x1800a10d6  nop     dword ptr [rax+rax+00h]
0x1800a10db  jmp     loc_1800A1287
0x1800a10e0  call    cs:__imp_IsDebuggerPresent
0x1800a10e7  nop     dword ptr [rax+rax+00h]
0x1800a10ec  test    eax, eax
0x1800a10ee  jnz     short loc_1800A10BE
0x1800a10f0  mov     rcx, [rsp+500h+hKey]; hKey
0x1800a10f5  lea     rax, [rsp+500h+cbData]
0x1800a10fa  mov     [rsp+500h+lpcbData], rax; lpcbData
0x1800a10ff  lea     r9, [rsp+500h+Type]; lpType
0x1800a1104  lea     rax, [rbp+400h+var_210]
0x1800a110b  mov     [rsp+500h+cbData], 100h
0x1800a1113  xor     r8d, r8d; lpReserved
0x1800a1116  mov     [rsp+500h+phkResult], rax; lpData
0x1800a111b  lea     rdx, aDebugger; "Debugger"
0x1800a1122  call    cs:__imp_RegQueryValueExW
0x1800a1129  nop     dword ptr [rax+rax+00h]
0x1800a112e  test    eax, eax
0x1800a1130  jnz     loc_1800A125C
0x1800a1136  cmp     [rsp+500h+Type], 1
0x1800a113b  jnz     loc_1800A125C
0x1800a1141  xor     eax, eax
0x1800a1143  lea     rcx, [rbp+400h+StartupInfo]; void *
0x1800a1147  xorps   xmm0, xmm0
0x1800a114a  mov     qword ptr [rsp+500h+ProcessInformation.dwProcessId], rax
0x1800a114f  xor     edx, edx; Val
0x1800a1151  movups  xmmword ptr [rsp+500h+ProcessInformation.hProcess], xmm0
0x1800a1156  lea     r8d, [rax+68h]; Size
0x1800a115a  call    memset_0
0x1800a115f  call    cs:__imp_GetCurrentProcessId
0x1800a1166  nop     dword ptr [rax+rax+00h]
0x1800a116b  lea     r8, aNtsdDGXPD; "ntsd -d -G -x -p %d"
0x1800a1172  mov     edx, 100h; unsigned __int64
0x1800a1177  mov     r9d, eax
0x1800a117a  lea     rcx, [rbp+400h+CommandLine]; unsigned __int16 *
0x1800a117e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a1183  test    eax, eax
0x1800a1185  js      loc_1800A10CA
0x1800a118b  lea     rdx, [rbp+400h+CommandLine]
0x1800a118f  lea     rcx, aTermsrvExecuti; "TERMSRV:*-----------------* Executing:<"...
0x1800a1196  call    cs:__imp_DbgPrint
0x1800a119d  nop     dword ptr [rax+rax+00h]
0x1800a11a2  xor     edx, edx; Val
0x1800a11a4  lea     rcx, [rbp+400h+StartupInfo+4]; void *
0x1800a11a8  lea     r8d, [rdx+64h]; Size
0x1800a11ac  call    memset_0
0x1800a11b1  lea     rax, [rsp+500h+ProcessInformation]
0x1800a11b6  mov     [rbp+400h+StartupInfo.cb], 68h ; 'h'
0x1800a11bd  mov     [rsp+500h+lpProcessInformation], rax; lpProcessInformation
0x1800a11c2  lea     rdx, [rbp+400h+CommandLine]; lpCommandLine
0x1800a11c6  lea     rax, [rbp+400h+StartupInfo]
0x1800a11ca  xor     r9d, r9d; lpThreadAttributes
0x1800a11cd  mov     [rsp+500h+lpStartupInfo], rax; lpStartupInfo
0x1800a11d2  xor     r8d, r8d; lpProcessAttributes
0x1800a11d5  mov     [rsp+500h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1800a11de  xor     ecx, ecx; lpApplicationName
0x1800a11e0  mov     [rsp+500h+lpEnvironment], 0; lpEnvironment
0x1800a11e9  mov     dword ptr [rsp+500h+lpcbData], 0; dwCreationFlags
0x1800a11f1  mov     dword ptr [rsp+500h+phkResult], 0; bInheritHandles
0x1800a11f9  call    cs:__imp_CreateProcessW
0x1800a1200  nop     dword ptr [rax+rax+00h]
0x1800a1205  test    eax, eax
0x1800a1207  jnz     short loc_1800A1212
0x1800a1209  lea     rcx, aTermsrvTermsrv; "TERMSRV:*-----------------* TERMSRV:Cre"...
0x1800a1210  jmp     short loc_1800A1263
0x1800a1212  mov     rcx, [rsp+500h+ProcessInformation.hProcess]; hObject
0x1800a1217  call    cs:__imp_CloseHandle
0x1800a121e  nop     dword ptr [rax+rax+00h]
0x1800a1223  mov     rcx, [rsp+500h+ProcessInformation.hThread]; hObject
0x1800a1228  call    cs:__imp_CloseHandle
0x1800a122f  nop     dword ptr [rax+rax+00h]
0x1800a1234  jmp     short loc_1800A1247
0x1800a1236  mov     ecx, 1F4h; dwMilliseconds
0x1800a123b  call    cs:__imp_Sleep
0x1800a1242  nop     dword ptr [rax+rax+00h]
0x1800a1247  call    cs:__imp_IsDebuggerPresent
0x1800a124e  nop     dword ptr [rax+rax+00h]
0x1800a1253  test    eax, eax
0x1800a1255  jz      short loc_1800A1236
0x1800a1257  jmp     loc_1800A10CA
0x1800a125c  lea     rcx, aTermsrvDidNotF; "TERMSRV:*-----------------* Did not fin"...
0x1800a1263  call    cs:__imp_DbgPrint
0x1800a126a  nop     dword ptr [rax+rax+00h]
0x1800a126f  jmp     loc_1800A10CA
0x1800a1274  lea     rcx, aTermsrvCouldNo; "TERMSRV:*-----------------* Could not o"...
0x1800a127b  call    cs:__imp_DbgPrint
0x1800a1282  nop     dword ptr [rax+rax+00h]
0x1800a1287  mov     rcx, [rbp+400h+var_10]
0x1800a128e  xor     rcx, rsp; StackCookie
0x1800a1291  call    __security_check_cookie
0x1800a1296  add     rsp, 500h
0x1800a129d  pop     rbp
0x1800a129e  retn
```
