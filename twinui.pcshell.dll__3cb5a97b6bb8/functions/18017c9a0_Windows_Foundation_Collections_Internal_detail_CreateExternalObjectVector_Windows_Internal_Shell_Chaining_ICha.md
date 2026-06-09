# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::Shell::Chaining::IChainLink,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Shell::Chaining::IChainLink *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Shell::Chaining::IChainLink *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Shell::Chaining::IChainLink *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Shell::Chaining::IChainLink *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Shell::Chaining::IChainLink *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Shell::Chaining::IChainLink *>,0> * *)

- ea: `0x18017c9a0`
- end: `0x18017cc2b`
- name: `??$CreateExternalObjectVector@UIChainLink@Chaining@Shell@Internal@Windows@@V?$AgileVector@PEAUIChainLink@Chaining@Shell@Internal@Windows@@U?$DefaultEqualityPredicate@PEAUIChainLink@Chaining@Shell@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAUIChainLink@Chaining@Shell@Internal@Windows@@@4785@$0A@@4Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAUIChainLink@Chaining@Shell@Internal@Windows@@U?$DefaultEqualityPredicate@PEAUIChainLink@Chaining@Shell@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAUIChainLink@Chaining@Shell@Internal@Windows@@@4785@$0A@@1234@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18017c864`

## callees

- `0x1800134f8`
- `0x18005d940`
- `0x18017c9a0`
- `0x1802c2bf0`
- `0x180356360`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18017ca08`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18017ca4f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18017ca96`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18017cb3d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18017ca08`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18017ca4f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18017ca96`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18017cb3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18017c9f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18017ca3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18017ca81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18017cb27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18017c9f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18017ca3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18017ca81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18017cb27`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18017cb54`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18017cb54`

## string_xrefs

- `0x18017c9ec`: `Windows.Foundation.Collections.IVector`1<Windows.Internal.Shell.Chaining.IChainLink>`
- `0x18017ca7a`: `Windows.Foundation.Collections.IIterator`1<Windows.Internal.Shell.Chaining.IChainLink>`
- `0x18017ca33`: `Windows.Foundation.Collections.IVectorView`1<Windows.Internal.Shell.Chaining.IChainLink>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::Shell::Chaining::IChainLink,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Shell::Chaining::IChainLink *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Shell::Chaining::IChainLink *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Shell::Chaining::IChainLink *>,0>>(
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
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rax
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x54u);
  v4 = v3 - 1;
  if ( v3 > 0x54 )
    v4 = 84;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.Shell.Chaining.IChainLink>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v30 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x58u);
  v7 = v6 - 1;
  if ( v6 > 0x58 )
    v7 = 88;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.Shell.Chaining.IChainLink>",
         v7,
         &v29,
         &v30);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x56u);
  v10 = v9 - 1;
  if ( v9 > 0x56 )
    v10 = 86;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.Shell.Chaining.IChainLink>",
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
  v22 = GUID_602076f4_9793_429d_a999_f951052e28e9;
  v23 = GUID_5f3c645e_9bbb_5278_b66a_b3b91222f682;
  v24 = GUID_bc3c36e9_6975_5bdd_8f0a_07d8d9136aa9;
  v25 = GUID_c6850dd9_2ffa_5d90_82ff_1d21fb413706;
  v26 = GUID_3fd15e42_1b6b_5849_86eb_3a0e746d1c7e;
  v20 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  v34 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v33, &v34);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v34, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v20);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    return (unsigned int)ActivationFactory;
  }
  v19 = 0;
  v15 = v20;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v15, v21, &v19);
  if ( ActivationFactory < 0 )
  {
    v16 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    v17 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return (unsigned int)ActivationFactory;
  }
  v18 = v19;
  v19 = 0;
  *a2 = v18;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  return 0;
}

```

## disassembly

```asm
0x18017c9a0  mov     [rsp-8+arg_0], rbx
0x18017c9a5  mov     [rsp-8+arg_10], rdi
0x18017c9aa  push    rbp
0x18017c9ab  lea     rbp, [rsp-30h]
0x18017c9b0  sub     rsp, 130h
0x18017c9b7  mov     rax, cs:__security_cookie
0x18017c9be  xor     rax, rsp
0x18017c9c1  mov     [rbp+30h+var_10], rax
0x18017c9c5  mov     rdi, rdx
0x18017c9c8  mov     [rbp+30h+string], 0
0x18017c9d0  mov     ebx, 54h ; 'T'
0x18017c9d5  mov     ecx, ebx; unsigned int
0x18017c9d7  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18017c9dc  lea     edx, [rax-1]
0x18017c9df  cmp     eax, ebx
0x18017c9e1  cmova   edx, ebx; length
0x18017c9e4  lea     r9, [rbp+30h+string]; string
0x18017c9e8  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18017c9ec  lea     rcx, aWindowsFoundat_40; "Windows.Foundation.Collections.IVector`"...
0x18017c9f3  call    cs:__imp_WindowsCreateStringReference
0x18017c9f9  test    eax, eax
0x18017c9fb  jns     short loc_18017CA0F
0x18017c9fd  xor     r9d, r9d; lpArguments
0x18017ca00  xor     r8d, r8d; nNumberOfArguments
0x18017ca03  lea     edx, [rbx-53h]; dwExceptionFlags
0x18017ca06  mov     ecx, eax; dwExceptionCode
0x18017ca08  call    cs:__imp_RaiseException
0x18017ca0e  int     3; Trap to Debugger
0x18017ca0f  mov     [rbp+30h+var_58], 0
0x18017ca17  mov     ebx, 58h ; 'X'
0x18017ca1c  mov     ecx, ebx; unsigned int
0x18017ca1e  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18017ca23  lea     edx, [rax-1]
0x18017ca26  cmp     eax, ebx
0x18017ca28  cmova   edx, ebx; length
0x18017ca2b  lea     r9, [rbp+30h+var_58]; string
0x18017ca2f  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18017ca33  lea     rcx, aWindowsFoundat_13; "Windows.Foundation.Collections.IVectorV"...
0x18017ca3a  call    cs:__imp_WindowsCreateStringReference
0x18017ca40  test    eax, eax
0x18017ca42  jns     short loc_18017CA56
0x18017ca44  xor     r9d, r9d; lpArguments
0x18017ca47  xor     r8d, r8d; nNumberOfArguments
0x18017ca4a  lea     edx, [rbx-57h]; dwExceptionFlags
0x18017ca4d  mov     ecx, eax; dwExceptionCode
0x18017ca4f  call    cs:__imp_RaiseException
0x18017ca55  int     3; Trap to Debugger
0x18017ca56  mov     [rbp+30h+var_38], 0
0x18017ca5e  mov     ebx, 56h ; 'V'
0x18017ca63  mov     ecx, ebx; unsigned int
0x18017ca65  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18017ca6a  lea     edx, [rax-1]
0x18017ca6d  cmp     eax, ebx
0x18017ca6f  cmova   edx, ebx; length
0x18017ca72  lea     r9, [rbp+30h+var_38]; string
0x18017ca76  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18017ca7a  lea     rcx, aWindowsFoundat_37; "Windows.Foundation.Collections.IIterato"...
0x18017ca81  call    cs:__imp_WindowsCreateStringReference
0x18017ca87  test    eax, eax
0x18017ca89  jns     short loc_18017CA9D
0x18017ca8b  xor     r9d, r9d; lpArguments
0x18017ca8e  xor     r8d, r8d; nNumberOfArguments
0x18017ca91  lea     edx, [rbx-55h]; dwExceptionFlags
0x18017ca94  mov     ecx, eax; dwExceptionCode
0x18017ca96  call    cs:__imp_RaiseException
0x18017ca9c  int     3; Trap to Debugger
0x18017ca9d  mov     rax, [rbp+30h+string]
0x18017caa1  mov     [rsp+130h+var_100], rax
0x18017caa6  mov     rax, [rbp+30h+var_58]
0x18017caaa  mov     [rsp+130h+var_F8], rax
0x18017caaf  mov     rax, [rbp+30h+var_38]
0x18017cab3  mov     [rsp+130h+var_F0], rax
0x18017cab8  movups  xmm0, xmmword ptr cs:_GUID_602076f4_9793_429d_a999_f951052e28e9.Data1
0x18017cabf  movdqu  [rsp+130h+var_E8], xmm0
0x18017cac5  movups  xmm1, xmmword ptr cs:_GUID_5f3c645e_9bbb_5278_b66a_b3b91222f682.Data1
0x18017cacc  movdqu  [rsp+130h+var_D8], xmm1
0x18017cad2  movups  xmm0, xmmword ptr cs:_GUID_bc3c36e9_6975_5bdd_8f0a_07d8d9136aa9.Data1
0x18017cad9  movdqu  [rsp+130h+var_C8], xmm0
0x18017cadf  movups  xmm1, xmmword ptr cs:_GUID_c6850dd9_2ffa_5d90_82ff_1d21fb413706.Data1
0x18017cae6  movdqu  [rsp+130h+var_B8], xmm1
0x18017caec  movups  xmm0, xmmword ptr cs:_GUID_3fd15e42_1b6b_5849_86eb_3a0e746d1c7e.Data1
0x18017caf3  movdqu  [rbp+30h+var_A8], xmm0
0x18017caf8  mov     [rsp+130h+var_108], 0
0x18017cb01  lea     rcx, [rsp+130h+var_108]
0x18017cb06  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017cb0b  mov     [rbp+30h+var_18], 0
0x18017cb13  lea     r9, [rbp+30h+var_18]; string
0x18017cb17  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18017cb1b  mov     edx, 2Ch ; ','; length
0x18017cb20  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18017cb27  call    cs:__imp_WindowsCreateStringReference
0x18017cb2d  test    eax, eax
0x18017cb2f  jns     short loc_18017CB44
0x18017cb31  xor     r9d, r9d; lpArguments
0x18017cb34  xor     r8d, r8d; nNumberOfArguments
0x18017cb37  lea     edx, [r9+1]; dwExceptionFlags
0x18017cb3b  mov     ecx, eax; dwExceptionCode
0x18017cb3d  call    cs:__imp_RaiseException
0x18017cb43  int     3; Trap to Debugger
0x18017cb44  lea     r8, [rsp+130h+var_108]
0x18017cb49  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18017cb50  mov     rcx, [rbp+30h+var_18]
0x18017cb54  call    cs:__imp_RoGetActivationFactory
0x18017cb5a  mov     ebx, eax
0x18017cb5c  test    eax, eax
0x18017cb5e  jns     short loc_18017CB71
0x18017cb60  lea     rcx, [rsp+130h+var_108]
0x18017cb65  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017cb6a  mov     eax, ebx
0x18017cb6c  jmp     loc_18017CC0A
0x18017cb71  mov     [rsp+130h+var_110], 0
0x18017cb7a  mov     rbx, [rsp+130h+var_108]
0x18017cb7f  lea     rcx, [rsp+130h+var_110]
0x18017cb84  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017cb89  lea     r8, [rsp+130h+var_110]
0x18017cb8e  lea     rdx, [rsp+130h+var_100]
0x18017cb93  mov     rcx, rbx
0x18017cb96  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18017cb9b  mov     ebx, eax
0x18017cb9d  test    eax, eax
0x18017cb9f  jns     short loc_18017CBE3
0x18017cba1  mov     rcx, [rsp+130h+var_110]
0x18017cba6  test    rcx, rcx
0x18017cba9  jz      short loc_18017CBC1
0x18017cbab  mov     [rsp+130h+var_110], 0
0x18017cbb4  mov     rdx, [rcx]
0x18017cbb7  mov     rax, [rdx+10h]
0x18017cbbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017cbc0  nop
0x18017cbc1  mov     rcx, [rsp+130h+var_108]
0x18017cbc6  test    rcx, rcx
0x18017cbc9  jz      short loc_18017CBE1
0x18017cbcb  mov     [rsp+130h+var_108], 0
0x18017cbd4  mov     rax, [rcx]
0x18017cbd7  mov     rax, [rax+10h]
0x18017cbdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017cbe0  nop
0x18017cbe1  jmp     short loc_18017CB6A
0x18017cbe3  mov     rax, [rsp+130h+var_110]
0x18017cbe8  mov     [rsp+130h+var_110], 0
0x18017cbf1  mov     [rdi], rax
0x18017cbf4  lea     rcx, [rsp+130h+var_110]
0x18017cbf9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017cbfe  lea     rcx, [rsp+130h+var_108]
0x18017cc03  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017cc08  xor     eax, eax
0x18017cc0a  mov     rcx, [rbp+30h+var_10]
0x18017cc0e  xor     rcx, rsp; StackCookie
0x18017cc11  call    __security_check_cookie
0x18017cc16  lea     r11, [rsp+130h+var_s0]
0x18017cc1e  mov     rbx, [r11+10h]
0x18017cc22  mov     rdi, [r11+20h]
0x18017cc26  mov     rsp, r11
0x18017cc29  pop     rbp
0x18017cc2a  retn
```
