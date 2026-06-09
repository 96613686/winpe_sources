# InternalCreateSplWowProcess(void *,_LUID &,ulong)

- ea: `0x14004bbd0`
- end: `0x14004be94`
- name: `?InternalCreateSplWowProcess@@YAJPEAXAEAU_LUID@@K@Z`
- size: `708`
- prototype: `__int64 __fastcall(HANDLE hToken, struct _LUID *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14004b6c4`

## callees

- `0x1400087c8`
- `0x14001748c`
- `0x1400177c4`
- `0x14002d0a0`
- `0x14002dd20`
- `0x140031720`
- `0x14004bbd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14004bdfa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14004bdfa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14004bc70`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14004bc70`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14004bc50`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14004bc50`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x14004bda2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x14004bda2`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x14004be4b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x14004be4b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14004be1f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14004be1f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14004be3f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14004be3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004bdb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004bdc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004be5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004bdb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004bdc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004be5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x14004bcc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x14004bcc3`
- `USERENV!CreateEnvironmentBlock` at `0x14004bd3b`
- `USERENV!CreateEnvironmentBlock` at `0x14004bd3b`
- `USERENV!DestroyEnvironmentBlock` at `0x14004bde2`
- `USERENV!DestroyEnvironmentBlock` at `0x14004bde2`

## string_xrefs

- `0x14004bc3c`: `InternalCreateSplWowProcess`
- `0x14004be13`: `InternalCreateSplWowProcess`

## pseudocode

```c
__int64 __fastcall InternalCreateSplWowProcess(HANDLE hToken, struct _LUID *a2, unsigned int a3)
{
  int LastErrorAsHResult; // ebx
  HANDLE MutexW; // rax
  void *v7; // rdi
  LPSECURITY_ATTRIBUTES lpThreadAttributes; // [rsp+20h] [rbp-E0h]
  LPVOID Environment; // [rsp+60h] [rbp-A0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-98h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Name[64]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR Buffer[264]; // [rsp+170h] [rbp+70h] BYREF
  WCHAR ApplicationName[264]; // [rsp+380h] [rbp+280h] BYREF
  WCHAR CommandLine[520]; // [rsp+590h] [rbp+490h] BYREF

  LastErrorAsHResult = StringCchPrintfW(
                         Name,
                         0x3Cu,
                         L"Local\\WinSpl64To32Mutex_%x_%x_%x",
                         a2->LowPart,
                         a2->HighPart,
                         0x2000);
  if ( LastErrorAsHResult >= 0 )
  {
    SpoolerServiceTelemetry::WriteDbgTraceInfo("InternalCreateSplWowProcess", L"MutexName %ws. Integrity %u", Name, a3);
    MutexW = CreateMutexW(0, 0, Name);
    v7 = MutexW;
    if ( !MutexW )
      return (unsigned int)GetLastErrorAsHResult();
    if ( WaitForSingleObject(MutexW, 0x2710u) )
    {
      SpoolerServiceTelemetry::WriteDbgTraceError(
        "InternalCreateSplWowProcess",
        L"Could not acquire mutex %ws in 10 seconds",
        Name);
      if ( IsDebuggerPresent() || MEMORY[0x7FFE02D4] )
      {
        OutputDebugStringW(L"Mutex could not be acquired within 10 seconds\n");
        DebugBreak();
      }
      LastErrorAsHResult = -2147467259;
      goto LABEL_18;
    }
    memset_0(&StartupInfo.cb + 1, 0, 0x64u);
    StartupInfo.cb = 104;
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    memset_0(Buffer, 0, 0x20Au);
    if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) )
    {
      LastErrorAsHResult = StringCchPrintfW(ApplicationName, 0x105u, L"%ws\\splwow64.exe", Buffer);
      if ( LastErrorAsHResult < 0 )
        goto LABEL_13;
      LODWORD(lpThreadAttributes) = a3;
      LastErrorAsHResult = StringCchPrintfW(CommandLine, 0x208u, L"%ws\\splwow64.exe %d", Buffer, lpThreadAttributes);
      if ( LastErrorAsHResult < 0 )
        goto LABEL_13;
      Environment = 0;
      if ( CreateEnvironmentBlock(&Environment, hToken, 0) )
      {
        if ( CreateProcessAsUserW(
               hToken,
               ApplicationName,
               CommandLine,
               0,
               0,
               0,
               0xC000408u,
               Environment,
               Buffer,
               &StartupInfo,
               &ProcessInformation) )
        {
          CloseHandle(ProcessInformation.hThread);
          CloseHandle(ProcessInformation.hProcess);
        }
        else
        {
          LastErrorAsHResult = GetLastErrorAsHResult();
        }
        DestroyEnvironmentBlock(Environment);
        goto LABEL_13;
      }
    }
    LastErrorAsHResult = GetLastErrorAsHResult();
LABEL_13:
    ReleaseMutex(v7);
LABEL_18:
    CloseHandle(v7);
  }
  return (unsigned int)LastErrorAsHResult;
}

```

## disassembly

```asm
0x14004bbd0  push    rbp
0x14004bbd2  push    rbx
0x14004bbd3  push    rsi
0x14004bbd4  push    rdi
0x14004bbd5  push    r14
0x14004bbd7  lea     rbp, [rsp-8B0h]
0x14004bbdf  sub     rsp, 9B0h
0x14004bbe6  mov     rax, cs:__security_cookie
0x14004bbed  xor     rax, rsp
0x14004bbf0  mov     [rbp+8D0h+var_30], rax
0x14004bbf7  mov     eax, [rdx+4]
0x14004bbfa  mov     esi, r8d
0x14004bbfd  mov     r9d, [rdx]
0x14004bc00  lea     r8, aLocalWinspl64t; "Local\\WinSpl64To32Mutex_%x_%x_%x"
0x14004bc07  mov     r14, rcx
0x14004bc0a  mov     [rsp+9D0h+bInheritHandles], 2000h
0x14004bc12  mov     edx, 3Ch ; '<'; unsigned __int64
0x14004bc17  mov     dword ptr [rsp+9D0h+lpThreadAttributes], eax
0x14004bc1b  lea     rcx, [rbp+8D0h+Name]; unsigned __int16 *
0x14004bc1f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14004bc24  mov     ebx, eax
0x14004bc26  test    eax, eax
0x14004bc28  js      loc_14004BE74
0x14004bc2e  mov     r9d, esi
0x14004bc31  lea     r8, [rbp+8D0h+Name]
0x14004bc35  lea     rdx, aMutexnameWsInt; "MutexName %ws. Integrity %u"
0x14004bc3c  lea     rcx, aInternalcreate; "InternalCreateSplWowProcess"
0x14004bc43  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14004bc48  lea     r8, [rbp+8D0h+Name]; lpName
0x14004bc4c  xor     edx, edx; bInitialOwner
0x14004bc4e  xor     ecx, ecx; lpMutexAttributes
0x14004bc50  call    cs:__imp_CreateMutexW
0x14004bc57  nop     dword ptr [rax+rax+00h]
0x14004bc5c  mov     rdi, rax
0x14004bc5f  test    rax, rax
0x14004bc62  jz      loc_14004BE6D
0x14004bc68  mov     edx, 2710h; dwMilliseconds
0x14004bc6d  mov     rcx, rax; hHandle
0x14004bc70  call    cs:__imp_WaitForSingleObject
0x14004bc77  nop     dword ptr [rax+rax+00h]
0x14004bc7c  test    eax, eax
0x14004bc7e  jnz     loc_14004BE08
0x14004bc84  xor     edx, edx; Val
0x14004bc86  lea     r8d, [rax+64h]; Size
0x14004bc8a  lea     rcx, [rbp+8D0h+StartupInfo+4]; void *
0x14004bc8e  call    memset_0
0x14004bc93  xorps   xmm0, xmm0
0x14004bc96  mov     [rbp+8D0h+StartupInfo.cb], 68h ; 'h'
0x14004bc9d  xor     eax, eax
0x14004bc9f  lea     rcx, [rbp+8D0h+Buffer]; void *
0x14004bca3  xor     edx, edx; Val
0x14004bca5  mov     qword ptr [rsp+9D0h+ProcessInformation.dwProcessId], rax
0x14004bcaa  mov     r8d, 20Ah; Size
0x14004bcb0  movups  xmmword ptr [rsp+9D0h+ProcessInformation.hProcess], xmm0
0x14004bcb5  call    memset_0
0x14004bcba  mov     edx, 104h; uSize
0x14004bcbf  lea     rcx, [rbp+8D0h+Buffer]; lpBuffer
0x14004bcc3  call    cs:__imp_GetSystemWindowsDirectoryW
0x14004bcca  nop     dword ptr [rax+rax+00h]
0x14004bccf  test    eax, eax
0x14004bcd1  jz      loc_14004BDF0
0x14004bcd7  lea     r9, [rbp+8D0h+Buffer]
0x14004bcdb  mov     edx, 105h; unsigned __int64
0x14004bce0  lea     r8, aWsSplwow64Exe; "%ws\\splwow64.exe"
0x14004bce7  lea     rcx, [rbp+8D0h+ApplicationName]; unsigned __int16 *
0x14004bcee  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14004bcf3  mov     ebx, eax
0x14004bcf5  test    eax, eax
0x14004bcf7  js      loc_14004BDF7
0x14004bcfd  lea     r9, [rbp+8D0h+Buffer]
0x14004bd01  mov     dword ptr [rsp+9D0h+lpThreadAttributes], esi
0x14004bd05  lea     r8, aWsSplwow64ExeD; "%ws\\splwow64.exe %d"
0x14004bd0c  mov     edx, 208h; unsigned __int64
0x14004bd11  lea     rcx, [rbp+8D0h+CommandLine]; unsigned __int16 *
0x14004bd18  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14004bd1d  mov     ebx, eax
0x14004bd1f  test    eax, eax
0x14004bd21  js      loc_14004BDF7
0x14004bd27  xor     r8d, r8d; bInherit
0x14004bd2a  mov     [rsp+9D0h+Environment], 0
0x14004bd33  mov     rdx, r14; hToken
0x14004bd36  lea     rcx, [rsp+9D0h+Environment]; lpEnvironment
0x14004bd3b  call    cs:__imp_CreateEnvironmentBlock
0x14004bd42  nop     dword ptr [rax+rax+00h]
0x14004bd47  test    eax, eax
0x14004bd49  jz      loc_14004BDF0
0x14004bd4f  lea     rax, [rsp+9D0h+ProcessInformation]
0x14004bd54  xor     r9d, r9d; lpProcessAttributes
0x14004bd57  mov     [rsp+9D0h+lpProcessInformation], rax; lpProcessInformation
0x14004bd5c  lea     r8, [rbp+8D0h+CommandLine]; lpCommandLine
0x14004bd63  lea     rax, [rbp+8D0h+StartupInfo]
0x14004bd67  mov     rcx, r14; hToken
0x14004bd6a  mov     [rsp+9D0h+lpStartupInfo], rax; lpStartupInfo
0x14004bd6f  lea     rdx, [rbp+8D0h+ApplicationName]; lpApplicationName
0x14004bd76  lea     rax, [rbp+8D0h+Buffer]
0x14004bd7a  mov     [rsp+9D0h+lpCurrentDirectory], rax; lpCurrentDirectory
0x14004bd7f  mov     rax, [rsp+9D0h+Environment]
0x14004bd84  mov     [rsp+9D0h+lpEnvironment], rax; lpEnvironment
0x14004bd89  mov     [rsp+9D0h+dwCreationFlags], 0C000408h; dwCreationFlags
0x14004bd91  mov     [rsp+9D0h+bInheritHandles], 0; bInheritHandles
0x14004bd99  mov     [rsp+9D0h+lpThreadAttributes], 0; lpThreadAttributes
0x14004bda2  call    cs:__imp_CreateProcessAsUserW
0x14004bda9  nop     dword ptr [rax+rax+00h]
0x14004bdae  test    eax, eax
0x14004bdb0  jz      short loc_14004BDD6
0x14004bdb2  mov     rcx, [rsp+9D0h+ProcessInformation.hThread]; hObject
0x14004bdb7  call    cs:__imp_CloseHandle
0x14004bdbe  nop     dword ptr [rax+rax+00h]
0x14004bdc3  mov     rcx, [rsp+9D0h+ProcessInformation.hProcess]; hObject
0x14004bdc8  call    cs:__imp_CloseHandle
0x14004bdcf  nop     dword ptr [rax+rax+00h]
0x14004bdd4  jmp     short loc_14004BDDD
0x14004bdd6  call    GetLastErrorAsHResult
0x14004bddb  mov     ebx, eax
0x14004bddd  mov     rcx, [rsp+9D0h+Environment]; lpEnvironment
0x14004bde2  call    cs:__imp_DestroyEnvironmentBlock
0x14004bde9  nop     dword ptr [rax+rax+00h]
0x14004bdee  jmp     short loc_14004BDF7
0x14004bdf0  call    GetLastErrorAsHResult
0x14004bdf5  mov     ebx, eax
0x14004bdf7  mov     rcx, rdi; hMutex
0x14004bdfa  call    cs:__imp_ReleaseMutex
0x14004be01  nop     dword ptr [rax+rax+00h]
0x14004be06  jmp     short loc_14004BE5C
0x14004be08  lea     r8, [rbp+8D0h+Name]
0x14004be0c  lea     rdx, aCouldNotAcquir; "Could not acquire mutex %ws in 10 secon"...
0x14004be13  lea     rcx, aInternalcreate; "InternalCreateSplWowProcess"
0x14004be1a  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004be1f  call    cs:__imp_IsDebuggerPresent
0x14004be26  nop     dword ptr [rax+rax+00h]
0x14004be2b  test    eax, eax
0x14004be2d  jnz     short loc_14004BE38
0x14004be2f  cmp     ds:7FFE02D4h, al
0x14004be36  jz      short loc_14004BE57
0x14004be38  lea     rcx, OutputString; "Mutex could not be acquired within 10 s"...
0x14004be3f  call    cs:__imp_OutputDebugStringW
0x14004be46  nop     dword ptr [rax+rax+00h]
0x14004be4b  call    cs:__imp_DebugBreak
0x14004be52  nop     dword ptr [rax+rax+00h]
0x14004be57  mov     ebx, 80004005h
0x14004be5c  mov     rcx, rdi; hObject
0x14004be5f  call    cs:__imp_CloseHandle
0x14004be66  nop     dword ptr [rax+rax+00h]
0x14004be6b  jmp     short loc_14004BE74
0x14004be6d  call    GetLastErrorAsHResult
0x14004be72  mov     ebx, eax
0x14004be74  mov     eax, ebx
0x14004be76  mov     rcx, [rbp+8D0h+var_30]
0x14004be7d  xor     rcx, rsp; StackCookie
0x14004be80  call    __security_check_cookie
0x14004be85  add     rsp, 9B0h
0x14004be8c  pop     r14
0x14004be8e  pop     rdi
0x14004be8f  pop     rsi
0x14004be90  pop     rbx
0x14004be91  pop     rbp
0x14004be92  retn
```
