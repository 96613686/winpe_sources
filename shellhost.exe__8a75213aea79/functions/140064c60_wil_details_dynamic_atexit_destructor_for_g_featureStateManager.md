# wil::details::_dynamic_atexit_destructor_for__g_featureStateManager__

- ea: `0x140064c60`
- end: `0x140064e42`
- name: `wil::details::_dynamic_atexit_destructor_for__g_featureStateManager__`
- size: `482`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140008ed0`
- `0x1400491bc`
- `0x14004a0f8`
- `0x14004b6b0`
- `0x140064c60`
- `0x140067010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140064d9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140064d9a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140064d6d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140064de2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140064d6d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140064de2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140064d07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140064d52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140064dc7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140064d07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140064d52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140064dc7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140064d15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140064d60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140064dd5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140064d15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140064d60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140064dd5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140064cba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140064ce7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140064cba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140064ce7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064ca8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064cd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064ca8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064cd5`

## string_xrefs

- `0x140064d93`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
  void *v13; // rcx

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    wil::details::g_featureStateManager = 0;
    v13 = qword_1400801A8;
    if ( !qword_1400801A8 )
      return;
    goto LABEL_28;
  }
  wil::details::g_featureStateManager = 0;
  v0 = pti;
  if ( pti )
  {
    LastError = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v0);
    SetLastError(LastError);
  }
  pti = 0;
  v2 = qword_1400801D0;
  if ( qword_1400801D0 )
  {
    v3 = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v2);
    SetLastError(v3);
  }
  qword_1400801D0 = 0;
  v4 = lpMem;
  lpMem = 0;
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  if ( xmmword_140080278 && qword_1400801B0 )
    wil::details_abi::SubscriptionList::Unsubscribe(
      (struct wil::srwlock *)((char *)qword_1400801B0 + 200),
      qword_1400801B0,
      xmmword_140080278);
  v6 = (void *)*((_QWORD *)&xmmword_140080268 + 1);
  *((_QWORD *)&xmmword_140080268 + 1) = 0;
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
  DeleteCriticalSection(&stru_140080230);
  v8 = qword_140080228;
  if ( qword_140080228 )
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
  v11 = (void *)*((_QWORD *)&xmmword_140080218 + 1);
  *((_QWORD *)&xmmword_140080218 + 1) = 0;
  if ( v11 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v11);
  }
  DeleteCriticalSection(&CriticalSection);
  if ( qword_1400801D0 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(qword_1400801D0);
  if ( pti )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(pti);
  v13 = qword_1400801A8;
  if ( qword_1400801A8 )
LABEL_28:
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v13);
}

```

## disassembly

```asm
0x140064c60  mov     [rsp+arg_0], rbx
0x140064c65  mov     [rsp+arg_8], rsi
0x140064c6a  push    rdi
0x140064c6b  sub     rsp, 20h
0x140064c6f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140064c76  jnz     loc_140064E19
0x140064c7c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140064c83  test    rax, rax
0x140064c86  jz      short loc_140064C95
0x140064c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140064c8d  test    al, al
0x140064c8f  jnz     loc_140064E19
0x140064c95  mov     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140064c9c  mov     rdi, cs:pti
0x140064ca3  test    rdi, rdi
0x140064ca6  jz      short loc_140064CC0
0x140064ca8  call    cs:__imp_GetLastError
0x140064cae  mov     ebx, eax
0x140064cb0  mov     rcx, rdi; pti
0x140064cb3  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x140064cb8  mov     ecx, ebx; dwErrCode
0x140064cba  call    cs:__imp_SetLastError
0x140064cc0  xor     esi, esi
0x140064cc2  mov     cs:pti, rsi
0x140064cc9  mov     rdi, cs:qword_1400801D0
0x140064cd0  test    rdi, rdi
0x140064cd3  jz      short loc_140064CED
0x140064cd5  call    cs:__imp_GetLastError
0x140064cdb  mov     ebx, eax
0x140064cdd  mov     rcx, rdi; pti
0x140064ce0  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x140064ce5  mov     ecx, ebx; dwErrCode
0x140064ce7  call    cs:__imp_SetLastError
0x140064ced  mov     cs:qword_1400801D0, rsi
0x140064cf4  mov     rbx, cs:lpMem
0x140064cfb  mov     cs:lpMem, rsi
0x140064d02  test    rbx, rbx
0x140064d05  jz      short loc_140064D1B
0x140064d07  call    cs:__imp_GetProcessHeap
0x140064d0d  mov     rcx, rax; hHeap
0x140064d10  mov     r8, rbx; lpMem
0x140064d13  xor     edx, edx; dwFlags
0x140064d15  call    cs:__imp_HeapFree
0x140064d1b  mov     r8, qword ptr cs:xmmword_140080278; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x140064d22  test    r8, r8
0x140064d25  jz      short loc_140064D3F
0x140064d27  mov     rdx, cs:qword_1400801B0; struct wil::srwlock *
0x140064d2e  test    rdx, rdx
0x140064d31  jz      short loc_140064D3F
0x140064d33  lea     rcx, [rdx+0C8h]; this
0x140064d3a  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x140064d3f  mov     rbx, qword ptr cs:xmmword_140080268+8
0x140064d46  mov     qword ptr cs:xmmword_140080268+8, rsi
0x140064d4d  test    rbx, rbx
0x140064d50  jz      short loc_140064D66
0x140064d52  call    cs:__imp_GetProcessHeap
0x140064d58  mov     rcx, rax; hHeap
0x140064d5b  mov     r8, rbx; lpMem
0x140064d5e  xor     edx, edx; dwFlags
0x140064d60  call    cs:__imp_HeapFree
0x140064d66  lea     rcx, stru_140080230; lpCriticalSection
0x140064d6d  call    cs:__imp_DeleteCriticalSection
0x140064d73  mov     rbx, cs:qword_140080228
0x140064d7a  test    rbx, rbx
0x140064d7d  jz      short loc_140064DB4
0x140064d7f  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x140064d86  test    rax, rax
0x140064d89  jnz     short loc_140064DAC
0x140064d8b  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x140064d90  mov     rcx, rax; hModule
0x140064d93  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x140064d9a  call    cs:__imp_GetProcAddress
0x140064da0  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x140064da7  test    rax, rax
0x140064daa  jz      short loc_140064DB4
0x140064dac  mov     rcx, rbx
0x140064daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140064db4  mov     rbx, qword ptr cs:xmmword_140080218+8
0x140064dbb  mov     qword ptr cs:xmmword_140080218+8, rsi
0x140064dc2  test    rbx, rbx
0x140064dc5  jz      short loc_140064DDB
0x140064dc7  call    cs:__imp_GetProcessHeap
0x140064dcd  mov     rcx, rax; hHeap
0x140064dd0  mov     r8, rbx; lpMem
0x140064dd3  xor     edx, edx; dwFlags
0x140064dd5  call    cs:__imp_HeapFree
0x140064ddb  lea     rcx, CriticalSection; lpCriticalSection
0x140064de2  call    cs:__imp_DeleteCriticalSection
0x140064de8  mov     rcx, cs:qword_1400801D0; pti
0x140064def  test    rcx, rcx
0x140064df2  jz      short loc_140064DF9
0x140064df4  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x140064df9  mov     rcx, cs:pti; pti
0x140064e00  test    rcx, rcx
0x140064e03  jz      short loc_140064E0B
0x140064e05  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x140064e0a  nop
0x140064e0b  mov     rcx, cs:qword_1400801A8
0x140064e12  test    rcx, rcx
0x140064e15  jnz     short loc_140064E2C
0x140064e17  jmp     short loc_140064E32
0x140064e19  mov     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140064e20  mov     rcx, cs:qword_1400801A8; lpMem
0x140064e27  test    rcx, rcx
0x140064e2a  jz      short loc_140064E32
0x140064e2c  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140064e31  nop
0x140064e32  mov     rbx, [rsp+28h+arg_0]
0x140064e37  mov     rsi, [rsp+28h+arg_8]
0x140064e3c  add     rsp, 20h
0x140064e40  pop     rdi
0x140064e41  retn
```
