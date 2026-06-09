# CConnectionEx::CConnectionEx(ushort const * const,_GUID const &,_GUID const &,RdpListenerTypeEnum,IWRdsProtocolConnection *,_WRDS_CONNECTION_SETTINGS *,IListener *,IWRdsProtocolConnectionCallback * *,long *)

- ea: `0x180018bd0`
- end: `0x1800195b9`
- name: `??0CConnectionEx@@QEAA@QEBGAEBU_GUID@@1W4RdpListenerTypeEnum@@PEAUIWRdsProtocolConnection@@PEAU_WRDS_CONNECTION_SETTINGS@@PEAVIListener@@PEAPEAUIWRdsProtocolConnectionCallback@@PEAJ@Z`
- size: `2537`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, _OWORD *, _OWORD *, int, __int64, unsigned int *Src, __int64, char *, int *)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180044da0`

## callees

- `0x180001008`
- `0x180001184`
- `0x180001688`
- `0x180002544`
- `0x18000a210`
- `0x18000c2f0`
- `0x1800127b0`
- `0x1800130d8`
- `0x180013150`
- `0x180013a18`
- `0x180013d00`
- `0x1800159f8`
- `0x180016200`
- `0x1800163e0`
- `0x180018bd0`
- `0x180024a8c`
- `0x180025fc4`
- `0x180027d54`
- `0x18002817c`
- `0x1800321f0`
- `0x1800330c4`
- `0x18007f950`
- `0x1800c4e0c`
- `0x1800c8010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x1800192fb`
- `ntdll!EtwEventActivityIdControl` at `0x180019504`
- `ntdll!EtwEventActivityIdControl` at `0x1800192fb`
- `ntdll!EtwEventActivityIdControl` at `0x180019504`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180018ed7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180018ed7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018d3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018d3a`

## string_xrefs

- `0x18001954a`: `Task completed successfully`
- `0x180018dce`: `Initializing CConnectionEx object for new incoming connection`
- `0x180018ebb`: `StringCchCopy`
- `0x180018f08`: `CreateEvent OnReady`
- `0x180019371`: `this->SecurityDescriptor.Initialize`

## pseudocode

```c
__int64 __fastcall CConnectionEx::CConnectionEx(
        __int64 a1,
        unsigned __int16 *a2,
        _OWORD *a3,
        _OWORD *a4,
        int a5,
        __int64 a6,
        unsigned int *Src,
        __int64 a8,
        char *a9,
        int *a10)
{
  __int64 *v13; // r12
  __int64 *v14; // r13
  unsigned int v15; // edx
  HANDLE ProcessHeap; // rax
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // r8
  const char *v20; // rdx
  int ConstrainedGuid; // ebx
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  const char *v25; // rax
  int *v26; // rdx
  HANDLE EventW; // rax
  __int64 v28; // rbx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 *v31; // rbx
  __int64 v32; // rcx
  int v33; // r8d
  int v34; // r9d
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  int InstanceOfSessionManager; // eax
  int v39; // esi
  void *v40; // r8
  const char *v41; // rax
  char *v42; // rdx
  struct IRemoteConnectionManager *v43; // rdi
  int v44; // eax
  const char *v45; // rax
  char *v46; // rdx
  struct IRemoteConnectionManager *v48; // [rsp+50h] [rbp-69h] BYREF
  char *v49; // [rsp+58h] [rbp-61h] BYREF
  const char *v50; // [rsp+60h] [rbp-59h] BYREF
  unsigned __int16 *v51; // [rsp+68h] [rbp-51h] BYREF
  __int64 v52; // [rsp+70h] [rbp-49h] BYREF
  const char *v53; // [rsp+78h] [rbp-41h] BYREF
  __int128 v54; // [rsp+80h] [rbp-39h] BYREF
  struct IRemoteConnectionManager *v55; // [rsp+90h] [rbp-29h] BYREF
  int *v56; // [rsp+98h] [rbp-21h]
  __int64 v57; // [rsp+A0h] [rbp-19h]
  __int128 v58; // [rsp+A8h] [rbp-11h] BYREF

  v51 = a2;
  v57 = a1;
  v49 = a9;
  v56 = a10;
  CTSPrivateObject<IConnection>::CTSPrivateObject<IConnection>();
  *(_QWORD *)a1 = &CConnectionEx::`vftable';
  *(_QWORD *)(a1 + 1592) = 0;
  *(_QWORD *)(a1 + 1600) = 0;
  *(_QWORD *)(a1 + 1608) = 0;
  *(_QWORD *)(a1 + 1616) = 0;
  v13 = (__int64 *)(a1 + 1624);
  *(_QWORD *)(a1 + 1624) = 0;
  v14 = (__int64 *)(a1 + 1632);
  *(_QWORD *)(a1 + 1632) = 0;
  *(_QWORD *)(a1 + 1640) = 0;
  CCriticalSection::CCriticalSection((CCriticalSection *)(a1 + 1648), v15);
  *(_OWORD *)(a1 + 1764) = *a3;
  *(_OWORD *)(a1 + 1780) = *a4;
  *(_QWORD *)(a1 + 16040) = 0;
  *(_QWORD *)(a1 + 16052) = 0;
  *(_DWORD *)(a1 + 17276) = -1;
  *(_DWORD *)(a1 + 17280) = -1;
  *(_QWORD *)(a1 + 17284) = 0;
  SmartPtr<IRemoteTerminal>::SmartPtr<IRemoteTerminal>(a1 + 17296, a8);
  *(_QWORD *)(a1 + 17304) = 0;
  *(_QWORD *)(a1 + 17312) = 0;
  *(_QWORD *)(a1 + 17320) = 0;
  *(_QWORD *)(a1 + 17328) = 0;
  *(_QWORD *)(a1 + 17336) = 0;
  *(_DWORD *)(a1 + 17868) = 0;
  *(_QWORD *)(a1 + 17872) = 0;
  *(_DWORD *)(a1 + 17880) = a5;
  *(_QWORD *)(a1 + 17884) = 0;
  *(_QWORD *)(a1 + 17896) = &CTSSecurityDescriptor::`vftable';
  *(_QWORD *)(a1 + 17904) = 0;
  *(_QWORD *)(a1 + 17912) = 0;
  *(_QWORD *)(a1 + 17952) = 0;
  *(_QWORD *)(a1 + 18480) = 0;
  ProcessHeap = GetProcessHeap();
  *(_QWORD *)(a1 + 18488) = 0;
  *(_QWORD *)(a1 + 18496) = 0;
  *(_QWORD *)(a1 + 18504) = 0;
  *(_QWORD *)(a1 + 18512) = ProcessHeap;
  *(_DWORD *)(a1 + 18616) = 0;
  *(_WORD *)(a1 + 18624) = -1;
  *(_QWORD *)(a1 + 18632) = 0;
  *(_QWORD *)(a1 + 18640) = &CConnectionEx::CRDPCallback::`vftable'{for `IWRdsProtocolConnectionCallback'};
  *(_QWORD *)(a1 + 18648) = &CConnectionEx::CRDPCallback::`vftable'{for `IWRdsProtocolShadowCallback'};
  *(_QWORD *)(a1 + 18656) = &CConnectionEx::CRDPCallback::`vftable'{for `IWRdsProtocolConnectionSettings'};
  *(_QWORD *)(a1 + 18664) = &CConnectionEx::CRDPCallback::`vftable'{for `IWTSConnectionCallbackPrivate'};
  *(_QWORD *)(a1 + 18672) = a1;
  v55 = 0;
  v58 = 0;
  if ( (unsigned int)dword_180128170 > 4 )
  {
    v48 = (struct IRemoteConnectionManager *)"Initializing CConnectionEx object for new incoming connection";
    v53 = "CConnectionEx::CConnectionEx";
    v50 = "Connection Start";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)"Connection Start",
      (unsigned int)word_18010F8D2,
      v17,
      v18,
      (__int64)&v50,
      (__int64)&v53,
      (__int64)&v48);
  }
  v48 = 0;
  GetInstanceOfRemoteConnectionManager(&v48);
  *(_QWORD *)(a1 + 18632) = (*(__int64 (__fastcall **)(struct IRemoteConnectionManager *))(*(_QWORD *)v48 + 288LL))(v48);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v48);
  if ( *Src != 1 )
  {
    v19 = *Src;
    v20 = "WRDS_CONNECTION_SETTINGS level passed to CConnectionEx is invalid: %d";
LABEL_5:
    ConstrainedGuid = -2147023591;
    _DbgPrintMessage(8, v20, v19);
    goto LABEL_70;
  }
  v19 = Src[928];
  if ( (_DWORD)v19 != 1 )
  {
    v20 = "WRDS_LISTENER_SETTINGS level passed to CConnectionEx is invalid: %d";
    goto LABEL_5;
  }
  memset_0((void *)(a1 + 1796), 0, 0x28E8u);
  ConstrainedGuid = StringCchCopyW((unsigned __int16 *)(a1 + 1696), 0x20u, v51);
  if ( ConstrainedGuid < 0 )
  {
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_70;
    v51 = (unsigned __int16 *)"CConnectionEx";
    v25 = "StringCchCopy";
    v26 = (int *)byte_18010F893;
LABEL_14:
    v50 = v25;
    v53 = "Warning HResult failed";
    LODWORD(v48) = ConstrainedGuid;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v22,
      (_DWORD)v26,
      v23,
      v24,
      (__int64)&v53,
      (__int64)&v50,
      (__int64)&v48,
      (__int64)&v51);
    goto LABEL_70;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)(a1 + 17872) = EventW;
  if ( !EventW )
  {
    ConstrainedGuid = -2147024882;
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_70;
    v51 = (unsigned __int16 *)"CConnectionEx";
    v25 = "CreateEvent OnReady";
    v26 = &dword_18010F854;
    goto LABEL_14;
  }
  v28 = *(_QWORD *)(a1 + 1592);
  *(_QWORD *)(a1 + 1592) = a6;
  if ( a6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 8LL))(a6);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  if ( (***(int (__fastcall ****)(_QWORD, GUID *, __int64))(a1 + 1592))(
         *(_QWORD *)(a1 + 1592),
         &IID_IWRdsConnectionRdp,
         a1 + 1608) < 0 )
    SmartPtr<ITSRpcClientTrackerMgr>::operator=(a1 + 1608);
  if ( (***(int (__fastcall ****)(_QWORD, GUID *, __int64))(a1 + 1592))(
         *(_QWORD *)(a1 + 1592),
         &IID_IWTSConnectionPrivate,
         a1 + 1616) < 0 )
    SmartPtr<ITSRpcClientTrackerMgr>::operator=(a1 + 1616);
  if ( (***(int (__fastcall ****)(_QWORD, GUID *, __int64))(a1 + 1592))(
         *(_QWORD *)(a1 + 1592),
         &IID_IWRdsWddmIddProps,
         a1 + 1624) < 0 )
  {
    v29 = *v13;
    *v13 = 0;
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  if ( (***(int (__fastcall ****)(_QWORD, GUID *, __int64))(a1 + 1592))(
         *(_QWORD *)(a1 + 1592),
         &IID_IWRdsWddmIddProps1,
         a1 + 1632) < 0 )
  {
    v30 = *v14;
    *v14 = 0;
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  v31 = (__int64 *)(a1 + 1640);
  if ( (***(int (__fastcall ****)(_QWORD, GUID *, __int64))(a1 + 1592))(
         *(_QWORD *)(a1 + 1592),
         &IID_IWRdsEnhancedFastReconnectArbitrator,
         a1 + 1640) < 0 )
  {
    v32 = *v31;
    *v31 = 0;
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  if ( *((_QWORD *)Src + 467) || _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] != *((_QWORD *)Src + 468) )
  {
    *(_OWORD *)(a1 + 17920) = *(_OWORD *)(Src + 934);
    if ( (unsigned int)dword_180128170 > 4 )
    {
      v51 = (unsigned __int16 *)(a1 + 17920);
      v50 = "Got Activity ID from client";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
        v32,
        (unsigned int)byte_18010F7B3,
        v33,
        v34,
        (__int64)&v50,
        (__int64)&v51);
    }
    if ( (unsigned int)dword_180128170 > 4 && (unsigned __int8)tlgKeywordOn(&dword_180128170, 0x470000000000LL) )
    {
      v51 = (unsigned __int16 *)(a1 + 17920);
      v50 = "Termsrv recieved a new connection";
      v53 = "Termsrv";
      v52 = 0x1000000;
      *(_QWORD *)&v54 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
        v35,
        (unsigned int)&byte_18010F75F,
        v36,
        v37,
        (__int64)&v54,
        (__int64)&v52,
        (__int64)&v53,
        (__int64)&v50,
        (__int64)&v51);
    }
    v48 = 0;
    InstanceOfSessionManager = CUtils::GetInstanceOfSessionManager(&v48);
    ConstrainedGuid = InstanceOfSessionManager;
    if ( InstanceOfSessionManager < 0 )
    {
      _DbgPrintMessage(
        8,
        "GetInstanceOfSessionManager failed: 0x%x in %s",
        InstanceOfSessionManager,
        "CConnectionEx::CConnectionEx");
      SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v48);
      goto LABEL_70;
    }
    if ( *(_QWORD *)(a1 + 1608) )
    {
      v54 = *(_OWORD *)(a1 + 17920);
      (*(void (__fastcall **)(struct IRemoteConnectionManager *, __int128 *, __int64))(*(_QWORD *)v48 + 112LL))(
        v48,
        &v54,
        1);
    }
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v48);
  }
  else
  {
    _DbgPrintMessage(
      4,
      "pWRdsConnectionSettings->WRdsConnectionSetting.WRdsConnectionSettings1.EventLogActivityId is NULL");
    ConstrainedGuid = GenerateConstrainedGuid((GUID *)(a1 + 17920), 0xF4400000);
    if ( ConstrainedGuid < 0 )
    {
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v51 = (unsigned __int16 *)"CConnectionEx";
        LODWORD(v48) = ConstrainedGuid;
        v50 = "GenerateConstrainedGuid";
        v53 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v22,
          (unsigned int)byte_18010F815,
          v23,
          v24,
          (__int64)&v53,
          (__int64)&v50,
          (__int64)&v48,
          (__int64)&v51);
      }
      goto LABEL_70;
    }
    if ( (unsigned int)dword_180128170 > 4 )
    {
      v51 = (unsigned __int16 *)(a1 + 17920);
      v50 = "Generated a new ActivityID since we couldn't get one from client";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
        v22,
        (unsigned int)&dword_18010F7E4,
        v23,
        v24,
        (__int64)&v50,
        (__int64)&v51);
    }
  }
  v58 = *(_OWORD *)(a1 + 17920);
  v39 = EtwEventActivityIdControl(4, &v58);
  memcpy_0((void *)(a1 + 12272), Src, 0xEB8u);
  *(_QWORD *)v49 = a1 + 18640;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(a1 + 18640) + 8LL))(a1 + 18640);
  v40 = *(void **)(a1 + 16000);
  if ( v40 )
  {
    ConstrainedGuid = CTSSecurityDescriptor::Initialize(
                        (CTSSecurityDescriptor *)(a1 + 17896),
                        (const unsigned __int16 *)(a1 + 1696),
                        v40);
    if ( ConstrainedGuid < 0 )
    {
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_67;
      v49 = "CConnectionEx";
      v41 = "this->SecurityDescriptor.Initialize";
      v42 = (char *)qword_18010F720;
      goto LABEL_66;
    }
    *(_DWORD *)(a1 + 17888) = 1;
    *(_QWORD *)(a1 + 16000) = 0;
    *(_DWORD *)(a1 + 15996) = 0;
  }
  ConstrainedGuid = GetInstanceOfRemoteConnectionManager(&v55);
  if ( ConstrainedGuid < 0 )
  {
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_67;
    v49 = "CConnectionEx";
    v41 = "GetInstanceOfRemoteConnectionManager";
    v42 = byte_18010F6E1;
    goto LABEL_66;
  }
  v43 = v55;
  ConstrainedGuid = (*(__int64 (__fastcall **)(struct IRemoteConnectionManager *, __int64))(*(_QWORD *)v55 + 128LL))(
                      v55,
                      a1 + 17284);
  if ( ConstrainedGuid < 0 )
  {
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_67;
    v49 = "CConnectionEx";
    v41 = "GetConnectionId";
    v42 = (char *)word_18010F6A2;
    goto LABEL_66;
  }
  *(_DWORD *)(a1 + 17288) = 1;
  ConstrainedGuid = CResource::Initialize((CResource *)(a1 + 18520));
  if ( ConstrainedGuid < 0 )
  {
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_67;
    v49 = "CConnectionEx";
    v41 = "m_SyncLock.Initialize";
    v42 = byte_18010F663;
    goto LABEL_66;
  }
  v44 = (*(__int64 (__fastcall **)(struct IRemoteConnectionManager *))(*(_QWORD *)v43 + 400LL))(v43);
  ConstrainedGuid = CConnectionEx::EnableWddmIdd((CConnectionEx *)a1, v44);
  if ( ConstrainedGuid < 0 && (unsigned int)dword_180128170 > 3 )
  {
    v49 = "CConnectionEx";
    v41 = "EnableWddmIdd";
    v42 = byte_18010F61D;
LABEL_66:
    *(_QWORD *)&v54 = v41;
    v52 = (__int64)"Warning HResult failed";
    LODWORD(v48) = ConstrainedGuid;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v22,
      (_DWORD)v42,
      v23,
      v24,
      (__int64)&v52,
      (__int64)&v54,
      (__int64)&v48,
      (__int64)&v49);
  }
LABEL_67:
  if ( !v39 )
    EtwEventActivityIdControl(2, &v58);
  if ( ConstrainedGuid < 0 )
  {
LABEL_70:
    if ( (unsigned int)dword_180128170 > 3 )
    {
      v49 = "CConnectionEx::CConnectionEx";
      v45 = "Connection Start";
      v46 = byte_18010F5DD;
LABEL_74:
      *(_QWORD *)&v54 = v45;
      LODWORD(v48) = ConstrainedGuid;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v22,
        (_DWORD)v46,
        v23,
        v24,
        (__int64)&v54,
        (__int64)&v49,
        (__int64)&v48);
      goto LABEL_75;
    }
    goto LABEL_75;
  }
  if ( (unsigned int)dword_180128170 > 5 )
  {
    v49 = "CConnectionEx::CConnectionEx";
    v45 = "Task completed successfully";
    v46 = byte_18010F5A5;
    goto LABEL_74;
  }
LABEL_75:
  *v56 = ConstrainedGuid;
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v55);
  return a1;
}

```

## disassembly

```asm
0x180018bd0  mov     [rsp-8+arg_10], rbx
0x180018bd5  push    rbp
0x180018bd6  push    rsi
0x180018bd7  push    rdi
0x180018bd8  push    r12
0x180018bda  push    r13
0x180018bdc  push    r14
0x180018bde  push    r15
0x180018be0  lea     rbp, [rsp-7]
0x180018be5  sub     rsp, 0C0h
0x180018bec  mov     rax, cs:__security_cookie
0x180018bf3  xor     rax, rsp
0x180018bf6  mov     [rbp+37h+var_38], rax
0x180018bfa  mov     rdi, r9
0x180018bfd  mov     rbx, r8
0x180018c00  mov     [rbp+37h+var_88], rdx
0x180018c04  mov     r14, rcx
0x180018c07  mov     r15, [rbp+37h+Src]
0x180018c0b  mov     [rbp+37h+var_50], rcx
0x180018c0f  mov     rsi, [rbp+37h+arg_38]
0x180018c13  mov     rax, [rbp+37h+arg_40]
0x180018c1a  mov     [rbp+37h+var_98], rax
0x180018c1e  mov     rax, [rbp+37h+arg_48]
0x180018c25  mov     [rbp+37h+var_58], rax
0x180018c29  call    ??0?$CTSPrivateObject@VIConnection@@@@QEAA@PEBD@Z; CTSPrivateObject<IConnection>::CTSPrivateObject<IConnection>(char const *)
0x180018c2e  nop
0x180018c2f  lea     rax, ??_7CConnectionEx@@6B@; const CConnectionEx::`vftable'
0x180018c36  mov     [r14], rax
0x180018c39  xor     eax, eax
0x180018c3b  mov     [r14+638h], rax
0x180018c42  mov     [r14+640h], rax
0x180018c49  mov     [r14+648h], rax
0x180018c50  mov     [r14+650h], rax
0x180018c57  lea     r12, [r14+658h]
0x180018c5e  mov     [r12], rax
0x180018c62  lea     r13, [r14+660h]
0x180018c69  mov     [r13+0], rax
0x180018c6d  mov     [r14+668h], rax
0x180018c74  lea     rcx, [r14+670h]; this
0x180018c7b  call    ??0CCriticalSection@@QEAA@K@Z; CCriticalSection::CCriticalSection(ulong)
0x180018c80  nop
0x180018c81  movups  xmm0, xmmword ptr [rbx]
0x180018c84  movdqu  xmmword ptr [r14+6E4h], xmm0
0x180018c8d  movups  xmm1, xmmword ptr [rdi]
0x180018c90  movdqu  xmmword ptr [r14+6F4h], xmm1
0x180018c99  xor     edi, edi
0x180018c9b  mov     [r14+3EA8h], rdi
0x180018ca2  mov     [r14+3EB4h], rdi
0x180018ca9  or      eax, 0FFFFFFFFh
0x180018cac  mov     [r14+437Ch], eax
0x180018cb3  mov     [r14+4380h], eax
0x180018cba  mov     [r14+4384h], rdi
0x180018cc1  lea     rcx, [r14+4390h]
0x180018cc8  mov     rdx, rsi
0x180018ccb  call    ??0?$SmartPtr@VIRemoteTerminal@@@@QEAA@PEAVIRemoteTerminal@@@Z; SmartPtr<IRemoteTerminal>::SmartPtr<IRemoteTerminal>(IRemoteTerminal *)
0x180018cd0  nop
0x180018cd1  mov     [r14+4398h], rdi
0x180018cd8  mov     [r14+43A0h], rdi
0x180018cdf  mov     [r14+43A8h], rdi
0x180018ce6  mov     [r14+43B0h], rdi
0x180018ced  mov     [r14+43B8h], rdi
0x180018cf4  mov     [r14+45CCh], edi
0x180018cfb  mov     [r14+45D0h], rdi
0x180018d02  mov     eax, [rbp+37h+arg_20]
0x180018d05  mov     [r14+45D8h], eax
0x180018d0c  mov     [r14+45DCh], rdi
0x180018d13  lea     rax, [r14+45E8h]
0x180018d1a  lea     rcx, ??_7CTSSecurityDescriptor@@6B@; const CTSSecurityDescriptor::`vftable'
0x180018d21  mov     [rax], rcx
0x180018d24  mov     [rax+8], rdi
0x180018d28  mov     [rax+10h], rdi
0x180018d2c  mov     [r14+4620h], rdi
0x180018d33  mov     [r14+4830h], rdi
0x180018d3a  call    cs:__imp_GetProcessHeap
0x180018d40  mov     [r14+4838h], rdi
0x180018d47  mov     [r14+4840h], rdi
0x180018d4e  mov     [r14+4848h], rdi
0x180018d55  mov     [r14+4850h], rax
0x180018d5c  mov     [r14+48B8h], edi
0x180018d63  mov     word ptr [r14+48C0h], 0FFFFh
0x180018d6d  mov     [r14+48C8h], rdi
0x180018d74  lea     rax, [r14+48D0h]
0x180018d7b  lea     rcx, ??_7CRDPCallback@CConnectionEx@@6BIWRdsProtocolConnectionCallback@@@; const CConnectionEx::CRDPCallback::`vftable'{for `IWRdsProtocolConnectionCallback'}
0x180018d82  mov     [rax], rcx
0x180018d85  lea     rcx, ??_7CRDPCallback@CConnectionEx@@6BIWRdsProtocolShadowCallback@@@; const CConnectionEx::CRDPCallback::`vftable'{for `IWRdsProtocolShadowCallback'}
0x180018d8c  mov     [rax+8], rcx
0x180018d90  lea     rcx, ??_7CRDPCallback@CConnectionEx@@6BIWRdsProtocolConnectionSettings@@@; const CConnectionEx::CRDPCallback::`vftable'{for `IWRdsProtocolConnectionSettings'}
0x180018d97  mov     [rax+10h], rcx
0x180018d9b  lea     rcx, ??_7CRDPCallback@CConnectionEx@@6BIWTSConnectionCallbackPrivate@@@; const CConnectionEx::CRDPCallback::`vftable'{for `IWTSConnectionCallbackPrivate'}
0x180018da2  mov     [rax+18h], rcx
0x180018da6  mov     [rax+20h], r14
0x180018daa  mov     [rbp+37h+var_60], rdi
0x180018dae  xorps   xmm0, xmm0
0x180018db1  movups  [rbp+37h+var_48], xmm0
0x180018db5  mov     eax, cs:dword_180128170
0x180018dbb  lea     rsi, aCconnectionexC_12; "CConnectionEx::CConnectionEx"
0x180018dc2  lea     rcx, aConnectionStar; "Connection Start"
0x180018dc9  cmp     eax, 4
0x180018dcc  jbe     short loc_180018E08
0x180018dce  lea     rax, aInitializingCc; "Initializing CConnectionEx object for n"...
0x180018dd5  mov     [rbp+37h+var_A0], rax
0x180018dd9  mov     [rbp+37h+var_78], rsi
0x180018ddd  mov     [rbp+37h+var_90], rcx
0x180018de1  lea     rax, [rbp+37h+var_A0]
0x180018de5  mov     [rsp+0F0h+var_C0], rax
0x180018dea  lea     rax, [rbp+37h+var_78]
0x180018dee  mov     [rsp+0F0h+var_C8], rax
0x180018df3  lea     rax, [rbp+37h+var_90]
0x180018df7  mov     [rsp+0F0h+var_D0], rax
0x180018dfc  lea     rdx, word_18010F8D2
0x180018e03  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180018e08  mov     [rbp+37h+var_A0], rdi
0x180018e0c  lea     rcx, [rbp+37h+var_A0]; struct IRemoteConnectionManager **
0x180018e10  call    ?GetInstanceOfRemoteConnectionManager@@YAJPEAPEAVIRemoteConnectionManager@@@Z; GetInstanceOfRemoteConnectionManager(IRemoteConnectionManager * *)
0x180018e15  mov     rcx, [rbp+37h+var_A0]
0x180018e19  mov     rax, [rcx]
0x180018e1c  mov     rax, [rax+120h]
0x180018e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e28  mov     [r14+48C8h], rax
0x180018e2f  lea     rcx, [rbp+37h+var_A0]; void *
0x180018e33  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180018e38  cmp     dword ptr [r15], 1
0x180018e3c  jz      short loc_180018E5C
0x180018e3e  mov     r8d, [r15]
0x180018e41  lea     rdx, aWrdsConnection; "WRDS_CONNECTION_SETTINGS level passed t"...
0x180018e48  mov     ebx, 80070519h
0x180018e4d  mov     ecx, 8; int
0x180018e52  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180018e57  jmp     loc_180019515
0x180018e5c  mov     r8d, [r15+0E80h]
0x180018e63  cmp     r8d, 1
0x180018e67  jz      short loc_180018E72
0x180018e69  lea     rdx, aWrdsListenerSe; "WRDS_LISTENER_SETTINGS level passed to "...
0x180018e70  jmp     short loc_180018E48
0x180018e72  lea     rcx, [r14+704h]; void *
0x180018e79  xor     edx, edx; Val
0x180018e7b  mov     r8d, 28E8h; Size
0x180018e81  call    memset_0
0x180018e86  lea     rcx, [r14+6A0h]; unsigned __int16 *
0x180018e8d  mov     r8, [rbp+37h+var_88]; unsigned __int16 *
0x180018e91  mov     edx, 20h ; ' '; unsigned __int64
0x180018e96  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018e9b  mov     ebx, eax
0x180018e9d  test    eax, eax
0x180018e9f  jns     short loc_180018ECB
0x180018ea1  mov     eax, cs:dword_180128170
0x180018ea7  cmp     eax, 3
0x180018eaa  jbe     loc_180019515
0x180018eb0  lea     rax, aCconnectionex; "CConnectionEx"
0x180018eb7  mov     [rbp+37h+var_88], rax
0x180018ebb  lea     rax, aStringcchcopy; "StringCchCopy"
0x180018ec2  lea     rdx, byte_18010F893
0x180018ec9  jmp     short loc_180018F16
0x180018ecb  xor     r9d, r9d; lpName
0x180018ece  xor     r8d, r8d; bInitialState
0x180018ed1  lea     edx, [r9+1]; bManualReset
0x180018ed5  xor     ecx, ecx; lpEventAttributes
0x180018ed7  call    cs:__imp_CreateEventW
0x180018edd  mov     [r14+45D0h], rax
0x180018ee4  test    rax, rax
0x180018ee7  jnz     short loc_180018F56
0x180018ee9  mov     ebx, 8007000Eh
0x180018eee  mov     eax, cs:dword_180128170
0x180018ef4  cmp     eax, 3
0x180018ef7  jbe     loc_180019515
0x180018efd  lea     rax, aCconnectionex; "CConnectionEx"
0x180018f04  mov     [rbp+37h+var_88], rax
0x180018f08  lea     rax, aCreateeventOnr; "CreateEvent OnReady"
0x180018f0f  lea     rdx, dword_18010F854
0x180018f16  mov     [rbp+37h+var_90], rax
0x180018f1a  lea     rax, aWarningHresult; "Warning HResult failed"
0x180018f21  mov     [rbp+37h+var_78], rax
0x180018f25  lea     rax, [rbp+37h+var_88]
0x180018f29  mov     [rsp+0F0h+var_B8], rax
0x180018f2e  lea     rax, [rbp+37h+var_A0]
0x180018f32  mov     [rsp+0F0h+var_C0], rax
0x180018f37  lea     rax, [rbp+37h+var_90]
0x180018f3b  mov     [rsp+0F0h+var_C8], rax
0x180018f40  lea     rax, [rbp+37h+var_78]
0x180018f44  mov     [rsp+0F0h+var_D0], rax
0x180018f49  mov     dword ptr [rbp+37h+var_A0], ebx
0x180018f4c  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180018f51  jmp     loc_180019515
0x180018f56  mov     rbx, [r14+638h]
0x180018f5d  mov     rcx, [rbp+37h+arg_28]
0x180018f61  mov     [r14+638h], rcx
0x180018f68  test    rcx, rcx
0x180018f6b  jz      short loc_180018F79
0x180018f6d  mov     rax, [rcx]
0x180018f70  mov     rax, [rax+8]
0x180018f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f79  test    rbx, rbx
0x180018f7c  jz      short loc_180018F8D
0x180018f7e  mov     rax, [rbx]
0x180018f81  mov     rcx, rbx
0x180018f84  mov     rax, [rax+10h]
0x180018f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f8d  mov     rcx, [r14+638h]
0x180018f94  mov     rax, [rcx]
0x180018f97  lea     rsi, [r14+648h]
0x180018f9e  mov     r8, rsi
0x180018fa1  lea     rdx, IID_IWRdsConnectionRdp
0x180018fa8  mov     rax, [rax]
0x180018fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fb0  test    eax, eax
0x180018fb2  jns     short loc_180018FBC
0x180018fb4  mov     rcx, rsi
0x180018fb7  call    ??4?$SmartPtr@VITSRpcClientTrackerMgr@@@@QEAAAEAV0@PEAVITSRpcClientTrackerMgr@@@Z; SmartPtr<ITSRpcClientTrackerMgr>::operator=(ITSRpcClientTrackerMgr *)
0x180018fbc  mov     rcx, [r14+638h]
0x180018fc3  mov     rax, [rcx]
0x180018fc6  lea     rbx, [r14+650h]
0x180018fcd  mov     r8, rbx
0x180018fd0  lea     rdx, IID_IWTSConnectionPrivate
0x180018fd7  mov     rax, [rax]
0x180018fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fdf  test    eax, eax
0x180018fe1  jns     short loc_180018FEB
0x180018fe3  mov     rcx, rbx
0x180018fe6  call    ??4?$SmartPtr@VITSRpcClientTrackerMgr@@@@QEAAAEAV0@PEAVITSRpcClientTrackerMgr@@@Z; SmartPtr<ITSRpcClientTrackerMgr>::operator=(ITSRpcClientTrackerMgr *)
0x180018feb  mov     rcx, [r14+638h]
0x180018ff2  mov     rax, [rcx]
0x180018ff5  mov     r8, r12
0x180018ff8  lea     rdx, IID_IWRdsWddmIddProps
0x180018fff  mov     rax, [rax]
0x180019002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019007  test    eax, eax
0x180019009  jns     short loc_180019024
0x18001900b  mov     rcx, [r12]
0x18001900f  mov     [r12], rdi
0x180019013  test    rcx, rcx
0x180019016  jz      short loc_180019024
0x180019018  mov     rax, [rcx]
0x18001901b  mov     rax, [rax+10h]
0x18001901f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019024  mov     rcx, [r14+638h]
0x18001902b  mov     rax, [rcx]
0x18001902e  mov     r8, r13
0x180019031  lea     rdx, IID_IWRdsWddmIddProps1
0x180019038  mov     rax, [rax]
0x18001903b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019040  test    eax, eax
0x180019042  jns     short loc_18001905D
0x180019044  mov     rcx, [r13+0]
0x180019048  mov     [r13+0], rdi
0x18001904c  test    rcx, rcx
0x18001904f  jz      short loc_18001905D
0x180019051  mov     rax, [rcx]
0x180019054  mov     rax, [rax+10h]
0x180019058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001905d  mov     rcx, [r14+638h]
0x180019064  mov     rax, [rcx]
0x180019067  lea     rbx, [r14+668h]
0x18001906e  mov     r8, rbx
0x180019071  lea     rdx, IID_IWRdsEnhancedFastReconnectArbitrator
0x180019078  mov     rax, [rax]
0x18001907b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019080  test    eax, eax
0x180019082  jns     short loc_18001909B
0x180019084  mov     rcx, [rbx]
0x180019087  mov     [rbx], rdi
0x18001908a  test    rcx, rcx
0x18001908d  jz      short loc_18001909B
0x18001908f  mov     rax, [rcx]
0x180019092  mov     rax, [rax+10h]
0x180019096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001909b  xorps   xmm0, xmm0
0x18001909e  movq    rax, xmm0
0x1800190a3  cmp     rax, [r15+0E98h]
0x1800190aa  jnz     loc_180019195
0x1800190b0  psrldq  xmm0, 8
0x1800190b5  movq    rax, xmm0
0x1800190ba  cmp     rax, [r15+0EA0h]
0x1800190c1  jnz     loc_180019195
0x1800190c7  lea     rdx, aPwrdsconnectio; "pWRdsConnectionSettings->WRdsConnection"...
0x1800190ce  mov     ecx, 4; int
0x1800190d3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800190d8  lea     rdi, [r14+4600h]
0x1800190df  mov     edx, 0F4400000h; unsigned int
0x1800190e4  mov     rcx, rdi; pguid
0x1800190e7  call    ?GenerateConstrainedGuid@@YAJPEAU_GUID@@K@Z; GenerateConstrainedGuid(_GUID *,ulong)
0x1800190ec  mov     ebx, eax
0x1800190ee  test    eax, eax
0x1800190f0  mov     eax, cs:dword_180128170
0x1800190f6  jns     short loc_18001915A
0x1800190f8  cmp     eax, 3
0x1800190fb  jbe     loc_18001950E
0x180019101  lea     rax, aCconnectionex; "CConnectionEx"
0x180019108  mov     [rbp+37h+var_88], rax
0x18001910c  mov     dword ptr [rbp+37h+var_A0], ebx
0x18001910f  lea     rax, aGenerateconstr_0; "GenerateConstrainedGuid"
0x180019116  mov     [rbp+37h+var_90], rax
0x18001911a  lea     rax, aWarningHresult; "Warning HResult failed"
0x180019121  mov     [rbp+37h+var_78], rax
0x180019125  lea     rax, [rbp+37h+var_88]
0x180019129  mov     [rsp+0F0h+var_B8], rax
0x18001912e  lea     rax, [rbp+37h+var_A0]
0x180019132  mov     [rsp+0F0h+var_C0], rax
0x180019137  lea     rax, [rbp+37h+var_90]
0x18001913b  mov     [rsp+0F0h+var_C8], rax
0x180019140  lea     rax, [rbp+37h+var_78]
  ... truncated ...
```
