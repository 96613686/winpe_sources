# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18001cac0`
- end: `0x18001cbcd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18001c604`
- `0x18001c700`
- `0x18001cac0`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cb61`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cb61`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001cb4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001cb4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cbb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cbb7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001cb10`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001cb10`

## string_xrefs

- `0x18001cb43`: `ntdll.dll`
- `0x18001cb57`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180028828);
      if ( qword_180028898 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180028898 = 0;
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
               &qword_180028898);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180028828);
    }
  }
}

```

## disassembly

```asm
0x18001cac0  mov     [rsp+arg_0], rbx
0x18001cac5  mov     [rsp+arg_8], rsi
0x18001caca  push    rdi
0x18001cacb  sub     rsp, 30h
0x18001cacf  mov     rdi, r8
0x18001cad2  mov     rsi, rdx
0x18001cad5  mov     rbx, rcx
0x18001cad8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001cadc  jnz     short loc_18001CAF5
0x18001cade  mov     r8, rdx; void (*)(void *)
0x18001cae1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18001cae4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001caeb  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18001caf0  jmp     loc_18001CBBD
0x18001caf5  mov     qword ptr [rcx], 0
0x18001cafc  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001cb03  jz      loc_18001CBBD
0x18001cb09  lea     rcx, stru_180028828; SRWLock
0x18001cb10  call    cs:__imp_AcquireSRWLockExclusive
0x18001cb16  cmp     cs:qword_180028898, 0
0x18001cb1e  jnz     short loc_18001CB9B
0x18001cb20  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18001cb27  mov     cs:qword_180028898, 0
0x18001cb32  test    rax, rax
0x18001cb35  jnz     short loc_18001CB7A
0x18001cb37  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001cb3e  test    rax, rax
0x18001cb41  jnz     short loc_18001CB57
0x18001cb43  lea     rcx, ModuleName; "ntdll.dll"
0x18001cb4a  call    cs:__imp_GetModuleHandleW
0x18001cb50  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001cb57  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001cb5e  mov     rcx, rax; hModule
0x18001cb61  call    cs:__imp_GetProcAddress
0x18001cb67  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001cb6e  test    rax, rax
0x18001cb71  jnz     short loc_18001CB7A
0x18001cb73  mov     eax, 0C0000139h
0x18001cb78  jmp     short loc_18001CB97
0x18001cb7a  lea     r9, qword_180028898
0x18001cb81  xor     r8d, r8d
0x18001cb84  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001cb8b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18001cb92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb97  test    eax, eax
0x18001cb99  jnz     short loc_18001CBB0
0x18001cb9b  mov     r9, rdi; void *
0x18001cb9e  lea     rcx, CriticalSection; this
0x18001cba5  mov     r8, rsi; void (*)(void *)
0x18001cba8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18001cbab  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18001cbb0  lea     rcx, stru_180028828; SRWLock
0x18001cbb7  call    cs:__imp_ReleaseSRWLockExclusive
0x18001cbbd  mov     rbx, [rsp+38h+arg_0]
0x18001cbc2  mov     rsi, [rsp+38h+arg_8]
0x18001cbc7  add     rsp, 30h
0x18001cbcb  pop     rdi
0x18001cbcc  retn
```
