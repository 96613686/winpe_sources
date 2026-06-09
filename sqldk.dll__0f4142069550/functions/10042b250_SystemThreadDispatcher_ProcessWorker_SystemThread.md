# SystemThreadDispatcher::ProcessWorker(SystemThread *)

- ea: `0x10042b250`
- end: `0x10042b54d`
- name: `?ProcessWorker@SystemThreadDispatcher@@QEAAXPEAVSystemThread@@@Z`
- size: `765`
- prototype: `void(SystemThreadDispatcher *__hidden this, struct SystemThread *)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10042b6f0`

## callees

- `0x100402ae0`
- `0x100426960`
- `0x100426a00`
- `0x10042b250`
- `0x10042bb30`
- `0x10042bbd0`
- `0x10042f090`
- `0x100434d70`
- `0x1004360f0`
- `0x10043e700`
- `0x1004744a0`
- `0x1004746e0`
- `0x100477040`
- `0x1004771d0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x10042b569`
- `KERNEL32!WaitForSingleObject` at `0x10042b569`
- `KERNEL32!GetThreadIOPendingFlag` at `0x10042b50b`
- `KERNEL32!GetThreadIOPendingFlag` at `0x10046d567`
- `KERNEL32!GetThreadIOPendingFlag` at `0x10046d883`
- `KERNEL32!GetThreadIOPendingFlag` at `0x10042b50b`
- `KERNEL32!GetThreadIOPendingFlag` at `0x10046d567`
- `KERNEL32!GetThreadIOPendingFlag` at `0x10046d883`
- `KERNEL32!SetThreadPriority` at `0x10042b390`
- `KERNEL32!SetThreadPriority` at `0x10042b390`
- `KERNEL32!GetCurrentThread` at `0x10042b381`
- `KERNEL32!GetCurrentThread` at `0x10042b381`
- `KERNEL32!QueryPerformanceCounter` at `0x10046d4bd`
- `KERNEL32!QueryPerformanceCounter` at `0x10046d4fb`
- `KERNEL32!QueryPerformanceCounter` at `0x10046d673`
- `KERNEL32!QueryPerformanceCounter` at `0x10046d6b9`
- `KERNEL32!QueryPerformanceCounter` at `0x10046d7fd`
- `KERNEL32!QueryPerformanceCounter` at `0x10046d843`
- `KERNEL32!QueryPerformanceCounter` at `0x10046d4bd`
- `KERNEL32!QueryPerformanceCounter` at `0x10046d4fb`
- `KERNEL32!QueryPerformanceCounter` at `0x10046d673`
- `KERNEL32!QueryPerformanceCounter` at `0x10046d6b9`
- `KERNEL32!QueryPerformanceCounter` at `0x10046d7fd`
- `KERNEL32!QueryPerformanceCounter` at `0x10046d843`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10046d585`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10046d731`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10046d8ac`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10046d9bb`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10046da06`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10046d585`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10046d731`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10046d8ac`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10046d9bb`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10046da06`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall SystemThreadDispatcher::ProcessWorker(SystemThreadDispatcher *this, struct SystemThread *a2)
{
  __int64 v4; // r12
  SpinlockBase *v5; // r15
  LARGE_INTEGER v6; // rbx
  signed __int64 UniqueThread_low; // r14
  SystemThreadDispatcher *v8; // rcx
  char *v9; // rbx
  char *v10; // rsi
  _QWORD *v11; // rcx
  __int64 v12; // rax
  int *v13; // rbx
  HANDLE CurrentThread; // rax
  __int64 v15; // rsi
  __int64 v16; // rbx
  __int64 v17; // r8
  int v18; // edx
  __int64 v19; // r14
  __int64 v20; // rsi
  __int64 v21; // r15
  __int64 v22; // rcx
  DWORD v23; // esi
  DWORD v24; // eax
  DWORD v25; // ebx
  int v26; // edx
  __int64 v27; // rsi
  __int64 v28; // rdx
  LARGE_INTEGER v29; // rcx
  LONGLONG v30; // rax
  int v31; // r8d
  LARGE_INTEGER v32; // rbx
  signed __int64 v33; // r14
  __int64 v34; // rsi
  __int64 v35; // rdx
  LARGE_INTEGER v36; // rcx
  LONGLONG v37; // rax
  SystemThreadDispatcher *v38; // rcx
  struct SystemThread *i; // rbx
  int v40; // eax
  __int64 v41; // r9
  __int64 v42; // rdx
  __int64 v43; // rcx
  LARGE_INTEGER v44; // rbx
  signed __int64 v45; // r14
  __int64 v46; // rsi
  __int64 v47; // rdx
  LARGE_INTEGER v48; // rcx
  LONGLONG v49; // rax
  int v50; // eax
  __int64 v51; // r9
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // rax
  int v55; // r8d
  int v56; // eax
  __int64 v57; // r9
  __int64 v58; // rdx
  __int64 v59; // rcx
  LARGE_INTEGER PerformanceCount; // [rsp+50h] [rbp-29h] BYREF
  LARGE_INTEGER v61; // [rsp+58h] [rbp-21h] BYREF
  LARGE_INTEGER v62; // [rsp+60h] [rbp-19h] BYREF
  LARGE_INTEGER v63; // [rsp+68h] [rbp-11h] BYREF
  LARGE_INTEGER v64; // [rsp+70h] [rbp-9h] BYREF
  LARGE_INTEGER v65; // [rsp+78h] [rbp-1h] BYREF
  volatile signed __int32 *v66; // [rsp+80h] [rbp+7h]
  __int64 v67; // [rsp+88h] [rbp+Fh]
  WINBOOL v68; // [rsp+E0h] [rbp+67h] BYREF
  WINBOOL v69; // [rsp+E8h] [rbp+6Fh] BYREF
  WINBOOL IOIsPending; // [rsp+F0h] [rbp+77h] BYREF

  v67 = -2;
  v4 = *((_QWORD *)a2 + 32);
  v66 = (volatile signed __int32 *)((char *)this + 4);
  _InterlockedIncrement((volatile signed __int32 *)this + 1);
  _InterlockedDecrement((volatile signed __int32 *)this);
  v5 = (SystemThreadDispatcher *)((char *)this + 64);
  while ( 1 )
  {
    v6.QuadPart = 0;
    UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( *(_DWORD *)v5 || _InterlockedCompareExchange64((volatile signed __int64 *)v5, UniqueThread_low, 0) )
    {
      v27 = 0;
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v28 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
            + (unsigned int)SystemThread_TlsOffset;
        if ( v28 && *(_QWORD *)(v28 + 272) == v28 )
          v27 = *(_QWORD *)(v28 + 256);
        if ( v27 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&PerformanceCount);
            v6 = PerformanceCount;
          }
          else
          {
            v6.QuadPart = MEMORY[0x7FFE0008];
          }
        }
      }
      if ( (qword_1007149B5 & 0x800000) == 0 )
        Spinlock<32,1,268435714>::SpinToAcquireWithExponentialBackoff(v5);
      else
        Spinlock<32,1,268435714>::SpinToAcquireOptimistic(v5);
      if ( v27 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v61);
          v29 = v61;
        }
        else
        {
          v29.QuadPart = MEMORY[0x7FFE0008];
        }
        v30 = 0;
        if ( v29.QuadPart >= (unsigned __int64)v6.QuadPart )
          v30 = v29.QuadPart - v6.QuadPart;
        *(_QWORD *)(v27 + 3192) += v30;
      }
    }
    v8 = (SystemThreadDispatcher *)*((_QWORD *)this + 3);
    v9 = 0;
    if ( v8 == (SystemThreadDispatcher *)((char *)this + 16) )
    {
      v10 = 0;
    }
    else
    {
      if ( v8 )
        v9 = (char *)v8 - 8;
      v10 = v9;
      if ( v9 )
      {
        v11 = (_QWORD *)*((_QWORD *)v9 + 2);
        v12 = *((_QWORD *)v9 + 1);
        *(_QWORD *)(v12 + 8) = v11;
        *v11 = v12;
        *((_QWORD *)v9 + 2) = 0;
        *((_QWORD *)v9 + 1) = 0;
        goto LABEL_9;
      }
    }
    if ( (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 7) + 280LL) + 1568LL) & 8) != 0
      && *((SystemThreadDispatcher **)this + 5) != (SystemThreadDispatcher *)((char *)this + 32)
      || *((_QWORD *)this + 6) >= (unsigned __int64)*((unsigned int *)this + 18) )
    {
      break;
    }
LABEL_38:
    *((_QWORD *)a2 + 22) = *((_QWORD *)this + 5);
    **((_QWORD **)this + 5) = (char *)a2 + 168;
    *((_QWORD *)this + 5) = (char *)a2 + 168;
    *((_QWORD *)a2 + 21) = (char *)this + 32;
    ++*((_QWORD *)this + 6);
LABEL_9:
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v31 = rand();
      if ( v31 == 5 * (v31 / 5) )
        ((void (*)(void))Spinlock<32,1,268435714>::UpdateStatSnapshot)();
    }
    *(_QWORD *)v5 = 0;
    if ( v9 )
    {
      SystemThreadDispatcher::StartNewSysThreadIfRequired(this);
      BindSystemThreadAndWorker(a2, (struct Worker *const)v9);
      *((_DWORD *)a2 + 66) &= 0xFFFFFFFC;
      SystemThread::ChangeCPUId(a2, *((_DWORD *)v9 + 19));
LABEL_12:
      v13 = (int *)*((_QWORD *)v10 + 76);
      SystemThread::SetScheduler(a2, (struct SOS_Scheduler *)v13);
      CurrentThread = GetCurrentThread();
      SetThreadPriority(CurrentThread, v13[1288]);
      SystemThread::RefreshAffinity(a2, 0);
      (*(void (__fastcall **)(int *, struct SystemThread *, char *))(*(_QWORD *)v13 + 56LL))(v13, a2, v10);
      SystemThread::SetScheduler(a2, 0);
      v15 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
          + (unsigned int)SystemThread_TlsOffset;
      v16 = *(_QWORD *)(v15 + 256);
      if ( !v16 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v16 = *(_QWORD *)(v15 + 256);
      }
      BindSystemThreadAndWorker(a2, (struct Worker *const)v4);
      *((_DWORD *)a2 + 66) &= ~1u;
      *((_DWORD *)a2 + 66) |= 2u;
      *(_DWORD *)(v4 + 76) = *((_DWORD *)a2 + 54);
      v17 = *(_QWORD *)(v16 + 608);
      v18 = *((_DWORD *)a2 + 84);
      if ( (v18 & 4) != 0 )
      {
        v19 = *(_QWORD *)(v4 + 992);
        v20 = *(_QWORD *)(v4 + 608);
        v21 = *(_QWORD *)(v4 + 1000);
        v22 = *(_QWORD *)(v17 + 3696);
        *(_QWORD *)(v4 + 992) = *(_QWORD *)(v16 + 992);
        *(_QWORD *)(v4 + 608) = v17;
        *(_QWORD *)(v4 + 1000) = v22;
        *(_DWORD *)(v4 + 76) = *(_DWORD *)(v17 + 3536);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v16 + 48), 0xFFFFFFFF) == 1 )
        {
          if ( *(_QWORD *)(v16 + 32) )
            TList<SchedulerManager,Worker,24,TListSLock>::RemoveElem(*(_QWORD *)(v16 + 40), v16);
          Worker::Destroy((Worker *)v16);
        }
        _InterlockedIncrement(&SOS_OS_WorkersAvailable);
        if ( SOS_OS::sm_WorkerPressureCount > 0 )
          _InterlockedDecrement(&SOS_OS::sm_WorkerPressureCount);
        *((_DWORD *)a2 + 84) &= ~4u;
        *(_QWORD *)(v4 + 992) = v19;
        *(_QWORD *)(v4 + 608) = v20;
        *(_QWORD *)(v4 + 1000) = v21;
        v5 = (SystemThreadDispatcher *)((char *)this + 64);
        if ( v20 )
          *(_DWORD *)(v4 + 76) = *(_DWORD *)(v20 + 3536);
      }
      else if ( (v18 & 1) != 0 )
      {
        SOS_Scheduler::ResumeNoCuzz(v16, (*((_DWORD *)a2 + 84) & 2) == 0, 0);
        *((_DWORD *)a2 + 84) &= 0xFFFFFFFC;
      }
      if ( (*((_DWORD *)a2 + 66) & 8) != 0 )
      {
        IOIsPending = 0;
        if ( !GetThreadIOPendingFlag(*((HANDLE *)a2 + 37), &IOIsPending) || !IOIsPending )
        {
          _InterlockedDecrement((volatile signed __int32 *)this + 1);
          SystemThreadDispatcher::StartNewSysThreadIfRequired(this);
          _InterlockedIncrement((volatile signed __int32 *)this + 1);
LABEL_27:
          _InterlockedDecrement((volatile signed __int32 *)this + 1);
          return;
        }
      }
    }
    else
    {
      while ( 2 )
      {
        v23 = SOS_PublicGlobals::sm_IdleTimeOut;
        while ( 1 )
        {
          v24 = WaitForSingleObject(*((HANDLE *)a2 + 40), v23);
          v25 = v24;
          if ( v23 != -1 || *((_QWORD *)a2 + 31) || (v26 = 1, v24 == 192) )
            v26 = 0;
          SystemThread::LogSpuriousEvent(a2, v26, v24);
          if ( *((_QWORD *)a2 + 31) )
            break;
          if ( v25 )
            goto LABEL_67;
        }
        if ( !v25 )
        {
          *((_QWORD *)a2 + 31) = 0;
          v10 = (char *)*((_QWORD *)a2 + 32);
          if ( v10 )
            goto LABEL_12;
          break;
        }
LABEL_67:
        v32.QuadPart = 0;
        v33 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        if ( *(_DWORD *)v5 || _InterlockedCompareExchange64((volatile signed __int64 *)v5, v33, 0) )
        {
          v34 = 0;
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
          {
            v35 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                + (unsigned int)SystemThread_TlsOffset;
            if ( v35 && *(_QWORD *)(v35 + 272) == v35 )
              v34 = *(_QWORD *)(v35 + 256);
            if ( v34 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v62);
                v32 = v62;
              }
              else
              {
                v32.QuadPart = MEMORY[0x7FFE0008];
              }
            }
          }
          if ( (qword_1007149B5 & 0x800000) == 0 )
            Spinlock<32,1,268435714>::SpinToAcquireWithExponentialBackoff(v5);
          else
            Spinlock<32,1,268435714>::SpinToAcquireOptimistic(v5);
          if ( v34 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v63);
              v36 = v63;
            }
            else
            {
              v36.QuadPart = MEMORY[0x7FFE0008];
            }
            v37 = 0;
            if ( v36.QuadPart >= (unsigned __int64)v32.QuadPart )
              v37 = v36.QuadPart - v32.QuadPart;
            *(_QWORD *)(v34 + 3192) += v37;
          }
        }
        v38 = (SystemThreadDispatcher *)*((_QWORD *)this + 5);
        for ( i = 0; v38 != (SystemThreadDispatcher *)((char *)this + 32); i = 0 )
        {
          if ( v38 )
            i = (SystemThreadDispatcher *)((char *)v38 - 168);
          if ( !i )
            break;
          v38 = (SystemThreadDispatcher *)*((_QWORD *)i + 22);
          if ( i == a2 )
          {
            v54 = *((_QWORD *)i + 21);
            *(_QWORD *)(v54 + 8) = v38;
            *(_QWORD *)v38 = v54;
            *((_QWORD *)i + 22) = 0;
            *((_QWORD *)i + 21) = 0;
            --*((_QWORD *)this + 6);
            break;
          }
        }
        if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v40 = rand();
          v42 = (unsigned int)(v40 / 5);
          v43 = (unsigned int)(5 * v42);
          if ( v40 == (_DWORD)v43 )
            Spinlock<32,1,268435714>::UpdateStatSnapshot(v43, v42, (unsigned int)v40, v41);
        }
        *(_QWORD *)v5 = 0;
        if ( !i )
          continue;
        break;
      }
      v44.QuadPart = 0;
      v45 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( *(_DWORD *)v5 || _InterlockedCompareExchange64((volatile signed __int64 *)v5, v45, 0) )
      {
        v46 = 0;
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v47 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
              + (unsigned int)SystemThread_TlsOffset;
          if ( v47 && *(_QWORD *)(v47 + 272) == v47 )
            v46 = *(_QWORD *)(v47 + 256);
          if ( v46 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v64);
              v44 = v64;
            }
            else
            {
              v44.QuadPart = MEMORY[0x7FFE0008];
            }
          }
        }
        if ( (qword_1007149B5 & 0x800000) == 0 )
          Spinlock<32,1,268435714>::SpinToAcquireWithExponentialBackoff(v5);
        else
          Spinlock<32,1,268435714>::SpinToAcquireOptimistic(v5);
        if ( v46 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v65);
            v48 = v65;
          }
          else
          {
            v48.QuadPart = MEMORY[0x7FFE0008];
          }
          v49 = 0;
          if ( v48.QuadPart >= (unsigned __int64)v44.QuadPart )
            v49 = v48.QuadPart - v44.QuadPart;
          *(_QWORD *)(v46 + 3192) += v49;
        }
      }
      v68 = 0;
      if ( GetThreadIOPendingFlag(*((HANDLE *)a2 + 37), &v68) )
      {
        if ( v68 )
          goto LABEL_114;
      }
      else
      {
        v68 = 0;
      }
      if ( *((_QWORD *)this + 6) )
      {
        if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v56 = rand();
          v58 = (unsigned int)(v56 / 5);
          v59 = (unsigned int)(5 * v58);
          if ( v56 == (_DWORD)v59 )
            Spinlock<32,1,268435714>::UpdateStatSnapshot(v59, v58, (unsigned int)v56, v57);
        }
        *(_QWORD *)v5 = 0;
        goto LABEL_27;
      }
LABEL_114:
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v50 = rand();
        v52 = (unsigned int)(v50 / 5);
        v53 = (unsigned int)(5 * v52);
        if ( v50 == (_DWORD)v53 )
          Spinlock<32,1,268435714>::UpdateStatSnapshot(v53, v52, (unsigned int)v50, v51);
      }
      *(_QWORD *)v5 = 0;
    }
  }
  v69 = 0;
  if ( GetThreadIOPendingFlag(*((HANDLE *)a2 + 37), &v69) )
  {
    if ( !v69 )
      goto LABEL_132;
    goto LABEL_38;
  }
  v69 = 0;
LABEL_132:
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v55 = rand();
    if ( v55 == 5 * (v55 / 5) )
      ((void (*)(void))Spinlock<32,1,268435714>::UpdateStatSnapshot)();
  }
  *(_QWORD *)v5 = 0;
  _InterlockedDecrement(v66);
}

```

## disassembly

```asm
0x10042b250  push    rbp
0x10042b252  push    rbx
0x10042b253  push    rsi
0x10042b254  push    rdi
0x10042b255  push    r12
0x10042b257  push    r13
0x10042b259  push    r14
0x10042b25b  push    r15
0x10042b25d  lea     rbp, [rsp-1Fh]
0x10042b262  sub     rsp, 98h
0x10042b269  mov     [rbp+57h+var_48], 0FFFFFFFFFFFFFFFEh
0x10042b271  mov     rdi, rdx
0x10042b274  mov     r13, rcx
0x10042b277  mov     r12, [rdx+100h]
0x10042b27e  lea     r15, [rcx+4]
0x10042b282  mov     [rbp+57h+var_50], r15
0x10042b286  lock inc dword ptr [r15]
0x10042b28a  lock dec dword ptr [rcx]
0x10042b28d  lea     r15, [rcx+40h]
0x10042b291  xor     r14d, r14d
0x10042b294  mov     [rbp+57h+var_B0], r15
0x10042b298  mov     [rbp+57h+var_A8], r14d
0x10042b29c  mov     rbx, r14
0x10042b29f  mov     eax, gs:48h
0x10042b2a7  mov     r14d, eax
0x10042b2aa  mov     rax, [rbp+57h+var_B0]
0x10042b2ae  mov     ecx, [rax]
0x10042b2b0  test    ecx, ecx
0x10042b2b2  jnz     loc_10046D46F
0x10042b2b8  mov     rcx, [rbp+57h+var_B0]
0x10042b2bc  xor     eax, eax
0x10042b2be  lock cmpxchg [rcx], r14
0x10042b2c3  mov     eax, 0
0x10042b2c8  setz    al
0x10042b2cb  test    eax, eax
0x10042b2cd  jz      loc_10046D46F
0x10042b2d3  xor     r14d, r14d
0x10042b2d6  mov     [rbp+57h+var_A8], 1
0x10042b2dd  lea     rax, [r13+10h]
0x10042b2e1  mov     rcx, [rax+8]
0x10042b2e5  mov     rbx, r14
0x10042b2e8  cmp     rcx, rax
0x10042b2eb  jz      loc_10042B5BB
0x10042b2f1  lea     rax, [rcx-8]
0x10042b2f5  test    rcx, rcx
0x10042b2f8  cmovnz  rbx, rax
0x10042b2fc  mov     rsi, rbx
0x10042b2ff  test    rbx, rbx
0x10042b302  jz      loc_10042B5BE
0x10042b308  mov     rcx, [rbx+10h]
0x10042b30c  mov     rax, [rbx+8]
0x10042b310  mov     [rax+8], rcx
0x10042b314  mov     [rcx], rax
0x10042b317  mov     [rbx+10h], r14
0x10042b31b  mov     [rbx+8], r14
0x10042b31f  jmp     short loc_10042B322
0x10042b322  cmp     cs:?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA, 0; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10042b329  jnz     loc_10046D585
0x10042b32f  mov     rax, [rbp+57h+var_B0]
0x10042b333  mov     [rax], r14
0x10042b336  mov     [rbp+57h+var_B0], r14
0x10042b33a  mov     [rbp+57h+var_A8], r14d
0x10042b33e  test    rbx, rbx
0x10042b341  jz      loc_10042B550
0x10042b347  mov     rcx, r13; this
0x10042b34a  call    ?StartNewSysThreadIfRequired@SystemThreadDispatcher@@AEAAXXZ; SystemThreadDispatcher::StartNewSysThreadIfRequired(void)
0x10042b34f  mov     rdx, rbx; struct Worker *
0x10042b352  mov     rcx, rdi; struct SystemThread *
0x10042b355  call    ?BindSystemThreadAndWorker@@YAXQEAVSystemThread@@QEAVWorker@@@Z; BindSystemThreadAndWorker(SystemThread * const,Worker * const)
0x10042b35a  and     dword ptr [rdi+108h], 0FFFFFFFCh
0x10042b361  mov     edx, [rbx+4Ch]; unsigned int
0x10042b364  mov     rcx, rdi; this
0x10042b367  call    ?ChangeCPUId@SystemThread@@QEAAKK@Z; SystemThread::ChangeCPUId(ulong)
0x10042b36c  jmp     short loc_10042B36F
0x10042b36f  mov     rbx, [rsi+260h]
0x10042b376  mov     rdx, rbx; struct SOS_Scheduler *
0x10042b379  mov     rcx, rdi; this
0x10042b37c  call    ?SetScheduler@SystemThread@@QEAAXPEAVSOS_Scheduler@@@Z; SystemThread::SetScheduler(SOS_Scheduler *)
0x10042b381  call    cs:__imp_GetCurrentThread
0x10042b387  mov     rcx, rax; hThread
0x10042b38a  mov     edx, [rbx+1420h]; nPriority
0x10042b390  call    cs:__imp_SetThreadPriority
0x10042b396  xor     edx, edx; struct SystemAffinity *
0x10042b398  mov     rcx, rdi; this
0x10042b39b  call    ?RefreshAffinity@SystemThread@@QEAAXPEBVSystemAffinity@@@Z; SystemThread::RefreshAffinity(SystemAffinity const *)
0x10042b3a0  mov     rax, [rbx]
0x10042b3a3  mov     r8, rsi
0x10042b3a6  mov     rdx, rdi
0x10042b3a9  mov     rcx, rbx
0x10042b3ac  call    qword ptr [rax+38h]
0x10042b3af  xor     edx, edx; struct SOS_Scheduler *
0x10042b3b1  mov     rcx, rdi; this
0x10042b3b4  call    ?SetScheduler@SystemThread@@QEAAXPEAVSOS_Scheduler@@@Z; SystemThread::SetScheduler(SOS_Scheduler *)
0x10042b3b9  mov     rcx, gs:58h
0x10042b3c2  mov     eax, cs:_tls_index
0x10042b3c8  mov     esi, cs:SystemThread_TlsOffset
0x10042b3ce  add     rsi, [rcx+rax*8]
0x10042b3d2  mov     rbx, [rsi+100h]
0x10042b3d9  test    rbx, rbx
0x10042b3dc  jnz     short loc_10042B3EC
0x10042b3de  xor     ecx, ecx; void *
0x10042b3e0  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10042b3e5  mov     rbx, [rsi+100h]
0x10042b3ec  mov     rdx, r12; struct Worker *
0x10042b3ef  mov     rcx, rdi; struct SystemThread *
0x10042b3f2  call    ?BindSystemThreadAndWorker@@YAXQEAVSystemThread@@QEAVWorker@@@Z; BindSystemThreadAndWorker(SystemThread * const,Worker * const)
0x10042b3f7  and     dword ptr [rdi+108h], 0FFFFFFFEh
0x10042b3fe  or      dword ptr [rdi+108h], 2
0x10042b405  mov     eax, [rdi+0D8h]
0x10042b40b  mov     [r12+4Ch], eax
0x10042b410  mov     r8, [rbx+260h]
0x10042b417  mov     edx, [rdi+150h]
0x10042b41d  test    dl, 4
0x10042b420  jz      loc_10046D942
0x10042b426  mov     r14, [r12+3E0h]
0x10042b42e  mov     rsi, [r12+260h]
0x10042b436  mov     r15, [r12+3E8h]
0x10042b43e  mov     rcx, [r8+0E70h]
0x10042b445  mov     rax, [rbx+3E0h]
0x10042b44c  mov     [r12+3E0h], rax
0x10042b454  mov     [r12+260h], r8
0x10042b45c  mov     [r12+3E8h], rcx
0x10042b464  mov     eax, [r8+0DD0h]
0x10042b46b  mov     [r12+4Ch], eax
0x10042b470  mov     eax, 0FFFFFFFFh
0x10042b475  lock xadd [rbx+30h], eax
0x10042b47a  cmp     eax, 1
0x10042b47d  jnz     short loc_10042B49A
0x10042b47f  cmp     qword ptr [rbx+20h], 0
0x10042b484  jz      short loc_10042B492
0x10042b486  mov     rdx, rbx
0x10042b489  mov     rcx, [rbx+28h]
0x10042b48d  call    ?RemoveElem@?$TList@VSchedulerManager@@VWorker@@$0BI@UTListSLock@@@@QEAAXPEAVWorker@@@Z; TList<SchedulerManager,Worker,24,TListSLock>::RemoveElem(Worker *)
0x10042b492  mov     rcx, rbx; this
0x10042b495  call    ?Destroy@Worker@@IEAAXXZ; Worker::Destroy(void)
0x10042b49a  lock inc cs:?SOS_OS_WorkersAvailable@@3JC; long volatile SOS_OS_WorkersAvailable
0x10042b4a1  mov     eax, cs:?sm_WorkerPressureCount@SOS_OS@@0JC; long volatile SOS_OS::sm_WorkerPressureCount
0x10042b4a7  test    eax, eax
0x10042b4a9  jle     short loc_10042B4B2
0x10042b4ab  lock dec cs:?sm_WorkerPressureCount@SOS_OS@@0JC; long volatile SOS_OS::sm_WorkerPressureCount
0x10042b4b2  and     dword ptr [rdi+150h], 0FFFFFFFBh
0x10042b4b9  mov     [r12+3E0h], r14
0x10042b4c1  mov     [r12+260h], rsi
0x10042b4c9  mov     [r12+3E8h], r15
0x10042b4d1  lea     r15, [r13+40h]
0x10042b4d5  xor     r14d, r14d
0x10042b4d8  test    rsi, rsi
0x10042b4db  jz      short loc_10042B4EB
0x10042b4dd  mov     eax, [rsi+0DD0h]
0x10042b4e3  mov     [r12+4Ch], eax
0x10042b4e8  jmp     short loc_10042B4EB
0x10042b4eb  mov     eax, [rdi+108h]
0x10042b4f1  shr     eax, 3
0x10042b4f4  test    al, 1
0x10042b4f6  jz      loc_10042B294
0x10042b4fc  mov     [rbp+57h+IOIsPending], r14d
0x10042b500  lea     rdx, [rbp+57h+IOIsPending]; lpIOIsPending
0x10042b504  mov     rcx, [rdi+128h]; hThread
0x10042b50b  call    cs:__imp_GetThreadIOPendingFlag
0x10042b511  test    eax, eax
0x10042b513  jz      short loc_10042B51F
0x10042b515  cmp     [rbp+57h+IOIsPending], 0
0x10042b519  jnz     loc_10042B294
0x10042b51f  lock dec dword ptr [r13+4]
0x10042b524  mov     rcx, r13; this
0x10042b527  call    ?StartNewSysThreadIfRequired@SystemThreadDispatcher@@AEAAXXZ; SystemThreadDispatcher::StartNewSysThreadIfRequired(void)
0x10042b52c  lock inc dword ptr [r13+4]
0x10042b531  jmp     short loc_10042B534
0x10042b534  lock dec dword ptr [r13+4]
0x10042b539  add     rsp, 98h
0x10042b540  pop     r15
0x10042b542  pop     r14
0x10042b544  pop     r13
0x10042b546  pop     r12
0x10042b548  pop     rdi
0x10042b549  pop     rsi
0x10042b54a  pop     rbx
0x10042b54b  pop     rbp
0x10042b54c  retn
0x10042b550  mov     esi, cs:?sm_IdleTimeOut@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_IdleTimeOut
0x10042b556  nop     word ptr [rax+rax+00000000h]
0x10042b560  mov     edx, esi; dwMilliseconds
0x10042b562  mov     rcx, [rdi+140h]; hHandle
0x10042b569  call    cs:__imp_WaitForSingleObject
0x10042b56f  mov     ebx, eax
0x10042b571  cmp     esi, 0FFFFFFFFh
0x10042b574  jz      loc_10046D5B7
0x10042b57a  mov     edx, r14d; int
0x10042b57d  mov     r8d, ebx; unsigned int
0x10042b580  mov     rcx, rdi; this
0x10042b583  call    ?LogSpuriousEvent@SystemThread@@AEAAXHK@Z; SystemThread::LogSpuriousEvent(int,ulong)
0x10042b588  cmp     qword ptr [rdi+0F8h], 0
0x10042b590  jz      loc_10046D5DB
0x10042b596  test    ebx, ebx
0x10042b598  jnz     loc_10046D5E6
0x10042b59e  mov     [rdi+0F8h], r14
0x10042b5a5  mov     rsi, [rdi+100h]
0x10042b5ac  test    rsi, rsi
0x10042b5af  jnz     loc_10042B36F
0x10042b5b5  jmp     loc_10046D770
0x10042b5bb  mov     rsi, r14
0x10042b5be  mov     rax, [r13+38h]
0x10042b5c2  mov     rcx, [rax+118h]
0x10042b5c9  mov     eax, [rcx+620h]
0x10042b5cf  shr     eax, 3
0x10042b5d2  test    al, 1
0x10042b5d4  jnz     loc_10046D54A
0x10042b5da  mov     eax, [r13+48h]
0x10042b5de  cmp     [r13+30h], rax
0x10042b5e2  jnb     loc_10046D558
0x10042b5e8  lea     rdx, [r13+20h]
0x10042b5ec  lea     rcx, [rdi+0A8h]
0x10042b5f3  mov     rax, [rdx+8]
0x10042b5f7  mov     [rcx+8], rax
0x10042b5fb  mov     rax, [rdx+8]
0x10042b5ff  mov     [rax], rcx
0x10042b602  mov     [rdx+8], rcx
0x10042b606  mov     [rcx], rdx
0x10042b609  inc     qword ptr [rdx+10h]
0x10042b60d  jmp     loc_10042B322
0x10046d46f  mov     eax, cs:?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10046d475  and     eax, 84h
0x10046d47a  xor     esi, esi
0x10046d47c  cmp     al, 84h
0x10046d47e  jnz     short loc_10046D4CA
0x10046d480  mov     rcx, gs:58h
0x10046d489  mov     eax, cs:_tls_index
0x10046d48f  mov     edx, cs:SystemThread_TlsOffset
0x10046d495  add     rdx, [rcx+rax*8]
0x10046d499  jz      short loc_10046D4AB
0x10046d49b  cmp     [rdx+110h], rdx
0x10046d4a2  jnz     short loc_10046D4AB
0x10046d4a4  mov     rsi, [rdx+100h]
0x10046d4ab  test    rsi, rsi
0x10046d4ae  jz      short loc_10046D4CA
0x10046d4b0  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x10046d4b7  jz      short loc_10046D528
0x10046d4b9  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x10046d4bd  call    cs:__imp_QueryPerformanceCounter
0x10046d4c3  mov     rbx, qword ptr [rbp+57h+PerformanceCount]
0x10046d4c7  jmp     short loc_10046D4CA
0x10046d4ca  mov     rcx, [rbp+57h+var_B0]; this
0x10046d4ce  test    byte ptr cs:qword_1007149B5+2, 80h
0x10046d4d5  jz      short loc_10046D533
0x10046d4d7  mov     r8, r14
0x10046d4da  mov     rdx, rsi
0x10046d4dd  call    ?SpinToAcquireOptimistic@?$Spinlock@$0CA@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<32,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10046d4e2  jmp     short loc_10046D4E5
0x10046d4e5  test    rsi, rsi
0x10046d4e8  jz      loc_10042B2D3
0x10046d4ee  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x10046d4f5  jz      short loc_10046D53F
0x10046d4f7  lea     rcx, [rbp+57h+var_78]; lpPerformanceCount
0x10046d4fb  call    cs:__imp_QueryPerformanceCounter
0x10046d501  mov     rcx, qword ptr [rbp+57h+var_78]
0x10046d505  jmp     short loc_10046D508
0x10046d508  mov     rdx, rcx
0x10046d50b  sub     rdx, rbx
0x10046d50e  xor     r14d, r14d
0x10046d511  mov     eax, r14d
0x10046d514  cmp     rcx, rbx
0x10046d517  cmovnb  rax, rdx
0x10046d51b  add     [rsi+0C78h], rax
0x10046d522  jmp     loc_10042B2D6
0x10046d528  mov     rbx, ds:7FFE0008h
0x10046d530  jmp     short loc_10046D4CA
0x10046d533  mov     rdx, r14
0x10046d536  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0CA@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<32,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10046d53b  nop
0x10046d53c  jmp     short loc_10046D4E5
0x10046d53f  mov     rcx, ds:7FFE0008h
0x10046d547  jmp     short loc_10046D508
0x10046d54a  lea     rax, [r13+20h]
0x10046d54e  cmp     [rax+8], rax
0x10046d552  jz      loc_10042B5DA
0x10046d558  mov     [rbp+57h+arg_8], r14d
0x10046d55c  lea     rdx, [rbp+57h+arg_8]; lpIOIsPending
0x10046d560  mov     rcx, [rdi+128h]; hThread
0x10046d567  call    cs:__imp_GetThreadIOPendingFlag
0x10046d56d  test    eax, eax
0x10046d56f  jz      loc_10046D9AE
0x10046d575  cmp     [rbp+57h+arg_8], 0
0x10046d579  jnz     loc_10042B5E8
0x10046d57f  jmp     loc_10046D9B2
0x10046d585  call    cs:__imp_rand
0x10046d58b  mov     r8d, eax
0x10046d58e  mov     eax, 66666667h
0x10046d593  imul    r8d
0x10046d596  sar     edx, 1
0x10046d598  mov     ecx, edx
0x10046d59a  shr     ecx, 1Fh
0x10046d59d  add     edx, ecx
0x10046d59f  lea     ecx, [rdx+rdx*4]
0x10046d5a2  cmp     r8d, ecx
0x10046d5a5  jnz     loc_10042B32F
0x10046d5ab  call    ?UpdateStatSnapshot@?$Spinlock@$0CA@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<32,1,268435714>::UpdateStatSnapshot(void)
0x10046d5b0  nop
0x10046d5b1  jmp     loc_10042B32F
0x10046d5b7  cmp     qword ptr [rdi+0F8h], 0
0x10046d5bf  jnz     loc_10042B57A
  ... truncated ...
```
