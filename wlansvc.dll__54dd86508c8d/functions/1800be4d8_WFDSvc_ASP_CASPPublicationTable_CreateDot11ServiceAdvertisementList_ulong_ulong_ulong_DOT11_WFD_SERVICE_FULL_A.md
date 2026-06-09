# WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList(ulong,ulong,ulong *,_DOT11_WFD_SERVICE_FULL_ADVERTISEMENT_LIST * *)

- ea: `0x1800be4d8`
- end: `0x1800bee66`
- name: `?CreateDot11ServiceAdvertisementList@CASPPublicationTable@ASP@WFDSvc@@QEAAXKKPEAKPEAPEAU_DOT11_WFD_SERVICE_FULL_ADVERTISEMENT_LIST@@@Z`
- size: `2446`
- prototype: `void __fastcall(WFDSvc::ASP::CASPPublicationTable *this, unsigned int, unsigned int, unsigned int *, struct _DOT11_WFD_SERVICE_FULL_ADVERTISEMENT_LIST **)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800fdb98`
- `0x1801da4d8`

## callees

- `0x18000bea0`
- `0x1800596b4`
- `0x18006d5b4`
- `0x180073c18`
- `0x18007d770`
- `0x18009598c`
- `0x1800bd620`
- `0x1800be4d8`
- `0x1800bee6c`
- `0x1800dfb4c`
- `0x180107318`
- `0x180107330`
- `0x180108cfc`
- `0x1801df598`
- `0x1801df648`
- `0x1801e32e0`
- `0x1801e3334`
- `0x1801e3388`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800becf5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800becf5`

## string_xrefs

- `0x1800be525`: `WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList`
- `0x1800be748`: `WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList`
- `0x1800be778`: `WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList`
- `0x1800be7dd`: `WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList`
- `0x1800be80d`: `WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList`
- `0x1800be83d`: `WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList`
- `0x1800be86d`: `WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList`
- `0x1800be8b8`: `WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList`
- `0x1800be8f6`: `WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList`
- `0x1800be980`: `WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList`
- `0x1800bec7c`: `WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList`
- `0x1800bed34`: `WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList`
- `0x1800bed64`: `WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList`
- `0x1800bed94`: `WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList`
- `0x1800bedc4`: `WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList`
- `0x1800bedf4`: `WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList`
- `0x1800bee24`: `WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList`
- `0x1800bee54`: `WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList`
- `0x1800bed1b`: `Allocation of spAdvertisedServiceList failed`
- `0x1800be967`: `Service name list size exceeded.`
- `0x1800be7c4`: `Failed to read invalid prefix from publication table to advertised service list`
- `0x1800bec63`: `Deferred Session Info for service is too long`

## pseudocode

```c
void __fastcall WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList(
        WFDSvc::ASP::CASPPublicationTable *this,
        unsigned int a2,
        unsigned int a3,
        unsigned int *a4,
        struct _DOT11_WFD_SERVICE_FULL_ADVERTISEMENT_LIST **a5)
{
  unsigned int v6; // r13d
  unsigned int v7; // esi
  unsigned int v8; // r15d
  _QWORD *v9; // rbx
  __int64 v10; // rbx
  unsigned int Utf8ServiceName; // r14d
  unsigned __int8 *v12; // rdx
  __int64 v13; // rax
  PVOID *v14; // rcx
  unsigned int v15; // r8d
  __int64 v16; // r12
  int v17; // edx
  int v18; // r8d
  unsigned int v19; // ecx
  unsigned int v20; // eax
  __int64 v21; // rbx
  int v22; // ecx
  int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // eax
  unsigned int v26; // ebx
  unsigned int v27; // r14d
  unsigned int v28; // eax
  unsigned int v29; // ecx
  unsigned int v30; // r12d
  _DWORD *v31; // r15
  const struct std::nothrow_t *v32; // rdx
  _DWORD *v33; // rsi
  unsigned __int8 *v34; // rbx
  __int64 v35; // rcx
  unsigned __int8 *v36; // rbx
  __int64 v37; // rbx
  size_t v38; // rdi
  size_t ServiceInformation; // r13
  unsigned int DeferredSessionResponse; // eax
  int v41; // ecx
  __int64 v42; // rbx
  _QWORD *v43; // rbx
  _QWORD *v44; // rcx
  unsigned int v45; // [rsp+38h] [rbp-91h]
  int v46; // [rsp+38h] [rbp-91h]
  unsigned int v47; // [rsp+3Ch] [rbp-8Dh] BYREF
  unsigned int v48; // [rsp+40h] [rbp-89h]
  unsigned int v49; // [rsp+44h] [rbp-85h]
  unsigned __int8 *v50; // [rsp+48h] [rbp-81h] BYREF
  unsigned __int8 *v51; // [rsp+50h] [rbp-79h] BYREF
  unsigned int v52; // [rsp+58h] [rbp-71h] BYREF
  void *Src; // [rsp+60h] [rbp-69h] BYREF
  __int64 v54; // [rsp+68h] [rbp-61h] BYREF
  void **v55; // [rsp+70h] [rbp-59h] BYREF
  unsigned __int8 *v56; // [rsp+78h] [rbp-51h]
  void **v57; // [rsp+80h] [rbp-49h]
  __int64 v58; // [rsp+88h] [rbp-41h]
  void **v59; // [rsp+90h] [rbp-39h] BYREF
  _QWORD *v60; // [rsp+98h] [rbp-31h]
  void **v61; // [rsp+A0h] [rbp-29h]
  void **v62; // [rsp+A8h] [rbp-21h] BYREF
  void *v63[2]; // [rsp+B0h] [rbp-19h]
  __int64 v64; // [rsp+C0h] [rbp-9h]
  PSRWLOCK SRWLock; // [rsp+D0h] [rbp+7h] BYREF
  char v66; // [rsp+D8h] [rbp+Fh]

  if ( !a5 )
    WFDSvc::CWFDSvcException::Throw(
      -2147024809,
      "WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspmgr\\src\\asppublicationtable.cpp",
      0xFEu,
      L"Invalid arguments");
  LockSentry<ReadersWriterLock,1>::LockSentry<ReadersWriterLock,1>(&SRWLock, (char *)this + 8);
  v47 = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v45 = 0;
  v48 = *((_DWORD *)this + 13);
  v62 = &WFDSvc::List<WFDSvc::ASP::StringPointerAndLength>::`vftable';
  *(_OWORD *)v63 = 0;
  v64 = 0;
  v52 = 0;
  v9 = (_QWORD *)*((_QWORD *)this + 3);
  v60 = v9;
  v61 = &WFDSvc::ForwardIteratorTraits<WFDSvc::ListNode<SmartPointer<WFDSvc::ASP::IASPConnection>>>::`vftable';
  v59 = &WFDSvc::BaseListIterator<WFDSvc::ListNode<SmartPointer<WFDSvc::ASP::CASPPublication>>,WFDSvc::ForwardIteratorTraits<WFDSvc::ListNode<SmartPointer<WFDSvc::ASP::CASPPublication>>>>::`vftable';
LABEL_4:
  if ( v9 )
  {
    v10 = *v9;
    Src = (void *)v10;
    SmartPointer<WFDSvc::ASPCoordination::ASPUnknownMessage>::AddRef(&Src);
    v51 = 0;
    Utf8ServiceName = WFDSvc::ASP::CASPPublication::GetUtf8ServiceName((WFDSvc::ASP::CASPPublication *)v10, &v51);
    LODWORD(v54) = WFDSvc::ASP::CASPPublication::GetServiceInformation((WFDSvc::ASP::CASPPublication *)v10, &v50);
    v49 = 0;
    v12 = *(unsigned __int8 **)(v10 + 816);
    v50 = v12;
    v13 = 0;
    v14 = (PVOID *)WPP_GLOBAL_Control;
    while ( 1 )
    {
      v46 = v13;
      if ( (unsigned int)v13 >= *(_DWORD *)(v10 + 804) )
      {
        if ( Utf8ServiceName + v6 < v6 )
          WFDSvc::CWFDSvcException::Throw(
            -2147024362,
            "WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList",
            "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspmgr\\src\\asppublicationtable.cpp",
            75,
            L"Function returned bad HRESULT",
            this);
        if ( v7 + (unsigned int)v54 < v7 )
          WFDSvc::CWFDSvcException::Throw(
            -2147024362,
            "WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList",
            "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspmgr\\src\\asppublicationtable.cpp",
            77,
            L"Function returned bad HRESULT",
            this);
        v20 = v8 + v49;
        if ( v8 + v49 < v8 )
          WFDSvc::CWFDSvcException::Throw(
            -2147024362,
            "WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList",
            "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspmgr\\src\\asppublicationtable.cpp",
            79,
            L"Function returned bad HRESULT",
            this);
        v6 += Utf8ServiceName;
        v7 += v54;
        v8 += v49;
        v45 = v20;
        SmartPointer<WFDSvc::ASPCoordination::ASPCommandMessage>::~SmartPointer<WFDSvc::ASPCoordination::ASPCommandMessage>(&Src);
        WFDSvc::ListIterator<WFDSvc::ListNode<WFDSvc::ASPCoordination::CSocketWrapper::ReceiveListenerWrapper>,WFDSvc::ForwardIteratorTraits<WFDSvc::ListNode<WFDSvc::ASPCoordination::CSocketWrapper::ReceiveListenerWrapper>>>::operator++(&v59);
        v9 = v60;
        goto LABEL_4;
      }
      v15 = *v12;
      if ( Utf8ServiceName <= v15 )
      {
        if ( v14 != &WPP_GLOBAL_Control && *((_BYTE *)v14 + 105) && (*((_BYTE *)v14 + 108) & 1) != 0 )
          WPP_SF_qDD(v14[12], 13, &WPP_42d5f68346563a82d53568ed43f42df4_Traceguids, this, v15, Utf8ServiceName);
        WFDSvc::CWFDSvcException::Throw(
          -2147024883,
          "WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList",
          "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspmgr\\src\\asppublicationtable.cpp",
          0x130u,
          L"Failed to read invalid prefix from publication table to advertised service list");
      }
      v16 = 7 * v13;
      v55 = &ConflictResolver::`vftable';
      LOBYTE(v56) = v12[7 * v13];
      v57 = (void **)v51;
      v58 = (__int64)&v12[7 * v13 + 1];
      if ( (unsigned __int8)WFDSvc::Set<WFDSvc::ASP::StringPointerAndLength,WFDSvc::ASP::SingleCompare>::TryInsert(&v62) )
        break;
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_qsD(*((_QWORD *)WPP_GLOBAL_Control + 12), v17, v18, (_DWORD)this, (__int64)v51, v50[v16]);
LABEL_16:
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
      v13 = (unsigned int)(v46 + 1);
      v12 = v50;
    }
    if ( v48 + 1 < v48 )
      WFDSvc::CWFDSvcException::Throw(
        -2147024362,
        "WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList",
        "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspmgr\\src\\asppublicationtable.cpp",
        59,
        L"Function returned bad HRESULT",
        this);
    v19 = v49 + v50[v16];
    if ( v19 < v49 )
      WFDSvc::CWFDSvcException::Throw(
        -2147024362,
        "WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList",
        "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspmgr\\src\\asppublicationtable.cpp",
        62,
        L"Function returned bad HRESULT",
        this);
    ++v48;
    v49 = v19;
    goto LABEL_16;
  }
  v21 = v48;
  v22 = ULongLongToULong(180LL * v48, &v47);
  if ( v22 < 0 )
    WFDSvc::CWFDSvcException::Throw(
      v22,
      "WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspmgr\\src\\asppublicationtable.cpp",
      83,
      L"Function returned bad HRESULT",
      this);
  v23 = ULongLongToULong(15 * v21, &v52);
  if ( v23 < 0 )
    WFDSvc::CWFDSvcException::Throw(
      v23,
      "WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspmgr\\src\\asppublicationtable.cpp",
      87,
      L"Function returned bad HRESULT",
      this);
  v24 = v52 + v6;
  if ( v52 + v6 < v52 )
    WFDSvc::CWFDSvcException::Throw(
      -2147024362,
      "WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspmgr\\src\\asppublicationtable.cpp",
      91,
      L"Function returned bad HRESULT",
      this);
  v25 = v24 + v8;
  if ( v24 + v8 < v24 )
    WFDSvc::CWFDSvcException::Throw(
      -2147024362,
      "WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspmgr\\src\\asppublicationtable.cpp",
      94,
      L"Function returned bad HRESULT",
      this);
  if ( v25 > a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_qDD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        15,
        &WPP_42d5f68346563a82d53568ed43f42df4_Traceguids,
        this,
        v25,
        a2);
    }
    WFDSvc::CWFDSvcException::Throw(
      -2147023613,
      "WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspmgr\\src\\asppublicationtable.cpp",
      0x167u,
      L"Service name list size exceeded.");
  }
  if ( v7 > a3
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 12), 16, &WPP_42d5f68346563a82d53568ed43f42df4_Traceguids, this, v7, a3);
  }
  v26 = v47;
  v27 = v47 + 40;
  if ( v47 >= 0xFFFFFFD8 )
    WFDSvc::CWFDSvcException::Throw(
      -2147024362,
      "WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspmgr\\src\\asppublicationtable.cpp",
      117,
      L"Function returned bad HRESULT",
      this);
  v28 = v27 + v6;
  if ( v27 + v6 < v27 )
    WFDSvc::CWFDSvcException::Throw(
      -2147024362,
      "WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspmgr\\src\\asppublicationtable.cpp",
      119,
      L"Function returned bad HRESULT",
      this);
  v29 = v28 + v7;
  if ( v28 + v7 < v28 )
    WFDSvc::CWFDSvcException::Throw(
      -2147024362,
      "WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspmgr\\src\\asppublicationtable.cpp",
      121,
      L"Function returned bad HRESULT",
      this);
  v30 = v29 + v8;
  if ( v29 + v8 < v29 )
    WFDSvc::CWFDSvcException::Throw(
      -2147024362,
      "WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspmgr\\src\\asppublicationtable.cpp",
      125,
      L"Function returned bad HRESULT",
      this);
  v31 = operator new[](v30, (const struct std::nothrow_t *)std::nothrow);
  v59 = &CAutoPtr<WFDSvc::ASP::CASPPublicationPrefix,DefaultArrayDeleter>::`vftable';
  v60 = v31;
  if ( !v31 )
    WFDSvc::CWFDSvcException::Throw(
      -2147024882,
      "WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspmgr\\src\\asppublicationtable.cpp",
      130,
      L"Allocation of spAdvertisedServiceList failed",
      this);
  memset_0(v31, 0, v30);
  *v31 = 2621824;
  *((_WORD *)v31 + 2) = *((_WORD *)this + 28);
  v31[2] = v48;
  v31[3] = 40;
  v31[4] = v26 + v6 + v45 + v7;
  v47 = v26 + 40 + v6 + v45;
  v33 = v31 + 10;
  v34 = (unsigned __int8 *)v63[0];
  v56 = (unsigned __int8 *)v63[0];
  v57 = &WFDSvc::ForwardIteratorTraits<WFDSvc::ListNode<WFDSvc::ASP::StringPointerAndLength>>::`vftable';
  v55 = &WFDSvc::BaseListIterator<WFDSvc::ListNode<SmartPointer<WFDSvc::ASP::CASPPublication>>,WFDSvc::ForwardIteratorTraits<WFDSvc::ListNode<SmartPointer<WFDSvc::ASP::CASPPublication>>>>::`vftable';
  while ( v34 )
  {
    *v33 = 0;
    v33[3] = 0;
    v35 = *((_QWORD *)v34 + 3);
    v33[1] = *(_DWORD *)v35;
    *((_WORD *)v33 + 4) = *(_WORD *)(v35 + 4);
    *((_WORD *)v33 + 8) = 1;
    *(_QWORD *)(v33 + 43) = 0;
    *((_BYTE *)v33 + 164) = v34[8];
    v33[42] = v27;
    *((_WORD *)v33 + 9) = 0;
    memcpy_0((char *)v31 + v27, *((const void **)v34 + 2), v34[8]);
    v27 += v34[8];
    v33 += 45;
    WFDSvc::ListIterator<WFDSvc::ListNode<WFDSvc::ASPCoordination::CSocketWrapper::ReceiveListenerWrapper>,WFDSvc::ForwardIteratorTraits<WFDSvc::ListNode<WFDSvc::ASPCoordination::CSocketWrapper::ReceiveListenerWrapper>>>::operator++(&v55);
    v34 = v56;
  }
  v36 = (unsigned __int8 *)*((_QWORD *)this + 3);
  v56 = v36;
  v57 = &WFDSvc::ForwardIteratorTraits<WFDSvc::ListNode<SmartPointer<WFDSvc::ASP::IASPConnection>>>::`vftable';
  v55 = &WFDSvc::BaseListIterator<WFDSvc::ListNode<SmartPointer<WFDSvc::ASP::CASPPublication>>,WFDSvc::ForwardIteratorTraits<WFDSvc::ListNode<SmartPointer<WFDSvc::ASP::CASPPublication>>>>::`vftable';
  while ( v36 )
  {
    v37 = *(_QWORD *)v36;
    v54 = v37;
    SmartPointer<WFDSvc::ASPCoordination::ASPUnknownMessage>::AddRef(&v54);
    v50 = 0;
    v38 = WFDSvc::ASP::CASPPublication::GetUtf8ServiceName((WFDSvc::ASP::CASPPublication *)v37, &v50);
    v51 = 0;
    ServiceInformation = WFDSvc::ASP::CASPPublication::GetServiceInformation((WFDSvc::ASP::CASPPublication *)v37, &v51);
    Src = 0;
    DeferredSessionResponse = WFDSvc::ASP::CASPPublication::GetDeferredSessionResponse(
                                (WFDSvc::ASP::CASPPublication *)v37,
                                (unsigned __int8 **)&Src);
    if ( DeferredSessionResponse > 0x90 )
      WFDSvc::CWFDSvcException::Throw(
        -2147024883,
        "WFDSvc::ASP::CASPPublicationTable::CreateDot11ServiceAdvertisementList",
        "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspmgr\\src\\asppublicationtable.cpp",
        0x1CFu,
        L"Deferred Session Info for service is too long");
    *v33 = *(_DWORD *)(v37 + 888);
    v33[3] = *(_DWORD *)(v37 + 848);
    v33[1] = *(_DWORD *)(v37 + 796);
    *((_WORD *)v33 + 4) = *(_WORD *)(v37 + 800);
    v41 = *(_DWORD *)(v37 + 856);
    if ( v41 == 2 )
      v41 = *(_DWORD *)(v37 + 860);
    *((_BYTE *)v33 + 16) = v41;
    *((_BYTE *)v33 + 17) = *(_BYTE *)(v37 + 853) != 0;
    v33[43] = ServiceInformation;
    v42 = v47;
    v33[44] = v47;
    *((_BYTE *)v33 + 164) = v38;
    v33[42] = v27;
    *((_WORD *)v33 + 9) = DeferredSessionResponse;
    memcpy_0(v33 + 5, Src, DeferredSessionResponse);
    memcpy_0((char *)v31 + v27, v50, v38);
    memcpy_0((char *)v31 + v42, v51, ServiceInformation);
    v27 += v38;
    v47 = ServiceInformation + v42;
    v33 += 45;
    SmartPointer<WFDSvc::ASPCoordination::ASPCommandMessage>::~SmartPointer<WFDSvc::ASPCoordination::ASPCommandMessage>(&v54);
    WFDSvc::ListIterator<WFDSvc::ListNode<WFDSvc::ASPCoordination::CSocketWrapper::ReceiveListenerWrapper>,WFDSvc::ForwardIteratorTraits<WFDSvc::ListNode<WFDSvc::ASPCoordination::CSocketWrapper::ReceiveListenerWrapper>>>::operator++(&v55);
    v36 = v56;
  }
  if ( a4 )
    *a4 = v30;
  *a5 = (struct _DOT11_WFD_SERVICE_FULL_ADVERTISEMENT_LIST *)v31;
  operator delete(0, v32);
  v62 = &WFDSvc::List<WFDSvc::ASP::StringPointerAndLength>::`vftable';
  v43 = v63[0];
  while ( v43 )
  {
    v44 = v43;
    v43 = (_QWORD *)v43[5];
    *v44 = &ConflictResolver::`vftable';
    operator delete(v44, (const struct std::nothrow_t *)0x30);
  }
  *(_OWORD *)v63 = 0;
  v64 = 0;
  if ( v66 && SRWLock )
    ReleaseSRWLockShared(SRWLock);
}

```

## disassembly

```asm
0x1800be4d8  mov     rax, rsp
0x1800be4db  mov     [rax+8], rbx
0x1800be4df  mov     [rax+20h], r9
0x1800be4e3  mov     [rax+18h], r8d
0x1800be4e7  mov     [rax+10h], edx
0x1800be4ea  push    rbp
0x1800be4eb  push    rsi
0x1800be4ec  push    rdi
0x1800be4ed  push    r12
0x1800be4ef  push    r13
0x1800be4f1  push    r14
0x1800be4f3  push    r15
0x1800be4f5  lea     rbp, [rax-57h]
0x1800be4f9  sub     rsp, 0E0h
0x1800be500  mov     rdi, rcx
0x1800be503  xor     r14d, r14d
0x1800be506  cmp     [rbp+4Fh+arg_20], r14
0x1800be50a  jnz     short loc_1800BE537
0x1800be50c  lea     rax, aInvalidArgumen_2; "Invalid arguments"
0x1800be513  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x1800be518  mov     r9d, 0FEh; unsigned int
0x1800be51e  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800be525  lea     rdx, aWfdsvcAspCaspp_1; "WFDSvc::ASP::CASPPublicationTable::Crea"...
0x1800be52c  mov     ecx, 80070057h; int
0x1800be531  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x1800be537  lea     rdx, [rcx+8]
0x1800be53b  lea     rcx, [rbp+4Fh+SRWLock]
0x1800be53f  call    ??0?$LockSentry@VReadersWriterLock@@$00@@QEAA@AEAVReadersWriterLock@@@Z; LockSentry<ReadersWriterLock,1>::LockSentry<ReadersWriterLock,1>(ReadersWriterLock &)
0x1800be544  nop
0x1800be545  mov     [rsp+110h+var_DC], r14d
0x1800be54a  mov     r13d, r14d
0x1800be54d  mov     esi, r14d
0x1800be550  mov     r15d, r14d
0x1800be553  mov     [rsp+110h+var_E0], r14d
0x1800be558  mov     r12d, [rdi+34h]
0x1800be55c  mov     dword ptr [rsp+110h+var_D8], r12d
0x1800be561  lea     rax, ??_7?$List@UStringPointerAndLength@ASP@WFDSvc@@@WFDSvc@@6B@; const WFDSvc::List<WFDSvc::ASP::StringPointerAndLength>::`vftable'
0x1800be568  mov     [rbp+4Fh+var_70], rax
0x1800be56c  xorps   xmm0, xmm0
0x1800be56f  movdqu  xmmword ptr [rbp+4Fh+var_68], xmm0
0x1800be574  mov     [rbp+4Fh+var_58], r14
0x1800be578  mov     [rbp+4Fh+var_C0], r14d
0x1800be57c  mov     rbx, [rdi+18h]
0x1800be580  mov     [rbp+4Fh+var_80], rbx
0x1800be584  lea     rax, ??_7?$ForwardIteratorTraits@V?$ListNode@V?$SmartPointer@VIASPConnection@ASP@WFDSvc@@@@@WFDSvc@@@WFDSvc@@6B@; const WFDSvc::ForwardIteratorTraits<WFDSvc::ListNode<SmartPointer<WFDSvc::ASP::IASPConnection>>>::`vftable'
0x1800be58b  mov     [rbp+4Fh+var_78], rax
0x1800be58f  lea     rax, ??_7?$BaseListIterator@V?$ListNode@V?$SmartPointer@VCASPPublication@ASP@WFDSvc@@@@@WFDSvc@@V?$ForwardIteratorTraits@V?$ListNode@V?$SmartPointer@VCASPPublication@ASP@WFDSvc@@@@@WFDSvc@@@2@@WFDSvc@@6B@; const WFDSvc::BaseListIterator<WFDSvc::ListNode<SmartPointer<WFDSvc::ASP::CASPPublication>>,WFDSvc::ForwardIteratorTraits<WFDSvc::ListNode<SmartPointer<WFDSvc::ASP::CASPPublication>>>>::`vftable'
0x1800be596  mov     [rbp+4Fh+var_88], rax
0x1800be59a  test    rbx, rbx
0x1800be59d  jz      loc_1800BE87F
0x1800be5a3  mov     rbx, [rbx]
0x1800be5a6  mov     [rbp+4Fh+Src], rbx
0x1800be5aa  lea     rcx, [rbp+4Fh+Src]
0x1800be5ae  call    ?AddRef@?$SmartPointer@VASPUnknownMessage@ASPCoordination@WFDSvc@@@@IEAAXXZ; SmartPointer<WFDSvc::ASPCoordination::ASPUnknownMessage>::AddRef(void)
0x1800be5b3  nop
0x1800be5b4  mov     [rbp+4Fh+var_C8], r14
0x1800be5b8  lea     rdx, [rbp+4Fh+var_C8]; unsigned __int8 **
0x1800be5bc  mov     rcx, rbx; this
0x1800be5bf  call    ?GetUtf8ServiceName@CASPPublication@ASP@WFDSvc@@QEAAKPEAPEAE@Z; WFDSvc::ASP::CASPPublication::GetUtf8ServiceName(uchar * *)
0x1800be5c4  mov     r14d, eax
0x1800be5c7  lea     rdx, [rsp+110h+var_D0]; unsigned __int8 **
0x1800be5cc  mov     rcx, rbx; this
0x1800be5cf  call    ?GetServiceInformation@CASPPublication@ASP@WFDSvc@@QEBAKPEAPEAE@Z; WFDSvc::ASP::CASPPublication::GetServiceInformation(uchar * *)
0x1800be5d4  mov     dword ptr [rbp+4Fh+var_B0], eax
0x1800be5d7  mov     dword ptr [rsp+110h+var_D8+4], 0
0x1800be5df  mov     rdx, [rbx+330h]
0x1800be5e6  mov     [rsp+110h+var_D0], rdx
0x1800be5eb  xor     eax, eax
0x1800be5ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be5f4  mov     [rsp+110h+var_E0], eax
0x1800be5f8  cmp     eax, [rbx+324h]
0x1800be5fe  jnb     loc_1800BE6D6
0x1800be604  movzx   r8d, byte ptr [rdx]
0x1800be608  cmp     r14d, r8d
0x1800be60b  jbe     loc_1800BE78A
0x1800be611  imul    r12, rax, 7
0x1800be615  lea     rax, ??_7ConflictResolver@@6B@; const ConflictResolver::`vftable'
0x1800be61c  mov     [rbp+4Fh+var_A8], rax
0x1800be620  mov     al, [r12+rdx]
0x1800be624  mov     byte ptr [rbp+4Fh+var_A0], al
0x1800be627  mov     rax, [rbp+4Fh+var_C8]
0x1800be62b  mov     [rbp+4Fh+var_98], rax
0x1800be62f  lea     rax, [rdx+1]
0x1800be633  add     rax, r12
0x1800be636  mov     [rbp+4Fh+var_90], rax
0x1800be63a  lea     rdx, [rbp+4Fh+var_A8]
0x1800be63e  lea     rcx, [rbp+4Fh+var_70]; void *
0x1800be642  call    ?TryInsert@?$Set@UStringPointerAndLength@ASP@WFDSvc@@USingleCompare@23@@WFDSvc@@QEAA_N$$QEAUStringPointerAndLength@ASP@2@@Z; WFDSvc::Set<WFDSvc::ASP::StringPointerAndLength,WFDSvc::ASP::SingleCompare>::TryInsert(WFDSvc::ASP::StringPointerAndLength &&)
0x1800be647  nop
0x1800be648  test    al, al
0x1800be64a  jz      short loc_1800BE67D
0x1800be64c  mov     eax, dword ptr [rsp+110h+var_D8]
0x1800be650  lea     edx, [rax+1]
0x1800be653  cmp     edx, eax
0x1800be655  jb      loc_1800BE75A
0x1800be65b  mov     rax, [rsp+110h+var_D0]
0x1800be660  movzx   ecx, byte ptr [r12+rax]
0x1800be665  add     ecx, dword ptr [rsp+110h+var_D8+4]
0x1800be669  cmp     ecx, dword ptr [rsp+110h+var_D8+4]
0x1800be66d  jb      loc_1800BE72A
0x1800be673  mov     dword ptr [rsp+110h+var_D8], edx
0x1800be677  mov     dword ptr [rsp+110h+var_D8+4], ecx
0x1800be67b  jmp     short loc_1800BE6BF
0x1800be67d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be684  lea     rax, WPP_GLOBAL_Control
0x1800be68b  cmp     rcx, rax
0x1800be68e  jz      short loc_1800BE6C6
0x1800be690  cmp     byte ptr [rcx+69h], 4
0x1800be694  jb      short loc_1800BE6C6
0x1800be696  test    byte ptr [rcx+6Ch], 1
0x1800be69a  jz      short loc_1800BE6C6
0x1800be69c  mov     rax, [rsp+110h+var_D0]
0x1800be6a1  movzx   eax, byte ptr [r12+rax]
0x1800be6a6  mov     dword ptr [rsp+110h+var_E8], eax
0x1800be6aa  mov     rax, [rbp+4Fh+var_C8]
0x1800be6ae  mov     [rsp+110h+var_F0], rax
0x1800be6b3  mov     r9, rdi
0x1800be6b6  mov     rcx, [rcx+60h]
0x1800be6ba  call    WPP_SF_qsD
0x1800be6bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be6c6  mov     eax, [rsp+110h+var_E0]
0x1800be6ca  inc     eax
0x1800be6cc  mov     rdx, [rsp+110h+var_D0]
0x1800be6d1  jmp     loc_1800BE5F4
0x1800be6d6  lea     edx, [r14+r13]
0x1800be6da  cmp     edx, r13d
0x1800be6dd  jb      loc_1800BE84F
0x1800be6e3  mov     ecx, dword ptr [rbp+4Fh+var_B0]
0x1800be6e6  add     ecx, esi
0x1800be6e8  cmp     ecx, esi
0x1800be6ea  jb      loc_1800BE81F
0x1800be6f0  mov     eax, dword ptr [rsp+110h+var_D8+4]
0x1800be6f4  add     eax, r15d
0x1800be6f7  cmp     eax, r15d
0x1800be6fa  jb      loc_1800BE7EF
0x1800be700  mov     r13d, edx
0x1800be703  mov     esi, ecx
0x1800be705  mov     r15d, eax
0x1800be708  mov     [rsp+110h+var_E0], eax
0x1800be70c  lea     rcx, [rbp+4Fh+Src]
0x1800be710  call    ??1?$SmartPointer@VASPCommandMessage@ASPCoordination@WFDSvc@@@@QEAA@XZ; SmartPointer<WFDSvc::ASPCoordination::ASPCommandMessage>::~SmartPointer<WFDSvc::ASPCoordination::ASPCommandMessage>(void)
0x1800be715  lea     rcx, [rbp+4Fh+var_88]
0x1800be719  call    ??E?$ListIterator@V?$ListNode@UReceiveListenerWrapper@CSocketWrapper@ASPCoordination@WFDSvc@@@WFDSvc@@V?$ForwardIteratorTraits@V?$ListNode@UReceiveListenerWrapper@CSocketWrapper@ASPCoordination@WFDSvc@@@WFDSvc@@@2@@WFDSvc@@QEAAAEAV01@XZ; WFDSvc::ListIterator<WFDSvc::ListNode<WFDSvc::ASPCoordination::CSocketWrapper::ReceiveListenerWrapper>,WFDSvc::ForwardIteratorTraits<WFDSvc::ListNode<WFDSvc::ASPCoordination::CSocketWrapper::ReceiveListenerWrapper>>>::operator++(void)
0x1800be71e  mov     rbx, [rbp+4Fh+var_80]
0x1800be722  xor     r14d, r14d
0x1800be725  jmp     loc_1800BE59A
0x1800be72a  mov     [rsp+110h+var_E8], rdi; void *
0x1800be72f  lea     rax, aFunctionReturn_2; "Function returned bad HRESULT"
0x1800be736  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x1800be73b  mov     r9d, 13Eh; char
0x1800be741  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800be748  lea     rdx, aWfdsvcAspCaspp_1; "WFDSvc::ASP::CASPPublicationTable::Crea"...
0x1800be74f  mov     ecx, 80070216h; int
0x1800be754  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBGPEBX@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800be75a  mov     [rsp+110h+var_E8], rdi; void *
0x1800be75f  lea     rax, aFunctionReturn_2; "Function returned bad HRESULT"
0x1800be766  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x1800be76b  mov     r9d, 13Bh; char
0x1800be771  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800be778  lea     rdx, aWfdsvcAspCaspp_1; "WFDSvc::ASP::CASPPublicationTable::Crea"...
0x1800be77f  mov     ecx, 80070216h; int
0x1800be784  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBGPEBX@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800be78a  lea     rax, WPP_GLOBAL_Control
0x1800be791  cmp     rcx, rax
0x1800be794  jz      short loc_1800BE7C4
0x1800be796  cmp     byte ptr [rcx+69h], 1
0x1800be79a  jb      short loc_1800BE7C4
0x1800be79c  test    byte ptr [rcx+6Ch], 1
0x1800be7a0  jz      short loc_1800BE7C4
0x1800be7a2  mov     edx, 0Dh
0x1800be7a7  mov     dword ptr [rsp+110h+var_E8], r14d
0x1800be7ac  mov     dword ptr [rsp+110h+var_F0], r8d
0x1800be7b1  mov     r9, rdi
0x1800be7b4  lea     r8, WPP_42d5f68346563a82d53568ed43f42df4_Traceguids
0x1800be7bb  mov     rcx, [rcx+60h]
0x1800be7bf  call    WPP_SF_qDD
0x1800be7c4  lea     rax, aFailedToReadIn; "Failed to read invalid prefix from publ"...
0x1800be7cb  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x1800be7d0  mov     r9d, 130h; unsigned int
0x1800be7d6  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800be7dd  lea     rdx, aWfdsvcAspCaspp_1; "WFDSvc::ASP::CASPPublicationTable::Crea"...
0x1800be7e4  mov     ecx, 8007000Dh; int
0x1800be7e9  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x1800be7ef  mov     [rsp+110h+var_E8], rdi; void *
0x1800be7f4  lea     rax, aFunctionReturn_2; "Function returned bad HRESULT"
0x1800be7fb  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x1800be800  mov     r9d, 14Fh; char
0x1800be806  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800be80d  lea     rdx, aWfdsvcAspCaspp_1; "WFDSvc::ASP::CASPPublicationTable::Crea"...
0x1800be814  mov     ecx, 80070216h; int
0x1800be819  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBGPEBX@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800be81f  mov     [rsp+110h+var_E8], rdi; void *
0x1800be824  lea     rax, aFunctionReturn_2; "Function returned bad HRESULT"
0x1800be82b  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x1800be830  mov     r9d, 14Dh; char
0x1800be836  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800be83d  lea     rdx, aWfdsvcAspCaspp_1; "WFDSvc::ASP::CASPPublicationTable::Crea"...
0x1800be844  mov     ecx, 80070216h; int
0x1800be849  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBGPEBX@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800be84f  mov     [rsp+110h+var_E8], rdi; void *
0x1800be854  lea     rax, aFunctionReturn_2; "Function returned bad HRESULT"
0x1800be85b  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x1800be860  mov     r9d, 14Bh; char
0x1800be866  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800be86d  lea     rdx, aWfdsvcAspCaspp_1; "WFDSvc::ASP::CASPPublicationTable::Crea"...
0x1800be874  mov     ecx, 80070216h; int
0x1800be879  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBGPEBX@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800be87f  mov     ebx, dword ptr [rsp+110h+var_D8]
0x1800be883  imul    rcx, rbx, 0B4h; unsigned __int64
0x1800be88a  lea     rdx, [rsp+110h+var_DC]; unsigned int *
0x1800be88f  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800be894  mov     ecx, eax; int
0x1800be896  test    eax, eax
0x1800be898  jns     short loc_1800BE8C5
0x1800be89a  mov     [rsp+110h+var_E8], rdi; void *
0x1800be89f  lea     rax, aFunctionReturn_2; "Function returned bad HRESULT"
0x1800be8a6  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x1800be8ab  mov     r9d, 153h; char
0x1800be8b1  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800be8b8  lea     rdx, aWfdsvcAspCaspp_1; "WFDSvc::ASP::CASPPublicationTable::Crea"...
0x1800be8bf  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBGPEBX@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800be8c5  imul    rcx, rbx, 0Fh; unsigned __int64
0x1800be8c9  lea     rdx, [rbp+4Fh+var_C0]; unsigned int *
0x1800be8cd  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800be8d2  mov     ecx, eax; int
0x1800be8d4  test    eax, eax
0x1800be8d6  jns     short loc_1800BE903
0x1800be8d8  mov     [rsp+110h+var_E8], rdi; void *
0x1800be8dd  lea     rax, aFunctionReturn_2; "Function returned bad HRESULT"
0x1800be8e4  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x1800be8e9  mov     r9d, 157h; char
0x1800be8ef  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800be8f6  lea     rdx, aWfdsvcAspCaspp_1; "WFDSvc::ASP::CASPPublicationTable::Crea"...
0x1800be8fd  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBGPEBX@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800be903  mov     eax, [rbp+4Fh+var_C0]
0x1800be906  lea     ecx, [rax+r13]
0x1800be90a  cmp     ecx, eax
0x1800be90c  jb      loc_1800BEE36
0x1800be912  lea     eax, [rcx+r15]
0x1800be916  cmp     eax, ecx
0x1800be918  jb      loc_1800BEE06
0x1800be91e  mov     r14d, [rbp+4Fh+arg_8]
0x1800be922  cmp     eax, r14d
0x1800be925  jbe     short loc_1800BE992
0x1800be927  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be92e  lea     rdx, WPP_GLOBAL_Control
0x1800be935  cmp     rcx, rdx
0x1800be938  jz      short loc_1800BE967
0x1800be93a  cmp     byte ptr [rcx+69h], 1
0x1800be93e  jb      short loc_1800BE967
0x1800be940  test    byte ptr [rcx+6Ch], 1
0x1800be944  jz      short loc_1800BE967
0x1800be946  mov     edx, 0Fh
0x1800be94b  mov     dword ptr [rsp+110h+var_E8], r14d
0x1800be950  mov     dword ptr [rsp+110h+var_F0], eax
0x1800be954  mov     r9, rdi
0x1800be957  lea     r8, WPP_42d5f68346563a82d53568ed43f42df4_Traceguids
0x1800be95e  mov     rcx, [rcx+60h]
0x1800be962  call    WPP_SF_qDD
0x1800be967  lea     rax, aServiceNameLis; "Service name list size exceeded."
0x1800be96e  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x1800be973  mov     r9d, 167h; unsigned int
0x1800be979  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800be980  lea     rdx, aWfdsvcAspCaspp_1; "WFDSvc::ASP::CASPPublicationTable::Crea"...
0x1800be987  mov     ecx, 80070503h; int
0x1800be98c  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x1800be992  mov     eax, [rbp+4Fh+arg_10]
0x1800be995  cmp     esi, eax
0x1800be997  jbe     short loc_1800BE9D8
0x1800be999  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be9a0  lea     rdx, WPP_GLOBAL_Control
0x1800be9a7  cmp     rcx, rdx
0x1800be9aa  jz      short loc_1800BE9D8
0x1800be9ac  cmp     byte ptr [rcx+69h], 4
0x1800be9b0  jb      short loc_1800BE9D8
0x1800be9b2  test    byte ptr [rcx+6Ch], 1
0x1800be9b6  jz      short loc_1800BE9D8
0x1800be9b8  mov     edx, 10h
0x1800be9bd  mov     dword ptr [rsp+110h+var_E8], eax
0x1800be9c1  mov     dword ptr [rsp+110h+var_F0], esi
0x1800be9c5  mov     r9, rdi
0x1800be9c8  lea     r8, WPP_42d5f68346563a82d53568ed43f42df4_Traceguids
0x1800be9cf  mov     rcx, [rcx+60h]
0x1800be9d3  call    WPP_SF_qDD
0x1800be9d8  mov     ebx, [rsp+110h+var_DC]
0x1800be9dc  lea     r14d, [rbx+28h]
0x1800be9e0  cmp     r14d, 28h ; '('
0x1800be9e4  jb      loc_1800BEDD6
0x1800be9ea  lea     eax, [r14+r13]
0x1800be9ee  cmp     eax, r14d
0x1800be9f1  jb      loc_1800BEDA6
0x1800be9f7  lea     ecx, [rax+rsi]
0x1800be9fa  cmp     ecx, eax
0x1800be9fc  jb      loc_1800BED76
0x1800bea02  lea     r12d, [rcx+r15]
0x1800bea06  cmp     r12d, ecx
0x1800bea09  jb      loc_1800BED46
0x1800bea0f  mov     ecx, r12d; unsigned __int64
0x1800bea12  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800bea19  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
  ... truncated ...
```
