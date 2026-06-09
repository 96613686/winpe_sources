# CnsPayloadProvider::ReconcileCnsFLights(ClientState *)

- ea: `0x180049460`
- end: `0x1800498b5`
- name: `?ReconcileCnsFLights@CnsPayloadProvider@@SAJPEAVClientState@@@Z`
- size: `1109`
- prototype: `__int64 __fastcall(struct ClientState *this)`
- caller_count: `2`
- callee_count: `27`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180049440`
- `0x1800498bc`

## callees

- `0x180005f50`
- `0x18000847c`
- `0x180009a60`
- `0x180009ff0`
- `0x18000a148`
- `0x1800101fc`
- `0x1800106c8`
- `0x1800116f8`
- `0x1800169c0`
- `0x180017dec`
- `0x180019e68`
- `0x18001a624`
- `0x180021f60`
- `0x1800245a8`
- `0x18002560c`
- `0x180025b54`
- `0x180027f80`
- `0x1800286b0`
- `0x180029f10`
- `0x18002a8c8`
- `0x180048230`
- `0x1800482b4`
- `0x180049460`
- `0x180049fe4`
- `0x18004a0fc`
- `0x18004a1f0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004954f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049816`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004954f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049816`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004955e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004955e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180049766`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180049766`

## string_xrefs

- `0x1800497c7`: `OneSettingsTIP::reason::CompletedSuccessfully`
- `0x1800494f3`: `OneSettingsTIP::reason::CnsCompletedNoContent`
- `0x18004985c`: `OneSettingsTIP::reason::CnsCompletedContentNotSupported`
- `0x18004979d`: `OneSettingsTIP::reason::CnsReconcileAllFlightsRemoved`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CnsPayloadProvider::ReconcileCnsFLights(struct ClientState *this)
{
  __int64 v2; // rax
  const char *v3; // rdx
  const char *v4; // rax
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // rdi
  HSTRING v8; // r13
  PCWSTR StringRawBuffer; // rax
  __int64 **CnsFlights; // rbx
  int v11; // eax
  bool v12; // r12
  struct _FILETIME system_time; // rax
  unsigned __int64 v14; // r14
  volatile signed __int32 *v15; // rax
  volatile signed __int32 *v16; // rbx
  volatile signed __int32 *v17; // r15
  __int64 v18; // rax
  __int64 v19; // rax
  const char *v20; // rdx
  const char *v21; // rax
  wil::filetime *v22; // rcx
  _QWORD *v23; // rax
  __int64 v24; // rax
  const char *v25; // rdx
  const char *v26; // rax
  _QWORD *v27; // rax
  volatile signed __int32 *v28; // rcx
  const unsigned __int16 *v29; // rax
  __int64 v30; // rbx
  const char *v31; // rdx
  const char *v32; // rax
  const char *v33; // rax
  __int64 v34; // rdx
  volatile signed __int32 *v35; // rcx
  __int64 v36; // rax
  __int64 v38; // [rsp+20h] [rbp-79h]
  int v39; // [rsp+20h] [rbp-79h]
  _QWORD v40[2]; // [rsp+30h] [rbp-69h] BYREF
  _QWORD v41[2]; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v42[16]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v43[16]; // [rsp+60h] [rbp-39h] BYREF
  void **v44; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v45[48]; // [rsp+78h] [rbp-21h] BYREF
  volatile signed __int32 *v46; // [rsp+A8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  volatile signed __int32 *v48; // [rsp+100h] [rbp+67h] BYREF
  __int64 v49; // [rsp+108h] [rbp+6Fh] BYREF
  __int64 v50; // [rsp+110h] [rbp+77h] BYREF
  HSTRING v51; // [rsp+118h] [rbp+7Fh]

  v48 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_WOSC_TIP_CnsReconcileAndUpdate_attributes,tip2::test_data_basic>>::start(
    &v48,
    v41);
  v44 = &tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes,tip2::test_data_basic>>::`vftable';
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v45,
    (struct wil::details::IFailureCallback *)&v44,
    0,
    1);
  v46 = v48;
  if ( v48 )
    _InterlockedIncrement(v48 + 84);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>,wil::err_returncode_policy>((void **)&v48);
  v2 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this);
  tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_TIP_HandleCnsPayload_attributes,tip2::test_data_basic>>::logf(
    &v44,
    "AppId='%ws'",
    v2);
  if ( !ClientState::HasCnsFlights(this) )
  {
    v4 = tip2::details::reason_string((tip2::details *)"OneSettingsTIP::reason::CnsCompletedNoContent", v3);
    v5 = 20;
    LOBYTE(v6) = 1;
LABEL_27:
    tip2::details::shared_data<0,0,1>::complete_without_lock(v46 + 2, v6, v5, v4);
    goto LABEL_28;
  }
  LOBYTE(v48) = 0;
  v7 = *((_QWORD *)this + 36);
  if ( !v7 || (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)v7 + 64LL))(*((_QWORD *)this + 36)) )
  {
    v4 = tip2::details::reason_string((tip2::details *)"OneSettingsTIP::reason::CnsCompletedContentNotSupported", v3);
    v5 = 21;
    LOBYTE(v6) = 2;
    goto LABEL_27;
  }
  v51 = 0;
  v8 = (HSTRING)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  WindowsDeleteString(0);
  v51 = v8;
  StringRawBuffer = WindowsGetStringRawBuffer(v8, 0);
  Windows::Internal::Flighting::OneSettings::OneSettingsPayload::GetJsonSettings(&v50, StringRawBuffer);
  std::map<std::wstring,std::shared_ptr<CnsFlightState>>::map<std::wstring,std::shared_ptr<CnsFlightState>>(v42);
  std::map<std::wstring,std::shared_ptr<CnsFlightState>>::map<std::wstring,std::shared_ptr<CnsFlightState>>(v40);
  CnsFlights = (__int64 **)ClientState::GetCnsFlights(this, v41);
  v49 = v50;
  Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::OneSettingsPayload>::InternalAddRef(&v49);
  v11 = CnsPayloadProvider::ApplyCnsFlightsToJson(&v49, CnsFlights, v7, &v48, v38, (__int64)v40);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18B,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\cnspayloadprovider.cpp",
      (const char *)(unsigned int)v11,
      v39);
  v12 = 0;
  system_time = wil::filetime::get_system_time(retaddr);
  v14 = system_time.dwLowDateTime
      + 1080123392
      + ((system_time.dwLowDateTime + (*(_QWORD *)&system_time & 0xFFFFFFFF00000000uLL) - 1296000000000LL)
       & 0xFFFFFFFF00000000uLL);
  ClientState::GetCnsFlights(this, v41);
  v15 = *(volatile signed __int32 **)v41[0];
  v48 = *(volatile signed __int32 **)v41[0];
  while ( !*((_BYTE *)v15 + 25) )
  {
    v16 = v15 + 8;
    v17 = v15 + 16;
    v18 = *((_QWORD *)v15 + 8);
    if ( *(_DWORD *)(v18 + 32) || *(_DWORD *)(v18 + 28) )
    {
      if ( *(unsigned int *)(v18 + 28) + ((unsigned __int64)*(unsigned int *)(v18 + 32) << 32) < v14 )
      {
        v23 = (_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<CnsFlightState>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>,0>>::find(
                          v40,
                          &v49,
                          v16);
        if ( *v23 == v40[0] )
        {
          v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v16);
          tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_TIP_HandleCnsPayload_attributes,tip2::test_data_basic>>::logf(
            &v44,
            "Flight %ws expired",
            v24);
          v26 = tip2::details::reason_string((tip2::details *)"OneSettingsTIP::reason::CnsReconcileExpiredFlight", v25);
          tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_TIP_CnsReconcileAndUpdate_attributes,tip2::test_data_basic>>::set_flag(
            &v44,
            23,
            v26);
          v27 = (_QWORD *)std::map<std::wstring,std::shared_ptr<CnsFlightState>>::_Try_emplace<std::wstring const &,>(
                            v40,
                            v43,
                            v16);
          std::shared_ptr<CnsFlightState>::operator=(*v27 + 64LL, v17);
        }
      }
    }
    else
    {
      v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v16);
      tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_TIP_HandleCnsPayload_attributes,tip2::test_data_basic>>::logf(
        &v44,
        "Flight %ws has no receiptTime",
        v19);
      v21 = tip2::details::reason_string((tip2::details *)"OneSettingsTIP::reason::CnsReconcileMissingReceiptTime", v20);
      tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_TIP_CnsReconcileAndUpdate_attributes,tip2::test_data_basic>>::set_flag(
        &v44,
        22,
        v21);
      *(struct _FILETIME *)(*(_QWORD *)v17 + 28LL) = wil::filetime::get_system_time(v22);
      v12 = 1;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>,std::_Iterator_base0>::operator++(&v48);
    v15 = v48;
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>>>(
    v41,
    v41);
  v28 = *(volatile signed __int32 **)v40[0];
  v48 = *(volatile signed __int32 **)v40[0];
  while ( !*((_BYTE *)v28 + 25) )
  {
    v29 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28 + 8);
    ClientState::RemoveCnsFlight(this, v29);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>,std::_Iterator_base0>::operator++(&v48);
    v28 = v48;
  }
  GetSystemTimeAsFileTime((LPFILETIME)((char *)this + 484));
  ClientState::SaveCnsState(this, v12);
  v30 = *(_QWORD *)(ClientState::GetCnsFlights(this, v41) + 8);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>>>(
    v41,
    v41);
  if ( v30 )
  {
    v35 = *(volatile signed __int32 **)v40[0];
    v48 = *(volatile signed __int32 **)v40[0];
    while ( !*((_BYTE *)v35 + 25) )
    {
      v36 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35 + 8);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 112LL))(v7, v36);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>,std::_Iterator_base0>::operator++(&v48);
      v35 = v48;
    }
  }
  else
  {
    v32 = tip2::details::reason_string((tip2::details *)"OneSettingsTIP::reason::CnsReconcileAllFlightsRemoved", v31);
    tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_TIP_CnsReconcileAndUpdate_attributes,tip2::test_data_basic>>::set_flag(
      &v44,
      24,
      v32);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 120LL))(v7);
  }
  v33 = tip2::details::reason_string((tip2::details *)"OneSettingsTIP::reason::CompletedSuccessfully", v31);
  LOBYTE(v34) = 1;
  tip2::details::shared_data<0,0,1>::complete_without_lock(v46 + 2, v34, 1, v33);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>>>(
    v40,
    v40);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>>>(
    v42,
    v42);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
  WindowsDeleteString(v8);
LABEL_28:
  tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>>(&v44);
  return 0;
}

```

## disassembly

```asm
0x180049460  push    rbp
0x180049462  push    rbx
0x180049463  push    rsi
0x180049464  push    rdi
0x180049465  push    r12
0x180049467  push    r13
0x180049469  push    r14
0x18004946b  push    r15
0x18004946d  lea     rbp, [rsp-1Fh]
0x180049472  sub     rsp, 0B8h
0x180049479  mov     rsi, rcx
0x18004947c  xor     r15d, r15d
0x18004947f  mov     [rbp+57h+arg_0], r15
0x180049483  lea     rdx, [rbp+57h+var_B0]
0x180049487  lea     rcx, [rbp+57h+arg_0]
0x18004948b  call    ?start@?$tip_test@V?$merged_data@U_tip_WOSC_TIP_CnsReconcileAndUpdate_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WOSC_TIP_CnsReconcileAndUpdate_attributes,tip2::test_data_basic>>::start(void)
0x180049490  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes,tip2::test_data_basic>>::`vftable'
0x180049497  mov     [rbp+57h+var_80], rax
0x18004949b  mov     r9b, 1; bool
0x18004949e  xor     r8d, r8d; struct wil::CallContextInfo *
0x1800494a1  lea     rdx, [rbp+57h+var_80]; struct wil::details::IFailureCallback *
0x1800494a5  lea     rcx, [rbp+57h+var_78]; this
0x1800494a9  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x1800494ae  mov     rax, [rbp+57h+arg_0]
0x1800494b2  mov     [rbp+57h+var_48], rax
0x1800494b6  test    rax, rax
0x1800494b9  jz      short loc_1800494C2
0x1800494bb  lock inc dword ptr [rax+150h]
0x1800494c2  lea     rcx, [rbp+57h+arg_0]
0x1800494c6  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WOSC_ForceRefreshOneSettings_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>,wil::err_returncode_policy>(void)
0x1800494cb  nop
0x1800494cc  mov     rcx, rsi
0x1800494cf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800494d4  mov     r8, rax
0x1800494d7  lea     rdx, aAppidWs; "AppId='%ws'"
0x1800494de  lea     rcx, [rbp+57h+var_80]
0x1800494e2  call    ?logf@?$test_watcher@V?$merged_data@U_tip_WOSC_TIP_HandleCnsPayload_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXPEBDZZ; tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_TIP_HandleCnsPayload_attributes,tip2::test_data_basic>>::logf(char const *,...)
0x1800494e7  mov     rcx, rsi; this
0x1800494ea  call    ?HasCnsFlights@ClientState@@QEAA_NXZ; ClientState::HasCnsFlights(void)
0x1800494ef  test    al, al
0x1800494f1  jnz     short loc_18004950C
0x1800494f3  lea     rcx, aOnesettingstip_0; "OneSettingsTIP::reason::CnsCompletedNoC"...
0x1800494fa  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800494ff  mov     r8d, 14h
0x180049505  mov     dl, 1
0x180049507  jmp     loc_180049870
0x18004950c  mov     byte ptr [rbp+57h+arg_0], r15b
0x180049510  mov     rdi, [rsi+120h]
0x180049517  test    rdi, rdi
0x18004951a  jz      loc_18004985C
0x180049520  mov     rax, [rdi]
0x180049523  mov     rcx, rdi
0x180049526  mov     rax, [rax+40h]
0x18004952a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004952f  test    eax, eax
0x180049531  jnz     loc_18004985C
0x180049537  mov     [rbp+57h+arg_18], r15
0x18004953b  mov     rax, [rdi]
0x18004953e  mov     rcx, rdi
0x180049541  mov     rax, [rax+10h]
0x180049545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004954a  mov     r13, rax
0x18004954d  xor     ecx, ecx; string
0x18004954f  call    cs:__imp_WindowsDeleteString
0x180049555  mov     [rbp+57h+arg_18], r13
0x180049559  xor     edx, edx; length
0x18004955b  mov     rcx, r13; string
0x18004955e  call    cs:__imp_WindowsGetStringRawBuffer
0x180049564  mov     rdx, rax
0x180049567  lea     rcx, [rbp+57h+arg_10]
0x18004956b  call    ?GetJsonSettings@OneSettingsPayload@OneSettings@Flighting@Internal@Windows@@SA?AV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBG@Z; Windows::Internal::Flighting::OneSettings::OneSettingsPayload::GetJsonSettings(ushort const *)
0x180049570  nop
0x180049571  lea     rcx, [rbp+57h+var_A0]
0x180049575  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::shared_ptr<CnsFlightState>>::map<std::wstring,std::shared_ptr<CnsFlightState>>(void)
0x18004957a  nop
0x18004957b  lea     rcx, [rbp+57h+var_C0]
0x18004957f  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::shared_ptr<CnsFlightState>>::map<std::wstring,std::shared_ptr<CnsFlightState>>(void)
0x180049584  nop
0x180049585  lea     rdx, [rbp+57h+var_B0]
0x180049589  mov     rcx, rsi
0x18004958c  call    ?GetCnsFlights@ClientState@@QEAA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@2@@std@@XZ; ClientState::GetCnsFlights(void)
0x180049591  mov     rbx, rax
0x180049594  mov     rcx, [rbp+57h+arg_10]
0x180049598  mov     [rbp+57h+arg_8], rcx
0x18004959c  lea     rcx, [rbp+57h+arg_8]
0x1800495a0  call    ?InternalAddRef@?$ComPtr@VOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::OneSettingsPayload>::InternalAddRef(void)
0x1800495a5  lea     rax, [rbp+57h+var_C0]
0x1800495a9  mov     [rsp+0F0h+var_C8], rax
0x1800495ae  lea     r9, [rbp+57h+arg_0]
0x1800495b2  mov     r8, rdi
0x1800495b5  mov     rdx, rbx
0x1800495b8  lea     rcx, [rbp+57h+arg_8]
0x1800495bc  call    ?ApplyCnsFlightsToJson@CnsPayloadProvider@@CAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@2@@std@@PEAVIPayloadHandler@@AEA_NPEAV56@4@Z; CnsPayloadProvider::ApplyCnsFlightsToJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,std::map<std::wstring,std::shared_ptr<CnsFlightState>>,IPayloadHandler *,bool &,std::map<std::wstring,std::shared_ptr<CnsFlightState>> *,std::map<std::wstring,std::shared_ptr<CnsFlightState>> *)
0x1800495c1  mov     rcx, [rbp+5Fh]; this
0x1800495c5  test    eax, eax
0x1800495c7  js      loc_1800498A0
0x1800495cd  mov     r12b, r15b
0x1800495d0  call    ?get_system_time@filetime@wil@@YA?AU_FILETIME@@XZ; wil::filetime::get_system_time(void)
0x1800495d5  mov     rdx, rax
0x1800495d8  mov     r8, 0FFFFFFFF00000000h
0x1800495e2  and     rdx, r8
0x1800495e5  mov     ecx, eax
0x1800495e7  mov     rax, 0FFFFFED240616000h
0x1800495f1  add     rdx, rax
0x1800495f4  add     rdx, rcx
0x1800495f7  mov     r14, rdx
0x1800495fa  and     r14, r8
0x1800495fd  mov     eax, edx
0x1800495ff  add     r14, rax
0x180049602  lea     rdx, [rbp+57h+var_B0]
0x180049606  mov     rcx, rsi
0x180049609  call    ?GetCnsFlights@ClientState@@QEAA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@2@@std@@XZ; ClientState::GetCnsFlights(void)
0x18004960e  nop
0x18004960f  mov     rax, [rbp+57h+var_B0]
0x180049613  mov     rax, [rax]
0x180049616  mov     [rbp+57h+arg_0], rax
0x18004961a  cmp     [rax+19h], r15b
0x18004961e  jnz     loc_18004971E
0x180049624  lea     rbx, [rax+20h]
0x180049628  lea     r15, [rbx+20h]
0x18004962c  mov     rax, [r15]
0x18004962f  cmp     dword ptr [rax+20h], 0
0x180049633  jnz     short loc_180049687
0x180049635  cmp     dword ptr [rax+1Ch], 0
0x180049639  jnz     short loc_180049687
0x18004963b  mov     rcx, rbx
0x18004963e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180049643  mov     r8, rax
0x180049646  lea     rdx, aFlightWsHasNoR; "Flight %ws has no receiptTime"
0x18004964d  lea     rcx, [rbp+57h+var_80]
0x180049651  call    ?logf@?$test_watcher@V?$merged_data@U_tip_WOSC_TIP_HandleCnsPayload_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXPEBDZZ; tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_TIP_HandleCnsPayload_attributes,tip2::test_data_basic>>::logf(char const *,...)
0x180049656  lea     rcx, aOnesettingstip_5; "OneSettingsTIP::reason::CnsReconcileMis"...
0x18004965d  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180049662  mov     r8, rax
0x180049665  mov     edx, 16h
0x18004966a  lea     rcx, [rbp+57h+var_80]
0x18004966e  call    ?set_flag@?$test_watcher@V?$merged_data@U_tip_WOSC_TIP_CnsReconcileAndUpdate_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_TIP_CnsReconcileAndUpdate_attributes,tip2::test_data_basic>>::set_flag(ushort,char const *)
0x180049673  call    ?get_system_time@filetime@wil@@YA?AU_FILETIME@@XZ; wil::filetime::get_system_time(void)
0x180049678  mov     rcx, [r15]
0x18004967b  mov     [rcx+1Ch], rax
0x18004967f  mov     r12b, 1
0x180049682  jmp     loc_180049709
0x180049687  mov     ecx, [rax+20h]
0x18004968a  shl     rcx, 20h
0x18004968e  mov     eax, [rax+1Ch]
0x180049691  add     rcx, rax
0x180049694  cmp     rcx, r14
0x180049697  jnb     short loc_180049709
0x180049699  mov     r8, rbx
0x18004969c  lea     rdx, [rbp+57h+arg_8]
0x1800496a0  lea     rcx, [rbp+57h+var_C0]
0x1800496a4  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<CnsFlightState>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>,0>>::find(std::wstring const &)
0x1800496a9  mov     rcx, [rbp+57h+var_C0]
0x1800496ad  cmp     [rax], rcx
0x1800496b0  jnz     short loc_180049709
0x1800496b2  mov     rcx, rbx
0x1800496b5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800496ba  mov     r8, rax
0x1800496bd  lea     rdx, aFlightWsExpire; "Flight %ws expired"
0x1800496c4  lea     rcx, [rbp+57h+var_80]
0x1800496c8  call    ?logf@?$test_watcher@V?$merged_data@U_tip_WOSC_TIP_HandleCnsPayload_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXPEBDZZ; tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_TIP_HandleCnsPayload_attributes,tip2::test_data_basic>>::logf(char const *,...)
0x1800496cd  lea     rcx, aOnesettingstip_3; "OneSettingsTIP::reason::CnsReconcileExp"...
0x1800496d4  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800496d9  mov     r8, rax
0x1800496dc  mov     edx, 17h
0x1800496e1  lea     rcx, [rbp+57h+var_80]
0x1800496e5  call    ?set_flag@?$test_watcher@V?$merged_data@U_tip_WOSC_TIP_CnsReconcileAndUpdate_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_TIP_CnsReconcileAndUpdate_attributes,tip2::test_data_basic>>::set_flag(ushort,char const *)
0x1800496ea  mov     r8, rbx
0x1800496ed  lea     rdx, [rbp+57h+var_90]
0x1800496f1  lea     rcx, [rbp+57h+var_C0]
0x1800496f5  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::shared_ptr<CnsFlightState>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x1800496fa  mov     rcx, [rax]
0x1800496fd  add     rcx, 40h ; '@'
0x180049701  mov     rdx, r15
0x180049704  call    ??4?$shared_ptr@UCnsFlightState@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CnsFlightState>::operator=(std::shared_ptr<CnsFlightState> const &)
0x180049709  lea     rcx, [rbp+57h+arg_0]
0x18004970d  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>,std::_Iterator_base0>::operator++(void)
0x180049712  mov     rax, [rbp+57h+arg_0]
0x180049716  xor     r15d, r15d
0x180049719  jmp     loc_18004961A
0x18004971e  lea     rdx, [rbp+57h+var_B0]
0x180049722  lea     rcx, [rbp+57h+var_B0]
0x180049726  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>> &)
0x18004972b  mov     rcx, [rbp+57h+var_C0]
0x18004972f  mov     rcx, [rcx]
0x180049732  mov     [rbp+57h+arg_0], rcx
0x180049736  cmp     [rcx+19h], r15b
0x18004973a  jnz     short loc_18004975F
0x18004973c  add     rcx, 20h ; ' '
0x180049740  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180049745  mov     rdx, rax; unsigned __int16 *
0x180049748  mov     rcx, rsi; this
0x18004974b  call    ?RemoveCnsFlight@ClientState@@QEAA_NPEBG@Z; ClientState::RemoveCnsFlight(ushort const *)
0x180049750  lea     rcx, [rbp+57h+arg_0]
0x180049754  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>,std::_Iterator_base0>::operator++(void)
0x180049759  mov     rcx, [rbp+57h+arg_0]
0x18004975d  jmp     short loc_180049736
0x18004975f  lea     rcx, [rsi+1E4h]; lpSystemTimeAsFileTime
0x180049766  call    cs:__imp_GetSystemTimeAsFileTime
0x18004976c  mov     dl, r12b; bool
0x18004976f  mov     rcx, rsi; this
0x180049772  call    ?SaveCnsState@ClientState@@QEAAX_N@Z; ClientState::SaveCnsState(bool)
0x180049777  lea     rdx, [rbp+57h+var_B0]
0x18004977b  mov     rcx, rsi
0x18004977e  call    ?GetCnsFlights@ClientState@@QEAA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@2@@std@@XZ; ClientState::GetCnsFlights(void)
0x180049783  mov     rbx, [rax+8]
0x180049787  lea     rdx, [rbp+57h+var_B0]
0x18004978b  lea     rcx, [rbp+57h+var_B0]
0x18004978f  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>> &)
0x180049794  test    rbx, rbx
0x180049797  jnz     loc_18004981E
0x18004979d  lea     rcx, aOnesettingstip; "OneSettingsTIP::reason::CnsReconcileAll"...
0x1800497a4  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800497a9  mov     r8, rax
0x1800497ac  lea     edx, [rbx+18h]
0x1800497af  lea     rcx, [rbp+57h+var_80]
0x1800497b3  call    ?set_flag@?$test_watcher@V?$merged_data@U_tip_WOSC_TIP_CnsReconcileAndUpdate_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_TIP_CnsReconcileAndUpdate_attributes,tip2::test_data_basic>>::set_flag(ushort,char const *)
0x1800497b8  mov     rax, [rdi]
0x1800497bb  mov     rcx, rdi
0x1800497be  mov     rax, [rax+78h]
0x1800497c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800497c7  lea     rcx, aOnesettingstip_2; "OneSettingsTIP::reason::CompletedSucces"...
0x1800497ce  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800497d3  mov     r9, rax
0x1800497d6  mov     r8d, 1
0x1800497dc  mov     rcx, [rbp+57h+var_48]
0x1800497e0  add     rcx, 8
0x1800497e4  mov     dl, r8b
0x1800497e7  call    ?complete_without_lock@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<0,0,1>::complete_without_lock(TestCompletionKind,ushort,char const *)
0x1800497ec  nop
0x1800497ed  lea     rdx, [rbp+57h+var_C0]
0x1800497f1  lea     rcx, [rbp+57h+var_C0]
0x1800497f5  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>> &)
0x1800497fa  nop
0x1800497fb  lea     rdx, [rbp+57h+var_A0]
0x1800497ff  lea     rcx, [rbp+57h+var_A0]
0x180049803  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>> &)
0x180049808  nop
0x180049809  lea     rcx, [rbp+57h+arg_10]
0x18004980d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180049812  nop
0x180049813  mov     rcx, r13; string
0x180049816  call    cs:__imp_WindowsDeleteString
0x18004981c  jmp     short loc_180049881
0x18004981e  mov     rcx, [rbp+57h+var_C0]
0x180049822  mov     rcx, [rcx]
0x180049825  mov     [rbp+57h+arg_0], rcx
0x180049829  cmp     [rcx+19h], r15b
0x18004982d  jnz     short loc_1800497C7
0x18004982f  add     rcx, 20h ; ' '
0x180049833  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180049838  mov     rcx, [rdi]
0x18004983b  mov     r8, [rcx+70h]
0x18004983f  mov     rdx, rax
0x180049842  mov     rcx, rdi
0x180049845  mov     rax, r8
0x180049848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004984d  lea     rcx, [rbp+57h+arg_0]
0x180049851  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>,std::_Iterator_base0>::operator++(void)
0x180049856  mov     rcx, [rbp+57h+arg_0]
0x18004985a  jmp     short loc_180049829
0x18004985c  lea     rcx, aOnesettingstip_7; "OneSettingsTIP::reason::CnsCompletedCon"...
0x180049863  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180049868  mov     r8d, 15h
0x18004986e  mov     dl, 2
0x180049870  mov     rcx, [rbp+57h+var_48]
0x180049874  mov     r9, rax
0x180049877  add     rcx, 8
0x18004987b  call    ?complete_without_lock@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<0,0,1>::complete_without_lock(TestCompletionKind,ushort,char const *)
0x180049880  nop
0x180049881  lea     rcx, [rbp+57h+var_80]
0x180049885  call    ??1?$test_watcher@V?$merged_data@U_tip_WOSC_ForceRefreshOneSettings_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>>(void)
0x18004988a  xor     eax, eax
0x18004988c  add     rsp, 0B8h
0x180049893  pop     r15
0x180049895  pop     r14
0x180049897  pop     r13
0x180049899  pop     r12
0x18004989b  pop     rdi
0x18004989c  pop     rsi
0x18004989d  pop     rbx
0x18004989e  pop     rbp
0x18004989f  retn
0x1800498a0  mov     r9d, eax; char *
0x1800498a3  lea     r8, aOnecoreBaseFli_38; "onecore\\base\\flighting\\onesettings\\"...
0x1800498aa  mov     edx, 18Bh; void *
0x1800498af  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
