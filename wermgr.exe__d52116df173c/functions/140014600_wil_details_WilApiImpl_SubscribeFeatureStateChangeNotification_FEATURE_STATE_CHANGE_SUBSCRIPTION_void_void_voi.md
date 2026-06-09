# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x140014600`
- end: `0x14001470d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x140013e88`
- `0x140013f84`
- `0x140014600`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400146a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400146a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001468a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001468a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400146f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400146f7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014650`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014650`

## string_xrefs

- `0x140014683`: `ntdll.dll`
- `0x140014697`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_14002C098);
      if ( qword_14002C108 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_14002C108 = 0;
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
               &qword_14002C108);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_14002C098);
    }
  }
}

```

## disassembly

```asm
0x140014600  mov     [rsp+arg_0], rbx
0x140014605  mov     [rsp+arg_8], rsi
0x14001460a  push    rdi
0x14001460b  sub     rsp, 30h
0x14001460f  mov     rdi, r8
0x140014612  mov     rsi, rdx
0x140014615  mov     rbx, rcx
0x140014618  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14001461c  jnz     short loc_140014635
0x14001461e  mov     r8, rdx; void (*)(void *)
0x140014621  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x140014624  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14001462b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x140014630  jmp     loc_1400146FD
0x140014635  mov     qword ptr [rcx], 0
0x14001463c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140014643  jz      loc_1400146FD
0x140014649  lea     rcx, stru_14002C098; SRWLock
0x140014650  call    cs:__imp_AcquireSRWLockExclusive
0x140014656  cmp     cs:qword_14002C108, 0
0x14001465e  jnz     short loc_1400146DB
0x140014660  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x140014667  mov     cs:qword_14002C108, 0
0x140014672  test    rax, rax
0x140014675  jnz     short loc_1400146BA
0x140014677  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001467e  test    rax, rax
0x140014681  jnz     short loc_140014697
0x140014683  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x14001468a  call    cs:__imp_GetModuleHandleW
0x140014690  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140014697  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14001469e  mov     rcx, rax; hModule
0x1400146a1  call    cs:__imp_GetProcAddress
0x1400146a7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1400146ae  test    rax, rax
0x1400146b1  jnz     short loc_1400146BA
0x1400146b3  mov     eax, 0C0000139h
0x1400146b8  jmp     short loc_1400146D7
0x1400146ba  lea     r9, qword_14002C108
0x1400146c1  xor     r8d, r8d
0x1400146c4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1400146cb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1400146d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400146d7  test    eax, eax
0x1400146d9  jnz     short loc_1400146F0
0x1400146db  mov     r9, rdi; void *
0x1400146de  lea     rcx, CriticalSection; this
0x1400146e5  mov     r8, rsi; void (*)(void *)
0x1400146e8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1400146eb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1400146f0  lea     rcx, stru_14002C098; SRWLock
0x1400146f7  call    cs:__imp_ReleaseSRWLockExclusive
0x1400146fd  mov     rbx, [rsp+38h+arg_0]
0x140014702  mov     rsi, [rsp+38h+arg_8]
0x140014707  add     rsp, 30h
0x14001470b  pop     rdi
0x14001470c  retn
```
