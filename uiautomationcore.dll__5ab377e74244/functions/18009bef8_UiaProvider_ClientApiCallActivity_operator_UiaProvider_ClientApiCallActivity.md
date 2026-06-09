# UiaProvider::ClientApiCallActivity::operator=(UiaProvider::ClientApiCallActivity &&)

- ea: `0x18009bef8`
- end: `0x18009c7f7`
- name: `??4ClientApiCallActivity@UiaProvider@@QEAAAEAV01@$$QEAV01@@Z`
- size: `2303`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b0b00`

## callees

- `0x180047b70`
- `0x18009aa78`
- `0x18009bef8`
- `0x18009d174`
- `0x18009d23c`
- `0x18009de10`
- `0x1800b1120`
- `0x1800deac4`
- `0x1800fbdf4`
- `0x18011f848`
- `0x1801e8320`
- `0x1801e8344`
- `0x1801e9258`
- `0x1801f1b68`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009bf9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009c1ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009c4ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009c56e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009c5a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009bf9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009c1ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009c4ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009c56e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009c5a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009bfaa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009c1fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009c4f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009c57c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009c5b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009bfaa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009c1fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009c4f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009c57c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009c5b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c0eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c14d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c35c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c3b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c3de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c478`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c0eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c14d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c35c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c3b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c3de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c478`

## string_xrefs

- `0x18009c748`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`
- `0x18009c7d5`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UiaProvider::ClientApiCallActivity::operator=(__int64 a1, __int64 a2)
{
  wil::details::ThreadFailureCallbackHolder *v4; // r14
  int v5; // ebx
  __int64 v6; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v8; // r14
  DWORD CurrentThreadId; // r15d
  unsigned __int64 v10; // rbx
  __int64 i; // rcx
  _QWORD *v12; // rcx
  int *v13; // rax
  void *v14; // rbx
  HANDLE v15; // rax
  volatile signed __int32 **v16; // r12
  volatile signed __int32 **v17; // r14
  volatile signed __int32 **v18; // r12
  volatile signed __int32 **v19; // rbx
  __int64 v20; // rax
  _QWORD *v21; // rbx
  __int64 v22; // r14
  DWORD v23; // r12d
  unsigned __int64 v24; // rdi
  __int64 j; // rcx
  _QWORD *v26; // rcx
  __int64 **v27; // rbx
  __int64 v28; // rax
  int *v29; // rcx
  int v30; // eax
  __int64 v31; // rdx
  _QWORD **v32; // rcx
  _QWORD *v33; // rax
  void *v34; // rbx
  HANDLE v35; // rax
  volatile signed __int32 *v37; // rbx
  HANDLE v38; // rax
  void *v39; // rbx
  HANDLE v40; // rax
  const struct _tlgProvider_t *v41; // rax
  char *v42; // rax
  signed __int64 v43; // rdx
  signed __int64 v44; // rax
  char *v45; // rax
  signed __int64 v46; // rdx
  signed __int64 v47; // rax
  volatile signed __int32 *v48; // r14
  void *v49; // rbx
  char v50; // bl
  const struct wil::FailureInfo *v51; // rdx
  _BYTE v52[16]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v53[160]; // [rsp+30h] [rbp-D0h] BYREF
  void **v54; // [rsp+D0h] [rbp-30h] BYREF
  int v55; // [rsp+D8h] [rbp-28h] BYREF
  char v56; // [rsp+DCh] [rbp-24h]
  _QWORD v57[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v58; // [rsp+F0h] [rbp-10h]
  __int128 v59; // [rsp+100h] [rbp+0h]
  LPVOID lpMem[2]; // [rsp+110h] [rbp+10h]
  int v61; // [rsp+120h] [rbp+20h]
  __int128 v62; // [rsp+128h] [rbp+28h]
  __int128 v63; // [rsp+138h] [rbp+38h]
  __int128 v64; // [rsp+148h] [rbp+48h]
  __int128 v65; // [rsp+158h] [rbp+58h]
  __int128 v66; // [rsp+168h] [rbp+68h]
  __int128 v67; // [rsp+178h] [rbp+78h]
  __int128 v68; // [rsp+188h] [rbp+88h]
  __int128 v69; // [rsp+198h] [rbp+98h]
  __int128 v70; // [rsp+1A8h] [rbp+A8h]
  __int64 v71; // [rsp+1B8h] [rbp+B8h]
  LPVOID v72[2]; // [rsp+1C0h] [rbp+C0h]
  int v73; // [rsp+1D0h] [rbp+D0h]
  __int64 v74; // [rsp+1D8h] [rbp+D8h]
  int *v75; // [rsp+1E0h] [rbp+E0h]
  void *Block; // [rsp+1E8h] [rbp+E8h] BYREF
  _QWORD v77[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  _QWORD *v78; // [rsp+200h] [rbp+100h]
  DWORD v79; // [rsp+208h] [rbp+108h]
  int *v80; // [rsp+210h] [rbp+110h]
  char v81; // [rsp+218h] [rbp+118h]
  void *retaddr; // [rsp+268h] [rbp+168h]

  v4 = (wil::details::ThreadFailureCallbackHolder *)(a1 + 288);
  v5 = *(_DWORD *)(a1 + 312);
  v54 = &wil::ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable';
  v6 = a1 + 8;
  v55 = *(_DWORD *)(a1 + 8);
  v56 = *(_BYTE *)(a1 + 12);
  v57[0] = *(_QWORD *)(a1 + 16);
  v57[1] = *(_QWORD *)(a1 + 24);
  v58 = *(_OWORD *)(a1 + 32);
  *(_DWORD *)(a1 + 8) = 0;
  *(_BYTE *)(a1 + 12) = 0;
  v59 = 0;
  *(_OWORD *)lpMem = 0;
  LODWORD(v59) = *(_DWORD *)(a1 + 48);
  *((_QWORD *)&v59 + 1) = *(_QWORD *)(a1 + 56);
  if ( (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8)) )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, 0);
  }
  lpMem[0] = *(LPVOID *)(v6 + 56);
  *(_QWORD *)(v6 + 56) = 0;
  LOBYTE(lpMem[1]) = *(_BYTE *)(v6 + 64);
  *(_BYTE *)(v6 + 64) = 0;
  v61 = *(_DWORD *)(a1 + 80);
  v62 = *(_OWORD *)(a1 + 88);
  v63 = *(_OWORD *)(a1 + 104);
  v64 = *(_OWORD *)(a1 + 120);
  v65 = *(_OWORD *)(a1 + 136);
  v66 = *(_OWORD *)(a1 + 152);
  v67 = *(_OWORD *)(a1 + 168);
  v68 = *(_OWORD *)(a1 + 184);
  v69 = *(_OWORD *)(a1 + 200);
  v70 = *(_OWORD *)(a1 + 216);
  v71 = *(_QWORD *)(a1 + 232);
  v72[0] = *(LPVOID *)(a1 + 240);
  v72[1] = *(LPVOID *)(a1 + 248);
  *(_QWORD *)(a1 + 240) = 0;
  *(_QWORD *)(a1 + 248) = 0;
  v73 = *(_DWORD *)(a1 + 256);
  v74 = 0;
  Block = *(void **)(a1 + 280);
  *(_QWORD *)(a1 + 280) = 0;
  v77[0] = 0;
  v77[1] = &v54;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  if ( v5 )
  {
    v8 = wil::details::g_pThreadFailureCallbacks;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
      for ( i = *(_QWORD *)(v8 + 8 * v10); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          v12 = (_QWORD *)(i + 16);
          goto LABEL_10;
        }
      }
      v42 = (char *)wil::details::ProcessHeapAlloc(0, 0x18u, 0);
      v43 = (signed __int64)v42;
      if ( v42 )
      {
        *(_DWORD *)v42 = CurrentThreadId;
        *((_DWORD *)v42 + 1) = 0;
        *((_QWORD *)v42 + 1) = 0;
        v12 = v42 + 16;
        *((_QWORD *)v42 + 2) = 0;
        do
        {
          v44 = *(_QWORD *)(v8 + 8 * v10);
          *(_QWORD *)(v43 + 8) = v44;
        }
        while ( v44 != _InterlockedCompareExchange64((volatile signed __int64 *)(v8 + 8 * v10), v43, v44) );
      }
      else
      {
        v12 = 0;
      }
LABEL_10:
      v77[0] = v12;
      if ( v12 )
      {
        v78 = (_QWORD *)*v12;
        *v12 = v77;
        v79 = GetCurrentThreadId();
      }
    }
    v4 = (wil::details::ThreadFailureCallbackHolder *)(a1 + 288);
  }
  if ( Block )
    v13 = (int *)(((unsigned __int64)Block + 8) & -(__int64)(Block != 0));
  else
    v13 = &v55;
  v75 = v13;
  v80 = v13 + 10;
  *(_QWORD *)(a1 + 272) = v6;
  if ( *(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StopWatching(v4);
  v54 = &UiaProvider::ClientApiCallActivity::`vftable';
  *(_DWORD *)v6 = *(_DWORD *)(a2 + 8);
  *(_BYTE *)(v6 + 4) = *(_BYTE *)(a2 + 12);
  *(_OWORD *)(v6 + 8) = *(_OWORD *)(a2 + 16);
  *(_OWORD *)(v6 + 24) = *(_OWORD *)(a2 + 32);
  *(_DWORD *)(a2 + 8) = 0;
  *(_BYTE *)(a2 + 12) = 0;
  *(_DWORD *)(v6 + 40) = *(_DWORD *)(a2 + 48);
  *(_QWORD *)(v6 + 48) = *(_QWORD *)(a2 + 56);
  if ( *(_BYTE *)(v6 + 64) )
  {
    v14 = *(void **)(v6 + 56);
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v14);
    *(_BYTE *)(v6 + 64) = 0;
  }
  *(_QWORD *)(v6 + 56) = 0;
  *(_QWORD *)(v6 + 56) = *(_QWORD *)(a2 + 64);
  *(_QWORD *)(a2 + 64) = 0;
  *(_BYTE *)(v6 + 64) = *(_BYTE *)(a2 + 72);
  *(_BYTE *)(a2 + 72) = 0;
  *(_DWORD *)(v6 + 72) = *(_DWORD *)(a2 + 80);
  *(_OWORD *)(v6 + 80) = *(_OWORD *)(a2 + 88);
  *(_OWORD *)(v6 + 96) = *(_OWORD *)(a2 + 104);
  *(_OWORD *)(v6 + 112) = *(_OWORD *)(a2 + 120);
  *(_OWORD *)(v6 + 128) = *(_OWORD *)(a2 + 136);
  *(_OWORD *)(v6 + 144) = *(_OWORD *)(a2 + 152);
  *(_OWORD *)(v6 + 160) = *(_OWORD *)(a2 + 168);
  *(_OWORD *)(v6 + 176) = *(_OWORD *)(a2 + 184);
  *(_OWORD *)(v6 + 192) = *(_OWORD *)(a2 + 200);
  *(_OWORD *)(v6 + 208) = *(_OWORD *)(a2 + 216);
  *(_QWORD *)(v6 + 224) = *(_QWORD *)(a2 + 232);
  v16 = (volatile signed __int32 **)(a2 + 240);
  v17 = (volatile signed __int32 **)(v6 + 232);
  if ( v6 + 232 != a2 + 240 )
  {
    if ( *v17 )
    {
      if ( _InterlockedExchangeAdd(*v17, 0xFFFFFFFF) == 1 )
      {
        v37 = *v17;
        v38 = GetProcessHeap();
        HeapFree(v38, 0, (LPVOID)v37);
      }
      *v17 = 0;
      *(_QWORD *)(v6 + 240) = 0;
    }
    *v17 = *v16;
    *(_QWORD *)(v6 + 240) = *(_QWORD *)(a2 + 248);
    *v16 = 0;
    *(_QWORD *)(a2 + 248) = 0;
  }
  *(_DWORD *)(v6 + 248) = *(_DWORD *)(a2 + 256);
  v18 = (volatile signed __int32 **)(a2 + 280);
  v19 = (volatile signed __int32 **)(a1 + 280);
  if ( a1 + 280 != a2 + 280 )
  {
    if ( *v19 )
    {
      if ( _InterlockedExchangeAdd(*v19, 0xFFFFFFFF) == 1 )
      {
        v48 = *v19;
        if ( *v19 )
        {
          wil::ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<UiaProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<UiaProvider,_TlgReflectorTag_Param0IsProviderType>(v48 + 2);
          operator delete((void *)v48);
        }
      }
      *v19 = 0;
    }
    *v19 = *v18;
    *v18 = 0;
  }
  v20 = *(_QWORD *)(a1 + 280);
  if ( v20 )
    v6 = v20 + 8;
  *(_QWORD *)(a1 + 272) = v6;
  *(_QWORD *)(a1 + 320) = v6 + 40;
  v21 = (_QWORD *)(a1 + 288);
  if ( *(_DWORD *)(a2 + 312) )
  {
    if ( !*(_DWORD *)(a1 + 312) )
    {
      v22 = wil::details::g_pThreadFailureCallbacks;
      if ( wil::details::g_pThreadFailureCallbacks )
      {
        v23 = GetCurrentThreadId();
        v24 = ((unsigned __int64)v23 >> 2) % 0xA;
        for ( j = *(_QWORD *)(v22 + 8 * v24); j; j = *(_QWORD *)(j + 8) )
        {
          if ( *(_DWORD *)j == v23 )
          {
            v26 = (_QWORD *)(j + 16);
            goto LABEL_35;
          }
        }
        v45 = (char *)wil::details::ProcessHeapAlloc(0, 0x18u, 0);
        v46 = (signed __int64)v45;
        if ( v45 )
        {
          *(_DWORD *)v45 = v23;
          *((_DWORD *)v45 + 1) = 0;
          *((_QWORD *)v45 + 1) = 0;
          v26 = v45 + 16;
          *((_QWORD *)v45 + 2) = 0;
          do
          {
            v47 = *(_QWORD *)(v22 + 8 * v24);
            *(_QWORD *)(v46 + 8) = v47;
          }
          while ( v47 != _InterlockedCompareExchange64((volatile signed __int64 *)(v22 + 8 * v24), v46, v47) );
        }
        else
        {
          v26 = 0;
        }
LABEL_35:
        *v21 = v26;
        if ( v26 )
        {
          *(_QWORD *)(a1 + 304) = *v26;
          *v26 = v21;
          *(_DWORD *)(a1 + 312) = GetCurrentThreadId();
        }
      }
      else
      {
        *v21 = 0;
      }
    }
  }
  else if ( *(_DWORD *)(a1 + 312) )
  {
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
  }
  *(_QWORD *)(a2 + 272) = a2 + 8;
  if ( *(_DWORD *)(a2 + 312) )
  {
    v27 = (__int64 **)(a2 + 288);
    if ( *(_DWORD *)(a2 + 312) != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
    *(_DWORD *)(a2 + 312) = 0;
    while ( 1 )
    {
      v28 = **v27;
      if ( !v28 )
        break;
      if ( (__int64 **)v28 == v27 )
      {
        **v27 = *(_QWORD *)(a2 + 304);
        break;
      }
      *v27 = (__int64 *)(v28 + 16);
    }
    *v27 = 0;
  }
  v54 = &UiaProvider::ClientApiCallActivity::`vftable';
  if ( !Block )
    goto LABEL_109;
  wil::ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(&v54, v52);
  if ( Block && *(_DWORD *)Block == 1 )
  {
    v50 = 1;
  }
  else
  {
    v50 = 0;
    wil::details::shared_object<wil::ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<UiaProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(&Block);
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v52);
  if ( v50 )
  {
LABEL_109:
    v29 = v75;
    if ( *v75 == 1 )
    {
      v30 = -2147024322;
      if ( v75[22] < 0 )
        v30 = v75[22];
      v31 = (unsigned int)v75[62];
      if ( (int)v31 < 1 )
      {
        memset_0(v53, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v53, v51);
      }
      if ( v75[18] >= 0 )
        v75[18] = v30;
      v29[62] = v31 - 1;
      wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
        &v54,
        v31);
    }
  }
  if ( v79 )
  {
    if ( v79 != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
    v79 = 0;
    v32 = (_QWORD **)v77[0];
    while ( 1 )
    {
      v33 = *v32;
      if ( !*v32 )
        break;
      if ( v33 == v77 )
      {
        *v32 = v78;
        break;
      }
      v32 = (_QWORD **)(v33 + 2);
      v77[0] = v33 + 2;
    }
    v77[0] = 0;
  }
  if ( Block )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block, 0xFFFFFFFF) == 1 )
    {
      v49 = Block;
      if ( Block )
      {
        wil::ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<UiaProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<UiaProvider,_TlgReflectorTag_Param0IsProviderType>((char *)Block + 8);
        operator delete(v49);
      }
    }
    Block = 0;
  }
  if ( v72[0] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v72[0], 0xFFFFFFFF) == 1 )
    {
      v39 = v72[0];
      v40 = GetProcessHeap();
      HeapFree(v40, 0, v39);
    }
    *(_OWORD *)v72 = 0;
  }
  if ( LOBYTE(lpMem[1]) )
  {
    v34 = lpMem[0];
    v35 = GetProcessHeap();
    HeapFree(v35, 0, v34);
    LOBYTE(lpMem[1]) = 0;
  }
  lpMem[0] = 0;
  if ( v55 == 1 )
  {
    v55 = 2;
    v41 = UiaProvider::Provider();
    _tlgWriteActivityAutoStop<0,5>(v41, v57);
  }
  return a1;
}

```

## disassembly

```asm
0x18009bef8  mov     [rsp-8+arg_10], rbx
0x18009befd  push    rbp
0x18009befe  push    rsi
0x18009beff  push    rdi
0x18009bf00  push    r12
0x18009bf02  push    r13
0x18009bf04  push    r14
0x18009bf06  push    r15
0x18009bf08  lea     rbp, [rsp-130h]
0x18009bf10  sub     rsp, 230h
0x18009bf17  mov     rax, cs:__security_cookie
0x18009bf1e  xor     rax, rsp
0x18009bf21  mov     [rbp+160h+var_40], rax
0x18009bf28  mov     rsi, rdx
0x18009bf2b  mov     r13, rcx
0x18009bf2e  lea     r14, [rcx+120h]
0x18009bf35  mov     ebx, [r14+18h]
0x18009bf39  lea     rax, ??_7?$ActivityBase@VUiaProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x18009bf40  mov     [rbp+160h+var_190], rax
0x18009bf44  lea     rdi, [rcx+8]
0x18009bf48  mov     eax, [rdi]
0x18009bf4a  mov     [rbp+160h+var_188], eax
0x18009bf4d  mov     al, [rdi+4]
0x18009bf50  mov     [rbp+160h+var_184], al
0x18009bf53  mov     rax, [rdi+8]
0x18009bf57  mov     [rbp+160h+var_180], rax
0x18009bf5b  mov     rax, [rdi+10h]
0x18009bf5f  mov     [rbp+160h+var_178], rax
0x18009bf63  movups  xmm0, xmmword ptr [rdi+18h]
0x18009bf67  movdqu  [rbp+160h+var_170], xmm0
0x18009bf6c  xor     r8d, r8d
0x18009bf6f  mov     [rdi], r8d
0x18009bf72  mov     [rdi+4], r8b
0x18009bf76  xorps   xmm0, xmm0
0x18009bf79  movups  [rbp+160h+var_160], xmm0
0x18009bf7d  movaps  xmmword ptr [rbp+160h+lpMem], xmm0
0x18009bf81  mov     eax, [rdi+28h]
0x18009bf84  mov     dword ptr [rbp+160h+var_160], eax
0x18009bf87  mov     rax, [rdi+30h]
0x18009bf8b  mov     qword ptr [rbp+160h+var_160+8], rax
0x18009bf8f  psrldq  xmm0, 8
0x18009bf94  movd    eax, xmm0
0x18009bf98  test    al, al
0x18009bf9a  jz      short loc_18009BFB3
0x18009bf9c  call    cs:__imp_GetProcessHeap
0x18009bfa2  xor     r8d, r8d; lpMem
0x18009bfa5  xor     edx, edx; dwFlags
0x18009bfa7  mov     rcx, rax; hHeap
0x18009bfaa  call    cs:__imp_HeapFree
0x18009bfb0  xor     r8d, r8d
0x18009bfb3  mov     rax, [rdi+38h]
0x18009bfb7  mov     [rbp+160h+lpMem], rax
0x18009bfbb  mov     [rdi+38h], r8
0x18009bfbf  mov     al, [rdi+40h]
0x18009bfc2  mov     byte ptr [rbp+160h+lpMem+8], al
0x18009bfc5  mov     [rdi+40h], r8b
0x18009bfc9  mov     eax, [r13+50h]
0x18009bfcd  mov     [rbp+160h+var_140], eax
0x18009bfd0  movups  xmm0, xmmword ptr [r13+58h]
0x18009bfd5  movups  [rbp+160h+var_138], xmm0
0x18009bfd9  movups  xmm1, xmmword ptr [r13+68h]
0x18009bfde  movups  [rbp+160h+var_128], xmm1
0x18009bfe2  movups  xmm0, xmmword ptr [r13+78h]
0x18009bfe7  movups  [rbp+160h+var_118], xmm0
0x18009bfeb  movups  xmm1, xmmword ptr [r13+88h]
0x18009bff3  movups  [rbp+160h+var_108], xmm1
0x18009bff7  movups  xmm0, xmmword ptr [r13+98h]
0x18009bfff  movups  [rbp+160h+var_F8], xmm0
0x18009c003  movups  xmm1, xmmword ptr [r13+0A8h]
0x18009c00b  movups  [rbp+160h+var_E8], xmm1
0x18009c00f  movups  xmm0, xmmword ptr [r13+0B8h]
0x18009c017  movups  [rbp+160h+var_D8], xmm0
0x18009c01e  movups  xmm1, xmmword ptr [r13+0C8h]
0x18009c026  movups  [rbp+160h+var_C8], xmm1
0x18009c02d  movups  xmm0, xmmword ptr [r13+0D8h]
0x18009c035  movups  [rbp+160h+var_B8], xmm0
0x18009c03c  mov     rax, [r13+0E8h]
0x18009c043  mov     [rbp+160h+var_A8], rax
0x18009c04a  mov     rax, [r13+0F0h]
0x18009c051  mov     [rbp+160h+var_A0], rax
0x18009c058  mov     rax, [r13+0F8h]
0x18009c05f  mov     [rbp+160h+var_A0+8], rax
0x18009c066  mov     [r13+0F0h], r8
0x18009c06d  mov     [r13+0F8h], r8
0x18009c074  mov     eax, [r13+100h]
0x18009c07b  mov     [rbp+160h+var_90], eax
0x18009c081  xor     eax, eax
0x18009c083  mov     [rbp+160h+var_88], rax
0x18009c08a  mov     rax, [r13+118h]
0x18009c091  mov     [rbp+160h+Block], rax
0x18009c098  mov     [r13+118h], r8
0x18009c09f  mov     [rbp+160h+var_70], r8
0x18009c0a6  lea     rax, [rbp+160h+var_190]
0x18009c0aa  mov     [rbp+160h+var_68], rax
0x18009c0b1  mov     [rbp+160h+var_60], r8
0x18009c0b8  mov     [rbp+160h+var_58], r8d
0x18009c0bf  mov     [rbp+160h+var_50], r8
0x18009c0c6  mov     [rbp+160h+var_48], r8b
0x18009c0cd  mov     r12, 0CCCCCCCCCCCCCCCDh
0x18009c0d7  test    ebx, ebx
0x18009c0d9  jz      loc_18009C163
0x18009c0df  mov     r14, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18009c0e6  test    r14, r14
0x18009c0e9  jz      short loc_18009C15C
0x18009c0eb  call    cs:__imp_GetCurrentThreadId
0x18009c0f1  mov     r15d, eax
0x18009c0f4  mov     ebx, eax
0x18009c0f6  shr     rbx, 2
0x18009c0fa  mov     rax, r12
0x18009c0fd  mul     rbx
0x18009c100  shr     rdx, 3
0x18009c104  lea     rax, [rdx+rdx*4]
0x18009c108  add     rax, rax
0x18009c10b  sub     rbx, rax
0x18009c10e  mov     rcx, [r14+rbx*8]
0x18009c112  xor     r8d, r8d; unsigned __int64
0x18009c115  test    rcx, rcx
0x18009c118  jz      loc_18009C5E5
0x18009c11e  cmp     [rcx], r15d
0x18009c121  jz      short loc_18009C129
0x18009c123  mov     rcx, [rcx+8]
0x18009c127  jmp     short loc_18009C115
0x18009c129  add     rcx, 10h
0x18009c12d  mov     [rbp+160h+var_70], rcx
0x18009c134  test    rcx, rcx
0x18009c137  jz      short loc_18009C15C
0x18009c139  mov     rax, [rcx]
0x18009c13c  mov     [rbp+160h+var_60], rax
0x18009c143  lea     rax, [rbp+160h+var_70]
0x18009c14a  mov     [rcx], rax
0x18009c14d  call    cs:__imp_GetCurrentThreadId
0x18009c153  mov     [rbp+160h+var_58], eax
0x18009c159  xor     r8d, r8d
0x18009c15c  lea     r14, [r13+120h]
0x18009c163  mov     rax, [rbp+160h+Block]
0x18009c16a  test    rax, rax
0x18009c16d  jnz     loc_18009C70F
0x18009c173  lea     rax, [rbp+160h+var_188]
0x18009c177  mov     [rbp+160h+var_80], rax
0x18009c17e  add     rax, 28h ; '('
0x18009c182  mov     [rbp+160h+var_50], rax
0x18009c189  mov     [r13+110h], rdi
0x18009c190  cmp     [r13+138h], r8d
0x18009c197  jnz     loc_18009C721
0x18009c19d  lea     rax, ??_7ClientApiCallActivity@UiaProvider@@6B@; const UiaProvider::ClientApiCallActivity::`vftable'
0x18009c1a4  mov     [rbp+160h+var_190], rax
0x18009c1a8  lea     r15, [rsi+8]
0x18009c1ac  mov     eax, [r15]
0x18009c1af  mov     [rdi], eax
0x18009c1b1  mov     al, [r15+4]
0x18009c1b5  mov     [rdi+4], al
0x18009c1b8  movups  xmm0, xmmword ptr [r15+8]
0x18009c1bd  movdqu  xmmword ptr [rdi+8], xmm0
0x18009c1c2  movups  xmm1, xmmword ptr [r15+18h]
0x18009c1c7  movdqu  xmmword ptr [rdi+18h], xmm1
0x18009c1cc  mov     [r15], r8d
0x18009c1cf  mov     [r15+4], r8b
0x18009c1d3  mov     eax, [r15+28h]
0x18009c1d7  mov     [rdi+28h], eax
0x18009c1da  mov     rax, [r15+30h]
0x18009c1de  mov     [rdi+30h], rax
0x18009c1e2  cmp     [rdi+40h], r8b
0x18009c1e6  jz      short loc_18009C207
0x18009c1e8  mov     rbx, [rdi+38h]
0x18009c1ec  call    cs:__imp_GetProcessHeap
0x18009c1f2  mov     r8, rbx; lpMem
0x18009c1f5  xor     edx, edx; dwFlags
0x18009c1f7  mov     rcx, rax; hHeap
0x18009c1fa  call    cs:__imp_HeapFree
0x18009c200  xor     r8d, r8d
0x18009c203  mov     [rdi+40h], r8b
0x18009c207  mov     [rdi+38h], r8
0x18009c20b  mov     rax, [r15+38h]
0x18009c20f  mov     [rdi+38h], rax
0x18009c213  mov     [r15+38h], r8
0x18009c217  mov     al, [r15+40h]
0x18009c21b  mov     [rdi+40h], al
0x18009c21e  mov     [r15+40h], r8b
0x18009c222  mov     eax, [rsi+50h]
0x18009c225  mov     [rdi+48h], eax
0x18009c228  movups  xmm0, xmmword ptr [rsi+58h]
0x18009c22c  movups  xmmword ptr [rdi+50h], xmm0
0x18009c230  movups  xmm1, xmmword ptr [rsi+68h]
0x18009c234  movups  xmmword ptr [rdi+60h], xmm1
0x18009c238  movups  xmm0, xmmword ptr [rsi+78h]
0x18009c23c  movups  xmmword ptr [rdi+70h], xmm0
0x18009c240  movups  xmm1, xmmword ptr [rsi+88h]
0x18009c247  movups  xmmword ptr [rdi+80h], xmm1
0x18009c24e  movups  xmm0, xmmword ptr [rsi+98h]
0x18009c255  movups  xmmword ptr [rdi+90h], xmm0
0x18009c25c  movups  xmm1, xmmword ptr [rsi+0A8h]
0x18009c263  movups  xmmword ptr [rdi+0A0h], xmm1
0x18009c26a  movups  xmm0, xmmword ptr [rsi+0B8h]
0x18009c271  movups  xmmword ptr [rdi+0B0h], xmm0
0x18009c278  movups  xmm1, xmmword ptr [rsi+0C8h]
0x18009c27f  movups  xmmword ptr [rdi+0C0h], xmm1
0x18009c286  movups  xmm0, xmmword ptr [rsi+0D8h]
0x18009c28d  movups  xmmword ptr [rdi+0D0h], xmm0
0x18009c294  mov     rax, [rsi+0E8h]
0x18009c29b  mov     [rdi+0E0h], rax
0x18009c2a2  lea     r12, [rsi+0F0h]
0x18009c2a9  lea     r14, [rdi+0E8h]
0x18009c2b0  cmp     r14, r12
0x18009c2b3  jz      short loc_18009C2DA
0x18009c2b5  mov     rcx, [r14]
0x18009c2b8  test    rcx, rcx
0x18009c2bb  jnz     loc_18009C55F
0x18009c2c1  mov     rax, [r12]
0x18009c2c5  mov     [r14], rax
0x18009c2c8  mov     rax, [r12+8]
0x18009c2cd  mov     [r14+8], rax
0x18009c2d1  mov     [r12], r8
0x18009c2d5  mov     [r12+8], r8
0x18009c2da  mov     eax, [rsi+100h]
0x18009c2e0  mov     [rdi+0F8h], eax
0x18009c2e6  lea     r12, [rsi+118h]
0x18009c2ed  lea     rbx, [r13+118h]
0x18009c2f4  cmp     rbx, r12
0x18009c2f7  jz      short loc_18009C310
0x18009c2f9  mov     rcx, [rbx]
0x18009c2fc  test    rcx, rcx
0x18009c2ff  jnz     loc_18009C676
0x18009c305  mov     rax, [r12]
0x18009c309  mov     [rbx], rax
0x18009c30c  mov     [r12], r8
0x18009c310  mov     rax, [r13+118h]
0x18009c317  test    rax, rax
0x18009c31a  jnz     loc_18009C66D
0x18009c320  mov     [r13+110h], rdi
0x18009c327  lea     rax, [rdi+28h]
0x18009c32b  mov     [r13+140h], rax
0x18009c332  lea     rbx, [r13+120h]
0x18009c339  cmp     [rsi+138h], r8d
0x18009c340  jz      loc_18009C53D
0x18009c346  cmp     [rbx+18h], r8d
0x18009c34a  jnz     short loc_18009C3C7
0x18009c34c  mov     r14, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18009c353  test    r14, r14
0x18009c356  jz      loc_18009C557
0x18009c35c  call    cs:__imp_GetCurrentThreadId
0x18009c362  mov     r12d, eax
0x18009c365  mov     edi, eax
0x18009c367  shr     rdi, 2
0x18009c36b  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18009c375  mul     rdi
0x18009c378  shr     rdx, 3
0x18009c37c  lea     rcx, [rdx+rdx*4]
0x18009c380  add     rcx, rcx
0x18009c383  sub     rdi, rcx
0x18009c386  mov     rcx, [r14+rdi*8]
0x18009c38a  xor     r8d, r8d; unsigned __int64
0x18009c38d  test    rcx, rcx
0x18009c390  jz      loc_18009C629
0x18009c396  cmp     [rcx], r12d
0x18009c399  jz      short loc_18009C3A1
0x18009c39b  mov     rcx, [rcx+8]
0x18009c39f  jmp     short loc_18009C38D
0x18009c3a1  add     rcx, 10h
0x18009c3a5  mov     [rbx], rcx
0x18009c3a8  test    rcx, rcx
0x18009c3ab  jz      short loc_18009C3C7
0x18009c3ad  mov     rax, [rcx]
0x18009c3b0  mov     [rbx+10h], rax
0x18009c3b4  mov     [rcx], rbx
0x18009c3b7  call    cs:__imp_GetCurrentThreadId
0x18009c3bd  mov     [r13+138h], eax
0x18009c3c4  xor     r8d, r8d
0x18009c3c7  mov     [rsi+110h], r15
0x18009c3ce  cmp     [rsi+138h], r8d
0x18009c3d5  jz      short loc_18009C412
0x18009c3d7  lea     rbx, [rsi+120h]
0x18009c3de  call    cs:__imp_GetCurrentThreadId
0x18009c3e4  cmp     [rbx+18h], eax
0x18009c3e7  jnz     loc_18009C731
0x18009c3ed  xor     r8d, r8d
0x18009c3f0  mov     [rbx+18h], r8d
0x18009c3f4  mov     rcx, [rbx]
0x18009c3f7  mov     rax, [rcx]
0x18009c3fa  test    rax, rax
0x18009c3fd  jz      short loc_18009C40F
0x18009c3ff  cmp     rax, rbx
0x18009c402  jnz     loc_18009C759
0x18009c408  mov     rax, [rbx+10h]
0x18009c40c  mov     [rcx], rax
0x18009c40f  mov     [rbx], r8
0x18009c412  lea     rax, ??_7ClientApiCallActivity@UiaProvider@@6B@; const UiaProvider::ClientApiCallActivity::`vftable'
0x18009c419  mov     [rbp+160h+var_190], rax
0x18009c41d  cmp     [rbp+160h+Block], r8
0x18009c424  jnz     loc_18009C765
0x18009c42a  mov     rcx, [rbp+160h+var_80]
0x18009c431  cmp     dword ptr [rcx], 1
0x18009c434  jnz     short loc_18009C46E
0x18009c436  mov     eax, 8007023Eh
0x18009c43b  cmp     [rcx+58h], r8d
0x18009c43f  cmovl   eax, [rcx+58h]
0x18009c443  mov     edx, [rcx+0F8h]
0x18009c449  cmp     edx, 1
0x18009c44c  jl      loc_18009C7A1
0x18009c452  cmp     [rcx+48h], r8d
0x18009c456  jl      short loc_18009C45B
  ... truncated ...
```
