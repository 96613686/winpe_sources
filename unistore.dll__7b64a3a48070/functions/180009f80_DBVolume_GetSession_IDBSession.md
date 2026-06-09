# DBVolume::GetSession(IDBSession * *)

- ea: `0x180009f80`
- end: `0x18000a4bc`
- name: `?GetSession@DBVolume@@EEAAJPEAPEAVIDBSession@@@Z`
- size: `1340`
- prototype: `__int64 __fastcall(DBVolume *__hidden this, struct IDBSession **)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180003b90`
- `0x180004440`
- `0x1800068f0`
- `0x180009f80`
- `0x180021c2c`
- `0x18004dcf0`
- `0x1800736c4`
- `0x180078a40`
- `0x180079030`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009fdc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009fe9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a195`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009fdc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009fe9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a195`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009ffc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a02b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a250`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a25d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a289`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a299`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a34f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009ffc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a02b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a250`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a25d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a289`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a299`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a34f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009fbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a162`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009fbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a162`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009fab`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a14e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009fab`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a14e`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000a43d`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000a49d`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000a43d`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000a49d`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000a064`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000a2e7`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000a064`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000a2e7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a18c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a18c`

## string_xrefs

- `0x18000a00f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000a037`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000a322`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000a35b`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000a3ac`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000a3f6`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`

## pseudocode

```c
__int64 __fastcall DBVolume::GetSession(DBVolume *this, struct IDBSession **a2)
{
  unsigned __int64 *Value; // rax
  unsigned __int64 v5; // rbp
  unsigned __int64 v6; // r15
  int v7; // ebx
  unsigned int v8; // edi
  __int64 v10; // rdx
  __int64 v11; // rcx
  DWORD v12; // r8d
  __int64 *v13; // r14
  __int64 *i; // rdi
  struct IDBSession *v15; // rbx
  __int64 *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  unsigned __int64 *v19; // rax
  unsigned __int64 v20; // rdi
  unsigned __int64 v21; // rax
  struct _TP_TIMER *v22; // rcx
  __int64 v23; // rbp
  _QWORD *v24; // rdi
  _QWORD *v25; // rax
  int v26; // edi
  struct IDBSession *v27; // rbx
  unsigned __int64 v28; // rcx
  int v29; // eax
  unsigned int v30; // ebx
  struct IDBSession *v31; // rbx
  int v32; // eax
  unsigned int v33; // edi
  DWORD v34; // eax
  __int64 v35; // rdx
  __int64 *v36; // rbx
  __int64 v37; // r8
  char v38; // cl
  __int64 *v39; // rcx
  struct IDBSession *v40; // [rsp+70h] [rbp+8h] BYREF
  struct IDBSession *v41; // [rsp+80h] [rbp+18h] BYREF

  if ( g_dwCallerClientIdSlot == -1 )
  {
    v12 = TlsAlloc();
    if ( _InterlockedCompareExchange((volatile signed __int32 *)&g_dwCallerClientIdSlot, v12, -1) == -1 )
    {
      if ( v12 == -1 )
      {
        Log_AssertionEvent_2(v11, v10, 1073);
LABEL_3:
        LODWORD(v5) = -2;
        LODWORD(v6) = GetCurrentThreadId();
        goto LABEL_4;
      }
    }
    else
    {
      TlsFree(v12);
    }
  }
  Value = (unsigned __int64 *)TlsGetValue(g_dwCallerClientIdSlot);
  if ( !Value )
    goto LABEL_3;
  v5 = *Value;
  if ( !(unsigned int)*Value )
    goto LABEL_3;
  v6 = HIDWORD(v5);
LABEL_4:
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  EnterCriticalSection(&g_csShutdownLock);
  v7 = g_serviceShuttingDown;
  LeaveCriticalSection(&g_csShutdownLock);
  if ( v7 )
  {
    v8 = -2147023781;
    Log_UnistoreHREvent_0(
      2147943515LL,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      5011);
LABEL_6:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
    Log_UnistoreHREvent_0(
      v8,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      4971);
    return v8;
  }
  else
  {
    v37 = *((_QWORD *)this + 13);
    if ( v37 )
    {
      v38 = *((_BYTE *)this + 120);
      v36 = *(__int64 **)(v37 + 16 * ((unsigned int)v6 & (unsigned __int64)((8LL << v38) - 1)));
      if ( v36 )
      {
        v39 = **(__int64 ***)(v37 + 16 * ((unsigned int)v6 & (unsigned __int64)((8LL << v38) - 1)) + 8);
        while ( v36 != v39 )
        {
          if ( v36[2] >= (unsigned __int64)(unsigned int)v6 )
          {
            if ( v36[2] > (unsigned __int64)(unsigned int)v6 )
              break;
            if ( (_DWORD)v5 == *((_DWORD *)v36 + 6) && (_DWORD)v6 == *((_DWORD *)v36 + 7) )
            {
              if ( v36 == (__int64 *)((char *)this + 88) )
                break;
              v27 = (struct IDBSession *)v36[4];
              if ( v27 )
                (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v27 + 8LL))(v27);
              *a2 = v27;
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
              return 0;
            }
          }
          v36 = (__int64 *)*v36;
        }
      }
    }
    v13 = (__int64 *)((char *)this + 128);
    for ( i = (__int64 *)*((_QWORD *)this + 16); i != v13; i = (__int64 *)*i )
    {
      if ( *((_DWORD *)i + 4) == (_DWORD)v5 && *((_DWORD *)i + 5) == (_DWORD)v6 )
      {
        v15 = (struct IDBSession *)i[3];
        v41 = v15;
        if ( v15 )
          (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v15 + 8LL))(v15);
        v16 = (__int64 *)i[1];
        v17 = *i;
        *v16 = *i;
        *(_QWORD *)(v17 + 8) = v16;
        v18 = i[3];
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        operator delete(i);
        --*((_QWORD *)this + 18);
        if ( g_dwCallerClientIdSlot == -1 )
        {
          v34 = TlsAlloc();
          if ( _InterlockedCompareExchange((volatile signed __int32 *)&g_dwCallerClientIdSlot, v34, -1) != -1 )
          {
            TlsFree(v34);
            goto LABEL_22;
          }
          if ( v34 == -1 )
          {
            Log_AssertionEvent_2(0xFFFFFFFFLL, v35, 1073);
            goto LABEL_23;
          }
        }
LABEL_22:
        v19 = (unsigned __int64 *)TlsGetValue(g_dwCallerClientIdSlot);
        if ( v19 && (v20 = *v19, (unsigned int)*v19) )
        {
          v21 = HIDWORD(v20);
        }
        else
        {
LABEL_23:
          LODWORD(v20) = -2;
          LODWORD(v21) = GetCurrentThreadId();
        }
        v22 = (struct _TP_TIMER *)*((_QWORD *)this + 24);
        v40 = (struct IDBSession *)__PAIR64__(v21, v20);
        if ( v22 )
          SetThreadpoolTimer(v22, &pftDueTime, 0, 0x124F80u);
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
        if ( v15 )
        {
          (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v15 + 8LL))(v15);
          (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v15 + 8LL))(v15);
        }
        v23 = *v13;
        v24 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v24 )
        {
          v24[2] = v40;
          v24[3] = v15;
          if ( v15 )
            (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v15 + 8LL))(v15);
          v25 = *(_QWORD **)(v23 + 8);
          v24[1] = v25;
          *v24 = v23;
          *v25 = v24;
          *(_QWORD *)(v23 + 8) = v24;
          v26 = 1;
          ++*((_QWORD *)this + 18);
        }
        else
        {
          v26 = 0;
        }
        if ( v15 )
          (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v15 + 16LL))(v15);
        if ( v26 )
        {
          if ( *((_QWORD *)this + 18) > 0x1Eu )
            utl::list<utl::pair<CallerId,ATL::CComPtr<IDBSession>>,utl::allocator<utl::pair<CallerId,ATL::CComPtr<IDBSession>>>>::erase(
              (char *)this + 128,
              &v40,
              *((_QWORD *)this + 17));
          if ( v15 )
            (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v15 + 16LL))(v15);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
          *a2 = v15;
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
          return 0;
        }
        v8 = -2147024882;
        Log_UnistoreHREvent_0(
          2147942414LL,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          5058);
        if ( v15 )
          (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v15 + 16LL))(v15);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
        Log_UnistoreHREvent_0(
          2147942414LL,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          5023);
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v41);
        goto LABEL_6;
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
    v28 = *((_QWORD *)this + 10);
    v40 = 0;
    v29 = DBSession::CreateInstance(v28, 0, &v40);
    v30 = v29;
    if ( v29 < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v29,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        4964);
      if ( v40 )
        (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v40 + 16LL))(v40);
      return v30;
    }
    else
    {
      v31 = v40;
      v32 = DBVolume::_AddSessionToCache(this, 0, v40);
      v33 = v32;
      if ( v32 >= 0 )
      {
        *a2 = v31;
        return 0;
      }
      Log_UnistoreHREvent_0(
        (unsigned int)v32,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        4965);
      if ( v31 )
        (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v31 + 16LL))(v31);
      return v33;
    }
  }
}

```

## disassembly

```asm
0x180009f80  push    rbx
0x180009f82  push    rbp
0x180009f83  push    rsi
0x180009f84  push    r12
0x180009f86  push    r13
0x180009f88  push    r15
0x180009f8a  sub     rsp, 38h
0x180009f8e  mov     r8d, cs:?g_dwCallerClientIdSlot@@3KC; ulong volatile g_dwCallerClientIdSlot
0x180009f95  mov     r12, rdx
0x180009f98  mov     r13, rcx
0x180009f9b  cmp     r8d, 0FFFFFFFFh
0x180009f9f  jz      loc_18000A064
0x180009fa5  mov     ecx, cs:?g_dwCallerClientIdSlot@@3KC; dwTlsIndex
0x180009fab  call    cs:__imp_TlsGetValue
0x180009fb1  test    rax, rax
0x180009fb4  jnz     loc_18000A09D
0x180009fba  mov     ebp, 0FFFFFFFEh
0x180009fbf  call    cs:__imp_GetCurrentThreadId
0x180009fc5  mov     r15d, eax
0x180009fc8  lea     rsi, [r13+98h]
0x180009fcf  mov     [rsp+68h+arg_8], rdi
0x180009fd4  mov     rcx, rsi; lpCriticalSection
0x180009fd7  mov     [rsp+68h+var_38], r14
0x180009fdc  call    cs:__imp_EnterCriticalSection
0x180009fe2  lea     rcx, ?g_csShutdownLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x180009fe9  call    cs:__imp_EnterCriticalSection
0x180009fef  mov     ebx, cs:?g_serviceShuttingDown@@3HA; int g_serviceShuttingDown
0x180009ff5  lea     rcx, ?g_csShutdownLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x180009ffc  call    cs:__imp_LeaveCriticalSection
0x18000a002  test    ebx, ebx
0x18000a004  jz      loc_18000A448
0x18000a00a  mov     edi, 8007045Bh
0x18000a00f  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000a016  mov     ecx, edi
0x18000a018  mov     r9d, 1393h
0x18000a01e  mov     edx, 1
0x18000a023  call    Log_UnistoreHREvent_0
0x18000a028  mov     rcx, rsi; lpCriticalSection
0x18000a02b  call    cs:__imp_LeaveCriticalSection
0x18000a031  mov     r9d, 136Bh
0x18000a037  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000a03e  mov     edx, 1
0x18000a043  mov     ecx, edi
0x18000a045  call    Log_UnistoreHREvent_0
0x18000a04a  mov     eax, edi
0x18000a04c  mov     r14, [rsp+68h+var_38]
0x18000a051  mov     rdi, [rsp+68h+arg_8]
0x18000a056  add     rsp, 38h
0x18000a05a  pop     r15
0x18000a05c  pop     r13
0x18000a05e  pop     r12
0x18000a060  pop     rsi
0x18000a061  pop     rbp
0x18000a062  pop     rbx
0x18000a063  retn
0x18000a064  call    cs:__imp_TlsAlloc
0x18000a06a  mov     r8d, eax
0x18000a06d  mov     eax, 0FFFFFFFFh
0x18000a072  lock cmpxchg cs:?g_dwCallerClientIdSlot@@3KC, r8d; ulong volatile g_dwCallerClientIdSlot
0x18000a07b  cmp     eax, 0FFFFFFFFh
0x18000a07e  jnz     loc_18000A43A
0x18000a084  cmp     r8d, eax
0x18000a087  jnz     loc_180009FA5
0x18000a08d  mov     r8d, 431h
0x18000a093  call    Log_AssertionEvent_2
0x18000a098  jmp     loc_180009FBA
0x18000a09d  mov     rbp, [rax]
0x18000a0a0  test    ebp, ebp
0x18000a0a2  jz      loc_180009FBA
0x18000a0a8  mov     r15, rbp
0x18000a0ab  shr     r15, 20h
0x18000a0af  jmp     loc_180009FC8
0x18000a0b4  cmp     rbx, rdx
0x18000a0b7  jnz     loc_18000A26A
0x18000a0bd  lea     r14, [r13+80h]
0x18000a0c4  mov     rdi, [r14]
0x18000a0c7  cmp     rdi, r14
0x18000a0ca  jz      loc_18000A296
0x18000a0d0  cmp     [rdi+10h], ebp
0x18000a0d3  jnz     loc_18000A380
0x18000a0d9  cmp     [rdi+14h], r15d
0x18000a0dd  jnz     loc_18000A380
0x18000a0e3  mov     rbx, [rdi+18h]
0x18000a0e7  mov     [rsp+68h+arg_10], rbx
0x18000a0ef  test    rbx, rbx
0x18000a0f2  jz      short loc_18000A103
0x18000a0f4  mov     rax, [rbx]
0x18000a0f7  mov     rcx, rbx
0x18000a0fa  mov     rax, [rax+8]
0x18000a0fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a103  mov     rcx, [rdi+8]
0x18000a107  mov     rax, [rdi]
0x18000a10a  mov     [rcx], rax
0x18000a10d  mov     [rax+8], rcx
0x18000a111  mov     rcx, [rdi+18h]
0x18000a115  test    rcx, rcx
0x18000a118  jz      short loc_18000A126
0x18000a11a  mov     rax, [rcx]
0x18000a11d  mov     rax, [rax+10h]
0x18000a121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a126  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000a12d  mov     rcx, rdi; Block
0x18000a130  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a135  dec     qword ptr [r14+10h]
0x18000a139  mov     ecx, cs:?g_dwCallerClientIdSlot@@3KC; ulong volatile g_dwCallerClientIdSlot
0x18000a13f  cmp     ecx, 0FFFFFFFFh
0x18000a142  jz      loc_18000A2E7
0x18000a148  mov     ecx, cs:?g_dwCallerClientIdSlot@@3KC; dwTlsIndex
0x18000a14e  call    cs:__imp_TlsGetValue
0x18000a154  test    rax, rax
0x18000a157  jnz     loc_18000A38F
0x18000a15d  mov     edi, 0FFFFFFFEh
0x18000a162  call    cs:__imp_GetCurrentThreadId
0x18000a168  mov     rcx, [r13+0C0h]; pti
0x18000a16f  mov     dword ptr [rsp+68h+arg_0], edi
0x18000a173  mov     dword ptr [rsp+68h+arg_0+4], eax
0x18000a177  test    rcx, rcx
0x18000a17a  jz      short loc_18000A192
0x18000a17c  mov     r9d, 124F80h; msWindowLength
0x18000a182  lea     rdx, pftDueTime; pftDueTime
0x18000a189  xor     r8d, r8d; msPeriod
0x18000a18c  call    cs:__imp_SetThreadpoolTimer
0x18000a192  mov     rcx, rsi; lpCriticalSection
0x18000a195  call    cs:__imp_EnterCriticalSection
0x18000a19b  test    rbx, rbx
0x18000a19e  jz      short loc_18000A1BE
0x18000a1a0  mov     rax, [rbx]
0x18000a1a3  mov     rcx, rbx
0x18000a1a6  mov     rax, [rax+8]
0x18000a1aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1af  mov     rax, [rbx]
0x18000a1b2  mov     rcx, rbx
0x18000a1b5  mov     rax, [rax+8]
0x18000a1b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1be  mov     rbp, [r14]
0x18000a1c1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a1c8  mov     ecx, 20h ; ' '; unsigned __int64
0x18000a1cd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a1d2  mov     rdi, rax
0x18000a1d5  test    rax, rax
0x18000a1d8  jz      loc_18000A388
0x18000a1de  mov     rax, [rsp+68h+arg_0]
0x18000a1e3  mov     [rdi+10h], rax
0x18000a1e7  mov     [rdi+18h], rbx
0x18000a1eb  test    rbx, rbx
0x18000a1ee  jnz     loc_18000A4A8
0x18000a1f4  mov     rax, [rbp+8]
0x18000a1f8  mov     [rdi+8], rax
0x18000a1fc  mov     [rdi], rbp
0x18000a1ff  mov     [rax], rdi
0x18000a202  mov     [rbp+8], rdi
0x18000a206  mov     edi, 1
0x18000a20b  inc     qword ptr [r14+10h]
0x18000a20f  test    rbx, rbx
0x18000a212  jz      short loc_18000A223
0x18000a214  mov     rax, [rbx]
0x18000a217  mov     rcx, rbx
0x18000a21a  mov     rax, [rax+10h]
0x18000a21e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a223  test    edi, edi
0x18000a225  jz      loc_18000A31D
0x18000a22b  cmp     qword ptr [r13+90h], 1Eh
0x18000a233  ja      loc_18000A3DA
0x18000a239  test    rbx, rbx
0x18000a23c  jz      short loc_18000A24D
0x18000a23e  mov     rax, [rbx]
0x18000a241  mov     rcx, rbx
0x18000a244  mov     rax, [rax+10h]
0x18000a248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a24d  mov     rcx, rsi; lpCriticalSection
0x18000a250  call    cs:__imp_LeaveCriticalSection
0x18000a256  mov     rcx, rsi; lpCriticalSection
0x18000a259  mov     [r12], rbx
0x18000a25d  call    cs:__imp_LeaveCriticalSection
0x18000a263  xor     eax, eax
0x18000a265  jmp     loc_18000A04C
0x18000a26a  mov     rbx, [rbx+20h]
0x18000a26e  test    rbx, rbx
0x18000a271  jz      short loc_18000A282
0x18000a273  mov     rax, [rbx]
0x18000a276  mov     rcx, rbx
0x18000a279  mov     rax, [rax+8]
0x18000a27d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a282  mov     rcx, rsi; lpCriticalSection
0x18000a285  mov     [r12], rbx
0x18000a289  call    cs:__imp_LeaveCriticalSection
0x18000a28f  xor     eax, eax
0x18000a291  jmp     loc_18000A04C
0x18000a296  mov     rcx, rsi; lpCriticalSection
0x18000a299  call    cs:__imp_LeaveCriticalSection
0x18000a29f  mov     rcx, [r13+50h]; unsigned __int64
0x18000a2a3  lea     r8, [rsp+68h+arg_0]; struct IDBSession **
0x18000a2a8  xor     edx, edx; int
0x18000a2aa  mov     [rsp+68h+arg_0], 0
0x18000a2b3  call    ?CreateInstance@DBSession@@SAJ_KHPEAPEAVIDBSession@@@Z; DBSession::CreateInstance(unsigned __int64,int,IDBSession * *)
0x18000a2b8  mov     ebx, eax
0x18000a2ba  test    eax, eax
0x18000a2bc  js      loc_18000A3F0
0x18000a2c2  mov     rbx, [rsp+68h+arg_0]
0x18000a2c7  xor     edx, edx; int
0x18000a2c9  mov     r8, rbx; struct IDBSession *
0x18000a2cc  mov     rcx, r13; this
0x18000a2cf  call    ?_AddSessionToCache@DBVolume@@IEAAJHPEAVIDBSession@@@Z; DBVolume::_AddSessionToCache(int,IDBSession *)
0x18000a2d4  mov     edi, eax
0x18000a2d6  test    eax, eax
0x18000a2d8  js      loc_18000A3A6
0x18000a2de  mov     [r12], rbx
0x18000a2e2  jmp     loc_18000A263
0x18000a2e7  call    cs:__imp_TlsAlloc
0x18000a2ed  mov     ecx, eax; dwTlsIndex
0x18000a2ef  mov     eax, 0FFFFFFFFh
0x18000a2f4  lock cmpxchg cs:?g_dwCallerClientIdSlot@@3KC, ecx; ulong volatile g_dwCallerClientIdSlot
0x18000a2fc  cmp     eax, 0FFFFFFFFh
0x18000a2ff  jnz     loc_18000A49D
0x18000a305  cmp     ecx, eax
0x18000a307  jnz     loc_18000A148
0x18000a30d  mov     r8d, 431h
0x18000a313  call    Log_AssertionEvent_2
0x18000a318  jmp     loc_18000A15D
0x18000a31d  mov     edi, 8007000Eh
0x18000a322  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000a329  mov     ecx, edi
0x18000a32b  mov     r9d, 13C2h
0x18000a331  xor     edx, edx
0x18000a333  call    Log_UnistoreHREvent_0
0x18000a338  test    rbx, rbx
0x18000a33b  jz      short loc_18000A34C
0x18000a33d  mov     rax, [rbx]
0x18000a340  mov     rcx, rbx
0x18000a343  mov     rax, [rax+10h]
0x18000a347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a34c  mov     rcx, rsi; lpCriticalSection
0x18000a34f  call    cs:__imp_LeaveCriticalSection
0x18000a355  mov     r9d, 139Fh
0x18000a35b  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000a362  mov     edx, 1
0x18000a367  mov     ecx, edi
0x18000a369  call    Log_UnistoreHREvent_0
0x18000a36e  lea     rcx, [rsp+68h+arg_10]; void *
0x18000a376  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18000a37b  jmp     loc_18000A028
0x18000a380  mov     rdi, [rdi]
0x18000a383  jmp     loc_18000A0C7
0x18000a388  xor     edi, edi
0x18000a38a  jmp     loc_18000A20F
0x18000a38f  mov     rdi, [rax]
0x18000a392  test    edi, edi
0x18000a394  jz      loc_18000A15D
0x18000a39a  mov     rax, rdi
0x18000a39d  shr     rax, 20h
0x18000a3a1  jmp     loc_18000A168
0x18000a3a6  mov     r9d, 1365h
0x18000a3ac  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000a3b3  mov     edx, 1
0x18000a3b8  mov     ecx, edi
0x18000a3ba  call    Log_UnistoreHREvent_0
0x18000a3bf  test    rbx, rbx
0x18000a3c2  jz      short loc_18000A3D3
0x18000a3c4  mov     rcx, [rbx]
0x18000a3c7  mov     rax, [rcx+10h]
0x18000a3cb  mov     rcx, rbx
0x18000a3ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3d3  mov     eax, edi
0x18000a3d5  jmp     loc_18000A04C
0x18000a3da  mov     r8, [r14+8]
0x18000a3de  lea     rdx, [rsp+68h+arg_0]
0x18000a3e3  mov     rcx, r14
0x18000a3e6  call    ?erase@?$list@U?$pair@UCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@V?$allocator@U?$pair@UCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@@2@@utl@@QEAA?AV?$_DlistIt@U?$_DlistNode@U?$pair@UCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@@utl@@U?$pair@UCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@2@@2@V?$_DlistConstIt@U?$_DlistNode@U?$pair@UCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@@utl@@U?$pair@UCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@2@@2@@Z; utl::list<utl::pair<CallerId,ATL::CComPtr<IDBSession>>,utl::allocator<utl::pair<CallerId,ATL::CComPtr<IDBSession>>>>::erase(utl::_DlistConstIt<utl::_DlistNode<utl::pair<CallerId,ATL::CComPtr<IDBSession>>>,utl::pair<CallerId,ATL::CComPtr<IDBSession>>>)
0x18000a3eb  jmp     loc_18000A239
0x18000a3f0  mov     r9d, 1364h
0x18000a3f6  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000a3fd  mov     edx, 1
0x18000a402  mov     ecx, ebx
0x18000a404  call    Log_UnistoreHREvent_0
0x18000a409  mov     rcx, [rsp+68h+arg_0]
0x18000a40e  test    rcx, rcx
0x18000a411  jz      short loc_18000A41F
0x18000a413  mov     rdx, [rcx]
0x18000a416  mov     rax, [rdx+10h]
0x18000a41a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a41f  mov     eax, ebx
0x18000a421  jmp     loc_18000A04C
0x18000a426  cmp     ebp, [rbx+18h]
0x18000a429  jnz     short loc_18000A435
0x18000a42b  cmp     r15d, [rbx+1Ch]
0x18000a42f  jz      loc_18000A0B4
0x18000a435  mov     rbx, [rbx]
0x18000a438  jmp     short loc_18000A486
0x18000a43a  mov     ecx, r8d; dwTlsIndex
0x18000a43d  call    cs:__imp_TlsFree
0x18000a443  jmp     loc_180009FA5
0x18000a448  mov     r8, [r13+68h]
0x18000a44c  lea     rdx, [r13+58h]
0x18000a450  test    r8, r8
0x18000a453  jz      loc_18000A0BD
0x18000a459  movzx   ecx, byte ptr [rdx+20h]
0x18000a45d  mov     eax, 8
0x18000a462  shl     rax, cl
0x18000a465  dec     rax
0x18000a468  mov     r9d, r15d
  ... truncated ...
```
