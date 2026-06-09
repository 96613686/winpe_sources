# DeviceListManager::InitializeWSDChallenge(void)

- ea: `0x18001e888`
- end: `0x18001e9bd`
- name: `?InitializeWSDChallenge@DeviceListManager@@QEAAXXZ`
- size: `309`
- prototype: `void __fastcall(DeviceListManager *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000e080`
- `0x18001e660`
- `0x18002a448`

## callees

- `0x18000ac34`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18001e888`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001e962`
- `KERNEL32!LeaveCriticalSection` at `0x18001e962`
- `KERNEL32!GetLastError` at `0x18001e973`
- `KERNEL32!GetLastError` at `0x18001e9a1`
- `KERNEL32!GetLastError` at `0x18001e973`
- `KERNEL32!GetLastError` at `0x18001e9a1`
- `KERNEL32!CloseHandle` at `0x18001e8ec`
- `KERNEL32!CloseHandle` at `0x18001e8ec`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001e8da`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001e8da`

## string_xrefs

- `0x18001e8f7`: `WSD Challenge successfully initiated (thread: %u)`
- `0x18001e930`: `WSD Challenge successfully initiated (thread: %u)`
- `0x18001e97b`: `CreateThread failed (GLE: 0x%X). The DeviceListManager failed to initialize the WSD Challenge.`
- `0x18001e9a9`: `CreateThread failed (GLE: 0x%X). The DeviceListManager failed to initialize the WSD Challenge.`

## pseudocode

```c
void __fastcall DeviceListManager::InitializeWSDChallenge(DeviceListManager *this)
{
  int v1; // edi
  HANDLE Thread; // rax
  char *v3; // rbx
  void *v4; // rdx
  void **v5; // rax
  void *v6; // rdx
  __int64 v7; // rcx
  int v8; // r9d
  char *v9; // rbx
  void *v10; // rdx
  DWORD LastError; // eax
  DeviceListManager *ThreadId; // [rsp+40h] [rbp+8h] BYREF

  ThreadId = this;
  v1 = CRIT_SECT::Lock((CRIT_SECT *)&DeviceListManager::m_csInitWSDChallenge);
  if ( !DeviceListManager::m_bWSDChallengeInitialized )
  {
    LODWORD(ThreadId) = 0;
    Thread = CreateThread(
               0,
               0,
               (LPTHREAD_START_ROUTINE)DeviceListManager::ChallengeInitThread,
               0,
               0,
               (LPDWORD)&ThreadId);
    if ( Thread )
    {
      CloseHandle(Thread);
      DeviceListManager::m_bWSDChallengeInitialized = 1;
      v3 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                     0,
                     0,
                     "WSD Challenge successfully initiated (thread: %u)",
                     (_DWORD)ThreadId);
      WriteDbgTraceInfoWI("DeviceListManager::InitializeWSDChallenge", v3);
      WiaTrcLib::Free((WiaTrcLib *)v3, v4);
      v5 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                      0,
                      0,
                      "WSD Challenge successfully initiated (thread: %u)",
                      (_DWORD)ThreadId);
      v8 = 4;
    }
    else
    {
      GetLastError();
      v9 = (char *)WiaTrace_TraceLog("CreateThread failed (GLE: 0x%X). The DeviceListManager failed to initialize the WSD Challenge.");
      WriteDbgTraceErrorWI("DeviceListManager::InitializeWSDChallenge", v9);
      WiaTrcLib::Free((WiaTrcLib *)v9, v10);
      LastError = GetLastError();
      v5 = (void **)WiaTrace_Trace(
                      "CreateThread failed (GLE: 0x%X). The DeviceListManager failed to initialize the WSD Challenge.",
                      LastError);
      v8 = 1;
    }
    WiaTrace_ProcessTrace_Ex(v7, v6, (void *)"DeviceListManager::InitializeWSDChallenge", v8, v5);
  }
  if ( v1 )
    LeaveCriticalSection(&DeviceListManager::m_csInitWSDChallenge);
}

```

## disassembly

```asm
0x18001e888  mov     [rsp+arg_8], rbx
0x18001e88d  mov     [rsp+ThreadId], rcx
0x18001e892  push    rdi
0x18001e893  sub     rsp, 30h
0x18001e897  lea     rcx, ?m_csInitWSDChallenge@DeviceListManager@@0VCRIT_SECT@@A; this
0x18001e89e  call    ?Lock@CRIT_SECT@@QEAAHXZ; CRIT_SECT::Lock(void)
0x18001e8a3  cmp     cs:?m_bWSDChallengeInitialized@DeviceListManager@@0HA, 0; int DeviceListManager::m_bWSDChallengeInitialized
0x18001e8aa  mov     edi, eax
0x18001e8ac  jnz     loc_18001E957
0x18001e8b2  lea     rax, [rsp+38h+ThreadId]
0x18001e8b7  mov     dword ptr [rsp+38h+ThreadId], 0
0x18001e8bf  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18001e8c4  lea     r8, ?ChallengeInitThread@DeviceListManager@@CAKPEAX@Z; lpStartAddress
0x18001e8cb  xor     r9d, r9d; lpParameter
0x18001e8ce  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18001e8d6  xor     edx, edx; dwStackSize
0x18001e8d8  xor     ecx, ecx; lpThreadAttributes
0x18001e8da  call    cs:__imp_CreateThread
0x18001e8e0  test    rax, rax
0x18001e8e3  jz      loc_18001E973
0x18001e8e9  mov     rcx, rax; hObject
0x18001e8ec  call    cs:__imp_CloseHandle
0x18001e8f2  mov     r9d, dword ptr [rsp+38h+ThreadId]
0x18001e8f7  lea     r8, aWsdChallengeSu; "WSD Challenge successfully initiated (t"...
0x18001e8fe  xor     edx, edx
0x18001e900  mov     cs:?m_bWSDChallengeInitialized@DeviceListManager@@0HA, 1; int DeviceListManager::m_bWSDChallengeInitialized
0x18001e90a  xor     ecx, ecx
0x18001e90c  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18001e911  mov     rdx, rax; char *
0x18001e914  lea     rcx, aDevicelistmana_9; "DeviceListManager::InitializeWSDChallen"...
0x18001e91b  mov     rbx, rax
0x18001e91e  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18001e923  mov     rcx, rbx; this
0x18001e926  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001e92b  mov     r9d, dword ptr [rsp+38h+ThreadId]
0x18001e930  lea     r8, aWsdChallengeSu; "WSD Challenge successfully initiated (t"...
0x18001e937  xor     edx, edx
0x18001e939  xor     ecx, ecx
0x18001e93b  call    WiaTrace_TraceWithSubCompTraceLevel
0x18001e940  mov     r9d, 4; int
0x18001e946  lea     r8, aDevicelistmana_9; "DeviceListManager::InitializeWSDChallen"...
0x18001e94d  mov     qword ptr [rsp+38h+dwCreationFlags], rax; lpMem
0x18001e952  call    WiaTrace_ProcessTrace_Ex
0x18001e957  test    edi, edi
0x18001e959  jz      short loc_18001E968
0x18001e95b  lea     rcx, ?m_csInitWSDChallenge@DeviceListManager@@0VCRIT_SECT@@A; lpCriticalSection
0x18001e962  call    cs:__imp_LeaveCriticalSection
0x18001e968  mov     rbx, [rsp+38h+arg_8]
0x18001e96d  add     rsp, 30h
0x18001e971  pop     rdi
0x18001e972  retn
0x18001e973  call    cs:__imp_GetLastError
0x18001e979  mov     edx, eax
0x18001e97b  lea     rcx, aCreatethreadFa; "CreateThread failed (GLE: 0x%X). The De"...
0x18001e982  call    WiaTrace_TraceLog
0x18001e987  mov     rdx, rax; char *
0x18001e98a  lea     rcx, aDevicelistmana_9; "DeviceListManager::InitializeWSDChallen"...
0x18001e991  mov     rbx, rax
0x18001e994  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001e999  mov     rcx, rbx; this
0x18001e99c  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001e9a1  call    cs:__imp_GetLastError
0x18001e9a7  mov     edx, eax
0x18001e9a9  lea     rcx, aCreatethreadFa; "CreateThread failed (GLE: 0x%X). The De"...
0x18001e9b0  call    WiaTrace_Trace
0x18001e9b5  mov     r9d, 1
0x18001e9bb  jmp     short loc_18001E946
```
