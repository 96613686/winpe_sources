# InitializeSvcHostLib

- ea: `0x140001970`
- end: `0x140001bb1`
- name: `InitializeSvcHostLib`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140002cb0`

## callees

- `0x140001970`
- `0x140001bc0`
- `0x140001c60`
- `0x140004a30`
- `0x140004f90`
- `0x140005922`
- `0x140006320`
- `0x140006520`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001ada`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140008de8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001ada`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140008de8`
- `api-ms-win-core-processthreads-l1-1-0!SetProcessAffinityUpdateMode` at `0x140008dfc`
- `api-ms-win-core-processthreads-l1-1-0!SetProcessAffinityUpdateMode` at `0x140008dfc`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140001b74`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140001b74`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1400019d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1400019d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1400019e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1400019e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140001b32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140001ba0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140001b32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140001ba0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400019f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400019f0`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140001a1f`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140001a32`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140001a1f`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140001a32`
- `api-ms-win-core-registry-l1-1-0!RegDisablePredefinedCacheEx` at `0x140001a3e`
- `api-ms-win-core-registry-l1-1-0!RegDisablePredefinedCacheEx` at `0x140001a3e`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140001a79`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140001a79`
- `ntdll!NtSetInformationProcess` at `0x1400019c0`
- `ntdll!NtSetInformationProcess` at `0x140001af9`
- `ntdll!NtSetInformationProcess` at `0x1400019c0`
- `ntdll!NtSetInformationProcess` at `0x140001af9`
- `ntdll!EtwEventRegister` at `0x140001a5d`
- `ntdll!EtwEventRegister` at `0x140001a5d`

## pseudocode

```c
__int64 InitializeSvcHostLib()
{
  __int64 v0; // rdi
  LPWSTR CommandLineW; // rax
  _QWORD *v2; // rbx
  __int64 v3; // rax
  __int64 v4; // r9
  HANDLE v5; // rax
  __int64 v6; // rcx
  void *v7; // r8
  HANDLE CurrentProcess; // rax
  int ProcessInformation[4]; // [rsp+30h] [rbp-B8h] BYREF
  _BYTE v11[12]; // [rsp+40h] [rbp-A8h] BYREF
  int v12; // [rsp+4Ch] [rbp-9Ch]
  wchar_t pszDest[64]; // [rsp+50h] [rbp-98h] BYREF

  memset_0(v11, 0, 0x90u);
  ProcessInformation[0] = 1;
  NtSetInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessCycleTime|ProcessUserModeIOPL, ProcessInformation, 4u);
  SetUnhandledExceptionFilter(SvchostUnhandledExceptionFilter);
  SetErrorMode(1u);
  g_hHeap = GetProcessHeap();
  qword_14000F3B8 = (__int64)&DllList;
  DllList = (__int64)&DllList;
  InitializeSRWLock(&ListLock);
  InitializeSRWLock(&g_pSvchostSharedGlobalsLock);
  RegDisablePredefinedCacheEx();
  EtwEventRegister(&MS_Services_Svchost_Provider, 0, 0, &PerfRegHandle);
  if ( (MEMORY[0x7FFE02F0] & 0x20) != 0 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !SetProcessAffinityUpdateMode(CurrentProcess, 1u) )
      goto LABEL_11;
  }
  v0 = 0;
  CommandLineW = GetCommandLineW();
  v2 = (_QWORD *)BuildCommandOptions(CommandLineW);
  if ( v2 )
  {
    memset_0(v11, 0, 0x90u);
    v12 = 1;
    v3 = v2[4];
    v4 = v2[3];
    if ( v3 )
      StringCchPrintfW(pszDest, 0x40u, L"[%ws] [%ws]", v4, v3);
    else
      StringCchPrintfW(pszDest, 0x40u, L"[%ws]", v4);
    v5 = GetCurrentProcess();
    NtSetInformationProcess(v5, ProcessPriorityClass|0x40, v11, 0x90u);
    BuildServiceArray(v6, v2);
    v0 = BuildServiceTable();
    if ( v0 && !(unsigned int)CallPerInstanceInitFunctions((__int64)v2) )
LABEL_11:
      ExitProcess(1u);
    v7 = (void *)v2[19];
    if ( v7 )
      HeapFree(g_hHeap, 0, v7);
    HeapFree(g_hHeap, 0, v2);
  }
  return v0;
}

```

## disassembly

```asm
0x140001970  mov     [rsp+arg_0], rbx
0x140001975  push    rdi
0x140001976  sub     rsp, 0E0h
0x14000197d  mov     rax, cs:__security_cookie
0x140001984  xor     rax, rsp
0x140001987  mov     [rsp+0E8h+var_18], rax
0x14000198f  xor     edx, edx; Val
0x140001991  lea     rcx, [rsp+0E8h+var_A8]; void *
0x140001996  mov     r8d, 90h; Size
0x14000199c  call    memset_0
0x1400019a1  mov     r9d, 4; ProcessInformationLength
0x1400019a7  mov     [rsp+0E8h+ProcessInformation], 1
0x1400019af  lea     r8, [rsp+0E8h+ProcessInformation]; ProcessInformation
0x1400019b4  mov     edx, 36h ; '6'; ProcessInformationClass
0x1400019b9  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400019c0  call    cs:__imp_NtSetInformationProcess
0x1400019c7  nop     dword ptr [rax+rax+00h]
0x1400019cc  lea     rcx, SvchostUnhandledExceptionFilter; lpTopLevelExceptionFilter
0x1400019d3  call    cs:__imp_SetUnhandledExceptionFilter
0x1400019da  nop     dword ptr [rax+rax+00h]
0x1400019df  mov     ecx, 1; uMode
0x1400019e4  call    cs:__imp_SetErrorMode
0x1400019eb  nop     dword ptr [rax+rax+00h]
0x1400019f0  call    cs:__imp_GetProcessHeap
0x1400019f7  nop     dword ptr [rax+rax+00h]
0x1400019fc  mov     cs:g_hHeap, rax
0x140001a03  lea     rcx, ListLock; SRWLock
0x140001a0a  lea     rax, DllList
0x140001a11  mov     cs:qword_14000F3B8, rax
0x140001a18  mov     cs:DllList, rax
0x140001a1f  call    cs:__imp_InitializeSRWLock
0x140001a26  nop     dword ptr [rax+rax+00h]
0x140001a2b  lea     rcx, g_pSvchostSharedGlobalsLock; SRWLock
0x140001a32  call    cs:__imp_InitializeSRWLock
0x140001a39  nop     dword ptr [rax+rax+00h]
0x140001a3e  call    cs:__imp_RegDisablePredefinedCacheEx
0x140001a45  nop     dword ptr [rax+rax+00h]
0x140001a4a  lea     r9, PerfRegHandle
0x140001a51  xor     r8d, r8d
0x140001a54  xor     edx, edx
0x140001a56  lea     rcx, MS_Services_Svchost_Provider
0x140001a5d  call    cs:__imp_EtwEventRegister
0x140001a64  nop     dword ptr [rax+rax+00h]
0x140001a69  test    byte ptr ds:7FFE02F0h, 20h
0x140001a71  jnz     loc_140008DE8
0x140001a77  xor     edi, edi
0x140001a79  call    cs:__imp_GetCommandLineW
0x140001a80  nop     dword ptr [rax+rax+00h]
0x140001a85  mov     rcx, rax; Src
0x140001a88  call    BuildCommandOptions
0x140001a8d  mov     rbx, rax
0x140001a90  test    rax, rax
0x140001a93  jz      loc_140001B3E
0x140001a99  xor     edx, edx; Val
0x140001a9b  lea     rcx, [rsp+0E8h+var_A8]; void *
0x140001aa0  mov     r8d, 90h; Size
0x140001aa6  call    memset_0
0x140001aab  mov     [rsp+0E8h+var_9C], 1
0x140001ab3  lea     rcx, [rsp+0E8h+pszDest]; pszDest
0x140001ab8  mov     rax, [rbx+20h]
0x140001abc  mov     edx, 40h ; '@'; cchDest
0x140001ac1  mov     r9, [rbx+18h]
0x140001ac5  test    rax, rax
0x140001ac8  jnz     loc_140001B81
0x140001ace  lea     r8, aWs; "[%ws]"
0x140001ad5  call    StringCchPrintfW
0x140001ada  call    cs:__imp_GetCurrentProcess
0x140001ae1  nop     dword ptr [rax+rax+00h]
0x140001ae6  mov     r9d, 90h; ProcessInformationLength
0x140001aec  lea     r8, [rsp+0E8h+var_A8]; ProcessInformation
0x140001af1  mov     rcx, rax; ProcessHandle
0x140001af4  mov     edx, 52h ; 'R'; ProcessInformationClass
0x140001af9  call    cs:__imp_NtSetInformationProcess
0x140001b00  nop     dword ptr [rax+rax+00h]
0x140001b05  mov     rdx, rbx
0x140001b08  call    BuildServiceArray
0x140001b0d  call    BuildServiceTable
0x140001b12  mov     rdi, rax
0x140001b15  test    rax, rax
0x140001b18  jnz     short loc_140001B63
0x140001b1a  mov     r8, [rbx+98h]; lpMem
0x140001b21  test    r8, r8
0x140001b24  jnz     short loc_140001B97
0x140001b26  mov     rcx, cs:g_hHeap; hHeap
0x140001b2d  mov     r8, rbx; lpMem
0x140001b30  xor     edx, edx; dwFlags
0x140001b32  call    cs:__imp_HeapFree
0x140001b39  nop     dword ptr [rax+rax+00h]
0x140001b3e  mov     rax, rdi
0x140001b41  mov     rcx, [rsp+0E8h+var_18]
0x140001b49  xor     rcx, rsp; StackCookie
0x140001b4c  call    __security_check_cookie
0x140001b51  mov     rbx, [rsp+0E8h+arg_0]
0x140001b59  add     rsp, 0E0h
0x140001b60  pop     rdi
0x140001b61  retn
0x140001b63  mov     rcx, rbx
0x140001b66  call    CallPerInstanceInitFunctions
0x140001b6b  test    eax, eax
0x140001b6d  jnz     short loc_140001B1A
0x140001b6f  mov     ecx, 1; uExitCode
0x140001b74  call    cs:__imp_ExitProcess
0x140001b81  lea     r8, aWsWs; "[%ws] [%ws]"
0x140001b88  mov     [rsp+0E8h+var_C8], rax
0x140001b8d  call    StringCchPrintfW
0x140001b92  jmp     loc_140001ADA
0x140001b97  mov     rcx, cs:g_hHeap; hHeap
0x140001b9e  xor     edx, edx; dwFlags
0x140001ba0  call    cs:__imp_HeapFree
0x140001ba7  nop     dword ptr [rax+rax+00h]
0x140001bac  jmp     loc_140001B26
0x140008de8  call    cs:__imp_GetCurrentProcess
0x140008def  nop     dword ptr [rax+rax+00h]
0x140008df4  mov     rcx, rax; hProcess
0x140008df7  mov     edx, 1; dwFlags
0x140008dfc  call    cs:__imp_SetProcessAffinityUpdateMode
0x140008e03  nop     dword ptr [rax+rax+00h]
0x140008e08  test    eax, eax
0x140008e0a  jz      loc_140001B6F
0x140008e10  jmp     loc_140001A77
```
