# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000ec50`
- end: `0x18000ed5d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000de1c`
- `0x18000df18`
- `0x18000ec50`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ecf1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ecf1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ecda`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ecda`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ed47`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ed47`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000eca0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000eca0`

## string_xrefs

- `0x18000ecd3`: `ntdll.dll`
- `0x18000ece7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_18001C0E0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18001C0E0 = 0;
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
               &qword_18001C0E0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&stru_18001C098,
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
0x18000ec50  mov     [rsp+arg_0], rbx
0x18000ec55  mov     [rsp+arg_8], rsi
0x18000ec5a  push    rdi
0x18000ec5b  sub     rsp, 30h
0x18000ec5f  mov     rdi, r8
0x18000ec62  mov     rsi, rdx
0x18000ec65  mov     rbx, rcx
0x18000ec68  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000ec6c  jnz     short loc_18000EC85
0x18000ec6e  mov     r8, rdx; void (*)(void *)
0x18000ec71  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000ec74  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000ec7b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000ec80  jmp     loc_18000ED4D
0x18000ec85  mov     qword ptr [rcx], 0
0x18000ec8c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000ec93  jz      loc_18000ED4D
0x18000ec99  lea     rcx, SRWLock; SRWLock
0x18000eca0  call    cs:__imp_AcquireSRWLockExclusive
0x18000eca6  cmp     cs:qword_18001C0E0, 0
0x18000ecae  jnz     short loc_18000ED2B
0x18000ecb0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000ecb7  mov     cs:qword_18001C0E0, 0
0x18000ecc2  test    rax, rax
0x18000ecc5  jnz     short loc_18000ED0A
0x18000ecc7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ecce  test    rax, rax
0x18000ecd1  jnz     short loc_18000ECE7
0x18000ecd3  lea     rcx, ModuleName; "ntdll.dll"
0x18000ecda  call    cs:__imp_GetModuleHandleW
0x18000ece0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ece7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000ecee  mov     rcx, rax; hModule
0x18000ecf1  call    cs:__imp_GetProcAddress
0x18000ecf7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000ecfe  test    rax, rax
0x18000ed01  jnz     short loc_18000ED0A
0x18000ed03  mov     eax, 0C0000139h
0x18000ed08  jmp     short loc_18000ED27
0x18000ed0a  lea     r9, qword_18001C0E0
0x18000ed11  xor     r8d, r8d
0x18000ed14  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000ed1b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000ed22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed27  test    eax, eax
0x18000ed29  jnz     short loc_18000ED40
0x18000ed2b  mov     r9, rdi; void *
0x18000ed2e  lea     rcx, stru_18001C098; this
0x18000ed35  mov     r8, rsi; void (*)(void *)
0x18000ed38  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000ed3b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000ed40  lea     rcx, SRWLock; SRWLock
0x18000ed47  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ed4d  mov     rbx, [rsp+38h+arg_0]
0x18000ed52  mov     rsi, [rsp+38h+arg_8]
0x18000ed57  add     rsp, 30h
0x18000ed5b  pop     rdi
0x18000ed5c  retn
```
