# CWbemNamespace::GetObjectW(ushort * const,long,IWbemContext *,IWbemClassObject * *,IWbemCallResult * *)

- ea: `0x18001e9a0`
- end: `0x18001f6bf`
- name: `?GetObjectW@CWbemNamespace@@UEAAJQEAGJPEAUIWbemContext@@PEAPEAUIWbemClassObject@@PEAPEAUIWbemCallResult@@@Z`
- size: `3359`
- prototype: `__int64 __usercall@<rax>(CWbemNamespace *__hidden this@<rcx>, unsigned __int16 *const@<rdx>, int@<r8d>, struct IWbemContext *@<r9>, struct IWbemClassObject **, struct IWbemCallResult **)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800237fc`

## callees

- `0x180007fb0`
- `0x18000ae2c`
- `0x18000b140`
- `0x18001e9a0`
- `0x18001f6d0`
- `0x180020870`
- `0x180020c90`
- `0x180020f20`
- `0x18003ad40`
- `0x18003cdb8`
- `0x18003cfe0`
- `0x18005fbbc`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001eaff`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001eaff`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001eb13`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001eb13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001eae6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001eae6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001eacc`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001ecde`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001ed02`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001ef09`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001ef68`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001f302`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001f378`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001f3ed`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001f4a4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001eacc`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001ecde`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001ed02`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001ef09`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001ef68`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001f302`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001f378`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001f3ed`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001f4a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ecf0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ecf0`
- `wbemcomn!IsNtSetupRunning` at `0x18001ead3`
- `wbemcomn!IsNtSetupRunning` at `0x18001ead3`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18001ec39`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18001ec39`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18001ebc2`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18001ebc2`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18001ebf2`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18001ebf2`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18001ec1f`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18001ec1f`
- `wbemcomn!GetMemLogObject` at `0x18001ee9c`
- `wbemcomn!GetMemLogObject` at `0x18001efd0`
- `wbemcomn!GetMemLogObject` at `0x18001f10d`
- `wbemcomn!GetMemLogObject` at `0x18001f15c`
- `wbemcomn!GetMemLogObject` at `0x18001f1ca`
- `wbemcomn!GetMemLogObject` at `0x18001f215`
- `wbemcomn!GetMemLogObject` at `0x18001f26d`
- `wbemcomn!GetMemLogObject` at `0x18001f2a9`
- `wbemcomn!GetMemLogObject` at `0x18001f31e`
- `wbemcomn!GetMemLogObject` at `0x18001f388`
- `wbemcomn!GetMemLogObject` at `0x18001f429`
- `wbemcomn!GetMemLogObject` at `0x18001f4b4`
- `wbemcomn!GetMemLogObject` at `0x18001f50b`
- `wbemcomn!GetMemLogObject` at `0x18001f609`
- `wbemcomn!GetMemLogObject` at `0x18001f661`
- `wbemcomn!GetMemLogObject` at `0x18001ee9c`
- `wbemcomn!GetMemLogObject` at `0x18001efd0`
- `wbemcomn!GetMemLogObject` at `0x18001f10d`
- `wbemcomn!GetMemLogObject` at `0x18001f15c`
- `wbemcomn!GetMemLogObject` at `0x18001f1ca`
- `wbemcomn!GetMemLogObject` at `0x18001f215`
- `wbemcomn!GetMemLogObject` at `0x18001f26d`
- `wbemcomn!GetMemLogObject` at `0x18001f2a9`
- `wbemcomn!GetMemLogObject` at `0x18001f31e`
- `wbemcomn!GetMemLogObject` at `0x18001f388`
- `wbemcomn!GetMemLogObject` at `0x18001f429`
- `wbemcomn!GetMemLogObject` at `0x18001f4b4`
- `wbemcomn!GetMemLogObject` at `0x18001f50b`
- `wbemcomn!GetMemLogObject` at `0x18001f609`
- `wbemcomn!GetMemLogObject` at `0x18001f661`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001eeac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001efe0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f11d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f16c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f1da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f223`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f27b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f2b7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f32c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f396`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f437`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f4c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f51b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f619`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f671`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001eeac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001efe0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f11d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f16c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f1da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f223`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f27b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f2b7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f32c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f396`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f437`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f4c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f51b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f619`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f671`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001efa5`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001efa5`

## string_xrefs

- `0x18001ea47`: `Read (GetObject)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWbemNamespace::GetObjectW(
        CWbemNamespace *this,
        unsigned __int16 *const a2,
        int a3,
        struct IWbemContext *a4,
        struct IWbemClassObject **a5,
        __int64 a6)
{
  struct IWbemClassObject **v9; // rdi
  struct IWbemCallResult **v10; // r13
  int v12; // r8d
  HANDLE CurrentThread; // rax
  _QWORD *Value; // rax
  struct IWbemContext *NewContext; // r12
  struct CSynchronousSink *v16; // rax
  struct CSynchronousSink *v17; // r14
  __int64 v18; // rcx
  void (__fastcall ***v19)(_QWORD, GUID *, IErrorInfo **); // r15
  int v20; // ebx
  struct IWbemClassObject *v21; // rax
  __int64 result; // rax
  struct _IWmiFinalizer *v23; // r12
  unsigned int v24; // edx
  int v25; // ebx
  int v26; // ebx
  int v27; // eax
  CMemoryLog *v28; // rax
  unsigned int v29; // ebx
  CMemoryLog *v30; // rax
  unsigned int v31; // ebx
  CMemoryLog *v32; // rax
  CMemoryLog *v33; // rax
  unsigned int v34; // ebx
  CMemoryLog *v35; // rax
  CClientCnt *v36; // rcx
  __int64 v37; // rdx
  CMemoryLog *v38; // rax
  CMemoryLog *v39; // rax
  CClientCnt *v40; // rcx
  __int64 v41; // rdx
  CMemoryLog *v42; // rax
  CMemoryLog *v43; // rax
  CMemoryLog *v44; // rax
  CMemoryLog *v45; // rax
  CMemoryLog *v46; // rax
  CMemoryLog *v47; // rax
  unsigned int v48; // ebx
  CMemoryLog *v49; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v51; // rax
  CMemoryLog *v52; // rax
  CMemoryLog *v53; // rax
  bool v54; // [rsp+28h] [rbp-90h]
  struct IWbemContext *v55; // [rsp+48h] [rbp-70h] BYREF
  struct CSynchronousSink *v56; // [rsp+50h] [rbp-68h] BYREF
  void (__fastcall ***v57)(_QWORD, GUID *, IErrorInfo **); // [rsp+58h] [rbp-60h]
  IErrorInfo *perrinfo; // [rsp+60h] [rbp-58h] BYREF
  void (__fastcall ***v59)(_QWORD, GUID *, IErrorInfo **); // [rsp+68h] [rbp-50h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-48h] BYREF
  struct _IWmiFinalizer *v61; // [rsp+78h] [rbp-40h] BYREF
  int v62; // [rsp+80h] [rbp-38h]
  char v63[8]; // [rsp+88h] [rbp-30h] BYREF
  struct IWbemContext *v65; // [rsp+D8h] [rbp+20h] BYREF

  v65 = a4;
  v9 = a5;
  if ( a5 && *a5 )
  {
    ((void (__fastcall *)(_QWORD))(*a5)->lpVtbl->Release)(*a5);
    *v9 = 0;
  }
  v10 = (struct IWbemCallResult **)a6;
  if ( a6 && *(_QWORD *)a6 )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)a6 + 16LL))(*(_QWORD *)a6);
    *v10 = 0;
  }
  if ( g_bDontAllowNewConnections || *((_DWORD *)this + 7) )
  {
    LODWORD(a5) = -2147217357;
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, (_DWORD)a5);
    v36 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)a5;
    }
    v37 = 778;
    goto LABEL_163;
  }
  LODWORD(a5) = 0;
  LODWORD(a5) = CWbemNamespace::AdjustCtx(this, &v65);
  if ( (int)a5 < 0 )
  {
    v35 = GetMemLogObject();
    CMemoryLog::Write(v35, (_DWORD)a5);
    v36 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)a5;
    }
    v37 = 779;
LABEL_163:
    WPP_SF_d(*((_QWORD *)v36 + 2), v37, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)a5);
    return (unsigned int)a5;
  }
  if ( CWbemNamespace::InnerAllowedWithSD(
         this,
         (CWbemNamespace *)((char *)this + 216),
         1u,
         L"Read (GetObject)",
         a2,
         v54,
         1) )
  {
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_Sdql(*((_QWORD *)WPP_GLOBAL_Control + 2), 781, v12, (_DWORD)a2, a3, (char)v9, *((_DWORD *)this + 76));
    }
    if ( v9 )
      *v9 = 0;
    if ( (a3 & 0xFFFDFDEF) != 0 )
    {
      v39 = GetMemLogObject();
      CMemoryLog::Write(v39, -2147217400);
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749896LL;
      }
      v41 = 782;
      goto LABEL_121;
    }
    if ( (a3 & 0x10) != 0 && !v10 )
    {
      v42 = GetMemLogObject();
      CMemoryLog::Write(v42, -2147217400);
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749896LL;
      }
      v41 = 783;
LABEL_121:
      WPP_SF_d(*((_QWORD *)v40 + 2), v41, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
      return 2147749896LL;
    }
    try
    {
      if ( (a3 & 0x10) == 0 && !v10 )
      {
        a6 = 1;
        TlsSetValue(g_SecFlagTlsIndex, (LPVOID)1);
        if ( IsNtSetupRunning() )
          TlsSetValue(g_SecFlagTlsIndex, 0);
        TokenHandle = 0;
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
        {
          CloseHandle(TokenHandle);
        }
        else
        {
          Value = TlsGetValue(g_QueueTlsIndex);
          if ( !Value || !Value[1] )
          {
            NewContext = v65;
            if ( v65 )
            {
              ((void (__fastcall *)(struct IWbemContext *))v65->lpVtbl->AddRef)(v65);
            }
            else
            {
              NewContext = ConfigMgr::GetNewContext();
              if ( !NewContext )
              {
                v43 = GetMemLogObject();
                CMemoryLog::Write(v43, -2147217402);
                if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    784,
                    WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                    2147749894LL);
                }
                TlsSetValue(g_SecFlagTlsIndex, (LPVOID)1);
                return 2147749894LL;
              }
            }
            v55 = NewContext;
            v16 = CSynchronousSink::Create(0);
            v17 = v16;
            if ( !v16 )
            {
              v44 = GetMemLogObject();
              CMemoryLog::Write(v44, -2147217402);
              if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  785,
                  WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                  2147749894LL);
              }
              CReleaseMe::release((CReleaseMe *)&v55);
              TlsSetValue(g_SecFlagTlsIndex, (LPVOID)1);
              return 2147749894LL;
            }
            (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v16 + 8LL))(v16);
            v56 = v17;
            LODWORD(a5) = CWbemNamespace::Exec_GetObject(this, a2, a3, NewContext, v17);
            if ( (int)a5 < 0 )
            {
              v28 = GetMemLogObject();
              CMemoryLog::Write(v28, (_DWORD)a5);
              if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  786,
                  WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                  (unsigned int)a5);
              }
              v29 = (unsigned int)a5;
              (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v17 + 16LL))(v17);
              v56 = 0;
              if ( NewContext )
                ((void (__fastcall *)(struct IWbemContext *))NewContext->lpVtbl->Release)(NewContext);
              v55 = 0;
              TlsSetValue(g_SecFlagTlsIndex, (LPVOID)1);
              return v29;
            }
            if ( *((_DWORD *)v17 + 8) == -2147217398 )
              CCoreQueue::QueueWaitForSingleObject(*((void **)v17 + 3), 0xFFFFFFFF);
            v57 = 0;
            CInCritSec::CInCritSec((CInCritSec *)v63, (struct _RTL_CRITICAL_SECTION *)v17 + 4);
            LODWORD(a5) = *((_DWORD *)v17 + 8);
            v57 = (void (__fastcall ***)(_QWORD, GUID *, IErrorInfo **))*((_QWORD *)v17 + 6);
            v18 = *((_QWORD *)v17 + 6);
            if ( v18 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
            CInCritSec::~CInCritSec((CInCritSec *)v63);
            v19 = v57;
            v59 = v57;
            if ( v57 )
            {
              perrinfo = 0;
              (**v57)(v57, &IID_IErrorInfo, &perrinfo);
              SetErrorInfo(0, perrinfo);
              ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
            }
            v20 = (int)a5;
            if ( (int)a5 >= 0 )
            {
              if ( CFlexArray::Size((struct CSynchronousSink *)((char *)v17 + 64)) != 1 )
              {
                v45 = GetMemLogObject();
                CMemoryLog::Write(v45, -2147217398);
                if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    787,
                    WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                    2147749898LL);
                }
                CReleaseMe::release((CReleaseMe *)&v59);
                CReleaseMe::release((CReleaseMe *)&v56);
                CReleaseMe::release((CReleaseMe *)&v55);
                TlsSetValue(g_SecFlagTlsIndex, (LPVOID)1);
                return 2147749898LL;
              }
              if ( v9 )
              {
                v21 = (struct IWbemClassObject *)CFlexArray::GetAt((struct CSynchronousSink *)((char *)v17 + 64), 0);
                *v9 = v21;
                ((void (__fastcall *)(struct IWbemClassObject *))v21->lpVtbl->AddRef)(v21);
              }
              v20 = (int)a5;
            }
            if ( v20 == -2147217406 )
            {
              if ( v19 )
                ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, IErrorInfo **)))(*v19)[2])(v19);
              v59 = 0;
              (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v17 + 16LL))(v17);
              v56 = 0;
              if ( NewContext )
                ((void (__fastcall *)(struct IWbemContext *))NewContext->lpVtbl->Release)(NewContext);
              v55 = 0;
              TlsSetValue(g_SecFlagTlsIndex, (LPVOID)1);
              return 2147749890LL;
            }
            else
            {
              if ( v20 < 0 )
              {
                v32 = GetMemLogObject();
                CMemoryLog::Write(v32, (_DWORD)a5);
                v20 = (int)a5;
              }
              if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  788,
                  WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                  (unsigned int)v20);
                v20 = (int)a5;
              }
              if ( v19 )
                ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, IErrorInfo **)))(*v19)[2])(v19);
              v59 = 0;
              (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v17 + 16LL))(v17);
              v56 = 0;
              if ( NewContext )
                ((void (__fastcall *)(struct IWbemContext *))NewContext->lpVtbl->Release)(NewContext);
              v55 = 0;
              TlsSetValue(g_SecFlagTlsIndex, (LPVOID)1);
              return (unsigned int)v20;
            }
          }
        }
        TlsSetValue(g_SecFlagTlsIndex, (LPVOID)1);
      }
      v61 = 0;
      LODWORD(a5) = CWbemNamespace::CreateSyncFinalizer(this, v65, &v61);
      if ( (int)a5 < 0 )
      {
        v46 = GetMemLogObject();
        CMemoryLog::Write(v46, (_DWORD)a5);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            789,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            (unsigned int)a5);
        }
        return (unsigned int)a5;
      }
      v23 = v61;
      a6 = (__int64)v61;
      if ( v10 )
        v24 = 33554433;
      else
        v24 = 16777217;
      try
      {
        LODWORD(a5) = CWbemNamespace::_GetObjectAsync(this, v24, v61, 0, a2, a3 & 0xFFFFFFEF, v65, 0);
      }
      catch ( SafeIntException )
      {
        _InterlockedIncrement(&ExceptionCounter::s_Count);
        v51 = GetMemLogObject();
        CMemoryLog::Write(v51, -2147217398);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            790,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            2147749898LL);
        }
        v62 = -2147217398;
        CReleaseMe::release((CReleaseMe *)&a6);
        return 2147749898LL;
      }
      v25 = (int)a5;
      if ( (int)a5 < 0 )
      {
        v47 = GetMemLogObject();
        CMemoryLog::Write(v47, (_DWORD)a5);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            791,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            (unsigned int)a5);
        }
        v48 = (unsigned int)a5;
        CReleaseMe::release((CReleaseMe *)&a6);
        return v48;
      }
      if ( (a3 & 0x10) == 0 )
      {
        v26 = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, __int64, struct IWbemClassObject ***))(*(_QWORD *)v23 + 104LL))(
                v23,
                0,
                0xFFFFFFFFLL,
                &a5);
        if ( v26 < 0 )
        {
          if ( v23 )
            (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v23 + 16LL))(v23);
          a6 = 0;
          return (unsigned int)v26;
        }
        v25 = (int)a5;
        if ( (int)a5 < 0 )
        {
          v30 = GetMemLogObject();
          CMemoryLog::Write(v30, (_DWORD)a5);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              792,
              WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
              (unsigned int)a5);
          }
          v31 = (unsigned int)a5;
          if ( v23 )
            (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v23 + 16LL))(v23);
          a6 = 0;
          return v31;
        }
      }
      if ( v10 )
      {
        v25 = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, GUID *, struct IWbemCallResult **))(*(_QWORD *)v23 + 88LL))(
                v23,
                0,
                &IID_IWbemCallResult,
                v10);
        LODWORD(a5) = v25;
        if ( v25 < 0 )
        {
          v33 = GetMemLogObject();
          CMemoryLog::Write(v33, (_DWORD)a5);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              793,
              WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
              (unsigned int)a5);
          }
          v34 = (unsigned int)a5;
          if ( v23 )
            (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v23 + 16LL))(v23);
          a6 = 0;
          return v34;
        }
        if ( !v9 || (a3 & 0x10) != 0 )
          goto LABEL_62;
        v27 = ((__int64 (__fastcall *)(struct IWbemCallResult *, __int64, struct IWbemClassObject **))(*v10)->lpVtbl->GetResultObject)(
                *v10,
                0xFFFFFFFFLL,
                v9);
      }
      else
      {
        if ( !v9 || (a3 & 0x10) != 0 )
          goto LABEL_62;
        v27 = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, GUID *, struct IWbemClassObject **))(*(_QWORD *)v23 + 88LL))(
                v23,
                0,
                &IID_IWbemClassObject,
                v9);
      }
      LODWORD(a5) = v27;
      v25 = v27;
LABEL_62:
      if ( v25 < 0 )
      {
        v49 = GetMemLogObject();
        CMemoryLog::Write(v49, (_DWORD)a5);
        v25 = (int)a5;
      }
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          794,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)v25);
        v25 = (int)a5;
      }
      if ( v23 )
        (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v23 + 16LL))(v23);
      a6 = 0;
      result = (unsigned int)v25;
    }
    catch ( CX_MemoryException )
    {
      _InterlockedIncrement(&ExceptionCounter::s_Count);
      v52 = GetMemLogObject();
      CMemoryLog::Write(v52, -2147217402);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          795,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          2147749894LL);
      }
      return 2147749894LL;
    }
    catch ( CX_Exception )
    {
      _InterlockedIncrement(&ExceptionCounter::s_Count);
      v53 = GetMemLogObject();
      CMemoryLog::Write(v53, -2147217398);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          796,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          2147749898LL);
      }
      return 2147749898LL;
    }
    return result;
  }
  v38 = GetMemLogObject();
  CMemoryLog::Write(v38, -2147217405);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 780, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749891LL);
  }
  return 2147749891LL;
}

```

## disassembly

```asm
0x18001e9a0  mov     [rsp+arg_0], rbx
0x18001e9a5  mov     [rsp+arg_10], rsi
0x18001e9aa  mov     [rsp+arg_18], r9
0x18001e9af  mov     [rsp+arg_8], rdx
0x18001e9b4  push    rdi
0x18001e9b5  push    r12
0x18001e9b7  push    r13
0x18001e9b9  push    r14
0x18001e9bb  push    r15
0x18001e9bd  sub     rsp, 90h
0x18001e9c4  mov     r15d, r8d
0x18001e9c7  mov     r14, rdx
0x18001e9ca  mov     rbx, rcx
0x18001e9cd  mov     rdi, [rsp+0B8h+arg_20]
0x18001e9d5  test    rdi, rdi
0x18001e9d8  jz      short loc_18001E9E6
0x18001e9da  mov     rcx, [rdi]
0x18001e9dd  test    rcx, rcx
0x18001e9e0  jnz     loc_18001F1B4
0x18001e9e6  xor     esi, esi
0x18001e9e8  mov     r13, [rsp+0B8h+arg_28]
0x18001e9f0  test    r13, r13
0x18001e9f3  jnz     loc_18001F0EB
0x18001e9f9  cmp     cs:?g_bDontAllowNewConnections@@3HA, 0; int g_bDontAllowNewConnections
0x18001ea00  jnz     loc_18001F656
0x18001ea06  cmp     dword ptr [rbx+1Ch], 0
0x18001ea0a  jnz     loc_18001F656
0x18001ea10  mov     dword ptr [rsp+0B8h+arg_20], esi
0x18001ea17  lea     rdx, [rsp+0B8h+arg_18]; struct IWbemContext **
0x18001ea1f  mov     rcx, rbx; this
0x18001ea22  call    ?AdjustCtx@CWbemNamespace@@QEAAJAEAPEAUIWbemContext@@J@Z; CWbemNamespace::AdjustCtx(IWbemContext * &,long)
0x18001ea27  mov     dword ptr [rsp+0B8h+arg_20], eax
0x18001ea2e  test    eax, eax
0x18001ea30  js      loc_18001F1CA
0x18001ea36  lea     rdx, [rbx+0D8h]; struct CNtSecurityDescriptor *
0x18001ea3d  mov     byte ptr [rsp+0B8h+var_88], 1; bool
0x18001ea42  mov     [rsp+0B8h+var_98], r14; unsigned __int16 *
0x18001ea47  lea     r9, aReadGetobject; "Read (GetObject)"
0x18001ea4e  mov     r8d, 1; unsigned int
0x18001ea54  mov     rcx, rbx; this
0x18001ea57  call    ?InnerAllowedWithSD@CWbemNamespace@@QEAA_NPEAVCNtSecurityDescriptor@@KPEBG1_N2@Z; CWbemNamespace::InnerAllowedWithSD(CNtSecurityDescriptor *,ulong,ushort const *,ushort const *,bool,bool)
0x18001ea5c  test    al, al
0x18001ea5e  jz      loc_18001F215
0x18001ea64  lea     r12, WPP_GLOBAL_Control
0x18001ea6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ea72  cmp     rcx, r12
0x18001ea75  jz      short loc_18001EA81
0x18001ea77  test    byte ptr [rcx+1Ch], 1
0x18001ea7b  jnz     loc_18001F028
0x18001ea81  test    rdi, rdi
0x18001ea84  jz      short loc_18001EA89
0x18001ea86  mov     [rdi], rsi
0x18001ea89  test    r15d, 0FFFDFDEFh
0x18001ea90  jnz     loc_18001F26D
0x18001ea96  mov     r14d, r15d
0x18001ea99  and     r14d, 10h
0x18001ea9d  jnz     loc_18001F2A0
0x18001eaa3  test    r14d, r14d
0x18001eaa6  jnz     loc_18001ED08
0x18001eaac  test    r13, r13
0x18001eaaf  jnz     loc_18001ED08
0x18001eab5  mov     [rsp+0B8h+arg_28], 1
0x18001eac1  mov     edx, 1; lpTlsValue
0x18001eac6  mov     ecx, cs:?g_SecFlagTlsIndex@@3VCTLS@@A; dwTlsIndex
0x18001eacc  call    cs:__imp_TlsSetValue
0x18001ead2  nop
0x18001ead3  call    cs:__imp_?IsNtSetupRunning@@YAHXZ; IsNtSetupRunning(void)
0x18001ead9  test    eax, eax
0x18001eadb  jnz     loc_18001F2FA
0x18001eae1  mov     [rsp+0B8h+TokenHandle], rsi
0x18001eae6  call    cs:__imp_GetCurrentThread
0x18001eaec  mov     rcx, rax; ThreadHandle
0x18001eaef  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x18001eaf4  mov     edx, 20008h; DesiredAccess
0x18001eaf9  mov     r8d, 1; OpenAsSelf
0x18001eaff  call    cs:__imp_OpenThreadToken
0x18001eb05  test    eax, eax
0x18001eb07  jnz     loc_18001ECEB
0x18001eb0d  mov     ecx, cs:?g_QueueTlsIndex@@3VCTLS@@A; dwTlsIndex
0x18001eb13  call    cs:__imp_TlsGetValue
0x18001eb19  test    rax, rax
0x18001eb1c  jz      short loc_18001EB29
0x18001eb1e  cmp     qword ptr [rax+8], 0
0x18001eb23  jnz     loc_18001ECF7
0x18001eb29  mov     r12, [rsp+0B8h+arg_18]
0x18001eb31  test    r12, r12
0x18001eb34  jz      loc_18001F30D
0x18001eb3a  mov     rax, [r12]
0x18001eb3e  mov     rcx, r12
0x18001eb41  mov     rax, [rax+8]
0x18001eb45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb4a  mov     [rsp+0B8h+var_70], r12
0x18001eb4f  xor     ecx, ecx; struct IWbemObjectSinkEx *
0x18001eb51  call    ?Create@CSynchronousSink@@SAPEAV1@PEAUIWbemObjectSinkEx@@@Z; CSynchronousSink::Create(IWbemObjectSinkEx *)
0x18001eb56  mov     r14, rax
0x18001eb59  test    rax, rax
0x18001eb5c  jz      loc_18001F388
0x18001eb62  mov     rax, [rax]
0x18001eb65  mov     rcx, r14
0x18001eb68  mov     rax, [rax+8]
0x18001eb6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb71  mov     [rsp+0B8h+var_68], r14
0x18001eb76  mov     [rsp+0B8h+var_98], r14; struct CBasicObjectSink *
0x18001eb7b  mov     r9, r12; struct IWbemContext *
0x18001eb7e  mov     r8d, r15d; int
0x18001eb81  mov     rdx, [rsp+0B8h+arg_8]; unsigned __int16 *
0x18001eb89  mov     rcx, rbx; this
0x18001eb8c  call    ?Exec_GetObject@CWbemNamespace@@QEAAJPEBGJPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z; CWbemNamespace::Exec_GetObject(ushort const *,long,IWbemContext *,CBasicObjectSink *)
0x18001eb91  mov     dword ptr [rsp+0B8h+arg_20], eax
0x18001eb98  test    eax, eax
0x18001eb9a  js      loc_18001EE9C
0x18001eba0  cmp     dword ptr [r14+20h], 8004100Ah
0x18001eba8  jz      loc_18001F0D8
0x18001ebae  mov     [rsp+0B8h+var_60], rsi
0x18001ebb3  lea     rdx, [r14+0A0h]
0x18001ebba  lea     rcx, [rsp+0B8h+var_30]
0x18001ebc2  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18001ebc8  nop
0x18001ebc9  mov     eax, [r14+20h]
0x18001ebcd  mov     dword ptr [rsp+0B8h+arg_20], eax
0x18001ebd4  mov     rax, [r14+30h]
0x18001ebd8  mov     [rsp+0B8h+var_60], rax
0x18001ebdd  mov     rcx, [r14+30h]
0x18001ebe1  test    rcx, rcx
0x18001ebe4  jnz     loc_18001F099
0x18001ebea  lea     rcx, [rsp+0B8h+var_30]
0x18001ebf2  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18001ebf8  mov     r15, [rsp+0B8h+var_60]
0x18001ebfd  mov     [rsp+0B8h+var_50], r15
0x18001ec02  mov     rcx, [rsp+0B8h+var_60]
0x18001ec07  test    rcx, rcx
0x18001ec0a  jnz     loc_18001EF82
0x18001ec10  mov     ebx, dword ptr [rsp+0B8h+arg_20]
0x18001ec17  test    ebx, ebx
0x18001ec19  js      short loc_18001EC5B
0x18001ec1b  lea     rcx, [r14+40h]
0x18001ec1f  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18001ec25  cmp     eax, 1
0x18001ec28  jnz     loc_18001F429
0x18001ec2e  test    rdi, rdi
0x18001ec31  jz      short loc_18001EC54
0x18001ec33  xor     edx, edx
0x18001ec35  lea     rcx, [r14+40h]
0x18001ec39  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18001ec3f  mov     rdx, rax
0x18001ec42  mov     [rdi], rax
0x18001ec45  mov     rcx, [rax]
0x18001ec48  mov     rax, [rcx+8]
0x18001ec4c  mov     rcx, rdx
0x18001ec4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec54  mov     ebx, dword ptr [rsp+0B8h+arg_20]
0x18001ec5b  cmp     ebx, 80041002h
0x18001ec61  jz      loc_18001EF16
0x18001ec67  test    ebx, ebx
0x18001ec69  js      loc_18001F10D
0x18001ec6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec76  lea     rax, WPP_GLOBAL_Control
0x18001ec7d  cmp     rcx, rax
0x18001ec80  jz      short loc_18001EC8C
0x18001ec82  test    byte ptr [rcx+1Ch], 1
0x18001ec86  jnz     loc_18001F05C
0x18001ec8c  test    r15, r15
0x18001ec8f  jz      short loc_18001ECA0
0x18001ec91  mov     rax, [r15]
0x18001ec94  mov     rcx, r15
0x18001ec97  mov     rax, [rax+10h]
0x18001ec9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eca0  mov     [rsp+0B8h+var_50], rsi
0x18001eca5  mov     rax, [r14]
0x18001eca8  mov     rcx, r14
0x18001ecab  mov     rax, [rax+10h]
0x18001ecaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecb4  mov     [rsp+0B8h+var_68], rsi
0x18001ecb9  test    r12, r12
0x18001ecbc  jz      short loc_18001ECCE
0x18001ecbe  mov     rcx, [r12]
0x18001ecc2  mov     rax, [rcx+10h]
0x18001ecc6  mov     rcx, r12
0x18001ecc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecce  mov     [rsp+0B8h+var_70], rsi
0x18001ecd3  mov     edx, 1; lpTlsValue
0x18001ecd8  mov     ecx, cs:?g_SecFlagTlsIndex@@3VCTLS@@A; dwTlsIndex
0x18001ecde  call    cs:__imp_TlsSetValue
0x18001ece4  mov     eax, ebx
0x18001ece6  jmp     loc_18001EE5E
0x18001eceb  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x18001ecf0  call    cs:__imp_CloseHandle
0x18001ecf6  nop
0x18001ecf7  mov     edx, 1; lpTlsValue
0x18001ecfc  mov     ecx, cs:?g_SecFlagTlsIndex@@3VCTLS@@A; dwTlsIndex
0x18001ed02  call    cs:__imp_TlsSetValue
0x18001ed08  mov     [rsp+0B8h+var_40], rsi
0x18001ed0d  lea     r8, [rsp+0B8h+var_40]; struct _IWmiFinalizer **
0x18001ed12  mov     rdx, [rsp+0B8h+arg_18]; struct IWbemContext *
0x18001ed1a  mov     rcx, rbx; this
0x18001ed1d  call    ?CreateSyncFinalizer@CWbemNamespace@@QEAAJPEAUIWbemContext@@PEAPEAU_IWmiFinalizer@@@Z; CWbemNamespace::CreateSyncFinalizer(IWbemContext *,_IWmiFinalizer * *)
0x18001ed22  mov     dword ptr [rsp+0B8h+arg_20], eax
0x18001ed29  test    eax, eax
0x18001ed2b  js      loc_18001F4B4
0x18001ed31  mov     r12, [rsp+0B8h+var_40]
0x18001ed36  mov     [rsp+0B8h+arg_28], r12
0x18001ed3e  mov     [rsp+0B8h+var_78], 1
0x18001ed46  test    r13, r13
0x18001ed49  jnz     loc_18001EF78
0x18001ed4f  mov     edx, 1000001h; unsigned int
0x18001ed54  mov     [rsp+0B8h+var_78], edx
0x18001ed58  and     r15d, 0FFFFFFEFh
0x18001ed5c  mov     [rsp+0B8h+var_80], rsi; struct IWbemObjectSink *
0x18001ed61  mov     rax, [rsp+0B8h+arg_18]
0x18001ed69  mov     [rsp+0B8h+var_88], rax; struct IWbemContext *
0x18001ed6e  mov     [rsp+0B8h+var_90], r15d; int
0x18001ed73  mov     rax, [rsp+0B8h+arg_8]
0x18001ed7b  mov     [rsp+0B8h+var_98], rax; unsigned __int16 *
0x18001ed80  xor     r9d, r9d; struct _IWmiCoreHandle *
0x18001ed83  mov     r8, r12; struct _IWmiFinalizer *
0x18001ed86  mov     rcx, rbx; this
0x18001ed89  call    ?_GetObjectAsync@CWbemNamespace@@MEAAJKPEAU_IWmiFinalizer@@PEAU_IWmiCoreHandle@@QEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z; CWbemNamespace::_GetObjectAsync(ulong,_IWmiFinalizer *,_IWmiCoreHandle *,ushort * const,long,IWbemContext *,IWbemObjectSink *)
0x18001ed8e  mov     dword ptr [rsp+0B8h+arg_20], eax
0x18001ed95  mov     ebx, dword ptr [rsp+0B8h+arg_20]
0x18001ed9c  test    ebx, ebx
0x18001ed9e  js      loc_18001F50B
0x18001eda4  test    r14d, r14d
0x18001eda7  jnz     short loc_18001EDE2
0x18001eda9  mov     rax, [r12]
0x18001edad  lea     r9, [rsp+0B8h+arg_20]
0x18001edb5  xor     edx, edx
0x18001edb7  mov     r8d, 0FFFFFFFFh
0x18001edbd  mov     rcx, r12
0x18001edc0  mov     rax, [rax+68h]
0x18001edc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edc9  mov     ebx, eax
0x18001edcb  test    eax, eax
0x18001edcd  js      loc_18001EE7B
0x18001edd3  mov     ebx, dword ptr [rsp+0B8h+arg_20]
0x18001edda  test    ebx, ebx
0x18001eddc  js      loc_18001EFD0
0x18001ede2  test    r13, r13
0x18001ede5  jnz     loc_18001F12F
0x18001edeb  test    rdi, rdi
0x18001edee  jz      short loc_18001EE1A
0x18001edf0  test    r14d, r14d
0x18001edf3  jnz     short loc_18001EE1A
0x18001edf5  mov     rax, [r12]
0x18001edf9  mov     r9, rdi
0x18001edfc  lea     r8, IID_IWbemClassObject
0x18001ee03  xor     edx, edx
0x18001ee05  mov     rcx, r12
0x18001ee08  mov     rax, [rax+58h]
0x18001ee0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee11  mov     dword ptr [rsp+0B8h+arg_20], eax
0x18001ee18  mov     ebx, eax
0x18001ee1a  test    ebx, ebx
0x18001ee1c  js      loc_18001F609
0x18001ee22  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee29  lea     rax, WPP_GLOBAL_Control
0x18001ee30  cmp     rcx, rax
0x18001ee33  jz      short loc_18001EE3F
0x18001ee35  test    byte ptr [rcx+1Ch], 1
0x18001ee39  jnz     loc_18001F0AA
0x18001ee3f  test    r12, r12
0x18001ee42  jz      short loc_18001EE54
0x18001ee44  mov     rcx, [r12]
0x18001ee48  mov     rax, [rcx+10h]
0x18001ee4c  mov     rcx, r12
0x18001ee4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee54  mov     [rsp+0B8h+arg_28], rsi
0x18001ee5c  mov     eax, ebx
0x18001ee5e  lea     r11, [rsp+0B8h+var_28]
0x18001ee66  mov     rbx, [r11+30h]
0x18001ee6a  mov     rsi, [r11+40h]
0x18001ee6e  mov     rsp, r11
0x18001ee71  pop     r15
0x18001ee73  pop     r14
0x18001ee75  pop     r13
0x18001ee77  pop     r12
0x18001ee79  pop     rdi
0x18001ee7a  retn
0x18001ee7b  test    r12, r12
0x18001ee7e  jz      short loc_18001EE90
0x18001ee80  mov     rdx, [r12]
0x18001ee84  mov     rcx, r12
0x18001ee87  mov     rax, [rdx+10h]
0x18001ee8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee90  mov     [rsp+0B8h+arg_28], rsi
0x18001ee98  mov     eax, ebx
0x18001ee9a  jmp     short loc_18001EE5E
0x18001ee9c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001eea2  mov     edx, dword ptr [rsp+0B8h+arg_20]
0x18001eea9  mov     rcx, rax
0x18001eeac  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001eeb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eeb9  lea     rax, WPP_GLOBAL_Control
0x18001eec0  cmp     rcx, rax
0x18001eec3  jnz     loc_18001EFC1
0x18001eec9  mov     ebx, dword ptr [rsp+0B8h+arg_20]
0x18001eed0  mov     rax, [r14]
0x18001eed3  mov     rcx, r14
0x18001eed6  mov     rax, [rax+10h]
0x18001eeda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eedf  mov     [rsp+0B8h+var_68], rsi
  ... truncated ...
```
