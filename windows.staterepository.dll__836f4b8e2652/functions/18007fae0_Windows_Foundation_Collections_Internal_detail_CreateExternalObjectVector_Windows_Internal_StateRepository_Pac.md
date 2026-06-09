# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::PackageFamily,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PackageFamily *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PackageFamily *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PackageFamily *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PackageFamily *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PackageFamily *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PackageFamily *>,0> * *)

- ea: `0x18007fae0`
- end: `0x18007fd77`
- name: `??$CreateExternalObjectVector@VPackageFamily@StateRepository@Internal@Windows@@V?$AgileVector@PEAVPackageFamily@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVPackageFamily@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPackageFamily@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVPackageFamily@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVPackageFamily@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPackageFamily@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `663`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18007f99c`
- `0x1801dfa50`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x18007fae0`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007fd21`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007fd34`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007fd47`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007fd5a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007fd21`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007fd34`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007fd47`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007fd5a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007fc59`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007fc59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007fb33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007fb6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007fba5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007fc3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007fb33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007fb6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007fba5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007fc3b`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::PackageFamily,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PackageFamily *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PackageFamily *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PackageFamily *>,0>>(
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
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v18; // rcx
  __int64 v19; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v21[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v22; // [rsp+48h] [rbp-B8h]
  GUID v23; // [rsp+58h] [rbp-A8h]
  GUID v24; // [rsp+68h] [rbp-98h]
  GUID v25; // [rsp+78h] [rbp-88h]
  GUID v26; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v29; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v30; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v31; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v32; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v33; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v34; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x58u);
  v4 = v3 - 1;
  if ( v3 > 0x58 )
    v4 = 88;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.PackageFamily>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v30 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Cu);
  v7 = v6 - 1;
  if ( v6 > 0x5C )
    v7 = 92;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.PackageFamily>",
         v7,
         &v29,
         &v30);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Au);
  v10 = v9 - 1;
  if ( v9 > 0x5A )
    v10 = 90;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.PackageFamily>",
          v10,
          &v31,
          &v32);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v21[0] = string;
  v21[1] = v30;
  v21[2] = v32;
  v22 = GUID_4fe0a6ff_aa6b_4cb3_9241_dd477a7abb84;
  v23 = GUID_d934d116_18b3_51f0_ac3e_6c1da0265ece;
  v24 = GUID_2f2812b4_707b_509a_8231_f187997a39a5;
  v25 = GUID_f41bc2e6_d45c_5958_87e2_88d9702253bf;
  v26 = GUID_d3496b2c_382a_594c_96f3_a1132146f538;
  v19 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  v34 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v33, &v34);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v34, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v19);
  if ( ActivationFactory < 0 )
  {
    v18 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return (unsigned int)ActivationFactory;
  }
  v20 = 0;
  v14 = v19;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v14, v21, &v20);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
    return (unsigned int)ActivationFactory;
  }
  v15 = v20;
  v20 = 0;
  *a2 = v15;
  v16 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  return 0;
}

```

## disassembly

```asm
0x18007fae0  mov     [rsp-8+arg_0], rbx
0x18007fae5  mov     [rsp-8+arg_10], rdi
0x18007faea  push    rbp
0x18007faeb  lea     rbp, [rsp-30h]
0x18007faf0  sub     rsp, 130h
0x18007faf7  mov     rax, cs:__security_cookie
0x18007fafe  xor     rax, rsp
0x18007fb01  mov     [rbp+30h+var_10], rax
0x18007fb05  mov     rdi, rdx
0x18007fb08  mov     [rbp+30h+string], 0
0x18007fb10  mov     ebx, 58h ; 'X'
0x18007fb15  mov     ecx, ebx; unsigned int
0x18007fb17  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18007fb1c  lea     edx, [rax-1]
0x18007fb1f  cmp     eax, ebx
0x18007fb21  cmova   edx, ebx; length
0x18007fb24  lea     r9, [rbp+30h+string]; string
0x18007fb28  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18007fb2c  lea     rcx, aWindowsFoundat_214; "Windows.Foundation.Collections.IVector`"...
0x18007fb33  call    cs:__imp_WindowsCreateStringReference
0x18007fb39  test    eax, eax
0x18007fb3b  js      loc_18007FD15
0x18007fb41  mov     [rbp+30h+var_58], 0
0x18007fb49  mov     ebx, 5Ch ; '\'
0x18007fb4e  mov     ecx, ebx; unsigned int
0x18007fb50  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18007fb55  lea     edx, [rax-1]
0x18007fb58  cmp     eax, ebx
0x18007fb5a  cmova   edx, ebx; length
0x18007fb5d  lea     r9, [rbp+30h+var_58]; string
0x18007fb61  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18007fb65  lea     rcx, aWindowsFoundat; "Windows.Foundation.Collections.IVectorV"...
0x18007fb6c  call    cs:__imp_WindowsCreateStringReference
0x18007fb72  test    eax, eax
0x18007fb74  js      loc_18007FD28
0x18007fb7a  mov     [rbp+30h+var_38], 0
0x18007fb82  mov     ebx, 5Ah ; 'Z'
0x18007fb87  mov     ecx, ebx; unsigned int
0x18007fb89  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18007fb8e  lea     edx, [rax-1]
0x18007fb91  cmp     eax, ebx
0x18007fb93  cmova   edx, ebx; length
0x18007fb96  lea     r9, [rbp+30h+var_38]; string
0x18007fb9a  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18007fb9e  lea     rcx, aWindowsFoundat_111; "Windows.Foundation.Collections.IIterato"...
0x18007fba5  call    cs:__imp_WindowsCreateStringReference
0x18007fbab  test    eax, eax
0x18007fbad  js      loc_18007FD3B
0x18007fbb3  mov     rax, [rbp+30h+string]
0x18007fbb7  mov     [rsp+130h+var_100], rax
0x18007fbbc  mov     rax, [rbp+30h+var_58]
0x18007fbc0  mov     [rsp+130h+var_F8], rax
0x18007fbc5  mov     rax, [rbp+30h+var_38]
0x18007fbc9  mov     [rsp+130h+var_F0], rax
0x18007fbce  movups  xmm0, xmmword ptr cs:_GUID_4fe0a6ff_aa6b_4cb3_9241_dd477a7abb84.Data1
0x18007fbd5  movdqu  [rsp+130h+var_E8], xmm0
0x18007fbdb  movups  xmm1, xmmword ptr cs:_GUID_d934d116_18b3_51f0_ac3e_6c1da0265ece.Data1
0x18007fbe2  movdqu  [rsp+130h+var_D8], xmm1
0x18007fbe8  movups  xmm0, xmmword ptr cs:_GUID_2f2812b4_707b_509a_8231_f187997a39a5.Data1
0x18007fbef  movdqu  [rsp+130h+var_C8], xmm0
0x18007fbf5  movups  xmm1, xmmword ptr cs:_GUID_f41bc2e6_d45c_5958_87e2_88d9702253bf.Data1
0x18007fbfc  movdqu  [rsp+130h+var_B8], xmm1
0x18007fc02  movups  xmm0, xmmword ptr cs:_GUID_d3496b2c_382a_594c_96f3_a1132146f538.Data1
0x18007fc09  movdqu  [rbp+30h+var_A8], xmm0
0x18007fc0e  mov     [rsp+130h+var_110], 0
0x18007fc17  lea     rcx, [rsp+130h+var_110]
0x18007fc1c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007fc21  mov     [rbp+30h+var_18], 0
0x18007fc29  lea     r9, [rbp+30h+var_18]; string
0x18007fc2d  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18007fc31  lea     edx, [rbx-2Eh]; length
0x18007fc34  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18007fc3b  call    cs:__imp_WindowsCreateStringReference
0x18007fc41  test    eax, eax
0x18007fc43  js      loc_18007FD4E
0x18007fc49  lea     r8, [rsp+130h+var_110]
0x18007fc4e  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18007fc55  mov     rcx, [rbp+30h+var_18]
0x18007fc59  call    cs:__imp_RoGetActivationFactory
0x18007fc5f  mov     ebx, eax
0x18007fc61  test    eax, eax
0x18007fc63  js      loc_18007FCF1
0x18007fc69  mov     [rsp+130h+var_108], 0
0x18007fc72  mov     rbx, [rsp+130h+var_110]
0x18007fc77  lea     rcx, [rsp+130h+var_108]
0x18007fc7c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007fc81  lea     r8, [rsp+130h+var_108]
0x18007fc86  lea     rdx, [rsp+130h+var_100]
0x18007fc8b  mov     rcx, rbx
0x18007fc8e  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18007fc93  mov     ebx, eax
0x18007fc95  test    eax, eax
0x18007fc97  js      loc_18007FD61
0x18007fc9d  mov     rax, [rsp+130h+var_108]
0x18007fca2  mov     [rsp+130h+var_108], 0
0x18007fcab  mov     [rdi], rax
0x18007fcae  mov     rcx, [rsp+130h+var_110]
0x18007fcb3  test    rcx, rcx
0x18007fcb6  jz      short loc_18007FCCE
0x18007fcb8  mov     [rsp+130h+var_110], 0
0x18007fcc1  mov     rax, [rcx]
0x18007fcc4  mov     rax, [rax+10h]
0x18007fcc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fccd  nop
0x18007fcce  xor     eax, eax
0x18007fcd0  mov     rcx, [rbp+30h+var_10]
0x18007fcd4  xor     rcx, rsp; StackCookie
0x18007fcd7  call    __security_check_cookie
0x18007fcdc  lea     r11, [rsp+130h+var_s0]
0x18007fce4  mov     rbx, [r11+10h]
0x18007fce8  mov     rdi, [r11+20h]
0x18007fcec  mov     rsp, r11
0x18007fcef  pop     rbp
0x18007fcf0  retn
0x18007fcf1  mov     rcx, [rsp+130h+var_110]
0x18007fcf6  test    rcx, rcx
0x18007fcf9  jz      short loc_18007FD11
0x18007fcfb  mov     [rsp+130h+var_110], 0
0x18007fd04  mov     rdx, [rcx]
0x18007fd07  mov     rax, [rdx+10h]
0x18007fd0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fd10  nop
0x18007fd11  mov     eax, ebx
0x18007fd13  jmp     short loc_18007FCD0
0x18007fd15  xor     r9d, r9d; lpArguments
0x18007fd18  xor     r8d, r8d; nNumberOfArguments
0x18007fd1b  lea     edx, [r9+1]; dwExceptionFlags
0x18007fd1f  mov     ecx, eax; dwExceptionCode
0x18007fd21  call    cs:__imp_RaiseException
0x18007fd27  int     3; Trap to Debugger
0x18007fd28  xor     r9d, r9d; lpArguments
0x18007fd2b  xor     r8d, r8d; nNumberOfArguments
0x18007fd2e  lea     edx, [r9+1]; dwExceptionFlags
0x18007fd32  mov     ecx, eax; dwExceptionCode
0x18007fd34  call    cs:__imp_RaiseException
0x18007fd3a  int     3; Trap to Debugger
0x18007fd3b  xor     r9d, r9d; lpArguments
0x18007fd3e  xor     r8d, r8d; nNumberOfArguments
0x18007fd41  lea     edx, [r9+1]; dwExceptionFlags
0x18007fd45  mov     ecx, eax; dwExceptionCode
0x18007fd47  call    cs:__imp_RaiseException
0x18007fd4d  int     3; Trap to Debugger
0x18007fd4e  xor     r9d, r9d; lpArguments
0x18007fd51  xor     r8d, r8d; nNumberOfArguments
0x18007fd54  lea     edx, [r9+1]; dwExceptionFlags
0x18007fd58  mov     ecx, eax; dwExceptionCode
0x18007fd5a  call    cs:__imp_RaiseException
0x18007fd60  int     3; Trap to Debugger
0x18007fd61  lea     rcx, [rsp+130h+var_108]
0x18007fd66  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007fd6b  lea     rcx, [rsp+130h+var_110]
0x18007fd70  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007fd75  jmp     short loc_18007FD11
```
