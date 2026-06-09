# SatellitePacketList::ReleasePacketProcessorTask(void)

- ea: `0x1004704c0`
- end: `0x100470c13`
- name: `?ReleasePacketProcessorTask@SatellitePacketList@@QEAAXXZ`
- size: `1875`
- prototype: `void __fastcall(SatellitePacketList *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x10046ffe0`

## callees

- `0x100403270`
- `0x10040c0e0`
- `0x10040c7a0`
- `0x10040c9e0`
- `0x10040cc90`
- `0x10040ce80`
- `0x10040d0c0`
- `0x10040d370`
- `0x10040d490`
- `0x10040d680`
- `0x1004704c0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100470667`
- `KERNEL32!QueryPerformanceCounter` at `0x1004706b8`
- `KERNEL32!QueryPerformanceCounter` at `0x100470942`
- `KERNEL32!QueryPerformanceCounter` at `0x100470994`
- `KERNEL32!QueryPerformanceCounter` at `0x100470667`
- `KERNEL32!QueryPerformanceCounter` at `0x1004706b8`
- `KERNEL32!QueryPerformanceCounter` at `0x100470942`
- `KERNEL32!QueryPerformanceCounter` at `0x100470994`
- `KERNEL32!VirtualProtect` at `0x100470a18`
- `KERNEL32!VirtualProtect` at `0x100470a18`
- `KERNEL32!VirtualFree` at `0x100470b6d`
- `KERNEL32!VirtualFree` at `0x100470b6d`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100470705`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100470acd`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100470b09`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x100470b4b`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100470658`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004706a8`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100470933`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100470984`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10047067b`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100470956`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x100470820`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x100470820`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x1004707f7`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x1004708a3`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100470bdb`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x1004707f7`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x1004708a3`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100470bdb`
- `sqldk!?WaitForDone@SOS_Task@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z` at `0x100470585`
- `sqldk!?WaitForDone@SOS_Task@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z` at `0x100470585`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100470be9`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100470be9`
- `sqldk!SystemThread_TlsIndex` at `0x10047050a`
- `sqldk!SystemThread_TlsIndex` at `0x10047062a`
- `sqldk!SystemThread_TlsIndex` at `0x100470748`
- `sqldk!SystemThread_TlsIndex` at `0x100470905`
- `sqldk!SystemThread_TlsOffset` at `0x100470513`
- `sqldk!SystemThread_TlsOffset` at `0x100470633`
- `sqldk!SystemThread_TlsOffset` at `0x100470751`
- `sqldk!SystemThread_TlsOffset` at `0x10047090e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100470532`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100470532`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10047060a`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004707ba`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10047086a`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004708e5`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100470ba2`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100470711`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100470ad9`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100470b15`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100470711`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100470ad9`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100470b15`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall SatellitePacketList::ReleasePacketProcessorTask(SatellitePacketList *this)
{
  __int64 *v2; // rdi
  __int64 v3; // rbx
  __int64 v4; // rdx
  int v5; // ecx
  __int64 *v6; // rsi
  volatile signed __int64 *v7; // r12
  LARGE_INTEGER v8; // rbx
  signed __int64 UniqueThread_low; // r13
  __int64 v10; // r15
  __int64 v11; // r8
  LARGE_INTEGER v12; // rax
  LONGLONG v13; // rcx
  _QWORD *v14; // rcx
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // r8
  __int64 v18; // rax
  _QWORD *v19; // rdi
  __int64 v20; // rbx
  SOS_Node *v21; // rcx
  __int64 v22; // r15
  __int64 *v23; // rcx
  _QWORD *v24; // rcx
  __int64 v25; // rbx
  __int64 *v26; // r14
  __int64 v27; // rsi
  LARGE_INTEGER v28; // rbx
  signed __int64 v29; // r13
  __int64 v30; // r15
  __int64 v31; // r8
  __int64 v32; // rcx
  LARGE_INTEGER v33; // rax
  LONGLONG v34; // rcx
  __int64 *v35; // rcx
  unsigned __int64 v36; // rax
  SOS_ObjectStore *v37; // rcx
  unsigned int PoolIdForObject; // eax
  char v39; // r10
  __int64 v40; // r8
  __int64 v41; // r9
  _QWORD *v42; // rdx
  __int64 v43; // rcx
  int v44; // r8d
  int v45; // r8d
  __int64 *v46; // rcx
  __int64 *v47; // rsi
  __int64 v48; // rbx
  LARGE_INTEGER v49; // [rsp+30h] [rbp-49h] BYREF
  LARGE_INTEGER v50; // [rsp+38h] [rbp-41h] BYREF
  LARGE_INTEGER v51; // [rsp+40h] [rbp-39h] BYREF
  int v52; // [rsp+48h] [rbp-31h]
  __int64 v53; // [rsp+50h] [rbp-29h]
  int v54; // [rsp+58h] [rbp-21h] BYREF
  __int64 v55; // [rsp+60h] [rbp-19h]
  __int64 v56; // [rsp+68h] [rbp-11h]
  __int64 v57; // [rsp+70h] [rbp-9h]
  __int64 v58; // [rsp+78h] [rbp-1h]
  __int64 v59; // [rsp+80h] [rbp+7h]
  DWORD flOldProtect; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 v61; // [rsp+F0h] [rbp+77h]
  LARGE_INTEGER PerformanceCount; // [rsp+F8h] [rbp+7Fh] BYREF

  v59 = -2;
  if ( *((_QWORD *)this + 12) )
  {
    *((_BYTE *)this + 88) = 1;
    EventAutoInternal<SuspendQueueSLock>::SignalAll((char *)this + 32);
    v2 = 0;
    v52 = 0;
    v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v4 = *(_QWORD *)(v3 + 256);
    v61 = v4;
    if ( !v4 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v4 = *(_QWORD *)(v3 + 256);
      v61 = v4;
    }
    v53 = v4;
    v5 = *(_DWORD *)(v4 + 616);
    v52 = !(*(_BYTE *)(v4 + 616) & 1);
    *(_DWORD *)(v4 + 616) = v5 | 1;
    v54 = 4195486;
    v55 = 0;
    v57 = 0;
    v56 = 0;
    v58 = 0;
    SOS_Task::WaitForDone(*((_QWORD *)this + 12), 0xFFFFFFFFLL, &v54);
    v6 = (__int64 *)*((_QWORD *)this + 12);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6 + 10, 0xFFFFFFFF) == 1 )
    {
      if ( v6[3] )
      {
        TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy();
      }
      else
      {
        if ( *((_DWORD *)v6 + 46) == 2 )
        {
          v7 = (volatile signed __int64 *)(v6[20] + 4952);
          v8.QuadPart = 0;
          UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
          if ( *(_DWORD *)v7 || _InterlockedCompareExchange64(v7, UniqueThread_low, 0) )
          {
            v10 = 0;
            if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
            {
              v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset;
              if ( v11 && *(_QWORD *)(v11 + 272) == v11 )
                v10 = *(_QWORD *)(v11 + 256);
              if ( v10 )
              {
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&PerformanceCount);
                  v8 = PerformanceCount;
                }
                else
                {
                  v8.QuadPart = MEMORY[0x7FFE0008];
                }
              }
            }
            if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
              Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v7, UniqueThread_low);
            else
              Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v7, v10, UniqueThread_low);
            if ( v10 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v49);
                v12 = v49;
              }
              else
              {
                v12.QuadPart = MEMORY[0x7FFE0008];
              }
              v13 = v12.QuadPart - v8.QuadPart;
              if ( v12.QuadPart < (unsigned __int64)v8.QuadPart )
                v13 = 0;
              *(_QWORD *)(v10 + 3192) += v13;
            }
          }
          v14 = (_QWORD *)v6[1];
          v15 = *v6;
          *(_QWORD *)(v15 + 8) = v14;
          *v14 = v15;
          v6[1] = 0;
          *v6 = 0;
          if ( v7 )
          {
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v16 = rand();
              if ( v16 == 5 * (v16 / 5) )
                Spinlock<11,2,268435714>::UpdateStatSnapshot();
            }
            *v7 = 0;
          }
        }
        v17 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( v17
          && *(_QWORD *)(v17 + 272) == v17
          && (v18 = *(_QWORD *)(v17 + 256)) != 0
          && *(__int64 **)(v18 + 528) == v6 )
        {
          if ( v6 )
            v2 = v6 - 1;
          *v2 = (__int64)&ISOSHost_TaskImpl::`vftable';
          v19 = v2 + 1;
          v20 = v19[22];
          if ( v20 )
          {
            if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
            {
              _InterlockedDecrement((volatile signed __int32 *)(v20 + 112));
              v20 = v19[22];
            }
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v20 + 24), 0xFFFFFFFF) == 1 )
            {
              if ( *(_QWORD *)(v20 + 8) )
                TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*(_QWORD *)(v20 + 16), v20);
              SOSHost::Destroy((SOSHost *)v20);
            }
          }
        }
        else
        {
          v21 = (SOS_Node *)v6[21];
          if ( v21 && *((_QWORD *)v21 + 30) && !SOS_Node::IsTaskStoreDisabled(v21) )
          {
            v22 = *(_QWORD *)(v6[21] + 240);
            v23 = v6 - 1;
            if ( !v6 )
              v23 = 0;
            *v23 = (__int64)&ISOSHost_TaskImpl::`vftable';
            v24 = v23 + 1;
            v25 = v24[22];
            if ( v25 )
            {
              if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
              {
                _InterlockedDecrement((volatile signed __int32 *)(v25 + 112));
                v25 = v24[22];
              }
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v25 + 24), 0xFFFFFFFF) == 1 )
              {
                if ( *(_QWORD *)(v25 + 8) )
                  TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*(_QWORD *)(v25 + 16), v25);
                SOSHost::Destroy((SOSHost *)v25);
              }
            }
            v26 = v6 - 1;
            if ( !v6 )
              v26 = 0;
            v27 = *(_QWORD *)(v22 + 2016);
            v28.QuadPart = 0;
            v29 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
            if ( *(_DWORD *)(v27 + 40) || _InterlockedCompareExchange64((volatile signed __int64 *)(v27 + 40), v29, 0) )
            {
              v30 = 0;
              if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
              {
                v31 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                    + SystemThread_TlsOffset;
                if ( v31 && *(_QWORD *)(v31 + 272) == v31 )
                  v30 = *(_QWORD *)(v31 + 256);
                if ( v30 )
                {
                  if ( Base_PublicGlobals::sm_invariantTscAvailable )
                  {
                    QueryPerformanceCounter(&v50);
                    v28 = v50;
                  }
                  else
                  {
                    v28.QuadPart = MEMORY[0x7FFE0008];
                  }
                }
              }
              v32 = v27 + 40;
              if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
                Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v32, v29);
              else
                Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v32, v30, v29);
              if ( v30 )
              {
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&v51);
                  v33 = v51;
                }
                else
                {
                  v33.QuadPart = MEMORY[0x7FFE0008];
                }
                v34 = v33.QuadPart - v28.QuadPart;
                if ( v33.QuadPart < (unsigned __int64)v28.QuadPart )
                  v34 = 0;
                *(_QWORD *)(v30 + 3192) += v34;
              }
            }
            if ( *(_QWORD *)(v27 + 8) >= *(_QWORD *)v27 )
            {
              if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
              {
                v45 = rand();
                if ( v45 == 5 * (v45 / 5) )
                  Spinlock<34,1,268435714>::UpdateStatSnapshot();
              }
              *(_QWORD *)(v27 + 40) = 0;
              (*(void (__fastcall **)(__int64 *))(v27 + 48))(v26);
            }
            else
            {
              if ( *(_BYTE *)(*(_QWORD *)(v27 + 32) + 5820LL) )
              {
                v35 = (__int64 *)(v27 + 16 * ((*(_DWORD *)(v27 + 1176) & 0x3F) + 9LL));
                *v26 = *v35;
                if ( !*v35 )
                  v35[1] = (__int64)v26;
                *v35 = (__int64)v26;
                ++*(_QWORD *)(v27 + 1176);
                VirtualProtect(v26, 0x1000u, 1u, &flOldProtect);
              }
              else
              {
                *v26 = *(_QWORD *)(v27 + 128);
                if ( !*(_QWORD *)(v27 + 128) )
                  *(_QWORD *)(v27 + 136) = v26;
                *(_QWORD *)(v27 + 128) = v26;
              }
              v36 = *(_QWORD *)(v27 + 1168) + 1LL;
              ++*(_QWORD *)(v27 + 8);
              v37 = *(SOS_ObjectStore **)(v27 + 32);
              if ( !*((_BYTE *)v37 + 5820) && v36 >= 0x20 )
              {
                PoolIdForObject = SOS_ObjectStore::GetPoolIdForObject(v37, (struct SList *)v26);
                v39 = PoolIdForObject;
                v40 = v27 + 8LL * PoolIdForObject;
                v41 = *(_QWORD *)(v27 + 128);
                v42 = *(_QWORD **)(v27 + 136);
                if ( v42 != (_QWORD *)(v27 + 128) && v42 )
                {
                  *v42 = *(_QWORD *)(v40 + 1184);
                  *(_QWORD *)(v40 + 1184) = v41;
                }
                *(_QWORD *)(v27 + 128) = 0;
                *(_QWORD *)(v27 + 136) = v27 + 128;
                v36 = 0;
                v43 = *(_QWORD *)(v27 + 1696);
                if ( (v43 & (1LL << v39)) == 0 )
                  *(_QWORD *)(v27 + 1696) = (1LL << v39) | v43;
              }
              *(_QWORD *)(v27 + 1168) = v36;
              if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
              {
                v44 = rand();
                if ( v44 == 5 * (v44 / 5) )
                  Spinlock<34,1,268435714>::UpdateStatSnapshot();
              }
              *(_QWORD *)(v27 + 40) = 0;
            }
          }
          else if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
          {
            v46 = v6 - 1;
            if ( !v6 )
              v46 = 0;
            VirtualFree(v46, 0, 0x8000u);
          }
          else if ( v6 )
          {
            v47 = v6 - 1;
            if ( v47 )
            {
              *v47 = (__int64)&ISOSHost_TaskImpl::`vftable';
              v48 = v47[23];
              if ( v48 )
              {
                if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
                {
                  _InterlockedDecrement((volatile signed __int32 *)(v48 + 112));
                  v48 = v47[23];
                }
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v48 + 24), 0xFFFFFFFF) == 1 )
                {
                  if ( *(_QWORD *)(v48 + 8) )
                    TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*(_QWORD *)(v48 + 16), v48);
                  SOSHost::Destroy((SOSHost *)v48);
                }
              }
              operator delete(v47, 0x3E0u);
            }
          }
        }
      }
    }
    *(_DWORD *)(v61 + 616) &= ~v52;
  }
}

```

## disassembly

```asm
0x1004704c0  push    rbp
0x1004704c2  push    rbx
0x1004704c3  push    rsi
0x1004704c4  push    rdi
0x1004704c5  push    r12
0x1004704c7  push    r13
0x1004704c9  push    r14
0x1004704cb  push    r15
0x1004704cd  lea     rbp, [rsp-1Fh]
0x1004704d2  sub     rsp, 98h
0x1004704d9  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x1004704e1  mov     rsi, rcx
0x1004704e4  cmp     qword ptr [rcx+60h], 0
0x1004704e9  jz      loc_100470BFF
0x1004704ef  mov     byte ptr [rcx+58h], 1
0x1004704f3  add     rcx, 20h ; ' '
0x1004704f7  call    ?SignalAll@?$EventAutoInternal@USuspendQueueSLock@@@@QEAAXXZ; EventAutoInternal<SuspendQueueSLock>::SignalAll(void)
0x1004704fc  xor     edi, edi
0x1004704fe  mov     [rbp+57h+var_88], edi
0x100470501  mov     r8, gs:58h
0x10047050a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100470511  mov     edx, [rax]
0x100470513  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10047051a  mov     ebx, [rax]
0x10047051c  add     rbx, [r8+rdx*8]
0x100470520  mov     rdx, [rbx+100h]
0x100470527  mov     [rbp+57h+arg_10], rdx
0x10047052b  test    rdx, rdx
0x10047052e  jnz     short loc_100470543
0x100470530  xor     ecx, ecx
0x100470532  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100470538  mov     rdx, [rbx+100h]
0x10047053f  mov     [rbp+57h+arg_10], rdx
0x100470543  mov     [rbp+57h+var_80], rdx
0x100470547  mov     ecx, [rdx+268h]
0x10047054d  mov     eax, ecx
0x10047054f  and     eax, 1
0x100470552  xor     eax, 1
0x100470555  mov     [rbp+57h+var_88], eax
0x100470558  or      ecx, 1
0x10047055b  mov     [rdx+268h], ecx
0x100470561  mov     [rbp+57h+var_78], 40049Eh
0x100470568  mov     [rbp+57h+var_70], rdi
0x10047056c  mov     [rbp+57h+var_60], rdi
0x100470570  mov     [rbp+57h+var_68], rdi
0x100470574  mov     [rbp+57h+var_58], rdi
0x100470578  lea     r8, [rbp+57h+var_78]
0x10047057c  mov     edx, 0FFFFFFFFh
0x100470581  mov     rcx, [rsi+60h]
0x100470585  call    cs:__imp_?WaitForDone@SOS_Task@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z; SOS_Task::WaitForDone(ulong,SOS_WaitInfo const *)
0x10047058b  mov     rsi, [rsi+60h]
0x10047058f  lea     rcx, [rsi+10h]
0x100470593  mov     r14d, 0FFFFFFFFh
0x100470599  mov     eax, r14d
0x10047059c  lock xadd [rcx+18h], eax
0x1004705a1  cmp     eax, 1
0x1004705a4  jnz     loc_100470BF0
0x1004705aa  cmp     qword ptr [rcx+8], 0
0x1004705af  jz      short loc_1004705BB
0x1004705b1  call    ?RemoveAndDestroy@?$TListElem@V?$TList@VSOS_Scheduler@@VSOS_Task@@$0BA@UTListSLock@@@@@@IEAAXXZ; TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(void)
0x1004705b6  jmp     loc_100470BF0
0x1004705bb  mov     eax, [rsi+0B8h]
0x1004705c1  cmp     eax, 2
0x1004705c4  jnz     loc_10047073F
0x1004705ca  mov     r12, [rsi+0A0h]
0x1004705d1  add     r12, 1358h
0x1004705d8  mov     [rbp+57h+var_B0], r12
0x1004705dc  mov     [rbp+57h+var_A8], edi
0x1004705df  mov     rbx, rdi
0x1004705e2  mov     eax, gs:48h
0x1004705ea  mov     r13d, eax
0x1004705ed  mov     eax, [r12]
0x1004705f1  test    eax, eax
0x1004705f3  jnz     short loc_10047060A
0x1004705f5  xor     eax, eax
0x1004705f7  lock cmpxchg [r12], r13
0x1004705fd  mov     eax, edi
0x1004705ff  setz    al
0x100470602  test    eax, eax
0x100470604  jnz     loc_1004706E0
0x10047060a  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100470611  mov     ecx, [rax]
0x100470613  and     ecx, 84h
0x100470619  mov     r15, rdi
0x10047061c  cmp     cl, 84h
0x10047061f  jnz     short loc_10047067B
0x100470621  mov     rdx, gs:58h
0x10047062a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100470631  mov     ecx, [rax]
0x100470633  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10047063a  mov     r8d, [rax]
0x10047063d  add     r8, [rdx+rcx*8]
0x100470641  jz      short loc_100470653
0x100470643  cmp     [r8+110h], r8
0x10047064a  jnz     short loc_100470653
0x10047064c  mov     r15, [r8+100h]
0x100470653  test    r15, r15
0x100470656  jz      short loc_10047067B
0x100470658  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10047065f  cmp     [rax], ebx
0x100470661  jz      short loc_100470673
0x100470663  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x100470667  call    cs:__imp_QueryPerformanceCounter
0x10047066d  mov     rbx, qword ptr [rbp+57h+PerformanceCount]
0x100470671  jmp     short loc_10047067B
0x100470673  mov     rbx, ds:7FFE0008h
0x10047067b  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100470682  mov     rcx, r12
0x100470685  cmp     byte ptr [rax+0C7h], 0
0x10047068c  jge     short loc_10047069B
0x10047068e  mov     r8, r13
0x100470691  mov     rdx, r15
0x100470694  call    ?SpinToAcquireOptimistic@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<11,2,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100470699  jmp     short loc_1004706A3
0x10047069b  mov     rdx, r13
0x10047069e  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAX_K@Z; Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x1004706a3  test    r15, r15
0x1004706a6  jz      short loc_1004706E0
0x1004706a8  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004706af  cmp     dword ptr [rax], 0
0x1004706b2  jz      short loc_1004706C4
0x1004706b4  lea     rcx, [rbp+57h+var_A0]; lpPerformanceCount
0x1004706b8  call    cs:__imp_QueryPerformanceCounter
0x1004706be  mov     rax, qword ptr [rbp+57h+var_A0]
0x1004706c2  jmp     short loc_1004706CC
0x1004706c4  mov     rax, ds:7FFE0008h
0x1004706cc  mov     rcx, rax
0x1004706cf  sub     rcx, rbx
0x1004706d2  cmp     rax, rbx
0x1004706d5  cmovb   rcx, rdi
0x1004706d9  add     [r15+0C78h], rcx
0x1004706e0  mov     [rbp+57h+var_A8], 1
0x1004706e7  mov     rcx, [rsi+8]
0x1004706eb  mov     rax, [rsi]
0x1004706ee  mov     [rax+8], rcx
0x1004706f2  mov     [rcx], rax
0x1004706f5  mov     [rsi+8], rdi
0x1004706f9  mov     [rsi], rdi
0x1004706fc  mov     rbx, [rbp+57h+var_B0]
0x100470700  test    rbx, rbx
0x100470703  jz      short loc_10047073F
0x100470705  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10047070c  cmp     byte ptr [rax], 0
0x10047070f  jz      short loc_100470735
0x100470711  call    cs:__imp_rand
0x100470717  mov     ecx, eax
0x100470719  mov     eax, 66666667h
0x10047071e  imul    ecx
0x100470720  sar     edx, 1
0x100470722  mov     eax, edx
0x100470724  shr     eax, 1Fh
0x100470727  add     edx, eax
0x100470729  lea     eax, [rdx+rdx*4]
0x10047072c  cmp     ecx, eax
0x10047072e  jnz     short loc_100470735
0x100470730  call    ?UpdateStatSnapshot@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXXZ; Spinlock<11,2,268435714>::UpdateStatSnapshot(void)
0x100470735  mov     [rbx], rdi
0x100470738  mov     [rbp+57h+var_B0], rdi
0x10047073c  mov     [rbp+57h+var_A8], edi
0x10047073f  mov     rdx, gs:58h
0x100470748  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10047074f  mov     ecx, [rax]
0x100470751  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100470758  mov     r8d, [rax]
0x10047075b  add     r8, [rdx+rcx*8]
0x10047075f  jz      loc_100470802
0x100470765  cmp     [r8+110h], r8
0x10047076c  jnz     loc_100470802
0x100470772  mov     rax, [r8+100h]
0x100470779  test    rax, rax
0x10047077c  jz      loc_100470802
0x100470782  cmp     [rax+210h], rsi
0x100470789  jnz     short loc_100470802
0x10047078b  test    rsi, rsi
0x10047078e  jz      short loc_100470794
0x100470790  lea     rdi, [rsi-8]
0x100470794  mov     [rbp+57h+arg_0], rdi
0x100470798  lea     rax, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x10047079f  mov     [rdi], rax
0x1004707a2  add     rdi, 8
0x1004707a6  mov     [rbp+57h+arg_0], rdi
0x1004707aa  mov     rbx, [rdi+0B0h]
0x1004707b1  test    rbx, rbx
0x1004707b4  jz      loc_100470BF0
0x1004707ba  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004707c1  test    byte ptr [rax], 8
0x1004707c4  jz      short loc_1004707D1
0x1004707c6  lock dec dword ptr [rbx+70h]
0x1004707ca  mov     rbx, [rdi+0B0h]
0x1004707d1  lock xadd [rbx+18h], r14d
0x1004707d7  cmp     r14d, 1
0x1004707db  jnz     loc_100470BF0
0x1004707e1  cmp     qword ptr [rbx+8], 0
0x1004707e6  jz      short loc_1004707F4
0x1004707e8  mov     rdx, rbx
0x1004707eb  mov     rcx, [rbx+10h]
0x1004707ef  call    ?RemoveElem@?$TList@VCertificateHashList@@VCertificateHash@@$0A@UTListSLock@@@@QEAAXPEAVCertificateHash@@@Z; TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(CertificateHash *)
0x1004707f4  mov     rcx, rbx
0x1004707f7  call    cs:__imp_?Destroy@SOSHost@@AEAAXXZ; SOSHost::Destroy(void)
0x1004707fd  jmp     loc_100470BF0
0x100470802  mov     rcx, [rsi+0A8h]
0x100470809  test    rcx, rcx
0x10047080c  jz      loc_100470B4B
0x100470812  cmp     qword ptr [rcx+0F0h], 0
0x10047081a  jz      loc_100470B4B
0x100470820  call    cs:__imp_?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ; SOS_Node::IsTaskStoreDisabled(void)
0x100470826  test    al, al
0x100470828  jnz     loc_100470B4B
0x10047082e  mov     rax, [rsi+0A8h]
0x100470835  mov     r15, [rax+0F0h]
0x10047083c  test    rsi, rsi
0x10047083f  lea     rcx, [rsi-8]
0x100470843  jnz     short loc_100470848
0x100470845  mov     rcx, rdi
0x100470848  mov     [rbp+57h+arg_0], rcx
0x10047084c  lea     rax, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x100470853  mov     [rcx], rax
0x100470856  add     rcx, 8
0x10047085a  mov     [rbp+57h+arg_0], rcx
0x10047085e  mov     rbx, [rcx+0B0h]
0x100470865  test    rbx, rbx
0x100470868  jz      short loc_1004708A9
0x10047086a  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100470871  test    byte ptr [rax], 8
0x100470874  jz      short loc_100470881
0x100470876  lock dec dword ptr [rbx+70h]
0x10047087a  mov     rbx, [rcx+0B0h]
0x100470881  lock xadd [rbx+18h], r14d
0x100470887  cmp     r14d, 1
0x10047088b  jnz     short loc_1004708A9
0x10047088d  cmp     qword ptr [rbx+8], 0
0x100470892  jz      short loc_1004708A0
0x100470894  mov     rdx, rbx
0x100470897  mov     rcx, [rbx+10h]
0x10047089b  call    ?RemoveElem@?$TList@VCertificateHashList@@VCertificateHash@@$0A@UTListSLock@@@@QEAAXPEAVCertificateHash@@@Z; TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(CertificateHash *)
0x1004708a0  mov     rcx, rbx
0x1004708a3  call    cs:__imp_?Destroy@SOSHost@@AEAAXXZ; SOSHost::Destroy(void)
0x1004708a9  lea     r14, [rsi-8]
0x1004708ad  test    rsi, rsi
0x1004708b0  cmovz   r14, rdi
0x1004708b4  mov     rsi, [r15+7E0h]
0x1004708bb  mov     rbx, rdi
0x1004708be  mov     eax, gs:48h
0x1004708c6  mov     r13d, eax
0x1004708c9  mov     eax, [rsi+28h]
0x1004708cc  test    eax, eax
0x1004708ce  jnz     short loc_1004708E5
0x1004708d0  xor     eax, eax
0x1004708d2  lock cmpxchg [rsi+28h], r13
0x1004708d8  mov     eax, edi
0x1004708da  setz    al
0x1004708dd  test    eax, eax
0x1004708df  jnz     loc_1004709BC
0x1004708e5  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004708ec  mov     ecx, [rax]
0x1004708ee  and     ecx, 84h
0x1004708f4  mov     r15, rdi
0x1004708f7  cmp     cl, 84h
0x1004708fa  jnz     short loc_100470956
0x1004708fc  mov     rdx, gs:58h
0x100470905  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10047090c  mov     ecx, [rax]
0x10047090e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100470915  mov     r8d, [rax]
0x100470918  add     r8, [rdx+rcx*8]
0x10047091c  jz      short loc_10047092E
0x10047091e  cmp     [r8+110h], r8
0x100470925  jnz     short loc_10047092E
0x100470927  mov     r15, [r8+100h]
0x10047092e  test    r15, r15
0x100470931  jz      short loc_100470956
0x100470933  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10047093a  cmp     [rax], ebx
0x10047093c  jz      short loc_10047094E
0x10047093e  lea     rcx, [rbp+57h+var_98]; lpPerformanceCount
0x100470942  call    cs:__imp_QueryPerformanceCounter
0x100470948  mov     rbx, qword ptr [rbp+57h+var_98]
0x10047094c  jmp     short loc_100470956
0x10047094e  mov     rbx, ds:7FFE0008h
0x100470956  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10047095d  lea     rcx, [rsi+28h]
0x100470961  cmp     byte ptr [rax+0C7h], 0
0x100470968  jge     short loc_100470977
0x10047096a  mov     r8, r13
0x10047096d  mov     rdx, r15
0x100470970  call    ?SpinToAcquireOptimistic@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<34,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100470975  jmp     short loc_10047097F
0x100470977  mov     rdx, r13
0x10047097a  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10047097f  test    r15, r15
0x100470982  jz      short loc_1004709BC
0x100470984  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10047098b  cmp     dword ptr [rax], 0
0x10047098e  jz      short loc_1004709A0
0x100470990  lea     rcx, [rbp+57h+var_90]; lpPerformanceCount
0x100470994  call    cs:__imp_QueryPerformanceCounter
0x10047099a  mov     rax, qword ptr [rbp+57h+var_90]
0x10047099e  jmp     short loc_1004709A8
0x1004709a0  mov     rax, ds:7FFE0008h
0x1004709a8  mov     rcx, rax
  ... truncated ...
```
