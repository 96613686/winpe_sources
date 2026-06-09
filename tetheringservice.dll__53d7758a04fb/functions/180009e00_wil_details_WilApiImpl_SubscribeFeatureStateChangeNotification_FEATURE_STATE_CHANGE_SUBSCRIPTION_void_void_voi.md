# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180009e00`
- end: `0x180009f0d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180009654`
- `0x180009750`
- `0x180009e00`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009e8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009e8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009ea1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009ea1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009ef7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009ef7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009e50`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009e50`

## string_xrefs

- `0x180009e83`: `ntdll.dll`
- `0x180009e97`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180041670);
      if ( qword_1800416E0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800416E0 = 0;
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
               &qword_1800416E0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180041670);
    }
  }
}

```

## disassembly

```asm
0x180009e00  mov     [rsp+arg_0], rbx
0x180009e05  mov     [rsp+arg_8], rsi
0x180009e0a  push    rdi
0x180009e0b  sub     rsp, 30h
0x180009e0f  mov     rdi, r8
0x180009e12  mov     rsi, rdx
0x180009e15  mov     rbx, rcx
0x180009e18  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180009e1c  jnz     short loc_180009E35
0x180009e1e  mov     r8, rdx; void (*)(void *)
0x180009e21  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180009e24  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180009e2b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180009e30  jmp     loc_180009EFD
0x180009e35  mov     qword ptr [rcx], 0
0x180009e3c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180009e43  jz      loc_180009EFD
0x180009e49  lea     rcx, stru_180041670; SRWLock
0x180009e50  call    cs:__imp_AcquireSRWLockExclusive
0x180009e56  cmp     cs:qword_1800416E0, 0
0x180009e5e  jnz     short loc_180009EDB
0x180009e60  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180009e67  mov     cs:qword_1800416E0, 0
0x180009e72  test    rax, rax
0x180009e75  jnz     short loc_180009EBA
0x180009e77  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009e7e  test    rax, rax
0x180009e81  jnz     short loc_180009E97
0x180009e83  lea     rcx, ModuleName; "ntdll.dll"
0x180009e8a  call    cs:__imp_GetModuleHandleW
0x180009e90  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009e97  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180009e9e  mov     rcx, rax; hModule
0x180009ea1  call    cs:__imp_GetProcAddress
0x180009ea7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180009eae  test    rax, rax
0x180009eb1  jnz     short loc_180009EBA
0x180009eb3  mov     eax, 0C0000139h
0x180009eb8  jmp     short loc_180009ED7
0x180009eba  lea     r9, qword_1800416E0
0x180009ec1  xor     r8d, r8d
0x180009ec4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180009ecb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180009ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ed7  test    eax, eax
0x180009ed9  jnz     short loc_180009EF0
0x180009edb  mov     r9, rdi; void *
0x180009ede  lea     rcx, CriticalSection; this
0x180009ee5  mov     r8, rsi; void (*)(void *)
0x180009ee8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180009eeb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180009ef0  lea     rcx, stru_180041670; SRWLock
0x180009ef7  call    cs:__imp_ReleaseSRWLockExclusive
0x180009efd  mov     rbx, [rsp+38h+arg_0]
0x180009f02  mov     rsi, [rsp+38h+arg_8]
0x180009f07  add     rsp, 30h
0x180009f0b  pop     rdi
0x180009f0c  retn
```
