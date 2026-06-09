# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000b310`
- end: `0x18000b41d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000ab8c`
- `0x18000ac90`
- `0x18000b310`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b3b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b3b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b39a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b39a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b407`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b407`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b360`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b360`

## string_xrefs

- `0x18000b393`: `ntdll.dll`
- `0x18000b3a7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_1800410A0);
      if ( qword_180041110 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180041110 = 0;
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
               &qword_180041110);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_1800410A0);
    }
  }
}

```

## disassembly

```asm
0x18000b310  mov     [rsp+arg_8], rbx
0x18000b315  mov     [rsp+arg_10], rsi
0x18000b31a  push    rdi
0x18000b31b  sub     rsp, 30h
0x18000b31f  mov     rsi, r8
0x18000b322  mov     rdi, rdx
0x18000b325  mov     rbx, rcx
0x18000b328  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000b32c  jnz     short loc_18000B345
0x18000b32e  mov     r8, rdx; void (*)(void *)
0x18000b331  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000b334  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000b33b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000b340  jmp     loc_18000B40D
0x18000b345  mov     qword ptr [rcx], 0
0x18000b34c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000b353  jz      loc_18000B40D
0x18000b359  lea     rcx, stru_1800410A0; SRWLock
0x18000b360  call    cs:__imp_AcquireSRWLockExclusive
0x18000b366  cmp     cs:qword_180041110, 0
0x18000b36e  jnz     short loc_18000B3EB
0x18000b370  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000b377  mov     cs:qword_180041110, 0
0x18000b382  test    rax, rax
0x18000b385  jnz     short loc_18000B3CA
0x18000b387  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b38e  test    rax, rax
0x18000b391  jnz     short loc_18000B3A7
0x18000b393  lea     rcx, ModuleName; "ntdll.dll"
0x18000b39a  call    cs:__imp_GetModuleHandleW
0x18000b3a0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b3a7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000b3ae  mov     rcx, rax; hModule
0x18000b3b1  call    cs:__imp_GetProcAddress
0x18000b3b7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000b3be  test    rax, rax
0x18000b3c1  jnz     short loc_18000B3CA
0x18000b3c3  mov     eax, 0C0000139h
0x18000b3c8  jmp     short loc_18000B3E7
0x18000b3ca  lea     r9, qword_180041110
0x18000b3d1  xor     r8d, r8d
0x18000b3d4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000b3db  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000b3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3e7  test    eax, eax
0x18000b3e9  jnz     short loc_18000B400
0x18000b3eb  mov     r9, rsi; void *
0x18000b3ee  lea     rcx, CriticalSection; this
0x18000b3f5  mov     r8, rdi; void (*)(void *)
0x18000b3f8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000b3fb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000b400  lea     rcx, stru_1800410A0; SRWLock
0x18000b407  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b40d  mov     rbx, [rsp+38h+arg_8]
0x18000b412  mov     rsi, [rsp+38h+arg_10]
0x18000b417  add     rsp, 30h
0x18000b41b  pop     rdi
0x18000b41c  retn
```
