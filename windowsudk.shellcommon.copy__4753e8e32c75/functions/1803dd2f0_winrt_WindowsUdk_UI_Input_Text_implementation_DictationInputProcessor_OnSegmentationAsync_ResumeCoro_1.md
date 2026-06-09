# winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnSegmentationAsync$_ResumeCoro$1

- ea: `0x1803dd2f0`
- end: `0x1803dd70c`
- name: `winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnSegmentationAsync$_ResumeCoro$1`
- size: `1052`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1803dd714`

## callees

- `0x18000b428`
- `0x18000b444`
- `0x180025348`
- `0x18004f234`
- `0x18004f258`
- `0x1800549a8`
- `0x18006a030`
- `0x1800dca48`
- `0x1800eba80`
- `0x1800ebacc`
- `0x1800f0238`
- `0x1801365bc`
- `0x18015cfa0`
- `0x180287674`
- `0x18028b43c`
- `0x1802bf744`
- `0x1802f0f48`
- `0x1803d7798`
- `0x1803dd2f0`
- `0x1804a2010`

## import_xrefs

- `CoreMessaging!MsgRelease` at `0x1803dd404`
- `CoreMessaging!MsgRelease` at `0x1803dd47f`
- `CoreMessaging!MsgRelease` at `0x1803dd404`
- `CoreMessaging!MsgRelease` at `0x1803dd47f`
- `CoreMessaging!MsgStringCreateShared` at `0x1803dd3be`
- `CoreMessaging!MsgStringCreateShared` at `0x1803dd43b`
- `CoreMessaging!MsgStringCreateShared` at `0x1803dd49f`
- `CoreMessaging!MsgStringCreateShared` at `0x1803dd3be`
- `CoreMessaging!MsgStringCreateShared` at `0x1803dd43b`
- `CoreMessaging!MsgStringCreateShared` at `0x1803dd49f`

## string_xrefs

- `0x1803dd564`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text\dictatedtextinputsession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnSegmentationAsync__ResumeCoro_1(
        __int64 a1)
{
  __int64 v2; // r14
  __int64 v3; // r10
  int v4; // r11d
  __int64 *v5; // r12
  __int64 *v6; // r15
  const wchar_t *v7; // rax
  unsigned int Shared; // eax
  __int64 v9; // rbx
  __int64 v10; // r13
  const wchar_t *v11; // rax
  unsigned int v12; // eax
  __int64 v13; // r13
  unsigned int v14; // eax
  __int64 v15; // rbx
  __int64 *v16; // r10
  __int64 v17; // rax
  __int64 v18; // rcx
  unsigned int v19; // eax
  __int64 ActionAsync; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // [rsp+20h] [rbp-B8h]
  unsigned int v24; // [rsp+E8h] [rbp+10h]

  v2 = a1 + 8;
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_13;
    case 2:
      winrt::implements<winrt::WindowsUdk::System::Profile::implementation::SystemSettingEntryPointIndex,winrt::WindowsUdk::System::Profile::SystemSettingEntryPointIndex>::get_strong(
        *(_QWORD *)(a1 + 312),
        a1 + 16);
      *(_DWORD *)(v3 + 136) += v4;
      v24 = *(_DWORD *)(v3 + 136);
      v5 = (__int64 *)(a1 + 32);
      *(_QWORD *)(a1 + 32) = 0;
      v6 = (__int64 *)(a1 + 40);
      *(_QWORD *)(a1 + 40) = 0;
      *(_DWORD *)(a1 + 48) = 0;
      *(_QWORD *)(a1 + 56) = 0;
      *(_QWORD *)(a1 + 64) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      v7 = winrt::hstring::c_str(*(winrt::hstring **)(a1 + 336));
      Shared = MsgStringCreateShared(v7);
      winrt::check_hresult(a1 + 72, Shared, a1 + 48);
      v9 = a1 + 80;
      *(_DWORD *)(a1 + 80) = 0;
      *(_QWORD *)(a1 + 88) = 0;
      *(_QWORD *)(a1 + 96) = 0;
      v10 = *(_QWORD *)(a1 + 32);
      if ( v10 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)(a1 + 256));
        MsgRelease(v10);
        wil::last_error_context::~last_error_context((wil::last_error_context *)(a1 + 256));
        v9 = a1 + 80;
      }
      *v5 = 0;
      v11 = winrt::hstring::c_str(*(winrt::hstring **)(a1 + 344));
      v12 = MsgStringCreateShared(v11);
      winrt::check_hresult(a1 + 104, v12, v9);
      *(_DWORD *)(a1 + 112) = 0;
      *(_QWORD *)(a1 + 120) = 0;
      *(_QWORD *)(a1 + 128) = 0;
      v13 = *v6;
      if ( *v6 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)(a1 + 288));
        MsgRelease(v13);
        wil::last_error_context::~last_error_context((wil::last_error_context *)(a1 + 288));
      }
      *v6 = 0;
      v14 = MsgStringCreateShared(L"35681b48-0f60-49ec-80ef-cadd76a84ca1");
      winrt::check_hresult(a1 + 136, v14, a1 + 112);
      *(_DWORD *)(a1 + 144) = 0;
      *(_QWORD *)(a1 + 152) = 0;
      *(_QWORD *)(a1 + 160) = 0;
      v15 = *(_QWORD *)(v2 + 304);
      v16 = *(__int64 **)(v15 + 40);
      v17 = *v16;
      v18 = *v5;
      *(_OWORD *)(a1 + 240) = *(_OWORD *)(a1 + 320);
      HIDWORD(v23) = HIDWORD(v18);
      v19 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(v17 + 48))(v16, a1 + 240, v24);
      winrt::check_hresult(a1 + 168, v19, a1 + 144);
      LODWORD(v23) = v24;
      ZTraceAsWil(
        "shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text\\dictatedtextinputsession.cpp",
        "winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::OnSegmentationAsync",
        0x3A2u,
        (wchar_t *)L"DictationInputProcessor::DisplayFinalResult id (%d)",
        v23);
      *(_QWORD *)(a1 + 272) = a1 - 112;
      ActionAsync = winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::GetActionAsync(
                      v15,
                      a1 + 184,
                      v24);
      v21 = winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::AI::MachineLearning::WisePredictor>,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::AI::MachineLearning::WisePredictor>,void>::await_transform<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::PredictionUnit::Predictor>>(
              a1 - 112,
              ActionAsync);
      v22 = winrt::Windows::Foundation::operator co_await<winrt::hstring>(a1 + 192, v21);
      *(_QWORD *)(a1 + 176) = v22;
      *(_WORD *)v2 = 4;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::WindowsUdk::UI::Input::Text::implementation::DictatedTextInputSession *,int>::promise_type>(
                              v22,
                              a1) )
        return;
      goto LABEL_10;
    case 4:
LABEL_10:
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_resume(*(_QWORD *)(a1 + 176));
      winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,1>>(a1 + 192);
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 184));
      wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(a1 + 40);
      wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(a1 + 32);
      wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(a1 + 24);
      if ( *(_QWORD *)(a1 + 16) )
        winrt::com_ptr<winrt::WindowsUdk::UI::Input::Text::implementation::SpeechCorrectionCandidateWindowClient>::unconditional_release_ref(a1 + 16);
      *(_QWORD *)(a1 + 224) = *(_QWORD *)(a1 + 272);
      *(_WORD *)v2 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::WindowsUdk::UI::MenuItem>>,winrt::Windows::Storage::IStorageItem,winrt::Windows::System::User,winrt::WindowsUdk::UI::MenuItemGetOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::WindowsUdk::UI::MenuItem>>,void>::final_suspend_awaiter::await_suspend() )
        goto LABEL_13;
      return;
    case 5:
      winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,1>>(a1 + 192);
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 184));
      wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(a1 + 40);
      wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(a1 + 32);
      wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(a1 + 24);
      if ( *(_QWORD *)(a1 + 16) )
        winrt::com_ptr<winrt::WindowsUdk::UI::Input::Text::implementation::SpeechCorrectionCandidateWindowClient>::unconditional_release_ref(a1 + 16);
LABEL_13:
      winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::WindowsUdk::UI::Input::Text::implementation::InputMethodConversionIndicator *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,void>::~promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::WindowsUdk::UI::Input::Text::implementation::InputMethodConversionIndicator *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,void>(a1 - 112);
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 112), (const struct std::nothrow_t *)0x1D0);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x1803dd2f0  mov     [rsp+arg_0], rcx
0x1803dd2f5  push    rbx
0x1803dd2f6  push    rsi
0x1803dd2f7  push    rdi
0x1803dd2f8  push    r12
0x1803dd2fa  push    r13
0x1803dd2fc  push    r14
0x1803dd2fe  push    r15
0x1803dd300  sub     rsp, 0A0h
0x1803dd307  mov     rdi, [rsp+0D8h+arg_0]
0x1803dd30f  lea     r14, [rdi+8]
0x1803dd313  mov     [rsp+0D8h+var_78], r14
0x1803dd318  movzx   eax, word ptr [r14]
0x1803dd31c  mov     [rsp+0D8h+var_88], ax
0x1803dd321  mov     r11d, 1
0x1803dd327  add     ax, r11w
0x1803dd32b  cmp     ax, 6; switch 7 cases
0x1803dd32f  ja      def_1803DD34A; jumptable 00000001803DD34A default case, case 1
0x1803dd335  movsx   rax, ax
0x1803dd339  lea     rdx, __ImageBase
0x1803dd340  mov     ecx, ds:(jpt_1803DD34A - 180000000h)[rdx+rax*4]
0x1803dd347  add     rcx, rdx
0x1803dd34a  jmp     rcx; switch jump
0x1803dd34c  xor     esi, esi; jumptable 00000001803DD34A case 4
0x1803dd34e  jmp     loc_1803DD6B9
0x1803dd353  mov     r10, [r14+130h]; jumptable 00000001803DD34A case 3
0x1803dd35a  lea     rdx, [rdi+10h]
0x1803dd35e  mov     rcx, r10
0x1803dd361  call    ?get_strong@?$implements@USystemSettingEntryPointIndex@implementation@Profile@System@WindowsUdk@winrt@@U13456@@winrt@@QEAA?AU?$com_ptr@USystemSettingEntryPointIndex@implementation@Profile@System@WindowsUdk@winrt@@@2@XZ; winrt::implements<winrt::WindowsUdk::System::Profile::implementation::SystemSettingEntryPointIndex,winrt::WindowsUdk::System::Profile::SystemSettingEntryPointIndex>::get_strong(void)
0x1803dd366  nop
0x1803dd367  add     [r10+88h], r11d
0x1803dd36e  mov     eax, [r10+88h]
0x1803dd375  mov     [rsp+0D8h+arg_8], eax
0x1803dd37c  lea     r12, [rdi+20h]
0x1803dd380  xor     esi, esi
0x1803dd382  mov     [r12], rsi
0x1803dd386  lea     r15, [rdi+28h]
0x1803dd38a  mov     [r15], rsi
0x1803dd38d  mov     [rdi+30h], esi
0x1803dd390  mov     [rdi+38h], rsi
0x1803dd394  mov     [rdi+40h], rsi
0x1803dd398  lea     r8, [rdi+18h]
0x1803dd39c  mov     [r8], rsi
0x1803dd39f  mov     rcx, [r12+130h]; this
0x1803dd3a7  mov     rax, [rcx]
0x1803dd3aa  test    rax, rax
0x1803dd3ad  jz      short loc_1803DD3B4
0x1803dd3af  mov     edx, [rax+4]
0x1803dd3b2  jmp     short loc_1803DD3B6
0x1803dd3b4  mov     edx, esi
0x1803dd3b6  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1803dd3bb  mov     rcx, rax
0x1803dd3be  call    cs:__imp_MsgStringCreateShared
0x1803dd3c4  lea     rcx, [rdi+48h]
0x1803dd3c8  lea     r8, [rdi+30h]
0x1803dd3cc  mov     edx, eax
0x1803dd3ce  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1803dd3d3  lea     rbx, [rdi+50h]
0x1803dd3d7  mov     [rbx], esi
0x1803dd3d9  mov     [rdi+58h], rsi
0x1803dd3dd  mov     [rdi+60h], rsi
0x1803dd3e1  mov     r13, [r12]
0x1803dd3e5  test    r13, r13
0x1803dd3e8  jz      short loc_1803DD416
0x1803dd3ea  mov     [rsp+0D8h+arg_18], r13
0x1803dd3f2  lea     rbx, [rdi+100h]
0x1803dd3f9  mov     rcx, rbx; this
0x1803dd3fc  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1803dd401  mov     rcx, r13
0x1803dd404  call    cs:__imp_MsgRelease
0x1803dd40a  mov     rcx, rbx; this
0x1803dd40d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1803dd412  lea     rbx, [rdi+50h]
0x1803dd416  mov     [r12], rsi
0x1803dd41a  mov     rcx, [r15+130h]; this
0x1803dd421  mov     rax, [rcx]
0x1803dd424  test    rax, rax
0x1803dd427  jz      short loc_1803DD42E
0x1803dd429  mov     edx, [rax+4]
0x1803dd42c  jmp     short loc_1803DD430
0x1803dd42e  mov     edx, esi
0x1803dd430  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1803dd435  mov     r8, r12
0x1803dd438  mov     rcx, rax
0x1803dd43b  call    cs:__imp_MsgStringCreateShared
0x1803dd441  lea     rcx, [rdi+68h]
0x1803dd445  mov     r8, rbx
0x1803dd448  mov     edx, eax
0x1803dd44a  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1803dd44f  mov     [rdi+70h], esi
0x1803dd452  mov     [rdi+78h], rsi
0x1803dd456  mov     [rdi+80h], rsi
0x1803dd45d  mov     r13, [r15]
0x1803dd460  test    r13, r13
0x1803dd463  jz      short loc_1803DD48D
0x1803dd465  mov     [rsp+0D8h+arg_10], r13
0x1803dd46d  lea     rbx, [rdi+120h]
0x1803dd474  mov     rcx, rbx; this
0x1803dd477  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1803dd47c  mov     rcx, r13
0x1803dd47f  call    cs:__imp_MsgRelease
0x1803dd485  mov     rcx, rbx; this
0x1803dd488  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1803dd48d  mov     [r15], rsi
0x1803dd490  mov     r8, r15
0x1803dd493  mov     edx, 24h ; '$'
0x1803dd498  lea     rcx, a35681b480f6049; "35681b48-0f60-49ec-80ef-cadd76a84ca1"
0x1803dd49f  call    cs:__imp_MsgStringCreateShared
0x1803dd4a5  lea     rcx, [rdi+88h]
0x1803dd4ac  lea     r8, [rdi+70h]
0x1803dd4b0  mov     edx, eax
0x1803dd4b2  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1803dd4b7  lea     r13, [rdi+90h]
0x1803dd4be  mov     [r13+0], esi
0x1803dd4c2  mov     [rdi+98h], rsi
0x1803dd4c9  mov     [rdi+0A0h], rsi
0x1803dd4d0  mov     rbx, [r14+130h]
0x1803dd4d7  mov     r10, [rbx+28h]
0x1803dd4db  mov     rax, [r10]
0x1803dd4de  mov     r8, [r15]
0x1803dd4e1  mov     [rsp+0D8h+arg_10], r8
0x1803dd4e9  mov     rcx, [r12]
0x1803dd4ed  mov     [rsp+0D8h+arg_18], rcx
0x1803dd4f5  mov     r9, [rdi+18h]
0x1803dd4f9  mov     [rsp+0D8h+var_70], r9
0x1803dd4fe  lea     rdx, [rdi+0F0h]
0x1803dd505  movups  xmm0, xmmword ptr [rdi+140h]
0x1803dd50c  movdqu  xmmword ptr [rdx], xmm0
0x1803dd510  mov     [rsp+0D8h+var_A0], 1
0x1803dd515  mov     [rsp+0D8h+var_A8], esi
0x1803dd519  mov     [rsp+0D8h+var_B0], r8
0x1803dd51e  mov     [rsp+0D8h+var_B8], rcx
0x1803dd523  mov     r12d, [rsp+0D8h+arg_8]
0x1803dd52b  mov     r8d, r12d
0x1803dd52e  mov     rcx, r10
0x1803dd531  mov     rax, [rax+30h]
0x1803dd535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803dd53a  lea     rcx, [rdi+0A8h]
0x1803dd541  mov     r8, r13
0x1803dd544  mov     edx, eax
0x1803dd546  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1803dd54b  mov     dword ptr [rsp+0D8h+var_B8], r12d
0x1803dd550  lea     r9, aDictationinput_0; "DictationInputProcessor::DisplayFinalRe"...
0x1803dd557  mov     r8d, 3A2h; unsigned int
0x1803dd55d  lea     rdx, aWinrtWindowsud_12; "winrt::WindowsUdk::UI::Input::Text::imp"...
0x1803dd564  lea     rcx, aShellcommonUnd_153; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1803dd56b  call    ?ZTraceAsWil@@YAXPEBD0IPEA_WZZ; ZTraceAsWil(char const *,char const *,uint,wchar_t *,...)
0x1803dd570  lea     r15, [rdi-70h]
0x1803dd574  mov     [rdi+110h], r15
0x1803dd57b  lea     rdx, [rdi+0B8h]
0x1803dd582  mov     r8d, r12d
0x1803dd585  mov     rcx, rbx
0x1803dd588  call    ?GetActionAsync@DictationInputProcessor@implementation@Text@Input@UI@WindowsUdk@winrt@@QEAA?AUIAsyncAction@Foundation@Windows@7@H@Z; winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::GetActionAsync(int)
0x1803dd58d  nop
0x1803dd58e  mov     rdx, rax
0x1803dd591  mov     rcx, r15
0x1803dd594  call    ??$await_transform@U?$IAsyncOperation@UPredictor@PredictionUnit@Internal@Windows@winrt@@@Foundation@Windows@winrt@@@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UWisePredictor@MachineLearning@AI@WindowsUdk@winrt@@@Foundation@Windows@winrt@@Uhstring@4@U54@@experimental@std@@U?$IAsyncOperation@UWisePredictor@MachineLearning@AI@WindowsUdk@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEAA$$QEAU?$IAsyncOperation@UPredictor@PredictionUnit@Internal@Windows@winrt@@@Foundation@Windows@2@$$QEAU3452@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::AI::MachineLearning::WisePredictor>,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::AI::MachineLearning::WisePredictor>,void>::await_transform<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::PredictionUnit::Predictor>>(winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::PredictionUnit::Predictor> &&)
0x1803dd599  lea     rcx, [rdi+0C0h]
0x1803dd5a0  mov     rdx, rax
0x1803dd5a3  call    ??$?__LUhstring@winrt@@@Foundation@Windows@winrt@@YA?AU?$await_adapter@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@$00@impl@2@AEBU?$IAsyncOperation@Uhstring@winrt@@@012@@Z; winrt::Windows::Foundation::operator co_await<winrt::hstring>(winrt::Windows::Foundation::IAsyncOperation<winrt::hstring> const &)
0x1803dd5a8  mov     [rdi+0B0h], rax
0x1803dd5af  mov     ecx, 4
0x1803dd5b4  mov     [r14], cx
0x1803dd5b8  mov     rdx, rdi
0x1803dd5bb  mov     rcx, rax
0x1803dd5be  call    ??$await_suspend@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUDictatedTextInputSession@implementation@Text@Input@UI@WindowsUdk@4@H@experimental@std@@@?$await_adapter@UIAsyncAction@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUDictatedTextInputSession@implementation@Text@Input@UI@WindowsUdk@4@H@experimental@std@@@experimental@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::WindowsUdk::UI::Input::Text::implementation::DictatedTextInputSession *,int>::promise_type>(std::experimental::coroutine_handle<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::WindowsUdk::UI::Input::Text::implementation::DictatedTextInputSession *,int>::promise_type>)
0x1803dd5c3  test    al, al
0x1803dd5c5  jz      short loc_1803DD624
0x1803dd5c7  jmp     loc_1803DD6D9
0x1803dd5cc  lea     rcx, [rdi+0C0h]; jumptable 00000001803DD34A case 6
0x1803dd5d3  call    ??1?$cancellable_awaiter@U?$await_adapter@U?$IAsyncOperation@I@Foundation@Windows@winrt@@$00@impl@winrt@@@winrt@@QEAA@XZ; winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<uint>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<uint>,1>>(void)
0x1803dd5d8  nop
0x1803dd5d9  lea     rcx, [rdi+0B8h]; this
0x1803dd5e0  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1803dd5e5  nop
0x1803dd5e6  lea     rcx, [rdi+28h]
0x1803dd5ea  call    ??1?$unique_storage@U?$resource_policy@PEAUMsgString@@P6AXPEAUMsgBuffer@@@Z$1?MsgRelease@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(void)
0x1803dd5ef  nop
0x1803dd5f0  lea     rcx, [rdi+20h]
0x1803dd5f4  call    ??1?$unique_storage@U?$resource_policy@PEAUMsgString@@P6AXPEAUMsgBuffer@@@Z$1?MsgRelease@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(void)
0x1803dd5f9  nop
0x1803dd5fa  lea     rcx, [rdi+18h]
0x1803dd5fe  call    ??1?$unique_storage@U?$resource_policy@PEAUMsgString@@P6AXPEAUMsgBuffer@@@Z$1?MsgRelease@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(void)
0x1803dd603  nop
0x1803dd604  lea     rcx, [rdi+10h]
0x1803dd608  mov     rax, [rcx]
0x1803dd60b  mov     [rsp+0D8h+var_80], rax
0x1803dd610  xor     esi, esi
0x1803dd612  test    rax, rax
0x1803dd615  jz      short loc_1803DD61D
0x1803dd617  call    ?unconditional_release_ref@?$com_ptr@USpeechCorrectionCandidateWindowClient@implementation@Text@Input@UI@WindowsUdk@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::WindowsUdk::UI::Input::Text::implementation::SpeechCorrectionCandidateWindowClient>::unconditional_release_ref(void)
0x1803dd61c  nop
0x1803dd61d  jmp     loc_1803DD6B9
0x1803dd622  xor     esi, esi; jumptable 00000001803DD34A case 5
0x1803dd624  mov     rcx, [rdi+0B0h]
0x1803dd62b  call    ?await_resume@?$await_adapter@UIAsyncAction@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_resume(void)
0x1803dd630  nop
0x1803dd631  lea     rcx, [rdi+0C0h]
0x1803dd638  call    ??1?$cancellable_awaiter@U?$await_adapter@U?$IAsyncOperation@I@Foundation@Windows@winrt@@$00@impl@winrt@@@winrt@@QEAA@XZ; winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<uint>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<uint>,1>>(void)
0x1803dd63d  nop
0x1803dd63e  lea     rcx, [rdi+0B8h]; this
0x1803dd645  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1803dd64a  nop
0x1803dd64b  lea     rcx, [rdi+28h]
0x1803dd64f  call    ??1?$unique_storage@U?$resource_policy@PEAUMsgString@@P6AXPEAUMsgBuffer@@@Z$1?MsgRelease@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(void)
0x1803dd654  nop
0x1803dd655  lea     rcx, [rdi+20h]
0x1803dd659  call    ??1?$unique_storage@U?$resource_policy@PEAUMsgString@@P6AXPEAUMsgBuffer@@@Z$1?MsgRelease@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(void)
0x1803dd65e  nop
0x1803dd65f  lea     rcx, [rdi+18h]
0x1803dd663  call    ??1?$unique_storage@U?$resource_policy@PEAUMsgString@@P6AXPEAUMsgBuffer@@@Z$1?MsgRelease@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(void)
0x1803dd668  nop
0x1803dd669  lea     rcx, [rdi+10h]
0x1803dd66d  mov     rax, [rcx]
0x1803dd670  mov     [rsp+0D8h+var_80], rax
0x1803dd675  test    rax, rax
0x1803dd678  jz      short loc_1803DD680
0x1803dd67a  call    ?unconditional_release_ref@?$com_ptr@USpeechCorrectionCandidateWindowClient@implementation@Text@Input@UI@WindowsUdk@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::WindowsUdk::UI::Input::Text::implementation::SpeechCorrectionCandidateWindowClient>::unconditional_release_ref(void)
0x1803dd67f  nop
0x1803dd680  mov     rax, [rdi+110h]
0x1803dd687  jmp     short loc_1803DD69C
0x1803dd689  mov     rdi, [rsp+0D8h+arg_0]
0x1803dd691  lea     rax, [rdi-70h]
0x1803dd695  xor     esi, esi
0x1803dd697  mov     r14, [rsp+0D8h+var_78]
0x1803dd69c  lea     rcx, [rdi+0E0h]
0x1803dd6a3  mov     [rcx], rax
0x1803dd6a6  xor     eax, eax
0x1803dd6a8  mov     [r14], ax
0x1803dd6ac  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@U?$IVectorView@UMenuItem@UI@WindowsUdk@winrt@@@Collections@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@UIStorageItem@Storage@34@UUser@System@34@UMenuItemGetOptions@UI@WindowsUdk@4@@experimental@std@@U?$IAsyncOperation@U?$IVectorView@UMenuItem@UI@WindowsUdk@winrt@@@Collections@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@experimental@std@@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::WindowsUdk::UI::MenuItem>>,winrt::Windows::Storage::IStorageItem,winrt::Windows::System::User,winrt::WindowsUdk::UI::MenuItemGetOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::WindowsUdk::UI::MenuItem>>,void>::final_suspend_awaiter::await_suspend(std::experimental::coroutine_handle<void>)
0x1803dd6b1  test    al, al
0x1803dd6b3  jz      short loc_1803DD6B9
0x1803dd6b5  jmp     short loc_1803DD6D9
0x1803dd6b7  xor     esi, esi; jumptable 00000001803DD34A cases 0,2
0x1803dd6b9  lea     rcx, [rdi-70h]
0x1803dd6bd  call    ??1?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@USoftwareBitmap@Imaging@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUInputMethodConversionIndicator@implementation@Text@Input@UI@WindowsUdk@4@@experimental@std@@U?$IAsyncOperation@USoftwareBitmap@Imaging@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@UEAA@XZ; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::WindowsUdk::UI::Input::Text::implementation::InputMethodConversionIndicator *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,void>::~promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::WindowsUdk::UI::Input::Text::implementation::InputMethodConversionIndicator *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,void>(void)
0x1803dd6c2  cmp     [rdi+0Ah], si
0x1803dd6c6  jz      short loc_1803DD6D9
0x1803dd6c8  mov     edx, 1D0h; struct std::nothrow_t *
0x1803dd6cd  lea     rcx, [rdi-70h]; void *
0x1803dd6d1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1803dd6d6  jmp     short loc_1803DD6D9
0x1803dd6d8  int     3; Trap to Debugger
0x1803dd6d9  add     rsp, 0A0h
0x1803dd6e0  pop     r15
0x1803dd6e2  pop     r14
0x1803dd6e4  pop     r13
0x1803dd6e6  pop     r12
0x1803dd6e8  pop     rdi
0x1803dd6e9  pop     rsi
0x1803dd6ea  pop     rbx
0x1803dd6eb  retn
```
