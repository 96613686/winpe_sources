# Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::~CWindowsTipPresenter(void)

- ea: `0x18031c208`
- end: `0x18031c405`
- name: `??1CWindowsTipPresenter@WindowsTip@UI@Internal@Windows@@UEAA@XZ`
- size: `509`
- prototype: `void(Windows::Internal::UI::WindowsTip::CWindowsTipPresenter *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a8e20`

## callees

- `0x180008acc`
- `0x18003c898`
- `0x180047420`
- `0x1800ee5f0`
- `0x1800f7620`
- `0x1802154c4`
- `0x18031c208`
- `0x18031c494`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c2d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c2ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c2fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c312`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c326`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c346`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c35a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c36b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c379`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c387`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c395`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c3a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c3b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c3bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c3cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c3db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c3e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c2d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c2ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c2fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c312`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c326`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c346`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c35a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c36b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c379`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c387`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c395`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c3a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c3b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c3bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c3cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c3db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031c3e9`

## pseudocode

```c
void __fastcall Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::~CWindowsTipPresenter(
        Windows::Internal::UI::WindowsTip::CWindowsTipPresenter *this)
{
  int v2; // eax
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = &Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::`vftable';
  *((_QWORD *)this + 1) = &Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::`vftable'{for `IUIAutomationStructureChangedEventHandler'};
  *((_QWORD *)this + 2) = &Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,IInspectable *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastDismissedEventArgs *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastFailedEventArgs *>>'};
  *((_QWORD *)this + 3) = &Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastDismissedEventArgs *>'};
  *((_QWORD *)this + 4) = &Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastFailedEventArgs *>>'};
  v2 = Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::CleanupNotification(this);
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x316,
      (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
      (const char *)(unsigned int)v2,
      v3);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 504);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 472);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 464);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 456);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 440);
  Windows::Internal::UI::WindowsTip::CreativeVisualDataForGuidedTours::~CreativeVisualDataForGuidedTours((Windows::Internal::UI::WindowsTip::CWindowsTipPresenter *)((char *)this + 320));
  Windows::Internal::UI::WindowsTip::CreativeMetadata::~CreativeMetadata((Windows::Internal::UI::WindowsTip::CWindowsTipPresenter *)((char *)this + 296));
  Windows::Internal::UI::WindowsTip::CWindowsTipNotification::~CWindowsTipNotification((Windows::Internal::UI::WindowsTip::CWindowsTipPresenter *)((char *)this + 240));
  WindowsDeleteString(*((HSTRING *)this + 23));
  *((_QWORD *)this + 23) = 0;
  WindowsDeleteString(*((HSTRING *)this + 22));
  *((_QWORD *)this + 22) = 0;
  WindowsDeleteString(*((HSTRING *)this + 21));
  *((_QWORD *)this + 21) = 0;
  WindowsDeleteString(*((HSTRING *)this + 20));
  *((_QWORD *)this + 20) = 0;
  WindowsDeleteString(*((HSTRING *)this + 19));
  *((_QWORD *)this + 19) = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 144);
  WindowsDeleteString(*((HSTRING *)this + 17));
  *((_QWORD *)this + 17) = 0;
  WindowsDeleteString(*((HSTRING *)this + 16));
  *((_QWORD *)this + 16) = 0;
  WindowsDeleteString(*((HSTRING *)this + 15));
  *((_QWORD *)this + 15) = 0;
  WindowsDeleteString(*((HSTRING *)this + 14));
  *((_QWORD *)this + 14) = 0;
  WindowsDeleteString(*((HSTRING *)this + 13));
  *((_QWORD *)this + 13) = 0;
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  WindowsDeleteString(*((HSTRING *)this + 11));
  *((_QWORD *)this + 11) = 0;
  WindowsDeleteString(*((HSTRING *)this + 10));
  *((_QWORD *)this + 10) = 0;
  WindowsDeleteString(*((HSTRING *)this + 9));
  *((_QWORD *)this + 9) = 0;
  WindowsDeleteString(*((HSTRING *)this + 8));
  *((_QWORD *)this + 8) = 0;
  WindowsDeleteString(*((HSTRING *)this + 7));
  *((_QWORD *)this + 7) = 0;
  WindowsDeleteString(*((HSTRING *)this + 6));
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 11) = -1073741823;
}

```

## disassembly

```asm
0x18031c208  mov     [rsp+arg_0], rbx
0x18031c20d  push    rdi; int
0x18031c20e  sub     rsp, 20h
0x18031c212  mov     rbx, rcx
0x18031c215  lea     rax, ??_7CWindowsTipPresenter@WindowsTip@UI@Internal@Windows@@6B@; const Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::`vftable'
0x18031c21c  mov     [rcx], rax
0x18031c21f  lea     rax, ??_7CWindowsTipPresenter@WindowsTip@UI@Internal@Windows@@6BIUIAutomationStructureChangedEventHandler@@@; const Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::`vftable'{for `IUIAutomationStructureChangedEventHandler'}
0x18031c226  mov     [rcx+8], rax
0x18031c22a  lea     rax, ??_7CWindowsTipPresenter@WindowsTip@UI@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAVToastDismissedEventArgs@234@@56@U?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAVToastFailedEventArgs@234@@56@@Details@WRL@Microsoft@@@; const Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,IInspectable *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastDismissedEventArgs *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastFailedEventArgs *>>'}
0x18031c231  mov     [rcx+10h], rax
0x18031c235  lea     rax, ??_7CWindowsTipPresenter@WindowsTip@UI@Internal@Windows@@6B?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAVToastDismissedEventArgs@234@@Foundation@4@@; const Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastDismissedEventArgs *>'}
0x18031c23c  mov     [rcx+18h], rax
0x18031c240  lea     rax, ??_7CWindowsTipPresenter@WindowsTip@UI@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAVToastFailedEventArgs@234@@Foundation@Windows@@@Details@WRL@Microsoft@@@; const Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastFailedEventArgs *>>'}
0x18031c247  mov     [rcx+20h], rax
0x18031c24b  call    ?CleanupNotification@CWindowsTipPresenter@WindowsTip@UI@Internal@Windows@@AEAAJXZ; Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::CleanupNotification(void)
0x18031c250  xor     edi, edi
0x18031c252  test    eax, eax
0x18031c254  jns     short loc_18031C26F
0x18031c256  mov     rcx, [rsp+28h]; this
0x18031c25b  mov     r9d, eax; char *
0x18031c25e  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18031c265  mov     edx, 316h; void *
0x18031c26a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18031c26f  lea     rcx, [rbx+1F8h]
0x18031c276  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18031c27b  lea     rcx, [rbx+1D8h]
0x18031c282  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18031c287  lea     rcx, [rbx+1D0h]
0x18031c28e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18031c293  lea     rcx, [rbx+1C8h]
0x18031c29a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18031c29f  lea     rcx, [rbx+1B8h]
0x18031c2a6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18031c2ab  lea     rcx, [rbx+140h]; this
0x18031c2b2  call    ??1CreativeVisualDataForGuidedTours@WindowsTip@UI@Internal@Windows@@QEAA@XZ; Windows::Internal::UI::WindowsTip::CreativeVisualDataForGuidedTours::~CreativeVisualDataForGuidedTours(void)
0x18031c2b7  lea     rcx, [rbx+128h]; this
0x18031c2be  call    ??1CreativeMetadata@WindowsTip@UI@Internal@Windows@@QEAA@XZ; Windows::Internal::UI::WindowsTip::CreativeMetadata::~CreativeMetadata(void)
0x18031c2c3  lea     rcx, [rbx+0F0h]; this
0x18031c2ca  call    ??1CWindowsTipNotification@WindowsTip@UI@Internal@Windows@@QEAA@XZ; Windows::Internal::UI::WindowsTip::CWindowsTipNotification::~CWindowsTipNotification(void)
0x18031c2cf  mov     rcx, [rbx+0B8h]; string
0x18031c2d6  call    cs:__imp_WindowsDeleteString
0x18031c2dc  mov     [rbx+0B8h], rdi
0x18031c2e3  mov     rcx, [rbx+0B0h]; string
0x18031c2ea  call    cs:__imp_WindowsDeleteString
0x18031c2f0  mov     [rbx+0B0h], rdi
0x18031c2f7  mov     rcx, [rbx+0A8h]; string
0x18031c2fe  call    cs:__imp_WindowsDeleteString
0x18031c304  mov     [rbx+0A8h], rdi
0x18031c30b  mov     rcx, [rbx+0A0h]; string
0x18031c312  call    cs:__imp_WindowsDeleteString
0x18031c318  mov     [rbx+0A0h], rdi
0x18031c31f  mov     rcx, [rbx+98h]; string
0x18031c326  call    cs:__imp_WindowsDeleteString
0x18031c32c  mov     [rbx+98h], rdi
0x18031c333  lea     rcx, [rbx+90h]
0x18031c33a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18031c33f  mov     rcx, [rbx+88h]; string
0x18031c346  call    cs:__imp_WindowsDeleteString
0x18031c34c  mov     [rbx+88h], rdi
0x18031c353  mov     rcx, [rbx+80h]; string
0x18031c35a  call    cs:__imp_WindowsDeleteString
0x18031c360  mov     [rbx+80h], rdi
0x18031c367  mov     rcx, [rbx+78h]; string
0x18031c36b  call    cs:__imp_WindowsDeleteString
0x18031c371  mov     [rbx+78h], rdi
0x18031c375  mov     rcx, [rbx+70h]; string
0x18031c379  call    cs:__imp_WindowsDeleteString
0x18031c37f  mov     [rbx+70h], rdi
0x18031c383  mov     rcx, [rbx+68h]; string
0x18031c387  call    cs:__imp_WindowsDeleteString
0x18031c38d  mov     [rbx+68h], rdi
0x18031c391  mov     rcx, [rbx+60h]; string
0x18031c395  call    cs:__imp_WindowsDeleteString
0x18031c39b  mov     [rbx+60h], rdi
0x18031c39f  mov     rcx, [rbx+58h]; string
0x18031c3a3  call    cs:__imp_WindowsDeleteString
0x18031c3a9  mov     [rbx+58h], rdi
0x18031c3ad  mov     rcx, [rbx+50h]; string
0x18031c3b1  call    cs:__imp_WindowsDeleteString
0x18031c3b7  mov     [rbx+50h], rdi
0x18031c3bb  mov     rcx, [rbx+48h]; string
0x18031c3bf  call    cs:__imp_WindowsDeleteString
0x18031c3c5  mov     [rbx+48h], rdi
0x18031c3c9  mov     rcx, [rbx+40h]; string
0x18031c3cd  call    cs:__imp_WindowsDeleteString
0x18031c3d3  mov     [rbx+40h], rdi
0x18031c3d7  mov     rcx, [rbx+38h]; string
0x18031c3db  call    cs:__imp_WindowsDeleteString
0x18031c3e1  mov     [rbx+38h], rdi
0x18031c3e5  mov     rcx, [rbx+30h]; string
0x18031c3e9  call    cs:__imp_WindowsDeleteString
0x18031c3ef  mov     [rbx+30h], rdi
0x18031c3f3  mov     dword ptr [rbx+2Ch], 0C0000001h
0x18031c3fa  mov     rbx, [rsp+28h+arg_0]
0x18031c3ff  add     rsp, 20h
0x18031c403  pop     rdi
0x18031c404  retn
```
