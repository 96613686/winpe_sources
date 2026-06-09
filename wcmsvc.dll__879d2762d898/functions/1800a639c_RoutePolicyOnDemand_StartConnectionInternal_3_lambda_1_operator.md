# _RoutePolicyOnDemand::StartConnectionInternal_::_3_::_lambda_1_::operator()

- ea: `0x1800a639c`
- end: `0x1800a6e18`
- name: `_RoutePolicyOnDemand::StartConnectionInternal_::_3_::_lambda_1_::operator()`
- size: `2684`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a9600`

## callees

- `0x180003b54`
- `0x180003cc4`
- `0x180003e0c`
- `0x180008394`
- `0x180010080`
- `0x180013afc`
- `0x180024cac`
- `0x180027250`
- `0x180027c68`
- `0x18003a08c`
- `0x18003a55c`
- `0x1800408bc`
- `0x18004d198`
- `0x180052d30`
- `0x180061ddc`
- `0x1800636ac`
- `0x18006462c`
- `0x18006b798`
- `0x18006b818`
- `0x18006bd88`
- `0x180084f50`
- `0x1800a28f4`
- `0x1800a3e98`
- `0x1800a639c`
- `0x1800a7830`
- `0x1800a9884`
- `0x1800b7768`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800a6885`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800a6ab2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800a6b58`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800a6885`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800a6ab2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800a6b58`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800a6824`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800a6bf9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800a6824`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800a6bf9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800a68be`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800a6ca7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800a68be`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800a6ca7`

## string_xrefs

- `0x1800a644b`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`
- `0x1800a6842`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`
- `0x1800a6aef`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`
- `0x1800a6c20`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`
- `0x1800a6de3`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall RoutePolicyOnDemand::StartConnectionInternal_::_3_::_lambda_1_::operator()(
        RoutePolicyOnDemand **a1,
        __int64 a2,
        int a3,
        int a4)
{
  RoutePolicyOnDemand **v5; // rdx
  RoutePolicyOnDemand **v6; // rcx
  int v7; // r8d
  int v8; // r9d
  unsigned int v9; // ebx
  __int64 v11; // rsi
  __int64 v12; // rbx
  RoutePolicyOnDemand *v13; // rax
  char *v14; // rbx
  _QWORD *v15; // rbx
  _QWORD *v16; // rsi
  __int16 v17; // cx
  __int64 v18; // r8
  __int64 v19; // r9
  std::_Ref_count_base *v20; // rcx
  __int64 v21; // rsi
  __int64 v22; // r8
  __int64 v23; // r9
  PTP_TIMER *v24; // rsi
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v26; // r9
  unsigned int LastError; // ebx
  __int64 v28; // rbx
  ULONGLONG TickCount64; // rax
  std::_Ref_count_base *v30; // rcx
  int v31; // r8d
  int v32; // r9d
  __int64 v33; // rax
  _QWORD *v34; // rcx
  __int64 v35; // r9
  RoutePolicyOnDemand *v36; // rsi
  ULONGLONG v37; // rbx
  __int64 v38; // rcx
  unsigned int v39; // eax
  unsigned int v40; // ebx
  std::_Ref_count_base *v41; // rcx
  int v42; // ecx
  __int64 v43; // r8
  char *v44; // rbx
  PTP_TIMER v45; // rax
  const char *v46; // r9
  unsigned int v47; // ebx
  std::_Ref_count_base *v48; // rcx
  __int128 v49; // xmm0
  std::_Ref_count_base *v50; // rcx
  unsigned int v51; // [rsp+20h] [rbp-148h]
  unsigned int v52; // [rsp+70h] [rbp-F8h] BYREF
  unsigned int v53[2]; // [rsp+78h] [rbp-F0h] BYREF
  __int64 v54; // [rsp+80h] [rbp-E8h] BYREF
  int *v55; // [rsp+88h] [rbp-E0h] BYREF
  char *v56; // [rsp+90h] [rbp-D8h] BYREF
  PVOID pv[2]; // [rsp+98h] [rbp-D0h] BYREF
  __int128 v58; // [rsp+A8h] [rbp-C0h] BYREF
  _DWORD Src[2]; // [rsp+B8h] [rbp-B0h] BYREF
  __int128 v60; // [rsp+C0h] [rbp-A8h]
  char v61[8]; // [rsp+D8h] [rbp-90h] BYREF
  int *v62; // [rsp+E0h] [rbp-88h]
  int *v63; // [rsp+E8h] [rbp-80h]
  unsigned int v64; // [rsp+F0h] [rbp-78h]
  std::_Ref_count_base *v65[2]; // [rsp+F8h] [rbp-70h] BYREF
  PVOID v66[3]; // [rsp+108h] [rbp-60h] BYREF
  struct _FILETIME pftDueTime[2]; // [rsp+120h] [rbp-48h] BYREF
  struct _FILETIME v68; // [rsp+130h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v5 = (RoutePolicyOnDemand **)*((_QWORD *)*a1 + 3);
  v6 = (RoutePolicyOnDemand **)*((_QWORD *)*a1 + 4);
  if ( v5 == v6 )
  {
LABEL_89:
    if ( (unsigned int)dword_18013A120 > 5 )
    {
      pftDueTime[0] = (struct _FILETIME)a1[1];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        (_DWORD)v6,
        (unsigned int)&dword_18011912C,
        a3,
        a4,
        (__int64)pftDueTime);
    }
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1B7,
             (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
             (const char *)0x490,
             v51);
  }
  while ( *v5 != a1[1] )
  {
    v5 += 2;
    if ( v5 == v6 )
      goto LABEL_89;
  }
  *(_OWORD *)v65 = 0;
  std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(v65, v5);
  if ( *((_QWORD *)v65[0] + 14) )
  {
    if ( (unsigned int)dword_18013A120 > 3 )
    {
      *(_QWORD *)v53 = a1[1];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        v65[0],
        (unsigned int)byte_18011918B,
        v7,
        v8,
        (__int64)v53);
    }
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1C5,
           (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
           (const char *)0xC,
           v51);
    if ( v65[1] )
      std::_Ref_count_base::_Decref(v65[1]);
    return v9;
  }
  RoutePolicyOnDemand::TrafficParameters::operator WWAN_TRAFFIC_PARAMETERS(v65[0], v61);
  *(_OWORD *)pv = 0;
  v12 = *((_QWORD *)*a1 + 3);
  v11 = *((_QWORD *)*a1 + 4);
  while ( v12 != v11
       && (*(std::_Ref_count_base **)v12 == v65[0]
        || !*(_QWORD *)(*(_QWORD *)v12 + 112LL)
        || !(unsigned __int8)((__int64 (*)(void))RoutePolicyOnDemand::TrafficParameters::operator==)()) )
    v12 += 16;
  v13 = *a1;
  if ( v12 == *((_QWORD *)*a1 + 4) )
  {
    v15 = (_QWORD *)*((_QWORD *)v13 + 6);
    v16 = (_QWORD *)*((_QWORD *)v13 + 7);
    while ( v15 != v16 && !(unsigned __int8)RoutePolicyOnDemand::TrafficParameters::operator==(*v15 + 8LL, v65[0]) )
      ++v15;
    if ( v15 == *((_QWORD **)*a1 + 7) )
      goto LABEL_52;
    std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>::operator=(pv, *v15 + 96LL);
    v14 = (char *)pv[0];
    if ( pv[0] )
      goto LABEL_26;
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  else
  {
    std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>::operator=(pv, *(_QWORD *)v12 + 112LL);
    v14 = (char *)pv[0];
  }
  if ( v14 )
  {
LABEL_26:
    v17 = *((_WORD *)v65[0] + 52);
    if ( v17 == 2 && v14[123] || v17 == 23 && v14[124] || !v17 && (v14[123] || v14[124]) )
    {
      if ( (unsigned int)dword_18013A120 > 4 )
      {
        v66[0] = v65[0];
        v53[0] = *((_DWORD *)v14 + 4);
        v68 = (struct _FILETIME)*((_QWORD *)v14 + 3);
        v56 = v14 + 32;
        *(_QWORD *)&v58 = EnumToString(v64);
        v54 = (__int64)v63;
        v55 = v62;
        pftDueTime[0] = (struct _FILETIME)((char *)v65[0] + 88);
        LOWORD(v52) = *((_WORD *)v65[0] + 52);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          (__int64)v65[0],
          (int)byte_180118F29,
          v18,
          v19,
          (__int64)&v52,
          (__int64 *)pftDueTime,
          &v55,
          (int **)&v54,
          (const char **)&v58,
          (__int64 *)&v56,
          (__int64)&v68,
          (__int64)v53,
          (__int64)v66);
      }
      std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>::operator=((char *)v65[0] + 112, pv);
      std::_Erase_remove_if_std::vector_std::unique_ptr_RoutePolicyOnDemand::Disconnect_std::default_delete_RoutePolicyOnDemand::Disconnect____std::allocator_std::unique_ptr_RoutePolicyOnDemand::Disconnect_std::default_delete_RoutePolicyOnDemand::Disconnect__________RoutePolicyOnDemand::StartConnectionInternal_::_3_::_lambda_1_::operator()_::_73_::_lambda_6___(
        (char *)*a1 + 48,
        v65);
      v20 = v65[0];
      if ( *((_QWORD *)v65[0] + 16) )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v20 = v65[0];
      }
      *((_QWORD *)v20 + 16) = a1[2];
      *((_QWORD *)v65[0] + 17) = a1[3];
      RoutePolicyOnDemand::CompleteRequest(*a1, v65[0], 0, *(union _NET_LUID_LH *)(v14 + 24));
LABEL_84:
      if ( pv[1] )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)pv[1]);
      if ( v65[1] )
        std::_Ref_count_base::_Decref(v65[1]);
      return 0;
    }
    v21 = *((_QWORD *)v14 + 10);
    if ( (unsigned int)dword_18013A120 > 4 )
    {
      pftDueTime[0] = (struct _FILETIME)v65[0];
      v53[0] = v21 == 0;
      v55 = (int *)EnumToString(v64);
      v54 = (__int64)v63;
      *(_QWORD *)&v58 = v62;
      v56 = (char *)v65[0] + 88;
      LOWORD(v52) = *((_WORD *)v65[0] + 52);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (__int64)v65[0],
        (int)word_180118E0A,
        v22,
        v23,
        (__int64)&v52,
        (__int64 *)&v56,
        (int **)&v58,
        (int **)&v54,
        (const char **)&v55,
        (__int64)v53,
        (__int64)pftDueTime);
    }
    if ( !v21 )
    {
      v24 = (PTP_TIMER *)(v14 + 88);
      if ( !*((_QWORD *)v14 + 11) )
      {
        ThreadpoolTimer = CreateThreadpoolTimer(RoutePolicyOnDemand::ReadyTimeoutCallback, v14, 0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          v14 + 88,
          ThreadpoolTimer);
        if ( !*v24 )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x259,
                        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
                        v26);
          if ( pv[1] )
            std::_Ref_count_base::_Decref((std::_Ref_count_base *)pv[1]);
          if ( v65[1] )
            std::_Ref_count_base::_Decref(v65[1]);
          return LastError;
        }
        v28 = *((_QWORD *)v14 + 14);
        TickCount64 = GetTickCount64();
        pftDueTime[0] = (struct _FILETIME)(-10000LL
                                         * ((20000 - ((_DWORD)TickCount64 - (_DWORD)v28))
                                          & (unsigned int)-(TickCount64 - v28 < 0x4E20)));
        SetThreadpoolTimer(*v24, pftDueTime, 0, 0);
      }
    }
    std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>::operator=((char *)v65[0] + 112, pv);
    std::_Erase_remove_if_std::vector_std::unique_ptr_RoutePolicyOnDemand::Disconnect_std::default_delete_RoutePolicyOnDemand::Disconnect____std::allocator_std::unique_ptr_RoutePolicyOnDemand::Disconnect_std::default_delete_RoutePolicyOnDemand::Disconnect__________RoutePolicyOnDemand::StartConnectionInternal_::_3_::_lambda_1_::operator()_::_73_::_lambda_6___(
      (char *)*a1 + 48,
      v65);
    v30 = v65[0];
    if ( *((_QWORD *)v65[0] + 16) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v30 = v65[0];
    }
    *((_QWORD *)v30 + 16) = a1[2];
    *((_QWORD *)v65[0] + 17) = a1[3];
    goto LABEL_84;
  }
LABEL_52:
  if ( (unsigned int)dword_18013A120 > 4 )
  {
    pftDueTime[0] = (struct _FILETIME)v65[0];
    v55 = (int *)EnumToString(v64);
    v54 = (__int64)v63;
    *(_QWORD *)&v58 = v62;
    v56 = (char *)v65[0] + 88;
    LOWORD(v52) = *((_WORD *)v65[0] + 52);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      v65[0],
      (unsigned int)byte_18011907D,
      v31,
      v32,
      (__int64)&v52,
      (__int64)&v56,
      (__int64)&v58,
      (__int64)&v54,
      (__int64)&v55,
      (__int64)pftDueTime);
  }
  *(_OWORD *)v66 = 0;
  std::make_shared<RoutePolicyOnDemand::InterfaceInfo,>(v66);
  *(_OWORD *)v66[0] = *(_OWORD *)((char *)v65[0] + 88);
  v33 = RoutePolicyOnDemand::ProfileNameFromTrafficParameters(Src);
  std::wstring::operator=((char *)v66[0] + 48, v33);
  ProfileRoutePolicyData::~ProfileRoutePolicyData((ProfileRoutePolicyData *)Src);
  v34 = (_QWORD *)*((_QWORD *)*a1 + 1);
  if ( v34 == *((_QWORD **)*a1 + 2) )
  {
    std::vector<std::shared_ptr<RouteManagement::InterfaceInfo>>::_Emplace_reallocate<std::shared_ptr<RouteManagement::InterfaceInfo> const &>(
      *a1,
      *((_QWORD *)*a1 + 1),
      v66);
  }
  else
  {
    std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(
      v34,
      v66);
    *(_QWORD *)(v35 + 8) += 16LL;
  }
  v58 = 0;
  v36 = *a1;
  *(_QWORD *)&v58 = *a1;
  BYTE8(v58) = 1;
  v37 = GetTickCount64();
  v39 = CspManager::ConnectionFromTrafficParameters(v38, (char *)v65[0] + 88, v61, (char *)v66[0] + 96);
  if ( v39 )
  {
    v40 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x1FB,
            (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
            (const char *)v39,
            v51);
    v41 = *(std::_Ref_count_base **)(*((_QWORD *)v36 + 1) - 8LL);
    if ( v41 )
      std::_Ref_count_base::_Decref(v41);
    *((_QWORD *)v36 + 1) -= 16LL;
    if ( v66[1] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v66[1]);
    if ( pv[1] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)pv[1]);
    if ( v65[1] )
      std::_Ref_count_base::_Decref(v65[1]);
    return v40;
  }
  else
  {
    *((_QWORD *)v66[0] + 13) = GetTickCount64();
    if ( (unsigned int)dword_18013A120 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013A120, 0x200000000000LL) )
    {
      pftDueTime[0] = (struct _FILETIME)0x1000000LL;
      v55 = (int *)(v43 - v37);
      v54 = 1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v42,
        (unsigned int)&unk_180119010,
        v43 - v37,
        (unsigned int)&v54,
        (__int64)&v55,
        (__int64)pftDueTime);
    }
    v44 = (char *)v66[0] + 80;
    v45 = CreateThreadpoolTimer(RoutePolicyOnDemand::ConnectTimeoutCallback, v66[0], 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      v44,
      v45);
    if ( *((_QWORD *)v66[0] + 10) )
    {
      v68 = (struct _FILETIME)-200000000LL;
      SetThreadpoolTimer(*((PTP_TIMER *)v66[0] + 10), &v68, 0, 0);
      v49 = *(_OWORD *)((char *)v65[0] + 88);
      Src[0] = 4;
      Src[1] = 1;
      v60 = v49;
      *(GUID *)&pftDueTime[0].dwLowDateTime = GUID_NULL;
      NetworkingTriageScenario::OnDemand::OnDemandConnectionStartedAction(
        (const struct NetworkingTriageScenario::OnDemand::RequiredFields *)Src,
        "RoutePolicyRequest",
        (struct _GUID *)pftDueTime,
        0,
        0);
      std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>::operator=((char *)v65[0] + 112, v66);
      BYTE8(v58) = 0;
      v50 = v65[0];
      if ( *((_QWORD *)v65[0] + 16) )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v50 = v65[0];
      }
      *((_QWORD *)v50 + 16) = a1[2];
      *((_QWORD *)v65[0] + 17) = a1[3];
      if ( v66[1] )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v66[1]);
      goto LABEL_84;
    }
    v47 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x20A,
            (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
            v46);
    v48 = *(std::_Ref_count_base **)(*((_QWORD *)v36 + 1) - 8LL);
    if ( v48 )
      std::_Ref_count_base::_Decref(v48);
    *((_QWORD *)v36 + 1) -= 16LL;
    if ( v66[1] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v66[1]);
    if ( pv[1] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)pv[1]);
    if ( v65[1] )
      std::_Ref_count_base::_Decref(v65[1]);
    return v47;
  }
}

```

## disassembly

```asm
0x1800a639c  push    rbx
0x1800a639e  push    rsi
0x1800a639f  push    rdi
0x1800a63a0  push    r14
0x1800a63a2  sub     rsp, 148h
0x1800a63a9  mov     rax, cs:__security_cookie
0x1800a63b0  xor     rax, rsp
0x1800a63b3  mov     [rsp+168h+var_30], rax
0x1800a63bb  mov     rdi, rcx
0x1800a63be  mov     rax, [rcx]
0x1800a63c1  mov     rdx, [rax+18h]
0x1800a63c5  mov     rcx, [rax+20h]
0x1800a63c9  cmp     rdx, rcx
0x1800a63cc  jz      loc_1800A6DA5
0x1800a63d2  mov     rax, [rdi+8]
0x1800a63d6  cmp     [rdx], rax
0x1800a63d9  jz      short loc_1800A63E9
0x1800a63db  add     rdx, 10h
0x1800a63df  cmp     rdx, rcx
0x1800a63e2  jnz     short loc_1800A63D6
0x1800a63e4  jmp     loc_1800A6DA5
0x1800a63e9  xorps   xmm0, xmm0
0x1800a63ec  movups  xmmword ptr [rsp+168h+var_70], xmm0
0x1800a63f4  lea     rcx, [rsp+168h+var_70]
0x1800a63fc  call    ??$?0V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@$0A@@?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAA@AEBV?$shared_ptr@V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@@1@@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<std::tuple<long,std::unique_ptr<_WCM_ONDEMAND_STATE_INFO,wil::function_deleter<void (*)(void *),&WcmFree(void *)>>>>> const &)
0x1800a6401  nop
0x1800a6402  xor     r14d, r14d
0x1800a6405  mov     rcx, [rsp+168h+var_70]
0x1800a640d  cmp     [rcx+70h], r14
0x1800a6411  jz      short loc_1800A6477
0x1800a6413  mov     eax, cs:dword_18013A120
0x1800a6419  cmp     eax, 3
0x1800a641c  jbe     short loc_1800A643D
0x1800a641e  mov     rax, [rdi+8]
0x1800a6422  mov     qword ptr [rsp+168h+var_F0], rax
0x1800a6427  lea     rax, [rsp+168h+var_F0]
0x1800a642c  mov     qword ptr [rsp+168h+var_148], rax; unsigned int
0x1800a6431  lea     rdx, byte_18011918B
0x1800a6438  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x1800a643d  mov     rcx, [rsp+168h]; this
0x1800a6445  mov     r9d, 0Ch; char *
0x1800a644b  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x1800a6452  mov     edx, 1C5h; void *
0x1800a6457  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a645c  mov     ebx, eax
0x1800a645e  mov     rcx, [rsp+168h+var_70+8]; this
0x1800a6466  test    rcx, rcx
0x1800a6469  jz      short loc_1800A6470
0x1800a646b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a6470  mov     eax, ebx
0x1800a6472  jmp     loc_1800A6DFA
0x1800a6477  lea     rdx, [rsp+168h+var_90]
0x1800a647f  call    ??BTrafficParameters@RoutePolicyOnDemand@@QEBA?AUWWAN_TRAFFIC_PARAMETERS@@XZ; RoutePolicyOnDemand::TrafficParameters::operator WWAN_TRAFFIC_PARAMETERS(void)
0x1800a6484  xorps   xmm1, xmm1
0x1800a6487  movdqu  xmmword ptr [rsp+168h+pv], xmm1
0x1800a6490  mov     rax, [rdi]
0x1800a6493  mov     rbx, [rax+18h]
0x1800a6497  mov     rsi, [rax+20h]
0x1800a649b  jmp     short loc_1800A64C0
0x1800a649d  mov     rdx, [rsp+168h+var_70]
0x1800a64a5  mov     rcx, [rbx]
0x1800a64a8  cmp     rcx, rdx
0x1800a64ab  jz      short loc_1800A64BC
0x1800a64ad  cmp     [rcx+70h], r14
0x1800a64b1  jz      short loc_1800A64BC
0x1800a64b3  call    ??8TrafficParameters@RoutePolicyOnDemand@@QEBA_NAEBU01@@Z; RoutePolicyOnDemand::TrafficParameters::operator==(RoutePolicyOnDemand::TrafficParameters const &)
0x1800a64b8  test    al, al
0x1800a64ba  jnz     short loc_1800A64C5
0x1800a64bc  add     rbx, 10h
0x1800a64c0  cmp     rbx, rsi
0x1800a64c3  jnz     short loc_1800A649D
0x1800a64c5  mov     rax, [rdi]
0x1800a64c8  cmp     rbx, [rax+20h]
0x1800a64cc  jz      short loc_1800A64EC
0x1800a64ce  mov     rdx, [rbx]
0x1800a64d1  add     rdx, 70h ; 'p'
0x1800a64d5  lea     rcx, [rsp+168h+pv]
0x1800a64dd  call    ??4?$shared_ptr@UInterfaceInfo@RoutePolicyOnDemand@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>::operator=(std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo> const &)
0x1800a64e2  mov     rbx, [rsp+168h+pv]
0x1800a64ea  jmp     short loc_1800A654A
0x1800a64ec  mov     rbx, [rax+30h]
0x1800a64f0  mov     rsi, [rax+38h]
0x1800a64f4  jmp     short loc_1800A6512
0x1800a64f6  mov     rcx, [rbx]
0x1800a64f9  add     rcx, 8
0x1800a64fd  mov     rdx, [rsp+168h+var_70]
0x1800a6505  call    ??8TrafficParameters@RoutePolicyOnDemand@@QEBA_NAEBU01@@Z; RoutePolicyOnDemand::TrafficParameters::operator==(RoutePolicyOnDemand::TrafficParameters const &)
0x1800a650a  test    al, al
0x1800a650c  jnz     short loc_1800A6517
0x1800a650e  add     rbx, 8
0x1800a6512  cmp     rbx, rsi
0x1800a6515  jnz     short loc_1800A64F6
0x1800a6517  mov     rax, [rdi]
0x1800a651a  cmp     rbx, [rax+38h]
0x1800a651e  jz      loc_1800A6932
0x1800a6524  mov     rdx, [rbx]
0x1800a6527  add     rdx, 60h ; '`'
0x1800a652b  lea     rcx, [rsp+168h+pv]
0x1800a6533  call    ??4?$shared_ptr@UInterfaceInfo@RoutePolicyOnDemand@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>::operator=(std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo> const &)
0x1800a6538  mov     rbx, [rsp+168h+pv]
0x1800a6540  test    rbx, rbx
0x1800a6543  jnz     short loc_1800A6553
0x1800a6545  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a654a  test    rbx, rbx
0x1800a654d  jz      loc_1800A6932
0x1800a6553  mov     rax, [rsp+168h+var_70]
0x1800a655b  movzx   ecx, word ptr [rax+68h]
0x1800a655f  cmp     cx, 2
0x1800a6563  jnz     short loc_1800A656B
0x1800a6565  cmp     [rbx+7Bh], r14b
0x1800a6569  jnz     short loc_1800A6590
0x1800a656b  cmp     cx, 17h
0x1800a656f  jnz     short loc_1800A6577
0x1800a6571  cmp     [rbx+7Ch], r14b
0x1800a6575  jnz     short loc_1800A6590
0x1800a6577  test    cx, cx
0x1800a657a  jnz     loc_1800A671F
0x1800a6580  cmp     [rbx+7Bh], r14b
0x1800a6584  jnz     short loc_1800A6590
0x1800a6586  cmp     [rbx+7Ch], r14b
0x1800a658a  jz      loc_1800A671F
0x1800a6590  mov     eax, cs:dword_18013A120
0x1800a6596  cmp     eax, 4
0x1800a6599  jbe     loc_1800A669A
0x1800a659f  mov     rax, [rsp+168h+var_70]
0x1800a65a7  mov     [rsp+168h+var_60], rax
0x1800a65af  mov     eax, [rbx+10h]
0x1800a65b2  mov     [rsp+168h+var_F0], eax
0x1800a65b6  mov     rax, [rbx+18h]
0x1800a65ba  mov     qword ptr [rsp+168h+var_38.dwLowDateTime], rax
0x1800a65c2  lea     rax, [rbx+20h]
0x1800a65c6  mov     [rsp+168h+var_D8], rax
0x1800a65ce  mov     ecx, [rsp+168h+var_78]
0x1800a65d5  call    ?EnumToString@@YAPEBDW4WWAN_CONNECTION_CAPABILITY@@@Z; EnumToString(WWAN_CONNECTION_CAPABILITY)
0x1800a65da  mov     qword ptr [rsp+168h+var_C0], rax
0x1800a65e2  mov     rax, [rsp+168h+var_80]
0x1800a65ea  mov     [rsp+168h+var_E8], rax
0x1800a65f2  mov     rax, [rsp+168h+var_88]
0x1800a65fa  mov     [rsp+168h+var_E0], rax
0x1800a6602  mov     rcx, [rsp+168h+var_70]
0x1800a660a  lea     rax, [rcx+58h]
0x1800a660e  mov     qword ptr [rsp+168h+pftDueTime.dwLowDateTime], rax
0x1800a6616  movzx   eax, word ptr [rcx+68h]
0x1800a661a  mov     word ptr [rsp+168h+var_F8], ax
0x1800a661f  lea     rax, [rsp+168h+var_60]
0x1800a6627  mov     [rsp+168h+var_108], rax
0x1800a662c  lea     rax, [rsp+168h+var_F0]
0x1800a6631  mov     [rsp+168h+var_110], rax
0x1800a6636  lea     rax, [rsp+168h+var_38]
0x1800a663e  mov     [rsp+168h+var_118], rax
0x1800a6643  lea     rax, [rsp+168h+var_D8]
0x1800a664b  mov     [rsp+168h+var_120], rax
0x1800a6650  lea     rax, [rsp+168h+var_C0]
0x1800a6658  mov     [rsp+168h+var_128], rax
0x1800a665d  lea     rax, [rsp+168h+var_E8]
0x1800a6665  mov     [rsp+168h+var_130], rax
0x1800a666a  lea     rax, [rsp+168h+var_E0]
0x1800a6672  mov     [rsp+168h+var_138], rax
0x1800a6677  lea     rax, [rsp+168h+pftDueTime]
0x1800a667f  mov     [rsp+168h+var_140], rax
0x1800a6684  lea     rax, [rsp+168h+var_F8]
0x1800a6689  mov     qword ptr [rsp+168h+var_148], rax
0x1800a668e  lea     rdx, byte_180118F29
0x1800a6695  call    ??$Write@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapSz@D@@U2@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U5@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapSz@D@@4AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@7@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<2> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800a669a  mov     rcx, [rsp+168h+var_70]
0x1800a66a2  add     rcx, 70h ; 'p'
0x1800a66a6  lea     rdx, [rsp+168h+pv]
0x1800a66ae  call    ??4?$shared_ptr@UInterfaceInfo@RoutePolicyOnDemand@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>::operator=(std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo> const &)
0x1800a66b3  mov     rcx, [rdi]
0x1800a66b6  add     rcx, 30h ; '0'
0x1800a66ba  lea     rdx, [rsp+168h+var_70]
0x1800a66c2  call    std___Erase_remove_if_std__vector_std__unique_ptr_RoutePolicyOnDemand__Disconnect_std__default_delete_RoutePolicyOnDemand__Disconnect____std__allocator_std__unique_ptr_RoutePolicyOnDemand__Disconnect_std__default_delete_RoutePolicyOnDemand__Disconnect__________RoutePolicyOnDemand__StartConnectionInternal____3____lambda_1___operator______73____lambda_6___
0x1800a66c7  mov     rcx, [rsp+168h+var_70]
0x1800a66cf  cmp     [rcx+80h], r14
0x1800a66d6  jz      short loc_1800A66E5
0x1800a66d8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a66dd  mov     rcx, [rsp+168h+var_70]
0x1800a66e5  mov     rax, [rdi+10h]
0x1800a66e9  mov     [rcx+80h], rax
0x1800a66f0  mov     rcx, [rdi+18h]
0x1800a66f4  mov     rax, [rsp+168h+var_70]
0x1800a66fc  mov     [rax+88h], rcx
0x1800a6703  mov     r9, [rbx+18h]; union _NET_LUID_LH
0x1800a6707  xor     r8d, r8d; int
0x1800a670a  mov     rdx, [rsp+168h+var_70]; struct Request *
0x1800a6712  mov     rcx, [rdi]; this
0x1800a6715  call    ?CompleteRequest@RoutePolicyOnDemand@@AEAAXAEAURequest@1@JT_NET_LUID_LH@@@Z; RoutePolicyOnDemand::CompleteRequest(RoutePolicyOnDemand::Request &,long,_NET_LUID_LH)
0x1800a671a  jmp     loc_1800A6D7C
0x1800a671f  mov     rsi, [rbx+50h]
0x1800a6723  mov     eax, cs:dword_18013A120
0x1800a6729  cmp     eax, 4
0x1800a672c  jbe     loc_1800A6801
0x1800a6732  mov     rax, [rsp+168h+var_70]
0x1800a673a  mov     qword ptr [rsp+168h+pftDueTime.dwLowDateTime], rax
0x1800a6742  mov     eax, r14d
0x1800a6745  test    rsi, rsi
0x1800a6748  setz    al
0x1800a674b  mov     [rsp+168h+var_F0], eax
0x1800a674f  mov     ecx, [rsp+168h+var_78]
0x1800a6756  call    ?EnumToString@@YAPEBDW4WWAN_CONNECTION_CAPABILITY@@@Z; EnumToString(WWAN_CONNECTION_CAPABILITY)
0x1800a675b  mov     [rsp+168h+var_E0], rax
0x1800a6763  mov     rax, [rsp+168h+var_80]
0x1800a676b  mov     [rsp+168h+var_E8], rax
0x1800a6773  mov     rax, [rsp+168h+var_88]
0x1800a677b  mov     qword ptr [rsp+168h+var_C0], rax
0x1800a6783  mov     rcx, [rsp+168h+var_70]
0x1800a678b  lea     rax, [rcx+58h]
0x1800a678f  mov     [rsp+168h+var_D8], rax
0x1800a6797  movzx   eax, word ptr [rcx+68h]
0x1800a679b  mov     word ptr [rsp+168h+var_F8], ax
0x1800a67a0  lea     rax, [rsp+168h+pftDueTime]
0x1800a67a8  mov     [rsp+168h+var_118], rax
0x1800a67ad  lea     rax, [rsp+168h+var_F0]
0x1800a67b2  mov     [rsp+168h+var_120], rax
0x1800a67b7  lea     rax, [rsp+168h+var_E0]
0x1800a67bf  mov     [rsp+168h+var_128], rax
0x1800a67c4  lea     rax, [rsp+168h+var_E8]
0x1800a67cc  mov     [rsp+168h+var_130], rax
0x1800a67d1  lea     rax, [rsp+168h+var_C0]
0x1800a67d9  mov     [rsp+168h+var_138], rax
0x1800a67de  lea     rax, [rsp+168h+var_D8]
0x1800a67e6  mov     [rsp+168h+var_140], rax
0x1800a67eb  lea     rax, [rsp+168h+var_F8]
0x1800a67f0  mov     qword ptr [rsp+168h+var_148], rax
0x1800a67f5  lea     rdx, word_180118E0A
0x1800a67fc  call    ??$Write@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<2> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800a6801  test    rsi, rsi
0x1800a6804  jnz     loc_1800A68C4
0x1800a680a  lea     rsi, [rbx+58h]
0x1800a680e  cmp     [rsi], r14
0x1800a6811  jnz     loc_1800A68C4
0x1800a6817  xor     r8d, r8d; pcbe
0x1800a681a  mov     rdx, rbx; pv
0x1800a681d  lea     rcx, ?ReadyTimeoutCallback@RoutePolicyOnDemand@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800a6824  call    cs:__imp_CreateThreadpoolTimer
0x1800a682a  mov     rdx, rax
0x1800a682d  mov     rcx, rsi
0x1800a6830  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800a6835  cmp     [rsi], r14
0x1800a6838  jnz     short loc_1800A6881
0x1800a683a  mov     rcx, [rsp+168h]; this
0x1800a6842  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x1800a6849  mov     edx, 259h; void *
0x1800a684e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a6853  mov     ebx, eax
0x1800a6855  mov     rcx, [rsp+168h+pv+8]; this
0x1800a685d  test    rcx, rcx
0x1800a6860  jz      short loc_1800A6868
0x1800a6862  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a6867  nop
0x1800a6868  mov     rcx, [rsp+168h+var_70+8]; this
0x1800a6870  test    rcx, rcx
0x1800a6873  jz      short loc_1800A687A
0x1800a6875  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a687a  mov     eax, ebx
0x1800a687c  jmp     loc_1800A6DFA
0x1800a6881  mov     rbx, [rbx+70h]
0x1800a6885  call    cs:__imp_GetTickCount64
0x1800a688b  sub     rax, rbx
0x1800a688e  mov     ecx, 4E20h
0x1800a6893  mov     edx, ecx
0x1800a6895  sub     edx, eax
0x1800a6897  cmp     rax, rcx
0x1800a689a  sbb     eax, eax
0x1800a689c  and     eax, edx
0x1800a689e  imul    rdx, rax, 0FFFFFFFFFFFFD8F0h
0x1800a68a5  mov     qword ptr [rsp+168h+pftDueTime.dwLowDateTime], rdx
0x1800a68ad  xor     r9d, r9d; msWindowLength
0x1800a68b0  xor     r8d, r8d; msPeriod
0x1800a68b3  lea     rdx, [rsp+168h+pftDueTime]; pftDueTime
0x1800a68bb  mov     rcx, [rsi]; pti
0x1800a68be  call    cs:__imp_SetThreadpoolTimer
0x1800a68c4  mov     rcx, [rsp+168h+var_70]
0x1800a68cc  add     rcx, 70h ; 'p'
0x1800a68d0  lea     rdx, [rsp+168h+pv]
0x1800a68d8  call    ??4?$shared_ptr@UInterfaceInfo@RoutePolicyOnDemand@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>::operator=(std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo> const &)
0x1800a68dd  mov     rcx, [rdi]
0x1800a68e0  add     rcx, 30h ; '0'
0x1800a68e4  lea     rdx, [rsp+168h+var_70]
0x1800a68ec  call    std___Erase_remove_if_std__vector_std__unique_ptr_RoutePolicyOnDemand__Disconnect_std__default_delete_RoutePolicyOnDemand__Disconnect____std__allocator_std__unique_ptr_RoutePolicyOnDemand__Disconnect_std__default_delete_RoutePolicyOnDemand__Disconnect__________RoutePolicyOnDemand__StartConnectionInternal____3____lambda_1___operator______73____lambda_6___
0x1800a68f1  mov     rcx, [rsp+168h+var_70]
0x1800a68f9  cmp     [rcx+80h], r14
0x1800a6900  jz      short loc_1800A690F
0x1800a6902  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a6907  mov     rcx, [rsp+168h+var_70]
0x1800a690f  mov     rax, [rdi+10h]
0x1800a6913  mov     [rcx+80h], rax
0x1800a691a  mov     rcx, [rdi+18h]
0x1800a691e  mov     rax, [rsp+168h+var_70]
0x1800a6926  mov     [rax+88h], rcx
0x1800a692d  jmp     loc_1800A6D7C
0x1800a6932  mov     eax, cs:dword_18013A120
0x1800a6938  cmp     eax, 4
0x1800a693b  jbe     loc_1800A69F9
0x1800a6941  mov     rax, [rsp+168h+var_70]
0x1800a6949  mov     qword ptr [rsp+168h+pftDueTime.dwLowDateTime], rax
0x1800a6951  mov     ecx, [rsp+168h+var_78]
0x1800a6958  call    ?EnumToString@@YAPEBDW4WWAN_CONNECTION_CAPABILITY@@@Z; EnumToString(WWAN_CONNECTION_CAPABILITY)
0x1800a695d  mov     [rsp+168h+var_E0], rax
0x1800a6965  mov     rax, [rsp+168h+var_80]
  ... truncated ...
```
