# SOS_OS::SuspendSystemThreads(void)

- ea: `0x1004b7110`
- end: `0x1004b7e0d`
- name: `?SuspendSystemThreads@SOS_OS@@CAXXZ`
- size: `3325`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1004b6f60`

## callees

- `0x100401010`
- `0x100403070`
- `0x100410010`
- `0x1004101f0`
- `0x100410950`
- `0x100411fb0`
- `0x100414400`
- `0x10041db40`
- `0x100435af0`
- `0x1004360f0`
- `0x10046baf0`
- `0x10046bd30`
- `0x100475070`
- `0x100475210`
- `0x1004753f0`
- `0x1004b7110`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1004b7165`
- `KERNEL32!GetCurrentThreadId` at `0x1004b7165`
- `KERNEL32!SetEvent` at `0x1004b798d`
- `KERNEL32!SetEvent` at `0x1004b7b12`
- `KERNEL32!SetEvent` at `0x1004b7b58`
- `KERNEL32!SetEvent` at `0x1004b7bec`
- `KERNEL32!SetEvent` at `0x1004b7c83`
- `KERNEL32!SetEvent` at `0x1004b798d`
- `KERNEL32!SetEvent` at `0x1004b7b12`
- `KERNEL32!SetEvent` at `0x1004b7b58`
- `KERNEL32!SetEvent` at `0x1004b7bec`
- `KERNEL32!SetEvent` at `0x1004b7c83`
- `KERNEL32!SuspendThread` at `0x1004b7d34`
- `KERNEL32!SuspendThread` at `0x1004b7d34`
- `KERNEL32!QueryPerformanceCounter` at `0x1004b7254`
- `KERNEL32!QueryPerformanceCounter` at `0x1004b72a5`
- `KERNEL32!QueryPerformanceCounter` at `0x1004b7587`
- `KERNEL32!QueryPerformanceCounter` at `0x1004b75d8`
- `KERNEL32!QueryPerformanceCounter` at `0x1004b77fa`
- `KERNEL32!QueryPerformanceCounter` at `0x1004b7849`
- `KERNEL32!QueryPerformanceCounter` at `0x1004b7254`
- `KERNEL32!QueryPerformanceCounter` at `0x1004b72a5`
- `KERNEL32!QueryPerformanceCounter` at `0x1004b7587`
- `KERNEL32!QueryPerformanceCounter` at `0x1004b75d8`
- `KERNEL32!QueryPerformanceCounter` at `0x1004b77fa`
- `KERNEL32!QueryPerformanceCounter` at `0x1004b7849`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004b7342`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004b7682`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004b78ff`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004b7342`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004b7682`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004b78ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void SOS_OS::SuspendSystemThreads(void)
{
  unsigned __int64 v0; // r15
  unsigned __int64 v1; // r12
  __int64 Head; // rdi
  volatile signed __int32 *v3; // r14
  _UNKNOWN **v4; // rbx
  LARGE_INTEGER v5; // rbx
  signed __int64 UniqueThread_low; // rsi
  __int64 v7; // rdi
  __int64 v8; // rdx
  LARGE_INTEGER v9; // rcx
  LONGLONG v10; // rax
  _UNKNOWN **v11; // rcx
  signed __int32 v12; // ecx
  _UNKNOWN **v13; // rcx
  int v14; // r8d
  unsigned __int64 StackAvailableBytes; // rax
  unsigned __int64 v16; // r8
  __int64 v17; // rax
  void *v18; // rsp
  __int64 v19; // rdi
  volatile signed __int32 *v20; // r12
  int v21; // r13d
  _UNKNOWN **v22; // rbx
  LARGE_INTEGER v23; // rbx
  signed __int64 v24; // rsi
  __int64 v25; // rdi
  __int64 v26; // rdx
  LARGE_INTEGER v27; // rcx
  LONGLONG v28; // rax
  _UNKNOWN **v29; // rcx
  signed __int32 v30; // ecx
  _UNKNOWN **v31; // rcx
  int v32; // r8d
  unsigned __int64 v33; // r12
  _UNKNOWN **v34; // rbx
  SystemThread *v35; // r14
  SystemThread *v36; // rbx
  _UNKNOWN **v37; // r12
  LARGE_INTEGER v38; // rbx
  signed __int64 v39; // rsi
  __int64 v40; // rdi
  __int64 v41; // rdx
  SpinlockBase *v42; // rcx
  LARGE_INTEGER v43; // rcx
  LONGLONG v44; // rax
  _UNKNOWN **v45; // rcx
  signed __int32 v46; // ecx
  _UNKNOWN **v47; // rcx
  int v48; // r8d
  __int64 v49; // rdi
  __int64 v50; // rsi
  unsigned __int64 v51; // rax
  unsigned __int64 v52; // rcx
  int v53; // edi
  __int64 v54; // rax
  SystemThread *v55; // rdi
  SystemThread *v56; // r8
  SystemThread *v57; // rbx
  void *v58; // rcx
  SystemThread *v59; // r8
  SystemThread *v60; // rbx
  void *v61; // rcx
  __int64 v62; // rcx
  char *v63; // rsi
  __int64 v64; // rbx
  __int64 v65; // rdi
  unsigned __int64 v66; // rax
  unsigned __int64 v67; // rdx
  int v68; // ebx
  char v69; // [rsp+20h] [rbp+0h] BYREF
  unsigned __int64 v70; // [rsp+28h] [rbp+8h]
  SystemThread *v71[2]; // [rsp+30h] [rbp+10h]
  _UNKNOWN **v72; // [rsp+40h] [rbp+20h]
  __int64 v73; // [rsp+48h] [rbp+28h]
  int v74; // [rsp+50h] [rbp+30h]
  DWORD CurrentThreadId; // [rsp+58h] [rbp+38h]
  unsigned __int64 v76; // [rsp+60h] [rbp+40h]
  volatile signed __int32 *v77; // [rsp+68h] [rbp+48h]
  __int64 v78; // [rsp+70h] [rbp+50h]
  __int64 Tail; // [rsp+78h] [rbp+58h]
  _UNKNOWN **v80; // [rsp+80h] [rbp+60h]
  __int64 v81; // [rsp+88h] [rbp+68h]
  int v82; // [rsp+90h] [rbp+70h]
  __int128 v83; // [rsp+98h] [rbp+78h]
  _UNKNOWN **v84; // [rsp+A8h] [rbp+88h]
  __int64 v85; // [rsp+B0h] [rbp+90h]
  int v86; // [rsp+B8h] [rbp+98h]
  char *v87; // [rsp+C0h] [rbp+A0h]
  LARGE_INTEGER PerformanceCount; // [rsp+C8h] [rbp+A8h] BYREF
  LARGE_INTEGER v89; // [rsp+D0h] [rbp+B0h] BYREF
  LARGE_INTEGER v90; // [rsp+D8h] [rbp+B8h] BYREF
  LARGE_INTEGER v91; // [rsp+E0h] [rbp+C0h] BYREF
  LARGE_INTEGER v92; // [rsp+E8h] [rbp+C8h] BYREF
  LARGE_INTEGER v93; // [rsp+F0h] [rbp+D0h] BYREF
  __int64 v94; // [rsp+F8h] [rbp+D8h]

  v94 = -2;
  v0 = 0;
  v70 = 0;
  v1 = 0;
  v76 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v81 = 0;
  v82 = 0;
  v80 = &SOS_PublicGlobals::sm_NodeManager;
  Head = TList<NodeManager,SOS_Node,16,TListSLock>::GetHead(&SOS_PublicGlobals::sm_NodeManager);
  v78 = Head;
  Tail = TList<GroupList,SOS_ResourceGroup,16,TListSLock>::GetTail(&SOS_PublicGlobals::sm_NodeManager);
  v3 = 0;
  while ( 1 )
  {
    v4 = 0;
    if ( !v3 )
    {
      v4 = (_UNKNOWN **)Head;
      goto LABEL_48;
    }
    if ( Head )
      break;
LABEL_48:
    v3 = (volatile signed __int32 *)v4;
    if ( !v4 )
      goto LABEL_51;
    v1 += *((int *)v4 + 207) + (__int64)*((int *)v4 + 131);
    v76 = v1;
    Head = v78;
  }
  if ( Head != Tail )
  {
    v5.QuadPart = 0;
    UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( qword_100714160
      || _InterlockedCompareExchange64((volatile signed __int64 *)&qword_100714160, UniqueThread_low, 0) )
    {
      v7 = 0;
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
           + (unsigned int)SystemThread_TlsOffset;
        if ( v8 && *(_QWORD *)(v8 + 272) == v8 )
          v7 = *(_QWORD *)(v8 + 256);
        if ( v7 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&PerformanceCount);
            v5 = PerformanceCount;
          }
          else
          {
            v5.QuadPart = MEMORY[0x7FFE0008];
          }
        }
      }
      if ( (qword_1007149B5 & 0x800000) == 0 )
        Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff((SpinlockBase *)&qword_100714160);
      else
        Spinlock<19,1,268435714>::SpinToAcquireOptimistic((SpinlockBase *)&qword_100714160);
      if ( v7 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v89);
          v9 = v89;
        }
        else
        {
          v9.QuadPart = MEMORY[0x7FFE0008];
        }
        v10 = 0;
        if ( v9.QuadPart >= (unsigned __int64)v5.QuadPart )
          v10 = v9.QuadPart - v5.QuadPart;
        *(_QWORD *)(v7 + 3192) += v10;
      }
    }
    v11 = (_UNKNOWN **)*((_QWORD *)v3 + 3);
    v4 = 0;
    if ( v11 != &SOS_PublicGlobals::sm_NodeManager )
    {
      if ( v11 )
        v4 = v11 - 2;
      if ( v4 )
      {
        while ( 1 )
        {
          v12 = *((_DWORD *)v4 + 10);
          if ( v12 )
          {
            while ( v12 != _InterlockedCompareExchange((volatile signed __int32 *)v4 + 10, v12 + 1, v12) )
            {
              _mm_pause();
              v12 = *((_DWORD *)v4 + 10);
              if ( !v12 )
                goto LABEL_35;
            }
            if ( v12 != -1 )
              break;
          }
LABEL_35:
          v13 = (_UNKNOWN **)v4[3];
          v4 = 0;
          if ( v13 != &SOS_PublicGlobals::sm_NodeManager )
          {
            if ( v13 )
              v4 = v13 - 2;
            if ( v4 )
              continue;
          }
          break;
        }
      }
    }
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v14 = rand();
      if ( v14 == 5 * (v14 / 5) )
        Spinlock<19,1,268435714>::UpdateStatSnapshot();
    }
    qword_100714160 = 0;
    v78 = (__int64)v4;
    if ( _InterlockedExchangeAdd(v3 + 10, 0xFFFFFFFF) == 1 && *((_QWORD *)v3 + 3) )
      TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*((_QWORD *)v3 + 4), v3);
    goto LABEL_47;
  }
  v78 = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(Head + 40), 0xFFFFFFFF) != 1 || !*(_QWORD *)(Head + 24) )
  {
LABEL_47:
    Head = v78;
    goto LABEL_48;
  }
  TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*(_QWORD *)(Head + 32), Head);
  Head = v78;
LABEL_51:
  if ( Head )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(Head + 40), 0xFFFFFFFF) == 1 && *(_QWORD *)(Head + 24) )
      TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*(_QWORD *)(Head + 32), Head);
    v78 = 0;
  }
  if ( Tail )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(Tail + 40), 0xFFFFFFFF) == 1 && *(_QWORD *)(Tail + 24) )
      TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*(_QWORD *)(Tail + 32), Tail);
    Tail = 0;
  }
  v80 = 0;
  StackAvailableBytes = SOS_Task::GetStackAvailableBytes();
  if ( StackAvailableBytes < (unsigned __int64)(unsigned int)(v16 + 128) + 0x10000 )
    return;
  v17 = v16 + 15;
  if ( v16 + 15 < v16 )
    v17 = 0xFFFFFFFFFFFFFF0LL;
  v18 = alloca(v17 & 0xFFFFFFFFFFFFFFF0uLL);
  v87 = &v69;
  v83 = 0;
  v85 = 0;
  v86 = 0;
  v84 = &SOS_PublicGlobals::sm_NodeManager;
  v19 = TList<NodeManager,SOS_Node,16,TListSLock>::GetHead(&SOS_PublicGlobals::sm_NodeManager);
  *(_QWORD *)&v83 = v19;
  *((_QWORD *)&v83 + 1) = TList<GroupList,SOS_ResourceGroup,16,TListSLock>::GetTail(&SOS_PublicGlobals::sm_NodeManager);
  v20 = 0;
  v21 = 0;
LABEL_65:
  v22 = 0;
  if ( !v20 )
  {
    v22 = (_UNKNOWN **)v19;
    goto LABEL_111;
  }
  if ( !v19 )
    goto LABEL_111;
  if ( v19 != *((_QWORD *)&v83 + 1) )
  {
    v23.QuadPart = 0;
    v24 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( qword_100714160 || _InterlockedCompareExchange64((volatile signed __int64 *)&qword_100714160, v24, 0) )
    {
      v25 = 0;
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v26 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
            + (unsigned int)SystemThread_TlsOffset;
        if ( v26 && *(_QWORD *)(v26 + 272) == v26 )
          v25 = *(_QWORD *)(v26 + 256);
        if ( v25 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v90);
            v23 = v90;
          }
          else
          {
            v23.QuadPart = MEMORY[0x7FFE0008];
          }
        }
      }
      if ( (qword_1007149B5 & 0x800000) == 0 )
        Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff((SpinlockBase *)&qword_100714160);
      else
        Spinlock<19,1,268435714>::SpinToAcquireOptimistic((SpinlockBase *)&qword_100714160);
      if ( v25 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v91);
          v27 = v91;
        }
        else
        {
          v27.QuadPart = MEMORY[0x7FFE0008];
        }
        v28 = 0;
        if ( v27.QuadPart >= (unsigned __int64)v23.QuadPart )
          v28 = v27.QuadPart - v23.QuadPart;
        *(_QWORD *)(v25 + 3192) += v28;
      }
    }
    v29 = (_UNKNOWN **)*((_QWORD *)v20 + 3);
    v22 = 0;
    if ( v29 != &SOS_PublicGlobals::sm_NodeManager )
    {
      if ( v29 )
        v22 = v29 - 2;
      if ( v22 )
      {
        while ( 1 )
        {
          v30 = *((_DWORD *)v22 + 10);
          if ( v30 )
          {
            while ( v30 != _InterlockedCompareExchange((volatile signed __int32 *)v22 + 10, v30 + 1, v30) )
            {
              _mm_pause();
              v30 = *((_DWORD *)v22 + 10);
              if ( !v30 )
                goto LABEL_98;
            }
            if ( v30 != -1 )
              break;
          }
LABEL_98:
          v31 = (_UNKNOWN **)v22[3];
          v22 = 0;
          if ( v31 != &SOS_PublicGlobals::sm_NodeManager )
          {
            if ( v31 )
              v22 = v31 - 2;
            if ( v22 )
              continue;
          }
          break;
        }
      }
    }
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v32 = rand();
      if ( v32 == 5 * (v32 / 5) )
        Spinlock<19,1,268435714>::UpdateStatSnapshot();
    }
    qword_100714160 = 0;
    *(_QWORD *)&v83 = v22;
    if ( _InterlockedExchangeAdd(v20 + 10, 0xFFFFFFFF) == 1 && *((_QWORD *)v20 + 3) )
      TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*((_QWORD *)v20 + 4), v20);
LABEL_110:
    v19 = v83;
LABEL_111:
    v77 = (volatile signed __int32 *)v22;
    v33 = v70;
    if ( !v22 || v70 >= v76 )
      goto LABEL_193;
    *(_OWORD *)v71 = 0;
    v73 = 0;
    v74 = 0;
    v34 = v22 + 8;
    v72 = v34;
    v71[0] = (SystemThread *)TList<SOS_Node,SystemThread,184,TListSLock>::GetHead(v34);
    v71[1] = (SystemThread *)TList<SOS_Node,SystemThread,184,TListSLock>::GetTail(v34);
    v35 = 0;
    while ( 1 )
    {
      v36 = 0;
      if ( v35 )
      {
        if ( v71[0] )
        {
          if ( v71[0] == v71[1] )
          {
            v55 = v71[0];
            v71[0] = 0;
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v55 + 52, 0xFFFFFFFF) == 1 )
            {
              if ( *((_QWORD *)v55 + 24) )
              {
                TList<SOS_Node,SystemThread,184,TListSLock>::RemoveElem(*((_QWORD *)v55 + 25) + 64LL, v55);
                *((_QWORD *)v55 + 31) = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                      + (unsigned int)SystemThread_TlsOffset;
                SetEvent(*((HANDLE *)v55 + 40));
LABEL_177:
                v56 = v71[0];
                if ( v71[0] )
                {
                  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v71[0] + 52, 0xFFFFFFFF) == 1 )
                  {
                    if ( *((_QWORD *)v56 + 24) )
                    {
                      v57 = v56;
                      TList<SOS_Node,SystemThread,184,TListSLock>::RemoveElem(*((_QWORD *)v56 + 25) + 64LL, v56);
                      *((_QWORD *)v57 + 31) = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                              + (unsigned int)tls_index)
                                            + (unsigned int)SystemThread_TlsOffset;
                      v58 = (void *)*((_QWORD *)v57 + 40);
                    }
                    else
                    {
                      *((_QWORD *)v56 + 31) = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                              + (unsigned int)tls_index)
                                            + (unsigned int)SystemThread_TlsOffset;
                      v58 = (void *)*((_QWORD *)v56 + 40);
                    }
                    SetEvent(v58);
                  }
                  v71[0] = 0;
                }
                v59 = v71[1];
                if ( v71[1] )
                {
                  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v71[1] + 52, 0xFFFFFFFF) == 1 )
                  {
                    if ( *((_QWORD *)v59 + 24) )
                    {
                      v60 = v59;
                      TList<SOS_Node,SystemThread,184,TListSLock>::RemoveElem(*((_QWORD *)v59 + 25) + 64LL, v59);
                      *((_QWORD *)v60 + 31) = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                              + (unsigned int)tls_index)
                                            + (unsigned int)SystemThread_TlsOffset;
                      v61 = (void *)*((_QWORD *)v60 + 40);
                    }
                    else
                    {
                      *((_QWORD *)v59 + 31) = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                              + (unsigned int)tls_index)
                                            + (unsigned int)SystemThread_TlsOffset;
                      v61 = (void *)*((_QWORD *)v59 + 40);
                    }
                    SetEvent(v61);
                  }
                  v71[1] = 0;
                }
                v72 = 0;
                v19 = v83;
                v20 = v77;
                goto LABEL_65;
              }
              *((_QWORD *)v55 + 31) = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                    + (unsigned int)SystemThread_TlsOffset;
              SetEvent(*((HANDLE *)v55 + 40));
            }
          }
          else
          {
            v37 = v72;
            v38.QuadPart = 0;
            v39 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
            if ( *((_DWORD *)v72 + 4) || _InterlockedCompareExchange64((volatile signed __int64 *)v72 + 2, v39, 0) )
            {
              v40 = 0;
              if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
              {
                v41 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                    + (unsigned int)SystemThread_TlsOffset;
                if ( v41 && *(_QWORD *)(v41 + 272) == v41 )
                  v40 = *(_QWORD *)(v41 + 256);
                if ( v40 )
                {
                  if ( Base_PublicGlobals::sm_invariantTscAvailable )
                  {
                    QueryPerformanceCounter(&v92);
                    v38 = v92;
                  }
                  else
                  {
                    v38.QuadPart = MEMORY[0x7FFE0008];
                  }
                }
              }
              v42 = (SpinlockBase *)(v37 + 2);
              if ( (qword_1007149B5 & 0x800000) == 0 )
                Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(v42);
              else
                Spinlock<19,1,268435714>::SpinToAcquireOptimistic(v42);
              if ( v40 )
              {
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&v93);
                  v43 = v93;
                }
                else
                {
                  v43.QuadPart = MEMORY[0x7FFE0008];
                }
                v44 = 0;
                if ( v43.QuadPart >= (unsigned __int64)v38.QuadPart )
                  v44 = v43.QuadPart - v38.QuadPart;
                *(_QWORD *)(v40 + 3192) += v44;
              }
            }
            v45 = (_UNKNOWN **)*((_QWORD *)v35 + 24);
            v36 = 0;
            if ( v45 != v72 )
            {
              if ( v45 )
                v36 = (SystemThread *)(v45 - 23);
              if ( v36 )
              {
                while ( 1 )
                {
                  v46 = *((_DWORD *)v36 + 52);
                  if ( v46 )
                  {
                    while ( v46 != _InterlockedCompareExchange((volatile signed __int32 *)v36 + 52, v46 + 1, v46) )
                    {
                      _mm_pause();
                      v46 = *((_DWORD *)v36 + 52);
                      if ( !v46 )
                        goto LABEL_147;
                    }
                    if ( v46 != -1 )
                      break;
                  }
LABEL_147:
                  v47 = (_UNKNOWN **)*((_QWORD *)v36 + 24);
                  v36 = 0;
                  if ( v47 != v72 )
                  {
                    if ( v47 )
                      v36 = (SystemThread *)(v47 - 23);
                    if ( v36 )
                      continue;
                  }
                  break;
                }
              }
            }
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v48 = rand();
              if ( v48 == 5 * (v48 / 5) )
                Spinlock<19,1,268435714>::UpdateStatSnapshot();
            }
            v37[2] = 0;
            v71[0] = v36;
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v35 + 52, 0xFFFFFFFF) == 1 )
            {
              if ( *((_QWORD *)v35 + 24) )
                TList<SOS_Node,SystemThread,184,TListSLock>::RemoveElem(*((_QWORD *)v35 + 25) + 64LL, v35);
              *((_QWORD *)v35 + 31) = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                    + (unsigned int)SystemThread_TlsOffset;
              SetEvent(*((HANDLE *)v35 + 40));
            }
            v33 = v70;
          }
        }
      }
      else
      {
        v36 = v71[0];
      }
      v35 = v36;
      if ( !v36 || v33 >= v76 )
        goto LABEL_177;
      if ( (++v21 & 0x7F) == 0 )
      {
        v49 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
            + (unsigned int)SystemThread_TlsOffset;
        v50 = *(_QWORD *)(v49 + 256);
        if ( !v50 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v50 = *(_QWORD *)(v49 + 256);
        }
        v51 = __rdtsc();
        v52 = *(_QWORD *)(v50 + 832);
        if ( v51 > v52 || v52 != 0x7FFFFFFFFFFFFFFFLL && v52 - v51 > *(_QWORD *)(*(_QWORD *)(v50 + 608) + 3568LL) )
        {
          v53 = *(_DWORD *)(v50 + 616);
          *(_DWORD *)(v50 + 616) = v53 | 1;
          SOS_Task::Sleep(0, yieldWait);
          *(_DWORD *)(v50 + 616) &= v53 | 0xFFFFFFFE;
        }
      }
      if ( *((_DWORD *)v36 + 70) != CurrentThreadId )
      {
        v54 = *((_QWORD *)v36 + 37);
        if ( v54 || (SystemThread::CreateThreadHandle(v36), (v54 = *((_QWORD *)v36 + 37)) != 0) )
        {
          _InterlockedIncrement((volatile signed __int32 *)v36 + 52);
          *(_QWORD *)&v87[8 * v33++] = v54;
          v70 = v33;
        }
      }
    }
  }
  *(_QWORD *)&v83 = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v19 + 40), 0xFFFFFFFF) != 1 || !*(_QWORD *)(v19 + 24) )
    goto LABEL_110;
  TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*(_QWORD *)(v19 + 32), v19);
  v19 = v83;
  v33 = v70;
LABEL_193:
  if ( v19 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v19 + 40), 0xFFFFFFFF) == 1 && *(_QWORD *)(v19 + 24) )
      TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*(_QWORD *)(v19 + 32), v19);
    *(_QWORD *)&v83 = 0;
  }
  v62 = *((_QWORD *)&v83 + 1);
  if ( *((_QWORD *)&v83 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v83 + 1) + 40LL), 0xFFFFFFFF) == 1
      && *(_QWORD *)(v62 + 24) )
    {
      TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*(_QWORD *)(v62 + 32), v62);
    }
    *((_QWORD *)&v83 + 1) = 0;
  }
  v84 = 0;
  if ( v33 )
  {
    v63 = v87;
    do
    {
      SuspendThread(*(HANDLE *)&v63[8 * v0]);
      if ( (v0 & 0x7F) == 0 )
      {
        v64 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
            + (unsigned int)SystemThread_TlsOffset;
        v65 = *(_QWORD *)(v64 + 256);
        if ( !v65 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v65 = *(_QWORD *)(v64 + 256);
        }
        v66 = __rdtsc();
        v67 = *(_QWORD *)(v65 + 832);
        if ( v66 > v67 || v67 != 0x7FFFFFFFFFFFFFFFLL && v67 - v66 > *(_QWORD *)(*(_QWORD *)(v65 + 608) + 3568LL) )
        {
          v68 = *(_DWORD *)(v65 + 616);
          *(_DWORD *)(v65 + 616) = v68 | 1;
          SOS_Task::Sleep(0, yieldWait);
          *(_DWORD *)(v65 + 616) &= v68 | 0xFFFFFFFE;
        }
      }
      ++v0;
    }
    while ( v0 < v33 );
  }
}

```

## disassembly

```asm
0x1004b7110  push    rbp
0x1004b7112  push    r12
0x1004b7114  push    r13
0x1004b7116  push    r14
0x1004b7118  push    r15
0x1004b711a  sub     rsp, 110h
0x1004b7121  lea     rbp, [rsp+20h]
0x1004b7126  mov     [rbp+110h+var_38], 0FFFFFFFFFFFFFFFEh
0x1004b7131  mov     [rbp+110h+arg_0], rbx
0x1004b7138  mov     [rbp+110h+arg_8], rsi
0x1004b713f  mov     [rbp+110h+arg_10], rdi
0x1004b7146  mov     rax, cs:__security_cookie
0x1004b714d  xor     rax, rbp
0x1004b7150  mov     [rbp+110h+var_30], rax
0x1004b7157  xor     r15d, r15d
0x1004b715a  mov     [rbp+110h+var_108], r15
0x1004b715e  mov     r12d, r15d
0x1004b7161  mov     [rbp+110h+var_D0], r15
0x1004b7165  call    cs:__imp_GetCurrentThreadId
0x1004b716b  mov     [rbp+110h+var_D8], eax
0x1004b716e  xorps   xmm0, xmm0
0x1004b7171  movdqu  [rbp+110h+var_C0], xmm0
0x1004b7176  mov     [rbp+110h+var_A8], r15
0x1004b717a  mov     [rbp+110h+var_A0], r15d
0x1004b717e  mov     [rbp+110h+var_B0], r15
0x1004b7182  lea     r13, ?sm_NodeManager@SOS_PublicGlobals@@2VNodeManager@@A; NodeManager SOS_PublicGlobals::sm_NodeManager
0x1004b7189  mov     [rbp+110h+var_B0], r13
0x1004b718d  mov     rcx, r13
0x1004b7190  call    ?GetHead@?$TList@VNodeManager@@VSOS_Node@@$0BA@UTListSLock@@@@QEAAPEAVSOS_Node@@XZ; TList<NodeManager,SOS_Node,16,TListSLock>::GetHead(void)
0x1004b7195  mov     rdi, rax
0x1004b7198  mov     qword ptr [rbp+110h+var_C0], rax
0x1004b719c  mov     rcx, r13
0x1004b719f  call    ?GetTail@?$TList@VGroupList@@VSOS_ResourceGroup@@$0BA@UTListSLock@@@@QEAAPEAVSOS_ResourceGroup@@XZ; TList<GroupList,SOS_ResourceGroup,16,TListSLock>::GetTail(void)
0x1004b71a4  mov     qword ptr [rbp+110h+var_C0+8], rax
0x1004b71a8  mov     r14d, r15d
0x1004b71ab  lea     esi, [r15-1]
0x1004b71af  nop
0x1004b71b0  mov     rbx, r15
0x1004b71b3  test    r14, r14
0x1004b71b6  jnz     short loc_1004B71C0
0x1004b71b8  mov     rbx, rdi
0x1004b71bb  jmp     loc_1004B73B5
0x1004b71c0  test    rdi, rdi
0x1004b71c3  jz      loc_1004B73B5
0x1004b71c9  cmp     rdi, qword ptr [rbp+110h+var_C0+8]
0x1004b71cd  jz      loc_1004B739B
0x1004b71d3  mov     rbx, r15
0x1004b71d6  mov     eax, gs:48h
0x1004b71de  mov     esi, eax
0x1004b71e0  mov     eax, dword ptr cs:qword_100714160
0x1004b71e6  test    eax, eax
0x1004b71e8  jnz     short loc_1004B7203
0x1004b71ea  xor     eax, eax
0x1004b71ec  lock cmpxchg cs:qword_100714160, rsi
0x1004b71f5  mov     eax, r15d
0x1004b71f8  setz    al
0x1004b71fb  test    eax, eax
0x1004b71fd  jnz     loc_1004B72D3
0x1004b7203  mov     eax, cs:?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004b7209  and     eax, 84h
0x1004b720e  mov     rdi, r15
0x1004b7211  cmp     al, 84h
0x1004b7213  jnz     short loc_1004B726B
0x1004b7215  mov     rcx, gs:58h
0x1004b721e  mov     eax, cs:_tls_index
0x1004b7224  mov     edx, cs:SystemThread_TlsOffset
0x1004b722a  add     rdx, [rcx+rax*8]
0x1004b722e  jz      short loc_1004B7240
0x1004b7230  cmp     [rdx+110h], rdx
0x1004b7237  jnz     short loc_1004B7240
0x1004b7239  mov     rdi, [rdx+100h]
0x1004b7240  test    rdi, rdi
0x1004b7243  jz      short loc_1004B726B
0x1004b7245  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, ebx; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004b724b  jz      short loc_1004B7263
0x1004b724d  lea     rcx, [rbp+110h+PerformanceCount]; lpPerformanceCount
0x1004b7254  call    cs:__imp_QueryPerformanceCounter
0x1004b725a  mov     rbx, qword ptr [rbp+110h+PerformanceCount]
0x1004b7261  jmp     short loc_1004B726B
0x1004b7263  mov     rbx, ds:7FFE0008h
0x1004b726b  lea     rcx, qword_100714160; this
0x1004b7272  test    byte ptr cs:qword_1007149B5+2, 80h
0x1004b7279  jz      short loc_1004B7288
0x1004b727b  mov     r8, rsi
0x1004b727e  mov     rdx, rdi
0x1004b7281  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<19,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x1004b7286  jmp     short loc_1004B7290
0x1004b7288  mov     rdx, rsi
0x1004b728b  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x1004b7290  test    rdi, rdi
0x1004b7293  jz      short loc_1004B72D3
0x1004b7295  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004b729c  jz      short loc_1004B72B4
0x1004b729e  lea     rcx, [rbp+110h+var_60]; lpPerformanceCount
0x1004b72a5  call    cs:__imp_QueryPerformanceCounter
0x1004b72ab  mov     rcx, qword ptr [rbp+110h+var_60]
0x1004b72b2  jmp     short loc_1004B72BC
0x1004b72b4  mov     rcx, ds:7FFE0008h
0x1004b72bc  mov     rdx, rcx
0x1004b72bf  sub     rdx, rbx
0x1004b72c2  mov     rax, r15
0x1004b72c5  cmp     rcx, rbx
0x1004b72c8  cmovnb  rax, rdx
0x1004b72cc  add     [rdi+0C78h], rax
0x1004b72d3  mov     rcx, [r14+18h]
0x1004b72d7  mov     rbx, r15
0x1004b72da  cmp     rcx, r13
0x1004b72dd  jz      short loc_1004B7339
0x1004b72df  lea     rax, [rcx-10h]
0x1004b72e3  test    rcx, rcx
0x1004b72e6  cmovnz  rbx, rax
0x1004b72ea  test    rbx, rbx
0x1004b72ed  jz      short loc_1004B7339
0x1004b72ef  nop
0x1004b72f0  mov     ecx, [rbx+28h]
0x1004b72f3  test    ecx, ecx
0x1004b72f5  jz      short loc_1004B731D
0x1004b72f7  nop     word ptr [rax+rax]
0x1004b72fc  nop     dword ptr [rax+00h]
0x1004b7300  lea     edx, [rcx+1]
0x1004b7303  mov     eax, ecx
0x1004b7305  lock cmpxchg [rbx+28h], edx
0x1004b730a  cmp     ecx, eax
0x1004b730c  jz      short loc_1004B7319
0x1004b730e  pause
0x1004b7310  mov     ecx, [rbx+28h]
0x1004b7313  test    ecx, ecx
0x1004b7315  jnz     short loc_1004B7300
0x1004b7317  jmp     short loc_1004B731D
0x1004b7319  test    edx, edx
0x1004b731b  jnz     short loc_1004B7339
0x1004b731d  mov     rcx, [rbx+18h]
0x1004b7321  mov     rbx, r15
0x1004b7324  cmp     rcx, r13
0x1004b7327  jz      short loc_1004B7339
0x1004b7329  lea     rax, [rcx-10h]
0x1004b732d  test    rcx, rcx
0x1004b7330  cmovnz  rbx, rax
0x1004b7334  test    rbx, rbx
0x1004b7337  jnz     short loc_1004B72F0
0x1004b7339  cmp     cs:?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA, 0; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x1004b7340  jz      short loc_1004B7369
0x1004b7342  call    cs:__imp_rand
0x1004b7348  mov     r8d, eax
0x1004b734b  mov     eax, 66666667h
0x1004b7350  imul    r8d
0x1004b7353  sar     edx, 1
0x1004b7355  mov     ecx, edx
0x1004b7357  shr     ecx, 1Fh
0x1004b735a  add     edx, ecx
0x1004b735c  lea     ecx, [rdx+rdx*4]
0x1004b735f  cmp     r8d, ecx
0x1004b7362  jnz     short loc_1004B7369
0x1004b7364  call    ?UpdateStatSnapshot@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<19,1,268435714>::UpdateStatSnapshot(void)
0x1004b7369  mov     cs:qword_100714160, r15
0x1004b7370  mov     qword ptr [rbp+110h+var_C0], rbx
0x1004b7374  mov     esi, 0FFFFFFFFh
0x1004b7379  mov     eax, esi
0x1004b737b  lock xadd [r14+28h], eax
0x1004b7381  cmp     eax, 1
0x1004b7384  jnz     short loc_1004B73B1
0x1004b7386  cmp     qword ptr [r14+18h], 0
0x1004b738b  jz      short loc_1004B73B1
0x1004b738d  mov     rdx, r14
0x1004b7390  mov     rcx, [r14+20h]
0x1004b7394  call    ?RemoveElem@?$TList@VGroupList@@VSOS_ResourceGroup@@$0BA@UTListSLock@@@@QEAAXPEAVSOS_ResourceGroup@@@Z; TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(SOS_ResourceGroup *)
0x1004b7399  jmp     short loc_1004B73B1
0x1004b739b  mov     qword ptr [rbp+110h+var_C0], r15
0x1004b739f  mov     eax, esi
0x1004b73a1  lock xadd [rdi+28h], eax
0x1004b73a6  cmp     eax, 1
0x1004b73a9  jnz     short loc_1004B73B1
0x1004b73ab  cmp     [rdi+18h], rbx
0x1004b73af  jnz     short loc_1004B73DE
0x1004b73b1  mov     rdi, qword ptr [rbp+110h+var_C0]
0x1004b73b5  mov     r14, rbx
0x1004b73b8  test    rbx, rbx
0x1004b73bb  jz      short loc_1004B73EE
0x1004b73bd  movsxd  rax, dword ptr [rbx+20Ch]
0x1004b73c4  add     r12, rax
0x1004b73c7  movsxd  rax, dword ptr [rbx+33Ch]
0x1004b73ce  add     r12, rax
0x1004b73d1  mov     [rbp+110h+var_D0], r12
0x1004b73d5  mov     rdi, qword ptr [rbp+110h+var_C0]
0x1004b73d9  jmp     loc_1004B71B0
0x1004b73de  mov     rdx, rdi
0x1004b73e1  mov     rcx, [rdi+20h]
0x1004b73e5  call    ?RemoveElem@?$TList@VGroupList@@VSOS_ResourceGroup@@$0BA@UTListSLock@@@@QEAAXPEAVSOS_ResourceGroup@@@Z; TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(SOS_ResourceGroup *)
0x1004b73ea  mov     rdi, qword ptr [rbp+110h+var_C0]
0x1004b73ee  test    rdi, rdi
0x1004b73f1  jz      short loc_1004B7416
0x1004b73f3  mov     eax, esi
0x1004b73f5  lock xadd [rdi+28h], eax
0x1004b73fa  cmp     eax, 1
0x1004b73fd  jnz     short loc_1004B7412
0x1004b73ff  cmp     qword ptr [rdi+18h], 0
0x1004b7404  jz      short loc_1004B7412
0x1004b7406  mov     rdx, rdi
0x1004b7409  mov     rcx, [rdi+20h]
0x1004b740d  call    ?RemoveElem@?$TList@VGroupList@@VSOS_ResourceGroup@@$0BA@UTListSLock@@@@QEAAXPEAVSOS_ResourceGroup@@@Z; TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(SOS_ResourceGroup *)
0x1004b7412  mov     qword ptr [rbp+110h+var_C0], r15
0x1004b7416  mov     rcx, qword ptr [rbp+110h+var_C0+8]
0x1004b741a  test    rcx, rcx
0x1004b741d  jz      short loc_1004B7442
0x1004b741f  mov     eax, esi
0x1004b7421  lock xadd [rcx+28h], eax
0x1004b7426  cmp     eax, 1
0x1004b7429  jnz     short loc_1004B743E
0x1004b742b  cmp     qword ptr [rcx+18h], 0
0x1004b7430  jz      short loc_1004B743E
0x1004b7432  mov     rdx, rcx
0x1004b7435  mov     rcx, [rcx+20h]
0x1004b7439  call    ?RemoveElem@?$TList@VGroupList@@VSOS_ResourceGroup@@$0BA@UTListSLock@@@@QEAAXPEAVSOS_ResourceGroup@@@Z; TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(SOS_ResourceGroup *)
0x1004b743e  mov     qword ptr [rbp+110h+var_C0+8], r15
0x1004b7442  mov     [rbp+110h+var_B0], r15
0x1004b7446  lea     r8, ds:0[r12*8]
0x1004b744e  call    ?GetStackAvailableBytes@SOS_Task@@SA_KXZ; SOS_Task::GetStackAvailableBytes(void)
0x1004b7453  lea     edx, [r8+80h]
0x1004b745a  add     rdx, 10000h
0x1004b7461  cmp     rax, rdx
0x1004b7464  jb      loc_1004B7DD8
0x1004b746a  lea     rax, [r8+0Fh]
0x1004b746e  cmp     rax, r8
0x1004b7471  ja      short loc_1004B747D
0x1004b7473  mov     rax, 0FFFFFFFFFFFFFF0h
0x1004b747d  and     rax, 0FFFFFFFFFFFFFFF0h
0x1004b7481  call    _alloca_probe
0x1004b7486  sub     rsp, rax
0x1004b7489  lea     rax, [rsp+130h+var_110]
0x1004b748e  mov     [rbp+110h+var_70], rax
0x1004b7495  xorps   xmm0, xmm0
0x1004b7498  movdqu  [rbp+110h+var_98], xmm0
0x1004b749d  mov     [rbp+110h+var_80], r15
0x1004b74a4  mov     [rbp+110h+var_78], r15d
0x1004b74ab  mov     [rbp+110h+var_88], r15
0x1004b74b2  mov     [rbp+110h+var_88], r13
0x1004b74b9  mov     rcx, r13
0x1004b74bc  call    ?GetHead@?$TList@VNodeManager@@VSOS_Node@@$0BA@UTListSLock@@@@QEAAPEAVSOS_Node@@XZ; TList<NodeManager,SOS_Node,16,TListSLock>::GetHead(void)
0x1004b74c1  mov     rdi, rax
0x1004b74c4  mov     qword ptr [rbp+110h+var_98], rax
0x1004b74c8  mov     rcx, r13
0x1004b74cb  call    ?GetTail@?$TList@VGroupList@@VSOS_ResourceGroup@@$0BA@UTListSLock@@@@QEAAPEAVSOS_ResourceGroup@@XZ; TList<GroupList,SOS_ResourceGroup,16,TListSLock>::GetTail(void)
0x1004b74d0  mov     qword ptr [rbp+110h+var_98+8], rax
0x1004b74d7  mov     r12, r15
0x1004b74da  mov     r13d, r15d
0x1004b74dd  nop     dword ptr [rax]
0x1004b74e0  mov     rbx, r15
0x1004b74e3  test    r12, r12
0x1004b74e6  jnz     short loc_1004B74F0
0x1004b74e8  mov     rbx, rdi
0x1004b74eb  jmp     loc_1004B76FC
0x1004b74f0  test    rdi, rdi
0x1004b74f3  jz      loc_1004B76FC
0x1004b74f9  cmp     rdi, qword ptr [rbp+110h+var_98+8]
0x1004b7500  jz      loc_1004B76DE
0x1004b7506  mov     rbx, r15
0x1004b7509  mov     eax, gs:48h
0x1004b7511  mov     esi, eax
0x1004b7513  mov     eax, dword ptr cs:qword_100714160
0x1004b7519  test    eax, eax
0x1004b751b  jnz     short loc_1004B7536
0x1004b751d  xor     eax, eax
0x1004b751f  lock cmpxchg cs:qword_100714160, rsi
0x1004b7528  mov     eax, r15d
0x1004b752b  setz    al
0x1004b752e  test    eax, eax
0x1004b7530  jnz     loc_1004B7606
0x1004b7536  mov     eax, cs:?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004b753c  and     eax, 84h
0x1004b7541  mov     rdi, r15
0x1004b7544  cmp     al, 84h
0x1004b7546  jnz     short loc_1004B759E
0x1004b7548  mov     rcx, gs:58h
0x1004b7551  mov     eax, cs:_tls_index
0x1004b7557  mov     edx, cs:SystemThread_TlsOffset
0x1004b755d  add     rdx, [rcx+rax*8]
0x1004b7561  jz      short loc_1004B7573
0x1004b7563  cmp     [rdx+110h], rdx
0x1004b756a  jnz     short loc_1004B7573
0x1004b756c  mov     rdi, [rdx+100h]
0x1004b7573  test    rdi, rdi
0x1004b7576  jz      short loc_1004B759E
0x1004b7578  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, ebx; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004b757e  jz      short loc_1004B7596
0x1004b7580  lea     rcx, [rbp+110h+var_58]; lpPerformanceCount
0x1004b7587  call    cs:__imp_QueryPerformanceCounter
0x1004b758d  mov     rbx, qword ptr [rbp+110h+var_58]
0x1004b7594  jmp     short loc_1004B759E
0x1004b7596  mov     rbx, ds:7FFE0008h
0x1004b759e  lea     rcx, qword_100714160; this
0x1004b75a5  test    byte ptr cs:qword_1007149B5+2, 80h
0x1004b75ac  jz      short loc_1004B75BB
0x1004b75ae  mov     r8, rsi
0x1004b75b1  mov     rdx, rdi
0x1004b75b4  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<19,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x1004b75b9  jmp     short loc_1004B75C3
0x1004b75bb  mov     rdx, rsi
0x1004b75be  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x1004b75c3  test    rdi, rdi
0x1004b75c6  jz      short loc_1004B7606
  ... truncated ...
```
