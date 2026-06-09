# EventService::InitializeGlobals(HINSTANCE__ *,TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider> &,bool)

- ea: `0x1800a4d68`
- end: `0x1800a5409`
- name: `?InitializeGlobals@EventService@@SAKPEAUHINSTANCE__@@AEAV?$TraceLoggingActivity@$1?g_hEventLogRpcActivityProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@_N@Z`
- size: `1697`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `reparse_path, registry_config, service_task`

## callers

- `0x18009daf0`

## callees

- `0x180001008`
- `0x180004a3c`
- `0x180006770`
- `0x18000a180`
- `0x180016250`
- `0x180017b98`
- `0x180031cc8`
- `0x180033418`
- `0x180033ae0`
- `0x180039778`
- `0x180064854`
- `0x18006d16c`
- `0x180092008`
- `0x180092ee4`
- `0x1800978a0`
- `0x18009aee0`
- `0x1800a4d68`
- `0x1800afd74`
- `0x1800bcff8`
- `0x1800be4b8`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x1800a4eb1`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x1800a4eb1`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800a4edb`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800a4f2a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800a4f7b`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800a4fcc`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800a501d`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800a506e`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800a50bf`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800a4edb`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800a4f2a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800a4f7b`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800a4fcc`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800a501d`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800a506e`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800a50bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a5283`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a5283`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a5358`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a5358`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a536c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a536c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5100`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5139`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5100`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5139`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800a512f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800a512f`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x1800a5300`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x1800a5300`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EventService::InitializeGlobals(__int64 a1, _DWORD *a2, char a3)
{
  HMODULE v4; // r14
  HKEY v5; // rdx
  const wchar_t *v6; // r8
  HKEY v7; // r9
  int *v8; // r9
  RegistryPaths *v9; // rcx
  DWORD v10; // eax
  unsigned int v11; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  struct _PERF_COUNTERSET_INSTANCE *Instance; // rax
  ULONG v15; // eax
  ULONG v16; // eax
  ULONG v17; // eax
  ULONG v18; // eax
  ULONG v19; // eax
  ULONG v20; // eax
  ULONG LastError; // eax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r9
  unsigned int v25; // eax
  char v26; // r14
  HKEY *v27; // rax
  LCID ThreadLocale; // eax
  unsigned int v29; // edx
  __int64 result; // rax
  PublisherManifestResource *v31; // rax
  __int64 v32; // r9
  const wchar_t *phkResult; // [rsp+20h] [rbp-2A8h]
  PublisherManifestResource *v34; // [rsp+30h] [rbp-298h] BYREF
  utl::_RefCountBase *v35; // [rsp+38h] [rbp-290h]
  EvtException *v36; // [rsp+40h] [rbp-288h] BYREF
  int v37; // [rsp+48h] [rbp-280h] BYREF
  char v38; // [rsp+4Ch] [rbp-27Ch]
  _BYTE v39[16]; // [rsp+50h] [rbp-278h] BYREF
  int v40; // [rsp+60h] [rbp-268h] BYREF
  int v41; // [rsp+64h] [rbp-264h]
  int v42; // [rsp+68h] [rbp-260h]
  int v43; // [rsp+6Ch] [rbp-25Ch]
  WCHAR Filename[264]; // [rsp+70h] [rbp-258h] BYREF

  v4 = hModule;
  v37 = 0;
  v40 = a2[2];
  v41 = a2[3];
  v42 = a2[4];
  v43 = a2[5];
  v38 = 1;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v37);
  if ( (unsigned int)dword_18010F008 > 5 )
  {
    if ( v38 && (v40 || v41 || v42 || v43) )
      v8 = &v40;
    else
      v8 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_18010F008,
      byte_1800FC0D3,
      v39,
      v8);
  }
  v9 = (RegistryPaths *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids);
  }
  v10 = RegistryPaths::Initialize(v9, v5, v6, v7, phkResult);
  v11 = v10;
  if ( v10 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_99;
    }
    v13 = 11;
LABEL_98:
    WPP_SF_d(v12[2], v13, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v10);
LABEL_99:
    TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>::~TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>(&v37);
    return v11;
  }
  Instance = PerfCreateInstance(WevtEventLogCounterProvider, &WevtEventLogCounterSetGuid, L"EventLogCounters", 1u);
  g_WevtCounterInstance = Instance;
  if ( Instance )
  {
    v15 = PerfSetCounterRefValue(WevtEventLogCounterProvider, Instance, 1u, &g_EnabledChannels);
    if ( v15
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v15);
    }
    v16 = PerfSetCounterRefValue(WevtEventLogCounterProvider, g_WevtCounterInstance, 9u, &g_ActiveChannels);
    if ( v16
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v16);
    }
    v17 = PerfSetCounterRefValue(WevtEventLogCounterProvider, g_WevtCounterInstance, 2u, &g_WevtRpcCallsTotal);
    if ( v17
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v17);
    }
    v18 = PerfSetCounterRefValue(WevtEventLogCounterProvider, g_WevtCounterInstance, 3u, &g_EventCount);
    if ( v18
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v18);
    }
    v19 = PerfSetCounterRefValue(WevtEventLogCounterProvider, g_WevtCounterInstance, 4u, &g_ElfRpcCallsTotal);
    if ( v19
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v19);
    }
    v20 = PerfSetCounterRefValue(WevtEventLogCounterProvider, g_WevtCounterInstance, 5u, &g_ActiveSubscriptionCount);
    if ( v20
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v20);
    }
    LastError = PerfSetCounterRefValue(
                  WevtEventLogCounterProvider,
                  g_WevtCounterInstance,
                  6u,
                  &g_FilterMatchingCallsTotal);
    if ( LastError )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v23 = 18;
LABEL_59:
        WPP_SF_d(v22[2], v23, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, LastError);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    v23 = 19;
    v22 = WPP_GLOBAL_Control;
    goto LABEL_59;
  }
  if ( !GetModuleFileNameW(v4, Filename, 0x104u) )
  {
    v10 = GetLastError();
    v11 = v10;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_99;
    }
    v13 = 20;
    goto LABEL_98;
  }
  utl::make_shared<PublisherManifestResource,>(&v34);
  if ( !v34 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 14);
    }
    if ( v35 )
      utl::_RefCountBase::_DecStrong(v35);
    v11 = 14;
    goto LABEL_99;
  }
  v25 = PublisherManifestResource::Open(v34, Filename, &EVENTLOG, v24, 0);
  v11 = v25;
  if ( v25 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        (unsigned int)&WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
        (unsigned int)Filename,
        v25);
    }
    if ( v35 )
      utl::_RefCountBase::_DecStrong(v35);
    goto LABEL_99;
  }
  utl::shared_ptr<PublisherManifestResource>::operator=(&g_eventLogPmRes, &v34);
  if ( v35 )
    utl::_RefCountBase::_DecStrong(v35);
  v26 = 0;
  v34 = 0;
  v27 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v34);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MiniNt", 0, 1u, v27) )
  {
    v26 = 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids);
    }
  }
  if ( (unsigned __int8)AreAnyRestrictionsEnabled(0x4000) )
  {
    v26 = 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids);
    }
  }
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v34);
  PublisherMetadata::InitializeEnvironmentPathTable();
  ThreadLocale = GetThreadLocale();
  v10 = EventRendering::InitializeGlobals((EventRendering *)ThreadLocale, v29);
  v11 = v10;
  if ( v10 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_99;
    }
    v13 = 25;
    goto LABEL_98;
  }
  AcquireSRWLockExclusive(&stru_180111D68);
  byte_18010F654 = 0;
  ReleaseSRWLockExclusive(&stru_180111D68);
  try
  {
    v31 = (PublisherManifestResource *)operator new(0x1E8u);
    v34 = v31;
    if ( v31 )
      v31 = EventService::EventService(v31, a3, v26);
    g_service = (PSRWLOCK)v31;
    v37 = 2;
    if ( (unsigned int)dword_18010F008 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_18010F008,
        &word_1800FC116,
        v39,
        0);
    TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>::~TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>(&v37);
    result = 0;
  }
  catch ( EvtException *v36 )
  {
    v32 = *((unsigned int *)v36 + 6);
    LODWORD(v34) = *((_DWORD *)v36 + 6);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v32);
    }
    TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>::~TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>(&v37);
    return (unsigned int)v34;
  }
  return result;
}

```

## disassembly

```asm
0x1800a4d68  push    rbx
0x1800a4d6a  push    rsi
0x1800a4d6b  push    rdi
0x1800a4d6c  push    r13
0x1800a4d6e  push    r14
0x1800a4d70  push    r15
0x1800a4d72  sub     rsp, 298h
0x1800a4d79  mov     rax, cs:__security_cookie
0x1800a4d80  xor     rax, rsp
0x1800a4d83  mov     [rsp+2C8h+var_48], rax
0x1800a4d8b  mov     r15b, r8b
0x1800a4d8e  mov     r14, cs:hModule
0x1800a4d95  mov     [rsp+2C8h+var_280], 0
0x1800a4d9d  mov     eax, [rdx+8]
0x1800a4da0  mov     [rsp+2C8h+var_268], eax
0x1800a4da4  mov     eax, [rdx+0Ch]
0x1800a4da7  mov     [rsp+2C8h+var_264], eax
0x1800a4dab  mov     eax, [rdx+10h]
0x1800a4dae  mov     [rsp+2C8h+var_260], eax
0x1800a4db2  mov     eax, [rdx+14h]
0x1800a4db5  mov     [rsp+2C8h+var_25C], eax
0x1800a4db9  mov     [rsp+2C8h+var_27C], 1
0x1800a4dbe  lea     rcx, [rsp+2C8h+var_280]
0x1800a4dc3  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hEventLogRpcActivityProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x1800a4dc8  mov     eax, cs:dword_18010F008
0x1800a4dce  cmp     eax, 5
0x1800a4dd1  jbe     short loc_1800A4E18
0x1800a4dd3  cmp     [rsp+2C8h+var_27C], 0
0x1800a4dd8  jz      short loc_1800A4DFD
0x1800a4dda  cmp     [rsp+2C8h+var_268], 0
0x1800a4ddf  jnz     short loc_1800A4DF6
0x1800a4de1  cmp     [rsp+2C8h+var_264], 0
0x1800a4de6  jnz     short loc_1800A4DF6
0x1800a4de8  cmp     [rsp+2C8h+var_260], 0
0x1800a4ded  jnz     short loc_1800A4DF6
0x1800a4def  cmp     [rsp+2C8h+var_25C], 0
0x1800a4df4  jz      short loc_1800A4DFD
0x1800a4df6  lea     r9, [rsp+2C8h+var_268]
0x1800a4dfb  jmp     short loc_1800A4E00
0x1800a4dfd  xor     r9d, r9d
0x1800a4e00  lea     r8, [rsp+2C8h+var_278]
0x1800a4e05  lea     rdx, byte_1800FC0D3
0x1800a4e0c  lea     rcx, dword_18010F008
0x1800a4e13  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800a4e18  lea     r13, WPP_GLOBAL_Control
0x1800a4e1f  mov     rcx, cs:WPP_GLOBAL_Control; this
0x1800a4e26  mov     dil, 8
0x1800a4e29  cmp     rcx, r13
0x1800a4e2c  jz      short loc_1800A4E54
0x1800a4e2e  test    [rcx+1Ch], dil
0x1800a4e32  jz      short loc_1800A4E54
0x1800a4e34  lea     rsi, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x1800a4e3b  cmp     byte ptr [rcx+19h], 4
0x1800a4e3f  jb      short loc_1800A4E5B
0x1800a4e41  mov     edx, 0Ah
0x1800a4e46  mov     r8, rsi
0x1800a4e49  mov     rcx, [rcx+10h]
0x1800a4e4d  call    WPP_SF_
0x1800a4e52  jmp     short loc_1800A4E5B
0x1800a4e54  lea     rsi, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x1800a4e5b  call    ?Initialize@RegistryPaths@@QEAAKPEAUHKEY__@@PEB_W01@Z; RegistryPaths::Initialize(HKEY__ *,wchar_t const *,HKEY__ *,wchar_t const *)
0x1800a4e60  mov     ebx, eax
0x1800a4e62  test    eax, eax
0x1800a4e64  jz      short loc_1800A4E94
0x1800a4e66  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4e6d  cmp     rcx, r13
0x1800a4e70  jz      loc_1800A5340
0x1800a4e76  test    [rcx+1Ch], dil
0x1800a4e7a  jz      loc_1800A5340
0x1800a4e80  cmp     byte ptr [rcx+19h], 2
0x1800a4e84  jb      loc_1800A5340
0x1800a4e8a  mov     edx, 0Bh
0x1800a4e8f  jmp     loc_1800A5330
0x1800a4e94  mov     ebx, 1
0x1800a4e99  mov     r9d, ebx; Id
0x1800a4e9c  lea     r8, aEventlogcounte; "EventLogCounters"
0x1800a4ea3  lea     rdx, WevtEventLogCounterSetGuid; CounterSetGuid
0x1800a4eaa  mov     rcx, cs:WevtEventLogCounterProvider; ProviderHandle
0x1800a4eb1  call    cs:__imp_PerfCreateInstance
0x1800a4eb7  mov     cs:?g_WevtCounterInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA, rax; _PERF_COUNTERSET_INSTANCE * g_WevtCounterInstance
0x1800a4ebe  test    rax, rax
0x1800a4ec1  jz      loc_1800A50E8
0x1800a4ec7  lea     r9, ?g_EnabledChannels@@3JA; Address
0x1800a4ece  mov     r8d, ebx; CounterId
0x1800a4ed1  mov     rdx, rax; Instance
0x1800a4ed4  mov     rcx, cs:WevtEventLogCounterProvider; Provider
0x1800a4edb  call    cs:__imp_PerfSetCounterRefValue
0x1800a4ee1  test    eax, eax
0x1800a4ee3  jz      short loc_1800A4F0F
0x1800a4ee5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4eec  cmp     rcx, r13
0x1800a4eef  jz      short loc_1800A4F0F
0x1800a4ef1  test    [rcx+1Ch], dil
0x1800a4ef5  jz      short loc_1800A4F0F
0x1800a4ef7  cmp     byte ptr [rcx+19h], 2
0x1800a4efb  jb      short loc_1800A4F0F
0x1800a4efd  lea     edx, [rbx+0Bh]
0x1800a4f00  mov     r9d, eax
0x1800a4f03  mov     r8, rsi
0x1800a4f06  mov     rcx, [rcx+10h]
0x1800a4f0a  call    WPP_SF_d
0x1800a4f0f  lea     r9, ?g_ActiveChannels@@3JA; Address
0x1800a4f16  mov     r8d, 9; CounterId
0x1800a4f1c  mov     rdx, cs:?g_WevtCounterInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA; Instance
0x1800a4f23  mov     rcx, cs:WevtEventLogCounterProvider; Provider
0x1800a4f2a  call    cs:__imp_PerfSetCounterRefValue
0x1800a4f30  test    eax, eax
0x1800a4f32  jz      short loc_1800A4F60
0x1800a4f34  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4f3b  cmp     rcx, r13
0x1800a4f3e  jz      short loc_1800A4F60
0x1800a4f40  test    [rcx+1Ch], dil
0x1800a4f44  jz      short loc_1800A4F60
0x1800a4f46  cmp     byte ptr [rcx+19h], 2
0x1800a4f4a  jb      short loc_1800A4F60
0x1800a4f4c  mov     edx, 0Dh
0x1800a4f51  mov     r9d, eax
0x1800a4f54  mov     r8, rsi
0x1800a4f57  mov     rcx, [rcx+10h]
0x1800a4f5b  call    WPP_SF_d
0x1800a4f60  lea     r9, ?g_WevtRpcCallsTotal@@3_JA; Address
0x1800a4f67  mov     r8d, 2; CounterId
0x1800a4f6d  mov     rdx, cs:?g_WevtCounterInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA; Instance
0x1800a4f74  mov     rcx, cs:WevtEventLogCounterProvider; Provider
0x1800a4f7b  call    cs:__imp_PerfSetCounterRefValue
0x1800a4f81  test    eax, eax
0x1800a4f83  jz      short loc_1800A4FB1
0x1800a4f85  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4f8c  cmp     rcx, r13
0x1800a4f8f  jz      short loc_1800A4FB1
0x1800a4f91  test    [rcx+1Ch], dil
0x1800a4f95  jz      short loc_1800A4FB1
0x1800a4f97  cmp     byte ptr [rcx+19h], 2
0x1800a4f9b  jb      short loc_1800A4FB1
0x1800a4f9d  mov     edx, 0Eh
0x1800a4fa2  mov     r9d, eax
0x1800a4fa5  mov     r8, rsi
0x1800a4fa8  mov     rcx, [rcx+10h]
0x1800a4fac  call    WPP_SF_d
0x1800a4fb1  lea     r9, ?g_EventCount@@3_JA; Address
0x1800a4fb8  mov     r8d, 3; CounterId
0x1800a4fbe  mov     rdx, cs:?g_WevtCounterInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA; Instance
0x1800a4fc5  mov     rcx, cs:WevtEventLogCounterProvider; Provider
0x1800a4fcc  call    cs:__imp_PerfSetCounterRefValue
0x1800a4fd2  test    eax, eax
0x1800a4fd4  jz      short loc_1800A5002
0x1800a4fd6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4fdd  cmp     rcx, r13
0x1800a4fe0  jz      short loc_1800A5002
0x1800a4fe2  test    [rcx+1Ch], dil
0x1800a4fe6  jz      short loc_1800A5002
0x1800a4fe8  cmp     byte ptr [rcx+19h], 2
0x1800a4fec  jb      short loc_1800A5002
0x1800a4fee  mov     edx, 0Fh
0x1800a4ff3  mov     r9d, eax
0x1800a4ff6  mov     r8, rsi
0x1800a4ff9  mov     rcx, [rcx+10h]
0x1800a4ffd  call    WPP_SF_d
0x1800a5002  lea     r9, ?g_ElfRpcCallsTotal@@3_JA; Address
0x1800a5009  mov     r8d, 4; CounterId
0x1800a500f  mov     rdx, cs:?g_WevtCounterInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA; Instance
0x1800a5016  mov     rcx, cs:WevtEventLogCounterProvider; Provider
0x1800a501d  call    cs:__imp_PerfSetCounterRefValue
0x1800a5023  test    eax, eax
0x1800a5025  jz      short loc_1800A5053
0x1800a5027  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a502e  cmp     rcx, r13
0x1800a5031  jz      short loc_1800A5053
0x1800a5033  test    [rcx+1Ch], dil
0x1800a5037  jz      short loc_1800A5053
0x1800a5039  cmp     byte ptr [rcx+19h], 2
0x1800a503d  jb      short loc_1800A5053
0x1800a503f  mov     edx, 10h
0x1800a5044  mov     r9d, eax
0x1800a5047  mov     r8, rsi
0x1800a504a  mov     rcx, [rcx+10h]
0x1800a504e  call    WPP_SF_d
0x1800a5053  lea     r9, ?g_ActiveSubscriptionCount@@3JA; Address
0x1800a505a  mov     r8d, 5; CounterId
0x1800a5060  mov     rdx, cs:?g_WevtCounterInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA; Instance
0x1800a5067  mov     rcx, cs:WevtEventLogCounterProvider; Provider
0x1800a506e  call    cs:__imp_PerfSetCounterRefValue
0x1800a5074  test    eax, eax
0x1800a5076  jz      short loc_1800A50A4
0x1800a5078  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a507f  cmp     rcx, r13
0x1800a5082  jz      short loc_1800A50A4
0x1800a5084  test    [rcx+1Ch], dil
0x1800a5088  jz      short loc_1800A50A4
0x1800a508a  cmp     byte ptr [rcx+19h], 2
0x1800a508e  jb      short loc_1800A50A4
0x1800a5090  mov     edx, 11h
0x1800a5095  mov     r9d, eax
0x1800a5098  mov     r8, rsi
0x1800a509b  mov     rcx, [rcx+10h]
0x1800a509f  call    WPP_SF_d
0x1800a50a4  lea     r9, ?g_FilterMatchingCallsTotal@@3_JA; Address
0x1800a50ab  mov     r8d, 6; CounterId
0x1800a50b1  mov     rdx, cs:?g_WevtCounterInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA; Instance
0x1800a50b8  mov     rcx, cs:WevtEventLogCounterProvider; Provider
0x1800a50bf  call    cs:__imp_PerfSetCounterRefValue
0x1800a50c5  test    eax, eax
0x1800a50c7  jz      short loc_1800A5121
0x1800a50c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a50d0  cmp     rcx, r13
0x1800a50d3  jz      short loc_1800A5121
0x1800a50d5  test    [rcx+1Ch], dil
0x1800a50d9  jz      short loc_1800A5121
0x1800a50db  cmp     byte ptr [rcx+19h], 2
0x1800a50df  jb      short loc_1800A5121
0x1800a50e1  mov     edx, 12h
0x1800a50e6  jmp     short loc_1800A5112
0x1800a50e8  mov     rax, cs:WPP_GLOBAL_Control
0x1800a50ef  cmp     rax, r13
0x1800a50f2  jz      short loc_1800A5121
0x1800a50f4  test    [rax+1Ch], dil
0x1800a50f8  jz      short loc_1800A5121
0x1800a50fa  cmp     byte ptr [rax+19h], 2
0x1800a50fe  jb      short loc_1800A5121
0x1800a5100  call    cs:__imp_GetLastError
0x1800a5106  mov     edx, 13h
0x1800a510b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5112  mov     r9d, eax
0x1800a5115  mov     r8, rsi
0x1800a5118  mov     rcx, [rcx+10h]
0x1800a511c  call    WPP_SF_d
0x1800a5121  mov     r8d, 104h; nSize
0x1800a5127  lea     rdx, [rsp+2C8h+Filename]; lpFilename
0x1800a512c  mov     rcx, r14; hModule
0x1800a512f  call    cs:__imp_GetModuleFileNameW
0x1800a5135  test    eax, eax
0x1800a5137  jnz     short loc_1800A516F
0x1800a5139  call    cs:__imp_GetLastError
0x1800a513f  mov     ebx, eax
0x1800a5141  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5148  cmp     rcx, r13
0x1800a514b  jz      loc_1800A5340
0x1800a5151  test    [rcx+1Ch], dil
0x1800a5155  jz      loc_1800A5340
0x1800a515b  cmp     byte ptr [rcx+19h], 2
0x1800a515f  jb      loc_1800A5340
0x1800a5165  mov     edx, 14h
0x1800a516a  jmp     loc_1800A5330
0x1800a516f  lea     rcx, [rsp+2C8h+var_298]
0x1800a5174  call    ??$make_shared@VPublisherManifestResource@@$$V@utl@@YA?AV?$shared_ptr@VPublisherManifestResource@@@0@XZ; utl::make_shared<PublisherManifestResource,>(void)
0x1800a5179  mov     rcx, [rsp+2C8h+var_298]; this
0x1800a517e  test    rcx, rcx
0x1800a5181  jnz     short loc_1800A51CB
0x1800a5183  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a518a  cmp     rcx, r13
0x1800a518d  jz      short loc_1800A51B1
0x1800a518f  test    [rcx+1Ch], dil
0x1800a5193  jz      short loc_1800A51B1
0x1800a5195  cmp     byte ptr [rcx+19h], 2
0x1800a5199  jb      short loc_1800A51B1
0x1800a519b  mov     edx, 15h
0x1800a51a0  lea     r9d, [rdx-7]
0x1800a51a4  mov     r8, rsi
0x1800a51a7  mov     rcx, [rcx+10h]
0x1800a51ab  call    WPP_SF_d
0x1800a51b0  nop
0x1800a51b1  mov     rcx, [rsp+2C8h+var_290]; this
0x1800a51b6  test    rcx, rcx
0x1800a51b9  jz      short loc_1800A51C1
0x1800a51bb  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800a51c0  nop
0x1800a51c1  mov     ebx, 0Eh
0x1800a51c6  jmp     loc_1800A5340
0x1800a51cb  mov     byte ptr [rsp+2C8h+phkResult], 0; bool
0x1800a51d0  lea     r8, EVENTLOG; struct _GUID *
0x1800a51d7  lea     rdx, [rsp+2C8h+Filename]; wchar_t *
0x1800a51dc  call    ?Open@PublisherManifestResource@@QEAAKPEB_WPEBU_GUID@@_N2@Z; PublisherManifestResource::Open(wchar_t const *,_GUID const *,bool,bool)
0x1800a51e1  mov     ebx, eax
0x1800a51e3  test    eax, eax
0x1800a51e5  jz      short loc_1800A522F
0x1800a51e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a51ee  cmp     rcx, r13
0x1800a51f1  jz      short loc_1800A521A
0x1800a51f3  test    [rcx+1Ch], dil
0x1800a51f7  jz      short loc_1800A521A
0x1800a51f9  cmp     byte ptr [rcx+19h], 2
0x1800a51fd  jb      short loc_1800A521A
0x1800a51ff  mov     edx, 16h
0x1800a5204  mov     dword ptr [rsp+2C8h+phkResult], eax
0x1800a5208  lea     r9, [rsp+2C8h+Filename]
0x1800a520d  mov     r8, rsi
0x1800a5210  mov     rcx, [rcx+10h]
0x1800a5214  call    WPP_SF_Sd
0x1800a5219  nop
0x1800a521a  mov     rcx, [rsp+2C8h+var_290]; this
0x1800a521f  test    rcx, rcx
0x1800a5222  jz      short loc_1800A522A
0x1800a5224  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800a5229  nop
0x1800a522a  jmp     loc_1800A5340
0x1800a522f  lea     rdx, [rsp+2C8h+var_298]
0x1800a5234  lea     rcx, ?g_eventLogPmRes@@3V?$shared_ptr@VPublisherManifestResource@@@utl@@A; utl::shared_ptr<PublisherManifestResource> g_eventLogPmRes
0x1800a523b  call    ??4?$shared_ptr@VPublisherManifestResource@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::shared_ptr<PublisherManifestResource>::operator=(utl::shared_ptr<PublisherManifestResource> &&)
0x1800a5240  nop
0x1800a5241  mov     rcx, [rsp+2C8h+var_290]; this
  ... truncated ...
```
