# CActivatedEventArgsWithViewIdBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x180046dc4`
- end: `0x18004726f`
- name: `?MarshalObjectToPropertySet@CActivatedEventArgsWithViewIdBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1195`
- prototype: `__int64 __fastcall(CActivatedEventArgsWithViewIdBase *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18019b00c`
- `0x1806698c0`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x180046040`
- `0x180046dc4`
- `0x18007b3e0`
- `0x180356360`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180047214`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180047238`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004724b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180047268`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180047214`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180047238`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004724b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180047268`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180046e52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180046f66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180046ffa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180047122`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180046e52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180046f66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180046ffa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180047122`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180046e7b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180046e7b`

## pseudocode

```c
__int64 __fastcall CActivatedEventArgsWithViewIdBase::MarshalObjectToPropertySet(
        RTL_SRWLOCK *this,
        __int64 (__fastcall ***a2)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 **))
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 (__fastcall **v6)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 **); // rax
  __int64 (__fastcall *v7)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 **); // rbx
  int ActivationFactory; // eax
  HRESULT v9; // eax
  HSTRING v10; // rbx
  __int64 (__fastcall *v11)(RTL_SRWLOCK *, __int64 *); // rbx
  int v12; // eax
  __int64 (__fastcall **Ptr)(RTL_SRWLOCK *, _OWORD *); // rax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  int v16; // eax
  _QWORD *v17; // rbx
  __int64 v18; // rsi
  __int64 v19; // rdi
  HRESULT v20; // eax
  __int64 v21; // rbx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, _QWORD, __int64 *); // rbx
  int v24; // eax
  _QWORD *v25; // rbx
  __int64 v26; // rsi
  __int64 v27; // rdi
  HRESULT v28; // eax
  __int64 v29; // rdx
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, __int64, __int64 *); // rbx
  __int64 v35; // rdx
  int v36; // eax
  _QWORD *v37; // rbx
  __int64 v38; // rsi
  __int64 v39; // rdi
  HRESULT v40; // eax
  __int64 v41; // rdx
  __int64 v42; // rdx
  _QWORD *v43; // rsi
  __int64 v44; // rax
  __int64 (__fastcall *v45)(_QWORD *, HSTRING, __int64, char *); // rdi
  int v46; // [rsp+20h] [rbp-49h]
  char v47[8]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v48; // [rsp+38h] [rbp-31h] BYREF
  __int64 v49; // [rsp+40h] [rbp-29h] BYREF
  __int64 v50; // [rsp+48h] [rbp-21h] BYREF
  _QWORD *v51; // [rsp+50h] [rbp-19h] BYREF
  __int64 v52; // [rsp+58h] [rbp-11h] BYREF
  __int64 v53; // [rsp+60h] [rbp-9h] BYREF
  unsigned int v54; // [rsp+68h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+7h] BYREF
  HSTRING string; // [rsp+88h] [rbp+1Fh] BYREF
  __int128 v57; // [rsp+90h] [rbp+27h] BYREF
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
      v46);
    return v5;
  }
  v6 = *a2;
  v51 = 0;
  v52 = 0;
  v7 = *v6;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
  ActivationFactory = v7(
                        (struct Windows::Foundation::Collections::IPropertySet *)a2,
                        &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
                        &v51);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v32 = 549;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v32,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v46);
    goto LABEL_20;
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
    v32 = 550;
    goto LABEL_25;
  }
  v54 = 0;
  ActivationFactory = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, unsigned int *))this[19].Ptr + 6))(this + 19, &v54);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v32 = 553;
    goto LABEL_25;
  }
  v48 = 0;
  v11 = (__int64 (__fastcall *)(RTL_SRWLOCK *, __int64 *))*((_QWORD *)this[20].Ptr + 6);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
  v12 = v11(this + 20, &v48);
  v5 = v12;
  if ( v12 < 0 )
  {
    v42 = 556;
LABEL_35:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v42,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v12,
      v46);
    goto LABEL_19;
  }
  Ptr = (__int64 (__fastcall **)(RTL_SRWLOCK *, _OWORD *))this[21].Ptr;
  v57 = 0;
  v12 = Ptr[8](this + 21, &v57);
  v5 = v12;
  if ( v12 < 0 )
  {
    v42 = 559;
    goto LABEL_35;
  }
  v14 = v52;
  v49 = 0;
  v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v52 + 80LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  v16 = v15(v14, v54, &v49);
  v5 = v16;
  if ( v16 < 0 )
  {
    v31 = 563;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v16,
      v46);
    goto LABEL_18;
  }
  v17 = v51;
  v18 = v49;
  v47[0] = 0;
  v19 = *v51;
  string = 0;
  v20 = WindowsCreateStringReference(L"CurrentlyShownApplicationViewId", 0x1Fu, &hstringHeader, &string);
  if ( v20 < 0 )
  {
    RaiseException(v20, 1u, 0, 0);
    __debugbreak();
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, char *))(v19 + 80))(v17, string, v18, v47);
  v5 = v16;
  if ( v16 < 0 )
  {
    v31 = 565;
    goto LABEL_23;
  }
  v21 = v48;
  if ( v48 )
  {
    v43 = v51;
    v44 = *v51;
    string = 0;
    v45 = *(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, char *))(v44 + 80);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ViewSwitcher", 0xDu, 0xCu);
    v16 = v45(v43, string, v21, v47);
    v5 = v16;
    if ( v16 < 0 )
    {
      v31 = 569;
      goto LABEL_23;
    }
  }
  v22 = v52;
  v50 = 0;
  v23 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v52 + 104LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  v24 = v23(v22, v57, &v50);
  v5 = v24;
  if ( v24 < 0 )
  {
    v29 = 573;
    goto LABEL_16;
  }
  v25 = v51;
  v26 = v50;
  v27 = *v51;
  string = 0;
  v28 = WindowsCreateStringReference(L"MultiView:AamActivationId", 0x19u, &hstringHeader, &string);
  if ( v28 < 0 )
  {
    RaiseException(v28, 1u, 0, 0);
    __debugbreak();
  }
  v24 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, char *))(v27 + 80))(v25, string, v26, v47);
  v5 = v24;
  if ( v24 < 0 )
  {
    v29 = 574;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v24,
      v46);
LABEL_17:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
LABEL_18:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
LABEL_19:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
LABEL_20:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    return v5;
  }
  v33 = v52;
  v53 = 0;
  v34 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v52 + 136LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
  LOBYTE(v35) = BYTE8(v57);
  v36 = v34(v33, v35, &v53);
  v5 = v36;
  if ( v36 < 0 )
  {
    v41 = 577;
    goto LABEL_30;
  }
  v37 = v51;
  v38 = v53;
  v39 = *v51;
  string = 0;
  v40 = WindowsCreateStringReference(L"IsApplicationMultiviewActivationPolicyEnabled", 0x2Du, &hstringHeader, &string);
  if ( v40 < 0 )
  {
    RaiseException(v40, 1u, 0, 0);
    JUMPOUT(0x18004726ELL);
  }
  v36 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, char *))(v39 + 80))(v37, string, v38, v47);
  v5 = v36;
  if ( v36 < 0 )
  {
    v41 = 578;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v41,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v36,
      v46);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
    goto LABEL_17;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
  return 0;
}

```

## disassembly

```asm
0x180046dc4  mov     [rsp-8+arg_10], rbx
0x180046dc9  mov     [rsp-8+arg_18], rsi
0x180046dce  push    rbp
0x180046dcf  push    rdi
0x180046dd0  push    r14
0x180046dd2  lea     rbp, [rsp-47h]
0x180046dd7  sub     rsp, 0B0h
0x180046dde  mov     rax, cs:__security_cookie
0x180046de5  xor     rax, rsp
0x180046de8  mov     [rbp+57h+var_20], rax
0x180046dec  mov     rdi, rdx
0x180046def  mov     rsi, rcx
0x180046df2  call    ?MarshalObjectToPropertySet@CActivatedEventArgsBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z; CActivatedEventArgsBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x180046df7  xor     r14d, r14d
0x180046dfa  mov     ebx, eax
0x180046dfc  test    eax, eax
0x180046dfe  js      loc_1800471EB
0x180046e04  mov     rax, [rdi]
0x180046e07  lea     rcx, [rbp+57h+var_70]
0x180046e0b  mov     [rbp+57h+var_70], r14
0x180046e0f  mov     [rbp+57h+var_68], r14
0x180046e13  mov     rbx, [rax]
0x180046e16  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046e1b  lea     r8, [rbp+57h+var_70]
0x180046e1f  mov     rcx, rdi
0x180046e22  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180046e29  mov     rax, rbx
0x180046e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046e31  mov     ebx, eax
0x180046e33  test    eax, eax
0x180046e35  js      loc_1800470AE
0x180046e3b  lea     r9, [rbp+57h+string]; string
0x180046e3f  mov     [rbp+57h+string], r14
0x180046e43  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180046e47  lea     edx, [r14+20h]; length
0x180046e4b  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x180046e52  call    cs:__imp_WindowsCreateStringReference
0x180046e58  test    eax, eax
0x180046e5a  js      loc_180047208
0x180046e60  mov     rbx, [rbp+57h+string]
0x180046e64  lea     rcx, [rbp+57h+var_68]
0x180046e68  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046e6d  lea     r8, [rbp+57h+var_68]
0x180046e71  mov     rcx, rbx
0x180046e74  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x180046e7b  call    cs:__imp_RoGetActivationFactory
0x180046e81  mov     ebx, eax
0x180046e83  test    eax, eax
0x180046e85  js      loc_18004721B
0x180046e8b  lea     rcx, [rsi+98h]
0x180046e92  mov     [rbp+57h+var_58], r14d
0x180046e96  mov     rax, [rcx]
0x180046e99  lea     rdx, [rbp+57h+var_58]
0x180046e9d  mov     rax, [rax+30h]
0x180046ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ea6  mov     ebx, eax
0x180046ea8  test    eax, eax
0x180046eaa  js      loc_18004717D
0x180046eb0  lea     rdi, [rsi+0A0h]
0x180046eb7  mov     [rbp+57h+var_88], r14
0x180046ebb  mov     rax, [rdi]
0x180046ebe  lea     rcx, [rbp+57h+var_88]
0x180046ec2  mov     rbx, [rax+30h]
0x180046ec6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046ecb  lea     rdx, [rbp+57h+var_88]
0x180046ecf  mov     rcx, rdi
0x180046ed2  mov     rax, rbx
0x180046ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046eda  mov     ebx, eax
0x180046edc  test    eax, eax
0x180046ede  js      loc_1800471C4
0x180046ee4  lea     rcx, [rsi+0A8h]
0x180046eeb  xorps   xmm0, xmm0
0x180046eee  mov     rax, [rcx]
0x180046ef1  lea     rdx, [rbp+57h+var_30]
0x180046ef5  movups  [rbp+57h+var_30], xmm0
0x180046ef9  mov     rax, [rax+40h]
0x180046efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f02  mov     ebx, eax
0x180046f04  test    eax, eax
0x180046f06  js      loc_180047225
0x180046f0c  mov     rdi, [rbp+57h+var_68]
0x180046f10  lea     rcx, [rbp+57h+var_80]
0x180046f14  mov     [rbp+57h+var_80], r14
0x180046f18  mov     rax, [rdi]
0x180046f1b  mov     rbx, [rax+50h]
0x180046f1f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046f24  mov     edx, [rbp+57h+var_58]
0x180046f27  lea     r8, [rbp+57h+var_80]
0x180046f2b  mov     rcx, rdi
0x180046f2e  mov     rax, rbx
0x180046f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f36  mov     ebx, eax
0x180046f38  test    eax, eax
0x180046f3a  js      loc_180047094
0x180046f40  mov     rbx, [rbp+57h+var_70]
0x180046f44  lea     r9, [rbp+57h+string]; string
0x180046f48  mov     rsi, [rbp+57h+var_80]
0x180046f4c  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180046f50  mov     [rbp+57h+var_90], r14b
0x180046f54  lea     edx, [r14+1Fh]; length
0x180046f58  lea     rcx, aCurrentlyshown; "CurrentlyShownApplicationViewId"
0x180046f5f  mov     rdi, [rbx]
0x180046f62  mov     [rbp+57h+string], r14
0x180046f66  call    cs:__imp_WindowsCreateStringReference
0x180046f6c  test    eax, eax
0x180046f6e  js      loc_18004722C
0x180046f74  mov     rdx, [rbp+57h+string]
0x180046f78  lea     r9, [rbp+57h+var_90]
0x180046f7c  mov     rax, [rdi+50h]
0x180046f80  mov     r8, rsi
0x180046f83  mov     rcx, rbx
0x180046f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f8b  mov     ebx, eax
0x180046f8d  test    eax, eax
0x180046f8f  js      loc_180047173
0x180046f95  mov     rbx, [rbp+57h+var_88]
0x180046f99  test    rbx, rbx
0x180046f9c  jnz     loc_1806EDA56
0x180046fa2  mov     rdi, [rbp+57h+var_68]
0x180046fa6  lea     rcx, [rbp+57h+var_78]
0x180046faa  mov     [rbp+57h+var_78], r14
0x180046fae  mov     rax, [rdi]
0x180046fb1  mov     rbx, [rax+68h]
0x180046fb5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046fba  mov     rdx, qword ptr [rbp+57h+var_30]
0x180046fbe  lea     r8, [rbp+57h+var_78]
0x180046fc2  mov     rcx, rdi
0x180046fc5  mov     rax, rbx
0x180046fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046fcd  mov     ebx, eax
0x180046fcf  test    eax, eax
0x180046fd1  js      loc_1800471E1
0x180046fd7  mov     rbx, [rbp+57h+var_70]
0x180046fdb  lea     r9, [rbp+57h+string]; string
0x180046fdf  mov     rsi, [rbp+57h+var_78]
0x180046fe3  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180046fe7  mov     edx, 19h; length
0x180046fec  lea     rcx, aMultiviewAamac; "MultiView:AamActivationId"
0x180046ff3  mov     rdi, [rbx]
0x180046ff6  mov     [rbp+57h+string], r14
0x180046ffa  call    cs:__imp_WindowsCreateStringReference
0x180047000  test    eax, eax
0x180047002  js      loc_18004723F
0x180047008  mov     rdx, [rbp+57h+string]
0x18004700c  lea     r9, [rbp+57h+var_90]
0x180047010  mov     rax, [rdi+50h]
0x180047014  mov     r8, rsi
0x180047017  mov     rcx, rbx
0x18004701a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004701f  mov     ebx, eax
0x180047021  test    eax, eax
0x180047023  jns     loc_1800470C8
0x180047029  mov     edx, 23Eh; void *
0x18004702e  mov     rcx, [rbp+5Fh]; this
0x180047032  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180047039  mov     r9d, eax; char *
0x18004703c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047041  lea     rcx, [rbp+57h+var_78]
0x180047045  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004704a  lea     rcx, [rbp+57h+var_80]
0x18004704e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180047053  lea     rcx, [rbp+57h+var_88]
0x180047057  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004705c  lea     rcx, [rbp+57h+var_68]
0x180047060  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180047065  lea     rcx, [rbp+57h+var_70]
0x180047069  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004706e  mov     eax, ebx
0x180047070  mov     rcx, [rbp+57h+var_20]
0x180047074  xor     rcx, rsp; StackCookie
0x180047077  call    __security_check_cookie
0x18004707c  lea     r11, [rsp+0C0h+var_10]
0x180047084  mov     rbx, [r11+30h]
0x180047088  mov     rsi, [r11+38h]
0x18004708c  mov     rsp, r11
0x18004708f  pop     r14
0x180047091  pop     rdi
0x180047092  pop     rbp
0x180047093  retn
0x180047094  mov     edx, 233h; void *
0x180047099  mov     rcx, [rbp+5Fh]; this
0x18004709d  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x1800470a4  mov     r9d, eax; char *
0x1800470a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800470ac  jmp     short loc_18004704A
0x1800470ae  mov     edx, 225h; void *
0x1800470b3  mov     rcx, [rbp+5Fh]; this
0x1800470b7  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x1800470be  mov     r9d, eax; char *
0x1800470c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800470c6  jmp     short loc_18004705C
0x1800470c8  mov     rdi, [rbp+57h+var_68]
0x1800470cc  lea     rcx, [rbp+57h+var_60]
0x1800470d0  mov     [rbp+57h+var_60], r14
0x1800470d4  mov     rax, [rdi]
0x1800470d7  mov     rbx, [rax+88h]
0x1800470de  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800470e3  mov     dl, byte ptr [rbp+57h+var_30+8]
0x1800470e6  lea     r8, [rbp+57h+var_60]
0x1800470ea  mov     rcx, rdi
0x1800470ed  mov     rax, rbx
0x1800470f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800470f5  mov     ebx, eax
0x1800470f7  test    eax, eax
0x1800470f9  js      loc_180047252
0x1800470ff  mov     rbx, [rbp+57h+var_70]
0x180047103  lea     r9, [rbp+57h+string]; string
0x180047107  mov     rsi, [rbp+57h+var_60]
0x18004710b  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18004710f  mov     edx, 2Dh ; '-'; length
0x180047114  lea     rcx, aIsapplicationm; "IsApplicationMultiviewActivationPolicyE"...
0x18004711b  mov     rdi, [rbx]
0x18004711e  mov     [rbp+57h+string], r14
0x180047122  call    cs:__imp_WindowsCreateStringReference
0x180047128  test    eax, eax
0x18004712a  js      loc_18004725C
0x180047130  mov     rdx, [rbp+57h+string]
0x180047134  lea     r9, [rbp+57h+var_90]
0x180047138  mov     rax, [rdi+50h]
0x18004713c  mov     r8, rsi
0x18004713f  mov     rcx, rbx
0x180047142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047147  mov     ebx, eax
0x180047149  test    eax, eax
0x18004714b  jns     short loc_180047187
0x18004714d  mov     edx, 242h; void *
0x180047152  mov     rcx, [rbp+5Fh]; this
0x180047156  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x18004715d  mov     r9d, eax; char *
0x180047160  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047165  lea     rcx, [rbp+57h+var_60]
0x180047169  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004716e  jmp     loc_180047041
0x180047173  mov     edx, 235h
0x180047178  jmp     loc_180047099
0x18004717d  mov     edx, 229h
0x180047182  jmp     loc_1800470B3
0x180047187  lea     rcx, [rbp+57h+var_60]
0x18004718b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180047190  lea     rcx, [rbp+57h+var_78]
0x180047194  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180047199  lea     rcx, [rbp+57h+var_80]
0x18004719d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800471a2  lea     rcx, [rbp+57h+var_88]
0x1800471a6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800471ab  lea     rcx, [rbp+57h+var_68]
0x1800471af  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800471b4  lea     rcx, [rbp+57h+var_70]
0x1800471b8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800471bd  xor     eax, eax
0x1800471bf  jmp     loc_180047070
0x1800471c4  mov     edx, 22Ch; void *
0x1800471c9  mov     rcx, [rbp+5Fh]; this
0x1800471cd  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x1800471d4  mov     r9d, eax; char *
0x1800471d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800471dc  jmp     loc_180047053
0x1800471e1  mov     edx, 23Dh
0x1800471e6  jmp     loc_18004702E
0x1800471eb  mov     rcx, [rbp+5Fh]; this
0x1800471ef  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x1800471f6  mov     r9d, ebx; char *
0x1800471f9  mov     edx, 220h; void *
0x1800471fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047203  jmp     loc_18004706E
0x180047208  xor     r9d, r9d; lpArguments
0x18004720b  xor     r8d, r8d; nNumberOfArguments
0x18004720e  mov     ecx, eax; dwExceptionCode
0x180047210  lea     edx, [r9+1]; dwExceptionFlags
0x180047214  call    cs:__imp_RaiseException
0x18004721a  int     3; Trap to Debugger
0x18004721b  mov     edx, 226h
0x180047220  jmp     loc_1800470B3
0x180047225  mov     edx, 22Fh
0x18004722a  jmp     short loc_1800471C9
0x18004722c  xor     r9d, r9d; lpArguments
0x18004722f  xor     r8d, r8d; nNumberOfArguments
0x180047232  mov     ecx, eax; dwExceptionCode
0x180047234  lea     edx, [r9+1]; dwExceptionFlags
0x180047238  call    cs:__imp_RaiseException
0x18004723e  int     3; Trap to Debugger
0x18004723f  xor     r9d, r9d; lpArguments
0x180047242  xor     r8d, r8d; nNumberOfArguments
0x180047245  mov     ecx, eax; dwExceptionCode
0x180047247  lea     edx, [r9+1]; dwExceptionFlags
0x18004724b  call    cs:__imp_RaiseException
0x180047251  int     3; Trap to Debugger
0x180047252  mov     edx, 241h
0x180047257  jmp     loc_180047152
0x18004725c  xor     r9d, r9d; lpArguments
0x18004725f  xor     r8d, r8d; nNumberOfArguments
0x180047262  mov     ecx, eax; dwExceptionCode
0x180047264  lea     edx, [r9+1]; dwExceptionFlags
0x180047268  call    cs:__imp_RaiseException
0x1806eda56  mov     rsi, [rbp+57h+var_70]
0x1806eda5a  lea     rdx, aViewswitcher; "ViewSwitcher"
0x1806eda61  mov     r9d, 0Ch; unsigned int
0x1806eda67  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1806eda6b  mov     rax, [rsi]
  ... truncated ...
```
