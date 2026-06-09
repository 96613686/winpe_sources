# Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback::ActivateHelper(ushort const *,ushort const *,NOTIFICATION_USER_INPUT_DATA const *,ulong)

- ea: `0x180132fa4`
- end: `0x1801331e8`
- name: `?ActivateHelper@WindowsTipNotificationActivationCallback@WindowsTip@UI@Internal@Windows@@AEAAJPEBG0PEBUNOTIFICATION_USER_INPUT_DATA@@K@Z`
- size: `580`
- prototype: `int(Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const struct NOTIFICATION_USER_INPUT_DATA *, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x180132f70`

## callees

- `0x18002cd80`
- `0x180031970`
- `0x18003c5e4`
- `0x1800f4224`
- `0x180103638`
- `0x180132fa4`
- `0x18013d330`
- `0x18021bfe4`
- `0x180307c4c`
- `0x180308384`
- `0x180308560`
- `0x1803086bc`
- `0x180308be0`
- `0x180308d7c`
- `0x180317e94`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180133036`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180133046`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180133090`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180133197`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801331a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801331b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180133036`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180133046`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180133090`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180133197`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801331a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801331b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801330d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801330d7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x180132fdf`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x180132fdf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback::ActivateHelper(
        Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct NOTIFICATION_USER_INPUT_DATA *a4)
{
  Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback *v7; // rcx
  int ContentIdAndPath; // eax
  int v9; // ebx
  Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback *v10; // rcx
  int CreativeId; // eax
  const unsigned __int16 *StringRawBuffer; // rbx
  volatile int *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rcx
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+20h] [rbp-E0h]
  HSTRING v18; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  char v20; // [rsp+40h] [rbp-C0h]
  HSTRING v21; // [rsp+48h] [rbp-B8h] BYREF
  char v22; // [rsp+50h] [rbp-B0h]
  Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback *v23; // [rsp+58h] [rbp-A8h] BYREF
  int v24[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v25[384]; // [rsp+1B0h] [rbp+B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  if ( StrCmpIW(a2, L"Windows.SystemToast.WindowsTip") || !a3 || !*a3 )
    return 2147942487LL;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SoftLandingV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SoftLandingV2>::GetImpl'::`2'::impl) )
  {
    Windows::Internal::UI::WindowsTip::SoftLandingV2Helper::ProcessActivationAsync(a3);
    return 0;
  }
  else
  {
    v20 = 0;
    v22 = 0;
    WindowsDeleteString(0);
    v21 = 0;
    WindowsDeleteString(0);
    string = 0;
    ContentIdAndPath = Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback::GetContentIdAndPath(
                         v7,
                         a3,
                         &string,
                         &v21);
    v9 = ContentIdAndPath;
    if ( ContentIdAndPath >= 0 )
    {
      WindowsDeleteString(0);
      v18 = 0;
      CreativeId = Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback::GetCreativeId(
                     v10,
                     string,
                     &v18);
      v9 = CreativeId;
      if ( CreativeId >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(v18, 0);
        wil::ActivityBase<SoftLandingLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SoftLandingLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v24);
        *(_QWORD *)v24 = &SoftLandingTelemetry::NotificationInvoke::`vftable';
        SoftLandingTelemetry::NotificationInvoke::StartActivity(
          (SoftLandingTelemetry::NotificationInvoke *)v24,
          StringRawBuffer,
          1);
        v23 = this;
        if ( this )
          Microsoft::WRL::Details::SafeUnknownIncrementReference(
            (Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback *)((char *)this + 12),
            v13);
        v14 = _lambda_6852bcebcf55780741477f5ab9ed6c4e_::_lambda_6852bcebcf55780741477f5ab9ed6c4e_(
                (unsigned int)v25,
                (unsigned int)&string,
                (unsigned int)&v21,
                (unsigned int)&v23,
                (__int64)v24);
        v9 = Windows::Internal::ComTaskPool::QueueTask<_lambda_6852bcebcf55780741477f5ab9ed6c4e_>(v15, v14);
        _lambda_6852bcebcf55780741477f5ab9ed6c4e_::~_lambda_6852bcebcf55780741477f5ab9ed6c4e_((_lambda_6852bcebcf55780741477f5ab9ed6c4e_ *)v25);
        if ( v9 < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7D,
            (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstipnotificationactivationcallback.cpp",
            (const char *)(unsigned int)v9,
            v17);
        if ( this )
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDuiBehaviorFactory>::Release(this);
        SoftLandingTelemetry::NotificationInvoke::~NotificationInvoke((SoftLandingTelemetry::NotificationInvoke *)v24);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x71,
          (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstipnotificationactivationcallback.cpp",
          (const char *)(unsigned int)CreativeId,
          v16);
      }
      WindowsDeleteString(v18);
      v18 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstipnotificationactivationcallback.cpp",
        (const char *)(unsigned int)ContentIdAndPath,
        v16);
    }
    WindowsDeleteString(v21);
    v21 = 0;
    WindowsDeleteString(string);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x180132fa4  mov     [rsp-8+arg_18], rbx
0x180132fa9  push    rbp
0x180132faa  push    rsi
0x180132fab  push    rdi
0x180132fac  lea     rbp, [rsp-240h]
0x180132fb4  sub     rsp, 340h
0x180132fbb  mov     rax, cs:__security_cookie
0x180132fc2  xor     rax, rsp
0x180132fc5  mov     [rbp+250h+var_20], rax
0x180132fcc  mov     rbx, r8
0x180132fcf  mov     rax, rdx
0x180132fd2  mov     rdi, rcx
0x180132fd5  lea     rdx, ?c_windowsTipAppIdentity@Shared@CreativeFramework@@3QBGB; "Windows.SystemToast.WindowsTip"
0x180132fdc  mov     rcx, rax; psz1
0x180132fdf  call    cs:__imp_StrCmpIW
0x180132fe5  xor     esi, esi
0x180132fe7  test    eax, eax
0x180132fe9  jnz     loc_1801331C1
0x180132fef  test    rbx, rbx
0x180132ff2  jz      loc_1801331C1
0x180132ff8  cmp     [rbx], si
0x180132ffb  jz      loc_1801331C1
0x180133001  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SoftLandingV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SoftLandingV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SoftLandingV2> `wil::Feature<__WilFeatureTraits_Feature_SoftLandingV2>::GetImpl(void)'::`2'::impl
0x180133008  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SoftLandingV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SoftLandingV2>::__private_IsEnabled(void)
0x18013300d  test    al, al
0x18013300f  jz      short loc_180133020
0x180133011  mov     rcx, rbx
0x180133014  call    ?ProcessActivationAsync@SoftLandingV2Helper@WindowsTip@UI@Internal@Windows@@SA?AUfire_and_forget@winrt@@PEBG@Z; Windows::Internal::UI::WindowsTip::SoftLandingV2Helper::ProcessActivationAsync(ushort const *)
0x180133019  xor     eax, eax
0x18013301b  jmp     loc_1801331C6
0x180133020  mov     [rsp+350h+string], rsi
0x180133025  mov     [rsp+350h+var_310], sil
0x18013302a  mov     [rsp+350h+var_308], rsi
0x18013302f  mov     [rsp+350h+var_300], sil
0x180133034  xor     ecx, ecx; string
0x180133036  call    cs:__imp_WindowsDeleteString
0x18013303c  mov     [rsp+350h+var_308], rsi
0x180133041  mov     rcx, [rsp+350h+string]; string
0x180133046  call    cs:__imp_WindowsDeleteString
0x18013304c  mov     [rsp+350h+string], rsi
0x180133051  lea     r9, [rsp+350h+var_308]; HSTRING *
0x180133056  lea     r8, [rsp+350h+string]; HSTRING *
0x18013305b  mov     rdx, rbx; unsigned __int16 *
0x18013305e  call    ?GetContentIdAndPath@WindowsTipNotificationActivationCallback@WindowsTip@UI@Internal@Windows@@AEAAJPEBGPEAPEAUHSTRING__@@1@Z; Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback::GetContentIdAndPath(ushort const *,HSTRING__ * *,HSTRING__ * *)
0x180133063  mov     ebx, eax
0x180133065  test    eax, eax
0x180133067  jns     short loc_180133089
0x180133069  mov     rcx, [rbp+258h]; this
0x180133070  mov     r9d, eax; char *
0x180133073  lea     r8, aShellTwinuiSof_1; "shell\\twinui\\softlanding\\lib\\window"...
0x18013307a  mov     edx, 6Eh ; 'n'; void *
0x18013307f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180133084  jmp     loc_1801331A2
0x180133089  mov     [rsp+350h+var_320], rsi
0x18013308e  xor     ecx, ecx; string
0x180133090  call    cs:__imp_WindowsDeleteString
0x180133096  mov     [rsp+350h+var_320], rsi
0x18013309b  lea     r8, [rsp+350h+var_320]; HSTRING *
0x1801330a0  mov     rdx, [rsp+350h+string]; HSTRING
0x1801330a5  call    ?GetCreativeId@WindowsTipNotificationActivationCallback@WindowsTip@UI@Internal@Windows@@AEAAJPEAUHSTRING__@@PEAPEAU6@@Z; Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback::GetCreativeId(HSTRING__ *,HSTRING__ * *)
0x1801330aa  mov     ebx, eax
0x1801330ac  test    eax, eax
0x1801330ae  jns     short loc_1801330D0
0x1801330b0  mov     rcx, [rbp+258h]; this
0x1801330b7  mov     r9d, eax; char *
0x1801330ba  lea     r8, aShellTwinuiSof_1; "shell\\twinui\\softlanding\\lib\\window"...
0x1801330c1  mov     edx, 71h ; 'q'; void *
0x1801330c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801330cb  jmp     loc_180133192
0x1801330d0  xor     edx, edx; length
0x1801330d2  mov     rcx, [rsp+350h+var_320]; string
0x1801330d7  call    cs:__imp_WindowsGetStringRawBuffer
0x1801330dd  mov     rbx, rax
0x1801330e0  lea     rdx, aNotificationin; "NotificationInvoke"
0x1801330e7  lea     rcx, [rsp+350h+var_2F0]; struct wil::details::IFailureCallback *
0x1801330ec  call    ??0?$ActivityBase@VSoftLandingLogging@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SoftLandingLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SoftLandingLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1801330f1  lea     rax, ??_7NotificationInvoke@SoftLandingTelemetry@@6B@; const SoftLandingTelemetry::NotificationInvoke::`vftable'
0x1801330f8  mov     qword ptr [rsp+350h+var_2F0], rax
0x1801330fd  mov     r8b, 1; bool
0x180133100  mov     rdx, rbx; unsigned __int16 *
0x180133103  lea     rcx, [rsp+350h+var_2F0]; this
0x180133108  call    ?StartActivity@NotificationInvoke@SoftLandingTelemetry@@QEAAXPEBG_N@Z; SoftLandingTelemetry::NotificationInvoke::StartActivity(ushort const *,bool)
0x18013310d  nop
0x18013310e  mov     [rsp+350h+var_2F8], rdi
0x180133113  test    rdi, rdi
0x180133116  jz      short loc_180133121
0x180133118  lea     rcx, [rdi+0Ch]; this
0x18013311c  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x180133121  lea     rax, [rsp+350h+var_2F0]
0x180133126  mov     qword ptr [rsp+350h+var_330], rax; int
0x18013312b  lea     r9, [rsp+350h+var_2F8]
0x180133130  lea     r8, [rsp+350h+var_308]
0x180133135  lea     rdx, [rsp+350h+string]
0x18013313a  lea     rcx, [rbp+250h+var_1A0]
0x180133141  call    ??0_lambda_6852bcebcf55780741477f5ab9ed6c4e_@@QEAA@AEBV?$MoveOnCopy@VHString@Wrappers@WRL@Microsoft@@@Internal@Windows@@0AEBV?$ComPtr@VWindowsTipNotificationActivationCallback@WindowsTip@UI@Internal@Windows@@@WRL@Microsoft@@AEBVNotificationInvoke@SoftLandingTelemetry@@@Z; _lambda_6852bcebcf55780741477f5ab9ed6c4e_::_lambda_6852bcebcf55780741477f5ab9ed6c4e_(Windows::Internal::MoveOnCopy<Microsoft::WRL::Wrappers::HString> const &,Windows::Internal::MoveOnCopy<Microsoft::WRL::Wrappers::HString> const &,Microsoft::WRL::ComPtr<Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback> const &,SoftLandingTelemetry::NotificationInvoke const &)
0x180133146  mov     rdx, rax
0x180133149  call    ??$QueueTask@V_lambda_6852bcebcf55780741477f5ab9ed6c4e_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@$$QEAV_lambda_6852bcebcf55780741477f5ab9ed6c4e_@@@Z; Windows::Internal::ComTaskPool::QueueTask<_lambda_6852bcebcf55780741477f5ab9ed6c4e_>(Windows::Internal::TaskApartment,_lambda_6852bcebcf55780741477f5ab9ed6c4e_ &&)
0x18013314e  mov     ebx, eax
0x180133150  lea     rcx, [rbp+250h+var_1A0]; this
0x180133157  call    ??1_lambda_6852bcebcf55780741477f5ab9ed6c4e_@@QEAA@XZ; _lambda_6852bcebcf55780741477f5ab9ed6c4e_::~_lambda_6852bcebcf55780741477f5ab9ed6c4e_(void)
0x18013315c  test    ebx, ebx
0x18013315e  jns     short loc_18013317B
0x180133160  mov     rcx, [rbp+258h]; this
0x180133167  mov     r9d, ebx; char *
0x18013316a  lea     r8, aShellTwinuiSof_1; "shell\\twinui\\softlanding\\lib\\window"...
0x180133171  mov     edx, 7Dh ; '}'; void *
0x180133176  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013317b  test    rdi, rdi
0x18013317e  jz      short loc_180133188
0x180133180  mov     rcx, rdi
0x180133183  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDuiBehaviorFactory@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDuiBehaviorFactory>::Release(void)
0x180133188  lea     rcx, [rsp+350h+var_2F0]; this
0x18013318d  call    ??1NotificationInvoke@SoftLandingTelemetry@@QEAA@XZ; SoftLandingTelemetry::NotificationInvoke::~NotificationInvoke(void)
0x180133192  mov     rcx, [rsp+350h+var_320]; string
0x180133197  call    cs:__imp_WindowsDeleteString
0x18013319d  mov     [rsp+350h+var_320], rsi
0x1801331a2  mov     rcx, [rsp+350h+var_308]; string
0x1801331a7  call    cs:__imp_WindowsDeleteString
0x1801331ad  mov     [rsp+350h+var_308], rsi
0x1801331b2  mov     rcx, [rsp+350h+string]; string
0x1801331b7  call    cs:__imp_WindowsDeleteString
0x1801331bd  mov     eax, ebx
0x1801331bf  jmp     short loc_1801331C6
0x1801331c1  mov     eax, 80070057h
0x1801331c6  mov     rcx, [rbp+250h+var_20]
0x1801331cd  xor     rcx, rsp; StackCookie
0x1801331d0  call    __security_check_cookie
0x1801331d5  mov     rbx, [rsp+350h+arg_18]
0x1801331dd  add     rsp, 340h
0x1801331e4  pop     rdi
0x1801331e5  pop     rsi
0x1801331e6  pop     rbp
0x1801331e7  retn
```
