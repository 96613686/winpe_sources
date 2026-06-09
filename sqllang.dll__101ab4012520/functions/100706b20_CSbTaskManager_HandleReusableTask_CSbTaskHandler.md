# CSbTaskManager::HandleReusableTask(CSbTaskHandler *)

- ea: `0x100706b20`
- end: `0x100707298`
- name: `?HandleReusableTask@CSbTaskManager@@QEAA_NPEAVCSbTaskHandler@@@Z`
- size: `1912`
- prototype: `bool __fastcall(CSbTaskManager *__hidden this, struct CSbTaskHandler *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x100869a00`

## callees

- `0x100401450`
- `0x100706810`
- `0x100706b20`
- `0x10083a1d0`
- `0x10083a3f0`
- `0x10083a660`
- `0x10086b810`
- `0x10086c9b0`
- `0x10086d6f0`
- `0x10086f460`
- `0x10086f680`
- `0x10086f8f0`
- `0x10086f9f0`
- `0x10086fc60`
- `0x10086fde0`
- `0x100899620`
- `0x101e899b0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100706d3f`
- `KERNEL32!QueryPerformanceCounter` at `0x100706d8e`
- `KERNEL32!QueryPerformanceCounter` at `0x10070710b`
- `KERNEL32!QueryPerformanceCounter` at `0x100707158`
- `KERNEL32!QueryPerformanceCounter` at `0x10086cde4`
- `KERNEL32!QueryPerformanceCounter` at `0x10086ce12`
- `KERNEL32!QueryPerformanceCounter` at `0x10086d266`
- `KERNEL32!QueryPerformanceCounter` at `0x10086d2b3`
- `KERNEL32!QueryPerformanceCounter` at `0x10086d422`
- `KERNEL32!QueryPerformanceCounter` at `0x10086d467`
- `KERNEL32!QueryPerformanceCounter` at `0x10086d54f`
- `KERNEL32!QueryPerformanceCounter` at `0x10086d59c`
- `KERNEL32!QueryPerformanceCounter` at `0x100706d3f`
- `KERNEL32!QueryPerformanceCounter` at `0x100706d8e`
- `KERNEL32!QueryPerformanceCounter` at `0x10070710b`
- `KERNEL32!QueryPerformanceCounter` at `0x100707158`
- `KERNEL32!QueryPerformanceCounter` at `0x10086cde4`
- `KERNEL32!QueryPerformanceCounter` at `0x10086ce12`
- `KERNEL32!QueryPerformanceCounter` at `0x10086d266`
- `KERNEL32!QueryPerformanceCounter` at `0x10086d2b3`
- `KERNEL32!QueryPerformanceCounter` at `0x10086d422`
- `KERNEL32!QueryPerformanceCounter` at `0x10086d467`
- `KERNEL32!QueryPerformanceCounter` at `0x10086d54f`
- `KERNEL32!QueryPerformanceCounter` at `0x10086d59c`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100706d4d`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100707118`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10086d273`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10086d42f`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10086d55c`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100706cdf`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1007070ac`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10086cd7a`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10086d207`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10086d3c7`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10086d4f0`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100706a77`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100706c61`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100706e60`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1007071f8`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10086cebe`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10086cf0d`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10086d035`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10086d2ed`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10086d5d7`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100706d2a`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100706d79`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1007070f7`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100707144`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10086cdd0`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10086cdfe`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10086d252`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10086d29f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10086d412`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10086d457`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10086d53b`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10086d588`
- `sqldk!?ResetAbort@SOS_Task@@SAXW4TASK_ABORT_TYPE@1@@Z` at `0x10086d6d0`
- `sqldk!?ResetAbort@SOS_Task@@SAXW4TASK_ABORT_TYPE@1@@Z` at `0x10086d6d0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100706ddf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100706e19`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1007071ad`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10070725a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100706ddf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100706e19`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1007071ad`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10070725a`
- `sqldk!SystemThread_TlsIndex` at `0x100706cfc`
- `sqldk!SystemThread_TlsIndex` at `0x1007070c9`
- `sqldk!SystemThread_TlsIndex` at `0x10086cd9e`
- `sqldk!SystemThread_TlsIndex` at `0x10086d0bd`
- `sqldk!SystemThread_TlsIndex` at `0x10086d16a`
- `sqldk!SystemThread_TlsIndex` at `0x10086d224`
- `sqldk!SystemThread_TlsIndex` at `0x10086d3e4`
- `sqldk!SystemThread_TlsIndex` at `0x10086d50d`
- `sqldk!SystemThread_TlsOffset` at `0x100706d05`
- `sqldk!SystemThread_TlsOffset` at `0x1007070d2`
- `sqldk!SystemThread_TlsOffset` at `0x10086cda7`
- `sqldk!SystemThread_TlsOffset` at `0x10086d0c6`
- `sqldk!SystemThread_TlsOffset` at `0x10086d173`
- `sqldk!SystemThread_TlsOffset` at `0x10086d22d`
- `sqldk!SystemThread_TlsOffset` at `0x10086d3ed`
- `sqldk!SystemThread_TlsOffset` at `0x10086d516`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10086d0e1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10086d18e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10086d0e1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10086d18e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100706a83`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100706c6d`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100706e6c`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100707204`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10086ceca`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10086cf19`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10086d041`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10086d2f9`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10086d5e3`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100706a83`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100706c6d`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100706e6c`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100707204`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10086ceca`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10086cf19`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10086d041`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10086d2f9`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10086d5e3`

## string_xrefs

- `0x100706b5d`: `SSB TASK: Task handler %p is starting.\n`
- `0x100706f55`: `SSB TASK: Idempotent task %s %p is invoked. Scheduled tasks: %i\n`
- `0x10086d6bf`: `SSB TASK: Task handler %p aborted. Handlers in use: %i\n`
- `0x10086d6a0`: `SSB TASK: Task handler %p stopped due to single task-handler mode. Handlers in use: %i\n`
- `0x10086d09c`: `SSB TASK: Task %s %p completed. Scheduled tasks: %i\n`
- `0x10086cf62`: `SSB TASK: Task %s %p is rescheduled. Scheduled tasks: %i\n`
- `0x10086d671`: `SSB TASK: Task handler %p stopped. Handlers in use: %i\n`
- `0x10086d65e`: `SSB TASK: Task handler %p is rescheduled.\n`
- `0x100706dd1`: `ucstask.cpp`
- `0x100706e0b`: `ucstask.cpp`
- `0x10070719c`: `ucstask.cpp`
- `0x100707249`: `ucstask.cpp`
- `0x100706dd8`: `pitsk->m_pTaskMgr == this`
- `0x1007071a3`: `pitsk->m_pTaskMgr == this`
- `0x100706e12`: `CSbIdempotentTask::x_Idempotent_Running == pitsk->m_eState || CSbIdempotentTask::x_Idempotent_RunningAndReScheduled == pitsk->m_eState`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall CSbTaskManager::HandleReusableTask(CSbTaskManager *this, struct CSbTaskHandler *a2)
{
  char v2; // r14
  char v3; // r12
  __int64 v4; // rsi
  char *v5; // rcx
  unsigned int v6; // ebx
  char v7; // di
  int v8; // r8d
  struct CSbTaskHandler *v9; // r13
  __int64 v11; // rdi
  __int64 NextScheduledTask; // rax
  __int64 v13; // rsi
  _QWORD *v14; // rcx
  __int64 v15; // rax
  _QWORD *v16; // rcx
  __int64 v17; // rax
  int v18; // eax
  unsigned int v19; // r12d
  signed __int32 v20; // ecx
  int v21; // r8d
  CSbTransportMgr *QuadPart; // rbx
  signed __int64 UniqueThread_low; // r14
  __int64 v24; // r8
  CSbTransportMgr *v25; // rcx
  signed __int64 v26; // rax
  int v27; // edi
  int v28; // r14d
  unsigned __int64 v29; // rax
  int v30; // r8d
  __int64 v31; // r9
  __int64 v32; // r13
  unsigned __int64 v33; // rax
  int v34; // eax
  char v35; // r12
  CSbTransportMgr *v36; // rbx
  signed __int64 v37; // r14
  __int64 v38; // r8
  CSbTransportMgr *v39; // rcx
  signed __int64 v40; // rax
  int v41; // r8d
  signed __int64 v43; // rdi
  __int64 v44; // r14
  __int64 v45; // r8
  CSbTransportMgr *v46; // rbx
  CSbTransportMgr *v47; // rcx
  signed __int64 v48; // rax
  __int64 v49; // rdx
  char *v50; // rcx
  char *v51; // rdx
  unsigned int v52; // ebx
  int v53; // r8d
  unsigned __int64 v54; // rax
  int v55; // r8d
  __int64 v56; // rax
  BOOL v57; // ebx
  __int64 v58; // rax
  int v59; // r8d
  __int64 v60; // rbx
  _QWORD *v61; // r8
  unsigned __int64 v62; // rax
  unsigned __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // rax
  bool v66; // zf
  __int64 v67; // rbx
  __int64 v68; // rax
  CSbTransportMgr *v69; // rbx
  signed __int64 v70; // rsi
  __int64 v71; // r8
  CSbTransportMgr *v72; // rcx
  signed __int64 v73; // rax
  int v74; // r8d
  CSbTransportMgr *v75; // rbx
  signed __int64 v76; // rsi
  __int64 v77; // r8
  CSbTransportMgr *v78; // rcx
  signed __int64 v79; // rax
  CSbTransportMgr *v80; // rbx
  signed __int64 v81; // rsi
  __int64 v82; // r8
  CSbTransportMgr *v83; // rcx
  signed __int64 v84; // rax
  volatile signed __int64 *v85; // rbx
  int v86; // r8d
  volatile signed __int64 *v87; // [rsp+30h] [rbp-D0h]
  volatile signed __int64 *v88; // [rsp+40h] [rbp-C0h]
  volatile signed __int64 *v89; // [rsp+50h] [rbp-B0h] BYREF
  int v90; // [rsp+58h] [rbp-A8h]
  int v91; // [rsp+60h] [rbp-A0h]
  LARGE_INTEGER PerformanceCount; // [rsp+70h] [rbp-90h] BYREF
  LARGE_INTEGER v93; // [rsp+78h] [rbp-88h] BYREF
  LARGE_INTEGER v94; // [rsp+80h] [rbp-80h] BYREF
  LARGE_INTEGER v95; // [rsp+88h] [rbp-78h] BYREF
  LARGE_INTEGER v96; // [rsp+90h] [rbp-70h] BYREF
  LARGE_INTEGER v97; // [rsp+98h] [rbp-68h] BYREF
  LARGE_INTEGER v98; // [rsp+A0h] [rbp-60h] BYREF
  LARGE_INTEGER v99; // [rsp+A8h] [rbp-58h] BYREF
  LARGE_INTEGER v100; // [rsp+B0h] [rbp-50h] BYREF
  LARGE_INTEGER v101; // [rsp+B8h] [rbp-48h] BYREF
  LARGE_INTEGER v102; // [rsp+C0h] [rbp-40h] BYREF
  LARGE_INTEGER v103; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v104; // [rsp+D0h] [rbp-30h]
  char v105[8]; // [rsp+E0h] [rbp-20h] BYREF
  int v106; // [rsp+E8h] [rbp-18h]
  int v107; // [rsp+F0h] [rbp-10h]
  __int64 **v108; // [rsp+F8h] [rbp-8h]
  char *v109; // [rsp+100h] [rbp+0h]
  __int64 v110; // [rsp+108h] [rbp+8h]
  __int64 *v111; // [rsp+110h] [rbp+10h] BYREF
  int v112; // [rsp+118h] [rbp+18h]
  int v113; // [rsp+11Ch] [rbp+1Ch]
  __int64 v114; // [rsp+120h] [rbp+20h]
  int v115; // [rsp+128h] [rbp+28h]
  int v116; // [rsp+12Ch] [rbp+2Ch]
  char v117; // [rsp+130h] [rbp+30h] BYREF
  __int64 v118; // [rsp+330h] [rbp+230h]
  __int64 v119; // [rsp+338h] [rbp+238h]
  __int64 v120; // [rsp+340h] [rbp+240h] BYREF
  int v121; // [rsp+348h] [rbp+248h]
  int v122; // [rsp+34Ch] [rbp+24Ch]
  int v123; // [rsp+350h] [rbp+250h]
  char v124[8]; // [rsp+360h] [rbp+260h] BYREF
  int v125; // [rsp+368h] [rbp+268h]
  int v126; // [rsp+370h] [rbp+270h]
  __int64 **v127; // [rsp+378h] [rbp+278h]
  char *v128; // [rsp+380h] [rbp+280h]
  __int64 v129; // [rsp+388h] [rbp+288h]
  __int64 *v130; // [rsp+390h] [rbp+290h] BYREF
  int v131; // [rsp+398h] [rbp+298h]
  int v132; // [rsp+39Ch] [rbp+29Ch]
  __int64 v133; // [rsp+3A0h] [rbp+2A0h]
  int v134; // [rsp+3A8h] [rbp+2A8h]
  int v135; // [rsp+3ACh] [rbp+2ACh]
  char v136; // [rsp+3B0h] [rbp+2B0h] BYREF
  __int64 v137; // [rsp+5B0h] [rbp+4B0h]
  __int64 v138; // [rsp+5B8h] [rbp+4B8h]
  __int64 v139; // [rsp+5C0h] [rbp+4C0h] BYREF
  int v140; // [rsp+5C8h] [rbp+4C8h]
  int v141; // [rsp+5CCh] [rbp+4CCh]
  int v142; // [rsp+5D0h] [rbp+4D0h]
  int v144; // [rsp+648h] [rbp+548h] BYREF

  v104 = -2;
  v9 = a2;
  if ( (UcsTrace::sm_UcsTraceMask & 0x8000) != 0 )
    traceprint(L"SSB TASK: Task handler %p is starting.\n");
  while ( 2 )
  {
    v11 = 0;
    v87 = (volatile signed __int64 *)((char *)this + 424);
    v91 = *((_DWORD *)v9 + 30);
    v89 = 0;
    v90 = 0;
    while ( 1 )
    {
      NextScheduledTask = CSbTaskManager::GetNextScheduledTask(this, v9, &v89, &v144);
      v13 = NextScheduledTask;
      if ( !NextScheduledTask )
        break;
      _InterlockedExchange((volatile __int32 *)(NextScheduledTask + 592), 3);
      v14 = *(_QWORD **)(NextScheduledTask + 16);
      v15 = *(_QWORD *)(NextScheduledTask + 8);
      *(_QWORD *)(v15 + 8) = v14;
      *v14 = v15;
      *(_QWORD *)(v13 + 16) = 0;
      *(_QWORD *)(v13 + 8) = 0;
      v16 = *(_QWORD **)(v13 + 32);
      v17 = *(_QWORD *)(v13 + 24);
      *(_QWORD *)(v17 + 8) = v16;
      *v16 = v17;
      *(_QWORD *)(v13 + 32) = 0;
      *(_QWORD *)(v13 + 24) = 0;
      _InterlockedDecrement((volatile signed __int32 *)this + 174);
      if ( *((_DWORD *)this + 178) >= *((_DWORD *)this + 174) )
        v18 = *((_DWORD *)this + 174);
      else
        v18 = *((_DWORD *)this + 178);
      *((_DWORD *)this + 178) = v18;
      v19 = *((_DWORD *)this + 174);
      v20 = _InterlockedIncrement((volatile signed __int32 *)this + 175);
      _InterlockedIncrement((volatile signed __int32 *)this + 180);
      if ( *((_DWORD *)this + 177) > v20 )
        v20 = *((_DWORD *)this + 177);
      *((_DWORD *)this + 177) = v20;
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v21 = rand();
        if ( v21 == 5 * (v21 / 5) )
          Spinlock<185,6,257>::UpdateStatSnapshot();
      }
      *v89 = 0;
      v90 = 0;
      v88 = (volatile signed __int64 *)(v13 + 40);
      QuadPart = 0;
      UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( *(_DWORD *)(v13 + 40) || _InterlockedCompareExchange64(v88, UniqueThread_low, 0) )
      {
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v24 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v24 && *(_QWORD *)(v24 + 272) == v24 )
            v11 = *(_QWORD *)(v24 + 256);
          if ( v11 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&PerformanceCount);
              QuadPart = (CSbTransportMgr *)PerformanceCount.QuadPart;
            }
            else
            {
              QuadPart = MEMORY[0x7FFE0008];
            }
          }
        }
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<178,7,258>::SpinToAcquireWithExponentialBackoff(v88, UniqueThread_low);
        else
          Spinlock<178,7,258>::SpinToAcquireOptimistic(v88, v11, UniqueThread_low);
        if ( v11 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v93);
            v25 = (CSbTransportMgr *)v93.QuadPart;
          }
          else
          {
            v25 = MEMORY[0x7FFE0008];
          }
          v26 = 0;
          if ( v25 >= QuadPart )
            v26 = v25 - QuadPart;
          *(_QWORD *)(v11 + 3192) += v26;
        }
      }
      if ( *(CSbTaskManager **)(v13 + 568) != this )
        utassert_fail(1u, "pitsk->m_pTaskMgr == this", "ucstask.cpp", 2050, 0);
      if ( *(_DWORD *)(v13 + 592) != 3 && *(_DWORD *)(v13 + 592) != 4 )
        utassert_fail(
          1u,
          "CSbIdempotentTask::x_Idempotent_Running == pitsk->m_eState || CSbIdempotentTask::x_Idempotent_RunningAndReSche"
          "duled == pitsk->m_eState",
          "ucstask.cpp",
          2051,
          0);
      v27 = *(_DWORD *)(v13 + 564);
      v28 = *(_DWORD *)(v13 + 592);
      *(_QWORD *)(v13 + 600) = v9;
      _InterlockedExchangeAdd64((volatile signed __int64 *)(v13 + 624), __rdtsc() - *(_QWORD *)(v13 + 608));
      v29 = __rdtsc();
      *(_QWORD *)(v13 + 616) = ((unsigned __int64)HIDWORD(v29) << 32) | (unsigned int)v29;
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v30 = rand();
        if ( v30 == 5 * (v30 / 5) )
          Spinlock<178,7,258>::UpdateStatSnapshot();
      }
      *v88 = 0;
      if ( (g_XeUcsPkg_enabledBitmap & 4) != 0 )
      {
        v106 = 0x20000;
        v107 = 0;
        v108 = &v111;
        v109 = &v117;
        v118 = 0;
        v110 = 0;
        v119 = 0;
        v111 = &v120;
        v112 = 28;
        v113 = 1;
        v120 = v13;
        v121 = *(_DWORD *)(v13 + 584);
        v114 = v13 + 52;
        v115 = 2 * v27;
        v116 = 4;
        v122 = 1;
        v123 = v28;
        XeUcsPkg::ucs_task_idempotent::Publish((XeUcsPkg::ucs_task_idempotent *)v105);
      }
      if ( (UcsTrace::sm_UcsTraceMask & 0x8000) != 0 )
        traceprint(
          L"SSB TASK: Idempotent task %s %p is invoked. Scheduled tasks: %i\n",
          (&sx_wsIdempotentTaskNames)[*(int *)(v13 + 584)],
          v13,
          v19);
      v32 = (**(__int64 (__fastcall ***)(__int64))v13)(v13);
      v33 = __rdtsc();
      _InterlockedExchangeAdd64(
        (volatile signed __int64 *)(v13 + 632),
        (((unsigned __int64)HIDWORD(v33) << 32) | (unsigned int)v33) - *(_QWORD *)(v13 + 616));
      if ( (g_XeUcsPkg_enabledBitmap & 4) != 0 )
      {
        v125 = 0x20000;
        v126 = 0;
        v127 = &v130;
        v128 = &v136;
        v137 = 0;
        v129 = 0;
        v138 = 0;
        v130 = &v139;
        v131 = 28;
        v132 = 1;
        v139 = v13;
        v140 = *(_DWORD *)(v13 + 584);
        v133 = v13 + 52;
        v134 = 2 * v27;
        v135 = 4;
        v11 = 0;
        v141 = 2;
        v142 = v28;
        XeUcsPkg::ucs_task_idempotent::Publish((XeUcsPkg::ucs_task_idempotent *)v124);
      }
      else
      {
        v11 = 0;
      }
      _InterlockedDecrement((volatile signed __int32 *)this + 175);
      if ( *((_DWORD *)this + 179) == -1 )
      {
        v34 = *((_DWORD *)this + 175);
      }
      else if ( *((_DWORD *)this + 175) >= *((_DWORD *)this + 179) )
      {
        v34 = *((_DWORD *)this + 179);
      }
      else
      {
        v34 = *((_DWORD *)this + 175);
      }
      *((_DWORD *)this + 179) = v34;
      v35 = 0;
      if ( !v32 )
        goto LABEL_138;
      v36 = 0;
      v37 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( *(_DWORD *)v88 || _InterlockedCompareExchange64(v88, v37, 0) )
      {
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v38 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v38 && *(_QWORD *)(v38 + 272) == v38 )
            v11 = *(_QWORD *)(v38 + 256);
          if ( v11 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v94);
              v36 = (CSbTransportMgr *)v94.QuadPart;
            }
            else
            {
              v36 = MEMORY[0x7FFE0008];
            }
          }
        }
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<178,7,258>::SpinToAcquireWithExponentialBackoff(v88, v37);
        else
          Spinlock<178,7,258>::SpinToAcquireOptimistic(v88, v11, v37);
        if ( v11 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v95);
            v39 = (CSbTransportMgr *)v95.QuadPart;
          }
          else
          {
            v39 = MEMORY[0x7FFE0008];
          }
          v40 = 0;
          if ( v39 >= v36 )
            v40 = v39 - v36;
          *(_QWORD *)(v11 + 3192) += v40;
        }
        v11 = 0;
      }
      if ( *(CSbTaskManager **)(v13 + 568) != this )
        utassert_fail(1u, "pitsk->m_pTaskMgr == this", "ucstask.cpp", 2118, 0);
      *(_QWORD *)(v13 + 600) = 0;
      *((_BYTE *)a2 + 48) = *(_BYTE *)(v13 + 596);
      v35 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
      (**(void (__fastcall ***)(CSbTaskManager *))this)(this);
      if ( *(_DWORD *)(v13 + 592) != 3 )
      {
        if ( *(_DWORD *)(v13 + 592) != 4 )
        {
          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v41 = rand();
            if ( v41 == 5 * (v41 / 5) )
              Spinlock<178,7,258>::UpdateStatSnapshot();
          }
          *v88 = 0;
          utassert_fail(1u, "FALSE", "ucstask.cpp", 2200, "Invalid switch value");
          goto LABEL_72;
        }
        v43 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        if ( *(_DWORD *)v89 || _InterlockedCompareExchange64(v89, v43, 0) )
        {
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
          {
            v44 = 0;
            v45 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            if ( v45 && *(_QWORD *)(v45 + 272) == v45 )
              v44 = *(_QWORD *)(v45 + 256);
            if ( v44 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v96);
                v46 = (CSbTransportMgr *)v96.QuadPart;
              }
              else
              {
                v46 = MEMORY[0x7FFE0008];
              }
              Spinlock<185,6,257>::SpinToAcquireWithExponentialBackoff(v89, v43);
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v97);
                v47 = (CSbTransportMgr *)v97.QuadPart;
              }
              else
              {
                v47 = MEMORY[0x7FFE0008];
              }
              v11 = 0;
              v48 = 0;
              if ( v47 >= v46 )
                v48 = v47 - v46;
              *(_QWORD *)(v44 + 3192) += v48;
              goto LABEL_111;
            }
          }
          Spinlock<185,6,257>::SpinToAcquireWithExponentialBackoff(v89, v43);
        }
        v11 = 0;
LABEL_111:
        v90 = 1;
        *(_DWORD *)(v13 + 592) = 2;
        v49 = v144;
        v50 = (char *)this + 16 * v144 + 440;
        *(_QWORD *)(v13 + 8) = *(_QWORD *)v50;
        *(_QWORD *)(*(_QWORD *)v50 + 8LL) = v13 + 8;
        *(_QWORD *)v50 = v13 + 8;
        *(_QWORD *)(v13 + 16) = v50;
        v51 = (char *)this + 128 * v49 + 16 * *(int *)(v13 + 588) + 856;
        *(_QWORD *)(v13 + 24) = *(_QWORD *)v51;
        *(_QWORD *)(*(_QWORD *)v51 + 8LL) = v13 + 24;
        *(_QWORD *)v51 = v13 + 24;
        *(_QWORD *)(v13 + 32) = v51;
        _InterlockedIncrement((volatile signed __int32 *)this + 174);
        v52 = *((_DWORD *)this + 174);
        if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v53 = rand();
          if ( v53 == 5 * (v53 / 5) )
            Spinlock<185,6,257>::UpdateStatSnapshot();
        }
        *v89 = 0;
        v90 = 0;
        v54 = __rdtsc();
        *(_QWORD *)(v13 + 608) = ((unsigned __int64)HIDWORD(v54) << 32) | (unsigned int)v54;
        if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v55 = rand();
          if ( v55 == 5 * (v55 / 5) )
            Spinlock<178,7,258>::UpdateStatSnapshot();
        }
        *v88 = 0;
        if ( (UcsTrace::sm_UcsTraceMask & 0x8000) != 0 )
          traceprint(
            L"SSB TASK: Task %s %p is rescheduled. Scheduled tasks: %i\n",
            (&sx_wsIdempotentTaskNames)[*(int *)(v13 + 584)],
            v13,
            v52);
        goto LABEL_72;
      }
      *(_DWORD *)(v13 + 592) = 1;
      v56 = *(_QWORD *)(v13 + 576);
      v57 = v56 != 0;
      if ( v56 )
      {
        if ( !*(_DWORD *)(v13 + 48) && *(_DWORD *)(v13 + 592) == 1 && (v58 = *(_QWORD *)(v13 + 576)) != 0 )
        {
          *(_QWORD *)(v13 + 568) = v58;
          *(_QWORD *)(v13 + 576) = 0;
        }
        else
        {
          v57 = 0;
        }
      }
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v59 = rand();
        if ( v59 == 5 * (v59 / 5) )
          Spinlock<178,7,258>::UpdateStatSnapshot();
      }
      *v88 = 0;
      if ( v57 )
        (*(void (__fastcall **)(CSbTaskManager *))(*(_QWORD *)this + 8LL))(this);
      if ( (UcsTrace::sm_UcsTraceMask & 0x8000) != 0 )
        traceprint(
          L"SSB TASK: Task %s %p completed. Scheduled tasks: %i\n",
          (&sx_wsIdempotentTaskNames)[*(int *)(v13 + 584)],
          v13,
          *((unsigned int *)this + 174));
LABEL_72:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      if ( (*(unsigned int (__fastcall **)(CSbTaskManager *))(*(_QWORD *)this + 8LL))(this) < 2 )
        return 0;
LABEL_138:
      v60 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v61 = *(_QWORD **)(v60 + 256);
      if ( !v61 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v61 = *(_QWORD **)(v60 + 256);
      }
      v62 = __rdtsc();
      v63 = v61[104];
      if ( v62 <= v63 && (v63 == 0x7FFFFFFFFFFFFFFFLL || v63 - v62 <= *(_QWORD *)(v61[76] + 3568LL)) )
      {
        v64 = v61[75];
        if ( (*(_DWORD *)(v64 + 188) & 4) == 0 )
          goto LABEL_147;
        v65 = *(_QWORD *)(v64 + 152);
        if ( (*(_BYTE *)(v65 + 616) & 1) != 0 )
          goto LABEL_147;
        v66 = (*(_DWORD *)(v65 + 800) & 0x180) == 0;
      }
      else
      {
        v66 = (unsigned int)SOS_Task::Sleep(0, &yieldWait, v61, v31) == 2;
      }
      if ( v66 )
        goto LABEL_181;
LABEL_147:
      v67 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v68 = *(_QWORD *)(v67 + 256);
      if ( !v68 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v68 = *(_QWORD *)(v67 + 256);
      }
      if ( *(_DWORD *)(*(_QWORD *)(v68 + 608) + 5112LL) || v35 )
      {
LABEL_181:
        v3 = 1;
        v9 = a2;
        CSbTaskHandler::Abort(a2);
        v75 = 0;
        v76 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        if ( *(_DWORD *)v87 || _InterlockedCompareExchange64(v87, v76, 0) )
        {
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
          {
            v77 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            if ( v77 && *(_QWORD *)(v77 + 272) == v77 )
              v11 = *(_QWORD *)(v77 + 256);
            if ( v11 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v100);
                v75 = (CSbTransportMgr *)v100.QuadPart;
              }
              else
              {
                v75 = MEMORY[0x7FFE0008];
              }
            }
          }
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<170,8,258>::SpinToAcquireWithExponentialBackoff(v87, v76);
          else
            Spinlock<170,8,258>::SpinToAcquireOptimistic(v87, v11, v76);
          if ( v11 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v101);
              v78 = (CSbTransportMgr *)v101.QuadPart;
            }
            else
            {
              v78 = MEMORY[0x7FFE0008];
            }
            v79 = 0;
            if ( v78 >= v75 )
              v79 = v78 - v75;
            *(_QWORD *)(v11 + 3192) += v79;
          }
        }
        v2 = 0;
        goto LABEL_75;
      }
      if ( (UcsTrace::sm_UcsTraceMask & 0x10000) != 0 && !v91 )
      {
        v69 = 0;
        v70 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        if ( *(_DWORD *)v87 || _InterlockedCompareExchange64(v87, v70, 0) )
        {
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
          {
            v71 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            if ( v71 && *(_QWORD *)(v71 + 272) == v71 )
              v11 = *(_QWORD *)(v71 + 256);
            if ( v11 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v98);
                v69 = (CSbTransportMgr *)v98.QuadPart;
              }
              else
              {
                v69 = MEMORY[0x7FFE0008];
              }
            }
          }
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<170,8,258>::SpinToAcquireWithExponentialBackoff(v87, v70);
          else
            Spinlock<170,8,258>::SpinToAcquireOptimistic(v87, v11, v70);
          if ( v11 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v99);
              v72 = (CSbTransportMgr *)v99.QuadPart;
            }
            else
            {
              v72 = MEMORY[0x7FFE0008];
            }
            v73 = 0;
            if ( v72 >= v69 )
              v73 = v72 - v69;
            *(_QWORD *)(v11 + 3192) += v73;
          }
          v11 = 0;
        }
        if ( *((int *)this + 96) > 1 )
        {
          v2 = 1;
          v9 = a2;
          CSbTaskHandler::Abort(a2);
          v3 = 0;
          goto LABEL_75;
        }
        if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v74 = rand();
          if ( v74 == 5 * (v74 / 5) )
            Spinlock<170,8,258>::UpdateStatSnapshot();
        }
        *v87 = 0;
      }
      v89 = 0;
      v90 = 0;
      v9 = a2;
    }
    v80 = 0;
    v81 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( *(_DWORD *)v87 || _InterlockedCompareExchange64(v87, v81, 0) )
    {
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v82 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( v82 && *(_QWORD *)(v82 + 272) == v82 )
          v11 = *(_QWORD *)(v82 + 256);
        if ( v11 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v102);
            v80 = (CSbTransportMgr *)v102.QuadPart;
          }
          else
          {
            v80 = MEMORY[0x7FFE0008];
          }
        }
      }
      if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
        Spinlock<170,8,258>::SpinToAcquireWithExponentialBackoff(v87, v81);
      else
        Spinlock<170,8,258>::SpinToAcquireOptimistic(v87, v11, v81);
      if ( v11 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v103);
          v83 = (CSbTransportMgr *)v103.QuadPart;
        }
        else
        {
          v83 = MEMORY[0x7FFE0008];
        }
        v84 = 0;
        if ( v83 >= v80 )
          v84 = v83 - v80;
        *(_QWORD *)(v11 + 3192) += v84;
      }
    }
    v85 = v89;
    if ( v89 && v90 )
    {
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v86 = rand();
        if ( v86 == 5 * (v86 / 5) )
          Spinlock<185,6,257>::UpdateStatSnapshot();
      }
      *v85 = 0;
      v89 = 0;
      v90 = 0;
    }
    v2 = 0;
    v3 = 0;
LABEL_75:
    v4 = v91;
    v5 = (char *)this + 16 * v91 + 256;
    *((_QWORD *)v9 + 20) = *((_QWORD *)v5 + 1);
    **((_QWORD **)v5 + 1) = (char *)v9 + 152;
    *((_QWORD *)v5 + 1) = (char *)v9 + 152;
    *((_QWORD *)v9 + 19) = v5;
    --*((_DWORD *)this + v4 + 96);
    v6 = --*((_DWORD *)this + 104);
    v7 = *((_BYTE *)this + 420);
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v8 = rand();
      if ( v8 == 5 * (v8 / 5) )
        Spinlock<170,8,258>::UpdateStatSnapshot();
    }
    *v87 = 0;
    if ( v3 )
    {
      if ( (UcsTrace::sm_UcsTraceMask & 0x8000) != 0 )
        traceprint(L"SSB TASK: Task handler %p aborted. Handlers in use: %i\n", v9, v6);
      SOS_Task::ResetAbort(0x7FFFFFFF);
      CSbTaskManager::KickOffTaskHandler(this, (unsigned int)v4);
      return 0;
    }
    if ( v2 )
    {
      if ( (UcsTrace::sm_UcsTraceMask & 0x8000) != 0 )
        traceprint(L"SSB TASK: Task handler %p stopped due to single task-handler mode. Handlers in use: %i\n", v9, v6);
    }
    else
    {
      if ( !(unsigned __int8)CSbTaskManager::IsTaskQueueEmptyForSpecialization(this, (unsigned int)v4) )
        CSbTaskManager::KickOffTaskHandler(this, (unsigned int)v4);
      if ( !CSbTaskHandler::Stop(v9, v7) )
      {
        if ( (UcsTrace::sm_UcsTraceMask & 0x8000) != 0 )
          traceprint(L"SSB TASK: Task handler %p is rescheduled.\n", v9);
        continue;
      }
      if ( (UcsTrace::sm_UcsTraceMask & 0x8000) != 0 )
        traceprint(L"SSB TASK: Task handler %p stopped. Handlers in use: %i\n", v9, v6);
    }
    return 1;
  }
}

```

## disassembly

```asm
0x100706b20  mov     [rsp-8+arg_8], rdx
0x100706b25  push    rbp
0x100706b26  push    rbx
0x100706b27  push    rsi
0x100706b28  push    rdi
0x100706b29  push    r12
0x100706b2b  push    r13
0x100706b2d  push    r14
0x100706b2f  push    r15
0x100706b31  lea     rbp, [rsp-4E8h]
0x100706b39  sub     rsp, 5E8h
0x100706b40  mov     [rbp+520h+var_550], 0FFFFFFFFFFFFFFFEh
0x100706b48  mov     r13, rdx
0x100706b4b  mov     r15, rcx
0x100706b4e  mov     rax, cs:?sm_UcsTraceMask@UcsTrace@@0_KA; unsigned __int64 UcsTrace::sm_UcsTraceMask
0x100706b55  shr     rax, 0Fh
0x100706b59  test    al, 1
0x100706b5b  jz      short loc_100706B69
0x100706b5d  lea     rcx, aSsbTaskTaskHan_1; "SSB TASK: Task handler %p is starting."...
0x100706b64  call    ?traceprint@@YAXPEB_WZZ; traceprint(wchar_t const *,...)
0x100706b69  mov     r14d, 1
0x100706b6f  xor     edi, edi
0x100706b71  lea     rax, [r15+1A8h]
0x100706b78  mov     [rsp+620h+var_5F0], rax
0x100706b7d  mov     [rsp+620h+var_5E8], edi
0x100706b81  mov     [rbp+520h+arg_10], dil
0x100706b88  mov     [rbp+520h+arg_0], dil
0x100706b8f  mov     eax, [r13+78h]
0x100706b93  mov     [rsp+620h+var_5C0], eax
0x100706b97  mov     [rsp+620h+var_5D0], rdi
0x100706b9c  mov     [rsp+620h+var_5C8], edi
0x100706ba0  lea     r9, [rbp+520h+arg_18]
0x100706ba7  lea     r8, [rsp+620h+var_5D0]
0x100706bac  mov     rdx, r13
0x100706baf  mov     rcx, r15
0x100706bb2  call    ?GetNextScheduledTask@CSbTaskManager@@QEAAPEAVCSbIdempotentTask@@PEAVCSbTaskHandler@@PEAV?$SpinlockHolder@$0LJ@$05$0BAB@@@AEAH@Z; CSbTaskManager::GetNextScheduledTask(CSbTaskHandler *,SpinlockHolder<185,6,257> *,int &)
0x100706bb7  test    rax, rax
0x100706bba  mov     rsi, rax
0x100706bbd  jz      loc_10086D4BF
0x100706bc3  mov     ecx, 3
0x100706bc8  xchg    ecx, [rsi+250h]
0x100706bce  mov     rcx, [rax+10h]
0x100706bd2  mov     rax, [rax+8]
0x100706bd6  mov     [rax+8], rcx
0x100706bda  mov     [rcx], rax
0x100706bdd  mov     [rsi+10h], rdi
0x100706be1  mov     [rsi+8], rdi
0x100706be5  mov     rcx, [rsi+20h]
0x100706be9  mov     rax, [rsi+18h]
0x100706bed  mov     [rax+8], rcx
0x100706bf1  mov     [rcx], rax
0x100706bf4  mov     [rsi+20h], rdi
0x100706bf8  mov     [rsi+18h], rdi
0x100706bfc  lock dec dword ptr [r15+2B8h]
0x100706c04  mov     ecx, [r15+2C8h]
0x100706c0b  mov     eax, [r15+2B8h]
0x100706c12  cmp     ecx, eax
0x100706c14  jge     loc_10086CCAA
0x100706c1a  mov     eax, [r15+2C8h]
0x100706c21  jmp     short loc_100706C24
0x100706c24  mov     [r15+2C8h], eax
0x100706c2b  mov     r12d, [r15+2B8h]
0x100706c32  mov     ecx, r14d
0x100706c35  lock xadd [r15+2BCh], ecx
0x100706c3e  inc     ecx
0x100706c40  lock inc dword ptr [r15+2D0h]
0x100706c48  mov     eax, [r15+2C4h]
0x100706c4f  cmp     eax, ecx
0x100706c51  jle     short loc_100706C5A
0x100706c53  mov     ecx, [r15+2C4h]
0x100706c5a  mov     [r15+2C4h], ecx
0x100706c61  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x100706c68  cmp     byte ptr [rax], 0
0x100706c6b  jz      short loc_100706C94
0x100706c6d  call    cs:__imp_rand
0x100706c73  mov     r8d, eax
0x100706c76  mov     eax, 66666667h
0x100706c7b  imul    r8d
0x100706c7e  sar     edx, 1
0x100706c80  mov     ecx, edx
0x100706c82  shr     ecx, 1Fh
0x100706c85  add     edx, ecx
0x100706c87  lea     ecx, [rdx+rdx*4]
0x100706c8a  cmp     r8d, ecx
0x100706c8d  jnz     short loc_100706C94
0x100706c8f  call    ?UpdateStatSnapshot@?$Spinlock@$0LJ@$05$0BAB@@@AEAAXXZ; Spinlock<185,6,257>::UpdateStatSnapshot(void)
0x100706c94  mov     rax, [rsp+620h+var_5D0]
0x100706c99  mov     [rax], rdi
0x100706c9c  mov     [rsp+620h+var_5C8], edi
0x100706ca0  lea     rax, [rsi+28h]
0x100706ca4  mov     [rsp+620h+var_5E0], rax
0x100706ca9  mov     [rsp+620h+var_5D8], edi
0x100706cad  mov     rbx, rdi
0x100706cb0  mov     eax, gs:48h
0x100706cb8  mov     r14d, eax
0x100706cbb  mov     rax, [rsp+620h+var_5E0]
0x100706cc0  mov     ecx, [rax]
0x100706cc2  test    ecx, ecx
0x100706cc4  jnz     short loc_100706CDF
0x100706cc6  mov     rcx, [rsp+620h+var_5E0]
0x100706ccb  xor     eax, eax
0x100706ccd  lock cmpxchg [rcx], r14
0x100706cd2  mov     eax, edi
0x100706cd4  setz    al
0x100706cd7  test    eax, eax
0x100706cd9  jnz     loc_100706DB4
0x100706cdf  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100706ce6  mov     ecx, [rax]
0x100706ce8  and     ecx, 84h
0x100706cee  cmp     cl, 84h
0x100706cf1  jnz     short loc_100706D4D
0x100706cf3  mov     rdx, gs:58h
0x100706cfc  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100706d03  mov     ecx, [rax]
0x100706d05  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100706d0c  mov     r8d, [rax]
0x100706d0f  add     r8, [rdx+rcx*8]
0x100706d13  jz      short loc_100706D25
0x100706d15  cmp     [r8+110h], r8
0x100706d1c  jnz     short loc_100706D25
0x100706d1e  mov     rdi, [r8+100h]
0x100706d25  test    rdi, rdi
0x100706d28  jz      short loc_100706D4D
0x100706d2a  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100706d31  cmp     dword ptr [rax], 0
0x100706d34  jz      loc_10086CCB7
0x100706d3a  lea     rcx, [rsp+620h+PerformanceCount]; lpPerformanceCount
0x100706d3f  call    cs:__imp_QueryPerformanceCounter
0x100706d45  mov     rbx, qword ptr [rsp+620h+PerformanceCount]
0x100706d4a  jmp     short loc_100706D4D
0x100706d4d  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100706d54  mov     rcx, [rsp+620h+var_5E0]
0x100706d59  cmp     byte ptr [rax+0C7h], 0
0x100706d60  jge     loc_10086CCC5
0x100706d66  mov     r8, r14
0x100706d69  mov     rdx, rdi
0x100706d6c  call    ?SpinToAcquireOptimistic@?$Spinlock@$0LC@$06$0BAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<178,7,258>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100706d71  jmp     short loc_100706D74
0x100706d74  test    rdi, rdi
0x100706d77  jz      short loc_100706DB2
0x100706d79  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100706d80  cmp     dword ptr [rax], 0
0x100706d83  jz      loc_10086CCD4
0x100706d89  lea     rcx, [rsp+620h+var_5A8]; lpPerformanceCount
0x100706d8e  call    cs:__imp_QueryPerformanceCounter
0x100706d94  mov     rcx, qword ptr [rsp+620h+var_5A8]
0x100706d99  jmp     short loc_100706D9C
0x100706d9c  mov     rdx, rcx
0x100706d9f  sub     rdx, rbx
0x100706da2  xor     eax, eax
0x100706da4  cmp     rcx, rbx
0x100706da7  cmovnb  rax, rdx
0x100706dab  add     [rdi+0C78h], rax
0x100706db2  xor     edi, edi
0x100706db4  mov     ecx, 1
0x100706db9  mov     [rsp+620h+var_5D8], ecx
0x100706dbd  cmp     [rsi+238h], r15
0x100706dc4  jz      short loc_100706DEA
0x100706dc6  mov     [rsp+620h+var_600], rdi
0x100706dcb  mov     r9d, 802h
0x100706dd1  lea     r8, aUcstaskCpp; "ucstask.cpp"
0x100706dd8  lea     rdx, aPitskMPtaskmgr; "pitsk->m_pTaskMgr == this"
0x100706ddf  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100706de5  mov     ecx, 1
0x100706dea  mov     eax, [rsi+250h]
0x100706df0  cmp     eax, 3
0x100706df3  jz      short loc_100706E1F
0x100706df5  mov     eax, [rsi+250h]
0x100706dfb  cmp     eax, 4
0x100706dfe  jz      short loc_100706E1F
0x100706e00  mov     [rsp+620h+var_600], rdi
0x100706e05  mov     r9d, 803h
0x100706e0b  lea     r8, aUcstaskCpp; "ucstask.cpp"
0x100706e12  lea     rdx, aCsbidempotentt; "CSbIdempotentTask::x_Idempotent_Running"...
0x100706e19  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100706e1f  lea     rbx, [rsi+34h]
0x100706e23  mov     edi, [rsi+234h]
0x100706e29  mov     r14d, [rsi+250h]
0x100706e30  mov     [rsi+258h], r13
0x100706e37  rdtsc
0x100706e39  shl     rdx, 20h
0x100706e3d  or      rax, rdx
0x100706e40  sub     rax, [rsi+260h]
0x100706e47  lock xadd [rsi+270h], rax
0x100706e50  rdtsc
0x100706e52  shl     rdx, 20h
0x100706e56  or      rax, rdx
0x100706e59  mov     [rsi+268h], rax
0x100706e60  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x100706e67  cmp     byte ptr [rax], 0
0x100706e6a  jz      short loc_100706E93
0x100706e6c  call    cs:__imp_rand
0x100706e72  mov     r8d, eax
0x100706e75  mov     eax, 66666667h
0x100706e7a  imul    r8d
0x100706e7d  sar     edx, 1
0x100706e7f  mov     ecx, edx
0x100706e81  shr     ecx, 1Fh
0x100706e84  add     edx, ecx
0x100706e86  lea     ecx, [rdx+rdx*4]
0x100706e89  cmp     r8d, ecx
0x100706e8c  jnz     short loc_100706E93
0x100706e8e  call    ?UpdateStatSnapshot@?$Spinlock@$0LC@$06$0BAC@@@AEAAXXZ; Spinlock<178,7,258>::UpdateStatSnapshot(void)
0x100706e93  mov     rax, [rsp+620h+var_5E0]
0x100706e98  xor     ecx, ecx
0x100706e9a  mov     [rax], rcx
0x100706e9d  mov     [rsp+620h+var_5D8], ecx
0x100706ea1  test    byte ptr cs:?g_XeUcsPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$0CL@@@@@A, 4; XBitmap<StaticStorage<43>> g_XeUcsPkg_enabledBitmap
0x100706ea8  jz      loc_100706F2E
0x100706eae  mov     [rbp+520h+var_538], 20000h
0x100706eb5  mov     [rbp+520h+var_530], ecx
0x100706eb8  lea     rax, [rbp+520h+var_510]
0x100706ebc  mov     [rbp+520h+var_528], rax
0x100706ec0  lea     rax, [rbp+520h+var_4F0]
0x100706ec4  mov     [rbp+520h+var_520], rax
0x100706ec8  mov     [rbp+520h+var_2F0], rcx
0x100706ecf  mov     [rbp+520h+var_518], rcx
0x100706ed3  mov     [rbp+520h+var_2E8], rcx
0x100706eda  lea     rax, [rbp+520h+var_2E0]
0x100706ee1  mov     [rbp+520h+var_510], rax
0x100706ee5  mov     [rbp+520h+var_508], 1Ch
0x100706eec  mov     edx, 1
0x100706ef1  mov     [rbp+520h+var_504], edx
0x100706ef4  mov     [rbp+520h+var_2E0], rsi
0x100706efb  mov     eax, [rsi+248h]
0x100706f01  mov     [rbp+520h+var_2D8], eax
0x100706f07  mov     [rbp+520h+var_500], rbx
0x100706f0b  lea     eax, [rdi+rdi]
0x100706f0e  mov     [rbp+520h+var_4F8], eax
0x100706f11  mov     [rbp+520h+var_4F4], 4
0x100706f18  mov     [rbp+520h+var_2D4], edx
0x100706f1e  mov     [rbp+520h+var_2D0], r14d
0x100706f25  lea     rcx, [rbp+520h+var_540]; this
0x100706f29  call    ?Publish@ucs_task_idempotent@XeUcsPkg@@QEAAXXZ; XeUcsPkg::ucs_task_idempotent::Publish(void)
0x100706f2e  mov     rax, cs:?sm_UcsTraceMask@UcsTrace@@0_KA; unsigned __int64 UcsTrace::sm_UcsTraceMask
0x100706f35  shr     rax, 0Fh
0x100706f39  test    al, 1
0x100706f3b  jz      short loc_100706F61
0x100706f3d  movsxd  rdx, dword ptr [rsi+248h]
0x100706f44  mov     r9d, r12d
0x100706f47  mov     r8, rsi
0x100706f4a  lea     rax, ?sx_wsIdempotentTaskNames@@3PAPEA_WA; wchar_t * near * sx_wsIdempotentTaskNames
0x100706f51  mov     rdx, [rax+rdx*8]
0x100706f55  lea     rcx, aSsbTaskIdempot; "SSB TASK: Idempotent task %s %p is invo"...
0x100706f5c  call    ?traceprint@@YAXPEB_WZZ; traceprint(wchar_t const *,...)
0x100706f61  mov     rax, [rsi]
0x100706f64  mov     rcx, rsi
0x100706f67  call    qword ptr [rax]
0x100706f69  mov     r13, rax
0x100706f6c  rdtsc
0x100706f6e  shl     rdx, 20h
0x100706f72  or      rax, rdx
0x100706f75  sub     rax, [rsi+268h]
0x100706f7c  lock xadd [rsi+278h], rax
0x100706f85  test    byte ptr cs:?g_XeUcsPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$0CL@@@@@A, 4; XBitmap<StaticStorage<43>> g_XeUcsPkg_enabledBitmap
0x100706f8c  jz      loc_10086CCE2
0x100706f92  xor     ecx, ecx
0x100706f94  mov     [rbp+520h+var_2B8], 20000h
0x100706f9e  lea     edx, [rcx+2]
0x100706fa1  mov     [rbp+520h+var_2B0], ecx
0x100706fa7  lea     rax, [rbp+520h+var_290]
0x100706fae  mov     [rbp+520h+var_2A8], rax
0x100706fb5  lea     rax, [rbp+520h+var_270]
0x100706fbc  mov     [rbp+520h+var_2A0], rax
0x100706fc3  mov     [rbp+520h+var_70], rcx
0x100706fca  mov     [rbp+520h+var_298], rcx
0x100706fd1  mov     [rbp+520h+var_68], rcx
0x100706fd8  lea     rax, [rbp+520h+var_60]
0x100706fdf  mov     [rbp+520h+var_290], rax
0x100706fe6  mov     [rbp+520h+var_288], 1Ch
0x100706ff0  mov     [rbp+520h+var_284], 1
0x100706ffa  mov     [rbp+520h+var_60], rsi
0x100707001  mov     eax, [rsi+248h]
0x100707007  mov     [rbp+520h+var_58], eax
0x10070700d  mov     [rbp+520h+var_280], rbx
0x100707014  lea     eax, [rdi+rdi]
0x100707017  mov     [rbp+520h+var_278], eax
0x10070701d  mov     [rbp+520h+var_274], 4
0x100707027  xor     edi, edi
0x100707029  mov     [rbp+520h+var_54], edx
0x10070702f  mov     [rbp+520h+var_50], r14d
0x100707036  lea     rcx, [rbp+520h+var_2C0]; this
0x10070703d  call    ?Publish@ucs_task_idempotent@XeUcsPkg@@QEAAXXZ; XeUcsPkg::ucs_task_idempotent::Publish(void)
0x100707042  jmp     short loc_100707045
0x100707045  lock dec dword ptr [r15+2BCh]
0x10070704d  mov     eax, [r15+2CCh]
0x100707054  cmp     eax, 0FFFFFFFFh
0x100707057  jnz     loc_10086CCEA
0x10070705d  mov     eax, [r15+2BCh]
0x100707064  jmp     short loc_100707067
0x100707067  mov     [r15+2CCh], eax
0x10070706e  xor     r12b, r12b
0x100707071  test    r13, r13
0x100707074  jz      loc_10086D0AE
0x10070707a  mov     rbx, rdi
0x10070707d  mov     eax, gs:48h
0x100707085  mov     r14d, eax
0x100707088  mov     rax, [rsp+620h+var_5E0]
0x10070708d  mov     ecx, [rax]
0x10070708f  test    ecx, ecx
  ... truncated ...
```
