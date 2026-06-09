# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::Protocol,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::Protocol *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::Protocol *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::Protocol *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::Protocol *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::Protocol *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::Protocol *>,0> * *)

- ea: `0x180021bc4`
- end: `0x180021e42`
- name: `??$CreateExternalObjectVector@VProtocol@StateRepository@Internal@Windows@@V?$AgileVector@PEAVProtocol@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVProtocol@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVProtocol@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVProtocol@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVProtocol@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVProtocol@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `638`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180021a68`
- `0x1801e8250`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x180021bc4`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021c2c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021c73`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021cba`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021d61`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021c2c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021c73`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021cba`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021d61`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180021d78`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180021d78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021c17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021c5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021ca5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021d4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021c17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021c5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021ca5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021d4b`

## string_xrefs

- `0x180021c10`: `Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.Protocol>`
- `0x180021c9e`: `Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.Protocol>`
- `0x180021c57`: `Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.Protocol>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::Protocol,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::Protocol *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::Protocol *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::Protocol *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x53u);
  v4 = v3 - 1;
  if ( v3 > 0x53 )
    v4 = 83;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.Protocol>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v30 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x57u);
  v7 = v6 - 1;
  if ( v6 > 0x57 )
    v7 = 87;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.Protocol>",
         v7,
         &v29,
         &v30);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x55u);
  v10 = v9 - 1;
  if ( v9 > 0x55 )
    v10 = 85;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.Protocol>",
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
  v22 = GUID_fdd7e51e_d1cc_41d9_ae36_a5fac6fe5216;
  v23 = GUID_cc120b37_0db1_536f_81c0_618b5008b969;
  v24 = GUID_63624def_cd42_5bcf_96e6_e27614e5d807;
  v25 = GUID_fbcc47f2_4d57_5bdf_a7ba_2a7e2e10859d;
  v26 = GUID_02eddd9e_b4a1_5a96_ae13_1dfc22e58e97;
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
0x180021bc4  mov     [rsp-8+arg_0], rbx
0x180021bc9  mov     [rsp-8+arg_10], rdi
0x180021bce  push    rbp
0x180021bcf  lea     rbp, [rsp-30h]
0x180021bd4  sub     rsp, 130h
0x180021bdb  mov     rax, cs:__security_cookie
0x180021be2  xor     rax, rsp
0x180021be5  mov     [rbp+30h+var_10], rax
0x180021be9  mov     rdi, rdx
0x180021bec  mov     [rbp+30h+string], 0
0x180021bf4  mov     ebx, 53h ; 'S'
0x180021bf9  mov     ecx, ebx; unsigned int
0x180021bfb  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180021c00  lea     edx, [rax-1]
0x180021c03  cmp     eax, ebx
0x180021c05  cmova   edx, ebx; length
0x180021c08  lea     r9, [rbp+30h+string]; string
0x180021c0c  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180021c10  lea     rcx, aWindowsFoundat_188; "Windows.Foundation.Collections.IVector`"...
0x180021c17  call    cs:__imp_WindowsCreateStringReference
0x180021c1d  test    eax, eax
0x180021c1f  jns     short loc_180021C33
0x180021c21  xor     r9d, r9d; lpArguments
0x180021c24  xor     r8d, r8d; nNumberOfArguments
0x180021c27  lea     edx, [rbx-52h]; dwExceptionFlags
0x180021c2a  mov     ecx, eax; dwExceptionCode
0x180021c2c  call    cs:__imp_RaiseException
0x180021c32  int     3; Trap to Debugger
0x180021c33  mov     [rbp+30h+var_58], 0
0x180021c3b  mov     ebx, 57h ; 'W'
0x180021c40  mov     ecx, ebx; unsigned int
0x180021c42  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180021c47  lea     edx, [rax-1]
0x180021c4a  cmp     eax, ebx
0x180021c4c  cmova   edx, ebx; length
0x180021c4f  lea     r9, [rbp+30h+var_58]; string
0x180021c53  lea     r8, [rbp+30h+var_70]; hstringHeader
0x180021c57  lea     rcx, aWindowsFoundat_45; "Windows.Foundation.Collections.IVectorV"...
0x180021c5e  call    cs:__imp_WindowsCreateStringReference
0x180021c64  test    eax, eax
0x180021c66  jns     short loc_180021C7A
0x180021c68  xor     r9d, r9d; lpArguments
0x180021c6b  xor     r8d, r8d; nNumberOfArguments
0x180021c6e  lea     edx, [rbx-56h]; dwExceptionFlags
0x180021c71  mov     ecx, eax; dwExceptionCode
0x180021c73  call    cs:__imp_RaiseException
0x180021c79  int     3; Trap to Debugger
0x180021c7a  mov     [rbp+30h+var_38], 0
0x180021c82  mov     ebx, 55h ; 'U'
0x180021c87  mov     ecx, ebx; unsigned int
0x180021c89  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180021c8e  lea     edx, [rax-1]
0x180021c91  cmp     eax, ebx
0x180021c93  cmova   edx, ebx; length
0x180021c96  lea     r9, [rbp+30h+var_38]; string
0x180021c9a  lea     r8, [rbp+30h+var_50]; hstringHeader
0x180021c9e  lea     rcx, aWindowsFoundat_35; "Windows.Foundation.Collections.IIterato"...
0x180021ca5  call    cs:__imp_WindowsCreateStringReference
0x180021cab  test    eax, eax
0x180021cad  jns     short loc_180021CC1
0x180021caf  xor     r9d, r9d; lpArguments
0x180021cb2  xor     r8d, r8d; nNumberOfArguments
0x180021cb5  lea     edx, [rbx-54h]; dwExceptionFlags
0x180021cb8  mov     ecx, eax; dwExceptionCode
0x180021cba  call    cs:__imp_RaiseException
0x180021cc0  int     3; Trap to Debugger
0x180021cc1  mov     rax, [rbp+30h+string]
0x180021cc5  mov     [rsp+130h+var_100], rax
0x180021cca  mov     rax, [rbp+30h+var_58]
0x180021cce  mov     [rsp+130h+var_F8], rax
0x180021cd3  mov     rax, [rbp+30h+var_38]
0x180021cd7  mov     [rsp+130h+var_F0], rax
0x180021cdc  movups  xmm0, xmmword ptr cs:_GUID_fdd7e51e_d1cc_41d9_ae36_a5fac6fe5216.Data1
0x180021ce3  movdqu  [rsp+130h+var_E8], xmm0
0x180021ce9  movups  xmm1, xmmword ptr cs:_GUID_cc120b37_0db1_536f_81c0_618b5008b969.Data1
0x180021cf0  movdqu  [rsp+130h+var_D8], xmm1
0x180021cf6  movups  xmm0, xmmword ptr cs:_GUID_63624def_cd42_5bcf_96e6_e27614e5d807.Data1
0x180021cfd  movdqu  [rsp+130h+var_C8], xmm0
0x180021d03  movups  xmm1, xmmword ptr cs:_GUID_fbcc47f2_4d57_5bdf_a7ba_2a7e2e10859d.Data1
0x180021d0a  movdqu  [rsp+130h+var_B8], xmm1
0x180021d10  movups  xmm0, xmmword ptr cs:_GUID_02eddd9e_b4a1_5a96_ae13_1dfc22e58e97.Data1
0x180021d17  movdqu  [rbp+30h+var_A8], xmm0
0x180021d1c  mov     [rsp+130h+var_110], 0
0x180021d25  lea     rcx, [rsp+130h+var_110]
0x180021d2a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180021d2f  mov     [rbp+30h+var_18], 0
0x180021d37  lea     r9, [rbp+30h+var_18]; string
0x180021d3b  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180021d3f  mov     edx, 2Ch ; ','; length
0x180021d44  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180021d4b  call    cs:__imp_WindowsCreateStringReference
0x180021d51  test    eax, eax
0x180021d53  jns     short loc_180021D68
0x180021d55  xor     r9d, r9d; lpArguments
0x180021d58  xor     r8d, r8d; nNumberOfArguments
0x180021d5b  lea     edx, [r9+1]; dwExceptionFlags
0x180021d5f  mov     ecx, eax; dwExceptionCode
0x180021d61  call    cs:__imp_RaiseException
0x180021d67  int     3; Trap to Debugger
0x180021d68  lea     r8, [rsp+130h+var_110]
0x180021d6d  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180021d74  mov     rcx, [rbp+30h+var_18]
0x180021d78  call    cs:__imp_RoGetActivationFactory
0x180021d7e  mov     ebx, eax
0x180021d80  test    eax, eax
0x180021d82  jns     short loc_180021DA8
0x180021d84  mov     rcx, [rsp+130h+var_110]
0x180021d89  test    rcx, rcx
0x180021d8c  jz      short loc_180021DA4
0x180021d8e  mov     [rsp+130h+var_110], 0
0x180021d97  mov     rdx, [rcx]
0x180021d9a  mov     rax, [rdx+10h]
0x180021d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021da3  nop
0x180021da4  mov     eax, ebx
0x180021da6  jmp     short loc_180021E21
0x180021da8  mov     [rsp+130h+var_108], 0
0x180021db1  mov     rbx, [rsp+130h+var_110]
0x180021db6  lea     rcx, [rsp+130h+var_108]
0x180021dbb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180021dc0  lea     r8, [rsp+130h+var_108]
0x180021dc5  lea     rdx, [rsp+130h+var_100]
0x180021dca  mov     rcx, rbx
0x180021dcd  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x180021dd2  mov     ebx, eax
0x180021dd4  test    eax, eax
0x180021dd6  jns     short loc_180021DEE
0x180021dd8  lea     rcx, [rsp+130h+var_108]
0x180021ddd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180021de2  lea     rcx, [rsp+130h+var_110]
0x180021de7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180021dec  jmp     short loc_180021DA4
0x180021dee  mov     rax, [rsp+130h+var_108]
0x180021df3  mov     [rsp+130h+var_108], 0
0x180021dfc  mov     [rdi], rax
0x180021dff  mov     rcx, [rsp+130h+var_110]
0x180021e04  test    rcx, rcx
0x180021e07  jz      short loc_180021E1F
0x180021e09  mov     [rsp+130h+var_110], 0
0x180021e12  mov     rax, [rcx]
0x180021e15  mov     rax, [rax+10h]
0x180021e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e1e  nop
0x180021e1f  xor     eax, eax
0x180021e21  mov     rcx, [rbp+30h+var_10]
0x180021e25  xor     rcx, rsp; StackCookie
0x180021e28  call    __security_check_cookie
0x180021e2d  lea     r11, [rsp+130h+var_s0]
0x180021e35  mov     rbx, [r11+10h]
0x180021e39  mov     rdi, [r11+20h]
0x180021e3d  mov     rsp, r11
0x180021e40  pop     rbp
0x180021e41  retn
```
