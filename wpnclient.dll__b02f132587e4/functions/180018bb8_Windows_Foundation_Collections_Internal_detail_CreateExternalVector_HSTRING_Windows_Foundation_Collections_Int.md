# Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)

- ea: `0x180018bb8`
- end: `0x180018c9a`
- name: `??$CreateExternalVector@PEAUHSTRING__@@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@1234@@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800186f0`

## callees

- `0x18001478c`
- `0x180018bb8`
- `0x18001d854`
- `0x18001ff00`
- `0x180026068`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180018c24`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180018c24`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(
        __int64 a1,
        _QWORD *a2)
{
  int ActivationFactory; // ebx
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v7; // [rsp+20h] [rbp-40h] BYREF
  __int64 v8; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  __int64 v10; // [rsp+48h] [rbp-18h]

  *a2 = 0;
  v8 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v8);
  v10 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Foundation.Collections.Detail.Vector",
    0x2Du,
    0x2Cu);
  ActivationFactory = RoGetActivationFactory(v10, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v8);
  if ( ActivationFactory >= 0 )
  {
    v7 = 0;
    v4 = v8;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v7);
    ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{208,{flat}}(v4, &v7);
    if ( ActivationFactory >= 0 )
    {
      v5 = v7;
      v7 = 0;
      *a2 = v5;
      ActivationFactory = 0;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v7);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v8);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180018bb8  mov     [rsp-8+arg_0], rbx
0x180018bbd  mov     [rsp-8+arg_10], rdi
0x180018bc2  push    rbp
0x180018bc3  mov     rbp, rsp
0x180018bc6  sub     rsp, 60h
0x180018bca  mov     rax, cs:__security_cookie
0x180018bd1  xor     rax, rsp
0x180018bd4  mov     [rbp+var_10], rax
0x180018bd8  mov     rdi, rdx
0x180018bdb  mov     qword ptr [rdx], 0
0x180018be2  mov     [rbp+var_38], 0
0x180018bea  lea     rcx, [rbp+var_38]
0x180018bee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018bf3  mov     [rbp+var_18], 0
0x180018bfb  mov     r9d, 2Ch ; ','; unsigned int
0x180018c01  lea     r8d, [r9+1]; unsigned int
0x180018c05  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180018c0c  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180018c10  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180018c15  lea     r8, [rbp+var_38]
0x180018c19  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180018c20  mov     rcx, [rbp+var_18]
0x180018c24  call    cs:__imp_RoGetActivationFactory
0x180018c2a  mov     ebx, eax
0x180018c2c  test    eax, eax
0x180018c2e  js      short loc_180018C71
0x180018c30  mov     [rbp+var_40], 0
0x180018c38  mov     rbx, [rbp+var_38]
0x180018c3c  lea     rcx, [rbp+var_40]
0x180018c40  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018c45  lea     rdx, [rbp+var_40]
0x180018c49  mov     rcx, rbx
0x180018c4c  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BNA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{208,{flat}}
0x180018c51  mov     ebx, eax
0x180018c53  test    eax, eax
0x180018c55  js      short loc_180018C68
0x180018c57  mov     rax, [rbp+var_40]
0x180018c5b  mov     [rbp+var_40], 0
0x180018c63  mov     [rdi], rax
0x180018c66  xor     ebx, ebx
0x180018c68  lea     rcx, [rbp+var_40]
0x180018c6c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018c71  lea     rcx, [rbp+var_38]
0x180018c75  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018c7a  mov     eax, ebx
0x180018c7c  mov     rcx, [rbp+var_10]
0x180018c80  xor     rcx, rsp; StackCookie
0x180018c83  call    __security_check_cookie
0x180018c88  lea     r11, [rsp+60h+var_s0]
0x180018c8d  mov     rbx, [r11+10h]
0x180018c91  mov     rdi, [r11+20h]
0x180018c95  mov     rsp, r11
0x180018c98  pop     rbp
0x180018c99  retn
```
