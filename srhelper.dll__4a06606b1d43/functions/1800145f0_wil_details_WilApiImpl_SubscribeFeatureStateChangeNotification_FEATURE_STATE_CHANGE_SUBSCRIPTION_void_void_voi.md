# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1800145f0`
- end: `0x1800146fd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180013f30`
- `0x18001402c`
- `0x1800145f0`
- `0x180016010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180014691`
- `KERNEL32!GetProcAddress` at `0x180014691`
- `KERNEL32!GetModuleHandleW` at `0x18001467a`
- `KERNEL32!GetModuleHandleW` at `0x18001467a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800146e7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800146e7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180014640`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180014640`

## string_xrefs

- `0x180014673`: `ntdll.dll`
- `0x180014687`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_18001D1F0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18001D1F0 = 0;
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
        v9 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), char *, _QWORD, __int64 *))ProcAddress)(
               _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
               &wil::details::g_featureStateManager,
               0,
               &qword_18001D1F0);
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
0x1800145f0  mov     [rsp+arg_0], rbx
0x1800145f5  mov     [rsp+arg_8], rsi
0x1800145fa  push    rdi
0x1800145fb  sub     rsp, 30h
0x1800145ff  mov     rdi, r8
0x180014602  mov     rsi, rdx
0x180014605  mov     rbx, rcx
0x180014608  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001460c  jnz     short loc_180014625
0x18001460e  mov     r8, rdx; void (*)(void *)
0x180014611  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180014614  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001461b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180014620  jmp     loc_1800146ED
0x180014625  mov     qword ptr [rcx], 0
0x18001462c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180014633  jz      loc_1800146ED
0x180014639  lea     rcx, SRWLock; SRWLock
0x180014640  call    cs:__imp_AcquireSRWLockExclusive
0x180014646  cmp     cs:qword_18001D1F0, 0
0x18001464e  jnz     short loc_1800146CB
0x180014650  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180014657  mov     cs:qword_18001D1F0, 0
0x180014662  test    rax, rax
0x180014665  jnz     short loc_1800146AA
0x180014667  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001466e  test    rax, rax
0x180014671  jnz     short loc_180014687
0x180014673  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001467a  call    cs:__imp_GetModuleHandleW
0x180014680  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014687  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001468e  mov     rcx, rax; hModule
0x180014691  call    cs:__imp_GetProcAddress
0x180014697  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001469e  test    rax, rax
0x1800146a1  jnz     short loc_1800146AA
0x1800146a3  mov     eax, 0C0000139h
0x1800146a8  jmp     short loc_1800146C7
0x1800146aa  lea     r9, qword_18001D1F0
0x1800146b1  xor     r8d, r8d
0x1800146b4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800146bb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800146c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146c7  test    eax, eax
0x1800146c9  jnz     short loc_1800146E0
0x1800146cb  mov     r9, rdi; void *
0x1800146ce  lea     rcx, CriticalSection; this
0x1800146d5  mov     r8, rsi; void (*)(void *)
0x1800146d8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800146db  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800146e0  lea     rcx, SRWLock; SRWLock
0x1800146e7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800146ed  mov     rbx, [rsp+38h+arg_0]
0x1800146f2  mov     rsi, [rsp+38h+arg_8]
0x1800146f7  add     rsp, 30h
0x1800146fb  pop     rdi
0x1800146fc  retn
```
