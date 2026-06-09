# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000afe0`
- end: `0x18000b0ed`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000a88c`
- `0x18000a988`
- `0x18000afe0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b081`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b081`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b06a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b06a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b030`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b030`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b0d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b0d7`

## string_xrefs

- `0x18000b063`: `ntdll.dll`
- `0x18000b077`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180015080);
      if ( qword_1800150F0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800150F0 = 0;
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
               &qword_1800150F0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180015080);
    }
  }
}

```

## disassembly

```asm
0x18000afe0  mov     [rsp+arg_0], rbx
0x18000afe5  mov     [rsp+arg_8], rsi
0x18000afea  push    rdi
0x18000afeb  sub     rsp, 30h
0x18000afef  mov     rdi, r8
0x18000aff2  mov     rsi, rdx
0x18000aff5  mov     rbx, rcx
0x18000aff8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000affc  jnz     short loc_18000B015
0x18000affe  mov     r8, rdx; void (*)(void *)
0x18000b001  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000b004  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000b00b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000b010  jmp     loc_18000B0DD
0x18000b015  mov     qword ptr [rcx], 0
0x18000b01c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000b023  jz      loc_18000B0DD
0x18000b029  lea     rcx, stru_180015080; SRWLock
0x18000b030  call    cs:__imp_AcquireSRWLockExclusive
0x18000b036  cmp     cs:qword_1800150F0, 0
0x18000b03e  jnz     short loc_18000B0BB
0x18000b040  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000b047  mov     cs:qword_1800150F0, 0
0x18000b052  test    rax, rax
0x18000b055  jnz     short loc_18000B09A
0x18000b057  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b05e  test    rax, rax
0x18000b061  jnz     short loc_18000B077
0x18000b063  lea     rcx, ModuleName; "ntdll.dll"
0x18000b06a  call    cs:__imp_GetModuleHandleW
0x18000b070  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b077  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000b07e  mov     rcx, rax; hModule
0x18000b081  call    cs:__imp_GetProcAddress
0x18000b087  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000b08e  test    rax, rax
0x18000b091  jnz     short loc_18000B09A
0x18000b093  mov     eax, 0C0000139h
0x18000b098  jmp     short loc_18000B0B7
0x18000b09a  lea     r9, qword_1800150F0
0x18000b0a1  xor     r8d, r8d
0x18000b0a4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000b0ab  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000b0b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0b7  test    eax, eax
0x18000b0b9  jnz     short loc_18000B0D0
0x18000b0bb  mov     r9, rdi; void *
0x18000b0be  lea     rcx, CriticalSection; this
0x18000b0c5  mov     r8, rsi; void (*)(void *)
0x18000b0c8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000b0cb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000b0d0  lea     rcx, stru_180015080; SRWLock
0x18000b0d7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b0dd  mov     rbx, [rsp+38h+arg_0]
0x18000b0e2  mov     rsi, [rsp+38h+arg_8]
0x18000b0e7  add     rsp, 30h
0x18000b0eb  pop     rdi
0x18000b0ec  retn
```
