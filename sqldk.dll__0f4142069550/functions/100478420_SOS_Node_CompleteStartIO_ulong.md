# SOS_Node::CompleteStartIO(ulong)

- ea: `0x100478420`
- end: `0x1004790dd`
- name: `?CompleteStartIO@SOS_Node@@AEAA?AW4SOS_RESULT@@K@Z`
- size: `3261`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x100470170`

## callees

- `0x100403070`
- `0x100406340`
- `0x100406510`
- `0x1004067b0`
- `0x100410810`
- `0x1004208d0`
- `0x1004360f0`
- `0x1004371b0`
- `0x1004718a0`
- `0x100475600`
- `0x100475810`
- `0x100475a50`
- `0x100475b60`
- `0x100478420`
- `0x1004790f0`
- `0x1004795c0`
- `0x100481f00`
- `0x10058bbc0`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x100478a73`
- `KERNEL32!VirtualProtect` at `0x100478a73`
- `KERNEL32!CreateIoCompletionPort` at `0x1004785e3`
- `KERNEL32!CreateIoCompletionPort` at `0x1004785e3`
- `KERNEL32!QueryPerformanceCounter` at `0x1004787b0`
- `KERNEL32!QueryPerformanceCounter` at `0x1004787f9`
- `KERNEL32!QueryPerformanceCounter` at `0x1004789a5`
- `KERNEL32!QueryPerformanceCounter` at `0x1004789ed`
- `KERNEL32!QueryPerformanceCounter` at `0x100478d68`
- `KERNEL32!QueryPerformanceCounter` at `0x100478db0`
- `KERNEL32!QueryPerformanceCounter` at `0x100478f5a`
- `KERNEL32!QueryPerformanceCounter` at `0x100478fa2`
- `KERNEL32!QueryPerformanceCounter` at `0x1004787b0`
- `KERNEL32!QueryPerformanceCounter` at `0x1004787f9`
- `KERNEL32!QueryPerformanceCounter` at `0x1004789a5`
- `KERNEL32!QueryPerformanceCounter` at `0x1004789ed`
- `KERNEL32!QueryPerformanceCounter` at `0x100478d68`
- `KERNEL32!QueryPerformanceCounter` at `0x100478db0`
- `KERNEL32!QueryPerformanceCounter` at `0x100478f5a`
- `KERNEL32!QueryPerformanceCounter` at `0x100478fa2`
- `KERNEL32!VirtualFree` at `0x10047909f`
- `KERNEL32!VirtualFree` at `0x10047909f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100478b31`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100478b74`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10047901e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100478b31`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100478b74`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10047901e`

## string_xrefs

- `0x1004784c1`: `Sql\DkTemp\sos\src\node_ext.cpp`
- `0x100478595`: `Sql\DkTemp\sos\src\node_ext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall SOS_Node::CompleteStartIO(LARGE_INTEGER a1, DWORD a2)
{
  DWORD v2; // r15d
  unsigned int v4; // edi
  unsigned __int64 v5; // r14
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rsi
  _QWORD *v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v14; // rax
  unsigned int v15; // r14d
  __int64 v16; // rdx
  struct SOS_Scheduler *HiddenScheduler; // rbx
  SOS_Task *v18; // rdi
  LARGE_INTEGER v19; // rbx
  signed __int64 v20; // r14
  __int64 v21; // rsi
  __int64 v22; // rdx
  LARGE_INTEGER v23; // rcx
  LONGLONG v24; // rax
  _QWORD *v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rax
  _QWORD *v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rbx
  _QWORD *v32; // rcx
  _QWORD *v33; // r14
  __int64 v34; // rdi
  __int64 v35; // rsi
  LARGE_INTEGER v36; // rbx
  signed __int64 v37; // r15
  __int64 v38; // rdx
  SpinlockBase *v39; // rcx
  LARGE_INTEGER v40; // rcx
  LONGLONG v41; // rax
  _QWORD *v42; // rcx
  DWORD *p_flOldProtect; // r9
  unsigned __int64 v44; // r8
  SOS_ObjectStore *v45; // rcx
  unsigned int PoolIdForObject; // eax
  _QWORD *v47; // rdx
  char v48; // r10
  __int64 v49; // r9
  __int64 v50; // r8
  __int64 v51; // rax
  __int64 v52; // rcx
  int v53; // eax
  int v54; // eax
  _QWORD *v55; // rbx
  __int64 v56; // rbx
  __int64 v57; // rcx
  LARGE_INTEGER v58; // rbx
  signed __int64 UniqueThread_low; // r14
  __int64 v60; // rsi
  __int64 v61; // rdx
  LARGE_INTEGER v62; // rcx
  LONGLONG v63; // rax
  _QWORD *v64; // rcx
  __int64 v65; // rax
  __int64 v66; // rdx
  __int64 v67; // rax
  _QWORD *v68; // rcx
  __int64 v69; // rax
  __int64 v70; // rbx
  _QWORD *v71; // rcx
  __int64 v72; // rsi
  LARGE_INTEGER v73; // rbx
  signed __int64 v74; // r15
  __int64 v75; // rdx
  SpinlockBase *v76; // rcx
  LARGE_INTEGER v77; // rcx
  LONGLONG v78; // rax
  int v79; // eax
  char *v80; // rcx
  int v81; // [rsp+20h] [rbp-E0h]
  unsigned int v82; // [rsp+40h] [rbp-C0h]
  int v83; // [rsp+44h] [rbp-BCh]
  unsigned int v85; // [rsp+4Ch] [rbp-B4h]
  __int64 i; // [rsp+58h] [rbp-A8h]
  __int64 v87; // [rsp+60h] [rbp-A0h]
  SOS_Task *v88; // [rsp+68h] [rbp-98h] BYREF
  SpinlockBase *v89; // [rsp+70h] [rbp-90h] BYREF
  int v90; // [rsp+78h] [rbp-88h]
  SpinlockBase *v91; // [rsp+80h] [rbp-80h] BYREF
  int v92; // [rsp+88h] [rbp-78h]
  LARGE_INTEGER v93; // [rsp+90h] [rbp-70h] BYREF
  LARGE_INTEGER v94; // [rsp+98h] [rbp-68h] BYREF
  _QWORD *v95; // [rsp+A0h] [rbp-60h]
  _QWORD *v96; // [rsp+A8h] [rbp-58h]
  LARGE_INTEGER v97; // [rsp+B0h] [rbp-50h] BYREF
  LARGE_INTEGER v98; // [rsp+B8h] [rbp-48h] BYREF
  LARGE_INTEGER v99; // [rsp+C0h] [rbp-40h] BYREF
  LARGE_INTEGER v100; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD *v101; // [rsp+D0h] [rbp-30h]
  _QWORD *v102; // [rsp+D8h] [rbp-28h]
  LARGE_INTEGER v103; // [rsp+E0h] [rbp-20h] BYREF
  DWORD flOldProtect; // [rsp+E8h] [rbp-18h] BYREF
  char v105; // [rsp+ECh] [rbp-14h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD *v107; // [rsp+F8h] [rbp-8h]
  char *v108; // [rsp+100h] [rbp+0h]
  SOS_Task *v109; // [rsp+108h] [rbp+8h]
  _QWORD *v110; // [rsp+110h] [rbp+10h]
  _QWORD *v111; // [rsp+118h] [rbp+18h]
  char *v112; // [rsp+120h] [rbp+20h]
  SOS_Task *v113; // [rsp+128h] [rbp+28h]
  __int64 v114; // [rsp+130h] [rbp+30h]
  _QWORD *v115; // [rsp+138h] [rbp+38h]
  _BYTE v116[80]; // [rsp+140h] [rbp+40h] BYREF

  v114 = -2;
  v2 = a2;
  v93 = a1;
  v4 = 0;
  v82 = 0;
  v5 = *(unsigned int *)(a1.QuadPart + 200);
  v85 = *(_DWORD *)(a1.QuadPart + 200);
  v6 = *(_QWORD *)(a1.QuadPart + 320);
  v7 = 456 * v5;
  if ( !is_mul_ok(v5, 0x1C8u) )
    v7 = -1;
  if ( v7 == -1 )
    v8 = 0;
  else
    v8 = (*(__int64 (__fastcall **)(__int64, __int64, const char *, __int64, char))(*(_QWORD *)v6 + 80LL))(
           v6,
           v7,
           "Sql\\DkTemp\\sos\\src\\node_ext.cpp",
           488,
           6);
  v87 = v8;
  if ( v8 )
  {
    if ( (_DWORD)v5 )
    {
      v9 = (_QWORD *)(v8 + 8);
      do
      {
        *((_DWORD *)v9 - 2) = 0;
        *((_DWORD *)v9 - 1) = 0;
        *v9 = 0;
        v9[1] = 0;
        v9[2] = 0;
        SchedulerMonitor::Track::Track((SchedulerMonitor::Track *)(v9 + 4));
        v9 = (_QWORD *)(v10 + 456);
      }
      while ( v11 != 1 );
    }
  }
  else
  {
    v8 = 0;
    v87 = 0;
  }
  if ( !v8 )
    return 0x80000000LL;
  *(_QWORD *)(a1.QuadPart + 192) = v8;
  v12 = 8LL * (unsigned int)v5;
  if ( !is_mul_ok((unsigned int)v5, 8u) )
    v12 = -1;
  if ( v12 == -1 )
  {
    *(_QWORD *)(a1.QuadPart + 936) = 0;
    return 0x80000000LL;
  }
  LOBYTE(v81) = 6;
  v14 = (*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64, int))(**(_QWORD **)(a1.QuadPart + 320) + 80LL))(
          *(_QWORD *)(a1.QuadPart + 320),
          v12,
          "Sql\\DkTemp\\sos\\src\\node_ext.cpp",
          501,
          v81);
  *(_QWORD *)(a1.QuadPart + 936) = v14;
  if ( !v14 )
    return 0x80000000LL;
  *(_DWORD *)(a1.QuadPart + 204) = v5;
  v15 = 0;
  v83 = 0;
  if ( v85 )
  {
    _mm_lfence();
    for ( i = 0; ; ++i )
    {
      if ( v4 )
        return v4;
      *(_QWORD *)(*(_QWORD *)(a1.QuadPart + 936) + 8 * i) = CreateIoCompletionPort(
                                                              (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                                              0,
                                                              0,
                                                              v2);
      if ( *(_QWORD *)(*(_QWORD *)(a1.QuadPart + 936) + 8 * i) )
      {
        v16 = 456 * i;
        *(LARGE_INTEGER *)(v16 + v8 + 16) = a1;
        *(_QWORD *)(v16 + v8 + 24) = *(_QWORD *)(*(_QWORD *)(a1.QuadPart + 936) + 8 * i);
        if ( (byte_1007149B4 & 8) == 0 || (*(_BYTE *)(a1.QuadPart + 1568) & 4) != 0 )
        {
          v56 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
              + (unsigned int)SystemThread_TlsOffset;
          v57 = *(_QWORD *)(v56 + 256);
          if ( !v57 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v57 = *(_QWORD *)(v56 + 256);
          }
          if ( !(unsigned int)SOS_Node::EnqueueTaskDirect(
                                *(_QWORD *)(v57 + 992),
                                SOS_Node::ListenOnIOCompletionPort,
                                v8 + 456LL * v15,
                                18,
                                &v88,
                                0) )
          {
            v18 = v88;
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v88 + 10, 0xFFFFFFFF) != 1 )
              goto LABEL_198;
            if ( !*((_QWORD *)v18 + 3) )
            {
              if ( *((_DWORD *)v18 + 46) == 2 )
              {
                v91 = (SpinlockBase *)(*((_QWORD *)v18 + 20) + 4952LL);
                v92 = 0;
                v58.QuadPart = 0;
                UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
                if ( *(_DWORD *)v91
                  || _InterlockedCompareExchange64((volatile signed __int64 *)v91, UniqueThread_low, 0) )
                {
                  v60 = 0;
                  if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
                  {
                    v61 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                        + (unsigned int)SystemThread_TlsOffset;
                    if ( v61 && *(_QWORD *)(v61 + 272) == v61 )
                      v60 = *(_QWORD *)(v61 + 256);
                    if ( v60 )
                    {
                      if ( Base_PublicGlobals::sm_invariantTscAvailable )
                      {
                        QueryPerformanceCounter(&v99);
                        v58 = v99;
                      }
                      else
                      {
                        v58.QuadPart = MEMORY[0x7FFE0008];
                      }
                    }
                  }
                  if ( (qword_1007149B5 & 0x800000) == 0 )
                    Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v91);
                  else
                    Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v91);
                  if ( v60 )
                  {
                    if ( Base_PublicGlobals::sm_invariantTscAvailable )
                    {
                      QueryPerformanceCounter(&v100);
                      v62 = v100;
                    }
                    else
                    {
                      v62.QuadPart = MEMORY[0x7FFE0008];
                    }
                    v63 = 0;
                    if ( v62.QuadPart >= (unsigned __int64)v58.QuadPart )
                      v63 = v62.QuadPart - v58.QuadPart;
                    *(_QWORD *)(v60 + 3192) += v63;
                  }
                }
                v92 = 1;
                v64 = (_QWORD *)*((_QWORD *)v18 + 1);
                v65 = *(_QWORD *)v18;
                *(_QWORD *)(v65 + 8) = v64;
                *v64 = v65;
                *((_QWORD *)v18 + 1) = 0;
                *(_QWORD *)v18 = 0;
                SpinlockHolder<11,2,268435714>::~SpinlockHolder<11,2,268435714>(&v91);
                v15 = v83;
              }
              v66 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                  + (unsigned int)SystemThread_TlsOffset;
              if ( v66 )
              {
                if ( *(_QWORD *)(v66 + 272) == v66 )
                {
                  v67 = *(_QWORD *)(v66 + 256);
                  if ( v67 )
                  {
                    if ( *(SOS_Task **)(v67 + 528) == v18 )
                    {
                      v68 = (_QWORD *)((char *)v18 - 8);
                      if ( !v18 )
                        v68 = 0;
                      v101 = v68;
                      *v68 = &ISOSHost_TaskImpl::`vftable';
                      v110 = v68 + 1;
                      SOS_Task::~SOS_Task((SOS_Task *)(v68 + 1));
                      goto LABEL_198;
                    }
                  }
                }
              }
              v69 = *((_QWORD *)v18 + 21);
              if ( v69 )
              {
                v70 = *(_QWORD *)(v69 + 240);
                if ( v70 )
                {
                  if ( (*(_BYTE *)(v69 + 1568) & 2) == 0 && !SOS_OS_TaskStoreDisabled )
                  {
                    v71 = (_QWORD *)((char *)v18 - 8);
                    if ( !v18 )
                      v71 = 0;
                    v102 = v71;
                    *v71 = &ISOSHost_TaskImpl::`vftable';
                    v111 = v71 + 1;
                    SOS_Task::~SOS_Task((SOS_Task *)(v71 + 1));
                    v33 = (_QWORD *)((char *)v18 - 8);
                    if ( !v18 )
                      v33 = 0;
                    v34 = *(_QWORD *)(v70 + 2016);
                    v72 = 0;
                    v73.QuadPart = 0;
                    v74 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
                    if ( *(_DWORD *)(v34 + 40)
                      || _InterlockedCompareExchange64((volatile signed __int64 *)(v34 + 40), v74, 0) )
                    {
                      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
                      {
                        v75 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                            + (unsigned int)SystemThread_TlsOffset;
                        if ( v75 && *(_QWORD *)(v75 + 272) == v75 )
                          v72 = *(_QWORD *)(v75 + 256);
                        if ( v72 )
                        {
                          if ( Base_PublicGlobals::sm_invariantTscAvailable )
                          {
                            QueryPerformanceCounter(&v103);
                            v73 = v103;
                          }
                          else
                          {
                            v73.QuadPart = MEMORY[0x7FFE0008];
                          }
                        }
                      }
                      v76 = (SpinlockBase *)(v34 + 40);
                      if ( (qword_1007149B5 & 0x800000) == 0 )
                        Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v76);
                      else
                        Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v76);
                      if ( v72 )
                      {
                        if ( Base_PublicGlobals::sm_invariantTscAvailable )
                        {
                          QueryPerformanceCounter(&v93);
                          v77 = v93;
                        }
                        else
                        {
                          v77.QuadPart = MEMORY[0x7FFE0008];
                        }
                        v78 = 0;
                        if ( v77.QuadPart >= (unsigned __int64)v73.QuadPart )
                          v78 = v77.QuadPart - v73.QuadPart;
                        *(_QWORD *)(v72 + 3192) += v78;
                      }
                    }
                    if ( *(_QWORD *)(v34 + 8) < *(_QWORD *)v34 )
                    {
                      if ( *(_BYTE *)(*(_QWORD *)(v34 + 32) + 5820LL) )
                      {
                        v42 = (_QWORD *)(v34 + 16 * ((*(_DWORD *)(v34 + 1176) & 0x3F) + 9LL));
                        *v33 = *v42;
                        if ( !*v42 )
                          v42[1] = v33;
                        p_flOldProtect = (DWORD *)&v105;
LABEL_94:
                        *v42 = v33;
                        ++*(_QWORD *)(v34 + 1176);
                        VirtualProtect(v33, 0x1000u, 1u, p_flOldProtect);
LABEL_98:
                        v44 = *(_QWORD *)(v34 + 1168) + 1LL;
                        v45 = *(SOS_ObjectStore **)(v34 + 32);
                        ++*(_QWORD *)(v34 + 8);
                        if ( !*((_BYTE *)v45 + 5820) && v44 >= 0x20 )
                        {
                          PoolIdForObject = SOS_ObjectStore::GetPoolIdForObject(v45, (struct SList *)v33);
                          v47 = *(_QWORD **)(v34 + 136);
                          v48 = PoolIdForObject;
                          v49 = *(_QWORD *)(v34 + 128);
                          v50 = v34 + 8LL * PoolIdForObject;
                          if ( v47 != (_QWORD *)(v34 + 128) && v47 )
                          {
                            *v47 = *(_QWORD *)(v50 + 1184);
                            *(_QWORD *)(v50 + 1184) = v49;
                          }
                          *(_QWORD *)(v34 + 128) = 0;
                          *(_QWORD *)(v34 + 136) = v34 + 128;
                          v51 = 1LL << PoolIdForObject;
                          v52 = *(_QWORD *)(v34 + 1696);
                          v44 = 0;
                          if ( ((1LL << v48) & v52) == 0 )
                            *(_QWORD *)(v34 + 1696) = v52 | v51;
                        }
                        *(_QWORD *)(v34 + 1168) = v44;
                        if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                        {
                          v53 = rand();
                          if ( v53 == 5 * (v53 / 5) )
                            Spinlock<34,1,268435714>::UpdateStatSnapshot();
                        }
                        *(_QWORD *)(v34 + 40) = 0;
                        v15 = v83;
                        v2 = a2;
LABEL_198:
                        v4 = v82;
                        goto LABEL_199;
                      }
LABEL_95:
                      *v33 = *(_QWORD *)(v34 + 128);
                      if ( !*(_QWORD *)(v34 + 128) )
                        *(_QWORD *)(v34 + 136) = v33;
                      *(_QWORD *)(v34 + 128) = v33;
                      goto LABEL_98;
                    }
                    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                    {
                      v79 = rand();
                      if ( v79 == 5 * (v79 / 5) )
                        Spinlock<34,1,268435714>::UpdateStatSnapshot();
                    }
LABEL_112:
                    *(_QWORD *)(v34 + 40) = 0;
                    (*(void (__fastcall **)(_QWORD *))(v34 + 48))(v33);
                    v15 = v83;
                    v2 = a2;
                    goto LABEL_198;
                  }
                }
              }
              if ( (SOS_Tracing_osTrace & 0x1000) == 0 )
              {
                if ( !v18 )
                  goto LABEL_198;
                v55 = (_QWORD *)((char *)v18 - 8);
                v112 = (char *)v18 - 8;
                if ( v18 == (SOS_Task *)8 )
                  goto LABEL_198;
                *v55 = &ISOSHost_TaskImpl::`vftable';
                v113 = v18;
LABEL_117:
                SOS_Task::~SOS_Task(v18);
                operator delete(v55, 0x3E0u);
                goto LABEL_198;
              }
LABEL_195:
              v80 = (char *)v18 - 8;
              if ( !v18 )
                v80 = 0;
              VirtualFree(v80, 0, 0x8000u);
              goto LABEL_198;
            }
LABEL_31:
            TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy((char *)v18 + 16);
            goto LABEL_198;
          }
          v4 = 0x80000000;
          v82 = 0x80000000;
        }
        else
        {
          HiddenScheduler = SOS_Node::CreateHiddenScheduler(
                              (SOS_Node *)a1.QuadPart,
                              0,
                              1,
                              SOS_PublicGlobals::sm_Priority,
                              0);
          if ( HiddenScheduler )
          {
            SOS_Task::Param::Init(
              (SOS_Task::Param *)v116,
              0x812u,
              (struct SOS_ResourceGroup *)qword_100716558,
              0xFFFFFFFFFFFFFFFFuLL,
              (void *(*)(void *))SOS_Node::ListenOnIOCompletionPort,
              (void *)(v8 + 456LL * v15),
              0);
            if ( !(unsigned int)SOS_Scheduler::EnqueueTask(HiddenScheduler, v116, &v88) )
            {
              v18 = v88;
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)v88 + 10, 0xFFFFFFFF) != 1 )
                goto LABEL_198;
              if ( !*((_QWORD *)v18 + 3) )
              {
                if ( *((_DWORD *)v18 + 46) == 2 )
                {
                  v89 = (SpinlockBase *)(*((_QWORD *)v18 + 20) + 4952LL);
                  v90 = 0;
                  v19.QuadPart = 0;
                  v20 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
                  if ( *(_DWORD *)v89 || _InterlockedCompareExchange64((volatile signed __int64 *)v89, v20, 0) )
                  {
                    v21 = 0;
                    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
                    {
                      v22 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                          + (unsigned int)SystemThread_TlsOffset;
                      if ( v22 && *(_QWORD *)(v22 + 272) == v22 )
                        v21 = *(_QWORD *)(v22 + 256);
                      if ( v21 )
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
                    if ( (qword_1007149B5 & 0x800000) == 0 )
                      Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v89);
                    else
                      Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v89);
                    if ( v21 )
                    {
                      if ( Base_PublicGlobals::sm_invariantTscAvailable )
                      {
                        QueryPerformanceCounter(&v94);
                        v23 = v94;
                      }
                      else
                      {
                        v23.QuadPart = MEMORY[0x7FFE0008];
                      }
                      v24 = 0;
                      if ( v23.QuadPart >= (unsigned __int64)v19.QuadPart )
                        v24 = v23.QuadPart - v19.QuadPart;
                      *(_QWORD *)(v21 + 3192) += v24;
                    }
                  }
                  v90 = 1;
                  v25 = (_QWORD *)*((_QWORD *)v18 + 1);
                  v26 = *(_QWORD *)v18;
                  *(_QWORD *)(v26 + 8) = v25;
                  *v25 = v26;
                  *((_QWORD *)v18 + 1) = 0;
                  *(_QWORD *)v18 = 0;
                  SpinlockHolder<11,2,268435714>::~SpinlockHolder<11,2,268435714>(&v89);
                  v15 = v83;
                }
                v27 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                    + (unsigned int)SystemThread_TlsOffset;
                if ( v27 )
                {
                  if ( *(_QWORD *)(v27 + 272) == v27 )
                  {
                    v28 = *(_QWORD *)(v27 + 256);
                    if ( v28 )
                    {
                      if ( *(SOS_Task **)(v28 + 528) == v18 )
                      {
                        v29 = (_QWORD *)((char *)v18 - 8);
                        if ( !v18 )
                          v29 = 0;
                        v95 = v29;
                        *v29 = &ISOSHost_TaskImpl::`vftable';
                        v115 = v29 + 1;
                        SOS_Task::~SOS_Task((SOS_Task *)(v29 + 1));
                        goto LABEL_198;
                      }
                    }
                  }
                }
                v30 = *((_QWORD *)v18 + 21);
                if ( v30 )
                {
                  v31 = *(_QWORD *)(v30 + 240);
                  if ( v31 )
                  {
                    if ( (*(_BYTE *)(v30 + 1568) & 2) == 0 && !SOS_OS_TaskStoreDisabled )
                    {
                      v32 = (_QWORD *)((char *)v18 - 8);
                      if ( !v18 )
                        v32 = 0;
                      v96 = v32;
                      *v32 = &ISOSHost_TaskImpl::`vftable';
                      v107 = v32 + 1;
                      SOS_Task::~SOS_Task((SOS_Task *)(v32 + 1));
                      v33 = (_QWORD *)((char *)v18 - 8);
                      if ( !v18 )
                        v33 = 0;
                      v34 = *(_QWORD *)(v31 + 2016);
                      v35 = 0;
                      v36.QuadPart = 0;
                      v37 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
                      if ( *(_DWORD *)(v34 + 40)
                        || _InterlockedCompareExchange64((volatile signed __int64 *)(v34 + 40), v37, 0) )
                      {
                        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
                        {
                          v38 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                              + (unsigned int)SystemThread_TlsOffset;
                          if ( v38 && *(_QWORD *)(v38 + 272) == v38 )
                            v35 = *(_QWORD *)(v38 + 256);
                          if ( v35 )
                          {
                            if ( Base_PublicGlobals::sm_invariantTscAvailable )
                            {
                              QueryPerformanceCounter(&v97);
                              v36 = v97;
                            }
                            else
                            {
                              v36.QuadPart = MEMORY[0x7FFE0008];
                            }
                          }
                        }
                        v39 = (SpinlockBase *)(v34 + 40);
                        if ( (qword_1007149B5 & 0x800000) == 0 )
                          Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v39);
                        else
                          Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v39);
                        if ( v35 )
                        {
                          if ( Base_PublicGlobals::sm_invariantTscAvailable )
                          {
                            QueryPerformanceCounter(&v98);
                            v40 = v98;
                          }
                          else
                          {
                            v40.QuadPart = MEMORY[0x7FFE0008];
                          }
                          v41 = 0;
                          if ( v40.QuadPart >= (unsigned __int64)v36.QuadPart )
                            v41 = v40.QuadPart - v36.QuadPart;
                          *(_QWORD *)(v35 + 3192) += v41;
                        }
                      }
                      if ( *(_QWORD *)(v34 + 8) < *(_QWORD *)v34 )
                      {
                        if ( *(_BYTE *)(*(_QWORD *)(v34 + 32) + 5820LL) )
                        {
                          v42 = (_QWORD *)(v34 + 16 * ((*(_DWORD *)(v34 + 1176) & 0x3F) + 9LL));
                          *v33 = *v42;
                          if ( !*v42 )
                            v42[1] = v33;
                          p_flOldProtect = &flOldProtect;
                          goto LABEL_94;
                        }
                        goto LABEL_95;
                      }
                      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                      {
                        v54 = rand();
                        if ( v54 == 5 * (v54 / 5) )
                          Spinlock<34,1,268435714>::UpdateStatSnapshot();
                      }
                      goto LABEL_112;
                    }
                  }
                }
                if ( (SOS_Tracing_osTrace & 0x1000) == 0 )
                {
                  if ( !v18 )
                    goto LABEL_198;
                  v55 = (_QWORD *)((char *)v18 - 8);
                  v108 = (char *)v18 - 8;
                  if ( v18 == (SOS_Task *)8 )
                    goto LABEL_198;
                  *v55 = &ISOSHost_TaskImpl::`vftable';
                  v109 = v18;
                  goto LABEL_117;
                }
                goto LABEL_195;
              }
              goto LABEL_31;
            }
            v4 = 0x80000000;
            v82 = 0x80000000;
          }
          else
          {
            v4 = 0x80000000;
            v82 = 0x80000000;
          }
        }
      }
      else
      {
        v4 = 0x80000000;
        v82 = 0x80000000;
      }
LABEL_199:
      v83 = ++v15;
      v8 = v87;
      if ( v15 >= v85 )
        return v4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x100478420  push    rbp
0x100478422  push    rsi
0x100478423  push    rdi
0x100478424  push    r12
0x100478426  push    r13
0x100478428  push    r14
0x10047842a  push    r15
0x10047842c  lea     rbp, [rsp-0A0h]
0x100478434  sub     rsp, 1A0h
0x10047843b  mov     [rbp+0D0h+var_A0], 0FFFFFFFFFFFFFFFEh
0x100478443  mov     [rsp+1D0h+arg_10], rbx
0x10047844b  mov     rax, cs:__security_cookie
0x100478452  xor     rax, rsp
0x100478455  mov     [rbp+0D0h+var_40], rax
0x10047845c  mov     r15d, edx
0x10047845f  mov     [rsp+1D0h+var_188], edx
0x100478463  mov     r13, rcx
0x100478466  mov     qword ptr [rbp+0D0h+var_140], rcx
0x10047846a  xor     r12d, r12d
0x10047846d  mov     edi, r12d
0x100478470  mov     [rsp+1D0h+var_190], r12d
0x100478475  mov     r14d, [rcx+0C8h]
0x10047847c  mov     [rsp+1D0h+var_184], r14d
0x100478481  mov     ebx, r14d
0x100478484  mov     [rsp+1D0h+var_18C], 1E8h
0x10047848c  mov     rcx, [rcx+140h]
0x100478493  mov     eax, 1C8h
0x100478498  mul     r14
0x10047849b  mov     rdx, rax
0x10047849e  mov     r9, 0FFFFFFFFFFFFFFFFh
0x1004784a5  cmovo   rdx, r9
0x1004784a9  cmp     rdx, r9
0x1004784ac  jnz     short loc_1004784B3
0x1004784ae  mov     esi, r12d
0x1004784b1  jmp     short loc_1004784CE
0x1004784b3  mov     rax, [rcx]
0x1004784b6  mov     byte ptr [rsp+1D0h+var_1B0], 6
0x1004784bb  mov     r9d, 1E8h
0x1004784c1  lea     r8, aSqlDktempSosSr_19; "Sql\\DkTemp\\sos\\src\\node_ext.cpp"
0x1004784c8  call    qword ptr [rax+50h]
0x1004784cb  mov     rsi, rax
0x1004784ce  mov     [rsp+1D0h+var_178], rsi
0x1004784d3  mov     [rsp+1D0h+var_170], rsi
0x1004784d8  test    rsi, rsi
0x1004784db  jz      short loc_10047851B
0x1004784dd  mov     r8, rbx
0x1004784e0  test    r14d, r14d
0x1004784e3  jz      short loc_100478523
0x1004784e5  lea     rdx, [rsi+8]
0x1004784e9  nop     dword ptr [rax+00000000h]
0x1004784f0  mov     [rdx-8], r12d
0x1004784f4  mov     [rdx-4], r12d
0x1004784f8  mov     [rdx], r12
0x1004784fb  mov     [rdx+8], r12
0x1004784ff  mov     [rdx+10h], r12
0x100478503  lea     rcx, [rdx+20h]; this
0x100478507  call    ??0Track@SchedulerMonitor@@QEAA@XZ; SchedulerMonitor::Track::Track(void)
0x10047850c  lea     rdx, [rdx+1C8h]
0x100478513  sub     r8, 1
0x100478517  jnz     short loc_1004784F0
0x100478519  jmp     short loc_100478523
0x10047851b  mov     rsi, r12
0x10047851e  mov     [rsp+1D0h+var_170], r12
0x100478523  test    rsi, rsi
0x100478526  jz      short loc_100478558
0x100478528  mov     [r13+0C0h], rsi
0x10047852f  mov     rcx, [r13+140h]
0x100478536  mov     eax, 8
0x10047853b  mul     rbx
0x10047853e  mov     rdx, rax
0x100478541  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x100478548  cmovo   rdx, rbx
0x10047854c  cmp     rdx, rbx
0x10047854f  jnz     short loc_100478587
0x100478551  mov     [r13+3A8h], r12
0x100478558  mov     eax, 80000000h
0x10047855d  mov     rcx, [rbp+0D0h+var_40]
0x100478564  xor     rcx, rsp; StackCookie
0x100478567  call    __security_check_cookie
0x10047856c  mov     rbx, [rsp+1D0h+arg_10]
0x100478574  add     rsp, 1A0h
0x10047857b  pop     r15
0x10047857d  pop     r14
0x10047857f  pop     r13
0x100478581  pop     r12
0x100478583  pop     rdi
0x100478584  pop     rsi
0x100478585  pop     rbp
0x100478586  retn
0x100478587  mov     rax, [rcx]
0x10047858a  mov     byte ptr [rsp+1D0h+var_1B0], 6
0x10047858f  mov     r9d, 1F5h
0x100478595  lea     r8, aSqlDktempSosSr_19; "Sql\\DkTemp\\sos\\src\\node_ext.cpp"
0x10047859c  call    qword ptr [rax+50h]
0x10047859f  mov     [r13+3A8h], rax
0x1004785a6  test    rax, rax
0x1004785a9  jz      short loc_100478558
0x1004785ab  mov     [r13+0CCh], r14d
0x1004785b2  mov     r14d, r12d
0x1004785b5  mov     [rsp+1D0h+var_18C], r12d
0x1004785ba  cmp     [rsp+1D0h+var_184], r12d
0x1004785bf  jbe     loc_1004790D4
0x1004785c5  lfence
0x1004785c8  mov     [rsp+1D0h+var_178], r12
0x1004785cd  nop     dword ptr [rax]
0x1004785d0  test    edi, edi
0x1004785d2  jnz     loc_1004790CD
0x1004785d8  mov     r9d, r15d; NumberOfConcurrentThreads
0x1004785db  xor     r8d, r8d; CompletionKey
0x1004785de  xor     edx, edx; ExistingCompletionPort
0x1004785e0  mov     rcx, rbx; FileHandle
0x1004785e3  call    cs:__imp_CreateIoCompletionPort
0x1004785e9  mov     rcx, rax
0x1004785ec  mov     rax, [r13+3A8h]
0x1004785f3  mov     rdi, [rsp+1D0h+var_178]
0x1004785f8  mov     [rax+rdi*8], rcx
0x1004785fc  mov     rax, [r13+3A8h]
0x100478603  cmp     qword ptr [rax+rdi*8], 0
0x100478608  jnz     short loc_100478618
0x10047860a  mov     edi, 80000000h
0x10047860f  mov     [rsp+1D0h+var_190], edi
0x100478613  jmp     loc_1004790B0
0x100478618  imul    rdx, rdi, 1C8h
0x10047861f  mov     [rdx+rsi+10h], r13
0x100478624  mov     rax, [r13+3A8h]
0x10047862b  mov     rcx, [rax+rdi*8]
0x10047862f  mov     [rdx+rsi+18h], rcx
0x100478634  test    cs:byte_1007149B4, 8
0x10047863b  jz      loc_100478C1B
0x100478641  test    byte ptr [r13+620h], 4
0x100478649  jnz     loc_100478C1B
0x10047864f  mov     byte ptr [rsp+1D0h+var_1B0], 0; bool
0x100478654  mov     r9d, cs:?sm_Priority@SOS_PublicGlobals@@2HA; int
0x10047865b  xor     edx, edx; unsigned __int64
0x10047865d  lea     r8d, [rdx+1]; int
0x100478661  mov     rcx, r13; this
0x100478664  call    ?CreateHiddenScheduler@SOS_Node@@QEAAPEAVSOS_Scheduler@@_KJH_N@Z; SOS_Node::CreateHiddenScheduler(unsigned __int64,long,int,bool)
0x100478669  mov     rbx, rax
0x10047866c  test    rax, rax
0x10047866f  jz      loc_100478C06
0x100478675  mov     eax, r14d
0x100478678  imul    rcx, rax, 1C8h
0x10047867f  add     rcx, rsi
0x100478682  mov     [rsp+1D0h+var_1A0], r12; struct SOS_Task *
0x100478687  mov     [rsp+1D0h+var_1A8], rcx; void *
0x10047868c  lea     rax, ?ListenOnIOCompletionPort@SOS_Node@@CAPEAXPEAX@Z; SOS_Node::ListenOnIOCompletionPort(void *)
0x100478693  mov     [rsp+1D0h+var_1B0], rax; void *(*)(void *)
0x100478698  mov     r9, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x10047869f  lea     r8, qword_100716558; struct SOS_ResourceGroup *
0x1004786a6  mov     edx, 812h; unsigned int
0x1004786ab  lea     rcx, [rbp+0D0h+var_90]; this
0x1004786af  call    ?Init@Param@SOS_Task@@QEAAXKPEAVSOS_ResourceGroup@@_KP6APEAXPEAX@Z2PEAV2@@Z; SOS_Task::Param::Init(ulong,SOS_ResourceGroup *,unsigned __int64,void * (*)(void *),void *,SOS_Task *)
0x1004786b4  lea     r8, [rsp+1D0h+var_168]
0x1004786b9  lea     rdx, [rbp+0D0h+var_90]
0x1004786bd  mov     rcx, rbx
0x1004786c0  call    ?EnqueueTask@SOS_Scheduler@@QEAA?AW4SOS_RESULT@@PEAVParam@SOS_Task@@PEAPEAV4@@Z; SOS_Scheduler::EnqueueTask(SOS_Task::Param *,SOS_Task * *)
0x1004786c5  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1004786cc  test    eax, eax
0x1004786ce  jz      short loc_1004786DE
0x1004786d0  mov     edi, 80000000h
0x1004786d5  mov     [rsp+1D0h+var_190], edi
0x1004786d9  jmp     loc_1004790B0
0x1004786de  mov     rdi, [rsp+1D0h+var_168]
0x1004786e3  mov     eax, ebx
0x1004786e5  lock xadd [rdi+28h], eax
0x1004786ea  cmp     eax, 1
0x1004786ed  jnz     loc_1004790AC
0x1004786f3  cmp     qword ptr [rdi+18h], 0
0x1004786f8  jz      short loc_100478708
0x1004786fa  lea     rcx, [rdi+10h]
0x1004786fe  call    ?RemoveAndDestroy@?$TListElem@V?$TList@VSOS_Scheduler@@VSOS_Task@@$0BA@UTListSLock@@@@@@IEAAXXZ; TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(void)
0x100478703  jmp     loc_1004790AC
0x100478708  mov     eax, [rdi+0B8h]
0x10047870e  cmp     eax, 2
0x100478711  jnz     loc_100478857
0x100478717  mov     rax, [rdi+0A0h]
0x10047871e  add     rax, 1358h
0x100478724  mov     [rsp+1D0h+var_160], rax
0x100478729  mov     [rsp+1D0h+var_158], r12d
0x10047872e  mov     rbx, r12
0x100478731  mov     eax, gs:48h
0x100478739  mov     r14d, eax
0x10047873c  mov     rax, [rsp+1D0h+var_160]
0x100478741  mov     ecx, [rax]
0x100478743  test    ecx, ecx
0x100478745  jnz     short loc_100478761
0x100478747  mov     rcx, [rsp+1D0h+var_160]
0x10047874c  xor     eax, eax
0x10047874e  lock cmpxchg [rcx], r14
0x100478753  mov     eax, r12d
0x100478756  setz    al
0x100478759  test    eax, eax
0x10047875b  jnz     loc_100478824
0x100478761  mov     eax, cs:?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100478767  and     eax, 84h
0x10047876c  mov     rsi, r12
0x10047876f  cmp     al, 84h
0x100478771  jnz     short loc_1004787C4
0x100478773  mov     rcx, gs:58h
0x10047877c  mov     eax, cs:_tls_index
0x100478782  mov     edx, cs:SystemThread_TlsOffset
0x100478788  add     rdx, [rcx+rax*8]
0x10047878c  jz      short loc_10047879E
0x10047878e  cmp     [rdx+110h], rdx
0x100478795  jnz     short loc_10047879E
0x100478797  mov     rsi, [rdx+100h]
0x10047879e  test    rsi, rsi
0x1004787a1  jz      short loc_1004787C4
0x1004787a3  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004787aa  jz      short loc_1004787BC
0x1004787ac  lea     rcx, [rbp+0D0h+PerformanceCount]; lpPerformanceCount
0x1004787b0  call    cs:__imp_QueryPerformanceCounter
0x1004787b6  mov     rbx, qword ptr [rbp+0D0h+PerformanceCount]
0x1004787ba  jmp     short loc_1004787C4
0x1004787bc  mov     rbx, ds:7FFE0008h
0x1004787c4  mov     rcx, [rsp+1D0h+var_160]; this
0x1004787c9  test    byte ptr cs:qword_1007149B5+2, 80h
0x1004787d0  jz      short loc_1004787DF
0x1004787d2  mov     r8, r14
0x1004787d5  mov     rdx, rsi
0x1004787d8  call    ?SpinToAcquireOptimistic@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<11,2,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x1004787dd  jmp     short loc_1004787E7
0x1004787df  mov     rdx, r14
0x1004787e2  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAX_K@Z; Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x1004787e7  test    rsi, rsi
0x1004787ea  jz      short loc_100478824
0x1004787ec  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004787f3  jz      short loc_100478805
0x1004787f5  lea     rcx, [rbp+0D0h+var_138]; lpPerformanceCount
0x1004787f9  call    cs:__imp_QueryPerformanceCounter
0x1004787ff  mov     rcx, qword ptr [rbp+0D0h+var_138]
0x100478803  jmp     short loc_10047880D
0x100478805  mov     rcx, ds:7FFE0008h
0x10047880d  mov     rdx, rcx
0x100478810  sub     rdx, rbx
0x100478813  mov     rax, r12
0x100478816  cmp     rcx, rbx
0x100478819  cmovnb  rax, rdx
0x10047881d  add     [rsi+0C78h], rax
0x100478824  mov     [rsp+1D0h+var_158], 1
0x10047882c  mov     rcx, [rdi+8]
0x100478830  mov     rax, [rdi]
0x100478833  mov     [rax+8], rcx
0x100478837  mov     [rcx], rax
0x10047883a  mov     [rdi+8], r12
0x10047883e  mov     [rdi], r12
0x100478841  lea     rcx, [rsp+1D0h+var_160]
0x100478846  call    ??1?$SpinlockHolder@$0L@$01$0BAAAABAC@@@QEAA@XZ; SpinlockHolder<11,2,268435714>::~SpinlockHolder<11,2,268435714>(void)
0x10047884b  mov     r14d, [rsp+1D0h+var_18C]
0x100478850  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x100478857  mov     rcx, gs:58h
0x100478860  mov     eax, cs:_tls_index
0x100478866  mov     edx, cs:SystemThread_TlsOffset
0x10047886c  add     rdx, [rcx+rax*8]
0x100478870  jz      short loc_1004788BC
0x100478872  cmp     [rdx+110h], rdx
0x100478879  jnz     short loc_1004788BC
0x10047887b  mov     rax, [rdx+100h]
0x100478882  test    rax, rax
0x100478885  jz      short loc_1004788BC
0x100478887  cmp     [rax+210h], rdi
0x10047888e  jnz     short loc_1004788BC
0x100478890  test    rdi, rdi
0x100478893  lea     rcx, [rdi-8]
0x100478897  jnz     short loc_10047889C
0x100478899  mov     rcx, r12
0x10047889c  mov     [rbp+0D0h+var_130], rcx
0x1004788a0  lea     rax, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x1004788a7  mov     [rcx], rax
0x1004788aa  add     rcx, 8; this
0x1004788ae  mov     [rbp+0D0h+var_98], rcx
0x1004788b2  call    ??1SOS_Task@@QEAA@XZ; SOS_Task::~SOS_Task(void)
0x1004788b7  jmp     loc_1004790AC
0x1004788bc  mov     rax, [rdi+0A8h]
0x1004788c3  test    rax, rax
0x1004788c6  jz      loc_100478BB4
0x1004788cc  mov     rbx, [rax+0F0h]
0x1004788d3  test    rbx, rbx
0x1004788d6  jz      loc_100478BB4
0x1004788dc  test    byte ptr [rax+620h], 2
0x1004788e3  jnz     loc_100478BB4
0x1004788e9  cmp     cs:?SOS_OS_TaskStoreDisabled@@3HA, 0; int SOS_OS_TaskStoreDisabled
0x1004788f0  jnz     loc_100478BB4
0x1004788f6  test    rdi, rdi
0x1004788f9  lea     rcx, [rdi-8]
0x1004788fd  jnz     short loc_100478902
0x1004788ff  mov     rcx, r12
0x100478902  mov     [rbp+0D0h+var_128], rcx
0x100478906  lea     rax, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x10047890d  mov     [rcx], rax
0x100478910  add     rcx, 8; this
0x100478914  mov     [rbp+0D0h+var_D8], rcx
0x100478918  call    ??1SOS_Task@@QEAA@XZ; SOS_Task::~SOS_Task(void)
0x10047891d  lea     r14, [rdi-8]
0x100478921  test    rdi, rdi
0x100478924  cmovz   r14, r12
0x100478928  mov     rdi, [rbx+7E0h]
0x10047892f  xor     esi, esi
0x100478931  mov     ebx, esi
0x100478933  mov     eax, gs:48h
  ... truncated ...
```
