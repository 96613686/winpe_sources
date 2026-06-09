# Vml::VmServiceModule<GuestComputeServiceModule>::main(int,ushort * *)

- ea: `0x14003d6c0`
- end: `0x14003db37`
- name: `?main@?$VmServiceModule@VGuestComputeServiceModule@@@Vml@@QEAAHHPEAPEAG@Z`
- size: `1143`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14003db98`

## callees

- `0x1400015b4`
- `0x140005360`
- `0x140006098`
- `0x140009f8c`
- `0x14000aeec`
- `0x14000ddac`
- `0x14000e120`
- `0x14000e7a0`
- `0x14003c5c8`
- `0x14003c64c`
- `0x14003c824`
- `0x14003cd60`
- `0x14003cee4`
- `0x14003d4f0`
- `0x14003d6c0`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14003d93d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14003d963`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14003d93d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14003d963`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14003d7f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14003d7f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003d708`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003d708`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x14003d71e`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x14003d745`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x14003d71e`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x14003d745`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x14003d867`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x14003d867`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x14003da36`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x14003da36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14003d756`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14003d7ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14003d756`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14003d7ab`
- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x14003d9b7`
- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x14003d9b7`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x14003d770`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x14003d7c6`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x14003d770`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x14003d7c6`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x14003d792`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x14003d7e9`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x14003d792`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x14003d7e9`

## string_xrefs

- `0x14003da7d`: `onecore\vm\common\vml\VmModules.h`
- `0x14003da96`: `onecore\vm\common\vml\VmModules.h`
- `0x14003daaf`: `onecore\vm\common\vml\VmModules.h`
- `0x14003dac8`: `onecore\vm\common\vml\VmModules.h`
- `0x14003db12`: `onecore\vm\common\vml\VmModules.h`
- `0x14003db24`: `onecore\vm\common\vml\VmModules.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Vml::VmServiceModule<GuestComputeServiceModule>::main(__int64 a1, int a2, __int64 a3)
{
  HANDLE ProcessHeap; // rbx
  HANDLE CurrentProcess; // rax
  int ProcessMitigationPolicy; // eax
  const char *v8; // r9
  const char *v9; // r9
  HANDLE v10; // rax
  const char *v11; // r9
  const char *v12; // r9
  LPCGUID v13; // rbx
  void *v14; // rax
  const char *v15; // r9
  int i; // ebx
  _WORD *v17; // rcx
  _WORD *v18; // r14
  const char *v19; // r9
  __int64 v20; // rax
  REGHANDLE v21; // rcx
  const struct wil::FailureInfo *v23; // rdx
  const struct wil::FailureInfo *v24; // rdx
  __int64 v25; // [rsp+20h] [rbp-F8h]
  _BYTE v26[160]; // [rsp+30h] [rbp-E8h] BYREF
  int HeapInformation; // [rsp+D0h] [rbp-48h] BYREF
  int v28; // [rsp+D4h] [rbp-44h] BYREF
  SERVICE_TABLE_ENTRYW ServiceStartTable; // [rsp+D8h] [rbp-40h] BYREF
  __int64 v30; // [rsp+E8h] [rbp-30h]
  __int64 v31; // [rsp+F0h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  ProcessHeap = GetProcessHeap();
  HeapSetInformation(ProcessHeap, HeapEnableTerminationOnCorruption, 0, 0);
  HeapInformation = 2;
  HeapSetInformation(ProcessHeap, HeapCompatibilityInformation, &HeapInformation, 4u);
  v28 = 0;
  CurrentProcess = GetCurrentProcess();
  ProcessMitigationPolicy = GetProcessMitigationPolicy(CurrentProcess, 3, &v28, 4, 0);
  try
  {
    if ( !ProcessMitigationPolicy )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x62D,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v8);
    v28 |= 3u;
    if ( !(unsigned int)SetProcessMitigationPolicy(3, &v28, 4) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x638,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v9);
    HeapInformation = 0;
    v10 = GetCurrentProcess();
    if ( !(unsigned int)GetProcessMitigationPolicy(v10, 6, &HeapInformation, 4, v25) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x647,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v11);
    HeapInformation |= 1u;
    if ( !(unsigned int)SetProcessMitigationPolicy(6, &HeapInformation, 4) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x651,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v12);
    GetModuleHandleW(0);
    Vml::VmModuleBase::gm_ModuleBase = &g_Module;
    VmlDebugSetDefaultTraceFilter();
    _InterlockedExchange64(
      (volatile __int64 *)&g_TraceOutput,
      (__int64)wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy);
    if ( wil::details::g_pfnLoggingCallback
      && (void (__fastcall *)(const struct wil::FailureInfo *))wil::details::g_pfnLoggingCallback != VmlpTraceWilFailure )
    {
      memset_0(v26, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v26, v23);
    }
    wil::details::g_pfnLoggingCallback = (__int64)VmlpTraceWilFailure;
    v13 = ProviderId;
    if ( ProviderId )
    {
      Vml::VmpModuleInfo::Initalize();
      if ( !EventRegister(v13, VmlEtwTraceFilterCallback, 0, (PREGHANDLE)&v13[1].Data1) )
      {
        _InterlockedExchange64((volatile __int64 *)&g_TraceOutput, (__int64)VmlpEtwUnifiedTraceOutput);
        g_VmlEtwTrace = (struct _VML_ETW_TRACE *)v13;
        g_TraceEventEnabled = (unsigned __int8 (*)(unsigned __int16))VmlIsEtwTraceEnabled;
      }
    }
    else
    {
      ProviderId = 0;
    }
    if ( (*(__int64 (__fastcall **)(void *))(g_Module + 48LL))(&g_Module) )
    {
      v14 = (void *)(*(__int64 (__fastcall **)(void *))(g_Module + 40LL))(&g_Module);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(v14);
    }
    if ( wil::details::g_pfnTelemetryCallback
      && (void (__fastcall *)(bool, const struct wil::FailureInfo *))wil::details::g_pfnTelemetryCallback != ComputeService::Diagnostics::TraceProvider::FallbackTelemetryCallback )
    {
      memset_0(v26, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v26, v24);
    }
    wil::details::g_pfnTelemetryCallback = (__int64)ComputeService::Diagnostics::TraceProvider::FallbackTelemetryCallback;
    *((_DWORD *)ComputeService::Diagnostics::TraceProvider::Instance() + 5) = 2;
    if ( a2 <= 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xB33,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v15);
    for ( i = 0; i < a2 - 1; ++i )
    {
      v17 = *(_WORD **)(a3 + 8LL * i + 8);
      if ( ((*v17 - 45) & 0xFFFD) == 0 )
      {
        v18 = v17 + 1;
        if ( !(unsigned int)_o__wcsicmp(v17 + 1, L"regserver") )
        {
          Vml::VmServiceModule<GuestComputeServiceModule>::RegisterServer();
          goto LABEL_42;
        }
        if ( !(unsigned int)_o__wcsicmp(v18, L"unregserver") )
        {
          Vml::VmServiceModule<GuestComputeServiceModule>::UnregisterServer();
          goto LABEL_42;
        }
      }
    }
    ServiceStartTable.lpServiceName = (LPWSTR)Vml::VmServiceModule<GuestComputeServiceModule>::GetServiceName(&g_Module);
    ServiceStartTable.lpServiceProc = (LPSERVICE_MAIN_FUNCTIONW)Vml::VmServiceModule<GuestComputeServiceModule>::ServiceMain;
    v30 = 0;
    v31 = 0;
    if ( !StartServiceCtrlDispatcherW(&ServiceStartTable) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xB42,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v19);
  }
  catch ( ... )
  {
  }
LABEL_42:
  if ( qword_14015F828 )
    qword_14015F828();
  Vml::VmSharableObject::WaitUntilAllocatedObjectCountIsZero();
  VmlEtwTraceFinalize();
  if ( (*(__int64 (__fastcall **)(void *))(g_Module + 48LL))(&g_Module) )
  {
    v20 = (*(__int64 (__fastcall **)(void *))(g_Module + 40LL))(&g_Module);
    v21 = *(_QWORD *)(v20 + 32);
    *(_DWORD *)v20 = 0;
    *(_QWORD *)(v20 + 32) = 0;
    EventUnregister(v21);
  }
  Vml::VmModuleBase::gm_ModuleBase = 0;
  return 0;
}

```

## disassembly

```asm
0x14003d6c0  mov     [rsp+arg_0], rbx
0x14003d6c5  mov     [rsp+arg_8], rsi
0x14003d6ca  push    r12
0x14003d6cc  push    r14
0x14003d6ce  push    r15
0x14003d6d0  sub     rsp, 100h
0x14003d6d7  mov     rax, cs:__security_cookie
0x14003d6de  xor     rax, rsp
0x14003d6e1  mov     [rsp+118h+var_20], rax
0x14003d6e9  mov     r12, r8
0x14003d6ec  mov     r15d, edx
0x14003d6ef  lea     rsi, ?g_Module@@3VGuestComputeServiceModule@@A; GuestComputeServiceModule g_Module
0x14003d6f6  mov     [rsp+118h+var_F0], rsi
0x14003d6fb  mov     [rsp+118h+var_F4], 1
0x14003d703  mov     [rsp+118h+var_F8], 0
0x14003d708  call    cs:__imp_GetProcessHeap
0x14003d70e  mov     rbx, rax
0x14003d711  xor     r9d, r9d; HeapInformationLength
0x14003d714  xor     r8d, r8d; HeapInformation
0x14003d717  lea     edx, [r9+1]; HeapInformationClass
0x14003d71b  mov     rcx, rax; HeapHandle
0x14003d71e  call    cs:__imp_HeapSetInformation
0x14003d724  mov     [rsp+118h+HeapInformation], 2
0x14003d72f  mov     r14d, 4
0x14003d735  mov     r9d, r14d; HeapInformationLength
0x14003d738  lea     r8, [rsp+118h+HeapInformation]; HeapInformation
0x14003d740  xor     edx, edx; HeapInformationClass
0x14003d742  mov     rcx, rbx; HeapHandle
0x14003d745  call    cs:__imp_HeapSetInformation
0x14003d74b  mov     [rsp+118h+var_44], 0
0x14003d756  call    cs:__imp_GetCurrentProcess
0x14003d75c  mov     rcx, rax
0x14003d75f  mov     r9d, r14d
0x14003d762  lea     r8, [rsp+118h+var_44]
0x14003d76a  lea     ebx, [r14-1]
0x14003d76e  mov     edx, ebx
0x14003d770  call    cs:__imp_GetProcessMitigationPolicy
0x14003d776  test    eax, eax
0x14003d778  jz      loc_14003DA75
0x14003d77e  or      [rsp+118h+var_44], ebx
0x14003d785  mov     r8, r14
0x14003d788  lea     rdx, [rsp+118h+var_44]
0x14003d790  mov     ecx, ebx
0x14003d792  call    cs:__imp_SetProcessMitigationPolicy
0x14003d798  test    eax, eax
0x14003d79a  jz      loc_14003DA8E
0x14003d7a0  mov     [rsp+118h+HeapInformation], 0
0x14003d7ab  call    cs:__imp_GetCurrentProcess
0x14003d7b1  mov     rcx, rax
0x14003d7b4  mov     r9, r14
0x14003d7b7  lea     r8, [rsp+118h+HeapInformation]
0x14003d7bf  mov     ebx, 6
0x14003d7c4  mov     edx, ebx
0x14003d7c6  call    cs:__imp_GetProcessMitigationPolicy
0x14003d7cc  test    eax, eax
0x14003d7ce  jz      loc_14003DAA7
0x14003d7d4  or      [rsp+118h+HeapInformation], 1
0x14003d7dc  mov     r8, r14
0x14003d7df  lea     rdx, [rsp+118h+HeapInformation]
0x14003d7e7  mov     ecx, ebx
0x14003d7e9  call    cs:__imp_SetProcessMitigationPolicy
0x14003d7ef  test    eax, eax
0x14003d7f1  jz      loc_14003DAC0
0x14003d7f7  xor     ecx, ecx; lpModuleName
0x14003d7f9  call    cs:__imp_GetModuleHandleW
0x14003d7ff  mov     cs:?gm_ModuleBase@VmModuleBase@Vml@@1PEAV12@EA, rsi; Vml::VmModuleBase * Vml::VmModuleBase::gm_ModuleBase
0x14003d806  call    ?VmlDebugSetDefaultTraceFilter@@YAXXZ; VmlDebugSetDefaultTraceFilter(void)
0x14003d80b  lea     rax, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x14003d812  xchg    rax, cs:?g_TraceOutput@@3R6AXGPEBG@ZEA; void (*g_TraceOutput)(ushort,ushort const *)
0x14003d819  mov     rcx, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14003d820  lea     rax, ?VmlpTraceWilFailure@@YAXAEBUFailureInfo@wil@@@Z; VmlpTraceWilFailure(wil::FailureInfo const &)
0x14003d827  test    rcx, rcx
0x14003d82a  jz      short loc_14003D835
0x14003d82c  cmp     rcx, rax
0x14003d82f  jnz     loc_14003DAD9
0x14003d835  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rax
0x14003d83c  mov     rbx, cs:ProviderId
0x14003d843  test    rbx, rbx
0x14003d846  jnz     short loc_14003D851
0x14003d848  mov     cs:ProviderId, rbx
0x14003d84f  jmp     short loc_14003D894
0x14003d851  call    ?Initalize@VmpModuleInfo@Vml@@SAXXZ; Vml::VmpModuleInfo::Initalize(void)
0x14003d856  lea     r9, [rbx+10h]; RegHandle
0x14003d85a  xor     r8d, r8d; CallbackContext
0x14003d85d  lea     rdx, ?VmlEtwTraceFilterCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; EnableCallback
0x14003d864  mov     rcx, rbx; ProviderId
0x14003d867  call    cs:__imp_EventRegister
0x14003d86d  test    eax, eax
0x14003d86f  jnz     short loc_14003D894
0x14003d871  lea     rax, ?VmlpEtwUnifiedTraceOutput@@YAXGPEBG@Z; VmlpEtwUnifiedTraceOutput(ushort,ushort const *)
0x14003d878  xchg    rax, cs:?g_TraceOutput@@3R6AXGPEBG@ZEA; void (*g_TraceOutput)(ushort,ushort const *)
0x14003d87f  mov     cs:?g_VmlEtwTrace@@3PEAU_VML_ETW_TRACE@@EA, rbx; _VML_ETW_TRACE * g_VmlEtwTrace
0x14003d886  lea     rax, ?VmlIsEtwTraceEnabled@@YAEG@Z; VmlIsEtwTraceEnabled(ushort)
0x14003d88d  mov     cs:?g_TraceEventEnabled@@3P6AEG@ZEA, rax; uchar (*g_TraceEventEnabled)(ushort)
0x14003d894  mov     rax, cs:?g_Module@@3VGuestComputeServiceModule@@A; GuestComputeServiceModule g_Module
0x14003d89b  mov     rcx, rsi
0x14003d89e  mov     rax, [rax+30h]
0x14003d8a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d8a7  test    rax, rax
0x14003d8aa  jz      short loc_14003D8C7
0x14003d8ac  mov     rax, cs:?g_Module@@3VGuestComputeServiceModule@@A; GuestComputeServiceModule g_Module
0x14003d8b3  mov     rcx, rsi
0x14003d8b6  mov     rax, [rax+28h]
0x14003d8ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d8bf  mov     rcx, rax; CallbackContext
0x14003d8c2  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14003d8c7  mov     rcx, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x14003d8ce  lea     rax, ?FallbackTelemetryCallback@TraceProvider@Diagnostics@ComputeService@@SAX_NAEBUFailureInfo@wil@@@Z; ComputeService::Diagnostics::TraceProvider::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x14003d8d5  test    rcx, rcx
0x14003d8d8  jz      short loc_14003D8E3
0x14003d8da  cmp     rcx, rax
0x14003d8dd  jnz     loc_14003DAF6
0x14003d8e3  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rax
0x14003d8ea  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x14003d8ef  mov     dword ptr [rax+14h], 2
0x14003d8f6  mov     rcx, [rsp+118h]; this
0x14003d8fe  test    r15d, r15d
0x14003d901  jle     loc_14003DB12
0x14003d907  mov     [rsp+118h+var_F8], 1
0x14003d90c  xor     ebx, ebx
0x14003d90e  lea     eax, [r15-1]
0x14003d912  cmp     ebx, eax
0x14003d914  jge     short loc_14003D978
0x14003d916  movsxd  rax, ebx
0x14003d919  mov     rcx, [r12+rax*8+8]
0x14003d91e  movzx   eax, word ptr [rcx]
0x14003d921  sub     ax, 2Dh ; '-'
0x14003d925  mov     edx, 0FFFDh
0x14003d92a  test    dx, ax
0x14003d92d  jnz     short loc_14003D974
0x14003d92f  lea     r14, [rcx+2]
0x14003d933  lea     rdx, aRegserver; "regserver"
0x14003d93a  mov     rcx, r14
0x14003d93d  call    cs:__imp__o__wcsicmp
0x14003d943  test    eax, eax
0x14003d945  jnz     short loc_14003D959
0x14003d947  call    ?RegisterServer@?$VmServiceModule@VGuestComputeServiceModule@@@Vml@@QEAAXXZ; Vml::VmServiceModule<GuestComputeServiceModule>::RegisterServer(void)
0x14003d94c  mov     [rsp+118h+var_F4], 0
0x14003d954  jmp     loc_14003D9DE
0x14003d959  lea     rdx, aUnregserver; "unregserver"
0x14003d960  mov     rcx, r14
0x14003d963  call    cs:__imp__o__wcsicmp
0x14003d969  test    eax, eax
0x14003d96b  jnz     short loc_14003D974
0x14003d96d  call    ?UnregisterServer@?$VmServiceModule@VGuestComputeServiceModule@@@Vml@@QEAAXXZ; Vml::VmServiceModule<GuestComputeServiceModule>::UnregisterServer(void)
0x14003d972  jmp     short loc_14003D94C
0x14003d974  inc     ebx
0x14003d976  jmp     short loc_14003D90E
0x14003d978  mov     rcx, rsi
0x14003d97b  call    ?GetServiceName@?$VmServiceModule@VGuestComputeServiceModule@@@Vml@@QEBAPEBGXZ; Vml::VmServiceModule<GuestComputeServiceModule>::GetServiceName(void)
0x14003d980  mov     [rsp+118h+ServiceStartTable.lpServiceName], rax
0x14003d988  lea     rax, ?ServiceMain@?$VmServiceModule@VGuestComputeServiceModule@@@Vml@@CAXKPEAPEAG@Z; Vml::VmServiceModule<GuestComputeServiceModule>::ServiceMain(ulong,ushort * *)
0x14003d98f  mov     [rsp+118h+ServiceStartTable.lpServiceProc], rax
0x14003d997  mov     [rsp+118h+var_30], 0
0x14003d9a3  mov     [rsp+118h+var_28], 0
0x14003d9af  lea     rcx, [rsp+118h+ServiceStartTable]; lpServiceStartTable
0x14003d9b7  call    cs:__imp_StartServiceCtrlDispatcherW
0x14003d9bd  mov     rcx, [rsp+118h]; this
0x14003d9c5  test    eax, eax
0x14003d9c7  jz      loc_14003DB24
0x14003d9cd  jmp     loc_14003D94C
0x14003d9d2  cmp     [rsp+118h+var_F8], 0
0x14003d9d7  jz      short loc_14003DA47
0x14003d9d9  mov     rsi, [rsp+118h+var_F0]
0x14003d9de  mov     rax, cs:qword_14015F828
0x14003d9e5  test    rax, rax
0x14003d9e8  jz      short loc_14003D9EF
0x14003d9ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d9ef  call    ?WaitUntilAllocatedObjectCountIsZero@VmSharableObject@Vml@@SAXXZ; Vml::VmSharableObject::WaitUntilAllocatedObjectCountIsZero(void)
0x14003d9f4  call    ?VmlEtwTraceFinalize@@YAXXZ; VmlEtwTraceFinalize(void)
0x14003d9f9  mov     rax, cs:?g_Module@@3VGuestComputeServiceModule@@A; GuestComputeServiceModule g_Module
0x14003da00  mov     rcx, rsi
0x14003da03  mov     rax, [rax+30h]
0x14003da07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003da0c  test    rax, rax
0x14003da0f  jz      short loc_14003DA3C
0x14003da11  mov     rax, cs:?g_Module@@3VGuestComputeServiceModule@@A; GuestComputeServiceModule g_Module
0x14003da18  mov     rcx, rsi
0x14003da1b  mov     rax, [rax+28h]
0x14003da1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003da24  mov     rcx, [rax+20h]; RegHandle
0x14003da28  mov     dword ptr [rax], 0
0x14003da2e  mov     qword ptr [rax+20h], 0
0x14003da36  call    cs:__imp_EventUnregister
0x14003da3c  mov     cs:?gm_ModuleBase@VmModuleBase@Vml@@1PEAV12@EA, 0; Vml::VmModuleBase * Vml::VmModuleBase::gm_ModuleBase
0x14003da47  mov     eax, [rsp+118h+var_F4]
0x14003da4b  mov     rcx, [rsp+118h+var_20]
0x14003da53  xor     rcx, rsp; StackCookie
0x14003da56  call    __security_check_cookie
0x14003da5b  lea     r11, [rsp+118h+var_18]
0x14003da63  mov     rbx, [r11+20h]
0x14003da67  mov     rsi, [r11+28h]
0x14003da6b  mov     rsp, r11
0x14003da6e  pop     r15
0x14003da70  pop     r14
0x14003da72  pop     r12
0x14003da74  retn
0x14003da75  mov     rcx, [rsp+118h]; this
0x14003da7d  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\vml\\VmModules.h"
0x14003da84  mov     edx, 62Dh; void *
0x14003da89  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14003da8e  mov     rcx, [rsp+118h]; this
0x14003da96  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\vml\\VmModules.h"
0x14003da9d  mov     edx, 638h; void *
0x14003daa2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14003daa7  mov     rcx, [rsp+118h]; this
0x14003daaf  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\vml\\VmModules.h"
0x14003dab6  mov     edx, 647h; void *
0x14003dabb  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14003dac0  mov     rcx, [rsp+118h]; this
0x14003dac8  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\vml\\VmModules.h"
0x14003dacf  mov     edx, 651h; void *
0x14003dad4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14003dad9  xor     edx, edx; Val
0x14003dadb  mov     r8d, 98h; Size
0x14003dae1  lea     rcx, [rsp+118h+var_E8]; void *
0x14003dae6  call    memset_0
0x14003daeb  lea     rcx, [rsp+118h+var_E8]; this
0x14003daf0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14003daf6  xor     edx, edx; Val
0x14003daf8  mov     r8d, 98h; Size
0x14003dafe  lea     rcx, [rsp+118h+var_E8]; void *
0x14003db03  call    memset_0
0x14003db08  lea     rcx, [rsp+118h+var_E8]; this
0x14003db0d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14003db12  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\vml\\VmModules.h"
0x14003db19  mov     edx, 0B33h; void *
0x14003db1e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14003db24  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\vml\\VmModules.h"
0x14003db2b  mov     edx, 0B42h; void *
0x14003db30  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
