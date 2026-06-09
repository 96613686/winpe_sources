# _GetStoreInstallPath

- ea: `0x180008bd8`
- end: `0x180008e98`
- name: `_GetStoreInstallPath`
- size: `704`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180007344`

## callees

- `0x180001dc0`
- `0x180004fd4`
- `0x1800068a4`
- `0x18000698c`
- `0x180008678`
- `0x180008bd8`
- `0x1800090f0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008c68`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008c68`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180008c01`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180008c01`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180008e02`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180008e78`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180008e02`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180008e78`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180008c7e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180008c7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008c54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008c54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008d8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008dcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008e42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008d8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008dcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008e42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008e13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008e13`

## pseudocode

```c
__int64 __fastcall GetStoreInstallPath(_QWORD *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  HRESULT v5; // eax
  int ActivationFactory; // eax
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  __int64 v15; // rcx
  char *StringRawBuffer; // rax
  const char *v17; // r9
  wil *cotaskmem_string_failfast; // rax
  __int64 v19; // rcx
  void *v20; // [rsp+20h] [rbp-29h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-21h] BYREF
  HSTRING string; // [rsp+40h] [rbp-9h] BYREF
  __int64 *v23; // [rsp+48h] [rbp-1h] BYREF
  HSTRING v24; // [rsp+50h] [rbp+7h] BYREF
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp+Fh] BYREF
  __int64 v26; // [rsp+60h] [rbp+17h] BYREF
  __int64 *v27; // [rsp+68h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v2 = RoInitialize(1);
  v3 = v2;
  LODWORD(v20) = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCC,
      (int)"onecore\\vm\\wsl\\lxss\\wslapi\\wslsession.cpp",
      (const char *)(unsigned int)v2);
    return v3;
  }
  v27 = 0;
  string = 0;
  v5 = WindowsCreateStringReference(L"Windows.Storage.ApplicationData", 0x1Fu, &hstringHeader, &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_5612147b_e843_45e3_94d8_06169e3c8e17, &v27);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCF,
      (int)"onecore\\vm\\wsl\\lxss\\wslapi\\wslsession.cpp",
      (const char *)(unsigned int)ActivationFactory);
LABEL_19:
    wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>((__int64 *)&v27);
    RoUninitialize(v15);
    return v3;
  }
  v23 = 0;
  v7 = *v27;
  v23 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v7 + 48))(v27, &v23);
  v3 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD2,
      (int)"onecore\\vm\\wsl\\lxss\\wslapi\\wslsession.cpp",
      (const char *)(unsigned int)v8);
LABEL_18:
    wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>((__int64 *)&v23);
    goto LABEL_19;
  }
  v25 = 0;
  v9 = *v23;
  v25 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(v9 + 96))(
          v23,
          &v25);
  v3 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD5,
      (int)"onecore\\vm\\wsl\\lxss\\wslapi\\wslsession.cpp",
      (const char *)(unsigned int)v10);
LABEL_17:
    wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>((__int64 *)&v25);
    goto LABEL_18;
  }
  v26 = 0;
  v11 = (**v25)(v25, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, &v26);
  v3 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD8,
      (int)"onecore\\vm\\wsl\\lxss\\wslapi\\wslsession.cpp",
      (const char *)(unsigned int)v11);
LABEL_16:
    wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>(&v26);
    goto LABEL_17;
  }
  v24 = 0;
  v12 = v26;
  v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v26 + 96LL);
  WindowsDeleteString(0);
  v24 = 0;
  v14 = v13(v12, &v24);
  v3 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDB,
      (int)"onecore\\vm\\wsl\\lxss\\wslapi\\wslsession.cpp",
      (const char *)(unsigned int)v14);
    WindowsDeleteString(v24);
    v24 = 0;
    goto LABEL_16;
  }
  StringRawBuffer = (char *)WindowsGetStringRawBuffer(v24, 0);
  cotaskmem_string_failfast = wil::make_cotaskmem_string_failfast(
                                (wil *)&v20,
                                StringRawBuffer,
                                0xFFFFFFFFFFFFFFFFuLL,
                                v17);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    a1,
    cotaskmem_string_failfast);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
  WindowsDeleteString(v24);
  v24 = 0;
  wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>(&v26);
  wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>((__int64 *)&v25);
  wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>((__int64 *)&v23);
  wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>((__int64 *)&v27);
  RoUninitialize(v19);
  return 0;
}

```

## disassembly

```asm
0x180008bd8  push    rbp
0x180008bda  push    rbx
0x180008bdb  push    rsi
0x180008bdc  push    rdi
0x180008bdd  lea     rbp, [rsp-3Fh]
0x180008be2  sub     rsp, 88h
0x180008be9  mov     rax, cs:__security_cookie
0x180008bf0  xor     rax, rsp
0x180008bf3  mov     [rbp+57h+var_30], rax
0x180008bf7  mov     rsi, rcx
0x180008bfa  mov     edi, 1
0x180008bff  mov     ecx, edi
0x180008c01  call    cs:__imp_RoInitialize
0x180008c07  mov     ebx, eax
0x180008c09  mov     dword ptr [rbp+57h+var_80], eax
0x180008c0c  test    eax, eax
0x180008c0e  jns     short loc_180008C30
0x180008c10  mov     rcx, [rbp+5Fh]; this
0x180008c14  mov     r9d, eax; char *
0x180008c17  lea     r8, aOnecoreVmWslLx_3; "onecore\\vm\\wsl\\lxss\\wslapi\\wslsess"...
0x180008c1e  mov     edx, 0CCh; void *
0x180008c23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c28  nop
0x180008c29  mov     eax, ebx
0x180008c2b  jmp     loc_180008E80
0x180008c30  mov     [rbp+57h+var_38], 0
0x180008c38  mov     [rbp+57h+string], 0
0x180008c40  lea     r9, [rbp+57h+string]; string
0x180008c44  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180008c48  mov     edx, 1Fh; length
0x180008c4d  lea     rcx, ?RuntimeClass_Windows_Storage_ApplicationData@@3QBGB; "Windows.Storage.ApplicationData"
0x180008c54  call    cs:__imp_WindowsCreateStringReference
0x180008c5a  test    eax, eax
0x180008c5c  jns     short loc_180008C6F
0x180008c5e  xor     r9d, r9d; lpArguments
0x180008c61  xor     r8d, r8d; nNumberOfArguments
0x180008c64  mov     edx, edi; dwExceptionFlags
0x180008c66  mov     ecx, eax; dwExceptionCode
0x180008c68  call    cs:__imp_RaiseException
0x180008c6e  int     3; Trap to Debugger
0x180008c6f  lea     r8, [rbp+57h+var_38]
0x180008c73  lea     rdx, _GUID_5612147b_e843_45e3_94d8_06169e3c8e17
0x180008c7a  mov     rcx, [rbp+57h+string]
0x180008c7e  call    cs:__imp_RoGetActivationFactory
0x180008c84  mov     ebx, eax
0x180008c86  test    eax, eax
0x180008c88  jns     short loc_180008CA7
0x180008c8a  mov     rcx, [rbp+5Fh]; this
0x180008c8e  mov     r9d, eax; char *
0x180008c91  lea     r8, aOnecoreVmWslLx_3; "onecore\\vm\\wsl\\lxss\\wslapi\\wslsess"...
0x180008c98  mov     edx, 0CFh; void *
0x180008c9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ca2  jmp     loc_180008DF8
0x180008ca7  mov     [rbp+57h+var_58], 0
0x180008caf  mov     rcx, [rbp+57h+var_38]
0x180008cb3  mov     rax, [rcx]
0x180008cb6  mov     [rbp+57h+var_58], 0
0x180008cbe  lea     rdx, [rbp+57h+var_58]
0x180008cc2  mov     rax, [rax+30h]
0x180008cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ccb  mov     ebx, eax
0x180008ccd  test    eax, eax
0x180008ccf  jns     short loc_180008CEE
0x180008cd1  mov     rcx, [rbp+5Fh]; this
0x180008cd5  mov     r9d, eax; char *
0x180008cd8  lea     r8, aOnecoreVmWslLx_3; "onecore\\vm\\wsl\\lxss\\wslapi\\wslsess"...
0x180008cdf  mov     edx, 0D2h; void *
0x180008ce4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ce9  jmp     loc_180008DEE
0x180008cee  mov     [rbp+57h+var_48], 0
0x180008cf6  mov     rcx, [rbp+57h+var_58]
0x180008cfa  mov     rax, [rcx]
0x180008cfd  mov     [rbp+57h+var_48], 0
0x180008d05  lea     rdx, [rbp+57h+var_48]
0x180008d09  mov     rax, [rax+60h]
0x180008d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d12  mov     ebx, eax
0x180008d14  test    eax, eax
0x180008d16  jns     short loc_180008D35
0x180008d18  mov     rcx, [rbp+5Fh]; this
0x180008d1c  mov     r9d, eax; char *
0x180008d1f  lea     r8, aOnecoreVmWslLx_3; "onecore\\vm\\wsl\\lxss\\wslapi\\wslsess"...
0x180008d26  mov     edx, 0D5h; void *
0x180008d2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d30  jmp     loc_180008DE4
0x180008d35  mov     [rbp+57h+var_40], 0
0x180008d3d  mov     rcx, [rbp+57h+var_48]
0x180008d41  mov     rax, [rcx]
0x180008d44  lea     r8, [rbp+57h+var_40]
0x180008d48  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x180008d4f  mov     rax, [rax]
0x180008d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d57  mov     ebx, eax
0x180008d59  test    eax, eax
0x180008d5b  jns     short loc_180008D77
0x180008d5d  mov     rcx, [rbp+5Fh]; this
0x180008d61  mov     r9d, eax; char *
0x180008d64  lea     r8, aOnecoreVmWslLx_3; "onecore\\vm\\wsl\\lxss\\wslapi\\wslsess"...
0x180008d6b  mov     edx, 0D8h; void *
0x180008d70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d75  jmp     short loc_180008DDA
0x180008d77  mov     [rbp+57h+var_50], 0
0x180008d7f  mov     rdi, [rbp+57h+var_40]
0x180008d83  mov     rax, [rdi]
0x180008d86  mov     rbx, [rax+60h]
0x180008d8a  xor     ecx, ecx; string
0x180008d8c  call    cs:__imp_WindowsDeleteString
0x180008d92  mov     [rbp+57h+var_50], 0
0x180008d9a  lea     rdx, [rbp+57h+var_50]
0x180008d9e  mov     rcx, rdi
0x180008da1  mov     rax, rbx
0x180008da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008da9  mov     ebx, eax
0x180008dab  test    eax, eax
0x180008dad  jns     short loc_180008E0D
0x180008daf  mov     rcx, [rbp+5Fh]; this
0x180008db3  mov     r9d, eax; char *
0x180008db6  lea     r8, aOnecoreVmWslLx_3; "onecore\\vm\\wsl\\lxss\\wslapi\\wslsess"...
0x180008dbd  mov     edx, 0DBh; void *
0x180008dc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008dc7  nop
0x180008dc8  mov     rcx, [rbp+57h+var_50]; string
0x180008dcc  call    cs:__imp_WindowsDeleteString
0x180008dd2  mov     [rbp+57h+var_50], 0
0x180008dda  lea     rcx, [rbp+57h+var_40]
0x180008dde  call    ??1?$com_ptr_t@UIApplicationDataStatics@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>(void)
0x180008de3  nop
0x180008de4  lea     rcx, [rbp+57h+var_48]
0x180008de8  call    ??1?$com_ptr_t@UIApplicationDataStatics@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>(void)
0x180008ded  nop
0x180008dee  lea     rcx, [rbp+57h+var_58]
0x180008df2  call    ??1?$com_ptr_t@UIApplicationDataStatics@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>(void)
0x180008df7  nop
0x180008df8  lea     rcx, [rbp+57h+var_38]
0x180008dfc  call    ??1?$com_ptr_t@UIApplicationDataStatics@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>(void)
0x180008e01  nop
0x180008e02  call    cs:__imp_RoUninitialize
0x180008e08  jmp     loc_180008C29
0x180008e0d  xor     edx, edx; length
0x180008e0f  mov     rcx, [rbp+57h+var_50]; string
0x180008e13  call    cs:__imp_WindowsGetStringRawBuffer
0x180008e19  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x180008e1d  mov     rdx, rax; unsigned __int16 *
0x180008e20  lea     rcx, [rbp+57h+var_80]; this
0x180008e24  call    ?make_cotaskmem_string_failfast@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_failfast(ushort const *,unsigned __int64)
0x180008e29  mov     rdx, rax
0x180008e2c  mov     rcx, rsi
0x180008e2f  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180008e34  lea     rcx, [rbp+57h+var_80]
0x180008e38  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180008e3d  nop
0x180008e3e  mov     rcx, [rbp+57h+var_50]; string
0x180008e42  call    cs:__imp_WindowsDeleteString
0x180008e48  mov     [rbp+57h+var_50], 0
0x180008e50  lea     rcx, [rbp+57h+var_40]
0x180008e54  call    ??1?$com_ptr_t@UIApplicationDataStatics@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>(void)
0x180008e59  nop
0x180008e5a  lea     rcx, [rbp+57h+var_48]
0x180008e5e  call    ??1?$com_ptr_t@UIApplicationDataStatics@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>(void)
0x180008e63  nop
0x180008e64  lea     rcx, [rbp+57h+var_58]
0x180008e68  call    ??1?$com_ptr_t@UIApplicationDataStatics@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>(void)
0x180008e6d  nop
0x180008e6e  lea     rcx, [rbp+57h+var_38]
0x180008e72  call    ??1?$com_ptr_t@UIApplicationDataStatics@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>(void)
0x180008e77  nop
0x180008e78  call    cs:__imp_RoUninitialize
0x180008e7e  xor     eax, eax
0x180008e80  mov     rcx, [rbp+57h+var_30]
0x180008e84  xor     rcx, rsp; StackCookie
0x180008e87  call    __security_check_cookie
0x180008e8c  add     rsp, 88h
0x180008e93  pop     rdi
0x180008e94  pop     rsi
0x180008e95  pop     rbx
0x180008e96  pop     rbp
0x180008e97  retn
```
