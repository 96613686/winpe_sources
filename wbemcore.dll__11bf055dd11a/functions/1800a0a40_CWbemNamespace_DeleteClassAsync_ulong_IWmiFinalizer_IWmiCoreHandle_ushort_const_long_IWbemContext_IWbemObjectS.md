# CWbemNamespace::_DeleteClassAsync(ulong,_IWmiFinalizer *,_IWmiCoreHandle *,ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x1800a0a40`
- end: `0x1800a125e`
- name: `?_DeleteClassAsync@CWbemNamespace@@MEAAJKPEAU_IWmiFinalizer@@PEAU_IWmiCoreHandle@@QEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `2078`
- prototype: `__int64 __fastcall(CWbemNamespace *this, unsigned int, struct _IWmiFinalizer *, struct _IWmiCoreHandle *, wchar_t *Str, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009b650`
- `0x18009bae0`

## callees

- `0x18000b140`
- `0x18000f474`
- `0x18003cfe0`
- `0x180041d00`
- `0x1800421ac`
- `0x180047ed0`
- `0x180049580`
- `0x1800523c0`
- `0x180062ed0`
- `0x1800903d0`
- `0x1800a0960`
- `0x1800a0a40`
- `0x1800a1cd8`
- `0x1800da010`

## import_xrefs

- `msvcrt!wcschr` at `0x1800a0c59`
- `msvcrt!wcschr` at `0x1800a0c59`
- `wbemcomn!??0WString@@QEAA@PEBG@Z` at `0x1800a0ff3`
- `wbemcomn!??0WString@@QEAA@PEBG@Z` at `0x1800a0ff3`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800a0fb8`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800a0fb8`
- `wbemcomn!GetMemLogObject` at `0x1800a0acd`
- `wbemcomn!GetMemLogObject` at `0x1800a0b23`
- `wbemcomn!GetMemLogObject` at `0x1800a0b8b`
- `wbemcomn!GetMemLogObject` at `0x1800a0c08`
- `wbemcomn!GetMemLogObject` at `0x1800a0c67`
- `wbemcomn!GetMemLogObject` at `0x1800a0cc0`
- `wbemcomn!GetMemLogObject` at `0x1800a0d12`
- `wbemcomn!GetMemLogObject` at `0x1800a0d96`
- `wbemcomn!GetMemLogObject` at `0x1800a0dfd`
- `wbemcomn!GetMemLogObject` at `0x1800a0e7e`
- `wbemcomn!GetMemLogObject` at `0x1800a0f61`
- `wbemcomn!GetMemLogObject` at `0x1800a1022`
- `wbemcomn!GetMemLogObject` at `0x1800a1093`
- `wbemcomn!GetMemLogObject` at `0x1800a111e`
- `wbemcomn!GetMemLogObject` at `0x1800a118e`
- `wbemcomn!GetMemLogObject` at `0x1800a11f7`
- `wbemcomn!GetMemLogObject` at `0x1800a0acd`
- `wbemcomn!GetMemLogObject` at `0x1800a0b23`
- `wbemcomn!GetMemLogObject` at `0x1800a0b8b`
- `wbemcomn!GetMemLogObject` at `0x1800a0c08`
- `wbemcomn!GetMemLogObject` at `0x1800a0c67`
- `wbemcomn!GetMemLogObject` at `0x1800a0cc0`
- `wbemcomn!GetMemLogObject` at `0x1800a0d12`
- `wbemcomn!GetMemLogObject` at `0x1800a0d96`
- `wbemcomn!GetMemLogObject` at `0x1800a0dfd`
- `wbemcomn!GetMemLogObject` at `0x1800a0e7e`
- `wbemcomn!GetMemLogObject` at `0x1800a0f61`
- `wbemcomn!GetMemLogObject` at `0x1800a1022`
- `wbemcomn!GetMemLogObject` at `0x1800a1093`
- `wbemcomn!GetMemLogObject` at `0x1800a111e`
- `wbemcomn!GetMemLogObject` at `0x1800a118e`
- `wbemcomn!GetMemLogObject` at `0x1800a11f7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a0ad8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a0b31`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a0b9b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a0c16`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a0c77`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a0cce`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a0d20`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a0da1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a0e08`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a0e89`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a0f6c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a1032`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a109e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a1129`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a119e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a1205`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a0ad8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a0b31`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a0b9b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a0c16`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a0c77`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a0cce`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a0d20`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a0da1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a0e08`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a0e89`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a0f6c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a1032`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a109e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a1129`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a119e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a1205`

## string_xrefs

- `0x1800a0e69`: `IWbemServices::DeleteClass`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CWbemNamespace::_DeleteClassAsync(
        CWbemNamespace *this,
        unsigned int a2,
        struct _IWmiFinalizer *a3,
        struct _IWmiCoreHandle *a4,
        wchar_t *Str,
        int a6,
        struct IWbemContext *a7,
        struct IWbemObjectSink *a8)
{
  struct _IWmiFinalizer *v8; // rdi
  int v10; // r15d
  wchar_t *v11; // r14
  int v12; // ebx
  CMemoryLog *MemLogObject; // rax
  CClientCnt *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  struct IWbemObjectSink *v18; // rbx
  CMemoryLog *v19; // rax
  CClientCnt *v20; // rcx
  __int64 v21; // rdx
  unsigned __int64 v22; // rax
  struct IWbemObjectSink *v23; // r9
  unsigned __int64 v24; // rdx
  CMemoryLog *v25; // rax
  const unsigned __int16 *v26; // r12
  int v27; // eax
  CMemoryLog *v28; // rax
  wchar_t *v29; // rax
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  CMemoryLog *v32; // rax
  int v33; // r13d
  struct IWbemContext *v34; // r15
  CMemoryLog *v35; // rax
  CMemoryLog *v36; // rax
  CMemoryLog *v37; // rax
  CClientCnt *v38; // rcx
  __int64 v39; // rdx
  const wchar_t *v40; // r8
  CMemoryLog *v41; // rax
  CNamespaceReq *v42; // rax
  CNamespaceReq *v43; // rbx
  struct IWbemContext *v44; // rax
  CMemoryLog *v45; // rax
  CClientCnt *v46; // rcx
  __int64 v47; // rdx
  int inited; // esi
  CMemoryLog *v49; // rax
  CMemoryLog *v50; // rax
  __int64 v51; // r9
  CMemoryLog *v52; // rax
  CMemoryLog *v53; // rax
  struct IWbemObjectSink **v54; // [rsp+20h] [rbp-60h]
  struct IWbemObjectSink *v55; // [rsp+28h] [rbp-58h]
  __int64 v56; // [rsp+30h] [rbp-50h]
  CAsyncReq_DeleteClassAsync *v57; // [rsp+40h] [rbp-40h] BYREF
  struct IWbemObjectSink *v58; // [rsp+48h] [rbp-38h] BYREF
  struct IWbemObjectSinkEx *v59; // [rsp+50h] [rbp-30h] BYREF
  struct IWbemObjectSinkEx *v60; // [rsp+58h] [rbp-28h] BYREF
  struct IWbemObjectSink *v61; // [rsp+60h] [rbp-20h] BYREF
  _QWORD v62[3]; // [rsp+68h] [rbp-18h] BYREF
  struct _IWmiFinalizer *v64; // [rsp+D0h] [rbp+50h] BYREF

  v64 = a3;
  v8 = a3;
  v10 = a6;
  v11 = Str;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_DqSl(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      586,
      (_DWORD)a8,
      a6,
      (char)a8,
      (__int64)Str,
      *((_DWORD *)this + 76));
  }
  v12 = CWbemNamespace::CheckNs(this);
  if ( v12 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v12);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v12;
    }
    v15 = 587;
    goto LABEL_10;
  }
  v18 = a8;
  if ( v8 || a8 )
  {
    if ( !v11 || !*v11 )
    {
      v53 = GetMemLogObject();
      CMemoryLog::Write(v53, -2147217400);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749896LL;
      }
      v21 = 589;
      goto LABEL_118;
    }
    v22 = wcslen_max(v11, (unsigned int)g_IdentifierLimit);
    if ( v22 > v24 )
    {
      v25 = GetMemLogObject();
      v12 = -2147217300;
      CMemoryLog::Write(v25, -2147217300);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)v12;
      }
      v15 = 590;
      v16 = 2147749996LL;
      goto LABEL_11;
    }
    if ( *v11 == 92 || *v11 == 47 )
    {
      v29 = wcschr(v11, 0x3Au);
      v23 = 0;
      if ( !v29 )
      {
        v30 = GetMemLogObject();
        v12 = -2147217350;
        CMemoryLog::Write(v30, -2147217350);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)v12;
        }
        v15 = 591;
        v16 = 2147749946LL;
        goto LABEL_11;
      }
      v26 = v29 + 1;
      if ( !v29[1] )
      {
        v31 = GetMemLogObject();
        CMemoryLog::Write(v31, -2147217400);
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return 2147749896LL;
        }
        v21 = 592;
        goto LABEL_118;
      }
    }
    else
    {
      v26 = v11;
    }
    v27 = v10 & 0x10000;
    if ( *((_DWORD *)this + 30) == (_DWORD)v23 && v27 )
    {
      v28 = GetMemLogObject();
      CMemoryLog::Write(v28, -2147217400);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749896LL;
      }
      v21 = 593;
      goto LABEL_118;
    }
    if ( (v10 & 0xFFFEFF7F) != 0 )
    {
      v32 = GetMemLogObject();
      CMemoryLog::Write(v32, -2147217400);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749896LL;
      }
      v21 = 594;
      goto LABEL_118;
    }
    v33 = v10 - 49152;
    if ( !v27 )
      v33 = v10;
    v58 = v23;
    v34 = a7;
    if ( v8 )
    {
      v12 = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, struct IWbemObjectSink **))(*(_QWORD *)v8 + 64LL))(
              v8,
              0,
              &v58);
      if ( v12 < 0 )
      {
        v36 = GetMemLogObject();
        CMemoryLog::Write(v36, v12);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)v12;
        }
        v15 = 596;
LABEL_10:
        v16 = (unsigned int)v12;
LABEL_11:
        WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v16);
        return (unsigned int)v12;
      }
      (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v8 + 8LL))(v8);
    }
    else
    {
      v12 = CWbemNamespace::CreateAsyncFinalizer(this, a7, v18, &v64, &v58);
      if ( v12 < 0 )
      {
        v35 = GetMemLogObject();
        CMemoryLog::Write(v35, v12);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)v12;
        }
        v15 = 595;
        goto LABEL_10;
      }
      v8 = v64;
    }
    v61 = v58;
    v62[0] = v8;
    v12 = CWbemNamespace::PublishInfo(this, L"IWbemServices::DeleteClass", v26, v8, v34);
    if ( v12 < 0 )
    {
      v37 = GetMemLogObject();
      CMemoryLog::Write(v37, v12);
      v38 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_71;
      }
      v39 = 597;
      goto LABEL_70;
    }
    if ( *((_DWORD *)this + 76) != -1 && g_cntWinmgmtTraceLogging )
    {
      v40 = L"Async";
      if ( !a8 )
        v40 = L"(Semi)Sync";
      LODWORD(v56) = *((_DWORD *)this + 76);
      LODWORD(v55) = *((_DWORD *)this + 95);
      LODWORD(v54) = v33;
      WinmgmtTelemetrylogging(*((_DWORD *)v8 + 181), 5, v40, v11, v54, v55, v56, *((_QWORD *)this + 11));
    }
    v59 = 0;
    v12 = ((__int64 (__fastcall *)(struct IWbemObjectSink *, GUID *, struct IWbemObjectSinkEx **))v58->lpVtbl->QueryInterface)(
            v58,
            &IID_IWbemObjectSinkEx,
            &v59);
    if ( v12 < 0 )
    {
      v41 = GetMemLogObject();
      CMemoryLog::Write(v41, v12);
      v38 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_71;
      }
      v39 = 598;
LABEL_70:
      WPP_SF_d(*((_QWORD *)v38 + 2), v39, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)v12);
LABEL_71:
      CReleaseMe::release((CReleaseMe *)v62);
      CReleaseMe::release((CReleaseMe *)&v61);
      return (unsigned int)v12;
    }
    v60 = v59;
    v57 = 0;
    v42 = (CNamespaceReq *)CWin32DefaultArena::WbemMemAlloc(0x70u);
    v43 = v42;
    v62[1] = v42;
    if ( v42 )
    {
      CNamespaceReq::CNamespaceReq(v42, this, v59, v34, 0);
      *(_QWORD *)v43 = &CAsyncReq_DeleteClassAsync::`vftable';
      WString::WString((CNamespaceReq *)((char *)v43 + 96), v26);
      *((_DWORD *)v43 + 26) = v33;
    }
    else
    {
      v43 = 0;
    }
    if ( v43 )
    {
      std::unique_ptr<CAsyncReq_DeleteClassAsync>::_Delete(&v57);
      v57 = v43;
      v44 = (struct IWbemContext *)*((_QWORD *)v43 + 5);
      if ( v44 )
      {
        inited = CWbemNamespace::InitNewTask(this, v43, v8, a2, v44, a8);
        if ( inited < 0 )
        {
          v49 = GetMemLogObject();
          CMemoryLog::Write(v49, inited);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              601,
              WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
              (unsigned int)inited);
          }
          std::unique_ptr<CAsyncReq_DeleteClassAsync>::_Delete(&v57);
          CReleaseMe::release((CReleaseMe *)&v60);
          v12 = inited;
          goto LABEL_71;
        }
        CReleaseMe::release((CReleaseMe *)&v61);
        v12 = ConfigMgr::EnqueueRequest(v43);
        if ( v12 >= 0 )
        {
          v57 = 0;
          v46 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_113;
          }
          v47 = 603;
        }
        else
        {
          (*(void (__fastcall **)(struct _IWmiFinalizer *, _QWORD))(*(_QWORD *)v8 + 112LL))(v8, 0);
          v50 = GetMemLogObject();
          CMemoryLog::Write(v50, v12);
          v46 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_113;
          }
          v47 = 602;
        }
        v51 = (unsigned int)v12;
        goto LABEL_112;
      }
      v45 = GetMemLogObject();
      v12 = -2147217402;
      CMemoryLog::Write(v45, -2147217402);
      v46 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_113;
      }
      v47 = 600;
    }
    else
    {
      v52 = GetMemLogObject();
      v12 = -2147217402;
      CMemoryLog::Write(v52, -2147217402);
      v46 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_113;
      }
      v47 = 599;
    }
    v51 = 2147749894LL;
LABEL_112:
    WPP_SF_d(*((_QWORD *)v46 + 2), v47, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v51);
LABEL_113:
    std::unique_ptr<CAsyncReq_DeleteClassAsync>::_Delete(&v57);
    CReleaseMe::release((CReleaseMe *)&v60);
    goto LABEL_71;
  }
  v19 = GetMemLogObject();
  CMemoryLog::Write(v19, -2147217400);
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return 2147749896LL;
  }
  v21 = 588;
LABEL_118:
  WPP_SF_d(*((_QWORD *)v20 + 2), v21, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
  return 2147749896LL;
}

```

## disassembly

```asm
0x1800a0a40  mov     [rsp-38h+arg_0], rbx
0x1800a0a45  mov     [rsp-38h+arg_10], r8
0x1800a0a4a  mov     [rsp-38h+arg_8], edx
0x1800a0a4e  push    rbp
0x1800a0a4f  push    rsi
0x1800a0a50  push    rdi
0x1800a0a51  push    r12
0x1800a0a53  push    r13
0x1800a0a55  push    r14
0x1800a0a57  push    r15
0x1800a0a59  mov     rbp, rsp
0x1800a0a5c  sub     rsp, 80h
0x1800a0a63  mov     rdi, r8
0x1800a0a66  mov     rsi, rcx
0x1800a0a69  lea     r12, WPP_GLOBAL_Control
0x1800a0a70  mov     r15d, [rbp+arg_28]
0x1800a0a74  mov     r14, [rbp+Str]
0x1800a0a78  mov     r13b, 1
0x1800a0a7b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0a82  cmp     rcx, r12
0x1800a0a85  jz      short loc_1800A0ABC
0x1800a0a87  test    [rcx+1Ch], r13b
0x1800a0a8b  jz      short loc_1800A0ABC
0x1800a0a8d  cmp     byte ptr [rcx+19h], 5
0x1800a0a91  jb      short loc_1800A0ABC
0x1800a0a93  mov     edx, 24Ah
0x1800a0a98  mov     eax, [rsi+130h]
0x1800a0a9e  mov     dword ptr [rsp+80h+var_50], eax
0x1800a0aa2  mov     [rsp+80h+var_58], r14
0x1800a0aa7  mov     r8, [rbp+arg_38]
0x1800a0aab  mov     [rsp+80h+var_60], r8
0x1800a0ab0  mov     r9d, r15d
0x1800a0ab3  mov     rcx, [rcx+10h]
0x1800a0ab7  call    WPP_SF_DqSl
0x1800a0abc  mov     rcx, rsi; this
0x1800a0abf  call    ?CheckNs@CWbemNamespace@@QEAAJXZ; CWbemNamespace::CheckNs(void)
0x1800a0ac4  mov     ebx, eax
0x1800a0ac6  xor     r9d, r9d
0x1800a0ac9  test    eax, eax
0x1800a0acb  jns     short loc_1800A0B15
0x1800a0acd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a0ad3  mov     edx, ebx
0x1800a0ad5  mov     rcx, rax
0x1800a0ad8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a0ade  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0ae5  cmp     rcx, r12
0x1800a0ae8  jz      short loc_1800A0B0E
0x1800a0aea  test    [rcx+1Ch], r13b
0x1800a0aee  jz      short loc_1800A0B0E
0x1800a0af0  cmp     byte ptr [rcx+19h], 2
0x1800a0af4  jb      short loc_1800A0B0E
0x1800a0af6  mov     edx, 24Bh
0x1800a0afb  mov     r9d, ebx
0x1800a0afe  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800a0b05  mov     rcx, [rcx+10h]
0x1800a0b09  call    WPP_SF_d
0x1800a0b0e  mov     eax, ebx
0x1800a0b10  jmp     loc_1800A1243
0x1800a0b15  mov     rbx, [rbp+arg_38]
0x1800a0b19  test    rdi, rdi
0x1800a0b1c  jnz     short loc_1800A0B65
0x1800a0b1e  test    rbx, rbx
0x1800a0b21  jnz     short loc_1800A0B65
0x1800a0b23  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a0b29  mov     edx, 80041008h
0x1800a0b2e  mov     rcx, rax
0x1800a0b31  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a0b37  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0b3e  cmp     rcx, r12
0x1800a0b41  jz      loc_1800A123E
0x1800a0b47  test    [rcx+1Ch], r13b
0x1800a0b4b  jz      loc_1800A123E
0x1800a0b51  cmp     byte ptr [rcx+19h], 2
0x1800a0b55  jb      loc_1800A123E
0x1800a0b5b  mov     edx, 24Ch
0x1800a0b60  jmp     loc_1800A1228
0x1800a0b65  test    r14, r14
0x1800a0b68  jz      loc_1800A11F7
0x1800a0b6e  cmp     [r14], r9w
0x1800a0b72  jz      loc_1800A11F7
0x1800a0b78  mov     edx, cs:?g_IdentifierLimit@@3KA; unsigned __int64
0x1800a0b7e  mov     rcx, r14; unsigned __int16 *
0x1800a0b81  call    ?wcslen_max@@YA_KPEBG_K@Z; wcslen_max(ushort const *,unsigned __int64)
0x1800a0b86  cmp     rax, rdx
0x1800a0b89  jbe     short loc_1800A0BD5
0x1800a0b8b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a0b91  mov     ebx, 8004106Ch
0x1800a0b96  mov     edx, ebx
0x1800a0b98  mov     rcx, rax
0x1800a0b9b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a0ba1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0ba8  cmp     rcx, r12
0x1800a0bab  jz      loc_1800A0B0E
0x1800a0bb1  test    [rcx+1Ch], r13b
0x1800a0bb5  jz      loc_1800A0B0E
0x1800a0bbb  cmp     byte ptr [rcx+19h], 2
0x1800a0bbf  jb      loc_1800A0B0E
0x1800a0bc5  mov     edx, 24Eh
0x1800a0bca  mov     r9d, 8004106Ch
0x1800a0bd0  jmp     loc_1800A0AFE
0x1800a0bd5  mov     eax, 5Ch ; '\'
0x1800a0bda  cmp     ax, [r14]
0x1800a0bde  jz      short loc_1800A0C51
0x1800a0be0  mov     eax, 2Fh ; '/'
0x1800a0be5  cmp     ax, [r14]
0x1800a0be9  jz      short loc_1800A0C51
0x1800a0beb  mov     r12, r14
0x1800a0bee  mov     eax, r15d
0x1800a0bf1  and     eax, 10000h
0x1800a0bf6  cmp     [rsi+78h], r9d
0x1800a0bfa  jnz     loc_1800A0D09
0x1800a0c00  test    eax, eax
0x1800a0c02  jz      loc_1800A0D09
0x1800a0c08  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a0c0e  mov     edx, 80041008h
0x1800a0c13  mov     rcx, rax
0x1800a0c16  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a0c1c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0c23  lea     rax, WPP_GLOBAL_Control
0x1800a0c2a  cmp     rcx, rax
0x1800a0c2d  jz      loc_1800A123E
0x1800a0c33  test    [rcx+1Ch], r13b
0x1800a0c37  jz      loc_1800A123E
0x1800a0c3d  cmp     byte ptr [rcx+19h], 2
0x1800a0c41  jb      loc_1800A123E
0x1800a0c47  mov     edx, 251h
0x1800a0c4c  jmp     loc_1800A1228
0x1800a0c51  mov     edx, 3Ah ; ':'; Ch
0x1800a0c56  mov     rcx, r14; Str
0x1800a0c59  call    cs:__imp_wcschr
0x1800a0c5f  xor     r9d, r9d
0x1800a0c62  test    rax, rax
0x1800a0c65  jnz     short loc_1800A0CB1
0x1800a0c67  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a0c6d  mov     ebx, 8004103Ah
0x1800a0c72  mov     edx, ebx
0x1800a0c74  mov     rcx, rax
0x1800a0c77  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a0c7d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0c84  cmp     rcx, r12
0x1800a0c87  jz      loc_1800A0B0E
0x1800a0c8d  test    [rcx+1Ch], r13b
0x1800a0c91  jz      loc_1800A0B0E
0x1800a0c97  cmp     byte ptr [rcx+19h], 2
0x1800a0c9b  jb      loc_1800A0B0E
0x1800a0ca1  mov     edx, 24Fh
0x1800a0ca6  mov     r9d, 8004103Ah
0x1800a0cac  jmp     loc_1800A0AFE
0x1800a0cb1  lea     r12, [rax+2]
0x1800a0cb5  cmp     r9w, [r12]
0x1800a0cba  jnz     loc_1800A0BEE
0x1800a0cc0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a0cc6  mov     edx, 80041008h
0x1800a0ccb  mov     rcx, rax
0x1800a0cce  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a0cd4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0cdb  lea     rax, WPP_GLOBAL_Control
0x1800a0ce2  cmp     rcx, rax
0x1800a0ce5  jz      loc_1800A123E
0x1800a0ceb  test    [rcx+1Ch], r13b
0x1800a0cef  jz      loc_1800A123E
0x1800a0cf5  cmp     byte ptr [rcx+19h], 2
0x1800a0cf9  jb      loc_1800A123E
0x1800a0cff  mov     edx, 250h
0x1800a0d04  jmp     loc_1800A1228
0x1800a0d09  test    r15d, 0FFFEFF7Fh
0x1800a0d10  jz      short loc_1800A0D5B
0x1800a0d12  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a0d18  mov     edx, 80041008h
0x1800a0d1d  mov     rcx, rax
0x1800a0d20  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a0d26  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0d2d  lea     rax, WPP_GLOBAL_Control
0x1800a0d34  cmp     rcx, rax
0x1800a0d37  jz      loc_1800A123E
0x1800a0d3d  test    [rcx+1Ch], r13b
0x1800a0d41  jz      loc_1800A123E
0x1800a0d47  cmp     byte ptr [rcx+19h], 2
0x1800a0d4b  jb      loc_1800A123E
0x1800a0d51  mov     edx, 252h
0x1800a0d56  jmp     loc_1800A1228
0x1800a0d5b  lea     r13d, [r15-0C000h]
0x1800a0d62  test    eax, eax
0x1800a0d64  cmovz   r13d, r15d
0x1800a0d68  mov     [rbp+var_38], r9
0x1800a0d6c  mov     r15, [rbp+arg_30]
0x1800a0d70  test    rdi, rdi
0x1800a0d73  jnz     short loc_1800A0DE2
0x1800a0d75  lea     rax, [rbp+var_38]
0x1800a0d79  mov     [rsp+80h+var_60], rax; struct IWbemObjectSink **
0x1800a0d7e  lea     r9, [rbp+arg_10]; struct _IWmiFinalizer **
0x1800a0d82  mov     r8, rbx; struct IWbemObjectSink *
0x1800a0d85  mov     rdx, r15; struct IWbemContext *
0x1800a0d88  mov     rcx, rsi; this
0x1800a0d8b  call    ?CreateAsyncFinalizer@CWbemNamespace@@QEAAJPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAPEAU_IWmiFinalizer@@PEAPEAU3@@Z; CWbemNamespace::CreateAsyncFinalizer(IWbemContext *,IWbemObjectSink *,_IWmiFinalizer * *,IWbemObjectSink * *)
0x1800a0d90  mov     ebx, eax
0x1800a0d92  test    eax, eax
0x1800a0d94  jns     short loc_1800A0DDC
0x1800a0d96  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a0d9c  mov     edx, ebx
0x1800a0d9e  mov     rcx, rax
0x1800a0da1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a0da7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0dae  lea     rax, WPP_GLOBAL_Control
0x1800a0db5  cmp     rcx, rax
0x1800a0db8  jz      loc_1800A0B0E
0x1800a0dbe  test    byte ptr [rcx+1Ch], 1
0x1800a0dc2  jz      loc_1800A0B0E
0x1800a0dc8  cmp     byte ptr [rcx+19h], 2
0x1800a0dcc  jb      loc_1800A0B0E
0x1800a0dd2  mov     edx, 253h
0x1800a0dd7  jmp     loc_1800A0AFB
0x1800a0ddc  mov     rdi, [rbp+arg_10]
0x1800a0de0  jmp     short loc_1800A0E52
0x1800a0de2  mov     rax, [rdi]
0x1800a0de5  lea     r8, [rbp+var_38]
0x1800a0de9  xor     edx, edx
0x1800a0deb  mov     rcx, rdi
0x1800a0dee  mov     rax, [rax+40h]
0x1800a0df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0df7  mov     ebx, eax
0x1800a0df9  test    eax, eax
0x1800a0dfb  jns     short loc_1800A0E43
0x1800a0dfd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a0e03  mov     edx, ebx
0x1800a0e05  mov     rcx, rax
0x1800a0e08  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a0e0e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0e15  lea     rax, WPP_GLOBAL_Control
0x1800a0e1c  cmp     rcx, rax
0x1800a0e1f  jz      loc_1800A0B0E
0x1800a0e25  test    byte ptr [rcx+1Ch], 1
0x1800a0e29  jz      loc_1800A0B0E
0x1800a0e2f  cmp     byte ptr [rcx+19h], 2
0x1800a0e33  jb      loc_1800A0B0E
0x1800a0e39  mov     edx, 254h
0x1800a0e3e  jmp     loc_1800A0AFB
0x1800a0e43  mov     rax, [rdi]
0x1800a0e46  mov     rcx, rdi
0x1800a0e49  mov     rax, [rax+8]
0x1800a0e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0e52  mov     rax, [rbp+var_38]
0x1800a0e56  mov     [rbp+var_20], rax
0x1800a0e5a  mov     [rbp+var_18], rdi
0x1800a0e5e  mov     [rsp+80h+var_60], r15; struct IWbemContext *
0x1800a0e63  mov     r9, rdi; struct _IWmiFinalizer *
0x1800a0e66  mov     r8, r12; unsigned __int16 *
0x1800a0e69  lea     rdx, aIwbemservicesD_0; "IWbemServices::DeleteClass"
0x1800a0e70  mov     rcx, rsi; this
0x1800a0e73  call    ?PublishInfo@CWbemNamespace@@QEAAJPEBG0PEAU_IWmiFinalizer@@PEAUIWbemContext@@@Z; CWbemNamespace::PublishInfo(ushort const *,ushort const *,_IWmiFinalizer *,IWbemContext *)
0x1800a0e78  mov     ebx, eax
0x1800a0e7a  test    eax, eax
0x1800a0e7c  jns     short loc_1800A0EDF
0x1800a0e7e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a0e84  mov     edx, ebx
0x1800a0e86  mov     rcx, rax
0x1800a0e89  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a0e8f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0e96  lea     rax, WPP_GLOBAL_Control
0x1800a0e9d  cmp     rcx, rax
0x1800a0ea0  jz      short loc_1800A0EC7
0x1800a0ea2  test    byte ptr [rcx+1Ch], 1
0x1800a0ea6  jz      short loc_1800A0EC7
0x1800a0ea8  cmp     byte ptr [rcx+19h], 2
0x1800a0eac  jb      short loc_1800A0EC7
0x1800a0eae  mov     edx, 255h
0x1800a0eb3  mov     r9d, ebx
0x1800a0eb6  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800a0ebd  mov     rcx, [rcx+10h]
0x1800a0ec1  call    WPP_SF_d
0x1800a0ec6  nop
0x1800a0ec7  lea     rcx, [rbp+var_18]; this
0x1800a0ecb  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800a0ed0  nop
0x1800a0ed1  lea     rcx, [rbp+var_20]; this
0x1800a0ed5  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800a0eda  jmp     loc_1800A0B0E
0x1800a0edf  mov     ecx, [rsi+130h]
0x1800a0ee5  cmp     ecx, 0FFFFFFFFh
0x1800a0ee8  jz      short loc_1800A0F3A
0x1800a0eea  cmp     cs:?g_cntWinmgmtTraceLogging@@3_JA, 0; __int64 g_cntWinmgmtTraceLogging
0x1800a0ef2  jz      short loc_1800A0F3A
0x1800a0ef4  lea     rax, aSemiSync; "(Semi)Sync"
0x1800a0efb  lea     r8, aAsync; "Async"
0x1800a0f02  cmp     [rbp+arg_38], 0
0x1800a0f07  cmovz   r8, rax
0x1800a0f0b  mov     rax, [rsi+58h]
0x1800a0f0f  mov     [rsp+80h+var_48], rax
0x1800a0f14  mov     dword ptr [rsp+80h+var_50], ecx
0x1800a0f18  mov     eax, [rsi+17Ch]
0x1800a0f1e  mov     dword ptr [rsp+80h+var_58], eax
0x1800a0f22  mov     dword ptr [rsp+80h+var_60], r13d
0x1800a0f27  mov     r9, r14
0x1800a0f2a  mov     edx, 5
0x1800a0f2f  mov     ecx, [rdi+2D4h]; unsigned int
0x1800a0f35  call    ?WinmgmtTelemetrylogging@@YAXKZZ; WinmgmtTelemetrylogging(ulong,...)
0x1800a0f3a  xor     r14d, r14d
0x1800a0f3d  mov     [rbp+var_30], r14
0x1800a0f41  mov     rcx, [rbp+var_38]
0x1800a0f45  mov     rax, [rcx]
  ... truncated ...
```
