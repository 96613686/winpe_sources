# ?Run@KeyboardOverriderHook@SystemKeyboardDeliveryInterceptor@implementation@Input@UI@WindowsUdk@winrt@@AEAAXV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@Z

- ea: `0x1800e4584`
- end: `0x1800e4885`
- name: `?Run@KeyboardOverriderHook@SystemKeyboardDeliveryInterceptor@implementation@Input@UI@WindowsUdk@winrt@@AEAAXV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@Z`
- size: `769`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1803cc610`

## callees

- `0x18000aa40`
- `0x18003e770`
- `0x18004f234`
- `0x18004f258`
- `0x18007abb0`
- `0x1800e4584`
- `0x1800e488c`
- `0x1803cc52c`
- `0x1803cc7f0`
- `0x1803cd080`
- `0x18046ba60`
- `0x1804a2010`

## import_xrefs

- `CoreUIComponents!CoreUIFactoryCreate` at `0x1800e45f5`
- `CoreUIComponents!CoreUIFactoryCreate` at `0x1800e45f5`
- `CoreMessaging!CoreUICreate` at `0x1800e45bb`
- `CoreMessaging!CoreUICreate` at `0x1800e45bb`

## string_xrefs

- `0x1800e45d0`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input\systemkeyboarddeliveryinterceptor.cpp`
- `0x1800e460a`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input\systemkeyboarddeliveryinterceptor.cpp`
- `0x1800e463d`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input\systemkeyboarddeliveryinterceptor.cpp`
- `0x1800e468b`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input\systemkeyboarddeliveryinterceptor.cpp`
- `0x1800e4709`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input\systemkeyboarddeliveryinterceptor.cpp`
- `0x1800e475e`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input\systemkeyboarddeliveryinterceptor.cpp`
- `0x1800e47c7`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input\systemkeyboarddeliveryinterceptor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall winrt::WindowsUdk::UI::Input::implementation::SystemKeyboardDeliveryInterceptor::KeyboardOverriderHook::Run(
        unsigned __int64 a1,
        __int64 a2)
{
  __int64 v2; // rdi
  _QWORD *v4; // rsi
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  __int64 v10; // rdx
  int v11; // eax
  wil::details *v12; // rbx
  void *v13; // rdx
  int v14; // eax
  __int128 v15; // kr10_16
  const char *v16; // r9
  int v18; // [rsp+20h] [rbp-78h]
  wil::details *v19; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int64 v20; // [rsp+48h] [rbp-50h] BYREF
  const wchar_t *v21; // [rsp+50h] [rbp-48h] BYREF
  _OWORD v22[4]; // [rsp+58h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  unsigned int v24; // [rsp+A0h] [rbp+8h] BYREF
  __int64 v25; // [rsp+A8h] [rbp+10h]
  __int64 v26; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v27; // [rsp+B8h] [rbp+20h] BYREF

  v25 = a2;
  v2 = a2;
  _SetEvent_scope_exit___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_XZ(
    a2,
    &v19);
  v4 = (_QWORD *)(a1 + 48);
  if ( *(_QWORD *)(a1 + 48) )
    winrt::com_ptr<Windows::Internal::Shell::Experience::ITrayMtcUvcFlyoutExperienceManager>::unconditional_release_ref(a1 + 48);
  v5 = CoreUICreate(a1 + 48);
  try
  {
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1AE,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input\\systemkeyboarddeliveryinterceptor.cpp",
        (const char *)(unsigned int)v5,
        v18);
    v26 = 0;
    v6 = CoreUIFactoryCreate(&v26);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1B1,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input\\systemkeyboarddeliveryinterceptor.cpp",
        (const char *)(unsigned int)v6,
        v18);
    v22[0] = 0;
    v7 = SharedMessagePortRefPtr::Initialize(v22);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1B4,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input\\systemkeyboarddeliveryinterceptor.cpp",
        (const char *)(unsigned int)v7,
        v18);
    v24 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, GUID *, unsigned int *))(*(_QWORD *)v26 + 24LL))(
           v26,
           &GUID_036f83f6_2c8b_4f50_ad5a_833402b2feb4,
           &v24);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1B7,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input\\systemkeyboarddeliveryinterceptor.cpp",
        (const char *)(unsigned int)v8,
        v18);
    v27 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v26 + 32LL))(
           v26,
           (a1 + 8) & ((unsigned __int128)-(__int128)a1 >> 64),
           0,
           v24);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C0,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input\\systemkeyboarddeliveryinterceptor.cpp",
        (const char *)(unsigned int)v9,
        (int)L"System\\RemoteTextInputOverrider");
    v20 = a1;
    v21 = L"System\\LowLevelKeyboardOverriderCallback";
    if ( *(_QWORD *)(a1 + 56) )
      winrt::com_ptr<Windows::Internal::Shell::Experience::ITrayMtcUvcFlyoutExperienceManager>::unconditional_release_ref(a1 + 56);
    v11 = Microsoft::WRL::Details::MakeAndInitialize<MessageProxyReconnectAdapter,MessageProxyReconnectAdapter,_GUID const &,unsigned short const *,winrt::WindowsUdk::UI::Input::implementation::SystemKeyboardDeliveryInterceptor::KeyboardOverriderHook *>(
            a1 + 56,
            v10,
            &v21,
            &v20);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C6,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input\\systemkeyboarddeliveryinterceptor.cpp",
        (const char *)(unsigned int)v11,
        (int)L"System\\RemoteTextInputOverrider");
    *(_BYTE *)(a1 + 72) = 1;
    v12 = v19;
    if ( v19 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v21);
      wil::details::SetEvent(v12, v13);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v21);
    }
    v19 = 0;
    v14 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 232LL))(*v4);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CE,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input\\systemkeyboarddeliveryinterceptor.cpp",
        (const char *)(unsigned int)v14,
        (int)L"System\\RemoteTextInputOverrider");
    if ( v27 )
      winrt::com_ptr<Windows::Internal::Shell::Experience::ITrayMtcUvcFlyoutExperienceManager>::unconditional_release_ref(&v27);
    v15 = v22[0];
    v22[0] = 0u;
    if ( (_QWORD)v15 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v15 + 32LL))(v15);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v15 + 16LL))(v15);
    }
    if ( *((_QWORD *)&v15 + 1) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v15 + 1) + 16LL))(*((_QWORD *)&v15 + 1));
    if ( v26 )
      winrt::com_ptr<Windows::Internal::Shell::Experience::ITrayMtcUvcFlyoutExperienceManager>::unconditional_release_ref(&v26);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1D0,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input\\systemkeyboarddeliveryinterceptor.cpp",
      v16);
    v2 = v25;
  }
  return std::shared_ptr<winrt::WindowsUdk::UI::Input::Text::implementation::UserRegistryReaderWriter>::~shared_ptr<winrt::WindowsUdk::UI::Input::Text::implementation::UserRegistryReaderWriter>(v2);
}

```

## disassembly

```asm
0x1800e4584  mov     [rsp+arg_8], rdx
0x1800e4589  push    rbx
0x1800e458a  push    rsi
0x1800e458b  push    rdi
0x1800e458c  push    r14
0x1800e458e  sub     rsp, 78h
0x1800e4592  mov     rdi, rdx
0x1800e4595  mov     rbx, rcx
0x1800e4598  lea     rdx, [rsp+98h+var_58]
0x1800e459d  mov     rcx, rdi
0x1800e45a0  call    ?SetEvent_scope_exit@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?SetEvent@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@XZ
0x1800e45a5  nop
0x1800e45a6  lea     rsi, [rbx+30h]
0x1800e45aa  cmp     qword ptr [rsi], 0
0x1800e45ae  jz      short loc_1800E45B8
0x1800e45b0  mov     rcx, rsi
0x1800e45b3  call    ?unconditional_release_ref@?$com_ptr@UITrayMtcUvcFlyoutExperienceManager@Experience@Shell@Internal@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Internal::Shell::Experience::ITrayMtcUvcFlyoutExperienceManager>::unconditional_release_ref(void)
0x1800e45b8  mov     rcx, rsi
0x1800e45bb  call    cs:__imp_CoreUICreate
0x1800e45c1  mov     rcx, [rsp+98h]; this
0x1800e45c9  test    eax, eax
0x1800e45cb  jns     short loc_1800E45E1
0x1800e45cd  mov     r9d, eax; char *
0x1800e45d0  lea     r8, aShellcommonUnd_85; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800e45d7  mov     edx, 1AEh; void *
0x1800e45dc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e45e1  mov     [rsp+98h+arg_10], 0
0x1800e45ed  lea     rcx, [rsp+98h+arg_10]
0x1800e45f5  call    cs:__imp_CoreUIFactoryCreate
0x1800e45fb  mov     rcx, [rsp+98h]; this
0x1800e4603  test    eax, eax
0x1800e4605  jns     short loc_1800E461B
0x1800e4607  mov     r9d, eax; char *
0x1800e460a  lea     r8, aShellcommonUnd_85; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800e4611  mov     edx, 1B1h; void *
0x1800e4616  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e461b  xorps   xmm0, xmm0
0x1800e461e  movdqu  [rsp+98h+var_40], xmm0
0x1800e4624  lea     rcx, [rsp+98h+var_40]
0x1800e4629  call    ?Initialize@SharedMessagePortRefPtr@@QEAAJW4InputCapability@@@Z; SharedMessagePortRefPtr::Initialize(InputCapability)
0x1800e462e  mov     rcx, [rsp+98h]; this
0x1800e4636  test    eax, eax
0x1800e4638  jns     short loc_1800E464E
0x1800e463a  mov     r9d, eax; char *
0x1800e463d  lea     r8, aShellcommonUnd_85; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800e4644  mov     edx, 1B4h; void *
0x1800e4649  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e464e  mov     [rsp+98h+arg_0], 0
0x1800e4659  mov     rcx, [rsp+98h+arg_10]
0x1800e4661  mov     rax, [rcx]
0x1800e4664  lea     r8, [rsp+98h+arg_0]
0x1800e466c  lea     rdx, _GUID_036f83f6_2c8b_4f50_ad5a_833402b2feb4
0x1800e4673  mov     rax, [rax+18h]
0x1800e4677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e467c  mov     rcx, [rsp+98h]; this
0x1800e4684  test    eax, eax
0x1800e4686  jns     short loc_1800E469C
0x1800e4688  mov     r9d, eax; char *
0x1800e468b  lea     r8, aShellcommonUnd_85; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800e4692  mov     edx, 1B7h; void *
0x1800e4697  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e469c  mov     [rsp+98h+arg_18], 0
0x1800e46a8  mov     rcx, [rsp+98h+arg_10]
0x1800e46b0  mov     r10, [rcx]
0x1800e46b3  mov     rax, rbx
0x1800e46b6  lea     r8, [rbx+8]
0x1800e46ba  neg     rax
0x1800e46bd  sbb     rdx, rdx
0x1800e46c0  and     rdx, r8
0x1800e46c3  lea     rax, [rsp+98h+arg_18]
0x1800e46cb  mov     [rsp+98h+var_68], rax
0x1800e46d0  mov     r8, qword ptr [rsp+98h+var_40+8]
0x1800e46d5  mov     [rsp+98h+var_70], r8
0x1800e46da  lea     rax, aSystemRemotete; "System\\RemoteTextInputOverrider"
0x1800e46e1  mov     qword ptr [rsp+98h+var_78], rax; int
0x1800e46e6  mov     r9d, [rsp+98h+arg_0]
0x1800e46ee  xor     r8d, r8d
0x1800e46f1  mov     rax, [r10+20h]
0x1800e46f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e46fa  mov     rcx, [rsp+98h]; this
0x1800e4702  test    eax, eax
0x1800e4704  jns     short loc_1800E471A
0x1800e4706  mov     r9d, eax; char *
0x1800e4709  lea     r8, aShellcommonUnd_85; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800e4710  mov     edx, 1C0h; void *
0x1800e4715  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e471a  mov     [rsp+98h+var_50], rbx
0x1800e471f  lea     rax, aSystemLowlevel; "System\\LowLevelKeyboardOverriderCallba"...
0x1800e4726  mov     [rsp+98h+var_48], rax
0x1800e472b  lea     r14, [rbx+38h]
0x1800e472f  cmp     qword ptr [r14], 0
0x1800e4733  jz      short loc_1800E473D
0x1800e4735  mov     rcx, r14
0x1800e4738  call    ?unconditional_release_ref@?$com_ptr@UITrayMtcUvcFlyoutExperienceManager@Experience@Shell@Internal@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Internal::Shell::Experience::ITrayMtcUvcFlyoutExperienceManager>::unconditional_release_ref(void)
0x1800e473d  lea     r9, [rsp+98h+var_50]
0x1800e4742  lea     r8, [rsp+98h+var_48]
0x1800e4747  mov     rcx, r14
0x1800e474a  call    ??$MakeAndInitialize@VMessageProxyReconnectAdapter@@V1@AEBU_GUID@@PEBGPEAVKeyboardOverriderHook@SystemKeyboardDeliveryInterceptor@implementation@Input@UI@WindowsUdk@winrt@@@Details@WRL@Microsoft@@YAJPEAPEAVMessageProxyReconnectAdapter@@AEBU_GUID@@$$QEAPEBG$$QEAPEAVKeyboardOverriderHook@SystemKeyboardDeliveryInterceptor@implementation@Input@UI@WindowsUdk@winrt@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MessageProxyReconnectAdapter,MessageProxyReconnectAdapter,_GUID const &,ushort const *,winrt::WindowsUdk::UI::Input::implementation::SystemKeyboardDeliveryInterceptor::KeyboardOverriderHook *>(MessageProxyReconnectAdapter * *,_GUID const &,ushort const * &&,winrt::WindowsUdk::UI::Input::implementation::SystemKeyboardDeliveryInterceptor::KeyboardOverriderHook * &&)
0x1800e474f  mov     rcx, [rsp+98h]; this
0x1800e4757  test    eax, eax
0x1800e4759  jns     short loc_1800E476F
0x1800e475b  mov     r9d, eax; char *
0x1800e475e  lea     r8, aShellcommonUnd_85; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800e4765  mov     edx, 1C6h; void *
0x1800e476a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e476f  mov     eax, 1
0x1800e4774  xchg    al, [rbx+48h]
0x1800e4777  mov     rbx, [rsp+98h+var_58]
0x1800e477c  test    rbx, rbx
0x1800e477f  jz      short loc_1800E479D
0x1800e4781  lea     rcx, [rsp+98h+var_48]; this
0x1800e4786  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800e478b  mov     rcx, rbx; this
0x1800e478e  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x1800e4793  lea     rcx, [rsp+98h+var_48]; this
0x1800e4798  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800e479d  mov     [rsp+98h+var_58], 0
0x1800e47a6  mov     rcx, [rsi]
0x1800e47a9  mov     rax, [rcx]
0x1800e47ac  mov     rax, [rax+0E8h]
0x1800e47b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e47b8  mov     rcx, [rsp+98h]; this
0x1800e47c0  test    eax, eax
0x1800e47c2  jns     short loc_1800E47D9
0x1800e47c4  mov     r9d, eax; char *
0x1800e47c7  lea     r8, aShellcommonUnd_85; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800e47ce  mov     edx, 1CEh; void *
0x1800e47d3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e47d9  cmp     [rsp+98h+arg_18], 0
0x1800e47e2  jz      short loc_1800E47F2
0x1800e47e4  lea     rcx, [rsp+98h+arg_18]
0x1800e47ec  call    ?unconditional_release_ref@?$com_ptr@UITrayMtcUvcFlyoutExperienceManager@Experience@Shell@Internal@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Internal::Shell::Experience::ITrayMtcUvcFlyoutExperienceManager>::unconditional_release_ref(void)
0x1800e47f1  nop
0x1800e47f2  mov     rbx, qword ptr [rsp+98h+var_40]
0x1800e47f7  mov     qword ptr [rsp+98h+var_40], 0
0x1800e4800  mov     rsi, qword ptr [rsp+98h+var_40+8]
0x1800e4805  mov     qword ptr [rsp+98h+var_40+8], 0
0x1800e480e  test    rbx, rbx
0x1800e4811  jz      short loc_1800E4831
0x1800e4813  mov     rax, [rbx]
0x1800e4816  mov     rcx, rbx
0x1800e4819  mov     rax, [rax+20h]
0x1800e481d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4822  mov     rax, [rbx]
0x1800e4825  mov     rcx, rbx
0x1800e4828  mov     rax, [rax+10h]
0x1800e482c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4831  test    rsi, rsi
0x1800e4834  jz      short loc_1800E4846
0x1800e4836  mov     rax, [rsi]
0x1800e4839  mov     rcx, rsi
0x1800e483c  mov     rax, [rax+10h]
0x1800e4840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4845  nop
0x1800e4846  cmp     [rsp+98h+arg_10], 0
0x1800e484f  jz      short loc_1800E485F
0x1800e4851  lea     rcx, [rsp+98h+arg_10]
0x1800e4859  call    ?unconditional_release_ref@?$com_ptr@UITrayMtcUvcFlyoutExperienceManager@Experience@Shell@Internal@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Internal::Shell::Experience::ITrayMtcUvcFlyoutExperienceManager>::unconditional_release_ref(void)
0x1800e485e  nop
0x1800e485f  lea     rcx, [rsp+98h+var_58]
0x1800e4864  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?SetEvent@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800e4869  nop
0x1800e486a  jmp     short loc_1800E4874
0x1800e486c  mov     rdi, [rsp+98h+arg_8]
0x1800e4874  mov     rcx, rdi
0x1800e4877  add     rsp, 78h
0x1800e487b  pop     r14
0x1800e487d  pop     rdi
0x1800e487e  pop     rsi
0x1800e487f  pop     rbx
0x1800e4880  jmp     ??1?$shared_ptr@VUserRegistryReaderWriter@implementation@Text@Input@UI@WindowsUdk@winrt@@@std@@QEAA@XZ; std::shared_ptr<winrt::WindowsUdk::UI::Input::Text::implementation::UserRegistryReaderWriter>::~shared_ptr<winrt::WindowsUdk::UI::Input::Text::implementation::UserRegistryReaderWriter>(void)
```
