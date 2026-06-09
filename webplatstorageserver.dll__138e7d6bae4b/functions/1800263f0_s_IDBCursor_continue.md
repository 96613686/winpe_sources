# s_IDBCursor_continue

- ea: `0x1800263f0`
- end: `0x1800273e5`
- name: `s_IDBCursor_continue`
- size: `4085`
- prototype: ``
- caller_count: `0`
- callee_count: `45`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000a95c`
- `0x18000a9d8`
- `0x18000c0c8`
- `0x18000c250`
- `0x180012840`
- `0x180013030`
- `0x180020ea0`
- `0x180022990`
- `0x180022a30`
- `0x180022b38`
- `0x180022f20`
- `0x1800241c0`
- `0x180024650`
- `0x180024720`
- `0x18002491c`
- `0x180024998`
- `0x180024eb0`
- `0x1800263f0`
- `0x180027550`
- `0x180028070`
- `0x180029718`
- `0x180029e74`
- `0x18002a060`
- `0x180037d40`
- `0x18004ca40`
- `0x180051bb4`
- `0x180052a4c`
- `0x18005e07c`
- `0x180070e88`
- `0x1800750fc`
- `0x1800766b8`
- `0x180080fb0`
- `0x1800810a4`
- `0x18008149c`
- `0x180081b10`
- `0x180083fcc`
- `0x180084034`
- `0x180088dd4`
- `0x1800a77c8`
- `0x1800afa1c`
- `0x1800b0bcc`
- `0x1800b24c4`
- `0x1800b5f04`
- `0x1800bab3c`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027309`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027331`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027309`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027331`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800272fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027323`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800272fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027323`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026963`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026963`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800264c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002681b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800264c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002681b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800264d8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002682d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800264d8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002682d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800268f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002692d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800268f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002692d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026e35`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026e35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800266c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026d0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800266c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026d0c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026533`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002679c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026533`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002679c`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x1800264d2`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x180026827`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x1800264d2`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x180026827`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18002645b`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800267be`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18002645b`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800267be`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall s_IDBCursor_continue(
        __int64 a1,
        __int64 a2,
        void *a3,
        unsigned __int8 a4,
        const struct __MIDL_RPCIndexedDB_0009 **a5)
{
  const WCHAR *v8; // rbx
  const wchar_t *v9; // r14
  const wchar_t *v10; // rax
  int v11; // eax
  unsigned __int16 *v12; // rcx
  HANDLE CurrentThread; // rax
  int CurrentKeyForIndex; // edi
  void *v15; // rax
  APTTYPEQUALIFIER v16; // edx
  void *v17; // rcx
  struct _FILETIME v18; // r15
  const struct __MIDL_RPCIndexedDB_0009 *v19; // rax
  char *v20; // rbx
  struct _RTL_CRITICAL_SECTION *v21; // rbx
  const WCHAR *v22; // rbx
  int v23; // eax
  unsigned __int16 *v24; // rdx
  HANDLE v25; // rax
  unsigned __int8 (__fastcall *v27)(struct _FILETIME); // rdi
  char v28; // bl
  __int64 v29; // rbx
  struct _RTL_CRITICAL_SECTION *v30; // r12
  unsigned __int64 v31; // rbx
  int *v32; // rbx
  bool v33; // r12
  char v34; // r12
  const char *v35; // r9
  __int64 v36; // rdx
  int v37; // ecx
  int v38; // edi
  void *v39; // rcx
  rsize_t v40; // r12
  int v41; // eax
  unsigned int v42; // r9d
  int v43; // r8d
  const struct __MIDL_RPCIndexedDB_0001 *v44; // rax
  const struct __MIDL_RPCIndexedDB_0001 *v45; // rdx
  const struct __MIDL_RPCIndexedDB_0001 *v46; // rdx
  int v47; // ecx
  void *v48; // rax
  __int64 v49; // rdx
  int v50; // ecx
  void *v51; // rcx
  rsize_t v52; // r12
  void *v53; // rax
  __int64 v54; // r15
  unsigned int v55; // r12d
  const char *v56; // r9
  void *v57; // r10
  unsigned int v58; // eax
  const char *v59; // r9
  __int64 v60; // r12
  __int64 v61; // rdx
  rsize_t v62; // r15
  int v63; // ecx
  int v64; // eax
  __int64 v65; // rcx
  int v66; // eax
  char v67; // bl
  APTTYPE v68; // eax
  __int64 v69; // rdx
  void *v70; // rbx
  void *v71; // rbx
  HANDLE ProcessHeap; // rax
  void *v73; // rbx
  HANDLE v74; // rax
  unsigned int *v75; // rax
  int v76; // [rsp+20h] [rbp-E0h]
  bool v77; // [rsp+30h] [rbp-D0h] BYREF
  bool v78[3]; // [rsp+31h] [rbp-CFh] BYREF
  APTTYPEQUALIFIER pAptQualifier; // [rsp+34h] [rbp-CCh] BYREF
  APTTYPE pAptType; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int8 v81; // [rsp+3Ch] [rbp-C4h]
  void *Source; // [rsp+40h] [rbp-C0h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v85; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v86; // [rsp+68h] [rbp-98h]
  const struct __MIDL_RPCIndexedDB_0009 **v87; // [rsp+70h] [rbp-90h]
  char v88[8]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v89; // [rsp+80h] [rbp-80h]
  __int128 v90; // [rsp+88h] [rbp-78h] BYREF
  __int64 v91; // [rsp+98h] [rbp-68h]
  void **v92; // [rsp+A0h] [rbp-60h] BYREF
  int v93; // [rsp+A8h] [rbp-58h] BYREF
  char v94; // [rsp+ACh] [rbp-54h]
  _BYTE v95[32]; // [rsp+B0h] [rbp-50h] BYREF
  int v96; // [rsp+D0h] [rbp-30h] BYREF
  const char *v97; // [rsp+D8h] [rbp-28h]
  LPVOID v98; // [rsp+E0h] [rbp-20h]
  char v99; // [rsp+E8h] [rbp-18h]
  int v100; // [rsp+F0h] [rbp-10h]
  __int128 v101; // [rsp+F8h] [rbp-8h]
  __int128 v102; // [rsp+108h] [rbp+8h]
  __int128 v103; // [rsp+118h] [rbp+18h]
  __int128 v104; // [rsp+128h] [rbp+28h]
  __int128 v105; // [rsp+138h] [rbp+38h]
  __int128 v106; // [rsp+148h] [rbp+48h]
  __int128 v107; // [rsp+158h] [rbp+58h]
  __int128 v108; // [rsp+168h] [rbp+68h]
  __int128 v109; // [rsp+178h] [rbp+78h]
  __int64 v110; // [rsp+188h] [rbp+88h]
  LPVOID lpMem[2]; // [rsp+190h] [rbp+90h]
  int v112; // [rsp+1A0h] [rbp+A0h]
  __int64 v113; // [rsp+1A8h] [rbp+A8h]
  int *v114; // [rsp+1B0h] [rbp+B0h]
  void *Block; // [rsp+1B8h] [rbp+B8h] BYREF
  _QWORD v116[3]; // [rsp+1C0h] [rbp+C0h] BYREF
  int v117; // [rsp+1D8h] [rbp+D8h]
  int *v118; // [rsp+1E0h] [rbp+E0h]
  char v119; // [rsp+1E8h] [rbp+E8h]
  unsigned __int16 v120[128]; // [rsp+1F0h] [rbp+F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  v81 = a4;
  Source = a3;
  v87 = a5;
  v8 = L"RPC IDBCur_continue";
  pAptType = APTTYPE_STA;
  pAptQualifier = APTTYPEQUALIFIER_NONE;
  v9 = L"NA";
  if ( CoGetApartmentType(&pAptType, &pAptQualifier) )
    goto LABEL_8;
  if ( pAptType == APTTYPE_MTA )
  {
    v10 = L"MTA";
    if ( pAptQualifier == APTTYPEQUALIFIER_IMPLICIT_MTA )
      v10 = (const wchar_t *)L"MTA Implicit";
    goto LABEL_5;
  }
  if ( pAptType == APTTYPE_STA )
  {
LABEL_159:
    v10 = L"ASTA";
    if ( pAptQualifier != APTTYPEQUALIFIER_APPLICATION_STA )
      v10 = L"STA";
    goto LABEL_5;
  }
  if ( pAptType != APTTYPE_NA )
  {
    if ( pAptType != APTTYPE_MAINSTA )
      goto LABEL_8;
    goto LABEL_159;
  }
  switch ( pAptQualifier )
  {
    case APTTYPEQUALIFIER_NA_ON_MTA:
      v10 = L"NA on MTA";
      break;
    case APTTYPEQUALIFIER_NA_ON_STA:
      v10 = L"NA on STA";
      break;
    case APTTYPEQUALIFIER_NA_ON_IMPLICIT_MTA:
      v10 = L"NA on MTA Implicit";
      break;
    case APTTYPEQUALIFIER_NA_ON_MAINSTA:
      v10 = L"NA on MAINSTA";
      break;
    default:
      v10 = L"NA";
      break;
  }
LABEL_5:
  v11 = StringCchPrintfW(v120, 0x80u, L"%s %s", L"RPC IDBCur_continue", v10);
  v12 = v120;
  if ( v11 < 0 )
    v12 = L"RPC IDBCur_continue";
  v8 = v12;
LABEL_8:
  CurrentThread = GetCurrentThread();
  SetThreadDescription(CurrentThread, v8);
  if ( IsDebuggerPresent() )
    SetThreadNameViaException(v8);
  if ( dword_180114128 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 5060LL) )
  {
    Init_thread_header(&dword_180114128);
    if ( dword_180114128 == -1 )
    {
      HangDetectionWatchDog::HangDetectionWatchDog(v65, 300000);
      atexit(HangDetectionWatchDog::s_DefaultInstance_::_2_::_dynamic_atexit_destructor_for__s_instance__);
      Init_thread_footer(&dword_180114128);
    }
  }
  _InterlockedIncrement64(&qword_180114130);
  pftDueTime = (struct _FILETIME)qword_180114140;
  SetThreadpoolTimer(pti, &pftDueTime, 0, 0);
  v93 = 0;
  v94 = 0;
  v99 = 0;
  v96 = 0;
  v97 = "IDB_IDBCursor_continue";
  v98 = 0;
  v100 = 0;
  *(_OWORD *)lpMem = 0;
  v101 = 0;
  v102 = 0;
  v103 = 0;
  v104 = 0;
  v105 = 0;
  v106 = 0;
  v107 = 0;
  v108 = 0;
  v109 = 0;
  v110 = 0;
  v112 = 1;
  v113 = 0;
  v114 = &v93;
  Block = 0;
  v116[0] = 0;
  v116[1] = &v92;
  v116[2] = 0;
  v117 = 0;
  v118 = &v96;
  v119 = 0;
  v92 = &IndexedDbTraceLogging::IDB_IDBCursor_continue::`vftable';
  IndexedDbTraceLogging::IDB_IDBCursor_continue::StartActivity(
    (IndexedDbTraceLogging::IDB_IDBCursor_continue *)&v92,
    (void *)a2,
    (const struct __MIDL_RPCIndexedDB_0001 *)a3,
    a4);
  *a5 = 0;
  if ( !a2 )
  {
    CurrentKeyForIndex = -2147024809;
    goto LABEL_13;
  }
  pftDueTime = 0;
  if ( (int)CIndexedDBServerConnectionsMgr::GetCallerId((struct ICallerIdentity **)&pftDueTime) < 0 )
  {
    CurrentKeyForIndex = -2147024891;
    wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v92, 2147942405LL);
    goto LABEL_32;
  }
  v18 = pftDueTime;
  if ( !*(_BYTE *)(a2 + 56)
    || (*(unsigned int (__fastcall **)(_QWORD, struct _FILETIME))(**(_QWORD **)(a2 + 8) + 16LL))(
         *(_QWORD *)(a2 + 8),
         pftDueTime)
    || (v27 = *(unsigned __int8 (__fastcall **)(struct _FILETIME))(**(_QWORD **)&v18 + 40LL),
        v28 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 8) + 40LL))(*(_QWORD *)(a2 + 8)),
        v28 != ((__int64 (__fastcall *)(_QWORD))v27)(v18)) )
  {
    CurrentKeyForIndex = -2147024891;
    goto LABEL_30;
  }
  *v87 = 0;
  v21 = (struct _RTL_CRITICAL_SECTION *)(a2 + 16);
  pAptType = APTTYPE_STA;
  if ( a2 != -16 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 16));
    pAptType = APTTYPE_MTA;
  }
  CurrentKeyForIndex = -2147024891;
  if ( *(_BYTE *)(a2 + 56) )
  {
    v29 = *(_QWORD *)(a2 + 96);
    v88[0] = 0;
    v89 = v29;
    _InterlockedIncrement((volatile signed __int32 *)(v29 + 88));
    v30 = (struct _RTL_CRITICAL_SECTION *)(v29 + 192);
    EnterCriticalSection((LPCRITICAL_SECTION)(v29 + 192));
    if ( !*(_BYTE *)(v29 + 56)
      || (v31 = *(_QWORD *)(v29 + 168), !*(_BYTE *)(v31 + 8))
      || (CurrentKeyForIndex = HrJetSetSessionContext(*(_QWORD *)(v31 + 24), v31), CurrentKeyForIndex < 0) )
    {
      LeaveCriticalSection(v30);
      goto LABEL_25;
    }
    *(_DWORD *)(v31 + 12) = GetCurrentThreadId();
    v88[0] = 1;
    v32 = *(int **)(a2 + 104);
    v33 = 0;
    v78[0] = 0;
    CurrentKeyForIndex = 0;
    if ( *((_BYTE *)v32 + 144) )
    {
      v77 = 0;
      CurrentKeyForIndex = CEseLayerCursor::StepPrevious((CEseLayerCursor *)v32, &v77);
      *((_BYTE *)v32 + 144) = 0;
    }
    if ( *((_BYTE *)v32 + 145) )
    {
      CurrentKeyForIndex = CEseLayerCursor::StepNext((CEseLayerCursor *)v32, v78);
      v33 = v78[0];
      if ( CurrentKeyForIndex >= 0 )
      {
        if ( v78[0] )
          goto LABEL_179;
        v90 = 0;
        v91 = 0;
        CurrentKeyForIndex = CEseLayerCursor::GetCurrentKeyForIndex(
                               (CEseLayerCursor *)v32,
                               *((struct CEseLayerIndexSchema **)v32 + 14),
                               (struct __MIDL_RPCIndexedDB_0001 *)&v90);
        if ( CurrentKeyForIndex >= 0 )
        {
          v77 = 1;
          if ( !(unsigned int)CompareKeys(
                                (const struct __MIDL_RPCIndexedDB_0001 *const)(v32 + 10),
                                (const struct __MIDL_RPCIndexedDB_0001 *const)&v90) )
          {
            v85 = 0;
            v86 = 0;
            CurrentKeyForIndex = CEseLayerCursor::GetCurrentKeyForIndex(
                                   (CEseLayerCursor *)v32,
                                   *((struct CEseLayerIndexSchema **)v32 + 15),
                                   (struct __MIDL_RPCIndexedDB_0001 *)&v85);
            if ( CurrentKeyForIndex >= 0 )
            {
              v77 = (unsigned int)CompareKeys(
                                    (const struct __MIDL_RPCIndexedDB_0001 *const)(v32 + 4),
                                    (const struct __MIDL_RPCIndexedDB_0001 *const)&v85) != 0;
              IDBKeyFree((struct __MIDL_RPCIndexedDB_0001 *)&v85);
            }
          }
          IDBKeyFree((struct __MIDL_RPCIndexedDB_0001 *)&v90);
          if ( CurrentKeyForIndex >= 0 && v77 )
          {
LABEL_179:
            v77 = 0;
            CurrentKeyForIndex = CEseLayerCursor::StepPrevious((CEseLayerCursor *)v32, &v77);
          }
        }
      }
      *((_BYTE *)v32 + 145) = 0;
    }
    if ( CurrentKeyForIndex < 0 || v33 )
      goto LABEL_69;
    if ( !Source )
    {
      v41 = *v32;
      v42 = 1;
      if ( (unsigned int)*v32 > 1 )
      {
        v43 = -1;
      }
      else
      {
        v43 = 1;
        if ( v41 == 1 )
        {
LABEL_81:
          CurrentKeyForIndex = HrJetMove(*(_QWORD *)(*((_QWORD *)v32 + 16) + 24LL), *((_QWORD *)v32 + 17), v43, v42);
          if ( CurrentKeyForIndex == -1906378307 )
          {
            v33 = 1;
            CurrentKeyForIndex = 0;
          }
LABEL_83:
          if ( CurrentKeyForIndex >= 0 && !v33 )
          {
            if ( *v32 != 3
              || (v77 = 0,
                  CurrentKeyForIndex = CEseLayerCursor::StepNext((CEseLayerCursor *)v32, &v77),
                  CurrentKeyForIndex >= 0)
              && (CurrentKeyForIndex = CEseLayerCursor::StepPrevious((CEseLayerCursor *)v32, &v77),
                  CurrentKeyForIndex >= 0) )
            {
              v34 = 0;
              CurrentKeyForIndex = CEseLayerCursor::CacheCurrentValues((CEseLayerCursor *)v32);
              if ( CurrentKeyForIndex >= 0 )
              {
                v44 = (const struct __MIDL_RPCIndexedDB_0001 *)(v32 + 4);
                if ( v32[4] )
                {
                  v45 = (const struct __MIDL_RPCIndexedDB_0001 *)*((_QWORD *)v32 + 11);
                  if ( v45 )
                  {
                    v66 = CompareKeys((const struct __MIDL_RPCIndexedDB_0001 *const)(v32 + 4), v45);
                    if ( v66 == -1 || !v66 && (v32[26] & 1) != 0 )
                      goto LABEL_129;
                    v44 = (const struct __MIDL_RPCIndexedDB_0001 *)(v32 + 4);
                  }
                  v46 = (const struct __MIDL_RPCIndexedDB_0001 *)*((_QWORD *)v32 + 12);
                  if ( !v46 || (v64 = CompareKeys(v44, v46), v64 != 1) && (v64 || (v32[26] & 2) == 0) )
                  {
                    v34 = 1;
                    goto LABEL_71;
                  }
                }
LABEL_129:
                CEseLayerCursor::ClearCurrentValues((CEseLayerCursor *)v32);
              }
LABEL_71:
              if ( CurrentKeyForIndex >= 0 && v34 )
              {
                MakeSmartRpcPointer<IndexedDbCursorPositionValues,>(&Source);
                v20 = (char *)Source;
                IndexedDbRpcHelpers::IndexedDbCursorPositionValuesTrait::Free((struct __MIDL_RPCIndexedDB_0009 *)Source);
                v36 = *(_QWORD *)(a2 + 104);
                *(_OWORD *)v20 = 0;
                *((_QWORD *)v20 + 2) = 0;
                *(_DWORD *)v20 = *(_DWORD *)(v36 + 16);
                v37 = *(_DWORD *)(v36 + 16);
                v38 = -2147024882;
                pAptQualifier = -2147024882;
                if ( v37 != 4 )
                {
                  v47 = v37 - 1;
                  if ( v47 )
                  {
                    if ( (unsigned int)(v47 - 1) > 1 )
                      wil::details::in1diag3::_FailFast_Unexpected(
                        retaddr,
                        (void *)0x13E,
                        (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\indexeddbv1\\utils\\indexeddbrpchelpers.cxx",
                        v35);
                    *((_QWORD *)v20 + 1) = *(_QWORD *)(v36 + 24);
                  }
                  else
                  {
                    *((_DWORD *)v20 + 2) = *(_DWORD *)(v36 + 24);
                  }
LABEL_101:
                  v49 = *(_QWORD *)(a2 + 104);
                  *(_OWORD *)(v20 + 24) = 0;
                  *((_QWORD *)v20 + 5) = 0;
                  *((_DWORD *)v20 + 6) = *(_DWORD *)(v49 + 40);
                  v50 = *(_DWORD *)(v49 + 40);
                  if ( v50 != 4 )
                  {
                    v63 = v50 - 1;
                    if ( v63 )
                    {
                      if ( (unsigned int)(v63 - 1) > 1 )
                        wil::details::in1diag3::_FailFast_Unexpected(
                          retaddr,
                          (void *)0x13E,
                          (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\indexeddbv1\\utils\\indexeddbrpchelpers.cxx",
                          v35);
                      *((_QWORD *)v20 + 4) = *(_QWORD *)(v49 + 48);
                    }
                    else
                    {
                      *((_DWORD *)v20 + 8) = *(_DWORD *)(v49 + 48);
                    }
LABEL_110:
                    CurrentKeyForIndex = 0;
                    if ( !v81 )
                      goto LABEL_21;
                    v54 = *(_QWORD *)(a2 + 104);
                    v55 = *(_DWORD *)(v54 + 64);
                    if ( v55 )
                    {
                      v57 = MIDL_user_allocate(v55);
                      if ( !v57 )
                        wil::details::in1diag3::_FailFast_NullAlloc(
                          retaddr,
                          (void *)0xFC,
                          (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\indexeddbv1\\utils\\indexeddbrpchelpers.cxx",
                          v56);
                    }
                    else
                    {
                      v57 = 0;
                    }
                    *((_QWORD *)v20 + 7) = v57;
                    *((_DWORD *)v20 + 12) = v55;
                    v58 = *(_DWORD *)(v54 + 64);
                    *((_DWORD *)v20 + 12) = v58;
                    memcpy_s_4(v57, v58, *(const void *const *)(v54 + 72), *(unsigned int *)(v54 + 64));
                    *((_QWORD *)v20 + 8) = 0;
                    if ( *(_QWORD *)(v54 + 80) )
                    {
                      CurrentKeyForIndex = IDBKeyAlloc((struct __MIDL_RPCIndexedDB_0001 **)v20 + 8);
                      if ( CurrentKeyForIndex >= 0 )
                      {
                        v60 = *((_QWORD *)v20 + 8);
                        v61 = *(_QWORD *)(v54 + 80);
                        *(_OWORD *)v60 = 0;
                        *(_QWORD *)(v60 + 16) = 0;
                        *(_DWORD *)v60 = *(_DWORD *)v61;
                        if ( *(_DWORD *)v61 != 4 )
                        {
                          if ( *(_DWORD *)v61 == 1 )
                          {
                            *(_DWORD *)(v60 + 8) = *(_DWORD *)(v61 + 8);
                          }
                          else
                          {
                            if ( (unsigned int)(*(_DWORD *)v61 - 2) > 1 )
                              wil::details::in1diag3::_FailFast_Unexpected(
                                retaddr,
                                (void *)0x13E,
                                (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\indexeddbv1\\utils\\indexeddbrpchelpers.cxx",
                                v59);
                            *(_QWORD *)(v60 + 8) = *(_QWORD *)(v61 + 8);
                          }
                          goto LABEL_20;
                        }
                        v17 = *(void **)(v61 + 16);
                        Source = v17;
                        SRWLock = (PSRWLOCK)*(unsigned int *)(v61 + 8);
                        v62 = 2LL * (unsigned int)SRWLock;
                        if ( !(_DWORD)SRWLock )
                        {
                          pAptQualifier = APTTYPEQUALIFIER_NONE;
LABEL_18:
                          memcpy_s_4(*(void *const *)(v60 + 16), 2LL * *(unsigned int *)(v60 + 8), v17, v62);
                          v16 = pAptQualifier;
LABEL_19:
                          if ( v16 < APTTYPEQUALIFIER_NONE )
                            wil::details::in1diag3::FailFast_Hr(
                              retaddr,
                              (void *)0x138,
                              (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\indexeddbv1\\utils\\indexeddbrpchelpers.cxx",
                              (const char *)(unsigned int)v16,
                              v76);
                          goto LABEL_20;
                        }
                        if ( v62 <= 0xFFFFFFFF )
                        {
                          v15 = MIDL_user_allocate((unsigned int)v62);
                          if ( !v15 )
                          {
                            v17 = Source;
                            v16 = -2147024882;
LABEL_17:
                            if ( v16 < APTTYPEQUALIFIER_NONE )
                              goto LABEL_19;
                            goto LABEL_18;
                          }
                          v16 = APTTYPEQUALIFIER_NONE;
                          *(_DWORD *)(v60 + 8) = (_DWORD)SRWLock;
                          *(_QWORD *)(v60 + 16) = v15;
                          v17 = Source;
                        }
                        else
                        {
                          v16 = -2147024362;
                        }
                        pAptQualifier = v16;
                        goto LABEL_17;
                      }
                      SCAObjectFree((struct __MIDL_RPCIndexedDB_0004 *)(v20 + 48));
                    }
LABEL_20:
                    v18 = pftDueTime;
LABEL_21:
                    if ( CurrentKeyForIndex >= 0 )
                    {
                      v19 = (const struct __MIDL_RPCIndexedDB_0009 *)v20;
                      v20 = 0;
                      *v87 = v19;
                    }
                    if ( v20 )
                    {
                      IndexedDbRpcHelpers::IndexedDbCursorPositionValuesTrait::Free((struct __MIDL_RPCIndexedDB_0009 *)v20);
                      SRWLock = (PSRWLOCK)v20;
                      WxFreeHeapEx((void **)&SRWLock);
                    }
                    goto LABEL_25;
                  }
                  v51 = *(void **)(v49 + 56);
                  Source = v51;
                  SRWLock = (PSRWLOCK)*(unsigned int *)(v49 + 48);
                  v52 = 2LL * (unsigned int)SRWLock;
                  if ( (_DWORD)SRWLock )
                  {
                    if ( v52 > 0xFFFFFFFF )
                    {
                      v38 = -2147024362;
                    }
                    else
                    {
                      v53 = MIDL_user_allocate((unsigned int)v52);
                      if ( v53 )
                      {
                        v38 = 0;
                        *((_DWORD *)v20 + 8) = (_DWORD)SRWLock;
                        *((_QWORD *)v20 + 5) = v53;
                      }
                      v51 = Source;
                    }
                    if ( v38 < 0 )
                      goto LABEL_109;
                  }
                  else
                  {
                    v38 = 0;
                  }
                  memcpy_s_4(*((void *const *)v20 + 5), 2LL * *((unsigned int *)v20 + 8), v51, v52);
LABEL_109:
                  if ( v38 < 0 )
                    wil::details::in1diag3::FailFast_Hr(
                      retaddr,
                      (void *)0x138,
                      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\indexeddbv1\\utils\\indexeddbrpchelpers.cxx",
                      (const char *)(unsigned int)v38,
                      v76);
                  goto LABEL_110;
                }
                v39 = *(void **)(v36 + 32);
                Source = v39;
                SRWLock = (PSRWLOCK)*(unsigned int *)(v36 + 24);
                v40 = 2LL * (unsigned int)SRWLock;
                if ( (_DWORD)SRWLock )
                {
                  if ( v40 <= 0xFFFFFFFF )
                  {
                    v48 = MIDL_user_allocate((unsigned int)v40);
                    if ( v48 )
                    {
                      v38 = 0;
                      *((_DWORD *)v20 + 2) = (_DWORD)SRWLock;
                      *((_QWORD *)v20 + 2) = v48;
                    }
                    v39 = Source;
                  }
                  else
                  {
                    v38 = -2147024362;
                  }
                  if ( v38 < 0 )
                    goto LABEL_99;
                }
                else
                {
                  v38 = 0;
                }
                memcpy_s_4(*((void *const *)v20 + 2), 2LL * *((unsigned int *)v20 + 2), v39, v40);
LABEL_99:
                if ( v38 < 0 )
                  wil::details::in1diag3::FailFast_Hr(
                    retaddr,
                    (void *)0x138,
                    (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\indexeddbv1\\utils\\indexeddbrpchelpers.cxx",
                    (const char *)(unsigned int)v38,
                    v76);
                v38 = -2147024882;
                goto LABEL_101;
              }
LABEL_25:
              CIndexedDBServerTransaction::CTransactionThreadScope::~CTransactionThreadScope((CIndexedDBServerTransaction::CTransactionThreadScope *)v88);
              v21 = (struct _RTL_CRITICAL_SECTION *)(a2 + 16);
              goto LABEL_26;
            }
LABEL_70:
            v34 = 0;
            goto LABEL_71;
          }
LABEL_69:
          CEseLayerCursor::ClearCurrentValues((CEseLayerCursor *)v32);
          goto LABEL_70;
        }
      }
      if ( v41 != 3 )
        v42 = 0;
      goto LABEL_81;
    }
    v77 = 0;
    while ( 1 )
    {
      if ( CurrentKeyForIndex < 0 || v33 )
        goto LABEL_69;
      CurrentKeyForIndex = CEseLayerCursor::StepNext((CEseLayerCursor *)v32, v78);
      v33 = v78[0];
      if ( CurrentKeyForIndex >= 0 && !v78[0] )
        break;
LABEL_154:
      if ( v77 )
        goto LABEL_83;
    }
    v85 = 0;
    v86 = 0;
    CurrentKeyForIndex = CEseLayerCursor::GetCurrentKeyForIndex(
                           (CEseLayerCursor *)v32,
                           *((struct CEseLayerIndexSchema **)v32 + 15),
                           (struct __MIDL_RPCIndexedDB_0001 *)&v85);
    if ( CurrentKeyForIndex < 0 )
    {
      v33 = 1;
      v78[0] = 1;
      CurrentKeyForIndex = 0;
      goto LABEL_153;
    }
    if ( !IsValidPositionInKeyRange(
            (const struct __MIDL_RPCIndexedDB_0003 *)(v32 + 22),
            (const struct __MIDL_RPCIndexedDB_0001 *)&v85) )
    {
      v33 = 1;
      v78[0] = 1;
      goto LABEL_152;
    }
    if ( !(unsigned int)CompareKeys(
                          (const struct __MIDL_RPCIndexedDB_0001 *const)Source,
                          (const struct __MIDL_RPCIndexedDB_0001 *const)&v85) )
      goto LABEL_191;
    if ( (unsigned int)*v32 <= 1 )
    {
      if ( (unsigned int)CompareKeys(
                           (const struct __MIDL_RPCIndexedDB_0001 *const)Source,
                           (const struct __MIDL_RPCIndexedDB_0001 *const)&v85) == -1 )
        goto LABEL_191;
      if ( (unsigned int)*v32 <= 1 )
      {
LABEL_152:
        IDBKeyFree((struct __MIDL_RPCIndexedDB_0001 *)&v85);
LABEL_153:
        IDBKeyFree((struct __MIDL_RPCIndexedDB_0001 *)&v85);
        goto LABEL_154;
      }
    }
    if ( (unsigned int)CompareKeys(
                         (const struct __MIDL_RPCIndexedDB_0001 *const)Source,
                         (const struct __MIDL_RPCIndexedDB_0001 *const)&v85) != 1 )
      goto LABEL_152;
LABEL_191:
    v77 = 1;
    goto LABEL_152;
  }
LABEL_26:
  if ( pAptType && v21 )
    LeaveCriticalSection(v21);
  pAptType = APTTYPE_STA;
  if ( CurrentKeyForIndex < 0
    && (int)CIndexedDBServerCursor::GetClientContextFlags((CIndexedDBServerCursor *)a2, (unsigned int *)&pAptType) >= 0 )
  {
    CIndexedDBServerPhysicalDBManager::HandleCorruptionIfDetected(pAptType, CurrentKeyForIndex, 0);
  }
LABEL_30:
  (*(void (__fastcall **)(struct _FILETIME))(**(_QWORD **)&v18 + 8LL))(v18);
  if ( CurrentKeyForIndex >= 0 )
  {
    IndexedDbTraceLogging::IDB_IDBCursor_continue::Stop((IndexedDbTraceLogging::IDB_IDBCursor_continue *)&v92, *v87);
    goto LABEL_32;
  }
LABEL_13:
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    &v92,
    (unsigned int)CurrentKeyForIndex);
LABEL_32:
  v92 = &IndexedDbTraceLogging::IDB_IDBCursor_continue::`vftable';
  if ( !Block )
    goto LABEL_33;
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(&v92, &SRWLock);
  if ( Block && *(_DWORD *)Block == 1 )
  {
    v67 = 1;
  }
  else
  {
    v67 = 0;
    wil::details::shared_object<wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(&Block);
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v67 )
  {
LABEL_33:
    if ( *v114 == 1 )
    {
      v68 = v114[22];
      pAptType = v68;
      v69 = 2147942974LL;
      if ( v68 < APTTYPE_STA )
        v69 = (unsigned int)v68;
      wil::ActivityBase<StorageServerProvider,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v114,
        v69,
        &pAptType);
      wil::ActivityBase<StorageServerProvider,1,70368744177666,4,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(&v92);
    }
  }
  if ( v117 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v116);
  if ( Block )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block, 0xFFFFFFFF) == 1 )
    {
      v70 = Block;
      if ( Block )
      {
        wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>((char *)Block + 8);
        operator delete(v70);
      }
    }
    Block = 0;
  }
  if ( lpMem[0] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpMem[0], 0xFFFFFFFF) == 1 )
    {
      v71 = lpMem[0];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v71);
    }
    *(_OWORD *)lpMem = 0;
  }
  if ( v99 )
  {
    v73 = v98;
    v74 = GetProcessHeap();
    HeapFree(v74, 0, v73);
    v99 = 0;
  }
  v98 = 0;
  if ( v93 == 1 )
  {
    v93 = 2;
    v75 = (unsigned int *)StorageServerProvider::Provider();
    _tlgWriteActivityAutoStop<8,4>(v75, (__int64)v95);
  }
  v93 = 3;
  if ( _InterlockedExchangeAdd64(&qword_180114130, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(pti, 0, 0, 0);
  v22 = &word_1800D6108;
  pAptType = APTTYPE_STA;
  pAptQualifier = APTTYPEQUALIFIER_NONE;
  if ( !CoGetApartmentType(&pAptType, &pAptQualifier) )
  {
    if ( pAptType == APTTYPE_MTA )
    {
      v9 = L"MTA";
      if ( pAptQualifier == APTTYPEQUALIFIER_IMPLICIT_MTA )
        v9 = (const wchar_t *)L"MTA Implicit";
    }
    else
    {
      if ( pAptType )
      {
        if ( pAptType == APTTYPE_NA )
        {
          switch ( pAptQualifier )
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
          }
          goto LABEL_48;
        }
        if ( pAptType != APTTYPE_MAINSTA )
          goto LABEL_51;
      }
      v9 = L"ASTA";
      if ( pAptQualifier != APTTYPEQUALIFIER_APPLICATION_STA )
        v9 = L"STA";
    }
LABEL_48:
    v23 = StringCchPrintfW(v120, 0x80u, L"%s %s", &word_1800D6108, v9);
    v24 = v120;
    if ( v23 < 0 )
      v24 = (unsigned __int16 *)&word_1800D6108;
    v22 = v24;
  }
LABEL_51:
  v25 = GetCurrentThread();
  SetThreadDescription(v25, v22);
  if ( IsDebuggerPresent() )
    SetThreadNameViaException(v22);
  return (unsigned int)CurrentKeyForIndex;
}

```

## disassembly

```asm
0x1800263f0  mov     [rsp-8+arg_0], rbx
0x1800263f5  push    rbp
0x1800263f6  push    rsi
0x1800263f7  push    rdi
0x1800263f8  push    r12
0x1800263fa  push    r13
0x1800263fc  push    r14
0x1800263fe  push    r15
0x180026400  lea     rbp, [rsp-200h]
0x180026408  sub     rsp, 300h
0x18002640f  mov     rax, cs:__security_cookie
0x180026416  xor     rax, rsp
0x180026419  mov     [rbp+230h+var_40], rax
0x180026420  movzx   r15d, r9b
0x180026424  mov     [rsp+330h+var_2F4], r9b
0x180026429  mov     rsi, r8
0x18002642c  mov     [rsp+330h+Source], r8
0x180026431  mov     r13, rdx
0x180026434  mov     rdi, [rbp+230h+arg_20]
0x18002643b  mov     [rsp+330h+var_2C0], rdi
0x180026440  lea     rbx, aRpcIdbcurConti; "RPC IDBCur_continue"
0x180026447  xor     eax, eax
0x180026449  mov     [rsp+330h+pAptType], eax
0x18002644d  mov     [rsp+330h+pAptQualifier], eax
0x180026451  lea     rdx, [rsp+330h+pAptQualifier]; pAptQualifier
0x180026456  lea     rcx, [rsp+330h+pAptType]; pAptType
0x18002645b  call    cs:__imp_CoGetApartmentType
0x180026461  lea     r14, aNa; "NA"
0x180026468  lea     r8, aSta; "STA"
0x18002646f  lea     rdx, aMtaImplicit; "MTA Implicit"
0x180026476  test    eax, eax
0x180026478  jnz     short loc_1800264C6
0x18002647a  mov     ecx, [rsp+330h+pAptType]
0x18002647e  cmp     ecx, 1
0x180026481  jnz     loc_180026E8A
0x180026487  lea     rax, aMta; "MTA"
0x18002648e  cmp     [rsp+330h+pAptQualifier], ecx
0x180026492  cmovz   rax, rdx
0x180026496  mov     qword ptr [rsp+330h+var_310], rax; int
0x18002649b  mov     r9, rbx
0x18002649e  lea     r8, aSS_1; "%s %s"
0x1800264a5  mov     edx, 80h; unsigned __int64
0x1800264aa  lea     rcx, [rbp+230h+var_140]; unsigned __int16 *
0x1800264b1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800264b6  lea     rcx, [rbp+230h+var_140]
0x1800264bd  test    eax, eax
0x1800264bf  cmovs   rcx, rbx
0x1800264c3  mov     rbx, rcx
0x1800264c6  call    cs:__imp_GetCurrentThread
0x1800264cc  mov     rcx, rax; hThread
0x1800264cf  mov     rdx, rbx; lpThreadDescription
0x1800264d2  call    cs:__imp_SetThreadDescription
0x1800264d8  call    cs:__imp_IsDebuggerPresent
0x1800264de  test    eax, eax
0x1800264e0  jnz     loc_180026F01
0x1800264e6  mov     ecx, cs:_tls_index
0x1800264ec  mov     rax, gs:58h
0x1800264f5  mov     edx, 13C4h
0x1800264fa  mov     rax, [rax+rcx*8]
0x1800264fe  mov     ecx, [rdx+rax]
0x180026501  cmp     cs:dword_180114128, ecx
0x180026507  jg      loc_180026D47
0x18002650d  lock inc cs:qword_180114130
0x180026515  mov     rax, cs:qword_180114140
0x18002651c  mov     qword ptr [rsp+330h+pftDueTime.dwLowDateTime], rax
0x180026521  xor     r9d, r9d; msWindowLength
0x180026524  xor     r8d, r8d; msPeriod
0x180026527  lea     rdx, [rsp+330h+pftDueTime]; pftDueTime
0x18002652c  mov     rcx, cs:pti; pti
0x180026533  call    cs:__imp_SetThreadpoolTimer
0x180026539  nop
0x18002653a  xor     ebx, ebx
0x18002653c  mov     [rbp+230h+var_288], ebx
0x18002653f  mov     [rbp+230h+var_284], bl
0x180026542  mov     [rbp+230h+var_248], bl
0x180026545  mov     [rbp+230h+var_260], ebx
0x180026548  lea     rax, aIdbIdbcursorCo; "IDB_IDBCursor_continue"
0x18002654f  mov     [rbp+230h+var_258], rax
0x180026553  mov     [rbp+230h+var_250], rbx
0x180026557  mov     [rbp+230h+var_240], ebx
0x18002655a  xorps   xmm0, xmm0
0x18002655d  movdqa  xmmword ptr [rbp+230h+lpMem], xmm0
0x180026565  xorps   xmm1, xmm1
0x180026568  xor     eax, eax
0x18002656a  movups  [rbp+230h+var_238], xmm1
0x18002656e  movups  [rbp+230h+var_228], xmm1
0x180026572  movups  [rbp+230h+var_218], xmm1
0x180026576  movups  [rbp+230h+var_208], xmm1
0x18002657a  movups  [rbp+230h+var_1F8], xmm1
0x18002657e  movups  [rbp+230h+var_1E8], xmm1
0x180026582  movups  [rbp+230h+var_1D8], xmm1
0x180026586  movups  [rbp+230h+var_1C8], xmm1
0x18002658a  movups  [rbp+230h+var_1B8], xmm1
0x18002658e  mov     [rbp+230h+var_1A8], rax
0x180026595  mov     r12d, 1
0x18002659b  mov     [rbp+230h+var_190], r12d
0x1800265a2  mov     [rbp+230h+var_188], rax
0x1800265a9  lea     rax, [rbp+230h+var_288]
0x1800265ad  mov     [rbp+230h+var_180], rax
0x1800265b4  mov     [rbp+230h+Block], rbx
0x1800265bb  mov     [rbp+230h+var_170], rbx
0x1800265c2  lea     rax, [rbp+230h+var_290]
0x1800265c6  mov     [rbp+230h+var_168], rax
0x1800265cd  mov     [rbp+230h+var_160], rbx
0x1800265d4  mov     [rbp+230h+var_158], ebx
0x1800265da  lea     rax, [rbp+230h+var_260]
0x1800265de  mov     [rbp+230h+var_150], rax
0x1800265e5  mov     [rbp+230h+var_148], bl
0x1800265eb  lea     rax, ??_7IDB_IDBCursor_continue@IndexedDbTraceLogging@@6B@; const IndexedDbTraceLogging::IDB_IDBCursor_continue::`vftable'
0x1800265f2  mov     [rbp+230h+var_290], rax
0x1800265f6  movzx   r9d, r15b; unsigned __int8
0x1800265fa  mov     r8, rsi; struct __MIDL_RPCIndexedDB_0001 *
0x1800265fd  mov     rdx, r13; void *
0x180026600  lea     rcx, [rbp+230h+var_290]; this
0x180026604  call    ?StartActivity@IDB_IDBCursor_continue@IndexedDbTraceLogging@@QEAAXPEAXPEBU__MIDL_RPCIndexedDB_0001@@E@Z; IndexedDbTraceLogging::IDB_IDBCursor_continue::StartActivity(void *,__MIDL_RPCIndexedDB_0001 const *,uchar)
0x180026609  nop
0x18002660a  mov     [rdi], rbx
0x18002660d  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180026614  test    r13, r13
0x180026617  jnz     loc_180026867
0x18002661d  mov     edi, 80070057h
0x180026622  mov     edx, edi
0x180026624  lea     rcx, [rbp+230h+var_290]
0x180026628  call    ?Stop@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002662d  jmp     loc_180026706
0x180026632  mov     ecx, r15d; size
0x180026635  call    MIDL_user_allocate
0x18002663a  test    rax, rax
0x18002663d  jz      loc_1800271E3
0x180026643  xor     edx, edx
0x180026645  mov     rcx, [rsp+330h+SRWLock]
0x18002664a  mov     [r12+8], ecx
0x18002664f  mov     [r12+10h], rax
0x180026654  mov     rcx, [rsp+330h+Source]
0x180026659  mov     [rsp+330h+pAptQualifier], edx
0x18002665d  test    edx, edx
0x18002665f  js      short loc_18002667D
0x180026661  mov     edx, [r12+8]
0x180026666  add     rdx, rdx; DestinationSize
0x180026669  mov     r9, r15; SourceSize
0x18002666c  mov     r8, rcx; Source
0x18002666f  mov     rcx, [r12+10h]; Destination
0x180026674  call    memcpy_s_4
0x180026679  mov     edx, [rsp+330h+pAptQualifier]
0x18002667d  mov     rcx, [rbp+238h]; this
0x180026684  test    edx, edx
0x180026686  js      loc_1800271F2
0x18002668c  mov     r15, qword ptr [rsp+330h+pftDueTime.dwLowDateTime]
0x180026691  test    edi, edi
0x180026693  js      short loc_1800266A2
0x180026695  mov     rax, rbx
0x180026698  xor     ebx, ebx
0x18002669a  mov     rcx, [rsp+330h+var_2C0]
0x18002669f  mov     [rcx], rax
0x1800266a2  test    rbx, rbx
0x1800266a5  jnz     loc_180027207
0x1800266ab  lea     rcx, [rsp+330h+var_2B8]; this
0x1800266b0  call    ??1CTransactionThreadScope@CIndexedDBServerTransaction@@QEAA@XZ; CIndexedDBServerTransaction::CTransactionThreadScope::~CTransactionThreadScope(void)
0x1800266b5  lea     rbx, [r13+10h]
0x1800266b9  cmp     [rsp+330h+pAptType], 0
0x1800266be  jz      short loc_1800266CE
0x1800266c0  test    rbx, rbx
0x1800266c3  jz      short loc_1800266CE
0x1800266c5  mov     rcx, rbx; lpCriticalSection
0x1800266c8  call    cs:__imp_LeaveCriticalSection
0x1800266ce  mov     [rsp+330h+pAptType], 0
0x1800266d6  test    edi, edi
0x1800266d8  js      loc_180027223
0x1800266de  mov     rax, [r15]
0x1800266e1  mov     rcx, r15
0x1800266e4  mov     rax, [rax+8]
0x1800266e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266ed  test    edi, edi
0x1800266ef  js      loc_180026622
0x1800266f5  mov     rax, [rsp+330h+var_2C0]
0x1800266fa  mov     rdx, [rax]; struct __MIDL_RPCIndexedDB_0009 *
0x1800266fd  lea     rcx, [rbp+230h+var_290]; this
0x180026701  call    ?Stop@IDB_IDBCursor_continue@IndexedDbTraceLogging@@QEAAXPEBU__MIDL_RPCIndexedDB_0009@@@Z; IndexedDbTraceLogging::IDB_IDBCursor_continue::Stop(__MIDL_RPCIndexedDB_0009 const *)
0x180026706  lea     rax, ??_7IDB_IDBCursor_continue@IndexedDbTraceLogging@@6B@; const IndexedDbTraceLogging::IDB_IDBCursor_continue::`vftable'
0x18002670d  mov     [rbp+230h+var_290], rax
0x180026711  cmp     [rbp+230h+Block], 0
0x180026719  jnz     loc_18002724B
0x18002671f  mov     rcx, [rbp+230h+var_180]
0x180026726  cmp     dword ptr [rcx], 1
0x180026729  jz      loc_180027284
0x18002672f  cmp     [rbp+230h+var_158], 0
0x180026736  jnz     loc_180026DF3
0x18002673c  mov     rcx, [rbp+230h+Block]
0x180026743  test    rcx, rcx
0x180026746  jnz     loc_1800272AD
0x18002674c  xor     r15d, r15d
0x18002674f  mov     rcx, [rbp+230h+lpMem]
0x180026756  test    rcx, rcx
0x180026759  jnz     loc_1800272E9
0x18002675f  cmp     [rbp+230h+var_248], 0
0x180026763  jnz     loc_18002731F
0x180026769  mov     [rbp+230h+var_250], r15
0x18002676d  cmp     [rbp+230h+var_288], 1
0x180026771  jz      loc_180027340
0x180026777  mov     [rbp+230h+var_288], 3
0x18002677e  lock xadd cs:qword_180114130, rsi
0x180026787  cmp     rsi, 1
0x18002678b  jnz     short loc_1800267A3
0x18002678d  xor     r9d, r9d; msWindowLength
0x180026790  xor     r8d, r8d; msPeriod
0x180026793  xor     edx, edx; pftDueTime
0x180026795  mov     rcx, cs:pti; pti
0x18002679c  call    cs:__imp_SetThreadpoolTimer
0x1800267a2  nop
0x1800267a3  lea     rbx, word_1800D6108
0x1800267aa  mov     [rsp+330h+pAptType], r15d
0x1800267af  mov     [rsp+330h+pAptQualifier], r15d
0x1800267b4  lea     rdx, [rsp+330h+pAptQualifier]; pAptQualifier
0x1800267b9  lea     rcx, [rsp+330h+pAptType]; pAptType
0x1800267be  call    cs:__imp_CoGetApartmentType
0x1800267c4  test    eax, eax
0x1800267c6  jnz     short loc_18002681B
0x1800267c8  mov     ecx, [rsp+330h+pAptType]
0x1800267cc  cmp     ecx, 1
0x1800267cf  jnz     loc_18002735D
0x1800267d5  lea     r14, aMta; "MTA"
0x1800267dc  cmp     [rsp+330h+pAptQualifier], ecx
0x1800267e0  lea     rax, aMtaImplicit; "MTA Implicit"
0x1800267e7  cmovz   r14, rax
0x1800267eb  mov     qword ptr [rsp+330h+var_310], r14
0x1800267f0  mov     r9, rbx
0x1800267f3  lea     r8, aSS_1; "%s %s"
0x1800267fa  mov     edx, 80h; unsigned __int64
0x1800267ff  lea     rcx, [rbp+230h+var_140]; unsigned __int16 *
0x180026806  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002680b  lea     rdx, [rbp+230h+var_140]
0x180026812  test    eax, eax
0x180026814  cmovs   rdx, rbx
0x180026818  mov     rbx, rdx
0x18002681b  call    cs:__imp_GetCurrentThread
0x180026821  mov     rcx, rax; hThread
0x180026824  mov     rdx, rbx; lpThreadDescription
0x180026827  call    cs:__imp_SetThreadDescription
0x18002682d  call    cs:__imp_IsDebuggerPresent
0x180026833  test    eax, eax
0x180026835  jnz     loc_1800273D7
0x18002683b  mov     eax, edi
0x18002683d  mov     rcx, [rbp+230h+var_40]
0x180026844  xor     rcx, rsp; StackCookie
0x180026847  call    __security_check_cookie
0x18002684c  mov     rbx, [rsp+330h+arg_0]
0x180026854  add     rsp, 300h
0x18002685b  pop     r15
0x18002685d  pop     r14
0x18002685f  pop     r13
0x180026861  pop     r12
0x180026863  pop     rdi
0x180026864  pop     rsi
0x180026865  pop     rbp
0x180026866  retn
0x180026867  mov     qword ptr [rsp+330h+pftDueTime.dwLowDateTime], rbx
0x18002686c  lea     rcx, [rsp+330h+pftDueTime]; struct ICallerIdentity **
0x180026871  call    ?GetCallerId@CIndexedDBServerConnectionsMgr@@SAJPEAPEAUICallerIdentity@@@Z; CIndexedDBServerConnectionsMgr::GetCallerId(ICallerIdentity * *)
0x180026876  test    eax, eax
0x180026878  js      loc_180026DBB
0x18002687e  movzx   eax, byte ptr [r13+38h]
0x180026883  nop
0x180026884  mov     r15, qword ptr [rsp+330h+pftDueTime.dwLowDateTime]
0x180026889  test    al, al
0x18002688b  jz      short loc_1800268A4
0x18002688d  mov     rcx, [r13+8]
0x180026891  mov     rax, [rcx]
0x180026894  mov     rdx, r15
0x180026897  mov     rax, [rax+10h]
0x18002689b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268a0  test    eax, eax
0x1800268a2  jz      short loc_1800268AE
0x1800268a4  mov     edi, 80070005h
0x1800268a9  jmp     loc_1800266DE
0x1800268ae  mov     rdx, [r13+8]
0x1800268b2  mov     rax, [r15]
0x1800268b5  mov     rdi, [rax+28h]
0x1800268b9  mov     rcx, [rdx]
0x1800268bc  mov     rax, [rcx+28h]
0x1800268c0  mov     rcx, rdx
0x1800268c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268c8  movzx   ebx, al
0x1800268cb  mov     rcx, r15
0x1800268ce  mov     rax, rdi
0x1800268d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268d6  cmp     bl, al
0x1800268d8  jnz     short loc_1800268A4
0x1800268da  mov     rax, [rsp+330h+var_2C0]
0x1800268df  xor     ecx, ecx
0x1800268e1  mov     [rax], rcx
0x1800268e4  lea     rbx, [r13+10h]
0x1800268e8  mov     [rsp+330h+pAptType], ecx
0x1800268ec  test    rbx, rbx
0x1800268ef  jz      short loc_1800268FF
0x1800268f1  mov     rcx, rbx; lpCriticalSection
0x1800268f4  call    cs:__imp_EnterCriticalSection
0x1800268fa  mov     [rsp+330h+pAptType], r12d
0x1800268ff  mov     edi, 80070005h
0x180026904  movzx   eax, byte ptr [r13+38h]
0x180026909  nop
  ... truncated ...
```
