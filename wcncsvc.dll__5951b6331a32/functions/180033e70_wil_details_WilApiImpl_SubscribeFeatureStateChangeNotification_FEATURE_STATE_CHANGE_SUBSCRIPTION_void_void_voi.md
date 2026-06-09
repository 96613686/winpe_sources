# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180033e70`
- end: `0x180033f7d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180033364`
- `0x180033460`
- `0x180033e70`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033f67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033f67`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033ec0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033ec0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033f11`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033f11`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180033efa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180033efa`

## string_xrefs

- `0x180033ef3`: `ntdll.dll`
- `0x180033f07`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180074118);
      if ( qword_180074188 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180074188 = 0;
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
        v9 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), void *, _QWORD, __int64 *))ProcAddress)(
               _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
               &wil::details::g_featureStateManager,
               0,
               &qword_180074188);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180074118);
    }
  }
}

```

## disassembly

```asm
0x180033e70  mov     [rsp+arg_0], rbx
0x180033e75  mov     [rsp+arg_8], rsi
0x180033e7a  push    rdi
0x180033e7b  sub     rsp, 30h
0x180033e7f  mov     rdi, r8
0x180033e82  mov     rsi, rdx
0x180033e85  mov     rbx, rcx
0x180033e88  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180033e8c  jnz     short loc_180033EA5
0x180033e8e  mov     r8, rdx; void (*)(void *)
0x180033e91  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180033e94  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180033e9b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180033ea0  jmp     loc_180033F6D
0x180033ea5  mov     qword ptr [rcx], 0
0x180033eac  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180033eb3  jz      loc_180033F6D
0x180033eb9  lea     rcx, stru_180074118; SRWLock
0x180033ec0  call    cs:__imp_AcquireSRWLockExclusive
0x180033ec6  cmp     cs:qword_180074188, 0
0x180033ece  jnz     short loc_180033F4B
0x180033ed0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180033ed7  mov     cs:qword_180074188, 0
0x180033ee2  test    rax, rax
0x180033ee5  jnz     short loc_180033F2A
0x180033ee7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180033eee  test    rax, rax
0x180033ef1  jnz     short loc_180033F07
0x180033ef3  lea     rcx, ModuleName; "ntdll.dll"
0x180033efa  call    cs:__imp_GetModuleHandleW
0x180033f00  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180033f07  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180033f0e  mov     rcx, rax; hModule
0x180033f11  call    cs:__imp_GetProcAddress
0x180033f17  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180033f1e  test    rax, rax
0x180033f21  jnz     short loc_180033F2A
0x180033f23  mov     eax, 0C0000139h
0x180033f28  jmp     short loc_180033F47
0x180033f2a  lea     r9, qword_180074188
0x180033f31  xor     r8d, r8d
0x180033f34  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180033f3b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180033f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f47  test    eax, eax
0x180033f49  jnz     short loc_180033F60
0x180033f4b  mov     r9, rdi; void *
0x180033f4e  lea     rcx, CriticalSection; this
0x180033f55  mov     r8, rsi; void (*)(void *)
0x180033f58  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180033f5b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180033f60  lea     rcx, stru_180074118; SRWLock
0x180033f67  call    cs:__imp_ReleaseSRWLockExclusive
0x180033f6d  mov     rbx, [rsp+38h+arg_0]
0x180033f72  mov     rsi, [rsp+38h+arg_8]
0x180033f77  add     rsp, 30h
0x180033f7b  pop     rdi
0x180033f7c  retn
```
