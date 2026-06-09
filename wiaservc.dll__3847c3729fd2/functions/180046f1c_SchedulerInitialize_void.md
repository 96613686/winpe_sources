# SchedulerInitialize(void)

- ea: `0x180046f1c`
- end: `0x18004704d`
- name: `?SchedulerInitialize@@YAHXZ`
- size: `305`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003b438`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18002c868`
- `0x18002c8b0`
- `0x180046f1c`
- `0x1800471ac`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180046f44`
- `KERNEL32!CreateEventW` at `0x180046f44`
- `KERNEL32!CloseHandle` at `0x180046fa0`
- `KERNEL32!CloseHandle` at `0x180046fa0`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180046fdb`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180046fdb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180046f87`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180046f87`

## pseudocode

```c
__int64 SchedulerInitialize(void)
{
  char *v1; // rbx
  void *v2; // rdx
  void **v3; // rax
  void *v4; // rdx
  __int64 v5; // rcx
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  ThreadId = 0;
  if ( g_fSchedulerInitialized )
    return 1;
  g_hSchedulerEvent = CreateEventW(0, 0, 0, 0);
  if ( g_hSchedulerEvent )
  {
    qword_1800B14C0 = (__int64)&g_ScheduleListHead;
    g_ScheduleListHead = (SCHED_ITEM *)&g_ScheduleListHead;
    g_hSchedulerThread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)SchedulerThread, 0, 0, &ThreadId);
    if ( g_hSchedulerThread )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2>::GetImpl'::`2'::impl) )
        g_schedulerThreadId = GetThreadId(g_hSchedulerThread);
      g_fSchedulerInitialized = 1;
      v1 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0x80000000LL, 0, "Work item scheduler initialized");
      WriteDbgTraceInfoWI("SchedulerInitialize", v1);
      WiaTrcLib::Free((WiaTrcLib *)v1, v2);
      v3 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0x80000000LL, 0, "Work item scheduler initialized");
      WiaTrace_ProcessTrace_Ex(v5, v4, (void *)"SchedulerInitialize", 4, v3);
      return 1;
    }
    CloseHandle(g_hSchedulerEvent);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2>::GetImpl'::`2'::impl) )
      g_schedulerThreadId = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180046f1c  push    rbx
0x180046f1e  sub     rsp, 30h
0x180046f22  xor     ebx, ebx
0x180046f24  cmp     cs:?g_fSchedulerInitialized@@3HA, ebx; int g_fSchedulerInitialized
0x180046f2a  mov     [rsp+38h+ThreadId], ebx
0x180046f2e  jz      short loc_180046F3A
0x180046f30  mov     eax, 1
0x180046f35  jmp     loc_180046FBE
0x180046f3a  xor     r9d, r9d; lpName
0x180046f3d  xor     r8d, r8d; bInitialState
0x180046f40  xor     edx, edx; bManualReset
0x180046f42  xor     ecx, ecx; lpEventAttributes
0x180046f44  call    cs:__imp_CreateEventW
0x180046f4a  mov     cs:?g_hSchedulerEvent@@3PEAXEA, rax; void * g_hSchedulerEvent
0x180046f51  test    rax, rax
0x180046f54  jz      short loc_180046FBC
0x180046f56  lea     rax, ?g_ScheduleListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ScheduleListHead
0x180046f5d  xor     r9d, r9d; lpParameter
0x180046f60  mov     cs:qword_1800B14C0, rax
0x180046f67  lea     r8, ?SchedulerThread@@YAKPEAK@Z; lpStartAddress
0x180046f6e  mov     cs:?g_ScheduleListHead@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_ScheduleListHead
0x180046f75  xor     edx, edx; dwStackSize
0x180046f77  lea     rax, [rsp+38h+ThreadId]
0x180046f7c  xor     ecx, ecx; lpThreadAttributes
0x180046f7e  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180046f83  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x180046f87  call    cs:__imp_CreateThread
0x180046f8d  mov     cs:?g_hSchedulerThread@@3PEAXEA, rax; void * g_hSchedulerThread
0x180046f94  test    rax, rax
0x180046f97  jnz     short loc_180046FC4
0x180046f99  mov     rcx, cs:?g_hSchedulerEvent@@3PEAXEA; hObject
0x180046fa0  call    cs:__imp_CloseHandle
0x180046fa6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2>::GetImpl(void)'::`2'::impl
0x180046fad  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2>::__private_IsEnabled(void)
0x180046fb2  test    al, al
0x180046fb4  jz      short loc_180046FBC
0x180046fb6  mov     cs:?g_schedulerThreadId@@3KA, ebx; ulong g_schedulerThreadId
0x180046fbc  xor     eax, eax
0x180046fbe  add     rsp, 30h
0x180046fc2  pop     rbx
0x180046fc3  retn
0x180046fc4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2>::GetImpl(void)'::`2'::impl
0x180046fcb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2>::__private_IsEnabled(void)
0x180046fd0  test    al, al
0x180046fd2  jz      short loc_180046FE7
0x180046fd4  mov     rcx, cs:?g_hSchedulerThread@@3PEAXEA; Thread
0x180046fdb  call    cs:__imp_GetThreadId
0x180046fe1  mov     cs:?g_schedulerThreadId@@3KA, eax; ulong g_schedulerThreadId
0x180046fe7  lea     r8, aWorkItemSchedu; "Work item scheduler initialized"
0x180046fee  mov     cs:?g_fSchedulerInitialized@@3HA, 1; int g_fSchedulerInitialized
0x180046ff8  xor     edx, edx
0x180046ffa  mov     ecx, 80000000h
0x180046fff  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180047004  mov     rdx, rax; char *
0x180047007  lea     rcx, aScheduleriniti; "SchedulerInitialize"
0x18004700e  mov     rbx, rax
0x180047011  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180047016  mov     rcx, rbx; this
0x180047019  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004701e  lea     r8, aWorkItemSchedu; "Work item scheduler initialized"
0x180047025  xor     edx, edx
0x180047027  mov     ecx, 80000000h
0x18004702c  call    WiaTrace_TraceWithSubCompTraceLevel
0x180047031  mov     r9d, 4; int
0x180047037  mov     qword ptr [rsp+38h+dwCreationFlags], rax; lpMem
0x18004703c  lea     r8, aScheduleriniti; "SchedulerInitialize"
0x180047043  call    WiaTrace_ProcessTrace_Ex
0x180047048  jmp     loc_180046F30
```
