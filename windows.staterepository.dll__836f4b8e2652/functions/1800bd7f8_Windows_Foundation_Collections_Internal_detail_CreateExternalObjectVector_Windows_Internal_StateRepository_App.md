# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::AppUriHandler,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppUriHandler *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppUriHandler *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppUriHandler *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppUriHandler *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppUriHandler *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppUriHandler *>,0> * *)

- ea: `0x1800bd7f8`
- end: `0x1800bda65`
- name: `??$CreateExternalObjectVector@VAppUriHandler@StateRepository@Internal@Windows@@V?$AgileVector@PEAVAppUriHandler@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAppUriHandler@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAppUriHandler@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVAppUriHandler@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAppUriHandler@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAppUriHandler@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `621`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ef04`
- `0x1801d26b0`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x1800bd7f8`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bd860`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bd8a7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bd8ee`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bd995`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bd860`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bd8a7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bd8ee`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bd995`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800bd9ac`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800bd9ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bd84b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bd892`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bd8d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bd97f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bd84b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bd892`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bd8d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bd97f`

## string_xrefs

- `0x1800bd8d2`: `Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.AppUriHandler>`
- `0x1800bd844`: `Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.AppUriHandler>`
- `0x1800bd88b`: `Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.AppUriHandler>`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::AppUriHandler,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppUriHandler *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppUriHandler *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppUriHandler *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x58u);
  v4 = v3 - 1;
  if ( v3 > 0x58 )
    v4 = 88;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.AppUriHandler>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v29 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Cu);
  v7 = v6 - 1;
  if ( v6 > 0x5C )
    v7 = 92;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.AppUriHandler>",
         v7,
         &v28,
         &v29);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Au);
  v10 = v9 - 1;
  if ( v9 > 0x5A )
    v10 = 90;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.AppUriHandler>",
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
  v21 = GUID_922b6ac1_60fb_4758_8dd7_3b60d8a697d0;
  v22 = GUID_54dbe6a8_cdeb_5611_87e9_6ec4d4a6d7f3;
  v23 = GUID_5cd5a978_35d5_5ade_a399_ebadbbf2fe76;
  v24 = GUID_6a21b502_595f_583d_b4ad_0665914dac99;
  v25 = GUID_9ef05baf_fd4e_55e9_aee9_1df88927546d;
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
0x1800bd7f8  mov     [rsp-8+arg_0], rbx
0x1800bd7fd  mov     [rsp-8+arg_10], rdi
0x1800bd802  push    rbp
0x1800bd803  lea     rbp, [rsp-30h]
0x1800bd808  sub     rsp, 130h
0x1800bd80f  mov     rax, cs:__security_cookie
0x1800bd816  xor     rax, rsp
0x1800bd819  mov     [rbp+30h+var_10], rax
0x1800bd81d  mov     rdi, rdx
0x1800bd820  mov     [rbp+30h+string], 0
0x1800bd828  mov     ebx, 58h ; 'X'
0x1800bd82d  mov     ecx, ebx; unsigned int
0x1800bd82f  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800bd834  lea     edx, [rax-1]
0x1800bd837  cmp     eax, ebx
0x1800bd839  cmova   edx, ebx; length
0x1800bd83c  lea     r9, [rbp+30h+string]; string
0x1800bd840  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x1800bd844  lea     rcx, aWindowsFoundat_73; "Windows.Foundation.Collections.IVector`"...
0x1800bd84b  call    cs:__imp_WindowsCreateStringReference
0x1800bd851  test    eax, eax
0x1800bd853  jns     short loc_1800BD867
0x1800bd855  xor     r9d, r9d; lpArguments
0x1800bd858  xor     r8d, r8d; nNumberOfArguments
0x1800bd85b  lea     edx, [rbx-57h]; dwExceptionFlags
0x1800bd85e  mov     ecx, eax; dwExceptionCode
0x1800bd860  call    cs:__imp_RaiseException
0x1800bd866  int     3; Trap to Debugger
0x1800bd867  mov     [rbp+30h+var_58], 0
0x1800bd86f  mov     ebx, 5Ch ; '\'
0x1800bd874  mov     ecx, ebx; unsigned int
0x1800bd876  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800bd87b  lea     edx, [rax-1]
0x1800bd87e  cmp     eax, ebx
0x1800bd880  cmova   edx, ebx; length
0x1800bd883  lea     r9, [rbp+30h+var_58]; string
0x1800bd887  lea     r8, [rbp+30h+var_70]; hstringHeader
0x1800bd88b  lea     rcx, aWindowsFoundat_103; "Windows.Foundation.Collections.IVectorV"...
0x1800bd892  call    cs:__imp_WindowsCreateStringReference
0x1800bd898  test    eax, eax
0x1800bd89a  jns     short loc_1800BD8AE
0x1800bd89c  xor     r9d, r9d; lpArguments
0x1800bd89f  xor     r8d, r8d; nNumberOfArguments
0x1800bd8a2  lea     edx, [rbx-5Bh]; dwExceptionFlags
0x1800bd8a5  mov     ecx, eax; dwExceptionCode
0x1800bd8a7  call    cs:__imp_RaiseException
0x1800bd8ad  int     3; Trap to Debugger
0x1800bd8ae  mov     [rbp+30h+var_38], 0
0x1800bd8b6  mov     ebx, 5Ah ; 'Z'
0x1800bd8bb  mov     ecx, ebx; unsigned int
0x1800bd8bd  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800bd8c2  lea     edx, [rax-1]
0x1800bd8c5  cmp     eax, ebx
0x1800bd8c7  cmova   edx, ebx; length
0x1800bd8ca  lea     r9, [rbp+30h+var_38]; string
0x1800bd8ce  lea     r8, [rbp+30h+var_50]; hstringHeader
0x1800bd8d2  lea     rcx, aWindowsFoundat_199; "Windows.Foundation.Collections.IIterato"...
0x1800bd8d9  call    cs:__imp_WindowsCreateStringReference
0x1800bd8df  test    eax, eax
0x1800bd8e1  jns     short loc_1800BD8F5
0x1800bd8e3  xor     r9d, r9d; lpArguments
0x1800bd8e6  xor     r8d, r8d; nNumberOfArguments
0x1800bd8e9  lea     edx, [rbx-59h]; dwExceptionFlags
0x1800bd8ec  mov     ecx, eax; dwExceptionCode
0x1800bd8ee  call    cs:__imp_RaiseException
0x1800bd8f4  int     3; Trap to Debugger
0x1800bd8f5  mov     rax, [rbp+30h+string]
0x1800bd8f9  mov     [rsp+130h+var_100], rax
0x1800bd8fe  mov     rax, [rbp+30h+var_58]
0x1800bd902  mov     [rsp+130h+var_F8], rax
0x1800bd907  mov     rax, [rbp+30h+var_38]
0x1800bd90b  mov     [rsp+130h+var_F0], rax
0x1800bd910  movups  xmm0, xmmword ptr cs:_GUID_922b6ac1_60fb_4758_8dd7_3b60d8a697d0.Data1
0x1800bd917  movdqu  [rsp+130h+var_E8], xmm0
0x1800bd91d  movups  xmm1, xmmword ptr cs:_GUID_54dbe6a8_cdeb_5611_87e9_6ec4d4a6d7f3.Data1
0x1800bd924  movdqu  [rsp+130h+var_D8], xmm1
0x1800bd92a  movups  xmm0, xmmword ptr cs:_GUID_5cd5a978_35d5_5ade_a399_ebadbbf2fe76.Data1
0x1800bd931  movdqu  [rsp+130h+var_C8], xmm0
0x1800bd937  movups  xmm1, xmmword ptr cs:_GUID_6a21b502_595f_583d_b4ad_0665914dac99.Data1
0x1800bd93e  movdqu  [rsp+130h+var_B8], xmm1
0x1800bd944  movups  xmm0, xmmword ptr cs:_GUID_9ef05baf_fd4e_55e9_aee9_1df88927546d.Data1
0x1800bd94b  movdqu  [rbp+30h+var_A8], xmm0
0x1800bd950  mov     [rsp+130h+var_110], 0
0x1800bd959  lea     rcx, [rsp+130h+var_110]
0x1800bd95e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bd963  mov     [rbp+30h+var_18], 0
0x1800bd96b  lea     r9, [rbp+30h+var_18]; string
0x1800bd96f  lea     r8, [rbp+30h+var_30]; hstringHeader
0x1800bd973  mov     edx, 2Ch ; ','; length
0x1800bd978  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x1800bd97f  call    cs:__imp_WindowsCreateStringReference
0x1800bd985  test    eax, eax
0x1800bd987  jns     short loc_1800BD99C
0x1800bd989  xor     r9d, r9d; lpArguments
0x1800bd98c  xor     r8d, r8d; nNumberOfArguments
0x1800bd98f  lea     edx, [r9+1]; dwExceptionFlags
0x1800bd993  mov     ecx, eax; dwExceptionCode
0x1800bd995  call    cs:__imp_RaiseException
0x1800bd99b  int     3; Trap to Debugger
0x1800bd99c  lea     r8, [rsp+130h+var_110]
0x1800bd9a1  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x1800bd9a8  mov     rcx, [rbp+30h+var_18]
0x1800bd9ac  call    cs:__imp_RoGetActivationFactory
0x1800bd9b2  mov     ebx, eax
0x1800bd9b4  test    eax, eax
0x1800bd9b6  jns     short loc_1800BD9DC
0x1800bd9b8  mov     rcx, [rsp+130h+var_110]
0x1800bd9bd  test    rcx, rcx
0x1800bd9c0  jz      short loc_1800BD9D8
0x1800bd9c2  mov     [rsp+130h+var_110], 0
0x1800bd9cb  mov     rdx, [rcx]
0x1800bd9ce  mov     rax, [rdx+10h]
0x1800bd9d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd9d7  nop
0x1800bd9d8  mov     eax, ebx
0x1800bd9da  jmp     short loc_1800BDA44
0x1800bd9dc  mov     [rsp+130h+var_108], 0
0x1800bd9e5  mov     rbx, [rsp+130h+var_110]
0x1800bd9ea  lea     rcx, [rsp+130h+var_108]
0x1800bd9ef  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bd9f4  lea     r8, [rsp+130h+var_108]
0x1800bd9f9  lea     rdx, [rsp+130h+var_100]
0x1800bd9fe  mov     rcx, rbx
0x1800bda01  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x1800bda06  mov     ebx, eax
0x1800bda08  lea     rcx, [rsp+130h+var_108]
0x1800bda0d  test    eax, eax
0x1800bda0f  jns     short loc_1800BDA22
0x1800bda11  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bda16  lea     rcx, [rsp+130h+var_110]
0x1800bda1b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bda20  jmp     short loc_1800BD9D8
0x1800bda22  mov     rax, [rsp+130h+var_108]
0x1800bda27  mov     [rsp+130h+var_108], 0
0x1800bda30  mov     [rdi], rax
0x1800bda33  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bda38  lea     rcx, [rsp+130h+var_110]
0x1800bda3d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bda42  xor     eax, eax
0x1800bda44  mov     rcx, [rbp+30h+var_10]
0x1800bda48  xor     rcx, rsp; StackCookie
0x1800bda4b  call    __security_check_cookie
0x1800bda50  lea     r11, [rsp+130h+var_s0]
0x1800bda58  mov     rbx, [r11+10h]
0x1800bda5c  mov     rdi, [r11+20h]
0x1800bda60  mov     rsp, r11
0x1800bda63  pop     rbp
0x1800bda64  retn
```
