# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000c0a0`
- end: `0x18000c1ad`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000b4e4`
- `0x18000b5e0`
- `0x18000c0a0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c12a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c12a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c141`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c141`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c0f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c0f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c197`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c197`

## string_xrefs

- `0x18000c123`: `ntdll.dll`
- `0x18000c137`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180023090);
      if ( qword_180023100 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180023100 = 0;
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
               &qword_180023100);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180023090);
    }
  }
}

```

## disassembly

```asm
0x18000c0a0  mov     [rsp+arg_0], rbx
0x18000c0a5  mov     [rsp+arg_8], rsi
0x18000c0aa  push    rdi
0x18000c0ab  sub     rsp, 30h
0x18000c0af  mov     rdi, r8
0x18000c0b2  mov     rsi, rdx
0x18000c0b5  mov     rbx, rcx
0x18000c0b8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000c0bc  jnz     short loc_18000C0D5
0x18000c0be  mov     r8, rdx; void (*)(void *)
0x18000c0c1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000c0c4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000c0cb  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000c0d0  jmp     loc_18000C19D
0x18000c0d5  mov     qword ptr [rcx], 0
0x18000c0dc  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000c0e3  jz      loc_18000C19D
0x18000c0e9  lea     rcx, stru_180023090; SRWLock
0x18000c0f0  call    cs:__imp_AcquireSRWLockExclusive
0x18000c0f6  cmp     cs:qword_180023100, 0
0x18000c0fe  jnz     short loc_18000C17B
0x18000c100  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000c107  mov     cs:qword_180023100, 0
0x18000c112  test    rax, rax
0x18000c115  jnz     short loc_18000C15A
0x18000c117  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c11e  test    rax, rax
0x18000c121  jnz     short loc_18000C137
0x18000c123  lea     rcx, ModuleName; "ntdll.dll"
0x18000c12a  call    cs:__imp_GetModuleHandleW
0x18000c130  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c137  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000c13e  mov     rcx, rax; hModule
0x18000c141  call    cs:__imp_GetProcAddress
0x18000c147  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000c14e  test    rax, rax
0x18000c151  jnz     short loc_18000C15A
0x18000c153  mov     eax, 0C0000139h
0x18000c158  jmp     short loc_18000C177
0x18000c15a  lea     r9, qword_180023100
0x18000c161  xor     r8d, r8d
0x18000c164  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000c16b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000c172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c177  test    eax, eax
0x18000c179  jnz     short loc_18000C190
0x18000c17b  mov     r9, rdi; void *
0x18000c17e  lea     rcx, CriticalSection; this
0x18000c185  mov     r8, rsi; void (*)(void *)
0x18000c188  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000c18b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000c190  lea     rcx, stru_180023090; SRWLock
0x18000c197  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c19d  mov     rbx, [rsp+38h+arg_0]
0x18000c1a2  mov     rsi, [rsp+38h+arg_8]
0x18000c1a7  add     rsp, 30h
0x18000c1ab  pop     rdi
0x18000c1ac  retn
```
