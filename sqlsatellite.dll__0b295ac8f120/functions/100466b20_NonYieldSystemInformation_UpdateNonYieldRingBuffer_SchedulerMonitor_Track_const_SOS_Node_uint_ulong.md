# NonYieldSystemInformation::UpdateNonYieldRingBuffer(SchedulerMonitor::Track const *,SOS_Node *,uint,ulong)

- ea: `0x100466b20`
- end: `0x1004673dc`
- name: `?UpdateNonYieldRingBuffer@NonYieldSystemInformation@@QEAAXPEBVTrack@SchedulerMonitor@@PEAVSOS_Node@@IK@Z`
- size: `2236`
- prototype: `void __fastcall(NonYieldSystemInformation *__hidden this, const struct SchedulerMonitor::Track *, struct SOS_Node *, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x100465450`
- `0x100465cb0`
- `0x1004661f0`

## callees

- `0x100455f90`
- `0x100466b20`
- `0x1004674e0`
- `0x1004675e0`
- `0x100467820`
- `0x100486af0`

## import_xrefs

- `KERNEL32!Thread32First` at `0x100466ff0`
- `KERNEL32!Thread32First` at `0x100466ff0`
- `KERNEL32!OpenProcess` at `0x100466f1a`
- `KERNEL32!OpenProcess` at `0x100466f1a`
- `KERNEL32!Process32NextW` at `0x100466fb3`
- `KERNEL32!Process32NextW` at `0x100466fb3`
- `KERNEL32!K32GetProcessMemoryInfo` at `0x100466f38`
- `KERNEL32!K32GetProcessMemoryInfo` at `0x100466f38`
- `KERNEL32!GetThreadTimes` at `0x100467035`
- `KERNEL32!GetThreadTimes` at `0x100467035`
- `KERNEL32!OpenThread` at `0x10046700f`
- `KERNEL32!OpenThread` at `0x10046700f`
- `KERNEL32!Thread32Next` at `0x1004670f7`
- `KERNEL32!Thread32Next` at `0x1004670f7`
- `KERNEL32!Process32FirstW` at `0x100466e73`
- `KERNEL32!Process32FirstW` at `0x100466e73`
- `KERNEL32!QueryPerformanceCounter` at `0x100466cc0`
- `KERNEL32!QueryPerformanceCounter` at `0x100466d12`
- `KERNEL32!QueryPerformanceCounter` at `0x1004672dd`
- `KERNEL32!QueryPerformanceCounter` at `0x100467330`
- `KERNEL32!QueryPerformanceCounter` at `0x100466cc0`
- `KERNEL32!QueryPerformanceCounter` at `0x100466d12`
- `KERNEL32!QueryPerformanceCounter` at `0x1004672dd`
- `KERNEL32!QueryPerformanceCounter` at `0x100467330`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x100466e0e`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x100466e0e`
- `KERNEL32!CloseHandle` at `0x100466f6d`
- `KERNEL32!CloseHandle` at `0x10046704a`
- `KERNEL32!CloseHandle` at `0x100466f6d`
- `KERNEL32!CloseHandle` at `0x10046704a`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100466d85`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100467372`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100466fa3`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x1004670e4`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100466fa3`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x1004670e4`
- `sqldk!?UpdateSystemHealth@SchedulerMonitor@@AEAAXH@Z` at `0x100466df8`
- `sqldk!?UpdateSystemHealth@SchedulerMonitor@@AEAAXH@Z` at `0x100466df8`
- `sqldk!?ResetNonYieldStats@SchedulerMonitor@@QEAAXPEAVTrack@1@@Z` at `0x10046723c`
- `sqldk!?ResetNonYieldStats@SchedulerMonitor@@QEAAXPEAVTrack@1@@Z` at `0x10046723c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100466cb0`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100466d02`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004672cd`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10046731f`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100466cd5`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x1004672f2`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x100466bb3`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x100466bb3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100466be1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100466be1`
- `sqldk!SystemThread_TlsIndex` at `0x100466c82`
- `sqldk!SystemThread_TlsIndex` at `0x10046729f`
- `sqldk!SystemThread_TlsOffset` at `0x100466c8b`
- `sqldk!SystemThread_TlsOffset` at `0x1004672a8`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100466c62`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10046727f`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x100466bac`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100466d91`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10046737e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100466d91`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10046737e`
- `pdh!PdhCloseQuery` at `0x100467123`
- `pdh!PdhCloseQuery` at `0x100467190`
- `pdh!PdhCloseQuery` at `0x100467210`
- `pdh!PdhCloseQuery` at `0x100467123`
- `pdh!PdhCloseQuery` at `0x100467190`
- `pdh!PdhCloseQuery` at `0x100467210`
- `pdh!PdhGetFormattedCounterValue` at `0x1004671ef`
- `pdh!PdhGetFormattedCounterValue` at `0x1004671ef`
- `pdh!PdhOpenQueryW` at `0x10046713b`
- `pdh!PdhOpenQueryW` at `0x10046713b`
- `pdh!PdhAddCounterW` at `0x10046716f`
- `pdh!PdhAddCounterW` at `0x10046716f`
- `pdh!PdhCollectQueryData` at `0x1004671b6`
- `pdh!PdhCollectQueryData` at `0x1004671b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall NonYieldSystemInformation::UpdateNonYieldRingBuffer(
        NonYieldSystemInformation *this,
        const struct SchedulerMonitor::Track *a2,
        LARGE_INTEGER *a3,
        unsigned int a4,
        unsigned int a5)
{
  unsigned int v9; // ebx
  unsigned int v10; // r15d
  int v11; // edi
  int v12; // edx
  __int64 v13; // rsi
  __int64 v14; // rax
  LARGE_INTEGER v15; // rbx
  signed __int64 UniqueThread_low; // r15
  __int64 v17; // rdi
  __int64 v18; // r8
  char *v19; // rcx
  LARGE_INTEGER v20; // rax
  LONGLONG v21; // rcx
  __int64 v22; // rax
  int v23; // r8d
  LARGE_INTEGER v24; // rax
  void *QuadPart; // r12
  HANDLE Toolhelp32Snapshot; // rax
  __int64 v27; // r13
  DWORD th32ProcessID; // r8d
  __int64 v29; // rdx
  char *v30; // rcx
  __int16 v31; // ax
  char *v32; // rax
  HANDLE v33; // rax
  void *v34; // rbx
  struct _FILETIME v35; // rsi
  struct _FILETIME v36; // rdi
  HANDLE v37; // rbx
  struct _FILETIME *v38; // rcx
  int v39; // ebx
  void *v40; // rcx
  PDH_STATUS v41; // eax
  int v42; // ebx
  PDH_STATUS v43; // eax
  PDH_STATUS Data; // eax
  char *v45; // rbx
  __int64 v46; // rdi
  volatile signed __int64 *v47; // rsi
  LARGE_INTEGER v48; // rbx
  signed __int64 v49; // r14
  __int64 v50; // rdi
  __int64 v51; // r8
  LARGE_INTEGER v52; // rax
  LONGLONG v53; // rcx
  int v54; // r8d
  int v55; // [rsp+30h] [rbp-D0h]
  __int64 v57; // [rsp+40h] [rbp-C0h]
  _QWORD *v58; // [rsp+40h] [rbp-C0h]
  LARGE_INTEGER v59; // [rsp+50h] [rbp-B0h] BYREF
  LARGE_INTEGER v60; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v61; // [rsp+60h] [rbp-A0h]
  _QWORD *v62; // [rsp+68h] [rbp-98h]
  int v63; // [rsp+70h] [rbp-90h]
  LARGE_INTEGER PerformanceCount; // [rsp+78h] [rbp-88h] BYREF
  LARGE_INTEGER v65; // [rsp+80h] [rbp-80h] BYREF
  struct _FILETIME KernelTime; // [rsp+88h] [rbp-78h] BYREF
  struct _FILETIME UserTime; // [rsp+90h] [rbp-70h] BYREF
  __int128 v68; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v69; // [rsp+B0h] [rbp-50h]
  DWORD th32OwnerProcessID; // [rsp+B8h] [rbp-48h]
  DWORD th32ThreadID; // [rsp+BCh] [rbp-44h]
  struct _FILETIME v72; // [rsp+C0h] [rbp-40h]
  struct _FILETIME v73; // [rsp+C8h] [rbp-38h]
  struct _FILETIME v74; // [rsp+D0h] [rbp-30h]
  struct _FILETIME v75; // [rsp+D8h] [rbp-28h]
  __int64 v76; // [rsp+E0h] [rbp-20h]
  struct _FILETIME ExitTime; // [rsp+E8h] [rbp-18h] BYREF
  struct _FILETIME CreationTime; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v79[216]; // [rsp+100h] [rbp+0h] BYREF
  int v80; // [rsp+1D8h] [rbp+D8h]
  __int64 v81; // [rsp+1E0h] [rbp+E0h]
  _BYTE v82[216]; // [rsp+1F0h] [rbp+F0h] BYREF
  int v83; // [rsp+2C8h] [rbp+1C8h]
  __int64 v84; // [rsp+2D0h] [rbp+1D0h]
  THREADENTRY32 te; // [rsp+2E0h] [rbp+1E0h] BYREF
  PROCESSENTRY32W pe; // [rsp+300h] [rbp+200h] BYREF
  PROCESS_MEMORY_COUNTERS ppsmemCounters; // [rsp+540h] [rbp+440h] BYREF
  __int64 v88; // [rsp+588h] [rbp+488h]
  __int128 v89; // [rsp+590h] [rbp+490h] BYREF
  __int64 v90; // [rsp+5A0h] [rbp+4A0h]
  DWORD v91; // [rsp+5A8h] [rbp+4A8h]
  char v92; // [rsp+5ACh] [rbp+4ACh] BYREF
  DWORD PageFaultCount; // [rsp+7B4h] [rbp+6B4h]
  SIZE_T WorkingSetSize; // [rsp+7B8h] [rbp+6B8h]
  __int64 v95; // [rsp+7C0h] [rbp+6C0h]

  v76 = -2;
  v9 = a5 >> 1;
  v10 = 0;
  v11 = 0;
  v55 = 0;
  v60.QuadPart = (LONGLONG)&a3[242];
  v59 = a3[242];
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
      v61 = v13;
      v14 = *((_QWORD *)this + 1);
      v57 = v14;
      if ( v13 || v14 )
      {
        if ( !v12 && !a3[243].QuadPart )
        {
          v62 = (_QWORD *)((char *)this + 159960);
          v63 = 0;
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
                QueryPerformanceCounter(&v65);
                v20 = v65;
              }
              else
              {
                v20.QuadPart = MEMORY[0x7FFE0008];
              }
              v21 = v20.QuadPart - v15.QuadPart;
              if ( v20.QuadPart < (unsigned __int64)v15.QuadPart )
                v21 = 0;
              *(_QWORD *)(v17 + 3192) += v21;
              v11 = 0;
            }
            else
            {
              v11 = 0;
            }
          }
          v63 = 1;
          v22 = *((_QWORD *)this + 3);
          if ( !v22 || !*(_QWORD *)(v22 + 8) )
          {
            *((_QWORD *)this + 3) = a3 + 242;
            a3[243] = *(LARGE_INTEGER *)((char *)a2 + 400);
          }
          if ( v62 )
          {
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v23 = rand();
              if ( v23 == 5 * (v23 / 5) )
                Spinlock<48,1,268435714>::UpdateStatSnapshot();
            }
            *v62 = 0;
            v62 = 0;
            v63 = 0;
          }
          v10 = 0;
          v13 = v61;
        }
        v24 = a3[243];
        if ( v24.QuadPart )
        {
          if ( v24.QuadPart == *((_QWORD *)a2 + 50) )
          {
            SchedulerMonitor::UpdateSystemHealth((SchedulerMonitor *)&a3[242], 1);
            QuadPart = (void *)v59.QuadPart;
            if ( v59.QuadPart == -1 )
            {
              Toolhelp32Snapshot = CreateToolhelp32Snapshot(6u, 0);
              QuadPart = Toolhelp32Snapshot;
              if ( Toolhelp32Snapshot == (HANDLE)-1LL )
                return;
              a3[242].QuadPart = (LONGLONG)Toolhelp32Snapshot;
              if ( v13 )
                *(_DWORD *)(v13 + 48) = 0;
              v27 = v57;
              if ( v57 )
                *(_DWORD *)(v57 + 48) = 0;
              v11 = 1;
              v55 = 1;
            }
            else
            {
              v27 = v57;
            }
            if ( v13 && Process32FirstW(QuadPart, &pe) )
            {
              v10 = 0;
              do
              {
                v89 = 0;
                v90 = 0;
                th32ProcessID = pe.th32ProcessID;
                v91 = pe.th32ProcessID;
                PageFaultCount = 0;
                WorkingSetSize = 0;
                v95 = 0;
                v29 = 260;
                v30 = &v92;
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
                    v95 = v88;
                  }
                  CloseHandle(v34);
                }
                v80 = 0;
                v81 = 0;
                if ( *(_QWORD *)(v13 + 64) )
                  StackFrames<24>::CaptureCurrent(v79, 1);
                SOS_RingBuffer::StoreRecordInternalWithoutEvent(v13, &v89, v79);
              }
              while ( Process32NextW(QuadPart, &pe) );
              v11 = v55;
            }
            if ( v27 && (v11 || !(a4 % a5)) )
            {
              if ( Thread32First(QuadPart, &te) )
              {
                v35 = 0;
                do
                {
                  v36 = 0;
                  v37 = OpenThread(0x40u, 0, te.th32ThreadID);
                  if ( v37 && GetThreadTimes(v37, &CreationTime, &ExitTime, &KernelTime, &UserTime) )
                  {
                    v36 = KernelTime;
                    v35 = UserTime;
                    CloseHandle(v37);
                  }
                  v38 = (struct _FILETIME *)((char *)this + 8 * v10);
                  v39 = v55;
                  if ( v55 )
                  {
                    v38[3609] = v36;
                    v38[11801] = v35;
                    v35 = 0;
                  }
                  else
                  {
                    v68 = 0;
                    v69 = 0;
                    th32OwnerProcessID = te.th32OwnerProcessID;
                    th32ThreadID = te.th32ThreadID;
                    v72 = v38[11801];
                    v73 = v35;
                    v74 = v38[3609];
                    v75 = v36;
                    v35 = 0;
                    v83 = 0;
                    v84 = 0;
                    if ( *(_QWORD *)(v27 + 64) )
                      StackFrames<24>::CaptureCurrent(v82, 1);
                    SOS_RingBuffer::StoreRecordInternalWithoutEvent(v27, &v68, v82);
                  }
                  ++v10;
                }
                while ( Thread32Next(QuadPart, &te) && v10 < 0x2000 );
                if ( v55 )
                {
                  v40 = (void *)*((_QWORD *)this + 19993);
                  if ( v40 != (void *)-1LL )
                    *((_DWORD *)this + 39988) = PdhCloseQuery(v40);
                  v41 = PdhOpenQueryW(0, 0, (PDH_HQUERY *)this + 19993);
                  *((_DWORD *)this + 39988) = v41;
                  if ( !v41 )
                  {
                    v42 = 0;
                    while ( 1 )
                    {
                      v43 = PdhAddCounterW(
                              *((PDH_HQUERY *)this + 19993),
                              (LPCWSTR)this + 2060 * v42 + 28,
                              0,
                              (PDH_HCOUNTER *)this + 515 * v42 + 4);
                      *((_DWORD *)this + 39988) = v43;
                      if ( v43 )
                        break;
                      if ( (unsigned int)++v42 >= 7 )
                        goto LABEL_90;
                    }
                    PdhCloseQuery(*((PDH_HQUERY *)this + 19993));
                    *((_QWORD *)this + 19993) = -1;
LABEL_90:
                    v39 = v55;
                  }
                }
                if ( !*((_DWORD *)this + 39988) )
                {
                  Data = PdhCollectQueryData(*((PDH_HQUERY *)this + 19993));
                  *((_DWORD *)this + 39988) = Data;
                  if ( !v39 )
                  {
                    if ( !Data )
                    {
                      v45 = (char *)this + 32;
                      v46 = 7;
                      do
                      {
                        *((_DWORD *)this + 39988) = PdhGetFormattedCounterValue(
                                                      *(PDH_HCOUNTER *)v45,
                                                      0x200u,
                                                      0,
                                                      (PPDH_FMT_COUNTERVALUE)(v45 + 8));
                        v45 += 4120;
                        --v46;
                      }
                      while ( v46 );
                    }
                    PdhCloseQuery(*((PDH_HQUERY *)this + 19993));
                    *((_QWORD *)this + 19993) = -1;
                  }
                }
              }
              if ( !(a4 % a5) )
              {
                SchedulerMonitor::ResetNonYieldStats((SchedulerMonitor *)v60.QuadPart, 0);
                v47 = (volatile signed __int64 *)((char *)this + 159960);
                v58 = (_QWORD *)((char *)this + 159960);
                v48.QuadPart = 0;
                v49 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
                if ( *(_DWORD *)v47 || _InterlockedCompareExchange64(v47, v49, 0) )
                {
                  v50 = 0;
                  if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
                  {
                    v51 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset;
                    if ( v51 && *(_QWORD *)(v51 + 272) == v51 )
                      v50 = *(_QWORD *)(v51 + 256);
                    if ( v50 )
                    {
                      if ( Base_PublicGlobals::sm_invariantTscAvailable )
                      {
                        QueryPerformanceCounter(&v60);
                        v48 = v60;
                      }
                      else
                      {
                        v48.QuadPart = MEMORY[0x7FFE0008];
                      }
                    }
                  }
                  if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
                    Spinlock<48,1,268435714>::SpinToAcquireWithExponentialBackoff(v47, v49);
                  else
                    Spinlock<48,1,268435714>::SpinToAcquireOptimistic(v47, v50, v49);
                  if ( v50 )
                  {
                    if ( Base_PublicGlobals::sm_invariantTscAvailable )
                    {
                      QueryPerformanceCounter(&v59);
                      v52 = v59;
                    }
                    else
                    {
                      v52.QuadPart = MEMORY[0x7FFE0008];
                    }
                    v53 = v52.QuadPart - v48.QuadPart;
                    if ( v52.QuadPart < (unsigned __int64)v48.QuadPart )
                      v53 = 0;
                    *(_QWORD *)(v50 + 3192) += v53;
                  }
                }
                qword_10052F138 = 0;
                if ( v58 )
                {
                  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                  {
                    v54 = rand();
                    if ( v54 == 5 * (v54 / 5) )
                      Spinlock<48,1,268435714>::UpdateStatSnapshot();
                  }
                  *v58 = 0;
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
0x100466b20  push    rbp
0x100466b22  push    rsi
0x100466b23  push    rdi
0x100466b24  push    r12
0x100466b26  push    r13
0x100466b28  push    r14
0x100466b2a  push    r15
0x100466b2c  lea     rbp, [rsp-6D0h]
0x100466b34  sub     rsp, 7D0h
0x100466b3b  mov     [rbp+700h+var_720], 0FFFFFFFFFFFFFFFEh
0x100466b43  mov     [rsp+800h+arg_8], rbx
0x100466b4b  mov     rax, cs:__security_cookie
0x100466b52  xor     rax, rsp
0x100466b55  mov     [rbp+700h+var_38], rax
0x100466b5c  mov     esi, r9d
0x100466b5f  mov     [rsp+800h+var_7C4], r9d
0x100466b64  mov     r13, r8
0x100466b67  mov     r12, rdx
0x100466b6a  mov     r14, rcx
0x100466b6d  mov     ebx, [rbp+700h+arg_20]
0x100466b73  shr     ebx, 1
0x100466b75  xor     eax, eax
0x100466b77  mov     r15d, eax
0x100466b7a  mov     [rsp+800h+var_7C8], eax
0x100466b7e  mov     edi, eax
0x100466b80  mov     [rsp+800h+var_7D0], eax
0x100466b84  lea     rax, [r8+790h]
0x100466b8b  mov     qword ptr [rsp+800h+var_7A8], rax
0x100466b90  mov     rax, [rax]
0x100466b93  mov     qword ptr [rsp+800h+var_7B0], rax
0x100466b98  mov     [rbp+700h+pe.dwSize], 238h
0x100466ba2  mov     [rbp+700h+te.dwSize], 1Ch
0x100466bac  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x100466bb3  call    cs:__imp_?IsXPlatInstance@OsInfo@@QEBA?B_NXZ; OsInfo::IsXPlatInstance(void)
0x100466bb9  test    al, al
0x100466bbb  jnz     loc_1004673B2
0x100466bc1  test    ebx, ebx
0x100466bc3  jnz     short loc_100466BE7
0x100466bc5  mov     [rsp+800h+lpUserTime], rdi
0x100466bca  mov     r9d, 5F6h
0x100466bd0  lea     r8, aSqlsosCpp; "sqlsos.cpp"
0x100466bd7  lea     rdx, aSnapshotPeriod; "SNAPSHOT_PERIOD != 0"
0x100466bde  lea     ecx, [rbx+1]
0x100466be1  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100466be7  xor     edx, edx
0x100466be9  mov     eax, esi
0x100466beb  div     ebx
0x100466bed  test    eax, eax
0x100466bef  jz      loc_1004673B2
0x100466bf5  mov     rsi, [r14]
0x100466bf8  mov     [rsp+800h+var_7A0], rsi
0x100466bfd  mov     rax, [r14+8]
0x100466c01  mov     [rsp+800h+var_7C0], rax
0x100466c06  test    rsi, rsi
0x100466c09  jnz     short loc_100466C14
0x100466c0b  test    rax, rax
0x100466c0e  jz      loc_1004673B2
0x100466c14  test    edx, edx
0x100466c16  jnz     loc_100466DCE
0x100466c1c  cmp     [r13+798h], rdi
0x100466c23  jnz     loc_100466DCE
0x100466c29  lea     rsi, [r14+270D8h]
0x100466c30  mov     [rsp+800h+var_798], rsi
0x100466c35  xor     edx, edx
0x100466c37  mov     [rsp+800h+var_790], edx
0x100466c3b  mov     ebx, edx
0x100466c3d  mov     eax, gs:48h
0x100466c45  mov     r15d, eax
0x100466c48  mov     eax, [rsi]
0x100466c4a  test    eax, eax
0x100466c4c  jnz     short loc_100466C62
0x100466c4e  xor     eax, eax
0x100466c50  lock cmpxchg [rsi], r15
0x100466c55  mov     eax, edx
0x100466c57  setz    al
0x100466c5a  test    eax, eax
0x100466c5c  jnz     loc_100466D47
0x100466c62  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100466c69  mov     ecx, [rax]
0x100466c6b  and     ecx, 84h
0x100466c71  mov     rdi, rdx
0x100466c74  cmp     cl, 84h
0x100466c77  jnz     short loc_100466CD5
0x100466c79  mov     rdx, gs:58h
0x100466c82  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100466c89  mov     ecx, [rax]
0x100466c8b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100466c92  mov     r8d, [rax]
0x100466c95  add     r8, [rdx+rcx*8]
0x100466c99  jz      short loc_100466CAB
0x100466c9b  cmp     [r8+110h], r8
0x100466ca2  jnz     short loc_100466CAB
0x100466ca4  mov     rdi, [r8+100h]
0x100466cab  test    rdi, rdi
0x100466cae  jz      short loc_100466CD5
0x100466cb0  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100466cb7  cmp     [rax], ebx
0x100466cb9  jz      short loc_100466CCD
0x100466cbb  lea     rcx, [rsp+800h+PerformanceCount]; lpPerformanceCount
0x100466cc0  call    cs:__imp_QueryPerformanceCounter
0x100466cc6  mov     rbx, qword ptr [rsp+800h+PerformanceCount]
0x100466ccb  jmp     short loc_100466CD5
0x100466ccd  mov     rbx, ds:7FFE0008h
0x100466cd5  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100466cdc  mov     rcx, rsi
0x100466cdf  cmp     byte ptr [rax+0C7h], 0
0x100466ce6  jge     short loc_100466CF5
0x100466ce8  mov     r8, r15
0x100466ceb  mov     rdx, rdi
0x100466cee  call    ?SpinToAcquireOptimistic@?$Spinlock@$0DA@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<48,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100466cf3  jmp     short loc_100466CFD
0x100466cf5  mov     rdx, r15
0x100466cf8  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0DA@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<48,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100466cfd  test    rdi, rdi
0x100466d00  jz      short loc_100466D43
0x100466d02  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100466d09  cmp     dword ptr [rax], 0
0x100466d0c  jz      short loc_100466D1E
0x100466d0e  lea     rcx, [rbp+700h+var_780]; lpPerformanceCount
0x100466d12  call    cs:__imp_QueryPerformanceCounter
0x100466d18  mov     rax, qword ptr [rbp+700h+var_780]
0x100466d1c  jmp     short loc_100466D26
0x100466d1e  mov     rax, ds:7FFE0008h
0x100466d26  mov     rcx, rax
0x100466d29  sub     rcx, rbx
0x100466d2c  cmp     rax, rbx
0x100466d2f  mov     esi, 0
0x100466d34  cmovb   rcx, rsi
0x100466d38  add     [rdi+0C78h], rcx
0x100466d3f  mov     edi, esi
0x100466d41  jmp     short loc_100466D49
0x100466d43  mov     edi, [rsp+800h+var_7D0]
0x100466d47  xor     esi, esi
0x100466d49  mov     [rsp+800h+var_790], 1
0x100466d51  mov     rax, [r14+18h]
0x100466d55  test    rax, rax
0x100466d58  jz      short loc_100466D61
0x100466d5a  cmp     qword ptr [rax+8], 0
0x100466d5f  jnz     short loc_100466D7B
0x100466d61  lea     rcx, [r13+790h]
0x100466d68  mov     [r14+18h], rcx
0x100466d6c  mov     rax, [r12+190h]
0x100466d74  mov     [r13+798h], rax
0x100466d7b  mov     rbx, [rsp+800h+var_798]
0x100466d80  test    rbx, rbx
0x100466d83  jz      short loc_100466DC4
0x100466d85  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x100466d8c  cmp     byte ptr [rax], 0
0x100466d8f  jz      short loc_100466DB8
0x100466d91  call    cs:__imp_rand
0x100466d97  mov     r8d, eax
0x100466d9a  mov     eax, 66666667h
0x100466d9f  imul    r8d
0x100466da2  sar     edx, 1
0x100466da4  mov     ecx, edx
0x100466da6  shr     ecx, 1Fh
0x100466da9  add     edx, ecx
0x100466dab  lea     ecx, [rdx+rdx*4]
0x100466dae  cmp     r8d, ecx
0x100466db1  jnz     short loc_100466DB8
0x100466db3  call    ?UpdateStatSnapshot@?$Spinlock@$0DA@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<48,1,268435714>::UpdateStatSnapshot(void)
0x100466db8  mov     [rbx], rsi
0x100466dbb  mov     [rsp+800h+var_798], rsi
0x100466dc0  mov     [rsp+800h+var_790], esi
0x100466dc4  mov     r15d, [rsp+800h+var_7C8]
0x100466dc9  mov     rsi, [rsp+800h+var_7A0]
0x100466dce  mov     rax, [r13+798h]
0x100466dd5  test    rax, rax
0x100466dd8  jz      loc_1004673B2
0x100466dde  cmp     rax, [r12+190h]
0x100466de6  jnz     loc_1004673B2
0x100466dec  mov     edx, 1
0x100466df1  lea     rcx, [r13+790h]
0x100466df8  call    cs:__imp_?UpdateSystemHealth@SchedulerMonitor@@AEAAXH@Z; SchedulerMonitor::UpdateSystemHealth(int)
0x100466dfe  mov     r12, qword ptr [rsp+800h+var_7B0]
0x100466e03  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x100466e07  jnz     short loc_100466E5B
0x100466e09  xor     edx, edx; th32ProcessID
0x100466e0b  lea     ecx, [rdx+6]; dwFlags
0x100466e0e  call    cs:__imp_CreateToolhelp32Snapshot
0x100466e14  mov     r12, rax
0x100466e17  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x100466e1b  jz      loc_1004673B2
0x100466e21  mov     [r13+790h], rax
0x100466e28  xor     eax, eax
0x100466e2a  test    rsi, rsi
0x100466e2d  jz      short loc_100466E3A
0x100466e2f  mov     [rsp+800h+var_7D0], eax
0x100466e33  mov     ecx, [rsp+800h+var_7D0]
0x100466e37  mov     [rsi+30h], ecx
0x100466e3a  mov     r13, [rsp+800h+var_7C0]
0x100466e3f  test    r13, r13
0x100466e42  jz      short loc_100466E50
0x100466e44  mov     [rsp+800h+var_7D0], eax
0x100466e48  mov     eax, [rsp+800h+var_7D0]
0x100466e4c  mov     [r13+30h], eax
0x100466e50  mov     edi, 1
0x100466e55  mov     [rsp+800h+var_7D0], edi
0x100466e59  jmp     short loc_100466E60
0x100466e5b  mov     r13, [rsp+800h+var_7C0]
0x100466e60  test    rsi, rsi
0x100466e63  jz      loc_100466FC5
0x100466e69  lea     rdx, [rbp+700h+pe]; lppe
0x100466e70  mov     rcx, r12; hSnapshot
0x100466e73  call    cs:__imp_Process32FirstW
0x100466e79  test    eax, eax
0x100466e7b  jz      loc_100466FC5
0x100466e81  lea     rdi, [rbp+700h+pe.szExeFile]
0x100466e88  lea     rax, [rbp+700h+var_254]
0x100466e8f  sub     rdi, rax
0x100466e92  xor     r15d, r15d
0x100466e95  nop     word ptr [rax+rax+00000000h]
0x100466ea0  xorps   xmm0, xmm0
0x100466ea3  xor     eax, eax
0x100466ea5  movups  [rbp+700h+var_270], xmm0
0x100466eac  mov     [rbp+700h+var_260], rax
0x100466eb3  mov     r8d, [rbp+700h+pe.th32ProcessID]; dwProcessId
0x100466eba  mov     [rbp+700h+var_258], r8d
0x100466ec1  mov     [rbp+700h+var_4C], r15d
0x100466ec8  mov     [rbp+700h+var_48], r15
0x100466ecf  mov     [rbp+700h+var_40], r15
0x100466ed6  mov     edx, 104h
0x100466edb  lea     rcx, [rbp+700h+var_254]
0x100466ee2  lea     rax, [rdx+7FFFFEFAh]
0x100466ee9  test    rax, rax
0x100466eec  jz      short loc_100466F04
0x100466eee  movzx   eax, word ptr [rdi+rcx]
0x100466ef2  test    ax, ax
0x100466ef5  jz      short loc_100466F04
0x100466ef7  mov     [rcx], ax
0x100466efa  add     rcx, 2
0x100466efe  sub     rdx, 1
0x100466f02  jnz     short loc_100466EE2
0x100466f04  lea     rax, [rcx-2]
0x100466f08  test    rdx, rdx
0x100466f0b  cmovnz  rax, rcx
0x100466f0f  mov     [rax], r15w
0x100466f13  xor     edx, edx; bInheritHandle
0x100466f15  mov     ecx, 400h; dwDesiredAccess
0x100466f1a  call    cs:__imp_OpenProcess
0x100466f20  mov     rbx, rax
0x100466f23  test    rax, rax
0x100466f26  jz      short loc_100466F73
0x100466f28  mov     r8d, 50h ; 'P'; cb
0x100466f2e  lea     rdx, [rbp+700h+ppsmemCounters]; ppsmemCounters
0x100466f35  mov     rcx, rax; Process
0x100466f38  call    cs:__imp_K32GetProcessMemoryInfo
0x100466f3e  test    eax, eax
0x100466f40  jz      short loc_100466F6A
0x100466f42  mov     ecx, [rbp+700h+ppsmemCounters.PageFaultCount]
0x100466f48  mov     [rbp+700h+var_4C], ecx
0x100466f4e  mov     rcx, [rbp+700h+ppsmemCounters.WorkingSetSize]
0x100466f55  mov     [rbp+700h+var_48], rcx
0x100466f5c  mov     rax, [rbp+700h+var_278]
0x100466f63  mov     [rbp+700h+var_40], rax
0x100466f6a  mov     rcx, rbx; hObject
0x100466f6d  call    cs:__imp_CloseHandle
0x100466f73  mov     [rbp+700h+var_628], r15d
0x100466f7a  mov     [rbp+700h+var_620], r15
0x100466f81  cmp     [rsi+40h], r15
0x100466f85  jz      short loc_100466F95
0x100466f87  mov     edx, 1
0x100466f8c  lea     rcx, [rbp+700h+var_700]
0x100466f90  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x100466f95  lea     r8, [rbp+700h+var_700]
0x100466f99  lea     rdx, [rbp+700h+var_270]
0x100466fa0  mov     rcx, rsi
0x100466fa3  call    cs:__imp_?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x100466fa9  lea     rdx, [rbp+700h+pe]; lppe
0x100466fb0  mov     rcx, r12; hSnapshot
0x100466fb3  call    cs:__imp_Process32NextW
0x100466fb9  test    eax, eax
0x100466fbb  jnz     loc_100466EA0
0x100466fc1  mov     edi, [rsp+800h+var_7D0]
0x100466fc5  test    r13, r13
0x100466fc8  jz      loc_1004673B2
0x100466fce  test    edi, edi
0x100466fd0  jnz     short loc_100466FE6
0x100466fd2  xor     edx, edx
0x100466fd4  mov     eax, [rsp+800h+var_7C4]
0x100466fd8  div     [rbp+700h+arg_20]
0x100466fde  test    edx, edx
0x100466fe0  jnz     loc_1004673B2
0x100466fe6  lea     rdx, [rbp+700h+te]; lpte
0x100466fed  mov     rcx, r12; hSnapshot
0x100466ff0  call    cs:__imp_Thread32First
0x100466ff6  test    eax, eax
0x100466ff8  jz      loc_100467221
0x100466ffe  xor     esi, esi
0x100467000  mov     rdi, rsi
0x100467003  mov     r8d, [rbp+700h+te.th32ThreadID]; dwThreadId
0x10046700a  xor     edx, edx; bInheritHandle
0x10046700c  lea     ecx, [rdx+40h]; dwDesiredAccess
0x10046700f  call    cs:__imp_OpenThread
0x100467015  mov     rbx, rax
0x100467018  test    rax, rax
0x10046701b  jz      short loc_100467050
0x10046701d  lea     rax, [rbp+700h+UserTime]
0x100467021  mov     [rsp+800h+lpUserTime], rax; lpUserTime
0x100467026  lea     r9, [rbp+700h+KernelTime]; lpKernelTime
  ... truncated ...
```
