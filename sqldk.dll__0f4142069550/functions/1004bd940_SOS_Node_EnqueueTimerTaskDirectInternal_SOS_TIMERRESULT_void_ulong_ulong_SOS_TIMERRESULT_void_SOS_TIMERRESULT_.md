# SOS_Node::EnqueueTimerTaskDirectInternal(SOS_TIMERRESULT (*)(void *,ulong *,ulong *),SOS_TIMERRESULT (*)(void *),SOS_TIMERRESULT (*)(void *),void *,ulong,ulong,SOSHost *)

- ea: `0x1004bd940`
- end: `0x1004be50b`
- name: `?EnqueueTimerTaskDirectInternal@SOS_Node@@AEAA?AW4SOS_RESULT@@P6A?AW4SOS_TIMERRESULT@@PEAXPEAK1@ZP6A?AW43@0@Z30KKPEAVSOSHost@@@Z`
- size: `3019`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1004b3750`
- `0x100558a60`

## callees

- `0x100403070`
- `0x100404860`
- `0x100406340`
- `0x100406510`
- `0x1004067b0`
- `0x1004097f0`
- `0x1004098e0`
- `0x10040a8f0`
- `0x1004104a0`
- `0x1004106b0`
- `0x100410810`
- `0x1004200b0`
- `0x1004208d0`
- `0x1004371b0`
- `0x100475600`
- `0x100475810`
- `0x100475a50`
- `0x100475b60`
- `0x1004795c0`
- `0x1004bd940`
- `0x1005546f0`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1004bd9b4`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1004bd9b4`
- `KERNEL32!VirtualProtect` at `0x1004bdd25`
- `KERNEL32!VirtualProtect` at `0x1004be331`
- `KERNEL32!VirtualProtect` at `0x1004bdd25`
- `KERNEL32!VirtualProtect` at `0x1004be331`
- `KERNEL32!QueryPerformanceCounter` at `0x1004bdc3d`
- `KERNEL32!QueryPerformanceCounter` at `0x1004bdc89`
- `KERNEL32!QueryPerformanceCounter` at `0x1004be06c`
- `KERNEL32!QueryPerformanceCounter` at `0x1004be0bb`
- `KERNEL32!QueryPerformanceCounter` at `0x1004be253`
- `KERNEL32!QueryPerformanceCounter` at `0x1004be2a5`
- `KERNEL32!QueryPerformanceCounter` at `0x1004bdc3d`
- `KERNEL32!QueryPerformanceCounter` at `0x1004bdc89`
- `KERNEL32!QueryPerformanceCounter` at `0x1004be06c`
- `KERNEL32!QueryPerformanceCounter` at `0x1004be0bb`
- `KERNEL32!QueryPerformanceCounter` at `0x1004be253`
- `KERNEL32!QueryPerformanceCounter` at `0x1004be2a5`
- `KERNEL32!VirtualAlloc` at `0x1004bde4d`
- `KERNEL32!VirtualAlloc` at `0x1004bde4d`
- `KERNEL32!VirtualFree` at `0x1004be483`
- `KERNEL32!VirtualFree` at `0x1004be483`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004bdd6e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004be3ef`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004be428`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004bdd6e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004be3ef`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004be428`

## string_xrefs

- `0x1004bde9c`: `Sql\DkTemp\sos\include\sos.inl`
- `0x1004bdad0`: `Sql\DkTemp\sos\src\sos.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall SOS_Node::EnqueueTimerTaskDirectInternal(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        int a7,
        __int64 a8)
{
  unsigned __int16 v11; // di
  _QWORD *v12; // r15
  __int64 v13; // rsi
  int v14; // eax
  LARGE_INTEGER v15; // r14
  unsigned __int16 v16; // ax
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rcx
  LARGE_INTEGER v19; // rbx
  _QWORD *v20; // rdi
  __int64 v21; // rsi
  MemoryClerkInternal *v22; // rsi
  __int64 v23; // rsi
  signed __int64 UniqueThread_low; // rdx
  __int64 v25; // r12
  __int64 v26; // rdx
  SpinlockBase *v27; // rcx
  LARGE_INTEGER v28; // rcx
  LONGLONG v29; // rax
  __int64 v30; // rcx
  LPVOID *v31; // rbx
  char v32; // cl
  bool v33; // zf
  _QWORD *v34; // rax
  __int64 v35; // rax
  int v36; // r8d
  __int64 v37; // rcx
  _QWORD *v38; // rsi
  _QWORD *v39; // rax
  __int64 v40; // rax
  SOS_Task *v41; // rdi
  LONGLONG v42; // rbx
  unsigned int v43; // eax
  unsigned int v44; // r13d
  unsigned int v45; // ecx
  SpinlockBase *v46; // r12
  LARGE_INTEGER v47; // rbx
  signed __int64 v48; // rcx
  __int64 v49; // r14
  __int64 v50; // rdx
  LARGE_INTEGER v51; // rcx
  LONGLONG v52; // rax
  _QWORD *v53; // rcx
  __int64 v54; // rax
  __int64 v55; // rdx
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rbx
  _QWORD *v59; // r14
  __int64 v60; // rsi
  __int64 v61; // rdi
  LARGE_INTEGER v62; // rbx
  signed __int64 v63; // rcx
  __int64 v64; // rdx
  LARGE_INTEGER v65; // rcx
  LONGLONG v66; // rax
  _QWORD *v67; // rcx
  unsigned __int64 v68; // rax
  SOS_ObjectStore *v69; // rcx
  __int64 PoolIdForObject; // r10
  __int64 v71; // r9
  __int64 v72; // rax
  _QWORD *v73; // r8
  __int64 v74; // rcx
  int v75; // r8d
  int v76; // r8d
  _QWORD *v77; // rbx
  int v79; // [rsp+28h] [rbp-E0h]
  WorkDispatcher *v80; // [rsp+48h] [rbp-C0h]
  unsigned int PoolId; // [rsp+58h] [rbp-B0h]
  DWORD v82[2]; // [rsp+60h] [rbp-A8h] BYREF
  LARGE_INTEGER v83; // [rsp+68h] [rbp-A0h] BYREF
  DWORD flOldProtect[2]; // [rsp+70h] [rbp-98h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+78h] [rbp-90h] BYREF
  LARGE_INTEGER v86; // [rsp+80h] [rbp-88h] BYREF
  struct WorkDispatcher::WorkerIdleElem *v87; // [rsp+88h] [rbp-80h] BYREF
  struct SOS_Task *v88; // [rsp+90h] [rbp-78h] BYREF
  LARGE_INTEGER v89; // [rsp+98h] [rbp-70h] BYREF
  LARGE_INTEGER v90; // [rsp+A0h] [rbp-68h] BYREF
  LARGE_INTEGER v91; // [rsp+A8h] [rbp-60h] BYREF
  SpinlockBase *v92; // [rsp+B0h] [rbp-58h] BYREF
  int v93; // [rsp+B8h] [rbp-50h]
  __int64 v94; // [rsp+C0h] [rbp-48h]
  _BYTE v95[80]; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD v96[16]; // [rsp+118h] [rbp+10h] BYREF

  v94 = -2;
  *(_QWORD *)flOldProtect = a2;
  *(_QWORD *)v82 = a8;
  v11 = 0;
  v12 = 0;
  v13 = *(_QWORD *)(a1 + 1584);
  if ( SOS_PublicGlobals::sm_isIdleDetectionEnabled )
  {
    GetSystemTimeAsFileTime((LPFILETIME)(a1 + 1928));
    v14 = *(_DWORD *)(a1 + 272);
    if ( v14 )
    {
      *(_DWORD *)(a1 + 272) = 0;
      ResourceMonitor::WakeUpSuspendedNodes(v14 == 2, 0);
    }
  }
  v15.QuadPart = SchedulerManager::FindBestFitScheduler(a1 + 328, ~v13, 0, 1);
  v83 = v15;
  v80 = *(WorkDispatcher **)(v15.QuadPart + 5144);
  if ( (*(_BYTE *)(a1 + 1568) & 4) == 0 )
    v11 = *(_WORD *)(a1 + 160);
  SystemAffinity::SafeCopy(&SOS_PublicGlobals::sm_AffinityMask, v96);
  v16 = 0;
  if ( v11 != 64 )
    v16 = v11;
  v17 = v96[*((unsigned __int16 *)&SOS_PublicGlobals::sm_SOSNodeInfo + 20 * v11 + 8)]
      & (unsigned __int64)*(&SOS_PublicGlobals::sm_SOSNodeInfo + 5 * v11 + 1)
      & (unsigned __int64)*(&SOS_PublicGlobals::sm_SOSNodeInfo + 5 * v16 + 1);
  v18 = 0;
  if ( (v17 & (v13 | (unsigned __int64)v80)) != v17 )
    v18 = v13 | (unsigned __int64)v80;
  *(_QWORD *)(a1 + 1584) = v18;
  if ( (a6 & 0x400) != 0
    && (*(_BYTE *)(a1 + 1568) & 8) != 0
    && *(_QWORD *)(v15.QuadPart + 4864) >= *(int *)(v15.QuadPart + 3552) )
  {
    goto LABEL_158;
  }
  v12 = (_QWORD *)(*(__int64 (__fastcall **)(unsigned __int64, __int64, const char *, __int64, char))(**(_QWORD **)(v15.QuadPart + 3696) + 80LL))(
                    v18,
                    104,
                    "Sql\\DkTemp\\sos\\src\\sos.cpp",
                    1883,
                    6);
  v19.QuadPart = 0;
  if ( v12 )
  {
    *v12 = &TimerRequest::`vftable';
    v12[1] = 0;
    v12[2] = 0;
    *v12 = &SystemTimerRequest::`vftable';
    v12[7] = *(_QWORD *)flOldProtect;
    v12[8] = a3;
    v12[9] = a4;
    v12[10] = a5;
    *((_DWORD *)v12 + 22) = a6;
    v12[12] = 0;
    *((_DWORD *)v12 + 23) = a7;
  }
  else
  {
    v12 = 0;
  }
  if ( !v12 )
    goto LABEL_158;
  SOS_Task::Param::Init(
    (SOS_Task::Param *)v95,
    a6 | 0x100,
    (struct SOS_ResourceGroup *)qword_100716558,
    0xFFFFFFFFFFFFFFFFuLL,
    (void *(*)(void *))SOS_Scheduler::SystemTimerInit,
    v12,
    0);
  v20 = 0;
  v21 = *(_QWORD *)(v15.QuadPart + 5192);
  if ( !v21 )
    goto LABEL_58;
  v22 = *(MemoryClerkInternal **)(v21 + 240);
  if ( !v22 )
    goto LABEL_58;
  PoolId = MemoryClerkInternal::GetPoolId(v22);
  v23 = *((_QWORD *)v22 + 252);
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  if ( *(_DWORD *)(v23 + 40)
    || _InterlockedCompareExchange64((volatile signed __int64 *)(v23 + 40), UniqueThread_low, 0) )
  {
    v25 = 0;
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
    {
      v26 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
          + (unsigned int)SystemThread_TlsOffset;
      if ( v26 && *(_QWORD *)(v26 + 272) == v26 )
        v25 = *(_QWORD *)(v26 + 256);
      if ( v25 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&PerformanceCount);
          v19 = PerformanceCount;
        }
        else
        {
          v19.QuadPart = MEMORY[0x7FFE0008];
        }
      }
    }
    v27 = (SpinlockBase *)(v23 + 40);
    if ( (qword_1007149B5 & 0x800000) == 0 )
      Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v27);
    else
      Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v27);
    if ( v25 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v86);
        v28 = v86;
      }
      else
      {
        v28.QuadPart = MEMORY[0x7FFE0008];
      }
      v29 = 0;
      if ( v28.QuadPart >= (unsigned __int64)v19.QuadPart )
        v29 = v28.QuadPart - v19.QuadPart;
      *(_QWORD *)(v25 + 3192) += v29;
    }
  }
  v30 = v23 + 8LL * PoolId;
  if ( *(_QWORD *)(v30 + 1184) )
  {
    v20 = *(_QWORD **)(v30 + 1184);
    *(_QWORD *)(v30 + 1184) = *v20;
    *v20 = 0;
    --*(_QWORD *)(v23 + 8);
    if ( !*(_QWORD *)(v30 + 1184) )
    {
      v37 = *(_QWORD *)(v23 + 1696);
      if ( ((1LL << PoolId) & v37) != 0 )
        *(_QWORD *)(v23 + 1696) = v37 & ~(1LL << PoolId);
    }
  }
  else
  {
    v31 = (LPVOID *)(v23 + 16 * ((*(_DWORD *)(v23 + 1176) & 0x3F) + 9LL));
    v32 = *(_BYTE *)(*(_QWORD *)(v23 + 32) + 5820LL);
    if ( v32 )
      v33 = *v31 == 0;
    else
      v33 = *(_QWORD *)(v23 + 128) == 0;
    if ( !v33 )
    {
      if ( v32 )
      {
        VirtualProtect(*v31, 0x1000u, 4u, flOldProtect);
        v20 = *v31;
        v34 = *(_QWORD **)*v31;
        *v31 = v34;
        if ( !v34 )
          v31[1] = v31;
      }
      else
      {
        v20 = *(_QWORD **)(v23 + 128);
        v35 = *v20;
        *(_QWORD *)(v23 + 128) = *v20;
        if ( !v35 )
          *(_QWORD *)(v23 + 136) = v23 + 128;
      }
      --*(_QWORD *)(v23 + 8);
      --*(_QWORD *)(v23 + 1168);
    }
  }
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v36 = rand();
    if ( v36 == 5 * (v36 / 5) )
      Spinlock<34,1,268435714>::UpdateStatSnapshot();
  }
  *(_QWORD *)(v23 + 40) = 0;
  if ( v20 )
  {
    _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v15.QuadPart + 5192) + 264LL));
    SOSHost_Task::SOSHost_Task(
      (SOSHost_Task *)(v20 + 1),
      (struct SOS_Task::Param *)v95,
      (struct SOS_Scheduler *)v15.QuadPart,
      *(struct SOSHost **)v82);
    *v20 = &ISOSHost_TaskImpl::`vftable';
  }
  else
  {
LABEL_58:
    v38 = 0;
    if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
    {
      v39 = VirtualAlloc(0, 0x1000u, 0x3000u, 4u);
      v20 = v39;
      if ( !v39 )
        goto LABEL_67;
      SOSHost_Task::SOSHost_Task(
        (SOSHost_Task *)(v39 + 1),
        (struct SOS_Task::Param *)v95,
        (struct SOS_Scheduler *)v15.QuadPart,
        *(struct SOSHost **)v82);
      *v20 = &ISOSHost_TaskImpl::`vftable';
    }
    else
    {
      LOBYTE(v79) = 6;
      v40 = (*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64, int))(**(_QWORD **)(v15.QuadPart + 3704)
                                                                                   + 80LL))(
              *(_QWORD *)(v15.QuadPart + 3704),
              992,
              "Sql\\DkTemp\\sos\\include\\sos.inl",
              2560,
              v79);
      v20 = (_QWORD *)v40;
      if ( v40 )
      {
        SOSHost_Task::SOSHost_Task(
          (SOSHost_Task *)(v40 + 8),
          (struct SOS_Task::Param *)v95,
          (struct SOS_Scheduler *)v15.QuadPart,
          *(struct SOSHost **)v82);
        *v20 = &ISOSHost_TaskImpl::`vftable';
      }
      else
      {
        v20 = 0;
      }
      if ( !v20 )
        goto LABEL_67;
    }
  }
  v38 = v20 + 1;
  if ( v20 != (_QWORD *)-8LL )
  {
    TList<SOS_Scheduler,SOS_Task,16,TListSLock>::AppendElem(v15.QuadPart + 48, v20 + 1);
    v41 = (SOS_Task *)(v20 + 1);
    goto LABEL_68;
  }
LABEL_67:
  v41 = (SOS_Task *)v38;
  if ( !v38 )
  {
LABEL_158:
    v44 = -1073741824;
LABEL_159:
    if ( v12 )
      (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
    return v44;
  }
LABEL_68:
  v42 = v15.QuadPart + 36LL * *(unsigned int *)(*(_QWORD *)(v38[11] + 3336LL) + 2864LL);
  v43 = *((_DWORD *)v38 + 12);
  _InterlockedExchangeAdd((volatile signed __int32 *)(v42 + 168), v43);
  _InterlockedExchangeAdd((volatile signed __int32 *)(v15.QuadPart + 5212), v43);
  _InterlockedIncrement((volatile signed __int32 *)(v15.QuadPart + 3544));
  _InterlockedIncrement((volatile signed __int32 *)(v15.QuadPart + 3548));
  v44 = WorkDispatcher::AcquireWorker(v15.QuadPart + 4816, 1, 0, &v87);
  if ( v44 )
  {
    v88 = 0;
    v45 = -*((_DWORD *)v38 + 12);
    _InterlockedExchangeAdd((volatile signed __int32 *)(v42 + 168), v45);
    _InterlockedExchangeAdd((volatile signed __int32 *)(v15.QuadPart + 5212), v45);
    _InterlockedDecrement((volatile signed __int32 *)(v15.QuadPart + 3544));
  }
  else
  {
    WorkDispatcher::EnqueueTask((WorkDispatcher *)(v15.QuadPart + 4816), (struct SOS_Task *)v38, v87, &v88);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v38 + 10, 0xFFFFFFFF) == 1 )
  {
    if ( v38[3] )
    {
      TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(v38 + 2);
    }
    else
    {
      if ( *((_DWORD *)v38 + 46) == 2 )
      {
        v92 = (SpinlockBase *)(v38[20] + 4952LL);
        v46 = v92;
        v93 = 0;
        v47.QuadPart = 0;
        v48 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        if ( *(_DWORD *)v92 || _InterlockedCompareExchange64((volatile signed __int64 *)v92, v48, 0) )
        {
          v49 = 0;
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
          {
            v50 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                + (unsigned int)SystemThread_TlsOffset;
            if ( v50 && *(_QWORD *)(v50 + 272) == v50 )
              v49 = *(_QWORD *)(v50 + 256);
            if ( v49 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v89);
                v47 = v89;
              }
              else
              {
                v47.QuadPart = MEMORY[0x7FFE0008];
              }
            }
          }
          if ( (qword_1007149B5 & 0x800000) == 0 )
            Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v46);
          else
            Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v46);
          if ( v49 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v90);
              v51 = v90;
            }
            else
            {
              v51.QuadPart = MEMORY[0x7FFE0008];
            }
            v52 = 0;
            if ( v51.QuadPart >= (unsigned __int64)v47.QuadPart )
              v52 = v51.QuadPart - v47.QuadPart;
            *(_QWORD *)(v49 + 3192) += v52;
          }
        }
        v93 = 1;
        v53 = (_QWORD *)v38[1];
        v54 = *v38;
        *(_QWORD *)(v54 + 8) = v53;
        *v53 = v54;
        v38[1] = 0;
        *v38 = 0;
        SpinlockHolder<11,2,268435714>::~SpinlockHolder<11,2,268435714>(&v92);
      }
      v55 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
          + (unsigned int)SystemThread_TlsOffset;
      if ( v55 && *(_QWORD *)(v55 + 272) == v55 && (v56 = *(_QWORD *)(v55 + 256)) != 0 && *(_QWORD **)(v56 + 528) == v38 )
      {
        *(v38 - 1) = &ISOSHost_TaskImpl::`vftable';
        v83.QuadPart = (LONGLONG)v41;
        SOS_Task::~SOS_Task(v41);
      }
      else
      {
        v57 = v38[21];
        if ( !v57
          || (v58 = *(_QWORD *)(v57 + 240)) == 0
          || (*(_BYTE *)(v57 + 1568) & 2) != 0
          || SOS_OS_TaskStoreDisabled )
        {
          v77 = (_QWORD *)((char *)v41 - 8);
          if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
          {
            if ( !v38 )
              v77 = 0;
            VirtualFree(v77, 0, 0x8000u);
          }
          else if ( v41 != (SOS_Task *)8 )
          {
            *v77 = &ISOSHost_TaskImpl::`vftable';
            SOS_Task::~SOS_Task(v41);
            operator delete((char *)v41 - 8, 0x3E0u);
          }
        }
        else
        {
          v59 = v38 - 1;
          *(v38 - 1) = &ISOSHost_TaskImpl::`vftable';
          SOS_Task::~SOS_Task(v41);
          v33 = v38 == 0;
          v60 = 0;
          if ( v33 )
            v59 = 0;
          v61 = *(_QWORD *)(v58 + 2016);
          v62.QuadPart = 0;
          v63 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
          if ( *(_DWORD *)(v61 + 40) || _InterlockedCompareExchange64((volatile signed __int64 *)(v61 + 40), v63, 0) )
          {
            if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
            {
              v64 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                  + (unsigned int)SystemThread_TlsOffset;
              if ( v64 && *(_QWORD *)(v64 + 272) == v64 )
                v60 = *(_QWORD *)(v64 + 256);
              if ( v60 )
              {
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&v91);
                  v62 = v91;
                }
                else
                {
                  v62.QuadPart = MEMORY[0x7FFE0008];
                }
              }
            }
            if ( (qword_1007149B5 & 0x800000) == 0 )
              Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff((SpinlockBase *)(v61 + 40));
            else
              Spinlock<34,1,268435714>::SpinToAcquireOptimistic((SpinlockBase *)(v61 + 40));
            if ( v60 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v83);
                v65 = v83;
              }
              else
              {
                v65.QuadPart = MEMORY[0x7FFE0008];
              }
              v66 = 0;
              if ( v65.QuadPart >= (unsigned __int64)v62.QuadPart )
                v66 = v65.QuadPart - v62.QuadPart;
              *(_QWORD *)(v60 + 3192) += v66;
            }
          }
          if ( *(_QWORD *)(v61 + 8) >= *(_QWORD *)v61 )
          {
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v76 = rand();
              if ( v76 == 5 * (v76 / 5) )
                Spinlock<34,1,268435714>::UpdateStatSnapshot();
            }
            *(_QWORD *)(v61 + 40) = 0;
            (*(void (__fastcall **)(_QWORD *))(v61 + 48))(v59);
          }
          else
          {
            if ( *(_BYTE *)(*(_QWORD *)(v61 + 32) + 5820LL) )
            {
              v67 = (_QWORD *)(v61 + 16 * ((*(_DWORD *)(v61 + 1176) & 0x3F) + 9LL));
              *v59 = *v67;
              if ( !*v67 )
                v67[1] = v59;
              *v67 = v59;
              ++*(_QWORD *)(v61 + 1176);
              VirtualProtect(v59, 0x1000u, 1u, v82);
            }
            else
            {
              *v59 = *(_QWORD *)(v61 + 128);
              if ( !*(_QWORD *)(v61 + 128) )
                *(_QWORD *)(v61 + 136) = v59;
              *(_QWORD *)(v61 + 128) = v59;
            }
            v68 = *(_QWORD *)(v61 + 1168) + 1LL;
            ++*(_QWORD *)(v61 + 8);
            v69 = *(SOS_ObjectStore **)(v61 + 32);
            if ( !*((_BYTE *)v69 + 5820) && v68 >= 0x20 )
            {
              PoolIdForObject = SOS_ObjectStore::GetPoolIdForObject(v69, (struct SList *)v59);
              v71 = v61 + 8 * PoolIdForObject;
              v72 = *(_QWORD *)(v61 + 128);
              v73 = *(_QWORD **)(v61 + 136);
              if ( v73 != (_QWORD *)(v61 + 128) && v73 )
              {
                *v73 = *(_QWORD *)(v71 + 1184);
                *(_QWORD *)(v71 + 1184) = v72;
              }
              *(_QWORD *)(v61 + 128) = 0;
              *(_QWORD *)(v61 + 136) = v61 + 128;
              v68 = 0;
              v74 = *(_QWORD *)(v61 + 1696);
              if ( ((1LL << PoolIdForObject) & v74) == 0 )
                *(_QWORD *)(v61 + 1696) = v74 | (1LL << PoolIdForObject);
            }
            *(_QWORD *)(v61 + 1168) = v68;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v75 = rand();
              if ( v75 == 5 * (v75 / 5) )
                Spinlock<34,1,268435714>::UpdateStatSnapshot();
            }
            *(_QWORD *)(v61 + 40) = 0;
          }
        }
      }
    }
  }
  if ( v44 )
    goto LABEL_159;
  return v44;
}

```

## disassembly

```asm
0x1004bd940  mov     rax, rsp
0x1004bd943  push    rbp
0x1004bd944  push    r12
0x1004bd946  push    r13
0x1004bd948  push    r14
0x1004bd94a  push    r15
0x1004bd94c  lea     rbp, [rax-0C8h]
0x1004bd953  sub     rsp, 1A0h
0x1004bd95a  mov     [rbp+0C0h+var_108], 0FFFFFFFFFFFFFFFEh
0x1004bd962  mov     [rax+10h], rbx
0x1004bd966  mov     [rax+18h], rsi
0x1004bd96a  mov     [rax+20h], rdi
0x1004bd96e  mov     rax, cs:__security_cookie
0x1004bd975  xor     rax, rsp
0x1004bd978  mov     [rbp+0C0h+var_30], rax
0x1004bd97f  mov     r12, r9
0x1004bd982  mov     r13, r8
0x1004bd985  mov     qword ptr [rsp+1C0h+flOldProtect], rdx
0x1004bd98a  mov     rbx, rcx
0x1004bd98d  mov     rax, [rbp+0C0h+arg_38]
0x1004bd994  mov     qword ptr [rsp+1C0h+var_168], rax
0x1004bd999  xor     edi, edi
0x1004bd99b  mov     r15d, edi
0x1004bd99e  mov     rsi, [rcx+630h]
0x1004bd9a5  cmp     cs:?sm_isIdleDetectionEnabled@SOS_PublicGlobals@@2HA, edi; int SOS_PublicGlobals::sm_isIdleDetectionEnabled
0x1004bd9ab  jz      short loc_1004BD9D9
0x1004bd9ad  add     rcx, 788h; lpSystemTimeAsFileTime
0x1004bd9b4  call    cs:__imp_GetSystemTimeAsFileTime
0x1004bd9ba  mov     eax, [rbx+110h]
0x1004bd9c0  test    eax, eax
0x1004bd9c2  jz      short loc_1004BD9D9
0x1004bd9c4  mov     [rbx+110h], edi
0x1004bd9ca  mov     ecx, edi
0x1004bd9cc  cmp     eax, 2
0x1004bd9cf  setz    cl
0x1004bd9d2  xor     edx, edx
0x1004bd9d4  call    ?WakeUpSuspendedNodes@ResourceMonitor@@SAXHW4WakeUpReason@@@Z; ResourceMonitor::WakeUpSuspendedNodes(int,WakeUpReason)
0x1004bd9d9  mov     rdx, rsi
0x1004bd9dc  not     rdx
0x1004bd9df  lea     rcx, [rbx+148h]
0x1004bd9e6  mov     r9d, 1
0x1004bd9ec  xor     r8d, r8d
0x1004bd9ef  call    ?FindBestFitScheduler@SchedulerManager@@QEAAPEAVSOS_Scheduler@@_KKW4RWLockMode@@@Z; SchedulerManager::FindBestFitScheduler(unsigned __int64,ulong,RWLockMode)
0x1004bd9f4  mov     r14, rax
0x1004bd9f7  mov     qword ptr [rsp+1C0h+var_160], rax
0x1004bd9fc  mov     rax, [rax+1418h]
0x1004bda03  mov     [rsp+1C0h+var_180], rax
0x1004bda08  test    byte ptr [rbx+620h], 4
0x1004bda0f  jnz     short loc_1004BDA18
0x1004bda11  movzx   edi, word ptr [rbx+0A0h]
0x1004bda18  lea     rdx, [rbp+0C0h+var_B0]
0x1004bda1c  lea     rcx, ?sm_AffinityMask@SOS_PublicGlobals@@2VSystemAffinity@@A; SystemAffinity SOS_PublicGlobals::sm_AffinityMask
0x1004bda23  call    ?SafeCopy@SystemAffinity@@QEBA?AV1@XZ; SystemAffinity::SafeCopy(void)
0x1004bda28  movzx   eax, di
0x1004bda2b  lea     rcx, [rax+rax*4]
0x1004bda2f  lea     rdx, ?sm_SOSNodeInfo@SOS_PublicGlobals@@2PAVSOS_NodeInfo@@A; SOS_NodeInfo near * SOS_PublicGlobals::sm_SOSNodeInfo
0x1004bda36  movzx   eax, word ptr [rdx+rcx*8+10h]
0x1004bda3b  mov     r8, [rdx+rcx*8+8]
0x1004bda40  and     r8, [rbp+rax*8+0C0h+var_B0]
0x1004bda45  mov     ecx, 40h ; '@'
0x1004bda4a  xor     r9d, r9d
0x1004bda4d  mov     eax, r9d
0x1004bda50  cmp     cx, di
0x1004bda53  cmovnz  ax, di
0x1004bda57  movzx   eax, ax
0x1004bda5a  lea     rcx, [rax+rax*4]
0x1004bda5e  mov     rdx, [rdx+rcx*8+8]
0x1004bda63  and     rdx, r8
0x1004bda66  mov     r8, [rsp+1C0h+var_180]
0x1004bda6b  or      r8, rsi
0x1004bda6e  mov     rax, r8
0x1004bda71  and     rax, rdx
0x1004bda74  mov     ecx, r9d
0x1004bda77  cmp     rax, rdx
0x1004bda7a  cmovnz  rcx, r8
0x1004bda7e  mov     [rbx+630h], rcx
0x1004bda85  mov     edi, [rbp+0C0h+arg_28]
0x1004bda8b  bt      edi, 0Ah
0x1004bda8f  jnb     short loc_1004BDAAE
0x1004bda91  test    byte ptr [rbx+620h], 8
0x1004bda98  jz      short loc_1004BDAAE
0x1004bda9a  movsxd  rax, dword ptr [r14+0DE0h]
0x1004bdaa1  cmp     [r14+1300h], rax
0x1004bdaa8  jge     loc_1004BE4C0
0x1004bdaae  mov     dword ptr [rsp+1C0h+var_170], 75Bh
0x1004bdab6  mov     rcx, [r14+0E70h]
0x1004bdabd  mov     [rsp+1C0h+var_180], rcx
0x1004bdac2  mov     rax, [rcx]
0x1004bdac5  mov     byte ptr [rsp+1C0h+var_1A0], 6
0x1004bdaca  mov     r9d, 75Bh
0x1004bdad0  lea     r8, aSqlDktempSosSr_16; "Sql\\DkTemp\\sos\\src\\sos.cpp"
0x1004bdad7  mov     edx, 68h ; 'h'
0x1004bdadc  call    qword ptr [rax+50h]
0x1004bdadf  mov     r15, rax
0x1004bdae2  mov     qword ptr [rsp+1C0h+var_178], rax
0x1004bdae7  xor     ebx, ebx
0x1004bdae9  test    rax, rax
0x1004bdaec  jz      short loc_1004BDB3A
0x1004bdaee  lea     rax, ??_7TimerRequest@@6B@; const TimerRequest::`vftable'
0x1004bdaf5  mov     [r15], rax
0x1004bdaf8  mov     [r15+8], rbx
0x1004bdafc  mov     [r15+10h], rbx
0x1004bdb00  lea     rax, ??_7SystemTimerRequest@@6B@; const SystemTimerRequest::`vftable'
0x1004bdb07  mov     [r15], rax
0x1004bdb0a  mov     rax, qword ptr [rsp+1C0h+flOldProtect]
0x1004bdb0f  mov     [r15+38h], rax
0x1004bdb13  mov     [r15+40h], r13
0x1004bdb17  mov     [r15+48h], r12
0x1004bdb1b  mov     rax, [rbp+0C0h+arg_20]
0x1004bdb22  mov     [r15+50h], rax
0x1004bdb26  mov     [r15+58h], edi
0x1004bdb2a  mov     [r15+60h], rbx
0x1004bdb2e  mov     eax, [rbp+0C0h+arg_30]
0x1004bdb34  mov     [r15+5Ch], eax
0x1004bdb38  jmp     short loc_1004BDB3D
0x1004bdb3a  mov     r15, rbx
0x1004bdb3d  test    r15, r15
0x1004bdb40  jz      loc_1004BE4C0
0x1004bdb46  bts     edi, 8
0x1004bdb4a  mov     [rsp+1C0h+var_190], rbx; struct SOS_Task *
0x1004bdb4f  mov     [rsp+1C0h+var_198], r15; void *
0x1004bdb54  lea     rax, ?SystemTimerInit@SOS_Scheduler@@SAPEAXPEAX@Z; SOS_Scheduler::SystemTimerInit(void *)
0x1004bdb5b  mov     [rsp+1C0h+var_1A0], rax; void *(*)(void *)
0x1004bdb60  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1004bdb67  mov     r9, r12; unsigned __int64
0x1004bdb6a  lea     r8, qword_100716558; struct SOS_ResourceGroup *
0x1004bdb71  mov     edx, edi; unsigned int
0x1004bdb73  lea     rcx, [rbp+0C0h+var_100]; this
0x1004bdb77  call    ?Init@Param@SOS_Task@@QEAAXKPEAVSOS_ResourceGroup@@_KP6APEAXPEAX@Z2PEAV2@@Z; SOS_Task::Param::Init(ulong,SOS_ResourceGroup *,unsigned __int64,void * (*)(void *),void *,SOS_Task *)
0x1004bdb7c  mov     rdi, rbx
0x1004bdb7f  mov     rsi, [r14+1448h]
0x1004bdb86  lea     r13, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x1004bdb8d  test    rsi, rsi
0x1004bdb90  jz      loc_1004BDE05
0x1004bdb96  mov     rsi, [rsi+0F0h]
0x1004bdb9d  test    rsi, rsi
0x1004bdba0  jz      loc_1004BDE05
0x1004bdba6  mov     rcx, rsi; this
0x1004bdba9  call    ?GetPoolId@MemoryClerkInternal@@IEBAKXZ; MemoryClerkInternal::GetPoolId(void)
0x1004bdbae  mov     dword ptr [rsp+1C0h+var_170], eax
0x1004bdbb2  mov     rsi, [rsi+7E0h]
0x1004bdbb9  mov     ecx, gs:48h
0x1004bdbc1  mov     edx, ecx
0x1004bdbc3  mov     [rsp+1C0h+var_180], rdx
0x1004bdbc8  mov     ecx, [rsi+28h]
0x1004bdbcb  test    ecx, ecx
0x1004bdbcd  jnz     short loc_1004BDBEB
0x1004bdbcf  xor     eax, eax
0x1004bdbd1  lock cmpxchg [rsi+28h], rdx
0x1004bdbd7  mov     ecx, 0
0x1004bdbdc  mov     eax, ecx
0x1004bdbde  setz    al
0x1004bdbe1  test    eax, eax
0x1004bdbe3  jnz     loc_1004BDCC0
0x1004bdbe9  jmp     short loc_1004BDBED
0x1004bdbeb  xor     ecx, ecx
0x1004bdbed  mov     eax, cs:?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004bdbf3  and     eax, 84h
0x1004bdbf8  mov     r12, rcx
0x1004bdbfb  cmp     al, 84h
0x1004bdbfd  jnz     short loc_1004BDC57
0x1004bdbff  mov     rcx, gs:58h
0x1004bdc08  mov     eax, cs:_tls_index
0x1004bdc0e  mov     edx, cs:SystemThread_TlsOffset
0x1004bdc14  add     rdx, [rcx+rax*8]
0x1004bdc18  jz      short loc_1004BDC2A
0x1004bdc1a  cmp     [rdx+110h], rdx
0x1004bdc21  jnz     short loc_1004BDC2A
0x1004bdc23  mov     r12, [rdx+100h]
0x1004bdc2a  test    r12, r12
0x1004bdc2d  jz      short loc_1004BDC52
0x1004bdc2f  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004bdc36  jz      short loc_1004BDC4A
0x1004bdc38  lea     rcx, [rsp+1C0h+PerformanceCount]; lpPerformanceCount
0x1004bdc3d  call    cs:__imp_QueryPerformanceCounter
0x1004bdc43  mov     rbx, qword ptr [rsp+1C0h+PerformanceCount]
0x1004bdc48  jmp     short loc_1004BDC52
0x1004bdc4a  mov     rbx, ds:7FFE0008h
0x1004bdc52  mov     rdx, [rsp+1C0h+var_180]
0x1004bdc57  lea     rcx, [rsi+28h]; this
0x1004bdc5b  test    byte ptr cs:qword_1007149B5+2, 80h
0x1004bdc62  jz      short loc_1004BDC71
0x1004bdc64  mov     r8, rdx
0x1004bdc67  mov     rdx, r12
0x1004bdc6a  call    ?SpinToAcquireOptimistic@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<34,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x1004bdc6f  jmp     short loc_1004BDC76
0x1004bdc71  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x1004bdc76  test    r12, r12
0x1004bdc79  jz      short loc_1004BDCB9
0x1004bdc7b  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004bdc82  jz      short loc_1004BDC96
0x1004bdc84  lea     rcx, [rsp+1C0h+var_148]; lpPerformanceCount
0x1004bdc89  call    cs:__imp_QueryPerformanceCounter
0x1004bdc8f  mov     rcx, qword ptr [rsp+1C0h+var_148]
0x1004bdc94  jmp     short loc_1004BDC9E
0x1004bdc96  mov     rcx, ds:7FFE0008h
0x1004bdc9e  mov     rdx, rcx
0x1004bdca1  sub     rdx, rbx
0x1004bdca4  xor     r9d, r9d
0x1004bdca7  mov     eax, r9d
0x1004bdcaa  cmp     rcx, rbx
0x1004bdcad  cmovnb  rax, rdx
0x1004bdcb1  add     [r12+0C78h], rax
0x1004bdcb9  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1004bdcc0  mov     edx, dword ptr [rsp+1C0h+var_170]
0x1004bdcc4  lea     rcx, [rsi+rdx*8]
0x1004bdcc8  cmp     qword ptr [rcx+4A0h], 0
0x1004bdcd0  jnz     loc_1004BDDB6
0x1004bdcd6  mov     ebx, [rsi+498h]
0x1004bdcdc  and     ebx, 3Fh
0x1004bdcdf  add     rbx, 9
0x1004bdce3  shl     rbx, 4
0x1004bdce7  add     rbx, rsi
0x1004bdcea  mov     rax, [rsi+20h]
0x1004bdcee  movzx   ecx, byte ptr [rax+16BCh]
0x1004bdcf5  test    cl, cl
0x1004bdcf7  jz      short loc_1004BDCFF
0x1004bdcf9  cmp     qword ptr [rbx], 0
0x1004bdcfd  jmp     short loc_1004BDD07
0x1004bdcff  cmp     qword ptr [rsi+80h], 0
0x1004bdd07  setnz   al
0x1004bdd0a  test    al, al
0x1004bdd0c  jz      short loc_1004BDD63
0x1004bdd0e  test    cl, cl
0x1004bdd10  jz      short loc_1004BDD3F
0x1004bdd12  lea     r9, [rsp+1C0h+flOldProtect]; lpflOldProtect
0x1004bdd17  mov     edx, 1000h; dwSize
0x1004bdd1c  mov     r8d, 4; flNewProtect
0x1004bdd22  mov     rcx, [rbx]; lpAddress
0x1004bdd25  call    cs:__imp_VirtualProtect
0x1004bdd2b  mov     rdi, [rbx]
0x1004bdd2e  mov     rax, [rdi]
0x1004bdd31  mov     [rbx], rax
0x1004bdd34  test    rax, rax
0x1004bdd37  jnz     short loc_1004BDD58
0x1004bdd39  mov     [rbx+8], rbx
0x1004bdd3d  jmp     short loc_1004BDD58
0x1004bdd3f  lea     rcx, [rsi+80h]
0x1004bdd46  mov     rdi, [rcx]
0x1004bdd49  mov     rax, [rdi]
0x1004bdd4c  mov     [rcx], rax
0x1004bdd4f  test    rax, rax
0x1004bdd52  jnz     short loc_1004BDD58
0x1004bdd54  mov     [rcx+8], rcx
0x1004bdd58  dec     qword ptr [rsi+8]
0x1004bdd5c  dec     qword ptr [rsi+490h]
0x1004bdd63  xor     ebx, ebx
0x1004bdd65  cmp     cs:?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA, 0; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x1004bdd6c  jz      short loc_1004BDD95
0x1004bdd6e  call    cs:__imp_rand
0x1004bdd74  mov     r8d, eax
0x1004bdd77  mov     eax, 66666667h
0x1004bdd7c  imul    r8d
0x1004bdd7f  sar     edx, 1
0x1004bdd81  mov     ecx, edx
0x1004bdd83  shr     ecx, 1Fh
0x1004bdd86  add     edx, ecx
0x1004bdd88  lea     ecx, [rdx+rdx*4]
0x1004bdd8b  cmp     r8d, ecx
0x1004bdd8e  jnz     short loc_1004BDD95
0x1004bdd90  call    ?UpdateStatSnapshot@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<34,1,268435714>::UpdateStatSnapshot(void)
0x1004bdd95  mov     [rsi+28h], rbx
0x1004bdd99  lea     r13, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x1004bdda0  test    rdi, rdi
0x1004bdda3  jz      short loc_1004BDE05
0x1004bdda5  mov     rax, [r14+1448h]
0x1004bddac  lock inc qword ptr [rax+108h]
0x1004bddb4  jmp     short loc_1004BDE0D
0x1004bddb6  mov     rdi, [rcx+4A0h]
0x1004bddbd  mov     rax, [rdi]
0x1004bddc0  mov     [rcx+4A0h], rax
0x1004bddc7  xor     ebx, ebx
0x1004bddc9  mov     [rdi], rbx
0x1004bddcc  dec     qword ptr [rsi+8]
0x1004bddd0  cmp     [rcx+4A0h], rbx
0x1004bddd7  jnz     short loc_1004BDD65
0x1004bddd9  mov     ecx, edx
0x1004bdddb  mov     eax, 1
0x1004bdde0  shl     rax, cl
0x1004bdde3  mov     rcx, [rsi+6A0h]
0x1004bddea  test    rcx, rax
0x1004bdded  jz      loc_1004BDD65
0x1004bddf3  not     rax
0x1004bddf6  and     rax, rcx
0x1004bddf9  mov     [rsi+6A0h], rax
0x1004bde00  jmp     loc_1004BDD65
0x1004bde05  mov     rsi, rbx
0x1004bde08  test    rdi, rdi
0x1004bde0b  jz      short loc_1004BDE30
0x1004bde0d  mov     qword ptr [rsp+1C0h+var_178], rdi
0x1004bde12  lea     rcx, [rdi+8]; this
0x1004bde16  mov     r9, qword ptr [rsp+1C0h+var_168]; struct SOSHost *
0x1004bde1b  mov     r8, r14; struct SOS_Scheduler *
0x1004bde1e  lea     rdx, [rbp+0C0h+var_100]; struct SOS_Task::Param *
0x1004bde22  call    ??0SOSHost_Task@@IEAA@PEAVParam@SOS_Task@@PEAVSOS_Scheduler@@PEAVSOSHost@@@Z; SOSHost_Task::SOSHost_Task(SOS_Task::Param *,SOS_Scheduler *,SOSHost *)
0x1004bde27  nop
0x1004bde28  mov     [rdi], r13
0x1004bde2b  jmp     loc_1004BDEDB
0x1004bde30  test    cs:?SOS_Tracing_osTrace@@3KA, 1000h; ulong SOS_Tracing_osTrace
0x1004bde3a  jz      short loc_1004BDE7F
  ... truncated ...
```
