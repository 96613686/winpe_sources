# ComputeService::Management::Details::InitializeLiveMigration(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::ActiveStateOperation &,Schema::Options::MigrationOrigin,Schema::Options::MigrationInitializeOptions)

- ea: `0x14011ef68`
- end: `0x14011f722`
- name: `?InitializeLiveMigration@Details@Management@ComputeService@@YAXAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@AEAVActiveStateOperation@23@W4MigrationOrigin@Options@Schema@@UMigrationInitializeOptions@89@@Z`
- size: `1978`
- prototype: ``
- caller_count: `2`
- callee_count: `47`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14011ea00`
- `0x1401cdb60`

## callees

- `0x140017040`
- `0x140020890`
- `0x140024030`
- `0x140026a80`
- `0x140027e64`
- `0x14002f9e8`
- `0x140042468`
- `0x1400451a0`
- `0x14004ec00`
- `0x140061680`
- `0x14007747c`
- `0x14007eb7c`
- `0x14007ed7c`
- `0x14007edc4`
- `0x14007ef00`
- `0x14007efd4`
- `0x14007f03c`
- `0x140080180`
- `0x140087500`
- `0x140092d38`
- `0x14009c7dc`
- `0x14009d75c`
- `0x1400ba760`
- `0x1400c40e0`
- `0x1400c7bb4`
- `0x1400ca10c`
- `0x1400cdfd4`
- `0x140106a68`
- `0x140106acc`
- `0x140109e40`
- `0x14011ef68`
- `0x1401332f0`
- `0x140133314`
- `0x1401336bc`
- `0x140134048`
- `0x14019b8c8`
- `0x1401b0e7c`
- `0x1401b19d8`
- `0x1401b20bc`
- `0x1401bc630`
- `0x1401c99c4`
- `0x1401c9a7c`
- `0x1401c9af4`
- `0x1401cb5f4`
- `0x1401d38d8`
- `0x1401da998`
- `0x1402a0e5c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14011f1a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14011f1b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14011f1bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14011f1a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14011f1b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14011f1bf`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14011f1ef`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14011f1ef`

## string_xrefs

- `0x14011f620`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x14011f673`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x14011f6b5`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x14011f6fb`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x14011f710`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x14011f638`: `onecore\vm\compute\management\computesystem\computesystem.h`
- `0x14011f60b`: `onecore\vm\compute\management\orchestration\virtualmachine\VirtualMachineConfiguration.h`
- `0x14011f019`: `LiveMigrationSourceInitializeTask`
- `0x14011f027`: `LiveMigrationDestinationInitializeTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall ComputeService::Management::Details::InitializeLiveMigration(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  int v8; // r12d
  __int64 v9; // rax
  __int64 v10; // r15
  __int64 v11; // r13
  __int64 v12; // rdx
  const wchar_t *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // r9
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rcx
  int v22; // eax
  HANDLE *v23; // rsi
  HANDLE CurrentProcess; // rdi
  HANDLE v25; // rbx
  HANDLE v26; // rax
  int v27; // r8d
  const char *v28; // r9
  const wchar_t *v29; // rax
  int v30; // ecx
  int v31; // r8d
  int v32; // eax
  _QWORD *v33; // rax
  const char *v34; // r9
  void *v35; // rbx
  int *v36; // rax
  void *v37; // rcx
  int v39; // eax
  __int64 v40; // rax
  __int64 v41; // rbx
  unsigned int v42; // eax
  __int64 v43; // rax
  unsigned int v44; // eax
  __int64 v45; // rdx
  int dwDesiredAccess; // [rsp+20h] [rbp-E0h]
  int dwDesiredAccessa; // [rsp+20h] [rbp-E0h]
  char v48; // [rsp+40h] [rbp-C0h]
  int v49; // [rsp+44h] [rbp-BCh] BYREF
  char v50[8]; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v51; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v52; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v53[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v54[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v55; // [rsp+80h] [rbp-80h]
  _QWORD v56[3]; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v57; // [rsp+B0h] [rbp-50h]
  _QWORD *v58; // [rsp+D0h] [rbp-30h]
  int *v59; // [rsp+D8h] [rbp-28h]
  _QWORD v60[2]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v61[16]; // [rsp+F0h] [rbp-10h] BYREF
  char v62[16]; // [rsp+100h] [rbp+0h] BYREF
  __int16 v63; // [rsp+110h] [rbp+10h]
  int v64; // [rsp+112h] [rbp+12h]
  __int16 v65; // [rsp+116h] [rbp+16h]
  __int16 v66; // [rsp+118h] [rbp+18h] BYREF
  int v67; // [rsp+11Ah] [rbp+1Ah]
  __int16 v68; // [rsp+11Eh] [rbp+1Eh]
  __int128 v69; // [rsp+120h] [rbp+20h]
  int v70; // [rsp+130h] [rbp+30h]
  __int64 v71; // [rsp+134h] [rbp+34h]
  __int64 v72; // [rsp+13Ch] [rbp+3Ch]
  __int64 v73; // [rsp+144h] [rbp+44h]
  __int64 v74; // [rsp+14Ch] [rbp+4Ch]
  __int64 v75; // [rsp+154h] [rbp+54h]
  int v76; // [rsp+15Ch] [rbp+5Ch]
  char v77; // [rsp+160h] [rbp+60h]
  __int16 v78; // [rsp+168h] [rbp+68h]
  int v79; // [rsp+16Ah] [rbp+6Ah]
  __int16 v80; // [rsp+16Eh] [rbp+6Eh]
  __int128 v81; // [rsp+170h] [rbp+70h]
  __int128 v82; // [rsp+180h] [rbp+80h]
  __int16 v83; // [rsp+190h] [rbp+90h]
  __int64 v84; // [rsp+192h] [rbp+92h]
  __int16 v85; // [rsp+19Ah] [rbp+9Ah]
  __int64 v86; // [rsp+19Ch] [rbp+9Ch]
  __int64 v87; // [rsp+1A4h] [rbp+A4h]
  __int64 v88; // [rsp+1ACh] [rbp+ACh]
  __int64 v89; // [rsp+1B4h] [rbp+B4h]
  int v90; // [rsp+1BCh] [rbp+BCh]
  char v91; // [rsp+1C0h] [rbp+C0h]
  __int16 v92; // [rsp+1C1h] [rbp+C1h]
  char v93; // [rsp+1C3h] [rbp+C3h]
  __int64 v94; // [rsp+1C4h] [rbp+C4h]
  int v95; // [rsp+1CCh] [rbp+CCh]
  _BYTE v96[80]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v97[72]; // [rsp+220h] [rbp+120h] BYREF
  __int128 v98; // [rsp+268h] [rbp+168h]
  __int128 v99; // [rsp+278h] [rbp+178h]
  __int128 v100; // [rsp+290h] [rbp+190h] BYREF
  __int64 v101; // [rsp+2A0h] [rbp+1A0h]
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v59 = (int *)a4;
  v8 = 0;
  v9 = _RTDynamicCast_0(
         *(_QWORD *)(*(_QWORD *)a1 + 8LL),
         0,
         &ComputeService::Management::ComputeSystemState `RTTI Type Descriptor',
         &ComputeService::Management::VirtualMachineState `RTTI Type Descriptor');
  v10 = v9;
  if ( !v9 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\computesystem.h",
      (const char *)0x80004001LL,
      0);
  v11 = v9 + 624;
  if ( (unsigned __int8)ComputeService::Management::Details::HasAssignedDevices(v9 + 624, 0) )
  {
    v40 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,long (*)(_SECURITY_CAPABILITIES *),&long FreeWorkerProcessCapabilities(_SECURITY_CAPABILITIES *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>>::get(a1);
    v41 = ComputeService::Management::ComputeSystem::GetConfigurationAs<ComputeService::Management::VirtualMachineConfiguration>(v40);
    v42 = wil::verify_BOOL<int>(2147942450LL);
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x5FE,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
      (const char *)v42,
      0);
    v43 = std::wstring::c_str(v41 + 8);
    ComputeService::Reporting::LogAndThrowComputeSystemError<>(v43, 2147942450LL, MSVCOMP_VM_HAS_ASSIGNED_DEVICE_FAILED);
  }
  LOBYTE(v12) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_GpupLiveMigration>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_GpupLiveMigration>::GetImpl'::`2'::impl,
    v12);
  v52 = 0;
  v50[0] = 1;
  if ( a3 )
  {
    v48 = 0;
    v13 = L"LiveMigrationDestinationInitializeTask";
  }
  else
  {
    v48 = 1;
    v13 = L"LiveMigrationSourceInitializeTask";
  }
  v51 = v13;
  v14 = Vml::VmComMultiInstanceObject<ComputeService::Vmwp::Task>::CreateInstance<bool const &,_GUID &,unsigned short const *>(
          v50,
          v11,
          &v51);
  Vml::VmComPtr<IStream>::Attach<Vml::VmComFixedMemStream>(&v52, v14);
  v101 = 0;
  v100 = 0;
  v15 = Vml::VmComPtr<IVmSimpleTask>::VmComPtr<IVmSimpleTask>(&v51, &v52);
  v17 = std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>(
          v54,
          a1,
          v15,
          v16);
  ComputeService::Management::Details::RegisterTaskForNotifications(v17, a2, v18, &v100);
  Vml::VmComPtr<IVmSimpleTask>::VmComPtr<IVmSimpleTask>(v54, &v52);
  v54[1] = v10;
  v55 = a3;
  v56[0] = &std::_Func_impl_no_alloc<_lambda_6768a48c2b1e4a1c1572b628bb22dbb5_,std::optional<ComputeService::Management::OperationResult>,std::shared_ptr<ComputeService::Management::OperationResult>>::`vftable';
  v19 = v54[0];
  v54[0] = 0;
  v56[1] = v19;
  v56[2] = v10;
  v57 = a3;
  v58 = v56;
  ComputeService::Management::ActiveStateOperation::RegisterCancellationCallback(a2, v56);
  Vml::VmComPtr<IVmSimpleTaskEvents>::~VmComPtr<IVmSimpleTaskEvents>(v54);
  v20 = Vml::VmComPtr<IVmSimpleTask>::VmComPtr<IVmSimpleTask>(&v51, &v52);
  ComputeService::Management::Details::AddTaskToServerOperation(v53, a2, v20);
  v22 = 2592;
  v49 = 2592;
  if ( *(_BYTE *)(a4 + 100) )
  {
    v22 = 2593;
    v49 = 2593;
  }
  if ( *(_BYTE *)(a4 + 101) )
  {
    v22 |= 2u;
    v49 = v22;
  }
  if ( *(_BYTE *)(a4 + 102) )
  {
    v22 |= 0x40u;
    v49 = v22;
  }
  if ( *(_BYTE *)(a4 + 96) )
  {
    v49 = v22 | 4;
    if ( !*(_BYTE *)(a4 + 96) )
      __fastfail(5u);
    LOBYTE(v21) = *(_BYTE *)(a4 + 92);
    if ( (_BYTE)v21 && !*(_DWORD *)(a4 + 88) )
    {
      v44 = wil::verify_BOOL<int>(2151088397LL);
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x63B,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
        (const char *)v44,
        0);
      v49 = 5;
      std::pair<std::wstring,enum Marshal::UnmarshalError>::pair<std::wstring,enum Marshal::UnmarshalError>(
        v54,
        v45,
        &v49);
      ComputeService::Reporting::FormatUnMarshalError(v56, v54);
      ComputeService::Reporting::LogAndThrowComputeError<std::wstring>(-2143878899);
    }
    LODWORD(v60[0]) = *(_DWORD *)(a4 + 88);
    BYTE4(v60[0]) = v21;
    LOBYTE(v21) = 1;
    v8 = ComputeService::Management::MigrationUtils::InitializeCompressionWorkerCount(v21, v60, a3);
  }
  else
  {
    LOBYTE(v8) = a3 != 0;
  }
  v60[0] = 0;
  v23 = (HANDLE *)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(v60);
  CurrentProcess = GetCurrentProcess();
  v25 = GetCurrentProcess();
  v26 = GetCurrentProcess();
  if ( !DuplicateHandle(v26, v25, CurrentProcess, v23, 0x100000u, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x64C,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
      v28);
  if ( v48 )
  {
    std::map<unsigned __int64,Config::Devices::Manifest::DeviceEntry>::map<unsigned __int64,Config::Devices::Manifest::DeviceEntry>(v61);
    std::map<_GUID,Migration::Parameters::Worker::MigrationTransferThrottleParams,Marshal::GuidLess,std::allocator<std::pair<_GUID const,Migration::Parameters::Worker::MigrationTransferThrottleParams>>>::map<_GUID,Migration::Parameters::Worker::MigrationTransferThrottleParams,Marshal::GuidLess,std::allocator<std::pair<_GUID const,Migration::Parameters::Worker::MigrationTransferThrottleParams>>>(v62);
    v63 = 0;
    v64 = 0;
    v65 = 0;
    memset_0(&v66, 0, 0x50u);
    v66 = 0;
    v67 = 0;
    v68 = 0;
    v69 = 0;
    BYTE8(v69) = 0;
    v70 = 0;
    v71 = 0;
    v72 = 0;
    v73 = 0;
    v74 = 0;
    v75 = 0;
    v76 = 0;
    v77 = 0;
    v78 = 0;
    v79 = 0;
    v80 = 0;
    v81 = 0u;
    v82 = 0u;
    v83 = 0;
    v84 = 0;
    v85 = 0;
    v90 = 0;
    v86 = 0;
    v87 = 0;
    v88 = 0;
    v89 = 0;
    v94 = 0;
    v91 = 0;
    v92 = 0;
    v93 = 0;
    v95 = 0;
    memset_0(v96, 0, sizeof(v96));
    vmstd::optional<Migration::Parameters::Worker::MigrationTdxParams>::optional<Migration::Parameters::Worker::MigrationTdxParams>(v96);
    memset_0(v97, 0, sizeof(v97));
    vmstd::optional<Migration::Parameters::Worker::MigrationClassOfServiceParams>::optional<Migration::Parameters::Worker::MigrationClassOfServiceParams>(v97);
    v98 = 0u;
    v99 = 0u;
    if ( *(_BYTE *)(a4 + 80) )
    {
      Schema::Options::MemoryMigrationTransferThrottleParams::operator=(&v66);
      v77 = 1;
    }
    v29 = (const wchar_t *)Marshal::ToJson<Migration::Parameters::Worker::MigrationSourceInit &,>(v56, v61);
    if ( *((_QWORD *)v29 + 3) > 7u )
      v29 = *(const wchar_t **)v29;
    v51 = v29;
    v54[0] = v60[0];
    v53[0] = v52;
    v32 = ___InvokeWorkerProcessMethod_UIVmVirtualMachine__PEAUIVmSimpleTask__IPEAXPEBG__ZPEAU2_AEAIPEAXPEBG_Vmwp_ComputeService__YAJAEBUWorkerProcessContext_01_PEAUIUnknown__P8IVmVirtualMachine__EAAJPEAUIVmSimpleTask__IPEAXPEBG_Z__QEAPEAU5_AEAI__QEAPEAX__QEAPEBG_Z(
            v30,
            *(_QWORD *)(v11 + 16),
            v31,
            (unsigned int)v53,
            (__int64)&v49,
            (__int64)v54,
            (__int64)&v51);
    if ( v32 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x65D,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
        (const char *)(unsigned int)v32,
        dwDesiredAccess);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v56);
    Migration::Parameters::Worker::MigrationSourceInit::~MigrationSourceInit((Migration::Parameters::Worker::MigrationSourceInit *)v61);
  }
  else
  {
    v53[0] = 0;
    v54[0] = v60[0];
    v51 = v52;
    v39 = ___InvokeWorkerProcessMethod_UIVmVirtualMachine__PEAUIVmSimpleTask__IPEAXPEBG__ZPEAU2_AEAIPEAX__T_Vmwp_ComputeService__YAJAEBUWorkerProcessContext_01_PEAUIUnknown__P8IVmVirtualMachine__EAAJPEAUIVmSimpleTask__IPEAXPEBG_Z__QEAPEAU5_AEAI__QEAPEAX__QEA__T_Z(
            (_DWORD)retaddr,
            *(_QWORD *)(v11 + 16),
            v27,
            (unsigned int)&v51,
            (__int64)&v49,
            (__int64)v54,
            (__int64)v53);
    if ( v39 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x667,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
        (const char *)(unsigned int)v39,
        dwDesiredAccessa);
  }
  v51 = 0;
  wil::AcquireSRWLockExclusive(&v51, v10 + 2720);
  v33 = (_QWORD *)Vml::VmComPtr<IVmSimpleTask>::VmComPtr<IVmSimpleTask>(v53, &v52);
  v35 = v33;
  if ( !*v33 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\VirtualMachineConfiguration.h",
      v34);
  *v33 = 0;
  Vml::VmComPtr<IVmSimpleTask>::Attach<IVmSimpleTask>(v10 + 2728);
  Vml::VmComPtr<IVmSimpleTaskEvents>::~VmComPtr<IVmSimpleTaskEvents>(v35);
  v36 = (int *)operator new(8u);
  v59 = v36;
  *v36 = v49;
  v36[1] = v8;
  v53[0] = 0;
  v37 = *(void **)(v10 + 2760);
  *(_QWORD *)(v10 + 2760) = v36;
  if ( v37 )
    operator delete(v37, (const struct std::nothrow_t *)8);
  std::unique_ptr<ComputeService::Management::MigrationOptions>::~unique_ptr<ComputeService::Management::MigrationOptions>(v53);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v51);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v60);
  ComputeService::Vmwp::ComTaskEventRAII<IVmSimpleTask,ComputeService::Management::WorkerProcessTaskEventSink>::~ComTaskEventRAII<IVmSimpleTask,ComputeService::Management::WorkerProcessTaskEventSink>(&v100);
  Vml::VmComPtr<IVmSimpleTaskEvents>::~VmComPtr<IVmSimpleTaskEvents>(&v52);
  return std::vector<unsigned char>::_Tidy(a4 + 104);
}

```

## disassembly

```asm
0x14011ef68  mov     [rsp-8+arg_10], rbx
0x14011ef6d  push    rbp
0x14011ef6e  push    rsi
0x14011ef6f  push    rdi
0x14011ef70  push    r12
0x14011ef72  push    r13
0x14011ef74  push    r14
0x14011ef76  push    r15
0x14011ef78  lea     rbp, [rsp-1B0h]
0x14011ef80  sub     rsp, 2B0h
0x14011ef87  mov     rax, cs:__security_cookie
0x14011ef8e  xor     rax, rsp
0x14011ef91  mov     [rbp+1E0h+var_38], rax
0x14011ef98  mov     r14, r9
0x14011ef9b  mov     ebx, r8d
0x14011ef9e  mov     rsi, rdx
0x14011efa1  mov     rdi, rcx
0x14011efa4  mov     [rbp+1E0h+var_208], r9
0x14011efa8  xor     r12d, r12d
0x14011efab  mov     rcx, [rcx]
0x14011efae  mov     [rsp+2E0h+dwDesiredAccess], r12d; int
0x14011efb3  lea     r9, ??_R0?AUVirtualMachineState@Management@ComputeService@@@8; ComputeService::Management::VirtualMachineState `RTTI Type Descriptor'
0x14011efba  lea     r8, ??_R0?AUComputeSystemState@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemState `RTTI Type Descriptor'
0x14011efc1  xor     edx, edx
0x14011efc3  mov     rcx, [rcx+8]
0x14011efc7  call    __RTDynamicCast_0
0x14011efcc  mov     r15, rax
0x14011efcf  mov     rcx, [rbp+1E8h]; this
0x14011efd6  test    rax, rax
0x14011efd9  jz      loc_14011F632
0x14011efdf  lea     r13, [rax+270h]
0x14011efe6  xor     edx, edx
0x14011efe8  mov     rcx, r13
0x14011efeb  call    ?HasAssignedDevices@Details@Management@ComputeService@@YA_NAEAUWorkerProcessContext@Vmwp@3@W4AssignedDeviceType@123@@Z; ComputeService::Management::Details::HasAssignedDevices(ComputeService::Vmwp::WorkerProcessContext &,ComputeService::Management::Details::AssignedDeviceType)
0x14011eff0  test    al, al
0x14011eff2  jnz     loc_14011F64A
0x14011eff8  mov     dl, 1
0x14011effa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GpupLiveMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GpupLiveMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GpupLiveMigration> `wil::Feature<__WilFeatureTraits_Feature_GpupLiveMigration>::GetImpl(void)'::`2'::impl
0x14011f001  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GpupLiveMigration@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GpupLiveMigration>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14011f006  mov     [rsp+2E0h+var_288], r12
0x14011f00b  mov     [rsp+2E0h+var_298], 1
0x14011f010  test    ebx, ebx
0x14011f012  jnz     short loc_14011F022
0x14011f014  mov     [rsp+2E0h+var_2A0], 1
0x14011f019  lea     rax, aLivemigrations_0; "LiveMigrationSourceInitializeTask"
0x14011f020  jmp     short loc_14011F02E
0x14011f022  mov     [rsp+2E0h+var_2A0], r12b
0x14011f027  lea     rax, aLivemigrationd; "LiveMigrationDestinationInitializeTask"
0x14011f02e  mov     [rsp+2E0h+var_290], rax
0x14011f033  lea     r8, [rsp+2E0h+var_290]
0x14011f038  mov     rdx, r13
0x14011f03b  lea     rcx, [rsp+2E0h+var_298]
0x14011f040  call    ??$CreateInstance@AEB_NAEAU_GUID@@PEBG@?$VmComMultiInstanceObject@VTask@Vmwp@ComputeService@@@Vml@@SAPEAVTask@Vmwp@ComputeService@@AEB_NAEAU_GUID@@$$QEAPEBG@Z; Vml::VmComMultiInstanceObject<ComputeService::Vmwp::Task>::CreateInstance<bool const &,_GUID &,ushort const *>(bool const &,_GUID &,ushort const * &&)
0x14011f045  mov     rdx, rax
0x14011f048  lea     rcx, [rsp+2E0h+var_288]
0x14011f04d  call    ??$Attach@VVmComFixedMemStream@Vml@@@?$VmComPtr@UIStream@@@Vml@@QEAAXPEAVVmComFixedMemStream@1@@Z; Vml::VmComPtr<IStream>::Attach<Vml::VmComFixedMemStream>(Vml::VmComFixedMemStream *)
0x14011f052  xor     eax, eax
0x14011f054  mov     [rbp+1E0h+var_40], rax
0x14011f05b  xorps   xmm1, xmm1
0x14011f05e  movdqu  [rbp+1E0h+var_50], xmm1
0x14011f066  lea     rdx, [rsp+2E0h+var_288]
0x14011f06b  lea     rcx, [rsp+2E0h+var_290]
0x14011f070  call    ??0?$VmComPtr@UIVmSimpleTask@@@Vml@@QEAA@AEBV01@@Z; Vml::VmComPtr<IVmSimpleTask>::VmComPtr<IVmSimpleTask>(Vml::VmComPtr<IVmSimpleTask> const &)
0x14011f075  mov     r8, rax
0x14011f078  mov     rdx, rdi
0x14011f07b  lea     rcx, [rsp+2E0h+var_270]
0x14011f080  call    ??0?$shared_ptr@VINetworkResourceAllocator@Resource@ComputeService@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>(std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator> const &)
0x14011f085  lea     r9, [rbp+1E0h+var_50]
0x14011f08c  mov     rdx, rsi
0x14011f08f  mov     rcx, rax
0x14011f092  call    ?RegisterTaskForNotifications@Details@Management@ComputeService@@YAXV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@AEAVActiveStateOperation@23@V?$VmComPtr@UIVmSimpleTask@@@Vml@@AEAV?$ComTaskEventRAII@UIVmSimpleTask@@VWorkerProcessTaskEventSink@Management@ComputeService@@@Vmwp@3@@Z; ComputeService::Management::Details::RegisterTaskForNotifications(std::shared_ptr<ComputeService::Management::ComputeSystem>,ComputeService::Management::ActiveStateOperation &,Vml::VmComPtr<IVmSimpleTask>,ComputeService::Vmwp::ComTaskEventRAII<IVmSimpleTask,ComputeService::Management::WorkerProcessTaskEventSink> &)
0x14011f097  lea     rdx, [rsp+2E0h+var_288]
0x14011f09c  lea     rcx, [rsp+2E0h+var_270]
0x14011f0a1  call    ??0?$VmComPtr@UIVmSimpleTask@@@Vml@@QEAA@AEBV01@@Z; Vml::VmComPtr<IVmSimpleTask>::VmComPtr<IVmSimpleTask>(Vml::VmComPtr<IVmSimpleTask> const &)
0x14011f0a6  mov     [rsp+2E0h+var_268], r15
0x14011f0ab  mov     [rbp+1E0h+var_260], ebx
0x14011f0ae  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_6768a48c2b1e4a1c1572b628bb22dbb5_@@V?$optional@UOperationResult@Management@ComputeService@@@std@@V?$shared_ptr@UOperationResult@Management@ComputeService@@@3@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_6768a48c2b1e4a1c1572b628bb22dbb5_,std::optional<ComputeService::Management::OperationResult>,std::shared_ptr<ComputeService::Management::OperationResult>>::`vftable'
0x14011f0b5  mov     [rbp+1E0h+var_248], rax
0x14011f0b9  mov     rax, [rsp+2E0h+var_270]
0x14011f0be  mov     [rsp+2E0h+var_270], r12
0x14011f0c3  mov     [rbp+1E0h+var_240], rax
0x14011f0c7  mov     [rbp+1E0h+var_238], r15
0x14011f0cb  mov     [rbp+1E0h+var_230], ebx
0x14011f0ce  lea     rax, [rbp+1E0h+var_248]
0x14011f0d2  mov     [rbp+1E0h+var_210], rax
0x14011f0d6  lea     rdx, [rbp+1E0h+var_248]
0x14011f0da  mov     rcx, rsi
0x14011f0dd  call    ?RegisterCancellationCallback@ActiveStateOperation@Management@ComputeService@@QEAAXV?$function@$$A6A?AV?$optional@UOperationResult@Management@ComputeService@@@std@@V?$shared_ptr@UOperationResult@Management@ComputeService@@@2@@Z@std@@@Z; ComputeService::Management::ActiveStateOperation::RegisterCancellationCallback(std::function<std::optional<ComputeService::Management::OperationResult> (std::shared_ptr<ComputeService::Management::OperationResult>)>)
0x14011f0e2  nop
0x14011f0e3  lea     rcx, [rsp+2E0h+var_270]; void *
0x14011f0e8  call    ??1?$VmComPtr@UIVmSimpleTaskEvents@@@Vml@@QEAA@XZ; Vml::VmComPtr<IVmSimpleTaskEvents>::~VmComPtr<IVmSimpleTaskEvents>(void)
0x14011f0ed  lea     rdx, [rsp+2E0h+var_288]
0x14011f0f2  lea     rcx, [rsp+2E0h+var_290]
0x14011f0f7  call    ??0?$VmComPtr@UIVmSimpleTask@@@Vml@@QEAA@AEBV01@@Z; Vml::VmComPtr<IVmSimpleTask>::VmComPtr<IVmSimpleTask>(Vml::VmComPtr<IVmSimpleTask> const &)
0x14011f0fc  mov     r8, rax
0x14011f0ff  mov     rdx, rsi
0x14011f102  lea     rcx, [rsp+2E0h+var_280]
0x14011f107  call    ?AddTaskToServerOperation@Details@Management@ComputeService@@YA?AU_GUID@@AEAVActiveStateOperation@23@V?$VmComPtr@UIVmSimpleTask@@@Vml@@@Z; ComputeService::Management::Details::AddTaskToServerOperation(ComputeService::Management::ActiveStateOperation &,Vml::VmComPtr<IVmSimpleTask>)
0x14011f10c  mov     eax, 0A20h
0x14011f111  mov     [rsp+2E0h+var_29C], eax
0x14011f115  cmp     [r14+64h], r12b
0x14011f119  jz      short loc_14011F124
0x14011f11b  mov     eax, 0A21h
0x14011f120  mov     [rsp+2E0h+var_29C], eax
0x14011f124  cmp     [r14+65h], r12b
0x14011f128  jz      short loc_14011F131
0x14011f12a  or      eax, 2
0x14011f12d  mov     [rsp+2E0h+var_29C], eax
0x14011f131  cmp     [r14+66h], r12b
0x14011f135  jz      short loc_14011F13E
0x14011f137  or      eax, 40h
0x14011f13a  mov     [rsp+2E0h+var_29C], eax
0x14011f13e  mov     edi, 5
0x14011f143  cmp     [r14+60h], r12b
0x14011f147  jz      short loc_14011F187
0x14011f149  or      eax, 4
0x14011f14c  mov     [rsp+2E0h+var_29C], eax
0x14011f150  cmp     [r14+60h], r12b
0x14011f154  jnz     short loc_14011F15A
0x14011f156  mov     ecx, edi
0x14011f158  int     29h; Win8: RtlFailFast(ecx)
0x14011f15a  mov     eax, [r14+58h]
0x14011f15e  mov     cl, [r14+5Ch]
0x14011f162  test    cl, cl
0x14011f164  jz      short loc_14011F16E
0x14011f166  test    eax, eax
0x14011f168  jz      loc_14011F69F
0x14011f16e  mov     dword ptr [rbp+1E0h+var_200], eax
0x14011f171  mov     byte ptr [rbp+1E0h+var_200+4], cl
0x14011f174  mov     r8d, ebx
0x14011f177  lea     rdx, [rbp+1E0h+var_200]
0x14011f17b  mov     cl, 1
0x14011f17d  call    ?InitializeCompressionWorkerCount@MigrationUtils@Management@ComputeService@@YAI_NU?$optional@I@vmstd@@W4MigrationOrigin@Options@Schema@@@Z; ComputeService::Management::MigrationUtils::InitializeCompressionWorkerCount(bool,vmstd::optional<uint>,Schema::Options::MigrationOrigin)
0x14011f182  mov     r12d, eax
0x14011f185  jmp     short loc_14011F18D
0x14011f187  test    ebx, ebx
0x14011f189  setnz   r12b
0x14011f18d  mov     [rbp+1E0h+var_200], 0
0x14011f195  lea     rcx, [rbp+1E0h+var_200]
0x14011f199  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x14011f19e  mov     rsi, rax
0x14011f1a1  call    cs:__imp_GetCurrentProcess
0x14011f1a8  nop     dword ptr [rax+rax+00h]
0x14011f1ad  mov     rdi, rax
0x14011f1b0  call    cs:__imp_GetCurrentProcess
0x14011f1b7  nop     dword ptr [rax+rax+00h]
0x14011f1bc  mov     rbx, rax
0x14011f1bf  call    cs:__imp_GetCurrentProcess
0x14011f1c6  nop     dword ptr [rax+rax+00h]
0x14011f1cb  mov     [rsp+2E0h+dwOptions], 0; dwOptions
0x14011f1d3  mov     [rsp+2E0h+bInheritHandle], 0; bInheritHandle
0x14011f1db  mov     [rsp+2E0h+dwDesiredAccess], 100000h; dwDesiredAccess
0x14011f1e3  mov     r9, rsi; lpTargetHandle
0x14011f1e6  mov     r8, rdi; hTargetProcessHandle
0x14011f1e9  mov     rdx, rbx; hSourceHandle
0x14011f1ec  mov     rcx, rax; hSourceProcessHandle
0x14011f1ef  call    cs:__imp_DuplicateHandle
0x14011f1f6  nop     dword ptr [rax+rax+00h]
0x14011f1fb  mov     rcx, [rbp+1E8h]; this
0x14011f202  xor     edi, edi
0x14011f204  test    eax, eax
0x14011f206  jz      loc_14011F6FB
0x14011f20c  cmp     [rsp+2E0h+var_2A0], dil
0x14011f211  jz      loc_14011F5B7
0x14011f217  lea     rcx, [rbp+1E0h+var_1F0]
0x14011f21b  call    ??0?$map@_KUDeviceEntry@Manifest@Devices@Config@@U?$less@X@std@@V?$allocator@U?$pair@$$CB_KUDeviceEntry@Manifest@Devices@Config@@@std@@@6@@std@@QEAA@XZ; std::map<unsigned __int64,Config::Devices::Manifest::DeviceEntry>::map<unsigned __int64,Config::Devices::Manifest::DeviceEntry>(void)
0x14011f220  nop
0x14011f221  lea     rcx, [rbp+1E0h+var_1E0]
0x14011f225  call    ??0?$map@U_GUID@@UMigrationTransferThrottleParams@Worker@Parameters@Migration@@UGuidLess@Marshal@@V?$allocator@U?$pair@$$CBU_GUID@@UMigrationTransferThrottleParams@Worker@Parameters@Migration@@@std@@@std@@@std@@QEAA@XZ; std::map<_GUID,Migration::Parameters::Worker::MigrationTransferThrottleParams,Marshal::GuidLess,std::allocator<std::pair<_GUID const,Migration::Parameters::Worker::MigrationTransferThrottleParams>>>::map<_GUID,Migration::Parameters::Worker::MigrationTransferThrottleParams,Marshal::GuidLess,std::allocator<std::pair<_GUID const,Migration::Parameters::Worker::MigrationTransferThrottleParams>>>(void)
0x14011f22a  xor     eax, eax
0x14011f22c  mov     [rbp+1E0h+var_1D0], di
0x14011f230  mov     [rbp+1E0h+var_1CE], eax
0x14011f233  mov     [rbp+1E0h+var_1CA], ax
0x14011f237  lea     ebx, [rdi+50h]
0x14011f23a  mov     r8d, ebx; Size
0x14011f23d  xor     edx, edx; Val
0x14011f23f  lea     rcx, [rbp+1E0h+var_1C8]; void *
0x14011f243  call    memset_0
0x14011f248  mov     [rbp+1E0h+var_1C8], di
0x14011f24c  xor     eax, eax
0x14011f24e  mov     [rbp+1E0h+var_1C6], eax
0x14011f251  mov     [rbp+1E0h+var_1C2], ax
0x14011f255  xorps   xmm0, xmm0
0x14011f258  movups  [rbp+1E0h+var_1C0], xmm0
0x14011f25c  xorps   xmm1, xmm1
0x14011f25f  movsd   qword ptr [rbp+1E0h+var_1C0], xmm1
0x14011f264  mov     byte ptr [rbp+1E0h+var_1C0+8], dil
0x14011f268  mov     [rbp+1E0h+var_1B0], eax
0x14011f26b  mov     word ptr [rbp+1E0h+var_1B0], di
0x14011f26f  mov     [rbp+1E0h+var_1AC], rax
0x14011f273  mov     dword ptr [rbp+1E0h+var_1AC], edi
0x14011f276  mov     byte ptr [rbp+1E0h+var_1AC+4], dil
0x14011f27a  mov     [rbp+1E0h+var_1A4], rax
0x14011f27e  mov     dword ptr [rbp+1E0h+var_1A4], edi
0x14011f281  mov     byte ptr [rbp+1E0h+var_1A4+4], dil
0x14011f285  mov     [rbp+1E0h+var_19C], rax
0x14011f289  mov     dword ptr [rbp+1E0h+var_19C], edi
0x14011f28c  mov     byte ptr [rbp+1E0h+var_19C+4], dil
0x14011f290  mov     [rbp+1E0h+var_194], rax
0x14011f294  mov     dword ptr [rbp+1E0h+var_194], edi
0x14011f297  mov     byte ptr [rbp+1E0h+var_194+4], dil
0x14011f29b  mov     [rbp+1E0h+var_18C], rax
0x14011f29f  mov     dword ptr [rbp+1E0h+var_18C], edi
0x14011f2a2  mov     byte ptr [rbp+1E0h+var_18C+4], dil
0x14011f2a6  mov     [rbp+1E0h+var_184], eax
0x14011f2a9  mov     [rbp+1E0h+var_180], dil
0x14011f2ad  mov     [rbp+1E0h+var_178], di
0x14011f2b1  mov     [rbp+1E0h+var_176], eax
0x14011f2b4  mov     [rbp+1E0h+var_172], ax
0x14011f2b8  movups  [rbp+1E0h+var_170], xmm0
0x14011f2bc  mov     qword ptr [rbp+1E0h+var_170], rdi
0x14011f2c0  mov     byte ptr [rbp+1E0h+var_170+8], dil
0x14011f2c4  movups  [rbp+1E0h+var_160], xmm0
0x14011f2cb  mov     qword ptr [rbp+1E0h+var_160], rdi
0x14011f2d2  mov     byte ptr [rbp+1E0h+var_160+8], dil
0x14011f2d9  mov     [rbp+1E0h+var_150], di
0x14011f2e0  mov     [rbp+1E0h+var_14E], rax
0x14011f2e7  mov     word ptr [rbp+1E0h+var_14E+7], di
0x14011f2ee  mov     byte ptr [rbp+1E0h+var_14E+6], dil
0x14011f2f5  mov     [rbp+1E0h+var_146], di
0x14011f2fc  mov     [rbp+1E0h+var_124], edi
0x14011f302  mov     [rbp+1E0h+var_144], rax
0x14011f309  mov     dword ptr [rbp+1E0h+var_144], edi
0x14011f30f  mov     byte ptr [rbp+1E0h+var_144+4], dil
0x14011f316  mov     [rbp+1E0h+var_13C], rax
0x14011f31d  mov     dword ptr [rbp+1E0h+var_13C], edi
0x14011f323  mov     byte ptr [rbp+1E0h+var_13C+4], dil
0x14011f32a  mov     [rbp+1E0h+var_134], rax
0x14011f331  mov     dword ptr [rbp+1E0h+var_134], edi
0x14011f337  mov     byte ptr [rbp+1E0h+var_134+4], dil
0x14011f33e  mov     [rbp+1E0h+var_12C], rax
0x14011f345  mov     dword ptr [rbp+1E0h+var_12C], edi
0x14011f34b  mov     byte ptr [rbp+1E0h+var_12C+4], dil
0x14011f352  mov     byte ptr [rbp+1E0h+var_124], dil
0x14011f359  mov     [rbp+1E0h+var_120], rax
0x14011f360  mov     [rbp+1E0h+var_120+4], rax
0x14011f367  mov     byte ptr [rbp+1E0h+var_120], dil
0x14011f36e  mov     word ptr [rbp+1E0h+var_120+1], ax
0x14011f375  mov     byte ptr [rbp+1E0h+var_120+3], al
0x14011f37b  mov     [rbp+1E0h+var_118], dil
0x14011f382  mov     [rbp+1E0h+var_114], eax
0x14011f388  mov     r8d, ebx; Size
0x14011f38b  xor     edx, edx; Val
0x14011f38d  lea     rcx, [rbp+1E0h+var_110]; void *
0x14011f394  call    memset_0
0x14011f399  lea     rcx, [rbp+1E0h+var_110]
0x14011f3a0  call    ??0?$optional@UMigrationTdxParams@Worker@Parameters@Migration@@@vmstd@@QEAA@XZ; vmstd::optional<Migration::Parameters::Worker::MigrationTdxParams>::optional<Migration::Parameters::Worker::MigrationTdxParams>(void)
0x14011f3a5  xor     edx, edx; Val
0x14011f3a7  lea     r8d, [rdi+48h]; Size
0x14011f3ab  lea     rcx, [rbp+1E0h+var_C0]; void *
0x14011f3b2  call    memset_0
0x14011f3b7  lea     rcx, [rbp+1E0h+var_C0]
0x14011f3be  call    ??0?$optional@UMigrationClassOfServiceParams@Worker@Parameters@Migration@@@vmstd@@QEAA@XZ; vmstd::optional<Migration::Parameters::Worker::MigrationClassOfServiceParams>::optional<Migration::Parameters::Worker::MigrationClassOfServiceParams>(void)
0x14011f3c3  xorps   xmm0, xmm0
0x14011f3c6  movups  [rbp+1E0h+var_78], xmm0
0x14011f3cd  movups  [rbp+1E0h+var_68], xmm0
0x14011f3d4  mov     dword ptr [rbp+1E0h+var_78], edi
0x14011f3da  xor     eax, eax
0x14011f3dc  mov     qword ptr [rbp+1E0h+var_78+4], rax
0x14011f3e3  mov     dword ptr [rbp+1E0h+var_78+4], edi
0x14011f3e9  mov     byte ptr [rbp+1E0h+var_78+8], dil
0x14011f3f0  mov     qword ptr [rbp+1E0h+var_78+0Ch], rax
0x14011f3f7  mov     dword ptr [rbp+1E0h+var_78+0Ch], edi
0x14011f3fd  mov     byte ptr [rbp+1E0h+var_68], dil
0x14011f404  mov     qword ptr [rbp+1E0h+var_68+4], rax
0x14011f40b  mov     dword ptr [rbp+1E0h+var_68+4], edi
0x14011f411  mov     byte ptr [rbp+1E0h+var_68+8], dil
0x14011f418  mov     byte ptr [rbp+1E0h+var_68+0Ch], dil
0x14011f41f  cmp     [r14+50h], dil
0x14011f423  jz      short loc_14011F441
0x14011f425  lea     rdx, [r14+8]
0x14011f429  cmp     [rdx+48h], dil
0x14011f42d  jnz     short loc_14011F434
0x14011f42f  lea     ecx, [rdi+5]
0x14011f432  int     29h; Win8: RtlFailFast(ecx)
0x14011f434  lea     rcx, [rbp+1E0h+var_1C8]
0x14011f438  call    ??4MemoryMigrationTransferThrottleParams@Options@Schema@@QEAAAEAU012@$$QEAU012@@Z; Schema::Options::MemoryMigrationTransferThrottleParams::operator=(Schema::Options::MemoryMigrationTransferThrottleParams &&)
0x14011f43d  mov     [rbp+1E0h+var_180], 1
0x14011f441  lea     rdx, [rbp+1E0h+var_1F0]
0x14011f445  lea     rcx, [rbp+1E0h+var_248]
0x14011f449  call    ??$ToJson@AEAUMigrationSourceInit@Worker@Parameters@Migration@@$$V@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUMigrationSourceInit@Worker@Parameters@Migration@@W4MarshalFlags@0@@Z; Marshal::ToJson<Migration::Parameters::Worker::MigrationSourceInit &,>(Migration::Parameters::Worker::MigrationSourceInit &,Marshal::MarshalFlags)
0x14011f44e  nop
0x14011f44f  cmp     qword ptr [rax+18h], 7
0x14011f454  jbe     short loc_14011F459
0x14011f456  mov     rax, [rax]
0x14011f459  mov     [rsp+2E0h+var_290], rax
0x14011f45e  mov     rax, [rbp+1E0h+var_200]
0x14011f462  mov     [rsp+2E0h+var_270], rax
0x14011f467  mov     rax, [rsp+2E0h+var_288]
0x14011f46c  mov     [rsp+2E0h+var_280], rax
0x14011f471  lea     rax, [rsp+2E0h+var_290]
0x14011f476  mov     qword ptr [rsp+2E0h+dwOptions], rax
0x14011f47b  lea     rax, [rsp+2E0h+var_270]
0x14011f480  mov     qword ptr [rsp+2E0h+bInheritHandle], rax
0x14011f485  lea     rax, [rsp+2E0h+var_29C]
0x14011f48a  mov     qword ptr [rsp+2E0h+dwDesiredAccess], rax; int
0x14011f48f  lea     r9, [rsp+2E0h+var_280]
0x14011f494  mov     rdx, [r13+10h]
0x14011f498  call    ??$InvokeWorkerProcessMethod@UIVmVirtualMachine@@PEAUIVmSimpleTask@@IPEAXPEBG$$ZPEAU2@AEAIPEAXPEBG@Vmwp@ComputeService@@YAJAEBUWorkerProcessContext@01@PEAUIUnknown@@P8IVmVirtualMachine@@EAAJPEAUIVmSimpleTask@@IPEAXPEBG@Z$$QEAPEAU5@AEAI$$QEAPEAX$$QEAPEBG@Z
0x14011f49d  mov     rcx, [rbp+1E8h]; this
  ... truncated ...
```
