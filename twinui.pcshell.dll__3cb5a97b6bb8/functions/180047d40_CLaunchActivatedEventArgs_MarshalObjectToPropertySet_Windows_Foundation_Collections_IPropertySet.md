# CLaunchActivatedEventArgs::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x180047d40`
- end: `0x1800481b6`
- name: `?MarshalObjectToPropertySet@CLaunchActivatedEventArgs@@UEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1142`
- prototype: `__int64 __fastcall(CLaunchActivatedEventArgs *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x180047d40`
- `0x18007b3e0`
- `0x1800a316c`
- `0x18019b00c`
- `0x180356360`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048139`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048192`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800481a5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048139`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048192`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800481a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180047dd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180047eff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180047f88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180047dd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180047eff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180047f88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047e1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047e4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047ff3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048001`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048081`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004808f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047e1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047e4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047ff3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048001`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048081`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004808f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180047dfe`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180047dfe`

## pseudocode

```c
__int64 __fastcall CLaunchActivatedEventArgs::MarshalObjectToPropertySet(
        CLaunchActivatedEventArgs *this,
        struct Windows::Foundation::Collections::IPropertySet *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 (__fastcall **v6)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rax
  __int64 (__fastcall *v7)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rbx
  int ActivationFactory; // eax
  HRESULT v9; // eax
  HSTRING v10; // rbx
  __int64 (__fastcall *v11)(char *, HSTRING *); // rbx
  int v12; // eax
  __int64 v13; // rax
  __int64 (__fastcall *v14)(char *, HSTRING *); // rbx
  int v15; // eax
  __int64 v16; // rax
  __int64 (__fastcall *v17)(char *, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING, __int64 *); // rbx
  int v21; // eax
  _QWORD *v22; // rbx
  __int64 v23; // rsi
  __int64 v24; // rdi
  HRESULT v25; // eax
  int v26; // eax
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, HSTRING, __int64 *); // rbx
  int v29; // eax
  _QWORD *v30; // rbx
  __int64 v31; // rsi
  __int64 v32; // rdi
  HRESULT v33; // eax
  int v34; // eax
  __int64 v35; // rbx
  __int64 v36; // rcx
  __int64 v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rdx
  _QWORD *v41; // rsi
  __int64 v42; // rax
  __int64 (__fastcall *v43)(_QWORD *, HSTRING, __int64, _BYTE *); // rdi
  int v44; // [rsp+20h] [rbp-39h]
  _BYTE v45[8]; // [rsp+30h] [rbp-29h] BYREF
  HSTRING v46; // [rsp+38h] [rbp-21h] BYREF
  HSTRING v47; // [rsp+40h] [rbp-19h] BYREF
  __int64 v48; // [rsp+48h] [rbp-11h] BYREF
  __int64 v49; // [rsp+50h] [rbp-9h] BYREF
  __int64 v50; // [rsp+58h] [rbp-1h] BYREF
  _QWORD *v51; // [rsp+60h] [rbp+7h] BYREF
  __int64 v52; // [rsp+68h] [rbp+Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+17h] BYREF
  HSTRING string; // [rsp+88h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v4 = CActivatedEventArgsWithPrelaunchAndViewIdBase::MarshalObjectToPropertySet(
         (CLaunchActivatedEventArgs *)((char *)this - 256),
         a2);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v4,
      v44);
    return v5;
  }
  v6 = *(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **))a2;
  v51 = 0;
  v52 = 0;
  v7 = *v6;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
  ActivationFactory = v7(a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v51);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v39 = 105;
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v39,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v44);
    goto LABEL_23;
  }
  string = 0;
  v9 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
  if ( v9 < 0 )
  {
    RaiseException(v9, 1u, 0, 0);
    __debugbreak();
  }
  v10 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
  ActivationFactory = RoGetActivationFactory(v10, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v52);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v39 = 106;
    goto LABEL_37;
  }
  v46 = 0;
  v11 = *(__int64 (__fastcall **)(char *, HSTRING *))(*((_QWORD *)this - 2) + 48LL);
  WindowsDeleteString(0);
  v46 = 0;
  v12 = v11((char *)this - 16, &v46);
  v5 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v12,
      v44);
    goto LABEL_22;
  }
  v13 = *((_QWORD *)this - 2);
  v47 = 0;
  v14 = *(__int64 (__fastcall **)(char *, HSTRING *))(v13 + 56);
  WindowsDeleteString(0);
  v47 = 0;
  v15 = v14((char *)this - 16, &v47);
  v5 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x71,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v15,
      v44);
LABEL_21:
    WindowsDeleteString(v47);
    v47 = 0;
LABEL_22:
    WindowsDeleteString(v46);
    v46 = 0;
LABEL_23:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    return v5;
  }
  v16 = *((_QWORD *)this - 1);
  v48 = 0;
  v17 = *(__int64 (__fastcall **)(char *, __int64 *))(v16 + 48);
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v48);
  v18 = v17((char *)this - 8, &v48);
  v5 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v18,
      v44);
LABEL_42:
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v48);
    goto LABEL_21;
  }
  v19 = v52;
  v49 = 0;
  v20 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v52 + 144LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  v21 = v20(v19, v46, &v49);
  v5 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v21,
      v44);
LABEL_41:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    goto LABEL_42;
  }
  v22 = v51;
  v23 = v49;
  v45[0] = 0;
  v24 = *v51;
  string = 0;
  v25 = WindowsCreateStringReference(L"Arguments", 9u, &hstringHeader, &string);
  if ( v25 < 0 )
  {
    RaiseException(v25, 1u, 0, 0);
    __debugbreak();
  }
  v26 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v24 + 80))(v22, string, v23, v45);
  v5 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v26,
      v44);
    goto LABEL_19;
  }
  v27 = v52;
  v50 = 0;
  v28 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v52 + 144LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  v29 = v28(v27, v47, &v50);
  v5 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v29,
      v44);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
LABEL_19:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    v38 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    goto LABEL_21;
  }
  v30 = v51;
  v31 = v50;
  v32 = *v51;
  string = 0;
  v33 = WindowsCreateStringReference(L"TileId", 6u, &hstringHeader, &string);
  if ( v33 < 0 )
  {
    RaiseException(v33, 1u, 0, 0);
    __debugbreak();
  }
  v34 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v32 + 80))(v30, string, v31, v45);
  v5 = v34;
  if ( v34 < 0 )
  {
    v40 = 126;
LABEL_40:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v40,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v34,
      v44);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    goto LABEL_41;
  }
  v35 = v48;
  if ( v48 )
  {
    v41 = v51;
    v42 = *v51;
    string = 0;
    v43 = *(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v42 + 80);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"TileActivatedInfo", 0x12u, 0x11u);
    v34 = v43(v41, string, v35, v45);
    v5 = v34;
    if ( v34 < 0 )
    {
      v40 = 130;
      goto LABEL_40;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  v36 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  }
  WindowsDeleteString(v47);
  v47 = 0;
  WindowsDeleteString(v46);
  v46 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
  return 0;
}

```

## disassembly

```asm
0x180047d40  mov     [rsp-8+arg_10], rbx
0x180047d45  mov     [rsp-8+arg_18], rsi
0x180047d4a  push    rbp
0x180047d4b  push    rdi
0x180047d4c  push    r14
0x180047d4e  lea     rbp, [rsp-47h]
0x180047d53  sub     rsp, 0A0h
0x180047d5a  mov     rax, cs:__security_cookie
0x180047d61  xor     rax, rsp
0x180047d64  mov     [rbp+57h+var_20], rax
0x180047d68  mov     rsi, rcx
0x180047d6b  mov     rdi, rdx
0x180047d6e  add     rcx, 0FFFFFFFFFFFFFF00h; this
0x180047d75  call    ?MarshalObjectToPropertySet@CActivatedEventArgsWithPrelaunchAndViewIdBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z; CActivatedEventArgsWithPrelaunchAndViewIdBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x180047d7a  xor     r14d, r14d
0x180047d7d  mov     ebx, eax
0x180047d7f  test    eax, eax
0x180047d81  js      loc_180048109
0x180047d87  mov     rax, [rdi]
0x180047d8a  lea     rcx, [rbp+57h+var_50]
0x180047d8e  mov     [rbp+57h+var_50], r14
0x180047d92  mov     [rbp+57h+var_48], r14
0x180047d96  mov     rbx, [rax]
0x180047d99  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180047d9e  lea     r8, [rbp+57h+var_50]
0x180047da2  mov     rcx, rdi
0x180047da5  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180047dac  mov     rax, rbx
0x180047daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047db4  mov     ebx, eax
0x180047db6  test    eax, eax
0x180047db8  js      loc_180048123
0x180047dbe  lea     r9, [rbp+57h+string]; string
0x180047dc2  mov     [rbp+57h+string], r14
0x180047dc6  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180047dca  lea     edx, [r14+20h]; length
0x180047dce  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x180047dd5  call    cs:__imp_WindowsCreateStringReference
0x180047ddb  test    eax, eax
0x180047ddd  js      loc_18004812D
0x180047de3  mov     rbx, [rbp+57h+string]
0x180047de7  lea     rcx, [rbp+57h+var_48]
0x180047deb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180047df0  lea     r8, [rbp+57h+var_48]
0x180047df4  mov     rcx, rbx
0x180047df7  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x180047dfe  call    cs:__imp_RoGetActivationFactory
0x180047e04  mov     ebx, eax
0x180047e06  test    eax, eax
0x180047e08  js      loc_180048140
0x180047e0e  lea     rdi, [rsi-10h]
0x180047e12  mov     [rbp+57h+var_78], r14
0x180047e16  mov     rax, [rdi]
0x180047e19  xor     ecx, ecx; string
0x180047e1b  mov     rbx, [rax+30h]
0x180047e1f  call    cs:__imp_WindowsDeleteString
0x180047e25  lea     rdx, [rbp+57h+var_78]
0x180047e29  mov     [rbp+57h+var_78], r14
0x180047e2d  mov     rcx, rdi
0x180047e30  mov     rax, rbx
0x180047e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e38  mov     ebx, eax
0x180047e3a  test    eax, eax
0x180047e3c  js      loc_1800480EF
0x180047e42  mov     rax, [rdi]
0x180047e45  xor     ecx, ecx; string
0x180047e47  mov     [rbp+57h+var_70], r14
0x180047e4b  mov     rbx, [rax+38h]
0x180047e4f  call    cs:__imp_WindowsDeleteString
0x180047e55  lea     rdx, [rbp+57h+var_70]
0x180047e59  mov     [rbp+57h+var_70], r14
0x180047e5d  mov     rcx, rdi
0x180047e60  mov     rax, rbx
0x180047e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e68  mov     ebx, eax
0x180047e6a  test    eax, eax
0x180047e6c  js      loc_1800480D5
0x180047e72  mov     rax, [rsi-8]
0x180047e76  lea     rcx, [rbp+57h+var_68]
0x180047e7a  mov     [rbp+57h+var_68], r14
0x180047e7e  mov     rbx, [rax+30h]
0x180047e82  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x180047e87  lea     rdx, [rbp+57h+var_68]
0x180047e8b  mov     rax, rbx
0x180047e8e  lea     rcx, [rsi-8]
0x180047e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e97  mov     ebx, eax
0x180047e99  test    eax, eax
0x180047e9b  js      loc_18004814A
0x180047ea1  mov     rdi, [rbp+57h+var_48]
0x180047ea5  lea     rcx, [rbp+57h+var_60]
0x180047ea9  mov     [rbp+57h+var_60], r14
0x180047ead  mov     rax, [rdi]
0x180047eb0  mov     rbx, [rax+90h]
0x180047eb7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180047ebc  mov     rdx, [rbp+57h+var_78]
0x180047ec0  lea     r8, [rbp+57h+var_60]
0x180047ec4  mov     rcx, rdi
0x180047ec7  mov     rax, rbx
0x180047eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ecf  mov     ebx, eax
0x180047ed1  test    eax, eax
0x180047ed3  js      loc_180048168
0x180047ed9  mov     rbx, [rbp+57h+var_50]
0x180047edd  lea     r9, [rbp+57h+string]; string
0x180047ee1  mov     rsi, [rbp+57h+var_60]
0x180047ee5  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180047ee9  mov     [rbp+57h+var_80], r14b
0x180047eed  lea     edx, [r14+9]; length
0x180047ef1  lea     rcx, aArguments_0; "Arguments"
0x180047ef8  mov     rdi, [rbx]
0x180047efb  mov     [rbp+57h+string], r14
0x180047eff  call    cs:__imp_WindowsCreateStringReference
0x180047f05  test    eax, eax
0x180047f07  js      loc_180048186
0x180047f0d  mov     rdx, [rbp+57h+string]
0x180047f11  lea     r9, [rbp+57h+var_80]
0x180047f15  mov     rax, [rdi+50h]
0x180047f19  mov     r8, rsi
0x180047f1c  mov     rcx, rbx
0x180047f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f24  mov     ebx, eax
0x180047f26  test    eax, eax
0x180047f28  js      loc_180048043
0x180047f2e  mov     rdi, [rbp+57h+var_48]
0x180047f32  lea     rcx, [rbp+57h+var_58]
0x180047f36  mov     [rbp+57h+var_58], r14
0x180047f3a  mov     rax, [rdi]
0x180047f3d  mov     rbx, [rax+90h]
0x180047f44  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180047f49  mov     rdx, [rbp+57h+var_70]
0x180047f4d  lea     r8, [rbp+57h+var_58]
0x180047f51  mov     rcx, rdi
0x180047f54  mov     rax, rbx
0x180047f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f5c  mov     ebx, eax
0x180047f5e  test    eax, eax
0x180047f60  js      loc_1800480B2
0x180047f66  mov     rbx, [rbp+57h+var_50]
0x180047f6a  lea     r9, [rbp+57h+string]; string
0x180047f6e  mov     rsi, [rbp+57h+var_58]
0x180047f72  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180047f76  lea     edx, [r14+6]; length
0x180047f7a  lea     rcx, aTileid_0; "TileId"
0x180047f81  mov     rdi, [rbx]
0x180047f84  mov     [rbp+57h+string], r14
0x180047f88  call    cs:__imp_WindowsCreateStringReference
0x180047f8e  test    eax, eax
0x180047f90  js      loc_180048199
0x180047f96  mov     rdx, [rbp+57h+string]
0x180047f9a  lea     r9, [rbp+57h+var_80]
0x180047f9e  mov     rax, [rdi+50h]
0x180047fa2  mov     r8, rsi
0x180047fa5  mov     rcx, rbx
0x180047fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047fad  mov     ebx, eax
0x180047faf  test    eax, eax
0x180047fb1  js      loc_1800481AC
0x180047fb7  mov     rbx, [rbp+57h+var_68]
0x180047fbb  test    rbx, rbx
0x180047fbe  jnz     loc_1806EDB43
0x180047fc4  lea     rcx, [rbp+57h+var_58]
0x180047fc8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180047fcd  lea     rcx, [rbp+57h+var_60]
0x180047fd1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180047fd6  mov     rcx, [rbp+57h+var_68]
0x180047fda  test    rcx, rcx
0x180047fdd  jz      short loc_180047FEF
0x180047fdf  mov     [rbp+57h+var_68], r14
0x180047fe3  mov     rax, [rcx]
0x180047fe6  mov     rax, [rax+10h]
0x180047fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047fef  mov     rcx, [rbp+57h+var_70]; string
0x180047ff3  call    cs:__imp_WindowsDeleteString
0x180047ff9  mov     rcx, [rbp+57h+var_78]; string
0x180047ffd  mov     [rbp+57h+var_70], r14
0x180048001  call    cs:__imp_WindowsDeleteString
0x180048007  lea     rcx, [rbp+57h+var_48]
0x18004800b  mov     [rbp+57h+var_78], r14
0x18004800f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048014  lea     rcx, [rbp+57h+var_50]
0x180048018  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004801d  xor     eax, eax
0x18004801f  mov     rcx, [rbp+57h+var_20]
0x180048023  xor     rcx, rsp; StackCookie
0x180048026  call    __security_check_cookie
0x18004802b  lea     r11, [rsp+0B0h+var_10]
0x180048033  mov     rbx, [r11+30h]
0x180048037  mov     rsi, [r11+38h]
0x18004803b  mov     rsp, r11
0x18004803e  pop     r14
0x180048040  pop     rdi
0x180048041  pop     rbp
0x180048042  retn
0x180048043  mov     rcx, [rbp+5Fh]; this
0x180048047  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\lib\\activationevent"...
0x18004804e  mov     r9d, eax; char *
0x180048051  mov     edx, 7Ah ; 'z'; void *
0x180048056  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004805b  lea     rcx, [rbp+57h+var_60]
0x18004805f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048064  mov     rcx, [rbp+57h+var_68]
0x180048068  test    rcx, rcx
0x18004806b  jz      short loc_18004807D
0x18004806d  mov     [rbp+57h+var_68], r14
0x180048071  mov     rax, [rcx]
0x180048074  mov     rax, [rax+10h]
0x180048078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004807d  mov     rcx, [rbp+57h+var_70]; string
0x180048081  call    cs:__imp_WindowsDeleteString
0x180048087  mov     [rbp+57h+var_70], r14
0x18004808b  mov     rcx, [rbp+57h+var_78]; string
0x18004808f  call    cs:__imp_WindowsDeleteString
0x180048095  mov     [rbp+57h+var_78], r14
0x180048099  lea     rcx, [rbp+57h+var_48]
0x18004809d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800480a2  lea     rcx, [rbp+57h+var_50]
0x1800480a6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800480ab  mov     eax, ebx
0x1800480ad  jmp     loc_18004801F
0x1800480b2  mov     rcx, [rbp+5Fh]; this
0x1800480b6  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\lib\\activationevent"...
0x1800480bd  mov     r9d, eax; char *
0x1800480c0  mov     edx, 7Dh ; '}'; void *
0x1800480c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800480ca  lea     rcx, [rbp+57h+var_58]
0x1800480ce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800480d3  jmp     short loc_18004805B
0x1800480d5  mov     rcx, [rbp+5Fh]; this
0x1800480d9  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\lib\\activationevent"...
0x1800480e0  mov     r9d, eax; char *
0x1800480e3  mov     edx, 71h ; 'q'; void *
0x1800480e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800480ed  jmp     short loc_18004807D
0x1800480ef  mov     rcx, [rbp+5Fh]; this
0x1800480f3  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\lib\\activationevent"...
0x1800480fa  mov     r9d, eax; char *
0x1800480fd  mov     edx, 6Eh ; 'n'; void *
0x180048102  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048107  jmp     short loc_18004808B
0x180048109  mov     rcx, [rbp+5Fh]; this
0x18004810d  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\lib\\activationevent"...
0x180048114  mov     r9d, ebx; char *
0x180048117  mov     edx, 64h ; 'd'; void *
0x18004811c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048121  jmp     short loc_1800480AB
0x180048123  mov     edx, 69h ; 'i'; void *
0x180048128  jmp     loc_1806EDB2A
0x18004812d  xor     r9d, r9d; lpArguments
0x180048130  xor     r8d, r8d; nNumberOfArguments
0x180048133  mov     ecx, eax; dwExceptionCode
0x180048135  lea     edx, [r9+1]; dwExceptionFlags
0x180048139  call    cs:__imp_RaiseException
0x18004813f  int     3; Trap to Debugger
0x180048140  mov     edx, 6Ah ; 'j'
0x180048145  jmp     loc_1806EDB2A
0x18004814a  mov     rcx, [rbp+5Fh]; this
0x18004814e  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\lib\\activationevent"...
0x180048155  mov     r9d, eax; char *
0x180048158  mov     edx, 74h ; 't'; void *
0x18004815d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048162  nop
0x180048163  jmp     loc_1806EDBB6
0x180048168  mov     rcx, [rbp+5Fh]; this
0x18004816c  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\lib\\activationevent"...
0x180048173  mov     r9d, eax; char *
0x180048176  mov     edx, 78h ; 'x'; void *
0x18004817b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048180  nop
0x180048181  jmp     loc_1806EDBAD
0x180048186  xor     r9d, r9d; lpArguments
0x180048189  xor     r8d, r8d; nNumberOfArguments
0x18004818c  mov     ecx, eax; dwExceptionCode
0x18004818e  lea     edx, [r9+1]; dwExceptionFlags
0x180048192  call    cs:__imp_RaiseException
0x180048198  int     3; Trap to Debugger
0x180048199  xor     r9d, r9d; lpArguments
0x18004819c  xor     r8d, r8d; nNumberOfArguments
0x18004819f  mov     ecx, eax; dwExceptionCode
0x1800481a1  lea     edx, [r9+1]; dwExceptionFlags
0x1800481a5  call    cs:__imp_RaiseException
0x1800481ab  int     3; Trap to Debugger
0x1800481ac  mov     edx, 7Eh ; '~'
0x1800481b1  jmp     loc_1806EDB91
0x1806edb2a  mov     rcx, [rbp+5Fh]; this
0x1806edb2e  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\lib\\activationevent"...
0x1806edb35  mov     r9d, eax; char *
0x1806edb38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1806edb3d  nop
0x1806edb3e  jmp     loc_180048099
0x1806edb43  mov     rsi, [rbp+57h+var_50]
0x1806edb47  lea     rdx, aTileactivatedi; "TileActivatedInfo"
0x1806edb4e  mov     r9d, 11h; unsigned int
0x1806edb54  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1806edb58  mov     rax, [rsi]
0x1806edb5b  lea     r8d, [r9+1]; unsigned int
0x1806edb5f  mov     [rbp+57h+string], r14
0x1806edb63  mov     rdi, [rax+50h]
0x1806edb67  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1806edb6c  mov     rdx, [rbp+57h+string]
  ... truncated ...
```
