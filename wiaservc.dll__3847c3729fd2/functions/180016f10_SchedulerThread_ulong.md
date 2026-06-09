# SchedulerThread(ulong *)

- ea: `0x180016f10`
- end: `0x180017357`
- name: `?SchedulerThread@@YAKPEAK@Z`
- size: `1095`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x180016f10`
- `0x180017360`
- `0x18002c868`
- `0x18002c8b0`
- `0x180034658`
- `0x180078010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180016fa5`
- `KERNEL32!EnterCriticalSection` at `0x18001707b`
- `KERNEL32!EnterCriticalSection` at `0x18001719a`
- `KERNEL32!EnterCriticalSection` at `0x180017291`
- `KERNEL32!EnterCriticalSection` at `0x180016fa5`
- `KERNEL32!EnterCriticalSection` at `0x18001707b`
- `KERNEL32!EnterCriticalSection` at `0x18001719a`
- `KERNEL32!EnterCriticalSection` at `0x180017291`
- `KERNEL32!GetModuleHandleExW` at `0x180016f66`
- `KERNEL32!GetModuleHandleExW` at `0x180016f66`
- `KERNEL32!LeaveCriticalSection` at `0x180016fbe`
- `KERNEL32!LeaveCriticalSection` at `0x1800170d0`
- `KERNEL32!LeaveCriticalSection` at `0x18001717a`
- `KERNEL32!LeaveCriticalSection` at `0x180017226`
- `KERNEL32!LeaveCriticalSection` at `0x1800172a3`
- `KERNEL32!LeaveCriticalSection` at `0x180016fbe`
- `KERNEL32!LeaveCriticalSection` at `0x1800170d0`
- `KERNEL32!LeaveCriticalSection` at `0x18001717a`
- `KERNEL32!LeaveCriticalSection` at `0x180017226`
- `KERNEL32!LeaveCriticalSection` at `0x1800172a3`
- `KERNEL32!GetTickCount` at `0x1800171b3`
- `KERNEL32!GetTickCount` at `0x180017279`
- `KERNEL32!GetTickCount` at `0x1800171b3`
- `KERNEL32!GetTickCount` at `0x180017279`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180016fdf`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180016fdf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180017187`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180017187`

## string_xrefs

- `0x180017004`: `SchedulerThread`
- `0x180017039`: `SchedulerThread`
- `0x180017135`: `SchedulerThread`
- `0x18001716b`: `SchedulerThread`
- `0x1800172ed`: `SchedulerThread`
- `0x18001731e`: `SchedulerThread`
- `0x180016ff1`: `SchedulerThread after calling WaitForMultipleObjects dwErr = 0x%08X`
- `0x18001701e`: `SchedulerThread after calling WaitForMultipleObjects dwErr = 0x%08X`
- `0x180017120`: `SchedulerThread: Item 0x%x has an invalid signature`
- `0x18001714e`: `SchedulerThread: Item 0x%x has an invalid signature`
- `0x1800172db`: `SchedulerThread: Reached max scheduled items!`
- `0x180017306`: `SchedulerThread: Reached max scheduled items!`

## pseudocode

```c
void __fastcall __noreturn SchedulerThread(PVOID Parameter)
{
  SCHED_ITEM *v1; // rsi
  DWORD v2; // ebp
  DWORD v3; // r14d
  SCHED_ITEM *i; // rdi
  DWORD v5; // eax
  __int64 v6; // rdi
  char *v7; // rbx
  void *v8; // rdx
  void **lpMem; // rax
  void *v10; // rdx
  __int64 v11; // rcx
  SCHED_ITEM *v12; // rcx
  int v13; // ebx
  SCHED_ITEM *v14; // rdx
  SCHED_ITEM **v15; // rax
  __int64 v16; // rcx
  unsigned int v17; // edx
  char *v18; // rbx
  void *v19; // rdx
  void **v20; // rax
  void *v21; // rdx
  __int64 v22; // rcx
  DWORD TickCount; // eax
  DWORD v24; // edi
  SCHED_ITEM *v25; // rbx
  DWORD v26; // ecx
  __int64 v27; // rcx
  _QWORD *v28; // rax
  __int64 v29; // rcx
  unsigned int v30; // edx
  void *v31; // rcx
  __int64 v32; // rax
  char *v33; // rbx
  void *v34; // rdx
  void **v35; // rax
  void *v36; // rdx
  __int64 v37; // rcx
  HMODULE phModule; // [rsp+30h] [rbp-268h] BYREF
  HANDLE Handles[64]; // [rsp+40h] [rbp-258h] BYREF

  v1 = 0;
  v2 = -1;
  memset_0(Handles, 0, sizeof(Handles));
  phModule = 0;
  GetModuleHandleExW(4u, (LPCWSTR)SchedulerThread, &phModule);
  while ( 1 )
  {
    while ( 1 )
    {
LABEL_2:
      if ( g_fSchedShutdown )
        goto LABEL_29;
      v3 = 1;
      Handles[0] = g_hSchedulerEvent;
      if ( dword_1800B1590 )
        EnterCriticalSection(&g_SchedulerLock);
      for ( i = g_ScheduleListHead; ; i = *(SCHED_ITEM **)i )
      {
        if ( i == (SCHED_ITEM *)&g_ScheduleListHead )
          goto LABEL_7;
        if ( *((_DWORD *)i + 4) != 1396918369 )
        {
          v18 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                          2,
                          0,
                          "SchedulerThread: Item 0x%x has an invalid signature",
                          (_DWORD)i);
          WriteDbgTraceInfoWI("SchedulerThread", v18);
          WiaTrcLib::Free((WiaTrcLib *)v18, v19);
          v20 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                           2,
                           0,
                           "SchedulerThread: Item 0x%x has an invalid signature",
                           (_DWORD)i);
          WiaTrace_ProcessTrace_Ex(v22, v21, (void *)"SchedulerThread", 4, v20);
          LeaveCriticalSection(&g_SchedulerLock);
LABEL_29:
          FreeLibraryAndExitThread(phModule, 0);
        }
        v1 = i;
        if ( !*((_DWORD *)i + 16) )
        {
          v31 = (void *)*((_QWORD *)i + 7);
          if ( v31 )
          {
            v32 = v3++;
            Handles[v32] = v31;
            if ( v3 == 64 )
              break;
          }
        }
      }
      v33 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(2, 0, "SchedulerThread: Reached max scheduled items!");
      WriteDbgTraceInfoWI("SchedulerThread", v33);
      WiaTrcLib::Free((WiaTrcLib *)v33, v34);
      v35 = (void **)WiaTrace_TraceWithSubCompTraceLevel(2, 0, "SchedulerThread: Reached max scheduled items!");
      WiaTrace_ProcessTrace_Ex(v37, v36, (void *)"SchedulerThread", 4, v35);
LABEL_7:
      LeaveCriticalSection(&g_SchedulerLock);
      if ( g_fSchedShutdown )
        goto LABEL_29;
      v5 = WaitForMultipleObjects(v3, Handles, 0, v2);
      v6 = v5;
      if ( v5 != 258 )
      {
        v7 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                       0,
                       0,
                       "SchedulerThread after calling WaitForMultipleObjects dwErr = 0x%08X",
                       v5);
        WriteDbgTraceInfoWI("SchedulerThread", v7);
        WiaTrcLib::Free((WiaTrcLib *)v7, v8);
        lpMem = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                           0,
                           0,
                           "SchedulerThread after calling WaitForMultipleObjects dwErr = 0x%08X",
                           v6);
        WiaTrace_ProcessTrace_Ex(v11, v10, (void *)"SchedulerThread", 4, lpMem);
      }
      if ( g_fSchedShutdown )
        goto LABEL_29;
      if ( !(_DWORD)v6 )
        break;
      if ( (_DWORD)v6 == 258 )
        goto LABEL_45;
      if ( (unsigned int)v6 >= v3 )
        break;
      if ( dword_1800B1590 )
        EnterCriticalSection(&g_SchedulerLock);
      v12 = g_ScheduleListHead;
      v13 = 0;
      while ( 1 )
      {
        if ( v12 == (SCHED_ITEM *)&g_ScheduleListHead )
          goto LABEL_21;
        v1 = v12;
        v14 = *(SCHED_ITEM **)v12;
        if ( Handles[v6] == *((HANDLE *)v12 + 7) )
          break;
        v12 = *(SCHED_ITEM **)v12;
      }
      v15 = (SCHED_ITEM **)*((_QWORD *)v12 + 1);
      v13 = 1;
      *v15 = v14;
      *((_QWORD *)v14 + 1) = v15;
      *(_QWORD *)v12 = 0;
      v16 = *((_QWORD *)v12 + 4);
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
LABEL_21:
      LeaveCriticalSection(&g_SchedulerLock);
      if ( v13 )
      {
        if ( *((_QWORD *)v1 + 4) )
        {
          if ( !*((_DWORD *)v1 + 16) )
            (*((void (**)(void))v1 + 3))();
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 4) + 16LL))(*((_QWORD *)v1 + 4));
        }
        SCHED_ITEM::`scalar deleting destructor'(v1, v17);
        v1 = 0;
      }
    }
    if ( dword_1800B1590 )
      EnterCriticalSection(&g_SchedulerLock);
    if ( g_ScheduleListHead == (SCHED_ITEM *)&g_ScheduleListHead )
    {
      v2 = -1;
    }
    else
    {
      v1 = g_ScheduleListHead;
      TickCount = GetTickCount();
      v24 = TickCount;
      if ( TickCount < *((_DWORD *)v1 + 10) )
      {
        v2 = *((_DWORD *)v1 + 10) - TickCount;
      }
      else
      {
        while ( 1 )
        {
          v25 = g_ScheduleListHead;
          if ( g_ScheduleListHead == (SCHED_ITEM *)&g_ScheduleListHead )
          {
            v2 = -1;
            goto LABEL_50;
          }
          v26 = *((_DWORD *)g_ScheduleListHead + 10);
          v1 = g_ScheduleListHead;
          if ( v24 < v26 || ((*((_QWORD *)g_ScheduleListHead + 7) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
            break;
          v27 = *(_QWORD *)g_ScheduleListHead;
          v28 = (_QWORD *)*((_QWORD *)g_ScheduleListHead + 1);
          *v28 = *(_QWORD *)g_ScheduleListHead;
          *(_QWORD *)(v27 + 8) = v28;
          v29 = *((_QWORD *)v25 + 4);
          *(_QWORD *)v25 = 0;
          if ( v29 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
          LeaveCriticalSection(&g_SchedulerLock);
          if ( *((_QWORD *)v25 + 4) )
          {
            if ( !*((_DWORD *)v25 + 16) )
              (*((void (**)(void))v25 + 3))();
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v25 + 4) + 16LL))(*((_QWORD *)v25 + 4));
          }
          SCHED_ITEM::`scalar deleting destructor'(v25, v30);
          v1 = 0;
LABEL_45:
          if ( g_fSchedShutdown )
            goto LABEL_29;
          if ( g_fSchedulePaused )
            goto LABEL_2;
          v24 = GetTickCount();
          if ( dword_1800B1590 )
            EnterCriticalSection(&g_SchedulerLock);
        }
        v2 = v26 - v24;
      }
    }
LABEL_50:
    LeaveCriticalSection(&g_SchedulerLock);
  }
}

```

## disassembly

```asm
0x180016f10  push    rbx
0x180016f12  push    rbp
0x180016f13  push    rsi
0x180016f14  push    rdi
0x180016f15  push    r12
0x180016f17  push    r13
0x180016f19  push    r14
0x180016f1b  push    r15
0x180016f1d  sub     rsp, 258h
0x180016f24  mov     rax, cs:__security_cookie
0x180016f2b  xor     rax, rsp
0x180016f2e  mov     [rsp+298h+var_58], rax
0x180016f36  xor     r15d, r15d
0x180016f39  lea     rcx, [rsp+298h+Handles]; void *
0x180016f3e  xor     edx, edx; Val
0x180016f40  mov     r8d, 200h; Size
0x180016f46  mov     esi, r15d
0x180016f49  or      ebp, 0FFFFFFFFh
0x180016f4c  call    memset_0
0x180016f51  lea     r8, [rsp+298h+phModule]; phModule
0x180016f56  mov     [rsp+298h+phModule], r15
0x180016f5b  lea     rdx, ?SchedulerThread@@YAKPEAK@Z; lpModuleName
0x180016f62  lea     ecx, [r15+4]; dwFlags
0x180016f66  call    cs:__imp_GetModuleHandleExW
0x180016f6c  lea     r12, ?g_SchedulerLock@@3VCRIT_SECT@@A; CRIT_SECT g_SchedulerLock
0x180016f73  lea     r13, ?g_ScheduleListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ScheduleListHead
0x180016f7a  cmp     cs:?g_fSchedShutdown@@3HA, r15d; int g_fSchedShutdown
0x180016f81  jnz     loc_180017180
0x180016f87  cmp     cs:dword_1800B1590, r15d
0x180016f8e  mov     r14d, 1
0x180016f94  mov     rax, cs:?g_hSchedulerEvent@@3PEAXEA; void * g_hSchedulerEvent
0x180016f9b  mov     [rsp+298h+Handles], rax
0x180016fa0  jz      short loc_180016FAB
0x180016fa2  mov     rcx, r12; lpCriticalSection
0x180016fa5  call    cs:__imp_EnterCriticalSection
0x180016fab  mov     rdi, cs:?g_ScheduleListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ScheduleListHead
0x180016fb2  cmp     rdi, r13
0x180016fb5  jnz     loc_180017111
0x180016fbb  mov     rcx, r12; lpCriticalSection
0x180016fbe  call    cs:__imp_LeaveCriticalSection
0x180016fc4  cmp     cs:?g_fSchedShutdown@@3HA, r15d; int g_fSchedShutdown
0x180016fcb  jnz     loc_180017180
0x180016fd1  mov     r9d, ebp; dwMilliseconds
0x180016fd4  lea     rdx, [rsp+298h+Handles]; lpHandles
0x180016fd9  xor     r8d, r8d; bWaitAll
0x180016fdc  mov     ecx, r14d; nCount
0x180016fdf  call    cs:__imp_WaitForMultipleObjects
0x180016fe5  mov     edi, eax
0x180016fe7  cmp     eax, 102h
0x180016fec  jz      short loc_180017045
0x180016fee  mov     r9d, edi
0x180016ff1  lea     r8, aSchedulerthrea_2; "SchedulerThread after calling WaitForMu"...
0x180016ff8  xor     edx, edx
0x180016ffa  xor     ecx, ecx
0x180016ffc  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180017001  mov     rdx, rax; char *
0x180017004  lea     rcx, aSchedulerthrea; "SchedulerThread"
0x18001700b  mov     rbx, rax
0x18001700e  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180017013  mov     rcx, rbx; this
0x180017016  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001701b  mov     r9d, edi
0x18001701e  lea     r8, aSchedulerthrea_2; "SchedulerThread after calling WaitForMu"...
0x180017025  xor     edx, edx
0x180017027  xor     ecx, ecx
0x180017029  call    WiaTrace_TraceWithSubCompTraceLevel
0x18001702e  mov     r9d, 4; int
0x180017034  mov     [rsp+298h+lpMem], rax; lpMem
0x180017039  lea     r8, aSchedulerthrea; "SchedulerThread"
0x180017040  call    WiaTrace_ProcessTrace_Ex
0x180017045  cmp     cs:?g_fSchedShutdown@@3HA, r15d; int g_fSchedShutdown
0x18001704c  jnz     loc_180017180
0x180017052  test    edi, edi
0x180017054  jz      loc_18001718E
0x18001705a  cmp     edi, 102h
0x180017060  jz      loc_18001725F
0x180017066  cmp     edi, r14d
0x180017069  jnb     loc_18001718E
0x18001706f  cmp     cs:dword_1800B1590, r15d
0x180017076  jz      short loc_180017081
0x180017078  mov     rcx, r12; lpCriticalSection
0x18001707b  call    cs:__imp_EnterCriticalSection
0x180017081  mov     rcx, cs:?g_ScheduleListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ScheduleListHead
0x180017088  mov     ebx, r15d
0x18001708b  cmp     rcx, r13
0x18001708e  jz      short loc_1800170CD
0x180017090  mov     rax, [rcx+38h]
0x180017094  mov     rsi, rcx
0x180017097  mov     rdx, [rcx]
0x18001709a  cmp     [rsp+rdi*8+298h+Handles], rax
0x18001709f  jnz     loc_18001732F
0x1800170a5  mov     rax, [rcx+8]
0x1800170a9  mov     ebx, 1
0x1800170ae  mov     [rax], rdx
0x1800170b1  mov     [rdx+8], rax
0x1800170b5  mov     [rcx], r15
0x1800170b8  mov     rcx, [rcx+20h]
0x1800170bc  test    rcx, rcx
0x1800170bf  jz      short loc_1800170CD
0x1800170c1  mov     rax, [rcx]
0x1800170c4  mov     rax, [rax+8]
0x1800170c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170cd  mov     rcx, r12; lpCriticalSection
0x1800170d0  call    cs:__imp_LeaveCriticalSection
0x1800170d6  test    ebx, ebx
0x1800170d8  jz      loc_180016F7A
0x1800170de  mov     rcx, [rsi+20h]
0x1800170e2  test    rcx, rcx
0x1800170e5  jz      short loc_180017101
0x1800170e7  cmp     [rsi+40h], r15d
0x1800170eb  jz      loc_180017337
0x1800170f1  mov     rcx, [rsi+20h]
0x1800170f5  mov     rax, [rcx]
0x1800170f8  mov     rax, [rax+10h]
0x1800170fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017101  mov     rcx, rsi; this
0x180017104  call    ??_GSCHED_ITEM@@QEAAPEAXI@Z; SCHED_ITEM::`scalar deleting destructor'(uint)
0x180017109  mov     rsi, r15
0x18001710c  jmp     loc_180016F7A
0x180017111  cmp     dword ptr [rdi+10h], 53434861h
0x180017118  jz      loc_1800172AE
0x18001711e  xor     edx, edx
0x180017120  lea     r8, aSchedulerthrea_0; "SchedulerThread: Item 0x%x has an inval"...
0x180017127  mov     r9, rdi
0x18001712a  lea     ecx, [rdx+2]
0x18001712d  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180017132  mov     rdx, rax; char *
0x180017135  lea     rcx, aSchedulerthrea; "SchedulerThread"
0x18001713c  mov     rbx, rax
0x18001713f  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180017144  mov     rcx, rbx; this
0x180017147  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001714c  xor     edx, edx
0x18001714e  lea     r8, aSchedulerthrea_0; "SchedulerThread: Item 0x%x has an inval"...
0x180017155  mov     r9, rdi
0x180017158  lea     ecx, [rdx+2]
0x18001715b  call    WiaTrace_TraceWithSubCompTraceLevel
0x180017160  mov     r9d, 4; int
0x180017166  mov     [rsp+298h+lpMem], rax; lpMem
0x18001716b  lea     r8, aSchedulerthrea; "SchedulerThread"
0x180017172  call    WiaTrace_ProcessTrace_Ex
0x180017177  mov     rcx, r12; lpCriticalSection
0x18001717a  call    cs:__imp_LeaveCriticalSection
0x180017180  mov     rcx, [rsp+298h+phModule]; hLibModule
0x180017185  xor     edx, edx; dwExitCode
0x180017187  call    cs:__imp_FreeLibraryAndExitThread
0x18001718d  int     3; Trap to Debugger
0x18001718e  cmp     cs:dword_1800B1590, r15d
0x180017195  jz      short loc_1800171A0
0x180017197  mov     rcx, r12; lpCriticalSection
0x18001719a  call    cs:__imp_EnterCriticalSection
0x1800171a0  mov     rax, cs:?g_ScheduleListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ScheduleListHead
0x1800171a7  cmp     rax, r13
0x1800171aa  jz      loc_18001734F
0x1800171b0  mov     rsi, rax
0x1800171b3  call    cs:__imp_GetTickCount
0x1800171b9  mov     edi, eax
0x1800171bb  cmp     eax, [rsi+28h]
0x1800171be  jb      loc_180017345
0x1800171c4  mov     rbx, cs:?g_ScheduleListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ScheduleListHead
0x1800171cb  mov     eax, 0FFFFFFFFh
0x1800171d0  cmp     rbx, r13
0x1800171d3  cmovz   ebp, eax
0x1800171d6  jz      loc_1800172A0
0x1800171dc  mov     ecx, [rbx+28h]
0x1800171df  mov     rsi, rbx
0x1800171e2  cmp     edi, ecx
0x1800171e4  jb      loc_18001729C
0x1800171ea  mov     rax, [rbx+38h]
0x1800171ee  inc     rax
0x1800171f1  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800171f7  jnz     loc_18001729C
0x1800171fd  mov     rcx, [rbx]
0x180017200  mov     rax, [rbx+8]
0x180017204  mov     [rax], rcx
0x180017207  mov     [rcx+8], rax
0x18001720b  mov     rcx, [rbx+20h]
0x18001720f  mov     [rbx], r15
0x180017212  test    rcx, rcx
0x180017215  jz      short loc_180017223
0x180017217  mov     rax, [rcx]
0x18001721a  mov     rax, [rax+8]
0x18001721e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017223  mov     rcx, r12; lpCriticalSection
0x180017226  call    cs:__imp_LeaveCriticalSection
0x18001722c  mov     rcx, [rbx+20h]
0x180017230  test    rcx, rcx
0x180017233  jz      short loc_180017254
0x180017235  cmp     [rbx+40h], r15d
0x180017239  jnz     short loc_180017244
0x18001723b  mov     rax, [rbx+18h]
0x18001723f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017244  mov     rcx, [rbx+20h]
0x180017248  mov     rax, [rcx]
0x18001724b  mov     rax, [rax+10h]
0x18001724f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017254  mov     rcx, rbx; this
0x180017257  call    ??_GSCHED_ITEM@@QEAAPEAXI@Z; SCHED_ITEM::`scalar deleting destructor'(uint)
0x18001725c  mov     rsi, r15
0x18001725f  cmp     cs:?g_fSchedShutdown@@3HA, r15d; int g_fSchedShutdown
0x180017266  jnz     loc_180017180
0x18001726c  cmp     cs:?g_fSchedulePaused@@3HA, r15d; int g_fSchedulePaused
0x180017273  jnz     loc_180016F7A
0x180017279  call    cs:__imp_GetTickCount
0x18001727f  cmp     cs:dword_1800B1590, r15d
0x180017286  mov     edi, eax
0x180017288  jz      loc_1800171C4
0x18001728e  mov     rcx, r12; lpCriticalSection
0x180017291  call    cs:__imp_EnterCriticalSection
0x180017297  jmp     loc_1800171C4
0x18001729c  mov     ebp, ecx
0x18001729e  sub     ebp, edi
0x1800172a0  mov     rcx, r12; lpCriticalSection
0x1800172a3  call    cs:__imp_LeaveCriticalSection
0x1800172a9  jmp     loc_180016F7A
0x1800172ae  mov     rsi, rdi
0x1800172b1  cmp     [rdi+40h], r15d
0x1800172b5  jnz     short loc_1800172C0
0x1800172b7  mov     rcx, [rdi+38h]
0x1800172bb  test    rcx, rcx
0x1800172be  jnz     short loc_1800172C8
0x1800172c0  mov     rdi, [rdi]
0x1800172c3  jmp     loc_180016FB2
0x1800172c8  mov     eax, r14d
0x1800172cb  inc     r14d
0x1800172ce  mov     [rsp+rax*8+298h+Handles], rcx
0x1800172d3  cmp     r14d, 40h ; '@'
0x1800172d7  jnz     short loc_1800172C0
0x1800172d9  xor     edx, edx
0x1800172db  lea     r8, aSchedulerthrea_1; "SchedulerThread: Reached max scheduled "...
0x1800172e2  lea     ecx, [rdx+2]
0x1800172e5  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800172ea  mov     rdx, rax; char *
0x1800172ed  lea     rcx, aSchedulerthrea; "SchedulerThread"
0x1800172f4  mov     rbx, rax
0x1800172f7  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800172fc  mov     rcx, rbx; this
0x1800172ff  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180017304  xor     edx, edx
0x180017306  lea     r8, aSchedulerthrea_1; "SchedulerThread: Reached max scheduled "...
0x18001730d  lea     ecx, [rdx+2]
0x180017310  call    WiaTrace_TraceWithSubCompTraceLevel
0x180017315  lea     r9d, [r14-3Ch]; int
0x180017319  mov     [rsp+298h+lpMem], rax; lpMem
0x18001731e  lea     r8, aSchedulerthrea; "SchedulerThread"
0x180017325  call    WiaTrace_ProcessTrace_Ex
0x18001732a  jmp     loc_180016FBB
0x18001732f  mov     rcx, rdx
0x180017332  jmp     loc_18001708B
0x180017337  mov     rax, [rsi+18h]
0x18001733b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017340  jmp     loc_1800170F1
0x180017345  mov     ebp, [rsi+28h]
0x180017348  sub     ebp, eax
0x18001734a  jmp     loc_1800172A0
0x18001734f  or      ebp, 0FFFFFFFFh
0x180017352  jmp     loc_1800172A0
```
