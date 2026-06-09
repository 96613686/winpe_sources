# DBVolume::_GetSession(int,IDBSession * *,int &)

- ea: `0x18000a4d0`
- end: `0x18000ab0b`
- name: `?_GetSession@DBVolume@@IEAAJHPEAPEAVIDBSession@@AEAH@Z`
- size: `1595`
- prototype: `__int64 __fastcall(DBVolume *__hidden this, int, struct IDBSession **, int *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180025f20`
- `0x18007f1d0`

## callees

- `0x180003b90`
- `0x180004220`
- `0x180004440`
- `0x1800068f0`
- `0x18000a4d0`
- `0x180021c2c`
- `0x180035d40`
- `0x18004dcf0`
- `0x1800736c4`
- `0x180073cb0`
- `0x180074480`
- `0x180078a40`
- `0x180079030`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a53b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a548`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a6f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a53b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a548`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a6f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a55b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a58a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a7ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a7e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a80d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a81d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a8f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a55b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a58a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a7ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a7e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a80d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a81d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a8f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a51b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a6ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a51b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a6ba`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a507`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a6a6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a507`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a6a6`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000aa6a`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000aacb`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000aa6a`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000aacb`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000a5bf`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000a888`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000a5bf`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000a888`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a6ea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a6ea`

## string_xrefs

- `0x18000a56e`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000a596`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000a8c3`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000a8fc`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000a9a5`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000a9d3`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000aa20`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`

## pseudocode

```c
__int64 __fastcall DBVolume::_GetSession(DBVolume *this, int a2, struct IDBSession **a3, int *a4)
{
  unsigned __int64 *Value; // rax
  unsigned __int64 v8; // rbp
  unsigned __int64 v9; // r14
  int v10; // ebx
  unsigned int v11; // edi
  __int64 v13; // rdx
  __int64 v14; // rcx
  DWORD v15; // r10d
  __int64 *v16; // r15
  __int64 *i; // rdi
  struct IDBSession *v18; // rbx
  __int64 *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  unsigned __int64 *v22; // rax
  unsigned __int64 v23; // rdi
  unsigned __int64 v24; // rax
  struct _TP_TIMER *v25; // rcx
  __int64 v26; // rbp
  _QWORD *v27; // rax
  struct IDBSession *v28; // rdi
  _QWORD *v29; // r14
  _QWORD *v30; // rax
  int v31; // ebp
  int v32; // r14d
  struct IDBSession *v33; // rbx
  unsigned __int64 v34; // rcx
  int v35; // eax
  unsigned int v36; // ebx
  struct IDBSession *v37; // rbx
  int v38; // r14d
  int v39; // eax
  unsigned int v40; // edi
  DWORD v41; // eax
  __int64 v42; // rdx
  _QWORD *v43; // rax
  __int64 v44; // rbp
  __int64 v45; // rcx
  __int64 *v46; // rbx
  __int64 v47; // rdx
  char v48; // cl
  __int64 *v49; // rcx
  struct IDBSession *v50; // [rsp+30h] [rbp-68h] BYREF
  _QWORD v51[2]; // [rsp+38h] [rbp-60h] BYREF
  char v52; // [rsp+48h] [rbp-50h]
  struct IDBSession *v53; // [rsp+A0h] [rbp+8h] BYREF
  int v54; // [rsp+A8h] [rbp+10h]
  struct IDBSession **v55; // [rsp+B0h] [rbp+18h]
  struct IDBSession *v56; // [rsp+B8h] [rbp+20h] BYREF

  v55 = a3;
  v54 = a2;
  if ( g_dwCallerClientIdSlot == -1 )
  {
    v15 = TlsAlloc();
    if ( _InterlockedCompareExchange((volatile signed __int32 *)&g_dwCallerClientIdSlot, v15, -1) == -1 )
    {
      if ( v15 == -1 )
      {
        Log_AssertionEvent_2(v14, v13, 1073);
LABEL_3:
        LODWORD(v8) = -2;
        LODWORD(v9) = GetCurrentThreadId();
        goto LABEL_4;
      }
    }
    else
    {
      TlsFree(v15);
    }
  }
  Value = (unsigned __int64 *)TlsGetValue(g_dwCallerClientIdSlot);
  if ( !Value )
    goto LABEL_3;
  v8 = *Value;
  if ( !(unsigned int)*Value )
    goto LABEL_3;
  v9 = HIDWORD(v8);
LABEL_4:
  *a4 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  EnterCriticalSection(&g_csShutdownLock);
  v10 = g_serviceShuttingDown;
  LeaveCriticalSection(&g_csShutdownLock);
  if ( v10 )
  {
    v11 = -2147023781;
    Log_UnistoreHREvent_0(
      2147943515LL,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      5011);
LABEL_6:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
    Log_UnistoreHREvent_0(
      v11,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      4971);
    return v11;
  }
  else
  {
    v47 = *((_QWORD *)this + 13);
    if ( v47 )
    {
      v48 = *((_BYTE *)this + 120);
      v46 = *(__int64 **)(v47 + 16 * ((unsigned int)v9 & (unsigned __int64)((8LL << v48) - 1)));
      if ( v46 )
      {
        v49 = **(__int64 ***)(v47 + 16 * ((unsigned int)v9 & (unsigned __int64)((8LL << v48) - 1)) + 8);
        while ( v46 != v49 )
        {
          if ( v46[2] >= (unsigned __int64)(unsigned int)v9 )
          {
            if ( v46[2] > (unsigned __int64)(unsigned int)v9 )
              break;
            if ( (_DWORD)v8 == *((_DWORD *)v46 + 6) && (_DWORD)v9 == *((_DWORD *)v46 + 7) )
            {
              if ( v46 == (__int64 *)((char *)this + 88) )
                break;
              v33 = (struct IDBSession *)v46[4];
              if ( v33 )
                (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v33 + 8LL))(v33);
              *a3 = v33;
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
              return 0;
            }
          }
          v46 = (__int64 *)*v46;
        }
      }
    }
    v16 = (__int64 *)((char *)this + 128);
    for ( i = (__int64 *)*((_QWORD *)this + 16); i != v16; i = (__int64 *)*i )
    {
      if ( *((_DWORD *)i + 4) == (_DWORD)v8 && *((_DWORD *)i + 5) == (_DWORD)v9 )
      {
        v18 = (struct IDBSession *)i[3];
        v50 = v18;
        if ( v18 )
          (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v18 + 8LL))(v18);
        v19 = (__int64 *)i[1];
        v20 = *i;
        *v19 = *i;
        *(_QWORD *)(v20 + 8) = v19;
        v21 = i[3];
        if ( v21 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        operator delete(i);
        --*((_QWORD *)this + 18);
        if ( g_dwCallerClientIdSlot == -1 )
        {
          v41 = TlsAlloc();
          if ( _InterlockedCompareExchange((volatile signed __int32 *)&g_dwCallerClientIdSlot, v41, -1) != -1 )
          {
            TlsFree(v41);
            goto LABEL_22;
          }
          if ( v41 == -1 )
          {
            Log_AssertionEvent_2(0xFFFFFFFFLL, v42, 1073);
            goto LABEL_23;
          }
        }
LABEL_22:
        v22 = (unsigned __int64 *)TlsGetValue(g_dwCallerClientIdSlot);
        if ( v22 && (v23 = *v22, (unsigned int)*v22) )
        {
          v24 = HIDWORD(v23);
        }
        else
        {
LABEL_23:
          LODWORD(v23) = -2;
          LODWORD(v24) = GetCurrentThreadId();
        }
        v25 = (struct _TP_TIMER *)*((_QWORD *)this + 24);
        v53 = (struct IDBSession *)__PAIR64__(v24, v23);
        if ( v25 )
          SetThreadpoolTimer(v25, &pftDueTime, 0, 0x124F80u);
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
        v56 = v18;
        if ( v18 )
        {
          (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v18 + 8LL))(v18);
          (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v18 + 8LL))(v18);
        }
        v26 = *v16;
        v27 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
        v28 = v53;
        v29 = v27;
        if ( v27 )
        {
          v27[2] = v53;
          v27[3] = v18;
          if ( v18 )
            (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v18 + 8LL))(v18);
          v30 = *(_QWORD **)(v26 + 8);
          *v29 = v26;
          v29[1] = v30;
          *v30 = v29;
          *(_QWORD *)(v26 + 8) = v29;
          v31 = 1;
          ++*((_QWORD *)this + 18);
        }
        else
        {
          v31 = 0;
        }
        if ( v18 )
          (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v18 + 16LL))(v18);
        if ( v31 )
        {
          if ( *((_QWORD *)this + 18) > 0x1Eu )
            utl::list<utl::pair<CallerId,ATL::CComPtr<IDBSession>>,utl::allocator<utl::pair<CallerId,ATL::CComPtr<IDBSession>>>>::erase(
              (char *)this + 128,
              &v53,
              *((_QWORD *)this + 17));
          v32 = v54;
          if ( v54 )
          {
            v43 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
            v44 = (__int64)v43;
            if ( v43 )
            {
              v43[3] = v28;
              ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(v43 + 4, v18);
              utl::_HashTable<CallerId,utl::pair<CallerId const,ATL::CComPtr<IDBSession>>,utl::hash<CallerId>,utl::equal_to<CallerId>,utl::allocator<utl::pair<CallerId const,ATL::CComPtr<IDBSession>>>,0>::_FindInsertPos(
                (char *)this + 88,
                v51,
                v44 + 24);
              if ( v52 )
              {
                utl::_ContainerBase<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(
                  v45,
                  v44);
                v43 = (_QWORD *)v51[0];
              }
              else
              {
                v43 = *(_QWORD **)utl::_HashTable<CallerId,utl::pair<CallerId const,ATL::CComPtr<IDBSession>>,utl::hash<CallerId>,utl::equal_to<CallerId>,utl::allocator<utl::pair<CallerId const,ATL::CComPtr<IDBSession>>>,0>::_InsertAt(
                                    (char *)this + 88,
                                    &v53,
                                    v51,
                                    v44);
              }
            }
            if ( !v43 )
            {
              v11 = -2147024882;
              Log_UnistoreHREvent_0(
                2147942414LL,
                0,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
                5067);
              ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v56);
              goto LABEL_53;
            }
          }
          if ( v18 )
            (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v18 + 16LL))(v18);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
          *v55 = v18;
          *a4 = v32;
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
          return 0;
        }
        v11 = -2147024882;
        Log_UnistoreHREvent_0(
          2147942414LL,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          5058);
        if ( v18 )
          (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v18 + 16LL))(v18);
LABEL_53:
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
        Log_UnistoreHREvent_0(
          2147942414LL,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          5023);
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v50);
        goto LABEL_6;
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
    v34 = *((_QWORD *)this + 10);
    v53 = 0;
    v35 = DBSession::CreateInstance(v34, 0, &v53);
    v36 = v35;
    if ( v35 < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v35,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        4964);
      if ( v53 )
        (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v53 + 16LL))(v53);
      return v36;
    }
    else
    {
      v37 = v53;
      v38 = v54;
      v39 = DBVolume::_AddSessionToCache(this, v54, v53);
      v40 = v39;
      if ( v39 >= 0 )
      {
        *v55 = v37;
        *a4 = v38;
        return 0;
      }
      Log_UnistoreHREvent_0(
        (unsigned int)v39,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        4965);
      if ( v37 )
        (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v37 + 16LL))(v37);
      return v40;
    }
  }
}

```

## disassembly

```asm
0x18000a4d0  mov     [rsp+arg_10], r8
0x18000a4d5  mov     [rsp+arg_8], edx
0x18000a4d9  push    rbx
0x18000a4da  push    rbp
0x18000a4db  push    rsi
0x18000a4dc  push    rdi
0x18000a4dd  push    r12
0x18000a4df  push    r13
0x18000a4e1  push    r14
0x18000a4e3  sub     rsp, 60h
0x18000a4e7  mov     r10d, cs:?g_dwCallerClientIdSlot@@3KC; ulong volatile g_dwCallerClientIdSlot
0x18000a4ee  mov     r12, r9
0x18000a4f1  mov     rdi, r8
0x18000a4f4  mov     r13, rcx
0x18000a4f7  cmp     r10d, 0FFFFFFFFh
0x18000a4fb  jz      loc_18000A5BF
0x18000a501  mov     ecx, cs:?g_dwCallerClientIdSlot@@3KC; dwTlsIndex
0x18000a507  call    cs:__imp_TlsGetValue
0x18000a50d  test    rax, rax
0x18000a510  jnz     loc_18000A5F8
0x18000a516  mov     ebp, 0FFFFFFFEh
0x18000a51b  call    cs:__imp_GetCurrentThreadId
0x18000a521  mov     r14d, eax
0x18000a524  lea     rsi, [r13+98h]
0x18000a52b  mov     [rsp+98h+var_40], r15
0x18000a530  mov     rcx, rsi; lpCriticalSection
0x18000a533  mov     dword ptr [r12], 0
0x18000a53b  call    cs:__imp_EnterCriticalSection
0x18000a541  lea     rcx, ?g_csShutdownLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x18000a548  call    cs:__imp_EnterCriticalSection
0x18000a54e  mov     ebx, cs:?g_serviceShuttingDown@@3HA; int g_serviceShuttingDown
0x18000a554  lea     rcx, ?g_csShutdownLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x18000a55b  call    cs:__imp_LeaveCriticalSection
0x18000a561  test    ebx, ebx
0x18000a563  jz      loc_18000AA75
0x18000a569  mov     edi, 8007045Bh
0x18000a56e  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000a575  mov     ecx, edi
0x18000a577  mov     r9d, 1393h
0x18000a57d  mov     edx, 1
0x18000a582  call    Log_UnistoreHREvent_0
0x18000a587  mov     rcx, rsi; lpCriticalSection
0x18000a58a  call    cs:__imp_LeaveCriticalSection
0x18000a590  mov     r9d, 136Bh
0x18000a596  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000a59d  mov     edx, 1
0x18000a5a2  mov     ecx, edi
0x18000a5a4  call    Log_UnistoreHREvent_0
0x18000a5a9  mov     eax, edi
0x18000a5ab  mov     r15, [rsp+98h+var_40]
0x18000a5b0  add     rsp, 60h
0x18000a5b4  pop     r14
0x18000a5b6  pop     r13
0x18000a5b8  pop     r12
0x18000a5ba  pop     rdi
0x18000a5bb  pop     rsi
0x18000a5bc  pop     rbp
0x18000a5bd  pop     rbx
0x18000a5be  retn
0x18000a5bf  call    cs:__imp_TlsAlloc
0x18000a5c5  mov     r10d, eax
0x18000a5c8  mov     eax, 0FFFFFFFFh
0x18000a5cd  lock cmpxchg cs:?g_dwCallerClientIdSlot@@3KC, r10d; ulong volatile g_dwCallerClientIdSlot
0x18000a5d6  cmp     eax, 0FFFFFFFFh
0x18000a5d9  jnz     loc_18000AA67
0x18000a5df  cmp     r10d, eax
0x18000a5e2  jnz     loc_18000A501
0x18000a5e8  mov     r8d, 431h
0x18000a5ee  call    Log_AssertionEvent_2
0x18000a5f3  jmp     loc_18000A516
0x18000a5f8  mov     rbp, [rax]
0x18000a5fb  test    ebp, ebp
0x18000a5fd  jz      loc_18000A516
0x18000a603  mov     r14, rbp
0x18000a606  shr     r14, 20h
0x18000a60a  jmp     loc_18000A524
0x18000a60f  cmp     rbx, r9
0x18000a612  jnz     loc_18000A7EF
0x18000a618  lea     r15, [r13+80h]
0x18000a61f  mov     rdi, [r15]
0x18000a622  cmp     rdi, r15
0x18000a625  jz      loc_18000A81A
0x18000a62b  cmp     [rdi+10h], ebp
0x18000a62e  jnz     loc_18000A91E
0x18000a634  cmp     [rdi+14h], r14d
0x18000a638  jnz     loc_18000A91E
0x18000a63e  mov     rbx, [rdi+18h]
0x18000a642  mov     [rsp+98h+var_68], rbx
0x18000a647  test    rbx, rbx
0x18000a64a  jz      short loc_18000A65B
0x18000a64c  mov     rax, [rbx]
0x18000a64f  mov     rcx, rbx
0x18000a652  mov     rax, [rax+8]
0x18000a656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a65b  mov     rcx, [rdi+8]
0x18000a65f  mov     rax, [rdi]
0x18000a662  mov     [rcx], rax
0x18000a665  mov     [rax+8], rcx
0x18000a669  mov     rcx, [rdi+18h]
0x18000a66d  test    rcx, rcx
0x18000a670  jz      short loc_18000A67E
0x18000a672  mov     rax, [rcx]
0x18000a675  mov     rax, [rax+10h]
0x18000a679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a67e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000a685  mov     rcx, rdi; Block
0x18000a688  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a68d  dec     qword ptr [r15+10h]
0x18000a691  mov     ecx, cs:?g_dwCallerClientIdSlot@@3KC; ulong volatile g_dwCallerClientIdSlot
0x18000a697  cmp     ecx, 0FFFFFFFFh
0x18000a69a  jz      loc_18000A888
0x18000a6a0  mov     ecx, cs:?g_dwCallerClientIdSlot@@3KC; dwTlsIndex
0x18000a6a6  call    cs:__imp_TlsGetValue
0x18000a6ac  test    rax, rax
0x18000a6af  jnz     loc_18000A92D
0x18000a6b5  mov     edi, 0FFFFFFFEh
0x18000a6ba  call    cs:__imp_GetCurrentThreadId
0x18000a6c0  mov     rcx, [r13+0C0h]; pti
0x18000a6c7  mov     dword ptr [rsp+98h+arg_0], edi
0x18000a6ce  mov     dword ptr [rsp+98h+arg_0+4], eax
0x18000a6d5  test    rcx, rcx
0x18000a6d8  jz      short loc_18000A6F0
0x18000a6da  mov     r9d, 124F80h; msWindowLength
0x18000a6e0  lea     rdx, pftDueTime; pftDueTime
0x18000a6e7  xor     r8d, r8d; msPeriod
0x18000a6ea  call    cs:__imp_SetThreadpoolTimer
0x18000a6f0  mov     rcx, rsi; lpCriticalSection
0x18000a6f3  call    cs:__imp_EnterCriticalSection
0x18000a6f9  mov     [rsp+98h+arg_18], rbx
0x18000a701  test    rbx, rbx
0x18000a704  jz      short loc_18000A724
0x18000a706  mov     rax, [rbx]
0x18000a709  mov     rcx, rbx
0x18000a70c  mov     rax, [rax+8]
0x18000a710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a715  mov     rax, [rbx]
0x18000a718  mov     rcx, rbx
0x18000a71b  mov     rax, [rax+8]
0x18000a71f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a724  mov     rbp, [r15]
0x18000a727  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a72e  mov     ecx, 20h ; ' '; unsigned __int64
0x18000a733  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a738  mov     rdi, [rsp+98h+arg_0]
0x18000a740  mov     r14, rax
0x18000a743  test    rax, rax
0x18000a746  jz      loc_18000A926
0x18000a74c  mov     [rax+10h], rdi
0x18000a750  mov     [rax+18h], rbx
0x18000a754  test    rbx, rbx
0x18000a757  jnz     loc_18000AAD6
0x18000a75d  mov     rax, [rbp+8]
0x18000a761  mov     [r14], rbp
0x18000a764  mov     [r14+8], rax
0x18000a768  mov     [rax], r14
0x18000a76b  mov     [rbp+8], r14
0x18000a76f  mov     ebp, 1
0x18000a774  inc     qword ptr [r15+10h]
0x18000a778  test    rbx, rbx
0x18000a77b  jz      short loc_18000A78C
0x18000a77d  mov     rax, [rbx]
0x18000a780  mov     rcx, rbx
0x18000a783  mov     rax, [rax+10h]
0x18000a787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a78c  test    ebp, ebp
0x18000a78e  jz      loc_18000A8BE
0x18000a794  cmp     qword ptr [r13+90h], 1Eh
0x18000a79c  ja      loc_18000AA01
0x18000a7a2  mov     r14d, [rsp+98h+arg_8]
0x18000a7aa  test    r14d, r14d
0x18000a7ad  jnz     loc_18000A944
0x18000a7b3  test    rbx, rbx
0x18000a7b6  jz      short loc_18000A7C7
0x18000a7b8  mov     rax, [rbx]
0x18000a7bb  mov     rcx, rbx
0x18000a7be  mov     rax, [rax+10h]
0x18000a7c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7c7  mov     rcx, rsi; lpCriticalSection
0x18000a7ca  call    cs:__imp_LeaveCriticalSection
0x18000a7d0  mov     rax, [rsp+98h+arg_10]
0x18000a7d8  mov     rcx, rsi; lpCriticalSection
0x18000a7db  mov     [rax], rbx
0x18000a7de  mov     [r12], r14d
0x18000a7e2  call    cs:__imp_LeaveCriticalSection
0x18000a7e8  xor     eax, eax
0x18000a7ea  jmp     loc_18000A5AB
0x18000a7ef  mov     rbx, [rbx+20h]
0x18000a7f3  test    rbx, rbx
0x18000a7f6  jz      short loc_18000A807
0x18000a7f8  mov     rax, [rbx]
0x18000a7fb  mov     rcx, rbx
0x18000a7fe  mov     rax, [rax+8]
0x18000a802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a807  mov     rcx, rsi; lpCriticalSection
0x18000a80a  mov     [rdi], rbx
0x18000a80d  call    cs:__imp_LeaveCriticalSection
0x18000a813  xor     eax, eax
0x18000a815  jmp     loc_18000A5AB
0x18000a81a  mov     rcx, rsi; lpCriticalSection
0x18000a81d  call    cs:__imp_LeaveCriticalSection
0x18000a823  mov     rcx, [r13+50h]; unsigned __int64
0x18000a827  lea     r8, [rsp+98h+arg_0]; struct IDBSession **
0x18000a82f  xor     edx, edx; int
0x18000a831  mov     [rsp+98h+arg_0], 0
0x18000a83d  call    ?CreateInstance@DBSession@@SAJ_KHPEAPEAVIDBSession@@@Z; DBSession::CreateInstance(unsigned __int64,int,IDBSession * *)
0x18000a842  mov     ebx, eax
0x18000a844  test    eax, eax
0x18000a846  js      loc_18000AA1A
0x18000a84c  mov     rbx, [rsp+98h+arg_0]
0x18000a854  mov     rcx, r13; this
0x18000a857  mov     r14d, [rsp+98h+arg_8]
0x18000a85f  mov     r8, rbx; struct IDBSession *
0x18000a862  mov     edx, r14d; int
0x18000a865  call    ?_AddSessionToCache@DBVolume@@IEAAJHPEAVIDBSession@@@Z; DBVolume::_AddSessionToCache(int,IDBSession *)
0x18000a86a  mov     edi, eax
0x18000a86c  test    eax, eax
0x18000a86e  js      loc_18000A9CD
0x18000a874  mov     rax, [rsp+98h+arg_10]
0x18000a87c  mov     [rax], rbx
0x18000a87f  mov     [r12], r14d
0x18000a883  jmp     loc_18000A7E8
0x18000a888  call    cs:__imp_TlsAlloc
0x18000a88e  mov     ecx, eax; dwTlsIndex
0x18000a890  mov     eax, 0FFFFFFFFh
0x18000a895  lock cmpxchg cs:?g_dwCallerClientIdSlot@@3KC, ecx; ulong volatile g_dwCallerClientIdSlot
0x18000a89d  cmp     eax, 0FFFFFFFFh
0x18000a8a0  jnz     loc_18000AACB
0x18000a8a6  cmp     ecx, eax
0x18000a8a8  jnz     loc_18000A6A0
0x18000a8ae  mov     r8d, 431h
0x18000a8b4  call    Log_AssertionEvent_2
0x18000a8b9  jmp     loc_18000A6B5
0x18000a8be  mov     edi, 8007000Eh
0x18000a8c3  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000a8ca  mov     ecx, edi
0x18000a8cc  mov     r9d, 13C2h
0x18000a8d2  xor     edx, edx
0x18000a8d4  call    Log_UnistoreHREvent_0
0x18000a8d9  test    rbx, rbx
0x18000a8dc  jz      short loc_18000A8ED
0x18000a8de  mov     rax, [rbx]
0x18000a8e1  mov     rcx, rbx
0x18000a8e4  mov     rax, [rax+10h]
0x18000a8e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8ed  mov     rcx, rsi; lpCriticalSection
0x18000a8f0  call    cs:__imp_LeaveCriticalSection
0x18000a8f6  mov     r9d, 139Fh
0x18000a8fc  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000a903  mov     edx, 1
0x18000a908  mov     ecx, edi
0x18000a90a  call    Log_UnistoreHREvent_0
0x18000a90f  lea     rcx, [rsp+98h+var_68]; void *
0x18000a914  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18000a919  jmp     loc_18000A587
0x18000a91e  mov     rdi, [rdi]
0x18000a921  jmp     loc_18000A622
0x18000a926  xor     ebp, ebp
0x18000a928  jmp     loc_18000A778
0x18000a92d  mov     rdi, [rax]
0x18000a930  test    edi, edi
0x18000a932  jz      loc_18000A6B5
0x18000a938  mov     rax, rdi
0x18000a93b  shr     rax, 20h
0x18000a93f  jmp     loc_18000A6C0
0x18000a944  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a94b  mov     ecx, 28h ; '('; unsigned __int64
0x18000a950  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a955  mov     rbp, rax
0x18000a958  test    rax, rax
0x18000a95b  jz      short loc_18000A997
0x18000a95d  lea     rcx, [rax+20h]
0x18000a961  mov     [rax+18h], rdi
0x18000a965  mov     rdx, rbx
0x18000a968  call    ??0?$CComPtrBase@VIDBVolume@@@ATL@@IEAA@PEAVIDBVolume@@@Z; ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(IDBVolume *)
0x18000a96d  lea     r8, [rbp+18h]
0x18000a971  lea     rdx, [rsp+98h+var_60]
0x18000a976  lea     rcx, [r13+58h]
0x18000a97a  call    ?_FindInsertPos@?$_HashTable@UCallerId@@U?$pair@$$CBUCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@U?$hash@UCallerId@@@3@U?$equal_to@UCallerId@@@3@V?$allocator@U?$pair@$$CBUCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@@3@$0A@@utl@@AEAA?AU_InsertPosResult@12@AEBUCallerId@@@Z; utl::_HashTable<CallerId,utl::pair<CallerId const,ATL::CComPtr<IDBSession>>,utl::hash<CallerId>,utl::equal_to<CallerId>,utl::allocator<utl::pair<CallerId const,ATL::CComPtr<IDBSession>>>,0>::_FindInsertPos(CallerId const &)
0x18000a97f  cmp     [rsp+98h+var_50], 0
0x18000a984  jz      loc_18000AAEA
0x18000a98a  mov     rdx, rbp
0x18000a98d  call    ??$_DeleteNode@U?$_HashNode@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@utl@@@?$_ContainerBase@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@V?$allocator@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@2@@utl@@IEAAXPEAU?$_HashNode@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@1@@Z; utl::_ContainerBase<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(utl::_HashNode<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>> *)
0x18000a992  mov     rax, [rsp+98h+var_60]
0x18000a997  test    rax, rax
0x18000a99a  jnz     loc_18000A7B3
0x18000a9a0  mov     edi, 8007000Eh
0x18000a9a5  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000a9ac  mov     ecx, edi
0x18000a9ae  mov     r9d, 13CBh
0x18000a9b4  xor     edx, edx
0x18000a9b6  call    Log_UnistoreHREvent_0
0x18000a9bb  lea     rcx, [rsp+98h+arg_18]; void *
0x18000a9c3  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18000a9c8  jmp     loc_18000A8ED
0x18000a9cd  mov     r9d, 1365h
0x18000a9d3  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000a9da  mov     edx, 1
0x18000a9df  mov     ecx, edi
0x18000a9e1  call    Log_UnistoreHREvent_0
0x18000a9e6  test    rbx, rbx
  ... truncated ...
```
