# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Authentication::Web::Core::WebTokenResponse,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Authentication::Web::Core::WebTokenResponse *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::Web::Core::WebTokenResponse *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::Web::Core::WebTokenResponse *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Authentication::Web::Core::WebTokenResponse *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::Web::Core::WebTokenResponse *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::Web::Core::WebTokenResponse *>,0> * *)

- ea: `0x1800247e4`
- end: `0x180024a7e`
- name: `??$CreateExternalObjectVector@VWebTokenResponse@Core@Web@Authentication@Security@Windows@@V?$AgileVector@PEAVWebTokenResponse@Core@Web@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebTokenResponse@Core@Web@Authentication@Security@Windows@@@Internal@Collections@Foundation@6@U?$DefaultLifetimeTraits@PEAVWebTokenResponse@Core@Web@Authentication@Security@Windows@@@89Foundation@6@$0A@@Internal@Collections@Foundation@6@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVWebTokenResponse@Core@Web@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebTokenResponse@Core@Web@Authentication@Security@Windows@@@Internal@Collections@Foundation@6@U?$DefaultLifetimeTraits@PEAVWebTokenResponse@Core@Web@Authentication@Security@Windows@@@89Foundation@6@$0A@@1234@@Z`
- size: `666`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800241ac`
- `0x180026a5c`
- `0x180027ccc`
- `0x18005aa84`
- `0x1800b2ee8`
- `0x1800f90ac`

## callees

- `0x180007350`
- `0x1800247e4`
- `0x180024a84`
- `0x180024ab0`
- `0x18008e690`
- `0x18009b108`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024a28`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024a3b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024a4e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024a61`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024a28`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024a3b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024a4e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024a61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024837`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024870`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800248a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024944`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024837`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024870`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800248a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024944`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180024960`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180024960`

## string_xrefs

- `0x180024869`: `Windows.Foundation.Collections.IVectorView`1<Windows.Security.Authentication.Web.Core.WebTokenResponse>`
- `0x180024830`: `Windows.Foundation.Collections.IVector`1<Windows.Security.Authentication.Web.Core.WebTokenResponse>`
- `0x1800248a2`: `Windows.Foundation.Collections.IIterator`1<Windows.Security.Authentication.Web.Core.WebTokenResponse>`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Authentication::Web::Core::WebTokenResponse,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Authentication::Web::Core::WebTokenResponse *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::Web::Core::WebTokenResponse *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::Web::Core::WebTokenResponse *>,0>>(
        __int64 a1,
        _QWORD *a2)
{
  unsigned int v3; // eax
  UINT32 v4; // edx
  HRESULT v5; // eax
  unsigned int v6; // eax
  UINT32 v7; // edx
  HRESULT v8; // eax
  unsigned int v9; // eax
  UINT32 v10; // edx
  HRESULT v11; // eax
  __int64 v12; // rbx
  HRESULT v13; // eax
  int ActivationFactory; // ebx
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v19; // rcx
  __int64 v20; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v21; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v22[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v23; // [rsp+48h] [rbp-B8h]
  GUID v24; // [rsp+58h] [rbp-A8h]
  GUID v25; // [rsp+68h] [rbp-98h]
  GUID v26; // [rsp+78h] [rbp-88h]
  GUID v27; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v30; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v31; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v32; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v33; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v34; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v35; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x63u);
  v4 = v3 - 1;
  if ( v3 > 0x63 )
    v4 = 99;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Security.Authentication.Web.Core.WebTokenResponse>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x67u);
  v7 = v6 - 1;
  if ( v6 > 0x67 )
    v7 = 103;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Security.Authentication.Web.Core.WebTokenResponse>",
         v7,
         &v30,
         &v31);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v33 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x65u);
  v10 = v9 - 1;
  if ( v9 > 0x65 )
    v10 = 101;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Security.Authentication.Web.Core.WebTokenResponse>",
          v10,
          &v32,
          &v33);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v22[0] = string;
  v22[1] = v31;
  v22[2] = v33;
  v23 = GUID_67a7c5ca_83f6_44c6_a3b1_0eb69e41fa8a;
  v24 = GUID_58dc4e4c_a84d_5ad6_a6d9_6ee477329c9f;
  v25 = GUID_199e065c_8195_55da_9c10_8aeaf9ac1062;
  v26 = GUID_7e5bb7ec_bbd7_5575_9a61_f5815fa22a0e;
  v27 = GUID_f080b0c9_a095_5b3a_a1dc_d17e7d2982c7;
  v20 = 0;
  v12 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v20);
  v35 = 0;
  v13 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v34, &v35);
  if ( v13 < 0 )
  {
    RaiseException(v13, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v35, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, v12);
  if ( ActivationFactory < 0 )
  {
    v19 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    return (unsigned int)ActivationFactory;
  }
  v21 = 0;
  v15 = v20;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v15, v22, &v21);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    return (unsigned int)ActivationFactory;
  }
  v16 = v21;
  v21 = 0;
  *a2 = v16;
  v17 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return 0;
}

```

## disassembly

```asm
0x1800247e4  mov     [rsp-8+arg_0], rbx
0x1800247e9  mov     [rsp-8+arg_10], rdi
0x1800247ee  push    rbp
0x1800247ef  lea     rbp, [rsp-30h]
0x1800247f4  sub     rsp, 130h
0x1800247fb  mov     rax, cs:__security_cookie
0x180024802  xor     rax, rsp
0x180024805  mov     [rbp+30h+var_10], rax
0x180024809  mov     rdi, rdx
0x18002480c  mov     [rbp+30h+string], 0
0x180024814  mov     ebx, 63h ; 'c'
0x180024819  mov     ecx, ebx; unsigned int
0x18002481b  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180024820  lea     edx, [rax-1]
0x180024823  cmp     eax, ebx
0x180024825  cmova   edx, ebx; length
0x180024828  lea     r9, [rbp+30h+string]; string
0x18002482c  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180024830  lea     rcx, aWindowsFoundat_14; "Windows.Foundation.Collections.IVector`"...
0x180024837  call    cs:__imp_WindowsCreateStringReference
0x18002483d  test    eax, eax
0x18002483f  js      loc_180024A1C
0x180024845  mov     [rbp+30h+var_58], 0
0x18002484d  mov     ebx, 67h ; 'g'
0x180024852  mov     ecx, ebx; unsigned int
0x180024854  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180024859  lea     edx, [rax-1]
0x18002485c  cmp     eax, ebx
0x18002485e  cmova   edx, ebx; length
0x180024861  lea     r9, [rbp+30h+var_58]; string
0x180024865  lea     r8, [rbp+30h+var_70]; hstringHeader
0x180024869  lea     rcx, aWindowsFoundat_17; "Windows.Foundation.Collections.IVectorV"...
0x180024870  call    cs:__imp_WindowsCreateStringReference
0x180024876  test    eax, eax
0x180024878  js      loc_180024A2F
0x18002487e  mov     [rbp+30h+var_38], 0
0x180024886  mov     ebx, 65h ; 'e'
0x18002488b  mov     ecx, ebx; unsigned int
0x18002488d  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180024892  lea     edx, [rax-1]
0x180024895  cmp     eax, ebx
0x180024897  cmova   edx, ebx; length
0x18002489a  lea     r9, [rbp+30h+var_38]; string
0x18002489e  lea     r8, [rbp+30h+var_50]; hstringHeader
0x1800248a2  lea     rcx, aWindowsFoundat_36; "Windows.Foundation.Collections.IIterato"...
0x1800248a9  call    cs:__imp_WindowsCreateStringReference
0x1800248af  test    eax, eax
0x1800248b1  js      loc_180024A42
0x1800248b7  mov     rax, [rbp+30h+string]
0x1800248bb  mov     [rsp+130h+var_100], rax
0x1800248c0  mov     rax, [rbp+30h+var_58]
0x1800248c4  mov     [rsp+130h+var_F8], rax
0x1800248c9  mov     rax, [rbp+30h+var_38]
0x1800248cd  mov     [rsp+130h+var_F0], rax
0x1800248d2  movups  xmm0, xmmword ptr cs:_GUID_67a7c5ca_83f6_44c6_a3b1_0eb69e41fa8a.Data1
0x1800248d9  movdqu  [rsp+130h+var_E8], xmm0
0x1800248df  movups  xmm1, xmmword ptr cs:_GUID_58dc4e4c_a84d_5ad6_a6d9_6ee477329c9f.Data1
0x1800248e6  movdqu  [rsp+130h+var_D8], xmm1
0x1800248ec  movups  xmm0, xmmword ptr cs:_GUID_199e065c_8195_55da_9c10_8aeaf9ac1062.Data1
0x1800248f3  movdqu  [rsp+130h+var_C8], xmm0
0x1800248f9  movups  xmm1, xmmword ptr cs:_GUID_7e5bb7ec_bbd7_5575_9a61_f5815fa22a0e.Data1
0x180024900  movdqu  [rsp+130h+var_B8], xmm1
0x180024906  movups  xmm0, xmmword ptr cs:_GUID_f080b0c9_a095_5b3a_a1dc_d17e7d2982c7.Data1
0x18002490d  movdqu  [rbp+30h+var_A8], xmm0
0x180024912  mov     [rsp+130h+var_110], 0
0x18002491b  lea     rcx, [rsp+130h+var_110]
0x180024920  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x180024925  mov     rbx, rax
0x180024928  mov     [rbp+30h+var_18], 0
0x180024930  lea     r9, [rbp+30h+var_18]; string
0x180024934  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180024938  mov     edx, 2Ch ; ','; length
0x18002493d  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180024944  call    cs:__imp_WindowsCreateStringReference
0x18002494a  test    eax, eax
0x18002494c  js      loc_180024A55
0x180024952  mov     r8, rbx
0x180024955  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18002495c  mov     rcx, [rbp+30h+var_18]
0x180024960  call    cs:__imp_RoGetActivationFactory
0x180024966  mov     ebx, eax
0x180024968  test    eax, eax
0x18002496a  js      loc_1800249F8
0x180024970  mov     [rsp+130h+var_108], 0
0x180024979  mov     rbx, [rsp+130h+var_110]
0x18002497e  lea     rcx, [rsp+130h+var_108]
0x180024983  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180024988  lea     r8, [rsp+130h+var_108]
0x18002498d  lea     rdx, [rsp+130h+var_100]
0x180024992  mov     rcx, rbx
0x180024995  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18002499a  mov     ebx, eax
0x18002499c  test    eax, eax
0x18002499e  js      loc_180024A68
0x1800249a4  mov     rax, [rsp+130h+var_108]
0x1800249a9  mov     [rsp+130h+var_108], 0
0x1800249b2  mov     [rdi], rax
0x1800249b5  mov     rcx, [rsp+130h+var_110]
0x1800249ba  test    rcx, rcx
0x1800249bd  jz      short loc_1800249D5
0x1800249bf  mov     [rsp+130h+var_110], 0
0x1800249c8  mov     rax, [rcx]
0x1800249cb  mov     rax, [rax+10h]
0x1800249cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249d4  nop
0x1800249d5  xor     eax, eax
0x1800249d7  mov     rcx, [rbp+30h+var_10]
0x1800249db  xor     rcx, rsp; StackCookie
0x1800249de  call    __security_check_cookie
0x1800249e3  lea     r11, [rsp+130h+var_s0]
0x1800249eb  mov     rbx, [r11+10h]
0x1800249ef  mov     rdi, [r11+20h]
0x1800249f3  mov     rsp, r11
0x1800249f6  pop     rbp
0x1800249f7  retn
0x1800249f8  mov     rcx, [rsp+130h+var_110]
0x1800249fd  test    rcx, rcx
0x180024a00  jz      short loc_180024A18
0x180024a02  mov     [rsp+130h+var_110], 0
0x180024a0b  mov     rdx, [rcx]
0x180024a0e  mov     rax, [rdx+10h]
0x180024a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a17  nop
0x180024a18  mov     eax, ebx
0x180024a1a  jmp     short loc_1800249D7
0x180024a1c  xor     r9d, r9d; lpArguments
0x180024a1f  xor     r8d, r8d; nNumberOfArguments
0x180024a22  lea     edx, [r9+1]; dwExceptionFlags
0x180024a26  mov     ecx, eax; dwExceptionCode
0x180024a28  call    cs:__imp_RaiseException
0x180024a2e  int     3; Trap to Debugger
0x180024a2f  xor     r9d, r9d; lpArguments
0x180024a32  xor     r8d, r8d; nNumberOfArguments
0x180024a35  lea     edx, [r9+1]; dwExceptionFlags
0x180024a39  mov     ecx, eax; dwExceptionCode
0x180024a3b  call    cs:__imp_RaiseException
0x180024a41  int     3; Trap to Debugger
0x180024a42  xor     r9d, r9d; lpArguments
0x180024a45  xor     r8d, r8d; nNumberOfArguments
0x180024a48  lea     edx, [r9+1]; dwExceptionFlags
0x180024a4c  mov     ecx, eax; dwExceptionCode
0x180024a4e  call    cs:__imp_RaiseException
0x180024a54  int     3; Trap to Debugger
0x180024a55  xor     r9d, r9d; lpArguments
0x180024a58  xor     r8d, r8d; nNumberOfArguments
0x180024a5b  lea     edx, [r9+1]; dwExceptionFlags
0x180024a5f  mov     ecx, eax; dwExceptionCode
0x180024a61  call    cs:__imp_RaiseException
0x180024a67  int     3; Trap to Debugger
0x180024a68  lea     rcx, [rsp+130h+var_108]
0x180024a6d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180024a72  lea     rcx, [rsp+130h+var_110]
0x180024a77  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180024a7c  jmp     short loc_180024A18
```
