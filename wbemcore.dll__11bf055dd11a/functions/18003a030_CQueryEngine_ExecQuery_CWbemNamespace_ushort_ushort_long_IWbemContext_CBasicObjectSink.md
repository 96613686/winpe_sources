# CQueryEngine::ExecQuery(CWbemNamespace *,ushort *,ushort *,long,IWbemContext *,CBasicObjectSink *)

- ea: `0x18003a030`
- end: `0x18003ad2d`
- name: `?ExecQuery@CQueryEngine@@SAJPEAVCWbemNamespace@@PEAG1JPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z`
- size: `3325`
- prototype: `static int(struct CWbemNamespace *, unsigned __int16 *, unsigned __int16 *, int, struct IWbemContext *, struct CBasicObjectSink *)`
- caller_count: `4`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180039e80`
- `0x18005f7e0`
- `0x18007d710`
- `0x18009d04c`

## callees

- `0x18000af58`
- `0x18000b140`
- `0x180010e80`
- `0x18001307c`
- `0x180013710`
- `0x180015d24`
- `0x18003615c`
- `0x180039d40`
- `0x180039f68`
- `0x18003a030`
- `0x18003be20`
- `0x18003cd90`
- `0x18003cfe0`
- `0x18003d3b0`
- `0x18008531c`
- `0x180086420`
- `0x18009703c`
- `0x1800da010`

## import_xrefs

- `msvcrt!iswspace` at `0x18003a173`
- `msvcrt!iswspace` at `0x18003a83e`
- `msvcrt!iswspace` at `0x18003a173`
- `msvcrt!iswspace` at `0x18003a83e`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18003a32a`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18003a375`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18003a5d8`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18003a623`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18003a8b3`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18003a90a`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18003a32a`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18003a375`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18003a5d8`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18003a623`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18003a8b3`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18003a90a`
- `wbemcomn!??0WString@@QEAA@PEBG@Z` at `0x18003a4e6`
- `wbemcomn!??0WString@@QEAA@PEBG@Z` at `0x18003a4e6`
- `wbemcomn!?GetLocales@CMUILocaleList@@QEAAPEBGXZ` at `0x18003a3ee`
- `wbemcomn!?GetLocales@CMUILocaleList@@QEAAPEBGXZ` at `0x18003a3ee`
- `wbemcomn!??0WString@@QEAA@XZ` at `0x18003a4f4`
- `wbemcomn!??0WString@@QEAA@XZ` at `0x18003a502`
- `wbemcomn!??0WString@@QEAA@XZ` at `0x18003a4f4`
- `wbemcomn!??0WString@@QEAA@XZ` at `0x18003a502`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003a3cd`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003a698`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003a3cd`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003a698`
- `wbemcomn!??0CCritSec@@QEAA@XZ` at `0x18003a4b5`
- `wbemcomn!??0CCritSec@@QEAA@XZ` at `0x18003a4d5`
- `wbemcomn!??0CCritSec@@QEAA@XZ` at `0x18003a4b5`
- `wbemcomn!??0CCritSec@@QEAA@XZ` at `0x18003a4d5`
- `wbemcomn!GetMemLogObject` at `0x18003aab8`
- `wbemcomn!GetMemLogObject` at `0x18003ab25`
- `wbemcomn!GetMemLogObject` at `0x18003ac10`
- `wbemcomn!GetMemLogObject` at `0x18003ac7c`
- `wbemcomn!GetMemLogObject` at `0x18003aab8`
- `wbemcomn!GetMemLogObject` at `0x18003ab25`
- `wbemcomn!GetMemLogObject` at `0x18003ac10`
- `wbemcomn!GetMemLogObject` at `0x18003ac7c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003aac6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ab33`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ac1b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ac8a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003aac6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ab33`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ac1b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ac8a`

## string_xrefs

- `0x18003a25c`: `delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=18 #try_helpers=1
__int64 __fastcall CQueryEngine::ExecQuery(
        struct CWbemNamespace *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4,
        struct IWbemContext *a5,
        struct CBasicObjectSink *a6)
{
  unsigned __int16 *v6; // r12
  unsigned __int16 *v7; // rsi
  const unsigned __int16 **v8; // r13
  struct IWbemClassObject *v9; // r9
  const OLECHAR *v10; // rdi
  WCHAR v11; // bx
  WCHAR v12; // cx
  wint_t v13; // cx
  wint_t *v14; // rbx
  __int64 v15; // r15
  __int64 v16; // r14
  const wchar_t *v17; // rdi
  WCHAR *v18; // rsi
  __int64 v19; // rax
  WCHAR v20; // bx
  WCHAR v21; // cx
  const wchar_t *v22; // rdi
  WCHAR *v23; // rsi
  __int64 v24; // rax
  WCHAR v25; // bx
  WCHAR v26; // cx
  int v27; // r12d
  volatile signed __int32 *v28; // rsi
  volatile signed __int32 *v29; // rbx
  struct IWbemClassObject *v30; // r9
  const unsigned __int16 *Locales; // r13
  unsigned int v32; // ebx
  unsigned int v34; // ebx
  CObjectSink *v35; // r13
  CBasicObjectSink *v36; // rax
  struct IWbemClassObject *v37; // r9
  struct CBasicObjectSink *v38; // rdi
  __int64 v39; // rcx
  struct CWbemNamespace *v40; // r15
  int v41; // r8d
  struct IWbemContext *v42; // r9
  CAssocQuery *Inst; // rax
  CAssocQuery *v44; // r14
  unsigned int v45; // edi
  int DbPtr; // edi
  unsigned int v47; // ebx
  struct IWbemClassObject *v48; // r9
  unsigned int v49; // ebx
  CMemoryLog *MemLogObject; // rax
  unsigned int v51; // ebx
  CMemoryLog *v52; // rax
  struct IWbemClassObject *v53; // r9
  unsigned int v54; // ebx
  unsigned int v55; // ebx
  CMemoryLog *v56; // rax
  CMemoryLog *v57; // rax
  unsigned int v58; // ebx
  WCHAR SrcStr; // [rsp+30h] [rbp-108h] BYREF
  WCHAR DestStr; // [rsp+38h] [rbp-100h] BYREF
  WCHAR v61; // [rsp+40h] [rbp-F8h] BYREF
  WCHAR lpDestStr; // [rsp+48h] [rbp-F0h] BYREF
  WCHAR v63; // [rsp+50h] [rbp-E8h] BYREF
  WCHAR v64; // [rsp+58h] [rbp-E0h] BYREF
  WCHAR v65; // [rsp+60h] [rbp-D8h] BYREF
  WCHAR v66; // [rsp+68h] [rbp-D0h] BYREF
  WCHAR v67; // [rsp+70h] [rbp-C8h] BYREF
  WCHAR v68; // [rsp+78h] [rbp-C0h] BYREF
  WCHAR v69; // [rsp+80h] [rbp-B8h] BYREF
  WCHAR v70[4]; // [rsp+88h] [rbp-B0h] BYREF
  _BYTE v71[8]; // [rsp+90h] [rbp-A8h] BYREF
  CObjectSink *v72; // [rsp+98h] [rbp-A0h]
  unsigned __int16 *v73; // [rsp+A0h] [rbp-98h]
  CBasicObjectSink *v74; // [rsp+A8h] [rbp-90h] BYREF
  volatile signed __int32 *v75; // [rsp+B0h] [rbp-88h] BYREF
  unsigned __int16 *v76; // [rsp+B8h] [rbp-80h]
  __int64 v77; // [rsp+C0h] [rbp-78h]
  unsigned __int16 *v78; // [rsp+C8h] [rbp-70h]
  const wchar_t *v79; // [rsp+D0h] [rbp-68h]
  __int64 v80; // [rsp+D8h] [rbp-60h]
  unsigned __int16 *v81; // [rsp+E0h] [rbp-58h]
  const wchar_t *v82; // [rsp+E8h] [rbp-50h]
  unsigned __int16 *v83; // [rsp+F0h] [rbp-48h]
  const OLECHAR *v84; // [rsp+F8h] [rbp-40h]

  v6 = a3;
  v73 = a3;
  v7 = a2;
  v8 = (const unsigned __int16 **)a1;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qSS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      (unsigned int)WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids,
      (_DWORD)a1,
      (__int64)a2,
      (__int64)a3);
  }
  COperationError::COperationError((COperationError *)v71, a6, L"ExecQuery", v6, 1);
  if ( !v71[0] )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids, 2147749894LL);
    }
    v51 = CBasicObjectSink::Return(a6, -2147217402, 0);
    COperationError::~COperationError((COperationError *)v71);
    return v51;
  }
  if ( g_bDontAllowNewConnections )
  {
    v52 = GetMemLogObject();
    CMemoryLog::Write(v52, -2147217357);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids, 2147749939LL);
    }
    v47 = COperationError::ErrorOccurredWithMessage(
            (COperationError *)v71,
            -2147217357,
            L"Can't execute the query because WMI Server is shutting down.",
            v53);
    if ( v72 )
      CObjectSink::Release(v72);
    return v47;
  }
  v10 = L"WQL";
  v84 = L"WQL";
  v83 = v7;
  while ( 1 )
  {
    v11 = *v7;
    if ( !*v7 )
      break;
    if ( v11 > 0x7Fu )
    {
      v67 = *v7;
      v68 = 0;
      if ( LCMapStringW(0x7Fu, 0x100u, &v67, 1, &v68, 1) )
        v11 = v68;
      else
        v11 = v67;
    }
    else if ( (unsigned __int16)(v11 - 65) <= 0x19u )
    {
      v11 += 32;
    }
LABEL_9:
    v12 = *v10;
    if ( *v10 > 0x7Fu )
    {
      v69 = *v10;
      v70[0] = 0;
      if ( LCMapStringW(0x7Fu, 0x100u, &v69, 1, v70, 1) )
        v12 = v70[0];
      else
        v12 = v69;
    }
    else if ( (unsigned __int16)(v12 - 65) <= 0x19u )
    {
      v12 += 32;
    }
    if ( v11 != v12 )
    {
      v34 = COperationError::ErrorOccurredWithMessage(
              (COperationError *)v71,
              -2147217384,
              L"Invalid query type specified. WMI server only supports WQL queries.",
              v9);
      COperationError::~COperationError((COperationError *)v71);
      return v34;
    }
    v83 = ++v7;
    v84 = ++v10;
  }
  if ( *v10 )
    goto LABEL_9;
  while ( *v6 && iswspace(*v6) )
    v73 = ++v6;
  v13 = *v6;
  if ( !*v6 )
  {
    v54 = COperationError::ErrorOccurredWithMessage(
            (COperationError *)v71,
            -2147217385,
            L"Invalid query was specified.",
            v9);
    COperationError::~COperationError((COperationError *)v71);
    return v54;
  }
  if ( (a4 & 2) != 0 )
  {
    v55 = ExecPrototypeQuery((struct CWbemNamespace *)v8, v6, a5, a6);
    COperationError::~COperationError((COperationError *)v71);
    return v55;
  }
  v14 = v6;
  v76 = v6;
  while ( v13 && !iswspace(v13) )
  {
    v76 = ++v14;
    v13 = *v14;
  }
  if ( (((char *)v14 - (char *)v6) & 0xFFFFFFFFFFFFFFFEuLL) == 0xC )
  {
    v15 = 6;
    v16 = 6;
    v77 = 6;
    v17 = L"select";
    v79 = L"select";
    v18 = v6;
    v78 = v6;
    while ( 1 )
    {
      v19 = v16--;
      v77 = v16;
      if ( !v19 )
      {
LABEL_35:
        wcscpy(v70, L"\x01");
        goto LABEL_36;
      }
      v20 = *v18;
      if ( *v18 )
      {
        if ( v20 > 0x7Fu )
        {
          SrcStr = *v18;
          DestStr = 0;
          v20 = LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, &DestStr, 1) ? DestStr : SrcStr;
        }
        else if ( (unsigned __int16)(v20 - 65) <= 0x19u )
        {
          v20 += 32;
        }
      }
      else if ( !*v17 )
      {
        goto LABEL_35;
      }
      v21 = *v17;
      if ( *v17 > 0x7Fu )
      {
        v61 = *v17;
        lpDestStr = 0;
        v21 = LCMapStringW(0x7Fu, 0x100u, &v61, 1, &lpDestStr, 1) ? lpDestStr : v61;
      }
      else if ( (unsigned __int16)(v21 - 65) <= 0x19u )
      {
        v21 += 32;
      }
      if ( v20 != v21 )
        break;
      v78 = ++v18;
      v79 = ++v17;
    }
    *(_DWORD *)v70 = 0;
LABEL_36:
    v80 = 6;
    v22 = L"delete";
    v82 = L"delete";
    v23 = v6;
    v81 = v6;
    while ( 1 )
    {
      v24 = v15--;
      v80 = v15;
      if ( !v24 )
        break;
      v25 = *v23;
      if ( *v23 )
      {
        if ( v25 > 0x7Fu )
        {
          v63 = *v23;
          v64 = 0;
          if ( LCMapStringW(0x7Fu, 0x100u, &v63, 1, &v64, 1) )
            v25 = v64;
          else
            v25 = v63;
        }
        else if ( (unsigned __int16)(v25 - 65) <= 0x19u )
        {
          v25 += 32;
        }
      }
      else if ( !*v22 )
      {
        break;
      }
      v26 = *v22;
      if ( *v22 > 0x7Fu )
      {
        v65 = *v22;
        v66 = 0;
        if ( LCMapStringW(0x7Fu, 0x100u, &v65, 1, &v66, 1) )
          v26 = v66;
        else
          v26 = v65;
      }
      else if ( (unsigned __int16)(v26 - 65) <= 0x19u )
      {
        v26 += 32;
      }
      if ( v25 != v26 )
        goto LABEL_99;
      v81 = ++v23;
      v82 = ++v22;
    }
    v27 = 1;
  }
  else
  {
    *(_DWORD *)v70 = 0;
LABEL_99:
    v27 = 0;
  }
  v28 = (volatile signed __int32 *)v72;
  if ( (a4 & 0x20000) == 0 )
  {
    v29 = 0;
    v35 = v72;
    goto LABEL_68;
  }
  v29 = (volatile signed __int32 *)CWin32DefaultArena::WbemMemAlloc(0xF0u);
  v74 = (CBasicObjectSink *)v29;
  if ( v29 )
  {
    Locales = CMUILocaleList::GetLocales((CMUILocaleList *)(v8 + 22));
    CBasicObjectSink::CBasicObjectSink((CBasicObjectSink *)v29);
    *(_QWORD *)v29 = &CObjectSink::`vftable'{for `IWbemObjectSinkEx'};
    *((_QWORD *)v29 + 1) = &CInternalMerger::COwnSink::`vftable'{for `CDestination'};
    *((_DWORD *)v29 + 4) = 0;
    *(_QWORD *)v29 = &CForwardingSink::`vftable'{for `IWbemObjectSinkEx'};
    *((_QWORD *)v29 + 1) = &CInternalMerger::COwnSink::`vftable'{for `CDestination'};
    *((_QWORD *)v29 + 3) = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 88LL))(v28);
    *((_QWORD *)v29 + 4) = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 96LL))(v28);
    *((_QWORD *)v29 + 5) = v28;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v29 + 3) + 8LL))(*((_QWORD *)v29 + 3));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v29 + 4) + 8LL))(*((_QWORD *)v29 + 4));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v29 + 5) + 8LL))(*((_QWORD *)v29 + 5));
    *(_QWORD *)v29 = &CCombiningSink::`vftable'{for `IWbemObjectSinkEx'};
    *((_QWORD *)v29 + 1) = &CInternalMerger::COwnSink::`vftable'{for `CDestination'};
    *((_DWORD *)v29 + 12) = 0;
    *((_DWORD *)v29 + 13) = 0;
    *((_QWORD *)v29 + 7) = 0;
    *((_QWORD *)v29 + 8) = 0;
    CCritSec::CCritSec((CCritSec *)(v29 + 18));
    *(_QWORD *)v29 = &CLocaleMergingSink::`vftable'{for `IWbemObjectSinkEx'};
    *((_QWORD *)v29 + 1) = &CInternalMerger::COwnSink::`vftable'{for `CDestination'};
    CCritSec::CCritSec((CCritSec *)(v29 + 28));
    WString::WString((WString *)(v29 + 38), Locales);
    WString::WString((WString *)(v29 + 40));
    WString::WString((WString *)(v29 + 42));
    *((_QWORD *)v29 + 22) = 0;
    *((_BYTE *)v29 + 184) = 1;
    *((_QWORD *)v29 + 24) = 0;
    *((_QWORD *)v29 + 25) = 0;
    *((_QWORD *)v29 + 26) = 0;
    *((_QWORD *)v29 + 27) = 0;
    *((_QWORD *)v29 + 28) = 0;
    *((_QWORD *)v29 + 29) = 0;
    v8 = (const unsigned __int16 **)a1;
  }
  else
  {
    v29 = 0;
  }
  if ( !v29 )
  {
    v32 = COperationError::ErrorOccurredWithMessage(
            (COperationError *)v71,
            -2147217402,
            L"WMI Server is low in memory.",
            v30);
    if ( v28 )
    {
      *(_DWORD *)v70 = _InterlockedDecrement(v28 + 4);
      if ( !*(_DWORD *)v70 )
        (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v28 + 80LL))(v28, 1);
    }
    return v32;
  }
  DbPtr = CLocaleMergingSink::GetDbPtr((struct IWmiDbHandle **)v29, v8[12]);
  if ( DbPtr < 0 )
  {
    v56 = GetMemLogObject();
    CMemoryLog::Write(v56, DbPtr);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids,
        (unsigned int)DbPtr);
    }
    CLocaleMergingSink::`vector deleting destructor'((CLocaleMergingSink *)v29, 1u);
    v49 = COperationError::ErrorOccurredWithMessage((COperationError *)v71, DbPtr, L"Unknown Error.", v48);
    if ( v28 )
      CObjectSink::Release((CObjectSink *)v28);
    return v49;
  }
  else
  {
    _InterlockedIncrement(v29 + 4);
    v35 = (CObjectSink *)v29;
LABEL_68:
    v75 = v29;
    v36 = (CBasicObjectSink *)CWin32DefaultArena::WbemMemAlloc(0x38u);
    v38 = v36;
    v74 = v36;
    if ( v36 )
    {
      CBasicObjectSink::CBasicObjectSink(v36);
      *(_QWORD *)v39 = &CObjectSink::`vftable'{for `IWbemObjectSinkEx'};
      *(_QWORD *)(v39 + 8) = &CInternalMerger::COwnSink::`vftable'{for `CDestination'};
      *(_DWORD *)(v39 + 16) = 0;
      *(_QWORD *)v39 = &CForwardingSink::`vftable'{for `IWbemObjectSinkEx'};
      *(_QWORD *)(v39 + 8) = &CInternalMerger::COwnSink::`vftable'{for `CDestination'};
      *((_QWORD *)v38 + 3) = (*(__int64 (__fastcall **)(CObjectSink *))(*(_QWORD *)v35 + 88LL))(v35);
      *((_QWORD *)v38 + 4) = (*(__int64 (__fastcall **)(CObjectSink *))(*(_QWORD *)v35 + 96LL))(v35);
      *((_QWORD *)v38 + 5) = v35;
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v38 + 3) + 8LL))(*((_QWORD *)v38 + 3));
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v38 + 4) + 8LL))(*((_QWORD *)v38 + 4));
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v38 + 5) + 8LL))(*((_QWORD *)v38 + 5));
      *(_QWORD *)v38 = &CFinalizingSink::`vftable'{for `IWbemObjectSinkEx'};
      *((_QWORD *)v38 + 1) = &CInternalMerger::COwnSink::`vftable'{for `CDestination'};
      v40 = a1;
      *((_QWORD *)v38 + 6) = a1;
      _InterlockedIncrement((volatile signed __int32 *)a1 + 6);
    }
    else
    {
      v38 = 0;
      v40 = a1;
    }
    if ( v38 )
    {
      (*(void (__fastcall **)(struct CBasicObjectSink *))(*(_QWORD *)v38 + 8LL))(v38);
      v74 = v38;
      if ( *(_DWORD *)v70 )
      {
        CQueryEngine::ExecQlQuery(v40, v73, a4, a5, v38);
        goto LABEL_73;
      }
      if ( v27 )
      {
        CQueryEngine::ExecRepositoryQuery(v40, v73, v41, v42, v38);
LABEL_73:
        (*(void (__fastcall **)(struct CBasicObjectSink *))(*(_QWORD *)v38 + 16LL))(v38);
        v74 = 0;
        if ( v29 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 16LL))(v29);
        v75 = 0;
        if ( v28 )
        {
          *(_DWORD *)v70 = _InterlockedDecrement(v28 + 4);
          if ( !*(_DWORD *)v70 )
            (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v28 + 80LL))(v28, 1);
        }
        return 0;
      }
      else
      {
        Inst = CAssocQuery::CreateInst();
        v44 = Inst;
        if ( Inst )
        {
          *(_QWORD *)v70 = Inst;
          CAssocQuery::Execute(Inst, v40, v73, a5, (struct IWbemObjectSink *)v38);
          (*(void (__fastcall **)(CAssocQuery *))(*(_QWORD *)v44 + 16LL))(v44);
          *(_QWORD *)v70 = 0;
          goto LABEL_73;
        }
        v57 = GetMemLogObject();
        CMemoryLog::Write(v57, -2147217402);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            42,
            WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids,
            2147749894LL);
        }
        v58 = CBasicObjectSink::Return(v38, -2147217402, 0);
        CReleaseMe::release((CReleaseMe *)&v74);
        CReleaseMe::release((CReleaseMe *)&v75);
        COperationError::~COperationError((COperationError *)v71);
        return v58;
      }
    }
    else
    {
      v45 = COperationError::ErrorOccurredWithMessage(
              (COperationError *)v71,
              -2147217402,
              L"WMI Server is low in memory.",
              v37);
      if ( v29 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 16LL))(v29);
      v75 = 0;
      if ( v28 )
        CObjectSink::Release((CObjectSink *)v28);
      return v45;
    }
  }
}

```

## disassembly

```asm
0x18003a030  mov     [rsp+arg_18], r9d
0x18003a035  mov     [rsp+arg_0], rcx
0x18003a03a  push    rbx
0x18003a03b  push    rsi
0x18003a03c  push    rdi
0x18003a03d  push    r12
0x18003a03f  push    r13
0x18003a041  push    r14
0x18003a043  push    r15
0x18003a045  sub     rsp, 100h
0x18003a04c  mov     r12, r8
0x18003a04f  mov     [rsp+138h+var_98], r8
0x18003a057  mov     rsi, rdx
0x18003a05a  mov     r13, rcx
0x18003a05d  lea     rbx, WPP_GLOBAL_Control
0x18003a064  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a06b  cmp     rcx, rbx
0x18003a06e  jnz     loc_18003A80D
0x18003a074  mov     dword ptr [rsp+138h+lpDestStr], 1; int
0x18003a07c  mov     r9, r12; unsigned __int16 *
0x18003a07f  lea     r8, aExecquery; "ExecQuery"
0x18003a086  mov     r14, [rsp+138h+arg_28]
0x18003a08e  mov     rdx, r14; struct CBasicObjectSink *
0x18003a091  lea     rcx, [rsp+138h+var_A8]; this
0x18003a099  call    ??0COperationError@@QEAA@PEAVCBasicObjectSink@@PEBG1H@Z; COperationError::COperationError(CBasicObjectSink *,ushort const *,ushort const *,int)
0x18003a09e  nop
0x18003a09f  cmp     [rsp+138h+var_A8], 0
0x18003a0a7  jz      loc_18003AAB8
0x18003a0ad  cmp     cs:?g_bDontAllowNewConnections@@3HA, 0; int g_bDontAllowNewConnections
0x18003a0b4  jnz     loc_18003AB25
0x18003a0ba  lea     rdi, aWql; "WQL"
0x18003a0c1  mov     [rsp+138h+var_40], rdi
0x18003a0c9  mov     [rsp+138h+var_48], rsi
0x18003a0d1  movzx   ebx, word ptr [rsi]
0x18003a0d4  test    bx, bx
0x18003a0d7  jz      short loc_18003A131
0x18003a0d9  cmp     bx, 7Fh
0x18003a0dd  ja      loc_18003A880
0x18003a0e3  lea     eax, [rbx-41h]
0x18003a0e6  cmp     ax, 19h
0x18003a0ea  jbe     short loc_18003A125
0x18003a0ec  movzx   ecx, word ptr [rdi]
0x18003a0ef  cmp     cx, 7Fh
0x18003a0f3  ja      loc_18003A8CB
0x18003a0f9  lea     eax, [rcx-41h]
0x18003a0fc  cmp     ax, 19h
0x18003a100  jbe     short loc_18003A12B
0x18003a102  cmp     bx, cx
0x18003a105  jnz     loc_18003A63B
0x18003a10b  add     rsi, 2
0x18003a10f  mov     [rsp+138h+var_48], rsi
0x18003a117  add     rdi, 2
0x18003a11b  mov     [rsp+138h+var_40], rdi
0x18003a123  jmp     short loc_18003A0D1
0x18003a125  add     bx, 20h ; ' '
0x18003a129  jmp     short loc_18003A0EC
0x18003a12b  add     cx, 20h ; ' '
0x18003a12f  jmp     short loc_18003A102
0x18003a131  cmp     word ptr [rdi], 0
0x18003a135  jnz     short loc_18003A0EC
0x18003a137  movzx   ecx, word ptr [r12]; C
0x18003a13c  test    cx, cx
0x18003a13f  jnz     loc_18003A83E
0x18003a145  movzx   ecx, word ptr [r12]; C
0x18003a14a  xor     eax, eax
0x18003a14c  cmp     ax, cx
0x18003a14f  jz      loc_18003AB7D
0x18003a155  test    byte ptr [rsp+138h+arg_18], 2
0x18003a15d  jnz     loc_18003ABAC
0x18003a163  mov     rbx, r12
0x18003a166  mov     [rsp+138h+var_80], rbx
0x18003a16e  test    cx, cx
0x18003a171  jz      short loc_18003A18E
0x18003a173  call    cs:__imp_iswspace
0x18003a179  test    eax, eax
0x18003a17b  jnz     short loc_18003A18E
0x18003a17d  add     rbx, 2
0x18003a181  mov     [rsp+138h+var_80], rbx
0x18003a189  movzx   ecx, word ptr [rbx]
0x18003a18c  jmp     short loc_18003A16E
0x18003a18e  sub     rbx, r12
0x18003a191  and     rbx, 0FFFFFFFFFFFFFFFEh
0x18003a195  cmp     rbx, 0Ch
0x18003a199  jnz     loc_18003AA16
0x18003a19f  mov     r15d, 6
0x18003a1a5  mov     r14d, r15d
0x18003a1a8  mov     [rsp+138h+var_78], r15
0x18003a1b0  lea     rdi, aSelect; "select"
0x18003a1b7  mov     [rsp+138h+var_68], rdi
0x18003a1bf  mov     rsi, r12
0x18003a1c2  mov     [rsp+138h+var_70], r12
0x18003a1ca  nop     word ptr [rax+rax+00h]
0x18003a1d0  mov     rax, r14
0x18003a1d3  dec     r14
0x18003a1d6  mov     [rsp+138h+var_78], r14
0x18003a1de  test    rax, rax
0x18003a1e1  jz      short loc_18003A249
0x18003a1e3  movzx   ebx, word ptr [rsi]
0x18003a1e6  test    bx, bx
0x18003a1e9  jz      short loc_18003A243
0x18003a1eb  cmp     bx, 7Fh
0x18003a1ef  ja      loc_18003A2F7
0x18003a1f5  lea     eax, [rbx-41h]
0x18003a1f8  cmp     ax, 19h
0x18003a1fc  jbe     short loc_18003A237
0x18003a1fe  movzx   ecx, word ptr [rdi]
0x18003a201  cmp     cx, 7Fh
0x18003a205  ja      loc_18003A342
0x18003a20b  lea     eax, [rcx-41h]
0x18003a20e  cmp     ax, 19h
0x18003a212  jbe     short loc_18003A23D
0x18003a214  cmp     bx, cx
0x18003a217  jnz     loc_18003ABEC
0x18003a21d  add     rsi, 2
0x18003a221  mov     [rsp+138h+var_70], rsi
0x18003a229  add     rdi, 2
0x18003a22d  mov     [rsp+138h+var_68], rdi
0x18003a235  jmp     short loc_18003A1D0
0x18003a237  add     bx, 20h ; ' '
0x18003a23b  jmp     short loc_18003A1FE
0x18003a23d  add     cx, 20h ; ' '
0x18003a241  jmp     short loc_18003A214
0x18003a243  cmp     word ptr [rdi], 0
0x18003a247  jnz     short loc_18003A1FE
0x18003a249  mov     dword ptr [rsp+138h+var_B0], 1
0x18003a254  mov     [rsp+138h+var_60], r15
0x18003a25c  lea     rdi, aDelete; "delete"
0x18003a263  mov     [rsp+138h+var_50], rdi
0x18003a26b  mov     rsi, r12
0x18003a26e  mov     [rsp+138h+var_58], r12
0x18003a276  nop     word ptr [rax+rax+00000000h]
0x18003a280  mov     rax, r15
0x18003a283  dec     r15
0x18003a286  mov     [rsp+138h+var_60], r15
0x18003a28e  test    rax, rax
0x18003a291  jz      loc_18003A3A9
0x18003a297  movzx   ebx, word ptr [rsi]
0x18003a29a  test    bx, bx
0x18003a29d  jz      loc_18003A39F
0x18003a2a3  cmp     bx, 7Fh
0x18003a2a7  ja      loc_18003A5A5
0x18003a2ad  lea     eax, [rbx-41h]
0x18003a2b0  cmp     ax, 19h
0x18003a2b4  jbe     loc_18003A38D
0x18003a2ba  movzx   ecx, word ptr [rdi]
0x18003a2bd  cmp     cx, 7Fh
0x18003a2c1  ja      loc_18003A5F0
0x18003a2c7  lea     eax, [rcx-41h]
0x18003a2ca  cmp     ax, 19h
0x18003a2ce  jbe     loc_18003A396
0x18003a2d4  cmp     bx, cx
0x18003a2d7  jnz     loc_18003AA21
0x18003a2dd  add     rsi, 2
0x18003a2e1  mov     [rsp+138h+var_58], rsi
0x18003a2e9  add     rdi, 2
0x18003a2ed  mov     [rsp+138h+var_50], rdi
0x18003a2f5  jmp     short loc_18003A280
0x18003a2f7  mov     [rsp+138h+SrcStr], bx
0x18003a2fc  xor     eax, eax
0x18003a2fe  mov     [rsp+138h+DestStr], ax
0x18003a303  mov     [rsp+138h+cchDest], 1; cchDest
0x18003a30b  lea     rax, [rsp+138h+DestStr]
0x18003a310  mov     [rsp+138h+lpDestStr], rax; lpDestStr
0x18003a315  mov     r9d, 1; cchSrc
0x18003a31b  lea     r8, [rsp+138h+SrcStr]; lpSrcStr
0x18003a320  mov     edx, 100h; dwMapFlags
0x18003a325  mov     ecx, 7Fh; Locale
0x18003a32a  call    cs:__imp_LCMapStringW
0x18003a330  test    eax, eax
0x18003a332  jnz     loc_18003ABD8
0x18003a338  movzx   ebx, [rsp+138h+SrcStr]
0x18003a33d  jmp     loc_18003A1FE
0x18003a342  mov     [rsp+138h+var_F8], cx
0x18003a347  xor     eax, eax
0x18003a349  mov     [rsp+138h+var_F0], ax
0x18003a34e  mov     [rsp+138h+cchDest], 1; cchDest
0x18003a356  lea     rax, [rsp+138h+var_F0]
0x18003a35b  mov     [rsp+138h+lpDestStr], rax; lpDestStr
0x18003a360  mov     r9d, 1; cchSrc
0x18003a366  lea     r8, [rsp+138h+var_F8]; lpSrcStr
0x18003a36b  mov     edx, 100h; dwMapFlags
0x18003a370  mov     ecx, 7Fh; Locale
0x18003a375  call    cs:__imp_LCMapStringW
0x18003a37b  test    eax, eax
0x18003a37d  jnz     loc_18003ABE2
0x18003a383  movzx   ecx, [rsp+138h+var_F8]
0x18003a388  jmp     loc_18003A214
0x18003a38d  add     bx, 20h ; ' '
0x18003a391  jmp     loc_18003A2BA
0x18003a396  add     cx, 20h ; ' '
0x18003a39a  jmp     loc_18003A2D4
0x18003a39f  cmp     word ptr [rdi], 0
0x18003a3a3  jnz     loc_18003A2BA
0x18003a3a9  mov     r12d, 1
0x18003a3af  mov     rsi, [rsp+138h+var_A0]
0x18003a3b7  test    [rsp+138h+arg_18], 20000h
0x18003a3c2  jz      loc_18003A678
0x18003a3c8  mov     ecx, 0F0h
0x18003a3cd  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003a3d3  mov     rbx, rax
0x18003a3d6  mov     [rsp+138h+var_90], rax
0x18003a3de  test    rax, rax
0x18003a3e1  jz      loc_18003A593
0x18003a3e7  lea     rcx, [r13+0B0h]
0x18003a3ee  call    cs:__imp_?GetLocales@CMUILocaleList@@QEAAPEBGXZ; CMUILocaleList::GetLocales(void)
0x18003a3f4  mov     r13, rax
0x18003a3f7  mov     rcx, rbx; this
0x18003a3fa  call    ??0CBasicObjectSink@@QEAA@XZ; CBasicObjectSink::CBasicObjectSink(void)
0x18003a3ff  nop
0x18003a400  lea     r14, ??_7CObjectSink@@6BIWbemObjectSinkEx@@@; const CObjectSink::`vftable'{for `IWbemObjectSinkEx'}
0x18003a407  mov     [rbx], r14
0x18003a40a  lea     r15, ??_7COwnSink@CInternalMerger@@6BCDestination@@@; const CInternalMerger::COwnSink::`vftable'{for `CDestination'}
0x18003a411  mov     [rbx+8], r15
0x18003a415  mov     dword ptr [rbx+10h], 0
0x18003a41c  lea     rdi, ??_7CForwardingSink@@6BIWbemObjectSinkEx@@@; const CForwardingSink::`vftable'{for `IWbemObjectSinkEx'}
0x18003a423  mov     [rbx], rdi
0x18003a426  lea     rdi, ??_7COwnSink@CInternalMerger@@6BCDestination@@@; const CInternalMerger::COwnSink::`vftable'{for `CDestination'}
0x18003a42d  mov     [rbx+8], rdi
0x18003a431  mov     rax, [rsi]
0x18003a434  mov     rcx, rsi
0x18003a437  mov     rax, [rax+58h]
0x18003a43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a440  mov     [rbx+18h], rax
0x18003a444  mov     rax, [rsi]
0x18003a447  mov     rcx, rsi
0x18003a44a  mov     rax, [rax+60h]
0x18003a44e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a453  mov     [rbx+20h], rax
0x18003a457  mov     [rbx+28h], rsi
0x18003a45b  mov     rcx, [rbx+18h]
0x18003a45f  mov     rax, [rcx]
0x18003a462  mov     rax, [rax+8]
0x18003a466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a46b  mov     rcx, [rbx+20h]
0x18003a46f  mov     rax, [rcx]
0x18003a472  mov     rax, [rax+8]
0x18003a476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a47b  mov     rcx, [rbx+28h]
0x18003a47f  mov     rax, [rcx]
0x18003a482  mov     rax, [rax+8]
0x18003a486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a48b  nop
0x18003a48c  lea     rax, ??_7CCombiningSink@@6BIWbemObjectSinkEx@@@; const CCombiningSink::`vftable'{for `IWbemObjectSinkEx'}
0x18003a493  mov     [rbx], rax
0x18003a496  lea     rax, ??_7COwnSink@CInternalMerger@@6BCDestination@@@; const CInternalMerger::COwnSink::`vftable'{for `CDestination'}
0x18003a49d  mov     [rbx+8], rax
0x18003a4a1  xor     edi, edi
0x18003a4a3  mov     [rbx+30h], edi
0x18003a4a6  mov     [rbx+34h], edi
0x18003a4a9  mov     [rbx+38h], rdi
0x18003a4ad  mov     [rbx+40h], rdi
0x18003a4b1  lea     rcx, [rbx+48h]
0x18003a4b5  call    cs:__imp_??0CCritSec@@QEAA@XZ; CCritSec::CCritSec(void)
0x18003a4bb  nop
0x18003a4bc  lea     rax, ??_7CLocaleMergingSink@@6BIWbemObjectSinkEx@@@; const CLocaleMergingSink::`vftable'{for `IWbemObjectSinkEx'}
0x18003a4c3  mov     [rbx], rax
0x18003a4c6  lea     rax, ??_7COwnSink@CInternalMerger@@6BCDestination@@@; const CInternalMerger::COwnSink::`vftable'{for `CDestination'}
0x18003a4cd  mov     [rbx+8], rax
0x18003a4d1  lea     rcx, [rbx+70h]
0x18003a4d5  call    cs:__imp_??0CCritSec@@QEAA@XZ; CCritSec::CCritSec(void)
0x18003a4db  nop
0x18003a4dc  lea     rcx, [rbx+98h]
0x18003a4e3  mov     rdx, r13
0x18003a4e6  call    cs:__imp_??0WString@@QEAA@PEBG@Z; WString::WString(ushort const *)
0x18003a4ec  nop
0x18003a4ed  lea     rcx, [rbx+0A0h]
0x18003a4f4  call    cs:__imp_??0WString@@QEAA@XZ; WString::WString(void)
0x18003a4fa  nop
0x18003a4fb  lea     rcx, [rbx+0A8h]
0x18003a502  call    cs:__imp_??0WString@@QEAA@XZ; WString::WString(void)
0x18003a508  nop
0x18003a509  mov     [rbx+0B0h], rdi
0x18003a510  mov     byte ptr [rbx+0B8h], 1
0x18003a517  mov     [rbx+0C0h], rdi
0x18003a51e  mov     [rbx+0C8h], rdi
0x18003a525  mov     [rbx+0D0h], rdi
0x18003a52c  mov     [rbx+0D8h], rdi
0x18003a533  mov     [rbx+0E0h], rdi
0x18003a53a  mov     [rbx+0E8h], rdi
0x18003a541  mov     r13, [rsp+138h+arg_0]
0x18003a549  test    rbx, rbx
0x18003a54c  jnz     loc_18003AA29
0x18003a552  lea     r8, aWmiServerIsLow; "WMI Server is low in memory."
0x18003a559  mov     edx, 80041006h; int
0x18003a55e  lea     rcx, [rsp+138h+var_A8]; this
0x18003a566  call    ?ErrorOccurredWithMessage@COperationError@@QEAAJJPEAGPEAUIWbemClassObject@@@Z; COperationError::ErrorOccurredWithMessage(long,ushort *,IWbemClassObject *)
0x18003a56b  mov     ebx, eax
0x18003a56d  test    rsi, rsi
0x18003a570  jz      short loc_18003A58C
0x18003a572  mov     ecx, 0FFFFFFFFh
0x18003a577  lock xadd [rsi+10h], ecx
0x18003a57c  sub     ecx, 1
0x18003a57f  mov     dword ptr [rsp+138h+var_B0], ecx
0x18003a586  jz      loc_18003A81C
0x18003a58c  mov     eax, ebx
0x18003a58e  jmp     loc_18003A665
0x18003a593  xor     ebx, ebx
0x18003a595  lea     r14, ??_7CObjectSink@@6BIWbemObjectSinkEx@@@; const CObjectSink::`vftable'{for `IWbemObjectSinkEx'}
0x18003a59c  lea     r15, ??_7COwnSink@CInternalMerger@@6BCDestination@@@; const CInternalMerger::COwnSink::`vftable'{for `CDestination'}
0x18003a5a3  jmp     short loc_18003A549
  ... truncated ...
```
