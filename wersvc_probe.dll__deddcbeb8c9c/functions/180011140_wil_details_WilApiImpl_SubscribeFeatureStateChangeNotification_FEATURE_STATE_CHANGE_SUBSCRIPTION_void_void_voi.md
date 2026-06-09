# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180011140`
- end: `0x18001124d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000d088`
- `0x18000d184`
- `0x180011140`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800111ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800111ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800111e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800111e1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011190`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011190`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011237`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011237`

## string_xrefs

- `0x1800111c3`: `ntdll.dll`
- `0x1800111d7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180047180);
      if ( qword_1800471F0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800471F0 = 0;
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
               &qword_1800471F0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180047180);
    }
  }
}

```

## disassembly

```asm
0x180011140  mov     [rsp+arg_0], rbx
0x180011145  mov     [rsp+arg_8], rsi
0x18001114a  push    rdi
0x18001114b  sub     rsp, 30h
0x18001114f  mov     rdi, r8
0x180011152  mov     rsi, rdx
0x180011155  mov     rbx, rcx
0x180011158  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001115c  jnz     short loc_180011175
0x18001115e  mov     r8, rdx; void (*)(void *)
0x180011161  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180011164  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001116b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180011170  jmp     loc_18001123D
0x180011175  mov     qword ptr [rcx], 0
0x18001117c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180011183  jz      loc_18001123D
0x180011189  lea     rcx, stru_180047180; SRWLock
0x180011190  call    cs:__imp_AcquireSRWLockExclusive
0x180011196  cmp     cs:qword_1800471F0, 0
0x18001119e  jnz     short loc_18001121B
0x1800111a0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800111a7  mov     cs:qword_1800471F0, 0
0x1800111b2  test    rax, rax
0x1800111b5  jnz     short loc_1800111FA
0x1800111b7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800111be  test    rax, rax
0x1800111c1  jnz     short loc_1800111D7
0x1800111c3  lea     rcx, Src; "ntdll.dll"
0x1800111ca  call    cs:__imp_GetModuleHandleW
0x1800111d0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800111d7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800111de  mov     rcx, rax; hModule
0x1800111e1  call    cs:__imp_GetProcAddress
0x1800111e7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800111ee  test    rax, rax
0x1800111f1  jnz     short loc_1800111FA
0x1800111f3  mov     eax, 0C0000139h
0x1800111f8  jmp     short loc_180011217
0x1800111fa  lea     r9, qword_1800471F0
0x180011201  xor     r8d, r8d
0x180011204  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001120b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180011212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011217  test    eax, eax
0x180011219  jnz     short loc_180011230
0x18001121b  mov     r9, rdi; void *
0x18001121e  lea     rcx, CriticalSection; this
0x180011225  mov     r8, rsi; void (*)(void *)
0x180011228  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18001122b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180011230  lea     rcx, stru_180047180; SRWLock
0x180011237  call    cs:__imp_ReleaseSRWLockExclusive
0x18001123d  mov     rbx, [rsp+38h+arg_0]
0x180011242  mov     rsi, [rsp+38h+arg_8]
0x180011247  add     rsp, 30h
0x18001124b  pop     rdi
0x18001124c  retn
```
