# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest,Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>> * *)

- ea: `0x18002f094`
- end: `0x18002f22f`
- name: `??$CreateExternalObjectVector@VOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@1234@@Z`
- size: `411`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180030dc0`

## callees

- `0x180003110`
- `0x180005f50`
- `0x180006b9c`
- `0x18000b0bc`
- `0x18002f094`
- `0x18002fff0`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002f1a9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002f1a9`

## string_xrefs

- `0x18002f0f0`: `Windows.Foundation.Collections.IIterator`1<Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest>`
- `0x18002f0d6`: `Windows.Foundation.Collections.IVectorView`1<Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest>`
- `0x18002f0bc`: `Windows.Foundation.Collections.IVector`1<Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest>`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest,Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>>(
        __int64 a1,
        _QWORD *a2)
{
  int ActivationFactory; // ebx
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v7; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v8; // [rsp+28h] [rbp-D8h] BYREF
  const WCHAR *v9[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v10[3]; // [rsp+40h] [rbp-C0h] BYREF
  GUID v11; // [rsp+58h] [rbp-A8h]
  GUID v12; // [rsp+68h] [rbp-98h]
  GUID v13; // [rsp+78h] [rbp-88h]
  GUID v14; // [rsp+88h] [rbp-78h]
  GUID v15; // [rsp+98h] [rbp-68h]
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v17; // [rsp+C8h] [rbp-38h]
  HSTRING_HEADER v18; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v19; // [rsp+E8h] [rbp-18h]
  HSTRING_HEADER v20; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v21; // [rsp+108h] [rbp+8h]
  HSTRING_HEADER v22; // [rsp+110h] [rbp+10h] BYREF
  __int64 v23; // [rsp+128h] [rbp+28h]

  v9[0] = L"Windows.Foundation.Collections.IVector`1<Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest>";
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v18, v9);
  v9[0] = L"Windows.Foundation.Collections.IVectorView`1<Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest>";
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v20, v9);
  v9[0] = L"Windows.Foundation.Collections.IIterator`1<Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest>";
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v22, v9);
  v10[0] = v19;
  v10[1] = v21;
  v10[2] = v23;
  v11 = GUID_297445d3_fb63_4135_8909_4e354c061466;
  v12 = GUID_f6ed9226_b260_5f49_9b84_e89e43cbabc6;
  v13 = GUID_1a7c6c05_3fef_5eeb_aaff_625ee3ebc07c;
  v14 = GUID_cb72d686_9516_520d_a274_fa4cd1762cb2;
  v15 = GUID_b6a5c8e4_6e3c_5c37_92cf_cf9f1c383335;
  v8 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
  v17 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Foundation.Collections.Detail.Vector",
    0x2Du,
    0x2Cu);
  ActivationFactory = RoGetActivationFactory(v17, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v8);
  if ( ActivationFactory >= 0 )
  {
    v7 = 0;
    v4 = v8;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
    ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}(v4, v10, &v7);
    if ( ActivationFactory >= 0 )
    {
      v5 = v7;
      v7 = 0;
      *a2 = v5;
      ActivationFactory = 0;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18002f094  mov     [rsp-8+arg_0], rbx
0x18002f099  mov     [rsp-8+arg_10], rdi
0x18002f09e  push    rbp
0x18002f09f  lea     rbp, [rsp-40h]
0x18002f0a4  sub     rsp, 140h
0x18002f0ab  mov     rax, cs:__security_cookie
0x18002f0b2  xor     rax, rsp
0x18002f0b5  mov     [rbp+40h+var_10], rax
0x18002f0b9  mov     rdi, rdx
0x18002f0bc  lea     rax, aWindowsFoundat_0; "Windows.Foundation.Collections.IVector`"...
0x18002f0c3  mov     [rsp+140h+var_110], rax
0x18002f0c8  lea     rdx, [rsp+140h+var_110]
0x18002f0cd  lea     rcx, [rbp+40h+var_70]
0x18002f0d1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002f0d6  lea     rax, aWindowsFoundat_1; "Windows.Foundation.Collections.IVectorV"...
0x18002f0dd  mov     [rsp+140h+var_110], rax
0x18002f0e2  lea     rdx, [rsp+140h+var_110]
0x18002f0e7  lea     rcx, [rbp+40h+var_50]
0x18002f0eb  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002f0f0  lea     rax, aWindowsFoundat; "Windows.Foundation.Collections.IIterato"...
0x18002f0f7  mov     [rsp+140h+var_110], rax
0x18002f0fc  lea     rdx, [rsp+140h+var_110]
0x18002f101  lea     rcx, [rbp+40h+var_30]
0x18002f105  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002f10a  mov     rax, [rbp+40h+var_58]
0x18002f10e  mov     [rsp+140h+var_100], rax
0x18002f113  mov     rax, [rbp+40h+var_38]
0x18002f117  mov     [rsp+140h+var_F8], rax
0x18002f11c  mov     rax, [rbp+40h+var_18]
0x18002f120  mov     [rsp+140h+var_F0], rax
0x18002f125  movups  xmm0, xmmword ptr cs:_GUID_297445d3_fb63_4135_8909_4e354c061466.Data1
0x18002f12c  movdqu  [rsp+140h+var_E8], xmm0
0x18002f132  movups  xmm1, xmmword ptr cs:_GUID_f6ed9226_b260_5f49_9b84_e89e43cbabc6.Data1
0x18002f139  movdqu  [rsp+140h+var_D8], xmm1
0x18002f13f  movups  xmm0, xmmword ptr cs:_GUID_1a7c6c05_3fef_5eeb_aaff_625ee3ebc07c.Data1
0x18002f146  movdqu  [rsp+140h+var_C8], xmm0
0x18002f14c  movups  xmm1, xmmword ptr cs:_GUID_cb72d686_9516_520d_a274_fa4cd1762cb2.Data1
0x18002f153  movdqu  [rbp+40h+var_B8], xmm1
0x18002f158  movups  xmm0, xmmword ptr cs:_GUID_b6a5c8e4_6e3c_5c37_92cf_cf9f1c383335.Data1
0x18002f15f  movdqu  [rbp+40h+var_A8], xmm0
0x18002f164  mov     [rsp+140h+var_118], 0
0x18002f16d  lea     rcx, [rsp+140h+var_118]
0x18002f172  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f177  mov     [rbp+40h+var_78], 0
0x18002f17f  mov     r9d, 2Ch ; ','; unsigned int
0x18002f185  lea     r8d, [r9+1]; unsigned int
0x18002f189  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18002f190  lea     rcx, [rbp+40h+hstringHeader]; hstringHeader
0x18002f194  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002f199  lea     r8, [rsp+140h+var_118]
0x18002f19e  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18002f1a5  mov     rcx, [rbp+40h+var_78]
0x18002f1a9  call    cs:__imp_RoGetActivationFactory
0x18002f1af  mov     ebx, eax
0x18002f1b1  test    eax, eax
0x18002f1b3  js      short loc_18002F202
0x18002f1b5  mov     [rsp+140h+var_120], 0
0x18002f1be  mov     rbx, [rsp+140h+var_118]
0x18002f1c3  lea     rcx, [rsp+140h+var_120]
0x18002f1c8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f1cd  lea     r8, [rsp+140h+var_120]
0x18002f1d2  lea     rdx, [rsp+140h+var_100]
0x18002f1d7  mov     rcx, rbx
0x18002f1da  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x18002f1df  mov     ebx, eax
0x18002f1e1  test    eax, eax
0x18002f1e3  js      short loc_18002F1F8
0x18002f1e5  mov     rax, [rsp+140h+var_120]
0x18002f1ea  mov     [rsp+140h+var_120], 0
0x18002f1f3  mov     [rdi], rax
0x18002f1f6  xor     ebx, ebx
0x18002f1f8  lea     rcx, [rsp+140h+var_120]
0x18002f1fd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f202  lea     rcx, [rsp+140h+var_118]
0x18002f207  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f20c  mov     eax, ebx
0x18002f20e  mov     rcx, [rbp+40h+var_10]
0x18002f212  xor     rcx, rsp; StackCookie
0x18002f215  call    __security_check_cookie
0x18002f21a  lea     r11, [rsp+140h+var_s0]
0x18002f222  mov     rbx, [r11+10h]
0x18002f226  mov     rdi, [r11+20h]
0x18002f22a  mov     rsp, r11
0x18002f22d  pop     rbp
0x18002f22e  retn
```
