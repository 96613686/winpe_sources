# winrt::WindowsUdk::System::Profile::implementation::SystemSettingEntryPointCatalog::GetRevisionInternalAsync$_ResumeCoro$1

- ea: `0x1800c0e60`
- end: `0x1800c1730`
- name: `winrt::WindowsUdk::System::Profile::implementation::SystemSettingEntryPointCatalog::GetRevisionInternalAsync$_ResumeCoro$1`
- size: `2256`
- prototype: ``
- caller_count: `1`
- callee_count: `38`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800932a4`

## callees

- `0x18000b428`
- `0x18000b444`
- `0x18000b510`
- `0x180026860`
- `0x180027af0`
- `0x18004511c`
- `0x18005edb0`
- `0x1800679d8`
- `0x180079148`
- `0x180081708`
- `0x180089db0`
- `0x18008b684`
- `0x18008b740`
- `0x18008dc98`
- `0x1800a5f70`
- `0x1800ad89c`
- `0x1800afccc`
- `0x1800bfb74`
- `0x1800c0e60`
- `0x1800d0bd8`
- `0x1800d5e80`
- `0x1800d8ec8`
- `0x1800d9838`
- `0x1800dca48`
- `0x1800de5ac`
- `0x1800e488c`
- `0x1800eba80`
- `0x1800f88a0`
- `0x1801043ec`
- `0x18010dd48`
- `0x1801205b0`
- `0x18015cfa0`
- `0x18015d85c`
- `0x180287674`
- `0x1802bf744`
- `0x1803b5f70`
- `0x1803ba940`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x1800c0ffa`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x1800c0ffa`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c134a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c134a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800c1309`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800c1309`

## string_xrefs

- `0x1800c131e`: `shellcommon\undockeddevkit\libs\windowsudk.system.profile\systemsettingentrypointcatalog.cpp`
- `0x1800c135a`: `shellcommon\undockeddevkit\libs\windowsudk.system.profile\systemsettingentrypointcatalog.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
void __fastcall winrt::WindowsUdk::System::Profile::implementation::SystemSettingEntryPointCatalog::GetRevisionInternalAsync__ResumeCoro_1(
        __int64 a1)
{
  __int64 v2; // rsi
  __int64 v3; // rcx
  unsigned int v4; // eax
  __int64 v5; // rax
  __int64 v6; // rdx
  LANGID UserDefaultUILanguage; // ax
  __int64 v8; // rdx
  unsigned int v9; // eax
  __int64 v10; // rax
  __int64 v11; // r10
  __int64 v12; // rax
  unsigned int v13; // eax
  __int64 v14; // rax
  __int64 v15; // r10
  __int64 v16; // rax
  unsigned __int64 v17; // r9
  _WORD *v18; // r10
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rax
  char v23; // bl
  HRESULT Guid; // eax
  __int64 v25; // rcx
  unsigned int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rcx
  void **v30; // rdi
  const void *v31; // r14
  size_t v32; // rsi
  char *v33; // rbx
  int i; // edx
  char v35; // r15
  char v36; // r14
  char v37; // si
  char v38; // di
  char v39; // bl
  char v40; // r11
  char v41; // r10
  char v42; // r9
  __int16 v43; // r8
  __int16 v44; // dx
  int v45; // [rsp+20h] [rbp-158h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v2 = a1 + 8;
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_21;
    case 2:
      *(_QWORD *)(a1 + 784) = &qword_1805ED2F8;
      _InterlockedAdd64(&qword_1805ED2F8, 1u);
      v3 = winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Cryptography::Core::HashAlgorithmNames,winrt::Windows::Security::Cryptography::Core::IHashAlgorithmNamesStatics>;
      if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Cryptography::Core::HashAlgorithmNames,winrt::Windows::Security::Cryptography::Core::IHashAlgorithmNamesStatics> )
      {
        *(_QWORD *)(a1 + 800) = 0;
        *(_DWORD *)(a1 + 808) = 0;
        *(_QWORD *)(a1 + 816) = 0;
        *(_QWORD *)(a1 + 824) = 0;
        v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 48LL))(v3, a1 + 800);
        winrt::check_hresult(a1 + 832, v4, a1 + 808);
        *(_QWORD *)(a1 + 48) = *(_QWORD *)(a1 + 800);
        _InterlockedDecrement64(&qword_1805ED2F8);
      }
      else
      {
        _InterlockedDecrement64(&qword_1805ED2F8);
        *(_QWORD *)(a1 + 792) = _lambda_ac9df8f43c44183f35c1c694c32310ab_::_lambda_invoker_cdecl_;
        winrt::impl::factory_cache_entry<winrt::Windows::Security::Cryptography::Core::HashAlgorithmNames,winrt::Windows::Security::Cryptography::Core::IHashAlgorithmNamesStatics>::call<winrt::hstring (*)(winrt::Windows::Security::Cryptography::Core::IHashAlgorithmNamesStatics const &)>(
          0,
          a1 + 48);
      }
      *(_QWORD *)(a1 + 16) = *(_QWORD *)(a1 + 48);
      v5 = winrt::Windows::Security::Cryptography::Core::HashAlgorithmProvider::OpenAlgorithm((const struct winrt::param::hstring *)(a1 + 56));
      winrt::impl::consume_SystemSettings_DataModel_ISettingsExtensibility<winrt::SystemSettings::DataModel::ISettingsExtensibility>::CheckIfInstalledExtensionAppsChangedAsync(
        v5,
        a1 + 64);
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 56));
      winrt::handle_type<winrt::impl::hstring_traits>::close(a1 + 48);
      GetOsVersion(a1 + 72);
      *(_DWORD *)(a1 + 104) = 1;
      winrt::param::hstring::hstring(a1 + 112, a1 + 72);
      v6 = winrt::Windows::Security::Cryptography::CryptographicBuffer::ConvertStringToBinary(
             (const struct winrt::param::hstring *)(a1 + 144),
             (const enum winrt::Windows::Security::Cryptography::BinaryStringEncoding *)(a1 + 112));
      winrt::impl::consume_Windows_Internal_UI_StartScreen_ISecondaryTilePrivate<winrt::Windows::Internal::UI::StartScreen::ISecondaryTilePrivate>::PopulateIdentity(
        a1 + 64,
        v6);
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 144));
      UserDefaultUILanguage = GetUserDefaultUILanguage();
      *(_DWORD *)(a1 + 152) = 1;
      std::_Integral_to_string<wchar_t,int>(a1 + 192, UserDefaultUILanguage);
      winrt::param::hstring::hstring(a1 + 160, a1 + 192);
      v8 = winrt::Windows::Security::Cryptography::CryptographicBuffer::ConvertStringToBinary(
             (const struct winrt::param::hstring *)(a1 + 224),
             (const enum winrt::Windows::Security::Cryptography::BinaryStringEncoding *)(a1 + 160));
      winrt::impl::consume_Windows_Internal_UI_StartScreen_ISecondaryTilePrivate<winrt::Windows::Internal::UI::StartScreen::ISecondaryTilePrivate>::PopulateIdentity(
        a1 + 64,
        v8);
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 224));
      std::filesystem::path::~path((std::filesystem::path *)(a1 + 192));
      *(_DWORD *)(a1 + 232) = 1;
      v9 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Internal::Text::Core::CoreTextKeyFilter>,winrt::Windows::UI::Internal::Text::Core::CoreTextKeyFilter>::Size(*(_QWORD *)(v2 + 1056));
      v10 = std::_UIntegral_to_buff<wchar_t,unsigned int>(a1 + 882, v9);
      std::wstring::wstring(a1 + 272, v10, v11);
      winrt::param::hstring::hstring(a1 + 240, a1 + 272);
      v12 = winrt::Windows::Security::Cryptography::CryptographicBuffer::ConvertStringToBinary(
              (const struct winrt::param::hstring *)(a1 + 304),
              (const enum winrt::Windows::Security::Cryptography::BinaryStringEncoding *)(a1 + 240));
      winrt::impl::consume_Windows_Internal_UI_StartScreen_ISecondaryTilePrivate<winrt::Windows::Internal::UI::StartScreen::ISecondaryTilePrivate>::PopulateIdentity(
        a1 + 64,
        v12);
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 304));
      std::filesystem::path::~path((std::filesystem::path *)(a1 + 272));
      *(_DWORD *)(a1 + 312) = 1;
      v13 = winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(*(_QWORD *)(v2 + 1056));
      v14 = std::_UIntegral_to_buff<wchar_t,unsigned int>(a1 + 930, v13);
      std::wstring::wstring(a1 + 352, v14, v15);
      winrt::param::hstring::hstring(a1 + 320, a1 + 352);
      v16 = winrt::Windows::Security::Cryptography::CryptographicBuffer::ConvertStringToBinary(
              (const struct winrt::param::hstring *)(a1 + 384),
              (const enum winrt::Windows::Security::Cryptography::BinaryStringEncoding *)(a1 + 320));
      winrt::impl::consume_Windows_Internal_UI_StartScreen_ISecondaryTilePrivate<winrt::Windows::Internal::UI::StartScreen::ISecondaryTilePrivate>::PopulateIdentity(
        a1 + 64,
        v16);
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 384));
      std::filesystem::path::~path((std::filesystem::path *)(a1 + 352));
      *(_DWORD *)(a1 + 392) = 1;
      v17 = winrt::impl::consume_SystemSettings_DataModel_ISettingsSearchDatabase<winrt::SystemSettings::DataModel::SettingsSearchContentManager>::DatabaseRevision(*(_QWORD *)(v2 + 1056));
      v18 = (_WORD *)(a1 + 978);
      do
      {
        *--v18 = v17 % 0xA + 48;
        v17 /= 0xAu;
      }
      while ( v17 );
      std::wstring::wstring(a1 + 432, v18, a1 + 978);
      winrt::param::hstring::hstring(a1 + 400, a1 + 432);
      v19 = winrt::Windows::Security::Cryptography::CryptographicBuffer::ConvertStringToBinary(
              (const struct winrt::param::hstring *)(a1 + 464),
              (const enum winrt::Windows::Security::Cryptography::BinaryStringEncoding *)(a1 + 400));
      winrt::impl::consume_Windows_Internal_UI_StartScreen_ISecondaryTilePrivate<winrt::Windows::Internal::UI::StartScreen::ISecondaryTilePrivate>::PopulateIdentity(
        a1 + 64,
        v19);
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 464));
      std::filesystem::path::~path((std::filesystem::path *)(a1 + 432));
      *(_QWORD *)(a1 + 1040) = a1 + 16;
      v20 = winrt::WindowsUdk::System::Profile::implementation::SystemSettingEntryPointCatalog::CheckForChangeInSettingExtensionAppsAsync(
              a1 + 480,
              a1 + 1072);
      v21 = winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::AI::MachineLearning::WisePredictor>,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::AI::MachineLearning::WisePredictor>,void>::await_transform<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::PredictionUnit::Predictor>>(
              a1 - 128,
              v20);
      v22 = winrt::Windows::Foundation::operator co_await<winrt::hstring>(a1 + 488, v21);
      *(_QWORD *)(a1 + 472) = v22;
      *(_WORD *)v2 = 4;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::guid>,winrt::SystemSettings::DataModel::SettingsSearchContentManager const &,winrt::SystemSettings::DataModel::SettingsExtensibility>::promise_type>(
                              v22,
                              a1) )
        return;
      goto LABEL_10;
    case 4:
LABEL_10:
      v23 = winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(*(_QWORD *)(a1 + 472));
      winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,1>>(a1 + 488);
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 480));
      if ( v23 )
      {
        *(_OWORD *)(a1 + 520) = 0;
        Guid = CoCreateGuid((GUID *)(a1 + 520));
        if ( Guid < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x327,
            (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.system.profile\\systemsettingentrypointcatalog.cpp",
            (const char *)(unsigned int)Guid,
            v45);
        if ( !StringFromGUID2((const GUID *const)(a1 + 520), (LPOLESTR)(a1 + 544), 39) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x329,
            (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.system.profile\\systemsettingentrypointcatalog.cpp",
            (const char *)0x8007007ALL,
            v45);
        winrt::param::hstring::hstring((winrt::param::hstring *)(a1 + 624), (const wchar_t *const)(a1 + 544));
        v25 = *(_QWORD *)(a1 + 1072);
        *(_DWORD *)(a1 + 984) = 0;
        *(_QWORD *)(a1 + 992) = 0;
        *(_QWORD *)(a1 + 1000) = 0;
        v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 96LL))(v25);
        winrt::check_hresult(a1 + 1008, v26, a1 + 984);
      }
      winrt::impl::consume_Windows_Internal_UI_StartScreen_IRecentFilesListenerActionInvokedEventArgs<winrt::Windows::Internal::UI::StartScreen::IRecentFilesListenerActionInvokedEventArgs>::ContentUri(
        *(_QWORD *)(a1 + 1040) + 1056LL,
        a1 + 656);
      *(_DWORD *)(a1 + 664) = 1;
      *(_QWORD *)(a1 + 672) = *(_QWORD *)(a1 + 656);
      v27 = winrt::Windows::Security::Cryptography::CryptographicBuffer::ConvertStringToBinary(
              (const struct winrt::param::hstring *)(a1 + 704),
              (const enum winrt::Windows::Security::Cryptography::BinaryStringEncoding *)(a1 + 672));
      winrt::impl::consume_Windows_Internal_UI_StartScreen_ISecondaryTilePrivate<winrt::Windows::Internal::UI::StartScreen::ISecondaryTilePrivate>::PopulateIdentity(
        a1 + 64,
        v27);
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 704));
      *(_QWORD *)(a1 + 712) = 0;
      *(_DWORD *)(a1 + 720) = 0;
      *(_QWORD *)(a1 + 1016) = winrt::impl::consume_Windows_Security_Cryptography_Core_IHashComputation<winrt::Windows::Security::Cryptography::Core::IHashComputation>::GetValueAndReset(
                                 a1 + 64,
                                 a1 + 728);
      *(_QWORD *)(a1 + 1024) = a1 + 712;
      winrt::impl::call_factory<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics,_lambda_b21a58bab620db48c17292046a196a8d_>();
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 728));
      v28 = *(unsigned int *)(a1 + 720);
      v29 = *(_QWORD *)(a1 + 712);
      v30 = (void **)(a1 + 736);
      *(_QWORD *)(a1 + 736) = 0;
      *(_QWORD *)(a1 + 744) = 0;
      *(_QWORD *)(a1 + 752) = 0;
      v31 = *(const void **)(a1 + 712);
      v32 = v29 + v28 - (_QWORD)v31;
      if ( v32 )
      {
        std::vector<unsigned char>::_Buy_nonzero(a1 + 736, v32);
        v33 = (char *)*v30;
        memmove_0(*v30, v31, v32);
        *(_QWORD *)(a1 + 744) = &v33[v32];
        *(_QWORD *)(a1 + 1032) = 0;
        std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>();
      }
      *(_OWORD *)(a1 + 760) = 0;
      *(_DWORD *)(a1 + 760) = (*((unsigned __int8 *)*v30 + 1) << 8)
                            | *(unsigned __int8 *)*v30
                            | (((*((unsigned __int8 *)*v30 + 3) << 8) | *((unsigned __int8 *)*v30 + 2)) << 16);
      *(_WORD *)(a1 + 764) = (*((unsigned __int8 *)*v30 + 5) << 8) | *((unsigned __int8 *)*v30 + 4);
      *(_WORD *)(a1 + 766) = *((_WORD *)*v30 + 3);
      for ( i = 0; i < 8; ++i )
        *(_BYTE *)((unsigned int)i + a1 + 768) = *((_BYTE *)*v30 + (unsigned int)i + 8);
      v35 = *(_BYTE *)(a1 + 768);
      v36 = *(_BYTE *)(a1 + 769);
      v37 = *(_BYTE *)(a1 + 770);
      v38 = *(_BYTE *)(a1 + 771);
      v39 = *(_BYTE *)(a1 + 772);
      v40 = *(_BYTE *)(a1 + 773);
      v41 = *(_BYTE *)(a1 + 774);
      v42 = *(_BYTE *)(a1 + 775);
      v43 = *(_WORD *)(a1 + 764);
      v44 = *(_WORD *)(a1 + 766);
      *(_DWORD *)(a1 - 24) = *(_DWORD *)(a1 + 760);
      *(_WORD *)(a1 - 20) = v43;
      *(_WORD *)(a1 - 18) = v44;
      *(_BYTE *)(a1 - 16) = v35;
      *(_BYTE *)(a1 - 15) = v36;
      *(_BYTE *)(a1 - 14) = v37;
      *(_BYTE *)(a1 - 13) = v38;
      *(_BYTE *)(a1 - 12) = v39;
      *(_BYTE *)(a1 - 11) = v40;
      *(_BYTE *)(a1 - 10) = v41;
      *(_BYTE *)(a1 - 9) = v42;
      std::vector<unsigned char>::_Tidy(a1 + 736);
      winrt::com_array<unsigned char>::clear(a1 + 712);
      winrt::handle_type<winrt::impl::hstring_traits>::close(a1 + 656);
      std::filesystem::path::~path((std::filesystem::path *)(a1 + 72));
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 64));
      *(_QWORD *)(a1 + 776) = a1 - 128;
      *(_WORD *)(a1 + 8) = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::SystemSettings::DataModel::SettingsExtensibility const &>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::final_suspend_awaiter::await_suspend() )
        goto LABEL_21;
      return;
    case 5:
      winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,1>>(a1 + 488);
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 480));
      std::filesystem::path::~path((std::filesystem::path *)(a1 + 72));
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 64));
LABEL_21:
      winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::WindowsUdk::UI::Input::Text::implementation::InputMethodConversionIndicator *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,void>::~promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::WindowsUdk::UI::Input::Text::implementation::InputMethodConversionIndicator *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,void>(a1 - 128);
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 1072));
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 128), (const struct std::nothrow_t *)0x4C0);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x1800c0e60  mov     rax, rsp
0x1800c0e63  mov     [rax+10h], rbx
0x1800c0e67  mov     [rax+18h], rsi
0x1800c0e6b  mov     [rax+8], rcx
0x1800c0e6f  push    rdi
0x1800c0e70  push    r12
0x1800c0e72  push    r13
0x1800c0e74  push    r14
0x1800c0e76  push    r15
0x1800c0e78  sub     rsp, 150h
0x1800c0e7f  mov     r13, rcx
0x1800c0e82  mov     [rsp+178h+var_120], rcx
0x1800c0e87  lea     rsi, [r13+8]
0x1800c0e8b  movzx   eax, word ptr [rsi]
0x1800c0e8e  mov     [rsp+178h+var_140], ax
0x1800c0e93  mov     r15d, 1
0x1800c0e99  add     ax, r15w
0x1800c0e9d  cmp     ax, 6; switch 7 cases
0x1800c0ea1  ja      def_1800C0EC1; jumptable 00000001800C0EC1 default case, case 1
0x1800c0ea7  mov     [rsp+178h+var_118], rsi
0x1800c0eac  movsx   rax, ax
0x1800c0eb0  lea     rdx, __ImageBase
0x1800c0eb7  mov     ecx, ds:(jpt_1800C0EC1 - 180000000h)[rdx+rax*4]
0x1800c0ebe  add     rcx, rdx
0x1800c0ec1  jmp     rcx; switch jump
0x1800c0ec3  xor     r12d, r12d; jumptable 00000001800C0EC1 case 4
0x1800c0ec6  jmp     loc_1800C16C9
0x1800c0ecb  xor     r12d, r12d; jumptable 00000001800C0EC1 case 3
0x1800c0ece  lea     rax, qword_1805ED2F8
0x1800c0ed5  mov     [r13+310h], rax
0x1800c0edc  lock add cs:qword_1805ED2F8, r15
0x1800c0ee4  mov     rcx, cs:??$factory_cache_entry_v@UHashAlgorithmNames@Core@Cryptography@Security@Windows@winrt@@UIHashAlgorithmNamesStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UHashAlgorithmNames@Core@Cryptography@Security@Windows@winrt@@UIHashAlgorithmNamesStatics@23456@@12@A; factory_cache_entry<winrt::Windows::Security::Cryptography::Core::HashAlgorithmNames,winrt::Windows::Security::Cryptography::Core::IHashAlgorithmNamesStatics>::winrt::factory_cache_entry<winrt::Windows::Security::Cryptography::Core::HashAlgorithmNames,winrt::Windows::Security::Cryptography::Core::IHashAlgorithmNamesStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Cryptography::Core::HashAlgorithmNames,winrt::Windows::Security::Cryptography::Core::IHashAlgorithmNamesStatics>
0x1800c0eeb  test    rcx, rcx
0x1800c0eee  jz      short loc_1800C0F48
0x1800c0ef0  lea     rdi, [r13+320h]
0x1800c0ef7  mov     [rdi], r12
0x1800c0efa  lea     rbx, [r13+328h]
0x1800c0f01  mov     [rbx], r12d
0x1800c0f04  mov     [r13+330h], r12
0x1800c0f0b  mov     [r13+338h], r12
0x1800c0f12  mov     rax, [rcx]
0x1800c0f15  mov     rdx, rdi
0x1800c0f18  mov     rax, [rax+30h]
0x1800c0f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0f21  lea     rcx, [r13+340h]
0x1800c0f28  mov     r8, rbx
0x1800c0f2b  mov     edx, eax
0x1800c0f2d  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800c0f32  mov     rax, [rdi]
0x1800c0f35  mov     [rsp+178h+var_100], rax
0x1800c0f3a  mov     [r13+30h], rax
0x1800c0f3e  lock dec cs:qword_1805ED2F8
0x1800c0f46  jmp     short loc_1800C0F6B
0x1800c0f48  lock dec cs:qword_1805ED2F8
0x1800c0f50  lea     r8, [r13+318h]
0x1800c0f57  lea     rax, ?_lambda_invoker_cdecl_@_lambda_ac9df8f43c44183f35c1c694c32310ab_@@CA@AEBUICoreKeyboardInputProfileManagerStatics@Core@Text@Internal@UI@Windows@winrt@@@Z; _lambda_ac9df8f43c44183f35c1c694c32310ab_::_lambda_invoker_cdecl_(winrt::Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManagerStatics const &)
0x1800c0f5e  mov     [r8], rax
0x1800c0f61  lea     rdx, [r13+30h]
0x1800c0f65  call    ??$call@P6A?AUhstring@winrt@@AEBUIHashAlgorithmNamesStatics@Core@Cryptography@Security@Windows@2@@Z@?$factory_cache_entry@UHashAlgorithmNames@Core@Cryptography@Security@Windows@winrt@@UIHashAlgorithmNamesStatics@23456@@impl@winrt@@QEAA?A_P$$QEAP6A?AUhstring@2@AEBUIHashAlgorithmNamesStatics@Core@Cryptography@Security@Windows@2@@Z@Z
0x1800c0f6a  nop
0x1800c0f6b  lea     r15, [r13+10h]
0x1800c0f6f  mov     rax, [r13+30h]
0x1800c0f73  mov     [rsp+178h+var_F8], rax
0x1800c0f7b  mov     [r15], rax
0x1800c0f7e  mov     rdx, r15
0x1800c0f81  lea     rcx, [r13+38h]; struct winrt::param::hstring *
0x1800c0f85  call    ?OpenAlgorithm@HashAlgorithmProvider@Core@Cryptography@Security@Windows@winrt@@SA@AEBUhstring@param@6@@Z; winrt::Windows::Security::Cryptography::Core::HashAlgorithmProvider::OpenAlgorithm(winrt::param::hstring const &)
0x1800c0f8a  nop
0x1800c0f8b  lea     r14, [r13+40h]
0x1800c0f8f  mov     rdx, r14
0x1800c0f92  mov     rcx, rax
0x1800c0f95  call    ?CheckIfInstalledExtensionAppsChangedAsync@?$consume_SystemSettings_DataModel_ISettingsExtensibility@UISettingsExtensibility@DataModel@SystemSettings@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_SystemSettings_DataModel_ISettingsExtensibility<winrt::SystemSettings::DataModel::ISettingsExtensibility>::CheckIfInstalledExtensionAppsChangedAsync(void)
0x1800c0f9a  nop
0x1800c0f9b  lea     rcx, [r13+38h]; this
0x1800c0f9f  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1800c0fa4  nop
0x1800c0fa5  lea     rcx, [r13+30h]
0x1800c0fa9  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800c0fae  lea     rcx, [r13+48h]
0x1800c0fb2  call    ?GetOsVersion@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; GetOsVersion(void)
0x1800c0fb7  nop
0x1800c0fb8  mov     dword ptr [r13+68h], 1
0x1800c0fc0  lea     rdx, [r13+48h]
0x1800c0fc4  lea     rcx, [r13+70h]
0x1800c0fc8  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x1800c0fcd  lea     rcx, [r13+90h]; struct winrt::param::hstring *
0x1800c0fd4  lea     r8, [r13+68h]
0x1800c0fd8  lea     rdx, [r13+70h]; enum winrt::Windows::Security::Cryptography::BinaryStringEncoding *
0x1800c0fdc  call    ?ConvertStringToBinary@CryptographicBuffer@Cryptography@Security@Windows@winrt@@SA@AEBUhstring@param@5@AEBW4BinaryStringEncoding@2345@@Z; winrt::Windows::Security::Cryptography::CryptographicBuffer::ConvertStringToBinary(winrt::param::hstring const &,winrt::Windows::Security::Cryptography::BinaryStringEncoding const &)
0x1800c0fe1  nop
0x1800c0fe2  mov     rdx, rax
0x1800c0fe5  mov     rcx, r14
0x1800c0fe8  call    ?PopulateIdentity@?$consume_Windows_Internal_UI_StartScreen_ISecondaryTilePrivate@UISecondaryTilePrivate@StartScreen@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Internal_UI_StartScreen_ISecondaryTilePrivate<winrt::Windows::Internal::UI::StartScreen::ISecondaryTilePrivate>::PopulateIdentity(winrt::param::hstring const &)
0x1800c0fed  nop
0x1800c0fee  lea     rcx, [r13+90h]; this
0x1800c0ff5  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1800c0ffa  call    cs:__imp_GetUserDefaultUILanguage
0x1800c1000  mov     dword ptr [r13+98h], 1
0x1800c100b  lea     rdi, [r13+0C0h]
0x1800c1012  movzx   edx, ax
0x1800c1015  mov     rcx, rdi
0x1800c1018  call    ??$_Integral_to_string@_WH@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@H@Z; std::_Integral_to_string<wchar_t,int>(int)
0x1800c101d  nop
0x1800c101e  lea     rbx, [r13+0A0h]
0x1800c1025  mov     rdx, rdi
0x1800c1028  mov     rcx, rbx
0x1800c102b  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x1800c1030  lea     rcx, [r13+0E0h]; struct winrt::param::hstring *
0x1800c1037  lea     r8, [r13+98h]
0x1800c103e  mov     rdx, rbx; enum winrt::Windows::Security::Cryptography::BinaryStringEncoding *
0x1800c1041  call    ?ConvertStringToBinary@CryptographicBuffer@Cryptography@Security@Windows@winrt@@SA@AEBUhstring@param@5@AEBW4BinaryStringEncoding@2345@@Z; winrt::Windows::Security::Cryptography::CryptographicBuffer::ConvertStringToBinary(winrt::param::hstring const &,winrt::Windows::Security::Cryptography::BinaryStringEncoding const &)
0x1800c1046  nop
0x1800c1047  mov     rdx, rax
0x1800c104a  mov     rcx, r14
0x1800c104d  call    ?PopulateIdentity@?$consume_Windows_Internal_UI_StartScreen_ISecondaryTilePrivate@UISecondaryTilePrivate@StartScreen@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Internal_UI_StartScreen_ISecondaryTilePrivate<winrt::Windows::Internal::UI::StartScreen::ISecondaryTilePrivate>::PopulateIdentity(winrt::param::hstring const &)
0x1800c1052  nop
0x1800c1053  lea     rcx, [r13+0E0h]; this
0x1800c105a  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1800c105f  nop
0x1800c1060  mov     rcx, rdi; this
0x1800c1063  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800c1068  mov     dword ptr [r13+0E8h], 1
0x1800c1073  mov     rcx, [rsi+420h]
0x1800c107a  call    ?Size@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@UCoreTextKeyFilter@Core@Text@Internal@UI@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UCoreTextKeyFilter@Core@Text@Internal@UI@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Internal::Text::Core::CoreTextKeyFilter>,winrt::Windows::UI::Internal::Text::Core::CoreTextKeyFilter>::Size(void)
0x1800c107f  lea     r10, [r13+372h]
0x1800c1086  mov     edx, eax
0x1800c1088  mov     rcx, r10
0x1800c108b  call    ??$_UIntegral_to_buff@_WI@std@@YAPEA_WPEA_WI@Z; std::_UIntegral_to_buff<wchar_t,uint>(wchar_t *,uint)
0x1800c1090  lea     rdi, [r13+110h]
0x1800c1097  mov     r8, r10
0x1800c109a  mov     rdx, rax
0x1800c109d  mov     rcx, rdi
0x1800c10a0  call    ??$?0PEA_W$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEA_W0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wchar_t *,wchar_t *,std::allocator<wchar_t> const &)
0x1800c10a5  nop
0x1800c10a6  lea     rbx, [r13+0F0h]
0x1800c10ad  mov     rdx, rdi
0x1800c10b0  mov     rcx, rbx
0x1800c10b3  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x1800c10b8  lea     rcx, [r13+130h]; struct winrt::param::hstring *
0x1800c10bf  lea     r8, [r13+0E8h]
0x1800c10c6  mov     rdx, rbx; enum winrt::Windows::Security::Cryptography::BinaryStringEncoding *
0x1800c10c9  call    ?ConvertStringToBinary@CryptographicBuffer@Cryptography@Security@Windows@winrt@@SA@AEBUhstring@param@5@AEBW4BinaryStringEncoding@2345@@Z; winrt::Windows::Security::Cryptography::CryptographicBuffer::ConvertStringToBinary(winrt::param::hstring const &,winrt::Windows::Security::Cryptography::BinaryStringEncoding const &)
0x1800c10ce  nop
0x1800c10cf  mov     rdx, rax
0x1800c10d2  mov     rcx, r14
0x1800c10d5  call    ?PopulateIdentity@?$consume_Windows_Internal_UI_StartScreen_ISecondaryTilePrivate@UISecondaryTilePrivate@StartScreen@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Internal_UI_StartScreen_ISecondaryTilePrivate<winrt::Windows::Internal::UI::StartScreen::ISecondaryTilePrivate>::PopulateIdentity(winrt::param::hstring const &)
0x1800c10da  nop
0x1800c10db  lea     rcx, [r13+130h]; this
0x1800c10e2  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1800c10e7  nop
0x1800c10e8  mov     rcx, rdi; this
0x1800c10eb  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800c10f0  mov     dword ptr [r13+138h], 1
0x1800c10fb  mov     rcx, [rsi+420h]
0x1800c1102  call    ?ValueType@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(void)
0x1800c1107  lea     r10, [r13+3A2h]
0x1800c110e  mov     edx, eax
0x1800c1110  mov     rcx, r10
0x1800c1113  call    ??$_UIntegral_to_buff@_WI@std@@YAPEA_WPEA_WI@Z; std::_UIntegral_to_buff<wchar_t,uint>(wchar_t *,uint)
0x1800c1118  lea     rdi, [r13+160h]
0x1800c111f  mov     r8, r10
0x1800c1122  mov     rdx, rax
0x1800c1125  mov     rcx, rdi
0x1800c1128  call    ??$?0PEA_W$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEA_W0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wchar_t *,wchar_t *,std::allocator<wchar_t> const &)
0x1800c112d  nop
0x1800c112e  lea     rbx, [r13+140h]
0x1800c1135  mov     rdx, rdi
0x1800c1138  mov     rcx, rbx
0x1800c113b  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x1800c1140  lea     rcx, [r13+180h]; struct winrt::param::hstring *
0x1800c1147  lea     r8, [r13+138h]
0x1800c114e  mov     rdx, rbx; enum winrt::Windows::Security::Cryptography::BinaryStringEncoding *
0x1800c1151  call    ?ConvertStringToBinary@CryptographicBuffer@Cryptography@Security@Windows@winrt@@SA@AEBUhstring@param@5@AEBW4BinaryStringEncoding@2345@@Z; winrt::Windows::Security::Cryptography::CryptographicBuffer::ConvertStringToBinary(winrt::param::hstring const &,winrt::Windows::Security::Cryptography::BinaryStringEncoding const &)
0x1800c1156  nop
0x1800c1157  mov     rdx, rax
0x1800c115a  mov     rcx, r14
0x1800c115d  call    ?PopulateIdentity@?$consume_Windows_Internal_UI_StartScreen_ISecondaryTilePrivate@UISecondaryTilePrivate@StartScreen@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Internal_UI_StartScreen_ISecondaryTilePrivate<winrt::Windows::Internal::UI::StartScreen::ISecondaryTilePrivate>::PopulateIdentity(winrt::param::hstring const &)
0x1800c1162  nop
0x1800c1163  lea     rcx, [r13+180h]; this
0x1800c116a  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1800c116f  nop
0x1800c1170  mov     rcx, rdi; this
0x1800c1173  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800c1178  mov     dword ptr [r13+188h], 1
0x1800c1183  mov     rcx, [rsi+420h]
0x1800c118a  call    ?DatabaseRevision@?$consume_SystemSettings_DataModel_ISettingsSearchDatabase@USettingsSearchContentManager@DataModel@SystemSettings@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_SystemSettings_DataModel_ISettingsSearchDatabase<winrt::SystemSettings::DataModel::SettingsSearchContentManager>::DatabaseRevision(void)
0x1800c118f  mov     r9, rax
0x1800c1192  lea     r8, [r13+3D2h]
0x1800c1199  mov     r10, r8
0x1800c119c  sub     r10, 2
0x1800c11a0  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800c11aa  mul     r9
0x1800c11ad  shr     rdx, 3
0x1800c11b1  movzx   eax, dx
0x1800c11b4  shl     ax, 2
0x1800c11b8  lea     ecx, [rax+rdx]
0x1800c11bb  add     cx, cx
0x1800c11be  sub     r9w, cx
0x1800c11c2  add     r9w, 30h ; '0'
0x1800c11c7  mov     [r10], r9w
0x1800c11cb  mov     r9, rdx
0x1800c11ce  test    rdx, rdx
0x1800c11d1  jnz     short loc_1800C119C
0x1800c11d3  lea     rdi, [r13+1B0h]
0x1800c11da  mov     rdx, r10
0x1800c11dd  mov     rcx, rdi
0x1800c11e0  call    ??$?0PEA_W$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEA_W0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wchar_t *,wchar_t *,std::allocator<wchar_t> const &)
0x1800c11e5  nop
0x1800c11e6  lea     rbx, [r13+190h]
0x1800c11ed  mov     rdx, rdi
0x1800c11f0  mov     rcx, rbx
0x1800c11f3  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x1800c11f8  lea     rcx, [r13+1D0h]; struct winrt::param::hstring *
0x1800c11ff  lea     r8, [r13+188h]
0x1800c1206  mov     rdx, rbx; enum winrt::Windows::Security::Cryptography::BinaryStringEncoding *
0x1800c1209  call    ?ConvertStringToBinary@CryptographicBuffer@Cryptography@Security@Windows@winrt@@SA@AEBUhstring@param@5@AEBW4BinaryStringEncoding@2345@@Z; winrt::Windows::Security::Cryptography::CryptographicBuffer::ConvertStringToBinary(winrt::param::hstring const &,winrt::Windows::Security::Cryptography::BinaryStringEncoding const &)
0x1800c120e  nop
0x1800c120f  mov     rdx, rax
0x1800c1212  mov     rcx, r14
0x1800c1215  call    ?PopulateIdentity@?$consume_Windows_Internal_UI_StartScreen_ISecondaryTilePrivate@UISecondaryTilePrivate@StartScreen@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Internal_UI_StartScreen_ISecondaryTilePrivate<winrt::Windows::Internal::UI::StartScreen::ISecondaryTilePrivate>::PopulateIdentity(winrt::param::hstring const &)
0x1800c121a  nop
0x1800c121b  lea     rcx, [r13+1D0h]; this
0x1800c1222  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1800c1227  nop
0x1800c1228  mov     rcx, rdi; this
0x1800c122b  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800c1230  mov     [r13+410h], r15
0x1800c1237  lea     rdx, [r15+420h]
0x1800c123e  lea     rcx, [r13+1E0h]
0x1800c1245  call    ?CheckForChangeInSettingExtensionAppsAsync@SystemSettingEntryPointCatalog@implementation@Profile@System@WindowsUdk@winrt@@CA?AU?$IAsyncOperation@_N@Foundation@Windows@6@AEBUSettingsExtensibility@DataModel@SystemSettings@6@@Z; winrt::WindowsUdk::System::Profile::implementation::SystemSettingEntryPointCatalog::CheckForChangeInSettingExtensionAppsAsync(winrt::SystemSettings::DataModel::SettingsExtensibility const &)
0x1800c124a  nop
0x1800c124b  mov     rdx, rax
0x1800c124e  lea     rcx, [r13-80h]
0x1800c1252  call    ??$await_transform@U?$IAsyncOperation@UPredictor@PredictionUnit@Internal@Windows@winrt@@@Foundation@Windows@winrt@@@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UWisePredictor@MachineLearning@AI@WindowsUdk@winrt@@@Foundation@Windows@winrt@@Uhstring@4@U54@@experimental@std@@U?$IAsyncOperation@UWisePredictor@MachineLearning@AI@WindowsUdk@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEAA$$QEAU?$IAsyncOperation@UPredictor@PredictionUnit@Internal@Windows@winrt@@@Foundation@Windows@2@$$QEAU3452@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::AI::MachineLearning::WisePredictor>,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::AI::MachineLearning::WisePredictor>,void>::await_transform<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::PredictionUnit::Predictor>>(winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::PredictionUnit::Predictor> &&)
0x1800c1257  lea     rcx, [r13+1E8h]
0x1800c125e  mov     rdx, rax
0x1800c1261  call    ??$?__LUhstring@winrt@@@Foundation@Windows@winrt@@YA?AU?$await_adapter@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@$00@impl@2@AEBU?$IAsyncOperation@Uhstring@winrt@@@012@@Z; winrt::Windows::Foundation::operator co_await<winrt::hstring>(winrt::Windows::Foundation::IAsyncOperation<winrt::hstring> const &)
0x1800c1266  mov     [r13+1D8h], rax
0x1800c126d  mov     ecx, 4
0x1800c1272  mov     [rsi], cx
0x1800c1275  mov     rdx, r13
0x1800c1278  mov     rcx, rax
0x1800c127b  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@Uguid@winrt@@@Foundation@Windows@winrt@@AEBUSettingsSearchContentManager@DataModel@SystemSettings@4@USettingsExtensibility@674@@experimental@std@@@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@Uguid@winrt@@@Foundation@Windows@winrt@@AEBUSettingsSearchContentManager@DataModel@SystemSettings@4@USettingsExtensibility@674@@experimental@std@@@experimental@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::guid>,winrt::SystemSettings::DataModel::SettingsSearchContentManager const &,winrt::SystemSettings::DataModel::SettingsExtensibility>::promise_type>(std::experimental::coroutine_handle<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::guid>,winrt::SystemSettings::DataModel::SettingsSearchContentManager const &,winrt::SystemSettings::DataModel::SettingsExtensibility>::promise_type>)
0x1800c1280  test    al, al
0x1800c1282  jz      short loc_1800C12C4
0x1800c1284  jmp     loc_1800C16F6
0x1800c1289  lea     rcx, [r13+1E8h]; jumptable 00000001800C0EC1 case 6
0x1800c1290  call    ??1?$cancellable_awaiter@U?$await_adapter@U?$IAsyncOperation@I@Foundation@Windows@winrt@@$00@impl@winrt@@@winrt@@QEAA@XZ; winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<uint>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<uint>,1>>(void)
0x1800c1295  nop
0x1800c1296  lea     rcx, [r13+1E0h]; this
0x1800c129d  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1800c12a2  nop
0x1800c12a3  lea     rcx, [r13+48h]; this
0x1800c12a7  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800c12ac  nop
0x1800c12ad  lea     rcx, [r13+40h]; this
0x1800c12b1  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1800c12b6  nop
0x1800c12b7  xor     r12d, r12d
0x1800c12ba  jmp     loc_1800C16C9
0x1800c12bf  xor     r12d, r12d; jumptable 00000001800C0EC1 case 5
0x1800c12c2  jmp     short loc_1800C12CA
0x1800c12c4  mov     r15d, 1
0x1800c12ca  mov     rcx, [r13+1D8h]
0x1800c12d1  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(void)
0x1800c12d6  mov     bl, al
0x1800c12d8  lea     rcx, [r13+1E8h]
0x1800c12df  call    ??1?$cancellable_awaiter@U?$await_adapter@U?$IAsyncOperation@I@Foundation@Windows@winrt@@$00@impl@winrt@@@winrt@@QEAA@XZ; winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<uint>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<uint>,1>>(void)
0x1800c12e4  nop
0x1800c12e5  lea     rcx, [r13+1E0h]; this
0x1800c12ec  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1800c12f1  test    bl, bl
0x1800c12f3  jz      loc_1800C13C7
0x1800c12f9  lea     rbx, [r13+208h]
0x1800c1300  xorps   xmm0, xmm0
0x1800c1303  movups  xmmword ptr [rbx], xmm0
0x1800c1306  mov     rcx, rbx; pguid
0x1800c1309  call    cs:__imp_CoCreateGuid
0x1800c130f  mov     rcx, [rsp+178h]; this
0x1800c1317  test    eax, eax
0x1800c1319  jns     short loc_1800C132F
0x1800c131b  mov     r9d, eax; char *
0x1800c131e  lea     r8, aShellcommonUnd_5; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800c1325  mov     edx, 327h; void *
0x1800c132a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c132f  lea     rdi, [r13+220h]
0x1800c1336  mov     rsi, [rsp+178h]
0x1800c133e  mov     r8d, 27h ; '''; cchMax
0x1800c1344  mov     rdx, rdi; lpsz
0x1800c1347  mov     rcx, rbx; rguid
0x1800c134a  call    cs:__imp_StringFromGUID2
0x1800c1350  test    eax, eax
0x1800c1352  jnz     short loc_1800C136E
0x1800c1354  mov     r9d, 8007007Ah; char *
0x1800c135a  lea     r8, aShellcommonUnd_5; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800c1361  mov     edx, 329h; void *
0x1800c1366  mov     rcx, rsi; this
0x1800c1369  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c136e  lea     rbx, [r13+270h]
0x1800c1375  mov     rdx, rdi; wchar_t *
  ... truncated ...
```
