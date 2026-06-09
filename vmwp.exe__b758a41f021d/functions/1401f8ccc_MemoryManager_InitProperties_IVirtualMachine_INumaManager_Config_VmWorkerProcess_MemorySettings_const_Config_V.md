# MemoryManager::InitProperties(IVirtualMachine *,INumaManager *,Config::VmWorkerProcess::MemorySettings const &,Config::VmWorkerProcess::NumaSettings const &,Config::VmWorkerProcess::CompatibilitySettings const &,Config::VmWorkerProcess::TopologySettings const &,bool)

- ea: `0x1401f8ccc`
- end: `0x1401f976c`
- name: `?InitProperties@MemoryManager@@AEAAXPEAUIVirtualMachine@@PEAUINumaManager@@AEBUMemorySettings@VmWorkerProcess@Config@@AEBUNumaSettings@56@AEBUCompatibilitySettings@56@AEBUTopologySettings@56@_N@Z`
- size: `2720`
- prototype: `void __fastcall(MemoryManager *__hidden this, struct IVirtualMachine *, struct INumaManager *, const struct Config::VmWorkerProcess::MemorySettings *, const struct Config::VmWorkerProcess::NumaSettings *, const struct Config::VmWorkerProcess::CompatibilitySettings *, const struct Config::VmWorkerProcess::TopologySettings *, bool)`
- caller_count: `1`
- callee_count: `42`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140075700`

## callees

- `0x1400314a4`
- `0x14003264c`
- `0x1400364a0`
- `0x14004517c`
- `0x1400466b8`
- `0x140053de8`
- `0x140053f10`
- `0x1400545bc`
- `0x140055af4`
- `0x140055e18`
- `0x14005c4b8`
- `0x14005e524`
- `0x140066eec`
- `0x140072128`
- `0x140073f70`
- `0x140078628`
- `0x140083990`
- `0x14008ff18`
- `0x140096934`
- `0x1400ba144`
- `0x1400c1de4`
- `0x1400cff50`
- `0x1400d65d4`
- `0x1400da040`
- `0x1401106f4`
- `0x140114ce0`
- `0x14011ea40`
- `0x14011edec`
- `0x14011f6fc`
- `0x140138908`
- `0x14014e438`
- `0x140161200`
- `0x140176a40`
- `0x1401ed67c`
- `0x1401f25c4`
- `0x1401f2838`
- `0x1401f3b80`
- `0x1401f8490`
- `0x1401f8ccc`
- `0x140200370`
- `0x1402077b0`
- `0x1402cb010`

## import_xrefs

- `ntdll!NtPowerInformation` at `0x1401f94cf`
- `ntdll!NtPowerInformation` at `0x1401f94cf`
- `vid!VidOpenStatisticsHandle` at `0x1401f93e1`
- `vid!VidOpenStatisticsHandle` at `0x1401f93e1`
- `vid!VidGetSystemInformation` at `0x1401f947b`
- `vid!VidGetSystemInformation` at `0x1401f947b`
- `vid!VidGetPartitionProperty` at `0x1401f93b6`
- `vid!VidGetPartitionProperty` at `0x1401f93b6`

## string_xrefs

- `0x1401f90d5`: `/configuration/settings/topology/shared_memory_mb`
- `0x1401f907b`: `/configuration/settings/topology/direct_file_mapping_mb`
- `0x1401f9409`: `Failed to open VID statistics handle`
- `0x1401f8e6c`: `System\CurrentControlSet\Services\Vid\Parameters\MemoryReserve\Primary`
- `0x1401f8ecc`: `UseSystemPartitionForHvDeposits`
- `0x1401f8efa`: `UseSystemPartitionForPhysicalBuffers`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
void __fastcall MemoryManager::InitProperties(
        MemoryManager *this,
        struct IVirtualMachine *a2,
        struct INumaManager *a3,
        const struct Config::VmWorkerProcess::MemorySettings *a4,
        unsigned int **a5,
        const struct Config::VmWorkerProcess::CompatibilitySettings *a6,
        const struct Config::VmWorkerProcess::TopologySettings *a7,
        bool a8)
{
  __int64 v11; // rax
  std::_Ref_count_base *v12; // r12
  __int64 *v13; // rax
  __int64 v14; // rdx
  const char *v15; // r9
  __int64 v16; // rbx
  int v17; // eax
  int v18; // eax
  __int64 v19; // r14
  __int64 v20; // rax
  int v21; // eax
  HKEY v22; // rdx
  int v23; // eax
  __int64 v24; // rdx
  __int64 *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rax
  RamUsage *v29; // rbx
  unsigned __int8 VirtualNumaNodeCount; // al
  int v31; // eax
  std::_Ref_count_base *v32; // rbx
  unsigned __int64 v33; // rbx
  char *v34; // r14
  __int64 v35; // r8
  unsigned __int64 v36; // rcx
  char *v37; // rax
  size_t v38; // rbx
  unsigned int *v39; // r9
  unsigned int *v40; // rdx
  const struct _GUID *v41; // r8
  const char *v42; // r9
  std::_Ref_count_base *v43; // rbx
  const char *v44; // r9
  bool v45; // bl
  NTSTATUS v46; // eax
  unsigned int v47; // eax
  unsigned int v48; // eax
  unsigned int v49; // eax
  const char *v50; // rdx
  unsigned int v51; // eax
  const char *v52; // rdx
  unsigned int v53; // eax
  int OutputBufferLength; // [rsp+20h] [rbp-118h]
  int OutputBufferLengtha; // [rsp+20h] [rbp-118h]
  char *v56; // [rsp+28h] [rbp-110h]
  char *v57; // [rsp+28h] [rbp-110h]
  char *v58; // [rsp+28h] [rbp-110h]
  char *v59; // [rsp+30h] [rbp-108h]
  std::_Ref_count_base *v60[2]; // [rsp+50h] [rbp-E8h] BYREF
  const struct Config::VmWorkerProcess::MemorySettings *v61; // [rsp+60h] [rbp-D8h]
  const struct Config::VmWorkerProcess::NumaSettings *v62; // [rsp+70h] [rbp-C8h]
  char v63[64]; // [rsp+80h] [rbp-B8h] BYREF
  char OutputBuffer[8]; // [rsp+C0h] [rbp-78h] BYREF
  unsigned int v65[2]; // [rsp+C8h] [rbp-70h] BYREF
  HKEY phkResult; // [rsp+D0h] [rbp-68h] BYREF
  struct IVirtualMachine *v67; // [rsp+D8h] [rbp-60h] BYREF
  __int64 v68; // [rsp+E0h] [rbp-58h] BYREF
  char v69; // [rsp+E8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v67 = a2;
  v61 = a4;
  v62 = (const struct Config::VmWorkerProcess::NumaSettings *)a5;
  Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::Reset(&qword_1403CC910);
  Vml::VmReferencePtr<VndCompletionThread,Vml::VmUserReferenceTraits>::Reset(&qword_1403CC918, a3);
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)qword_1403CC910 + 56LL))(qword_1403CC910, &v68);
  Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::operator=(&qword_1403CC920, v11);
  Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(&v68);
  if ( (unsigned int)(*((_DWORD *)a7 + 17) - 3) <= 1 )
    byte_1403CCB98 = 1;
  v12 = (std::_Ref_count_base *)*((_QWORD *)a4 + 4);
  v60[0] = v12;
  v13 = (__int64 *)Vml::CreateComObject<MemoryBalancerInterface,>(&v68);
  v14 = *v13;
  *v13 = 0;
  Vml::VmComPtr<MemoryBalancerInterface>::Attach<MemoryBalancerInterface>(&qword_1403CC9F8, v14);
  Vml::VmComPtr<TdxStateMigrationTransfer::TdxStateMigrationTransferObjectSourceImpl>::~VmComPtr<TdxStateMigrationTransfer::TdxStateMigrationTransferObjectSourceImpl>(&v68);
  v16 = qword_1403CC9F8;
  if ( !qword_1403CC9F8 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x50A,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      v15);
  Vml::VmReferencePtr<VndCompletionThread,Vml::VmUserReferenceTraits>::Reset(qword_1403CC9F8 + 32, qword_1403CC918);
  *(_QWORD *)(v16 + 128) = 0;
  std::wstring::operator=(v16 + 88, (char *)a4 + 48);
  if ( a8 )
  {
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)qword_1403CC910 + 424LL))(qword_1403CC910, &v68);
    *(__int16 *)((char *)&word_1403CC9C8 + 1) = 257;
    qword_1403CC9D0 = v68;
    byte_1403CC9D8 = (v68 & 8) != 0;
    if ( v69 )
    {
      if ( (v68 & 0x20) != 0 && (v68 & 0x40) == 0 )
        qword_1403CC9D0 = v68 & 0xFFFFFFFFFFFFFFF7uLL;
    }
  }
  phkResult = 0;
  if ( (unsigned int)Vml::VmRegistryKey::Open(
                       &phkResult,
                       HKEY_LOCAL_MACHINE,
                       L"System\\CurrentControlSet\\Services\\Vid\\Parameters\\MemoryReserve\\Primary",
                       0x20019u) )
  {
    v65[0] = 0;
    if ( Vml::VmRegistryKey::QueryValue((Vml::VmRegistryKey *)&phkResult, L"AllowSpillingForHvDeposits", v65) )
      BYTE1(dword_1403CCBF8) = v65[0] != 0;
    if ( Vml::VmRegistryKey::QueryValue((Vml::VmRegistryKey *)&phkResult, L"UseSystemPartitionForHvDeposits", v65) )
      BYTE2(dword_1403CCBF8) = v65[0] != 0;
    if ( Vml::VmRegistryKey::QueryValue((Vml::VmRegistryKey *)&phkResult, L"UseSystemPartitionForPhysicalBuffers", v65) )
      HIBYTE(dword_1403CCBF8) = v65[0] != 0;
  }
  Vml::VmRegistryKey::Close((Vml::VmRegistryKey *)&phkResult);
  *(_OWORD *)v60 = 0;
  VmRepositoryAutoLock::VmRepositoryAutoLock(v60, qword_1403CC920, 0);
  if ( SLODWORD(v60[1]) < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x54D,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      (const char *)LODWORD(v60[1]),
      OutputBufferLength);
  v17 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)qword_1403CC920 + 288LL))(
          qword_1403CC920,
          &dword_1403CC980);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x552,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      (const char *)(unsigned int)v17,
      OutputBufferLength);
  v18 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)qword_1403CC920 + 320LL))(
          qword_1403CC920,
          &dword_1403CC984);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x553,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      (const char *)(unsigned int)v18,
      OutputBufferLength);
  v19 = 0;
  if ( *((_BYTE *)a4 + 256) )
  {
    BYTE4(qword_1403CCB4C) = 1;
    v19 = *((_QWORD *)a4 + 33);
  }
  if ( *((_BYTE *)a4 + 312) )
    BYTE5(qword_1403CCB4C) = 1;
  HIBYTE(qword_1403CCB4C) = (*(_DWORD *)a6 & 0x80) != 0;
  qword_1403CC940 = *((_QWORD *)a4 + 5);
  v20 = 0x40000;
  if ( *((_QWORD *)a4 + 23) == 0x40000 )
  {
    if ( (unsigned int)dword_1403CC980 < 0x803 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
        VmlDebugTrace(16416, L"Only RS4 or above VMs support huge page.\n");
      v48 = wil::verify_hresult<long>(2147778582LL);
      LODWORD(v56) = (_DWORD)dword_1403CC980;
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x574,
        (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
        (const char *)v48,
        (int)"VM version %x does not support huge page.",
        v56);
    }
  }
  else
  {
    v20 = 512;
  }
  qword_1403CCB78 = v20;
  v21 = (int)dword_1403CC984;
  if ( (_DWORD)dword_1403CC984 == 8 || (_DWORD)dword_1403CC984 == 1 )
  {
    phkResult = 0;
    if ( (*(int (__fastcall **)(__int64, const unsigned __int16 *, HKEY *))(*(_QWORD *)qword_1403CC920 + 120LL))(
           qword_1403CC920,
           L"/configuration/settings/topology/direct_file_mapping_mb",
           &phkResult) >= 0 )
    {
      v22 = phkResult;
      if ( ((unsigned __int8)phkResult & 1) != 0 )
      {
        v49 = wil::verify_hresult<long>(2147942487LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x58A,
          (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
          (const char *)v49,
          (int)"directFileMappingMb = %I64u",
          v50);
      }
      if ( (unsigned __int64)phkResult > 0x10000 )
        v22 = (HKEY)0x10000;
      phkResult = v22;
    }
    *(_QWORD *)v65 = 0;
    v23 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned int *))(*(_QWORD *)qword_1403CC920
                                                                                       + 120LL))(
            qword_1403CC920,
            L"/configuration/settings/topology/shared_memory_mb",
            v65);
    v24 = *(_QWORD *)v65;
    if ( v23 >= 0 )
    {
      if ( (v65[0] & 1) != 0 )
      {
        v51 = wil::verify_hresult<long>(2147942487LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x59C,
          (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
          (const char *)v51,
          (int)"sharedMemoryMb = %I64u",
          v52);
      }
      if ( *(_QWORD *)v65 > 0x10000u )
        v24 = 0x10000;
    }
    qword_1403CCA78 = (_QWORD)phkResult << 8;
    qword_1403CCA80 = v24 << 8;
    qword_1403CCA88 = (v24 << 8) + ((_QWORD)phkResult << 8);
    v21 = (int)dword_1403CC984;
  }
  if ( (unsigned int)dword_1403CC980 >= 0x701 && v21 == 1 )
    byte_1403CCB48 = 0;
  VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v60);
  v25 = (__int64 *)std::make_unique<GpaSpaceBestFitAllocator,unsigned __int64 const &,0>(v60);
  v26 = *v25;
  *v25 = 0;
  v27 = qword_1403CCAB8;
  qword_1403CCAB8 = v26;
  if ( v27 )
    std::default_delete<GpaSpaceBestFitAllocator>::operator()();
  std::unique_ptr<GpaSpaceBestFitAllocator>::~unique_ptr<GpaSpaceBestFitAllocator>(v60);
  v28 = std::make_shared<RamUsage,>(v60);
  __4__shared_ptr___CBX_std__QEAAAEAV01___QEAV01__Z(&qword_1403CCA58, v28);
  if ( v60[1] )
    std::_Ref_count_base::_Decref(v60[1]);
  v29 = qword_1403CCA58;
  VirtualNumaNodeCount = MemoryManager::GetVirtualNumaNodeCount((MemoryManager *)&MemoryManager::m_Instance);
  v31 = RamUsage::Initialize(v29, VirtualNumaNodeCount);
  if ( v31 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5B8,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      (const char *)(unsigned int)v31,
      OutputBufferLength);
  v32 = (std::_Ref_count_base *)operator new(0x498u);
  v60[0] = v32;
  memset_0(v32, 0, 0x498u);
  qword_1403CC9A0 = (__int64)MemoryConfiguration::MemoryConfiguration(v32);
  v59 = (char *)(v19 << 8);
  v57 = (char *)((_QWORD)v12 << 8);
  (**(void (__fastcall ***)(__int64, struct IVirtualMachine *, __int64, __int64))qword_1403CC9A0)(
    qword_1403CC9A0,
    a2,
    qword_1403CC918,
    (qword_1403CC9F8 + 24) & -(__int64)(qword_1403CC9F8 != 0));
  if ( qword_1403CC940 == 3 )
  {
    if ( *(_DWORD *)(*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)qword_1403CC9A0 + 40LL))(
                      qword_1403CC9A0,
                      v63) )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x5CE,
        (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
        (const char *)0x32,
        (unsigned int)a5);
    v33 = 0x6DB6DB6DB6DB6DB7LL * (((char *)a5[2] - (char *)a5[1]) >> 3);
    v34 = (char *)xmmword_1403CC950;
    v35 = qword_1403CC948;
    v36 = ((__int64)xmmword_1403CC950 - qword_1403CC948) >> 2;
    if ( v33 >= v36 )
    {
      if ( v33 <= v36 )
        goto LABEL_56;
      if ( v33 > ((__int64)*(&xmmword_1403CC950 + 1) - qword_1403CC948) >> 2 )
      {
        std::vector<enum Schema::VirtualMachines::Resources::Compute::MemoryBackingType>::_Resize_reallocate<std::_Value_init_tag>(
          &qword_1403CC948,
          0x6DB6DB6DB6DB6DB7LL * (((char *)a5[2] - (char *)a5[1]) >> 3));
        v35 = qword_1403CC948;
        goto LABEL_56;
      }
      v38 = 4 * (v33 - v36);
      memset_0(xmmword_1403CC950, 0, v38);
      v37 = &v34[v38];
      v35 = qword_1403CC948;
    }
    else
    {
      v37 = (char *)(qword_1403CC948 - 0x4924924924924924LL * (((char *)a5[2] - (char *)a5[1]) >> 3));
    }
    xmmword_1403CC950 = v37;
LABEL_56:
    v39 = a5[2];
    v40 = a5[1];
    if ( v40 != v39 )
    {
      while ( 1 )
      {
        *(_DWORD *)(v35 + 4LL * *v40) = v40[6];
        v40 += 14;
        if ( v40 == v39 )
          break;
        v35 = qword_1403CC948;
      }
    }
  }
  if ( *((_BYTE *)a4 + 344) )
  {
    if ( (_DWORD)dword_1403CC984 != 1 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
        VmlDebugTrace(16416, L"Only generation 2 VMs support memory encryption");
      v53 = wil::verify_hresult<long>(2147778583LL);
      LODWORD(v57) = (_DWORD)dword_1403CC984;
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x608,
        (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
        (const char *)v53,
        (int)"virtualSystemSubType = %u",
        v57);
    }
    LODWORD(v59) = (_DWORD)dword_1403CC980;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x60F,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      (const char *)0x80048016LL,
      (unsigned int)dword_1403CC980 < 0xA00,
      (bool)"VM version %x does not support memory encryption.",
      v59);
    v67 = 0;
    if ( !(unsigned int)VidGetPartitionProperty(-1, 393216, &v67) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x61D,
        (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
        v42);
    if ( v67 != (struct IVirtualMachine *)1 )
      goto LABEL_71;
    v43 = (std::_Ref_count_base *)VidOpenStatisticsHandle(retaddr);
    v60[0] = v43;
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0x624,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      (const char *)((((unsigned __int64)v43 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0),
      (bool)"Failed to open VID statistics handle",
      v58);
    v65[0] = 0;
    v68 = 0;
    LODWORD(phkResult) = 13;
    LODWORD(v58) = 8;
    if ( !(unsigned int)VidGetSystemInformation(v43, 10, &phkResult) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x632,
        (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
        v44);
    v45 = 0;
    if ( v68 )
    {
      v45 = 1;
      if ( (unsigned int)Vml::VmOsVersion::IsOsClientVersion() )
      {
        OutputBuffer[0] = 0;
        v46 = NtPowerInformation((POWER_INFORMATION_LEVEL)66, 0, 0, OutputBuffer, 1u);
        if ( v46 < 0 )
          wil::details::in1diag3::_Throw_NtStatus(
            retaddr,
            (void *)0x645,
            (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
            (const char *)(unsigned int)v46,
            OutputBufferLengtha);
        v45 = OutputBuffer[0] != 0;
      }
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>(v60);
    if ( v45 )
    {
      byte_1403CCC68 = 1;
    }
    else
    {
LABEL_71:
      if ( *((_BYTE *)a4 + 344) == 2 )
      {
        VmEventWriteAndReport(
          &MSVML_WP_INIT_MEMORY_ENCRYPTION_NOT_SUPPORTED_ERROR,
          5u,
          v41,
          (const unsigned __int16 *)v42);
        v47 = wil::verify_hresult<long>(2147942450LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x65C,
          (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
          (const char *)v47,
          (int)"Memory encryption not supported",
          v58);
      }
    }
  }
  BYTE6(qword_1403CCB4C) = *((_BYTE *)a4 + 317);
}

```

## disassembly

```asm
0x1401f8ccc  push    rbx
0x1401f8cce  push    rsi
0x1401f8ccf  push    rdi
0x1401f8cd0  push    r12
0x1401f8cd2  push    r13
0x1401f8cd4  push    r14
0x1401f8cd6  push    r15
0x1401f8cd8  sub     rsp, 100h
0x1401f8cdf  mov     rax, cs:__security_cookie
0x1401f8ce6  xor     rax, rsp
0x1401f8ce9  mov     [rsp+138h+var_48], rax
0x1401f8cf1  mov     rsi, r9
0x1401f8cf4  mov     rbx, r8
0x1401f8cf7  mov     r13, rdx
0x1401f8cfa  mov     [rsp+138h+var_60], rdx
0x1401f8d02  mov     [rsp+138h+var_D8], r9
0x1401f8d07  mov     r15, [rsp+138h+arg_20]
0x1401f8d0f  mov     [rsp+138h+var_C8], r15
0x1401f8d14  lea     rcx, qword_1403CC910
0x1401f8d1b  call    ?Reset@?$VmReferencePtr@UIVirtualMachine@@VVmWeakReferenceTraits@Vml@@@Vml@@QEAAXPEAUIVirtualMachine@@@Z; Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::Reset(IVirtualMachine *)
0x1401f8d20  mov     rdx, rbx
0x1401f8d23  lea     rcx, qword_1403CC918
0x1401f8d2a  call    ?Reset@?$VmReferencePtr@VVndCompletionThread@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVVndCompletionThread@@@Z; Vml::VmReferencePtr<VndCompletionThread,Vml::VmUserReferenceTraits>::Reset(VndCompletionThread *)
0x1401f8d2f  mov     rcx, cs:qword_1403CC910
0x1401f8d36  mov     rax, [rcx]
0x1401f8d39  lea     rdx, [rsp+138h+var_58]
0x1401f8d41  mov     rax, [rax+38h]
0x1401f8d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401f8d4a  mov     rdx, rax
0x1401f8d4d  lea     rcx, qword_1403CC920
0x1401f8d54  call    ??4?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAAEBV01@$$QEAV01@@Z; Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::operator=(Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> &&)
0x1401f8d59  lea     rcx, [rsp+138h+var_58]
0x1401f8d61  call    ??1?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(void)
0x1401f8d66  mov     rax, [rsp+138h+arg_30]
0x1401f8d6e  mov     ecx, [rax+44h]
0x1401f8d71  sub     ecx, 3
0x1401f8d74  cmp     ecx, 1
0x1401f8d77  ja      short loc_1401F8D80
0x1401f8d79  mov     cs:byte_1403CCB98, 1
0x1401f8d80  mov     r12, [rsi+20h]
0x1401f8d84  mov     [rsp+138h+var_E8], r12
0x1401f8d89  lea     rcx, [rsp+138h+var_58]
0x1401f8d91  call    ??$CreateComObject@VMemoryBalancerInterface@@$$V@Vml@@YA?AV?$VmComPtr@VMemoryBalancerInterface@@@0@XZ; Vml::CreateComObject<MemoryBalancerInterface,>(void)
0x1401f8d96  mov     rdx, [rax]
0x1401f8d99  xor     edi, edi
0x1401f8d9b  mov     [rax], rdi
0x1401f8d9e  lea     rcx, qword_1403CC9F8
0x1401f8da5  call    ??$Attach@VMemoryBalancerInterface@@@?$VmComPtr@VMemoryBalancerInterface@@@Vml@@QEAAXPEAVMemoryBalancerInterface@@@Z; Vml::VmComPtr<MemoryBalancerInterface>::Attach<MemoryBalancerInterface>(MemoryBalancerInterface *)
0x1401f8daa  lea     rcx, [rsp+138h+var_58]
0x1401f8db2  call    ??1?$VmComPtr@VTdxStateMigrationTransferObjectSourceImpl@TdxStateMigrationTransfer@@@Vml@@QEAA@XZ; Vml::VmComPtr<TdxStateMigrationTransfer::TdxStateMigrationTransferObjectSourceImpl>::~VmComPtr<TdxStateMigrationTransfer::TdxStateMigrationTransferObjectSourceImpl>(void)
0x1401f8db7  mov     rcx, [rsp+138h]; this
0x1401f8dbf  mov     rbx, cs:qword_1403CC9F8
0x1401f8dc6  test    rbx, rbx
0x1401f8dc9  jz      loc_1401F958A
0x1401f8dcf  lea     rcx, [rbx+20h]
0x1401f8dd3  mov     rdx, cs:qword_1403CC918
0x1401f8dda  call    ?Reset@?$VmReferencePtr@VVndCompletionThread@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVVndCompletionThread@@@Z; Vml::VmReferencePtr<VndCompletionThread,Vml::VmUserReferenceTraits>::Reset(VndCompletionThread *)
0x1401f8ddf  mov     [rbx+80h], rdi
0x1401f8de6  lea     rdx, [rsi+30h]
0x1401f8dea  lea     rcx, [rbx+58h]
0x1401f8dee  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1401f8df3  cmp     [rsp+138h+arg_38], dil
0x1401f8dfb  jz      short loc_1401F8E5E
0x1401f8dfd  mov     rcx, cs:qword_1403CC910
0x1401f8e04  mov     rax, [rcx]
0x1401f8e07  lea     rdx, [rsp+138h+var_58]
0x1401f8e0f  mov     rax, [rax+1A8h]
0x1401f8e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401f8e1b  mov     cs:word_1403CC9C8+1, 101h
0x1401f8e24  mov     rax, [rsp+138h+var_58]
0x1401f8e2c  mov     cs:qword_1403CC9D0, rax
0x1401f8e33  mov     cl, al
0x1401f8e35  shr     cl, 3
0x1401f8e38  and     cl, 1
0x1401f8e3b  mov     cs:byte_1403CC9D8, cl
0x1401f8e41  cmp     [rsp+138h+var_50], dil
0x1401f8e49  jz      short loc_1401F8E5E
0x1401f8e4b  test    al, 20h
0x1401f8e4d  jz      short loc_1401F8E5E
0x1401f8e4f  test    al, 40h
0x1401f8e51  jnz     short loc_1401F8E5E
0x1401f8e53  and     rax, 0FFFFFFFFFFFFFFF7h
0x1401f8e57  mov     cs:qword_1403CC9D0, rax
0x1401f8e5e  mov     [rsp+138h+phkResult], rdi
0x1401f8e66  mov     r9d, 20019h; unsigned int
0x1401f8e6c  lea     r8, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Vi"...
0x1401f8e73  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1401f8e7a  lea     rcx, [rsp+138h+phkResult]; phkResult
0x1401f8e82  call    ?Open@VmRegistryKey@Vml@@QEAAHPEAUHKEY__@@PEBGK@Z; Vml::VmRegistryKey::Open(HKEY__ *,ushort const *,ulong)
0x1401f8e87  test    eax, eax
0x1401f8e89  jz      loc_1401F8F20
0x1401f8e8f  mov     [rsp+138h+var_70], edi
0x1401f8e96  lea     r8, [rsp+138h+var_70]; unsigned int *
0x1401f8e9e  lea     rdx, aAllowspillingf; "AllowSpillingForHvDeposits"
0x1401f8ea5  lea     rcx, [rsp+138h+phkResult]; this
0x1401f8ead  call    ?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAK@Z; Vml::VmRegistryKey::QueryValue(ushort const *,ulong &)
0x1401f8eb2  test    eax, eax
0x1401f8eb4  jz      short loc_1401F8EC4
0x1401f8eb6  cmp     [rsp+138h+var_70], edi
0x1401f8ebd  setnz   byte ptr cs:dword_1403CCBF8+1
0x1401f8ec4  lea     r8, [rsp+138h+var_70]; unsigned int *
0x1401f8ecc  lea     rdx, aUsesystemparti; "UseSystemPartitionForHvDeposits"
0x1401f8ed3  lea     rcx, [rsp+138h+phkResult]; this
0x1401f8edb  call    ?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAK@Z; Vml::VmRegistryKey::QueryValue(ushort const *,ulong &)
0x1401f8ee0  test    eax, eax
0x1401f8ee2  jz      short loc_1401F8EF2
0x1401f8ee4  cmp     [rsp+138h+var_70], edi
0x1401f8eeb  setnz   byte ptr cs:dword_1403CCBF8+2
0x1401f8ef2  lea     r8, [rsp+138h+var_70]; unsigned int *
0x1401f8efa  lea     rdx, aUsesystemparti_0; "UseSystemPartitionForPhysicalBuffers"
0x1401f8f01  lea     rcx, [rsp+138h+phkResult]; this
0x1401f8f09  call    ?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAK@Z; Vml::VmRegistryKey::QueryValue(ushort const *,ulong &)
0x1401f8f0e  test    eax, eax
0x1401f8f10  jz      short loc_1401F8F20
0x1401f8f12  cmp     [rsp+138h+var_70], edi
0x1401f8f19  setnz   byte ptr cs:dword_1403CCBF8+3
0x1401f8f20  lea     rcx, [rsp+138h+phkResult]; this
0x1401f8f28  call    ?Close@VmRegistryKey@Vml@@QEAAXXZ; Vml::VmRegistryKey::Close(void)
0x1401f8f2d  nop
0x1401f8f2e  jmp     short loc_1401F8F49
0x1401f8f30  xor     edi, edi
0x1401f8f32  mov     r13, [rsp+138h+var_60]
0x1401f8f3a  mov     rsi, [rsp+138h+var_D8]
0x1401f8f3f  mov     r15, [rsp+138h+var_C8]
0x1401f8f44  mov     r12, [rsp+138h+var_E8]
0x1401f8f49  xorps   xmm0, xmm0
0x1401f8f4c  movups  xmmword ptr [rsp+138h+var_E8], xmm0
0x1401f8f51  xor     r8d, r8d
0x1401f8f54  mov     rdx, cs:qword_1403CC920
0x1401f8f5b  lea     rcx, [rsp+138h+var_E8]
0x1401f8f60  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x1401f8f65  nop
0x1401f8f66  mov     r9d, dword ptr [rsp+138h+var_E8+8]; char *
0x1401f8f6b  mov     rcx, [rsp+138h]; this
0x1401f8f73  test    r9d, r9d
0x1401f8f76  js      loc_1401F959C
0x1401f8f7c  mov     rcx, cs:qword_1403CC920
0x1401f8f83  mov     rax, [rcx]
0x1401f8f86  lea     rdx, dword_1403CC980
0x1401f8f8d  mov     rax, [rax+120h]
0x1401f8f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401f8f99  mov     rcx, [rsp+138h]; this
0x1401f8fa1  test    eax, eax
0x1401f8fa3  js      loc_1401F95AE
0x1401f8fa9  mov     rcx, cs:qword_1403CC920
0x1401f8fb0  mov     rax, [rcx]
0x1401f8fb3  lea     rdx, dword_1403CC984
0x1401f8fba  mov     rax, [rax+140h]
0x1401f8fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401f8fc6  mov     rcx, [rsp+138h]; this
0x1401f8fce  test    eax, eax
0x1401f8fd0  js      loc_1401F95C3
0x1401f8fd6  mov     r14, rdi
0x1401f8fd9  cmp     [rsi+100h], dil
0x1401f8fe0  jz      short loc_1401F8FF0
0x1401f8fe2  mov     byte ptr cs:qword_1403CCB4C+4, 1
0x1401f8fe9  mov     r14, [rsi+108h]
0x1401f8ff0  cmp     [rsi+138h], dil
0x1401f8ff7  jz      short loc_1401F9000
0x1401f8ff9  mov     byte ptr cs:qword_1403CCB4C+5, 1
0x1401f9000  mov     rax, [rsp+138h+arg_28]
0x1401f9008  mov     ecx, [rax]
0x1401f900a  shr     ecx, 7
0x1401f900d  and     cl, 1
0x1401f9010  mov     byte ptr cs:qword_1403CCB4C+7, cl
0x1401f9016  mov     rax, [rsi+28h]
0x1401f901a  mov     cs:qword_1403CC940, rax
0x1401f9021  mov     eax, 40000h
0x1401f9026  cmp     [rsi+0B8h], rax
0x1401f902d  jnz     short loc_1401F9041
0x1401f902f  cmp     cs:dword_1403CC980, 803h
0x1401f9039  jb      loc_1401F95D8
0x1401f903f  jmp     short loc_1401F9046
0x1401f9041  mov     eax, 200h
0x1401f9046  mov     cs:qword_1403CCB78, rax
0x1401f904d  mov     eax, cs:dword_1403CC984
0x1401f9053  cmp     eax, 8
0x1401f9056  jz      short loc_1401F9061
0x1401f9058  cmp     eax, 1
0x1401f905b  jnz     loc_1401F912F
0x1401f9061  mov     [rsp+138h+phkResult], rdi
0x1401f9069  mov     rcx, cs:qword_1403CC920
0x1401f9070  mov     rax, [rcx]
0x1401f9073  lea     r8, [rsp+138h+phkResult]
0x1401f907b  lea     rdx, ?VIRTUAL_MACHINE_TOPOLOGY_DIRECT_FILE_MAPPING_XPATH@@3QBGB; "/configuration/settings/topology/direct"...
0x1401f9082  mov     rax, [rax+78h]
0x1401f9086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401f908b  test    eax, eax
0x1401f908d  js      short loc_1401F90B6
0x1401f908f  mov     rdx, [rsp+138h+phkResult]
0x1401f9097  test    dl, 1
0x1401f909a  jnz     loc_1401F9633
0x1401f90a0  mov     ebx, 10000h
0x1401f90a5  cmp     rdx, rbx
0x1401f90a8  cmova   rdx, rbx
0x1401f90ac  mov     [rsp+138h+phkResult], rdx
0x1401f90b4  jmp     short loc_1401F90BB
0x1401f90b6  mov     ebx, 10000h
0x1401f90bb  mov     qword ptr [rsp+138h+var_70], rdi
0x1401f90c3  mov     rcx, cs:qword_1403CC920
0x1401f90ca  mov     rax, [rcx]
0x1401f90cd  lea     r8, [rsp+138h+var_70]
0x1401f90d5  lea     rdx, ?VIRTUAL_MACHINE_TOPOLOGY_SHARED_MEMORY_XPATH@@3QBGB; "/configuration/settings/topology/shared"...
0x1401f90dc  mov     rax, [rax+78h]
0x1401f90e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401f90e5  mov     rdx, qword ptr [rsp+138h+var_70]
0x1401f90ed  test    eax, eax
0x1401f90ef  js      short loc_1401F9101
0x1401f90f1  test    dl, 1
0x1401f90f4  jnz     loc_1401F966B
0x1401f90fa  cmp     rdx, rbx
0x1401f90fd  cmova   rdx, rbx
0x1401f9101  mov     rax, [rsp+138h+phkResult]
0x1401f9109  shl     rax, 8
0x1401f910d  mov     cs:qword_1403CCA78, rax
0x1401f9114  shl     rdx, 8
0x1401f9118  mov     cs:qword_1403CCA80, rdx
0x1401f911f  add     rax, rdx
0x1401f9122  mov     cs:qword_1403CCA88, rax
0x1401f9129  mov     eax, cs:dword_1403CC984
0x1401f912f  cmp     cs:dword_1403CC980, 701h
0x1401f9139  jb      short loc_1401F9147
0x1401f913b  cmp     eax, 1
0x1401f913e  jnz     short loc_1401F9147
0x1401f9140  mov     cs:byte_1403CCB48, dil
0x1401f9147  lea     rcx, [rsp+138h+var_E8]; this
0x1401f914c  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1401f9151  lea     rcx, [rsp+138h+var_E8]
0x1401f9156  call    ??$make_unique@VGpaSpaceBestFitAllocator@@AEB_K$0A@@std@@YA?AV?$unique_ptr@VGpaSpaceBestFitAllocator@@U?$default_delete@VGpaSpaceBestFitAllocator@@@std@@@0@AEB_K@Z; std::make_unique<GpaSpaceBestFitAllocator,unsigned __int64 const &,0>(unsigned __int64 const &)
0x1401f915b  mov     rcx, [rax]
0x1401f915e  mov     [rax], rdi
0x1401f9161  mov     rdx, cs:qword_1403CCAB8
0x1401f9168  mov     cs:qword_1403CCAB8, rcx
0x1401f916f  test    rdx, rdx
0x1401f9172  jz      short loc_1401F9179
0x1401f9174  call    ??R?$default_delete@VGpaSpaceBestFitAllocator@@@std@@QEBAXPEAVGpaSpaceBestFitAllocator@@@Z; std::default_delete<GpaSpaceBestFitAllocator>::operator()(GpaSpaceBestFitAllocator *)
0x1401f9179  lea     rcx, [rsp+138h+var_E8]
0x1401f917e  call    ??1?$unique_ptr@VGpaSpaceBestFitAllocator@@U?$default_delete@VGpaSpaceBestFitAllocator@@@std@@@std@@QEAA@XZ; std::unique_ptr<GpaSpaceBestFitAllocator>::~unique_ptr<GpaSpaceBestFitAllocator>(void)
0x1401f9183  lea     rcx, [rsp+138h+var_E8]
0x1401f9188  call    ??$make_shared@VRamUsage@@$$V@std@@YA?AV?$shared_ptr@VRamUsage@@@0@XZ; std::make_shared<RamUsage,>(void)
0x1401f918d  mov     rdx, rax
0x1401f9190  lea     rcx, qword_1403CCA58
0x1401f9197  call    ??4?$shared_ptr@$$CBX@std@@QEAAAEAV01@$$QEAV01@@Z
0x1401f919c  mov     rcx, [rsp+138h+var_E8+8]; this
0x1401f91a1  test    rcx, rcx
0x1401f91a4  jz      short loc_1401F91AB
0x1401f91a6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1401f91ab  mov     rbx, cs:qword_1403CCA58
0x1401f91b2  lea     rcx, ?m_Instance@MemoryManager@@0V1@A; this
0x1401f91b9  call    ?GetVirtualNumaNodeCount@MemoryManager@@AEBAEXZ; MemoryManager::GetVirtualNumaNodeCount(void)
0x1401f91be  mov     dl, al; unsigned __int8
0x1401f91c0  mov     rcx, rbx; this
0x1401f91c3  call    ?Initialize@RamUsage@@QEAAJE@Z; RamUsage::Initialize(uchar)
0x1401f91c8  mov     rcx, [rsp+138h]; this
0x1401f91d0  test    eax, eax
0x1401f91d2  js      loc_1401F96A3
0x1401f91d8  mov     ecx, 498h; Size
0x1401f91dd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1401f91e2  mov     rbx, rax
0x1401f91e5  mov     [rsp+138h+var_E8], rax
0x1401f91ea  xor     edx, edx; Val
0x1401f91ec  mov     r8d, 498h; Size
0x1401f91f2  mov     rcx, rax; void *
0x1401f91f5  call    memset_0
0x1401f91fa  mov     rcx, rbx; this
0x1401f91fd  call    ??0MemoryConfiguration@@QEAA@XZ; MemoryConfiguration::MemoryConfiguration(void)
0x1401f9202  nop
0x1401f9203  mov     cs:qword_1403CC9A0, rax
0x1401f920a  mov     r11, cs:qword_1403CCB78
0x1401f9211  mov     r9, cs:qword_1403CC9F8
0x1401f9218  mov     r10, [rax]
0x1401f921b  shl     r14, 8
0x1401f921f  shl     r12, 8
0x1401f9223  lea     rcx, [r9+18h]
0x1401f9227  neg     r9
0x1401f922a  sbb     r9, r9
0x1401f922d  and     r9, rcx
0x1401f9230  mov     [rsp+138h+var_100], r11
0x1401f9235  mov     [rsp+138h+var_108], r14
0x1401f923a  mov     [rsp+138h+var_110], r12
0x1401f923f  mov     qword ptr [rsp+138h+OutputBufferLength], r15; unsigned int
0x1401f9244  mov     r8, cs:qword_1403CC918
0x1401f924b  mov     rdx, r13
0x1401f924e  mov     rcx, rax
0x1401f9251  mov     rax, [r10]
0x1401f9254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401f9259  cmp     cs:qword_1403CC940, 3
0x1401f9261  jnz     loc_1401F9342
0x1401f9267  mov     rcx, cs:qword_1403CC9A0
0x1401f926e  mov     rax, [rcx]
0x1401f9271  lea     rdx, [rsp+138h+var_B8]
0x1401f9279  mov     rax, [rax+28h]
0x1401f927d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401f9282  cmp     [rax], edi
0x1401f9284  jnz     loc_1401F96B8
0x1401f928a  mov     rbx, [r15+10h]
0x1401f928e  sub     rbx, [r15+8]
0x1401f9292  sar     rbx, 3
0x1401f9296  mov     rax, 6DB6DB6DB6DB6DB7h
0x1401f92a0  imul    rbx, rax
  ... truncated ...
```
