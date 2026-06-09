# DBVolume::_AddSessionToCache(int,IDBSession *)

- ea: `0x180003b90`
- end: `0x180003e88`
- name: `?_AddSessionToCache@DBVolume@@IEAAJHPEAVIDBSession@@@Z`
- size: `760`
- prototype: `__int64 __fastcall(DBVolume *__hidden this, int, struct IDBSession *)`
- caller_count: `3`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009f80`
- `0x18000a4d0`
- `0x180027540`

## callees

- `0x180003b90`
- `0x18000416c`
- `0x180004220`
- `0x180004440`
- `0x1800068f0`
- `0x180035d40`
- `0x1800736c4`
- `0x180073cb0`
- `0x180074480`
- `0x180079030`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003ce9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003d73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003ce9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003d73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003bd6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003bd6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003bc2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003bc2`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180003e48`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180003e48`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180003d09`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180003d09`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003c06`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003c06`

## string_xrefs

- `0x180003d45`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180003e03`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`

## pseudocode

```c
__int64 __fastcall DBVolume::_AddSessionToCache(DBVolume *this, int a2, struct IDBSession *a3)
{
  unsigned __int64 *Value; // rax
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rax
  struct _TP_TIMER *v9; // rcx
  __int64 v10; // r13
  _QWORD *v11; // rax
  unsigned __int64 v12; // rdi
  _QWORD *v13; // rbx
  _QWORD *v14; // rax
  DWORD v16; // eax
  __int64 v17; // rdx
  _QWORD *v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rcx
  __int64 *v21; // rdx
  __int64 *v22; // rcx
  __int64 v23; // rax
  _QWORD v24[2]; // [rsp+30h] [rbp-58h] BYREF
  char v25; // [rsp+40h] [rbp-48h]
  unsigned __int64 v26; // [rsp+90h] [rbp+8h] BYREF
  struct IDBSession *v27; // [rsp+A0h] [rbp+18h] BYREF

  if ( g_dwCallerClientIdSlot == -1 )
  {
    v16 = TlsAlloc();
    if ( _InterlockedCompareExchange((volatile signed __int32 *)&g_dwCallerClientIdSlot, v16, -1) == -1 )
    {
      if ( v16 == -1 )
      {
        Log_AssertionEvent_2(0xFFFFFFFFLL, v17, 1073);
LABEL_3:
        LODWORD(v7) = -2;
        LODWORD(v8) = GetCurrentThreadId();
        goto LABEL_4;
      }
    }
    else
    {
      TlsFree(v16);
    }
  }
  Value = (unsigned __int64 *)TlsGetValue(g_dwCallerClientIdSlot);
  if ( !Value )
    goto LABEL_3;
  v7 = *Value;
  if ( !(unsigned int)*Value )
    goto LABEL_3;
  v8 = HIDWORD(v7);
LABEL_4:
  v9 = (struct _TP_TIMER *)*((_QWORD *)this + 24);
  v26 = __PAIR64__(v8, v7);
  if ( v9 )
    SetThreadpoolTimer(v9, &pftDueTime, 0, 0x124F80u);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  v27 = a3;
  if ( a3 )
  {
    (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)a3 + 8LL))(a3);
    (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)a3 + 8LL))(a3);
  }
  v10 = *((_QWORD *)this + 16);
  v11 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v26;
  v13 = v11;
  if ( v11 )
  {
    v11[2] = v26;
    v11[3] = a3;
    if ( a3 )
      (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)a3 + 8LL))(a3);
    v14 = *(_QWORD **)(v10 + 8);
    v13[1] = v14;
    *v13 = v10;
    *v14 = v13;
    *(_QWORD *)(v10 + 8) = v13;
    ++*((_QWORD *)this + 18);
  }
  else
  {
    v13 = 0;
  }
  if ( a3 )
    (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)a3 + 16LL))(a3);
  if ( !v13 )
  {
    Log_UnistoreHREvent_0(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      5058);
    if ( a3 )
      (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)a3 + 16LL))(a3);
    goto LABEL_26;
  }
  if ( *((_QWORD *)this + 18) > 0x1Eu )
  {
    v21 = (__int64 *)*((_QWORD *)this + 17);
    v22 = (__int64 *)v21[1];
    v23 = *v21;
    *v22 = *v21;
    *(_QWORD *)(v23 + 8) = v22;
    utl::_ContainerBase<utl::pair<CallerId,ATL::CComPtr<IDBSession>>,utl::allocator<utl::pair<CallerId,ATL::CComPtr<IDBSession>>>>::_DeleteNode<utl::_DlistNode<utl::pair<CallerId,ATL::CComPtr<IDBSession>>>>(
      (__int64)v22,
      v21);
    --*((_QWORD *)this + 18);
  }
  if ( a2 )
  {
    v18 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    v19 = (__int64)v18;
    if ( v18 )
    {
      v18[3] = v12;
      ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(v18 + 4, a3);
      utl::_HashTable<CallerId,utl::pair<CallerId const,ATL::CComPtr<IDBSession>>,utl::hash<CallerId>,utl::equal_to<CallerId>,utl::allocator<utl::pair<CallerId const,ATL::CComPtr<IDBSession>>>,0>::_FindInsertPos(
        (char *)this + 88,
        v24,
        v19 + 24);
      if ( v25 )
      {
        utl::_ContainerBase<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(
          v20,
          v19);
        v18 = (_QWORD *)v24[0];
      }
      else
      {
        v18 = *(_QWORD **)utl::_HashTable<CallerId,utl::pair<CallerId const,ATL::CComPtr<IDBSession>>,utl::hash<CallerId>,utl::equal_to<CallerId>,utl::allocator<utl::pair<CallerId const,ATL::CComPtr<IDBSession>>>,0>::_InsertAt(
                            (char *)this + 88,
                            &v26,
                            v24,
                            v19);
      }
    }
    if ( !v18 )
    {
      Log_UnistoreHREvent_0(
        2147942414LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        5067);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v27);
LABEL_26:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
      return 2147942414LL;
    }
  }
  if ( a3 )
    (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)a3 + 16LL))(a3);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  return 0;
}

```

## disassembly

```asm
0x180003b90  mov     [rsp+arg_8], rbx
0x180003b95  push    rbp
0x180003b96  push    rsi
0x180003b97  push    rdi
0x180003b98  push    r12
0x180003b9a  push    r13
0x180003b9c  push    r14
0x180003b9e  push    r15
0x180003ba0  sub     rsp, 50h
0x180003ba4  mov     rbp, rcx
0x180003ba7  mov     rsi, r8
0x180003baa  mov     ecx, cs:?g_dwCallerClientIdSlot@@3KC; ulong volatile g_dwCallerClientIdSlot
0x180003bb0  mov     r12d, edx
0x180003bb3  cmp     ecx, 0FFFFFFFFh
0x180003bb6  jz      loc_180003D09
0x180003bbc  mov     ecx, cs:?g_dwCallerClientIdSlot@@3KC; dwTlsIndex
0x180003bc2  call    cs:__imp_TlsGetValue
0x180003bc8  test    rax, rax
0x180003bcb  jnz     loc_180003D8A
0x180003bd1  mov     ebx, 0FFFFFFFEh
0x180003bd6  call    cs:__imp_GetCurrentThreadId
0x180003bdc  mov     rcx, [rbp+0C0h]; pti
0x180003be3  mov     dword ptr [rsp+88h+arg_0], ebx
0x180003bea  mov     dword ptr [rsp+88h+arg_0+4], eax
0x180003bf1  test    rcx, rcx
0x180003bf4  jz      short loc_180003C0C
0x180003bf6  mov     r9d, 124F80h; msWindowLength
0x180003bfc  lea     rdx, pftDueTime; pftDueTime
0x180003c03  xor     r8d, r8d; msPeriod
0x180003c06  call    cs:__imp_SetThreadpoolTimer
0x180003c0c  lea     rcx, [rbp+98h]; lpCriticalSection
0x180003c13  call    cs:__imp_EnterCriticalSection
0x180003c19  mov     [rsp+88h+arg_10], rsi
0x180003c21  lea     r15, [rbp+80h]
0x180003c28  test    rsi, rsi
0x180003c2b  jz      short loc_180003C4B
0x180003c2d  mov     rax, [rsi]
0x180003c30  mov     rcx, rsi
0x180003c33  mov     rax, [rax+8]
0x180003c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c3c  mov     rax, [rsi]
0x180003c3f  mov     rcx, rsi
0x180003c42  mov     rax, [rax+8]
0x180003c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c4b  mov     r13, [r15]
0x180003c4e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003c55  mov     ecx, 20h ; ' '; unsigned __int64
0x180003c5a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003c5f  mov     rdi, [rsp+88h+arg_0]
0x180003c67  mov     rbx, rax
0x180003c6a  test    rax, rax
0x180003c6d  jz      loc_180003D83
0x180003c73  mov     [rax+10h], rdi
0x180003c77  mov     [rax+18h], rsi
0x180003c7b  test    rsi, rsi
0x180003c7e  jnz     loc_180003E53
0x180003c84  mov     rax, [r13+8]
0x180003c88  mov     [rbx+8], rax
0x180003c8c  mov     [rbx], r13
0x180003c8f  mov     [rax], rbx
0x180003c92  mov     [r13+8], rbx
0x180003c96  inc     qword ptr [r15+10h]
0x180003c9a  test    rsi, rsi
0x180003c9d  jz      short loc_180003CAE
0x180003c9f  mov     rax, [rsi]
0x180003ca2  mov     rcx, rsi
0x180003ca5  mov     rax, [rax+10h]
0x180003ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cae  test    rbx, rbx
0x180003cb1  jz      loc_180003D3F
0x180003cb7  cmp     qword ptr [rbp+90h], 1Eh
0x180003cbf  ja      loc_180003E28
0x180003cc5  test    r12d, r12d
0x180003cc8  jnz     loc_180003DA1
0x180003cce  test    rsi, rsi
0x180003cd1  jz      short loc_180003CE2
0x180003cd3  mov     rax, [rsi]
0x180003cd6  mov     rcx, rsi
0x180003cd9  mov     rax, [rax+10h]
0x180003cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ce2  lea     rcx, [rbp+98h]; lpCriticalSection
0x180003ce9  call    cs:__imp_LeaveCriticalSection
0x180003cef  xor     eax, eax
0x180003cf1  mov     rbx, [rsp+88h+arg_8]
0x180003cf9  add     rsp, 50h
0x180003cfd  pop     r15
0x180003cff  pop     r14
0x180003d01  pop     r13
0x180003d03  pop     r12
0x180003d05  pop     rdi
0x180003d06  pop     rsi
0x180003d07  pop     rbp
0x180003d08  retn
0x180003d09  call    cs:__imp_TlsAlloc
0x180003d0f  mov     ecx, eax; dwTlsIndex
0x180003d11  mov     eax, 0FFFFFFFFh
0x180003d16  lock cmpxchg cs:?g_dwCallerClientIdSlot@@3KC, ecx; ulong volatile g_dwCallerClientIdSlot
0x180003d1e  cmp     eax, 0FFFFFFFFh
0x180003d21  jnz     loc_180003E48
0x180003d27  cmp     ecx, eax
0x180003d29  jnz     loc_180003BBC
0x180003d2f  mov     r8d, 431h
0x180003d35  call    Log_AssertionEvent_2
0x180003d3a  jmp     loc_180003BD1
0x180003d3f  mov     r9d, 13C2h
0x180003d45  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180003d4c  xor     edx, edx
0x180003d4e  mov     ecx, 8007000Eh
0x180003d53  call    Log_UnistoreHREvent_0
0x180003d58  test    rsi, rsi
0x180003d5b  jz      short loc_180003D6C
0x180003d5d  mov     rdx, [rsi]
0x180003d60  mov     rcx, rsi
0x180003d63  mov     rax, [rdx+10h]
0x180003d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d6c  lea     rcx, [rbp+98h]; lpCriticalSection
0x180003d73  call    cs:__imp_LeaveCriticalSection
0x180003d79  mov     eax, 8007000Eh
0x180003d7e  jmp     loc_180003CF1
0x180003d83  xor     ebx, ebx
0x180003d85  jmp     loc_180003C9A
0x180003d8a  mov     rbx, [rax]
0x180003d8d  test    ebx, ebx
0x180003d8f  jz      loc_180003BD1
0x180003d95  mov     rax, rbx
0x180003d98  shr     rax, 20h
0x180003d9c  jmp     loc_180003BDC
0x180003da1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003da8  mov     ecx, 28h ; '('; unsigned __int64
0x180003dad  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003db2  mov     rbx, rax
0x180003db5  test    rax, rax
0x180003db8  jz      short loc_180003DF4
0x180003dba  lea     rcx, [rax+20h]
0x180003dbe  mov     [rax+18h], rdi
0x180003dc2  mov     rdx, rsi
0x180003dc5  call    ??0?$CComPtrBase@VIDBVolume@@@ATL@@IEAA@PEAVIDBVolume@@@Z; ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(IDBVolume *)
0x180003dca  lea     r8, [rbx+18h]
0x180003dce  lea     rdx, [rsp+88h+var_58]
0x180003dd3  lea     rcx, [rbp+58h]
0x180003dd7  call    ?_FindInsertPos@?$_HashTable@UCallerId@@U?$pair@$$CBUCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@U?$hash@UCallerId@@@3@U?$equal_to@UCallerId@@@3@V?$allocator@U?$pair@$$CBUCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@@3@$0A@@utl@@AEAA?AU_InsertPosResult@12@AEBUCallerId@@@Z; utl::_HashTable<CallerId,utl::pair<CallerId const,ATL::CComPtr<IDBSession>>,utl::hash<CallerId>,utl::equal_to<CallerId>,utl::allocator<utl::pair<CallerId const,ATL::CComPtr<IDBSession>>>,0>::_FindInsertPos(CallerId const &)
0x180003ddc  cmp     [rsp+88h+var_48], 0
0x180003de1  jz      loc_180003E67
0x180003de7  mov     rdx, rbx
0x180003dea  call    ??$_DeleteNode@U?$_HashNode@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@utl@@@?$_ContainerBase@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@V?$allocator@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@2@@utl@@IEAAXPEAU?$_HashNode@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@1@@Z; utl::_ContainerBase<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(utl::_HashNode<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>> *)
0x180003def  mov     rax, [rsp+88h+var_58]
0x180003df4  test    rax, rax
0x180003df7  jnz     loc_180003CCE
0x180003dfd  mov     r9d, 13CBh
0x180003e03  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180003e0a  xor     edx, edx
0x180003e0c  mov     ecx, 8007000Eh
0x180003e11  call    Log_UnistoreHREvent_0
0x180003e16  lea     rcx, [rsp+88h+arg_10]; void *
0x180003e1e  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180003e23  jmp     loc_180003D6C
0x180003e28  mov     rdx, [r15+8]
0x180003e2c  mov     rcx, [rdx+8]
0x180003e30  mov     rax, [rdx]
0x180003e33  mov     [rcx], rax
0x180003e36  mov     [rax+8], rcx
0x180003e3a  call    ??$_DeleteNode@U?$_DlistNode@U?$pair@UCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@@utl@@@?$_ContainerBase@U?$pair@UCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@V?$allocator@U?$pair@UCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@@2@@utl@@IEAAXPEAU?$_DlistNode@U?$pair@UCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@@1@@Z; utl::_ContainerBase<utl::pair<CallerId,ATL::CComPtr<IDBSession>>,utl::allocator<utl::pair<CallerId,ATL::CComPtr<IDBSession>>>>::_DeleteNode<utl::_DlistNode<utl::pair<CallerId,ATL::CComPtr<IDBSession>>>>(utl::_DlistNode<utl::pair<CallerId,ATL::CComPtr<IDBSession>>> *)
0x180003e3f  dec     qword ptr [r15+10h]
0x180003e43  jmp     loc_180003CC5
0x180003e48  call    cs:__imp_TlsFree
0x180003e4e  jmp     loc_180003BBC
0x180003e53  mov     rax, [rsi]
0x180003e56  mov     rcx, rsi
0x180003e59  mov     rax, [rax+8]
0x180003e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e62  jmp     loc_180003C84
0x180003e67  mov     r9, rbx
0x180003e6a  lea     r8, [rsp+88h+var_58]
0x180003e6f  lea     rdx, [rsp+88h+arg_0]
0x180003e77  lea     rcx, [rbp+58h]
0x180003e7b  call    ?_InsertAt@?$_HashTable@UCallerId@@U?$pair@$$CBUCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@U?$hash@UCallerId@@@3@U?$equal_to@UCallerId@@@3@V?$allocator@U?$pair@$$CBUCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@@3@$0A@@utl@@AEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CBUCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@@utl@@U?$pair@$$CBUCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@2@@2@AEBU_InsertPosResult@12@PEAU?$_HashNode@U?$pair@$$CBUCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@@2@@Z; utl::_HashTable<CallerId,utl::pair<CallerId const,ATL::CComPtr<IDBSession>>,utl::hash<CallerId>,utl::equal_to<CallerId>,utl::allocator<utl::pair<CallerId const,ATL::CComPtr<IDBSession>>>,0>::_InsertAt(utl::_HashTable<CallerId,utl::pair<CallerId const,ATL::CComPtr<IDBSession>>,utl::hash<CallerId>,utl::equal_to<CallerId>,utl::allocator<utl::pair<CallerId const,ATL::CComPtr<IDBSession>>>,0>::_InsertPosResult const &,utl::_HashNode<utl::pair<CallerId const,ATL::CComPtr<IDBSession>>> *)
0x180003e80  mov     rax, [rax]
0x180003e83  jmp     loc_180003DF4
```
