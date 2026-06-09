# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::PackageSourceUri,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PackageSourceUri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PackageSourceUri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PackageSourceUri *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PackageSourceUri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PackageSourceUri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PackageSourceUri *>,0> * *)

- ea: `0x1800b44c8`
- end: `0x1800b4735`
- name: `??$CreateExternalObjectVector@VPackageSourceUri@StateRepository@Internal@Windows@@V?$AgileVector@PEAVPackageSourceUri@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVPackageSourceUri@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPackageSourceUri@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVPackageSourceUri@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVPackageSourceUri@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPackageSourceUri@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `621`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002b254`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x1800b44c8`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b4530`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b4577`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b45be`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b4665`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b4530`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b4577`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b45be`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b4665`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b467c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b467c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b451b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b4562`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b45a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b464f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b451b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b4562`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b45a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b464f`

## string_xrefs

- `0x1800b45a2`: `Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.PackageSourceUri>`
- `0x1800b4514`: `Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.PackageSourceUri>`
- `0x1800b455b`: `Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.PackageSourceUri>`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::PackageSourceUri,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PackageSourceUri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PackageSourceUri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PackageSourceUri *>,0>>(
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
  __int64 v14; // rcx
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v19; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v20[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v21; // [rsp+48h] [rbp-B8h]
  GUID v22; // [rsp+58h] [rbp-A8h]
  GUID v23; // [rsp+68h] [rbp-98h]
  GUID v24; // [rsp+78h] [rbp-88h]
  GUID v25; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v28; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v29; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v30; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v31; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v32; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v33; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Bu);
  v4 = v3 - 1;
  if ( v3 > 0x5B )
    v4 = 91;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.PackageSourceUri>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v29 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Fu);
  v7 = v6 - 1;
  if ( v6 > 0x5F )
    v7 = 95;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.PackageSourceUri>",
         v7,
         &v28,
         &v29);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Du);
  v10 = v9 - 1;
  if ( v9 > 0x5D )
    v10 = 93;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.PackageSourceUri>",
          v10,
          &v30,
          &v31);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v20[0] = string;
  v20[1] = v29;
  v20[2] = v31;
  v21 = GUID_b3b62566_ec3c_4f37_93ed_1089e768cc3a;
  v22 = GUID_51a20b6d_9a37_5d41_8877_0d631202f2a9;
  v23 = GUID_52516ebe_44fc_5126_8972_50bc8f018da3;
  v24 = GUID_eca5938b_fc43_5152_87a1_05480b044d8c;
  v25 = GUID_97238417_ae5b_5c24_90df_205063743b3c;
  v18 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
  v33 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v32, &v33);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v33, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v18);
  if ( ActivationFactory < 0 )
  {
    v14 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return (unsigned int)ActivationFactory;
  }
  v19 = 0;
  v16 = v18;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v16, v20, &v19);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
    return (unsigned int)ActivationFactory;
  }
  v17 = v19;
  v19 = 0;
  *a2 = v17;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
  return 0;
}

```

## disassembly

```asm
0x1800b44c8  mov     [rsp-8+arg_0], rbx
0x1800b44cd  mov     [rsp-8+arg_10], rdi
0x1800b44d2  push    rbp
0x1800b44d3  lea     rbp, [rsp-30h]
0x1800b44d8  sub     rsp, 130h
0x1800b44df  mov     rax, cs:__security_cookie
0x1800b44e6  xor     rax, rsp
0x1800b44e9  mov     [rbp+30h+var_10], rax
0x1800b44ed  mov     rdi, rdx
0x1800b44f0  mov     [rbp+30h+string], 0
0x1800b44f8  mov     ebx, 5Bh ; '['
0x1800b44fd  mov     ecx, ebx; unsigned int
0x1800b44ff  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800b4504  lea     edx, [rax-1]
0x1800b4507  cmp     eax, ebx
0x1800b4509  cmova   edx, ebx; length
0x1800b450c  lea     r9, [rbp+30h+string]; string
0x1800b4510  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x1800b4514  lea     rcx, aWindowsFoundat_90; "Windows.Foundation.Collections.IVector`"...
0x1800b451b  call    cs:__imp_WindowsCreateStringReference
0x1800b4521  test    eax, eax
0x1800b4523  jns     short loc_1800B4537
0x1800b4525  xor     r9d, r9d; lpArguments
0x1800b4528  xor     r8d, r8d; nNumberOfArguments
0x1800b452b  lea     edx, [rbx-5Ah]; dwExceptionFlags
0x1800b452e  mov     ecx, eax; dwExceptionCode
0x1800b4530  call    cs:__imp_RaiseException
0x1800b4536  int     3; Trap to Debugger
0x1800b4537  mov     [rbp+30h+var_58], 0
0x1800b453f  mov     ebx, 5Fh ; '_'
0x1800b4544  mov     ecx, ebx; unsigned int
0x1800b4546  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800b454b  lea     edx, [rax-1]
0x1800b454e  cmp     eax, ebx
0x1800b4550  cmova   edx, ebx; length
0x1800b4553  lea     r9, [rbp+30h+var_58]; string
0x1800b4557  lea     r8, [rbp+30h+var_70]; hstringHeader
0x1800b455b  lea     rcx, aWindowsFoundat_119; "Windows.Foundation.Collections.IVectorV"...
0x1800b4562  call    cs:__imp_WindowsCreateStringReference
0x1800b4568  test    eax, eax
0x1800b456a  jns     short loc_1800B457E
0x1800b456c  xor     r9d, r9d; lpArguments
0x1800b456f  xor     r8d, r8d; nNumberOfArguments
0x1800b4572  lea     edx, [rbx-5Eh]; dwExceptionFlags
0x1800b4575  mov     ecx, eax; dwExceptionCode
0x1800b4577  call    cs:__imp_RaiseException
0x1800b457d  int     3; Trap to Debugger
0x1800b457e  mov     [rbp+30h+var_38], 0
0x1800b4586  mov     ebx, 5Dh ; ']'
0x1800b458b  mov     ecx, ebx; unsigned int
0x1800b458d  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800b4592  lea     edx, [rax-1]
0x1800b4595  cmp     eax, ebx
0x1800b4597  cmova   edx, ebx; length
0x1800b459a  lea     r9, [rbp+30h+var_38]; string
0x1800b459e  lea     r8, [rbp+30h+var_50]; hstringHeader
0x1800b45a2  lea     rcx, aWindowsFoundat_79; "Windows.Foundation.Collections.IIterato"...
0x1800b45a9  call    cs:__imp_WindowsCreateStringReference
0x1800b45af  test    eax, eax
0x1800b45b1  jns     short loc_1800B45C5
0x1800b45b3  xor     r9d, r9d; lpArguments
0x1800b45b6  xor     r8d, r8d; nNumberOfArguments
0x1800b45b9  lea     edx, [rbx-5Ch]; dwExceptionFlags
0x1800b45bc  mov     ecx, eax; dwExceptionCode
0x1800b45be  call    cs:__imp_RaiseException
0x1800b45c4  int     3; Trap to Debugger
0x1800b45c5  mov     rax, [rbp+30h+string]
0x1800b45c9  mov     [rsp+130h+var_100], rax
0x1800b45ce  mov     rax, [rbp+30h+var_58]
0x1800b45d2  mov     [rsp+130h+var_F8], rax
0x1800b45d7  mov     rax, [rbp+30h+var_38]
0x1800b45db  mov     [rsp+130h+var_F0], rax
0x1800b45e0  movups  xmm0, xmmword ptr cs:_GUID_b3b62566_ec3c_4f37_93ed_1089e768cc3a.Data1
0x1800b45e7  movdqu  [rsp+130h+var_E8], xmm0
0x1800b45ed  movups  xmm1, xmmword ptr cs:_GUID_51a20b6d_9a37_5d41_8877_0d631202f2a9.Data1
0x1800b45f4  movdqu  [rsp+130h+var_D8], xmm1
0x1800b45fa  movups  xmm0, xmmword ptr cs:_GUID_52516ebe_44fc_5126_8972_50bc8f018da3.Data1
0x1800b4601  movdqu  [rsp+130h+var_C8], xmm0
0x1800b4607  movups  xmm1, xmmword ptr cs:_GUID_eca5938b_fc43_5152_87a1_05480b044d8c.Data1
0x1800b460e  movdqu  [rsp+130h+var_B8], xmm1
0x1800b4614  movups  xmm0, xmmword ptr cs:_GUID_97238417_ae5b_5c24_90df_205063743b3c.Data1
0x1800b461b  movdqu  [rbp+30h+var_A8], xmm0
0x1800b4620  mov     [rsp+130h+var_110], 0
0x1800b4629  lea     rcx, [rsp+130h+var_110]
0x1800b462e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4633  mov     [rbp+30h+var_18], 0
0x1800b463b  lea     r9, [rbp+30h+var_18]; string
0x1800b463f  lea     r8, [rbp+30h+var_30]; hstringHeader
0x1800b4643  mov     edx, 2Ch ; ','; length
0x1800b4648  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x1800b464f  call    cs:__imp_WindowsCreateStringReference
0x1800b4655  test    eax, eax
0x1800b4657  jns     short loc_1800B466C
0x1800b4659  xor     r9d, r9d; lpArguments
0x1800b465c  xor     r8d, r8d; nNumberOfArguments
0x1800b465f  lea     edx, [r9+1]; dwExceptionFlags
0x1800b4663  mov     ecx, eax; dwExceptionCode
0x1800b4665  call    cs:__imp_RaiseException
0x1800b466b  int     3; Trap to Debugger
0x1800b466c  lea     r8, [rsp+130h+var_110]
0x1800b4671  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x1800b4678  mov     rcx, [rbp+30h+var_18]
0x1800b467c  call    cs:__imp_RoGetActivationFactory
0x1800b4682  mov     ebx, eax
0x1800b4684  test    eax, eax
0x1800b4686  jns     short loc_1800B46AC
0x1800b4688  mov     rcx, [rsp+130h+var_110]
0x1800b468d  test    rcx, rcx
0x1800b4690  jz      short loc_1800B46A8
0x1800b4692  mov     [rsp+130h+var_110], 0
0x1800b469b  mov     rdx, [rcx]
0x1800b469e  mov     rax, [rdx+10h]
0x1800b46a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b46a7  nop
0x1800b46a8  mov     eax, ebx
0x1800b46aa  jmp     short loc_1800B4714
0x1800b46ac  mov     [rsp+130h+var_108], 0
0x1800b46b5  mov     rbx, [rsp+130h+var_110]
0x1800b46ba  lea     rcx, [rsp+130h+var_108]
0x1800b46bf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b46c4  lea     r8, [rsp+130h+var_108]
0x1800b46c9  lea     rdx, [rsp+130h+var_100]
0x1800b46ce  mov     rcx, rbx
0x1800b46d1  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x1800b46d6  mov     ebx, eax
0x1800b46d8  lea     rcx, [rsp+130h+var_108]
0x1800b46dd  test    eax, eax
0x1800b46df  jns     short loc_1800B46F2
0x1800b46e1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b46e6  lea     rcx, [rsp+130h+var_110]
0x1800b46eb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b46f0  jmp     short loc_1800B46A8
0x1800b46f2  mov     rax, [rsp+130h+var_108]
0x1800b46f7  mov     [rsp+130h+var_108], 0
0x1800b4700  mov     [rdi], rax
0x1800b4703  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4708  lea     rcx, [rsp+130h+var_110]
0x1800b470d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4712  xor     eax, eax
0x1800b4714  mov     rcx, [rbp+30h+var_10]
0x1800b4718  xor     rcx, rsp; StackCookie
0x1800b471b  call    __security_check_cookie
0x1800b4720  lea     r11, [rsp+130h+var_s0]
0x1800b4728  mov     rbx, [r11+10h]
0x1800b472c  mov     rdi, [r11+20h]
0x1800b4730  mov     rsp, r11
0x1800b4733  pop     rbp
0x1800b4734  retn
```
