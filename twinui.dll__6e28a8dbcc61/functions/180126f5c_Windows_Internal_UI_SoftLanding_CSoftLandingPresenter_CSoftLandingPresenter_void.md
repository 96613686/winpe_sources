# Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::~CSoftLandingPresenter(void)

- ea: `0x180126f5c`
- end: `0x1801270cc`
- name: `??1CSoftLandingPresenter@SoftLanding@UI@Internal@Windows@@UEAA@XZ`
- size: `368`
- prototype: `void(Windows::Internal::UI::SoftLanding::CSoftLandingPresenter *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1803279b0`

## callees

- `0x180008acc`
- `0x18003c898`
- `0x180047420`
- `0x180126f5c`
- `0x1801270d4`
- `0x180127220`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180127021`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180127033`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180127045`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180127057`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180127069`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012707b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012708d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012709f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801270b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180127021`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180127033`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180127045`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180127057`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180127069`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012707b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012708d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012709f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801270b1`

## pseudocode

```c
void __fastcall Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::~CSoftLandingPresenter(
        Windows::Internal::UI::SoftLanding::CSoftLandingPresenter *this)
{
  int v2; // eax
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = &Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::`vftable';
  *((_QWORD *)this + 1) = &Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::`vftable'{for `IUIAutomationStructureChangedEventHandler'};
  *((_QWORD *)this + 2) = &Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,IInspectable *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastDismissedEventArgs *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastFailedEventArgs *>>'};
  *((_QWORD *)this + 3) = &Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastDismissedEventArgs *>'};
  *((_QWORD *)this + 4) = &Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastFailedEventArgs *>>'};
  v2 = Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::_CleanupNotification(this);
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1D3,
      (unsigned int)"shell\\twinui\\softlanding\\lib\\softlandingpresenter.cpp",
      (const char *)(unsigned int)v2,
      v3);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 376);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 344);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 336);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 328);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 312);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 272);
  Windows::Internal::UI::SoftLanding::CSoftLandingNotification::~CSoftLandingNotification((Windows::Internal::UI::SoftLanding::CSoftLandingPresenter *)((char *)this + 208));
  Windows::Internal::UI::SoftLanding::CSoftLandingNotification::~CSoftLandingNotification((Windows::Internal::UI::SoftLanding::CSoftLandingPresenter *)((char *)this + 152));
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
0x180126f5c  push    rbx; int
0x180126f5e  sub     rsp, 20h
0x180126f62  mov     rbx, rcx
0x180126f65  lea     rax, ??_7CSoftLandingPresenter@SoftLanding@UI@Internal@Windows@@6B@; const Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::`vftable'
0x180126f6c  mov     [rcx], rax
0x180126f6f  lea     rax, ??_7CSoftLandingPresenter@SoftLanding@UI@Internal@Windows@@6BIUIAutomationStructureChangedEventHandler@@@; const Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::`vftable'{for `IUIAutomationStructureChangedEventHandler'}
0x180126f76  mov     [rcx+8], rax
0x180126f7a  lea     rax, ??_7CSoftLandingPresenter@SoftLanding@UI@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAVToastDismissedEventArgs@234@@56@U?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAVToastFailedEventArgs@234@@56@@Details@WRL@Microsoft@@@; const Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,IInspectable *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastDismissedEventArgs *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastFailedEventArgs *>>'}
0x180126f81  mov     [rcx+10h], rax
0x180126f85  lea     rax, ??_7CSoftLandingPresenter@SoftLanding@UI@Internal@Windows@@6B?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAVToastDismissedEventArgs@234@@Foundation@4@@; const Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastDismissedEventArgs *>'}
0x180126f8c  mov     [rcx+18h], rax
0x180126f90  lea     rax, ??_7CSoftLandingPresenter@SoftLanding@UI@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAVToastFailedEventArgs@234@@Foundation@Windows@@@Details@WRL@Microsoft@@@; const Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastFailedEventArgs *>>'}
0x180126f97  mov     [rcx+20h], rax
0x180126f9b  call    ?_CleanupNotification@CSoftLandingPresenter@SoftLanding@UI@Internal@Windows@@AEAAJXZ; Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::_CleanupNotification(void)
0x180126fa0  test    eax, eax
0x180126fa2  jns     short loc_180126FBD
0x180126fa4  mov     rcx, [rsp+28h]; this
0x180126fa9  mov     r9d, eax; char *
0x180126fac  lea     r8, aShellTwinuiSof_3; "shell\\twinui\\softlanding\\lib\\softla"...
0x180126fb3  mov     edx, 1D3h; void *
0x180126fb8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180126fbd  lea     rcx, [rbx+178h]
0x180126fc4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180126fc9  lea     rcx, [rbx+158h]
0x180126fd0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180126fd5  lea     rcx, [rbx+150h]
0x180126fdc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180126fe1  lea     rcx, [rbx+148h]
0x180126fe8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180126fed  lea     rcx, [rbx+138h]
0x180126ff4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180126ff9  lea     rcx, [rbx+110h]
0x180127000  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180127005  lea     rcx, [rbx+0D0h]; this
0x18012700c  call    ??1CSoftLandingNotification@SoftLanding@UI@Internal@Windows@@QEAA@XZ; Windows::Internal::UI::SoftLanding::CSoftLandingNotification::~CSoftLandingNotification(void)
0x180127011  lea     rcx, [rbx+98h]; this
0x180127018  call    ??1CSoftLandingNotification@SoftLanding@UI@Internal@Windows@@QEAA@XZ; Windows::Internal::UI::SoftLanding::CSoftLandingNotification::~CSoftLandingNotification(void)
0x18012701d  mov     rcx, [rbx+70h]; string
0x180127021  call    cs:__imp_WindowsDeleteString
0x180127027  mov     qword ptr [rbx+70h], 0
0x18012702f  mov     rcx, [rbx+68h]; string
0x180127033  call    cs:__imp_WindowsDeleteString
0x180127039  mov     qword ptr [rbx+68h], 0
0x180127041  mov     rcx, [rbx+60h]; string
0x180127045  call    cs:__imp_WindowsDeleteString
0x18012704b  mov     qword ptr [rbx+60h], 0
0x180127053  mov     rcx, [rbx+58h]; string
0x180127057  call    cs:__imp_WindowsDeleteString
0x18012705d  mov     qword ptr [rbx+58h], 0
0x180127065  mov     rcx, [rbx+50h]; string
0x180127069  call    cs:__imp_WindowsDeleteString
0x18012706f  mov     qword ptr [rbx+50h], 0
0x180127077  mov     rcx, [rbx+48h]; string
0x18012707b  call    cs:__imp_WindowsDeleteString
0x180127081  mov     qword ptr [rbx+48h], 0
0x180127089  mov     rcx, [rbx+40h]; string
0x18012708d  call    cs:__imp_WindowsDeleteString
0x180127093  mov     qword ptr [rbx+40h], 0
0x18012709b  mov     rcx, [rbx+38h]; string
0x18012709f  call    cs:__imp_WindowsDeleteString
0x1801270a5  mov     qword ptr [rbx+38h], 0
0x1801270ad  mov     rcx, [rbx+30h]; string
0x1801270b1  call    cs:__imp_WindowsDeleteString
0x1801270b7  mov     qword ptr [rbx+30h], 0
0x1801270bf  mov     dword ptr [rbx+2Ch], 0C0000001h
0x1801270c6  add     rsp, 20h
0x1801270ca  pop     rbx
0x1801270cb  retn
```
