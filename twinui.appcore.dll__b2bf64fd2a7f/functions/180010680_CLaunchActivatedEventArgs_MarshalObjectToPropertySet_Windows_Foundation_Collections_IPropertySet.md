# CLaunchActivatedEventArgs::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x180010680`
- end: `0x180010af7`
- name: `?MarshalObjectToPropertySet@CLaunchActivatedEventArgs@@UEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1143`
- prototype: `__int64 __fastcall(CLaunchActivatedEventArgs *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180003d24`
- `0x1800083f0`
- `0x180010680`
- `0x180011c6c`
- `0x18001cc38`
- `0x180022fb4`
- `0x18002b1b0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010749`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010749`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800107a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800107e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010819`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010a59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010a67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010aa7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010ab5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800107a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800107e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010819`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010a59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010a67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010aa7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010ab5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010733`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010733`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001076b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001076b`

## pseudocode

```c
__int64 __fastcall CLaunchActivatedEventArgs::MarshalObjectToPropertySet(
        CLaunchActivatedEventArgs *this,
        struct Windows::Foundation::Collections::IPropertySet *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 (__fastcall **v7)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rax
  __int64 (__fastcall *v8)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rbx
  int ActivationFactory; // eax
  __int64 v10; // rdx
  HRESULT v11; // eax
  HSTRING v12; // rbx
  __int64 (__fastcall *v13)(char *, HSTRING *); // rbx
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 (__fastcall *v17)(char *, HSTRING *); // rbx
  int v18; // eax
  __int64 v19; // rax
  __int64 (__fastcall *v20)(char *, __int64 *); // rbx
  int v21; // eax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, HSTRING, __int64 *); // rbx
  int v24; // eax
  __int64 v25; // rdx
  _QWORD *v26; // rsi
  __int64 v27; // rbx
  __int64 v28; // rax
  __int64 (__fastcall *v29)(_QWORD *, HSTRING, __int64, _BYTE *); // rdi
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, HSTRING, __int64 *); // rbx
  int v32; // eax
  __int64 v33; // rdx
  _QWORD *v34; // rsi
  __int64 v35; // rbx
  __int64 v36; // rax
  __int64 (__fastcall *v37)(_QWORD *, HSTRING, __int64, _BYTE *); // rdi
  __int64 v38; // rbx
  _QWORD *v39; // rsi
  __int64 v40; // rax
  __int64 (__fastcall *v41)(_QWORD *, HSTRING, __int64, _BYTE *); // rdi
  int v42; // [rsp+20h] [rbp-39h]
  _BYTE v43[8]; // [rsp+30h] [rbp-29h] BYREF
  HSTRING v44; // [rsp+38h] [rbp-21h] BYREF
  HSTRING v45; // [rsp+40h] [rbp-19h] BYREF
  __int64 v46; // [rsp+48h] [rbp-11h] BYREF
  __int64 v47; // [rsp+50h] [rbp-9h] BYREF
  __int64 v48; // [rsp+58h] [rbp-1h] BYREF
  __int64 v49; // [rsp+60h] [rbp+7h] BYREF
  _QWORD *v50; // [rsp+68h] [rbp+Fh] BYREF
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
      v42);
    return v5;
  }
  v7 = *(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **))a2;
  v50 = 0;
  v48 = 0;
  v8 = *v7;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  ActivationFactory = v8(a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v50);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v10 = 105;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v42);
LABEL_34:
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v48);
LABEL_35:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    return v5;
  }
  string = 0;
  v11 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v12 = string;
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v48);
  ActivationFactory = RoGetActivationFactory(v12, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v48);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v10 = 106;
    goto LABEL_10;
  }
  v44 = 0;
  v13 = *(__int64 (__fastcall **)(char *, HSTRING *))(*((_QWORD *)this - 2) + 48LL);
  WindowsDeleteString(0);
  v44 = 0;
  v14 = v13((char *)this - 16, &v44);
  v5 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v14,
      v42);
    WindowsDeleteString(v44);
    v15 = v48;
    v44 = 0;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    goto LABEL_35;
  }
  v16 = *((_QWORD *)this - 2);
  v45 = 0;
  v17 = *(__int64 (__fastcall **)(char *, HSTRING *))(v16 + 56);
  WindowsDeleteString(0);
  v45 = 0;
  v18 = v17((char *)this - 16, &v45);
  v5 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x71,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v18,
      v42);
LABEL_33:
    WindowsDeleteString(v45);
    v45 = 0;
    WindowsDeleteString(v44);
    v44 = 0;
    goto LABEL_34;
  }
  v19 = *((_QWORD *)this - 1);
  v46 = 0;
  v20 = *(__int64 (__fastcall **)(char *, __int64 *))(v19 + 48);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  v21 = v20((char *)this - 8, &v46);
  v5 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v21,
      v42);
LABEL_32:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    goto LABEL_33;
  }
  v22 = v48;
  v47 = 0;
  v23 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v48 + 144LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  v24 = v23(v22, v44, &v47);
  v5 = v24;
  if ( v24 < 0 )
  {
    v25 = 120;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v24,
      v42);
LABEL_31:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    goto LABEL_32;
  }
  v26 = v50;
  v27 = v47;
  v43[0] = 0;
  v28 = *v50;
  string = 0;
  v29 = *(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v28 + 80);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Arguments", 0xAu, 9u);
  v24 = v29(v26, string, v27, v43);
  v5 = v24;
  if ( v24 < 0 )
  {
    v25 = 122;
    goto LABEL_20;
  }
  v30 = v48;
  v49 = 0;
  v31 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v48 + 144LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  v32 = v31(v30, v45, &v49);
  v5 = v32;
  if ( v32 < 0 )
  {
    v33 = 125;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v33,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v32,
      v42);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    goto LABEL_31;
  }
  v34 = v50;
  v35 = v49;
  v36 = *v50;
  string = 0;
  v37 = *(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v36 + 80);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"TileId", 7u, 6u);
  v32 = v37(v34, string, v35, v43);
  v5 = v32;
  if ( v32 < 0 )
  {
    v33 = 126;
    goto LABEL_30;
  }
  v38 = v46;
  if ( v46 )
  {
    v39 = v50;
    v40 = *v50;
    string = 0;
    v41 = *(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v40 + 80);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"TileActivatedInfo", 0x12u, 0x11u);
    v32 = v41(v39, string, v38, v43);
    v5 = v32;
    if ( v32 < 0 )
    {
      v33 = 130;
      goto LABEL_30;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  WindowsDeleteString(v45);
  v45 = 0;
  WindowsDeleteString(v44);
  v44 = 0;
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v48);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  return 0;
}

```

## disassembly

```asm
0x180010680  mov     [rsp-8+arg_10], rbx
0x180010685  mov     [rsp-8+arg_18], rsi
0x18001068a  push    rbp
0x18001068b  push    rdi
0x18001068c  push    r14
0x18001068e  lea     rbp, [rsp-47h]
0x180010693  sub     rsp, 0A0h
0x18001069a  mov     rax, cs:__security_cookie
0x1800106a1  xor     rax, rsp
0x1800106a4  mov     [rbp+57h+var_20], rax
0x1800106a8  mov     rsi, rcx
0x1800106ab  mov     rdi, rdx
0x1800106ae  add     rcx, 0FFFFFFFFFFFFFF00h; this
0x1800106b5  call    ?MarshalObjectToPropertySet@CActivatedEventArgsWithPrelaunchAndViewIdBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z; CActivatedEventArgsWithPrelaunchAndViewIdBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x1800106ba  xor     r14d, r14d
0x1800106bd  mov     ebx, eax
0x1800106bf  test    eax, eax
0x1800106c1  jns     short loc_1800106E1
0x1800106c3  mov     rcx, [rbp+5Fh]; this
0x1800106c7  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\lib\\activationevent"...
0x1800106ce  mov     r9d, eax; char *
0x1800106d1  lea     edx, [r14+64h]; void *
0x1800106d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800106da  mov     eax, ebx
0x1800106dc  jmp     loc_180010AD3
0x1800106e1  mov     rax, [rdi]
0x1800106e4  lea     rcx, [rbp+57h+var_48]
0x1800106e8  mov     [rbp+57h+var_48], r14
0x1800106ec  mov     [rbp+57h+var_58], r14
0x1800106f0  mov     rbx, [rax]
0x1800106f3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800106f8  lea     r8, [rbp+57h+var_48]
0x1800106fc  mov     rcx, rdi
0x1800106ff  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180010706  mov     rax, rbx
0x180010709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001070e  mov     ebx, eax
0x180010710  test    eax, eax
0x180010712  jns     short loc_18001071B
0x180010714  mov     edx, 69h ; 'i'
0x180010719  jmp     short loc_18001077C
0x18001071b  lea     r9, [rbp+57h+string]; string
0x18001071f  mov     [rbp+57h+string], r14
0x180010723  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180010727  mov     edx, 20h ; ' '; length
0x18001072c  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x180010733  call    cs:__imp_WindowsCreateStringReference
0x180010739  test    eax, eax
0x18001073b  jns     short loc_180010750
0x18001073d  xor     r9d, r9d; lpArguments
0x180010740  xor     r8d, r8d; nNumberOfArguments
0x180010743  mov     ecx, eax; dwExceptionCode
0x180010745  lea     edx, [r9+1]; dwExceptionFlags
0x180010749  call    cs:__imp_RaiseException
0x18001074f  int     3; Trap to Debugger
0x180010750  mov     rbx, [rbp+57h+string]
0x180010754  lea     rcx, [rbp+57h+var_58]
0x180010758  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18001075d  lea     r8, [rbp+57h+var_58]
0x180010761  mov     rcx, rbx
0x180010764  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x18001076b  call    cs:__imp_RoGetActivationFactory
0x180010771  mov     ebx, eax
0x180010773  test    eax, eax
0x180010775  jns     short loc_180010794
0x180010777  mov     edx, 6Ah ; 'j'; void *
0x18001077c  mov     rcx, [rbp+5Fh]; this
0x180010780  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\lib\\activationevent"...
0x180010787  mov     r9d, eax; char *
0x18001078a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001078f  jmp     loc_180010A71
0x180010794  lea     rdi, [rsi-10h]
0x180010798  mov     [rbp+57h+var_78], r14
0x18001079c  mov     rax, [rdi]
0x18001079f  xor     ecx, ecx; string
0x1800107a1  mov     rbx, [rax+30h]
0x1800107a5  call    cs:__imp_WindowsDeleteString
0x1800107ab  lea     rdx, [rbp+57h+var_78]
0x1800107af  mov     [rbp+57h+var_78], r14
0x1800107b3  mov     rcx, rdi
0x1800107b6  mov     rax, rbx
0x1800107b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107be  mov     ebx, eax
0x1800107c0  test    eax, eax
0x1800107c2  jns     short loc_18001080C
0x1800107c4  mov     rcx, [rbp+5Fh]; this
0x1800107c8  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\lib\\activationevent"...
0x1800107cf  mov     r9d, eax; char *
0x1800107d2  mov     edx, 6Eh ; 'n'; void *
0x1800107d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800107dc  mov     rcx, [rbp+57h+var_78]; string
0x1800107e0  call    cs:__imp_WindowsDeleteString
0x1800107e6  mov     rcx, [rbp+57h+var_58]
0x1800107ea  mov     [rbp+57h+var_78], r14
0x1800107ee  test    rcx, rcx
0x1800107f1  jz      loc_180010A7A
0x1800107f7  mov     [rbp+57h+var_58], r14
0x1800107fb  mov     rax, [rcx]
0x1800107fe  mov     rax, [rax+10h]
0x180010802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010807  jmp     loc_180010A7A
0x18001080c  mov     rax, [rdi]
0x18001080f  xor     ecx, ecx; string
0x180010811  mov     [rbp+57h+var_70], r14
0x180010815  mov     rbx, [rax+38h]
0x180010819  call    cs:__imp_WindowsDeleteString
0x18001081f  lea     rdx, [rbp+57h+var_70]
0x180010823  mov     [rbp+57h+var_70], r14
0x180010827  mov     rcx, rdi
0x18001082a  mov     rax, rbx
0x18001082d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010832  mov     ebx, eax
0x180010834  test    eax, eax
0x180010836  jns     short loc_180010855
0x180010838  mov     rcx, [rbp+5Fh]; this
0x18001083c  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\lib\\activationevent"...
0x180010843  mov     r9d, eax; char *
0x180010846  mov     edx, 71h ; 'q'; void *
0x18001084b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010850  jmp     loc_180010A55
0x180010855  mov     rax, [rsi-8]
0x180010859  lea     rcx, [rbp+57h+var_68]
0x18001085d  mov     [rbp+57h+var_68], r14
0x180010861  mov     rbx, [rax+30h]
0x180010865  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001086a  lea     rdx, [rbp+57h+var_68]
0x18001086e  mov     rax, rbx
0x180010871  lea     rcx, [rsi-8]
0x180010875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001087a  mov     ebx, eax
0x18001087c  test    eax, eax
0x18001087e  jns     short loc_18001089D
0x180010880  mov     rcx, [rbp+5Fh]; this
0x180010884  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\lib\\activationevent"...
0x18001088b  mov     r9d, eax; char *
0x18001088e  mov     edx, 74h ; 't'; void *
0x180010893  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010898  jmp     loc_180010A4C
0x18001089d  mov     rdi, [rbp+57h+var_58]
0x1800108a1  lea     rcx, [rbp+57h+var_60]
0x1800108a5  mov     [rbp+57h+var_60], r14
0x1800108a9  mov     rax, [rdi]
0x1800108ac  mov     rbx, [rax+90h]
0x1800108b3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800108b8  mov     rdx, [rbp+57h+var_78]
0x1800108bc  lea     r8, [rbp+57h+var_60]
0x1800108c0  mov     rcx, rdi
0x1800108c3  mov     rax, rbx
0x1800108c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108cb  mov     ebx, eax
0x1800108cd  test    eax, eax
0x1800108cf  jns     short loc_1800108EE
0x1800108d1  mov     edx, 78h ; 'x'; void *
0x1800108d6  mov     rcx, [rbp+5Fh]; this
0x1800108da  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\lib\\activationevent"...
0x1800108e1  mov     r9d, eax; char *
0x1800108e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800108e9  jmp     loc_180010A43
0x1800108ee  mov     rsi, [rbp+57h+var_48]
0x1800108f2  lea     rdx, aArguments; "Arguments"
0x1800108f9  mov     rbx, [rbp+57h+var_60]
0x1800108fd  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180010901  mov     [rbp+57h+var_80], r14b
0x180010905  mov     r9d, 9; unsigned int
0x18001090b  mov     rax, [rsi]
0x18001090e  mov     [rbp+57h+string], r14
0x180010912  lea     r8d, [r9+1]; unsigned int
0x180010916  mov     rdi, [rax+50h]
0x18001091a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001091f  mov     rdx, [rbp+57h+string]
0x180010923  lea     r9, [rbp+57h+var_80]
0x180010927  mov     r8, rbx
0x18001092a  mov     rcx, rsi
0x18001092d  mov     rax, rdi
0x180010930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010935  mov     ebx, eax
0x180010937  test    eax, eax
0x180010939  jns     short loc_180010942
0x18001093b  mov     edx, 7Ah ; 'z'
0x180010940  jmp     short loc_1800108D6
0x180010942  mov     rdi, [rbp+57h+var_58]
0x180010946  lea     rcx, [rbp+57h+var_50]
0x18001094a  mov     [rbp+57h+var_50], r14
0x18001094e  mov     rax, [rdi]
0x180010951  mov     rbx, [rax+90h]
0x180010958  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001095d  mov     rdx, [rbp+57h+var_70]
0x180010961  lea     r8, [rbp+57h+var_50]
0x180010965  mov     rcx, rdi
0x180010968  mov     rax, rbx
0x18001096b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010970  mov     ebx, eax
0x180010972  test    eax, eax
0x180010974  jns     short loc_180010980
0x180010976  mov     edx, 7Dh ; '}'
0x18001097b  jmp     loc_180010A27
0x180010980  mov     rsi, [rbp+57h+var_48]
0x180010984  lea     rdx, aTileid; "TileId"
0x18001098b  mov     rbx, [rbp+57h+var_50]
0x18001098f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180010993  mov     r9d, 6; unsigned int
0x180010999  mov     rax, [rsi]
0x18001099c  mov     [rbp+57h+string], r14
0x1800109a0  lea     r8d, [r9+1]; unsigned int
0x1800109a4  mov     rdi, [rax+50h]
0x1800109a8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800109ad  mov     rdx, [rbp+57h+string]
0x1800109b1  lea     r9, [rbp+57h+var_80]
0x1800109b5  mov     r8, rbx
0x1800109b8  mov     rcx, rsi
0x1800109bb  mov     rax, rdi
0x1800109be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109c3  mov     ebx, eax
0x1800109c5  test    eax, eax
0x1800109c7  jns     short loc_1800109D0
0x1800109c9  mov     edx, 7Eh ; '~'
0x1800109ce  jmp     short loc_180010A27
0x1800109d0  mov     rbx, [rbp+57h+var_68]
0x1800109d4  test    rbx, rbx
0x1800109d7  jz      loc_180010A88
0x1800109dd  mov     rsi, [rbp+57h+var_48]
0x1800109e1  lea     rdx, aTileactivatedi; "TileActivatedInfo"
0x1800109e8  mov     r9d, 11h; unsigned int
0x1800109ee  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800109f2  mov     rax, [rsi]
0x1800109f5  lea     r8d, [r9+1]; unsigned int
0x1800109f9  mov     [rbp+57h+string], r14
0x1800109fd  mov     rdi, [rax+50h]
0x180010a01  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180010a06  mov     rdx, [rbp+57h+string]
0x180010a0a  lea     r9, [rbp+57h+var_80]
0x180010a0e  mov     r8, rbx
0x180010a11  mov     rcx, rsi
0x180010a14  mov     rax, rdi
0x180010a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a1c  mov     ebx, eax
0x180010a1e  test    eax, eax
0x180010a20  jns     short loc_180010A88
0x180010a22  mov     edx, 82h; void *
0x180010a27  mov     rcx, [rbp+5Fh]; this
0x180010a2b  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\lib\\activationevent"...
0x180010a32  mov     r9d, eax; char *
0x180010a35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010a3a  lea     rcx, [rbp+57h+var_50]
0x180010a3e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180010a43  lea     rcx, [rbp+57h+var_60]
0x180010a47  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180010a4c  lea     rcx, [rbp+57h+var_68]
0x180010a50  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180010a55  mov     rcx, [rbp+57h+var_70]; string
0x180010a59  call    cs:__imp_WindowsDeleteString
0x180010a5f  mov     rcx, [rbp+57h+var_78]; string
0x180010a63  mov     [rbp+57h+var_70], r14
0x180010a67  call    cs:__imp_WindowsDeleteString
0x180010a6d  mov     [rbp+57h+var_78], r14
0x180010a71  lea     rcx, [rbp+57h+var_58]
0x180010a75  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x180010a7a  lea     rcx, [rbp+57h+var_48]
0x180010a7e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180010a83  jmp     loc_1800106DA
0x180010a88  lea     rcx, [rbp+57h+var_50]
0x180010a8c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180010a91  lea     rcx, [rbp+57h+var_60]
0x180010a95  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180010a9a  lea     rcx, [rbp+57h+var_68]
0x180010a9e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180010aa3  mov     rcx, [rbp+57h+var_70]; string
0x180010aa7  call    cs:__imp_WindowsDeleteString
0x180010aad  mov     rcx, [rbp+57h+var_78]; string
0x180010ab1  mov     [rbp+57h+var_70], r14
0x180010ab5  call    cs:__imp_WindowsDeleteString
0x180010abb  lea     rcx, [rbp+57h+var_58]
0x180010abf  mov     [rbp+57h+var_78], r14
0x180010ac3  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x180010ac8  lea     rcx, [rbp+57h+var_48]
0x180010acc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180010ad1  xor     eax, eax
0x180010ad3  mov     rcx, [rbp+57h+var_20]
0x180010ad7  xor     rcx, rsp; StackCookie
0x180010ada  call    __security_check_cookie
0x180010adf  lea     r11, [rsp+0B0h+var_10]
0x180010ae7  mov     rbx, [r11+30h]
0x180010aeb  mov     rsi, [r11+38h]
0x180010aef  mov     rsp, r11
0x180010af2  pop     r14
0x180010af4  pop     rdi
0x180010af5  pop     rbp
0x180010af6  retn
```
