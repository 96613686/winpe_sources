# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000fac0`
- end: `0x18000fbcd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000f39c`
- `0x18000f4a0`
- `0x18000fac0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000fb61`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000fb61`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000fb4a`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000fb4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fbb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fbb7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fb10`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fb10`

## string_xrefs

- `0x18000fb43`: `ntdll.dll`
- `0x18000fb57`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_18002B0F0);
      if ( qword_18002B160 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18002B160 = 0;
      if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification )
        goto LABEL_10;
      ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "RtlRegisterFeatureConfigurationChangeNotification");
      g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_10:
        v9 = ((__int64 (__fastcall *)(void (__fastcall *)(__int64), char *, _QWORD, __int64 *))ProcAddress)(
               `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
               &wil::details::g_featureStateManager,
               0,
               &qword_18002B160);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&stru_18002B118,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_18002B0F0);
    }
  }
}

```

## disassembly

```asm
0x18000fac0  mov     [rsp+arg_8], rbx
0x18000fac5  mov     [rsp+arg_10], rsi
0x18000faca  push    rdi
0x18000facb  sub     rsp, 30h
0x18000facf  mov     rsi, r8
0x18000fad2  mov     rdi, rdx
0x18000fad5  mov     rbx, rcx
0x18000fad8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000fadc  jnz     short loc_18000FAF5
0x18000fade  mov     r8, rdx; void (*)(void *)
0x18000fae1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000fae4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000faeb  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000faf0  jmp     loc_18000FBBD
0x18000faf5  mov     qword ptr [rcx], 0
0x18000fafc  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000fb03  jz      loc_18000FBBD
0x18000fb09  lea     rcx, stru_18002B0F0; SRWLock
0x18000fb10  call    cs:__imp_AcquireSRWLockExclusive
0x18000fb16  cmp     cs:qword_18002B160, 0
0x18000fb1e  jnz     short loc_18000FB9B
0x18000fb20  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000fb27  mov     cs:qword_18002B160, 0
0x18000fb32  test    rax, rax
0x18000fb35  jnz     short loc_18000FB7A
0x18000fb37  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000fb3e  test    rax, rax
0x18000fb41  jnz     short loc_18000FB57
0x18000fb43  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000fb4a  call    cs:__imp_GetModuleHandleW
0x18000fb50  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000fb57  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000fb5e  mov     rcx, rax; hModule
0x18000fb61  call    cs:__imp_GetProcAddress
0x18000fb67  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000fb6e  test    rax, rax
0x18000fb71  jnz     short loc_18000FB7A
0x18000fb73  mov     eax, 0C0000139h
0x18000fb78  jmp     short loc_18000FB97
0x18000fb7a  lea     r9, qword_18002B160
0x18000fb81  xor     r8d, r8d
0x18000fb84  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000fb8b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToStateChangesUnderLock@FeatureStateManager@details@wil@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@5@PEAX@Z@SA@1@Z; `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,void *)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x18000fb92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb97  test    eax, eax
0x18000fb99  jnz     short loc_18000FBB0
0x18000fb9b  mov     r9, rsi; void *
0x18000fb9e  lea     rcx, stru_18002B118; this
0x18000fba5  mov     r8, rdi; void (*)(void *)
0x18000fba8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000fbab  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000fbb0  lea     rcx, stru_18002B0F0; SRWLock
0x18000fbb7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fbbd  mov     rbx, [rsp+38h+arg_8]
0x18000fbc2  mov     rsi, [rsp+38h+arg_10]
0x18000fbc7  add     rsp, 30h
0x18000fbcb  pop     rdi
0x18000fbcc  retn
```
