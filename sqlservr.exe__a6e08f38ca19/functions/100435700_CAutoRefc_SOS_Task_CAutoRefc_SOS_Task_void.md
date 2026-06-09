# CAutoRefc<SOS_Task>::~CAutoRefc<SOS_Task>(void)

- ea: `0x100435700`
- end: `0x100435d95`
- name: `??1?$CAutoRefc@VSOS_Task@@@@QEAA@XZ`
- size: `1685`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1004238f0`
- `0x100454f90`

## callees

- `0x100408320`
- `0x100408560`
- `0x100408810`
- `0x10041d870`
- `0x10041df30`
- `0x10041e170`
- `0x10041e420`
- `0x10041e540`
- `0x10041e640`
- `0x100435700`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x100435bb6`
- `KERNEL32!VirtualProtect` at `0x100435bb6`
- `KERNEL32!QueryPerformanceCounter` at `0x100435809`
- `KERNEL32!QueryPerformanceCounter` at `0x100435862`
- `KERNEL32!QueryPerformanceCounter` at `0x100435ade`
- `KERNEL32!QueryPerformanceCounter` at `0x100435b32`
- `KERNEL32!QueryPerformanceCounter` at `0x100435809`
- `KERNEL32!QueryPerformanceCounter` at `0x100435862`
- `KERNEL32!QueryPerformanceCounter` at `0x100435ade`
- `KERNEL32!QueryPerformanceCounter` at `0x100435b32`
- `KERNEL32!VirtualFree` at `0x100435d02`
- `KERNEL32!VirtualFree` at `0x100435d02`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100435821`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100435af3`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100435d7e`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100435d7e`
- `sqldk!SystemThread_TlsOffset` at `0x1004357d1`
- `sqldk!SystemThread_TlsOffset` at `0x100435901`
- `sqldk!SystemThread_TlsOffset` at `0x100435aa9`
- `sqldk!SystemThread_TlsIndex` at `0x1004357c8`
- `sqldk!SystemThread_TlsIndex` at `0x1004358f8`
- `sqldk!SystemThread_TlsIndex` at `0x100435aa0`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x1004359a1`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100435a48`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100435d70`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x1004359a1`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100435a48`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100435d70`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x1004359ca`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x1004359ca`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004357f6`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10043584e`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100435ace`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100435b21`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1004358b2`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100435c66`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100435ca2`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004357a8`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100435966`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100435a11`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100435a80`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100435d39`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x100435ce8`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004358be`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100435c72`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100435cae`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004358be`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100435c72`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100435cae`

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
              TList<HostManager,SOSHost,0,TListSLock>::RemoveElem(*(_QWORD *)(v13 + 16), v13);
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
                TList<HostManager,SOSHost,0,TListSLock>::RemoveElem(*(_QWORD *)(v17 + 16), v17);
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
                  TList<HostManager,SOSHost,0,TListSLock>::RemoveElem(*(_QWORD *)(v38 + 16), v38);
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
0x100435700  push    rbx
0x100435702  push    rbp
0x100435703  push    rsi
0x100435704  push    rdi
0x100435705  push    r12
0x100435707  push    r13
0x100435709  push    r14
0x10043570b  push    r15
0x10043570d  sub     rsp, 58h
0x100435711  mov     [rsp+98h+var_68], 0FFFFFFFFFFFFFFFEh
0x10043571a  mov     rsi, [rcx]
0x10043571d  test    rsi, rsi
0x100435720  jz      loc_100435D84
0x100435726  lea     rcx, [rsi+10h]
0x10043572a  mov     edi, 0FFFFFFFFh
0x10043572f  mov     eax, edi
0x100435731  lock xadd [rcx+18h], eax
0x100435736  cmp     eax, 1
0x100435739  jnz     loc_100435D84
0x10043573f  cmp     qword ptr [rcx+8], 0
0x100435744  jz      short loc_100435750
0x100435746  call    ?RemoveAndDestroy@?$TListElem@V?$TList@VSOS_Scheduler@@VSOS_Task@@$0BA@UTListSLock@@@@@@IEAAXXZ; TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(void)
0x10043574b  jmp     loc_100435D84
0x100435750  mov     eax, [rsi+0B8h]
0x100435756  xor     r13d, r13d
0x100435759  lea     r12d, [r13+1]
0x10043575d  cmp     eax, 2
0x100435760  jnz     loc_1004358EF
0x100435766  mov     r14, [rsi+0A0h]
0x10043576d  add     r14, 1358h
0x100435774  mov     [rsp+98h+var_58], r14
0x100435779  mov     [rsp+98h+var_50], r13d
0x10043577e  mov     ebx, r13d
0x100435781  mov     eax, gs:48h
0x100435789  mov     r15d, eax
0x10043578c  mov     eax, [r14]
0x10043578f  test    eax, eax
0x100435791  jnz     short loc_1004357A8
0x100435793  xor     eax, eax
0x100435795  lock cmpxchg [r14], r15
0x10043579a  mov     eax, r13d
0x10043579d  setz    al
0x1004357a0  test    eax, eax
0x1004357a2  jnz     loc_10043588E
0x1004357a8  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004357af  mov     ecx, [rax]
0x1004357b1  and     ecx, 84h
0x1004357b7  mov     rbp, r13
0x1004357ba  cmp     cl, 84h
0x1004357bd  jnz     short loc_100435821
0x1004357bf  mov     rdx, gs:58h
0x1004357c8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004357cf  mov     ecx, [rax]
0x1004357d1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004357d8  mov     r8d, [rax]
0x1004357db  add     r8, [rdx+rcx*8]
0x1004357df  jz      short loc_1004357F1
0x1004357e1  cmp     [r8+110h], r8
0x1004357e8  jnz     short loc_1004357F1
0x1004357ea  mov     rbp, [r8+100h]
0x1004357f1  test    rbp, rbp
0x1004357f4  jz      short loc_100435821
0x1004357f6  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004357fd  cmp     [rax], ebx
0x1004357ff  jz      short loc_100435819
0x100435801  lea     rcx, [rsp+98h+PerformanceCount]; lpPerformanceCount
0x100435809  call    cs:__imp_QueryPerformanceCounter
0x10043580f  mov     rbx, qword ptr [rsp+98h+PerformanceCount]
0x100435817  jmp     short loc_100435821
0x100435819  mov     rbx, ds:7FFE0008h
0x100435821  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100435828  mov     rcx, r14
0x10043582b  cmp     byte ptr [rax+0C7h], 0
0x100435832  jge     short loc_100435841
0x100435834  mov     r8, r15
0x100435837  mov     rdx, rbp
0x10043583a  call    ?SpinToAcquireOptimistic@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<11,2,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10043583f  jmp     short loc_100435849
0x100435841  mov     rdx, r15
0x100435844  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAX_K@Z; Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100435849  test    rbp, rbp
0x10043584c  jz      short loc_10043588E
0x10043584e  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100435855  cmp     dword ptr [rax], 0
0x100435858  jz      short loc_100435872
0x10043585a  lea     rcx, [rsp+98h+arg_18]; lpPerformanceCount
0x100435862  call    cs:__imp_QueryPerformanceCounter
0x100435868  mov     rax, qword ptr [rsp+98h+arg_18]
0x100435870  jmp     short loc_10043587A
0x100435872  mov     rax, ds:7FFE0008h
0x10043587a  mov     rcx, rax
0x10043587d  sub     rcx, rbx
0x100435880  cmp     rax, rbx
0x100435883  cmovb   rcx, r13
0x100435887  add     [rbp+0C78h], rcx
0x10043588e  mov     [rsp+98h+var_50], r12d
0x100435893  mov     rcx, [rsi+8]
0x100435897  mov     rax, [rsi]
0x10043589a  mov     [rax+8], rcx
0x10043589e  mov     [rcx], rax
0x1004358a1  mov     [rsi+8], r13
0x1004358a5  mov     [rsi], r13
0x1004358a8  mov     rbx, [rsp+98h+var_58]
0x1004358ad  test    rbx, rbx
0x1004358b0  jz      short loc_1004358EF
0x1004358b2  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x1004358b9  cmp     byte ptr [rax], 0
0x1004358bc  jz      short loc_1004358E2
0x1004358be  call    cs:__imp_rand
0x1004358c4  mov     ecx, eax
0x1004358c6  mov     eax, 66666667h
0x1004358cb  imul    ecx
0x1004358cd  sar     edx, 1
0x1004358cf  mov     eax, edx
0x1004358d1  shr     eax, 1Fh
0x1004358d4  add     edx, eax
0x1004358d6  lea     eax, [rdx+rdx*4]
0x1004358d9  cmp     ecx, eax
0x1004358db  jnz     short loc_1004358E2
0x1004358dd  call    ?UpdateStatSnapshot@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXXZ; Spinlock<11,2,268435714>::UpdateStatSnapshot(void)
0x1004358e2  mov     [rbx], r13
0x1004358e5  mov     [rsp+98h+var_58], r13
0x1004358ea  mov     [rsp+98h+var_50], r13d
0x1004358ef  mov     rdx, gs:58h
0x1004358f8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004358ff  mov     ecx, [rax]
0x100435901  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100435908  mov     r8d, [rax]
0x10043590b  add     r8, [rdx+rcx*8]
0x10043590f  jz      loc_1004359AC
0x100435915  cmp     [r8+110h], r8
0x10043591c  jnz     loc_1004359AC
0x100435922  mov     rax, [r8+100h]
0x100435929  test    rax, rax
0x10043592c  jz      short loc_1004359AC
0x10043592e  cmp     [rax+210h], rsi
0x100435935  jnz     short loc_1004359AC
0x100435937  lea     rax, [rsi-8]
0x10043593b  mov     [rsp+98h+arg_0], rax
0x100435943  lea     rcx, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x10043594a  mov     [rax], rcx
0x10043594d  lea     rcx, [rax+8]
0x100435951  mov     [rsp+98h+var_60], rcx
0x100435956  mov     rbx, [rcx+0B0h]
0x10043595d  test    rbx, rbx
0x100435960  jz      loc_100435D84
0x100435966  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10043596d  test    byte ptr [rax], 8
0x100435970  jz      short loc_10043597D
0x100435972  lock dec dword ptr [rbx+70h]
0x100435976  mov     rbx, [rcx+0B0h]
0x10043597d  lock xadd [rbx+18h], edi
0x100435982  cmp     edi, 1
0x100435985  jnz     loc_100435D84
0x10043598b  cmp     qword ptr [rbx+8], 0
0x100435990  jz      short loc_10043599E
0x100435992  mov     rdx, rbx
0x100435995  mov     rcx, [rbx+10h]
0x100435999  call    ?RemoveElem@?$TList@VHostManager@@VSOSHost@@$0A@UTListSLock@@@@QEAAXPEAVSOSHost@@@Z; TList<HostManager,SOSHost,0,TListSLock>::RemoveElem(SOSHost *)
0x10043599e  mov     rcx, rbx
0x1004359a1  call    cs:__imp_?Destroy@SOSHost@@AEAAXXZ; SOSHost::Destroy(void)
0x1004359a7  jmp     loc_100435D84
0x1004359ac  mov     rcx, [rsi+0A8h]
0x1004359b3  test    rcx, rcx
0x1004359b6  jz      loc_100435CE4
0x1004359bc  cmp     qword ptr [rcx+0F0h], 0
0x1004359c4  jz      loc_100435CE4
0x1004359ca  call    cs:__imp_?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ; SOS_Node::IsTaskStoreDisabled(void)
0x1004359d0  test    al, al
0x1004359d2  jnz     loc_100435CE4
0x1004359d8  mov     rax, [rsi+0A8h]
0x1004359df  mov     rbp, [rax+0F0h]
0x1004359e6  add     rsi, 0FFFFFFFFFFFFFFF8h
0x1004359ea  mov     [rsp+98h+arg_0], rsi
0x1004359f2  lea     rcx, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x1004359f9  mov     [rsi], rcx
0x1004359fc  lea     rcx, [rsi+8]
0x100435a00  mov     [rsp+98h+var_60], rcx
0x100435a05  mov     rbx, [rcx+0B0h]
0x100435a0c  test    rbx, rbx
0x100435a0f  jz      short loc_100435A4E
0x100435a11  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100435a18  test    byte ptr [rax], 8
0x100435a1b  jz      short loc_100435A28
0x100435a1d  lock dec dword ptr [rbx+70h]
0x100435a21  mov     rbx, [rcx+0B0h]
0x100435a28  lock xadd [rbx+18h], edi
0x100435a2d  cmp     edi, 1
0x100435a30  jnz     short loc_100435A4E
0x100435a32  cmp     qword ptr [rbx+8], 0
0x100435a37  jz      short loc_100435A45
0x100435a39  mov     rdx, rbx
0x100435a3c  mov     rcx, [rbx+10h]
0x100435a40  call    ?RemoveElem@?$TList@VHostManager@@VSOSHost@@$0A@UTListSLock@@@@QEAAXPEAVSOSHost@@@Z; TList<HostManager,SOSHost,0,TListSLock>::RemoveElem(SOSHost *)
0x100435a45  mov     rcx, rbx
0x100435a48  call    cs:__imp_?Destroy@SOSHost@@AEAAXXZ; SOSHost::Destroy(void)
0x100435a4e  mov     rdi, [rbp+7E0h]
0x100435a55  mov     rbx, r13
0x100435a58  mov     eax, gs:48h
0x100435a60  mov     r15d, eax
0x100435a63  mov     eax, [rdi+28h]
0x100435a66  test    eax, eax
0x100435a68  jnz     short loc_100435A80
0x100435a6a  xor     eax, eax
0x100435a6c  lock cmpxchg [rdi+28h], r15
0x100435a72  mov     eax, r13d
0x100435a75  setz    al
0x100435a78  test    eax, eax
0x100435a7a  jnz     loc_100435B5B
0x100435a80  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100435a87  mov     ecx, [rax]
0x100435a89  and     ecx, 84h
0x100435a8f  mov     rbp, r13
0x100435a92  cmp     cl, 84h
0x100435a95  jnz     short loc_100435AF3
0x100435a97  mov     rdx, gs:58h
0x100435aa0  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100435aa7  mov     ecx, [rax]
0x100435aa9  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100435ab0  mov     r8d, [rax]
0x100435ab3  add     r8, [rdx+rcx*8]
0x100435ab7  jz      short loc_100435AC9
0x100435ab9  cmp     [r8+110h], r8
0x100435ac0  jnz     short loc_100435AC9
0x100435ac2  mov     rbp, [r8+100h]
0x100435ac9  test    rbp, rbp
0x100435acc  jz      short loc_100435AF3
0x100435ace  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100435ad5  cmp     [rax], ebx
0x100435ad7  jz      short loc_100435AEB
0x100435ad9  lea     rcx, [rsp+98h+var_78]; lpPerformanceCount
0x100435ade  call    cs:__imp_QueryPerformanceCounter
0x100435ae4  mov     rbx, qword ptr [rsp+98h+var_78]
0x100435ae9  jmp     short loc_100435AF3
0x100435aeb  mov     rbx, ds:7FFE0008h
0x100435af3  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100435afa  lea     rcx, [rdi+28h]
0x100435afe  cmp     byte ptr [rax+0C7h], 0
0x100435b05  jge     short loc_100435B14
0x100435b07  mov     r8, r15
0x100435b0a  mov     rdx, rbp
0x100435b0d  call    ?SpinToAcquireOptimistic@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<34,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100435b12  jmp     short loc_100435B1C
0x100435b14  mov     rdx, r15
0x100435b17  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100435b1c  test    rbp, rbp
0x100435b1f  jz      short loc_100435B5B
0x100435b21  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100435b28  cmp     dword ptr [rax], 0
0x100435b2b  jz      short loc_100435B3F
0x100435b2d  lea     rcx, [rsp+98h+var_70]; lpPerformanceCount
0x100435b32  call    cs:__imp_QueryPerformanceCounter
0x100435b38  mov     rax, qword ptr [rsp+98h+var_70]
0x100435b3d  jmp     short loc_100435B47
0x100435b3f  mov     rax, ds:7FFE0008h
0x100435b47  mov     rcx, rax
0x100435b4a  sub     rcx, rbx
0x100435b4d  cmp     rax, rbx
0x100435b50  cmovb   rcx, r13
0x100435b54  add     [rbp+0C78h], rcx
0x100435b5b  mov     rax, [rdi]
0x100435b5e  cmp     [rdi+8], rax
0x100435b62  jnb     loc_100435CA2
0x100435b68  mov     rax, [rdi+20h]
0x100435b6c  cmp     byte ptr [rax+16BCh], 0
0x100435b73  jz      short loc_100435BBE
0x100435b75  mov     ecx, [rdi+498h]
0x100435b7b  and     ecx, 3Fh
0x100435b7e  add     rcx, 9
0x100435b82  shl     rcx, 4
0x100435b86  add     rcx, rdi
0x100435b89  mov     rax, [rcx]
0x100435b8c  mov     [rsi], rax
0x100435b8f  cmp     qword ptr [rcx], 0
0x100435b93  jnz     short loc_100435B99
0x100435b95  mov     [rcx+8], rsi
0x100435b99  mov     [rcx], rsi
0x100435b9c  inc     qword ptr [rdi+498h]
0x100435ba3  lea     r9, [rsp+98h+flOldProtect]; lpflOldProtect
0x100435bab  mov     r8d, r12d; flNewProtect
0x100435bae  mov     edx, 1000h; dwSize
0x100435bb3  mov     rcx, rsi; lpAddress
0x100435bb6  call    cs:__imp_VirtualProtect
0x100435bbc  jmp     short loc_100435BE0
0x100435bbe  mov     rax, [rdi+80h]
0x100435bc5  mov     [rsi], rax
0x100435bc8  cmp     qword ptr [rdi+80h], 0
0x100435bd0  jnz     short loc_100435BD9
0x100435bd2  mov     [rdi+88h], rsi
0x100435bd9  mov     [rdi+80h], rsi
0x100435be0  mov     rax, [rdi+490h]
0x100435be7  inc     rax
0x100435bea  inc     qword ptr [rdi+8]
0x100435bee  mov     rcx, [rdi+20h]; this
0x100435bf2  cmp     byte ptr [rcx+16BCh], 0
0x100435bf9  jnz     short loc_100435C5F
0x100435bfb  cmp     rax, 20h ; ' '
0x100435bff  jb      short loc_100435C5F
0x100435c01  mov     rdx, rsi; struct SList *
0x100435c04  call    ?GetPoolIdForObject@SOS_ObjectStore@@AEBAKPEAVSList@@@Z; SOS_ObjectStore::GetPoolIdForObject(SList *)
  ... truncated ...
```
