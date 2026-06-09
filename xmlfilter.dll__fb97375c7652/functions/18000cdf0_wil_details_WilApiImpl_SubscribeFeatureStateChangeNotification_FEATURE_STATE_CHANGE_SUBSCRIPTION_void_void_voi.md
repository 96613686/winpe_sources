# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000cdf0`
- end: `0x18000cefd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000c4fc`
- `0x18000c5f8`
- `0x18000cdf0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cee7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cee7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ce40`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ce40`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ce7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ce7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ce91`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ce91`

## string_xrefs

- `0x18000ce73`: `ntdll.dll`
- `0x18000ce87`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180021118);
      if ( qword_180021188 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180021188 = 0;
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
               &qword_180021188);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180021118);
    }
  }
}

```

## disassembly

```asm
0x18000cdf0  mov     [rsp+arg_0], rbx
0x18000cdf5  mov     [rsp+arg_8], rsi
0x18000cdfa  push    rdi
0x18000cdfb  sub     rsp, 30h
0x18000cdff  mov     rdi, r8
0x18000ce02  mov     rsi, rdx
0x18000ce05  mov     rbx, rcx
0x18000ce08  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000ce0c  jnz     short loc_18000CE25
0x18000ce0e  mov     r8, rdx; void (*)(void *)
0x18000ce11  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000ce14  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000ce1b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000ce20  jmp     loc_18000CEED
0x18000ce25  mov     qword ptr [rcx], 0
0x18000ce2c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000ce33  jz      loc_18000CEED
0x18000ce39  lea     rcx, stru_180021118; SRWLock
0x18000ce40  call    cs:__imp_AcquireSRWLockExclusive
0x18000ce46  cmp     cs:qword_180021188, 0
0x18000ce4e  jnz     short loc_18000CECB
0x18000ce50  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000ce57  mov     cs:qword_180021188, 0
0x18000ce62  test    rax, rax
0x18000ce65  jnz     short loc_18000CEAA
0x18000ce67  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ce6e  test    rax, rax
0x18000ce71  jnz     short loc_18000CE87
0x18000ce73  lea     rcx, ModuleName; "ntdll.dll"
0x18000ce7a  call    cs:__imp_GetModuleHandleW
0x18000ce80  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ce87  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000ce8e  mov     rcx, rax; hModule
0x18000ce91  call    cs:__imp_GetProcAddress
0x18000ce97  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000ce9e  test    rax, rax
0x18000cea1  jnz     short loc_18000CEAA
0x18000cea3  mov     eax, 0C0000139h
0x18000cea8  jmp     short loc_18000CEC7
0x18000ceaa  lea     r9, qword_180021188
0x18000ceb1  xor     r8d, r8d
0x18000ceb4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000cebb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000cec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cec7  test    eax, eax
0x18000cec9  jnz     short loc_18000CEE0
0x18000cecb  mov     r9, rdi; void *
0x18000cece  lea     rcx, CriticalSection; this
0x18000ced5  mov     r8, rsi; void (*)(void *)
0x18000ced8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000cedb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000cee0  lea     rcx, stru_180021118; SRWLock
0x18000cee7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ceed  mov     rbx, [rsp+38h+arg_0]
0x18000cef2  mov     rsi, [rsp+38h+arg_8]
0x18000cef7  add     rsp, 30h
0x18000cefb  pop     rdi
0x18000cefc  retn
```
