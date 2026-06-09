# CWbemNamespace::_ExecQueryAsync(ulong,_IWmiFinalizer *,_IWmiCoreHandle *,ushort * const,ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x180022a90`
- end: `0x1800231e2`
- name: `?_ExecQueryAsync@CWbemNamespace@@MEAAJKPEAU_IWmiFinalizer@@PEAU_IWmiCoreHandle@@QEAG2JPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `1874`
- prototype: `__int64 __fastcall(CWbemNamespace *this, unsigned int, struct _IWmiFinalizer *, struct _IWmiCoreHandle *, unsigned __int16 *const, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001b550`
- `0x1800225a0`

## callees

- `0x18000ac94`
- `0x18000b140`
- `0x18000f474`
- `0x18001f6d0`
- `0x180022a90`
- `0x18003cfe0`
- `0x1800421ac`
- `0x180042c40`
- `0x180047ed0`
- `0x180049580`
- `0x1800523c0`
- `0x180062ed0`
- `0x1800903d0`
- `0x1800a09a8`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180022f3c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180022f3c`
- `wbemcomn!GetMemLogObject` at `0x180022ac4`
- `wbemcomn!GetMemLogObject` at `0x180022b43`
- `wbemcomn!GetMemLogObject` at `0x180022be9`
- `wbemcomn!GetMemLogObject` at `0x180022c67`
- `wbemcomn!GetMemLogObject` at `0x180022cb9`
- `wbemcomn!GetMemLogObject` at `0x180022d29`
- `wbemcomn!GetMemLogObject` at `0x180022d88`
- `wbemcomn!GetMemLogObject` at `0x180022e05`
- `wbemcomn!GetMemLogObject` at `0x180022ee9`
- `wbemcomn!GetMemLogObject` at `0x180022f9b`
- `wbemcomn!GetMemLogObject` at `0x180023008`
- `wbemcomn!GetMemLogObject` at `0x18002308d`
- `wbemcomn!GetMemLogObject` at `0x1800230e9`
- `wbemcomn!GetMemLogObject` at `0x18002314a`
- `wbemcomn!GetMemLogObject` at `0x18002317c`
- `wbemcomn!GetMemLogObject` at `0x180022ac4`
- `wbemcomn!GetMemLogObject` at `0x180022b43`
- `wbemcomn!GetMemLogObject` at `0x180022be9`
- `wbemcomn!GetMemLogObject` at `0x180022c67`
- `wbemcomn!GetMemLogObject` at `0x180022cb9`
- `wbemcomn!GetMemLogObject` at `0x180022d29`
- `wbemcomn!GetMemLogObject` at `0x180022d88`
- `wbemcomn!GetMemLogObject` at `0x180022e05`
- `wbemcomn!GetMemLogObject` at `0x180022ee9`
- `wbemcomn!GetMemLogObject` at `0x180022f9b`
- `wbemcomn!GetMemLogObject` at `0x180023008`
- `wbemcomn!GetMemLogObject` at `0x18002308d`
- `wbemcomn!GetMemLogObject` at `0x1800230e9`
- `wbemcomn!GetMemLogObject` at `0x18002314a`
- `wbemcomn!GetMemLogObject` at `0x18002317c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022acf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022b53`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022bf7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022c77`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022cc7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022d34`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022d93`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022e10`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022ef4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022fab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180023014`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180023098`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800230f9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180023158`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002318a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022acf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022b53`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022bf7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022c77`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022cc7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022d34`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022d93`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022e10`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022ef4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022fab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180023014`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180023098`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800230f9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180023158`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002318a`

## string_xrefs

- `0x180022b30`: `Read (ExecQuery)`
- `0x180022df0`: `IWbemServices::ExecQuery`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CWbemNamespace::_ExecQueryAsync(
        CWbemNamespace *this,
        unsigned int a2,
        struct _IWmiFinalizer *a3,
        struct _IWmiCoreHandle *a4,
        unsigned __int16 *const a5,
        unsigned __int16 *const a6,
        int a7,
        struct IWbemContext *a8,
        struct IWbemObjectSink *a9)
{
  struct _IWmiFinalizer *v9; // r14
  __int64 v11; // rcx
  int v12; // esi
  CMemoryLog *MemLogObject; // rax
  CClientCnt *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  unsigned __int16 *v18; // r12
  int v19; // r8d
  CMemoryLog *v20; // rax
  unsigned __int16 *v21; // r13
  struct IWbemObjectSink *v22; // rsi
  CMemoryLog *v23; // rax
  CClientCnt *v24; // rcx
  __int64 v25; // rdx
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // rdx
  CMemoryLog *v28; // rax
  CMemoryLog *v29; // rax
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  CMemoryLog *v32; // rax
  CClientCnt *v33; // rcx
  __int64 v34; // rdx
  const wchar_t *v35; // r8
  CMemoryLog *v36; // rax
  CAsyncReq_ExecQueryAsync *v37; // rax
  CAsyncReq_ExecQueryAsync *Async; // rsi
  struct IWbemContext *v39; // rax
  CMemoryLog *v40; // rax
  CClientCnt *v41; // rcx
  __int64 v42; // rdx
  int inited; // r15d
  CMemoryLog *v44; // rax
  CMemoryLog *v45; // rax
  __int64 v46; // r9
  CMemoryLog *v47; // rax
  CMemoryLog *v48; // rax
  CMemoryLog *v49; // rax
  struct IWbemObjectSink **v50; // [rsp+20h] [rbp-60h]
  bool v51; // [rsp+28h] [rbp-58h]
  struct IWbemObjectSinkEx *v52; // [rsp+28h] [rbp-58h]
  struct IWbemContext *v53; // [rsp+30h] [rbp-50h]
  CAsyncReq_ExecQueryAsync *v54; // [rsp+40h] [rbp-40h] BYREF
  struct IWbemObjectSink *v55; // [rsp+48h] [rbp-38h] BYREF
  struct IWbemObjectSinkEx *v56; // [rsp+50h] [rbp-30h] BYREF
  struct IWbemObjectSinkEx *v57; // [rsp+58h] [rbp-28h] BYREF
  struct IWbemObjectSink *v58; // [rsp+60h] [rbp-20h] BYREF
  _QWORD v59[3]; // [rsp+68h] [rbp-18h] BYREF
  struct _IWmiFinalizer *v61; // [rsp+D0h] [rbp+50h] BYREF

  v61 = a3;
  v9 = a3;
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
    v15 = 667;
    goto LABEL_6;
  }
  v18 = a6;
  if ( !CWbemNamespace::InnerAllowedWithSD(
          (CWbemNamespace *)v11,
          (struct CNtSecurityDescriptor *)(v11 + 216),
          1u,
          L"Read (ExecQuery)",
          a6,
          v51,
          1) )
  {
    v20 = GetMemLogObject();
    v12 = -2147217405;
    CMemoryLog::Write(v20, -2147217405);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v12;
    }
    v15 = 668;
    v16 = 2147749891LL;
    goto LABEL_7;
  }
  v21 = a5;
  if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    v22 = a9;
  }
  else
  {
    v22 = a9;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      WPP_SF_SSql(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        669,
        v19,
        (_DWORD)a5,
        (__int64)v18,
        (char)a9,
        *((_DWORD *)this + 76));
  }
  if ( v9 || v22 )
  {
    if ( !v21 || !v18 )
    {
      v49 = GetMemLogObject();
      CMemoryLog::Write(v49, -2147217400);
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749896LL;
      }
      v25 = 671;
      goto LABEL_109;
    }
    if ( !*v21 || !*v18 )
    {
      v48 = GetMemLogObject();
      CMemoryLog::Write(v48, -2147217400);
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749896LL;
      }
      v25 = 672;
      goto LABEL_109;
    }
    v26 = wcslen_max(v18, (unsigned int)g_QueryLimit);
    if ( v26 > v27 )
    {
      v28 = GetMemLogObject();
      v12 = -2147217300;
      CMemoryLog::Write(v28, -2147217300);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)v12;
      }
      v15 = 673;
      v16 = 2147749996LL;
      goto LABEL_7;
    }
    if ( (a7 & 0xFFEDFC7D) != 0 )
    {
      v29 = GetMemLogObject();
      CMemoryLog::Write(v29, -2147217400);
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749896LL;
      }
      v25 = 674;
      goto LABEL_109;
    }
    v55 = 0;
    if ( v9 )
    {
      v12 = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, struct IWbemObjectSink **))(*(_QWORD *)v9 + 64LL))(
              v9,
              0,
              &v55);
      if ( v12 < 0 )
      {
        v31 = GetMemLogObject();
        CMemoryLog::Write(v31, v12);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)v12;
        }
        v15 = 676;
LABEL_6:
        v16 = (unsigned int)v12;
LABEL_7:
        WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v16);
        return (unsigned int)v12;
      }
      (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v9 + 8LL))(v9);
    }
    else
    {
      v12 = CWbemNamespace::CreateAsyncFinalizer(this, a8, v22, &v61, &v55);
      if ( v12 < 0 )
      {
        v30 = GetMemLogObject();
        CMemoryLog::Write(v30, v12);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)v12;
        }
        v15 = 675;
        goto LABEL_6;
      }
      v9 = v61;
    }
    v58 = v55;
    v59[0] = v9;
    v12 = CWbemNamespace::PublishInfo(this, L"IWbemServices::ExecQuery", v18, v9, a8);
    if ( v12 < 0 )
    {
      v32 = GetMemLogObject();
      CMemoryLog::Write(v32, v12);
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_58;
      }
      v34 = 677;
      goto LABEL_57;
    }
    if ( *((_DWORD *)this + 76) != -1 && g_cntWinmgmtTraceLogging )
    {
      v35 = L"Async";
      if ( !a9 )
        v35 = L"(Semi)Sync";
      LODWORD(v53) = *((_DWORD *)this + 76);
      LODWORD(v52) = *((_DWORD *)this + 95);
      LODWORD(v50) = a7;
      WinmgmtTelemetrylogging(*((_DWORD *)v9 + 181), 2, v35, v18, v50, v52, v53, *((_QWORD *)this + 11));
    }
    v56 = 0;
    v12 = ((__int64 (__fastcall *)(struct IWbemObjectSink *, GUID *, struct IWbemObjectSinkEx **))v55->lpVtbl->QueryInterface)(
            v55,
            &IID_IWbemObjectSinkEx,
            &v56);
    if ( v12 < 0 )
    {
      v36 = GetMemLogObject();
      CMemoryLog::Write(v36, v12);
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_58;
      }
      v34 = 678;
LABEL_57:
      WPP_SF_d(*((_QWORD *)v33 + 2), v34, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)v12);
LABEL_58:
      CReleaseMe::release((CReleaseMe *)v59);
      CReleaseMe::release((CReleaseMe *)&v58);
      return (unsigned int)v12;
    }
    v57 = v56;
    v54 = 0;
    v37 = (CAsyncReq_ExecQueryAsync *)CWin32DefaultArena::WbemMemAlloc(0x78u);
    v59[1] = v37;
    if ( v37 )
      Async = CAsyncReq_ExecQueryAsync::CAsyncReq_ExecQueryAsync(v37, this, v21, v18, a7, v56, a8);
    else
      Async = 0;
    if ( Async )
    {
      std::unique_ptr<CAsyncReq_ExecQueryAsync>::_Delete(&v54);
      v54 = Async;
      v39 = (struct IWbemContext *)*((_QWORD *)Async + 5);
      if ( v39 )
      {
        inited = CWbemNamespace::InitNewTask(this, Async, v9, a2, v39, a9);
        if ( inited < 0 )
        {
          v44 = GetMemLogObject();
          CMemoryLog::Write(v44, inited);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              681,
              WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
              (unsigned int)inited);
          }
          std::unique_ptr<CAsyncReq_ExecQueryAsync>::_Delete(&v54);
          CReleaseMe::release((CReleaseMe *)&v57);
          v12 = inited;
          goto LABEL_58;
        }
        CReleaseMe::release((CReleaseMe *)&v58);
        v12 = ConfigMgr::EnqueueRequest(Async);
        if ( v12 >= 0 )
        {
          v54 = 0;
          v41 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_100;
          }
          v42 = 683;
        }
        else
        {
          (*(void (__fastcall **)(struct _IWmiFinalizer *, _QWORD))(*(_QWORD *)v9 + 112LL))(v9, 0);
          v45 = GetMemLogObject();
          CMemoryLog::Write(v45, v12);
          v41 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_100;
          }
          v42 = 682;
        }
        v46 = (unsigned int)v12;
        goto LABEL_99;
      }
      v40 = GetMemLogObject();
      v12 = -2147217402;
      CMemoryLog::Write(v40, -2147217402);
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_100;
      }
      v42 = 680;
    }
    else
    {
      v47 = GetMemLogObject();
      v12 = -2147217402;
      CMemoryLog::Write(v47, -2147217402);
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_100;
      }
      v42 = 679;
    }
    v46 = 2147749894LL;
LABEL_99:
    WPP_SF_d(*((_QWORD *)v41 + 2), v42, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v46);
LABEL_100:
    std::unique_ptr<CAsyncReq_ExecQueryAsync>::_Delete(&v54);
    CReleaseMe::release((CReleaseMe *)&v57);
    goto LABEL_58;
  }
  v23 = GetMemLogObject();
  CMemoryLog::Write(v23, -2147217400);
  v24 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return 2147749896LL;
  }
  v25 = 670;
LABEL_109:
  WPP_SF_d(*((_QWORD *)v24 + 2), v25, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
  return 2147749896LL;
}

```

## disassembly

```asm
0x180022a90  mov     [rsp-38h+arg_0], rbx
0x180022a95  mov     [rsp-38h+arg_10], r8
0x180022a9a  mov     [rsp-38h+arg_8], edx
0x180022a9e  push    rbp
0x180022a9f  push    rsi
0x180022aa0  push    rdi
0x180022aa1  push    r12
0x180022aa3  push    r13
0x180022aa5  push    r14
0x180022aa7  push    r15
0x180022aa9  mov     rbp, rsp
0x180022aac  sub     rsp, 80h
0x180022ab3  mov     r14, r8
0x180022ab6  mov     r15, rcx
0x180022ab9  call    ?CheckNs@CWbemNamespace@@QEAAJXZ; CWbemNamespace::CheckNs(void)
0x180022abe  mov     esi, eax
0x180022ac0  test    eax, eax
0x180022ac2  jns     short loc_180022B17
0x180022ac4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180022aca  mov     edx, esi
0x180022acc  mov     rcx, rax
0x180022acf  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180022ad5  lea     rdi, WPP_GLOBAL_Control
0x180022adc  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ae3  cmp     rcx, rdi
0x180022ae6  jz      short loc_180022B10
0x180022ae8  mov     ebx, 1
0x180022aed  test    [rcx+1Ch], bl
0x180022af0  jz      short loc_180022B10
0x180022af2  cmp     byte ptr [rcx+19h], 2
0x180022af6  jb      short loc_180022B10
0x180022af8  mov     edx, 29Bh
0x180022afd  mov     r9d, esi
0x180022b00  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180022b07  mov     rcx, [rcx+10h]
0x180022b0b  call    WPP_SF_d
0x180022b10  mov     eax, esi
0x180022b12  jmp     loc_1800231C7
0x180022b17  lea     rdx, [rcx+0D8h]; struct CNtSecurityDescriptor *
0x180022b1e  mov     ebx, 1
0x180022b23  mov     byte ptr [rsp+80h+var_50], bl; bool
0x180022b27  mov     r12, [rbp+arg_28]
0x180022b2b  mov     [rsp+80h+var_60], r12; unsigned __int16 *
0x180022b30  lea     r9, aReadExecquery; "Read (ExecQuery)"
0x180022b37  mov     r8d, ebx; unsigned int
0x180022b3a  call    ?InnerAllowedWithSD@CWbemNamespace@@QEAA_NPEAVCNtSecurityDescriptor@@KPEBG1_N2@Z; CWbemNamespace::InnerAllowedWithSD(CNtSecurityDescriptor *,ulong,ushort const *,ushort const *,bool,bool)
0x180022b3f  test    al, al
0x180022b41  jnz     short loc_180022B87
0x180022b43  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180022b49  mov     esi, 80041003h
0x180022b4e  mov     edx, esi
0x180022b50  mov     rcx, rax
0x180022b53  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180022b59  lea     rdi, WPP_GLOBAL_Control
0x180022b60  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b67  cmp     rcx, rdi
0x180022b6a  jz      short loc_180022B10
0x180022b6c  test    [rcx+1Ch], bl
0x180022b6f  jz      short loc_180022B10
0x180022b71  cmp     byte ptr [rcx+19h], 2
0x180022b75  jb      short loc_180022B10
0x180022b77  mov     edx, 29Ch
0x180022b7c  mov     r9d, 80041003h
0x180022b82  jmp     loc_180022B00
0x180022b87  lea     rdi, WPP_GLOBAL_Control
0x180022b8e  mov     r13, [rbp+arg_20]
0x180022b92  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b99  cmp     rcx, rdi
0x180022b9c  jz      short loc_180022BD8
0x180022b9e  test    [rcx+1Ch], bl
0x180022ba1  jz      short loc_180022BD8
0x180022ba3  mov     rsi, [rbp+arg_40]
0x180022baa  cmp     byte ptr [rcx+19h], 5
0x180022bae  jb      short loc_180022BDF
0x180022bb0  mov     edx, 29Dh
0x180022bb5  mov     eax, [r15+130h]
0x180022bbc  mov     dword ptr [rsp+80h+var_50], eax
0x180022bc0  mov     [rsp+80h+var_58], rsi
0x180022bc5  mov     [rsp+80h+var_60], r12
0x180022bca  mov     r9, r13
0x180022bcd  mov     rcx, [rcx+10h]
0x180022bd1  call    WPP_SF_SSql
0x180022bd6  jmp     short loc_180022BDF
0x180022bd8  mov     rsi, [rbp+arg_40]
0x180022bdf  test    r14, r14
0x180022be2  jnz     short loc_180022C2A
0x180022be4  test    rsi, rsi
0x180022be7  jnz     short loc_180022C2A
0x180022be9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180022bef  mov     edx, 80041008h
0x180022bf4  mov     rcx, rax
0x180022bf7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180022bfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c04  cmp     rcx, rdi
0x180022c07  jz      loc_1800231C2
0x180022c0d  test    [rcx+1Ch], bl
0x180022c10  jz      loc_1800231C2
0x180022c16  cmp     byte ptr [rcx+19h], 2
0x180022c1a  jb      loc_1800231C2
0x180022c20  mov     edx, 29Eh
0x180022c25  jmp     loc_1800231AC
0x180022c2a  test    r13, r13
0x180022c2d  jz      loc_18002317C
0x180022c33  test    r12, r12
0x180022c36  jz      loc_18002317C
0x180022c3c  xor     eax, eax
0x180022c3e  cmp     ax, [r13+0]
0x180022c43  jz      loc_18002314A
0x180022c49  cmp     ax, [r12]
0x180022c4e  jz      loc_18002314A
0x180022c54  mov     edx, cs:?g_QueryLimit@@3KA; unsigned __int64
0x180022c5a  mov     rcx, r12; unsigned __int16 *
0x180022c5d  call    ?wcslen_max@@YA_KPEBG_K@Z; wcslen_max(ushort const *,unsigned __int64)
0x180022c62  cmp     rax, rdx
0x180022c65  jbe     short loc_180022CB0
0x180022c67  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180022c6d  mov     esi, 8004106Ch
0x180022c72  mov     edx, esi
0x180022c74  mov     rcx, rax
0x180022c77  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180022c7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c84  cmp     rcx, rdi
0x180022c87  jz      loc_180022B10
0x180022c8d  test    [rcx+1Ch], bl
0x180022c90  jz      loc_180022B10
0x180022c96  cmp     byte ptr [rcx+19h], 2
0x180022c9a  jb      loc_180022B10
0x180022ca0  mov     edx, 2A1h
0x180022ca5  mov     r9d, 8004106Ch
0x180022cab  jmp     loc_180022B00
0x180022cb0  test    [rbp+arg_30], 0FFEDFC7Dh
0x180022cb7  jz      short loc_180022CFA
0x180022cb9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180022cbf  mov     edx, 80041008h
0x180022cc4  mov     rcx, rax
0x180022cc7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180022ccd  mov     rcx, cs:WPP_GLOBAL_Control
0x180022cd4  cmp     rcx, rdi
0x180022cd7  jz      loc_1800231C2
0x180022cdd  test    [rcx+1Ch], bl
0x180022ce0  jz      loc_1800231C2
0x180022ce6  cmp     byte ptr [rcx+19h], 2
0x180022cea  jb      loc_1800231C2
0x180022cf0  mov     edx, 2A2h
0x180022cf5  jmp     loc_1800231AC
0x180022cfa  mov     [rbp+var_38], 0
0x180022d02  test    r14, r14
0x180022d05  jnz     short loc_180022D6D
0x180022d07  lea     rax, [rbp+var_38]
0x180022d0b  mov     [rsp+80h+var_60], rax; struct IWbemObjectSink **
0x180022d10  lea     r9, [rbp+arg_10]; struct _IWmiFinalizer **
0x180022d14  mov     r8, rsi; struct IWbemObjectSink *
0x180022d17  mov     rdx, [rbp+arg_38]; struct IWbemContext *
0x180022d1b  mov     rcx, r15; this
0x180022d1e  call    ?CreateAsyncFinalizer@CWbemNamespace@@QEAAJPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAPEAU_IWmiFinalizer@@PEAPEAU3@@Z; CWbemNamespace::CreateAsyncFinalizer(IWbemContext *,IWbemObjectSink *,_IWmiFinalizer * *,IWbemObjectSink * *)
0x180022d23  mov     esi, eax
0x180022d25  test    eax, eax
0x180022d27  jns     short loc_180022D67
0x180022d29  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180022d2f  mov     edx, esi
0x180022d31  mov     rcx, rax
0x180022d34  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180022d3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d41  cmp     rcx, rdi
0x180022d44  jz      loc_180022B10
0x180022d4a  test    [rcx+1Ch], bl
0x180022d4d  jz      loc_180022B10
0x180022d53  cmp     byte ptr [rcx+19h], 2
0x180022d57  jb      loc_180022B10
0x180022d5d  mov     edx, 2A3h
0x180022d62  jmp     loc_180022AFD
0x180022d67  mov     r14, [rbp+arg_10]
0x180022d6b  jmp     short loc_180022DD5
0x180022d6d  mov     rax, [r14]
0x180022d70  lea     r8, [rbp+var_38]
0x180022d74  xor     edx, edx
0x180022d76  mov     rcx, r14
0x180022d79  mov     rax, [rax+40h]
0x180022d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d82  mov     esi, eax
0x180022d84  test    eax, eax
0x180022d86  jns     short loc_180022DC6
0x180022d88  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180022d8e  mov     edx, esi
0x180022d90  mov     rcx, rax
0x180022d93  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180022d99  mov     rcx, cs:WPP_GLOBAL_Control
0x180022da0  cmp     rcx, rdi
0x180022da3  jz      loc_180022B10
0x180022da9  test    [rcx+1Ch], bl
0x180022dac  jz      loc_180022B10
0x180022db2  cmp     byte ptr [rcx+19h], 2
0x180022db6  jb      loc_180022B10
0x180022dbc  mov     edx, 2A4h
0x180022dc1  jmp     loc_180022AFD
0x180022dc6  mov     rax, [r14]
0x180022dc9  mov     rcx, r14
0x180022dcc  mov     rax, [rax+8]
0x180022dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022dd5  mov     rax, [rbp+var_38]
0x180022dd9  mov     [rbp+var_20], rax
0x180022ddd  mov     [rbp+var_18], r14
0x180022de1  mov     rax, [rbp+arg_38]
0x180022de5  mov     [rsp+80h+var_60], rax; struct IWbemContext *
0x180022dea  mov     r9, r14; struct _IWmiFinalizer *
0x180022ded  mov     r8, r12; unsigned __int16 *
0x180022df0  lea     rdx, aIwbemservicesE_1; "IWbemServices::ExecQuery"
0x180022df7  mov     rcx, r15; this
0x180022dfa  call    ?PublishInfo@CWbemNamespace@@QEAAJPEBG0PEAU_IWmiFinalizer@@PEAUIWbemContext@@@Z; CWbemNamespace::PublishInfo(ushort const *,ushort const *,_IWmiFinalizer *,IWbemContext *)
0x180022dff  mov     esi, eax
0x180022e01  test    eax, eax
0x180022e03  jns     short loc_180022E5E
0x180022e05  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180022e0b  mov     edx, esi
0x180022e0d  mov     rcx, rax
0x180022e10  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180022e16  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e1d  cmp     rcx, rdi
0x180022e20  jz      short loc_180022E46
0x180022e22  test    [rcx+1Ch], bl
0x180022e25  jz      short loc_180022E46
0x180022e27  cmp     byte ptr [rcx+19h], 2
0x180022e2b  jb      short loc_180022E46
0x180022e2d  mov     edx, 2A5h
0x180022e32  mov     r9d, esi
0x180022e35  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180022e3c  mov     rcx, [rcx+10h]
0x180022e40  call    WPP_SF_d
0x180022e45  nop
0x180022e46  lea     rcx, [rbp+var_18]; this
0x180022e4a  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x180022e4f  nop
0x180022e50  lea     rcx, [rbp+var_20]; this
0x180022e54  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x180022e59  jmp     loc_180022B10
0x180022e5e  mov     ecx, [r15+130h]
0x180022e65  cmp     ecx, 0FFFFFFFFh
0x180022e68  jz      short loc_180022EC1
0x180022e6a  cmp     cs:?g_cntWinmgmtTraceLogging@@3_JA, 0; __int64 g_cntWinmgmtTraceLogging
0x180022e72  jz      short loc_180022EC1
0x180022e74  lea     rax, aSemiSync; "(Semi)Sync"
0x180022e7b  lea     r8, aAsync; "Async"
0x180022e82  cmp     [rbp+arg_40], 0
0x180022e8a  cmovz   r8, rax
0x180022e8e  mov     rax, [r15+58h]
0x180022e92  mov     [rsp+80h+var_48], rax
0x180022e97  mov     dword ptr [rsp+80h+var_50], ecx
0x180022e9b  mov     eax, [r15+17Ch]
0x180022ea2  mov     dword ptr [rsp+80h+var_58], eax
0x180022ea6  mov     eax, [rbp+arg_30]
0x180022ea9  mov     dword ptr [rsp+80h+var_60], eax
0x180022ead  mov     r9, r12
0x180022eb0  mov     edx, 2
0x180022eb5  mov     ecx, [r14+2D4h]; unsigned int
0x180022ebc  call    ?WinmgmtTelemetrylogging@@YAXKZZ; WinmgmtTelemetrylogging(ulong,...)
0x180022ec1  mov     [rbp+var_30], 0
0x180022ec9  mov     rcx, [rbp+var_38]
0x180022ecd  mov     rax, [rcx]
0x180022ed0  lea     r8, [rbp+var_30]
0x180022ed4  lea     rdx, IID_IWbemObjectSinkEx
0x180022edb  mov     rax, [rax]
0x180022ede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ee3  mov     esi, eax
0x180022ee5  test    eax, eax
0x180022ee7  jns     short loc_180022F27
0x180022ee9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180022eef  mov     edx, esi
0x180022ef1  mov     rcx, rax
0x180022ef4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180022efa  mov     rcx, cs:WPP_GLOBAL_Control
0x180022f01  cmp     rcx, rdi
0x180022f04  jz      loc_180022E46
0x180022f0a  test    [rcx+1Ch], bl
0x180022f0d  jz      loc_180022E46
0x180022f13  cmp     byte ptr [rcx+19h], 2
0x180022f17  jb      loc_180022E46
0x180022f1d  mov     edx, 2A6h
0x180022f22  jmp     loc_180022E32
0x180022f27  mov     rax, [rbp+var_30]
0x180022f2b  mov     [rbp+var_28], rax
0x180022f2f  mov     [rbp+var_40], 0
0x180022f37  mov     ecx, 78h ; 'x'
0x180022f3c  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180022f42  mov     [rbp+var_10], rax
0x180022f46  test    rax, rax
0x180022f49  jz      short loc_180022F7A
0x180022f4b  mov     rcx, [rbp+arg_38]
0x180022f4f  mov     [rsp+80h+var_50], rcx; struct IWbemContext *
0x180022f54  mov     rcx, [rbp+var_30]
0x180022f58  mov     [rsp+80h+var_58], rcx; struct IWbemObjectSinkEx *
0x180022f5d  mov     ecx, [rbp+arg_30]
0x180022f60  mov     dword ptr [rsp+80h+var_60], ecx; int
0x180022f64  mov     r9, r12; unsigned __int16 *
0x180022f67  mov     r8, r13; unsigned __int16 *
0x180022f6a  mov     rdx, r15; struct CWbemNamespace *
0x180022f6d  mov     rcx, rax; this
0x180022f70  call    ??0CAsyncReq_ExecQueryAsync@@QEAA@PEAVCWbemNamespace@@PEAG1JPEAUIWbemObjectSinkEx@@PEAUIWbemContext@@@Z; CAsyncReq_ExecQueryAsync::CAsyncReq_ExecQueryAsync(CWbemNamespace *,ushort *,ushort *,long,IWbemObjectSinkEx *,IWbemContext *)
0x180022f75  mov     rsi, rax
0x180022f78  jmp     short loc_180022F7C
0x180022f7a  xor     esi, esi
  ... truncated ...
```
