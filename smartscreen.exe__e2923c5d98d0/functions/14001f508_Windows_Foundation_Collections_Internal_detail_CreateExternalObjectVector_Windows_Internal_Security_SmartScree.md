# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::Security::SmartScreen::ButtonInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Security::SmartScreen::ButtonInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Security::SmartScreen::ButtonInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Security::SmartScreen::ButtonInfo *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Security::SmartScreen::ButtonInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Security::SmartScreen::ButtonInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Security::SmartScreen::ButtonInfo *>,0> * *)

- ea: `0x14001f508`
- end: `0x14001f69a`
- name: `??$CreateExternalObjectVector@VButtonInfo@SmartScreen@Security@Internal@Windows@@V?$AgileVector@PEAVButtonInfo@SmartScreen@Security@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVButtonInfo@SmartScreen@Security@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVButtonInfo@SmartScreen@Security@Internal@Windows@@@4785@$0A@@4Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVButtonInfo@SmartScreen@Security@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVButtonInfo@SmartScreen@Security@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVButtonInfo@SmartScreen@Security@Internal@Windows@@@4785@$0A@@1234@@Z`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14001f310`

## callees

- `0x1400111a8`
- `0x140012a84`
- `0x14001f48c`
- `0x14001f508`
- `0x140025aa0`
- `0x14003bbb8`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14001f61c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14001f61c`

## string_xrefs

- `0x14001f564`: `Windows.Foundation.Collections.IIterator`1<Windows.Internal.Security.SmartScreen.ButtonInfo>`
- `0x14001f54a`: `Windows.Foundation.Collections.IVectorView`1<Windows.Internal.Security.SmartScreen.ButtonInfo>`
- `0x14001f530`: `Windows.Foundation.Collections.IVector`1<Windows.Internal.Security.SmartScreen.ButtonInfo>`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::Security::SmartScreen::ButtonInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Security::SmartScreen::ButtonInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Security::SmartScreen::ButtonInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Security::SmartScreen::ButtonInfo *>,0>>(
        __int64 a1,
        _QWORD *a2)
{
  int ActivationFactory; // ebx
  __int64 v4; // rbx
  __int64 v5; // rax
  const WCHAR *v7; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v9; // [rsp+40h] [rbp-C0h]
  _QWORD v10[3]; // [rsp+50h] [rbp-B0h] BYREF
  GUID v11; // [rsp+68h] [rbp-98h]
  GUID v12; // [rsp+78h] [rbp-88h]
  GUID v13; // [rsp+88h] [rbp-78h]
  GUID v14; // [rsp+98h] [rbp-68h]
  GUID v15; // [rsp+A8h] [rbp-58h]
  __int64 v16; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v17; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING_HEADER v18; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v19; // [rsp+E8h] [rbp-18h]
  HSTRING_HEADER v20; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v21; // [rsp+108h] [rbp+8h]
  HSTRING_HEADER v22; // [rsp+110h] [rbp+10h] BYREF
  __int64 v23; // [rsp+128h] [rbp+28h]

  v7 = L"Windows.Foundation.Collections.IVector`1<Windows.Internal.Security.SmartScreen.ButtonInfo>";
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v18, &v7);
  v7 = L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.Security.SmartScreen.ButtonInfo>";
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v20, &v7);
  v7 = L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.Security.SmartScreen.ButtonInfo>";
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v22, &v7);
  v10[0] = v19;
  v10[1] = v21;
  v10[2] = v23;
  v11 = GUID_9ad9b845_b683_493e_8d39_45a56d54617d;
  v12 = GUID_50a07d41_5535_5d66_b3c2_bd900af35b4d;
  v13 = GUID_e9444d66_3ff9_5410_8984_f9063f825683;
  v14 = GUID_69c26f3c_53aa_56cc_818f_4be79004cd02;
  v15 = GUID_60f00258_24f8_5460_bb2d_853a614a50ec;
  v17 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v17);
  v9 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Foundation.Collections.Detail.Vector",
    0x2Du,
    0x2Cu);
  ActivationFactory = RoGetActivationFactory(v9, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v17);
  if ( ActivationFactory >= 0 )
  {
    v16 = 0;
    v4 = v17;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v16);
    ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v4, v10, &v16);
    if ( ActivationFactory >= 0 )
    {
      v5 = v16;
      v16 = 0;
      *a2 = v5;
      ActivationFactory = 0;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v16);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v17);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x14001f508  mov     [rsp-8+arg_0], rbx
0x14001f50d  mov     [rsp-8+arg_10], rdi
0x14001f512  push    rbp
0x14001f513  lea     rbp, [rsp-40h]
0x14001f518  sub     rsp, 140h
0x14001f51f  mov     rax, cs:__security_cookie
0x14001f526  xor     rax, rsp
0x14001f529  mov     [rbp+40h+var_10], rax
0x14001f52d  mov     rdi, rdx
0x14001f530  lea     rax, aWindowsFoundat_4; "Windows.Foundation.Collections.IVector`"...
0x14001f537  mov     [rsp+140h+var_120], rax
0x14001f53c  lea     rdx, [rsp+140h+var_120]
0x14001f541  lea     rcx, [rbp+40h+var_70]
0x14001f545  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14001f54a  lea     rax, aWindowsFoundat_1; "Windows.Foundation.Collections.IVectorV"...
0x14001f551  mov     [rsp+140h+var_120], rax
0x14001f556  lea     rdx, [rsp+140h+var_120]
0x14001f55b  lea     rcx, [rbp+40h+var_50]
0x14001f55f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14001f564  lea     rax, aWindowsFoundat_5; "Windows.Foundation.Collections.IIterato"...
0x14001f56b  mov     [rsp+140h+var_120], rax
0x14001f570  lea     rdx, [rsp+140h+var_120]
0x14001f575  lea     rcx, [rbp+40h+var_30]
0x14001f579  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14001f57e  mov     rax, [rbp+40h+var_58]
0x14001f582  mov     [rsp+140h+var_F0], rax
0x14001f587  mov     rax, [rbp+40h+var_38]
0x14001f58b  mov     [rsp+140h+var_E8], rax
0x14001f590  mov     rax, [rbp+40h+var_18]
0x14001f594  mov     [rsp+140h+var_E0], rax
0x14001f599  movups  xmm0, xmmword ptr cs:_GUID_9ad9b845_b683_493e_8d39_45a56d54617d.Data1
0x14001f5a0  movdqu  [rsp+140h+var_D8], xmm0
0x14001f5a6  movups  xmm1, xmmword ptr cs:_GUID_50a07d41_5535_5d66_b3c2_bd900af35b4d.Data1
0x14001f5ad  movdqu  [rsp+140h+var_C8], xmm1
0x14001f5b3  movups  xmm0, xmmword ptr cs:_GUID_e9444d66_3ff9_5410_8984_f9063f825683.Data1
0x14001f5ba  movdqu  [rbp+40h+var_B8], xmm0
0x14001f5bf  movups  xmm1, xmmword ptr cs:_GUID_69c26f3c_53aa_56cc_818f_4be79004cd02.Data1
0x14001f5c6  movdqu  [rbp+40h+var_A8], xmm1
0x14001f5cb  movups  xmm0, xmmword ptr cs:_GUID_60f00258_24f8_5460_bb2d_853a614a50ec.Data1
0x14001f5d2  movdqu  [rbp+40h+var_98], xmm0
0x14001f5d7  mov     [rbp+40h+var_78], 0
0x14001f5df  lea     rcx, [rbp+40h+var_78]
0x14001f5e3  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x14001f5e8  mov     [rsp+140h+var_100], 0
0x14001f5f1  mov     r9d, 2Ch ; ','; unsigned int
0x14001f5f7  lea     r8d, [r9+1]; unsigned int
0x14001f5fb  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x14001f602  lea     rcx, [rsp+140h+hstringHeader]; hstringHeader
0x14001f607  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14001f60c  lea     r8, [rbp+40h+var_78]
0x14001f610  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x14001f617  mov     rcx, [rsp+140h+var_100]
0x14001f61c  call    cs:__imp_RoGetActivationFactory
0x14001f622  mov     ebx, eax
0x14001f624  test    eax, eax
0x14001f626  js      short loc_14001F66E
0x14001f628  mov     [rbp+40h+var_80], 0
0x14001f630  mov     rbx, [rbp+40h+var_78]
0x14001f634  lea     rcx, [rbp+40h+var_80]
0x14001f638  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x14001f63d  lea     r8, [rbp+40h+var_80]
0x14001f641  lea     rdx, [rsp+140h+var_F0]
0x14001f646  mov     rcx, rbx
0x14001f649  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x14001f64e  mov     ebx, eax
0x14001f650  test    eax, eax
0x14001f652  js      short loc_14001F665
0x14001f654  mov     rax, [rbp+40h+var_80]
0x14001f658  mov     [rbp+40h+var_80], 0
0x14001f660  mov     [rdi], rax
0x14001f663  xor     ebx, ebx
0x14001f665  lea     rcx, [rbp+40h+var_80]
0x14001f669  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x14001f66e  lea     rcx, [rbp+40h+var_78]
0x14001f672  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x14001f677  mov     eax, ebx
0x14001f679  mov     rcx, [rbp+40h+var_10]
0x14001f67d  xor     rcx, rsp; StackCookie
0x14001f680  call    __security_check_cookie
0x14001f685  lea     r11, [rsp+140h+var_s0]
0x14001f68d  mov     rbx, [r11+10h]
0x14001f691  mov     rdi, [r11+20h]
0x14001f695  mov     rsp, r11
0x14001f698  pop     rbp
0x14001f699  retn
```
