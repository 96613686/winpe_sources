# Microsoft::Diagnostics::SettingsManager::SettingsManager(Microsoft::Diagnostics::SettingsManagerConfig &)

- ea: `0x18018be10`
- end: `0x18018c831`
- name: `??0SettingsManager@Diagnostics@Microsoft@@QEAA@AEAUSettingsManagerConfig@12@@Z`
- size: `2593`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::SettingsManager *__hidden this, struct Microsoft::Diagnostics::SettingsManagerConfig *)`
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006de38`

## callees

- `0x180001bf4`
- `0x1800035ec`
- `0x18001be18`
- `0x18001cd34`
- `0x18001d160`
- `0x180020fbc`
- `0x1800277e8`
- `0x180027be0`
- `0x180035698`
- `0x18004ab70`
- `0x1800551b0`
- `0x18005af1c`
- `0x18005d050`
- `0x180080054`
- `0x180089c54`
- `0x180093f0c`
- `0x18009d380`
- `0x1800b83bc`
- `0x1800c2220`
- `0x1800d0d9c`
- `0x1800df6f0`
- `0x1800ef644`
- `0x18012de40`
- `0x18016ff48`
- `0x180188c3c`
- `0x18018b8c8`
- `0x18018b8e8`
- `0x18018be10`
- `0x18018ea94`
- `0x1801917b4`
- `0x180191b1c`
- `0x180198228`
- `0x1801bbc9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018c69e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018c78f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018c69e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018c78f`
- `api-ms-win-oobe-notification-l1-1-0!RegisterWaitUntilOOBECompleted` at `0x18018c712`
- `api-ms-win-oobe-notification-l1-1-0!RegisterWaitUntilOOBECompleted` at `0x18018c712`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x18018c666`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x18018c666`
- `api-ms-win-oobe-notification-l1-1-0!UnregisterWaitUntilOOBECompleted` at `0x18018c6e1`

## string_xrefs

- `0x18018c55e`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
Microsoft::Diagnostics::SettingsManager *__fastcall Microsoft::Diagnostics::SettingsManager::SettingsManager(
        char **this,
        struct Microsoft::Diagnostics::SettingsManagerConfig *a2)
{
  char *v4; // rax
  _QWORD *v5; // rax
  _QWORD *v6; // rsi
  __int64 v7; // rax
  int PreviouslyRegisteredSettingsEndpoints; // eax
  Microsoft::Diagnostics::SettingsManager *v9; // rcx
  signed int LastError; // eax
  int v11; // r8d
  int v12; // r9d
  void *v13; // rdx
  int v15; // [rsp+20h] [rbp-99h]
  __int128 v16; // [rsp+70h] [rbp-49h] BYREF
  __int128 v17; // [rsp+80h] [rbp-39h] BYREF
  __int128 v18; // [rsp+90h] [rbp-29h] BYREF
  int v19; // [rsp+A0h] [rbp-19h] BYREF
  int v20; // [rsp+A4h] [rbp-15h] BYREF
  int v21; // [rsp+A8h] [rbp-11h] BYREF
  Microsoft::Diagnostics::SettingsManager *v22; // [rsp+B0h] [rbp-9h] BYREF
  _BYTE v23[32]; // [rsp+B8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v22 = (Microsoft::Diagnostics::SettingsManager *)this;
  *this = (char *)&Microsoft::Diagnostics::SettingsManager::`vftable';
  this[1] = 0;
  this[2] = 0;
  v4 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(0x38u);
  *(_QWORD *)v4 = v4;
  *((_QWORD *)v4 + 1) = v4;
  this[1] = v4;
  std::map<std::wstring,std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::pair<std::wstring const,std::wstring>>>::map<std::wstring,std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::pair<std::wstring const,std::wstring>>>(this + 3);
  this[5] = 0;
  this[6] = 0;
  v5 = std::_Allocate<16,std::_Default_allocate_traits>(0x40u);
  *v5 = v5;
  v5[1] = v5;
  v5[2] = v5;
  *((_WORD *)v5 + 12) = 257;
  this[5] = (char *)v5;
  this[7] = 0;
  this[8] = 0;
  this[7] = (char *)std::_Tree_node<std::pair<std::wstring const,unsigned __int64>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<std::wstring const,unsigned __int64>,void *>>>();
  this[9] = (char *)258;
  *((_OWORD *)this + 6) = 0;
  *((_OWORD *)this + 7) = 0;
  *((_OWORD *)this + 8) = 0;
  this[10] = 0;
  this[11] = 0;
  *((_DWORD *)this + 36) = -1;
  *((_DWORD *)this + 37) = 0;
  this[19] = (char *)258;
  *((_OWORD *)this + 11) = 0;
  *((_OWORD *)this + 12) = 0;
  *((_OWORD *)this + 13) = 0;
  this[20] = 0;
  this[21] = 0;
  *((_DWORD *)this + 56) = -1;
  *((_DWORD *)this + 57) = 0;
  this[29] = (char *)258;
  *((_OWORD *)this + 16) = 0;
  *((_OWORD *)this + 17) = 0;
  *((_OWORD *)this + 18) = 0;
  this[30] = 0;
  this[31] = 0;
  *((_DWORD *)this + 76) = -1;
  *((_DWORD *)this + 77) = 0;
  this[39] = (char *)258;
  *((_OWORD *)this + 21) = 0;
  *((_OWORD *)this + 22) = 0;
  *((_OWORD *)this + 23) = 0;
  this[40] = 0;
  this[41] = 0;
  *((_DWORD *)this + 96) = -1;
  *((_DWORD *)this + 97) = 0;
  std::wstring::wstring(this + 49);
  std::wstring::wstring(this + 53);
  *((_DWORD *)this + 114) = 3;
  std::wstring::wstring(this + 58);
  std::wstring::wstring(this + 62);
  this[66] = (char *)Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL();
  this[67] = (char *)Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL();
  *((_DWORD *)this + 136) = 10080;
  *((_DWORD *)this + 137) = 5760;
  v16 = *(_OWORD *)&Microsoft::Diagnostics::SettingsManager::k_msaTicketPolicy;
  v17 = *(_OWORD *)&Microsoft::Diagnostics::SettingsDownloader::k_settingsV3UrlPrefix;
  Microsoft::Diagnostics::DeviceTicket::DeviceTicket(
    this + 69,
    &v17,
    &v16,
    &Microsoft::Diagnostics::SettingsManager::k_utcApplicationGuid);
  this[79] = (char *)258;
  *((_OWORD *)this + 41) = 0;
  *((_OWORD *)this + 42) = 0;
  *((_OWORD *)this + 43) = 0;
  this[80] = 0;
  this[81] = 0;
  this[88] = (char *)0xFFFFFFFFLL;
  this[89] = (char *)258;
  *((_OWORD *)this + 46) = 0;
  *((_OWORD *)this + 47) = 0;
  *((_OWORD *)this + 48) = 0;
  this[90] = 0;
  this[91] = 0;
  *((_DWORD *)this + 196) = -1;
  *((_DWORD *)this + 197) = 0;
  std::unordered_map<std::wstring,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>,Microsoft::Diagnostics::Utils::Hash::CaseInsensitiveHashPredicate,Microsoft::Diagnostics::Utils::String::CaseInsensitiveEqualToPredicate,std::allocator<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>>>>::unordered_map<std::wstring,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>,Microsoft::Diagnostics::Utils::Hash::CaseInsensitiveHashPredicate,Microsoft::Diagnostics::Utils::String::CaseInsensitiveEqualToPredicate,std::allocator<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>>>>(this + 99);
  std::unordered_map<std::wstring,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>,Microsoft::Diagnostics::Utils::Hash::CaseInsensitiveHashPredicate,Microsoft::Diagnostics::Utils::String::CaseInsensitiveEqualToPredicate,std::allocator<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>>>>::unordered_map<std::wstring,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>,Microsoft::Diagnostics::Utils::Hash::CaseInsensitiveHashPredicate,Microsoft::Diagnostics::Utils::String::CaseInsensitiveEqualToPredicate,std::allocator<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>>>>(this + 107);
  this[115] = 0;
  this[116] = 0;
  this[117] = 0;
  this[118] = 0;
  this[119] = 0;
  this[120] = 0;
  v6 = this + 121;
  this[121] = 0;
  *((_BYTE *)this + 976) = 1;
  Microsoft::Diagnostics::TpSerialWork::TpSerialWork(this + 123);
  this[138] = 0;
  *((_DWORD *)this + 278) = 900000;
  *((_DWORD *)this + 279) = 15;
  std::wstring::wstring((__int64)(this + 140), &off_18035F2E0);
  std::set<std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::wstring>>::set<std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::wstring>>(this + 144);
  std::set<std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::wstring>>::set<std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::wstring>>(this + 146);
  std::wstring::wstring(this + 148);
  *((_BYTE *)this + 1216) = *((_BYTE *)a2 + 1);
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (_DWORD)this + 1104,
    1,
    0,
    0,
    0);
  if ( !*((_BYTE *)a2 + 2) )
  {
    std::wstring::wstring(v23);
    v16 = *(_OWORD *)&off_18035F2D0;
    if ( (unsigned __int8)Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(&v16, v23) )
    {
      v7 = std::wstring::operator std::wstring_view(v23, &v16);
      std::wstring::_Assign<wchar_t>(this + 69, *(const void **)v7, *(char **)(v7 + 8));
    }
    v16 = 0;
    *(_QWORD *)&v17 = L"app";
    *((_QWORD *)&v17 + 1) = 3;
    *(_QWORD *)&v18 = L"utc";
    *((_QWORD *)&v18 + 1) = 3;
    Microsoft::Diagnostics::SettingsManager::RegisterSettingsEndpoint(
      (_DWORD)this,
      (unsigned int)&v18,
      (unsigned int)&v17,
      1,
      1,
      0,
      0,
      0,
      0,
      (__int64)&v16);
    v16 = 0;
    *(_QWORD *)&v17 = L"ASM-WindowsDefault";
    *((_QWORD *)&v17 + 1) = 18;
    *(_QWORD *)&v18 = L"telemetry";
    *((_QWORD *)&v18 + 1) = 9;
    Microsoft::Diagnostics::SettingsManager::RegisterSettingsEndpoint(
      (_DWORD)this,
      (unsigned int)&v18,
      (unsigned int)&v17,
      1,
      1,
      0,
      0,
      0,
      0,
      (__int64)&v16);
    v16 = 0;
    *(_QWORD *)&v17 = L"cert";
    *((_QWORD *)&v17 + 1) = 4;
    *(_QWORD *)&v18 = L"utc";
    *((_QWORD *)&v18 + 1) = 3;
    Microsoft::Diagnostics::SettingsManager::RegisterSettingsEndpoint(
      (_DWORD)this,
      (unsigned int)&v18,
      (unsigned int)&v17,
      1,
      2,
      0,
      0,
      0,
      0,
      (__int64)&v16);
    *(_QWORD *)&v17 = &Src;
    *((_QWORD *)&v17 + 1) = 0;
    *(_QWORD *)&v18 = L"privacy";
    *((_QWORD *)&v18 + 1) = 7;
    *(_QWORD *)&v16 = L"utc";
    *((_QWORD *)&v16 + 1) = 3;
    Microsoft::Diagnostics::SettingsManager::RegisterSettingsEndpoint(
      (_DWORD)this,
      (unsigned int)&v16,
      (unsigned int)&v18,
      1,
      2,
      0,
      1,
      1,
      0,
      (__int64)&v17);
    *(_QWORD *)&v16 = &Src;
    *((_QWORD *)&v16 + 1) = 0;
    *(_QWORD *)&v17 = L"allow";
    *((_QWORD *)&v17 + 1) = 5;
    *(_QWORD *)&v18 = L"utc";
    *((_QWORD *)&v18 + 1) = 3;
    Microsoft::Diagnostics::SettingsManager::RegisterSettingsEndpoint(
      (_DWORD)this,
      (unsigned int)&v18,
      (unsigned int)&v17,
      1,
      2,
      0,
      1,
      0,
      0,
      (__int64)&v16);
    *(_QWORD *)&v16 = &Src;
    *((_QWORD *)&v16 + 1) = 0;
    *(_QWORD *)&v17 = L"aggregators";
    *((_QWORD *)&v17 + 1) = 11;
    *(_QWORD *)&v18 = L"utc";
    *((_QWORD *)&v18 + 1) = 3;
    Microsoft::Diagnostics::SettingsManager::RegisterSettingsEndpoint(
      (_DWORD)this,
      (unsigned int)&v18,
      (unsigned int)&v17,
      1,
      2,
      0,
      2,
      0,
      0,
      (__int64)&v16);
    v18 = 0;
    *(_QWORD *)&v16 = L"P-Eco3PTelDefault";
    *((_QWORD *)&v16 + 1) = 17;
    *(_QWORD *)&v17 = L"telemetry";
    *((_QWORD *)&v17 + 1) = 9;
    Microsoft::Diagnostics::SettingsManager::RegisterSettingsEndpoint(
      (_DWORD)this,
      (unsigned int)&v17,
      (unsigned int)&v16,
      1,
      2,
      0,
      0,
      0,
      0,
      (__int64)&v18);
    PreviouslyRegisteredSettingsEndpoints = Microsoft::Diagnostics::SettingsManager::LoadPreviouslyRegisteredSettingsEndpoints(
                                              (Microsoft::Diagnostics::SettingsManager *)this,
                                              *((_BYTE *)a2 + 3));
    if ( PreviouslyRegisteredSettingsEndpoints < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
        (const char *)(unsigned int)PreviouslyRegisteredSettingsEndpoints,
        v15);
    Microsoft::Diagnostics::SettingsManager::LoadPersistedTelemetryFeatures((Microsoft::Diagnostics::SettingsManager *)this);
    Microsoft::Diagnostics::SettingsManager::RegisterConditionalEndpoints((Microsoft::Diagnostics::SettingsManager *)this);
    Microsoft::Diagnostics::SettingsManager::CopyDefinedInboxSettingsToMutableDirectory(v9);
    if ( *(_BYTE *)a2 )
      Microsoft::Diagnostics::SettingsManager::RefreshFromDisk((Microsoft::Diagnostics::SettingsManager *)this);
    *(_QWORD *)&v16 = L"SettingsExpirationMinutes";
    *((_QWORD *)&v16 + 1) = 25;
    Microsoft::Diagnostics::SettingsManager::GetSetting(this, &v16, this + 68);
    *(_QWORD *)&v16 = L"SettingsPendingExpirationMinutes";
    *((_QWORD *)&v16 + 1) = 32;
    Microsoft::Diagnostics::SettingsManager::GetSetting(this, &v16, (char *)this + 548);
    v19 = 0;
    v16 = *(_OWORD *)&off_18035F2C0;
    v17 = *(_OWORD *)&off_18035F2B0;
    if ( (int)Microsoft::Diagnostics::Utils::Registry::GetDword(-2147483646, &v17, &v16, &v19) >= 0 )
      *((_DWORD *)this + 136) = v19;
    v20 = 0;
    v16 = *(_OWORD *)&off_18035F2A0;
    v17 = *(_OWORD *)&off_18035F2B0;
    if ( (int)Microsoft::Diagnostics::Utils::Registry::GetDword(-2147483646, &v17, &v16, &v20) >= 0 )
      *((_DWORD *)this + 137) = v20;
    v21 = 1;
    if ( (unsigned int)OOBEComplete(&v21) )
    {
      if ( v21 )
      {
        if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 512) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_18042D328,
            &unk_1803C43BA);
        goto LABEL_34;
      }
      if ( *v6 )
      {
        *(_QWORD *)&v18 = *v6;
        wil::last_error_context::last_error_context((wil::last_error_context *)&v22);
        *(_QWORD *)&v17 = UnregisterWaitUntilOOBECompleted;
        wistd::invoke<void * (*)(void *),void * &>(&v17, &v18);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v22);
      }
      *v6 = 0;
      if ( (unsigned int)RegisterWaitUntilOOBECompleted(
                           Microsoft::Diagnostics::SettingsManager::StaticOobeCompletedCallback,
                           this,
                           this + 121) )
      {
        *((_BYTE *)this + 976) = 0;
        if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 512) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_18042D328,
            &unk_1803C443A);
        goto LABEL_34;
      }
      if ( (unsigned int)dword_18042D328 <= 4 || !(unsigned __int8)tlgKeywordOn(&dword_18042D328, 512) )
      {
LABEL_34:
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v23);
        return (Microsoft::Diagnostics::SettingsManager *)this;
      }
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v13 = &unk_1803C43EF;
    }
    else
    {
      if ( (unsigned int)dword_18042D328 <= 4 || !(unsigned __int8)tlgKeywordOn(&dword_18042D328, 512) )
        goto LABEL_34;
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v13 = &unk_1803C4472;
    }
    LODWORD(v18) = LastError;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18042D328,
      (_DWORD)v13,
      v11,
      v12,
      (__int64)&v18);
    goto LABEL_34;
  }
  return (Microsoft::Diagnostics::SettingsManager *)this;
}

```

## disassembly

```asm
0x18018be10  mov     [rsp-8+arg_10], rbx
0x18018be15  push    rbp
0x18018be16  push    rsi
0x18018be17  push    rdi
0x18018be18  push    r12
0x18018be1a  push    r13
0x18018be1c  push    r14
0x18018be1e  push    r15
0x18018be20  lea     rbp, [rsp-27h]
0x18018be25  sub     rsp, 0E0h
0x18018be2c  mov     rax, cs:__security_cookie
0x18018be33  xor     rax, rsp
0x18018be36  mov     [rbp+57h+var_38], rax
0x18018be3a  mov     r14, rdx
0x18018be3d  mov     rdi, rcx
0x18018be40  mov     [rbp+57h+var_60], rcx
0x18018be44  lea     rax, ??_7SettingsManager@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::SettingsManager::`vftable'
0x18018be4b  mov     [rcx], rax
0x18018be4e  xor     r15d, r15d
0x18018be51  mov     [rcx+8], r15
0x18018be55  mov     [rcx+10h], r15
0x18018be59  lea     ecx, [r15+38h]
0x18018be5d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18018be62  mov     [rax], rax
0x18018be65  mov     [rax+8], rax
0x18018be69  mov     [rdi+8], rax
0x18018be6d  lea     rcx, [rdi+18h]
0x18018be71  call    ??0?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@UCaseInsensitiveLessThanPredicate@String@Utils@Diagnostics@Microsoft@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::pair<std::wstring const,std::wstring>>>::map<std::wstring,std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::pair<std::wstring const,std::wstring>>>(void)
0x18018be76  nop
0x18018be77  mov     [rdi+28h], r15
0x18018be7b  mov     [rdi+30h], r15
0x18018be7f  lea     ecx, [r15+40h]
0x18018be83  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18018be88  mov     [rax], rax
0x18018be8b  mov     [rax+8], rax
0x18018be8f  mov     [rax+10h], rax
0x18018be93  mov     word ptr [rax+18h], 101h
0x18018be99  mov     [rdi+28h], rax
0x18018be9d  mov     [rdi+38h], r15
0x18018bea1  mov     [rdi+40h], r15
0x18018bea5  call    ??$_Buyheadnode@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@PEAX@std@@SAPEAU01@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@PEAX@std@@@1@@Z; std::_Tree_node<std::pair<std::wstring const,unsigned __int64>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<std::wstring const,unsigned __int64>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,unsigned __int64>,void *>> &)
0x18018beaa  mov     [rdi+38h], rax
0x18018beae  mov     qword ptr [rdi+48h], 102h
0x18018beb6  xorps   xmm0, xmm0
0x18018beb9  movups  xmmword ptr [rdi+60h], xmm0
0x18018bebd  movups  xmmword ptr [rdi+70h], xmm0
0x18018bec1  movups  xmmword ptr [rdi+80h], xmm0
0x18018bec8  mov     [rdi+50h], r15
0x18018becc  mov     [rdi+58h], r15
0x18018bed0  or      esi, 0FFFFFFFFh
0x18018bed3  mov     [rdi+90h], esi
0x18018bed9  mov     [rdi+94h], r15d
0x18018bee0  mov     qword ptr [rdi+98h], 102h
0x18018beeb  movups  xmmword ptr [rdi+0B0h], xmm0
0x18018bef2  movups  xmmword ptr [rdi+0C0h], xmm0
0x18018bef9  movups  xmmword ptr [rdi+0D0h], xmm0
0x18018bf00  mov     [rdi+0A0h], r15
0x18018bf07  mov     [rdi+0A8h], r15
0x18018bf0e  mov     [rdi+0E0h], esi
0x18018bf14  mov     [rdi+0E4h], r15d
0x18018bf1b  mov     qword ptr [rdi+0E8h], 102h
0x18018bf26  movups  xmmword ptr [rdi+100h], xmm0
0x18018bf2d  movups  xmmword ptr [rdi+110h], xmm0
0x18018bf34  movups  xmmword ptr [rdi+120h], xmm0
0x18018bf3b  mov     [rdi+0F0h], r15
0x18018bf42  mov     [rdi+0F8h], r15
0x18018bf49  mov     [rdi+130h], esi
0x18018bf4f  mov     [rdi+134h], r15d
0x18018bf56  mov     qword ptr [rdi+138h], 102h
0x18018bf61  movups  xmmword ptr [rdi+150h], xmm0
0x18018bf68  movups  xmmword ptr [rdi+160h], xmm0
0x18018bf6f  movups  xmmword ptr [rdi+170h], xmm0
0x18018bf76  mov     [rdi+140h], r15
0x18018bf7d  mov     [rdi+148h], r15
0x18018bf84  mov     [rdi+180h], esi
0x18018bf8a  mov     [rdi+184h], r15d
0x18018bf91  lea     rcx, [rdi+188h]; void *
0x18018bf98  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18018bf9d  nop
0x18018bf9e  lea     rcx, [rdi+1A8h]; void *
0x18018bfa5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18018bfaa  nop
0x18018bfab  mov     dword ptr [rdi+1C8h], 3
0x18018bfb5  lea     rcx, [rdi+1D0h]; void *
0x18018bfbc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18018bfc1  nop
0x18018bfc2  lea     rcx, [rdi+1F0h]; void *
0x18018bfc9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18018bfce  nop
0x18018bfcf  call    ?GetFileTimeAsULL@Time@Utils@Diagnostics@Microsoft@@SA_KXZ; Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL(void)
0x18018bfd4  mov     [rdi+210h], rax
0x18018bfdb  call    ?GetFileTimeAsULL@Time@Utils@Diagnostics@Microsoft@@SA_KXZ; Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL(void)
0x18018bfe0  mov     [rdi+218h], rax
0x18018bfe7  lea     r12, [rdi+220h]
0x18018bfee  mov     dword ptr [r12], 2760h
0x18018bff6  lea     r13, [rdi+224h]
0x18018bffd  mov     dword ptr [r13+0], 1680h
0x18018c005  lea     r15, [rdi+228h]
0x18018c00c  movups  xmm0, xmmword ptr cs:?k_msaTicketPolicy@SettingsManager@Diagnostics@Microsoft@@2V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::SettingsManager::k_msaTicketPolicy
0x18018c013  movdqu  [rbp+57h+var_A0], xmm0
0x18018c018  movups  xmm1, xmmword ptr cs:?k_settingsV3UrlPrefix@SettingsDownloader@Diagnostics@Microsoft@@2V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::SettingsDownloader::k_settingsV3UrlPrefix
0x18018c01f  movdqu  [rbp+57h+var_90], xmm1
0x18018c024  lea     r9, ?k_utcApplicationGuid@SettingsManager@Diagnostics@Microsoft@@2U_GUID@@B; _GUID const Microsoft::Diagnostics::SettingsManager::k_utcApplicationGuid
0x18018c02b  lea     r8, [rbp+57h+var_A0]
0x18018c02f  lea     rdx, [rbp+57h+var_90]
0x18018c033  mov     rcx, r15
0x18018c036  call    ??0DeviceTicket@Diagnostics@Microsoft@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBU_GUID@@@Z; Microsoft::Diagnostics::DeviceTicket::DeviceTicket(std::wstring_view,std::wstring_view,_GUID const &)
0x18018c03b  nop
0x18018c03c  mov     qword ptr [rdi+278h], 102h
0x18018c047  xorps   xmm0, xmm0
0x18018c04a  movups  xmmword ptr [rdi+290h], xmm0
0x18018c051  movups  xmmword ptr [rdi+2A0h], xmm0
0x18018c058  movups  xmmword ptr [rdi+2B0h], xmm0
0x18018c05f  xor     ecx, ecx
0x18018c061  mov     [rdi+280h], rcx
0x18018c068  mov     [rdi+288h], rcx
0x18018c06f  mov     [rdi+2C0h], esi
0x18018c075  mov     [rdi+2C4h], ecx
0x18018c07b  mov     qword ptr [rdi+2C8h], 102h
0x18018c086  movups  xmmword ptr [rdi+2E0h], xmm0
0x18018c08d  movups  xmmword ptr [rdi+2F0h], xmm0
0x18018c094  movups  xmmword ptr [rdi+300h], xmm0
0x18018c09b  mov     [rdi+2D0h], rcx
0x18018c0a2  mov     [rdi+2D8h], rcx
0x18018c0a9  mov     [rdi+310h], esi
0x18018c0af  xor     ebx, ebx
0x18018c0b1  mov     [rdi+314h], ebx
0x18018c0b7  lea     rcx, [rdi+318h]
0x18018c0be  call    ??0?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VSettingsEndpoint@Diagnostics@Microsoft@@U?$default_delete@VSettingsEndpoint@Diagnostics@Microsoft@@@std@@@2@UCaseInsensitiveHashPredicate@Hash@Utils@Diagnostics@Microsoft@@UCaseInsensitiveEqualToPredicate@String@678@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VSettingsEndpoint@Diagnostics@Microsoft@@U?$default_delete@VSettingsEndpoint@Diagnostics@Microsoft@@@std@@@2@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>,Microsoft::Diagnostics::Utils::Hash::CaseInsensitiveHashPredicate,Microsoft::Diagnostics::Utils::String::CaseInsensitiveEqualToPredicate,std::allocator<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>>>>::unordered_map<std::wstring,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>,Microsoft::Diagnostics::Utils::Hash::CaseInsensitiveHashPredicate,Microsoft::Diagnostics::Utils::String::CaseInsensitiveEqualToPredicate,std::allocator<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>>>>(void)
0x18018c0c3  nop
0x18018c0c4  lea     rcx, [rdi+358h]
0x18018c0cb  call    ??0?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VSettingsEndpoint@Diagnostics@Microsoft@@U?$default_delete@VSettingsEndpoint@Diagnostics@Microsoft@@@std@@@2@UCaseInsensitiveHashPredicate@Hash@Utils@Diagnostics@Microsoft@@UCaseInsensitiveEqualToPredicate@String@678@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VSettingsEndpoint@Diagnostics@Microsoft@@U?$default_delete@VSettingsEndpoint@Diagnostics@Microsoft@@@std@@@2@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>,Microsoft::Diagnostics::Utils::Hash::CaseInsensitiveHashPredicate,Microsoft::Diagnostics::Utils::String::CaseInsensitiveEqualToPredicate,std::allocator<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>>>>::unordered_map<std::wstring,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>,Microsoft::Diagnostics::Utils::Hash::CaseInsensitiveHashPredicate,Microsoft::Diagnostics::Utils::String::CaseInsensitiveEqualToPredicate,std::allocator<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>>>>(void)
0x18018c0d0  nop
0x18018c0d1  mov     [rdi+398h], rbx
0x18018c0d8  mov     [rdi+3A0h], rbx
0x18018c0df  mov     [rdi+3A8h], rbx
0x18018c0e6  mov     [rdi+3B0h], rbx
0x18018c0ed  mov     [rdi+3B8h], rbx
0x18018c0f4  mov     [rdi+3C0h], rbx
0x18018c0fb  lea     rsi, [rdi+3C8h]
0x18018c102  mov     [rsi], rbx
0x18018c105  mov     byte ptr [rdi+3D0h], 1
0x18018c10c  lea     rcx, [rdi+3D8h]; pv
0x18018c113  call    ??0TpSerialWork@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::TpSerialWork::TpSerialWork(void)
0x18018c118  nop
0x18018c119  lea     rbx, [rdi+450h]
0x18018c120  mov     qword ptr [rbx], 0
0x18018c127  mov     dword ptr [rdi+458h], 0DBBA0h
0x18018c131  mov     dword ptr [rdi+45Ch], 0Fh
0x18018c13b  lea     rcx, [rdi+460h]
0x18018c142  lea     rdx, off_18035F2E0; "dedb3435bceb4d2d9f40bcb2139e6562-4de2fa"...
0x18018c149  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18018c14e  nop
0x18018c14f  lea     rcx, [rdi+480h]
0x18018c156  call    ??0?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitiveLessThanPredicate@String@Utils@Diagnostics@Microsoft@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::wstring>>::set<std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::wstring>>(void)
0x18018c15b  nop
0x18018c15c  lea     rcx, [rdi+490h]
0x18018c163  call    ??0?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitiveLessThanPredicate@String@Utils@Diagnostics@Microsoft@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::wstring>>::set<std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::wstring>>(void)
0x18018c168  nop
0x18018c169  lea     rcx, [rdi+4A0h]
0x18018c170  lea     rdx, Src
0x18018c177  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18018c17c  nop
0x18018c17d  mov     al, [r14+1]
0x18018c181  mov     [rdi+4C0h], al
0x18018c187  mov     qword ptr [rsp+110h+var_F0], 0
0x18018c190  xor     r9d, r9d
0x18018c193  xor     r8d, r8d
0x18018c196  lea     edx, [r9+1]
0x18018c19a  mov     rcx, rbx
0x18018c19d  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18018c1a2  xor     ebx, ebx
0x18018c1a4  cmp     [r14+2], bl
0x18018c1a8  jnz     loc_18018C806
0x18018c1ae  lea     rcx, [rbp+57h+var_58]; void *
0x18018c1b2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18018c1b7  nop
0x18018c1b8  movups  xmm0, xmmword ptr cs:off_18035F2D0; "SettingsBaseUrl"
0x18018c1bf  movdqu  [rbp+57h+var_A0], xmm0
0x18018c1c4  lea     rdx, [rbp+57h+var_58]
0x18018c1c8  lea     rcx, [rbp+57h+var_A0]
0x18018c1cc  call    ?IsTestHookEnabled@General@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@6@@Z; Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(std::wstring_view,std::wstring &)
0x18018c1d1  test    al, al
0x18018c1d3  jz      short loc_18018C1F1
0x18018c1d5  lea     rdx, [rbp+57h+var_A0]
0x18018c1d9  lea     rcx, [rbp+57h+var_58]
0x18018c1dd  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18018c1e2  mov     r8, [rax+8]
0x18018c1e6  mov     rdx, [rax]
0x18018c1e9  mov     rcx, r15
0x18018c1ec  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18018c1f1  xorps   xmm0, xmm0
0x18018c1f4  movdqa  [rbp+57h+var_A0], xmm0
0x18018c1f9  lea     r9, aApp; "app"
0x18018c200  mov     qword ptr [rbp+57h+var_90], r9
0x18018c204  mov     r10d, 3
0x18018c20a  mov     qword ptr [rbp+57h+var_90+8], r10
0x18018c20e  lea     r9, aUtc_3; "utc"
0x18018c215  mov     qword ptr [rbp+57h+var_80], r9
0x18018c219  mov     qword ptr [rbp+57h+var_80+8], r10
0x18018c21d  mov     [rsp+110h+var_B0], bl
0x18018c221  mov     r10d, 1
0x18018c227  mov     [rsp+110h+var_B8], r10b
0x18018c22c  lea     r9, [rbp+57h+var_A0]
0x18018c230  mov     [rsp+110h+var_C8], r9
0x18018c235  mov     [rsp+110h+var_D0], bx
0x18018c23a  mov     [rsp+110h+var_D8], bx
0x18018c23f  mov     [rsp+110h+var_E0], bx
0x18018c244  mov     [rsp+110h+var_E8], bx
0x18018c249  mov     word ptr [rsp+110h+var_F0], r10w
0x18018c24f  movzx   r9d, r10w
0x18018c253  lea     r8, [rbp+57h+var_90]
0x18018c257  lea     rdx, [rbp+57h+var_80]
0x18018c25b  mov     rcx, rdi
0x18018c25e  call    ?RegisterSettingsEndpoint@SettingsManager@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0VSettingsType@23@VSettingsPriority@23@VSettingsRegistrationType@23@VSettingsPayloadType@23@VSettingsParseType@23@VSettingsCreationType@23@0_N77@Z; Microsoft::Diagnostics::SettingsManager::RegisterSettingsEndpoint(std::wstring_view,std::wstring_view,Microsoft::Diagnostics::SettingsType,Microsoft::Diagnostics::SettingsPriority,Microsoft::Diagnostics::SettingsRegistrationType,Microsoft::Diagnostics::SettingsPayloadType,Microsoft::Diagnostics::SettingsParseType,Microsoft::Diagnostics::SettingsCreationType,std::wstring_view,bool,bool,bool)
0x18018c263  xorps   xmm0, xmm0
0x18018c266  movdqa  [rbp+57h+var_A0], xmm0
0x18018c26b  lea     r9, aAsmWindowsdefa; "ASM-WindowsDefault"
0x18018c272  mov     qword ptr [rbp+57h+var_90], r9
0x18018c276  mov     qword ptr [rbp+57h+var_90+8], 12h
0x18018c27e  lea     r9, aTelemetry_0; "telemetry"
0x18018c285  mov     qword ptr [rbp+57h+var_80], r9
0x18018c289  mov     r15d, 9
0x18018c28f  mov     qword ptr [rbp+57h+var_80+8], r15
0x18018c293  mov     [rsp+110h+var_B0], bl
0x18018c297  lea     r10d, [r15-8]
0x18018c29b  mov     [rsp+110h+var_B8], r10b
0x18018c2a0  lea     r9, [rbp+57h+var_A0]
0x18018c2a4  mov     [rsp+110h+var_C8], r9
0x18018c2a9  mov     [rsp+110h+var_D0], bx
0x18018c2ae  mov     [rsp+110h+var_D8], bx
0x18018c2b3  mov     [rsp+110h+var_E0], bx
0x18018c2b8  mov     [rsp+110h+var_E8], bx
0x18018c2bd  mov     word ptr [rsp+110h+var_F0], r10w
0x18018c2c3  movzx   r9d, r10w
0x18018c2c7  lea     r8, [rbp+57h+var_90]
0x18018c2cb  lea     rdx, [rbp+57h+var_80]
0x18018c2cf  mov     rcx, rdi
0x18018c2d2  call    ?RegisterSettingsEndpoint@SettingsManager@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0VSettingsType@23@VSettingsPriority@23@VSettingsRegistrationType@23@VSettingsPayloadType@23@VSettingsParseType@23@VSettingsCreationType@23@0_N77@Z; Microsoft::Diagnostics::SettingsManager::RegisterSettingsEndpoint(std::wstring_view,std::wstring_view,Microsoft::Diagnostics::SettingsType,Microsoft::Diagnostics::SettingsPriority,Microsoft::Diagnostics::SettingsRegistrationType,Microsoft::Diagnostics::SettingsPayloadType,Microsoft::Diagnostics::SettingsParseType,Microsoft::Diagnostics::SettingsCreationType,std::wstring_view,bool,bool,bool)
0x18018c2d7  mov     r8d, ebx
0x18018c2da  mov     edx, ebx
0x18018c2dc  mov     ecx, ebx
0x18018c2de  mov     eax, ebx
0x18018c2e0  lea     ebx, [r15-7]
0x18018c2e4  xorps   xmm0, xmm0
0x18018c2e7  movdqa  [rbp+57h+var_A0], xmm0
0x18018c2ec  lea     r9, aCert; "cert"
0x18018c2f3  mov     qword ptr [rbp+57h+var_90], r9
0x18018c2f7  mov     qword ptr [rbp+57h+var_90+8], 4
0x18018c2ff  lea     r9, aUtc_3; "utc"
0x18018c306  mov     qword ptr [rbp+57h+var_80], r9
0x18018c30a  mov     qword ptr [rbp+57h+var_80+8], 3
0x18018c312  mov     [rsp+110h+var_B0], al
0x18018c316  lea     r10d, [r15-8]
0x18018c31a  mov     [rsp+110h+var_B8], r10b
0x18018c31f  lea     r9, [rbp+57h+var_A0]
0x18018c323  mov     [rsp+110h+var_C8], r9
0x18018c328  mov     [rsp+110h+var_D0], r8w
0x18018c32e  mov     [rsp+110h+var_D8], dx
0x18018c333  mov     [rsp+110h+var_E0], cx
0x18018c338  mov     [rsp+110h+var_E8], ax
0x18018c33d  mov     word ptr [rsp+110h+var_F0], bx
0x18018c342  movzx   r9d, r10w
0x18018c346  lea     r8, [rbp+57h+var_90]
0x18018c34a  lea     rdx, [rbp+57h+var_80]
0x18018c34e  mov     rcx, rdi
0x18018c351  call    ?RegisterSettingsEndpoint@SettingsManager@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0VSettingsType@23@VSettingsPriority@23@VSettingsRegistrationType@23@VSettingsPayloadType@23@VSettingsParseType@23@VSettingsCreationType@23@0_N77@Z; Microsoft::Diagnostics::SettingsManager::RegisterSettingsEndpoint(std::wstring_view,std::wstring_view,Microsoft::Diagnostics::SettingsType,Microsoft::Diagnostics::SettingsPriority,Microsoft::Diagnostics::SettingsRegistrationType,Microsoft::Diagnostics::SettingsPayloadType,Microsoft::Diagnostics::SettingsParseType,Microsoft::Diagnostics::SettingsCreationType,std::wstring_view,bool,bool,bool)
0x18018c356  xor     r8d, r8d
0x18018c359  lea     rdx, Src
0x18018c360  mov     qword ptr [rbp+57h+var_90], rdx
0x18018c364  mov     qword ptr [rbp+57h+var_90+8], r8
0x18018c368  lea     rdx, aPrivacy; "privacy"
0x18018c36f  mov     qword ptr [rbp+57h+var_80], rdx
0x18018c373  mov     qword ptr [rbp+57h+var_80+8], 7
0x18018c37b  lea     rdx, aUtc_3; "utc"
0x18018c382  mov     qword ptr [rbp+57h+var_A0], rdx
0x18018c386  mov     qword ptr [rbp+57h+var_A0+8], 3
0x18018c38e  mov     [rsp+110h+var_B0], r8b
0x18018c393  mov     [rsp+110h+var_B8], r8b
0x18018c398  lea     rdx, [rbp+57h+var_90]
0x18018c39c  mov     [rsp+110h+var_C8], rdx
0x18018c3a1  mov     [rsp+110h+var_D0], r8w
0x18018c3a7  lea     ecx, [rbx-1]
0x18018c3aa  mov     [rsp+110h+var_D8], cx
0x18018c3af  mov     [rsp+110h+var_E0], cx
0x18018c3b4  mov     [rsp+110h+var_E8], r8w
0x18018c3ba  mov     word ptr [rsp+110h+var_F0], bx
0x18018c3bf  movzx   r9d, cx
0x18018c3c3  lea     r8, [rbp+57h+var_80]
0x18018c3c7  lea     rdx, [rbp+57h+var_A0]
0x18018c3cb  mov     rcx, rdi
0x18018c3ce  call    ?RegisterSettingsEndpoint@SettingsManager@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0VSettingsType@23@VSettingsPriority@23@VSettingsRegistrationType@23@VSettingsPayloadType@23@VSettingsParseType@23@VSettingsCreationType@23@0_N77@Z; Microsoft::Diagnostics::SettingsManager::RegisterSettingsEndpoint(std::wstring_view,std::wstring_view,Microsoft::Diagnostics::SettingsType,Microsoft::Diagnostics::SettingsPriority,Microsoft::Diagnostics::SettingsRegistrationType,Microsoft::Diagnostics::SettingsPayloadType,Microsoft::Diagnostics::SettingsParseType,Microsoft::Diagnostics::SettingsCreationType,std::wstring_view,bool,bool,bool)
0x18018c3d3  xor     r10d, r10d
0x18018c3d6  lea     r8, Src
0x18018c3dd  mov     qword ptr [rbp+57h+var_A0], r8
0x18018c3e1  mov     qword ptr [rbp+57h+var_A0+8], r10
0x18018c3e5  lea     r8, aAllow_0; "allow"
0x18018c3ec  mov     qword ptr [rbp+57h+var_90], r8
0x18018c3f0  mov     qword ptr [rbp+57h+var_90+8], 5
0x18018c3f8  lea     r9, aUtc_3; "utc"
  ... truncated ...
```
