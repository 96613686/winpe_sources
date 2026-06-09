# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14000a850`
- end: `0x14000a95d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x14000a40c`
- `0x14000a508`
- `0x14000a850`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a8da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a8da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000a8f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000a8f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a947`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a947`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a8a0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a8a0`

## string_xrefs

- `0x14000a8d3`: `ntdll.dll`
- `0x14000a8e7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_1400120A0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1400120A0 = 0;
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
        v9 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), char *, _QWORD, __int64 *))ProcAddress)(
               _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
               &wil::details::g_featureStateManager,
               0,
               &qword_1400120A0);
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
0x14000a850  mov     [rsp+arg_0], rbx
0x14000a855  mov     [rsp+arg_8], rsi
0x14000a85a  push    rdi
0x14000a85b  sub     rsp, 30h
0x14000a85f  mov     rdi, r8
0x14000a862  mov     rsi, rdx
0x14000a865  mov     rbx, rcx
0x14000a868  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14000a86c  jnz     short loc_14000A885
0x14000a86e  mov     r8, rdx; void (*)(void *)
0x14000a871  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000a874  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000a87b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x14000a880  jmp     loc_14000A94D
0x14000a885  mov     qword ptr [rcx], 0
0x14000a88c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000a893  jz      loc_14000A94D
0x14000a899  lea     rcx, SRWLock; SRWLock
0x14000a8a0  call    cs:__imp_AcquireSRWLockExclusive
0x14000a8a6  cmp     cs:qword_1400120A0, 0
0x14000a8ae  jnz     short loc_14000A92B
0x14000a8b0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000a8b7  mov     cs:qword_1400120A0, 0
0x14000a8c2  test    rax, rax
0x14000a8c5  jnz     short loc_14000A90A
0x14000a8c7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a8ce  test    rax, rax
0x14000a8d1  jnz     short loc_14000A8E7
0x14000a8d3  lea     rcx, ModuleName; "ntdll.dll"
0x14000a8da  call    cs:__imp_GetModuleHandleW
0x14000a8e0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a8e7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000a8ee  mov     rcx, rax; hModule
0x14000a8f1  call    cs:__imp_GetProcAddress
0x14000a8f7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000a8fe  test    rax, rax
0x14000a901  jnz     short loc_14000A90A
0x14000a903  mov     eax, 0C0000139h
0x14000a908  jmp     short loc_14000A927
0x14000a90a  lea     r9, qword_1400120A0
0x14000a911  xor     r8d, r8d
0x14000a914  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000a91b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x14000a922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a927  test    eax, eax
0x14000a929  jnz     short loc_14000A940
0x14000a92b  mov     r9, rdi; void *
0x14000a92e  lea     rcx, CriticalSection; this
0x14000a935  mov     r8, rsi; void (*)(void *)
0x14000a938  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000a93b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x14000a940  lea     rcx, SRWLock; SRWLock
0x14000a947  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a94d  mov     rbx, [rsp+38h+arg_0]
0x14000a952  mov     rsi, [rsp+38h+arg_8]
0x14000a957  add     rsp, 30h
0x14000a95b  pop     rdi
0x14000a95c  retn
```
