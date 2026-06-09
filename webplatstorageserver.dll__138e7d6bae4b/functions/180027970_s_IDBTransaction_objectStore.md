# s_IDBTransaction_objectStore

- ea: `0x180027970`
- end: `0x180028068`
- name: `s_IDBTransaction_objectStore`
- size: `1784`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180027550`
- `0x180027970`
- `0x1800294c4`
- `0x180029718`
- `0x1800297e0`
- `0x180029e74`
- `0x18002a060`
- `0x1800300c0`
- `0x180037d40`
- `0x18004ca40`
- `0x180051bb4`
- `0x180052a4c`
- `0x18005e07c`
- `0x180070e88`
- `0x1800750fc`
- `0x180080fb0`
- `0x1800810a4`
- `0x18008149c`
- `0x180083fcc`
- `0x180084034`
- `0x1800a77c8`
- `0x1800b0bcc`
- `0x1800b1370`
- `0x1800b5f04`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027f8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027fb2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027f8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027fb2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027f7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027fa4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027f7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027fa4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180027a32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180027d63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180027a32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180027d63`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180027a44`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180027d75`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180027a44`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180027d75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027e1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027e1e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180027a9f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180027ce4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180027a9f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180027ce4`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x180027a3e`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x180027d6f`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x180027a3e`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x180027d6f`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800279c7`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180027d06`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800279c7`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180027d06`

## string_xrefs

- `0x1800279a9`: `RPC IDBTran_openObjectStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall s_IDBTransaction_objectStore(__int64 a1, __int64 a2, __int64 a3, void **a4)
{
  const WCHAR *v7; // rbx
  const wchar_t *v8; // r14
  const wchar_t *v9; // rax
  int v10; // eax
  unsigned __int16 *v11; // rcx
  HANDLE CurrentThread; // rax
  int v13; // esi
  __int64 v14; // r15
  char v15; // bl
  const WCHAR *v16; // rbx
  int v17; // eax
  unsigned __int16 *v18; // rdx
  HANDLE v19; // rax
  __int64 v21; // rcx
  char v22; // bl
  APTTYPE v23; // eax
  __int64 v24; // rdx
  void *v25; // rdi
  void *v26; // rdi
  HANDLE ProcessHeap; // rax
  void *v28; // rdi
  HANDLE v29; // rax
  unsigned int *v30; // rax
  APTTYPE pAptType[2]; // [rsp+30h] [rbp-D0h] BYREF
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+38h] [rbp-C8h] BYREF
  void **v33; // [rsp+40h] [rbp-C0h] BYREF
  int v34; // [rsp+48h] [rbp-B8h] BYREF
  char v35; // [rsp+4Ch] [rbp-B4h]
  _BYTE v36[32]; // [rsp+50h] [rbp-B0h] BYREF
  int v37; // [rsp+70h] [rbp-90h] BYREF
  const char *v38; // [rsp+78h] [rbp-88h]
  LPVOID v39; // [rsp+80h] [rbp-80h]
  char v40; // [rsp+88h] [rbp-78h]
  int v41; // [rsp+90h] [rbp-70h]
  __int128 v42; // [rsp+98h] [rbp-68h]
  __int128 v43; // [rsp+A8h] [rbp-58h]
  __int128 v44; // [rsp+B8h] [rbp-48h]
  __int128 v45; // [rsp+C8h] [rbp-38h]
  __int128 v46; // [rsp+D8h] [rbp-28h]
  __int128 v47; // [rsp+E8h] [rbp-18h]
  __int128 v48; // [rsp+F8h] [rbp-8h]
  __int128 v49; // [rsp+108h] [rbp+8h]
  __int128 v50; // [rsp+118h] [rbp+18h]
  __int64 v51; // [rsp+128h] [rbp+28h]
  LPVOID lpMem[2]; // [rsp+130h] [rbp+30h]
  int v53; // [rsp+140h] [rbp+40h]
  __int64 v54; // [rsp+148h] [rbp+48h]
  int *v55; // [rsp+150h] [rbp+50h]
  void *Block; // [rsp+158h] [rbp+58h] BYREF
  _QWORD v57[3]; // [rsp+160h] [rbp+60h] BYREF
  int v58; // [rsp+178h] [rbp+78h]
  int *v59; // [rsp+180h] [rbp+80h]
  char v60; // [rsp+188h] [rbp+88h]
  unsigned __int16 v61[128]; // [rsp+190h] [rbp+90h] BYREF

  v7 = L"RPC IDBTran_openObjectStore";
  pAptType[0] = APTTYPE_STA;
  pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
  v8 = L"NA";
  if ( CoGetApartmentType(pAptType, pAptQualifier) )
    goto LABEL_8;
  if ( pAptType[0] == APTTYPE_MTA )
  {
    v9 = L"MTA";
    if ( pAptQualifier[0] == APTTYPEQUALIFIER_IMPLICIT_MTA )
      v9 = (const wchar_t *)L"MTA Implicit";
    goto LABEL_5;
  }
  if ( pAptType[0] == APTTYPE_STA )
  {
LABEL_56:
    v9 = L"ASTA";
    if ( pAptQualifier[0] != APTTYPEQUALIFIER_APPLICATION_STA )
      v9 = L"STA";
    goto LABEL_5;
  }
  if ( pAptType[0] != APTTYPE_NA )
  {
    if ( pAptType[0] != APTTYPE_MAINSTA )
      goto LABEL_8;
    goto LABEL_56;
  }
  switch ( pAptQualifier[0] )
  {
    case APTTYPEQUALIFIER_NA_ON_MTA:
      v9 = L"NA on MTA";
      break;
    case APTTYPEQUALIFIER_NA_ON_STA:
      v9 = L"NA on STA";
      break;
    case APTTYPEQUALIFIER_NA_ON_IMPLICIT_MTA:
      v9 = L"NA on MTA Implicit";
      break;
    case APTTYPEQUALIFIER_NA_ON_MAINSTA:
      v9 = L"NA on MAINSTA";
      break;
    default:
      v9 = L"NA";
      break;
  }
LABEL_5:
  v10 = StringCchPrintfW(v61, 0x80u, L"%s %s", L"RPC IDBTran_openObjectStore", v9);
  v11 = v61;
  if ( v10 < 0 )
    v11 = L"RPC IDBTran_openObjectStore";
  v7 = v11;
LABEL_8:
  CurrentThread = GetCurrentThread();
  SetThreadDescription(CurrentThread, v7);
  if ( IsDebuggerPresent() )
    SetThreadNameViaException(v7);
  if ( dword_180114128 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 5060LL) )
  {
    Init_thread_header(&dword_180114128);
    if ( dword_180114128 == -1 )
    {
      HangDetectionWatchDog::HangDetectionWatchDog(v21, 300000);
      atexit(HangDetectionWatchDog::s_DefaultInstance_::_2_::_dynamic_atexit_destructor_for__s_instance__);
      Init_thread_footer(&dword_180114128);
    }
  }
  _InterlockedIncrement64(&qword_180114130);
  *(_QWORD *)pAptType = qword_180114140;
  SetThreadpoolTimer(pti, (PFILETIME)pAptType, 0, 0);
  v34 = 0;
  v35 = 0;
  v40 = 0;
  v37 = 0;
  v38 = "IDB_IDBTransaction_objectStore";
  v39 = 0;
  v41 = 0;
  *(_OWORD *)lpMem = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v53 = 1;
  v54 = 0;
  v55 = &v34;
  Block = 0;
  v57[0] = 0;
  v57[1] = &v33;
  v57[2] = 0;
  v58 = 0;
  v59 = &v37;
  v60 = 0;
  v33 = &IndexedDbTraceLogging::IDB_IDBTransaction_objectStore::`vftable';
  IndexedDbTraceLogging::IDB_IDBTransaction_objectStore::StartActivity(
    (IndexedDbTraceLogging::IDB_IDBTransaction_objectStore *)&v33,
    (void *)a2,
    (const struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 *)a3);
  if ( a4 )
    *a4 = 0;
  v13 = -2147024809;
  if ( a2 && a4 )
  {
    *(_QWORD *)pAptType = 0;
    if ( (int)CIndexedDBServerConnectionsMgr::GetCallerId((struct ICallerIdentity **)pAptType) < 0 )
    {
      v13 = -2147024891;
    }
    else
    {
      v14 = *(_QWORD *)pAptType;
      if ( *(_BYTE *)(a2 + 56)
        && !(*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a2 + 8) + 16LL))(
              *(_QWORD *)(a2 + 8),
              *(_QWORD *)pAptType)
        && (v15 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 8) + 40LL))(*(_QWORD *)(a2 + 8)),
            v15 == (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v14 + 40LL))(v14)) )
      {
        *(_QWORD *)pAptQualifier = 0;
        v13 = CIndexedDBServerTransaction::OpenObjectStore(
                (CIndexedDBServerTransaction *)a2,
                *(_DWORD *)a3,
                *(const unsigned __int16 **)(a3 + 8),
                (struct CIndexedDBServerObjectStore **)pAptQualifier);
        pAptType[0] = APTTYPE_STA;
        if ( v13 < 0 )
        {
          if ( (int)CIndexedDBServerTransaction::GetClientContextFlags(
                      (CIndexedDBServerTransaction *)a2,
                      (unsigned int *)pAptType) >= 0 )
            CIndexedDBServerPhysicalDBManager::HandleCorruptionIfDetected(pAptType[0], v13, 0);
        }
        else
        {
          *a4 = *(void **)pAptQualifier;
        }
      }
      else
      {
        v13 = -2147024891;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
      if ( v13 >= 0 )
      {
        IndexedDbTraceLogging::IDB_IDBTransaction_objectStore::Stop(
          (IndexedDbTraceLogging::IDB_IDBTransaction_objectStore *)&v33,
          *a4);
        goto LABEL_24;
      }
    }
  }
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v33, (unsigned int)v13);
LABEL_24:
  v33 = &IndexedDbTraceLogging::IDB_IDBTransaction_objectStore::`vftable';
  if ( !Block )
    goto LABEL_25;
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(&v33, pAptType);
  if ( Block && *(_DWORD *)Block == 1 )
  {
    v22 = 1;
  }
  else
  {
    v22 = 0;
    wil::details::shared_object<wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(&Block);
  }
  if ( *(_QWORD *)pAptType )
    ReleaseSRWLockExclusive(*(PSRWLOCK *)pAptType);
  if ( v22 )
  {
LABEL_25:
    if ( *v55 == 1 )
    {
      v23 = v55[22];
      pAptType[0] = v23;
      v24 = 2147942974LL;
      if ( v23 < APTTYPE_STA )
        v24 = (unsigned int)v23;
      wil::ActivityBase<StorageServerProvider,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v55,
        v24,
        pAptType);
      wil::ActivityBase<StorageServerProvider,1,70368744177666,4,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(&v33);
    }
  }
  if ( v58 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v57);
  if ( Block )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block, 0xFFFFFFFF) == 1 )
    {
      v25 = Block;
      if ( Block )
      {
        wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>((char *)Block + 8);
        operator delete(v25);
      }
    }
    Block = 0;
  }
  if ( lpMem[0] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpMem[0], 0xFFFFFFFF) == 1 )
    {
      v26 = lpMem[0];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v26);
    }
    *(_OWORD *)lpMem = 0;
  }
  if ( v40 )
  {
    v28 = v39;
    v29 = GetProcessHeap();
    HeapFree(v29, 0, v28);
    v40 = 0;
  }
  v39 = 0;
  if ( v34 == 1 )
  {
    v34 = 2;
    v30 = (unsigned int *)StorageServerProvider::Provider();
    _tlgWriteActivityAutoStop<8,4>(v30, (__int64)v36);
  }
  v34 = 3;
  if ( _InterlockedExchangeAdd64(&qword_180114130, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(pti, 0, 0, 0);
  v16 = &word_1800D6108;
  pAptType[0] = APTTYPE_STA;
  pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
  if ( !CoGetApartmentType(pAptType, pAptQualifier) )
  {
    if ( pAptType[0] == APTTYPE_MTA )
    {
      v8 = L"MTA";
      if ( pAptQualifier[0] == APTTYPEQUALIFIER_IMPLICIT_MTA )
        v8 = (const wchar_t *)L"MTA Implicit";
    }
    else
    {
      if ( pAptType[0] )
      {
        if ( pAptType[0] == APTTYPE_NA )
        {
          switch ( pAptQualifier[0] )
          {
            case APTTYPEQUALIFIER_NA_ON_MTA:
              v8 = L"NA on MTA";
              break;
            case APTTYPEQUALIFIER_NA_ON_STA:
              v8 = L"NA on STA";
              break;
            case APTTYPEQUALIFIER_NA_ON_IMPLICIT_MTA:
              v8 = L"NA on MTA Implicit";
              break;
            case APTTYPEQUALIFIER_NA_ON_MAINSTA:
              v8 = L"NA on MAINSTA";
              break;
          }
          goto LABEL_40;
        }
        if ( pAptType[0] != APTTYPE_MAINSTA )
          goto LABEL_43;
      }
      v8 = L"ASTA";
      if ( pAptQualifier[0] != APTTYPEQUALIFIER_APPLICATION_STA )
        v8 = L"STA";
    }
LABEL_40:
    v17 = StringCchPrintfW(v61, 0x80u, L"%s %s", &word_1800D6108, v8);
    v18 = v61;
    if ( v17 < 0 )
      v18 = (unsigned __int16 *)&word_1800D6108;
    v16 = v18;
  }
LABEL_43:
  v19 = GetCurrentThread();
  SetThreadDescription(v19, v16);
  if ( IsDebuggerPresent() )
    SetThreadNameViaException(v16);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180027970  mov     [rsp-8+arg_0], rbx
0x180027975  push    rbp
0x180027976  push    rsi
0x180027977  push    rdi
0x180027978  push    r12
0x18002797a  push    r13
0x18002797c  push    r14
0x18002797e  push    r15
0x180027980  lea     rbp, [rsp-1A0h]
0x180027988  sub     rsp, 2A0h
0x18002798f  mov     rax, cs:__security_cookie
0x180027996  xor     rax, rsp
0x180027999  mov     [rbp+1D0h+var_40], rax
0x1800279a0  mov     rdi, r9
0x1800279a3  mov     r12, r8
0x1800279a6  mov     r13, rdx
0x1800279a9  lea     rbx, aRpcIdbtranOpen; "RPC IDBTran_openObjectStore"
0x1800279b0  xor     r15d, r15d
0x1800279b3  mov     [rsp+2D0h+pAptType], r15d
0x1800279b8  mov     [rsp+2D0h+pAptQualifier], r15d
0x1800279bd  lea     rdx, [rsp+2D0h+pAptQualifier]; pAptQualifier
0x1800279c2  lea     rcx, [rsp+2D0h+pAptType]; pAptType
0x1800279c7  call    cs:__imp_CoGetApartmentType
0x1800279cd  lea     r14, aNa; "NA"
0x1800279d4  lea     r8, aSta; "STA"
0x1800279db  lea     rdx, aMtaImplicit; "MTA Implicit"
0x1800279e2  test    eax, eax
0x1800279e4  jnz     short loc_180027A32
0x1800279e6  mov     ecx, [rsp+2D0h+pAptType]
0x1800279ea  cmp     ecx, 1
0x1800279ed  jnz     loc_180027E26
0x1800279f3  lea     rax, aMta; "MTA"
0x1800279fa  cmp     [rsp+2D0h+pAptQualifier], ecx
0x1800279fe  cmovz   rax, rdx
0x180027a02  mov     [rsp+2D0h+var_2B0], rax
0x180027a07  mov     r9, rbx
0x180027a0a  lea     r8, aSS_1; "%s %s"
0x180027a11  mov     edx, 80h; unsigned __int64
0x180027a16  lea     rcx, [rbp+1D0h+var_140]; unsigned __int16 *
0x180027a1d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027a22  lea     rcx, [rbp+1D0h+var_140]
0x180027a29  test    eax, eax
0x180027a2b  cmovs   rcx, rbx
0x180027a2f  mov     rbx, rcx
0x180027a32  call    cs:__imp_GetCurrentThread
0x180027a38  mov     rcx, rax; hThread
0x180027a3b  mov     rdx, rbx; lpThreadDescription
0x180027a3e  call    cs:__imp_SetThreadDescription
0x180027a44  call    cs:__imp_IsDebuggerPresent
0x180027a4a  test    eax, eax
0x180027a4c  jnz     loc_180027E9D
0x180027a52  mov     ecx, cs:_tls_index
0x180027a58  mov     rax, gs:58h
0x180027a61  mov     edx, 13C4h
0x180027a66  mov     rax, [rax+rcx*8]
0x180027a6a  mov     ecx, [rdx+rax]
0x180027a6d  cmp     cs:dword_180114128, ecx
0x180027a73  jg      loc_180027DB9
0x180027a79  lock inc cs:qword_180114130
0x180027a81  mov     rax, cs:qword_180114140
0x180027a88  mov     qword ptr [rsp+2D0h+pAptType], rax
0x180027a8d  xor     r9d, r9d; msWindowLength
0x180027a90  xor     r8d, r8d; msPeriod
0x180027a93  lea     rdx, [rsp+2D0h+pAptType]; pftDueTime
0x180027a98  mov     rcx, cs:pti; pti
0x180027a9f  call    cs:__imp_SetThreadpoolTimer
0x180027aa5  nop
0x180027aa6  mov     [rsp+2D0h+var_288], r15d
0x180027aab  mov     [rsp+2D0h+var_284], 0
0x180027ab0  mov     [rbp+1D0h+var_248], 0
0x180027ab4  mov     [rsp+2D0h+var_260], r15d
0x180027ab9  lea     rax, aIdbIdbtransact_1; "IDB_IDBTransaction_objectStore"
0x180027ac0  mov     [rsp+2D0h+var_258], rax
0x180027ac5  mov     [rbp+1D0h+var_250], r15
0x180027ac9  mov     [rbp+1D0h+var_240], r15d
0x180027acd  xorps   xmm0, xmm0
0x180027ad0  movdqa  xmmword ptr [rbp+1D0h+lpMem], xmm0
0x180027ad5  xorps   xmm1, xmm1
0x180027ad8  xor     eax, eax
0x180027ada  movups  [rbp+1D0h+var_238], xmm1
0x180027ade  movups  [rbp+1D0h+var_228], xmm1
0x180027ae2  movups  [rbp+1D0h+var_218], xmm1
0x180027ae6  movups  [rbp+1D0h+var_208], xmm1
0x180027aea  movups  [rbp+1D0h+var_1F8], xmm1
0x180027aee  movups  [rbp+1D0h+var_1E8], xmm1
0x180027af2  movups  [rbp+1D0h+var_1D8], xmm1
0x180027af6  movups  [rbp+1D0h+var_1C8], xmm1
0x180027afa  movups  [rbp+1D0h+var_1B8], xmm1
0x180027afe  mov     [rbp+1D0h+var_1A8], rax
0x180027b02  mov     [rbp+1D0h+var_190], 1
0x180027b09  mov     [rbp+1D0h+var_188], rax
0x180027b0d  lea     rax, [rsp+2D0h+var_288]
0x180027b12  mov     [rbp+1D0h+var_180], rax
0x180027b16  mov     [rbp+1D0h+Block], r15
0x180027b1a  mov     [rbp+1D0h+var_170], r15
0x180027b1e  lea     rax, [rsp+2D0h+var_290]
0x180027b23  mov     [rbp+1D0h+var_168], rax
0x180027b27  mov     [rbp+1D0h+var_160], r15
0x180027b2b  mov     [rbp+1D0h+var_158], r15d
0x180027b2f  lea     rax, [rsp+2D0h+var_260]
0x180027b34  mov     [rbp+1D0h+var_150], rax
0x180027b3b  mov     [rbp+1D0h+var_148], 0
0x180027b42  lea     rax, ??_7IDB_IDBTransaction_objectStore@IndexedDbTraceLogging@@6B@; const IndexedDbTraceLogging::IDB_IDBTransaction_objectStore::`vftable'
0x180027b49  mov     [rsp+2D0h+var_290], rax
0x180027b4e  mov     r8, r12; struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 *
0x180027b51  mov     rdx, r13; void *
0x180027b54  lea     rcx, [rsp+2D0h+var_290]; this
0x180027b59  call    ?StartActivity@IDB_IDBTransaction_objectStore@IndexedDbTraceLogging@@QEAAXPEAXAEBU__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001@@@Z; IndexedDbTraceLogging::IDB_IDBTransaction_objectStore::StartActivity(void *,__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 const &)
0x180027b5e  nop
0x180027b5f  test    rdi, rdi
0x180027b62  jz      short loc_180027B67
0x180027b64  mov     [rdi], r15
0x180027b67  mov     esi, 80070057h
0x180027b6c  test    r13, r13
0x180027b6f  jnz     short loc_180027B82
0x180027b71  mov     edx, esi
0x180027b73  lea     rcx, [rsp+2D0h+var_290]
0x180027b78  call    ?Stop@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180027b7d  jmp     loc_180027C53
0x180027b82  test    rdi, rdi
0x180027b85  jz      short loc_180027B71
0x180027b87  mov     qword ptr [rsp+2D0h+pAptType], r15
0x180027b8c  lea     rcx, [rsp+2D0h+pAptType]; struct ICallerIdentity **
0x180027b91  call    ?GetCallerId@CIndexedDBServerConnectionsMgr@@SAJPEAPEAUICallerIdentity@@@Z; CIndexedDBServerConnectionsMgr::GetCallerId(ICallerIdentity * *)
0x180027b96  test    eax, eax
0x180027b98  js      loc_180027ED2
0x180027b9e  movzx   eax, byte ptr [r13+38h]
0x180027ba3  nop
0x180027ba4  mov     r15, qword ptr [rsp+2D0h+pAptType]
0x180027ba9  test    al, al
0x180027bab  jz      loc_180027DAF
0x180027bb1  mov     rcx, [r13+8]
0x180027bb5  mov     rax, [rcx]
0x180027bb8  mov     rdx, r15
0x180027bbb  mov     rax, [rax+10h]
0x180027bbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bc4  test    eax, eax
0x180027bc6  jnz     loc_180027DAF
0x180027bcc  mov     rcx, [r13+8]
0x180027bd0  mov     rax, [rcx]
0x180027bd3  mov     rax, [rax+28h]
0x180027bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bdc  movzx   ebx, al
0x180027bdf  mov     rcx, [r15]
0x180027be2  mov     rax, [rcx+28h]
0x180027be6  mov     rcx, r15
0x180027be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bee  cmp     bl, al
0x180027bf0  jnz     loc_180027DAF
0x180027bf6  mov     qword ptr [rsp+2D0h+pAptQualifier], 0
0x180027bff  lea     r9, [rsp+2D0h+pAptQualifier]; struct CIndexedDBServerObjectStore **
0x180027c04  mov     r8, [r12+8]; unsigned __int16 *
0x180027c09  mov     edx, [r12]; unsigned int
0x180027c0d  mov     rcx, r13; this
0x180027c10  call    ?OpenObjectStore@CIndexedDBServerTransaction@@QEAAJKPEBGPEAPEAVCIndexedDBServerObjectStore@@@Z; CIndexedDBServerTransaction::OpenObjectStore(ulong,ushort const *,CIndexedDBServerObjectStore * *)
0x180027c15  mov     esi, eax
0x180027c17  mov     [rsp+2D0h+pAptType], 0
0x180027c1f  test    eax, eax
0x180027c21  js      loc_180027EAA
0x180027c27  mov     rcx, qword ptr [rsp+2D0h+pAptQualifier]
0x180027c2c  mov     [rdi], rcx
0x180027c2f  mov     rax, [r15]
0x180027c32  mov     rcx, r15
0x180027c35  mov     rax, [rax+8]
0x180027c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c3e  test    esi, esi
0x180027c40  js      loc_180027B71
0x180027c46  mov     rdx, [rdi]; void *
0x180027c49  lea     rcx, [rsp+2D0h+var_290]; this
0x180027c4e  call    ?Stop@IDB_IDBTransaction_objectStore@IndexedDbTraceLogging@@QEAAXPEAX@Z; IndexedDbTraceLogging::IDB_IDBTransaction_objectStore::Stop(void *)
0x180027c53  lea     rax, ??_7IDB_IDBTransaction_objectStore@IndexedDbTraceLogging@@6B@; const IndexedDbTraceLogging::IDB_IDBTransaction_objectStore::`vftable'
0x180027c5a  mov     [rsp+2D0h+var_290], rax
0x180027c5f  cmp     [rbp+1D0h+Block], 0
0x180027c64  jnz     loc_180027EDC
0x180027c6a  mov     rcx, [rbp+1D0h+var_180]
0x180027c6e  cmp     dword ptr [rcx], 1
0x180027c71  jz      loc_180027F10
0x180027c77  cmp     [rbp+1D0h+var_158], 0
0x180027c7b  jnz     loc_180027DF9
0x180027c81  mov     rcx, [rbp+1D0h+Block]
0x180027c85  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180027c8c  test    rcx, rcx
0x180027c8f  jnz     loc_180027F3A
0x180027c95  xor     r15d, r15d
0x180027c98  mov     rcx, [rbp+1D0h+lpMem]
0x180027c9c  test    rcx, rcx
0x180027c9f  jnz     loc_180027F70
0x180027ca5  cmp     [rbp+1D0h+var_248], 0
0x180027ca9  jnz     loc_180027FA0
0x180027caf  mov     [rbp+1D0h+var_250], r15
0x180027cb3  cmp     [rsp+2D0h+var_288], 1
0x180027cb8  jz      loc_180027FC1
0x180027cbe  mov     [rsp+2D0h+var_288], 3
0x180027cc6  lock xadd cs:qword_180114130, rbx
0x180027ccf  cmp     rbx, 1
0x180027cd3  jnz     short loc_180027CEB
0x180027cd5  xor     r9d, r9d; msWindowLength
0x180027cd8  xor     r8d, r8d; msPeriod
0x180027cdb  xor     edx, edx; pftDueTime
0x180027cdd  mov     rcx, cs:pti; pti
0x180027ce4  call    cs:__imp_SetThreadpoolTimer
0x180027cea  nop
0x180027ceb  lea     rbx, word_1800D6108
0x180027cf2  mov     [rsp+2D0h+pAptType], r15d
0x180027cf7  mov     [rsp+2D0h+pAptQualifier], r15d
0x180027cfc  lea     rdx, [rsp+2D0h+pAptQualifier]; pAptQualifier
0x180027d01  lea     rcx, [rsp+2D0h+pAptType]; pAptType
0x180027d06  call    cs:__imp_CoGetApartmentType
0x180027d0c  test    eax, eax
0x180027d0e  jnz     short loc_180027D63
0x180027d10  mov     ecx, [rsp+2D0h+pAptType]
0x180027d14  cmp     ecx, 1
0x180027d17  jnz     loc_180027FE0
0x180027d1d  lea     r14, aMta; "MTA"
0x180027d24  cmp     [rsp+2D0h+pAptQualifier], ecx
0x180027d28  lea     rax, aMtaImplicit; "MTA Implicit"
0x180027d2f  cmovz   r14, rax
0x180027d33  mov     [rsp+2D0h+var_2B0], r14
0x180027d38  mov     r9, rbx
0x180027d3b  lea     r8, aSS_1; "%s %s"
0x180027d42  mov     edx, 80h; unsigned __int64
0x180027d47  lea     rcx, [rbp+1D0h+var_140]; unsigned __int16 *
0x180027d4e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027d53  lea     rdx, [rbp+1D0h+var_140]
0x180027d5a  test    eax, eax
0x180027d5c  cmovs   rdx, rbx
0x180027d60  mov     rbx, rdx
0x180027d63  call    cs:__imp_GetCurrentThread
0x180027d69  mov     rcx, rax; hThread
0x180027d6c  mov     rdx, rbx; lpThreadDescription
0x180027d6f  call    cs:__imp_SetThreadDescription
0x180027d75  call    cs:__imp_IsDebuggerPresent
0x180027d7b  test    eax, eax
0x180027d7d  jnz     loc_18002805A
0x180027d83  mov     eax, esi
0x180027d85  mov     rcx, [rbp+1D0h+var_40]
0x180027d8c  xor     rcx, rsp; StackCookie
0x180027d8f  call    __security_check_cookie
0x180027d94  mov     rbx, [rsp+2D0h+arg_0]
0x180027d9c  add     rsp, 2A0h
0x180027da3  pop     r15
0x180027da5  pop     r14
0x180027da7  pop     r13
0x180027da9  pop     r12
0x180027dab  pop     rdi
0x180027dac  pop     rsi
0x180027dad  pop     rbp
0x180027dae  retn
0x180027daf  mov     esi, 80070005h
0x180027db4  jmp     loc_180027C2F
0x180027db9  lea     rcx, dword_180114128
0x180027dc0  call    _Init_thread_header
0x180027dc5  cmp     cs:dword_180114128, 0FFFFFFFFh
0x180027dcc  jnz     loc_180027A79
0x180027dd2  mov     edx, 493E0h
0x180027dd7  call    ??0HangDetectionWatchDog@@QEAA@V?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@@Z; HangDetectionWatchDog::HangDetectionWatchDog(std::chrono::duration<__int64,std::ratio<1,1000>>)
0x180027ddc  lea     rcx, _HangDetectionWatchDog__s_DefaultInstance____2____dynamic_atexit_destructor_for__s_instance__; void (__cdecl *)()
0x180027de3  call    atexit
0x180027de8  lea     rcx, dword_180114128
0x180027def  call    _Init_thread_footer
0x180027df4  jmp     loc_180027A79
0x180027df9  lea     rcx, [rbp+1D0h+var_170]; this
0x180027dfd  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180027e02  jmp     loc_180027C81
0x180027e07  test    bl, bl
0x180027e09  jnz     loc_180027C6A
0x180027e0f  jmp     loc_180027C77
0x180027e14  mov     rcx, qword ptr [rsp+2D0h+pAptType]; SRWLock
0x180027e19  test    rcx, rcx
0x180027e1c  jz      short loc_180027E07
0x180027e1e  call    cs:__imp_ReleaseSRWLockExclusive
0x180027e24  jmp     short loc_180027E07
0x180027e26  test    ecx, ecx
0x180027e28  jz      short loc_180027E38
0x180027e2a  sub     ecx, 2
0x180027e2d  jz      short loc_180027E4D
0x180027e2f  cmp     ecx, 1
0x180027e32  jnz     loc_180027A32
0x180027e38  lea     rax, aAsta; "ASTA"
0x180027e3f  cmp     [rsp+2D0h+pAptQualifier], 6
0x180027e44  cmovnz  rax, r8
0x180027e48  jmp     loc_180027A02
0x180027e4d  mov     ecx, [rsp+2D0h+pAptQualifier]
0x180027e51  sub     ecx, 2
0x180027e54  jz      short loc_180027E91
0x180027e56  sub     ecx, 1
0x180027e59  jz      short loc_180027E85
0x180027e5b  sub     ecx, 1
0x180027e5e  jz      short loc_180027E79
0x180027e60  cmp     ecx, 1
0x180027e63  jz      short loc_180027E6D
0x180027e65  mov     rax, r14
0x180027e68  jmp     loc_180027A02
0x180027e6d  lea     rax, aNaOnMainsta; "NA on MAINSTA"
0x180027e74  jmp     loc_180027A02
0x180027e79  lea     rax, aNaOnMtaImplici; "NA on MTA Implicit"
0x180027e80  jmp     loc_180027A02
0x180027e85  lea     rax, aNaOnSta; "NA on STA"
0x180027e8c  jmp     loc_180027A02
0x180027e91  lea     rax, aNaOnMta; "NA on MTA"
  ... truncated ...
```
