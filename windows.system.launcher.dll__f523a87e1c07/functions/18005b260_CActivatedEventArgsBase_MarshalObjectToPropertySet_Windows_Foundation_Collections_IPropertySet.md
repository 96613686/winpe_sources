# CActivatedEventArgsBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x18005b260`
- end: `0x18005be60`
- name: `?MarshalObjectToPropertySet@CActivatedEventArgsBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `3072`
- prototype: `__int64 __fastcall(CActivatedEventArgsBase *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005ade0`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x180027108`
- `0x18002cec0`
- `0x18003c4f8`
- `0x18005b260`
- `0x18008a030`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005b78d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005b812`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005b78d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005b812`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005b33c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005b33c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b2fb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b3e7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b4e2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b5ed`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b72d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b2fb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b3e7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b4e2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b5ed`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b72d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b2e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b3d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b4cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b5d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b717`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b2e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b3d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b4cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b5d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b717`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CActivatedEventArgsBase::MarshalObjectToPropertySet(
        RTL_SRWLOCK *this,
        __int64 (__fastcall ***a2)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 **))
{
  __int64 (__fastcall *v4)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 **); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  HRESULT v8; // eax
  unsigned int Ptr; // edi
  __int64 v10; // rsi
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64 *); // rbx
  int v12; // eax
  __int64 *v13; // rbx
  __int64 v14; // rdi
  __int64 v15; // rsi
  HRESULT v16; // eax
  int v17; // eax
  unsigned int Ptr_high; // edi
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, _QWORD, __int64 *); // rbx
  int v21; // eax
  __int64 *v22; // rbx
  __int64 v23; // rdi
  __int64 v24; // rsi
  HRESULT v25; // eax
  int v26; // eax
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, PVOID, __int64 *); // rbx
  int v29; // eax
  __int64 *v30; // rbx
  __int64 v31; // rdi
  __int64 v32; // rsi
  HRESULT v33; // eax
  int v34; // eax
  PVOID v35; // rsi
  __int64 *v36; // rdi
  __int64 (__fastcall *v37)(__int64 *, HSTRING, PVOID, _BYTE *); // rbx
  int v38; // eax
  PVOID v39; // rbx
  __int64 *v40; // rdi
  __int64 v41; // rsi
  HRESULT v42; // eax
  int v43; // eax
  __int64 v44; // rdi
  __int64 (__fastcall *v45)(__int64, __int64, __int64 *); // rbx
  __int64 v46; // rdx
  int v47; // eax
  __int64 *v48; // rsi
  __int64 (__fastcall *v49)(__int64 *, HSTRING, __int64, _BYTE *); // rdi
  __int64 v50; // rbx
  int v51; // eax
  __int64 v52; // rdi
  __int64 (__fastcall *v53)(__int64, __int64, __int64 *); // rbx
  __int64 v54; // rdx
  int v55; // eax
  __int64 *v56; // rsi
  __int64 (__fastcall *v57)(__int64 *, HSTRING, __int64, _BYTE *); // rdi
  __int64 v58; // rbx
  int v59; // eax
  __int64 v60; // rdi
  __int64 (__fastcall *v61)(__int64, __int64, __int64 *); // rbx
  __int64 v62; // rdx
  int v63; // eax
  __int64 *v64; // rsi
  __int64 (__fastcall *v65)(__int64 *, HSTRING, __int64, _BYTE *); // rdi
  __int64 v66; // rbx
  int v67; // eax
  __int64 v68; // rdi
  __int64 (__fastcall *v69)(__int64, PVOID, __int64 *); // rbx
  int v70; // eax
  __int64 *v71; // rsi
  __int64 (__fastcall *v72)(__int64 *, HSTRING, __int64, _BYTE *); // rdi
  __int64 v73; // rbx
  int v74; // eax
  __int64 v75; // rdi
  __int64 (__fastcall *v76)(__int64, HSTRING_HEADER *, __int64 *); // rbx
  int v77; // eax
  __int64 *v78; // rsi
  __int64 (__fastcall *v79)(__int64 *, HSTRING, __int64, _BYTE *); // rdi
  __int64 v80; // rbx
  int v81; // eax
  int v83; // [rsp+20h] [rbp-79h]
  _BYTE v84[8]; // [rsp+30h] [rbp-69h] BYREF
  __int64 v85; // [rsp+38h] [rbp-61h] BYREF
  __int64 v86; // [rsp+40h] [rbp-59h] BYREF
  __int64 v87; // [rsp+48h] [rbp-51h] BYREF
  RTL_SRWLOCK *v88; // [rsp+50h] [rbp-49h] BYREF
  __int64 v89; // [rsp+58h] [rbp-41h] BYREF
  __int64 *v90; // [rsp+60h] [rbp-39h] BYREF
  __int64 v91; // [rsp+68h] [rbp-31h] BYREF
  __int64 v92; // [rsp+70h] [rbp-29h] BYREF
  __int64 v93; // [rsp+78h] [rbp-21h] BYREF
  __int64 v94; // [rsp+80h] [rbp-19h] BYREF
  __int64 v95; // [rsp+88h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-9h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v90 = 0;
  v92 = 0;
  v4 = **a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90);
  v5 = v4((struct Windows::Foundation::Collections::IPropertySet *)a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v90);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 53;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v5,
      v83);
LABEL_58:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90);
    return v6;
  }
  string = 0;
  v8 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(
         string,
         &v92);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 54;
    goto LABEL_7;
  }
  AcquireSRWLockShared(this + 18);
  v88 = this + 18;
  v85 = 0;
  Ptr = (unsigned int)this[9].Ptr;
  v10 = v92;
  v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v92 + 88LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
  v12 = v11(v10, Ptr, &v85);
  v6 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v12,
      v83);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v88);
    goto LABEL_58;
  }
  v84[0] = 0;
  v13 = v90;
  v14 = *v90;
  v15 = v85;
  string = 0;
  v16 = WindowsCreateStringReference(L"ActivationKind", 0xEu, &hstringHeader, &string);
  if ( v16 < 0 )
  {
    RaiseException(v16, 1u, 0, 0);
    __debugbreak();
  }
  v17 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(v14 + 80))(v13, string, v15, v84);
  v6 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v17,
      v83);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v88);
    goto LABEL_58;
  }
  v86 = 0;
  Ptr_high = HIDWORD(this[9].Ptr);
  v19 = v92;
  v20 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v92 + 88LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
  v21 = v20(v19, Ptr_high, &v86);
  v6 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v21,
      v83);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v88);
    goto LABEL_58;
  }
  v22 = v90;
  v23 = *v90;
  v24 = v86;
  string = 0;
  v25 = WindowsCreateStringReference(L"PreviousExecutionState", 0x16u, &hstringHeader, &string);
  if ( v25 < 0 )
  {
    RaiseException(v25, 1u, 0, 0);
    __debugbreak();
  }
  v26 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(v23 + 80))(v22, string, v24, v84);
  v6 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v26,
      v83);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v88);
    goto LABEL_58;
  }
  v87 = 0;
  v27 = v92;
  v28 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v92 + 104LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
  v29 = v28(v27, this[13].Ptr, &v87);
  v6 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v29,
      v83);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v88);
    goto LABEL_58;
  }
  v30 = v90;
  v31 = *v90;
  v32 = v87;
  string = 0;
  v33 = WindowsCreateStringReference(L"UserContext", 0xBu, &hstringHeader, &string);
  if ( v33 < 0 )
  {
    RaiseException(v33, 1u, 0, 0);
    __debugbreak();
  }
  v34 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(v31 + 80))(v30, string, v32, v84);
  v6 = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v34,
      v83);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v88);
    goto LABEL_58;
  }
  v35 = this[11].Ptr;
  if ( v35 )
  {
    v36 = v90;
    v37 = *(__int64 (__fastcall **)(__int64 *, HSTRING, PVOID, _BYTE *))(*v90 + 80);
    string = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"SplashScreen", 0xDu, 0xCu);
    v38 = v37(v36, string, v35, v84);
    v6 = v38;
    if ( v38 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4B,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
        (const char *)(unsigned int)v38,
        v83);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v88);
      goto LABEL_58;
    }
  }
  v39 = this[10].Ptr;
  if ( v39 )
  {
    v40 = v90;
    v41 = *v90;
    string = 0;
    v42 = WindowsCreateStringReference(L"ActivationValueSetReference", 0x1Bu, &hstringHeader, &string);
    if ( v42 < 0 )
    {
      RaiseException(v42, 1u, 0, 0);
      __debugbreak();
    }
    v43 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, PVOID, _BYTE *))(v41 + 80))(v40, string, v39, v84);
    v6 = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x50,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
        (const char *)(unsigned int)v43,
        v83);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
      if ( this != (RTL_SRWLOCK *)-144LL )
        ReleaseSRWLockShared(this + 18);
      goto LABEL_58;
    }
  }
  v89 = 0;
  v44 = v92;
  v45 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v92 + 136LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
  LOBYTE(v46) = BYTE6(this[12].Ptr);
  v47 = v45(v44, v46, &v89);
  v6 = v47;
  if ( v47 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v47,
      v83);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    if ( this != (RTL_SRWLOCK *)-144LL )
      ReleaseSRWLockShared(this + 18);
    goto LABEL_58;
  }
  v48 = v90;
  v49 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(*v90 + 80);
  v50 = v89;
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"IsForeground", 0xDu, 0xCu);
  v51 = v49(v48, string, v50, v84);
  v6 = v51;
  if ( v51 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v51,
      v83);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v88);
    goto LABEL_58;
  }
  v91 = 0;
  v52 = v92;
  v53 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v92 + 136LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
  LOBYTE(v54) = this[14].Ptr;
  v55 = v53(v52, v54, &v91);
  v6 = v55;
  if ( v55 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v55,
      v83);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v88);
    goto LABEL_58;
  }
  v56 = v90;
  v57 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(*v90 + 80);
  v58 = v91;
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"IsHolographic", 0xEu, 0xDu);
  v59 = v57(v56, string, v58, v84);
  v6 = v59;
  if ( v59 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x59,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v59,
      v83);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v88);
    goto LABEL_58;
  }
  v93 = 0;
  v60 = v92;
  v61 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v92 + 136LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
  LOBYTE(v62) = BYTE5(this[12].Ptr);
  v63 = v61(v60, v62, &v93);
  v6 = v63;
  if ( v63 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v63,
      v83);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v88);
    goto LABEL_58;
  }
  v64 = v90;
  v65 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(*v90 + 80);
  v66 = v93;
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"IsInitialized", 0xEu, 0xDu);
  v67 = v65(v64, string, v66, v84);
  v6 = v67;
  if ( v67 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v67,
      v83);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v88);
    goto LABEL_58;
  }
  v94 = 0;
  v68 = v92;
  v69 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v92 + 104LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v94);
  v70 = v69(v68, this[15].Ptr, &v94);
  v6 = v70;
  if ( v70 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v70,
      v83);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v94);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v88);
    goto LABEL_58;
  }
  v71 = v90;
  v72 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(*v90 + 80);
  v73 = v94;
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AamActivationId", 0x10u, 0xFu);
  v74 = v72(v71, string, v73, v84);
  v6 = v74;
  if ( v74 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v74,
      v83);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v94);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v88);
    goto LABEL_58;
  }
  v95 = 0;
  v75 = v92;
  v76 = *(__int64 (__fastcall **)(__int64, HSTRING_HEADER *, __int64 *))(*(_QWORD *)v92 + 160LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v95);
  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *(_OWORD *)&this[16].Ptr;
  v77 = v76(v75, &hstringHeader, &v95);
  v6 = v77;
  if ( v77 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v77,
      v83);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v95);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v94);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v88);
    goto LABEL_58;
  }
  v78 = v90;
  v79 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(*v90 + 80);
  v80 = v95;
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AamActivityId", 0xEu, 0xDu);
  v81 = v79(v78, string, v80, v84);
  v6 = v81;
  if ( v81 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v81,
      v83);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v95);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v94);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v88);
    goto LABEL_58;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v95);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v94);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v88);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90);
  return 0;
}

```

## disassembly

```asm
0x18005b260  mov     [rsp-8+arg_10], rbx
0x18005b265  push    rbp
0x18005b266  push    rsi
0x18005b267  push    rdi
0x18005b268  push    r12
0x18005b26a  push    r13
0x18005b26c  push    r14
0x18005b26e  push    r15
0x18005b270  lea     rbp, [rsp-27h]
0x18005b275  sub     rsp, 0C0h
0x18005b27c  mov     rax, cs:__security_cookie
0x18005b283  xor     rax, rsp
0x18005b286  mov     [rbp+57h+var_40], rax
0x18005b28a  mov     rdi, rdx
0x18005b28d  mov     r14, rcx
0x18005b290  xor     r12d, r12d
0x18005b293  mov     [rbp+57h+var_90], r12
0x18005b297  mov     [rbp+57h+var_80], r12
0x18005b29b  mov     rax, [rdx]
0x18005b29e  mov     rbx, [rax]
0x18005b2a1  lea     rcx, [rbp+57h+var_90]
0x18005b2a5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005b2aa  lea     r8, [rbp+57h+var_90]
0x18005b2ae  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18005b2b5  mov     rcx, rdi
0x18005b2b8  mov     rax, rbx
0x18005b2bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b2c0  mov     ebx, eax
0x18005b2c2  test    eax, eax
0x18005b2c4  jns     short loc_18005B2CD
0x18005b2c6  lea     edx, [r12+35h]
0x18005b2cb  jmp     short loc_18005B31A
0x18005b2cd  mov     [rbp+57h+string], r12
0x18005b2d1  lea     r9, [rbp+57h+string]; string
0x18005b2d5  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18005b2d9  mov     edx, 20h ; ' '; length
0x18005b2de  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18005b2e5  call    cs:__imp_WindowsCreateStringReference
0x18005b2eb  test    eax, eax
0x18005b2ed  jns     short loc_18005B302
0x18005b2ef  xor     r9d, r9d; lpArguments
0x18005b2f2  xor     r8d, r8d; nNumberOfArguments
0x18005b2f5  lea     edx, [r9+1]; dwExceptionFlags
0x18005b2f9  mov     ecx, eax; dwExceptionCode
0x18005b2fb  call    cs:__imp_RaiseException
0x18005b301  int     3; Trap to Debugger
0x18005b302  lea     rdx, [rbp+57h+var_80]
0x18005b306  mov     rcx, [rbp+57h+string]
0x18005b30a  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x18005b30f  mov     ebx, eax
0x18005b311  test    eax, eax
0x18005b313  jns     short loc_18005B332
0x18005b315  mov     edx, 36h ; '6'; void *
0x18005b31a  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x18005b321  mov     r9d, eax; char *
0x18005b324  mov     rcx, [rbp+5Fh]; this
0x18005b328  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b32d  jmp     loc_18005BDBC
0x18005b332  lea     r15, [r14+90h]
0x18005b339  mov     rcx, r15; SRWLock
0x18005b33c  call    cs:__imp_AcquireSRWLockShared
0x18005b342  mov     [rbp+57h+var_A0], r15
0x18005b346  mov     [rbp+57h+var_B8], r12
0x18005b34a  mov     edi, [r14+48h]
0x18005b34e  mov     rsi, [rbp+57h+var_80]
0x18005b352  mov     rax, [rsi]
0x18005b355  mov     rbx, [rax+58h]
0x18005b359  lea     rcx, [rbp+57h+var_B8]
0x18005b35d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005b362  lea     r8, [rbp+57h+var_B8]
0x18005b366  mov     edx, edi
0x18005b368  mov     rcx, rsi
0x18005b36b  mov     rax, rbx
0x18005b36e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b373  mov     ebx, eax
0x18005b375  test    eax, eax
0x18005b377  jns     short loc_18005B3AA
0x18005b379  mov     rcx, [rbp+5Fh]; this
0x18005b37d  mov     r9d, eax; char *
0x18005b380  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x18005b387  mov     edx, 3Ch ; '<'; void *
0x18005b38c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b391  lea     rcx, [rbp+57h+var_B8]
0x18005b395  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005b39a  nop
0x18005b39b  lea     rcx, [rbp+57h+var_A0]
0x18005b39f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18005b3a4  nop
0x18005b3a5  jmp     loc_18005BDBC
0x18005b3aa  mov     [rbp+57h+var_C0], r12b
0x18005b3ae  mov     rbx, [rbp+57h+var_90]
0x18005b3b2  mov     rdi, [rbx]
0x18005b3b5  mov     rsi, [rbp+57h+var_B8]
0x18005b3b9  mov     [rbp+57h+string], r12
0x18005b3bd  lea     r9, [rbp+57h+string]; string
0x18005b3c1  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18005b3c5  mov     edx, 0Eh; length
0x18005b3ca  lea     rcx, aActivationkind; "ActivationKind"
0x18005b3d1  call    cs:__imp_WindowsCreateStringReference
0x18005b3d7  test    eax, eax
0x18005b3d9  jns     short loc_18005B3EE
0x18005b3db  xor     r9d, r9d; lpArguments
0x18005b3de  xor     r8d, r8d; nNumberOfArguments
0x18005b3e1  lea     edx, [r9+1]; dwExceptionFlags
0x18005b3e5  mov     ecx, eax; dwExceptionCode
0x18005b3e7  call    cs:__imp_RaiseException
0x18005b3ed  int     3; Trap to Debugger
0x18005b3ee  lea     r9, [rbp+57h+var_C0]
0x18005b3f2  mov     r8, rsi
0x18005b3f5  mov     rdx, [rbp+57h+string]
0x18005b3f9  mov     rcx, rbx
0x18005b3fc  mov     rax, [rdi+50h]
0x18005b400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b405  mov     ebx, eax
0x18005b407  test    eax, eax
0x18005b409  jns     short loc_18005B43C
0x18005b40b  mov     rcx, [rbp+5Fh]; this
0x18005b40f  mov     r9d, eax; char *
0x18005b412  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x18005b419  mov     edx, 3Eh ; '>'; void *
0x18005b41e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b423  lea     rcx, [rbp+57h+var_B8]
0x18005b427  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005b42c  nop
0x18005b42d  lea     rcx, [rbp+57h+var_A0]
0x18005b431  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18005b436  nop
0x18005b437  jmp     loc_18005BDBC
0x18005b43c  mov     [rbp+57h+var_B0], r12
0x18005b440  mov     edi, [r14+4Ch]
0x18005b444  mov     rsi, [rbp+57h+var_80]
0x18005b448  mov     rax, [rsi]
0x18005b44b  mov     rbx, [rax+58h]
0x18005b44f  lea     rcx, [rbp+57h+var_B0]
0x18005b453  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005b458  lea     r8, [rbp+57h+var_B0]
0x18005b45c  mov     edx, edi
0x18005b45e  mov     rcx, rsi
0x18005b461  mov     rax, rbx
0x18005b464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b469  mov     ebx, eax
0x18005b46b  test    eax, eax
0x18005b46d  jns     short loc_18005B4A9
0x18005b46f  mov     rcx, [rbp+5Fh]; this
0x18005b473  mov     r9d, eax; char *
0x18005b476  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x18005b47d  mov     edx, 42h ; 'B'; void *
0x18005b482  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b487  lea     rcx, [rbp+57h+var_B0]
0x18005b48b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005b490  lea     rcx, [rbp+57h+var_B8]
0x18005b494  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005b499  nop
0x18005b49a  lea     rcx, [rbp+57h+var_A0]
0x18005b49e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18005b4a3  nop
0x18005b4a4  jmp     loc_18005BDBC
0x18005b4a9  mov     rbx, [rbp+57h+var_90]
0x18005b4ad  mov     rdi, [rbx]
0x18005b4b0  mov     rsi, [rbp+57h+var_B0]
0x18005b4b4  mov     [rbp+57h+string], r12
0x18005b4b8  lea     r9, [rbp+57h+string]; string
0x18005b4bc  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18005b4c0  mov     edx, 16h; length
0x18005b4c5  lea     rcx, aPreviousexecut; "PreviousExecutionState"
0x18005b4cc  call    cs:__imp_WindowsCreateStringReference
0x18005b4d2  test    eax, eax
0x18005b4d4  jns     short loc_18005B4E9
0x18005b4d6  xor     r9d, r9d; lpArguments
0x18005b4d9  xor     r8d, r8d; nNumberOfArguments
0x18005b4dc  lea     edx, [r9+1]; dwExceptionFlags
0x18005b4e0  mov     ecx, eax; dwExceptionCode
0x18005b4e2  call    cs:__imp_RaiseException
0x18005b4e8  int     3; Trap to Debugger
0x18005b4e9  lea     r9, [rbp+57h+var_C0]
0x18005b4ed  mov     r8, rsi
0x18005b4f0  mov     rdx, [rbp+57h+string]
0x18005b4f4  mov     rcx, rbx
0x18005b4f7  mov     rax, [rdi+50h]
0x18005b4fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b500  mov     ebx, eax
0x18005b502  test    eax, eax
0x18005b504  jns     short loc_18005B540
0x18005b506  mov     rcx, [rbp+5Fh]; this
0x18005b50a  mov     r9d, eax; char *
0x18005b50d  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x18005b514  mov     edx, 43h ; 'C'; void *
0x18005b519  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b51e  lea     rcx, [rbp+57h+var_B0]
0x18005b522  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005b527  lea     rcx, [rbp+57h+var_B8]
0x18005b52b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005b530  nop
0x18005b531  lea     rcx, [rbp+57h+var_A0]
0x18005b535  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18005b53a  nop
0x18005b53b  jmp     loc_18005BDBC
0x18005b540  mov     [rbp+57h+var_A8], r12
0x18005b544  mov     rdi, [rbp+57h+var_80]
0x18005b548  mov     rax, [rdi]
0x18005b54b  mov     rbx, [rax+68h]
0x18005b54f  lea     rcx, [rbp+57h+var_A8]
0x18005b553  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005b558  lea     r8, [rbp+57h+var_A8]
0x18005b55c  mov     rdx, [r14+68h]
0x18005b560  mov     rcx, rdi
0x18005b563  mov     rax, rbx
0x18005b566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b56b  mov     ebx, eax
0x18005b56d  test    eax, eax
0x18005b56f  jns     short loc_18005B5B4
0x18005b571  mov     rcx, [rbp+5Fh]; this
0x18005b575  mov     r9d, eax; char *
0x18005b578  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x18005b57f  mov     edx, 46h ; 'F'; void *
0x18005b584  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b589  lea     rcx, [rbp+57h+var_A8]
0x18005b58d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005b592  lea     rcx, [rbp+57h+var_B0]
0x18005b596  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005b59b  lea     rcx, [rbp+57h+var_B8]
0x18005b59f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005b5a4  nop
0x18005b5a5  lea     rcx, [rbp+57h+var_A0]
0x18005b5a9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18005b5ae  nop
0x18005b5af  jmp     loc_18005BDBC
0x18005b5b4  mov     rbx, [rbp+57h+var_90]
0x18005b5b8  mov     rdi, [rbx]
0x18005b5bb  mov     rsi, [rbp+57h+var_A8]
0x18005b5bf  mov     [rbp+57h+string], r12
0x18005b5c3  lea     r9, [rbp+57h+string]; string
0x18005b5c7  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18005b5cb  mov     edx, 0Bh; length
0x18005b5d0  lea     rcx, aUsercontext; "UserContext"
0x18005b5d7  call    cs:__imp_WindowsCreateStringReference
0x18005b5dd  test    eax, eax
0x18005b5df  jns     short loc_18005B5F4
0x18005b5e1  xor     r9d, r9d; lpArguments
0x18005b5e4  xor     r8d, r8d; nNumberOfArguments
0x18005b5e7  lea     edx, [r9+1]; dwExceptionFlags
0x18005b5eb  mov     ecx, eax; dwExceptionCode
0x18005b5ed  call    cs:__imp_RaiseException
0x18005b5f3  int     3; Trap to Debugger
0x18005b5f4  lea     r9, [rbp+57h+var_C0]
0x18005b5f8  mov     r8, rsi
0x18005b5fb  mov     rdx, [rbp+57h+string]
0x18005b5ff  mov     rcx, rbx
0x18005b602  mov     rax, [rdi+50h]
0x18005b606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b60b  mov     ebx, eax
0x18005b60d  test    eax, eax
0x18005b60f  jns     short loc_18005B654
0x18005b611  mov     rcx, [rbp+5Fh]; this
0x18005b615  mov     r9d, eax; char *
0x18005b618  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x18005b61f  mov     edx, 47h ; 'G'; void *
0x18005b624  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b629  lea     rcx, [rbp+57h+var_A8]
0x18005b62d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005b632  lea     rcx, [rbp+57h+var_B0]
0x18005b636  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005b63b  lea     rcx, [rbp+57h+var_B8]
0x18005b63f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005b644  nop
0x18005b645  lea     rcx, [rbp+57h+var_A0]
0x18005b649  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18005b64e  nop
0x18005b64f  jmp     loc_18005BDBC
0x18005b654  mov     rsi, [r14+58h]
0x18005b658  mov     r13d, 0Dh
0x18005b65e  test    rsi, rsi
0x18005b661  jz      loc_18005B6EB
0x18005b667  mov     rdi, [rbp+57h+var_90]
0x18005b66b  mov     rax, [rdi]
0x18005b66e  mov     rbx, [rax+50h]
0x18005b672  mov     [rbp+57h+string], r12
0x18005b676  lea     r9d, [r13-1]; unsigned int
0x18005b67a  mov     r8d, r13d; unsigned int
0x18005b67d  lea     rdx, aSplashscreen; "SplashScreen"
0x18005b684  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005b688  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005b68d  lea     r9, [rbp+57h+var_C0]
0x18005b691  mov     r8, rsi
0x18005b694  mov     rdx, [rbp+57h+string]
0x18005b698  mov     rcx, rdi
0x18005b69b  mov     rax, rbx
0x18005b69e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b6a3  mov     ebx, eax
0x18005b6a5  test    eax, eax
0x18005b6a7  jns     short loc_18005B6EB
0x18005b6a9  mov     rcx, [rbp+5Fh]; this
0x18005b6ad  mov     r9d, eax; char *
0x18005b6b0  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x18005b6b7  lea     edx, [r13+3Eh]; void *
0x18005b6bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b6c0  lea     rcx, [rbp+57h+var_A8]
0x18005b6c4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005b6c9  lea     rcx, [rbp+57h+var_B0]
0x18005b6cd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
  ... truncated ...
```
