# TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(void)

- ea: `0x10041d870`
- end: `0x10041df2a`
- name: `?RemoveAndDestroy@?$TListElem@V?$TList@VSOS_Scheduler@@VSOS_Task@@$0BA@UTListSLock@@@@@@IEAAXXZ`
- size: `1722`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x100412470`
- `0x100416770`
- `0x100435700`
- `0x1004369a0`
- `0x10043f6a0`

## callees

- `0x100408320`
- `0x100408560`
- `0x100408810`
- `0x10040af70`
- `0x10041d870`
- `0x10041df30`
- `0x10041e170`
- `0x10041e420`
- `0x10041e540`
- `0x10041e640`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x10041dd35`
- `KERNEL32!VirtualProtect` at `0x10041dd35`
- `KERNEL32!QueryPerformanceCounter` at `0x10041d95a`
- `KERNEL32!QueryPerformanceCounter` at `0x10041d9b3`
- `KERNEL32!QueryPerformanceCounter` at `0x10041dc5d`
- `KERNEL32!QueryPerformanceCounter` at `0x10041dcb1`
- `KERNEL32!QueryPerformanceCounter` at `0x10041d95a`
- `KERNEL32!QueryPerformanceCounter` at `0x10041d9b3`
- `KERNEL32!QueryPerformanceCounter` at `0x10041dc5d`
- `KERNEL32!QueryPerformanceCounter` at `0x10041dcb1`
- `KERNEL32!VirtualFree` at `0x10041de85`
- `KERNEL32!VirtualFree` at `0x10041de85`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10041d972`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10041dc72`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10041df13`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10041df13`
- `sqldk!SystemThread_TlsOffset` at `0x10041d922`
- `sqldk!SystemThread_TlsOffset` at `0x10041da51`
- `sqldk!SystemThread_TlsOffset` at `0x10041dc28`
- `sqldk!SystemThread_TlsIndex` at `0x10041d919`
- `sqldk!SystemThread_TlsIndex` at `0x10041da48`
- `sqldk!SystemThread_TlsIndex` at `0x10041dc1f`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10041db06`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10041dbbd`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10041df05`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10041db06`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10041dbbd`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10041df05`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x10041db2f`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x10041db2f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10041d947`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10041d99f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10041dc4d`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10041dca0`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10041da03`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10041dde5`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10041de21`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10041d8f9`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10041dac6`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10041db81`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10041dbff`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10041dec9`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x10041de63`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10041da0f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10041ddf1`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10041de2d`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10041da0f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10041ddf1`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10041de2d`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(__int64 a1)
{
  __int64 *v1; // rsi
  __int64 *v2; // rdi
  LARGE_INTEGER v3; // rbx
  signed __int64 UniqueThread_low; // r15
  __int64 v5; // rbp
  __int64 v6; // r8
  LARGE_INTEGER v7; // rax
  LONGLONG v8; // rcx
  _QWORD *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // r8
  __int64 v13; // rax
  _QWORD *v14; // rdi
  __int64 v15; // rbx
  SOS_Node *v16; // rcx
  __int64 v17; // rbp
  __int64 *v18; // rcx
  _QWORD *v19; // rcx
  __int64 v20; // rbx
  __int64 *v21; // r14
  __int64 v22; // rsi
  LARGE_INTEGER v23; // rbx
  signed __int64 v24; // r12
  __int64 v25; // rbp
  __int64 v26; // r8
  __int64 v27; // rcx
  LARGE_INTEGER v28; // rax
  LONGLONG v29; // rcx
  __int64 *v30; // rcx
  unsigned __int64 v31; // rax
  SOS_ObjectStore *v32; // rcx
  unsigned int PoolIdForObject; // eax
  char v34; // r10
  __int64 v35; // r8
  __int64 v36; // r9
  _QWORD *v37; // rdx
  __int64 v38; // rcx
  int v39; // r8d
  int v40; // r8d
  __int64 *v41; // rcx
  __int64 *v42; // rsi
  __int64 v43; // rbx
  LARGE_INTEGER v44; // [rsp+20h] [rbp-78h] BYREF
  LARGE_INTEGER v45; // [rsp+28h] [rbp-70h] BYREF
  __int64 v46; // [rsp+30h] [rbp-68h]
  volatile signed __int64 *v47; // [rsp+38h] [rbp-60h]
  int v48; // [rsp+40h] [rbp-58h]
  DWORD flOldProtect; // [rsp+A8h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+B0h] [rbp+18h] BYREF
  LARGE_INTEGER v51; // [rsp+B8h] [rbp+20h] BYREF

  v46 = -2;
  v1 = (__int64 *)(a1 - 16);
  v2 = 0;
  if ( !a1 )
    v1 = 0;
  TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*(_QWORD *)(a1 + 16) + 48LL, v1);
  if ( *((_DWORD *)v1 + 46) == 2 )
  {
    v47 = (volatile signed __int64 *)(v1[20] + 4952);
    v48 = 0;
    v3.QuadPart = 0;
    UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( *(_DWORD *)v47 || _InterlockedCompareExchange64(v47, UniqueThread_low, 0) )
    {
      v5 = 0;
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( v6 && *(_QWORD *)(v6 + 272) == v6 )
          v5 = *(_QWORD *)(v6 + 256);
        if ( v5 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&PerformanceCount);
            v3 = PerformanceCount;
          }
          else
          {
            v3.QuadPart = MEMORY[0x7FFE0008];
          }
        }
      }
      if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
        Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v47, UniqueThread_low);
      else
        Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v47, v5, UniqueThread_low);
      if ( v5 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v51);
          v7 = v51;
        }
        else
        {
          v7.QuadPart = MEMORY[0x7FFE0008];
        }
        v8 = v7.QuadPart - v3.QuadPart;
        if ( v7.QuadPart < (unsigned __int64)v3.QuadPart )
          v8 = 0;
        *(_QWORD *)(v5 + 3192) += v8;
      }
    }
    v48 = 1;
    v9 = (_QWORD *)v1[1];
    v10 = *v1;
    *(_QWORD *)(v10 + 8) = v9;
    *v9 = v10;
    v1[1] = 0;
    *v1 = 0;
    if ( v47 )
    {
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v11 = rand();
        if ( v11 == 5 * (v11 / 5) )
          Spinlock<11,2,268435714>::UpdateStatSnapshot();
      }
      *v47 = 0;
      v47 = 0;
      v48 = 0;
    }
  }
  v12 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  if ( v12 && *(_QWORD *)(v12 + 272) == v12 && (v13 = *(_QWORD *)(v12 + 256)) != 0 && *(__int64 **)(v13 + 528) == v1 )
  {
    if ( v1 )
      v2 = v1 - 1;
    *v2 = (__int64)&ISOSHost_TaskImpl::`vftable';
    v14 = v2 + 1;
    v15 = v14[22];
    if ( v15 )
    {
      if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
      {
        _InterlockedDecrement((volatile signed __int32 *)(v15 + 112));
        v15 = v14[22];
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v15 + 24), 0xFFFFFFFF) == 1 )
      {
        if ( *(_QWORD *)(v15 + 8) )
          TList<HostManager,SOSHost,0,TListSLock>::RemoveElem(*(_QWORD *)(v15 + 16), v15);
        SOSHost::Destroy((SOSHost *)v15);
      }
    }
  }
  else
  {
    v16 = (SOS_Node *)v1[21];
    if ( v16 && *((_QWORD *)v16 + 30) && !SOS_Node::IsTaskStoreDisabled(v16) )
    {
      v17 = *(_QWORD *)(v1[21] + 240);
      v18 = v1 - 1;
      if ( !v1 )
        v18 = 0;
      *v18 = (__int64)&ISOSHost_TaskImpl::`vftable';
      v19 = v18 + 1;
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
            TList<HostManager,SOSHost,0,TListSLock>::RemoveElem(*(_QWORD *)(v20 + 16), v20);
          SOSHost::Destroy((SOSHost *)v20);
        }
      }
      v21 = v1 - 1;
      if ( !v1 )
        v21 = 0;
      v22 = *(_QWORD *)(v17 + 2016);
      v23.QuadPart = 0;
      v24 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( *(_DWORD *)(v22 + 40) || _InterlockedCompareExchange64((volatile signed __int64 *)(v22 + 40), v24, 0) )
      {
        v25 = 0;
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v26 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v26 && *(_QWORD *)(v26 + 272) == v26 )
            v25 = *(_QWORD *)(v26 + 256);
          if ( v25 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v44);
              v23 = v44;
            }
            else
            {
              v23.QuadPart = MEMORY[0x7FFE0008];
            }
          }
        }
        v27 = v22 + 40;
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v27, v24);
        else
          Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v27, v25, v24);
        if ( v25 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v45);
            v28 = v45;
          }
          else
          {
            v28.QuadPart = MEMORY[0x7FFE0008];
          }
          v29 = v28.QuadPart - v23.QuadPart;
          if ( v28.QuadPart < (unsigned __int64)v23.QuadPart )
            v29 = 0;
          *(_QWORD *)(v25 + 3192) += v29;
        }
      }
      if ( *(_QWORD *)(v22 + 8) >= *(_QWORD *)v22 )
      {
        if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v40 = rand();
          if ( v40 == 5 * (v40 / 5) )
            Spinlock<34,1,268435714>::UpdateStatSnapshot();
        }
        *(_QWORD *)(v22 + 40) = 0;
        (*(void (__fastcall **)(__int64 *))(v22 + 48))(v21);
      }
      else
      {
        if ( *(_BYTE *)(*(_QWORD *)(v22 + 32) + 5820LL) )
        {
          v30 = (__int64 *)(v22 + 16 * ((*(_DWORD *)(v22 + 1176) & 0x3F) + 9LL));
          *v21 = *v30;
          if ( !*v30 )
            v30[1] = (__int64)v21;
          *v30 = (__int64)v21;
          ++*(_QWORD *)(v22 + 1176);
          VirtualProtect(v21, 0x1000u, 1u, &flOldProtect);
        }
        else
        {
          *v21 = *(_QWORD *)(v22 + 128);
          if ( !*(_QWORD *)(v22 + 128) )
            *(_QWORD *)(v22 + 136) = v21;
          *(_QWORD *)(v22 + 128) = v21;
        }
        v31 = *(_QWORD *)(v22 + 1168) + 1LL;
        ++*(_QWORD *)(v22 + 8);
        v32 = *(SOS_ObjectStore **)(v22 + 32);
        if ( !*((_BYTE *)v32 + 5820) && v31 >= 0x20 )
        {
          PoolIdForObject = SOS_ObjectStore::GetPoolIdForObject(v32, (struct SList *)v21);
          v34 = PoolIdForObject;
          v35 = v22 + 8LL * PoolIdForObject;
          v36 = *(_QWORD *)(v22 + 128);
          v37 = *(_QWORD **)(v22 + 136);
          if ( v37 != (_QWORD *)(v22 + 128) && v37 )
          {
            *v37 = *(_QWORD *)(v35 + 1184);
            *(_QWORD *)(v35 + 1184) = v36;
          }
          *(_QWORD *)(v22 + 128) = 0;
          *(_QWORD *)(v22 + 136) = v22 + 128;
          v31 = 0;
          v38 = *(_QWORD *)(v22 + 1696);
          if ( ((1LL << v34) & v38) == 0 )
            *(_QWORD *)(v22 + 1696) = v38 | (1LL << v34);
        }
        *(_QWORD *)(v22 + 1168) = v31;
        if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v39 = rand();
          if ( v39 == 5 * (v39 / 5) )
            Spinlock<34,1,268435714>::UpdateStatSnapshot();
        }
        *(_QWORD *)(v22 + 40) = 0;
      }
    }
    else if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
    {
      v41 = v1 - 1;
      if ( !v1 )
        v41 = 0;
      VirtualFree(v41, 0, 0x8000u);
    }
    else if ( v1 )
    {
      v42 = v1 - 1;
      if ( v42 )
      {
        *v42 = (__int64)&ISOSHost_TaskImpl::`vftable';
        v43 = v42[23];
        if ( v43 )
        {
          if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
          {
            _InterlockedDecrement((volatile signed __int32 *)(v43 + 112));
            v43 = v42[23];
          }
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v43 + 24), 0xFFFFFFFF) == 1 )
          {
            if ( *(_QWORD *)(v43 + 8) )
              TList<HostManager,SOSHost,0,TListSLock>::RemoveElem(*(_QWORD *)(v43 + 16), v43);
            SOSHost::Destroy((SOSHost *)v43);
          }
        }
        operator delete(v42, 0x3E0u);
      }
    }
  }
}

```

## disassembly

```asm
0x10041d870  push    rbx
0x10041d872  push    rbp
0x10041d873  push    rsi
0x10041d874  push    rdi
0x10041d875  push    r12
0x10041d877  push    r13
0x10041d879  push    r14
0x10041d87b  push    r15
0x10041d87d  sub     rsp, 58h
0x10041d881  mov     [rsp+98h+var_68], 0FFFFFFFFFFFFFFFEh
0x10041d88a  lea     rsi, [rcx-10h]
0x10041d88e  xor     edi, edi
0x10041d890  test    rcx, rcx
0x10041d893  cmovz   rsi, rdi
0x10041d897  mov     rcx, [rcx+10h]
0x10041d89b  add     rcx, 30h ; '0'
0x10041d89f  mov     rdx, rsi
0x10041d8a2  call    ?RemoveElem@?$TList@VGroupList@@VSOS_ResourceGroup@@$0BA@UTListSLock@@@@QEAAXPEAVSOS_ResourceGroup@@@Z; TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(SOS_ResourceGroup *)
0x10041d8a7  mov     eax, [rsi+0B8h]
0x10041d8ad  lea     r13d, [rdi+1]
0x10041d8b1  cmp     eax, 2
0x10041d8b4  jnz     loc_10041DA3F
0x10041d8ba  mov     r14, [rsi+0A0h]
0x10041d8c1  add     r14, 1358h
0x10041d8c8  mov     [rsp+98h+var_60], r14
0x10041d8cd  mov     [rsp+98h+var_58], edi
0x10041d8d1  mov     ebx, edi
0x10041d8d3  mov     eax, gs:48h
0x10041d8db  mov     r15d, eax
0x10041d8de  mov     eax, [r14]
0x10041d8e1  test    eax, eax
0x10041d8e3  jnz     short loc_10041D8F9
0x10041d8e5  xor     eax, eax
0x10041d8e7  lock cmpxchg [r14], r15
0x10041d8ec  mov     eax, edi
0x10041d8ee  setz    al
0x10041d8f1  test    eax, eax
0x10041d8f3  jnz     loc_10041D9DF
0x10041d8f9  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10041d900  mov     ecx, [rax]
0x10041d902  and     ecx, 84h
0x10041d908  mov     rbp, rdi
0x10041d90b  cmp     cl, 84h
0x10041d90e  jnz     short loc_10041D972
0x10041d910  mov     rdx, gs:58h
0x10041d919  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041d920  mov     ecx, [rax]
0x10041d922  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041d929  mov     r8d, [rax]
0x10041d92c  add     r8, [rdx+rcx*8]
0x10041d930  jz      short loc_10041D942
0x10041d932  cmp     [r8+110h], r8
0x10041d939  jnz     short loc_10041D942
0x10041d93b  mov     rbp, [r8+100h]
0x10041d942  test    rbp, rbp
0x10041d945  jz      short loc_10041D972
0x10041d947  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10041d94e  cmp     [rax], ebx
0x10041d950  jz      short loc_10041D96A
0x10041d952  lea     rcx, [rsp+98h+PerformanceCount]; lpPerformanceCount
0x10041d95a  call    cs:__imp_QueryPerformanceCounter
0x10041d960  mov     rbx, qword ptr [rsp+98h+PerformanceCount]
0x10041d968  jmp     short loc_10041D972
0x10041d96a  mov     rbx, ds:7FFE0008h
0x10041d972  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10041d979  mov     rcx, r14
0x10041d97c  cmp     byte ptr [rax+0C7h], 0
0x10041d983  jge     short loc_10041D992
0x10041d985  mov     r8, r15
0x10041d988  mov     rdx, rbp
0x10041d98b  call    ?SpinToAcquireOptimistic@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<11,2,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10041d990  jmp     short loc_10041D99A
0x10041d992  mov     rdx, r15
0x10041d995  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAX_K@Z; Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10041d99a  test    rbp, rbp
0x10041d99d  jz      short loc_10041D9DF
0x10041d99f  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10041d9a6  cmp     dword ptr [rax], 0
0x10041d9a9  jz      short loc_10041D9C3
0x10041d9ab  lea     rcx, [rsp+98h+arg_18]; lpPerformanceCount
0x10041d9b3  call    cs:__imp_QueryPerformanceCounter
0x10041d9b9  mov     rax, qword ptr [rsp+98h+arg_18]
0x10041d9c1  jmp     short loc_10041D9CB
0x10041d9c3  mov     rax, ds:7FFE0008h
0x10041d9cb  mov     rcx, rax
0x10041d9ce  sub     rcx, rbx
0x10041d9d1  cmp     rax, rbx
0x10041d9d4  cmovb   rcx, rdi
0x10041d9d8  add     [rbp+0C78h], rcx
0x10041d9df  mov     [rsp+98h+var_58], r13d
0x10041d9e4  mov     rcx, [rsi+8]
0x10041d9e8  mov     rax, [rsi]
0x10041d9eb  mov     [rax+8], rcx
0x10041d9ef  mov     [rcx], rax
0x10041d9f2  mov     [rsi+8], rdi
0x10041d9f6  mov     [rsi], rdi
0x10041d9f9  mov     rbx, [rsp+98h+var_60]
0x10041d9fe  test    rbx, rbx
0x10041da01  jz      short loc_10041DA3F
0x10041da03  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10041da0a  cmp     byte ptr [rax], 0
0x10041da0d  jz      short loc_10041DA33
0x10041da0f  call    cs:__imp_rand
0x10041da15  mov     ecx, eax
0x10041da17  mov     eax, 66666667h
0x10041da1c  imul    ecx
0x10041da1e  sar     edx, 1
0x10041da20  mov     eax, edx
0x10041da22  shr     eax, 1Fh
0x10041da25  add     edx, eax
0x10041da27  lea     eax, [rdx+rdx*4]
0x10041da2a  cmp     ecx, eax
0x10041da2c  jnz     short loc_10041DA33
0x10041da2e  call    ?UpdateStatSnapshot@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXXZ; Spinlock<11,2,268435714>::UpdateStatSnapshot(void)
0x10041da33  mov     [rbx], rdi
0x10041da36  mov     [rsp+98h+var_60], rdi
0x10041da3b  mov     [rsp+98h+var_58], edi
0x10041da3f  mov     rdx, gs:58h
0x10041da48  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041da4f  mov     ecx, [rax]
0x10041da51  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041da58  mov     r8d, [rax]
0x10041da5b  add     r8, [rdx+rcx*8]
0x10041da5f  jz      loc_10041DB11
0x10041da65  cmp     [r8+110h], r8
0x10041da6c  jnz     loc_10041DB11
0x10041da72  mov     rax, [r8+100h]
0x10041da79  test    rax, rax
0x10041da7c  jz      loc_10041DB11
0x10041da82  cmp     [rax+210h], rsi
0x10041da89  jnz     loc_10041DB11
0x10041da8f  test    rsi, rsi
0x10041da92  jz      short loc_10041DA98
0x10041da94  lea     rdi, [rsi-8]
0x10041da98  mov     [rsp+98h+arg_0], rdi
0x10041daa0  lea     rax, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x10041daa7  mov     [rdi], rax
0x10041daaa  add     rdi, 8
0x10041daae  mov     [rsp+98h+arg_0], rdi
0x10041dab6  mov     rbx, [rdi+0B0h]
0x10041dabd  test    rbx, rbx
0x10041dac0  jz      loc_10041DF19
0x10041dac6  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10041dacd  test    byte ptr [rax], 8
0x10041dad0  jz      short loc_10041DADD
0x10041dad2  lock dec dword ptr [rbx+70h]
0x10041dad6  mov     rbx, [rdi+0B0h]
0x10041dadd  mov     eax, 0FFFFFFFFh
0x10041dae2  lock xadd [rbx+18h], eax
0x10041dae7  cmp     eax, 1
0x10041daea  jnz     loc_10041DF19
0x10041daf0  cmp     qword ptr [rbx+8], 0
0x10041daf5  jz      short loc_10041DB03
0x10041daf7  mov     rdx, rbx
0x10041dafa  mov     rcx, [rbx+10h]
0x10041dafe  call    ?RemoveElem@?$TList@VHostManager@@VSOSHost@@$0A@UTListSLock@@@@QEAAXPEAVSOSHost@@@Z; TList<HostManager,SOSHost,0,TListSLock>::RemoveElem(SOSHost *)
0x10041db03  mov     rcx, rbx
0x10041db06  call    cs:__imp_?Destroy@SOSHost@@AEAAXXZ; SOSHost::Destroy(void)
0x10041db0c  jmp     loc_10041DF19
0x10041db11  mov     rcx, [rsi+0A8h]
0x10041db18  test    rcx, rcx
0x10041db1b  jz      loc_10041DE63
0x10041db21  cmp     qword ptr [rcx+0F0h], 0
0x10041db29  jz      loc_10041DE63
0x10041db2f  call    cs:__imp_?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ; SOS_Node::IsTaskStoreDisabled(void)
0x10041db35  test    al, al
0x10041db37  jnz     loc_10041DE63
0x10041db3d  mov     rax, [rsi+0A8h]
0x10041db44  mov     rbp, [rax+0F0h]
0x10041db4b  test    rsi, rsi
0x10041db4e  lea     rcx, [rsi-8]
0x10041db52  jnz     short loc_10041DB57
0x10041db54  mov     rcx, rdi
0x10041db57  mov     [rsp+98h+arg_0], rcx
0x10041db5f  lea     rax, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x10041db66  mov     [rcx], rax
0x10041db69  add     rcx, 8
0x10041db6d  mov     [rsp+98h+arg_0], rcx
0x10041db75  mov     rbx, [rcx+0B0h]
0x10041db7c  test    rbx, rbx
0x10041db7f  jz      short loc_10041DBC3
0x10041db81  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10041db88  test    byte ptr [rax], 8
0x10041db8b  jz      short loc_10041DB98
0x10041db8d  lock dec dword ptr [rbx+70h]
0x10041db91  mov     rbx, [rcx+0B0h]
0x10041db98  mov     eax, 0FFFFFFFFh
0x10041db9d  lock xadd [rbx+18h], eax
0x10041dba2  cmp     eax, 1
0x10041dba5  jnz     short loc_10041DBC3
0x10041dba7  cmp     qword ptr [rbx+8], 0
0x10041dbac  jz      short loc_10041DBBA
0x10041dbae  mov     rdx, rbx
0x10041dbb1  mov     rcx, [rbx+10h]
0x10041dbb5  call    ?RemoveElem@?$TList@VHostManager@@VSOSHost@@$0A@UTListSLock@@@@QEAAXPEAVSOSHost@@@Z; TList<HostManager,SOSHost,0,TListSLock>::RemoveElem(SOSHost *)
0x10041dbba  mov     rcx, rbx
0x10041dbbd  call    cs:__imp_?Destroy@SOSHost@@AEAAXXZ; SOSHost::Destroy(void)
0x10041dbc3  lea     r14, [rsi-8]
0x10041dbc7  test    rsi, rsi
0x10041dbca  cmovz   r14, rdi
0x10041dbce  mov     rsi, [rbp+7E0h]
0x10041dbd5  mov     rbx, rdi
0x10041dbd8  mov     eax, gs:48h
0x10041dbe0  mov     r12d, eax
0x10041dbe3  mov     eax, [rsi+28h]
0x10041dbe6  test    eax, eax
0x10041dbe8  jnz     short loc_10041DBFF
0x10041dbea  xor     eax, eax
0x10041dbec  lock cmpxchg [rsi+28h], r12
0x10041dbf2  mov     eax, edi
0x10041dbf4  setz    al
0x10041dbf7  test    eax, eax
0x10041dbf9  jnz     loc_10041DCDA
0x10041dbff  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10041dc06  mov     ecx, [rax]
0x10041dc08  and     ecx, 84h
0x10041dc0e  mov     rbp, rdi
0x10041dc11  cmp     cl, 84h
0x10041dc14  jnz     short loc_10041DC72
0x10041dc16  mov     rdx, gs:58h
0x10041dc1f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041dc26  mov     ecx, [rax]
0x10041dc28  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041dc2f  mov     r8d, [rax]
0x10041dc32  add     r8, [rdx+rcx*8]
0x10041dc36  jz      short loc_10041DC48
0x10041dc38  cmp     [r8+110h], r8
0x10041dc3f  jnz     short loc_10041DC48
0x10041dc41  mov     rbp, [r8+100h]
0x10041dc48  test    rbp, rbp
0x10041dc4b  jz      short loc_10041DC72
0x10041dc4d  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10041dc54  cmp     [rax], ebx
0x10041dc56  jz      short loc_10041DC6A
0x10041dc58  lea     rcx, [rsp+98h+var_78]; lpPerformanceCount
0x10041dc5d  call    cs:__imp_QueryPerformanceCounter
0x10041dc63  mov     rbx, qword ptr [rsp+98h+var_78]
0x10041dc68  jmp     short loc_10041DC72
0x10041dc6a  mov     rbx, ds:7FFE0008h
0x10041dc72  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10041dc79  lea     rcx, [rsi+28h]
0x10041dc7d  cmp     byte ptr [rax+0C7h], 0
0x10041dc84  jge     short loc_10041DC93
0x10041dc86  mov     r8, r12
0x10041dc89  mov     rdx, rbp
0x10041dc8c  call    ?SpinToAcquireOptimistic@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<34,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10041dc91  jmp     short loc_10041DC9B
0x10041dc93  mov     rdx, r12
0x10041dc96  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10041dc9b  test    rbp, rbp
0x10041dc9e  jz      short loc_10041DCDA
0x10041dca0  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10041dca7  cmp     dword ptr [rax], 0
0x10041dcaa  jz      short loc_10041DCBE
0x10041dcac  lea     rcx, [rsp+98h+var_70]; lpPerformanceCount
0x10041dcb1  call    cs:__imp_QueryPerformanceCounter
0x10041dcb7  mov     rax, qword ptr [rsp+98h+var_70]
0x10041dcbc  jmp     short loc_10041DCC6
0x10041dcbe  mov     rax, ds:7FFE0008h
0x10041dcc6  mov     rcx, rax
0x10041dcc9  sub     rcx, rbx
0x10041dccc  cmp     rax, rbx
0x10041dccf  cmovb   rcx, rdi
0x10041dcd3  add     [rbp+0C78h], rcx
0x10041dcda  mov     rax, [rsi]
0x10041dcdd  cmp     [rsi+8], rax
0x10041dce1  jnb     loc_10041DE21
0x10041dce7  mov     rax, [rsi+20h]
0x10041dceb  cmp     byte ptr [rax+16BCh], 0
0x10041dcf2  jz      short loc_10041DD3D
0x10041dcf4  mov     ecx, [rsi+498h]
0x10041dcfa  and     ecx, 3Fh
0x10041dcfd  add     rcx, 9
0x10041dd01  shl     rcx, 4
0x10041dd05  add     rcx, rsi
0x10041dd08  mov     rax, [rcx]
0x10041dd0b  mov     [r14], rax
0x10041dd0e  cmp     qword ptr [rcx], 0
0x10041dd12  jnz     short loc_10041DD18
0x10041dd14  mov     [rcx+8], r14
0x10041dd18  mov     [rcx], r14
0x10041dd1b  inc     qword ptr [rsi+498h]
0x10041dd22  lea     r9, [rsp+98h+flOldProtect]; lpflOldProtect
0x10041dd2a  mov     r8d, r13d; flNewProtect
0x10041dd2d  mov     edx, 1000h; dwSize
0x10041dd32  mov     rcx, r14; lpAddress
0x10041dd35  call    cs:__imp_VirtualProtect
0x10041dd3b  jmp     short loc_10041DD5F
0x10041dd3d  mov     rax, [rsi+80h]
0x10041dd44  mov     [r14], rax
0x10041dd47  cmp     qword ptr [rsi+80h], 0
0x10041dd4f  jnz     short loc_10041DD58
0x10041dd51  mov     [rsi+88h], r14
0x10041dd58  mov     [rsi+80h], r14
0x10041dd5f  mov     rax, [rsi+490h]
0x10041dd66  inc     rax
0x10041dd69  inc     qword ptr [rsi+8]
0x10041dd6d  mov     rcx, [rsi+20h]; this
0x10041dd71  cmp     byte ptr [rcx+16BCh], 0
0x10041dd78  jnz     short loc_10041DDDE
  ... truncated ...
```
