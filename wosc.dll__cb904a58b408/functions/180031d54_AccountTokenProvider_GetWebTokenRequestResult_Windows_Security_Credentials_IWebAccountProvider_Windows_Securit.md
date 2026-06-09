# AccountTokenProvider::GetWebTokenRequestResult(Windows::Security::Credentials::IWebAccountProvider *,Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics *,ushort const *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult * *)

- ea: `0x180031d54`
- end: `0x180031fc4`
- name: `?GetWebTokenRequestResult@AccountTokenProvider@@AEAAJPEAUIWebAccountProvider@Credentials@Security@Windows@@PEAUIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@45@PEBGPEAPEAUIWebTokenRequestResult@78945@@Z`
- size: `624`
- prototype: `__int64 __fastcall(AccountTokenProvider *__hidden this, struct Windows::Security::Credentials::IWebAccountProvider *, struct Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics *, const unsigned __int16 *, struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800321f0`

## callees

- `0x180003110`
- `0x180005f50`
- `0x180006b9c`
- `0x18000b0bc`
- `0x1800101fc`
- `0x18002f058`
- `0x18002f238`
- `0x180031d54`
- `0x180059010`

## string_xrefs

- `0x180031d9e`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`
- `0x180031dc7`: `onecore\base\flighting\onesettings\libs\identityprovider\accounttokenprovider.cpp`
- `0x180031e45`: `onecore\base\flighting\onesettings\libs\identityprovider\accounttokenprovider.cpp`
- `0x180031e89`: `onecore\base\flighting\onesettings\libs\identityprovider\accounttokenprovider.cpp`
- `0x180031efc`: `onecore\base\flighting\onesettings\libs\identityprovider\accounttokenprovider.cpp`
- `0x180031f40`: `onecore\base\flighting\onesettings\libs\identityprovider\accounttokenprovider.cpp`
- `0x180031f69`: `onecore\base\flighting\onesettings\libs\identityprovider\accounttokenprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall AccountTokenProvider::GetWebTokenRequestResult(
        const WCHAR **this,
        struct Windows::Security::Credentials::IWebAccountProvider *a2,
        struct Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics *a3,
        const unsigned __int16 *a4,
        struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult **a5)
{
  int v8; // eax
  __int64 v9; // rsi
  __int64 (__fastcall *v10)(__int64, struct Windows::Security::Credentials::IWebAccountProvider *, PVOID, PVOID); // rdi
  PVOID Reserved1; // rbx
  HSTRING_HEADER *v12; // rax
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rsi
  __int64 (__fastcall *v18)(__int64, __int64, PVOID, _BYTE *); // rdi
  PVOID v19; // rbx
  int v20; // eax
  __int64 (__fastcall *v21)(struct Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics *, __int64, __int64 *); // rbx
  int v22; // eax
  int v23; // eax
  int v25; // [rsp+20h] [rbp-91h]
  _BYTE v26[8]; // [rsp+40h] [rbp-71h] BYREF
  __int64 v27; // [rsp+48h] [rbp-69h] BYREF
  __int64 v28; // [rsp+50h] [rbp-61h] BYREF
  __int64 v29; // [rsp+58h] [rbp-59h] BYREF
  __int64 v30; // [rsp+60h] [rbp-51h] BYREF
  const WCHAR *v31; // [rsp+68h] [rbp-49h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-41h] BYREF
  __int64 v33; // [rsp+88h] [rbp-29h]
  HSTRING_HEADER v34; // [rsp+90h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]

  v31 = a4;
  v30 = 0;
  v33 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Authentication.Web.Core.WebTokenRequest",
    0x39u,
    0x38u);
  v8 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>(
         v33,
         (__int64)&v30);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\accounttokenprovider.cpp",
      (const char *)(unsigned int)v8,
      v25);
  v27 = 0;
  v9 = v30;
  v10 = *(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccountProvider *, PVOID, PVOID))(*(_QWORD *)v30 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v31)[1].Reserved.Reserved1;
  v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v34, this + 6);
  v13 = v10(v9, a2, v12[1].Reserved.Reserved1, Reserved1);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9B,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\accounttokenprovider.cpp",
      (const char *)(unsigned int)v13,
      0);
  v29 = 0;
  v14 = v27;
  v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  v16 = v15(v14, &v29);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\accounttokenprovider.cpp",
      (const char *)(unsigned int)v16,
      0);
  v26[0] = 0;
  v17 = v29;
  v18 = *(__int64 (__fastcall **)(__int64, __int64, PVOID, _BYTE *))(*(_QWORD *)v29 + 80LL);
  v19 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v34, this + 4)[1].Reserved.Reserved1;
  v33 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"authority", 0xAu, 9u);
  v20 = v18(v17, v33, v19, v26);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\accounttokenprovider.cpp",
      (const char *)(unsigned int)v20,
      0);
  v28 = 0;
  v21 = *(__int64 (__fastcall **)(struct Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics *, __int64, __int64 *))(*(_QWORD *)a3 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  v22 = v21(a3, v27, &v28);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA6,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\accounttokenprovider.cpp",
      (const char *)(unsigned int)v22,
      0);
  v23 = BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *>(
          v28,
          (__int64)a5);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\accounttokenprovider.cpp",
      (const char *)(unsigned int)v23,
      0);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  return 0;
}

```

## disassembly

```asm
0x180031d54  push    rbp
0x180031d56  push    rbx
0x180031d57  push    rsi
0x180031d58  push    rdi
0x180031d59  push    r12
0x180031d5b  push    r13
0x180031d5d  push    r14
0x180031d5f  push    r15
0x180031d61  lea     rbp, [rsp-17h]
0x180031d66  sub     rsp, 0C8h
0x180031d6d  mov     rax, cs:__security_cookie
0x180031d74  xor     rax, rsp
0x180031d77  mov     [rbp+4Fh+var_50], rax
0x180031d7b  mov     r14, r8
0x180031d7e  mov     r12, rdx
0x180031d81  mov     r13, rcx
0x180031d84  mov     [rbp+4Fh+var_98], r9
0x180031d88  mov     r15, [rbp+4Fh+arg_20]
0x180031d8c  xor     ebx, ebx
0x180031d8e  mov     [rbp+4Fh+var_A0], rbx
0x180031d92  mov     [rbp+4Fh+var_78], rbx
0x180031d96  lea     r9d, [rbx+38h]; unsigned int
0x180031d9a  lea     r8d, [rbx+39h]; unsigned int
0x180031d9e  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x180031da5  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x180031da9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180031dae  nop
0x180031daf  lea     rdx, [rbp+4Fh+var_A0]
0x180031db3  mov     rcx, [rbp+4Fh+var_78]
0x180031db7  call    ??$GetActivationFactory@V?$ComPtr@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>)
0x180031dbc  mov     rcx, [rbp+57h]; this
0x180031dc0  test    eax, eax
0x180031dc2  jns     short loc_180031DD9
0x180031dc4  mov     r9d, eax; char *
0x180031dc7  lea     r8, aOnecoreBaseFli_29; "onecore\\base\\flighting\\onesettings\\"...
0x180031dce  mov     edx, 92h; void *
0x180031dd3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031dd9  mov     [rbp+4Fh+var_B8], rbx
0x180031ddd  mov     rsi, [rbp+4Fh+var_A0]
0x180031de1  mov     rax, [rsi]
0x180031de4  mov     rdi, [rax+38h]
0x180031de8  lea     rcx, [rbp+4Fh+var_B8]
0x180031dec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031df1  lea     rdx, [rbp+4Fh+var_98]
0x180031df5  lea     rcx, [rbp+4Fh+hstringHeader]
0x180031df9  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180031dfe  nop
0x180031dff  mov     rbx, [rax+18h]
0x180031e03  lea     rdx, [r13+30h]
0x180031e07  lea     rcx, [rbp+4Fh+var_70]
0x180031e0b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180031e10  nop
0x180031e11  lea     rcx, [rbp+4Fh+var_B8]
0x180031e15  mov     [rsp+100h+var_D8], rcx
0x180031e1a  mov     [rsp+100h+var_E0], 0; int
0x180031e22  mov     r9, rbx
0x180031e25  mov     r8, [rax+18h]
0x180031e29  mov     rdx, r12
0x180031e2c  mov     rcx, rsi
0x180031e2f  mov     rax, rdi
0x180031e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e37  mov     rcx, [rbp+57h]; this
0x180031e3b  xor     r12d, r12d
0x180031e3e  test    eax, eax
0x180031e40  jns     short loc_180031E57
0x180031e42  mov     r9d, eax; char *
0x180031e45  lea     r8, aOnecoreBaseFli_29; "onecore\\base\\flighting\\onesettings\\"...
0x180031e4c  mov     edx, 9Bh; void *
0x180031e51  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031e57  mov     [rbp+4Fh+var_A8], r12
0x180031e5b  mov     rdi, [rbp+4Fh+var_B8]
0x180031e5f  mov     rax, [rdi]
0x180031e62  mov     rbx, [rax+50h]
0x180031e66  lea     rcx, [rbp+4Fh+var_A8]
0x180031e6a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031e6f  lea     rdx, [rbp+4Fh+var_A8]
0x180031e73  mov     rcx, rdi
0x180031e76  mov     rax, rbx
0x180031e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e7e  mov     rcx, [rbp+57h]; this
0x180031e82  test    eax, eax
0x180031e84  jns     short loc_180031E9B
0x180031e86  mov     r9d, eax; char *
0x180031e89  lea     r8, aOnecoreBaseFli_29; "onecore\\base\\flighting\\onesettings\\"...
0x180031e90  mov     edx, 9Eh; void *
0x180031e95  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031e9b  mov     [rbp+4Fh+var_C0], r12b
0x180031e9f  mov     rsi, [rbp+4Fh+var_A8]
0x180031ea3  mov     rax, [rsi]
0x180031ea6  mov     rdi, [rax+50h]
0x180031eaa  lea     rdx, [r13+20h]
0x180031eae  lea     rcx, [rbp+4Fh+var_70]
0x180031eb2  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180031eb7  nop
0x180031eb8  mov     rbx, [rax+18h]
0x180031ebc  mov     [rbp+4Fh+var_78], r12
0x180031ec0  mov     r9d, 9; unsigned int
0x180031ec6  lea     r8d, [r9+1]; unsigned int
0x180031eca  lea     rdx, aAuthority; "authority"
0x180031ed1  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x180031ed5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180031eda  nop
0x180031edb  lea     r9, [rbp+4Fh+var_C0]
0x180031edf  mov     r8, rbx
0x180031ee2  mov     rdx, [rbp+4Fh+var_78]
0x180031ee6  mov     rcx, rsi
0x180031ee9  mov     rax, rdi
0x180031eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ef1  mov     rcx, [rbp+57h]; this
0x180031ef5  test    eax, eax
0x180031ef7  jns     short loc_180031F0E
0x180031ef9  mov     r9d, eax; char *
0x180031efc  lea     r8, aOnecoreBaseFli_29; "onecore\\base\\flighting\\onesettings\\"...
0x180031f03  mov     edx, 0A3h; void *
0x180031f08  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031f0e  mov     [rbp+4Fh+var_B0], r12
0x180031f12  mov     rax, [r14]
0x180031f15  mov     rbx, [rax+30h]
0x180031f19  lea     rcx, [rbp+4Fh+var_B0]
0x180031f1d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031f22  lea     r8, [rbp+4Fh+var_B0]
0x180031f26  mov     rdx, [rbp+4Fh+var_B8]
0x180031f2a  mov     rcx, r14
0x180031f2d  mov     rax, rbx
0x180031f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f35  mov     rcx, [rbp+57h]; this
0x180031f39  test    eax, eax
0x180031f3b  jns     short loc_180031F52
0x180031f3d  mov     r9d, eax; char *
0x180031f40  lea     r8, aOnecoreBaseFli_29; "onecore\\base\\flighting\\onesettings\\"...
0x180031f47  mov     edx, 0A6h; void *
0x180031f4c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031f52  mov     rdx, r15
0x180031f55  mov     rcx, [rbp+4Fh+var_B0]
0x180031f59  call    ??$BlockOnCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@PEAUIWebTokenRequestResult@Core@Web@Authentication@Security@3@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@PEAPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@2@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult * *,tagCOWAIT_FLAGS,void *)
0x180031f5e  mov     rcx, [rbp+57h]; this
0x180031f62  test    eax, eax
0x180031f64  jns     short loc_180031F7B
0x180031f66  mov     r9d, eax; char *
0x180031f69  lea     r8, aOnecoreBaseFli_29; "onecore\\base\\flighting\\onesettings\\"...
0x180031f70  mov     edx, 0A8h; void *
0x180031f75  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031f7b  lea     rcx, [rbp+4Fh+var_B0]
0x180031f7f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031f84  nop
0x180031f85  lea     rcx, [rbp+4Fh+var_A8]
0x180031f89  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031f8e  nop
0x180031f8f  lea     rcx, [rbp+4Fh+var_B8]
0x180031f93  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031f98  nop
0x180031f99  lea     rcx, [rbp+4Fh+var_A0]
0x180031f9d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031fa2  xor     eax, eax
0x180031fa4  mov     rcx, [rbp+4Fh+var_50]
0x180031fa8  xor     rcx, rsp; StackCookie
0x180031fab  call    __security_check_cookie
0x180031fb0  add     rsp, 0C8h
0x180031fb7  pop     r15
0x180031fb9  pop     r14
0x180031fbb  pop     r13
0x180031fbd  pop     r12
0x180031fbf  pop     rdi
0x180031fc0  pop     rsi
0x180031fc1  pop     rbx
0x180031fc2  pop     rbp
0x180031fc3  retn
```
