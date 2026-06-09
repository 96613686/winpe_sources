# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1400051e0`
- end: `0x1400052ed`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x140004d34`
- `0x140004e30`
- `0x1400051e0`
- `0x140018010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400052d7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400052d7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140005230`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140005230`
- `KERNEL32!GetProcAddress` at `0x140005281`
- `KERNEL32!GetProcAddress` at `0x140005281`
- `KERNEL32!GetModuleHandleW` at `0x14000526a`
- `KERNEL32!GetModuleHandleW` at `0x14000526a`

## string_xrefs

- `0x140005263`: `ntdll.dll`
- `0x140005277`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_1400208F0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1400208F0 = 0;
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
               &qword_1400208F0);
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
0x1400051e0  mov     [rsp+arg_0], rbx
0x1400051e5  mov     [rsp+arg_8], rsi
0x1400051ea  push    rdi
0x1400051eb  sub     rsp, 30h
0x1400051ef  mov     rdi, r8
0x1400051f2  mov     rsi, rdx
0x1400051f5  mov     rbx, rcx
0x1400051f8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1400051fc  jnz     short loc_140005215
0x1400051fe  mov     r8, rdx; void (*)(void *)
0x140005201  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x140005204  lea     rcx, ?g_featureStateManager@details@wil@@3V?$manually_managed_shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000520b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x140005210  jmp     loc_1400052DD
0x140005215  mov     qword ptr [rcx], 0
0x14000521c  cmp     cs:?g_featureStateManager@details@wil@@3V?$manually_managed_shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::manually_managed_shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140005223  jz      loc_1400052DD
0x140005229  lea     rcx, SRWLock; SRWLock
0x140005230  call    cs:__imp_AcquireSRWLockExclusive
0x140005236  cmp     cs:qword_1400208F0, 0
0x14000523e  jnz     short loc_1400052BB
0x140005240  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x140005247  mov     cs:qword_1400208F0, 0
0x140005252  test    rax, rax
0x140005255  jnz     short loc_14000529A
0x140005257  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000525e  test    rax, rax
0x140005261  jnz     short loc_140005277
0x140005263  lea     rcx, ModuleName; "ntdll.dll"
0x14000526a  call    cs:__imp_GetModuleHandleW
0x140005270  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140005277  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000527e  mov     rcx, rax; hModule
0x140005281  call    cs:__imp_GetProcAddress
0x140005287  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000528e  test    rax, rax
0x140005291  jnz     short loc_14000529A
0x140005293  mov     eax, 0C0000139h
0x140005298  jmp     short loc_1400052B7
0x14000529a  lea     r9, qword_1400208F0
0x1400052a1  xor     r8d, r8d
0x1400052a4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$manually_managed_shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::manually_managed_shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1400052ab  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1400052b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400052b7  test    eax, eax
0x1400052b9  jnz     short loc_1400052D0
0x1400052bb  mov     r9, rdi; void *
0x1400052be  lea     rcx, CriticalSection; this
0x1400052c5  mov     r8, rsi; void (*)(void *)
0x1400052c8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1400052cb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1400052d0  lea     rcx, SRWLock; SRWLock
0x1400052d7  call    cs:__imp_ReleaseSRWLockExclusive
0x1400052dd  mov     rbx, [rsp+38h+arg_0]
0x1400052e2  mov     rsi, [rsp+38h+arg_8]
0x1400052e7  add     rsp, 30h
0x1400052eb  pop     rdi
0x1400052ec  retn
```
