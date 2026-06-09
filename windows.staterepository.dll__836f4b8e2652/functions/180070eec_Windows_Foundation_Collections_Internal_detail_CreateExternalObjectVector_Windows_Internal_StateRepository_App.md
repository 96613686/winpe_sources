# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::AppInstaller,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppInstaller *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppInstaller *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppInstaller *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppInstaller *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppInstaller *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppInstaller *>,0> * *)

- ea: `0x180070eec`
- end: `0x180071185`
- name: `??$CreateExternalObjectVector@VAppInstaller@StateRepository@Internal@Windows@@V?$AgileVector@PEAVAppInstaller@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAppInstaller@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAppInstaller@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVAppInstaller@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAppInstaller@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAppInstaller@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `665`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180070da4`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x180070eec`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007112c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007113f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180071152`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180071165`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007112c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007113f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180071152`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180071165`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180071065`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180071065`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180070f3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180070f78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180070fb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180071047`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180070f3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180070f78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180070fb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180071047`

## string_xrefs

- `0x180070f38`: `Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.AppInstaller>`
- `0x180070f71`: `Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.AppInstaller>`
- `0x180070faa`: `Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.AppInstaller>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::AppInstaller,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppInstaller *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppInstaller *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppInstaller *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x57u);
  v4 = v3 - 1;
  if ( v3 > 0x57 )
    v4 = 87;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.AppInstaller>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v30 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Bu);
  v7 = v6 - 1;
  if ( v6 > 0x5B )
    v7 = 91;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.AppInstaller>",
         v7,
         &v29,
         &v30);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x59u);
  v10 = v9 - 1;
  if ( v9 > 0x59 )
    v10 = 89;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.AppInstaller>",
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
  v22 = GUID_3737b7cb_0720_452d_adea_fe4818651a27;
  v23 = GUID_6701024d_2a52_5e84_a666_a2b8c7b2e704;
  v24 = GUID_68af2a4f_e5da_5f20_bb4b_568e5a9b0931;
  v25 = GUID_3dad9b9d_2e64_55ee_af44_640cf2536704;
  v26 = GUID_36a5e33b_4138_511f_b3bc_1be3ef1ea024;
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
    v14 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return (unsigned int)ActivationFactory;
  }
  v20 = 0;
  v16 = v19;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v16, v21, &v20);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
    return (unsigned int)ActivationFactory;
  }
  v17 = v20;
  v20 = 0;
  *a2 = v17;
  v18 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return 0;
}

```

## disassembly

```asm
0x180070eec  mov     [rsp-8+arg_0], rbx
0x180070ef1  mov     [rsp-8+arg_10], rdi
0x180070ef6  push    rbp
0x180070ef7  lea     rbp, [rsp-30h]
0x180070efc  sub     rsp, 130h
0x180070f03  mov     rax, cs:__security_cookie
0x180070f0a  xor     rax, rsp
0x180070f0d  mov     [rbp+30h+var_10], rax
0x180070f11  mov     rdi, rdx
0x180070f14  mov     [rbp+30h+string], 0
0x180070f1c  mov     ebx, 57h ; 'W'
0x180070f21  mov     ecx, ebx; unsigned int
0x180070f23  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180070f28  lea     edx, [rax-1]
0x180070f2b  cmp     eax, ebx
0x180070f2d  cmova   edx, ebx; length
0x180070f30  lea     r9, [rbp+30h+string]; string
0x180070f34  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180070f38  lea     rcx, aWindowsFoundat_105; "Windows.Foundation.Collections.IVector`"...
0x180070f3f  call    cs:__imp_WindowsCreateStringReference
0x180070f45  test    eax, eax
0x180070f47  js      loc_180071120
0x180070f4d  mov     [rbp+30h+var_58], 0
0x180070f55  mov     ebx, 5Bh ; '['
0x180070f5a  mov     ecx, ebx; unsigned int
0x180070f5c  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180070f61  lea     edx, [rax-1]
0x180070f64  cmp     eax, ebx
0x180070f66  cmova   edx, ebx; length
0x180070f69  lea     r9, [rbp+30h+var_58]; string
0x180070f6d  lea     r8, [rbp+30h+var_70]; hstringHeader
0x180070f71  lea     rcx, aWindowsFoundat_47; "Windows.Foundation.Collections.IVectorV"...
0x180070f78  call    cs:__imp_WindowsCreateStringReference
0x180070f7e  test    eax, eax
0x180070f80  js      loc_180071133
0x180070f86  mov     [rbp+30h+var_38], 0
0x180070f8e  mov     ebx, 59h ; 'Y'
0x180070f93  mov     ecx, ebx; unsigned int
0x180070f95  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180070f9a  lea     edx, [rax-1]
0x180070f9d  cmp     eax, ebx
0x180070f9f  cmova   edx, ebx; length
0x180070fa2  lea     r9, [rbp+30h+var_38]; string
0x180070fa6  lea     r8, [rbp+30h+var_50]; hstringHeader
0x180070faa  lea     rcx, aWindowsFoundat_172; "Windows.Foundation.Collections.IIterato"...
0x180070fb1  call    cs:__imp_WindowsCreateStringReference
0x180070fb7  test    eax, eax
0x180070fb9  js      loc_180071146
0x180070fbf  mov     rax, [rbp+30h+string]
0x180070fc3  mov     [rsp+130h+var_100], rax
0x180070fc8  mov     rax, [rbp+30h+var_58]
0x180070fcc  mov     [rsp+130h+var_F8], rax
0x180070fd1  mov     rax, [rbp+30h+var_38]
0x180070fd5  mov     [rsp+130h+var_F0], rax
0x180070fda  movups  xmm0, xmmword ptr cs:_GUID_3737b7cb_0720_452d_adea_fe4818651a27.Data1
0x180070fe1  movdqu  [rsp+130h+var_E8], xmm0
0x180070fe7  movups  xmm1, xmmword ptr cs:_GUID_6701024d_2a52_5e84_a666_a2b8c7b2e704.Data1
0x180070fee  movdqu  [rsp+130h+var_D8], xmm1
0x180070ff4  movups  xmm0, xmmword ptr cs:_GUID_68af2a4f_e5da_5f20_bb4b_568e5a9b0931.Data1
0x180070ffb  movdqu  [rsp+130h+var_C8], xmm0
0x180071001  movups  xmm1, xmmword ptr cs:_GUID_3dad9b9d_2e64_55ee_af44_640cf2536704.Data1
0x180071008  movdqu  [rsp+130h+var_B8], xmm1
0x18007100e  movups  xmm0, xmmword ptr cs:_GUID_36a5e33b_4138_511f_b3bc_1be3ef1ea024.Data1
0x180071015  movdqu  [rbp+30h+var_A8], xmm0
0x18007101a  mov     [rsp+130h+var_110], 0
0x180071023  lea     rcx, [rsp+130h+var_110]
0x180071028  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007102d  mov     [rbp+30h+var_18], 0
0x180071035  lea     r9, [rbp+30h+var_18]; string
0x180071039  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18007103d  lea     edx, [rbx-2Dh]; length
0x180071040  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180071047  call    cs:__imp_WindowsCreateStringReference
0x18007104d  test    eax, eax
0x18007104f  js      loc_180071159
0x180071055  lea     r8, [rsp+130h+var_110]
0x18007105a  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180071061  mov     rcx, [rbp+30h+var_18]
0x180071065  call    cs:__imp_RoGetActivationFactory
0x18007106b  mov     ebx, eax
0x18007106d  test    eax, eax
0x18007106f  jns     short loc_1800710B4
0x180071071  mov     rcx, [rsp+130h+var_110]
0x180071076  test    rcx, rcx
0x180071079  jz      short loc_180071091
0x18007107b  mov     [rsp+130h+var_110], 0
0x180071084  mov     rdx, [rcx]
0x180071087  mov     rax, [rdx+10h]
0x18007108b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071090  nop
0x180071091  mov     eax, ebx
0x180071093  mov     rcx, [rbp+30h+var_10]
0x180071097  xor     rcx, rsp; StackCookie
0x18007109a  call    __security_check_cookie
0x18007109f  lea     r11, [rsp+130h+var_s0]
0x1800710a7  mov     rbx, [r11+10h]
0x1800710ab  mov     rdi, [r11+20h]
0x1800710af  mov     rsp, r11
0x1800710b2  pop     rbp
0x1800710b3  retn
0x1800710b4  mov     [rsp+130h+var_108], 0
0x1800710bd  mov     rbx, [rsp+130h+var_110]
0x1800710c2  lea     rcx, [rsp+130h+var_108]
0x1800710c7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800710cc  lea     r8, [rsp+130h+var_108]
0x1800710d1  lea     rdx, [rsp+130h+var_100]
0x1800710d6  mov     rcx, rbx
0x1800710d9  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x1800710de  mov     ebx, eax
0x1800710e0  test    eax, eax
0x1800710e2  js      loc_18007116C
0x1800710e8  mov     rax, [rsp+130h+var_108]
0x1800710ed  mov     [rsp+130h+var_108], 0
0x1800710f6  mov     [rdi], rax
0x1800710f9  mov     rcx, [rsp+130h+var_110]
0x1800710fe  test    rcx, rcx
0x180071101  jz      short loc_180071119
0x180071103  mov     [rsp+130h+var_110], 0
0x18007110c  mov     rax, [rcx]
0x18007110f  mov     rax, [rax+10h]
0x180071113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071118  nop
0x180071119  xor     eax, eax
0x18007111b  jmp     loc_180071093
0x180071120  xor     r9d, r9d; lpArguments
0x180071123  xor     r8d, r8d; nNumberOfArguments
0x180071126  lea     edx, [r9+1]; dwExceptionFlags
0x18007112a  mov     ecx, eax; dwExceptionCode
0x18007112c  call    cs:__imp_RaiseException
0x180071132  int     3; Trap to Debugger
0x180071133  xor     r9d, r9d; lpArguments
0x180071136  xor     r8d, r8d; nNumberOfArguments
0x180071139  lea     edx, [r9+1]; dwExceptionFlags
0x18007113d  mov     ecx, eax; dwExceptionCode
0x18007113f  call    cs:__imp_RaiseException
0x180071145  int     3; Trap to Debugger
0x180071146  xor     r9d, r9d; lpArguments
0x180071149  xor     r8d, r8d; nNumberOfArguments
0x18007114c  lea     edx, [r9+1]; dwExceptionFlags
0x180071150  mov     ecx, eax; dwExceptionCode
0x180071152  call    cs:__imp_RaiseException
0x180071158  int     3; Trap to Debugger
0x180071159  xor     r9d, r9d; lpArguments
0x18007115c  xor     r8d, r8d; nNumberOfArguments
0x18007115f  lea     edx, [r9+1]; dwExceptionFlags
0x180071163  mov     ecx, eax; dwExceptionCode
0x180071165  call    cs:__imp_RaiseException
0x18007116b  int     3; Trap to Debugger
0x18007116c  lea     rcx, [rsp+130h+var_108]
0x180071171  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180071176  lea     rcx, [rsp+130h+var_110]
0x18007117b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180071180  jmp     loc_180071091
```
