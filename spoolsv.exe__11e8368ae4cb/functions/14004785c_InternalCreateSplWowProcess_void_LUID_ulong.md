# InternalCreateSplWowProcess(void *,_LUID &,ulong)

- ea: `0x14004785c`
- end: `0x140047ad1`
- name: `?InternalCreateSplWowProcess@@YAJPEAXAEAU_LUID@@K@Z`
- size: `629`
- prototype: `__int64 __fastcall(HANDLE hToken, struct _LUID *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400473bc`

## callees

- `0x140007bdc`
- `0x1400160a0`
- `0x1400163ec`
- `0x14002abc0`
- `0x14002b810`
- `0x14002f030`
- `0x14004785c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140047a56`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140047a56`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400478f6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400478f6`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1400478dc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1400478dc`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x140047a16`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x140047a16`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x140047a95`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x140047a95`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140047a75`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140047a75`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140047a8f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140047a8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047a25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047a30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047aa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047a25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047a30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047aa3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x140047943`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x140047943`
- `USERENV!CreateEnvironmentBlock` at `0x1400479b5`
- `USERENV!CreateEnvironmentBlock` at `0x1400479b5`
- `USERENV!DestroyEnvironmentBlock` at `0x140047a44`
- `USERENV!DestroyEnvironmentBlock` at `0x140047a44`

## string_xrefs

- `0x1400478c8`: `InternalCreateSplWowProcess`
- `0x140047a69`: `InternalCreateSplWowProcess`

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
0x14004785c  push    rbp
0x14004785e  push    rbx
0x14004785f  push    rsi
0x140047860  push    rdi
0x140047861  push    r14
0x140047863  lea     rbp, [rsp-8B0h]
0x14004786b  sub     rsp, 9B0h
0x140047872  mov     rax, cs:__security_cookie
0x140047879  xor     rax, rsp
0x14004787c  mov     [rbp+8D0h+var_30], rax
0x140047883  mov     eax, [rdx+4]
0x140047886  mov     esi, r8d
0x140047889  mov     r9d, [rdx]
0x14004788c  lea     r8, aLocalWinspl64t; "Local\\WinSpl64To32Mutex_%x_%x_%x"
0x140047893  mov     r14, rcx
0x140047896  mov     [rsp+9D0h+bInheritHandles], 2000h
0x14004789e  mov     edx, 3Ch ; '<'; unsigned __int64
0x1400478a3  mov     dword ptr [rsp+9D0h+lpThreadAttributes], eax
0x1400478a7  lea     rcx, [rbp+8D0h+Name]; unsigned __int16 *
0x1400478ab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400478b0  mov     ebx, eax
0x1400478b2  test    eax, eax
0x1400478b4  js      loc_140047AB2
0x1400478ba  mov     r9d, esi
0x1400478bd  lea     r8, [rbp+8D0h+Name]
0x1400478c1  lea     rdx, aMutexnameWsInt; "MutexName %ws. Integrity %u"
0x1400478c8  lea     rcx, aInternalcreate; "InternalCreateSplWowProcess"
0x1400478cf  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400478d4  lea     r8, [rbp+8D0h+Name]; lpName
0x1400478d8  xor     edx, edx; bInitialOwner
0x1400478da  xor     ecx, ecx; lpMutexAttributes
0x1400478dc  call    cs:__imp_CreateMutexW
0x1400478e2  mov     rdi, rax
0x1400478e5  test    rax, rax
0x1400478e8  jz      loc_140047AAB
0x1400478ee  mov     edx, 2710h; dwMilliseconds
0x1400478f3  mov     rcx, rax; hHandle
0x1400478f6  call    cs:__imp_WaitForSingleObject
0x1400478fc  test    eax, eax
0x1400478fe  jnz     loc_140047A5E
0x140047904  xor     edx, edx; Val
0x140047906  lea     r8d, [rax+64h]; Size
0x14004790a  lea     rcx, [rbp+8D0h+StartupInfo+4]; void *
0x14004790e  call    memset_0
0x140047913  xorps   xmm0, xmm0
0x140047916  mov     [rbp+8D0h+StartupInfo.cb], 68h ; 'h'
0x14004791d  xor     eax, eax
0x14004791f  lea     rcx, [rbp+8D0h+Buffer]; void *
0x140047923  xor     edx, edx; Val
0x140047925  mov     qword ptr [rsp+9D0h+ProcessInformation.dwProcessId], rax
0x14004792a  mov     r8d, 20Ah; Size
0x140047930  movups  xmmword ptr [rsp+9D0h+ProcessInformation.hProcess], xmm0
0x140047935  call    memset_0
0x14004793a  mov     edx, 104h; uSize
0x14004793f  lea     rcx, [rbp+8D0h+Buffer]; lpBuffer
0x140047943  call    cs:__imp_GetSystemWindowsDirectoryW
0x140047949  test    eax, eax
0x14004794b  jz      loc_140047A4C
0x140047951  lea     r9, [rbp+8D0h+Buffer]
0x140047955  mov     edx, 105h; unsigned __int64
0x14004795a  lea     r8, aWsSplwow64Exe; "%ws\\splwow64.exe"
0x140047961  lea     rcx, [rbp+8D0h+ApplicationName]; unsigned __int16 *
0x140047968  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14004796d  mov     ebx, eax
0x14004796f  test    eax, eax
0x140047971  js      loc_140047A53
0x140047977  lea     r9, [rbp+8D0h+Buffer]
0x14004797b  mov     dword ptr [rsp+9D0h+lpThreadAttributes], esi
0x14004797f  lea     r8, aWsSplwow64ExeD; "%ws\\splwow64.exe %d"
0x140047986  mov     edx, 208h; unsigned __int64
0x14004798b  lea     rcx, [rbp+8D0h+CommandLine]; unsigned __int16 *
0x140047992  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140047997  mov     ebx, eax
0x140047999  test    eax, eax
0x14004799b  js      loc_140047A53
0x1400479a1  xor     r8d, r8d; bInherit
0x1400479a4  mov     [rsp+9D0h+Environment], 0
0x1400479ad  mov     rdx, r14; hToken
0x1400479b0  lea     rcx, [rsp+9D0h+Environment]; lpEnvironment
0x1400479b5  call    cs:__imp_CreateEnvironmentBlock
0x1400479bb  test    eax, eax
0x1400479bd  jz      loc_140047A4C
0x1400479c3  lea     rax, [rsp+9D0h+ProcessInformation]
0x1400479c8  xor     r9d, r9d; lpProcessAttributes
0x1400479cb  mov     [rsp+9D0h+lpProcessInformation], rax; lpProcessInformation
0x1400479d0  lea     r8, [rbp+8D0h+CommandLine]; lpCommandLine
0x1400479d7  lea     rax, [rbp+8D0h+StartupInfo]
0x1400479db  mov     rcx, r14; hToken
0x1400479de  mov     [rsp+9D0h+lpStartupInfo], rax; lpStartupInfo
0x1400479e3  lea     rdx, [rbp+8D0h+ApplicationName]; lpApplicationName
0x1400479ea  lea     rax, [rbp+8D0h+Buffer]
0x1400479ee  mov     [rsp+9D0h+lpCurrentDirectory], rax; lpCurrentDirectory
0x1400479f3  mov     rax, [rsp+9D0h+Environment]
0x1400479f8  mov     [rsp+9D0h+lpEnvironment], rax; lpEnvironment
0x1400479fd  mov     [rsp+9D0h+dwCreationFlags], 0C000408h; dwCreationFlags
0x140047a05  mov     [rsp+9D0h+bInheritHandles], 0; bInheritHandles
0x140047a0d  mov     [rsp+9D0h+lpThreadAttributes], 0; lpThreadAttributes
0x140047a16  call    cs:__imp_CreateProcessAsUserW
0x140047a1c  test    eax, eax
0x140047a1e  jz      short loc_140047A38
0x140047a20  mov     rcx, [rsp+9D0h+ProcessInformation.hThread]; hObject
0x140047a25  call    cs:__imp_CloseHandle
0x140047a2b  mov     rcx, [rsp+9D0h+ProcessInformation.hProcess]; hObject
0x140047a30  call    cs:__imp_CloseHandle
0x140047a36  jmp     short loc_140047A3F
0x140047a38  call    GetLastErrorAsHResult
0x140047a3d  mov     ebx, eax
0x140047a3f  mov     rcx, [rsp+9D0h+Environment]; lpEnvironment
0x140047a44  call    cs:__imp_DestroyEnvironmentBlock
0x140047a4a  jmp     short loc_140047A53
0x140047a4c  call    GetLastErrorAsHResult
0x140047a51  mov     ebx, eax
0x140047a53  mov     rcx, rdi; hMutex
0x140047a56  call    cs:__imp_ReleaseMutex
0x140047a5c  jmp     short loc_140047AA0
0x140047a5e  lea     r8, [rbp+8D0h+Name]
0x140047a62  lea     rdx, aCouldNotAcquir; "Could not acquire mutex %ws in 10 secon"...
0x140047a69  lea     rcx, aInternalcreate; "InternalCreateSplWowProcess"
0x140047a70  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140047a75  call    cs:__imp_IsDebuggerPresent
0x140047a7b  test    eax, eax
0x140047a7d  jnz     short loc_140047A88
0x140047a7f  cmp     ds:7FFE02D4h, al
0x140047a86  jz      short loc_140047A9B
0x140047a88  lea     rcx, OutputString; "Mutex could not be acquired within 10 s"...
0x140047a8f  call    cs:__imp_OutputDebugStringW
0x140047a95  call    cs:__imp_DebugBreak
0x140047a9b  mov     ebx, 80004005h
0x140047aa0  mov     rcx, rdi; hObject
0x140047aa3  call    cs:__imp_CloseHandle
0x140047aa9  jmp     short loc_140047AB2
0x140047aab  call    GetLastErrorAsHResult
0x140047ab0  mov     ebx, eax
0x140047ab2  mov     eax, ebx
0x140047ab4  mov     rcx, [rbp+8D0h+var_30]
0x140047abb  xor     rcx, rsp; StackCookie
0x140047abe  call    __security_check_cookie
0x140047ac3  add     rsp, 9B0h
0x140047aca  pop     r14
0x140047acc  pop     rdi
0x140047acd  pop     rsi
0x140047ace  pop     rbx
0x140047acf  pop     rbp
0x140047ad0  retn
```
