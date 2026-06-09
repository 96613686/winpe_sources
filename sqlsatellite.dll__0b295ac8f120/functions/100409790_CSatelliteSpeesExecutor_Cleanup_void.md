# CSatelliteSpeesExecutor::Cleanup(void)

- ea: `0x100409790`
- end: `0x10040a09b`
- name: `?Cleanup@CSatelliteSpeesExecutor@@UEAAJXZ`
- size: `2315`
- prototype: `__int64 __fastcall(CSatelliteSpeesExecutor *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x100403270`
- `0x100409790`
- `0x10040c0e0`
- `0x10040c7a0`
- `0x10040c9e0`
- `0x10040cc90`
- `0x10040ce80`
- `0x10040d0c0`
- `0x10040d370`
- `0x10040d490`
- `0x10041bc90`
- `0x1004737e0`
- `0x100475640`
- `0x100478670`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100409a33`
- `KERNEL32!QueryPerformanceCounter` at `0x100409a86`
- `KERNEL32!QueryPerformanceCounter` at `0x100409d3c`
- `KERNEL32!QueryPerformanceCounter` at `0x100409d90`
- `KERNEL32!QueryPerformanceCounter` at `0x100409a33`
- `KERNEL32!QueryPerformanceCounter` at `0x100409a86`
- `KERNEL32!QueryPerformanceCounter` at `0x100409d3c`
- `KERNEL32!QueryPerformanceCounter` at `0x100409d90`
- `KERNEL32!VirtualProtect` at `0x100409e1f`
- `KERNEL32!VirtualProtect` at `0x100409e1f`
- `KERNEL32!VirtualFree` at `0x100409f74`
- `KERNEL32!VirtualFree` at `0x100409f74`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100409adf`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100409ed4`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100409f10`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x100409f52`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100409a23`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100409a75`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100409d2c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100409d7f`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100409a48`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100409d51`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x100409c11`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x100409c11`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100409be8`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100409c9b`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100409fe6`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100409be8`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100409c9b`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100409fe6`
- `sqldk!?WaitForDone@SOS_Task@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z` at `0x100409950`
- `sqldk!?WaitForDone@SOS_Task@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z` at `0x100409950`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x100409833`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x100409833`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100409ff4`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100409ff4`
- `sqldk!SystemThread_TlsIndex` at `0x1004098cd`
- `sqldk!SystemThread_TlsIndex` at `0x1004099f5`
- `sqldk!SystemThread_TlsIndex` at `0x100409b25`
- `sqldk!SystemThread_TlsIndex` at `0x100409cfe`
- `sqldk!SystemThread_TlsOffset` at `0x1004098d6`
- `sqldk!SystemThread_TlsOffset` at `0x1004099fe`
- `sqldk!SystemThread_TlsOffset` at `0x100409b2e`
- `sqldk!SystemThread_TlsOffset` at `0x100409d07`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004098f8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004098f8`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004099d8`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100409bad`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100409c64`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100409ce1`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100409faf`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100409aeb`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100409ee0`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100409f1c`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100409aeb`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100409ee0`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100409f1c`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CSatelliteSpeesExecutor::Cleanup(CSatelliteSpeesExecutor *this)
{
  __int64 v2; // r14
  unsigned int v3; // edi
  __int64 v4; // rax
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rbx
  __int64 v8; // rdx
  int v9; // ecx
  __int64 *v10; // rdi
  volatile signed __int64 *v11; // r15
  LARGE_INTEGER v12; // rbx
  signed __int64 UniqueThread_low; // r12
  __int64 v14; // r8
  LARGE_INTEGER v15; // rax
  LONGLONG v16; // rcx
  _QWORD *v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // r8
  __int64 v21; // rax
  __int64 *v22; // rdi
  _QWORD *v23; // rdi
  __int64 v24; // rbx
  SOS_Node *v25; // rcx
  __int64 v26; // r14
  __int64 *v27; // rax
  __int64 v28; // rbx
  __int64 *v29; // rsi
  __int64 v30; // rdi
  __int64 v31; // r14
  LARGE_INTEGER v32; // rbx
  signed __int64 v33; // r12
  __int64 v34; // r8
  __int64 v35; // rcx
  LARGE_INTEGER v36; // rax
  LONGLONG v37; // rcx
  __int64 *v38; // rcx
  unsigned __int64 v39; // rax
  SOS_ObjectStore *v40; // rcx
  unsigned int PoolIdForObject; // eax
  char v42; // r9
  __int64 v43; // r8
  __int64 v44; // r10
  _QWORD *v45; // rdx
  __int64 v46; // rcx
  int v47; // eax
  int v48; // eax
  __int64 *v49; // rcx
  __int64 *v50; // rdi
  __int64 v51; // rbx
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp-C0h] BYREF
  LARGE_INTEGER v54; // [rsp+48h] [rbp-B8h] BYREF
  LARGE_INTEGER v55; // [rsp+50h] [rbp-B0h] BYREF
  LARGE_INTEGER v56; // [rsp+58h] [rbp-A8h] BYREF
  int v57; // [rsp+60h] [rbp-A0h]
  __int64 v58; // [rsp+68h] [rbp-98h]
  int v59; // [rsp+70h] [rbp-90h] BYREF
  __int64 v60; // [rsp+78h] [rbp-88h]
  __int64 v61; // [rsp+80h] [rbp-80h]
  __int64 v62; // [rsp+88h] [rbp-78h]
  __int64 v63; // [rsp+90h] [rbp-70h]
  int v64; // [rsp+98h] [rbp-68h] BYREF
  __int64 v65; // [rsp+A0h] [rbp-60h]
  __int64 v66; // [rsp+A8h] [rbp-58h]
  __int64 v67; // [rsp+B0h] [rbp-50h]
  __int64 v68; // [rsp+B8h] [rbp-48h]
  __int64 v69; // [rsp+C0h] [rbp-40h]
  _BYTE v70[8]; // [rsp+D0h] [rbp-30h] BYREF
  int v71; // [rsp+D8h] [rbp-28h]
  int v72; // [rsp+E0h] [rbp-20h]
  _QWORD *v73; // [rsp+E8h] [rbp-18h]
  char *v74; // [rsp+F0h] [rbp-10h]
  __int64 v75; // [rsp+F8h] [rbp-8h]
  _QWORD v76[2]; // [rsp+100h] [rbp+0h] BYREF
  char v77; // [rsp+110h] [rbp+10h] BYREF
  __int64 v78; // [rsp+320h] [rbp+220h]
  __int64 v79; // [rsp+328h] [rbp+228h]
  _QWORD v80[2]; // [rsp+330h] [rbp+230h] BYREF
  unsigned int v81; // [rsp+340h] [rbp+240h]
  unsigned int v82; // [rsp+3A0h] [rbp+2A0h]
  DWORD flOldProtect; // [rsp+3B0h] [rbp+2B0h] BYREF
  __int64 v84; // [rsp+3B8h] [rbp+2B8h]

  v69 = -2;
  v2 = 0;
  v3 = 0;
  v82 = 0;
  v4 = *((_QWORD *)this + 258);
  if ( v4 && !*(_BYTE *)(v4 + 57) )
  {
    if ( !*(_BYTE *)(*((_QWORD *)this + 259) + 3377LL) )
    {
      v5 = *((_QWORD *)this + 259);
      v59 = 4195479;
      v60 = 0;
      v62 = 0;
      v61 = 0;
      v63 = 0;
      if ( (unsigned int)WaitableBase::Wait(*(_QWORD *)(v5 + 3320), 0xFFFFFFFFLL, &v59, 0, 1) )
        v3 = -2147467260;
      v82 = v3;
      if ( *(_BYTE *)(*((_QWORD *)this + 259) + 3378LL) )
      {
        v6 = CSQLSatelliteCommunication::SendAckMessage(*((_QWORD *)this + 258), (char *)this + 3136, 4);
        if ( v6 < 0 )
        {
          _mm_lfence();
          FireTraceEvent(1, (unsigned int)v6, (char *)this + 3136, L"SendAckMessage failed.");
        }
      }
    }
    if ( !*(_BYTE *)(*((_QWORD *)this + 258) + 57LL) )
      CSQLSatelliteConnection::AbortConnection(
        *((CSQLSatelliteConnection **)this + 258),
        L"Tear down connection at SQLSatellite_CleanUp\n");
  }
  if ( *((_QWORD *)this + 262) )
  {
    v57 = 0;
    v7 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v8 = *(_QWORD *)(v7 + 256);
    v84 = v8;
    if ( !v8 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v8 = *(_QWORD *)(v7 + 256);
      v84 = v8;
    }
    v58 = v8;
    v9 = *(_DWORD *)(v8 + 616);
    v57 = !(*(_BYTE *)(v8 + 616) & 1);
    *(_DWORD *)(v8 + 616) = v9 | 1;
    v64 = 4195486;
    v65 = 0;
    v67 = 0;
    v66 = 0;
    v68 = 0;
    SOS_Task::WaitForDone(*((_QWORD *)this + 262), 0xFFFFFFFFLL, &v64);
    v10 = (__int64 *)*((_QWORD *)this + 262);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 10, 0xFFFFFFFF) == 1 )
    {
      if ( v10[3] )
      {
        TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy();
      }
      else
      {
        if ( *((_DWORD *)v10 + 46) == 2 )
        {
          v11 = (volatile signed __int64 *)(v10[20] + 4952);
          v12.QuadPart = 0;
          UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
          if ( *(_DWORD *)v11 || _InterlockedCompareExchange64(v11, UniqueThread_low, 0) )
          {
            if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
            {
              v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset;
              if ( v14 && *(_QWORD *)(v14 + 272) == v14 )
                v2 = *(_QWORD *)(v14 + 256);
              if ( v2 )
              {
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&PerformanceCount);
                  v12 = PerformanceCount;
                }
                else
                {
                  v12.QuadPart = MEMORY[0x7FFE0008];
                }
              }
            }
            if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
              Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v11, UniqueThread_low);
            else
              Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v11, v2, UniqueThread_low);
            if ( v2 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v54);
                v15 = v54;
              }
              else
              {
                v15.QuadPart = MEMORY[0x7FFE0008];
              }
              v16 = v15.QuadPart - v12.QuadPart;
              if ( v15.QuadPart < (unsigned __int64)v12.QuadPart )
                v16 = 0;
              *(_QWORD *)(v2 + 3192) += v16;
            }
          }
          v17 = (_QWORD *)v10[1];
          v18 = *v10;
          *(_QWORD *)(v18 + 8) = v17;
          *v17 = v18;
          v10[1] = 0;
          *v10 = 0;
          if ( v11 )
          {
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v19 = rand();
              if ( v19 == 5 * (v19 / 5) )
                Spinlock<11,2,268435714>::UpdateStatSnapshot();
            }
            *v11 = 0;
          }
        }
        v20 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( v20
          && *(_QWORD *)(v20 + 272) == v20
          && (v21 = *(_QWORD *)(v20 + 256)) != 0
          && *(__int64 **)(v21 + 528) == v10 )
        {
          if ( v10 )
            v22 = v10 - 1;
          else
            v22 = 0;
          *v22 = (__int64)&ISOSHost_TaskImpl::`vftable';
          v23 = v22 + 1;
          v24 = v23[22];
          if ( v24 )
          {
            if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
            {
              _InterlockedDecrement((volatile signed __int32 *)(v24 + 112));
              v24 = v23[22];
            }
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v24 + 24), 0xFFFFFFFF) == 1 )
            {
              if ( *(_QWORD *)(v24 + 8) )
                TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*(_QWORD *)(v24 + 16), v24);
              SOSHost::Destroy((SOSHost *)v24);
            }
          }
        }
        else
        {
          v25 = (SOS_Node *)v10[21];
          if ( v25 && *((_QWORD *)v25 + 30) && !SOS_Node::IsTaskStoreDisabled(v25) )
          {
            v26 = *(_QWORD *)(v10[21] + 240);
            v27 = v10 - 1;
            if ( !v10 )
              v27 = 0;
            *v27 = (__int64)&ISOSHost_TaskImpl::`vftable';
            v28 = v27[23];
            if ( v28 )
            {
              if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
              {
                _InterlockedDecrement((volatile signed __int32 *)(v28 + 112));
                v28 = v27[23];
              }
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v28 + 24), 0xFFFFFFFF) == 1 )
              {
                if ( *(_QWORD *)(v28 + 8) )
                  TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*(_QWORD *)(v28 + 16), v28);
                SOSHost::Destroy((SOSHost *)v28);
              }
            }
            v29 = v10 - 1;
            if ( !v10 )
              v29 = 0;
            v30 = *(_QWORD *)(v26 + 2016);
            v31 = 0;
            v32.QuadPart = 0;
            v33 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
            if ( *(_DWORD *)(v30 + 40) || _InterlockedCompareExchange64((volatile signed __int64 *)(v30 + 40), v33, 0) )
            {
              if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
              {
                v34 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                    + SystemThread_TlsOffset;
                if ( v34 && *(_QWORD *)(v34 + 272) == v34 )
                  v31 = *(_QWORD *)(v34 + 256);
                if ( v31 )
                {
                  if ( Base_PublicGlobals::sm_invariantTscAvailable )
                  {
                    QueryPerformanceCounter(&v55);
                    v32 = v55;
                  }
                  else
                  {
                    v32.QuadPart = MEMORY[0x7FFE0008];
                  }
                }
              }
              v35 = v30 + 40;
              if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
                Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v35, v33);
              else
                Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v35, v31, v33);
              if ( v31 )
              {
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&v56);
                  v36 = v56;
                }
                else
                {
                  v36.QuadPart = MEMORY[0x7FFE0008];
                }
                v37 = v36.QuadPart - v32.QuadPart;
                if ( v36.QuadPart < (unsigned __int64)v32.QuadPart )
                  v37 = 0;
                *(_QWORD *)(v31 + 3192) += v37;
              }
            }
            if ( *(_QWORD *)(v30 + 8) >= *(_QWORD *)v30 )
            {
              if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
              {
                v48 = rand();
                if ( v48 == 5 * (v48 / 5) )
                  Spinlock<34,1,268435714>::UpdateStatSnapshot();
              }
              *(_QWORD *)(v30 + 40) = 0;
              (*(void (__fastcall **)(__int64 *))(v30 + 48))(v29);
            }
            else
            {
              if ( *(_BYTE *)(*(_QWORD *)(v30 + 32) + 5820LL) )
              {
                v38 = (__int64 *)(v30 + 16 * ((*(_DWORD *)(v30 + 1176) & 0x3F) + 9LL));
                *v29 = *v38;
                if ( !*v38 )
                  v38[1] = (__int64)v29;
                *v38 = (__int64)v29;
                ++*(_QWORD *)(v30 + 1176);
                VirtualProtect(v29, 0x1000u, 1u, &flOldProtect);
              }
              else
              {
                *v29 = *(_QWORD *)(v30 + 128);
                if ( !*(_QWORD *)(v30 + 128) )
                  *(_QWORD *)(v30 + 136) = v29;
                *(_QWORD *)(v30 + 128) = v29;
              }
              v39 = *(_QWORD *)(v30 + 1168) + 1LL;
              ++*(_QWORD *)(v30 + 8);
              v40 = *(SOS_ObjectStore **)(v30 + 32);
              if ( !*((_BYTE *)v40 + 5820) && v39 >= 0x20 )
              {
                PoolIdForObject = SOS_ObjectStore::GetPoolIdForObject(v40, (struct SList *)v29);
                v42 = PoolIdForObject;
                v43 = v30 + 8LL * PoolIdForObject;
                v44 = *(_QWORD *)(v30 + 128);
                v45 = *(_QWORD **)(v30 + 136);
                if ( v45 != (_QWORD *)(v30 + 128) && v45 )
                {
                  *v45 = *(_QWORD *)(v43 + 1184);
                  *(_QWORD *)(v43 + 1184) = v44;
                }
                *(_QWORD *)(v30 + 128) = 0;
                *(_QWORD *)(v30 + 136) = v30 + 128;
                v39 = 0;
                v46 = *(_QWORD *)(v30 + 1696);
                if ( (v46 & (1LL << v42)) == 0 )
                  *(_QWORD *)(v30 + 1696) = (1LL << v42) | v46;
              }
              *(_QWORD *)(v30 + 1168) = v39;
              if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
              {
                v47 = rand();
                if ( v47 == 5 * (v47 / 5) )
                  Spinlock<34,1,268435714>::UpdateStatSnapshot();
              }
              *(_QWORD *)(v30 + 40) = 0;
            }
          }
          else if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
          {
            v49 = v10 - 1;
            if ( !v10 )
              v49 = 0;
            VirtualFree(v49, 0, 0x8000u);
          }
          else if ( v10 )
          {
            v50 = v10 - 1;
            if ( v50 )
            {
              *v50 = (__int64)&ISOSHost_TaskImpl::`vftable';
              v51 = v50[23];
              if ( v51 )
              {
                if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
                {
                  _InterlockedDecrement((volatile signed __int32 *)(v51 + 112));
                  v51 = v50[23];
                }
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v51 + 24), 0xFFFFFFFF) == 1 )
                {
                  if ( *(_QWORD *)(v51 + 8) )
                    TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*(_QWORD *)(v51 + 16), v51);
                  SOSHost::Destroy((SOSHost *)v51);
                }
              }
              operator delete(v50, 0x3E0u);
            }
          }
        }
      }
    }
    *(_DWORD *)(v84 + 616) &= ~v57;
    v3 = v82;
  }
  if ( g_XeSQLSatellitePkg_enabledBitmap < 0 )
  {
    v71 = 0x10000;
    v72 = 0;
    v73 = v76;
    v74 = &v77;
    v78 = 0;
    v75 = 0;
    v79 = 0;
    v76[0] = v80;
    v76[1] = 20;
    v80[0] = *((_QWORD *)this + 258);
    v80[1] = this;
    v81 = v3;
    XeSQLSatellitePkg::satellite_cleanup::Publish((XeSQLSatellitePkg::satellite_cleanup *)v70);
  }
  return v3;
}

```

## disassembly

```asm
0x100409790  push    rbp
0x100409792  push    rbx
0x100409793  push    rsi
0x100409794  push    rdi
0x100409795  push    r12
0x100409797  push    r13
0x100409799  push    r14
0x10040979b  push    r15
0x10040979d  lea     rbp, [rsp-258h]
0x1004097a5  sub     rsp, 358h
0x1004097ac  mov     [rbp+290h+var_2D0], 0FFFFFFFFFFFFFFFEh
0x1004097b4  mov     r13, rcx
0x1004097b7  xor     r14d, r14d
0x1004097ba  mov     edi, r14d
0x1004097bd  mov     [rbp+290h+arg_0], r14d
0x1004097c4  mov     rax, [rcx+810h]
0x1004097cb  lea     esi, [r14+1]
0x1004097cf  test    rax, rax
0x1004097d2  jz      loc_1004098B2
0x1004097d8  movzx   eax, byte ptr [rax+39h]
0x1004097dc  test    al, al
0x1004097de  jnz     loc_1004098B2
0x1004097e4  mov     rax, [rcx+818h]
0x1004097eb  movzx   eax, byte ptr [rax+0D31h]
0x1004097f2  test    al, al
0x1004097f4  jnz     loc_100409890
0x1004097fa  mov     rcx, [rcx+818h]
0x100409801  mov     [rsp+390h+var_320], 400497h
0x100409809  mov     [rsp+390h+var_318], r14
0x10040980e  mov     [rbp+290h+var_308], r14
0x100409812  mov     [rbp+290h+var_310], r14
0x100409816  mov     [rbp+290h+var_300], r14
0x10040981a  mov     [rsp+390h+var_370], sil
0x10040981f  xor     r9d, r9d
0x100409822  lea     r8, [rsp+390h+var_320]
0x100409827  mov     edx, 0FFFFFFFFh
0x10040982c  mov     rcx, [rcx+0CF8h]
0x100409833  call    cs:__imp_?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z; WaitableBase::Wait(ulong,SOS_WaitInfo const *,SOS_SYNC_WAIT_OPTIONS,bool)
0x100409839  mov     ecx, 80004004h
0x10040983e  test    eax, eax
0x100409840  cmovnz  edi, ecx
0x100409843  mov     [rbp+290h+arg_0], edi
0x100409849  mov     rax, [r13+818h]
0x100409850  movzx   eax, byte ptr [rax+0D32h]
0x100409857  test    al, al
0x100409859  jz      short loc_100409890
0x10040985b  lea     r8d, [r14+4]
0x10040985f  lea     rdx, [r13+0C40h]
0x100409866  mov     rcx, [r13+810h]
0x10040986d  call    ?SendAckMessage@CSQLSatelliteCommunication@@SAJPEAVCSQLSatelliteConnection@@PEBU_GUID@@W4ESQLSatelliteMessageType@@@Z; CSQLSatelliteCommunication::SendAckMessage(CSQLSatelliteConnection *,_GUID const *,ESQLSatelliteMessageType)
0x100409872  test    eax, eax
0x100409874  jns     short loc_100409890
0x100409876  lfence
0x100409879  lea     r9, aSendackmessage; "SendAckMessage failed."
0x100409880  lea     r8, [r13+0C40h]
0x100409887  mov     edx, eax
0x100409889  mov     ecx, esi
0x10040988b  call    ?FireTraceEvent@@YAXW4ExtensibilityTraceLevel@@JPEBU_GUID@@PEB_WZZ; FireTraceEvent(ExtensibilityTraceLevel,long,_GUID const *,wchar_t const *,...)
0x100409890  mov     rax, [r13+810h]
0x100409897  movzx   eax, byte ptr [rax+39h]
0x10040989b  test    al, al
0x10040989d  jnz     short loc_1004098B2
0x10040989f  lea     rdx, aTearDownConnec; "Tear down connection at SQLSatellite_Cl"...
0x1004098a6  mov     rcx, [r13+810h]; this
0x1004098ad  call    ?AbortConnection@CSQLSatelliteConnection@@QEAAXPEB_WZZ; CSQLSatelliteConnection::AbortConnection(wchar_t const *,...)
0x1004098b2  cmp     [r13+830h], r14
0x1004098b9  jz      loc_10040A014
0x1004098bf  mov     [rsp+390h+var_330], r14d
0x1004098c4  mov     rdx, gs:58h
0x1004098cd  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004098d4  mov     ecx, [rax]
0x1004098d6  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004098dd  mov     ebx, [rax]
0x1004098df  add     rbx, [rdx+rcx*8]
0x1004098e3  mov     rdx, [rbx+100h]
0x1004098ea  mov     [rbp+290h+arg_18], rdx
0x1004098f1  test    rdx, rdx
0x1004098f4  jnz     short loc_10040990C
0x1004098f6  xor     ecx, ecx
0x1004098f8  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004098fe  mov     rdx, [rbx+100h]
0x100409905  mov     [rbp+290h+arg_18], rdx
0x10040990c  mov     [rsp+390h+var_328], rdx
0x100409911  mov     ecx, [rdx+268h]
0x100409917  mov     eax, ecx
0x100409919  and     eax, esi
0x10040991b  xor     eax, esi
0x10040991d  mov     [rsp+390h+var_330], eax
0x100409921  or      ecx, esi
0x100409923  mov     [rdx+268h], ecx
0x100409929  mov     [rbp+290h+var_2F8], 40049Eh
0x100409930  mov     [rbp+290h+var_2F0], r14
0x100409934  mov     [rbp+290h+var_2E0], r14
0x100409938  mov     [rbp+290h+var_2E8], r14
0x10040993c  mov     [rbp+290h+var_2D8], r14
0x100409940  lea     r8, [rbp+290h+var_2F8]
0x100409944  mov     edx, 0FFFFFFFFh
0x100409949  mov     rcx, [r13+830h]
0x100409950  call    cs:__imp_?WaitForDone@SOS_Task@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z; SOS_Task::WaitForDone(ulong,SOS_WaitInfo const *)
0x100409956  mov     rdi, [r13+830h]
0x10040995d  lea     rcx, [rdi+10h]
0x100409961  mov     esi, 0FFFFFFFFh
0x100409966  mov     eax, esi
0x100409968  lock xadd [rcx+18h], eax
0x10040996d  cmp     eax, 1
0x100409970  jnz     loc_100409FFB
0x100409976  cmp     qword ptr [rcx+8], 0
0x10040997b  jz      short loc_100409987
0x10040997d  call    ?RemoveAndDestroy@?$TListElem@V?$TList@VSOS_Scheduler@@VSOS_Task@@$0BA@UTListSLock@@@@@@IEAAXXZ; TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(void)
0x100409982  jmp     loc_100409FFB
0x100409987  mov     eax, [rdi+0B8h]
0x10040998d  cmp     eax, 2
0x100409990  jnz     loc_100409B1C
0x100409996  mov     r15, [rdi+0A0h]
0x10040999d  add     r15, 1358h
0x1004099a4  mov     [rsp+390h+var_360], r15
0x1004099a9  mov     [rsp+390h+var_358], r14d
0x1004099ae  mov     rbx, r14
0x1004099b1  mov     eax, gs:48h
0x1004099b9  mov     r12d, eax
0x1004099bc  mov     eax, [r15]
0x1004099bf  test    eax, eax
0x1004099c1  jnz     short loc_1004099D8
0x1004099c3  xor     eax, eax
0x1004099c5  lock cmpxchg [r15], r12
0x1004099ca  mov     eax, r14d
0x1004099cd  setz    al
0x1004099d0  test    eax, eax
0x1004099d2  jnz     loc_100409AB8
0x1004099d8  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004099df  mov     ecx, [rax]
0x1004099e1  and     ecx, 84h
0x1004099e7  cmp     cl, 84h
0x1004099ea  jnz     short loc_100409A48
0x1004099ec  mov     rdx, gs:58h
0x1004099f5  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004099fc  mov     ecx, [rax]
0x1004099fe  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100409a05  mov     r8d, [rax]
0x100409a08  add     r8, [rdx+rcx*8]
0x100409a0c  jz      short loc_100409A1E
0x100409a0e  cmp     [r8+110h], r8
0x100409a15  jnz     short loc_100409A1E
0x100409a17  mov     r14, [r8+100h]
0x100409a1e  test    r14, r14
0x100409a21  jz      short loc_100409A48
0x100409a23  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100409a2a  cmp     [rax], ebx
0x100409a2c  jz      short loc_100409A40
0x100409a2e  lea     rcx, [rsp+390h+PerformanceCount]; lpPerformanceCount
0x100409a33  call    cs:__imp_QueryPerformanceCounter
0x100409a39  mov     rbx, qword ptr [rsp+390h+PerformanceCount]
0x100409a3e  jmp     short loc_100409A48
0x100409a40  mov     rbx, ds:7FFE0008h
0x100409a48  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100409a4f  mov     rcx, r15
0x100409a52  cmp     byte ptr [rax+0C7h], 0
0x100409a59  jge     short loc_100409A68
0x100409a5b  mov     r8, r12
0x100409a5e  mov     rdx, r14
0x100409a61  call    ?SpinToAcquireOptimistic@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<11,2,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100409a66  jmp     short loc_100409A70
0x100409a68  mov     rdx, r12
0x100409a6b  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAX_K@Z; Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100409a70  test    r14, r14
0x100409a73  jz      short loc_100409AB5
0x100409a75  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100409a7c  cmp     dword ptr [rax], 0
0x100409a7f  jz      short loc_100409A93
0x100409a81  lea     rcx, [rsp+390h+var_348]; lpPerformanceCount
0x100409a86  call    cs:__imp_QueryPerformanceCounter
0x100409a8c  mov     rax, qword ptr [rsp+390h+var_348]
0x100409a91  jmp     short loc_100409A9B
0x100409a93  mov     rax, ds:7FFE0008h
0x100409a9b  mov     rcx, rax
0x100409a9e  sub     rcx, rbx
0x100409aa1  cmp     rax, rbx
0x100409aa4  mov     r12d, 0
0x100409aaa  cmovb   rcx, r12
0x100409aae  add     [r14+0C78h], rcx
0x100409ab5  xor     r14d, r14d
0x100409ab8  mov     [rsp+390h+var_358], 1
0x100409ac0  mov     rcx, [rdi+8]
0x100409ac4  mov     rax, [rdi]
0x100409ac7  mov     [rax+8], rcx
0x100409acb  mov     [rcx], rax
0x100409ace  mov     [rdi+8], r14
0x100409ad2  mov     [rdi], r14
0x100409ad5  mov     rbx, [rsp+390h+var_360]
0x100409ada  test    rbx, rbx
0x100409add  jz      short loc_100409B1C
0x100409adf  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x100409ae6  cmp     byte ptr [rax], 0
0x100409ae9  jz      short loc_100409B0F
0x100409aeb  call    cs:__imp_rand
0x100409af1  mov     ecx, eax
0x100409af3  mov     eax, 66666667h
0x100409af8  imul    ecx
0x100409afa  sar     edx, 1
0x100409afc  mov     eax, edx
0x100409afe  shr     eax, 1Fh
0x100409b01  add     edx, eax
0x100409b03  lea     eax, [rdx+rdx*4]
0x100409b06  cmp     ecx, eax
0x100409b08  jnz     short loc_100409B0F
0x100409b0a  call    ?UpdateStatSnapshot@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXXZ; Spinlock<11,2,268435714>::UpdateStatSnapshot(void)
0x100409b0f  mov     [rbx], r14
0x100409b12  mov     [rsp+390h+var_360], r14
0x100409b17  mov     [rsp+390h+var_358], r14d
0x100409b1c  mov     rdx, gs:58h
0x100409b25  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100409b2c  mov     ecx, [rax]
0x100409b2e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100409b35  mov     r8d, [rax]
0x100409b38  add     r8, [rdx+rcx*8]
0x100409b3c  jz      loc_100409BF3
0x100409b42  cmp     [r8+110h], r8
0x100409b49  jnz     loc_100409BF3
0x100409b4f  mov     rax, [r8+100h]
0x100409b56  test    rax, rax
0x100409b59  jz      loc_100409BF3
0x100409b5f  cmp     [rax+210h], rdi
0x100409b66  jnz     loc_100409BF3
0x100409b6c  test    rdi, rdi
0x100409b6f  jz      short loc_100409B7E
0x100409b71  add     rdi, 0FFFFFFFFFFFFFFF8h
0x100409b75  mov     [rbp+290h+arg_8], rdi
0x100409b7c  jmp     short loc_100409B88
0x100409b7e  mov     rdi, r14
0x100409b81  mov     [rbp+290h+arg_8], r14
0x100409b88  lea     rcx, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x100409b8f  mov     [rdi], rcx
0x100409b92  add     rdi, 8
0x100409b96  mov     [rbp+290h+arg_8], rdi
0x100409b9d  mov     rbx, [rdi+0B0h]
0x100409ba4  test    rbx, rbx
0x100409ba7  jz      loc_100409FFB
0x100409bad  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100409bb4  test    byte ptr [rax], 8
0x100409bb7  jz      short loc_100409BC4
0x100409bb9  lock dec dword ptr [rbx+70h]
0x100409bbd  mov     rbx, [rdi+0B0h]
0x100409bc4  lock xadd [rbx+18h], esi
0x100409bc9  cmp     esi, 1
0x100409bcc  jnz     loc_100409FFB
0x100409bd2  cmp     qword ptr [rbx+8], 0
0x100409bd7  jz      short loc_100409BE5
0x100409bd9  mov     rdx, rbx
0x100409bdc  mov     rcx, [rbx+10h]
0x100409be0  call    ?RemoveElem@?$TList@VCertificateHashList@@VCertificateHash@@$0A@UTListSLock@@@@QEAAXPEAVCertificateHash@@@Z; TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(CertificateHash *)
0x100409be5  mov     rcx, rbx
0x100409be8  call    cs:__imp_?Destroy@SOSHost@@AEAAXXZ; SOSHost::Destroy(void)
0x100409bee  jmp     loc_100409FFB
0x100409bf3  mov     rcx, [rdi+0A8h]
0x100409bfa  test    rcx, rcx
0x100409bfd  jz      loc_100409F52
0x100409c03  cmp     qword ptr [rcx+0F0h], 0
0x100409c0b  jz      loc_100409F52
0x100409c11  call    cs:__imp_?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ; SOS_Node::IsTaskStoreDisabled(void)
0x100409c17  test    al, al
0x100409c19  jnz     loc_100409F52
0x100409c1f  mov     rax, [rdi+0A8h]
0x100409c26  mov     r14, [rax+0F0h]
0x100409c2d  xor     r12d, r12d
0x100409c30  test    rdi, rdi
0x100409c33  lea     rax, [rdi-8]
0x100409c37  jnz     short loc_100409C3C
0x100409c39  mov     eax, r12d
0x100409c3c  mov     [rbp+290h+arg_8], rax
0x100409c43  lea     rcx, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x100409c4a  mov     [rax], rcx
0x100409c4d  lea     rcx, [rax+8]
0x100409c51  mov     [rbp+290h+arg_8], rcx
0x100409c58  mov     rbx, [rcx+0B0h]
0x100409c5f  test    rbx, rbx
0x100409c62  jz      short loc_100409CA1
0x100409c64  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100409c6b  test    byte ptr [rax], 8
0x100409c6e  jz      short loc_100409C7B
0x100409c70  lock dec dword ptr [rbx+70h]
0x100409c74  mov     rbx, [rcx+0B0h]
0x100409c7b  lock xadd [rbx+18h], esi
0x100409c80  cmp     esi, 1
0x100409c83  jnz     short loc_100409CA1
0x100409c85  cmp     qword ptr [rbx+8], 0
0x100409c8a  jz      short loc_100409C98
0x100409c8c  mov     rdx, rbx
0x100409c8f  mov     rcx, [rbx+10h]
0x100409c93  call    ?RemoveElem@?$TList@VCertificateHashList@@VCertificateHash@@$0A@UTListSLock@@@@QEAAXPEAVCertificateHash@@@Z; TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(CertificateHash *)
0x100409c98  mov     rcx, rbx
0x100409c9b  call    cs:__imp_?Destroy@SOSHost@@AEAAXXZ; SOSHost::Destroy(void)
0x100409ca1  lea     rsi, [rdi-8]
0x100409ca5  test    rdi, rdi
0x100409ca8  cmovz   rsi, r12
0x100409cac  mov     rdi, [r14+7E0h]
0x100409cb3  xor     r14d, r14d
0x100409cb6  mov     ebx, r14d
0x100409cb9  mov     eax, gs:48h
0x100409cc1  mov     r12d, eax
0x100409cc4  mov     eax, [rdi+28h]
  ... truncated ...
```
