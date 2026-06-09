# WorkerTaskStarting::RunRestoreStartSteps(void)

- ea: `0x1400c2b6c`
- end: `0x1400c3f9f`
- name: `?RunRestoreStartSteps@WorkerTaskStarting@@AEAAJXZ`
- size: `5171`
- prototype: `__int64 __fastcall(WorkerTaskStarting *__hidden this)`
- caller_count: `1`
- callee_count: `68`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14016cc50`

## callees

- `0x14001ec28`
- `0x140022290`
- `0x140032620`
- `0x1400364a0`
- `0x14003b720`
- `0x14003b7c0`
- `0x14003cc30`
- `0x14003d828`
- `0x140053de8`
- `0x140053f10`
- `0x1400545bc`
- `0x140055e18`
- `0x140056b38`
- `0x14005c320`
- `0x14005c4b8`
- `0x14005e524`
- `0x14005e6e8`
- `0x14005eb6c`
- `0x14005ec10`
- `0x14005fff4`
- `0x140066eec`
- `0x14006da84`
- `0x1400a5d70`
- `0x1400b1890`
- `0x1400b3318`
- `0x1400b9090`
- `0x1400bbfe4`
- `0x1400bc078`
- `0x1400bc420`
- `0x1400c2b6c`
- `0x1400c4940`
- `0x1400c4b40`
- `0x1400c4d90`
- `0x1400c4e80`
- `0x1400c4fe8`
- `0x1400cf1dc`
- `0x1400e7314`
- `0x1400e9cb4`
- `0x140102580`
- `0x1401090a8`
- `0x140110314`
- `0x14011ea40`
- `0x14011ee30`
- `0x14011f6fc`
- `0x140138ce8`
- `0x14014e438`
- `0x1401536f0`
- `0x140158c5c`
- `0x14015ea30`
- `0x14016b464`

## import_xrefs

- `vid!VidTrimPartitionMemory` at `0x1400c3cd0`
- `vid!VidTrimPartitionMemory` at `0x1400c3cd0`

## string_xrefs

- `0x1400c31db`: `onecore\vm\worker\wpcore\workertaskstarting.cpp`
- `0x1400c39e5`: `onecore\vm\worker\wpcore\workertaskstarting.cpp`
- `0x1400c3b45`: `onecore\vm\worker\wpcore\workertaskstarting.cpp`
- `0x1400c35d7`: `EnableAllZeroBufferWrite`
- `0x1400c2d92`: `ConfigReadFail:%ld`
- `0x1400c2cf2`: `'WorkerTaskStarting::RunRestoreStartSteps': Failed to call '%hs'; hr=0x%08X\n`
- `0x1400c2eba`: `'WorkerTaskStarting::RunRestoreStartSteps': Failed to call '%hs'; hr=0x%08X\n`
- `0x1400c2fda`: `'WorkerTaskStarting::RunRestoreStartSteps': Failed to call '%hs'; hr=0x%08X\n`
- `0x1400c2ceb`: `Failed to create version manager`

## pseudocode

```c
// Hidden C++ exception states: #wind=26 #try_helpers=1
__int64 __fastcall WorkerTaskStarting::RunRestoreStartSteps(WorkerTaskStarting *this, __int64 a2)
{
  _DWORD *v3; // r13
  __int64 v4; // rdx
  __int64 v5; // rdx
  VirtualMachine **v6; // r14
  int started; // edi
  __int64 SavedStateRepositoryForRestore; // rax
  struct VmRepository *v9; // rbx
  int v10; // eax
  VmPrefixRepository *v11; // rax
  const unsigned __int16 *v12; // r8
  VmPrefixRepository *v13; // r15
  __int128 *v14; // rax
  VirtualMachine *v15; // rcx
  unsigned __int64 v16; // rbx
  char v17; // al
  unsigned int v18; // r12d
  VirtualMachine *v19; // rdx
  __int64 v20; // rcx
  unsigned int v21; // ecx
  wil *v22; // rcx
  int v23; // eax
  wil *v24; // rcx
  VirtualMachine *v25; // r13
  __int64 v26; // rdi
  int v27; // r12d
  WorkerTaskStarting *v28; // rbx
  unsigned int v29; // edi
  WorkerTaskStarting *v30; // r13
  int v31; // eax
  unsigned int v32; // ebx
  VirtualMachine *v33; // rcx
  int v34; // eax
  VirtualMachine *v35; // rcx
  int v36; // eax
  int v37; // eax
  unsigned int v38; // r9d
  int v39; // eax
  int v40; // eax
  VirtualMachine *v41; // rdi
  __int64 v42; // rbx
  int v43; // eax
  VirtualMachine *v44; // rdi
  __int64 v45; // rbx
  int v46; // eax
  __int64 v47; // rdi
  __int64 v48; // r15
  __int64 (__fastcall *v49)(__int64, __int64, __int64, _QWORD); // r13
  unsigned int v50; // ebx
  __int64 v51; // r12
  __int64 v52; // rax
  int v53; // eax
  int v54; // eax
  __int64 v55; // rax
  VirtualMachine *v56; // r15
  __int64 v57; // rbx
  const char *v58; // r9
  __int64 v59; // rdx
  VirtualMachine *v60; // r8
  int v62; // [rsp+20h] [rbp-508h]
  unsigned __int64 RamSizeInPages; // [rsp+30h] [rbp-4F8h]
  int v64; // [rsp+50h] [rbp-4D8h]
  __int64 v66; // [rsp+68h] [rbp-4C0h] BYREF
  __int64 v67; // [rsp+70h] [rbp-4B8h] BYREF
  char v68; // [rsp+78h] [rbp-4B0h]
  int v69; // [rsp+7Ch] [rbp-4ACh]
  int v70; // [rsp+80h] [rbp-4A8h]
  int v71; // [rsp+84h] [rbp-4A4h]
  __int64 v72; // [rsp+88h] [rbp-4A0h] BYREF
  VirtualMachine **v73; // [rsp+90h] [rbp-498h]
  __int64 VmName; // [rsp+98h] [rbp-490h] BYREF
  struct VmRepository *v75; // [rsp+A0h] [rbp-488h] BYREF
  struct IVersionManager *v76; // [rsp+A8h] [rbp-480h] BYREF
  VmPrefixRepository *v77; // [rsp+B0h] [rbp-478h] BYREF
  _BYTE v78[336]; // [rsp+C0h] [rbp-468h] BYREF
  unsigned int v79[2]; // [rsp+210h] [rbp-318h] BYREF
  int v80; // [rsp+218h] [rbp-310h] BYREF
  unsigned int v81; // [rsp+21Ch] [rbp-30Ch] BYREF
  HKEY phkResult; // [rsp+220h] [rbp-308h] BYREF
  __int128 v83; // [rsp+228h] [rbp-300h] BYREF
  __m128i si128; // [rsp+238h] [rbp-2F0h]
  _OWORD v85[2]; // [rsp+248h] [rbp-2E0h] BYREF
  _QWORD v86[42]; // [rsp+270h] [rbp-2B8h] BYREF
  _QWORD v87[23]; // [rsp+3C0h] [rbp-168h] BYREF
  int v88; // [rsp+478h] [rbp-B0h]
  unsigned int v89; // [rsp+488h] [rbp-A0h]
  int v90; // [rsp+494h] [rbp-94h]
  __int64 v91[4]; // [rsp+4B0h] [rbp-78h] BYREF
  __int64 v92[4]; // [rsp+4D0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+0h]

  v72 = (__int64)this;
  LODWORD(v67) = 0;
  v3 = (_DWORD *)((char *)this + 404);
  v66 = (__int64)this + 404;
  LOBYTE(a2) = *((_BYTE *)this + 404) & 1;
  WorkerAsyncTask<VmWorkerTrace::StartingTask>::LogFlag(this, a2, L"VmPhu");
  v4 = *v3 >> 2;
  LOBYTE(v4) = (*v3 & 4) != 0;
  WorkerAsyncTask<VmWorkerTrace::StartingTask>::LogFlag(this, v4, L"DisableFlushes");
  v5 = *v3 >> 4;
  LOBYTE(v5) = (*v3 & 0x10) != 0;
  WorkerAsyncTask<VmWorkerTrace::StartingTask>::LogFlag(this, v5, L"HandleTransfer");
  v71 = 0;
  v69 = 0;
  LODWORD(phkResult) = 0;
  v70 = 0;
  v80 = 0;
  memset_0(v87, 0, 0xF0u);
  GmoRamOperation::GmoRamOperation((GmoRamOperation *)v87);
  v87[0] = &GmoRamOperationRestore::`vftable';
  v77 = 0;
  v76 = 0;
  v85[0] = 0;
  v85[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v85[0]) = 0;
  v75 = 0;
  v6 = (VirtualMachine **)((char *)this + 16);
  v73 = (VirtualMachine **)((char *)this + 16);
  (*(void (__fastcall **)(_QWORD, int *))(**(_QWORD **)(*((_QWORD *)this + 2) + 1072LL) + 112LL))(
    *(_QWORD *)(*((_QWORD *)this + 2) + 1072LL),
    &v80);
  started = VersionManagerDefaultFactory::CreateVersionManagerInstance(&v76);
  v64 = started;
  if ( started < 0 )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
      VmlDebugTrace(
        16416,
        L"'WorkerTaskStarting::RunRestoreStartSteps': Failed to call '%hs'; hr=0x%08X\n",
        "Failed to create version manager",
        (unsigned int)started);
    goto LABEL_126;
  }
  SavedStateRepositoryForRestore = VirtualMachine::GetSavedStateRepositoryForRestore(
                                     *v6,
                                     v79,
                                     *(unsigned int *)(*((_QWORD *)*v6 + 177) + 108LL));
  Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::operator=(&v75, SavedStateRepositoryForRestore);
  Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(v79);
  v83 = 0;
  v9 = v75;
  VmRepositoryAutoLock::VmRepositoryAutoLock(&v83, v75, 0);
  if ( (SDWORD2(v83) & 0x80000000) == 0 )
  {
    v10 = (*(__int64 (__fastcall **)(struct VmRepository *, const unsigned __int16 *, _OWORD *))(*(_QWORD *)v9 + 104LL))(
            v9,
            L"/savedstate/VmwpVersion",
            v85);
    if ( v10 < 0 )
      Vml::FormatString(v85, L"ConfigReadFail:%ld", (unsigned int)v10);
    started = 0;
    v64 = 0;
  }
  VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)&v83);
  v11 = (VmPrefixRepository *)operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
  VmName = (__int64)v11;
  if ( v11 )
    v13 = VmPrefixRepository::VmPrefixRepository(v11, v9, v12);
  else
    v13 = 0;
  if ( !v13 )
  {
    v77 = 0;
    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
      VmlDebugTrace(16416, L"Failed to allocate prefix repository!\n");
    goto LABEL_126;
  }
  Vml::VmSharableObject::IncrementUserCount((VmPrefixRepository *)((char *)v13 + 8));
  v77 = v13;
  v81 = 0;
  v83 = 0;
  VmRepositoryAutoLock::VmRepositoryAutoLock(&v83, v9, 1);
  started = DWORD2(v83);
  if ( SDWORD2(v83) < 0 )
  {
    v64 = DWORD2(v83);
    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
      VmlDebugTraceWithError(16416, &off_1402E3010, (unsigned int)started);
LABEL_15:
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)&v83);
LABEL_126:
    v28 = this;
    goto LABEL_127;
  }
  *(_QWORD *)v79 = 0;
  started = (*(__int64 (__fastcall **)(struct VmRepository *, const unsigned __int16 *, unsigned int *))(*(_QWORD *)v9 + 112LL))(
              v9,
              L"/savedstate/VmVersion",
              v79);
  v64 = started;
  if ( started < 0 )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
      VmlDebugTrace(
        16416,
        L"'WorkerTaskStarting::RunRestoreStartSteps': Failed to call '%hs'; hr=0x%08X\n",
        "Failed to get saved state VmVersion",
        (unsigned int)started);
    goto LABEL_15;
  }
  v81 = v79[0];
  VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)&v83);
  if ( !(**(unsigned __int8 (__fastcall ***)(struct IVersionManager *, unsigned int *))v76)(v76, &v81) )
  {
    v83 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v83) = 0;
    GetVmVersionString(v81, &v83);
    v14 = &v83;
    if ( si128.m128i_i64[1] > 7uLL )
      v14 = (__int128 *)v83;
    v72 = (__int64)v14;
    v15 = *v6;
    v66 = (__int64)*v6 + 1152;
    *(_QWORD *)v79 = VirtualMachine::GetVmName((VirtualMachine *)((char *)v15 + 16));
    VmEventWriteAndReport<unsigned short const *,unsigned short const *,unsigned short const *>(
      (struct _EVENT_DESCRIPTOR *)&MSVML_WP_SAVEDSTATE_VERSION_INCOMPATIBLE_ERROR,
      5u,
      (__int64)v79,
      (__int64)&v66,
      (__int64)&v72);
    started = -2147188714;
    v64 = -2147188714;
    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
      VmlDebugTrace(
        16416,
        L"'WorkerTaskStarting::RunRestoreStartSteps': Failed to call '%hs'; hr=0x%08X\n",
        "Saved state VmVersion is not supported",
        2147778582LL);
    std::wstring::_Tidy_deallocate(&v83);
    goto LABEL_126;
  }
  v79[0] = 0;
  v16 = 0;
  v17 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)*v6 + 130) + 504LL))(*((_QWORD *)*v6 + 130));
  v68 = v17;
  v18 = 2;
  v19 = *v6;
  v20 = *((_QWORD *)*v6 + 177);
  if ( *(_DWORD *)(v20 + 108) )
  {
    v16 = *((_QWORD *)v19 + 331);
    v21 = (v16 >> 1) & 8 | 6;
    if ( (v16 & 0x40) != 0 )
      v21 = (*((_QWORD *)v19 + 331) >> 1) & 8 | 0x86;
    if ( (*(_BYTE *)v3 & 0x10) != 0 )
      v21 |= 0x10u;
    if ( (*(_BYTE *)v3 & 0x20) != 0 )
      v21 |= 0x20u;
    if ( (*(_BYTE *)v3 & 0x40) != 0 )
      v21 |= 0x40u;
    v18 = v21 | 0x100;
    if ( !v17 )
      v18 = v21;
  }
  try
  {
    if ( *(_BYTE *)(MemoryManager::RestoreCloneTemplateId(&MemoryManager::m_Instance, &v83, v13) + 16) )
    {
      v79[0] = 1;
    }
    else if ( (unsigned int)VmlIsDebugTraceEnabled(49184) )
    {
      VmlDebugTrace(49184, L"Restoring memory from saved state.");
    }
  }
  catch ( ... )
  {
    v64 = wil::ResultFromCaughtException(v22);
    started = v64;
    v28 = (WorkerTaskStarting *)v72;
    v6 = v73;
    v3 = (_DWORD *)v66;
    goto LABEL_127;
  }
  if ( (*(_BYTE *)v3 & 1) != 0 )
  {
    started = VirtualMachine::RestoreIgvmSaveState(*v6, v13);
    v64 = started;
    if ( started < 0 )
      goto LABEL_126;
  }
  started = VirtualMotherboard::StartReservingResources(*((_QWORD *)*v6 + 123), v13, v18);
  v64 = started;
  if ( started < 0 )
    goto LABEL_126;
  if ( v80 )
  {
    started = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)*v6 + 134) + 168LL))(*((_QWORD *)*v6 + 134));
    v64 = started;
    if ( started < 0 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
        VmlDebugTrace(16416, L"Failed to initialize encryption keys.");
      goto LABEL_126;
    }
  }
  memset_0(v86, 0, sizeof(v86));
  WorkerAsyncTask<VmWorkerTrace::StartingTask>::GetCurrentActivity(this, v78);
  VmPerf::StartRelatedActivity_VmWorkerTrace::ConstructGuestRam_VmWorkerTrace::StartingTask__GUID_const___((VmWorkerTrace::ConstructGuestRam *)v86);
  VmWorkerTrace::StartingTask::~StartingTask((VmWorkerTrace::StartingTask *)v78);
  v23 = VirtualMachine::ConstructGuestRam(
          *v6,
          v13,
          *((struct IVmSimpleTask **)this + 3),
          (const struct _GUID *)(v86[34] + 8LL));
  started = v23;
  v64 = v23;
  if ( v23 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x409,
      (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskstarting.cpp",
      (const char *)(unsigned int)v23,
      v62);
  wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v86, (unsigned int)started);
  VmWorkerTrace::ConstructGuestRam::~ConstructGuestRam((VmWorkerTrace::ConstructGuestRam *)v86);
  if ( started < 0 )
    goto LABEL_126;
  if ( (v16 & 2) == 0 )
  {
    try
    {
      (*(void (__fastcall **)(_QWORD, VmPrefixRepository *))(**((_QWORD **)*v6 + 128) + 264LL))(
        *((_QWORD *)*v6 + 128),
        v13);
      MemoryManager::RestoreVtlProtections((MemoryManager *)&MemoryManager::m_Instance, v13, 0);
    }
    catch ( ... )
    {
      v64 = wil::ResultFromCaughtException(v24);
      started = v64;
      v28 = (WorkerTaskStarting *)v72;
      v6 = v73;
      v3 = (_DWORD *)v66;
      goto LABEL_127;
    }
  }
  WorkerAsyncTaskBase::UpdateStatusProgress(this, 0x32u, (int *)&phkResult);
  if ( (_DWORD)phkResult )
  {
    started = -2147023673;
    v64 = -2147023673;
    goto LABEL_126;
  }
  v25 = *v6;
  if ( *(_DWORD *)(*((_QWORD *)*v6 + 177) + 108LL) || v79[0] )
  {
    v30 = this;
    v27 = v67;
  }
  else
  {
    memset_0(v86, 0, sizeof(v86));
    v26 = *(_QWORD *)(WorkerAsyncTask<VmWorkerTrace::StartingTask>::GetCurrentActivity(this, v78) + 272);
    memset_0(v86, 0, sizeof(v86));
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v86);
    v86[0] = &VmWorkerTrace::RestoreGuestRam::`vftable';
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(v86, v26 + 8);
    VmWorkerTrace::RestoreGuestRam::StartActivity((VmWorkerTrace::RestoreGuestRam *)v86, (const struct _GUID *)v25 + 71);
    v27 = 1;
    LODWORD(v67) = 1;
    VmWorkerTrace::StartingTask::~StartingTask((VmWorkerTrace::StartingTask *)v78);
    v83 = 0;
    VmRepositoryAutoLock::VmRepositoryAutoLock(&v83, v13, 0);
    started = DWORD2(v83);
    if ( SDWORD2(v83) < 0 )
    {
      v64 = DWORD2(v83);
      if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
        VmlDebugTrace(16416, L"Failed to lock memory repository.\n");
LABEL_59:
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)&v83);
      VmWorkerTrace::RestoreGuestRam::~RestoreGuestRam((VmWorkerTrace::RestoreGuestRam *)v86);
      v28 = this;
      v3 = (_DWORD *)v66;
      goto LABEL_127;
    }
    v29 = v81;
    RamSizeInPages = MemoryManager::GetRamSizeInPages((MemoryManager *)&MemoryManager::m_Instance);
    v30 = this;
    v31 = GmoRamOperation::Initialize(
            (GmoRamOperation *)v87,
            v13,
            *v6,
            *((struct IVmSimpleTask **)this + 3),
            0x63u,
            0x32u,
            RamSizeInPages,
            0,
            v29);
    started = v31;
    if ( v31 < 0 )
    {
      v64 = v31;
      v32 = v31 & 0xEFFFFFFF;
      _snwprintf_s<16>(v92, 16, L"%%%%%u", v31 & 0xEFFFFFFF);
      _snwprintf_s<16>(v91, 16, L"0x%08X", v32);
      v33 = *v6;
      v67 = (__int64)*v6 + 1152;
      VmName = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)v33 + 16));
      VmEventWriteAndReport<unsigned short const *,unsigned short const *,unsigned short (&)[16],unsigned short (&)[16]>(
        (struct _EVENT_DESCRIPTOR *)&MSVML_GMO_RESTORE_INIT_ERROR,
        5u,
        (__int64)&VmName,
        (__int64)&v67,
        (__int64)v92,
        (__int64)v91);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)&v83);
      VmWorkerTrace::RestoreGuestRam::~RestoreGuestRam((VmWorkerTrace::RestoreGuestRam *)v86);
      v28 = this;
      v3 = (_DWORD *)v66;
      goto LABEL_127;
    }
    v70 = 1;
    if ( v80 )
    {
      v34 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**((_QWORD **)*v6 + 134) + 184LL))(
              *((_QWORD *)*v6 + 134),
              v89,
              256,
              3);
      started = v34;
      if ( v34 < 0 )
      {
        v64 = v34;
        if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
          VmlDebugTrace(16416, L"Failed to allocate VID buffers.\n");
        goto LABEL_59;
      }
    }
    phkResult = 0;
    Vml::VmRegistryKey::Open(
      &phkResult,
      HKEY_LOCAL_MACHINE,
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization",
      0x20019u);
    v79[0] = 0;
    if ( (!Vml::VmRegistryKey::QueryValue((Vml::VmRegistryKey *)&phkResult, L"EnableAllZeroBufferWrite", v79)
       || v79[0] != 1)
      && !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)*v6 + 124) + 800LL))(*((_QWORD *)*v6 + 124)) )
    {
      v90 = 1;
    }
    started = GmoRamOperation::WorkThreadsStart((GmoRamOperation *)v87);
    v64 = started;
    if ( started < 0 )
    {
      Vml::VmRegistryKey::Close((Vml::VmRegistryKey *)&phkResult);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)&v83);
      VmWorkerTrace::RestoreGuestRam::~RestoreGuestRam((VmWorkerTrace::RestoreGuestRam *)v86);
      v28 = this;
      v3 = (_DWORD *)v66;
      goto LABEL_127;
    }
    GmoRamOperation::WorkDispatch((GmoRamOperation *)v87);
    GmoRamOperation::WorkThreadsWaitForExit((GmoRamOperation *)v87);
    started = v88;
    v64 = v88;
    if ( v88 < 0 )
    {
      if ( v88 == -2147213311 )
      {
        v35 = *v6;
        VmName = (__int64)*v6 + 1152;
        v67 = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)v35 + 16));
        VmEventWriteAndReport<unsigned short const *,unsigned short const *>(
          (struct _EVENT_DESCRIPTOR *)&MSVML_RESTORE_CANCELED,
          5u,
          (__int64)&v67,
          (__int64)&VmName);
      }
      Vml::VmRegistryKey::Close((Vml::VmRegistryKey *)&phkResult);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)&v83);
      VmWorkerTrace::RestoreGuestRam::~RestoreGuestRam((VmWorkerTrace::RestoreGuestRam *)v86);
      v28 = this;
      v3 = (_DWORD *)v66;
      goto LABEL_127;
    }
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v86, 0);
    Vml::VmRegistryKey::Close((Vml::VmRegistryKey *)&phkResult);
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)&v83);
    VmWorkerTrace::RestoreGuestRam::~RestoreGuestRam((VmWorkerTrace::RestoreGuestRam *)v86);
  }
  if ( *(_DWORD *)(*((_QWORD *)*v6 + 177) + 108LL) )
  {
    if ( v68 )
    {
      started = (*(__int64 (__fastcall **)(__int64, VmPrefixRepository *))(*(_QWORD *)(*((_QWORD *)*v6 + 128) + 8LL)
                                                                         + 104LL))(
                  *((_QWORD *)*v6 + 128) + 8LL,
                  v13);
      v64 = started;
      if ( started < 0 )
      {
        v28 = this;
        v3 = (_DWORD *)v66;
        goto LABEL_127;
      }
    }
  }
  v36 = WorkerTaskStarting::PowerOnVirtualMotherboard(v30, v13, v16);
  started = v36;
  if ( v36 < 0 )
  {
    v64 = v36;
    v28 = this;
    v3 = (_DWORD *)v66;
    goto LABEL_127;
  }
  v71 = 1;
  started = VirtualMachine::RegisterGuestCrashManager(*v6);
  v64 = started;
  if ( started < 0 )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
      VmlDebugTraceWithError(16416, &off_1402E2FF8, (unsigned int)started);
    v28 = this;
    v3 = (_DWORD *)v66;
    goto LABEL_127;
  }
  v37 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)*v6 + 133) + 48LL))(*((_QWORD *)*v6 + 133));
  started = v37;
  if ( v37 < 0 )
  {
    v64 = v37;
    v28 = this;
    v3 = (_DWORD *)v66;
    goto LABEL_127;
  }
  v39 = VirtualMachine::RestorePartitionStates(*v6, v13, v16 & 1, v38);
  started = v39;
  if ( v39 < 0 )
  {
    v64 = v39;
    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
      VmlDebugTrace(16416, L"Failed to restore partition.\n");
    v28 = this;
    v3 = (_DWORD *)v66;
    goto LABEL_127;
  }
  v40 = (*(__int64 (__fastcall **)(_QWORD, VmPrefixRepository *))(**((_QWORD **)*v6 + 130) + 768LL))(
          *((_QWORD *)*v6 + 130),
          v13);
  started = v40;
  if ( v40 < 0 )
  {
    v64 = v40;
    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
      VmlDebugTrace(16416, L"Failed to restore isolation control state.\n");
    v28 = this;
    v3 = (_DWORD *)v66;
    goto LABEL_127;
  }
  v41 = *v6;
  if ( *((_DWORD *)*v6 + 653) )
  {
    memset_0(v86, 0, sizeof(v86));
    v42 = *(_QWORD *)(WorkerAsyncTask<VmWorkerTrace::StartingTask>::GetCurrentActivity(v30, v78) + 272);
    memset_0(v86, 0, sizeof(v86));
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v86);
    v86[0] = &VmWorkerTrace::RestoreEpfState::`vftable';
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(v86, v42 + 8);
    VmWorkerTrace::RestoreEpfState::StartActivity((VmWorkerTrace::RestoreEpfState *)v86, (const struct _GUID *)v41 + 71);
    v27 = v27 & 0xFFFFFFF3 | 4;
    LODWORD(v67) = v27;
    VmWorkerTrace::StartingTask::~StartingTask((VmWorkerTrace::StartingTask *)v78);
    v43 = (*(__int64 (__fastcall **)(_QWORD, VmPrefixRepository *))(**((_QWORD **)*v6 + 128) + 280LL))(
            *((_QWORD *)*v6 + 128),
            v13);
    started = v43;
    if ( v43 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4F1,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskstarting.cpp",
        (const char *)(unsigned int)v43,
        v62);
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v86, (unsigned int)started);
    if ( started < 0 )
    {
      v64 = started;
      if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
        VmlDebugTrace(16416, L"Failed to restore partition EPF state.\n");
      VmWorkerTrace::RestoreEpfState::~RestoreEpfState((VmWorkerTrace::RestoreEpfState *)v86);
      v28 = this;
      v3 = (_DWORD *)v66;
      goto LABEL_127;
    }
    VmWorkerTrace::RestoreEpfState::~RestoreEpfState((VmWorkerTrace::RestoreEpfState *)v86);
  }
  v44 = *v6;
  if ( *((_BYTE *)*v6 + 2616) )
  {
    memset_0(v86, 0, sizeof(v86));
    v45 = *(_QWORD *)(WorkerAsyncTask<VmWorkerTrace::StartingTask>::GetCurrentActivity(v30, v78) + 272);
    memset_0(v86, 0, sizeof(v86));
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v86);
    v86[0] = &VmWorkerTrace::RestoreSchedulerAssistState::`vftable';
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(v86, v45 + 8);
    VmWorkerTrace::RestoreSchedulerAssistState::StartActivity(
      (VmWorkerTrace::RestoreSchedulerAssistState *)v86,
      (const struct _GUID *)v44 + 71);
    LODWORD(v67) = v27 & 0xFFFFFFCF | 0x10;
    VmWorkerTrace::StartingTask::~StartingTask((VmWorkerTrace::StartingTask *)v78);
    v46 = (*(__int64 (__fastcall **)(_QWORD, VmPrefixRepository *))(**((_QWORD **)*v6 + 128) + 304LL))(
            *((_QWORD *)*v6 + 128),
            v13);
    started = v46;
    if ( v46 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x506,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskstarting.cpp",
        (const char *)(unsigned int)v46,
        v62);
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v86, (unsigned int)started);
    if ( started < 0 )
    {
      v64 = started;
      if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
        VmlDebugTrace(16416, L"Failed to restore partition scheduler assist state.\n");
      VmWorkerTrace::RestoreSchedulerAssistState::~RestoreSchedulerAssistState((VmWorkerTrace::RestoreSchedulerAssistState *)v86);
      v28 = this;
      v3 = (_DWORD *)v66;
      goto LABEL_127;
    }
    VmWorkerTrace::RestoreSchedulerAssistState::~RestoreSchedulerAssistState((VmWorkerTrace::RestoreSchedulerAssistState *)v86);
  }
  v47 = *((_QWORD *)*v6 + 124);
  v48 = *((_QWORD *)*v6 + 132);
  v49 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v48 + 24LL);
  v50 = (*(_DWORD *)v66 >> 2) & 1;
  v51 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 528LL))(v47);
  v52 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 512LL))(v47);
  v53 = v49(v48, v52, v51, v50);
  started = v53;
  if ( v53 >= 0 )
  {
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)*v6 + 130) + 656LL))(*((_QWORD *)*v6 + 130), 1);
    v28 = this;
    v3 = (_DWORD *)v66;
    if ( *((_DWORD *)this + 100) != 4 )
    {
      v54 = VirtualMachine::StartVm(*v6, 4 * (*(_DWORD *)v66 & 0x10u), 14);
      started = v54;
      if ( v54 < 0 )
      {
        v64 = v54;
        goto LABEL_127;
      }
      v69 = 1;
    }
    v55 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)*v6 + 128) + 24LL))(*((_QWORD *)*v6 + 128) + 24LL);
    VidTrimPartitionMemory(v55);
    started = 0;
    v64 = 0;
  }
  else
  {
    v64 = v53;
    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
      VmlDebugTrace(16416, L"Failed to restore saved state manager.\n");
    v28 = this;
    v3 = (_DWORD *)v66;
  }
LABEL_127:
  WorkerTaskStarting::UploadRestoreTelemetry(v28, v85, (unsigned int)started);
  if ( v70 )
    GmoRamOperation::Teardown((GmoRamOperation *)v87);
  if ( v80 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)*v6 + 134) + 192LL))(*((_QWORD *)*v6 + 134));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)*v6 + 134) + 176LL))(*((_QWORD *)*v6 + 134));
  }
  if ( started < 0 )
  {
    if ( v69 )
      VirtualMachine::StopVm(*v6, 0, 17);
    if ( v71 )
    {
      v59 = 2048;
      v60 = *v6;
      if ( *(_DWORD *)(*((_QWORD *)*v6 + 177) + 108LL)
        && (*((_BYTE *)v60 + 2648) & 0x10) != 0
        && (*(_BYTE *)v3 & 0x10) != 0 )
      {
        v59 = *v3 & 0x20 | 0x81Cu;
        if ( (*(_BYTE *)v3 & 0x40) != 0 )
          v59 = *v3 & 0x20 | 0x85Cu;
        if ( *(char *)v3 < 0 )
          LODWORD(v59) = v59 | 0x100;
      }
      VirtualMotherboard::PowerOff(*((_QWORD *)v60 + 123), v59);
    }
  }
  else
  {
    v56 = *v6;
    if ( *(_DWORD *)(*((_QWORD *)*v6 + 177) + 108LL) )
    {
      memset_0(v86, 0, sizeof(v86));
      v57 = *(_QWORD *)(WorkerAsyncTask<VmWorkerTrace::StartingTask>::GetCurrentActivity(v28, v78) + 272);
      memset_0(v86, 0, sizeof(v86));
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v86);
      v86[0] = &VmWorkerTrace::UnpersistRamInformation::`vftable';
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
        v86,
        v57 + 8);
      VmWorkerTrace::UnpersistRamInformation::StartActivity(
        (VmWorkerTrace::UnpersistRamInformation *)v86,
        (const struct _GUID *)v56 + 71);
      VmWorkerTrace::StartingTask::~StartingTask((VmWorkerTrace::StartingTask *)v78);
      try
      {
        MemoryManager::UnPersistRamInformation((MemoryManager *)&MemoryManager::m_Instance);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x55C,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskstarting.cpp",
          v58);
        started = v64;
        v6 = v73;
      }
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v86, 0);
      VmWorkerTrace::UnpersistRamInformation::~UnpersistRamInformation((VmWorkerTrace::UnpersistRamInformation *)v86);
    }
    if ( v69 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)*v6 + 133) + 56LL))(*((_QWORD *)*v6 + 133));
  }
  if ( !v80 )
    std::unique_ptr<GmoBitmap>::reset(&qword_1403CC9E0, 0);
  Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(&v75);
  std::wstring::_Tidy_deallocate(v85);
  Vml::VmReferencePtr<IMemoryContentsFileSizeChangeCallback,Vml::VmUserReferenceTraits>::~VmReferencePtr<IMemoryContentsFileSizeChangeCallback,Vml::VmUserReferenceTraits>(&v76);
  Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(&v77);
  GmoRamOperationRestore::~GmoRamOperationRestore((GmoRamOperationRestore *)v87);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1400c2b6c  mov     [rsp+arg_8], rbx
0x1400c2b71  mov     [rsp+arg_10], rsi
0x1400c2b76  push    rdi
0x1400c2b77  push    r12
0x1400c2b79  push    r13
0x1400c2b7b  push    r14
0x1400c2b7d  push    r15
0x1400c2b7f  sub     rsp, 500h
0x1400c2b86  mov     rax, cs:__security_cookie
0x1400c2b8d  xor     rax, rsp
0x1400c2b90  mov     [rsp+528h+var_38], rax
0x1400c2b98  mov     rbx, rcx
0x1400c2b9b  mov     [rsp+528h+var_4D0], rcx
0x1400c2ba0  mov     [rsp+528h+var_4A0], rcx
0x1400c2ba8  xor     esi, esi
0x1400c2baa  mov     r12d, esi
0x1400c2bad  mov     dword ptr [rsp+528h+var_4B8], esi
0x1400c2bb1  mov     [rsp+528h+var_4C8], esi
0x1400c2bb5  lea     r13, [rcx+194h]
0x1400c2bbc  mov     [rsp+528h+var_4C0], r13
0x1400c2bc1  mov     dl, [r13+0]
0x1400c2bc5  and     dl, 1
0x1400c2bc8  lea     r8, aVmphu; "VmPhu"
0x1400c2bcf  call    ?LogFlag@?$WorkerAsyncTask@VStartingTask@VmWorkerTrace@@@@IEAAX_NPEBG@Z; WorkerAsyncTask<VmWorkerTrace::StartingTask>::LogFlag(bool,ushort const *)
0x1400c2bd4  mov     edx, [r13+0]
0x1400c2bd8  shr     edx, 2
0x1400c2bdb  and     dl, 1
0x1400c2bde  lea     r8, aDisableflushes; "DisableFlushes"
0x1400c2be5  mov     rcx, rbx
0x1400c2be8  call    ?LogFlag@?$WorkerAsyncTask@VStartingTask@VmWorkerTrace@@@@IEAAX_NPEBG@Z; WorkerAsyncTask<VmWorkerTrace::StartingTask>::LogFlag(bool,ushort const *)
0x1400c2bed  mov     edx, [r13+0]
0x1400c2bf1  shr     edx, 4
0x1400c2bf4  and     dl, 1
0x1400c2bf7  lea     r8, aHandletransfer_1; "HandleTransfer"
0x1400c2bfe  mov     rcx, rbx
0x1400c2c01  call    ?LogFlag@?$WorkerAsyncTask@VStartingTask@VmWorkerTrace@@@@IEAAX_NPEBG@Z; WorkerAsyncTask<VmWorkerTrace::StartingTask>::LogFlag(bool,ushort const *)
0x1400c2c06  mov     [rsp+528h+var_4A4], esi
0x1400c2c0d  mov     [rsp+528h+var_4AC], esi
0x1400c2c11  mov     dword ptr [rsp+528h+phkResult], esi
0x1400c2c18  mov     [rsp+528h+var_4A8], esi
0x1400c2c1f  mov     [rsp+528h+var_310], esi
0x1400c2c26  xor     edx, edx; Val
0x1400c2c28  mov     r8d, 0F0h; Size
0x1400c2c2e  lea     rcx, [rsp+528h+var_168]; void *
0x1400c2c36  call    memset_0
0x1400c2c3b  lea     rcx, [rsp+528h+var_168]; this
0x1400c2c43  call    ??0GmoRamOperation@@QEAA@XZ; GmoRamOperation::GmoRamOperation(void)
0x1400c2c48  lea     rax, ??_7GmoRamOperationRestore@@6B@; const GmoRamOperationRestore::`vftable'
0x1400c2c4f  mov     [rsp+528h+var_168], rax
0x1400c2c57  mov     [rsp+528h+var_478], rsi
0x1400c2c5f  mov     [rsp+528h+var_480], rsi
0x1400c2c67  xorps   xmm0, xmm0
0x1400c2c6a  movups  [rsp+528h+var_2E0], xmm0
0x1400c2c72  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1400c2c7a  movdqu  [rsp+528h+var_2D0], xmm1
0x1400c2c83  mov     word ptr [rsp+528h+var_2E0], si
0x1400c2c8b  mov     [rsp+528h+var_488], rsi
0x1400c2c93  lea     r14, [rbx+10h]
0x1400c2c97  mov     [rsp+528h+var_498], r14
0x1400c2c9f  mov     rax, [r14]
0x1400c2ca2  mov     rcx, [rax+430h]
0x1400c2ca9  mov     rax, [rcx]
0x1400c2cac  lea     rdx, [rsp+528h+var_310]
0x1400c2cb4  mov     rax, [rax+70h]
0x1400c2cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400c2cbd  lea     rcx, [rsp+528h+var_480]; struct IVersionManager **
0x1400c2cc5  call    ?CreateVersionManagerInstance@VersionManagerDefaultFactory@@SAJPEAPEAUIVersionManager@@@Z; VersionManagerDefaultFactory::CreateVersionManagerInstance(IVersionManager * *)
0x1400c2cca  mov     edi, eax
0x1400c2ccc  mov     [rsp+528h+var_4D8], eax
0x1400c2cd0  test    eax, eax
0x1400c2cd2  jns     short loc_1400C2D05
0x1400c2cd4  mov     ebx, 4020h
0x1400c2cd9  mov     ecx, ebx
0x1400c2cdb  call    VmlIsDebugTraceEnabled
0x1400c2ce0  test    eax, eax
0x1400c2ce2  jz      loc_1400C3D19
0x1400c2ce8  mov     r9d, edi
0x1400c2ceb  lea     r8, aFailedToCreate_3; "Failed to create version manager"
0x1400c2cf2  lea     rdx, aWorkertaskstar_3; "'WorkerTaskStarting::RunRestoreStartSte"...
0x1400c2cf9  mov     ecx, ebx
0x1400c2cfb  call    VmlDebugTrace
0x1400c2d00  jmp     loc_1400C3D19
0x1400c2d05  mov     rcx, [r14]
0x1400c2d08  mov     r8, [rcx+588h]
0x1400c2d0f  mov     r8d, [r8+6Ch]
0x1400c2d13  lea     rdx, [rsp+528h+var_318]
0x1400c2d1b  call    ?GetSavedStateRepositoryForRestore@VirtualMachine@@UEAA?AV?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@H@Z; VirtualMachine::GetSavedStateRepositoryForRestore(int)
0x1400c2d20  mov     rdx, rax
0x1400c2d23  lea     rcx, [rsp+528h+var_488]
0x1400c2d2b  call    ??4?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAAEBV01@$$QEAV01@@Z; Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::operator=(Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> &&)
0x1400c2d30  lea     rcx, [rsp+528h+var_318]
0x1400c2d38  call    ??1?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(void)
0x1400c2d3d  xorps   xmm0, xmm0
0x1400c2d40  movups  [rsp+528h+var_300], xmm0
0x1400c2d48  xor     r8d, r8d
0x1400c2d4b  mov     rbx, [rsp+528h+var_488]
0x1400c2d53  mov     rdx, rbx
0x1400c2d56  lea     rcx, [rsp+528h+var_300]
0x1400c2d5e  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x1400c2d63  nop
0x1400c2d64  cmp     dword ptr [rsp+528h+var_300+8], esi
0x1400c2d6b  jl      short loc_1400C2DAC
0x1400c2d6d  mov     rax, [rbx]
0x1400c2d70  lea     r8, [rsp+528h+var_2E0]
0x1400c2d78  lea     rdx, ?VM_SAVED_STATE_VMWP_VERSION@@3QBGB; "/savedstate/VmwpVersion"
0x1400c2d7f  mov     rcx, rbx
0x1400c2d82  mov     rax, [rax+68h]
0x1400c2d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400c2d8b  test    eax, eax
0x1400c2d8d  jns     short loc_1400C2DA6
0x1400c2d8f  mov     r8d, eax
0x1400c2d92  lea     rdx, aConfigreadfail; "ConfigReadFail:%ld"
0x1400c2d99  lea     rcx, [rsp+528h+var_2E0]
0x1400c2da1  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x1400c2da6  mov     edi, esi
0x1400c2da8  mov     [rsp+528h+var_4D8], esi
0x1400c2dac  lea     rcx, [rsp+528h+var_300]; this
0x1400c2db4  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400c2db9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400c2dc0  mov     ecx, 80h; unsigned __int64
0x1400c2dc5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400c2dca  mov     [rsp+528h+var_490], rax
0x1400c2dd2  test    rax, rax
0x1400c2dd5  jz      short loc_1400C2DE7
0x1400c2dd7  mov     rdx, rbx; struct VmRepository *
0x1400c2dda  mov     rcx, rax; this
0x1400c2ddd  call    ??0VmPrefixRepository@@QEAA@PEAVVmRepository@@PEBG@Z; VmPrefixRepository::VmPrefixRepository(VmRepository *,ushort const *)
0x1400c2de2  mov     r15, rax
0x1400c2de5  jmp     short loc_1400C2DEA
0x1400c2de7  mov     r15, rsi
0x1400c2dea  test    r15, r15
0x1400c2ded  jz      loc_1400C3CF3
0x1400c2df3  lea     rcx, [r15+8]; this
0x1400c2df7  call    ?IncrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::IncrementUserCount(void)
0x1400c2dfc  mov     [rsp+528h+var_478], r15
0x1400c2e04  mov     [rsp+528h+var_30C], esi
0x1400c2e0b  xorps   xmm0, xmm0
0x1400c2e0e  movups  [rsp+528h+var_300], xmm0
0x1400c2e16  mov     r8d, 1
0x1400c2e1c  mov     rdx, rbx
0x1400c2e1f  lea     rcx, [rsp+528h+var_300]
0x1400c2e27  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x1400c2e2c  nop
0x1400c2e2d  mov     edi, dword ptr [rsp+528h+var_300+8]
0x1400c2e34  test    edi, edi
0x1400c2e36  jns     short loc_1400C2E70
0x1400c2e38  mov     [rsp+528h+var_4D8], edi
0x1400c2e3c  mov     ebx, 4020h
0x1400c2e41  mov     ecx, ebx
0x1400c2e43  call    VmlIsDebugTraceEnabled
0x1400c2e48  test    eax, eax
0x1400c2e4a  jz      short loc_1400C2E5E
0x1400c2e4c  mov     r8d, edi
0x1400c2e4f  lea     rdx, off_1402E3010; "Failed to lock runtime repository"
0x1400c2e56  mov     ecx, ebx
0x1400c2e58  call    VmlDebugTraceWithError
0x1400c2e5d  nop
0x1400c2e5e  lea     rcx, [rsp+528h+var_300]; this
0x1400c2e66  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400c2e6b  jmp     loc_1400C3D19
0x1400c2e70  mov     qword ptr [rsp+528h+var_318], rsi
0x1400c2e78  mov     rax, [rbx]
0x1400c2e7b  lea     r8, [rsp+528h+var_318]
0x1400c2e83  lea     rdx, ?VM_SAVED_STATE_VM_VERSION@@3QBGB; "/savedstate/VmVersion"
0x1400c2e8a  mov     rcx, rbx
0x1400c2e8d  mov     rax, [rax+70h]
0x1400c2e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400c2e96  mov     edi, eax
0x1400c2e98  mov     [rsp+528h+var_4D8], eax
0x1400c2e9c  test    eax, eax
0x1400c2e9e  jns     short loc_1400C2ECA
0x1400c2ea0  mov     ebx, 4020h
0x1400c2ea5  mov     ecx, ebx
0x1400c2ea7  call    VmlIsDebugTraceEnabled
0x1400c2eac  test    eax, eax
0x1400c2eae  jz      short loc_1400C2E5E
0x1400c2eb0  mov     r9d, edi
0x1400c2eb3  lea     r8, aFailedToGetSav; "Failed to get saved state VmVersion"
0x1400c2eba  lea     rdx, aWorkertaskstar_3; "'WorkerTaskStarting::RunRestoreStartSte"...
0x1400c2ec1  mov     ecx, ebx
0x1400c2ec3  call    VmlDebugTrace
0x1400c2ec8  jmp     short loc_1400C2E5E
0x1400c2eca  mov     eax, [rsp+528h+var_318]
0x1400c2ed1  mov     [rsp+528h+var_30C], eax
0x1400c2ed8  lea     rcx, [rsp+528h+var_300]; this
0x1400c2ee0  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400c2ee5  mov     rcx, [rsp+528h+var_480]
0x1400c2eed  mov     rax, [rcx]
0x1400c2ef0  lea     rdx, [rsp+528h+var_30C]
0x1400c2ef8  mov     rax, [rax]
0x1400c2efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400c2f00  test    al, al
0x1400c2f02  jnz     loc_1400C2FFB
0x1400c2f08  xorps   xmm0, xmm0
0x1400c2f0b  movups  [rsp+528h+var_300], xmm0
0x1400c2f13  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1400c2f1b  movdqu  [rsp+528h+var_2F0], xmm1
0x1400c2f24  mov     word ptr [rsp+528h+var_300], si
0x1400c2f2c  lea     rdx, [rsp+528h+var_300]
0x1400c2f34  mov     ecx, [rsp+528h+var_30C]
0x1400c2f3b  call    ?GetVmVersionString@@YAXIAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetVmVersionString(uint,std::wstring &)
0x1400c2f40  lea     rax, [rsp+528h+var_300]
0x1400c2f48  cmp     qword ptr [rsp+528h+var_2F0+8], 7
0x1400c2f51  cmova   rax, qword ptr [rsp+528h+var_300]
0x1400c2f5a  mov     [rsp+528h+var_4A0], rax
0x1400c2f62  mov     rcx, [r14]
0x1400c2f65  lea     rax, [rcx+480h]
0x1400c2f6c  mov     [rsp+528h+var_4C0], rax
0x1400c2f71  add     rcx, 10h; this
0x1400c2f75  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400c2f7a  mov     qword ptr [rsp+528h+var_318], rax
0x1400c2f82  lea     rax, [rsp+528h+var_4A0]
0x1400c2f8a  mov     [rsp+528h+var_4F8], rax; __int64
0x1400c2f8f  lea     rax, [rsp+528h+var_4C0]
0x1400c2f94  mov     [rsp+528h+var_500], rax; __int64
0x1400c2f99  lea     rax, [rsp+528h+var_318]
0x1400c2fa1  mov     [rsp+528h+var_508], rax; __int64
0x1400c2fa6  mov     edx, 5; unsigned int
0x1400c2fab  lea     rcx, MSVML_WP_SAVEDSTATE_VERSION_INCOMPATIBLE_ERROR; struct _EVENT_DESCRIPTOR *
0x1400c2fb2  call    ??$VmEventWriteAndReport@PEBGPEBGPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBG$$QEAPEBG33@Z; VmEventWriteAndReport<ushort const *,ushort const *,ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *,ushort const * &&,ushort const * &&,ushort const * &&)
0x1400c2fb7  mov     edi, 80048016h
0x1400c2fbc  mov     [rsp+528h+var_4D8], edi
0x1400c2fc0  mov     ebx, 4020h
0x1400c2fc5  mov     ecx, ebx
0x1400c2fc7  call    VmlIsDebugTraceEnabled
0x1400c2fcc  test    eax, eax
0x1400c2fce  jz      short loc_1400C2FE9
0x1400c2fd0  mov     r9d, edi
0x1400c2fd3  lea     r8, aSavedStateVmve; "Saved state VmVersion is not supported"
0x1400c2fda  lea     rdx, aWorkertaskstar_3; "'WorkerTaskStarting::RunRestoreStartSte"...
0x1400c2fe1  mov     ecx, ebx
0x1400c2fe3  call    VmlDebugTrace
0x1400c2fe8  nop
0x1400c2fe9  lea     rcx, [rsp+528h+var_300]
0x1400c2ff1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400c2ff6  jmp     loc_1400C3D19
0x1400c2ffb  mov     [rsp+528h+var_318], esi
0x1400c3002  mov     rbx, rsi
0x1400c3005  mov     rax, [r14]
0x1400c3008  mov     rcx, [rax+410h]
0x1400c300f  mov     rax, [rcx]
0x1400c3012  mov     rax, [rax+1F8h]
0x1400c3019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400c301e  mov     [rsp+528h+var_4B0], al
0x1400c3022  mov     r12d, 2
0x1400c3028  mov     rdx, [r14]
0x1400c302b  mov     rcx, [rdx+588h]
0x1400c3032  cmp     [rcx+6Ch], esi
0x1400c3035  jz      short loc_1400C307F
0x1400c3037  mov     rbx, [rdx+0A58h]
0x1400c303e  mov     rcx, rbx
0x1400c3041  shr     rcx, 1
0x1400c3044  and     ecx, 8
0x1400c3047  or      ecx, 6
0x1400c304a  test    bl, 40h
0x1400c304d  jz      short loc_1400C3053
0x1400c304f  bts     ecx, 7
0x1400c3053  test    byte ptr [r13+0], 10h
0x1400c3058  jz      short loc_1400C305D
0x1400c305a  or      ecx, 10h
0x1400c305d  test    byte ptr [r13+0], 20h
0x1400c3062  jz      short loc_1400C3067
0x1400c3064  or      ecx, 20h
0x1400c3067  test    byte ptr [r13+0], 40h
0x1400c306c  jz      short loc_1400C3071
0x1400c306e  or      ecx, 40h
0x1400c3071  mov     r12d, ecx
0x1400c3074  bts     r12d, 8
0x1400c3079  test    al, al
0x1400c307b  cmovz   r12d, ecx
0x1400c307f  mov     r8, r15
0x1400c3082  lea     rdx, [rsp+528h+var_300]
0x1400c308a  lea     rcx, ?m_Instance@MemoryManager@@0V1@A; MemoryManager MemoryManager::m_Instance
0x1400c3091  call    ?RestoreCloneTemplateId@MemoryManager@@QEAA?AV?$optional@U_GUID@@@std@@PEAVVmRepository@@@Z; MemoryManager::RestoreCloneTemplateId(VmRepository *)
0x1400c3096  cmp     [rax+10h], sil
0x1400c309a  jz      short loc_1400C30A9
0x1400c309c  mov     [rsp+528h+var_318], 1
0x1400c30a7  jmp     short loc_1400C30C8
0x1400c30a9  mov     edi, 0C020h
0x1400c30ae  mov     ecx, edi
0x1400c30b0  call    VmlIsDebugTraceEnabled
0x1400c30b5  test    eax, eax
0x1400c30b7  jz      short loc_1400C30C8
0x1400c30b9  lea     rdx, aRestoringMemor; "Restoring memory from saved state."
0x1400c30c0  mov     ecx, edi
0x1400c30c2  call    VmlDebugTrace
0x1400c30c7  nop
0x1400c30c8  test    byte ptr [r13+0], 1
0x1400c30cd  jz      short loc_1400C30E4
0x1400c30cf  mov     rdx, r15; struct VmRepository *
0x1400c30d2  mov     rcx, [r14]; this
0x1400c30d5  call    ?RestoreIgvmSaveState@VirtualMachine@@UEAAJPEAVVmRepository@@@Z; VirtualMachine::RestoreIgvmSaveState(VmRepository *)
0x1400c30da  mov     edi, eax
0x1400c30dc  mov     [rsp+528h+var_4D8], eax
0x1400c30e0  test    eax, eax
0x1400c30e2  js      short loc_1400C314D
0x1400c30e4  mov     rcx, [r14]
0x1400c30e7  mov     r8d, r12d
0x1400c30ea  mov     rdx, r15
0x1400c30ed  mov     rcx, [rcx+3D8h]
  ... truncated ...
```
