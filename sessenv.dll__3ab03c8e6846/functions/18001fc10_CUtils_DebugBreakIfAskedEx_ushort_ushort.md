# CUtils::DebugBreakIfAskedEx(ushort *,ushort *)

- ea: `0x18001fc10`
- end: `0x18001febd`
- name: `?DebugBreakIfAskedEx@CUtils@@SAXPEAG0@Z`
- size: `685`
- prototype: `void __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001d7f4`

## callees

- `0x180017b30`
- `0x18001a280`
- `0x18001ad5c`
- `0x18001fc10`
- `0x180021188`

## import_xrefs

- `ntdll!DbgPrint` at `0x18001fde4`
- `ntdll!DbgPrint` at `0x18001fe8d`
- `ntdll!DbgPrint` at `0x18001fe9f`
- `ntdll!DbgPrint` at `0x18001fde4`
- `ntdll!DbgPrint` at `0x18001fe8d`
- `ntdll!DbgPrint` at `0x18001fe9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fe59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fe64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fe59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fe64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fc74`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fc74`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001fcb2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001fcf3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001fd7c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001fcb2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001fcf3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001fd7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fd35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fd35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001fdb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001fdb3`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001fe41`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001fe41`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18001fd2a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18001fd2a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001fd17`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001fd40`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001fe77`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001fd17`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001fd40`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001fe77`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001fe71`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001fe71`

## string_xrefs

- `0x18001fe4b`: `TERMSRV:*-----------------* TERMSRV:CreateProcess failed *-----------------*\n`
- `0x18001fe98`: `TERMSRV:*-----------------* Could not open termsrv registry *-----------------*\n`

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
      if ( RegQueryValueExW(hKey, L"SessEnvBreakOnStart", 0, &Type, Data, &cbData) || Type != 4 )
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
            if ( StringCchPrintfW(CommandLine, 0x100u, L"ntsd -d -G -x -p %d", CurrentProcessId) >= 0 )
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
0x18001fc10  push    rbp
0x18001fc12  lea     rbp, [rsp-400h]
0x18001fc1a  sub     rsp, 500h
0x18001fc21  mov     rax, cs:__security_cookie
0x18001fc28  xor     rax, rsp
0x18001fc2b  mov     [rbp+400h+var_10], rax
0x18001fc32  lea     rax, [rsp+500h+hKey]
0x18001fc37  mov     [rsp+500h+hKey], 0
0x18001fc40  mov     r9d, 20019h; samDesired
0x18001fc46  mov     [rsp+500h+phkResult], rax; phkResult
0x18001fc4b  xor     r8d, r8d; ulOptions
0x18001fc4e  mov     dword ptr [rsp+500h+Data], 0
0x18001fc56  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x18001fc5d  mov     [rsp+500h+Type], 0
0x18001fc65  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001fc6c  mov     [rsp+500h+cbData], 0
0x18001fc74  call    cs:__imp_RegOpenKeyExW
0x18001fc7a  test    eax, eax
0x18001fc7c  jnz     loc_18001FE98
0x18001fc82  mov     rcx, [rsp+500h+hKey]; hKey
0x18001fc87  lea     rax, [rsp+500h+cbData]
0x18001fc8c  mov     [rsp+500h+lpcbData], rax; lpcbData
0x18001fc91  lea     r9, [rsp+500h+Type]; lpType
0x18001fc96  lea     rax, [rsp+500h+Data]
0x18001fc9b  mov     [rsp+500h+cbData], 4
0x18001fca3  xor     r8d, r8d; lpReserved
0x18001fca6  mov     [rsp+500h+phkResult], rax; lpData
0x18001fcab  lea     rdx, aDebugts; "DebugTS"
0x18001fcb2  call    cs:__imp_RegQueryValueExW
0x18001fcb8  test    eax, eax
0x18001fcba  jnz     short loc_18001FCC3
0x18001fcbc  cmp     [rsp+500h+Type], 4
0x18001fcc1  jz      short loc_18001FD04
0x18001fcc3  mov     rcx, [rsp+500h+hKey]; hKey
0x18001fcc8  lea     rax, [rsp+500h+cbData]
0x18001fccd  mov     [rsp+500h+lpcbData], rax; lpcbData
0x18001fcd2  lea     r9, [rsp+500h+Type]; lpType
0x18001fcd7  lea     rax, [rsp+500h+Data]
0x18001fcdc  mov     [rsp+500h+cbData], 4
0x18001fce4  xor     r8d, r8d; lpReserved
0x18001fce7  mov     [rsp+500h+phkResult], rax; lpData
0x18001fcec  lea     rdx, aSessenvbreakon; "SessEnvBreakOnStart"
0x18001fcf3  call    cs:__imp_RegQueryValueExW
0x18001fcf9  test    eax, eax
0x18001fcfb  jnz     short loc_18001FD30
0x18001fcfd  cmp     [rsp+500h+Type], 4
0x18001fd02  jnz     short loc_18001FD30
0x18001fd04  mov     eax, dword ptr [rsp+500h+Data]
0x18001fd08  sub     eax, 1
0x18001fd0b  jz      short loc_18001FD17
0x18001fd0d  sub     eax, 1
0x18001fd10  jz      short loc_18001FD40
0x18001fd12  cmp     eax, 1
0x18001fd15  jnz     short loc_18001FD30
0x18001fd17  call    cs:__imp_IsDebuggerPresent
0x18001fd1d  test    eax, eax
0x18001fd1f  jnz     short loc_18001FD2A
0x18001fd21  call    ?IsKernelDebuggerAttached@CUtils@@SAHXZ; CUtils::IsKernelDebuggerAttached(void)
0x18001fd26  test    eax, eax
0x18001fd28  jz      short loc_18001FD30
0x18001fd2a  call    cs:__imp_DebugBreak
0x18001fd30  mov     rcx, [rsp+500h+hKey]; hKey
0x18001fd35  call    cs:__imp_RegCloseKey
0x18001fd3b  jmp     loc_18001FEA5
0x18001fd40  call    cs:__imp_IsDebuggerPresent
0x18001fd46  test    eax, eax
0x18001fd48  jnz     short loc_18001FD2A
0x18001fd4a  mov     rcx, [rsp+500h+hKey]; hKey
0x18001fd4f  lea     rax, [rsp+500h+cbData]
0x18001fd54  mov     [rsp+500h+lpcbData], rax; lpcbData
0x18001fd59  lea     r9, [rsp+500h+Type]; lpType
0x18001fd5e  lea     rax, [rbp+400h+var_210]
0x18001fd65  mov     [rsp+500h+cbData], 100h
0x18001fd6d  xor     r8d, r8d; lpReserved
0x18001fd70  mov     [rsp+500h+phkResult], rax; lpData
0x18001fd75  lea     rdx, aDebugger; "Debugger"
0x18001fd7c  call    cs:__imp_RegQueryValueExW
0x18001fd82  test    eax, eax
0x18001fd84  jnz     loc_18001FE86
0x18001fd8a  cmp     [rsp+500h+Type], 1
0x18001fd8f  jnz     loc_18001FE86
0x18001fd95  xor     eax, eax
0x18001fd97  lea     rcx, [rbp+400h+StartupInfo]; void *
0x18001fd9b  xorps   xmm0, xmm0
0x18001fd9e  mov     qword ptr [rsp+500h+ProcessInformation.dwProcessId], rax
0x18001fda3  xor     edx, edx; Val
0x18001fda5  movups  xmmword ptr [rsp+500h+ProcessInformation.hProcess], xmm0
0x18001fdaa  lea     r8d, [rax+68h]; Size
0x18001fdae  call    memset_0
0x18001fdb3  call    cs:__imp_GetCurrentProcessId
0x18001fdb9  lea     r8, aNtsdDGXPD; "ntsd -d -G -x -p %d"
0x18001fdc0  mov     edx, 100h; unsigned __int64
0x18001fdc5  mov     r9d, eax
0x18001fdc8  lea     rcx, [rbp+400h+CommandLine]; unsigned __int16 *
0x18001fdcc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001fdd1  test    eax, eax
0x18001fdd3  js      loc_18001FD30
0x18001fdd9  lea     rdx, [rbp+400h+CommandLine]
0x18001fddd  lea     rcx, Format; "TERMSRV:*-----------------* Executing:<"...
0x18001fde4  call    cs:__imp_DbgPrint
0x18001fdea  xor     edx, edx; Val
0x18001fdec  lea     rcx, [rbp+400h+StartupInfo+4]; void *
0x18001fdf0  lea     r8d, [rdx+64h]; Size
0x18001fdf4  call    memset_0
0x18001fdf9  lea     rax, [rsp+500h+ProcessInformation]
0x18001fdfe  mov     [rbp+400h+StartupInfo.cb], 68h ; 'h'
0x18001fe05  mov     [rsp+500h+lpProcessInformation], rax; lpProcessInformation
0x18001fe0a  lea     rdx, [rbp+400h+CommandLine]; lpCommandLine
0x18001fe0e  lea     rax, [rbp+400h+StartupInfo]
0x18001fe12  xor     r9d, r9d; lpThreadAttributes
0x18001fe15  mov     [rsp+500h+lpStartupInfo], rax; lpStartupInfo
0x18001fe1a  xor     r8d, r8d; lpProcessAttributes
0x18001fe1d  mov     [rsp+500h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18001fe26  xor     ecx, ecx; lpApplicationName
0x18001fe28  mov     [rsp+500h+lpEnvironment], 0; lpEnvironment
0x18001fe31  mov     dword ptr [rsp+500h+lpcbData], 0; dwCreationFlags
0x18001fe39  mov     dword ptr [rsp+500h+phkResult], 0; bInheritHandles
0x18001fe41  call    cs:__imp_CreateProcessW
0x18001fe47  test    eax, eax
0x18001fe49  jnz     short loc_18001FE54
0x18001fe4b  lea     rcx, aTermsrvTermsrv; "TERMSRV:*-----------------* TERMSRV:Cre"...
0x18001fe52  jmp     short loc_18001FE8D
0x18001fe54  mov     rcx, [rsp+500h+ProcessInformation.hProcess]; hObject
0x18001fe59  call    cs:__imp_CloseHandle
0x18001fe5f  mov     rcx, [rsp+500h+ProcessInformation.hThread]; hObject
0x18001fe64  call    cs:__imp_CloseHandle
0x18001fe6a  jmp     short loc_18001FE77
0x18001fe6c  mov     ecx, 1F4h; dwMilliseconds
0x18001fe71  call    cs:__imp_Sleep
0x18001fe77  call    cs:__imp_IsDebuggerPresent
0x18001fe7d  test    eax, eax
0x18001fe7f  jz      short loc_18001FE6C
0x18001fe81  jmp     loc_18001FD30
0x18001fe86  lea     rcx, aTermsrvDidNotF; "TERMSRV:*-----------------* Did not fin"...
0x18001fe8d  call    cs:__imp_DbgPrint
0x18001fe93  jmp     loc_18001FD30
0x18001fe98  lea     rcx, aTermsrvCouldNo; "TERMSRV:*-----------------* Could not o"...
0x18001fe9f  call    cs:__imp_DbgPrint
0x18001fea5  mov     rcx, [rbp+400h+var_10]
0x18001feac  xor     rcx, rsp; StackCookie
0x18001feaf  call    __security_check_cookie
0x18001feb4  add     rsp, 500h
0x18001febb  pop     rbp
0x18001febc  retn
```
