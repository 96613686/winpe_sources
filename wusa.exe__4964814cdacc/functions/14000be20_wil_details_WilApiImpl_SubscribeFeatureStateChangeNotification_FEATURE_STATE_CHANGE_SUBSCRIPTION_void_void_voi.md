# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14000be20`
- end: `0x14000bf2d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x14000ad3c`
- `0x14000ae38`
- `0x14000be20`
- `0x140015010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000bec1`
- `KERNEL32!GetProcAddress` at `0x14000bec1`
- `KERNEL32!GetModuleHandleW` at `0x14000beaa`
- `KERNEL32!GetModuleHandleW` at `0x14000beaa`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000be70`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000be70`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000bf17`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000bf17`

## string_xrefs

- `0x14000bea3`: `ntdll.dll`
- `0x14000beb7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_140020030);
      if ( qword_1400200A0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1400200A0 = 0;
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
               &qword_1400200A0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_140020030);
    }
  }
}

```

## disassembly

```asm
0x14000be20  mov     [rsp+arg_0], rbx
0x14000be25  mov     [rsp+arg_8], rsi
0x14000be2a  push    rdi
0x14000be2b  sub     rsp, 30h
0x14000be2f  mov     rdi, r8
0x14000be32  mov     rsi, rdx
0x14000be35  mov     rbx, rcx
0x14000be38  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14000be3c  jnz     short loc_14000BE55
0x14000be3e  mov     r8, rdx; void (*)(void *)
0x14000be41  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000be44  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000be4b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x14000be50  jmp     loc_14000BF1D
0x14000be55  mov     qword ptr [rcx], 0
0x14000be5c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000be63  jz      loc_14000BF1D
0x14000be69  lea     rcx, stru_140020030; SRWLock
0x14000be70  call    cs:__imp_AcquireSRWLockExclusive
0x14000be76  cmp     cs:qword_1400200A0, 0
0x14000be7e  jnz     short loc_14000BEFB
0x14000be80  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000be87  mov     cs:qword_1400200A0, 0
0x14000be92  test    rax, rax
0x14000be95  jnz     short loc_14000BEDA
0x14000be97  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000be9e  test    rax, rax
0x14000bea1  jnz     short loc_14000BEB7
0x14000bea3  lea     rcx, ModuleName; "ntdll.dll"
0x14000beaa  call    cs:__imp_GetModuleHandleW
0x14000beb0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000beb7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000bebe  mov     rcx, rax; hModule
0x14000bec1  call    cs:__imp_GetProcAddress
0x14000bec7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000bece  test    rax, rax
0x14000bed1  jnz     short loc_14000BEDA
0x14000bed3  mov     eax, 0C0000139h
0x14000bed8  jmp     short loc_14000BEF7
0x14000beda  lea     r9, qword_1400200A0
0x14000bee1  xor     r8d, r8d
0x14000bee4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000beeb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x14000bef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bef7  test    eax, eax
0x14000bef9  jnz     short loc_14000BF10
0x14000befb  mov     r9, rdi; void *
0x14000befe  lea     rcx, CriticalSection; this
0x14000bf05  mov     r8, rsi; void (*)(void *)
0x14000bf08  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000bf0b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x14000bf10  lea     rcx, stru_140020030; SRWLock
0x14000bf17  call    cs:__imp_ReleaseSRWLockExclusive
0x14000bf1d  mov     rbx, [rsp+38h+arg_0]
0x14000bf22  mov     rsi, [rsp+38h+arg_8]
0x14000bf27  add     rsp, 30h
0x14000bf2b  pop     rdi
0x14000bf2c  retn
```
