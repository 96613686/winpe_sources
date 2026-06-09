# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo *>,0> * *)

- ea: `0x180022d7c`
- end: `0x18002303b`
- name: `??$CreateExternalObjectVector@VFileTypeAssociationLauncherInfo@StateRepository@Internal@Windows@@V?$AgileVector@PEAVFileTypeAssociationLauncherInfo@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVFileTypeAssociationLauncherInfo@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVFileTypeAssociationLauncherInfo@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVFileTypeAssociationLauncherInfo@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVFileTypeAssociationLauncherInfo@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVFileTypeAssociationLauncherInfo@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `703`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180022614`

## callees

- `0x1800049bc`
- `0x180022d7c`
- `0x180023044`
- `0x18008a030`
- `0x1800a6468`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022ffb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002300e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023021`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023034`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022ffb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002300e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023021`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023034`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022dcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022e08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022e41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022ed7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022dcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022e08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022e41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022ed7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180022ef5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180022ef5`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x6Au);
  v4 = v3 - 1;
  if ( v3 > 0x6A )
    v4 = 106;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.FileTypeAssociationLauncherInfo>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x6Eu);
  v7 = v6 - 1;
  if ( v6 > 0x6E )
    v7 = 110;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.FileTypeAssociationLauncherInfo>",
         v7,
         &v31,
         &v32);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v34 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x6Cu);
  v10 = v9 - 1;
  if ( v9 > 0x6C )
    v10 = 108;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.FileTypeAssociationLauncherInfo>",
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
  v24 = GUID_8f8bf3e3_b9be_4969_9eb5_e49b5a12d2ec;
  v25 = GUID_fc55d7f4_c1af_5c25_b77d_d1f9516765b4;
  v26 = GUID_15f99879_aa48_571f_845d_144893440cfd;
  v27 = GUID_2174d9a7_5463_51ac_b54a_c798378d9298;
  v28 = GUID_3eb826b1_30bc_5da4_8dbd_b32384a8d5c6;
  v21 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v36 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v35, &v36);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    JUMPOUT(0x18002303ALL);
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
0x180022d7c  mov     [rsp-8+arg_0], rbx
0x180022d81  mov     [rsp-8+arg_10], rdi
0x180022d86  push    rbp
0x180022d87  lea     rbp, [rsp-30h]
0x180022d8c  sub     rsp, 130h
0x180022d93  mov     rax, cs:__security_cookie
0x180022d9a  xor     rax, rsp
0x180022d9d  mov     [rbp+30h+var_10], rax
0x180022da1  mov     rdi, rdx
0x180022da4  mov     [rbp+30h+string], 0
0x180022dac  mov     ebx, 6Ah ; 'j'
0x180022db1  mov     ecx, ebx; unsigned int
0x180022db3  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180022db8  lea     edx, [rax-1]
0x180022dbb  cmp     eax, ebx
0x180022dbd  cmova   edx, ebx; length
0x180022dc0  lea     r9, [rbp+30h+string]; string
0x180022dc4  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180022dc8  lea     rcx, aWindowsFoundat_34; "Windows.Foundation.Collections.IVector`"...
0x180022dcf  call    cs:__imp_WindowsCreateStringReference
0x180022dd5  test    eax, eax
0x180022dd7  js      loc_180022FEF
0x180022ddd  mov     [rbp+30h+var_58], 0
0x180022de5  mov     ebx, 6Eh ; 'n'
0x180022dea  mov     ecx, ebx; unsigned int
0x180022dec  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180022df1  lea     edx, [rax-1]
0x180022df4  cmp     eax, ebx
0x180022df6  cmova   edx, ebx; length
0x180022df9  lea     r9, [rbp+30h+var_58]; string
0x180022dfd  lea     r8, [rbp+30h+var_70]; hstringHeader
0x180022e01  lea     rcx, aWindowsFoundat_21; "Windows.Foundation.Collections.IVectorV"...
0x180022e08  call    cs:__imp_WindowsCreateStringReference
0x180022e0e  test    eax, eax
0x180022e10  js      loc_180023002
0x180022e16  mov     [rbp+30h+var_38], 0
0x180022e1e  mov     ebx, 6Ch ; 'l'
0x180022e23  mov     ecx, ebx; unsigned int
0x180022e25  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180022e2a  lea     edx, [rax-1]
0x180022e2d  cmp     eax, ebx
0x180022e2f  cmova   edx, ebx; length
0x180022e32  lea     r9, [rbp+30h+var_38]; string
0x180022e36  lea     r8, [rbp+30h+var_50]; hstringHeader
0x180022e3a  lea     rcx, aWindowsFoundat_23; "Windows.Foundation.Collections.IIterato"...
0x180022e41  call    cs:__imp_WindowsCreateStringReference
0x180022e47  test    eax, eax
0x180022e49  js      loc_180023015
0x180022e4f  mov     rax, [rbp+30h+string]
0x180022e53  mov     [rsp+130h+var_100], rax
0x180022e58  mov     rax, [rbp+30h+var_58]
0x180022e5c  mov     [rsp+130h+var_F8], rax
0x180022e61  mov     rax, [rbp+30h+var_38]
0x180022e65  mov     [rsp+130h+var_F0], rax
0x180022e6a  movups  xmm0, xmmword ptr cs:_GUID_8f8bf3e3_b9be_4969_9eb5_e49b5a12d2ec.Data1
0x180022e71  movdqu  [rsp+130h+var_E8], xmm0
0x180022e77  movups  xmm1, xmmword ptr cs:_GUID_fc55d7f4_c1af_5c25_b77d_d1f9516765b4.Data1
0x180022e7e  movdqu  [rsp+130h+var_D8], xmm1
0x180022e84  movups  xmm0, xmmword ptr cs:_GUID_15f99879_aa48_571f_845d_144893440cfd.Data1
0x180022e8b  movdqu  [rsp+130h+var_C8], xmm0
0x180022e91  movups  xmm1, xmmword ptr cs:_GUID_2174d9a7_5463_51ac_b54a_c798378d9298.Data1
0x180022e98  movdqu  [rsp+130h+var_B8], xmm1
0x180022e9e  movups  xmm0, xmmword ptr cs:_GUID_3eb826b1_30bc_5da4_8dbd_b32384a8d5c6.Data1
0x180022ea5  movdqu  [rbp+30h+var_A8], xmm0
0x180022eaa  mov     [rsp+130h+var_110], 0
0x180022eb3  lea     rcx, [rsp+130h+var_110]
0x180022eb8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180022ebd  mov     [rbp+30h+var_18], 0
0x180022ec5  lea     r9, [rbp+30h+var_18]; string
0x180022ec9  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180022ecd  lea     edx, [rbx-40h]; length
0x180022ed0  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180022ed7  call    cs:__imp_WindowsCreateStringReference
0x180022edd  test    eax, eax
0x180022edf  js      loc_180023028
0x180022ee5  lea     r8, [rsp+130h+var_110]
0x180022eea  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180022ef1  mov     rcx, [rbp+30h+var_18]
0x180022ef5  call    cs:__imp_RoGetActivationFactory
0x180022efb  mov     ebx, eax
0x180022efd  test    eax, eax
0x180022eff  js      loc_180022FCD
0x180022f05  mov     [rsp+130h+var_108], 0
0x180022f0e  mov     rbx, [rsp+130h+var_110]
0x180022f13  lea     rcx, [rsp+130h+var_108]
0x180022f18  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180022f1d  lea     r8, [rsp+130h+var_108]
0x180022f22  lea     rdx, [rsp+130h+var_100]
0x180022f27  mov     rcx, rbx
0x180022f2a  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x180022f2f  mov     ebx, eax
0x180022f31  test    eax, eax
0x180022f33  jns     short loc_180022F98
0x180022f35  mov     rcx, [rsp+130h+var_108]
0x180022f3a  test    rcx, rcx
0x180022f3d  jz      short loc_180022F55
0x180022f3f  mov     [rsp+130h+var_108], 0
0x180022f48  mov     rdx, [rcx]
0x180022f4b  mov     rax, [rdx+10h]
0x180022f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f54  nop
0x180022f55  mov     rcx, [rsp+130h+var_110]
0x180022f5a  test    rcx, rcx
0x180022f5d  jz      short loc_180022F75
0x180022f5f  mov     [rsp+130h+var_110], 0
0x180022f68  mov     rax, [rcx]
0x180022f6b  mov     rax, [rax+10h]
0x180022f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f74  nop
0x180022f75  mov     eax, ebx
0x180022f77  mov     rcx, [rbp+30h+var_10]
0x180022f7b  xor     rcx, rsp; StackCookie
0x180022f7e  call    __security_check_cookie
0x180022f83  lea     r11, [rsp+130h+var_s0]
0x180022f8b  mov     rbx, [r11+10h]
0x180022f8f  mov     rdi, [r11+20h]
0x180022f93  mov     rsp, r11
0x180022f96  pop     rbp
0x180022f97  retn
0x180022f98  mov     rax, [rsp+130h+var_108]
0x180022f9d  mov     [rsp+130h+var_108], 0
0x180022fa6  mov     [rdi], rax
0x180022fa9  mov     rcx, [rsp+130h+var_110]
0x180022fae  test    rcx, rcx
0x180022fb1  jz      short loc_180022FC9
0x180022fb3  mov     [rsp+130h+var_110], 0
0x180022fbc  mov     rax, [rcx]
0x180022fbf  mov     rax, [rax+10h]
0x180022fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022fc8  nop
0x180022fc9  xor     eax, eax
0x180022fcb  jmp     short loc_180022F77
0x180022fcd  mov     rcx, [rsp+130h+var_110]
0x180022fd2  test    rcx, rcx
0x180022fd5  jz      short loc_180022FED
0x180022fd7  mov     [rsp+130h+var_110], 0
0x180022fe0  mov     rdx, [rcx]
0x180022fe3  mov     rax, [rdx+10h]
0x180022fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022fec  nop
0x180022fed  jmp     short loc_180022F75
0x180022fef  xor     r9d, r9d; lpArguments
0x180022ff2  xor     r8d, r8d; nNumberOfArguments
0x180022ff5  lea     edx, [r9+1]; dwExceptionFlags
0x180022ff9  mov     ecx, eax; dwExceptionCode
0x180022ffb  call    cs:__imp_RaiseException
0x180023001  int     3; Trap to Debugger
0x180023002  xor     r9d, r9d; lpArguments
0x180023005  xor     r8d, r8d; nNumberOfArguments
0x180023008  lea     edx, [r9+1]; dwExceptionFlags
0x18002300c  mov     ecx, eax; dwExceptionCode
0x18002300e  call    cs:__imp_RaiseException
0x180023014  int     3; Trap to Debugger
0x180023015  xor     r9d, r9d; lpArguments
0x180023018  xor     r8d, r8d; nNumberOfArguments
0x18002301b  lea     edx, [r9+1]; dwExceptionFlags
0x18002301f  mov     ecx, eax; dwExceptionCode
0x180023021  call    cs:__imp_RaiseException
0x180023027  int     3; Trap to Debugger
0x180023028  xor     r9d, r9d; lpArguments
0x18002302b  xor     r8d, r8d; nNumberOfArguments
0x18002302e  lea     edx, [r9+1]; dwExceptionFlags
0x180023032  mov     ecx, eax; dwExceptionCode
0x180023034  call    cs:__imp_RaiseException
```
