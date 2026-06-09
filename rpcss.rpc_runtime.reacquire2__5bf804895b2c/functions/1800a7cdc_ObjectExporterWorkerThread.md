# ObjectExporterWorkerThread

- ea: `0x1800a7cdc`
- end: `0x1800a8237`
- name: `ObjectExporterWorkerThread`
- size: `1371`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800bd340`

## callees

- `0x180015ea0`
- `0x180015eec`
- `0x180019cb0`
- `0x18001c624`
- `0x18001d440`
- `0x18002a89c`
- `0x180034260`
- `0x1800369b0`
- `0x1800464a4`
- `0x180059020`
- `0x18006016c`
- `0x180060b04`
- `0x18006d0b0`
- `0x180074364`
- `0x18007a28c`
- `0x18007fa88`
- `0x1800852b0`
- `0x1800858f0`
- `0x1800a7388`
- `0x1800a780c`
- `0x1800a7cdc`
- `0x1800a8240`
- `0x1800be360`
- `0x1800c1d64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a7cf9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a7de3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a81fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a7cf9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a7de3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a81fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a7eae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a7f7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a7eae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a7f7f`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800a7d8f`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800a7d8f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a7d53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a7d61`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a7dfe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a7e46`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a7e97`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a7f68`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a81a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a7d53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a7d61`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a7dfe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a7e46`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a7e97`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a7f68`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a81a0`

## string_xrefs

- `0x1800a7d43`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x1800a7dc2`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x1800a7f1e`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x1800a80ad`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x1800a80ee`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x1800a81f1`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x1800a7d27`: `Worker thread started`
- `0x1800a7d3c`: `ObjectExporterWorkerThread`
- `0x1800a7db6`: `ObjectExporterWorkerThread`
- `0x1800a7f12`: `ObjectExporterWorkerThread`
- `0x1800a80a1`: `ObjectExporterWorkerThread`
- `0x1800a80e3`: `ObjectExporterWorkerThread`
- `0x1800a81ea`: `ObjectExporterWorkerThread`
- `0x1800a7dc9`: `Worker thread, new iteration %I64d`
- `0x1800a8094`: `Creating additional task thread, we're behind..`
- `0x1800a8167`: `ServerOXIDs:%d ServerOIDs:%d ServerSets:%d ClientOxids:%d ClientOids:%d ClientSets:%d Mids:%d Process:%d Threads:%d`
- `0x1800a81d1`: `Worker thread waiting until %#x`

## pseudocode

```c
void __fastcall __noreturn ObjectExporterWorkerThread(__int64 a1)
{
  DWORD TickCount; // esi
  DWORD v2; // r14d
  unsigned int i; // r12d
  unsigned __int16 CurrentThreadId; // ax
  DWORD v5; // edi
  DWORD v6; // ebx
  CServerSetTable *v7; // rcx
  unsigned __int64 v8; // r15
  CServerSetTable *v9; // rcx
  CClientOxid *v10; // rbx
  int v11; // r9d
  struct CListElement *v12; // rax
  int v13; // r15d
  int v14; // eax
  int v15; // r13d
  int v16; // r12d
  DWORD v17; // ecx
  int v18; // ecx
  int v19; // edi
  DWORD v20; // edx
  CRemoteMachineList *v21; // rcx
  int v22; // r9d
  DWORD v23; // ebx
  unsigned __int16 v24; // ax
  __int64 v25; // [rsp+20h] [rbp-69h]
  __int64 v26; // [rsp+28h] [rbp-61h]
  __int64 v27; // [rsp+30h] [rbp-59h]
  __int64 v28; // [rsp+38h] [rbp-51h]
  __int64 v29; // [rsp+40h] [rbp-49h]
  __int64 v30; // [rsp+48h] [rbp-41h]
  __int64 v31; // [rsp+50h] [rbp-39h]
  __int64 v32; // [rsp+58h] [rbp-31h]
  __int64 v33; // [rsp+60h] [rbp-29h]
  __int64 v34; // [rsp+68h] [rbp-21h]
  __int64 v35; // [rsp+70h] [rbp-19h]
  PSRWLOCK v36; // [rsp+80h] [rbp-9h] BYREF
  char v37[8]; // [rsp+88h] [rbp-1h] BYREF
  _BYTE v38[80]; // [rsp+90h] [rbp+7h] BYREF
  __int64 v39; // [rsp+F0h] [rbp+67h] BYREF
  DWORD v40; // [rsp+F8h] [rbp+6Fh] BYREF
  DWORD v41; // [rsp+100h] [rbp+77h] BYREF
  PSRWLOCK SRWLock; // [rsp+108h] [rbp+7Fh] BYREF

  v39 = a1;
  dword_180158718 = GetCurrentThreadId();
  if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
    ComTraceMessageT<>(
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\worker.cxx",
      (unsigned int)"ObjectExporterWorkerThread",
      210,
      3,
      (__int64)L"Worker thread started");
  LODWORD(v39) = 0;
  TickCount = GetTickCount();
  v2 = GetTickCount();
  for ( i = 0; ; ++i )
  {
    v40 = i;
    ++RpcssTestHook_PingIntervalCount;
    WakeByAddressAll(&RpcssTestHook_PingIntervalCount);
    if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
      ComTraceMessageT<unsigned short const *>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\worker.cxx",
        (unsigned int)"ObjectExporterWorkerThread",
        236,
        3,
        (__int64)L"Worker thread, new iteration %I64d",
        RpcssTestHook_PingIntervalCount);
    CurrentThreadId = GetCurrentThreadId();
    RpcssTestLog::Log((RpcssTestLog *)0x3EA, CurrentThreadId, i);
    v5 = GetTickCount();
    v41 = v5;
    v6 = v5 + 1000 * g_usBasePingInterval;
    if ( (v5 - v2) / 0x3E8 > g_usBaseFastRundownTimeoutInterval )
    {
      if ( MoveFastRundownOidsFromGlobalListToServerOXIDList() )
        CProcess::FastRundownAllProcesses();
      v2 = GetTickCount();
    }
    Microsoft::WRL::Wrappers::SRWLock::LockShared(v37, &gpServerLock);
    v8 = CServerSetTable::CheckForRundowns(v7);
    Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v37);
    if ( v8 )
    {
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, &gpServerLock);
      if ( CServerSetTable::RundownSetIfNeeded(v9, v8) )
        v6 = GetTickCount();
      if ( SRWLock )
      {
        ReleaseSRWLockExclusive(SRWLock);
        SRWLock = 0;
      }
    }
    if ( (unsigned int)CPList::PeekMin(gpClientOxidPList, (struct CTime *)&v39) )
    {
      if ( (int)(v39 - v5) >= 0 )
      {
        if ( (int)(v39 - v6) < 0 )
          v6 = v39;
      }
      else
      {
        Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&v36, &gpClientLock);
        while ( 1 )
        {
          v12 = CPList::MaybeRemoveMin(gpClientOxidPList, (const struct CTime *)&v41);
          if ( !v12 )
            break;
          v10 = (struct CListElement *)((char *)v12 - 40);
          if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
            ComTraceMessageT<CClientOxid *,unsigned __int64>(
              (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\worker.cxx",
              (unsigned int)"ObjectExporterWorkerThread",
              300,
              v11,
              (__int64)L"Cleaning up client OXID %p OXID:%I64X",
              v10,
              *((_QWORD *)v10 + 3));
          if ( v10 )
            CClientOxid::`vector deleting destructor'(v10, 1u);
        }
        v6 = GetTickCount();
        if ( v36 )
        {
          ReleaseSRWLockExclusive(v36);
          v36 = 0;
        }
      }
    }
    v13 = 0;
    if ( (unsigned int)CPList::PeekMin(gpClientSetRemotePList, (struct CTime *)&v39) )
    {
      v14 = CInterlockedInteger::operator long(&dword_1801581F0);
      v15 = g_usBasePingInterval;
      v16 = v14;
      if ( (unsigned int)CInterlockedInteger::operator long(&dword_1801581F0)
        && (v17 = v5 + 1000 * (v15 + 10 * v16), (int)(v17 - v39) >= 0) )
      {
        i = v40;
        if ( (int)(v17 - v6) < 0 )
          v6 = v17;
      }
      else
      {
        i = v40;
        v13 = 1;
      }
    }
    Microsoft::WRL::Wrappers::SRWLock::LockShared(v38, &gpServerLock);
    if ( (unsigned int)CPList::PeekMin(gpServerOidPList, (struct CTime *)&v39) )
    {
      v18 = 10000 * CInterlockedInteger::operator long(&dword_1801581F0) - v5;
      v19 = v39;
      if ( (int)v39 + v18 >= 0 )
      {
        v20 = v19 + 20000 * CInterlockedInteger::operator long(&dword_1801581F0);
        if ( (int)(v20 - v6) < 0 )
          v6 = v20;
      }
      else
      {
        v13 = 1;
      }
    }
    Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v38);
    if ( v13 )
    {
      if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
        ComTraceMessageT<>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\worker.cxx",
          (unsigned int)"ObjectExporterWorkerThread",
          367,
          v22,
          (__int64)L"Creating additional task thread, we're behind..");
      TryToCreateNewTaskThread();
    }
    if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
    {
      LODWORD(v35) = dword_1801581F0;
      LODWORD(v34) = *((_DWORD *)gpProcessList + 1);
      LODWORD(v33) = *((_DWORD *)gpMidTable + 1);
      LODWORD(v32) = *((_DWORD *)gpClientSetTable + 1);
      LODWORD(v31) = *((_DWORD *)gpClientOidTable + 1);
      LODWORD(v30) = *((_DWORD *)gpClientOxidTable + 1);
      LODWORD(v29) = *((_DWORD *)gpServerSetTable + 3);
      LODWORD(v28) = *((_DWORD *)gpServerOidTable + 1);
      LODWORD(v27) = *((_DWORD *)gpServerOxidTable + 1);
      LODWORD(v25) = 4;
      ComTraceMessage(
        0xFFFFFFFFLL,
        "onecore\\com\\combase\\rpcss\\objex\\worker.cxx",
        "ObjectExporterWorkerThread",
        396,
        v25,
        L"ServerOXIDs:%d ServerOIDs:%d ServerSets:%d ClientOxids:%d ClientOids:%d ClientSets:%d Mids:%d Process:%d Threads:%d",
        v27,
        v28,
        v29,
        v30,
        v31,
        v32,
        v33,
        v34,
        v35);
    }
    v23 = v6 + 1000;
    v40 = v23;
    if ( v23 - TickCount >= 0x7918 )
    {
      CRemoteMachineList::TryToFlushIdleOrTooOldElements(v21);
      TickCount = GetTickCount();
    }
    CleanUpLeakedStateObjects();
    AnalyzeAndReportResourceMetrics();
    if ( gfEnableTracing )
    {
      if ( (unsigned __int8)IsWppLevelEnabled(3) )
      {
        LODWORD(v26) = v23;
        ComTraceMessageT<int>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\worker.cxx",
          (unsigned int)"ObjectExporterWorkerThread",
          413,
          3,
          (__int64)L"Worker thread waiting until %#x",
          v26);
      }
    }
    v24 = GetCurrentThreadId();
    RpcssTestLog::Log((RpcssTestLog *)0x3ED, v24, v23);
    CTime::Sleep((CTime *)&v40, gWorkerThreadTimer, gWorkerThreadWaitEvent);
  }
}

```

## disassembly

```asm
0x1800a7cdc  mov     [rsp-8+arg_0], rcx
0x1800a7ce1  push    rbp
0x1800a7ce2  push    rbx
0x1800a7ce3  push    rsi
0x1800a7ce4  push    rdi
0x1800a7ce5  push    r12
0x1800a7ce7  push    r13
0x1800a7ce9  push    r14
0x1800a7ceb  push    r15
0x1800a7ced  lea     rbp, [rsp-1Fh]
0x1800a7cf2  sub     rsp, 0A8h
0x1800a7cf9  call    cs:__imp_GetCurrentThreadId
0x1800a7d00  nop     dword ptr [rax+rax+00h]
0x1800a7d05  xor     r13d, r13d
0x1800a7d08  mov     cs:dword_180158718, eax
0x1800a7d0e  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x1800a7d15  mov     edi, 3
0x1800a7d1a  jz      short loc_1800A7D4F
0x1800a7d1c  mov     ecx, edi
0x1800a7d1e  call    IsWppLevelEnabled
0x1800a7d23  test    al, al
0x1800a7d25  jz      short loc_1800A7D4F
0x1800a7d27  lea     rax, aWorkerThreadSt; "Worker thread started"
0x1800a7d2e  mov     r9d, edi
0x1800a7d31  mov     r8d, 0D2h
0x1800a7d37  mov     [rsp+0E0h+var_C0], rax
0x1800a7d3c  lea     rdx, aObjectexporter; "ObjectExporterWorkerThread"
0x1800a7d43  lea     rcx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x1800a7d4a  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x1800a7d4f  mov     dword ptr [rbp+57h+arg_0], r13d
0x1800a7d53  call    cs:__imp_GetTickCount
0x1800a7d5a  nop     dword ptr [rax+rax+00h]
0x1800a7d5f  mov     esi, eax
0x1800a7d61  call    cs:__imp_GetTickCount
0x1800a7d68  nop     dword ptr [rax+rax+00h]
0x1800a7d6d  mov     r14d, eax
0x1800a7d70  mov     r12d, r13d
0x1800a7d73  mov     rax, cs:RpcssTestHook_PingIntervalCount
0x1800a7d7a  lea     rcx, RpcssTestHook_PingIntervalCount; Address
0x1800a7d81  inc     rax
0x1800a7d84  mov     [rbp+57h+arg_8], r12d
0x1800a7d88  mov     cs:RpcssTestHook_PingIntervalCount, rax
0x1800a7d8f  call    cs:__imp_WakeByAddressAll
0x1800a7d96  nop     dword ptr [rax+rax+00h]
0x1800a7d9b  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x1800a7da2  jz      short loc_1800A7DE3
0x1800a7da4  mov     ecx, edi
0x1800a7da6  call    IsWppLevelEnabled
0x1800a7dab  test    al, al
0x1800a7dad  jz      short loc_1800A7DE3
0x1800a7daf  mov     rax, cs:RpcssTestHook_PingIntervalCount
0x1800a7db6  lea     rdx, aObjectexporter; "ObjectExporterWorkerThread"
0x1800a7dbd  mov     [rsp+0E0h+var_B8], rax
0x1800a7dc2  lea     rcx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x1800a7dc9  lea     rax, aWorkerThreadNe; "Worker thread, new iteration %I64d"
0x1800a7dd0  mov     r9d, edi
0x1800a7dd3  mov     r8d, 0ECh
0x1800a7dd9  mov     [rsp+0E0h+var_C0], rax
0x1800a7dde  call    ??$ComTraceMessageT@PEBG@@YAXPEBD0HW4TraceLevel@@PEBG2@Z; ComTraceMessageT<ushort const *>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *)
0x1800a7de3  call    cs:__imp_GetCurrentThreadId
0x1800a7dea  nop     dword ptr [rax+rax+00h]
0x1800a7def  mov     ecx, 3EAh; this
0x1800a7df4  mov     r8d, r12d
0x1800a7df7  mov     edx, eax; unsigned __int16
0x1800a7df9  call    ?Log@RpcssTestLog@@YAXGZZ; RpcssTestLog::Log(ushort,...)
0x1800a7dfe  call    cs:__imp_GetTickCount
0x1800a7e05  nop     dword ptr [rax+rax+00h]
0x1800a7e0a  mov     edi, eax
0x1800a7e0c  mov     [rbp+57h+arg_10], eax
0x1800a7e0f  movzx   eax, cs:?g_usBasePingInterval@@3GA; ushort g_usBasePingInterval
0x1800a7e16  mov     ecx, edi
0x1800a7e18  imul    ebx, eax, 3E8h
0x1800a7e1e  sub     ecx, r14d
0x1800a7e21  mov     eax, 10624DD3h
0x1800a7e26  mul     ecx
0x1800a7e28  movzx   eax, cs:?g_usBaseFastRundownTimeoutInterval@@3GA; ushort g_usBaseFastRundownTimeoutInterval
0x1800a7e2f  add     ebx, edi
0x1800a7e31  shr     edx, 6
0x1800a7e34  cmp     edx, eax
0x1800a7e36  jbe     short loc_1800A7E55
0x1800a7e38  call    ?MoveFastRundownOidsFromGlobalListToServerOXIDList@@YA_NXZ; MoveFastRundownOidsFromGlobalListToServerOXIDList(void)
0x1800a7e3d  test    al, al
0x1800a7e3f  jz      short loc_1800A7E46
0x1800a7e41  call    ?FastRundownAllProcesses@CProcess@@SAXXZ; CProcess::FastRundownAllProcesses(void)
0x1800a7e46  call    cs:__imp_GetTickCount
0x1800a7e4d  nop     dword ptr [rax+rax+00h]
0x1800a7e52  mov     r14d, eax
0x1800a7e55  lea     rdx, ?gpServerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gpServerLock
0x1800a7e5c  lea     rcx, [rbp+57h+var_58]
0x1800a7e60  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x1800a7e65  call    ?CheckForRundowns@CServerSetTable@@QEAA_KXZ; CServerSetTable::CheckForRundowns(void)
0x1800a7e6a  lea     rcx, [rbp+57h+var_58]; this
0x1800a7e6e  mov     r15, rax
0x1800a7e71  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x1800a7e76  test    r15, r15
0x1800a7e79  jz      short loc_1800A7EBE
0x1800a7e7b  lea     rdx, ?gpServerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gpServerLock
0x1800a7e82  lea     rcx, [rbp+57h+SRWLock]
0x1800a7e86  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800a7e8b  mov     rdx, r15; unsigned __int64
0x1800a7e8e  call    ?RundownSetIfNeeded@CServerSetTable@@QEAAH_K@Z; CServerSetTable::RundownSetIfNeeded(unsigned __int64)
0x1800a7e93  test    eax, eax
0x1800a7e95  jz      short loc_1800A7EA5
0x1800a7e97  call    cs:__imp_GetTickCount
0x1800a7e9e  nop     dword ptr [rax+rax+00h]
0x1800a7ea3  mov     ebx, eax
0x1800a7ea5  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800a7ea9  test    rcx, rcx
0x1800a7eac  jz      short loc_1800A7EBE
0x1800a7eae  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a7eb5  nop     dword ptr [rax+rax+00h]
0x1800a7eba  mov     [rbp+57h+SRWLock], r13
0x1800a7ebe  mov     rcx, cs:?gpClientOxidPList@@3PEAVCPList@@EA; this
0x1800a7ec5  lea     rdx, [rbp+57h+arg_0]; struct CTime *
0x1800a7ec9  call    ?PeekMin@CPList@@QEAAHAEAVCTime@@@Z; CPList::PeekMin(CTime &)
0x1800a7ece  test    eax, eax
0x1800a7ed0  jz      loc_1800A7F96
0x1800a7ed6  mov     eax, dword ptr [rbp+57h+arg_0]
0x1800a7ed9  cmp     eax, edi
0x1800a7edb  jns     loc_1800A7F91
0x1800a7ee1  lea     rdx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gpClientLock
0x1800a7ee8  lea     rcx, [rbp+57h+var_60]
0x1800a7eec  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800a7ef1  jmp     short loc_1800A7F53
0x1800a7ef3  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x1800a7efa  lea     rbx, [rax-28h]
0x1800a7efe  jz      short loc_1800A7F41
0x1800a7f00  mov     ecx, 4
0x1800a7f05  call    IsWppLevelEnabled
0x1800a7f0a  test    al, al
0x1800a7f0c  jz      short loc_1800A7F41
0x1800a7f0e  mov     rax, [rbx+18h]
0x1800a7f12  lea     rdx, aObjectexporter; "ObjectExporterWorkerThread"
0x1800a7f19  mov     [rsp+0E0h+var_B0], rax
0x1800a7f1e  lea     rcx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x1800a7f25  lea     rax, aCleaningUpClie; "Cleaning up client OXID %p OXID:%I64X"
0x1800a7f2c  mov     [rsp+0E0h+var_B8], rbx
0x1800a7f31  mov     r8d, 12Ch
0x1800a7f37  mov     [rsp+0E0h+var_C0], rax
0x1800a7f3c  call    ??$ComTraceMessageT@PEAVCClientOxid@@_K@@YAXPEBD0HW4TraceLevel@@PEBGPEAVCClientOxid@@_K@Z; ComTraceMessageT<CClientOxid *,unsigned __int64>(char const *,char const *,int,TraceLevel,ushort const *,CClientOxid *,unsigned __int64)
0x1800a7f41  test    rbx, rbx
0x1800a7f44  jz      short loc_1800A7F53
0x1800a7f46  mov     edx, 1; unsigned int
0x1800a7f4b  mov     rcx, rbx; this
0x1800a7f4e  call    ??_ECClientOxid@@UEAAPEAXI@Z; CClientOxid::`vector deleting destructor'(uint)
0x1800a7f53  mov     rcx, cs:?gpClientOxidPList@@3PEAVCPList@@EA; this
0x1800a7f5a  lea     rdx, [rbp+57h+arg_10]; struct CTime *
0x1800a7f5e  call    ?MaybeRemoveMin@CPList@@QEAAPEAVCListElement@@AEBVCTime@@@Z; CPList::MaybeRemoveMin(CTime const &)
0x1800a7f63  test    rax, rax
0x1800a7f66  jnz     short loc_1800A7EF3
0x1800a7f68  call    cs:__imp_GetTickCount
0x1800a7f6f  nop     dword ptr [rax+rax+00h]
0x1800a7f74  mov     rcx, [rbp+57h+var_60]; SRWLock
0x1800a7f78  mov     ebx, eax
0x1800a7f7a  test    rcx, rcx
0x1800a7f7d  jz      short loc_1800A7F96
0x1800a7f7f  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a7f86  nop     dword ptr [rax+rax+00h]
0x1800a7f8b  mov     [rbp+57h+var_60], r13
0x1800a7f8f  jmp     short loc_1800A7F96
0x1800a7f91  cmp     eax, ebx
0x1800a7f93  cmovs   ebx, eax
0x1800a7f96  mov     rcx, cs:?gpClientSetRemotePList@@3PEAVCPList@@EA; this
0x1800a7f9d  lea     rdx, [rbp+57h+arg_0]; struct CTime *
0x1800a7fa1  mov     r15d, r13d
0x1800a7fa4  call    ?PeekMin@CPList@@QEAAHAEAVCTime@@@Z; CPList::PeekMin(CTime &)
0x1800a7fa9  test    eax, eax
0x1800a7fab  jz      short loc_1800A800B
0x1800a7fad  lea     rcx, dword_1801581F0
0x1800a7fb4  call    ??BCInterlockedInteger@@QEAAJXZ; CInterlockedInteger::operator long(void)
0x1800a7fb9  movzx   r13d, cs:?g_usBasePingInterval@@3GA; ushort g_usBasePingInterval
0x1800a7fc1  lea     rcx, dword_1801581F0
0x1800a7fc8  mov     r12d, eax
0x1800a7fcb  call    ??BCInterlockedInteger@@QEAAJXZ; CInterlockedInteger::operator long(void)
0x1800a7fd0  test    eax, eax
0x1800a7fd2  jz      short loc_1800A7FFE
0x1800a7fd4  lea     eax, [r12+r12*4]
0x1800a7fd8  lea     ecx, ds:0[rax*2]
0x1800a7fdf  add     ecx, r13d
0x1800a7fe2  imul    ecx, 3E8h
0x1800a7fe8  add     ecx, edi
0x1800a7fea  cmp     ecx, dword ptr [rbp+57h+arg_0]
0x1800a7fed  js      short loc_1800A7FFE
0x1800a7fef  mov     r12d, [rbp+57h+arg_8]
0x1800a7ff3  xor     r13d, r13d
0x1800a7ff6  cmp     ecx, ebx
0x1800a7ff8  jns     short loc_1800A800B
0x1800a7ffa  mov     ebx, ecx
0x1800a7ffc  jmp     short loc_1800A800B
0x1800a7ffe  mov     r12d, [rbp+57h+arg_8]
0x1800a8002  mov     r15d, 1
0x1800a8008  xor     r13d, r13d
0x1800a800b  lea     rdx, ?gpServerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gpServerLock
0x1800a8012  lea     rcx, [rbp+57h+var_50]
0x1800a8016  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x1800a801b  mov     rcx, cs:?gpServerOidPList@@3PEAVCServerOidPList@@EA; this
0x1800a8022  lea     rdx, [rbp+57h+arg_0]; struct CTime *
0x1800a8026  call    ?PeekMin@CPList@@QEAAHAEAVCTime@@@Z; CPList::PeekMin(CTime &)
0x1800a802b  test    eax, eax
0x1800a802d  jz      short loc_1800A806B
0x1800a802f  lea     rcx, dword_1801581F0
0x1800a8036  call    ??BCInterlockedInteger@@QEAAJXZ; CInterlockedInteger::operator long(void)
0x1800a803b  imul    ecx, eax, 2710h
0x1800a8041  sub     ecx, edi
0x1800a8043  mov     edi, dword ptr [rbp+57h+arg_0]
0x1800a8046  add     ecx, edi
0x1800a8048  jns     short loc_1800A8052
0x1800a804a  mov     r15d, 1
0x1800a8050  jmp     short loc_1800A806B
0x1800a8052  lea     rcx, dword_1801581F0
0x1800a8059  call    ??BCInterlockedInteger@@QEAAJXZ; CInterlockedInteger::operator long(void)
0x1800a805e  imul    edx, eax, 4E20h
0x1800a8064  add     edx, edi
0x1800a8066  cmp     edx, ebx
0x1800a8068  cmovs   ebx, edx
0x1800a806b  lea     rcx, [rbp+57h+var_50]; this
0x1800a806f  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x1800a8074  test    r15d, r15d
0x1800a8077  jz      short loc_1800A80BE
0x1800a8079  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x1800a8080  jz      short loc_1800A80B9
0x1800a8082  mov     r9d, 3
0x1800a8088  mov     ecx, r9d
0x1800a808b  call    IsWppLevelEnabled
0x1800a8090  test    al, al
0x1800a8092  jz      short loc_1800A80B9
0x1800a8094  lea     rax, aCreatingAdditi; "Creating additional task thread, we're "...
0x1800a809b  mov     r8d, 16Fh
0x1800a80a1  lea     rdx, aObjectexporter; "ObjectExporterWorkerThread"
0x1800a80a8  mov     [rsp+0E0h+var_C0], rax
0x1800a80ad  lea     rcx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x1800a80b4  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x1800a80b9  call    ?TryToCreateNewTaskThread@@YAXXZ; TryToCreateNewTaskThread(void)
0x1800a80be  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x1800a80c5  jz      loc_1800A8187
0x1800a80cb  mov     ecx, 4
0x1800a80d0  call    IsWppLevelEnabled
0x1800a80d5  test    al, al
0x1800a80d7  jz      loc_1800A8187
0x1800a80dd  mov     eax, cs:dword_1801581F0
0x1800a80e3  lea     r8, aObjectexporter; "ObjectExporterWorkerThread"
0x1800a80ea  mov     [rsp+0E0h+var_70], eax
0x1800a80ee  lea     rdx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x1800a80f5  mov     rax, cs:?gpProcessList@@3PEAVCBList@@EA; CBList * gpProcessList
0x1800a80fc  mov     r9d, 18Ch
0x1800a8102  mov     ecx, [rax+4]
0x1800a8105  mov     rax, cs:?gpMidTable@@3PEAVCHashTable@ObjexHashTable@@EA; ObjexHashTable::CHashTable * gpMidTable
0x1800a810c  mov     dword ptr [rsp+0E0h+var_78], ecx
0x1800a8110  mov     ecx, [rax+4]
0x1800a8113  mov     rax, cs:?gpClientSetTable@@3PEAVCHashTable@ObjexHashTable@@EA; ObjexHashTable::CHashTable * gpClientSetTable
0x1800a811a  mov     dword ptr [rsp+0E0h+var_80], ecx
0x1800a811e  mov     ecx, [rax+4]
0x1800a8121  mov     rax, cs:?gpClientOidTable@@3PEAVCHashTable@ObjexHashTable@@EA; ObjexHashTable::CHashTable * gpClientOidTable
0x1800a8128  mov     dword ptr [rsp+0E0h+var_88], ecx
0x1800a812c  mov     ecx, [rax+4]
0x1800a812f  mov     rax, cs:?gpClientOxidTable@@3PEAVCHashTable@ObjexHashTable@@EA; ObjexHashTable::CHashTable * gpClientOxidTable
0x1800a8136  mov     dword ptr [rsp+0E0h+var_90], ecx
0x1800a813a  mov     ecx, [rax+4]
0x1800a813d  mov     rax, cs:?gpServerSetTable@@3PEAVCServerSetTable@@EA; CServerSetTable * gpServerSetTable
0x1800a8144  mov     dword ptr [rsp+0E0h+var_98], ecx
0x1800a8148  mov     ecx, [rax+0Ch]
0x1800a814b  mov     rax, cs:?gpServerOidTable@@3PEAVCHashTable@ObjexHashTable@@EA; ObjexHashTable::CHashTable * gpServerOidTable
0x1800a8152  mov     dword ptr [rsp+0E0h+var_A0], ecx
0x1800a8156  mov     ecx, [rax+4]
0x1800a8159  mov     rax, cs:?gpServerOxidTable@@3PEAVCHashTable@ObjexHashTable@@EA; ObjexHashTable::CHashTable * gpServerOxidTable
0x1800a8160  mov     dword ptr [rsp+0E0h+var_A8], ecx
0x1800a8164  mov     ecx, [rax+4]
0x1800a8167  lea     rax, aServeroxidsDSe; "ServerOXIDs:%d ServerOIDs:%d ServerSets"...
0x1800a816e  mov     dword ptr [rsp+0E0h+var_B0], ecx
0x1800a8172  or      ecx, 0FFFFFFFFh
0x1800a8175  mov     [rsp+0E0h+var_B8], rax
0x1800a817a  mov     dword ptr [rsp+0E0h+var_C0], 4
0x1800a8182  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800a8187  add     ebx, 3E8h
0x1800a818d  mov     eax, ebx
0x1800a818f  mov     [rbp+57h+arg_8], ebx
0x1800a8192  sub     eax, esi
0x1800a8194  cmp     eax, 7918h
0x1800a8199  jb      short loc_1800A81AE
0x1800a819b  call    ?TryToFlushIdleOrTooOldElements@CRemoteMachineList@@QEAAXXZ; CRemoteMachineList::TryToFlushIdleOrTooOldElements(void)
0x1800a81a0  call    cs:__imp_GetTickCount
0x1800a81a7  nop     dword ptr [rax+rax+00h]
0x1800a81ac  mov     esi, eax
0x1800a81ae  call    ?CleanUpLeakedStateObjects@@YAXXZ; CleanUpLeakedStateObjects(void)
0x1800a81b3  call    ?AnalyzeAndReportResourceMetrics@@YAXXZ; AnalyzeAndReportResourceMetrics(void)
0x1800a81b8  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x1800a81bf  mov     edi, 3
0x1800a81c4  jz      short loc_1800A81FD
0x1800a81c6  mov     ecx, edi
0x1800a81c8  call    IsWppLevelEnabled
0x1800a81cd  test    al, al
0x1800a81cf  jz      short loc_1800A81FD
0x1800a81d1  lea     rax, aWorkerThreadWa; "Worker thread waiting until %#x"
0x1800a81d8  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x1800a81dc  mov     r9d, edi
0x1800a81df  mov     [rsp+0E0h+var_C0], rax
0x1800a81e4  mov     r8d, 19Dh
0x1800a81ea  lea     rdx, aObjectexporter; "ObjectExporterWorkerThread"
0x1800a81f1  lea     rcx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x1800a81f8  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
  ... truncated ...
```
