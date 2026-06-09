# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::System::Internal::Launch::ExtensionInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::System::Internal::Launch::ExtensionInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::Internal::Launch::ExtensionInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::Internal::Launch::ExtensionInfo *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::System::Internal::Launch::ExtensionInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::Internal::Launch::ExtensionInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::Internal::Launch::ExtensionInfo *>,0> * *)

- ea: `0x1800217e0`
- end: `0x180021a81`
- name: `??$CreateExternalObjectVector@VExtensionInfo@Launch@Internal@System@Windows@@V?$AgileVector@PEAVExtensionInfo@Launch@Internal@System@Windows@@U?$DefaultEqualityPredicate@PEAVExtensionInfo@Launch@Internal@System@Windows@@@3Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVExtensionInfo@Launch@Internal@System@Windows@@@3785@$0A@@3Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVExtensionInfo@Launch@Internal@System@Windows@@U?$DefaultEqualityPredicate@PEAVExtensionInfo@Launch@Internal@System@Windows@@@3Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVExtensionInfo@Launch@Internal@System@Windows@@@3785@$0A@@1234@@Z`
- size: `673`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021ae4`
- `0x18002984c`
- `0x18002cf0c`

## callees

- `0x1800049bc`
- `0x1800217e0`
- `0x180023044`
- `0x18008a030`
- `0x1800a6468`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021848`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002188f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800218d6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002197d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021848`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002188f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800218d6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002197d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021833`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002187a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800218c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021967`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021833`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002187a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800218c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021967`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180021994`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180021994`

## string_xrefs

- `0x18002182c`: `Windows.Foundation.Collections.IVector`1<Windows.System.Internal.Launch.ExtensionInfo>`
- `0x180021873`: `Windows.Foundation.Collections.IVectorView`1<Windows.System.Internal.Launch.ExtensionInfo>`
- `0x1800218ba`: `Windows.Foundation.Collections.IIterator`1<Windows.System.Internal.Launch.ExtensionInfo>`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::System::Internal::Launch::ExtensionInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::System::Internal::Launch::ExtensionInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::Internal::Launch::ExtensionInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::Internal::Launch::ExtensionInfo *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x56u);
  v4 = v3 - 1;
  if ( v3 > 0x56 )
    v4 = 86;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.System.Internal.Launch.ExtensionInfo>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Au);
  v7 = v6 - 1;
  if ( v6 > 0x5A )
    v7 = 90;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.System.Internal.Launch.ExtensionInfo>",
         v7,
         &v30,
         &v31);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v33 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x58u);
  v10 = v9 - 1;
  if ( v9 > 0x58 )
    v10 = 88;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.System.Internal.Launch.ExtensionInfo>",
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
  v23 = GUID_def041c5_cd85_4add_959b_e848f800d000;
  v24 = GUID_a0cd89fa_c82c_5db1_b2d1_cd32747e65eb;
  v25 = GUID_49244656_5ea6_5680_bf99_87ef7636f6c8;
  v26 = GUID_46fe7bc0_d826_574d_985e_9a777db6beca;
  v27 = GUID_9808ea27_0bf8_5e8c_95c5_d873cb12c525;
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
0x1800217e0  mov     [rsp-8+arg_0], rbx
0x1800217e5  mov     [rsp-8+arg_10], rdi
0x1800217ea  push    rbp
0x1800217eb  lea     rbp, [rsp-30h]
0x1800217f0  sub     rsp, 130h
0x1800217f7  mov     rax, cs:__security_cookie
0x1800217fe  xor     rax, rsp
0x180021801  mov     [rbp+30h+var_10], rax
0x180021805  mov     rdi, rdx
0x180021808  mov     [rbp+30h+string], 0
0x180021810  mov     ebx, 56h ; 'V'
0x180021815  mov     ecx, ebx; unsigned int
0x180021817  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002181c  lea     edx, [rax-1]
0x18002181f  cmp     eax, ebx
0x180021821  cmova   edx, ebx; length
0x180021824  lea     r9, [rbp+30h+string]; string
0x180021828  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18002182c  lea     rcx, aWindowsFoundat_33; "Windows.Foundation.Collections.IVector`"...
0x180021833  call    cs:__imp_WindowsCreateStringReference
0x180021839  test    eax, eax
0x18002183b  jns     short loc_18002184F
0x18002183d  xor     r9d, r9d; lpArguments
0x180021840  xor     r8d, r8d; nNumberOfArguments
0x180021843  lea     edx, [rbx-55h]; dwExceptionFlags
0x180021846  mov     ecx, eax; dwExceptionCode
0x180021848  call    cs:__imp_RaiseException
0x18002184e  int     3; Trap to Debugger
0x18002184f  mov     [rbp+30h+var_58], 0
0x180021857  mov     ebx, 5Ah ; 'Z'
0x18002185c  mov     ecx, ebx; unsigned int
0x18002185e  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180021863  lea     edx, [rax-1]
0x180021866  cmp     eax, ebx
0x180021868  cmova   edx, ebx; length
0x18002186b  lea     r9, [rbp+30h+var_58]; string
0x18002186f  lea     r8, [rbp+30h+var_70]; hstringHeader
0x180021873  lea     rcx, aWindowsFoundat_35; "Windows.Foundation.Collections.IVectorV"...
0x18002187a  call    cs:__imp_WindowsCreateStringReference
0x180021880  test    eax, eax
0x180021882  jns     short loc_180021896
0x180021884  xor     r9d, r9d; lpArguments
0x180021887  xor     r8d, r8d; nNumberOfArguments
0x18002188a  lea     edx, [rbx-59h]; dwExceptionFlags
0x18002188d  mov     ecx, eax; dwExceptionCode
0x18002188f  call    cs:__imp_RaiseException
0x180021895  int     3; Trap to Debugger
0x180021896  mov     [rbp+30h+var_38], 0
0x18002189e  mov     ebx, 58h ; 'X'
0x1800218a3  mov     ecx, ebx; unsigned int
0x1800218a5  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800218aa  lea     edx, [rax-1]
0x1800218ad  cmp     eax, ebx
0x1800218af  cmova   edx, ebx; length
0x1800218b2  lea     r9, [rbp+30h+var_38]; string
0x1800218b6  lea     r8, [rbp+30h+var_50]; hstringHeader
0x1800218ba  lea     rcx, aWindowsFoundat_37; "Windows.Foundation.Collections.IIterato"...
0x1800218c1  call    cs:__imp_WindowsCreateStringReference
0x1800218c7  test    eax, eax
0x1800218c9  jns     short loc_1800218DD
0x1800218cb  xor     r9d, r9d; lpArguments
0x1800218ce  xor     r8d, r8d; nNumberOfArguments
0x1800218d1  lea     edx, [rbx-57h]; dwExceptionFlags
0x1800218d4  mov     ecx, eax; dwExceptionCode
0x1800218d6  call    cs:__imp_RaiseException
0x1800218dc  int     3; Trap to Debugger
0x1800218dd  mov     rax, [rbp+30h+string]
0x1800218e1  mov     [rsp+130h+var_100], rax
0x1800218e6  mov     rax, [rbp+30h+var_58]
0x1800218ea  mov     [rsp+130h+var_F8], rax
0x1800218ef  mov     rax, [rbp+30h+var_38]
0x1800218f3  mov     [rsp+130h+var_F0], rax
0x1800218f8  movups  xmm0, xmmword ptr cs:_GUID_def041c5_cd85_4add_959b_e848f800d000.Data1
0x1800218ff  movdqu  [rsp+130h+var_E8], xmm0
0x180021905  movups  xmm1, xmmword ptr cs:_GUID_a0cd89fa_c82c_5db1_b2d1_cd32747e65eb.Data1
0x18002190c  movdqu  [rsp+130h+var_D8], xmm1
0x180021912  movups  xmm0, xmmword ptr cs:_GUID_49244656_5ea6_5680_bf99_87ef7636f6c8.Data1
0x180021919  movdqu  [rsp+130h+var_C8], xmm0
0x18002191f  movups  xmm1, xmmword ptr cs:_GUID_46fe7bc0_d826_574d_985e_9a777db6beca.Data1
0x180021926  movdqu  [rsp+130h+var_B8], xmm1
0x18002192c  movups  xmm0, xmmword ptr cs:_GUID_9808ea27_0bf8_5e8c_95c5_d873cb12c525.Data1
0x180021933  movdqu  [rbp+30h+var_A8], xmm0
0x180021938  mov     [rsp+130h+var_110], 0
0x180021941  lea     rcx, [rsp+130h+var_110]
0x180021946  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002194b  mov     [rbp+30h+var_18], 0
0x180021953  lea     r9, [rbp+30h+var_18]; string
0x180021957  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18002195b  mov     edx, 2Ch ; ','; length
0x180021960  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180021967  call    cs:__imp_WindowsCreateStringReference
0x18002196d  test    eax, eax
0x18002196f  jns     short loc_180021984
0x180021971  xor     r9d, r9d; lpArguments
0x180021974  xor     r8d, r8d; nNumberOfArguments
0x180021977  lea     edx, [r9+1]; dwExceptionFlags
0x18002197b  mov     ecx, eax; dwExceptionCode
0x18002197d  call    cs:__imp_RaiseException
0x180021983  int     3; Trap to Debugger
0x180021984  lea     r8, [rsp+130h+var_110]
0x180021989  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180021990  mov     rcx, [rbp+30h+var_18]
0x180021994  call    cs:__imp_RoGetActivationFactory
0x18002199a  mov     ebx, eax
0x18002199c  test    eax, eax
0x18002199e  jns     short loc_1800219C7
0x1800219a0  mov     rcx, [rsp+130h+var_110]
0x1800219a5  test    rcx, rcx
0x1800219a8  jz      short loc_1800219C0
0x1800219aa  mov     [rsp+130h+var_110], 0
0x1800219b3  mov     rdx, [rcx]
0x1800219b6  mov     rax, [rdx+10h]
0x1800219ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219bf  nop
0x1800219c0  mov     eax, ebx
0x1800219c2  jmp     loc_180021A60
0x1800219c7  mov     [rsp+130h+var_108], 0
0x1800219d0  mov     rbx, [rsp+130h+var_110]
0x1800219d5  lea     rcx, [rsp+130h+var_108]
0x1800219da  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800219df  lea     r8, [rsp+130h+var_108]
0x1800219e4  lea     rdx, [rsp+130h+var_100]
0x1800219e9  mov     rcx, rbx
0x1800219ec  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x1800219f1  mov     ebx, eax
0x1800219f3  test    eax, eax
0x1800219f5  jns     short loc_180021A39
0x1800219f7  mov     rcx, [rsp+130h+var_108]
0x1800219fc  test    rcx, rcx
0x1800219ff  jz      short loc_180021A17
0x180021a01  mov     [rsp+130h+var_108], 0
0x180021a0a  mov     rdx, [rcx]
0x180021a0d  mov     rax, [rdx+10h]
0x180021a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a16  nop
0x180021a17  mov     rcx, [rsp+130h+var_110]
0x180021a1c  test    rcx, rcx
0x180021a1f  jz      short loc_180021A37
0x180021a21  mov     [rsp+130h+var_110], 0
0x180021a2a  mov     rax, [rcx]
0x180021a2d  mov     rax, [rax+10h]
0x180021a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a36  nop
0x180021a37  jmp     short loc_1800219C0
0x180021a39  mov     rax, [rsp+130h+var_108]
0x180021a3e  mov     [rsp+130h+var_108], 0
0x180021a47  mov     [rdi], rax
0x180021a4a  lea     rcx, [rsp+130h+var_108]
0x180021a4f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180021a54  lea     rcx, [rsp+130h+var_110]
0x180021a59  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180021a5e  xor     eax, eax
0x180021a60  mov     rcx, [rbp+30h+var_10]
0x180021a64  xor     rcx, rsp; StackCookie
0x180021a67  call    __security_check_cookie
0x180021a6c  lea     r11, [rsp+130h+var_s0]
0x180021a74  mov     rbx, [r11+10h]
0x180021a78  mov     rdi, [r11+20h]
0x180021a7c  mov     rsp, r11
0x180021a7f  pop     rbp
0x180021a80  retn
```
