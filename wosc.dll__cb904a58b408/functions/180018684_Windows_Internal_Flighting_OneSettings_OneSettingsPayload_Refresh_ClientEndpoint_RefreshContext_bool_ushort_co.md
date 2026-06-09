# Windows::Internal::Flighting::OneSettings::OneSettingsPayload::Refresh(ClientEndpoint *,RefreshContext *,bool,ushort const *,bool,bool)

- ea: `0x180018684`
- end: `0x180018d9d`
- name: `?Refresh@OneSettingsPayload@OneSettings@Flighting@Internal@Windows@@AEAAXPEAVClientEndpoint@@PEAVRefreshContext@@_NPEBG22@Z`
- size: `1817`
- prototype: `void __fastcall(Windows::Internal::Flighting::OneSettings::OneSettingsPayload *this, struct ClientEndpoint *, struct RefreshContext *, char, const unsigned __int16 *, bool, bool)`
- caller_count: `1`
- callee_count: `36`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800195e0`

## callees

- `0x180003110`
- `0x180003210`
- `0x180009384`
- `0x18000fe24`
- `0x1800101fc`
- `0x180010278`
- `0x18001365c`
- `0x180013d80`
- `0x1800148e0`
- `0x180014b60`
- `0x180014d3c`
- `0x180014da4`
- `0x180014f30`
- `0x180014f6c`
- `0x180018684`
- `0x180019d84`
- `0x180019e18`
- `0x180019e48`
- `0x180019e68`
- `0x180019f58`
- `0x180019ff0`
- `0x18001a918`
- `0x180028830`
- `0x1800288a4`
- `0x180029cc8`
- `0x18002aee0`
- `0x18002af1c`
- `0x18002b29c`
- `0x18002d58c`
- `0x18002d5ac`
- `0x18002d720`
- `0x18002d8b8`
- `0x18002dc84`
- `0x180037c40`
- `0x1800498bc`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018b97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018c00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018b97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018c00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018a44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018a44`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180018a64`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180018a64`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrA` at `0x180018920`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrA` at `0x180018920`

## string_xrefs

- `0x180018c78`: `onecore\base\flighting\onesettings\libs\configurationsmanager\onesettingspayload.cpp`
- `0x180018d75`: `onecore\base\flighting\onesettings\libs\configurationsmanager\onesettingspayload.cpp`
- `0x180018d29`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180018d8a`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`

## pseudocode

```c
void __fastcall Windows::Internal::Flighting::OneSettings::OneSettingsPayload::Refresh(
        Windows::Internal::Flighting::OneSettings::OneSettingsPayload *this,
        struct ClientEndpoint *a2,
        struct RefreshContext *a3,
        char a4,
        const unsigned __int16 *a5,
        bool a6,
        bool a7)
{
  struct ClientEndpoint *v8; // r15
  Windows::Internal::Flighting::OneSettings::OneSettingsPayload *v9; // r14
  char v10; // di
  char *v11; // r13
  int v12; // eax
  ClientState *v13; // r10
  struct RefreshContext *v14; // r11
  __int64 v15; // rbx
  _QWORD *v16; // rax
  bool v17; // r12
  __int64 OneSettingsProvider; // rax
  HSTRING v19; // r9
  std::_Ref_count_base *v20; // rbx
  int v21; // r8d
  int v22; // r8d
  const unsigned __int16 *KnownEntityId; // rax
  const CHAR *v24; // rax
  PCSTR v25; // r8
  _QWORD *v26; // rax
  int v27; // eax
  const char *v28; // r9
  void *v29; // rcx
  __int64 OSVersionFromCtacOverride; // rax
  __int64 v31; // rbx
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rbx
  _QWORD *v36; // rax
  __int64 v37; // rax
  void (__fastcall ***v38)(_QWORD, __int64); // r9
  wil *v39; // rcx
  __int64 v40; // rdi
  HSTRING v41; // rbx
  __int64 v42; // rbx
  __int64 v43; // rax
  const unsigned __int16 *v44; // rax
  int v45; // eax
  void (__fastcall ***v46)(_QWORD); // rbx
  __int64 v47; // rdx
  const char *v48; // r9
  unsigned int v49; // ebx
  OneSettingsResponse *v50; // rax
  __int64 (__fastcall ***v51)(_QWORD); // rax
  __int64 v52; // rdx
  unsigned int v53; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-1A8h]
  int bIgnoreCasea; // [rsp+20h] [rbp-1A8h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-1A8h]
  __int64 PayloadHandler; // [rsp+28h] [rbp-1A0h]
  std::_Ref_count_base *v58; // [rsp+40h] [rbp-188h] BYREF
  const unsigned __int16 *ETag; // [rsp+48h] [rbp-180h] BYREF
  HSTRING string; // [rsp+50h] [rbp-178h] BYREF
  Windows::Internal::Flighting::OneSettings::OneSettingsPayload *v61; // [rsp+58h] [rbp-170h] BYREF
  char v62; // [rsp+60h] [rbp-168h]
  int *v63; // [rsp+68h] [rbp-160h] BYREF
  std::_Ref_count_base *v64; // [rsp+70h] [rbp-158h]
  struct RefreshContext *v65; // [rsp+78h] [rbp-150h]
  const unsigned __int16 *Name; // [rsp+80h] [rbp-148h] BYREF
  __int64 v67; // [rsp+88h] [rbp-140h] BYREF
  struct ClientEndpoint *v68; // [rsp+90h] [rbp-138h] BYREF
  Windows::Internal::Flighting::OneSettings::OneSettingsPayload *v69; // [rsp+98h] [rbp-130h]
  _QWORD *v70; // [rsp+A0h] [rbp-128h] BYREF
  __int128 v71; // [rsp+A8h] [rbp-120h] BYREF
  _BYTE v72[8]; // [rsp+B8h] [rbp-110h] BYREF
  std::_Ref_count_base *v73; // [rsp+C0h] [rbp-108h]
  __int128 v74; // [rsp+D8h] [rbp-F0h] BYREF
  __int64 v75; // [rsp+E8h] [rbp-E0h]
  __int64 v76; // [rsp+F0h] [rbp-D8h]
  _BYTE v77[128]; // [rsp+100h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  v65 = a3;
  v8 = a2;
  v9 = this;
  v69 = this;
  v68 = a2;
  ETag = (const unsigned __int16 *)a3;
  v61 = this;
  v10 = 1;
  v62 = 1;
  v11 = (char *)this + 48;
  if ( a5 )
  {
    v12 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            *(_QWORD *)v11 + 256LL,
            a5,
            -1);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x223,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)(unsigned int)v12,
        bIgnoreCasea);
  }
  if ( *((_BYTE *)v8 + 65) && !a4
    || (PayloadHandler = ClientEndpoint::GetPayloadHandler(v8, &v71),
        !(unsigned __int8)ClientState::PrepareForRefresh(
                            v13,
                            v14,
                            *((HSTRING *)v8 + 7),
                            *((_QWORD *)v8 + 18),
                            PayloadHandler,
                            a6)) )
  {
    v62 = 0;
    lambda_06024f6e3d3756a97a847ffa01993fe5_::operator()(&v61);
    return;
  }
  v15 = *(_QWORD *)v11;
  v16 = operator new(0x20u);
  v67 = (__int64)v16;
  *v16 = &ClientConfig::`vftable';
  v16[1] = v8;
  v16[2] = v15;
  v17 = a7;
  *((_BYTE *)v16 + 24) = a7;
  v70 = v16;
  v71 = 0;
  OneSettingsProvider = MakeOneSettingsProvider(v72);
  string = *(HSTRING *)OneSettingsProvider;
  v19 = string;
  v20 = *(std::_Ref_count_base **)(OneSettingsProvider + 8);
  v58 = v20;
  Name = (const unsigned __int16 *)v20;
  *(_QWORD *)OneSettingsProvider = 0;
  *(_QWORD *)(OneSettingsProvider + 8) = 0;
  *(_QWORD *)&v71 = v19;
  *((_QWORD *)&v71 + 1) = v20;
  if ( v73 )
  {
    std::_Ref_count_base::_Decref(v73);
    v19 = string;
  }
  (**(void (__fastcall ***)(HSTRING, int **, __int64))v19)(v19, &v63, v67);
  v21 = *v63;
  *(_DWORD *)(*(_QWORD *)v11 + 212LL) = *v63;
  *(_DWORD *)(*(_QWORD *)v11 + 216LL) = v63[1];
  *(_DWORD *)(*(_QWORD *)v11 + 220LL) = v63[2];
  v22 = v21 - 200;
  if ( !v22 )
  {
    if ( ClientEndpoint::GetKnownEntityId(v8) )
    {
      std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v77);
      KnownEntityId = ClientEndpoint::GetKnownEntityId(v8);
      std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::to_bytes(
        v77,
        v72,
        KnownEntityId);
      v67 = std::_String_val<std::_Simple_types<char>>::_Myptr(v63 + 4);
      v24 = (const CHAR *)std::_String_val<std::_Simple_types<char>>::_Myptr(v72);
      if ( !StrStrA(v25, v24) )
      {
        Name = ClientEndpoint::GetName(v8);
        OneSettingsClientTelemetry::KnownEntityIdNotFound<unsigned short const *,char const * &>(&Name, &v67);
        v48 = (const char *)(unsigned int)wil::verify_hresult<long>(2147549183LL, v47);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x26B,
          (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingspayload.cpp",
          v48,
          bIgnoreCaseb);
      }
      std::string::_Tidy_deallocate(v72);
      std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v77);
    }
    if ( ClientState::IsETagValidated(*((ClientState **)v9 + 6)) && !a7 )
    {
      v26 = (_QWORD *)ClientEndpoint::GetPayloadHandler(v8, v72);
      try
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 32LL))(*v26);
        if ( v73 )
          std::_Ref_count_base::_Decref(v73);
        v27 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                *((_QWORD *)v9 + 6) + 112LL,
                *(_QWORD *)(*((_QWORD *)v9 + 6) + 72LL),
                -1);
        if ( v27 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1BF,
            (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
            (const char *)(unsigned int)v27,
            bIgnoreCaseb);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x27A,
          (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingspayload.cpp",
          v28);
        v10 = 1;
        v17 = a7;
        v9 = v69;
        v8 = v68;
        v29 = (void *)ETag;
        v58 = (std::_Ref_count_base *)Name;
        goto LABEL_23;
      }
    }
    v29 = v65;
LABEL_23:
    v74 = 0;
    v75 = 0;
    v76 = 7;
    LOWORD(v74) = 0;
    if ( v17 )
    {
      OSVersionFromCtacOverride = RefreshContext::GetOSVersionFromCtacOverride(v29, v72);
      std::wstring::operator=(&v74, OSVersionFromCtacOverride);
      std::wstring::_Tidy_deallocate(v72);
      ETag = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v74);
      OneSettingsClientTelemetry::StagedCloudConfigsOsVersion<unsigned short const *>(&ETag);
    }
    ClientEndpoint::GetPayloadString(v8, &string);
    v31 = *((_QWORD *)v9 + 6);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v33 = *(const WCHAR **)(v31 + 304);
    if ( v33 && CompareStringOrdinal(v33, -1, StringRawBuffer, -1, 0) == 2 )
    {
      v10 = 0;
    }
    else
    {
      v34 = *((_QWORD *)v9 + 6);
      v35 = *(_QWORD *)(v34 + 288);
      if ( v35 )
      {
        if ( v75 )
          (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v35 + 8LL))(*(_QWORD *)(v34 + 288), &v74);
        (**(void (__fastcall ***)(__int64, _QWORD))v35)(v35, 0);
      }
    }
    try
    {
      if ( v75 )
      {
        v36 = (_QWORD *)ClientEndpoint::GetPayloadHandler(v8, v72);
        (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v36 + 8LL))(*v36, &v74);
        if ( v73 )
          std::_Ref_count_base::_Decref(v73);
      }
      ClientEndpoint::GetPayloadHandler(v8, v72);
      v37 = std::_String_val<std::_Simple_types<char>>::_Myptr(v63 + 4);
      (**v38)(v38, v37);
      v39 = v73;
      if ( v73 )
        std::_Ref_count_base::_Decref(v73);
    }
    catch ( ... )
    {
      v49 = wil::ResultFromCaughtException(v39);
      LODWORD(v58) = v49;
      v50 = (OneSettingsResponse *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::get(&v63);
      ETag = OneSettingsResponse::GetETag(v50);
      v51 = (__int64 (__fastcall ***)(_QWORD))wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::get(&v70);
      v68 = (struct ClientEndpoint *)(**v51)(v51);
      OneSettingsClientTelemetry::SettingsHandlerFailure<unsigned short const *,unsigned short const *,long const &>(
        &v68,
        &ETag,
        &v58);
      v53 = wil::verify_hresult<long>(v49, v52);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2A2,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingspayload.cpp",
        (const char *)v53,
        bIgnoreCase);
    }
    if ( v10 )
    {
      if ( v17 )
        goto LABEL_41;
      v40 = *((_QWORD *)v9 + 6);
      v41 = string;
      string = 0;
      WindowsDeleteString(*(HSTRING *)(v40 + 328));
      *(_QWORD *)(v40 + 328) = v41;
    }
    if ( !v17 )
    {
      v44 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v63 + 12);
      ClientState::SetETag(*((ClientState **)v9 + 6), v44);
      goto LABEL_43;
    }
LABEL_41:
    v42 = *((_QWORD *)v9 + 6);
    std::wstring::wstring(v72, &v74);
    v43 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v63 + 12);
    ClientState::SetETagStagedForVersion(v42, v43);
LABEL_43:
    WindowsDeleteString(string);
    string = 0;
    std::wstring::_Tidy_deallocate(&v74);
LABEL_44:
    ClientState::UpdateJsonString(
      *((struct Windows::Data::Json::IJsonObject **)v8 + 15),
      (struct Microsoft::WRL::Wrappers::HString *)(*((_QWORD *)v9 + 6) + 392LL));
    *(_DWORD *)(*((_QWORD *)v9 + 6) + 208LL) = v63[20];
    *(_QWORD *)(*((_QWORD *)v9 + 6) + 184LL) = *(_QWORD *)(*((_QWORD *)v9 + 6) + 192LL);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::GetImpl'::`2'::impl) )
    {
      v45 = CnsPayloadUtilities::ReconcileCnsFLights((char *)v9 + 48);
      if ( v45 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2C6,
          (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingspayload.cpp",
          (const char *)(unsigned int)v45,
          bIgnoreCaseb);
    }
    v10 = 0;
    v62 = 0;
    lambda_06024f6e3d3756a97a847ffa01993fe5_::operator()(&v61);
    v46 = (void (__fastcall ***)(_QWORD))*((_QWORD *)v8 + 16);
    if ( v46 && !ClientState::IsETagAcknowledged(*((ClientState **)v9 + 6)) && !v17 )
    {
      try
      {
        (**v46)(v46);
      }
      catch ( ... )
      {
        ETag = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*((_QWORD *)v69 + 6));
        OneSettingsClientTelemetry::FailedToNotifyClient<unsigned short const *>(&ETag);
        v10 = v62;
        v20 = (std::_Ref_count_base *)Name;
        goto LABEL_51;
      }
    }
    v20 = v58;
    goto LABEL_51;
  }
  if ( v22 == 104 )
    goto LABEL_44;
LABEL_51:
  if ( v64 )
    std::_Ref_count_base::_Decref(v64);
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
  std::unique_ptr<ClientConfig>::~unique_ptr<ClientConfig>(&v70);
  if ( v10 )
  {
    v62 = 0;
    lambda_06024f6e3d3756a97a847ffa01993fe5_::operator()(&v61);
  }
}

```

## disassembly

```asm
0x180018684  push    rbx
0x180018686  push    rsi
0x180018687  push    rdi
0x180018688  push    r12
0x18001868a  push    r13
0x18001868c  push    r14
0x18001868e  push    r15
0x180018690  sub     rsp, 190h
0x180018697  mov     rax, cs:__security_cookie
0x18001869e  xor     rax, rsp
0x1800186a1  mov     [rsp+1C8h+var_48], rax
0x1800186a9  mov     bl, r9b
0x1800186ac  mov     r11, r8
0x1800186af  mov     [rsp+1C8h+var_150], r8
0x1800186b4  mov     r15, rdx
0x1800186b7  mov     r14, rcx
0x1800186ba  mov     [rsp+1C8h+var_130], rcx
0x1800186c2  mov     [rsp+1C8h+var_138], rdx
0x1800186ca  mov     [rsp+1C8h+var_180], r8
0x1800186cf  mov     rdx, [rsp+1C8h+arg_20]
0x1800186d7  xor     esi, esi
0x1800186d9  mov     [rsp+1C8h+var_170], rcx
0x1800186de  mov     dil, 1
0x1800186e1  mov     [rsp+1C8h+var_168], dil
0x1800186e6  lea     r13, [rcx+30h]
0x1800186ea  test    rdx, rdx
0x1800186ed  jz      short loc_180018718
0x1800186ef  mov     rcx, [r13+0]
0x1800186f3  add     rcx, 100h
0x1800186fa  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800186fe  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180018703  mov     rcx, [rsp+1C8h]; this
0x18001870b  test    eax, eax
0x18001870d  js      loc_180018D26
0x180018713  mov     r11, [rsp+1C8h+var_150]
0x180018718  cmp     [r15+41h], sil
0x18001871c  jz      short loc_180018755
0x18001871e  test    bl, bl
0x180018720  jnz     short loc_180018755
0x180018722  mov     [rsp+1C8h+var_168], sil
0x180018727  lea     rcx, [rsp+1C8h+var_170]
0x18001872c  call    _lambda_06024f6e3d3756a97a847ffa01993fe5___operator__
0x180018731  nop
0x180018732  mov     rcx, [rsp+1C8h+var_48]
0x18001873a  xor     rcx, rsp; StackCookie
0x18001873d  call    __security_check_cookie
0x180018742  add     rsp, 190h
0x180018749  pop     r15
0x18001874b  pop     r14
0x18001874d  pop     r13
0x18001874f  pop     r12
0x180018751  pop     rdi
0x180018752  pop     rsi
0x180018753  pop     rbx
0x180018754  retn
0x180018755  mov     r10, [r13+0]
0x180018759  lea     rdx, [rsp+1C8h+var_120]
0x180018761  mov     rcx, r15
0x180018764  call    ?GetPayloadHandler@ClientEndpoint@@QEBA?AV?$shared_ptr@VIPayloadHandler@@@std@@XZ; ClientEndpoint::GetPayloadHandler(void)
0x180018769  mov     cl, [rsp+1C8h+arg_28]
0x180018770  mov     [rsp+1C8h+var_198], cl; bool
0x180018774  mov     [rsp+1C8h+var_1A0], rax; __int64
0x180018779  mov     rax, [r15+90h]
0x180018780  mov     qword ptr [rsp+1C8h+bIgnoreCase], rax; int
0x180018785  mov     r9b, bl
0x180018788  mov     r8, [r15+38h]; HSTRING
0x18001878c  mov     rdx, r11; struct RefreshContext *
0x18001878f  mov     rcx, r10; this
0x180018792  call    ?PrepareForRefresh@ClientState@@QEAA_NPEAVRefreshContext@@PEAUHSTRING__@@_NPEAVRefreshPolicy@@V?$shared_ptr@VIPayloadHandler@@@std@@2@Z; ClientState::PrepareForRefresh(RefreshContext *,HSTRING__ *,bool,RefreshPolicy *,std::shared_ptr<IPayloadHandler>,bool)
0x180018797  test    al, al
0x180018799  jnz     short loc_1800187AD
0x18001879b  mov     [rsp+1C8h+var_168], sil
0x1800187a0  lea     rcx, [rsp+1C8h+var_170]
0x1800187a5  call    _lambda_06024f6e3d3756a97a847ffa01993fe5___operator__
0x1800187aa  nop
0x1800187ab  jmp     short loc_180018732
0x1800187ad  mov     rbx, [r13+0]
0x1800187b1  mov     ecx, 20h ; ' '; Size
0x1800187b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800187bb  mov     [rsp+1C8h+var_140], rax
0x1800187c3  lea     rcx, ??_7ClientConfig@@6B@; const ClientConfig::`vftable'
0x1800187ca  mov     [rax], rcx
0x1800187cd  mov     [rax+8], r15
0x1800187d1  mov     [rax+10h], rbx
0x1800187d5  mov     r12b, [rsp+1C8h+arg_30]
0x1800187dd  mov     [rax+18h], r12b
0x1800187e1  mov     [rsp+1C8h+var_128], rax
0x1800187e9  xorps   xmm0, xmm0
0x1800187ec  movdqu  [rsp+1C8h+var_120], xmm0
0x1800187f5  lea     rcx, [rsp+1C8h+var_110]
0x1800187fd  call    ?MakeOneSettingsProvider@@YA?AV?$shared_ptr@VIOneSettingsProvider@@@std@@XZ; MakeOneSettingsProvider(void)
0x180018802  mov     r9, [rax]
0x180018805  mov     [rsp+1C8h+string], r9
0x18001880a  mov     rbx, [rax+8]
0x18001880e  mov     [rsp+1C8h+var_188], rbx
0x180018813  mov     [rsp+1C8h+var_148], rbx
0x18001881b  mov     [rax], rsi
0x18001881e  mov     [rax+8], rsi
0x180018822  mov     qword ptr [rsp+1C8h+var_120], r9
0x18001882a  mov     qword ptr [rsp+1C8h+var_120+8], rbx
0x180018832  mov     rcx, [rsp+1C8h+var_108]; this
0x18001883a  test    rcx, rcx
0x18001883d  jz      short loc_180018849
0x18001883f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018844  mov     r9, [rsp+1C8h+string]
0x180018849  mov     rax, [r9]
0x18001884c  mov     r8, [rsp+1C8h+var_140]
0x180018854  lea     rdx, [rsp+1C8h+var_160]
0x180018859  mov     rcx, r9
0x18001885c  mov     rax, [rax]
0x18001885f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018864  nop
0x180018865  mov     rax, [rsp+1C8h+var_160]
0x18001886a  mov     r8d, [rax]
0x18001886d  mov     rax, [r13+0]
0x180018871  mov     [rax+0D4h], r8d
0x180018878  mov     rdx, [r13+0]
0x18001887c  mov     rax, [rsp+1C8h+var_160]
0x180018881  mov     ecx, [rax+4]
0x180018884  mov     [rdx+0D8h], ecx
0x18001888a  mov     rdx, [r13+0]
0x18001888e  mov     rax, [rsp+1C8h+var_160]
0x180018893  mov     ecx, [rax+8]
0x180018896  mov     [rdx+0DCh], ecx
0x18001889c  sub     r8d, 0C8h
0x1800188a3  jz      short loc_1800188B4
0x1800188a5  cmp     r8d, 68h ; 'h'
0x1800188a9  jz      loc_180018C18
0x1800188af  jmp     loc_180018CCF
0x1800188b4  mov     rcx, r15; this
0x1800188b7  call    ?GetKnownEntityId@ClientEndpoint@@QEBAPEBGXZ; ClientEndpoint::GetKnownEntityId(void)
0x1800188bc  test    rax, rax
0x1800188bf  jz      loc_18001894A
0x1800188c5  lea     rcx, [rsp+1C8h+var_C8]
0x1800188cd  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1800188d2  nop
0x1800188d3  mov     rcx, r15; this
0x1800188d6  call    ?GetKnownEntityId@ClientEndpoint@@QEBAPEBGXZ; ClientEndpoint::GetKnownEntityId(void)
0x1800188db  mov     r8, rax
0x1800188de  lea     rdx, [rsp+1C8h+var_110]
0x1800188e6  lea     rcx, [rsp+1C8h+var_C8]
0x1800188ee  call    ?to_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEBG@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::to_bytes(ushort const *)
0x1800188f3  nop
0x1800188f4  mov     rcx, [rsp+1C8h+var_160]
0x1800188f9  add     rcx, 10h
0x1800188fd  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180018902  mov     r8, rax
0x180018905  mov     [rsp+1C8h+var_140], rax
0x18001890d  lea     rcx, [rsp+1C8h+var_110]
0x180018915  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18001891a  mov     rdx, rax; pszSrch
0x18001891d  mov     rcx, r8; pszFirst
0x180018920  call    cs:__imp_StrStrA
0x180018926  test    rax, rax
0x180018929  jz      loc_180018D3B
0x18001892f  lea     rcx, [rsp+1C8h+var_110]
0x180018937  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001893c  nop
0x18001893d  lea     rcx, [rsp+1C8h+var_C8]
0x180018945  call    ??1?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x18001894a  mov     rcx, [r14+30h]; this
0x18001894e  call    ?IsETagValidated@ClientState@@QEBA_NXZ; ClientState::IsETagValidated(void)
0x180018953  test    al, al
0x180018955  jz      short loc_1800189B4
0x180018957  test    r12b, r12b
0x18001895a  jnz     short loc_1800189B4
0x18001895c  lea     rdx, [rsp+1C8h+var_110]
0x180018964  mov     rcx, r15
0x180018967  call    ?GetPayloadHandler@ClientEndpoint@@QEBA?AV?$shared_ptr@VIPayloadHandler@@@std@@XZ; ClientEndpoint::GetPayloadHandler(void)
0x18001896c  nop
0x18001896d  mov     rcx, [rax]
0x180018970  mov     rax, [rcx]
0x180018973  mov     rax, [rax+20h]
0x180018977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001897c  nop
0x18001897d  mov     rcx, [rsp+1C8h+var_108]; this
0x180018985  test    rcx, rcx
0x180018988  jz      short loc_18001898F
0x18001898a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001898f  mov     rdx, [r14+30h]
0x180018993  lea     rcx, [rdx+70h]
0x180018997  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001899b  mov     rdx, [rdx+48h]
0x18001899f  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800189a4  mov     rcx, [rsp+1C8h]; this
0x1800189ac  test    eax, eax
0x1800189ae  js      loc_180018D87
0x1800189b4  mov     rcx, [rsp+1C8h+var_150]
0x1800189b9  xorps   xmm0, xmm0
0x1800189bc  movups  [rsp+1C8h+var_F0], xmm0
0x1800189c4  mov     [rsp+1C8h+var_E0], rsi
0x1800189cc  mov     [rsp+1C8h+var_D8], 7
0x1800189d8  mov     word ptr [rsp+1C8h+var_F0], si
0x1800189e0  test    r12b, r12b
0x1800189e3  jz      short loc_180018A2B
0x1800189e5  lea     rdx, [rsp+1C8h+var_110]
0x1800189ed  call    ?GetOSVersionFromCtacOverride@RefreshContext@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; RefreshContext::GetOSVersionFromCtacOverride(void)
0x1800189f2  mov     rdx, rax
0x1800189f5  lea     rcx, [rsp+1C8h+var_F0]
0x1800189fd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180018a02  lea     rcx, [rsp+1C8h+var_110]
0x180018a0a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018a0f  lea     rcx, [rsp+1C8h+var_F0]
0x180018a17  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018a1c  mov     [rsp+1C8h+var_180], rax
0x180018a21  lea     rcx, [rsp+1C8h+var_180]
0x180018a26  call    ??$StagedCloudConfigsOsVersion@PEBG@OneSettingsClientTelemetry@@SAX$$QEAPEBG@Z; OneSettingsClientTelemetry::StagedCloudConfigsOsVersion<ushort const *>(ushort const * &&)
0x180018a2b  lea     rdx, [rsp+1C8h+string]
0x180018a30  mov     rcx, r15
0x180018a33  call    ?GetPayloadString@ClientEndpoint@@QEBA?AVHString@Wrappers@WRL@Microsoft@@XZ; ClientEndpoint::GetPayloadString(void)
0x180018a38  nop
0x180018a39  mov     rbx, [r14+30h]
0x180018a3d  xor     edx, edx; length
0x180018a3f  mov     rcx, [rsp+1C8h+string]; string
0x180018a44  call    cs:__imp_WindowsGetStringRawBuffer
0x180018a4a  mov     rcx, [rbx+130h]; lpString1
0x180018a51  test    rcx, rcx
0x180018a54  jz      short loc_180018A6F
0x180018a56  mov     [rsp+1C8h+bIgnoreCase], esi; int
0x180018a5a  or      r9d, 0FFFFFFFFh; cchCount2
0x180018a5e  mov     r8, rax; lpString2
0x180018a61  or      edx, r9d; cchCount1
0x180018a64  call    cs:__imp_CompareStringOrdinal
0x180018a6a  cmp     eax, 2
0x180018a6d  jz      short loc_180018AE6
0x180018a6f  mov     rax, [r14+30h]
0x180018a73  mov     rbx, [rax+120h]
0x180018a7a  test    rbx, rbx
0x180018a7d  jz      short loc_180018AE9
0x180018a7f  cmp     [rsp+1C8h+var_E0], rsi
0x180018a87  jz      short loc_180018AA0
0x180018a89  mov     rax, [rbx]
0x180018a8c  lea     rdx, [rsp+1C8h+var_F0]
0x180018a94  mov     rcx, rbx
0x180018a97  mov     rax, [rax+8]
0x180018a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018aa0  mov     rax, [rbx]
0x180018aa3  xor     edx, edx
0x180018aa5  mov     rcx, rbx
0x180018aa8  mov     rax, [rax]
0x180018aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ab0  jmp     short loc_180018AE9
0x180018ab2  xor     esi, esi
0x180018ab4  mov     dil, 1
0x180018ab7  mov     r12b, [rsp+1C8h+arg_30]
0x180018abf  mov     r14, [rsp+1C8h+var_130]
0x180018ac7  mov     r15, [rsp+1C8h+var_138]
0x180018acf  mov     rcx, [rsp+1C8h+var_180]
0x180018ad4  mov     rax, [rsp+1C8h+var_148]
0x180018adc  mov     [rsp+1C8h+var_188], rax
0x180018ae1  jmp     loc_1800189B9
0x180018ae6  mov     dil, sil
0x180018ae9  cmp     [rsp+1C8h+var_E0], rsi
0x180018af1  jz      short loc_180018B2E
0x180018af3  lea     rdx, [rsp+1C8h+var_110]
0x180018afb  mov     rcx, r15
0x180018afe  call    ?GetPayloadHandler@ClientEndpoint@@QEBA?AV?$shared_ptr@VIPayloadHandler@@@std@@XZ; ClientEndpoint::GetPayloadHandler(void)
0x180018b03  nop
0x180018b04  mov     rcx, [rax]
0x180018b07  mov     rax, [rcx]
0x180018b0a  lea     rdx, [rsp+1C8h+var_F0]
0x180018b12  mov     rax, [rax+8]
0x180018b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b1b  nop
0x180018b1c  mov     rcx, [rsp+1C8h+var_108]; this
0x180018b24  test    rcx, rcx
0x180018b27  jz      short loc_180018B2E
0x180018b29  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018b2e  lea     rdx, [rsp+1C8h+var_110]
0x180018b36  mov     rcx, r15
0x180018b39  call    ?GetPayloadHandler@ClientEndpoint@@QEBA?AV?$shared_ptr@VIPayloadHandler@@@std@@XZ; ClientEndpoint::GetPayloadHandler(void)
0x180018b3e  nop
0x180018b3f  mov     r9, [rax]
0x180018b42  mov     rcx, [rsp+1C8h+var_160]
0x180018b47  add     rcx, 10h
0x180018b4b  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180018b50  mov     rcx, [r9]
0x180018b53  mov     r8, [rcx]
0x180018b56  mov     rdx, rax
0x180018b59  mov     rcx, r9
0x180018b5c  mov     rax, r8
0x180018b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b64  nop
0x180018b65  mov     rcx, [rsp+1C8h+var_108]; this
0x180018b6d  test    rcx, rcx
0x180018b70  jz      short loc_180018B78
0x180018b72  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018b77  nop
0x180018b78  test    dil, dil
0x180018b7b  jz      short loc_180018BA4
0x180018b7d  test    r12b, r12b
0x180018b80  jnz     short loc_180018BA9
0x180018b82  mov     rdi, [r14+30h]
0x180018b86  mov     rbx, [rsp+1C8h+string]
0x180018b8b  mov     [rsp+1C8h+string], rsi
0x180018b90  mov     rcx, [rdi+148h]; string
0x180018b97  call    cs:__imp_WindowsDeleteString
0x180018b9d  mov     [rdi+148h], rbx
0x180018ba4  test    r12b, r12b
0x180018ba7  jz      short loc_180018BE0
  ... truncated ...
```
