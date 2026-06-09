# CryptoBase::EnqueueAuthTask(void * (*)(void *),void *)

- ea: `0x100446b10`
- end: `0x100447277`
- name: `?EnqueueAuthTask@CryptoBase@@IEAAKP6APEAXPEAX@Z0@Z`
- size: `1895`
- prototype: `unsigned int __fastcall(CryptoBase *__hidden this, void *(*)(void *), void *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x100444980`
- `0x100445bc0`

## callees

- `0x100403270`
- `0x10040bd60`
- `0x10040c0e0`
- `0x10040c7a0`
- `0x10040c9e0`
- `0x10040cc90`
- `0x10040ce80`
- `0x10040d0c0`
- `0x10040d370`
- `0x10040d490`
- `0x10042b7f0`
- `0x100446b10`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100446c8f`
- `KERNEL32!QueryPerformanceCounter` at `0x100446ce0`
- `KERNEL32!QueryPerformanceCounter` at `0x100446f7d`
- `KERNEL32!QueryPerformanceCounter` at `0x100446fcf`
- `KERNEL32!QueryPerformanceCounter` at `0x100446c8f`
- `KERNEL32!QueryPerformanceCounter` at `0x100446ce0`
- `KERNEL32!QueryPerformanceCounter` at `0x100446f7d`
- `KERNEL32!QueryPerformanceCounter` at `0x100446fcf`
- `KERNEL32!VirtualProtect` at `0x100447057`
- `KERNEL32!VirtualProtect` at `0x100447057`
- `KERNEL32!VirtualFree` at `0x1004471a7`
- `KERNEL32!VirtualFree` at `0x1004471a7`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100446d33`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100447107`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100447143`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x100447185`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100446c80`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100446cd0`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100446f6e`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100446fbf`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100446ca3`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100446f91`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x100446e59`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x100446e59`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100446e30`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100446edd`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100447213`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100446e30`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100446edd`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x100447213`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100447221`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100447221`
- `sqldk!SystemThread_TlsIndex` at `0x100446b50`
- `sqldk!SystemThread_TlsIndex` at `0x100446c52`
- `sqldk!SystemThread_TlsIndex` at `0x100446d7a`
- `sqldk!SystemThread_TlsIndex` at `0x100446f40`
- `sqldk!SystemThread_TlsOffset` at `0x100446b59`
- `sqldk!SystemThread_TlsOffset` at `0x100446c5b`
- `sqldk!SystemThread_TlsOffset` at `0x100446d83`
- `sqldk!SystemThread_TlsOffset` at `0x100446f49`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100446b72`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100446b72`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100446c35`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100446df5`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100446ea6`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100446f23`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004471dc`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100446d3f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100447113`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10044714f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100446d3f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100447113`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10044714f`

## string_xrefs

- `0x10044724d`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100447239`: `Task enqueueing succeeded: %d{WINERR}\n`
- `0x100447246`: `CryptoBase::EnqueueAuthTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CryptoBase::EnqueueAuthTask(CryptoBase *this, void *(*a2)(void *), void *a3)
{
  __int64 v5; // r14
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 result; // rax
  unsigned int v9; // r13d
  __int64 *v10; // rdi
  volatile signed __int64 *v11; // r15
  LARGE_INTEGER v12; // rbx
  signed __int64 UniqueThread_low; // r12
  __int64 v14; // r8
  LARGE_INTEGER v15; // rax
  LONGLONG v16; // rcx
  _QWORD *v17; // rcx
  __int64 v18; // rax
  volatile signed __int64 *v19; // rbx
  int v20; // r8d
  __int64 v21; // r8
  __int64 v22; // rax
  __int64 *v23; // rdi
  _QWORD *v24; // rdi
  __int64 v25; // rbx
  SOS_Node *v26; // rcx
  __int64 v27; // r14
  __int64 *v28; // rcx
  _QWORD *v29; // rcx
  __int64 v30; // rbx
  __int64 *v31; // rsi
  __int64 v32; // rdi
  __int64 v33; // r14
  LARGE_INTEGER v34; // rbx
  signed __int64 v35; // r12
  __int64 v36; // r8
  __int64 v37; // rcx
  LARGE_INTEGER v38; // rax
  LONGLONG v39; // rcx
  __int64 *v40; // rcx
  unsigned __int64 v41; // rax
  SOS_ObjectStore *v42; // rcx
  __int64 PoolIdForObject; // r11
  __int64 v44; // r9
  __int64 v45; // r10
  _QWORD *v46; // r8
  __int64 v47; // rcx
  int v48; // r8d
  int v49; // r8d
  __int64 *v50; // rcx
  __int64 *v51; // rdi
  __int64 v52; // rbx
  DWORD flOldProtect; // [rsp+30h] [rbp-50h] BYREF
  volatile signed __int32 *v54; // [rsp+38h] [rbp-48h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp-40h] BYREF
  LARGE_INTEGER v56; // [rsp+48h] [rbp-38h] BYREF
  LARGE_INTEGER v57; // [rsp+50h] [rbp-30h] BYREF
  LARGE_INTEGER v58; // [rsp+58h] [rbp-28h] BYREF
  __int64 v59; // [rsp+60h] [rbp-20h]
  volatile signed __int64 *v60; // [rsp+68h] [rbp-18h]
  int v61; // [rsp+70h] [rbp-10h]

  v59 = -2;
  v5 = 0;
  v54 = 0;
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v7 = *(_QWORD *)(v6 + 256);
  if ( !v7 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v7 = *(_QWORD *)(v6 + 256);
  }
  result = SOS_Node::EnqueueTaskDirect(*(_QWORD *)(v7 + 992), a2, a3, 1024, &v54, 0);
  v9 = result;
  if ( !(_DWORD)result )
  {
    v10 = (__int64 *)v54;
    if ( _InterlockedExchangeAdd(v54 + 10, 0xFFFFFFFF) == 1 )
    {
      if ( v10[3] )
      {
        TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(v10 + 2);
      }
      else
      {
        if ( *((_DWORD *)v10 + 46) == 2 )
        {
          v60 = (volatile signed __int64 *)(v10[20] + 4952);
          v11 = v60;
          v61 = 0;
          v12.QuadPart = 0;
          UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
          if ( *(_DWORD *)v60 || _InterlockedCompareExchange64(v60, UniqueThread_low, 0) )
          {
            if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
            {
              v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset;
              if ( v14 && *(_QWORD *)(v14 + 272) == v14 )
                v5 = *(_QWORD *)(v14 + 256);
              if ( v5 )
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
              Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v11, v5, UniqueThread_low);
            if ( v5 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v56);
                v15 = v56;
              }
              else
              {
                v15.QuadPart = MEMORY[0x7FFE0008];
              }
              v16 = v15.QuadPart - v12.QuadPart;
              if ( v15.QuadPart < (unsigned __int64)v12.QuadPart )
                v16 = 0;
              *(_QWORD *)(v5 + 3192) += v16;
            }
          }
          v61 = 1;
          v17 = (_QWORD *)v10[1];
          v18 = *v10;
          *(_QWORD *)(v18 + 8) = v17;
          *v17 = v18;
          v10[1] = 0;
          *v10 = 0;
          v19 = v60;
          if ( v60 )
          {
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v20 = rand();
              if ( v20 == 5 * (v20 / 5) )
                Spinlock<11,2,268435714>::UpdateStatSnapshot();
            }
            *v19 = 0;
            v60 = 0;
            v61 = 0;
          }
        }
        v21 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( v21
          && *(_QWORD *)(v21 + 272) == v21
          && (v22 = *(_QWORD *)(v21 + 256)) != 0
          && *(__int64 **)(v22 + 528) == v10 )
        {
          if ( v10 )
            v23 = v10 - 1;
          else
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
        }
        else
        {
          v26 = (SOS_Node *)v10[21];
          if ( v26 && *((_QWORD *)v26 + 30) && !SOS_Node::IsTaskStoreDisabled(v26) )
          {
            v27 = *(_QWORD *)(v10[21] + 240);
            v28 = v10 - 1;
            if ( !v10 )
              v28 = 0;
            *v28 = (__int64)&ISOSHost_TaskImpl::`vftable';
            v29 = v28 + 1;
            v30 = v29[22];
            if ( v30 )
            {
              if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
              {
                _InterlockedDecrement((volatile signed __int32 *)(v30 + 112));
                v30 = v29[22];
              }
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v30 + 24), 0xFFFFFFFF) == 1 )
              {
                if ( *(_QWORD *)(v30 + 8) )
                  TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*(_QWORD *)(v30 + 16), v30);
                SOSHost::Destroy((SOSHost *)v30);
              }
            }
            v31 = v10 - 1;
            if ( !v10 )
              v31 = 0;
            v32 = *(_QWORD *)(v27 + 2016);
            v33 = 0;
            v34.QuadPart = 0;
            v35 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
            if ( *(_DWORD *)(v32 + 40) || _InterlockedCompareExchange64((volatile signed __int64 *)(v32 + 40), v35, 0) )
            {
              if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
              {
                v36 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                    + SystemThread_TlsOffset;
                if ( v36 && *(_QWORD *)(v36 + 272) == v36 )
                  v33 = *(_QWORD *)(v36 + 256);
                if ( v33 )
                {
                  if ( Base_PublicGlobals::sm_invariantTscAvailable )
                  {
                    QueryPerformanceCounter(&v57);
                    v34 = v57;
                  }
                  else
                  {
                    v34.QuadPart = MEMORY[0x7FFE0008];
                  }
                }
              }
              v37 = v32 + 40;
              if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
                Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v37, v35);
              else
                Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v37, v33, v35);
              if ( v33 )
              {
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&v58);
                  v38 = v58;
                }
                else
                {
                  v38.QuadPart = MEMORY[0x7FFE0008];
                }
                v39 = v38.QuadPart - v34.QuadPart;
                if ( v38.QuadPart < (unsigned __int64)v34.QuadPart )
                  v39 = 0;
                *(_QWORD *)(v33 + 3192) += v39;
              }
            }
            if ( *(_QWORD *)(v32 + 8) >= *(_QWORD *)v32 )
            {
              if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
              {
                v49 = rand();
                if ( v49 == 5 * (v49 / 5) )
                  Spinlock<34,1,268435714>::UpdateStatSnapshot();
              }
              *(_QWORD *)(v32 + 40) = 0;
              (*(void (__fastcall **)(__int64 *))(v32 + 48))(v31);
            }
            else
            {
              if ( *(_BYTE *)(*(_QWORD *)(v32 + 32) + 5820LL) )
              {
                v40 = (__int64 *)(v32 + 16 * ((*(_DWORD *)(v32 + 1176) & 0x3F) + 9LL));
                *v31 = *v40;
                if ( !*v40 )
                  v40[1] = (__int64)v31;
                *v40 = (__int64)v31;
                ++*(_QWORD *)(v32 + 1176);
                VirtualProtect(v31, 0x1000u, 1u, &flOldProtect);
              }
              else
              {
                *v31 = *(_QWORD *)(v32 + 128);
                if ( !*(_QWORD *)(v32 + 128) )
                  *(_QWORD *)(v32 + 136) = v31;
                *(_QWORD *)(v32 + 128) = v31;
              }
              v41 = *(_QWORD *)(v32 + 1168) + 1LL;
              ++*(_QWORD *)(v32 + 8);
              v42 = *(SOS_ObjectStore **)(v32 + 32);
              if ( !*((_BYTE *)v42 + 5820) && v41 >= 0x20 )
              {
                PoolIdForObject = SOS_ObjectStore::GetPoolIdForObject(v42, (struct SList *)v31);
                v44 = v32 + 8 * PoolIdForObject;
                v45 = *(_QWORD *)(v32 + 128);
                v46 = *(_QWORD **)(v32 + 136);
                if ( v46 != (_QWORD *)(v32 + 128) && v46 )
                {
                  *v46 = *(_QWORD *)(v44 + 1184);
                  *(_QWORD *)(v44 + 1184) = v45;
                }
                *(_QWORD *)(v32 + 128) = 0;
                *(_QWORD *)(v32 + 136) = v32 + 128;
                v41 = 0;
                v47 = *(_QWORD *)(v32 + 1696);
                if ( (v47 & (1LL << PoolIdForObject)) == 0 )
                  *(_QWORD *)(v32 + 1696) = (1LL << PoolIdForObject) | v47;
              }
              *(_QWORD *)(v32 + 1168) = v41;
              if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
              {
                v48 = rand();
                if ( v48 == 5 * (v48 / 5) )
                  Spinlock<34,1,268435714>::UpdateStatSnapshot();
              }
              *(_QWORD *)(v32 + 40) = 0;
            }
          }
          else if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
          {
            v50 = v10 - 1;
            if ( !v10 )
              v50 = 0;
            VirtualFree(v50, 0, 0x8000u);
          }
          else if ( v10 )
          {
            v51 = v10 - 1;
            if ( v51 )
            {
              *v51 = (__int64)&ISOSHost_TaskImpl::`vftable';
              v52 = v51[23];
              if ( v52 )
              {
                if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
                {
                  _InterlockedDecrement((volatile signed __int32 *)(v52 + 112));
                  v52 = v51[23];
                }
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v52 + 24), 0xFFFFFFFF) == 1 )
                {
                  if ( *(_QWORD *)(v52 + 8) )
                    TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*(_QWORD *)(v52 + 16), v52);
                  SOSHost::Destroy((SOSHost *)v52);
                }
              }
              operator delete(v51, 0x3E0u);
            }
          }
        }
        v9 = 0;
      }
    }
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
        "CryptoBase::EnqueueAuthTask",
        2631,
        L"Task enqueueing succeeded: %d{WINERR}\n",
        0);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x100446b10  mov     [rsp-38h+arg_0], rcx
0x100446b15  push    rbp
0x100446b16  push    rsi
0x100446b17  push    rdi
0x100446b18  push    r12
0x100446b1a  push    r13
0x100446b1c  push    r14
0x100446b1e  push    r15
0x100446b20  mov     rbp, rsp
0x100446b23  sub     rsp, 80h
0x100446b2a  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x100446b32  mov     [rsp+80h+arg_8], rbx
0x100446b3a  mov     rdi, r8
0x100446b3d  mov     rsi, rdx
0x100446b40  xor     r14d, r14d
0x100446b43  mov     [rbp+var_48], r14
0x100446b47  mov     r9, gs:58h
0x100446b50  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100446b57  mov     ecx, [rax]
0x100446b59  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100446b60  mov     ebx, [rax]
0x100446b62  add     rbx, [r9+rcx*8]
0x100446b66  mov     rcx, [rbx+100h]
0x100446b6d  test    rcx, rcx
0x100446b70  jnz     short loc_100446B7F
0x100446b72  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100446b78  mov     rcx, [rbx+100h]
0x100446b7f  mov     [rsp+80h+var_58], r14
0x100446b84  lea     rax, [rbp+var_48]
0x100446b88  mov     [rsp+80h+var_60], rax
0x100446b8d  mov     r9d, 400h
0x100446b93  mov     r8, rdi
0x100446b96  mov     rdx, rsi
0x100446b99  mov     rcx, [rcx+3E0h]
0x100446ba0  call    ?EnqueueTaskDirect@SOS_Node@@QEAA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@PEAPEAX@Z; SOS_Node::EnqueueTaskDirect(void * (*)(void *),void *,ulong,SOS_Task * *,void * *)
0x100446ba5  mov     r13d, eax
0x100446ba8  mov     dword ptr [rbp+arg_0], eax
0x100446bab  test    eax, eax
0x100446bad  jnz     loc_10044725C
0x100446bb3  mov     rdi, [rbp+var_48]
0x100446bb7  mov     esi, 0FFFFFFFFh
0x100446bbc  mov     edx, esi
0x100446bbe  lock xadd [rdi+28h], edx
0x100446bc3  cmp     edx, 1
0x100446bc6  jnz     loc_10044722B
0x100446bcc  cmp     [rdi+18h], r14
0x100446bd0  jz      short loc_100446BE0
0x100446bd2  lea     rcx, [rdi+10h]
0x100446bd6  call    ?RemoveAndDestroy@?$TListElem@V?$TList@VSOS_Scheduler@@VSOS_Task@@$0BA@UTListSLock@@@@@@IEAAXXZ; TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(void)
0x100446bdb  jmp     loc_10044722B
0x100446be0  mov     eax, [rdi+0B8h]
0x100446be6  mov     r13d, 1
0x100446bec  cmp     eax, 2
0x100446bef  jnz     loc_100446D71
0x100446bf5  mov     r15, [rdi+0A0h]
0x100446bfc  add     r15, 1358h
0x100446c03  mov     [rbp+var_18], r15
0x100446c07  mov     [rbp+var_10], r14d
0x100446c0b  mov     rbx, r14
0x100446c0e  mov     eax, gs:48h
0x100446c16  mov     r12d, eax
0x100446c19  mov     eax, [r15]
0x100446c1c  test    eax, eax
0x100446c1e  jnz     short loc_100446C35
0x100446c20  xor     eax, eax
0x100446c22  lock cmpxchg [r15], r12
0x100446c27  mov     eax, r14d
0x100446c2a  setz    al
0x100446c2d  test    eax, eax
0x100446c2f  jnz     loc_100446D11
0x100446c35  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100446c3c  mov     ecx, [rax]
0x100446c3e  and     ecx, 84h
0x100446c44  cmp     cl, 84h
0x100446c47  jnz     short loc_100446CA3
0x100446c49  mov     rdx, gs:58h
0x100446c52  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100446c59  mov     ecx, [rax]
0x100446c5b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100446c62  mov     r8d, [rax]
0x100446c65  add     r8, [rdx+rcx*8]
0x100446c69  jz      short loc_100446C7B
0x100446c6b  cmp     [r8+110h], r8
0x100446c72  jnz     short loc_100446C7B
0x100446c74  mov     r14, [r8+100h]
0x100446c7b  test    r14, r14
0x100446c7e  jz      short loc_100446CA3
0x100446c80  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100446c87  cmp     [rax], ebx
0x100446c89  jz      short loc_100446C9B
0x100446c8b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x100446c8f  call    cs:__imp_QueryPerformanceCounter
0x100446c95  mov     rbx, qword ptr [rbp+PerformanceCount]
0x100446c99  jmp     short loc_100446CA3
0x100446c9b  mov     rbx, ds:7FFE0008h
0x100446ca3  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100446caa  mov     rcx, r15
0x100446cad  cmp     byte ptr [rax+0C7h], 0
0x100446cb4  jge     short loc_100446CC3
0x100446cb6  mov     r8, r12
0x100446cb9  mov     rdx, r14
0x100446cbc  call    ?SpinToAcquireOptimistic@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<11,2,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100446cc1  jmp     short loc_100446CCB
0x100446cc3  mov     rdx, r12
0x100446cc6  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAX_K@Z; Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100446ccb  test    r14, r14
0x100446cce  jz      short loc_100446D0E
0x100446cd0  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100446cd7  cmp     dword ptr [rax], 0
0x100446cda  jz      short loc_100446CEC
0x100446cdc  lea     rcx, [rbp+var_38]; lpPerformanceCount
0x100446ce0  call    cs:__imp_QueryPerformanceCounter
0x100446ce6  mov     rax, qword ptr [rbp+var_38]
0x100446cea  jmp     short loc_100446CF4
0x100446cec  mov     rax, ds:7FFE0008h
0x100446cf4  mov     rcx, rax
0x100446cf7  sub     rcx, rbx
0x100446cfa  cmp     rax, rbx
0x100446cfd  mov     r12d, 0
0x100446d03  cmovb   rcx, r12
0x100446d07  add     [r14+0C78h], rcx
0x100446d0e  xor     r14d, r14d
0x100446d11  mov     [rbp+var_10], r13d
0x100446d15  mov     rcx, [rdi+8]
0x100446d19  mov     rax, [rdi]
0x100446d1c  mov     [rax+8], rcx
0x100446d20  mov     [rcx], rax
0x100446d23  mov     [rdi+8], r14
0x100446d27  mov     [rdi], r14
0x100446d2a  mov     rbx, [rbp+var_18]
0x100446d2e  test    rbx, rbx
0x100446d31  jz      short loc_100446D71
0x100446d33  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x100446d3a  cmp     byte ptr [rax], 0
0x100446d3d  jz      short loc_100446D66
0x100446d3f  call    cs:__imp_rand
0x100446d45  mov     r8d, eax
0x100446d48  mov     eax, 66666667h
0x100446d4d  imul    r8d
0x100446d50  sar     edx, 1
0x100446d52  mov     ecx, edx
0x100446d54  shr     ecx, 1Fh
0x100446d57  add     edx, ecx
0x100446d59  lea     ecx, [rdx+rdx*4]
0x100446d5c  cmp     r8d, ecx
0x100446d5f  jnz     short loc_100446D66
0x100446d61  call    ?UpdateStatSnapshot@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXXZ; Spinlock<11,2,268435714>::UpdateStatSnapshot(void)
0x100446d66  mov     [rbx], r14
0x100446d69  mov     [rbp+var_18], r14
0x100446d6d  mov     [rbp+var_10], r14d
0x100446d71  mov     rdx, gs:58h
0x100446d7a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100446d81  mov     ecx, [rax]
0x100446d83  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100446d8a  mov     r8d, [rax]
0x100446d8d  add     r8, [rdx+rcx*8]
0x100446d91  jz      loc_100446E3B
0x100446d97  cmp     [r8+110h], r8
0x100446d9e  jnz     loc_100446E3B
0x100446da4  mov     rax, [r8+100h]
0x100446dab  test    rax, rax
0x100446dae  jz      loc_100446E3B
0x100446db4  cmp     [rax+210h], rdi
0x100446dbb  jnz     short loc_100446E3B
0x100446dbd  test    rdi, rdi
0x100446dc0  jz      short loc_100446DCC
0x100446dc2  add     rdi, 0FFFFFFFFFFFFFFF8h
0x100446dc6  mov     [rbp+arg_18], rdi
0x100446dca  jmp     short loc_100446DD3
0x100446dcc  mov     rdi, r14
0x100446dcf  mov     [rbp+arg_18], r14
0x100446dd3  lea     rax, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x100446dda  mov     [rdi], rax
0x100446ddd  add     rdi, 8
0x100446de1  mov     [rbp+arg_18], rdi
0x100446de5  mov     rbx, [rdi+0B0h]
0x100446dec  test    rbx, rbx
0x100446def  jz      loc_100447227
0x100446df5  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100446dfc  test    byte ptr [rax], 8
0x100446dff  jz      short loc_100446E0C
0x100446e01  lock dec dword ptr [rbx+70h]
0x100446e05  mov     rbx, [rdi+0B0h]
0x100446e0c  lock xadd [rbx+18h], esi
0x100446e11  cmp     esi, 1
0x100446e14  jnz     loc_100447227
0x100446e1a  cmp     qword ptr [rbx+8], 0
0x100446e1f  jz      short loc_100446E2D
0x100446e21  mov     rdx, rbx
0x100446e24  mov     rcx, [rbx+10h]
0x100446e28  call    ?RemoveElem@?$TList@VCertificateHashList@@VCertificateHash@@$0A@UTListSLock@@@@QEAAXPEAVCertificateHash@@@Z; TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(CertificateHash *)
0x100446e2d  mov     rcx, rbx
0x100446e30  call    cs:__imp_?Destroy@SOSHost@@AEAAXXZ; SOSHost::Destroy(void)
0x100446e36  jmp     loc_100447227
0x100446e3b  mov     rcx, [rdi+0A8h]
0x100446e42  test    rcx, rcx
0x100446e45  jz      loc_100447185
0x100446e4b  cmp     qword ptr [rcx+0F0h], 0
0x100446e53  jz      loc_100447185
0x100446e59  call    cs:__imp_?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ; SOS_Node::IsTaskStoreDisabled(void)
0x100446e5f  test    al, al
0x100446e61  jnz     loc_100447185
0x100446e67  mov     rax, [rdi+0A8h]
0x100446e6e  mov     r14, [rax+0F0h]
0x100446e75  xor     r12d, r12d
0x100446e78  test    rdi, rdi
0x100446e7b  lea     rcx, [rdi-8]
0x100446e7f  jnz     short loc_100446E84
0x100446e81  mov     ecx, r12d
0x100446e84  mov     [rbp+arg_18], rcx
0x100446e88  lea     rax, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x100446e8f  mov     [rcx], rax
0x100446e92  add     rcx, 8
0x100446e96  mov     [rbp+arg_18], rcx
0x100446e9a  mov     rbx, [rcx+0B0h]
0x100446ea1  test    rbx, rbx
0x100446ea4  jz      short loc_100446EE3
0x100446ea6  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100446ead  test    byte ptr [rax], 8
0x100446eb0  jz      short loc_100446EBD
0x100446eb2  lock dec dword ptr [rbx+70h]
0x100446eb6  mov     rbx, [rcx+0B0h]
0x100446ebd  lock xadd [rbx+18h], esi
0x100446ec2  cmp     esi, 1
0x100446ec5  jnz     short loc_100446EE3
0x100446ec7  cmp     qword ptr [rbx+8], 0
0x100446ecc  jz      short loc_100446EDA
0x100446ece  mov     rdx, rbx
0x100446ed1  mov     rcx, [rbx+10h]
0x100446ed5  call    ?RemoveElem@?$TList@VCertificateHashList@@VCertificateHash@@$0A@UTListSLock@@@@QEAAXPEAVCertificateHash@@@Z; TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(CertificateHash *)
0x100446eda  mov     rcx, rbx
0x100446edd  call    cs:__imp_?Destroy@SOSHost@@AEAAXXZ; SOSHost::Destroy(void)
0x100446ee3  lea     rsi, [rdi-8]
0x100446ee7  test    rdi, rdi
0x100446eea  cmovz   rsi, r12
0x100446eee  mov     rdi, [r14+7E0h]
0x100446ef5  xor     r14d, r14d
0x100446ef8  mov     ebx, r14d
0x100446efb  mov     eax, gs:48h
0x100446f03  mov     r12d, eax
0x100446f06  mov     eax, [rdi+28h]
0x100446f09  test    eax, eax
0x100446f0b  jnz     short loc_100446F23
0x100446f0d  xor     eax, eax
0x100446f0f  lock cmpxchg [rdi+28h], r12
0x100446f15  mov     eax, r14d
0x100446f18  setz    al
0x100446f1b  test    eax, eax
0x100446f1d  jnz     loc_100447000
0x100446f23  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100446f2a  mov     ecx, [rax]
0x100446f2c  and     ecx, 84h
0x100446f32  cmp     cl, 84h
0x100446f35  jnz     short loc_100446F91
0x100446f37  mov     rdx, gs:58h
0x100446f40  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100446f47  mov     ecx, [rax]
0x100446f49  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100446f50  mov     r8d, [rax]
0x100446f53  add     r8, [rdx+rcx*8]
0x100446f57  jz      short loc_100446F69
0x100446f59  cmp     [r8+110h], r8
0x100446f60  jnz     short loc_100446F69
0x100446f62  mov     r14, [r8+100h]
0x100446f69  test    r14, r14
0x100446f6c  jz      short loc_100446F91
0x100446f6e  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100446f75  cmp     [rax], ebx
0x100446f77  jz      short loc_100446F89
0x100446f79  lea     rcx, [rbp+var_30]; lpPerformanceCount
0x100446f7d  call    cs:__imp_QueryPerformanceCounter
0x100446f83  mov     rbx, qword ptr [rbp+var_30]
0x100446f87  jmp     short loc_100446F91
0x100446f89  mov     rbx, ds:7FFE0008h
0x100446f91  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100446f98  lea     rcx, [rdi+28h]
0x100446f9c  cmp     byte ptr [rax+0C7h], 0
0x100446fa3  jge     short loc_100446FB2
0x100446fa5  mov     r8, r12
0x100446fa8  mov     rdx, r14
0x100446fab  call    ?SpinToAcquireOptimistic@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<34,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100446fb0  jmp     short loc_100446FBA
0x100446fb2  mov     rdx, r12
0x100446fb5  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100446fba  test    r14, r14
0x100446fbd  jz      short loc_100446FFD
0x100446fbf  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100446fc6  cmp     dword ptr [rax], 0
0x100446fc9  jz      short loc_100446FDB
0x100446fcb  lea     rcx, [rbp+var_28]; lpPerformanceCount
0x100446fcf  call    cs:__imp_QueryPerformanceCounter
0x100446fd5  mov     rax, qword ptr [rbp+var_28]
0x100446fd9  jmp     short loc_100446FE3
0x100446fdb  mov     rax, ds:7FFE0008h
0x100446fe3  mov     rcx, rax
0x100446fe6  sub     rcx, rbx
0x100446fe9  cmp     rax, rbx
0x100446fec  mov     r12d, 0
0x100446ff2  cmovb   rcx, r12
0x100446ff6  add     [r14+0C78h], rcx
  ... truncated ...
```
