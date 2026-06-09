# SOS_OS::InitOs(void)

- ea: `0x1004b1350`
- end: `0x1004b1dfe`
- name: `?InitOs@SOS_OS@@CAHXZ`
- size: `2734`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x100440fb0`

## callees

- `0x100403070`
- `0x10040e870`
- `0x100411fb0`
- `0x100412c80`
- `0x1004354a0`
- `0x100435660`
- `0x1004a49f0`
- `0x1004b1350`
- `0x1004b4120`
- `0x1004b4480`
- `0x1004b8b50`
- `0x1004b96d0`
- `0x10061547c`
- `0x1006157c0`
- `0x100615824`

## import_xrefs

- `ntdll!RtlCaptureStackBackTrace` at `0x1004b16fd`
- `KERNEL32!CreateEventW` at `0x1004b1789`
- `KERNEL32!CreateEventW` at `0x1004b1bae`
- `KERNEL32!CreateEventW` at `0x1004b1be7`
- `KERNEL32!CreateEventW` at `0x1004b1789`
- `KERNEL32!CreateEventW` at `0x1004b1bae`
- `KERNEL32!CreateEventW` at `0x1004b1be7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1004b1a22`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1004b1a22`
- `KERNEL32!GetLargePageMinimum` at `0x1004b18da`
- `KERNEL32!GetLargePageMinimum` at `0x1004b18e5`
- `KERNEL32!GetLargePageMinimum` at `0x1004b18da`
- `KERNEL32!GetLargePageMinimum` at `0x1004b18e5`
- `KERNEL32!CreateMutexW` at `0x1004b1c9e`
- `KERNEL32!CreateMutexW` at `0x1004b1c9e`
- `KERNEL32!SetProcessAffinityUpdateMode` at `0x1004b1d99`
- `KERNEL32!GetCurrentThreadStackLimits` at `0x1004b1d7c`
- `KERNEL32!GetCurrentThreadStackLimits` at `0x1004b1d7c`
- `KERNEL32!CreateMemoryResourceNotification` at `0x1004b1c4a`
- `KERNEL32!CreateMemoryResourceNotification` at `0x1004b1c59`
- `KERNEL32!CreateMemoryResourceNotification` at `0x1004b1c4a`
- `KERNEL32!CreateMemoryResourceNotification` at `0x1004b1c59`
- `KERNEL32!QueryMemoryResourceNotification` at `0x1004b1c30`
- `KERNEL32!QueryPerformanceCounter` at `0x1004b1a00`
- `KERNEL32!QueryPerformanceCounter` at `0x1004b1a66`
- `KERNEL32!QueryPerformanceCounter` at `0x1004b1a00`
- `KERNEL32!QueryPerformanceCounter` at `0x1004b1a66`
- `KERNEL32!GetModuleHandleW` at `0x1004b13af`
- `KERNEL32!GetModuleHandleW` at `0x1004b13bf`
- `KERNEL32!GetModuleHandleW` at `0x1004b13af`
- `KERNEL32!GetModuleHandleW` at `0x1004b13bf`
- `KERNEL32!GetProcAddress` at `0x1004b1715`
- `KERNEL32!GetProcAddress` at `0x1004b172c`
- `KERNEL32!GetProcAddress` at `0x1004b1743`
- `KERNEL32!GetProcAddress` at `0x1004b175a`
- `KERNEL32!GetProcAddress` at `0x1004b1715`
- `KERNEL32!GetProcAddress` at `0x1004b172c`
- `KERNEL32!GetProcAddress` at `0x1004b1743`
- `KERNEL32!GetProcAddress` at `0x1004b175a`
- `KERNEL32!LoadLibraryW` at `0x1004b13cf`
- `KERNEL32!LoadLibraryW` at `0x1004b13cf`
- `KERNEL32!CloseHandle` at `0x1004b1538`
- `KERNEL32!CloseHandle` at `0x1004b1d0d`
- `KERNEL32!CloseHandle` at `0x1004b1d2a`
- `KERNEL32!CloseHandle` at `0x1004b1538`
- `KERNEL32!CloseHandle` at `0x1004b1d0d`
- `KERNEL32!CloseHandle` at `0x1004b1d2a`
- `KERNEL32!GetLastError` at `0x1004b1520`
- `KERNEL32!GetLastError` at `0x1004b1cd9`
- `KERNEL32!GetLastError` at `0x1004b1d15`
- `KERNEL32!GetLastError` at `0x1004b1d20`
- `KERNEL32!GetLastError` at `0x1004b1520`
- `KERNEL32!GetLastError` at `0x1004b1cd9`
- `KERNEL32!GetLastError` at `0x1004b1d15`
- `KERNEL32!GetLastError` at `0x1004b1d20`
- `KERNEL32!VirtualAlloc` at `0x1004b17cb`
- `KERNEL32!VirtualAlloc` at `0x1004b17cb`
- `KERNEL32!GetCurrentProcess` at `0x1004b14b2`
- `KERNEL32!GetCurrentProcess` at `0x1004b1cbd`
- `KERNEL32!GetCurrentProcess` at `0x1004b14b2`
- `KERNEL32!GetCurrentProcess` at `0x1004b1cbd`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1004b151a`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1004b151a`
- `ADVAPI32!LookupPrivilegeValueW` at `0x1004b14df`
- `ADVAPI32!LookupPrivilegeValueW` at `0x1004b14df`
- `ADVAPI32!GetLengthSid` at `0x1004b1d6e`
- `ADVAPI32!GetLengthSid` at `0x1004b1d6e`
- `ADVAPI32!GetTokenInformation` at `0x1004b1cff`
- `ADVAPI32!GetTokenInformation` at `0x1004b1d57`
- `ADVAPI32!GetTokenInformation` at `0x1004b1cff`
- `ADVAPI32!GetTokenInformation` at `0x1004b1d57`
- `ADVAPI32!OpenProcessToken` at `0x1004b14c4`
- `ADVAPI32!OpenProcessToken` at `0x1004b1ccf`
- `ADVAPI32!OpenProcessToken` at `0x1004b14c4`
- `ADVAPI32!OpenProcessToken` at `0x1004b1ccf`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004b1d35`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004b1d35`

## string_xrefs

- `0x1004b13b8`: `ntdll.dll`
- `0x1004b17ad`: `Failed to create event for handling Virtual Memory pressureresponding to memory pressure might not work \n`
- `0x1004b1907`: `Large Page Extensions enabled.\nLarge Page Granularity: %Iu \n`
- `0x1004b1925`: `Cannot use Large Page Extensions: lock memory privilege was not granted.\n`
- `0x1004b13a8`: `kernel32.dll`
- `0x1004b13c8`: `psapi.dll`
- `0x1004b14d6`: `SeLockMemoryPrivilege`
- `0x1004b170b`: `SetThreadStackGuarantee`
- `0x1004b1c0b`: `Failed to create idle server event\n`
- `0x1004b1bd2`: `Failed to create event for handling Memory pressureresponding to memory pressure might not work \n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 SOS_OS::InitOs(void)
{
  HMODULE ModuleHandleW; // rsi
  HMODULE v1; // r14
  HMODULE LibraryW; // r15
  HANDLE CurrentProcess; // rax
  void *v4; // rbx
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // r8
  unsigned __int64 v7; // r11
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // r8
  unsigned __int64 v11; // r8
  void (*v12)(const wchar_t *, ...); // rax
  char *v13; // rax
  __int64 v14; // rdx
  unsigned __int64 v15; // r8
  int v16; // ecx
  unsigned int v17; // eax
  SIZE_T LargePageMinimum; // rax
  void (*v19)(const wchar_t *, ...); // r8
  void (*v20)(const wchar_t *, ...); // rax
  unsigned int v21; // eax
  int v22; // ecx
  unsigned int v23; // eax
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rcx
  void *v26; // rsp
  void *v27; // rsp
  void **p_Luid; // r9
  _LUID v29; // rax
  struct MemoryNode *FreeFloatingNode; // rax
  struct MemoryNode *v31; // rbx
  LARGE_INTEGER v32; // rcx
  void (*v33)(const wchar_t *, ...); // rax
  void (*v34)(const wchar_t *, ...); // rax
  HANDLE v35; // rax
  PSID *v36; // rbx
  signed __int32 v38[8]; // [rsp+0h] [rbp-40h] BYREF
  _LUID Luid; // [rsp+40h] [rbp+0h] BYREF
  DWORD TokenInformationLength; // [rsp+48h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+58h] [rbp+18h] BYREF
  __int64 v43; // [rsp+60h] [rbp+20h] BYREF
  __int128 v44; // [rsp+70h] [rbp+30h]
  __int64 v45; // [rsp+B0h] [rbp+70h]
  _TOKEN_PRIVILEGES NewState; // [rsp+B8h] [rbp+78h] BYREF
  _OWORD v47[8]; // [rsp+D0h] [rbp+90h] BYREF
  _BYTE v48[6048]; // [rsp+150h] [rbp+110h] BYREF

  v45 = -2;
  SOS_PublicGlobals::sm_excGlobalCookie = _security_cookie;
  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  v1 = GetModuleHandleW(L"ntdll.dll");
  LibraryW = LoadLibraryW(L"psapi.dll");
  if ( dword_1007BC3D0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 8LL) )
  {
    Init_thread_header(&dword_1007BC3D0);
    if ( dword_1007BC3D0 == -1 )
    {
      qword_1007BC3D8 = &GroupNumaConfig::`vftable';
      atexit(OsNumaConfig::StaticInit_::_2_::_dynamic_atexit_destructor_for__sm_groupNumaConfig__);
      Init_thread_footer(&dword_1007BC3D0);
    }
  }
  OsNumaConfig::sm_instance = (struct OsNumaConfig *)&qword_1007BC3D8;
  (*(void (__fastcall **)(void *, _QWORD))(qword_1007BC3D8 + 104LL))(&qword_1007BC3D8, 0);
  v47[0] = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v47[1] = v47[0];
  v47[2] = v47[0];
  v47[3] = v47[0];
  v47[4] = v47[0];
  v47[5] = v47[0];
  v47[6] = v47[0];
  v47[7] = v47[0];
  SOS_OS::LoadHardwareConfig((const struct SystemAffinity *)v47);
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xF01FFu, &TokenHandle) )
  {
    v4 = TokenHandle;
    if ( LookupPrivilegeValueW(0, L"SeLockMemoryPrivilege", &Luid) )
    {
      NewState.PrivilegeCount = 1;
      NewState.Privileges[0].Luid = Luid;
      NewState.Privileges[0].Attributes = 2;
      AdjustTokenPrivileges(v4, 0, &NewState, 0x10u, 0, 0);
      if ( !GetLastError() )
        SOS_PublicGlobals::sm_osStatus |= 0x800u;
    }
    CloseHandle(TokenHandle);
  }
  SOS_OS::DetermineCpuSpeed();
  v5 = -1;
  v6 = 15000 * SOS_PublicGlobals::sm_CpuTicksPerMillisecond;
  if ( !Base_PublicGlobals::sm_invariantTscAvailable )
  {
    v7 = 40000;
    SOS_PublicGlobals::sm_QuantumLengthInMS = 40000;
    SOS_OS_MaxQuantumLength = v6 / 0x3E8;
    SOS_OS::sm_MinQuantumLength = 100 * SOS_PublicGlobals::sm_CpuTicksPerMillisecond / 0x3E8;
LABEL_13:
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
      v8 = 1000 * v7 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
    else
      v8 = v7 / 0x2710;
    goto LABEL_16;
  }
  v7 = (4 * Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart + 999) / 0x3E8uLL;
  SOS_PublicGlobals::sm_QuantumLengthInMS = v7;
  SOS_OS_MaxQuantumLength = v6 / 0x3E8;
  SOS_OS::sm_MinQuantumLength = 100 * SOS_PublicGlobals::sm_CpuTicksPerMillisecond / 0x3E8;
  if ( v7 != -1 )
    goto LABEL_13;
  v8 = -1;
LABEL_16:
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
    v9 = (Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart * 1000 * v8 + 999) / 0x3E8;
  else
    v9 = 10000000 * v8;
  SOS_OS::sm_QuantumThiefLength = v9;
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
    v10 = (Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart
         * (unsigned __int64)SOS_PublicGlobals::sm_IdleTimeOut
         + 999)
        / 0x3E8;
  else
    v10 = 10000LL * SOS_PublicGlobals::sm_IdleTimeOut;
  SOS_PublicGlobals::sm_IdleTimeOutTicks = v10;
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
    v11 = (Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart
         * (unsigned __int64)SOS_PublicGlobals::sm_IdleOfflineTimeOut
         + 999)
        / 0x3E8;
  else
    v11 = 10000LL * SOS_PublicGlobals::sm_IdleOfflineTimeOut;
  SOS_PublicGlobals::sm_IdleOfflineTimeOutTicks = v11;
  SOS_OS::CalculateAndSetLpPerPp();
  SOS_OS_StackBackTraceRoutine = RtlCaptureStackBackTrace;
  SOS_OS::sm_SetThreadStackGuarantee = (int (*)(unsigned int *))GetProcAddress(ModuleHandleW, "SetThreadStackGuarantee");
  SOS_OS_QueryWorkingSetExRoutine = (int (*)(void *, void *, unsigned int))GetProcAddress(LibraryW, "QueryWorkingSetEx");
  SOS_OS::sm_GetSystemTimes = (int (*)(struct _FILETIME *, struct _FILETIME *, struct _FILETIME *))GetProcAddress(
                                                                                                     ModuleHandleW,
                                                                                                     "GetSystemTimes");
  SOS_OS::sm_NtQuerySystemInformation = (int (*)(int, void *, unsigned int, unsigned int *))GetProcAddress(
                                                                                              v1,
                                                                                              "NtQuerySystemInformation");
  MemoryNode::UpdateGlobalMemoryStatus();
  LODWORD(dwSize) = 0x80000;
  dword_10072F848 = 0;
  hEvent = CreateEventW(0, 1, 0, 0);
  if ( !hEvent )
  {
    v12 = (void (*)(const wchar_t *, ...))SOS_PublicGlobals::sm_LogSystemMetadataRoutine;
    if ( !SOS_PublicGlobals::sm_LogSystemMetadataRoutine )
      v12 = SOS_OS_LogUnlocalizedRoutine;
    v12(L"Failed to create event for handling Virtual Memory pressureresponding to memory pressure might not work \n");
  }
  v13 = (char *)VirtualAlloc(0, 0x100000u, 0x1000u, 4u);
  v15 = (unsigned __int64)v13;
  if ( v13 )
  {
    qword_10072F8C8 = 0x100000;
    qword_10072F8B8 = 0x2000;
    qword_10072F8C0 = (__int64)v13;
    MemoryNode::sm_emergencyPageAllocator = 0;
    dword_10072F8B4 = 0;
    if ( v13 < v13 + 0x100000 )
    {
      do
      {
        *(_QWORD *)v15 = 0;
        *(_QWORD *)(v15 + 8) = 0;
        *(_QWORD *)v15 = off_10072F8D8;
        *((_QWORD *)off_10072F8D8 + 1) = v15;
        off_10072F8D8 = (_UNKNOWN *)v15;
        *(_QWORD *)(v15 + 8) = &off_10072F8D8;
        v15 += 0x2000LL;
        ++dword_10072F8B4;
      }
      while ( v15 < qword_10072F8C0 + qword_10072F8C8 );
    }
    v14 = 0x100000 % (unsigned int)dword_1007153CC;
    _InterlockedExchangeAdd64(&MemoryNode_OSVasPagesReserved, 0x100000 / (unsigned int)dword_1007153CC);
    _InterlockedExchangeAdd64(&MemoryNode_OSVasPagesCommitted, 0x100000 / (unsigned int)dword_1007153CC);
  }
  v16 = dword_10072F380;
  do
  {
    v17 = v16 & 0xFFFFFFFE;
    v44 = MemoryNode::sm_ms64atomic;
    _InterlockedOr(v38, 0);
    v16 = dword_10072F380;
  }
  while ( v17 != dword_10072F380 );
  MemoryNode::sm_startupTotalPhysicalPages = *((_QWORD *)&v44 + 1) >> 13;
  if ( (SOS_PublicGlobals::sm_osStatus & 0x800) != 0 && GetLargePageMinimum() )
  {
    LargePageMinimum = GetLargePageMinimum();
    MemoryNode_LargePageSize = LargePageMinimum;
    v19 = (void (*)(const wchar_t *, ...))SOS_PublicGlobals::sm_LogSystemMetadataRoutine;
    if ( !SOS_PublicGlobals::sm_LogSystemMetadataRoutine )
      v19 = SOS_OS_LogUnlocalizedRoutine;
    v19(L"Large Page Extensions enabled.\nLarge Page Granularity: %Iu \n", LargePageMinimum);
  }
  else
  {
    v20 = (void (*)(const wchar_t *, ...))SOS_PublicGlobals::sm_LogSystemMetadataRoutine;
    if ( !SOS_PublicGlobals::sm_LogSystemMetadataRoutine )
      v20 = SOS_OS_LogUnlocalizedRoutine;
    v20(L"Cannot use Large Page Extensions: lock memory privilege was not granted.\n", v14, v15);
  }
  v21 = SOS_PublicGlobals::sm_osStatus;
  if ( (SOS_PublicGlobals::sm_osStatus & 0x10000) == 0 )
  {
    v22 = dword_10072F380;
    do
    {
      v23 = v22 & 0xFFFFFFFE;
      v44 = MemoryNode::sm_ms64atomic;
      _InterlockedOr(v38, 0);
      v22 = dword_10072F380;
    }
    while ( v23 != dword_10072F380 );
    v21 = SOS_PublicGlobals::sm_osStatus;
    if ( *((_QWORD *)&v44 + 1) <= 0x80000000 )
    {
      v21 = SOS_PublicGlobals::sm_osStatus | 0x10000;
      SOS_PublicGlobals::sm_osStatus |= 0x10000u;
    }
  }
  if ( (v21 & 0x20000) == 0 && (unsigned int)SOS_PublicGlobals::sm_cpuCount <= 1 )
    SOS_PublicGlobals::sm_osStatus |= 0x20000u;
  if ( qword_100714440 )
  {
    v24 = 8 * qword_100714440 + 15;
    if ( v24 <= 8 * qword_100714440 )
      v24 = 0xFFFFFFFFFFFFFF0LL;
    v25 = v24 & 0xFFFFFFFFFFFFFFF0uLL;
    v26 = alloca(v25);
    v27 = alloca(v25);
    p_Luid = (void **)&Luid;
  }
  else
  {
    p_Luid = 0;
  }
  AutoMakeMicroSOSThread::AutoMakeMicroSOSThread((AutoMakeMicroSOSThread *)v48, 0, qword_100714440, p_Luid, 0, 0, 0);
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter((LARGE_INTEGER *)&Luid);
    v29 = Luid;
  }
  else
  {
    v29 = (_LUID)MEMORY[0x7FFE0008];
  }
  SOS_OS_TicksWhenSOSBooted = (__int64)v29;
  GetSystemTimeAsFileTime(&SOS_OS_TimeWhenSOSBooted);
  FreeFloatingNode = MemoryNodeManager::CreateFreeFloatingNode((MemoryNodeManager *)&SOS_PublicGlobals::sm_MemoryNodeManager);
  v31 = FreeFloatingNode;
  if ( FreeFloatingNode )
    TList<HostManager,SOSHost,0,TListSLock>::AppendElem(&SOS_PublicGlobals::sm_MemoryNodeManager, FreeFloatingNode);
  SOS_OS_InitialMemoryNode = v31;
  qword_10071F880 = (__int64)v31;
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&PerformanceCount);
    v32 = PerformanceCount;
  }
  else
  {
    v32.QuadPart = MEMORY[0x7FFE0008];
  }
  if ( v32.QuadPart != -1 )
  {
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
      v5 = (unsigned __int64)(1000 * v32.QuadPart) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
    else
      v5 = v32.QuadPart / 0x2710uLL;
  }
  dword_10072F4D8 = 0;
  dword_10072F4DC = 50;
  xmmword_10072F4E0 = (__int128)_mm_load_si128((const __m128i *)&_xmm);
  qword_10072F4F0 = 60000;
  qword_10072F500 = 0;
  qword_10072F4F8 = v5 - 3000;
  ResourceMonitor::sm_memEffects = 1;
  byte_10072F4D4 = 0;
  dword_10072F548 = 0;
  dword_10072F54C = 70;
  xmmword_10072F550 = xmmword_10072F4E0;
  qword_10072F560 = 60000;
  qword_10072F570 = 0;
  qword_10072F568 = v5 - 3000;
  dword_10072F540 = 1;
  byte_10072F544 = 0;
  dword_10072F510 = 95;
  dword_10072F514 = 100;
  qword_10072F518 = 3000;
  xmmword_10072F520 = (__int128)_mm_load_si128((const __m128i *)&_xmm);
  qword_10072F538 = 0;
  qword_10072F530 = v5 - 3000;
  dword_10072F508 = 1;
  byte_10072F50C = 0;
  ResourceMonitor::sm_runningTime = 165;
  ResourceMonitor::sm_sleepingTime = 82;
  ResourceMonitor::sm_processWideEvent = CreateEventW(0, 1, 0, 0);
  if ( !ResourceMonitor::sm_processWideEvent )
  {
    v33 = (void (*)(const wchar_t *, ...))SOS_PublicGlobals::sm_LogSystemMetadataRoutine;
    if ( !SOS_PublicGlobals::sm_LogSystemMetadataRoutine )
      v33 = SOS_OS_LogUnlocalizedRoutine;
    v33(L"Failed to create event for handling Memory pressureresponding to memory pressure might not work \n");
  }
  ResourceMonitor::sm_IdleEvent = CreateEventW(0, 1, 0, 0);
  if ( !ResourceMonitor::sm_IdleEvent )
  {
    v34 = (void (*)(const wchar_t *, ...))SOS_PublicGlobals::sm_LogSystemMetadataRoutine;
    if ( !SOS_PublicGlobals::sm_LogSystemMetadataRoutine )
      v34 = SOS_OS_LogUnlocalizedRoutine;
    v34(L"Failed to create idle server event\n");
  }
  qword_1007BA998 = (__int64)ResourceMonitor::LowPhysicalMemoryQueryRoutine;
  qword_1007BA948 = (__int64)ResourceMonitor::HighPhysicalMemoryQueryRoutine;
  ResourceMonitor::sm_queryHighMemoryResourceNotification = (int (*)(void *, int *))QueryMemoryResourceNotification;
  ResourceMonitor::sm_queryLowMemoryResourceNotification = (int (*)(void *, int *))QueryMemoryResourceNotification;
  ResourceMonitor::sm_configIndicators = (struct Indicator near *)CreateMemoryResourceNotification(HighMemoryResourceNotification);
  qword_1007BA990 = (__int64)CreateMemoryResourceNotification(LowMemoryResourceNotification);
  qword_1007BA9E8 = (__int64)MemoryNode::QueryAndSetVirtualMemoryStatus;
  qword_1007BA9E0 = (__int64)hEvent;
  off_100714718[0] = (_UNKNOWN **)&ResourceMonitor::sm_resetReclaimTargetTimerTaskList;
  ResourceMonitor::sm_resetReclaimTargetTimerTaskList = &ResourceMonitor::sm_resetReclaimTargetTimerTaskList;
  SOS_OS::sm_KillProcessMutex = CreateMutexW(0, 0, 0);
  SOS_PublicGlobals::sm_osStatus |= 8u;
  SOS_OS::sm_LastNodeEnqueuedOn = 0;
  Luid = 0;
  v35 = GetCurrentProcess();
  if ( OpenProcessToken(v35, 8u, (PHANDLE)&Luid) )
  {
    TokenInformationLength = 0;
    if ( GetTokenInformation(*(HANDLE *)&Luid, TokenUser, 0, 0, &TokenInformationLength) )
    {
      CloseHandle(*(HANDLE *)&Luid);
    }
    else if ( GetLastError() == 122
           && (v36 = (PSID *)malloc(TokenInformationLength),
               GetTokenInformation(*(HANDLE *)&Luid, TokenUser, v36, TokenInformationLength, &TokenInformationLength)) )
    {
      SOS_PublicGlobals::sm_ProcessSID = *v36;
      GetLengthSid(*v36);
    }
    else
    {
      GetLastError();
      CloseHandle(*(HANDLE *)&Luid);
    }
  }
  else
  {
    GetLastError();
  }
  GetCurrentThreadStackLimits(&NewState, &v43);
  if ( v43 != *(_QWORD *)&NewState.PrivilegeCount )
    SOS_PublicGlobals::sm_StackSize = v43 - *(_QWORD *)&NewState.PrivilegeCount - 4096;
  SOS_OS::sm_pfnSetProcessAffinityUpdateMode = (int (*)(void *, unsigned int))SetProcessAffinityUpdateMode;
  OsInfo::Init((OsInfo *)&SOS_OS_OsInfo, SOS_OS::sm_NtQuerySystemInformation);
  AutoMakeMicroSOSThread::~AutoMakeMicroSOSThread((AutoMakeMicroSOSThread *)v48);
  return 0;
}

```

## disassembly

```asm
0x1004b1350  push    rbp
0x1004b1352  push    r12
0x1004b1354  push    r13
0x1004b1356  push    r14
0x1004b1358  push    r15
0x1004b135a  mov     eax, 1900h
0x1004b135f  call    _alloca_probe
0x1004b1364  sub     rsp, rax
0x1004b1367  lea     rbp, [rsp+40h]
0x1004b136c  mov     [rbp+18E0h+var_1870], 0FFFFFFFFFFFFFFFEh
0x1004b1374  mov     [rbp+18E0h+arg_0], rbx
0x1004b137b  mov     [rbp+18E0h+arg_8], rsi
0x1004b1382  mov     [rbp+18E0h+arg_10], rdi
0x1004b1389  mov     rax, cs:__security_cookie
0x1004b1390  xor     rax, rbp
0x1004b1393  mov     [rbp+18E0h+var_30], rax
0x1004b139a  mov     rax, cs:__security_cookie
0x1004b13a1  mov     cs:?sm_excGlobalCookie@SOS_PublicGlobals@@2_KA, rax; unsigned __int64 SOS_PublicGlobals::sm_excGlobalCookie
0x1004b13a8  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1004b13af  call    cs:__imp_GetModuleHandleW
0x1004b13b5  mov     rsi, rax
0x1004b13b8  lea     rcx, ModuleName; "ntdll.dll"
0x1004b13bf  call    cs:__imp_GetModuleHandleW
0x1004b13c5  mov     r14, rax
0x1004b13c8  lea     rcx, aPsapiDll; "psapi.dll"
0x1004b13cf  call    cs:__imp_LoadLibraryW
0x1004b13d5  mov     r15, rax
0x1004b13d8  mov     rdx, gs:58h
0x1004b13e1  mov     ecx, cs:_tls_index
0x1004b13e7  mov     eax, 8
0x1004b13ec  mov     rcx, [rdx+rcx*8]
0x1004b13f0  mov     edx, [rax+rcx]
0x1004b13f3  cmp     cs:dword_1007BC3D0, edx
0x1004b13f9  jle     short loc_1004B1445
0x1004b13fb  lea     rcx, dword_1007BC3D0
0x1004b1402  call    _Init_thread_header
0x1004b1407  cmp     cs:dword_1007BC3D0, 0FFFFFFFFh
0x1004b140e  jnz     short loc_1004B1445
0x1004b1410  lea     rax, ??_7OsNumaConfig@@6B@; const OsNumaConfig::`vftable'
0x1004b1417  mov     cs:qword_1007BC3D8, rax
0x1004b141e  lea     rax, ??_7GroupNumaConfig@@6B@; const GroupNumaConfig::`vftable'
0x1004b1425  mov     cs:qword_1007BC3D8, rax
0x1004b142c  lea     rcx, _OsNumaConfig__StaticInit____2____dynamic_atexit_destructor_for__sm_groupNumaConfig__; void (__cdecl *)()
0x1004b1433  call    atexit
0x1004b1438  nop
0x1004b1439  lea     rcx, dword_1007BC3D0
0x1004b1440  call    _Init_thread_footer
0x1004b1445  lea     rcx, qword_1007BC3D8
0x1004b144c  mov     cs:?sm_instance@OsNumaConfig@@0PEAV1@EA, rcx; OsNumaConfig * OsNumaConfig::sm_instance
0x1004b1453  xor     edx, edx
0x1004b1455  mov     rax, cs:qword_1007BC3D8
0x1004b145c  call    qword ptr [rax+68h]
0x1004b145f  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1004b1467  movups  [rbp+18E0h+var_1850], xmm0
0x1004b146e  movups  [rbp+18E0h+var_1840], xmm0
0x1004b1475  movups  [rbp+18E0h+var_1830], xmm0
0x1004b147c  movups  [rbp+18E0h+var_1820], xmm0
0x1004b1483  movups  [rbp+18E0h+var_1810], xmm0
0x1004b148a  movups  [rbp+18E0h+var_1800], xmm0
0x1004b1491  movups  [rbp+18E0h+var_17F0], xmm0
0x1004b1498  movups  [rbp+18E0h+var_17E0], xmm0
0x1004b149f  lea     rcx, [rbp+18E0h+var_1850]; struct SystemAffinity *
0x1004b14a6  call    ?LoadHardwareConfig@SOS_OS@@SAXAEBVSystemAffinity@@@Z; SOS_OS::LoadHardwareConfig(SystemAffinity const &)
0x1004b14ab  xor     r12d, r12d
0x1004b14ae  mov     [rbp+18E0h+TokenHandle], r12
0x1004b14b2  call    cs:__imp_GetCurrentProcess
0x1004b14b8  mov     rcx, rax; ProcessHandle
0x1004b14bb  lea     r8, [rbp+18E0h+TokenHandle]; TokenHandle
0x1004b14bf  mov     edx, 0F01FFh; DesiredAccess
0x1004b14c4  call    cs:__imp_OpenProcessToken
0x1004b14ca  test    eax, eax
0x1004b14cc  jz      short loc_1004B153E
0x1004b14ce  mov     rbx, [rbp+18E0h+TokenHandle]
0x1004b14d2  lea     r8, [rbp+18E0h+Luid]; lpLuid
0x1004b14d6  lea     rdx, aSelockmemorypr; "SeLockMemoryPrivilege"
0x1004b14dd  xor     ecx, ecx; lpSystemName
0x1004b14df  call    cs:__imp_LookupPrivilegeValueW
0x1004b14e5  test    eax, eax
0x1004b14e7  jz      short loc_1004B1534
0x1004b14e9  mov     [rbp+18E0h+NewState.PrivilegeCount], 1
0x1004b14f0  mov     rax, qword ptr [rbp+18E0h+Luid.LowPart]
0x1004b14f4  mov     qword ptr [rbp+18E0h+NewState.Privileges.Luid.LowPart], rax
0x1004b14f8  mov     [rbp+18E0h+NewState.Privileges.Attributes], 2
0x1004b1502  mov     [rsp+1920h+ReturnLength], r12; ReturnLength
0x1004b1507  mov     [rsp+1920h+PreviousState], r12; PreviousState
0x1004b150c  lea     r9d, [r12+10h]; BufferLength
0x1004b1511  lea     r8, [rbp+18E0h+NewState]; NewState
0x1004b1515  xor     edx, edx; DisableAllPrivileges
0x1004b1517  mov     rcx, rbx; TokenHandle
0x1004b151a  call    cs:__imp_AdjustTokenPrivileges
0x1004b1520  call    cs:__imp_GetLastError
0x1004b1526  test    eax, eax
0x1004b1528  jnz     short loc_1004B1534
0x1004b152a  or      cs:?sm_osStatus@SOS_PublicGlobals@@2KA, 800h; ulong SOS_PublicGlobals::sm_osStatus
0x1004b1534  mov     rcx, [rbp+18E0h+TokenHandle]; hObject
0x1004b1538  call    cs:__imp_CloseHandle
0x1004b153e  call    ?DetermineCpuSpeed@SOS_OS@@SAXXZ; SOS_OS::DetermineCpuSpeed(void)
0x1004b1543  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1004b154a  mov     r13, 346DC5D63886594Bh
0x1004b1554  mov     rcx, cs:?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A; _LARGE_INTEGER Base_PublicGlobals::sm_QueryPerformanceFrequency
0x1004b155b  mov     r10d, cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004b1562  mov     rbx, 624DD2F1A9FBE77h
0x1004b156c  imul    r8, cs:?sm_CpuTicksPerMillisecond@SOS_PublicGlobals@@2_KA, 3A98h; unsigned __int64 SOS_PublicGlobals::sm_CpuTicksPerMillisecond
0x1004b1577  mov     rax, rbx
0x1004b157a  test    r10d, r10d
0x1004b157d  jz      short loc_1004B15E4
0x1004b157f  lea     r11, ds:3E7h[rcx*4]
0x1004b1587  mul     r11
0x1004b158a  sub     r11, rdx
0x1004b158d  shr     r11, 1
0x1004b1590  add     r11, rdx
0x1004b1593  shr     r11, 9
0x1004b1597  mov     cs:?sm_QuantumLengthInMS@SOS_PublicGlobals@@2V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@A, r11; SOS_Ticks<InterruptTicks<unsigned __int64>,-3> SOS_PublicGlobals::sm_QuantumLengthInMS
0x1004b159e  mov     rax, rbx
0x1004b15a1  mul     r8
0x1004b15a4  sub     r8, rdx
0x1004b15a7  shr     r8, 1
0x1004b15aa  add     r8, rdx
0x1004b15ad  shr     r8, 9
0x1004b15b1  mov     cs:?SOS_OS_MaxQuantumLength@@3_KA, r8; unsigned __int64 SOS_OS_MaxQuantumLength
0x1004b15b8  imul    r8, cs:?sm_CpuTicksPerMillisecond@SOS_PublicGlobals@@2_KA, 64h ; 'd'; unsigned __int64 SOS_PublicGlobals::sm_CpuTicksPerMillisecond
0x1004b15c0  mov     rax, rbx
0x1004b15c3  mul     r8
0x1004b15c6  sub     r8, rdx
0x1004b15c9  shr     r8, 1
0x1004b15cc  add     r8, rdx
0x1004b15cf  shr     r8, 9
0x1004b15d3  mov     cs:?sm_MinQuantumLength@SOS_OS@@0_KA, r8; unsigned __int64 SOS_OS::sm_MinQuantumLength
0x1004b15da  cmp     r11, rdi
0x1004b15dd  jnz     short loc_1004B162A
0x1004b15df  mov     rdx, rdi
0x1004b15e2  jmp     short loc_1004B164A
0x1004b15e4  mov     r11d, 9C40h
0x1004b15ea  mov     cs:?sm_QuantumLengthInMS@SOS_PublicGlobals@@2V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@A, r11; SOS_Ticks<InterruptTicks<unsigned __int64>,-3> SOS_PublicGlobals::sm_QuantumLengthInMS
0x1004b15f1  mul     r8
0x1004b15f4  sub     r8, rdx
0x1004b15f7  shr     r8, 1
0x1004b15fa  add     r8, rdx
0x1004b15fd  shr     r8, 9
0x1004b1601  mov     cs:?SOS_OS_MaxQuantumLength@@3_KA, r8; unsigned __int64 SOS_OS_MaxQuantumLength
0x1004b1608  imul    r8, cs:?sm_CpuTicksPerMillisecond@SOS_PublicGlobals@@2_KA, 64h ; 'd'; unsigned __int64 SOS_PublicGlobals::sm_CpuTicksPerMillisecond
0x1004b1610  mov     rax, rbx
0x1004b1613  mul     r8
0x1004b1616  sub     r8, rdx
0x1004b1619  shr     r8, 1
0x1004b161c  add     r8, rdx
0x1004b161f  shr     r8, 9
0x1004b1623  mov     cs:?sm_MinQuantumLength@SOS_OS@@0_KA, r8; unsigned __int64 SOS_OS::sm_MinQuantumLength
0x1004b162a  test    r10d, r10d
0x1004b162d  jz      short loc_1004B1640
0x1004b162f  imul    rax, r11, 3E8h
0x1004b1636  xor     edx, edx
0x1004b1638  div     rcx
0x1004b163b  mov     rdx, rax
0x1004b163e  jmp     short loc_1004B164A
0x1004b1640  mov     rax, r13
0x1004b1643  mul     r11
0x1004b1646  shr     rdx, 0Bh
0x1004b164a  imul    r8, rdx, 3E8h
0x1004b1651  test    r10d, r10d
0x1004b1654  jz      short loc_1004B1676
0x1004b1656  imul    r8, rcx
0x1004b165a  add     r8, 3E7h
0x1004b1661  mov     rax, rbx
0x1004b1664  mul     r8
0x1004b1667  sub     r8, rdx
0x1004b166a  shr     r8, 1
0x1004b166d  add     r8, rdx
0x1004b1670  shr     r8, 9
0x1004b1674  jmp     short loc_1004B167D
0x1004b1676  imul    r8, 2710h
0x1004b167d  mov     cs:?sm_QuantumThiefLength@SOS_OS@@0V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@A, r8; SOS_Ticks<InterruptTicks<unsigned __int64>,-3> SOS_OS::sm_QuantumThiefLength
0x1004b1684  mov     r8d, cs:?sm_IdleTimeOut@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_IdleTimeOut
0x1004b168b  test    r10d, r10d
0x1004b168e  jz      short loc_1004B16B0
0x1004b1690  imul    r8, rcx
0x1004b1694  add     r8, 3E7h
0x1004b169b  mov     rax, rbx
0x1004b169e  mul     r8
0x1004b16a1  sub     r8, rdx
0x1004b16a4  shr     r8, 1
0x1004b16a7  add     r8, rdx
0x1004b16aa  shr     r8, 9
0x1004b16ae  jmp     short loc_1004B16B7
0x1004b16b0  imul    r8, 2710h
0x1004b16b7  mov     cs:?sm_IdleTimeOutTicks@SOS_PublicGlobals@@2V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@A, r8; SOS_Ticks<InterruptTicks<unsigned __int64>,-3> SOS_PublicGlobals::sm_IdleTimeOutTicks
0x1004b16be  mov     r8d, cs:?sm_IdleOfflineTimeOut@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_IdleOfflineTimeOut
0x1004b16c5  test    r10d, r10d
0x1004b16c8  jz      short loc_1004B16EA
0x1004b16ca  imul    r8, rcx
0x1004b16ce  add     r8, 3E7h
0x1004b16d5  mov     rax, rbx
0x1004b16d8  mul     r8
0x1004b16db  sub     r8, rdx
0x1004b16de  shr     r8, 1
0x1004b16e1  add     r8, rdx
0x1004b16e4  shr     r8, 9
0x1004b16e8  jmp     short loc_1004B16F1
0x1004b16ea  imul    r8, 2710h
0x1004b16f1  mov     cs:?sm_IdleOfflineTimeOutTicks@SOS_PublicGlobals@@2V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@A, r8; SOS_Ticks<InterruptTicks<unsigned __int64>,-3> SOS_PublicGlobals::sm_IdleOfflineTimeOutTicks
0x1004b16f8  call    ?CalculateAndSetLpPerPp@SOS_OS@@SAXXZ; SOS_OS::CalculateAndSetLpPerPp(void)
0x1004b16fd  mov     rax, cs:__imp_RtlCaptureStackBackTrace
0x1004b1704  mov     cs:?SOS_OS_StackBackTraceRoutine@@3P6AGKKPEAPEAXPEAK@ZEA, rax; ushort (*SOS_OS_StackBackTraceRoutine)(ulong,ulong,void * *,ulong *)
0x1004b170b  lea     rdx, aSetthreadstack; "SetThreadStackGuarantee"
0x1004b1712  mov     rcx, rsi; hModule
0x1004b1715  call    cs:__imp_GetProcAddress
0x1004b171b  mov     cs:?sm_SetThreadStackGuarantee@SOS_OS@@0P6AHPEAK@ZEA, rax; int (*SOS_OS::sm_SetThreadStackGuarantee)(ulong *)
0x1004b1722  lea     rdx, aQueryworkingse; "QueryWorkingSetEx"
0x1004b1729  mov     rcx, r15; hModule
0x1004b172c  call    cs:__imp_GetProcAddress
0x1004b1732  mov     cs:?SOS_OS_QueryWorkingSetExRoutine@@3P6AHPEAX0K@ZEA, rax; int (*SOS_OS_QueryWorkingSetExRoutine)(void *,void *,ulong)
0x1004b1739  lea     rdx, aGetsystemtimes_0; "GetSystemTimes"
0x1004b1740  mov     rcx, rsi; hModule
0x1004b1743  call    cs:__imp_GetProcAddress
0x1004b1749  mov     cs:?sm_GetSystemTimes@SOS_OS@@0P6AHPEAU_FILETIME@@00@ZEA, rax; int (*SOS_OS::sm_GetSystemTimes)(_FILETIME *,_FILETIME *,_FILETIME *)
0x1004b1750  lea     rdx, aNtquerysystemi; "NtQuerySystemInformation"
0x1004b1757  mov     rcx, r14; hModule
0x1004b175a  call    cs:__imp_GetProcAddress
0x1004b1760  mov     cs:?sm_NtQuerySystemInformation@SOS_OS@@0P6AJHPEAXKPEAK@ZEA, rax; long (*SOS_OS::sm_NtQuerySystemInformation)(int,void *,ulong,ulong *)
0x1004b1767  call    ?UpdateGlobalMemoryStatus@MemoryNode@@SAXXZ; MemoryNode::UpdateGlobalMemoryStatus(void)
0x1004b176c  mov     cs:dwSize, 80000h
0x1004b1776  mov     cs:dword_10072F848, r12d
0x1004b177d  xor     r9d, r9d; lpName
0x1004b1780  xor     r8d, r8d; bInitialState
0x1004b1783  lea     edx, [r9+1]; bManualReset
0x1004b1787  xor     ecx, ecx; lpEventAttributes
0x1004b1789  call    cs:__imp_CreateEventW
0x1004b178f  mov     cs:hEvent, rax
0x1004b1796  test    rax, rax
0x1004b1799  jnz     short loc_1004B17B6
0x1004b179b  mov     rax, cs:?sm_LogSystemMetadataRoutine@SOS_PublicGlobals@@2P6AXPEB_WZZEA; void (*SOS_PublicGlobals::sm_LogSystemMetadataRoutine)(wchar_t const *,...)
0x1004b17a2  test    rax, rax
0x1004b17a5  cmovz   rax, cs:?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x1004b17ad  lea     rcx, aFailedToCreate_1; "Failed to create event for handling Vir"...
0x1004b17b4  call    rax
0x1004b17b6  mov     ebx, 100000h
0x1004b17bb  mov     r9d, 4; flProtect
0x1004b17c1  mov     r8d, 1000h; flAllocationType
0x1004b17c7  mov     edx, ebx; dwSize
0x1004b17c9  xor     ecx, ecx; lpAddress
0x1004b17cb  call    cs:__imp_VirtualAlloc
0x1004b17d1  mov     r8, rax
0x1004b17d4  test    rax, rax
0x1004b17d7  jz      loc_1004B188D
0x1004b17dd  mov     cs:qword_10072F8C8, rbx
0x1004b17e4  mov     cs:qword_10072F8B8, 2000h
0x1004b17ef  mov     cs:qword_10072F8C0, rax
0x1004b17f6  mov     cs:?sm_emergencyPageAllocator@MemoryNode@@0VFreePagePool@@A, r12d; FreePagePool MemoryNode::sm_emergencyPageAllocator
0x1004b17fd  mov     cs:dword_10072F8B4, r12d
0x1004b1804  lea     rcx, [rbx+rax]
0x1004b1808  cmp     rax, rcx
0x1004b180b  jnb     short loc_1004B186F
0x1004b180d  lea     r9, off_10072F8D8
0x1004b1814  nop     dword ptr [rax+00h]
0x1004b1818  nop     dword ptr [rax+rax+00000000h]
0x1004b1820  mov     [r8], r12
0x1004b1823  mov     [r8+8], r12
0x1004b1827  mov     rax, cs:off_10072F8D8
0x1004b182e  mov     [r8], rax
0x1004b1831  mov     rax, cs:off_10072F8D8
0x1004b1838  mov     [rax+8], r8
0x1004b183c  mov     cs:off_10072F8D8, r8
0x1004b1843  mov     [r8+8], r9
0x1004b1847  add     r8, 2000h
0x1004b184e  mov     ecx, cs:dword_10072F8B4
0x1004b1854  inc     ecx
0x1004b1856  mov     cs:dword_10072F8B4, ecx
0x1004b185c  mov     rdx, cs:qword_10072F8C8
0x1004b1863  add     rdx, cs:qword_10072F8C0
0x1004b186a  cmp     r8, rdx
0x1004b186d  jb      short loc_1004B1820
0x1004b186f  xor     edx, edx
0x1004b1871  mov     eax, ebx
0x1004b1873  div     cs:dword_1007153CC
0x1004b1879  mov     ecx, eax
0x1004b187b  lock xadd cs:?MemoryNode_OSVasPagesReserved@@3_JA, rax; __int64 MemoryNode_OSVasPagesReserved
0x1004b1884  lock xadd cs:?MemoryNode_OSVasPagesCommitted@@3_JA, rcx; __int64 MemoryNode_OSVasPagesCommitted
0x1004b188d  mov     ecx, cs:dword_10072F380
0x1004b1893  nop     dword ptr [rax+00h]
0x1004b1897  nop     word ptr [rax+rax+00000000h]
0x1004b18a0  and     ecx, 0FFFFFFFEh
0x1004b18a3  mov     eax, ecx
0x1004b18a5  movaps  xmm0, cs:?sm_ms64atomic@MemoryNode@@0V?$SOS_Atomic@U_MEMORYSTATUSEX@@@@A; SOS_Atomic<_MEMORYSTATUSEX> MemoryNode::sm_ms64atomic
0x1004b18ac  movaps  [rbp+18E0h+var_18B0], xmm0
0x1004b18b0  lock or [rsp+1920h+var_1920], r12d
0x1004b18b5  mov     ecx, cs:dword_10072F380
0x1004b18bb  cmp     eax, ecx
0x1004b18bd  jnz     short loc_1004B18A0
0x1004b18bf  mov     rax, qword ptr [rbp+18E0h+var_18B0+8]
0x1004b18c3  shr     rax, 0Dh
0x1004b18c7  mov     cs:?sm_startupTotalPhysicalPages@MemoryNode@@0_JA, rax; __int64 MemoryNode::sm_startupTotalPhysicalPages
0x1004b18ce  test    cs:?sm_osStatus@SOS_PublicGlobals@@2KA, 800h; ulong SOS_PublicGlobals::sm_osStatus
0x1004b18d8  jz      short loc_1004B1913
0x1004b18da  call    cs:__imp_GetLargePageMinimum
0x1004b18e0  test    rax, rax
0x1004b18e3  jz      short loc_1004B1913
0x1004b18e5  call    cs:__imp_GetLargePageMinimum
0x1004b18eb  mov     cs:?MemoryNode_LargePageSize@@3_KA, rax; unsigned __int64 MemoryNode_LargePageSize
0x1004b18f2  mov     r8, cs:?sm_LogSystemMetadataRoutine@SOS_PublicGlobals@@2P6AXPEB_WZZEA; void (*SOS_PublicGlobals::sm_LogSystemMetadataRoutine)(wchar_t const *,...)
0x1004b18f9  test    r8, r8
  ... truncated ...
```
