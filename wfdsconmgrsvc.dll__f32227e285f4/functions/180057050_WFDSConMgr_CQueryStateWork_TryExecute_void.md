# WFDSConMgr::CQueryStateWork::TryExecute(void)

- ea: `0x180057050`
- end: `0x180057b41`
- name: `?TryExecute@CQueryStateWork@WFDSConMgr@@MEAAXXZ`
- size: `2801`
- prototype: `void __fastcall(WFDSConMgr::CQueryStateWork *__hidden this)`
- caller_count: `0`
- callee_count: `41`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002600`
- `0x18000475c`
- `0x180004c7c`
- `0x180004ca8`
- `0x1800059c0`
- `0x180006740`
- `0x180006e6c`
- `0x18000f1ac`
- `0x18000f22c`
- `0x18001a21c`
- `0x18001d18c`
- `0x180024b88`
- `0x180024de8`
- `0x180025708`
- `0x180025fb4`
- `0x180026884`
- `0x180026d20`
- `0x18002c3dc`
- `0x18002f560`
- `0x1800391b8`
- `0x180039ec4`
- `0x180039f10`
- `0x18003a14c`
- `0x18003a684`
- `0x18003aaf0`
- `0x18003b09c`
- `0x18003b19c`
- `0x18003c264`
- `0x18003c310`
- `0x18003f044`
- `0x180047270`
- `0x180047b70`
- `0x180053eec`
- `0x180054164`
- `0x1800545dc`
- `0x180054688`
- `0x1800546c4`
- `0x180057050`
- `0x18005c888`
- `0x18005f9a0`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005782f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005782f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005722a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800579a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005722a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800579a4`

## string_xrefs

- `0x180057632`: `Attempted to pair with headless client, unable to continue`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall WFDSConMgr::CQueryStateWork::TryExecute(WFDSConMgr::CQueryStateWork *this)
{
  WFDSConMgr::CQueryStateWork *v1; // r14
  _QWORD *v2; // rcx
  _DWORD *v3; // rdx
  __int64 v4; // rbx
  struct WFDSConMgr::IConnectManagerFactory *v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rbx
  struct WFDSConMgr::IConnectManagerFactory *ConnectManagerFactory; // rax
  __int64 v10; // rax
  WFDSConMgr::CDevQueryHelper **v11; // r12
  WFDSConMgr::CRemoteDevice *v12; // rcx
  struct WFDSConMgr::IConfigHelper *ConfigHelper; // rax
  int v14; // r13d
  struct WFDSConMgr::CMiracastHelper *MiracastHelper; // rsi
  __int64 v16; // rdi
  _QWORD *v17; // rbx
  struct WFDSConMgr::IConfigHelper *v18; // rax
  int v19; // r8d
  unsigned __int8 v20; // bl
  int v21; // edx
  __int64 v22; // rax
  char v23; // di
  unsigned int v24; // eax
  int v25; // r8d
  int v26; // r10d
  int v27; // r8d
  __int64 v28; // rcx
  char v29; // al
  _BYTE *v30; // rdx
  struct WFDSConMgr::CSessionStateMachine *StateMachine; // rsi
  __int64 v32; // rbx
  bool v33; // zf
  char v34; // bl
  unsigned __int8 v35; // r8
  struct WFDSConMgr::IConfigHelper *v36; // rax
  __int64 v37; // rbx
  struct WFDSConMgr::IConnectManagerFactory *v38; // rax
  __int64 v39; // rax
  __int64 v40; // r9
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  void *v44; // [rsp+28h] [rbp-2C0h]
  bool v45; // [rsp+80h] [rbp-268h] BYREF
  unsigned __int8 v46; // [rsp+81h] [rbp-267h]
  unsigned __int8 v47; // [rsp+82h] [rbp-266h] BYREF
  unsigned __int8 v48; // [rsp+83h] [rbp-265h] BYREF
  bool v49; // [rsp+84h] [rbp-264h] BYREF
  char v50; // [rsp+85h] [rbp-263h] BYREF
  char v51; // [rsp+86h] [rbp-262h] BYREF
  char v52; // [rsp+87h] [rbp-261h] BYREF
  _BYTE v53[8]; // [rsp+88h] [rbp-260h] BYREF
  __int64 v54; // [rsp+90h] [rbp-258h] BYREF
  LPCRITICAL_SECTION v55; // [rsp+98h] [rbp-250h] BYREF
  WFDSConMgr::CQueryStateWork *v56; // [rsp+A0h] [rbp-248h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+A8h] [rbp-240h] BYREF
  int v58; // [rsp+B0h] [rbp-238h] BYREF
  __int64 v59; // [rsp+B8h] [rbp-230h] BYREF
  std::_Ref_count_base *v60; // [rsp+C0h] [rbp-228h]
  PSRWLOCK SRWLock; // [rsp+C8h] [rbp-220h] BYREF
  std::_Ref_count_base *v62; // [rsp+D0h] [rbp-218h]
  int v63; // [rsp+D8h] [rbp-210h] BYREF
  int v64; // [rsp+DCh] [rbp-20Ch] BYREF
  _QWORD v65[3]; // [rsp+E0h] [rbp-208h] BYREF
  __int16 v66; // [rsp+F8h] [rbp-1F0h]
  char v67; // [rsp+FAh] [rbp-1EEh]
  int v68; // [rsp+FBh] [rbp-1EDh]
  char v69; // [rsp+FFh] [rbp-1E9h]
  _BYTE v70[8]; // [rsp+100h] [rbp-1E8h] BYREF
  std::_Ref_count_base *v71; // [rsp+108h] [rbp-1E0h]
  __int16 v72; // [rsp+118h] [rbp-1D0h]
  char v73; // [rsp+11Ah] [rbp-1CEh]
  _QWORD v74[3]; // [rsp+128h] [rbp-1C0h] BYREF
  _QWORD v75[3]; // [rsp+140h] [rbp-1A8h] BYREF
  const std::exception *v76; // [rsp+158h] [rbp-190h] BYREF
  const WFDSConMgr::CException *v77; // [rsp+160h] [rbp-188h] BYREF
  _BYTE v78[16]; // [rsp+168h] [rbp-180h] BYREF
  _OWORD v79[2]; // [rsp+178h] [rbp-170h] BYREF
  struct _GUID v80; // [rsp+198h] [rbp-150h] BYREF
  _BYTE v81[32]; // [rsp+1A8h] [rbp-140h] BYREF
  _BYTE v82[32]; // [rsp+1C8h] [rbp-120h] BYREF
  _BYTE v83[32]; // [rsp+1E8h] [rbp-100h] BYREF
  _BYTE v84[32]; // [rsp+208h] [rbp-E0h] BYREF
  _BYTE v85[40]; // [rsp+228h] [rbp-C0h] BYREF
  _BYTE v86[96]; // [rsp+250h] [rbp-98h] BYREF

  v1 = this;
  v56 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_5715219f333a32af0405bc0f43c43705_Traceguids, this);
  }
  v2 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v55, (__int64)v1);
  WFDSConMgr::TryCatchTelemetry__lambda_60eb66934bdbd716f57d09050600bc53___(v2);
  WFDSConMgr::CriticalSection::Lock((char *)v1 + 64, &lpCriticalSection);
  if ( *((_BYTE *)v1 + 104) )
    WFDSConMgr::CException::Throw(
      199,
      "WFDSConMgr::CQueryStateWork::TryExecute",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionwork.cpp",
      195,
      L"Query operation was canceled before starting",
      v1);
  v3 = (_DWORD *)*((_QWORD *)v1 + 4);
  if ( v3[28] == 1 )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v3 + 32LL))(*((_QWORD *)v1 + 4));
    ConnectManagerFactory = WFDSConMgr::CRemoteDevice::GetConnectManagerFactory(*((WFDSConMgr::CRemoteDevice **)v1 + 4));
    v10 = (*(__int64 (__fastcall **)(struct WFDSConMgr::IConnectManagerFactory *, __int64 *))(*(_QWORD *)ConnectManagerFactory
                                                                                            + 24LL))(
            ConnectManagerFactory,
            &v59);
    v7 = WFDSConMgr::CWfdDevQueryHelper::Create(&SRWLock, v10, v8);
  }
  else
  {
    if ( v3[28] != 2 )
      WFDSConMgr::CException::Throw(
        159,
        "WFDSConMgr::CQueryStateWork::TryExecute",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionwork.cpp",
        209,
        L"Device has invalid DAF provider type",
        v1);
    v4 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v3 + 32LL))(*((_QWORD *)v1 + 4));
    v5 = WFDSConMgr::CRemoteDevice::GetConnectManagerFactory(*((WFDSConMgr::CRemoteDevice **)v1 + 4));
    v6 = (*(__int64 (__fastcall **)(struct WFDSConMgr::IConnectManagerFactory *, __int64 *))(*(_QWORD *)v5 + 24LL))(
           v5,
           &v59);
    v7 = WFDSConMgr::CInfraDevQueryHelper::Create(&SRWLock, v6, v4, 0);
  }
  v11 = (WFDSConMgr::CDevQueryHelper **)((char *)v1 + 48);
  std::shared_ptr<WFDSConMgr::CDevQueryHelper>::operator=((char *)v1 + 48, v7);
  if ( v62 )
    std::_Ref_count_base::_Decref(v62);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  WFDSConMgr::CDevQueryHelper::DoQuery(*v11, 0, 1, 0x2710u);
  v45 = 0;
  v51 = 0;
  v80 = 0;
  std::wstring::wstring((__int64)v82);
  std::wstring::wstring((__int64)v85);
  std::wstring::wstring((__int64)v84);
  std::wstring::wstring((__int64)v83);
  v64 = 0;
  v63 = 0;
  std::vector<std::unique_ptr<WFDSConMgr::ISessionWork>>::vector<std::unique_ptr<WFDSConMgr::ISessionWork>>(v75);
  std::vector<std::unique_ptr<WFDSConMgr::ISessionWork>>::vector<std::unique_ptr<WFDSConMgr::ISessionWork>>(v74);
  LODWORD(lpCriticalSection) = 0;
  v50 = 0;
  v12 = (WFDSConMgr::CRemoteDevice *)*((_QWORD *)v1 + 4);
  v46 = *((_DWORD *)v12 + 28) == 2;
  v47 = 0;
  v48 = 1;
  ConfigHelper = WFDSConMgr::CRemoteDevice::GetConfigHelper(v12);
  (*(void (__fastcall **)(struct WFDSConMgr::IConfigHelper *, unsigned __int8 *))(*(_QWORD *)ConfigHelper + 32LL))(
    ConfigHelper,
    &v48);
  std::wstring::wstring((__int64)v81);
  std::vector<std::unique_ptr<WFDSConMgr::ISessionWork>>::vector<std::unique_ptr<WFDSConMgr::ISessionWork>>(v65);
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v54 = 0;
  v49 = 0;
  memset(v79, 0, 28);
  v58 = 0;
  if ( *(_DWORD *)(*((_QWORD *)v1 + 4) + 112LL) != 1 )
  {
    if ( *(_DWORD *)(*((_QWORD *)v1 + 4) + 112LL) == 2 )
    {
      WFDSConMgr::CDevQueryHelper::GetPropertiesForInfraDevice(*v11, &v45, &v80);
      v14 = 1;
      LODWORD(lpCriticalSection) = 1;
      goto LABEL_22;
    }
LABEL_20:
    WFDSConMgr::CException::Throw(
      176,
      "WFDSConMgr::CQueryStateWork::TryExecute",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionwork.cpp",
      27,
      L"Device does not support any transports to connect",
      v1);
  }
  WFDSConMgr::CDevQueryHelper::GetPropertiesForWFDDevice(
    *v11,
    &v45,
    &v51,
    &v80,
    v75,
    v74,
    v82,
    &v50,
    &v47,
    v81,
    v65,
    &v54);
  v14 = WFDSConMgr::Common::ConvertStringListToTransportBitmask(v75);
  LODWORD(lpCriticalSection) = v14;
  WFDSConMgr::CDevQueryHelper::GetPropertiesForTelemetry(*v11, v85, v84, v83, v82, &v64, &v63);
  if ( !v14 )
    goto LABEL_20;
  v46 = v47;
LABEL_22:
  MiracastHelper = WFDSConMgr::CRemoteDevice::GetMiracastHelper(*((WFDSConMgr::CRemoteDevice **)v1 + 4));
  v16 = *(_QWORD *)WFDSConMgr::CClientHandleStore::GetWlanClientHandle(
                     *(_QWORD *)(*((_QWORD *)v1 + 4) + 1104LL),
                     &SRWLock);
  v55 = (LPCRITICAL_SECTION)&v59;
  v17 = std::shared_ptr<WFDSConMgr::IConfigHelper>::shared_ptr<WFDSConMgr::IConfigHelper>(
          &v59,
          (_QWORD *)(*((_QWORD *)v1 + 4) + 1072LL));
  v18 = WFDSConMgr::CRemoteDevice::GetConfigHelper(*((WFDSConMgr::CRemoteDevice **)v1 + 4));
  v44 = v17;
  LOBYTE(v19) = v47;
  v20 = v46;
  LOBYTE(v21) = v46;
  v22 = WFDSConMgr::CalculateCurrentInfraState(
          (unsigned int)v70,
          v21,
          v19,
          (unsigned int)v65,
          (__int64)v18,
          (__int64)v44,
          v16,
          (__int64)MiracastHelper);
  v23 = *(_BYTE *)(v22 + 32);
  v79[0] = *(_OWORD *)(v22 + 4);
  *(_OWORD *)((char *)v79 + 12) = *(_OWORD *)(v22 + 16);
  v58 = *(_DWORD *)v22;
  if ( v62 )
    std::_Ref_count_base::_Decref(v62);
  if ( v48 )
  {
    if ( !v23 )
      goto LABEL_31;
  }
  else if ( !v23 )
  {
    WFDSConMgr::CException::Throw(
      176,
      "WFDSConMgr::CQueryStateWork::TryExecute",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionwork.cpp",
      41,
      L"Policy does not allow WFD, no other transport supported.",
      v1);
  }
  if ( HIBYTE(v66) && !WFDSConMgr::CRemoteDevice::CanHandleUserInputOutput(*((WFDSConMgr::CRemoteDevice **)v1 + 4)) )
  {
    *((_DWORD *)v1 + 28) = 6;
    WFDSConMgr::CException::Throw(
      50,
      "WFDSConMgr::CQueryStateWork::TryExecute",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionwork.cpp",
      47,
      L"Attempted to pair with headless client, unable to continue",
      v1);
  }
LABEL_31:
  v53[0] = BYTE1(v54);
  v55 = (LPCRITICAL_SECTION)v70;
  std::vector<std::wstring>::vector<std::wstring>(v70, v65);
  v72 = v66;
  v73 = v67;
  WFDSConMgr::CRemoteDevice::GetConfigHelper(*((WFDSConMgr::CRemoteDevice **)v1 + 4));
  v24 = (unsigned int)std::shared_ptr<WFDSConMgr::IConfigHelper>::shared_ptr<WFDSConMgr::IConfigHelper>(
                        &v59,
                        (_QWORD *)(*((_QWORD *)v1 + 4) + 1056LL));
  LOBYTE(v25) = v23;
  WFDSConMgr::CalculateCurrentMiracastRtspConnectionParams(v24, v26, v25, (unsigned int)v70, (__int64)&v54);
  v28 = *((_QWORD *)v1 + 4);
  if ( !v20 || (v29 = 1, *(_DWORD *)(v28 + 112) != 1) )
    v29 = 0;
  v30 = v81;
  LOBYTE(v27) = v51;
  LOBYTE(v30) = v45;
  WFDSConMgr::CRemoteDevice::OnDAFQueryComplete(
    v28,
    (_DWORD)v30,
    v27,
    (unsigned int)&v80,
    v14,
    (__int64)v74,
    (__int64)v82,
    (__int64)v85,
    (__int64)v84,
    (__int64)v83,
    v50,
    v29,
    (__int64)v81,
    (__int64)v65,
    (__int64)v79,
    (__int64)&v54);
  StateMachine = WFDSConMgr::CRemoteDevice::GetStateMachine(*((WFDSConMgr::CRemoteDevice **)v1 + 4));
  v46 = v48;
  v32 = *((_QWORD *)v1 + 4);
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,1>::LockSentry<WFDSConMgr::ReadersWriterLock,1>(
    (__int64)&SRWLock,
    (RTL_SRWLOCK *)(v32 + 48));
  if ( *(_DWORD *)(v32 + 112) != 1
    || !*(_BYTE *)(v32 + 216)
    || !*(_BYTE *)(v32 + 219)
    || !*(_QWORD *)(v32 + 432)
    || (v33 = (*(_BYTE *)(v32 + 412) & 2) == 0, v34 = 1, !v33) )
  {
    v34 = 0;
  }
  if ( (_BYTE)v62 && SRWLock )
    ReleaseSRWLockShared(SRWLock);
  if ( !v34 || (v35 = 1, !v23) )
    v35 = 0;
  WFDSConMgr::CSessionStateMachine::OnInitialQueryComplete(
    (__int64)StateMachine,
    *(_DWORD *)(*((_QWORD *)v1 + 4) + 112LL),
    v35,
    v46);
  v52 = 0;
  v36 = WFDSConMgr::CRemoteDevice::GetConfigHelper(*((WFDSConMgr::CRemoteDevice **)v1 + 4));
  (*(void (__fastcall **)(struct WFDSConMgr::IConfigHelper *, char *))(*(_QWORD *)v36 + 168LL))(v36, &v52);
  if ( v52 )
    WFDSConMgr::CRemoteDevice::InitUsername(*((WFDSConMgr::CRemoteDevice **)v1 + 4));
  if ( (*((_BYTE *)v1 + 108) & (unsigned __int8)v14 & 1) != 0 )
    WFDSConMgr::CRemoteDevice::TryAcquireMiracastResourceToken(*((WFDSConMgr::CRemoteDevice **)v1 + 4));
  if ( (*((_BYTE *)v1 + 108) & (unsigned __int8)v14 & 2) != 0 )
    WFDSConMgr::CRemoteDevice::TryAcquireMaUsbResourceToken(*((WFDSConMgr::CRemoteDevice **)v1 + 4));
  std::shared_ptr<WFDSConMgr::IConfigHelper>::shared_ptr<WFDSConMgr::IConfigHelper>(&v59, (_QWORD *)v1 + 6);
  if ( WFDSConMgr::CRemoteDevice::IsWfdDeviceInfra(*((WFDSConMgr::CRemoteDevice **)v1 + 4)) )
  {
    WFDSConMgr::CriticalSection::Lock((char *)v1 + 64, &v55);
    if ( *((_BYTE *)v1 + 104) )
      WFDSConMgr::CException::Throw(
        199,
        "WFDSConMgr::CQueryStateWork::TryExecute",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionwork.cpp",
        109,
        L"Query operation (2) was canceled before starting",
        v1);
    v37 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 4) + 40LL))(*((_QWORD *)v1 + 4));
    v38 = WFDSConMgr::CRemoteDevice::GetConnectManagerFactory(*((WFDSConMgr::CRemoteDevice **)v1 + 4));
    v39 = (*(__int64 (__fastcall **)(struct WFDSConMgr::IConnectManagerFactory *, _BYTE *))(*(_QWORD *)v38 + 24LL))(
            v38,
            v78);
    LOBYTE(v40) = 1;
    v41 = WFDSConMgr::CInfraDevQueryHelper::Create(v70, v39, v37, v40);
    std::shared_ptr<WFDSConMgr::CDevQueryHelper>::operator=((char *)v1 + 48, v41);
    if ( v71 )
      std::_Ref_count_base::_Decref(v71);
    if ( v55 )
      LeaveCriticalSection(v55);
    try
    {
      WFDSConMgr::CDevQueryHelper::DoQuery(*v11, 1, 1, 0);
      WFDSConMgr::CDevQueryHelper::GetPropertiesForInfraDevice(*v11, &v49, &v80);
      if ( v49 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 4) + 72LL))(*((_QWORD *)v1 + 4));
    }
    catch ( std::bad_alloc )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_5715219f333a32af0405bc0f43c43705_Traceguids, v56);
      }
      LODWORD(v1) = (_DWORD)v56;
    }
    catch ( const std::exception *v76 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v43 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v76 + 8LL))(v76);
        WPP_SF_qs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)&WPP_5715219f333a32af0405bc0f43c43705_Traceguids,
          (_DWORD)v56,
          v43);
      }
      LODWORD(v1) = (_DWORD)v56;
    }
    catch ( const WFDSConMgr::CException *v77 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          &WPP_5715219f333a32af0405bc0f43c43705_Traceguids,
          v56,
          *(_DWORD *)v77);
      }
      LODWORD(v1) = (_DWORD)v56;
    }
  }
  v42 = lambda_aea7821165466b944f70b16bfe2c608e_::_lambda_aea7821165466b944f70b16bfe2c608e_(
          (unsigned int)v86,
          (_DWORD)v1,
          (unsigned int)&v45,
          (unsigned int)&v58,
          (__int64)&v49,
          (__int64)&lpCriticalSection,
          (__int64)v81,
          (__int64)&v59,
          (__int64)v65,
          (__int64)&v54,
          (__int64)v53);
  WFDSConMgr::TryCatchTelemetry__lambda_aea7821165466b944f70b16bfe2c608e___(v42);
  lambda_aea7821165466b944f70b16bfe2c608e_::__lambda_aea7821165466b944f70b16bfe2c608e_(v86);
  if ( v60 )
    std::_Ref_count_base::_Decref(v60);
  std::vector<std::wstring>::_Tidy(v65);
  std::wstring::_Tidy_deallocate(v81);
  std::vector<std::wstring>::_Tidy(v74);
  std::vector<std::wstring>::_Tidy(v75);
  std::wstring::_Tidy_deallocate(v83);
  std::wstring::_Tidy_deallocate(v84);
  std::wstring::_Tidy_deallocate(v85);
  std::wstring::_Tidy_deallocate(v82);
}

```

## disassembly

```asm
0x180057050  mov     [rsp+arg_8], rbx
0x180057055  mov     [rsp+arg_10], rsi
0x18005705a  push    rdi
0x18005705b  push    r12
0x18005705d  push    r13
0x18005705f  push    r14
0x180057061  push    r15
0x180057063  sub     rsp, 2C0h
0x18005706a  mov     rax, cs:__security_cookie
0x180057071  xor     rax, rsp
0x180057074  mov     [rsp+2E8h+var_38], rax
0x18005707c  mov     r14, rcx
0x18005707f  mov     [rsp+2E8h+var_248], rcx
0x180057087  lea     rax, WPP_GLOBAL_Control
0x18005708e  mov     rcx, cs:WPP_GLOBAL_Control
0x180057095  cmp     rcx, rax
0x180057098  jz      short loc_1800570BE
0x18005709a  cmp     byte ptr [rcx+19h], 4
0x18005709e  jb      short loc_1800570BE
0x1800570a0  test    byte ptr [rcx+1Ch], 1
0x1800570a4  jz      short loc_1800570BE
0x1800570a6  mov     edx, 0Dh
0x1800570ab  mov     r9, r14
0x1800570ae  lea     r8, WPP_5715219f333a32af0405bc0f43c43705_Traceguids
0x1800570b5  mov     rcx, [rcx+10h]
0x1800570b9  call    WPP_SF_q
0x1800570be  mov     rdx, r14
0x1800570c1  lea     rcx, [rsp+2E8h+var_250]
0x1800570c9  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800570ce  mov     rcx, rax
0x1800570d1  call    WFDSConMgr__TryCatchTelemetry__lambda_60eb66934bdbd716f57d09050600bc53___
0x1800570d6  lea     rcx, [r14+40h]
0x1800570da  lea     rdx, [rsp+2E8h+lpCriticalSection]
0x1800570e2  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x1800570e7  nop
0x1800570e8  xor     r15d, r15d
0x1800570eb  cmp     [r14+68h], r15b
0x1800570ef  jz      short loc_180057121
0x1800570f1  mov     [rsp+2E8h+var_2C0], r14; void *
0x1800570f6  lea     rax, aQueryOperation_0; "Query operation was canceled before sta"...
0x1800570fd  mov     [rsp+2E8h+var_2C8], rax; unsigned __int16 *
0x180057102  mov     r9d, 0C3h; char
0x180057108  lea     r8, aOnecoreuapNetW_25; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18005710f  lea     rdx, aWfdsconmgrCque; "WFDSConMgr::CQueryStateWork::TryExecute"
0x180057116  mov     ecx, 800704C7h; char
0x18005711b  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180057121  mov     rdx, [r14+20h]
0x180057125  mov     ecx, [rdx+70h]
0x180057128  sub     ecx, 1
0x18005712b  jz      loc_1800571B3
0x180057131  cmp     ecx, 1
0x180057134  jz      short loc_180057166
0x180057136  mov     [rsp+2E8h+var_2C0], r14; void *
0x18005713b  lea     rax, aDeviceHasInval; "Device has invalid DAF provider type"
0x180057142  mov     [rsp+2E8h+var_2C8], rax; unsigned __int16 *
0x180057147  mov     r9d, 0D1h; char
0x18005714d  lea     r8, aOnecoreuapNetW_25; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180057154  lea     rdx, aWfdsconmgrCque; "WFDSConMgr::CQueryStateWork::TryExecute"
0x18005715b  mov     ecx, 8007139Fh; char
0x180057160  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180057166  mov     rax, [rdx]
0x180057169  mov     rcx, rdx
0x18005716c  mov     rax, [rax+20h]
0x180057170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057175  mov     rbx, rax
0x180057178  mov     rcx, [r14+20h]; this
0x18005717c  call    ?GetConnectManagerFactory@CRemoteDevice@WFDSConMgr@@QEAAAEAVIConnectManagerFactory@2@XZ; WFDSConMgr::CRemoteDevice::GetConnectManagerFactory(void)
0x180057181  mov     r8, rax
0x180057184  mov     rcx, [rax]
0x180057187  mov     rax, [rcx+18h]
0x18005718b  lea     rdx, [rsp+2E8h+var_230]
0x180057193  mov     rcx, r8
0x180057196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005719b  xor     r9d, r9d
0x18005719e  mov     r8, rbx
0x1800571a1  mov     rdx, rax
0x1800571a4  lea     rcx, [rsp+2E8h+SRWLock]
0x1800571ac  call    ?Create@CInfraDevQueryHelper@WFDSConMgr@@SA?AV?$shared_ptr@VCDevQueryHelper@WFDSConMgr@@@std@@V?$shared_ptr@VCDevQueryShim@WFDSConMgr@@@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@_N@Z; WFDSConMgr::CInfraDevQueryHelper::Create(std::shared_ptr<WFDSConMgr::CDevQueryShim>,std::wstring const &,bool)
0x1800571b1  jmp     short loc_1800571FB
0x1800571b3  mov     rax, [rdx]
0x1800571b6  mov     rcx, rdx
0x1800571b9  mov     rax, [rax+20h]
0x1800571bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800571c2  mov     rbx, rax
0x1800571c5  mov     rcx, [r14+20h]; this
0x1800571c9  call    ?GetConnectManagerFactory@CRemoteDevice@WFDSConMgr@@QEAAAEAVIConnectManagerFactory@2@XZ; WFDSConMgr::CRemoteDevice::GetConnectManagerFactory(void)
0x1800571ce  mov     r8, rax
0x1800571d1  mov     rcx, [rax]
0x1800571d4  mov     rax, [rcx+18h]
0x1800571d8  lea     rdx, [rsp+2E8h+var_230]
0x1800571e0  mov     rcx, r8
0x1800571e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800571e8  mov     r8, rbx
0x1800571eb  mov     rdx, rax
0x1800571ee  lea     rcx, [rsp+2E8h+SRWLock]
0x1800571f6  call    ?Create@CWfdDevQueryHelper@WFDSConMgr@@SA?AV?$shared_ptr@VCDevQueryHelper@WFDSConMgr@@@std@@V?$shared_ptr@VCDevQueryShim@WFDSConMgr@@@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; WFDSConMgr::CWfdDevQueryHelper::Create(std::shared_ptr<WFDSConMgr::CDevQueryShim>,std::wstring const &)
0x1800571fb  lea     r12, [r14+30h]
0x1800571ff  mov     rdx, rax
0x180057202  mov     rcx, r12
0x180057205  call    ??4?$shared_ptr@VCDevQueryHelper@WFDSConMgr@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<WFDSConMgr::CDevQueryHelper>::operator=(std::shared_ptr<WFDSConMgr::CDevQueryHelper> &&)
0x18005720a  mov     rcx, [rsp+2E8h+var_218]; this
0x180057212  test    rcx, rcx
0x180057215  jz      short loc_18005721D
0x180057217  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005721c  nop
0x18005721d  mov     rcx, [rsp+2E8h+lpCriticalSection]; lpCriticalSection
0x180057225  test    rcx, rcx
0x180057228  jz      short loc_180057230
0x18005722a  call    cs:__imp_LeaveCriticalSection
0x180057230  mov     r9d, 2710h; unsigned int
0x180057236  mov     r8b, 1; bool
0x180057239  xor     edx, edx; bool
0x18005723b  mov     rcx, [r12]; this
0x18005723f  call    ?DoQuery@CDevQueryHelper@WFDSConMgr@@QEAA_N_N0K@Z; WFDSConMgr::CDevQueryHelper::DoQuery(bool,bool,ulong)
0x180057244  mov     [rsp+2E8h+var_268], r15b
0x18005724c  mov     [rsp+2E8h+var_262], r15b
0x180057254  xorps   xmm0, xmm0
0x180057257  movups  xmmword ptr [rsp+2E8h+var_150.Data1], xmm0
0x18005725f  lea     rcx, [rsp+2E8h+var_120]
0x180057267  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18005726c  nop
0x18005726d  lea     rcx, [rsp+2E8h+var_C0]
0x180057275  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18005727a  nop
0x18005727b  lea     rcx, [rsp+2E8h+var_E0]
0x180057283  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180057288  nop
0x180057289  lea     rcx, [rsp+2E8h+var_100]
0x180057291  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180057296  nop
0x180057297  mov     [rsp+2E8h+var_20C], r15d
0x18005729f  mov     [rsp+2E8h+var_210], r15d
0x1800572a7  lea     rcx, [rsp+2E8h+var_1A8]
0x1800572af  call    ??0?$vector@V?$unique_ptr@VISessionWork@WFDSConMgr@@U?$default_delete@VISessionWork@WFDSConMgr@@@std@@@std@@V?$allocator@V?$unique_ptr@VISessionWork@WFDSConMgr@@U?$default_delete@VISessionWork@WFDSConMgr@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<WFDSConMgr::ISessionWork>>::vector<std::unique_ptr<WFDSConMgr::ISessionWork>>(void)
0x1800572b4  nop
0x1800572b5  lea     rcx, [rsp+2E8h+var_1C0]
0x1800572bd  call    ??0?$vector@V?$unique_ptr@VISessionWork@WFDSConMgr@@U?$default_delete@VISessionWork@WFDSConMgr@@@std@@@std@@V?$allocator@V?$unique_ptr@VISessionWork@WFDSConMgr@@U?$default_delete@VISessionWork@WFDSConMgr@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<WFDSConMgr::ISessionWork>>::vector<std::unique_ptr<WFDSConMgr::ISessionWork>>(void)
0x1800572c2  nop
0x1800572c3  mov     dword ptr [rsp+2E8h+lpCriticalSection], r15d
0x1800572cb  mov     [rsp+2E8h+var_263], r15b
0x1800572d3  mov     rcx, [r14+20h]; this
0x1800572d7  cmp     dword ptr [rcx+70h], 2
0x1800572db  setz    [rsp+2E8h+var_267]
0x1800572e3  mov     [rsp+2E8h+var_266], r15b
0x1800572eb  mov     [rsp+2E8h+var_265], 1
0x1800572f3  call    ?GetConfigHelper@CRemoteDevice@WFDSConMgr@@QEAAAEAVIConfigHelper@2@XZ; WFDSConMgr::CRemoteDevice::GetConfigHelper(void)
0x1800572f8  mov     r8, rax
0x1800572fb  mov     rcx, [rax]
0x1800572fe  mov     rax, [rcx+20h]
0x180057302  lea     rdx, [rsp+2E8h+var_265]
0x18005730a  mov     rcx, r8
0x18005730d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057312  lea     rcx, [rsp+2E8h+var_140]
0x18005731a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18005731f  nop
0x180057320  lea     rcx, [rsp+2E8h+var_208]
0x180057328  call    ??0?$vector@V?$unique_ptr@VISessionWork@WFDSConMgr@@U?$default_delete@VISessionWork@WFDSConMgr@@@std@@@std@@V?$allocator@V?$unique_ptr@VISessionWork@WFDSConMgr@@U?$default_delete@VISessionWork@WFDSConMgr@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<WFDSConMgr::ISessionWork>>::vector<std::unique_ptr<WFDSConMgr::ISessionWork>>(void)
0x18005732d  mov     [rsp+2E8h+var_1F0], r15w
0x180057336  mov     [rsp+2E8h+var_1EE], r15b
0x18005733e  xor     eax, eax
0x180057340  mov     [rsp+2E8h+var_1ED], eax
0x180057347  mov     [rsp+2E8h+var_1E9], al
0x18005734e  mov     [rsp+2E8h+var_258], r15
0x180057356  mov     [rsp+2E8h+var_264], r15b
0x18005735e  mov     qword ptr [rsp+2E8h+var_170], r15
0x180057366  mov     [rsp+2E8h+var_170+8], r15b
0x18005736e  mov     word ptr [rsp+2E8h+var_170+9], ax
0x180057376  mov     [rsp+2E8h+var_170+0Bh], al
0x18005737d  xorps   xmm0, xmm0
0x180057380  movups  xmmword ptr [rsp+2E8h+var_170+0Ch], xmm0
0x180057388  mov     [rsp+2E8h+var_238], r15d
0x180057390  mov     rcx, [r14+20h]
0x180057394  mov     edx, [rcx+70h]
0x180057397  sub     edx, 1
0x18005739a  jz      short loc_1800573D1
0x18005739c  cmp     edx, 1
0x18005739f  jnz     loc_1800574BE
0x1800573a5  lea     r8, [rsp+2E8h+var_150]; struct _GUID *
0x1800573ad  lea     rdx, [rsp+2E8h+var_268]; bool *
0x1800573b5  mov     rcx, [r12]; this
0x1800573b9  call    ?GetPropertiesForInfraDevice@CDevQueryHelper@WFDSConMgr@@QEBAXAEA_NAEAU_GUID@@@Z; WFDSConMgr::CDevQueryHelper::GetPropertiesForInfraDevice(bool &,_GUID &)
0x1800573be  mov     r13d, 1
0x1800573c4  mov     dword ptr [rsp+2E8h+lpCriticalSection], r13d
0x1800573cc  jmp     loc_1800574FC
0x1800573d1  lea     rax, [rsp+2E8h+var_258]
0x1800573d9  mov     [rsp+2E8h+var_290], rax
0x1800573de  lea     rax, [rsp+2E8h+var_208]
0x1800573e6  mov     [rsp+2E8h+var_298], rax
0x1800573eb  lea     rax, [rsp+2E8h+var_140]
0x1800573f3  mov     [rsp+2E8h+var_2A0], rax
0x1800573f8  lea     rax, [rsp+2E8h+var_266]
0x180057400  mov     [rsp+2E8h+var_2A8], rax
0x180057405  lea     rax, [rsp+2E8h+var_263]
0x18005740d  mov     [rsp+2E8h+var_2B0], rax
0x180057412  lea     rax, [rsp+2E8h+var_120]
0x18005741a  mov     [rsp+2E8h+var_2B8], rax
0x18005741f  lea     rax, [rsp+2E8h+var_1C0]
0x180057427  mov     [rsp+2E8h+var_2C0], rax
0x18005742c  lea     rax, [rsp+2E8h+var_1A8]
0x180057434  mov     [rsp+2E8h+var_2C8], rax
0x180057439  lea     r9, [rsp+2E8h+var_150]
0x180057441  lea     r8, [rsp+2E8h+var_262]
0x180057449  lea     rdx, [rsp+2E8h+var_268]
0x180057451  mov     rcx, [r12]
0x180057455  call    ?GetPropertiesForWFDDevice@CDevQueryHelper@WFDSConMgr@@QEBAXAEA_N0AEAU_GUID@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@2AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@003AEAUInfraBackchannelParameters@2@AEAURtspConnectionParameters@2@@Z; WFDSConMgr::CDevQueryHelper::GetPropertiesForWFDDevice(bool &,bool &,_GUID &,std::vector<std::wstring> &,std::vector<std::wstring> &,std::wstring &,bool &,bool &,std::wstring &,WFDSConMgr::InfraBackchannelParameters &,WFDSConMgr::RtspConnectionParameters &)
0x18005745a  lea     rcx, [rsp+2E8h+var_1A8]
0x180057462  call    ?ConvertStringListToTransportBitmask@Common@WFDSConMgr@@YA?AW4_WFDSConMgrTransport@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; WFDSConMgr::Common::ConvertStringListToTransportBitmask(std::vector<std::wstring> const &)
0x180057467  mov     r13d, eax
0x18005746a  mov     dword ptr [rsp+2E8h+lpCriticalSection], eax
0x180057471  lea     rax, [rsp+2E8h+var_210]
0x180057479  mov     [rsp+2E8h+var_2B8], rax
0x18005747e  lea     rax, [rsp+2E8h+var_20C]
0x180057486  mov     [rsp+2E8h+var_2C0], rax
0x18005748b  lea     rax, [rsp+2E8h+var_120]
0x180057493  mov     [rsp+2E8h+var_2C8], rax
0x180057498  lea     r9, [rsp+2E8h+var_100]
0x1800574a0  lea     r8, [rsp+2E8h+var_E0]
0x1800574a8  lea     rdx, [rsp+2E8h+var_C0]
0x1800574b0  mov     rcx, [r12]
0x1800574b4  call    ?GetPropertiesForTelemetry@CDevQueryHelper@WFDSConMgr@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000AEAHAEAI@Z; WFDSConMgr::CDevQueryHelper::GetPropertiesForTelemetry(std::wstring &,std::wstring &,std::wstring &,std::wstring &,int &,uint &)
0x1800574b9  test    r13d, r13d
0x1800574bc  jnz     short loc_1800574EE
0x1800574be  mov     [rsp+2E8h+var_2C0], r14; void *
0x1800574c3  lea     rax, aDeviceDoesNotS; "Device does not support any transports "...
0x1800574ca  mov     [rsp+2E8h+var_2C8], rax; unsigned __int16 *
0x1800574cf  mov     r9d, 11Bh; char
0x1800574d5  lea     r8, aOnecoreuapNetW_25; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x1800574dc  lea     rdx, aWfdsconmgrCque; "WFDSConMgr::CQueryStateWork::TryExecute"
0x1800574e3  mov     ecx, 800704B0h; char
0x1800574e8  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800574ee  mov     al, [rsp+2E8h+var_266]
0x1800574f5  mov     [rsp+2E8h+var_267], al
0x1800574fc  mov     rcx, [r14+20h]; this
0x180057500  call    ?GetMiracastHelper@CRemoteDevice@WFDSConMgr@@QEAAAEAVCMiracastHelper@2@XZ; WFDSConMgr::CRemoteDevice::GetMiracastHelper(void)
0x180057505  mov     rsi, rax
0x180057508  mov     rcx, [r14+20h]
0x18005750c  lea     rdx, [rsp+2E8h+SRWLock]
0x180057514  mov     rcx, [rcx+450h]
0x18005751b  call    ?GetWlanClientHandle@CClientHandleStore@WFDSConMgr@@QEBA?AV?$shared_ptr@X@std@@XZ; WFDSConMgr::CClientHandleStore::GetWlanClientHandle(void)
0x180057520  nop
0x180057521  mov     rdi, [rax]
0x180057524  lea     rax, [rsp+2E8h+var_230]
0x18005752c  mov     [rsp+2E8h+var_250], rax
0x180057534  mov     rdx, [r14+20h]
0x180057538  add     rdx, 430h
0x18005753f  lea     rcx, [rsp+2E8h+var_230]
0x180057547  call    ??0?$shared_ptr@VIConfigHelper@WFDSConMgr@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<WFDSConMgr::IConfigHelper>::shared_ptr<WFDSConMgr::IConfigHelper>(std::shared_ptr<WFDSConMgr::IConfigHelper> const &)
0x18005754c  mov     rbx, rax
0x18005754f  mov     rcx, [r14+20h]; this
0x180057553  call    ?GetConfigHelper@CRemoteDevice@WFDSConMgr@@QEAAAEAVIConfigHelper@2@XZ; WFDSConMgr::CRemoteDevice::GetConfigHelper(void)
0x180057558  nop
0x180057559  mov     [rsp+2E8h+var_2B0], rsi
0x18005755e  mov     [rsp+2E8h+var_2B8], rdi
0x180057563  mov     [rsp+2E8h+var_2C0], rbx
0x180057568  mov     [rsp+2E8h+var_2C8], rax
0x18005756d  lea     r9, [rsp+2E8h+var_208]
0x180057575  mov     r8b, [rsp+2E8h+var_266]
0x18005757d  mov     bl, [rsp+2E8h+var_267]
0x180057584  mov     dl, bl
0x180057586  lea     rcx, [rsp+2E8h+var_1E8]
0x18005758e  call    ?CalculateCurrentInfraState@WFDSConMgr@@YA?AV?$tuple@_NUConnectedInfraState@WFDSConMgr@@W4InfraStateFlags@Telemetry@2@@std@@_N0AEAUInfraBackchannelParameters@1@AEBVIConfigHelper@1@V?$shared_ptr@VCWlanApiShim@WFDSConMgr@@@3@PEAXAEAVCMiracastHelper@1@@Z; WFDSConMgr::CalculateCurrentInfraState(bool,bool,WFDSConMgr::InfraBackchannelParameters &,WFDSConMgr::IConfigHelper const &,std::shared_ptr<WFDSConMgr::CWlanApiShim>,void *,WFDSConMgr::CMiracastHelper &)
0x180057593  mov     dil, [rax+20h]
0x180057597  movups  xmm0, xmmword ptr [rax+4]
0x18005759b  movups  xmmword ptr [rsp+2E8h+var_170], xmm0
0x1800575a3  movups  xmm1, xmmword ptr [rax+10h]
0x1800575a7  movups  xmmword ptr [rsp+2E8h+var_170+0Ch], xmm1
0x1800575af  mov     eax, [rax]
0x1800575b1  mov     [rsp+2E8h+var_238], eax
0x1800575b8  mov     rcx, [rsp+2E8h+var_218]; this
0x1800575c0  test    rcx, rcx
0x1800575c3  jz      short loc_1800575CA
0x1800575c5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800575ca  cmp     [rsp+2E8h+var_265], r15b
0x1800575d2  jnz     short loc_180057609
0x1800575d4  test    dil, dil
0x1800575d7  jnz     short loc_18005760E
0x1800575d9  mov     [rsp+2E8h+var_2C0], r14; void *
0x1800575de  lea     rax, aPolicyDoesNotA; "Policy does not allow WFD, no other tra"...
0x1800575e5  mov     [rsp+2E8h+var_2C8], rax; unsigned __int16 *
0x1800575ea  mov     r9d, 129h; char
0x1800575f0  lea     r8, aOnecoreuapNetW_25; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x1800575f7  lea     rdx, aWfdsconmgrCque; "WFDSConMgr::CQueryStateWork::TryExecute"
0x1800575fe  mov     ecx, 800704B0h; char
0x180057603  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180057609  test    dil, dil
0x18005760c  jz      short loc_18005765D
0x18005760e  cmp     byte ptr [rsp+2E8h+var_1F0+1], r15b
0x180057616  jz      short loc_18005765D
0x180057618  mov     rcx, [r14+20h]; this
0x18005761c  call    ?CanHandleUserInputOutput@CRemoteDevice@WFDSConMgr@@QEBA_NXZ; WFDSConMgr::CRemoteDevice::CanHandleUserInputOutput(void)
0x180057621  test    al, al
0x180057623  jnz     short loc_18005765D
0x180057625  mov     dword ptr [r14+70h], 6
0x18005762d  mov     [rsp+2E8h+var_2C0], r14; void *
0x180057632  lea     rax, aAttemptedToPai; "Attempted to pair with headless client,"...
0x180057639  mov     [rsp+2E8h+var_2C8], rax; unsigned __int16 *
0x18005763e  mov     r9d, 12Fh; char
0x180057644  lea     r8, aOnecoreuapNetW_25; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18005764b  lea     rdx, aWfdsconmgrCque; "WFDSConMgr::CQueryStateWork::TryExecute"
0x180057652  mov     ecx, 80070032h; char
  ... truncated ...
```
