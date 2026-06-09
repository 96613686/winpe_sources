# CAutoRefc<SOS_Task>::~CAutoRefc<SOS_Task>(void)

- ea: `0x100477b20`
- end: `0x1004781b5`
- name: `??1?$CAutoRefc@VSOS_Task@@@@QEAA@XZ`
- size: `1685`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x100472580`
- `0x100476570`
- `0x10048d555`
- `0x10048d7c0`

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
- `0x100477b20`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100477c29`
- `KERNEL32!QueryPerformanceCounter` at `0x100477c82`
- `KERNEL32!QueryPerformanceCounter` at `0x100477efe`
- `KERNEL32!QueryPerformanceCounter` at `0x100477f52`
- `KERNEL32!QueryPerformanceCounter` at `0x100477c29`
- `KERNEL32!QueryPerformanceCounter` at `0x100477c82`
- `KERNEL32!QueryPerformanceCounter` at `0x100477efe`
- `KERNEL32!QueryPerformanceCounter` at `0x100477f52`
- `KERNEL32!VirtualProtect` at `0x100477fd6`
- `KERNEL32!VirtualProtect` at `0x100477fd6`
- `KERNEL32!VirtualFree` at `0x100478122`
- `KERNEL32!VirtualFree` at `0x100478122`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100477cd2`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100478086`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1004780c2`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x100478108`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100477c16`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100477c6e`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100477eee`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100477f41`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100477c41`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100477f13`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x100477dea`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x100477dea`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100477dc1`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100477e68`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100478190`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100477dc1`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100477e68`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100478190`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10047819e`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10047819e`
- `sqldk!SystemThread_TlsIndex` at `0x100477be8`
- `sqldk!SystemThread_TlsIndex` at `0x100477d18`
- `sqldk!SystemThread_TlsIndex` at `0x100477ec0`
- `sqldk!SystemThread_TlsOffset` at `0x100477bf1`
- `sqldk!SystemThread_TlsOffset` at `0x100477d21`
- `sqldk!SystemThread_TlsOffset` at `0x100477ec9`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100477bc8`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100477d86`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100477e31`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100477ea0`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100478159`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100477cde`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100478092`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004780ce`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100477cde`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100478092`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004780ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall CAutoRefc<SOS_Task>::~CAutoRefc<SOS_Task>(__int64 **a1)
{
  __int64 *v1; // rsi
  LARGE_INTEGER v2; // rbx
  signed __int64 UniqueThread_low; // r15
  __int64 v4; // rbp
  __int64 v5; // r8
  LARGE_INTEGER v6; // rax
  LONGLONG v7; // rcx
  _QWORD *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // rbx
  SOS_Node *v14; // rcx
  __int64 v15; // rbp
  __int64 *v16; // rsi
  __int64 v17; // rbx
  __int64 v18; // rdi
  LARGE_INTEGER v19; // rbx
  signed __int64 v20; // r15
  __int64 v21; // rbp
  __int64 v22; // r8
  __int64 v23; // rcx
  LARGE_INTEGER v24; // rax
  LONGLONG v25; // rcx
  __int64 *v26; // rcx
  unsigned __int64 v27; // rax
  SOS_ObjectStore *v28; // rcx
  unsigned int PoolIdForObject; // eax
  char v30; // r10
  __int64 v31; // r8
  __int64 v32; // r9
  _QWORD *v33; // rdx
  __int64 v34; // rcx
  int v35; // r8d
  int v36; // r8d
  __int64 *v37; // rsi
  __int64 v38; // rbx
  LARGE_INTEGER v39; // [rsp+20h] [rbp-78h] BYREF
  LARGE_INTEGER v40; // [rsp+28h] [rbp-70h] BYREF
  __int64 v41; // [rsp+30h] [rbp-68h]
  __int64 *v42; // [rsp+38h] [rbp-60h]
  volatile signed __int64 *v43; // [rsp+40h] [rbp-58h]
  int v44; // [rsp+48h] [rbp-50h]
  DWORD flOldProtect; // [rsp+A8h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+B0h] [rbp+18h] BYREF
  LARGE_INTEGER v47; // [rsp+B8h] [rbp+20h] BYREF

  v41 = -2;
  v1 = *a1;
  if ( *a1 && _InterlockedExchangeAdd((volatile signed __int32 *)v1 + 10, 0xFFFFFFFF) == 1 )
  {
    if ( v1[3] )
    {
      TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy((__int64)(v1 + 2));
    }
    else
    {
      if ( *((_DWORD *)v1 + 46) == 2 )
      {
        v43 = (volatile signed __int64 *)(v1[20] + 4952);
        v44 = 0;
        v2.QuadPart = 0;
        UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        if ( *(_DWORD *)v43 || _InterlockedCompareExchange64(v43, UniqueThread_low, 0) )
        {
          v4 = 0;
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
          {
            v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
            if ( v5 && *(_QWORD *)(v5 + 272) == v5 )
              v4 = *(_QWORD *)(v5 + 256);
            if ( v4 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&PerformanceCount);
                v2 = PerformanceCount;
              }
              else
              {
                v2.QuadPart = MEMORY[0x7FFE0008];
              }
            }
          }
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v43, UniqueThread_low);
          else
            Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v43, v4, UniqueThread_low);
          if ( v4 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v47);
              v6 = v47;
            }
            else
            {
              v6.QuadPart = MEMORY[0x7FFE0008];
            }
            v7 = v6.QuadPart - v2.QuadPart;
            if ( v6.QuadPart < (unsigned __int64)v2.QuadPart )
              v7 = 0;
            *(_QWORD *)(v4 + 3192) += v7;
          }
        }
        v44 = 1;
        v8 = (_QWORD *)v1[1];
        v9 = *v1;
        *(_QWORD *)(v9 + 8) = v8;
        *v8 = v9;
        v1[1] = 0;
        *v1 = 0;
        if ( v43 )
        {
          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v10 = rand();
            if ( v10 == 5 * (v10 / 5) )
              Spinlock<11,2,268435714>::UpdateStatSnapshot();
          }
          *v43 = 0;
          v43 = 0;
          v44 = 0;
        }
      }
      v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      if ( v11 && *(_QWORD *)(v11 + 272) == v11 && (v12 = *(_QWORD *)(v11 + 256)) != 0 && *(__int64 **)(v12 + 528) == v1 )
      {
        *(v1 - 1) = (__int64)&ISOSHost_TaskImpl::`vftable';
        v42 = v1;
        v13 = v1[22];
        if ( v13 )
        {
          if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
          {
            _InterlockedDecrement((volatile signed __int32 *)(v13 + 112));
            v13 = v1[22];
          }
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v13 + 24), 0xFFFFFFFF) == 1 )
          {
            if ( *(_QWORD *)(v13 + 8) )
              TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*(_QWORD *)(v13 + 16), v13);
            SOSHost::Destroy((SOSHost *)v13);
          }
        }
      }
      else
      {
        v14 = (SOS_Node *)v1[21];
        if ( v14 && *((_QWORD *)v14 + 30) && !SOS_Node::IsTaskStoreDisabled(v14) )
        {
          v15 = *(_QWORD *)(v1[21] + 240);
          v16 = v1 - 1;
          *v16 = (__int64)&ISOSHost_TaskImpl::`vftable';
          v42 = v16 + 1;
          v17 = v16[23];
          if ( v17 )
          {
            if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
            {
              _InterlockedDecrement((volatile signed __int32 *)(v17 + 112));
              v17 = v16[23];
            }
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v17 + 24), 0xFFFFFFFF) == 1 )
            {
              if ( *(_QWORD *)(v17 + 8) )
                TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*(_QWORD *)(v17 + 16), v17);
              SOSHost::Destroy((SOSHost *)v17);
            }
          }
          v18 = *(_QWORD *)(v15 + 2016);
          v19.QuadPart = 0;
          v20 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
          if ( *(_DWORD *)(v18 + 40) || _InterlockedCompareExchange64((volatile signed __int64 *)(v18 + 40), v20, 0) )
          {
            v21 = 0;
            if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
            {
              v22 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset;
              if ( v22 && *(_QWORD *)(v22 + 272) == v22 )
                v21 = *(_QWORD *)(v22 + 256);
              if ( v21 )
              {
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&v39);
                  v19 = v39;
                }
                else
                {
                  v19.QuadPart = MEMORY[0x7FFE0008];
                }
              }
            }
            v23 = v18 + 40;
            if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
              Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v23, v20);
            else
              Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v23, v21, v20);
            if ( v21 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v40);
                v24 = v40;
              }
              else
              {
                v24.QuadPart = MEMORY[0x7FFE0008];
              }
              v25 = v24.QuadPart - v19.QuadPart;
              if ( v24.QuadPart < (unsigned __int64)v19.QuadPart )
                v25 = 0;
              *(_QWORD *)(v21 + 3192) += v25;
            }
          }
          if ( *(_QWORD *)(v18 + 8) >= *(_QWORD *)v18 )
          {
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v36 = rand();
              if ( v36 == 5 * (v36 / 5) )
                Spinlock<34,1,268435714>::UpdateStatSnapshot();
            }
            *(_QWORD *)(v18 + 40) = 0;
            (*(void (__fastcall **)(__int64 *))(v18 + 48))(v16);
          }
          else
          {
            if ( *(_BYTE *)(*(_QWORD *)(v18 + 32) + 5820LL) )
            {
              v26 = (__int64 *)(v18 + 16 * ((*(_DWORD *)(v18 + 1176) & 0x3F) + 9LL));
              *v16 = *v26;
              if ( !*v26 )
                v26[1] = (__int64)v16;
              *v26 = (__int64)v16;
              ++*(_QWORD *)(v18 + 1176);
              VirtualProtect(v16, 0x1000u, 1u, &flOldProtect);
            }
            else
            {
              *v16 = *(_QWORD *)(v18 + 128);
              if ( !*(_QWORD *)(v18 + 128) )
                *(_QWORD *)(v18 + 136) = v16;
              *(_QWORD *)(v18 + 128) = v16;
            }
            v27 = *(_QWORD *)(v18 + 1168) + 1LL;
            ++*(_QWORD *)(v18 + 8);
            v28 = *(SOS_ObjectStore **)(v18 + 32);
            if ( !*((_BYTE *)v28 + 5820) && v27 >= 0x20 )
            {
              PoolIdForObject = SOS_ObjectStore::GetPoolIdForObject(v28, (struct SList *)v16);
              v30 = PoolIdForObject;
              v31 = v18 + 8LL * PoolIdForObject;
              v32 = *(_QWORD *)(v18 + 128);
              v33 = *(_QWORD **)(v18 + 136);
              if ( v33 != (_QWORD *)(v18 + 128) && v33 )
              {
                *v33 = *(_QWORD *)(v31 + 1184);
                *(_QWORD *)(v31 + 1184) = v32;
              }
              *(_QWORD *)(v18 + 128) = 0;
              *(_QWORD *)(v18 + 136) = v18 + 128;
              v27 = 0;
              v34 = *(_QWORD *)(v18 + 1696);
              if ( ((1LL << v30) & v34) == 0 )
                *(_QWORD *)(v18 + 1696) = v34 | (1LL << v30);
            }
            *(_QWORD *)(v18 + 1168) = v27;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v35 = rand();
              if ( v35 == 5 * (v35 / 5) )
                Spinlock<34,1,268435714>::UpdateStatSnapshot();
            }
            *(_QWORD *)(v18 + 40) = 0;
          }
        }
        else
        {
          v37 = v1 - 1;
          if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
          {
            VirtualFree(v37, 0, 0x8000u);
          }
          else if ( v37 )
          {
            *v37 = (__int64)&ISOSHost_TaskImpl::`vftable';
            v38 = v37[23];
            if ( v38 )
            {
              if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
              {
                _InterlockedDecrement((volatile signed __int32 *)(v38 + 112));
                v38 = v37[23];
              }
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v38 + 24), 0xFFFFFFFF) == 1 )
              {
                if ( *(_QWORD *)(v38 + 8) )
                  TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*(_QWORD *)(v38 + 16), v38);
                SOSHost::Destroy((SOSHost *)v38);
              }
            }
            operator delete(v37, 0x3E0u);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x100477b20  push    rbx
0x100477b22  push    rbp
0x100477b23  push    rsi
0x100477b24  push    rdi
0x100477b25  push    r12
0x100477b27  push    r13
0x100477b29  push    r14
0x100477b2b  push    r15
0x100477b2d  sub     rsp, 58h
0x100477b31  mov     [rsp+98h+var_68], 0FFFFFFFFFFFFFFFEh
0x100477b3a  mov     rsi, [rcx]
0x100477b3d  test    rsi, rsi
0x100477b40  jz      loc_1004781A4
0x100477b46  lea     rcx, [rsi+10h]
0x100477b4a  mov     edi, 0FFFFFFFFh
0x100477b4f  mov     eax, edi
0x100477b51  lock xadd [rcx+18h], eax
0x100477b56  cmp     eax, 1
0x100477b59  jnz     loc_1004781A4
0x100477b5f  cmp     qword ptr [rcx+8], 0
0x100477b64  jz      short loc_100477B70
0x100477b66  call    ?RemoveAndDestroy@?$TListElem@V?$TList@VSOS_Scheduler@@VSOS_Task@@$0BA@UTListSLock@@@@@@IEAAXXZ; TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(void)
0x100477b6b  jmp     loc_1004781A4
0x100477b70  mov     eax, [rsi+0B8h]
0x100477b76  xor     r13d, r13d
0x100477b79  lea     r12d, [r13+1]
0x100477b7d  cmp     eax, 2
0x100477b80  jnz     loc_100477D0F
0x100477b86  mov     r14, [rsi+0A0h]
0x100477b8d  add     r14, 1358h
0x100477b94  mov     [rsp+98h+var_58], r14
0x100477b99  mov     [rsp+98h+var_50], r13d
0x100477b9e  mov     ebx, r13d
0x100477ba1  mov     eax, gs:48h
0x100477ba9  mov     r15d, eax
0x100477bac  mov     eax, [r14]
0x100477baf  test    eax, eax
0x100477bb1  jnz     short loc_100477BC8
0x100477bb3  xor     eax, eax
0x100477bb5  lock cmpxchg [r14], r15
0x100477bba  mov     eax, r13d
0x100477bbd  setz    al
0x100477bc0  test    eax, eax
0x100477bc2  jnz     loc_100477CAE
0x100477bc8  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100477bcf  mov     ecx, [rax]
0x100477bd1  and     ecx, 84h
0x100477bd7  mov     rbp, r13
0x100477bda  cmp     cl, 84h
0x100477bdd  jnz     short loc_100477C41
0x100477bdf  mov     rdx, gs:58h
0x100477be8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100477bef  mov     ecx, [rax]
0x100477bf1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100477bf8  mov     r8d, [rax]
0x100477bfb  add     r8, [rdx+rcx*8]
0x100477bff  jz      short loc_100477C11
0x100477c01  cmp     [r8+110h], r8
0x100477c08  jnz     short loc_100477C11
0x100477c0a  mov     rbp, [r8+100h]
0x100477c11  test    rbp, rbp
0x100477c14  jz      short loc_100477C41
0x100477c16  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100477c1d  cmp     [rax], ebx
0x100477c1f  jz      short loc_100477C39
0x100477c21  lea     rcx, [rsp+98h+PerformanceCount]; lpPerformanceCount
0x100477c29  call    cs:__imp_QueryPerformanceCounter
0x100477c2f  mov     rbx, qword ptr [rsp+98h+PerformanceCount]
0x100477c37  jmp     short loc_100477C41
0x100477c39  mov     rbx, ds:7FFE0008h
0x100477c41  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100477c48  mov     rcx, r14
0x100477c4b  cmp     byte ptr [rax+0C7h], 0
0x100477c52  jge     short loc_100477C61
0x100477c54  mov     r8, r15
0x100477c57  mov     rdx, rbp
0x100477c5a  call    ?SpinToAcquireOptimistic@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<11,2,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100477c5f  jmp     short loc_100477C69
0x100477c61  mov     rdx, r15
0x100477c64  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAX_K@Z; Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100477c69  test    rbp, rbp
0x100477c6c  jz      short loc_100477CAE
0x100477c6e  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100477c75  cmp     dword ptr [rax], 0
0x100477c78  jz      short loc_100477C92
0x100477c7a  lea     rcx, [rsp+98h+arg_18]; lpPerformanceCount
0x100477c82  call    cs:__imp_QueryPerformanceCounter
0x100477c88  mov     rax, qword ptr [rsp+98h+arg_18]
0x100477c90  jmp     short loc_100477C9A
0x100477c92  mov     rax, ds:7FFE0008h
0x100477c9a  mov     rcx, rax
0x100477c9d  sub     rcx, rbx
0x100477ca0  cmp     rax, rbx
0x100477ca3  cmovb   rcx, r13
0x100477ca7  add     [rbp+0C78h], rcx
0x100477cae  mov     [rsp+98h+var_50], r12d
0x100477cb3  mov     rcx, [rsi+8]
0x100477cb7  mov     rax, [rsi]
0x100477cba  mov     [rax+8], rcx
0x100477cbe  mov     [rcx], rax
0x100477cc1  mov     [rsi+8], r13
0x100477cc5  mov     [rsi], r13
0x100477cc8  mov     rbx, [rsp+98h+var_58]
0x100477ccd  test    rbx, rbx
0x100477cd0  jz      short loc_100477D0F
0x100477cd2  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x100477cd9  cmp     byte ptr [rax], 0
0x100477cdc  jz      short loc_100477D02
0x100477cde  call    cs:__imp_rand
0x100477ce4  mov     ecx, eax
0x100477ce6  mov     eax, 66666667h
0x100477ceb  imul    ecx
0x100477ced  sar     edx, 1
0x100477cef  mov     eax, edx
0x100477cf1  shr     eax, 1Fh
0x100477cf4  add     edx, eax
0x100477cf6  lea     eax, [rdx+rdx*4]
0x100477cf9  cmp     ecx, eax
0x100477cfb  jnz     short loc_100477D02
0x100477cfd  call    ?UpdateStatSnapshot@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXXZ; Spinlock<11,2,268435714>::UpdateStatSnapshot(void)
0x100477d02  mov     [rbx], r13
0x100477d05  mov     [rsp+98h+var_58], r13
0x100477d0a  mov     [rsp+98h+var_50], r13d
0x100477d0f  mov     rdx, gs:58h
0x100477d18  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100477d1f  mov     ecx, [rax]
0x100477d21  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100477d28  mov     r8d, [rax]
0x100477d2b  add     r8, [rdx+rcx*8]
0x100477d2f  jz      loc_100477DCC
0x100477d35  cmp     [r8+110h], r8
0x100477d3c  jnz     loc_100477DCC
0x100477d42  mov     rax, [r8+100h]
0x100477d49  test    rax, rax
0x100477d4c  jz      short loc_100477DCC
0x100477d4e  cmp     [rax+210h], rsi
0x100477d55  jnz     short loc_100477DCC
0x100477d57  lea     rax, [rsi-8]
0x100477d5b  mov     [rsp+98h+arg_0], rax
0x100477d63  lea     rcx, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x100477d6a  mov     [rax], rcx
0x100477d6d  lea     rcx, [rax+8]
0x100477d71  mov     [rsp+98h+var_60], rcx
0x100477d76  mov     rbx, [rcx+0B0h]
0x100477d7d  test    rbx, rbx
0x100477d80  jz      loc_1004781A4
0x100477d86  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100477d8d  test    byte ptr [rax], 8
0x100477d90  jz      short loc_100477D9D
0x100477d92  lock dec dword ptr [rbx+70h]
0x100477d96  mov     rbx, [rcx+0B0h]
0x100477d9d  lock xadd [rbx+18h], edi
0x100477da2  cmp     edi, 1
0x100477da5  jnz     loc_1004781A4
0x100477dab  cmp     qword ptr [rbx+8], 0
0x100477db0  jz      short loc_100477DBE
0x100477db2  mov     rdx, rbx
0x100477db5  mov     rcx, [rbx+10h]
0x100477db9  call    ?RemoveElem@?$TList@VCertificateHashList@@VCertificateHash@@$0A@UTListSLock@@@@QEAAXPEAVCertificateHash@@@Z; TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(CertificateHash *)
0x100477dbe  mov     rcx, rbx
0x100477dc1  call    cs:__imp_?Destroy@SOSHost@@AEAAXXZ; SOSHost::Destroy(void)
0x100477dc7  jmp     loc_1004781A4
0x100477dcc  mov     rcx, [rsi+0A8h]
0x100477dd3  test    rcx, rcx
0x100477dd6  jz      loc_100478104
0x100477ddc  cmp     qword ptr [rcx+0F0h], 0
0x100477de4  jz      loc_100478104
0x100477dea  call    cs:__imp_?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ; SOS_Node::IsTaskStoreDisabled(void)
0x100477df0  test    al, al
0x100477df2  jnz     loc_100478104
0x100477df8  mov     rax, [rsi+0A8h]
0x100477dff  mov     rbp, [rax+0F0h]
0x100477e06  add     rsi, 0FFFFFFFFFFFFFFF8h
0x100477e0a  mov     [rsp+98h+arg_0], rsi
0x100477e12  lea     rcx, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x100477e19  mov     [rsi], rcx
0x100477e1c  lea     rcx, [rsi+8]
0x100477e20  mov     [rsp+98h+var_60], rcx
0x100477e25  mov     rbx, [rcx+0B0h]
0x100477e2c  test    rbx, rbx
0x100477e2f  jz      short loc_100477E6E
0x100477e31  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100477e38  test    byte ptr [rax], 8
0x100477e3b  jz      short loc_100477E48
0x100477e3d  lock dec dword ptr [rbx+70h]
0x100477e41  mov     rbx, [rcx+0B0h]
0x100477e48  lock xadd [rbx+18h], edi
0x100477e4d  cmp     edi, 1
0x100477e50  jnz     short loc_100477E6E
0x100477e52  cmp     qword ptr [rbx+8], 0
0x100477e57  jz      short loc_100477E65
0x100477e59  mov     rdx, rbx
0x100477e5c  mov     rcx, [rbx+10h]
0x100477e60  call    ?RemoveElem@?$TList@VCertificateHashList@@VCertificateHash@@$0A@UTListSLock@@@@QEAAXPEAVCertificateHash@@@Z; TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(CertificateHash *)
0x100477e65  mov     rcx, rbx
0x100477e68  call    cs:__imp_?Destroy@SOSHost@@AEAAXXZ; SOSHost::Destroy(void)
0x100477e6e  mov     rdi, [rbp+7E0h]
0x100477e75  mov     rbx, r13
0x100477e78  mov     eax, gs:48h
0x100477e80  mov     r15d, eax
0x100477e83  mov     eax, [rdi+28h]
0x100477e86  test    eax, eax
0x100477e88  jnz     short loc_100477EA0
0x100477e8a  xor     eax, eax
0x100477e8c  lock cmpxchg [rdi+28h], r15
0x100477e92  mov     eax, r13d
0x100477e95  setz    al
0x100477e98  test    eax, eax
0x100477e9a  jnz     loc_100477F7B
0x100477ea0  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100477ea7  mov     ecx, [rax]
0x100477ea9  and     ecx, 84h
0x100477eaf  mov     rbp, r13
0x100477eb2  cmp     cl, 84h
0x100477eb5  jnz     short loc_100477F13
0x100477eb7  mov     rdx, gs:58h
0x100477ec0  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100477ec7  mov     ecx, [rax]
0x100477ec9  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100477ed0  mov     r8d, [rax]
0x100477ed3  add     r8, [rdx+rcx*8]
0x100477ed7  jz      short loc_100477EE9
0x100477ed9  cmp     [r8+110h], r8
0x100477ee0  jnz     short loc_100477EE9
0x100477ee2  mov     rbp, [r8+100h]
0x100477ee9  test    rbp, rbp
0x100477eec  jz      short loc_100477F13
0x100477eee  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100477ef5  cmp     [rax], ebx
0x100477ef7  jz      short loc_100477F0B
0x100477ef9  lea     rcx, [rsp+98h+var_78]; lpPerformanceCount
0x100477efe  call    cs:__imp_QueryPerformanceCounter
0x100477f04  mov     rbx, qword ptr [rsp+98h+var_78]
0x100477f09  jmp     short loc_100477F13
0x100477f0b  mov     rbx, ds:7FFE0008h
0x100477f13  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100477f1a  lea     rcx, [rdi+28h]
0x100477f1e  cmp     byte ptr [rax+0C7h], 0
0x100477f25  jge     short loc_100477F34
0x100477f27  mov     r8, r15
0x100477f2a  mov     rdx, rbp
0x100477f2d  call    ?SpinToAcquireOptimistic@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<34,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100477f32  jmp     short loc_100477F3C
0x100477f34  mov     rdx, r15
0x100477f37  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100477f3c  test    rbp, rbp
0x100477f3f  jz      short loc_100477F7B
0x100477f41  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100477f48  cmp     dword ptr [rax], 0
0x100477f4b  jz      short loc_100477F5F
0x100477f4d  lea     rcx, [rsp+98h+var_70]; lpPerformanceCount
0x100477f52  call    cs:__imp_QueryPerformanceCounter
0x100477f58  mov     rax, qword ptr [rsp+98h+var_70]
0x100477f5d  jmp     short loc_100477F67
0x100477f5f  mov     rax, ds:7FFE0008h
0x100477f67  mov     rcx, rax
0x100477f6a  sub     rcx, rbx
0x100477f6d  cmp     rax, rbx
0x100477f70  cmovb   rcx, r13
0x100477f74  add     [rbp+0C78h], rcx
0x100477f7b  mov     rax, [rdi]
0x100477f7e  cmp     [rdi+8], rax
0x100477f82  jnb     loc_1004780C2
0x100477f88  mov     rax, [rdi+20h]
0x100477f8c  cmp     byte ptr [rax+16BCh], 0
0x100477f93  jz      short loc_100477FDE
0x100477f95  mov     ecx, [rdi+498h]
0x100477f9b  and     ecx, 3Fh
0x100477f9e  add     rcx, 9
0x100477fa2  shl     rcx, 4
0x100477fa6  add     rcx, rdi
0x100477fa9  mov     rax, [rcx]
0x100477fac  mov     [rsi], rax
0x100477faf  cmp     qword ptr [rcx], 0
0x100477fb3  jnz     short loc_100477FB9
0x100477fb5  mov     [rcx+8], rsi
0x100477fb9  mov     [rcx], rsi
0x100477fbc  inc     qword ptr [rdi+498h]
0x100477fc3  lea     r9, [rsp+98h+flOldProtect]; lpflOldProtect
0x100477fcb  mov     r8d, r12d; flNewProtect
0x100477fce  mov     edx, 1000h; dwSize
0x100477fd3  mov     rcx, rsi; lpAddress
0x100477fd6  call    cs:__imp_VirtualProtect
0x100477fdc  jmp     short loc_100478000
0x100477fde  mov     rax, [rdi+80h]
0x100477fe5  mov     [rsi], rax
0x100477fe8  cmp     qword ptr [rdi+80h], 0
0x100477ff0  jnz     short loc_100477FF9
0x100477ff2  mov     [rdi+88h], rsi
0x100477ff9  mov     [rdi+80h], rsi
0x100478000  mov     rax, [rdi+490h]
0x100478007  inc     rax
0x10047800a  inc     qword ptr [rdi+8]
0x10047800e  mov     rcx, [rdi+20h]; this
0x100478012  cmp     byte ptr [rcx+16BCh], 0
0x100478019  jnz     short loc_10047807F
0x10047801b  cmp     rax, 20h ; ' '
0x10047801f  jb      short loc_10047807F
0x100478021  mov     rdx, rsi; struct SList *
0x100478024  call    ?GetPoolIdForObject@SOS_ObjectStore@@AEBAKPEAVSList@@@Z; SOS_ObjectStore::GetPoolIdForObject(SList *)
  ... truncated ...
```
