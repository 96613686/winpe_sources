# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Credentials::WebAccountProvider,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccountProvider *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccountProvider *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccountProvider *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccountProvider *>,0> * *)

- ea: `0x180054d08`
- end: `0x180054fa2`
- name: `??$CreateExternalObjectVector@VWebAccountProvider@Credentials@Security@Windows@@V?$AgileVector@PEAVWebAccountProvider@Credentials@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccountProvider@Credentials@Security@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVWebAccountProvider@Credentials@Security@Windows@@@6784@$0A@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVWebAccountProvider@Credentials@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccountProvider@Credentials@Security@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVWebAccountProvider@Credentials@Security@Windows@@@6784@$0A@@1234@@Z`
- size: `666`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006e064`
- `0x1800e1e04`

## callees

- `0x180007350`
- `0x180024a84`
- `0x180024ab0`
- `0x180054d08`
- `0x18008e690`
- `0x18009b108`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180054f4c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180054f5f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180054f72`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180054f85`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180054f4c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180054f5f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180054f72`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180054f85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180054d5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180054d94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180054dcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180054e68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180054d5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180054d94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180054dcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180054e68`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180054e84`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180054e84`

## string_xrefs

- `0x180054d8d`: `Windows.Foundation.Collections.IVectorView`1<Windows.Security.Credentials.WebAccountProvider>`
- `0x180054d54`: `Windows.Foundation.Collections.IVector`1<Windows.Security.Credentials.WebAccountProvider>`
- `0x180054dc6`: `Windows.Foundation.Collections.IIterator`1<Windows.Security.Credentials.WebAccountProvider>`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Credentials::WebAccountProvider,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccountProvider *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccountProvider *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x59u);
  v4 = v3 - 1;
  if ( v3 > 0x59 )
    v4 = 89;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Security.Credentials.WebAccountProvider>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Du);
  v7 = v6 - 1;
  if ( v6 > 0x5D )
    v7 = 93;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Security.Credentials.WebAccountProvider>",
         v7,
         &v30,
         &v31);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v33 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Bu);
  v10 = v9 - 1;
  if ( v9 > 0x5B )
    v10 = 91;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Security.Credentials.WebAccountProvider>",
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
  v23 = GUID_29dcc8c3_7ab9_4a7c_a336_b942f9dbf7c7;
  v24 = GUID_496bc8c3_614a_59b5_9fa4_5d71b17faa19;
  v25 = GUID_fcce45dd_2213_54e6_b918_c0f31a8c6d54;
  v26 = GUID_7413656a_4784_5ede_bcd0_ea5ec4dd1a7b;
  v27 = GUID_e2e7ec4d_2889_5b44_8bde_2225b1253c3c;
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
0x180054d08  mov     [rsp-8+arg_0], rbx
0x180054d0d  mov     [rsp-8+arg_10], rdi
0x180054d12  push    rbp
0x180054d13  lea     rbp, [rsp-30h]
0x180054d18  sub     rsp, 130h
0x180054d1f  mov     rax, cs:__security_cookie
0x180054d26  xor     rax, rsp
0x180054d29  mov     [rbp+30h+var_10], rax
0x180054d2d  mov     rdi, rdx
0x180054d30  mov     [rbp+30h+string], 0
0x180054d38  mov     ebx, 59h ; 'Y'
0x180054d3d  mov     ecx, ebx; unsigned int
0x180054d3f  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180054d44  lea     edx, [rax-1]
0x180054d47  cmp     eax, ebx
0x180054d49  cmova   edx, ebx; length
0x180054d4c  lea     r9, [rbp+30h+string]; string
0x180054d50  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180054d54  lea     rcx, aWindowsFoundat_33; "Windows.Foundation.Collections.IVector`"...
0x180054d5b  call    cs:__imp_WindowsCreateStringReference
0x180054d61  test    eax, eax
0x180054d63  js      loc_180054F40
0x180054d69  mov     [rbp+30h+var_58], 0
0x180054d71  mov     ebx, 5Dh ; ']'
0x180054d76  mov     ecx, ebx; unsigned int
0x180054d78  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180054d7d  lea     edx, [rax-1]
0x180054d80  cmp     eax, ebx
0x180054d82  cmova   edx, ebx; length
0x180054d85  lea     r9, [rbp+30h+var_58]; string
0x180054d89  lea     r8, [rbp+30h+var_70]; hstringHeader
0x180054d8d  lea     rcx, aWindowsFoundat_27; "Windows.Foundation.Collections.IVectorV"...
0x180054d94  call    cs:__imp_WindowsCreateStringReference
0x180054d9a  test    eax, eax
0x180054d9c  js      loc_180054F53
0x180054da2  mov     [rbp+30h+var_38], 0
0x180054daa  mov     ebx, 5Bh ; '['
0x180054daf  mov     ecx, ebx; unsigned int
0x180054db1  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180054db6  lea     edx, [rax-1]
0x180054db9  cmp     eax, ebx
0x180054dbb  cmova   edx, ebx; length
0x180054dbe  lea     r9, [rbp+30h+var_38]; string
0x180054dc2  lea     r8, [rbp+30h+var_50]; hstringHeader
0x180054dc6  lea     rcx, aWindowsFoundat_8; "Windows.Foundation.Collections.IIterato"...
0x180054dcd  call    cs:__imp_WindowsCreateStringReference
0x180054dd3  test    eax, eax
0x180054dd5  js      loc_180054F66
0x180054ddb  mov     rax, [rbp+30h+string]
0x180054ddf  mov     [rsp+130h+var_100], rax
0x180054de4  mov     rax, [rbp+30h+var_58]
0x180054de8  mov     [rsp+130h+var_F8], rax
0x180054ded  mov     rax, [rbp+30h+var_38]
0x180054df1  mov     [rsp+130h+var_F0], rax
0x180054df6  movups  xmm0, xmmword ptr cs:_GUID_29dcc8c3_7ab9_4a7c_a336_b942f9dbf7c7.Data1
0x180054dfd  movdqu  [rsp+130h+var_E8], xmm0
0x180054e03  movups  xmm1, xmmword ptr cs:_GUID_496bc8c3_614a_59b5_9fa4_5d71b17faa19.Data1
0x180054e0a  movdqu  [rsp+130h+var_D8], xmm1
0x180054e10  movups  xmm0, xmmword ptr cs:_GUID_fcce45dd_2213_54e6_b918_c0f31a8c6d54.Data1
0x180054e17  movdqu  [rsp+130h+var_C8], xmm0
0x180054e1d  movups  xmm1, xmmword ptr cs:_GUID_7413656a_4784_5ede_bcd0_ea5ec4dd1a7b.Data1
0x180054e24  movdqu  [rsp+130h+var_B8], xmm1
0x180054e2a  movups  xmm0, xmmword ptr cs:_GUID_e2e7ec4d_2889_5b44_8bde_2225b1253c3c.Data1
0x180054e31  movdqu  [rbp+30h+var_A8], xmm0
0x180054e36  mov     [rsp+130h+var_110], 0
0x180054e3f  lea     rcx, [rsp+130h+var_110]
0x180054e44  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x180054e49  mov     rbx, rax
0x180054e4c  mov     [rbp+30h+var_18], 0
0x180054e54  lea     r9, [rbp+30h+var_18]; string
0x180054e58  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180054e5c  mov     edx, 2Ch ; ','; length
0x180054e61  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180054e68  call    cs:__imp_WindowsCreateStringReference
0x180054e6e  test    eax, eax
0x180054e70  js      loc_180054F79
0x180054e76  mov     r8, rbx
0x180054e79  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180054e80  mov     rcx, [rbp+30h+var_18]
0x180054e84  call    cs:__imp_RoGetActivationFactory
0x180054e8a  mov     ebx, eax
0x180054e8c  test    eax, eax
0x180054e8e  js      loc_180054F1C
0x180054e94  mov     [rsp+130h+var_108], 0
0x180054e9d  mov     rbx, [rsp+130h+var_110]
0x180054ea2  lea     rcx, [rsp+130h+var_108]
0x180054ea7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180054eac  lea     r8, [rsp+130h+var_108]
0x180054eb1  lea     rdx, [rsp+130h+var_100]
0x180054eb6  mov     rcx, rbx
0x180054eb9  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x180054ebe  mov     ebx, eax
0x180054ec0  test    eax, eax
0x180054ec2  js      loc_180054F8C
0x180054ec8  mov     rax, [rsp+130h+var_108]
0x180054ecd  mov     [rsp+130h+var_108], 0
0x180054ed6  mov     [rdi], rax
0x180054ed9  mov     rcx, [rsp+130h+var_110]
0x180054ede  test    rcx, rcx
0x180054ee1  jz      short loc_180054EF9
0x180054ee3  mov     [rsp+130h+var_110], 0
0x180054eec  mov     rax, [rcx]
0x180054eef  mov     rax, [rax+10h]
0x180054ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ef8  nop
0x180054ef9  xor     eax, eax
0x180054efb  mov     rcx, [rbp+30h+var_10]
0x180054eff  xor     rcx, rsp; StackCookie
0x180054f02  call    __security_check_cookie
0x180054f07  lea     r11, [rsp+130h+var_s0]
0x180054f0f  mov     rbx, [r11+10h]
0x180054f13  mov     rdi, [r11+20h]
0x180054f17  mov     rsp, r11
0x180054f1a  pop     rbp
0x180054f1b  retn
0x180054f1c  mov     rcx, [rsp+130h+var_110]
0x180054f21  test    rcx, rcx
0x180054f24  jz      short loc_180054F3C
0x180054f26  mov     [rsp+130h+var_110], 0
0x180054f2f  mov     rdx, [rcx]
0x180054f32  mov     rax, [rdx+10h]
0x180054f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054f3b  nop
0x180054f3c  mov     eax, ebx
0x180054f3e  jmp     short loc_180054EFB
0x180054f40  xor     r9d, r9d; lpArguments
0x180054f43  xor     r8d, r8d; nNumberOfArguments
0x180054f46  lea     edx, [r9+1]; dwExceptionFlags
0x180054f4a  mov     ecx, eax; dwExceptionCode
0x180054f4c  call    cs:__imp_RaiseException
0x180054f52  int     3; Trap to Debugger
0x180054f53  xor     r9d, r9d; lpArguments
0x180054f56  xor     r8d, r8d; nNumberOfArguments
0x180054f59  lea     edx, [r9+1]; dwExceptionFlags
0x180054f5d  mov     ecx, eax; dwExceptionCode
0x180054f5f  call    cs:__imp_RaiseException
0x180054f65  int     3; Trap to Debugger
0x180054f66  xor     r9d, r9d; lpArguments
0x180054f69  xor     r8d, r8d; nNumberOfArguments
0x180054f6c  lea     edx, [r9+1]; dwExceptionFlags
0x180054f70  mov     ecx, eax; dwExceptionCode
0x180054f72  call    cs:__imp_RaiseException
0x180054f78  int     3; Trap to Debugger
0x180054f79  xor     r9d, r9d; lpArguments
0x180054f7c  xor     r8d, r8d; nNumberOfArguments
0x180054f7f  lea     edx, [r9+1]; dwExceptionFlags
0x180054f83  mov     ecx, eax; dwExceptionCode
0x180054f85  call    cs:__imp_RaiseException
0x180054f8b  int     3; Trap to Debugger
0x180054f8c  lea     rcx, [rsp+130h+var_108]
0x180054f91  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180054f96  lea     rcx, [rsp+130h+var_110]
0x180054f9b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180054fa0  jmp     short loc_180054F3C
```
