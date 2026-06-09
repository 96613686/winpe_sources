# CWbemNamespace::PutInstance(IWbemClassObject *,long,IWbemContext *,IWbemCallResult * *)

- ea: `0x1800458a0`
- end: `0x1800462cb`
- name: `?PutInstance@CWbemNamespace@@UEAAJPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAPEAUIWbemCallResult@@@Z`
- size: `2603`
- prototype: `__int64 __fastcall(CWbemNamespace *this, struct IWbemClassObject *, unsigned int, struct IWbemContext *, struct IWbemCallResult **)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000b140`
- `0x180020870`
- `0x180020c90`
- `0x18003cdb8`
- `0x18003cfe0`
- `0x180044658`
- `0x1800458a0`
- `0x1800469a4`
- `0x180047ed0`
- `0x180048a50`
- `0x18005d98c`
- `0x18005fbbc`
- `0x1800842f0`
- `0x1800a1d8c`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800459a2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800459a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180045989`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180045989`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18004596c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180045b38`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180045ba8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180045c10`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180045f82`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180045fa5`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180046015`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800460be`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18004596c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180045b38`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180045ba8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180045c10`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180045f82`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180045fa5`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180046015`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800460be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045f95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045f95`
- `wbemcomn!IsNtSetupRunning` at `0x180045973`
- `wbemcomn!IsNtSetupRunning` at `0x180045973`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180045a71`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180045a71`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180045a9e`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180045a9e`
- `wbemcomn!GetMemLogObject` at `0x180045b5e`
- `wbemcomn!GetMemLogObject` at `0x180045bb3`
- `wbemcomn!GetMemLogObject` at `0x180045c72`
- `wbemcomn!GetMemLogObject` at `0x180045d4c`
- `wbemcomn!GetMemLogObject` at `0x180045e48`
- `wbemcomn!GetMemLogObject` at `0x180045ecf`
- `wbemcomn!GetMemLogObject` at `0x180045f30`
- `wbemcomn!GetMemLogObject` at `0x180045fc1`
- `wbemcomn!GetMemLogObject` at `0x180046056`
- `wbemcomn!GetMemLogObject` at `0x18004613c`
- `wbemcomn!GetMemLogObject` at `0x180046185`
- `wbemcomn!GetMemLogObject` at `0x1800461d4`
- `wbemcomn!GetMemLogObject` at `0x18004625d`
- `wbemcomn!GetMemLogObject` at `0x180045b5e`
- `wbemcomn!GetMemLogObject` at `0x180045bb3`
- `wbemcomn!GetMemLogObject` at `0x180045c72`
- `wbemcomn!GetMemLogObject` at `0x180045d4c`
- `wbemcomn!GetMemLogObject` at `0x180045e48`
- `wbemcomn!GetMemLogObject` at `0x180045ecf`
- `wbemcomn!GetMemLogObject` at `0x180045f30`
- `wbemcomn!GetMemLogObject` at `0x180045fc1`
- `wbemcomn!GetMemLogObject` at `0x180046056`
- `wbemcomn!GetMemLogObject` at `0x18004613c`
- `wbemcomn!GetMemLogObject` at `0x180046185`
- `wbemcomn!GetMemLogObject` at `0x1800461d4`
- `wbemcomn!GetMemLogObject` at `0x18004625d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045b70`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045bc0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045c7f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045d59`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045e58`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045edc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045f40`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045fd3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046066`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046149`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046195`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800461e1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004626a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045b70`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045bc0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045c7f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045d59`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045e58`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045edc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045f40`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045fd3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046066`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046149`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046195`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800461e1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004626a`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180046120`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180046120`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall CWbemNamespace::PutInstance(
        CWbemNamespace *this,
        struct IWbemClassObject *a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IWbemCallResult **a5)
{
  struct IWbemCallResult **v8; // r15
  CWbemNamespace *v9; // rcx
  int v10; // r8d
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  HANDLE CurrentThread; // rax
  struct IWbemContext *NewContext; // rsi
  struct CSynchronousSink *v16; // rax
  struct CSynchronousSink *v17; // r14
  int v18; // eax
  int v19; // r8d
  __int64 v20; // rcx
  unsigned int v21; // r15d
  __int64 result; // rax
  CMemoryLog *v23; // rax
  CMemoryLog *v24; // rax
  CMemoryLog *v25; // rax
  CClientCnt *v26; // rcx
  struct IWbemContext *v27; // r14
  struct _IWmiFinalizer *v28; // rsi
  int v29; // r14d
  CMemoryLog *v30; // rax
  int v31; // r14d
  CMemoryLog *MemLogObject; // rax
  unsigned int v33; // esi
  CClientCnt *v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // r9
  __int64 v37; // rdx
  CMemoryLog *v38; // rax
  CMemoryLog *v39; // rax
  CMemoryLog *v40; // rax
  CMemoryLog *v41; // rax
  CMemoryLog *v42; // rax
  CMemoryLog *v43; // rax
  CMemoryLog *v44; // rax
  CMemoryLog *v45; // rax
  CMemoryLog *v46; // rax
  CMemoryLog *v47; // rax
  CMemoryLog *v48; // rax
  int v49; // [rsp+40h] [rbp-88h] BYREF
  struct IWbemContext *v50; // [rsp+48h] [rbp-80h] BYREF
  struct _IWmiFinalizer *v51; // [rsp+50h] [rbp-78h] BYREF
  int v52; // [rsp+58h] [rbp-70h]
  __int64 v53; // [rsp+60h] [rbp-68h]
  IErrorInfo *perrinfo; // [rsp+68h] [rbp-60h] BYREF
  struct CSynchronousSink *v55; // [rsp+70h] [rbp-58h] BYREF
  struct _IWmiFinalizer *v56; // [rsp+78h] [rbp-50h] BYREF
  __int64 v57; // [rsp+80h] [rbp-48h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp-40h] BYREF
  int v59; // [rsp+90h] [rbp-38h]
  struct IWbemContext *v61; // [rsp+E8h] [rbp+20h] BYREF

  v61 = a4;
  if ( (unsigned int)IsCallFromLowIntegrityClient() )
  {
    MemLogObject = GetMemLogObject();
    v33 = -2147217405;
    CMemoryLog::Write(MemLogObject, -2147217405);
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v33;
    }
    v35 = 749;
    v36 = 2147749891LL;
    goto LABEL_75;
  }
  v8 = a5;
  if ( a5 && *a5 )
  {
    ((void (__fastcall *)(_QWORD))(*a5)->lpVtbl->Release)(*a5);
    *v8 = 0;
  }
  v49 = CWbemNamespace::CheckNs(this);
  if ( v49 < 0 )
  {
    v25 = GetMemLogObject();
    CMemoryLog::Write(v25, v49);
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v49;
    }
    v37 = 750;
    goto LABEL_84;
  }
  v11 = CWbemNamespace::AdjustCtx(v9, &v61, v10);
  v49 = v11;
  if ( v11 < 0 )
  {
    v38 = GetMemLogObject();
    CMemoryLog::Write(v38, v49);
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v49;
    }
    v37 = 751;
LABEL_84:
    WPP_SF_d(*((_QWORD *)v26 + 2), v37, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)v49);
    return (unsigned int)v49;
  }
  if ( (a3 & 0xFFFCFFEC) != 0 )
  {
    v39 = GetMemLogObject();
    v33 = -2147217400;
    CMemoryLog::Write(v39, -2147217400);
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v33;
    }
    v35 = 752;
    v36 = 2147749896LL;
LABEL_75:
    WPP_SF_d(*((_QWORD *)v34 + 2), v35, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v36);
    return v33;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_Dql(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, a3, a2, *((_DWORD *)this + 76));
    }
    LODWORD(v50) = a3 & 0x10;
    if ( !v8 )
    {
      if ( (a3 & 0x10) != 0 )
      {
        v43 = GetMemLogObject();
        CMemoryLog::Write(v43, -2147217400);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            759,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            2147749896LL);
        }
        return 2147749896LL;
      }
      v56 = (struct _IWmiFinalizer *)1;
      TlsSetValue(g_SecFlagTlsIndex, (LPVOID)1);
      if ( IsNtSetupRunning() )
        TlsSetValue(g_SecFlagTlsIndex, 0);
      TokenHandle = 0;
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
      {
        CloseHandle(TokenHandle);
      }
      else if ( !CWbemQueue::GetCurrentRequest() )
      {
        NewContext = v61;
        if ( v61 )
        {
          ((void (__fastcall *)(struct IWbemContext *))v61->lpVtbl->AddRef)(v61);
          goto LABEL_16;
        }
        NewContext = ConfigMgr::GetNewContext();
        if ( NewContext )
        {
LABEL_16:
          v50 = NewContext;
          v16 = CSynchronousSink::Create(0);
          v17 = v16;
          if ( v16 )
          {
            (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v16 + 8LL))(v16);
            v55 = v17;
            v18 = a3 & 0x10000;
            if ( !*((_DWORD *)this + 30) && v18 )
            {
              v41 = GetMemLogObject();
              CMemoryLog::Write(v41, -2147217400);
              if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  756,
                  WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                  2147749896LL);
              }
              CReleaseMe::release((CReleaseMe *)&v55);
              CReleaseMe::release((CReleaseMe *)&v50);
              TlsSetValue(g_SecFlagTlsIndex, (LPVOID)1);
              return 2147749896LL;
            }
            else
            {
              v19 = a3 - 49152;
              if ( !v18 )
                v19 = a3;
              v49 = CWbemNamespace::Exec_PutInstance(this, a2, v19, NewContext, v17);
              if ( v49 < 0 )
              {
                v24 = GetMemLogObject();
                CMemoryLog::Write(v24, v49);
                if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    757,
                    WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                    (unsigned int)v49);
                }
                (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v17 + 16LL))(v17);
                v55 = 0;
                if ( NewContext )
                  ((void (__fastcall *)(struct IWbemContext *))NewContext->lpVtbl->Release)(NewContext);
                v50 = 0;
                TlsSetValue(g_SecFlagTlsIndex, (LPVOID)1);
                return (unsigned int)v49;
              }
              else
              {
                CSynchronousSink::Block(v17);
                v53 = 0;
                CInCritSec::CInCritSec((CInCritSec *)&v57, (struct _RTL_CRITICAL_SECTION *)v17 + 4);
                v49 = *((_DWORD *)v17 + 8);
                v53 = *((_QWORD *)v17 + 6);
                v20 = *((_QWORD *)v17 + 6);
                if ( v20 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
                CInCritSec::~CInCritSec((CInCritSec *)&v57);
                v57 = v53;
                if ( v53 )
                {
                  perrinfo = 0;
                  (**(void (__fastcall ***)(__int64, GUID *, IErrorInfo **))v53)(v53, &IID_IErrorInfo, &perrinfo);
                  SetErrorInfo(0, perrinfo);
                  ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
                }
                v21 = v49;
                if ( v49 < 0 )
                {
                  v42 = GetMemLogObject();
                  CMemoryLog::Write(v42, v49);
                  v21 = v49;
                }
                if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    758,
                    WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                    v21);
                  v21 = v49;
                }
                if ( v53 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
                v57 = 0;
                (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v17 + 16LL))(v17);
                v55 = 0;
                if ( NewContext )
                  ((void (__fastcall *)(struct IWbemContext *))NewContext->lpVtbl->Release)(NewContext);
                v50 = 0;
                TlsSetValue(g_SecFlagTlsIndex, (LPVOID)1);
                return v21;
              }
            }
          }
          else
          {
            v23 = GetMemLogObject();
            CMemoryLog::Write(v23, -2147217402);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                755,
                WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                2147749894LL);
            }
            if ( NewContext )
              ((void (__fastcall *)(struct IWbemContext *))NewContext->lpVtbl->Release)(NewContext);
            v50 = 0;
            TlsSetValue(g_SecFlagTlsIndex, (LPVOID)1);
            return 2147749894LL;
          }
        }
        v40 = GetMemLogObject();
        CMemoryLog::Write(v40, -2147217402);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            754,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            2147749894LL);
        }
        TlsSetValue(g_SecFlagTlsIndex, (LPVOID)1);
        return 2147749894LL;
      }
      TlsSetValue(g_SecFlagTlsIndex, (LPVOID)1);
    }
    v56 = 0;
    v27 = v61;
    v49 = CWbemNamespace::CreateSyncFinalizer(this, v61, &v56);
    if ( v49 >= 0 )
    {
      v28 = v56;
      v51 = v56;
      v52 = v8 != 0 ? 33554435 : 16777219;
      if ( __eh34_try(0, 1) )
      {
        __eh34_scope_strut(1);
        v49 = CWbemNamespace::_PutInstanceAsync(
                this,
                v8 != 0 ? 33554435 : 16777219,
                v56,
                0,
                a2,
                a3 & 0xFFFFFFEF,
                v27,
                0);
      }
      if ( __eh34_catch(1) )
      {
        if ( __eh34_catch_type(1, &SafeIntException `RTTI Type Descriptor', 0) )
        {
          _InterlockedIncrement(&ExceptionCounter::s_Count);
          v46 = GetMemLogObject();
          CMemoryLog::Write(v46, -2147217398);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              761,
              WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
              2147749898LL);
          }
          v59 = -2147217398;
          __eh34_try_continuation(1, &SafeIntException `RTTI Type Descriptor', &loc_1800462A6);
          CReleaseMe::release((CReleaseMe *)&v51);
          return 2147749898LL;
        }
      }
      v29 = v49;
      if ( v49 < 0 )
      {
        v30 = GetMemLogObject();
        CMemoryLog::Write(v30, v49);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            762,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            (unsigned int)v49);
        }
        if ( v28 )
          (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v28 + 16LL))(v28);
        v51 = 0;
        return (unsigned int)v49;
      }
      if ( !(_DWORD)v50 )
      {
        v31 = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, __int64, int *))(*(_QWORD *)v28 + 104LL))(
                v28,
                0,
                0xFFFFFFFFLL,
                &v49);
        if ( v31 < 0 )
        {
          if ( v28 )
            (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v28 + 16LL))(v28);
          v51 = 0;
          return (unsigned int)v31;
        }
        v29 = v49;
      }
      if ( v8 )
      {
        v29 = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, GUID *, struct IWbemCallResult **))(*(_QWORD *)v28 + 88LL))(
                v28,
                0,
                &IID_IWbemCallResult,
                v8);
        v49 = v29;
      }
      if ( v29 < 0 )
      {
        v45 = GetMemLogObject();
        CMemoryLog::Write(v45, v49);
        v29 = v49;
      }
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          763,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)v29);
        v29 = v49;
      }
      if ( v28 )
        (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v28 + 16LL))(v28);
      v51 = 0;
      return (unsigned int)v29;
    }
    v44 = GetMemLogObject();
    CMemoryLog::Write(v44, v49);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        760,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)v49);
    }
    result = (unsigned int)v49;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &CX_MemoryException `RTTI Type Descriptor', 0) )
    {
      _InterlockedIncrement(&ExceptionCounter::s_Count);
      v47 = GetMemLogObject();
      CMemoryLog::Write(v47, -2147217402);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          764,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          2147749894LL);
      }
      result = 2147749894LL;
      __eh34_try_continuation(0, &CX_MemoryException `RTTI Type Descriptor', &loc_1800462BA);
      return result;
    }
    if ( __eh34_catch_type(0, &CX_Exception `RTTI Type Descriptor', 0) )
    {
      _InterlockedIncrement(&ExceptionCounter::s_Count);
      v48 = GetMemLogObject();
      CMemoryLog::Write(v48, -2147217398);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          765,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          2147749898LL);
      }
      result = 2147749898LL;
      __eh34_try_continuation(0, &CX_Exception `RTTI Type Descriptor', &loc_1800462C1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800458a0  mov     rax, rsp
0x1800458a3  mov     [rax+8], rbx
0x1800458a7  mov     [rax+18h], rsi
0x1800458ab  mov     [rax+20h], r9
0x1800458af  mov     [rax+10h], rdx
0x1800458b3  push    rdi
0x1800458b4  push    r12
0x1800458b6  push    r13
0x1800458b8  push    r14
0x1800458ba  push    r15
0x1800458bc  sub     rsp, 0A0h
0x1800458c3  mov     r13d, r8d
0x1800458c6  mov     rsi, rdx
0x1800458c9  mov     r12, rcx
0x1800458cc  call    ?IsCallFromLowIntegrityClient@@YAHXZ; IsCallFromLowIntegrityClient(void)
0x1800458d1  xor     r14d, r14d
0x1800458d4  test    eax, eax
0x1800458d6  jnz     loc_180045E48
0x1800458dc  mov     r15, [rsp+0C8h+arg_20]
0x1800458e4  test    r15, r15
0x1800458e7  jnz     loc_180045C52
0x1800458ed  mov     rcx, r12; this
0x1800458f0  call    ?CheckNs@CWbemNamespace@@QEAAJXZ; CWbemNamespace::CheckNs(void)
0x1800458f5  mov     [rsp+0C8h+var_88], eax
0x1800458f9  test    eax, eax
0x1800458fb  js      loc_180045C72
0x180045901  lea     rdx, [rsp+0C8h+arg_18]; struct IWbemContext **
0x180045909  call    ?AdjustCtx@CWbemNamespace@@QEAAJAEAPEAUIWbemContext@@J@Z; CWbemNamespace::AdjustCtx(IWbemContext * &,long)
0x18004590e  mov     [rsp+0C8h+var_88], eax
0x180045912  test    eax, eax
0x180045914  js      loc_180045ECF
0x18004591a  test    r13d, 0FFFCFFECh
0x180045921  jnz     loc_180045F30
0x180045927  lea     rdi, WPP_GLOBAL_Control
0x18004592e  mov     rcx, cs:WPP_GLOBAL_Control
0x180045935  mov     ebx, 1
0x18004593a  cmp     rcx, rdi
0x18004593d  jnz     loc_180045C1D
0x180045943  mov     eax, r13d
0x180045946  and     eax, 10h
0x180045949  mov     dword ptr [rsp+0C8h+var_80], eax
0x18004594d  test    r15, r15
0x180045950  jnz     loc_180045CB6
0x180045956  test    eax, eax
0x180045958  jnz     loc_180046185
0x18004595e  mov     [rsp+0C8h+var_50], rbx
0x180045963  mov     rdx, rbx; lpTlsValue
0x180045966  mov     ecx, cs:?g_SecFlagTlsIndex@@3VCTLS@@A; dwTlsIndex
0x18004596c  call    cs:__imp_TlsSetValue
0x180045972  nop
0x180045973  call    cs:__imp_?IsNtSetupRunning@@YAHXZ; IsNtSetupRunning(void)
0x180045979  test    eax, eax
0x18004597b  jnz     loc_180045F7A
0x180045981  mov     [rsp+0C8h+TokenHandle], r14
0x180045989  call    cs:__imp_GetCurrentThread
0x18004598f  mov     rcx, rax; ThreadHandle
0x180045992  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x18004599a  mov     r8d, ebx; OpenAsSelf
0x18004599d  mov     edx, 20008h; DesiredAccess
0x1800459a2  call    cs:__imp_OpenThreadToken
0x1800459a8  test    eax, eax
0x1800459aa  jnz     loc_180045F8D
0x1800459b0  call    ?GetCurrentRequest@CWbemQueue@@SAPEAVCWbemRequest@@XZ; CWbemQueue::GetCurrentRequest(void)
0x1800459b5  test    rax, rax
0x1800459b8  jnz     loc_180045F9C
0x1800459be  mov     rsi, [rsp+0C8h+arg_18]
0x1800459c6  test    rsi, rsi
0x1800459c9  jz      loc_180045FB0
0x1800459cf  mov     rax, [rsi]
0x1800459d2  mov     rcx, rsi
0x1800459d5  mov     rax, [rax+8]
0x1800459d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800459de  mov     [rsp+0C8h+var_80], rsi
0x1800459e3  xor     ecx, ecx; struct IWbemObjectSinkEx *
0x1800459e5  call    ?Create@CSynchronousSink@@SAPEAV1@PEAUIWbemObjectSinkEx@@@Z; CSynchronousSink::Create(IWbemObjectSinkEx *)
0x1800459ea  mov     r14, rax
0x1800459ed  xor     r15d, r15d
0x1800459f0  test    rax, rax
0x1800459f3  jz      loc_180045B5E
0x1800459f9  mov     rax, [rax]
0x1800459fc  mov     rcx, r14
0x1800459ff  mov     rax, [rax+8]
0x180045a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a08  mov     [rsp+0C8h+var_58], r14
0x180045a0d  mov     eax, r13d
0x180045a10  and     eax, 10000h
0x180045a15  cmp     [r12+78h], r15d
0x180045a1a  jnz     short loc_180045A24
0x180045a1c  test    eax, eax
0x180045a1e  jnz     loc_180046056
0x180045a24  lea     r8d, [r13-0C000h]
0x180045a2b  test    eax, eax
0x180045a2d  cmovz   r8d, r13d; int
0x180045a31  mov     [rsp+0C8h+var_A8], r14; struct CBasicObjectSink *
0x180045a36  mov     r9, rsi; struct IWbemContext *
0x180045a39  mov     rdx, [rsp+0C8h+arg_8]; struct IWbemClassObject *
0x180045a41  mov     rcx, r12; this
0x180045a44  call    ?Exec_PutInstance@CWbemNamespace@@QEAAJPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z; CWbemNamespace::Exec_PutInstance(IWbemClassObject *,long,IWbemContext *,CBasicObjectSink *)
0x180045a49  mov     [rsp+0C8h+var_88], eax
0x180045a4d  test    eax, eax
0x180045a4f  js      loc_180045BB3
0x180045a55  mov     rcx, r14; this
0x180045a58  call    ?Block@CSynchronousSink@@QEAAXXZ; CSynchronousSink::Block(void)
0x180045a5d  mov     [rsp+0C8h+var_68], r15
0x180045a62  lea     rdx, [r14+0A0h]
0x180045a69  lea     rcx, [rsp+0C8h+var_48]
0x180045a71  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180045a77  nop
0x180045a78  mov     eax, [r14+20h]
0x180045a7c  mov     [rsp+0C8h+var_88], eax
0x180045a80  mov     rax, [r14+30h]
0x180045a84  mov     [rsp+0C8h+var_68], rax
0x180045a89  mov     rcx, [r14+30h]
0x180045a8d  test    rcx, rcx
0x180045a90  jnz     loc_180045CA5
0x180045a96  lea     rcx, [rsp+0C8h+var_48]
0x180045a9e  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180045aa4  mov     r12, [rsp+0C8h+var_68]
0x180045aa9  mov     [rsp+0C8h+var_48], r12
0x180045ab1  mov     rcx, [rsp+0C8h+var_68]
0x180045ab6  test    rcx, rcx
0x180045ab9  jnz     loc_1800460FD
0x180045abf  mov     r15d, [rsp+0C8h+var_88]
0x180045ac4  xor     r13d, r13d
0x180045ac7  test    r15d, r15d
0x180045aca  js      loc_18004613C
0x180045ad0  mov     rcx, cs:WPP_GLOBAL_Control
0x180045ad7  cmp     rcx, rdi
0x180045ada  jz      short loc_180045AE5
0x180045adc  test    [rcx+1Ch], bl
0x180045adf  jnz     loc_180046159
0x180045ae5  test    r12, r12
0x180045ae8  jz      short loc_180045AFA
0x180045aea  mov     rax, [r12]
0x180045aee  mov     rcx, r12
0x180045af1  mov     rax, [rax+10h]
0x180045af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045afa  mov     [rsp+0C8h+var_48], r13
0x180045b02  mov     rax, [r14]
0x180045b05  mov     rcx, r14
0x180045b08  mov     rax, [rax+10h]
0x180045b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b11  mov     [rsp+0C8h+var_58], r13
0x180045b16  test    rsi, rsi
0x180045b19  jz      short loc_180045B2A
0x180045b1b  mov     rcx, [rsi]
0x180045b1e  mov     rax, [rcx+10h]
0x180045b22  mov     rcx, rsi
0x180045b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b2a  mov     [rsp+0C8h+var_80], r13
0x180045b2f  mov     rdx, rbx; lpTlsValue
0x180045b32  mov     ecx, cs:?g_SecFlagTlsIndex@@3VCTLS@@A; dwTlsIndex
0x180045b38  call    cs:__imp_TlsSetValue
0x180045b3e  mov     eax, r15d
0x180045b41  lea     r11, [rsp+0C8h+var_28]
0x180045b49  mov     rbx, [r11+30h]
0x180045b4d  mov     rsi, [r11+40h]
0x180045b51  mov     rsp, r11
0x180045b54  pop     r15
0x180045b56  pop     r14
0x180045b58  pop     r13
0x180045b5a  pop     r12
0x180045b5c  pop     rdi
0x180045b5d  retn
0x180045b5e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180045b64  mov     r14d, 80041006h
0x180045b6a  mov     edx, r14d
0x180045b6d  mov     rcx, rax
0x180045b70  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180045b76  mov     rcx, cs:WPP_GLOBAL_Control
0x180045b7d  cmp     rcx, rdi
0x180045b80  jnz     loc_180046023
0x180045b86  test    rsi, rsi
0x180045b89  jz      short loc_180045B9A
0x180045b8b  mov     rax, [rsi]
0x180045b8e  mov     rcx, rsi
0x180045b91  mov     rax, [rax+10h]
0x180045b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b9a  mov     [rsp+0C8h+var_80], r15
0x180045b9f  mov     rdx, rbx; lpTlsValue
0x180045ba2  mov     ecx, cs:?g_SecFlagTlsIndex@@3VCTLS@@A; dwTlsIndex
0x180045ba8  call    cs:__imp_TlsSetValue
0x180045bae  mov     eax, r14d
0x180045bb1  jmp     short loc_180045B41
0x180045bb3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180045bb9  mov     edx, [rsp+0C8h+var_88]
0x180045bbd  mov     rcx, rax
0x180045bc0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180045bc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180045bcd  cmp     rcx, rdi
0x180045bd0  jnz     loc_1800460CB
0x180045bd6  mov     edi, [rsp+0C8h+var_88]
0x180045bda  mov     rax, [r14]
0x180045bdd  mov     rcx, r14
0x180045be0  mov     rax, [rax+10h]
0x180045be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045be9  mov     [rsp+0C8h+var_58], r15
0x180045bee  test    rsi, rsi
0x180045bf1  jz      short loc_180045C02
0x180045bf3  mov     rcx, [rsi]
0x180045bf6  mov     rax, [rcx+10h]
0x180045bfa  mov     rcx, rsi
0x180045bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c02  mov     [rsp+0C8h+var_80], r15
0x180045c07  mov     rdx, rbx; lpTlsValue
0x180045c0a  mov     ecx, cs:?g_SecFlagTlsIndex@@3VCTLS@@A; dwTlsIndex
0x180045c10  call    cs:__imp_TlsSetValue
0x180045c16  mov     eax, edi
0x180045c18  jmp     loc_180045B41
0x180045c1d  test    [rcx+1Ch], bl
0x180045c20  jz      loc_180045943
0x180045c26  cmp     byte ptr [rcx+19h], 5
0x180045c2a  jb      loc_180045943
0x180045c30  mov     eax, [r12+130h]
0x180045c38  mov     [rsp+0C8h+var_A0], eax
0x180045c3c  mov     [rsp+0C8h+var_A8], rsi
0x180045c41  mov     r9d, r13d
0x180045c44  mov     rcx, [rcx+10h]
0x180045c48  call    WPP_SF_Dql
0x180045c4d  jmp     loc_180045943
0x180045c52  mov     rcx, [r15]
0x180045c55  test    rcx, rcx
0x180045c58  jz      loc_1800458ED
0x180045c5e  mov     rax, [rcx]
0x180045c61  mov     rax, [rax+10h]
0x180045c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c6a  mov     [r15], r14
0x180045c6d  jmp     loc_1800458ED
0x180045c72  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180045c78  mov     edx, [rsp+0C8h+var_88]
0x180045c7c  mov     rcx, rax
0x180045c7f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180045c85  lea     rdi, WPP_GLOBAL_Control
0x180045c8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180045c93  cmp     rcx, rdi
0x180045c96  jnz     loc_180045EB0
0x180045c9c  mov     eax, [rsp+0C8h+var_88]
0x180045ca0  jmp     loc_180045B41
0x180045ca5  mov     rax, [rcx]
0x180045ca8  mov     rax, [rax+8]
0x180045cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045cb1  jmp     loc_180045A96
0x180045cb6  mov     [rsp+0C8h+var_50], r14
0x180045cbb  lea     r8, [rsp+0C8h+var_50]; struct _IWmiFinalizer **
0x180045cc0  mov     r14, [rsp+0C8h+arg_18]
0x180045cc8  mov     rdx, r14; struct IWbemContext *
0x180045ccb  mov     rcx, r12; this
0x180045cce  call    ?CreateSyncFinalizer@CWbemNamespace@@QEAAJPEAUIWbemContext@@PEAPEAU_IWmiFinalizer@@@Z; CWbemNamespace::CreateSyncFinalizer(IWbemContext *,_IWmiFinalizer * *)
0x180045cd3  mov     [rsp+0C8h+var_88], eax
0x180045cd7  test    eax, eax
0x180045cd9  js      loc_1800461D4
0x180045cdf  mov     rsi, [rsp+0C8h+var_50]
0x180045ce4  mov     [rsp+0C8h+var_78], rsi
0x180045ce9  mov     [rsp+0C8h+var_70], 3
0x180045cf1  mov     rax, r15
0x180045cf4  neg     rax
0x180045cf7  sbb     edx, edx
0x180045cf9  and     edx, 1000000h
0x180045cff  add     edx, 1000003h; unsigned int
0x180045d05  mov     [rsp+0C8h+var_70], edx
0x180045d09  and     r13d, 0FFFFFFEFh
0x180045d0d  mov     [rsp+0C8h+var_90], 0; struct IWbemObjectSink *
0x180045d16  mov     [rsp+0C8h+var_98], r14; struct IWbemContext *
0x180045d1b  mov     [rsp+0C8h+var_A0], r13d; int
0x180045d20  mov     rax, [rsp+0C8h+arg_8]
0x180045d28  mov     [rsp+0C8h+var_A8], rax; struct IWbemClassObject *
0x180045d2d  xor     r9d, r9d; struct _IWmiCoreHandle *
0x180045d30  mov     r8, rsi; struct _IWmiFinalizer *
0x180045d33  mov     rcx, r12; this
0x180045d36  call    ?_PutInstanceAsync@CWbemNamespace@@MEAAJKPEAU_IWmiFinalizer@@PEAU_IWmiCoreHandle@@PEAUIWbemClassObject@@JPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z; CWbemNamespace::_PutInstanceAsync(ulong,_IWmiFinalizer *,_IWmiCoreHandle *,IWbemClassObject *,long,IWbemContext *,IWbemObjectSink *)
0x180045d3b  mov     [rsp+0C8h+var_88], eax
0x180045d3f  mov     r14d, [rsp+0C8h+var_88]
0x180045d44  xor     r12d, r12d
0x180045d47  test    r14d, r14d
0x180045d4a  jns     short loc_180045D93
0x180045d4c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180045d52  mov     edx, [rsp+0C8h+var_88]
0x180045d56  mov     rcx, rax
0x180045d59  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180045d5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180045d66  cmp     rcx, rdi
0x180045d69  jnz     loc_180046221
0x180045d6f  mov     ebx, [rsp+0C8h+var_88]
0x180045d73  test    rsi, rsi
0x180045d76  jz      short loc_180045D87
0x180045d78  mov     rdx, [rsi]
0x180045d7b  mov     rcx, rsi
0x180045d7e  mov     rax, [rdx+10h]
0x180045d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d87  mov     [rsp+0C8h+var_78], r12
0x180045d8c  mov     eax, ebx
0x180045d8e  jmp     loc_180045B41
0x180045d93  cmp     dword ptr [rsp+0C8h+var_80], r12d
0x180045d98  jz      short loc_180045E02
0x180045d9a  test    r15, r15
0x180045d9d  jnz     short loc_180045DDE
0x180045d9f  test    r14d, r14d
0x180045da2  js      loc_18004625D
0x180045da8  mov     rcx, cs:WPP_GLOBAL_Control
0x180045daf  cmp     rcx, rdi
  ... truncated ...
```
