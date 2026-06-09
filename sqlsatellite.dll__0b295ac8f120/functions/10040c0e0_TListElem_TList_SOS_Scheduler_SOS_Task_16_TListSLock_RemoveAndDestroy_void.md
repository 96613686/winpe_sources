# TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(void)

- ea: `0x10040c0e0`
- end: `0x10040c79a`
- name: `?RemoveAndDestroy@?$TListElem@V?$TList@VSOS_Scheduler@@VSOS_Task@@$0BA@UTListSLock@@@@@@IEAAXXZ`
- size: `1722`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x100409790`
- `0x10040af40`
- `0x100446b10`
- `0x1004704c0`
- `0x100477b20`

## callees

- `0x100403270`
- `0x10040bf30`
- `0x10040c0e0`
- `0x10040c7a0`
- `0x10040c9e0`
- `0x10040cc90`
- `0x10040ce80`
- `0x10040d0c0`
- `0x10040d370`
- `0x10040d490`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10040c1ca`
- `KERNEL32!QueryPerformanceCounter` at `0x10040c223`
- `KERNEL32!QueryPerformanceCounter` at `0x10040c4cd`
- `KERNEL32!QueryPerformanceCounter` at `0x10040c521`
- `KERNEL32!QueryPerformanceCounter` at `0x10040c1ca`
- `KERNEL32!QueryPerformanceCounter` at `0x10040c223`
- `KERNEL32!QueryPerformanceCounter` at `0x10040c4cd`
- `KERNEL32!QueryPerformanceCounter` at `0x10040c521`
- `KERNEL32!VirtualProtect` at `0x10040c5a5`
- `KERNEL32!VirtualProtect` at `0x10040c5a5`
- `KERNEL32!VirtualFree` at `0x10040c6f5`
- `KERNEL32!VirtualFree` at `0x10040c6f5`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10040c273`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10040c655`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10040c691`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x10040c6d3`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040c1b7`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040c20f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040c4bd`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040c510`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10040c1e2`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10040c4e2`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x10040c39f`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x10040c39f`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10040c376`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10040c42d`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10040c775`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10040c376`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10040c42d`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10040c775`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10040c783`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10040c783`
- `sqldk!SystemThread_TlsIndex` at `0x10040c189`
- `sqldk!SystemThread_TlsIndex` at `0x10040c2b8`
- `sqldk!SystemThread_TlsIndex` at `0x10040c48f`
- `sqldk!SystemThread_TlsOffset` at `0x10040c192`
- `sqldk!SystemThread_TlsOffset` at `0x10040c2c1`
- `sqldk!SystemThread_TlsOffset` at `0x10040c498`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040c169`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040c336`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040c3f1`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040c46f`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040c739`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040c27f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040c661`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040c69d`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040c27f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040c661`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040c69d`

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
  TList<SOS_Scheduler,SOS_Task,16,TListSLock>::RemoveElem(*(_QWORD *)(a1 + 16) + 48LL, v1);
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
          TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*(_QWORD *)(v15 + 16), v15);
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
            TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*(_QWORD *)(v20 + 16), v20);
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
              TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*(_QWORD *)(v43 + 16), v43);
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
0x10040c0e0  push    rbx
0x10040c0e2  push    rbp
0x10040c0e3  push    rsi
0x10040c0e4  push    rdi
0x10040c0e5  push    r12
0x10040c0e7  push    r13
0x10040c0e9  push    r14
0x10040c0eb  push    r15
0x10040c0ed  sub     rsp, 58h
0x10040c0f1  mov     [rsp+98h+var_68], 0FFFFFFFFFFFFFFFEh
0x10040c0fa  lea     rsi, [rcx-10h]
0x10040c0fe  xor     edi, edi
0x10040c100  test    rcx, rcx
0x10040c103  cmovz   rsi, rdi
0x10040c107  mov     rcx, [rcx+10h]
0x10040c10b  add     rcx, 30h ; '0'
0x10040c10f  mov     rdx, rsi
0x10040c112  call    ?RemoveElem@?$TList@VSOS_Scheduler@@VSOS_Task@@$0BA@UTListSLock@@@@QEAAXPEAVSOS_Task@@@Z; TList<SOS_Scheduler,SOS_Task,16,TListSLock>::RemoveElem(SOS_Task *)
0x10040c117  mov     eax, [rsi+0B8h]
0x10040c11d  lea     r13d, [rdi+1]
0x10040c121  cmp     eax, 2
0x10040c124  jnz     loc_10040C2AF
0x10040c12a  mov     r14, [rsi+0A0h]
0x10040c131  add     r14, 1358h
0x10040c138  mov     [rsp+98h+var_60], r14
0x10040c13d  mov     [rsp+98h+var_58], edi
0x10040c141  mov     ebx, edi
0x10040c143  mov     eax, gs:48h
0x10040c14b  mov     r15d, eax
0x10040c14e  mov     eax, [r14]
0x10040c151  test    eax, eax
0x10040c153  jnz     short loc_10040C169
0x10040c155  xor     eax, eax
0x10040c157  lock cmpxchg [r14], r15
0x10040c15c  mov     eax, edi
0x10040c15e  setz    al
0x10040c161  test    eax, eax
0x10040c163  jnz     loc_10040C24F
0x10040c169  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10040c170  mov     ecx, [rax]
0x10040c172  and     ecx, 84h
0x10040c178  mov     rbp, rdi
0x10040c17b  cmp     cl, 84h
0x10040c17e  jnz     short loc_10040C1E2
0x10040c180  mov     rdx, gs:58h
0x10040c189  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040c190  mov     ecx, [rax]
0x10040c192  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040c199  mov     r8d, [rax]
0x10040c19c  add     r8, [rdx+rcx*8]
0x10040c1a0  jz      short loc_10040C1B2
0x10040c1a2  cmp     [r8+110h], r8
0x10040c1a9  jnz     short loc_10040C1B2
0x10040c1ab  mov     rbp, [r8+100h]
0x10040c1b2  test    rbp, rbp
0x10040c1b5  jz      short loc_10040C1E2
0x10040c1b7  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040c1be  cmp     [rax], ebx
0x10040c1c0  jz      short loc_10040C1DA
0x10040c1c2  lea     rcx, [rsp+98h+PerformanceCount]; lpPerformanceCount
0x10040c1ca  call    cs:__imp_QueryPerformanceCounter
0x10040c1d0  mov     rbx, qword ptr [rsp+98h+PerformanceCount]
0x10040c1d8  jmp     short loc_10040C1E2
0x10040c1da  mov     rbx, ds:7FFE0008h
0x10040c1e2  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10040c1e9  mov     rcx, r14
0x10040c1ec  cmp     byte ptr [rax+0C7h], 0
0x10040c1f3  jge     short loc_10040C202
0x10040c1f5  mov     r8, r15
0x10040c1f8  mov     rdx, rbp
0x10040c1fb  call    ?SpinToAcquireOptimistic@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<11,2,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10040c200  jmp     short loc_10040C20A
0x10040c202  mov     rdx, r15
0x10040c205  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAX_K@Z; Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10040c20a  test    rbp, rbp
0x10040c20d  jz      short loc_10040C24F
0x10040c20f  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040c216  cmp     dword ptr [rax], 0
0x10040c219  jz      short loc_10040C233
0x10040c21b  lea     rcx, [rsp+98h+arg_18]; lpPerformanceCount
0x10040c223  call    cs:__imp_QueryPerformanceCounter
0x10040c229  mov     rax, qword ptr [rsp+98h+arg_18]
0x10040c231  jmp     short loc_10040C23B
0x10040c233  mov     rax, ds:7FFE0008h
0x10040c23b  mov     rcx, rax
0x10040c23e  sub     rcx, rbx
0x10040c241  cmp     rax, rbx
0x10040c244  cmovb   rcx, rdi
0x10040c248  add     [rbp+0C78h], rcx
0x10040c24f  mov     [rsp+98h+var_58], r13d
0x10040c254  mov     rcx, [rsi+8]
0x10040c258  mov     rax, [rsi]
0x10040c25b  mov     [rax+8], rcx
0x10040c25f  mov     [rcx], rax
0x10040c262  mov     [rsi+8], rdi
0x10040c266  mov     [rsi], rdi
0x10040c269  mov     rbx, [rsp+98h+var_60]
0x10040c26e  test    rbx, rbx
0x10040c271  jz      short loc_10040C2AF
0x10040c273  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10040c27a  cmp     byte ptr [rax], 0
0x10040c27d  jz      short loc_10040C2A3
0x10040c27f  call    cs:__imp_rand
0x10040c285  mov     ecx, eax
0x10040c287  mov     eax, 66666667h
0x10040c28c  imul    ecx
0x10040c28e  sar     edx, 1
0x10040c290  mov     eax, edx
0x10040c292  shr     eax, 1Fh
0x10040c295  add     edx, eax
0x10040c297  lea     eax, [rdx+rdx*4]
0x10040c29a  cmp     ecx, eax
0x10040c29c  jnz     short loc_10040C2A3
0x10040c29e  call    ?UpdateStatSnapshot@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXXZ; Spinlock<11,2,268435714>::UpdateStatSnapshot(void)
0x10040c2a3  mov     [rbx], rdi
0x10040c2a6  mov     [rsp+98h+var_60], rdi
0x10040c2ab  mov     [rsp+98h+var_58], edi
0x10040c2af  mov     rdx, gs:58h
0x10040c2b8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040c2bf  mov     ecx, [rax]
0x10040c2c1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040c2c8  mov     r8d, [rax]
0x10040c2cb  add     r8, [rdx+rcx*8]
0x10040c2cf  jz      loc_10040C381
0x10040c2d5  cmp     [r8+110h], r8
0x10040c2dc  jnz     loc_10040C381
0x10040c2e2  mov     rax, [r8+100h]
0x10040c2e9  test    rax, rax
0x10040c2ec  jz      loc_10040C381
0x10040c2f2  cmp     [rax+210h], rsi
0x10040c2f9  jnz     loc_10040C381
0x10040c2ff  test    rsi, rsi
0x10040c302  jz      short loc_10040C308
0x10040c304  lea     rdi, [rsi-8]
0x10040c308  mov     [rsp+98h+arg_0], rdi
0x10040c310  lea     rax, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x10040c317  mov     [rdi], rax
0x10040c31a  add     rdi, 8
0x10040c31e  mov     [rsp+98h+arg_0], rdi
0x10040c326  mov     rbx, [rdi+0B0h]
0x10040c32d  test    rbx, rbx
0x10040c330  jz      loc_10040C789
0x10040c336  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10040c33d  test    byte ptr [rax], 8
0x10040c340  jz      short loc_10040C34D
0x10040c342  lock dec dword ptr [rbx+70h]
0x10040c346  mov     rbx, [rdi+0B0h]
0x10040c34d  mov     eax, 0FFFFFFFFh
0x10040c352  lock xadd [rbx+18h], eax
0x10040c357  cmp     eax, 1
0x10040c35a  jnz     loc_10040C789
0x10040c360  cmp     qword ptr [rbx+8], 0
0x10040c365  jz      short loc_10040C373
0x10040c367  mov     rdx, rbx
0x10040c36a  mov     rcx, [rbx+10h]
0x10040c36e  call    ?RemoveElem@?$TList@VCertificateHashList@@VCertificateHash@@$0A@UTListSLock@@@@QEAAXPEAVCertificateHash@@@Z; TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(CertificateHash *)
0x10040c373  mov     rcx, rbx
0x10040c376  call    cs:__imp_?Destroy@SOSHost@@AEAAXXZ; SOSHost::Destroy(void)
0x10040c37c  jmp     loc_10040C789
0x10040c381  mov     rcx, [rsi+0A8h]
0x10040c388  test    rcx, rcx
0x10040c38b  jz      loc_10040C6D3
0x10040c391  cmp     qword ptr [rcx+0F0h], 0
0x10040c399  jz      loc_10040C6D3
0x10040c39f  call    cs:__imp_?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ; SOS_Node::IsTaskStoreDisabled(void)
0x10040c3a5  test    al, al
0x10040c3a7  jnz     loc_10040C6D3
0x10040c3ad  mov     rax, [rsi+0A8h]
0x10040c3b4  mov     rbp, [rax+0F0h]
0x10040c3bb  test    rsi, rsi
0x10040c3be  lea     rcx, [rsi-8]
0x10040c3c2  jnz     short loc_10040C3C7
0x10040c3c4  mov     rcx, rdi
0x10040c3c7  mov     [rsp+98h+arg_0], rcx
0x10040c3cf  lea     rax, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x10040c3d6  mov     [rcx], rax
0x10040c3d9  add     rcx, 8
0x10040c3dd  mov     [rsp+98h+arg_0], rcx
0x10040c3e5  mov     rbx, [rcx+0B0h]
0x10040c3ec  test    rbx, rbx
0x10040c3ef  jz      short loc_10040C433
0x10040c3f1  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10040c3f8  test    byte ptr [rax], 8
0x10040c3fb  jz      short loc_10040C408
0x10040c3fd  lock dec dword ptr [rbx+70h]
0x10040c401  mov     rbx, [rcx+0B0h]
0x10040c408  mov     eax, 0FFFFFFFFh
0x10040c40d  lock xadd [rbx+18h], eax
0x10040c412  cmp     eax, 1
0x10040c415  jnz     short loc_10040C433
0x10040c417  cmp     qword ptr [rbx+8], 0
0x10040c41c  jz      short loc_10040C42A
0x10040c41e  mov     rdx, rbx
0x10040c421  mov     rcx, [rbx+10h]
0x10040c425  call    ?RemoveElem@?$TList@VCertificateHashList@@VCertificateHash@@$0A@UTListSLock@@@@QEAAXPEAVCertificateHash@@@Z; TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(CertificateHash *)
0x10040c42a  mov     rcx, rbx
0x10040c42d  call    cs:__imp_?Destroy@SOSHost@@AEAAXXZ; SOSHost::Destroy(void)
0x10040c433  lea     r14, [rsi-8]
0x10040c437  test    rsi, rsi
0x10040c43a  cmovz   r14, rdi
0x10040c43e  mov     rsi, [rbp+7E0h]
0x10040c445  mov     rbx, rdi
0x10040c448  mov     eax, gs:48h
0x10040c450  mov     r12d, eax
0x10040c453  mov     eax, [rsi+28h]
0x10040c456  test    eax, eax
0x10040c458  jnz     short loc_10040C46F
0x10040c45a  xor     eax, eax
0x10040c45c  lock cmpxchg [rsi+28h], r12
0x10040c462  mov     eax, edi
0x10040c464  setz    al
0x10040c467  test    eax, eax
0x10040c469  jnz     loc_10040C54A
0x10040c46f  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10040c476  mov     ecx, [rax]
0x10040c478  and     ecx, 84h
0x10040c47e  mov     rbp, rdi
0x10040c481  cmp     cl, 84h
0x10040c484  jnz     short loc_10040C4E2
0x10040c486  mov     rdx, gs:58h
0x10040c48f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040c496  mov     ecx, [rax]
0x10040c498  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040c49f  mov     r8d, [rax]
0x10040c4a2  add     r8, [rdx+rcx*8]
0x10040c4a6  jz      short loc_10040C4B8
0x10040c4a8  cmp     [r8+110h], r8
0x10040c4af  jnz     short loc_10040C4B8
0x10040c4b1  mov     rbp, [r8+100h]
0x10040c4b8  test    rbp, rbp
0x10040c4bb  jz      short loc_10040C4E2
0x10040c4bd  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040c4c4  cmp     [rax], ebx
0x10040c4c6  jz      short loc_10040C4DA
0x10040c4c8  lea     rcx, [rsp+98h+var_78]; lpPerformanceCount
0x10040c4cd  call    cs:__imp_QueryPerformanceCounter
0x10040c4d3  mov     rbx, qword ptr [rsp+98h+var_78]
0x10040c4d8  jmp     short loc_10040C4E2
0x10040c4da  mov     rbx, ds:7FFE0008h
0x10040c4e2  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10040c4e9  lea     rcx, [rsi+28h]
0x10040c4ed  cmp     byte ptr [rax+0C7h], 0
0x10040c4f4  jge     short loc_10040C503
0x10040c4f6  mov     r8, r12
0x10040c4f9  mov     rdx, rbp
0x10040c4fc  call    ?SpinToAcquireOptimistic@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<34,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10040c501  jmp     short loc_10040C50B
0x10040c503  mov     rdx, r12
0x10040c506  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10040c50b  test    rbp, rbp
0x10040c50e  jz      short loc_10040C54A
0x10040c510  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040c517  cmp     dword ptr [rax], 0
0x10040c51a  jz      short loc_10040C52E
0x10040c51c  lea     rcx, [rsp+98h+var_70]; lpPerformanceCount
0x10040c521  call    cs:__imp_QueryPerformanceCounter
0x10040c527  mov     rax, qword ptr [rsp+98h+var_70]
0x10040c52c  jmp     short loc_10040C536
0x10040c52e  mov     rax, ds:7FFE0008h
0x10040c536  mov     rcx, rax
0x10040c539  sub     rcx, rbx
0x10040c53c  cmp     rax, rbx
0x10040c53f  cmovb   rcx, rdi
0x10040c543  add     [rbp+0C78h], rcx
0x10040c54a  mov     rax, [rsi]
0x10040c54d  cmp     [rsi+8], rax
0x10040c551  jnb     loc_10040C691
0x10040c557  mov     rax, [rsi+20h]
0x10040c55b  cmp     byte ptr [rax+16BCh], 0
0x10040c562  jz      short loc_10040C5AD
0x10040c564  mov     ecx, [rsi+498h]
0x10040c56a  and     ecx, 3Fh
0x10040c56d  add     rcx, 9
0x10040c571  shl     rcx, 4
0x10040c575  add     rcx, rsi
0x10040c578  mov     rax, [rcx]
0x10040c57b  mov     [r14], rax
0x10040c57e  cmp     qword ptr [rcx], 0
0x10040c582  jnz     short loc_10040C588
0x10040c584  mov     [rcx+8], r14
0x10040c588  mov     [rcx], r14
0x10040c58b  inc     qword ptr [rsi+498h]
0x10040c592  lea     r9, [rsp+98h+flOldProtect]; lpflOldProtect
0x10040c59a  mov     r8d, r13d; flNewProtect
0x10040c59d  mov     edx, 1000h; dwSize
0x10040c5a2  mov     rcx, r14; lpAddress
0x10040c5a5  call    cs:__imp_VirtualProtect
0x10040c5ab  jmp     short loc_10040C5CF
0x10040c5ad  mov     rax, [rsi+80h]
0x10040c5b4  mov     [r14], rax
0x10040c5b7  cmp     qword ptr [rsi+80h], 0
0x10040c5bf  jnz     short loc_10040C5C8
0x10040c5c1  mov     [rsi+88h], r14
0x10040c5c8  mov     [rsi+80h], r14
0x10040c5cf  mov     rax, [rsi+490h]
0x10040c5d6  inc     rax
0x10040c5d9  inc     qword ptr [rsi+8]
0x10040c5dd  mov     rcx, [rsi+20h]; this
0x10040c5e1  cmp     byte ptr [rcx+16BCh], 0
0x10040c5e8  jnz     short loc_10040C64E
  ... truncated ...
```
