# NonYieldSystemInformation::UpdateNonYieldRingBuffer(SchedulerMonitor::Track const *,SOS_Node *,uint,ulong)

- ea: `0x100407490`
- end: `0x100407e0b`
- name: `?UpdateNonYieldRingBuffer@NonYieldSystemInformation@@QEAAXPEBVTrack@SchedulerMonitor@@PEAVSOS_Node@@IK@Z`
- size: `2427`
- prototype: `void __fastcall(NonYieldSystemInformation *__hidden this, const struct SchedulerMonitor::Track *, struct SOS_Node *, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x100405b20`
- `0x100406350`
- `0x100406750`

## callees

- `0x100401580`
- `0x100407490`
- `0x100408f00`
- `0x100409000`
- `0x100409240`
- `0x1004534f8`

## import_xrefs

- `pdh!PdhAddCounterW` at `0x100407baf`
- `pdh!PdhAddCounterW` at `0x100407baf`
- `pdh!PdhCloseQuery` at `0x100407b62`
- `pdh!PdhCloseQuery` at `0x100407bcf`
- `pdh!PdhCloseQuery` at `0x100407c3f`
- `pdh!PdhCloseQuery` at `0x100407b62`
- `pdh!PdhCloseQuery` at `0x100407bcf`
- `pdh!PdhCloseQuery` at `0x100407c3f`
- `pdh!PdhOpenQueryW` at `0x100407b79`
- `pdh!PdhOpenQueryW` at `0x100407b79`
- `pdh!PdhGetFormattedCounterValue` at `0x100407c1f`
- `pdh!PdhGetFormattedCounterValue` at `0x100407c1f`
- `pdh!PdhCollectQueryData` at `0x100407bf4`
- `pdh!PdhCollectQueryData` at `0x100407bf4`
- `KERNEL32!Process32FirstW` at `0x1004077e4`
- `KERNEL32!Process32FirstW` at `0x1004077e4`
- `KERNEL32!CloseHandle` at `0x1004078dd`
- `KERNEL32!CloseHandle` at `0x100407a1a`
- `KERNEL32!CloseHandle` at `0x1004078dd`
- `KERNEL32!CloseHandle` at `0x100407a1a`
- `KERNEL32!GetThreadTimes` at `0x100407a05`
- `KERNEL32!GetThreadTimes` at `0x100407a05`
- `KERNEL32!K32GetProcessMemoryInfo` at `0x1004078a8`
- `KERNEL32!K32GetProcessMemoryInfo` at `0x1004078a8`
- `KERNEL32!Process32NextW` at `0x10040797c`
- `KERNEL32!Process32NextW` at `0x10040797c`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x10040778c`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x10040778c`
- `KERNEL32!OpenProcess` at `0x10040788a`
- `KERNEL32!OpenProcess` at `0x10040788a`
- `KERNEL32!Thread32First` at `0x1004079bb`
- `KERNEL32!Thread32First` at `0x1004079bb`
- `KERNEL32!Thread32Next` at `0x100407b36`
- `KERNEL32!Thread32Next` at `0x100407b36`
- `KERNEL32!OpenThread` at `0x1004079df`
- `KERNEL32!OpenThread` at `0x1004079df`
- `KERNEL32!QueryPerformanceCounter` at `0x100407633`
- `KERNEL32!QueryPerformanceCounter` at `0x100407685`
- `KERNEL32!QueryPerformanceCounter` at `0x100407d0c`
- `KERNEL32!QueryPerformanceCounter` at `0x100407d5f`
- `KERNEL32!QueryPerformanceCounter` at `0x100407633`
- `KERNEL32!QueryPerformanceCounter` at `0x100407685`
- `KERNEL32!QueryPerformanceCounter` at `0x100407d0c`
- `KERNEL32!QueryPerformanceCounter` at `0x100407d5f`
- `sqldk!?SOS_OS_StackBackTraceRoutine@@3P6AGKKPEAPEAXPEAK@ZEA` at `0x100407909`
- `sqldk!?SOS_OS_StackBackTraceRoutine@@3P6AGKKPEAPEAXPEAK@ZEA` at `0x100407ab2`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100407648`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100407d21`
- `sqldk!SystemThread_TlsOffset` at `0x1004075fe`
- `sqldk!SystemThread_TlsOffset` at `0x100407cd7`
- `sqldk!SystemThread_TlsIndex` at `0x1004075f5`
- `sqldk!SystemThread_TlsIndex` at `0x100407cce`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x100407529`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x100407529`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100407557`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100407557`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x10040796c`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100407b23`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x10040796c`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100407b23`
- `sqldk!?UpdateSystemHealth@SchedulerMonitor@@AEAAXH@Z` at `0x100407776`
- `sqldk!?UpdateSystemHealth@SchedulerMonitor@@AEAAXH@Z` at `0x100407776`
- `sqldk!?ResetNonYieldStats@SchedulerMonitor@@QEAAXPEAVTrack@1@@Z` at `0x100407c6b`
- `sqldk!?ResetNonYieldStats@SchedulerMonitor@@QEAAXPEAVTrack@1@@Z` at `0x100407c6b`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100407623`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100407675`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100407cfc`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100407d4e`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1004076fd`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100407da1`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004075d5`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100407cae`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x100407522`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100407709`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100407dad`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100407709`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100407dad`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall NonYieldSystemInformation::UpdateNonYieldRingBuffer(
        NonYieldSystemInformation *this,
        const struct SchedulerMonitor::Track *a2,
        struct SOS_Node *a3,
        unsigned int a4,
        unsigned int a5)
{
  const struct SchedulerMonitor::Track *v7; // rsi
  unsigned int v9; // ebx
  unsigned int v10; // r15d
  int v11; // r14d
  int v12; // edx
  __int64 v13; // r12
  __int64 v14; // rbx
  LARGE_INTEGER v15; // rbx
  signed __int64 UniqueThread_low; // r15
  __int64 v17; // rsi
  __int64 v18; // r8
  char *v19; // rcx
  LARGE_INTEGER v20; // rax
  LONGLONG v21; // rcx
  __int64 v22; // rax
  int v23; // r8d
  __int64 v24; // rax
  _QWORD *v25; // rsi
  HANDLE v26; // r13
  HANDLE Toolhelp32Snapshot; // rax
  DWORD th32ProcessID; // r8d
  __int64 v29; // rdx
  char *v30; // rax
  __int16 v31; // cx
  char *v32; // rcx
  HANDLE v33; // rax
  void *v34; // rbx
  unsigned int v35; // edx
  struct _FILETIME v36; // r14
  struct _FILETIME v37; // rsi
  HANDLE v38; // rbx
  struct _FILETIME *v39; // rcx
  int v40; // ebx
  unsigned int v41; // edx
  void *v42; // rcx
  PDH_STATUS v43; // eax
  int v44; // ebx
  PDH_STATUS v45; // eax
  PDH_STATUS Data; // eax
  char *v47; // rbx
  __int64 v48; // rsi
  volatile signed __int64 *v49; // rsi
  LARGE_INTEGER v50; // rbx
  signed __int64 v51; // r14
  __int64 v52; // rdi
  __int64 v53; // r8
  char *v54; // rax
  char *v55; // rcx
  int v56; // r8d
  int v57; // [rsp+30h] [rbp-D0h]
  _QWORD *v60; // [rsp+40h] [rbp-C0h]
  __int64 v61; // [rsp+50h] [rbp-B0h]
  HANDLE hSnapshot; // [rsp+58h] [rbp-A8h] BYREF
  LARGE_INTEGER v63; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v64; // [rsp+68h] [rbp-98h]
  int v65; // [rsp+70h] [rbp-90h]
  LARGE_INTEGER PerformanceCount; // [rsp+78h] [rbp-88h] BYREF
  LARGE_INTEGER v67; // [rsp+80h] [rbp-80h] BYREF
  struct _FILETIME KernelTime; // [rsp+88h] [rbp-78h] BYREF
  struct _FILETIME UserTime; // [rsp+90h] [rbp-70h] BYREF
  __int128 v70; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v71; // [rsp+B0h] [rbp-50h]
  DWORD th32OwnerProcessID; // [rsp+B8h] [rbp-48h]
  DWORD th32ThreadID; // [rsp+BCh] [rbp-44h]
  struct _FILETIME v74; // [rsp+C0h] [rbp-40h]
  struct _FILETIME v75; // [rsp+C8h] [rbp-38h]
  struct _FILETIME v76; // [rsp+D0h] [rbp-30h]
  struct _FILETIME v77; // [rsp+D8h] [rbp-28h]
  __int64 v78; // [rsp+E0h] [rbp-20h]
  struct _FILETIME ExitTime; // [rsp+E8h] [rbp-18h] BYREF
  _FILETIME CreationTime; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v81[16]; // [rsp+100h] [rbp+0h] BYREF
  int v82; // [rsp+110h] [rbp+10h] BYREF
  void *v83; // [rsp+118h] [rbp+18h] BYREF
  int v84; // [rsp+1D8h] [rbp+D8h]
  __int64 v85; // [rsp+1E0h] [rbp+E0h]
  _BYTE v86[16]; // [rsp+1F0h] [rbp+F0h] BYREF
  int v87; // [rsp+200h] [rbp+100h] BYREF
  void *v88; // [rsp+208h] [rbp+108h] BYREF
  int v89; // [rsp+2C8h] [rbp+1C8h]
  __int64 v90; // [rsp+2D0h] [rbp+1D0h]
  THREADENTRY32 te; // [rsp+2E0h] [rbp+1E0h] BYREF
  PROCESSENTRY32W pe; // [rsp+300h] [rbp+200h] BYREF
  PROCESS_MEMORY_COUNTERS ppsmemCounters; // [rsp+540h] [rbp+440h] BYREF
  __int64 v94; // [rsp+588h] [rbp+488h]
  __int128 v95; // [rsp+590h] [rbp+490h] BYREF
  __int64 v96; // [rsp+5A0h] [rbp+4A0h]
  DWORD v97; // [rsp+5A8h] [rbp+4A8h]
  char v98; // [rsp+5ACh] [rbp+4ACh] BYREF
  DWORD PageFaultCount; // [rsp+7B4h] [rbp+6B4h]
  SIZE_T WorkingSetSize; // [rsp+7B8h] [rbp+6B8h]
  __int64 v101; // [rsp+7C0h] [rbp+6C0h]

  v78 = -2;
  v7 = a2;
  v9 = a5 >> 1;
  v10 = 0;
  v11 = 0;
  v57 = 0;
  v63.QuadPart = (LONGLONG)a3 + 1936;
  hSnapshot = (HANDLE)*((_QWORD *)a3 + 242);
  pe.dwSize = 568;
  te.dwSize = 28;
  if ( !OsInfo::IsXPlatInstance(SOS_OS_OsInfo) )
  {
    if ( !v9 )
      utassert_fail(1u, "SNAPSHOT_PERIOD != 0", "sqlsos.cpp", 1526, 0);
    v12 = a4 % v9;
    if ( a4 / v9 )
    {
      v13 = *(_QWORD *)this;
      v14 = *((_QWORD *)this + 1);
      v61 = v14;
      if ( *(_QWORD *)this || v14 )
      {
        if ( !v12 && !*((_QWORD *)a3 + 243) )
        {
          v64 = (_QWORD *)((char *)this + 159960);
          v65 = 0;
          v15.QuadPart = 0;
          UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
          if ( *((_DWORD *)this + 39990)
            || _InterlockedCompareExchange64((volatile signed __int64 *)this + 19995, UniqueThread_low, 0) )
          {
            v17 = 0;
            if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
            {
              v18 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset;
              if ( v18 && *(_QWORD *)(v18 + 272) == v18 )
                v17 = *(_QWORD *)(v18 + 256);
              if ( v17 )
              {
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&PerformanceCount);
                  v15 = PerformanceCount;
                }
                else
                {
                  v15.QuadPart = MEMORY[0x7FFE0008];
                }
              }
            }
            v19 = (char *)this + 159960;
            if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
              Spinlock<48,1,268435714>::SpinToAcquireWithExponentialBackoff(v19, UniqueThread_low);
            else
              Spinlock<48,1,268435714>::SpinToAcquireOptimistic(v19, v17, UniqueThread_low);
            if ( v17 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v67);
                v20 = v67;
              }
              else
              {
                v20.QuadPart = MEMORY[0x7FFE0008];
              }
              v21 = v20.QuadPart - v15.QuadPart;
              if ( v20.QuadPart < (unsigned __int64)v15.QuadPart )
                v21 = 0;
              *(_QWORD *)(v17 + 3192) += v21;
              v7 = a2;
            }
            else
            {
              v7 = a2;
            }
          }
          v65 = 1;
          v22 = *((_QWORD *)this + 3);
          if ( !v22 || !*(_QWORD *)(v22 + 8) )
          {
            *((_QWORD *)this + 3) = (char *)a3 + 1936;
            *((_QWORD *)a3 + 243) = *((_QWORD *)v7 + 50);
          }
          if ( v64 )
          {
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v23 = rand();
              if ( v23 == 5 * (v23 / 5) )
                Spinlock<48,1,268435714>::UpdateStatSnapshot();
            }
            *v64 = 0;
            v64 = 0;
            v65 = 0;
          }
          v10 = 0;
          v11 = 0;
          v14 = v61;
        }
        v24 = *((_QWORD *)a3 + 243);
        if ( v24 )
        {
          if ( v24 == *((_QWORD *)v7 + 50) )
          {
            v25 = (_QWORD *)((char *)a3 + 1936);
            SchedulerMonitor::UpdateSystemHealth((struct SOS_Node *)((char *)a3 + 1936), 1);
            v26 = hSnapshot;
            if ( hSnapshot == (HANDLE)-1LL )
            {
              Toolhelp32Snapshot = CreateToolhelp32Snapshot(6u, 0);
              v26 = Toolhelp32Snapshot;
              if ( Toolhelp32Snapshot == (HANDLE)-1LL )
                return;
              *v25 = Toolhelp32Snapshot;
              if ( v13 )
                *(_DWORD *)(v13 + 48) = 0;
              if ( v14 )
                *(_DWORD *)(v14 + 48) = 0;
              v11 = 1;
              v57 = 1;
            }
            if ( v13 && Process32FirstW(v26, &pe) )
            {
              v10 = 0;
              do
              {
                v95 = 0;
                v96 = 0;
                th32ProcessID = pe.th32ProcessID;
                v97 = pe.th32ProcessID;
                PageFaultCount = 0;
                WorkingSetSize = 0;
                v101 = 0;
                v29 = 260;
                v30 = &v98;
                do
                {
                  if ( v29 == -2147483386 )
                    break;
                  v31 = *((_WORD *)v30 - 320);
                  if ( !v31 )
                    break;
                  *(_WORD *)v30 = v31;
                  v30 += 2;
                  --v29;
                }
                while ( v29 );
                v32 = v30 - 2;
                if ( v29 )
                  v32 = v30;
                *(_WORD *)v32 = 0;
                v33 = OpenProcess(0x400u, 0, th32ProcessID);
                v34 = v33;
                if ( v33 )
                {
                  if ( K32GetProcessMemoryInfo(v33, &ppsmemCounters, 0x50u) )
                  {
                    PageFaultCount = ppsmemCounters.PageFaultCount;
                    WorkingSetSize = ppsmemCounters.WorkingSetSize;
                    v101 = v94;
                  }
                  CloseHandle(v34);
                }
                v84 = 0;
                v85 = 0;
                if ( *(_QWORD *)(v13 + 64) )
                {
                  memset_0(v81, 0, 0xE8u);
                  v84 = SOS_OS_StackBackTraceRoutine(1u, 0x18u, &v83, (unsigned int *)&v82);
                  v35 = ((9 * ((v82 + ~(v82 << 15)) ^ ((unsigned int)(v82 + ~(v82 << 15)) >> 10)))
                       ^ ((9 * ((v82 + ~(v82 << 15)) ^ ((unsigned int)(v82 + ~(v82 << 15)) >> 10))) >> 6))
                      + ~(((9 * ((v82 + ~(v82 << 15)) ^ ((unsigned int)(v82 + ~(v82 << 15)) >> 10)))
                         ^ ((9 * ((v82 + ~(v82 << 15)) ^ ((unsigned int)(v82 + ~(v82 << 15)) >> 10))) >> 6)) << 11);
                  v82 = v35 ^ HIWORD(v35);
                }
                SOS_RingBuffer::StoreRecordInternalWithoutEvent(v13, &v95, v81);
              }
              while ( Process32NextW(v26, &pe) );
            }
            if ( v61 && (v11 || !(a4 % a5)) )
            {
              if ( Thread32First(v26, &te) )
              {
                v36 = 0;
                do
                {
                  v37 = 0;
                  v38 = OpenThread(0x40u, 0, te.th32ThreadID);
                  if ( v38 && GetThreadTimes(v38, &CreationTime, &ExitTime, &KernelTime, &UserTime) )
                  {
                    v37 = KernelTime;
                    v36 = UserTime;
                    CloseHandle(v38);
                  }
                  v39 = (struct _FILETIME *)((char *)this + 8 * v10);
                  v40 = v57;
                  if ( v57 )
                  {
                    v39[3609] = v37;
                    v39[11801] = v36;
                    v36 = 0;
                  }
                  else
                  {
                    v70 = 0;
                    v71 = 0;
                    th32OwnerProcessID = te.th32OwnerProcessID;
                    th32ThreadID = te.th32ThreadID;
                    v74 = v39[11801];
                    v75 = v36;
                    v76 = v39[3609];
                    v77 = v37;
                    v36 = 0;
                    v89 = 0;
                    v90 = 0;
                    if ( *(_QWORD *)(v61 + 64) )
                    {
                      memset_0(v86, 0, 0xE8u);
                      v89 = SOS_OS_StackBackTraceRoutine(1u, 0x18u, &v88, (unsigned int *)&v87);
                      v41 = ((9 * ((v87 + ~(v87 << 15)) ^ ((unsigned int)(v87 + ~(v87 << 15)) >> 10)))
                           ^ ((9 * ((v87 + ~(v87 << 15)) ^ ((unsigned int)(v87 + ~(v87 << 15)) >> 10))) >> 6))
                          + ~(((9 * ((v87 + ~(v87 << 15)) ^ ((unsigned int)(v87 + ~(v87 << 15)) >> 10)))
                             ^ ((9 * ((v87 + ~(v87 << 15)) ^ ((unsigned int)(v87 + ~(v87 << 15)) >> 10))) >> 6)) << 11);
                      v87 = v41 ^ HIWORD(v41);
                    }
                    SOS_RingBuffer::StoreRecordInternalWithoutEvent(v61, &v70, v86);
                  }
                  ++v10;
                }
                while ( Thread32Next(v26, &te) && v10 < 0x2000 );
                if ( v57 )
                {
                  v42 = (void *)*((_QWORD *)this + 19993);
                  if ( v42 != (void *)-1LL )
                    *((_DWORD *)this + 39988) = PdhCloseQuery(v42);
                  v43 = PdhOpenQueryW(0, 0, (PDH_HQUERY *)this + 19993);
                  *((_DWORD *)this + 39988) = v43;
                  if ( !v43 )
                  {
                    v44 = 0;
                    while ( 1 )
                    {
                      v45 = PdhAddCounterW(
                              *((PDH_HQUERY *)this + 19993),
                              (LPCWSTR)this + 2060 * v44 + 28,
                              0,
                              (PDH_HCOUNTER *)this + 515 * v44 + 4);
                      *((_DWORD *)this + 39988) = v45;
                      if ( v45 )
                        break;
                      if ( (unsigned int)++v44 >= 7 )
                        goto LABEL_88;
                    }
                    PdhCloseQuery(*((PDH_HQUERY *)this + 19993));
                    *((_QWORD *)this + 19993) = -1;
LABEL_88:
                    v40 = v57;
                  }
                }
                if ( !*((_DWORD *)this + 39988) )
                {
                  Data = PdhCollectQueryData(*((PDH_HQUERY *)this + 19993));
                  *((_DWORD *)this + 39988) = Data;
                  if ( !v40 )
                  {
                    if ( !Data )
                    {
                      v47 = (char *)this + 32;
                      v48 = 7;
                      do
                      {
                        *((_DWORD *)this + 39988) = PdhGetFormattedCounterValue(
                                                      *(PDH_HCOUNTER *)v47,
                                                      0x200u,
                                                      0,
                                                      (PPDH_FMT_COUNTERVALUE)(v47 + 8));
                        v47 += 4120;
                        --v48;
                      }
                      while ( v48 );
                    }
                    PdhCloseQuery(*((PDH_HQUERY *)this + 19993));
                    *((_QWORD *)this + 19993) = -1;
                  }
                }
              }
              if ( !(a4 % a5) )
              {
                SchedulerMonitor::ResetNonYieldStats((SchedulerMonitor *)v63.QuadPart, 0);
                v49 = (volatile signed __int64 *)((char *)this + 159960);
                v60 = (_QWORD *)((char *)this + 159960);
                v50.QuadPart = 0;
                v51 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
                if ( *((_DWORD *)this + 39990) || _InterlockedCompareExchange64(v49, v51, 0) )
                {
                  v52 = 0;
                  if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
                  {
                    v53 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset;
                    if ( v53 && *(_QWORD *)(v53 + 272) == v53 )
                      v52 = *(_QWORD *)(v53 + 256);
                    if ( v52 )
                    {
                      if ( Base_PublicGlobals::sm_invariantTscAvailable )
                      {
                        QueryPerformanceCounter(&v63);
                        v50 = v63;
                      }
                      else
                      {
                        v50.QuadPart = MEMORY[0x7FFE0008];
                      }
                    }
                  }
                  if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
                    Spinlock<48,1,268435714>::SpinToAcquireWithExponentialBackoff(v49, v51);
                  else
                    Spinlock<48,1,268435714>::SpinToAcquireOptimistic(v49, v52, v51);
                  if ( v52 )
                  {
                    if ( Base_PublicGlobals::sm_invariantTscAvailable )
                    {
                      QueryPerformanceCounter((LARGE_INTEGER *)&hSnapshot);
                      v54 = (char *)hSnapshot;
                    }
                    else
                    {
                      v54 = (char *)MEMORY[0x7FFE0008];
                    }
                    v55 = &v54[-v50.QuadPart];
                    if ( (unsigned __int64)v54 < v50.QuadPart )
                      v55 = 0;
                    *(_QWORD *)(v52 + 3192) += v55;
                  }
                }
                qword_1004A9A28 = 0;
                if ( v60 )
                {
                  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                  {
                    v56 = rand();
                    if ( v56 == 5 * (v56 / 5) )
                      Spinlock<48,1,268435714>::UpdateStatSnapshot();
                  }
                  *v60 = 0;
                }
              }
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x100407490  push    rbp
0x100407492  push    rsi
0x100407493  push    rdi
0x100407494  push    r12
0x100407496  push    r13
0x100407498  push    r14
0x10040749a  push    r15
0x10040749c  lea     rbp, [rsp-6D0h]
0x1004074a4  sub     rsp, 7D0h
0x1004074ab  mov     [rbp+700h+var_720], 0FFFFFFFFFFFFFFFEh
0x1004074b3  mov     [rsp+800h+arg_8], rbx
0x1004074bb  mov     rax, cs:__security_cookie
0x1004074c2  xor     rax, rsp
0x1004074c5  mov     [rbp+700h+var_38], rax
0x1004074cc  mov     r12d, r9d
0x1004074cf  mov     [rsp+800h+var_7C4], r9d
0x1004074d4  mov     r13, r8
0x1004074d7  mov     rsi, rdx
0x1004074da  mov     [rsp+800h+var_7C0], rdx
0x1004074df  mov     rdi, rcx
0x1004074e2  mov     ebx, [rbp+700h+arg_20]
0x1004074e8  shr     ebx, 1
0x1004074ea  xor     eax, eax
0x1004074ec  mov     r15d, eax
0x1004074ef  mov     [rsp+800h+var_7C8], eax
0x1004074f3  mov     r14d, eax
0x1004074f6  mov     [rsp+800h+var_7D0], eax
0x1004074fa  lea     rax, [r8+790h]
0x100407501  mov     qword ptr [rsp+800h+var_7A0], rax
0x100407506  mov     rax, [rax]
0x100407509  mov     [rsp+800h+hSnapshot], rax
0x10040750e  mov     [rbp+700h+pe.dwSize], 238h
0x100407518  mov     [rbp+700h+te.dwSize], 1Ch
0x100407522  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x100407529  call    cs:__imp_?IsXPlatInstance@OsInfo@@QEBA?B_NXZ; OsInfo::IsXPlatInstance(void)
0x10040752f  test    al, al
0x100407531  jnz     loc_100407DE1
0x100407537  test    ebx, ebx
0x100407539  jnz     short loc_10040755D
0x10040753b  mov     [rsp+800h+lpUserTime], r14
0x100407540  mov     r9d, 5F6h
0x100407546  lea     r8, aSqlsosCpp; "sqlsos.cpp"
0x10040754d  lea     rdx, aSnapshotPeriod; "SNAPSHOT_PERIOD != 0"
0x100407554  lea     ecx, [rbx+1]
0x100407557  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10040755d  xor     edx, edx
0x10040755f  mov     eax, r12d
0x100407562  div     ebx
0x100407564  test    eax, eax
0x100407566  jz      loc_100407DE1
0x10040756c  mov     r12, [rdi]
0x10040756f  mov     rbx, [rdi+8]
0x100407573  mov     [rsp+800h+var_7B0], rbx
0x100407578  test    r12, r12
0x10040757b  jnz     short loc_100407586
0x10040757d  test    rbx, rbx
0x100407580  jz      loc_100407DE1
0x100407586  test    edx, edx
0x100407588  jnz     loc_10040774A
0x10040758e  cmp     [r13+798h], r14
0x100407595  jnz     loc_10040774A
0x10040759b  lea     r14, [rdi+270D8h]
0x1004075a2  mov     [rsp+800h+var_798], r14
0x1004075a7  xor     edx, edx
0x1004075a9  mov     [rsp+800h+var_790], edx
0x1004075ad  mov     ebx, edx
0x1004075af  mov     eax, gs:48h
0x1004075b7  mov     r15d, eax
0x1004075ba  mov     eax, [r14]
0x1004075bd  test    eax, eax
0x1004075bf  jnz     short loc_1004075D5
0x1004075c1  xor     eax, eax
0x1004075c3  lock cmpxchg [r14], r15
0x1004075c8  mov     eax, edx
0x1004075ca  setz    al
0x1004075cd  test    eax, eax
0x1004075cf  jnz     loc_1004076BF
0x1004075d5  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004075dc  mov     ecx, [rax]
0x1004075de  and     ecx, 84h
0x1004075e4  mov     rsi, rdx
0x1004075e7  cmp     cl, 84h
0x1004075ea  jnz     short loc_100407648
0x1004075ec  mov     rdx, gs:58h
0x1004075f5  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004075fc  mov     ecx, [rax]
0x1004075fe  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100407605  mov     r8d, [rax]
0x100407608  add     r8, [rdx+rcx*8]
0x10040760c  jz      short loc_10040761E
0x10040760e  cmp     [r8+110h], r8
0x100407615  jnz     short loc_10040761E
0x100407617  mov     rsi, [r8+100h]
0x10040761e  test    rsi, rsi
0x100407621  jz      short loc_100407648
0x100407623  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040762a  cmp     [rax], ebx
0x10040762c  jz      short loc_100407640
0x10040762e  lea     rcx, [rsp+800h+PerformanceCount]; lpPerformanceCount
0x100407633  call    cs:__imp_QueryPerformanceCounter
0x100407639  mov     rbx, qword ptr [rsp+800h+PerformanceCount]
0x10040763e  jmp     short loc_100407648
0x100407640  mov     rbx, ds:7FFE0008h
0x100407648  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10040764f  mov     rcx, r14
0x100407652  cmp     byte ptr [rax+0C7h], 0
0x100407659  jge     short loc_100407668
0x10040765b  mov     r8, r15
0x10040765e  mov     rdx, rsi
0x100407661  call    ?SpinToAcquireOptimistic@?$Spinlock@$0DA@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<48,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100407666  jmp     short loc_100407670
0x100407668  mov     rdx, r15
0x10040766b  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0DA@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<48,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100407670  test    rsi, rsi
0x100407673  jz      short loc_1004076BA
0x100407675  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040767c  cmp     dword ptr [rax], 0
0x10040767f  jz      short loc_100407691
0x100407681  lea     rcx, [rbp+700h+var_780]; lpPerformanceCount
0x100407685  call    cs:__imp_QueryPerformanceCounter
0x10040768b  mov     rax, qword ptr [rbp+700h+var_780]
0x10040768f  jmp     short loc_100407699
0x100407691  mov     rax, ds:7FFE0008h
0x100407699  mov     rcx, rax
0x10040769c  sub     rcx, rbx
0x10040769f  cmp     rax, rbx
0x1004076a2  mov     r14d, 0
0x1004076a8  cmovb   rcx, r14
0x1004076ac  add     [rsi+0C78h], rcx
0x1004076b3  mov     rsi, [rsp+800h+var_7C0]
0x1004076b8  jmp     short loc_1004076C2
0x1004076ba  mov     rsi, [rsp+800h+var_7C0]
0x1004076bf  xor     r14d, r14d
0x1004076c2  mov     [rsp+800h+var_790], 1
0x1004076ca  mov     rax, [rdi+18h]
0x1004076ce  test    rax, rax
0x1004076d1  jz      short loc_1004076DA
0x1004076d3  cmp     qword ptr [rax+8], 0
0x1004076d8  jnz     short loc_1004076F3
0x1004076da  lea     rcx, [r13+790h]
0x1004076e1  mov     [rdi+18h], rcx
0x1004076e5  mov     rax, [rsi+190h]
0x1004076ec  mov     [r13+798h], rax
0x1004076f3  mov     rbx, [rsp+800h+var_798]
0x1004076f8  test    rbx, rbx
0x1004076fb  jz      short loc_10040773D
0x1004076fd  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x100407704  cmp     byte ptr [rax], 0
0x100407707  jz      short loc_100407730
0x100407709  call    cs:__imp_rand
0x10040770f  mov     r8d, eax
0x100407712  mov     eax, 66666667h
0x100407717  imul    r8d
0x10040771a  sar     edx, 1
0x10040771c  mov     ecx, edx
0x10040771e  shr     ecx, 1Fh
0x100407721  add     edx, ecx
0x100407723  lea     ecx, [rdx+rdx*4]
0x100407726  cmp     r8d, ecx
0x100407729  jnz     short loc_100407730
0x10040772b  call    ?UpdateStatSnapshot@?$Spinlock@$0DA@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<48,1,268435714>::UpdateStatSnapshot(void)
0x100407730  mov     [rbx], r14
0x100407733  mov     [rsp+800h+var_798], r14
0x100407738  mov     [rsp+800h+var_790], r14d
0x10040773d  mov     r15d, [rsp+800h+var_7C8]
0x100407742  mov     r14d, r15d
0x100407745  mov     rbx, [rsp+800h+var_7B0]
0x10040774a  mov     rax, [r13+798h]
0x100407751  test    rax, rax
0x100407754  jz      loc_100407DE1
0x10040775a  cmp     rax, [rsi+190h]
0x100407761  jnz     loc_100407DE1
0x100407767  mov     edx, 1
0x10040776c  lea     rsi, [r13+790h]
0x100407773  mov     rcx, rsi
0x100407776  call    cs:__imp_?UpdateSystemHealth@SchedulerMonitor@@AEAAXH@Z; SchedulerMonitor::UpdateSystemHealth(int)
0x10040777c  mov     r13, [rsp+800h+hSnapshot]
0x100407781  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x100407785  jnz     short loc_1004077D1
0x100407787  xor     edx, edx; th32ProcessID
0x100407789  lea     ecx, [rdx+6]; dwFlags
0x10040778c  call    cs:__imp_CreateToolhelp32Snapshot
0x100407792  mov     r13, rax
0x100407795  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x100407799  jz      loc_100407DE1
0x10040779f  mov     [rsi], rax
0x1004077a2  xor     eax, eax
0x1004077a4  test    r12, r12
0x1004077a7  jz      short loc_1004077B6
0x1004077a9  mov     [rsp+800h+var_7D0], eax
0x1004077ad  mov     ecx, [rsp+800h+var_7D0]
0x1004077b1  mov     [r12+30h], ecx
0x1004077b6  test    rbx, rbx
0x1004077b9  jz      short loc_1004077C6
0x1004077bb  mov     [rsp+800h+var_7D0], eax
0x1004077bf  mov     eax, [rsp+800h+var_7D0]
0x1004077c3  mov     [rbx+30h], eax
0x1004077c6  mov     r14d, 1
0x1004077cc  mov     [rsp+800h+var_7D0], r14d
0x1004077d1  test    r12, r12
0x1004077d4  jz      loc_10040798A
0x1004077da  lea     rdx, [rbp+700h+pe]; lppe
0x1004077e1  mov     rcx, r13; hSnapshot
0x1004077e4  call    cs:__imp_Process32FirstW
0x1004077ea  test    eax, eax
0x1004077ec  jz      loc_10040798A
0x1004077f2  lea     rsi, [rbp+700h+pe.szExeFile]
0x1004077f9  lea     rax, [rbp+700h+var_254]
0x100407800  sub     rsi, rax
0x100407803  xor     r15d, r15d
0x100407806  nop     word ptr [rax+rax+00000000h]
0x100407810  xorps   xmm0, xmm0
0x100407813  xor     eax, eax
0x100407815  movups  [rbp+700h+var_270], xmm0
0x10040781c  mov     [rbp+700h+var_260], rax
0x100407823  mov     r8d, [rbp+700h+pe.th32ProcessID]; dwProcessId
0x10040782a  mov     [rbp+700h+var_258], r8d
0x100407831  mov     [rbp+700h+var_4C], r15d
0x100407838  mov     [rbp+700h+var_48], r15
0x10040783f  mov     [rbp+700h+var_40], r15
0x100407846  mov     edx, 104h
0x10040784b  lea     rax, [rbp+700h+var_254]
0x100407852  lea     rcx, [rdx+7FFFFEFAh]
0x100407859  test    rcx, rcx
0x10040785c  jz      short loc_100407874
0x10040785e  movzx   ecx, word ptr [rax+rsi]
0x100407862  test    cx, cx
0x100407865  jz      short loc_100407874
0x100407867  mov     [rax], cx
0x10040786a  add     rax, 2
0x10040786e  sub     rdx, 1
0x100407872  jnz     short loc_100407852
0x100407874  lea     rcx, [rax-2]
0x100407878  test    rdx, rdx
0x10040787b  cmovnz  rcx, rax
0x10040787f  mov     [rcx], r15w
0x100407883  xor     edx, edx; bInheritHandle
0x100407885  mov     ecx, 400h; dwDesiredAccess
0x10040788a  call    cs:__imp_OpenProcess
0x100407890  mov     rbx, rax
0x100407893  test    rax, rax
0x100407896  jz      short loc_1004078E3
0x100407898  mov     r8d, 50h ; 'P'; cb
0x10040789e  lea     rdx, [rbp+700h+ppsmemCounters]; ppsmemCounters
0x1004078a5  mov     rcx, rax; Process
0x1004078a8  call    cs:__imp_K32GetProcessMemoryInfo
0x1004078ae  test    eax, eax
0x1004078b0  jz      short loc_1004078DA
0x1004078b2  mov     ecx, [rbp+700h+ppsmemCounters.PageFaultCount]
0x1004078b8  mov     [rbp+700h+var_4C], ecx
0x1004078be  mov     rcx, [rbp+700h+ppsmemCounters.WorkingSetSize]
0x1004078c5  mov     [rbp+700h+var_48], rcx
0x1004078cc  mov     rax, [rbp+700h+var_278]
0x1004078d3  mov     [rbp+700h+var_40], rax
0x1004078da  mov     rcx, rbx; hObject
0x1004078dd  call    cs:__imp_CloseHandle
0x1004078e3  mov     [rbp+700h+var_628], r15d
0x1004078ea  mov     [rbp+700h+var_620], r15
0x1004078f1  cmp     [r12+40h], r15
0x1004078f6  jz      short loc_10040795E
0x1004078f8  xor     edx, edx; Val
0x1004078fa  mov     r8d, 0E8h; Size
0x100407900  lea     rcx, [rbp+700h+var_700]; void *
0x100407904  call    memset_0
0x100407909  mov     rax, cs:__imp_?SOS_OS_StackBackTraceRoutine@@3P6AGKKPEAPEAXPEAK@ZEA; ushort (*SOS_OS_StackBackTraceRoutine)(ulong,ulong,void * *,ulong *)
0x100407910  mov     r10, [rax]
0x100407913  lea     r9, [rbp+700h+var_6F0]
0x100407917  lea     r8, [rbp+700h+var_6E8]
0x10040791b  mov     edx, 18h
0x100407920  lea     ecx, [rdx-17h]
0x100407923  call    r10
0x100407926  movzx   eax, ax
0x100407929  mov     [rbp+700h+var_628], eax
0x10040792f  mov     ecx, [rbp+700h+var_6F0]
0x100407932  shl     ecx, 0Fh
0x100407935  not     ecx
0x100407937  add     ecx, [rbp+700h+var_6F0]
0x10040793a  mov     eax, ecx
0x10040793c  shr     eax, 0Ah
0x10040793f  xor     eax, ecx
0x100407941  lea     eax, [rax+rax*8]
0x100407944  mov     ecx, eax
0x100407946  shr     ecx, 6
0x100407949  xor     ecx, eax
0x10040794b  mov     edx, ecx
0x10040794d  shl     edx, 0Bh
0x100407950  not     edx
0x100407952  add     edx, ecx
0x100407954  mov     eax, edx
0x100407956  shr     eax, 10h
0x100407959  xor     eax, edx
0x10040795b  mov     [rbp+700h+var_6F0], eax
0x10040795e  lea     r8, [rbp+700h+var_700]
0x100407962  lea     rdx, [rbp+700h+var_270]
0x100407969  mov     rcx, r12
0x10040796c  call    cs:__imp_?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x100407972  lea     rdx, [rbp+700h+pe]; lppe
0x100407979  mov     rcx, r13; hSnapshot
0x10040797c  call    cs:__imp_Process32NextW
0x100407982  test    eax, eax
  ... truncated ...
```
