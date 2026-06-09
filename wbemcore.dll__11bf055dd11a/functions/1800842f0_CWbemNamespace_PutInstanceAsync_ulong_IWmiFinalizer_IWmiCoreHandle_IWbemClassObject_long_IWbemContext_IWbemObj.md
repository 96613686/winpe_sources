# CWbemNamespace::_PutInstanceAsync(ulong,_IWmiFinalizer *,_IWmiCoreHandle *,IWbemClassObject *,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x1800842f0`
- end: `0x180084a47`
- name: `?_PutInstanceAsync@CWbemNamespace@@MEAAJKPEAU_IWmiFinalizer@@PEAU_IWmiCoreHandle@@PEAUIWbemClassObject@@JPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `1879`
- prototype: `__int64 __fastcall(CWbemNamespace *this, unsigned int, struct _IWmiFinalizer *, struct _IWmiCoreHandle *, struct IWbemClassObject *, CWbemNamespace *, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800458a0`
- `0x18009fb30`

## callees

- `0x18000b140`
- `0x18000e950`
- `0x18000f474`
- `0x18003cfe0`
- `0x180041d00`
- `0x1800421ac`
- `0x180047ed0`
- `0x1800523c0`
- `0x180062ed0`
- `0x180072280`
- `0x1800842f0`
- `0x1800903d0`
- `0x1800a0a14`
- `0x1800a1ec0`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180084800`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180084800`
- `wbemcomn!GetMemLogObject` at `0x180084325`
- `wbemcomn!GetMemLogObject` at `0x1800843df`
- `wbemcomn!GetMemLogObject` at `0x180084425`
- `wbemcomn!GetMemLogObject` at `0x180084472`
- `wbemcomn!GetMemLogObject` at `0x1800844b6`
- `wbemcomn!GetMemLogObject` at `0x180084553`
- `wbemcomn!GetMemLogObject` at `0x1800845b2`
- `wbemcomn!GetMemLogObject` at `0x18008464c`
- `wbemcomn!GetMemLogObject` at `0x1800846db`
- `wbemcomn!GetMemLogObject` at `0x18008479e`
- `wbemcomn!GetMemLogObject` at `0x180084873`
- `wbemcomn!GetMemLogObject` at `0x1800848dd`
- `wbemcomn!GetMemLogObject` at `0x180084962`
- `wbemcomn!GetMemLogObject` at `0x1800849ba`
- `wbemcomn!GetMemLogObject` at `0x180084325`
- `wbemcomn!GetMemLogObject` at `0x1800843df`
- `wbemcomn!GetMemLogObject` at `0x180084425`
- `wbemcomn!GetMemLogObject` at `0x180084472`
- `wbemcomn!GetMemLogObject` at `0x1800844b6`
- `wbemcomn!GetMemLogObject` at `0x180084553`
- `wbemcomn!GetMemLogObject` at `0x1800845b2`
- `wbemcomn!GetMemLogObject` at `0x18008464c`
- `wbemcomn!GetMemLogObject` at `0x1800846db`
- `wbemcomn!GetMemLogObject` at `0x18008479e`
- `wbemcomn!GetMemLogObject` at `0x180084873`
- `wbemcomn!GetMemLogObject` at `0x1800848dd`
- `wbemcomn!GetMemLogObject` at `0x180084962`
- `wbemcomn!GetMemLogObject` at `0x1800849ba`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180084330`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800843ed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180084433`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180084480`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800844c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008455e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800845bd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180084657`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800846e6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800847a9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180084883`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800848e9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008496d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800849ca`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180084330`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800843ed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180084433`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180084480`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800844c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008455e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800845bd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180084657`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800846e6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800847a9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180084883`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800848e9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008496d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800849ca`
- `OLEAUT32!__imp_VariantInit` at `0x18008460f`
- `OLEAUT32!__imp_VariantInit` at `0x18008460f`

## string_xrefs

- `0x180084636`: `__RELPATH`
- `0x1800846c6`: `IWbemServices::PutInstance`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWbemNamespace::_PutInstanceAsync(
        CWbemNamespace *this,
        unsigned int a2,
        struct _IWmiFinalizer *a3,
        struct _IWmiCoreHandle *a4,
        struct IWbemClassObject *a5,
        CWbemNamespace *a6,
        struct IWbemContext *a7,
        struct IWbemObjectSink *a8)
{
  struct _IWmiFinalizer *v8; // r14
  __int64 v10; // rdx
  int v11; // esi
  __int64 v12; // r8
  CMemoryLog *MemLogObject; // rax
  CClientCnt *v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // esi
  struct IWbemObjectSink *v17; // r12
  struct IWbemClassObject *v18; // r13
  CMemoryLog *v19; // rax
  CClientCnt *v20; // rcx
  __int64 v21; // rdx
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  int v24; // eax
  CMemoryLog *v25; // rax
  unsigned __int64 v27; // rcx
  struct IWbemContext *v28; // r13
  CMemoryLog *v29; // rax
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  CClientCnt *v32; // rcx
  __int64 v33; // rdx
  const unsigned __int16 *bstrVal; // r12
  CMemoryLog *v35; // rax
  const wchar_t *v36; // r8
  CMemoryLog *v37; // rax
  CNamespaceReq *v38; // rax
  CNamespaceReq *v39; // rsi
  struct IWbemClassObject *v40; // rcx
  struct IWbemContext *v41; // rax
  CMemoryLog *v42; // rax
  CClientCnt *v43; // rcx
  __int64 v44; // rdx
  int inited; // r15d
  CMemoryLog *v46; // rax
  CMemoryLog *v47; // rax
  __int64 v48; // r9
  CMemoryLog *v49; // rax
  struct IWbemObjectSink **v50; // [rsp+28h] [rbp-79h]
  struct IWbemObjectSink *v51; // [rsp+30h] [rbp-71h]
  __int64 v52; // [rsp+38h] [rbp-69h]
  __int64 v53; // [rsp+48h] [rbp-59h] BYREF
  CAsyncReq_PutInstanceAsync *v54; // [rsp+50h] [rbp-51h] BYREF
  int v55; // [rsp+58h] [rbp-49h]
  struct IWbemObjectSink *v56; // [rsp+60h] [rbp-41h] BYREF
  struct IWbemObjectSink *v57; // [rsp+68h] [rbp-39h] BYREF
  struct IWbemObjectSinkEx *v58; // [rsp+70h] [rbp-31h] BYREF
  struct IWbemObjectSinkEx *v59; // [rsp+78h] [rbp-29h] BYREF
  struct _IWmiFinalizer *v60; // [rsp+80h] [rbp-21h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-19h] BYREF
  CNamespaceReq *v62; // [rsp+A0h] [rbp-1h]
  struct _IWmiFinalizer *v64; // [rsp+F8h] [rbp+57h] BYREF

  v64 = a3;
  v8 = a3;
  v11 = CWbemNamespace::CheckNs(this);
  if ( v11 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v11);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v11;
    }
    v15 = 570;
    goto LABEL_6;
  }
  v16 = (unsigned int)a6;
  if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    v18 = a5;
    v17 = a8;
  }
  else
  {
    v17 = a8;
    v18 = a5;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      WPP_SF_Dqql(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v12, (unsigned int)a6, a5, a8, *((_DWORD *)this + 76));
  }
  if ( !v8 && !v17 )
  {
    v19 = GetMemLogObject();
    CMemoryLog::Write(v19, -2147217400);
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v21 = 572;
LABEL_34:
    WPP_SF_d(*((_QWORD *)v20 + 2), v21, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
    return 2147749896LL;
  }
  if ( !v18 )
  {
    v22 = GetMemLogObject();
    CMemoryLog::Write(v22, -2147217400);
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v21 = 573;
    goto LABEL_34;
  }
  if ( (v16 & 0xFFFCFF7F) > 2 )
  {
    v23 = GetMemLogObject();
    CMemoryLog::Write(v23, -2147217400);
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v21 = 574;
    goto LABEL_34;
  }
  v24 = v16 & 0x10000;
  if ( !*((_DWORD *)this + 30) && v24 )
  {
    v25 = GetMemLogObject();
    CMemoryLog::Write(v25, -2147217400);
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v21 = 575;
    goto LABEL_34;
  }
  v27 = v16 - 49152;
  if ( !v24 )
    v27 = v16;
  v55 = v27;
  v28 = a7;
  if ( a7 )
    CWbemNamespace::AdjustPutContext((CWbemNamespace *)v27, a7);
  v56 = 0;
  if ( !v8 )
  {
    v11 = CWbemNamespace::CreateAsyncFinalizer(this, v28, v17, &v64, &v56);
    if ( v11 < 0 )
    {
      v29 = GetMemLogObject();
      CMemoryLog::Write(v29, v11);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)v11;
      }
      v15 = 576;
      goto LABEL_6;
    }
    v8 = v64;
LABEL_53:
    v57 = v56;
    v60 = v8;
    VariantInit(&pvarg);
    v11 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a5->lpVtbl->Get)(
            a5,
            L"__RELPATH",
            0,
            &pvarg,
            0,
            0);
    if ( v11 < 0 )
    {
      v31 = GetMemLogObject();
      CMemoryLog::Write(v31, v11);
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_59;
      }
      v33 = 578;
LABEL_58:
      WPP_SF_d(*((_QWORD *)v32 + 2), v33, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)v11);
LABEL_59:
      _variant_t::~_variant_t(&pvarg);
LABEL_110:
      CReleaseMe::release((CReleaseMe *)&v60);
      CReleaseMe::release((CReleaseMe *)&v57);
      return (unsigned int)v11;
    }
    LOWORD(v53) = 0;
    bstrVal = (const unsigned __int16 *)&v53;
    if ( pvarg.vt == 8 && pvarg.llVal )
      bstrVal = pvarg.bstrVal;
    v11 = CWbemNamespace::PublishInfo(this, L"IWbemServices::PutInstance", bstrVal, v8, v28);
    if ( v11 < 0 )
    {
      v35 = GetMemLogObject();
      CMemoryLog::Write(v35, v11);
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_59;
      }
      v33 = 579;
      goto LABEL_58;
    }
    if ( *((_DWORD *)this + 76) != -1 && g_cntWinmgmtTraceLogging )
    {
      v36 = L"Async";
      if ( !a8 )
        v36 = L"(Semi)Sync";
      LODWORD(v52) = *((_DWORD *)this + 76);
      LODWORD(v51) = *((_DWORD *)this + 95);
      LODWORD(v50) = v55;
      WinmgmtTelemetrylogging(*((_DWORD *)v8 + 181), 9, v36, bstrVal, v50, v51, v52, *((_QWORD *)this + 11), v53);
    }
    _variant_t::~_variant_t(&pvarg);
    v58 = 0;
    v11 = ((__int64 (__fastcall *)(struct IWbemObjectSink *, GUID *, struct IWbemObjectSinkEx **))v56->lpVtbl->QueryInterface)(
            v56,
            &IID_IWbemObjectSinkEx,
            &v58);
    if ( v11 < 0 )
    {
      v37 = GetMemLogObject();
      CMemoryLog::Write(v37, v11);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          580,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)v11);
      }
      goto LABEL_110;
    }
    v59 = v58;
    v54 = 0;
    v38 = (CNamespaceReq *)CWin32DefaultArena::WbemMemAlloc(0x70u);
    v39 = v38;
    v62 = v38;
    if ( v38 )
    {
      CNamespaceReq::CNamespaceReq(v38, this, v58, v28, 0);
      *(_QWORD *)v39 = &CAsyncReq_PutInstanceAsync::`vftable';
      v40 = a5;
      *((_QWORD *)v39 + 12) = a5;
      *((_DWORD *)v39 + 26) = v55;
      ((void (__fastcall *)(struct IWbemClassObject *))v40->lpVtbl->AddRef)(v40);
    }
    else
    {
      v39 = 0;
    }
    if ( v39 )
    {
      std::unique_ptr<CAsyncReq_PutInstanceAsync>::_Delete(&v54);
      v54 = v39;
      v41 = (struct IWbemContext *)*((_QWORD *)v39 + 5);
      if ( v41 )
      {
        inited = CWbemNamespace::InitNewTask(this, v39, v8, a2, v41, a8);
        if ( inited < 0 )
        {
          v46 = GetMemLogObject();
          CMemoryLog::Write(v46, inited);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              583,
              WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
              (unsigned int)inited);
          }
          std::unique_ptr<CAsyncReq_PutInstanceAsync>::_Delete(&v54);
          CReleaseMe::release((CReleaseMe *)&v59);
          v11 = inited;
          goto LABEL_110;
        }
        CReleaseMe::release((CReleaseMe *)&v57);
        v11 = ConfigMgr::EnqueueRequest(v39);
        if ( v11 >= 0 )
        {
          v54 = 0;
          v43 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_109;
          }
          v44 = 585;
        }
        else
        {
          (*(void (__fastcall **)(struct _IWmiFinalizer *, _QWORD))(*(_QWORD *)v8 + 112LL))(v8, 0);
          v47 = GetMemLogObject();
          CMemoryLog::Write(v47, v11);
          v43 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_109;
          }
          v44 = 584;
        }
        v48 = (unsigned int)v11;
        goto LABEL_108;
      }
      v42 = GetMemLogObject();
      v11 = -2147217402;
      CMemoryLog::Write(v42, -2147217402);
      v43 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_109;
      }
      v44 = 582;
    }
    else
    {
      v49 = GetMemLogObject();
      v11 = -2147217402;
      CMemoryLog::Write(v49, -2147217402);
      v43 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_109;
      }
      v44 = 581;
    }
    v48 = 2147749894LL;
LABEL_108:
    WPP_SF_d(*((_QWORD *)v43 + 2), v44, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v48);
LABEL_109:
    std::unique_ptr<CAsyncReq_PutInstanceAsync>::_Delete(&v54);
    CReleaseMe::release((CReleaseMe *)&v59);
    goto LABEL_110;
  }
  v11 = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, struct IWbemObjectSink **))(*(_QWORD *)v8 + 64LL))(
          v8,
          0,
          &v56);
  if ( v11 >= 0 )
  {
    (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v8 + 8LL))(v8);
    goto LABEL_53;
  }
  v30 = GetMemLogObject();
  CMemoryLog::Write(v30, v11);
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return (unsigned int)v11;
  }
  v15 = 577;
LABEL_6:
  WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800842f0  mov     rax, rsp
0x1800842f3  mov     [rax+8], rbx
0x1800842f7  mov     [rax+18h], r8
0x1800842fb  mov     [rax+10h], edx
0x1800842fe  push    rbp
0x1800842ff  push    rsi
0x180084300  push    rdi
0x180084301  push    r12
0x180084303  push    r13
0x180084305  push    r14
0x180084307  push    r15
0x180084309  lea     rbp, [rax-3Fh]
0x18008430d  sub     rsp, 0A0h
0x180084314  mov     r14, r8
0x180084317  mov     r15, rcx
0x18008431a  call    ?CheckNs@CWbemNamespace@@QEAAJXZ; CWbemNamespace::CheckNs(void)
0x18008431f  mov     esi, eax
0x180084321  test    eax, eax
0x180084323  jns     short loc_18008437F
0x180084325  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008432b  mov     edx, esi
0x18008432d  mov     rcx, rax
0x180084330  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180084336  lea     rdi, WPP_GLOBAL_Control
0x18008433d  mov     rcx, cs:WPP_GLOBAL_Control
0x180084344  cmp     rcx, rdi
0x180084347  jz      loc_180084A2A
0x18008434d  mov     bl, 1
0x18008434f  test    [rcx+1Ch], bl
0x180084352  jz      loc_180084A2A
0x180084358  cmp     byte ptr [rcx+19h], 2
0x18008435c  jb      loc_180084A2A
0x180084362  mov     edx, 23Ah
0x180084367  mov     r9d, esi
0x18008436a  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180084371  mov     rcx, [rcx+10h]
0x180084375  call    WPP_SF_d
0x18008437a  jmp     loc_180084A2A
0x18008437f  lea     rdi, WPP_GLOBAL_Control
0x180084386  mov     esi, dword ptr [rbp+37h+arg_28]
0x180084389  mov     bl, 1
0x18008438b  mov     rcx, cs:WPP_GLOBAL_Control
0x180084392  cmp     rcx, rdi
0x180084395  jz      short loc_1800843CD
0x180084397  test    [rcx+1Ch], bl
0x18008439a  jz      short loc_1800843CD
0x18008439c  mov     r12, [rbp+37h+arg_38]
0x1800843a0  mov     r13, [rbp+37h+arg_20]
0x1800843a4  cmp     byte ptr [rcx+19h], 5
0x1800843a8  jb      short loc_1800843D5
0x1800843aa  mov     eax, [r15+130h]
0x1800843b1  mov     dword ptr [rsp+0D0h+var_A0], eax
0x1800843b5  mov     [rsp+0D0h+var_A8], r12
0x1800843ba  mov     [rsp+0D0h+var_B0], r13
0x1800843bf  mov     r9d, esi
0x1800843c2  mov     rcx, [rcx+10h]
0x1800843c6  call    WPP_SF_Dqql
0x1800843cb  jmp     short loc_1800843D5
0x1800843cd  mov     r13, [rbp+37h+arg_20]
0x1800843d1  mov     r12, [rbp+37h+arg_38]
0x1800843d5  test    r14, r14
0x1800843d8  jnz     short loc_180084420
0x1800843da  test    r12, r12
0x1800843dd  jnz     short loc_180084420
0x1800843df  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800843e5  mov     edx, 80041008h
0x1800843ea  mov     rcx, rax
0x1800843ed  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800843f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800843fa  cmp     rcx, rdi
0x1800843fd  jz      loc_1800844FC
0x180084403  test    [rcx+1Ch], bl
0x180084406  jz      loc_1800844FC
0x18008440c  cmp     byte ptr [rcx+19h], 2
0x180084410  jb      loc_1800844FC
0x180084416  mov     edx, 23Ch
0x18008441b  jmp     loc_1800844E6
0x180084420  test    r13, r13
0x180084423  jnz     short loc_180084466
0x180084425  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008442b  mov     edx, 80041008h
0x180084430  mov     rcx, rax
0x180084433  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180084439  mov     rcx, cs:WPP_GLOBAL_Control
0x180084440  cmp     rcx, rdi
0x180084443  jz      loc_1800844FC
0x180084449  test    [rcx+1Ch], bl
0x18008444c  jz      loc_1800844FC
0x180084452  cmp     byte ptr [rcx+19h], 2
0x180084456  jb      loc_1800844FC
0x18008445c  mov     edx, 23Dh
0x180084461  jmp     loc_1800844E6
0x180084466  mov     eax, esi
0x180084468  and     eax, 0FFFCFF7Fh
0x18008446d  cmp     eax, 2
0x180084470  jbe     short loc_1800844A4
0x180084472  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180084478  mov     edx, 80041008h
0x18008447d  mov     rcx, rax
0x180084480  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180084486  mov     rcx, cs:WPP_GLOBAL_Control
0x18008448d  cmp     rcx, rdi
0x180084490  jz      short loc_1800844FC
0x180084492  test    [rcx+1Ch], bl
0x180084495  jz      short loc_1800844FC
0x180084497  cmp     byte ptr [rcx+19h], 2
0x18008449b  jb      short loc_1800844FC
0x18008449d  mov     edx, 23Eh
0x1800844a2  jmp     short loc_1800844E6
0x1800844a4  mov     eax, esi
0x1800844a6  and     eax, 10000h
0x1800844ab  cmp     dword ptr [r15+78h], 0
0x1800844b0  jnz     short loc_180084506
0x1800844b2  test    eax, eax
0x1800844b4  jz      short loc_180084506
0x1800844b6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800844bc  mov     edx, 80041008h
0x1800844c1  mov     rcx, rax
0x1800844c4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800844ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800844d1  cmp     rcx, rdi
0x1800844d4  jz      short loc_1800844FC
0x1800844d6  test    [rcx+1Ch], bl
0x1800844d9  jz      short loc_1800844FC
0x1800844db  cmp     byte ptr [rcx+19h], 2
0x1800844df  jb      short loc_1800844FC
0x1800844e1  mov     edx, 23Fh
0x1800844e6  mov     r9d, 80041008h
0x1800844ec  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800844f3  mov     rcx, [rcx+10h]
0x1800844f7  call    WPP_SF_d
0x1800844fc  mov     eax, 80041008h
0x180084501  jmp     loc_180084A2C
0x180084506  lea     ecx, [rsi-0C000h]
0x18008450c  test    eax, eax
0x18008450e  cmovz   ecx, esi; this
0x180084511  mov     [rbp+37h+var_80], ecx
0x180084514  mov     r13, [rbp+37h+arg_30]
0x180084518  test    r13, r13
0x18008451b  jz      short loc_180084525
0x18008451d  mov     rdx, r13; struct IWbemContext *
0x180084520  call    ?AdjustPutContext@CWbemNamespace@@QEAAJPEAUIWbemContext@@@Z; CWbemNamespace::AdjustPutContext(IWbemContext *)
0x180084525  mov     [rbp+37h+var_78], 0
0x18008452d  test    r14, r14
0x180084530  jnz     short loc_180084597
0x180084532  lea     rax, [rbp+37h+var_78]
0x180084536  mov     [rsp+0D0h+var_B0], rax; struct IWbemObjectSink **
0x18008453b  lea     r9, [rbp+37h+arg_10]; struct _IWmiFinalizer **
0x18008453f  mov     r8, r12; struct IWbemObjectSink *
0x180084542  mov     rdx, r13; struct IWbemContext *
0x180084545  mov     rcx, r15; this
0x180084548  call    ?CreateAsyncFinalizer@CWbemNamespace@@QEAAJPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAPEAU_IWmiFinalizer@@PEAPEAU3@@Z; CWbemNamespace::CreateAsyncFinalizer(IWbemContext *,IWbemObjectSink *,_IWmiFinalizer * *,IWbemObjectSink * *)
0x18008454d  mov     esi, eax
0x18008454f  test    eax, eax
0x180084551  jns     short loc_180084591
0x180084553  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180084559  mov     edx, esi
0x18008455b  mov     rcx, rax
0x18008455e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180084564  mov     rcx, cs:WPP_GLOBAL_Control
0x18008456b  cmp     rcx, rdi
0x18008456e  jz      loc_180084A2A
0x180084574  test    [rcx+1Ch], bl
0x180084577  jz      loc_180084A2A
0x18008457d  cmp     byte ptr [rcx+19h], 2
0x180084581  jb      loc_180084A2A
0x180084587  mov     edx, 240h
0x18008458c  jmp     loc_180084367
0x180084591  mov     r14, [rbp+37h+arg_10]
0x180084595  jmp     short loc_1800845FF
0x180084597  mov     rax, [r14]
0x18008459a  lea     r8, [rbp+37h+var_78]
0x18008459e  xor     edx, edx
0x1800845a0  mov     rcx, r14
0x1800845a3  mov     rax, [rax+40h]
0x1800845a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800845ac  mov     esi, eax
0x1800845ae  test    eax, eax
0x1800845b0  jns     short loc_1800845F0
0x1800845b2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800845b8  mov     edx, esi
0x1800845ba  mov     rcx, rax
0x1800845bd  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800845c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800845ca  cmp     rcx, rdi
0x1800845cd  jz      loc_180084A2A
0x1800845d3  test    [rcx+1Ch], bl
0x1800845d6  jz      loc_180084A2A
0x1800845dc  cmp     byte ptr [rcx+19h], 2
0x1800845e0  jb      loc_180084A2A
0x1800845e6  mov     edx, 241h
0x1800845eb  jmp     loc_180084367
0x1800845f0  mov     rax, [r14]
0x1800845f3  mov     rcx, r14
0x1800845f6  mov     rax, [rax+8]
0x1800845fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800845ff  mov     rax, [rbp+37h+var_78]
0x180084603  mov     [rbp+37h+var_70], rax
0x180084607  mov     [rbp+37h+var_58], r14
0x18008460b  lea     rcx, [rbp+37h+pvarg]; pvarg
0x18008460f  call    cs:__imp_VariantInit
0x180084615  nop
0x180084616  mov     rcx, [rbp+37h+arg_20]
0x18008461a  mov     rax, [rcx]
0x18008461d  mov     [rsp+0D0h+var_A8], 0
0x180084626  mov     [rsp+0D0h+var_B0], 0
0x18008462f  lea     r9, [rbp+37h+pvarg]
0x180084633  xor     r8d, r8d
0x180084636  lea     rdx, aRelpath_0; "__RELPATH"
0x18008463d  mov     rax, [rax+20h]
0x180084641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084646  mov     esi, eax
0x180084648  test    eax, eax
0x18008464a  jns     short loc_18008469B
0x18008464c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180084652  mov     edx, esi
0x180084654  mov     rcx, rax
0x180084657  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008465d  mov     rcx, cs:WPP_GLOBAL_Control
0x180084664  cmp     rcx, rdi
0x180084667  jz      short loc_18008468D
0x180084669  test    [rcx+1Ch], bl
0x18008466c  jz      short loc_18008468D
0x18008466e  cmp     byte ptr [rcx+19h], 2
0x180084672  jb      short loc_18008468D
0x180084674  mov     edx, 242h
0x180084679  mov     r9d, esi
0x18008467c  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180084683  mov     rcx, [rcx+10h]
0x180084687  call    WPP_SF_d
0x18008468c  nop
0x18008468d  lea     rcx, [rbp+37h+pvarg]; this
0x180084691  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180084696  jmp     loc_180084A17
0x18008469b  xor     eax, eax
0x18008469d  mov     word ptr [rbp+37h+var_90], ax
0x1800846a1  lea     r12, [rbp+37h+var_90]
0x1800846a5  mov     eax, 8
0x1800846aa  cmp     ax, word ptr [rbp+37h+pvarg]
0x1800846ae  jnz     short loc_1800846BB
0x1800846b0  mov     rax, qword ptr [rbp+37h+pvarg+8]
0x1800846b4  test    rax, rax
0x1800846b7  cmovnz  r12, rax
0x1800846bb  mov     [rsp+0D0h+var_B0], r13; struct IWbemContext *
0x1800846c0  mov     r9, r14; struct _IWmiFinalizer *
0x1800846c3  mov     r8, r12; unsigned __int16 *
0x1800846c6  lea     rdx, aIwbemservicesP; "IWbemServices::PutInstance"
0x1800846cd  mov     rcx, r15; this
0x1800846d0  call    ?PublishInfo@CWbemNamespace@@QEAAJPEBG0PEAU_IWmiFinalizer@@PEAUIWbemContext@@@Z; CWbemNamespace::PublishInfo(ushort const *,ushort const *,_IWmiFinalizer *,IWbemContext *)
0x1800846d5  mov     esi, eax
0x1800846d7  test    eax, eax
0x1800846d9  jns     short loc_18008470D
0x1800846db  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800846e1  mov     edx, esi
0x1800846e3  mov     rcx, rax
0x1800846e6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800846ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800846f3  cmp     rcx, rdi
0x1800846f6  jz      short loc_18008468D
0x1800846f8  test    [rcx+1Ch], bl
0x1800846fb  jz      short loc_18008468D
0x1800846fd  cmp     byte ptr [rcx+19h], 2
0x180084701  jb      short loc_18008468D
0x180084703  mov     edx, 243h
0x180084708  jmp     loc_180084679
0x18008470d  mov     ecx, [r15+130h]
0x180084714  cmp     ecx, 0FFFFFFFFh
0x180084717  jz      short loc_18008476E
0x180084719  cmp     cs:?g_cntWinmgmtTraceLogging@@3_JA, 0; __int64 g_cntWinmgmtTraceLogging
0x180084721  jz      short loc_18008476E
0x180084723  lea     rax, aSemiSync; "(Semi)Sync"
0x18008472a  lea     r8, aAsync; "Async"
0x180084731  cmp     [rbp+37h+arg_38], 0
0x180084736  cmovz   r8, rax
0x18008473a  mov     rax, [r15+58h]
0x18008473e  mov     [rsp+38h], rax
0x180084743  mov     dword ptr [rsp+0D0h+var_A0], ecx
0x180084747  mov     eax, [r15+17Ch]
0x18008474e  mov     dword ptr [rsp+0D0h+var_A8], eax
0x180084752  mov     eax, [rbp+37h+var_80]
0x180084755  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180084759  mov     r9, r12
0x18008475c  mov     edx, 9
0x180084761  mov     ecx, [r14+2D4h]; unsigned int
0x180084768  call    ?WinmgmtTelemetrylogging@@YAXKZZ; WinmgmtTelemetrylogging(ulong,...)
0x18008476d  nop
0x18008476e  lea     rcx, [rbp+37h+pvarg]; this
0x180084772  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180084777  xor     r12d, r12d
0x18008477a  mov     [rbp+37h+var_68], r12
0x18008477e  mov     rcx, [rbp+37h+var_78]
0x180084782  mov     rax, [rcx]
0x180084785  lea     r8, [rbp+37h+var_68]
0x180084789  lea     rdx, IID_IWbemObjectSinkEx
0x180084790  mov     rax, [rax]
0x180084793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084798  mov     esi, eax
0x18008479a  test    eax, eax
0x18008479c  jns     short loc_1800847EF
0x18008479e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
  ... truncated ...
```
