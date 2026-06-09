# SOS_Scheduler::EnqueueTask(SOS_Task::Param *,SOS_Task * *)

- ea: `0x100481f00`
- end: `0x1004828a1`
- name: `?EnqueueTask@SOS_Scheduler@@QEAA?AW4SOS_RESULT@@PEAVParam@SOS_Task@@PEAPEAV4@@Z`
- size: `2465`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x100478420`
- `0x100481e60`
- `0x10054fb10`

## callees

- `0x100406340`
- `0x100406510`
- `0x1004067b0`
- `0x1004097f0`
- `0x1004098e0`
- `0x10040a8f0`
- `0x1004104a0`
- `0x1004106b0`
- `0x100410810`
- `0x1004360f0`
- `0x1004371b0`
- `0x100475600`
- `0x100475810`
- `0x100475a50`
- `0x100475b60`
- `0x1004795c0`
- `0x100481f00`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x1004820e2`
- `KERNEL32!VirtualProtect` at `0x1004826d6`
- `KERNEL32!VirtualProtect` at `0x1004820e2`
- `KERNEL32!VirtualProtect` at `0x1004826d6`
- `KERNEL32!QueryPerformanceCounter` at `0x100482011`
- `KERNEL32!QueryPerformanceCounter` at `0x100482058`
- `KERNEL32!QueryPerformanceCounter` at `0x100482440`
- `KERNEL32!QueryPerformanceCounter` at `0x100482487`
- `KERNEL32!QueryPerformanceCounter` at `0x10048260d`
- `KERNEL32!QueryPerformanceCounter` at `0x100482655`
- `KERNEL32!QueryPerformanceCounter` at `0x100482011`
- `KERNEL32!QueryPerformanceCounter` at `0x100482058`
- `KERNEL32!QueryPerformanceCounter` at `0x100482440`
- `KERNEL32!QueryPerformanceCounter` at `0x100482487`
- `KERNEL32!QueryPerformanceCounter` at `0x10048260d`
- `KERNEL32!QueryPerformanceCounter` at `0x100482655`
- `KERNEL32!VirtualAlloc` at `0x100482214`
- `KERNEL32!VirtualAlloc` at `0x100482214`
- `KERNEL32!VirtualFree` at `0x10048283d`
- `KERNEL32!VirtualFree` at `0x10048283d`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10048212f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100482792`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004827dd`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10048212f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100482792`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004827dd`

## string_xrefs

- `0x100482265`: `Sql\DkTemp\sos\include\sos.inl`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall SOS_Scheduler::EnqueueTask(__int64 a1, struct SOS_Task::Param *a2, struct SOS_Task **a3)
{
  struct SOS_Task::Param *v3; // rbx
  __int64 v5; // rsi
  MemoryClerkInternal *v6; // rsi
  __int64 v7; // rsi
  _QWORD *v8; // rdi
  LARGE_INTEGER v9; // rbx
  signed __int64 UniqueThread_low; // r13
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
  int v22; // eax
  __int64 v23; // rcx
  _QWORD *v24; // rax
  __int64 v25; // rax
  _QWORD *v26; // rdi
  __int64 v27; // rdx
  unsigned int v28; // r8d
  __int64 v29; // rbx
  unsigned int v30; // r12d
  unsigned int v32; // eax
  SpinlockBase *v33; // r14
  LARGE_INTEGER v34; // rbx
  signed __int64 v35; // r12
  __int64 v36; // rsi
  __int64 v37; // rdx
  LARGE_INTEGER v38; // rcx
  LONGLONG v39; // rax
  _QWORD *v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rdx
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rbx
  _QWORD *v46; // rsi
  __int64 v47; // rdi
  LARGE_INTEGER v48; // rbx
  signed __int64 v49; // r12
  __int64 v50; // r14
  __int64 v51; // rdx
  SpinlockBase *v52; // rcx
  LARGE_INTEGER v53; // rcx
  LONGLONG v54; // rax
  _QWORD *v55; // rcx
  unsigned __int64 v56; // rax
  SOS_ObjectStore *v57; // rcx
  unsigned int PoolIdForObject; // eax
  char v59; // r9
  __int64 v60; // r8
  __int64 v61; // r10
  _QWORD *v62; // rdx
  __int64 v63; // rcx
  int v64; // r8d
  int v65; // r8d
  DWORD flOldProtect; // [rsp+38h] [rbp-41h] BYREF
  DWORD v67; // [rsp+3Ch] [rbp-3Dh] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp-39h] BYREF
  LARGE_INTEGER v69; // [rsp+48h] [rbp-31h] BYREF
  struct WorkDispatcher::WorkerIdleElem *v70; // [rsp+50h] [rbp-29h] BYREF
  LARGE_INTEGER v71; // [rsp+58h] [rbp-21h] BYREF
  LARGE_INTEGER v72; // [rsp+60h] [rbp-19h] BYREF
  LARGE_INTEGER v73; // [rsp+68h] [rbp-11h] BYREF
  LARGE_INTEGER v74; // [rsp+70h] [rbp-9h] BYREF
  SpinlockBase *v75; // [rsp+78h] [rbp-1h] BYREF
  int v76; // [rsp+80h] [rbp+7h]
  __int64 v77; // [rsp+88h] [rbp+Fh]
  unsigned int v78; // [rsp+E0h] [rbp+67h]
  unsigned int PoolId; // [rsp+F8h] [rbp+7Fh]

  v77 = -2;
  v3 = a2;
  if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                  + (unsigned int)SystemThread_TlsOffset
                  + 256LL) )
    SystemThread::MakeMiniSOSThread(0);
  v5 = *(_QWORD *)(a1 + 5192);
  if ( !v5 )
    goto LABEL_44;
  v6 = *(MemoryClerkInternal **)(v5 + 240);
  if ( !v6 )
    goto LABEL_44;
  PoolId = MemoryClerkInternal::GetPoolId(v6);
  v7 = *((_QWORD *)v6 + 252);
  v8 = 0;
  v9.QuadPart = 0;
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  if ( *(_DWORD *)(v7 + 40) || _InterlockedCompareExchange64((volatile signed __int64 *)(v7 + 40), UniqueThread_low, 0) )
  {
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
        QueryPerformanceCounter(&v69);
        v14 = v69;
      }
      else
      {
        v14.QuadPart = MEMORY[0x7FFE0008];
      }
      v15 = 0;
      if ( v14.QuadPart >= (unsigned __int64)v9.QuadPart )
        v15 = v14.QuadPart - v9.QuadPart;
      *(_QWORD *)(v11 + 3192) += v15;
    }
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
      v23 = *(_QWORD *)(v7 + 1696);
      if ( (v23 & (1LL << PoolId)) != 0 )
        *(_QWORD *)(v7 + 1696) = v23 & ~(1LL << PoolId);
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
        VirtualProtect(*v17, 0x1000u, 4u, &flOldProtect);
        v8 = *v17;
        v20 = *(_QWORD **)*v17;
        *v17 = v20;
        if ( !v20 )
          v17[1] = v17;
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
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v22 = rand();
    if ( v22 == 5 * (v22 / 5) )
      Spinlock<34,1,268435714>::UpdateStatSnapshot();
  }
  *(_QWORD *)(v7 + 40) = 0;
  v3 = a2;
  if ( v8 )
  {
    _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(a1 + 5192) + 264LL));
    SOSHost_Task::SOSHost_Task((SOSHost_Task *)(v8 + 1), a2, (struct SOS_Scheduler *)a1, 0);
    *v8 = &ISOSHost_TaskImpl::`vftable';
  }
  else
  {
LABEL_44:
    if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
    {
      v24 = VirtualAlloc(0, 0x1000u, 0x3000u, 4u);
      v8 = v24;
      if ( !v24 )
        return 3221225472LL;
      SOSHost_Task::SOSHost_Task((SOSHost_Task *)(v24 + 1), v3, (struct SOS_Scheduler *)a1, 0);
      *v8 = &ISOSHost_TaskImpl::`vftable';
    }
    else
    {
      v25 = (*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64, char))(**(_QWORD **)(a1 + 3704) + 80LL))(
              *(_QWORD *)(a1 + 3704),
              992,
              "Sql\\DkTemp\\sos\\include\\sos.inl",
              2560,
              6);
      v8 = (_QWORD *)v25;
      if ( v25 )
      {
        SOSHost_Task::SOSHost_Task((SOSHost_Task *)(v25 + 8), v3, (struct SOS_Scheduler *)a1, 0);
        *v8 = &ISOSHost_TaskImpl::`vftable';
      }
      else
      {
        v8 = 0;
      }
      if ( !v8 )
        return 3221225472LL;
    }
  }
  v26 = v8 + 1;
  if ( !v26 )
    return 3221225472LL;
  TList<SOS_Scheduler,SOS_Task,16,TListSLock>::AppendElem(a1 + 48, v26);
  v27 = *(_DWORD *)v3 | 1u;
  v28 = *((_DWORD *)v26 + 12);
  v29 = a1 + 36LL * *(unsigned int *)(*(_QWORD *)(v26[11] + 3336LL) + 2864LL);
  _InterlockedExchangeAdd((volatile signed __int32 *)(v29 + 168), v28);
  _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 5212), v28);
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 3544));
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 3548));
  v30 = WorkDispatcher::AcquireWorker(a1 + 4816, v27, 0, &v70);
  v78 = v30;
  if ( !v30 )
  {
    WorkDispatcher::EnqueueTask((WorkDispatcher *)(a1 + 4816), (struct SOS_Task *)v26, v70, a3);
    return 0;
  }
  *a3 = 0;
  v32 = -*((_DWORD *)v26 + 12);
  _InterlockedExchangeAdd((volatile signed __int32 *)(v29 + 168), v32);
  _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 5212), v32);
  _InterlockedDecrement((volatile signed __int32 *)(a1 + 3544));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v26 + 10, 0xFFFFFFFF) != 1 )
  {
LABEL_135:
    *a3 = 0;
    return v78;
  }
  if ( v26[3] )
  {
    TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(v26 + 2);
    *a3 = 0;
    return v30;
  }
  if ( *((_DWORD *)v26 + 46) == 2 )
  {
    v75 = (SpinlockBase *)(v26[20] + 4952LL);
    v33 = v75;
    v76 = 0;
    v34.QuadPart = 0;
    v35 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( *(_DWORD *)v75 || _InterlockedCompareExchange64((volatile signed __int64 *)v75, v35, 0) )
    {
      v36 = 0;
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v37 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
            + (unsigned int)SystemThread_TlsOffset;
        if ( v37 && *(_QWORD *)(v37 + 272) == v37 )
          v36 = *(_QWORD *)(v37 + 256);
        if ( v36 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v71);
            v34 = v71;
          }
          else
          {
            v34.QuadPart = MEMORY[0x7FFE0008];
          }
        }
      }
      if ( (qword_1007149B5 & 0x800000) == 0 )
        Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v33);
      else
        Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v33);
      if ( v36 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v72);
          v38 = v72;
        }
        else
        {
          v38.QuadPart = MEMORY[0x7FFE0008];
        }
        v39 = 0;
        if ( v38.QuadPart >= (unsigned __int64)v34.QuadPart )
          v39 = v38.QuadPart - v34.QuadPart;
        *(_QWORD *)(v36 + 3192) += v39;
      }
    }
    v76 = 1;
    v40 = (_QWORD *)v26[1];
    v41 = *v26;
    *(_QWORD *)(v41 + 8) = v40;
    *v40 = v41;
    v26[1] = 0;
    *v26 = 0;
    SpinlockHolder<11,2,268435714>::~SpinlockHolder<11,2,268435714>(&v75);
  }
  v42 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
      + (unsigned int)SystemThread_TlsOffset;
  if ( v42 )
  {
    if ( *(_QWORD *)(v42 + 272) == v42 )
    {
      v43 = *(_QWORD *)(v42 + 256);
      if ( v43 )
      {
        if ( *(_QWORD **)(v43 + 528) == v26 )
        {
          *(v26 - 1) = &ISOSHost_TaskImpl::`vftable';
          SOS_Task::~SOS_Task((SOS_Task *)v26);
          *a3 = 0;
          return v78;
        }
      }
    }
  }
  v44 = v26[21];
  if ( !v44 || (v45 = *(_QWORD *)(v44 + 240)) == 0 || (*(_BYTE *)(v44 + 1568) & 2) != 0 || SOS_OS_TaskStoreDisabled )
  {
    if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
    {
      VirtualFree(v26 - 1, 0, 0x8000u);
      *a3 = 0;
      return v78;
    }
    if ( v26 != (_QWORD *)8 )
    {
      *(v26 - 1) = &ISOSHost_TaskImpl::`vftable';
      SOS_Task::~SOS_Task((SOS_Task *)v26);
      operator delete(v26 - 1, 0x3E0u);
    }
    goto LABEL_135;
  }
  v46 = v26 - 1;
  *(v26 - 1) = &ISOSHost_TaskImpl::`vftable';
  SOS_Task::~SOS_Task((SOS_Task *)v26);
  v47 = *(_QWORD *)(v45 + 2016);
  v48.QuadPart = 0;
  v49 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  if ( *(_DWORD *)(v47 + 40) || _InterlockedCompareExchange64((volatile signed __int64 *)(v47 + 40), v49, 0) )
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
          QueryPerformanceCounter(&v73);
          v48 = v73;
        }
        else
        {
          v48.QuadPart = MEMORY[0x7FFE0008];
        }
      }
    }
    v52 = (SpinlockBase *)(v47 + 40);
    if ( (qword_1007149B5 & 0x800000) == 0 )
      Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v52);
    else
      Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v52);
    if ( v50 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v74);
        v53 = v74;
      }
      else
      {
        v53.QuadPart = MEMORY[0x7FFE0008];
      }
      v54 = 0;
      if ( v53.QuadPart >= (unsigned __int64)v48.QuadPart )
        v54 = v53.QuadPart - v48.QuadPart;
      *(_QWORD *)(v50 + 3192) += v54;
    }
  }
  if ( *(_QWORD *)(v47 + 8) >= *(_QWORD *)v47 )
  {
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v65 = rand();
      if ( v65 == 5 * (v65 / 5) )
        Spinlock<34,1,268435714>::UpdateStatSnapshot();
    }
    *(_QWORD *)(v47 + 40) = 0;
    (*(void (__fastcall **)(_QWORD *))(v47 + 48))(v46);
    *a3 = 0;
    return v78;
  }
  else
  {
    if ( *(_BYTE *)(*(_QWORD *)(v47 + 32) + 5820LL) )
    {
      v55 = (_QWORD *)(v47 + 16 * ((*(_DWORD *)(v47 + 1176) & 0x3F) + 9LL));
      *v46 = *v55;
      if ( !*v55 )
        v55[1] = v46;
      *v55 = v46;
      ++*(_QWORD *)(v47 + 1176);
      VirtualProtect(v46, 0x1000u, 1u, &v67);
    }
    else
    {
      *v46 = *(_QWORD *)(v47 + 128);
      if ( !*(_QWORD *)(v47 + 128) )
        *(_QWORD *)(v47 + 136) = v46;
      *(_QWORD *)(v47 + 128) = v46;
    }
    v56 = *(_QWORD *)(v47 + 1168) + 1LL;
    ++*(_QWORD *)(v47 + 8);
    v57 = *(SOS_ObjectStore **)(v47 + 32);
    if ( !*((_BYTE *)v57 + 5820) && v56 >= 0x20 )
    {
      PoolIdForObject = SOS_ObjectStore::GetPoolIdForObject(v57, (struct SList *)v46);
      v59 = PoolIdForObject;
      v60 = v47 + 8LL * PoolIdForObject;
      v61 = *(_QWORD *)(v47 + 128);
      v62 = *(_QWORD **)(v47 + 136);
      if ( v62 != (_QWORD *)(v47 + 128) && v62 )
      {
        *v62 = *(_QWORD *)(v60 + 1184);
        *(_QWORD *)(v60 + 1184) = v61;
      }
      *(_QWORD *)(v47 + 128) = 0;
      *(_QWORD *)(v47 + 136) = v47 + 128;
      v56 = 0;
      v63 = *(_QWORD *)(v47 + 1696);
      if ( ((1LL << v59) & v63) == 0 )
        *(_QWORD *)(v47 + 1696) = v63 | (1LL << v59);
    }
    *(_QWORD *)(v47 + 1168) = v56;
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v64 = rand();
      if ( v64 == 5 * (v64 / 5) )
        Spinlock<34,1,268435714>::UpdateStatSnapshot();
    }
    *(_QWORD *)(v47 + 40) = 0;
    *a3 = 0;
    return v78;
  }
}

```

## disassembly

```asm
0x100481f00  mov     [rsp-8+arg_10], r8
0x100481f05  mov     [rsp-8+arg_8], rdx
0x100481f0a  mov     [rsp-8+arg_0], rcx
0x100481f0f  push    rbp
0x100481f10  push    rbx
0x100481f11  push    rsi
0x100481f12  push    rdi
0x100481f13  push    r12
0x100481f15  push    r13
0x100481f17  push    r14
0x100481f19  push    r15
0x100481f1b  lea     rbp, [rsp-1Fh]
0x100481f20  sub     rsp, 98h
0x100481f27  mov     [rbp+57h+var_48], 0FFFFFFFFFFFFFFFEh
0x100481f2f  mov     rbx, rdx
0x100481f32  mov     r14, rcx
0x100481f35  mov     r9, gs:58h
0x100481f3e  mov     eax, cs:_tls_index
0x100481f44  mov     r10d, cs:SystemThread_TlsOffset
0x100481f4b  add     r10, [r9+rax*8]
0x100481f4f  cmp     qword ptr [r10+100h], 0
0x100481f57  jnz     short loc_100481F60
0x100481f59  xor     ecx, ecx; void *
0x100481f5b  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100481f60  mov     rsi, [r14+1448h]
0x100481f67  mov     r13d, 1
0x100481f6d  test    rsi, rsi
0x100481f70  jz      loc_1004821F7
0x100481f76  mov     rsi, [rsi+0F0h]
0x100481f7d  test    rsi, rsi
0x100481f80  jz      loc_1004821F7
0x100481f86  mov     rcx, rsi; this
0x100481f89  call    ?GetPoolId@MemoryClerkInternal@@IEBAKXZ; MemoryClerkInternal::GetPoolId(void)
0x100481f8e  mov     dword ptr [rbp+57h+arg_18], eax
0x100481f91  mov     rsi, [rsi+7E0h]
0x100481f98  xor     edi, edi
0x100481f9a  xor     ebx, ebx
0x100481f9c  mov     eax, gs:48h
0x100481fa4  mov     r13d, eax
0x100481fa7  mov     eax, [rsi+28h]
0x100481faa  test    eax, eax
0x100481fac  jnz     short loc_100481FC3
0x100481fae  xor     eax, eax
0x100481fb0  lock cmpxchg [rsi+28h], r13
0x100481fb6  mov     eax, ebx
0x100481fb8  setz    al
0x100481fbb  test    eax, eax
0x100481fbd  jnz     loc_100482082
0x100481fc3  mov     eax, cs:?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100481fc9  and     eax, 84h
0x100481fce  xor     r15d, r15d
0x100481fd1  cmp     al, 84h
0x100481fd3  jnz     short loc_100482025
0x100481fd5  mov     rcx, gs:58h
0x100481fde  mov     eax, cs:_tls_index
0x100481fe4  mov     edx, cs:SystemThread_TlsOffset
0x100481fea  add     rdx, [rcx+rax*8]
0x100481fee  jz      short loc_100482000
0x100481ff0  cmp     [rdx+110h], rdx
0x100481ff7  jnz     short loc_100482000
0x100481ff9  mov     r15, [rdx+100h]
0x100482000  test    r15, r15
0x100482003  jz      short loc_100482025
0x100482005  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, ebx; int Base_PublicGlobals::sm_invariantTscAvailable
0x10048200b  jz      short loc_10048201D
0x10048200d  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x100482011  call    cs:__imp_QueryPerformanceCounter
0x100482017  mov     rbx, qword ptr [rbp+57h+PerformanceCount]
0x10048201b  jmp     short loc_100482025
0x10048201d  mov     rbx, ds:7FFE0008h
0x100482025  lea     rcx, [rsi+28h]; this
0x100482029  test    byte ptr cs:qword_1007149B5+2, 80h
0x100482030  jz      short loc_10048203F
0x100482032  mov     r8, r13
0x100482035  mov     rdx, r15
0x100482038  call    ?SpinToAcquireOptimistic@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<34,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10048203d  jmp     short loc_100482047
0x10048203f  mov     rdx, r13
0x100482042  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100482047  test    r15, r15
0x10048204a  jz      short loc_100482082
0x10048204c  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, edi; int Base_PublicGlobals::sm_invariantTscAvailable
0x100482052  jz      short loc_100482064
0x100482054  lea     rcx, [rbp+57h+var_88]; lpPerformanceCount
0x100482058  call    cs:__imp_QueryPerformanceCounter
0x10048205e  mov     rcx, qword ptr [rbp+57h+var_88]
0x100482062  jmp     short loc_10048206C
0x100482064  mov     rcx, ds:7FFE0008h
0x10048206c  mov     rdx, rcx
0x10048206f  sub     rdx, rbx
0x100482072  xor     eax, eax
0x100482074  cmp     rcx, rbx
0x100482077  cmovnb  rax, rdx
0x10048207b  add     [r15+0C78h], rax
0x100482082  mov     edx, dword ptr [rbp+57h+arg_18]
0x100482085  lea     rcx, [rsi+rdx*8]
0x100482089  cmp     [rcx+4A0h], rdi
0x100482090  jnz     loc_10048219D
0x100482096  mov     ebx, [rsi+498h]
0x10048209c  and     ebx, 3Fh
0x10048209f  add     rbx, 9
0x1004820a3  shl     rbx, 4
0x1004820a7  add     rbx, rsi
0x1004820aa  mov     rax, [rsi+20h]
0x1004820ae  movzx   ecx, byte ptr [rax+16BCh]
0x1004820b5  test    cl, cl
0x1004820b7  jz      short loc_1004820BE
0x1004820b9  cmp     [rbx], rdi
0x1004820bc  jmp     short loc_1004820C5
0x1004820be  cmp     [rsi+80h], rdi
0x1004820c5  setnz   al
0x1004820c8  test    al, al
0x1004820ca  jz      short loc_100482120
0x1004820cc  test    cl, cl
0x1004820ce  jz      short loc_1004820FC
0x1004820d0  lea     r9, [rbp+57h+flOldProtect]; lpflOldProtect
0x1004820d4  mov     edx, 1000h; dwSize
0x1004820d9  mov     r8d, 4; flNewProtect
0x1004820df  mov     rcx, [rbx]; lpAddress
0x1004820e2  call    cs:__imp_VirtualProtect
0x1004820e8  mov     rdi, [rbx]
0x1004820eb  mov     rax, [rdi]
0x1004820ee  mov     [rbx], rax
0x1004820f1  test    rax, rax
0x1004820f4  jnz     short loc_100482115
0x1004820f6  mov     [rbx+8], rbx
0x1004820fa  jmp     short loc_100482115
0x1004820fc  lea     rcx, [rsi+80h]
0x100482103  mov     rdi, [rcx]
0x100482106  mov     rax, [rdi]
0x100482109  mov     [rcx], rax
0x10048210c  test    rax, rax
0x10048210f  jnz     short loc_100482115
0x100482111  mov     [rcx+8], rcx
0x100482115  dec     qword ptr [rsi+8]
0x100482119  dec     qword ptr [rsi+490h]
0x100482120  mov     r13d, 1
0x100482126  cmp     cs:?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA, 0; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10048212d  jz      short loc_100482153
0x10048212f  call    cs:__imp_rand
0x100482135  mov     ecx, eax
0x100482137  mov     eax, 66666667h
0x10048213c  imul    ecx
0x10048213e  sar     edx, 1
0x100482140  mov     eax, edx
0x100482142  shr     eax, 1Fh
0x100482145  add     edx, eax
0x100482147  lea     eax, [rdx+rdx*4]
0x10048214a  cmp     ecx, eax
0x10048214c  jnz     short loc_100482153
0x10048214e  call    ?UpdateStatSnapshot@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<34,1,268435714>::UpdateStatSnapshot(void)
0x100482153  mov     qword ptr [rsi+28h], 0
0x10048215b  mov     rbx, [rbp+57h+arg_8]
0x10048215f  test    rdi, rdi
0x100482162  jz      loc_1004821F7
0x100482168  mov     rax, [r14+1448h]
0x10048216f  lock inc qword ptr [rax+108h]
0x100482177  mov     [rbp+57h+arg_0], rdi
0x10048217b  lea     rcx, [rdi+8]; this
0x10048217f  xor     r9d, r9d; struct SOSHost *
0x100482182  mov     r8, r14; struct SOS_Scheduler *
0x100482185  mov     rdx, rbx; struct SOS_Task::Param *
0x100482188  call    ??0SOSHost_Task@@IEAA@PEAVParam@SOS_Task@@PEAVSOS_Scheduler@@PEAVSOSHost@@@Z; SOSHost_Task::SOSHost_Task(SOS_Task::Param *,SOS_Scheduler *,SOSHost *)
0x10048218d  nop
0x10048218e  lea     r15, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x100482195  mov     [rdi], r15
0x100482198  jmp     loc_1004822AA
0x10048219d  mov     rdi, [rcx+4A0h]
0x1004821a4  mov     rax, [rdi]
0x1004821a7  mov     [rcx+4A0h], rax
0x1004821ae  mov     qword ptr [rdi], 0
0x1004821b5  dec     qword ptr [rsi+8]
0x1004821b9  cmp     qword ptr [rcx+4A0h], 0
0x1004821c1  jnz     loc_100482120
0x1004821c7  mov     ecx, edx
0x1004821c9  mov     r13d, 1
0x1004821cf  mov     eax, r13d
0x1004821d2  shl     rax, cl
0x1004821d5  mov     rcx, [rsi+6A0h]
0x1004821dc  test    rax, rcx
0x1004821df  jz      loc_100482126
0x1004821e5  not     rax
0x1004821e8  and     rax, rcx
0x1004821eb  mov     [rsi+6A0h], rax
0x1004821f2  jmp     loc_100482126
0x1004821f7  test    cs:?SOS_Tracing_osTrace@@3KA, 1000h; ulong SOS_Tracing_osTrace
0x100482201  jz      short loc_100482249
0x100482203  mov     edx, 1000h; dwSize
0x100482208  xor     ecx, ecx; lpAddress
0x10048220a  lea     r9d, [rcx+4]; flProtect
0x10048220e  mov     r8d, 3000h; flAllocationType
0x100482214  call    cs:__imp_VirtualAlloc
0x10048221a  mov     rdi, rax
0x10048221d  test    rax, rax
0x100482220  jz      loc_100482888
0x100482226  mov     [rbp+57h+arg_0], rax
0x10048222a  lea     rcx, [rax+8]; this
0x10048222e  xor     r9d, r9d; struct SOSHost *
0x100482231  mov     r8, r14; struct SOS_Scheduler *
0x100482234  mov     rdx, rbx; struct SOS_Task::Param *
0x100482237  call    ??0SOSHost_Task@@IEAA@PEAVParam@SOS_Task@@PEAVSOS_Scheduler@@PEAVSOSHost@@@Z; SOSHost_Task::SOSHost_Task(SOS_Task::Param *,SOS_Scheduler *,SOSHost *)
0x10048223c  nop
0x10048223d  lea     r15, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x100482244  mov     [rdi], r15
0x100482247  jmp     short loc_1004822AA
0x100482249  mov     dword ptr [rbp+57h+arg_18], 0A00h
0x100482250  mov     rcx, [r14+0E78h]
0x100482257  mov     rax, [rcx]
0x10048225a  mov     [rsp+0D0h+var_B0], 6
0x10048225f  mov     r9d, 0A00h
0x100482265  lea     r8, aSqlDktempSosIn_2; "Sql\\DkTemp\\sos\\include\\sos.inl"
0x10048226c  mov     edx, 3E0h
0x100482271  call    qword ptr [rax+50h]
0x100482274  mov     rdi, rax
0x100482277  mov     [rbp+57h+var_A0], rax
0x10048227b  lea     r15, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x100482282  test    rax, rax
0x100482285  jz      short loc_10048229F
0x100482287  lea     rcx, [rax+8]; this
0x10048228b  xor     r9d, r9d; struct SOSHost *
0x10048228e  mov     r8, r14; struct SOS_Scheduler *
0x100482291  mov     rdx, rbx; struct SOS_Task::Param *
0x100482294  call    ??0SOSHost_Task@@IEAA@PEAVParam@SOS_Task@@PEAVSOS_Scheduler@@PEAVSOSHost@@@Z; SOSHost_Task::SOSHost_Task(SOS_Task::Param *,SOS_Scheduler *,SOSHost *)
0x100482299  nop
0x10048229a  mov     [rdi], r15
0x10048229d  jmp     short loc_1004822A1
0x10048229f  xor     edi, edi
0x1004822a1  test    rdi, rdi
0x1004822a4  jz      loc_100482888
0x1004822aa  add     rdi, 8
0x1004822ae  jz      loc_100482888
0x1004822b4  lea     rcx, [r14+30h]
0x1004822b8  mov     rdx, rdi
0x1004822bb  call    ?AppendElem@?$TList@VSOS_Scheduler@@VSOS_Task@@$0BA@UTListSLock@@@@QEAAXPEAVSOS_Task@@@Z; TList<SOS_Scheduler,SOS_Task,16,TListSLock>::AppendElem(SOS_Task *)
0x1004822c0  mov     edx, [rbx]
0x1004822c2  or      edx, 1
0x1004822c5  mov     rax, [rdi+58h]
0x1004822c9  mov     rcx, [rax+0D08h]
0x1004822d0  mov     r8d, [rdi+30h]
0x1004822d4  mov     eax, [rcx+0B30h]
0x1004822da  lea     rcx, [rax+rax*8]
0x1004822de  lea     rbx, [r14+rcx*4]
0x1004822e2  mov     eax, r8d
0x1004822e5  lock xadd [rbx+0A8h], eax
0x1004822ed  lock xadd [r14+145Ch], r8d
0x1004822f6  lock inc dword ptr [r14+0DD8h]
0x1004822fe  lock inc dword ptr [r14+0DDCh]
0x100482306  lea     r9, [rbp+57h+var_80]
0x10048230a  xor     r8d, r8d
0x10048230d  lea     rcx, [r14+12D0h]
0x100482314  call    ?AcquireWorker@WorkDispatcher@@AEAA?AW4SOS_RESULT@@KHPEAPEAVWorkerIdleElem@1@@Z; WorkDispatcher::AcquireWorker(ulong,int,WorkDispatcher::WorkerIdleElem * *)
0x100482319  mov     r12d, eax
0x10048231c  mov     dword ptr [rbp+57h+arg_0], eax
0x10048231f  test    eax, eax
0x100482321  jnz     short loc_100482342
0x100482323  mov     r9, [rbp+57h+arg_10]; struct SOS_Task **
0x100482327  mov     r8, [rbp+57h+var_80]; struct WorkDispatcher::WorkerIdleElem *
0x10048232b  mov     rdx, rdi; struct SOS_Task *
0x10048232e  lea     rcx, [r14+12D0h]; this
0x100482335  call    ?EnqueueTask@WorkDispatcher@@AEAAXPEAVSOS_Task@@PEAVWorkerIdleElem@1@PEAPEAV2@@Z; WorkDispatcher::EnqueueTask(SOS_Task *,WorkDispatcher::WorkerIdleElem *,SOS_Task * *)
0x10048233a  mov     eax, r12d
0x10048233d  jmp     loc_10048288D
0x100482342  mov     rax, [rbp+57h+arg_10]
0x100482346  mov     qword ptr [rax], 0
0x10048234d  mov     ecx, [rdi+30h]
0x100482350  neg     ecx
0x100482352  mov     eax, ecx
0x100482354  lock xadd [rbx+0A8h], eax
0x10048235c  lock xadd [r14+145Ch], ecx
0x100482365  lock dec dword ptr [r14+0DD8h]
0x10048236d  lea     rcx, [rdi+10h]
0x100482371  mov     eax, 0FFFFFFFFh
0x100482376  lock xadd [rcx+18h], eax
0x10048237b  cmp     eax, 1
0x10048237e  jnz     loc_100482878
0x100482384  cmp     qword ptr [rcx+8], 0
0x100482389  jz      short loc_1004823A3
0x10048238b  call    ?RemoveAndDestroy@?$TListElem@V?$TList@VSOS_Scheduler@@VSOS_Task@@$0BA@UTListSLock@@@@@@IEAAXXZ; TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(void)
0x100482390  mov     rax, [rbp+57h+arg_10]
0x100482394  mov     qword ptr [rax], 0
0x10048239b  mov     eax, dword ptr [rbp+57h+arg_0]
0x10048239e  jmp     loc_10048288D
0x1004823a3  mov     eax, [rdi+0B8h]
0x1004823a9  cmp     eax, 2
0x1004823ac  jnz     loc_1004824DB
0x1004823b2  mov     r14, [rdi+0A0h]
0x1004823b9  add     r14, 1358h
0x1004823c0  mov     [rbp+57h+var_58], r14
0x1004823c4  mov     [rbp+57h+var_50], 0
0x1004823cb  xor     ebx, ebx
0x1004823cd  mov     eax, gs:48h
0x1004823d5  mov     r12d, eax
0x1004823d8  mov     eax, [r14]
0x1004823db  test    eax, eax
0x1004823dd  jnz     short loc_1004823F3
0x1004823df  xor     eax, eax
0x1004823e1  lock cmpxchg [r14], r12
0x1004823e6  mov     eax, ebx
0x1004823e8  setz    al
0x1004823eb  test    eax, eax
  ... truncated ...
```
