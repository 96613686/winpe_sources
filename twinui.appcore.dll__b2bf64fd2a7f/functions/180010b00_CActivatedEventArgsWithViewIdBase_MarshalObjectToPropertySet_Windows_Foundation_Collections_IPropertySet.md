# CActivatedEventArgsWithViewIdBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x180010b00`
- end: `0x180011050`
- name: `?MarshalObjectToPropertySet@CActivatedEventArgsWithViewIdBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1360`
- prototype: `__int64 __fastcall(CActivatedEventArgsWithViewIdBase *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011c6c`

## callees

- `0x180003d24`
- `0x1800083f0`
- `0x180010b00`
- `0x180011058`
- `0x18001cc38`
- `0x180022fb4`
- `0x18002b1b0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010bdc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010d7f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010eb5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010f6b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010bdc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010d7f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010eb5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010f6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010bc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010d68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010e9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010f54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010bc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010d68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010e9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010f54`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180010bfe`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180010bfe`

## pseudocode

```c
__int64 __fastcall CActivatedEventArgsWithViewIdBase::MarshalObjectToPropertySet(
        CActivatedEventArgsWithViewIdBase *this,
        struct Windows::Foundation::Collections::IPropertySet *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 (__fastcall **v7)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rax
  __int64 (__fastcall *v8)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rbx
  int v9; // eax
  int v10; // ebx
  HRESULT v11; // eax
  HSTRING v12; // rbx
  int ActivationFactory; // eax
  int v14; // eax
  __int64 v15; // rax
  __int64 (__fastcall *v16)(char *, __int64 *); // rbx
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, _QWORD, __int64 *); // rbx
  int v22; // eax
  _QWORD *v23; // rbx
  __int64 v24; // rsi
  __int64 v25; // rdi
  HRESULT v26; // eax
  int v27; // eax
  __int64 v28; // rbx
  _QWORD *v29; // rsi
  __int64 v30; // rax
  __int64 (__fastcall *v31)(_QWORD *, HSTRING, __int64, _BYTE *); // rdi
  int v32; // eax
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, _QWORD, __int64 *); // rbx
  int v35; // eax
  _QWORD *v36; // rbx
  __int64 v37; // rsi
  __int64 v38; // rdi
  HRESULT v39; // eax
  int v40; // eax
  __int64 v41; // rdi
  __int64 (__fastcall *v42)(__int64, _QWORD, __int64 *); // rbx
  __int64 v43; // rdx
  _QWORD *v44; // rbx
  __int64 v45; // rsi
  __int64 v46; // rdi
  HRESULT v47; // eax
  __int64 v48; // rcx
  int v49; // [rsp+20h] [rbp-49h]
  _BYTE v50[8]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v51; // [rsp+38h] [rbp-31h] BYREF
  _QWORD *v52; // [rsp+40h] [rbp-29h] BYREF
  __int64 v53; // [rsp+48h] [rbp-21h] BYREF
  __int64 v54; // [rsp+50h] [rbp-19h] BYREF
  __int64 v55; // [rsp+58h] [rbp-11h] BYREF
  __int64 v56; // [rsp+60h] [rbp-9h] BYREF
  unsigned int v57; // [rsp+68h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+7h] BYREF
  HSTRING string; // [rsp+88h] [rbp+1Fh] BYREF
  __int128 v60; // [rsp+90h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v4 = CActivatedEventArgsBase::MarshalObjectToPropertySet(this, a2);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x220,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v4,
      v49);
    return v5;
  }
  v7 = *(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **))a2;
  v52 = 0;
  v51 = 0;
  v8 = *v7;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
  v9 = v8(a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v52);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x225,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v9,
      v49);
LABEL_40:
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v51);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    return (unsigned int)v10;
  }
  string = 0;
  v11 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v12 = string;
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v51);
  ActivationFactory = RoGetActivationFactory(v12, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v51);
  v10 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x226,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v49);
    goto LABEL_40;
  }
  v57 = 0;
  v14 = (*(__int64 (__fastcall **)(char *, unsigned int *))(*((_QWORD *)this + 19) + 48LL))((char *)this + 152, &v57);
  v10 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x229,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v14,
      v49);
    goto LABEL_40;
  }
  v15 = *((_QWORD *)this + 20);
  v53 = 0;
  v16 = *(__int64 (__fastcall **)(char *, __int64 *))(v15 + 48);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
  v17 = v16((char *)this + 160, &v53);
  v10 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22C,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v17,
      v49);
LABEL_39:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
    goto LABEL_40;
  }
  v18 = *((_QWORD *)this + 21);
  v60 = 0;
  v19 = (*(__int64 (__fastcall **)(char *, __int128 *))(v18 + 64))((char *)this + 168, &v60);
  v10 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22F,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v19,
      v49);
    goto LABEL_39;
  }
  v20 = v51;
  v54 = 0;
  v21 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v51 + 80LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  v22 = v21(v20, v57, &v54);
  v10 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x233,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v22,
      v49);
LABEL_38:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
    goto LABEL_39;
  }
  v23 = v52;
  v24 = v54;
  v50[0] = 0;
  v25 = *v52;
  string = 0;
  v26 = WindowsCreateStringReference(L"CurrentlyShownApplicationViewId", 0x1Fu, &hstringHeader, &string);
  if ( v26 < 0 )
  {
    RaiseException(v26, 1u, 0, 0);
    __debugbreak();
  }
  v27 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v25 + 80))(v23, string, v24, v50);
  v10 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x235,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v27,
      v49);
    goto LABEL_38;
  }
  v28 = v53;
  if ( v53 )
  {
    v29 = v52;
    v30 = *v52;
    string = 0;
    v31 = *(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v30 + 80);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ViewSwitcher", 0xDu, 0xCu);
    v32 = v31(v29, string, v28, v50);
    v10 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x239,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
        (const char *)(unsigned int)v32,
        v49);
      goto LABEL_38;
    }
  }
  v33 = v51;
  v55 = 0;
  v34 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v51 + 104LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
  v35 = v34(v33, v60, &v55);
  v10 = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23D,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v35,
      v49);
LABEL_37:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
    goto LABEL_38;
  }
  v36 = v52;
  v37 = v55;
  v38 = *v52;
  string = 0;
  v39 = WindowsCreateStringReference(L"MultiView:AamActivationId", 0x19u, &hstringHeader, &string);
  if ( v39 < 0 )
  {
    RaiseException(v39, 1u, 0, 0);
    __debugbreak();
  }
  v40 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v38 + 80))(v36, string, v37, v50);
  v10 = v40;
  if ( v40 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23E,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v40,
      v49);
    goto LABEL_37;
  }
  v41 = v51;
  v56 = 0;
  v42 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v51 + 136LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
  v10 = v42(v41, BYTE8(v60), &v56);
  if ( v10 < 0 )
  {
    v43 = 577;
LABEL_36:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v43,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v10,
      v49);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
    goto LABEL_37;
  }
  v44 = v52;
  v45 = v56;
  v46 = *v52;
  string = 0;
  v47 = WindowsCreateStringReference(L"IsApplicationMultiviewActivationPolicyEnabled", 0x2Du, &hstringHeader, &string);
  if ( v47 < 0 )
  {
    RaiseException(v47, 1u, 0, 0);
    __debugbreak();
  }
  v10 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v46 + 80))(v44, string, v45, v50);
  if ( v10 < 0 )
  {
    v43 = 578;
    goto LABEL_36;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
  v48 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
  return 0;
}

```

## disassembly

```asm
0x180010b00  mov     [rsp-8+arg_18], rbx
0x180010b05  push    rbp
0x180010b06  push    rsi
0x180010b07  push    rdi
0x180010b08  lea     rbp, [rsp-47h]
0x180010b0d  sub     rsp, 0B0h
0x180010b14  mov     rax, cs:__security_cookie
0x180010b1b  xor     rax, rsp
0x180010b1e  mov     [rbp+57h+var_20], rax
0x180010b22  mov     rdi, rdx
0x180010b25  mov     rsi, rcx
0x180010b28  call    ?MarshalObjectToPropertySet@CActivatedEventArgsBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z; CActivatedEventArgsBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x180010b2d  mov     ebx, eax
0x180010b2f  test    eax, eax
0x180010b31  jns     short loc_180010B52
0x180010b33  mov     rcx, [rbp+5Fh]; this
0x180010b37  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180010b3e  mov     r9d, eax; char *
0x180010b41  mov     edx, 220h; void *
0x180010b46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010b4b  mov     eax, ebx
0x180010b4d  jmp     loc_180011031
0x180010b52  mov     rax, [rdi]
0x180010b55  lea     rcx, [rbp+57h+var_80]
0x180010b59  mov     [rsp+0C0h+arg_10], r14
0x180010b61  xor     r14d, r14d
0x180010b64  mov     [rbp+57h+var_80], r14
0x180010b68  mov     [rbp+57h+var_88], r14
0x180010b6c  mov     rbx, [rax]
0x180010b6f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180010b74  lea     r8, [rbp+57h+var_80]
0x180010b78  mov     rcx, rdi
0x180010b7b  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180010b82  mov     rax, rbx
0x180010b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b8a  mov     ebx, eax
0x180010b8c  test    eax, eax
0x180010b8e  jns     short loc_180010BAD
0x180010b90  mov     rcx, [rbp+5Fh]; this
0x180010b94  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180010b9b  mov     r9d, eax; char *
0x180010b9e  mov     edx, 225h; void *
0x180010ba3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010ba8  jmp     loc_180010FCB
0x180010bad  lea     r9, [rbp+57h+string]; string
0x180010bb1  mov     [rbp+57h+string], r14
0x180010bb5  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180010bb9  mov     edx, 20h ; ' '; length
0x180010bbe  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x180010bc5  call    cs:__imp_WindowsCreateStringReference
0x180010bcb  test    eax, eax
0x180010bcd  jns     short loc_180010BE3
0x180010bcf  xor     r9d, r9d; lpArguments
0x180010bd2  xor     r8d, r8d; nNumberOfArguments
0x180010bd5  mov     edx, 1; dwExceptionFlags
0x180010bda  mov     ecx, eax; dwExceptionCode
0x180010bdc  call    cs:__imp_RaiseException
0x180010be2  int     3; Trap to Debugger
0x180010be3  mov     rbx, [rbp+57h+string]
0x180010be7  lea     rcx, [rbp+57h+var_88]
0x180010beb  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x180010bf0  lea     r8, [rbp+57h+var_88]
0x180010bf4  mov     rcx, rbx
0x180010bf7  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x180010bfe  call    cs:__imp_RoGetActivationFactory
0x180010c04  mov     ebx, eax
0x180010c06  test    eax, eax
0x180010c08  jns     short loc_180010C27
0x180010c0a  mov     rcx, [rbp+5Fh]; this
0x180010c0e  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180010c15  mov     r9d, eax; char *
0x180010c18  mov     edx, 226h; void *
0x180010c1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c22  jmp     loc_180010FCB
0x180010c27  lea     rcx, [rsi+98h]
0x180010c2e  mov     [rbp+57h+var_58], r14d
0x180010c32  mov     rax, [rcx]
0x180010c35  lea     rdx, [rbp+57h+var_58]
0x180010c39  mov     rax, [rax+30h]
0x180010c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c42  mov     ebx, eax
0x180010c44  test    eax, eax
0x180010c46  jns     short loc_180010C65
0x180010c48  mov     rcx, [rbp+5Fh]; this
0x180010c4c  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180010c53  mov     r9d, eax; char *
0x180010c56  mov     edx, 229h; void *
0x180010c5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c60  jmp     loc_180010FCB
0x180010c65  mov     rax, [rsi+0A0h]
0x180010c6c  lea     rcx, [rbp+57h+var_78]
0x180010c70  mov     [rbp+57h+var_78], r14
0x180010c74  mov     rbx, [rax+30h]
0x180010c78  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180010c7d  lea     rdx, [rbp+57h+var_78]
0x180010c81  mov     rax, rbx
0x180010c84  lea     rcx, [rsi+0A0h]
0x180010c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c90  mov     ebx, eax
0x180010c92  test    eax, eax
0x180010c94  jns     short loc_180010CB3
0x180010c96  mov     rcx, [rbp+5Fh]; this
0x180010c9a  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180010ca1  mov     r9d, eax; char *
0x180010ca4  mov     edx, 22Ch; void *
0x180010ca9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010cae  jmp     loc_180010FC2
0x180010cb3  lea     rcx, [rsi+0A8h]
0x180010cba  xorps   xmm0, xmm0
0x180010cbd  mov     rax, [rcx]
0x180010cc0  lea     rdx, [rbp+57h+var_30]
0x180010cc4  movups  [rbp+57h+var_30], xmm0
0x180010cc8  mov     rax, [rax+40h]
0x180010ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cd1  mov     ebx, eax
0x180010cd3  test    eax, eax
0x180010cd5  jns     short loc_180010CF4
0x180010cd7  mov     rcx, [rbp+5Fh]; this
0x180010cdb  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180010ce2  mov     r9d, eax; char *
0x180010ce5  mov     edx, 22Fh; void *
0x180010cea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010cef  jmp     loc_180010FC2
0x180010cf4  mov     rdi, [rbp+57h+var_88]
0x180010cf8  lea     rcx, [rbp+57h+var_70]
0x180010cfc  mov     [rbp+57h+var_70], r14
0x180010d00  mov     rax, [rdi]
0x180010d03  mov     rbx, [rax+50h]
0x180010d07  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180010d0c  mov     edx, [rbp+57h+var_58]
0x180010d0f  lea     r8, [rbp+57h+var_70]
0x180010d13  mov     rcx, rdi
0x180010d16  mov     rax, rbx
0x180010d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d1e  mov     ebx, eax
0x180010d20  test    eax, eax
0x180010d22  jns     short loc_180010D41
0x180010d24  mov     rcx, [rbp+5Fh]; this
0x180010d28  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180010d2f  mov     r9d, eax; char *
0x180010d32  mov     edx, 233h; void *
0x180010d37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010d3c  jmp     loc_180010FB9
0x180010d41  mov     rbx, [rbp+57h+var_80]
0x180010d45  lea     r9, [rbp+57h+string]; string
0x180010d49  mov     rsi, [rbp+57h+var_70]
0x180010d4d  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180010d51  mov     [rbp+57h+var_90], r14b
0x180010d55  lea     rcx, aCurrentlyshown; "CurrentlyShownApplicationViewId"
0x180010d5c  mov     edx, 1Fh; length
0x180010d61  mov     rdi, [rbx]
0x180010d64  mov     [rbp+57h+string], r14
0x180010d68  call    cs:__imp_WindowsCreateStringReference
0x180010d6e  test    eax, eax
0x180010d70  jns     short loc_180010D86
0x180010d72  xor     r9d, r9d; lpArguments
0x180010d75  xor     r8d, r8d; nNumberOfArguments
0x180010d78  mov     edx, 1; dwExceptionFlags
0x180010d7d  mov     ecx, eax; dwExceptionCode
0x180010d7f  call    cs:__imp_RaiseException
0x180010d85  int     3; Trap to Debugger
0x180010d86  mov     rdx, [rbp+57h+string]
0x180010d8a  lea     r9, [rbp+57h+var_90]
0x180010d8e  mov     rax, [rdi+50h]
0x180010d92  mov     r8, rsi
0x180010d95  mov     rcx, rbx
0x180010d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d9d  mov     ebx, eax
0x180010d9f  test    eax, eax
0x180010da1  jns     short loc_180010DC0
0x180010da3  mov     rcx, [rbp+5Fh]; this
0x180010da7  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180010dae  mov     r9d, eax; char *
0x180010db1  mov     edx, 235h; void *
0x180010db6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010dbb  jmp     loc_180010FB9
0x180010dc0  mov     rbx, [rbp+57h+var_78]
0x180010dc4  test    rbx, rbx
0x180010dc7  jz      short loc_180010E2D
0x180010dc9  mov     rsi, [rbp+57h+var_80]
0x180010dcd  lea     rdx, aViewswitcher; "ViewSwitcher"
0x180010dd4  mov     r9d, 0Ch; unsigned int
0x180010dda  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180010dde  mov     r8d, 0Dh; unsigned int
0x180010de4  mov     rax, [rsi]
0x180010de7  mov     [rbp+57h+string], r14
0x180010deb  mov     rdi, [rax+50h]
0x180010def  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180010df4  mov     rdx, [rbp+57h+string]
0x180010df8  lea     r9, [rbp+57h+var_90]
0x180010dfc  mov     r8, rbx
0x180010dff  mov     rcx, rsi
0x180010e02  mov     rax, rdi
0x180010e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e0a  mov     ebx, eax
0x180010e0c  test    eax, eax
0x180010e0e  jns     short loc_180010E2D
0x180010e10  mov     rcx, [rbp+5Fh]; this
0x180010e14  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180010e1b  mov     r9d, eax; char *
0x180010e1e  mov     edx, 239h; void *
0x180010e23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010e28  jmp     loc_180010FB9
0x180010e2d  mov     rdi, [rbp+57h+var_88]
0x180010e31  lea     rcx, [rbp+57h+var_68]
0x180010e35  mov     [rbp+57h+var_68], r14
0x180010e39  mov     rax, [rdi]
0x180010e3c  mov     rbx, [rax+68h]
0x180010e40  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180010e45  mov     rdx, qword ptr [rbp+57h+var_30]
0x180010e49  lea     r8, [rbp+57h+var_68]
0x180010e4d  mov     rcx, rdi
0x180010e50  mov     rax, rbx
0x180010e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e58  mov     ebx, eax
0x180010e5a  test    eax, eax
0x180010e5c  jns     short loc_180010E7B
0x180010e5e  mov     rcx, [rbp+5Fh]; this
0x180010e62  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180010e69  mov     r9d, eax; char *
0x180010e6c  mov     edx, 23Dh; void *
0x180010e71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010e76  jmp     loc_180010FB0
0x180010e7b  mov     rbx, [rbp+57h+var_80]
0x180010e7f  lea     r9, [rbp+57h+string]; string
0x180010e83  mov     rsi, [rbp+57h+var_68]
0x180010e87  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180010e8b  mov     edx, 19h; length
0x180010e90  lea     rcx, aMultiviewAamac; "MultiView:AamActivationId"
0x180010e97  mov     rdi, [rbx]
0x180010e9a  mov     [rbp+57h+string], r14
0x180010e9e  call    cs:__imp_WindowsCreateStringReference
0x180010ea4  test    eax, eax
0x180010ea6  jns     short loc_180010EBC
0x180010ea8  xor     r9d, r9d; lpArguments
0x180010eab  xor     r8d, r8d; nNumberOfArguments
0x180010eae  mov     edx, 1; dwExceptionFlags
0x180010eb3  mov     ecx, eax; dwExceptionCode
0x180010eb5  call    cs:__imp_RaiseException
0x180010ebb  int     3; Trap to Debugger
0x180010ebc  mov     rdx, [rbp+57h+string]
0x180010ec0  lea     r9, [rbp+57h+var_90]
0x180010ec4  mov     rax, [rdi+50h]
0x180010ec8  mov     r8, rsi
0x180010ecb  mov     rcx, rbx
0x180010ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ed3  mov     ebx, eax
0x180010ed5  test    eax, eax
0x180010ed7  jns     short loc_180010EF6
0x180010ed9  mov     rcx, [rbp+5Fh]; this
0x180010edd  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180010ee4  mov     r9d, eax; char *
0x180010ee7  mov     edx, 23Eh; void *
0x180010eec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010ef1  jmp     loc_180010FB0
0x180010ef6  mov     rdi, [rbp+57h+var_88]
0x180010efa  lea     rcx, [rbp+57h+var_60]
0x180010efe  mov     [rbp+57h+var_60], r14
0x180010f02  mov     rax, [rdi]
0x180010f05  mov     rbx, [rax+88h]
0x180010f0c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180010f11  movzx   edx, byte ptr [rbp+57h+var_30+8]
0x180010f15  lea     r8, [rbp+57h+var_60]
0x180010f19  mov     rcx, rdi
0x180010f1c  mov     rax, rbx
0x180010f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f24  mov     ebx, eax
0x180010f26  test    eax, eax
0x180010f28  jns     short loc_180010F31
0x180010f2a  mov     edx, 241h
0x180010f2f  jmp     short loc_180010F94
0x180010f31  mov     rbx, [rbp+57h+var_80]
0x180010f35  lea     r9, [rbp+57h+string]; string
0x180010f39  mov     rsi, [rbp+57h+var_60]
0x180010f3d  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180010f41  mov     edx, 2Dh ; '-'; length
0x180010f46  lea     rcx, aIsapplicationm; "IsApplicationMultiviewActivationPolicyE"...
0x180010f4d  mov     rdi, [rbx]
0x180010f50  mov     [rbp+57h+string], r14
0x180010f54  call    cs:__imp_WindowsCreateStringReference
0x180010f5a  test    eax, eax
0x180010f5c  jns     short loc_180010F72
0x180010f5e  xor     r9d, r9d; lpArguments
0x180010f61  xor     r8d, r8d; nNumberOfArguments
0x180010f64  mov     edx, 1; dwExceptionFlags
0x180010f69  mov     ecx, eax; dwExceptionCode
0x180010f6b  call    cs:__imp_RaiseException
0x180010f71  int     3; Trap to Debugger
0x180010f72  mov     rdx, [rbp+57h+string]
0x180010f76  lea     r9, [rbp+57h+var_90]
0x180010f7a  mov     rax, [rdi+50h]
0x180010f7e  mov     r8, rsi
0x180010f81  mov     rcx, rbx
0x180010f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f89  mov     ebx, eax
0x180010f8b  test    eax, eax
0x180010f8d  jns     short loc_180010FE1
0x180010f8f  mov     edx, 242h; void *
0x180010f94  mov     rcx, [rbp+5Fh]; this
0x180010f98  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
  ... truncated ...
```
