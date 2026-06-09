# IOCompletionPortThreadPool::ShutdownCompletionPorts(void)

- ea: `0x1005b0a40`
- end: `0x1005b11bf`
- name: `?ShutdownCompletionPorts@IOCompletionPortThreadPool@@QEAAXXZ`
- size: `1919`
- prototype: `void __fastcall(IOCompletionPortThreadPool *__hidden this)`
- caller_count: `3`
- callee_count: `17`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1005b0500`
- `0x1005b0630`
- `0x1005b1d30`

## callees

- `0x100403990`
- `0x100406340`
- `0x100406510`
- `0x1004067b0`
- `0x1004086d0`
- `0x1004089c0`
- `0x100410810`
- `0x10041fdd0`
- `0x1004360f0`
- `0x1004371b0`
- `0x100475600`
- `0x100475810`
- `0x100475a50`
- `0x100475b60`
- `0x1004795c0`
- `0x1005b0a40`
- `0x1005b1fc0`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x1005b0f86`
- `KERNEL32!VirtualProtect` at `0x1005b0f86`
- `KERNEL32!QueryPerformanceCounter` at `0x1005b0cca`
- `KERNEL32!QueryPerformanceCounter` at `0x1005b0d15`
- `KERNEL32!QueryPerformanceCounter` at `0x1005b0eaf`
- `KERNEL32!QueryPerformanceCounter` at `0x1005b0ef9`
- `KERNEL32!QueryPerformanceCounter` at `0x1005b0cca`
- `KERNEL32!QueryPerformanceCounter` at `0x1005b0d15`
- `KERNEL32!QueryPerformanceCounter` at `0x1005b0eaf`
- `KERNEL32!QueryPerformanceCounter` at `0x1005b0ef9`
- `KERNEL32!CloseHandle` at `0x1005b0a70`
- `KERNEL32!CloseHandle` at `0x1005b0a70`
- `KERNEL32!VirtualFree` at `0x1005b10e1`
- `KERNEL32!VirtualFree` at `0x1005b10e1`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1005b1042`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1005b1085`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1005b1042`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1005b1085`

## string_xrefs

- `0x1005b0a85`: `"Sql\\Common\\src\\IOCompletionPortThreadPool.cpp"`
- `0x1005b0a8c`: `::CloseHandle(m_completionPort)`
- `0x1005b0bd8`: `Sql\Common\src\IOCompletionPortThreadPool.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall IOCompletionPortThreadPool::ShutdownCompletionPorts(IOCompletionPortThreadPool *this)
{
  void *v2; // rcx
  __int64 v3; // rbx
  __int64 v4; // rdi
  int v5; // eax
  int v6; // ebx
  unsigned int v7; // r15d
  __int64 v8; // rsi
  __int64 v9; // rcx
  __int64 v10; // rbx
  int v11; // edi
  __int64 *v12; // rdi
  LARGE_INTEGER v13; // rbx
  signed __int64 UniqueThread_low; // r14
  __int64 v15; // rsi
  __int64 v16; // rdx
  LARGE_INTEGER v17; // rax
  LONGLONG v18; // rcx
  _QWORD *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rax
  __int64 *v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rbx
  __int64 *v26; // rcx
  __int64 *v27; // r14
  __int64 v28; // rdi
  __int64 v29; // rsi
  LARGE_INTEGER v30; // rbx
  signed __int64 v31; // r15
  __int64 v32; // rdx
  SpinlockBase *v33; // rcx
  LARGE_INTEGER v34; // rax
  LONGLONG v35; // rcx
  __int64 *v36; // rcx
  unsigned __int64 v37; // r8
  SOS_ObjectStore *v38; // rcx
  unsigned int PoolIdForObject; // eax
  __int64 v40; // r9
  __int64 v41; // r10
  _QWORD *v42; // r8
  __int64 v43; // rax
  __int64 v44; // rcx
  int v45; // r8d
  int v46; // r8d
  __int64 *v47; // rcx
  __int64 v48; // rdx
  unsigned __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rcx
  _BYTE *v52; // rcx
  char *Format; // [rsp+20h] [rbp-E0h]
  SpinlockBase *v54; // [rsp+30h] [rbp-D0h] BYREF
  int v55; // [rsp+38h] [rbp-C8h]
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp-C0h] BYREF
  LARGE_INTEGER v57; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v58; // [rsp+50h] [rbp-B0h]
  __int64 *v59; // [rsp+58h] [rbp-A8h]
  LARGE_INTEGER v60; // [rsp+60h] [rbp-A0h] BYREF
  LARGE_INTEGER v61; // [rsp+68h] [rbp-98h] BYREF
  __int64 v62; // [rsp+70h] [rbp-90h]
  int v63; // [rsp+78h] [rbp-88h]
  __int64 v64; // [rsp+80h] [rbp-80h]
  int v65; // [rsp+88h] [rbp-78h] BYREF
  __int64 v66; // [rsp+90h] [rbp-70h]
  __int64 v67; // [rsp+98h] [rbp-68h]
  __int64 v68; // [rsp+A0h] [rbp-60h]
  __int64 v69; // [rsp+A8h] [rbp-58h]
  __int64 v70; // [rsp+B0h] [rbp-50h]
  _QWORD *v71; // [rsp+B8h] [rbp-48h]
  _QWORD *v72; // [rsp+C0h] [rbp-40h]
  __int64 *v73; // [rsp+C8h] [rbp-38h]
  __int64 *v74; // [rsp+D0h] [rbp-30h]
  _BYTE v75[8]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v76[136]; // [rsp+E8h] [rbp-18h] BYREF
  int v77; // [rsp+180h] [rbp+80h]
  DWORD flOldProtect; // [rsp+190h] [rbp+90h] BYREF
  __int64 v79; // [rsp+198h] [rbp+98h]

  v70 = -2;
  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    if ( !CloseHandle(v2) )
      utassert_fail(
        1u,
        "::CloseHandle(m_completionPort)",
        "\"Sql\\\\Common\\\\src\\\\IOCompletionPortThreadPool.cpp\"",
        0x18Eu,
        0);
    *((_QWORD *)this + 1) = 0;
  }
  if ( *((_QWORD *)this + 3) )
  {
    v63 = 0;
    v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
       + (unsigned int)SystemThread_TlsOffset;
    v4 = *(_QWORD *)(v3 + 256);
    v79 = v4;
    if ( !v4 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v4 = *(_QWORD *)(v3 + 256);
      v79 = v4;
    }
    v64 = v4;
    v5 = *(_DWORD *)(v4 + 616);
    v6 = !(*(_BYTE *)(v4 + 616) & 1);
    v63 = v6;
    *(_DWORD *)(v4 + 616) = v5 | 1;
    v7 = 0;
    v77 = 0;
    if ( *(_DWORD *)this )
    {
      do
      {
        v8 = 56LL * v7;
        v62 = v8;
        v9 = *(_QWORD *)(v8 + *((_QWORD *)this + 3) + 32);
        if ( v9 )
        {
          SOS_Task::SetAbort(v9, 0x7FFFFFFF);
          v65 = 4194612;
          v66 = 0;
          v68 = 0;
          v67 = 0;
          v69 = 0;
          v10 = *(_QWORD *)(v8 + *((_QWORD *)this + 3) + 32);
          v11 = 0;
          if ( *(char *)(v10 + 64) >= 0 )
            goto LABEL_15;
          if ( *(_DWORD *)(v10 + 184) != 2 )
          {
            SOS_WaitableAddress::SOS_WaitableAddress((SOS_WaitableAddress *)v75, (const void *const)(v10 + 64));
            if ( *(_DWORD *)(v10 + 184) != 2 )
            {
              LOBYTE(Format) = 1;
              v11 = WaitableBase::Wait(v76, 0xFFFFFFFFLL, &v65, 0, Format);
            }
            SOS_WaitableAddress::~SOS_WaitableAddress((SOS_WaitableAddress *)v75);
            if ( v11 )
LABEL_15:
              utassert_fail(1u, "SOS_OK == result", "Sql\\Common\\src\\IOCompletionPortThreadPool.cpp", 0x19Eu, 0);
          }
          v12 = *(__int64 **)(v8 + *((_QWORD *)this + 3) + 32);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 + 10, 0xFFFFFFFF) == 1 )
          {
            if ( v12[3] )
            {
              TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(v12 + 2);
            }
            else
            {
              if ( *((_DWORD *)v12 + 46) == 2 )
              {
                v54 = (SpinlockBase *)(v12[20] + 4952);
                v55 = 0;
                v13.QuadPart = 0;
                UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
                if ( *(_DWORD *)v54
                  || _InterlockedCompareExchange64((volatile signed __int64 *)v54, UniqueThread_low, 0) )
                {
                  v15 = 0;
                  if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
                  {
                    v16 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                        + (unsigned int)SystemThread_TlsOffset;
                    if ( v16 && *(_QWORD *)(v16 + 272) == v16 )
                      v15 = *(_QWORD *)(v16 + 256);
                    if ( v15 )
                    {
                      if ( Base_PublicGlobals::sm_invariantTscAvailable )
                      {
                        QueryPerformanceCounter(&PerformanceCount);
                        v13 = PerformanceCount;
                      }
                      else
                      {
                        v13.QuadPart = MEMORY[0x7FFE0008];
                      }
                    }
                  }
                  if ( (qword_1007149B5 & 0x800000) == 0 )
                    Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v54);
                  else
                    Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v54);
                  if ( v15 )
                  {
                    if ( Base_PublicGlobals::sm_invariantTscAvailable )
                    {
                      QueryPerformanceCounter(&v57);
                      v17 = v57;
                    }
                    else
                    {
                      v17.QuadPart = MEMORY[0x7FFE0008];
                    }
                    v18 = v17.QuadPart - v13.QuadPart;
                    if ( v17.QuadPart < (unsigned __int64)v13.QuadPart )
                      v18 = 0;
                    *(_QWORD *)(v15 + 3192) += v18;
                  }
                }
                v55 = 1;
                v19 = (_QWORD *)v12[1];
                v20 = *v12;
                *(_QWORD *)(v20 + 8) = v19;
                *v19 = v20;
                v12[1] = 0;
                *v12 = 0;
                SpinlockHolder<11,2,268435714>::~SpinlockHolder<11,2,268435714>(&v54);
              }
              v21 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                  + (unsigned int)SystemThread_TlsOffset;
              if ( v21
                && *(_QWORD *)(v21 + 272) == v21
                && (v22 = *(_QWORD *)(v21 + 256)) != 0
                && *(__int64 **)(v22 + 528) == v12 )
              {
                v23 = v12 - 1;
                if ( !v12 )
                  v23 = 0;
                v58 = v23;
                *v23 = (__int64)&ISOSHost_TaskImpl::`vftable';
                v71 = v23 + 1;
                SOS_Task::~SOS_Task((SOS_Task *)(v23 + 1));
              }
              else
              {
                v24 = v12[21];
                if ( !v24
                  || (v25 = *(_QWORD *)(v24 + 240)) == 0
                  || (*(_BYTE *)(v24 + 1568) & 2) != 0
                  || SOS_OS_TaskStoreDisabled )
                {
                  if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
                  {
                    v47 = v12 - 1;
                    if ( !v12 )
                      v47 = 0;
                    VirtualFree(v47, 0, 0x8000u);
                  }
                  else if ( v12 )
                  {
                    v73 = v12 - 1;
                    if ( v12 != (__int64 *)8 )
                    {
                      *(v12 - 1) = (__int64)&ISOSHost_TaskImpl::`vftable';
                      v74 = v12;
                      SOS_Task::~SOS_Task((SOS_Task *)v12);
                      operator delete(v12 - 1, 0x3E0u);
                    }
                  }
                }
                else
                {
                  v26 = v12 - 1;
                  if ( !v12 )
                    v26 = 0;
                  v59 = v26;
                  *v26 = (__int64)&ISOSHost_TaskImpl::`vftable';
                  v72 = v26 + 1;
                  SOS_Task::~SOS_Task((SOS_Task *)(v26 + 1));
                  v27 = v12 - 1;
                  if ( !v12 )
                    v27 = 0;
                  v28 = *(_QWORD *)(v25 + 2016);
                  v29 = 0;
                  v30.QuadPart = 0;
                  v31 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
                  if ( *(_DWORD *)(v28 + 40)
                    || _InterlockedCompareExchange64((volatile signed __int64 *)(v28 + 40), v31, 0) )
                  {
                    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
                    {
                      v32 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                          + (unsigned int)SystemThread_TlsOffset;
                      if ( v32 && *(_QWORD *)(v32 + 272) == v32 )
                        v29 = *(_QWORD *)(v32 + 256);
                      if ( v29 )
                      {
                        if ( Base_PublicGlobals::sm_invariantTscAvailable )
                        {
                          QueryPerformanceCounter(&v60);
                          v30 = v60;
                        }
                        else
                        {
                          v30.QuadPart = MEMORY[0x7FFE0008];
                        }
                      }
                    }
                    v33 = (SpinlockBase *)(v28 + 40);
                    if ( (qword_1007149B5 & 0x800000) == 0 )
                      Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v33);
                    else
                      Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v33);
                    if ( v29 )
                    {
                      if ( Base_PublicGlobals::sm_invariantTscAvailable )
                      {
                        QueryPerformanceCounter(&v61);
                        v34 = v61;
                      }
                      else
                      {
                        v34.QuadPart = MEMORY[0x7FFE0008];
                      }
                      v35 = v34.QuadPart - v30.QuadPart;
                      if ( v34.QuadPart < (unsigned __int64)v30.QuadPart )
                        v35 = 0;
                      *(_QWORD *)(v29 + 3192) += v35;
                    }
                  }
                  if ( *(_QWORD *)(v28 + 8) >= *(_QWORD *)v28 )
                  {
                    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                    {
                      v46 = rand();
                      if ( v46 == 5 * (v46 / 5) )
                        Spinlock<34,1,268435714>::UpdateStatSnapshot();
                    }
                    *(_QWORD *)(v28 + 40) = 0;
                    (*(void (__fastcall **)(__int64 *))(v28 + 48))(v27);
                    v7 = v77;
                  }
                  else
                  {
                    if ( *(_BYTE *)(*(_QWORD *)(v28 + 32) + 5820LL) )
                    {
                      v36 = (__int64 *)(v28 + 16 * ((*(_DWORD *)(v28 + 1176) & 0x3F) + 9LL));
                      *v27 = *v36;
                      if ( !*v36 )
                        v36[1] = (__int64)v27;
                      *v36 = (__int64)v27;
                      ++*(_QWORD *)(v28 + 1176);
                      VirtualProtect(v27, 0x1000u, 1u, &flOldProtect);
                    }
                    else
                    {
                      *v27 = *(_QWORD *)(v28 + 128);
                      if ( !*(_QWORD *)(v28 + 128) )
                        *(_QWORD *)(v28 + 136) = v27;
                      *(_QWORD *)(v28 + 128) = v27;
                    }
                    v37 = *(_QWORD *)(v28 + 1168) + 1LL;
                    ++*(_QWORD *)(v28 + 8);
                    v38 = *(SOS_ObjectStore **)(v28 + 32);
                    if ( !*((_BYTE *)v38 + 5820) && v37 >= 0x20 )
                    {
                      PoolIdForObject = SOS_ObjectStore::GetPoolIdForObject(v38, (struct SList *)v27);
                      v40 = v28 + 8LL * PoolIdForObject;
                      v41 = *(_QWORD *)(v28 + 128);
                      v42 = *(_QWORD **)(v28 + 136);
                      if ( v42 != (_QWORD *)(v28 + 128) && v42 )
                      {
                        *v42 = *(_QWORD *)(v40 + 1184);
                        *(_QWORD *)(v40 + 1184) = v41;
                      }
                      *(_QWORD *)(v28 + 128) = 0;
                      *(_QWORD *)(v28 + 136) = v28 + 128;
                      v37 = 0;
                      v43 = 1LL << PoolIdForObject;
                      v44 = *(_QWORD *)(v28 + 1696);
                      if ( (v43 & v44) == 0 )
                        *(_QWORD *)(v28 + 1696) = v44 | v43;
                    }
                    *(_QWORD *)(v28 + 1168) = v37;
                    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                    {
                      v45 = rand();
                      if ( v45 == 5 * (v45 / 5) )
                        Spinlock<34,1,268435714>::UpdateStatSnapshot();
                    }
                    *(_QWORD *)(v28 + 40) = 0;
                    v7 = v77;
                  }
                }
              }
            }
          }
          *(_QWORD *)(v62 + *((_QWORD *)this + 3) + 32) = 0;
        }
        v77 = ++v7;
      }
      while ( v7 < *(_DWORD *)this );
      v6 = v63;
      v4 = v79;
    }
    v48 = *((_QWORD *)this + 3);
    if ( v48 )
    {
      v49 = v48 & 0xFFFFFFFFFFFFE000uLL;
      if ( (v48 & 0xFFFFFFFFFFFFE000uLL) != 0 && *(_WORD *)((v48 & 0xFFFFFFFFFFFFE000uLL) + 4) == 512 )
        v49 = *(_QWORD *)((v48 & 0xFFFFFFFFFFFFE000uLL) + 0x28);
      v50 = *(_QWORD *)(v49 + 8);
      v51 = v48 & -*(_QWORD *)(v50 + 16);
      if ( v51 && *(_WORD *)((v48 & -*(_QWORD *)(v50 + 16)) + 4) == 512 )
        v51 = *(_QWORD *)((v48 & -*(_QWORD *)(v50 + 16)) + 0x28);
      v52 = *(_BYTE **)(v51 + 8);
      if ( (v52[40] & 8) == 0 )
        (*(void (__fastcall **)(_BYTE *, __int64, __int64))(*(_QWORD *)v52 + 40LL))(v52, v48, 512);
    }
    *((_QWORD *)this + 3) = 0;
    *(_DWORD *)(v4 + 616) &= ~v6;
  }
  *((_QWORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x1005b0a40  push    rbp
0x1005b0a42  push    rbx
0x1005b0a43  push    rsi
0x1005b0a44  push    rdi
0x1005b0a45  push    r12
0x1005b0a47  push    r13
0x1005b0a49  push    r14
0x1005b0a4b  push    r15
0x1005b0a4d  lea     rbp, [rsp-38h]
0x1005b0a52  sub     rsp, 138h
0x1005b0a59  mov     [rbp+70h+var_C0], 0FFFFFFFFFFFFFFFEh
0x1005b0a61  mov     r13, rcx
0x1005b0a64  mov     rcx, [rcx+8]; hObject
0x1005b0a68  xor     r12d, r12d
0x1005b0a6b  test    rcx, rcx
0x1005b0a6e  jz      short loc_1005B0A9F
0x1005b0a70  call    cs:__imp_CloseHandle
0x1005b0a76  test    eax, eax
0x1005b0a78  jnz     short loc_1005B0A9B
0x1005b0a7a  mov     [rsp+170h+Format], r12; Format
0x1005b0a7f  mov     r9d, 18Eh; int
0x1005b0a85  lea     r8, aSqlCommonSrcIo_0; "\"Sql\\\\Common\\\\src\\\\IOCompletionP"...
0x1005b0a8c  lea     rdx, aClosehandleMCo; "::CloseHandle(m_completionPort)"
0x1005b0a93  lea     ecx, [rax+1]; unsigned int
0x1005b0a96  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1005b0a9b  mov     [r13+8], r12
0x1005b0a9f  cmp     [r13+18h], r12
0x1005b0aa3  jz      loc_1005B11A7
0x1005b0aa9  mov     [rsp+170h+var_F8], r12d
0x1005b0aae  mov     rcx, gs:58h
0x1005b0ab7  mov     eax, cs:_tls_index
0x1005b0abd  mov     ebx, cs:SystemThread_TlsOffset
0x1005b0ac3  add     rbx, [rcx+rax*8]
0x1005b0ac7  mov     rdi, [rbx+100h]
0x1005b0ace  mov     [rbp+70h+arg_18], rdi
0x1005b0ad5  test    rdi, rdi
0x1005b0ad8  jnz     short loc_1005B0AEF
0x1005b0ada  xor     ecx, ecx; void *
0x1005b0adc  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1005b0ae1  mov     rdi, [rbx+100h]
0x1005b0ae8  mov     [rbp+70h+arg_18], rdi
0x1005b0aef  mov     [rbp+70h+var_F0], rdi
0x1005b0af3  mov     eax, [rdi+268h]
0x1005b0af9  mov     ebx, eax
0x1005b0afb  and     ebx, 1
0x1005b0afe  xor     ebx, 1
0x1005b0b01  mov     [rsp+170h+var_F8], ebx
0x1005b0b05  or      eax, 1
0x1005b0b08  mov     [rdi+268h], eax
0x1005b0b0e  mov     r15d, r12d
0x1005b0b11  mov     [rbp+70h+arg_0], r12d
0x1005b0b18  cmp     [r13+0], r12d
0x1005b0b1c  jbe     loc_1005B114B
0x1005b0b22  lea     r14, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x1005b0b29  nop     dword ptr [rax+00000000h]
0x1005b0b30  mov     eax, r15d
0x1005b0b33  imul    rsi, rax, 38h ; '8'
0x1005b0b37  mov     [rsp+170h+var_100], rsi
0x1005b0b3c  mov     rax, [r13+18h]
0x1005b0b40  mov     rcx, [rsi+rax+20h]
0x1005b0b45  test    rcx, rcx
0x1005b0b48  jz      loc_1005B112C
0x1005b0b4e  mov     edx, 7FFFFFFFh
0x1005b0b53  call    ?SetAbort@SOS_Task@@QEAAXW4TASK_ABORT_TYPE@1@@Z; SOS_Task::SetAbort(SOS_Task::TASK_ABORT_TYPE)
0x1005b0b58  mov     [rbp+70h+var_E8], 400134h
0x1005b0b5f  mov     [rbp+70h+var_E0], r12
0x1005b0b63  mov     [rbp+70h+var_D0], r12
0x1005b0b67  mov     [rbp+70h+var_D8], r12
0x1005b0b6b  mov     [rbp+70h+var_C8], r12
0x1005b0b6f  mov     rax, [r13+18h]
0x1005b0b73  mov     rbx, [rsi+rax+20h]
0x1005b0b78  mov     edi, r12d
0x1005b0b7b  lea     rdx, [rbx+40h]; void *
0x1005b0b7f  test    byte ptr [rdx], 80h
0x1005b0b82  jz      short loc_1005B0BCD
0x1005b0b84  mov     eax, [rbx+0B8h]
0x1005b0b8a  cmp     eax, 2
0x1005b0b8d  jz      short loc_1005B0BF0
0x1005b0b8f  lea     rcx, [rbp+70h+var_90]; this
0x1005b0b93  call    ??0SOS_WaitableAddress@@QEAA@QEBX@Z; SOS_WaitableAddress::SOS_WaitableAddress(void const * const)
0x1005b0b98  nop
0x1005b0b99  mov     eax, [rbx+0B8h]
0x1005b0b9f  cmp     eax, 2
0x1005b0ba2  jz      short loc_1005B0BC0
0x1005b0ba4  mov     byte ptr [rsp+170h+Format], 1
0x1005b0ba9  xor     r9d, r9d
0x1005b0bac  lea     r8, [rbp+70h+var_E8]
0x1005b0bb0  mov     edx, 0FFFFFFFFh
0x1005b0bb5  lea     rcx, [rbp+70h+var_88]
0x1005b0bb9  call    ?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z; WaitableBase::Wait(ulong,SOS_WaitInfo const *,SOS_SYNC_WAIT_OPTIONS,bool)
0x1005b0bbe  mov     edi, eax
0x1005b0bc0  lea     rcx, [rbp+70h+var_90]; this
0x1005b0bc4  call    ??1SOS_WaitableAddress@@QEAA@XZ; SOS_WaitableAddress::~SOS_WaitableAddress(void)
0x1005b0bc9  test    edi, edi
0x1005b0bcb  jz      short loc_1005B0BF0
0x1005b0bcd  mov     [rsp+170h+Format], r12; Format
0x1005b0bd2  mov     r9d, 19Eh; int
0x1005b0bd8  lea     r8, aSqlCommonSrcIo_1; "Sql\\Common\\src\\IOCompletionPortThrea"...
0x1005b0bdf  lea     rdx, aSosOkResult; "SOS_OK == result"
0x1005b0be6  mov     ecx, 1; unsigned int
0x1005b0beb  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1005b0bf0  mov     rax, [r13+18h]
0x1005b0bf4  mov     rdi, [rsi+rax+20h]
0x1005b0bf9  lea     rcx, [rdi+10h]
0x1005b0bfd  mov     eax, 0FFFFFFFFh
0x1005b0c02  lock xadd [rcx+18h], eax
0x1005b0c07  cmp     eax, 1
0x1005b0c0a  jnz     loc_1005B1117
0x1005b0c10  cmp     qword ptr [rcx+8], 0
0x1005b0c15  jz      short loc_1005B0C21
0x1005b0c17  call    ?RemoveAndDestroy@?$TListElem@V?$TList@VSOS_Scheduler@@VSOS_Task@@$0BA@UTListSLock@@@@@@IEAAXXZ; TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(void)
0x1005b0c1c  jmp     loc_1005B1117
0x1005b0c21  mov     eax, [rdi+0B8h]
0x1005b0c27  cmp     eax, 2
0x1005b0c2a  jnz     loc_1005B0D6C
0x1005b0c30  mov     rax, [rdi+0A0h]
0x1005b0c37  add     rax, 1358h
0x1005b0c3d  mov     [rsp+170h+var_140], rax
0x1005b0c42  mov     [rsp+170h+var_138], r12d
0x1005b0c47  mov     rbx, r12
0x1005b0c4a  mov     eax, gs:48h
0x1005b0c52  mov     r14d, eax
0x1005b0c55  mov     rax, [rsp+170h+var_140]
0x1005b0c5a  mov     ecx, [rax]
0x1005b0c5c  test    ecx, ecx
0x1005b0c5e  jnz     short loc_1005B0C7A
0x1005b0c60  mov     rcx, [rsp+170h+var_140]
0x1005b0c65  xor     eax, eax
0x1005b0c67  lock cmpxchg [rcx], r14
0x1005b0c6c  mov     eax, r12d
0x1005b0c6f  setz    al
0x1005b0c72  test    eax, eax
0x1005b0c74  jnz     loc_1005B0D3E
0x1005b0c7a  mov     eax, cs:?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1005b0c80  and     eax, 84h
0x1005b0c85  mov     rsi, r12
0x1005b0c88  cmp     al, 84h
0x1005b0c8a  jnz     short loc_1005B0CDF
0x1005b0c8c  mov     rcx, gs:58h
0x1005b0c95  mov     eax, cs:_tls_index
0x1005b0c9b  mov     edx, cs:SystemThread_TlsOffset
0x1005b0ca1  add     rdx, [rcx+rax*8]
0x1005b0ca5  jz      short loc_1005B0CB7
0x1005b0ca7  cmp     [rdx+110h], rdx
0x1005b0cae  jnz     short loc_1005B0CB7
0x1005b0cb0  mov     rsi, [rdx+100h]
0x1005b0cb7  test    rsi, rsi
0x1005b0cba  jz      short loc_1005B0CDF
0x1005b0cbc  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x1005b0cc3  jz      short loc_1005B0CD7
0x1005b0cc5  lea     rcx, [rsp+170h+PerformanceCount]; lpPerformanceCount
0x1005b0cca  call    cs:__imp_QueryPerformanceCounter
0x1005b0cd0  mov     rbx, qword ptr [rsp+170h+PerformanceCount]
0x1005b0cd5  jmp     short loc_1005B0CDF
0x1005b0cd7  mov     rbx, ds:7FFE0008h
0x1005b0cdf  mov     rcx, [rsp+170h+var_140]; this
0x1005b0ce4  test    byte ptr cs:qword_1007149B5+2, 80h
0x1005b0ceb  jz      short loc_1005B0CFA
0x1005b0ced  mov     r8, r14
0x1005b0cf0  mov     rdx, rsi
0x1005b0cf3  call    ?SpinToAcquireOptimistic@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<11,2,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x1005b0cf8  jmp     short loc_1005B0D02
0x1005b0cfa  mov     rdx, r14
0x1005b0cfd  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAX_K@Z; Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x1005b0d02  test    rsi, rsi
0x1005b0d05  jz      short loc_1005B0D3E
0x1005b0d07  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x1005b0d0e  jz      short loc_1005B0D22
0x1005b0d10  lea     rcx, [rsp+170h+var_128]; lpPerformanceCount
0x1005b0d15  call    cs:__imp_QueryPerformanceCounter
0x1005b0d1b  mov     rax, qword ptr [rsp+170h+var_128]
0x1005b0d20  jmp     short loc_1005B0D2A
0x1005b0d22  mov     rax, ds:7FFE0008h
0x1005b0d2a  mov     rcx, rax
0x1005b0d2d  sub     rcx, rbx
0x1005b0d30  cmp     rax, rbx
0x1005b0d33  cmovb   rcx, r12
0x1005b0d37  add     [rsi+0C78h], rcx
0x1005b0d3e  mov     [rsp+170h+var_138], 1
0x1005b0d46  mov     rcx, [rdi+8]
0x1005b0d4a  mov     rax, [rdi]
0x1005b0d4d  mov     [rax+8], rcx
0x1005b0d51  mov     [rcx], rax
0x1005b0d54  mov     [rdi+8], r12
0x1005b0d58  mov     [rdi], r12
0x1005b0d5b  lea     rcx, [rsp+170h+var_140]
0x1005b0d60  call    ??1?$SpinlockHolder@$0L@$01$0BAAAABAC@@@QEAA@XZ; SpinlockHolder<11,2,268435714>::~SpinlockHolder<11,2,268435714>(void)
0x1005b0d65  lea     r14, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x1005b0d6c  mov     rcx, gs:58h
0x1005b0d75  mov     eax, cs:_tls_index
0x1005b0d7b  mov     edx, cs:SystemThread_TlsOffset
0x1005b0d81  add     rdx, [rcx+rax*8]
0x1005b0d85  jz      short loc_1005B0DCB
0x1005b0d87  cmp     [rdx+110h], rdx
0x1005b0d8e  jnz     short loc_1005B0DCB
0x1005b0d90  mov     rax, [rdx+100h]
0x1005b0d97  test    rax, rax
0x1005b0d9a  jz      short loc_1005B0DCB
0x1005b0d9c  cmp     [rax+210h], rdi
0x1005b0da3  jnz     short loc_1005B0DCB
0x1005b0da5  test    rdi, rdi
0x1005b0da8  lea     rcx, [rdi-8]
0x1005b0dac  jnz     short loc_1005B0DB1
0x1005b0dae  mov     rcx, r12
0x1005b0db1  mov     [rsp+170h+var_120], rcx
0x1005b0db6  mov     [rcx], r14
0x1005b0db9  add     rcx, 8; this
0x1005b0dbd  mov     [rbp+70h+var_B8], rcx
0x1005b0dc1  call    ??1SOS_Task@@QEAA@XZ; SOS_Task::~SOS_Task(void)
0x1005b0dc6  jmp     loc_1005B1117
0x1005b0dcb  mov     rax, [rdi+0A8h]
0x1005b0dd2  test    rax, rax
0x1005b0dd5  jz      loc_1005B10C2
0x1005b0ddb  mov     rbx, [rax+0F0h]
0x1005b0de2  test    rbx, rbx
0x1005b0de5  jz      loc_1005B10C2
0x1005b0deb  test    byte ptr [rax+620h], 2
0x1005b0df2  jnz     loc_1005B10C2
0x1005b0df8  cmp     cs:?SOS_OS_TaskStoreDisabled@@3HA, 0; int SOS_OS_TaskStoreDisabled
0x1005b0dff  jnz     loc_1005B10C2
0x1005b0e05  test    rdi, rdi
0x1005b0e08  lea     rcx, [rdi-8]
0x1005b0e0c  jnz     short loc_1005B0E11
0x1005b0e0e  mov     rcx, r12
0x1005b0e11  mov     [rsp+170h+var_118], rcx
0x1005b0e16  mov     [rcx], r14
0x1005b0e19  add     rcx, 8; this
0x1005b0e1d  mov     [rbp+70h+var_B0], rcx
0x1005b0e21  call    ??1SOS_Task@@QEAA@XZ; SOS_Task::~SOS_Task(void)
0x1005b0e26  lea     r14, [rdi-8]
0x1005b0e2a  test    rdi, rdi
0x1005b0e2d  cmovz   r14, r12
0x1005b0e31  mov     rdi, [rbx+7E0h]
0x1005b0e38  xor     esi, esi
0x1005b0e3a  mov     ebx, esi
0x1005b0e3c  mov     eax, gs:48h
0x1005b0e44  mov     r15d, eax
0x1005b0e47  mov     eax, [rdi+28h]
0x1005b0e4a  test    eax, eax
0x1005b0e4c  jnz     short loc_1005B0E63
0x1005b0e4e  xor     eax, eax
0x1005b0e50  lock cmpxchg [rdi+28h], r15
0x1005b0e56  mov     eax, esi
0x1005b0e58  setz    al
0x1005b0e5b  test    eax, eax
0x1005b0e5d  jnz     loc_1005B0F29
0x1005b0e63  mov     eax, cs:?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1005b0e69  and     eax, 84h
0x1005b0e6e  cmp     al, 84h
0x1005b0e70  jnz     short loc_1005B0EC4
0x1005b0e72  mov     rcx, gs:58h
0x1005b0e7b  mov     eax, cs:_tls_index
0x1005b0e81  mov     edx, cs:SystemThread_TlsOffset
0x1005b0e87  add     rdx, [rcx+rax*8]
0x1005b0e8b  jz      short loc_1005B0E9D
0x1005b0e8d  cmp     [rdx+110h], rdx
0x1005b0e94  jnz     short loc_1005B0E9D
0x1005b0e96  mov     rsi, [rdx+100h]
0x1005b0e9d  test    rsi, rsi
0x1005b0ea0  jz      short loc_1005B0EC4
0x1005b0ea2  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, ebx; int Base_PublicGlobals::sm_invariantTscAvailable
0x1005b0ea8  jz      short loc_1005B0EBC
0x1005b0eaa  lea     rcx, [rsp+170h+var_110]; lpPerformanceCount
0x1005b0eaf  call    cs:__imp_QueryPerformanceCounter
0x1005b0eb5  mov     rbx, qword ptr [rsp+170h+var_110]
0x1005b0eba  jmp     short loc_1005B0EC4
0x1005b0ebc  mov     rbx, ds:7FFE0008h
0x1005b0ec4  lea     rcx, [rdi+28h]; this
0x1005b0ec8  test    byte ptr cs:qword_1007149B5+2, 80h
0x1005b0ecf  jz      short loc_1005B0EDE
0x1005b0ed1  mov     r8, r15
0x1005b0ed4  mov     rdx, rsi
0x1005b0ed7  call    ?SpinToAcquireOptimistic@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<34,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x1005b0edc  jmp     short loc_1005B0EE6
0x1005b0ede  mov     rdx, r15
0x1005b0ee1  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x1005b0ee6  test    rsi, rsi
0x1005b0ee9  jz      short loc_1005B0F27
0x1005b0eeb  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x1005b0ef2  jz      short loc_1005B0F06
0x1005b0ef4  lea     rcx, [rsp+170h+var_108]; lpPerformanceCount
0x1005b0ef9  call    cs:__imp_QueryPerformanceCounter
0x1005b0eff  mov     rax, qword ptr [rsp+170h+var_108]
0x1005b0f04  jmp     short loc_1005B0F0E
0x1005b0f06  mov     rax, ds:7FFE0008h
0x1005b0f0e  mov     rcx, rax
0x1005b0f11  sub     rcx, rbx
0x1005b0f14  cmp     rax, rbx
0x1005b0f17  mov     eax, 0
0x1005b0f1c  cmovb   rcx, rax
0x1005b0f20  add     [rsi+0C78h], rcx
0x1005b0f27  xor     esi, esi
0x1005b0f29  mov     rax, [rdi]
0x1005b0f2c  cmp     [rdi+8], rax
0x1005b0f30  jnb     loc_1005B107C
0x1005b0f36  mov     rax, [rdi+20h]
0x1005b0f3a  cmp     byte ptr [rax+16BCh], 0
0x1005b0f41  jz      short loc_1005B0F8E
0x1005b0f43  mov     ecx, [rdi+498h]
0x1005b0f49  and     ecx, 3Fh
  ... truncated ...
```
