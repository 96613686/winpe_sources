# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180012110`
- end: `0x18001221d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180010f34`
- `0x180011030`
- `0x180012110`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001219a`
- `KERNEL32!GetModuleHandleW` at `0x18001219a`
- `KERNEL32!GetProcAddress` at `0x1800121b1`
- `KERNEL32!GetProcAddress` at `0x1800121b1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180012160`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180012160`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180012207`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180012207`

## string_xrefs

- `0x180012193`: `ntdll.dll`
- `0x1800121a7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180038140 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180038140 = 0;
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
               &qword_180038140);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&SRWLock);
    }
  }
}

```

## disassembly

```asm
0x180012110  mov     [rsp+arg_0], rbx
0x180012115  mov     [rsp+arg_8], rsi
0x18001211a  push    rdi
0x18001211b  sub     rsp, 30h
0x18001211f  mov     rdi, r8
0x180012122  mov     rsi, rdx
0x180012125  mov     rbx, rcx
0x180012128  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001212c  jnz     short loc_180012145
0x18001212e  mov     r8, rdx; void (*)(void *)
0x180012131  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180012134  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001213b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180012140  jmp     loc_18001220D
0x180012145  mov     qword ptr [rcx], 0
0x18001214c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180012153  jz      loc_18001220D
0x180012159  lea     rcx, SRWLock; SRWLock
0x180012160  call    cs:__imp_AcquireSRWLockExclusive
0x180012166  cmp     cs:qword_180038140, 0
0x18001216e  jnz     short loc_1800121EB
0x180012170  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180012177  mov     cs:qword_180038140, 0
0x180012182  test    rax, rax
0x180012185  jnz     short loc_1800121CA
0x180012187  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001218e  test    rax, rax
0x180012191  jnz     short loc_1800121A7
0x180012193  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001219a  call    cs:__imp_GetModuleHandleW
0x1800121a0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800121a7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800121ae  mov     rcx, rax; hModule
0x1800121b1  call    cs:__imp_GetProcAddress
0x1800121b7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800121be  test    rax, rax
0x1800121c1  jnz     short loc_1800121CA
0x1800121c3  mov     eax, 0C0000139h
0x1800121c8  jmp     short loc_1800121E7
0x1800121ca  lea     r9, qword_180038140
0x1800121d1  xor     r8d, r8d
0x1800121d4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800121db  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800121e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121e7  test    eax, eax
0x1800121e9  jnz     short loc_180012200
0x1800121eb  mov     r9, rdi; void *
0x1800121ee  lea     rcx, CriticalSection; this
0x1800121f5  mov     r8, rsi; void (*)(void *)
0x1800121f8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800121fb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180012200  lea     rcx, SRWLock; SRWLock
0x180012207  call    cs:__imp_ReleaseSRWLockExclusive
0x18001220d  mov     rbx, [rsp+38h+arg_0]
0x180012212  mov     rsi, [rsp+38h+arg_8]
0x180012217  add     rsp, 30h
0x18001221b  pop     rdi
0x18001221c  retn
```
