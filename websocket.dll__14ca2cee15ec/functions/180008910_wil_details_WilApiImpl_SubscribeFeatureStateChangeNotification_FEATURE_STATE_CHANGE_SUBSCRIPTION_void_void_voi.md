# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180008910`
- end: `0x180008a1d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1800081b8`
- `0x1800082b4`
- `0x180008910`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000899a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000899a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800089b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800089b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008960`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008960`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008a07`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008a07`

## string_xrefs

- `0x180008993`: `ntdll.dll`
- `0x1800089a7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180012090);
      if ( qword_180012100 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180012100 = 0;
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
               &qword_180012100);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180012090);
    }
  }
}

```

## disassembly

```asm
0x180008910  mov     [rsp+arg_0], rbx
0x180008915  mov     [rsp+arg_8], rsi
0x18000891a  push    rdi
0x18000891b  sub     rsp, 30h
0x18000891f  mov     rdi, r8
0x180008922  mov     rsi, rdx
0x180008925  mov     rbx, rcx
0x180008928  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000892c  jnz     short loc_180008945
0x18000892e  mov     r8, rdx; void (*)(void *)
0x180008931  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180008934  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000893b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180008940  jmp     loc_180008A0D
0x180008945  mov     qword ptr [rcx], 0
0x18000894c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180008953  jz      loc_180008A0D
0x180008959  lea     rcx, stru_180012090; SRWLock
0x180008960  call    cs:__imp_AcquireSRWLockExclusive
0x180008966  cmp     cs:qword_180012100, 0
0x18000896e  jnz     short loc_1800089EB
0x180008970  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180008977  mov     cs:qword_180012100, 0
0x180008982  test    rax, rax
0x180008985  jnz     short loc_1800089CA
0x180008987  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000898e  test    rax, rax
0x180008991  jnz     short loc_1800089A7
0x180008993  lea     rcx, ModuleName; "ntdll.dll"
0x18000899a  call    cs:__imp_GetModuleHandleW
0x1800089a0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800089a7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800089ae  mov     rcx, rax; hModule
0x1800089b1  call    cs:__imp_GetProcAddress
0x1800089b7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800089be  test    rax, rax
0x1800089c1  jnz     short loc_1800089CA
0x1800089c3  mov     eax, 0C0000139h
0x1800089c8  jmp     short loc_1800089E7
0x1800089ca  lea     r9, qword_180012100
0x1800089d1  xor     r8d, r8d
0x1800089d4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800089db  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800089e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089e7  test    eax, eax
0x1800089e9  jnz     short loc_180008A00
0x1800089eb  mov     r9, rdi; void *
0x1800089ee  lea     rcx, CriticalSection; this
0x1800089f5  mov     r8, rsi; void (*)(void *)
0x1800089f8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800089fb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180008a00  lea     rcx, stru_180012090; SRWLock
0x180008a07  call    cs:__imp_ReleaseSRWLockExclusive
0x180008a0d  mov     rbx, [rsp+38h+arg_0]
0x180008a12  mov     rsi, [rsp+38h+arg_8]
0x180008a17  add     rsp, 30h
0x180008a1b  pop     rdi
0x180008a1c  retn
```
