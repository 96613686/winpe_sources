# BootAndKeepProcessAliveInWcow(wchar_t const *,wchar_t const *,wchar_t const *,IMemObj *)

- ea: `0x10043f6a0`
- end: `0x10043ffb4`
- name: `?BootAndKeepProcessAliveInWcow@@YAJPEB_W00PEAVIMemObj@@@Z`
- size: `2324`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, const wchar_t *, struct IMemObj *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x100412470`
- `0x10043ffc0`

## callees

- `0x100401580`
- `0x100408320`
- `0x100408560`
- `0x100408810`
- `0x10041d870`
- `0x10041df30`
- `0x10041e170`
- `0x10041e420`
- `0x10041e540`
- `0x10041e640`
- `0x10043ef80`
- `0x10043f6a0`
- `0x1004404f0`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x10043fd45`
- `KERNEL32!VirtualProtect` at `0x10043fd45`
- `KERNEL32!QueryPerformanceCounter` at `0x10043f977`
- `KERNEL32!QueryPerformanceCounter` at `0x10043f9c8`
- `KERNEL32!QueryPerformanceCounter` at `0x10043fc66`
- `KERNEL32!QueryPerformanceCounter` at `0x10043fcbc`
- `KERNEL32!QueryPerformanceCounter` at `0x10043f977`
- `KERNEL32!QueryPerformanceCounter` at `0x10043f9c8`
- `KERNEL32!QueryPerformanceCounter` at `0x10043fc66`
- `KERNEL32!QueryPerformanceCounter` at `0x10043fcbc`
- `KERNEL32!VirtualFree` at `0x10043fe9a`
- `KERNEL32!VirtualFree` at `0x10043fe9a`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10043f98b`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10043fc80`
- `sqldk!?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z` at `0x10043ff2d`
- `sqldk!?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z` at `0x10043ff2d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043f7c1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043f7c1`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043ff23`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043ff3e`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043ff4d`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043ff5c`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043ff6a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043ff23`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043ff3e`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043ff4d`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043ff5c`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043ff6a`
- `sqldk!SystemThread_TlsOffset` at `0x10043f7a6`
- `sqldk!SystemThread_TlsOffset` at `0x10043f81d`
- `sqldk!SystemThread_TlsOffset` at `0x10043f943`
- `sqldk!SystemThread_TlsOffset` at `0x10043fa6c`
- `sqldk!SystemThread_TlsOffset` at `0x10043fc31`
- `sqldk!SystemThread_TlsIndex` at `0x10043f79d`
- `sqldk!SystemThread_TlsIndex` at `0x10043f814`
- `sqldk!SystemThread_TlsIndex` at `0x10043f93a`
- `sqldk!SystemThread_TlsIndex` at `0x10043fa63`
- `sqldk!SystemThread_TlsIndex` at `0x10043fc28`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10043fb14`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10043fbc2`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10043ff15`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10043fb14`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10043fbc2`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10043ff15`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x10043fb3d`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x10043fb3d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10043f723`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10043f723`
- `sqldk!?EnqueueTaskDirectInternal@SOS_Node@@AEAA?AW4SOS_RESULT@@PEAVParam@SOS_Task@@PEAVSOSHost@@PEAPEAV4@PEAPEAX@Z` at `0x10043f892`
- `sqldk!?EnqueueTaskDirectInternal@SOS_Node@@AEAA?AW4SOS_RESULT@@PEAVParam@SOS_Task@@PEAVSOSHost@@PEAPEAV4@PEAPEAX@Z` at `0x10043f892`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10043f968`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10043f9b8`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10043fc56`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10043fcab`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10043fa18`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10043fdfa`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10043fe36`
- `sqldk!?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A` at `0x10043f7d5`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10043f91a`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10043fad7`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10043fb89`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10043fc08`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10043fedc`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x10043fe78`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10043fa24`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10043fe06`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10043fe42`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10043fa24`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10043fe06`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10043fe42`

## string_xrefs

- `0x10043f712`: `Sql\Ntdbms\xdb\containers\xdbcontainerscommon.cpp`
- `0x10043ff85`: `[%hs] ERROR: Failed to launch WCOW process %s and keep-alive thread in WCOW. (HRESULT 0x%x)`
- `0x10043f783`: `[%hs] ERROR: Failed to initialize SidecarProcessInfo. (HRESULT 0x%x)`
- `0x10043f6f1`: `[%hs] INFO: Enqueues a task %s to the dispatcher.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall BootAndKeepProcessAliveInWcow(
        const wchar_t *a1,
        const wchar_t *a2,
        const wchar_t *a3,
        struct IMemObj *a4)
{
  __int64 *v8; // rdi
  void **v9; // rax
  void **v10; // rbx
  int v12; // eax
  int v13; // r13d
  __int64 v14; // rsi
  __int64 v15; // rax
  __int64 v16; // rsi
  __int64 v17; // r8
  unsigned int v18; // eax
  __int64 *v19; // rsi
  volatile signed __int64 *v20; // r12
  LARGE_INTEGER v21; // rbx
  signed __int64 UniqueThread_low; // r13
  __int64 v23; // r15
  __int64 v24; // r8
  LARGE_INTEGER v25; // rcx
  LONGLONG v26; // rax
  _QWORD *v27; // rcx
  __int64 v28; // rax
  volatile signed __int64 *v29; // rbx
  int v30; // r8d
  __int64 v31; // r8
  __int64 v32; // rax
  _QWORD *v33; // rdi
  __int64 v34; // rbx
  SOS_Node *v35; // rcx
  __int64 v36; // r15
  __int64 *v37; // rcx
  _QWORD *v38; // rcx
  __int64 v39; // rbx
  __int64 *v40; // r14
  __int64 v41; // rsi
  LARGE_INTEGER v42; // rbx
  signed __int64 v43; // rdx
  __int64 v44; // r15
  __int64 v45; // r8
  __int64 v46; // rcx
  LARGE_INTEGER v47; // rcx
  LONGLONG v48; // rax
  __int64 *v49; // rcx
  unsigned __int64 v50; // rax
  SOS_ObjectStore *v51; // rcx
  unsigned int PoolIdForObject; // eax
  char v53; // r10
  __int64 v54; // r9
  __int64 v55; // rax
  _QWORD *v56; // r8
  __int64 v57; // rcx
  int v58; // r8d
  int v59; // r8d
  __int64 *v60; // rcx
  __int64 *v61; // rsi
  __int64 v62; // rbx
  signed __int64 v63; // [rsp+30h] [rbp-A9h]
  int v64; // [rsp+38h] [rbp-A1h]
  DWORD flOldProtect; // [rsp+40h] [rbp-99h] BYREF
  volatile signed __int32 *v66; // [rsp+48h] [rbp-91h] BYREF
  LARGE_INTEGER v67; // [rsp+50h] [rbp-89h] BYREF
  LARGE_INTEGER v68; // [rsp+58h] [rbp-81h] BYREF
  volatile signed __int64 *v69; // [rsp+60h] [rbp-79h]
  int v70; // [rsp+68h] [rbp-71h]
  LARGE_INTEGER PerformanceCount; // [rsp+70h] [rbp-69h] BYREF
  LARGE_INTEGER v72; // [rsp+78h] [rbp-61h] BYREF
  __int64 v73; // [rsp+80h] [rbp-59h]
  int v74; // [rsp+90h] [rbp-49h] BYREF
  void *(__fastcall *v75)(void *); // [rsp+98h] [rbp-41h]
  void **v76; // [rsp+A0h] [rbp-39h]
  char *v77; // [rsp+A8h] [rbp-31h]
  __int64 v78; // [rsp+B0h] [rbp-29h]
  __int64 v79; // [rsp+B8h] [rbp-21h]
  __int128 v80; // [rsp+C0h] [rbp-19h] BYREF
  int v81; // [rsp+D0h] [rbp-9h]

  v73 = -2;
  v68.QuadPart = (LONGLONG)a4;
  v8 = 0;
  v66 = 0;
  log_unlocalized(L"[%hs] INFO: Enqueues a task %s to the dispatcher.\n", "BootAndKeepProcessAliveInWcow", a2);
  v9 = (void **)operator new(0x18u, a4, 1, "Sql\\Ntdbms\\xdb\\containers\\xdbcontainerscommon.cpp", 396, 6u);
  v10 = v9;
  v67.QuadPart = (LONGLONG)v9;
  if ( v9 )
  {
    *v9 = 0;
    v9[1] = 0;
    v9[2] = 0;
  }
  else
  {
    v10 = 0;
  }
  if ( !v10 )
    return 2147942414LL;
  v12 = SidecarProcessInfo::Initialize((SidecarProcessInfo *)v10, a1, a2, a3, a4);
  v13 = v12;
  v64 = v12;
  _mm_lfence();
  if ( v12 >= 0 )
  {
    v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v15 = *(_QWORD *)(v14 + 256);
    if ( !v15 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v15 = *(_QWORD *)(v14 + 256);
    }
    v16 = *(_QWORD *)(v15 + 992);
    v74 = 50;
    v75 = KeepProcessAliveInWcow;
    v76 = v10;
    v77 = (char *)&SOS_PublicGlobals::sm_ResourceManager + 3576;
    v79 = -1;
    v78 = 0;
    v17 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    if ( v17
      && *(_QWORD *)(v17 + 272) == v17
      && qword_1004A9518
      && qword_1004A9758
      && qword_1004A99D8
      && (unsigned int)qword_1004A9538() )
    {
      qword_1004A9678(&v80);
    }
    else
    {
      v80 = XEAID_0;
      v81 = 0;
    }
    v18 = SOS_Node::EnqueueTaskDirectInternal(v16, &v74, 0, &v66, 0);
    if ( v18 )
    {
      v13 = HRESULT_FROM_SOS_RESULT_Uncommon(v18);
      operator delete(*v10, 2u);
      operator delete(v10[1], 2u);
      operator delete(v10[2], 2u);
      operator delete(v10, 0x18u);
      if ( v13 < 0 )
      {
        _mm_lfence();
        log_unlocalized(
          L"[%hs] ERROR: Failed to launch WCOW process %s and keep-alive thread in WCOW. (HRESULT 0x%x)",
          "BootAndKeepProcessAliveInWcow",
          a3,
          (unsigned int)v13);
      }
    }
    else
    {
      v19 = (__int64 *)v66;
      if ( _InterlockedExchangeAdd(v66 + 10, 0xFFFFFFFF) == 1 )
      {
        if ( v19[3] )
        {
          TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(v19 + 2);
        }
        else
        {
          if ( *((_DWORD *)v19 + 46) == 2 )
          {
            v69 = (volatile signed __int64 *)(v19[20] + 4952);
            v20 = v69;
            v70 = 0;
            v21.QuadPart = 0;
            UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
            if ( *(_DWORD *)v69 || _InterlockedCompareExchange64(v69, UniqueThread_low, 0) )
            {
              v23 = 0;
              if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
              {
                v24 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                    + SystemThread_TlsOffset;
                if ( v24 && *(_QWORD *)(v24 + 272) == v24 )
                  v23 = *(_QWORD *)(v24 + 256);
                if ( v23 )
                {
                  if ( Base_PublicGlobals::sm_invariantTscAvailable )
                  {
                    QueryPerformanceCounter(&PerformanceCount);
                    v21 = PerformanceCount;
                  }
                  else
                  {
                    v21.QuadPart = MEMORY[0x7FFE0008];
                  }
                }
              }
              if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
                Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v20, UniqueThread_low);
              else
                Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v20, v23, UniqueThread_low);
              if ( v23 )
              {
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&v72);
                  v25 = v72;
                }
                else
                {
                  v25.QuadPart = MEMORY[0x7FFE0008];
                }
                v26 = 0;
                if ( v25.QuadPart >= (unsigned __int64)v21.QuadPart )
                  v26 = v25.QuadPart - v21.QuadPart;
                *(_QWORD *)(v23 + 3192) += v26;
              }
            }
            v70 = 1;
            v27 = (_QWORD *)v19[1];
            v28 = *v19;
            *(_QWORD *)(v28 + 8) = v27;
            *v27 = v28;
            v19[1] = 0;
            *v19 = 0;
            v29 = v69;
            if ( v69 )
            {
              if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
              {
                v30 = rand();
                if ( v30 == 5 * (v30 / 5) )
                  Spinlock<11,2,268435714>::UpdateStatSnapshot();
              }
              *v29 = 0;
              v69 = 0;
              v70 = 0;
            }
            v13 = v64;
          }
          v31 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v31
            && *(_QWORD *)(v31 + 272) == v31
            && (v32 = *(_QWORD *)(v31 + 256)) != 0
            && *(__int64 **)(v32 + 528) == v19 )
          {
            if ( v19 )
              v8 = v19 - 1;
            *v8 = (__int64)&ISOSHost_TaskImpl::`vftable';
            v33 = v8 + 1;
            v34 = v33[22];
            if ( v34 )
            {
              if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
              {
                _InterlockedDecrement((volatile signed __int32 *)(v34 + 112));
                v34 = v33[22];
              }
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v34 + 24), 0xFFFFFFFF) == 1 )
              {
                if ( *(_QWORD *)(v34 + 8) )
                  TList<HostManager,SOSHost,0,TListSLock>::RemoveElem(*(_QWORD *)(v34 + 16), v34);
                SOSHost::Destroy((SOSHost *)v34);
              }
            }
          }
          else
          {
            v35 = (SOS_Node *)v19[21];
            if ( v35 && *((_QWORD *)v35 + 30) && !SOS_Node::IsTaskStoreDisabled(v35) )
            {
              v36 = *(_QWORD *)(v19[21] + 240);
              v37 = v19 - 1;
              if ( !v19 )
                v37 = 0;
              *v37 = (__int64)&ISOSHost_TaskImpl::`vftable';
              v38 = v37 + 1;
              v39 = v38[22];
              if ( v39 )
              {
                if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
                {
                  _InterlockedDecrement((volatile signed __int32 *)(v39 + 112));
                  v39 = v38[22];
                }
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v39 + 24), 0xFFFFFFFF) == 1 )
                {
                  if ( *(_QWORD *)(v39 + 8) )
                    TList<HostManager,SOSHost,0,TListSLock>::RemoveElem(*(_QWORD *)(v39 + 16), v39);
                  SOSHost::Destroy((SOSHost *)v39);
                }
              }
              v40 = v19 - 1;
              if ( !v19 )
                v40 = 0;
              v41 = *(_QWORD *)(v36 + 2016);
              v42.QuadPart = 0;
              v43 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
              v63 = v43;
              if ( *(_DWORD *)(v41 + 40) || _InterlockedCompareExchange64((volatile signed __int64 *)(v41 + 40), v43, 0) )
              {
                v44 = 0;
                if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
                {
                  v45 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset;
                  if ( v45 && *(_QWORD *)(v45 + 272) == v45 )
                    v44 = *(_QWORD *)(v45 + 256);
                  if ( v44 )
                  {
                    if ( Base_PublicGlobals::sm_invariantTscAvailable )
                    {
                      QueryPerformanceCounter(&v67);
                      v42 = v67;
                    }
                    else
                    {
                      v42.QuadPart = MEMORY[0x7FFE0008];
                    }
                  }
                  v43 = v63;
                }
                v46 = v41 + 40;
                if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
                  Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v46, v43);
                else
                  Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v46, v44, v43);
                if ( v44 )
                {
                  if ( Base_PublicGlobals::sm_invariantTscAvailable )
                  {
                    QueryPerformanceCounter(&v68);
                    v47 = v68;
                  }
                  else
                  {
                    v47.QuadPart = MEMORY[0x7FFE0008];
                  }
                  v48 = 0;
                  if ( v47.QuadPart >= (unsigned __int64)v42.QuadPart )
                    v48 = v47.QuadPart - v42.QuadPart;
                  *(_QWORD *)(v44 + 3192) += v48;
                }
              }
              if ( *(_QWORD *)(v41 + 8) >= *(_QWORD *)v41 )
              {
                if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                {
                  v59 = rand();
                  if ( v59 == 5 * (v59 / 5) )
                    Spinlock<34,1,268435714>::UpdateStatSnapshot();
                }
                *(_QWORD *)(v41 + 40) = 0;
                (*(void (__fastcall **)(__int64 *))(v41 + 48))(v40);
              }
              else
              {
                if ( *(_BYTE *)(*(_QWORD *)(v41 + 32) + 5820LL) )
                {
                  v49 = (__int64 *)(v41 + 16 * ((*(_DWORD *)(v41 + 1176) & 0x3F) + 9LL));
                  *v40 = *v49;
                  if ( !*v49 )
                    v49[1] = (__int64)v40;
                  *v49 = (__int64)v40;
                  ++*(_QWORD *)(v41 + 1176);
                  VirtualProtect(v40, 0x1000u, 1u, &flOldProtect);
                }
                else
                {
                  *v40 = *(_QWORD *)(v41 + 128);
                  if ( !*(_QWORD *)(v41 + 128) )
                    *(_QWORD *)(v41 + 136) = v40;
                  *(_QWORD *)(v41 + 128) = v40;
                }
                v50 = *(_QWORD *)(v41 + 1168) + 1LL;
                ++*(_QWORD *)(v41 + 8);
                v51 = *(SOS_ObjectStore **)(v41 + 32);
                if ( !*((_BYTE *)v51 + 5820) && v50 >= 0x20 )
                {
                  PoolIdForObject = SOS_ObjectStore::GetPoolIdForObject(v51, (struct SList *)v40);
                  v53 = PoolIdForObject;
                  v54 = v41 + 8LL * PoolIdForObject;
                  v55 = *(_QWORD *)(v41 + 128);
                  v56 = *(_QWORD **)(v41 + 136);
                  if ( v56 != (_QWORD *)(v41 + 128) && v56 )
                  {
                    *v56 = *(_QWORD *)(v54 + 1184);
                    *(_QWORD *)(v54 + 1184) = v55;
                  }
                  *(_QWORD *)(v41 + 128) = 0;
                  *(_QWORD *)(v41 + 136) = v41 + 128;
                  v50 = 0;
                  v57 = *(_QWORD *)(v41 + 1696);
                  if ( (v57 & (1LL << v53)) == 0 )
                    *(_QWORD *)(v41 + 1696) = (1LL << v53) | v57;
                }
                *(_QWORD *)(v41 + 1168) = v50;
                if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                {
                  v58 = rand();
                  if ( v58 == 5 * (v58 / 5) )
                    Spinlock<34,1,268435714>::UpdateStatSnapshot();
                }
                *(_QWORD *)(v41 + 40) = 0;
              }
            }
            else if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
            {
              v60 = v19 - 1;
              if ( !v19 )
                v60 = 0;
              VirtualFree(v60, 0, 0x8000u);
            }
            else if ( v19 )
            {
              v61 = v19 - 1;
              if ( v61 )
              {
                *v61 = (__int64)&ISOSHost_TaskImpl::`vftable';
                v62 = v61[23];
                if ( v62 )
                {
                  if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
                  {
                    _InterlockedDecrement((volatile signed __int32 *)(v62 + 112));
                    v62 = v61[23];
                  }
                  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v62 + 24), 0xFFFFFFFF) == 1 )
                  {
                    if ( *(_QWORD *)(v62 + 8) )
                      TList<HostManager,SOSHost,0,TListSLock>::RemoveElem(*(_QWORD *)(v62 + 16), v62);
                    SOSHost::Destroy((SOSHost *)v62);
                  }
                }
                operator delete(v61, 0x3E0u);
              }
            }
          }
        }
      }
    }
  }
  else
  {
    log_unlocalized(
      L"[%hs] ERROR: Failed to initialize SidecarProcessInfo. (HRESULT 0x%x)",
      "BootAndKeepProcessAliveInWcow",
      (unsigned int)v12);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x10043f6a0  push    rbp
0x10043f6a2  push    rbx
0x10043f6a3  push    rsi
0x10043f6a4  push    rdi
0x10043f6a5  push    r12
0x10043f6a7  push    r13
0x10043f6a9  push    r14
0x10043f6ab  push    r15
0x10043f6ad  lea     rbp, [rsp-1Fh]
0x10043f6b2  sub     rsp, 0F8h
0x10043f6b9  mov     [rbp+57h+var_B0], 0FFFFFFFFFFFFFFFEh
0x10043f6c1  mov     rax, cs:__security_cookie
0x10043f6c8  xor     rax, rsp
0x10043f6cb  mov     [rbp+57h+var_50], rax
0x10043f6cf  mov     rsi, r9
0x10043f6d2  mov     r15, r8
0x10043f6d5  mov     r14, rdx
0x10043f6d8  mov     r12, rcx
0x10043f6db  mov     qword ptr [rsp+130h+var_D8], r9
0x10043f6e0  xor     edi, edi
0x10043f6e2  mov     [rsp+130h+var_E8], rdi
0x10043f6e7  mov     r8, rdx
0x10043f6ea  lea     rdx, aBootandkeeppro; "BootAndKeepProcessAliveInWcow"
0x10043f6f1  lea     rcx, aHsInfoEnqueues; "[%hs] INFO: Enqueues a task %s to the d"...
0x10043f6f8  call    ?log_unlocalized@@YAXPEB_WZZ; log_unlocalized(wchar_t const *,...)
0x10043f6fd  mov     [rsp+130h+var_F8], 18Ch
0x10043f705  mov     [rsp+130h+var_108], 6
0x10043f70a  mov     dword ptr [rsp+130h+var_110], 18Ch
0x10043f712  lea     r9, aSqlNtdbmsXdbCo; "Sql\\Ntdbms\\xdb\\containers\\xdbcontai"...
0x10043f719  lea     r8d, [rdi+1]
0x10043f71d  mov     rdx, rsi
0x10043f720  lea     ecx, [rdi+18h]
0x10043f723  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10043f729  mov     rbx, rax
0x10043f72c  mov     qword ptr [rsp+130h+var_E0], rax
0x10043f731  test    rax, rax
0x10043f734  jz      short loc_10043F743
0x10043f736  mov     [rax], rdi
0x10043f739  mov     [rax+8], rdi
0x10043f73d  mov     [rax+10h], rdi
0x10043f741  jmp     short loc_10043F746
0x10043f743  mov     rbx, rdi
0x10043f746  test    rbx, rbx
0x10043f749  jnz     short loc_10043F755
0x10043f74b  mov     eax, 8007000Eh
0x10043f750  jmp     loc_10043FF94
0x10043f755  mov     [rsp+130h+var_110], rsi; struct IMemObj *
0x10043f75a  mov     r9, r15; wchar_t *
0x10043f75d  mov     r8, r14; wchar_t *
0x10043f760  mov     rdx, r12; wchar_t *
0x10043f763  mov     rcx, rbx; this
0x10043f766  call    ?Initialize@SidecarProcessInfo@@QEAAJPEB_W00PEAVIMemObj@@@Z; SidecarProcessInfo::Initialize(wchar_t const *,wchar_t const *,wchar_t const *,IMemObj *)
0x10043f76b  mov     r13d, eax
0x10043f76e  mov     [rsp+130h+var_F8], eax
0x10043f772  lfence
0x10043f775  test    eax, eax
0x10043f777  jns     short loc_10043F794
0x10043f779  mov     r8d, eax
0x10043f77c  lea     rdx, aBootandkeeppro; "BootAndKeepProcessAliveInWcow"
0x10043f783  lea     rcx, aHsErrorFailedT; "[%hs] ERROR: Failed to initialize Sidec"...
0x10043f78a  call    ?log_unlocalized@@YAXPEB_WZZ; log_unlocalized(wchar_t const *,...)
0x10043f78f  jmp     loc_10043FF91
0x10043f794  mov     rdx, gs:58h
0x10043f79d  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10043f7a4  mov     ecx, [rax]
0x10043f7a6  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043f7ad  mov     esi, [rax]
0x10043f7af  add     rsi, [rdx+rcx*8]
0x10043f7b3  mov     rax, [rsi+100h]
0x10043f7ba  test    rax, rax
0x10043f7bd  jnz     short loc_10043F7CE
0x10043f7bf  xor     ecx, ecx
0x10043f7c1  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10043f7c7  mov     rax, [rsi+100h]
0x10043f7ce  mov     rsi, [rax+3E0h]
0x10043f7d5  mov     rax, cs:__imp_?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A; SOS_ResourceManager SOS_PublicGlobals::sm_ResourceManager
0x10043f7dc  add     rax, 0DF8h
0x10043f7e2  mov     [rbp+57h+var_A0], 32h ; '2'
0x10043f7e9  lea     rcx, ?KeepProcessAliveInWcow@@YAPEAXPEAX@Z; KeepProcessAliveInWcow(void *)
0x10043f7f0  mov     [rbp+57h+var_98], rcx
0x10043f7f4  mov     [rbp+57h+var_90], rbx
0x10043f7f8  mov     [rbp+57h+var_88], rax
0x10043f7fc  mov     r14, 0FFFFFFFFFFFFFFFFh
0x10043f803  mov     [rbp+57h+var_78], r14
0x10043f807  mov     [rbp+57h+var_80], rdi
0x10043f80b  mov     rdx, gs:58h
0x10043f814  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10043f81b  mov     ecx, [rax]
0x10043f81d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043f824  mov     r8d, [rax]
0x10043f827  add     r8, [rdx+rcx*8]
0x10043f82b  jz      short loc_10043F86A
0x10043f82d  cmp     [r8+110h], r8
0x10043f834  jnz     short loc_10043F86A
0x10043f836  cmp     cs:qword_1004A9518, 0
0x10043f83e  jz      short loc_10043F86A
0x10043f840  cmp     cs:qword_1004A9758, 0
0x10043f848  jz      short loc_10043F86A
0x10043f84a  cmp     cs:qword_1004A99D8, 0
0x10043f852  jz      short loc_10043F86A
0x10043f854  call    cs:qword_1004A9538
0x10043f85a  test    eax, eax
0x10043f85c  jz      short loc_10043F86A
0x10043f85e  lea     rcx, [rbp+57h+var_70]
0x10043f862  call    cs:qword_1004A9678
0x10043f868  jmp     short loc_10043F87E
0x10043f86a  movups  xmm0, cs:XEAID_0
0x10043f871  movaps  [rbp+57h+var_70], xmm0
0x10043f875  mov     eax, cs:dword_10045A688
0x10043f87b  mov     [rbp+57h+var_60], eax
0x10043f87e  mov     [rsp+130h+var_110], rdi
0x10043f883  lea     r9, [rsp+130h+var_E8]
0x10043f888  xor     r8d, r8d
0x10043f88b  lea     rdx, [rbp+57h+var_A0]
0x10043f88f  mov     rcx, rsi
0x10043f892  call    cs:__imp_?EnqueueTaskDirectInternal@SOS_Node@@AEAA?AW4SOS_RESULT@@PEAVParam@SOS_Task@@PEAVSOSHost@@PEAPEAV4@PEAPEAX@Z; SOS_Node::EnqueueTaskDirectInternal(SOS_Task::Param *,SOSHost *,SOS_Task * *,void * *)
0x10043f898  test    eax, eax
0x10043f89a  jnz     loc_10043FF2B
0x10043f8a0  mov     rsi, [rsp+130h+var_E8]
0x10043f8a5  mov     eax, r14d
0x10043f8a8  lock xadd [rsi+28h], eax
0x10043f8ad  cmp     eax, 1
0x10043f8b0  jnz     loc_10043FF91
0x10043f8b6  cmp     qword ptr [rsi+18h], 0
0x10043f8bb  jz      short loc_10043F8CB
0x10043f8bd  lea     rcx, [rsi+10h]
0x10043f8c1  call    ?RemoveAndDestroy@?$TListElem@V?$TList@VSOS_Scheduler@@VSOS_Task@@$0BA@UTListSLock@@@@@@IEAAXXZ; TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(void)
0x10043f8c6  jmp     loc_10043FF91
0x10043f8cb  mov     eax, [rsi+0B8h]
0x10043f8d1  cmp     eax, 2
0x10043f8d4  jnz     loc_10043FA5A
0x10043f8da  mov     r12, [rsi+0A0h]
0x10043f8e1  add     r12, 1358h
0x10043f8e8  mov     [rbp+57h+var_D0], r12
0x10043f8ec  mov     [rbp+57h+var_C8], edi
0x10043f8ef  mov     rbx, rdi
0x10043f8f2  mov     eax, gs:48h
0x10043f8fa  mov     r13d, eax
0x10043f8fd  mov     eax, [r12]
0x10043f901  test    eax, eax
0x10043f903  jnz     short loc_10043F91A
0x10043f905  xor     eax, eax
0x10043f907  lock cmpxchg [r12], r13
0x10043f90d  mov     eax, edi
0x10043f90f  setz    al
0x10043f912  test    eax, eax
0x10043f914  jnz     loc_10043F9F3
0x10043f91a  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10043f921  mov     ecx, [rax]
0x10043f923  and     ecx, 84h
0x10043f929  mov     r15, rdi
0x10043f92c  cmp     cl, 84h
0x10043f92f  jnz     short loc_10043F98B
0x10043f931  mov     rdx, gs:58h
0x10043f93a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10043f941  mov     ecx, [rax]
0x10043f943  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043f94a  mov     r8d, [rax]
0x10043f94d  add     r8, [rdx+rcx*8]
0x10043f951  jz      short loc_10043F963
0x10043f953  cmp     [r8+110h], r8
0x10043f95a  jnz     short loc_10043F963
0x10043f95c  mov     r15, [r8+100h]
0x10043f963  test    r15, r15
0x10043f966  jz      short loc_10043F98B
0x10043f968  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10043f96f  cmp     [rax], ebx
0x10043f971  jz      short loc_10043F983
0x10043f973  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x10043f977  call    cs:__imp_QueryPerformanceCounter
0x10043f97d  mov     rbx, qword ptr [rbp+57h+PerformanceCount]
0x10043f981  jmp     short loc_10043F98B
0x10043f983  mov     rbx, ds:7FFE0008h
0x10043f98b  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10043f992  mov     rcx, r12
0x10043f995  cmp     byte ptr [rax+0C7h], 0
0x10043f99c  jge     short loc_10043F9AB
0x10043f99e  mov     r8, r13
0x10043f9a1  mov     rdx, r15
0x10043f9a4  call    ?SpinToAcquireOptimistic@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<11,2,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10043f9a9  jmp     short loc_10043F9B3
0x10043f9ab  mov     rdx, r13
0x10043f9ae  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAX_K@Z; Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10043f9b3  test    r15, r15
0x10043f9b6  jz      short loc_10043F9F3
0x10043f9b8  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10043f9bf  cmp     dword ptr [rax], 0
0x10043f9c2  jz      short loc_10043F9D4
0x10043f9c4  lea     rcx, [rbp+57h+var_B8]; lpPerformanceCount
0x10043f9c8  call    cs:__imp_QueryPerformanceCounter
0x10043f9ce  mov     rcx, qword ptr [rbp+57h+var_B8]
0x10043f9d2  jmp     short loc_10043F9DC
0x10043f9d4  mov     rcx, ds:7FFE0008h
0x10043f9dc  mov     rdx, rcx
0x10043f9df  sub     rdx, rbx
0x10043f9e2  mov     rax, rdi
0x10043f9e5  cmp     rcx, rbx
0x10043f9e8  cmovnb  rax, rdx
0x10043f9ec  add     [r15+0C78h], rax
0x10043f9f3  mov     [rbp+57h+var_C8], 1
0x10043f9fa  mov     rcx, [rsi+8]
0x10043f9fe  mov     rax, [rsi]
0x10043fa01  mov     [rax+8], rcx
0x10043fa05  mov     [rcx], rax
0x10043fa08  mov     [rsi+8], rdi
0x10043fa0c  mov     [rsi], rdi
0x10043fa0f  mov     rbx, [rbp+57h+var_D0]
0x10043fa13  test    rbx, rbx
0x10043fa16  jz      short loc_10043FA55
0x10043fa18  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10043fa1f  cmp     byte ptr [rax], 0
0x10043fa22  jz      short loc_10043FA4B
0x10043fa24  call    cs:__imp_rand
0x10043fa2a  mov     r8d, eax
0x10043fa2d  mov     eax, 66666667h
0x10043fa32  imul    r8d
0x10043fa35  sar     edx, 1
0x10043fa37  mov     ecx, edx
0x10043fa39  shr     ecx, 1Fh
0x10043fa3c  add     edx, ecx
0x10043fa3e  lea     ecx, [rdx+rdx*4]
0x10043fa41  cmp     r8d, ecx
0x10043fa44  jnz     short loc_10043FA4B
0x10043fa46  call    ?UpdateStatSnapshot@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXXZ; Spinlock<11,2,268435714>::UpdateStatSnapshot(void)
0x10043fa4b  mov     [rbx], rdi
0x10043fa4e  mov     [rbp+57h+var_D0], rdi
0x10043fa52  mov     [rbp+57h+var_C8], edi
0x10043fa55  mov     r13d, [rsp+130h+var_F8]
0x10043fa5a  mov     rdx, gs:58h
0x10043fa63  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10043fa6a  mov     ecx, [rax]
0x10043fa6c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043fa73  mov     r8d, [rax]
0x10043fa76  add     r8, [rdx+rcx*8]
0x10043fa7a  jz      loc_10043FB1F
0x10043fa80  cmp     [r8+110h], r8
0x10043fa87  jnz     loc_10043FB1F
0x10043fa8d  mov     rax, [r8+100h]
0x10043fa94  test    rax, rax
0x10043fa97  jz      loc_10043FB1F
0x10043fa9d  cmp     [rax+210h], rsi
0x10043faa4  jnz     short loc_10043FB1F
0x10043faa6  test    rsi, rsi
0x10043faa9  jz      short loc_10043FAAF
0x10043faab  lea     rdi, [rsi-8]
0x10043faaf  mov     [rsp+130h+var_100], rdi
0x10043fab4  lea     rax, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x10043fabb  mov     [rdi], rax
0x10043fabe  add     rdi, 8
0x10043fac2  mov     [rsp+130h+var_100], rdi
0x10043fac7  mov     rbx, [rdi+0B0h]
0x10043face  test    rbx, rbx
0x10043fad1  jz      loc_10043FF91
0x10043fad7  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10043fade  test    byte ptr [rax], 8
0x10043fae1  jz      short loc_10043FAEE
0x10043fae3  lock dec dword ptr [rbx+70h]
0x10043fae7  mov     rbx, [rdi+0B0h]
0x10043faee  lock xadd [rbx+18h], r14d
0x10043faf4  cmp     r14d, 1
0x10043faf8  jnz     loc_10043FF91
0x10043fafe  cmp     qword ptr [rbx+8], 0
0x10043fb03  jz      short loc_10043FB11
0x10043fb05  mov     rdx, rbx
0x10043fb08  mov     rcx, [rbx+10h]
0x10043fb0c  call    ?RemoveElem@?$TList@VHostManager@@VSOSHost@@$0A@UTListSLock@@@@QEAAXPEAVSOSHost@@@Z; TList<HostManager,SOSHost,0,TListSLock>::RemoveElem(SOSHost *)
0x10043fb11  mov     rcx, rbx
0x10043fb14  call    cs:__imp_?Destroy@SOSHost@@AEAAXXZ; SOSHost::Destroy(void)
0x10043fb1a  jmp     loc_10043FF91
0x10043fb1f  mov     rcx, [rsi+0A8h]
0x10043fb26  test    rcx, rcx
0x10043fb29  jz      loc_10043FE78
0x10043fb2f  cmp     qword ptr [rcx+0F0h], 0
0x10043fb37  jz      loc_10043FE78
0x10043fb3d  call    cs:__imp_?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ; SOS_Node::IsTaskStoreDisabled(void)
0x10043fb43  test    al, al
0x10043fb45  jnz     loc_10043FE78
0x10043fb4b  mov     rax, [rsi+0A8h]
0x10043fb52  mov     r15, [rax+0F0h]
0x10043fb59  test    rsi, rsi
0x10043fb5c  lea     rcx, [rsi-8]
0x10043fb60  jnz     short loc_10043FB65
0x10043fb62  mov     rcx, rdi
0x10043fb65  mov     [rsp+130h+var_100], rcx
0x10043fb6a  lea     rax, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x10043fb71  mov     [rcx], rax
0x10043fb74  add     rcx, 8
0x10043fb78  mov     [rsp+130h+var_100], rcx
0x10043fb7d  mov     rbx, [rcx+0B0h]
0x10043fb84  test    rbx, rbx
0x10043fb87  jz      short loc_10043FBC8
0x10043fb89  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10043fb90  test    byte ptr [rax], 8
0x10043fb93  jz      short loc_10043FBA0
0x10043fb95  lock dec dword ptr [rbx+70h]
0x10043fb99  mov     rbx, [rcx+0B0h]
0x10043fba0  lock xadd [rbx+18h], r14d
0x10043fba6  cmp     r14d, 1
0x10043fbaa  jnz     short loc_10043FBC8
0x10043fbac  cmp     qword ptr [rbx+8], 0
  ... truncated ...
```
