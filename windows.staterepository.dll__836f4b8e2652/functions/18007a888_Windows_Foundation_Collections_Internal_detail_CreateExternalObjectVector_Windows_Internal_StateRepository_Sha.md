# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::SharedPackageContainer,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::SharedPackageContainer *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::SharedPackageContainer *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::SharedPackageContainer *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::SharedPackageContainer *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::SharedPackageContainer *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::SharedPackageContainer *>,0> * *)

- ea: `0x18007a888`
- end: `0x18007ab47`
- name: `??$CreateExternalObjectVector@VSharedPackageContainer@StateRepository@Internal@Windows@@V?$AgileVector@PEAVSharedPackageContainer@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVSharedPackageContainer@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVSharedPackageContainer@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVSharedPackageContainer@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVSharedPackageContainer@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVSharedPackageContainer@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `703`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18007a730`
- `0x1801c5004`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x18007a888`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007ab07`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007ab1a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007ab2d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007ab40`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007ab07`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007ab1a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007ab2d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007ab40`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007aa01`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007aa01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007a8db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007a914`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007a94d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007a9e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007a8db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007a914`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007a94d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007a9e3`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::SharedPackageContainer,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::SharedPackageContainer *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::SharedPackageContainer *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::SharedPackageContainer *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x61u);
  v4 = v3 - 1;
  if ( v3 > 0x61 )
    v4 = 97;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.SharedPackageContainer>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x65u);
  v7 = v6 - 1;
  if ( v6 > 0x65 )
    v7 = 101;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.SharedPackageContainer>",
         v7,
         &v31,
         &v32);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v34 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x63u);
  v10 = v9 - 1;
  if ( v9 > 0x63 )
    v10 = 99;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.SharedPackageContainer>",
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
  v24 = GUID_3a9f4b3c_f803_495c_bc57_de39766105ab;
  v25 = GUID_a1bc3f40_026d_5641_9d1c_7f029e8493f6;
  v26 = GUID_1a5ebfa0_c9ee_58fe_8406_6f04e6419189;
  v27 = GUID_69d2049f_bd36_5ebe_b863_5bd424df2e5e;
  v28 = GUID_d283e6fd_b135_5290_91d6_c1b47a44b78f;
  v21 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v36 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v35, &v36);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    JUMPOUT(0x18007AB46LL);
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
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v14, v23, &v22);
  if ( ActivationFactory < 0 )
  {
    v18 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
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
0x18007a888  mov     [rsp-8+arg_0], rbx
0x18007a88d  mov     [rsp-8+arg_10], rdi
0x18007a892  push    rbp
0x18007a893  lea     rbp, [rsp-30h]
0x18007a898  sub     rsp, 130h
0x18007a89f  mov     rax, cs:__security_cookie
0x18007a8a6  xor     rax, rsp
0x18007a8a9  mov     [rbp+30h+var_10], rax
0x18007a8ad  mov     rdi, rdx
0x18007a8b0  mov     [rbp+30h+string], 0
0x18007a8b8  mov     ebx, 61h ; 'a'
0x18007a8bd  mov     ecx, ebx; unsigned int
0x18007a8bf  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18007a8c4  lea     edx, [rax-1]
0x18007a8c7  cmp     eax, ebx
0x18007a8c9  cmova   edx, ebx; length
0x18007a8cc  lea     r9, [rbp+30h+string]; string
0x18007a8d0  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18007a8d4  lea     rcx, aWindowsFoundat_185; "Windows.Foundation.Collections.IVector`"...
0x18007a8db  call    cs:__imp_WindowsCreateStringReference
0x18007a8e1  test    eax, eax
0x18007a8e3  js      loc_18007AAFB
0x18007a8e9  mov     [rbp+30h+var_58], 0
0x18007a8f1  mov     ebx, 65h ; 'e'
0x18007a8f6  mov     ecx, ebx; unsigned int
0x18007a8f8  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18007a8fd  lea     edx, [rax-1]
0x18007a900  cmp     eax, ebx
0x18007a902  cmova   edx, ebx; length
0x18007a905  lea     r9, [rbp+30h+var_58]; string
0x18007a909  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18007a90d  lea     rcx, aWindowsFoundat_182; "Windows.Foundation.Collections.IVectorV"...
0x18007a914  call    cs:__imp_WindowsCreateStringReference
0x18007a91a  test    eax, eax
0x18007a91c  js      loc_18007AB0E
0x18007a922  mov     [rbp+30h+var_38], 0
0x18007a92a  mov     ebx, 63h ; 'c'
0x18007a92f  mov     ecx, ebx; unsigned int
0x18007a931  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18007a936  lea     edx, [rax-1]
0x18007a939  cmp     eax, ebx
0x18007a93b  cmova   edx, ebx; length
0x18007a93e  lea     r9, [rbp+30h+var_38]; string
0x18007a942  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18007a946  lea     rcx, aWindowsFoundat_152; "Windows.Foundation.Collections.IIterato"...
0x18007a94d  call    cs:__imp_WindowsCreateStringReference
0x18007a953  test    eax, eax
0x18007a955  js      loc_18007AB21
0x18007a95b  mov     rax, [rbp+30h+string]
0x18007a95f  mov     [rsp+130h+var_100], rax
0x18007a964  mov     rax, [rbp+30h+var_58]
0x18007a968  mov     [rsp+130h+var_F8], rax
0x18007a96d  mov     rax, [rbp+30h+var_38]
0x18007a971  mov     [rsp+130h+var_F0], rax
0x18007a976  movups  xmm0, xmmword ptr cs:_GUID_3a9f4b3c_f803_495c_bc57_de39766105ab.Data1
0x18007a97d  movdqu  [rsp+130h+var_E8], xmm0
0x18007a983  movups  xmm1, xmmword ptr cs:_GUID_a1bc3f40_026d_5641_9d1c_7f029e8493f6.Data1
0x18007a98a  movdqu  [rsp+130h+var_D8], xmm1
0x18007a990  movups  xmm0, xmmword ptr cs:_GUID_1a5ebfa0_c9ee_58fe_8406_6f04e6419189.Data1
0x18007a997  movdqu  [rsp+130h+var_C8], xmm0
0x18007a99d  movups  xmm1, xmmword ptr cs:_GUID_69d2049f_bd36_5ebe_b863_5bd424df2e5e.Data1
0x18007a9a4  movdqu  [rsp+130h+var_B8], xmm1
0x18007a9aa  movups  xmm0, xmmword ptr cs:_GUID_d283e6fd_b135_5290_91d6_c1b47a44b78f.Data1
0x18007a9b1  movdqu  [rbp+30h+var_A8], xmm0
0x18007a9b6  mov     [rsp+130h+var_110], 0
0x18007a9bf  lea     rcx, [rsp+130h+var_110]
0x18007a9c4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007a9c9  mov     [rbp+30h+var_18], 0
0x18007a9d1  lea     r9, [rbp+30h+var_18]; string
0x18007a9d5  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18007a9d9  lea     edx, [rbx-37h]; length
0x18007a9dc  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18007a9e3  call    cs:__imp_WindowsCreateStringReference
0x18007a9e9  test    eax, eax
0x18007a9eb  js      loc_18007AB34
0x18007a9f1  lea     r8, [rsp+130h+var_110]
0x18007a9f6  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18007a9fd  mov     rcx, [rbp+30h+var_18]
0x18007aa01  call    cs:__imp_RoGetActivationFactory
0x18007aa07  mov     ebx, eax
0x18007aa09  test    eax, eax
0x18007aa0b  js      loc_18007AAD9
0x18007aa11  mov     [rsp+130h+var_108], 0
0x18007aa1a  mov     rbx, [rsp+130h+var_110]
0x18007aa1f  lea     rcx, [rsp+130h+var_108]
0x18007aa24  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007aa29  lea     r8, [rsp+130h+var_108]
0x18007aa2e  lea     rdx, [rsp+130h+var_100]
0x18007aa33  mov     rcx, rbx
0x18007aa36  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18007aa3b  mov     ebx, eax
0x18007aa3d  test    eax, eax
0x18007aa3f  js      short loc_18007AA95
0x18007aa41  mov     rax, [rsp+130h+var_108]
0x18007aa46  mov     [rsp+130h+var_108], 0
0x18007aa4f  mov     [rdi], rax
0x18007aa52  mov     rcx, [rsp+130h+var_110]
0x18007aa57  test    rcx, rcx
0x18007aa5a  jz      short loc_18007AA72
0x18007aa5c  mov     [rsp+130h+var_110], 0
0x18007aa65  mov     rax, [rcx]
0x18007aa68  mov     rax, [rax+10h]
0x18007aa6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aa71  nop
0x18007aa72  xor     eax, eax
0x18007aa74  mov     rcx, [rbp+30h+var_10]
0x18007aa78  xor     rcx, rsp; StackCookie
0x18007aa7b  call    __security_check_cookie
0x18007aa80  lea     r11, [rsp+130h+var_s0]
0x18007aa88  mov     rbx, [r11+10h]
0x18007aa8c  mov     rdi, [r11+20h]
0x18007aa90  mov     rsp, r11
0x18007aa93  pop     rbp
0x18007aa94  retn
0x18007aa95  mov     rcx, [rsp+130h+var_108]
0x18007aa9a  test    rcx, rcx
0x18007aa9d  jz      short loc_18007AAB5
0x18007aa9f  mov     [rsp+130h+var_108], 0
0x18007aaa8  mov     rdx, [rcx]
0x18007aaab  mov     rax, [rdx+10h]
0x18007aaaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aab4  nop
0x18007aab5  mov     rcx, [rsp+130h+var_110]
0x18007aaba  test    rcx, rcx
0x18007aabd  jz      short loc_18007AAD5
0x18007aabf  mov     [rsp+130h+var_110], 0
0x18007aac8  mov     rax, [rcx]
0x18007aacb  mov     rax, [rax+10h]
0x18007aacf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aad4  nop
0x18007aad5  mov     eax, ebx
0x18007aad7  jmp     short loc_18007AA74
0x18007aad9  mov     rcx, [rsp+130h+var_110]
0x18007aade  test    rcx, rcx
0x18007aae1  jz      short loc_18007AAF9
0x18007aae3  mov     [rsp+130h+var_110], 0
0x18007aaec  mov     rdx, [rcx]
0x18007aaef  mov     rax, [rdx+10h]
0x18007aaf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aaf8  nop
0x18007aaf9  jmp     short loc_18007AAD5
0x18007aafb  xor     r9d, r9d; lpArguments
0x18007aafe  xor     r8d, r8d; nNumberOfArguments
0x18007ab01  lea     edx, [r9+1]; dwExceptionFlags
0x18007ab05  mov     ecx, eax; dwExceptionCode
0x18007ab07  call    cs:__imp_RaiseException
0x18007ab0d  int     3; Trap to Debugger
0x18007ab0e  xor     r9d, r9d; lpArguments
0x18007ab11  xor     r8d, r8d; nNumberOfArguments
0x18007ab14  lea     edx, [r9+1]; dwExceptionFlags
0x18007ab18  mov     ecx, eax; dwExceptionCode
0x18007ab1a  call    cs:__imp_RaiseException
0x18007ab20  int     3; Trap to Debugger
0x18007ab21  xor     r9d, r9d; lpArguments
0x18007ab24  xor     r8d, r8d; nNumberOfArguments
0x18007ab27  lea     edx, [r9+1]; dwExceptionFlags
0x18007ab2b  mov     ecx, eax; dwExceptionCode
0x18007ab2d  call    cs:__imp_RaiseException
0x18007ab33  int     3; Trap to Debugger
0x18007ab34  xor     r9d, r9d; lpArguments
0x18007ab37  xor     r8d, r8d; nNumberOfArguments
0x18007ab3a  lea     edx, [r9+1]; dwExceptionFlags
0x18007ab3e  mov     ecx, eax; dwExceptionCode
0x18007ab40  call    cs:__imp_RaiseException
```
