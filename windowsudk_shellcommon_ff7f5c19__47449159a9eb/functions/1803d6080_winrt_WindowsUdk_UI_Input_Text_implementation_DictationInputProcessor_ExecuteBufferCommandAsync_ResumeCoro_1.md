# winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::ExecuteBufferCommandAsync$_ResumeCoro$1

- ea: `0x1803d6080`
- end: `0x1803d64a4`
- name: `winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::ExecuteBufferCommandAsync$_ResumeCoro$1`
- size: `1060`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1803d64ac`

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
- `0x1803d6080`
- `0x1803d7798`
- `0x1804a2010`

## import_xrefs

- `CoreMessaging!MsgRelease` at `0x1803d6176`
- `CoreMessaging!MsgRelease` at `0x1803d6176`
- `CoreMessaging!MsgStringCreateShared` at `0x1803d6134`
- `CoreMessaging!MsgStringCreateShared` at `0x1803d61ad`
- `CoreMessaging!MsgStringCreateShared` at `0x1803d6134`
- `CoreMessaging!MsgStringCreateShared` at `0x1803d61ad`

## string_xrefs

- `0x1803d62a9`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text\dictatedtextinputsession.cpp`
- `0x1803d62a2`: `winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::ExecuteBufferCommandAsync`
- `0x1803d6295`: `DictationInputProcessor::ExecuteBufferCommandAsync id (%d)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::ExecuteBufferCommandAsync__ResumeCoro_1(
        __int64 a1)
{
  _WORD *v2; // r14
  __int64 v3; // r13
  __int64 *v4; // r12
  __int64 v5; // rbx
  const wchar_t *v6; // rax
  unsigned int Shared; // eax
  __int64 v8; // r15
  const wchar_t *v9; // rax
  unsigned int v10; // eax
  __int64 v11; // rcx
  unsigned int v12; // eax
  __int64 *v13; // r11
  __int64 v14; // rax
  __int64 v15; // r10
  __int64 v16; // rcx
  unsigned int v17; // eax
  unsigned int v18; // r15d
  __int64 v19; // rcx
  unsigned int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // [rsp+20h] [rbp-98h]

  v2 = (_WORD *)(a1 + 8);
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_11;
    case 2:
      v3 = *(_QWORD *)(a1 + 360);
      winrt::implements<winrt::WindowsUdk::System::Profile::implementation::SystemSettingEntryPointIndex,winrt::WindowsUdk::System::Profile::SystemSettingEntryPointIndex>::get_strong(
        v3,
        a1 + 16);
      v4 = (__int64 *)(a1 + 32);
      *(_QWORD *)(a1 + 32) = 0;
      *(_QWORD *)(a1 + 40) = 0;
      v5 = a1 + 48;
      *(_DWORD *)(a1 + 48) = 0;
      *(_QWORD *)(a1 + 56) = 0;
      *(_QWORD *)(a1 + 64) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      v6 = winrt::hstring::c_str(*(winrt::hstring **)(a1 + 392));
      Shared = MsgStringCreateShared(v6);
      winrt::check_hresult(a1 + 72, Shared, a1 + 48);
      *(_DWORD *)(a1 + 80) = 0;
      *(_QWORD *)(a1 + 88) = 0;
      *(_QWORD *)(a1 + 96) = 0;
      v8 = *(_QWORD *)(a1 + 32);
      if ( v8 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)(a1 + 336));
        MsgRelease(v8);
        wil::last_error_context::~last_error_context((wil::last_error_context *)(a1 + 336));
        v5 = a1 + 48;
      }
      *v4 = 0;
      v9 = winrt::hstring::c_str(*(winrt::hstring **)(v5 + 352));
      v10 = MsgStringCreateShared(v9);
      winrt::check_hresult(a1 + 104, v10, a1 + 80);
      *(_DWORD *)(a1 + 112) = 0;
      *(_QWORD *)(a1 + 120) = 0;
      *(_QWORD *)(a1 + 128) = 0;
      v11 = *(_QWORD *)(v3 + 40);
      *(_OWORD *)(a1 + 272) = *(_OWORD *)(a1 + 368);
      v12 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v11 + 88LL))(v11, a1 + 272, 0);
      winrt::check_hresult(a1 + 136, v12, a1 + 112);
      *(_DWORD *)(a1 + 144) = 0;
      *(_QWORD *)(a1 + 152) = 0;
      *(_QWORD *)(a1 + 160) = 0;
      v13 = *(__int64 **)(v3 + 40);
      v14 = *v13;
      v15 = *v4;
      v16 = *(_QWORD *)(a1 + 24);
      *(_OWORD *)(a1 + 288) = *(_OWORD *)(a1 + 368);
      v17 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, _QWORD, __int64, __int64, _DWORD))(v14 + 72))(
              v13,
              a1 + 288,
              0,
              *(unsigned int *)(a1 + 384),
              v16,
              v15,
              0);
      winrt::check_hresult(a1 + 168, v17, a1 + 144);
      v18 = ++*(_DWORD *)(v3 + 136);
      LODWORD(v23) = v18;
      ZTraceAsWil(
        "shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text\\dictatedtextinputsession.cpp",
        "winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::ExecuteBufferCommandAsync",
        0x36Eu,
        (wchar_t *)L"DictationInputProcessor::ExecuteBufferCommandAsync id (%d)",
        v23);
      *(_DWORD *)(a1 + 176) = 0;
      *(_QWORD *)(a1 + 184) = 0;
      *(_QWORD *)(a1 + 192) = 0;
      v19 = *(_QWORD *)(v3 + 40);
      *(_OWORD *)(a1 + 304) = *(_OWORD *)(a1 + 368);
      v20 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v19 + 96LL))(v19, a1 + 304, v18);
      winrt::check_hresult(a1 + 200, v20, a1 + 176);
      *(_QWORD *)(a1 + 320) = a1 - 112;
      winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::GetActionAsync(v3, a1 + 216, v18);
      v21 = winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::AI::MachineLearning::WisePredictor>,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::AI::MachineLearning::WisePredictor>,void>::await_transform<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::PredictionUnit::Predictor>>(a1 - 112);
      v22 = winrt::Windows::Foundation::operator co_await<winrt::hstring>(a1 + 224, v21);
      *(_QWORD *)(a1 + 208) = v22;
      *v2 = 4;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::WindowsUdk::UI::Input::Text::implementation::DictatedTextInputSession *,int>::promise_type>(
                              v22,
                              a1) )
        return;
      goto LABEL_8;
    case 4:
LABEL_8:
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_resume(*(_QWORD *)(a1 + 208));
      winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,1>>(a1 + 224);
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 216));
      wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(a1 + 40);
      wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(a1 + 32);
      wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(a1 + 24);
      if ( *(_QWORD *)(a1 + 16) )
        winrt::com_ptr<winrt::WindowsUdk::UI::Input::Text::implementation::SpeechCorrectionCandidateWindowClient>::unconditional_release_ref(a1 + 16);
      *(_QWORD *)(a1 + 256) = *(_QWORD *)(a1 + 320);
      *v2 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::WindowsUdk::UI::MenuItem>>,winrt::Windows::Storage::IStorageItem,winrt::Windows::System::User,winrt::WindowsUdk::UI::MenuItemGetOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::WindowsUdk::UI::MenuItem>>,void>::final_suspend_awaiter::await_suspend() )
        goto LABEL_11;
      return;
    case 5:
      winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,1>>(a1 + 224);
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 216));
      wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(a1 + 40);
      wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(a1 + 32);
      wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(a1 + 24);
      if ( *(_QWORD *)(a1 + 16) )
        winrt::com_ptr<winrt::WindowsUdk::UI::Input::Text::implementation::SpeechCorrectionCandidateWindowClient>::unconditional_release_ref(a1 + 16);
LABEL_11:
      winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::WindowsUdk::UI::Input::Text::implementation::InputMethodConversionIndicator *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,void>::~promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::WindowsUdk::UI::Input::Text::implementation::InputMethodConversionIndicator *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,void>(a1 - 112);
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 112), (const struct std::nothrow_t *)0x210);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x1803d6080  mov     [rsp+arg_0], rcx
0x1803d6085  push    rbx
0x1803d6086  push    rsi
0x1803d6087  push    rdi
0x1803d6088  push    r12
0x1803d608a  push    r13
0x1803d608c  push    r14
0x1803d608e  push    r15
0x1803d6090  sub     rsp, 80h
0x1803d6097  mov     rdi, [rsp+0B8h+arg_0]
0x1803d609f  lea     r14, [rdi+8]
0x1803d60a3  mov     [rsp+0B8h+arg_18], r14
0x1803d60ab  movzx   eax, word ptr [r14]
0x1803d60af  mov     [rsp+0B8h+var_78], ax
0x1803d60b4  inc     ax; switch 7 cases
0x1803d60b7  cmp     ax, 6
0x1803d60bb  ja      def_1803D60D6; jumptable 00000001803D60D6 default case, case 0
0x1803d60c1  movsx   rax, ax
0x1803d60c5  lea     rdx, __ImageBase
0x1803d60cc  mov     ecx, ds:(jpt_1803D60D6 - 180000000h)[rdx+rax*4]
0x1803d60d3  add     rcx, rdx
0x1803d60d6  jmp     rcx; switch jump
0x1803d60d8  xor     esi, esi; jumptable 00000001803D60D6 case 3
0x1803d60da  jmp     loc_1803D6454
0x1803d60df  mov     r13, [r14+160h]; jumptable 00000001803D60D6 case 2
0x1803d60e6  lea     rdx, [rdi+10h]
0x1803d60ea  mov     rcx, r13
0x1803d60ed  call    ?get_strong@?$implements@USystemSettingEntryPointIndex@implementation@Profile@System@WindowsUdk@winrt@@U13456@@winrt@@QEAA?AU?$com_ptr@USystemSettingEntryPointIndex@implementation@Profile@System@WindowsUdk@winrt@@@2@XZ; winrt::implements<winrt::WindowsUdk::System::Profile::implementation::SystemSettingEntryPointIndex,winrt::WindowsUdk::System::Profile::SystemSettingEntryPointIndex>::get_strong(void)
0x1803d60f2  nop
0x1803d60f3  lea     r12, [rdi+20h]
0x1803d60f7  xor     esi, esi
0x1803d60f9  mov     [r12], rsi
0x1803d60fd  mov     [rdi+28h], rsi
0x1803d6101  lea     rbx, [rdi+30h]
0x1803d6105  mov     [rbx], esi
0x1803d6107  mov     [rdi+38h], rsi
0x1803d610b  mov     [rdi+40h], rsi
0x1803d610f  lea     r8, [rdi+18h]
0x1803d6113  mov     [r8], rsi
0x1803d6116  mov     rcx, [rdi+188h]; this
0x1803d611d  mov     rax, [rcx]
0x1803d6120  test    rax, rax
0x1803d6123  jz      short loc_1803D612A
0x1803d6125  mov     edx, [rax+4]
0x1803d6128  jmp     short loc_1803D612C
0x1803d612a  mov     edx, esi
0x1803d612c  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1803d6131  mov     rcx, rax
0x1803d6134  call    cs:__imp_MsgStringCreateShared
0x1803d613a  lea     rcx, [rdi+48h]
0x1803d613e  mov     r8, rbx
0x1803d6141  mov     edx, eax
0x1803d6143  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1803d6148  mov     [rdi+50h], esi
0x1803d614b  mov     [rdi+58h], rsi
0x1803d614f  mov     [rdi+60h], rsi
0x1803d6153  mov     r15, [r12]
0x1803d6157  test    r15, r15
0x1803d615a  jz      short loc_1803D6188
0x1803d615c  mov     [rsp+0B8h+arg_8], r15
0x1803d6164  lea     rbx, [rdi+150h]
0x1803d616b  mov     rcx, rbx; this
0x1803d616e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1803d6173  mov     rcx, r15
0x1803d6176  call    cs:__imp_MsgRelease
0x1803d617c  mov     rcx, rbx; this
0x1803d617f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1803d6184  lea     rbx, [rdi+30h]
0x1803d6188  mov     [r12], rsi
0x1803d618c  mov     rcx, [rbx+160h]; this
0x1803d6193  mov     rax, [rcx]
0x1803d6196  test    rax, rax
0x1803d6199  jz      short loc_1803D61A0
0x1803d619b  mov     edx, [rax+4]
0x1803d619e  jmp     short loc_1803D61A2
0x1803d61a0  mov     edx, esi
0x1803d61a2  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1803d61a7  mov     r8, r12
0x1803d61aa  mov     rcx, rax
0x1803d61ad  call    cs:__imp_MsgStringCreateShared
0x1803d61b3  lea     rcx, [rdi+68h]
0x1803d61b7  lea     r8, [rdi+50h]
0x1803d61bb  mov     edx, eax
0x1803d61bd  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1803d61c2  mov     [rdi+70h], esi
0x1803d61c5  mov     [rdi+78h], rsi
0x1803d61c9  mov     [rdi+80h], rsi
0x1803d61d0  mov     rcx, [r13+28h]
0x1803d61d4  lea     rdx, [rdi+110h]
0x1803d61db  movups  xmm0, xmmword ptr [rdi+170h]
0x1803d61e2  movdqu  xmmword ptr [rdx], xmm0
0x1803d61e6  mov     rax, [rcx]
0x1803d61e9  xor     r8d, r8d
0x1803d61ec  mov     rax, [rax+58h]
0x1803d61f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803d61f5  lea     rcx, [rdi+88h]
0x1803d61fc  lea     r8, [rdi+70h]
0x1803d6200  mov     edx, eax
0x1803d6202  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1803d6207  lea     rbx, [rdi+90h]
0x1803d620e  mov     [rbx], esi
0x1803d6210  mov     [rdi+98h], rsi
0x1803d6217  mov     [rdi+0A0h], rsi
0x1803d621e  mov     r11, [r13+28h]
0x1803d6222  mov     rax, [r11]
0x1803d6225  mov     r10, [r12]
0x1803d6229  mov     [rsp+0B8h+arg_8], r10
0x1803d6231  mov     rcx, [rdi+18h]
0x1803d6235  mov     [rsp+0B8h+var_70], rcx
0x1803d623a  lea     rdx, [rdi+120h]
0x1803d6241  movups  xmm0, xmmword ptr [rdi+170h]
0x1803d6248  movdqu  xmmword ptr [rdx], xmm0
0x1803d624c  mov     [rsp+0B8h+var_88], esi
0x1803d6250  mov     [rsp+0B8h+var_90], r10
0x1803d6255  mov     [rsp+0B8h+var_98], rcx
0x1803d625a  mov     r9d, [r12+160h]
0x1803d6262  xor     r8d, r8d
0x1803d6265  mov     rcx, r11
0x1803d6268  mov     rax, [rax+48h]
0x1803d626c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803d6271  lea     rcx, [rdi+0A8h]
0x1803d6278  mov     r8, rbx
0x1803d627b  mov     edx, eax
0x1803d627d  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1803d6282  inc     dword ptr [r13+88h]
0x1803d6289  mov     r15d, [r13+88h]
0x1803d6290  mov     dword ptr [rsp+0B8h+var_98], r15d
0x1803d6295  lea     r9, aDictationinput_10; "DictationInputProcessor::ExecuteBufferC"...
0x1803d629c  mov     r8d, 36Eh; unsigned int
0x1803d62a2  lea     rdx, aWinrtWindowsud_3; "winrt::WindowsUdk::UI::Input::Text::imp"...
0x1803d62a9  lea     rcx, aShellcommonUnd_153; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1803d62b0  call    ?ZTraceAsWil@@YAXPEBD0IPEA_WZZ; ZTraceAsWil(char const *,char const *,uint,wchar_t *,...)
0x1803d62b5  lea     rbx, [rdi+0B0h]
0x1803d62bc  mov     [rbx], esi
0x1803d62be  mov     [rdi+0B8h], rsi
0x1803d62c5  mov     [rdi+0C0h], rsi
0x1803d62cc  mov     rcx, [r13+28h]
0x1803d62d0  lea     rdx, [rdi+130h]
0x1803d62d7  movups  xmm0, xmmword ptr [rdi+170h]
0x1803d62de  movdqu  xmmword ptr [rdx], xmm0
0x1803d62e2  mov     rax, [rcx]
0x1803d62e5  mov     r8d, r15d
0x1803d62e8  mov     rax, [rax+60h]
0x1803d62ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803d62f1  lea     rcx, [rdi+0C8h]
0x1803d62f8  mov     r8, rbx
0x1803d62fb  mov     edx, eax
0x1803d62fd  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1803d6302  lea     rbx, [rdi-70h]
0x1803d6306  mov     [rdi+140h], rbx
0x1803d630d  lea     rdx, [rdi+0D8h]
0x1803d6314  mov     r8d, r15d
0x1803d6317  mov     rcx, r13
0x1803d631a  call    ?GetActionAsync@DictationInputProcessor@implementation@Text@Input@UI@WindowsUdk@winrt@@QEAA?AUIAsyncAction@Foundation@Windows@7@H@Z; winrt::WindowsUdk::UI::Input::Text::implementation::DictationInputProcessor::GetActionAsync(int)
0x1803d631f  nop
0x1803d6320  mov     rdx, rax
0x1803d6323  mov     rcx, rbx
0x1803d6326  call    ??$await_transform@U?$IAsyncOperation@UPredictor@PredictionUnit@Internal@Windows@winrt@@@Foundation@Windows@winrt@@@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UWisePredictor@MachineLearning@AI@WindowsUdk@winrt@@@Foundation@Windows@winrt@@Uhstring@4@U54@@experimental@std@@U?$IAsyncOperation@UWisePredictor@MachineLearning@AI@WindowsUdk@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEAA$$QEAU?$IAsyncOperation@UPredictor@PredictionUnit@Internal@Windows@winrt@@@Foundation@Windows@2@$$QEAU3452@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::AI::MachineLearning::WisePredictor>,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::AI::MachineLearning::WisePredictor>,void>::await_transform<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::PredictionUnit::Predictor>>(winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::PredictionUnit::Predictor> &&)
0x1803d632b  lea     rcx, [rdi+0E0h]
0x1803d6332  mov     rdx, rax
0x1803d6335  call    ??$?__LUhstring@winrt@@@Foundation@Windows@winrt@@YA?AU?$await_adapter@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@$00@impl@2@AEBU?$IAsyncOperation@Uhstring@winrt@@@012@@Z; winrt::Windows::Foundation::operator co_await<winrt::hstring>(winrt::Windows::Foundation::IAsyncOperation<winrt::hstring> const &)
0x1803d633a  mov     [rdi+0D0h], rax
0x1803d6341  mov     ecx, 4
0x1803d6346  mov     [r14], cx
0x1803d634a  mov     rdx, rdi
0x1803d634d  mov     rcx, rax
0x1803d6350  call    ??$await_suspend@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUDictatedTextInputSession@implementation@Text@Input@UI@WindowsUdk@4@H@experimental@std@@@?$await_adapter@UIAsyncAction@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUDictatedTextInputSession@implementation@Text@Input@UI@WindowsUdk@4@H@experimental@std@@@experimental@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::WindowsUdk::UI::Input::Text::implementation::DictatedTextInputSession *,int>::promise_type>(std::experimental::coroutine_handle<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::WindowsUdk::UI::Input::Text::implementation::DictatedTextInputSession *,int>::promise_type>)
0x1803d6355  test    al, al
0x1803d6357  jz      short loc_1803D63B9
0x1803d6359  jmp     loc_1803D6474
0x1803d635e  lea     rcx, [rdi+0E0h]; jumptable 00000001803D60D6 case 5
0x1803d6365  call    ??1?$cancellable_awaiter@U?$await_adapter@U?$IAsyncOperation@I@Foundation@Windows@winrt@@$00@impl@winrt@@@winrt@@QEAA@XZ; winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<uint>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<uint>,1>>(void)
0x1803d636a  nop
0x1803d636b  lea     rcx, [rdi+0D8h]; this
0x1803d6372  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1803d6377  nop
0x1803d6378  lea     rcx, [rdi+28h]
0x1803d637c  call    ??1?$unique_storage@U?$resource_policy@PEAUMsgString@@P6AXPEAUMsgBuffer@@@Z$1?MsgRelease@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(void)
0x1803d6381  nop
0x1803d6382  lea     rcx, [rdi+20h]
0x1803d6386  call    ??1?$unique_storage@U?$resource_policy@PEAUMsgString@@P6AXPEAUMsgBuffer@@@Z$1?MsgRelease@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(void)
0x1803d638b  nop
0x1803d638c  lea     rcx, [rdi+18h]
0x1803d6390  call    ??1?$unique_storage@U?$resource_policy@PEAUMsgString@@P6AXPEAUMsgBuffer@@@Z$1?MsgRelease@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(void)
0x1803d6395  nop
0x1803d6396  lea     rcx, [rdi+10h]
0x1803d639a  mov     rax, [rcx]
0x1803d639d  mov     [rsp+0B8h+arg_10], rax
0x1803d63a5  xor     esi, esi
0x1803d63a7  test    rax, rax
0x1803d63aa  jz      short loc_1803D63B2
0x1803d63ac  call    ?unconditional_release_ref@?$com_ptr@USpeechCorrectionCandidateWindowClient@implementation@Text@Input@UI@WindowsUdk@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::WindowsUdk::UI::Input::Text::implementation::SpeechCorrectionCandidateWindowClient>::unconditional_release_ref(void)
0x1803d63b1  nop
0x1803d63b2  jmp     loc_1803D6454
0x1803d63b7  xor     esi, esi; jumptable 00000001803D60D6 case 4
0x1803d63b9  mov     rcx, [rdi+0D0h]
0x1803d63c0  call    ?await_resume@?$await_adapter@UIAsyncAction@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_resume(void)
0x1803d63c5  nop
0x1803d63c6  lea     rcx, [rdi+0E0h]
0x1803d63cd  call    ??1?$cancellable_awaiter@U?$await_adapter@U?$IAsyncOperation@I@Foundation@Windows@winrt@@$00@impl@winrt@@@winrt@@QEAA@XZ; winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<uint>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<uint>,1>>(void)
0x1803d63d2  nop
0x1803d63d3  lea     rcx, [rdi+0D8h]; this
0x1803d63da  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1803d63df  nop
0x1803d63e0  lea     rcx, [rdi+28h]
0x1803d63e4  call    ??1?$unique_storage@U?$resource_policy@PEAUMsgString@@P6AXPEAUMsgBuffer@@@Z$1?MsgRelease@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(void)
0x1803d63e9  nop
0x1803d63ea  lea     rcx, [rdi+20h]
0x1803d63ee  call    ??1?$unique_storage@U?$resource_policy@PEAUMsgString@@P6AXPEAUMsgBuffer@@@Z$1?MsgRelease@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(void)
0x1803d63f3  nop
0x1803d63f4  lea     rcx, [rdi+18h]
0x1803d63f8  call    ??1?$unique_storage@U?$resource_policy@PEAUMsgString@@P6AXPEAUMsgBuffer@@@Z$1?MsgRelease@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgString *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgString *,MsgString *,0,std::nullptr_t>>(void)
0x1803d63fd  nop
0x1803d63fe  lea     rcx, [rdi+10h]
0x1803d6402  mov     rax, [rcx]
0x1803d6405  mov     [rsp+0B8h+arg_10], rax
0x1803d640d  test    rax, rax
0x1803d6410  jz      short loc_1803D6418
0x1803d6412  call    ?unconditional_release_ref@?$com_ptr@USpeechCorrectionCandidateWindowClient@implementation@Text@Input@UI@WindowsUdk@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::WindowsUdk::UI::Input::Text::implementation::SpeechCorrectionCandidateWindowClient>::unconditional_release_ref(void)
0x1803d6417  nop
0x1803d6418  mov     rax, [rdi+140h]
0x1803d641f  jmp     short loc_1803D6437
0x1803d6421  mov     rdi, [rsp+0B8h+arg_0]
0x1803d6429  lea     rax, [rdi-70h]
0x1803d642d  xor     esi, esi
0x1803d642f  mov     r14, [rsp+0B8h+arg_18]
0x1803d6437  lea     rcx, [rdi+100h]
0x1803d643e  mov     [rcx], rax
0x1803d6441  xor     eax, eax
0x1803d6443  mov     [r14], ax
0x1803d6447  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@U?$IVectorView@UMenuItem@UI@WindowsUdk@winrt@@@Collections@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@UIStorageItem@Storage@34@UUser@System@34@UMenuItemGetOptions@UI@WindowsUdk@4@@experimental@std@@U?$IAsyncOperation@U?$IVectorView@UMenuItem@UI@WindowsUdk@winrt@@@Collections@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@experimental@std@@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::WindowsUdk::UI::MenuItem>>,winrt::Windows::Storage::IStorageItem,winrt::Windows::System::User,winrt::WindowsUdk::UI::MenuItemGetOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::WindowsUdk::UI::MenuItem>>,void>::final_suspend_awaiter::await_suspend(std::experimental::coroutine_handle<void>)
0x1803d644c  test    al, al
0x1803d644e  jz      short loc_1803D6454
0x1803d6450  jmp     short loc_1803D6474
0x1803d6452  xor     esi, esi; jumptable 00000001803D60D6 cases -1,1
0x1803d6454  lea     rcx, [rdi-70h]
0x1803d6458  call    ??1?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@USoftwareBitmap@Imaging@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUInputMethodConversionIndicator@implementation@Text@Input@UI@WindowsUdk@4@@experimental@std@@U?$IAsyncOperation@USoftwareBitmap@Imaging@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@UEAA@XZ; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::WindowsUdk::UI::Input::Text::implementation::InputMethodConversionIndicator *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,void>::~promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::WindowsUdk::UI::Input::Text::implementation::InputMethodConversionIndicator *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,void>(void)
0x1803d645d  cmp     [rdi+0Ah], si
0x1803d6461  jz      short loc_1803D6474
0x1803d6463  mov     edx, 210h; struct std::nothrow_t *
0x1803d6468  lea     rcx, [rdi-70h]; void *
0x1803d646c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1803d6471  jmp     short loc_1803D6474
0x1803d6473  int     3; Trap to Debugger
0x1803d6474  add     rsp, 80h
0x1803d647b  pop     r15
0x1803d647d  pop     r14
0x1803d647f  pop     r13
0x1803d6481  pop     r12
0x1803d6483  pop     rdi
0x1803d6484  pop     rsi
0x1803d6485  pop     rbx
0x1803d6486  retn
```
