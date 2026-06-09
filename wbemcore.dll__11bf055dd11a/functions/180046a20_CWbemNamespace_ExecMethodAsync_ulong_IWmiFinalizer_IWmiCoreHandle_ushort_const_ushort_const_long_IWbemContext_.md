# CWbemNamespace::_ExecMethodAsync(ulong,_IWmiFinalizer *,_IWmiCoreHandle *,ushort * const,ushort * const,long,IWbemContext *,IWbemClassObject *,IWbemObjectSink *)

- ea: `0x180046a20`
- end: `0x180047335`
- name: `?_ExecMethodAsync@CWbemNamespace@@MEAAJKPEAU_IWmiFinalizer@@PEAU_IWmiCoreHandle@@QEAG2JPEAUIWbemContext@@PEAUIWbemClassObject@@PEAUIWbemObjectSink@@@Z`
- size: `2325`
- prototype: `__int64 __fastcall(CWbemNamespace *this, unsigned int, struct _IWmiFinalizer *, struct _IWmiCoreHandle *, unsigned __int16 *const, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemClassObject *, struct IWbemObjectSink *)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800463a0`
- `0x18007d9c0`

## callees

- `0x18000a9a0`
- `0x18000b140`
- `0x18000f474`
- `0x18001cce0`
- `0x18001d390`
- `0x18003cfe0`
- `0x1800421ac`
- `0x180046a20`
- `0x180047ed0`
- `0x1800523c0`
- `0x18005fc7c`
- `0x180062ed0`
- `0x1800639b8`
- `0x180063a28`
- `0x1800903d0`
- `0x1800a0984`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180046e0f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800470dd`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180046e0f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800470dd`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180046ed7`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180046f86`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180046fe8`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180046ed7`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180046f86`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180046fe8`
- `wbemcomn!GetMemLogObject` at `0x180046a9a`
- `wbemcomn!GetMemLogObject` at `0x180046b5a`
- `wbemcomn!GetMemLogObject` at `0x180046b96`
- `wbemcomn!GetMemLogObject` at `0x180046c15`
- `wbemcomn!GetMemLogObject` at `0x180046c75`
- `wbemcomn!GetMemLogObject` at `0x180046d22`
- `wbemcomn!GetMemLogObject` at `0x180046da5`
- `wbemcomn!GetMemLogObject` at `0x180046e1d`
- `wbemcomn!GetMemLogObject` at `0x180046e91`
- `wbemcomn!GetMemLogObject` at `0x180046efb`
- `wbemcomn!GetMemLogObject` at `0x180046f41`
- `wbemcomn!GetMemLogObject` at `0x180046fb5`
- `wbemcomn!GetMemLogObject` at `0x180047085`
- `wbemcomn!GetMemLogObject` at `0x180047146`
- `wbemcomn!GetMemLogObject` at `0x1800471b1`
- `wbemcomn!GetMemLogObject` at `0x180047238`
- `wbemcomn!GetMemLogObject` at `0x18004729a`
- `wbemcomn!GetMemLogObject` at `0x180046a9a`
- `wbemcomn!GetMemLogObject` at `0x180046b5a`
- `wbemcomn!GetMemLogObject` at `0x180046b96`
- `wbemcomn!GetMemLogObject` at `0x180046c15`
- `wbemcomn!GetMemLogObject` at `0x180046c75`
- `wbemcomn!GetMemLogObject` at `0x180046d22`
- `wbemcomn!GetMemLogObject` at `0x180046da5`
- `wbemcomn!GetMemLogObject` at `0x180046e1d`
- `wbemcomn!GetMemLogObject` at `0x180046e91`
- `wbemcomn!GetMemLogObject` at `0x180046efb`
- `wbemcomn!GetMemLogObject` at `0x180046f41`
- `wbemcomn!GetMemLogObject` at `0x180046fb5`
- `wbemcomn!GetMemLogObject` at `0x180047085`
- `wbemcomn!GetMemLogObject` at `0x180047146`
- `wbemcomn!GetMemLogObject` at `0x1800471b1`
- `wbemcomn!GetMemLogObject` at `0x180047238`
- `wbemcomn!GetMemLogObject` at `0x18004729a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046aa5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046b68`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046ba4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046c20`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046c80`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046d2d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046db0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046e2d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046e9d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046f07`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046f4c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046fc0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047090`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047156`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800471bd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047243`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800472aa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046aa5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046b68`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046ba4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046c20`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046c80`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046d2d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046db0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046e2d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046e9d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046f07`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046f4c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046fc0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047090`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047156`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800471bd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047243`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800472aa`

## string_xrefs

- `0x180046fa0`: `IWbemServices::ExecMethod`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWbemNamespace::_ExecMethodAsync(
        CWbemNamespace *this,
        unsigned int a2,
        struct _IWmiFinalizer *a3,
        struct _IWmiCoreHandle *a4,
        unsigned __int16 *const a5,
        unsigned __int16 *const a6,
        int a7,
        struct IWbemContext *a8,
        struct IWbemClassObject *a9,
        struct IWbemObjectSink *a10)
{
  struct _IWmiFinalizer *v10; // r15
  struct IWbemObjectSink *v12; // rdx
  int v13; // ebx
  int v14; // r8d
  char v15; // r9
  struct IWbemContext *v16; // r10
  CMemoryLog *MemLogObject; // rax
  CClientCnt *v18; // rcx
  __int64 v19; // rdx
  CMemoryLog *v20; // rax
  CClientCnt *v21; // rcx
  __int64 v22; // rdx
  CMemoryLog *v23; // rax
  CMemoryLog *v25; // rax
  CMemoryLog *v26; // rax
  unsigned __int64 v27; // rbx
  CMemoryLog *v28; // rax
  CClientCnt *v29; // rcx
  __int64 v30; // rdx
  CMemoryLog *v31; // rax
  unsigned __int16 *v32; // rax
  unsigned __int16 *v33; // r14
  CMemoryLog *v34; // rax
  __int64 v35; // r9
  int v36; // r12d
  CMemoryLog *v37; // rax
  CClientCnt *v38; // rcx
  __int64 v39; // rdx
  CMemoryLog *v40; // rax
  CMemoryLog *v41; // rax
  CClientCnt *v42; // rcx
  __int64 v43; // rdx
  CMemoryLog *v44; // rax
  unsigned __int16 *v45; // r14
  unsigned __int16 *v46; // r12
  const wchar_t *v47; // r8
  CMemoryLog *v48; // rax
  unsigned __int16 *v49; // rax
  CAsyncReq_ExecMethodAsync *v50; // rbx
  struct IWbemContext *v51; // rax
  CMemoryLog *v52; // rax
  CClientCnt *v53; // rcx
  __int64 v54; // rdx
  int inited; // r14d
  CMemoryLog *v56; // rax
  CMemoryLog *v57; // rax
  __int64 v58; // r9
  CMemoryLog *v59; // rax
  struct IWbemObjectSink **v60; // [rsp+20h] [rbp-B9h]
  struct IWbemClassObject *v61; // [rsp+28h] [rbp-B1h]
  struct IWbemObjectSinkEx *v62; // [rsp+30h] [rbp-A9h]
  _WORD v63[2]; // [rsp+50h] [rbp-89h] BYREF
  int v64; // [rsp+54h] [rbp-85h]
  unsigned __int16 *v65; // [rsp+58h] [rbp-81h] BYREF
  struct _IWmiFinalizer *v66; // [rsp+60h] [rbp-79h] BYREF
  unsigned __int64 v67; // [rsp+68h] [rbp-71h] BYREF
  __int64 v68; // [rsp+70h] [rbp-69h] BYREF
  struct IWbemObjectSink *v69; // [rsp+78h] [rbp-61h] BYREF
  unsigned int v70; // [rsp+80h] [rbp-59h]
  unsigned __int16 *v71; // [rsp+88h] [rbp-51h]
  struct IWbemContext *v72; // [rsp+90h] [rbp-49h]
  struct IWbemObjectSinkEx *v73; // [rsp+98h] [rbp-41h] BYREF
  struct IWbemObjectSink *v74; // [rsp+A0h] [rbp-39h]
  unsigned __int16 *v75; // [rsp+A8h] [rbp-31h]
  unsigned __int16 *v76; // [rsp+B0h] [rbp-29h]
  struct _IWmiFinalizer *v77; // [rsp+B8h] [rbp-21h] BYREF
  struct IWbemClassObject *v78; // [rsp+C0h] [rbp-19h]
  unsigned __int16 v79[4]; // [rsp+C8h] [rbp-11h] BYREF

  v10 = a3;
  v70 = a2;
  v66 = a3;
  v65 = a5;
  v71 = a6;
  v64 = a7;
  v72 = a8;
  v78 = a9;
  v74 = a10;
  v13 = CWbemNamespace::CheckNs(this);
  if ( v13 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v13);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v13;
    }
    v19 = 697;
    goto LABEL_6;
  }
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSdql(*((_QWORD *)WPP_GLOBAL_Control + 2), 698, v14, (int)a5, (__int64)a6, v14, v15, *((_DWORD *)this + 76));
    v14 = v64;
    v12 = v74;
    v16 = v72;
  }
  if ( !v10 && !v12 )
  {
    v20 = GetMemLogObject();
    CMemoryLog::Write(v20, -2147217400);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v22 = 699;
LABEL_22:
    WPP_SF_d(*((_QWORD *)v21 + 2), v22, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
    return 2147749896LL;
  }
  if ( (v14 & 0xFFFFFF7F) != 0 )
  {
    v23 = GetMemLogObject();
    CMemoryLog::Write(v23, -2147217400);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v22 = 700;
    goto LABEL_22;
  }
  v69 = 0;
  if ( !v10 )
  {
    v13 = CWbemNamespace::CreateAsyncFinalizer(this, v16, v12, &v66, &v69);
    if ( v13 < 0 )
    {
      v25 = GetMemLogObject();
      CMemoryLog::Write(v25, v13);
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)v13;
      }
      v19 = 701;
      goto LABEL_6;
    }
    v10 = v66;
LABEL_37:
    v66 = (struct _IWmiFinalizer *)v69;
    v77 = v10;
    v63[0] = 0;
    *(_DWORD *)v79 = *(_DWORD *)L"::";
    v79[2] = asc_1800EB4C4[2];
    v27 = 3;
    v68 = 3;
    v67 = 0;
    if ( a5 )
    {
      v13 = StringCchLengthW(a5, 0x7FFFFFFFu, &v67);
      if ( v13 < 0 )
      {
        v28 = GetMemLogObject();
        CMemoryLog::Write(v28, v13);
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_126;
        }
        v30 = 703;
        goto LABEL_93;
      }
      v76 = a5;
      SafeInt<unsigned __int64>::operator+=<unsigned __int64>(&v68, v67);
      v27 = v68;
    }
    else
    {
      v76 = v63;
    }
    v67 = 0;
    if ( !a6 )
    {
      v75 = v63;
      goto LABEL_53;
    }
    v13 = StringCchLengthW(a6, 0x7FFFFFFFu, &v67);
    if ( v13 >= 0 )
    {
      v75 = a6;
      SafeInt<unsigned __int64>::operator+=<unsigned __int64>(&v68, v67);
      v27 = v68;
LABEL_53:
      v32 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v27, 2u));
      v33 = v32;
      if ( !v32 )
      {
        v34 = GetMemLogObject();
        v13 = -2147217402;
        CMemoryLog::Write(v34, -2147217402);
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_126;
        }
        v30 = 705;
        v35 = 2147749894LL;
        goto LABEL_58;
      }
      v67 = (unsigned __int64)v32;
      v36 = StringCchCopyW(v32, v27, v76);
      if ( v36 < 0 )
      {
        v37 = GetMemLogObject();
        CMemoryLog::Write(v37, v36);
        v38 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_65;
        }
        v39 = 706;
LABEL_64:
        WPP_SF_d(*((_QWORD *)v38 + 2), v39, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)v36);
LABEL_65:
        CWin32DefaultArena::WbemMemFree(v33);
        v13 = v36;
        goto LABEL_126;
      }
      v36 = StringCchCatW(v33, v27, v79);
      if ( v36 < 0 )
      {
        v40 = GetMemLogObject();
        CMemoryLog::Write(v40, v36);
        v38 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_65;
        }
        v39 = 707;
        goto LABEL_64;
      }
      v13 = StringCchCatW(v33, v27, v75);
      if ( v13 < 0 )
      {
        v41 = GetMemLogObject();
        CMemoryLog::Write(v41, v13);
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_77;
        }
        v43 = 708;
LABEL_76:
        WPP_SF_d(*((_QWORD *)v42 + 2), v43, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)v13);
LABEL_77:
        CWin32DefaultArena::WbemMemFree(v33);
        goto LABEL_126;
      }
      v13 = CWbemNamespace::PublishInfo(this, L"IWbemServices::ExecMethod", v33, v10, v72);
      if ( v13 < 0 )
      {
        v44 = GetMemLogObject();
        CMemoryLog::Write(v44, v13);
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_77;
        }
        v43 = 709;
        goto LABEL_76;
      }
      CWin32DefaultArena::WbemMemFree(v33);
      v45 = v71;
      v46 = v65;
      if ( *((_DWORD *)this + 76) != -1 && g_cntWinmgmtTraceLogging )
      {
        v47 = L"Async";
        if ( !v74 )
          v47 = L"(Semi)Sync";
        LODWORD(v62) = *((_DWORD *)this + 76);
        LODWORD(v61) = *((_DWORD *)this + 95);
        LODWORD(v60) = v64;
        WinmgmtTelemetrylogging(*((_DWORD *)v10 + 181), 3, v47, v65, v60, v61, v62, *((_QWORD *)this + 11), v71);
      }
      v73 = 0;
      v13 = ((__int64 (__fastcall *)(struct IWbemObjectSink *, GUID *, struct IWbemObjectSinkEx **))v69->lpVtbl->QueryInterface)(
              v69,
              &IID_IWbemObjectSinkEx,
              &v73);
      if ( v13 < 0 )
      {
        v48 = GetMemLogObject();
        CMemoryLog::Write(v48, v13);
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_126;
        }
        v30 = 710;
        goto LABEL_93;
      }
      v65 = (unsigned __int16 *)v73;
      *(_QWORD *)v79 = 0;
      v49 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x80u);
      v75 = v49;
      if ( v49 )
        v50 = CAsyncReq_ExecMethodAsync::CAsyncReq_ExecMethodAsync(
                (CAsyncReq_ExecMethodAsync *)v49,
                this,
                v46,
                v45,
                v64,
                v78,
                v73,
                v72);
      else
        v50 = 0;
      if ( v50 )
      {
        std::unique_ptr<CAsyncReq_ExecMethodAsync>::_Delete(v79);
        *(_QWORD *)v79 = v50;
        v51 = (struct IWbemContext *)*((_QWORD *)v50 + 5);
        if ( v51 )
        {
          inited = CWbemNamespace::InitNewTask(this, v50, v10, v70, v51, v74);
          if ( inited < 0 )
          {
            v56 = GetMemLogObject();
            CMemoryLog::Write(v56, inited);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                713,
                WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                (unsigned int)inited);
            }
            std::unique_ptr<CAsyncReq_ExecMethodAsync>::_Delete(v79);
            CReleaseMe::release((CReleaseMe *)&v65);
            v13 = inited;
            goto LABEL_126;
          }
          CReleaseMe::release((CReleaseMe *)&v66);
          v13 = ConfigMgr::EnqueueRequest(v50);
          if ( v13 >= 0 )
          {
            *(_QWORD *)v79 = 0;
            v53 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_125;
            }
            v54 = 715;
          }
          else
          {
            (*(void (__fastcall **)(struct _IWmiFinalizer *, _QWORD))(*(_QWORD *)v10 + 112LL))(v10, 0);
            v57 = GetMemLogObject();
            CMemoryLog::Write(v57, v13);
            v53 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_125;
            }
            v54 = 714;
          }
          v58 = (unsigned int)v13;
          goto LABEL_124;
        }
        v52 = GetMemLogObject();
        v13 = -2147217402;
        CMemoryLog::Write(v52, -2147217402);
        v53 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_125;
        }
        v54 = 712;
      }
      else
      {
        v59 = GetMemLogObject();
        v13 = -2147217402;
        CMemoryLog::Write(v59, -2147217402);
        v53 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_125;
        }
        v54 = 711;
      }
      v58 = 2147749894LL;
LABEL_124:
      WPP_SF_d(*((_QWORD *)v53 + 2), v54, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v58);
LABEL_125:
      std::unique_ptr<CAsyncReq_ExecMethodAsync>::_Delete(v79);
      CReleaseMe::release((CReleaseMe *)&v65);
      goto LABEL_126;
    }
    v31 = GetMemLogObject();
    CMemoryLog::Write(v31, v13);
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_126;
    }
    v30 = 704;
LABEL_93:
    v35 = (unsigned int)v13;
LABEL_58:
    WPP_SF_d(*((_QWORD *)v29 + 2), v30, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v35);
LABEL_126:
    CReleaseMe::release((CReleaseMe *)&v77);
    CReleaseMe::release((CReleaseMe *)&v66);
    return (unsigned int)v13;
  }
  v13 = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, struct IWbemObjectSink **))(*(_QWORD *)v10 + 64LL))(
          v10,
          0,
          &v69);
  if ( v13 >= 0 )
  {
    (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v10 + 8LL))(v10);
    goto LABEL_37;
  }
  v26 = GetMemLogObject();
  CMemoryLog::Write(v26, v13);
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return (unsigned int)v13;
  }
  v19 = 702;
LABEL_6:
  WPP_SF_d(*((_QWORD *)v18 + 2), v19, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)v13);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180046a20  mov     [rsp-8+arg_18], rbx
0x180046a25  push    rbp
0x180046a26  push    rsi
0x180046a27  push    rdi
0x180046a28  push    r12
0x180046a2a  push    r13
0x180046a2c  push    r14
0x180046a2e  push    r15
0x180046a30  lea     rbp, [rsp-7]
0x180046a35  sub     rsp, 0E0h
0x180046a3c  mov     rax, cs:__security_cookie
0x180046a43  xor     rax, rsp
0x180046a46  mov     [rbp+37h+var_40], rax
0x180046a4a  mov     r15, r8
0x180046a4d  mov     [rbp+37h+var_90], edx
0x180046a50  mov     r13, rcx
0x180046a53  mov     [rbp+37h+var_B0], r8
0x180046a57  mov     r14, [rbp+37h+arg_20]
0x180046a5b  mov     [rsp+110h+var_B8], r14
0x180046a60  mov     r12, [rbp+37h+arg_28]
0x180046a64  mov     [rbp+37h+var_88], r12
0x180046a68  mov     r8d, [rbp+37h+arg_30]
0x180046a6c  mov     [rsp+110h+var_BC], r8d
0x180046a71  mov     r10, [rbp+37h+arg_38]
0x180046a75  mov     [rbp+37h+var_80], r10
0x180046a79  mov     r9, [rbp+37h+arg_40]
0x180046a80  mov     [rbp+37h+var_50], r9
0x180046a84  mov     rdx, [rbp+37h+arg_48]
0x180046a8b  mov     [rbp+37h+var_70], rdx
0x180046a8f  call    ?CheckNs@CWbemNamespace@@QEAAJXZ; CWbemNamespace::CheckNs(void)
0x180046a94  mov     ebx, eax
0x180046a96  test    eax, eax
0x180046a98  jns     short loc_180046AF6
0x180046a9a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180046aa0  mov     edx, ebx
0x180046aa2  mov     rcx, rax
0x180046aa5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180046aab  lea     rsi, WPP_GLOBAL_Control
0x180046ab2  mov     rcx, cs:WPP_GLOBAL_Control
0x180046ab9  cmp     rcx, rsi
0x180046abc  jz      loc_18004730C
0x180046ac2  mov     dil, 1
0x180046ac5  test    [rcx+1Ch], dil
0x180046ac9  jz      loc_18004730C
0x180046acf  cmp     byte ptr [rcx+19h], 2
0x180046ad3  jb      loc_18004730C
0x180046ad9  mov     edx, 2B9h
0x180046ade  mov     r9d, ebx
0x180046ae1  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180046ae8  mov     rcx, [rcx+10h]
0x180046aec  call    WPP_SF_d
0x180046af1  jmp     loc_18004730C
0x180046af6  lea     rsi, WPP_GLOBAL_Control
0x180046afd  mov     dil, 1
0x180046b00  mov     rcx, cs:WPP_GLOBAL_Control
0x180046b07  cmp     rcx, rsi
0x180046b0a  jz      short loc_180046B50
0x180046b0c  test    [rcx+1Ch], dil
0x180046b10  jz      short loc_180046B50
0x180046b12  cmp     byte ptr [rcx+19h], 5
0x180046b16  jb      short loc_180046B50
0x180046b18  mov     edx, 2BAh
0x180046b1d  mov     eax, [r13+130h]
0x180046b24  mov     dword ptr [rsp+110h+var_D8], eax
0x180046b28  mov     [rsp+110h+var_E0], r9
0x180046b2d  mov     dword ptr [rsp+110h+var_E8], r8d
0x180046b32  mov     [rsp+110h+var_F0], r12
0x180046b37  mov     r9, r14
0x180046b3a  mov     rcx, [rcx+10h]
0x180046b3e  call    WPP_SF_SSdql
0x180046b43  mov     r8d, [rsp+110h+var_BC]
0x180046b48  mov     rdx, [rbp+37h+var_70]
0x180046b4c  mov     r10, [rbp+37h+var_80]
0x180046b50  test    r15, r15
0x180046b53  jnz     short loc_180046B8D
0x180046b55  test    rdx, rdx
0x180046b58  jnz     short loc_180046B8D
0x180046b5a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180046b60  mov     edx, 80041008h
0x180046b65  mov     rcx, rax
0x180046b68  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180046b6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180046b75  cmp     rcx, rsi
0x180046b78  jz      short loc_180046BDD
0x180046b7a  test    [rcx+1Ch], dil
0x180046b7e  jz      short loc_180046BDD
0x180046b80  cmp     byte ptr [rcx+19h], 2
0x180046b84  jb      short loc_180046BDD
0x180046b86  mov     edx, 2BBh
0x180046b8b  jmp     short loc_180046BC7
0x180046b8d  test    r8d, 0FFFFFF7Fh
0x180046b94  jz      short loc_180046BE7
0x180046b96  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180046b9c  mov     edx, 80041008h
0x180046ba1  mov     rcx, rax
0x180046ba4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180046baa  mov     rcx, cs:WPP_GLOBAL_Control
0x180046bb1  cmp     rcx, rsi
0x180046bb4  jz      short loc_180046BDD
0x180046bb6  test    [rcx+1Ch], dil
0x180046bba  jz      short loc_180046BDD
0x180046bbc  cmp     byte ptr [rcx+19h], 2
0x180046bc0  jb      short loc_180046BDD
0x180046bc2  mov     edx, 2BCh
0x180046bc7  mov     r9d, 80041008h
0x180046bcd  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180046bd4  mov     rcx, [rcx+10h]
0x180046bd8  call    WPP_SF_d
0x180046bdd  mov     eax, 80041008h
0x180046be2  jmp     loc_18004730E
0x180046be7  mov     [rbp+37h+var_98], 0
0x180046bef  test    r15, r15
0x180046bf2  jnz     short loc_180046C5A
0x180046bf4  lea     rax, [rbp+37h+var_98]
0x180046bf8  mov     [rsp+110h+var_F0], rax; struct IWbemObjectSink **
0x180046bfd  lea     r9, [rbp+37h+var_B0]; struct _IWmiFinalizer **
0x180046c01  mov     r8, rdx; struct IWbemObjectSink *
0x180046c04  mov     rdx, r10; struct IWbemContext *
0x180046c07  mov     rcx, r13; this
0x180046c0a  call    ?CreateAsyncFinalizer@CWbemNamespace@@QEAAJPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAPEAU_IWmiFinalizer@@PEAPEAU3@@Z; CWbemNamespace::CreateAsyncFinalizer(IWbemContext *,IWbemObjectSink *,_IWmiFinalizer * *,IWbemObjectSink * *)
0x180046c0f  mov     ebx, eax
0x180046c11  test    eax, eax
0x180046c13  jns     short loc_180046C54
0x180046c15  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180046c1b  mov     edx, ebx
0x180046c1d  mov     rcx, rax
0x180046c20  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180046c26  mov     rcx, cs:WPP_GLOBAL_Control
0x180046c2d  cmp     rcx, rsi
0x180046c30  jz      loc_18004730C
0x180046c36  test    [rcx+1Ch], dil
0x180046c3a  jz      loc_18004730C
0x180046c40  cmp     byte ptr [rcx+19h], 2
0x180046c44  jb      loc_18004730C
0x180046c4a  mov     edx, 2BDh
0x180046c4f  jmp     loc_180046ADE
0x180046c54  mov     r15, [rbp+37h+var_B0]
0x180046c58  jmp     short loc_180046CC3
0x180046c5a  mov     rax, [r15]
0x180046c5d  lea     r8, [rbp+37h+var_98]
0x180046c61  xor     edx, edx
0x180046c63  mov     rcx, r15
0x180046c66  mov     rax, [rax+40h]
0x180046c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c6f  mov     ebx, eax
0x180046c71  test    eax, eax
0x180046c73  jns     short loc_180046CB4
0x180046c75  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180046c7b  mov     edx, ebx
0x180046c7d  mov     rcx, rax
0x180046c80  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180046c86  mov     rcx, cs:WPP_GLOBAL_Control
0x180046c8d  cmp     rcx, rsi
0x180046c90  jz      loc_18004730C
0x180046c96  test    [rcx+1Ch], dil
0x180046c9a  jz      loc_18004730C
0x180046ca0  cmp     byte ptr [rcx+19h], 2
0x180046ca4  jb      loc_18004730C
0x180046caa  mov     edx, 2BEh
0x180046caf  jmp     loc_180046ADE
0x180046cb4  mov     rax, [r15]
0x180046cb7  mov     rcx, r15
0x180046cba  mov     rax, [rax+8]
0x180046cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046cc3  mov     rax, [rbp+37h+var_98]
0x180046cc7  mov     [rbp+37h+var_B0], rax
0x180046ccb  mov     [rbp+37h+var_58], r15
0x180046ccf  xor     eax, eax
0x180046cd1  mov     [rsp+110h+var_C0], ax
0x180046cd6  mov     eax, dword ptr cs:asc_1800EB4C4; "::"
0x180046cdc  mov     dword ptr [rbp+37h+var_48], eax
0x180046cdf  movzx   eax, word ptr cs:asc_1800EB4C4+4; ""
0x180046ce6  mov     [rbp+37h+var_48+4], ax
0x180046cea  mov     ebx, 3
0x180046cef  mov     [rbp+37h+var_A0], rbx
0x180046cf3  mov     [rbp+37h+var_A8], 0
0x180046cfb  test    r14, r14
0x180046cfe  jnz     short loc_180046D0B
0x180046d00  lea     r14, [rsp+110h+var_C0]
0x180046d05  mov     [rbp+37h+var_60], r14
0x180046d09  jmp     short loc_180046D76
0x180046d0b  lea     r8, [rbp+37h+var_A8]; unsigned __int64 *
0x180046d0f  mov     edx, 7FFFFFFFh; unsigned __int64
0x180046d14  mov     rcx, r14; unsigned __int16 *
0x180046d17  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180046d1c  mov     ebx, eax
0x180046d1e  test    eax, eax
0x180046d20  jns     short loc_180046D61
0x180046d22  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180046d28  mov     edx, ebx
0x180046d2a  mov     rcx, rax
0x180046d2d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180046d33  mov     rcx, cs:WPP_GLOBAL_Control
0x180046d3a  cmp     rcx, rsi
0x180046d3d  jz      loc_1800472F9
0x180046d43  test    [rcx+1Ch], dil
0x180046d47  jz      loc_1800472F9
0x180046d4d  cmp     byte ptr [rcx+19h], 2
0x180046d51  jb      loc_1800472F9
0x180046d57  mov     edx, 2BFh
0x180046d5c  jmp     loc_1800470BF
0x180046d61  mov     [rbp+37h+var_60], r14
0x180046d65  mov     rdx, [rbp+37h+var_A8]
0x180046d69  lea     rcx, [rbp+37h+var_A0]
0x180046d6d  call    ??$?Y_K@?$SafeInt@_K@@QEAAAEAV0@_K@Z; SafeInt<unsigned __int64>::operator+=<unsigned __int64>(unsigned __int64)
0x180046d72  mov     rbx, [rbp+37h+var_A0]
0x180046d76  mov     [rbp+37h+var_A8], 0
0x180046d7e  test    r12, r12
0x180046d81  jnz     short loc_180046D8E
0x180046d83  lea     r12, [rsp+110h+var_C0]
0x180046d88  mov     [rbp+37h+var_68], r12
0x180046d8c  jmp     short loc_180046DF9
0x180046d8e  lea     r8, [rbp+37h+var_A8]; unsigned __int64 *
0x180046d92  mov     edx, 7FFFFFFFh; unsigned __int64
0x180046d97  mov     rcx, r12; unsigned __int16 *
0x180046d9a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180046d9f  mov     ebx, eax
0x180046da1  test    eax, eax
0x180046da3  jns     short loc_180046DE4
0x180046da5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180046dab  mov     edx, ebx
0x180046dad  mov     rcx, rax
0x180046db0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180046db6  mov     rcx, cs:WPP_GLOBAL_Control
0x180046dbd  cmp     rcx, rsi
0x180046dc0  jz      loc_1800472F9
0x180046dc6  test    [rcx+1Ch], dil
0x180046dca  jz      loc_1800472F9
0x180046dd0  cmp     byte ptr [rcx+19h], 2
0x180046dd4  jb      loc_1800472F9
0x180046dda  mov     edx, 2C0h
0x180046ddf  jmp     loc_1800470BF
0x180046de4  mov     [rbp+37h+var_68], r12
0x180046de8  mov     rdx, [rbp+37h+var_A8]
0x180046dec  lea     rcx, [rbp+37h+var_A0]
0x180046df0  call    ??$?Y_K@?$SafeInt@_K@@QEAAAEAV0@_K@Z; SafeInt<unsigned __int64>::operator+=<unsigned __int64>(unsigned __int64)
0x180046df5  mov     rbx, [rbp+37h+var_A0]
0x180046df9  mov     eax, 2
0x180046dfe  mul     rbx
0x180046e01  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180046e08  cmovb   rax, rcx
0x180046e0c  mov     rcx, rax
0x180046e0f  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180046e15  mov     r14, rax
0x180046e18  test    rax, rax
0x180046e1b  jnz     short loc_180046E77
0x180046e1d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180046e23  mov     ebx, 80041006h
0x180046e28  mov     edx, ebx
0x180046e2a  mov     rcx, rax
0x180046e2d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180046e33  mov     rcx, cs:WPP_GLOBAL_Control
0x180046e3a  cmp     rcx, rsi
0x180046e3d  jz      loc_1800472F9
0x180046e43  test    [rcx+1Ch], dil
0x180046e47  jz      loc_1800472F9
0x180046e4d  cmp     byte ptr [rcx+19h], 2
0x180046e51  jb      loc_1800472F9
0x180046e57  mov     edx, 2C1h
0x180046e5c  mov     r9d, 80041006h
0x180046e62  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180046e69  mov     rcx, [rcx+10h]
0x180046e6d  call    WPP_SF_d
0x180046e72  jmp     loc_1800472F9
0x180046e77  mov     [rbp+37h+var_A8], r14
0x180046e7b  mov     r8, [rbp+37h+var_60]; unsigned __int16 *
0x180046e7f  mov     rdx, rbx; unsigned __int64
0x180046e82  mov     rcx, r14; unsigned __int16 *
0x180046e85  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180046e8a  mov     r12d, eax
0x180046e8d  test    eax, eax
0x180046e8f  jns     short loc_180046EE5
0x180046e91  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180046e97  mov     edx, r12d
0x180046e9a  mov     rcx, rax
0x180046e9d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180046ea3  mov     rcx, cs:WPP_GLOBAL_Control
0x180046eaa  cmp     rcx, rsi
0x180046ead  jz      short loc_180046ED4
0x180046eaf  test    [rcx+1Ch], dil
0x180046eb3  jz      short loc_180046ED4
0x180046eb5  cmp     byte ptr [rcx+19h], 2
0x180046eb9  jb      short loc_180046ED4
0x180046ebb  mov     edx, 2C2h
0x180046ec0  mov     r9d, r12d
0x180046ec3  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180046eca  mov     rcx, [rcx+10h]
0x180046ece  call    WPP_SF_d
0x180046ed3  nop
0x180046ed4  mov     rcx, r14
0x180046ed7  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180046edd  mov     ebx, r12d
0x180046ee0  jmp     loc_1800472F9
0x180046ee5  lea     r8, [rbp+37h+var_48]; unsigned __int16 *
0x180046ee9  mov     rdx, rbx; unsigned __int64
0x180046eec  mov     rcx, r14; unsigned __int16 *
0x180046eef  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180046ef4  mov     r12d, eax
0x180046ef7  test    eax, eax
0x180046ef9  jns     short loc_180046F2C
  ... truncated ...
```
