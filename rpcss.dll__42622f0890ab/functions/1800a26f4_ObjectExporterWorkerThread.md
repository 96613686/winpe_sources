# ObjectExporterWorkerThread

- ea: `0x1800a26f4`
- end: `0x1800a2c01`
- name: `ObjectExporterWorkerThread`
- size: `1293`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b7d10`

## callees

- `0x180011ec4`
- `0x180011f10`
- `0x180015ad0`
- `0x180018344`
- `0x180019158`
- `0x180027690`
- `0x180034368`
- `0x180034540`
- `0x18003bf60`
- `0x180053cf4`
- `0x18005ba08`
- `0x18005c11c`
- `0x180068440`
- `0x18006ff5c`
- `0x180075aec`
- `0x18007b3c8`
- `0x180080870`
- `0x18008150c`
- `0x1800a1e98`
- `0x1800a228c`
- `0x1800a26f4`
- `0x1800a2c08`
- `0x1800b8c4c`
- `0x1800bc430`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a2711`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a27e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a2bcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a2711`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a27e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a2bcd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a2896`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a295b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a2896`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a295b`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800a2795`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800a2795`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a2765`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a276d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a27f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a283a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a2885`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a294a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a2b76`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a2765`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a276d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a27f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a283a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a2885`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a294a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a2b76`

## string_xrefs

- `0x1800a2755`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x1800a27c2`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x1800a2900`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x1800a2a83`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x1800a2ac4`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x1800a2bc1`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x1800a2739`: `Worker thread started`
- `0x1800a274e`: `ObjectExporterWorkerThread`
- `0x1800a27b6`: `ObjectExporterWorkerThread`
- `0x1800a28f4`: `ObjectExporterWorkerThread`
- `0x1800a2a77`: `ObjectExporterWorkerThread`
- `0x1800a2ab9`: `ObjectExporterWorkerThread`
- `0x1800a2bba`: `ObjectExporterWorkerThread`
- `0x1800a27c9`: `Worker thread, new iteration %I64d`
- `0x1800a2a6a`: `Creating additional task thread, we're behind..`
- `0x1800a2b3d`: `ServerOXIDs:%d ServerOIDs:%d ServerSets:%d ClientOxids:%d ClientOids:%d ClientSets:%d Mids:%d Process:%d Threads:%d`
- `0x1800a2ba1`: `Worker thread waiting until %#x`

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
  __int64 v8; // r15
  CServerSetTable *v9; // rcx
  CClientOxid *v10; // rbx
  struct CListElement *v11; // rax
  int v12; // r15d
  int v13; // eax
  int v14; // r13d
  int v15; // r12d
  DWORD v16; // ecx
  int v17; // ecx
  int v18; // edi
  DWORD v19; // edx
  CRemoteMachineList *v20; // rcx
  DWORD v21; // ebx
  unsigned __int16 v22; // ax
  const wchar_t *v23; // [rsp+28h] [rbp-61h]
  PSRWLOCK v24; // [rsp+80h] [rbp-9h] BYREF
  char v25[8]; // [rsp+88h] [rbp-1h] BYREF
  _BYTE v26[80]; // [rsp+90h] [rbp+7h] BYREF
  __int64 v27; // [rsp+F0h] [rbp+67h] BYREF
  DWORD v28; // [rsp+F8h] [rbp+6Fh] BYREF
  DWORD v29; // [rsp+100h] [rbp+77h] BYREF
  PSRWLOCK SRWLock; // [rsp+108h] [rbp+7Fh] BYREF

  v27 = a1;
  dword_18014F618 = GetCurrentThreadId();
  if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
    ComTraceMessageT<>(
      (__int64)"onecore\\com\\combase\\rpcss\\objex\\worker.cxx",
      (__int64)"ObjectExporterWorkerThread",
      0xD2u);
  LODWORD(v27) = 0;
  TickCount = GetTickCount();
  v2 = GetTickCount();
  for ( i = 0; ; ++i )
  {
    v28 = i;
    ++RpcssTestHook_PingIntervalCount;
    WakeByAddressAll(&RpcssTestHook_PingIntervalCount);
    if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
      ComTraceMessageT<unsigned short const *>(
        (__int64)"onecore\\com\\combase\\rpcss\\objex\\worker.cxx",
        (__int64)"ObjectExporterWorkerThread",
        0xECu,
        3,
        (__int64)L"Worker thread, new iteration %I64d",
        RpcssTestHook_PingIntervalCount);
    CurrentThreadId = GetCurrentThreadId();
    RpcssTestLog::Log((RpcssTestLog *)0x3EA, CurrentThreadId, i);
    v5 = GetTickCount();
    v29 = v5;
    v6 = v5 + 1000 * g_usBasePingInterval;
    if ( (v5 - v2) / 0x3E8 > g_usBaseFastRundownTimeoutInterval )
    {
      if ( MoveFastRundownOidsFromGlobalListToServerOXIDList() )
        CProcess::FastRundownAllProcesses();
      v2 = GetTickCount();
    }
    Microsoft::WRL::Wrappers::SRWLock::LockShared(v25, &gpServerLock);
    v8 = CServerSetTable::CheckForRundowns(v7);
    Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v25);
    if ( v8 )
    {
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, &gpServerLock);
      if ( (unsigned int)CServerSetTable::RundownSetIfNeeded(v9, v8) )
        v6 = GetTickCount();
      if ( SRWLock )
      {
        ReleaseSRWLockExclusive(SRWLock);
        SRWLock = 0;
      }
    }
    if ( (unsigned int)CPList::PeekMin(gpClientOxidPList, (struct CTime *)&v27) )
    {
      if ( (int)(v27 - v5) >= 0 )
      {
        if ( (int)(v27 - v6) < 0 )
          v6 = v27;
      }
      else
      {
        Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&v24, &gpClientLock);
        while ( 1 )
        {
          v11 = CPList::MaybeRemoveMin(gpClientOxidPList, (const struct CTime *)&v29);
          if ( !v11 )
            break;
          v10 = (struct CListElement *)((char *)v11 - 40);
          if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
          {
            HIDWORD(v23) = HIDWORD(v10);
            ComTraceMessageT<CClientOxid *,unsigned __int64>(
              (__int64)"onecore\\com\\combase\\rpcss\\objex\\worker.cxx",
              (__int64)"ObjectExporterWorkerThread",
              0x12Cu);
          }
          if ( v10 )
            CClientOxid::`vector deleting destructor'(v10, 1u);
        }
        v6 = GetTickCount();
        if ( v24 )
        {
          ReleaseSRWLockExclusive(v24);
          v24 = 0;
        }
      }
    }
    v12 = 0;
    if ( (unsigned int)CPList::PeekMin(gpClientSetRemotePList, (struct CTime *)&v27) )
    {
      v13 = CInterlockedInteger::operator long(&dword_18014F0F0);
      v14 = g_usBasePingInterval;
      v15 = v13;
      if ( (unsigned int)CInterlockedInteger::operator long(&dword_18014F0F0)
        && (v16 = v5 + 1000 * (v14 + 10 * v15), (int)(v16 - v27) >= 0) )
      {
        i = v28;
        if ( (int)(v16 - v6) < 0 )
          v6 = v16;
      }
      else
      {
        i = v28;
        v12 = 1;
      }
    }
    Microsoft::WRL::Wrappers::SRWLock::LockShared(v26, &gpServerLock);
    if ( (unsigned int)CPList::PeekMin(gpServerOidPList, (struct CTime *)&v27) )
    {
      v17 = 10000 * CInterlockedInteger::operator long(&dword_18014F0F0) - v5;
      v18 = v27;
      if ( (int)v27 + v17 >= 0 )
      {
        v19 = v18 + 20000 * CInterlockedInteger::operator long(&dword_18014F0F0);
        if ( (int)(v19 - v6) < 0 )
          v6 = v19;
      }
      else
      {
        v12 = 1;
      }
    }
    Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v26);
    if ( v12 )
    {
      if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
        ComTraceMessageT<>(
          (__int64)"onecore\\com\\combase\\rpcss\\objex\\worker.cxx",
          (__int64)"ObjectExporterWorkerThread",
          0x16Fu);
      TryToCreateNewTaskThread();
    }
    if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
    {
      v23 = L"ServerOXIDs:%d ServerOIDs:%d ServerSets:%d ClientOxids:%d ClientOids:%d ClientSets:%d Mids:%d Process:%d Threads:%d";
      ComTraceMessage(
        0xFFFFFFFFLL,
        "onecore\\com\\combase\\rpcss\\objex\\worker.cxx",
        "ObjectExporterWorkerThread",
        396);
    }
    v21 = v6 + 1000;
    v28 = v21;
    if ( v21 - TickCount >= 0x7918 )
    {
      CRemoteMachineList::TryToFlushIdleOrTooOldElements(v20);
      TickCount = GetTickCount();
    }
    CleanUpLeakedStateObjects();
    AnalyzeAndReportResourceMetrics();
    if ( gfEnableTracing )
    {
      if ( (unsigned __int8)IsWppLevelEnabled(3) )
      {
        LODWORD(v23) = v21;
        ComTraceMessageT<int>(
          (__int64)"onecore\\com\\combase\\rpcss\\objex\\worker.cxx",
          (__int64)"ObjectExporterWorkerThread",
          0x19Du,
          3,
          (__int64)L"Worker thread waiting until %#x",
          v23);
      }
    }
    v22 = GetCurrentThreadId();
    RpcssTestLog::Log((RpcssTestLog *)0x3ED, v22, v21);
    CTime::Sleep((CTime *)&v28, gWorkerThreadTimer, gWorkerThreadWaitEvent);
  }
}

```

## disassembly

```asm
0x1800a26f4  mov     [rsp-8+arg_0], rcx
0x1800a26f9  push    rbp
0x1800a26fa  push    rbx
0x1800a26fb  push    rsi
0x1800a26fc  push    rdi
0x1800a26fd  push    r12
0x1800a26ff  push    r13
0x1800a2701  push    r14
0x1800a2703  push    r15
0x1800a2705  lea     rbp, [rsp-1Fh]
0x1800a270a  sub     rsp, 0A8h
0x1800a2711  call    cs:__imp_GetCurrentThreadId
0x1800a2717  xor     r13d, r13d
0x1800a271a  mov     cs:dword_18014F618, eax
0x1800a2720  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x1800a2727  mov     edi, 3
0x1800a272c  jz      short loc_1800A2761
0x1800a272e  mov     ecx, edi
0x1800a2730  call    IsWppLevelEnabled
0x1800a2735  test    al, al
0x1800a2737  jz      short loc_1800A2761
0x1800a2739  lea     rax, aWorkerThreadSt; "Worker thread started"
0x1800a2740  mov     r9d, edi
0x1800a2743  mov     r8d, 0D2h
0x1800a2749  mov     [rsp+0E0h+var_C0], rax
0x1800a274e  lea     rdx, aObjectexporter; "ObjectExporterWorkerThread"
0x1800a2755  lea     rcx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x1800a275c  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x1800a2761  mov     dword ptr [rbp+57h+arg_0], r13d
0x1800a2765  call    cs:__imp_GetTickCount
0x1800a276b  mov     esi, eax
0x1800a276d  call    cs:__imp_GetTickCount
0x1800a2773  mov     r14d, eax
0x1800a2776  mov     r12d, r13d
0x1800a2779  mov     rax, cs:RpcssTestHook_PingIntervalCount
0x1800a2780  lea     rcx, RpcssTestHook_PingIntervalCount; Address
0x1800a2787  inc     rax
0x1800a278a  mov     [rbp+57h+arg_8], r12d
0x1800a278e  mov     cs:RpcssTestHook_PingIntervalCount, rax
0x1800a2795  call    cs:__imp_WakeByAddressAll
0x1800a279b  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x1800a27a2  jz      short loc_1800A27E3
0x1800a27a4  mov     ecx, edi
0x1800a27a6  call    IsWppLevelEnabled
0x1800a27ab  test    al, al
0x1800a27ad  jz      short loc_1800A27E3
0x1800a27af  mov     rax, cs:RpcssTestHook_PingIntervalCount
0x1800a27b6  lea     rdx, aObjectexporter; "ObjectExporterWorkerThread"
0x1800a27bd  mov     [rsp+0E0h+var_B8], rax
0x1800a27c2  lea     rcx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x1800a27c9  lea     rax, aWorkerThreadNe; "Worker thread, new iteration %I64d"
0x1800a27d0  mov     r9d, edi
0x1800a27d3  mov     r8d, 0ECh
0x1800a27d9  mov     [rsp+0E0h+var_C0], rax
0x1800a27de  call    ??$ComTraceMessageT@PEBG@@YAXPEBD0HW4TraceLevel@@PEBG2@Z; ComTraceMessageT<ushort const *>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *)
0x1800a27e3  call    cs:__imp_GetCurrentThreadId
0x1800a27e9  mov     ecx, 3EAh; this
0x1800a27ee  mov     r8d, r12d
0x1800a27f1  mov     edx, eax; unsigned __int16
0x1800a27f3  call    ?Log@RpcssTestLog@@YAXGZZ; RpcssTestLog::Log(ushort,...)
0x1800a27f8  call    cs:__imp_GetTickCount
0x1800a27fe  mov     edi, eax
0x1800a2800  mov     [rbp+57h+arg_10], eax
0x1800a2803  movzx   eax, cs:?g_usBasePingInterval@@3GA; ushort g_usBasePingInterval
0x1800a280a  mov     ecx, edi
0x1800a280c  imul    ebx, eax, 3E8h
0x1800a2812  sub     ecx, r14d
0x1800a2815  mov     eax, 10624DD3h
0x1800a281a  mul     ecx
0x1800a281c  movzx   eax, cs:?g_usBaseFastRundownTimeoutInterval@@3GA; ushort g_usBaseFastRundownTimeoutInterval
0x1800a2823  add     ebx, edi
0x1800a2825  shr     edx, 6
0x1800a2828  cmp     edx, eax
0x1800a282a  jbe     short loc_1800A2843
0x1800a282c  call    ?MoveFastRundownOidsFromGlobalListToServerOXIDList@@YA_NXZ; MoveFastRundownOidsFromGlobalListToServerOXIDList(void)
0x1800a2831  test    al, al
0x1800a2833  jz      short loc_1800A283A
0x1800a2835  call    ?FastRundownAllProcesses@CProcess@@SAXXZ; CProcess::FastRundownAllProcesses(void)
0x1800a283a  call    cs:__imp_GetTickCount
0x1800a2840  mov     r14d, eax
0x1800a2843  lea     rdx, ?gpServerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gpServerLock
0x1800a284a  lea     rcx, [rbp+57h+var_58]
0x1800a284e  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x1800a2853  call    ?CheckForRundowns@CServerSetTable@@QEAA_KXZ; CServerSetTable::CheckForRundowns(void)
0x1800a2858  lea     rcx, [rbp+57h+var_58]; this
0x1800a285c  mov     r15, rax
0x1800a285f  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x1800a2864  test    r15, r15
0x1800a2867  jz      short loc_1800A28A0
0x1800a2869  lea     rdx, ?gpServerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gpServerLock
0x1800a2870  lea     rcx, [rbp+57h+SRWLock]
0x1800a2874  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800a2879  mov     rdx, r15; unsigned __int64
0x1800a287c  call    ?RundownSetIfNeeded@CServerSetTable@@QEAAH_K@Z; CServerSetTable::RundownSetIfNeeded(unsigned __int64)
0x1800a2881  test    eax, eax
0x1800a2883  jz      short loc_1800A288D
0x1800a2885  call    cs:__imp_GetTickCount
0x1800a288b  mov     ebx, eax
0x1800a288d  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800a2891  test    rcx, rcx
0x1800a2894  jz      short loc_1800A28A0
0x1800a2896  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a289c  mov     [rbp+57h+SRWLock], r13
0x1800a28a0  mov     rcx, cs:?gpClientOxidPList@@3PEAVCPList@@EA; this
0x1800a28a7  lea     rdx, [rbp+57h+arg_0]; struct CTime *
0x1800a28ab  call    ?PeekMin@CPList@@QEAAHAEAVCTime@@@Z; CPList::PeekMin(CTime &)
0x1800a28b0  test    eax, eax
0x1800a28b2  jz      loc_1800A296C
0x1800a28b8  mov     eax, dword ptr [rbp+57h+arg_0]
0x1800a28bb  cmp     eax, edi
0x1800a28bd  jns     loc_1800A2967
0x1800a28c3  lea     rdx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gpClientLock
0x1800a28ca  lea     rcx, [rbp+57h+var_60]
0x1800a28ce  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800a28d3  jmp     short loc_1800A2935
0x1800a28d5  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x1800a28dc  lea     rbx, [rax-28h]
0x1800a28e0  jz      short loc_1800A2923
0x1800a28e2  mov     ecx, 4
0x1800a28e7  call    IsWppLevelEnabled
0x1800a28ec  test    al, al
0x1800a28ee  jz      short loc_1800A2923
0x1800a28f0  mov     rax, [rbx+18h]
0x1800a28f4  lea     rdx, aObjectexporter; "ObjectExporterWorkerThread"
0x1800a28fb  mov     [rsp+0E0h+var_B0], rax
0x1800a2900  lea     rcx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x1800a2907  lea     rax, aCleaningUpClie; "Cleaning up client OXID %p OXID:%I64X"
0x1800a290e  mov     [rsp+0E0h+var_B8], rbx
0x1800a2913  mov     r8d, 12Ch
0x1800a2919  mov     [rsp+0E0h+var_C0], rax
0x1800a291e  call    ??$ComTraceMessageT@PEAVCClientOxid@@_K@@YAXPEBD0HW4TraceLevel@@PEBGPEAVCClientOxid@@_K@Z; ComTraceMessageT<CClientOxid *,unsigned __int64>(char const *,char const *,int,TraceLevel,ushort const *,CClientOxid *,unsigned __int64)
0x1800a2923  test    rbx, rbx
0x1800a2926  jz      short loc_1800A2935
0x1800a2928  mov     edx, 1; unsigned int
0x1800a292d  mov     rcx, rbx; this
0x1800a2930  call    ??_ECClientOxid@@UEAAPEAXI@Z; CClientOxid::`vector deleting destructor'(uint)
0x1800a2935  mov     rcx, cs:?gpClientOxidPList@@3PEAVCPList@@EA; this
0x1800a293c  lea     rdx, [rbp+57h+arg_10]; struct CTime *
0x1800a2940  call    ?MaybeRemoveMin@CPList@@QEAAPEAVCListElement@@AEBVCTime@@@Z; CPList::MaybeRemoveMin(CTime const &)
0x1800a2945  test    rax, rax
0x1800a2948  jnz     short loc_1800A28D5
0x1800a294a  call    cs:__imp_GetTickCount
0x1800a2950  mov     rcx, [rbp+57h+var_60]; SRWLock
0x1800a2954  mov     ebx, eax
0x1800a2956  test    rcx, rcx
0x1800a2959  jz      short loc_1800A296C
0x1800a295b  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a2961  mov     [rbp+57h+var_60], r13
0x1800a2965  jmp     short loc_1800A296C
0x1800a2967  cmp     eax, ebx
0x1800a2969  cmovs   ebx, eax
0x1800a296c  mov     rcx, cs:?gpClientSetRemotePList@@3PEAVCPList@@EA; this
0x1800a2973  lea     rdx, [rbp+57h+arg_0]; struct CTime *
0x1800a2977  mov     r15d, r13d
0x1800a297a  call    ?PeekMin@CPList@@QEAAHAEAVCTime@@@Z; CPList::PeekMin(CTime &)
0x1800a297f  test    eax, eax
0x1800a2981  jz      short loc_1800A29E1
0x1800a2983  lea     rcx, dword_18014F0F0
0x1800a298a  call    ??BCInterlockedInteger@@QEAAJXZ; CInterlockedInteger::operator long(void)
0x1800a298f  movzx   r13d, cs:?g_usBasePingInterval@@3GA; ushort g_usBasePingInterval
0x1800a2997  lea     rcx, dword_18014F0F0
0x1800a299e  mov     r12d, eax
0x1800a29a1  call    ??BCInterlockedInteger@@QEAAJXZ; CInterlockedInteger::operator long(void)
0x1800a29a6  test    eax, eax
0x1800a29a8  jz      short loc_1800A29D4
0x1800a29aa  lea     eax, [r12+r12*4]
0x1800a29ae  lea     ecx, ds:0[rax*2]
0x1800a29b5  add     ecx, r13d
0x1800a29b8  imul    ecx, 3E8h
0x1800a29be  add     ecx, edi
0x1800a29c0  cmp     ecx, dword ptr [rbp+57h+arg_0]
0x1800a29c3  js      short loc_1800A29D4
0x1800a29c5  mov     r12d, [rbp+57h+arg_8]
0x1800a29c9  xor     r13d, r13d
0x1800a29cc  cmp     ecx, ebx
0x1800a29ce  jns     short loc_1800A29E1
0x1800a29d0  mov     ebx, ecx
0x1800a29d2  jmp     short loc_1800A29E1
0x1800a29d4  mov     r12d, [rbp+57h+arg_8]
0x1800a29d8  mov     r15d, 1
0x1800a29de  xor     r13d, r13d
0x1800a29e1  lea     rdx, ?gpServerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gpServerLock
0x1800a29e8  lea     rcx, [rbp+57h+var_50]
0x1800a29ec  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x1800a29f1  mov     rcx, cs:?gpServerOidPList@@3PEAVCServerOidPList@@EA; this
0x1800a29f8  lea     rdx, [rbp+57h+arg_0]; struct CTime *
0x1800a29fc  call    ?PeekMin@CPList@@QEAAHAEAVCTime@@@Z; CPList::PeekMin(CTime &)
0x1800a2a01  test    eax, eax
0x1800a2a03  jz      short loc_1800A2A41
0x1800a2a05  lea     rcx, dword_18014F0F0
0x1800a2a0c  call    ??BCInterlockedInteger@@QEAAJXZ; CInterlockedInteger::operator long(void)
0x1800a2a11  imul    ecx, eax, 2710h
0x1800a2a17  sub     ecx, edi
0x1800a2a19  mov     edi, dword ptr [rbp+57h+arg_0]
0x1800a2a1c  add     ecx, edi
0x1800a2a1e  jns     short loc_1800A2A28
0x1800a2a20  mov     r15d, 1
0x1800a2a26  jmp     short loc_1800A2A41
0x1800a2a28  lea     rcx, dword_18014F0F0
0x1800a2a2f  call    ??BCInterlockedInteger@@QEAAJXZ; CInterlockedInteger::operator long(void)
0x1800a2a34  imul    edx, eax, 4E20h
0x1800a2a3a  add     edx, edi
0x1800a2a3c  cmp     edx, ebx
0x1800a2a3e  cmovs   ebx, edx
0x1800a2a41  lea     rcx, [rbp+57h+var_50]; this
0x1800a2a45  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x1800a2a4a  test    r15d, r15d
0x1800a2a4d  jz      short loc_1800A2A94
0x1800a2a4f  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x1800a2a56  jz      short loc_1800A2A8F
0x1800a2a58  mov     r9d, 3
0x1800a2a5e  mov     ecx, r9d
0x1800a2a61  call    IsWppLevelEnabled
0x1800a2a66  test    al, al
0x1800a2a68  jz      short loc_1800A2A8F
0x1800a2a6a  lea     rax, aCreatingAdditi; "Creating additional task thread, we're "...
0x1800a2a71  mov     r8d, 16Fh
0x1800a2a77  lea     rdx, aObjectexporter; "ObjectExporterWorkerThread"
0x1800a2a7e  mov     [rsp+0E0h+var_C0], rax
0x1800a2a83  lea     rcx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x1800a2a8a  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x1800a2a8f  call    ?TryToCreateNewTaskThread@@YAXXZ; TryToCreateNewTaskThread(void)
0x1800a2a94  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x1800a2a9b  jz      loc_1800A2B5D
0x1800a2aa1  mov     ecx, 4
0x1800a2aa6  call    IsWppLevelEnabled
0x1800a2aab  test    al, al
0x1800a2aad  jz      loc_1800A2B5D
0x1800a2ab3  mov     eax, cs:dword_18014F0F0
0x1800a2ab9  lea     r8, aObjectexporter; "ObjectExporterWorkerThread"
0x1800a2ac0  mov     [rsp+0E0h+var_70], eax
0x1800a2ac4  lea     rdx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x1800a2acb  mov     rax, cs:?gpProcessList@@3PEAVCBList@@EA; CBList * gpProcessList
0x1800a2ad2  mov     r9d, 18Ch
0x1800a2ad8  mov     ecx, [rax+4]
0x1800a2adb  mov     rax, cs:?gpMidTable@@3PEAVCHashTable@ObjexHashTable@@EA; ObjexHashTable::CHashTable * gpMidTable
0x1800a2ae2  mov     [rsp+0E0h+var_78], ecx
0x1800a2ae6  mov     ecx, [rax+4]
0x1800a2ae9  mov     rax, cs:?gpClientSetTable@@3PEAVCHashTable@ObjexHashTable@@EA; ObjexHashTable::CHashTable * gpClientSetTable
0x1800a2af0  mov     [rsp+0E0h+var_80], ecx
0x1800a2af4  mov     ecx, [rax+4]
0x1800a2af7  mov     rax, cs:?gpClientOidTable@@3PEAVCHashTable@ObjexHashTable@@EA; ObjexHashTable::CHashTable * gpClientOidTable
0x1800a2afe  mov     [rsp+0E0h+var_88], ecx
0x1800a2b02  mov     ecx, [rax+4]
0x1800a2b05  mov     rax, cs:?gpClientOxidTable@@3PEAVCHashTable@ObjexHashTable@@EA; ObjexHashTable::CHashTable * gpClientOxidTable
0x1800a2b0c  mov     [rsp+0E0h+var_90], ecx
0x1800a2b10  mov     ecx, [rax+4]
0x1800a2b13  mov     rax, cs:?gpServerSetTable@@3PEAVCServerSetTable@@EA; CServerSetTable * gpServerSetTable
0x1800a2b1a  mov     [rsp+0E0h+var_98], ecx
0x1800a2b1e  mov     ecx, [rax+0Ch]
0x1800a2b21  mov     rax, cs:?gpServerOidTable@@3PEAVCHashTable@ObjexHashTable@@EA; ObjexHashTable::CHashTable * gpServerOidTable
0x1800a2b28  mov     [rsp+0E0h+var_A0], ecx
0x1800a2b2c  mov     ecx, [rax+4]
0x1800a2b2f  mov     rax, cs:?gpServerOxidTable@@3PEAVCHashTable@ObjexHashTable@@EA; ObjexHashTable::CHashTable * gpServerOxidTable
0x1800a2b36  mov     [rsp+0E0h+var_A8], ecx
0x1800a2b3a  mov     ecx, [rax+4]
0x1800a2b3d  lea     rax, aServeroxidsDSe; "ServerOXIDs:%d ServerOIDs:%d ServerSets"...
0x1800a2b44  mov     dword ptr [rsp+0E0h+var_B0], ecx
0x1800a2b48  or      ecx, 0FFFFFFFFh
0x1800a2b4b  mov     [rsp+0E0h+var_B8], rax
0x1800a2b50  mov     dword ptr [rsp+0E0h+var_C0], 4
0x1800a2b58  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800a2b5d  add     ebx, 3E8h
0x1800a2b63  mov     eax, ebx
0x1800a2b65  mov     [rbp+57h+arg_8], ebx
0x1800a2b68  sub     eax, esi
0x1800a2b6a  cmp     eax, 7918h
0x1800a2b6f  jb      short loc_1800A2B7E
0x1800a2b71  call    ?TryToFlushIdleOrTooOldElements@CRemoteMachineList@@QEAAXXZ; CRemoteMachineList::TryToFlushIdleOrTooOldElements(void)
0x1800a2b76  call    cs:__imp_GetTickCount
0x1800a2b7c  mov     esi, eax
0x1800a2b7e  call    ?CleanUpLeakedStateObjects@@YAXXZ; CleanUpLeakedStateObjects(void)
0x1800a2b83  call    ?AnalyzeAndReportResourceMetrics@@YAXXZ; AnalyzeAndReportResourceMetrics(void)
0x1800a2b88  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x1800a2b8f  mov     edi, 3
0x1800a2b94  jz      short loc_1800A2BCD
0x1800a2b96  mov     ecx, edi
0x1800a2b98  call    IsWppLevelEnabled
0x1800a2b9d  test    al, al
0x1800a2b9f  jz      short loc_1800A2BCD
0x1800a2ba1  lea     rax, aWorkerThreadWa; "Worker thread waiting until %#x"
0x1800a2ba8  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x1800a2bac  mov     r9d, edi
0x1800a2baf  mov     [rsp+0E0h+var_C0], rax
0x1800a2bb4  mov     r8d, 19Dh
0x1800a2bba  lea     rdx, aObjectexporter; "ObjectExporterWorkerThread"
0x1800a2bc1  lea     rcx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x1800a2bc8  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x1800a2bcd  call    cs:__imp_GetCurrentThreadId
0x1800a2bd3  mov     ecx, 3EDh; this
0x1800a2bd8  mov     r8d, ebx
0x1800a2bdb  mov     edx, eax; unsigned __int16
0x1800a2bdd  call    ?Log@RpcssTestLog@@YAXGZZ; RpcssTestLog::Log(ushort,...)
0x1800a2be2  mov     r8, cs:gWorkerThreadWaitEvent; void *
0x1800a2be9  lea     rcx, [rbp+57h+arg_8]; this
0x1800a2bed  mov     rdx, cs:gWorkerThreadTimer; struct _TP_TIMER *
0x1800a2bf4  call    ?Sleep@CTime@@QEBAXPEAU_TP_TIMER@@PEAX@Z; CTime::Sleep(_TP_TIMER *,void *)
0x1800a2bf9  inc     r12d
0x1800a2bfc  jmp     loc_1800A2779
```
