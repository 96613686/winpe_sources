# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::ViewManagement::Core::CoreInputViewOcclusion,Windows::Foundation::Collections::Internal::Vector<Windows::UI::ViewManagement::Core::CoreInputViewOcclusion *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::ViewManagement::Core::CoreInputViewOcclusion *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::ViewManagement::Core::CoreInputViewOcclusion *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::ViewManagement::Core::CoreInputViewOcclusion *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::UI::ViewManagement::Core::CoreInputViewOcclusion *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::ViewManagement::Core::CoreInputViewOcclusion *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::ViewManagement::Core::CoreInputViewOcclusion *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::ViewManagement::Core::CoreInputViewOcclusion *>> * *)

- ea: `0x180075e98`
- end: `0x180076157`
- name: `??$CreateExternalObjectVector@VCoreInputViewOcclusion@Core@ViewManagement@UI@Windows@@V?$Vector@PEAVCoreInputViewOcclusion@Core@ViewManagement@UI@Windows@@U?$DefaultEqualityPredicate@PEAVCoreInputViewOcclusion@Core@ViewManagement@UI@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCoreInputViewOcclusion@Core@ViewManagement@UI@Windows@@@7895@U?$DefaultVectorOptions@PEAVCoreInputViewOcclusion@Core@ViewManagement@UI@Windows@@@7895@@Internal@Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVCoreInputViewOcclusion@Core@ViewManagement@UI@Windows@@U?$DefaultEqualityPredicate@PEAVCoreInputViewOcclusion@Core@ViewManagement@UI@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCoreInputViewOcclusion@Core@ViewManagement@UI@Windows@@@7895@U?$DefaultVectorOptions@PEAVCoreInputViewOcclusion@Core@ViewManagement@UI@Windows@@@7895@@1234@@Z`
- size: `703`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180075c04`

## callees

- `0x1800134f8`
- `0x18005d940`
- `0x180075e98`
- `0x180356360`
- `0x1804c4500`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180076117`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007612a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007613d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180076150`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180076117`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007612a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007613d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180076150`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180075eeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180075f24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180075f5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180075ff3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180075eeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180075f24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180075f5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180075ff3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180076011`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180076011`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::ViewManagement::Core::CoreInputViewOcclusion,Windows::Foundation::Collections::Internal::Vector<Windows::UI::ViewManagement::Core::CoreInputViewOcclusion *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::ViewManagement::Core::CoreInputViewOcclusion *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::ViewManagement::Core::CoreInputViewOcclusion *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::ViewManagement::Core::CoreInputViewOcclusion *>>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Fu);
  v4 = v3 - 1;
  if ( v3 > 0x5F )
    v4 = 95;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.UI.ViewManagement.Core.CoreInputViewOcclusion>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x63u);
  v7 = v6 - 1;
  if ( v6 > 0x63 )
    v7 = 99;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.UI.ViewManagement.Core.CoreInputViewOcclusion>",
         v7,
         &v31,
         &v32);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v34 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x61u);
  v10 = v9 - 1;
  if ( v9 > 0x61 )
    v10 = 97;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.UI.ViewManagement.Core.CoreInputViewOcclusion>",
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
  v24 = GUID_cc36ce06_3865_4177_b5f5_8b65e0b9ce84;
  v25 = GUID_496abefc_24af_5e94_b857_b0f24db23ef6;
  v26 = GUID_e0963578_a246_5680_86d1_27519423e212;
  v27 = GUID_0a11958b_63da_5566_913a_180550dad26a;
  v28 = GUID_5bb57354_4f40_5ef3_a5d1_6a6049f905a1;
  v21 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v36 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v35, &v36);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    JUMPOUT(0x180076156LL);
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
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}(v14, v23, &v22);
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
0x180075e98  mov     [rsp-8+arg_0], rbx
0x180075e9d  mov     [rsp-8+arg_10], rdi
0x180075ea2  push    rbp
0x180075ea3  lea     rbp, [rsp-30h]
0x180075ea8  sub     rsp, 130h
0x180075eaf  mov     rax, cs:__security_cookie
0x180075eb6  xor     rax, rsp
0x180075eb9  mov     [rbp+30h+var_10], rax
0x180075ebd  mov     rdi, rdx
0x180075ec0  mov     [rbp+30h+string], 0
0x180075ec8  mov     ebx, 5Fh ; '_'
0x180075ecd  mov     ecx, ebx; unsigned int
0x180075ecf  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180075ed4  lea     edx, [rax-1]
0x180075ed7  cmp     eax, ebx
0x180075ed9  cmova   edx, ebx; length
0x180075edc  lea     r9, [rbp+30h+string]; string
0x180075ee0  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180075ee4  lea     rcx, aWindowsFoundat_43; "Windows.Foundation.Collections.IVector`"...
0x180075eeb  call    cs:__imp_WindowsCreateStringReference
0x180075ef1  test    eax, eax
0x180075ef3  js      loc_18007610B
0x180075ef9  mov     [rbp+30h+var_58], 0
0x180075f01  mov     ebx, 63h ; 'c'
0x180075f06  mov     ecx, ebx; unsigned int
0x180075f08  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180075f0d  lea     edx, [rax-1]
0x180075f10  cmp     eax, ebx
0x180075f12  cmova   edx, ebx; length
0x180075f15  lea     r9, [rbp+30h+var_58]; string
0x180075f19  lea     r8, [rbp+30h+var_70]; hstringHeader
0x180075f1d  lea     rcx, aWindowsFoundat_34; "Windows.Foundation.Collections.IVectorV"...
0x180075f24  call    cs:__imp_WindowsCreateStringReference
0x180075f2a  test    eax, eax
0x180075f2c  js      loc_18007611E
0x180075f32  mov     [rbp+30h+var_38], 0
0x180075f3a  mov     ebx, 61h ; 'a'
0x180075f3f  mov     ecx, ebx; unsigned int
0x180075f41  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180075f46  lea     edx, [rax-1]
0x180075f49  cmp     eax, ebx
0x180075f4b  cmova   edx, ebx; length
0x180075f4e  lea     r9, [rbp+30h+var_38]; string
0x180075f52  lea     r8, [rbp+30h+var_50]; hstringHeader
0x180075f56  lea     rcx, aWindowsFoundat_29; "Windows.Foundation.Collections.IIterato"...
0x180075f5d  call    cs:__imp_WindowsCreateStringReference
0x180075f63  test    eax, eax
0x180075f65  js      loc_180076131
0x180075f6b  mov     rax, [rbp+30h+string]
0x180075f6f  mov     [rsp+130h+var_100], rax
0x180075f74  mov     rax, [rbp+30h+var_58]
0x180075f78  mov     [rsp+130h+var_F8], rax
0x180075f7d  mov     rax, [rbp+30h+var_38]
0x180075f81  mov     [rsp+130h+var_F0], rax
0x180075f86  movups  xmm0, xmmword ptr cs:_GUID_cc36ce06_3865_4177_b5f5_8b65e0b9ce84.Data1
0x180075f8d  movdqu  [rsp+130h+var_E8], xmm0
0x180075f93  movups  xmm1, xmmword ptr cs:_GUID_496abefc_24af_5e94_b857_b0f24db23ef6.Data1
0x180075f9a  movdqu  [rsp+130h+var_D8], xmm1
0x180075fa0  movups  xmm0, xmmword ptr cs:_GUID_e0963578_a246_5680_86d1_27519423e212.Data1
0x180075fa7  movdqu  [rsp+130h+var_C8], xmm0
0x180075fad  movups  xmm1, xmmword ptr cs:_GUID_0a11958b_63da_5566_913a_180550dad26a.Data1
0x180075fb4  movdqu  [rsp+130h+var_B8], xmm1
0x180075fba  movups  xmm0, xmmword ptr cs:_GUID_5bb57354_4f40_5ef3_a5d1_6a6049f905a1.Data1
0x180075fc1  movdqu  [rbp+30h+var_A8], xmm0
0x180075fc6  mov     [rsp+130h+var_110], 0
0x180075fcf  lea     rcx, [rsp+130h+var_110]
0x180075fd4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180075fd9  mov     [rbp+30h+var_18], 0
0x180075fe1  lea     r9, [rbp+30h+var_18]; string
0x180075fe5  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180075fe9  lea     edx, [rbx-35h]; length
0x180075fec  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180075ff3  call    cs:__imp_WindowsCreateStringReference
0x180075ff9  test    eax, eax
0x180075ffb  js      loc_180076144
0x180076001  lea     r8, [rsp+130h+var_110]
0x180076006  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18007600d  mov     rcx, [rbp+30h+var_18]
0x180076011  call    cs:__imp_RoGetActivationFactory
0x180076017  mov     ebx, eax
0x180076019  test    eax, eax
0x18007601b  js      loc_1800760E9
0x180076021  mov     [rsp+130h+var_108], 0
0x18007602a  mov     rbx, [rsp+130h+var_110]
0x18007602f  lea     rcx, [rsp+130h+var_108]
0x180076034  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180076039  lea     r8, [rsp+130h+var_108]
0x18007603e  lea     rdx, [rsp+130h+var_100]
0x180076043  mov     rcx, rbx
0x180076046  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x18007604b  mov     ebx, eax
0x18007604d  test    eax, eax
0x18007604f  jns     short loc_1800760B4
0x180076051  mov     rcx, [rsp+130h+var_108]
0x180076056  test    rcx, rcx
0x180076059  jz      short loc_180076071
0x18007605b  mov     [rsp+130h+var_108], 0
0x180076064  mov     rdx, [rcx]
0x180076067  mov     rax, [rdx+10h]
0x18007606b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076070  nop
0x180076071  mov     rcx, [rsp+130h+var_110]
0x180076076  test    rcx, rcx
0x180076079  jz      short loc_180076091
0x18007607b  mov     [rsp+130h+var_110], 0
0x180076084  mov     rax, [rcx]
0x180076087  mov     rax, [rax+10h]
0x18007608b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076090  nop
0x180076091  mov     eax, ebx
0x180076093  mov     rcx, [rbp+30h+var_10]
0x180076097  xor     rcx, rsp; StackCookie
0x18007609a  call    __security_check_cookie
0x18007609f  lea     r11, [rsp+130h+var_s0]
0x1800760a7  mov     rbx, [r11+10h]
0x1800760ab  mov     rdi, [r11+20h]
0x1800760af  mov     rsp, r11
0x1800760b2  pop     rbp
0x1800760b3  retn
0x1800760b4  mov     rax, [rsp+130h+var_108]
0x1800760b9  mov     [rsp+130h+var_108], 0
0x1800760c2  mov     [rdi], rax
0x1800760c5  mov     rcx, [rsp+130h+var_110]
0x1800760ca  test    rcx, rcx
0x1800760cd  jz      short loc_1800760E5
0x1800760cf  mov     [rsp+130h+var_110], 0
0x1800760d8  mov     rax, [rcx]
0x1800760db  mov     rax, [rax+10h]
0x1800760df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800760e4  nop
0x1800760e5  xor     eax, eax
0x1800760e7  jmp     short loc_180076093
0x1800760e9  mov     rcx, [rsp+130h+var_110]
0x1800760ee  test    rcx, rcx
0x1800760f1  jz      short loc_180076109
0x1800760f3  mov     [rsp+130h+var_110], 0
0x1800760fc  mov     rdx, [rcx]
0x1800760ff  mov     rax, [rdx+10h]
0x180076103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076108  nop
0x180076109  jmp     short loc_180076091
0x18007610b  xor     r9d, r9d; lpArguments
0x18007610e  xor     r8d, r8d; nNumberOfArguments
0x180076111  lea     edx, [r9+1]; dwExceptionFlags
0x180076115  mov     ecx, eax; dwExceptionCode
0x180076117  call    cs:__imp_RaiseException
0x18007611d  int     3; Trap to Debugger
0x18007611e  xor     r9d, r9d; lpArguments
0x180076121  xor     r8d, r8d; nNumberOfArguments
0x180076124  lea     edx, [r9+1]; dwExceptionFlags
0x180076128  mov     ecx, eax; dwExceptionCode
0x18007612a  call    cs:__imp_RaiseException
0x180076130  int     3; Trap to Debugger
0x180076131  xor     r9d, r9d; lpArguments
0x180076134  xor     r8d, r8d; nNumberOfArguments
0x180076137  lea     edx, [r9+1]; dwExceptionFlags
0x18007613b  mov     ecx, eax; dwExceptionCode
0x18007613d  call    cs:__imp_RaiseException
0x180076143  int     3; Trap to Debugger
0x180076144  xor     r9d, r9d; lpArguments
0x180076147  xor     r8d, r8d; nNumberOfArguments
0x18007614a  lea     edx, [r9+1]; dwExceptionFlags
0x18007614e  mov     ecx, eax; dwExceptionCode
0x180076150  call    cs:__imp_RaiseException
```
