# ComputeService::Management::Details::StartVmWorker(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::ActiveStateOperation)

- ea: `0x140027340`
- end: `0x140027e5d`
- name: `?StartVmWorker@Details@Management@ComputeService@@YAXAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@VActiveStateOperation@23@@Z`
- size: `2845`
- prototype: ``
- caller_count: `0`
- callee_count: `54`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1400142a0`
- `0x140017040`
- `0x14001d490`
- `0x14001d4d0`
- `0x140021f9c`
- `0x140026a80`
- `0x14002716c`
- `0x140027194`
- `0x140027340`
- `0x140027e64`
- `0x140028c68`
- `0x14002ac78`
- `0x14002ecd8`
- `0x14002f868`
- `0x140037618`
- `0x14005bdc8`
- `0x1400602cc`
- `0x14007ca70`
- `0x14007cb30`
- `0x14007d964`
- `0x14007edc4`
- `0x14007ef00`
- `0x14007efd4`
- `0x14007f03c`
- `0x14008569c`
- `0x14009c7dc`
- `0x14009d75c`
- `0x1400c40e0`
- `0x1400c9288`
- `0x1400d0da8`
- `0x1400f3944`
- `0x1400fc040`
- `0x1400ffacc`
- `0x1400fff5c`
- `0x140102828`
- `0x140109e40`
- `0x1401133bc`
- `0x1401332f0`
- `0x140134048`
- `0x1401826b4`
- `0x1401abf24`
- `0x1401b0d90`
- `0x1401b0e4c`
- `0x1401b66c4`
- `0x1401bc8dc`
- `0x1401c9c20`
- `0x1401cb148`
- `0x1401d39cc`
- `0x1401d8e88`
- `0x1401da7a0`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!GetDynamicTimeZoneInformation` at `0x140027b21`
- `api-ms-win-core-timezone-l1-1-0!GetDynamicTimeZoneInformation` at `0x140027b21`

## string_xrefs

- `0x140027454`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x14002747c`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x140027587`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x140027690`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x1400276b7`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x140027727`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x1400277b4`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x14002781d`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x140027844`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x1400278ba`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x1400278fb`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x140027961`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x1400279f9`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x140027402`: `onecore\vm\compute\management\computesystem\computesystem.h`
- `0x1400273bc`: `onecore\vm\compute\management\computesystem\ComputeSystem.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall ComputeService::Management::Details::StartVmWorker(
        _QWORD **a1,
        ComputeService::Management::ActiveStateOperation *a2)
{
  __int64 v4; // rsi
  __int64 v5; // r15
  __int64 started; // rdi
  struct ComputeService::Management::VirtualMachineState *v7; // rdx
  int v8; // ecx
  int v9; // r8d
  int v10; // eax
  struct IVmSimpleTask *v11; // r8
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  const struct ComputeService::Vmwp::WorkerProcessContext *v16; // r14
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // eax
  int v21; // ecx
  int v22; // eax
  HANDLE *v23; // r13
  int v24; // eax
  int v25; // eax
  int v26; // eax
  unsigned int v27; // eax
  __int64 v28; // r8
  __int64 v29; // rax
  int v30; // eax
  int CancellationToken; // eax
  struct Schema::VirtualMachines::Resources::TimeZoneInformation *v32; // r8
  __int64 v33; // rsi
  void (__fastcall *v34)(__int64, _DWORD *, __int64); // rdi
  __int64 v35; // rbx
  __int64 v36; // rdi
  void (__fastcall *v37)(__int64, _DWORD *); // rbx
  __int64 v38; // rdi
  void (__fastcall *v39)(__int64, _DWORD *, _QWORD *); // rbx
  BOOL v40; // esi
  __int64 v41; // rdi
  void (__fastcall *v42)(__int64, _DWORD *, _QWORD, _OWORD *); // rbx
  unsigned int v43; // r9d
  int pv; // [rsp+28h] [rbp-E0h]
  int v46[2]; // [rsp+58h] [rbp-B0h] BYREF
  const struct ComputeService::Vmwp::WorkerProcessContext *v47; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v48[3]; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v49[9]; // [rsp+80h] [rbp-88h] BYREF
  int v50; // [rsp+C8h] [rbp-40h] BYREF
  _DWORD v51[5]; // [rsp+CCh] [rbp-3Ch] BYREF
  __int128 v52; // [rsp+E0h] [rbp-28h]
  _OWORD v53[2]; // [rsp+F0h] [rbp-18h] BYREF
  __int128 v54; // [rsp+110h] [rbp+8h]
  __int64 v55; // [rsp+120h] [rbp+18h]
  __int64 v56; // [rsp+128h] [rbp+20h]
  Vml *v57[2]; // [rsp+130h] [rbp+28h] BYREF
  struct _GUID *v58; // [rsp+140h] [rbp+38h]
  unsigned int v59; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v60[120]; // [rsp+150h] [rbp+48h] BYREF
  _TIME_DYNAMIC_ZONE_INFORMATION pTimeZoneInformation; // [rsp+1C8h] [rbp+C0h] BYREF
  _BYTE v62[8]; // [rsp+378h] [rbp+270h] BYREF
  _BYTE v63[416]; // [rsp+380h] [rbp+278h] BYREF
  struct _TIME_DYNAMIC_ZONE_INFORMATION v64; // [rsp+520h] [rbp+418h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6F0h] [rbp+5E8h]

  v48[0] = a1;
  v49[8] = a2;
  v4 = _RTDynamicCast_0(
         **a1,
         0,
         &ComputeService::Management::ComputeSystemConfiguration `RTTI Type Descriptor',
         &ComputeService::Management::VirtualMachineConfiguration `RTTI Type Descriptor');
  if ( !v4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\ComputeSystem.h",
      (const char *)0x80004001LL,
      0);
  v5 = _RTDynamicCast_0(
         (*a1)[1],
         0,
         &ComputeService::Management::ComputeSystemState `RTTI Type Descriptor',
         &ComputeService::Management::VirtualMachineState `RTTI Type Descriptor');
  if ( !v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\computesystem.h",
      (const char *)0x80004001LL,
      0);
  started = ComputeService::Management::StateOperation::GetContextAs<ComputeService::Management::Details::StartVirtualMachineContext>(**(_QWORD **)a2);
  if ( *(_DWORD *)(v5 + 768) == 4 )
  {
    ComputeService::Management::ActiveStateOperation::RetrieveSocketResource(a2, v53);
    if ( !BYTE8(v53[0]) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8F6,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
        (const char *)0x80070057LL,
        0);
    if ( !*(_BYTE *)(started + 36) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8F8,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
        (const char *)0x80070057LL,
        0);
    LODWORD(v48[0]) = *(_DWORD *)(started + 32);
    v49[0] = &std::_Func_impl_no_alloc<_lambda_e0c1b49274b94860c5d3ddf2c0642f31_,std::optional<ComputeService::Management::OperationResult>,std::shared_ptr<ComputeService::Management::OperationResult>>::`vftable';
    v49[1] = v5;
    v49[7] = v49;
    ComputeService::Management::ActiveStateOperation::RegisterCancellationCallback(a2, v49);
    v51[0] = ComputeService::Management::MigrationUtils::GetCompressionWorkerCountFromSettings(
               (ComputeService::Management::MigrationUtils *)v5,
               v7);
    *(_OWORD *)&v48[1] = 0;
    v50 = 0;
    *(_OWORD *)&v51[1] = 0;
    *(_QWORD *)&v52 = 0;
    std::vector<SecureBuffer>::vector<SecureBuffer>(&v51[1], 0);
    if ( *(_QWORD *)&v51[3] == (_QWORD)v52 )
    {
      std::vector<SecureBuffer>::_Emplace_reallocate<SecureBuffer>(&v51[1], *(_QWORD *)&v51[3], &v48[1]);
    }
    else
    {
      **(_OWORD **)&v51[3] = 0;
      *(_QWORD *)&v51[3] += 16LL;
    }
    v47 = *(const struct ComputeService::Vmwp::WorkerProcessContext **)&v51[1];
    v46[0] = 7;
    if ( !BYTE8(v53[0]) )
      std::_Throw_bad_optional_access();
    v48[1] = *(_QWORD *)&v53[0];
    v10 = ___InvokeWorkerProcessMethod_UIVmVirtualMachine__PEAXKIIIPEAUSecureBuffer____ZPEAXJAEAIAEAIAEAIPEAU2__Vmwp_ComputeService__YAJAEBUWorkerProcessContext_01_PEAUIUnknown__P8IVmVirtualMachine__EAAJPEAXKIIIPEAUSecureBuffer___Z__QEAPEAX__QEAJAEAI77__QEAPEAU5__Z(
            v8,
            *(_QWORD *)(v5 + 640),
            v9,
            (unsigned int)&v48[1],
            (__int64)v46,
            (__int64)v48,
            (__int64)v51,
            (__int64)&v50,
            (__int64)&v47);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x920,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
        (const char *)(unsigned int)v10,
        pv);
    *(_QWORD *)v46 = 0;
    wil::AcquireSRWLockShared(v46, v5 + 2720);
    v12 = ComputeService::Vmwp::CheckForWorkerProcessTaskResult(
            (ComputeService::Vmwp *)(v5 + 624),
            *(const struct ComputeService::Vmwp::WorkerProcessContext **)(v5 + 2728),
            v11);
    ComputeService::Management::ActiveStateOperation::Complete(a2, v12);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v46);
    std::vector<_HV_SUBNODE>::_Tidy(&v51[1]);
    std::_Optional_destruct_base<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>>,0>::~_Optional_destruct_base<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>>,0>(v53);
  }
  else
  {
    v50 = 0;
    LOBYTE(v51[0]) = 0;
    v13 = Vml::VmComMultiInstanceObject<ComputeService::Vmwp::Task>::CreateInstance<bool>(v51);
    v16 = (const struct ComputeService::Vmwp::WorkerProcessContext *)((v13 + 24) & -(__int64)(v13 != 0));
    v48[1] = v16;
    v58 = 0;
    *(_OWORD *)v57 = 0;
    *(_QWORD *)v46 = v16;
    if ( v16 )
      (*(void (__fastcall **)(const struct ComputeService::Vmwp::WorkerProcessContext *))(*(_QWORD *)v16 + 8LL))(v16);
    v17 = std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>(
            v53,
            a1,
            v14,
            v15);
    ComputeService::Management::Details::RegisterTaskForNotifications(v17, a2, v46, v57);
    v19 = (unsigned int)(*(_DWORD *)(v5 + 768) - 1);
    switch ( *(_DWORD *)(v5 + 768) )
    {
      case 1:
        v47 = v16;
        v23 = (HANDLE *)(v5 + 624);
        v26 = ___InvokeWorkerProcessMethod_UIVmVirtualMachine__PEAUIVmSimpleTask____ZPEAU2__Vmwp_ComputeService__YAJAEBUWorkerProcessContext_01_PEAUIUnknown__P8IVmVirtualMachine__EAAJPEAUIVmSimpleTask___Z__QEAPEAU5__Z(
                v19,
                *(_QWORD *)(v5 + 640),
                SavedStateStorage::SetUnsignedIntegerValue,
                &v47);
        if ( v26 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x98A,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
            (const char *)(unsigned int)v26,
            0);
        break;
      case 2:
        if ( *(_BYTE *)(started + 28) )
        {
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x93B,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
            (const char *)0x8037010DLL,
            0);
          v46[0] = 5;
          std::pair<std::wstring,enum Marshal::UnmarshalError>::pair<std::wstring,enum Marshal::UnmarshalError>(
            v53,
            L"RestoreOptions unexpected",
            v46);
          ComputeService::Reporting::FormatUnMarshalError(&v51[1], v53);
          ComputeService::Reporting::LogAndThrowComputeError<std::wstring>(-2143878899);
        }
        v47 = v16;
        v23 = (HANDLE *)(v5 + 624);
        v25 = ___InvokeWorkerProcessMethod_UIVmVirtualMachine__PEAUIVmSimpleTask__W4__MIDL___MIDL_itf_vmwrkr_0000_0006_0005____ZPEAU2_AEAW43__Vmwp_ComputeService__YAJAEBUWorkerProcessContext_01_P8IVmVirtualMachine__EAAJPEAUIVmSimpleTask__W4__MIDL___MIDL_itf_vmwrkr_0000_0006_0005___Z__QEAPEAU4_AEAW45__Z(
                v5 + 624,
                v18,
                &v47,
                &v50);
        if ( v25 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x942,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
            (const char *)(unsigned int)v25,
            0);
        break;
      case 3:
        if ( !*(_BYTE *)(started + 28) )
        {
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x94B,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
            (const char *)0x8037010DLL,
            0);
          std::wstring::wstring(v53, L"RestoreOptions required");
          LODWORD(v54) = 5;
          ComputeService::Reporting::FormatUnMarshalError(&v51[1], v53);
          ComputeService::Reporting::LogAndThrowComputeError<std::wstring>(-2143878899);
        }
        if ( *(_DWORD *)(started + 8) )
        {
          if ( !*(_BYTE *)(v4 + 4296) )
            __fastfail(5u);
          if ( *(_BYTE *)(v4 + 3767) )
          {
            wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)0x953,
              (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
              (const char *)0x8037010DLL,
              0);
            std::wstring::wstring(v53, L"GuestConnection and RestoreModePaused unexpected");
            LODWORD(v54) = 5;
            ComputeService::Reporting::FormatUnMarshalError(&v51[1], v53);
            ComputeService::Reporting::LogAndThrowComputeError<std::wstring>(-2143878899);
          }
        }
        v20 = 1;
        v50 = 1;
        if ( *(_DWORD *)(started + 8) == 1 )
        {
          v20 = 9;
          v50 = 9;
          v21 = 13;
        }
        else
        {
          v21 = 5;
        }
        if ( *(_BYTE *)(started + 24) )
        {
          v18 = *(unsigned int *)(started + 20);
          if ( (*(_BYTE *)(started + 16) & 1) != 0 )
            v20 = v21;
          v50 = v20;
          if ( (v18 & 7) != 0 )
          {
            if ( !*(_QWORD *)(v5 + 1736) )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x96D,
                (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
                (const char *)0x80070006LL,
                0);
            v22 = v20 | 0x10;
            v50 = v22;
            if ( (v18 & 1) != 0 )
            {
              v22 |= 0x20u;
              v50 = v22;
            }
            if ( (v18 & 2) != 0 )
            {
              v22 |= 0x40u;
              v50 = v22;
            }
            if ( (v18 & 4) != 0 )
              v50 = v22 | 0x80;
          }
        }
        v47 = v16;
        v23 = (HANDLE *)(v5 + 624);
        v24 = ___InvokeWorkerProcessMethod_UIVmVirtualMachine__PEAUIVmSimpleTask__W4__MIDL___MIDL_itf_vmwrkr_0000_0006_0005____ZPEAU2_AEAW43__Vmwp_ComputeService__YAJAEBUWorkerProcessContext_01_P8IVmVirtualMachine__EAAJPEAUIVmSimpleTask__W4__MIDL___MIDL_itf_vmwrkr_0000_0006_0005___Z__QEAPEAU4_AEAW45__Z(
                v5 + 624,
                v18,
                &v47,
                &v50);
        if ( v24 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x983,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
            (const char *)(unsigned int)v24,
            0);
        break;
      default:
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x98E,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
          (const char *)0x80004001LL,
          0);
    }
    *(_QWORD *)v46 = v16;
    if ( v16 )
      (*(void (__fastcall **)(const struct ComputeService::Vmwp::WorkerProcessContext *))(*(_QWORD *)v16 + 8LL))(v16);
    ComputeService::Management::Details::AddTaskToServerOperation(v53, a2, v46);
    v27 = ComputeService::Vmwp::WaitForWorkerProcessTask(v23, v16, (struct IVmSimpleTask *)0xFFFFFFFFLL);
    v28 = v27;
    if ( (v27 & 0x80000000) != 0 )
    {
      if ( v27 == -2147217408 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x998,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
          (const char *)0x80070102LL,
          0);
      *(_DWORD *)(**(_QWORD **)a2 + 136LL) = 2;
      ComputeService::Vmwp::ThrowComputeExceptionOnTaskFailure(
        (ComputeService::Vmwp *)v27,
        (int)v16,
        (struct IVmSimpleTask *)v27);
    }
    if ( *(_DWORD *)(v5 + 768) == 3 )
    {
      if ( !*(_BYTE *)(started + 28) )
        __fastfail(5u);
      if ( !*(_DWORD *)(started + 8) )
      {
        *(_QWORD *)v46 = 0;
        LOBYTE(v51[0]) = 0;
        v29 = Vml::VmComMultiInstanceObject<ComputeService::Vmwp::Task>::CreateInstance<bool>(v51);
        Vml::VmComPtr<IStream>::Attach<Vml::VmComFixedMemStream>(v46, v29);
        v47 = *(const struct ComputeService::Vmwp::WorkerProcessContext **)v46;
        v30 = ___InvokeWorkerProcessMethod_UIVmVirtualMachine__PEAUIVmSimpleTask____ZPEAU2__Vmwp_ComputeService__YAJAEBUWorkerProcessContext_01_P8IVmVirtualMachine__EAAJPEAUIVmSimpleTask___Z__QEAPEAU4__Z(
                v23,
                 IVmVirtualMachine::`vcall'{152,{flat}},
                &v47);
        if ( v30 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x9AD,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
            (const char *)(unsigned int)v30,
            0);
        Vml::VmComPtr<IVmSimpleTaskEvents>::~VmComPtr<IVmSimpleTaskEvents>(v46);
      }
    }
    if ( !*(_BYTE *)(v4 + 4296) )
      __fastfail(5u);
    if ( *(_BYTE *)(v4 + 3767) )
    {
      LOWORD(v51[0]) = *(_WORD *)(v4 + 3764);
      CancellationToken = ComputeService::Management::CreateCancellationToken(v53, v5, v28);
      ComputeService::UtilityVm::ConnectToGuestService(
        v48[0],
        v5 + 128,
        (int)v23,
        CancellationToken,
        (PVOID)(v5 + 72),
        (__int64)v51);
      (*(void (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(v5 + 168) + 48LL))(*(_QWORD *)(v5 + 168), &v59);
      if ( *(_DWORD *)(v5 + 768) == 1 && v59 >= 4 )
      {
        if ( v60[0] )
        {
          Config::Containers::VmHosted::VmHostedContainerSettings::VmHostedContainerSettings((Config::Containers::VmHosted::VmHostedContainerSettings *)v62);
          std::wstring::operator=(v63, v4 + 48);
          if ( !*(_BYTE *)(v4 + 4296) )
            __fastfail(5u);
          if ( !*(_BYTE *)(v4 + 3767) )
            __fastfail(5u);
          if ( *(_BYTE *)(v4 + 3766) )
          {
            memset_0(&pTimeZoneInformation, 0, sizeof(pTimeZoneInformation));
            if ( GetDynamicTimeZoneInformation(&pTimeZoneInformation) != -1 )
              ComputeService::Communication::BridgeUtilities::TimeZoneInfoToHostedContainerSettings(
                (ComputeService::Communication::BridgeUtilities *)&pTimeZoneInformation,
                &v64,
                v32);
          }
          v33 = *(_QWORD *)(v5 + 136);
          v34 = *(void (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v33 + 8LL);
          v35 = Marshal::ToJson<Config::Containers::VmHosted::VmHostedContainerSettings &,>(v53, v62);
          std::wstring::wstring(&v51[1], L"00000000-0000-0000-0000-000000000000");
          v34(v33, &v51[1], v35);
          Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)&v51[1]);
          Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v53);
          if ( v60[1] )
          {
            v36 = *(_QWORD *)(v5 + 136);
            v37 = *(void (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v36 + 16LL);
            std::wstring::wstring(&v51[1], L"00000000-0000-0000-0000-000000000000");
            v37(v36, &v51[1]);
            Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)&v51[1]);
          }
          Config::Containers::VmHosted::VmHostedContainerSettings::~VmHostedContainerSettings((Config::Containers::VmHosted::VmHostedContainerSettings *)v62);
        }
        if ( v60[2] )
        {
          v52 = 0;
          *(_OWORD *)&v51[1] = *(_OWORD *)v23;
          *(_QWORD *)&v52 = 0x424F9D79894CC2D6LL;
          *((_QWORD *)&v52 + 1) = 0xD1D8E69A9642FE93uLL;
          memset_0(&pTimeZoneInformation.StandardName[2], 0, 0x40u);
          memset(&pTimeZoneInformation.StandardName[2], 0, 60);
          memset_0(&pTimeZoneInformation.StandardDate.wDayOfWeek, 0, 0x40u);
          memset(&pTimeZoneInformation.StandardDate.wDayOfWeek, 0, 60);
          pTimeZoneInformation.Bias = 4;
          wcscpy(pTimeZoneInformation.StandardName, L"\x02");
          Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(
            v49,
            &v51[1]);
          Marshal::DelayedBase<Schema::Responses::System::CacheQueryStatsResponse,Marshal::Details::DelayedJsonTraits>::operator=(
            &pTimeZoneInformation.StandardName[2],
            v49);
          Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(v49);
          v38 = *(_QWORD *)(v5 + 136);
          v39 = *(void (__fastcall **)(__int64, _DWORD *, _QWORD *))(*(_QWORD *)v38 + 48LL);
          Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(
            v49,
            &pTimeZoneInformation);
          std::wstring::wstring(&v51[1], L"00000000-0000-0000-0000-000000000000");
          v39(v38, &v51[1], v49);
          Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)&v51[1]);
          Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(v49);
          Schema::Requests::Guest::GuestModifySettingRequest::~GuestModifySettingRequest((Schema::Requests::Guest::GuestModifySettingRequest *)&pTimeZoneInformation);
        }
      }
      v40 = *(_DWORD *)(v5 + 768) == 2;
      v41 = *(_QWORD *)(v5 + 136);
      v42 = *(void (__fastcall **)(__int64, _DWORD *, _QWORD, _OWORD *))(*(_QWORD *)v41 + 88LL);
      v47 = (const struct ComputeService::Vmwp::WorkerProcessContext *)v53;
      v56 = 0;
      memset(v53, 0, sizeof(v53));
      v54 = 0;
      v55 = 0;
      *(_OWORD *)&v51[1] = 0;
      v52 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v51[1], L"00000000-0000-0000-0000-000000000000");
      v42(v41, &v51[1], (unsigned int)(v40 + 1), v53);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)&v51[1]);
      Compute::Containers::BridgeMessage::GcsCapabilities::~GcsCapabilities((Compute::Containers::BridgeMessage::GcsCapabilities *)v60);
    }
    ComputeService::Management::ActiveStateOperation::Complete(a2, 0);
    if ( v57[1] )
      Vml::VmComEventDisconnect(
        v57[0],
        (struct IUnknown *)&GUID_14187e2c_d951_4846_be6b_d028020c18e2,
        (const struct _GUID *)(unsigned int)v58,
        v43);
    Vml::VmComPtr<Vml::VmComLocalMemStream>::~VmComPtr<Vml::VmComLocalMemStream>(&v57[1]);
    Vml::VmComPtr<IVmSimpleTaskEvents>::~VmComPtr<IVmSimpleTaskEvents>(v57);
    if ( v16 )
      (*(void (__fastcall **)(const struct ComputeService::Vmwp::WorkerProcessContext *))(*(_QWORD *)v16 + 16LL))(v16);
  }
  return std::unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>::~unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>(a2);
}

```

## disassembly

```asm
0x140027340  mov     rax, rsp
0x140027343  mov     [rax+18h], rbx
0x140027347  push    rbp
0x140027348  push    rsi
0x140027349  push    rdi
0x14002734a  push    r12
0x14002734c  push    r13
0x14002734e  push    r14
0x140027350  push    r15
0x140027352  lea     rbp, [rax-5E8h]
0x140027359  sub     rsp, 6B0h
0x140027360  movaps  xmmword ptr [rax-48h], xmm6
0x140027364  mov     rax, cs:__security_cookie
0x14002736b  xor     rax, rsp
0x14002736e  mov     qword ptr [rbp+5E0h+var_1C8.TimeZoneKeyName+0CCh], rax
0x140027375  mov     r12, rdx
0x140027378  mov     rbx, rcx
0x14002737b  mov     qword ptr [rsp+6E0h+var_680], rcx
0x140027380  mov     [rbp+5E0h+var_628], rdx
0x140027384  mov     rcx, [rcx]
0x140027387  xor     r13d, r13d
0x14002738a  mov     dword ptr [rsp+6E0h+pv], r13d; int
0x14002738f  lea     r9, ??_R0?AUVirtualMachineConfiguration@Management@ComputeService@@@8; ComputeService::Management::VirtualMachineConfiguration `RTTI Type Descriptor'
0x140027396  lea     r8, ??_R0?AUComputeSystemConfiguration@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemConfiguration `RTTI Type Descriptor'
0x14002739d  xor     edx, edx
0x14002739f  mov     rcx, [rcx]
0x1400273a2  call    __RTDynamicCast_0
0x1400273a7  mov     rsi, rax
0x1400273aa  mov     rcx, [rbp+5E8h]; this
0x1400273b1  test    rax, rax
0x1400273b4  jnz     short loc_1400273CC
0x1400273b6  mov     r9d, 80004001h; char *
0x1400273bc  lea     r8, aOnecoreVmCompu_61; "onecore\\vm\\compute\\management\\compu"...
0x1400273c3  lea     edx, [rax+5Dh]; void *
0x1400273c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400273cc  mov     rcx, [rbx]
0x1400273cf  mov     dword ptr [rsp+6E0h+pv], r13d; int
0x1400273d4  lea     r9, ??_R0?AUVirtualMachineState@Management@ComputeService@@@8; ComputeService::Management::VirtualMachineState `RTTI Type Descriptor'
0x1400273db  lea     r8, ??_R0?AUComputeSystemState@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemState `RTTI Type Descriptor'
0x1400273e2  xor     edx, edx
0x1400273e4  mov     rcx, [rcx+8]
0x1400273e8  call    __RTDynamicCast_0
0x1400273ed  mov     r15, rax
0x1400273f0  mov     rcx, [rbp+5E8h]; this
0x1400273f7  test    rax, rax
0x1400273fa  jnz     short loc_140027412
0x1400273fc  mov     r9d, 80004001h; char *
0x140027402  lea     r8, aOnecoreVmCompu_31; "onecore\\vm\\compute\\management\\compu"...
0x140027409  lea     edx, [rax+5Dh]; void *
0x14002740c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140027412  mov     rcx, [r12]
0x140027416  mov     rcx, [rcx]
0x140027419  call    ??$GetContextAs@UStartVirtualMachineContext@Details@Management@ComputeService@@@StateOperation@Management@ComputeService@@QEBAPEAUStartVirtualMachineContext@Details@12@XZ; ComputeService::Management::StateOperation::GetContextAs<ComputeService::Management::Details::StartVirtualMachineContext>(void)
0x14002741e  mov     rdi, rax
0x140027421  cmp     dword ptr [r15+300h], 4
0x140027429  jnz     loc_1400275ED
0x14002742f  lea     rdx, [rbp+5E0h+var_5F8]
0x140027433  mov     rcx, r12
0x140027436  call    ?RetrieveSocketResource@ActiveStateOperation@Management@ComputeService@@QEAA?AV?$optional@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@wil@@@std@@PEBG@Z; ComputeService::Management::ActiveStateOperation::RetrieveSocketResource(ushort const *)
0x14002743b  nop
0x14002743c  cmp     byte ptr [rbp+5E0h+var_5F8+8], r13b
0x140027440  setz    cl
0x140027443  mov     rax, [rbp+5E8h]
0x14002744a  test    cl, cl
0x14002744c  jz      short loc_140027469
0x14002744e  mov     r9d, 80070057h; char *
0x140027454  lea     r8, aOnecoreVmCompu_36; "onecore\\vm\\compute\\management\\orche"...
0x14002745b  mov     edx, 8F6h; void *
0x140027460  mov     rcx, rax; this
0x140027463  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140027469  mov     rcx, [rbp+5E8h]; this
0x140027470  cmp     [rdi+24h], r13b
0x140027474  jnz     short loc_14002748E
0x140027476  mov     r9d, 80070057h; char *
0x14002747c  lea     r8, aOnecoreVmCompu_36; "onecore\\vm\\compute\\management\\orche"...
0x140027483  mov     edx, 8F8h; void *
0x140027488  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14002748e  mov     eax, [rdi+20h]
0x140027491  mov     dword ptr [rsp+6E0h+var_680], eax
0x140027495  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_e0c1b49274b94860c5d3ddf2c0642f31_@@V?$optional@UOperationResult@Management@ComputeService@@@std@@V?$shared_ptr@UOperationResult@Management@ComputeService@@@3@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_e0c1b49274b94860c5d3ddf2c0642f31_,std::optional<ComputeService::Management::OperationResult>,std::shared_ptr<ComputeService::Management::OperationResult>>::`vftable'
0x14002749c  mov     [rsp+6E0h+var_668], rax
0x1400274a1  mov     [rbp+5E0h+var_660], r15
0x1400274a5  lea     rax, [rsp+6E0h+var_668]
0x1400274aa  mov     [rbp+5E0h+var_630], rax
0x1400274ae  lea     rdx, [rsp+6E0h+var_668]
0x1400274b3  mov     rcx, r12
0x1400274b6  call    ?RegisterCancellationCallback@ActiveStateOperation@Management@ComputeService@@QEAAXV?$function@$$A6A?AV?$optional@UOperationResult@Management@ComputeService@@@std@@V?$shared_ptr@UOperationResult@Management@ComputeService@@@2@@Z@std@@@Z; ComputeService::Management::ActiveStateOperation::RegisterCancellationCallback(std::function<std::optional<ComputeService::Management::OperationResult> (std::shared_ptr<ComputeService::Management::OperationResult>)>)
0x1400274bb  mov     rcx, r15; this
0x1400274be  call    ?GetCompressionWorkerCountFromSettings@MigrationUtils@Management@ComputeService@@YAIPEAUVirtualMachineState@23@@Z; ComputeService::Management::MigrationUtils::GetCompressionWorkerCountFromSettings(ComputeService::Management::VirtualMachineState *)
0x1400274c3  mov     dword ptr [rbp+5E0h+var_61C], eax
0x1400274c6  xorps   xmm6, xmm6
0x1400274c9  movups  xmmword ptr [rsp+6E0h+var_680+8], xmm6
0x1400274ce  mov     [rbp+5E0h+var_620], r13d
0x1400274d2  xorps   xmm0, xmm0
0x1400274d5  xor     eax, eax
0x1400274d7  movups  xmmword ptr [rbp+5E0h+var_61C+4], xmm0
0x1400274db  mov     qword ptr [rbp+5E0h+var_608], rax
0x1400274df  xor     edx, edx
0x1400274e1  lea     rcx, [rbp+5E0h+var_61C+4]
0x1400274e5  call    ??0?$vector@USecureBuffer@@V?$allocator@USecureBuffer@@@std@@@std@@QEAA@_KAEBV?$allocator@USecureBuffer@@@1@@Z; std::vector<SecureBuffer>::vector<SecureBuffer>(unsigned __int64,std::allocator<SecureBuffer> const &)
0x1400274ea  nop
0x1400274eb  mov     rdx, qword ptr [rbp+5E0h+var_61C+0Ch]
0x1400274ef  cmp     rdx, qword ptr [rbp+5E0h+var_608]
0x1400274f3  jz      short loc_140027500
0x1400274f5  movdqu  xmmword ptr [rdx], xmm6
0x1400274f9  add     qword ptr [rbp+5E0h+var_61C+0Ch], 10h
0x1400274fe  jmp     short loc_14002750E
0x140027500  lea     r8, [rsp+6E0h+var_680+8]
0x140027505  lea     rcx, [rbp+5E0h+var_61C+4]
0x140027509  call    ??$_Emplace_reallocate@USecureBuffer@@@?$vector@USecureBuffer@@V?$allocator@USecureBuffer@@@std@@@std@@AEAAPEAUSecureBuffer@@QEAU2@$$QEAU2@@Z; std::vector<SecureBuffer>::_Emplace_reallocate<SecureBuffer>(SecureBuffer * const,SecureBuffer &&)
0x14002750e  mov     rax, qword ptr [rbp+5E0h+var_61C+4]
0x140027512  mov     [rsp+6E0h+var_688], rax
0x140027517  mov     [rsp+6E0h+var_690], 7
0x14002751f  cmp     byte ptr [rbp+5E0h+var_5F8+8], r13b
0x140027523  jnz     short loc_14002752B
0x140027525  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
0x14002752b  mov     rax, qword ptr [rbp+5E0h+var_5F8]
0x14002752f  mov     qword ptr [rsp+6E0h+var_680+8], rax
0x140027534  lea     rbx, [r15+270h]
0x14002753b  lea     rax, [rsp+6E0h+var_688]
0x140027540  mov     [rsp+6E0h+var_6A0], rax
0x140027545  lea     rax, [rbp+5E0h+var_620]
0x140027549  mov     [rsp+6E0h+var_6A8], rax
0x14002754e  lea     rax, [rbp+5E0h+var_61C]
0x140027552  mov     [rsp+6E0h+var_6B0], rax
0x140027557  lea     rax, [rsp+6E0h+var_680]
0x14002755c  mov     [rsp+6E0h+var_6B8], rax
0x140027561  lea     rax, [rsp+6E0h+var_690]
0x140027566  mov     [rsp+6E0h+pv], rax; int
0x14002756b  lea     r9, [rsp+6E0h+var_680+8]
0x140027570  mov     rdx, [rbx+10h]
0x140027574  call    ??$InvokeWorkerProcessMethod@UIVmVirtualMachine@@PEAXKIIIPEAUSecureBuffer@@$$ZPEAXJAEAIAEAIAEAIPEAU2@@Vmwp@ComputeService@@YAJAEBUWorkerProcessContext@01@PEAUIUnknown@@P8IVmVirtualMachine@@EAAJPEAXKIIIPEAUSecureBuffer@@@Z$$QEAPEAX$$QEAJAEAI77$$QEAPEAU5@@Z
0x140027579  mov     rcx, [rbp+5E8h]; this
0x140027580  test    eax, eax
0x140027582  jns     short loc_140027599
0x140027584  mov     r9d, eax; char *
0x140027587  lea     r8, aOnecoreVmCompu_36; "onecore\\vm\\compute\\management\\orche"...
0x14002758e  mov     edx, 920h; void *
0x140027593  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140027599  mov     qword ptr [rsp+6E0h+var_690], r13
0x14002759e  lea     rdx, [r15+0AA0h]
0x1400275a5  lea     rcx, [rsp+6E0h+var_690]
0x1400275aa  call    ?AcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockShared(_RTL_SRWLOCK *)
0x1400275af  nop
0x1400275b0  mov     rdx, [r15+0AA8h]; struct ComputeService::Vmwp::WorkerProcessContext *
0x1400275b7  mov     rcx, rbx; this
0x1400275ba  call    ?CheckForWorkerProcessTaskResult@Vmwp@ComputeService@@YAJAEBUWorkerProcessContext@12@PEAUIVmSimpleTask@@@Z; ComputeService::Vmwp::CheckForWorkerProcessTaskResult(ComputeService::Vmwp::WorkerProcessContext const &,IVmSimpleTask *)
0x1400275bf  mov     edx, eax; int
0x1400275c1  mov     rcx, r12; this
0x1400275c4  call    ?Complete@ActiveStateOperation@Management@ComputeService@@QEAAXJ@Z; ComputeService::Management::ActiveStateOperation::Complete(long)
0x1400275c9  nop
0x1400275ca  lea     rcx, [rsp+6E0h+var_690]
0x1400275cf  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1400275d4  nop
0x1400275d5  lea     rcx, [rbp+5E0h+var_61C+4]
0x1400275d9  call    ?_Tidy@?$vector@U_HV_SUBNODE@@V?$allocator@U_HV_SUBNODE@@@std@@@std@@AEAAXXZ; std::vector<_HV_SUBNODE>::_Tidy(void)
0x1400275de  nop
0x1400275df  lea     rcx, [rbp+5E0h+var_5F8]
0x1400275e3  call    ??1?$_Optional_destruct_base@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@wil@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>>,0>::~_Optional_destruct_base<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>>,0>(void)
0x1400275e8  jmp     loc_140027E25
0x1400275ed  mov     [rbp+5E0h+var_620], r13d
0x1400275f1  mov     qword ptr [rsp+6E0h+var_680+8], r13
0x1400275f6  mov     [rbp+5E0h+var_61C], r13b
0x1400275fa  lea     rcx, [rbp+5E0h+var_61C]
0x1400275fe  call    ??$CreateInstance@_N@?$VmComMultiInstanceObject@VTask@Vmwp@ComputeService@@@Vml@@SAPEAVTask@Vmwp@ComputeService@@$$QEA_N@Z; Vml::VmComMultiInstanceObject<ComputeService::Vmwp::Task>::CreateInstance<bool>(bool &&)
0x140027603  lea     rcx, [rax+18h]
0x140027607  neg     rax
0x14002760a  sbb     r14, r14
0x14002760d  and     r14, rcx
0x140027610  mov     qword ptr [rsp+6E0h+var_680+8], r14
0x140027615  xor     eax, eax
0x140027617  mov     [rbp+5E0h+var_5A8], rax
0x14002761b  xorps   xmm1, xmm1
0x14002761e  movdqu  xmmword ptr [rbp+5E0h+var_5B8], xmm1
0x140027623  mov     qword ptr [rsp+6E0h+var_690], r14
0x140027628  test    r14, r14
0x14002762b  jz      short loc_14002763C
0x14002762d  mov     rax, [r14]
0x140027630  mov     rcx, r14
0x140027633  mov     rax, [rax+8]
0x140027637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002763c  mov     rdx, rbx
0x14002763f  lea     rcx, [rbp+5E0h+var_5F8]
0x140027643  call    ??0?$shared_ptr@VINetworkResourceAllocator@Resource@ComputeService@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>(std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator> const &)
0x140027648  lea     r9, [rbp+5E0h+var_5B8]
0x14002764c  lea     r8, [rsp+6E0h+var_690]
0x140027651  mov     rdx, r12
0x140027654  mov     rcx, rax
0x140027657  call    ?RegisterTaskForNotifications@Details@Management@ComputeService@@YAXV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@AEAVActiveStateOperation@23@V?$VmComPtr@UIVmSimpleTask@@@Vml@@AEAV?$ComTaskEventRAII@UIVmSimpleTask@@VWorkerProcessTaskEventSink@Management@ComputeService@@@Vmwp@3@@Z; ComputeService::Management::Details::RegisterTaskForNotifications(std::shared_ptr<ComputeService::Management::ComputeSystem>,ComputeService::Management::ActiveStateOperation &,Vml::VmComPtr<IVmSimpleTask>,ComputeService::Vmwp::ComTaskEventRAII<IVmSimpleTask,ComputeService::Management::WorkerProcessTaskEventSink> &)
0x14002765c  mov     ecx, [r15+300h]
0x140027663  mov     ebx, 5
0x140027668  lea     r8d, [rbx-4]
0x14002766c  sub     ecx, r8d
0x14002766f  jz      loc_1400278CC
0x140027675  sub     ecx, r8d
0x140027678  jz      loc_14002782F
0x14002767e  cmp     ecx, r8d
0x140027681  jz      short loc_1400276A2
0x140027683  mov     rcx, [rbp+5E8h]; this
0x14002768a  mov     r9d, 80004001h; char *
0x140027690  lea     r8, aOnecoreVmCompu_36; "onecore\\vm\\compute\\management\\orche"...
0x140027697  mov     edx, 98Eh; void *
0x14002769c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400276a2  cmp     [rdi+1Ch], r13b
0x1400276a6  jnz     short loc_1400276FB
0x1400276a8  mov     rcx, [rbp+5E8h]; this
0x1400276af  mov     edi, 8037010Dh
0x1400276b4  mov     r9d, edi; char *
0x1400276b7  lea     r8, aOnecoreVmCompu_36; "onecore\\vm\\compute\\management\\orche"...
0x1400276be  mov     edx, 94Bh; void *
0x1400276c3  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1400276c8  lea     rdx, aRestoreoptions; "RestoreOptions required"
0x1400276cf  lea     rcx, [rbp+5E0h+var_5F8]
0x1400276d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400276d8  mov     dword ptr [rbp+5E0h+var_5D8], ebx
0x1400276db  lea     rdx, [rbp+5E0h+var_5F8]
0x1400276df  lea     rcx, [rbp+5E0h+var_61C+4]
0x1400276e3  call    ?FormatUnMarshalError@Reporting@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@4@@Z; ComputeService::Reporting::FormatUnMarshalError(std::pair<std::wstring,Marshal::UnmarshalError> const &)
0x1400276e8  nop
0x1400276e9  mov     r8, rax
0x1400276ec  lea     rdx, MSVCOMP_INVALID_OPTIONS_DOCUMENT
0x1400276f3  mov     ecx, edi; int
0x1400276f5  call    ??$LogAndThrowComputeError@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Reporting@ComputeService@@YAXJPEBU_EVENT_DESCRIPTOR@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::Reporting::LogAndThrowComputeError<std::wstring>(long,_EVENT_DESCRIPTOR const *,std::wstring &&)
0x1400276fb  cmp     [rdi+8], r13d
0x1400276ff  jz      short loc_14002776B
0x140027701  cmp     [rsi+10C8h], r13b
0x140027708  jnz     short loc_14002770F
0x14002770a  mov     rcx, rbx
0x14002770d  int     29h; Win8: RtlFailFast(ecx)
0x14002770f  cmp     [rsi+0EB7h], r13b
0x140027716  jz      short loc_14002776B
0x140027718  mov     rcx, [rbp+5E8h]; this
0x14002771f  mov     edi, 8037010Dh
0x140027724  mov     r9d, edi; char *
0x140027727  lea     r8, aOnecoreVmCompu_36; "onecore\\vm\\compute\\management\\orche"...
0x14002772e  mov     edx, 953h; void *
0x140027733  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x140027738  lea     rdx, aGuestconnectio_1; "GuestConnection and RestoreModePaused u"...
0x14002773f  lea     rcx, [rbp+5E0h+var_5F8]
0x140027743  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140027748  mov     dword ptr [rbp+5E0h+var_5D8], ebx
0x14002774b  lea     rdx, [rbp+5E0h+var_5F8]
0x14002774f  lea     rcx, [rbp+5E0h+var_61C+4]
0x140027753  call    ?FormatUnMarshalError@Reporting@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@4@@Z; ComputeService::Reporting::FormatUnMarshalError(std::pair<std::wstring,Marshal::UnmarshalError> const &)
0x140027758  nop
0x140027759  mov     r8, rax
0x14002775c  lea     rdx, MSVCOMP_INVALID_CONFIGURATION_DOCUMENT
0x140027763  mov     ecx, edi; int
0x140027765  call    ??$LogAndThrowComputeError@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Reporting@ComputeService@@YAXJPEBU_EVENT_DESCRIPTOR@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::Reporting::LogAndThrowComputeError<std::wstring>(long,_EVENT_DESCRIPTOR const *,std::wstring &&)
0x14002776b  mov     eax, r8d
0x14002776e  mov     [rbp+5E0h+var_620], eax
0x140027771  cmp     [rdi+8], r8d
0x140027775  jnz     short loc_140027784
0x140027777  mov     eax, 9
0x14002777c  mov     [rbp+5E0h+var_620], eax
0x14002777f  lea     ecx, [rax+4]
0x140027782  jmp     short loc_140027786
0x140027784  mov     ecx, ebx
0x140027786  cmp     [rdi+18h], r13b
0x14002778a  jz      short loc_1400277EE
0x14002778c  mov     edx, [rdi+14h]
0x14002778f  test    [rdi+10h], r8b
0x140027793  cmovnz  eax, ecx
0x140027796  mov     [rbp+5E0h+var_620], eax
0x140027799  test    dl, 7
0x14002779c  jz      short loc_1400277EE
0x14002779e  mov     rcx, [rbp+5E8h]; this
0x1400277a5  cmp     [r15+6C8h], r13
0x1400277ac  jnz     short loc_1400277C6
0x1400277ae  mov     r9d, 80070006h; char *
0x1400277b4  lea     r8, aOnecoreVmCompu_36; "onecore\\vm\\compute\\management\\orche"...
0x1400277bb  mov     edx, 96Dh; void *
0x1400277c0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400277c6  or      eax, 10h
0x1400277c9  mov     [rbp+5E0h+var_620], eax
0x1400277cc  test    r8b, dl
0x1400277cf  jz      short loc_1400277D7
0x1400277d1  or      eax, 20h
0x1400277d4  mov     [rbp+5E0h+var_620], eax
0x1400277d7  test    dl, 2
0x1400277da  jz      short loc_1400277E2
0x1400277dc  or      eax, 40h
0x1400277df  mov     [rbp+5E0h+var_620], eax
0x1400277e2  test    dl, 4
0x1400277e5  jz      short loc_1400277EE
0x1400277e7  bts     eax, 7
0x1400277eb  mov     [rbp+5E0h+var_620], eax
0x1400277ee  mov     [rsp+6E0h+var_688], r14
0x1400277f3  lea     r13, [r15+270h]
0x1400277fa  lea     r9, [rbp+5E0h+var_620]
0x1400277fe  lea     r8, [rsp+6E0h+var_688]
0x140027803  mov     rcx, r13
0x140027806  call    ??$InvokeWorkerProcessMethod@UIVmVirtualMachine@@PEAUIVmSimpleTask@@W4__MIDL___MIDL_itf_vmwrkr_0000_0006_0005@@$$ZPEAU2@AEAW43@@Vmwp@ComputeService@@YAJAEBUWorkerProcessContext@01@P8IVmVirtualMachine@@EAAJPEAUIVmSimpleTask@@W4__MIDL___MIDL_itf_vmwrkr_0000_0006_0005@@@Z$$QEAPEAU4@AEAW45@@Z
0x14002780b  mov     rcx, [rbp+5E8h]; this
0x140027812  test    eax, eax
0x140027814  jns     loc_14002790D
0x14002781a  mov     r9d, eax; char *
0x14002781d  lea     r8, aOnecoreVmCompu_36; "onecore\\vm\\compute\\management\\orche"...
0x140027824  mov     edx, 983h; void *
0x140027829  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
