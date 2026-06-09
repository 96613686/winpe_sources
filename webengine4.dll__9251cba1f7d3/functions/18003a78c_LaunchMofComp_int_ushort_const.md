# LaunchMofComp(int,ushort const *)

- ea: `0x18003a78c`
- end: `0x18003aa64`
- name: `?LaunchMofComp@@YAJHPEBG@Z`
- size: `728`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180039d08`
- `0x18003ea5c`
- `0x18003ef38`
- `0x18003fd70`
- `0x180040830`

## callees

- `0x180007824`
- `0x18003a78c`
- `0x18003abe4`
- `0x180040fa0`
- `0x18004d030`
- `0x18004d350`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18003a9f5`
- `KERNEL32!CloseHandle` at `0x18003aa05`
- `KERNEL32!CloseHandle` at `0x18003aa14`
- `KERNEL32!CloseHandle` at `0x18003a9f5`
- `KERNEL32!CloseHandle` at `0x18003aa05`
- `KERNEL32!CloseHandle` at `0x18003aa14`
- `KERNEL32!CreateFileW` at `0x18003a943`
- `KERNEL32!CreateFileW` at `0x18003a943`
- `KERNEL32!WaitForSingleObject` at `0x18003a9b8`
- `KERNEL32!WaitForSingleObject` at `0x18003a9b8`
- `KERNEL32!GetExitCodeProcess` at `0x18003a9d0`
- `KERNEL32!GetExitCodeProcess` at `0x18003a9d0`
- `KERNEL32!CreateProcessW` at `0x18003a9a0`
- `KERNEL32!CreateProcessW` at `0x18003a9a0`
- `KERNEL32!GetWindowsDirectoryW` at `0x18003a826`
- `KERNEL32!GetWindowsDirectoryW` at `0x18003a826`

## string_xrefs

- `0x18003a7c8`: `Installing WMI file:`
- `0x18003aa1a`: `Installing WMI file:`
- `0x18003a7d3`: `InstallMOF`
- `0x18003aa29`: `InstallMOF`
- `0x18003a862`: `system32\wbem\mofcomp.exe`
- `0x18003a882`: `mofcomp `

## pseudocode

```c
__int64 __fastcall LaunchMofComp(int a1, const unsigned __int16 *a2)
{
  __int64 v4; // rdi
  unsigned int LastWin32Error; // ebx
  int v6; // eax
  const unsigned __int16 *v7; // r8
  HANDLE v8; // rax
  DWORD ExitCode; // [rsp+50h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  WCHAR CommandLine[520]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR Buffer[520]; // [rsp+510h] [rbp+410h] BYREF

  v4 = -1;
  CSetupLogging::Log(1, "InstallMOF", 0, "Installing WMI file:", a2);
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  CommandLine[0] = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  Buffer[0] = 0;
  if ( !GetWindowsDirectoryW(Buffer, 0x105u) )
  {
LABEL_2:
    LastWin32Error = GetLastWin32Error();
    goto LABEL_19;
  }
  LastWin32Error = StringCchCatW(Buffer, 0x208u, L"\\");
  if ( !LastWin32Error )
  {
    LastWin32Error = StringCchCatW(Buffer, 0x208u, L"system32\\wbem\\mofcomp.exe");
    if ( !LastWin32Error )
    {
      LastWin32Error = StringCchCatW(CommandLine, 0x208u, L"mofcomp ");
      if ( !LastWin32Error )
      {
        if ( a1 )
          goto LABEL_11;
        v6 = IsWow64();
        v7 = &Names::s_wszInstallDirectory64;
        if ( !v6 )
          v7 = &Names::s_wszInstallDirectory;
        LastWin32Error = StringCchCatW(CommandLine, 0x208u, v7);
        if ( !LastWin32Error )
        {
          LastWin32Error = StringCchCatW(CommandLine, 0x208u, L"\\");
          if ( !LastWin32Error )
          {
LABEL_11:
            LastWin32Error = StringCchCatW(CommandLine, 0x208u, a2);
            if ( !LastWin32Error )
            {
              SecurityAttributes.nLength = 24;
              SecurityAttributes.lpSecurityDescriptor = 0;
              SecurityAttributes.bInheritHandle = 1;
              v8 = CreateFileW(L"nul", 0x80u, 1u, &SecurityAttributes, 3u, 0, 0);
              v4 = (__int64)v8;
              if ( v8 != (HANDLE)-1LL )
              {
                StartupInfo.dwFlags = 256;
                StartupInfo.hStdInput = v8;
                StartupInfo.hStdOutput = v8;
                StartupInfo.hStdError = v8;
              }
              if ( !CreateProcessW(Buffer, CommandLine, 0, 0, 1, 0, 0, 0, &StartupInfo, &ProcessInformation)
                || WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF) == -1
                || !GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
              {
                goto LABEL_2;
              }
              if ( ExitCode )
                LastWin32Error = -2147467259;
            }
          }
        }
      }
    }
  }
LABEL_19:
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  if ( v4 != -1 )
    CloseHandle((HANDLE)v4);
  CSetupLogging::Log(LastWin32Error, "InstallMOF", 0, "Installing WMI file:", a2);
  return LastWin32Error;
}

```

## disassembly

```asm
0x18003a78c  mov     [rsp-8+arg_0], rbx
0x18003a791  mov     [rsp-8+arg_10], rsi
0x18003a796  push    rbp
0x18003a797  push    rdi
0x18003a798  push    r12
0x18003a79a  push    r14
0x18003a79c  push    r15
0x18003a79e  lea     rbp, [rsp-830h]
0x18003a7a6  sub     rsp, 930h
0x18003a7ad  mov     rax, cs:__security_cookie
0x18003a7b4  xor     rax, rsp
0x18003a7b7  mov     [rbp+850h+var_30], rax
0x18003a7be  mov     r14, rdx
0x18003a7c1  mov     qword ptr [rsp+950h+dwCreationDisposition], rdx; unsigned __int16 *
0x18003a7c6  mov     esi, ecx
0x18003a7c8  lea     r9, aInstallingWmiF; "Installing WMI file:"
0x18003a7cf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003a7d3  lea     rdx, aInstallmof; "InstallMOF"
0x18003a7da  xor     r8d, r8d; unsigned int
0x18003a7dd  lea     ecx, [rdi+2]; int
0x18003a7e0  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003a7e5  xor     edx, edx; Val
0x18003a7e7  lea     r8d, [rdi+65h]; Size
0x18003a7eb  lea     rcx, [rbp+850h+StartupInfo+4]; void *
0x18003a7ef  call    memset_0
0x18003a7f4  xorps   xmm0, xmm0
0x18003a7f7  mov     [rbp+850h+StartupInfo.cb], 68h ; 'h'
0x18003a7fe  xor     eax, eax
0x18003a800  lea     rcx, [rbp+850h+Buffer]; lpBuffer
0x18003a807  xor     r15d, r15d
0x18003a80a  mov     qword ptr [rsp+950h+ProcessInformation.dwProcessId], rax
0x18003a80f  mov     edx, 105h; uSize
0x18003a814  mov     [rbp+850h+CommandLine], r15w
0x18003a819  movups  xmmword ptr [rsp+950h+ProcessInformation.hProcess], xmm0
0x18003a81e  mov     [rbp+850h+Buffer], r15w
0x18003a826  call    cs:__imp_GetWindowsDirectoryW
0x18003a82c  test    eax, eax
0x18003a82e  jnz     short loc_18003A83C
0x18003a830  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003a835  mov     ebx, eax
0x18003a837  jmp     loc_18003A9EB
0x18003a83c  mov     r12d, 208h
0x18003a842  lea     r8, SubBlock; "\\"
0x18003a849  mov     edx, r12d; unsigned __int64
0x18003a84c  lea     rcx, [rbp+850h+Buffer]; unsigned __int16 *
0x18003a853  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003a858  mov     ebx, eax
0x18003a85a  test    eax, eax
0x18003a85c  jnz     loc_18003A9EB
0x18003a862  lea     r8, aSystem32WbemMo; "system32\\wbem\\mofcomp.exe"
0x18003a869  mov     edx, r12d; unsigned __int64
0x18003a86c  lea     rcx, [rbp+850h+Buffer]; unsigned __int16 *
0x18003a873  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003a878  mov     ebx, eax
0x18003a87a  test    eax, eax
0x18003a87c  jnz     loc_18003A9EB
0x18003a882  lea     r8, aMofcomp; "mofcomp "
0x18003a889  mov     edx, r12d; unsigned __int64
0x18003a88c  lea     rcx, [rbp+850h+CommandLine]; unsigned __int16 *
0x18003a890  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003a895  mov     ebx, eax
0x18003a897  test    eax, eax
0x18003a899  jnz     loc_18003A9EB
0x18003a89f  test    esi, esi
0x18003a8a1  jnz     short loc_18003A8EF
0x18003a8a3  call    IsWow64
0x18003a8a8  test    eax, eax
0x18003a8aa  lea     rcx, ?s_wszInstallDirectory@Names@@0PAGA; ushort near * Names::s_wszInstallDirectory
0x18003a8b1  lea     r8, ?s_wszInstallDirectory64@Names@@0PAGA; ushort near * Names::s_wszInstallDirectory64
0x18003a8b8  mov     edx, r12d; unsigned __int64
0x18003a8bb  cmovz   r8, rcx; unsigned __int16 *
0x18003a8bf  lea     rcx, [rbp+850h+CommandLine]; unsigned __int16 *
0x18003a8c3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003a8c8  mov     ebx, eax
0x18003a8ca  test    eax, eax
0x18003a8cc  jnz     loc_18003A9EB
0x18003a8d2  lea     r8, SubBlock; "\\"
0x18003a8d9  mov     edx, r12d; unsigned __int64
0x18003a8dc  lea     rcx, [rbp+850h+CommandLine]; unsigned __int16 *
0x18003a8e0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003a8e5  mov     ebx, eax
0x18003a8e7  test    eax, eax
0x18003a8e9  jnz     loc_18003A9EB
0x18003a8ef  mov     r8, r14; unsigned __int16 *
0x18003a8f2  lea     rcx, [rbp+850h+CommandLine]; unsigned __int16 *
0x18003a8f6  mov     rdx, r12; unsigned __int64
0x18003a8f9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003a8fe  mov     ebx, eax
0x18003a900  test    eax, eax
0x18003a902  jnz     loc_18003A9EB
0x18003a908  mov     [rsp+950h+hTemplateFile], r15; hTemplateFile
0x18003a90d  lea     r9, [rsp+950h+SecurityAttributes]; lpSecurityAttributes
0x18003a912  mov     [rsp+950h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18003a917  lea     r8d, [rax+1]; dwShareMode
0x18003a91b  mov     edx, 80h; dwDesiredAccess
0x18003a920  mov     [rsp+950h+dwCreationDisposition], 3; dwCreationDisposition
0x18003a928  lea     rcx, aNul; "nul"
0x18003a92f  mov     [rsp+950h+SecurityAttributes.nLength], 18h
0x18003a937  mov     [rsp+950h+SecurityAttributes.lpSecurityDescriptor], r15
0x18003a93c  mov     [rbp+850h+SecurityAttributes.bInheritHandle], 1
0x18003a943  call    cs:__imp_CreateFileW
0x18003a949  mov     rdi, rax
0x18003a94c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003a950  jz      short loc_18003A965
0x18003a952  mov     [rbp+850h+StartupInfo.dwFlags], 100h
0x18003a959  mov     [rbp+850h+StartupInfo.hStdInput], rax
0x18003a95d  mov     [rbp+850h+StartupInfo.hStdOutput], rax
0x18003a961  mov     [rbp+850h+StartupInfo.hStdError], rax
0x18003a965  lea     rax, [rsp+950h+ProcessInformation]
0x18003a96a  xor     r9d, r9d; lpThreadAttributes
0x18003a96d  mov     [rsp+950h+lpProcessInformation], rax; lpProcessInformation
0x18003a972  lea     rdx, [rbp+850h+CommandLine]; lpCommandLine
0x18003a976  lea     rax, [rbp+850h+StartupInfo]
0x18003a97a  xor     r8d, r8d; lpProcessAttributes
0x18003a97d  mov     [rsp+950h+lpStartupInfo], rax; lpStartupInfo
0x18003a982  lea     rcx, [rbp+850h+Buffer]; lpApplicationName
0x18003a989  mov     [rsp+950h+lpCurrentDirectory], r15; lpCurrentDirectory
0x18003a98e  mov     [rsp+950h+hTemplateFile], r15; lpEnvironment
0x18003a993  mov     [rsp+950h+dwFlagsAndAttributes], r15d; dwCreationFlags
0x18003a998  mov     [rsp+950h+dwCreationDisposition], 1; bInheritHandles
0x18003a9a0  call    cs:__imp_CreateProcessW
0x18003a9a6  test    eax, eax
0x18003a9a8  jz      loc_18003A830
0x18003a9ae  mov     rcx, [rsp+950h+ProcessInformation.hProcess]; hHandle
0x18003a9b3  or      esi, 0FFFFFFFFh
0x18003a9b6  mov     edx, esi; dwMilliseconds
0x18003a9b8  call    cs:__imp_WaitForSingleObject
0x18003a9be  cmp     eax, esi
0x18003a9c0  jz      loc_18003A830
0x18003a9c6  mov     rcx, [rsp+950h+ProcessInformation.hProcess]; hProcess
0x18003a9cb  lea     rdx, [rsp+950h+ExitCode]; lpExitCode
0x18003a9d0  call    cs:__imp_GetExitCodeProcess
0x18003a9d6  test    eax, eax
0x18003a9d8  jz      loc_18003A830
0x18003a9de  cmp     [rsp+950h+ExitCode], r15d
0x18003a9e3  mov     eax, 80004005h
0x18003a9e8  cmovnz  ebx, eax
0x18003a9eb  mov     rcx, [rsp+950h+ProcessInformation.hThread]; hObject
0x18003a9f0  test    rcx, rcx
0x18003a9f3  jz      short loc_18003A9FB
0x18003a9f5  call    cs:__imp_CloseHandle
0x18003a9fb  mov     rcx, [rsp+950h+ProcessInformation.hProcess]; hObject
0x18003aa00  test    rcx, rcx
0x18003aa03  jz      short loc_18003AA0B
0x18003aa05  call    cs:__imp_CloseHandle
0x18003aa0b  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18003aa0f  jz      short loc_18003AA1A
0x18003aa11  mov     rcx, rdi; hObject
0x18003aa14  call    cs:__imp_CloseHandle
0x18003aa1a  lea     r9, aInstallingWmiF; "Installing WMI file:"
0x18003aa21  mov     qword ptr [rsp+950h+dwCreationDisposition], r14; unsigned __int16 *
0x18003aa26  xor     r8d, r8d; unsigned int
0x18003aa29  lea     rdx, aInstallmof; "InstallMOF"
0x18003aa30  mov     ecx, ebx; int
0x18003aa32  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003aa37  mov     eax, ebx
0x18003aa39  mov     rcx, [rbp+850h+var_30]
0x18003aa40  xor     rcx, rsp; StackCookie
0x18003aa43  call    __security_check_cookie
0x18003aa48  lea     r11, [rsp+950h+var_20]
0x18003aa50  mov     rbx, [r11+30h]
0x18003aa54  mov     rsi, [r11+40h]
0x18003aa58  mov     rsp, r11
0x18003aa5b  pop     r15
0x18003aa5d  pop     r14
0x18003aa5f  pop     r12
0x18003aa61  pop     rdi
0x18003aa62  pop     rbp
0x18003aa63  retn
```
