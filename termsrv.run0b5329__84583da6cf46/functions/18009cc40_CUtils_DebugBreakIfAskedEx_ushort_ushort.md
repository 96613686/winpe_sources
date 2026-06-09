# CUtils::DebugBreakIfAskedEx(ushort *,ushort *)

- ea: `0x18009cc40`
- end: `0x18009ceed`
- name: `?DebugBreakIfAskedEx@CUtils@@SAXPEAG0@Z`
- size: `685`
- prototype: `void __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180046100`

## callees

- `0x180015ab0`
- `0x1800321f0`
- `0x1800330c4`
- `0x18009cc40`
- `0x18009dcb4`

## import_xrefs

- `ntdll!DbgPrint` at `0x18009ce14`
- `ntdll!DbgPrint` at `0x18009cebd`
- `ntdll!DbgPrint` at `0x18009cecf`
- `ntdll!DbgPrint` at `0x18009ce14`
- `ntdll!DbgPrint` at `0x18009cebd`
- `ntdll!DbgPrint` at `0x18009cecf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009cde3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009cde3`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18009ce71`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18009ce71`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18009cd47`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18009cd70`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18009cea7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18009cd47`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18009cd70`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18009cea7`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18009cd5a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18009cd5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ce89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ce94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ce89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ce94`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009cce2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009cd23`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009cdac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009cce2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009cd23`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009cdac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009cd65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009cd65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009cca4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009cca4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18009cea1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18009cea1`

## string_xrefs

- `0x18009ce7b`: `TERMSRV:*-----------------* TERMSRV:CreateProcess failed *-----------------*\n`
- `0x18009cec8`: `TERMSRV:*-----------------* Could not open termsrv registry *-----------------*\n`

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
0x18009cc40  push    rbp
0x18009cc42  lea     rbp, [rsp-400h]
0x18009cc4a  sub     rsp, 500h
0x18009cc51  mov     rax, cs:__security_cookie
0x18009cc58  xor     rax, rsp
0x18009cc5b  mov     [rbp+400h+var_10], rax
0x18009cc62  lea     rax, [rsp+500h+hKey]
0x18009cc67  mov     [rsp+500h+hKey], 0
0x18009cc70  mov     r9d, 20019h; samDesired
0x18009cc76  mov     [rsp+500h+phkResult], rax; phkResult
0x18009cc7b  xor     r8d, r8d; ulOptions
0x18009cc7e  mov     dword ptr [rsp+500h+Data], 0
0x18009cc86  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x18009cc8d  mov     [rsp+500h+Type], 0
0x18009cc95  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009cc9c  mov     [rsp+500h+cbData], 0
0x18009cca4  call    cs:__imp_RegOpenKeyExW
0x18009ccaa  test    eax, eax
0x18009ccac  jnz     loc_18009CEC8
0x18009ccb2  mov     rcx, [rsp+500h+hKey]; hKey
0x18009ccb7  lea     rax, [rsp+500h+cbData]
0x18009ccbc  mov     [rsp+500h+lpcbData], rax; lpcbData
0x18009ccc1  lea     r9, [rsp+500h+Type]; lpType
0x18009ccc6  lea     rax, [rsp+500h+Data]
0x18009cccb  mov     [rsp+500h+cbData], 4
0x18009ccd3  xor     r8d, r8d; lpReserved
0x18009ccd6  mov     [rsp+500h+phkResult], rax; lpData
0x18009ccdb  lea     rdx, aDebugts; "DebugTS"
0x18009cce2  call    cs:__imp_RegQueryValueExW
0x18009cce8  test    eax, eax
0x18009ccea  jnz     short loc_18009CCF3
0x18009ccec  cmp     [rsp+500h+Type], 4
0x18009ccf1  jz      short loc_18009CD34
0x18009ccf3  mov     rcx, [rsp+500h+hKey]; hKey
0x18009ccf8  lea     rax, [rsp+500h+cbData]
0x18009ccfd  mov     [rsp+500h+lpcbData], rax; lpcbData
0x18009cd02  lea     r9, [rsp+500h+Type]; lpType
0x18009cd07  lea     rax, [rsp+500h+Data]
0x18009cd0c  mov     [rsp+500h+cbData], 4
0x18009cd14  xor     r8d, r8d; lpReserved
0x18009cd17  mov     [rsp+500h+phkResult], rax; lpData
0x18009cd1c  lea     rdx, aBreakonrcmstar; "BreakOnRCMStart"
0x18009cd23  call    cs:__imp_RegQueryValueExW
0x18009cd29  test    eax, eax
0x18009cd2b  jnz     short loc_18009CD60
0x18009cd2d  cmp     [rsp+500h+Type], 4
0x18009cd32  jnz     short loc_18009CD60
0x18009cd34  mov     eax, dword ptr [rsp+500h+Data]
0x18009cd38  sub     eax, 1
0x18009cd3b  jz      short loc_18009CD47
0x18009cd3d  sub     eax, 1
0x18009cd40  jz      short loc_18009CD70
0x18009cd42  cmp     eax, 1
0x18009cd45  jnz     short loc_18009CD60
0x18009cd47  call    cs:__imp_IsDebuggerPresent
0x18009cd4d  test    eax, eax
0x18009cd4f  jnz     short loc_18009CD5A
0x18009cd51  call    ?IsKernelDebuggerAttached@CUtils@@SAHXZ; CUtils::IsKernelDebuggerAttached(void)
0x18009cd56  test    eax, eax
0x18009cd58  jz      short loc_18009CD60
0x18009cd5a  call    cs:__imp_DebugBreak
0x18009cd60  mov     rcx, [rsp+500h+hKey]; hKey
0x18009cd65  call    cs:__imp_RegCloseKey
0x18009cd6b  jmp     loc_18009CED5
0x18009cd70  call    cs:__imp_IsDebuggerPresent
0x18009cd76  test    eax, eax
0x18009cd78  jnz     short loc_18009CD5A
0x18009cd7a  mov     rcx, [rsp+500h+hKey]; hKey
0x18009cd7f  lea     rax, [rsp+500h+cbData]
0x18009cd84  mov     [rsp+500h+lpcbData], rax; lpcbData
0x18009cd89  lea     r9, [rsp+500h+Type]; lpType
0x18009cd8e  lea     rax, [rbp+400h+var_210]
0x18009cd95  mov     [rsp+500h+cbData], 100h
0x18009cd9d  xor     r8d, r8d; lpReserved
0x18009cda0  mov     [rsp+500h+phkResult], rax; lpData
0x18009cda5  lea     rdx, aDebugger; "Debugger"
0x18009cdac  call    cs:__imp_RegQueryValueExW
0x18009cdb2  test    eax, eax
0x18009cdb4  jnz     loc_18009CEB6
0x18009cdba  cmp     [rsp+500h+Type], 1
0x18009cdbf  jnz     loc_18009CEB6
0x18009cdc5  xor     eax, eax
0x18009cdc7  lea     rcx, [rbp+400h+StartupInfo]; void *
0x18009cdcb  xorps   xmm0, xmm0
0x18009cdce  mov     qword ptr [rsp+500h+ProcessInformation.dwProcessId], rax
0x18009cdd3  xor     edx, edx; Val
0x18009cdd5  movups  xmmword ptr [rsp+500h+ProcessInformation.hProcess], xmm0
0x18009cdda  lea     r8d, [rax+68h]; Size
0x18009cdde  call    memset_0
0x18009cde3  call    cs:__imp_GetCurrentProcessId
0x18009cde9  lea     r8, aNtsdDGXPD; "ntsd -d -G -x -p %d"
0x18009cdf0  mov     edx, 100h; unsigned __int64
0x18009cdf5  mov     r9d, eax
0x18009cdf8  lea     rcx, [rbp+400h+CommandLine]; unsigned __int16 *
0x18009cdfc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009ce01  test    eax, eax
0x18009ce03  js      loc_18009CD60
0x18009ce09  lea     rdx, [rbp+400h+CommandLine]
0x18009ce0d  lea     rcx, aTermsrvExecuti; "TERMSRV:*-----------------* Executing:<"...
0x18009ce14  call    cs:__imp_DbgPrint
0x18009ce1a  xor     edx, edx; Val
0x18009ce1c  lea     rcx, [rbp+400h+StartupInfo+4]; void *
0x18009ce20  lea     r8d, [rdx+64h]; Size
0x18009ce24  call    memset_0
0x18009ce29  lea     rax, [rsp+500h+ProcessInformation]
0x18009ce2e  mov     [rbp+400h+StartupInfo.cb], 68h ; 'h'
0x18009ce35  mov     [rsp+500h+lpProcessInformation], rax; lpProcessInformation
0x18009ce3a  lea     rdx, [rbp+400h+CommandLine]; lpCommandLine
0x18009ce3e  lea     rax, [rbp+400h+StartupInfo]
0x18009ce42  xor     r9d, r9d; lpThreadAttributes
0x18009ce45  mov     [rsp+500h+lpStartupInfo], rax; lpStartupInfo
0x18009ce4a  xor     r8d, r8d; lpProcessAttributes
0x18009ce4d  mov     [rsp+500h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18009ce56  xor     ecx, ecx; lpApplicationName
0x18009ce58  mov     [rsp+500h+lpEnvironment], 0; lpEnvironment
0x18009ce61  mov     dword ptr [rsp+500h+lpcbData], 0; dwCreationFlags
0x18009ce69  mov     dword ptr [rsp+500h+phkResult], 0; bInheritHandles
0x18009ce71  call    cs:__imp_CreateProcessW
0x18009ce77  test    eax, eax
0x18009ce79  jnz     short loc_18009CE84
0x18009ce7b  lea     rcx, aTermsrvTermsrv; "TERMSRV:*-----------------* TERMSRV:Cre"...
0x18009ce82  jmp     short loc_18009CEBD
0x18009ce84  mov     rcx, [rsp+500h+ProcessInformation.hProcess]; hObject
0x18009ce89  call    cs:__imp_CloseHandle
0x18009ce8f  mov     rcx, [rsp+500h+ProcessInformation.hThread]; hObject
0x18009ce94  call    cs:__imp_CloseHandle
0x18009ce9a  jmp     short loc_18009CEA7
0x18009ce9c  mov     ecx, 1F4h; dwMilliseconds
0x18009cea1  call    cs:__imp_Sleep
0x18009cea7  call    cs:__imp_IsDebuggerPresent
0x18009cead  test    eax, eax
0x18009ceaf  jz      short loc_18009CE9C
0x18009ceb1  jmp     loc_18009CD60
0x18009ceb6  lea     rcx, aTermsrvDidNotF; "TERMSRV:*-----------------* Did not fin"...
0x18009cebd  call    cs:__imp_DbgPrint
0x18009cec3  jmp     loc_18009CD60
0x18009cec8  lea     rcx, aTermsrvCouldNo; "TERMSRV:*-----------------* Could not o"...
0x18009cecf  call    cs:__imp_DbgPrint
0x18009ced5  mov     rcx, [rbp+400h+var_10]
0x18009cedc  xor     rcx, rsp; StackCookie
0x18009cedf  call    __security_check_cookie
0x18009cee4  add     rsp, 500h
0x18009ceeb  pop     rbp
0x18009ceec  retn
```
