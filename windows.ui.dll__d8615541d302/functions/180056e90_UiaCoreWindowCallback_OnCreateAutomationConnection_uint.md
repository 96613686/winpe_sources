# UiaCoreWindowCallback::OnCreateAutomationConnection(uint)

- ea: `0x180056e90`
- end: `0x1800571e7`
- name: `?OnCreateAutomationConnection@UiaCoreWindowCallback@@UEAAJI@Z`
- size: `855`
- prototype: `__int64 __fastcall(UiaCoreWindowCallback *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800038e0`
- `0x180014754`
- `0x180016064`
- `0x180021e80`
- `0x180044d80`
- `0x18004c0a0`
- `0x180056e54`
- `0x180056e90`
- `0x1800571f0`
- `0x1800581b8`
- `0x18005f1a4`
- `0x18007278c`
- `0x18007caac`
- `0x18007d080`
- `0x18007e824`
- `0x18007f4b4`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180056ecc`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180056ecc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056ede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056ede`

## string_xrefs

- `0x180056f75`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x18005703e`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x1800570ba`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x18005712e`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall UiaCoreWindowCallback::OnCreateAutomationConnection(UiaCoreWindowCallback *this)
{
  char *v2; // rbx
  void *v3; // rdx
  HANDLE Event; // rdi
  unsigned int v5; // r8d
  const char *v6; // r9
  wil **v7; // r12
  __int64 *v8; // rax
  __int64 v9; // r15
  unsigned int LastError; // edi
  _QWORD *v12; // rdi
  _QWORD *v13; // rax
  _QWORD *v14; // rsi
  __int64 v15; // r14
  __int64 (__fastcall *v16)(__int64, __int64, __int64, __int64 *); // rsi
  int v17; // eax
  unsigned int v18; // esi
  int v19; // eax
  void *v20; // rdx
  unsigned int v21; // r8d
  int v22; // r9d
  wil *v23; // rcx
  const char *v24; // r9
  int v25; // [rsp+20h] [rbp-50h]
  __int128 v26; // [rsp+38h] [rbp-38h] BYREF
  _QWORD v27[2]; // [rsp+48h] [rbp-28h] BYREF
  __int128 v28; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  __int64 v30; // [rsp+B0h] [rbp+40h] BYREF
  _QWORD *v31; // [rsp+C0h] [rbp+50h] BYREF
  char *v32; // [rsp+C8h] [rbp+58h] BYREF

  v2 = (char *)this - 32;
  v32 = (char *)this - 32;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v32);
  v26 = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v3, v5, v6);
  GetLastError();
  _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
    &v26,
    Event);
  v27[0] = v2;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v27);
  v27[1] = v2;
  v28 = 0;
  v7 = (wil **)v26;
  if ( *((_QWORD *)&v26 + 1) )
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v26 + 1) + 8LL));
  __Reset0____Ptr_base_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___std__QEAAXPEAV__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__PEAV_Ref_count_base_2__Z(
    &v28,
    v7);
  v8 = (__int64 *)Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::UI::Core::IDispatchedHandler::*)(void)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::UI::Core::IDispatchedHandler,Microsoft::WRL::FtmBase>,_lambda_f4d7964cda81561d270afa7547c0169b_,-1,>,_lambda_f4d7964cda81561d270afa7547c0169b_>(
                    &v31,
                    v27);
  v9 = *v8;
  *v8 = 0;
  if ( v31 )
  {
    v31 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::FtmBase>>::Release();
  }
  _lambda_f4d7964cda81561d270afa7547c0169b_::~_lambda_f4d7964cda81561d270afa7547c0169b_((_lambda_f4d7964cda81561d270afa7547c0169b_ *)v27);
  if ( !v9 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13C,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)0x8007000ELL,
      v25);
    __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(&v26);
    if ( v2 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    return LastError;
  }
  v12 = 0;
  v13 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  v14 = v13;
  v31 = v13;
  if ( v13 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler>(v13);
    *v14 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncActionCompletedHandler::*)(Windows::Foundation::IAsyncAction *,enum ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Windows::Foundation::IAsyncActionCompletedHandler,_lambda_e731e89b699233f6c77bfa940b55790c_,-1,Windows::Foundation::IAsyncAction *,enum ABI::Windows::Foundation::AsyncStatus>::`vftable';
    v12 = v14;
    v31 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::UI::Core::CDispatcher>::~MakeAllocator<Windows::UI::Core::CDispatcher>(&v31);
  v31 = v12;
  v30 = 0;
  v15 = *((_QWORD *)this + 3);
  v16 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v15 + 64LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v30);
  v17 = v16(v15, 1, v9, &v30);
  v18 = v17;
  if ( v17 >= 0 )
  {
    v19 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v30 + 48LL))(v30, v12);
    LastError = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x148,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
        (const char *)(unsigned int)v19,
        v25);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v30);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v31);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(&v26);
      if ( v2 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
      return LastError;
    }
    if ( v7 )
      v23 = *v7;
    else
      v23 = 0;
    if ( !wil::handle_wait(v23, v20, v21, v22) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x149,
                    (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
                    v24);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v30);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v31);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(&v26);
      if ( v2 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
      return LastError;
    }
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v30);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v31);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(&v26);
    if ( v2 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)v17,
      v25);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v30);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v31);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(&v26);
    if ( v2 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    return v18;
  }
}

```

## disassembly

```asm
0x180056e90  push    rbp
0x180056e92  push    rbx
0x180056e93  push    rsi
0x180056e94  push    rdi
0x180056e95  push    r12
0x180056e97  push    r14
0x180056e99  push    r15
0x180056e9b  mov     rbp, rsp
0x180056e9e  sub     rsp, 70h
0x180056ea2  mov     r14, rcx
0x180056ea5  lea     rbx, [rcx-20h]
0x180056ea9  mov     [rbp+arg_18], rbx
0x180056ead  lea     rcx, [rbp+arg_18]
0x180056eb1  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180056eb6  nop
0x180056eb7  xorps   xmm0, xmm0
0x180056eba  movdqu  [rbp+var_38], xmm0
0x180056ebf  mov     r9d, 1F0003h; dwDesiredAccess
0x180056ec5  xor     r8d, r8d; dwFlags
0x180056ec8  xor     edx, edx; lpName
0x180056eca  xor     ecx, ecx; lpEventAttributes
0x180056ecc  call    cs:__imp_CreateEventExW
0x180056ed2  mov     rdi, rax
0x180056ed5  test    rax, rax
0x180056ed8  jz      loc_1800571DD
0x180056ede  call    cs:__imp_GetLastError
0x180056ee4  mov     rdx, rdi
0x180056ee7  lea     rcx, [rbp+var_38]
0x180056eeb  call    ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x180056ef0  nop
0x180056ef1  mov     [rbp+var_28], rbx
0x180056ef5  lea     rcx, [rbp+var_28]
0x180056ef9  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180056efe  mov     [rbp+var_20], rbx
0x180056f02  xorps   xmm0, xmm0
0x180056f05  movdqu  [rbp+var_18], xmm0
0x180056f0a  mov     r8, qword ptr [rbp+var_38+8]
0x180056f0e  mov     r12, qword ptr [rbp+var_38]
0x180056f12  test    r8, r8
0x180056f15  jz      short loc_180056F1C
0x180056f17  lock inc dword ptr [r8+8]
0x180056f1c  mov     rdx, r12
0x180056f1f  lea     rcx, [rbp+var_18]
0x180056f23  call    ?_Reset0@?$_Ptr_base@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@std@@QEAAXPEAV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@PEAV_Ref_count_base@2@@Z
0x180056f28  nop
0x180056f29  lea     rdx, [rbp+var_28]
0x180056f2d  lea     rcx, [rbp+arg_10]
0x180056f31  call    ??$Make@U?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDispatchedHandler@Core@UI@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_f4d7964cda81561d270afa7547c0169b_@@$0?0$$V@?$DelegateArgTraits@P8IDispatchedHandler@Core@UI@Windows@@EAAJXZ@Details@WRL@Microsoft@@V_lambda_f4d7964cda81561d270afa7547c0169b_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@U?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDispatchedHandler@Core@UI@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_f4d7964cda81561d270afa7547c0169b_@@$0?0$$V@?$DelegateArgTraits@P8IDispatchedHandler@Core@UI@Windows@@EAAJXZ@Details@WRL@Microsoft@@@12@$$QEAV_lambda_f4d7964cda81561d270afa7547c0169b_@@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::UI::Core::IDispatchedHandler::*)(void)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::UI::Core::IDispatchedHandler,Microsoft::WRL::FtmBase>,_lambda_f4d7964cda81561d270afa7547c0169b_,-1,>,_lambda_f4d7964cda81561d270afa7547c0169b_>(_lambda_f4d7964cda81561d270afa7547c0169b_ &&)
0x180056f36  mov     r15, [rax]
0x180056f39  mov     [rbp+var_40], r15
0x180056f3d  mov     qword ptr [rax], 0
0x180056f44  mov     rcx, [rbp+arg_10]
0x180056f48  test    rcx, rcx
0x180056f4b  jz      short loc_180056F5B
0x180056f4d  mov     [rbp+arg_10], 0
0x180056f55  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVRadialController@Input@UI@Windows@@PEAVRadialControllerButtonPressedEventArgs@234@@Foundation@Windows@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::FtmBase>>::Release(void)
0x180056f5a  nop
0x180056f5b  lea     rcx, [rbp+var_28]; this
0x180056f5f  call    ??1_lambda_f4d7964cda81561d270afa7547c0169b_@@QEAA@XZ; _lambda_f4d7964cda81561d270afa7547c0169b_::~_lambda_f4d7964cda81561d270afa7547c0169b_(void)
0x180056f64  test    r15, r15
0x180056f67  jnz     short loc_180056FB7
0x180056f69  mov     rcx, [rbp+38h]; this
0x180056f6d  mov     edi, 8007000Eh
0x180056f72  mov     r9d, edi; char *
0x180056f75  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180056f7c  mov     edx, 13Ch; void *
0x180056f81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056f86  nop
0x180056f87  lea     rcx, [rbp+var_38]
0x180056f8b  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x180056f90  nop
0x180056f91  test    rbx, rbx
0x180056f94  jz      short loc_180056FA6
0x180056f96  mov     rcx, [rbx]
0x180056f99  mov     rax, [rcx+10h]
0x180056f9d  mov     rcx, rbx
0x180056fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056fa5  nop
0x180056fa6  mov     eax, edi
0x180056fa8  add     rsp, 70h
0x180056fac  pop     r15
0x180056fae  pop     r14
0x180056fb0  pop     r12
0x180056fb2  pop     rdi
0x180056fb3  pop     rsi
0x180056fb4  pop     rbx
0x180056fb5  pop     rbp
0x180056fb6  retn
0x180056fb7  xor     edi, edi
0x180056fb9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180056fc0  lea     ecx, [rdi+18h]; unsigned __int64
0x180056fc3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180056fc8  mov     rsi, rax
0x180056fcb  mov     [rbp+arg_10], rax
0x180056fcf  test    rax, rax
0x180056fd2  jz      short loc_180056FF1
0x180056fd4  mov     rcx, rax
0x180056fd7  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler>(void)
0x180056fdc  lea     rax, ??_7?$DelegateInvokeHelper@UIAsyncActionCompletedHandler@Foundation@Windows@@V_lambda_e731e89b699233f6c77bfa940b55790c_@@$0?0PEAUIAsyncAction@23@W4AsyncStatus@23ABI@@@?$DelegateArgTraits@P8IAsyncActionCompletedHandler@Foundation@Windows@@EAAJPEAUIAsyncAction@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncActionCompletedHandler::*)(Windows::Foundation::IAsyncAction *,ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Windows::Foundation::IAsyncActionCompletedHandler,_lambda_e731e89b699233f6c77bfa940b55790c_,-1,Windows::Foundation::IAsyncAction *,ABI::Windows::Foundation::AsyncStatus>::`vftable'
0x180056fe3  mov     [rsi], rax
0x180056fe6  mov     rdi, rsi
0x180056fe9  mov     [rbp+arg_10], 0
0x180056ff1  lea     rcx, [rbp+arg_10]
0x180056ff5  call    ??1?$MakeAllocator@VCDispatcher@Core@UI@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::UI::Core::CDispatcher>::~MakeAllocator<Windows::UI::Core::CDispatcher>(void)
0x180056ffa  mov     [rbp+arg_10], rdi
0x180056ffe  mov     [rbp+arg_0], 0
0x180057006  mov     r14, [r14+18h]
0x18005700a  mov     rax, [r14]
0x18005700d  mov     rsi, [rax+40h]
0x180057011  lea     rcx, [rbp+arg_0]
0x180057015  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005701a  lea     r9, [rbp+arg_0]
0x18005701e  mov     r8, r15
0x180057021  mov     edx, 1
0x180057026  mov     rcx, r14
0x180057029  mov     rax, rsi
0x18005702c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057031  mov     esi, eax
0x180057033  test    eax, eax
0x180057035  jns     short loc_18005709A
0x180057037  mov     rcx, [rbp+38h]; this
0x18005703b  mov     r9d, eax; char *
0x18005703e  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180057045  mov     edx, 147h; void *
0x18005704a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005704f  nop
0x180057050  lea     rcx, [rbp+arg_0]
0x180057054  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180057059  nop
0x18005705a  lea     rcx, [rbp+arg_10]
0x18005705e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180057063  nop
0x180057064  mov     rax, [r15]
0x180057067  mov     rcx, r15
0x18005706a  mov     rax, [rax+10h]
0x18005706e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057073  nop
0x180057074  lea     rcx, [rbp+var_38]
0x180057078  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x18005707d  nop
0x18005707e  test    rbx, rbx
0x180057081  jz      short loc_180057093
0x180057083  mov     rax, [rbx]
0x180057086  mov     rcx, rbx
0x180057089  mov     rax, [rax+10h]
0x18005708d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057092  nop
0x180057093  mov     eax, esi
0x180057095  jmp     loc_180056FA8
0x18005709a  mov     rcx, [rbp+arg_0]
0x18005709e  mov     rax, [rcx]
0x1800570a1  mov     rdx, rdi
0x1800570a4  mov     rax, [rax+30h]
0x1800570a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800570ad  mov     edi, eax
0x1800570af  test    eax, eax
0x1800570b1  jns     short loc_180057114
0x1800570b3  mov     rcx, [rbp+38h]; this
0x1800570b7  mov     r9d, eax; char *
0x1800570ba  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800570c1  mov     edx, 148h; void *
0x1800570c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800570cb  nop
0x1800570cc  lea     rcx, [rbp+arg_0]
0x1800570d0  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800570d5  nop
0x1800570d6  lea     rcx, [rbp+arg_10]
0x1800570da  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800570df  nop
0x1800570e0  mov     rax, [r15]
0x1800570e3  mov     rcx, r15
0x1800570e6  mov     rax, [rax+10h]
0x1800570ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800570ef  nop
0x1800570f0  lea     rcx, [rbp+var_38]
0x1800570f4  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x1800570f9  nop
0x1800570fa  test    rbx, rbx
0x1800570fd  jz      short loc_18005710F
0x1800570ff  mov     rax, [rbx]
0x180057102  mov     rcx, rbx
0x180057105  mov     rax, [rax+10h]
0x180057109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005710e  nop
0x18005710f  jmp     loc_180056FA6
0x180057114  test    r12, r12
0x180057117  jz      short loc_18005711F
0x180057119  mov     rcx, [r12]
0x18005711d  jmp     short loc_180057121
0x18005711f  xor     ecx, ecx; this
0x180057121  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x180057126  test    al, al
0x180057128  jnz     short loc_18005718E
0x18005712a  mov     rcx, [rbp+38h]; this
0x18005712e  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180057135  mov     edx, 149h; void *
0x18005713a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005713f  mov     edi, eax
0x180057141  lea     rcx, [rbp+arg_0]
0x180057145  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005714a  nop
0x18005714b  lea     rcx, [rbp+arg_10]
0x18005714f  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180057154  nop
0x180057155  test    r15, r15
0x180057158  jz      short loc_18005716A
0x18005715a  mov     rcx, [r15]
0x18005715d  mov     rax, [rcx+10h]
0x180057161  mov     rcx, r15
0x180057164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057169  nop
0x18005716a  lea     rcx, [rbp+var_38]
0x18005716e  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x180057173  nop
0x180057174  test    rbx, rbx
0x180057177  jz      short loc_180057189
0x180057179  mov     rax, [rbx]
0x18005717c  mov     rcx, rbx
0x18005717f  mov     rax, [rax+10h]
0x180057183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057188  nop
0x180057189  jmp     loc_180056FA6
0x18005718e  lea     rcx, [rbp+arg_0]
0x180057192  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180057197  nop
0x180057198  lea     rcx, [rbp+arg_10]
0x18005719c  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800571a1  nop
0x1800571a2  test    r15, r15
0x1800571a5  jz      short loc_1800571B7
0x1800571a7  mov     rax, [r15]
0x1800571aa  mov     rcx, r15
0x1800571ad  mov     rax, [rax+10h]
0x1800571b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800571b6  nop
0x1800571b7  lea     rcx, [rbp+var_38]
0x1800571bb  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x1800571c0  nop
0x1800571c1  test    rbx, rbx
0x1800571c4  jz      short loc_1800571D6
0x1800571c6  mov     rax, [rbx]
0x1800571c9  mov     rcx, rbx
0x1800571cc  mov     rax, [rax+10h]
0x1800571d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800571d5  nop
0x1800571d6  xor     eax, eax
0x1800571d8  jmp     loc_180056FA8
0x1800571dd  mov     rcx, [rbp+38h]; this
0x1800571e1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
