# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::System::User,Windows::Foundation::Collections::Internal::Vector<Windows::System::User *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::User *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::User *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::System::User *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::System::User *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::User *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::User *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::System::User *>> * *)

- ea: `0x1800186e8`
- end: `0x1800189a7`
- name: `??$CreateExternalObjectVector@VUser@System@Windows@@V?$Vector@PEAVUser@System@Windows@@U?$DefaultEqualityPredicate@PEAVUser@System@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAVUser@System@Windows@@@5673@U?$DefaultVectorOptions@PEAVUser@System@Windows@@@5673@@Internal@Collections@Foundation@3@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVUser@System@Windows@@U?$DefaultEqualityPredicate@PEAVUser@System@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAVUser@System@Windows@@@5673@U?$DefaultVectorOptions@PEAVUser@System@Windows@@@5673@@1234@@Z`
- size: `703`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180044960`
- `0x180044bf0`

## callees

- `0x18000ce48`
- `0x1800186e8`
- `0x1800189b0`
- `0x1800778fc`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018967`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001897a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001898d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800189a0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018967`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001897a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001898d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800189a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001873b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018774`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800187ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018843`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001873b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018774`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800187ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018843`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180018861`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180018861`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::System::User,Windows::Foundation::Collections::Internal::Vector<Windows::System::User *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::User *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::User *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::System::User *>>>(
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
  HRESULT v12; // eax
  int ActivationFactory; // ebx
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v22; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v23[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v24; // [rsp+48h] [rbp-B8h]
  GUID v25; // [rsp+58h] [rbp-A8h]
  GUID v26; // [rsp+68h] [rbp-98h]
  GUID v27; // [rsp+78h] [rbp-88h]
  GUID v28; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v31; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v32; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v33; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v34; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v35; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v36; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x3Du);
  v4 = v3 - 1;
  if ( v3 > 0x3D )
    v4 = 61;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.System.User>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x41u);
  v7 = v6 - 1;
  if ( v6 > 0x41 )
    v7 = 65;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.System.User>",
         v7,
         &v31,
         &v32);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v34 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x3Fu);
  v10 = v9 - 1;
  if ( v9 > 0x3F )
    v10 = 63;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.System.User>",
          v10,
          &v33,
          &v34);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v23[0] = string;
  v23[1] = v32;
  v23[2] = v34;
  v24 = GUID_df9a26c6_e746_4bcd_b5d4_120103c4209b;
  v25 = GUID_8cb35b00_501c_5532_a664_38c9c429bb1a;
  v26 = GUID_8cbd762a_1222_5ee5_b745_489e7a42c6ec;
  v27 = GUID_d1bacd1f_0376_5823_8c29_1d45b9f4c191;
  v28 = GUID_326fe162_582b_5659_b8a4_68ff0f525745;
  v21 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
  v36 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v35, &v36);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    JUMPOUT(0x1800189A6LL);
  }
  ActivationFactory = RoGetActivationFactory(v36, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v21);
  if ( ActivationFactory < 0 )
  {
    v20 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return (unsigned int)ActivationFactory;
  }
  v22 = 0;
  v14 = v21;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}(v14, v23, &v22);
  if ( ActivationFactory < 0 )
  {
    v15 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v16 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return (unsigned int)ActivationFactory;
  }
  v18 = v22;
  v22 = 0;
  *a2 = v18;
  v19 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  return 0;
}

```

## disassembly

```asm
0x1800186e8  mov     [rsp-8+arg_0], rbx
0x1800186ed  mov     [rsp-8+arg_10], rdi
0x1800186f2  push    rbp
0x1800186f3  lea     rbp, [rsp-30h]
0x1800186f8  sub     rsp, 130h
0x1800186ff  mov     rax, cs:__security_cookie
0x180018706  xor     rax, rsp
0x180018709  mov     [rbp+30h+var_10], rax
0x18001870d  mov     rdi, rdx
0x180018710  mov     [rbp+30h+string], 0
0x180018718  mov     ebx, 3Dh ; '='
0x18001871d  mov     ecx, ebx; unsigned int
0x18001871f  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180018724  lea     edx, [rax-1]
0x180018727  cmp     eax, ebx
0x180018729  cmova   edx, ebx; length
0x18001872c  lea     r9, [rbp+30h+string]; string
0x180018730  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180018734  lea     rcx, aWindowsFoundat_8; "Windows.Foundation.Collections.IVector`"...
0x18001873b  call    cs:__imp_WindowsCreateStringReference
0x180018741  test    eax, eax
0x180018743  js      loc_18001895B
0x180018749  mov     [rbp+30h+var_58], 0
0x180018751  mov     ebx, 41h ; 'A'
0x180018756  mov     ecx, ebx; unsigned int
0x180018758  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18001875d  lea     edx, [rax-1]
0x180018760  cmp     eax, ebx
0x180018762  cmova   edx, ebx; length
0x180018765  lea     r9, [rbp+30h+var_58]; string
0x180018769  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18001876d  lea     rcx, aWindowsFoundat_5; "Windows.Foundation.Collections.IVectorV"...
0x180018774  call    cs:__imp_WindowsCreateStringReference
0x18001877a  test    eax, eax
0x18001877c  js      loc_18001896E
0x180018782  mov     [rbp+30h+var_38], 0
0x18001878a  mov     ebx, 3Fh ; '?'
0x18001878f  mov     ecx, ebx; unsigned int
0x180018791  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180018796  lea     edx, [rax-1]
0x180018799  cmp     eax, ebx
0x18001879b  cmova   edx, ebx; length
0x18001879e  lea     r9, [rbp+30h+var_38]; string
0x1800187a2  lea     r8, [rbp+30h+var_50]; hstringHeader
0x1800187a6  lea     rcx, aWindowsFoundat_16; "Windows.Foundation.Collections.IIterato"...
0x1800187ad  call    cs:__imp_WindowsCreateStringReference
0x1800187b3  test    eax, eax
0x1800187b5  js      loc_180018981
0x1800187bb  mov     rax, [rbp+30h+string]
0x1800187bf  mov     [rsp+130h+var_100], rax
0x1800187c4  mov     rax, [rbp+30h+var_58]
0x1800187c8  mov     [rsp+130h+var_F8], rax
0x1800187cd  mov     rax, [rbp+30h+var_38]
0x1800187d1  mov     [rsp+130h+var_F0], rax
0x1800187d6  movups  xmm0, xmmword ptr cs:_GUID_df9a26c6_e746_4bcd_b5d4_120103c4209b.Data1
0x1800187dd  movdqu  [rsp+130h+var_E8], xmm0
0x1800187e3  movups  xmm1, xmmword ptr cs:_GUID_8cb35b00_501c_5532_a664_38c9c429bb1a.Data1
0x1800187ea  movdqu  [rsp+130h+var_D8], xmm1
0x1800187f0  movups  xmm0, xmmword ptr cs:_GUID_8cbd762a_1222_5ee5_b745_489e7a42c6ec.Data1
0x1800187f7  movdqu  [rsp+130h+var_C8], xmm0
0x1800187fd  movups  xmm1, xmmword ptr cs:_GUID_d1bacd1f_0376_5823_8c29_1d45b9f4c191.Data1
0x180018804  movdqu  [rsp+130h+var_B8], xmm1
0x18001880a  movups  xmm0, xmmword ptr cs:_GUID_326fe162_582b_5659_b8a4_68ff0f525745.Data1
0x180018811  movdqu  [rbp+30h+var_A8], xmm0
0x180018816  mov     [rsp+130h+var_110], 0
0x18001881f  lea     rcx, [rsp+130h+var_110]
0x180018824  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018829  mov     [rbp+30h+var_18], 0
0x180018831  lea     r9, [rbp+30h+var_18]; string
0x180018835  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180018839  lea     edx, [rbx-13h]; length
0x18001883c  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180018843  call    cs:__imp_WindowsCreateStringReference
0x180018849  test    eax, eax
0x18001884b  js      loc_180018994
0x180018851  lea     r8, [rsp+130h+var_110]
0x180018856  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18001885d  mov     rcx, [rbp+30h+var_18]
0x180018861  call    cs:__imp_RoGetActivationFactory
0x180018867  mov     ebx, eax
0x180018869  test    eax, eax
0x18001886b  js      loc_180018939
0x180018871  mov     [rsp+130h+var_108], 0
0x18001887a  mov     rbx, [rsp+130h+var_110]
0x18001887f  lea     rcx, [rsp+130h+var_108]
0x180018884  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018889  lea     r8, [rsp+130h+var_108]
0x18001888e  lea     rdx, [rsp+130h+var_100]
0x180018893  mov     rcx, rbx
0x180018896  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x18001889b  mov     ebx, eax
0x18001889d  test    eax, eax
0x18001889f  jns     short loc_180018904
0x1800188a1  mov     rcx, [rsp+130h+var_108]
0x1800188a6  test    rcx, rcx
0x1800188a9  jz      short loc_1800188C1
0x1800188ab  mov     [rsp+130h+var_108], 0
0x1800188b4  mov     rdx, [rcx]
0x1800188b7  mov     rax, [rdx+10h]
0x1800188bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188c0  nop
0x1800188c1  mov     rcx, [rsp+130h+var_110]
0x1800188c6  test    rcx, rcx
0x1800188c9  jz      short loc_1800188E1
0x1800188cb  mov     [rsp+130h+var_110], 0
0x1800188d4  mov     rax, [rcx]
0x1800188d7  mov     rax, [rax+10h]
0x1800188db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188e0  nop
0x1800188e1  mov     eax, ebx
0x1800188e3  mov     rcx, [rbp+30h+var_10]
0x1800188e7  xor     rcx, rsp; StackCookie
0x1800188ea  call    __security_check_cookie
0x1800188ef  lea     r11, [rsp+130h+var_s0]
0x1800188f7  mov     rbx, [r11+10h]
0x1800188fb  mov     rdi, [r11+20h]
0x1800188ff  mov     rsp, r11
0x180018902  pop     rbp
0x180018903  retn
0x180018904  mov     rax, [rsp+130h+var_108]
0x180018909  mov     [rsp+130h+var_108], 0
0x180018912  mov     [rdi], rax
0x180018915  mov     rcx, [rsp+130h+var_110]
0x18001891a  test    rcx, rcx
0x18001891d  jz      short loc_180018935
0x18001891f  mov     [rsp+130h+var_110], 0
0x180018928  mov     rax, [rcx]
0x18001892b  mov     rax, [rax+10h]
0x18001892f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018934  nop
0x180018935  xor     eax, eax
0x180018937  jmp     short loc_1800188E3
0x180018939  mov     rcx, [rsp+130h+var_110]
0x18001893e  test    rcx, rcx
0x180018941  jz      short loc_180018959
0x180018943  mov     [rsp+130h+var_110], 0
0x18001894c  mov     rdx, [rcx]
0x18001894f  mov     rax, [rdx+10h]
0x180018953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018958  nop
0x180018959  jmp     short loc_1800188E1
0x18001895b  xor     r9d, r9d; lpArguments
0x18001895e  xor     r8d, r8d; nNumberOfArguments
0x180018961  lea     edx, [r9+1]; dwExceptionFlags
0x180018965  mov     ecx, eax; dwExceptionCode
0x180018967  call    cs:__imp_RaiseException
0x18001896d  int     3; Trap to Debugger
0x18001896e  xor     r9d, r9d; lpArguments
0x180018971  xor     r8d, r8d; nNumberOfArguments
0x180018974  lea     edx, [r9+1]; dwExceptionFlags
0x180018978  mov     ecx, eax; dwExceptionCode
0x18001897a  call    cs:__imp_RaiseException
0x180018980  int     3; Trap to Debugger
0x180018981  xor     r9d, r9d; lpArguments
0x180018984  xor     r8d, r8d; nNumberOfArguments
0x180018987  lea     edx, [r9+1]; dwExceptionFlags
0x18001898b  mov     ecx, eax; dwExceptionCode
0x18001898d  call    cs:__imp_RaiseException
0x180018993  int     3; Trap to Debugger
0x180018994  xor     r9d, r9d; lpArguments
0x180018997  xor     r8d, r8d; nNumberOfArguments
0x18001899a  lea     edx, [r9+1]; dwExceptionFlags
0x18001899e  mov     ecx, eax; dwExceptionCode
0x1800189a0  call    cs:__imp_RaiseException
```
