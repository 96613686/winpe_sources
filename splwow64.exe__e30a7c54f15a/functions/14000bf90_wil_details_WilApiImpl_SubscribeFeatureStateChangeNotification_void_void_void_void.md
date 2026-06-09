# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(void * *,void (*)(void *),void *)

- ea: `0x14000bf90`
- end: `0x14000c09d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAXP6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(void **this, void **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x14000babc`
- `0x14000bbb8`
- `0x14000bf90`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000c031`
- `KERNEL32!GetProcAddress` at `0x14000c031`
- `KERNEL32!GetModuleHandleW` at `0x14000c01a`
- `KERNEL32!GetModuleHandleW` at `0x14000c01a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000bfe0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000bfe0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000c087`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000c087`

## string_xrefs

- `0x14000c013`: `ntdll.dll`
- `0x14000c027`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(
        void **this,
        void **a2,
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
      AcquireSRWLockExclusive(&stru_140021170);
      if ( qword_1400211E0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1400211E0 = 0;
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
               &qword_1400211E0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_140021170);
    }
  }
}

```

## disassembly

```asm
0x14000bf90  mov     [rsp+arg_0], rbx
0x14000bf95  mov     [rsp+arg_8], rsi
0x14000bf9a  push    rdi
0x14000bf9b  sub     rsp, 30h
0x14000bf9f  mov     rdi, r8
0x14000bfa2  mov     rsi, rdx
0x14000bfa5  mov     rbx, rcx
0x14000bfa8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14000bfac  jnz     short loc_14000BFC5
0x14000bfae  mov     r8, rdx; void (*)(void *)
0x14000bfb1  mov     rdx, rcx; void **
0x14000bfb4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000bfbb  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAXP6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(void * *,void (*)(void *))
0x14000bfc0  jmp     loc_14000C08D
0x14000bfc5  mov     qword ptr [rcx], 0
0x14000bfcc  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000bfd3  jz      loc_14000C08D
0x14000bfd9  lea     rcx, stru_140021170; SRWLock
0x14000bfe0  call    cs:__imp_AcquireSRWLockExclusive
0x14000bfe6  cmp     cs:qword_1400211E0, 0
0x14000bfee  jnz     short loc_14000C06B
0x14000bff0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000bff7  mov     cs:qword_1400211E0, 0
0x14000c002  test    rax, rax
0x14000c005  jnz     short loc_14000C04A
0x14000c007  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAXXZ@4PEAXEA; void * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c00e  test    rax, rax
0x14000c011  jnz     short loc_14000C027
0x14000c013  lea     rcx, ModuleName; "ntdll.dll"
0x14000c01a  call    cs:__imp_GetModuleHandleW
0x14000c020  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAXXZ@4PEAXEA, rax; void * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c027  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000c02e  mov     rcx, rax; hModule
0x14000c031  call    cs:__imp_GetProcAddress
0x14000c037  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000c03e  test    rax, rax
0x14000c041  jnz     short loc_14000C04A
0x14000c043  mov     eax, 0C0000139h
0x14000c048  jmp     short loc_14000C067
0x14000c04a  lea     r9, qword_1400211E0
0x14000c051  xor     r8d, r8d
0x14000c054  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000c05b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x14000c062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c067  test    eax, eax
0x14000c069  jnz     short loc_14000C080
0x14000c06b  mov     r9, rdi; void *
0x14000c06e  lea     rcx, CriticalSection; this
0x14000c075  mov     r8, rsi; void (*)(void *)
0x14000c078  mov     rdx, rbx; void **
0x14000c07b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAXP6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(void * *,void (*)(void *),void *)
0x14000c080  lea     rcx, stru_140021170; SRWLock
0x14000c087  call    cs:__imp_ReleaseSRWLockExclusive
0x14000c08d  mov     rbx, [rsp+38h+arg_0]
0x14000c092  mov     rsi, [rsp+38h+arg_8]
0x14000c097  add     rsp, 30h
0x14000c09b  pop     rdi
0x14000c09c  retn
```
