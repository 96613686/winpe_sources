# SOS_Scheduler::Start(void)

- ea: `0x10047dac0`
- end: `0x10047e641`
- name: `?Start@SOS_Scheduler@@IEAA?AW4SOS_RESULT@@XZ`
- size: `2945`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x10046de00`
- `0x1004718a0`

## callees

- `0x100403070`
- `0x100406340`
- `0x100406510`
- `0x1004067b0`
- `0x1004097f0`
- `0x1004098e0`
- `0x10040a8f0`
- `0x1004104a0`
- `0x1004106b0`
- `0x100410810`
- `0x100412b80`
- `0x100414400`
- `0x1004208d0`
- `0x10042aef0`
- `0x10042ba60`
- `0x10042bf30`
- `0x1004360f0`
- `0x1004371b0`
- `0x100475600`
- `0x100475810`
- `0x100475a50`
- `0x100475b60`
- `0x100477040`
- `0x1004771d0`
- `0x1004795c0`
- `0x10047dac0`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x10047db68`
- `KERNEL32!CreateEventW` at `0x10047db68`
- `KERNEL32!VirtualProtect` at `0x10047dd5c`
- `KERNEL32!VirtualProtect` at `0x10047e342`
- `KERNEL32!VirtualProtect` at `0x10047dd5c`
- `KERNEL32!VirtualProtect` at `0x10047e342`
- `KERNEL32!Sleep` at `0x10047e5c9`
- `KERNEL32!Sleep` at `0x10047e5c9`
- `KERNEL32!QueryPerformanceCounter` at `0x10047dc78`
- `KERNEL32!QueryPerformanceCounter` at `0x10047dcc1`
- `KERNEL32!QueryPerformanceCounter` at `0x10047e093`
- `KERNEL32!QueryPerformanceCounter` at `0x10047e0e2`
- `KERNEL32!QueryPerformanceCounter` at `0x10047e266`
- `KERNEL32!QueryPerformanceCounter` at `0x10047e2b8`
- `KERNEL32!QueryPerformanceCounter` at `0x10047dc78`
- `KERNEL32!QueryPerformanceCounter` at `0x10047dcc1`
- `KERNEL32!QueryPerformanceCounter` at `0x10047e093`
- `KERNEL32!QueryPerformanceCounter` at `0x10047e0e2`
- `KERNEL32!QueryPerformanceCounter` at `0x10047e266`
- `KERNEL32!QueryPerformanceCounter` at `0x10047e2b8`
- `KERNEL32!VirtualAlloc` at `0x10047de79`
- `KERNEL32!VirtualAlloc` at `0x10047de79`
- `KERNEL32!VirtualFree` at `0x10047e487`
- `KERNEL32!VirtualFree` at `0x10047e487`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10047ddf5`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10047e400`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10047e439`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10047ddf5`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10047e400`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10047e439`

## string_xrefs

- `0x10047decd`: `Sql\DkTemp\sos\include\sos.inl`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall SOS_Scheduler::Start(LARGE_INTEGER a1)
{
  unsigned int v2; // r14d
  HANDLE EventW; // rax
  __int64 v4; // r12
  __int64 v5; // r14
  MemoryClerkInternal *v6; // r14
  __int64 v7; // r14
  _QWORD *v8; // rsi
  LARGE_INTEGER v9; // rbx
  signed __int64 UniqueThread_low; // r12
  __int64 v11; // r15
  __int64 v12; // rdx
  SpinlockBase *v13; // rcx
  LARGE_INTEGER v14; // rcx
  LONGLONG v15; // rax
  __int64 v16; // rcx
  LPVOID *v17; // rbx
  char v18; // cl
  bool v19; // zf
  _QWORD *v20; // rax
  __int64 v21; // rax
  __int64 v22; // rcx
  int v23; // r8d
  _QWORD *v24; // rax
  __int64 v25; // rax
  _QWORD *v26; // rsi
  LONGLONG v27; // rbx
  unsigned int v28; // ecx
  SpinlockBase *v29; // r12
  LARGE_INTEGER v30; // rbx
  signed __int64 v31; // rcx
  __int64 v32; // r15
  __int64 v33; // rdx
  LARGE_INTEGER v34; // rcx
  LONGLONG v35; // rax
  _QWORD *v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rbx
  _QWORD *v42; // r15
  __int64 v43; // rsi
  LARGE_INTEGER v44; // rbx
  signed __int64 v45; // rcx
  __int64 v46; // rdx
  LARGE_INTEGER v47; // rcx
  LONGLONG v48; // rax
  _QWORD *v49; // rcx
  unsigned __int64 v50; // rax
  SOS_ObjectStore *v51; // rcx
  __int64 PoolIdForObject; // r10
  __int64 v53; // r9
  __int64 v54; // rax
  _QWORD *v55; // r8
  __int64 v56; // rcx
  int v57; // r8d
  int v58; // r8d
  __int64 v59; // r14
  unsigned int v60; // esi
  __int64 v61; // rax
  __int64 v62; // rbx
  __int64 v63; // rbx
  __int64 v64; // rax
  bool v65; // si
  int i; // ebx
  int v68; // [rsp+28h] [rbp-E0h]
  unsigned int PoolId; // [rsp+48h] [rbp-C0h]
  DWORD v70[2]; // [rsp+58h] [rbp-B0h] BYREF
  LARGE_INTEGER v71; // [rsp+60h] [rbp-A8h] BYREF
  DWORD flOldProtect[2]; // [rsp+68h] [rbp-A0h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+70h] [rbp-98h] BYREF
  LARGE_INTEGER v74; // [rsp+78h] [rbp-90h] BYREF
  struct WorkDispatcher::WorkerIdleElem *v75; // [rsp+80h] [rbp-88h] BYREF
  struct SOS_Task *v76; // [rsp+88h] [rbp-80h] BYREF
  LARGE_INTEGER v77; // [rsp+90h] [rbp-78h] BYREF
  LARGE_INTEGER v78; // [rsp+98h] [rbp-70h] BYREF
  LARGE_INTEGER v79; // [rsp+A0h] [rbp-68h] BYREF
  SpinlockBase *v80; // [rsp+A8h] [rbp-60h] BYREF
  int v81; // [rsp+B0h] [rbp-58h]
  int v82; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v83; // [rsp+C0h] [rbp-48h]
  __int64 v84; // [rsp+C8h] [rbp-40h]
  __int64 v85; // [rsp+D0h] [rbp-38h]
  __int64 v86; // [rsp+D8h] [rbp-30h]
  __int64 v87; // [rsp+E0h] [rbp-28h]
  _BYTE v88[80]; // [rsp+E8h] [rbp-20h] BYREF

  v87 = -2;
  v71 = a1;
  v2 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))IMemObj::InsertIntoMemObjList)(
         *(_QWORD *)(a1.QuadPart + 3696),
         0xFFFFFFFFLL,
         (LARGE_INTEGER)a1.QuadPart);
  if ( v2 )
    return v2;
  v2 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))IMemObj::InsertIntoMemObjList)(
         *(_QWORD *)(a1.QuadPart + 3704),
         0xFFFFFFFFLL,
         (LARGE_INTEGER)a1.QuadPart);
  if ( v2 )
    return v2;
  v2 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))IMemObj::InsertIntoMemObjList)(
         *(_QWORD *)(a1.QuadPart + 3712),
         0xFFFFFFFFLL,
         (LARGE_INTEGER)a1.QuadPart);
  if ( v2 )
    return v2;
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1.QuadPart + 3720) = EventW;
  if ( !EventW )
    return 0x80000000;
  v4 = 0;
  if ( (*(_BYTE *)(a1.QuadPart + 5104) & 8) != 0 )
    goto LABEL_144;
  SOS_Task::Param::Init(
    (SOS_Task::Param *)v88,
    2u,
    (struct SOS_ResourceGroup *)qword_100716558,
    0xFFFFFFFFFFFFFFFFuLL,
    (void *(*)(void *))SOS_Scheduler::Idle,
    (void *)a1.QuadPart,
    0);
  v5 = *(_QWORD *)(a1.QuadPart + 5192);
  if ( !v5 )
    goto LABEL_49;
  v6 = *(MemoryClerkInternal **)(v5 + 240);
  if ( !v6 )
    goto LABEL_49;
  PoolId = MemoryClerkInternal::GetPoolId(v6);
  v7 = *((_QWORD *)v6 + 252);
  v8 = 0;
  v9.QuadPart = 0;
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  if ( !*(_DWORD *)(v7 + 40)
    && !_InterlockedCompareExchange64((volatile signed __int64 *)(v7 + 40), UniqueThread_low, 0) )
  {
    goto LABEL_29;
  }
  v11 = 0;
  if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
  {
    v12 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
        + (unsigned int)SystemThread_TlsOffset;
    if ( v12 && *(_QWORD *)(v12 + 272) == v12 )
      v11 = *(_QWORD *)(v12 + 256);
    if ( v11 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&PerformanceCount);
        v9 = PerformanceCount;
      }
      else
      {
        v9.QuadPart = MEMORY[0x7FFE0008];
      }
    }
  }
  v13 = (SpinlockBase *)(v7 + 40);
  if ( (qword_1007149B5 & 0x800000) == 0 )
    Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v13);
  else
    Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v13);
  if ( v11 )
  {
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v74);
      v14 = v74;
    }
    else
    {
      v14.QuadPart = MEMORY[0x7FFE0008];
    }
    v4 = 0;
    v15 = 0;
    if ( v14.QuadPart >= (unsigned __int64)v9.QuadPart )
      v15 = v14.QuadPart - v9.QuadPart;
    *(_QWORD *)(v11 + 3192) += v15;
  }
  else
  {
LABEL_29:
    v4 = 0;
  }
  v16 = v7 + 8LL * PoolId;
  if ( *(_QWORD *)(v16 + 1184) )
  {
    v8 = *(_QWORD **)(v16 + 1184);
    *(_QWORD *)(v16 + 1184) = *v8;
    *v8 = 0;
    --*(_QWORD *)(v7 + 8);
    if ( !*(_QWORD *)(v16 + 1184) )
    {
      v22 = *(_QWORD *)(v7 + 1696);
      if ( ((1LL << PoolId) & v22) != 0 )
        *(_QWORD *)(v7 + 1696) = v22 & ~(1LL << PoolId);
    }
  }
  else
  {
    v17 = (LPVOID *)(v7 + 16 * ((*(_DWORD *)(v7 + 1176) & 0x3F) + 9LL));
    v18 = *(_BYTE *)(*(_QWORD *)(v7 + 32) + 5820LL);
    if ( v18 )
      v19 = *v17 == 0;
    else
      v19 = *(_QWORD *)(v7 + 128) == 0;
    if ( !v19 )
    {
      if ( v18 )
      {
        VirtualProtect(*v17, 0x1000u, 4u, flOldProtect);
        v8 = *v17;
        v20 = *(_QWORD **)*v17;
        *v17 = v20;
        if ( !v20 )
        {
          v17[1] = v17;
          --*(_QWORD *)(v7 + 8);
          --*(_QWORD *)(v7 + 1168);
          goto LABEL_44;
        }
      }
      else
      {
        v8 = *(_QWORD **)(v7 + 128);
        v21 = *v8;
        *(_QWORD *)(v7 + 128) = *v8;
        if ( !v21 )
          *(_QWORD *)(v7 + 136) = v7 + 128;
      }
      --*(_QWORD *)(v7 + 8);
      --*(_QWORD *)(v7 + 1168);
    }
  }
LABEL_44:
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v23 = rand();
    if ( v23 == 5 * (v23 / 5) )
      Spinlock<34,1,268435714>::UpdateStatSnapshot();
  }
  *(_QWORD *)(v7 + 40) = 0;
  if ( v8 )
  {
    _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(a1.QuadPart + 5192) + 264LL));
    SOSHost_Task::SOSHost_Task(
      (SOSHost_Task *)(v8 + 1),
      (struct SOS_Task::Param *)v88,
      (struct SOS_Scheduler *)a1.QuadPart,
      0);
    *v8 = &ISOSHost_TaskImpl::`vftable';
    goto LABEL_56;
  }
LABEL_49:
  if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
  {
    v24 = VirtualAlloc(0, 0x1000u, 0x3000u, 4u);
    v8 = v24;
    if ( !v24 )
      return (unsigned int)-1073741824;
    SOSHost_Task::SOSHost_Task(
      (SOSHost_Task *)(v24 + 1),
      (struct SOS_Task::Param *)v88,
      (struct SOS_Scheduler *)a1.QuadPart,
      0);
    *v8 = &ISOSHost_TaskImpl::`vftable';
  }
  else
  {
    LOBYTE(v68) = 6;
    v25 = (*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64, int))(**(_QWORD **)(a1.QuadPart + 3704)
                                                                                 + 80LL))(
            *(_QWORD *)(a1.QuadPart + 3704),
            992,
            "Sql\\DkTemp\\sos\\include\\sos.inl",
            2560,
            v68);
    v8 = (_QWORD *)v25;
    if ( v25 )
    {
      SOSHost_Task::SOSHost_Task(
        (SOSHost_Task *)(v25 + 8),
        (struct SOS_Task::Param *)v88,
        (struct SOS_Scheduler *)a1.QuadPart,
        0);
      *v8 = &ISOSHost_TaskImpl::`vftable';
    }
    else
    {
      v8 = 0;
    }
    if ( !v8 )
      return (unsigned int)-1073741824;
  }
LABEL_56:
  v26 = v8 + 1;
  if ( !v26 )
    return (unsigned int)-1073741824;
  TList<SOS_Scheduler,SOS_Task,16,TListSLock>::AppendElem(a1.QuadPart + 48, v26);
  *((_DWORD *)v26 + 12) = 0;
  v27 = a1.QuadPart + 36LL * *(unsigned int *)(*(_QWORD *)(v26[11] + 3336LL) + 2864LL);
  _InterlockedExchangeAdd((volatile signed __int32 *)(v27 + 168), 0);
  _InterlockedExchangeAdd((volatile signed __int32 *)(a1.QuadPart + 5212), 0);
  _InterlockedIncrement((volatile signed __int32 *)(a1.QuadPart + 3544));
  _InterlockedIncrement((volatile signed __int32 *)(a1.QuadPart + 3548));
  v2 = WorkDispatcher::AcquireWorker(a1.QuadPart + 4816, 2, 0, &v75);
  if ( v2 )
  {
    v76 = 0;
    v28 = -*((_DWORD *)v26 + 12);
    _InterlockedExchangeAdd((volatile signed __int32 *)(v27 + 168), v28);
    _InterlockedExchangeAdd((volatile signed __int32 *)(a1.QuadPart + 5212), v28);
    _InterlockedDecrement((volatile signed __int32 *)(a1.QuadPart + 3544));
  }
  else
  {
    WorkDispatcher::EnqueueTask((WorkDispatcher *)(a1.QuadPart + 4816), (struct SOS_Task *)v26, v75, &v76);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v26 + 10, 0xFFFFFFFF) == 1 )
  {
    if ( v26[3] )
    {
      TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(v26 + 2);
    }
    else
    {
      if ( *((_DWORD *)v26 + 46) == 2 )
      {
        v80 = (SpinlockBase *)(v26[20] + 4952LL);
        v29 = v80;
        v81 = 0;
        v30.QuadPart = 0;
        v31 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        if ( !*(_DWORD *)v80 && !_InterlockedCompareExchange64((volatile signed __int64 *)v80, v31, 0) )
          goto LABEL_84;
        v32 = 0;
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v33 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
              + (unsigned int)SystemThread_TlsOffset;
          if ( v33 && *(_QWORD *)(v33 + 272) == v33 )
            v32 = *(_QWORD *)(v33 + 256);
          if ( v32 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v77);
              v30 = v77;
            }
            else
            {
              v30.QuadPart = MEMORY[0x7FFE0008];
            }
          }
        }
        if ( (qword_1007149B5 & 0x800000) == 0 )
          Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v29);
        else
          Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v29);
        if ( v32 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v78);
            v34 = v78;
          }
          else
          {
            v34.QuadPart = MEMORY[0x7FFE0008];
          }
          v4 = 0;
          v35 = 0;
          if ( v34.QuadPart >= (unsigned __int64)v30.QuadPart )
            v35 = v34.QuadPart - v30.QuadPart;
          *(_QWORD *)(v32 + 3192) += v35;
        }
        else
        {
LABEL_84:
          v4 = 0;
        }
        v81 = 1;
        v36 = (_QWORD *)v26[1];
        v37 = *v26;
        *(_QWORD *)(v37 + 8) = v36;
        *v36 = v37;
        v26[1] = 0;
        *v26 = 0;
        SpinlockHolder<11,2,268435714>::~SpinlockHolder<11,2,268435714>(&v80);
      }
      v38 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
          + (unsigned int)SystemThread_TlsOffset;
      if ( v38 && *(_QWORD *)(v38 + 272) == v38 && (v39 = *(_QWORD *)(v38 + 256)) != 0 && *(_QWORD **)(v39 + 528) == v26 )
      {
        *(v26 - 1) = &ISOSHost_TaskImpl::`vftable';
        SOS_Task::~SOS_Task((SOS_Task *)v26);
      }
      else
      {
        v40 = v26[21];
        if ( !v40
          || (v41 = *(_QWORD *)(v40 + 240)) == 0
          || (*(_BYTE *)(v40 + 1568) & 2) != 0
          || SOS_OS_TaskStoreDisabled )
        {
          if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
          {
            VirtualFree(v26 - 1, 0, 0x8000u);
          }
          else if ( v26 != (_QWORD *)8 )
          {
            *(v26 - 1) = &ISOSHost_TaskImpl::`vftable';
            SOS_Task::~SOS_Task((SOS_Task *)v26);
            operator delete(v26 - 1, 0x3E0u);
          }
        }
        else
        {
          v42 = v26 - 1;
          *(v26 - 1) = &ISOSHost_TaskImpl::`vftable';
          SOS_Task::~SOS_Task((SOS_Task *)v26);
          v43 = *(_QWORD *)(v41 + 2016);
          v44.QuadPart = 0;
          v45 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
          if ( *(_DWORD *)(v43 + 40) || _InterlockedCompareExchange64((volatile signed __int64 *)(v43 + 40), v45, 0) )
          {
            if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
            {
              v46 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                  + (unsigned int)SystemThread_TlsOffset;
              if ( v46 && *(_QWORD *)(v46 + 272) == v46 )
                v4 = *(_QWORD *)(v46 + 256);
              if ( v4 )
              {
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&v79);
                  v44 = v79;
                }
                else
                {
                  v44.QuadPart = MEMORY[0x7FFE0008];
                }
              }
            }
            if ( (qword_1007149B5 & 0x800000) == 0 )
              Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff((SpinlockBase *)(v43 + 40));
            else
              Spinlock<34,1,268435714>::SpinToAcquireOptimistic((SpinlockBase *)(v43 + 40));
            if ( v4 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v71);
                v47 = v71;
              }
              else
              {
                v47.QuadPart = MEMORY[0x7FFE0008];
              }
              v48 = 0;
              if ( v47.QuadPart >= (unsigned __int64)v44.QuadPart )
                v48 = v47.QuadPart - v44.QuadPart;
              *(_QWORD *)(v4 + 3192) += v48;
            }
          }
          if ( *(_QWORD *)(v43 + 8) >= *(_QWORD *)v43 )
          {
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v58 = rand();
              if ( v58 == 5 * (v58 / 5) )
                Spinlock<34,1,268435714>::UpdateStatSnapshot();
            }
            *(_QWORD *)(v43 + 40) = 0;
            (*(void (__fastcall **)(_QWORD *))(v43 + 48))(v42);
          }
          else
          {
            if ( *(_BYTE *)(*(_QWORD *)(v43 + 32) + 5820LL) )
            {
              v49 = (_QWORD *)(v43 + 16 * ((*(_DWORD *)(v43 + 1176) & 0x3F) + 9LL));
              *v42 = *v49;
              if ( !*v49 )
                v49[1] = v42;
              *v49 = v42;
              ++*(_QWORD *)(v43 + 1176);
              VirtualProtect(v42, 0x1000u, 1u, v70);
            }
            else
            {
              *v42 = *(_QWORD *)(v43 + 128);
              if ( !*(_QWORD *)(v43 + 128) )
                *(_QWORD *)(v43 + 136) = v42;
              *(_QWORD *)(v43 + 128) = v42;
            }
            v50 = *(_QWORD *)(v43 + 1168) + 1LL;
            ++*(_QWORD *)(v43 + 8);
            v51 = *(SOS_ObjectStore **)(v43 + 32);
            if ( !*((_BYTE *)v51 + 5820) && v50 >= 0x20 )
            {
              PoolIdForObject = SOS_ObjectStore::GetPoolIdForObject(v51, (struct SList *)v42);
              v53 = v43 + 8 * PoolIdForObject;
              v54 = *(_QWORD *)(v43 + 128);
              v55 = *(_QWORD **)(v43 + 136);
              if ( v55 != (_QWORD *)(v43 + 128) && v55 )
              {
                *v55 = *(_QWORD *)(v53 + 1184);
                *(_QWORD *)(v53 + 1184) = v54;
              }
              *(_QWORD *)(v43 + 128) = 0;
              *(_QWORD *)(v43 + 136) = v43 + 128;
              v50 = 0;
              v56 = *(_QWORD *)(v43 + 1696);
              if ( ((1LL << PoolIdForObject) & v56) == 0 )
                *(_QWORD *)(v43 + 1696) = v56 | (1LL << PoolIdForObject);
            }
            *(_QWORD *)(v43 + 1168) = v50;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v57 = rand();
              if ( v57 == 5 * (v57 / 5) )
                Spinlock<34,1,268435714>::UpdateStatSnapshot();
            }
            *(_QWORD *)(v43 + 40) = 0;
          }
        }
      }
    }
  }
  if ( !v2 )
  {
    v2 = (*(__int64 (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)a1.QuadPart + 40LL))(a1);
    if ( !v2 )
    {
LABEL_144:
      v59 = *(_QWORD *)(a1.QuadPart + 5200);
      v60 = 0;
      v61 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))Worker::CreateWorker)(
              *(_QWORD *)(a1.QuadPart + 5192),
              (LARGE_INTEGER)a1.QuadPart,
              4);
      v62 = v61;
      if ( v61
        && (TList<SchedulerManager,Worker,24,TListSLock>::AppendElem(v59, v61),
            v60 = SystemThreadDispatcher::EnqueueWorker(v59 + 192, v62, 1),
            (v2 = v60) != 0)
        && _InterlockedExchangeAdd((volatile signed __int32 *)(v62 + 48), 0xFFFFFFFF) == 1 )
      {
        if ( *(_QWORD *)(v62 + 32) )
          TList<SchedulerManager,Worker,24,TListSLock>::RemoveElem(*(_QWORD *)(v62 + 40), v62);
        Worker::Destroy((Worker *)v62);
      }
      else
      {
        v2 = v60;
        if ( !v60 )
        {
          v63 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
              + (unsigned int)SystemThread_TlsOffset;
          v64 = *(_QWORD *)(v63 + 256);
          if ( !v64 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v64 = *(_QWORD *)(v63 + 256);
          }
          v65 = *(_QWORD *)(v64 + 608) == a1.QuadPart;
          for ( i = 0; !*(_DWORD *)(a1.QuadPart + 5108); ++i )
          {
            if ( i >= 10000 )
              break;
            if ( v65 )
            {
              Sleep(1u);
            }
            else
            {
              v82 = 4194400;
              v83 = 0;
              v85 = 0;
              v84 = 0;
              v86 = 0;
              SOS_Task::Sleep(1, &v82);
            }
          }
          if ( !*(_DWORD *)(a1.QuadPart + 5108) )
            *(_DWORD *)(a1.QuadPart + 4816) = 1;
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x10047dac0  mov     rax, rsp
0x10047dac3  push    rbp
0x10047dac4  push    r12
0x10047dac6  push    r13
0x10047dac8  push    r14
0x10047daca  push    r15
0x10047dacc  lea     rbp, [rax-68h]
0x10047dad0  sub     rsp, 140h
0x10047dad7  mov     [rbp+60h+var_88], 0FFFFFFFFFFFFFFFEh
0x10047dadf  mov     [rax+10h], rbx
0x10047dae3  mov     [rax+18h], rsi
0x10047dae7  mov     [rax+20h], rdi
0x10047daeb  mov     rax, cs:__security_cookie
0x10047daf2  xor     rax, rsp
0x10047daf5  mov     [rbp+60h+var_30], rax
0x10047daf9  mov     rdi, rcx
0x10047dafc  mov     qword ptr [rsp+160h+var_108], rcx
0x10047db01  mov     r8, rcx
0x10047db04  mov     edx, 0FFFFFFFFh
0x10047db09  mov     rcx, [rcx+0E70h]
0x10047db10  call    ?InsertIntoMemObjList@IMemObj@@QEAA?AW4SOS_RESULT@@KPEAVSOS_Scheduler@@@Z; IMemObj::InsertIntoMemObjList(ulong,SOS_Scheduler *)
0x10047db15  mov     r14d, eax
0x10047db18  test    eax, eax
0x10047db1a  jnz     loc_10047E611
0x10047db20  mov     r8, rdi
0x10047db23  mov     edx, 0FFFFFFFFh
0x10047db28  mov     rcx, [rdi+0E78h]
0x10047db2f  call    ?InsertIntoMemObjList@IMemObj@@QEAA?AW4SOS_RESULT@@KPEAVSOS_Scheduler@@@Z; IMemObj::InsertIntoMemObjList(ulong,SOS_Scheduler *)
0x10047db34  mov     r14d, eax
0x10047db37  test    eax, eax
0x10047db39  jnz     loc_10047E611
0x10047db3f  mov     r8, rdi
0x10047db42  mov     edx, 0FFFFFFFFh
0x10047db47  mov     rcx, [rdi+0E80h]
0x10047db4e  call    ?InsertIntoMemObjList@IMemObj@@QEAA?AW4SOS_RESULT@@KPEAVSOS_Scheduler@@@Z; IMemObj::InsertIntoMemObjList(ulong,SOS_Scheduler *)
0x10047db53  mov     r14d, eax
0x10047db56  test    eax, eax
0x10047db58  jnz     loc_10047E611
0x10047db5e  xor     r9d, r9d; lpName
0x10047db61  xor     r8d, r8d; bInitialState
0x10047db64  xor     edx, edx; bManualReset
0x10047db66  xor     ecx, ecx; lpEventAttributes
0x10047db68  call    cs:__imp_CreateEventW
0x10047db6e  mov     [rdi+0E88h], rax
0x10047db75  test    rax, rax
0x10047db78  jnz     short loc_10047DB85
0x10047db7a  mov     r14d, 80000000h
0x10047db80  jmp     loc_10047E611
0x10047db85  xor     r12d, r12d
0x10047db88  lea     r15, [r12-1]
0x10047db8d  test    byte ptr [rdi+13F0h], 8
0x10047db94  jnz     loc_10047E4DA
0x10047db9a  mov     [rsp+160h+var_130], r12; struct SOS_Task *
0x10047db9f  mov     [rsp+160h+var_138], rdi; void *
0x10047dba4  lea     rax, ?Idle@SOS_Scheduler@@KAPEAXPEAX@Z; SOS_Scheduler::Idle(void *)
0x10047dbab  mov     [rsp+160h+var_140], rax; void *(*)(void *)
0x10047dbb0  mov     r9, r15; unsigned __int64
0x10047dbb3  lea     r8, qword_100716558; struct SOS_ResourceGroup *
0x10047dbba  lea     edx, [r12+2]; unsigned int
0x10047dbbf  lea     rcx, [rbp+60h+var_80]; this
0x10047dbc3  call    ?Init@Param@SOS_Task@@QEAAXKPEAVSOS_ResourceGroup@@_KP6APEAXPEAX@Z2PEAV2@@Z; SOS_Task::Param::Init(ulong,SOS_ResourceGroup *,unsigned __int64,void * (*)(void *),void *,SOS_Task *)
0x10047dbc8  mov     r14, [rdi+1448h]
0x10047dbcf  test    r14, r14
0x10047dbd2  jz      loc_10047DE5C
0x10047dbd8  mov     r14, [r14+0F0h]
0x10047dbdf  test    r14, r14
0x10047dbe2  jz      loc_10047DE5C
0x10047dbe8  mov     rcx, r14; this
0x10047dbeb  call    ?GetPoolId@MemoryClerkInternal@@IEBAKXZ; MemoryClerkInternal::GetPoolId(void)
0x10047dbf0  mov     dword ptr [rsp+160h+var_120], eax
0x10047dbf4  mov     r14, [r14+7E0h]
0x10047dbfb  mov     esi, r12d
0x10047dbfe  mov     ebx, r12d
0x10047dc01  mov     ecx, gs:48h
0x10047dc09  mov     r12d, ecx
0x10047dc0c  mov     ecx, [r14+28h]
0x10047dc10  test    ecx, ecx
0x10047dc12  jnz     short loc_10047DC29
0x10047dc14  xor     eax, eax
0x10047dc16  lock cmpxchg [r14+28h], r12
0x10047dc1c  mov     eax, ebx
0x10047dc1e  setz    al
0x10047dc21  test    eax, eax
0x10047dc23  jnz     loc_10047DCF2
0x10047dc29  mov     eax, cs:?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10047dc2f  and     eax, 84h
0x10047dc34  xor     r15d, r15d
0x10047dc37  cmp     al, 84h
0x10047dc39  jnz     short loc_10047DC8D
0x10047dc3b  mov     rcx, gs:58h
0x10047dc44  mov     eax, cs:_tls_index
0x10047dc4a  mov     edx, cs:SystemThread_TlsOffset
0x10047dc50  add     rdx, [rcx+rax*8]
0x10047dc54  jz      short loc_10047DC66
0x10047dc56  cmp     [rdx+110h], rdx
0x10047dc5d  jnz     short loc_10047DC66
0x10047dc5f  mov     r15, [rdx+100h]
0x10047dc66  test    r15, r15
0x10047dc69  jz      short loc_10047DC8D
0x10047dc6b  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, ebx; int Base_PublicGlobals::sm_invariantTscAvailable
0x10047dc71  jz      short loc_10047DC85
0x10047dc73  lea     rcx, [rsp+160h+PerformanceCount]; lpPerformanceCount
0x10047dc78  call    cs:__imp_QueryPerformanceCounter
0x10047dc7e  mov     rbx, qword ptr [rsp+160h+PerformanceCount]
0x10047dc83  jmp     short loc_10047DC8D
0x10047dc85  mov     rbx, ds:7FFE0008h
0x10047dc8d  lea     rcx, [r14+28h]; this
0x10047dc91  test    byte ptr cs:qword_1007149B5+2, 80h
0x10047dc98  jz      short loc_10047DCA7
0x10047dc9a  mov     r8, r12
0x10047dc9d  mov     rdx, r15
0x10047dca0  call    ?SpinToAcquireOptimistic@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<34,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10047dca5  jmp     short loc_10047DCAF
0x10047dca7  mov     rdx, r12
0x10047dcaa  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10047dcaf  test    r15, r15
0x10047dcb2  jz      short loc_10047DCF2
0x10047dcb4  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, esi; int Base_PublicGlobals::sm_invariantTscAvailable
0x10047dcba  jz      short loc_10047DCCE
0x10047dcbc  lea     rcx, [rsp+160h+var_F0]; lpPerformanceCount
0x10047dcc1  call    cs:__imp_QueryPerformanceCounter
0x10047dcc7  mov     rcx, qword ptr [rsp+160h+var_F0]
0x10047dccc  jmp     short loc_10047DCD6
0x10047dcce  mov     rcx, ds:7FFE0008h
0x10047dcd6  mov     rdx, rcx
0x10047dcd9  sub     rdx, rbx
0x10047dcdc  xor     r12d, r12d
0x10047dcdf  mov     eax, r12d
0x10047dce2  cmp     rcx, rbx
0x10047dce5  cmovnb  rax, rdx
0x10047dce9  add     [r15+0C78h], rax
0x10047dcf0  jmp     short loc_10047DCF5
0x10047dcf2  xor     r12d, r12d
0x10047dcf5  mov     edx, dword ptr [rsp+160h+var_120]
0x10047dcf9  lea     rcx, [r14+rdx*8]
0x10047dcfd  cmp     [rcx+4A0h], rsi
0x10047dd04  jnz     loc_10047DDA7
0x10047dd0a  mov     ebx, [r14+498h]
0x10047dd11  and     ebx, 3Fh
0x10047dd14  add     rbx, 9
0x10047dd18  shl     rbx, 4
0x10047dd1c  add     rbx, r14
0x10047dd1f  mov     rax, [r14+20h]
0x10047dd23  movzx   ecx, byte ptr [rax+16BCh]
0x10047dd2a  test    cl, cl
0x10047dd2c  jz      short loc_10047DD33
0x10047dd2e  cmp     [rbx], rsi
0x10047dd31  jmp     short loc_10047DD3A
0x10047dd33  cmp     [r14+80h], rsi
0x10047dd3a  setnz   al
0x10047dd3d  test    al, al
0x10047dd3f  jz      loc_10047DDEC
0x10047dd45  test    cl, cl
0x10047dd47  jz      short loc_10047DD81
0x10047dd49  lea     r9, [rsp+160h+flOldProtect]; lpflOldProtect
0x10047dd4e  mov     edx, 1000h; dwSize
0x10047dd53  mov     r8d, 4; flNewProtect
0x10047dd59  mov     rcx, [rbx]; lpAddress
0x10047dd5c  call    cs:__imp_VirtualProtect
0x10047dd62  mov     rsi, [rbx]
0x10047dd65  mov     rax, [rsi]
0x10047dd68  mov     [rbx], rax
0x10047dd6b  test    rax, rax
0x10047dd6e  jnz     short loc_10047DD9A
0x10047dd70  mov     [rbx+8], rbx
0x10047dd74  dec     qword ptr [r14+8]
0x10047dd78  dec     qword ptr [r14+490h]
0x10047dd7f  jmp     short loc_10047DDEC
0x10047dd81  lea     rcx, [r14+80h]
0x10047dd88  mov     rsi, [rcx]
0x10047dd8b  mov     rax, [rsi]
0x10047dd8e  mov     [rcx], rax
0x10047dd91  test    rax, rax
0x10047dd94  jnz     short loc_10047DD9A
0x10047dd96  mov     [rcx+8], rcx
0x10047dd9a  dec     qword ptr [r14+8]
0x10047dd9e  dec     qword ptr [r14+490h]
0x10047dda5  jmp     short loc_10047DDEC
0x10047dda7  mov     rsi, [rcx+4A0h]
0x10047ddae  mov     rax, [rsi]
0x10047ddb1  mov     [rcx+4A0h], rax
0x10047ddb8  mov     [rsi], r12
0x10047ddbb  dec     qword ptr [r14+8]
0x10047ddbf  cmp     qword ptr [rcx+4A0h], 0
0x10047ddc7  jnz     short loc_10047DDEC
0x10047ddc9  mov     ecx, edx
0x10047ddcb  mov     eax, 1
0x10047ddd0  shl     rax, cl
0x10047ddd3  mov     rcx, [r14+6A0h]
0x10047ddda  test    rcx, rax
0x10047dddd  jz      short loc_10047DDEC
0x10047dddf  not     rax
0x10047dde2  and     rax, rcx
0x10047dde5  mov     [r14+6A0h], rax
0x10047ddec  cmp     cs:?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA, 0; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10047ddf3  jz      short loc_10047DE1C
0x10047ddf5  call    cs:__imp_rand
0x10047ddfb  mov     r8d, eax
0x10047ddfe  mov     eax, 66666667h
0x10047de03  imul    r8d
0x10047de06  sar     edx, 1
0x10047de08  mov     ecx, edx
0x10047de0a  shr     ecx, 1Fh
0x10047de0d  add     edx, ecx
0x10047de0f  lea     ecx, [rdx+rdx*4]
0x10047de12  cmp     r8d, ecx
0x10047de15  jnz     short loc_10047DE1C
0x10047de17  call    ?UpdateStatSnapshot@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<34,1,268435714>::UpdateStatSnapshot(void)
0x10047de1c  mov     [r14+28h], r12
0x10047de20  test    rsi, rsi
0x10047de23  jz      short loc_10047DE5C
0x10047de25  mov     rax, [rdi+1448h]
0x10047de2c  lock inc qword ptr [rax+108h]
0x10047de34  mov     qword ptr [rsp+160h+var_118], rsi
0x10047de39  lea     rcx, [rsi+8]; this
0x10047de3d  xor     r9d, r9d; struct SOSHost *
0x10047de40  mov     r8, rdi; struct SOS_Scheduler *
0x10047de43  lea     rdx, [rbp+60h+var_80]; struct SOS_Task::Param *
0x10047de47  call    ??0SOSHost_Task@@IEAA@PEAVParam@SOS_Task@@PEAVSOS_Scheduler@@PEAVSOSHost@@@Z; SOSHost_Task::SOSHost_Task(SOS_Task::Param *,SOS_Scheduler *,SOSHost *)
0x10047de4c  nop
0x10047de4d  lea     r13, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x10047de54  mov     [rsi], r13
0x10047de57  jmp     loc_10047DF15
0x10047de5c  test    cs:?SOS_Tracing_osTrace@@3KA, 1000h; ulong SOS_Tracing_osTrace
0x10047de66  jz      short loc_10047DEB0
0x10047de68  mov     edx, 1000h; dwSize
0x10047de6d  xor     ecx, ecx; lpAddress
0x10047de6f  lea     r9d, [rcx+4]; flProtect
0x10047de73  mov     r8d, 3000h; flAllocationType
0x10047de79  call    cs:__imp_VirtualAlloc
0x10047de7f  mov     rsi, rax
0x10047de82  test    rax, rax
0x10047de85  jz      loc_10047E556
0x10047de8b  mov     qword ptr [rsp+160h+var_118], rax
0x10047de90  lea     rcx, [rax+8]; this
0x10047de94  xor     r9d, r9d; struct SOSHost *
0x10047de97  mov     r8, rdi; struct SOS_Scheduler *
0x10047de9a  lea     rdx, [rbp+60h+var_80]; struct SOS_Task::Param *
0x10047de9e  call    ??0SOSHost_Task@@IEAA@PEAVParam@SOS_Task@@PEAVSOS_Scheduler@@PEAVSOSHost@@@Z; SOSHost_Task::SOSHost_Task(SOS_Task::Param *,SOS_Scheduler *,SOSHost *)
0x10047dea3  nop
0x10047dea4  lea     r13, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x10047deab  mov     [rsi], r13
0x10047deae  jmp     short loc_10047DF15
0x10047deb0  mov     dword ptr [rsp+160h+var_120], 0A00h
0x10047deb8  mov     rcx, [rdi+0E78h]
0x10047debf  mov     rax, [rcx]
0x10047dec2  mov     byte ptr [rsp+160h+var_140], 6
0x10047dec7  mov     r9d, 0A00h
0x10047decd  lea     r8, aSqlDktempSosIn_2; "Sql\\DkTemp\\sos\\include\\sos.inl"
0x10047ded4  mov     edx, 3E0h
0x10047ded9  call    qword ptr [rax+50h]
0x10047dedc  mov     rsi, rax
0x10047dedf  mov     qword ptr [rsp+160h+var_118], rax
0x10047dee4  lea     r13, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x10047deeb  test    rax, rax
0x10047deee  jz      short loc_10047DF09
0x10047def0  lea     rcx, [rax+8]; this
0x10047def4  xor     r9d, r9d; struct SOSHost *
0x10047def7  mov     r8, rdi; struct SOS_Scheduler *
0x10047defa  lea     rdx, [rbp+60h+var_80]; struct SOS_Task::Param *
0x10047defe  call    ??0SOSHost_Task@@IEAA@PEAVParam@SOS_Task@@PEAVSOS_Scheduler@@PEAVSOSHost@@@Z; SOSHost_Task::SOSHost_Task(SOS_Task::Param *,SOS_Scheduler *,SOSHost *)
0x10047df03  nop
0x10047df04  mov     [rsi], r13
0x10047df07  jmp     short loc_10047DF0C
0x10047df09  mov     rsi, r12
0x10047df0c  test    rsi, rsi
0x10047df0f  jz      loc_10047E556
0x10047df15  add     rsi, 8
0x10047df19  jz      loc_10047E556
0x10047df1f  lea     rcx, [rdi+30h]
0x10047df23  mov     rdx, rsi
0x10047df26  call    ?AppendElem@?$TList@VSOS_Scheduler@@VSOS_Task@@$0BA@UTListSLock@@@@QEAAXPEAVSOS_Task@@@Z; TList<SOS_Scheduler,SOS_Task,16,TListSLock>::AppendElem(SOS_Task *)
0x10047df2b  mov     [rsi+30h], r12d
0x10047df2f  mov     rax, [rsi+58h]
0x10047df33  mov     rcx, [rax+0D08h]
0x10047df3a  mov     eax, [rcx+0B30h]
0x10047df40  lea     rcx, [rax+rax*8]
0x10047df44  lea     rbx, [rdi+rcx*4]
0x10047df48  mov     eax, r12d
0x10047df4b  lock xadd [rbx+0A8h], eax
0x10047df53  mov     eax, r12d
0x10047df56  lock xadd [rdi+145Ch], eax
0x10047df5e  lock inc dword ptr [rdi+0DD8h]
0x10047df65  lock inc dword ptr [rdi+0DDCh]
0x10047df6c  lea     r9, [rsp+160h+var_E8]
0x10047df71  xor     r8d, r8d
0x10047df74  lea     edx, [r8+2]
0x10047df78  lea     rcx, [rdi+12D0h]
0x10047df7f  call    ?AcquireWorker@WorkDispatcher@@AEAA?AW4SOS_RESULT@@KHPEAPEAVWorkerIdleElem@1@@Z; WorkDispatcher::AcquireWorker(ulong,int,WorkDispatcher::WorkerIdleElem * *)
0x10047df84  mov     r14d, eax
0x10047df87  test    eax, eax
0x10047df89  jnz     short loc_10047DFA5
0x10047df8b  lea     r9, [rbp+60h+var_E0]; struct SOS_Task **
0x10047df8f  mov     r8, [rsp+160h+var_E8]; struct WorkDispatcher::WorkerIdleElem *
0x10047df94  mov     rdx, rsi; struct SOS_Task *
0x10047df97  lea     rcx, [rdi+12D0h]; this
0x10047df9e  call    ?EnqueueTask@WorkDispatcher@@AEAAXPEAVSOS_Task@@PEAVWorkerIdleElem@1@PEAPEAV2@@Z; WorkDispatcher::EnqueueTask(SOS_Task *,WorkDispatcher::WorkerIdleElem *,SOS_Task * *)
0x10047dfa3  jmp     short loc_10047DFC7
0x10047dfa5  mov     [rbp+60h+var_E0], r12
0x10047dfa9  mov     ecx, [rsi+30h]
  ... truncated ...
```
