# UwpWindowManagerBridge::RuntimeClassInitialize(IUwpWindowEventDispatcherInternal *)

- ea: `0x1800d6290`
- end: `0x1800d6790`
- name: `?RuntimeClassInitialize@UwpWindowManagerBridge@@QEAAJPEAUIUwpWindowEventDispatcherInternal@@@Z`
- size: `1280`
- prototype: `__int64 __fastcall(UwpWindowManagerBridge *__hidden this, struct IUwpWindowEventDispatcherInternal *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800d60d4`

## callees

- `0x1800358f0`
- `0x180043f00`
- `0x18006c2dc`
- `0x18006fd50`
- `0x18007f488`
- `0x18007ff08`
- `0x180081d98`
- `0x1800d5490`
- `0x1800d6290`
- `0x1800d7f48`
- `0x1801b87b0`
- `0x1801d4cec`
- `0x18028ef50`
- `0x1802ac9b4`
- `0x1802b83d0`
- `0x1802d19d8`
- `0x180322264`
- `0x180356360`
- `0x18048a92c`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800d62e1`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800d62e1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d64ff`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d6590`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d64ff`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d6590`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d62f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d62f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d64e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d6579`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d64e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d6579`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d6517`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d65a8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d6517`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d65a8`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800d6492`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800d6492`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800d647d`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800d647d`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800d649e`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800d649e`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800d6382`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800d6382`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800d63dc`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800d6404`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800d63dc`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800d6404`
- `msvcp_win!_Thrd_detach` at `0x1800d63f8`
- `msvcp_win!_Thrd_detach` at `0x1800d63f8`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800d6460`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800d6460`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall UwpWindowManagerBridge::RuntimeClassInitialize(
        UwpWindowManagerBridge *this,
        struct IUwpWindowEventDispatcherInternal *a2)
{
  HANDLE Event; // rax
  void *v4; // rdx
  unsigned int v5; // r8d
  const char *v6; // r9
  HANDLE v7; // rbx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  int v9; // eax
  __int64 v10; // rdx
  unsigned int v11; // r8d
  int v12; // r9d
  wil *v13; // rcx
  Windows::Internal::ApplicationModel::WindowManagement *v14; // rcx
  __int64 v15; // rcx
  int ActivationFactory; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, char *); // rbx
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rbx
  __int64 (__fastcall *v24)(__int64, char *); // rdi
  __int64 v25; // rdx
  int v26; // eax
  __int64 v27; // rsi
  __int64 (__fastcall *v28)(__int64, char *); // rdi
  int v29; // eax
  int started; // eax
  wil *v31; // rcx
  int v33; // eax
  UwpWindowManagerBridge *v34; // rbx
  void *v35; // rdx
  CCriticalFailureHandler *v36; // rcx
  const char *v37; // r9
  unsigned __int64 *v38; // [rsp+20h] [rbp-C8h]
  unsigned __int64 *v39; // [rsp+28h] [rbp-C0h]
  int v40; // [rsp+20h] [rbp-C8h]
  unsigned int v41[4]; // [rsp+30h] [rbp-B8h] BYREF
  _Thrd_t v42; // [rsp+40h] [rbp-A8h] BYREF
  __int128 v43; // [rsp+50h] [rbp-98h] BYREF
  std::_Ref_count_base *v44[2]; // [rsp+60h] [rbp-88h] BYREF
  UwpWindowManagerBridge *v45; // [rsp+70h] [rbp-78h]
  _BYTE v46[24]; // [rsp+78h] [rbp-70h] BYREF
  _BYTE v47[16]; // [rsp+90h] [rbp-58h] BYREF
  _Thrd_t v48; // [rsp+A0h] [rbp-48h] BYREF
  Windows::Internal::ApplicationModel::WindowManagement *retaddr; // [rsp+E8h] [rbp+0h]

  v45 = this;
  wil::com_ptr_t<Windows::Foundation::Collections::IPropertySet,wil::err_exception_policy>::operator=(
    (char *)this + 296,
    a2);
  *(_OWORD *)v44 = 0;
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  try
  {
    v7 = Event;
    if ( !Event )
      wil::details::in1diag3::Throw_GetLastError(retaddr, v4, v5, v6);
    GetLastError();
    _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
      v44,
      v7);
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((char *)this + 280, 1, 0);
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x37,
        (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\uwpwindowmanagerbridge.cpp",
        (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
        v40);
    v9 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
           (char *)this + 288,
           1,
           0);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x39,
        (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\uwpwindowmanagerbridge.cpp",
        (const char *)(unsigned int)v9,
        v40);
    if ( Windows::Internal::ApplicationModel::WindowManagement::IsWindowManagementInProcEnabled(retaddr) )
    {
      v43 = 0;
      __ExceptionPtrCreate(&v43);
      *(_QWORD *)v41 = this;
      if ( this )
        (*(void (__fastcall **)(UwpWindowManagerBridge *))(*(_QWORD *)this + 8LL))(this);
      v10 = lambda_2a8f8fa06f2e0b1768a49123f6915af2_::_lambda_2a8f8fa06f2e0b1768a49123f6915af2_(
              (unsigned int)v46,
              (unsigned int)v44,
              (_DWORD)this,
              (unsigned int)v41,
              (__int64)&v43);
      std::thread::_Start__lambda_2a8f8fa06f2e0b1768a49123f6915af2___(&v42, v10);
      if ( !v42._Id )
        std::_Throw_Cpp_error(1);
      v48 = v42;
      if ( _Thrd_detach(&v48) )
        std::_Throw_Cpp_error(1);
      v42 = 0;
      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(v47);
      __1__shared_ptr_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___std__QEAA_XZ(v46);
      if ( *(_QWORD *)v41 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v41 + 16LL))(*(_QWORD *)v41);
      if ( v44[0] )
        v13 = *(wil **)v44[0];
      else
        v13 = 0;
      wil::handle_wait(v13, (void *)0xFFFFFFFFLL, v11, v12);
      if ( __ExceptionPtrToBool(&v43) )
      {
        v42 = 0;
        __ExceptionPtrCopy(&v42, &v43);
        *(_QWORD *)v41 = &v42;
        __ExceptionPtrRethrow(&v42);
      }
      __ExceptionPtrDestroy(&v43);
    }
    else
    {
      v15 = *((_QWORD *)this + 21);
      *((_QWORD *)this + 21) = 0;
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      if ( WindowsCreateStringReference(
             L"Windows.Internal.ApplicationModel.WindowManagement.Window",
             0x39u,
             (HSTRING_HEADER *)&v48._Id,
             (HSTRING *)&v48) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      ActivationFactory = RoGetActivationFactory(
                            v48._Hnd,
                            &GUID_5e75aba7_c424_4076_9d47_409a1eda087f,
                            (char *)this + 168);
      if ( ActivationFactory < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7B,
          (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\uwpwindowmanagerbridge.cpp",
          (const char *)(unsigned int)ActivationFactory,
          v40);
      v17 = *((_QWORD *)this + 6);
      *((_QWORD *)this + 6) = 0;
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      if ( WindowsCreateStringReference(
             L"Windows.Internal.ApplicationModel.WindowManagement.UniversalAppModel",
             0x44u,
             (HSTRING_HEADER *)&v48._Id,
             (HSTRING *)&v48) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v18 = RoGetActivationFactory(v48._Hnd, &GUID_b880ce78_2e50_5a73_bfaa_a3f9a8b2f042, (char *)this + 48);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7C,
          (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\uwpwindowmanagerbridge.cpp",
          (const char *)(unsigned int)v18,
          v40);
      v19 = *((_QWORD *)this + 21);
      v20 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v19 + 48LL);
      wil::com_ptr_t<IUwpWindowWrapperInternal,wil::err_exception_policy>::reset((char *)this + 176);
      v21 = v20(v19, (char *)this + 176);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7E,
          (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\uwpwindowmanagerbridge.cpp",
          (const char *)(unsigned int)v21,
          v40);
      v22 = *((_QWORD *)this + 23);
      *((_QWORD *)this + 23) = 0;
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      wil::com_ptr_t<Windows::Internal::ApplicationModel::WindowManagement::IWindowWatcher,wil::err_exception_policy>::query_to<Windows::Internal::ApplicationModel::WindowManagement::IUniversalAppModelWatcher>(
        (char *)this + 176,
        (char *)this + 184);
      wil::GetActivationFactory<Windows::Internal::Shell::UwpWindowLifecycleManagement::IUwpWindowLifecycleManagerStatics>(v41);
      v23 = *(_QWORD *)v41;
      v24 = *(__int64 (__fastcall **)(__int64, char *))(**(_QWORD **)v41 + 48LL);
      v25 = *((_QWORD *)this + 29);
      *((_QWORD *)this + 29) = 0;
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      v26 = v24(v23, (char *)this + 232);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x82,
          (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\uwpwindowmanagerbridge.cpp",
          (const char *)(unsigned int)v26,
          v40);
      v27 = *((_QWORD *)this + 29);
      v28 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v27 + 120LL);
      wil::com_ptr_t<IUwpWindowWrapperInternal,wil::err_exception_policy>::reset((char *)this + 240);
      v29 = v28(v27, (char *)this + 240);
      if ( v29 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x84,
          (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\uwpwindowmanagerbridge.cpp",
          (const char *)(unsigned int)v29,
          v40);
      v14 = *(Windows::Internal::ApplicationModel::WindowManagement **)v41;
      if ( *(_QWORD *)v41 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v41 + 16LL))(*(_QWORD *)v41);
    }
    if ( !Windows::Internal::ApplicationModel::WindowManagement::IsWindowManagementInProcEnabled(v14) )
    {
      started = UwpWindowManagerBridge::StartWindowWatcher(this);
      if ( started < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8B,
          (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\uwpwindowmanagerbridge.cpp",
          (const char *)(unsigned int)started,
          v40);
    }
    v31 = v44[1];
    if ( v44[1] )
      std::_Ref_count_base::_Decref(v44[1]);
  }
  catch ( ... )
  {
    v33 = wil::ResultFromCaughtException(v31);
    v34 = v45;
    *((_DWORD *)v45 + 76) = v33;
    wil::details::SetEvent(*((wil::details **)v34 + 35), v35);
    v37 = (const char *)*((unsigned int *)v34 + 76);
    v41[0] = *((_DWORD *)v34 + 76);
    if ( !CRVPrivate::cfhImmersiveShellStartup )
    {
      CCriticalFailureHandler::GetFakeFailure(v36, (int *)v41);
      CRVPrivate::cfhImmersiveShellStartup = 1;
      v37 = (const char *)v41[0];
    }
    if ( (int)v37 < 0 )
    {
      if ( (_DWORD)v37 != -2147024882 && (_DWORD)v37 != -2144862209 )
      {
        CCriticalFailureHandler::HandleFailure(
          v36,
          (int *)v41,
          L"pcshell\\twinui\\viewmanagerinterop\\lib\\uwpwindowmanagerbridge.cpp",
          0x96u,
          v38,
          v39);
        v37 = (const char *)v41[0];
      }
      if ( (int)v37 < 0 )
      {
        v41[0] = (unsigned int)v37;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x96,
          (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\uwpwindowmanagerbridge.cpp",
          v37,
          (int)v38);
        return v41[0];
      }
    }
  }
  ViewManagerInteropTraceLogging::WindowEventDispatcher_ConnectedToWindowManager();
  return 0;
}

```

## disassembly

```asm
0x1800d6290  mov     [rsp+arg_10], rbx
0x1800d6295  push    rsi
0x1800d6296  push    rdi
0x1800d6297  push    r14
0x1800d6299  sub     rsp, 0D0h
0x1800d62a0  mov     rax, cs:__security_cookie
0x1800d62a7  xor     rax, rsp
0x1800d62aa  mov     [rsp+0E8h+var_28], rax
0x1800d62b2  mov     r14, rcx
0x1800d62b5  mov     [rsp+0E8h+var_78], rcx
0x1800d62ba  add     rcx, 128h
0x1800d62c1  call    ??4?$com_ptr_t@UIPropertySet@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@PEAUIPropertySet@Collections@Foundation@Windows@@@Z; wil::com_ptr_t<Windows::Foundation::Collections::IPropertySet,wil::err_exception_policy>::operator=(Windows::Foundation::Collections::IPropertySet *)
0x1800d62c6  xorps   xmm0, xmm0
0x1800d62c9  movdqu  xmmword ptr [rsp+0E8h+var_88], xmm0
0x1800d62cf  mov     esi, 1
0x1800d62d4  mov     r9d, 1F0003h; dwDesiredAccess
0x1800d62da  mov     r8d, esi; dwFlags
0x1800d62dd  xor     edx, edx; lpName
0x1800d62df  xor     ecx, ecx; lpEventAttributes
0x1800d62e1  call    cs:__imp_CreateEventExW
0x1800d62e7  mov     rbx, rax
0x1800d62ea  test    rax, rax
0x1800d62ed  jz      loc_1800D6751
0x1800d62f3  call    cs:__imp_GetLastError
0x1800d62f9  mov     rdx, rbx
0x1800d62fc  lea     rcx, [rsp+0E8h+var_88]
0x1800d6301  call    ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x1800d6306  nop
0x1800d6307  lea     rcx, [r14+118h]
0x1800d630e  xor     r8d, r8d
0x1800d6311  mov     edx, esi
0x1800d6313  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800d6318  mov     rcx, [rsp+0E8h]; this
0x1800d6320  test    eax, eax
0x1800d6322  jns     short loc_1800D6336
0x1800d6324  mov     r9d, eax; char *
0x1800d6327  lea     r8, aPcshellTwinuiV_44; "pcshell\\twinui\\viewmanagerinterop\\li"...
0x1800d632e  lea     edx, [rsi+36h]; void *
0x1800d6331  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d6336  lea     rcx, [r14+120h]
0x1800d633d  xor     r8d, r8d
0x1800d6340  mov     edx, esi
0x1800d6342  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800d6347  mov     rcx, [rsp+0E8h]; this
0x1800d634f  test    eax, eax
0x1800d6351  jns     short loc_1800D6367
0x1800d6353  mov     r9d, eax; char *
0x1800d6356  lea     r8, aPcshellTwinuiV_44; "pcshell\\twinui\\viewmanagerinterop\\li"...
0x1800d635d  mov     edx, 39h ; '9'; void *
0x1800d6362  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d6367  call    ?IsWindowManagementInProcEnabled@WindowManagement@ApplicationModel@Internal@Windows@@YA_NXZ; Windows::Internal::ApplicationModel::WindowManagement::IsWindowManagementInProcEnabled(void)
0x1800d636c  test    al, al
0x1800d636e  jz      loc_1800D64A9
0x1800d6374  xorps   xmm0, xmm0
0x1800d6377  movdqu  [rsp+0E8h+var_98], xmm0
0x1800d637d  lea     rcx, [rsp+0E8h+var_98]
0x1800d6382  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800d6388  nop
0x1800d6389  mov     qword ptr [rsp+0E8h+var_B8], r14
0x1800d638e  test    r14, r14
0x1800d6391  jz      short loc_1800D63A3
0x1800d6393  mov     rax, [r14]
0x1800d6396  mov     rcx, r14
0x1800d6399  mov     rax, [rax+8]
0x1800d639d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d63a2  nop
0x1800d63a3  lea     rax, [rsp+0E8h+var_98]
0x1800d63a8  mov     qword ptr [rsp+0E8h+var_C8], rax
0x1800d63ad  lea     r9, [rsp+0E8h+var_B8]
0x1800d63b2  mov     r8, r14
0x1800d63b5  lea     rdx, [rsp+0E8h+var_88]
0x1800d63ba  lea     rcx, [rsp+0E8h+var_70]
0x1800d63bf  call    _lambda_2a8f8fa06f2e0b1768a49123f6915af2____lambda_2a8f8fa06f2e0b1768a49123f6915af2_
0x1800d63c4  nop
0x1800d63c5  mov     rdx, rax
0x1800d63c8  lea     rcx, [rsp+0E8h+var_A8]
0x1800d63cd  call    std__thread___Start__lambda_2a8f8fa06f2e0b1768a49123f6915af2___
0x1800d63d2  nop
0x1800d63d3  cmp     dword ptr [rsp+0E8h+var_A8+8], 0
0x1800d63d8  jnz     short loc_1800D63E2
0x1800d63da  mov     ecx, esi
0x1800d63dc  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800d63e2  movaps  xmm0, [rsp+0E8h+var_A8]
0x1800d63e7  movdqa  xmmword ptr [rsp+0E8h+var_48._Hnd], xmm0
0x1800d63f0  lea     rcx, [rsp+0E8h+var_48]; _Thrd_t
0x1800d63f8  call    cs:__imp__Thrd_detach
0x1800d63fe  test    eax, eax
0x1800d6400  jz      short loc_1800D640A
0x1800d6402  mov     ecx, esi
0x1800d6404  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800d640a  xorps   xmm0, xmm0
0x1800d640d  movdqa  [rsp+0E8h+var_A8], xmm0
0x1800d6413  lea     rcx, [rsp+0E8h+var_58]; void *
0x1800d641b  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1800d6420  lea     rcx, [rsp+0E8h+var_70]
0x1800d6425  call    ??1?$shared_ptr@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@std@@QEAA@XZ
0x1800d642a  nop
0x1800d642b  mov     rcx, qword ptr [rsp+0E8h+var_B8]
0x1800d6430  test    rcx, rcx
0x1800d6433  jz      short loc_1800D6442
0x1800d6435  mov     rax, [rcx]
0x1800d6438  mov     rax, [rax+10h]
0x1800d643c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6441  nop
0x1800d6442  mov     rax, [rsp+0E8h+var_88]
0x1800d6447  test    rax, rax
0x1800d644a  jz      short loc_1800D6451
0x1800d644c  mov     rcx, [rax]
0x1800d644f  jmp     short loc_1800D6453
0x1800d6451  xor     ecx, ecx; this
0x1800d6453  or      edx, 0FFFFFFFFh; void *
0x1800d6456  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x1800d645b  lea     rcx, [rsp+0E8h+var_98]
0x1800d6460  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1800d6466  test    al, al
0x1800d6468  jz      short loc_1800D6499
0x1800d646a  xorps   xmm0, xmm0
0x1800d646d  movdqu  [rsp+0E8h+var_A8], xmm0
0x1800d6473  lea     rdx, [rsp+0E8h+var_98]
0x1800d6478  lea     rcx, [rsp+0E8h+var_A8]
0x1800d647d  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800d6483  lea     rax, [rsp+0E8h+var_A8]
0x1800d6488  mov     qword ptr [rsp+0E8h+var_B8], rax
0x1800d648d  lea     rcx, [rsp+0E8h+var_A8]
0x1800d6492  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x1800d6498  nop
0x1800d6499  lea     rcx, [rsp+0E8h+var_98]
0x1800d649e  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800d64a4  jmp     loc_1800D670D
0x1800d64a9  lea     rdi, [r14+0A8h]
0x1800d64b0  mov     rcx, [rdi]
0x1800d64b3  mov     qword ptr [rdi], 0
0x1800d64ba  test    rcx, rcx
0x1800d64bd  jz      short loc_1800D64CC
0x1800d64bf  mov     rax, [rcx]
0x1800d64c2  mov     rax, [rax+10h]
0x1800d64c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d64cb  nop
0x1800d64cc  lea     r9, [rsp+0E8h+var_48]; string
0x1800d64d4  lea     r8, [rsp+0E8h+var_48._Id]; hstringHeader
0x1800d64dc  mov     edx, 39h ; '9'; length
0x1800d64e1  lea     rcx, ?RuntimeClass_Windows_Internal_ApplicationModel_WindowManagement_Window@@3QBGB; "Windows.Internal.ApplicationModel.Windo"...
0x1800d64e8  call    cs:__imp_WindowsCreateStringReference
0x1800d64ee  test    eax, eax
0x1800d64f0  jns     short loc_1800D6505
0x1800d64f2  xor     r9d, r9d; lpArguments
0x1800d64f5  xor     r8d, r8d; nNumberOfArguments
0x1800d64f8  mov     edx, esi; dwExceptionFlags
0x1800d64fa  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800d64ff  call    cs:__imp_RaiseException
0x1800d6505  mov     r8, rdi
0x1800d6508  lea     rdx, _GUID_5e75aba7_c424_4076_9d47_409a1eda087f
0x1800d650f  mov     rcx, [rsp+0E8h+var_48._Hnd]
0x1800d6517  call    cs:__imp_RoGetActivationFactory
0x1800d651d  mov     rcx, [rsp+0E8h]; this
0x1800d6525  test    eax, eax
0x1800d6527  jns     short loc_1800D653D
0x1800d6529  mov     r9d, eax; char *
0x1800d652c  lea     r8, aPcshellTwinuiV_44; "pcshell\\twinui\\viewmanagerinterop\\li"...
0x1800d6533  mov     edx, 7Bh ; '{'; void *
0x1800d6538  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d653d  lea     rbx, [r14+30h]
0x1800d6541  mov     rcx, [rbx]
0x1800d6544  mov     qword ptr [rbx], 0
0x1800d654b  test    rcx, rcx
0x1800d654e  jz      short loc_1800D655D
0x1800d6550  mov     rax, [rcx]
0x1800d6553  mov     rax, [rax+10h]
0x1800d6557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d655c  nop
0x1800d655d  lea     r9, [rsp+0E8h+var_48]; string
0x1800d6565  lea     r8, [rsp+0E8h+var_48._Id]; hstringHeader
0x1800d656d  mov     edx, 44h ; 'D'; length
0x1800d6572  lea     rcx, ?RuntimeClass_Windows_Internal_ApplicationModel_WindowManagement_UniversalAppModel@@3QBGB; "Windows.Internal.ApplicationModel.Windo"...
0x1800d6579  call    cs:__imp_WindowsCreateStringReference
0x1800d657f  test    eax, eax
0x1800d6581  jns     short loc_1800D6596
0x1800d6583  xor     r9d, r9d; lpArguments
0x1800d6586  xor     r8d, r8d; nNumberOfArguments
0x1800d6589  mov     edx, esi; dwExceptionFlags
0x1800d658b  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800d6590  call    cs:__imp_RaiseException
0x1800d6596  mov     r8, rbx
0x1800d6599  lea     rdx, _GUID_b880ce78_2e50_5a73_bfaa_a3f9a8b2f042
0x1800d65a0  mov     rcx, [rsp+0E8h+var_48._Hnd]
0x1800d65a8  call    cs:__imp_RoGetActivationFactory
0x1800d65ae  mov     rcx, [rsp+0E8h]; this
0x1800d65b6  test    eax, eax
0x1800d65b8  jns     short loc_1800D65CE
0x1800d65ba  mov     r9d, eax; char *
0x1800d65bd  lea     r8, aPcshellTwinuiV_44; "pcshell\\twinui\\viewmanagerinterop\\li"...
0x1800d65c4  mov     edx, 7Ch ; '|'; void *
0x1800d65c9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d65ce  mov     rdi, [rdi]
0x1800d65d1  mov     rax, [rdi]
0x1800d65d4  mov     rbx, [rax+30h]
0x1800d65d8  lea     rsi, [r14+0B0h]
0x1800d65df  mov     rcx, rsi
0x1800d65e2  call    ?reset@?$com_ptr_t@UIUwpWindowWrapperInternal@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUwpWindowWrapperInternal,wil::err_exception_policy>::reset(void)
0x1800d65e7  mov     rdx, rsi
0x1800d65ea  mov     rcx, rdi
0x1800d65ed  mov     rax, rbx
0x1800d65f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d65f5  mov     rcx, [rsp+0E8h]; this
0x1800d65fd  test    eax, eax
0x1800d65ff  jns     short loc_1800D6615
0x1800d6601  mov     r9d, eax; char *
0x1800d6604  lea     r8, aPcshellTwinuiV_44; "pcshell\\twinui\\viewmanagerinterop\\li"...
0x1800d660b  mov     edx, 7Eh ; '~'; void *
0x1800d6610  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d6615  lea     rbx, [r14+0B8h]
0x1800d661c  mov     rcx, [rbx]
0x1800d661f  mov     qword ptr [rbx], 0
0x1800d6626  test    rcx, rcx
0x1800d6629  jz      short loc_1800D6638
0x1800d662b  mov     rax, [rcx]
0x1800d662e  mov     rax, [rax+10h]
0x1800d6632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6637  nop
0x1800d6638  mov     rdx, rbx
0x1800d663b  mov     rcx, rsi
0x1800d663e  call    ??$query_to@UIUniversalAppModelWatcher@WindowManagement@ApplicationModel@Internal@Windows@@@?$com_ptr_t@UIWindowWatcher@WindowManagement@ApplicationModel@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEBAXPEAPEAUIUniversalAppModelWatcher@WindowManagement@ApplicationModel@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::ApplicationModel::WindowManagement::IWindowWatcher,wil::err_exception_policy>::query_to<Windows::Internal::ApplicationModel::WindowManagement::IUniversalAppModelWatcher>(Windows::Internal::ApplicationModel::WindowManagement::IUniversalAppModelWatcher * *)
0x1800d6643  lea     rcx, [rsp+0E8h+var_B8]
0x1800d6648  call    ??$GetActivationFactory@UIUwpWindowLifecycleManagerStatics@UwpWindowLifecycleManagement@Shell@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIUwpWindowLifecycleManagerStatics@UwpWindowLifecycleManagement@Shell@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::Shell::UwpWindowLifecycleManagement::IUwpWindowLifecycleManagerStatics>(ushort const *)
0x1800d664d  nop
0x1800d664e  mov     rbx, qword ptr [rsp+0E8h+var_B8]
0x1800d6653  mov     rax, [rbx]
0x1800d6656  mov     rdi, [rax+30h]
0x1800d665a  lea     rsi, [r14+0E8h]
0x1800d6661  mov     rdx, [rsi]
0x1800d6664  mov     qword ptr [rsi], 0
0x1800d666b  test    rdx, rdx
0x1800d666e  jz      short loc_1800D6680
0x1800d6670  mov     rcx, [rdx]
0x1800d6673  mov     rax, [rcx+10h]
0x1800d6677  mov     rcx, rdx
0x1800d667a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d667f  nop
0x1800d6680  mov     rdx, rsi
0x1800d6683  mov     rcx, rbx
0x1800d6686  mov     rax, rdi
0x1800d6689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d668e  mov     rcx, [rsp+0E8h]; this
0x1800d6696  test    eax, eax
0x1800d6698  jns     short loc_1800D66AE
0x1800d669a  mov     r9d, eax; char *
0x1800d669d  lea     r8, aPcshellTwinuiV_44; "pcshell\\twinui\\viewmanagerinterop\\li"...
0x1800d66a4  mov     edx, 82h; void *
0x1800d66a9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d66ae  mov     rsi, [rsi]
0x1800d66b1  mov     rax, [rsi]
0x1800d66b4  mov     rdi, [rax+78h]
0x1800d66b8  lea     rbx, [r14+0F0h]
0x1800d66bf  mov     rcx, rbx
0x1800d66c2  call    ?reset@?$com_ptr_t@UIUwpWindowWrapperInternal@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUwpWindowWrapperInternal,wil::err_exception_policy>::reset(void)
0x1800d66c7  mov     rdx, rbx
0x1800d66ca  mov     rcx, rsi
0x1800d66cd  mov     rax, rdi
0x1800d66d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d66d5  mov     rcx, [rsp+0E8h]; this
0x1800d66dd  test    eax, eax
0x1800d66df  jns     short loc_1800D66F6
0x1800d66e1  mov     r9d, eax; char *
0x1800d66e4  lea     r8, aPcshellTwinuiV_44; "pcshell\\twinui\\viewmanagerinterop\\li"...
0x1800d66eb  mov     edx, 84h; void *
0x1800d66f0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d66f6  mov     rcx, qword ptr [rsp+0E8h+var_B8]
0x1800d66fb  test    rcx, rcx
0x1800d66fe  jz      short loc_1800D670D
0x1800d6700  mov     rax, [rcx]
0x1800d6703  mov     rax, [rax+10h]
0x1800d6707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d670c  nop
0x1800d670d  call    ?IsWindowManagementInProcEnabled@WindowManagement@ApplicationModel@Internal@Windows@@YA_NXZ; Windows::Internal::ApplicationModel::WindowManagement::IsWindowManagementInProcEnabled(void)
0x1800d6712  test    al, al
0x1800d6714  jnz     short loc_1800D673F
0x1800d6716  mov     rcx, r14; this
0x1800d6719  call    ?StartWindowWatcher@UwpWindowManagerBridge@@UEAAJXZ; UwpWindowManagerBridge::StartWindowWatcher(void)
0x1800d671e  mov     rcx, [rsp+0E8h]; this
0x1800d6726  test    eax, eax
0x1800d6728  jns     short loc_1800D673F
0x1800d672a  mov     r9d, eax; char *
0x1800d672d  lea     r8, aPcshellTwinuiV_44; "pcshell\\twinui\\viewmanagerinterop\\li"...
0x1800d6734  mov     edx, 8Bh; void *
0x1800d6739  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d673f  mov     rcx, [rsp+0E8h+var_88+8]; this
0x1800d6744  test    rcx, rcx
0x1800d6747  jz      short loc_1800D674F
0x1800d6749  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d674e  nop
0x1800d674f  jmp     short loc_1800D6765
0x1800d6751  mov     rcx, [rsp+0E8h]; this
0x1800d6759  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800d675f  mov     eax, [rsp+0E8h+var_B8]
0x1800d6763  jmp     short loc_1800D676C
0x1800d6765  call    ?WindowEventDispatcher_ConnectedToWindowManager@ViewManagerInteropTraceLogging@@SAXXZ; ViewManagerInteropTraceLogging::WindowEventDispatcher_ConnectedToWindowManager(void)
0x1800d676a  xor     eax, eax
0x1800d676c  mov     rcx, [rsp+0E8h+var_28]
0x1800d6774  xor     rcx, rsp; StackCookie
0x1800d6777  call    __security_check_cookie
  ... truncated ...
```
