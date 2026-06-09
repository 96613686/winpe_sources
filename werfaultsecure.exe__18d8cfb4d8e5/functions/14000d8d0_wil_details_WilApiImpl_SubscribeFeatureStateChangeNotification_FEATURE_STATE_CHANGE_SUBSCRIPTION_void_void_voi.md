# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14000d8d0`
- end: `0x14000d9dd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x14000c580`
- `0x14000c67c`
- `0x14000d8d0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000d971`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000d971`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000d95a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000d95a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000d920`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000d920`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d9c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d9c7`

## string_xrefs

- `0x14000d953`: `ntdll.dll`
- `0x14000d967`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v9; // eax

  if ( a3 == (void (*)(void *))-1LL )
  {
    wil::details::FeatureStateManager::SubscribeToUsageFlush(
      (wil::details::FeatureStateManager *)&wil::details::g_featureStateManager,
      this,
      (void (*)(void *))a2);
  }
  else
  {
    *this = 0;
    if ( wil::details::g_featureStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_14001A150 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_14001A150 = 0;
      if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification )
        goto LABEL_10;
      ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "RtlRegisterFeatureConfigurationChangeNotification");
      g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_10:
        v9 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), void *, _QWORD, __int64 *))ProcAddress)(
               _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
               &wil::details::g_featureStateManager,
               0,
               &qword_14001A150);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&SRWLock);
    }
  }
}

```

## disassembly

```asm
0x14000d8d0  mov     [rsp+arg_0], rbx
0x14000d8d5  mov     [rsp+arg_8], rsi
0x14000d8da  push    rdi
0x14000d8db  sub     rsp, 30h
0x14000d8df  mov     rdi, r8
0x14000d8e2  mov     rsi, rdx
0x14000d8e5  mov     rbx, rcx
0x14000d8e8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14000d8ec  jnz     short loc_14000D905
0x14000d8ee  mov     r8, rdx; void (*)(void *)
0x14000d8f1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000d8f4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000d8fb  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x14000d900  jmp     loc_14000D9CD
0x14000d905  mov     qword ptr [rcx], 0
0x14000d90c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000d913  jz      loc_14000D9CD
0x14000d919  lea     rcx, SRWLock; SRWLock
0x14000d920  call    cs:__imp_AcquireSRWLockExclusive
0x14000d926  cmp     cs:qword_14001A150, 0
0x14000d92e  jnz     short loc_14000D9AB
0x14000d930  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000d937  mov     cs:qword_14001A150, 0
0x14000d942  test    rax, rax
0x14000d945  jnz     short loc_14000D98A
0x14000d947  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000d94e  test    rax, rax
0x14000d951  jnz     short loc_14000D967
0x14000d953  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x14000d95a  call    cs:__imp_GetModuleHandleW
0x14000d960  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000d967  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000d96e  mov     rcx, rax; hModule
0x14000d971  call    cs:__imp_GetProcAddress
0x14000d977  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000d97e  test    rax, rax
0x14000d981  jnz     short loc_14000D98A
0x14000d983  mov     eax, 0C0000139h
0x14000d988  jmp     short loc_14000D9A7
0x14000d98a  lea     r9, qword_14001A150
0x14000d991  xor     r8d, r8d
0x14000d994  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000d99b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x14000d9a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d9a7  test    eax, eax
0x14000d9a9  jnz     short loc_14000D9C0
0x14000d9ab  mov     r9, rdi; void *
0x14000d9ae  lea     rcx, CriticalSection; this
0x14000d9b5  mov     r8, rsi; void (*)(void *)
0x14000d9b8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000d9bb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x14000d9c0  lea     rcx, SRWLock; SRWLock
0x14000d9c7  call    cs:__imp_ReleaseSRWLockExclusive
0x14000d9cd  mov     rbx, [rsp+38h+arg_0]
0x14000d9d2  mov     rsi, [rsp+38h+arg_8]
0x14000d9d7  add     rsp, 30h
0x14000d9db  pop     rdi
0x14000d9dc  retn
```
