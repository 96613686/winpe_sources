# FailoverToast::CreateToast(bool,unsigned __int64)

- ea: `0x1800d5df8`
- end: `0x1800d65b7`
- name: `?CreateToast@FailoverToast@@AEAA?AUToast@@_N_K@Z`
- size: `1983`
- prototype: ``
- caller_count: `1`
- callee_count: `37`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180067e14`

## callees

- `0x180013afc`
- `0x180019434`
- `0x18002ab74`
- `0x180034470`
- `0x180058768`
- `0x1800693d8`
- `0x18006adf0`
- `0x180077b14`
- `0x18007b11c`
- `0x18007b57c`
- `0x18007f7b0`
- `0x180080650`
- `0x180084f50`
- `0x180085bc4`
- `0x1800b5e50`
- `0x1800b6398`
- `0x1800d0c38`
- `0x1800d0cac`
- `0x1800d0d48`
- `0x1800d0de4`
- `0x1800d0e80`
- `0x1800d35c0`
- `0x1800d362c`
- `0x1800d4468`
- `0x1800d4564`
- `0x1800d4af8`
- `0x1800d4b50`
- `0x1800d4ba8`
- `0x1800d4c00`
- `0x1800d51bc`
- `0x1800d57c4`
- `0x1800d5df8`
- `0x1800d6760`
- `0x1800d6e04`
- `0x1800da4c8`
- `0x1800eaa80`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800d5edb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800d5f16`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800d5f4f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800d5f88`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800d5edb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800d5f16`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800d5f4f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800d5f88`

## string_xrefs

- `0x1800d5eee`: `onecoreuap\net\wcm\service\base\toast\failovertoast.cpp`
- `0x1800d5f27`: `onecoreuap\net\wcm\service\base\toast\failovertoast.cpp`
- `0x1800d5f60`: `onecoreuap\net\wcm\service\base\toast\failovertoast.cpp`
- `0x1800d5f99`: `onecoreuap\net\wcm\service\base\toast\failovertoast.cpp`
- `0x1800d609c`: `        <binding template="ToastGeneric">`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
_QWORD *__fastcall FailoverToast::CreateToast(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  const char *v7; // r9
  const char *v8; // r9
  const char *v9; // r9
  const char *v10; // r9
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  _QWORD *v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rdi
  unsigned int v24; // eax
  __int64 v25; // rbx
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rdi
  unsigned int v29; // eax
  __int64 v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rdi
  unsigned int v34; // eax
  __int64 v35; // rbx
  __int64 v36; // rax
  __int64 v38; // [rsp+20h] [rbp-E0h] BYREF
  int v39; // [rsp+28h] [rbp-D8h]
  __int128 v40; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v41; // [rsp+40h] [rbp-C0h]
  __int64 v42; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v44[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v45; // [rsp+70h] [rbp-90h]
  __int64 v46; // [rsp+80h] [rbp-80h] BYREF
  __int64 v47; // [rsp+88h] [rbp-78h]
  std::_Ref_count_base *v48[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v49; // [rsp+B0h] [rbp-50h]
  struct IUnknown v50; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v51[4]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v52[32]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v53[32]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v54[40]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v55[8]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v56[232]; // [rsp+158h] [rbp+58h] BYREF
  WCHAR Buffer[512]; // [rsp+240h] [rbp+140h] BYREF
  WCHAR v58[512]; // [rsp+640h] [rbp+540h] BYREF
  WCHAR v59[512]; // [rsp+A40h] [rbp+940h] BYREF
  WCHAR v60[512]; // [rsp+E40h] [rbp+D40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1288h] [rbp+1188h]

  v49 = a2;
  v39 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, &WPP_36ba8b8ab71539cb7e9a28af59916125_Traceguids);
  }
  memset_0(Buffer, 0, sizeof(Buffer));
  memset_0(v58, 0, sizeof(v58));
  memset_0(v59, 0, sizeof(v59));
  memset_0(v60, 0, sizeof(v60));
  if ( !LoadStringW(g_instanceHandle, 0x1004u, Buffer, 512) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x12B,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\toast\\failovertoast.cpp",
      v7);
  if ( !LoadStringW(g_instanceHandle, 0x1005u, v58, 512) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x12C,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\toast\\failovertoast.cpp",
      v8);
  if ( !LoadStringW(g_instanceHandle, 0x1006u, v59, 512) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x12D,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\toast\\failovertoast.cpp",
      v9);
  if ( !LoadStringW(g_instanceHandle, 0x1007u, v60, 512) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x12F,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\toast\\failovertoast.cpp",
      v10);
  std::wstring::wstring(v44, Buffer);
  XmlBuilder::EscapeString(v54, v44);
  ProfileRoutePolicyData::~ProfileRoutePolicyData((ProfileRoutePolicyData *)v44);
  std::wstring::wstring(&v40, v58);
  XmlBuilder::EscapeString(v51, &v40);
  ProfileRoutePolicyData::~ProfileRoutePolicyData((ProfileRoutePolicyData *)&v40);
  std::wstring::wstring(v44, v59);
  XmlBuilder::EscapeString(v53, v44);
  ProfileRoutePolicyData::~ProfileRoutePolicyData((ProfileRoutePolicyData *)v44);
  std::wstring::wstring(&v40, v60);
  XmlBuilder::EscapeString(v52, &v40);
  ProfileRoutePolicyData::~ProfileRoutePolicyData((ProfileRoutePolicyData *)&v40);
  ___call_factory_cast_P6A_AUXmlDocument_Dom_Xml_Data_Windows_winrt__AEBUIActivationFactory_Foundation_56__ZU123456_U7856_V_lambda_31____0___0123456_QEAA_XZ__impl_winrt__YA_A_P__QEAV_lambda_31____0___0XmlDocument_Dom_Xml_Data_Windows_1_QEAA_XZ__Z(&v50);
  memset_0(v55, 0, 0xE8u);
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v55);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v55, L"<toast scenario=\"Reminder\">");
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v55, L"    <visual>");
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v55, L"        <binding template=\"ToastGeneric\">");
  v11 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v55, L"            <text hint-style=\"body\">");
  v12 = std::operator<<<unsigned short>(v11, v54);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v12, L"</text>");
  v13 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v55, L"            <text>");
  v14 = v51;
  if ( v51[3] > 7u )
    v14 = (_QWORD *)v51[0];
  v15 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v13, v14);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v15, L"</text>");
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v55, L"        </binding>");
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v55, L"    </visual>");
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v55, L"    <actions>");
  v16 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          v55,
          L"        <action activationType=\"Background\" arguments=\"turnOn\" content=\"");
  v17 = std::operator<<<unsigned short>(v16, v53);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v17, L"\"/>");
  v18 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          v55,
          L"        <action activationType=\"Background\" arguments=\"fewerNotifications\" content=\"");
  v19 = std::operator<<<unsigned short>(v18, v52);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v19, L"\"/>");
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v55, L"    </actions>");
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v55, L"</toast>");
  v40 = 0;
  v41 = 0;
  std::wstring::_Construct_empty(&v40);
  v39 = 8;
  std::basic_stringbuf<unsigned short>::_Get_buffer_view(v56, v44);
  if ( v44[0] )
    std::wstring::assign(&v40, v44[0], v44[1]);
  v39 = 4;
  winrt::param::hstring::hstring(&v46, &v40);
  winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(
    &v50,
    &v46);
  ProfileRoutePolicyData::~ProfileRoutePolicyData((ProfileRoutePolicyData *)&v40);
  v20 = `winrt::Windows::UI::Notifications::ToastNotification::ToastNotification'::`1'::_lambda_25__::_lambda_25__(
          &v38,
          &v50);
  ___call_factory_UToastNotification_Notifications_UI_Windows_winrt__UIToastNotificationFactory_2345_V_lambda_25____0___012345_QEAA_AEBUXmlDocument_Dom_Xml_Data_45__Z__impl_winrt__YA_A_P__QEAV_lambda_25____0___0ToastNotification_Notifications_UI_Windows_1_QEAA_AEBUXmlDocument_Dom_Xml_Data_61__Z__Z(
    (__int64)&v43,
    v20);
  v21 = v43;
  *a2 = v43;
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
  a2[1] = 0;
  a2[2] = 0;
  a2[3] = 0;
  a2[4] = 0;
  a2[5] = 0;
  a2[6] = 0;
  a2[7] = 0;
  a2[8] = 0;
  a2[9] = 0;
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v43);
  v39 = 5;
  winrt::impl::consume_Windows_UI_Notifications_IToastNotification6<winrt::Windows::UI::Notifications::ToastNotification>::ExpiresOnReboot(a2);
  *(_OWORD *)v48 = 0;
  std::weak_ptr<wcm::pdc::Activation>::weak_ptr<wcm::pdc::Activation>(v48, a1);
  std::weak_ptr<wcm::pdc::Activation>::weak_ptr<wcm::pdc::Activation>(v44, v48);
  v45 = a4;
  winrt::Windows::Foundation::TypedEventHandler_winrt::Windows::UI::Notifications::ToastNotification_winrt::Windows::Foundation::IInspectable_::TypedEventHandler_winrt::Windows::UI::Notifications::ToastNotification_winrt::Windows::Foundation::IInspectable___FailoverToast::CreateToast_::_2_::_lambda_1___(
    &v38,
    v44);
  v42 = 0;
  v22 = *a2;
  LODWORD(v40) = 3065;
  *((_QWORD *)&v40 + 1) = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.UI.Notifications.h";
  *(_QWORD *)&v41 = 0;
  v23 = v38;
  v24 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v22 + 88LL))(v22, v38, &v42);
  winrt::check_hresult(&v43, v24, &v40);
  v25 = v42;
  winrt::weak_ref<winrt::Windows::UI::Notifications::IToastNotification>::weak_ref<winrt::Windows::UI::Notifications::IToastNotification>(
    &v46,
    a2);
  v47 = v25;
  v39 = 101;
  v26 = v46;
  v46 = 0;
  *(_QWORD *)&v40 = v26;
  *((_QWORD *)&v40 + 1) =  winrt::impl::abi<winrt::Windows::UI::Notifications::IToastNotification,void>::type::`vcall'{96,{flat}};
  *(_QWORD *)&v41 = v25;
  winrt::event_revoker<winrt::Windows::UI::Notifications::IToastNotification>::operator=(a2 + 1, &v40);
  winrt::event_revoker<winrt::Windows::UI::Notifications::IToastNotification>::~event_revoker<winrt::Windows::UI::Notifications::IToastNotification>(&v40);
  __1__event_revoker_UIToastNotification_Notifications_UI_Windows_winrt___MP8type___abi_UIToastNotification_Notifications_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BGA_AA_impl_winrt__QEAA_XZ(&v46);
  if ( v23 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v38);
  std::weak_ptr<wcm::pdc::Activation>::weak_ptr<wcm::pdc::Activation>(v44, v48);
  v45 = a4;
  winrt::Windows::Foundation::TypedEventHandler_winrt::Windows::UI::Notifications::ToastNotification_winrt::Windows::UI::Notifications::ToastDismissedEventArgs_::TypedEventHandler_winrt::Windows::UI::Notifications::ToastNotification_winrt::Windows::UI::Notifications::ToastDismissedEventArgs___FailoverToast::CreateToast_::_2_::_lambda_2___(
    &v42,
    v44);
  v38 = 0;
  v27 = *a2;
  LODWORD(v40) = 3027;
  *((_QWORD *)&v40 + 1) = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.UI.Notifications.h";
  *(_QWORD *)&v41 = 0;
  v28 = v42;
  v29 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v27 + 72LL))(v27, v42, &v38);
  winrt::check_hresult(&v43, v29, &v40);
  v30 = v38;
  winrt::weak_ref<winrt::Windows::UI::Notifications::IToastNotification>::weak_ref<winrt::Windows::UI::Notifications::IToastNotification>(
    &v46,
    a2);
  v47 = v30;
  v39 = 485;
  v31 = v46;
  v46 = 0;
  *(_QWORD *)&v40 = v31;
  *((_QWORD *)&v40 + 1) =  winrt::impl::abi<winrt::Windows::UI::Notifications::IToastNotification,void>::type::`vcall'{80,{flat}};
  *(_QWORD *)&v41 = v30;
  winrt::event_revoker<winrt::Windows::UI::Notifications::IToastNotification>::operator=(a2 + 4, &v40);
  winrt::event_revoker<winrt::Windows::UI::Notifications::IToastNotification>::~event_revoker<winrt::Windows::UI::Notifications::IToastNotification>(&v40);
  __1__event_revoker_UIToastNotification_Notifications_UI_Windows_winrt___MP8type___abi_UIToastNotification_Notifications_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BFA_AA_impl_winrt__QEAA_XZ(&v46);
  if ( v28 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v42);
  std::weak_ptr<wcm::pdc::Activation>::weak_ptr<wcm::pdc::Activation>(v44, v48);
  v45 = a4;
  winrt::Windows::Foundation::TypedEventHandler_winrt::Windows::UI::Notifications::ToastNotification_winrt::Windows::UI::Notifications::ToastFailedEventArgs_::TypedEventHandler_winrt::Windows::UI::Notifications::ToastNotification_winrt::Windows::UI::Notifications::ToastFailedEventArgs___FailoverToast::CreateToast_::_2_::_lambda_3___(
    &v42,
    v44);
  v38 = 0;
  v32 = *a2;
  LODWORD(v40) = 3103;
  *((_QWORD *)&v40 + 1) = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.UI.Notifications.h";
  *(_QWORD *)&v41 = 0;
  v33 = v42;
  v34 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v32 + 104LL))(v32, v42, &v38);
  winrt::check_hresult(&v43, v34, &v40);
  v35 = v38;
  winrt::weak_ref<winrt::Windows::UI::Notifications::IToastNotification>::weak_ref<winrt::Windows::UI::Notifications::IToastNotification>(
    &v46,
    a2);
  v47 = v35;
  v36 = v46;
  v46 = 0;
  *(_QWORD *)&v40 = v36;
  *((_QWORD *)&v40 + 1) =  winrt::impl::abi<winrt::Windows::UI::Notifications::IToastNotification,void>::type::`vcall'{112,{flat}};
  *(_QWORD *)&v41 = v35;
  winrt::event_revoker<winrt::Windows::UI::Notifications::IToastNotification>::operator=(a2 + 7, &v40);
  winrt::event_revoker<winrt::Windows::UI::Notifications::IToastNotification>::~event_revoker<winrt::Windows::UI::Notifications::IToastNotification>(&v40);
  __1__event_revoker_UIToastNotification_Notifications_UI_Windows_winrt___MP8type___abi_UIToastNotification_Notifications_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BHA_AA_impl_winrt__QEAA_XZ(&v46);
  if ( v33 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v42);
  if ( v48[1] )
    std::_Ref_count_base::_Decwref(v48[1]);
  std::basic_ostringstream<unsigned short>::`vbase destructor'(v55);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v50);
  ProfileRoutePolicyData::~ProfileRoutePolicyData((ProfileRoutePolicyData *)v52);
  ProfileRoutePolicyData::~ProfileRoutePolicyData((ProfileRoutePolicyData *)v53);
  ProfileRoutePolicyData::~ProfileRoutePolicyData((ProfileRoutePolicyData *)v51);
  ProfileRoutePolicyData::~ProfileRoutePolicyData((ProfileRoutePolicyData *)v54);
  return a2;
}

```

## disassembly

```asm
0x1800d5df8  mov     [rsp-8+arg_10], rbx
0x1800d5dfd  push    rbp
0x1800d5dfe  push    rsi
0x1800d5dff  push    rdi
0x1800d5e00  push    r12
0x1800d5e02  push    r13
0x1800d5e04  push    r14
0x1800d5e06  push    r15
0x1800d5e08  lea     rbp, [rsp-1150h]
0x1800d5e10  mov     eax, 1250h
0x1800d5e15  call    _alloca_probe
0x1800d5e1a  sub     rsp, rax
0x1800d5e1d  mov     rax, cs:__security_cookie
0x1800d5e24  xor     rax, rsp
0x1800d5e27  mov     [rbp+1180h+var_40], rax
0x1800d5e2e  mov     r13, r9
0x1800d5e31  mov     r14, rdx
0x1800d5e34  mov     rbx, rcx
0x1800d5e37  mov     [rbp+1180h+var_11D0], rdx
0x1800d5e3b  mov     [rsp+1280h+var_1258], 0
0x1800d5e43  lea     rax, WPP_GLOBAL_Control
0x1800d5e4a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d5e51  cmp     rcx, rax
0x1800d5e54  jz      short loc_1800D5E77
0x1800d5e56  cmp     byte ptr [rcx+19h], 4
0x1800d5e5a  jb      short loc_1800D5E77
0x1800d5e5c  test    byte ptr [rcx+1Ch], 1
0x1800d5e60  jz      short loc_1800D5E77
0x1800d5e62  mov     edx, 12h
0x1800d5e67  lea     r8, WPP_36ba8b8ab71539cb7e9a28af59916125_Traceguids
0x1800d5e6e  mov     rcx, [rcx+10h]
0x1800d5e72  call    WPP_SF_
0x1800d5e77  mov     edi, 400h
0x1800d5e7c  mov     r8d, edi; Size
0x1800d5e7f  xor     edx, edx; Val
0x1800d5e81  lea     rcx, [rbp+1180h+Buffer]; void *
0x1800d5e88  call    memset_0
0x1800d5e8d  mov     r8d, edi; Size
0x1800d5e90  xor     edx, edx; Val
0x1800d5e92  lea     rcx, [rbp+1180h+var_C40]; void *
0x1800d5e99  call    memset_0
0x1800d5e9e  mov     r8d, edi; Size
0x1800d5ea1  xor     edx, edx; Val
0x1800d5ea3  lea     rcx, [rbp+1180h+var_840]; void *
0x1800d5eaa  call    memset_0
0x1800d5eaf  mov     r8d, edi; Size
0x1800d5eb2  xor     edx, edx; Val
0x1800d5eb4  lea     rcx, [rbp+1180h+var_440]; void *
0x1800d5ebb  call    memset_0
0x1800d5ec0  mov     esi, 200h
0x1800d5ec5  mov     r9d, esi; cchBufferMax
0x1800d5ec8  lea     r8, [rbp+1180h+Buffer]; lpBuffer
0x1800d5ecf  mov     edx, 1004h; uID
0x1800d5ed4  mov     rcx, cs:?g_instanceHandle@@3PEAUHINSTANCE__@@EA; hInstance
0x1800d5edb  call    cs:__imp_LoadStringW
0x1800d5ee1  mov     rcx, [rbp+1188h]; this
0x1800d5ee8  xor     edi, edi
0x1800d5eea  test    eax, eax
0x1800d5eec  jnz     short loc_1800D5F00
0x1800d5eee  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wcm\\service\\base\\to"...
0x1800d5ef5  mov     edx, 12Bh; void *
0x1800d5efa  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800d5f00  mov     r9d, esi; cchBufferMax
0x1800d5f03  lea     r8, [rbp+1180h+var_C40]; lpBuffer
0x1800d5f0a  mov     edx, 1005h; uID
0x1800d5f0f  mov     rcx, cs:?g_instanceHandle@@3PEAUHINSTANCE__@@EA; hInstance
0x1800d5f16  call    cs:__imp_LoadStringW
0x1800d5f1c  mov     rcx, [rbp+1188h]; this
0x1800d5f23  test    eax, eax
0x1800d5f25  jnz     short loc_1800D5F39
0x1800d5f27  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wcm\\service\\base\\to"...
0x1800d5f2e  mov     edx, 12Ch; void *
0x1800d5f33  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800d5f39  mov     r9d, esi; cchBufferMax
0x1800d5f3c  lea     r8, [rbp+1180h+var_840]; lpBuffer
0x1800d5f43  mov     edx, 1006h; uID
0x1800d5f48  mov     rcx, cs:?g_instanceHandle@@3PEAUHINSTANCE__@@EA; hInstance
0x1800d5f4f  call    cs:__imp_LoadStringW
0x1800d5f55  mov     rcx, [rbp+1188h]; this
0x1800d5f5c  test    eax, eax
0x1800d5f5e  jnz     short loc_1800D5F72
0x1800d5f60  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wcm\\service\\base\\to"...
0x1800d5f67  mov     edx, 12Dh; void *
0x1800d5f6c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800d5f72  mov     r9d, esi; cchBufferMax
0x1800d5f75  lea     r8, [rbp+1180h+var_440]; lpBuffer
0x1800d5f7c  mov     edx, 1007h; uID
0x1800d5f81  mov     rcx, cs:?g_instanceHandle@@3PEAUHINSTANCE__@@EA; hInstance
0x1800d5f88  call    cs:__imp_LoadStringW
0x1800d5f8e  mov     rcx, [rbp+1188h]; this
0x1800d5f95  test    eax, eax
0x1800d5f97  jnz     short loc_1800D5FAB
0x1800d5f99  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wcm\\service\\base\\to"...
0x1800d5fa0  mov     edx, 12Fh; void *
0x1800d5fa5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800d5fab  lea     rdx, [rbp+1180h+Buffer]
0x1800d5fb2  lea     rcx, [rsp+1280h+var_1220]
0x1800d5fb7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d5fbc  nop
0x1800d5fbd  lea     rdx, [rsp+1280h+var_1220]
0x1800d5fc2  lea     rcx, [rbp+1180h+var_1158]
0x1800d5fc6  call    ?EscapeString@XmlBuilder@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; XmlBuilder::EscapeString(std::wstring const &)
0x1800d5fcb  nop
0x1800d5fcc  lea     rcx, [rsp+1280h+var_1220]; this
0x1800d5fd1  call    ??1ProfileRoutePolicyData@@QEAA@XZ; ProfileRoutePolicyData::~ProfileRoutePolicyData(void)
0x1800d5fd6  lea     rdx, [rbp+1180h+var_C40]
0x1800d5fdd  lea     rcx, [rsp+1280h+var_1250]
0x1800d5fe2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d5fe7  nop
0x1800d5fe8  lea     rdx, [rsp+1280h+var_1250]
0x1800d5fed  lea     rcx, [rbp+1180h+var_11B8]
0x1800d5ff1  call    ?EscapeString@XmlBuilder@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; XmlBuilder::EscapeString(std::wstring const &)
0x1800d5ff6  nop
0x1800d5ff7  lea     rcx, [rsp+1280h+var_1250]; this
0x1800d5ffc  call    ??1ProfileRoutePolicyData@@QEAA@XZ; ProfileRoutePolicyData::~ProfileRoutePolicyData(void)
0x1800d6001  lea     rdx, [rbp+1180h+var_840]
0x1800d6008  lea     rcx, [rsp+1280h+var_1220]
0x1800d600d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d6012  nop
0x1800d6013  lea     rdx, [rsp+1280h+var_1220]
0x1800d6018  lea     rcx, [rbp+1180h+var_1178]
0x1800d601c  call    ?EscapeString@XmlBuilder@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; XmlBuilder::EscapeString(std::wstring const &)
0x1800d6021  nop
0x1800d6022  lea     rcx, [rsp+1280h+var_1220]; this
0x1800d6027  call    ??1ProfileRoutePolicyData@@QEAA@XZ; ProfileRoutePolicyData::~ProfileRoutePolicyData(void)
0x1800d602c  lea     rdx, [rbp+1180h+var_440]
0x1800d6033  lea     rcx, [rsp+1280h+var_1250]
0x1800d6038  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d603d  nop
0x1800d603e  lea     rdx, [rsp+1280h+var_1250]
0x1800d6043  lea     rcx, [rbp+1180h+var_1198]
0x1800d6047  call    ?EscapeString@XmlBuilder@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; XmlBuilder::EscapeString(std::wstring const &)
0x1800d604c  nop
0x1800d604d  lea     rcx, [rsp+1280h+var_1250]; this
0x1800d6052  call    ??1ProfileRoutePolicyData@@QEAA@XZ; ProfileRoutePolicyData::~ProfileRoutePolicyData(void)
0x1800d6057  lea     rcx, [rbp+1180h+var_11C0]
0x1800d605b  call    ??$call_factory_cast@P6A?AUXmlDocument@Dom@Xml@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@56@@ZU123456@U7856@V_lambda_31__@?0???0123456@QEAA@XZ@@impl@winrt@@YA?A_P$$QEAV_lambda_31__@?0???0XmlDocument@Dom@Xml@Data@Windows@1@QEAA@XZ@@Z
0x1800d6060  nop
0x1800d6061  xor     edx, edx; Val
0x1800d6063  mov     r8d, 0E8h; Size
0x1800d6069  lea     rcx, [rbp+1180h+var_1130]; void *
0x1800d606d  call    memset_0
0x1800d6072  lea     rcx, [rbp+1180h+var_1130]
0x1800d6076  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x1800d607b  nop
0x1800d607c  lea     rdx, aToastScenarioR; "<toast scenario=\"Reminder\">"
0x1800d6083  lea     rcx, [rbp+1180h+var_1130]
0x1800d6087  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800d608c  lea     rdx, aVisual; "    <visual>"
0x1800d6093  lea     rcx, [rbp+1180h+var_1130]
0x1800d6097  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800d609c  lea     rdx, aBindingTemplat; "        <binding template=\"ToastGeneri"...
0x1800d60a3  lea     rcx, [rbp+1180h+var_1130]
0x1800d60a7  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800d60ac  lea     rdx, aTextHintStyleB; "            <text hint-style=\"body\">"
0x1800d60b3  lea     rcx, [rbp+1180h+var_1130]
0x1800d60b7  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800d60bc  mov     rcx, rax
0x1800d60bf  lea     rdx, [rbp+1180h+var_1158]
0x1800d60c3  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x1800d60c8  mov     rcx, rax
0x1800d60cb  lea     rdx, aText; "</text>"
0x1800d60d2  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800d60d7  lea     rdx, aText_0; "            <text>"
0x1800d60de  lea     rcx, [rbp+1180h+var_1130]
0x1800d60e2  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800d60e7  lea     rdx, [rbp+1180h+var_11B8]
0x1800d60eb  cmp     [rbp+1180h+var_11A0], 7
0x1800d60f0  cmova   rdx, [rbp+1180h+var_11B8]
0x1800d60f5  mov     rcx, rax
0x1800d60f8  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800d60fd  mov     rcx, rax
0x1800d6100  lea     rdx, aText; "</text>"
0x1800d6107  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800d610c  lea     rdx, aBinding; "        </binding>"
0x1800d6113  lea     rcx, [rbp+1180h+var_1130]
0x1800d6117  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800d611c  lea     rdx, aVisual_0; "    </visual>"
0x1800d6123  lea     rcx, [rbp+1180h+var_1130]
0x1800d6127  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800d612c  lea     rdx, aActions; "    <actions>"
0x1800d6133  lea     rcx, [rbp+1180h+var_1130]
0x1800d6137  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800d613c  lea     rdx, aActionActivati; "        <action activationType=\"Backgr"...
0x1800d6143  lea     rcx, [rbp+1180h+var_1130]
0x1800d6147  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800d614c  mov     rcx, rax
0x1800d614f  lea     rdx, [rbp+1180h+var_1178]
0x1800d6153  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x1800d6158  mov     rcx, rax
0x1800d615b  lea     rdx, asc_18010F418; "\"/>"
0x1800d6162  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800d6167  lea     rdx, aActionActivati_0; "        <action activationType=\"Backgr"...
0x1800d616e  lea     rcx, [rbp+1180h+var_1130]
0x1800d6172  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800d6177  mov     rcx, rax
0x1800d617a  lea     rdx, [rbp+1180h+var_1198]
0x1800d617e  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x1800d6183  mov     rcx, rax
0x1800d6186  lea     rdx, asc_18010F418; "\"/>"
0x1800d618d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800d6192  lea     rdx, aActions_0; "    </actions>"
0x1800d6199  lea     rcx, [rbp+1180h+var_1130]
0x1800d619d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800d61a2  lea     rdx, aToast; "</toast>"
0x1800d61a9  lea     rcx, [rbp+1180h+var_1130]
0x1800d61ad  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800d61b2  nop
0x1800d61b3  xorps   xmm0, xmm0
0x1800d61b6  movups  [rsp+1280h+var_1250], xmm0
0x1800d61bb  xorps   xmm1, xmm1
0x1800d61be  movdqu  [rsp+1280h+var_1240], xmm1
0x1800d61c4  lea     rcx, [rsp+1280h+var_1250]
0x1800d61c9  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1800d61ce  mov     [rsp+1280h+var_1258], 8
0x1800d61d6  lea     rdx, [rsp+1280h+var_1220]
0x1800d61db  lea     rcx, [rbp+1180h+var_1128]
0x1800d61df  call    ?_Get_buffer_view@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AU_Buffer_view@12@XZ; std::basic_stringbuf<ushort>::_Get_buffer_view(void)
0x1800d61e4  mov     rdx, [rsp+1280h+var_1220]
0x1800d61e9  test    rdx, rdx
0x1800d61ec  jz      short loc_1800D61FE
0x1800d61ee  mov     r8, [rsp+1280h+var_1218]
0x1800d61f3  lea     rcx, [rsp+1280h+var_1250]
0x1800d61f8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x1800d61fd  nop
0x1800d61fe  mov     [rsp+1280h+var_1258], 4
0x1800d6206  lea     rdx, [rsp+1280h+var_1250]
0x1800d620b  lea     rcx, [rbp+1180h+var_1200]
0x1800d620f  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x1800d6214  lea     rdx, [rbp+1180h+var_1200]
0x1800d6218  lea     rcx, [rbp+1180h+var_11C0]
0x1800d621c  call    ?LoadXml@?$consume_Windows_Data_Xml_Dom_IXmlDocumentIO@UXmlDocument@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(winrt::param::hstring const &)
0x1800d6221  nop
0x1800d6222  lea     rcx, [rsp+1280h+var_1250]; this
0x1800d6227  call    ??1ProfileRoutePolicyData@@QEAA@XZ; ProfileRoutePolicyData::~ProfileRoutePolicyData(void)
0x1800d622c  lea     rdx, [rbp+1180h+var_11C0]
0x1800d6230  lea     rcx, [rsp+1280h+var_1260]
0x1800d6235  call    ??0_lambda_25__@?0???0ToastNotification@Notifications@UI@Windows@winrt@@QEAA@AEBUXmlDocument@Dom@Xml@Data@45@@Z@QEAA@0@Z; `winrt::Windows::UI::Notifications::ToastNotification::ToastNotification(winrt::Windows::Data::Xml::Dom::XmlDocument const &)'::`1'::_lambda_25__::_lambda_25__(winrt::Windows::Data::Xml::Dom::XmlDocument const &)
0x1800d623a  mov     rdx, rax
0x1800d623d  lea     rcx, [rsp+1280h+var_1228]
0x1800d6242  call    ??$call_factory@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@V_lambda_25__@?0???012345@QEAA@AEBUXmlDocument@Dom@Xml@Data@45@@Z@@impl@winrt@@YA?A_P$$QEAV_lambda_25__@?0???0ToastNotification@Notifications@UI@Windows@1@QEAA@AEBUXmlDocument@Dom@Xml@Data@61@@Z@@Z
0x1800d6247  mov     rcx, [rsp+1280h+var_1228]
0x1800d624c  mov     [r14], rcx
0x1800d624f  test    rcx, rcx
0x1800d6252  jz      short loc_1800D6260
0x1800d6254  mov     rax, [rcx]
0x1800d6257  mov     rax, [rax+8]
0x1800d625b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6260  mov     [r14+8], rdi
0x1800d6264  mov     [r14+10h], rdi
0x1800d6268  mov     [r14+18h], rdi
0x1800d626c  mov     [r14+20h], rdi
0x1800d6270  mov     [r14+28h], rdi
0x1800d6274  mov     [r14+30h], rdi
0x1800d6278  mov     [r14+38h], rdi
0x1800d627c  mov     [r14+40h], rdi
0x1800d6280  mov     [r14+48h], rdi
0x1800d6284  lea     rcx, [rsp+1280h+var_1228]
0x1800d6289  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1800d628e  mov     [rsp+1280h+var_1258], 5
0x1800d6296  mov     rcx, r14
0x1800d6299  call    ?ExpiresOnReboot@?$consume_Windows_UI_Notifications_IToastNotification6@UToastNotification@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@_N@Z; winrt::impl::consume_Windows_UI_Notifications_IToastNotification6<winrt::Windows::UI::Notifications::ToastNotification>::ExpiresOnReboot(bool)
0x1800d629e  xorps   xmm0, xmm0
0x1800d62a1  movups  xmmword ptr [rbp+1180h+var_11E0], xmm0
0x1800d62a5  mov     rdx, rbx
0x1800d62a8  lea     rcx, [rbp+1180h+var_11E0]
0x1800d62ac  call    ??0?$weak_ptr@VActivation@pdc@wcm@@@std@@QEAA@AEBV01@@Z; std::weak_ptr<wcm::pdc::Activation>::weak_ptr<wcm::pdc::Activation>(std::weak_ptr<wcm::pdc::Activation> const &)
0x1800d62b1  nop
0x1800d62b2  lea     rdx, [rbp+1180h+var_11E0]
0x1800d62b6  lea     rcx, [rsp+1280h+var_1220]
0x1800d62bb  call    ??0?$weak_ptr@VActivation@pdc@wcm@@@std@@QEAA@AEBV01@@Z; std::weak_ptr<wcm::pdc::Activation>::weak_ptr<wcm::pdc::Activation>(std::weak_ptr<wcm::pdc::Activation> const &)
0x1800d62c0  mov     [rsp+1280h+var_1210], r13
0x1800d62c5  lea     rdx, [rsp+1280h+var_1220]
0x1800d62ca  lea     rcx, [rsp+1280h+var_1260]
0x1800d62cf  call    winrt__Windows__Foundation__TypedEventHandler_winrt__Windows__UI__Notifications__ToastNotification_winrt__Windows__Foundation__IInspectable___TypedEventHandler_winrt__Windows__UI__Notifications__ToastNotification_winrt__Windows__Foundation__IInspectable___FailoverToast__CreateToast____2____lambda_1___
0x1800d62d4  nop
0x1800d62d5  mov     [rsp+1280h+var_1230], rdi
0x1800d62da  mov     rcx, [r14]
0x1800d62dd  mov     dword ptr [rsp+1280h+var_1250], 0BF9h
0x1800d62e5  lea     rax, aOnecoreuapInte_3; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800d62ec  mov     qword ptr [rsp+1280h+var_1250+8], rax
0x1800d62f1  mov     qword ptr [rsp+1280h+var_1240], rdi
0x1800d62f6  mov     rax, [rcx]
0x1800d62f9  lea     r8, [rsp+1280h+var_1230]
0x1800d62fe  mov     rdi, [rsp+1280h+var_1260]
0x1800d6303  mov     rdx, rdi
0x1800d6306  mov     rax, [rax+58h]
0x1800d630a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d630f  lea     r8, [rsp+1280h+var_1250]
0x1800d6314  mov     edx, eax
0x1800d6316  lea     rcx, [rsp+1280h+var_1228]
0x1800d631b  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800d6320  mov     rbx, [rsp+1280h+var_1230]
0x1800d6325  mov     rdx, r14
0x1800d6328  lea     rcx, [rbp+1180h+var_1200]
0x1800d632c  call    ??$?0AEBUIToastNotification@Notifications@UI@Windows@winrt@@X@?$weak_ref@UIToastNotification@Notifications@UI@Windows@winrt@@@winrt@@QEAA@AEBUIToastNotification@Notifications@UI@Windows@1@@Z; winrt::weak_ref<winrt::Windows::UI::Notifications::IToastNotification>::weak_ref<winrt::Windows::UI::Notifications::IToastNotification>(winrt::Windows::UI::Notifications::IToastNotification const &)
0x1800d6331  mov     [rbp+1180h+var_11F8], rbx
0x1800d6335  mov     [rsp+1280h+var_1258], 65h ; 'e'
0x1800d633d  mov     rax, [rbp+1180h+var_1200]
0x1800d6341  mov     [rbp+1180h+var_1200], 0
  ... truncated ...
```
