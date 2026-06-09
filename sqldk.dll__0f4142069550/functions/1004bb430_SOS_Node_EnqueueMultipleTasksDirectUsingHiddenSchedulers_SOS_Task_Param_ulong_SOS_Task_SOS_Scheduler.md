# SOS_Node::EnqueueMultipleTasksDirectUsingHiddenSchedulers(SOS_Task::Param *,ulong,SOS_Task * *,SOS_Scheduler * *)

- ea: `0x1004bb430`
- end: `0x1004bbf01`
- name: `?EnqueueMultipleTasksDirectUsingHiddenSchedulers@SOS_Node@@QEAA?AW4SOS_RESULT@@PEAVParam@SOS_Task@@KPEAPEAV4@PEAPEAVSOS_Scheduler@@@Z`
- size: `2769`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1005dc930`

## callees

- `0x100403070`
- `0x100404860`
- `0x100406340`
- `0x100406510`
- `0x1004067b0`
- `0x10040a8f0`
- `0x1004104a0`
- `0x1004106b0`
- `0x100410810`
- `0x1004371b0`
- `0x1004718a0`
- `0x100475600`
- `0x100475810`
- `0x100475a50`
- `0x100475b60`
- `0x1004795c0`
- `0x1004899d0`
- `0x1004bb430`
- `0x1004bd140`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x1004bb71d`
- `KERNEL32!VirtualProtect` at `0x1004bbd11`
- `KERNEL32!VirtualProtect` at `0x1004bb71d`
- `KERNEL32!VirtualProtect` at `0x1004bbd11`
- `KERNEL32!QueryPerformanceCounter` at `0x1004bb635`
- `KERNEL32!QueryPerformanceCounter` at `0x1004bb67f`
- `KERNEL32!QueryPerformanceCounter` at `0x1004bba61`
- `KERNEL32!QueryPerformanceCounter` at `0x1004bbaab`
- `KERNEL32!QueryPerformanceCounter` at `0x1004bbc48`
- `KERNEL32!QueryPerformanceCounter` at `0x1004bbc90`
- `KERNEL32!QueryPerformanceCounter` at `0x1004bb635`
- `KERNEL32!QueryPerformanceCounter` at `0x1004bb67f`
- `KERNEL32!QueryPerformanceCounter` at `0x1004bba61`
- `KERNEL32!QueryPerformanceCounter` at `0x1004bbaab`
- `KERNEL32!QueryPerformanceCounter` at `0x1004bbc48`
- `KERNEL32!QueryPerformanceCounter` at `0x1004bbc90`
- `KERNEL32!VirtualAlloc` at `0x1004bb84e`
- `KERNEL32!VirtualAlloc` at `0x1004bb84e`
- `KERNEL32!VirtualFree` at `0x1004bbe63`
- `KERNEL32!VirtualFree` at `0x1004bbe63`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004bb7b7`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004bbdd5`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004bbe0e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004bb7b7`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004bbdd5`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004bbe0e`

## string_xrefs

- `0x1004bb899`: `Sql\DkTemp\sos\include\sos.inl`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall SOS_Node::EnqueueMultipleTasksDirectUsingHiddenSchedulers(
        __int64 a1,
        LARGE_INTEGER a2,
        unsigned int a3,
        struct SOS_Task **a4,
        SOS_Scheduler **a5)
{
  struct SOS_Task **v5; // r14
  unsigned int v6; // esi
  LARGE_INTEGER v7; // r15
  SOS_Scheduler **v9; // r12
  unsigned int v10; // r13d
  unsigned __int16 v11; // di
  unsigned __int16 v12; // ax
  unsigned __int64 v13; // rdi
  struct SOS_Scheduler *HiddenScheduler; // rax
  _QWORD *v15; // rdx
  signed __int64 v16; // rdx
  unsigned int v17; // eax
  struct SOS_Task::Param *v18; // rsi
  __int64 v19; // r13
  _QWORD *v20; // rdi
  __int64 v21; // rax
  __int64 v22; // rsi
  __int64 PoolId; // r12
  __int64 v24; // rsi
  SpinlockBase *v25; // r9
  LARGE_INTEGER v26; // rbx
  signed __int64 UniqueThread_low; // r15
  __int64 v28; // r14
  __int64 v29; // rdx
  LARGE_INTEGER v30; // rcx
  LONGLONG v31; // rax
  __int64 v32; // rcx
  LPVOID *v33; // rbx
  char v34; // cl
  bool v35; // zf
  _QWORD *v36; // rax
  __int64 v37; // rax
  __int64 v38; // rcx
  int v39; // r8d
  struct SOS_Task *v40; // rbx
  _QWORD *v41; // rax
  __int64 v42; // rax
  unsigned int v44; // r13d
  __int64 v45; // rax
  struct SOS_Task *v46; // rdi
  __int64 v47; // rcx
  LARGE_INTEGER v48; // rbx
  signed __int64 v49; // r14
  __int64 v50; // rsi
  __int64 v51; // rdx
  LARGE_INTEGER v52; // rax
  LONGLONG v53; // rax
  _QWORD *v54; // rcx
  __int64 v55; // rax
  __int64 v56; // rax
  _QWORD *v57; // rcx
  __int64 v58; // rax
  __int64 v59; // rbx
  _QWORD *v60; // rcx
  _QWORD *v61; // r14
  __int64 v62; // rdi
  LARGE_INTEGER v63; // rbx
  signed __int64 v64; // r15
  __int64 v65; // rsi
  __int64 v66; // rdx
  SpinlockBase *v67; // rcx
  LARGE_INTEGER v68; // rax
  LONGLONG v69; // rax
  _QWORD *v70; // rcx
  unsigned __int64 v71; // r8
  SOS_ObjectStore *v72; // rcx
  unsigned int PoolIdForObject; // eax
  __int64 v74; // r9
  __int64 v75; // r10
  _QWORD *v76; // r8
  __int64 v77; // rax
  __int64 v78; // rcx
  int v79; // r8d
  int v80; // r8d
  char *v81; // rcx
  __int64 v82; // rbx
  int v83; // [rsp+20h] [rbp-E0h]
  unsigned int v84; // [rsp+30h] [rbp-D0h]
  unsigned int v85; // [rsp+34h] [rbp-CCh]
  struct SOS_Task **v87; // [rsp+40h] [rbp-C0h]
  __int64 v88; // [rsp+40h] [rbp-C0h]
  struct SOS_Task::Param *v89; // [rsp+48h] [rbp-B8h]
  LARGE_INTEGER v91; // [rsp+68h] [rbp-98h] BYREF
  SpinlockBase *v92; // [rsp+70h] [rbp-90h] BYREF
  int v93; // [rsp+78h] [rbp-88h]
  DWORD v94[2]; // [rsp+80h] [rbp-80h] BYREF
  SOS_Scheduler **v95; // [rsp+88h] [rbp-78h]
  struct SOS_Task **v96; // [rsp+90h] [rbp-70h]
  __int64 v97; // [rsp+98h] [rbp-68h]
  DWORD flOldProtect; // [rsp+A0h] [rbp-60h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+A8h] [rbp-58h] BYREF
  LARGE_INTEGER v100; // [rsp+B0h] [rbp-50h] BYREF
  LARGE_INTEGER v101; // [rsp+B8h] [rbp-48h] BYREF
  LARGE_INTEGER v102; // [rsp+C0h] [rbp-40h] BYREF
  LARGE_INTEGER v103; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v104; // [rsp+D0h] [rbp-30h]
  _QWORD *v105; // [rsp+D8h] [rbp-28h]
  _QWORD *v106; // [rsp+E0h] [rbp-20h]
  __int64 v107; // [rsp+E8h] [rbp-18h]
  struct SOS_Task *v108; // [rsp+F0h] [rbp-10h]
  _QWORD v109[16]; // [rsp+100h] [rbp+0h] BYREF

  v107 = -2;
  v5 = a4;
  v6 = a3;
  v7 = a2;
  v91 = a2;
  v9 = a5;
  v95 = a5;
  v10 = 0;
  v11 = 0;
  if ( (*(_BYTE *)(a1 + 1568) & 4) == 0 )
    v11 = *(_WORD *)(a1 + 160);
  SystemAffinity::SafeCopy(&SOS_PublicGlobals::sm_AffinityMask, v109);
  v12 = 0;
  if ( v11 != 64 )
    v12 = v11;
  v13 = v109[*((unsigned __int16 *)&SOS_PublicGlobals::sm_SOSNodeInfo + 20 * v11 + 8)]
      & (unsigned __int64)*(&SOS_PublicGlobals::sm_SOSNodeInfo + 5 * v11 + 1)
      & (unsigned __int64)*(&SOS_PublicGlobals::sm_SOSNodeInfo + 5 * v12 + 1);
  if ( !v6 )
  {
LABEL_64:
    SOS_Node::StartMultipleTasksInternal(v5, v6);
    return 0;
  }
  do
  {
    HiddenScheduler = SOS_Node::CreateHiddenScheduler((SOS_Node *)a1, v13, 1, SOS_PublicGlobals::sm_Priority, 1);
    a5[v10] = HiddenScheduler;
    if ( !HiddenScheduler )
      goto LABEL_161;
    ++v10;
  }
  while ( v10 < v6 );
  v87 = v5;
  v16 = (char *)a5 - (char *)v5;
  *(_QWORD *)v94 = (char *)a5 - (char *)v5;
  v17 = 0;
  v84 = 0;
  v85 = v10;
  while ( 1 )
  {
    v18 = (struct SOS_Task::Param *)(v7.QuadPart + 72LL * v17);
    v89 = v18;
    v19 = *(__int64 *)((char *)v5 + v16);
    v96 = (struct SOS_Task **)v19;
    v20 = 0;
    v21 = *(_QWORD *)(v19 + 5192);
    if ( !v21 )
      goto LABEL_52;
    v22 = *(_QWORD *)(v21 + 240);
    if ( v22 )
    {
      PoolId = MemoryClerkInternal::GetPoolId(*(MemoryClerkInternal **)(v21 + 240));
      v24 = *(_QWORD *)(v22 + 2016);
      v25 = (SpinlockBase *)(v24 + 40);
      v26.QuadPart = 0;
      UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( *(_DWORD *)(v24 + 40) || _InterlockedCompareExchange64((volatile signed __int64 *)v25, UniqueThread_low, 0) )
      {
        v28 = 0;
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v29 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
              + (unsigned int)SystemThread_TlsOffset;
          if ( v29 && *(_QWORD *)(v29 + 272) == v29 )
            v28 = *(_QWORD *)(v29 + 256);
          if ( v28 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&PerformanceCount);
              v26 = PerformanceCount;
              v25 = (SpinlockBase *)(v24 + 40);
            }
            else
            {
              v26.QuadPart = MEMORY[0x7FFE0008];
            }
          }
        }
        if ( (qword_1007149B5 & 0x800000) == 0 )
          Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v25);
        else
          Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v25);
        if ( v28 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v100);
            v30 = v100;
          }
          else
          {
            v30.QuadPart = MEMORY[0x7FFE0008];
          }
          v31 = 0;
          if ( v30.QuadPart >= (unsigned __int64)v26.QuadPart )
            v31 = v30.QuadPart - v26.QuadPart;
          *(_QWORD *)(v28 + 3192) += v31;
          v5 = v87;
        }
        else
        {
          v5 = v87;
        }
      }
      v32 = v24 + 8 * PoolId;
      if ( *(_QWORD *)(v32 + 1184) )
      {
        v20 = *(_QWORD **)(v32 + 1184);
        *(_QWORD *)(v32 + 1184) = *v20;
        *v20 = 0;
        --*(_QWORD *)(v24 + 8);
        if ( !*(_QWORD *)(v32 + 1184) )
        {
          v38 = *(_QWORD *)(v24 + 1696);
          if ( (v38 & (1LL << PoolId)) != 0 )
            *(_QWORD *)(v24 + 1696) = v38 & ~(1LL << PoolId);
        }
      }
      else
      {
        v33 = (LPVOID *)(v24 + 16 * ((*(_DWORD *)(v24 + 1176) & 0x3F) + 9LL));
        v34 = *(_BYTE *)(*(_QWORD *)(v24 + 32) + 5820LL);
        if ( v34 )
          v35 = *v33 == 0;
        else
          v35 = *(_QWORD *)(v24 + 128) == 0;
        if ( !v35 )
        {
          if ( v34 )
          {
            VirtualProtect(*v33, 0x1000u, 4u, &flOldProtect);
            v20 = *v33;
            v36 = *(_QWORD **)*v33;
            *v33 = v36;
            if ( !v36 )
            {
              v33[1] = v33;
              --*(_QWORD *)(v24 + 8);
              --*(_QWORD *)(v24 + 1168);
              goto LABEL_46;
            }
          }
          else
          {
            v20 = *(_QWORD **)(v24 + 128);
            v37 = *v20;
            *(_QWORD *)(v24 + 128) = *v20;
            if ( !v37 )
              *(_QWORD *)(v24 + 136) = v24 + 128;
          }
          --*(_QWORD *)(v24 + 8);
          --*(_QWORD *)(v24 + 1168);
        }
      }
LABEL_46:
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v39 = rand();
        if ( v39 == 5 * (v39 / 5) )
          Spinlock<34,1,268435714>::UpdateStatSnapshot();
      }
      *(_QWORD *)(v24 + 40) = 0;
      if ( v20 )
      {
        _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v19 + 5192) + 264LL));
        v105 = v20;
        SOSHost_Task::SOSHost_Task((SOSHost_Task *)(v20 + 1), v89, (struct SOS_Scheduler *)v19, 0);
        *v20 = &ISOSHost_TaskImpl::`vftable';
        goto LABEL_59;
      }
    }
    v18 = v89;
LABEL_52:
    v40 = 0;
    if ( (SOS_Tracing_osTrace & 0x1000) == 0 )
      break;
    v41 = VirtualAlloc(0, 0x1000u, 0x3000u, 4u);
    v20 = v41;
    if ( !v41 )
      goto LABEL_61;
    v106 = v41;
    SOSHost_Task::SOSHost_Task((SOSHost_Task *)(v41 + 1), v18, (struct SOS_Scheduler *)v19, 0);
    *v20 = &ISOSHost_TaskImpl::`vftable';
LABEL_59:
    v40 = (struct SOS_Task *)(v20 + 1);
    if ( v20 == (_QWORD *)-8LL )
      goto LABEL_61;
    TList<SOS_Scheduler,SOS_Task,16,TListSLock>::AppendElem(v19 + 48, v20 + 1);
    *v5 = v40;
LABEL_62:
    v17 = v84 + 1;
    v84 = v17;
    v87 = ++v5;
    v6 = a3;
    v16 = *(_QWORD *)v94;
    v7 = v91;
    if ( v17 >= a3 )
    {
      v5 = a4;
      goto LABEL_64;
    }
  }
  LOBYTE(v83) = 6;
  v42 = (*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64, int))(**(_QWORD **)(v19 + 3704) + 80LL))(
          *(_QWORD *)(v19 + 3704),
          992,
          "Sql\\DkTemp\\sos\\include\\sos.inl",
          2560,
          v83);
  v20 = (_QWORD *)v42;
  v97 = v42;
  if ( v42 )
  {
    SOSHost_Task::SOSHost_Task((SOSHost_Task *)(v42 + 8), v18, (struct SOS_Scheduler *)v19, 0);
    *v20 = &ISOSHost_TaskImpl::`vftable';
  }
  else
  {
    v20 = 0;
  }
  if ( v20 )
    goto LABEL_59;
LABEL_61:
  *v5 = v40;
  if ( v40 )
    goto LABEL_62;
  v44 = 0;
  if ( v84 )
  {
    v45 = 0;
    v88 = 0;
    do
    {
      v96 = &a4[v45];
      v46 = *v96;
      v47 = (__int64)*v96 + 16;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)*v96 + 10, 0xFFFFFFFF) == 1 )
      {
        if ( *(_QWORD *)(v47 + 8) )
        {
          TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(v47);
        }
        else
        {
          if ( *((_DWORD *)v46 + 46) == 2 )
          {
            v92 = (SpinlockBase *)(*((_QWORD *)v46 + 20) + 4952LL);
            v93 = 0;
            v48.QuadPart = 0;
            v49 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
            if ( *(_DWORD *)v92 || _InterlockedCompareExchange64((volatile signed __int64 *)v92, v49, 0) )
            {
              v50 = 0;
              if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
              {
                v51 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                    + (unsigned int)SystemThread_TlsOffset;
                if ( v51 && *(_QWORD *)(v51 + 272) == v51 )
                  v50 = *(_QWORD *)(v51 + 256);
                if ( v50 )
                {
                  if ( Base_PublicGlobals::sm_invariantTscAvailable )
                  {
                    QueryPerformanceCounter(&v91);
                    v48 = v91;
                  }
                  else
                  {
                    v48.QuadPart = MEMORY[0x7FFE0008];
                  }
                }
              }
              if ( (qword_1007149B5 & 0x800000) == 0 )
                Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v92);
              else
                Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v92);
              if ( v50 )
              {
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&v101);
                  v52 = v101;
                }
                else
                {
                  v52.QuadPart = MEMORY[0x7FFE0008];
                }
                if ( v52.QuadPart < (unsigned __int64)v48.QuadPart )
                  v53 = 0;
                else
                  v53 = v52.QuadPart - v48.QuadPart;
                *(_QWORD *)(v50 + 3192) += v53;
              }
            }
            v93 = 1;
            v54 = (_QWORD *)*((_QWORD *)v46 + 1);
            v55 = *(_QWORD *)v46;
            *(_QWORD *)(v55 + 8) = v54;
            *v54 = v55;
            *((_QWORD *)v46 + 1) = 0;
            *(_QWORD *)v46 = 0;
            SpinlockHolder<11,2,268435714>::~SpinlockHolder<11,2,268435714>(&v92);
          }
          v15 = (_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                         + (unsigned int)SystemThread_TlsOffset);
          if ( v15 && (_QWORD *)v15[34] == v15 && (v56 = v15[32]) != 0 && *(struct SOS_Task **)(v56 + 528) == v46 )
          {
            v57 = (_QWORD *)((char *)v46 - 8);
            if ( !v46 )
              v57 = 0;
            *v57 = &ISOSHost_TaskImpl::`vftable';
            v106 = v57 + 1;
            SOS_Task::~SOS_Task((SOS_Task *)(v57 + 1));
          }
          else
          {
            v58 = *((_QWORD *)v46 + 21);
            if ( !v58
              || (v59 = *(_QWORD *)(v58 + 240)) == 0
              || (*(_BYTE *)(v58 + 1568) & 2) != 0
              || SOS_OS_TaskStoreDisabled )
            {
              if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
              {
                v81 = (char *)v46 - 8;
                if ( !v46 )
                  v81 = 0;
                VirtualFree(v81, 0, 0x8000u);
              }
              else if ( v46 )
              {
                v104 = (__int64)v46 - 8;
                if ( v46 != (struct SOS_Task *)8 )
                {
                  *((_QWORD *)v46 - 1) = &ISOSHost_TaskImpl::`vftable';
                  v108 = v46;
                  SOS_Task::~SOS_Task(v46);
                  operator delete((char *)v46 - 8, 0x3E0u);
                }
              }
            }
            else
            {
              v60 = (_QWORD *)((char *)v46 - 8);
              if ( !v46 )
                v60 = 0;
              *v60 = &ISOSHost_TaskImpl::`vftable';
              v105 = v60 + 1;
              SOS_Task::~SOS_Task((SOS_Task *)(v60 + 1));
              v61 = (_QWORD *)((char *)v46 - 8);
              if ( !v46 )
                v61 = 0;
              v62 = *(_QWORD *)(v59 + 2016);
              v63.QuadPart = 0;
              v64 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
              if ( *(_DWORD *)(v62 + 40) || _InterlockedCompareExchange64((volatile signed __int64 *)(v62 + 40), v64, 0) )
              {
                v65 = 0;
                if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
                {
                  v66 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                      + (unsigned int)SystemThread_TlsOffset;
                  if ( v66 && *(_QWORD *)(v66 + 272) == v66 )
                    v65 = *(_QWORD *)(v66 + 256);
                  if ( v65 )
                  {
                    if ( Base_PublicGlobals::sm_invariantTscAvailable )
                    {
                      QueryPerformanceCounter(&v102);
                      v63 = v102;
                    }
                    else
                    {
                      v63.QuadPart = MEMORY[0x7FFE0008];
                    }
                  }
                }
                v67 = (SpinlockBase *)(v62 + 40);
                if ( (qword_1007149B5 & 0x800000) == 0 )
                  Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v67);
                else
                  Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v67);
                if ( v65 )
                {
                  if ( Base_PublicGlobals::sm_invariantTscAvailable )
                  {
                    QueryPerformanceCounter(&v103);
                    v68 = v103;
                  }
                  else
                  {
                    v68.QuadPart = MEMORY[0x7FFE0008];
                  }
                  if ( v68.QuadPart < (unsigned __int64)v63.QuadPart )
                    v69 = 0;
                  else
                    v69 = v68.QuadPart - v63.QuadPart;
                  *(_QWORD *)(v65 + 3192) += v69;
                }
              }
              if ( *(_QWORD *)(v62 + 8) >= *(_QWORD *)v62 )
              {
                if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                {
                  v80 = rand();
                  if ( v80 == 5 * (v80 / 5) )
                    Spinlock<34,1,268435714>::UpdateStatSnapshot();
                }
                *(_QWORD *)(v62 + 40) = 0;
                (*(void (__fastcall **)(_QWORD *))(v62 + 48))(v61);
              }
              else
              {
                if ( *(_BYTE *)(*(_QWORD *)(v62 + 32) + 5820LL) )
                {
                  v70 = (_QWORD *)(v62 + 16 * ((*(_DWORD *)(v62 + 1176) & 0x3F) + 9LL));
                  *v61 = *v70;
                  if ( !*v70 )
                    v70[1] = v61;
                  *v70 = v61;
                  ++*(_QWORD *)(v62 + 1176);
                  VirtualProtect(v61, 0x1000u, 1u, v94);
                }
                else
                {
                  *v61 = *(_QWORD *)(v62 + 128);
                  if ( !*(_QWORD *)(v62 + 128) )
                    *(_QWORD *)(v62 + 136) = v61;
                  *(_QWORD *)(v62 + 128) = v61;
                }
                v71 = *(_QWORD *)(v62 + 1168) + 1LL;
                ++*(_QWORD *)(v62 + 8);
                v72 = *(SOS_ObjectStore **)(v62 + 32);
                if ( !*((_BYTE *)v72 + 5820) && v71 >= 0x20 )
                {
                  PoolIdForObject = SOS_ObjectStore::GetPoolIdForObject(v72, (struct SList *)v61);
                  v15 = (_QWORD *)(v62 + 128);
                  v74 = v62 + 8LL * PoolIdForObject;
                  v75 = *(_QWORD *)(v62 + 128);
                  v76 = *(_QWORD **)(v62 + 136);
                  if ( v76 != (_QWORD *)(v62 + 128) && v76 )
                  {
                    *v76 = *(_QWORD *)(v74 + 1184);
                    *(_QWORD *)(v74 + 1184) = v75;
                  }
                  *v15 = 0;
                  *(_QWORD *)(v62 + 136) = v62 + 128;
                  v71 = 0;
                  v77 = 1LL << PoolIdForObject;
                  v78 = *(_QWORD *)(v62 + 1696);
                  if ( (v77 & v78) == 0 )
                    *(_QWORD *)(v62 + 1696) = v78 | v77;
                }
                *(_QWORD *)(v62 + 1168) = v71;
                if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                {
                  v79 = rand();
                  LODWORD(v15) = v79 / 5;
                  if ( v79 == 5 * (v79 / 5) )
                    Spinlock<34,1,268435714>::UpdateStatSnapshot();
                }
                *(_QWORD *)(v62 + 40) = 0;
              }
            }
          }
        }
      }
      *v96 = 0;
      ++v44;
      v45 = ++v88;
    }
    while ( v44 < v84 );
  }
  v10 = v85;
  v9 = v95;
LABEL_161:
  if ( v10 )
  {
    v82 = v10;
    do
    {
      SOS_Scheduler::SelfOfflineIfPossible(*v9, (bool)v15);
      *v9++ = 0;
      --v82;
    }
    while ( v82 );
  }
  return 3221225472LL;
}

```

## disassembly

```asm
0x1004bb430  push    rbp
0x1004bb432  push    rsi
0x1004bb433  push    rdi
0x1004bb434  push    r12
0x1004bb436  push    r13
0x1004bb438  push    r14
0x1004bb43a  push    r15
0x1004bb43c  lea     rbp, [rsp-90h]
0x1004bb444  sub     rsp, 190h
0x1004bb44b  mov     [rbp+0C0h+var_D8], 0FFFFFFFFFFFFFFFEh
0x1004bb453  mov     [rsp+1C0h+arg_8], rbx
0x1004bb45b  mov     rax, cs:__security_cookie
0x1004bb462  xor     rax, rsp
0x1004bb465  mov     [rbp+0C0h+var_40], rax
0x1004bb46c  mov     r14, r9
0x1004bb46f  mov     [rsp+1C0h+var_168], r9
0x1004bb474  mov     esi, r8d
0x1004bb477  mov     [rsp+1C0h+var_188], r8d
0x1004bb47c  mov     r15, rdx
0x1004bb47f  mov     qword ptr [rsp+1C0h+var_158], rdx
0x1004bb484  mov     rbx, rcx
0x1004bb487  mov     r12, [rbp+0C0h+arg_20]
0x1004bb48e  mov     [rbp+0C0h+var_138], r12
0x1004bb492  xor     r13d, r13d
0x1004bb495  test    byte ptr [rcx+620h], 4
0x1004bb49c  movzx   edi, r13w
0x1004bb4a0  jnz     short loc_1004BB4A9
0x1004bb4a2  movzx   edi, word ptr [rcx+0A0h]
0x1004bb4a9  lea     rdx, [rbp+0C0h+var_C0]
0x1004bb4ad  lea     rcx, ?sm_AffinityMask@SOS_PublicGlobals@@2VSystemAffinity@@A; SystemAffinity SOS_PublicGlobals::sm_AffinityMask
0x1004bb4b4  call    ?SafeCopy@SystemAffinity@@QEBA?AV1@XZ; SystemAffinity::SafeCopy(void)
0x1004bb4b9  movzx   eax, di
0x1004bb4bc  lea     rcx, [rax+rax*4]
0x1004bb4c0  lea     r8, ?sm_SOSNodeInfo@SOS_PublicGlobals@@2PAVSOS_NodeInfo@@A; SOS_NodeInfo near * SOS_PublicGlobals::sm_SOSNodeInfo
0x1004bb4c7  movzx   eax, word ptr [r8+rcx*8+10h]
0x1004bb4cd  mov     rdx, [r8+rcx*8+8]
0x1004bb4d2  and     rdx, [rbp+rax*8+0C0h+var_C0]
0x1004bb4d7  mov     ecx, 40h ; '@'
0x1004bb4dc  mov     eax, r13d
0x1004bb4df  cmp     cx, di
0x1004bb4e2  cmovnz  ax, di
0x1004bb4e6  movzx   eax, ax
0x1004bb4e9  lea     rcx, [rax+rax*4]
0x1004bb4ed  mov     rdi, [r8+rcx*8+8]
0x1004bb4f2  and     rdi, rdx
0x1004bb4f5  test    esi, esi
0x1004bb4f7  jz      loc_1004BB923
0x1004bb4fd  nop     dword ptr [rax]
0x1004bb500  mov     byte ptr [rsp+1C0h+var_1A0], 1; bool
0x1004bb505  mov     r9d, cs:?sm_Priority@SOS_PublicGlobals@@2HA; int
0x1004bb50c  mov     r8d, 1; int
0x1004bb512  mov     rdx, rdi; unsigned __int64
0x1004bb515  mov     rcx, rbx; this
0x1004bb518  call    ?CreateHiddenScheduler@SOS_Node@@QEAAPEAVSOS_Scheduler@@_KJH_N@Z; SOS_Node::CreateHiddenScheduler(unsigned __int64,long,int,bool)
0x1004bb51d  mov     ecx, r13d
0x1004bb520  mov     [r12+rcx*8], rax
0x1004bb524  test    rax, rax
0x1004bb527  jz      loc_1004BBEF6
0x1004bb52d  inc     r13d
0x1004bb530  cmp     r13d, esi
0x1004bb533  jb      short loc_1004BB500
0x1004bb535  mov     [rsp+1C0h+var_180], r14
0x1004bb53a  mov     rdx, r12
0x1004bb53d  sub     rdx, r14
0x1004bb540  mov     qword ptr [rbp+0C0h+var_140], rdx
0x1004bb544  xor     eax, eax
0x1004bb546  mov     [rsp+1C0h+var_190], eax
0x1004bb54a  mov     [rsp+1C0h+var_18C], r13d
0x1004bb54f  lea     r12, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x1004bb556  nop     word ptr [rax+rax+00000000h]
0x1004bb560  mov     eax, eax
0x1004bb562  lea     rcx, [rax+rax*8]
0x1004bb566  lea     rsi, [r15+rcx*8]
0x1004bb56a  mov     [rsp+1C0h+var_178], rsi
0x1004bb56f  mov     r13, [rdx+r14]
0x1004bb573  mov     [rbp+0C0h+var_130], r13
0x1004bb577  xor     r15d, r15d
0x1004bb57a  mov     edi, r15d
0x1004bb57d  mov     rax, [r13+1448h]
0x1004bb584  test    rax, rax
0x1004bb587  jz      loc_1004BB808
0x1004bb58d  mov     rsi, [rax+0F0h]
0x1004bb594  test    rsi, rsi
0x1004bb597  jz      loc_1004BB803
0x1004bb59d  mov     rcx, rsi; this
0x1004bb5a0  call    ?GetPoolId@MemoryClerkInternal@@IEBAKXZ; MemoryClerkInternal::GetPoolId(void)
0x1004bb5a5  mov     r12d, eax
0x1004bb5a8  mov     rsi, [rsi+7E0h]
0x1004bb5af  lea     r9, [rsi+28h]
0x1004bb5b3  mov     [rsp+1C0h+var_160], r9
0x1004bb5b8  mov     ebx, r15d
0x1004bb5bb  mov     ecx, gs:48h
0x1004bb5c3  mov     r15d, ecx
0x1004bb5c6  mov     ecx, [r9]
0x1004bb5c9  test    ecx, ecx
0x1004bb5cb  jnz     short loc_1004BB5E5
0x1004bb5cd  xor     eax, eax
0x1004bb5cf  lock cmpxchg [r9], r15
0x1004bb5d4  mov     ecx, ebx
0x1004bb5d6  mov     eax, ecx
0x1004bb5d8  setz    al
0x1004bb5db  test    eax, eax
0x1004bb5dd  jnz     loc_1004BB6B9
0x1004bb5e3  jmp     short loc_1004BB5E7
0x1004bb5e5  xor     ecx, ecx
0x1004bb5e7  mov     eax, cs:?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004bb5ed  and     eax, 84h
0x1004bb5f2  mov     r14, rcx
0x1004bb5f5  cmp     al, 84h
0x1004bb5f7  jnz     short loc_1004BB64D
0x1004bb5f9  mov     rcx, gs:58h
0x1004bb602  mov     eax, cs:_tls_index
0x1004bb608  mov     edx, cs:SystemThread_TlsOffset
0x1004bb60e  add     rdx, [rcx+rax*8]
0x1004bb612  jz      short loc_1004BB624
0x1004bb614  cmp     [rdx+110h], rdx
0x1004bb61b  jnz     short loc_1004BB624
0x1004bb61d  mov     r14, [rdx+100h]
0x1004bb624  test    r14, r14
0x1004bb627  jz      short loc_1004BB64D
0x1004bb629  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, ebx; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004bb62f  jz      short loc_1004BB645
0x1004bb631  lea     rcx, [rbp+0C0h+PerformanceCount]; lpPerformanceCount
0x1004bb635  call    cs:__imp_QueryPerformanceCounter
0x1004bb63b  mov     rbx, qword ptr [rbp+0C0h+PerformanceCount]
0x1004bb63f  lea     r9, [rsi+28h]
0x1004bb643  jmp     short loc_1004BB64D
0x1004bb645  mov     rbx, ds:7FFE0008h
0x1004bb64d  mov     rcx, r9; this
0x1004bb650  test    byte ptr cs:qword_1007149B5+2, 80h
0x1004bb657  jz      short loc_1004BB666
0x1004bb659  mov     r8, r15
0x1004bb65c  mov     rdx, r14
0x1004bb65f  call    ?SpinToAcquireOptimistic@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<34,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x1004bb664  jmp     short loc_1004BB66E
0x1004bb666  mov     rdx, r15
0x1004bb669  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x1004bb66e  test    r14, r14
0x1004bb671  jz      short loc_1004BB6B4
0x1004bb673  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, edi; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004bb679  jz      short loc_1004BB68B
0x1004bb67b  lea     rcx, [rbp+0C0h+var_110]; lpPerformanceCount
0x1004bb67f  call    cs:__imp_QueryPerformanceCounter
0x1004bb685  mov     rcx, qword ptr [rbp+0C0h+var_110]
0x1004bb689  jmp     short loc_1004BB693
0x1004bb68b  mov     rcx, ds:7FFE0008h
0x1004bb693  mov     rdx, rcx
0x1004bb696  sub     rdx, rbx
0x1004bb699  xor     r15d, r15d
0x1004bb69c  mov     eax, r15d
0x1004bb69f  cmp     rcx, rbx
0x1004bb6a2  cmovnb  rax, rdx
0x1004bb6a6  add     [r14+0C78h], rax
0x1004bb6ad  mov     r14, [rsp+1C0h+var_180]
0x1004bb6b2  jmp     short loc_1004BB6BC
0x1004bb6b4  mov     r14, [rsp+1C0h+var_180]
0x1004bb6b9  xor     r15d, r15d
0x1004bb6bc  lea     rcx, [rsi+r12*8]
0x1004bb6c0  cmp     [rcx+4A0h], rdi
0x1004bb6c7  jnz     loc_1004BB768
0x1004bb6cd  mov     ebx, [rsi+498h]
0x1004bb6d3  and     ebx, 3Fh
0x1004bb6d6  add     rbx, 9
0x1004bb6da  shl     rbx, 4
0x1004bb6de  add     rbx, rsi
0x1004bb6e1  mov     rax, [rsi+20h]
0x1004bb6e5  movzx   ecx, byte ptr [rax+16BCh]
0x1004bb6ec  test    cl, cl
0x1004bb6ee  jz      short loc_1004BB6F5
0x1004bb6f0  cmp     [rbx], rdi
0x1004bb6f3  jmp     short loc_1004BB6FC
0x1004bb6f5  cmp     [rsi+80h], rdi
0x1004bb6fc  setnz   al
0x1004bb6ff  test    al, al
0x1004bb701  jz      loc_1004BB7AE
0x1004bb707  test    cl, cl
0x1004bb709  jz      short loc_1004BB742
0x1004bb70b  lea     r9, [rbp+0C0h+flOldProtect]; lpflOldProtect
0x1004bb70f  mov     edx, 1000h; dwSize
0x1004bb714  mov     r8d, 4; flNewProtect
0x1004bb71a  mov     rcx, [rbx]; lpAddress
0x1004bb71d  call    cs:__imp_VirtualProtect
0x1004bb723  mov     rdi, [rbx]
0x1004bb726  mov     rax, [rdi]
0x1004bb729  mov     [rbx], rax
0x1004bb72c  test    rax, rax
0x1004bb72f  jnz     short loc_1004BB75B
0x1004bb731  mov     [rbx+8], rbx
0x1004bb735  dec     qword ptr [rsi+8]
0x1004bb739  dec     qword ptr [rsi+490h]
0x1004bb740  jmp     short loc_1004BB7AE
0x1004bb742  lea     rcx, [rsi+80h]
0x1004bb749  mov     rdi, [rcx]
0x1004bb74c  mov     rax, [rdi]
0x1004bb74f  mov     [rcx], rax
0x1004bb752  test    rax, rax
0x1004bb755  jnz     short loc_1004BB75B
0x1004bb757  mov     [rcx+8], rcx
0x1004bb75b  dec     qword ptr [rsi+8]
0x1004bb75f  dec     qword ptr [rsi+490h]
0x1004bb766  jmp     short loc_1004BB7AE
0x1004bb768  mov     rdi, [rcx+4A0h]
0x1004bb76f  mov     rax, [rdi]
0x1004bb772  mov     [rcx+4A0h], rax
0x1004bb779  mov     [rdi], r15
0x1004bb77c  dec     qword ptr [rsi+8]
0x1004bb780  cmp     qword ptr [rcx+4A0h], 0
0x1004bb788  jnz     short loc_1004BB7AE
0x1004bb78a  mov     ecx, r12d
0x1004bb78d  mov     eax, 1
0x1004bb792  shl     rax, cl
0x1004bb795  mov     rcx, [rsi+6A0h]
0x1004bb79c  test    rax, rcx
0x1004bb79f  jz      short loc_1004BB7AE
0x1004bb7a1  not     rax
0x1004bb7a4  and     rax, rcx
0x1004bb7a7  mov     [rsi+6A0h], rax
0x1004bb7ae  cmp     cs:?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA, 0; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x1004bb7b5  jz      short loc_1004BB7DE
0x1004bb7b7  call    cs:__imp_rand
0x1004bb7bd  mov     r8d, eax
0x1004bb7c0  mov     eax, 66666667h
0x1004bb7c5  imul    r8d
0x1004bb7c8  sar     edx, 1
0x1004bb7ca  mov     ecx, edx
0x1004bb7cc  shr     ecx, 1Fh
0x1004bb7cf  add     edx, ecx
0x1004bb7d1  lea     ecx, [rdx+rdx*4]
0x1004bb7d4  cmp     r8d, ecx
0x1004bb7d7  jnz     short loc_1004BB7DE
0x1004bb7d9  call    ?UpdateStatSnapshot@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<34,1,268435714>::UpdateStatSnapshot(void)
0x1004bb7de  mov     rax, [rsp+1C0h+var_160]
0x1004bb7e3  mov     [rax], r15
0x1004bb7e6  lea     r12, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x1004bb7ed  test    rdi, rdi
0x1004bb7f0  jz      short loc_1004BB803
0x1004bb7f2  mov     rax, [r13+1448h]
0x1004bb7f9  lock inc qword ptr [rax+108h]
0x1004bb801  jmp     short loc_1004BB810
0x1004bb803  mov     rsi, [rsp+1C0h+var_178]
0x1004bb808  mov     rbx, r15
0x1004bb80b  test    rdi, rdi
0x1004bb80e  jz      short loc_1004BB831
0x1004bb810  mov     [rbp+0C0h+var_E8], rdi
0x1004bb814  lea     rcx, [rdi+8]; this
0x1004bb818  xor     r9d, r9d; struct SOSHost *
0x1004bb81b  mov     r8, r13; struct SOS_Scheduler *
0x1004bb81e  mov     rdx, [rsp+1C0h+var_178]; struct SOS_Task::Param *
0x1004bb823  call    ??0SOSHost_Task@@IEAA@PEAVParam@SOS_Task@@PEAVSOS_Scheduler@@PEAVSOSHost@@@Z; SOSHost_Task::SOSHost_Task(SOS_Task::Param *,SOS_Scheduler *,SOSHost *)
0x1004bb828  nop
0x1004bb829  mov     [rdi], r12
0x1004bb82c  jmp     loc_1004BB8D4
0x1004bb831  test    cs:?SOS_Tracing_osTrace@@3KA, 1000h; ulong SOS_Tracing_osTrace
0x1004bb83b  jz      short loc_1004BB87C
0x1004bb83d  mov     edx, 1000h; dwSize
0x1004bb842  xor     ecx, ecx; lpAddress
0x1004bb844  lea     r9d, [rcx+4]; flProtect
0x1004bb848  mov     r8d, 3000h; flAllocationType
0x1004bb84e  call    cs:__imp_VirtualAlloc
0x1004bb854  mov     rdi, rax
0x1004bb857  test    rax, rax
0x1004bb85a  jz      loc_1004BB8EE
0x1004bb860  mov     [rbp+0C0h+var_E0], rax
0x1004bb864  lea     rcx, [rax+8]; this
0x1004bb868  xor     r9d, r9d; struct SOSHost *
0x1004bb86b  mov     r8, r13; struct SOS_Scheduler *
0x1004bb86e  mov     rdx, rsi; struct SOS_Task::Param *
0x1004bb871  call    ??0SOSHost_Task@@IEAA@PEAVParam@SOS_Task@@PEAVSOS_Scheduler@@PEAVSOSHost@@@Z; SOSHost_Task::SOSHost_Task(SOS_Task::Param *,SOS_Scheduler *,SOSHost *)
0x1004bb876  nop
0x1004bb877  mov     [rdi], r12
0x1004bb87a  jmp     short loc_1004BB8D4
0x1004bb87c  mov     [rsp+1C0h+var_170], 0A00h
0x1004bb884  mov     rcx, [r13+0E78h]
0x1004bb88b  mov     rax, [rcx]
0x1004bb88e  mov     byte ptr [rsp+1C0h+var_1A0], 6
0x1004bb893  mov     r9d, 0A00h
0x1004bb899  lea     r8, aSqlDktempSosIn_2; "Sql\\DkTemp\\sos\\include\\sos.inl"
0x1004bb8a0  mov     edx, 3E0h
0x1004bb8a5  call    qword ptr [rax+50h]
0x1004bb8a8  mov     rdi, rax
0x1004bb8ab  mov     [rbp+0C0h+var_128], rax
0x1004bb8af  test    rax, rax
0x1004bb8b2  jz      short loc_1004BB8CC
0x1004bb8b4  lea     rcx, [rax+8]; this
0x1004bb8b8  xor     r9d, r9d; struct SOSHost *
0x1004bb8bb  mov     r8, r13; struct SOS_Scheduler *
0x1004bb8be  mov     rdx, rsi; struct SOS_Task::Param *
0x1004bb8c1  call    ??0SOSHost_Task@@IEAA@PEAVParam@SOS_Task@@PEAVSOS_Scheduler@@PEAVSOSHost@@@Z; SOSHost_Task::SOSHost_Task(SOS_Task::Param *,SOS_Scheduler *,SOSHost *)
0x1004bb8c6  nop
0x1004bb8c7  mov     [rdi], r12
0x1004bb8ca  jmp     short loc_1004BB8CF
0x1004bb8cc  mov     rdi, r15
0x1004bb8cf  test    rdi, rdi
0x1004bb8d2  jz      short loc_1004BB8EE
0x1004bb8d4  lea     rbx, [rdi+8]
0x1004bb8d8  test    rbx, rbx
0x1004bb8db  jz      short loc_1004BB8EE
0x1004bb8dd  lea     rcx, [r13+30h]
0x1004bb8e1  mov     rdx, rbx
0x1004bb8e4  call    ?AppendElem@?$TList@VSOS_Scheduler@@VSOS_Task@@$0BA@UTListSLock@@@@QEAAXPEAVSOS_Task@@@Z; TList<SOS_Scheduler,SOS_Task,16,TListSLock>::AppendElem(SOS_Task *)
  ... truncated ...
```
