# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::AppInstallerUri,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppInstallerUri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppInstallerUri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppInstallerUri *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppInstallerUri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppInstallerUri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppInstallerUri *>,0> * *)

- ea: `0x1800b1a64`
- end: `0x1800b1cd1`
- name: `??$CreateExternalObjectVector@VAppInstallerUri@StateRepository@Internal@Windows@@V?$AgileVector@PEAVAppInstallerUri@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAppInstallerUri@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAppInstallerUri@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVAppInstallerUri@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAppInstallerUri@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAppInstallerUri@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `621`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800b1984`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x1800b1a64`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b1acc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b1b13`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b1b5a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b1c01`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b1acc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b1b13`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b1b5a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b1c01`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b1c18`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b1c18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b1ab7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b1afe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b1b45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b1beb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b1ab7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b1afe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b1b45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b1beb`

## string_xrefs

- `0x1800b1af7`: `Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.AppInstallerUri>`
- `0x1800b1b3e`: `Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.AppInstallerUri>`
- `0x1800b1ab0`: `Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.AppInstallerUri>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::AppInstallerUri,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppInstallerUri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppInstallerUri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppInstallerUri *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Au);
  v4 = v3 - 1;
  if ( v3 > 0x5A )
    v4 = 90;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.AppInstallerUri>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v29 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Eu);
  v7 = v6 - 1;
  if ( v6 > 0x5E )
    v7 = 94;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.AppInstallerUri>",
         v7,
         &v28,
         &v29);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Cu);
  v10 = v9 - 1;
  if ( v9 > 0x5C )
    v10 = 92;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.AppInstallerUri>",
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
  v21 = GUID_ce7817be_b28d_4049_bbff_0d627e1a198e;
  v22 = GUID_18cbbbcf_b799_5a33_a996_6c759d0a9dec;
  v23 = GUID_252de3a0_dd85_540f_af6a_3c1558fed1c2;
  v24 = GUID_7474695d_24e4_5209_9356_d2b7b1e51716;
  v25 = GUID_d9be6a6f_0033_57cb_b75f_8f630ec4813a;
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
0x1800b1a64  mov     [rsp-8+arg_0], rbx
0x1800b1a69  mov     [rsp-8+arg_10], rdi
0x1800b1a6e  push    rbp
0x1800b1a6f  lea     rbp, [rsp-30h]
0x1800b1a74  sub     rsp, 130h
0x1800b1a7b  mov     rax, cs:__security_cookie
0x1800b1a82  xor     rax, rsp
0x1800b1a85  mov     [rbp+30h+var_10], rax
0x1800b1a89  mov     rdi, rdx
0x1800b1a8c  mov     [rbp+30h+string], 0
0x1800b1a94  mov     ebx, 5Ah ; 'Z'
0x1800b1a99  mov     ecx, ebx; unsigned int
0x1800b1a9b  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800b1aa0  lea     edx, [rax-1]
0x1800b1aa3  cmp     eax, ebx
0x1800b1aa5  cmova   edx, ebx; length
0x1800b1aa8  lea     r9, [rbp+30h+string]; string
0x1800b1aac  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x1800b1ab0  lea     rcx, aWindowsFoundat_189; "Windows.Foundation.Collections.IVector`"...
0x1800b1ab7  call    cs:__imp_WindowsCreateStringReference
0x1800b1abd  test    eax, eax
0x1800b1abf  jns     short loc_1800B1AD3
0x1800b1ac1  xor     r9d, r9d; lpArguments
0x1800b1ac4  xor     r8d, r8d; nNumberOfArguments
0x1800b1ac7  lea     edx, [rbx-59h]; dwExceptionFlags
0x1800b1aca  mov     ecx, eax; dwExceptionCode
0x1800b1acc  call    cs:__imp_RaiseException
0x1800b1ad2  int     3; Trap to Debugger
0x1800b1ad3  mov     [rbp+30h+var_58], 0
0x1800b1adb  mov     ebx, 5Eh ; '^'
0x1800b1ae0  mov     ecx, ebx; unsigned int
0x1800b1ae2  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800b1ae7  lea     edx, [rax-1]
0x1800b1aea  cmp     eax, ebx
0x1800b1aec  cmova   edx, ebx; length
0x1800b1aef  lea     r9, [rbp+30h+var_58]; string
0x1800b1af3  lea     r8, [rbp+30h+var_70]; hstringHeader
0x1800b1af7  lea     rcx, aWindowsFoundat_170; "Windows.Foundation.Collections.IVectorV"...
0x1800b1afe  call    cs:__imp_WindowsCreateStringReference
0x1800b1b04  test    eax, eax
0x1800b1b06  jns     short loc_1800B1B1A
0x1800b1b08  xor     r9d, r9d; lpArguments
0x1800b1b0b  xor     r8d, r8d; nNumberOfArguments
0x1800b1b0e  lea     edx, [rbx-5Dh]; dwExceptionFlags
0x1800b1b11  mov     ecx, eax; dwExceptionCode
0x1800b1b13  call    cs:__imp_RaiseException
0x1800b1b19  int     3; Trap to Debugger
0x1800b1b1a  mov     [rbp+30h+var_38], 0
0x1800b1b22  mov     ebx, 5Ch ; '\'
0x1800b1b27  mov     ecx, ebx; unsigned int
0x1800b1b29  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800b1b2e  lea     edx, [rax-1]
0x1800b1b31  cmp     eax, ebx
0x1800b1b33  cmova   edx, ebx; length
0x1800b1b36  lea     r9, [rbp+30h+var_38]; string
0x1800b1b3a  lea     r8, [rbp+30h+var_50]; hstringHeader
0x1800b1b3e  lea     rcx, aWindowsFoundat_86; "Windows.Foundation.Collections.IIterato"...
0x1800b1b45  call    cs:__imp_WindowsCreateStringReference
0x1800b1b4b  test    eax, eax
0x1800b1b4d  jns     short loc_1800B1B61
0x1800b1b4f  xor     r9d, r9d; lpArguments
0x1800b1b52  xor     r8d, r8d; nNumberOfArguments
0x1800b1b55  lea     edx, [rbx-5Bh]; dwExceptionFlags
0x1800b1b58  mov     ecx, eax; dwExceptionCode
0x1800b1b5a  call    cs:__imp_RaiseException
0x1800b1b60  int     3; Trap to Debugger
0x1800b1b61  mov     rax, [rbp+30h+string]
0x1800b1b65  mov     [rsp+130h+var_100], rax
0x1800b1b6a  mov     rax, [rbp+30h+var_58]
0x1800b1b6e  mov     [rsp+130h+var_F8], rax
0x1800b1b73  mov     rax, [rbp+30h+var_38]
0x1800b1b77  mov     [rsp+130h+var_F0], rax
0x1800b1b7c  movups  xmm0, xmmword ptr cs:_GUID_ce7817be_b28d_4049_bbff_0d627e1a198e.Data1
0x1800b1b83  movdqu  [rsp+130h+var_E8], xmm0
0x1800b1b89  movups  xmm1, xmmword ptr cs:_GUID_18cbbbcf_b799_5a33_a996_6c759d0a9dec.Data1
0x1800b1b90  movdqu  [rsp+130h+var_D8], xmm1
0x1800b1b96  movups  xmm0, xmmword ptr cs:_GUID_252de3a0_dd85_540f_af6a_3c1558fed1c2.Data1
0x1800b1b9d  movdqu  [rsp+130h+var_C8], xmm0
0x1800b1ba3  movups  xmm1, xmmword ptr cs:_GUID_7474695d_24e4_5209_9356_d2b7b1e51716.Data1
0x1800b1baa  movdqu  [rsp+130h+var_B8], xmm1
0x1800b1bb0  movups  xmm0, xmmword ptr cs:_GUID_d9be6a6f_0033_57cb_b75f_8f630ec4813a.Data1
0x1800b1bb7  movdqu  [rbp+30h+var_A8], xmm0
0x1800b1bbc  mov     [rsp+130h+var_110], 0
0x1800b1bc5  lea     rcx, [rsp+130h+var_110]
0x1800b1bca  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b1bcf  mov     [rbp+30h+var_18], 0
0x1800b1bd7  lea     r9, [rbp+30h+var_18]; string
0x1800b1bdb  lea     r8, [rbp+30h+var_30]; hstringHeader
0x1800b1bdf  mov     edx, 2Ch ; ','; length
0x1800b1be4  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x1800b1beb  call    cs:__imp_WindowsCreateStringReference
0x1800b1bf1  test    eax, eax
0x1800b1bf3  jns     short loc_1800B1C08
0x1800b1bf5  xor     r9d, r9d; lpArguments
0x1800b1bf8  xor     r8d, r8d; nNumberOfArguments
0x1800b1bfb  lea     edx, [r9+1]; dwExceptionFlags
0x1800b1bff  mov     ecx, eax; dwExceptionCode
0x1800b1c01  call    cs:__imp_RaiseException
0x1800b1c07  int     3; Trap to Debugger
0x1800b1c08  lea     r8, [rsp+130h+var_110]
0x1800b1c0d  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x1800b1c14  mov     rcx, [rbp+30h+var_18]
0x1800b1c18  call    cs:__imp_RoGetActivationFactory
0x1800b1c1e  mov     ebx, eax
0x1800b1c20  test    eax, eax
0x1800b1c22  jns     short loc_1800B1C48
0x1800b1c24  mov     rcx, [rsp+130h+var_110]
0x1800b1c29  test    rcx, rcx
0x1800b1c2c  jz      short loc_1800B1C44
0x1800b1c2e  mov     [rsp+130h+var_110], 0
0x1800b1c37  mov     rdx, [rcx]
0x1800b1c3a  mov     rax, [rdx+10h]
0x1800b1c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1c43  nop
0x1800b1c44  mov     eax, ebx
0x1800b1c46  jmp     short loc_1800B1CB0
0x1800b1c48  mov     [rsp+130h+var_108], 0
0x1800b1c51  mov     rbx, [rsp+130h+var_110]
0x1800b1c56  lea     rcx, [rsp+130h+var_108]
0x1800b1c5b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b1c60  lea     r8, [rsp+130h+var_108]
0x1800b1c65  lea     rdx, [rsp+130h+var_100]
0x1800b1c6a  mov     rcx, rbx
0x1800b1c6d  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x1800b1c72  mov     ebx, eax
0x1800b1c74  lea     rcx, [rsp+130h+var_108]
0x1800b1c79  test    eax, eax
0x1800b1c7b  jns     short loc_1800B1C8E
0x1800b1c7d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b1c82  lea     rcx, [rsp+130h+var_110]
0x1800b1c87  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b1c8c  jmp     short loc_1800B1C44
0x1800b1c8e  mov     rax, [rsp+130h+var_108]
0x1800b1c93  mov     [rsp+130h+var_108], 0
0x1800b1c9c  mov     [rdi], rax
0x1800b1c9f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b1ca4  lea     rcx, [rsp+130h+var_110]
0x1800b1ca9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b1cae  xor     eax, eax
0x1800b1cb0  mov     rcx, [rbp+30h+var_10]
0x1800b1cb4  xor     rcx, rsp; StackCookie
0x1800b1cb7  call    __security_check_cookie
0x1800b1cbc  lea     r11, [rsp+130h+var_s0]
0x1800b1cc4  mov     rbx, [r11+10h]
0x1800b1cc8  mov     rdi, [r11+20h]
0x1800b1ccc  mov     rsp, r11
0x1800b1ccf  pop     rbp
0x1800b1cd0  retn
```
