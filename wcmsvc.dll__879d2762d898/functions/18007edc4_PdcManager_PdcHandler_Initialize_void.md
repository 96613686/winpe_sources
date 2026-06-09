# PdcManager::PdcHandler::Initialize(void)

- ea: `0x18007edc4`
- end: `0x18007f113`
- name: `?Initialize@PdcHandler@PdcManager@@AEAAKXZ`
- size: `847`
- prototype: `unsigned int __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007ecbc`

## callees

- `0x180002e54`
- `0x180027250`
- `0x180027630`
- `0x18002ea80`
- `0x180032cdc`
- `0x18003322c`
- `0x180036f60`
- `0x180037064`
- `0x18003a08c`
- `0x180052d30`
- `0x1800538f8`
- `0x180061ddc`
- `0x1800622cc`
- `0x18006c86c`
- `0x18007edc4`
- `0x180084f50`
- `0x180092970`
- `0x18009e058`
- `0x18009f888`
- `0x18009fc6c`
- `0x1800a195c`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007f086`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007f086`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007eee9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007eee9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ef02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ef02`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18007ee14`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18007ee14`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18007ee78`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18007ee78`

## string_xrefs

- `0x18007eeb1`: `onecoreuap\net\wcm\service\base\server\sleepstudy.cpp`
- `0x18007ef1c`: `CreateEvent for Restricted Standby failed.`
- `0x18007ee2f`: `onecoreuap\net\wcm\service\base\server\pdchandler.cpp`
- `0x18007ee89`: `onecoreuap\net\wcm\service\base\server\pdchandler.cpp`
- `0x18007eec9`: `onecoreuap\net\wcm\service\base\server\pdchandler.cpp`

## pseudocode

```c
DWORD __fastcall PdcManager::PdcHandler::Initialize(HPOWERNOTIFY *pv)
{
  _QWORD *v2; // rbx
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v4; // r9
  DWORD v6; // eax
  int v7; // eax
  unsigned int v8; // ebx
  HANDLE EventW; // rax
  DWORD LastError; // eax
  int v11; // r8d
  int v12; // r9d
  DWORD v13; // ebx
  int started; // ebx
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  unsigned int v20; // [rsp+20h] [rbp-49h]
  int v21; // [rsp+20h] [rbp-49h]
  int v22; // [rsp+20h] [rbp-49h]
  int v23; // [rsp+28h] [rbp-41h]
  int v24; // [rsp+30h] [rbp-39h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+38h] [rbp-31h] BYREF
  _QWORD v26[7]; // [rsp+40h] [rbp-29h] BYREF
  _QWORD *v27; // [rsp+78h] [rbp+Fh]
  __int64 v28[2]; // [rsp+80h] [rbp+17h] BYREF
  _QWORD Recipient[2]; // [rsp+90h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  _InterlockedExchange(&dword_18013F8B0, -1);
  _InterlockedExchange(&dword_18013F8A8, -1);
  v2 = pv + 296;
  ThreadpoolTimer = CreateThreadpoolTimer(PdcManager::PdcHandler::GlobalPowerStateTimerCallback, pv, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    v2,
    ThreadpoolTimer);
  if ( !*v2 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x336,
             (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\pdchandler.cpp",
             v4);
  Recipient[0] = PdcManager::PdcHandler::DisplayStateNotificationCallback;
  Recipient[1] = pv;
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int UnregisterPowerSettingNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    pv + 297,
    0);
  v6 = PowerSettingRegisterNotification(&GUID_CONSOLE_DISPLAY_STATE, 2u, Recipient, pv + 297);
  if ( v6 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x33C,
             (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\pdchandler.cpp",
             (const char *)v6,
             v20);
  v7 = SleepStudy::Singleton::Initialize();
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x290,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\sleepstudy.cpp",
      (const char *)(unsigned int)v7,
      v20);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x33E,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\pdchandler.cpp",
      (const char *)v8,
      v21);
  }
  EventW = CreateEventW(0, 1, 0, 0);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    pv + 3,
    EventW);
  if ( pv[3] || (LastError = GetLastError(), (v13 = LastError) == 0) )
  {
    v26[0] = ___7___Func_impl_no_alloc_P6AXW4NotificationTypes_NsiNotifications__AEBT_NET_LUID_LH__PEBU_NDIS_NSI_INTERFACE_ENUM_ROD__PEBU_NDIS_NSI_INTERFACE_ENUM_ROS____EXW412_AEBT3_PEBU4_PEBU5__std__6B_;
    v26[1] = &PdcManager::PdcHandler::NsiAdapterEnumCallback;
    v27 = v26;
    if ( pv + 79 != v26 )
    {
      std::_Func_class<void,_SRU_STATS_RECORD_SET *>::_Tidy(pv + 79);
      if ( v27 )
      {
        if ( v27 == v26 )
        {
          pv[86] = (HPOWERNOTIFY)(*(__int64 (__fastcall **)(_QWORD *, char *))(*v27 + 8LL))(v27, (char *)pv + 632);
          std::_Func_class<void,_SRU_STATS_RECORD_SET *>::_Tidy(v26);
        }
        else
        {
          pv[86] = v27;
          v27 = 0;
        }
      }
    }
    *((_BYTE *)pv + 732) = 1;
    std::_Func_class<void,_SRU_STATS_RECORD_SET *>::_Tidy(v26);
    started = NsiNotifications::NotificationTracking::StartNotifications((NsiNotifications::NotificationTracking *)(pv + 29));
    if ( started < 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( (unsigned int)dword_18013A120 > 1 )
      {
        v24 = started;
        lpCriticalSection = (LPCRITICAL_SECTION)"NotificationTracking::StartNotifications failed.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          dword_18013A120,
          (unsigned int)&byte_18011726F,
          v15,
          v16,
          (__int64)&lpCriticalSection,
          (__int64)&v24);
      }
    }
    lpCriticalSection = 0;
    wil::EnterCriticalSection(&lpCriticalSection, pv + 4);
    *(_OWORD *)v28 = 0;
    v24 = 1;
    PdcManager::PdcHandler::ProcessNetQuietModeChange(
      (PdcManager::PdcHandler *)pv,
      (enum PdcManager::NetQuietModePowerState *)&v24,
      0,
      (__int64)v28);
    v24 = 1;
    LOBYTE(v23) = 0;
    LOBYTE(v22) = 0;
    ((void (__fastcall *)(HPOWERNOTIFY *, int *, __int64, _QWORD, int, int))PdcManager::PdcHandler::ProcessStandbyChange)(
      pv,
      &v24,
      1,
      0,
      v22,
      v23);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    InDisconnectedStandby(&v24);
    if ( (unsigned int)dword_18013A120 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013A120, 0x400000000000LL) )
    {
      lpCriticalSection = (LPCRITICAL_SECTION)2048;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
        v17,
        (int)byte_1801172A9,
        v18,
        v19,
        (__int64)&v24,
        (__int64)&lpCriticalSection);
    }
    return PdcManager::PdcHandler::Register((PdcManager::PdcHandler *)pv);
  }
  else
  {
    if ( (unsigned int)dword_18013A120 > 1 )
    {
      v24 = LastError;
      lpCriticalSection = (LPCRITICAL_SECTION)"CreateEvent for Restricted Standby failed.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_18013A120,
        (unsigned int)byte_1801172E9,
        v11,
        v12,
        (__int64)&lpCriticalSection,
        (__int64)&v24);
    }
    return v13;
  }
}

```

## disassembly

```asm
0x18007edc4  mov     [rsp-8+arg_8], rbx
0x18007edc9  mov     [rsp-8+arg_10], rsi
0x18007edce  push    rbp
0x18007edcf  push    rdi
0x18007edd0  push    r15
0x18007edd2  lea     rbp, [rsp-47h]
0x18007edd7  sub     rsp, 0B0h
0x18007edde  mov     rax, cs:__security_cookie
0x18007ede5  xor     rax, rsp
0x18007ede8  mov     [rbp+57h+var_20], rax
0x18007edec  mov     rdi, rcx
0x18007edef  or      ecx, 0FFFFFFFFh
0x18007edf2  mov     eax, ecx
0x18007edf4  xchg    eax, cs:dword_18013F8B0
0x18007edfa  xchg    ecx, cs:dword_18013F8A8
0x18007ee00  lea     rbx, [rdi+940h]
0x18007ee07  xor     r8d, r8d; pcbe
0x18007ee0a  mov     rdx, rdi; pv
0x18007ee0d  lea     rcx, ?GlobalPowerStateTimerCallback@PdcHandler@PdcManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18007ee14  call    cs:__imp_CreateThreadpoolTimer
0x18007ee1a  mov     rdx, rax
0x18007ee1d  mov     rcx, rbx
0x18007ee20  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18007ee25  cmp     qword ptr [rbx], 0
0x18007ee29  jnz     short loc_18007EE45
0x18007ee2b  mov     rcx, [rbp+5Fh]; this
0x18007ee2f  lea     r8, aOnecoreuapNetW_14; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18007ee36  mov     edx, 336h; void *
0x18007ee3b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007ee40  jmp     loc_18007F0EF
0x18007ee45  lea     rax, ?DisplayStateNotificationCallback@PdcHandler@PdcManager@@CAKPEAXK0@Z; PdcManager::PdcHandler::DisplayStateNotificationCallback(void *,ulong,void *)
0x18007ee4c  mov     [rbp+57h+Recipient], rax
0x18007ee50  mov     [rbp+57h+var_28], rdi
0x18007ee54  lea     rbx, [rdi+948h]
0x18007ee5b  xor     edx, edx
0x18007ee5d  mov     rcx, rbx
0x18007ee60  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?UnregisterPowerSettingNotification@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&UnregisterPowerSettingNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18007ee65  mov     r9, rbx; RegistrationHandle
0x18007ee68  lea     r8, [rbp+57h+Recipient]; Recipient
0x18007ee6c  mov     edx, 2; Flags
0x18007ee71  lea     rcx, GUID_CONSOLE_DISPLAY_STATE; SettingGuid
0x18007ee78  call    cs:__imp_PowerSettingRegisterNotification
0x18007ee7e  test    eax, eax
0x18007ee80  jz      short loc_18007EE9F
0x18007ee82  mov     rcx, [rbp+5Fh]; this
0x18007ee86  mov     r9d, eax; char *
0x18007ee89  lea     r8, aOnecoreuapNetW_14; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18007ee90  mov     edx, 33Ch; void *
0x18007ee95  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007ee9a  jmp     loc_18007F0EF
0x18007ee9f  call    ?Initialize@Singleton@SleepStudy@@SAJXZ; SleepStudy::Singleton::Initialize(void)
0x18007eea4  mov     ebx, eax
0x18007eea6  test    eax, eax
0x18007eea8  jns     short loc_18007EEDA
0x18007eeaa  mov     rcx, [rbp+5Fh]; this
0x18007eeae  mov     r9d, eax; char *
0x18007eeb1  lea     r8, aOnecoreuapNetW_22; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18007eeb8  mov     edx, 290h; void *
0x18007eebd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007eec2  mov     rcx, [rbp+5Fh]; this
0x18007eec6  mov     r9d, ebx; char *
0x18007eec9  lea     r8, aOnecoreuapNetW_14; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18007eed0  mov     edx, 33Eh; void *
0x18007eed5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007eeda  xor     r9d, r9d; lpName
0x18007eedd  xor     r8d, r8d; bInitialState
0x18007eee0  lea     r15d, [r9+1]
0x18007eee4  mov     edx, r15d; bManualReset
0x18007eee7  xor     ecx, ecx; lpEventAttributes
0x18007eee9  call    cs:__imp_CreateEventW
0x18007eeef  mov     rdx, rax
0x18007eef2  lea     rcx, [rdi+18h]
0x18007eef6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18007eefb  cmp     qword ptr [rdi+18h], 0
0x18007ef00  jnz     short loc_18007EF4C
0x18007ef02  call    cs:__imp_GetLastError
0x18007ef08  mov     ebx, eax
0x18007ef0a  test    eax, eax
0x18007ef0c  jz      short loc_18007EF4C
0x18007ef0e  mov     ecx, cs:dword_18013A120
0x18007ef14  cmp     ecx, r15d
0x18007ef17  jbe     short loc_18007EF45
0x18007ef19  mov     [rbp+57h+var_90], eax
0x18007ef1c  lea     rax, aCreateeventFor; "CreateEvent for Restricted Standby fail"...
0x18007ef23  mov     [rbp+57h+lpCriticalSection], rax
0x18007ef27  lea     rax, [rbp+57h+var_90]
0x18007ef2b  mov     [rsp+0C0h+var_98], rax
0x18007ef30  lea     rax, [rbp+57h+lpCriticalSection]
0x18007ef34  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18007ef39  lea     rdx, byte_1801172E9
0x18007ef40  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007ef45  mov     eax, ebx
0x18007ef47  jmp     loc_18007F0EF
0x18007ef4c  lea     rax, ??_7?$_Func_impl_no_alloc@P6AXW4NotificationTypes@NsiNotifications@@AEBT_NET_LUID_LH@@PEBU_NDIS_NSI_INTERFACE_ENUM_ROD@@PEBU_NDIS_NSI_INTERFACE_ENUM_ROS@@@_EXW412@AEBT3@PEBU4@PEBU5@@std@@6B@
0x18007ef53  mov     [rbp+57h+var_80], rax
0x18007ef57  lea     rax, ?NsiAdapterEnumCallback@PdcHandler@PdcManager@@CAXW4NotificationTypes@NsiNotifications@@AEBT_NET_LUID_LH@@PEBU_NDIS_NSI_INTERFACE_ENUM_ROD@@PEBU_NDIS_NSI_INTERFACE_ENUM_ROS@@@Z; PdcManager::PdcHandler::NsiAdapterEnumCallback(NsiNotifications::NotificationTypes,_NET_LUID_LH const &,_NDIS_NSI_INTERFACE_ENUM_ROD const *,_NDIS_NSI_INTERFACE_ENUM_ROS const *)
0x18007ef5e  mov     [rbp+57h+var_78], rax
0x18007ef62  lea     rax, [rbp+57h+var_80]
0x18007ef66  mov     [rbp+57h+var_48], rax
0x18007ef6a  lea     rbx, [rdi+278h]
0x18007ef71  lea     rax, [rbp+57h+var_80]
0x18007ef75  cmp     rbx, rax
0x18007ef78  jz      short loc_18007EFBE
0x18007ef7a  mov     rcx, rbx
0x18007ef7d  call    ?_Tidy@?$_Func_class@XPEAU_SRU_STATS_RECORD_SET@@@std@@IEAAXXZ; std::_Func_class<void,_SRU_STATS_RECORD_SET *>::_Tidy(void)
0x18007ef82  mov     rcx, [rbp+57h+var_48]
0x18007ef86  test    rcx, rcx
0x18007ef89  jz      short loc_18007EFBE
0x18007ef8b  lea     rax, [rbp+57h+var_80]
0x18007ef8f  cmp     rcx, rax
0x18007ef92  jnz     short loc_18007EFB2
0x18007ef94  mov     rax, [rcx]
0x18007ef97  mov     rdx, rbx
0x18007ef9a  mov     rax, [rax+8]
0x18007ef9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007efa3  mov     [rbx+38h], rax
0x18007efa7  lea     rcx, [rbp+57h+var_80]
0x18007efab  call    ?_Tidy@?$_Func_class@XPEAU_SRU_STATS_RECORD_SET@@@std@@IEAAXXZ; std::_Func_class<void,_SRU_STATS_RECORD_SET *>::_Tidy(void)
0x18007efb0  jmp     short loc_18007EFBE
0x18007efb2  mov     [rbx+38h], rcx
0x18007efb6  mov     [rbp+57h+var_48], 0
0x18007efbe  mov     [rdi+2DCh], r15b
0x18007efc5  lea     rcx, [rbp+57h+var_80]
0x18007efc9  call    ?_Tidy@?$_Func_class@XPEAU_SRU_STATS_RECORD_SET@@@std@@IEAAXXZ; std::_Func_class<void,_SRU_STATS_RECORD_SET *>::_Tidy(void)
0x18007efce  lea     rcx, [rdi+0E8h]; this
0x18007efd5  call    ?StartNotifications@NotificationTracking@NsiNotifications@@QEAAJXZ; NsiNotifications::NotificationTracking::StartNotifications(void)
0x18007efda  mov     ebx, eax
0x18007efdc  test    eax, eax
0x18007efde  jns     short loc_18007F01C
0x18007efe0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007efe5  mov     ecx, cs:dword_18013A120
0x18007efeb  cmp     ecx, r15d
0x18007efee  jbe     short loc_18007F01C
0x18007eff0  mov     [rbp+57h+var_90], ebx
0x18007eff3  lea     rax, aNotificationtr; "NotificationTracking::StartNotification"...
0x18007effa  mov     [rbp+57h+lpCriticalSection], rax
0x18007effe  lea     rax, [rbp+57h+var_90]
0x18007f002  mov     [rsp+0C0h+var_98], rax
0x18007f007  lea     rax, [rbp+57h+lpCriticalSection]
0x18007f00b  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18007f010  lea     rdx, byte_18011726F
0x18007f017  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007f01c  mov     [rbp+57h+lpCriticalSection], 0
0x18007f024  lea     rdx, [rdi+20h]
0x18007f028  lea     rcx, [rbp+57h+lpCriticalSection]
0x18007f02c  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18007f031  xorps   xmm0, xmm0
0x18007f034  movdqu  xmmword ptr [rbp+57h+var_40], xmm0
0x18007f039  mov     [rbp+57h+var_90], r15d
0x18007f03d  lea     rax, [rbp+57h+var_40]
0x18007f041  mov     [rsp+0C0h+var_98], rax; __int64
0x18007f046  mov     [rsp+0C0h+var_A0], 0; char
0x18007f04b  xor     r9d, r9d
0x18007f04e  mov     r8d, r15d
0x18007f051  lea     rdx, [rbp+57h+var_90]; enum PdcManager::NetQuietModePowerState *
0x18007f055  mov     rcx, rdi; this
0x18007f058  call    ?ProcessNetQuietModeChange@PdcHandler@PdcManager@@AEAAKAEBW4NetQuietModePowerState@2@W4PowerChangeSource@2@W4NetQuietModeRestrictedStandbyFlag@2@_NV?$shared_ptr@UPowerRef@PdcHandler@PdcManager@@@std@@@Z; PdcManager::PdcHandler::ProcessNetQuietModeChange(PdcManager::NetQuietModePowerState const &,PdcManager::PowerChangeSource,PdcManager::NetQuietModeRestrictedStandbyFlag,bool,std::shared_ptr<PdcManager::PdcHandler::PowerRef>)
0x18007f05d  mov     [rbp+57h+var_90], r15d
0x18007f061  mov     byte ptr [rsp+0C0h+var_98], 0
0x18007f066  mov     [rsp+0C0h+var_A0], 0
0x18007f06b  xor     r9d, r9d
0x18007f06e  mov     r8d, r15d
0x18007f071  lea     rdx, [rbp+57h+var_90]
0x18007f075  mov     rcx, rdi
0x18007f078  call    ?ProcessStandbyChange@PdcHandler@PdcManager@@AEAAXAEBW4StandbyPowerState@2@W4PowerChangeSource@2@_N22@Z; PdcManager::PdcHandler::ProcessStandbyChange(PdcManager::StandbyPowerState const &,PdcManager::PowerChangeSource,bool,bool,bool)
0x18007f07d  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x18007f081  test    rcx, rcx
0x18007f084  jz      short loc_18007F08C
0x18007f086  call    cs:__imp_LeaveCriticalSection
0x18007f08c  lea     rcx, [rbp+57h+var_90]
0x18007f090  call    InDisconnectedStandby
0x18007f095  mov     eax, cs:dword_18013A120
0x18007f09b  cmp     eax, 5
0x18007f09e  jbe     short loc_18007F0E6
0x18007f0a0  mov     rdx, 400000000000h
0x18007f0aa  lea     rcx, dword_18013A120
0x18007f0b1  call    _tlgKeywordOn
0x18007f0b6  test    al, al
0x18007f0b8  jz      short loc_18007F0E6
0x18007f0ba  mov     [rbp+57h+lpCriticalSection], 800h
0x18007f0c2  mov     al, byte ptr [rbp+57h+var_90]
0x18007f0c5  mov     byte ptr [rbp+57h+var_90], al
0x18007f0c8  lea     rax, [rbp+57h+lpCriticalSection]
0x18007f0cc  mov     [rsp+0C0h+var_98], rax
0x18007f0d1  lea     rax, [rbp+57h+var_90]
0x18007f0d5  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18007f0da  lea     rdx, byte_1801172A9
0x18007f0e1  call    ??$Write@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x18007f0e6  mov     rcx, rdi; this
0x18007f0e9  call    ?Register@PdcHandler@PdcManager@@AEAAKXZ; PdcManager::PdcHandler::Register(void)
0x18007f0ee  nop
0x18007f0ef  mov     rcx, [rbp+57h+var_20]
0x18007f0f3  xor     rcx, rsp; StackCookie
0x18007f0f6  call    __security_check_cookie
0x18007f0fb  lea     r11, [rsp+0C0h+var_10]
0x18007f103  mov     rbx, [r11+28h]
0x18007f107  mov     rsi, [r11+30h]
0x18007f10b  mov     rsp, r11
0x18007f10e  pop     r15
0x18007f110  pop     rdi
0x18007f111  pop     rbp
0x18007f112  retn
```
