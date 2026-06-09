# MemoryManager::InitProperties(IVirtualMachine *,INumaManager *,Config::VmWorkerProcess::MemorySettings const &,Config::VmWorkerProcess::NumaSettings const &,Config::VmWorkerProcess::CompatibilitySettings const &,Config::VmWorkerProcess::TopologySettings const &,bool)

- ea: `0x140085fb8`
- end: `0x140086a9f`
- name: `?InitProperties@MemoryManager@@AEAAXPEAUIVirtualMachine@@PEAUINumaManager@@AEBUMemorySettings@VmWorkerProcess@Config@@AEBUNumaSettings@56@AEBUCompatibilitySettings@56@AEBUTopologySettings@56@_N@Z`
- size: `2791`
- prototype: `void __fastcall(MemoryManager *__hidden this, struct IVirtualMachine *, struct INumaManager *, const struct Config::VmWorkerProcess::MemorySettings *, const struct Config::VmWorkerProcess::NumaSettings *, const struct Config::VmWorkerProcess::CompatibilitySettings *, const struct Config::VmWorkerProcess::TopologySettings *, bool)`
- caller_count: `1`
- callee_count: `40`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140068030`

## callees

- `0x140033634`
- `0x140033698`
- `0x140033b9c`
- `0x140042260`
- `0x140047ad8`
- `0x1400544a8`
- `0x1400545d0`
- `0x140054a90`
- `0x140055d80`
- `0x14005600c`
- `0x14005b648`
- `0x14005ecc0`
- `0x14006407c`
- `0x140066780`
- `0x14006af58`
- `0x14007e5a0`
- `0x140085d24`
- `0x140085fb8`
- `0x140086aa8`
- `0x140086ac8`
- `0x140086be0`
- `0x1400996d8`
- `0x14009d7cc`
- `0x1400c5a3c`
- `0x1400d4974`
- `0x1400e52f4`
- `0x1400e75ac`
- `0x140120084`
- `0x140123fa8`
- `0x140132960`
- `0x140132d0c`
- `0x14013361c`
- `0x14014c608`
- `0x14016176c`
- `0x140172bf0`
- `0x1401896b0`
- `0x1401fd4ec`
- `0x140202514`
- `0x140203898`
- `0x1402c2010`

## import_xrefs

- `ntdll!NtPowerInformation` at `0x1400869da`
- `ntdll!NtPowerInformation` at `0x1400869da`
- `vid!VidOpenStatisticsHandle` at `0x1400868de`
- `vid!VidOpenStatisticsHandle` at `0x1400868de`
- `vid!VidGetSystemInformation` at `0x140086978`
- `vid!VidGetSystemInformation` at `0x140086978`
- `vid!VidGetPartitionProperty` at `0x1400868a5`
- `vid!VidGetPartitionProperty` at `0x1400868a5`

## string_xrefs

- `0x140086906`: `Failed to open VID statistics handle`
- `0x14008649c`: `/configuration/settings/topology/shared_memory_mb`
- `0x140086416`: `/configuration/settings/topology/direct_file_mapping_mb`
- `0x140086189`: `System\CurrentControlSet\Services\Vid\Parameters\MemoryReserve\Primary`
- `0x140086217`: `UseSystemPartitionForPhysicalBuffers`
- `0x1400861e9`: `UseSystemPartitionForHvDeposits`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall MemoryManager::InitProperties(
        MemoryManager *this,
        struct IVirtualMachine *a2,
        struct INumaManager *a3,
        const struct Config::VmWorkerProcess::MemorySettings *a4,
        const struct Config::VmWorkerProcess::NumaSettings *a5,
        const struct Config::VmWorkerProcess::CompatibilitySettings *a6,
        const struct Config::VmWorkerProcess::TopologySettings *a7,
        bool a8)
{
  const struct Config::VmWorkerProcess::MemorySettings *v8; // rsi
  struct IVirtualMachine *v10; // r13
  const struct Config::VmWorkerProcess::NumaSettings *v11; // r15
  __int64 v12; // rax
  std::_Ref_count_base *v13; // r12
  __int64 *v14; // rax
  __int64 v15; // rdx
  const char *v16; // r9
  __int64 v17; // rbx
  const char *v18; // r9
  int v19; // eax
  int v20; // eax
  __int64 v21; // r14
  __int64 v22; // rax
  int v23; // eax
  HKEY v24; // rax
  int v25; // eax
  __int64 v26; // rdx
  __int64 *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rdx
  _DWORD *v30; // rax
  RamUsage *v31; // rbx
  unsigned __int8 VirtualNumaNodeCount; // al
  int v33; // eax
  _QWORD *v34; // rbx
  const unsigned __int16 *v35; // rdx
  unsigned __int64 v36; // rbx
  char *v37; // r14
  __int64 v38; // r8
  unsigned __int64 v39; // rcx
  char *v40; // rax
  size_t v41; // rbx
  unsigned int *v42; // r9
  unsigned int *v43; // rdx
  const struct _GUID *v44; // r8
  const char *v45; // r9
  std::_Ref_count_base *v46; // rbx
  const char *v47; // r9
  bool v48; // bl
  NTSTATUS v49; // eax
  int OutputBufferLength; // [rsp+20h] [rbp-118h]
  int OutputBufferLengtha; // [rsp+20h] [rbp-118h]
  char *v52; // [rsp+28h] [rbp-110h]
  char *v53; // [rsp+28h] [rbp-110h]
  char *v54; // [rsp+28h] [rbp-110h]
  char *v55; // [rsp+30h] [rbp-108h]
  __int64 v56; // [rsp+38h] [rbp-100h]
  std::_Ref_count_base *v57[2]; // [rsp+50h] [rbp-E8h] BYREF
  const struct Config::VmWorkerProcess::MemorySettings *v58; // [rsp+60h] [rbp-D8h]
  const struct Config::VmWorkerProcess::NumaSettings *v59; // [rsp+70h] [rbp-C8h]
  char v60[64]; // [rsp+80h] [rbp-B8h] BYREF
  char OutputBuffer[8]; // [rsp+C0h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+C8h] [rbp-70h] BYREF
  char *v63; // [rsp+D0h] [rbp-68h] BYREF
  struct IVirtualMachine *v64; // [rsp+D8h] [rbp-60h] BYREF
  __int64 v65; // [rsp+E0h] [rbp-58h] BYREF
  char v66; // [rsp+E8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v8 = a4;
  v10 = a2;
  v64 = a2;
  v58 = a4;
  v11 = a5;
  v59 = a5;
  Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::Reset(&qword_1403C0380);
  Vml::VmReferencePtr<VndCompletionThread,Vml::VmUserReferenceTraits>::Reset(&qword_1403C0388, a3);
  v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)qword_1403C0380 + 56LL))(qword_1403C0380, &v65);
  Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::operator=(&qword_1403C0390, v12);
  Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(&v65);
  byte_1403C0608 = *((_DWORD *)a7 + 17) == 3;
  v13 = (std::_Ref_count_base *)*((_QWORD *)v8 + 4);
  v57[0] = v13;
  if ( byte_1403C0608 && *((_QWORD *)a7 + 3) > (unsigned __int64)v13 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x506,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      (const char *)0x80070057LL,
      OutputBufferLength);
  v14 = (__int64 *)Vml::CreateComObject<MemoryBalancerInterface,>(&v65);
  v15 = *v14;
  *v14 = 0;
  Vml::VmComPtr<MemoryBalancerInterface>::Attach<MemoryBalancerInterface>(&qword_1403C0468, v15);
  Vml::VmComPtr<TdxStateMigrationTransfer::TdxStateMigrationTransferObjectSourceImpl>::~VmComPtr<TdxStateMigrationTransfer::TdxStateMigrationTransferObjectSourceImpl>(&v65);
  v17 = qword_1403C0468;
  if ( !qword_1403C0468 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x50A,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      v16);
  Vml::VmReferencePtr<VndCompletionThread,Vml::VmUserReferenceTraits>::Reset(qword_1403C0468 + 32, qword_1403C0388);
  *(_QWORD *)(v17 + 128) = 0;
  std::wstring::operator=(v17 + 88, (char *)v8 + 48);
  if ( a8 )
  {
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)qword_1403C0380 + 408LL))(qword_1403C0380, &v65);
    *(__int16 *)((char *)&word_1403C0438 + 1) = 257;
    qword_1403C0440 = v65;
    byte_1403C0448 = (v65 & 8) != 0;
    if ( v66 )
    {
      if ( (v65 & 0x60) == 0x20 )
        qword_1403C0440 = v65 & 0xFFFFFFFFFFFFFFF7uLL;
    }
  }
  try
  {
    phkResult = 0;
    if ( (unsigned int)Vml::VmRegistryKey::Open(
                         &phkResult,
                         HKEY_LOCAL_MACHINE,
                         L"System\\CurrentControlSet\\Services\\Vid\\Parameters\\MemoryReserve\\Primary",
                         0x20019u) )
    {
      LODWORD(v63) = 0;
      if ( Vml::VmRegistryKey::QueryValue(
             (Vml::VmRegistryKey *)&phkResult,
             L"AllowSpillingForHvDeposits",
             (unsigned int *)&v63) )
      {
        BYTE1(dword_1403C0668) = (_DWORD)v63 != 0;
      }
      if ( Vml::VmRegistryKey::QueryValue(
             (Vml::VmRegistryKey *)&phkResult,
             L"UseSystemPartitionForHvDeposits",
             (unsigned int *)&v63) )
      {
        BYTE2(dword_1403C0668) = (_DWORD)v63 != 0;
      }
      if ( Vml::VmRegistryKey::QueryValue(
             (Vml::VmRegistryKey *)&phkResult,
             L"UseSystemPartitionForPhysicalBuffers",
             (unsigned int *)&v63) )
      {
        HIBYTE(dword_1403C0668) = (_DWORD)v63 != 0;
      }
    }
    Vml::VmRegistryKey::Close((Vml::VmRegistryKey *)&phkResult);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x548,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      v18);
    v10 = v64;
    v8 = v58;
    v11 = v59;
    v13 = v57[0];
  }
  *(_OWORD *)v57 = 0;
  VmRepositoryAutoLock::VmRepositoryAutoLock(v57, qword_1403C0390, 0);
  if ( SLODWORD(v57[1]) < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x54D,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      (const char *)LODWORD(v57[1]),
      OutputBufferLength);
  v19 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)qword_1403C0390 + 288LL))(
          qword_1403C0390,
          &dword_1403C03F0);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x552,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      (const char *)(unsigned int)v19,
      OutputBufferLength);
  v20 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)qword_1403C0390 + 320LL))(
          qword_1403C0390,
          &dword_1403C03F4);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x553,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      (const char *)(unsigned int)v20,
      OutputBufferLength);
  v21 = 0;
  if ( *((_BYTE *)v8 + 256) )
  {
    BYTE4(qword_1403C05BC) = 1;
    v21 = *((_QWORD *)v8 + 33);
  }
  if ( *((_BYTE *)v8 + 312) )
    BYTE5(qword_1403C05BC) = 1;
  HIBYTE(qword_1403C05BC) = (*(_DWORD *)a6 & 0x80) != 0;
  qword_1403C03B0 = *((_QWORD *)v8 + 5);
  v22 = 0x40000;
  if ( *((_QWORD *)v8 + 23) == 0x40000 )
  {
    if ( (unsigned int)dword_1403C03F0 < 0x803 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
        VmlDebugTrace(16416, L"Only RS4 or above VMs support huge page.\n");
      LODWORD(v52) = (_DWORD)dword_1403C03F0;
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x574,
        (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
        (const char *)0x80048016LL,
        (int)"VM version %x does not support huge page.",
        v52);
    }
  }
  else
  {
    v22 = 512;
  }
  qword_1403C05E8 = v22;
  v23 = (int)dword_1403C03F4;
  if ( (_DWORD)dword_1403C03F4 == 8 || (_DWORD)dword_1403C03F4 == 1 )
  {
    phkResult = 0;
    if ( (*(int (__fastcall **)(__int64, const unsigned __int16 *, HKEY *))(*(_QWORD *)qword_1403C0390 + 120LL))(
           qword_1403C0390,
           L"/configuration/settings/topology/direct_file_mapping_mb",
           &phkResult) >= 0 )
    {
      v24 = phkResult;
      if ( ((unsigned __int8)phkResult & 1) != 0 )
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x58A,
          (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
          (const char *)0x80070057LL,
          (int)"directFileMappingMb = %I64u",
          (const char *)phkResult);
      if ( (unsigned __int64)phkResult > 0x10000 )
        v24 = (HKEY)0x10000;
      phkResult = v24;
    }
    v63 = 0;
    v25 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, char **))(*(_QWORD *)qword_1403C0390 + 120LL))(
            qword_1403C0390,
            L"/configuration/settings/topology/shared_memory_mb",
            &v63);
    v26 = (__int64)v63;
    if ( v25 >= 0 )
    {
      if ( ((unsigned __int8)v63 & 1) != 0 )
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x59C,
          (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
          (const char *)0x80070057LL,
          (int)"sharedMemoryMb = %I64u",
          v63);
      if ( (unsigned __int64)v63 > 0x10000 )
        v26 = 0x10000;
    }
    qword_1403C04E8 = (_QWORD)phkResult << 8;
    qword_1403C04F0 = v26 << 8;
    qword_1403C04F8 = (v26 << 8) + ((_QWORD)phkResult << 8);
    v23 = (int)dword_1403C03F4;
  }
  if ( (unsigned int)dword_1403C03F0 >= 0x701 && v23 == 1 )
    byte_1403C05B8 = 0;
  VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
  v27 = (__int64 *)std::make_unique<GpaSpaceBestFitAllocator,unsigned __int64 const &,0>(v57);
  v28 = *v27;
  *v27 = 0;
  v29 = qword_1403C0528;
  qword_1403C0528 = v28;
  if ( v29 )
    std::default_delete<GpaSpaceBestFitAllocator>::operator()();
  std::unique_ptr<GpaSpaceBestFitAllocator>::~unique_ptr<GpaSpaceBestFitAllocator>(v57);
  v30 = operator new(0x48u);
  *(_OWORD *)v30 = 0;
  v30[2] = 1;
  v30[3] = 1;
  *(_QWORD *)v30 = &std::_Ref_count_obj2<RamUsage>::`vftable';
  *((_QWORD *)v30 + 3) = 0;
  *((_QWORD *)v30 + 4) = 0;
  *((_QWORD *)v30 + 5) = 0;
  *((_QWORD *)v30 + 6) = 0;
  *((_QWORD *)v30 + 7) = 0;
  *((_QWORD *)v30 + 8) = 0;
  v57[0] = (std::_Ref_count_base *)(v30 + 4);
  v57[1] = (std::_Ref_count_base *)v30;
  __4__shared_ptr___CBX_std__QEAAAEAV01___QEAV01__Z(&qword_1403C04C8, v57);
  if ( v57[1] )
    std::_Ref_count_base::_Decref(v57[1]);
  v31 = qword_1403C04C8;
  VirtualNumaNodeCount = MemoryManager::GetVirtualNumaNodeCount((MemoryManager *)&MemoryManager::m_Instance);
  v33 = RamUsage::Initialize(v31, VirtualNumaNodeCount);
  if ( v33 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5B8,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      (const char *)(unsigned int)v33,
      OutputBufferLength);
  v34 = operator new(0x498u);
  v57[0] = (std::_Ref_count_base *)v34;
  memset_0(v34, 0, 0x498u);
  *v34 = &MemoryConfiguration::`vftable';
  v34[1] = 0;
  v34[2] = 0;
  v34[3] = 0;
  v34[4] = 0;
  Vml::VmSlimReaderWriterLock::VmSlimReaderWriterLock((Vml::VmSlimReaderWriterLock *)(v34 + 13), v35);
  v34[15] = 0;
  v34[16] = 0;
  v34[81] = 0;
  v34[146] = 0;
  qword_1403C0410 = (__int64)v34;
  v56 = qword_1403C05E8;
  v55 = (char *)(v21 << 8);
  v53 = (char *)((_QWORD)v13 << 8);
  (*(void (__fastcall **)(_QWORD *, struct IVirtualMachine *, __int64, __int64))*v34)(
    v34,
    v10,
    qword_1403C0388,
    (qword_1403C0468 + 24) & -(__int64)(qword_1403C0468 != 0));
  if ( qword_1403C03B0 == 3 )
  {
    if ( *(_DWORD *)(*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)qword_1403C0410 + 40LL))(
                      qword_1403C0410,
                      v60) )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x5CE,
        (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
        (const char *)0x32,
        (unsigned int)v11);
    v36 = 0x6DB6DB6DB6DB6DB7LL * ((__int64)(*((_QWORD *)v11 + 2) - *((_QWORD *)v11 + 1)) >> 3);
    v37 = (char *)xmmword_1403C03C0;
    v38 = qword_1403C03B8;
    v39 = ((__int64)xmmword_1403C03C0 - qword_1403C03B8) >> 2;
    if ( v36 >= v39 )
    {
      if ( v36 <= v39 )
        goto LABEL_67;
      if ( v36 > ((__int64)*(&xmmword_1403C03C0 + 1) - qword_1403C03B8) >> 2 )
      {
        std::vector<enum Schema::VirtualMachines::Resources::Compute::MemoryBackingType>::_Resize_reallocate<std::_Value_init_tag>(
          &qword_1403C03B8,
          0x6DB6DB6DB6DB6DB7LL * ((__int64)(*((_QWORD *)v11 + 2) - *((_QWORD *)v11 + 1)) >> 3));
        v38 = qword_1403C03B8;
        goto LABEL_67;
      }
      v41 = 4 * (v36 - v39);
      memset_0(xmmword_1403C03C0, 0, v41);
      v40 = &v37[v41];
      v38 = qword_1403C03B8;
    }
    else
    {
      v40 = (char *)(qword_1403C03B8
                   - 0x4924924924924924LL * ((__int64)(*((_QWORD *)v11 + 2) - *((_QWORD *)v11 + 1)) >> 3));
    }
    xmmword_1403C03C0 = v40;
LABEL_67:
    v42 = (unsigned int *)*((_QWORD *)v11 + 2);
    v43 = (unsigned int *)*((_QWORD *)v11 + 1);
    if ( v43 != v42 )
    {
      while ( 1 )
      {
        *(_DWORD *)(v38 + 4LL * *v43) = v43[6];
        v43 += 14;
        if ( v43 == v42 )
          break;
        v38 = qword_1403C03B8;
      }
    }
  }
  if ( *((_BYTE *)v8 + 344) )
  {
    if ( (_DWORD)dword_1403C03F4 != 1 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
        VmlDebugTrace(16416, L"Only generation 2 VMs support memory encryption");
      LODWORD(v53) = (_DWORD)dword_1403C03F4;
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x608,
        (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
        (const char *)0x80048017LL,
        (int)"virtualSystemSubType = %u",
        v53,
        v55,
        v56);
    }
    LODWORD(v55) = (_DWORD)dword_1403C03F0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x60F,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      (const char *)0x80048016LL,
      (unsigned int)dword_1403C03F0 < 0xA00,
      (bool)"VM version %x does not support memory encryption.",
      v55,
      v56);
    v64 = 0;
    if ( !(unsigned int)VidGetPartitionProperty(-1, 393216, &v64) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x61D,
        (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
        v45);
    if ( v64 != (struct IVirtualMachine *)1 )
      goto LABEL_88;
    v46 = (std::_Ref_count_base *)VidOpenStatisticsHandle(retaddr);
    v57[0] = v46;
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0x624,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      (const char *)((((unsigned __int64)v46 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0),
      (bool)"Failed to open VID statistics handle",
      v54);
    LODWORD(v63) = 0;
    v65 = 0;
    LODWORD(phkResult) = 13;
    LODWORD(v54) = 8;
    if ( !(unsigned int)VidGetSystemInformation(v46, 10, &phkResult) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x632,
        (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
        v47);
    v48 = 0;
    if ( v65 )
    {
      v48 = 1;
      if ( (unsigned int)Vml::VmOsVersion::IsOsClientVersion() )
      {
        OutputBuffer[0] = 0;
        v49 = NtPowerInformation((POWER_INFORMATION_LEVEL)66, 0, 0, OutputBuffer, 1u);
        if ( v49 < 0 )
          wil::details::in1diag3::_Throw_NtStatus(
            retaddr,
            (void *)0x645,
            (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
            (const char *)(unsigned int)v49,
            OutputBufferLengtha);
        v48 = OutputBuffer[0] != 0;
      }
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>(v57);
    if ( v48 )
    {
      byte_1403C06D8 = 1;
    }
    else
    {
LABEL_88:
      if ( *((_BYTE *)v8 + 344) == 2 )
      {
        VmEventWriteAndReport(
          &MSVML_WP_INIT_MEMORY_ENCRYPTION_NOT_SUPPORTED_ERROR,
          5u,
          v44,
          (const unsigned __int16 *)v45);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x65C,
          (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
          (const char *)0x80070032LL,
          (int)"Memory encryption not supported",
          v54);
      }
    }
  }
  BYTE6(qword_1403C05BC) = *((_BYTE *)v8 + 317);
}

```

## disassembly

```asm
0x140085fb8  push    rbx
0x140085fba  push    rsi
0x140085fbb  push    rdi
0x140085fbc  push    r12
0x140085fbe  push    r13
0x140085fc0  push    r14
0x140085fc2  push    r15
0x140085fc4  sub     rsp, 100h
0x140085fcb  mov     rax, cs:__security_cookie
0x140085fd2  xor     rax, rsp
0x140085fd5  mov     [rsp+138h+var_48], rax
0x140085fdd  mov     rsi, r9
0x140085fe0  mov     rbx, r8
0x140085fe3  mov     r13, rdx
0x140085fe6  mov     [rsp+138h+var_60], rdx
0x140085fee  mov     [rsp+138h+var_D8], r9
0x140085ff3  mov     r15, [rsp+138h+arg_20]
0x140085ffb  mov     [rsp+138h+var_C8], r15
0x140086000  xor     edi, edi
0x140086002  lea     rcx, qword_1403C0380
0x140086009  call    ?Reset@?$VmReferencePtr@UIVirtualMachine@@VVmWeakReferenceTraits@Vml@@@Vml@@QEAAXPEAUIVirtualMachine@@@Z; Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::Reset(IVirtualMachine *)
0x14008600e  mov     rdx, rbx
0x140086011  lea     rcx, qword_1403C0388
0x140086018  call    ?Reset@?$VmReferencePtr@VVndCompletionThread@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVVndCompletionThread@@@Z; Vml::VmReferencePtr<VndCompletionThread,Vml::VmUserReferenceTraits>::Reset(VndCompletionThread *)
0x14008601d  mov     rcx, cs:qword_1403C0380
0x140086024  mov     rax, [rcx]
0x140086027  lea     rdx, [rsp+138h+var_58]
0x14008602f  mov     rax, [rax+38h]
0x140086033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086038  mov     rdx, rax
0x14008603b  lea     rcx, qword_1403C0390
0x140086042  call    ??4?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAAEBV01@$$QEAV01@@Z; Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::operator=(Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> &&)
0x140086047  lea     rcx, [rsp+138h+var_58]
0x14008604f  call    ??1?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(void)
0x140086054  mov     rcx, [rsp+138h+arg_30]
0x14008605c  cmp     dword ptr [rcx+44h], 3
0x140086060  setz    cs:byte_1403C0608
0x140086067  mov     r12, [rsi+20h]
0x14008606b  mov     [rsp+138h+var_E8], r12
0x140086070  jnz     short loc_140086098
0x140086072  cmp     [rcx+18h], r12
0x140086076  jbe     short loc_140086098
0x140086078  mov     rcx, [rsp+138h]; this
0x140086080  mov     r9d, 80070057h; char *
0x140086086  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14008608d  mov     edx, 506h; void *
0x140086092  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140086098  lea     rcx, [rsp+138h+var_58]
0x1400860a0  call    ??$CreateComObject@VMemoryBalancerInterface@@$$V@Vml@@YA?AV?$VmComPtr@VMemoryBalancerInterface@@@0@XZ; Vml::CreateComObject<MemoryBalancerInterface,>(void)
0x1400860a5  mov     rdx, [rax]
0x1400860a8  mov     [rax], rdi
0x1400860ab  lea     rcx, qword_1403C0468
0x1400860b2  call    ??$Attach@VMemoryBalancerInterface@@@?$VmComPtr@VMemoryBalancerInterface@@@Vml@@QEAAXPEAVMemoryBalancerInterface@@@Z; Vml::VmComPtr<MemoryBalancerInterface>::Attach<MemoryBalancerInterface>(MemoryBalancerInterface *)
0x1400860b7  lea     rcx, [rsp+138h+var_58]
0x1400860bf  call    ??1?$VmComPtr@VTdxStateMigrationTransferObjectSourceImpl@TdxStateMigrationTransfer@@@Vml@@QEAA@XZ; Vml::VmComPtr<TdxStateMigrationTransfer::TdxStateMigrationTransferObjectSourceImpl>::~VmComPtr<TdxStateMigrationTransfer::TdxStateMigrationTransferObjectSourceImpl>(void)
0x1400860c4  mov     rcx, [rsp+138h]; this
0x1400860cc  mov     rbx, cs:qword_1403C0468
0x1400860d3  test    rbx, rbx
0x1400860d6  jnz     short loc_1400860EA
0x1400860d8  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400860df  mov     edx, 50Ah; void *
0x1400860e4  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1400860ea  lea     rcx, [rbx+20h]
0x1400860ee  mov     rdx, cs:qword_1403C0388
0x1400860f5  call    ?Reset@?$VmReferencePtr@VVndCompletionThread@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVVndCompletionThread@@@Z; Vml::VmReferencePtr<VndCompletionThread,Vml::VmUserReferenceTraits>::Reset(VndCompletionThread *)
0x1400860fa  mov     [rbx+80h], rdi
0x140086101  lea     rdx, [rsi+30h]
0x140086105  lea     rcx, [rbx+58h]
0x140086109  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14008610e  cmp     [rsp+138h+arg_38], dil
0x140086116  jz      short loc_14008617B
0x140086118  mov     rcx, cs:qword_1403C0380
0x14008611f  mov     rax, [rcx]
0x140086122  lea     rdx, [rsp+138h+var_58]
0x14008612a  mov     rax, [rax+198h]
0x140086131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086136  mov     cs:word_1403C0438+1, 101h
0x14008613f  mov     rax, [rsp+138h+var_58]
0x140086147  mov     cs:qword_1403C0440, rax
0x14008614e  mov     cl, al
0x140086150  shr     cl, 3
0x140086153  and     cl, 1
0x140086156  mov     cs:byte_1403C0448, cl
0x14008615c  cmp     [rsp+138h+var_50], dil
0x140086164  jz      short loc_14008617B
0x140086166  mov     cl, al
0x140086168  and     cl, 60h
0x14008616b  cmp     cl, 20h ; ' '
0x14008616e  jnz     short loc_14008617B
0x140086170  and     rax, 0FFFFFFFFFFFFFFF7h
0x140086174  mov     cs:qword_1403C0440, rax
0x14008617b  mov     [rsp+138h+phkResult], rdi
0x140086183  mov     r9d, 20019h; unsigned int
0x140086189  lea     r8, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Vi"...
0x140086190  mov     rdx, 0FFFFFFFF80000002h; hKey
0x140086197  lea     rcx, [rsp+138h+phkResult]; phkResult
0x14008619f  call    ?Open@VmRegistryKey@Vml@@QEAAHPEAUHKEY__@@PEBGK@Z; Vml::VmRegistryKey::Open(HKEY__ *,ushort const *,ulong)
0x1400861a4  test    eax, eax
0x1400861a6  jz      loc_14008623D
0x1400861ac  mov     dword ptr [rsp+138h+var_68], edi
0x1400861b3  lea     r8, [rsp+138h+var_68]; unsigned int *
0x1400861bb  lea     rdx, aAllowspillingf; "AllowSpillingForHvDeposits"
0x1400861c2  lea     rcx, [rsp+138h+phkResult]; this
0x1400861ca  call    ?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAK@Z; Vml::VmRegistryKey::QueryValue(ushort const *,ulong &)
0x1400861cf  test    eax, eax
0x1400861d1  jz      short loc_1400861E1
0x1400861d3  cmp     dword ptr [rsp+138h+var_68], edi
0x1400861da  setnz   byte ptr cs:dword_1403C0668+1
0x1400861e1  lea     r8, [rsp+138h+var_68]; unsigned int *
0x1400861e9  lea     rdx, aUsesystemparti; "UseSystemPartitionForHvDeposits"
0x1400861f0  lea     rcx, [rsp+138h+phkResult]; this
0x1400861f8  call    ?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAK@Z; Vml::VmRegistryKey::QueryValue(ushort const *,ulong &)
0x1400861fd  test    eax, eax
0x1400861ff  jz      short loc_14008620F
0x140086201  cmp     dword ptr [rsp+138h+var_68], edi
0x140086208  setnz   byte ptr cs:dword_1403C0668+2
0x14008620f  lea     r8, [rsp+138h+var_68]; unsigned int *
0x140086217  lea     rdx, aUsesystemparti_0; "UseSystemPartitionForPhysicalBuffers"
0x14008621e  lea     rcx, [rsp+138h+phkResult]; this
0x140086226  call    ?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAK@Z; Vml::VmRegistryKey::QueryValue(ushort const *,ulong &)
0x14008622b  test    eax, eax
0x14008622d  jz      short loc_14008623D
0x14008622f  cmp     dword ptr [rsp+138h+var_68], edi
0x140086236  setnz   byte ptr cs:dword_1403C0668+3
0x14008623d  lea     rcx, [rsp+138h+phkResult]; this
0x140086245  call    ?Close@VmRegistryKey@Vml@@QEAAXXZ; Vml::VmRegistryKey::Close(void)
0x14008624a  nop
0x14008624b  jmp     short loc_140086266
0x14008624d  xor     edi, edi
0x14008624f  mov     r13, [rsp+138h+var_60]
0x140086257  mov     rsi, [rsp+138h+var_D8]
0x14008625c  mov     r15, [rsp+138h+var_C8]
0x140086261  mov     r12, [rsp+138h+var_E8]
0x140086266  xorps   xmm0, xmm0
0x140086269  movups  xmmword ptr [rsp+138h+var_E8], xmm0
0x14008626e  xor     r8d, r8d
0x140086271  mov     rdx, cs:qword_1403C0390
0x140086278  lea     rcx, [rsp+138h+var_E8]
0x14008627d  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x140086282  nop
0x140086283  mov     r9d, dword ptr [rsp+138h+var_E8+8]; char *
0x140086288  mov     rcx, [rsp+138h]; this
0x140086290  test    r9d, r9d
0x140086293  jns     short loc_1400862A7
0x140086295  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14008629c  mov     edx, 54Dh; void *
0x1400862a1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400862a7  mov     rcx, cs:qword_1403C0390
0x1400862ae  mov     rax, [rcx]
0x1400862b1  lea     rdx, dword_1403C03F0
0x1400862b8  mov     rax, [rax+120h]
0x1400862bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400862c4  mov     rcx, [rsp+138h]; this
0x1400862cc  test    eax, eax
0x1400862ce  jns     short loc_1400862E5
0x1400862d0  mov     r9d, eax; char *
0x1400862d3  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400862da  mov     edx, 552h; void *
0x1400862df  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400862e5  mov     rcx, cs:qword_1403C0390
0x1400862ec  mov     rax, [rcx]
0x1400862ef  lea     rdx, dword_1403C03F4
0x1400862f6  mov     rax, [rax+140h]
0x1400862fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086302  mov     rcx, [rsp+138h]; this
0x14008630a  test    eax, eax
0x14008630c  jns     short loc_140086323
0x14008630e  mov     r9d, eax; char *
0x140086311  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x140086318  mov     edx, 553h; void *
0x14008631d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140086323  mov     r14, rdi
0x140086326  cmp     [rsi+100h], dil
0x14008632d  jz      short loc_14008633D
0x14008632f  mov     byte ptr cs:qword_1403C05BC+4, 1
0x140086336  mov     r14, [rsi+108h]
0x14008633d  cmp     [rsi+138h], dil
0x140086344  jz      short loc_14008634D
0x140086346  mov     byte ptr cs:qword_1403C05BC+5, 1
0x14008634d  mov     rax, [rsp+138h+arg_28]
0x140086355  mov     ecx, [rax]
0x140086357  shr     ecx, 7
0x14008635a  and     cl, 1
0x14008635d  mov     byte ptr cs:qword_1403C05BC+7, cl
0x140086363  mov     rax, [rsi+28h]
0x140086367  mov     cs:qword_1403C03B0, rax
0x14008636e  mov     eax, 40000h
0x140086373  cmp     [rsi+0B8h], rax
0x14008637a  jnz     short loc_1400863DC
0x14008637c  cmp     cs:dword_1403C03F0, 803h
0x140086386  jnb     short loc_1400863E1
0x140086388  mov     ebx, 4020h
0x14008638d  mov     ecx, ebx
0x14008638f  call    VmlIsDebugTraceEnabled
0x140086394  test    eax, eax
0x140086396  jz      short loc_1400863A6
0x140086398  lea     rdx, aOnlyRs4OrAbove; "Only RS4 or above VMs support huge page"...
0x14008639f  mov     ecx, ebx
0x1400863a1  call    VmlDebugTrace
0x1400863a6  mov     rcx, [rsp+138h]; this
0x1400863ae  mov     eax, cs:dword_1403C03F0
0x1400863b4  mov     dword ptr [rsp+138h+var_110], eax; char *
0x1400863b8  lea     rax, aVmVersionXDoes_1; "VM version %x does not support huge pag"...
0x1400863bf  mov     qword ptr [rsp+138h+OutputBufferLength], rax; int
0x1400863c4  mov     r9d, 80048016h; char *
0x1400863ca  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400863d1  mov     edx, 574h; void *
0x1400863d6  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1400863dc  mov     eax, 200h
0x1400863e1  mov     cs:qword_1403C05E8, rax
0x1400863e8  mov     eax, cs:dword_1403C03F4
0x1400863ee  cmp     eax, 8
0x1400863f1  jz      short loc_1400863FC
0x1400863f3  cmp     eax, 1
0x1400863f6  jnz     loc_140086523
0x1400863fc  mov     [rsp+138h+phkResult], rdi
0x140086404  mov     rcx, cs:qword_1403C0390
0x14008640b  mov     rax, [rcx]
0x14008640e  lea     r8, [rsp+138h+phkResult]
0x140086416  lea     rdx, ?VIRTUAL_MACHINE_TOPOLOGY_DIRECT_FILE_MAPPING_XPATH@@3QBGB; "/configuration/settings/topology/direct"...
0x14008641d  mov     rax, [rax+78h]
0x140086421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086426  test    eax, eax
0x140086428  js      short loc_14008647D
0x14008642a  mov     rax, [rsp+138h+phkResult]
0x140086432  test    al, 1
0x140086434  jz      short loc_140086467
0x140086436  mov     rcx, [rsp+138h]; this
0x14008643e  mov     [rsp+138h+var_110], rax; char *
0x140086443  lea     rax, aDirectfilemapp; "directFileMappingMb = %I64u"
0x14008644a  mov     qword ptr [rsp+138h+OutputBufferLength], rax; int
0x14008644f  mov     r9d, 80070057h; char *
0x140086455  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14008645c  mov     edx, 58Ah; void *
0x140086461  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x140086467  mov     ebx, 10000h
0x14008646c  cmp     rax, rbx
0x14008646f  cmova   rax, rbx
0x140086473  mov     [rsp+138h+phkResult], rax
0x14008647b  jmp     short loc_140086482
0x14008647d  mov     ebx, 10000h
0x140086482  mov     [rsp+138h+var_68], rdi
0x14008648a  mov     rcx, cs:qword_1403C0390
0x140086491  mov     rax, [rcx]
0x140086494  lea     r8, [rsp+138h+var_68]
0x14008649c  lea     rdx, ?VIRTUAL_MACHINE_TOPOLOGY_SHARED_MEMORY_XPATH@@3QBGB; "/configuration/settings/topology/shared"...
0x1400864a3  mov     rax, [rax+78h]
0x1400864a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400864ac  mov     rdx, [rsp+138h+var_68]
0x1400864b4  test    eax, eax
0x1400864b6  js      short loc_1400864F5
0x1400864b8  test    dl, 1
0x1400864bb  jz      short loc_1400864EE
0x1400864bd  mov     rcx, [rsp+138h]; this
0x1400864c5  mov     [rsp+138h+var_110], rdx; char *
0x1400864ca  lea     rax, aSharedmemorymb; "sharedMemoryMb = %I64u"
0x1400864d1  mov     qword ptr [rsp+138h+OutputBufferLength], rax; int
0x1400864d6  mov     r9d, 80070057h; char *
0x1400864dc  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400864e3  mov     edx, 59Ch; void *
0x1400864e8  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1400864ee  cmp     rdx, rbx
0x1400864f1  cmova   rdx, rbx
0x1400864f5  mov     rax, [rsp+138h+phkResult]
0x1400864fd  shl     rax, 8
0x140086501  mov     cs:qword_1403C04E8, rax
0x140086508  shl     rdx, 8
0x14008650c  mov     cs:qword_1403C04F0, rdx
0x140086513  add     rax, rdx
0x140086516  mov     cs:qword_1403C04F8, rax
0x14008651d  mov     eax, cs:dword_1403C03F4
0x140086523  cmp     cs:dword_1403C03F0, 701h
0x14008652d  jb      short loc_14008653B
0x14008652f  cmp     eax, 1
0x140086532  jnz     short loc_14008653B
0x140086534  mov     cs:byte_1403C05B8, dil
0x14008653b  lea     rcx, [rsp+138h+var_E8]; this
0x140086540  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140086545  lea     rcx, [rsp+138h+var_E8]
0x14008654a  call    ??$make_unique@VGpaSpaceBestFitAllocator@@AEB_K$0A@@std@@YA?AV?$unique_ptr@VGpaSpaceBestFitAllocator@@U?$default_delete@VGpaSpaceBestFitAllocator@@@std@@@0@AEB_K@Z; std::make_unique<GpaSpaceBestFitAllocator,unsigned __int64 const &,0>(unsigned __int64 const &)
0x14008654f  mov     rcx, [rax]
0x140086552  mov     [rax], rdi
0x140086555  mov     rdx, cs:qword_1403C0528
0x14008655c  mov     cs:qword_1403C0528, rcx
0x140086563  test    rdx, rdx
0x140086566  jz      short loc_14008656D
0x140086568  call    ??R?$default_delete@VGpaSpaceBestFitAllocator@@@std@@QEBAXPEAVGpaSpaceBestFitAllocator@@@Z; std::default_delete<GpaSpaceBestFitAllocator>::operator()(GpaSpaceBestFitAllocator *)
0x14008656d  lea     rcx, [rsp+138h+var_E8]
0x140086572  call    ??1?$unique_ptr@VGpaSpaceBestFitAllocator@@U?$default_delete@VGpaSpaceBestFitAllocator@@@std@@@std@@QEAA@XZ; std::unique_ptr<GpaSpaceBestFitAllocator>::~unique_ptr<GpaSpaceBestFitAllocator>(void)
0x140086577  mov     ecx, 48h ; 'H'; Size
0x14008657c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140086581  mov     [rsp+138h+var_E8], rax
0x140086586  xorps   xmm0, xmm0
0x140086589  movups  xmmword ptr [rax], xmm0
0x14008658c  mov     dword ptr [rax+8], 1
0x140086593  mov     dword ptr [rax+0Ch], 1
0x14008659a  lea     rcx, ??_7?$_Ref_count_obj2@VRamUsage@@@std@@6B@; const std::_Ref_count_obj2<RamUsage>::`vftable'
0x1400865a1  mov     [rax], rcx
0x1400865a4  lea     rcx, [rax+10h]
0x1400865a8  mov     [rcx+8], rdi
  ... truncated ...
```
