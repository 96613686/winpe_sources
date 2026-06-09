# winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnPropertyChanged(ushort)

- ea: `0x1800c2080`
- end: `0x1800c2e39`
- name: `?OnPropertyChanged@DictationInputProcessor@implementation@Text@Input@UI@WindowsUdk@winrt@@AEAAXG@Z`
- size: `3513`
- prototype: `void __fastcall(winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor *__hidden this, unsigned __int16)`
- caller_count: `0`
- callee_count: `43`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b428`
- `0x180011e64`
- `0x180011f98`
- `0x180013490`
- `0x18001eaf4`
- `0x180023098`
- `0x180027af0`
- `0x18002ddb0`
- `0x18002ecb0`
- `0x180031f90`
- `0x180032da0`
- `0x180033b20`
- `0x1800483f4`
- `0x18004f234`
- `0x18004f258`
- `0x18006a030`
- `0x1800a796c`
- `0x1800b25a0`
- `0x1800c2080`
- `0x1800cbaa8`
- `0x1800cc2cc`
- `0x1800e0aec`
- `0x1800e15ec`
- `0x1800e189c`
- `0x1800e1c44`
- `0x1800f0238`
- `0x180103144`
- `0x180107d28`
- `0x1801365bc`
- `0x1801365dc`
- `0x18015cb00`
- `0x1803d0fb8`
- `0x1803d1550`
- `0x1803d1630`
- `0x1803d1698`
- `0x1803d1914`
- `0x1803d2630`
- `0x1803d7f94`
- `0x1803dcb7c`
- `0x1803dcdb0`
- `0x1803dee50`
- `0x1803e49c0`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c2553`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c2e03`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c2553`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c2e03`
- `CoreMessaging!MsgRelease` at `0x1800c2165`
- `CoreMessaging!MsgRelease` at `0x1800c21aa`
- `CoreMessaging!MsgRelease` at `0x1800c21ef`
- `CoreMessaging!MsgRelease` at `0x1800c2165`
- `CoreMessaging!MsgRelease` at `0x1800c21aa`
- `CoreMessaging!MsgRelease` at `0x1800c21ef`

## string_xrefs

- `0x1800c2108`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text\dictatedtextinputsession.cpp`
- `0x1800c2241`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text\dictatedtextinputsession.cpp`
- `0x1800c227a`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text\dictatedtextinputsession.cpp`
- `0x1800c24b0`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text\dictatedtextinputsession.cpp`
- `0x1800c2543`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text\dictatedtextinputsession.cpp`
- `0x1800c2614`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text\dictatedtextinputsession.cpp`
- `0x1800c26d5`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text\dictatedtextinputsession.cpp`
- `0x1800c2741`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text\dictatedtextinputsession.cpp`
- `0x1800c27d1`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text\dictatedtextinputsession.cpp`
- `0x1800c281c`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text\dictatedtextinputsession.cpp`
- `0x1800c286e`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text\dictatedtextinputsession.cpp`
- `0x1800c28ab`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text\dictatedtextinputsession.cpp`
- `0x1800c292d`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text\dictatedtextinputsession.cpp`
- `0x1800c29cc`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text\dictatedtextinputsession.cpp`
- `0x1800c2a94`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text\dictatedtextinputsession.cpp`
- `0x1800c2b06`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text\dictatedtextinputsession.cpp`
- `0x1800c2baa`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text\dictatedtextinputsession.cpp`
- `0x1800c2c04`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text\dictatedtextinputsession.cpp`
- `0x1800c2c26`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text\dictatedtextinputsession.cpp`
- `0x1800c2cbc`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text\dictatedtextinputsession.cpp`
- `0x1800c2dd1`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text\dictatedtextinputsession.cpp`
- `0x1800c2dbd`: `RemoteDictationInput_PropertyID_NotifyOperationComplete id (%d)`
- `0x1800c2897`: `RemoteDictationInput_PropertyID_CommandReady`
- `0x1800c252f`: `refresh of id %d complete; status = %d`
- `0x1800c249c`: `Start complete`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
void __fastcall winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnPropertyChanged(
        winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor *this,
        __int64 a2)
{
  __int64 v3; // rdi
  void (__fastcall *v4)(__int64, struct MsgString **); // rsi
  __int64 v5; // rdi
  void (__fastcall *v6)(__int64, struct MsgString **); // rsi
  __int64 v7; // rdi
  void (__fastcall *v8)(__int64, struct MsgString **); // rsi
  struct MsgString *v9; // rbx
  const wchar_t *v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rax
  char *v13; // r13
  __int64 v14; // kr00_8
  __int16 v15; // cx
  __int16 v16; // dx
  const wchar_t *v17; // rax
  unsigned int v18; // r8d
  char *v19; // rax
  __int64 v20; // rdx
  const wchar_t *v21; // rax
  unsigned int v22; // r8d
  char *v23; // rax
  __int64 v24; // rdx
  const wchar_t *v25; // rax
  unsigned int v26; // r8d
  char *v27; // rax
  __int64 v28; // rdx
  int v29; // edi
  __int64 v30; // rbx
  __int64 v31; // rdx
  __int64 v32; // rbx
  __int64 v33; // rax
  struct MsgString **v34; // rcx
  __int64 *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  __int64 v38; // rbx
  const wchar_t *v39; // rax
  unsigned int v40; // r8d
  __int64 *v41; // rax
  __int64 v42; // rdx
  __int64 v43; // rax
  __int64 v44; // rbx
  __int64 v45; // rax
  __int64 v46; // rbx
  __int64 v47; // rax
  struct MsgString **v48; // rcx
  __int64 *v49; // rcx
  __int64 v50; // rax
  const wchar_t *v51; // rax
  unsigned int v52; // r8d
  __int64 v53; // rbx
  __int64 *v54; // rcx
  __int64 v55; // rax
  int v56; // eax
  char *v57; // rbx
  const wchar_t *v58; // rax
  unsigned int v59; // r8d
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 *v62; // rcx
  __int64 v63; // rax
  int v64; // eax
  const wchar_t *Data; // rax
  unsigned int v66; // r8d
  __int64 v67; // rax
  int v68; // ecx
  volatile __int32 *v69; // rbx
  __int64 v70; // rax
  char *v71; // rbx
  __int64 v72; // rax
  __int64 v73; // rbx
  int v74[2]; // [rsp+20h] [rbp-79h]
  int v75; // [rsp+20h] [rbp-79h]
  struct MsgString *v76; // [rsp+30h] [rbp-69h] BYREF
  __int64 v77; // [rsp+38h] [rbp-61h] BYREF
  char v78; // [rsp+40h] [rbp-59h]
  _BYTE v79[8]; // [rsp+48h] [rbp-51h] BYREF
  struct MsgString *v80; // [rsp+50h] [rbp-49h] BYREF
  struct MsgString **v81; // [rsp+58h] [rbp-41h] BYREF
  struct MsgString *v82; // [rsp+60h] [rbp-39h] BYREF
  __int64 v83; // [rsp+68h] [rbp-31h] BYREF
  struct MsgString *v84; // [rsp+70h] [rbp-29h] BYREF
  __int64 v85; // [rsp+78h] [rbp-21h] BYREF
  _OWORD v86[2]; // [rsp+80h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  if ( (unsigned __int16)a2 > 0xBu )
  {
    if ( (unsigned __int16)a2 == 12 )
    {
      LODWORD(v80) = 0;
      (*(void (__fastcall **)(_QWORD, struct MsgString **))(**((_QWORD **)this + 5) + 224LL))(
        *((_QWORD *)this + 5),
        &v80);
      ZTraceAsWil(
        "shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text\\dictatedtextinputsession.cpp",
        "winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnPropertyChanged",
        0x4DBu,
        (wchar_t *)L"RemoteDictationInput_PropertyID_NotifyOperationComplete id (%d)",
        (_DWORD)v80);
      v77 = (unsigned int)v80;
      std::_Tree<std::_Tmap_traits<__int64,winrt::handle_type<winrt::handle_traits>,std::less<__int64>,std::allocator<std::pair<__int64 const,winrt::handle_type<winrt::handle_traits>>>,0>>::find(
        (char *)this + 24,
        &v85,
        &v77);
      v73 = v85;
      if ( v85 != *((_QWORD *)this + 3) )
      {
        SetEvent(*(HANDLE *)(v85 + 40));
        std::_Tree<std::_Tmap_traits<__int64,winrt::handle_type<winrt::handle_traits>,std::less<__int64>,std::allocator<std::pair<__int64 const,winrt::handle_type<winrt::handle_traits>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,winrt::handle_type<winrt::handle_traits>>>>>,0>(
          (char *)this + 24,
          &v77,
          v73);
      }
      return;
    }
    if ( (unsigned __int16)a2 != 13 )
    {
      switch ( (unsigned __int16)a2 )
      {
        case 0xFu:
          ZTraceAsWil(
            "shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text\\dictatedtextinputsession.cpp",
            "winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnPropertyChanged",
            0x50Au,
            (wchar_t *)L"RemoteDictationInput_PropertyID_ClientSessionTelemetry");
          v76 = 0;
          v62 = (__int64 *)*((_QWORD *)this + 5);
          v63 = *v62;
          v76 = 0;
          (*(void (__fastcall **)(__int64 *, struct MsgString **))(v63 + 248))(v62, &v76);
          if ( v76 )
            v64 = *(_DWORD *)v76 & 0x1FFFFFFF;
          else
            v64 = 0;
          ZTraceAsWil(
            "shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text\\dictatedtextinputsession.cpp",
            "winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnPropertyChanged",
            0x50Du,
            (wchar_t *)L"session telemetry length %d",
            v64);
          if ( !*((_BYTE *)this + 128) )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x50E,
              (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text\\dictatedtextinputsession.cpp",
              (const char *)0x8000FFFFLL,
              v75);
          Data = MsgStringGetData(v76);
          v67 = winrt::hstring::hstring((winrt::hstring *)&v77, Data, v66);
          Concurrency::task_completion_event<winrt::hstring>::set((char *)this + 112, v67);
          break;
        case 0x10u:
          ZTraceAsWil(
            "shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text\\dictatedtextinputsession.cpp",
            "winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnPropertyChanged",
            0x515u,
            (wchar_t *)L"RemoteDictationInput_PropertyID_ClientCorrectionTelemetry");
          v76 = 0;
          v54 = (__int64 *)*((_QWORD *)this + 5);
          v55 = *v54;
          v76 = 0;
          (*(void (__fastcall **)(__int64 *, struct MsgString **))(v55 + 256))(v54, &v76);
          winrt::weak_ref<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>::get((char *)this + 88, &v82);
          if ( v82 )
          {
            if ( v76 )
              v56 = *(_DWORD *)v76 & 0x1FFFFFFF;
            else
              v56 = 0;
            ZTraceAsWil(
              "shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text\\dictatedtextinputsession.cpp",
              "winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnPropertyChanged",
              0x51Au,
              (wchar_t *)L"firing strlen %d",
              v56);
            v57 = (char *)v82 - 16;
            if ( !v82 )
              v57 = 0;
            v58 = MsgStringGetData(v76);
            v60 = winrt::hstring::hstring((winrt::hstring *)&v85, v58, v59);
            v61 = winrt::impl::create_and_initialize<winrt::WindowsUdk::UI::Input::Text::implementation::AlternatesReportedEventArgs,winrt::hstring>(v60);
            v77 = (v61 + 16) & -(__int64)(v61 != 0);
            winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession,winrt::WindowsUdk::UI::Input::Text::AlternatesReportedEventArgs>>::operator()<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession,winrt::WindowsUdk::UI::Input::Text::AlternatesReportedEventArgs>(
              v57 + 88,
              &v82,
              &v77);
            winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v77);
            winrt::handle_type<winrt::impl::hstring_traits>::close(&v85);
          }
          winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v82);
          break;
        case 0x13u:
          LOBYTE(a2) = 1;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_VTCUXD>::ReportUsage(
            `wil::Feature<__WilFeatureTraits_Feature_VTCUXD>::GetImpl'::`2'::impl,
            a2);
          ZTraceAsWil(
            "shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text\\dictatedtextinputsession.cpp",
            "winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnPropertyChanged",
            0x523u,
            (wchar_t *)L"RemoteDictationInput_PropertyID_ActionCandidateSelected");
          v82 = 0;
          v49 = (__int64 *)*((_QWORD *)this + 5);
          v50 = *v49;
          v82 = 0;
          (*(void (__fastcall **)(__int64 *, struct MsgString **))(v50 + 272))(v49, &v82);
          v51 = MsgStringGetData(v82);
          if ( v82 )
            v52 = *(_DWORD *)v82 & 0x1FFFFFFF;
          else
            v52 = 0;
          winrt::hstring::hstring((winrt::hstring *)&v83, v51, v52);
          LODWORD(v81) = (unsigned __int8)winrt::operator==(&v83, L"SpellThat") ^ 1;
          winrt::weak_ref<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>::get((char *)this + 88, &v77);
          if ( v77 )
          {
            ZTraceAsWil(
              "shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text\\dictatedtextinputsession.cpp",
              "winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnPropertyChanged",
              0x52Fu,
              (wchar_t *)L"firing action candidate selected");
            winrt::WindowsUdk::UI::Input::Text::implementation::SpeechCorrectionCandidateWindowClient::GetCurrentAsync(&v80);
            winrt::impl::wait_get<winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::UI::Input::Text::SpeechCorrectionCandidateWindowClient>>((winrt *)&v85);
            v53 = (v85 - 16) & -(__int64)(v85 != 0);
            winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v85);
            winrt::make<winrt::WindowsUdk::UI::Input::Text::implementation::ActionCandidateSelectedEventArgs,int &,winrt::hstring &>(
              &v84,
              &v81,
              &v83);
            v76 = v84;
            winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ModalDialog>::add_ref(&v76);
            v81 = &v76;
            winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::WindowsUdk::UI::Input::Text::SpeechCorrectionCandidateWindowClient,winrt::WindowsUdk::UI::Input::Text::ActionCandidateSelectedEventArgs>>::operator()<winrt::WindowsUdk::UI::Input::Text::implementation::SpeechCorrectionCandidateWindowClient,winrt::WindowsUdk::UI::Input::Text::ActionCandidateSelectedEventArgs>(
              v53 + 32,
              v53,
              &v76);
            winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v76);
            winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v84);
            winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v80);
          }
          winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v77);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v83);
          v34 = &v82;
          goto LABEL_42;
        default:
          return;
      }
LABEL_41:
      v34 = &v76;
LABEL_42:
      wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(v34);
      return;
    }
    winrt::weak_ref<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>::get((char *)this + 88, &v76);
    if ( !v76 )
    {
LABEL_92:
      v48 = &v76;
LABEL_49:
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)v48);
      return;
    }
    LODWORD(v80) = 0;
    (*(void (__fastcall **)(_QWORD, struct MsgString **))(**((_QWORD **)this + 5) + 232LL))(*((_QWORD *)this + 5), &v80);
    ZTraceAsWil(
      "shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text\\dictatedtextinputsession.cpp",
      "winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnPropertyChanged",
      0x4EBu,
      (wchar_t *)L"RemoteDictationInput_PropertyID_NotifyUserAction (type %d)",
      (_DWORD)v80);
    v68 = (int)v80;
    if ( (unsigned int)((_DWORD)v80 - 5) <= 1 )
    {
      LODWORD(v81) = 0;
      (*(void (__fastcall **)(_QWORD, struct MsgString ***))(**((_QWORD **)this + 5) + 240LL))(
        *((_QWORD *)this + 5),
        &v81);
      v71 = (char *)v76 - 16;
      if ( !v76 )
        v71 = 0;
      LODWORD(v84) = (_DWORD)v81;
      LODWORD(v82) = (_DWORD)v80;
      v72 = winrt::make<winrt::WindowsUdk::UI::Input::Text::implementation::KeypressNotificationEventArgs,enum winrt::WindowsUdk::UI::Input::Text::DictatedSessionEvent,enum winrt::Windows::System::VirtualKey>(
              &v77,
              &v82,
              &v84);
      winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession,winrt::WindowsUdk::UI::Input::Text::KeypressNotificationEventArgs>>::operator()<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession,winrt::WindowsUdk::UI::Input::Text::KeypressNotificationEventArgs>(
        v71 + 64,
        &v76,
        v72);
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v77);
      goto LABEL_92;
    }
    v69 = (volatile __int32 *)((char *)v76 - 16);
    if ( !v76 )
      v69 = 0;
    if ( (_DWORD)v80 == 7 )
    {
      *((_BYTE *)this + 130) = 0;
    }
    else if ( (_DWORD)v80 )
    {
LABEL_88:
      LODWORD(v81) = v68;
      v70 = winrt::make<winrt::WindowsUdk::UI::Input::Text::implementation::DictatedSessionEventArgs,enum winrt::WindowsUdk::UI::Input::Text::DictatedSessionEvent>(
              &v77,
              &v81);
      winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession,winrt::WindowsUdk::UI::Input::Text::DictatedSessionEventArgs>>::operator()<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession,winrt::WindowsUdk::UI::Input::Text::DictatedSessionEventArgs>(
        v69 + 10,
        &v76,
        v70);
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v77);
      goto LABEL_92;
    }
    _InterlockedExchange(v69 + 42, 0);
    v68 = (int)v80;
    goto LABEL_88;
  }
  if ( (unsigned __int16)a2 == 11 )
  {
    ZTraceAsWil(
      "shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text\\dictatedtextinputsession.cpp",
      "winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnPropertyChanged",
      0x4D0u,
      (wchar_t *)L"RemoteDictationInput_PropertyID_CommandReady");
    memset(v86, 0, 28);
    (*(void (__fastcall **)(_QWORD, _OWORD *))(**((_QWORD **)this + 5) + 216LL))(*((_QWORD *)this + 5), v86);
  }
  else if ( (_WORD)a2 )
  {
    if ( (unsigned __int16)a2 != 1 )
    {
      switch ( (unsigned __int16)a2 )
      {
        case 2u:
          ZTraceAsWil(
            "shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text\\dictatedtextinputsession.cpp",
            "winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnPropertyChanged",
            0x45Du,
            (wchar_t *)L"RemoteDictationInput_PropertyID_DictationSessionFailed");
          LODWORD(v81) = 0;
          (*(void (__fastcall **)(_QWORD, struct MsgString ***))(**((_QWORD **)this + 5) + 144LL))(
            *((_QWORD *)this + 5),
            &v81);
          winrt::weak_ref<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>::get((char *)this + 88, &v83);
          v46 = v83;
          if ( v83 )
          {
            LODWORD(v80) = 12;
            v47 = winrt::make<winrt::WindowsUdk::UI::Input::Text::implementation::DictatedSessionEventArgs,enum winrt::WindowsUdk::UI::Input::Text::DictatedSessionEvent>(
                    &v77,
                    &v80);
            winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession,winrt::WindowsUdk::UI::Input::Text::DictatedSessionEventArgs>>::operator()<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession,winrt::WindowsUdk::UI::Input::Text::DictatedSessionEventArgs>(
              v46 + 24,
              &v83,
              v47);
            winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v77);
          }
          break;
        case 3u:
          ZTraceAsWil(
            "shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text\\dictatedtextinputsession.cpp",
            "winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnPropertyChanged",
            0x469u,
            (wchar_t *)L"RemoteDictationInput_PropertyID_UserInteractionAfterSessionEnd");
          winrt::weak_ref<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>::get((char *)this + 88, &v83);
          v44 = v83;
          if ( v83 )
          {
            LODWORD(v81) = 13;
            v45 = winrt::make<winrt::WindowsUdk::UI::Input::Text::implementation::DictatedSessionEventArgs,enum winrt::WindowsUdk::UI::Input::Text::DictatedSessionEvent>(
                    &v77,
                    &v81);
            winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession,winrt::WindowsUdk::UI::Input::Text::DictatedSessionEventArgs>>::operator()<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession,winrt::WindowsUdk::UI::Input::Text::DictatedSessionEventArgs>(
              v44 + 24,
              &v83,
              v45);
            winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v77);
          }
          break;
        case 6u:
          v76 = 0;
          v35 = (__int64 *)*((_QWORD *)this + 5);
          v36 = *v35;
          v76 = 0;
          (*(void (__fastcall **)(__int64 *, struct MsgString **))(v36 + 176))(v35, &v76);
          if ( v76 )
            v37 = *(_DWORD *)v76 & 0x1FFFFFFF;
          else
            v37 = 0;
          ZTraceAsWil(
            "shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text\\dictatedtextinputsession.cpp",
            "winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnPropertyChanged",
            0x475u,
            (wchar_t *)L"RemoteDictationInput_PropertyID_View, len %d",
            v37);
          winrt::weak_ref<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>::get((char *)this + 88, &v83);
          v38 = v83;
          if ( v83 )
          {
            v39 = MsgStringGetData(v76);
            v41 = (__int64 *)winrt::hstring::hstring((winrt::hstring *)&v77, v39, v40);
            if ( (__int64 *)(v38 + 120) != v41 )
            {
              v42 = *v41;
              *v41 = 0;
              winrt::handle_type<winrt::impl::hstring_traits>::attach(v38 + 120, v42);
            }
            winrt::handle_type<winrt::impl::hstring_traits>::close(&v77);
            LODWORD(v81) = 11;
            v43 = winrt::make<winrt::WindowsUdk::UI::Input::Text::implementation::DictatedSessionEventArgs,enum winrt::WindowsUdk::UI::Input::Text::DictatedSessionEvent>(
                    &v77,
                    &v81);
            winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession,winrt::WindowsUdk::UI::Input::Text::DictatedSessionEventArgs>>::operator()<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession,winrt::WindowsUdk::UI::Input::Text::DictatedSessionEventArgs>(
              v38 + 24,
              &v83,
              v43);
            winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v77);
          }
          winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v83);
          goto LABEL_41;
        case 7u:
          ZTraceAsWil(
            "shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text\\dictatedtextinputsession.cpp",
            "winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnPropertyChanged",
            0x483u,
            (wchar_t *)L"RemoteDictationInput_PropertyID_DictationSessionStarted");
          memset(v86, 0, 28);
          v80 = 0;
          v76 = 0;
          v84 = 0;
          (*(void (__fastcall **)(_QWORD, _OWORD *))(**((_QWORD **)this + 5) + 184LL))(*((_QWORD *)this + 5), v86);
          v3 = *((_QWORD *)this + 5);
          v4 = *(void (__fastcall **)(__int64, struct MsgString **))(*(_QWORD *)v3 + 192LL);
          v80 = 0;
          v4(v3, &v80);
          v5 = *((_QWORD *)this + 5);
          v6 = *(void (__fastcall **)(__int64, struct MsgString **))(*(_QWORD *)v5 + 200LL);
          v76 = 0;
          v6(v5, &v76);
          v7 = *((_QWORD *)this + 5);
          v8 = *(void (__fastcall **)(__int64, struct MsgString **))(*(_QWORD *)v7 + 208LL);
          v9 = v84;
          if ( v84 )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v77);
            MsgRelease(v9);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v77);
          }
          v84 = 0;
          v8(v7, &v84);
          winrt::weak_ref<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>::get((char *)this + 88, &v82);
          v10 = MsgStringGetData(v84);
          ZTraceAsWil(
            "shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text\\dictatedtextinputsession.cpp",
            "winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnPropertyChanged",
            0x48Fu,
            (wchar_t *)L"Follow Txt = %s",
            v10);
          v77 = 0;
          if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v82, &v77) )
          {
            ZTraceAsWil(
              "shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text\\dictatedtextinputsession.cpp",
              "winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnPropertyChanged",
              0x492u,
              (wchar_t *)L"Creating session");
            winrt::make_self<winrt::WindowsUdk::UI::Input::Text::implementation::DictatedTextInputSession,>(&v85);
            v11 = v85;
            winrt::impl::as<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession,winrt::WindowsUdk::UI::Input::Text::implementation::DictatedTextInputSession,0>(
              &v83,
              v85);
            v12 = winrt::make_weak<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>(&v81, &v83);
            winrt::Windows::Foundation::IUnknown::operator=((char *)this + 88, v12);
            if ( v81 )
              winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v81);
            winrt::impl::root_implements<winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor,winrt::Windows::Foundation::IClosable,winrt::non_agile>::get_weak<winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor>(
              this,
              &v81);
            winrt::Windows::Foundation::IUnknown::operator=(v11 + 176, &v81);
            if ( v81 )
              winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v81);
            winrt::Windows::Foundation::IUnknown::operator=(&v82, &v83);
            winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v83);
            if ( v11 )
              winrt::com_ptr<winrt::WindowsUdk::UI::Input::Text::implementation::SpeechCorrectionCandidateWindowClient>::unconditional_release_ref(&v85);
          }
          v13 = (char *)v82 - 16;
          if ( !v82 )
            v13 = 0;
          v14 = *((_QWORD *)&v86[0] + 1);
          v15 = WORD2(v86[0]);
          v16 = WORD3(v86[0]);
          *((_DWORD *)v13 + 37) = v86[0];
          *((_WORD *)v13 + 76) = v15;
          *((_WORD *)v13 + 77) = v16;
          *(_QWORD *)(v13 + 156) = v14;
          v17 = MsgStringGetData(v80);
          v19 = (char *)winrt::hstring::hstring((winrt::hstring *)&v77, v17, v18);
          if ( v13 + 112 != v19 )
          {
            v20 = *(_QWORD *)v19;
            *(_QWORD *)v19 = 0;
            winrt::handle_type<winrt::impl::hstring_traits>::attach(v13 + 112, v20);
          }
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v77);
          v21 = MsgStringGetData(v76);
          v23 = (char *)winrt::hstring::hstring((winrt::hstring *)&v77, v21, v22);
          if ( v13 + 120 != v23 )
          {
            v24 = *(_QWORD *)v23;
            *(_QWORD *)v23 = 0;
            winrt::handle_type<winrt::impl::hstring_traits>::attach(v13 + 120, v24);
          }
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v77);
          v25 = MsgStringGetData(v84);
          v27 = (char *)winrt::hstring::hstring((winrt::hstring *)&v77, v25, v26);
          if ( v13 + 128 != v27 )
          {
            v28 = *(_QWORD *)v27;
            *(_QWORD *)v27 = 0;
            winrt::handle_type<winrt::impl::hstring_traits>::attach(v13 + 128, v28);
          }
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v77);
          *((_DWORD *)v13 + 36) = DWORD1(v86[1]);
          _InterlockedExchange((volatile __int32 *)v13 + 41, v86[1]);
          _InterlockedExchange((volatile __int32 *)v13 + 42, 1);
          v29 = *((_DWORD *)this + 35);
          if ( v29 )
          {
            v77 = *((int *)this + 35);
            std::_Tree<std::_Tmap_traits<__int64,winrt::handle_type<winrt::handle_traits>,std::less<__int64>,std::allocator<std::pair<__int64 const,winrt::handle_type<winrt::handle_traits>>>,0>>::find(
              (char *)this + 24,
              &v85,
              &v77);
            v32 = v85;
            if ( v85 != *((_QWORD *)this + 3) )
            {
              v74[0] = v29;
              ZTraceAsWil(
                "shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text\\dictatedtextinputsession.cpp",
                "winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnPropertyChanged",
                0x4B2u,
                (wchar_t *)L"refresh of id %d complete; status = %d",
                *(_QWORD *)v74,
                *((_DWORD *)v13 + 42));
              SetEvent(*(HANDLE *)(v32 + 40));
              std::_Tree<std::_Tmap_traits<__int64,winrt::handle_type<winrt::handle_traits>,std::less<__int64>,std::allocator<std::pair<__int64 const,winrt::handle_type<winrt::handle_traits>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,winrt::handle_type<winrt::handle_traits>>>>>,0>(
                (char *)this + 24,
                &v77,
                v32);
              *((_DWORD *)this + 35) = 0;
            }
          }
          else
          {
            ZTraceAsWil(
              "shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text\\dictatedtextinputsession.cpp",
              "winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnPropertyChanged",
              0x4A6u,
              (wchar_t *)L"Start complete");
            v30 = *((_QWORD *)this + 13);
            if ( v30 )
            {
              v77 = (__int64)v82;
              winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ModalDialog>::add_ref(&v77);
              v78 = 1;
              Concurrency::task_completion_event<std::optional<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>>::set(
                v30,
                &v77);
              v31 = *((_QWORD *)this + 13);
              *((_QWORD *)this + 13) = 0;
              if ( v31 )
                std::default_delete<Concurrency::task_completion_event<std::optional<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>>>::operator()();
            }
          }
          LODWORD(v81) = 11;
          v33 = winrt::make<winrt::WindowsUdk::UI::Input::Text::implementation::DictatedSessionEventArgs,enum winrt::WindowsUdk::UI::Input::Text::DictatedSessionEvent>(
                  &v77,
                  &v81);
          winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession,winrt::WindowsUdk::UI::Input::Text::DictatedSessionEventArgs>>::operator()<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession,winrt::WindowsUdk::UI::Input::Text::DictatedSessionEventArgs>(
            v13 + 40,
            &v82,
            v33);
          winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v77);
          winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v82);
          wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(&v84);
          wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(&v76);
          v34 = &v80;
          goto LABEL_42;
        default:
          return;
      }
      v48 = (struct MsgString **)&v83;
      goto LABEL_49;
    }
    ZTraceAsWil(
      "shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text\\dictatedtextinputsession.cpp",
      "winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnPropertyChanged",
      0x453u,
      (wchar_t *)L"RemoteDictationInput_PropertyID_DictationSessionStartFailed");
    LODWORD(v80) = 0;
    (*(void (__fastcall **)(_QWORD, struct MsgString **))(**((_QWORD **)this + 5) + 136LL))(*((_QWORD *)this + 5), &v80);
    winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnDictationSessionStartFailed(
      this,
      (unsigned int)v80);
  }
  else
  {
    ZTraceAsWil(
      "shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text\\dictatedtextinputsession.cpp",
      "winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnPropertyChanged",
      0x445u,
      (wchar_t *)L"RemoteDictationInput_PropertyID_DictationAvailableChanged");
    *((_BYTE *)this + 130) = 1;
    v79[0] = 0;
    if ( (*(int (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 10) + 24LL))(*((_QWORD *)this + 10), v79) >= 0
      && v79[0] )
    {
      ZTraceAsWil(
        "shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text\\dictatedtextinputsession.cpp",
        "winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnPropertyChanged",
        0x44Au,
        (wchar_t *)L"Activated while waiting for timer");
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 96LL))(*((_QWORD *)this + 10));
      winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnRefreshProxy(this);
    }
  }
}

```

## disassembly

```asm
0x1800c2080  push    rbp
0x1800c2082  push    rbx
0x1800c2083  push    rsi
0x1800c2084  push    rdi
0x1800c2085  push    r12
0x1800c2087  push    r13
0x1800c2089  push    r14
0x1800c208b  push    r15
0x1800c208d  lea     rbp, [rsp-1Fh]
0x1800c2092  sub     rsp, 0B8h
0x1800c2099  mov     rax, cs:__security_cookie
0x1800c20a0  xor     rax, rsp
0x1800c20a3  mov     [rbp+57h+var_50], rax
0x1800c20a7  mov     r15, rcx
0x1800c20aa  xor     r12d, r12d
0x1800c20ad  movzx   ecx, dx
0x1800c20b0  cmp     ecx, 0Bh
0x1800c20b3  ja      loc_1800C28DE
0x1800c20b9  jz      loc_1800C2897
0x1800c20bf  test    ecx, ecx
0x1800c20c1  jz      loc_1800C2808
0x1800c20c7  sub     ecx, 1
0x1800c20ca  jz      loc_1800C27BD
0x1800c20d0  sub     ecx, 1
0x1800c20d3  jz      loc_1800C272D
0x1800c20d9  sub     ecx, 1
0x1800c20dc  jz      loc_1800C26C1
0x1800c20e2  sub     ecx, 3
0x1800c20e5  jz      loc_1800C25C6
0x1800c20eb  cmp     ecx, 1
0x1800c20ee  jnz     loc_1800C2E19
0x1800c20f4  lea     r9, aRemotedictatio_9; "RemoteDictationInput_PropertyID_Dictati"...
0x1800c20fb  mov     r8d, 483h; unsigned int
0x1800c2101  lea     rdx, aWinrtWindowsud_16; "winrt::WindowsUdk::UI::Input::Text::imp"...
0x1800c2108  lea     rcx, aShellcommonUnd_153; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800c210f  call    ?ZTraceAsWil@@YAXPEBD0IPEA_WZZ; ZTraceAsWil(char const *,char const *,uint,wchar_t *,...)
0x1800c2114  xorps   xmm0, xmm0
0x1800c2117  movups  [rbp+57h+var_70], xmm0
0x1800c211b  movups  [rbp+57h+var_70+0Ch], xmm0
0x1800c211f  mov     [rbp+57h+var_A0], r12
0x1800c2123  mov     [rbp+57h+var_C0], r12
0x1800c2127  mov     [rbp+57h+var_80], r12
0x1800c212b  mov     rcx, [r15+28h]
0x1800c212f  mov     rax, [rcx]
0x1800c2132  lea     rdx, [rbp+57h+var_70]
0x1800c2136  mov     rax, [rax+0B8h]
0x1800c213d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2142  mov     rdi, [r15+28h]
0x1800c2146  mov     rax, [rdi]
0x1800c2149  mov     rsi, [rax+0C0h]
0x1800c2150  mov     rbx, [rbp+57h+var_A0]
0x1800c2154  test    rbx, rbx
0x1800c2157  jz      short loc_1800C2174
0x1800c2159  lea     rcx, [rbp+57h+var_B8]; this
0x1800c215d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800c2162  mov     rcx, rbx
0x1800c2165  call    cs:__imp_MsgRelease
0x1800c216b  lea     rcx, [rbp+57h+var_B8]; this
0x1800c216f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800c2174  mov     [rbp+57h+var_A0], r12
0x1800c2178  lea     rdx, [rbp+57h+var_A0]
0x1800c217c  mov     rcx, rdi
0x1800c217f  mov     rax, rsi
0x1800c2182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2187  mov     rdi, [r15+28h]
0x1800c218b  mov     rax, [rdi]
0x1800c218e  mov     rsi, [rax+0C8h]
0x1800c2195  mov     rbx, [rbp+57h+var_C0]
0x1800c2199  test    rbx, rbx
0x1800c219c  jz      short loc_1800C21B9
0x1800c219e  lea     rcx, [rbp+57h+var_B8]; this
0x1800c21a2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800c21a7  mov     rcx, rbx
0x1800c21aa  call    cs:__imp_MsgRelease
0x1800c21b0  lea     rcx, [rbp+57h+var_B8]; this
0x1800c21b4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800c21b9  mov     [rbp+57h+var_C0], r12
0x1800c21bd  lea     rdx, [rbp+57h+var_C0]
0x1800c21c1  mov     rcx, rdi
0x1800c21c4  mov     rax, rsi
0x1800c21c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c21cc  mov     rdi, [r15+28h]
0x1800c21d0  mov     rax, [rdi]
0x1800c21d3  mov     rsi, [rax+0D0h]
0x1800c21da  mov     rbx, [rbp+57h+var_80]
0x1800c21de  test    rbx, rbx
0x1800c21e1  jz      short loc_1800C21FE
0x1800c21e3  lea     rcx, [rbp+57h+var_B8]; this
0x1800c21e7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800c21ec  mov     rcx, rbx
0x1800c21ef  call    cs:__imp_MsgRelease
0x1800c21f5  lea     rcx, [rbp+57h+var_B8]; this
0x1800c21f9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800c21fe  mov     [rbp+57h+var_80], r12
0x1800c2202  lea     rdx, [rbp+57h+var_80]
0x1800c2206  mov     rcx, rdi
0x1800c2209  mov     rax, rsi
0x1800c220c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2211  lea     rdx, [rbp+57h+var_90]
0x1800c2215  lea     rcx, [r15+58h]
0x1800c2219  call    ?get@?$weak_ref@UDictatedTextInputSession@Text@Input@UI@WindowsUdk@winrt@@@winrt@@QEBA@XZ; winrt::weak_ref<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>::get(void)
0x1800c221e  nop
0x1800c221f  mov     rcx, [rbp+57h+var_80]; struct MsgString *
0x1800c2223  call    ?MsgStringGetData@@YAPEB_WPEAUMsgString@@@Z; MsgStringGetData(MsgString *)
0x1800c2228  mov     qword ptr [rsp+0F0h+var_D0], rax
0x1800c222d  lea     r9, aFollowTxtS; "Follow Txt = %s"
0x1800c2234  mov     r8d, 48Fh; unsigned int
0x1800c223a  lea     rdx, aWinrtWindowsud_16; "winrt::WindowsUdk::UI::Input::Text::imp"...
0x1800c2241  lea     rcx, aShellcommonUnd_153; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800c2248  call    ?ZTraceAsWil@@YAXPEBD0IPEA_WZZ; ZTraceAsWil(char const *,char const *,uint,wchar_t *,...)
0x1800c224d  mov     [rbp+57h+var_B8], r12
0x1800c2251  lea     rdx, [rbp+57h+var_B8]
0x1800c2255  lea     rcx, [rbp+57h+var_90]
0x1800c2259  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x1800c225e  test    al, al
0x1800c2260  jz      loc_1800C231A
0x1800c2266  lea     r9, aCreatingSessio; "Creating session"
0x1800c226d  mov     r8d, 492h; unsigned int
0x1800c2273  lea     rdx, aWinrtWindowsud_16; "winrt::WindowsUdk::UI::Input::Text::imp"...
0x1800c227a  lea     rcx, aShellcommonUnd_153; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800c2281  call    ?ZTraceAsWil@@YAXPEBD0IPEA_WZZ; ZTraceAsWil(char const *,char const *,uint,wchar_t *,...)
0x1800c2286  lea     rcx, [rbp+57h+var_78]
0x1800c228a  call    ??$make_self@UDictatedTextInputSession@implementation@Text@Input@UI@WindowsUdk@winrt@@$$V@winrt@@YA?AU?$com_ptr@UDictatedTextInputSession@implementation@Text@Input@UI@WindowsUdk@winrt@@@0@XZ; winrt::make_self<winrt::WindowsUdk::UI::Input::Text::implementation::DictatedTextInputSession,>(void)
0x1800c228f  nop
0x1800c2290  mov     rbx, [rbp+57h+var_78]
0x1800c2294  mov     rdx, rbx
0x1800c2297  lea     rcx, [rbp+57h+var_88]
0x1800c229b  call    ??$as@UDictatedTextInputSession@Text@Input@UI@WindowsUdk@winrt@@U1implementation@23456@$0A@@impl@winrt@@YA?AUDictatedTextInputSession@Text@Input@UI@WindowsUdk@1@PEAU2implementation@34561@@Z; winrt::impl::as<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession,winrt::WindowsUdk::UI::Input::Text::implementation::DictatedTextInputSession,0>(winrt::WindowsUdk::UI::Input::Text::implementation::DictatedTextInputSession *)
0x1800c22a0  nop
0x1800c22a1  lea     rdx, [rbp+57h+var_88]
0x1800c22a5  lea     rcx, [rbp+57h+var_98]
0x1800c22a9  call    ??$make_weak@UDictatedTextInputSession@Text@Input@UI@WindowsUdk@winrt@@@winrt@@YA?AU?$weak_ref@UDictatedTextInputSession@Text@Input@UI@WindowsUdk@winrt@@@0@AEBUDictatedTextInputSession@Text@Input@UI@WindowsUdk@0@@Z; winrt::make_weak<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>(winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession const &)
0x1800c22ae  mov     rdx, rax
0x1800c22b1  lea     rcx, [r15+58h]
0x1800c22b5  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1800c22ba  cmp     [rbp+57h+var_98], r12
0x1800c22be  jz      short loc_1800C22C9
0x1800c22c0  lea     rcx, [rbp+57h+var_98]
0x1800c22c4  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800c22c9  lea     rdx, [rbp+57h+var_98]
0x1800c22cd  mov     rcx, r15
0x1800c22d0  call    ??$get_weak@UDictationInputProcessor@implementation@Text@Input@UI@WindowsUdk@winrt@@@?$root_implements@UDictationInputProcessor@implementation@Text@Input@UI@WindowsUdk@winrt@@UIClosable@Foundation@Windows@7@Unon_agile@7@@impl@winrt@@IEAA?AU?$weak_ref@UDictationInputProcessor@implementation@Text@Input@UI@WindowsUdk@winrt@@@2@XZ; winrt::impl::root_implements<winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor,winrt::Windows::Foundation::IClosable,winrt::non_agile>::get_weak<winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor>(void)
0x1800c22d5  lea     rcx, [rbx+0B0h]
0x1800c22dc  lea     rdx, [rbp+57h+var_98]
0x1800c22e0  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1800c22e5  cmp     [rbp+57h+var_98], r12
0x1800c22e9  jz      short loc_1800C22F4
0x1800c22eb  lea     rcx, [rbp+57h+var_98]
0x1800c22ef  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800c22f4  lea     rdx, [rbp+57h+var_88]
0x1800c22f8  lea     rcx, [rbp+57h+var_90]
0x1800c22fc  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@AEBU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown const &)
0x1800c2301  nop
0x1800c2302  lea     rcx, [rbp+57h+var_88]; this
0x1800c2306  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1800c230b  nop
0x1800c230c  test    rbx, rbx
0x1800c230f  jz      short loc_1800C231A
0x1800c2311  lea     rcx, [rbp+57h+var_78]
0x1800c2315  call    ?unconditional_release_ref@?$com_ptr@USpeechCorrectionCandidateWindowClient@implementation@Text@Input@UI@WindowsUdk@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::WindowsUdk::UI::Input::Text::implementation::SpeechCorrectionCandidateWindowClient>::unconditional_release_ref(void)
0x1800c231a  mov     rax, [rbp+57h+var_90]
0x1800c231e  test    rax, rax
0x1800c2321  lea     r13, [rax-10h]
0x1800c2325  jnz     short loc_1800C232A
0x1800c2327  mov     r13, r12
0x1800c232a  mov     r8b, byte ptr [rbp+57h+var_70+8]
0x1800c232e  mov     r9b, byte ptr [rbp+57h+var_70+9]
0x1800c2332  mov     r10b, byte ptr [rbp+57h+var_70+0Ah]
0x1800c2336  mov     r11b, byte ptr [rbp+57h+var_70+0Bh]
0x1800c233a  mov     bl, byte ptr [rbp+57h+var_70+0Ch]
0x1800c233d  mov     dil, byte ptr [rbp+57h+var_70+0Dh]
0x1800c2341  mov     sil, byte ptr [rbp+57h+var_70+0Eh]
0x1800c2345  mov     r14b, byte ptr [rbp+57h+var_70+0Fh]
0x1800c2349  movzx   ecx, word ptr [rbp+57h+var_70+4]
0x1800c234d  movzx   edx, word ptr [rbp+57h+var_70+6]
0x1800c2351  mov     eax, dword ptr [rbp+57h+var_70]
0x1800c2354  mov     [r13+94h], eax
0x1800c235b  mov     [r13+98h], cx
0x1800c2363  mov     [r13+9Ah], dx
0x1800c236b  mov     [r13+9Ch], r8b
0x1800c2372  mov     [r13+9Dh], r9b
0x1800c2379  mov     [r13+9Eh], r10b
0x1800c2380  mov     [r13+9Fh], r11b
0x1800c2387  mov     [r13+0A0h], bl
0x1800c238e  mov     [r13+0A1h], dil
0x1800c2395  mov     [r13+0A2h], sil
0x1800c239c  mov     [r13+0A3h], r14b
0x1800c23a3  mov     edi, 1FFFFFFFh
0x1800c23a8  mov     rcx, [rbp+57h+var_A0]; struct MsgString *
0x1800c23ac  test    rcx, rcx
0x1800c23af  jnz     short loc_1800C23B6
0x1800c23b1  mov     r8d, r12d
0x1800c23b4  jmp     short loc_1800C23BC
0x1800c23b6  mov     r8d, [rcx]
0x1800c23b9  and     r8d, edi
0x1800c23bc  call    ?MsgStringGetData@@YAPEB_WPEAUMsgString@@@Z; MsgStringGetData(MsgString *)
0x1800c23c1  mov     rdx, rax; wchar_t *
0x1800c23c4  lea     rcx, [rbp+57h+var_B8]; this
0x1800c23c8  call    ??0hstring@winrt@@QEAA@PEB_WI@Z; winrt::hstring::hstring(wchar_t const *,uint)
0x1800c23cd  lea     rcx, [r13+70h]
0x1800c23d1  cmp     rcx, rax
0x1800c23d4  jz      short loc_1800C23E1
0x1800c23d6  mov     rdx, [rax]
0x1800c23d9  mov     [rax], r12
0x1800c23dc  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x1800c23e1  lea     rcx, [rbp+57h+var_B8]
0x1800c23e5  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800c23ea  mov     rcx, [rbp+57h+var_C0]; struct MsgString *
0x1800c23ee  test    rcx, rcx
0x1800c23f1  jnz     short loc_1800C23F8
0x1800c23f3  mov     r8d, r12d
0x1800c23f6  jmp     short loc_1800C23FE
0x1800c23f8  mov     r8d, [rcx]
0x1800c23fb  and     r8d, edi
0x1800c23fe  call    ?MsgStringGetData@@YAPEB_WPEAUMsgString@@@Z; MsgStringGetData(MsgString *)
0x1800c2403  mov     rdx, rax; wchar_t *
0x1800c2406  lea     rcx, [rbp+57h+var_B8]; this
0x1800c240a  call    ??0hstring@winrt@@QEAA@PEB_WI@Z; winrt::hstring::hstring(wchar_t const *,uint)
0x1800c240f  lea     rcx, [r13+78h]
0x1800c2413  cmp     rcx, rax
0x1800c2416  jz      short loc_1800C2423
0x1800c2418  mov     rdx, [rax]
0x1800c241b  mov     [rax], r12
0x1800c241e  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x1800c2423  lea     rcx, [rbp+57h+var_B8]
0x1800c2427  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800c242c  mov     rcx, [rbp+57h+var_80]; struct MsgString *
0x1800c2430  test    rcx, rcx
0x1800c2433  jnz     short loc_1800C243A
0x1800c2435  mov     r8d, r12d
0x1800c2438  jmp     short loc_1800C2440
0x1800c243a  mov     r8d, [rcx]
0x1800c243d  and     r8d, edi
0x1800c2440  call    ?MsgStringGetData@@YAPEB_WPEAUMsgString@@@Z; MsgStringGetData(MsgString *)
0x1800c2445  mov     rdx, rax; wchar_t *
0x1800c2448  lea     rcx, [rbp+57h+var_B8]; this
0x1800c244c  call    ??0hstring@winrt@@QEAA@PEB_WI@Z; winrt::hstring::hstring(wchar_t const *,uint)
0x1800c2451  lea     rcx, [r13+80h]
0x1800c2458  cmp     rcx, rax
0x1800c245b  jz      short loc_1800C2468
0x1800c245d  mov     rdx, [rax]
0x1800c2460  mov     [rax], r12
0x1800c2463  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x1800c2468  lea     rcx, [rbp+57h+var_B8]
0x1800c246c  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800c2471  mov     eax, [rbp+57h+var_5C]
0x1800c2474  mov     [r13+90h], eax
0x1800c247b  mov     eax, [rbp+57h+var_60]
0x1800c247e  xchg    eax, [r13+0A4h]
0x1800c2485  mov     eax, 1
0x1800c248a  xchg    eax, [r13+0A8h]
0x1800c2491  movsxd  rdi, dword ptr [r15+8Ch]
0x1800c2498  test    edi, edi
0x1800c249a  jnz     short loc_1800C24FE
0x1800c249c  lea     r9, aStartComplete; "Start complete"
0x1800c24a3  mov     r8d, 4A6h; unsigned int
0x1800c24a9  lea     rdx, aWinrtWindowsud_16; "winrt::WindowsUdk::UI::Input::Text::imp"...
0x1800c24b0  lea     rcx, aShellcommonUnd_153; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800c24b7  call    ?ZTraceAsWil@@YAXPEBD0IPEA_WZZ; ZTraceAsWil(char const *,char const *,uint,wchar_t *,...)
0x1800c24bc  mov     rbx, [r15+68h]
0x1800c24c0  test    rbx, rbx
0x1800c24c3  jz      loc_1800C256F
0x1800c24c9  mov     rax, [rbp+57h+var_90]
0x1800c24cd  mov     [rbp+57h+var_B8], rax
0x1800c24d1  lea     rcx, [rbp+57h+var_B8]
0x1800c24d5  call    ?add_ref@?$com_ptr@UModalDialog@implementation@Shell@UI@WindowsUdk@winrt@@@winrt@@AEBAXXZ; winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ModalDialog>::add_ref(void)
0x1800c24da  mov     [rbp+57h+var_B0], 1
0x1800c24de  lea     rdx, [rbp+57h+var_B8]
0x1800c24e2  mov     rcx, rbx
0x1800c24e5  call    ?set@?$task_completion_event@V?$optional@UDictatedTextInputSession@Text@Input@UI@WindowsUdk@winrt@@@std@@@Concurrency@@QEBA_NV?$optional@UDictatedTextInputSession@Text@Input@UI@WindowsUdk@winrt@@@std@@@Z; Concurrency::task_completion_event<std::optional<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>>::set(std::optional<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>)
0x1800c24ea  mov     rdx, [r15+68h]
0x1800c24ee  mov     [r15+68h], r12
0x1800c24f2  test    rdx, rdx
0x1800c24f5  jz      short loc_1800C256F
0x1800c24f7  call    ??R?$default_delete@V?$task_completion_event@V?$optional@UDictatedTextInputSession@Text@Input@UI@WindowsUdk@winrt@@@std@@@Concurrency@@@std@@QEBAXPEAV?$task_completion_event@V?$optional@UDictatedTextInputSession@Text@Input@UI@WindowsUdk@winrt@@@std@@@Concurrency@@@Z; std::default_delete<Concurrency::task_completion_event<std::optional<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>>>::operator()(Concurrency::task_completion_event<std::optional<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>> *)
0x1800c24fc  jmp     short loc_1800C256F
0x1800c24fe  lea     rsi, [r15+18h]
0x1800c2502  mov     [rbp+57h+var_B8], rdi
0x1800c2506  lea     r8, [rbp+57h+var_B8]
0x1800c250a  lea     rdx, [rbp+57h+var_78]
0x1800c250e  mov     rcx, rsi
0x1800c2511  call    ?find@?$_Tree@V?$_Tmap_traits@_JU?$handle_type@Uhandle_traits@winrt@@@winrt@@U?$less@_J@std@@V?$allocator@U?$pair@$$CB_JU?$handle_type@Uhandle_traits@winrt@@@winrt@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JU?$handle_type@Uhandle_traits@winrt@@@winrt@@@std@@@std@@@std@@@2@AEB_J@Z; std::_Tree<std::_Tmap_traits<__int64,winrt::handle_type<winrt::handle_traits>,std::less<__int64>,std::allocator<std::pair<__int64 const,winrt::handle_type<winrt::handle_traits>>>,0>>::find(__int64 const &)
0x1800c2516  mov     rbx, [rbp+57h+var_78]
0x1800c251a  cmp     rbx, [rsi]
0x1800c251d  jz      short loc_1800C256F
0x1800c251f  mov     eax, [r13+0A8h]
0x1800c2526  nop
0x1800c2527  mov     [rsp+0F0h+var_C8], eax
0x1800c252b  mov     [rsp+0F0h+var_D0], edi
0x1800c252f  lea     r9, aRefreshOfIdDCo; "refresh of id %d complete; status = %d"
0x1800c2536  mov     r8d, 4B2h; unsigned int
0x1800c253c  lea     rdx, aWinrtWindowsud_16; "winrt::WindowsUdk::UI::Input::Text::imp"...
0x1800c2543  lea     rcx, aShellcommonUnd_153; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800c254a  call    ?ZTraceAsWil@@YAXPEBD0IPEA_WZZ; ZTraceAsWil(char const *,char const *,uint,wchar_t *,...)
0x1800c254f  mov     rcx, [rbx+28h]; hEvent
0x1800c2553  call    cs:__imp_SetEvent
0x1800c2559  mov     r8, rbx
0x1800c255c  lea     rdx, [rbp+57h+var_B8]
0x1800c2560  mov     rcx, rsi
0x1800c2563  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JU?$handle_type@Uhandle_traits@winrt@@@winrt@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@_JU?$handle_type@Uhandle_traits@winrt@@@winrt@@U?$less@_J@std@@V?$allocator@U?$pair@$$CB_JU?$handle_type@Uhandle_traits@winrt@@@winrt@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JU?$handle_type@Uhandle_traits@winrt@@@winrt@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<__int64,winrt::handle_type<winrt::handle_traits>,std::less<__int64>,std::allocator<std::pair<__int64 const,winrt::handle_type<winrt::handle_traits>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,winrt::handle_type<winrt::handle_traits>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,winrt::handle_type<winrt::handle_traits>>>>>)
  ... truncated ...
```
