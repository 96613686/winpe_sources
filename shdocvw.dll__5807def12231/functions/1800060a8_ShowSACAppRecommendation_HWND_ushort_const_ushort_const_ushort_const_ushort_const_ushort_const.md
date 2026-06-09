# ShowSACAppRecommendation(HWND__ *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800060a8`
- end: `0x1800065be`
- name: `?ShowSACAppRecommendation@@YA_NPEAUHWND__@@PEBG1111@Z`
- size: `1302`
- prototype: `bool __fastcall(HWND, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001d900`

## callees

- `0x180005540`
- `0x180005560`
- `0x1800060a8`
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
- `0x180021e84`
- `0x180029010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800064f0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006507`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800064f0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006507`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800064dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800064dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800063b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800063b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
char __fastcall ShowSACAppRecommendation(
        HWND a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6)
{
  int v9; // eax
  int v10; // eax
  __int64 v11; // r8
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64, __int64, _QWORD); // rbx
  _QWORD *v14; // rax
  __int64 v15; // rax
  int v16; // eax
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rbx
  __int64 (__fastcall *v21)(__int64, __int64, __int64, HSTRING); // rdi
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rax
  _QWORD *v25; // rcx
  int v26; // eax
  __int64 *v27; // rdi
  __int64 (__fastcall *v28)(__int64 *, HSTRING *); // rsi
  HSTRING v29; // rbx
  int v30; // eax
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rax
  int v34; // eax
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, __int64, HSTRING *); // rbx
  int v37; // eax
  PCWSTR StringRawBuffer; // rdi
  char v39; // bl
  __int64 *v40; // rcx
  int v42; // [rsp+20h] [rbp-A9h]
  char *v43; // [rsp+30h] [rbp-99h] BYREF
  HSTRING string; // [rsp+38h] [rbp-91h] BYREF
  int v45[2]; // [rsp+40h] [rbp-89h] BYREF
  __int64 *v46; // [rsp+48h] [rbp-81h] BYREF
  __int64 v47; // [rsp+50h] [rbp-79h] BYREF
  _QWORD *v48; // [rsp+58h] [rbp-71h] BYREF
  HSTRING v49; // [rsp+60h] [rbp-69h] BYREF
  __int64 v50; // [rsp+68h] [rbp-61h] BYREF
  __int64 *v51; // [rsp+70h] [rbp-59h] BYREF
  __int64 v52; // [rsp+78h] [rbp-51h] BYREF
  __int64 *v53; // [rsp+80h] [rbp-49h] BYREF
  __int64 v54; // [rsp+88h] [rbp-41h] BYREF
  __int64 v55; // [rsp+90h] [rbp-39h] BYREF
  _QWORD v56[4]; // [rsp+98h] [rbp-31h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-11h] BYREF
  __int64 v58; // [rsp+D0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+4Fh]

  wil::GetActivationFactory<Windows::Services::Store::IStoreContextStatics>(&v55);
  v47 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v55 + 48LL))(v55, &v47);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3CD,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v9,
      v42);
  wil::com_ptr_t<Windows::Services::Store::IStoreContext,wil::err_exception_policy>::query<IInitializeWithWindow>(
    &v47,
    &v54);
  v10 = (*(__int64 (__fastcall **)(__int64, HWND))(*(_QWORD *)v54 + 24LL))(v54, a1);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3D1,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v10,
      v42);
  wil::GetActivationFactory<Windows::Services::Store::IStoreRequestHelperStatics>(&v52);
  BuildRequestStringForSAC((__int64)v56, a2, v11, (__int64)a4, (__int64)a5, (__int64)a6);
  *(_QWORD *)v45 = 0;
  v12 = v52;
  v13 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v52 + 48LL);
  *(_QWORD *)v45 = 0;
  v14 = v56;
  if ( v56[3] > 7u )
    v14 = (_QWORD *)v56[0];
  v48 = v14;
  v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v48);
  v16 = v13(v12, v47, 33, *(_QWORD *)(v15 + 24));
  if ( v16 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3DE,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v16,
      (int)v45);
  wil::wait_for_completion<Windows::Services::Store::StoreSendRequestResult *,Microsoft::WRL::ComPtr<Windows::Services::Store::IStoreSendRequestResult>>(
    &v46,
    *(_QWORD *)v45);
  LODWORD(v43) = 0;
  v17 = (*(__int64 (__fastcall **)(__int64 *, char **))(*v46 + 56))(v46, &v43);
  if ( v17 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3E2,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v17,
      (int)v45);
  if ( (int)v43 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3E5,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v43,
      (int)v45);
  string = 0;
  v18 = *v46;
  string = 0;
  v19 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v18 + 48))(v46, &string);
  if ( v19 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3E8,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v19,
      (int)v45);
  v20 = v52;
  v21 = *(__int64 (__fastcall **)(__int64, __int64, __int64, HSTRING))(*(_QWORD *)v52 + 48LL);
  v22 = *(_QWORD *)v45;
  *(_QWORD *)v45 = 0;
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  v23 = v21(v20, v47, 34, string);
  if ( v23 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3F0,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v23,
      (int)v45);
  v24 = wil::wait_for_completion<Windows::Services::Store::StoreSendRequestResult *,Microsoft::WRL::ComPtr<Windows::Services::Store::IStoreSendRequestResult>>(
          &v48,
          *(_QWORD *)v45);
  Microsoft::WRL::ComPtr<Windows::Services::Store::IStoreSendRequestResult>::operator=(&v46, v24);
  v25 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v25 + 16LL))(v25);
  }
  v26 = (*(__int64 (__fastcall **)(__int64 *, char **))(*v46 + 56))(v46, &v43);
  if ( v26 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3F4,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v26,
      (int)v45);
  if ( (int)v43 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3F5,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v43,
      (int)v45);
  v27 = v46;
  v28 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*v46 + 48);
  v29 = string;
  if ( string )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v48);
    WindowsDeleteString(v29);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v48);
  }
  string = 0;
  v30 = v28(v27, &string);
  if ( v30 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3F6,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v30,
      (int)v45);
  wil::GetActivationFactory<Windows::Data::Json::IJsonValueStatics>(&v53);
  v51 = 0;
  v31 = *v53;
  v51 = 0;
  v32 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 **))(v31 + 48))(v53, string, &v51);
  if ( v32 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3FB,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v32,
      (int)v45);
  v50 = 0;
  v33 = *v51;
  v50 = 0;
  v34 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v33 + 96))(v51, &v50);
  if ( v34 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3FE,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v34,
      (int)v45);
  v49 = 0;
  v35 = v50;
  v36 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v50 + 80LL);
  v49 = 0;
  v58 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"status", 7u, 6u);
  v37 = v36(v35, v58, &v49);
  if ( v37 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x401,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v37,
      (int)v45);
  StringRawBuffer = WindowsGetStringRawBuffer(v49, 0);
  if ( !(unsigned int)_o__wcsicmp(StringRawBuffer, L"success")
    || (v39 = 0, !(unsigned int)_o__wcsicmp(StringRawBuffer, L"cancelled")) )
  {
    v39 = 1;
  }
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v49);
  wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(&v50);
  wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(&v51);
  wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(&v53);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
  v40 = v46;
  if ( v46 )
  {
    v46 = 0;
    (*(void (__fastcall **)(__int64 *))(*v40 + 16))(v40);
  }
  wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(v45);
  std::wstring::_Tidy_deallocate(v56);
  wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(&v52);
  wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(&v54);
  wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(&v47);
  wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(&v55);
  return v39;
}

```

## disassembly

```asm
0x1800060a8  push    rbp
0x1800060aa  push    rbx
0x1800060ab  push    rsi
0x1800060ac  push    rdi
0x1800060ad  push    r12
0x1800060af  push    r14
0x1800060b1  push    r15
0x1800060b3  lea     rbp, [rsp-17h]
0x1800060b8  sub     rsp, 0E0h
0x1800060bf  mov     rax, cs:__security_cookie
0x1800060c6  xor     rax, rsp
0x1800060c9  mov     [rbp+47h+var_38], rax
0x1800060cd  mov     rsi, r9
0x1800060d0  mov     rdi, rdx
0x1800060d3  mov     rbx, rcx
0x1800060d6  mov     r14, [rbp+47h+arg_20]
0x1800060da  mov     r15, [rbp+47h+arg_28]
0x1800060de  lea     rcx, [rbp+47h+var_80]
0x1800060e2  call    ??$GetActivationFactory@UIStoreContextStatics@Store@Services@Windows@@@wil@@YA?AV?$com_ptr_t@UIStoreContextStatics@Store@Services@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Services::Store::IStoreContextStatics>(ushort const *)
0x1800060e7  nop
0x1800060e8  xor     r12d, r12d
0x1800060eb  mov     [rbp+47h+var_C0], r12
0x1800060ef  mov     rcx, [rbp+47h+var_80]
0x1800060f3  mov     rax, [rcx]
0x1800060f6  mov     [rbp+47h+var_C0], r12
0x1800060fa  lea     rdx, [rbp+47h+var_C0]
0x1800060fe  mov     rax, [rax+30h]
0x180006102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006107  mov     rcx, [rbp+4Fh]; this
0x18000610b  test    eax, eax
0x18000610d  jns     short loc_180006124
0x18000610f  mov     r9d, eax; char *
0x180006112  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180006119  mov     edx, 3CDh; void *
0x18000611e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180006124  lea     rdx, [rbp+47h+var_88]
0x180006128  lea     rcx, [rbp+47h+var_C0]
0x18000612c  call    ??$query@UIInitializeWithWindow@@@?$com_ptr_t@UIStoreContext@Store@Services@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIInitializeWithWindow@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Services::Store::IStoreContext,wil::err_exception_policy>::query<IInitializeWithWindow>(void)
0x180006131  nop
0x180006132  mov     rcx, [rbp+47h+var_88]
0x180006136  mov     rax, [rcx]
0x180006139  mov     rdx, rbx
0x18000613c  mov     rax, [rax+18h]
0x180006140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006145  mov     rcx, [rbp+4Fh]; this
0x180006149  test    eax, eax
0x18000614b  jns     short loc_180006162
0x18000614d  mov     r9d, eax; char *
0x180006150  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180006157  mov     edx, 3D1h; void *
0x18000615c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180006162  lea     rcx, [rbp+47h+var_98]
0x180006166  call    ??$GetActivationFactory@UIStoreRequestHelperStatics@Store@Services@Windows@@@wil@@YA?AV?$com_ptr_t@UIStoreRequestHelperStatics@Store@Services@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Services::Store::IStoreRequestHelperStatics>(ushort const *)
0x18000616b  nop
0x18000616c  mov     [rsp+110h+var_E8], r15
0x180006171  mov     qword ptr [rsp+110h+var_F0], r14
0x180006176  mov     r9, rsi
0x180006179  mov     rdx, rdi
0x18000617c  lea     rcx, [rbp+47h+var_78]
0x180006180  call    ?BuildRequestStringForSAC@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0000@Z; BuildRequestStringForSAC(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180006185  nop
0x180006186  mov     qword ptr [rsp+110h+var_D0], r12
0x18000618b  mov     rdi, [rbp+47h+var_98]
0x18000618f  mov     rax, [rdi]
0x180006192  mov     rbx, [rax+30h]
0x180006196  mov     qword ptr [rsp+110h+var_D0], r12
0x18000619b  lea     rax, [rbp+47h+var_78]
0x18000619f  cmp     [rbp+47h+var_60], 7
0x1800061a4  cmova   rax, [rbp+47h+var_78]
0x1800061a9  mov     [rbp+47h+var_B8], rax
0x1800061ad  lea     rdx, [rbp+47h+var_B8]
0x1800061b1  lea     rcx, [rbp+47h+hstringHeader]
0x1800061b5  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800061ba  nop
0x1800061bb  lea     rcx, [rsp+110h+var_D0]
0x1800061c0  mov     qword ptr [rsp+110h+var_F0], rcx; int
0x1800061c5  mov     r9, [rax+18h]
0x1800061c9  mov     r8d, 21h ; '!'
0x1800061cf  mov     rdx, [rbp+47h+var_C0]
0x1800061d3  mov     rcx, rdi
0x1800061d6  mov     rax, rbx
0x1800061d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061de  mov     rcx, [rbp+4Fh]; this
0x1800061e2  test    eax, eax
0x1800061e4  jns     short loc_1800061FB
0x1800061e6  mov     r9d, eax; char *
0x1800061e9  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x1800061f0  mov     edx, 3DEh; void *
0x1800061f5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800061fb  mov     rdx, qword ptr [rsp+110h+var_D0]
0x180006200  lea     rcx, [rsp+110h+var_C8]
0x180006205  call    ??$wait_for_completion@PEAVStoreSendRequestResult@Store@Services@Windows@@V?$ComPtr@UIStoreSendRequestResult@Store@Services@Windows@@@WRL@Microsoft@@@wil@@YA?AV?$ComPtr@UIStoreSendRequestResult@Store@Services@Windows@@@WRL@Microsoft@@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@@Z; wil::wait_for_completion<Windows::Services::Store::StoreSendRequestResult *,Microsoft::WRL::ComPtr<Windows::Services::Store::IStoreSendRequestResult>>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS)
0x18000620a  nop
0x18000620b  mov     dword ptr [rsp+110h+var_E0], r12d
0x180006210  mov     rcx, [rsp+110h+var_C8]
0x180006215  mov     rax, [rcx]
0x180006218  lea     rdx, [rsp+110h+var_E0]
0x18000621d  mov     rax, [rax+38h]
0x180006221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006226  mov     rcx, [rbp+4Fh]; this
0x18000622a  test    eax, eax
0x18000622c  jns     short loc_180006243
0x18000622e  mov     r9d, eax; char *
0x180006231  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180006238  mov     edx, 3E2h; void *
0x18000623d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180006243  mov     r9d, dword ptr [rsp+110h+var_E0]; char *
0x180006248  mov     rcx, [rbp+4Fh]; this
0x18000624c  test    r9d, r9d
0x18000624f  jns     short loc_180006263
0x180006251  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180006258  mov     edx, 3E5h; void *
0x18000625d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180006263  mov     [rsp+110h+string], r12
0x180006268  mov     rcx, [rsp+110h+var_C8]
0x18000626d  mov     rax, [rcx]
0x180006270  mov     [rsp+110h+string], r12
0x180006275  lea     rdx, [rsp+110h+string]
0x18000627a  mov     rax, [rax+30h]
0x18000627e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006283  mov     rcx, [rbp+4Fh]; this
0x180006287  test    eax, eax
0x180006289  jns     short loc_1800062A0
0x18000628b  mov     r9d, eax; char *
0x18000628e  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180006295  mov     edx, 3E8h; void *
0x18000629a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800062a0  mov     rbx, [rbp+47h+var_98]
0x1800062a4  mov     rax, [rbx]
0x1800062a7  mov     rdi, [rax+30h]
0x1800062ab  mov     rcx, qword ptr [rsp+110h+var_D0]
0x1800062b0  mov     qword ptr [rsp+110h+var_D0], r12
0x1800062b5  test    rcx, rcx
0x1800062b8  jz      short loc_1800062C7
0x1800062ba  mov     rax, [rcx]
0x1800062bd  mov     rax, [rax+10h]
0x1800062c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062c6  nop
0x1800062c7  lea     rax, [rsp+110h+var_D0]
0x1800062cc  mov     qword ptr [rsp+110h+var_F0], rax; int
0x1800062d1  mov     r9, [rsp+110h+string]
0x1800062d6  mov     r8d, 22h ; '"'
0x1800062dc  mov     rdx, [rbp+47h+var_C0]
0x1800062e0  mov     rcx, rbx
0x1800062e3  mov     rax, rdi
0x1800062e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062eb  mov     rcx, [rbp+4Fh]; this
0x1800062ef  test    eax, eax
0x1800062f1  jns     short loc_180006308
0x1800062f3  mov     r9d, eax; char *
0x1800062f6  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x1800062fd  mov     edx, 3F0h; void *
0x180006302  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180006308  mov     rdx, qword ptr [rsp+110h+var_D0]
0x18000630d  lea     rcx, [rbp+47h+var_B8]
0x180006311  call    ??$wait_for_completion@PEAVStoreSendRequestResult@Store@Services@Windows@@V?$ComPtr@UIStoreSendRequestResult@Store@Services@Windows@@@WRL@Microsoft@@@wil@@YA?AV?$ComPtr@UIStoreSendRequestResult@Store@Services@Windows@@@WRL@Microsoft@@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@@Z; wil::wait_for_completion<Windows::Services::Store::StoreSendRequestResult *,Microsoft::WRL::ComPtr<Windows::Services::Store::IStoreSendRequestResult>>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS)
0x180006316  mov     rdx, rax
0x180006319  lea     rcx, [rsp+110h+var_C8]
0x18000631e  call    ??4?$ComPtr@UIStoreSendRequestResult@Store@Services@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::Services::Store::IStoreSendRequestResult>::operator=(Microsoft::WRL::ComPtr<Windows::Services::Store::IStoreSendRequestResult> &&)
0x180006323  nop
0x180006324  mov     rcx, [rbp+47h+var_B8]
0x180006328  test    rcx, rcx
0x18000632b  jz      short loc_18000633E
0x18000632d  mov     [rbp+47h+var_B8], r12
0x180006331  mov     rax, [rcx]
0x180006334  mov     rax, [rax+10h]
0x180006338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000633d  nop
0x18000633e  mov     rcx, [rsp+110h+var_C8]
0x180006343  mov     rax, [rcx]
0x180006346  lea     rdx, [rsp+110h+var_E0]
0x18000634b  mov     rax, [rax+38h]
0x18000634f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006354  mov     rcx, [rbp+4Fh]; this
0x180006358  test    eax, eax
0x18000635a  jns     short loc_180006371
0x18000635c  mov     r9d, eax; char *
0x18000635f  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180006366  mov     edx, 3F4h; void *
0x18000636b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180006371  mov     r9d, dword ptr [rsp+110h+var_E0]; char *
0x180006376  mov     rcx, [rbp+4Fh]; this
0x18000637a  test    r9d, r9d
0x18000637d  jns     short loc_180006391
0x18000637f  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180006386  mov     edx, 3F5h; void *
0x18000638b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180006391  mov     rdi, [rsp+110h+var_C8]
0x180006396  mov     rax, [rdi]
0x180006399  mov     rsi, [rax+30h]
0x18000639d  mov     rbx, [rsp+110h+string]
0x1800063a2  test    rbx, rbx
0x1800063a5  jz      short loc_1800063C2
0x1800063a7  lea     rcx, [rbp+47h+var_B8]; this
0x1800063ab  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800063b0  mov     rcx, rbx; string
0x1800063b3  call    cs:__imp_WindowsDeleteString
0x1800063b9  lea     rcx, [rbp+47h+var_B8]; this
0x1800063bd  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800063c2  mov     [rsp+110h+string], r12
0x1800063c7  lea     rdx, [rsp+110h+string]
0x1800063cc  mov     rcx, rdi
0x1800063cf  mov     rax, rsi
0x1800063d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063d7  mov     rcx, [rbp+4Fh]; this
0x1800063db  test    eax, eax
0x1800063dd  jns     short loc_1800063F4
0x1800063df  mov     r9d, eax; char *
0x1800063e2  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x1800063e9  mov     edx, 3F6h; void *
0x1800063ee  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800063f4  lea     rcx, [rbp+47h+var_90]
0x1800063f8  call    ??$GetActivationFactory@UIJsonValueStatics@Json@Data@Windows@@@wil@@YA?AV?$com_ptr_t@UIJsonValueStatics@Json@Data@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Data::Json::IJsonValueStatics>(ushort const *)
0x1800063fd  nop
0x1800063fe  mov     [rbp+47h+var_A0], r12
0x180006402  mov     rcx, [rbp+47h+var_90]
0x180006406  mov     rax, [rcx]
0x180006409  mov     [rbp+47h+var_A0], r12
0x18000640d  lea     r8, [rbp+47h+var_A0]
0x180006411  mov     rdx, [rsp+110h+string]
0x180006416  mov     rax, [rax+30h]
0x18000641a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000641f  mov     rcx, [rbp+4Fh]; this
0x180006423  test    eax, eax
0x180006425  jns     short loc_18000643C
0x180006427  mov     r9d, eax; char *
0x18000642a  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180006431  mov     edx, 3FBh; void *
0x180006436  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000643c  mov     [rbp+47h+var_A8], r12
0x180006440  mov     rcx, [rbp+47h+var_A0]
0x180006444  mov     rax, [rcx]
0x180006447  mov     [rbp+47h+var_A8], r12
0x18000644b  lea     rdx, [rbp+47h+var_A8]
0x18000644f  mov     rax, [rax+60h]
0x180006453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006458  mov     rcx, [rbp+4Fh]; this
0x18000645c  test    eax, eax
0x18000645e  jns     short loc_180006475
0x180006460  mov     r9d, eax; char *
0x180006463  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x18000646a  mov     edx, 3FEh; void *
0x18000646f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180006475  mov     [rbp+47h+var_B0], r12
0x180006479  mov     rdi, [rbp+47h+var_A8]
0x18000647d  mov     rax, [rdi]
0x180006480  mov     rbx, [rax+50h]
0x180006484  mov     [rbp+47h+var_B0], r12
0x180006488  mov     [rbp+47h+var_40], r12
0x18000648c  mov     r9d, 6; unsigned int
0x180006492  lea     r8d, [r9+1]; unsigned int
0x180006496  lea     rdx, sourceString; "status"
0x18000649d  lea     rcx, [rbp+47h+hstringHeader]; hstringHeader
0x1800064a1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800064a6  nop
0x1800064a7  lea     r8, [rbp+47h+var_B0]
0x1800064ab  mov     rdx, [rbp+47h+var_40]
0x1800064af  mov     rcx, rdi
0x1800064b2  mov     rax, rbx
0x1800064b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064ba  mov     rcx, [rbp+4Fh]; this
0x1800064be  test    eax, eax
0x1800064c0  jns     short loc_1800064D7
0x1800064c2  mov     r9d, eax; char *
0x1800064c5  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x1800064cc  mov     edx, 401h; void *
0x1800064d1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800064d7  xor     edx, edx; length
0x1800064d9  mov     rcx, [rbp+47h+var_B0]; string
0x1800064dd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800064e3  mov     rdi, rax
0x1800064e6  lea     rdx, aSuccess; "success"
0x1800064ed  mov     rcx, rax
0x1800064f0  call    cs:__imp__o__wcsicmp
0x1800064f6  test    eax, eax
0x1800064f8  jz      short loc_180006511
0x1800064fa  mov     bl, r12b
0x1800064fd  lea     rdx, aCancelled; "cancelled"
0x180006504  mov     rcx, rdi
0x180006507  call    cs:__imp__o__wcsicmp
0x18000650d  test    eax, eax
0x18000650f  jnz     short loc_180006513
0x180006511  mov     bl, 1
0x180006513  lea     rcx, [rbp+47h+var_B0]
0x180006517  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18000651c  nop
0x18000651d  lea     rcx, [rbp+47h+var_A8]
0x180006521  call    ??1?$com_ptr_t@UIStoreRequestHelperStatics@Store@Services@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(void)
0x180006526  nop
0x180006527  lea     rcx, [rbp+47h+var_A0]
0x18000652b  call    ??1?$com_ptr_t@UIStoreRequestHelperStatics@Store@Services@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(void)
0x180006530  nop
0x180006531  lea     rcx, [rbp+47h+var_90]
0x180006535  call    ??1?$com_ptr_t@UIStoreRequestHelperStatics@Store@Services@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(void)
0x18000653a  nop
0x18000653b  lea     rcx, [rsp+110h+string]
0x180006540  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180006545  nop
0x180006546  mov     rcx, [rsp+110h+var_C8]
0x18000654b  test    rcx, rcx
  ... truncated ...
```
