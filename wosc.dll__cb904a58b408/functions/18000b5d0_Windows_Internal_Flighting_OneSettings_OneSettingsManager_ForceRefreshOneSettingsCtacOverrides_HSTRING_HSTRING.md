# Windows::Internal::Flighting::OneSettings::OneSettingsManager::ForceRefreshOneSettingsCtacOverrides(HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *,Windows::Internal::Flighting::OneSettings::IOneSettingsPayload * *)

- ea: `0x18000b5d0`
- end: `0x18000b861`
- name: `?ForceRefreshOneSettingsCtacOverrides@OneSettingsManager@OneSettings@Flighting@Internal@Windows@@UEAAJPEAUHSTRING__@@0PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@5@PEAPEAUIOneSettingsPayload@2345@@Z`
- size: `657`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003110`
- `0x180005f50`
- `0x180007754`
- `0x18000943c`
- `0x180009a60`
- `0x180009ff0`
- `0x18000a148`
- `0x18000a594`
- `0x18000b0bc`
- `0x18000b5d0`
- `0x18000ea80`
- `0x18000ed34`
- `0x1800101fc`
- `0x1800106c8`
- `0x1800116f8`
- `0x18001262c`
- `0x1800222a4`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b713`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b73b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b749`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b713`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b73b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b749`

## string_xrefs

- `0x18000b836`: `onecore\base\flighting\onesettings\libs\configurationsmanager\onesettingsmanager.cpp`
- `0x18000b84e`: `onecore\base\flighting\onesettings\libs\configurationsmanager\onesettingsmanager.cpp`
- `0x18000b7c0`: `OneSettingsTIP::reason::CompletedSuccessfully`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::Flighting::OneSettings::OneSettingsManager::ForceRefreshOneSettingsCtacOverrides(
        __int64 a1,
        HSTRING a2,
        HSTRING a3,
        __int64 a4,
        volatile signed __int32 **a5)
{
  __int64 (__fastcall *v8)(__int64, __int64, _BYTE *); // rbx
  int v9; // eax
  int StringRawBuffer; // ebx
  int v11; // eax
  volatile signed __int32 *v12; // rax
  const char *v13; // rdx
  wil *v14; // rcx
  const char *v15; // rax
  __int64 v16; // rdx
  const char *v17; // r9
  __int64 result; // rax
  int v19; // ebx
  int v20; // edx
  const char *v21; // rax
  __int64 v22; // rdx
  int v23; // [rsp+20h] [rbp-208h]
  int v24; // [rsp+20h] [rbp-208h]
  _BYTE v25[8]; // [rsp+30h] [rbp-1F8h] BYREF
  volatile signed __int32 *v26; // [rsp+38h] [rbp-1F0h] BYREF
  void **v27; // [rsp+40h] [rbp-1E8h] BYREF
  _BYTE v28[48]; // [rsp+48h] [rbp-1E0h] BYREF
  volatile signed __int32 *v29; // [rsp+78h] [rbp-1B0h]
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-1A8h] BYREF
  __int64 v31; // [rsp+98h] [rbp-190h]
  _QWORD v32[42]; // [rsp+A0h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  *a5 = 0;
  v26 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes,tip2::test_data_basic>>::start(
    (__int64 *)&v26,
    (__int64)&hstringHeader);
  v27 = &tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes,tip2::test_data_basic>>::`vftable';
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v28,
    (struct wil::details::IFailureCallback *)&v27,
    0,
    1);
  v29 = v26;
  if ( v26 )
    _InterlockedIncrement(v26 + 84);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>,wil::err_returncode_policy>((void **)&v26);
  wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v32);
  v32[0] = &OneSettingsClientTelemetry::ForceRefreshOneSettingsCtacOverrides::`vftable';
  OneSettingsClientTelemetry::ForceRefreshOneSettingsCtacOverrides::StartActivity((OneSettingsClientTelemetry::ForceRefreshOneSettingsCtacOverrides *)v32);
  v25[0] = 0;
  v8 = *(__int64 (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)a4 + 64LL);
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"OSVersion", 0xAu, 9u);
  try
  {
    try
    {
      v9 = v8(a4, v31, v25);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5A,
          (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingsmanager.cpp",
          (const char *)(unsigned int)v9,
          v24);
      if ( !v25[0] )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5B,
          (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingsmanager.cpp",
          (const char *)0x80070057LL,
          v24);
      hstringHeader.Reserved.Reserved1 = (PVOID)WindowsGetStringRawBuffer(a2, 0);
      OneSettingsClientTelemetry::ForceRefreshOneSettingsCtacOverrides::RefreshApp<unsigned short const *>(
        v32,
        &hstringHeader);
      StringRawBuffer = (unsigned int)WindowsGetStringRawBuffer(a3, 0);
      v11 = (unsigned int)WindowsGetStringRawBuffer(a2, 0);
      EndpointManager::GetAppPayloadRefreshed((__int64)&v26, v11, StringRawBuffer, 1, a4);
      v12 = v26;
      v26 = 0;
      *a5 = v12;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    }
    catch ( ... )
    {
      v19 = wil::ResultFromCaughtException(v14);
      LODWORD(v26) = v19;
      if ( TelemetryHelpers::IsIgnorableError((TelemetryHelpers *)(unsigned int)v19, v20) )
      {
        v21 = tip2::details::reason_string((tip2::details *)"OneSettingsTIP::reason::IgnorableError", v13);
        LOBYTE(v22) = 4;
        tip2::details::shared_data<0,0,1>::complete_without_lock(v29 + 2, v22, 2, v21);
        if ( v19 < 0 )
          goto LABEL_13;
LABEL_16:
        goto LABEL_7;
      }
      if ( v19 >= 0 )
        goto LABEL_16;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingsmanager.cpp",
        (const char *)(unsigned int)v19,
        v23);
LABEL_13:
      OneSettingsClientTelemetry::ForceRefreshOneSettingsCtacOverrides::~ForceRefreshOneSettingsCtacOverrides((OneSettingsClientTelemetry::ForceRefreshOneSettingsCtacOverrides *)v32);
      tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>>(&v27);
      return (unsigned int)v26;
    }
LABEL_7:
    v15 = tip2::details::reason_string((tip2::details *)"OneSettingsTIP::reason::CompletedSuccessfully", v13);
    LOBYTE(v16) = 1;
    tip2::details::shared_data<0,0,1>::complete_without_lock(v29 + 2, v16, 1, v15);
    wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::Stop(v32);
    OneSettingsClientTelemetry::ForceRefreshOneSettingsCtacOverrides::~ForceRefreshOneSettingsCtacOverrides((OneSettingsClientTelemetry::ForceRefreshOneSettingsCtacOverrides *)v32);
    tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>>(&v27);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x69,
                           (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingsmanager.cpp",
                           v17);
  }
  return result;
}

```

## disassembly

```asm
0x18000b5d0  push    rbx
0x18000b5d2  push    rsi
0x18000b5d3  push    rdi
0x18000b5d4  push    r14
0x18000b5d6  push    r15
0x18000b5d8  sub     rsp, 200h
0x18000b5df  mov     rax, cs:__security_cookie
0x18000b5e6  xor     rax, rsp
0x18000b5e9  mov     [rsp+228h+var_38], rax
0x18000b5f1  mov     rsi, r9
0x18000b5f4  mov     r15, r8
0x18000b5f7  mov     r14, rdx
0x18000b5fa  mov     rdi, [rsp+228h+arg_20]
0x18000b602  mov     qword ptr [rdi], 0
0x18000b609  mov     [rsp+228h+var_1F0], 0
0x18000b612  lea     rdx, [rsp+228h+hstringHeader]
0x18000b61a  lea     rcx, [rsp+228h+var_1F0]
0x18000b61f  call    ?start@?$tip_test@V?$merged_data@U_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes,tip2::test_data_basic>>::start(void)
0x18000b624  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes,tip2::test_data_basic>>::`vftable'
0x18000b62b  mov     [rsp+228h+var_1E8], rax
0x18000b630  mov     r9b, 1; bool
0x18000b633  xor     r8d, r8d; struct wil::CallContextInfo *
0x18000b636  lea     rdx, [rsp+228h+var_1E8]; struct wil::details::IFailureCallback *
0x18000b63b  lea     rcx, [rsp+228h+var_1E0]; this
0x18000b640  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x18000b645  mov     rax, [rsp+228h+var_1F0]
0x18000b64a  mov     [rsp+228h+var_1B0], rax
0x18000b64f  test    rax, rax
0x18000b652  jz      short loc_18000B65B
0x18000b654  lock inc dword ptr [rax+150h]
0x18000b65b  lea     rcx, [rsp+228h+var_1F0]
0x18000b660  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WOSC_ForceRefreshOneSettings_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>,wil::err_returncode_policy>(void)
0x18000b665  nop
0x18000b666  lea     rdx, aForcerefreshon_0; "ForceRefreshOneSettingsCtacOverrides"
0x18000b66d  lea     rcx, [rsp+228h+var_188]; struct wil::details::IFailureCallback *
0x18000b675  call    ??0?$ActivityBase@VWoscLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0IAAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000b67a  lea     rax, ??_7ForceRefreshOneSettingsCtacOverrides@OneSettingsClientTelemetry@@6B@; const OneSettingsClientTelemetry::ForceRefreshOneSettingsCtacOverrides::`vftable'
0x18000b681  mov     [rsp+228h+var_188], rax
0x18000b689  lea     rcx, [rsp+228h+var_188]; this
0x18000b691  call    ?StartActivity@ForceRefreshOneSettingsCtacOverrides@OneSettingsClientTelemetry@@QEAAXXZ; OneSettingsClientTelemetry::ForceRefreshOneSettingsCtacOverrides::StartActivity(void)
0x18000b696  nop
0x18000b697  mov     [rsp+228h+var_1F8], 0
0x18000b69c  mov     rax, [rsi]
0x18000b69f  mov     rbx, [rax+40h]
0x18000b6a3  mov     [rsp+228h+var_190], 0
0x18000b6af  mov     r9d, 9; unsigned int
0x18000b6b5  lea     r8d, [r9+1]; unsigned int
0x18000b6b9  lea     rdx, sourceString; "OSVersion"
0x18000b6c0  lea     rcx, [rsp+228h+hstringHeader]; hstringHeader
0x18000b6c8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000b6cd  nop
0x18000b6ce  lea     r8, [rsp+228h+var_1F8]
0x18000b6d3  mov     rdx, [rsp+228h+var_190]
0x18000b6db  mov     rcx, rsi
0x18000b6de  mov     rax, rbx
0x18000b6e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6e6  mov     rcx, [rsp+228h]; this
0x18000b6ee  test    eax, eax
0x18000b6f0  js      loc_18000B833
0x18000b6f6  cmp     [rsp+228h+var_1F8], 0
0x18000b6fb  setz    al
0x18000b6fe  mov     rcx, [rsp+228h]; this
0x18000b706  test    al, al
0x18000b708  jnz     loc_18000B848
0x18000b70e  xor     edx, edx; length
0x18000b710  mov     rcx, r14; string
0x18000b713  call    cs:__imp_WindowsGetStringRawBuffer
0x18000b719  mov     qword ptr [rsp+228h+hstringHeader.Reserved], rax
0x18000b721  lea     rdx, [rsp+228h+hstringHeader]
0x18000b729  lea     rcx, [rsp+228h+var_188]
0x18000b731  call    ??$RefreshApp@PEBG@ForceRefreshOneSettingsCtacOverrides@OneSettingsClientTelemetry@@QEAAX$$QEAPEBG@Z; OneSettingsClientTelemetry::ForceRefreshOneSettingsCtacOverrides::RefreshApp<ushort const *>(ushort const * &&)
0x18000b736  xor     edx, edx; length
0x18000b738  mov     rcx, r15; string
0x18000b73b  call    cs:__imp_WindowsGetStringRawBuffer
0x18000b741  mov     rbx, rax
0x18000b744  xor     edx, edx; length
0x18000b746  mov     rcx, r14; string
0x18000b749  call    cs:__imp_WindowsGetStringRawBuffer
0x18000b74f  mov     qword ptr [rsp+228h+var_208], rsi
0x18000b754  mov     r9b, 1
0x18000b757  mov     r8, rbx
0x18000b75a  mov     rdx, rax
0x18000b75d  lea     rcx, [rsp+228h+var_1F0]
0x18000b762  call    ?GetAppPayloadRefreshed@EndpointManager@@SA?AV?$ComPtr@VOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@PEBG0_NPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Z; EndpointManager::GetAppPayloadRefreshed(ushort const *,ushort const *,bool,Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *)
0x18000b767  mov     rax, [rsp+228h+var_1F0]
0x18000b76c  mov     [rsp+228h+var_1F0], 0
0x18000b775  mov     [rdi], rax
0x18000b778  lea     rcx, [rsp+228h+var_1F0]
0x18000b77d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000b782  jmp     short loc_18000B7C0
0x18000b784  lea     rcx, [rsp+228h+var_188]; this
0x18000b78c  call    ??1ForceRefreshOneSettingsCtacOverrides@OneSettingsClientTelemetry@@QEAA@XZ; OneSettingsClientTelemetry::ForceRefreshOneSettingsCtacOverrides::~ForceRefreshOneSettingsCtacOverrides(void)
0x18000b791  nop
0x18000b792  lea     rcx, [rsp+228h+var_1E8]
0x18000b797  call    ??1?$test_watcher@V?$merged_data@U_tip_WOSC_ForceRefreshOneSettings_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>>(void)
0x18000b79c  mov     eax, dword ptr [rsp+228h+var_1F0]
0x18000b7a0  jmp     short loc_18000B814
0x18000b7a2  lea     rcx, [rsp+228h+var_188]; this
0x18000b7aa  call    ??1ForceRefreshOneSettingsCtacOverrides@OneSettingsClientTelemetry@@QEAA@XZ; OneSettingsClientTelemetry::ForceRefreshOneSettingsCtacOverrides::~ForceRefreshOneSettingsCtacOverrides(void)
0x18000b7af  nop
0x18000b7b0  lea     rcx, [rsp+228h+var_1E8]
0x18000b7b5  call    ??1?$test_watcher@V?$merged_data@U_tip_WOSC_ForceRefreshOneSettings_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>>(void)
0x18000b7ba  mov     eax, dword ptr [rsp+228h+var_1F0]
0x18000b7be  jmp     short loc_18000B814
0x18000b7c0  lea     rcx, aOnesettingstip_2; "OneSettingsTIP::reason::CompletedSucces"...
0x18000b7c7  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000b7cc  mov     r9, rax
0x18000b7cf  mov     r8d, 1
0x18000b7d5  mov     rcx, [rsp+228h+var_1B0]
0x18000b7da  add     rcx, 8
0x18000b7de  mov     dl, r8b
0x18000b7e1  call    ?complete_without_lock@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<0,0,1>::complete_without_lock(TestCompletionKind,ushort,char const *)
0x18000b7e6  lea     rcx, [rsp+228h+var_188]
0x18000b7ee  call    ?Stop@?$ActivityBase@VWoscLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0IAAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000b7f3  nop
0x18000b7f4  lea     rcx, [rsp+228h+var_188]; this
0x18000b7fc  call    ??1ForceRefreshOneSettingsCtacOverrides@OneSettingsClientTelemetry@@QEAA@XZ; OneSettingsClientTelemetry::ForceRefreshOneSettingsCtacOverrides::~ForceRefreshOneSettingsCtacOverrides(void)
0x18000b801  nop
0x18000b802  lea     rcx, [rsp+228h+var_1E8]
0x18000b807  call    ??1?$test_watcher@V?$merged_data@U_tip_WOSC_ForceRefreshOneSettings_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>>(void)
0x18000b80c  xor     eax, eax
0x18000b80e  jmp     short loc_18000B814
0x18000b810  mov     eax, dword ptr [rsp+228h+var_1F0]
0x18000b814  mov     rcx, [rsp+228h+var_38]
0x18000b81c  xor     rcx, rsp; StackCookie
0x18000b81f  call    __security_check_cookie
0x18000b824  add     rsp, 200h
0x18000b82b  pop     r15
0x18000b82d  pop     r14
0x18000b82f  pop     rdi
0x18000b830  pop     rsi
0x18000b831  pop     rbx
0x18000b832  retn
0x18000b833  mov     r9d, eax; char *
0x18000b836  lea     r8, aOnecoreBaseFli_15; "onecore\\base\\flighting\\onesettings\\"...
0x18000b83d  mov     edx, 5Ah ; 'Z'; void *
0x18000b842  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000b848  mov     r9d, 80070057h; char *
0x18000b84e  lea     r8, aOnecoreBaseFli_15; "onecore\\base\\flighting\\onesettings\\"...
0x18000b855  mov     edx, 5Bh ; '['; void *
0x18000b85a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
