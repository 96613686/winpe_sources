# UninstallWrapperMsi(void *)

- ea: `0x14000b84c`
- end: `0x14000bbd8`
- name: `?UninstallWrapperMsi@@YAJPEAX@Z`
- size: `908`
- prototype: `__int64 __fastcall(HANDLE hToken)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140006fb8`

## callees

- `0x140001a63`
- `0x1400044e0`
- `0x1400087e4`
- `0x14000b84c`
- `0x14000e280`
- `0x140013490`
- `0x140014910`
- `0x140015010`

## import_xrefs

- `ADVAPI32!CreateProcessAsUserW` at `0x14000ba1d`
- `ADVAPI32!CreateProcessAsUserW` at `0x14000ba1d`
- `KERNEL32!CloseHandle` at `0x14000bb4b`
- `KERNEL32!CloseHandle` at `0x14000bb60`
- `KERNEL32!CloseHandle` at `0x14000bb4b`
- `KERNEL32!CloseHandle` at `0x14000bb60`
- `KERNEL32!LocalFree` at `0x14000bba9`
- `KERNEL32!LocalFree` at `0x14000bba9`
- `KERNEL32!GetSystemDirectoryW` at `0x14000b955`
- `KERNEL32!GetSystemDirectoryW` at `0x14000b955`
- `KERNEL32!GetExitCodeProcess` at `0x14000ba96`
- `KERNEL32!GetExitCodeProcess` at `0x14000ba96`
- `KERNEL32!GetLastError` at `0x14000ba27`
- `KERNEL32!GetLastError` at `0x14000ba61`
- `KERNEL32!GetLastError` at `0x14000baa0`
- `KERNEL32!GetLastError` at `0x14000bb0e`
- `KERNEL32!GetLastError` at `0x14000ba27`
- `KERNEL32!GetLastError` at `0x14000ba61`
- `KERNEL32!GetLastError` at `0x14000baa0`
- `KERNEL32!GetLastError` at `0x14000bb0e`
- `KERNEL32!WaitForSingleObject` at `0x14000ba57`
- `KERNEL32!WaitForSingleObject` at `0x14000ba57`
- `msvcrt!wcsrchr` at `0x14000b971`
- `msvcrt!wcsrchr` at `0x14000b971`

## string_xrefs

- `0x14000b8b3`: `Failed to load  msi.dll with error 0x%x`
- `0x14000b8bf`: `UninstallWrapperMsi`
- `0x14000b8e6`: `UninstallWrapperMsi`
- `0x14000b8f1`: `Failed to set MSI internal UI level to none`
- `0x14000b939`: `Failed to uninstall the wrapper MSI %ls`
- `0x14000bb23`: `Failed to get system directory`
- `0x14000b992`: `%ls\msiexec.exe /quiet /x %ls`
- `0x14000b9b0`: `Failed to build msiexec.exe command line`
- `0x14000ba3c`: `Failed: CreateProcessAsUser()`
- `0x14000ba76`: `Failed to wait on msiexec.exe process`
- `0x14000bab5`: `Failed to get exit code of msiexec.exe process.`
- `0x14000bae0`: `Failed: msiexec.exe failed with error code %u`
- `0x14000baf1`: `Succeeded to uninstall the wrapper MSI %ls`

## pseudocode

```c
__int64 __fastcall UninstallWrapperMsi(HANDLE hToken)
{
  int v2; // eax
  signed int v3; // ebx
  int v4; // eax
  wchar_t *v5; // rax
  signed int v6; // eax
  const char *v7; // r8
  __int64 v8; // rdx
  signed int v9; // eax
  signed int v10; // eax
  signed int LastError; // eax
  void *v12; // rsi
  DWORD ExitCode[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-98h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v18[526]; // [rsp+F2h] [rbp-Eh] BYREF

  Buffer = 0;
  memset_0(v18, 0, 0x206u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v2 = MsiLoad();
  v3 = v2;
  if ( v2 < 0 )
  {
    WusaLogDebugEventA(L"UninstallWrapperMsi", 1853, "Failed to load  msi.dll with error 0x%x", (unsigned int)v2);
    goto LABEL_42;
  }
  if ( !(unsigned int)((__int64 (__fastcall *)(__int64))qword_140020C30)(2) )
    WusaLogDebugEventA(L"UninstallWrapperMsi", 1858, "Failed to set MSI internal UI level to none");
  if ( !hToken )
  {
    v4 = ((__int64 (__fastcall *)(LPCWSTR, _QWORD, __int64))qword_140020C38)(String2, 0, 2);
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    if ( v3 < 0 )
    {
      WusaLogDebugEventA(L"UninstallWrapperMsi", 1869, "Failed to uninstall the wrapper MSI %ls", String2);
      goto LABEL_42;
    }
LABEL_34:
    WusaLogDebugEventA(L"UninstallWrapperMsi", 1922, "Succeeded to uninstall the wrapper MSI %ls", String2);
    goto LABEL_42;
  }
  if ( GetSystemDirectoryW(&Buffer, 0x104u) - 1 > 0x102 )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v7 = "Failed to get system directory";
    v8 = 1877;
  }
  else
  {
    v5 = wcsrchr(&Buffer, 0x5Cu);
    if ( v5 && !v5[1] )
      *v5 = 0;
    v3 = StringCchPrintfW(&Buffer, 0x104u, L"%ls\\msiexec.exe /quiet /x %ls", &Buffer, String2);
    if ( v3 < 0 )
    {
      WusaLogDebugEventA(L"UninstallWrapperMsi", 1883, "Failed to build msiexec.exe command line");
      goto LABEL_42;
    }
    memset_0(&StartupInfo, 0, sizeof(StartupInfo));
    StartupInfo.cb = 104;
    StartupInfo.lpDesktop = L"winsta0\\default";
    if ( CreateProcessAsUserW(hToken, 0, &Buffer, 0, 0, 0, 0x400u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      if ( WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF) == -1 )
      {
        v9 = GetLastError();
        v3 = v9;
        if ( v9 > 0 )
          v3 = (unsigned __int16)v9 | 0x80070000;
        v7 = "Failed to wait on msiexec.exe process";
        v8 = 1908;
      }
      else
      {
        ExitCode[0] = 0;
        if ( GetExitCodeProcess(ProcessInformation.hProcess, ExitCode) )
        {
          if ( (int)ExitCode[0] > 0 )
            v3 = LOWORD(ExitCode[0]) | 0x80070000;
          else
            v3 = ExitCode[0];
          if ( v3 < 0 )
          {
            WusaLogDebugEventA(
              L"UninstallWrapperMsi",
              1919,
              "Failed: msiexec.exe failed with error code %u",
              ExitCode[0]);
            goto LABEL_42;
          }
          goto LABEL_34;
        }
        v10 = GetLastError();
        v3 = v10;
        if ( v10 > 0 )
          v3 = (unsigned __int16)v10 | 0x80070000;
        v7 = "Failed to get exit code of msiexec.exe process.";
        v8 = 1915;
      }
    }
    else
    {
      v6 = GetLastError();
      v3 = v6;
      if ( v6 > 0 )
        v3 = (unsigned __int16)v6 | 0x80070000;
      v7 = "Failed: CreateProcessAsUser()";
      v8 = 1902;
    }
  }
  if ( v3 >= 0 )
    v3 = -2147467259;
  WusaLogDebugEventA(L"UninstallWrapperMsi", v8, v7);
LABEL_42:
  if ( ProcessInformation.hProcess )
  {
    CloseHandle(ProcessInformation.hProcess);
    ProcessInformation.hProcess = 0;
  }
  if ( ProcessInformation.hThread )
  {
    CloseHandle(ProcessInformation.hThread);
    ProcessInformation.hThread = 0;
  }
  if ( v3 < 0 )
  {
    *(_QWORD *)ExitCode = 0;
    WusaGetErrorMessage(v3, (unsigned __int16 **)ExitCode);
    v12 = *(void **)ExitCode;
    WusaLogDebugEventA(L"UninstallWrapperMsi", 1929, "Exit with error code 0X%x (%ls)", v3, *(const wchar_t **)ExitCode);
    if ( v12 )
      LocalFree(v12);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000b84c  mov     [rsp-8+arg_8], rbx
0x14000b851  mov     [rsp-8+arg_10], rsi
0x14000b856  push    rbp
0x14000b857  push    rdi
0x14000b858  push    r14
0x14000b85a  lea     rbp, [rsp-210h]
0x14000b862  sub     rsp, 310h
0x14000b869  mov     rax, cs:__security_cookie
0x14000b870  xor     rax, rsp
0x14000b873  mov     [rbp+220h+var_20], rax
0x14000b87a  mov     rsi, rcx
0x14000b87d  xor     r14d, r14d
0x14000b880  lea     rcx, [rbp+220h+var_22E]; void *
0x14000b884  mov     [rbp+220h+Buffer], r14w
0x14000b889  xor     edx, edx; Val
0x14000b88b  mov     r8d, 206h; Size
0x14000b891  call    memset_0
0x14000b896  xorps   xmm0, xmm0
0x14000b899  xor     eax, eax
0x14000b89b  movups  xmmword ptr [rsp+320h+ProcessInformation.hProcess], xmm0
0x14000b8a0  mov     qword ptr [rsp+320h+ProcessInformation.dwProcessId], rax
0x14000b8a5  call    ?MsiLoad@@YAJXZ; MsiLoad(void)
0x14000b8aa  mov     ebx, eax
0x14000b8ac  test    eax, eax
0x14000b8ae  jns     short loc_14000B8D3
0x14000b8b0  mov     r9d, eax
0x14000b8b3  lea     r8, aFailedToLoadMs_0; "Failed to load  msi.dll with error 0x%x"
0x14000b8ba  mov     edx, 73Dh
0x14000b8bf  lea     rdi, aUninstallwrapp; "UninstallWrapperMsi"
0x14000b8c6  mov     rcx, rdi
0x14000b8c9  call    WusaLogDebugEventA
0x14000b8ce  jmp     loc_14000BB41
0x14000b8d3  mov     rax, cs:qword_140020C30
0x14000b8da  xor     edx, edx
0x14000b8dc  lea     ebx, [rdx+2]
0x14000b8df  mov     ecx, ebx
0x14000b8e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b8e6  lea     rdi, aUninstallwrapp; "UninstallWrapperMsi"
0x14000b8ed  test    eax, eax
0x14000b8ef  jnz     short loc_14000B905
0x14000b8f1  lea     r8, aFailedToSetMsi; "Failed to set MSI internal UI level to "...
0x14000b8f8  mov     edx, 742h
0x14000b8fd  mov     rcx, rdi
0x14000b900  call    WusaLogDebugEventA
0x14000b905  test    rsi, rsi
0x14000b908  jnz     short loc_14000B94A
0x14000b90a  mov     rcx, cs:String2
0x14000b911  mov     r8d, ebx
0x14000b914  mov     rax, cs:qword_140020C38
0x14000b91b  xor     edx, edx
0x14000b91d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b922  mov     ebx, eax
0x14000b924  test    eax, eax
0x14000b926  jle     short loc_14000B931
0x14000b928  movzx   ebx, ax
0x14000b92b  or      ebx, 80070000h
0x14000b931  test    ebx, ebx
0x14000b933  jns     loc_14000BAF1
0x14000b939  lea     r8, aFailedToUninst; "Failed to uninstall the wrapper MSI %ls"
0x14000b940  mov     edx, 74Dh
0x14000b945  jmp     loc_14000BAFD
0x14000b94a  mov     ebx, 104h
0x14000b94f  lea     rcx, [rbp+220h+Buffer]; lpBuffer
0x14000b953  mov     edx, ebx; uSize
0x14000b955  call    cs:__imp_GetSystemDirectoryW
0x14000b95b  dec     eax
0x14000b95d  cmp     eax, 102h
0x14000b962  ja      loc_14000BB0E
0x14000b968  mov     edx, 5Ch ; '\'; Ch
0x14000b96d  lea     rcx, [rbp+220h+Buffer]; Str
0x14000b971  call    cs:__imp_wcsrchr
0x14000b977  test    rax, rax
0x14000b97a  jz      short loc_14000B987
0x14000b97c  cmp     [rax+2], r14w
0x14000b981  jnz     short loc_14000B987
0x14000b983  mov     [rax], r14w
0x14000b987  mov     rax, cs:String2
0x14000b98e  lea     r9, [rbp+220h+Buffer]
0x14000b992  lea     r8, aLsMsiexecExeQu; "%ls\\msiexec.exe /quiet /x %ls"
0x14000b999  mov     [rsp+320h+lpThreadAttributes], rax
0x14000b99e  mov     rdx, rbx; unsigned __int64
0x14000b9a1  lea     rcx, [rbp+220h+Buffer]; unsigned __int16 *
0x14000b9a5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000b9aa  mov     ebx, eax
0x14000b9ac  test    eax, eax
0x14000b9ae  jns     short loc_14000B9C1
0x14000b9b0  lea     r8, aFailedToBuildM; "Failed to build msiexec.exe command lin"...
0x14000b9b7  mov     edx, 75Bh
0x14000b9bc  jmp     loc_14000BB39
0x14000b9c1  mov     ebx, 68h ; 'h'
0x14000b9c6  lea     rcx, [rbp+220h+StartupInfo]; void *
0x14000b9ca  mov     r8d, ebx; Size
0x14000b9cd  xor     edx, edx; Val
0x14000b9cf  call    memset_0
0x14000b9d4  lea     rax, aWinsta0Default; "winsta0\\default"
0x14000b9db  mov     [rbp+220h+StartupInfo.cb], ebx
0x14000b9de  mov     [rbp+220h+StartupInfo.lpDesktop], rax
0x14000b9e2  lea     r8, [rbp+220h+Buffer]; lpCommandLine
0x14000b9e6  lea     rax, [rsp+320h+ProcessInformation]
0x14000b9eb  xor     r9d, r9d; lpProcessAttributes
0x14000b9ee  mov     [rsp+320h+lpProcessInformation], rax; lpProcessInformation
0x14000b9f3  xor     edx, edx; lpApplicationName
0x14000b9f5  lea     rax, [rbp+220h+StartupInfo]
0x14000b9f9  mov     rcx, rsi; hToken
0x14000b9fc  mov     [rsp+320h+lpStartupInfo], rax; lpStartupInfo
0x14000ba01  mov     [rsp+320h+lpCurrentDirectory], r14; lpCurrentDirectory
0x14000ba06  mov     [rsp+320h+lpEnvironment], r14; lpEnvironment
0x14000ba0b  mov     [rsp+320h+dwCreationFlags], 400h; dwCreationFlags
0x14000ba13  mov     [rsp+320h+bInheritHandles], r14d; bInheritHandles
0x14000ba18  mov     [rsp+320h+lpThreadAttributes], r14; lpThreadAttributes
0x14000ba1d  call    cs:__imp_CreateProcessAsUserW
0x14000ba23  test    eax, eax
0x14000ba25  jnz     short loc_14000BA4D
0x14000ba27  call    cs:__imp_GetLastError
0x14000ba2d  mov     ebx, eax
0x14000ba2f  test    eax, eax
0x14000ba31  jle     short loc_14000BA3C
0x14000ba33  movzx   ebx, ax
0x14000ba36  or      ebx, 80070000h
0x14000ba3c  lea     r8, aFailedCreatepr; "Failed: CreateProcessAsUser()"
0x14000ba43  mov     edx, 76Eh
0x14000ba48  jmp     loc_14000BB2F
0x14000ba4d  mov     rcx, [rsp+320h+ProcessInformation.hProcess]; hHandle
0x14000ba52  or      ebx, 0FFFFFFFFh
0x14000ba55  mov     edx, ebx; dwMilliseconds
0x14000ba57  call    cs:__imp_WaitForSingleObject
0x14000ba5d  cmp     eax, ebx
0x14000ba5f  jnz     short loc_14000BA87
0x14000ba61  call    cs:__imp_GetLastError
0x14000ba67  mov     ebx, eax
0x14000ba69  test    eax, eax
0x14000ba6b  jle     short loc_14000BA76
0x14000ba6d  movzx   ebx, ax
0x14000ba70  or      ebx, 80070000h
0x14000ba76  lea     r8, aFailedToWaitOn; "Failed to wait on msiexec.exe process"
0x14000ba7d  mov     edx, 774h
0x14000ba82  jmp     loc_14000BB2F
0x14000ba87  mov     rcx, [rsp+320h+ProcessInformation.hProcess]; hProcess
0x14000ba8c  lea     rdx, [rsp+320h+ExitCode]; lpExitCode
0x14000ba91  mov     [rsp+320h+ExitCode], r14d
0x14000ba96  call    cs:__imp_GetExitCodeProcess
0x14000ba9c  test    eax, eax
0x14000ba9e  jnz     short loc_14000BAC3
0x14000baa0  call    cs:__imp_GetLastError
0x14000baa6  mov     ebx, eax
0x14000baa8  test    eax, eax
0x14000baaa  jle     short loc_14000BAB5
0x14000baac  movzx   ebx, ax
0x14000baaf  or      ebx, 80070000h
0x14000bab5  lea     r8, aFailedToGetExi; "Failed to get exit code of msiexec.exe "...
0x14000babc  mov     edx, 77Bh
0x14000bac1  jmp     short loc_14000BB2F
0x14000bac3  mov     r9d, [rsp+320h+ExitCode]
0x14000bac8  test    r9d, r9d
0x14000bacb  jg      short loc_14000BAD2
0x14000bacd  mov     ebx, r9d
0x14000bad0  jmp     short loc_14000BADC
0x14000bad2  movzx   ebx, r9w
0x14000bad6  or      ebx, 80070000h
0x14000badc  test    ebx, ebx
0x14000bade  jns     short loc_14000BAF1
0x14000bae0  lea     r8, aFailedMsiexecE; "Failed: msiexec.exe failed with error c"...
0x14000bae7  mov     edx, 77Fh
0x14000baec  jmp     loc_14000B8C6
0x14000baf1  lea     r8, aSucceededToUni; "Succeeded to uninstall the wrapper MSI "...
0x14000baf8  mov     edx, 782h
0x14000bafd  mov     r9, cs:String2
0x14000bb04  mov     rcx, rdi
0x14000bb07  call    WusaLogDebugEventA
0x14000bb0c  jmp     short loc_14000BB41
0x14000bb0e  call    cs:__imp_GetLastError
0x14000bb14  mov     ebx, eax
0x14000bb16  test    eax, eax
0x14000bb18  jle     short loc_14000BB23
0x14000bb1a  movzx   ebx, ax
0x14000bb1d  or      ebx, 80070000h
0x14000bb23  lea     r8, aFailedToGetSys_0; "Failed to get system directory"
0x14000bb2a  mov     edx, 755h
0x14000bb2f  test    ebx, ebx
0x14000bb31  mov     eax, 80004005h
0x14000bb36  cmovns  ebx, eax
0x14000bb39  mov     rcx, rdi
0x14000bb3c  call    WusaLogDebugEventA
0x14000bb41  mov     rcx, [rsp+320h+ProcessInformation.hProcess]; hObject
0x14000bb46  test    rcx, rcx
0x14000bb49  jz      short loc_14000BB56
0x14000bb4b  call    cs:__imp_CloseHandle
0x14000bb51  mov     [rsp+320h+ProcessInformation.hProcess], r14
0x14000bb56  mov     rcx, [rsp+320h+ProcessInformation.hThread]; hObject
0x14000bb5b  test    rcx, rcx
0x14000bb5e  jz      short loc_14000BB6B
0x14000bb60  call    cs:__imp_CloseHandle
0x14000bb66  mov     [rsp+320h+ProcessInformation.hThread], r14
0x14000bb6b  test    ebx, ebx
0x14000bb6d  jns     short loc_14000BBAF
0x14000bb6f  lea     rdx, [rsp+320h+ExitCode]; unsigned __int16 **
0x14000bb74  mov     qword ptr [rsp+320h+ExitCode], r14
0x14000bb79  mov     ecx, ebx; dwMessageId
0x14000bb7b  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x14000bb80  mov     rsi, qword ptr [rsp+320h+ExitCode]
0x14000bb85  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x14000bb8c  mov     r9d, ebx
0x14000bb8f  mov     [rsp+320h+lpThreadAttributes], rsi
0x14000bb94  mov     edx, 789h
0x14000bb99  mov     rcx, rdi
0x14000bb9c  call    WusaLogDebugEventA
0x14000bba1  test    rsi, rsi
0x14000bba4  jz      short loc_14000BBAF
0x14000bba6  mov     rcx, rsi; hMem
0x14000bba9  call    cs:__imp_LocalFree
0x14000bbaf  mov     eax, ebx
0x14000bbb1  mov     rcx, [rbp+220h+var_20]
0x14000bbb8  xor     rcx, rsp; StackCookie
0x14000bbbb  call    __security_check_cookie
0x14000bbc0  lea     r11, [rsp+320h+var_10]
0x14000bbc8  mov     rbx, [r11+28h]
0x14000bbcc  mov     rsi, [r11+30h]
0x14000bbd0  mov     rsp, r11
0x14000bbd3  pop     r14
0x14000bbd5  pop     rdi
0x14000bbd6  pop     rbp
0x14000bbd7  retn
```
