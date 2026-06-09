# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::PackageUser,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PackageUser *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PackageUser *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PackageUser *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PackageUser *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PackageUser *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PackageUser *>,0> * *)

- ea: `0x18002e778`
- end: `0x18002ea37`
- name: `??$CreateExternalObjectVector@VPackageUser@StateRepository@Internal@Windows@@V?$AgileVector@PEAVPackageUser@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVPackageUser@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPackageUser@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVPackageUser@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVPackageUser@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPackageUser@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `703`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002e630`
- `0x1800bc48c`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x18002e778`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002e9f7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ea0a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ea1d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ea30`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002e9f7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ea0a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ea1d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ea30`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002e8f1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002e8f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002e7cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002e804`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002e83d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002e8d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002e7cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002e804`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002e83d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002e8d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::PackageUser,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PackageUser *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PackageUser *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PackageUser *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x56u);
  v4 = v3 - 1;
  if ( v3 > 0x56 )
    v4 = 86;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.PackageUser>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Au);
  v7 = v6 - 1;
  if ( v6 > 0x5A )
    v7 = 90;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.PackageUser>",
         v7,
         &v31,
         &v32);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v34 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x58u);
  v10 = v9 - 1;
  if ( v9 > 0x58 )
    v10 = 88;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.PackageUser>",
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
  v24 = GUID_2f38c0c7_84cb_4ab9_9c3c_c4561b0ccef6;
  v25 = GUID_6b5b4030_fbd3_51e7_af49_2ec6ee8c3793;
  v26 = GUID_19e9bb40_5d92_58ce_bcc2_ea49a8bb839c;
  v27 = GUID_71c97823_7ccf_513c_856e_41b641623987;
  v28 = GUID_06defc69_8ca3_57a3_a25a_fbdca57a98c2;
  v21 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v36 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v35, &v36);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    JUMPOUT(0x18002EA36LL);
  }
  ActivationFactory = RoGetActivationFactory(v36, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v21);
  if ( ActivationFactory < 0 )
  {
    v18 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return (unsigned int)ActivationFactory;
  }
  v22 = 0;
  v14 = v21;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v14, v23, &v22);
  if ( ActivationFactory < 0 )
  {
    v19 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return (unsigned int)ActivationFactory;
  }
  v15 = v22;
  v22 = 0;
  *a2 = v15;
  v16 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  return 0;
}

```

## disassembly

```asm
0x18002e778  mov     [rsp-8+arg_0], rbx
0x18002e77d  mov     [rsp-8+arg_10], rdi
0x18002e782  push    rbp
0x18002e783  lea     rbp, [rsp-30h]
0x18002e788  sub     rsp, 130h
0x18002e78f  mov     rax, cs:__security_cookie
0x18002e796  xor     rax, rsp
0x18002e799  mov     [rbp+30h+var_10], rax
0x18002e79d  mov     rdi, rdx
0x18002e7a0  mov     [rbp+30h+string], 0
0x18002e7a8  mov     ebx, 56h ; 'V'
0x18002e7ad  mov     ecx, ebx; unsigned int
0x18002e7af  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002e7b4  lea     edx, [rax-1]
0x18002e7b7  cmp     eax, ebx
0x18002e7b9  cmova   edx, ebx; length
0x18002e7bc  lea     r9, [rbp+30h+string]; string
0x18002e7c0  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18002e7c4  lea     rcx, aWindowsFoundat_19; "Windows.Foundation.Collections.IVector`"...
0x18002e7cb  call    cs:__imp_WindowsCreateStringReference
0x18002e7d1  test    eax, eax
0x18002e7d3  js      loc_18002E9EB
0x18002e7d9  mov     [rbp+30h+var_58], 0
0x18002e7e1  mov     ebx, 5Ah ; 'Z'
0x18002e7e6  mov     ecx, ebx; unsigned int
0x18002e7e8  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002e7ed  lea     edx, [rax-1]
0x18002e7f0  cmp     eax, ebx
0x18002e7f2  cmova   edx, ebx; length
0x18002e7f5  lea     r9, [rbp+30h+var_58]; string
0x18002e7f9  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18002e7fd  lea     rcx, aWindowsFoundat_204; "Windows.Foundation.Collections.IVectorV"...
0x18002e804  call    cs:__imp_WindowsCreateStringReference
0x18002e80a  test    eax, eax
0x18002e80c  js      loc_18002E9FE
0x18002e812  mov     [rbp+30h+var_38], 0
0x18002e81a  mov     ebx, 58h ; 'X'
0x18002e81f  mov     ecx, ebx; unsigned int
0x18002e821  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002e826  lea     edx, [rax-1]
0x18002e829  cmp     eax, ebx
0x18002e82b  cmova   edx, ebx; length
0x18002e82e  lea     r9, [rbp+30h+var_38]; string
0x18002e832  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18002e836  lea     rcx, aWindowsFoundat_16; "Windows.Foundation.Collections.IIterato"...
0x18002e83d  call    cs:__imp_WindowsCreateStringReference
0x18002e843  test    eax, eax
0x18002e845  js      loc_18002EA11
0x18002e84b  mov     rax, [rbp+30h+string]
0x18002e84f  mov     [rsp+130h+var_100], rax
0x18002e854  mov     rax, [rbp+30h+var_58]
0x18002e858  mov     [rsp+130h+var_F8], rax
0x18002e85d  mov     rax, [rbp+30h+var_38]
0x18002e861  mov     [rsp+130h+var_F0], rax
0x18002e866  movups  xmm0, xmmword ptr cs:_GUID_2f38c0c7_84cb_4ab9_9c3c_c4561b0ccef6.Data1
0x18002e86d  movdqu  [rsp+130h+var_E8], xmm0
0x18002e873  movups  xmm1, xmmword ptr cs:_GUID_6b5b4030_fbd3_51e7_af49_2ec6ee8c3793.Data1
0x18002e87a  movdqu  [rsp+130h+var_D8], xmm1
0x18002e880  movups  xmm0, xmmword ptr cs:_GUID_19e9bb40_5d92_58ce_bcc2_ea49a8bb839c.Data1
0x18002e887  movdqu  [rsp+130h+var_C8], xmm0
0x18002e88d  movups  xmm1, xmmword ptr cs:_GUID_71c97823_7ccf_513c_856e_41b641623987.Data1
0x18002e894  movdqu  [rsp+130h+var_B8], xmm1
0x18002e89a  movups  xmm0, xmmword ptr cs:_GUID_06defc69_8ca3_57a3_a25a_fbdca57a98c2.Data1
0x18002e8a1  movdqu  [rbp+30h+var_A8], xmm0
0x18002e8a6  mov     [rsp+130h+var_110], 0
0x18002e8af  lea     rcx, [rsp+130h+var_110]
0x18002e8b4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e8b9  mov     [rbp+30h+var_18], 0
0x18002e8c1  lea     r9, [rbp+30h+var_18]; string
0x18002e8c5  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18002e8c9  lea     edx, [rbx-2Ch]; length
0x18002e8cc  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18002e8d3  call    cs:__imp_WindowsCreateStringReference
0x18002e8d9  test    eax, eax
0x18002e8db  js      loc_18002EA24
0x18002e8e1  lea     r8, [rsp+130h+var_110]
0x18002e8e6  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18002e8ed  mov     rcx, [rbp+30h+var_18]
0x18002e8f1  call    cs:__imp_RoGetActivationFactory
0x18002e8f7  mov     ebx, eax
0x18002e8f9  test    eax, eax
0x18002e8fb  js      loc_18002E985
0x18002e901  mov     [rsp+130h+var_108], 0
0x18002e90a  mov     rbx, [rsp+130h+var_110]
0x18002e90f  lea     rcx, [rsp+130h+var_108]
0x18002e914  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e919  lea     r8, [rsp+130h+var_108]
0x18002e91e  lea     rdx, [rsp+130h+var_100]
0x18002e923  mov     rcx, rbx
0x18002e926  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18002e92b  mov     ebx, eax
0x18002e92d  test    eax, eax
0x18002e92f  js      short loc_18002E9A9
0x18002e931  mov     rax, [rsp+130h+var_108]
0x18002e936  mov     [rsp+130h+var_108], 0
0x18002e93f  mov     [rdi], rax
0x18002e942  mov     rcx, [rsp+130h+var_110]
0x18002e947  test    rcx, rcx
0x18002e94a  jz      short loc_18002E962
0x18002e94c  mov     [rsp+130h+var_110], 0
0x18002e955  mov     rax, [rcx]
0x18002e958  mov     rax, [rax+10h]
0x18002e95c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e961  nop
0x18002e962  xor     eax, eax
0x18002e964  mov     rcx, [rbp+30h+var_10]
0x18002e968  xor     rcx, rsp; StackCookie
0x18002e96b  call    __security_check_cookie
0x18002e970  lea     r11, [rsp+130h+var_s0]
0x18002e978  mov     rbx, [r11+10h]
0x18002e97c  mov     rdi, [r11+20h]
0x18002e980  mov     rsp, r11
0x18002e983  pop     rbp
0x18002e984  retn
0x18002e985  mov     rcx, [rsp+130h+var_110]
0x18002e98a  test    rcx, rcx
0x18002e98d  jz      short loc_18002E9A5
0x18002e98f  mov     [rsp+130h+var_110], 0
0x18002e998  mov     rdx, [rcx]
0x18002e99b  mov     rax, [rdx+10h]
0x18002e99f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9a4  nop
0x18002e9a5  mov     eax, ebx
0x18002e9a7  jmp     short loc_18002E964
0x18002e9a9  mov     rcx, [rsp+130h+var_108]
0x18002e9ae  test    rcx, rcx
0x18002e9b1  jz      short loc_18002E9C9
0x18002e9b3  mov     [rsp+130h+var_108], 0
0x18002e9bc  mov     rdx, [rcx]
0x18002e9bf  mov     rax, [rdx+10h]
0x18002e9c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9c8  nop
0x18002e9c9  mov     rcx, [rsp+130h+var_110]
0x18002e9ce  test    rcx, rcx
0x18002e9d1  jz      short loc_18002E9E9
0x18002e9d3  mov     [rsp+130h+var_110], 0
0x18002e9dc  mov     rax, [rcx]
0x18002e9df  mov     rax, [rax+10h]
0x18002e9e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9e8  nop
0x18002e9e9  jmp     short loc_18002E9A5
0x18002e9eb  xor     r9d, r9d; lpArguments
0x18002e9ee  xor     r8d, r8d; nNumberOfArguments
0x18002e9f1  lea     edx, [r9+1]; dwExceptionFlags
0x18002e9f5  mov     ecx, eax; dwExceptionCode
0x18002e9f7  call    cs:__imp_RaiseException
0x18002e9fd  int     3; Trap to Debugger
0x18002e9fe  xor     r9d, r9d; lpArguments
0x18002ea01  xor     r8d, r8d; nNumberOfArguments
0x18002ea04  lea     edx, [r9+1]; dwExceptionFlags
0x18002ea08  mov     ecx, eax; dwExceptionCode
0x18002ea0a  call    cs:__imp_RaiseException
0x18002ea10  int     3; Trap to Debugger
0x18002ea11  xor     r9d, r9d; lpArguments
0x18002ea14  xor     r8d, r8d; nNumberOfArguments
0x18002ea17  lea     edx, [r9+1]; dwExceptionFlags
0x18002ea1b  mov     ecx, eax; dwExceptionCode
0x18002ea1d  call    cs:__imp_RaiseException
0x18002ea23  int     3; Trap to Debugger
0x18002ea24  xor     r9d, r9d; lpArguments
0x18002ea27  xor     r8d, r8d; nNumberOfArguments
0x18002ea2a  lea     edx, [r9+1]; dwExceptionFlags
0x18002ea2e  mov     ecx, eax; dwExceptionCode
0x18002ea30  call    cs:__imp_RaiseException
```
