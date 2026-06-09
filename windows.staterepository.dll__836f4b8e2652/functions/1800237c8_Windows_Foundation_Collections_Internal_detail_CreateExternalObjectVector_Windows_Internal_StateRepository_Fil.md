# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo *>,0> * *)

- ea: `0x1800237c8`
- end: `0x180023a69`
- name: `??$CreateExternalObjectVector@VFileTypeAssociationLauncherInfo@StateRepository@Internal@Windows@@V?$AgileVector@PEAVFileTypeAssociationLauncherInfo@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVFileTypeAssociationLauncherInfo@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVFileTypeAssociationLauncherInfo@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVFileTypeAssociationLauncherInfo@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVFileTypeAssociationLauncherInfo@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVFileTypeAssociationLauncherInfo@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `673`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002366c`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x1800237c8`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023830`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023877`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800238be`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023965`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023830`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023877`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800238be`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023965`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002397c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002397c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002381b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180023862`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800238a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002394f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002381b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180023862`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800238a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002394f`

## pseudocode

```c
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
  __int64 v14; // rcx
  __int64 v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v21; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v22[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v23; // [rsp+48h] [rbp-B8h]
  GUID v24; // [rsp+58h] [rbp-A8h]
  GUID v25; // [rsp+68h] [rbp-98h]
  GUID v26; // [rsp+78h] [rbp-88h]
  GUID v27; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v30; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v31; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v32; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v33; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v34; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v35; // [rsp+118h] [rbp+18h] BYREF

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
  v31 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x6Eu);
  v7 = v6 - 1;
  if ( v6 > 0x6E )
    v7 = 110;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.FileTypeAssociationLauncherInfo>",
         v7,
         &v30,
         &v31);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v33 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x6Cu);
  v10 = v9 - 1;
  if ( v9 > 0x6C )
    v10 = 108;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.FileTypeAssociationLauncherInfo>",
          v10,
          &v32,
          &v33);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v22[0] = string;
  v22[1] = v31;
  v22[2] = v33;
  v23 = GUID_8f8bf3e3_b9be_4969_9eb5_e49b5a12d2ec;
  v24 = GUID_fc55d7f4_c1af_5c25_b77d_d1f9516765b4;
  v25 = GUID_15f99879_aa48_571f_845d_144893440cfd;
  v26 = GUID_2174d9a7_5463_51ac_b54a_c798378d9298;
  v27 = GUID_3eb826b1_30bc_5da4_8dbd_b32384a8d5c6;
  v20 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  v35 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v34, &v35);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v35, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v20);
  if ( ActivationFactory < 0 )
  {
    v14 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return (unsigned int)ActivationFactory;
  }
  v21 = 0;
  v16 = v20;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v16, v22, &v21);
  if ( ActivationFactory < 0 )
  {
    v17 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return (unsigned int)ActivationFactory;
  }
  v19 = v21;
  v21 = 0;
  *a2 = v19;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  return 0;
}

```

## disassembly

```asm
0x1800237c8  mov     [rsp-8+arg_0], rbx
0x1800237cd  mov     [rsp-8+arg_10], rdi
0x1800237d2  push    rbp
0x1800237d3  lea     rbp, [rsp-30h]
0x1800237d8  sub     rsp, 130h
0x1800237df  mov     rax, cs:__security_cookie
0x1800237e6  xor     rax, rsp
0x1800237e9  mov     [rbp+30h+var_10], rax
0x1800237ed  mov     rdi, rdx
0x1800237f0  mov     [rbp+30h+string], 0
0x1800237f8  mov     ebx, 6Ah ; 'j'
0x1800237fd  mov     ecx, ebx; unsigned int
0x1800237ff  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180023804  lea     edx, [rax-1]
0x180023807  cmp     eax, ebx
0x180023809  cmova   edx, ebx; length
0x18002380c  lea     r9, [rbp+30h+string]; string
0x180023810  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180023814  lea     rcx, aWindowsFoundat_161; "Windows.Foundation.Collections.IVector`"...
0x18002381b  call    cs:__imp_WindowsCreateStringReference
0x180023821  test    eax, eax
0x180023823  jns     short loc_180023837
0x180023825  xor     r9d, r9d; lpArguments
0x180023828  xor     r8d, r8d; nNumberOfArguments
0x18002382b  lea     edx, [rbx-69h]; dwExceptionFlags
0x18002382e  mov     ecx, eax; dwExceptionCode
0x180023830  call    cs:__imp_RaiseException
0x180023836  int     3; Trap to Debugger
0x180023837  mov     [rbp+30h+var_58], 0
0x18002383f  mov     ebx, 6Eh ; 'n'
0x180023844  mov     ecx, ebx; unsigned int
0x180023846  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002384b  lea     edx, [rax-1]
0x18002384e  cmp     eax, ebx
0x180023850  cmova   edx, ebx; length
0x180023853  lea     r9, [rbp+30h+var_58]; string
0x180023857  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18002385b  lea     rcx, aWindowsFoundat_125; "Windows.Foundation.Collections.IVectorV"...
0x180023862  call    cs:__imp_WindowsCreateStringReference
0x180023868  test    eax, eax
0x18002386a  jns     short loc_18002387E
0x18002386c  xor     r9d, r9d; lpArguments
0x18002386f  xor     r8d, r8d; nNumberOfArguments
0x180023872  lea     edx, [rbx-6Dh]; dwExceptionFlags
0x180023875  mov     ecx, eax; dwExceptionCode
0x180023877  call    cs:__imp_RaiseException
0x18002387d  int     3; Trap to Debugger
0x18002387e  mov     [rbp+30h+var_38], 0
0x180023886  mov     ebx, 6Ch ; 'l'
0x18002388b  mov     ecx, ebx; unsigned int
0x18002388d  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180023892  lea     edx, [rax-1]
0x180023895  cmp     eax, ebx
0x180023897  cmova   edx, ebx; length
0x18002389a  lea     r9, [rbp+30h+var_38]; string
0x18002389e  lea     r8, [rbp+30h+var_50]; hstringHeader
0x1800238a2  lea     rcx, aWindowsFoundat_129; "Windows.Foundation.Collections.IIterato"...
0x1800238a9  call    cs:__imp_WindowsCreateStringReference
0x1800238af  test    eax, eax
0x1800238b1  jns     short loc_1800238C5
0x1800238b3  xor     r9d, r9d; lpArguments
0x1800238b6  xor     r8d, r8d; nNumberOfArguments
0x1800238b9  lea     edx, [rbx-6Bh]; dwExceptionFlags
0x1800238bc  mov     ecx, eax; dwExceptionCode
0x1800238be  call    cs:__imp_RaiseException
0x1800238c4  int     3; Trap to Debugger
0x1800238c5  mov     rax, [rbp+30h+string]
0x1800238c9  mov     [rsp+130h+var_100], rax
0x1800238ce  mov     rax, [rbp+30h+var_58]
0x1800238d2  mov     [rsp+130h+var_F8], rax
0x1800238d7  mov     rax, [rbp+30h+var_38]
0x1800238db  mov     [rsp+130h+var_F0], rax
0x1800238e0  movups  xmm0, xmmword ptr cs:_GUID_8f8bf3e3_b9be_4969_9eb5_e49b5a12d2ec.Data1
0x1800238e7  movdqu  [rsp+130h+var_E8], xmm0
0x1800238ed  movups  xmm1, xmmword ptr cs:_GUID_fc55d7f4_c1af_5c25_b77d_d1f9516765b4.Data1
0x1800238f4  movdqu  [rsp+130h+var_D8], xmm1
0x1800238fa  movups  xmm0, xmmword ptr cs:_GUID_15f99879_aa48_571f_845d_144893440cfd.Data1
0x180023901  movdqu  [rsp+130h+var_C8], xmm0
0x180023907  movups  xmm1, xmmword ptr cs:_GUID_2174d9a7_5463_51ac_b54a_c798378d9298.Data1
0x18002390e  movdqu  [rsp+130h+var_B8], xmm1
0x180023914  movups  xmm0, xmmword ptr cs:_GUID_3eb826b1_30bc_5da4_8dbd_b32384a8d5c6.Data1
0x18002391b  movdqu  [rbp+30h+var_A8], xmm0
0x180023920  mov     [rsp+130h+var_110], 0
0x180023929  lea     rcx, [rsp+130h+var_110]
0x18002392e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180023933  mov     [rbp+30h+var_18], 0
0x18002393b  lea     r9, [rbp+30h+var_18]; string
0x18002393f  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180023943  mov     edx, 2Ch ; ','; length
0x180023948  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18002394f  call    cs:__imp_WindowsCreateStringReference
0x180023955  test    eax, eax
0x180023957  jns     short loc_18002396C
0x180023959  xor     r9d, r9d; lpArguments
0x18002395c  xor     r8d, r8d; nNumberOfArguments
0x18002395f  lea     edx, [r9+1]; dwExceptionFlags
0x180023963  mov     ecx, eax; dwExceptionCode
0x180023965  call    cs:__imp_RaiseException
0x18002396b  int     3; Trap to Debugger
0x18002396c  lea     r8, [rsp+130h+var_110]
0x180023971  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180023978  mov     rcx, [rbp+30h+var_18]
0x18002397c  call    cs:__imp_RoGetActivationFactory
0x180023982  mov     ebx, eax
0x180023984  test    eax, eax
0x180023986  jns     short loc_1800239AF
0x180023988  mov     rcx, [rsp+130h+var_110]
0x18002398d  test    rcx, rcx
0x180023990  jz      short loc_1800239A8
0x180023992  mov     [rsp+130h+var_110], 0
0x18002399b  mov     rdx, [rcx]
0x18002399e  mov     rax, [rdx+10h]
0x1800239a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239a7  nop
0x1800239a8  mov     eax, ebx
0x1800239aa  jmp     loc_180023A48
0x1800239af  mov     [rsp+130h+var_108], 0
0x1800239b8  mov     rbx, [rsp+130h+var_110]
0x1800239bd  lea     rcx, [rsp+130h+var_108]
0x1800239c2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800239c7  lea     r8, [rsp+130h+var_108]
0x1800239cc  lea     rdx, [rsp+130h+var_100]
0x1800239d1  mov     rcx, rbx
0x1800239d4  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x1800239d9  mov     ebx, eax
0x1800239db  test    eax, eax
0x1800239dd  jns     short loc_180023A21
0x1800239df  mov     rcx, [rsp+130h+var_108]
0x1800239e4  test    rcx, rcx
0x1800239e7  jz      short loc_1800239FF
0x1800239e9  mov     [rsp+130h+var_108], 0
0x1800239f2  mov     rdx, [rcx]
0x1800239f5  mov     rax, [rdx+10h]
0x1800239f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239fe  nop
0x1800239ff  mov     rcx, [rsp+130h+var_110]
0x180023a04  test    rcx, rcx
0x180023a07  jz      short loc_180023A1F
0x180023a09  mov     [rsp+130h+var_110], 0
0x180023a12  mov     rax, [rcx]
0x180023a15  mov     rax, [rax+10h]
0x180023a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a1e  nop
0x180023a1f  jmp     short loc_1800239A8
0x180023a21  mov     rax, [rsp+130h+var_108]
0x180023a26  mov     [rsp+130h+var_108], 0
0x180023a2f  mov     [rdi], rax
0x180023a32  lea     rcx, [rsp+130h+var_108]
0x180023a37  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180023a3c  lea     rcx, [rsp+130h+var_110]
0x180023a41  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180023a46  xor     eax, eax
0x180023a48  mov     rcx, [rbp+30h+var_10]
0x180023a4c  xor     rcx, rsp; StackCookie
0x180023a4f  call    __security_check_cookie
0x180023a54  lea     r11, [rsp+130h+var_s0]
0x180023a5c  mov     rbx, [r11+10h]
0x180023a60  mov     rdi, [r11+20h]
0x180023a64  mov     rsp, r11
0x180023a67  pop     rbp
0x180023a68  retn
```
