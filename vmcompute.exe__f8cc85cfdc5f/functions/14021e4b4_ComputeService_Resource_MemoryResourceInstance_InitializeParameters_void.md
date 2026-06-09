# ComputeService::Resource::MemoryResourceInstance::InitializeParameters(void)

- ea: `0x14021e4b4`
- end: `0x14021f245`
- name: `?InitializeParameters@MemoryResourceInstance@Resource@ComputeService@@AEAAXXZ`
- size: `3473`
- prototype: `void __fastcall(ComputeService::Resource::MemoryResourceInstance *__hidden this)`
- caller_count: `1`
- callee_count: `60`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14021dda0`

## callees

- `0x140004450`
- `0x14001bc28`
- `0x14002d818`
- `0x140033a7c`
- `0x140038268`
- `0x140044eec`
- `0x14004ec00`
- `0x1400521fc`
- `0x14005b21c`
- `0x1400606d0`
- `0x140062fd0`
- `0x1400631d8`
- `0x14006485c`
- `0x14006499c`
- `0x14006512c`
- `0x140067f2c`
- `0x1400680a8`
- `0x1400692a8`
- `0x140076024`
- `0x140076b68`
- `0x140076f0c`
- `0x140077884`
- `0x140077f14`
- `0x140079c9c`
- `0x1400851f0`
- `0x1400857b4`
- `0x14009c7dc`
- `0x1400b2a44`
- `0x1400c40e0`
- `0x1400d3d68`
- `0x1400e7ff0`
- `0x1400ebbec`
- `0x1400ec334`
- `0x1400f3924`
- `0x1400f3944`
- `0x1400f4898`
- `0x1400fa598`
- `0x1400ffff0`
- `0x140106acc`
- `0x14010ddb4`
- `0x1401279e8`
- `0x1401296e8`
- `0x1401332f0`
- `0x1401365c5`
- `0x140189f38`
- `0x140190b40`
- `0x14019b8c8`
- `0x1401c9e50`
- `0x14021cd30`
- `0x14021e1e8`

## string_xrefs

- `0x14021e69f`: `/configuration/settings/numa_node_mask`
- `0x14021e73a`: `onecore\vm\compute\management\resources\memory\memoryresourceinstance.cpp`
- `0x14021effd`: `onecore\vm\compute\management\resources\memory\memoryresourceinstance.cpp`
- `0x14021f00f`: `onecore\vm\compute\management\resources\memory\memoryresourceinstance.cpp`
- `0x14021f024`: `onecore\vm\compute\management\resources\memory\memoryresourceinstance.cpp`
- `0x14021f039`: `onecore\vm\compute\management\resources\memory\memoryresourceinstance.cpp`
- `0x14021f04e`: `onecore\vm\compute\management\resources\memory\memoryresourceinstance.cpp`
- `0x14021f0ff`: `onecore\vm\compute\management\resources\memory\memoryresourceinstance.cpp`
- `0x14021f117`: `onecore\vm\compute\management\resources\memory\memoryresourceinstance.cpp`
- `0x14021f132`: `onecore\vm\compute\management\resources\memory\memoryresourceinstance.cpp`
- `0x14021f14a`: `onecore\vm\compute\management\resources\memory\memoryresourceinstance.cpp`
- `0x14021f162`: `onecore\vm\compute\management\resources\memory\memoryresourceinstance.cpp`
- `0x14021f17d`: `onecore\vm\compute\management\resources\memory\memoryresourceinstance.cpp`
- `0x14021f198`: `onecore\vm\compute\management\resources\memory\memoryresourceinstance.cpp`
- `0x14021f1b0`: `onecore\vm\compute\management\resources\memory\memoryresourceinstance.cpp`
- `0x14021f200`: `onecore\vm\compute\management\resources\memory\memoryresourceinstance.cpp`
- `0x14021f218`: `onecore\vm\compute\management\resources\memory\memoryresourceinstance.cpp`
- `0x14021f233`: `onecore\vm\compute\management\resources\memory\memoryresourceinstance.cpp`
- `0x14021eff1`: `HW threads per core out of range.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall ComputeService::Resource::MemoryResourceInstance::InitializeParameters(
        ComputeService::Resource::MemoryResourceInstance *this)
{
  const struct Config::VmWorkerProcess::MemorySettings **v2; // r15
  int v3; // eax
  int v4; // eax
  __int64 MemorySettingsFromTheConfiguration; // rax
  struct _VM_MEMORY_PARAMETERS *v6; // r9
  int MemoryParameters; // eax
  __int64 ProcessorSettingsFromTheConfiguration; // rax
  __int16 *NumaSettingsFromTheConfiguration; // rax
  unsigned int v10; // r8d
  __int64 VirtualNumaNodeCountFromSettings; // rax
  unsigned int v12; // eax
  char v13; // dl
  char v14; // di
  _BYTE *v15; // r14
  _DWORD *v16; // r12
  struct Vml::VmPhysicalProcessorInfo *Info; // rdi
  int v18; // eax
  int v19; // eax
  int v20; // eax
  __int64 *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r8
  unsigned int v25; // esi
  ComputeService::Management::ServiceCapabilities::Helpers *v26; // rcx
  __int64 HostMaxProcessorCountPerL3; // rax
  unsigned int v28; // eax
  unsigned int v29; // ecx
  ComputeService::Management::ServiceCapabilities::Helpers *v30; // rcx
  __int128 i; // rdi
  const struct _tlgProvider_t *v32; // rax
  unsigned int v33; // edx
  const unsigned __int16 *v34; // r9
  _QWORD *v35; // rcx
  __int64 v36; // rcx
  const struct Config::VmWorkerProcess::NumaSettings *v37; // rdx
  unsigned __int8 v38; // r8
  unsigned int v39; // edi
  unsigned int v40; // r9d
  bool v41; // al
  char v42; // al
  int v43; // r8d
  int v44; // r9d
  int v45; // r8d
  __int64 VirtualProcessorCountByVNode; // rax
  __int64 v47; // rdx
  __int64 v48; // r8
  unsigned __int64 v49; // r8
  unsigned __int64 v50; // r9
  _DWORD *v51; // rcx
  unsigned __int64 v52; // rdi
  __int64 v53; // rcx
  unsigned __int64 v54; // r8
  __int64 v55; // rdx
  const char *v56; // r9
  __int64 v57; // rax
  __int64 v58; // rax
  const char *v59; // r9
  unsigned int v60; // eax
  __int64 v61; // rdx
  int v62; // [rsp+20h] [rbp-10A8h]
  int v63; // [rsp+20h] [rbp-10A8h]
  int v64; // [rsp+20h] [rbp-10A8h]
  unsigned __int64 *v65; // [rsp+20h] [rbp-10A8h]
  unsigned __int64 *v66; // [rsp+20h] [rbp-10A8h]
  int v67; // [rsp+20h] [rbp-10A8h]
  int v68; // [rsp+20h] [rbp-10A8h]
  const char *v69; // [rsp+28h] [rbp-10A0h]
  char v70; // [rsp+28h] [rbp-10A0h]
  unsigned __int64 *v71; // [rsp+28h] [rbp-10A0h]
  __int64 v72; // [rsp+50h] [rbp-1078h] BYREF
  __int64 v73; // [rsp+58h] [rbp-1070h] BYREF
  __int64 v74; // [rsp+60h] [rbp-1068h] BYREF
  _OWORD Buf2[2]; // [rsp+68h] [rbp-1060h] BYREF
  ComputeService::Resource::MemoryResourceInstance *v76; // [rsp+88h] [rbp-1040h]
  _BYTE v77[560]; // [rsp+90h] [rbp-1038h] BYREF
  VmMemorySettings *v78[2]; // [rsp+2C0h] [rbp-E08h] BYREF
  _BYTE v79[64]; // [rsp+2D0h] [rbp-DF8h] BYREF
  unsigned int v80; // [rsp+310h] [rbp-DB8h]
  int v81; // [rsp+314h] [rbp-DB4h]
  char v82; // [rsp+33Ch] [rbp-D8Ch]
  unsigned int v83; // [rsp+3A0h] [rbp-D28h]
  struct _GUID Buf1; // [rsp+3B8h] [rbp-D10h] BYREF
  unsigned int v85; // [rsp+3D4h] [rbp-CF4h]
  char v86; // [rsp+3D8h] [rbp-CF0h]
  int v87; // [rsp+3DCh] [rbp-CECh]
  char v88; // [rsp+3E0h] [rbp-CE8h]
  char v89; // [rsp+4C0h] [rbp-C08h]
  char v90; // [rsp+4C1h] [rbp-C07h]
  __int64 v91; // [rsp+500h] [rbp-BC8h] BYREF
  __int16 v92; // [rsp+508h] [rbp-BC0h] BYREF
  __int128 v93; // [rsp+510h] [rbp-BB8h] BYREF
  __int64 v94; // [rsp+520h] [rbp-BA8h]
  char *v95[2]; // [rsp+528h] [rbp-BA0h] BYREF
  __int128 v96; // [rsp+540h] [rbp-B88h] BYREF
  __int64 v97; // [rsp+550h] [rbp-B78h]
  __int64 v98[3]; // [rsp+558h] [rbp-B70h] BYREF
  _BYTE v99[32]; // [rsp+570h] [rbp-B58h] BYREF
  __int64 v100; // [rsp+590h] [rbp-B38h]
  char v101; // [rsp+5C8h] [rbp-B00h]
  char v102; // [rsp+5C9h] [rbp-AFFh]
  __int64 v103; // [rsp+628h] [rbp-AA0h]
  char v104[32]; // [rsp+6B0h] [rbp-A18h] BYREF
  _BYTE v105[1968]; // [rsp+6D0h] [rbp-9F8h] BYREF
  int v106; // [rsp+E80h] [rbp-248h]
  wil::details::in1diag3 *retaddr; // [rsp+10C8h] [rbp+0h]

  v76 = this;
  v78[0] = 0;
  Config::VmWorkerProcess::MemorySettings::MemorySettings((Config::VmWorkerProcess::MemorySettings *)v99);
  Config::VmWorkerProcess::ProcessorSettings::ProcessorSettings((Config::VmWorkerProcess::ProcessorSettings *)v79);
  v92 = 0;
  v93 = 0;
  v94 = 0;
  v91 = 0;
  *(_OWORD *)v95 = 0;
  v2 = (const struct Config::VmWorkerProcess::MemorySettings **)((char *)this + 128);
  VmRepositoryAutoLock::VmRepositoryAutoLock(v95, *((_QWORD *)this + 16), 0);
  if ( SLODWORD(v95[1]) < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x264,
      (unsigned int)"onecore\\vm\\compute\\management\\resources\\memory\\memoryresourceinstance.cpp",
      (const char *)LODWORD(v95[1]),
      v62);
  v3 = (*(__int64 (__fastcall **)(const struct Config::VmWorkerProcess::MemorySettings *, VmMemorySettings **))(*(_QWORD *)*v2 + 288LL))(
         *v2,
         v78);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x266,
      (unsigned int)"onecore\\vm\\compute\\management\\resources\\memory\\memoryresourceinstance.cpp",
      (const char *)(unsigned int)v3,
      v62);
  v4 = (*(__int64 (__fastcall **)(const struct Config::VmWorkerProcess::MemorySettings *, char *))(*(_QWORD *)*v2 + 320LL))(
         *v2,
         (char *)v78 + 4);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x268,
      (unsigned int)"onecore\\vm\\compute\\management\\resources\\memory\\memoryresourceinstance.cpp",
      (const char *)(unsigned int)v4,
      v62);
  MemorySettingsFromTheConfiguration = VmMemoryConfigurationKeys::ReadMemorySettingsFromTheConfiguration(v77, *v2);
  Config::VmWorkerProcess::MemorySettings::operator=(v99, MemorySettingsFromTheConfiguration);
  Config::VmWorkerProcess::MemorySettings::~MemorySettings((Config::VmWorkerProcess::MemorySettings *)v77);
  MemoryParameters = VmUtilities::GetMemoryParameters(
                       (VmUtilities *)v99,
                       *v2,
                       (ComputeService::Resource::MemoryResourceInstance *)((char *)this + 240),
                       v6);
  if ( MemoryParameters < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x270,
      (unsigned int)"onecore\\vm\\compute\\management\\resources\\memory\\memoryresourceinstance.cpp",
      (const char *)(unsigned int)MemoryParameters,
      v62);
  ProcessorSettingsFromTheConfiguration = VmProcessorConfigurationKeys::ReadProcessorSettingsFromTheConfiguration(
                                            v77,
                                            *v2);
  Config::VmWorkerProcess::ProcessorSettings::operator=(v79, ProcessorSettingsFromTheConfiguration);
  Config::VmWorkerProcess::ProcessorSettings::~ProcessorSettings((Config::VmWorkerProcess::ProcessorSettings *)v77);
  NumaSettingsFromTheConfiguration = (__int16 *)VmNumaConfigurationKeys::ReadNumaSettingsFromTheConfiguration(Buf2, *v2);
  v92 = *NumaSettingsFromTheConfiguration;
  std::vector<Schema::VirtualMachines::Resources::Compute::NumaSetting>::operator=(
    &v93,
    NumaSettingsFromTheConfiguration + 4);
  std::vector<Schema::VirtualMachines::Resources::Compute::NumaSetting>::_Tidy((char *)Buf2 + 8);
  if ( (*(int (__fastcall **)(const struct Config::VmWorkerProcess::MemorySettings *, const unsigned __int16 *, __int64 *))(*(_QWORD *)*v2 + 112LL))(
         *v2,
         L"/configuration/settings/numa_node_mask",
         &v91) < 0 )
    v91 = 0;
  VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v95);
  v95[0] = (char *)32;
  v95[1] = (char *)VmMemorySettings::GetSizeUpperBoundInMb((VmMemorySettings *)LODWORD(v78[0]), HIDWORD(v78[0]), v10);
  VirtualNumaNodeCountFromSettings = VmUtilities::GetVirtualNumaNodeCountFromSettings(Buf2, v79, v99, &v92);
  if ( *(_DWORD *)(VirtualNumaNodeCountFromSettings + 16) )
  {
    v12 = wil::verify_BOOL<int>(2147942487LL);
    if ( (v13 & 8) == 0 )
    {
      if ( (v13 & 2) != 0 )
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x29F,
          (unsigned int)"onecore\\vm\\compute\\management\\resources\\memory\\memoryresourceinstance.cpp",
          (const char *)v12,
          (int)v95);
        v58 = std::wstring::c_str((char *)this + 40);
        ComputeService::Reporting::LogAndThrowComputeSystemError<>(
          v58,
          2147942487LL,
          MSVCOMP_DM_FAILED_TO_START_VM_DUE_TO_CONFIGURED_MEMORY_INCOMPATIPLE_WITH_HOST);
      }
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2A1,
        (unsigned int)"onecore\\vm\\compute\\management\\resources\\memory\\memoryresourceinstance.cpp",
        (const char *)v12,
        (int)v95);
    }
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x296,
      (unsigned int)"onecore\\vm\\compute\\management\\resources\\memory\\memoryresourceinstance.cpp",
      (const char *)v12,
      (int)v95);
    v57 = std::wstring::c_str((char *)this + 40);
    ComputeService::Reporting::LogAndThrowComputeSystemError<>(
      v57,
      2147942487LL,
      MSVCOMP_DM_FAILED_TO_START_VM_WITH_REQUESTED_VNODE_COUNT);
  }
  v14 = *(_BYTE *)VirtualNumaNodeCountFromSettings;
  if ( *((_DWORD *)this + 30) == 1 )
    *((_QWORD *)this + 25) = v100 << 8;
  std::vector<unsigned char>::operator=((char *)this + 2352, v104);
  v15 = (char *)this + 193;
  *((_BYTE *)this + 193) = v14;
  *((_QWORD *)this + 29) = v91;
  v16 = (_DWORD *)((char *)this + 160);
  *((_DWORD *)this + 40) = v80;
  if ( v90 )
    *((_BYTE *)this + 2496) = v89;
  Buf2[0] = 0;
  if ( memcmp_0(&Buf1, Buf2, 0x10u) )
    ComputeService::Resource::MemoryResourceInstance::SelectNumaNodes(this, &Buf1);
  Info = Vml::VmPhysicalProcessorInfo::GetInfo();
  switch ( *((_DWORD *)this + 30) )
  {
    case 1:
      v20 = v81;
      *((_DWORD *)this + 625) = v81;
      if ( LODWORD(v78[0]) >= 0x900 && !v20 )
        *((_DWORD *)this + 625) = (*((_DWORD *)Info + 13) < *((_DWORD *)Info + 11)) + 1;
      if ( v86 )
      {
        if ( v85 )
        {
          *((_DWORD *)this + 620) = v85;
          *((_BYTE *)this + 2484) = 1;
          *(_WORD *)((char *)this + 2485) = *(_WORD *)((char *)&v91 + 5);
          *((_BYTE *)this + 2487) = HIBYTE(v91);
        }
        else
        {
          *((_QWORD *)this + 310) = *(_QWORD *)ComputeService::Resource::GetHostMaxProcessorCountPerL3(Buf2);
        }
      }
      else
      {
        *(_OWORD *)v98 = 0;
        v21 = (__int64 *)std::make_unique<Vml::VmMachineLocalSettingsStore,,0>(&v74);
        v22 = *v21;
        *v21 = 0;
        v73 = v22;
        VirtualizationSettings::VirtualizationSettings(v98, v23, v24, &v73);
        std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(&v73);
        std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(&v74);
        v25 = VirtualizationSettings::GetAzureFeatureSetEnabled((VirtualizationSettings *)v98) ? 2307 : 2560;
        if ( !ComputeService::Management::ServiceCapabilities::Helpers::IsHypervisorRootSchedulerEnabled(v26)
          && *(_DWORD *)Info == 2
          && LODWORD(v78[0]) >= v25 )
        {
          HostMaxProcessorCountPerL3 = ComputeService::Resource::GetHostMaxProcessorCountPerL3(Buf2);
          if ( !*(_BYTE *)(HostMaxProcessorCountPerL3 + 4) )
            std::_Throw_bad_optional_access();
          v28 = *(_DWORD *)HostMaxProcessorCountPerL3;
          if ( v83 < v28 )
            v28 = v83;
          *((_DWORD *)this + 620) = v28;
          *((_BYTE *)this + 2484) = 1;
          *(_WORD *)((char *)this + 2485) = *(_WORD *)((char *)&v91 + 5);
          *((_BYTE *)this + 2487) = HIBYTE(v91);
        }
        std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(&v98[1]);
      }
      if ( v88 )
      {
        if ( v87 )
        {
          *((_DWORD *)this + 622) = v87;
          *((_BYTE *)this + 2492) = 1;
          *(_WORD *)((char *)this + 2493) = *(_WORD *)((char *)&v91 + 5);
          *((_BYTE *)this + 2495) = HIBYTE(v91);
        }
        else
        {
          *((_QWORD *)this + 311) = *(_QWORD *)ComputeService::Resource::GetHostMaxClusterCountPerSocket(Buf2);
        }
      }
      break;
    case 2:
    case 3:
      if ( *((_DWORD *)this + 625) == -1 )
      {
        v19 = v81;
        goto LABEL_26;
      }
      break;
    case 4:
      v18 = *((_DWORD *)this + 625);
      if ( !v18 )
      {
        v18 = v81;
        *((_DWORD *)this + 625) = v81;
      }
      if ( LODWORD(v78[0]) >= 0x900 && !v18 )
      {
        v19 = (*((_DWORD *)Info + 13) < *((_DWORD *)Info + 11)) + 1;
LABEL_26:
        *((_DWORD *)this + 625) = v19;
      }
      break;
  }
  v29 = *((_DWORD *)this + 625);
  if ( v29 - 1 > 1 )
  {
    v56 = (const char *)(unsigned int)wil::verify_BOOL<int>(2147942487LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x350,
      (unsigned int)"onecore\\vm\\compute\\management\\resources\\memory\\memoryresourceinstance.cpp",
      v56,
      (int)"HW threads per core out of range.\n",
      v69);
  }
  if ( v82 && v80 % v29 )
  {
    v73 = std::wstring::c_str((char *)this + 72);
    VmEventWrite<unsigned short const *,unsigned char &,unsigned int &>(
      &MSVCOMP_INVALID_SMT_SIBLINGS_DISTRIBUTION,
      (__int64)this + 193,
      (__int64)this + 160);
    v59 = (const char *)(unsigned int)wil::verify_BOOL<int>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x35A,
      (unsigned int)"onecore\\vm\\compute\\management\\resources\\memory\\memoryresourceinstance.cpp",
      v59,
      v67);
  }
  v96 = 0;
  v97 = 0;
  VmNumaSettings::ValidateNumaSettingsConfigWithResults(
    (unsigned int)&v92,
    (unsigned int)v99,
    v78[0],
    HIDWORD(v78[0]),
    *v16,
    *((_QWORD *)this + 25),
    (__int64)&v96);
  for ( i = v96; (_QWORD)i != *((_QWORD *)&i + 1); *(_QWORD *)&i = i + 24 )
  {
    v32 = ComputeService::Diagnostics::TraceProvider::Provider();
    if ( *(_DWORD *)v32 > 2u )
    {
      v98[0] = *(_QWORD *)(i + 8);
      LOBYTE(v72) = *(_BYTE *)(i + 4);
      LODWORD(v74) = *(_DWORD *)(i + 16);
      LODWORD(v73) = *(_DWORD *)i;
      v35 = (_QWORD *)((char *)this + 40);
      if ( *((_QWORD *)this + 8) > 7u )
        v35 = (_QWORD *)*v35;
      *(_QWORD *)&Buf2[0] = v35;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
        (int)v32,
        (__int64)Buf2,
        (__int64)&v73,
        (__int64)&v74,
        (__int64)&v72,
        (__int64)v98);
    }
    VmEventWriteAndReport(
      (const struct _EVENT_DESCRIPTOR *)VmNumaSettings::g_VmNumaSettingsValidationEventArray[*(int *)i],
      v33,
      &GUID_NULL,
      v34);
  }
  if ( (_QWORD)v93 != *((_QWORD *)&v93 + 1) )
  {
    v36 = Vml::VmSingletonObject<NumaPhysicalTopologyInfo,INumaPhysicalTopologyInfo>::OpenShared();
    *(_QWORD *)&Buf2[0] = v36;
    if ( !v36 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x38C,
        (unsigned int)"onecore\\vm\\compute\\management\\resources\\memory\\memoryresourceinstance.cpp",
        (const char *)0x8007000ELL,
        v63);
    LOBYTE(v37) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 24LL))(v36);
    VmNumaSettings::ValidateNumaSettingsHost((VmNumaSettings *)&v92, v37, v38);
    Vml::VmReferencePtr<IComputePhysicalTopologyInfo,Vml::VmUserReferenceTraits>::~VmReferencePtr<IComputePhysicalTopologyInfo,Vml::VmUserReferenceTraits>(Buf2);
  }
  if ( *((_BYTE *)this + 2484) )
  {
    v39 = *(_DWORD *)std::optional<unsigned long>::value((char *)this + 2480);
    if ( !v39 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x39C,
        (unsigned int)"onecore\\vm\\compute\\management\\resources\\memory\\memoryresourceinstance.cpp",
        (const char *)0x8007000DLL,
        v63);
    v41 = VmProcessorSettings::ValidateVpCount((VmProcessorSettings *)LODWORD(v78[0]), HIDWORD(v78[0]), v39, v40);
    v30 = retaddr;
    if ( !v41 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x39D,
        (unsigned int)"onecore\\vm\\compute\\management\\resources\\memory\\memoryresourceinstance.cpp",
        (const char *)0x8007000DLL,
        v63);
    v85 = v39;
    v42 = 1;
  }
  else
  {
    v42 = 0;
    v85 = 0;
  }
  v86 = v42;
  if ( *((_BYTE *)this + 2492) )
  {
    v30 = (ComputeService::Management::ServiceCapabilities::Helpers *)*(unsigned int *)std::optional<unsigned long>::value((char *)this + 2488);
    if ( !(_DWORD)v30 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3A9,
        (unsigned int)"onecore\\vm\\compute\\management\\resources\\memory\\memoryresourceinstance.cpp",
        (const char *)0x8007000DLL,
        v63);
    if ( (unsigned int)v30 > 8 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3AD,
        (unsigned int)"onecore\\vm\\compute\\management\\resources\\memory\\memoryresourceinstance.cpp",
        (const char *)0x8007000DLL,
        v63);
    v87 = (int)v30;
    v88 = 1;
    LOBYTE(v30) = 1;
    v42 = v86;
  }
  else
  {
    v88 = 0;
    v87 = 0;
    LOBYTE(v30) = 0;
  }
  if ( (v42 || (_BYTE)v30)
    && ComputeService::Management::ServiceCapabilities::Helpers::IsHypervisorRootSchedulerEnabled(v30) )
  {
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3BB,
      (unsigned int)"onecore\\vm\\compute\\management\\resources\\memory\\memoryresourceinstance.cpp",
      (const char *)0x80070057LL,
      v63);
  }
  Config::VmWorkerProcess::Configuration::Configuration((Config::VmWorkerProcess::Configuration *)v105);
  if ( !*(_BYTE *)Marshal::FromRepositoryXml<Vml::VmReferencePtr<HyperVRepository,Vml::VmUserReferenceTraits> &,Config::VmWorkerProcess::Configuration,>(
                    Buf2,
                    (char *)this + 128,
                    v105) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3C1,
      (unsigned int)"onecore\\vm\\compute\\management\\resources\\memory\\memoryresourceinstance.cpp",
      (const char *)0x80070057LL,
      v63);
  std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy((char *)Buf2 + 8);
  v43 = (_DWORD)this + 2512;
  try
  {
    LOBYTE(v43) = *v15;
    *((_BYTE *)this + 192) = VmProcessorSettings::PopulateComputeTopology(
                               (unsigned int)v79,
                               (unsigned int)&v92,
                               v43,
                               *((_DWORD *)this + 625),
                               (__int64)this + 2504,
                               (__int64)this + 2512,
                               (__int64)this + 2536,
                               (__int64)this + 2560,
                               (v106 & 0x400) != 0);
    *((char **)this + 18) = v95[0];
    *((char **)this + 19) = v95[1];
    v70 = v82;
    v64 = *((_DWORD *)this + 625);
    LOBYTE(v44) = *v15;
    v45 = *v16;
  }
  catch ( ... )
  {
    v76 = (ComputeService::Resource::MemoryResourceInstance *)std::wstring::c_str((char *)v76 + 72);
    VmEventWrite<unsigned short const *,unsigned char &,unsigned int &>(
      &MSVCOMP_INVALID_PROCESSOR_TOPOLOGY,
      v61 + 193,
      v61 + 160);
    throw;
  }
  VirtualProcessorCountByVNode = ComputeService::Resource::GetVirtualProcessorCountByVNode(
                                   (unsigned int)v95,
                                   (unsigned int)&v92,
                                   v45,
                                   v44,
                                   v64,
                                   v70);
  std::vector<enum Schema::VirtualMachines::Resources::Compute::XsaveProcessorFeature>::operator=(
    (char *)this + 168,
    VirtualProcessorCountByVNode);
  std::vector<enum Schema::Requests::System::NetworkProperty>::_Tidy(v95, v47, v48);
  if ( v82 )
  {
    v51 = (_DWORD *)*((_QWORD *)this + 21);
    v49 = *((_QWORD *)this + 22);
    while ( v51 != (_DWORD *)v49 )
    {
      if ( *v51 % *((_DWORD *)this + 625) )
      {
        *(_QWORD *)&Buf2[0] = std::wstring::c_str((char *)this + 72);
        VmEventWrite<unsigned short const *,unsigned char &,unsigned int &>(
          &MSVCOMP_INVALID_SMT_SIBLINGS_DISTRIBUTION,
          (__int64)this + 193,
          (__int64)this + 160);
        v60 = wil::verify_BOOL<int>(2147942487LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3F8,
          (unsigned int)"onecore\\vm\\compute\\management\\resources\\memory\\memoryresourceinstance.cpp",
          (const char *)v60,
          v68);
      }
      ++v51;
    }
  }
  v52 = 512;
  if ( v103 == 0x40000 )
    v52 = 0x40000;
  if ( (unsigned int)(*((_DWORD *)this + 30) - 2) <= 1 )
  {
    if ( !v102 )
      __fastfail(5u);
    if ( !v101 )
    {
      v53 = *((_QWORD *)this + 25);
      if ( v53 != v100 << 8 )
      {
        *((_QWORD *)this + 31) = v53;
        *((_QWORD *)this + 32) = v53;
      }
    }
  }
  else
  {
    LOBYTE(v50) = *v15;
    VmUtilities::GetInitialPagesByVNode(
      (VmUtilities *)&v92,
      *((const struct Config::VmWorkerProcess::NumaSettings **)this + 25),
      (unsigned int)v52,
      v50,
      (_BYTE)this + 48,
      v71);
  }
  if ( *((_DWORD *)this + 30) == 3 )
  {
    v55 = (unsigned __int8)*v15;
    if ( *((_QWORD *)this + 300) - *((_QWORD *)this + 299) != v55 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x441,
        (unsigned int)"onecore\\vm\\compute\\management\\resources\\memory\\memoryresourceinstance.cpp",
        (const char *)0x8007000DLL,
        (int)v65);
    if ( *((_QWORD *)this + 330) - *((_QWORD *)this + 329) != v55 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x445,
        (unsigned int)"onecore\\vm\\compute\\management\\resources\\memory\\memoryresourceinstance.cpp",
        (const char *)0x8007000DLL,
        (int)v65);
  }
  else
  {
    VmNumaSettings::GetVirtualToPhysicalNodeMaps(&v92, (char *)this + 2632, (char *)this + 2392);
  }
  LOBYTE(v49) = *v15;
  VmUtilities::DivideMemoryAmongVNodes(*((VmUtilities **)this + 35), v52, v49, (_BYTE)this + 48, v65);
  LOBYTE(v54) = *v15;
  VmUtilities::DivideMemoryAmongVNodes(*((VmUtilities **)this + 36), v52, v54, (_BYTE)this + 48, v66);
  Config::VmWorkerProcess::Configuration::~Configuration((Config::VmWorkerProcess::Configuration *)v105);
  if ( (_QWORD)v96 )
  {
    std::_Deallocate<16>(v96, 8 * ((v97 - (__int64)v96) >> 3));
    v96 = 0;
    v97 = 0;
  }
  std::vector<Schema::VirtualMachines::Resources::Compute::NumaSetting>::_Tidy(&v93);
  Config::VmWorkerProcess::ProcessorSettings::~ProcessorSettings((Config::VmWorkerProcess::ProcessorSettings *)v79);
  Config::VmWorkerProcess::MemorySettings::~MemorySettings((Config::VmWorkerProcess::MemorySettings *)v99);
}

```

## disassembly

```asm
0x14021e4b4  mov     [rsp+arg_8], rbx
0x14021e4b9  mov     [rsp+arg_10], rsi
0x14021e4be  push    rdi
0x14021e4bf  push    r12
0x14021e4c1  push    r13
0x14021e4c3  push    r14
0x14021e4c5  push    r15
0x14021e4c7  mov     eax, 10A0h
0x14021e4cc  call    _alloca_probe
0x14021e4d1  sub     rsp, rax
0x14021e4d4  mov     rax, cs:__security_cookie
0x14021e4db  xor     rax, rsp
0x14021e4de  mov     [rsp+10C8h+var_38], rax
0x14021e4e6  mov     rbx, rcx
0x14021e4e9  mov     [rsp+10C8h+var_1040], rcx
0x14021e4f1  xor     r13d, r13d
0x14021e4f4  mov     dword ptr [rsp+10C8h+var_E08], r13d
0x14021e4fc  mov     dword ptr [rsp+10C8h+var_E08+4], r13d
0x14021e504  lea     rcx, [rsp+10C8h+var_B58]; this
0x14021e50c  call    ??0MemorySettings@VmWorkerProcess@Config@@QEAA@XZ; Config::VmWorkerProcess::MemorySettings::MemorySettings(void)
0x14021e511  nop
0x14021e512  lea     rcx, [rsp+10C8h+var_DF8]; this
0x14021e51a  call    ??0ProcessorSettings@VmWorkerProcess@Config@@QEAA@XZ; Config::VmWorkerProcess::ProcessorSettings::ProcessorSettings(void)
0x14021e51f  nop
0x14021e520  mov     [rsp+10C8h+var_BC0], r13w
0x14021e529  xorps   xmm0, xmm0
0x14021e52c  movdqu  [rsp+10C8h+var_BB8], xmm0
0x14021e535  mov     [rsp+10C8h+var_BA8], r13
0x14021e53d  mov     [rsp+10C8h+var_BC8], r13
0x14021e545  movups  xmmword ptr [rsp+10C8h+var_BA0], xmm0
0x14021e54d  lea     r15, [rbx+80h]
0x14021e554  xor     r8d, r8d
0x14021e557  mov     rdx, [r15]
0x14021e55a  lea     rcx, [rsp+10C8h+var_BA0]
0x14021e562  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x14021e567  nop
0x14021e568  mov     r9d, dword ptr [rsp+10C8h+var_BA0+8]; char *
0x14021e570  mov     rcx, [rsp+10C8h]; this
0x14021e578  test    r9d, r9d
0x14021e57b  js      loc_14021F00F
0x14021e581  mov     rcx, [r15]
0x14021e584  mov     rax, [rcx]
0x14021e587  lea     rdx, [rsp+10C8h+var_E08]
0x14021e58f  mov     rax, [rax+120h]
0x14021e596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14021e59b  mov     rcx, [rsp+10C8h]; this
0x14021e5a3  test    eax, eax
0x14021e5a5  js      loc_14021F021
0x14021e5ab  mov     rcx, [r15]
0x14021e5ae  mov     rax, [rcx]
0x14021e5b1  lea     rdx, [rsp+10C8h+var_E08+4]
0x14021e5b9  mov     rax, [rax+140h]
0x14021e5c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14021e5c5  mov     rcx, [rsp+10C8h]; this
0x14021e5cd  test    eax, eax
0x14021e5cf  js      loc_14021F036
0x14021e5d5  mov     rdx, [r15]
0x14021e5d8  lea     rcx, [rsp+10C8h+var_1038]
0x14021e5e0  call    ?ReadMemorySettingsFromTheConfiguration@VmMemoryConfigurationKeys@@YA?AUMemorySettings@VmWorkerProcess@Config@@PEAVVmRepository@@@Z; VmMemoryConfigurationKeys::ReadMemorySettingsFromTheConfiguration(VmRepository *)
0x14021e5e5  mov     rdx, rax
0x14021e5e8  lea     rcx, [rsp+10C8h+var_B58]
0x14021e5f0  call    ??4MemorySettings@VmWorkerProcess@Config@@QEAAAEAU012@$$QEAU012@@Z; Config::VmWorkerProcess::MemorySettings::operator=(Config::VmWorkerProcess::MemorySettings &&)
0x14021e5f5  lea     rcx, [rsp+10C8h+var_1038]; this
0x14021e5fd  call    ??1MemorySettings@VmWorkerProcess@Config@@QEAA@XZ; Config::VmWorkerProcess::MemorySettings::~MemorySettings(void)
0x14021e602  lea     r8, [rbx+0F0h]; struct VmRepository *
0x14021e609  mov     rdx, [r15]; struct Config::VmWorkerProcess::MemorySettings *
0x14021e60c  lea     rcx, [rsp+10C8h+var_B58]; this
0x14021e614  call    ?GetMemoryParameters@VmUtilities@@YAJAEBUMemorySettings@VmWorkerProcess@Config@@PEAVVmRepository@@AEAU_VM_MEMORY_PARAMETERS@@@Z; VmUtilities::GetMemoryParameters(Config::VmWorkerProcess::MemorySettings const &,VmRepository *,_VM_MEMORY_PARAMETERS &)
0x14021e619  mov     rcx, [rsp+10C8h]; this
0x14021e621  test    eax, eax
0x14021e623  js      loc_14021F04B
0x14021e629  mov     rdx, [r15]
0x14021e62c  lea     rcx, [rsp+10C8h+var_1038]
0x14021e634  call    ?ReadProcessorSettingsFromTheConfiguration@VmProcessorConfigurationKeys@@YA?AUProcessorSettings@VmWorkerProcess@Config@@PEAVVmRepository@@@Z; VmProcessorConfigurationKeys::ReadProcessorSettingsFromTheConfiguration(VmRepository *)
0x14021e639  mov     rdx, rax
0x14021e63c  lea     rcx, [rsp+10C8h+var_DF8]
0x14021e644  call    ??4ProcessorSettings@VmWorkerProcess@Config@@QEAAAEAU012@$$QEAU012@@Z; Config::VmWorkerProcess::ProcessorSettings::operator=(Config::VmWorkerProcess::ProcessorSettings &&)
0x14021e649  lea     rcx, [rsp+10C8h+var_1038]; this
0x14021e651  call    ??1ProcessorSettings@VmWorkerProcess@Config@@QEAA@XZ; Config::VmWorkerProcess::ProcessorSettings::~ProcessorSettings(void)
0x14021e656  mov     rdx, [r15]
0x14021e659  lea     rcx, [rsp+10C8h+Buf2]
0x14021e65e  call    ?ReadNumaSettingsFromTheConfiguration@VmNumaConfigurationKeys@@YA?AUNumaSettings@VmWorkerProcess@Config@@PEAVVmRepository@@@Z; VmNumaConfigurationKeys::ReadNumaSettingsFromTheConfiguration(VmRepository *)
0x14021e663  mov     cl, [rax]
0x14021e665  mov     byte ptr [rsp+10C8h+var_BC0], cl
0x14021e66c  mov     cl, [rax+1]
0x14021e66f  mov     byte ptr [rsp+10C8h+var_BC0+1], cl
0x14021e676  lea     rdx, [rax+8]
0x14021e67a  lea     rcx, [rsp+10C8h+var_BB8]
0x14021e682  call    ??4?$vector@UNumaSetting@Compute@Resources@VirtualMachines@Schema@@V?$allocator@UNumaSetting@Compute@Resources@VirtualMachines@Schema@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<Schema::VirtualMachines::Resources::Compute::NumaSetting>::operator=(std::vector<Schema::VirtualMachines::Resources::Compute::NumaSetting> &&)
0x14021e687  lea     rcx, [rsp+10C8h+Buf2+8]
0x14021e68c  call    ?_Tidy@?$vector@UNumaSetting@Compute@Resources@VirtualMachines@Schema@@V?$allocator@UNumaSetting@Compute@Resources@VirtualMachines@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::VirtualMachines::Resources::Compute::NumaSetting>::_Tidy(void)
0x14021e691  mov     rcx, [r15]
0x14021e694  mov     rax, [rcx]
0x14021e697  lea     r8, [rsp+10C8h+var_BC8]
0x14021e69f  lea     rdx, ?VIRTUAL_MACHINE_NUMA_NODE_MASK_XPATH@@3QBGB; "/configuration/settings/numa_node_mask"
0x14021e6a6  mov     rax, [rax+70h]
0x14021e6aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14021e6af  test    eax, eax
0x14021e6b1  jns     short loc_14021E6BB
0x14021e6b3  mov     [rsp+10C8h+var_BC8], r13
0x14021e6bb  lea     rcx, [rsp+10C8h+var_BA0]; this
0x14021e6c3  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x14021e6c8  mov     [rsp+10C8h+var_BA0], 20h ; ' '
0x14021e6d4  mov     edx, dword ptr [rsp+10C8h+var_E08+4]; unsigned int
0x14021e6db  mov     ecx, dword ptr [rsp+10C8h+var_E08]; this
0x14021e6e2  call    ?GetSizeUpperBoundInMb@VmMemorySettings@@YA_KII@Z; VmMemorySettings::GetSizeUpperBoundInMb(uint,uint)
0x14021e6e7  mov     [rsp+10C8h+var_BA0+8], rax
0x14021e6ef  lea     rax, [rsp+10C8h+var_BA0]
0x14021e6f7  mov     qword ptr [rsp+10C8h+var_10A8], rax; int
0x14021e6fc  lea     r9, [rsp+10C8h+var_BC0]
0x14021e704  lea     r8, [rsp+10C8h+var_B58]
0x14021e70c  lea     rdx, [rsp+10C8h+var_DF8]
0x14021e714  lea     rcx, [rsp+10C8h+Buf2]
0x14021e719  call    ?GetVirtualNumaNodeCountFromSettings@VmUtilities@@YA?AUVirtualNumaNodeCountResult@@AEBUProcessorSettings@VmWorkerProcess@Config@@AEBUMemorySettings@45@AEBUNumaSettings@45@AEBU_MemorySettingBoundValues@@@Z; VmUtilities::GetVirtualNumaNodeCountFromSettings(Config::VmWorkerProcess::ProcessorSettings const &,Config::VmWorkerProcess::MemorySettings const &,Config::VmWorkerProcess::NumaSettings const &,_MemorySettingBoundValues const &)
0x14021e71e  mov     edx, [rax+10h]
0x14021e721  test    edx, edx
0x14021e723  jz      short loc_14021E758
0x14021e725  mov     ecx, 80070057h
0x14021e72a  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x14021e72f  mov     rcx, [rsp+10C8h]; this
0x14021e737  mov     r9d, eax; char *
0x14021e73a  lea     r8, aOnecoreVmCompu_121; "onecore\\vm\\compute\\management\\resou"...
0x14021e741  test    dl, 8
0x14021e744  jnz     loc_14021F060
0x14021e74a  test    dl, 2
0x14021e74d  jz      loc_14021F0B0
0x14021e753  jmp     loc_14021F088
0x14021e758  mov     dil, [rax]
0x14021e75b  cmp     dword ptr [rbx+78h], 1
0x14021e75f  jnz     short loc_14021E774
0x14021e761  mov     rax, [rsp+10C8h+var_B38]
0x14021e769  shl     rax, 8
0x14021e76d  mov     [rbx+0C8h], rax
0x14021e774  lea     rcx, [rbx+930h]
0x14021e77b  lea     rdx, [rsp+10C8h+var_A18]
0x14021e783  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x14021e788  lea     r14, [rbx+0C1h]
0x14021e78f  mov     [r14], dil
0x14021e792  mov     rax, [rsp+10C8h+var_BC8]
0x14021e79a  mov     [rbx+0E8h], rax
0x14021e7a1  lea     r12, [rbx+0A0h]
0x14021e7a8  mov     eax, [rsp+10C8h+var_DB8]
0x14021e7af  mov     [r12], eax
0x14021e7b3  cmp     [rsp+10C8h+var_C07], r13b
0x14021e7bb  jz      short loc_14021E7CA
0x14021e7bd  mov     al, [rsp+10C8h+var_C08]
0x14021e7c4  mov     [rbx+9C0h], al
0x14021e7ca  xorps   xmm0, xmm0
0x14021e7cd  movups  [rsp+10C8h+Buf2], xmm0
0x14021e7d2  mov     r8d, 10h; Size
0x14021e7d8  lea     rdx, [rsp+10C8h+Buf2]; Buf2
0x14021e7dd  lea     rcx, [rsp+10C8h+Buf1]; Buf1
0x14021e7e5  call    memcmp_0
0x14021e7ea  test    eax, eax
0x14021e7ec  jz      short loc_14021E7FE
0x14021e7ee  lea     rdx, [rsp+10C8h+Buf1]; struct _GUID *
0x14021e7f6  mov     rcx, rbx; this
0x14021e7f9  call    ?SelectNumaNodes@MemoryResourceInstance@Resource@ComputeService@@AEAAXAEBU_GUID@@@Z; ComputeService::Resource::MemoryResourceInstance::SelectNumaNodes(_GUID const &)
0x14021e7fe  call    ?GetInfo@VmPhysicalProcessorInfo@Vml@@SAPEAV12@XZ; Vml::VmPhysicalProcessorInfo::GetInfo(void)
0x14021e803  mov     rdi, rax
0x14021e806  mov     edx, [rbx+78h]
0x14021e809  sub     edx, 1
0x14021e80c  jz      short loc_14021E87E
0x14021e80e  sub     edx, 1
0x14021e811  jz      short loc_14021E868
0x14021e813  sub     edx, 1
0x14021e816  jz      short loc_14021E868
0x14021e818  cmp     edx, 1
0x14021e81b  jnz     loc_14021EA36
0x14021e821  mov     eax, [rbx+9C4h]
0x14021e827  test    eax, eax
0x14021e829  jnz     short loc_14021E838
0x14021e82b  mov     eax, [rsp+10C8h+var_DB4]
0x14021e832  mov     [rbx+9C4h], eax
0x14021e838  cmp     dword ptr [rsp+10C8h+var_E08], 900h
0x14021e843  jb      loc_14021EA36
0x14021e849  test    eax, eax
0x14021e84b  jnz     loc_14021EA36
0x14021e851  mov     eax, [rdi+2Ch]
0x14021e854  cmp     [rdi+34h], eax
0x14021e857  sbb     eax, eax
0x14021e859  neg     eax
0x14021e85b  inc     eax
0x14021e85d  mov     [rbx+9C4h], eax
0x14021e863  jmp     loc_14021EA36
0x14021e868  cmp     dword ptr [rbx+9C4h], 0FFFFFFFFh
0x14021e86f  jnz     loc_14021EA36
0x14021e875  mov     eax, [rsp+10C8h+var_DB4]
0x14021e87c  jmp     short loc_14021E85D
0x14021e87e  mov     eax, [rsp+10C8h+var_DB4]
0x14021e885  mov     [rbx+9C4h], eax
0x14021e88b  cmp     dword ptr [rsp+10C8h+var_E08], 900h
0x14021e896  jb      short loc_14021E8AE
0x14021e898  test    eax, eax
0x14021e89a  jnz     short loc_14021E8AE
0x14021e89c  mov     eax, [rdi+2Ch]
0x14021e89f  cmp     [rdi+34h], eax
0x14021e8a2  sbb     eax, eax
0x14021e8a4  neg     eax
0x14021e8a6  inc     eax
0x14021e8a8  mov     [rbx+9C4h], eax
0x14021e8ae  cmp     [rsp+10C8h+var_CF0], r13b
0x14021e8b6  jz      short loc_14021E90A
0x14021e8b8  mov     eax, [rsp+10C8h+var_CF4]
0x14021e8bf  test    eax, eax
0x14021e8c1  jnz     short loc_14021E8DC
0x14021e8c3  lea     rcx, [rsp+10C8h+Buf2]
0x14021e8c8  call    ComputeService__Resource__GetHostMaxProcessorCountPerL3
0x14021e8cd  mov     rcx, [rax]
0x14021e8d0  mov     [rbx+9B0h], rcx
0x14021e8d7  jmp     loc_14021E9E2
0x14021e8dc  mov     [rbx+9B0h], eax
0x14021e8e2  mov     byte ptr [rbx+9B4h], 1
0x14021e8e9  movzx   eax, word ptr [rsp+10C8h+var_BC8+5]
0x14021e8f1  mov     [rbx+9B5h], ax
0x14021e8f8  mov     al, byte ptr [rsp+10C8h+var_BC8+7]
0x14021e8ff  mov     [rbx+9B7h], al
0x14021e905  jmp     loc_14021E9E2
0x14021e90a  xorps   xmm0, xmm0
0x14021e90d  movups  xmmword ptr [rsp+10C8h+var_B70], xmm0
0x14021e915  lea     rcx, [rsp+10C8h+var_1068]
0x14021e91a  call    ??$make_unique@VVmMachineLocalSettingsStore@Vml@@$$V$0A@@std@@YA?AV?$unique_ptr@VVmMachineLocalSettingsStore@Vml@@U?$default_delete@VVmMachineLocalSettingsStore@Vml@@@std@@@0@XZ; std::make_unique<Vml::VmMachineLocalSettingsStore,,0>(void)
0x14021e91f  nop
0x14021e920  mov     rcx, [rax]
0x14021e923  mov     [rax], r13
0x14021e926  mov     [rsp+10C8h+var_1070], rcx
0x14021e92b  lea     r9, [rsp+10C8h+var_1070]
0x14021e930  lea     rcx, [rsp+10C8h+var_B70]
0x14021e938  call    ??0VirtualizationSettings@@QEAA@_NPEBG$$QEAV?$unique_ptr@VISettingsStore@@U?$default_delete@VISettingsStore@@@std@@@std@@@Z; VirtualizationSettings::VirtualizationSettings(bool,ushort const *,std::unique_ptr<ISettingsStore> &&)
0x14021e93d  nop
0x14021e93e  lea     rcx, [rsp+10C8h+var_1070]
0x14021e943  call    ??1?$unique_ptr@UComputeSystemConfiguration@Management@ComputeService@@U?$default_delete@UComputeSystemConfiguration@Management@ComputeService@@@std@@@std@@QEAA@XZ; std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(void)
0x14021e948  nop
0x14021e949  lea     rcx, [rsp+10C8h+var_1068]
0x14021e94e  call    ??1?$unique_ptr@UComputeSystemConfiguration@Management@ComputeService@@U?$default_delete@UComputeSystemConfiguration@Management@ComputeService@@@std@@@std@@QEAA@XZ; std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(void)
0x14021e953  lea     rcx, [rsp+10C8h+var_B70]; this
0x14021e95b  call    ?GetAzureFeatureSetEnabled@VirtualizationSettings@@UEBA_NXZ; VirtualizationSettings::GetAzureFeatureSetEnabled(void)
0x14021e960  neg     al
0x14021e962  sbb     esi, esi
0x14021e964  and     esi, 0FFFFFF03h
0x14021e96a  add     esi, 0A00h
0x14021e970  call    ?IsHypervisorRootSchedulerEnabled@Helpers@ServiceCapabilities@Management@ComputeService@@YA_NXZ; ComputeService::Management::ServiceCapabilities::Helpers::IsHypervisorRootSchedulerEnabled(void)
0x14021e975  test    al, al
0x14021e977  jnz     short loc_14021E9D5
0x14021e979  cmp     dword ptr [rdi], 2
0x14021e97c  jnz     short loc_14021E9D5
0x14021e97e  cmp     dword ptr [rsp+10C8h+var_E08], esi
0x14021e985  jb      short loc_14021E9D5
0x14021e987  lea     rcx, [rsp+10C8h+Buf2]
0x14021e98c  call    ComputeService__Resource__GetHostMaxProcessorCountPerL3
0x14021e991  cmp     [rax+4], r13b
0x14021e995  jz      loc_14021F0BB
0x14021e99b  mov     eax, [rax]
0x14021e99d  cmp     [rsp+10C8h+var_D28], eax
0x14021e9a4  cmovb   eax, [rsp+10C8h+var_D28]
0x14021e9ac  mov     [rbx+9B0h], eax
0x14021e9b2  mov     byte ptr [rbx+9B4h], 1
0x14021e9b9  movzx   eax, word ptr [rsp+10C8h+var_BC8+5]
0x14021e9c1  mov     [rbx+9B5h], ax
0x14021e9c8  mov     al, byte ptr [rsp+10C8h+var_BC8+7]
0x14021e9cf  mov     [rbx+9B7h], al
0x14021e9d5  lea     rcx, [rsp+10C8h+var_B70+8]
0x14021e9dd  call    ??1?$unique_ptr@UComputeSystemConfiguration@Management@ComputeService@@U?$default_delete@UComputeSystemConfiguration@Management@ComputeService@@@std@@@std@@QEAA@XZ; std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(void)
0x14021e9e2  cmp     [rsp+10C8h+var_CE8], r13b
0x14021e9ea  jz      short loc_14021EA36
0x14021e9ec  mov     eax, [rsp+10C8h+var_CEC]
0x14021e9f3  test    eax, eax
0x14021e9f5  jnz     short loc_14021EA0D
0x14021e9f7  lea     rcx, [rsp+10C8h+Buf2]
0x14021e9fc  call    ComputeService__Resource__GetHostMaxClusterCountPerSocket
0x14021ea01  mov     rcx, [rax]
0x14021ea04  mov     [rbx+9B8h], rcx
0x14021ea0b  jmp     short loc_14021EA36
0x14021ea0d  mov     [rbx+9B8h], eax
0x14021ea13  mov     byte ptr [rbx+9BCh], 1
0x14021ea1a  movzx   eax, word ptr [rsp+10C8h+var_BC8+5]
0x14021ea22  mov     [rbx+9BDh], ax
0x14021ea29  mov     al, byte ptr [rsp+10C8h+var_BC8+7]
0x14021ea30  mov     [rbx+9BFh], al
0x14021ea36  mov     ecx, [rbx+9C4h]
0x14021ea3c  lea     eax, [rcx-1]
0x14021ea3f  cmp     eax, 1
0x14021ea42  ja      loc_14021EFDC
0x14021ea48  cmp     [rsp+10C8h+var_D8C], r13b
0x14021ea50  jz      short loc_14021EA65
0x14021ea52  xor     edx, edx
0x14021ea54  mov     eax, [rsp+10C8h+var_DB8]
0x14021ea5b  div     ecx
0x14021ea5d  test    edx, edx
0x14021ea5f  jnz     loc_14021F0C1
0x14021ea65  xorps   xmm1, xmm1
0x14021ea68  movdqu  [rsp+10C8h+var_B88], xmm1
0x14021ea71  mov     [rsp+10C8h+var_B78], r13
0x14021ea79  lea     rax, [rsp+10C8h+var_B88]
0x14021ea81  mov     [rsp+10C8h+var_1098], rax
0x14021ea86  mov     rax, [rbx+0C8h]
0x14021ea8d  mov     [rsp+10C8h+var_10A0], rax
0x14021ea92  mov     eax, [r12]
0x14021ea96  mov     dword ptr [rsp+10C8h+var_10A8], eax
0x14021ea9a  mov     r9d, dword ptr [rsp+10C8h+var_E08+4]
  ... truncated ...
```
