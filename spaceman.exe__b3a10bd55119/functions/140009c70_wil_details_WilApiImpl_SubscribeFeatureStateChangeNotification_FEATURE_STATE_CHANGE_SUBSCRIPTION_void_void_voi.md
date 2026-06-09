# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x140009c70`
- end: `0x140009d7d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1400095bc`
- `0x1400096b8`
- `0x140009c70`
- `0x14000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009d67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009d67`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009cc0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009cc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009d11`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009d11`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009cfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009cfa`

## string_xrefs

- `0x140009cf3`: `ntdll.dll`
- `0x140009d07`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_140014160 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_140014160 = 0;
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
               &qword_140014160);
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
0x140009c70  mov     [rsp+arg_0], rbx
0x140009c75  mov     [rsp+arg_8], rsi
0x140009c7a  push    rdi
0x140009c7b  sub     rsp, 30h
0x140009c7f  mov     rdi, r8
0x140009c82  mov     rsi, rdx
0x140009c85  mov     rbx, rcx
0x140009c88  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140009c8c  jnz     short loc_140009CA5
0x140009c8e  mov     r8, rdx; void (*)(void *)
0x140009c91  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x140009c94  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x140009c9b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x140009ca0  jmp     loc_140009D6D
0x140009ca5  mov     qword ptr [rcx], 0
0x140009cac  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140009cb3  jz      loc_140009D6D
0x140009cb9  lea     rcx, SRWLock; SRWLock
0x140009cc0  call    cs:__imp_AcquireSRWLockExclusive
0x140009cc6  cmp     cs:qword_140014160, 0
0x140009cce  jnz     short loc_140009D4B
0x140009cd0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x140009cd7  mov     cs:qword_140014160, 0
0x140009ce2  test    rax, rax
0x140009ce5  jnz     short loc_140009D2A
0x140009ce7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009cee  test    rax, rax
0x140009cf1  jnz     short loc_140009D07
0x140009cf3  lea     rcx, ModuleName; "ntdll.dll"
0x140009cfa  call    cs:__imp_GetModuleHandleW
0x140009d00  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009d07  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x140009d0e  mov     rcx, rax; hModule
0x140009d11  call    cs:__imp_GetProcAddress
0x140009d17  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x140009d1e  test    rax, rax
0x140009d21  jnz     short loc_140009D2A
0x140009d23  mov     eax, 0C0000139h
0x140009d28  jmp     short loc_140009D47
0x140009d2a  lea     r9, qword_140014160
0x140009d31  xor     r8d, r8d
0x140009d34  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140009d3b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x140009d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009d47  test    eax, eax
0x140009d49  jnz     short loc_140009D60
0x140009d4b  mov     r9, rdi; void *
0x140009d4e  lea     rcx, CriticalSection; this
0x140009d55  mov     r8, rsi; void (*)(void *)
0x140009d58  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x140009d5b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x140009d60  lea     rcx, SRWLock; SRWLock
0x140009d67  call    cs:__imp_ReleaseSRWLockExclusive
0x140009d6d  mov     rbx, [rsp+38h+arg_0]
0x140009d72  mov     rsi, [rsp+38h+arg_8]
0x140009d77  add     rsp, 30h
0x140009d7b  pop     rdi
0x140009d7c  retn
```
