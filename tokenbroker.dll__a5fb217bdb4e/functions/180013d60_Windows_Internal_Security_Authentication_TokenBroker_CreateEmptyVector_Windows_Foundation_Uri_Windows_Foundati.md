# Windows::Internal::Security::Authentication::TokenBroker::CreateEmptyVector<Windows::Foundation::Uri *>(Windows::Foundation::Collections::IVector<Windows::Foundation::Uri *> * *)

- ea: `0x180013d60`
- end: `0x18001400b`
- name: `??$CreateEmptyVector@PEAVUri@Foundation@Windows@@@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAPEAU?$IVector@PEAVUri@Foundation@Windows@@@Collections@Foundation@4@@Z`
- size: `683`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180011400`
- `0x18009e3d0`

## callees

- `0x180007350`
- `0x180013d60`
- `0x18008e690`
- `0x18009b108`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013fae`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013fc2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013fd6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013fea`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013fae`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013fc2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013fd6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013fea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013dac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013dd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013df8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013e78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013dac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013dd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013df8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013e78`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013e96`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013e96`

## string_xrefs

- `0x180013da5`: `Windows.Foundation.Collections.IVector`1<Windows.Foundation.Uri>`
- `0x180013dcb`: `Windows.Foundation.Collections.IVectorView`1<Windows.Foundation.Uri>`
- `0x180013df1`: `Windows.Foundation.Collections.IIterator`1<Windows.Foundation.Uri>`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::CreateEmptyVector<Windows::Foundation::Uri *>(
        _QWORD *a1)
{
  HRESULT v2; // eax
  HRESULT v3; // eax
  HRESULT v4; // eax
  HRESULT v5; // eax
  int ActivationFactory; // ebx
  __int64 (__fastcall ***v7)(_QWORD, GUID *, _QWORD *); // rax
  __int64 v8; // rcx
  __int64 (__fastcall ***v9)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 (__fastcall ***v10)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v12; // rcx
  __int64 (__fastcall ***v13)(_QWORD, GUID *, _QWORD *); // [rsp+20h] [rbp-E0h] BYREF
  __int64 v14; // [rsp+28h] [rbp-D8h] BYREF
  __int64 (__fastcall ***v15)(_QWORD, GUID *, _QWORD *); // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v16[3]; // [rsp+40h] [rbp-C0h] BYREF
  GUID v17; // [rsp+58h] [rbp-A8h]
  GUID v18; // [rsp+68h] [rbp-98h]
  GUID v19; // [rsp+78h] [rbp-88h]
  GUID v20; // [rsp+88h] [rbp-78h]
  GUID v21; // [rsp+98h] [rbp-68h]
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING string; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING_HEADER v24; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING v25; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING_HEADER v26; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING v27; // [rsp+108h] [rbp+8h] BYREF
  HSTRING_HEADER v28; // [rsp+110h] [rbp+10h] BYREF
  HSTRING v29; // [rsp+128h] [rbp+28h] BYREF

  v15 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
  string = 0;
  v2 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Foundation.Uri>",
         0x40u,
         &hstringHeader,
         &string);
  if ( v2 < 0 )
  {
    RaiseException(v2, 1u, 0, 0);
    __debugbreak();
  }
  v25 = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Foundation.Uri>",
         0x44u,
         &v24,
         &v25);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  v27 = 0;
  v4 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IIterator`1<Windows.Foundation.Uri>",
         0x42u,
         &v26,
         &v27);
  if ( v4 < 0 )
  {
    RaiseException(v4, 1u, 0, 0);
    __debugbreak();
  }
  v16[0] = string;
  v16[1] = v25;
  v16[2] = v27;
  v17 = GUID_9e365e57_48b2_4160_956f_c7385120bbfc;
  v18 = GUID_0d82bd8d_fe62_5d67_a7b9_7886dd75bc4e;
  v19 = GUID_4b8385bd_a2cd_5ff1_bf74_7ea580423e50;
  v20 = GUID_b0d63b78_78ad_5e31_b6d8_e32a0e16c447;
  v21 = GUID_1c157d0f_5efe_5cec_bbd6_0c6ce9af07a5;
  v14 = 0;
  v29 = 0;
  v5 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v28, &v29);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v29, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v14);
  if ( ActivationFactory < 0 )
  {
    v12 = v14;
    if ( v14 )
    {
      v14 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  else
  {
    v13 = 0;
    ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v14, v16, &v13);
    if ( ActivationFactory < 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
    }
    else
    {
      v7 = v13;
      v13 = 0;
      v15 = v7;
      v8 = v14;
      if ( v14 )
      {
        v14 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      ActivationFactory = 0;
    }
  }
  if ( ActivationFactory >= 0 )
  {
    v13 = 0;
    ActivationFactory = (**v15)(v15, &GUID_0d82bd8d_fe62_5d67_a7b9_7886dd75bc4e, &v13);
    if ( ActivationFactory < 0 )
    {
      v9 = v13;
    }
    else
    {
      v9 = 0;
      *a1 = v13;
    }
    if ( v9 )
    {
      v13 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v9)[2])(v9);
    }
  }
  v10 = v15;
  if ( v15 )
  {
    v15 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v10)[2])(v10);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180013d60  push    rbp
0x180013d62  push    rbx
0x180013d63  push    rsi
0x180013d64  push    rdi
0x180013d65  lea     rbp, [rsp-48h]
0x180013d6a  sub     rsp, 148h
0x180013d71  mov     rax, cs:__security_cookie
0x180013d78  xor     rax, rsp
0x180013d7b  mov     [rbp+60h+var_30], rax
0x180013d7f  mov     rdi, rcx
0x180013d82  xor     esi, esi
0x180013d84  mov     [rsp+160h+var_130], rsi
0x180013d89  lea     rcx, [rsp+160h+var_130]
0x180013d8e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013d93  nop
0x180013d94  mov     [rbp+60h+string], rsi
0x180013d98  lea     r9, [rbp+60h+string]; string
0x180013d9c  lea     r8, [rbp+60h+hstringHeader]; hstringHeader
0x180013da0  mov     edx, 40h ; '@'; length
0x180013da5  lea     rcx, aWindowsFoundat; "Windows.Foundation.Collections.IVector`"...
0x180013dac  call    cs:__imp_WindowsCreateStringReference
0x180013db2  test    eax, eax
0x180013db4  js      loc_180013FA1
0x180013dba  mov     [rbp+60h+var_78], rsi
0x180013dbe  lea     r9, [rbp+60h+var_78]; string
0x180013dc2  lea     r8, [rbp+60h+var_90]; hstringHeader
0x180013dc6  mov     edx, 44h ; 'D'; length
0x180013dcb  lea     rcx, aWindowsFoundat_16; "Windows.Foundation.Collections.IVectorV"...
0x180013dd2  call    cs:__imp_WindowsCreateStringReference
0x180013dd8  test    eax, eax
0x180013dda  js      loc_180013FB5
0x180013de0  mov     [rbp+60h+var_58], rsi
0x180013de4  lea     r9, [rbp+60h+var_58]; string
0x180013de8  lea     r8, [rbp+60h+var_70]; hstringHeader
0x180013dec  mov     edx, 42h ; 'B'; length
0x180013df1  lea     rcx, aWindowsFoundat_11; "Windows.Foundation.Collections.IIterato"...
0x180013df8  call    cs:__imp_WindowsCreateStringReference
0x180013dfe  test    eax, eax
0x180013e00  js      loc_180013FC9
0x180013e06  mov     rax, [rbp+60h+string]
0x180013e0a  mov     [rsp+160h+var_120], rax
0x180013e0f  mov     rax, [rbp+60h+var_78]
0x180013e13  mov     [rsp+160h+var_118], rax
0x180013e18  mov     rax, [rbp+60h+var_58]
0x180013e1c  mov     [rsp+160h+var_110], rax
0x180013e21  movups  xmm0, xmmword ptr cs:_GUID_9e365e57_48b2_4160_956f_c7385120bbfc.Data1
0x180013e28  movups  [rsp+160h+var_108], xmm0
0x180013e2d  movups  xmm1, xmmword ptr cs:_GUID_0d82bd8d_fe62_5d67_a7b9_7886dd75bc4e.Data1
0x180013e34  movups  [rsp+160h+var_F8], xmm1
0x180013e39  movups  xmm0, xmmword ptr cs:_GUID_4b8385bd_a2cd_5ff1_bf74_7ea580423e50.Data1
0x180013e40  movups  [rsp+160h+var_E8], xmm0
0x180013e45  movups  xmm1, xmmword ptr cs:_GUID_b0d63b78_78ad_5e31_b6d8_e32a0e16c447.Data1
0x180013e4c  movups  [rbp+60h+var_D8], xmm1
0x180013e50  movups  xmm0, xmmword ptr cs:_GUID_1c157d0f_5efe_5cec_bbd6_0c6ce9af07a5.Data1
0x180013e57  movups  [rbp+60h+var_C8], xmm0
0x180013e5b  mov     [rsp+160h+var_138], rsi
0x180013e60  mov     [rbp+60h+var_38], rsi
0x180013e64  lea     r9, [rbp+60h+var_38]; string
0x180013e68  lea     r8, [rbp+60h+var_50]; hstringHeader
0x180013e6c  mov     edx, 2Ch ; ','; length
0x180013e71  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180013e78  call    cs:__imp_WindowsCreateStringReference
0x180013e7e  test    eax, eax
0x180013e80  js      loc_180013FDD
0x180013e86  lea     r8, [rsp+160h+var_138]
0x180013e8b  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180013e92  mov     rcx, [rbp+60h+var_38]
0x180013e96  call    cs:__imp_RoGetActivationFactory
0x180013e9c  mov     ebx, eax
0x180013e9e  test    eax, eax
0x180013ea0  js      loc_180013F79
0x180013ea6  mov     [rsp+160h+var_140], rsi
0x180013eab  lea     r8, [rsp+160h+var_140]
0x180013eb0  lea     rdx, [rsp+160h+var_120]
0x180013eb5  mov     rcx, [rsp+160h+var_138]
0x180013eba  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x180013ebf  mov     ebx, eax
0x180013ec1  test    eax, eax
0x180013ec3  js      loc_180013FF1
0x180013ec9  mov     rax, [rsp+160h+var_140]
0x180013ece  mov     [rsp+160h+var_140], rsi
0x180013ed3  mov     [rsp+160h+var_130], rax
0x180013ed8  mov     rcx, [rsp+160h+var_138]
0x180013edd  test    rcx, rcx
0x180013ee0  jz      short loc_180013EF4
0x180013ee2  mov     [rsp+160h+var_138], rsi
0x180013ee7  mov     rax, [rcx]
0x180013eea  mov     rax, [rax+10h]
0x180013eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ef3  nop
0x180013ef4  mov     ebx, esi
0x180013ef6  test    ebx, ebx
0x180013ef8  js      short loc_180013F43
0x180013efa  mov     [rsp+160h+var_140], rsi
0x180013eff  mov     rcx, [rsp+160h+var_130]
0x180013f04  mov     rax, [rcx]
0x180013f07  lea     r8, [rsp+160h+var_140]
0x180013f0c  lea     rdx, _GUID_0d82bd8d_fe62_5d67_a7b9_7886dd75bc4e
0x180013f13  mov     rax, [rax]
0x180013f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f1b  mov     ebx, eax
0x180013f1d  test    eax, eax
0x180013f1f  js      short loc_180013F9A
0x180013f21  mov     rax, [rsp+160h+var_140]
0x180013f26  mov     rcx, rsi
0x180013f29  mov     [rdi], rax
0x180013f2c  test    rcx, rcx
0x180013f2f  jz      short loc_180013F43
0x180013f31  mov     [rsp+160h+var_140], rsi
0x180013f36  mov     rax, [rcx]
0x180013f39  mov     rax, [rax+10h]
0x180013f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f42  nop
0x180013f43  mov     rcx, [rsp+160h+var_130]
0x180013f48  test    rcx, rcx
0x180013f4b  jz      short loc_180013F5F
0x180013f4d  mov     [rsp+160h+var_130], rsi
0x180013f52  mov     rax, [rcx]
0x180013f55  mov     rax, [rax+10h]
0x180013f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f5e  nop
0x180013f5f  mov     eax, ebx
0x180013f61  mov     rcx, [rbp+60h+var_30]
0x180013f65  xor     rcx, rsp; StackCookie
0x180013f68  call    __security_check_cookie
0x180013f6d  add     rsp, 148h
0x180013f74  pop     rdi
0x180013f75  pop     rsi
0x180013f76  pop     rbx
0x180013f77  pop     rbp
0x180013f78  retn
0x180013f79  mov     rcx, [rsp+160h+var_138]
0x180013f7e  test    rcx, rcx
0x180013f81  jz      short loc_180013F95
0x180013f83  mov     [rsp+160h+var_138], rsi
0x180013f88  mov     rax, [rcx]
0x180013f8b  mov     rax, [rax+10h]
0x180013f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f94  nop
0x180013f95  jmp     loc_180013EF6
0x180013f9a  mov     rcx, [rsp+160h+var_140]
0x180013f9f  jmp     short loc_180013F2C
0x180013fa1  xor     r9d, r9d; lpArguments
0x180013fa4  xor     r8d, r8d; nNumberOfArguments
0x180013fa7  mov     edx, 1; dwExceptionFlags
0x180013fac  mov     ecx, eax; dwExceptionCode
0x180013fae  call    cs:__imp_RaiseException
0x180013fb4  int     3; Trap to Debugger
0x180013fb5  xor     r9d, r9d; lpArguments
0x180013fb8  xor     r8d, r8d; nNumberOfArguments
0x180013fbb  mov     edx, 1; dwExceptionFlags
0x180013fc0  mov     ecx, eax; dwExceptionCode
0x180013fc2  call    cs:__imp_RaiseException
0x180013fc8  int     3; Trap to Debugger
0x180013fc9  xor     r9d, r9d; lpArguments
0x180013fcc  xor     r8d, r8d; nNumberOfArguments
0x180013fcf  mov     edx, 1; dwExceptionFlags
0x180013fd4  mov     ecx, eax; dwExceptionCode
0x180013fd6  call    cs:__imp_RaiseException
0x180013fdc  int     3; Trap to Debugger
0x180013fdd  xor     r9d, r9d; lpArguments
0x180013fe0  xor     r8d, r8d; nNumberOfArguments
0x180013fe3  mov     edx, 1; dwExceptionFlags
0x180013fe8  mov     ecx, eax; dwExceptionCode
0x180013fea  call    cs:__imp_RaiseException
0x180013ff0  int     3; Trap to Debugger
0x180013ff1  lea     rcx, [rsp+160h+var_140]
0x180013ff6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013ffb  lea     rcx, [rsp+160h+var_138]
0x180014000  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014005  jmp     loc_180013EF6
```
