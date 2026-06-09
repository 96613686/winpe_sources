# wil::details::_dynamic_atexit_destructor_for__g_featureStateManager__

- ea: `0x1800315a0`
- end: `0x1800317c8`
- name: `wil::details::_dynamic_atexit_destructor_for__g_featureStateManager__`
- size: `552`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002b10`
- `0x1800037b0`
- `0x18000462c`
- `0x18000b664`
- `0x1800315a0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800316da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800316da`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800316ad`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031722`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800316ad`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031722`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031647`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031692`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031707`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031647`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031692`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031707`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031655`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800316a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031715`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031655`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800316a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800315e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031615`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800315e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031615`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800315fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031627`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800315fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031627`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003174d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180031781`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003174d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180031781`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180031756`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003178a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180031756`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003178a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003173f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180031773`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003173f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180031773`

## string_xrefs

- `0x1800316d3`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void wil::details::_dynamic_atexit_destructor_for__g_featureStateManager__()
{
  struct _TP_TIMER *v0; // rdi
  DWORD LastError; // ebx
  struct _TP_TIMER *v2; // rdi
  DWORD v3; // ebx
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rbx
  HANDLE v7; // rax
  __int64 v8; // rbx
  FARPROC ProcAddress; // rax
  HMODULE NtDllModuleHandle; // rax
  void *v11; // rbx
  HANDLE v12; // rax
  struct _TP_TIMER *v13; // rbx
  struct _TP_TIMER *v14; // rbx
  void *v15; // rcx

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    wil::details::g_featureStateManager = 0;
    v15 = qword_180041380;
    if ( !qword_180041380 )
      return;
    goto LABEL_28;
  }
  wil::details::g_featureStateManager = 0;
  v0 = qword_1800413A0;
  if ( qword_1800413A0 )
  {
    LastError = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v0);
    SetLastError(LastError);
  }
  qword_1800413A0 = 0;
  v2 = qword_1800413A8;
  if ( qword_1800413A8 )
  {
    v3 = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v2);
    SetLastError(v3);
  }
  qword_1800413A8 = 0;
  v4 = qword_180041470;
  qword_180041470 = 0;
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  if ( xmmword_180041450 && qword_180041388 )
    wil::details_abi::SubscriptionList::Unsubscribe(
      (struct wil::srwlock *)((char *)qword_180041388 + 200),
      qword_180041388,
      xmmword_180041450);
  v6 = (void *)*((_QWORD *)&xmmword_180041440 + 1);
  *((_QWORD *)&xmmword_180041440 + 1) = 0;
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
  DeleteCriticalSection(&stru_180041408);
  v8 = qword_180041400;
  if ( qword_180041400 )
  {
    ProcAddress = (FARPROC)g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification;
    if ( g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
      || (NtDllModuleHandle = wil_details_GetNtDllModuleHandle(),
          ProcAddress = GetProcAddress(NtDllModuleHandle, "RtlUnregisterFeatureConfigurationChangeNotification"),
          (g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification = (__int64)ProcAddress) != 0) )
    {
      ((void (__fastcall *)(__int64))ProcAddress)(v8);
    }
  }
  v11 = (void *)*((_QWORD *)&xmmword_1800413F0 + 1);
  *((_QWORD *)&xmmword_1800413F0 + 1) = 0;
  if ( v11 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v11);
  }
  DeleteCriticalSection(&CriticalSection);
  v13 = qword_1800413A8;
  if ( qword_1800413A8 )
  {
    SetThreadpoolTimer(qword_1800413A8, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v13, 1);
    CloseThreadpoolTimer(v13);
  }
  v14 = qword_1800413A0;
  if ( qword_1800413A0 )
  {
    SetThreadpoolTimer(qword_1800413A0, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v14, 1);
    CloseThreadpoolTimer(v14);
  }
  v15 = qword_180041380;
  if ( qword_180041380 )
LABEL_28:
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v15);
}

```

## disassembly

```asm
0x1800315a0  mov     [rsp+arg_0], rbx
0x1800315a5  mov     [rsp+arg_8], rsi
0x1800315aa  push    rdi
0x1800315ab  sub     rsp, 20h
0x1800315af  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800315b6  jnz     loc_18003179F
0x1800315bc  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800315c3  test    rax, rax
0x1800315c6  jz      short loc_1800315D5
0x1800315c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800315cd  test    al, al
0x1800315cf  jnz     loc_18003179F
0x1800315d5  mov     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800315dc  mov     rdi, cs:qword_1800413A0
0x1800315e3  test    rdi, rdi
0x1800315e6  jz      short loc_180031600
0x1800315e8  call    cs:__imp_GetLastError
0x1800315ee  mov     ebx, eax
0x1800315f0  mov     rcx, rdi; pti
0x1800315f3  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800315f8  mov     ecx, ebx; dwErrCode
0x1800315fa  call    cs:__imp_SetLastError
0x180031600  xor     esi, esi
0x180031602  mov     cs:qword_1800413A0, rsi
0x180031609  mov     rdi, cs:qword_1800413A8
0x180031610  test    rdi, rdi
0x180031613  jz      short loc_18003162D
0x180031615  call    cs:__imp_GetLastError
0x18003161b  mov     ebx, eax
0x18003161d  mov     rcx, rdi; pti
0x180031620  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180031625  mov     ecx, ebx; dwErrCode
0x180031627  call    cs:__imp_SetLastError
0x18003162d  mov     cs:qword_1800413A8, rsi
0x180031634  mov     rbx, cs:qword_180041470
0x18003163b  mov     cs:qword_180041470, rsi
0x180031642  test    rbx, rbx
0x180031645  jz      short loc_18003165B
0x180031647  call    cs:__imp_GetProcessHeap
0x18003164d  mov     rcx, rax; hHeap
0x180031650  mov     r8, rbx; lpMem
0x180031653  xor     edx, edx; dwFlags
0x180031655  call    cs:__imp_HeapFree
0x18003165b  mov     r8, qword ptr cs:xmmword_180041450; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180031662  test    r8, r8
0x180031665  jz      short loc_18003167F
0x180031667  mov     rdx, cs:qword_180041388; struct wil::srwlock *
0x18003166e  test    rdx, rdx
0x180031671  jz      short loc_18003167F
0x180031673  lea     rcx, [rdx+0C8h]; this
0x18003167a  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18003167f  mov     rbx, qword ptr cs:xmmword_180041440+8
0x180031686  mov     qword ptr cs:xmmword_180041440+8, rsi
0x18003168d  test    rbx, rbx
0x180031690  jz      short loc_1800316A6
0x180031692  call    cs:__imp_GetProcessHeap
0x180031698  mov     rcx, rax; hHeap
0x18003169b  mov     r8, rbx; lpMem
0x18003169e  xor     edx, edx; dwFlags
0x1800316a0  call    cs:__imp_HeapFree
0x1800316a6  lea     rcx, stru_180041408; lpCriticalSection
0x1800316ad  call    cs:__imp_DeleteCriticalSection
0x1800316b3  mov     rbx, cs:qword_180041400
0x1800316ba  test    rbx, rbx
0x1800316bd  jz      short loc_1800316F4
0x1800316bf  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x1800316c6  test    rax, rax
0x1800316c9  jnz     short loc_1800316EC
0x1800316cb  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1800316d0  mov     rcx, rax; hModule
0x1800316d3  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x1800316da  call    cs:__imp_GetProcAddress
0x1800316e0  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x1800316e7  test    rax, rax
0x1800316ea  jz      short loc_1800316F4
0x1800316ec  mov     rcx, rbx
0x1800316ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800316f4  mov     rbx, qword ptr cs:xmmword_1800413F0+8
0x1800316fb  mov     qword ptr cs:xmmword_1800413F0+8, rsi
0x180031702  test    rbx, rbx
0x180031705  jz      short loc_18003171B
0x180031707  call    cs:__imp_GetProcessHeap
0x18003170d  mov     rcx, rax; hHeap
0x180031710  mov     r8, rbx; lpMem
0x180031713  xor     edx, edx; dwFlags
0x180031715  call    cs:__imp_HeapFree
0x18003171b  lea     rcx, CriticalSection; lpCriticalSection
0x180031722  call    cs:__imp_DeleteCriticalSection
0x180031728  mov     rbx, cs:qword_1800413A8
0x18003172f  test    rbx, rbx
0x180031732  jz      short loc_18003175C
0x180031734  xor     r9d, r9d; msWindowLength
0x180031737  xor     r8d, r8d; msPeriod
0x18003173a  xor     edx, edx; pftDueTime
0x18003173c  mov     rcx, rbx; pti
0x18003173f  call    cs:__imp_SetThreadpoolTimer
0x180031745  mov     edx, 1; fCancelPendingCallbacks
0x18003174a  mov     rcx, rbx; pti
0x18003174d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180031753  mov     rcx, rbx; pti
0x180031756  call    cs:__imp_CloseThreadpoolTimer
0x18003175c  mov     rbx, cs:qword_1800413A0
0x180031763  test    rbx, rbx
0x180031766  jz      short loc_180031791
0x180031768  xor     r9d, r9d; msWindowLength
0x18003176b  xor     r8d, r8d; msPeriod
0x18003176e  xor     edx, edx; pftDueTime
0x180031770  mov     rcx, rbx; pti
0x180031773  call    cs:__imp_SetThreadpoolTimer
0x180031779  mov     edx, 1; fCancelPendingCallbacks
0x18003177e  mov     rcx, rbx; pti
0x180031781  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180031787  mov     rcx, rbx; pti
0x18003178a  call    cs:__imp_CloseThreadpoolTimer
0x180031790  nop
0x180031791  mov     rcx, cs:qword_180041380
0x180031798  test    rcx, rcx
0x18003179b  jnz     short loc_1800317B2
0x18003179d  jmp     short loc_1800317B8
0x18003179f  mov     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800317a6  mov     rcx, cs:qword_180041380; lpMem
0x1800317ad  test    rcx, rcx
0x1800317b0  jz      short loc_1800317B8
0x1800317b2  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800317b7  nop
0x1800317b8  mov     rbx, [rsp+28h+arg_0]
0x1800317bd  mov     rsi, [rsp+28h+arg_8]
0x1800317c2  add     rsp, 20h
0x1800317c6  pop     rdi
0x1800317c7  retn
```
