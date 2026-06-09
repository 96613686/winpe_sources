# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000eb30`
- end: `0x18000ec3d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000e670`
- `0x18000e76c`
- `0x18000eb30`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000eb80`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000eb80`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ec27`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ec27`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ebba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ebba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ebd1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ebd1`

## string_xrefs

- `0x18000ebb3`: `ntdll.dll`
- `0x18000ebc7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180034068);
      if ( qword_1800340D8 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800340D8 = 0;
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
               &qword_1800340D8);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180034068);
    }
  }
}

```

## disassembly

```asm
0x18000eb30  mov     [rsp+arg_0], rbx
0x18000eb35  mov     [rsp+arg_8], rsi
0x18000eb3a  push    rdi
0x18000eb3b  sub     rsp, 30h
0x18000eb3f  mov     rdi, r8
0x18000eb42  mov     rsi, rdx
0x18000eb45  mov     rbx, rcx
0x18000eb48  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000eb4c  jnz     short loc_18000EB65
0x18000eb4e  mov     r8, rdx; void (*)(void *)
0x18000eb51  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000eb54  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000eb5b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000eb60  jmp     loc_18000EC2D
0x18000eb65  mov     qword ptr [rcx], 0
0x18000eb6c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000eb73  jz      loc_18000EC2D
0x18000eb79  lea     rcx, stru_180034068; SRWLock
0x18000eb80  call    cs:__imp_AcquireSRWLockExclusive
0x18000eb86  cmp     cs:qword_1800340D8, 0
0x18000eb8e  jnz     short loc_18000EC0B
0x18000eb90  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000eb97  mov     cs:qword_1800340D8, 0
0x18000eba2  test    rax, rax
0x18000eba5  jnz     short loc_18000EBEA
0x18000eba7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ebae  test    rax, rax
0x18000ebb1  jnz     short loc_18000EBC7
0x18000ebb3  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000ebba  call    cs:__imp_GetModuleHandleW
0x18000ebc0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ebc7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000ebce  mov     rcx, rax; hModule
0x18000ebd1  call    cs:__imp_GetProcAddress
0x18000ebd7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000ebde  test    rax, rax
0x18000ebe1  jnz     short loc_18000EBEA
0x18000ebe3  mov     eax, 0C0000139h
0x18000ebe8  jmp     short loc_18000EC07
0x18000ebea  lea     r9, qword_1800340D8
0x18000ebf1  xor     r8d, r8d
0x18000ebf4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000ebfb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000ec02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec07  test    eax, eax
0x18000ec09  jnz     short loc_18000EC20
0x18000ec0b  mov     r9, rdi; void *
0x18000ec0e  lea     rcx, CriticalSection; this
0x18000ec15  mov     r8, rsi; void (*)(void *)
0x18000ec18  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000ec1b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000ec20  lea     rcx, stru_180034068; SRWLock
0x18000ec27  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ec2d  mov     rbx, [rsp+38h+arg_0]
0x18000ec32  mov     rsi, [rsp+38h+arg_8]
0x18000ec37  add     rsp, 30h
0x18000ec3b  pop     rdi
0x18000ec3c  retn
```
