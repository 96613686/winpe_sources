# ShowSmartInstallAppRecommendation(HWND__ *,ushort const *,Windows::Internal::Security::SmartScreen::AppControlEnforcementLevel,bool &)

- ea: `0x180005b0c`
- end: `0x1800060a0`
- name: `?ShowSmartInstallAppRecommendation@@YAJPEAUHWND__@@PEBGW4AppControlEnforcementLevel@SmartScreen@Security@Internal@Windows@@AEA_N@Z`
- size: `1428`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180005914`

## callees

- `0x180005540`
- `0x180005560`
- `0x180005b0c`
- `0x1800065c4`
- `0x1800065e4`
- `0x180006608`
- `0x180006688`
- `0x1800066d0`
- `0x180006750`
- `0x180008320`
- `0x180012420`
- `0x18001a610`
- `0x1800208c0`
- `0x180020960`
- `0x180020a00`
- `0x18002132c`
- `0x180021b00`
- `0x180029010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180005fca`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180005fca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005fac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005fac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005e54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005e54`

## pseudocode

```c
// Hidden C++ exception states: #wind=19 #try_helpers=1
__int64 __fastcall ShowSmartInstallAppRecommendation(__int64 a1, const WCHAR *a2, int a3, _BYTE *a4)
{
  __int64 v8; // rax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64, __int64, __int64); // rbx
  _QWORD *v13; // rax
  __int64 v14; // r9
  int v15; // eax
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, __int64, __int64, HSTRING); // rdi
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rax
  _QWORD *v24; // rcx
  int v25; // eax
  __int64 *v26; // rdi
  __int64 (__fastcall *v27)(__int64 *, HSTRING *); // rsi
  HSTRING v28; // rbx
  int v29; // eax
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, __int64, HSTRING *); // rbx
  int v36; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v38; // r8
  __int64 *v39; // rcx
  int v41; // [rsp+20h] [rbp-E8h]
  char *v42; // [rsp+30h] [rbp-D8h] BYREF
  HSTRING string; // [rsp+38h] [rbp-D0h] BYREF
  int v44[2]; // [rsp+40h] [rbp-C8h] BYREF
  __int64 *v45; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v46; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD *v47; // [rsp+58h] [rbp-B0h] BYREF
  HSTRING v48; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v49; // [rsp+68h] [rbp-A0h] BYREF
  __int64 *v50; // [rsp+70h] [rbp-98h] BYREF
  __int64 v51; // [rsp+78h] [rbp-90h] BYREF
  __int64 *v52; // [rsp+80h] [rbp-88h] BYREF
  __int64 v53; // [rsp+88h] [rbp-80h] BYREF
  __int64 *v54; // [rsp+90h] [rbp-78h] BYREF
  _QWORD v55[4]; // [rsp+98h] [rbp-70h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v57; // [rsp+D0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  *a4 = 0;
  wil::GetActivationFactory<Windows::Services::Store::IStoreContextStatics>(&v54);
  v46 = 0;
  v8 = *v54;
  v46 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v8 + 48))(v54, &v46);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x364,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v9,
      v41);
  wil::com_ptr_t<Windows::Services::Store::IStoreContext,wil::err_exception_policy>::query<IInitializeWithWindow>(
    &v46,
    &v53);
  v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v53 + 24LL))(v53, a1);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x368,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v10,
      v41);
  wil::GetActivationFactory<Windows::Services::Store::IStoreRequestHelperStatics>(&v51);
  BuildRequestString((__int64)v55, a2, a3);
  *(_QWORD *)v44 = 0;
  v11 = v51;
  v12 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v51 + 48LL);
  *(_QWORD *)v44 = 0;
  v13 = v55;
  if ( v55[3] > 7u )
    v13 = (_QWORD *)v55[0];
  v47 = v13;
  v14 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v47) + 24);
  v15 = v12(v11, v46, 23, v14);
  if ( v15 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x37A,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v15,
      (int)v44);
  wil::wait_for_completion<Windows::Services::Store::StoreSendRequestResult *,Microsoft::WRL::ComPtr<Windows::Services::Store::IStoreSendRequestResult>>(
    &v45,
    *(_QWORD *)v44);
  LODWORD(v42) = 0;
  v16 = (*(__int64 (__fastcall **)(__int64 *, char **))(*v45 + 56))(v45, &v42);
  if ( v16 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x380,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v16,
      (int)v44);
  if ( (int)v42 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x384,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v42,
      (int)v44);
  string = 0;
  v17 = *v45;
  string = 0;
  v18 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v17 + 48))(v45, &string);
  if ( v18 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x387,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v18,
      (int)v44);
  v19 = v51;
  v20 = *(__int64 (__fastcall **)(__int64, __int64, __int64, HSTRING))(*(_QWORD *)v51 + 48LL);
  v21 = *(_QWORD *)v44;
  *(_QWORD *)v44 = 0;
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  v22 = v20(v19, v46, 24, string);
  if ( v22 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x392,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v22,
      (int)v44);
  v23 = wil::wait_for_completion<Windows::Services::Store::StoreSendRequestResult *,Microsoft::WRL::ComPtr<Windows::Services::Store::IStoreSendRequestResult>>(
          &v47,
          *(_QWORD *)v44);
  Microsoft::WRL::ComPtr<Windows::Services::Store::IStoreSendRequestResult>::operator=(&v45, v23);
  v24 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v24 + 16LL))(v24);
  }
  v25 = (*(__int64 (__fastcall **)(__int64 *, char **))(*v45 + 56))(v45, &v42);
  if ( v25 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x39A,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v25,
      (int)v44);
  if ( (int)v42 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x39B,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v42,
      (int)v44);
  v26 = v45;
  v27 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*v45 + 48);
  v28 = string;
  if ( string )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v47);
    WindowsDeleteString(v28);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v47);
  }
  string = 0;
  v29 = v27(v26, &string);
  if ( v29 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x39C,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v29,
      (int)v44);
  wil::GetActivationFactory<Windows::Data::Json::IJsonValueStatics>(&v52);
  v50 = 0;
  v30 = *v52;
  v50 = 0;
  v31 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 **))(v30 + 48))(v52, string, &v50);
  if ( v31 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3A7,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v31,
      (int)v44);
  v49 = 0;
  v32 = *v50;
  v49 = 0;
  v33 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v32 + 96))(v50, &v49);
  if ( v33 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3AB,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v33,
      (int)v44);
  v48 = 0;
  v34 = v49;
  v35 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v49 + 80LL);
  v48 = 0;
  v57 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"status", 7u, 6u);
  v36 = v35(v34, v57, &v48);
  if ( v36 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3AF,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v36,
      (int)v44);
  StringRawBuffer = WindowsGetStringRawBuffer(v48, 0);
  v38 = -1;
  do
    ++v38;
  while ( StringRawBuffer[v38] );
  if ( !(unsigned int)_o__wcsnicmp(StringRawBuffer, L"success") )
    *a4 = 1;
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v48);
  wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(&v49);
  wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(&v50);
  wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(&v52);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
  v39 = v45;
  if ( v45 )
  {
    v45 = 0;
    (*(void (__fastcall **)(__int64 *))(*v39 + 16))(v39);
  }
  wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(v44);
  std::wstring::_Tidy_deallocate(v55);
  wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(&v51);
  wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(&v53);
  wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(&v46);
  wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(&v54);
  return 0;
}

```

## disassembly

```asm
0x180005b0c  mov     r11, rsp
0x180005b0f  push    rbx
0x180005b10  push    rsi
0x180005b11  push    rdi
0x180005b12  push    r14
0x180005b14  push    r15
0x180005b16  sub     rsp, 0E0h
0x180005b1d  mov     rax, cs:__security_cookie
0x180005b24  xor     rax, rsp
0x180005b27  mov     [rsp+108h+var_30], rax
0x180005b2f  mov     r14, r9
0x180005b32  mov     ebx, r8d
0x180005b35  mov     rdi, rdx
0x180005b38  mov     rsi, rcx
0x180005b3b  xor     r15d, r15d
0x180005b3e  mov     [r9], r15b
0x180005b41  lea     rcx, [r11-78h]
0x180005b45  call    ??$GetActivationFactory@UIStoreContextStatics@Store@Services@Windows@@@wil@@YA?AV?$com_ptr_t@UIStoreContextStatics@Store@Services@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Services::Store::IStoreContextStatics>(ushort const *)
0x180005b4a  nop
0x180005b4b  mov     [rsp+108h+var_B8], r15
0x180005b50  mov     rcx, [rsp+108h+var_78]
0x180005b58  mov     rax, [rcx]
0x180005b5b  mov     [rsp+108h+var_B8], r15
0x180005b60  lea     rdx, [rsp+108h+var_B8]
0x180005b65  mov     rax, [rax+30h]
0x180005b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b6e  mov     rcx, [rsp+108h]; this
0x180005b76  test    eax, eax
0x180005b78  jns     short loc_180005B8E
0x180005b7a  mov     r9d, eax; char *
0x180005b7d  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180005b84  mov     edx, 364h; void *
0x180005b89  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005b8e  lea     rdx, [rsp+108h+var_80]
0x180005b96  lea     rcx, [rsp+108h+var_B8]
0x180005b9b  call    ??$query@UIInitializeWithWindow@@@?$com_ptr_t@UIStoreContext@Store@Services@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIInitializeWithWindow@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Services::Store::IStoreContext,wil::err_exception_policy>::query<IInitializeWithWindow>(void)
0x180005ba0  nop
0x180005ba1  mov     rcx, [rsp+108h+var_80]
0x180005ba9  mov     rax, [rcx]
0x180005bac  mov     rdx, rsi
0x180005baf  mov     rax, [rax+18h]
0x180005bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bb8  mov     rcx, [rsp+108h]; this
0x180005bc0  test    eax, eax
0x180005bc2  jns     short loc_180005BD8
0x180005bc4  mov     r9d, eax; char *
0x180005bc7  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180005bce  mov     edx, 368h; void *
0x180005bd3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005bd8  lea     rcx, [rsp+108h+var_90]
0x180005bdd  call    ??$GetActivationFactory@UIStoreRequestHelperStatics@Store@Services@Windows@@@wil@@YA?AV?$com_ptr_t@UIStoreRequestHelperStatics@Store@Services@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Services::Store::IStoreRequestHelperStatics>(ushort const *)
0x180005be2  nop
0x180005be3  mov     r8d, ebx
0x180005be6  mov     rdx, rdi
0x180005be9  lea     rcx, [rsp+108h+var_70]
0x180005bf1  call    ?BuildRequestString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGW4AppControlEnforcementLevel@SmartScreen@Security@Internal@Windows@@@Z; BuildRequestString(ushort const *,Windows::Internal::Security::SmartScreen::AppControlEnforcementLevel)
0x180005bf6  nop
0x180005bf7  mov     qword ptr [rsp+108h+var_C8], r15
0x180005bfc  mov     rdi, [rsp+108h+var_90]
0x180005c01  mov     rax, [rdi]
0x180005c04  mov     rbx, [rax+30h]
0x180005c08  mov     qword ptr [rsp+108h+var_C8], r15
0x180005c0d  lea     rax, [rsp+108h+var_70]
0x180005c15  cmp     [rsp+108h+var_58], 7
0x180005c1e  cmova   rax, [rsp+108h+var_70]
0x180005c27  mov     [rsp+108h+var_B0], rax
0x180005c2c  lea     rdx, [rsp+108h+var_B0]
0x180005c31  lea     rcx, [rsp+108h+hstringHeader]
0x180005c39  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180005c3e  nop
0x180005c3f  lea     rcx, [rsp+108h+var_C8]
0x180005c44  mov     qword ptr [rsp+108h+var_E8], rcx; int
0x180005c49  mov     r9, [rax+18h]
0x180005c4d  mov     r8d, 17h
0x180005c53  mov     rdx, [rsp+108h+var_B8]
0x180005c58  mov     rcx, rdi
0x180005c5b  mov     rax, rbx
0x180005c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c63  mov     rcx, [rsp+108h]; this
0x180005c6b  test    eax, eax
0x180005c6d  jns     short loc_180005C84
0x180005c6f  mov     r9d, eax; char *
0x180005c72  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180005c79  mov     edx, 37Ah; void *
0x180005c7e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005c84  mov     rdx, qword ptr [rsp+108h+var_C8]
0x180005c89  lea     rcx, [rsp+108h+var_C0]
0x180005c8e  call    ??$wait_for_completion@PEAVStoreSendRequestResult@Store@Services@Windows@@V?$ComPtr@UIStoreSendRequestResult@Store@Services@Windows@@@WRL@Microsoft@@@wil@@YA?AV?$ComPtr@UIStoreSendRequestResult@Store@Services@Windows@@@WRL@Microsoft@@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@@Z; wil::wait_for_completion<Windows::Services::Store::StoreSendRequestResult *,Microsoft::WRL::ComPtr<Windows::Services::Store::IStoreSendRequestResult>>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS)
0x180005c93  nop
0x180005c94  mov     dword ptr [rsp+108h+var_D8], r15d
0x180005c99  mov     rcx, [rsp+108h+var_C0]
0x180005c9e  mov     rax, [rcx]
0x180005ca1  lea     rdx, [rsp+108h+var_D8]
0x180005ca6  mov     rax, [rax+38h]
0x180005caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005caf  mov     rcx, [rsp+108h]; this
0x180005cb7  test    eax, eax
0x180005cb9  jns     short loc_180005CCF
0x180005cbb  mov     r9d, eax; char *
0x180005cbe  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180005cc5  mov     edx, 380h; void *
0x180005cca  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005ccf  mov     r9d, dword ptr [rsp+108h+var_D8]; char *
0x180005cd4  mov     rcx, [rsp+108h]; this
0x180005cdc  test    r9d, r9d
0x180005cdf  jns     short loc_180005CF2
0x180005ce1  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180005ce8  mov     edx, 384h; void *
0x180005ced  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005cf2  mov     [rsp+108h+string], r15
0x180005cf7  mov     rcx, [rsp+108h+var_C0]
0x180005cfc  mov     rax, [rcx]
0x180005cff  mov     [rsp+108h+string], r15
0x180005d04  lea     rdx, [rsp+108h+string]
0x180005d09  mov     rax, [rax+30h]
0x180005d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d12  mov     rcx, [rsp+108h]; this
0x180005d1a  test    eax, eax
0x180005d1c  jns     short loc_180005D32
0x180005d1e  mov     r9d, eax; char *
0x180005d21  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180005d28  mov     edx, 387h; void *
0x180005d2d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005d32  mov     rbx, [rsp+108h+var_90]
0x180005d37  mov     rax, [rbx]
0x180005d3a  mov     rdi, [rax+30h]
0x180005d3e  mov     rcx, qword ptr [rsp+108h+var_C8]
0x180005d43  mov     qword ptr [rsp+108h+var_C8], r15
0x180005d48  test    rcx, rcx
0x180005d4b  jz      short loc_180005D5A
0x180005d4d  mov     rax, [rcx]
0x180005d50  mov     rax, [rax+10h]
0x180005d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d59  nop
0x180005d5a  lea     rax, [rsp+108h+var_C8]
0x180005d5f  mov     qword ptr [rsp+108h+var_E8], rax; int
0x180005d64  mov     r9, [rsp+108h+string]
0x180005d69  mov     r8d, 18h
0x180005d6f  mov     rdx, [rsp+108h+var_B8]
0x180005d74  mov     rcx, rbx
0x180005d77  mov     rax, rdi
0x180005d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d7f  mov     rcx, [rsp+108h]; this
0x180005d87  test    eax, eax
0x180005d89  jns     short loc_180005D9F
0x180005d8b  mov     r9d, eax; char *
0x180005d8e  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180005d95  mov     edx, 392h; void *
0x180005d9a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005d9f  mov     rdx, qword ptr [rsp+108h+var_C8]
0x180005da4  lea     rcx, [rsp+108h+var_B0]
0x180005da9  call    ??$wait_for_completion@PEAVStoreSendRequestResult@Store@Services@Windows@@V?$ComPtr@UIStoreSendRequestResult@Store@Services@Windows@@@WRL@Microsoft@@@wil@@YA?AV?$ComPtr@UIStoreSendRequestResult@Store@Services@Windows@@@WRL@Microsoft@@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@@Z; wil::wait_for_completion<Windows::Services::Store::StoreSendRequestResult *,Microsoft::WRL::ComPtr<Windows::Services::Store::IStoreSendRequestResult>>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS)
0x180005dae  mov     rdx, rax
0x180005db1  lea     rcx, [rsp+108h+var_C0]
0x180005db6  call    ??4?$ComPtr@UIStoreSendRequestResult@Store@Services@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::Services::Store::IStoreSendRequestResult>::operator=(Microsoft::WRL::ComPtr<Windows::Services::Store::IStoreSendRequestResult> &&)
0x180005dbb  nop
0x180005dbc  mov     rcx, [rsp+108h+var_B0]
0x180005dc1  test    rcx, rcx
0x180005dc4  jz      short loc_180005DD8
0x180005dc6  mov     [rsp+108h+var_B0], r15
0x180005dcb  mov     rax, [rcx]
0x180005dce  mov     rax, [rax+10h]
0x180005dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dd7  nop
0x180005dd8  mov     rcx, [rsp+108h+var_C0]
0x180005ddd  mov     rax, [rcx]
0x180005de0  lea     rdx, [rsp+108h+var_D8]
0x180005de5  mov     rax, [rax+38h]
0x180005de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dee  mov     rcx, [rsp+108h]; this
0x180005df6  test    eax, eax
0x180005df8  jns     short loc_180005E0E
0x180005dfa  mov     r9d, eax; char *
0x180005dfd  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180005e04  mov     edx, 39Ah; void *
0x180005e09  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005e0e  mov     r9d, dword ptr [rsp+108h+var_D8]; char *
0x180005e13  mov     rcx, [rsp+108h]; this
0x180005e1b  test    r9d, r9d
0x180005e1e  jns     short loc_180005E31
0x180005e20  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180005e27  mov     edx, 39Bh; void *
0x180005e2c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005e31  mov     rdi, [rsp+108h+var_C0]
0x180005e36  mov     rax, [rdi]
0x180005e39  mov     rsi, [rax+30h]
0x180005e3d  mov     rbx, [rsp+108h+string]
0x180005e42  test    rbx, rbx
0x180005e45  jz      short loc_180005E64
0x180005e47  lea     rcx, [rsp+108h+var_B0]; this
0x180005e4c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180005e51  mov     rcx, rbx; string
0x180005e54  call    cs:__imp_WindowsDeleteString
0x180005e5a  lea     rcx, [rsp+108h+var_B0]; this
0x180005e5f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180005e64  mov     [rsp+108h+string], r15
0x180005e69  lea     rdx, [rsp+108h+string]
0x180005e6e  mov     rcx, rdi
0x180005e71  mov     rax, rsi
0x180005e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e79  mov     rcx, [rsp+108h]; this
0x180005e81  test    eax, eax
0x180005e83  jns     short loc_180005E99
0x180005e85  mov     r9d, eax; char *
0x180005e88  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180005e8f  mov     edx, 39Ch; void *
0x180005e94  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005e99  lea     rcx, [rsp+108h+var_88]
0x180005ea1  call    ??$GetActivationFactory@UIJsonValueStatics@Json@Data@Windows@@@wil@@YA?AV?$com_ptr_t@UIJsonValueStatics@Json@Data@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Data::Json::IJsonValueStatics>(ushort const *)
0x180005ea6  nop
0x180005ea7  mov     [rsp+108h+var_98], r15
0x180005eac  mov     rcx, [rsp+108h+var_88]
0x180005eb4  mov     rax, [rcx]
0x180005eb7  mov     [rsp+108h+var_98], r15
0x180005ebc  lea     r8, [rsp+108h+var_98]
0x180005ec1  mov     rdx, [rsp+108h+string]
0x180005ec6  mov     rax, [rax+30h]
0x180005eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ecf  mov     rcx, [rsp+108h]; this
0x180005ed7  test    eax, eax
0x180005ed9  jns     short loc_180005EEF
0x180005edb  mov     r9d, eax; char *
0x180005ede  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180005ee5  mov     edx, 3A7h; void *
0x180005eea  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005eef  mov     [rsp+108h+var_A0], r15
0x180005ef4  mov     rcx, [rsp+108h+var_98]
0x180005ef9  mov     rax, [rcx]
0x180005efc  mov     [rsp+108h+var_A0], r15
0x180005f01  lea     rdx, [rsp+108h+var_A0]
0x180005f06  mov     rax, [rax+60h]
0x180005f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f0f  mov     rcx, [rsp+108h]; this
0x180005f17  test    eax, eax
0x180005f19  jns     short loc_180005F2F
0x180005f1b  mov     r9d, eax; char *
0x180005f1e  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180005f25  mov     edx, 3ABh; void *
0x180005f2a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005f2f  mov     [rsp+108h+var_A8], r15
0x180005f34  mov     rdi, [rsp+108h+var_A0]
0x180005f39  mov     rax, [rdi]
0x180005f3c  mov     rbx, [rax+50h]
0x180005f40  mov     [rsp+108h+var_A8], r15
0x180005f45  mov     [rsp+108h+var_38], r15
0x180005f4d  mov     r9d, 6; unsigned int
0x180005f53  lea     r8d, [r9+1]; unsigned int
0x180005f57  lea     rdx, sourceString; "status"
0x180005f5e  lea     rcx, [rsp+108h+hstringHeader]; hstringHeader
0x180005f66  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180005f6b  nop
0x180005f6c  lea     r8, [rsp+108h+var_A8]
0x180005f71  mov     rdx, [rsp+108h+var_38]
0x180005f79  mov     rcx, rdi
0x180005f7c  mov     rax, rbx
0x180005f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f84  mov     rcx, [rsp+108h]; this
0x180005f8c  test    eax, eax
0x180005f8e  jns     short loc_180005FA5
0x180005f90  mov     r9d, eax; char *
0x180005f93  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180005f9a  mov     edx, 3AFh; void *
0x180005f9f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005fa5  xor     edx, edx; length
0x180005fa7  mov     rcx, [rsp+108h+var_A8]; string
0x180005fac  call    cs:__imp_WindowsGetStringRawBuffer
0x180005fb2  or      r8, 0FFFFFFFFFFFFFFFFh
0x180005fb6  inc     r8
0x180005fb9  cmp     [rax+r8*2], r15w
0x180005fbe  jnz     short loc_180005FB6
0x180005fc0  lea     rdx, aSuccess; "success"
0x180005fc7  mov     rcx, rax
0x180005fca  call    cs:__imp__o__wcsnicmp
0x180005fd0  test    eax, eax
0x180005fd2  jnz     short loc_180005FD8
0x180005fd4  mov     byte ptr [r14], 1
0x180005fd8  lea     rcx, [rsp+108h+var_A8]
0x180005fdd  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180005fe2  nop
0x180005fe3  lea     rcx, [rsp+108h+var_A0]
0x180005fe8  call    ??1?$com_ptr_t@UIStoreRequestHelperStatics@Store@Services@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(void)
0x180005fed  nop
0x180005fee  lea     rcx, [rsp+108h+var_98]
0x180005ff3  call    ??1?$com_ptr_t@UIStoreRequestHelperStatics@Store@Services@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(void)
0x180005ff8  nop
0x180005ff9  lea     rcx, [rsp+108h+var_88]
0x180006001  call    ??1?$com_ptr_t@UIStoreRequestHelperStatics@Store@Services@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(void)
0x180006006  nop
0x180006007  lea     rcx, [rsp+108h+string]
0x18000600c  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180006011  nop
0x180006012  mov     rcx, [rsp+108h+var_C0]
0x180006017  test    rcx, rcx
0x18000601a  jz      short loc_18000602E
0x18000601c  mov     [rsp+108h+var_C0], r15
0x180006021  mov     rax, [rcx]
0x180006024  mov     rax, [rax+10h]
0x180006028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000602d  nop
0x18000602e  lea     rcx, [rsp+108h+var_C8]
  ... truncated ...
```
