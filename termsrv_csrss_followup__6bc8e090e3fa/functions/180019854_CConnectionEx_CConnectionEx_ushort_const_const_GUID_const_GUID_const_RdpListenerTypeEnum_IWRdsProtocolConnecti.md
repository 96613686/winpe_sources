# CConnectionEx::CConnectionEx(ushort const * const,_GUID const &,_GUID const &,RdpListenerTypeEnum,IWRdsProtocolConnection *,_WRDS_CONNECTION_SETTINGS *,IListener *,IWRdsProtocolConnectionCallback * *,long *)

- ea: `0x180019854`
- end: `0x18001a256`
- name: `??0CConnectionEx@@QEAA@QEBGAEBU_GUID@@1W4RdpListenerTypeEnum@@PEAUIWRdsProtocolConnection@@PEAU_WRDS_CONNECTION_SETTINGS@@PEAVIListener@@PEAPEAUIWRdsProtocolConnectionCallback@@PEAJ@Z`
- size: `2562`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180047180`

## callees

- `0x180001008`
- `0x18000118c`
- `0x1800016a8`
- `0x18000256c`
- `0x180009940`
- `0x18000c2a0`
- `0x180012d10`
- `0x180013948`
- `0x1800139c0`
- `0x1800143e4`
- `0x1800146c8`
- `0x1800164ac`
- `0x180016d38`
- `0x180016e30`
- `0x180019854`
- `0x180025e6c`
- `0x180027434`
- `0x180029420`
- `0x180029754`
- `0x180033f60`
- `0x180034e64`
- `0x1800830e0`
- `0x1800caedc`
- `0x1800ce010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180019f8b`
- `ntdll!EtwEventActivityIdControl` at `0x18001a19a`
- `ntdll!EtwEventActivityIdControl` at `0x180019f8b`
- `ntdll!EtwEventActivityIdControl` at `0x18001a19a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019b61`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019b61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800199be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800199be`

## string_xrefs

- `0x18001a1e6`: `Task completed successfully`
- `0x180019a58`: `Initializing CConnectionEx object for new incoming connection`
- `0x180019b45`: `StringCchCopy`
- `0x180019b98`: `CreateEvent OnReady`
- `0x18001a007`: `this->SecurityDescriptor.Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
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
  __int64 v33; // r8
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
  if ( (unsigned int)dword_18012E170 > 4 )
  {
    v48 = (struct IRemoteConnectionManager *)"Initializing CConnectionEx object for new incoming connection";
    v53 = "CConnectionEx::CConnectionEx";
    v50 = "Connection Start";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)"Connection Start",
      (unsigned int)word_180115952,
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
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_70;
    v51 = (unsigned __int16 *)"CConnectionEx";
    v25 = "StringCchCopy";
    v26 = (int *)byte_180115913;
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
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_70;
    v51 = (unsigned __int16 *)"CConnectionEx";
    v25 = "CreateEvent OnReady";
    v26 = &dword_1801158D4;
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
    if ( (unsigned int)dword_18012E170 > 4 )
    {
      v51 = (unsigned __int16 *)(a1 + 17920);
      v50 = "Got Activity ID from client";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
        v32,
        (unsigned int)byte_180115833,
        v33,
        v34,
        (__int64)&v50,
        (__int64)&v51);
    }
    if ( (unsigned int)dword_18012E170 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18012E170, 0x470000000000LL, v33) )
    {
      v51 = (unsigned __int16 *)(a1 + 17920);
      v50 = "Termsrv recieved a new connection";
      v53 = "Termsrv";
      v52 = 0x1000000;
      *(_QWORD *)&v54 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
        v35,
        (unsigned int)&byte_1801157DF,
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
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v51 = (unsigned __int16 *)"CConnectionEx";
        LODWORD(v48) = ConstrainedGuid;
        v50 = "GenerateConstrainedGuid";
        v53 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v22,
          (unsigned int)byte_180115895,
          v23,
          v24,
          (__int64)&v53,
          (__int64)&v50,
          (__int64)&v48,
          (__int64)&v51);
      }
      goto LABEL_70;
    }
    if ( (unsigned int)dword_18012E170 > 4 )
    {
      v51 = (unsigned __int16 *)(a1 + 17920);
      v50 = "Generated a new ActivityID since we couldn't get one from client";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
        v22,
        (unsigned int)&dword_180115864,
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
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_67;
      v49 = "CConnectionEx";
      v41 = "this->SecurityDescriptor.Initialize";
      v42 = (char *)qword_1801157A0;
      goto LABEL_66;
    }
    *(_DWORD *)(a1 + 17888) = 1;
    *(_QWORD *)(a1 + 16000) = 0;
    *(_DWORD *)(a1 + 15996) = 0;
  }
  ConstrainedGuid = GetInstanceOfRemoteConnectionManager(&v55);
  if ( ConstrainedGuid < 0 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_67;
    v49 = "CConnectionEx";
    v41 = "GetInstanceOfRemoteConnectionManager";
    v42 = byte_180115761;
    goto LABEL_66;
  }
  v43 = v55;
  ConstrainedGuid = (*(__int64 (__fastcall **)(struct IRemoteConnectionManager *, __int64))(*(_QWORD *)v55 + 128LL))(
                      v55,
                      a1 + 17284);
  if ( ConstrainedGuid < 0 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_67;
    v49 = "CConnectionEx";
    v41 = "GetConnectionId";
    v42 = (char *)word_180115722;
    goto LABEL_66;
  }
  *(_DWORD *)(a1 + 17288) = 1;
  ConstrainedGuid = CResource::Initialize((CResource *)(a1 + 18520));
  if ( ConstrainedGuid < 0 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_67;
    v49 = "CConnectionEx";
    v41 = "m_SyncLock.Initialize";
    v42 = byte_1801156E3;
    goto LABEL_66;
  }
  v44 = (*(__int64 (__fastcall **)(struct IRemoteConnectionManager *))(*(_QWORD *)v43 + 400LL))(v43);
  ConstrainedGuid = CConnectionEx::EnableWddmIdd((CConnectionEx *)a1, v44);
  if ( ConstrainedGuid < 0 && (unsigned int)dword_18012E170 > 3 )
  {
    v49 = "CConnectionEx";
    v41 = "EnableWddmIdd";
    v42 = byte_18011569D;
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
    if ( (unsigned int)dword_18012E170 > 3 )
    {
      v49 = "CConnectionEx::CConnectionEx";
      v45 = "Connection Start";
      v46 = byte_18011565D;
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
  if ( (unsigned int)dword_18012E170 > 5 )
  {
    v49 = "CConnectionEx::CConnectionEx";
    v45 = "Task completed successfully";
    v46 = byte_180115625;
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
0x180019854  mov     [rsp-8+arg_10], rbx
0x180019859  push    rbp
0x18001985a  push    rsi
0x18001985b  push    rdi
0x18001985c  push    r12
0x18001985e  push    r13
0x180019860  push    r14
0x180019862  push    r15
0x180019864  lea     rbp, [rsp-7]
0x180019869  sub     rsp, 0C0h
0x180019870  mov     rax, cs:__security_cookie
0x180019877  xor     rax, rsp
0x18001987a  mov     [rbp+37h+var_38], rax
0x18001987e  mov     rdi, r9
0x180019881  mov     rbx, r8
0x180019884  mov     [rbp+37h+var_88], rdx
0x180019888  mov     r14, rcx
0x18001988b  mov     r15, [rbp+37h+Src]
0x18001988f  mov     [rbp+37h+var_50], rcx
0x180019893  mov     rsi, [rbp+37h+arg_38]
0x180019897  mov     rax, [rbp+37h+arg_40]
0x18001989e  mov     [rbp+37h+var_98], rax
0x1800198a2  mov     rax, [rbp+37h+arg_48]
0x1800198a9  mov     [rbp+37h+var_58], rax
0x1800198ad  call    ??0?$CTSPrivateObject@VIConnection@@@@QEAA@PEBD@Z; CTSPrivateObject<IConnection>::CTSPrivateObject<IConnection>(char const *)
0x1800198b2  nop
0x1800198b3  lea     rax, ??_7CConnectionEx@@6B@; const CConnectionEx::`vftable'
0x1800198ba  mov     [r14], rax
0x1800198bd  xor     eax, eax
0x1800198bf  mov     [r14+638h], rax
0x1800198c6  mov     [r14+640h], rax
0x1800198cd  mov     [r14+648h], rax
0x1800198d4  mov     [r14+650h], rax
0x1800198db  lea     r12, [r14+658h]
0x1800198e2  mov     [r12], rax
0x1800198e6  lea     r13, [r14+660h]
0x1800198ed  mov     [r13+0], rax
0x1800198f1  mov     [r14+668h], rax
0x1800198f8  lea     rcx, [r14+670h]; this
0x1800198ff  call    ??0CCriticalSection@@QEAA@K@Z; CCriticalSection::CCriticalSection(ulong)
0x180019904  nop
0x180019905  movups  xmm0, xmmword ptr [rbx]
0x180019908  movdqu  xmmword ptr [r14+6E4h], xmm0
0x180019911  movups  xmm1, xmmword ptr [rdi]
0x180019914  movdqu  xmmword ptr [r14+6F4h], xmm1
0x18001991d  xor     edi, edi
0x18001991f  mov     [r14+3EA8h], rdi
0x180019926  mov     [r14+3EB4h], rdi
0x18001992d  or      eax, 0FFFFFFFFh
0x180019930  mov     [r14+437Ch], eax
0x180019937  mov     [r14+4380h], eax
0x18001993e  mov     [r14+4384h], rdi
0x180019945  lea     rcx, [r14+4390h]
0x18001994c  mov     rdx, rsi
0x18001994f  call    ??0?$SmartPtr@VIRemoteTerminal@@@@QEAA@PEAVIRemoteTerminal@@@Z; SmartPtr<IRemoteTerminal>::SmartPtr<IRemoteTerminal>(IRemoteTerminal *)
0x180019954  nop
0x180019955  mov     [r14+4398h], rdi
0x18001995c  mov     [r14+43A0h], rdi
0x180019963  mov     [r14+43A8h], rdi
0x18001996a  mov     [r14+43B0h], rdi
0x180019971  mov     [r14+43B8h], rdi
0x180019978  mov     [r14+45CCh], edi
0x18001997f  mov     [r14+45D0h], rdi
0x180019986  mov     eax, [rbp+37h+arg_20]
0x180019989  mov     [r14+45D8h], eax
0x180019990  mov     [r14+45DCh], rdi
0x180019997  lea     rax, [r14+45E8h]
0x18001999e  lea     rcx, ??_7CTSSecurityDescriptor@@6B@; const CTSSecurityDescriptor::`vftable'
0x1800199a5  mov     [rax], rcx
0x1800199a8  mov     [rax+8], rdi
0x1800199ac  mov     [rax+10h], rdi
0x1800199b0  mov     [r14+4620h], rdi
0x1800199b7  mov     [r14+4830h], rdi
0x1800199be  call    cs:__imp_GetProcessHeap
0x1800199c5  nop     dword ptr [rax+rax+00h]
0x1800199ca  mov     [r14+4838h], rdi
0x1800199d1  mov     [r14+4840h], rdi
0x1800199d8  mov     [r14+4848h], rdi
0x1800199df  mov     [r14+4850h], rax
0x1800199e6  mov     [r14+48B8h], edi
0x1800199ed  mov     word ptr [r14+48C0h], 0FFFFh
0x1800199f7  mov     [r14+48C8h], rdi
0x1800199fe  lea     rax, [r14+48D0h]
0x180019a05  lea     rcx, ??_7CRDPCallback@CConnectionEx@@6BIWRdsProtocolConnectionCallback@@@; const CConnectionEx::CRDPCallback::`vftable'{for `IWRdsProtocolConnectionCallback'}
0x180019a0c  mov     [rax], rcx
0x180019a0f  lea     rcx, ??_7CRDPCallback@CConnectionEx@@6BIWRdsProtocolShadowCallback@@@; const CConnectionEx::CRDPCallback::`vftable'{for `IWRdsProtocolShadowCallback'}
0x180019a16  mov     [rax+8], rcx
0x180019a1a  lea     rcx, ??_7CRDPCallback@CConnectionEx@@6BIWRdsProtocolConnectionSettings@@@; const CConnectionEx::CRDPCallback::`vftable'{for `IWRdsProtocolConnectionSettings'}
0x180019a21  mov     [rax+10h], rcx
0x180019a25  lea     rcx, ??_7CRDPCallback@CConnectionEx@@6BIWTSConnectionCallbackPrivate@@@; const CConnectionEx::CRDPCallback::`vftable'{for `IWTSConnectionCallbackPrivate'}
0x180019a2c  mov     [rax+18h], rcx
0x180019a30  mov     [rax+20h], r14
0x180019a34  mov     [rbp+37h+var_60], rdi
0x180019a38  xorps   xmm0, xmm0
0x180019a3b  movups  [rbp+37h+var_48], xmm0
0x180019a3f  mov     eax, cs:dword_18012E170
0x180019a45  lea     rsi, aCconnectionexC_12; "CConnectionEx::CConnectionEx"
0x180019a4c  lea     rcx, aConnectionStar; "Connection Start"
0x180019a53  cmp     eax, 4
0x180019a56  jbe     short loc_180019A92
0x180019a58  lea     rax, aInitializingCc; "Initializing CConnectionEx object for n"...
0x180019a5f  mov     [rbp+37h+var_A0], rax
0x180019a63  mov     [rbp+37h+var_78], rsi
0x180019a67  mov     [rbp+37h+var_90], rcx
0x180019a6b  lea     rax, [rbp+37h+var_A0]
0x180019a6f  mov     [rsp+0F0h+var_C0], rax
0x180019a74  lea     rax, [rbp+37h+var_78]
0x180019a78  mov     [rsp+0F0h+var_C8], rax
0x180019a7d  lea     rax, [rbp+37h+var_90]
0x180019a81  mov     [rsp+0F0h+var_D0], rax
0x180019a86  lea     rdx, word_180115952
0x180019a8d  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180019a92  mov     [rbp+37h+var_A0], rdi
0x180019a96  lea     rcx, [rbp+37h+var_A0]; struct IRemoteConnectionManager **
0x180019a9a  call    ?GetInstanceOfRemoteConnectionManager@@YAJPEAPEAVIRemoteConnectionManager@@@Z; GetInstanceOfRemoteConnectionManager(IRemoteConnectionManager * *)
0x180019a9f  mov     rcx, [rbp+37h+var_A0]
0x180019aa3  mov     rax, [rcx]
0x180019aa6  mov     rax, [rax+120h]
0x180019aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ab2  mov     [r14+48C8h], rax
0x180019ab9  lea     rcx, [rbp+37h+var_A0]; void *
0x180019abd  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180019ac2  cmp     dword ptr [r15], 1
0x180019ac6  jz      short loc_180019AE6
0x180019ac8  mov     r8d, [r15]
0x180019acb  lea     rdx, aWrdsConnection; "WRDS_CONNECTION_SETTINGS level passed t"...
0x180019ad2  mov     ebx, 80070519h
0x180019ad7  mov     ecx, 8; int
0x180019adc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180019ae1  jmp     loc_18001A1B1
0x180019ae6  mov     r8d, [r15+0E80h]
0x180019aed  cmp     r8d, 1
0x180019af1  jz      short loc_180019AFC
0x180019af3  lea     rdx, aWrdsListenerSe; "WRDS_LISTENER_SETTINGS level passed to "...
0x180019afa  jmp     short loc_180019AD2
0x180019afc  lea     rcx, [r14+704h]; void *
0x180019b03  xor     edx, edx; Val
0x180019b05  mov     r8d, 28E8h; Size
0x180019b0b  call    memset_0
0x180019b10  lea     rcx, [r14+6A0h]; unsigned __int16 *
0x180019b17  mov     r8, [rbp+37h+var_88]; unsigned __int16 *
0x180019b1b  mov     edx, 20h ; ' '; unsigned __int64
0x180019b20  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180019b25  mov     ebx, eax
0x180019b27  test    eax, eax
0x180019b29  jns     short loc_180019B55
0x180019b2b  mov     eax, cs:dword_18012E170
0x180019b31  cmp     eax, 3
0x180019b34  jbe     loc_18001A1B1
0x180019b3a  lea     rax, aCconnectionex; "CConnectionEx"
0x180019b41  mov     [rbp+37h+var_88], rax
0x180019b45  lea     rax, aStringcchcopy; "StringCchCopy"
0x180019b4c  lea     rdx, byte_180115913
0x180019b53  jmp     short loc_180019BA6
0x180019b55  xor     r9d, r9d; lpName
0x180019b58  xor     r8d, r8d; bInitialState
0x180019b5b  lea     edx, [r9+1]; bManualReset
0x180019b5f  xor     ecx, ecx; lpEventAttributes
0x180019b61  call    cs:__imp_CreateEventW
0x180019b68  nop     dword ptr [rax+rax+00h]
0x180019b6d  mov     [r14+45D0h], rax
0x180019b74  test    rax, rax
0x180019b77  jnz     short loc_180019BE6
0x180019b79  mov     ebx, 8007000Eh
0x180019b7e  mov     eax, cs:dword_18012E170
0x180019b84  cmp     eax, 3
0x180019b87  jbe     loc_18001A1B1
0x180019b8d  lea     rax, aCconnectionex; "CConnectionEx"
0x180019b94  mov     [rbp+37h+var_88], rax
0x180019b98  lea     rax, aCreateeventOnr; "CreateEvent OnReady"
0x180019b9f  lea     rdx, dword_1801158D4
0x180019ba6  mov     [rbp+37h+var_90], rax
0x180019baa  lea     rax, aWarningHresult; "Warning HResult failed"
0x180019bb1  mov     [rbp+37h+var_78], rax
0x180019bb5  lea     rax, [rbp+37h+var_88]
0x180019bb9  mov     [rsp+0F0h+var_B8], rax
0x180019bbe  lea     rax, [rbp+37h+var_A0]
0x180019bc2  mov     [rsp+0F0h+var_C0], rax
0x180019bc7  lea     rax, [rbp+37h+var_90]
0x180019bcb  mov     [rsp+0F0h+var_C8], rax
0x180019bd0  lea     rax, [rbp+37h+var_78]
0x180019bd4  mov     [rsp+0F0h+var_D0], rax
0x180019bd9  mov     dword ptr [rbp+37h+var_A0], ebx
0x180019bdc  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180019be1  jmp     loc_18001A1B1
0x180019be6  mov     rbx, [r14+638h]
0x180019bed  mov     rcx, [rbp+37h+arg_28]
0x180019bf1  mov     [r14+638h], rcx
0x180019bf8  test    rcx, rcx
0x180019bfb  jz      short loc_180019C09
0x180019bfd  mov     rax, [rcx]
0x180019c00  mov     rax, [rax+8]
0x180019c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c09  test    rbx, rbx
0x180019c0c  jz      short loc_180019C1D
0x180019c0e  mov     rax, [rbx]
0x180019c11  mov     rcx, rbx
0x180019c14  mov     rax, [rax+10h]
0x180019c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c1d  mov     rcx, [r14+638h]
0x180019c24  mov     rax, [rcx]
0x180019c27  lea     rsi, [r14+648h]
0x180019c2e  mov     r8, rsi
0x180019c31  lea     rdx, IID_IWRdsConnectionRdp
0x180019c38  mov     rax, [rax]
0x180019c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c40  test    eax, eax
0x180019c42  jns     short loc_180019C4C
0x180019c44  mov     rcx, rsi
0x180019c47  call    ??4?$SmartPtr@VITSRpcClientTrackerMgr@@@@QEAAAEAV0@PEAVITSRpcClientTrackerMgr@@@Z; SmartPtr<ITSRpcClientTrackerMgr>::operator=(ITSRpcClientTrackerMgr *)
0x180019c4c  mov     rcx, [r14+638h]
0x180019c53  mov     rax, [rcx]
0x180019c56  lea     rbx, [r14+650h]
0x180019c5d  mov     r8, rbx
0x180019c60  lea     rdx, IID_IWTSConnectionPrivate
0x180019c67  mov     rax, [rax]
0x180019c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c6f  test    eax, eax
0x180019c71  jns     short loc_180019C7B
0x180019c73  mov     rcx, rbx
0x180019c76  call    ??4?$SmartPtr@VITSRpcClientTrackerMgr@@@@QEAAAEAV0@PEAVITSRpcClientTrackerMgr@@@Z; SmartPtr<ITSRpcClientTrackerMgr>::operator=(ITSRpcClientTrackerMgr *)
0x180019c7b  mov     rcx, [r14+638h]
0x180019c82  mov     rax, [rcx]
0x180019c85  mov     r8, r12
0x180019c88  lea     rdx, IID_IWRdsWddmIddProps
0x180019c8f  mov     rax, [rax]
0x180019c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c97  test    eax, eax
0x180019c99  jns     short loc_180019CB4
0x180019c9b  mov     rcx, [r12]
0x180019c9f  mov     [r12], rdi
0x180019ca3  test    rcx, rcx
0x180019ca6  jz      short loc_180019CB4
0x180019ca8  mov     rax, [rcx]
0x180019cab  mov     rax, [rax+10h]
0x180019caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cb4  mov     rcx, [r14+638h]
0x180019cbb  mov     rax, [rcx]
0x180019cbe  mov     r8, r13
0x180019cc1  lea     rdx, IID_IWRdsWddmIddProps1
0x180019cc8  mov     rax, [rax]
0x180019ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cd0  test    eax, eax
0x180019cd2  jns     short loc_180019CED
0x180019cd4  mov     rcx, [r13+0]
0x180019cd8  mov     [r13+0], rdi
0x180019cdc  test    rcx, rcx
0x180019cdf  jz      short loc_180019CED
0x180019ce1  mov     rax, [rcx]
0x180019ce4  mov     rax, [rax+10h]
0x180019ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ced  mov     rcx, [r14+638h]
0x180019cf4  mov     rax, [rcx]
0x180019cf7  lea     rbx, [r14+668h]
0x180019cfe  mov     r8, rbx
0x180019d01  lea     rdx, IID_IWRdsEnhancedFastReconnectArbitrator
0x180019d08  mov     rax, [rax]
0x180019d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d10  test    eax, eax
0x180019d12  jns     short loc_180019D2B
0x180019d14  mov     rcx, [rbx]
0x180019d17  mov     [rbx], rdi
0x180019d1a  test    rcx, rcx
0x180019d1d  jz      short loc_180019D2B
0x180019d1f  mov     rax, [rcx]
0x180019d22  mov     rax, [rax+10h]
0x180019d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d2b  xorps   xmm0, xmm0
0x180019d2e  movq    rax, xmm0
0x180019d33  cmp     rax, [r15+0E98h]
0x180019d3a  jnz     loc_180019E25
0x180019d40  psrldq  xmm0, 8
0x180019d45  movq    rax, xmm0
0x180019d4a  cmp     rax, [r15+0EA0h]
0x180019d51  jnz     loc_180019E25
0x180019d57  lea     rdx, aPwrdsconnectio; "pWRdsConnectionSettings->WRdsConnection"...
0x180019d5e  mov     ecx, 4; int
0x180019d63  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180019d68  lea     rdi, [r14+4600h]
0x180019d6f  mov     edx, 0F4400000h; unsigned int
0x180019d74  mov     rcx, rdi; pguid
0x180019d77  call    ?GenerateConstrainedGuid@@YAJPEAU_GUID@@K@Z; GenerateConstrainedGuid(_GUID *,ulong)
0x180019d7c  mov     ebx, eax
0x180019d7e  test    eax, eax
0x180019d80  mov     eax, cs:dword_18012E170
0x180019d86  jns     short loc_180019DEA
0x180019d88  cmp     eax, 3
0x180019d8b  jbe     loc_18001A1AA
0x180019d91  lea     rax, aCconnectionex; "CConnectionEx"
0x180019d98  mov     [rbp+37h+var_88], rax
0x180019d9c  mov     dword ptr [rbp+37h+var_A0], ebx
0x180019d9f  lea     rax, aGenerateconstr_0; "GenerateConstrainedGuid"
0x180019da6  mov     [rbp+37h+var_90], rax
0x180019daa  lea     rax, aWarningHresult; "Warning HResult failed"
0x180019db1  mov     [rbp+37h+var_78], rax
0x180019db5  lea     rax, [rbp+37h+var_88]
0x180019db9  mov     [rsp+0F0h+var_B8], rax
0x180019dbe  lea     rax, [rbp+37h+var_A0]
0x180019dc2  mov     [rsp+0F0h+var_C0], rax
0x180019dc7  lea     rax, [rbp+37h+var_90]
  ... truncated ...
```
