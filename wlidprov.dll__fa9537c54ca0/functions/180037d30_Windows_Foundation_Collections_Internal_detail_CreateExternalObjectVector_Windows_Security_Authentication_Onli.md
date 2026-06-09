# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest,Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>> * *)

- ea: `0x180037d30`
- end: `0x180037ecb`
- name: `??$CreateExternalObjectVector@VOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@1234@@Z`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180038e80`

## callees

- `0x18001a0d0`
- `0x18002717c`
- `0x180029b38`
- `0x18002ae68`
- `0x180037d30`
- `0x180037f98`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180037e45`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180037e45`

## string_xrefs

- `0x180037d8c`: `Windows.Foundation.Collections.IIterator`1<Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest>`
- `0x180037d72`: `Windows.Foundation.Collections.IVectorView`1<Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest>`
- `0x180037d58`: `Windows.Foundation.Collections.IVector`1<Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest>`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest,Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>>(
        __int64 a1,
        _QWORD *a2)
{
  int ActivationFactory; // ebx
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v7; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v8; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v9[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v10[3]; // [rsp+40h] [rbp-C0h] BYREF
  GUID v11; // [rsp+58h] [rbp-A8h]
  GUID v12; // [rsp+68h] [rbp-98h]
  GUID v13; // [rsp+78h] [rbp-88h]
  GUID v14; // [rsp+88h] [rbp-78h]
  GUID v15; // [rsp+98h] [rbp-68h]
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v17; // [rsp+C8h] [rbp-38h]
  _BYTE v18[24]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v19; // [rsp+E8h] [rbp-18h]
  _BYTE v20[24]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v21; // [rsp+108h] [rbp+8h]
  _BYTE v22[24]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v23; // [rsp+128h] [rbp+28h]

  v9[0] = L"Windows.Foundation.Collections.IVector`1<Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest>";
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(v18, v9);
  v9[0] = L"Windows.Foundation.Collections.IVectorView`1<Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest>";
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(v20, v9);
  v9[0] = L"Windows.Foundation.Collections.IIterator`1<Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest>";
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(v22, v9);
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
0x180037d30  mov     [rsp-8+arg_0], rbx
0x180037d35  mov     [rsp-8+arg_10], rdi
0x180037d3a  push    rbp
0x180037d3b  lea     rbp, [rsp-40h]
0x180037d40  sub     rsp, 140h
0x180037d47  mov     rax, cs:__security_cookie
0x180037d4e  xor     rax, rsp
0x180037d51  mov     [rbp+40h+var_10], rax
0x180037d55  mov     rdi, rdx
0x180037d58  lea     rax, aWindowsFoundat_0; "Windows.Foundation.Collections.IVector`"...
0x180037d5f  mov     [rsp+140h+var_110], rax
0x180037d64  lea     rdx, [rsp+140h+var_110]
0x180037d69  lea     rcx, [rbp+40h+var_70]
0x180037d6d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180037d72  lea     rax, aWindowsFoundat_2; "Windows.Foundation.Collections.IVectorV"...
0x180037d79  mov     [rsp+140h+var_110], rax
0x180037d7e  lea     rdx, [rsp+140h+var_110]
0x180037d83  lea     rcx, [rbp+40h+var_50]
0x180037d87  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180037d8c  lea     rax, aWindowsFoundat; "Windows.Foundation.Collections.IIterato"...
0x180037d93  mov     [rsp+140h+var_110], rax
0x180037d98  lea     rdx, [rsp+140h+var_110]
0x180037d9d  lea     rcx, [rbp+40h+var_30]
0x180037da1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180037da6  mov     rax, [rbp+40h+var_58]
0x180037daa  mov     [rsp+140h+var_100], rax
0x180037daf  mov     rax, [rbp+40h+var_38]
0x180037db3  mov     [rsp+140h+var_F8], rax
0x180037db8  mov     rax, [rbp+40h+var_18]
0x180037dbc  mov     [rsp+140h+var_F0], rax
0x180037dc1  movups  xmm0, xmmword ptr cs:_GUID_297445d3_fb63_4135_8909_4e354c061466.Data1
0x180037dc8  movdqu  [rsp+140h+var_E8], xmm0
0x180037dce  movups  xmm1, xmmword ptr cs:_GUID_f6ed9226_b260_5f49_9b84_e89e43cbabc6.Data1
0x180037dd5  movdqu  [rsp+140h+var_D8], xmm1
0x180037ddb  movups  xmm0, xmmword ptr cs:_GUID_1a7c6c05_3fef_5eeb_aaff_625ee3ebc07c.Data1
0x180037de2  movdqu  [rsp+140h+var_C8], xmm0
0x180037de8  movups  xmm1, xmmword ptr cs:_GUID_cb72d686_9516_520d_a274_fa4cd1762cb2.Data1
0x180037def  movdqu  [rbp+40h+var_B8], xmm1
0x180037df4  movups  xmm0, xmmword ptr cs:_GUID_b6a5c8e4_6e3c_5c37_92cf_cf9f1c383335.Data1
0x180037dfb  movdqu  [rbp+40h+var_A8], xmm0
0x180037e00  mov     [rsp+140h+var_118], 0
0x180037e09  lea     rcx, [rsp+140h+var_118]
0x180037e0e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037e13  mov     [rbp+40h+var_78], 0
0x180037e1b  mov     r9d, 2Ch ; ','; unsigned int
0x180037e21  lea     r8d, [r9+1]; unsigned int
0x180037e25  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180037e2c  lea     rcx, [rbp+40h+hstringHeader]; hstringHeader
0x180037e30  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180037e35  lea     r8, [rsp+140h+var_118]
0x180037e3a  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180037e41  mov     rcx, [rbp+40h+var_78]
0x180037e45  call    cs:__imp_RoGetActivationFactory
0x180037e4b  mov     ebx, eax
0x180037e4d  test    eax, eax
0x180037e4f  js      short loc_180037E9E
0x180037e51  mov     [rsp+140h+var_120], 0
0x180037e5a  mov     rbx, [rsp+140h+var_118]
0x180037e5f  lea     rcx, [rsp+140h+var_120]
0x180037e64  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037e69  lea     r8, [rsp+140h+var_120]
0x180037e6e  lea     rdx, [rsp+140h+var_100]
0x180037e73  mov     rcx, rbx
0x180037e76  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x180037e7b  mov     ebx, eax
0x180037e7d  test    eax, eax
0x180037e7f  js      short loc_180037E94
0x180037e81  mov     rax, [rsp+140h+var_120]
0x180037e86  mov     [rsp+140h+var_120], 0
0x180037e8f  mov     [rdi], rax
0x180037e92  xor     ebx, ebx
0x180037e94  lea     rcx, [rsp+140h+var_120]
0x180037e99  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037e9e  lea     rcx, [rsp+140h+var_118]
0x180037ea3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037ea8  mov     eax, ebx
0x180037eaa  mov     rcx, [rbp+40h+var_10]
0x180037eae  xor     rcx, rsp; StackCookie
0x180037eb1  call    __security_check_cookie
0x180037eb6  lea     r11, [rsp+140h+var_s0]
0x180037ebe  mov     rbx, [r11+10h]
0x180037ec2  mov     rdi, [r11+20h]
0x180037ec6  mov     rsp, r11
0x180037ec9  pop     rbp
0x180037eca  retn
```
