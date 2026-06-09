# NlmManager::InitializeCOM(void)

- ea: `0x18005ee18`
- end: `0x18005f41a`
- name: `?InitializeCOM@NlmManager@@AEAA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@wil@@XZ`
- size: `1538`
- prototype: ``
- caller_count: `8`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180031ae4`
- `0x180050bb0`
- `0x18005eb98`
- `0x180071ec8`
- `0x1800c92d0`
- `0x1800c9430`
- `0x1800c97c8`
- `0x1800c9dec`

## callees

- `0x1800137a0`
- `0x180019434`
- `0x18001b710`
- `0x180027630`
- `0x180032644`
- `0x180034584`
- `0x18003a08c`
- `0x1800430d8`
- `0x18005eae0`
- `0x18005ee18`
- `0x180069f88`
- `0x18006a1b0`
- `0x18006a448`
- `0x180072ccc`
- `0x180072d28`
- `0x180084f50`
- `0x180092970`
- `0x1800b60dc`
- `0x1800c7fb0`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005f3ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005f3ed`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x18005eea0`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x18005eea0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005ef9d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005ef9d`

## string_xrefs

- `0x18005ee82`: `onecoreuap\net\wcm\service\base\nlmmanager\lib\nlmmanager.cpp`
- `0x18005eebc`: `NlmManager::InitializeCOM - CoIncrementMTAUsage failed`
- `0x18005efcb`: `CoCreateInstance(INetworkListManagerPrivate)`
- `0x18005ef42`: `NlmManager::InitializeCOM - creating a new NLM instance`
- `0x18005f382`: `Reset the INetworkListManagerPrivate ptr because the netprofm service is not running`
- `0x18005f312`: `NlmManager::InitializeCOM - NLM service is not running`
- `0x18005f2a1`: `NlmManager::InitializeCOM - created new NLM instance`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NlmManager::InitializeCOM(__int64 a1, __int64 a2)
{
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  LPVOID *v7; // rdi
  int v8; // ecx
  int v9; // ebx
  HRESULT v10; // eax
  int v11; // r8d
  int v12; // r9d
  int v13; // ebx
  int v14; // ecx
  int v15; // eax
  int v16; // r8d
  int v17; // r9d
  int v18; // ebx
  int v19; // ecx
  int v20; // eax
  int v21; // r8d
  int v22; // r9d
  int v23; // ebx
  int v24; // ecx
  int v25; // eax
  int v26; // r8d
  int v27; // r9d
  int v28; // ebx
  int v29; // ecx
  LPVOID v30; // rcx
  LPVOID v31; // rbx
  WcmCommon::COM::AdviseHandler::AdviseInstance *v32; // rdx
  WcmCommon::COM::AdviseHandler::AdviseInstance *v33; // rcx
  WcmCommon::COM::AdviseHandler::AdviseInstance *v34; // rdx
  WcmCommon::COM::AdviseHandler::AdviseInstance *v35; // rcx
  int v36; // ecx
  int v37; // r8d
  int v38; // r9d
  int ppv; // [rsp+20h] [rbp-49h]
  int v41[2]; // [rsp+40h] [rbp-29h] BYREF
  int v42[2]; // [rsp+48h] [rbp-21h] BYREF
  const char *v43; // [rsp+50h] [rbp-19h] BYREF
  int v44; // [rsp+58h] [rbp-11h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp-9h] BYREF
  __int64 v46; // [rsp+68h] [rbp-1h] BYREF
  LPVOID *v47; // [rsp+70h] [rbp+7h]
  const char **v48; // [rsp+78h] [rbp+Fh]
  __int64 v49; // [rsp+80h] [rbp+17h]
  LPVOID v50; // [rsp+88h] [rbp+1Fh] BYREF
  const char *v51; // [rsp+90h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v49 = a2;
  wil::CoInitializeEx(a2);
  v44 = 1;
  lpCriticalSection = 0;
  wil::EnterCriticalSection(&lpCriticalSection, a1 + 920);
  v7 = (LPVOID *)(a1 + 848);
  if ( !*(_QWORD *)(a1 + 880) )
  {
    wil::details::unique_storage<wil::details::resource_policy<CO_MTA_USAGE_COOKIE__ *,long (*)(CO_MTA_USAGE_COOKIE__ *),&long CoDecrementMTAUsage(CO_MTA_USAGE_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_MTA_USAGE_COOKIE__ *,CO_MTA_USAGE_COOKIE__ *,0,std::nullptr_t>>::reset(
      a1 + 880,
      0);
    v9 = CoIncrementMTAUsage(a1 + 880);
    if ( v9 < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( (unsigned int)dword_18013A120 > 5 )
    {
      v51 = "NlmManager::InitializeCOM - CoIncrementMTAUsage failed";
      v50 = (LPVOID)"onecoreuap\\net\\wcm\\service\\base\\nlmmanager\\lib\\nlmmanager.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v8,
        (unsigned int)&byte_18011F20F,
        v5,
        v6,
        (__int64)&v50,
        (__int64)&v51);
    }
    v4 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        11,
        &WPP_27fc5881657a3a5d8e63e8dc45cbf9d3_Traceguids,
        (unsigned int)v9);
    }
  }
  if ( *(_BYTE *)(a1 + 888) )
  {
    if ( !*v7 )
    {
      if ( (unsigned int)dword_18013A120 > 5 )
      {
        v43 = "NlmManager::InitializeCOM - creating a new NLM instance";
        *(_QWORD *)v41 = "onecoreuap\\net\\wcm\\service\\base\\nlmmanager\\lib\\nlmmanager.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v4,
          (unsigned int)&byte_18011F1DF,
          v5,
          v6,
          (__int64)v41,
          (__int64)&v43);
      }
      v50 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
      v10 = CoCreateInstance(&CLSID_CNetworkListManager, 0, 4u, &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b, &v50);
      v13 = v10;
      v14 = (int)retaddr;
      if ( v10 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xBD,
          (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\nlmmanager\\lib\\nlmmanager.cpp",
          (const char *)(unsigned int)v10,
          ppv);
      if ( (unsigned int)dword_18013A120 > 5 )
      {
        LODWORD(v43) = v13;
        *(_QWORD *)v41 = "CoCreateInstance(INetworkListManagerPrivate)";
        *(_QWORD *)v42 = "onecoreuap\\net\\wcm\\service\\base\\nlmmanager\\lib\\nlmmanager.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v14,
          (unsigned int)&byte_18011F0D7,
          v11,
          v12,
          (__int64)v42,
          (__int64)v41,
          (__int64)&v43);
      }
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          12,
          &WPP_27fc5881657a3a5d8e63e8dc45cbf9d3_Traceguids,
          (unsigned int)v13);
      }
      v51 = 0;
      if ( v13 < 0 )
        goto LABEL_57;
      v51 = 0;
      v15 = Microsoft::WRL::Details::MakeAndInitialize<NlmManager::NlmEventSink,INotifyNetworkListManagerEventsPrivate,>(&v51);
      v18 = v15;
      v19 = (int)retaddr;
      if ( v15 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xC4,
          (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\nlmmanager\\lib\\nlmmanager.cpp",
          (const char *)(unsigned int)v15,
          ppv);
      if ( (unsigned int)dword_18013A120 > 5 )
      {
        LODWORD(v43) = v18;
        *(_QWORD *)v42 = "MakeAndInitialize(NlmEventSink)";
        *(_QWORD *)v41 = "onecoreuap\\net\\wcm\\service\\base\\nlmmanager\\lib\\nlmmanager.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v19,
          (unsigned int)byte_18011F09B,
          v16,
          v17,
          (__int64)v41,
          (__int64)v42,
          (__int64)&v43);
      }
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          13,
          &WPP_27fc5881657a3a5d8e63e8dc45cbf9d3_Traceguids,
          (unsigned int)v18);
      }
      if ( v18 < 0 )
        goto LABEL_57;
      v46 = a1;
      v47 = &v50;
      v48 = &v51;
      v20 = wil::ResultFromException__NlmManager::InitializeCOM_::_37_::_lambda_1___(&v46);
      v23 = v20;
      v24 = (int)retaddr;
      if ( v20 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xCE,
          (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\nlmmanager\\lib\\nlmmanager.cpp",
          (const char *)(unsigned int)v20,
          ppv);
      if ( (unsigned int)dword_18013A120 > 5 )
      {
        LODWORD(v43) = v23;
        *(_QWORD *)v42 = "Advise(INotifyNetworkListManagerEventsPrivate)";
        *(_QWORD *)v41 = "onecoreuap\\net\\wcm\\service\\base\\nlmmanager\\lib\\nlmmanager.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v24,
          (unsigned int)&byte_18011F05F,
          v21,
          v22,
          (__int64)v41,
          (__int64)v42,
          (__int64)&v43);
      }
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          14,
          &WPP_27fc5881657a3a5d8e63e8dc45cbf9d3_Traceguids,
          (unsigned int)v23);
      }
      if ( v23 < 0 )
        goto LABEL_57;
      v46 = a1;
      v47 = &v50;
      v48 = &v51;
      v25 = wil::ResultFromException__NlmManager::InitializeCOM_::_45_::_lambda_2___(&v46);
      v28 = v25;
      v29 = (int)retaddr;
      if ( v25 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xD8,
          (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\nlmmanager\\lib\\nlmmanager.cpp",
          (const char *)(unsigned int)v25,
          ppv);
      if ( (unsigned int)dword_18013A120 > 5 )
      {
        LODWORD(v43) = v28;
        *(_QWORD *)v42 = "Advise(INotifyNetworkInterfaceEventsPrivate)";
        *(_QWORD *)v41 = "onecoreuap\\net\\wcm\\service\\base\\nlmmanager\\lib\\nlmmanager.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v29,
          (unsigned int)byte_18011F1A3,
          v26,
          v27,
          (__int64)v41,
          (__int64)v42,
          (__int64)&v43);
      }
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          15,
          &WPP_27fc5881657a3a5d8e63e8dc45cbf9d3_Traceguids,
          (unsigned int)v28);
      }
      if ( v28 < 0 )
      {
LABEL_57:
        v32 = *(WcmCommon::COM::AdviseHandler::AdviseInstance **)(a1 + 864);
        v33 = *(WcmCommon::COM::AdviseHandler::AdviseInstance **)(a1 + 856);
        if ( v33 != v32 )
        {
          std::_Destroy_range<std::allocator<WcmCommon::COM::AdviseHandler::AdviseInstance>>(v33, v32);
          *(_QWORD *)(a1 + 864) = *(_QWORD *)(a1 + 856);
        }
      }
      else
      {
        v30 = v50;
        v31 = *v7;
        *v7 = v50;
        if ( v30 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v30 + 8LL))(v30);
        if ( v31 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v31 + 16LL))(v31);
        if ( (unsigned int)dword_18013A120 > 5 )
        {
          *(_QWORD *)v42 = "NlmManager::InitializeCOM - created new NLM instance";
          *(_QWORD *)v41 = "onecoreuap\\net\\wcm\\service\\base\\nlmmanager\\lib\\nlmmanager.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (_DWORD)v30,
            (unsigned int)byte_18011F173,
            v26,
            v27,
            (__int64)v41,
            (__int64)v42);
        }
        NlmManager::IndicatePowerStatusChange();
      }
      wil::com_ptr_t<IEnumNetworkInterfacePrivate,wil::err_exception_policy>::~com_ptr_t<IEnumNetworkInterfacePrivate,wil::err_exception_policy>(&v51);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
    }
  }
  else
  {
    if ( (unsigned int)dword_18013A120 > 5 )
    {
      *(_QWORD *)v42 = "NlmManager::InitializeCOM - NLM service is not running";
      *(_QWORD *)v41 = "onecoreuap\\net\\wcm\\service\\base\\nlmmanager\\lib\\nlmmanager.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v4,
        (unsigned int)byte_18011F143,
        v5,
        v6,
        (__int64)v41,
        (__int64)v42);
    }
    if ( *v7 )
    {
      v34 = *(WcmCommon::COM::AdviseHandler::AdviseInstance **)(a1 + 864);
      v35 = *(WcmCommon::COM::AdviseHandler::AdviseInstance **)(a1 + 856);
      if ( v35 != v34 )
      {
        std::_Destroy_range<std::allocator<WcmCommon::COM::AdviseHandler::AdviseInstance>>(v35, v34);
        *(_QWORD *)(a1 + 864) = *(_QWORD *)(a1 + 856);
      }
      wil::com_ptr_t<INetworkListManagerPrivate,wil::err_exception_policy>::reset(a1 + 848);
      if ( (unsigned int)dword_18013A120 > 5 )
      {
        *(_QWORD *)v42 = "Reset the INetworkListManagerPrivate ptr because the netprofm service is not running";
        *(_QWORD *)v41 = "onecoreuap\\net\\wcm\\service\\base\\nlmmanager\\lib\\nlmmanager.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v36,
          (unsigned int)byte_18011F113,
          v37,
          v38,
          (__int64)v41,
          (__int64)v42);
      }
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, &WPP_27fc5881657a3a5d8e63e8dc45cbf9d3_Traceguids);
      }
    }
  }
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  return a2;
}

```

## disassembly

```asm
0x18005ee18  mov     [rsp-8+arg_10], rbx
0x18005ee1d  push    rbp
0x18005ee1e  push    rsi
0x18005ee1f  push    rdi
0x18005ee20  push    r12
0x18005ee22  push    r14
0x18005ee24  lea     rbp, [rsp-37h]
0x18005ee29  sub     rsp, 0A0h
0x18005ee30  mov     rax, cs:__security_cookie
0x18005ee37  xor     rax, rsp
0x18005ee3a  mov     [rbp+57h+var_28], rax
0x18005ee3e  mov     r14, rdx
0x18005ee41  mov     rsi, rcx
0x18005ee44  mov     [rbp+57h+var_40], rdx
0x18005ee48  mov     [rbp+57h+var_68], 0
0x18005ee4f  mov     rcx, rdx
0x18005ee52  call    ?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx(ulong)
0x18005ee57  mov     [rbp+57h+var_68], 1
0x18005ee5e  mov     [rbp+57h+lpCriticalSection], 0
0x18005ee66  lea     rdx, [rsi+398h]
0x18005ee6d  lea     rcx, [rbp+57h+lpCriticalSection]
0x18005ee71  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18005ee76  nop
0x18005ee77  lea     rdi, [rsi+350h]
0x18005ee7e  lea     rbx, [rdi+20h]
0x18005ee82  lea     r12, aOnecoreuapNetW_33; "onecoreuap\\net\\wcm\\service\\base\\nl"...
0x18005ee89  cmp     qword ptr [rbx], 0
0x18005ee8d  jnz     loc_18005EF20
0x18005ee93  xor     edx, edx
0x18005ee95  mov     rcx, rbx
0x18005ee98  call    ?reset@?$unique_storage@U?$resource_policy@PEAUCO_MTA_USAGE_COOKIE__@@P6AJPEAU1@@Z$1?CoDecrementMTAUsage@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUCO_MTA_USAGE_COOKIE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<CO_MTA_USAGE_COOKIE__ *,long (*)(CO_MTA_USAGE_COOKIE__ *),&CoDecrementMTAUsage(CO_MTA_USAGE_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_MTA_USAGE_COOKIE__ *,CO_MTA_USAGE_COOKIE__ *,0,std::nullptr_t>>::reset(CO_MTA_USAGE_COOKIE__ *)
0x18005ee9d  mov     rcx, rbx
0x18005eea0  call    cs:__imp_CoIncrementMTAUsage
0x18005eea6  mov     ebx, eax
0x18005eea8  test    eax, eax
0x18005eeaa  jns     short loc_18005EEB1
0x18005eeac  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005eeb1  mov     eax, cs:dword_18013A120
0x18005eeb7  cmp     eax, 5
0x18005eeba  jbe     short loc_18005EEE9
0x18005eebc  lea     rax, aNlmmanagerInit_2; "NlmManager::InitializeCOM - CoIncrement"...
0x18005eec3  mov     [rbp+57h+var_30], rax
0x18005eec7  mov     [rbp+57h+var_38], r12
0x18005eecb  lea     rax, [rbp+57h+var_30]
0x18005eecf  mov     [rsp+0C0h+var_98], rax
0x18005eed4  lea     rax, [rbp+57h+var_38]
0x18005eed8  mov     [rsp+0C0h+ppv], rax
0x18005eedd  lea     rdx, byte_18011F20F
0x18005eee4  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18005eee9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eef0  lea     rax, WPP_GLOBAL_Control
0x18005eef7  cmp     rcx, rax
0x18005eefa  jz      short loc_18005EF20
0x18005eefc  cmp     byte ptr [rcx+19h], 4
0x18005ef00  jb      short loc_18005EF20
0x18005ef02  test    byte ptr [rcx+1Ch], 1
0x18005ef06  jz      short loc_18005EF20
0x18005ef08  mov     edx, 0Bh
0x18005ef0d  mov     r9d, ebx
0x18005ef10  lea     r8, WPP_27fc5881657a3a5d8e63e8dc45cbf9d3_Traceguids
0x18005ef17  mov     rcx, [rcx+10h]
0x18005ef1b  call    WPP_SF_d
0x18005ef20  cmp     byte ptr [rsi+378h], 0
0x18005ef27  jz      loc_18005F307
0x18005ef2d  cmp     qword ptr [rdi], 0
0x18005ef31  jnz     loc_18005F3E4
0x18005ef37  mov     eax, cs:dword_18013A120
0x18005ef3d  cmp     eax, 5
0x18005ef40  jbe     short loc_18005EF6F
0x18005ef42  lea     rax, aNlmmanagerInit; "NlmManager::InitializeCOM - creating a "...
0x18005ef49  mov     [rbp+57h+var_70], rax
0x18005ef4d  mov     qword ptr [rbp+57h+var_80], r12
0x18005ef51  lea     rax, [rbp+57h+var_70]
0x18005ef55  mov     [rsp+0C0h+var_98], rax
0x18005ef5a  lea     rax, [rbp+57h+var_80]
0x18005ef5e  mov     [rsp+0C0h+ppv], rax
0x18005ef63  lea     rdx, byte_18011F1DF
0x18005ef6a  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18005ef6f  mov     [rbp+57h+var_38], 0
0x18005ef77  lea     rcx, [rbp+57h+var_38]
0x18005ef7b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005ef80  lea     rax, [rbp+57h+var_38]
0x18005ef84  mov     [rsp+0C0h+ppv], rax; int
0x18005ef89  lea     r9, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b; riid
0x18005ef90  xor     edx, edx; pUnkOuter
0x18005ef92  lea     r8d, [rdx+4]; dwClsContext
0x18005ef96  lea     rcx, CLSID_CNetworkListManager; rclsid
0x18005ef9d  call    cs:__imp_CoCreateInstance
0x18005efa3  mov     ebx, eax
0x18005efa5  mov     rcx, [rbp+5Fh]; this
0x18005efa9  test    eax, eax
0x18005efab  jns     short loc_18005EFBD
0x18005efad  mov     r9d, eax; char *
0x18005efb0  mov     r8, r12; unsigned int
0x18005efb3  mov     edx, 0BDh; void *
0x18005efb8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005efbd  mov     eax, cs:dword_18013A120
0x18005efc3  cmp     eax, 5
0x18005efc6  jbe     short loc_18005F001
0x18005efc8  mov     dword ptr [rbp+57h+var_70], ebx
0x18005efcb  lea     rax, aCocreateinstan; "CoCreateInstance(INetworkListManagerPri"...
0x18005efd2  mov     qword ptr [rbp+57h+var_80], rax
0x18005efd6  mov     qword ptr [rbp+57h+var_78], r12
0x18005efda  lea     rax, [rbp+57h+var_70]
0x18005efde  mov     [rsp+0C0h+var_90], rax
0x18005efe3  lea     rax, [rbp+57h+var_80]
0x18005efe7  mov     [rsp+0C0h+var_98], rax
0x18005efec  lea     rax, [rbp+57h+var_78]
0x18005eff0  mov     [rsp+0C0h+ppv], rax; int
0x18005eff5  lea     rdx, byte_18011F0D7
0x18005effc  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005f001  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f008  lea     rax, WPP_GLOBAL_Control
0x18005f00f  cmp     rcx, rax
0x18005f012  jz      short loc_18005F038
0x18005f014  cmp     byte ptr [rcx+19h], 4
0x18005f018  jb      short loc_18005F038
0x18005f01a  test    byte ptr [rcx+1Ch], 1
0x18005f01e  jz      short loc_18005F038
0x18005f020  mov     edx, 0Ch
0x18005f025  mov     r9d, ebx
0x18005f028  lea     r8, WPP_27fc5881657a3a5d8e63e8dc45cbf9d3_Traceguids
0x18005f02f  mov     rcx, [rcx+10h]
0x18005f033  call    WPP_SF_d
0x18005f038  mov     [rbp+57h+var_30], 0
0x18005f040  test    ebx, ebx
0x18005f042  js      loc_18005F2D5
0x18005f048  mov     [rbp+57h+var_30], 0
0x18005f050  lea     rcx, [rbp+57h+var_30]
0x18005f054  call    ??$MakeAndInitialize@VNlmEventSink@NlmManager@@UINotifyNetworkListManagerEventsPrivate@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUINotifyNetworkListManagerEventsPrivate@@@Z; Microsoft::WRL::Details::MakeAndInitialize<NlmManager::NlmEventSink,INotifyNetworkListManagerEventsPrivate,>(INotifyNetworkListManagerEventsPrivate * *)
0x18005f059  mov     ebx, eax
0x18005f05b  mov     rcx, [rbp+5Fh]; this
0x18005f05f  test    eax, eax
0x18005f061  jns     short loc_18005F073
0x18005f063  mov     r9d, eax; char *
0x18005f066  mov     r8, r12; unsigned int
0x18005f069  mov     edx, 0C4h; void *
0x18005f06e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005f073  mov     eax, cs:dword_18013A120
0x18005f079  cmp     eax, 5
0x18005f07c  jbe     short loc_18005F0B7
0x18005f07e  mov     dword ptr [rbp+57h+var_70], ebx
0x18005f081  lea     rax, aMakeandinitial; "MakeAndInitialize(NlmEventSink)"
0x18005f088  mov     qword ptr [rbp+57h+var_78], rax
0x18005f08c  mov     qword ptr [rbp+57h+var_80], r12
0x18005f090  lea     rax, [rbp+57h+var_70]
0x18005f094  mov     [rsp+0C0h+var_90], rax
0x18005f099  lea     rax, [rbp+57h+var_78]
0x18005f09d  mov     [rsp+0C0h+var_98], rax
0x18005f0a2  lea     rax, [rbp+57h+var_80]
0x18005f0a6  mov     [rsp+0C0h+ppv], rax; int
0x18005f0ab  lea     rdx, byte_18011F09B
0x18005f0b2  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005f0b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f0be  lea     rax, WPP_GLOBAL_Control
0x18005f0c5  cmp     rcx, rax
0x18005f0c8  jz      short loc_18005F0EE
0x18005f0ca  cmp     byte ptr [rcx+19h], 4
0x18005f0ce  jb      short loc_18005F0EE
0x18005f0d0  test    byte ptr [rcx+1Ch], 1
0x18005f0d4  jz      short loc_18005F0EE
0x18005f0d6  mov     edx, 0Dh
0x18005f0db  mov     r9d, ebx
0x18005f0de  lea     r8, WPP_27fc5881657a3a5d8e63e8dc45cbf9d3_Traceguids
0x18005f0e5  mov     rcx, [rcx+10h]
0x18005f0e9  call    WPP_SF_d
0x18005f0ee  test    ebx, ebx
0x18005f0f0  js      loc_18005F2D5
0x18005f0f6  mov     [rbp+57h+var_58], rsi
0x18005f0fa  lea     rax, [rbp+57h+var_38]
0x18005f0fe  mov     [rbp+57h+var_50], rax
0x18005f102  lea     rax, [rbp+57h+var_30]
0x18005f106  mov     [rbp+57h+var_48], rax
0x18005f10a  lea     rcx, [rbp+57h+var_58]
0x18005f10e  call    wil__ResultFromException__NlmManager__InitializeCOM____37____lambda_1___
0x18005f113  mov     ebx, eax
0x18005f115  mov     rcx, [rbp+5Fh]; this
0x18005f119  test    eax, eax
0x18005f11b  jns     short loc_18005F12D
0x18005f11d  mov     r9d, eax; char *
0x18005f120  mov     r8, r12; unsigned int
0x18005f123  mov     edx, 0CEh; void *
0x18005f128  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005f12d  mov     eax, cs:dword_18013A120
0x18005f133  cmp     eax, 5
0x18005f136  jbe     short loc_18005F171
0x18005f138  mov     dword ptr [rbp+57h+var_70], ebx
0x18005f13b  lea     rax, aAdviseInotifyn; "Advise(INotifyNetworkListManagerEventsP"...
0x18005f142  mov     qword ptr [rbp+57h+var_78], rax
0x18005f146  mov     qword ptr [rbp+57h+var_80], r12
0x18005f14a  lea     rax, [rbp+57h+var_70]
0x18005f14e  mov     [rsp+0C0h+var_90], rax
0x18005f153  lea     rax, [rbp+57h+var_78]
0x18005f157  mov     [rsp+0C0h+var_98], rax
0x18005f15c  lea     rax, [rbp+57h+var_80]
0x18005f160  mov     [rsp+0C0h+ppv], rax; int
0x18005f165  lea     rdx, byte_18011F05F
0x18005f16c  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005f171  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f178  lea     rax, WPP_GLOBAL_Control
0x18005f17f  cmp     rcx, rax
0x18005f182  jz      short loc_18005F1A8
0x18005f184  cmp     byte ptr [rcx+19h], 4
0x18005f188  jb      short loc_18005F1A8
0x18005f18a  test    byte ptr [rcx+1Ch], 1
0x18005f18e  jz      short loc_18005F1A8
0x18005f190  mov     edx, 0Eh
0x18005f195  mov     r9d, ebx
0x18005f198  lea     r8, WPP_27fc5881657a3a5d8e63e8dc45cbf9d3_Traceguids
0x18005f19f  mov     rcx, [rcx+10h]
0x18005f1a3  call    WPP_SF_d
0x18005f1a8  test    ebx, ebx
0x18005f1aa  js      loc_18005F2D5
0x18005f1b0  mov     [rbp+57h+var_58], rsi
0x18005f1b4  lea     rax, [rbp+57h+var_38]
0x18005f1b8  mov     [rbp+57h+var_50], rax
0x18005f1bc  lea     rax, [rbp+57h+var_30]
0x18005f1c0  mov     [rbp+57h+var_48], rax
0x18005f1c4  lea     rcx, [rbp+57h+var_58]
0x18005f1c8  call    wil__ResultFromException__NlmManager__InitializeCOM____45____lambda_2___
0x18005f1cd  mov     ebx, eax
0x18005f1cf  mov     rcx, [rbp+5Fh]; this
0x18005f1d3  test    eax, eax
0x18005f1d5  jns     short loc_18005F1E7
0x18005f1d7  mov     r9d, eax; char *
0x18005f1da  mov     r8, r12; unsigned int
0x18005f1dd  mov     edx, 0D8h; void *
0x18005f1e2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005f1e7  mov     eax, cs:dword_18013A120
0x18005f1ed  cmp     eax, 5
0x18005f1f0  jbe     short loc_18005F22B
0x18005f1f2  mov     dword ptr [rbp+57h+var_70], ebx
0x18005f1f5  lea     rax, aAdviseInotifyn_0; "Advise(INotifyNetworkInterfaceEventsPri"...
0x18005f1fc  mov     qword ptr [rbp+57h+var_78], rax
0x18005f200  mov     qword ptr [rbp+57h+var_80], r12
0x18005f204  lea     rax, [rbp+57h+var_70]
0x18005f208  mov     [rsp+0C0h+var_90], rax
0x18005f20d  lea     rax, [rbp+57h+var_78]
0x18005f211  mov     [rsp+0C0h+var_98], rax
0x18005f216  lea     rax, [rbp+57h+var_80]
0x18005f21a  mov     [rsp+0C0h+ppv], rax
0x18005f21f  lea     rdx, byte_18011F1A3
0x18005f226  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005f22b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f232  lea     rax, WPP_GLOBAL_Control
0x18005f239  cmp     rcx, rax
0x18005f23c  jz      short loc_18005F262
0x18005f23e  cmp     byte ptr [rcx+19h], 4
0x18005f242  jb      short loc_18005F262
0x18005f244  test    byte ptr [rcx+1Ch], 1
0x18005f248  jz      short loc_18005F262
0x18005f24a  mov     edx, 0Fh
0x18005f24f  mov     r9d, ebx
0x18005f252  lea     r8, WPP_27fc5881657a3a5d8e63e8dc45cbf9d3_Traceguids
0x18005f259  mov     rcx, [rcx+10h]
0x18005f25d  call    WPP_SF_d
0x18005f262  test    ebx, ebx
0x18005f264  js      short loc_18005F2D5
0x18005f266  mov     rcx, [rbp+57h+var_38]
0x18005f26a  mov     rbx, [rdi]
0x18005f26d  mov     [rdi], rcx
0x18005f270  test    rcx, rcx
0x18005f273  jz      short loc_18005F281
0x18005f275  mov     rax, [rcx]
0x18005f278  mov     rax, [rax+8]
0x18005f27c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f281  test    rbx, rbx
0x18005f284  jz      short loc_18005F296
0x18005f286  mov     rax, [rbx]
0x18005f289  mov     rcx, rbx
0x18005f28c  mov     rax, [rax+10h]
0x18005f290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f295  nop
0x18005f296  mov     eax, cs:dword_18013A120
0x18005f29c  cmp     eax, 5
0x18005f29f  jbe     short loc_18005F2CE
0x18005f2a1  lea     rax, aNlmmanagerInit_1; "NlmManager::InitializeCOM - created new"...
0x18005f2a8  mov     qword ptr [rbp+57h+var_78], rax
0x18005f2ac  mov     qword ptr [rbp+57h+var_80], r12
0x18005f2b0  lea     rax, [rbp+57h+var_78]
0x18005f2b4  mov     [rsp+0C0h+var_98], rax
0x18005f2b9  lea     rax, [rbp+57h+var_80]
0x18005f2bd  mov     [rsp+0C0h+ppv], rax
0x18005f2c2  lea     rdx, byte_18011F173
0x18005f2c9  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18005f2ce  call    ?IndicatePowerStatusChange@NlmManager@@SAXXZ; NlmManager::IndicatePowerStatusChange(void)
0x18005f2d3  jmp     short loc_18005F2EF
0x18005f2d5  mov     rdx, [rdi+10h]
0x18005f2d9  mov     rcx, [rdi+8]; this
0x18005f2dd  cmp     rcx, rdx
0x18005f2e0  jz      short loc_18005F2EF
0x18005f2e2  call    ??$_Destroy_range@V?$allocator@UAdviseInstance@AdviseHandler@COM@WcmCommon@@@std@@@std@@YAXPEAUAdviseInstance@AdviseHandler@COM@WcmCommon@@QEAU1234@AEAV?$allocator@UAdviseInstance@AdviseHandler@COM@WcmCommon@@@0@@Z; std::_Destroy_range<std::allocator<WcmCommon::COM::AdviseHandler::AdviseInstance>>(WcmCommon::COM::AdviseHandler::AdviseInstance *,WcmCommon::COM::AdviseHandler::AdviseInstance * const,std::allocator<WcmCommon::COM::AdviseHandler::AdviseInstance> &)
0x18005f2e7  mov     rax, [rdi+8]
0x18005f2eb  mov     [rdi+10h], rax
0x18005f2ef  lea     rcx, [rbp+57h+var_30]
0x18005f2f3  call    ??1?$com_ptr_t@UIEnumNetworkInterfacePrivate@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IEnumNetworkInterfacePrivate,wil::err_exception_policy>::~com_ptr_t<IEnumNetworkInterfacePrivate,wil::err_exception_policy>(void)
0x18005f2f8  nop
0x18005f2f9  lea     rcx, [rbp+57h+var_38]
0x18005f2fd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005f302  jmp     loc_18005F3E4
  ... truncated ...
```
