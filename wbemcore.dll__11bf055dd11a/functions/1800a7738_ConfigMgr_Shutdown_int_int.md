# ConfigMgr::Shutdown(int,int)

- ea: `0x1800a7738`
- end: `0x1800a7a8e`
- name: `?Shutdown@ConfigMgr@@SAKHH@Z`
- size: `854`
- prototype: `static unsigned int(int, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800aa190`

## callees

- `0x18000b46c`
- `0x18000e8c0`
- `0x18003717c`
- `0x18008a194`
- `0x18008a5b4`
- `0x18008da44`
- `0x1800a7738`
- `0x1800a7e84`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a79d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a79d0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800a779c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800a779c`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800a7a0e`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800a7a0e`
- `wbemcomn!??1CEventLog@@QEAA@XZ` at `0x1800a7972`
- `wbemcomn!??1CEventLog@@QEAA@XZ` at `0x1800a7972`
- `wbemcomn!?Close@CEventLog@@QEAAHXZ` at `0x1800a795d`
- `wbemcomn!?Close@CEventLog@@QEAAHXZ` at `0x1800a795d`
- `wbemcomn!?SetStr@Registry@@QEAAHPEBG0@Z` at `0x1800a77ff`
- `wbemcomn!?SetStr@Registry@@QEAAHPEBG0@Z` at `0x1800a77ff`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x1800a778a`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x1800a778a`
- `wbemcomn!?DeleteValue@Registry@@QEAAHPEBG@Z` at `0x1800a7810`
- `wbemcomn!?DeleteValue@Registry@@QEAAHPEBG@Z` at `0x1800a7821`
- `wbemcomn!?DeleteValue@Registry@@QEAAHPEBG@Z` at `0x1800a7810`
- `wbemcomn!?DeleteValue@Registry@@QEAAHPEBG@Z` at `0x1800a7821`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x1800a782c`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x1800a782c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800a797b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800a798f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800a79a3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800a79b7`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800a797b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800a798f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800a79a3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800a79b7`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x1800a776b`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x1800a776b`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1800a7891`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1800a7891`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800a78af`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800a78af`

## string_xrefs

- `0x1800a7816`: `LastServiceReady`
- `0x1800a7805`: `LastServiceStart`
- `0x1800a77f4`: `PreviousServiceShutdown`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ConfigMgr::Shutdown(unsigned int a1, int a2)
{
  struct CEventLog *v4; // rbx
  REGHANDLE v5; // rcx
  unsigned int v6; // edx
  __int64 i; // rbx
  vaArgs *v8; // rcx
  _BYTE v10[8]; // [rsp+50h] [rbp-29h] BYREF
  _BYTE v11[24]; // [rsp+58h] [rbp-21h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-9h] BYREF
  unsigned __int16 v13[24]; // [rsp+80h] [rbp+7h] BYREF

  ShutdownSubsystems(a2);
  if ( !(unsigned __int8)CWbemInstallObject::IsOffline() )
  {
    Registry::Registry((Registry *)v11, L"Software\\Microsoft\\WBEM\\CIMOM", 3u);
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    StringCchPrintfW(
      v13,
      0x18u,
      L"%d/%d/%d %d:%d:%d'%d",
      SystemTime.wYear,
      SystemTime.wMonth,
      SystemTime.wDay,
      SystemTime.wHour,
      SystemTime.wMinute,
      SystemTime.wSecond,
      SystemTime.wMilliseconds);
    Registry::SetStr((Registry *)v11, L"PreviousServiceShutdown", v13);
    Registry::DeleteValue((Registry *)v11, L"LastServiceStart");
    Registry::DeleteValue((Registry *)v11, L"LastServiceReady");
    Registry::~Registry((Registry *)v11);
  }
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids, a1, 0);
    }
    if ( g_pAsyncSvcQueue )
    {
      CCoreQueue::Shutdown(g_pAsyncSvcQueue, 0);
      CInCritSec::CInCritSec((CInCritSec *)v10, (struct _RTL_CRITICAL_SECTION *)ConfigMgr::g_csEss);
      CCoreQueue::Release(g_pAsyncSvcQueue);
      g_pAsyncSvcQueue = 0;
      CInCritSec::~CInCritSec((CInCritSec *)v10);
    }
    if ( g_pContextFac )
    {
      ((void (__fastcall *)(struct IClassFactory *, _QWORD))g_pContextFac->lpVtbl->LockServer)(g_pContextFac, 0);
      ((void (__fastcall *)(struct IClassFactory *))g_pContextFac->lpVtbl->Release)(g_pContextFac);
      g_pContextFac = 0;
    }
    if ( g_pPathFac )
    {
      ((void (__fastcall *)(struct IClassFactory *, _QWORD))g_pPathFac->lpVtbl->LockServer)(g_pPathFac, 0);
      ((void (__fastcall *)(struct IClassFactory *))g_pPathFac->lpVtbl->Release)(g_pPathFac);
      g_pPathFac = 0;
    }
    if ( g_pQueryFact )
    {
      ((void (__fastcall *)(struct IClassFactory *, _QWORD))g_pQueryFact->lpVtbl->LockServer)(g_pQueryFact, 0);
      ((void (__fastcall *)(struct IClassFactory *))g_pQueryFact->lpVtbl->Release)(g_pQueryFact);
      g_pQueryFact = 0;
    }
    if ( g_pEventLog )
    {
      CEventLog::Close(g_pEventLog);
      v4 = g_pEventLog;
      if ( g_pEventLog )
      {
        CEventLog::~CEventLog(g_pEventLog);
        CWin32DefaultArena::WbemMemFree(v4);
      }
      g_pEventLog = 0;
    }
    CWin32DefaultArena::WbemMemFree(g_pDbDir);
    g_pDbDir = 0;
    CWin32DefaultArena::WbemMemFree((void *)g_pWorkDir);
    g_pWorkDir = 0;
    CWin32DefaultArena::WbemMemFree(g_pAutorecoverDir);
    g_pAutorecoverDir = 0;
    if ( g_hOpenForClients )
    {
      CloseHandle(g_hOpenForClients);
      g_hOpenForClients = 0;
    }
    if ( g_cntWinmgmtTraceLogging )
    {
      _InterlockedExchange64(&g_cntWinmgmtTraceLogging, 0);
      _InterlockedExchange64((volatile __int64 *)&g_lastTelemetryTrace, 0);
      v5 = RegHandle;
      dword_1801A0018 = 0;
      RegHandle = 0;
      EventUnregister(v5);
      for ( i = 0; i != 1000; ++i )
      {
        v8 = (vaArgs *)_InterlockedExchange64((volatile __int64 *)&(&g_WinmgmtTelemetryOperations)[i], 0);
        if ( v8 )
          vaArgs::`scalar deleting destructor'(v8, v6);
      }
    }
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800a7738  mov     [rsp-8+arg_10], rbx
0x1800a773d  mov     [rsp-8+arg_18], rsi
0x1800a7742  push    rbp
0x1800a7743  push    rdi
0x1800a7744  push    r14
0x1800a7746  lea     rbp, [rsp-47h]
0x1800a774b  sub     rsp, 0C0h
0x1800a7752  mov     rax, cs:__security_cookie
0x1800a7759  xor     rax, rsp
0x1800a775c  mov     [rbp+57h+var_20], rax
0x1800a7760  mov     ebx, edx
0x1800a7762  mov     edi, ecx
0x1800a7764  mov     ecx, edx; int
0x1800a7766  call    ?ShutdownSubsystems@@YAJH@Z; ShutdownSubsystems(int)
0x1800a776b  call    cs:__imp_?IsOffline@CWbemInstallObject@@SA_NXZ; CWbemInstallObject::IsOffline(void)
0x1800a7771  xor     esi, esi
0x1800a7773  test    al, al
0x1800a7775  jnz     loc_1800A7832
0x1800a777b  lea     r8d, [rsi+3]
0x1800a777f  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\WBEM\\CIMOM"
0x1800a7786  lea     rcx, [rbp+57h+var_78]
0x1800a778a  call    cs:__imp_??0Registry@@QEAA@PEBGK@Z; Registry::Registry(ushort const *,ulong)
0x1800a7790  nop
0x1800a7791  xorps   xmm0, xmm0
0x1800a7794  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1800a7798  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x1800a779c  call    cs:__imp_GetSystemTime
0x1800a77a2  movzx   eax, [rbp+57h+SystemTime.wMilliseconds]
0x1800a77a6  movzx   ecx, [rbp+57h+SystemTime.wSecond]
0x1800a77aa  movzx   edx, [rbp+57h+SystemTime.wMinute]
0x1800a77ae  movzx   r8d, [rbp+57h+SystemTime.wHour]
0x1800a77b3  movzx   r10d, [rbp+57h+SystemTime.wDay]
0x1800a77b8  movzx   r11d, [rbp+57h+SystemTime.wMonth]
0x1800a77bd  movzx   r9d, [rbp+57h+SystemTime.wYear]
0x1800a77c2  mov     [rsp+0D0h+var_88], eax
0x1800a77c6  mov     [rsp+0D0h+var_90], ecx
0x1800a77ca  mov     [rsp+0D0h+var_98], edx
0x1800a77ce  mov     [rsp+0D0h+var_A0], r8d
0x1800a77d3  mov     [rsp+0D0h+var_A8], r10d
0x1800a77d8  mov     [rsp+0D0h+var_B0], r11d
0x1800a77dd  lea     r8, aDDDDDDD; "%d/%d/%d %d:%d:%d'%d"
0x1800a77e4  lea     edx, [rsi+18h]; unsigned __int64
0x1800a77e7  lea     rcx, [rbp+57h+var_50]; unsigned __int16 *
0x1800a77eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a77f0  lea     r8, [rbp+57h+var_50]
0x1800a77f4  lea     rdx, aPreviousservic; "PreviousServiceShutdown"
0x1800a77fb  lea     rcx, [rbp+57h+var_78]
0x1800a77ff  call    cs:__imp_?SetStr@Registry@@QEAAHPEBG0@Z; Registry::SetStr(ushort const *,ushort const *)
0x1800a7805  lea     rdx, aLastservicesta; "LastServiceStart"
0x1800a780c  lea     rcx, [rbp+57h+var_78]
0x1800a7810  call    cs:__imp_?DeleteValue@Registry@@QEAAHPEBG@Z; Registry::DeleteValue(ushort const *)
0x1800a7816  lea     rdx, aLastservicerea; "LastServiceReady"
0x1800a781d  lea     rcx, [rbp+57h+var_78]
0x1800a7821  call    cs:__imp_?DeleteValue@Registry@@QEAAHPEBG@Z; Registry::DeleteValue(ushort const *)
0x1800a7827  nop
0x1800a7828  lea     rcx, [rbp+57h+var_78]
0x1800a782c  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x1800a7832  test    ebx, ebx
0x1800a7834  jnz     loc_1800A7A68
0x1800a783a  lea     r14, WPP_GLOBAL_Control
0x1800a7841  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7848  cmp     rcx, r14
0x1800a784b  jz      short loc_1800A7873
0x1800a784d  test    byte ptr [rcx+1Ch], 1
0x1800a7851  jz      short loc_1800A7873
0x1800a7853  cmp     byte ptr [rcx+19h], 5
0x1800a7857  jb      short loc_1800A7873
0x1800a7859  lea     edx, [rbx+65h]
0x1800a785c  mov     [rsp+0D0h+var_B0], esi
0x1800a7860  mov     r9d, edi
0x1800a7863  lea     r8, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x1800a786a  mov     rcx, [rcx+10h]
0x1800a786e  call    WPP_SF_dd
0x1800a7873  mov     rcx, cs:?g_pAsyncSvcQueue@@3PEAVCAsyncServiceQueue@@EA; this
0x1800a787a  test    rcx, rcx
0x1800a787d  jz      short loc_1800A78B5
0x1800a787f  xor     edx, edx; int
0x1800a7881  call    ?Shutdown@CCoreQueue@@QEAAXH@Z; CCoreQueue::Shutdown(int)
0x1800a7886  lea     rdx, ?g_csEss@ConfigMgr@@0VCStaticCritSec@@A; CStaticCritSec ConfigMgr::g_csEss
0x1800a788d  lea     rcx, [rbp+57h+var_80]
0x1800a7891  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x1800a7897  nop
0x1800a7898  mov     rcx, cs:?g_pAsyncSvcQueue@@3PEAVCAsyncServiceQueue@@EA; this
0x1800a789f  call    ?Release@CCoreQueue@@QEAAXXZ; CCoreQueue::Release(void)
0x1800a78a4  mov     cs:?g_pAsyncSvcQueue@@3PEAVCAsyncServiceQueue@@EA, rsi; CAsyncServiceQueue * g_pAsyncSvcQueue
0x1800a78ab  lea     rcx, [rbp+57h+var_80]
0x1800a78af  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x1800a78b5  mov     rcx, cs:?g_pContextFac@@3PEAUIClassFactory@@EA; IClassFactory * g_pContextFac
0x1800a78bc  test    rcx, rcx
0x1800a78bf  jz      short loc_1800A78E9
0x1800a78c1  mov     rax, [rcx]
0x1800a78c4  xor     edx, edx
0x1800a78c6  mov     rax, [rax+20h]
0x1800a78ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a78cf  mov     rcx, cs:?g_pContextFac@@3PEAUIClassFactory@@EA; IClassFactory * g_pContextFac
0x1800a78d6  mov     rax, [rcx]
0x1800a78d9  mov     rax, [rax+10h]
0x1800a78dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a78e2  mov     cs:?g_pContextFac@@3PEAUIClassFactory@@EA, rsi; IClassFactory * g_pContextFac
0x1800a78e9  mov     rcx, cs:?g_pPathFac@@3PEAUIClassFactory@@EA; IClassFactory * g_pPathFac
0x1800a78f0  test    rcx, rcx
0x1800a78f3  jz      short loc_1800A791D
0x1800a78f5  mov     rax, [rcx]
0x1800a78f8  xor     edx, edx
0x1800a78fa  mov     rax, [rax+20h]
0x1800a78fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7903  mov     rcx, cs:?g_pPathFac@@3PEAUIClassFactory@@EA; IClassFactory * g_pPathFac
0x1800a790a  mov     rax, [rcx]
0x1800a790d  mov     rax, [rax+10h]
0x1800a7911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7916  mov     cs:?g_pPathFac@@3PEAUIClassFactory@@EA, rsi; IClassFactory * g_pPathFac
0x1800a791d  mov     rcx, cs:?g_pQueryFact@@3PEAUIClassFactory@@EA; IClassFactory * g_pQueryFact
0x1800a7924  test    rcx, rcx
0x1800a7927  jz      short loc_1800A7951
0x1800a7929  mov     rax, [rcx]
0x1800a792c  xor     edx, edx
0x1800a792e  mov     rax, [rax+20h]
0x1800a7932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7937  mov     rcx, cs:?g_pQueryFact@@3PEAUIClassFactory@@EA; IClassFactory * g_pQueryFact
0x1800a793e  mov     rax, [rcx]
0x1800a7941  mov     rax, [rax+10h]
0x1800a7945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a794a  mov     cs:?g_pQueryFact@@3PEAUIClassFactory@@EA, rsi; IClassFactory * g_pQueryFact
0x1800a7951  mov     rcx, cs:?g_pEventLog@@3PEAVCEventLog@@EA; CEventLog * g_pEventLog
0x1800a7958  test    rcx, rcx
0x1800a795b  jz      short loc_1800A7988
0x1800a795d  call    cs:__imp_?Close@CEventLog@@QEAAHXZ; CEventLog::Close(void)
0x1800a7963  mov     rbx, cs:?g_pEventLog@@3PEAVCEventLog@@EA; CEventLog * g_pEventLog
0x1800a796a  test    rbx, rbx
0x1800a796d  jz      short loc_1800A7981
0x1800a796f  mov     rcx, rbx
0x1800a7972  call    cs:__imp_??1CEventLog@@QEAA@XZ; CEventLog::~CEventLog(void)
0x1800a7978  mov     rcx, rbx
0x1800a797b  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800a7981  mov     cs:?g_pEventLog@@3PEAVCEventLog@@EA, rsi; CEventLog * g_pEventLog
0x1800a7988  mov     rcx, cs:?g_pDbDir@@3PEAGEA; ushort * g_pDbDir
0x1800a798f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800a7995  mov     cs:?g_pDbDir@@3PEAGEA, rsi; ushort * g_pDbDir
0x1800a799c  mov     rcx, cs:?g_pWorkDir@@3PEAGEA; ushort * g_pWorkDir
0x1800a79a3  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800a79a9  mov     cs:?g_pWorkDir@@3PEAGEA, rsi; ushort * g_pWorkDir
0x1800a79b0  mov     rcx, cs:?g_pAutorecoverDir@@3PEAGEA; ushort * g_pAutorecoverDir
0x1800a79b7  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800a79bd  mov     cs:?g_pAutorecoverDir@@3PEAGEA, rsi; ushort * g_pAutorecoverDir
0x1800a79c4  mov     rcx, cs:?g_hOpenForClients@@3PEAXEA; hObject
0x1800a79cb  test    rcx, rcx
0x1800a79ce  jz      short loc_1800A79DD
0x1800a79d0  call    cs:__imp_CloseHandle
0x1800a79d6  mov     cs:?g_hOpenForClients@@3PEAXEA, rsi; void * g_hOpenForClients
0x1800a79dd  cmp     cs:?g_cntWinmgmtTraceLogging@@3_JA, rsi; __int64 g_cntWinmgmtTraceLogging
0x1800a79e4  jz      short loc_1800A7A3B
0x1800a79e6  mov     rax, rsi
0x1800a79e9  xchg    rax, cs:?g_cntWinmgmtTraceLogging@@3_JA; __int64 g_cntWinmgmtTraceLogging
0x1800a79f0  mov     rcx, rsi
0x1800a79f3  xchg    rcx, cs:?g_lastTelemetryTrace@@3_KA; unsigned __int64 g_lastTelemetryTrace
0x1800a79fa  mov     rcx, cs:RegHandle; RegHandle
0x1800a7a01  mov     cs:dword_1801A0018, esi
0x1800a7a07  mov     cs:RegHandle, rsi
0x1800a7a0e  call    cs:__imp_EventUnregister
0x1800a7a14  mov     rbx, rsi
0x1800a7a17  lea     rax, ?g_WinmgmtTelemetryOperations@@3PAPEAVvaArgs@@A; vaArgs * near * g_WinmgmtTelemetryOperations
0x1800a7a1e  mov     rcx, rsi
0x1800a7a21  xchg    rcx, [rax+rbx*8]; this
0x1800a7a25  test    rcx, rcx
0x1800a7a28  jz      short loc_1800A7A2F
0x1800a7a2a  call    ??_GvaArgs@@QEAAPEAXI@Z; vaArgs::`scalar deleting destructor'(uint)
0x1800a7a2f  inc     rbx
0x1800a7a32  cmp     rbx, 3E8h
0x1800a7a39  jnz     short loc_1800A7A17
0x1800a7a3b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7a42  cmp     rcx, r14
0x1800a7a45  jz      short loc_1800A7A68
0x1800a7a47  test    byte ptr [rcx+1Ch], 1
0x1800a7a4b  jz      short loc_1800A7A68
0x1800a7a4d  cmp     byte ptr [rcx+19h], 5
0x1800a7a51  jb      short loc_1800A7A68
0x1800a7a53  mov     edx, 66h ; 'f'
0x1800a7a58  lea     r8, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x1800a7a5f  mov     rcx, [rcx+10h]
0x1800a7a63  call    WPP_SF_
0x1800a7a68  xor     eax, eax
0x1800a7a6a  mov     rcx, [rbp+57h+var_20]
0x1800a7a6e  xor     rcx, rsp; StackCookie
0x1800a7a71  call    __security_check_cookie
0x1800a7a76  lea     r11, [rsp+0D0h+var_10]
0x1800a7a7e  mov     rbx, [r11+30h]
0x1800a7a82  mov     rsi, [r11+38h]
0x1800a7a86  mov     rsp, r11
0x1800a7a89  pop     r14
0x1800a7a8b  pop     rdi
0x1800a7a8c  pop     rbp
0x1800a7a8d  retn
```
