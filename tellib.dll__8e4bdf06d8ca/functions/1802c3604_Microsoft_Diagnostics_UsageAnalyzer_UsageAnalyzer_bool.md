# Microsoft::Diagnostics::UsageAnalyzer::UsageAnalyzer(bool)

- ea: `0x1802c3604`
- end: `0x1802c3c49`
- name: `??0UsageAnalyzer@Diagnostics@Microsoft@@QEAA@_N@Z`
- size: `1605`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::UsageAnalyzer *__hidden this, bool)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801817c4`

## callees

- `0x180024ee0`
- `0x18003eb78`
- `0x180040b90`
- `0x18004dcf0`
- `0x18009efa0`
- `0x18009f7f0`
- `0x1800a1ce8`
- `0x1800a1e24`
- `0x1800b84fc`
- `0x18012de40`
- `0x1801f84d0`
- `0x1801fa574`
- `0x180273bf8`
- `0x1802c339c`
- `0x1802c33e8`
- `0x1802c34a0`
- `0x1802c35ac`
- `0x1802c3604`
- `0x1802c6918`
- `0x1802c6bbc`
- `0x1802c8054`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1802c3acf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1802c3b0f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1802c3b4f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1802c3acf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1802c3b0f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1802c3b4f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1802c3c00`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1802c3c00`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1802c3672`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1802c3730`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1802c3672`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1802c3730`

## string_xrefs

- `0x1802c3ae7`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x1802c3b27`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x1802c3b67`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
Microsoft::Diagnostics::UsageAnalyzer *__fastcall Microsoft::Diagnostics::UsageAnalyzer::UsageAnalyzer(
        Microsoft::Diagnostics::UsageAnalyzer *this)
{
  __int64 v2; // rcx
  __int64 RegistryConfig; // rax
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v5; // r9
  PTP_TIMER v6; // rax
  const char *v7; // r9
  PTP_TIMER v8; // rax
  const char *v9; // r9
  __int64 v10; // rax
  __int64 v11; // rbx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h]
  __int128 v16; // [rsp+50h] [rbp-B0h] BYREF
  Microsoft::Diagnostics::UsageAnalyzer *v17; // [rsp+60h] [rbp-A0h]
  _BYTE v18[224]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v17 = this;
  Microsoft::Diagnostics::ProcessStateEventBasedMetadata::ProcessStateEventBasedMetadata(this);
  *(_QWORD *)this = &Microsoft::Diagnostics::UsageAnalyzer::`vftable'{for `Microsoft::Diagnostics::ProcessStateEventBasedMetadata'};
  *((_QWORD *)this + 20) = &Microsoft::Diagnostics::UsageAnalyzer::`vftable'{for `Microsoft::Diagnostics::IRundownProducer'};
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 2 * GetTickCount64();
  *((_QWORD *)this + 25) = 258;
  *((_OWORD *)this + 14) = 0;
  *((_OWORD *)this + 15) = 0;
  *((_OWORD *)this + 16) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_DWORD *)this + 68) = -1;
  *((_DWORD *)this + 69) = 0;
  Microsoft::Diagnostics::UsageAnalyzer::ScenarioStats::ScenarioStats((Microsoft::Diagnostics::UsageAnalyzer *)((char *)this + 280));
  *((_QWORD *)this + 41) = 258;
  *((_OWORD *)this + 22) = 0;
  *((_OWORD *)this + 23) = 0;
  *((_OWORD *)this + 24) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_DWORD *)this + 100) = -1;
  *((_DWORD *)this + 101) = 0;
  Microsoft::Diagnostics::UsageAnalyzer::DerivedEventStats::DerivedEventStats((Microsoft::Diagnostics::UsageAnalyzer *)((char *)this + 408));
  *((_QWORD *)this + 71) = 0;
  *((_BYTE *)this + 576) = 0;
  *((_QWORD *)this + 73) = GetTickCount64();
  *((_QWORD *)this + 74) = 258;
  *(_OWORD *)((char *)this + 616) = 0;
  *(_OWORD *)((char *)this + 632) = 0;
  *(_OWORD *)((char *)this + 648) = 0;
  *((_QWORD *)this + 75) = 0;
  *((_QWORD *)this + 76) = 0;
  *((_DWORD *)this + 166) = -1;
  *((_DWORD *)this + 167) = 0;
  pftDueTime = (struct _FILETIME)((char *)this + 672);
  *((_DWORD *)this + 168) = 0;
  *((_QWORD *)this + 85) = 0;
  *((_QWORD *)this + 86) = 0;
  std::list<std::pair<Microsoft::Diagnostics::TraceRequestOccurrenceTracker::OccurrenceKey const,std::vector<unsigned long>>>::_Alloc_sentinel_and_proxy((char *)this + 680);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>((_QWORD *)this + 87);
  *((_QWORD *)this + 90) = 7;
  *((_QWORD *)this + 91) = 8;
  *((_DWORD *)this + 168) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,Microsoft::Diagnostics::AppIdMetadata::SessionInfo>>>>>>::_Assign_grow(
    v2,
    16,
    *((_QWORD *)this + 85));
  *((_QWORD *)this + 92) = 258;
  *(_OWORD *)((char *)this + 760) = 0;
  *(_OWORD *)((char *)this + 776) = 0;
  *(_OWORD *)((char *)this + 792) = 0;
  *((_QWORD *)this + 93) = 0;
  *((_QWORD *)this + 94) = 0;
  *((_DWORD *)this + 202) = -1;
  *((_DWORD *)this + 203) = 0;
  Microsoft::Diagnostics::UsageAnalyzer::AggregatedAsimovData::AggregatedAsimovData((Microsoft::Diagnostics::UsageAnalyzer *)((char *)this + 816));
  *((_QWORD *)this + 106) = 258;
  *(_OWORD *)((char *)this + 872) = 0;
  *(_OWORD *)((char *)this + 888) = 0;
  *(_OWORD *)((char *)this + 904) = 0;
  *((_QWORD *)this + 107) = 0;
  *((_QWORD *)this + 108) = 0;
  *((_DWORD *)this + 230) = -1;
  *((_DWORD *)this + 231) = 0;
  Microsoft::Diagnostics::UsageAnalyzer::ReportScenarioStats::ReportScenarioStats((Microsoft::Diagnostics::UsageAnalyzer *)((char *)this + 928));
  *((_QWORD *)this + 121) = 258;
  *((_OWORD *)this + 62) = 0;
  *((_OWORD *)this + 63) = 0;
  *((_OWORD *)this + 64) = 0;
  *((_QWORD *)this + 122) = 0;
  *((_QWORD *)this + 123) = 0;
  *((_DWORD *)this + 260) = -1;
  *((_DWORD *)this + 261) = 0;
  *((_QWORD *)this + 131) = 0;
  *((_QWORD *)this + 132) = 0;
  std::_Tree<std::_Tmap_traits<std::wstring const,std::unique_ptr<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const,std::default_delete<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>>,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::unique_ptr<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const,std::default_delete<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>>>>,0>>::_Alloc_sentinel_and_proxy((char *)this + 1048);
  pftDueTime.dwLowDateTime = 0;
  v14 = L"PersistInprocInfo";
  v15 = 17;
  v16 = *(_OWORD *)&off_180348470;
  RegistryConfig = Microsoft::Diagnostics::DynamicConfig<unsigned long>::CreateRegistryConfig(
                     (unsigned int)v18,
                     (unsigned int)&pftDueTime,
                     (unsigned int)&v16,
                     (unsigned int)&v14,
                     0);
  *((_DWORD *)this + 266) = Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get(RegistryConfig);
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::~DynamicConfig<unsigned long>((struct Microsoft::Diagnostics::ISettingReceiver *)v18);
  *((_QWORD *)this + 134) = 258;
  *(_OWORD *)((char *)this + 1096) = 0;
  *(_OWORD *)((char *)this + 1112) = 0;
  *(_OWORD *)((char *)this + 1128) = 0;
  *((_QWORD *)this + 135) = 0;
  *((_QWORD *)this + 136) = 0;
  *((_DWORD *)this + 286) = -1;
  *((_DWORD *)this + 287) = 0;
  *((_QWORD *)this + 144) = 0;
  *((_QWORD *)this + 145) = 0;
  *((_QWORD *)this + 146) = 0;
  *((_QWORD *)this + 147) = 258;
  *((_OWORD *)this + 75) = 0;
  *((_OWORD *)this + 76) = 0;
  *((_OWORD *)this + 77) = 0;
  *((_QWORD *)this + 148) = 0;
  *((_QWORD *)this + 149) = 0;
  *((_DWORD *)this + 312) = -1;
  *((_DWORD *)this + 313) = 0;
  *((_QWORD *)this + 157) = 258;
  *((_OWORD *)this + 80) = 0;
  *((_OWORD *)this + 81) = 0;
  *((_OWORD *)this + 82) = 0;
  *((_QWORD *)this + 158) = 0;
  *((_QWORD *)this + 159) = 0;
  *((_DWORD *)this + 332) = -1;
  *((_DWORD *)this + 333) = 0;
  *((_QWORD *)this + 167) = 0;
  *((_QWORD *)this + 168) = -1;
  *((_QWORD *)this + 169) = 0;
  *((_QWORD *)this + 170) = 0;
  *((_QWORD *)this + 171) = 0;
  *((_QWORD *)this + 172) = 0;
  *((_QWORD *)this + 173) = -1;
  *((_QWORD *)this + 174) = 0;
  *((_QWORD *)this + 175) = 0;
  *((_QWORD *)this + 176) = 0;
  *((_QWORD *)this + 177) = 0;
  *((_QWORD *)this + 178) = -1;
  *((_QWORD *)this + 179) = 0;
  *((_QWORD *)this + 180) = 0;
  *((_QWORD *)this + 181) = 0;
  *((_QWORD *)this + 182) = 0;
  *((_QWORD *)this + 183) = 0;
  *((_QWORD *)this + 184) = 0;
  *((_QWORD *)this + 185) = 0;
  *((_QWORD *)this + 186) = 0;
  *((_QWORD *)this + 187) = 0;
  *((_QWORD *)this + 188) = Microsoft::Diagnostics::Utils::Time::QueryUbiTime();
  *((_QWORD *)this + 189) = 0;
  *((_QWORD *)this + 190) = 0;
  *((_QWORD *)this + 191) = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Alloc_sentinel_and_proxy();
  *((_QWORD *)this + 192) = 0;
  *((_QWORD *)this + 193) = 0;
  *((_QWORD *)this + 194) = 0;
  *((_BYTE *)this + 1560) = 0;
  ThreadpoolTimer = CreateThreadpoolTimer(
                      Microsoft::Diagnostics::Utils::Os::MethodToTpTimerCallbackAdapter<Microsoft::Diagnostics::UsageAnalyzer,{public: void Microsoft::Diagnostics::UsageAnalyzer::ClearReportState(void),0}>,
                      this,
                      0);
  if ( !ThreadpoolTimer )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x12,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
      v5);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 176,
    ThreadpoolTimer);
  v6 = CreateThreadpoolTimer(
         Microsoft::Diagnostics::Utils::Os::MethodToTpTimerCallbackAdapter<Microsoft::Diagnostics::UsageAnalyzer,{private: void Microsoft::Diagnostics::UsageAnalyzer::LogStatsToSynthetic(void),0}>,
         this,
         0);
  if ( !v6 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x17,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
      v7);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 168,
    v6);
  v8 = CreateThreadpoolTimer(
         Microsoft::Diagnostics::Utils::Os::MethodToTpTimerCallbackAdapter<Microsoft::Diagnostics::UsageAnalyzer const,{[thunk]: Microsoft::Diagnostics::UsageAnalyzer::`vcall'{8,{flat}},160}>,
         this,
         0);
  if ( !v8 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
      v9);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 184,
    v8);
  pftDueTime.dwLowDateTime = 0;
  v14 = L"UsageAnalyzerTimer_DoCaptureState";
  v15 = 33;
  v16 = *(_OWORD *)&off_180348470;
  v10 = Microsoft::Diagnostics::DynamicConfig<unsigned long>::CreateRegistryConfig(
          (unsigned int)v18,
          (unsigned int)&pftDueTime,
          (unsigned int)&v16,
          (unsigned int)&v14,
          0);
  v11 = (unsigned int)Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get(v10);
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::~DynamicConfig<unsigned long>((struct Microsoft::Diagnostics::ISettingReceiver *)v18);
  if ( (_DWORD)v11 )
  {
    pftDueTime = (struct _FILETIME)(-10000 * v11);
    SetThreadpoolTimer(*((PTP_TIMER *)this + 23), &pftDueTime, v11, 0x2710u);
  }
  Microsoft::Diagnostics::UsageAnalyzer::RefreshReportEnabled(this);
  Microsoft::Diagnostics::UsageAnalyzer::RearmLogStatsToSyntheticTimer(this);
  Microsoft::Diagnostics::ProcessStateEventBasedMetadata::RegisterForAppStateChangeEvents(this);
  return this;
}

```

## disassembly

```asm
0x1802c3604  push    rbp
0x1802c3606  push    rbx
0x1802c3607  push    rsi
0x1802c3608  push    rdi
0x1802c3609  push    r12
0x1802c360b  push    r13
0x1802c360d  push    r14
0x1802c360f  push    r15
0x1802c3611  lea     rbp, [rsp-68h]
0x1802c3616  sub     rsp, 168h
0x1802c361d  mov     rax, cs:__security_cookie
0x1802c3624  xor     rax, rsp
0x1802c3627  mov     [rbp+0A0h+var_50], rax
0x1802c362b  mov     rsi, rcx
0x1802c362e  mov     [rsp+1A0h+var_140], rcx
0x1802c3633  call    ??0ProcessStateEventBasedMetadata@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ProcessStateEventBasedMetadata::ProcessStateEventBasedMetadata(void)
0x1802c3638  nop
0x1802c3639  lea     rax, ??_7UsageAnalyzer@Diagnostics@Microsoft@@6BProcessStateEventBasedMetadata@12@@; const Microsoft::Diagnostics::UsageAnalyzer::`vftable'{for `Microsoft::Diagnostics::ProcessStateEventBasedMetadata'}
0x1802c3640  mov     [rsi], rax
0x1802c3643  lea     rax, ??_7UsageAnalyzer@Diagnostics@Microsoft@@6BIRundownProducer@12@@; const Microsoft::Diagnostics::UsageAnalyzer::`vftable'{for `Microsoft::Diagnostics::IRundownProducer'}
0x1802c364a  mov     [rsi+0A0h], rax
0x1802c3651  lea     r15, [rsi+0A8h]
0x1802c3658  xor     ebx, ebx
0x1802c365a  mov     [r15], rbx
0x1802c365d  lea     r14, [rsi+0B0h]
0x1802c3664  mov     [r14], rbx
0x1802c3667  lea     r12, [rsi+0B8h]
0x1802c366e  mov     [r12], rbx
0x1802c3672  call    cs:__imp_GetTickCount64
0x1802c3679  nop     dword ptr [rax+rax+00h]
0x1802c367e  add     rax, rax
0x1802c3681  mov     [rsi+0C0h], rax
0x1802c3688  mov     qword ptr [rsi+0C8h], 102h
0x1802c3693  xorps   xmm0, xmm0
0x1802c3696  movups  xmmword ptr [rsi+0E0h], xmm0
0x1802c369d  movups  xmmword ptr [rsi+0F0h], xmm0
0x1802c36a4  movups  xmmword ptr [rsi+100h], xmm0
0x1802c36ab  mov     [rsi+0D0h], rbx
0x1802c36b2  mov     [rsi+0D8h], rbx
0x1802c36b9  mov     dword ptr [rsi+110h], 0FFFFFFFFh
0x1802c36c3  mov     [rsi+114h], ebx
0x1802c36c9  lea     rcx, [rsi+118h]; this
0x1802c36d0  call    ??0ScenarioStats@UsageAnalyzer@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::UsageAnalyzer::ScenarioStats::ScenarioStats(void)
0x1802c36d5  nop
0x1802c36d6  mov     qword ptr [rsi+148h], 102h
0x1802c36e1  xorps   xmm0, xmm0
0x1802c36e4  movups  xmmword ptr [rsi+160h], xmm0
0x1802c36eb  movups  xmmword ptr [rsi+170h], xmm0
0x1802c36f2  movups  xmmword ptr [rsi+180h], xmm0
0x1802c36f9  mov     [rsi+150h], rbx
0x1802c3700  mov     [rsi+158h], rbx
0x1802c3707  mov     dword ptr [rsi+190h], 0FFFFFFFFh
0x1802c3711  mov     [rsi+194h], ebx
0x1802c3717  lea     rcx, [rsi+198h]; this
0x1802c371e  call    ??0DerivedEventStats@UsageAnalyzer@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::UsageAnalyzer::DerivedEventStats::DerivedEventStats(void)
0x1802c3723  mov     [rsi+238h], rbx
0x1802c372a  mov     [rsi+240h], bl
0x1802c3730  call    cs:__imp_GetTickCount64
0x1802c3737  nop     dword ptr [rax+rax+00h]
0x1802c373c  mov     [rsi+248h], rax
0x1802c3743  mov     qword ptr [rsi+250h], 102h
0x1802c374e  xorps   xmm0, xmm0
0x1802c3751  movups  xmmword ptr [rsi+268h], xmm0
0x1802c3758  movups  xmmword ptr [rsi+278h], xmm0
0x1802c375f  movups  xmmword ptr [rsi+288h], xmm0
0x1802c3766  mov     [rsi+258h], rbx
0x1802c376d  mov     [rsi+260h], rbx
0x1802c3774  mov     dword ptr [rsi+298h], 0FFFFFFFFh
0x1802c377e  mov     [rsi+29Ch], ebx
0x1802c3784  lea     rdi, [rsi+2A0h]
0x1802c378b  mov     qword ptr [rsp+1A0h+pftDueTime.dwLowDateTime], rdi
0x1802c3790  mov     [rdi], ebx
0x1802c3792  lea     rbx, [rdi+8]
0x1802c3796  mov     qword ptr [rbx], 0
0x1802c379d  mov     qword ptr [rbx+8], 0
0x1802c37a5  mov     rcx, rbx
0x1802c37a8  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@$$CBUOccurrenceKey@TraceRequestOccurrenceTracker@Diagnostics@Microsoft@@V?$vector@KV?$allocator@K@std@@@std@@@std@@V?$allocator@U?$pair@$$CBUOccurrenceKey@TraceRequestOccurrenceTracker@Diagnostics@Microsoft@@V?$vector@KV?$allocator@K@std@@@std@@@std@@@2@@std@@AEAAXXZ; std::list<std::pair<Microsoft::Diagnostics::TraceRequestOccurrenceTracker::OccurrenceKey const,std::vector<ulong>>>::_Alloc_sentinel_and_proxy(void)
0x1802c37ad  nop
0x1802c37ae  lea     rcx, [rdi+18h]; void *
0x1802c37b2  call    ??$?0AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(std::allocator<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>> const &)
0x1802c37b7  nop
0x1802c37b8  mov     qword ptr [rdi+30h], 7
0x1802c37c0  mov     qword ptr [rdi+38h], 8
0x1802c37c8  mov     dword ptr [rdi], 3F800000h
0x1802c37ce  mov     r8, [rbx]
0x1802c37d1  mov     edx, 10h
0x1802c37d6  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKUSessionInfo@AppIdMetadata@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKUSessionInfo@AppIdMetadata@Diagnostics@Microsoft@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,Microsoft::Diagnostics::AppIdMetadata::SessionInfo>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,Microsoft::Diagnostics::AppIdMetadata::SessionInfo>>>>)
0x1802c37db  nop
0x1802c37dc  mov     qword ptr [rsi+2E0h], 102h
0x1802c37e7  xorps   xmm0, xmm0
0x1802c37ea  movups  xmmword ptr [rsi+2F8h], xmm0
0x1802c37f1  movups  xmmword ptr [rsi+308h], xmm0
0x1802c37f8  movups  xmmword ptr [rsi+318h], xmm0
0x1802c37ff  xor     edi, edi
0x1802c3801  mov     [rsi+2E8h], rdi
0x1802c3808  mov     [rsi+2F0h], rdi
0x1802c380f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1802c3813  mov     [rsi+328h], ebx
0x1802c3819  mov     [rsi+32Ch], edi
0x1802c381f  lea     rcx, [rsi+330h]; this
0x1802c3826  call    ??0AggregatedAsimovData@UsageAnalyzer@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::UsageAnalyzer::AggregatedAsimovData::AggregatedAsimovData(void)
0x1802c382b  nop
0x1802c382c  mov     qword ptr [rsi+350h], 102h
0x1802c3837  xorps   xmm0, xmm0
0x1802c383a  movups  xmmword ptr [rsi+368h], xmm0
0x1802c3841  movups  xmmword ptr [rsi+378h], xmm0
0x1802c3848  movups  xmmword ptr [rsi+388h], xmm0
0x1802c384f  mov     [rsi+358h], rdi
0x1802c3856  mov     [rsi+360h], rdi
0x1802c385d  mov     [rsi+398h], ebx
0x1802c3863  mov     [rsi+39Ch], edi
0x1802c3869  lea     rcx, [rsi+3A0h]; this
0x1802c3870  call    ??0ReportScenarioStats@UsageAnalyzer@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::UsageAnalyzer::ReportScenarioStats::ReportScenarioStats(void)
0x1802c3875  nop
0x1802c3876  mov     qword ptr [rsi+3C8h], 102h
0x1802c3881  xorps   xmm0, xmm0
0x1802c3884  movups  xmmword ptr [rsi+3E0h], xmm0
0x1802c388b  movups  xmmword ptr [rsi+3F0h], xmm0
0x1802c3892  movups  xmmword ptr [rsi+400h], xmm0
0x1802c3899  mov     [rsi+3D0h], rdi
0x1802c38a0  mov     [rsi+3D8h], rdi
0x1802c38a7  mov     [rsi+410h], ebx
0x1802c38ad  mov     [rsi+414h], edi
0x1802c38b3  lea     rcx, [rsi+418h]
0x1802c38ba  mov     [rcx], rdi
0x1802c38bd  mov     [rcx+8], rdi
0x1802c38c1  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@$$CBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@U?$default_delete@$$CBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@@std@@@2@U?$less@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@$$CBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@U?$default_delete@$$CBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring const,std::unique_ptr<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>> const,std::default_delete<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>> const>>,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::unique_ptr<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>> const,std::default_delete<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>> const>>>>,0>>::_Alloc_sentinel_and_proxy(void)
0x1802c38c6  nop
0x1802c38c7  mov     [rsp+1A0h+pftDueTime.dwLowDateTime], edi
0x1802c38cb  lea     rax, aPersistinproci; "PersistInprocInfo"
0x1802c38d2  mov     [rsp+1A0h+var_160], rax
0x1802c38d7  mov     [rsp+1A0h+var_158], 11h
0x1802c38e0  movups  xmm0, xmmword ptr cs:off_180348470; "%DiagtrackRegistryRoot%\\UsageAnalyzer"
0x1802c38e7  movdqu  [rsp+1A0h+var_150], xmm0
0x1802c38ed  mov     [rsp+1A0h+var_180], dil
0x1802c38f2  lea     r9, [rsp+1A0h+var_160]
0x1802c38f7  lea     r8, [rsp+1A0h+var_150]
0x1802c38fc  lea     rdx, [rsp+1A0h+pftDueTime]
0x1802c3901  lea     rcx, [rsp+1A0h+var_130]
0x1802c3906  call    ?CreateRegistryConfig@?$DynamicConfig@K@Diagnostics@Microsoft@@SA?AV123@AEBKV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1_N@Z; Microsoft::Diagnostics::DynamicConfig<ulong>::CreateRegistryConfig(ulong const &,std::wstring_view,std::wstring_view,bool)
0x1802c390b  nop
0x1802c390c  mov     rcx, rax
0x1802c390f  call    ?Get@?$DynamicConfig@K@Diagnostics@Microsoft@@QEBAKXZ; Microsoft::Diagnostics::DynamicConfig<ulong>::Get(void)
0x1802c3914  mov     [rsi+428h], eax
0x1802c391a  lea     rcx, [rsp+1A0h+var_130]
0x1802c391f  call    ??1?$DynamicConfig@K@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::DynamicConfig<ulong>::~DynamicConfig<ulong>(void)
0x1802c3924  mov     qword ptr [rsi+430h], 102h
0x1802c392f  xorps   xmm0, xmm0
0x1802c3932  movups  xmmword ptr [rsi+448h], xmm0
0x1802c3939  movups  xmmword ptr [rsi+458h], xmm0
0x1802c3940  movups  xmmword ptr [rsi+468h], xmm0
0x1802c3947  mov     [rsi+438h], rdi
0x1802c394e  mov     [rsi+440h], rdi
0x1802c3955  mov     [rsi+478h], ebx
0x1802c395b  mov     [rsi+47Ch], edi
0x1802c3961  mov     [rsi+480h], rdi
0x1802c3968  mov     [rsi+488h], rdi
0x1802c396f  mov     [rsi+490h], rdi
0x1802c3976  mov     qword ptr [rsi+498h], 102h
0x1802c3981  movups  xmmword ptr [rsi+4B0h], xmm0
0x1802c3988  movups  xmmword ptr [rsi+4C0h], xmm0
0x1802c398f  movups  xmmword ptr [rsi+4D0h], xmm0
0x1802c3996  mov     [rsi+4A0h], rdi
0x1802c399d  mov     [rsi+4A8h], rdi
0x1802c39a4  mov     [rsi+4E0h], ebx
0x1802c39aa  mov     [rsi+4E4h], edi
0x1802c39b0  mov     qword ptr [rsi+4E8h], 102h
0x1802c39bb  movups  xmmword ptr [rsi+500h], xmm0
0x1802c39c2  movups  xmmword ptr [rsi+510h], xmm0
0x1802c39c9  movups  xmmword ptr [rsi+520h], xmm0
0x1802c39d0  mov     [rsi+4F0h], rdi
0x1802c39d7  mov     [rsi+4F8h], rdi
0x1802c39de  mov     [rsi+530h], ebx
0x1802c39e4  mov     [rsi+534h], edi
0x1802c39ea  mov     [rsi+538h], rdi
0x1802c39f1  mov     [rsi+540h], rbx
0x1802c39f8  mov     [rsi+548h], rdi
0x1802c39ff  mov     [rsi+550h], rdi
0x1802c3a06  mov     [rsi+558h], rdi
0x1802c3a0d  mov     [rsi+560h], rdi
0x1802c3a14  mov     [rsi+568h], rbx
0x1802c3a1b  mov     [rsi+570h], rdi
0x1802c3a22  mov     [rsi+578h], rdi
0x1802c3a29  mov     [rsi+580h], rdi
0x1802c3a30  mov     [rsi+588h], rdi
0x1802c3a37  mov     [rsi+590h], rbx
0x1802c3a3e  mov     [rsi+598h], rdi
0x1802c3a45  mov     [rsi+5A0h], rdi
0x1802c3a4c  mov     [rsi+5A8h], rdi
0x1802c3a53  mov     [rsi+5B0h], rdi
0x1802c3a5a  mov     [rsi+5B8h], rdi
0x1802c3a61  mov     [rsi+5C0h], rdi
0x1802c3a68  mov     [rsi+5C8h], rdi
0x1802c3a6f  mov     [rsi+5D0h], rdi
0x1802c3a76  mov     [rsi+5D8h], rdi
0x1802c3a7d  call    ?QueryUbiTime@Time@Utils@Diagnostics@Microsoft@@SA_KXZ; Microsoft::Diagnostics::Utils::Time::QueryUbiTime(void)
0x1802c3a82  mov     [rsi+5E0h], rax
0x1802c3a89  lea     rax, [rsi+5E8h]
0x1802c3a90  mov     [rax], rdi
0x1802c3a93  lea     rcx, [rax+8]
0x1802c3a97  mov     [rcx], rdi
0x1802c3a9a  mov     [rcx+8], rdi
0x1802c3a9e  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Alloc_sentinel_and_proxy(void)
0x1802c3aa3  nop
0x1802c3aa4  xor     eax, eax
0x1802c3aa6  mov     [rsi+600h], rax
0x1802c3aad  mov     [rsi+608h], rax
0x1802c3ab4  mov     [rsi+610h], rdi
0x1802c3abb  mov     [rsi+618h], dil
0x1802c3ac2  xor     r8d, r8d; pcbe
0x1802c3ac5  mov     rdx, rsi; pv
0x1802c3ac8  lea     rcx, ??$MethodToTpTimerCallbackAdapter@VUsageAnalyzer@Diagnostics@Microsoft@@$H?ClearReportState@123@QEAAXXZA@@Os@Utils@Diagnostics@Microsoft@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1802c3acf  call    cs:__imp_CreateThreadpoolTimer
0x1802c3ad6  nop     dword ptr [rax+rax+00h]
0x1802c3adb  mov     rcx, [rbp+0A8h]; this
0x1802c3ae2  test    rax, rax
0x1802c3ae5  jnz     short loc_1802C3AF7
0x1802c3ae7  lea     r8, aOnecoreBaseTel_153; "onecore\\base\\telemetry\\utc\\service"...
0x1802c3aee  lea     edx, [rdi+12h]; void *
0x1802c3af1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1802c3af7  mov     rdx, rax
0x1802c3afa  mov     rcx, r14
0x1802c3afd  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1802c3b02  xor     r8d, r8d; pcbe
0x1802c3b05  mov     rdx, rsi; pv
0x1802c3b08  lea     rcx, ??$MethodToTpTimerCallbackAdapter@VUsageAnalyzer@Diagnostics@Microsoft@@$H?LogStatsToSynthetic@123@AEAAXXZA@@Os@Utils@Diagnostics@Microsoft@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1802c3b0f  call    cs:__imp_CreateThreadpoolTimer
0x1802c3b16  nop     dword ptr [rax+rax+00h]
0x1802c3b1b  mov     rcx, [rbp+0A8h]; this
0x1802c3b22  test    rax, rax
0x1802c3b25  jnz     short loc_1802C3B37
0x1802c3b27  lea     r8, aOnecoreBaseTel_153; "onecore\\base\\telemetry\\utc\\service"...
0x1802c3b2e  lea     edx, [rax+17h]; void *
0x1802c3b31  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1802c3b37  mov     rdx, rax
0x1802c3b3a  mov     rcx, r15
0x1802c3b3d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1802c3b42  xor     r8d, r8d; pcbe
0x1802c3b45  mov     rdx, rsi; pv
0x1802c3b48  lea     rcx, ??$MethodToTpTimerCallbackAdapter@$$CBVUsageAnalyzer@Diagnostics@Microsoft@@$H??_9123@$B7AAKA@@Os@Utils@Diagnostics@Microsoft@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1802c3b4f  call    cs:__imp_CreateThreadpoolTimer
0x1802c3b56  nop     dword ptr [rax+rax+00h]
0x1802c3b5b  mov     rcx, [rbp+0A8h]; this
0x1802c3b62  test    rax, rax
0x1802c3b65  jnz     short loc_1802C3B77
0x1802c3b67  lea     r8, aOnecoreBaseTel_153; "onecore\\base\\telemetry\\utc\\service"...
0x1802c3b6e  lea     edx, [rax+1Ch]; void *
0x1802c3b71  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1802c3b77  mov     rdx, rax
0x1802c3b7a  mov     rcx, r12
0x1802c3b7d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1802c3b82  mov     [rsp+1A0h+pftDueTime.dwLowDateTime], edi
0x1802c3b86  lea     rax, aUsageanalyzert_1; "UsageAnalyzerTimer_DoCaptureState"
0x1802c3b8d  mov     [rsp+1A0h+var_160], rax
0x1802c3b92  mov     [rsp+1A0h+var_158], 21h ; '!'
0x1802c3b9b  movups  xmm0, xmmword ptr cs:off_180348470; "%DiagtrackRegistryRoot%\\UsageAnalyzer"
0x1802c3ba2  movdqu  [rsp+1A0h+var_150], xmm0
0x1802c3ba8  mov     [rsp+1A0h+var_180], dil
0x1802c3bad  lea     r9, [rsp+1A0h+var_160]
0x1802c3bb2  lea     r8, [rsp+1A0h+var_150]
0x1802c3bb7  lea     rdx, [rsp+1A0h+pftDueTime]
0x1802c3bbc  lea     rcx, [rsp+1A0h+var_130]
0x1802c3bc1  call    ?CreateRegistryConfig@?$DynamicConfig@K@Diagnostics@Microsoft@@SA?AV123@AEBKV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1_N@Z; Microsoft::Diagnostics::DynamicConfig<ulong>::CreateRegistryConfig(ulong const &,std::wstring_view,std::wstring_view,bool)
0x1802c3bc6  nop
0x1802c3bc7  mov     rcx, rax
0x1802c3bca  call    ?Get@?$DynamicConfig@K@Diagnostics@Microsoft@@QEBAKXZ; Microsoft::Diagnostics::DynamicConfig<ulong>::Get(void)
0x1802c3bcf  mov     ebx, eax
0x1802c3bd1  lea     rcx, [rsp+1A0h+var_130]
0x1802c3bd6  call    ??1?$DynamicConfig@K@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::DynamicConfig<ulong>::~DynamicConfig<ulong>(void)
0x1802c3bdb  test    ebx, ebx
0x1802c3bdd  jz      short loc_1802C3C0C
0x1802c3bdf  imul    rdx, rbx, 0FFFFFFFFFFFFD8F0h
0x1802c3be6  mov     qword ptr [rsp+1A0h+pftDueTime.dwLowDateTime], rdx
0x1802c3beb  mov     r9d, 2710h; msWindowLength
0x1802c3bf1  mov     r8d, ebx; msPeriod
0x1802c3bf4  lea     rdx, [rsp+1A0h+pftDueTime]; pftDueTime
0x1802c3bf9  mov     rcx, [rsi+0B8h]; pti
0x1802c3c00  call    cs:__imp_SetThreadpoolTimer
0x1802c3c07  nop     dword ptr [rax+rax+00h]
0x1802c3c0c  mov     rcx, rsi; this
0x1802c3c0f  call    ?RefreshReportEnabled@UsageAnalyzer@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::UsageAnalyzer::RefreshReportEnabled(void)
0x1802c3c14  mov     rcx, rsi; this
0x1802c3c17  call    ?RearmLogStatsToSyntheticTimer@UsageAnalyzer@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::UsageAnalyzer::RearmLogStatsToSyntheticTimer(void)
0x1802c3c1c  mov     rcx, rsi; this
0x1802c3c1f  call    ?RegisterForAppStateChangeEvents@ProcessStateEventBasedMetadata@Diagnostics@Microsoft@@IEAAXXZ; Microsoft::Diagnostics::ProcessStateEventBasedMetadata::RegisterForAppStateChangeEvents(void)
0x1802c3c24  nop
0x1802c3c25  mov     rax, rsi
0x1802c3c28  mov     rcx, [rbp+0A0h+var_50]
0x1802c3c2c  xor     rcx, rsp; StackCookie
0x1802c3c2f  call    __security_check_cookie
0x1802c3c34  add     rsp, 168h
0x1802c3c3b  pop     r15
0x1802c3c3d  pop     r14
0x1802c3c3f  pop     r13
0x1802c3c41  pop     r12
0x1802c3c43  pop     rdi
0x1802c3c44  pop     rsi
0x1802c3c45  pop     rbx
0x1802c3c46  pop     rbp
0x1802c3c47  retn
  ... truncated ...
```
