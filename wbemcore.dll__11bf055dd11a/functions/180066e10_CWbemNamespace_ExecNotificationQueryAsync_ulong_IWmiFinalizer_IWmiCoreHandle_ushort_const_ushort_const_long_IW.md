# CWbemNamespace::_ExecNotificationQueryAsync(ulong,_IWmiFinalizer *,_IWmiCoreHandle *,ushort * const,ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x180066e10`
- end: `0x180067718`
- name: `?_ExecNotificationQueryAsync@CWbemNamespace@@MEAAJKPEAU_IWmiFinalizer@@PEAU_IWmiCoreHandle@@QEAG2JPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `2312`
- prototype: `__int64 __fastcall(CWbemNamespace *this, unsigned int, struct _IWmiFinalizer *, struct _IWmiCoreHandle *, unsigned __int16 *const, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180066730`
- `0x180066cf0`

## callees

- `0x18000b140`
- `0x18000b274`
- `0x18000f474`
- `0x18001f6d0`
- `0x18003cfe0`
- `0x1800421ac`
- `0x180047ed0`
- `0x180049580`
- `0x1800523c0`
- `0x18005fc58`
- `0x180062ed0`
- `0x180065e88`
- `0x1800661f4`
- `0x180066e10`
- `0x1800711a0`
- `0x1800903d0`
- `0x1800a1fc8`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006731a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006731a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006760e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006760e`
- `wbemcomn!IsNtSetupRunning` at `0x1800672f9`
- `wbemcomn!IsNtSetupRunning` at `0x1800672f9`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180067408`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180067408`
- `wbemcomn!GetMemLogObject` at `0x180066e8f`
- `wbemcomn!GetMemLogObject` at `0x180066efe`
- `wbemcomn!GetMemLogObject` at `0x180066fa5`
- `wbemcomn!GetMemLogObject` at `0x180067010`
- `wbemcomn!GetMemLogObject` at `0x18006707a`
- `wbemcomn!GetMemLogObject` at `0x1800670d0`
- `wbemcomn!GetMemLogObject` at `0x18006714a`
- `wbemcomn!GetMemLogObject` at `0x1800671b8`
- `wbemcomn!GetMemLogObject` at `0x18006723a`
- `wbemcomn!GetMemLogObject` at `0x180067328`
- `wbemcomn!GetMemLogObject` at `0x1800673a4`
- `wbemcomn!GetMemLogObject` at `0x18006746b`
- `wbemcomn!GetMemLogObject` at `0x1800674d3`
- `wbemcomn!GetMemLogObject` at `0x18006755c`
- `wbemcomn!GetMemLogObject` at `0x1800675c1`
- `wbemcomn!GetMemLogObject` at `0x180067638`
- `wbemcomn!GetMemLogObject` at `0x1800676ab`
- `wbemcomn!GetMemLogObject` at `0x180066e8f`
- `wbemcomn!GetMemLogObject` at `0x180066efe`
- `wbemcomn!GetMemLogObject` at `0x180066fa5`
- `wbemcomn!GetMemLogObject` at `0x180067010`
- `wbemcomn!GetMemLogObject` at `0x18006707a`
- `wbemcomn!GetMemLogObject` at `0x1800670d0`
- `wbemcomn!GetMemLogObject` at `0x18006714a`
- `wbemcomn!GetMemLogObject` at `0x1800671b8`
- `wbemcomn!GetMemLogObject` at `0x18006723a`
- `wbemcomn!GetMemLogObject` at `0x180067328`
- `wbemcomn!GetMemLogObject` at `0x1800673a4`
- `wbemcomn!GetMemLogObject` at `0x18006746b`
- `wbemcomn!GetMemLogObject` at `0x1800674d3`
- `wbemcomn!GetMemLogObject` at `0x18006755c`
- `wbemcomn!GetMemLogObject` at `0x1800675c1`
- `wbemcomn!GetMemLogObject` at `0x180067638`
- `wbemcomn!GetMemLogObject` at `0x1800676ab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066e9a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066f0e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066fb3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180067020`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006708a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800670de`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180067155`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800671c3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180067245`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180067338`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800673af`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006747b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800674e3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180067567`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800675cc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180067648`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800676b9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066e9a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066f0e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066fb3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180067020`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006708a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800670de`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180067155`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800671c3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180067245`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180067338`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800673af`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006747b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800674e3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180067567`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800675cc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180067648`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800676b9`

## string_xrefs

- `0x180066ee8`: `Read (ExecNotificationQuery)`
- `0x180067225`: `IWbemServices::ExecNotificationQuery`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CWbemNamespace::_ExecNotificationQueryAsync(
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
  struct _IWmiFinalizer *v9; // rdi
  unsigned __int16 *v11; // rsi
  unsigned __int16 *v12; // r13
  CWbemNamespace *v13; // rcx
  int inited; // ebx
  CMemoryLog *MemLogObject; // rax
  CClientCnt *v16; // rcx
  __int64 v17; // rdx
  int v19; // r8d
  CMemoryLog *v20; // rax
  unsigned int v21; // edi
  CClientCnt *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r9
  struct IWbemObjectSink *v25; // r15
  int v26; // r12d
  CMemoryLog *v27; // rax
  CClientCnt *v28; // rcx
  __int64 v29; // rdx
  CMemoryLog *v30; // rax
  unsigned __int64 v31; // rax
  struct IWbemObjectSink *v32; // r9
  unsigned __int64 v33; // rdx
  CMemoryLog *v34; // rax
  CMemoryLog *v35; // rax
  CMemoryLog *v36; // rax
  CMemoryLog *v37; // rax
  CMemoryLog *v38; // rax
  const wchar_t *v39; // r8
  struct IWbemEventSubsystem_m4 *EssSink; // r12
  HANDLE EventW; // rax
  void *v42; // r15
  CMemoryLog *v43; // rax
  CClientCnt *v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // r9
  CMemoryLog *v47; // rax
  CAsyncReq_ExecNotificationQueryAsync *v48; // rax
  CAsyncReq_ExecNotificationQueryAsync *v49; // rsi
  CMemoryLog *v50; // rax
  struct IWbemContext *v51; // rax
  CMemoryLog *v52; // rax
  CClientCnt *v53; // rcx
  __int64 v54; // rdx
  __int64 v55; // r9
  CMemoryLog *v56; // rax
  CMemoryLog *v57; // rax
  CMemoryLog *v58; // rax
  CMemoryLog *v59; // rax
  struct IWbemObjectSink **v60; // [rsp+28h] [rbp-79h]
  bool v61; // [rsp+30h] [rbp-71h]
  struct IWbemObjectSink *v62; // [rsp+30h] [rbp-71h]
  struct IWbemObjectSinkEx *v63; // [rsp+38h] [rbp-69h]
  struct IWbemEventSubsystem_m4 *v64; // [rsp+58h] [rbp-49h] BYREF
  int v65; // [rsp+60h] [rbp-41h] BYREF
  HANDLE v66; // [rsp+68h] [rbp-39h] BYREF
  struct IWbemObjectSinkEx *v67; // [rsp+70h] [rbp-31h] BYREF
  struct IWbemObjectSink *v68; // [rsp+78h] [rbp-29h] BYREF
  struct IWbemObjectSinkEx *v69; // [rsp+80h] [rbp-21h] BYREF
  struct IWbemObjectSink *v70; // [rsp+88h] [rbp-19h] BYREF
  struct _IWmiFinalizer *v71; // [rsp+90h] [rbp-11h] BYREF
  CAsyncReq_ExecNotificationQueryAsync *v72; // [rsp+98h] [rbp-9h]
  struct _IWmiFinalizer *v74; // [rsp+F8h] [rbp+57h] BYREF

  v74 = a3;
  v9 = a3;
  v11 = a6;
  v12 = a5;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      280,
      (unsigned int)WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
      (_DWORD)a5,
      (__int64)a6);
  }
  inited = CWbemNamespace::CheckNs(this);
  if ( inited < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, inited);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)inited;
    }
    v17 = 281;
    goto LABEL_10;
  }
  if ( !CWbemNamespace::InnerAllowedWithSD(
          v13,
          (CWbemNamespace *)((char *)this + 216),
          1u,
          L"Read (ExecNotificationQuery)",
          v11,
          v61,
          1) )
  {
    v20 = GetMemLogObject();
    v21 = -2147217405;
    CMemoryLog::Write(v20, -2147217405);
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v21;
    }
    v23 = 282;
    v24 = 2147749891LL;
LABEL_17:
    WPP_SF_d(*((_QWORD *)v22 + 2), v23, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v24);
    return v21;
  }
  if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    v26 = a7;
    v25 = a9;
  }
  else
  {
    v25 = a9;
    v26 = a7;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      WPP_SF_SSDq(*((_QWORD *)WPP_GLOBAL_Control + 2), 283, v19, (_DWORD)v12, (__int64)v11, a7, (char)a9);
  }
  if ( v9 || v25 )
  {
    if ( !v12 || !v11 || !*v12 )
    {
      v59 = GetMemLogObject();
      CMemoryLog::Write(v59, -2147217400);
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749896LL;
      }
      v29 = 285;
      goto LABEL_124;
    }
    if ( !*v11 )
    {
      v30 = GetMemLogObject();
      v21 = -2147217320;
      CMemoryLog::Write(v30, -2147217320);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v21;
      }
      v23 = 286;
      v24 = 2147749976LL;
      goto LABEL_17;
    }
    v31 = wcslen_max(v11, (unsigned int)g_QueryLimit);
    if ( v31 > v33 )
    {
      v34 = GetMemLogObject();
      v21 = -2147217300;
      CMemoryLog::Write(v34, -2147217300);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v21;
      }
      v23 = 287;
      v24 = 2147749996LL;
      goto LABEL_17;
    }
    if ( (v26 & 0xFFFDFF7F) != 0 )
    {
      v35 = GetMemLogObject();
      CMemoryLog::Write(v35, -2147217400);
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749896LL;
      }
      v29 = 288;
      goto LABEL_124;
    }
    *((_DWORD *)this + 32) = (_DWORD)v32;
    v68 = v32;
    if ( v9 )
    {
      inited = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, struct IWbemObjectSink **))(*(_QWORD *)v9 + 64LL))(
                 v9,
                 0,
                 &v68);
      if ( inited < 0 )
      {
        v37 = GetMemLogObject();
        CMemoryLog::Write(v37, inited);
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)inited;
        }
        v17 = 290;
LABEL_10:
        WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)inited);
        return (unsigned int)inited;
      }
      (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v9 + 8LL))(v9);
    }
    else
    {
      inited = CWbemNamespace::CreateAsyncFinalizer(this, a8, v25, &v74, &v68);
      if ( inited < 0 )
      {
        v36 = GetMemLogObject();
        CMemoryLog::Write(v36, inited);
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)inited;
        }
        v17 = 289;
        goto LABEL_10;
      }
      v9 = v74;
    }
    v70 = v68;
    v71 = v9;
    inited = CWbemNamespace::PublishInfo(this, L"IWbemServices::ExecNotificationQuery", v11, v9, a8);
    if ( inited < 0 )
    {
      v38 = GetMemLogObject();
      CMemoryLog::Write(v38, inited);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          291,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)inited);
      }
      goto LABEL_119;
    }
    if ( *((_DWORD *)this + 76) != -1 && g_cntWinmgmtTraceLogging )
    {
      v39 = L"Async";
      if ( !v25 )
        v39 = L"(Semi)Sync";
      LODWORD(v63) = *((_DWORD *)this + 76);
      LODWORD(v62) = *((_DWORD *)this + 95);
      LODWORD(v60) = v26;
      WinmgmtTelemetrylogging(*((_DWORD *)v9 + 181), 10, v39, v11, v60, v62, v63, *((_QWORD *)this + 11));
    }
    EssSink = ConfigMgr::GetEssSink();
    v64 = EssSink;
    if ( IsNtSetupRunning() || !EssSink )
    {
      v58 = GetMemLogObject();
      inited = -2147217396;
      CMemoryLog::Write(v58, -2147217396);
      v44 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_118;
      }
      v45 = 292;
      v46 = 2147749900LL;
LABEL_117:
      WPP_SF_d(*((_QWORD *)v44 + 2), v45, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v46);
      goto LABEL_118;
    }
    EventW = CreateEventW(0, 0, 0, 0);
    v42 = EventW;
    if ( !EventW )
    {
      v43 = GetMemLogObject();
      inited = -2147217402;
      CMemoryLog::Write(v43, -2147217402);
      v44 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_118;
      }
      v45 = 293;
      v46 = 2147749894LL;
      goto LABEL_117;
    }
    v66 = EventW;
    v65 = 0;
    v69 = 0;
    inited = ((__int64 (__fastcall *)(struct IWbemObjectSink *, GUID *, struct IWbemObjectSinkEx **))v68->lpVtbl->QueryInterface)(
               v68,
               &IID_IWbemObjectSinkEx,
               &v69);
    if ( inited < 0 )
    {
      v47 = GetMemLogObject();
      CMemoryLog::Write(v47, inited);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          294,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)inited);
      }
      goto LABEL_83;
    }
    v67 = v69;
    v48 = (CAsyncReq_ExecNotificationQueryAsync *)CWin32DefaultArena::WbemMemAlloc(0x90u);
    v72 = v48;
    if ( v48 )
      v49 = CAsyncReq_ExecNotificationQueryAsync::CAsyncReq_ExecNotificationQueryAsync(
              v48,
              this,
              EssSink,
              v12,
              v11,
              a7,
              v69,
              a8,
              &v65,
              v42);
    else
      v49 = 0;
    v72 = v49;
    if ( !v49 )
    {
      v50 = GetMemLogObject();
      inited = -2147217402;
      CMemoryLog::Write(v50, -2147217402);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          295,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          2147749894LL);
      }
      goto LABEL_92;
    }
    v51 = (struct IWbemContext *)*((_QWORD *)v49 + 5);
    if ( v51 )
    {
      inited = CWbemNamespace::InitNewTask(this, v49, v9, a2, v51, a9);
      if ( inited >= 0 )
      {
        CReleaseMe::release((CReleaseMe *)&v70);
        inited = ConfigMgr::EnqueueRequest(v49);
        if ( inited >= 0 )
        {
          v72 = 0;
          WaitForSingleObject(v42, 0xFFFFFFFF);
          inited = v65;
          if ( v65 < 0 )
          {
            (*(void (__fastcall **)(struct _IWmiFinalizer *, _QWORD))(*(_QWORD *)v9 + 112LL))(v9, 0);
            inited = v65;
          }
          goto LABEL_92;
        }
        (*(void (__fastcall **)(struct _IWmiFinalizer *, _QWORD))(*(_QWORD *)v9 + 112LL))(v9, 0);
        v57 = GetMemLogObject();
        CMemoryLog::Write(v57, inited);
        v53 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_99;
        }
        v54 = 298;
      }
      else
      {
        v56 = GetMemLogObject();
        CMemoryLog::Write(v56, inited);
        v53 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_99;
        }
        v54 = 297;
      }
      v55 = (unsigned int)inited;
    }
    else
    {
      v52 = GetMemLogObject();
      inited = -2147217402;
      CMemoryLog::Write(v52, -2147217402);
      v53 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_99;
      }
      v54 = 296;
      v55 = 2147749894LL;
    }
    WPP_SF_d(*((_QWORD *)v53 + 2), v54, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v55);
LABEL_99:
    CAsyncReq_ExecNotificationQueryAsync::`scalar deleting destructor'(v49, 1u);
LABEL_92:
    CReleaseMe::release((CReleaseMe *)&v67);
LABEL_83:
    CCloseMe::~CCloseMe((CCloseMe *)&v66);
LABEL_118:
    CReleaseMe::release((CReleaseMe *)&v64);
LABEL_119:
    CReleaseMe::release((CReleaseMe *)&v71);
    CReleaseMe::release((CReleaseMe *)&v70);
    return (unsigned int)inited;
  }
  v27 = GetMemLogObject();
  CMemoryLog::Write(v27, -2147217400);
  v28 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return 2147749896LL;
  }
  v29 = 284;
LABEL_124:
  WPP_SF_d(*((_QWORD *)v28 + 2), v29, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
  return 2147749896LL;
}

```

## disassembly

```asm
0x180066e10  mov     rax, rsp
0x180066e13  mov     [rax+8], rbx
0x180066e17  mov     [rax+18h], r8
0x180066e1b  mov     [rax+10h], edx
0x180066e1e  push    rbp
0x180066e1f  push    rsi
0x180066e20  push    rdi
0x180066e21  push    r12
0x180066e23  push    r13
0x180066e25  push    r14
0x180066e27  push    r15
0x180066e29  lea     rbp, [rax-3Fh]
0x180066e2d  sub     rsp, 0A0h
0x180066e34  mov     rdi, r8
0x180066e37  mov     r14, rcx
0x180066e3a  lea     r15, WPP_GLOBAL_Control
0x180066e41  lea     r12, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180066e48  mov     rsi, [rbp+37h+arg_28]
0x180066e4c  mov     r13, [rbp+37h+arg_20]
0x180066e50  mov     rcx, cs:WPP_GLOBAL_Control
0x180066e57  cmp     rcx, r15
0x180066e5a  jz      short loc_180066E81
0x180066e5c  test    byte ptr [rcx+1Ch], 1
0x180066e60  jz      short loc_180066E81
0x180066e62  cmp     byte ptr [rcx+19h], 5
0x180066e66  jb      short loc_180066E81
0x180066e68  mov     edx, 118h
0x180066e6d  mov     [rsp+0D0h+var_B0], rsi
0x180066e72  mov     r9, r13
0x180066e75  mov     r8, r12
0x180066e78  mov     rcx, [rcx+10h]
0x180066e7c  call    WPP_SF_SS
0x180066e81  mov     rcx, r14; this
0x180066e84  call    ?CheckNs@CWbemNamespace@@QEAAJXZ; CWbemNamespace::CheckNs(void)
0x180066e89  mov     ebx, eax
0x180066e8b  test    eax, eax
0x180066e8d  jns     short loc_180066ED3
0x180066e8f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180066e95  mov     edx, ebx
0x180066e97  mov     rcx, rax
0x180066e9a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180066ea0  mov     rcx, cs:WPP_GLOBAL_Control
0x180066ea7  cmp     rcx, r15
0x180066eaa  jz      short loc_180066ECC
0x180066eac  test    byte ptr [rcx+1Ch], 1
0x180066eb0  jz      short loc_180066ECC
0x180066eb2  cmp     byte ptr [rcx+19h], 2
0x180066eb6  jb      short loc_180066ECC
0x180066eb8  mov     edx, 119h
0x180066ebd  mov     r8, r12
0x180066ec0  mov     r9d, ebx
0x180066ec3  mov     rcx, [rcx+10h]
0x180066ec7  call    WPP_SF_d
0x180066ecc  mov     eax, ebx
0x180066ece  jmp     loc_1800676FD
0x180066ed3  lea     rdx, [r14+0D8h]; struct CNtSecurityDescriptor *
0x180066eda  mov     ebx, 1
0x180066edf  mov     byte ptr [rsp+0D0h+var_A0], bl; bool
0x180066ee3  mov     [rsp+0D0h+var_B0], rsi; unsigned __int16 *
0x180066ee8  lea     r9, aReadExecnotifi; "Read (ExecNotificationQuery)"
0x180066eef  mov     r8d, ebx; unsigned int
0x180066ef2  call    ?InnerAllowedWithSD@CWbemNamespace@@QEAA_NPEAVCNtSecurityDescriptor@@KPEBG1_N2@Z; CWbemNamespace::InnerAllowedWithSD(CNtSecurityDescriptor *,ulong,ushort const *,ushort const *,bool,bool)
0x180066ef7  xor     r9d, r9d
0x180066efa  test    al, al
0x180066efc  jnz     short loc_180066F49
0x180066efe  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180066f04  mov     edi, 80041003h
0x180066f09  mov     edx, edi
0x180066f0b  mov     rcx, rax
0x180066f0e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180066f14  mov     rcx, cs:WPP_GLOBAL_Control
0x180066f1b  cmp     rcx, r15
0x180066f1e  jz      short loc_180066F42
0x180066f20  test    [rcx+1Ch], bl
0x180066f23  jz      short loc_180066F42
0x180066f25  cmp     byte ptr [rcx+19h], 2
0x180066f29  jb      short loc_180066F42
0x180066f2b  mov     edx, 11Ah
0x180066f30  mov     r9d, 80041003h
0x180066f36  mov     r8, r12
0x180066f39  mov     rcx, [rcx+10h]
0x180066f3d  call    WPP_SF_d
0x180066f42  mov     eax, edi
0x180066f44  jmp     loc_1800676FD
0x180066f49  mov     rcx, cs:WPP_GLOBAL_Control
0x180066f50  cmp     rcx, r15
0x180066f53  jz      short loc_180066F90
0x180066f55  test    [rcx+1Ch], bl
0x180066f58  jz      short loc_180066F90
0x180066f5a  mov     r15, [rbp+37h+arg_40]
0x180066f61  mov     r12d, [rbp+37h+arg_30]
0x180066f65  cmp     byte ptr [rcx+19h], 5
0x180066f69  jb      short loc_180066F9B
0x180066f6b  mov     edx, 11Bh
0x180066f70  mov     [rsp+0D0h+var_A0], r15
0x180066f75  mov     dword ptr [rsp+0D0h+var_A8], r12d
0x180066f7a  mov     [rsp+0D0h+var_B0], rsi
0x180066f7f  mov     r9, r13
0x180066f82  mov     rcx, [rcx+10h]
0x180066f86  call    WPP_SF_SSDq
0x180066f8b  xor     r9d, r9d
0x180066f8e  jmp     short loc_180066F9B
0x180066f90  mov     r12d, [rbp+37h+arg_30]
0x180066f94  mov     r15, [rbp+37h+arg_40]
0x180066f9b  test    rdi, rdi
0x180066f9e  jnz     short loc_180066FED
0x180066fa0  test    r15, r15
0x180066fa3  jnz     short loc_180066FED
0x180066fa5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180066fab  mov     edx, 80041008h
0x180066fb0  mov     rcx, rax
0x180066fb3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180066fb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180066fc0  lea     rax, WPP_GLOBAL_Control
0x180066fc7  cmp     rcx, rax
0x180066fca  jz      loc_1800676F8
0x180066fd0  test    [rcx+1Ch], bl
0x180066fd3  jz      loc_1800676F8
0x180066fd9  cmp     byte ptr [rcx+19h], 2
0x180066fdd  jb      loc_1800676F8
0x180066fe3  mov     edx, 11Ch
0x180066fe8  jmp     loc_1800676E2
0x180066fed  test    r13, r13
0x180066ff0  jz      loc_1800676AB
0x180066ff6  test    rsi, rsi
0x180066ff9  jz      loc_1800676AB
0x180066fff  cmp     [r13+0], r9w
0x180067004  jz      loc_1800676AB
0x18006700a  cmp     [rsi], r9w
0x18006700e  jnz     short loc_180067067
0x180067010  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180067016  mov     edi, 80041058h
0x18006701b  mov     edx, edi
0x18006701d  mov     rcx, rax
0x180067020  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180067026  mov     rcx, cs:WPP_GLOBAL_Control
0x18006702d  lea     rax, WPP_GLOBAL_Control
0x180067034  cmp     rcx, rax
0x180067037  jz      loc_180066F42
0x18006703d  test    [rcx+1Ch], bl
0x180067040  jz      loc_180066F42
0x180067046  cmp     byte ptr [rcx+19h], 2
0x18006704a  jb      loc_180066F42
0x180067050  mov     edx, 11Eh
0x180067055  mov     r9d, 80041058h
0x18006705b  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180067062  jmp     loc_180066F39
0x180067067  mov     edx, cs:?g_QueryLimit@@3KA; unsigned __int64
0x18006706d  mov     rcx, rsi; unsigned __int16 *
0x180067070  call    ?wcslen_max@@YA_KPEBG_K@Z; wcslen_max(ushort const *,unsigned __int64)
0x180067075  cmp     rax, rdx
0x180067078  jbe     short loc_1800670C7
0x18006707a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180067080  mov     edi, 8004106Ch
0x180067085  mov     edx, edi
0x180067087  mov     rcx, rax
0x18006708a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180067090  mov     rcx, cs:WPP_GLOBAL_Control
0x180067097  lea     rax, WPP_GLOBAL_Control
0x18006709e  cmp     rcx, rax
0x1800670a1  jz      loc_180066F42
0x1800670a7  test    [rcx+1Ch], bl
0x1800670aa  jz      loc_180066F42
0x1800670b0  cmp     byte ptr [rcx+19h], 2
0x1800670b4  jb      loc_180066F42
0x1800670ba  mov     edx, 11Fh
0x1800670bf  mov     r9d, 8004106Ch
0x1800670c5  jmp     short loc_18006705B
0x1800670c7  test    r12d, 0FFFDFF7Fh
0x1800670ce  jz      short loc_180067118
0x1800670d0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800670d6  mov     edx, 80041008h
0x1800670db  mov     rcx, rax
0x1800670de  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800670e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800670eb  lea     rax, WPP_GLOBAL_Control
0x1800670f2  cmp     rcx, rax
0x1800670f5  jz      loc_1800676F8
0x1800670fb  test    [rcx+1Ch], bl
0x1800670fe  jz      loc_1800676F8
0x180067104  cmp     byte ptr [rcx+19h], 2
0x180067108  jb      loc_1800676F8
0x18006710e  mov     edx, 120h
0x180067113  jmp     loc_1800676E2
0x180067118  mov     [r14+80h], r9d
0x18006711f  mov     [rbp+37h+var_60], r9
0x180067123  test    rdi, rdi
0x180067126  jnz     short loc_18006719D
0x180067128  lea     rax, [rbp+37h+var_60]
0x18006712c  mov     [rsp+0D0h+var_B0], rax; struct IWbemObjectSink **
0x180067131  lea     r9, [rbp+37h+arg_10]; struct _IWmiFinalizer **
0x180067135  mov     r8, r15; struct IWbemObjectSink *
0x180067138  mov     rdx, [rbp+37h+arg_38]; struct IWbemContext *
0x18006713c  mov     rcx, r14; this
0x18006713f  call    ?CreateAsyncFinalizer@CWbemNamespace@@QEAAJPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAPEAU_IWmiFinalizer@@PEAPEAU3@@Z; CWbemNamespace::CreateAsyncFinalizer(IWbemContext *,IWbemObjectSink *,_IWmiFinalizer * *,IWbemObjectSink * *)
0x180067144  mov     ebx, eax
0x180067146  test    eax, eax
0x180067148  jns     short loc_180067197
0x18006714a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180067150  mov     edx, ebx
0x180067152  mov     rcx, rax
0x180067155  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006715b  mov     rcx, cs:WPP_GLOBAL_Control
0x180067162  lea     rax, WPP_GLOBAL_Control
0x180067169  cmp     rcx, rax
0x18006716c  jz      loc_180066ECC
0x180067172  test    byte ptr [rcx+1Ch], 1
0x180067176  jz      loc_180066ECC
0x18006717c  cmp     byte ptr [rcx+19h], 2
0x180067180  jb      loc_180066ECC
0x180067186  mov     edx, 121h
0x18006718b  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180067192  jmp     loc_180066EC0
0x180067197  mov     rdi, [rbp+37h+arg_10]
0x18006719b  jmp     short loc_18006720A
0x18006719d  mov     rax, [rdi]
0x1800671a0  lea     r8, [rbp+37h+var_60]
0x1800671a4  xor     edx, edx
0x1800671a6  mov     rcx, rdi
0x1800671a9  mov     rax, [rax+40h]
0x1800671ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800671b2  mov     ebx, eax
0x1800671b4  test    eax, eax
0x1800671b6  jns     short loc_1800671FB
0x1800671b8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800671be  mov     edx, ebx
0x1800671c0  mov     rcx, rax
0x1800671c3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800671c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800671d0  lea     rax, WPP_GLOBAL_Control
0x1800671d7  cmp     rcx, rax
0x1800671da  jz      loc_180066ECC
0x1800671e0  test    byte ptr [rcx+1Ch], 1
0x1800671e4  jz      loc_180066ECC
0x1800671ea  cmp     byte ptr [rcx+19h], 2
0x1800671ee  jb      loc_180066ECC
0x1800671f4  mov     edx, 122h
0x1800671f9  jmp     short loc_18006718B
0x1800671fb  mov     rax, [rdi]
0x1800671fe  mov     rcx, rdi
0x180067201  mov     rax, [rax+8]
0x180067205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006720a  mov     rax, [rbp+37h+var_60]
0x18006720e  mov     [rbp+37h+var_50], rax
0x180067212  mov     [rbp+37h+var_48], rdi
0x180067216  mov     rax, [rbp+37h+arg_38]
0x18006721a  mov     [rsp+0D0h+var_B0], rax; struct IWbemContext *
0x18006721f  mov     r9, rdi; struct _IWmiFinalizer *
0x180067222  mov     r8, rsi; unsigned __int16 *
0x180067225  lea     rdx, aIwbemservicesE_0; "IWbemServices::ExecNotificationQuery"
0x18006722c  mov     rcx, r14; this
0x18006722f  call    ?PublishInfo@CWbemNamespace@@QEAAJPEBG0PEAU_IWmiFinalizer@@PEAUIWbemContext@@@Z; CWbemNamespace::PublishInfo(ushort const *,ushort const *,_IWmiFinalizer *,IWbemContext *)
0x180067234  mov     ebx, eax
0x180067236  test    eax, eax
0x180067238  jns     short loc_180067293
0x18006723a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180067240  mov     edx, ebx
0x180067242  mov     rcx, rax
0x180067245  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006724b  mov     rcx, cs:WPP_GLOBAL_Control
0x180067252  lea     rax, WPP_GLOBAL_Control
0x180067259  cmp     rcx, rax
0x18006725c  jz      loc_180067693
0x180067262  test    byte ptr [rcx+1Ch], 1
0x180067266  jz      loc_180067693
0x18006726c  cmp     byte ptr [rcx+19h], 2
0x180067270  jb      loc_180067693
0x180067276  mov     edx, 123h
0x18006727b  mov     r9d, ebx
0x18006727e  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180067285  mov     rcx, [rcx+10h]
0x180067289  call    WPP_SF_d
0x18006728e  jmp     loc_180067693
0x180067293  mov     ecx, [r14+130h]
0x18006729a  xor     ebx, ebx
0x18006729c  cmp     ecx, 0FFFFFFFFh
0x18006729f  jz      short loc_1800672ED
0x1800672a1  cmp     cs:?g_cntWinmgmtTraceLogging@@3_JA, rbx; __int64 g_cntWinmgmtTraceLogging
0x1800672a8  jz      short loc_1800672ED
0x1800672aa  lea     rax, aSemiSync; "(Semi)Sync"
0x1800672b1  lea     r8, aAsync; "Async"
0x1800672b8  test    r15, r15
0x1800672bb  cmovz   r8, rax
0x1800672bf  mov     rax, [r14+58h]
0x1800672c3  mov     [rsp+0D0h+var_98], rax
0x1800672c8  mov     dword ptr [rsp+0D0h+var_A0], ecx
0x1800672cc  mov     eax, [r14+17Ch]
0x1800672d3  mov     dword ptr [rsp+0D0h+var_A8], eax
0x1800672d7  mov     dword ptr [rsp+0D0h+var_B0], r12d
0x1800672dc  mov     r9, rsi
0x1800672df  lea     edx, [rbx+0Ah]
0x1800672e2  mov     ecx, [rdi+2D4h]; unsigned int
0x1800672e8  call    ?WinmgmtTelemetrylogging@@YAXKZZ; WinmgmtTelemetrylogging(ulong,...)
0x1800672ed  call    ?GetEssSink@ConfigMgr@@SAPEAUIWbemEventSubsystem_m4@@XZ; ConfigMgr::GetEssSink(void)
0x1800672f2  mov     r12, rax
0x1800672f5  mov     [rbp+37h+var_80], rax
0x1800672f9  call    cs:__imp_?IsNtSetupRunning@@YAHXZ; IsNtSetupRunning(void)
0x1800672ff  test    eax, eax
0x180067301  jnz     loc_180067638
0x180067307  test    r12, r12
  ... truncated ...
```
