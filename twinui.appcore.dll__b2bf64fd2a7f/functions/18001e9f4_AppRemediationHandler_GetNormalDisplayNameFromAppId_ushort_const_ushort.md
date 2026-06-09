# AppRemediationHandler::GetNormalDisplayNameFromAppId(ushort const *,ushort * *)

- ea: `0x18001e9f4`
- end: `0x18001ec6d`
- name: `?GetNormalDisplayNameFromAppId@AppRemediationHandler@@AEAAJPEBGPEAPEAG@Z`
- size: `633`
- prototype: `__int64 __fastcall(AppRemediationHandler *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e360`

## callees

- `0x1800083f0`
- `0x180012450`
- `0x180016300`
- `0x18001d578`
- `0x18001d95c`
- `0x18001e9f4`
- `0x18002b1b0`
- `0x180033d5c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eb94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ec0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eb94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ec0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ebd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ebd6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001ea57`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001eb15`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001ea57`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001eb15`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall AppRemediationHandler::GetNormalDisplayNameFromAppId(
        AppRemediationHandler *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  int ActivationFactory; // eax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, _QWORD, __int64 *); // rbx
  __int64 v7; // rax
  int v8; // eax
  int v9; // eax
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  PCWSTR StringRawBuffer; // rax
  unsigned __int16 *v16; // rax
  int v18; // [rsp+20h] [rbp-88h]
  HSTRING string; // [rsp+30h] [rbp-78h] BYREF
  const unsigned __int16 *v20; // [rsp+38h] [rbp-70h] BYREF
  __int64 v21; // [rsp+40h] [rbp-68h] BYREF
  __int64 v22; // [rsp+48h] [rbp-60h] BYREF
  __int64 *v23; // [rsp+50h] [rbp-58h] BYREF
  __int64 v24; // [rsp+58h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-48h] BYREF
  __int64 v26; // [rsp+78h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v20 = a2;
  *a3 = 0;
  v24 = 0;
  v26 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.Application",
    0x2Du,
    0x2Cu);
  ActivationFactory = RoGetActivationFactory(v26, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v24);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x16F,
      (unsigned int)"onecoreuap\\shell\\twinui\\appremediationhandler\\lib\\appremediationhandler.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v18);
  v22 = 0;
  v5 = v24;
  v6 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v24 + 240LL);
  v22 = 0;
  v7 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v20);
  v8 = v6(v5, 0, *(_QWORD *)(v7 + 24), &v22);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x171,
      (unsigned int)"onecoreuap\\shell\\twinui\\appremediationhandler\\lib\\appremediationhandler.cpp",
      (const char *)(unsigned int)v8,
      v18);
  v23 = 0;
  v26 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.ApplicationResourceResolver",
    0x3Du,
    0x3Cu);
  v9 = RoGetActivationFactory(v26, &GUID_84463b2a_c88e_4597_b41f_17d3bf6486e9, &v23);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x173,
      (unsigned int)"onecoreuap\\shell\\twinui\\appremediationhandler\\lib\\appremediationhandler.cpp",
      (const char *)(unsigned int)v9,
      v18);
  v21 = 0;
  v10 = *v23;
  v21 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v10 + 48))(v23, v22, &v21);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x175,
      (unsigned int)"onecoreuap\\shell\\twinui\\appremediationhandler\\lib\\appremediationhandler.cpp",
      (const char *)(unsigned int)v11,
      v18);
  string = 0;
  v12 = v21;
  v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v21 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v14 = v13(v12, &string);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecoreuap\\shell\\twinui\\appremediationhandler\\lib\\appremediationhandler.cpp",
      (const char *)(unsigned int)v14,
      v18);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v20,
    StringRawBuffer,
    -1);
  v16 = (unsigned __int16 *)v20;
  v20 = 0;
  *a3 = v16;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
  WindowsDeleteString(string);
  string = 0;
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v21);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v23);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v22);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v24);
  return 0;
}

```

## disassembly

```asm
0x18001e9f4  mov     r11, rsp
0x18001e9f7  mov     [r11+8], rbx
0x18001e9fb  push    rsi
0x18001e9fc  push    rdi
0x18001e9fd  push    r14
0x18001e9ff  sub     rsp, 90h
0x18001ea06  mov     rax, cs:__security_cookie
0x18001ea0d  xor     rax, rsp
0x18001ea10  mov     [rsp+0A8h+var_28], rax
0x18001ea18  mov     rsi, r8
0x18001ea1b  mov     [r11-70h], rdx
0x18001ea1f  xor     r14d, r14d
0x18001ea22  mov     [r8], r14
0x18001ea25  mov     [r11-50h], r14
0x18001ea29  mov     [r11-30h], r14
0x18001ea2d  lea     r9d, [r14+2Ch]; unsigned int
0x18001ea31  lea     r8d, [r14+2Dh]; unsigned int
0x18001ea35  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x18001ea3c  lea     rcx, [r11-48h]; hstringHeader
0x18001ea40  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001ea45  nop
0x18001ea46  lea     r8, [rsp+0A8h+var_50]
0x18001ea4b  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x18001ea52  mov     rcx, [rsp+0A8h+var_30]
0x18001ea57  call    cs:__imp_RoGetActivationFactory
0x18001ea5d  mov     rcx, [rsp+0A8h]; this
0x18001ea65  test    eax, eax
0x18001ea67  jns     short loc_18001EA7E
0x18001ea69  mov     r9d, eax; char *
0x18001ea6c  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\twinui\\appremediati"...
0x18001ea73  mov     edx, 16Fh; void *
0x18001ea78  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ea7e  mov     [rsp+0A8h+var_60], r14
0x18001ea83  mov     rdi, [rsp+0A8h+var_50]
0x18001ea88  mov     rax, [rdi]
0x18001ea8b  mov     rbx, [rax+0F0h]
0x18001ea92  mov     [rsp+0A8h+var_60], r14
0x18001ea97  lea     rdx, [rsp+0A8h+var_70]
0x18001ea9c  lea     rcx, [rsp+0A8h+hstringHeader]
0x18001eaa1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001eaa6  nop
0x18001eaa7  lea     r9, [rsp+0A8h+var_60]
0x18001eaac  mov     r8, [rax+18h]
0x18001eab0  xor     edx, edx
0x18001eab2  mov     rcx, rdi
0x18001eab5  mov     rax, rbx
0x18001eab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eabd  mov     rcx, [rsp+0A8h]; this
0x18001eac5  test    eax, eax
0x18001eac7  jns     short loc_18001EADE
0x18001eac9  mov     r9d, eax; char *
0x18001eacc  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\twinui\\appremediati"...
0x18001ead3  mov     edx, 171h; void *
0x18001ead8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001eade  mov     [rsp+0A8h+var_58], r14
0x18001eae3  mov     [rsp+0A8h+var_30], r14
0x18001eae8  mov     r9d, 3Ch ; '<'; unsigned int
0x18001eaee  lea     r8d, [r9+1]; unsigned int
0x18001eaf2  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationResourceResolver@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x18001eaf9  lea     rcx, [rsp+0A8h+hstringHeader]; hstringHeader
0x18001eafe  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001eb03  nop
0x18001eb04  lea     r8, [rsp+0A8h+var_58]
0x18001eb09  lea     rdx, _GUID_84463b2a_c88e_4597_b41f_17d3bf6486e9
0x18001eb10  mov     rcx, [rsp+0A8h+var_30]
0x18001eb15  call    cs:__imp_RoGetActivationFactory
0x18001eb1b  mov     rcx, [rsp+0A8h]; this
0x18001eb23  test    eax, eax
0x18001eb25  jns     short loc_18001EB3C
0x18001eb27  mov     r9d, eax; char *
0x18001eb2a  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\twinui\\appremediati"...
0x18001eb31  mov     edx, 173h; void *
0x18001eb36  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001eb3c  mov     [rsp+0A8h+var_68], r14
0x18001eb41  mov     rcx, [rsp+0A8h+var_58]
0x18001eb46  mov     rax, [rcx]
0x18001eb49  mov     [rsp+0A8h+var_68], r14
0x18001eb4e  lea     r8, [rsp+0A8h+var_68]
0x18001eb53  mov     rdx, [rsp+0A8h+var_60]
0x18001eb58  mov     rax, [rax+30h]
0x18001eb5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb61  mov     rcx, [rsp+0A8h]; this
0x18001eb69  test    eax, eax
0x18001eb6b  jns     short loc_18001EB81
0x18001eb6d  mov     r9d, eax; char *
0x18001eb70  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\twinui\\appremediati"...
0x18001eb77  mov     edx, 175h; void *
0x18001eb7c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001eb81  mov     [rsp+0A8h+string], r14
0x18001eb86  mov     rdi, [rsp+0A8h+var_68]
0x18001eb8b  mov     rax, [rdi]
0x18001eb8e  mov     rbx, [rax+30h]
0x18001eb92  xor     ecx, ecx; string
0x18001eb94  call    cs:__imp_WindowsDeleteString
0x18001eb9a  mov     [rsp+0A8h+string], r14
0x18001eb9f  lea     rdx, [rsp+0A8h+string]
0x18001eba4  mov     rcx, rdi
0x18001eba7  mov     rax, rbx
0x18001ebaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebaf  mov     rcx, [rsp+0A8h]; this
0x18001ebb7  test    eax, eax
0x18001ebb9  jns     short loc_18001EBCF
0x18001ebbb  mov     r9d, eax; char *
0x18001ebbe  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\twinui\\appremediati"...
0x18001ebc5  mov     edx, 177h; void *
0x18001ebca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ebcf  xor     edx, edx; length
0x18001ebd1  mov     rcx, [rsp+0A8h+string]; string
0x18001ebd6  call    cs:__imp_WindowsGetStringRawBuffer
0x18001ebdc  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001ebe0  mov     rdx, rax
0x18001ebe3  lea     rcx, [rsp+0A8h+var_70]
0x18001ebe8  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001ebed  mov     rax, [rsp+0A8h+var_70]
0x18001ebf2  mov     [rsp+0A8h+var_70], r14
0x18001ebf7  mov     [rsi], rax
0x18001ebfa  lea     rcx, [rsp+0A8h+var_70]
0x18001ebff  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001ec04  nop
0x18001ec05  mov     rcx, [rsp+0A8h+string]; string
0x18001ec0a  call    cs:__imp_WindowsDeleteString
0x18001ec10  mov     [rsp+0A8h+string], r14
0x18001ec15  lea     rcx, [rsp+0A8h+var_68]
0x18001ec1a  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18001ec1f  nop
0x18001ec20  lea     rcx, [rsp+0A8h+var_58]
0x18001ec25  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18001ec2a  nop
0x18001ec2b  lea     rcx, [rsp+0A8h+var_60]
0x18001ec30  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18001ec35  nop
0x18001ec36  lea     rcx, [rsp+0A8h+var_50]
0x18001ec3b  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18001ec40  xor     eax, eax
0x18001ec42  jmp     short loc_18001EC48
0x18001ec44  mov     eax, dword ptr [rsp+0A8h+string]
0x18001ec48  mov     rcx, [rsp+0A8h+var_28]
0x18001ec50  xor     rcx, rsp; StackCookie
0x18001ec53  call    __security_check_cookie
0x18001ec58  mov     rbx, [rsp+0A8h+arg_0]
0x18001ec60  add     rsp, 90h
0x18001ec67  pop     r14
0x18001ec69  pop     rdi
0x18001ec6a  pop     rsi
0x18001ec6b  retn
```
