# Microsoft::Diagnostics::UsageAnalyzer::LogThreadCycleStatsToSynthetic(void)

- ea: `0x1800a74e0`
- end: `0x1800a7d2a`
- name: `?LogThreadCycleStatsToSynthetic@UsageAnalyzer@Diagnostics@Microsoft@@AEAAXXZ`
- size: `2122`
- prototype: `void __fastcall(Microsoft::Diagnostics::UsageAnalyzer *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180184c84`

## callees

- `0x18001c5b0`
- `0x18001d160`
- `0x1800333b0`
- `0x180040b90`
- `0x18005b974`
- `0x1800a5324`
- `0x1800a60e4`
- `0x1800a74e0`
- `0x1800a7d30`
- `0x1800a8324`
- `0x1800a8e5c`
- `0x18012de40`
- `0x180187284`
- `0x18023321c`
- `0x180233284`
- `0x1802be0a4`
- `0x1802c4f7c`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800a7cc5`
- `msvcp_win!_Mtx_unlock` at `0x1800a7cc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a7677`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a7741`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a7677`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a7741`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x1800a775a`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x1800a775a`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1800a791a`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1800a79d6`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1800a7a7a`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1800a791a`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1800a79d6`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1800a7a7a`

## string_xrefs

- `0x1800a78df`: `UpdateRulesCy`
- `0x1800a7adb`: `ConsumerThreadOverheadKCy`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Microsoft::Diagnostics::UsageAnalyzer::LogThreadCycleStatsToSynthetic(
        Microsoft::Diagnostics::UsageAnalyzer *this)
{
  unsigned __int64 UbiTime; // rdi
  HANDLE CurrentProcess; // rax
  unsigned __int64 v4; // r8
  double v5; // xmm0_8
  double v6; // xmm0_8
  double v7; // xmm1_8
  HANDLE v8; // rax
  unsigned __int64 v9; // rdi
  __int64 v10; // rcx
  double v11; // xmm0_8
  double v12; // xmm0_8
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // r15
  __int64 v15; // rcx
  double v16; // xmm0_8
  double v17; // xmm0_8
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rdi
  unsigned __int64 v20; // rsi
  void *v21; // rcx
  unsigned __int64 v22; // rdi
  unsigned __int64 v23; // rsi
  __int64 v24; // rdi
  __int64 v25; // r12
  unsigned __int64 v26; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B8h]
  __int128 v28; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int64 v29; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 CycleTime; // [rsp+78h] [rbp-90h] BYREF
  __int64 v31; // [rsp+80h] [rbp-88h]
  int v32[282]; // [rsp+98h] [rbp-70h] BYREF
  int v33[14]; // [rsp+500h] [rbp+3F8h] BYREF

  UbiTime = Microsoft::Diagnostics::Utils::Time::QueryUbiTime();
  *(_QWORD *)&v28 = L"UsageAnalyzer_PerfStats_0";
  *((_QWORD *)&v28 + 1) = 25;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
    (unsigned int)v32,
    (unsigned int)&v28,
    0x1000000,
    0,
    0,
    0,
    0);
  Microsoft::Diagnostics::Utils::Os::GetCpu0Name(&CycleTime);
  *(_QWORD *)&v28 = L"Cpu0Name";
  *((_QWORD *)&v28 + 1) = 8;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>((unsigned int)v32, (unsigned int)v33);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&CycleTime);
  Microsoft::Diagnostics::Utils::Os::GetCpu0Identifier(&CycleTime);
  *(_QWORD *)&v28 = L"Cpu0Id";
  *((_QWORD *)&v28 + 1) = 6;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>((unsigned int)v32, (unsigned int)v33);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&CycleTime);
  *(_QWORD *)&v28 = (char *)this + 1256;
  std::_Mutex_base::lock((Microsoft::Diagnostics::UsageAnalyzer *)((char *)this + 1256));
  CycleTime = (UbiTime - *((_QWORD *)this + 188)) / 0x989680;
  v26 = (unsigned __int64)L"TimeCoveredSec";
  v27 = 14;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((unsigned int)v32, (unsigned int)v33);
  *((_QWORD *)this + 188) = UbiTime;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcProcessPerf>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_UtcProcessPerf>::GetImpl'::`2'::impl) )
  {
    *(double *)&CycleTime = 0.0;
    v26 = 0;
    v29 = 0;
    CurrentProcess = GetCurrentProcess();
    Microsoft::Diagnostics::UsageAnalyzer::GetProcessTimesDelta(this, CurrentProcess, &CycleTime, &v26, &v29);
    if ( v29 )
    {
      v4 = CycleTime + v26;
      if ( (__int64)(CycleTime + v26) < 0 )
        v5 = (double)(int)(v4 & 1 | (v4 >> 1)) + (double)(int)(v4 & 1 | (v4 >> 1));
      else
        v5 = (double)(int)v4;
      v6 = v5 * 100.0;
      if ( (v29 & 0x8000000000000000uLL) != 0LL )
        v7 = (double)(int)(v29 & 1 | (v29 >> 1)) + (double)(int)(v29 & 1 | (v29 >> 1));
      else
        v7 = (double)(int)v29;
      *(double *)&CycleTime = v6 / v7;
      v26 = (unsigned __int64)L"ProcessCpuPercent";
      v27 = 17;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<double>((int)v32, (int)v33);
    }
  }
  v8 = GetCurrentProcess();
  *(double *)&CycleTime = 0.0;
  QueryProcessCycleTime(v8, &CycleTime);
  v9 = CycleTime;
  CycleTime = ((CycleTime - *((_QWORD *)this + 187)) & -(__int64)(*((_QWORD *)this + 187) < CycleTime)) / 0x3E8;
  v26 = (unsigned __int64)L"UtcProcessKCy";
  v27 = 13;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((unsigned int)v32, (unsigned int)v33);
  *((_QWORD *)this + 187) = v9;
  *(double *)&CycleTime = COERCE_DOUBLE(L"ConsumerCallbackCy");
  v31 = 18;
  Microsoft::Diagnostics::UsageAnalyzer::AddDistroInfoSyntheticField((unsigned int)v32);
  v10 = *((_QWORD *)this + 167);
  if ( v10 < 0 )
    v11 = (double)(int)(*((_DWORD *)this + 334) & 1 | ((unsigned __int64)v10 >> 1))
        + (double)(int)(*((_DWORD *)this + 334) & 1 | ((unsigned __int64)v10 >> 1));
  else
    v11 = (double)(int)v10;
  v12 = v11 * *((double *)this + 170);
  v13 = 0;
  if ( v12 >= 9.223372036854776e18 )
  {
    v12 = v12 - 9.223372036854776e18;
    if ( v12 < 9.223372036854776e18 )
      v13 = 0x8000000000000000uLL;
  }
  v14 = v13 + (unsigned int)(int)v12;
  *(double *)&CycleTime = COERCE_DOUBLE(L"DefaultPersistCy");
  v31 = 16;
  Microsoft::Diagnostics::UsageAnalyzer::AddDistroInfoSyntheticField((unsigned int)v32);
  v15 = *((_QWORD *)this + 172);
  if ( v15 < 0 )
    v16 = (double)(int)(*((_DWORD *)this + 344) & 1 | ((unsigned __int64)v15 >> 1))
        + (double)(int)(*((_DWORD *)this + 344) & 1 | ((unsigned __int64)v15 >> 1));
  else
    v16 = (double)(int)v15;
  v17 = v16 * *((double *)this + 175);
  v18 = 0;
  if ( v17 >= 9.223372036854776e18 )
  {
    v17 = v17 - 9.223372036854776e18;
    if ( v17 < 9.223372036854776e18 )
      v18 = 0x8000000000000000uLL;
  }
  v19 = v18 + (unsigned int)(int)v17;
  *(double *)&CycleTime = COERCE_DOUBLE(L"UpdateRulesCy");
  v31 = 13;
  Microsoft::Diagnostics::UsageAnalyzer::AddDistroInfoSyntheticField((unsigned int)v32);
  *(double *)&CycleTime = 0.0;
  QueryThreadCycleTime(*((HANDLE *)&xmmword_18043BF00 + 1), &CycleTime);
  v20 = CycleTime;
  CycleTime = ((((CycleTime - *((_QWORD *)this + 144)) & -(__int64)(*((_QWORD *)this + 144) < CycleTime)) - v19)
             & -(__int64)(v19 < ((CycleTime - *((_QWORD *)this + 144)) & -(__int64)(*((_QWORD *)this + 144) < CycleTime))))
            / 0x3E8;
  v26 = (unsigned __int64)L"MatchEngineOverheadKCy";
  v27 = 22;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((unsigned int)v32, (unsigned int)v33);
  if ( *((_QWORD *)this + 144) >= v20 )
    v20 = *((_QWORD *)this + 144);
  *((_QWORD *)this + 144) = v20;
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_18043BF70, 0, 0) )
    v21 = *(void **)(xmmword_18043BF70 + 24);
  else
    v21 = 0;
  *(double *)&CycleTime = 0.0;
  QueryThreadCycleTime(v21, &CycleTime);
  v22 = CycleTime;
  CycleTime = ((CycleTime - *((_QWORD *)this + 145)) & -(__int64)(*((_QWORD *)this + 145) < CycleTime)) / 0x3E8;
  v26 = (unsigned __int64)L"MetadataEngineOverheadKCy";
  v27 = 25;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((unsigned int)v32, (unsigned int)v33);
  if ( *((_QWORD *)this + 145) >= v22 )
    v22 = *((_QWORD *)this + 145);
  *((_QWORD *)this + 145) = v22;
  v23 = 0;
  v24 = qword_18043C0B8;
  v25 = qword_18043C0C0;
  while ( v24 != v25 )
  {
    *(double *)&CycleTime = 0.0;
    QueryThreadCycleTime(*(HANDLE *)(v24 + 16), &CycleTime);
    v23 += CycleTime;
    v24 += 24;
  }
  CycleTime = ((((v23 - *((_QWORD *)this + 146)) & -(__int64)(*((_QWORD *)this + 146) < v23)) - v14)
             & -(__int64)(v14 < ((v23 - *((_QWORD *)this + 146)) & -(__int64)(*((_QWORD *)this + 146) < v23))))
            / 0x3E8;
  v26 = (unsigned __int64)L"ConsumerThreadOverheadKCy";
  v27 = 25;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((unsigned int)v32, (unsigned int)v33);
  if ( *((_QWORD *)this + 146) >= v23 )
    v23 = *((_QWORD *)this + 146);
  *((_QWORD *)this + 146) = v23;
  CycleTime = *((_QWORD *)this + 185) / 0x3E8uLL;
  v26 = (unsigned __int64)L"TotalUploadKCy";
  v27 = 14;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((unsigned int)v32, (unsigned int)v33);
  *((_QWORD *)this + 185) = 0;
  CycleTime = *((_QWORD *)this + 186) / 0x3E8uLL;
  v26 = (unsigned __int64)L"TotalSettingsDlKCy";
  v27 = 18;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((unsigned int)v32, (unsigned int)v33);
  *((_QWORD *)this + 186) = 0;
  CycleTime = *((_QWORD *)this + 182) / 0x3E8uLL;
  v26 = (unsigned __int64)L"TotalScenarioListeningKCy";
  v27 = 25;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((unsigned int)v32, (unsigned int)v33);
  *((_QWORD *)this + 182) = 0;
  CycleTime = *((_QWORD *)this + 183) / 0x3E8uLL;
  v26 = (unsigned __int64)L"TotalScenarioMatchEngineKCy";
  v27 = 27;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((unsigned int)v32, (unsigned int)v33);
  *((_QWORD *)this + 183) = 0;
  CycleTime = *((_QWORD *)this + 184) / 0x3E8uLL;
  v26 = (unsigned __int64)L"TotalEscalationKCy";
  v27 = 18;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((unsigned int)v32, (unsigned int)v33);
  *((_QWORD *)this + 184) = 0;
  _Mtx_unlock((Microsoft::Diagnostics::UsageAnalyzer *)((char *)this + 1256));
  v28 = 0;
  Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(&v29, &v28);
  Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v32);
  Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v32);
}

```

## disassembly

```asm
0x1800a74e0  mov     rax, rsp
0x1800a74e3  push    rbp
0x1800a74e4  push    rbx
0x1800a74e5  push    rsi
0x1800a74e6  push    rdi
0x1800a74e7  push    r12
0x1800a74e9  push    r13
0x1800a74eb  push    r14
0x1800a74ed  push    r15
0x1800a74ef  lea     rbp, [rax-498h]
0x1800a74f6  sub     rsp, 558h
0x1800a74fd  movaps  xmmword ptr [rax-58h], xmm6
0x1800a7501  mov     rax, cs:__security_cookie
0x1800a7508  xor     rax, rsp
0x1800a750b  mov     [rbp+490h+var_60], rax
0x1800a7512  mov     r14, rcx
0x1800a7515  call    ?QueryUbiTime@Time@Utils@Diagnostics@Microsoft@@SA_KXZ; Microsoft::Diagnostics::Utils::Time::QueryUbiTime(void)
0x1800a751a  mov     rdi, rax
0x1800a751d  xor     r13d, r13d
0x1800a7520  lea     rax, aUsageanalyzerP; "UsageAnalyzer_PerfStats_0"
0x1800a7527  mov     qword ptr [rsp+590h+var_548+8], rax
0x1800a752c  mov     [rsp+590h+var_538], 19h
0x1800a7535  mov     r8d, 1000000h
0x1800a753b  mov     [rsp+30h], r13b
0x1800a7540  mov     [rsp+590h+var_568], r13b
0x1800a7545  mov     byte ptr [rsp+590h+var_570], r13b
0x1800a754a  mov     r9, 400000000000h
0x1800a7554  lea     rdx, [rsp+590h+var_548+8]
0x1800a7559  lea     rcx, [rbp+490h+var_500]
0x1800a755d  call    ??0AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@UPrivacyDataType@@_KVTriggerPersistence@12@VTriggerLatency@12@_N@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(std::wstring_view,PrivacyDataType,unsigned __int64,Microsoft::Diagnostics::TriggerPersistence,Microsoft::Diagnostics::TriggerLatency,bool)
0x1800a7562  nop
0x1800a7563  lea     rcx, [rsp+590h+CycleTime]
0x1800a7568  call    ?GetCpu0Name@Os@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Microsoft::Diagnostics::Utils::Os::GetCpu0Name(void)
0x1800a756d  nop
0x1800a756e  lea     rcx, aCpu0name; "Cpu0Name"
0x1800a7575  mov     qword ptr [rsp+590h+var_548+8], rcx
0x1800a757a  mov     [rsp+590h+var_538], 8
0x1800a7583  mov     r9, rax
0x1800a7586  lea     r8, [rsp+590h+var_548+8]
0x1800a758b  lea     rdx, [rbp+490h+var_98]
0x1800a7592  lea     rcx, [rbp+490h+var_500]
0x1800a7596  call    ??$AddField@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,std::wstring const &)
0x1800a759b  nop
0x1800a759c  lea     rcx, [rsp+590h+CycleTime]; this
0x1800a75a1  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800a75a6  lea     rcx, [rsp+590h+CycleTime]
0x1800a75ab  call    ?GetCpu0Identifier@Os@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Microsoft::Diagnostics::Utils::Os::GetCpu0Identifier(void)
0x1800a75b0  nop
0x1800a75b1  lea     rcx, aCpu0id; "Cpu0Id"
0x1800a75b8  mov     qword ptr [rsp+590h+var_548+8], rcx
0x1800a75bd  mov     [rsp+590h+var_538], 6
0x1800a75c6  mov     r9, rax
0x1800a75c9  lea     r8, [rsp+590h+var_548+8]
0x1800a75ce  lea     rdx, [rbp+490h+var_98]
0x1800a75d5  lea     rcx, [rbp+490h+var_500]
0x1800a75d9  call    ??$AddField@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,std::wstring const &)
0x1800a75de  nop
0x1800a75df  lea     rcx, [rsp+590h+CycleTime]; this
0x1800a75e4  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800a75e9  lea     rbx, [r14+4E8h]
0x1800a75f0  mov     qword ptr [rsp+590h+var_548+8], rbx
0x1800a75f5  mov     rcx, rbx; this
0x1800a75f8  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800a75fd  nop
0x1800a75fe  mov     rcx, rdi
0x1800a7601  sub     rcx, [r14+5E0h]
0x1800a7608  mov     rax, 0D6BF94D5E57A42BDh
0x1800a7612  mul     rcx
0x1800a7615  shr     rdx, 17h
0x1800a7619  mov     [rsp+590h+CycleTime], rdx
0x1800a761e  lea     rax, aTimecoveredsec; "TimeCoveredSec"
0x1800a7625  mov     [rsp+590h+var_550], rax
0x1800a762a  mov     qword ptr [rsp+590h+var_548], 0Eh
0x1800a7633  lea     r9, [rsp+590h+CycleTime]
0x1800a7638  lea     r8, [rsp+590h+var_550]
0x1800a763d  lea     rdx, [rbp+490h+var_98]
0x1800a7644  lea     rcx, [rbp+490h+var_500]
0x1800a7648  call    ??$AddField@_K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEB_K@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,unsigned __int64 const &)
0x1800a764d  mov     [r14+5E0h], rdi
0x1800a7654  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UtcProcessPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UtcProcessPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcProcessPerf> `wil::Feature<__WilFeatureTraits_Feature_UtcProcessPerf>::GetImpl(void)'::`2'::impl
0x1800a765b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UtcProcessPerf@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcProcessPerf>::__private_IsEnabled(void)
0x1800a7660  test    al, al
0x1800a7662  jz      loc_1800A7741
0x1800a7668  mov     [rsp+590h+CycleTime], r13
0x1800a766d  mov     [rsp+590h+var_550], r13
0x1800a7672  mov     [rsp+590h+var_530], r13
0x1800a7677  call    cs:__imp_GetCurrentProcess
0x1800a767e  nop     dword ptr [rax+rax+00h]
0x1800a7683  mov     rdx, rax; void *
0x1800a7686  lea     rax, [rsp+590h+var_530]
0x1800a768b  mov     [rsp+590h+var_570], rax; unsigned __int64 *
0x1800a7690  lea     r9, [rsp+590h+var_550]; unsigned __int64 *
0x1800a7695  lea     r8, [rsp+590h+CycleTime]; unsigned __int64 *
0x1800a769a  mov     rcx, r14; this
0x1800a769d  call    ?GetProcessTimesDelta@UsageAnalyzer@Diagnostics@Microsoft@@AEAAXPEAXAEA_K11@Z; Microsoft::Diagnostics::UsageAnalyzer::GetProcessTimesDelta(void *,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &)
0x1800a76a2  mov     rdx, [rsp+590h+var_530]
0x1800a76a7  test    rdx, rdx
0x1800a76aa  jz      loc_1800A7741
0x1800a76b0  mov     r8, [rsp+590h+var_550]
0x1800a76b5  add     r8, [rsp+590h+CycleTime]
0x1800a76ba  xorps   xmm0, xmm0
0x1800a76bd  js      short loc_1800A76C6
0x1800a76bf  cvtsi2sd xmm0, r8
0x1800a76c4  jmp     short loc_1800A76DC
0x1800a76c6  mov     rax, r8
0x1800a76c9  shr     rax, 1
0x1800a76cc  and     r8d, 1
0x1800a76d0  or      rax, r8
0x1800a76d3  cvtsi2sd xmm0, rax
0x1800a76d8  addsd   xmm0, xmm0
0x1800a76dc  mulsd   xmm0, cs:__real@4059000000000000
0x1800a76e4  xorps   xmm1, xmm1
0x1800a76e7  test    rdx, rdx
0x1800a76ea  js      short loc_1800A76F3
0x1800a76ec  cvtsi2sd xmm1, rdx
0x1800a76f1  jmp     short loc_1800A7708
0x1800a76f3  mov     rax, rdx
0x1800a76f6  shr     rax, 1
0x1800a76f9  and     edx, 1
0x1800a76fc  or      rax, rdx
0x1800a76ff  cvtsi2sd xmm1, rax
0x1800a7704  addsd   xmm1, xmm1
0x1800a7708  divsd   xmm0, xmm1
0x1800a770c  movsd   [rsp+590h+CycleTime], xmm0
0x1800a7712  lea     rax, aProcesscpuperc; "ProcessCpuPercent"
0x1800a7719  mov     [rsp+590h+var_550], rax
0x1800a771e  mov     qword ptr [rsp+590h+var_548], 11h
0x1800a7727  lea     r9, [rsp+590h+CycleTime]
0x1800a772c  lea     r8, [rsp+590h+var_550]
0x1800a7731  lea     rdx, [rbp+490h+var_98]; int
0x1800a7738  lea     rcx, [rbp+490h+var_500]; int
0x1800a773c  call    ??$AddField@N@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBN@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<double>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,double const &)
0x1800a7741  call    cs:__imp_GetCurrentProcess
0x1800a7748  nop     dword ptr [rax+rax+00h]
0x1800a774d  mov     [rsp+590h+CycleTime], r13
0x1800a7752  lea     rdx, [rsp+590h+CycleTime]; CycleTime
0x1800a7757  mov     rcx, rax; ProcessHandle
0x1800a775a  call    cs:__imp_QueryProcessCycleTime
0x1800a7761  nop     dword ptr [rax+rax+00h]
0x1800a7766  mov     rdi, [rsp+590h+CycleTime]
0x1800a776b  mov     rcx, [r14+5D8h]
0x1800a7772  mov     rax, rdi
0x1800a7775  sub     rax, rcx
0x1800a7778  cmp     rcx, rdi
0x1800a777b  sbb     rcx, rcx
0x1800a777e  and     rcx, rax
0x1800a7781  mov     r12, 624DD2F1A9FBE77h
0x1800a778b  mov     rax, r12
0x1800a778e  mul     rcx
0x1800a7791  sub     rcx, rdx
0x1800a7794  shr     rcx, 1
0x1800a7797  add     rcx, rdx
0x1800a779a  shr     rcx, 9
0x1800a779e  mov     [rsp+590h+CycleTime], rcx
0x1800a77a3  lea     rax, aUtcprocesskcy; "UtcProcessKCy"
0x1800a77aa  mov     [rsp+590h+var_550], rax
0x1800a77af  mov     qword ptr [rsp+590h+var_548], 0Dh
0x1800a77b8  lea     r9, [rsp+590h+CycleTime]
0x1800a77bd  lea     r8, [rsp+590h+var_550]
0x1800a77c2  lea     rdx, [rbp+490h+var_98]
0x1800a77c9  lea     rcx, [rbp+490h+var_500]
0x1800a77cd  call    ??$AddField@_K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEB_K@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,unsigned __int64 const &)
0x1800a77d2  mov     [r14+5D8h], rdi
0x1800a77d9  lea     rax, aConsumercallba; "ConsumerCallbackCy"
0x1800a77e0  mov     [rsp+590h+CycleTime], rax
0x1800a77e5  mov     [rsp+590h+var_518], 12h
0x1800a77ee  lea     rdi, [r14+538h]
0x1800a77f5  mov     r8, rdi
0x1800a77f8  lea     rdx, [rsp+590h+CycleTime]
0x1800a77fd  lea     rcx, [rbp+490h+var_500]
0x1800a7801  call    ?AddDistroInfoSyntheticField@UsageAnalyzer@Diagnostics@Microsoft@@CAXAEAVAsimovSyntheticEvent@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$SimpleDistroInfo@_K@23@@Z; Microsoft::Diagnostics::UsageAnalyzer::AddDistroInfoSyntheticField(Microsoft::Diagnostics::AsimovSyntheticEvent &,std::wstring_view,Microsoft::Diagnostics::SimpleDistroInfo<unsigned __int64> &)
0x1800a7806  mov     rcx, [rdi]
0x1800a7809  xorps   xmm0, xmm0
0x1800a780c  test    rcx, rcx
0x1800a780f  js      short loc_1800A7818
0x1800a7811  cvtsi2sd xmm0, rcx
0x1800a7816  jmp     short loc_1800A782D
0x1800a7818  mov     rax, rcx
0x1800a781b  shr     rax, 1
0x1800a781e  and     ecx, 1
0x1800a7821  or      rax, rcx
0x1800a7824  cvtsi2sd xmm0, rax
0x1800a7829  addsd   xmm0, xmm0
0x1800a782d  mulsd   xmm0, qword ptr [r14+550h]
0x1800a7836  xor     eax, eax
0x1800a7838  mov     rsi, 8000000000000000h
0x1800a7842  movsd   xmm6, cs:__real@43e0000000000000
0x1800a784a  comisd  xmm0, xmm6
0x1800a784e  jb      short loc_1800A785D
0x1800a7850  subsd   xmm0, xmm6
0x1800a7854  comisd  xmm0, xmm6
0x1800a7858  jnb     short loc_1800A785D
0x1800a785a  mov     rax, rsi
0x1800a785d  cvttsd2si r15, xmm0
0x1800a7862  add     r15, rax
0x1800a7865  lea     rax, aDefaultpersist; "DefaultPersistCy"
0x1800a786c  mov     [rsp+590h+CycleTime], rax
0x1800a7871  mov     [rsp+590h+var_518], 10h
0x1800a787a  lea     rdi, [r14+560h]
0x1800a7881  mov     r8, rdi
0x1800a7884  lea     rdx, [rsp+590h+CycleTime]
0x1800a7889  lea     rcx, [rbp+490h+var_500]
0x1800a788d  call    ?AddDistroInfoSyntheticField@UsageAnalyzer@Diagnostics@Microsoft@@CAXAEAVAsimovSyntheticEvent@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$SimpleDistroInfo@_K@23@@Z; Microsoft::Diagnostics::UsageAnalyzer::AddDistroInfoSyntheticField(Microsoft::Diagnostics::AsimovSyntheticEvent &,std::wstring_view,Microsoft::Diagnostics::SimpleDistroInfo<unsigned __int64> &)
0x1800a7892  mov     rcx, [rdi]
0x1800a7895  xorps   xmm0, xmm0
0x1800a7898  test    rcx, rcx
0x1800a789b  js      short loc_1800A78A4
0x1800a789d  cvtsi2sd xmm0, rcx
0x1800a78a2  jmp     short loc_1800A78B9
0x1800a78a4  mov     rax, rcx
0x1800a78a7  shr     rax, 1
0x1800a78aa  and     ecx, 1
0x1800a78ad  or      rax, rcx
0x1800a78b0  cvtsi2sd xmm0, rax
0x1800a78b5  addsd   xmm0, xmm0
0x1800a78b9  mulsd   xmm0, qword ptr [r14+578h]
0x1800a78c2  xor     eax, eax
0x1800a78c4  comisd  xmm0, xmm6
0x1800a78c8  jb      short loc_1800A78D7
0x1800a78ca  subsd   xmm0, xmm6
0x1800a78ce  comisd  xmm0, xmm6
0x1800a78d2  jnb     short loc_1800A78D7
0x1800a78d4  mov     rax, rsi
0x1800a78d7  cvttsd2si rdi, xmm0
0x1800a78dc  add     rdi, rax
0x1800a78df  lea     rax, aUpdaterulescy; "UpdateRulesCy"
0x1800a78e6  mov     [rsp+590h+CycleTime], rax
0x1800a78eb  mov     [rsp+590h+var_518], 0Dh
0x1800a78f4  lea     r8, [r14+588h]
0x1800a78fb  lea     rdx, [rsp+590h+CycleTime]
0x1800a7900  lea     rcx, [rbp+490h+var_500]
0x1800a7904  call    ?AddDistroInfoSyntheticField@UsageAnalyzer@Diagnostics@Microsoft@@CAXAEAVAsimovSyntheticEvent@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$SimpleDistroInfo@_K@23@@Z; Microsoft::Diagnostics::UsageAnalyzer::AddDistroInfoSyntheticField(Microsoft::Diagnostics::AsimovSyntheticEvent &,std::wstring_view,Microsoft::Diagnostics::SimpleDistroInfo<unsigned __int64> &)
0x1800a7909  mov     [rsp+590h+CycleTime], r13
0x1800a790e  lea     rdx, [rsp+590h+CycleTime]; CycleTime
0x1800a7913  mov     rcx, qword ptr cs:xmmword_18043BF00+8; ThreadHandle
0x1800a791a  call    cs:__imp_QueryThreadCycleTime
0x1800a7921  nop     dword ptr [rax+rax+00h]
0x1800a7926  mov     rsi, [rsp+590h+CycleTime]
0x1800a792b  mov     rcx, [r14+480h]
0x1800a7932  mov     rax, rsi
0x1800a7935  sub     rax, rcx
0x1800a7938  cmp     rcx, rsi
0x1800a793b  sbb     rcx, rcx
0x1800a793e  and     rcx, rax
0x1800a7941  mov     rax, rcx
0x1800a7944  sub     rax, rdi
0x1800a7947  cmp     rdi, rcx
0x1800a794a  sbb     rcx, rcx
0x1800a794d  and     rcx, rax
0x1800a7950  mov     rax, r12
0x1800a7953  mul     rcx
0x1800a7956  sub     rcx, rdx
0x1800a7959  shr     rcx, 1
0x1800a795c  add     rcx, rdx
0x1800a795f  shr     rcx, 9
0x1800a7963  mov     [rsp+590h+CycleTime], rcx
0x1800a7968  lea     rax, aMatchengineove; "MatchEngineOverheadKCy"
0x1800a796f  mov     [rsp+590h+var_550], rax
0x1800a7974  mov     qword ptr [rsp+590h+var_548], 16h
0x1800a797d  lea     r9, [rsp+590h+CycleTime]
0x1800a7982  lea     r8, [rsp+590h+var_550]
0x1800a7987  lea     rdx, [rbp+490h+var_98]
0x1800a798e  lea     rcx, [rbp+490h+var_500]
0x1800a7992  call    ??$AddField@_K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEB_K@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,unsigned __int64 const &)
0x1800a7997  mov     rax, [r14+480h]
0x1800a799e  cmp     rax, rsi
0x1800a79a1  cmovnb  rsi, rax
0x1800a79a5  mov     [r14+480h], rsi
0x1800a79ac  mov     rcx, r13
0x1800a79af  xor     eax, eax
0x1800a79b1  lock cmpxchg qword ptr cs:xmmword_18043BF70, rcx
0x1800a79ba  jz      short loc_1800A79C9
0x1800a79bc  mov     rax, qword ptr cs:xmmword_18043BF70
0x1800a79c3  mov     rcx, [rax+18h]
0x1800a79c7  jmp     short loc_1800A79CC
0x1800a79c9  mov     rcx, r13; ThreadHandle
0x1800a79cc  mov     [rsp+590h+CycleTime], r13
0x1800a79d1  lea     rdx, [rsp+590h+CycleTime]; CycleTime
0x1800a79d6  call    cs:__imp_QueryThreadCycleTime
0x1800a79dd  nop     dword ptr [rax+rax+00h]
0x1800a79e2  mov     rdi, [rsp+590h+CycleTime]
0x1800a79e7  mov     rcx, [r14+488h]
0x1800a79ee  mov     rax, rdi
0x1800a79f1  sub     rax, rcx
0x1800a79f4  cmp     rcx, rdi
0x1800a79f7  sbb     rcx, rcx
0x1800a79fa  and     rcx, rax
0x1800a79fd  mov     rax, r12
0x1800a7a00  mul     rcx
0x1800a7a03  sub     rcx, rdx
0x1800a7a06  shr     rcx, 1
0x1800a7a09  add     rcx, rdx
0x1800a7a0c  shr     rcx, 9
0x1800a7a10  mov     [rsp+590h+CycleTime], rcx
0x1800a7a15  lea     rax, aMetadataengine_1; "MetadataEngineOverheadKCy"
0x1800a7a1c  mov     [rsp+590h+var_550], rax
0x1800a7a21  mov     qword ptr [rsp+590h+var_548], 19h
0x1800a7a2a  lea     r9, [rsp+590h+CycleTime]
0x1800a7a2f  lea     r8, [rsp+590h+var_550]
0x1800a7a34  lea     rdx, [rbp+490h+var_98]
  ... truncated ...
```
