# CAutoDestItemsFolder::_BindToTargetShellItem(_ITEMIDLIST_RELATIVE const *,_GUID const &,void * *)

- ea: `0x18003c550`
- end: `0x18003ccfa`
- name: `?_BindToTargetShellItem@CAutoDestItemsFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_GUID@@PEAPEAX@Z`
- size: `1962`
- prototype: `__int64 __fastcall(CAutoDestItemsFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, const struct _GUID *, void **)`
- caller_count: `9`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006f24c`
- `0x180084df0`
- `0x1800c14f0`
- `0x1800c25d0`
- `0x180252cc0`
- `0x180343af0`
- `0x180634380`
- `0x180635400`
- `0x180638c80`

## callees

- `0x18001eb5c`
- `0x180038f50`
- `0x18003bdd0`
- `0x18003c410`
- `0x18003c550`
- `0x18003df10`
- `0x18003eb00`
- `0x18003eb20`
- `0x180085a60`
- `0x1800a3704`
- `0x1803b1f60`
- `0x1803b23ec`
- `0x1803b243c`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003c949`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003c949`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003cc58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003cc81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ccab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ccd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003cc58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003cc81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ccab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ccd5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003cc6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003cc95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ccbf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003cce9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003cc6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003cc95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ccbf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003cce9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c629`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c68e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c72b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c78e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c629`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c68e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c72b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c78e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003c5a9`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003c6cc`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003c5a9`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003c6cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c849`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003caa5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cb19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c849`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003caa5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cb19`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c7f8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c8d9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003cc3a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c7f8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c8d9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003cc3a`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x18003c899`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x18003c899`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAutoDestItemsFolder::_BindToTargetShellItem(
        CAutoDestItemsFolder *this,
        const struct _ITEMIDLIST_RELATIVE *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v7; // rdi
  DWORD CurrentThreadId; // ebx
  unsigned __int64 v9; // r8
  __int64 v10; // rsi
  __int64 i; // rax
  __int64 *v12; // rcx
  __int64 v13; // rdi
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // r8
  __int64 v16; // rsi
  __int64 j; // rax
  __int64 *v18; // rcx
  unsigned int v19; // edi
  unsigned __int64 v20; // rax
  __int64 v21; // rdx
  void *v22; // rcx
  int v24; // eax
  LPVOID v25; // r14
  int inited; // esi
  CMarshalByValue *v27; // rax
  CMarshalByValue *v28; // rdi
  __int64 v29; // rcx
  void *v30; // rcx
  void *v31; // rcx
  char *v32; // rax
  signed __int64 v33; // rdx
  signed __int64 v34; // rax
  char *v35; // rax
  signed __int64 v36; // rdx
  signed __int64 v37; // rax
  void *v38; // rbx
  HANDLE v39; // rax
  void *v40; // rbx
  HANDLE ProcessHeap; // rax
  void *v42; // rbx
  HANDLE v43; // rax
  void *v44; // rbx
  HANDLE v45; // rax
  union _RTL_RUN_ONCE *v46; // [rsp+20h] [rbp-E0h] BYREF
  int v47; // [rsp+28h] [rbp-D8h]
  WINBOOL fPending[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  PROPVARIANT pvar[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v52; // [rsp+58h] [rbp-A8h]
  int v53; // [rsp+60h] [rbp-A0h] BYREF
  const char *v54; // [rsp+68h] [rbp-98h]
  LPVOID v55; // [rsp+70h] [rbp-90h]
  char v56; // [rsp+78h] [rbp-88h]
  _QWORD v57[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v58; // [rsp+90h] [rbp-70h]
  DWORD v59; // [rsp+98h] [rbp-68h]
  int *v60; // [rsp+A0h] [rbp-60h]
  char v61; // [rsp+A8h] [rbp-58h]
  int v62; // [rsp+B0h] [rbp-50h] BYREF
  const char *v63; // [rsp+B8h] [rbp-48h]
  LPVOID lpMem; // [rsp+C0h] [rbp-40h]
  char v65; // [rsp+C8h] [rbp-38h]
  _QWORD v66[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v67; // [rsp+E0h] [rbp-20h]
  DWORD v68; // [rsp+E8h] [rbp-18h]
  int *v69; // [rsp+F0h] [rbp-10h]
  char v70; // [rsp+F8h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  *a4 = 0;
  Context = 0;
  fPending[0] = 0;
  if ( InitOnceBeginInitialize(&`FavoritesTelemetry::Instance'::`2'::wrapper, 0, fPending, &Context) && fPending[0] )
  {
    v46 = &`FavoritesTelemetry::Instance'::`2'::wrapper;
    Context = &qword_18082CC58;
    qword_18082CC60 = 0;
    byte_18082CC68 = 0;
    dword_18082CC6C = 0;
    qword_18082CC58 = (__int64)&FileExplorerTelemetry::`vftable';
    atexit(_lambda_6d1781482f98053d9c23f1daeac3d9b0_::_lambda_invoker_cdecl_);
    v47 = 0;
    wil::details::static_lazy<FileExplorerTelemetry>::Completer::~Completer(&v46);
  }
  v56 = 0;
  v53 = 0;
  v54 = "CAutoDestItemsFolder::_BindToTargetShellItem";
  v55 = 0;
  v57[0] = 0;
  v57[1] = Context;
  v58 = 0;
  v59 = 0;
  v60 = &v53;
  v61 = 0;
  v7 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
    v10 = 8 * v9;
    for ( i = *(_QWORD *)(8 * v9 + v7); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == CurrentThreadId )
      {
        v12 = (__int64 *)(i + 16);
        goto LABEL_10;
      }
    }
    v32 = (char *)wil::details::ProcessHeapAlloc(0, 0x18u, v9);
    v33 = (signed __int64)v32;
    if ( v32 )
    {
      *(_DWORD *)v32 = CurrentThreadId;
      *((_DWORD *)v32 + 1) = 0;
      *((_QWORD *)v32 + 1) = 0;
      v12 = (__int64 *)(v32 + 16);
      *((_QWORD *)v32 + 2) = 0;
      do
      {
        v34 = *(_QWORD *)(v10 + v7);
        *(_QWORD *)(v33 + 8) = v34;
      }
      while ( v34 != _InterlockedCompareExchange64((volatile signed __int64 *)(v10 + v7), v33, v34) );
    }
    else
    {
      v12 = 0;
    }
LABEL_10:
    v57[0] = v12;
    if ( v12 )
    {
      v58 = *v12;
      *v12 = (__int64)v57;
      v59 = GetCurrentThreadId();
    }
  }
  pv = 0;
  Context = 0;
  fPending[0] = 0;
  if ( InitOnceBeginInitialize(&`FavoritesTelemetry::Instance'::`2'::wrapper, 0, fPending, &Context) && fPending[0] )
  {
    v46 = &`FavoritesTelemetry::Instance'::`2'::wrapper;
    Context = &qword_18082CC58;
    qword_18082CC60 = 0;
    byte_18082CC68 = 0;
    dword_18082CC6C = 0;
    qword_18082CC58 = (__int64)&FileExplorerTelemetry::`vftable';
    atexit(_lambda_6d1781482f98053d9c23f1daeac3d9b0_::_lambda_invoker_cdecl_);
    v47 = 0;
    wil::details::static_lazy<FileExplorerTelemetry>::Completer::~Completer(&v46);
  }
  v65 = 0;
  v62 = 0;
  v63 = "CAutoDestItemsFolder::_GetTargetAbsolutePIDL";
  lpMem = 0;
  v66[0] = 0;
  v66[1] = Context;
  v67 = 0;
  v68 = 0;
  v69 = &v62;
  v70 = 0;
  v13 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    v14 = GetCurrentThreadId();
    v15 = (v14 >> 2) % 0xA;
    v16 = 8 * v15;
    for ( j = *(_QWORD *)(v13 + 8 * v15); j; j = *(_QWORD *)(j + 8) )
    {
      if ( *(_DWORD *)j == (_DWORD)v14 )
      {
        v18 = (__int64 *)(j + 16);
        goto LABEL_21;
      }
    }
    v35 = (char *)wil::details::ProcessHeapAlloc(0, 0x18u, v15);
    v36 = (signed __int64)v35;
    if ( v35 )
    {
      *(_DWORD *)v35 = v14;
      *((_DWORD *)v35 + 1) = 0;
      *((_QWORD *)v35 + 1) = 0;
      v18 = (__int64 *)(v35 + 16);
      *((_QWORD *)v35 + 2) = 0;
      do
      {
        v37 = *(_QWORD *)(v16 + v13);
        *(_QWORD *)(v36 + 8) = v37;
      }
      while ( v37 != _InterlockedCompareExchange64((volatile signed __int64 *)(v13 + v16), v36, v37) );
    }
    else
    {
      v18 = 0;
    }
LABEL_21:
    v66[0] = v18;
    if ( v18 )
    {
      v67 = *v18;
      *v18 = (__int64)v66;
      v68 = GetCurrentThreadId();
    }
  }
  *(_OWORD *)pvar = 0;
  v52 = 0;
  v19 = -2147024809;
  if ( !a2 )
    goto LABEL_27;
  v20 = *(unsigned __int16 *)a2;
  if ( (unsigned int)v20 < 0xF )
    goto LABEL_27;
  if ( *(_DWORD *)((char *)a2 + 6) != 203342025 )
    goto LABEL_27;
  v21 = *((unsigned __int16 *)a2 + 5);
  if ( v20 < v21 + 15 )
    goto LABEL_27;
  if ( !(_WORD)v21 )
    goto LABEL_27;
  if ( a2 == (const struct _ITEMIDLIST_RELATIVE *)-15LL )
    goto LABEL_27;
  v19 = PSGetPropertyFromPropertyStorage(
          (const struct _ITEMIDLIST_RELATIVE *)((char *)a2 + 15),
          v21,
          &PKEY_DelegateIDList,
          pvar);
  if ( (v19 & 0x80000000) != 0 )
    goto LABEL_27;
  if ( !LOWORD(pvar[0]) )
  {
    v19 = -2147023288;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8DB,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
      (const char *)v19,
      (int)v46);
    PropVariantClear(pvar);
    if ( v68 )
      wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v66);
    if ( v65 )
    {
      v40 = lpMem;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v40);
    }
    goto LABEL_31;
  }
  v24 = PropVariantToIDList(pvar, &pv);
  v19 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8DC,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
      (const char *)(unsigned int)v24,
      (int)v46);
    PropVariantClear(pvar);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)&v62);
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E9,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
      (const char *)v19,
      (int)v46);
    v22 = pv;
    pv = 0;
    CoTaskMemFree(v22);
    if ( v59 )
      wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v57);
    wil::details::StoredCallContextInfo::ClearMessage((wil::details::StoredCallContextInfo *)&v53);
    return v19;
  }
  PropVariantClear(pvar);
  if ( v68 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v66);
  if ( v65 )
  {
    v38 = lpMem;
    v39 = GetProcessHeap();
    HeapFree(v39, 0, v38);
  }
  v25 = pv;
  *a4 = 0;
  *(_QWORD *)fPending = 0;
  inited = -2147024882;
  v27 = (CMarshalByValue *)operator new(0xD8u, (const struct std::nothrow_t *)&std::nothrow);
  v28 = v27;
  if ( !v27 )
    goto LABEL_55;
  CMarshalByValue::CMarshalByValue(v27);
  *(_DWORD *)(v29 + 120) = -2;
  *(_DWORD *)(v29 + 124) = 1;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v29 + 80));
  *(_QWORD *)v28 = &CShellItem::`vftable'{for `CMarshalByValue'};
  *((_QWORD *)v28 + 1) = &CShellItem::`vftable'{for `IShellItem2'};
  *((_QWORD *)v28 + 2) = &CShellItem::`vftable'{for `IShellItemImageFactoryPriv'};
  *((_QWORD *)v28 + 3) = &CShellItem::`vftable'{for `IPersistIDList'};
  *((_QWORD *)v28 + 4) = &CShellItem::`vftable'{for `IParentAndItem'};
  *((_QWORD *)v28 + 5) = &CShellItem::`vftable'{for `IPersistStream'};
  *((_QWORD *)v28 + 6) = &CShellItem::`vftable'{for `ICacheableObject'};
  *((_QWORD *)v28 + 7) = &CShellItem::`vftable'{for `IChildId'};
  *((_QWORD *)v28 + 8) = &CShellItem::`vftable'{for `IObjectWithBackReferences'};
  *((_QWORD *)v28 + 9) = &CShellItem::`vftable'{for `IInitializeWithFolder'};
  *((_DWORD *)v28 + 32) = 1;
  *((_QWORD *)v28 + 17) = 0;
  *((_QWORD *)v28 + 18) = 0;
  *((_QWORD *)v28 + 19) = 0;
  *((_QWORD *)v28 + 20) = 0;
  *((_QWORD *)v28 + 21) = 0;
  *((_QWORD *)v28 + 22) = 0;
  *((_QWORD *)v28 + 23) = 0;
  *((_QWORD *)v28 + 24) = 0;
  *((_QWORD *)v28 + 25) = 0;
  *((_DWORD *)v28 + 52) = 0;
  inited = CObjectWithThreadUseDetection::InitApartmentId((CMarshalByValue *)((char *)v28 + 80));
  if ( inited >= 0 )
    inited = (**(__int64 (__fastcall ***)(CMarshalByValue *, GUID *, WINBOOL *))v28)(
               v28,
               &GUID_1079acfc_29bd_11d3_8e0d_00c04f6837d5,
               fPending);
  (*(void (__fastcall **)(CMarshalByValue *))(*(_QWORD *)v28 + 16LL))(v28);
  if ( inited < 0 )
    goto LABEL_55;
  inited = (*(__int64 (__fastcall **)(_QWORD, LPVOID))(**(_QWORD **)fPending + 32LL))(*(_QWORD *)fPending, v25);
  if ( inited >= 0 )
    inited = (***(__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))fPending)(
               *(_QWORD *)fPending,
               a3,
               a4);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)fPending + 16LL))(*(_QWORD *)fPending);
  if ( inited >= 0 )
  {
    v30 = pv;
    pv = 0;
    CoTaskMemFree(v30);
    if ( v59 )
      wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v57);
    if ( v56 )
    {
      v42 = v55;
      v43 = GetProcessHeap();
      HeapFree(v43, 0, v42);
    }
    return 0;
  }
  else
  {
LABEL_55:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8EA,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
      (const char *)(unsigned int)inited,
      (int)v46);
    v31 = pv;
    pv = 0;
    CoTaskMemFree(v31);
    if ( v59 )
      wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v57);
    if ( v56 )
    {
      v44 = v55;
      v45 = GetProcessHeap();
      HeapFree(v45, 0, v44);
    }
    return (unsigned int)inited;
  }
}

```

## disassembly

```asm
0x18003c550  mov     [rsp-8+arg_0], rbx
0x18003c555  push    rbp
0x18003c556  push    rsi
0x18003c557  push    rdi
0x18003c558  push    r12
0x18003c55a  push    r13
0x18003c55c  push    r14
0x18003c55e  push    r15
0x18003c560  lea     rbp, [rsp-10h]
0x18003c565  sub     rsp, 110h
0x18003c56c  mov     rax, cs:__security_cookie
0x18003c573  xor     rax, rsp
0x18003c576  mov     [rbp+40h+var_40], rax
0x18003c57a  mov     r15, r9
0x18003c57d  mov     r12, r8
0x18003c580  mov     r14, rdx
0x18003c583  xor     r13d, r13d
0x18003c586  mov     [r9], r13
0x18003c589  mov     [rsp+140h+Context], r13
0x18003c58e  mov     [rsp+140h+fPending], r13d
0x18003c593  lea     r9, [rsp+140h+Context]; lpContext
0x18003c598  lea     r8, [rsp+140h+fPending]; fPending
0x18003c59d  xor     edx, edx; dwFlags
0x18003c59f  lea     rdi, ?wrapper@?1??Instance@FavoritesTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VFavoritesTelemetry@@@details@wil@@A; wil::details::static_lazy<FavoritesTelemetry> `FavoritesTelemetry::Instance(void)'::`2'::wrapper
0x18003c5a6  mov     rcx, rdi; lpInitOnce
0x18003c5a9  call    cs:__imp_InitOnceBeginInitialize
0x18003c5b0  nop     dword ptr [rax+rax+00h]
0x18003c5b5  lea     rcx, qword_18082CC58
0x18003c5bc  lea     rdx, ??_7FileExplorerTelemetry@@6B@; const FileExplorerTelemetry::`vftable'
0x18003c5c3  test    eax, eax
0x18003c5c5  jz      short loc_18003C5D2
0x18003c5c7  cmp     [rsp+140h+fPending], r13d
0x18003c5cc  jnz     loc_18003CBCD
0x18003c5d2  mov     rax, [rsp+140h+Context]
0x18003c5d7  mov     [rsp+140h+var_C8], r13b
0x18003c5dc  mov     [rsp+140h+var_E0], r13d
0x18003c5e1  lea     rcx, aCautodestitems_1; "CAutoDestItemsFolder::_BindToTargetShel"...
0x18003c5e8  mov     [rsp+140h+var_D8], rcx
0x18003c5ed  mov     [rsp+140h+var_D0], r13
0x18003c5f2  mov     [rbp+40h+var_C0], r13
0x18003c5f6  mov     [rbp+40h+var_B8], rax
0x18003c5fa  mov     [rbp+40h+var_B0], r13
0x18003c5fe  mov     [rbp+40h+var_A8], r13d
0x18003c602  lea     rax, [rsp+140h+var_E0]
0x18003c607  mov     [rbp+40h+var_A0], rax
0x18003c60b  mov     [rbp+40h+var_98], 0
0x18003c60f  mov     rsi, 0CCCCCCCCCCCCCCCDh
0x18003c619  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18003c620  test    rdi, rdi
0x18003c623  jz      loc_18003C6A7
0x18003c629  call    cs:__imp_GetCurrentThreadId
0x18003c630  nop     dword ptr [rax+rax+00h]
0x18003c635  mov     ebx, eax
0x18003c637  mov     r8d, eax
0x18003c63a  shr     r8, 2
0x18003c63e  mov     rax, rsi
0x18003c641  mul     r8
0x18003c644  shr     rdx, 3
0x18003c648  lea     rcx, [rdx+rdx*4]
0x18003c64c  add     rcx, rcx
0x18003c64f  sub     r8, rcx; unsigned __int64
0x18003c652  lea     rsi, ds:0[r8*8]
0x18003c65a  mov     rax, [rsi+rdi]
0x18003c65e  xchg    ax, ax
0x18003c660  test    rax, rax
0x18003c663  jz      loc_18003CB45
0x18003c669  cmp     [rax], ebx
0x18003c66b  jz      short loc_18003C673
0x18003c66d  mov     rax, [rax+8]
0x18003c671  jmp     short loc_18003C660
0x18003c673  lea     rcx, [rax+10h]
0x18003c677  mov     [rbp+40h+var_C0], rcx
0x18003c67b  test    rcx, rcx
0x18003c67e  jz      short loc_18003C69D
0x18003c680  mov     rax, [rcx]
0x18003c683  mov     [rbp+40h+var_B0], rax
0x18003c687  lea     rax, [rbp+40h+var_C0]
0x18003c68b  mov     [rcx], rax
0x18003c68e  call    cs:__imp_GetCurrentThreadId
0x18003c695  nop     dword ptr [rax+rax+00h]
0x18003c69a  mov     [rbp+40h+var_A8], eax
0x18003c69d  mov     rsi, 0CCCCCCCCCCCCCCCDh
0x18003c6a7  mov     [rsp+140h+pv], r13
0x18003c6ac  mov     [rsp+140h+Context], r13
0x18003c6b1  mov     [rsp+140h+fPending], r13d
0x18003c6b6  lea     r9, [rsp+140h+Context]; lpContext
0x18003c6bb  lea     r8, [rsp+140h+fPending]; fPending
0x18003c6c0  xor     edx, edx; dwFlags
0x18003c6c2  lea     rbx, ?wrapper@?1??Instance@FavoritesTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VFavoritesTelemetry@@@details@wil@@A; wil::details::static_lazy<FavoritesTelemetry> `FavoritesTelemetry::Instance(void)'::`2'::wrapper
0x18003c6c9  mov     rcx, rbx; lpInitOnce
0x18003c6cc  call    cs:__imp_InitOnceBeginInitialize
0x18003c6d3  nop     dword ptr [rax+rax+00h]
0x18003c6d8  test    eax, eax
0x18003c6da  jz      short loc_18003C6E7
0x18003c6dc  cmp     [rsp+140h+fPending], 0
0x18003c6e1  jnz     loc_1806604EE
0x18003c6e7  mov     rax, [rsp+140h+Context]
0x18003c6ec  mov     [rbp+40h+var_78], 0
0x18003c6f0  mov     [rbp+40h+var_90], r13d
0x18003c6f4  lea     rcx, aCautodestitems_4; "CAutoDestItemsFolder::_GetTargetAbsolut"...
0x18003c6fb  mov     [rbp+40h+var_88], rcx
0x18003c6ff  mov     [rbp+40h+lpMem], r13
0x18003c703  mov     [rbp+40h+var_70], r13
0x18003c707  mov     [rbp+40h+var_68], rax
0x18003c70b  mov     [rbp+40h+var_60], r13
0x18003c70f  mov     [rbp+40h+var_58], r13d
0x18003c713  lea     rcx, [rbp+40h+var_90]
0x18003c717  mov     [rbp+40h+var_50], rcx
0x18003c71b  mov     [rbp+40h+var_48], 0
0x18003c71f  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18003c726  test    rdi, rdi
0x18003c729  jz      short loc_18003C79D
0x18003c72b  call    cs:__imp_GetCurrentThreadId
0x18003c732  nop     dword ptr [rax+rax+00h]
0x18003c737  mov     ebx, eax
0x18003c739  mov     r8d, eax
0x18003c73c  shr     r8, 2
0x18003c740  mov     rax, rsi
0x18003c743  mul     r8
0x18003c746  shr     rdx, 3
0x18003c74a  lea     rcx, [rdx+rdx*4]
0x18003c74e  add     rcx, rcx
0x18003c751  sub     r8, rcx; unsigned __int64
0x18003c754  lea     rsi, ds:0[r8*8]
0x18003c75c  mov     rax, [rdi+rsi]
0x18003c760  test    rax, rax
0x18003c763  jz      loc_18003CB81
0x18003c769  cmp     [rax], ebx
0x18003c76b  jz      short loc_18003C773
0x18003c76d  mov     rax, [rax+8]
0x18003c771  jmp     short loc_18003C760
0x18003c773  lea     rcx, [rax+10h]
0x18003c777  mov     [rbp+40h+var_70], rcx
0x18003c77b  test    rcx, rcx
0x18003c77e  jz      short loc_18003C79D
0x18003c780  mov     rax, [rcx]
0x18003c783  mov     [rbp+40h+var_60], rax
0x18003c787  lea     rax, [rbp+40h+var_70]
0x18003c78b  mov     [rcx], rax
0x18003c78e  call    cs:__imp_GetCurrentThreadId
0x18003c795  nop     dword ptr [rax+rax+00h]
0x18003c79a  mov     [rbp+40h+var_58], eax
0x18003c79d  xorps   xmm0, xmm0
0x18003c7a0  xor     eax, eax
0x18003c7a2  movups  xmmword ptr [rsp+140h+pvar], xmm0
0x18003c7a7  mov     [rsp+140h+var_E8], rax
0x18003c7ac  mov     edi, 80070057h
0x18003c7b1  test    r14, r14
0x18003c7b4  jz      short loc_18003C7DB
0x18003c7b6  movzx   eax, word ptr [r14]
0x18003c7ba  cmp     eax, 0Fh
0x18003c7bd  jb      short loc_18003C7DB
0x18003c7bf  cmp     dword ptr [r14+6], 0C1EC0C9h
0x18003c7c7  jnz     short loc_18003C7DB
0x18003c7c9  movzx   edx, word ptr [r14+0Ah]; cb
0x18003c7ce  lea     rcx, [rdx+0Fh]
0x18003c7d2  cmp     rax, rcx
0x18003c7d5  jnb     loc_18003C877
0x18003c7db  mov     rcx, [rbp+48h]; this
0x18003c7df  mov     r9d, edi; char *
0x18003c7e2  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\windows.storage\\fre"...
0x18003c7e9  mov     edx, 8DBh; void *
0x18003c7ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c7f3  lea     rcx, [rsp+140h+pvar]; pvar
0x18003c7f8  call    cs:__imp_PropVariantClear
0x18003c7ff  nop     dword ptr [rax+rax+00h]
0x18003c804  nop
0x18003c805  cmp     [rbp+40h+var_58], 0
0x18003c809  jz      short loc_18003C815
0x18003c80b  lea     rcx, [rbp+40h+var_70]; this
0x18003c80f  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18003c814  nop
0x18003c815  cmp     [rbp+40h+var_78], 0
0x18003c819  jnz     loc_18003CC7D
0x18003c81f  test    edi, edi
0x18003c821  jns     loc_18003C900
0x18003c827  mov     rcx, [rbp+48h]; this
0x18003c82b  mov     r9d, edi; char *
0x18003c82e  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\windows.storage\\fre"...
0x18003c835  mov     edx, 8E9h; void *
0x18003c83a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c83f  mov     rcx, [rsp+140h+pv]; pv
0x18003c844  mov     [rsp+140h+pv], r13
0x18003c849  call    cs:__imp_CoTaskMemFree
0x18003c850  nop     dword ptr [rax+rax+00h]
0x18003c855  nop
0x18003c856  cmp     [rbp+40h+var_A8], 0
0x18003c85a  jz      short loc_18003C866
0x18003c85c  lea     rcx, [rbp+40h+var_C0]; this
0x18003c860  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18003c865  nop
0x18003c866  lea     rcx, [rsp+140h+var_E0]; this
0x18003c86b  call    ?ClearMessage@StoredCallContextInfo@details@wil@@QEAAXXZ; wil::details::StoredCallContextInfo::ClearMessage(void)
0x18003c870  mov     eax, edi
0x18003c872  jmp     loc_18003CACF
0x18003c877  test    dx, dx
0x18003c87a  jz      loc_18003C7DB
0x18003c880  lea     rcx, [r14+0Fh]; psps
0x18003c884  test    rcx, rcx
0x18003c887  jz      loc_18003C7DB
0x18003c88d  lea     r9, [rsp+140h+pvar]; ppropvar
0x18003c892  lea     r8, PKEY_DelegateIDList; rpkey
0x18003c899  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x18003c8a0  nop     dword ptr [rax+rax+00h]
0x18003c8a5  mov     edi, eax
0x18003c8a7  test    eax, eax
0x18003c8a9  js      loc_18003C7DB
0x18003c8af  cmp     word ptr [rsp+140h+pvar], 0
0x18003c8b5  jz      loc_18003CC13
0x18003c8bb  lea     rdx, [rsp+140h+pv]
0x18003c8c0  lea     rcx, [rsp+140h+pvar]
0x18003c8c5  call    PropVariantToIDList
0x18003c8ca  mov     edi, eax
0x18003c8cc  test    eax, eax
0x18003c8ce  js      loc_18003CC1D
0x18003c8d4  lea     rcx, [rsp+140h+pvar]; pvar
0x18003c8d9  call    cs:__imp_PropVariantClear
0x18003c8e0  nop     dword ptr [rax+rax+00h]
0x18003c8e5  nop
0x18003c8e6  cmp     [rbp+40h+var_58], 0
0x18003c8ea  jz      short loc_18003C8F6
0x18003c8ec  lea     rcx, [rbp+40h+var_70]; this
0x18003c8f0  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18003c8f5  nop
0x18003c8f6  cmp     [rbp+40h+var_78], 0
0x18003c8fa  jnz     loc_18003CC54
0x18003c900  mov     r14, [rsp+140h+pv]
0x18003c905  mov     [r15], r13
0x18003c908  mov     qword ptr [rsp+140h+fPending], r13
0x18003c90d  mov     esi, 8007000Eh
0x18003c912  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003c919  mov     ecx, 0D8h; unsigned __int64
0x18003c91e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003c923  mov     rdi, rax
0x18003c926  test    rax, rax
0x18003c929  jz      loc_18003CAF7
0x18003c92f  mov     rcx, rax; this
0x18003c932  call    ??0CMarshalByValue@@QEAA@XZ; CMarshalByValue::CMarshalByValue(void)
0x18003c937  mov     dword ptr [rcx+78h], 0FFFFFFFEh
0x18003c93e  mov     dword ptr [rcx+7Ch], 1
0x18003c945  lea     rcx, [rcx+50h]; lpCriticalSection
0x18003c949  call    cs:__imp_InitializeCriticalSection
0x18003c950  nop     dword ptr [rax+rax+00h]
0x18003c955  lea     rax, ??_7CShellItem@@6BCMarshalByValue@@@; const CShellItem::`vftable'{for `CMarshalByValue'}
0x18003c95c  mov     [rdi], rax
0x18003c95f  lea     rax, ??_7CShellItem@@6BIShellItem2@@@; const CShellItem::`vftable'{for `IShellItem2'}
0x18003c966  mov     [rdi+8], rax
0x18003c96a  lea     rax, ??_7CShellItem@@6BIShellItemImageFactoryPriv@@@; const CShellItem::`vftable'{for `IShellItemImageFactoryPriv'}
0x18003c971  mov     [rdi+10h], rax
0x18003c975  lea     rax, ??_7CShellItem@@6BIPersistIDList@@@; const CShellItem::`vftable'{for `IPersistIDList'}
0x18003c97c  mov     [rdi+18h], rax
0x18003c980  lea     rax, ??_7CShellItem@@6BIParentAndItem@@@; const CShellItem::`vftable'{for `IParentAndItem'}
0x18003c987  mov     [rdi+20h], rax
0x18003c98b  lea     rax, ??_7CShellItem@@6BIPersistStream@@@; const CShellItem::`vftable'{for `IPersistStream'}
0x18003c992  mov     [rdi+28h], rax
0x18003c996  lea     rax, ??_7CShellItem@@6BICacheableObject@@@; const CShellItem::`vftable'{for `ICacheableObject'}
0x18003c99d  mov     [rdi+30h], rax
0x18003c9a1  lea     rax, ??_7CShellItem@@6BIChildId@@@; const CShellItem::`vftable'{for `IChildId'}
0x18003c9a8  mov     [rdi+38h], rax
0x18003c9ac  lea     rax, ??_7CShellItem@@6BIObjectWithBackReferences@@@; const CShellItem::`vftable'{for `IObjectWithBackReferences'}
0x18003c9b3  mov     [rdi+40h], rax
0x18003c9b7  lea     rax, ??_7CShellItem@@6BIInitializeWithFolder@@@; const CShellItem::`vftable'{for `IInitializeWithFolder'}
0x18003c9be  mov     [rdi+48h], rax
0x18003c9c2  mov     dword ptr [rdi+80h], 1
0x18003c9cc  mov     [rdi+88h], r13
0x18003c9d3  mov     [rdi+90h], r13
0x18003c9da  mov     [rdi+98h], r13
0x18003c9e1  mov     [rdi+0A0h], r13
0x18003c9e8  mov     [rdi+0A8h], r13
0x18003c9ef  mov     [rdi+0B0h], r13
0x18003c9f6  mov     [rdi+0B8h], r13
0x18003c9fd  mov     [rdi+0C0h], r13
0x18003ca04  mov     [rdi+0C8h], r13
0x18003ca0b  mov     [rdi+0D0h], r13d
0x18003ca12  lea     rcx, [rdi+50h]; this
0x18003ca16  call    ?InitApartmentId@CObjectWithThreadUseDetection@@QEAAJXZ; CObjectWithThreadUseDetection::InitApartmentId(void)
0x18003ca1b  mov     esi, eax
0x18003ca1d  test    eax, eax
0x18003ca1f  js      short loc_18003CA3D
0x18003ca21  mov     rax, [rdi]
0x18003ca24  lea     r8, [rsp+140h+fPending]
0x18003ca29  lea     rdx, _GUID_1079acfc_29bd_11d3_8e0d_00c04f6837d5
0x18003ca30  mov     rcx, rdi
0x18003ca33  mov     rax, [rax]
0x18003ca36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca3b  mov     esi, eax
0x18003ca3d  mov     rax, [rdi]
0x18003ca40  mov     rcx, rdi
0x18003ca43  mov     rax, [rax+10h]
0x18003ca47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca4c  test    esi, esi
0x18003ca4e  js      loc_18003CAF7
0x18003ca54  mov     rcx, qword ptr [rsp+140h+fPending]
0x18003ca59  mov     rax, [rcx]
0x18003ca5c  mov     rdx, r14
0x18003ca5f  mov     rax, [rax+20h]
0x18003ca63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca68  mov     esi, eax
0x18003ca6a  test    eax, eax
0x18003ca6c  js      short loc_18003CA86
  ... truncated ...
```
