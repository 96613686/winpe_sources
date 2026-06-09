# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180007ff0`
- end: `0x1800080fd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1800078b8`
- `0x1800079b4`
- `0x180007ff0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000807a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000807a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008091`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008091`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008040`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008040`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800080e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800080e7`

## string_xrefs

- `0x180008073`: `ntdll.dll`
- `0x180008087`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_18002D100);
      if ( qword_18002D170 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18002D170 = 0;
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
               &qword_18002D170);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_18002D100);
    }
  }
}

```

## disassembly

```asm
0x180007ff0  mov     [rsp+arg_0], rbx
0x180007ff5  mov     [rsp+arg_8], rsi
0x180007ffa  push    rdi
0x180007ffb  sub     rsp, 30h
0x180007fff  mov     rdi, r8
0x180008002  mov     rsi, rdx
0x180008005  mov     rbx, rcx
0x180008008  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000800c  jnz     short loc_180008025
0x18000800e  mov     r8, rdx; void (*)(void *)
0x180008011  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180008014  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000801b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180008020  jmp     loc_1800080ED
0x180008025  mov     qword ptr [rcx], 0
0x18000802c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180008033  jz      loc_1800080ED
0x180008039  lea     rcx, stru_18002D100; SRWLock
0x180008040  call    cs:__imp_AcquireSRWLockExclusive
0x180008046  cmp     cs:qword_18002D170, 0
0x18000804e  jnz     short loc_1800080CB
0x180008050  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180008057  mov     cs:qword_18002D170, 0
0x180008062  test    rax, rax
0x180008065  jnz     short loc_1800080AA
0x180008067  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000806e  test    rax, rax
0x180008071  jnz     short loc_180008087
0x180008073  lea     rcx, ModuleName; "ntdll.dll"
0x18000807a  call    cs:__imp_GetModuleHandleW
0x180008080  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008087  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000808e  mov     rcx, rax; hModule
0x180008091  call    cs:__imp_GetProcAddress
0x180008097  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000809e  test    rax, rax
0x1800080a1  jnz     short loc_1800080AA
0x1800080a3  mov     eax, 0C0000139h
0x1800080a8  jmp     short loc_1800080C7
0x1800080aa  lea     r9, qword_18002D170
0x1800080b1  xor     r8d, r8d
0x1800080b4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800080bb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800080c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080c7  test    eax, eax
0x1800080c9  jnz     short loc_1800080E0
0x1800080cb  mov     r9, rdi; void *
0x1800080ce  lea     rcx, CriticalSection; this
0x1800080d5  mov     r8, rsi; void (*)(void *)
0x1800080d8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800080db  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800080e0  lea     rcx, stru_18002D100; SRWLock
0x1800080e7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800080ed  mov     rbx, [rsp+38h+arg_0]
0x1800080f2  mov     rsi, [rsp+38h+arg_8]
0x1800080f7  add     rsp, 30h
0x1800080fb  pop     rdi
0x1800080fc  retn
```
