# ComputeService::Management::VmHostedContainer::ProcessManagement::ExecuteProcess(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::OrchestratorCallContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1400aa790`
- end: `0x1400ab194`
- name: `?ExecuteProcess@ProcessManagement@VmHostedContainer@Management@ComputeService@@UEAA?AUProcessInfo@34@AEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@UOrchestratorCallContext@34@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z`
- size: `2564`
- prototype: `ComputeService::Management::RetireServerOperation *__fastcall(__int64, ComputeService::Management::RetireServerOperation *, __int64 **, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `39`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x140005360`
- `0x140005384`
- `0x1400056fc`
- `0x140006098`
- `0x1400083bc`
- `0x140008760`
- `0x14000ea60`
- `0x14000f93c`
- `0x14001bfa4`
- `0x140029594`
- `0x14002cb24`
- `0x140034170`
- `0x140038dd4`
- `0x1400392a8`
- `0x1400393b8`
- `0x14003a318`
- `0x14003a9ac`
- `0x14003e278`
- `0x14003f1c4`
- `0x14003f374`
- `0x14003f5d0`
- `0x14003f698`
- `0x14003f850`
- `0x14003fa78`
- `0x14003ff0c`
- `0x1400a9830`
- `0x1400a9bdc`
- `0x1400aa3b0`
- `0x1400aa790`
- `0x1400ab278`
- `0x1400b8624`
- `0x1400ba5e8`
- `0x1400bf578`
- `0x1400dc6e8`
- `0x1400e0b10`
- `0x1400e6cf0`
- `0x1400edcc4`
- `0x1400f4eb8`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400aaeec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400aaeec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400aad45`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400aad45`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400aaecb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400aaecb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400aaeb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400aaeb8`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400aacad`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400aacad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400aac47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400aaec3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400aac47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400aaec3`

## string_xrefs

- `0x1400ab0bf`: `onecore\vm\compute\management\computeSystem\ComputeSystem.h`
- `0x1400ab0da`: `onecore\vm\compute\management\computeSystem\ComputeSystem.h`
- `0x1400ab0f2`: `onecore\vm\compute\management\computeSystem\ComputeSystem.h`
- `0x1400ab10a`: `onecore\vm\compute\management\computeSystem\ComputeSystem.h`
- `0x1400ab16d`: `onecore\vm\compute\management\computeSystem\ComputeSystem.h`
- `0x1400ab182`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\processmanagement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
ComputeService::Management::RetireServerOperation *__fastcall ComputeService::Management::VmHostedContainer::ProcessManagement::ExecuteProcess(
        __int64 a1,
        ComputeService::Management::RetireServerOperation *a2,
        __int64 **a3,
        __int64 a4,
        _QWORD *a5)
{
  _QWORD *v8; // rcx
  __int64 v9; // r15
  __int64 v10; // rdx
  __int64 v11; // r8
  RTL_SRWLOCK *v12; // rax
  PSRWLOCK v13; // r12
  _QWORD *v14; // rsi
  __int128 *v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // r14
  __int64 v18; // rcx
  PVOID Ptr; // rsi
  char IsHostProcessContainer; // al
  HANDLE v21; // rdi
  __int64 v22; // rbx
  LPHANDLE v23; // rax
  __int128 *v24; // rdx
  int started; // eax
  DWORD ProcessId; // ebx
  volatile signed __int32 *v27; // rbx
  RTL_SRWLOCK *v28; // r12
  PSRWLOCK v29; // r15
  char *inserted; // rsi
  _QWORD *v31; // rax
  PVOID v32; // rbx
  char *v33; // rax
  volatile signed __int32 *v34; // rbx
  void **v35; // r14
  void *v36; // r15
  DWORD LastError; // ebx
  __m128i si128; // xmm6
  volatile signed __int32 *v39; // rbx
  volatile signed __int32 *v40; // rbx
  __int64 v42; // rax
  __int64 v43; // rax
  unsigned int v44; // eax
  const char *v45; // rdx
  int v46; // [rsp+28h] [rbp-E0h]
  int v47; // [rsp+28h] [rbp-E0h]
  char v48; // [rsp+48h] [rbp-C0h]
  int v49; // [rsp+4Ch] [rbp-BCh]
  __int128 v50; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v51; // [rsp+68h] [rbp-A0h] BYREF
  HANDLE v52; // [rsp+78h] [rbp-90h] BYREF
  char v53; // [rsp+80h] [rbp-88h]
  int v54; // [rsp+81h] [rbp-87h]
  __int16 v55; // [rsp+85h] [rbp-83h]
  char v56; // [rsp+87h] [rbp-81h]
  HANDLE hObject[2]; // [rsp+88h] [rbp-80h] BYREF
  __int128 v58; // [rsp+98h] [rbp-70h] BYREF
  __int128 *v59; // [rsp+A8h] [rbp-60h]
  ComputeService::Management::RetireServerOperation *v60; // [rsp+B0h] [rbp-58h]
  _QWORD *v61; // [rsp+B8h] [rbp-50h]
  __int64 v62; // [rsp+C8h] [rbp-40h]
  __int64 v63; // [rsp+D0h] [rbp-38h]
  PSRWLOCK SRWLock; // [rsp+D8h] [rbp-30h]
  DWORD v65; // [rsp+E0h] [rbp-28h]
  __m256i v66; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v67; // [rsp+108h] [rbp+0h]
  __int64 v68; // [rsp+110h] [rbp+8h]
  _QWORD v69[2]; // [rsp+118h] [rbp+10h] BYREF
  __int128 v70; // [rsp+128h] [rbp+20h] BYREF
  __int64 v71; // [rsp+138h] [rbp+30h]
  unsigned __int64 v72; // [rsp+140h] [rbp+38h]
  __int128 v73; // [rsp+148h] [rbp+40h]
  __int128 v74; // [rsp+158h] [rbp+50h]
  __int128 v75; // [rsp+168h] [rbp+60h]
  __int64 v76; // [rsp+178h] [rbp+70h]
  int v77; // [rsp+180h] [rbp+78h]
  _BYTE v78[24]; // [rsp+188h] [rbp+80h] BYREF
  void *v79; // [rsp+1A0h] [rbp+98h] BYREF
  void *v80; // [rsp+1A8h] [rbp+A0h]
  int v81[2]; // [rsp+1B0h] [rbp+A8h]
  _OWORD v82[2]; // [rsp+1B8h] [rbp+B0h] BYREF
  __int128 v83; // [rsp+1D8h] [rbp+D0h] BYREF
  char v84[32]; // [rsp+1F8h] [rbp+F0h] BYREF
  _BYTE v85[32]; // [rsp+218h] [rbp+110h] BYREF
  char v86[32]; // [rsp+238h] [rbp+130h] BYREF
  char v87[24]; // [rsp+258h] [rbp+150h] BYREF
  _BYTE v88[16]; // [rsp+270h] [rbp+168h] BYREF
  __int64 v89; // [rsp+280h] [rbp+178h]
  char v90[32]; // [rsp+290h] [rbp+188h] BYREF
  _BYTE v91[40]; // [rsp+2B0h] [rbp+1A8h] BYREF
  _QWORD v92[42]; // [rsp+2D8h] [rbp+1D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+480h] [rbp+378h]

  v62 = a4;
  v60 = a2;
  v63 = a4;
  memset_0(v92, 0, sizeof(v92));
  v8 = (_QWORD *)(**a3 + 8);
  if ( *(_QWORD *)(**a3 + 32) > 7u )
    v8 = (_QWORD *)*v8;
  hObject[0] = v8;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v92,
    "VmHostedContainer_ExecuteProcess");
  v92[0] = &ComputeService::Diagnostics::TraceProvider::VmHostedContainer_ExecuteProcess::`vftable';
  ComputeService::Diagnostics::TraceProvider::VmHostedContainer_ExecuteProcess::StartActivity<unsigned short const *>(
    v92,
    hObject);
  v9 = **a3;
  if ( !v9 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computeSystem\\ComputeSystem.h",
      (const char *)0x80004001LL,
      v46);
  v10 = _RTDynamicCast_0(
          (*a3)[1],
          0,
          &ComputeService::Management::ComputeSystemState `RTTI Type Descriptor',
          &ComputeService::Management::BaseStateMachine `RTTI Type Descriptor');
  if ( !v10 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computeSystem\\ComputeSystem.h",
      (const char *)0x80004001LL,
      0);
  v69[0] = 0;
  *(_OWORD *)v66.m256i_i8 = *(_OWORD *)a4;
  *(_QWORD *)a4 = 0;
  *(_QWORD *)(a4 + 8) = 0;
  v60 = (ComputeService::Management::RetireServerOperation *)(a4 + 16);
  *(_OWORD *)&v66.m256i_u64[2] = *(_OWORD *)(a4 + 16);
  *(_QWORD *)(a4 + 16) = 0;
  *(_QWORD *)(a4 + 24) = 0;
  v67 = *(_QWORD *)(a4 + 32);
  v68 = *(_QWORD *)(a4 + 40);
  *(_QWORD *)(a4 + 32) = 0;
  *(_QWORD *)(a4 + 40) = 0;
  ComputeService::Management::BeginGenericOperation_InState(v69, v10, v11, &v66);
  v12 = (RTL_SRWLOCK *)_RTDynamicCast_0(
                         (*a3)[1],
                         0,
                         &ComputeService::Management::ComputeSystemState `RTTI Type Descriptor',
                         &ComputeService::Management::VmHostedProcessExecutionState `RTTI Type Descriptor');
  if ( !v12 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computeSystem\\ComputeSystem.h",
      (const char *)0x80004001LL,
      0);
  SRWLock = v12;
  v13 = (PSRWLOCK)_RTDynamicCast_0(
                    (*a3)[1],
                    0,
                    &ComputeService::Management::ComputeSystemState `RTTI Type Descriptor',
                    &ComputeService::Management::ServerContainerState `RTTI Type Descriptor');
  if ( !v13 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computeSystem\\ComputeSystem.h",
      (const char *)0x80004001LL,
      0);
  v70 = 0;
  v71 = 0;
  v72 = 7;
  LOWORD(v70) = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  if ( a5[3] <= 7u )
    v14 = a5;
  else
    v14 = (_QWORD *)*a5;
  memset_0(v82, 0, 0x60u);
  *(_QWORD *)&v50 = v14;
  *((_QWORD *)&v50 + 1) = a5[2];
  Marshal::JsonParser::JsonParser(v82, &v50);
  Marshal::FromJson<Config::Containers::VmHosted::ExecuteProcessSettings,>(&v66, v82, &v70);
  std::wstring::~wstring(v84);
  std::wstring::~wstring(&v83);
  if ( !v66.m256i_i8[0] )
  {
    v42 = std::shared_ptr<ComputeService::Management::ComputeSystem>::operator-><ComputeService::Management::ComputeSystem,0>(&v66.m256i_u64[1]);
    v43 = std::wstring::c_str(v42);
    v44 = wil::verify_hresult<long>(3224830221LL, v43);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x1F,
      (unsigned int)"OneCore\\Internal\\VM\\inc\\MarshalUtilities.h",
      (const char *)v44,
      (int)"%ls",
      v45);
  }
  std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&v66.m256i_u64[1]);
  Schema::Process::ProcessParameters::ProcessParameters((Schema::Process::ProcessParameters *)v85);
  v15 = &v70;
  if ( v72 > 7 )
    v15 = (__int128 *)v70;
  *(_QWORD *)&v50 = v15;
  *((_QWORD *)&v50 + 1) = v71;
  ComputeService::MarshalUtilities::FromJsonThrow<Schema::Process::ProcessParameters,>(&v50, v85);
  ComputeService::ContainerProcess::CreateStandardPipesForProcess(v78);
  v50 = 0;
  ComputeService::Management::CancellationProvider::CreateCancellationToken(*(_QWORD *)((*a3)[1] + 112), &v58);
  v59 = &v58;
  *(_OWORD *)&v66.m256i_u64[2] = 0;
  LOWORD(v67) = 0;
  *(GUID *)v66.m256i_i8 = HV_GUID_PARENT;
  *(_OWORD *)hObject = v58;
  v58 = 0;
  v82[0] = v73;
  v82[1] = v74;
  v83 = v75;
  ComputeService::Process::CreateProcessRelaySet(
    (unsigned int)&v50,
    (unsigned int)&v66,
    (unsigned int)v78,
    (unsigned int)v82,
    (__int64)hObject);
  v16 = *((_QWORD *)&v58 + 1);
  if ( *((_QWORD *)&v58 + 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v58 + 1) + 12LL), 0xFFFFFFFF) == 1 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
  }
  v17 = v50;
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v50 + 24LL))(v50);
  if ( v91[26] && *(_DWORD *)(v9 + 40) != 5 )
  {
    wil::init_once__lambda_9f8fc3345094d0460fc0841a96a6fc88___((LPINIT_ONCE)&SRWLock[4]);
    v13 = SRWLock + 3;
  }
  Ptr = v13->Ptr;
  IsHostProcessContainer = ComputeService::Management::VmHostedContainer::ProcessManagement::IsHostProcessContainer(
                             v18,
                             a3,
                             v9);
  v51 = 0;
  v21 = 0;
  v52 = 0;
  v48 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  if ( IsHostProcessContainer )
  {
    v22 = _RTDynamicCast_0(
            (*a3)[1],
            0,
            &ComputeService::Management::ComputeSystemState `RTTI Type Descriptor',
            &ComputeService::Management::SiloContainerState `RTTI Type Descriptor');
    if ( !v22 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"onecore\\vm\\compute\\management\\computeSystem\\ComputeSystem.h",
        (const char *)0x80004001LL,
        0);
    if ( !v89 )
      std::wstring::_Assign<unsigned short>(v88, L"NT AUTHORITY\\SYSTEM", 19);
    v23 = CExec::ExecuteProcess(
            hObject,
            (__int64)v85,
            v79,
            v80,
            *(HANDLE *)v81,
            (ConsoleToPipeRedirector *)(v22 + 536),
            *(_QWORD *)(v22 + 128));
    if ( &v52 != v23 )
    {
      v21 = *v23;
      v52 = *v23;
      *v23 = 0;
    }
    if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject[0]);
  }
  else
  {
    v52 = 0;
    v24 = &v70;
    if ( v72 > 7 )
      LODWORD(v24) = v70;
    started = ContainerStartProcess((_DWORD)Ptr, (_DWORD)v24, (_DWORD)v79, (_DWORD)v80, *(__int64 *)v81, (__int64)&v52);
    if ( started < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDA,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\processmanagement.cpp",
        (const char *)(unsigned int)started,
        v47);
    v48 = v53;
    v21 = v52;
  }
  ProcessId = GetProcessId(v21);
  v65 = ProcessId;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 32LL))(v17);
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v17 + 48LL))(v17) )
  {
    hObject[0] = *((HANDLE *)&v50 + 1);
    v50 = 0;
    *(_QWORD *)&v51 = v17;
    v27 = (volatile signed __int32 *)*((_QWORD *)&v51 + 1);
    *((HANDLE *)&v51 + 1) = hObject[0];
    if ( v27 )
    {
      if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
        if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
      }
    }
    ProcessId = v65;
  }
  else
  {
    hObject[0] = *((HANDLE *)&v51 + 1);
    v17 = v51;
  }
  v28 = SRWLock;
  AcquireSRWLockExclusive(SRWLock);
  *(_QWORD *)&v58 = v28;
  v29 = SRWLock + 1;
  inserted = (char *)SRWLock[1].Ptr;
  v61 = (_QWORD *)*((_QWORD *)inserted + 1);
  v49 = 0;
  v59 = 0;
  v31 = v61;
  while ( !*((_BYTE *)v31 + 25) )
  {
    v61 = v31;
    if ( *((_DWORD *)v31 + 8) >= ProcessId )
    {
      v49 = 1;
      inserted = (char *)v31;
      v31 = (_QWORD *)*v31;
    }
    else
    {
      v49 = 0;
      v31 = (_QWORD *)v31[2];
    }
  }
  if ( inserted[25] || ProcessId < *((_DWORD *)inserted + 8) )
  {
    if ( SRWLock[2].Ptr == (PVOID)0x38E38E38E38E38ELL )
      std::_Throw_tree_length_error();
    v32 = v29->Ptr;
    *(_OWORD *)v66.m256i_i8 = (unsigned __int64)v29;
    v33 = (char *)operator new(0x48u);
    *((_DWORD *)v33 + 8) = v65;
    *(_DWORD *)(v33 + 65) = 0;
    *(_WORD *)(v33 + 69) = 0;
    v33[71] = 0;
    *((_QWORD *)v33 + 5) = 0;
    *((_QWORD *)v33 + 6) = 0;
    *((_QWORD *)v33 + 7) = 0;
    v33[64] = 0;
    *(_QWORD *)v33 = v32;
    *((_QWORD *)v33 + 1) = v32;
    *((_QWORD *)v33 + 2) = v32;
    *((_WORD *)v33 + 12) = 0;
    *(_QWORD *)&v58 = v61;
    *((_QWORD *)&v58 + 1) = __PAIR64__((unsigned int)v59, v49);
    inserted = (char *)std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Schema::Responses::Service::PropertyResponse>>>::_Insert_node(
                         v29,
                         &v58);
  }
  v51 = 0;
  *((_QWORD *)inserted + 5) = v17;
  v34 = (volatile signed __int32 *)*((_QWORD *)inserted + 6);
  *((HANDLE *)inserted + 6) = hObject[0];
  if ( v34 )
  {
    if ( _InterlockedExchangeAdd(v34 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
      if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
    }
  }
  v35 = (void **)(inserted + 56);
  if ( inserted + 56 != (char *)&v52 )
  {
    v36 = *v35;
    if ( (char *)*v35 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CloseHandle(v36);
      SetLastError(LastError);
    }
    *v35 = v21;
    v52 = 0;
  }
  inserted[64] = v48;
  if ( v28 )
    ReleaseSRWLockExclusive(v28);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  *(__m128i *)&v66.m256i_u64[1] = si128;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v92,
    0);
  *(_DWORD *)a2 = v65;
  *((_QWORD *)a2 + 1) = v66.m256i_i64[1];
  *((_QWORD *)a2 + 2) = si128.m128i_i64[0];
  *((_QWORD *)a2 + 3) = -1;
  ComputeService::Management::ProcessState::~ProcessState((ComputeService::Management::ProcessState *)&v51);
  v39 = (volatile signed __int32 *)*((_QWORD *)&v50 + 1);
  if ( *((_QWORD *)&v50 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v50 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
      if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
    }
  }
  `eh vector destructor iterator'(
    &v79,
    8u,
    3u,
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
  `eh vector destructor iterator'(
    v78,
    8u,
    3u,
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
    v91,
    v91);
  std::wstring::~wstring(v90);
  std::wstring::~wstring(v88);
  std::vector<std::wstring>::_Tidy(v87);
  std::wstring::~wstring(v86);
  std::wstring::~wstring(v85);
  std::wstring::~wstring(&v70);
  std::unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>::~unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>(v69);
  v92[0] = &ComputeService::Diagnostics::TraceProvider::VmHostedContainer_ExecuteProcess::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v92);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(v92);
  ComputeService::Management::RetireServerOperation::~RetireServerOperation(v60);
  v40 = *(volatile signed __int32 **)(v62 + 8);
  if ( v40 )
  {
    if ( _InterlockedExchangeAdd(v40 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
      if ( _InterlockedExchangeAdd(v40 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1400aa790  mov     rax, rsp
0x1400aa793  mov     [rax+8], rbx
0x1400aa797  mov     [rax+20h], r9
0x1400aa79b  mov     [rax+10h], rdx
0x1400aa79f  push    rbp
0x1400aa7a0  push    rsi
0x1400aa7a1  push    rdi
0x1400aa7a2  push    r12
0x1400aa7a4  push    r13
0x1400aa7a6  push    r14
0x1400aa7a8  push    r15
0x1400aa7aa  lea     rbp, [rax-378h]
0x1400aa7b1  sub     rsp, 440h
0x1400aa7b8  movaps  xmmword ptr [rax-48h], xmm6
0x1400aa7bc  mov     rax, cs:__security_cookie
0x1400aa7c3  xor     rax, rsp
0x1400aa7c6  mov     [rbp+370h+var_50], rax
0x1400aa7cd  mov     rdi, r9
0x1400aa7d0  mov     [rbp+370h+var_3B0], r9
0x1400aa7d4  mov     rbx, r8
0x1400aa7d7  mov     r13, rdx
0x1400aa7da  mov     [rbp+370h+var_3C8], rdx
0x1400aa7de  mov     [rbp+370h+var_3A8], r9
0x1400aa7e2  xor     r14d, r14d
0x1400aa7e5  xor     edx, edx; Val
0x1400aa7e7  mov     r8d, 150h; Size
0x1400aa7ed  lea     rcx, [rbp+370h+var_1A0]; void *
0x1400aa7f4  call    memset_0
0x1400aa7f9  mov     rax, [rbx]
0x1400aa7fc  mov     rcx, [rax]
0x1400aa7ff  add     rcx, 8
0x1400aa803  cmp     qword ptr [rcx+18h], 7
0x1400aa808  jbe     short loc_1400AA80D
0x1400aa80a  mov     rcx, [rcx]
0x1400aa80d  mov     [rbp+370h+hObject], rcx
0x1400aa811  lea     rdx, aVmhostedcontai_5; "VmHostedContainer_ExecuteProcess"
0x1400aa818  lea     rcx, [rbp+370h+var_1A0]
0x1400aa81f  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400aa824  lea     rax, ??_7VmHostedContainer_ExecuteProcess@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::VmHostedContainer_ExecuteProcess::`vftable'
0x1400aa82b  mov     [rbp+370h+var_1A0], rax
0x1400aa832  lea     rdx, [rbp+370h+hObject]
0x1400aa836  lea     rcx, [rbp+370h+var_1A0]
0x1400aa83d  call    ??$StartActivity@PEBG@VmHostedContainer_ExecuteProcess@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEBG@Z; ComputeService::Diagnostics::TraceProvider::VmHostedContainer_ExecuteProcess::StartActivity<ushort const *>(ushort const * &&)
0x1400aa842  nop
0x1400aa843  mov     rcx, [rbx]
0x1400aa846  mov     r15, [rcx]
0x1400aa849  mov     rax, [rbp+378h]
0x1400aa850  test    r15, r15
0x1400aa853  jz      loc_1400AB0B9
0x1400aa859  mov     [rsp+470h+var_450], r14d; int
0x1400aa85e  lea     r9, ??_R0?AUBaseStateMachine@Management@ComputeService@@@8; ComputeService::Management::BaseStateMachine `RTTI Type Descriptor'
0x1400aa865  lea     rsi, ??_R0?AUComputeSystemState@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemState `RTTI Type Descriptor'
0x1400aa86c  mov     r8, rsi
0x1400aa86f  xor     edx, edx
0x1400aa871  mov     rcx, [rcx+8]
0x1400aa875  call    __RTDynamicCast_0
0x1400aa87a  mov     rdx, rax
0x1400aa87d  mov     rcx, [rbp+378h]; this
0x1400aa884  test    rax, rax
0x1400aa887  jz      loc_1400AB0D4
0x1400aa88d  mov     [rbp+370h+var_360], r14
0x1400aa891  mov     rax, [rdi]
0x1400aa894  mov     qword ptr [rbp+370h+var_390], rax
0x1400aa898  mov     rax, [rdi+8]
0x1400aa89c  mov     qword ptr [rbp+370h+var_390+8], rax
0x1400aa8a0  mov     [rdi], r14
0x1400aa8a3  mov     [rdi+8], r14
0x1400aa8a7  lea     rcx, [rdi+10h]
0x1400aa8ab  mov     [rbp+370h+var_3C8], rcx
0x1400aa8af  mov     rax, [rcx]
0x1400aa8b2  mov     qword ptr [rbp+370h+var_380], rax
0x1400aa8b6  mov     rax, [rcx+8]
0x1400aa8ba  mov     qword ptr [rbp+370h+var_380+8], rax
0x1400aa8be  mov     [rcx], r14
0x1400aa8c1  mov     [rcx+8], r14
0x1400aa8c5  mov     rax, [rcx+10h]
0x1400aa8c9  mov     [rbp+370h+var_370], rax
0x1400aa8cd  mov     rax, [rcx+18h]
0x1400aa8d1  mov     [rbp+370h+var_368], rax
0x1400aa8d5  mov     [rcx+10h], r14
0x1400aa8d9  mov     [rcx+18h], r14
0x1400aa8dd  lea     r9, [rbp+370h+var_390]
0x1400aa8e1  lea     rcx, [rbp+370h+var_360]
0x1400aa8e5  call    ?BeginGenericOperation_InState@Management@ComputeService@@YA?AVActiveStateOperation@12@PEAUBaseStateMachine@12@W4SystemState@12@VActiveServerOperation@12@@Z; ComputeService::Management::BeginGenericOperation_InState(ComputeService::Management::BaseStateMachine *,ComputeService::Management::SystemState,ComputeService::Management::ActiveServerOperation)
0x1400aa8ea  nop
0x1400aa8eb  mov     rcx, [rbx]
0x1400aa8ee  mov     [rsp+470h+var_450], r14d; int
0x1400aa8f3  lea     r9, ??_R0?AUVmHostedProcessExecutionState@Management@ComputeService@@@8; ComputeService::Management::VmHostedProcessExecutionState `RTTI Type Descriptor'
0x1400aa8fa  mov     r8, rsi
0x1400aa8fd  xor     edx, edx
0x1400aa8ff  mov     rcx, [rcx+8]
0x1400aa903  call    __RTDynamicCast_0
0x1400aa908  mov     rcx, [rbp+378h]; this
0x1400aa90f  test    rax, rax
0x1400aa912  jz      loc_1400AB0EC
0x1400aa918  mov     [rbp+370h+SRWLock], rax
0x1400aa91c  mov     rcx, [rbx]
0x1400aa91f  mov     [rsp+470h+var_450], r14d; int
0x1400aa924  lea     r9, ??_R0?AUServerContainerState@Management@ComputeService@@@8; ComputeService::Management::ServerContainerState `RTTI Type Descriptor'
0x1400aa92b  mov     r8, rsi
0x1400aa92e  xor     edx, edx
0x1400aa930  mov     rcx, [rcx+8]
0x1400aa934  call    __RTDynamicCast_0
0x1400aa939  mov     r12, rax
0x1400aa93c  mov     rcx, [rbp+378h]; this
0x1400aa943  test    rax, rax
0x1400aa946  jz      loc_1400AB104
0x1400aa94c  xorps   xmm0, xmm0
0x1400aa94f  movups  [rbp+370h+var_350], xmm0
0x1400aa953  mov     [rbp+370h+var_340], r14
0x1400aa957  mov     [rbp+370h+var_338], 7
0x1400aa95f  mov     word ptr [rbp+370h+var_350], r14w
0x1400aa964  movups  [rbp+370h+var_330], xmm0
0x1400aa968  xorps   xmm1, xmm1
0x1400aa96b  movups  [rbp+370h+var_320], xmm1
0x1400aa96f  movups  [rbp+370h+var_310], xmm0
0x1400aa973  mov     [rbp+370h+var_300], r14
0x1400aa977  mov     [rbp+370h+var_2F8], r14d
0x1400aa97b  mov     rdi, [rbp+370h+arg_20]
0x1400aa982  cmp     qword ptr [rdi+18h], 7
0x1400aa987  jbe     short loc_1400AA98E
0x1400aa989  mov     rsi, [rdi]
0x1400aa98c  jmp     short loc_1400AA991
0x1400aa98e  mov     rsi, rdi
0x1400aa991  xor     edx, edx; Val
0x1400aa993  lea     r8d, [rdx+60h]; Size
0x1400aa997  lea     rcx, [rbp+370h+var_2C0]; void *
0x1400aa99e  call    memset_0
0x1400aa9a3  mov     qword ptr [rsp+470h+var_428+8], rsi
0x1400aa9a8  mov     rax, [rdi+10h]
0x1400aa9ac  mov     qword ptr [rsp+470h+var_418], rax
0x1400aa9b1  lea     rdx, [rsp+470h+var_428+8]
0x1400aa9b6  lea     rcx, [rbp+370h+var_2C0]
0x1400aa9bd  call    ??0JsonParser@Marshal@@QEAA@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; Marshal::JsonParser::JsonParser(std::basic_string_view<ushort>)
0x1400aa9c2  nop
0x1400aa9c3  lea     r8, [rbp+370h+var_350]
0x1400aa9c7  lea     rdx, [rbp+370h+var_2C0]
0x1400aa9ce  lea     rcx, [rbp+370h+var_390]
0x1400aa9d2  call    ??$FromJson@UExecuteProcessSettings@VmHosted@Containers@Config@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@AEAVJsonParser@0@PEAUExecuteProcessSettings@VmHosted@Containers@Config@@W4UnmarshalFlags@0@@Z; Marshal::FromJson<Config::Containers::VmHosted::ExecuteProcessSettings,>(Marshal::JsonParser &,Config::Containers::VmHosted::ExecuteProcessSettings *,Marshal::UnmarshalFlags)
0x1400aa9d7  nop
0x1400aa9d8  lea     rcx, [rbp+370h+var_280]; void *
0x1400aa9df  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400aa9e4  lea     rcx, [rbp+370h+var_2A0]; void *
0x1400aa9eb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400aa9f0  nop
0x1400aa9f1  cmp     byte ptr [rbp+370h+var_390], r14b
0x1400aa9f5  jz      loc_1400AB11C
0x1400aa9fb  lea     rcx, [rbp+370h+var_390+8]
0x1400aa9ff  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x1400aaa04  lea     rcx, [rbp+370h+var_260]; this
0x1400aaa0b  call    ??0ProcessParameters@Process@Schema@@QEAA@XZ; Schema::Process::ProcessParameters::ProcessParameters(void)
0x1400aaa10  nop
0x1400aaa11  lea     rcx, [rbp+370h+var_350]
0x1400aaa15  cmp     [rbp+370h+var_338], 7
0x1400aaa1a  cmova   rcx, qword ptr [rbp+370h+var_350]
0x1400aaa1f  mov     rax, [rbp+370h+var_340]
0x1400aaa23  mov     qword ptr [rsp+470h+var_428+8], rcx
0x1400aaa28  mov     qword ptr [rsp+470h+var_418], rax
0x1400aaa2d  lea     rdx, [rbp+370h+var_260]
0x1400aaa34  lea     rcx, [rsp+470h+var_428+8]
0x1400aaa39  call    ??$FromJsonThrow@UProcessParameters@Process@Schema@@$$V@MarshalUtilities@ComputeService@@YAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAUProcessParameters@Process@Schema@@W4UnmarshalFlags@Marshal@@@Z; ComputeService::MarshalUtilities::FromJsonThrow<Schema::Process::ProcessParameters,>(std::basic_string_view<ushort>,Schema::Process::ProcessParameters *,Marshal::UnmarshalFlags)
0x1400aaa3e  lea     rdx, [rbp+370h+var_350]
0x1400aaa42  lea     rcx, [rbp+370h+var_2F0]; void *
0x1400aaa49  call    ?CreateStandardPipesForProcess@ContainerProcess@ComputeService@@YA?AU?$pair@V?$array@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$02@std@@V12@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@_N@Z; ComputeService::ContainerProcess::CreateStandardPipesForProcess(std::wstring const &,bool)
0x1400aaa4e  nop
0x1400aaa4f  xorps   xmm0, xmm0
0x1400aaa52  movups  [rsp+470h+var_428+8], xmm0
0x1400aaa57  mov     rax, [rbx]
0x1400aaa5a  mov     rcx, [rax+8]
0x1400aaa5e  lea     rdx, [rbp+370h+var_3E0]
0x1400aaa62  mov     rcx, [rcx+70h]
0x1400aaa66  call    ?CreateCancellationToken@CancellationProvider@Management@ComputeService@@QEAA?AVCancellationToken@23@XZ; ComputeService::Management::CancellationProvider::CreateCancellationToken(void)
0x1400aaa6b  lea     rax, [rbp+370h+var_3E0]
0x1400aaa6f  mov     [rbp+370h+var_3D0], rax
0x1400aaa73  xorps   xmm0, xmm0
0x1400aaa76  movups  [rbp+370h+var_380], xmm0
0x1400aaa7a  mov     word ptr [rbp+370h+var_370], r14w
0x1400aaa7f  movups  xmm1, xmmword ptr cs:HV_GUID_PARENT.Data1
0x1400aaa86  movdqu  [rbp+370h+var_390], xmm1
0x1400aaa8b  movaps  xmm0, [rbp+370h+var_3E0]
0x1400aaa8f  movdqa  xmmword ptr [rbp+370h+hObject], xmm0
0x1400aaa94  xorps   xmm1, xmm1
0x1400aaa97  movdqa  [rbp+370h+var_3E0], xmm1
0x1400aaa9c  movaps  xmm0, [rbp+370h+var_330]
0x1400aaaa0  movaps  [rbp+370h+var_2C0], xmm0
0x1400aaaa7  movaps  xmm1, [rbp+370h+var_320]
0x1400aaaab  movaps  [rbp+370h+var_2B0], xmm1
0x1400aaab2  movaps  xmm0, [rbp+370h+var_310]
0x1400aaab6  movaps  [rbp+370h+var_2A0], xmm0
0x1400aaabd  lea     rax, [rbp+370h+hObject]
0x1400aaac1  mov     qword ptr [rsp+470h+var_450], rax
0x1400aaac6  lea     r9, [rbp+370h+var_2C0]
0x1400aaacd  lea     r8, [rbp+370h+var_2F0]
0x1400aaad4  lea     rdx, [rbp+370h+var_390]
0x1400aaad8  lea     rcx, [rsp+470h+var_428+8]
0x1400aaadd  call    ?CreateProcessRelaySet@Process@ComputeService@@YA?AV?$shared_ptr@VIProcessRelaySet@Process@ComputeService@@@std@@AEAUBridgeRelayProperties@Communication@2@$$QEAV?$array@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$02@4@UExecuteProcessStdioRelaySettings@VmHosted@Containers@Config@@VCancellationToken@Management@2@@Z; ComputeService::Process::CreateProcessRelaySet(ComputeService::Communication::BridgeRelayProperties &,std::array<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,3> &&,Config::Containers::VmHosted::ExecuteProcessStdioRelaySettings,ComputeService::Management::CancellationToken)
0x1400aaae2  nop
0x1400aaae3  mov     rcx, qword ptr [rbp+370h+var_3E0+8]
0x1400aaae7  test    rcx, rcx
0x1400aaaea  jz      short loc_1400AAB06
0x1400aaaec  or      eax, 0FFFFFFFFh
0x1400aaaef  lock xadd [rcx+0Ch], eax
0x1400aaaf4  cmp     eax, 1
0x1400aaaf7  jnz     short loc_1400AAB06
0x1400aaaf9  mov     rax, [rcx]
0x1400aaafc  mov     rax, [rax+8]
0x1400aab00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400aab05  nop
0x1400aab06  mov     r14, qword ptr [rsp+470h+var_428+8]
0x1400aab0b  mov     rax, [r14]
0x1400aab0e  mov     rcx, r14
0x1400aab11  mov     rax, [rax+18h]
0x1400aab15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400aab1a  cmp     [rbp+370h+var_1AE], 0
0x1400aab21  jz      short loc_1400AAB43
0x1400aab23  cmp     dword ptr [r15+28h], 5
0x1400aab28  jz      short loc_1400AAB43
0x1400aab2a  mov     rcx, [rbp+370h+SRWLock]
0x1400aab2e  add     rcx, 20h ; ' '; lpInitOnce
0x1400aab32  lea     rdx, [rbp+370h+SRWLock]
0x1400aab36  call    wil__init_once__lambda_9f8fc3345094d0460fc0841a96a6fc88___
0x1400aab3b  mov     r12, [rbp+370h+SRWLock]
0x1400aab3f  add     r12, 18h
0x1400aab43  mov     rsi, [r12]
0x1400aab47  mov     r8, r15
0x1400aab4a  mov     rdx, rbx
0x1400aab4d  call    ?IsHostProcessContainer@ProcessManagement@VmHostedContainer@Management@ComputeService@@AEAA_NAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@PEBUComputeSystemConfiguration@34@@Z; ComputeService::Management::VmHostedContainer::ProcessManagement::IsHostProcessContainer(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::ComputeSystemConfiguration const *)
0x1400aab52  xorps   xmm1, xmm1
0x1400aab55  movdqu  [rsp+470h+var_418+8], xmm1
0x1400aab5b  xor     r12d, r12d
0x1400aab5e  mov     edi, r12d
0x1400aab61  mov     [rsp+470h+var_400], r12
0x1400aab66  mov     [rsp+470h+var_430], r12b
0x1400aab6b  mov     [rsp+470h+var_3F8], r12b
0x1400aab70  xor     ecx, ecx
0x1400aab72  mov     [rsp+470h+var_3F7], ecx
0x1400aab76  mov     [rsp+470h+var_3F3], cx
0x1400aab7b  mov     [rsp+470h+var_3F1], cl
0x1400aab7f  test    al, al
0x1400aab81  jz      loc_1400AAC4F
0x1400aab87  mov     rcx, [rbx]
0x1400aab8a  mov     [rsp+470h+var_450], r12d; int
0x1400aab8f  lea     r9, ??_R0?AUSiloContainerState@Management@ComputeService@@@8; ComputeService::Management::SiloContainerState `RTTI Type Descriptor'
0x1400aab96  lea     r8, ??_R0?AUComputeSystemState@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemState `RTTI Type Descriptor'
0x1400aab9d  xor     edx, edx
0x1400aab9f  mov     rcx, [rcx+8]
0x1400aaba3  call    __RTDynamicCast_0
0x1400aaba8  mov     rbx, rax
0x1400aabab  mov     rcx, [rbp+378h]; this
0x1400aabb2  test    rax, rax
0x1400aabb5  jz      loc_1400AB167
0x1400aabbb  cmp     [rbp+370h+var_1F8], r12
0x1400aabc2  jnz     short loc_1400AABDC
0x1400aabc4  lea     r8d, [r12+13h]
0x1400aabc9  lea     rdx, aNtAuthoritySys; "NT AUTHORITY\\SYSTEM"
0x1400aabd0  lea     rcx, [rbp+370h+var_208]
0x1400aabd7  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1400aabdc  lea     rcx, [rbx+218h]
0x1400aabe3  mov     rax, [rbx+80h]
0x1400aabea  mov     [rsp+470h+var_440], rax
0x1400aabef  mov     [rsp+470h+var_448], rcx
0x1400aabf4  mov     rax, qword ptr [rbp+370h+var_2C8]
0x1400aabfb  mov     qword ptr [rsp+470h+var_450], rax
0x1400aac00  mov     r9, [rbp+370h+var_2D0]
0x1400aac07  mov     r8, [rbp+370h+var_2D8]
0x1400aac0e  lea     rdx, [rbp+370h+var_260]
0x1400aac15  lea     rcx, [rbp+370h+hObject]
0x1400aac19  call    ?ExecuteProcess@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBUProcessParameters@Process@Schema@@PEAX11AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; CExec::ExecuteProcess(Schema::Process::ProcessParameters const &,void *,void *,void *,std::wstring const &,void *)
0x1400aac1e  mov     rsi, rax
0x1400aac21  lea     rax, [rsp+470h+var_400]
0x1400aac26  cmp     rax, rsi
0x1400aac29  jz      short loc_1400AAC39
0x1400aac2b  mov     r15, [rsi]
0x1400aac2e  mov     rdi, r15
0x1400aac31  mov     [rsp+470h+var_400], r15
0x1400aac36  mov     [rsi], r12
0x1400aac39  mov     rcx, [rbp+370h+hObject]; hObject
0x1400aac3d  lea     rax, [rcx-1]
0x1400aac41  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400aac45  ja      short loc_1400AACAA
0x1400aac47  call    cs:__imp_CloseHandle
0x1400aac4d  jmp     short loc_1400AACAA
0x1400aac4f  mov     [rsp+470h+var_400], r12
0x1400aac54  mov     rax, qword ptr [rbp+370h+var_2C8]
0x1400aac5b  lea     rdx, [rbp+370h+var_350]
0x1400aac5f  cmp     [rbp+370h+var_338], 7
0x1400aac64  cmova   rdx, qword ptr [rbp+370h+var_350]
0x1400aac69  lea     rcx, [rsp+470h+var_400]
0x1400aac6e  mov     [rsp+470h+var_448], rcx
0x1400aac73  mov     qword ptr [rsp+470h+var_450], rax; int
0x1400aac78  mov     r9, [rbp+370h+var_2D0]
0x1400aac7f  mov     r8, [rbp+370h+var_2D8]
0x1400aac86  mov     rcx, rsi
0x1400aac89  call    ContainerStartProcess
0x1400aac8e  mov     rcx, [rbp+378h]; this
0x1400aac95  test    eax, eax
0x1400aac97  js      loc_1400AB17F
0x1400aac9d  mov     al, [rsp+470h+var_3F8]
0x1400aaca1  mov     [rsp+470h+var_430], al
0x1400aaca5  mov     rdi, [rsp+470h+var_400]
  ... truncated ...
```
