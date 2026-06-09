# InitializeSvcHostLib

- ea: `0x1400018d0`
- end: `0x140001ab9`
- name: `InitializeSvcHostLib`
- size: `489`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140002a40`

## callees

- `0x1400018d0`
- `0x140001ac0`
- `0x140001b50`
- `0x140004680`
- `0x140004bd0`
- `0x140005542`
- `0x140005ea0`
- `0x140006080`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001a04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000876e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001a04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000876e`
- `api-ms-win-core-processthreads-l1-1-0!SetProcessAffinityUpdateMode` at `0x14000877c`
- `api-ms-win-core-processthreads-l1-1-0!SetProcessAffinityUpdateMode` at `0x14000877c`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140001a8b`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140001a8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x14000192d`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x14000192d`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x140001938`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x140001938`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140001a50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140001ab1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140001a50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140001ab1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000193e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000193e`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140001967`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140001974`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140001967`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140001974`
- `api-ms-win-core-registry-l1-1-0!RegDisablePredefinedCacheEx` at `0x14000197a`
- `api-ms-win-core-registry-l1-1-0!RegDisablePredefinedCacheEx` at `0x14000197a`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1400019a9`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1400019a9`
- `ntdll!NtSetInformationProcess` at `0x140001920`
- `ntdll!NtSetInformationProcess` at `0x140001a1d`
- `ntdll!NtSetInformationProcess` at `0x140001920`
- `ntdll!NtSetInformationProcess` at `0x140001a1d`
- `ntdll!EtwEventRegister` at `0x140001993`
- `ntdll!EtwEventRegister` at `0x140001993`

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
  EtwEventRegister(MS_Services_Svchost_Provider, 0, 0, &PerfRegHandle);
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
0x1400018d0  mov     [rsp+arg_0], rbx
0x1400018d5  push    rdi
0x1400018d6  sub     rsp, 0E0h
0x1400018dd  mov     rax, cs:__security_cookie
0x1400018e4  xor     rax, rsp
0x1400018e7  mov     [rsp+0E8h+var_18], rax
0x1400018ef  xor     edx, edx; Val
0x1400018f1  lea     rcx, [rsp+0E8h+var_A8]; void *
0x1400018f6  mov     r8d, 90h; Size
0x1400018fc  call    memset_0
0x140001901  mov     r9d, 4; ProcessInformationLength
0x140001907  mov     [rsp+0E8h+ProcessInformation], 1
0x14000190f  lea     r8, [rsp+0E8h+ProcessInformation]; ProcessInformation
0x140001914  mov     edx, 36h ; '6'; ProcessInformationClass
0x140001919  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140001920  call    cs:__imp_NtSetInformationProcess
0x140001926  lea     rcx, SvchostUnhandledExceptionFilter; lpTopLevelExceptionFilter
0x14000192d  call    cs:__imp_SetUnhandledExceptionFilter
0x140001933  mov     ecx, 1; uMode
0x140001938  call    cs:__imp_SetErrorMode
0x14000193e  call    cs:__imp_GetProcessHeap
0x140001944  mov     cs:g_hHeap, rax
0x14000194b  lea     rcx, ListLock; SRWLock
0x140001952  lea     rax, DllList
0x140001959  mov     cs:qword_14000F3B8, rax
0x140001960  mov     cs:DllList, rax
0x140001967  call    cs:__imp_InitializeSRWLock
0x14000196d  lea     rcx, g_pSvchostSharedGlobalsLock; SRWLock
0x140001974  call    cs:__imp_InitializeSRWLock
0x14000197a  call    cs:__imp_RegDisablePredefinedCacheEx
0x140001980  lea     r9, PerfRegHandle
0x140001987  xor     r8d, r8d
0x14000198a  xor     edx, edx
0x14000198c  lea     rcx, MS_Services_Svchost_Provider
0x140001993  call    cs:__imp_EtwEventRegister
0x140001999  test    byte ptr ds:7FFE02F0h, 20h
0x1400019a1  jnz     loc_14000876E
0x1400019a7  xor     edi, edi
0x1400019a9  call    cs:__imp_GetCommandLineW
0x1400019af  mov     rcx, rax; Src
0x1400019b2  call    BuildCommandOptions
0x1400019b7  mov     rbx, rax
0x1400019ba  test    rax, rax
0x1400019bd  jz      loc_140001A56
0x1400019c3  xor     edx, edx; Val
0x1400019c5  lea     rcx, [rsp+0E8h+var_A8]; void *
0x1400019ca  mov     r8d, 90h; Size
0x1400019d0  call    memset_0
0x1400019d5  mov     [rsp+0E8h+var_9C], 1
0x1400019dd  lea     rcx, [rsp+0E8h+pszDest]; pszDest
0x1400019e2  mov     rax, [rbx+20h]
0x1400019e6  mov     edx, 40h ; '@'; cchDest
0x1400019eb  mov     r9, [rbx+18h]
0x1400019ef  test    rax, rax
0x1400019f2  jnz     loc_140001A92
0x1400019f8  lea     r8, aWs; "[%ws]"
0x1400019ff  call    StringCchPrintfW
0x140001a04  call    cs:__imp_GetCurrentProcess
0x140001a0a  mov     r9d, 90h; ProcessInformationLength
0x140001a10  lea     r8, [rsp+0E8h+var_A8]; ProcessInformation
0x140001a15  mov     rcx, rax; ProcessHandle
0x140001a18  mov     edx, 52h ; 'R'; ProcessInformationClass
0x140001a1d  call    cs:__imp_NtSetInformationProcess
0x140001a23  mov     rdx, rbx
0x140001a26  call    BuildServiceArray
0x140001a2b  call    BuildServiceTable
0x140001a30  mov     rdi, rax
0x140001a33  test    rax, rax
0x140001a36  jnz     short loc_140001A7A
0x140001a38  mov     r8, [rbx+98h]; lpMem
0x140001a3f  test    r8, r8
0x140001a42  jnz     short loc_140001AA8
0x140001a44  mov     rcx, cs:g_hHeap; hHeap
0x140001a4b  mov     r8, rbx; lpMem
0x140001a4e  xor     edx, edx; dwFlags
0x140001a50  call    cs:__imp_HeapFree
0x140001a56  mov     rax, rdi
0x140001a59  mov     rcx, [rsp+0E8h+var_18]
0x140001a61  xor     rcx, rsp; StackCookie
0x140001a64  call    __security_check_cookie
0x140001a69  mov     rbx, [rsp+0E8h+arg_0]
0x140001a71  add     rsp, 0E0h
0x140001a78  pop     rdi
0x140001a79  retn
0x140001a7a  mov     rcx, rbx
0x140001a7d  call    CallPerInstanceInitFunctions
0x140001a82  test    eax, eax
0x140001a84  jnz     short loc_140001A38
0x140001a86  mov     ecx, 1; uExitCode
0x140001a8b  call    cs:__imp_ExitProcess
0x140001a92  lea     r8, aWsWs; "[%ws] [%ws]"
0x140001a99  mov     [rsp+0E8h+var_C8], rax
0x140001a9e  call    StringCchPrintfW
0x140001aa3  jmp     loc_140001A04
0x140001aa8  mov     rcx, cs:g_hHeap; hHeap
0x140001aaf  xor     edx, edx; dwFlags
0x140001ab1  call    cs:__imp_HeapFree
0x140001ab7  jmp     short loc_140001A44
0x14000876e  call    cs:__imp_GetCurrentProcess
0x140008774  mov     rcx, rax; hProcess
0x140008777  mov     edx, 1; dwFlags
0x14000877c  call    cs:__imp_SetProcessAffinityUpdateMode
0x140008782  test    eax, eax
0x140008784  jz      loc_140001A86
0x14000878a  jmp     loc_1400019A7
```
