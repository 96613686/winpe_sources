# SOS_OS::Boot(void)

- ea: `0x1004b8080`
- end: `0x1004b8a45`
- name: `?Boot@SOS_OS@@SA?AW4SOS_RESULT@@XZ`
- size: `2501`
- prototype: ``
- caller_count: `0`
- callee_count: `31`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x100406b20`
- `0x100406b40`
- `0x100406f10`
- `0x10040d510`
- `0x100410010`
- `0x1004101f0`
- `0x100412b80`
- `0x100412d30`
- `0x10041bdf0`
- `0x100423140`
- `0x100426a00`
- `0x100435230`
- `0x1004360f0`
- `0x10043b220`
- `0x10043b2f0`
- `0x10046c3e0`
- `0x10048d6c0`
- `0x1004a5fb0`
- `0x1004a9580`
- `0x1004afc30`
- `0x1004b2560`
- `0x1004b2e10`
- `0x1004b46f0`
- `0x1004b5fa0`
- `0x1004b8080`
- `0x1005998d0`
- `0x1005a6070`
- `0x1005a64a0`
- `0x1005a7120`
- `0x1005af320`
- `0x1005b1fc0`

## import_xrefs

- `WINMM!timeGetDevCaps` at `0x1004b826d`
- `WINMM!timeGetDevCaps` at `0x1004b826d`
- `KERNEL32!CreateEventW` at `0x1004b818b`
- `KERNEL32!CreateEventW` at `0x1004b818b`
- `KERNEL32!SetEvent` at `0x1004b8a1a`
- `KERNEL32!SetEvent` at `0x1004b8a1a`
- `KERNEL32!SetProcessAffinityUpdateMode` at `0x1004b8963`
- `KERNEL32!SetProcessAffinityUpdateMode` at `0x1004b8963`
- `KERNEL32!QueryPerformanceCounter` at `0x1004b8838`
- `KERNEL32!QueryPerformanceCounter` at `0x1004b8838`
- `KERNEL32!GetModuleHandleW` at `0x1004b8144`
- `KERNEL32!GetModuleHandleW` at `0x1004b8200`
- `KERNEL32!GetModuleHandleW` at `0x1004b8144`
- `KERNEL32!GetModuleHandleW` at `0x1004b8200`
- `KERNEL32!GetProcAddress` at `0x1004b816a`
- `KERNEL32!GetProcAddress` at `0x1004b8210`
- `KERNEL32!GetProcAddress` at `0x1004b8511`
- `KERNEL32!GetProcAddress` at `0x1004b816a`
- `KERNEL32!GetProcAddress` at `0x1004b8210`
- `KERNEL32!GetProcAddress` at `0x1004b8511`
- `KERNEL32!GetCurrentProcess` at `0x1004b8955`
- `KERNEL32!GetCurrentProcess` at `0x1004b8955`
- `SQLOS!IsHardwareSupported` at `0x1004b812b`
- `SQLOS!IsHardwareSupported` at `0x1004b812b`
- `VCRUNTIME140!_set_se_translator` at `0x1004b80fe`
- `VCRUNTIME140!_set_se_translator` at `0x1004b80fe`
- `VCRUNTIME140!set_unexpected` at `0x1004b8118`
- `VCRUNTIME140!set_unexpected` at `0x1004b8118`
- `api-ms-win-crt-runtime-l1-1-0!_set_new_handler` at `0x1004b8125`
- `api-ms-win-crt-runtime-l1-1-0!_set_new_handler` at `0x1004b8125`
- `api-ms-win-crt-runtime-l1-1-0!set_terminate` at `0x1004b810b`
- `api-ms-win-crt-runtime-l1-1-0!set_terminate` at `0x1004b810b`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004b88fd`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004b88fd`

## string_xrefs

- `0x1004b8726`: `Sql\DkTemp\sos\include\common.inl`
- `0x1004b81f9`: `kernel32.dll`
- `0x1004b8160`: `SetDllMainCallback`
- `0x1004b8431`: `Sql\DkTemp\sos\src\os_ext.cpp`
- `0x1004b8503`: `SetCreateSOSHostObjectCallback`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 SOS_OS::Boot()
{
  struct SOS_Node *j; // rbx
  unsigned int MemoryNodes; // edi
  __int64 v2; // rsi
  __int64 v3; // r14
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rsi
  unsigned int v6; // eax
  HMODULE v7; // rax
  FARPROC v8; // r10
  char v9; // al
  UINT wPeriodMin; // eax
  void (*v11)(const wchar_t *, ...); // r9
  __int64 *v12; // rdx
  unsigned __int64 v13; // rax
  unsigned int v14; // r8d
  SystemThread *v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // rcx
  __int64 v18; // rdi
  struct IMemObj *MemObject; // rax
  __int64 v20; // rax
  __int64 v21; // rdi
  struct SOS_Task **v22; // rcx
  FARPROC v23; // r15
  __int64 v24; // rsi
  SOS_WaitableAddressManager *v25; // r14
  int i; // edi
  __int64 v27; // rsi
  __int64 v28; // rdx
  __int64 v29; // rdx
  _QWORD *v30; // rcx
  __int64 v31; // rsi
  __int64 v32; // rax
  SystemThread *v33; // rcx
  LARGE_INTEGER v34; // rdx
  __int64 v35; // rax
  __int64 v36; // rdi
  unsigned __int16 v37; // ax
  int v38; // r8d
  HANDLE CurrentProcess; // rax
  int Format; // [rsp+20h] [rbp-69h]
  char *Formata; // [rsp+20h] [rbp-69h]
  LARGE_INTEGER PerformanceCount; // [rsp+30h] [rbp-59h] BYREF
  struct IMemObj *v44; // [rsp+38h] [rbp-51h]
  __int128 v45; // [rsp+40h] [rbp-49h] BYREF
  _UNKNOWN **v46; // [rsp+50h] [rbp-39h]
  __int64 v47; // [rsp+58h] [rbp-31h]
  int v48; // [rsp+60h] [rbp-29h]
  _DWORD v49[4]; // [rsp+68h] [rbp-21h] BYREF
  __int64 v50; // [rsp+78h] [rbp-11h]
  __int64 v51; // [rsp+80h] [rbp-9h] BYREF
  int v52; // [rsp+F8h] [rbp+6Fh] BYREF
  timecaps_tag ptc; // [rsp+100h] [rbp+77h] BYREF
  __int64 v54; // [rsp+108h] [rbp+7Fh]

  v50 = -2;
  j = 0;
  MemoryNodes = 0;
  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
     + (unsigned int)SystemThread_TlsOffset;
  v3 = *(_QWORD *)(v2 + 256);
  if ( !v3 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v3 = *(_QWORD *)(v2 + 256);
  }
  if ( (SOS_OS_sm_osProcessStatus & 0x200) == 0 )
  {
    SOS_OS::sm_SOSProcessGlobals = g_SosProcessConfiguration;
    _set_se_translator(SOS_SEHTranslator);
    set_terminate(ex_terminator);
    set_unexpected(ex_terminator);
    _set_new_handler(SOS_OS::OutOfMemoryHandler);
    IsHardwareSupported();
    ModuleHandleW = SOS_OS::sm_hmodSQLOS;
    if ( SOS_OS::sm_hmodSQLOS
      || (ModuleHandleW = GetModuleHandleW(SOS_OS_SOSDllName), (SOS_OS::sm_hmodSQLOS = ModuleHandleW) != 0) )
    {
      ProcAddress = GetProcAddress(ModuleHandleW, "SetDllMainCallback");
      if ( ProcAddress )
      {
        SOS_OS_BootEvent = CreateEventW(0, 1, 0, 0);
        if ( SOS_OS_BootEvent )
        {
          ((void (__fastcall *)(__int64 (__fastcall *)(HINSTANCE, unsigned int, void *)))ProcAddress)(SystemThread::DllMainCallback);
          SOS_OS::QueryIsHypervisorEnabledInternal((struct SOS_OS::HypervisorInfo *)v49);
          if ( v49[0] )
          {
            v6 = SOS_PublicGlobals::sm_osStatus | 0x400;
            SOS_PublicGlobals::sm_osStatus |= 0x400u;
            if ( v49[1] )
              SOS_PublicGlobals::sm_osStatus = v6 | 0x4000;
          }
          SOS_OS_sm_osProcessStatus |= 0x200u;
        }
        else
        {
          MemoryNodes = 0x80000000;
        }
      }
      else
      {
        MemoryNodes = 0x80000000;
      }
    }
    else
    {
      MemoryNodes = 0x80000000;
    }
  }
  if ( (SOS_OS_sm_osProcessStatus & 1) == 0 && !MemoryNodes )
  {
    v7 = GetModuleHandleW(L"kernel32.dll");
    v8 = GetProcAddress(v7, "HeapSetInformation");
    v9 = byte_1007149B1;
    if ( (byte_1007149B1 & 8) == 0 && v8 )
    {
      ((void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))v8)(0, 1, 0, 0);
      v9 = byte_1007149B1;
    }
    if ( (byte_1007149B0 & 4) == 0
      && ((v9 & 0x20) != 0 || !Base_PublicGlobals::sm_invariantTscAvailable
                           && (SOS_PublicGlobals::sm_osOptions & 1) != 0) )
    {
      ptc = 0;
      if ( timeGetDevCaps(&ptc, 8u) )
        utassert_fail(1u, "TIMERR_NOERROR == res", "sostime.cpp", 74, 0);
      wPeriodMin = ptc.wPeriodMin;
      if ( ptc.wPeriodMin > 1 )
      {
        v11 = (void (*)(const wchar_t *, ...))SOS_PublicGlobals::sm_LogSystemMetadataRoutine;
        if ( !SOS_PublicGlobals::sm_LogSystemMetadataRoutine )
          v11 = SOS_OS_LogUnlocalizedRoutine;
        v11(L"Warning: Timer device resolution is greater than required. Required: %d. Found: %d.", 1, ptc.wPeriodMin);
        wPeriodMin = ptc.wPeriodMin;
      }
      TimePriv::sm_TimePeriodMin = wPeriodMin;
      TimePriv::TimeBeginPeriod();
    }
    SOS_OS::LoadNodeConfiguration();
    if ( !SOS_PublicGlobals::sm_MaxWorkers )
      SOS_OS::ConfigureMaxWorkers(0);
    MemoryNodes = SOS_OS::CreateMemoryNodes();
    if ( !MemoryNodes )
    {
      v12 = &qword_100720528[4 * *((unsigned __int16 *)SOS_OS_InitialMemoryNode + 64)];
      _BitScanForward64(&v13, ~(*v12 - 1) & *v12);
      v14 = *((_DWORD *)SOS_OS::sm_AffinityToCPUInfo + 64 * *((unsigned __int16 *)v12 + 4) + (unsigned int)v13);
      v15 = (SystemThread *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                           + (unsigned int)SystemThread_TlsOffset);
      *(_DWORD *)(*((_QWORD *)v15 + 32) + 76LL) = v14;
      SystemThread::ChangeCPUId(v15, v14);
      MemoryNodes = SOS_MemoryWorkSpace::Finalize();
      if ( !MemoryNodes )
      {
        MemoryNode_MemoryVisibleTargetPages = MemoryNode::GetCommittedPotentialPages();
        MemoryNode_MemoryTargetPages = MemoryNode_MemoryVisibleTargetPages;
        v16 = SOS_OS_TotalPagesCommittedRoutine();
        if ( MemoryNode_MemoryTargetPages - v16 + MemoryNode::GetTotalPagesFree() >= 0 )
        {
          v18 = SOS_OS_TotalPagesCommittedRoutine();
          v17 = MemoryNode_MemoryTargetPages - v18 + MemoryNode::GetTotalPagesFree();
        }
        else
        {
          v17 = 0;
        }
        MemoryNode_MemoryAvailablePages = v17;
        SOS_DebugBreakHookMgr::HookAll(1);
        BYTE1(Format) = 0;
        MemObject = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(1, 38, &qword_10071F300);
        SOS_OS::sm_pMemObj = MemObject;
        if ( !MemObject )
          return (unsigned int)-1073741824;
        v52 = 907;
        LOBYTE(Format) = 6;
        v20 = (*(__int64 (__fastcall **)(struct IMemObj *, __int64, const char *, __int64, int))(*(_QWORD *)MemObject
                                                                                               + 80LL))(
                MemObject,
                24,
                "Sql\\DkTemp\\sos\\src\\os_ext.cpp",
                907,
                Format);
        v54 = v20;
        if ( v20 )
        {
          v44 = (struct IMemObj *)v20;
          *(_QWORD *)v20 = 0;
          *(_QWORD *)(v20 + 8) = 0;
          *(_DWORD *)(v20 + 16) = 0;
        }
        else
        {
          v20 = 0;
        }
        SOS_OS::sm_pWaitAddrMgr = (SOS_WaitableAddressManager *)v20;
        if ( !v20 )
          return (unsigned int)-1073741824;
        MemoryNodes = PerProcessGlobals::Init(&SOS_OS::sm_SOSProcessGlobals);
        if ( !MemoryNodes )
          MemoryNodes = PerProcessGlobals::Init(&SOS_OS::sm_ClientProcessGlobals);
      }
    }
    if ( !MemoryNodes )
    {
      qword_100713910 = (__int64)SOS_OS::sm_pMemObj;
      if ( (*(_DWORD *)(v3 + 800) & 0x400) == 0 )
      {
        v21 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
            + (unsigned int)SystemThread_TlsOffset;
        v22 = *(struct SOS_Task ***)(v21 + 256);
        if ( !v22 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v22 = *(struct SOS_Task ***)(v21 + 256);
        }
        SystemThread::UnmakeMicroSOSThread((struct Worker *const)v22, v22[75], 1);
        SystemThread::MakeMiniSOSThread(0);
      }
      v23 = GetProcAddress(SOS_OS::sm_hmodSQLOS, "SetCreateSOSHostObjectCallback");
      if ( !v23 )
        return 0x80000000;
      MemoryNodes = SOS_ResourceManager::Init(&SOS_PublicGlobals::sm_ResourceManager);
      if ( !MemoryNodes )
      {
        ((void (__fastcall *)(void *))v23)(&ISOSHostImpl::CreateVersionedSOSHostObjectCallback);
        MemoryNodes = NodeManager::Init(&SOS_PublicGlobals::sm_NodeManager, SOS_OS::sm_pMemObj);
        if ( !MemoryNodes )
        {
          v24 = qword_100714178;
          if ( qword_100714178 && (*(_BYTE *)(qword_100714178 + 1568) & 0x10) != 0 )
            v24 = 0;
          qword_10071F2E8 = v24;
          (*(void (__fastcall **)(void *, _QWORD))(SOS_PublicGlobals::sm_osMemoryClerk + 32LL))(
            &SOS_PublicGlobals::sm_osMemoryClerk,
            0);
          TList<ResourceClerkList,ResourceClerk,8,ResourceClerkListSLock>::AppendElem(
            v24 + 1288,
            &SOS_PublicGlobals::sm_osMemoryClerk);
          qword_1007B9BE8 = v24;
          (*(void (__fastcall **)(void *, _QWORD))(SOS_MemoryWorkSpace::sm_descriptorClerk + 32LL))(
            &SOS_MemoryWorkSpace::sm_descriptorClerk,
            0);
          TList<ResourceClerkList,ResourceClerk,8,ResourceClerkListSLock>::AppendElem(
            v24 + 1288,
            &SOS_MemoryWorkSpace::sm_descriptorClerk);
          qword_1007BA2A8 = v24;
          (*(void (__fastcall **)(void *, _QWORD))(SOS_MemoryWorkSpace::sm_bitmapClerk + 32LL))(
            &SOS_MemoryWorkSpace::sm_bitmapClerk,
            0);
          TList<ResourceClerkList,ResourceClerk,8,ResourceClerkListSLock>::AppendElem(
            v24 + 1288,
            &SOS_MemoryWorkSpace::sm_bitmapClerk);
          SOS_OS::sm_OOMRingBuffer = (struct SOS_RingBuffer *)SOS_OS::CreateRingBuffer(4, 240, 128);
          if ( SOS_OS::sm_OOMRingBuffer )
          {
            SOS_OS::sm_SchedulerMonitorRingBuffer = (struct SOS_RingBuffer *)SOS_OS::CreateRingBuffer(8, 120, 256);
            if ( SOS_OS::sm_SchedulerMonitorRingBuffer )
            {
              Formata = (char *)SOS_MemoryBrokerRingRecord::SerializeRecord;
              SOS_OS::sm_MemoryBrokerRingBuffer = (struct SOS_RingBuffer *)SOS_OS::CreateRingBuffer(2, 96, 256);
              if ( SOS_OS::sm_MemoryBrokerRingBuffer )
              {
                v44 = SOS_OS::sm_pMemObj;
                v25 = SOS_OS::sm_pWaitAddrMgr;
                for ( i = 1; i < 1031; i *= 2 )
                  ;
                v27 = i;
                v52 = 836;
                v28 = 24LL * i;
                if ( !is_mul_ok(i, 0x18u) )
                  v28 = -1;
                if ( v28 == -1 )
                {
                  v29 = 0;
                  v54 = 0;
                }
                else
                {
                  LOBYTE(Formata) = 6;
                  v29 = (*(__int64 (__fastcall **)(struct IMemObj *, __int64, const char *, __int64, char *))(*(_QWORD *)SOS_OS::sm_pMemObj + 80LL))(
                          SOS_OS::sm_pMemObj,
                          v28,
                          "Sql\\DkTemp\\sos\\include\\common.inl",
                          836,
                          Formata);
                  v54 = v29;
                }
                if ( v29 )
                {
                  v30 = (_QWORD *)v29;
                  do
                  {
                    v30[1] = v30;
                    *v30 = v30;
                    v30[2] = 0;
                    v30 += 3;
                    --v27;
                  }
                  while ( v27 );
                }
                else
                {
                  v29 = 0;
                }
                if ( v29 )
                {
                  *((_DWORD *)v25 + 3) = i - 1;
                  *(_QWORD *)v25 = v29;
                  *((_DWORD *)v25 + 2) = i;
                  *((_DWORD *)v25 + 4) = 1;
                  MemoryNodes = IMemObj::InsertIntoMemObjList(SOS_OS::sm_pMemObj, 0xFFFFFFFFLL, 0);
                  v31 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                      + (unsigned int)SystemThread_TlsOffset;
                  v32 = *(_QWORD *)(v31 + 256);
                  if ( !v32 )
                  {
                    SystemThread::MakeMiniSOSThread(0);
                    v32 = *(_QWORD *)(v31 + 256);
                  }
                  *(_DWORD *)(v32 + 616) &= ~0x200u;
                  if ( !MemoryNodes )
                  {
                    MemoryNodes = MiniSOSThreadResourcesMgr::BindPreBootResources(&SOS_PublicGlobals::sm_MiniSOSThreadResourcesMgr);
                    if ( !MemoryNodes )
                    {
                      v33 = (SystemThread *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                             + (unsigned int)tls_index)
                                           + (unsigned int)SystemThread_TlsOffset);
                      SystemThread::ChangeCPUId(v33, *(_DWORD *)(*((_QWORD *)v33 + 32) + 76LL));
                      MemoryNodes = 0;
                      if ( SOS_PublicGlobals::sm_BootFinalize )
                        MemoryNodes = SOS_PublicGlobals::sm_BootFinalize();
                      if ( !MemoryNodes )
                      {
                        if ( Base_PublicGlobals::sm_invariantTscAvailable )
                        {
                          QueryPerformanceCounter(&PerformanceCount);
                          v34 = PerformanceCount;
                        }
                        else
                        {
                          v34.QuadPart = MEMORY[0x7FFE0008];
                        }
                        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))MemoryPoolManager::AdjustMemoryUsage)(
                          qword_100721010,
                          (LARGE_INTEGER)v34.QuadPart,
                          byte_1007149B0 & 0x40,
                          1);
                        if ( SOS_PublicGlobals::sm_isResourceManagerEnabled )
                        {
                          v35 = -1;
                          do
                            ++v35;
                          while ( *((_WORD *)&dword_1007158D4 + v35) );
                          v52 = qword_100715780(&dword_1007158D4, (unsigned int)(2 * v35));
                          TSimpleHashTable_EntryAccessor<SOS_ResourceGroup,ResManagerHashSLock,0,unsigned int>::TSimpleHashTable_EntryAccessor<SOS_ResourceGroup,ResManagerHashSLock,0,unsigned int>(
                            (unsigned int)&v51,
                            (unsigned int)qword_100718D08,
                            (unsigned int)&v52,
                            -1,
                            1);
                          v36 = v51;
                          ++*(_DWORD *)(v51 + 16);
                          qword_1007157D8 = *(_QWORD *)(v36 + 8);
                          **(_QWORD **)(v36 + 8) = &qword_1007157D0;
                          *(_QWORD *)(v36 + 8) = &qword_1007157D0;
                          qword_1007157D0 = v36;
                          v37 = *(_WORD *)(v36 + 16);
                          if ( v37 > *(_WORD *)(v36 + 34) )
                            *(_WORD *)(v36 + 34) = v37;
                          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                          {
                            v38 = rand();
                            if ( v38 == 5 * (v38 / 5) )
                              Spinlock<36,1,268435714>::UpdateStatSnapshot();
                          }
                          *(_QWORD *)(v36 + 24) = 0;
                        }
                        MemoryNodes = 0;
                        if ( SOS_PublicGlobals::sm_IsHotAddCpuSupportEnabled
                          && (SOS_PublicGlobals::sm_osStatus & 0x1080) == 0
                          && (SOS_PublicGlobals::sm_osStatus & 0x20) == 0
                          && (byte_1007149B0 & 8) == 0
                          && SOS_OS::sm_pfnSetProcessAffinityUpdateMode )
                        {
                          CurrentProcess = GetCurrentProcess();
                          SetProcessAffinityUpdateMode(CurrentProcess, 1u);
                        }
                        SOS_MemoryTopLevelBlockAllocator::TouchLargeMMFragment((SOS_MemoryTopLevelBlockAllocator *)&SOS_MemoryTopLevelBlockAllocator::sm_MemoryTopLevelBlockAllocator);
                        v45 = 0;
                        v47 = 0;
                        v48 = 0;
                        v46 = &SOS_PublicGlobals::sm_NodeManager;
                        *(_QWORD *)&v45 = TList<NodeManager,SOS_Node,16,TListSLock>::GetHead(&SOS_PublicGlobals::sm_NodeManager);
                        *((_QWORD *)&v45 + 1) = TList<GroupList,SOS_ResourceGroup,16,TListSLock>::GetTail(&SOS_PublicGlobals::sm_NodeManager);
                        while ( 1 )
                        {
                          for ( j = SOS_NodeEnumIncludeUninitializedNodes::GetNext(
                                      (SOS_NodeEnumIncludeUninitializedNodes *)&v45,
                                      j);
                                j;
                                j = SOS_NodeEnumIncludeUninitializedNodes::GetNext(
                                      (SOS_NodeEnumIncludeUninitializedNodes *)&v45,
                                      j) )
                          {
                            if ( (*((_BYTE *)j + 1568) & 0x10) == 0 )
                              break;
                          }
                          if ( !j )
                            break;
                          *(_DWORD *)(*((_QWORD *)j + 22) + 1572LL) &= ~1u;
                        }
                        if ( SOS_OS_DACNode )
                          *(_DWORD *)(*((_QWORD *)SOS_OS_DACNode + 22) + 1572LL) &= ~1u;
                        SOS_OS_sm_osProcessStatus |= 1u;
                        SetEvent(SOS_OS_BootEvent);
                        SOS_NodeEnumIncludeUninitializedNodes::~SOS_NodeEnumIncludeUninitializedNodes((SOS_NodeEnumIncludeUninitializedNodes *)&v45);
                      }
                    }
                  }
                  return MemoryNodes;
                }
              }
            }
          }
          return (unsigned int)-1073741824;
        }
      }
    }
  }
  return MemoryNodes;
}

```

## disassembly

```asm
0x1004b8080  push    rbp
0x1004b8082  push    rbx
0x1004b8083  push    rsi
0x1004b8084  push    rdi
0x1004b8085  push    r12
0x1004b8087  push    r14
0x1004b8089  push    r15
0x1004b808b  lea     rbp, [rsp-27h]
0x1004b8090  sub     rsp, 0B0h
0x1004b8097  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFEh
0x1004b809f  xor     ebx, ebx
0x1004b80a1  mov     edi, ebx
0x1004b80a3  mov     rcx, gs:58h
0x1004b80ac  mov     eax, cs:_tls_index
0x1004b80b2  mov     esi, cs:SystemThread_TlsOffset
0x1004b80b8  add     rsi, [rcx+rax*8]
0x1004b80bc  mov     r14, [rsi+100h]
0x1004b80c3  test    r14, r14
0x1004b80c6  jnz     short loc_1004B80D6
0x1004b80c8  xor     ecx, ecx; void *
0x1004b80ca  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004b80cf  mov     r14, [rsi+100h]
0x1004b80d6  mov     r15, rbx
0x1004b80d9  test    cs:?SOS_OS_sm_osProcessStatus@@3KA, 200h; ulong SOS_OS_sm_osProcessStatus
0x1004b80e3  jnz     loc_1004B81E4
0x1004b80e9  lea     rax, ?g_SosProcessConfiguration@@3V?$SOS_ProcessConfigImpl@$0A@@@A; SOS_ProcessConfigImpl<0> g_SosProcessConfiguration
0x1004b80f0  mov     cs:?sm_SOSProcessGlobals@SOS_OS@@0VPerProcessGlobals@@A, rax; PerProcessGlobals SOS_OS::sm_SOSProcessGlobals
0x1004b80f7  lea     rcx, ?SOS_SEHTranslator@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SOS_SEHTranslator(uint,_EXCEPTION_POINTERS *)
0x1004b80fe  call    cs:__imp__set_se_translator
0x1004b8104  lea     rcx, ?ex_terminator@@YAXXZ; ex_terminator(void)
0x1004b810b  call    cs:__imp_set_terminate
0x1004b8111  lea     rcx, ?ex_terminator@@YAXXZ; ex_terminator(void)
0x1004b8118  call    cs:__imp_set_unexpected
0x1004b811e  lea     rcx, ?OutOfMemoryHandler@SOS_OS@@SAH_K@Z; NewHandler
0x1004b8125  call    cs:__imp__set_new_handler
0x1004b812b  call    cs:__imp_?IsHardwareSupported@@YA?AW4HardwareCheckResult@@XZ; IsHardwareSupported(void)
0x1004b8131  mov     rax, cs:?sm_hmodSQLOS@SOS_OS@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * SOS_OS::sm_hmodSQLOS
0x1004b8138  test    rax, rax
0x1004b813b  jnz     short loc_1004B8160
0x1004b813d  mov     rcx, cs:?SOS_OS_SOSDllName@@3PEA_WEA; lpModuleName
0x1004b8144  call    cs:__imp_GetModuleHandleW
0x1004b814a  mov     cs:?sm_hmodSQLOS@SOS_OS@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * SOS_OS::sm_hmodSQLOS
0x1004b8151  test    rax, rax
0x1004b8154  jnz     short loc_1004B8160
0x1004b8156  mov     edi, 80000000h
0x1004b815b  jmp     loc_1004B81E4
0x1004b8160  lea     rdx, aSetdllmaincall; "SetDllMainCallback"
0x1004b8167  mov     rcx, rax; hModule
0x1004b816a  call    cs:__imp_GetProcAddress
0x1004b8170  mov     rsi, rax
0x1004b8173  test    rax, rax
0x1004b8176  jnz     short loc_1004B817F
0x1004b8178  mov     edi, 80000000h
0x1004b817d  jmp     short loc_1004B81E4
0x1004b817f  xor     r9d, r9d; lpName
0x1004b8182  xor     r8d, r8d; bInitialState
0x1004b8185  lea     edx, [r9+1]; bManualReset
0x1004b8189  xor     ecx, ecx; lpEventAttributes
0x1004b818b  call    cs:__imp_CreateEventW
0x1004b8191  mov     cs:?SOS_OS_BootEvent@@3PEAXEA, rax; void * SOS_OS_BootEvent
0x1004b8198  test    rax, rax
0x1004b819b  jnz     short loc_1004B81A4
0x1004b819d  mov     edi, 80000000h
0x1004b81a2  jmp     short loc_1004B81E4
0x1004b81a4  lea     rcx, ?DllMainCallback@SystemThread@@SAHPEAUHINSTANCE__@@KPEAX@Z; SystemThread::DllMainCallback(HINSTANCE__ *,ulong,void *)
0x1004b81ab  call    rsi
0x1004b81ad  lea     rcx, [rbp+57h+var_78]; struct SOS_OS::HypervisorInfo *
0x1004b81b1  call    ?QueryIsHypervisorEnabledInternal@SOS_OS@@SAXPEAUHypervisorInfo@1@@Z; SOS_OS::QueryIsHypervisorEnabledInternal(SOS_OS::HypervisorInfo *)
0x1004b81b6  cmp     [rbp+57h+var_78], ebx
0x1004b81b9  jz      short loc_1004B81DA
0x1004b81bb  mov     eax, cs:?sm_osStatus@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStatus
0x1004b81c1  bts     eax, 0Ah
0x1004b81c5  mov     cs:?sm_osStatus@SOS_PublicGlobals@@2KA, eax; ulong SOS_PublicGlobals::sm_osStatus
0x1004b81cb  cmp     [rbp+57h+var_74], ebx
0x1004b81ce  jz      short loc_1004B81DA
0x1004b81d0  bts     eax, 0Eh
0x1004b81d4  mov     cs:?sm_osStatus@SOS_PublicGlobals@@2KA, eax; ulong SOS_PublicGlobals::sm_osStatus
0x1004b81da  or      cs:?SOS_OS_sm_osProcessStatus@@3KA, 200h; ulong SOS_OS_sm_osProcessStatus
0x1004b81e4  test    byte ptr cs:?SOS_OS_sm_osProcessStatus@@3KA, 1; ulong SOS_OS_sm_osProcessStatus
0x1004b81eb  jnz     loc_1004B8A31
0x1004b81f1  test    edi, edi
0x1004b81f3  jnz     loc_1004B8A31
0x1004b81f9  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1004b8200  call    cs:__imp_GetModuleHandleW
0x1004b8206  mov     rcx, rax; hModule
0x1004b8209  lea     rdx, aHeapsetinforma; "HeapSetInformation"
0x1004b8210  call    cs:__imp_GetProcAddress
0x1004b8216  mov     r10, rax
0x1004b8219  movzx   eax, cs:byte_1007149B1
0x1004b8220  test    al, 8
0x1004b8222  jnz     short loc_1004B823E
0x1004b8224  test    r10, r10
0x1004b8227  jz      short loc_1004B823E
0x1004b8229  xor     r9d, r9d
0x1004b822c  xor     r8d, r8d
0x1004b822f  lea     edx, [rdi+1]
0x1004b8232  xor     ecx, ecx
0x1004b8234  call    r10
0x1004b8237  movzx   eax, cs:byte_1007149B1
0x1004b823e  test    cs:byte_1007149B0, 4
0x1004b8245  jnz     loc_1004B82D5
0x1004b824b  test    al, 20h
0x1004b824d  jnz     short loc_1004B8260
0x1004b824f  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, ebx; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004b8255  jnz     short loc_1004B82D5
0x1004b8257  test    byte ptr cs:?sm_osOptions@SOS_PublicGlobals@@2KA, 1; ulong SOS_PublicGlobals::sm_osOptions
0x1004b825e  jz      short loc_1004B82D5
0x1004b8260  mov     qword ptr [rbp+57h+ptc.wPeriodMin], rbx
0x1004b8264  mov     edx, 8; cbtc
0x1004b8269  lea     rcx, [rbp+57h+ptc]; ptc
0x1004b826d  call    cs:__imp_timeGetDevCaps
0x1004b8273  test    eax, eax
0x1004b8275  jz      short loc_1004B8299
0x1004b8277  mov     [rsp+0E0h+Format], rbx; Format
0x1004b827c  mov     r9d, 4Ah ; 'J'; int
0x1004b8282  lea     r8, aSostimeCpp; "sostime.cpp"
0x1004b8289  lea     rdx, aTimerrNoerrorR; "TIMERR_NOERROR == res"
0x1004b8290  lea     ecx, [r9-49h]; unsigned int
0x1004b8294  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1004b8299  mov     rax, qword ptr [rbp+57h+ptc.wPeriodMin]
0x1004b829d  cmp     eax, 1
0x1004b82a0  jbe     short loc_1004B82CA
0x1004b82a2  mov     r9, cs:?sm_LogSystemMetadataRoutine@SOS_PublicGlobals@@2P6AXPEB_WZZEA; void (*SOS_PublicGlobals::sm_LogSystemMetadataRoutine)(wchar_t const *,...)
0x1004b82a9  test    r9, r9
0x1004b82ac  cmovz   r9, cs:?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x1004b82b4  mov     r8d, eax
0x1004b82b7  mov     edx, 1
0x1004b82bc  lea     rcx, aWarningTimerDe; "Warning: Timer device resolution is gre"...
0x1004b82c3  call    r9
0x1004b82c6  mov     rax, qword ptr [rbp+57h+ptc.wPeriodMin]
0x1004b82ca  mov     cs:?sm_TimePeriodMin@TimePriv@@0KA, eax; ulong TimePriv::sm_TimePeriodMin
0x1004b82d0  call    ?TimeBeginPeriod@TimePriv@@CAXXZ; TimePriv::TimeBeginPeriod(void)
0x1004b82d5  call    ?LoadNodeConfiguration@SOS_OS@@CAXXZ; SOS_OS::LoadNodeConfiguration(void)
0x1004b82da  mov     eax, cs:?sm_MaxWorkers@SOS_PublicGlobals@@2IA; uint SOS_PublicGlobals::sm_MaxWorkers
0x1004b82e0  test    eax, eax
0x1004b82e2  jnz     short loc_1004B82EB
0x1004b82e4  xor     ecx, ecx; unsigned int
0x1004b82e6  call    ?ConfigureMaxWorkers@SOS_OS@@SAHI@Z; SOS_OS::ConfigureMaxWorkers(uint)
0x1004b82eb  call    ?CreateMemoryNodes@SOS_OS@@CA?AW4SOS_RESULT@@XZ; SOS_OS::CreateMemoryNodes(void)
0x1004b82f0  mov     edi, eax
0x1004b82f2  mov     r12d, 80h
0x1004b82f8  test    eax, eax
0x1004b82fa  jnz     loc_1004B848C
0x1004b8300  mov     rax, cs:?SOS_OS_InitialMemoryNode@@3PEAVMemoryNode@@EA; MemoryNode * SOS_OS_InitialMemoryNode
0x1004b8307  movzx   edx, word ptr [rax+80h]
0x1004b830e  shl     rdx, 5
0x1004b8312  lea     rax, qword_100720528
0x1004b8319  add     rdx, rax
0x1004b831c  mov     rcx, [rdx]
0x1004b831f  lea     rax, [rcx-1]
0x1004b8323  not     rax
0x1004b8326  and     rcx, rax
0x1004b8329  bsf     rax, rcx
0x1004b832d  mov     [rbp+57h+arg_0], eax
0x1004b8330  movzx   ecx, word ptr [rdx+8]
0x1004b8334  shl     rcx, 6
0x1004b8338  add     rcx, rax
0x1004b833b  mov     ecx, ecx
0x1004b833d  mov     rax, cs:?sm_AffinityToCPUInfo@SOS_OS@@0PEAKEA; ulong * SOS_OS::sm_AffinityToCPUInfo
0x1004b8344  mov     r8d, [rax+rcx*4]
0x1004b8348  mov     rdx, gs:58h
0x1004b8351  mov     eax, cs:_tls_index
0x1004b8357  mov     ecx, cs:SystemThread_TlsOffset
0x1004b835d  add     rcx, [rdx+rax*8]; this
0x1004b8361  mov     rax, [rcx+100h]
0x1004b8368  mov     [rax+4Ch], r8d
0x1004b836c  mov     edx, r8d; unsigned int
0x1004b836f  call    ?ChangeCPUId@SystemThread@@QEAAKK@Z; SystemThread::ChangeCPUId(ulong)
0x1004b8374  call    ?Finalize@SOS_MemoryWorkSpace@@SA?AW4SOS_RESULT@@XZ; SOS_MemoryWorkSpace::Finalize(void)
0x1004b8379  mov     edi, eax
0x1004b837b  test    eax, eax
0x1004b837d  jnz     loc_1004B848C
0x1004b8383  call    ?GetCommittedPotentialPages@MemoryNode@@SA_JXZ; MemoryNode::GetCommittedPotentialPages(void)
0x1004b8388  mov     cs:?MemoryNode_MemoryVisibleTargetPages@@3_JA, rax; __int64 MemoryNode_MemoryVisibleTargetPages
0x1004b838f  mov     cs:?MemoryNode_MemoryTargetPages@@3_JA, rax; __int64 MemoryNode_MemoryTargetPages
0x1004b8396  call    cs:?SOS_OS_TotalPagesCommittedRoutine@@3P6A_JXZEA; MemoryNode::GetTotalPagesCommittedInternal(void)
0x1004b839c  mov     rdi, rax
0x1004b839f  call    ?GetTotalPagesFree@MemoryNode@@SA_JXZ; MemoryNode::GetTotalPagesFree(void)
0x1004b83a4  mov     rcx, rax
0x1004b83a7  mov     rax, cs:?MemoryNode_MemoryTargetPages@@3_JA; __int64 MemoryNode_MemoryTargetPages
0x1004b83ae  sub     rax, rdi
0x1004b83b1  add     rcx, rax
0x1004b83b4  jns     short loc_1004B83BB
0x1004b83b6  mov     rcx, rbx
0x1004b83b9  jmp     short loc_1004B83D9
0x1004b83bb  call    cs:?SOS_OS_TotalPagesCommittedRoutine@@3P6A_JXZEA; MemoryNode::GetTotalPagesCommittedInternal(void)
0x1004b83c1  mov     rdi, rax
0x1004b83c4  call    ?GetTotalPagesFree@MemoryNode@@SA_JXZ; MemoryNode::GetTotalPagesFree(void)
0x1004b83c9  mov     rcx, rax
0x1004b83cc  mov     rax, cs:?MemoryNode_MemoryTargetPages@@3_JA; __int64 MemoryNode_MemoryTargetPages
0x1004b83d3  sub     rax, rdi
0x1004b83d6  add     rcx, rax
0x1004b83d9  mov     cs:?MemoryNode_MemoryAvailablePages@@3_JA, rcx; __int64 MemoryNode_MemoryAvailablePages
0x1004b83e0  mov     ecx, 1
0x1004b83e5  call    ?HookAll@SOS_DebugBreakHookMgr@@SA?AW4SOS_RESULT@@W4Action@1@@Z; SOS_DebugBreakHookMgr::HookAll(SOS_DebugBreakHookMgr::Action)
0x1004b83ea  mov     r9d, 8
0x1004b83f0  mov     word ptr [rsp+0E0h+Format], r12w
0x1004b83f6  lea     r8, qword_10071F300
0x1004b83fd  lea     edx, [r9+1Eh]
0x1004b8401  lea     ecx, [rdx-25h]
0x1004b8404  call    ?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z; MemoryObjectFactory::CreateMemObject(SOSHOST_MEMOBJ_ID,ulong,PageAllocator *,short,short)
0x1004b8409  mov     rcx, rax
0x1004b840c  mov     cs:?sm_pMemObj@SOS_OS@@0PEAVIMemObj@@EA, rax; IMemObj * SOS_OS::sm_pMemObj
0x1004b8413  test    rax, rax
0x1004b8416  jz      loc_1004B8A2C
0x1004b841c  mov     [rbp+57h+arg_8], 38Bh
0x1004b8423  mov     rax, [rax]
0x1004b8426  mov     byte ptr [rsp+0E0h+Format], 6
0x1004b842b  mov     r9d, 38Bh
0x1004b8431  lea     r8, aSqlDktempSosSr_18; "Sql\\DkTemp\\sos\\src\\os_ext.cpp"
0x1004b8438  mov     edx, 18h
0x1004b843d  call    qword ptr [rax+50h]
0x1004b8440  mov     [rbp+57h+arg_18], rax
0x1004b8444  test    rax, rax
0x1004b8447  jz      short loc_1004B8459
0x1004b8449  mov     [rbp+57h+var_A8], rax
0x1004b844d  mov     [rax], rbx
0x1004b8450  mov     [rax+8], rbx
0x1004b8454  mov     [rax+10h], ebx
0x1004b8457  jmp     short loc_1004B845C
0x1004b8459  mov     rax, rbx
0x1004b845c  mov     cs:?sm_pWaitAddrMgr@SOS_OS@@0PEAVSOS_WaitableAddressManager@@EA, rax; SOS_WaitableAddressManager * SOS_OS::sm_pWaitAddrMgr
0x1004b8463  test    rax, rax
0x1004b8466  jz      loc_1004B8A2C
0x1004b846c  lea     rcx, ?sm_SOSProcessGlobals@SOS_OS@@0VPerProcessGlobals@@A; PerProcessGlobals SOS_OS::sm_SOSProcessGlobals
0x1004b8473  call    ?Init@PerProcessGlobals@@QEAA?AW4SOS_RESULT@@XZ; PerProcessGlobals::Init(void)
0x1004b8478  mov     edi, eax
0x1004b847a  test    eax, eax
0x1004b847c  jnz     short loc_1004B848C
0x1004b847e  lea     rcx, ?sm_ClientProcessGlobals@SOS_OS@@0VPerProcessGlobals@@A; PerProcessGlobals SOS_OS::sm_ClientProcessGlobals
0x1004b8485  call    ?Init@PerProcessGlobals@@QEAA?AW4SOS_RESULT@@XZ; PerProcessGlobals::Init(void)
0x1004b848a  mov     edi, eax
0x1004b848c  test    edi, edi
0x1004b848e  jnz     loc_1004B8A31
0x1004b8494  mov     rax, cs:?sm_pMemObj@SOS_OS@@0PEAVIMemObj@@EA; IMemObj * SOS_OS::sm_pMemObj
0x1004b849b  mov     cs:qword_100713910, rax
0x1004b84a2  test    dword ptr [r14+320h], 400h
0x1004b84ad  jnz     short loc_1004B84FB
0x1004b84af  mov     rcx, gs:58h
0x1004b84b8  mov     eax, cs:_tls_index
0x1004b84be  mov     edi, cs:SystemThread_TlsOffset
0x1004b84c4  add     rdi, [rcx+rax*8]
0x1004b84c8  mov     rcx, [rdi+100h]; void *
0x1004b84cf  test    rcx, rcx
0x1004b84d2  jnz     short loc_1004B84E0
0x1004b84d4  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004b84d9  mov     rcx, [rdi+100h]; this
0x1004b84e0  mov     r8d, 1; int
0x1004b84e6  mov     rdx, [rcx+258h]; struct SOS_Task *
0x1004b84ed  call    ?UnmakeMicroSOSThread@SystemThread@@SAXQEAVWorker@@QEAVSOS_Task@@H@Z; SystemThread::UnmakeMicroSOSThread(Worker * const,SOS_Task * const,int)
0x1004b84f2  xor     ecx, ecx; void *
0x1004b84f4  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004b84f9  jmp     short loc_1004B8503
0x1004b84fb  test    edi, edi
0x1004b84fd  jnz     loc_1004B8A31
0x1004b8503  lea     rdx, aSetcreatesosho; "SetCreateSOSHostObjectCallback"
0x1004b850a  mov     rcx, cs:?sm_hmodSQLOS@SOS_OS@@0PEAUHINSTANCE__@@EA; hModule
0x1004b8511  call    cs:__imp_GetProcAddress
0x1004b8517  mov     r15, rax
0x1004b851a  test    rax, rax
0x1004b851d  jnz     short loc_1004B8529
0x1004b851f  mov     edi, 80000000h
0x1004b8524  jmp     loc_1004B8A31
0x1004b8529  lea     rcx, ?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A; SOS_ResourceManager SOS_PublicGlobals::sm_ResourceManager
0x1004b8530  call    ?Init@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@XZ; SOS_ResourceManager::Init(void)
0x1004b8535  mov     edi, eax
0x1004b8537  test    eax, eax
0x1004b8539  jnz     loc_1004B8A31
0x1004b853f  lea     rcx, ?CreateVersionedSOSHostObjectCallback@ISOSHostImpl@@SAJAEBU_GUID@@W4SOSHOST_CLIENTID@@PEB_WPEAPEAUISOSHost@@@Z; ISOSHostImpl::CreateVersionedSOSHostObjectCallback(_GUID const &,SOSHOST_CLIENTID,wchar_t const *,ISOSHost * *)
0x1004b8546  call    r15
0x1004b8549  mov     rdx, cs:?sm_pMemObj@SOS_OS@@0PEAVIMemObj@@EA; IMemObj * SOS_OS::sm_pMemObj
0x1004b8550  lea     r15, ?sm_NodeManager@SOS_PublicGlobals@@2VNodeManager@@A; NodeManager SOS_PublicGlobals::sm_NodeManager
0x1004b8557  mov     rcx, r15
0x1004b855a  call    ?Init@NodeManager@@QEAA?AW4SOS_RESULT@@PEAVIMemObj@@@Z; NodeManager::Init(IMemObj *)
0x1004b855f  mov     edi, eax
0x1004b8561  test    eax, eax
0x1004b8563  jnz     loc_1004B8A31
0x1004b8569  mov     rsi, cs:qword_100714178
0x1004b8570  test    rsi, rsi
0x1004b8573  jz      short loc_1004B8580
0x1004b8575  test    byte ptr [rsi+620h], 10h
0x1004b857c  cmovnz  rsi, rbx
0x1004b8580  mov     cs:qword_10071F2E8, rsi
0x1004b8587  xor     edx, edx
0x1004b8589  lea     rcx, ?sm_osMemoryClerk@SOS_PublicGlobals@@2VMemoryClerk@@A; MemoryClerk SOS_PublicGlobals::sm_osMemoryClerk
0x1004b8590  mov     rax, cs:?sm_osMemoryClerk@SOS_PublicGlobals@@2VMemoryClerk@@A; MemoryClerk SOS_PublicGlobals::sm_osMemoryClerk
0x1004b8597  call    qword ptr [rax+20h]
0x1004b859a  lea     rdx, ?sm_osMemoryClerk@SOS_PublicGlobals@@2VMemoryClerk@@A; MemoryClerk SOS_PublicGlobals::sm_osMemoryClerk
0x1004b85a1  lea     rcx, [rsi+508h]
0x1004b85a8  call    ?AppendElem@?$TList@VResourceClerkList@@VResourceClerk@@$07UResourceClerkListSLock@@@@QEAAXPEAVResourceClerk@@@Z; TList<ResourceClerkList,ResourceClerk,8,ResourceClerkListSLock>::AppendElem(ResourceClerk *)
0x1004b85ad  mov     cs:qword_1007B9BE8, rsi
0x1004b85b4  xor     edx, edx
0x1004b85b6  lea     rcx, ?sm_descriptorClerk@SOS_MemoryWorkSpace@@0VMemoryClerk@@A; MemoryClerk SOS_MemoryWorkSpace::sm_descriptorClerk
0x1004b85bd  mov     rax, cs:?sm_descriptorClerk@SOS_MemoryWorkSpace@@0VMemoryClerk@@A; MemoryClerk SOS_MemoryWorkSpace::sm_descriptorClerk
0x1004b85c4  call    qword ptr [rax+20h]
0x1004b85c7  lea     rdx, ?sm_descriptorClerk@SOS_MemoryWorkSpace@@0VMemoryClerk@@A; MemoryClerk SOS_MemoryWorkSpace::sm_descriptorClerk
0x1004b85ce  lea     rcx, [rsi+508h]
0x1004b85d5  call    ?AppendElem@?$TList@VResourceClerkList@@VResourceClerk@@$07UResourceClerkListSLock@@@@QEAAXPEAVResourceClerk@@@Z; TList<ResourceClerkList,ResourceClerk,8,ResourceClerkListSLock>::AppendElem(ResourceClerk *)
0x1004b85da  mov     cs:qword_1007BA2A8, rsi
0x1004b85e1  xor     edx, edx
  ... truncated ...
```
