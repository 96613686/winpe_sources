# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::StartScreen::JumpListItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::UI::StartScreen::JumpListItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::StartScreen::JumpListItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::StartScreen::JumpListItem *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::UI::StartScreen::JumpListItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::StartScreen::JumpListItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::StartScreen::JumpListItem *>,0> * *)

- ea: `0x18000d780`
- end: `0x18000d9ec`
- name: `??$CreateExternalObjectVector@VJumpListItem@StartScreen@UI@Windows@@V?$AgileVector@PEAVJumpListItem@StartScreen@UI@Windows@@U?$DefaultEqualityPredicate@PEAVJumpListItem@StartScreen@UI@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVJumpListItem@StartScreen@UI@Windows@@@6784@$0A@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVJumpListItem@StartScreen@UI@Windows@@U?$DefaultEqualityPredicate@PEAVJumpListItem@StartScreen@UI@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVJumpListItem@StartScreen@UI@Windows@@@6784@$0A@@1234@@Z`
- size: `620`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800c4f40`

## callees

- `0x18000b7e8`
- `0x18000d780`
- `0x18000e028`
- `0x18013d330`
- `0x1801577f4`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d7e8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d82f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d876`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d91d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d7e8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d82f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d876`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d91d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d7d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d81a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d861`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d907`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d7d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d81a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d861`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d907`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000d934`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000d934`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::StartScreen::JumpListItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::UI::StartScreen::JumpListItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::StartScreen::JumpListItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::StartScreen::JumpListItem *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x4Du);
  v4 = v3 - 1;
  if ( v3 > 0x4D )
    v4 = 77;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.UI.StartScreen.JumpListItem>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v29 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x51u);
  v7 = v6 - 1;
  if ( v6 > 0x51 )
    v7 = 81;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.UI.StartScreen.JumpListItem>",
         v7,
         &v28,
         &v29);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x4Fu);
  v10 = v9 - 1;
  if ( v9 > 0x4F )
    v10 = 79;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.UI.StartScreen.JumpListItem>",
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
  v21 = GUID_7adb6717_8b5d_4820_995b_9b418dbe48b0;
  v22 = GUID_af8f3fb2_f179_5f0a_aa09_28942eedf625;
  v23 = GUID_be418be9_ab72_56b0_b6d3_ec70ef11f663;
  v24 = GUID_130a7274_1afb_5c10_abea_61d81692a496;
  v25 = GUID_f69f5cc4_004f_53eb_89e6_786e460588a4;
  v18 = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v18);
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
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v19);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v16, v20, &v19);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v19);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v18);
    return (unsigned int)ActivationFactory;
  }
  v17 = v19;
  v19 = 0;
  *a2 = v17;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v18);
  return 0;
}

```

## disassembly

```asm
0x18000d780  mov     [rsp-8+arg_0], rbx
0x18000d785  mov     [rsp-8+arg_10], rdi
0x18000d78a  push    rbp
0x18000d78b  lea     rbp, [rsp-30h]
0x18000d790  sub     rsp, 130h
0x18000d797  mov     rax, cs:__security_cookie
0x18000d79e  xor     rax, rsp
0x18000d7a1  mov     [rbp+30h+var_10], rax
0x18000d7a5  mov     rdi, rdx
0x18000d7a8  mov     [rbp+30h+string], 0
0x18000d7b0  mov     ebx, 4Dh ; 'M'
0x18000d7b5  mov     ecx, ebx; unsigned int
0x18000d7b7  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18000d7bc  lea     edx, [rax-1]
0x18000d7bf  cmp     eax, ebx
0x18000d7c1  cmova   edx, ebx; length
0x18000d7c4  lea     r9, [rbp+30h+string]; string
0x18000d7c8  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18000d7cc  lea     rcx, aWindowsFoundat_41; "Windows.Foundation.Collections.IVector`"...
0x18000d7d3  call    cs:__imp_WindowsCreateStringReference
0x18000d7d9  test    eax, eax
0x18000d7db  jns     short loc_18000D7EF
0x18000d7dd  xor     r9d, r9d; lpArguments
0x18000d7e0  xor     r8d, r8d; nNumberOfArguments
0x18000d7e3  lea     edx, [rbx-4Ch]; dwExceptionFlags
0x18000d7e6  mov     ecx, eax; dwExceptionCode
0x18000d7e8  call    cs:__imp_RaiseException
0x18000d7ee  int     3; Trap to Debugger
0x18000d7ef  mov     [rbp+30h+var_58], 0
0x18000d7f7  mov     ebx, 51h ; 'Q'
0x18000d7fc  mov     ecx, ebx; unsigned int
0x18000d7fe  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18000d803  lea     edx, [rax-1]
0x18000d806  cmp     eax, ebx
0x18000d808  cmova   edx, ebx; length
0x18000d80b  lea     r9, [rbp+30h+var_58]; string
0x18000d80f  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18000d813  lea     rcx, aWindowsFoundat_14; "Windows.Foundation.Collections.IVectorV"...
0x18000d81a  call    cs:__imp_WindowsCreateStringReference
0x18000d820  test    eax, eax
0x18000d822  jns     short loc_18000D836
0x18000d824  xor     r9d, r9d; lpArguments
0x18000d827  xor     r8d, r8d; nNumberOfArguments
0x18000d82a  lea     edx, [rbx-50h]; dwExceptionFlags
0x18000d82d  mov     ecx, eax; dwExceptionCode
0x18000d82f  call    cs:__imp_RaiseException
0x18000d835  int     3; Trap to Debugger
0x18000d836  mov     [rbp+30h+var_38], 0
0x18000d83e  mov     ebx, 4Fh ; 'O'
0x18000d843  mov     ecx, ebx; unsigned int
0x18000d845  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18000d84a  lea     edx, [rax-1]
0x18000d84d  cmp     eax, ebx
0x18000d84f  cmova   edx, ebx; length
0x18000d852  lea     r9, [rbp+30h+var_38]; string
0x18000d856  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18000d85a  lea     rcx, aWindowsFoundat_25; "Windows.Foundation.Collections.IIterato"...
0x18000d861  call    cs:__imp_WindowsCreateStringReference
0x18000d867  test    eax, eax
0x18000d869  jns     short loc_18000D87D
0x18000d86b  xor     r9d, r9d; lpArguments
0x18000d86e  xor     r8d, r8d; nNumberOfArguments
0x18000d871  lea     edx, [rbx-4Eh]; dwExceptionFlags
0x18000d874  mov     ecx, eax; dwExceptionCode
0x18000d876  call    cs:__imp_RaiseException
0x18000d87c  int     3; Trap to Debugger
0x18000d87d  mov     rax, [rbp+30h+string]
0x18000d881  mov     [rsp+130h+var_100], rax
0x18000d886  mov     rax, [rbp+30h+var_58]
0x18000d88a  mov     [rsp+130h+var_F8], rax
0x18000d88f  mov     rax, [rbp+30h+var_38]
0x18000d893  mov     [rsp+130h+var_F0], rax
0x18000d898  movups  xmm0, xmmword ptr cs:_GUID_7adb6717_8b5d_4820_995b_9b418dbe48b0.Data1
0x18000d89f  movdqu  [rsp+130h+var_E8], xmm0
0x18000d8a5  movups  xmm1, xmmword ptr cs:_GUID_af8f3fb2_f179_5f0a_aa09_28942eedf625.Data1
0x18000d8ac  movdqu  [rsp+130h+var_D8], xmm1
0x18000d8b2  movups  xmm0, xmmword ptr cs:_GUID_be418be9_ab72_56b0_b6d3_ec70ef11f663.Data1
0x18000d8b9  movdqu  [rsp+130h+var_C8], xmm0
0x18000d8bf  movups  xmm1, xmmword ptr cs:_GUID_130a7274_1afb_5c10_abea_61d81692a496.Data1
0x18000d8c6  movdqu  [rsp+130h+var_B8], xmm1
0x18000d8cc  movups  xmm0, xmmword ptr cs:_GUID_f69f5cc4_004f_53eb_89e6_786e460588a4.Data1
0x18000d8d3  movdqu  [rbp+30h+var_A8], xmm0
0x18000d8d8  mov     [rsp+130h+var_110], 0
0x18000d8e1  lea     rcx, [rsp+130h+var_110]
0x18000d8e6  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18000d8eb  mov     [rbp+30h+var_18], 0
0x18000d8f3  lea     r9, [rbp+30h+var_18]; string
0x18000d8f7  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18000d8fb  mov     edx, 2Ch ; ','; length
0x18000d900  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18000d907  call    cs:__imp_WindowsCreateStringReference
0x18000d90d  test    eax, eax
0x18000d90f  jns     short loc_18000D924
0x18000d911  xor     r9d, r9d; lpArguments
0x18000d914  xor     r8d, r8d; nNumberOfArguments
0x18000d917  lea     edx, [r9+1]; dwExceptionFlags
0x18000d91b  mov     ecx, eax; dwExceptionCode
0x18000d91d  call    cs:__imp_RaiseException
0x18000d923  int     3; Trap to Debugger
0x18000d924  lea     r8, [rsp+130h+var_110]
0x18000d929  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18000d930  mov     rcx, [rbp+30h+var_18]
0x18000d934  call    cs:__imp_RoGetActivationFactory
0x18000d93a  mov     ebx, eax
0x18000d93c  test    eax, eax
0x18000d93e  jns     short loc_18000D963
0x18000d940  mov     rcx, [rsp+130h+var_110]
0x18000d945  test    rcx, rcx
0x18000d948  jz      short loc_18000D95F
0x18000d94a  mov     [rsp+130h+var_110], 0
0x18000d953  mov     rdx, [rcx]
0x18000d956  mov     rax, [rdx+10h]
0x18000d95a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d95f  mov     eax, ebx
0x18000d961  jmp     short loc_18000D9CB
0x18000d963  mov     [rsp+130h+var_108], 0
0x18000d96c  mov     rbx, [rsp+130h+var_110]
0x18000d971  lea     rcx, [rsp+130h+var_108]
0x18000d976  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18000d97b  lea     r8, [rsp+130h+var_108]
0x18000d980  lea     rdx, [rsp+130h+var_100]
0x18000d985  mov     rcx, rbx
0x18000d988  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18000d98d  mov     ebx, eax
0x18000d98f  lea     rcx, [rsp+130h+var_108]
0x18000d994  test    eax, eax
0x18000d996  jns     short loc_18000D9A9
0x18000d998  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18000d99d  lea     rcx, [rsp+130h+var_110]
0x18000d9a2  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18000d9a7  jmp     short loc_18000D95F
0x18000d9a9  mov     rax, [rsp+130h+var_108]
0x18000d9ae  mov     [rsp+130h+var_108], 0
0x18000d9b7  mov     [rdi], rax
0x18000d9ba  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18000d9bf  lea     rcx, [rsp+130h+var_110]
0x18000d9c4  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18000d9c9  xor     eax, eax
0x18000d9cb  mov     rcx, [rbp+30h+var_10]
0x18000d9cf  xor     rcx, rsp; StackCookie
0x18000d9d2  call    __security_check_cookie
0x18000d9d7  lea     r11, [rsp+130h+var_s0]
0x18000d9df  mov     rbx, [r11+10h]
0x18000d9e3  mov     rdi, [r11+20h]
0x18000d9e7  mov     rsp, r11
0x18000d9ea  pop     rbp
0x18000d9eb  retn
```
