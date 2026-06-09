# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1800392e0`
- end: `0x1800393ed`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180038b30`
- `0x180038c2c`
- `0x1800392e0`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039381`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039381`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003936a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003936a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180039330`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180039330`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800393d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800393d7`

## string_xrefs

- `0x180039363`: `ntdll.dll`
- `0x180039377`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_1800BD738);
      if ( qword_1800BD7A8 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800BD7A8 = 0;
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
               &qword_1800BD7A8);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_1800BD738);
    }
  }
}

```

## disassembly

```asm
0x1800392e0  mov     [rsp+arg_0], rbx
0x1800392e5  mov     [rsp+arg_8], rsi
0x1800392ea  push    rdi
0x1800392eb  sub     rsp, 30h
0x1800392ef  mov     rdi, r8
0x1800392f2  mov     rsi, rdx
0x1800392f5  mov     rbx, rcx
0x1800392f8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800392fc  jnz     short loc_180039315
0x1800392fe  mov     r8, rdx; void (*)(void *)
0x180039301  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180039304  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18003930b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180039310  jmp     loc_1800393DD
0x180039315  mov     qword ptr [rcx], 0
0x18003931c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180039323  jz      loc_1800393DD
0x180039329  lea     rcx, stru_1800BD738; SRWLock
0x180039330  call    cs:__imp_AcquireSRWLockExclusive
0x180039336  cmp     cs:qword_1800BD7A8, 0
0x18003933e  jnz     short loc_1800393BB
0x180039340  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180039347  mov     cs:qword_1800BD7A8, 0
0x180039352  test    rax, rax
0x180039355  jnz     short loc_18003939A
0x180039357  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003935e  test    rax, rax
0x180039361  jnz     short loc_180039377
0x180039363  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18003936a  call    cs:__imp_GetModuleHandleW
0x180039370  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180039377  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18003937e  mov     rcx, rax; hModule
0x180039381  call    cs:__imp_GetProcAddress
0x180039387  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18003938e  test    rax, rax
0x180039391  jnz     short loc_18003939A
0x180039393  mov     eax, 0C0000139h
0x180039398  jmp     short loc_1800393B7
0x18003939a  lea     r9, qword_1800BD7A8
0x1800393a1  xor     r8d, r8d
0x1800393a4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800393ab  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800393b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393b7  test    eax, eax
0x1800393b9  jnz     short loc_1800393D0
0x1800393bb  mov     r9, rdi; void *
0x1800393be  lea     rcx, CriticalSection; this
0x1800393c5  mov     r8, rsi; void (*)(void *)
0x1800393c8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800393cb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800393d0  lea     rcx, stru_1800BD738; SRWLock
0x1800393d7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800393dd  mov     rbx, [rsp+38h+arg_0]
0x1800393e2  mov     rsi, [rsp+38h+arg_8]
0x1800393e7  add     rsp, 30h
0x1800393eb  pop     rdi
0x1800393ec  retn
```
