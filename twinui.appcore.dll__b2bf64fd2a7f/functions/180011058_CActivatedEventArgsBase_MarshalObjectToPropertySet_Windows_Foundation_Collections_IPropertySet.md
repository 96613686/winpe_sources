# CActivatedEventArgsBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x180011058`
- end: `0x180011c65`
- name: `?MarshalObjectToPropertySet@CActivatedEventArgsBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `3085`
- prototype: `__int64 __fastcall(CActivatedEventArgsBase *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180010b00`

## callees

- `0x180003d24`
- `0x1800083f0`
- `0x180011058`
- `0x180016cf0`
- `0x18001cc38`
- `0x180022fb4`
- `0x18002b1b0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180011160`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180011160`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800112c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800112c6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001110b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001120b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001110b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001120b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800110f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800111f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800110f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800111f5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001112d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001112d`

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
  HRESULT v7; // eax
  HSTRING v8; // rbx
  int ActivationFactory; // eax
  unsigned int Ptr; // edi
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *); // rbx
  int v13; // eax
  __int64 *v14; // rbx
  __int64 v15; // rdi
  __int64 v16; // rsi
  HRESULT v17; // eax
  int v18; // eax
  unsigned int Ptr_high; // edi
  __int64 v20; // rsi
  __int64 (__fastcall *v21)(__int64, _QWORD, __int64 *); // rbx
  int v22; // eax
  __int64 v23; // rcx
  __int64 *v24; // rsi
  __int64 (__fastcall *v25)(__int64 *, HSTRING, __int64, _BYTE *); // rdi
  __int64 v26; // rbx
  int v27; // eax
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, PVOID, __int64 *); // rbx
  int v30; // eax
  __int64 *v31; // rsi
  __int64 (__fastcall *v32)(__int64 *, HSTRING, __int64, _BYTE *); // rdi
  __int64 v33; // rbx
  int v34; // eax
  PVOID v35; // rsi
  __int64 *v36; // rdi
  __int64 (__fastcall *v37)(__int64 *, HSTRING, PVOID, _BYTE *); // rbx
  int v38; // eax
  PVOID v39; // rsi
  __int64 *v40; // rdi
  __int64 (__fastcall *v41)(__int64 *, HSTRING, PVOID, _BYTE *); // rbx
  int v42; // eax
  __int64 v43; // rdi
  __int64 (__fastcall *v44)(__int64, __int64, __int64 *); // rbx
  __int64 v45; // rdx
  int v46; // eax
  __int64 *v47; // rsi
  __int64 (__fastcall *v48)(__int64 *, HSTRING, __int64, _BYTE *); // rdi
  __int64 v49; // rbx
  int v50; // eax
  __int64 v51; // rdi
  __int64 (__fastcall *v52)(__int64, __int64, __int64 *); // rbx
  __int64 v53; // rdx
  int v54; // eax
  __int64 *v55; // rsi
  __int64 (__fastcall *v56)(__int64 *, HSTRING, __int64, _BYTE *); // rdi
  __int64 v57; // rbx
  int v58; // eax
  __int64 v59; // rdi
  __int64 (__fastcall *v60)(__int64, __int64, __int64 *); // rbx
  __int64 v61; // rdx
  int v62; // eax
  __int64 *v63; // rsi
  __int64 (__fastcall *v64)(__int64 *, HSTRING, __int64, _BYTE *); // rdi
  __int64 v65; // rbx
  int v66; // eax
  __int64 v67; // rdi
  __int64 (__fastcall *v68)(__int64, PVOID, __int64 *); // rbx
  int v69; // eax
  __int64 *v70; // rsi
  __int64 (__fastcall *v71)(__int64 *, HSTRING, __int64, _BYTE *); // rdi
  __int64 v72; // rbx
  int v73; // eax
  __int64 v74; // rdi
  __int64 (__fastcall *v75)(__int64, HSTRING_HEADER *, __int64 *); // rbx
  int v76; // eax
  __int64 *v77; // rsi
  __int64 (__fastcall *v78)(__int64 *, HSTRING, __int64, _BYTE *); // rdi
  __int64 v79; // rbx
  int v80; // eax
  int v82; // [rsp+20h] [rbp-69h]
  _BYTE v83[8]; // [rsp+30h] [rbp-59h] BYREF
  __int64 v84; // [rsp+38h] [rbp-51h] BYREF
  __int64 v85; // [rsp+40h] [rbp-49h] BYREF
  __int64 v86; // [rsp+48h] [rbp-41h] BYREF
  __int64 v87; // [rsp+50h] [rbp-39h] BYREF
  RTL_SRWLOCK *v88; // [rsp+58h] [rbp-31h] BYREF
  __int64 v89; // [rsp+60h] [rbp-29h] BYREF
  __int64 *v90; // [rsp+68h] [rbp-21h] BYREF
  __int64 v91; // [rsp+70h] [rbp-19h] BYREF
  __int64 v92; // [rsp+78h] [rbp-11h] BYREF
  __int64 v93; // [rsp+80h] [rbp-9h] BYREF
  __int64 v94; // [rsp+88h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp+7h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v90 = 0;
  v84 = 0;
  v4 = **a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90);
  v5 = v4((struct Windows::Foundation::Collections::IPropertySet *)a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v90);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v5,
      v82);
LABEL_16:
    v23 = v84;
    if ( v84 )
    {
      v84 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    goto LABEL_51;
  }
  string = 0;
  v7 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
  if ( v7 < 0 )
  {
    RaiseException(v7, 1u, 0, 0);
    __debugbreak();
  }
  v8 = string;
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v84);
  ActivationFactory = RoGetActivationFactory(v8, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v84);
  v6 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v82);
LABEL_50:
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v84);
LABEL_51:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90);
    return v6;
  }
  AcquireSRWLockShared(this + 18);
  v88 = this + 18;
  v85 = 0;
  Ptr = (unsigned int)this[9].Ptr;
  v11 = v84;
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v84 + 88LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
  v13 = v12(v11, Ptr, &v85);
  v6 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v13,
      v82);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v88);
    goto LABEL_50;
  }
  v83[0] = 0;
  v14 = v90;
  v15 = *v90;
  v16 = v85;
  string = 0;
  v17 = WindowsCreateStringReference(L"ActivationKind", 0xEu, &hstringHeader, &string);
  if ( v17 < 0 )
  {
    RaiseException(v17, 1u, 0, 0);
    __debugbreak();
  }
  v18 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(v15 + 80))(v14, string, v16, v83);
  v6 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v18,
      v82);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v88);
    goto LABEL_50;
  }
  v86 = 0;
  Ptr_high = HIDWORD(this[9].Ptr);
  v20 = v84;
  v21 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v84 + 88LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
  v22 = v21(v20, Ptr_high, &v86);
  v6 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v22,
      v82);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    if ( this != (RTL_SRWLOCK *)-144LL )
      ReleaseSRWLockShared(this + 18);
    goto LABEL_16;
  }
  v24 = v90;
  v25 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(*v90 + 80);
  v26 = v86;
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"PreviousExecutionState", 0x17u, 0x16u);
  v27 = v25(v24, string, v26, v83);
  v6 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v27,
      v82);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v88);
    goto LABEL_50;
  }
  v87 = 0;
  v28 = v84;
  v29 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v84 + 104LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
  v30 = v29(v28, this[13].Ptr, &v87);
  v6 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v30,
      v82);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v88);
    goto LABEL_50;
  }
  v31 = v90;
  v32 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(*v90 + 80);
  v33 = v87;
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UserContext", 0xCu, 0xBu);
  v34 = v32(v31, string, v33, v83);
  v6 = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v34,
      v82);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v88);
    goto LABEL_50;
  }
  v35 = this[11].Ptr;
  if ( v35 )
  {
    v36 = v90;
    v37 = *(__int64 (__fastcall **)(__int64 *, HSTRING, PVOID, _BYTE *))(*v90 + 80);
    string = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"SplashScreen", 0xDu, 0xCu);
    v38 = v37(v36, string, v35, v83);
    v6 = v38;
    if ( v38 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4B,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
        (const char *)(unsigned int)v38,
        v82);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
      CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v88);
      goto LABEL_50;
    }
  }
  v39 = this[10].Ptr;
  if ( v39 )
  {
    v40 = v90;
    v41 = *(__int64 (__fastcall **)(__int64 *, HSTRING, PVOID, _BYTE *))(*v90 + 80);
    string = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"ActivationValueSetReference",
      0x1Cu,
      0x1Bu);
    v42 = v41(v40, string, v39, v83);
    v6 = v42;
    if ( v42 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x50,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
        (const char *)(unsigned int)v42,
        v82);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
      CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v88);
      goto LABEL_50;
    }
  }
  v89 = 0;
  v43 = v84;
  v44 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v84 + 136LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
  LOBYTE(v45) = BYTE6(this[12].Ptr);
  v46 = v44(v43, v45, &v89);
  v6 = v46;
  if ( v46 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v46,
      v82);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v88);
    goto LABEL_50;
  }
  v47 = v90;
  v48 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(*v90 + 80);
  v49 = v89;
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"IsForeground", 0xDu, 0xCu);
  v50 = v48(v47, string, v49, v83);
  v6 = v50;
  if ( v50 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v50,
      v82);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v88);
    goto LABEL_50;
  }
  v91 = 0;
  v51 = v84;
  v52 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v84 + 136LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
  LOBYTE(v53) = this[14].Ptr;
  v54 = v52(v51, v53, &v91);
  v6 = v54;
  if ( v54 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v54,
      v82);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v88);
    goto LABEL_50;
  }
  v55 = v90;
  v56 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(*v90 + 80);
  v57 = v91;
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"IsHolographic", 0xEu, 0xDu);
  v58 = v56(v55, string, v57, v83);
  v6 = v58;
  if ( v58 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x59,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v58,
      v82);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v88);
    goto LABEL_50;
  }
  v92 = 0;
  v59 = v84;
  v60 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v84 + 136LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
  LOBYTE(v61) = BYTE5(this[12].Ptr);
  v62 = v60(v59, v61, &v92);
  v6 = v62;
  if ( v62 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v62,
      v82);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v88);
    goto LABEL_50;
  }
  v63 = v90;
  v64 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(*v90 + 80);
  v65 = v92;
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"IsInitialized", 0xEu, 0xDu);
  v66 = v64(v63, string, v65, v83);
  v6 = v66;
  if ( v66 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v66,
      v82);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v88);
    goto LABEL_50;
  }
  v93 = 0;
  v67 = v84;
  v68 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v84 + 104LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
  v69 = v68(v67, this[15].Ptr, &v93);
  v6 = v69;
  if ( v69 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v69,
      v82);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v88);
    goto LABEL_50;
  }
  v70 = v90;
  v71 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(*v90 + 80);
  v72 = v93;
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AamActivationId", 0x10u, 0xFu);
  v73 = v71(v70, string, v72, v83);
  v6 = v73;
  if ( v73 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v73,
      v82);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v88);
    goto LABEL_50;
  }
  v94 = 0;
  v74 = v84;
  v75 = *(__int64 (__fastcall **)(__int64, HSTRING_HEADER *, __int64 *))(*(_QWORD *)v84 + 160LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v94);
  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *(_OWORD *)&this[16].Ptr;
  v76 = v75(v74, &hstringHeader, &v94);
  v6 = v76;
  if ( v76 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v76,
      v82);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v94);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v88);
    goto LABEL_50;
  }
  v77 = v90;
  v78 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(*v90 + 80);
  v79 = v94;
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AamActivityId", 0xEu, 0xDu);
  v80 = v78(v77, string, v79, v83);
  v6 = v80;
  if ( v80 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v80,
      v82);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v94);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v88);
    goto LABEL_50;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v94);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
  CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v88);
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v84);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90);
  return 0;
}

```

## disassembly

```asm
0x180011058  mov     [rsp-8+arg_10], rbx
0x18001105d  mov     [rsp-8+arg_18], rsi
0x180011062  push    rbp
0x180011063  push    rdi
0x180011064  push    r12
0x180011066  push    r14
0x180011068  push    r15
0x18001106a  lea     rbp, [rsp-37h]
0x18001106f  sub     rsp, 0C0h
0x180011076  mov     rax, cs:__security_cookie
0x18001107d  xor     rax, rsp
0x180011080  mov     [rbp+57h+var_30], rax
0x180011084  mov     rdi, rdx
0x180011087  mov     r14, rcx
0x18001108a  xor     r12d, r12d
0x18001108d  mov     [rbp+57h+var_78], r12
0x180011091  mov     [rbp+57h+var_A8], r12
0x180011095  mov     rax, [rdx]
0x180011098  mov     rbx, [rax]
0x18001109b  lea     rcx, [rbp+57h+var_78]
0x18001109f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800110a4  lea     r8, [rbp+57h+var_78]
0x1800110a8  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x1800110af  mov     rcx, rdi
0x1800110b2  mov     rax, rbx
0x1800110b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110ba  mov     ebx, eax
0x1800110bc  test    eax, eax
0x1800110be  jns     short loc_1800110DD
0x1800110c0  mov     rcx, [rbp+5Fh]; this
0x1800110c4  mov     r9d, eax; char *
0x1800110c7  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x1800110ce  lea     edx, [r12+35h]; void *
0x1800110d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800110d8  jmp     loc_1800112CD
0x1800110dd  mov     [rbp+57h+string], r12
0x1800110e1  lea     r9, [rbp+57h+string]; string
0x1800110e5  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800110e9  mov     edx, 20h ; ' '; length
0x1800110ee  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x1800110f5  call    cs:__imp_WindowsCreateStringReference
0x1800110fb  test    eax, eax
0x1800110fd  jns     short loc_180011112
0x1800110ff  xor     r9d, r9d; lpArguments
0x180011102  xor     r8d, r8d; nNumberOfArguments
0x180011105  lea     edx, [r9+1]; dwExceptionFlags
0x180011109  mov     ecx, eax; dwExceptionCode
0x18001110b  call    cs:__imp_RaiseException
0x180011111  int     3; Trap to Debugger
0x180011112  mov     rbx, [rbp+57h+string]
0x180011116  lea     rcx, [rbp+57h+var_A8]
0x18001111a  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18001111f  lea     r8, [rbp+57h+var_A8]
0x180011123  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x18001112a  mov     rcx, rbx
0x18001112d  call    cs:__imp_RoGetActivationFactory
0x180011133  mov     ebx, eax
0x180011135  test    eax, eax
0x180011137  jns     short loc_180011156
0x180011139  mov     rcx, [rbp+5Fh]; this
0x18001113d  mov     r9d, eax; char *
0x180011140  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180011147  mov     edx, 36h ; '6'; void *
0x18001114c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011151  jmp     loc_180011BC0
0x180011156  lea     r15, [r14+90h]
0x18001115d  mov     rcx, r15; SRWLock
0x180011160  call    cs:__imp_AcquireSRWLockShared
0x180011166  mov     [rbp+57h+var_88], r15
0x18001116a  mov     [rbp+57h+var_A0], r12
0x18001116e  mov     edi, [r14+48h]
0x180011172  mov     rsi, [rbp+57h+var_A8]
0x180011176  mov     rax, [rsi]
0x180011179  mov     rbx, [rax+58h]
0x18001117d  lea     rcx, [rbp+57h+var_A0]
0x180011181  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011186  lea     r8, [rbp+57h+var_A0]
0x18001118a  mov     edx, edi
0x18001118c  mov     rcx, rsi
0x18001118f  mov     rax, rbx
0x180011192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011197  mov     ebx, eax
0x180011199  test    eax, eax
0x18001119b  jns     short loc_1800111CE
0x18001119d  mov     rcx, [rbp+5Fh]; this
0x1800111a1  mov     r9d, eax; char *
0x1800111a4  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x1800111ab  mov     edx, 3Ch ; '<'; void *
0x1800111b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800111b5  lea     rcx, [rbp+57h+var_A0]
0x1800111b9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800111be  nop
0x1800111bf  lea     rcx, [rbp+57h+var_88]; this
0x1800111c3  call    ??1CAutoSRWSharedLock@@QEAA@XZ; CAutoSRWSharedLock::~CAutoSRWSharedLock(void)
0x1800111c8  nop
0x1800111c9  jmp     loc_180011BC0
0x1800111ce  mov     [rbp+57h+var_B0], r12b
0x1800111d2  mov     rbx, [rbp+57h+var_78]
0x1800111d6  mov     rdi, [rbx]
0x1800111d9  mov     rsi, [rbp+57h+var_A0]
0x1800111dd  mov     [rbp+57h+string], r12
0x1800111e1  lea     r9, [rbp+57h+string]; string
0x1800111e5  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800111e9  mov     edx, 0Eh; length
0x1800111ee  lea     rcx, aActivationkind; "ActivationKind"
0x1800111f5  call    cs:__imp_WindowsCreateStringReference
0x1800111fb  test    eax, eax
0x1800111fd  jns     short loc_180011212
0x1800111ff  xor     r9d, r9d; lpArguments
0x180011202  xor     r8d, r8d; nNumberOfArguments
0x180011205  lea     edx, [r9+1]; dwExceptionFlags
0x180011209  mov     ecx, eax; dwExceptionCode
0x18001120b  call    cs:__imp_RaiseException
0x180011211  int     3; Trap to Debugger
0x180011212  lea     r9, [rbp+57h+var_B0]
0x180011216  mov     r8, rsi
0x180011219  mov     rdx, [rbp+57h+string]
0x18001121d  mov     rcx, rbx
0x180011220  mov     rax, [rdi+50h]
0x180011224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011229  mov     ebx, eax
0x18001122b  test    eax, eax
0x18001122d  jns     short loc_180011260
0x18001122f  mov     rcx, [rbp+5Fh]; this
0x180011233  mov     r9d, eax; char *
0x180011236  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x18001123d  mov     edx, 3Eh ; '>'; void *
0x180011242  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011247  lea     rcx, [rbp+57h+var_A0]
0x18001124b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011250  nop
0x180011251  lea     rcx, [rbp+57h+var_88]; this
0x180011255  call    ??1CAutoSRWSharedLock@@QEAA@XZ; CAutoSRWSharedLock::~CAutoSRWSharedLock(void)
0x18001125a  nop
0x18001125b  jmp     loc_180011BC0
0x180011260  mov     [rbp+57h+var_98], r12
0x180011264  mov     edi, [r14+4Ch]
0x180011268  mov     rsi, [rbp+57h+var_A8]
0x18001126c  mov     rax, [rsi]
0x18001126f  mov     rbx, [rax+58h]
0x180011273  lea     rcx, [rbp+57h+var_98]
0x180011277  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001127c  lea     r8, [rbp+57h+var_98]
0x180011280  mov     edx, edi
0x180011282  mov     rcx, rsi
0x180011285  mov     rax, rbx
0x180011288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001128d  mov     ebx, eax
0x18001128f  test    eax, eax
0x180011291  jns     short loc_1800112EF
0x180011293  mov     rcx, [rbp+5Fh]; this
0x180011297  mov     r9d, eax; char *
0x18001129a  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x1800112a1  mov     edx, 42h ; 'B'; void *
0x1800112a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800112ab  lea     rcx, [rbp+57h+var_98]
0x1800112af  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800112b4  lea     rcx, [rbp+57h+var_A0]
0x1800112b8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800112bd  nop
0x1800112be  test    r15, r15
0x1800112c1  jz      short loc_1800112CD
0x1800112c3  mov     rcx, r15; SRWLock
0x1800112c6  call    cs:__imp_ReleaseSRWLockShared
0x1800112cc  nop
0x1800112cd  mov     rcx, [rbp+57h+var_A8]
0x1800112d1  test    rcx, rcx
0x1800112d4  jz      loc_180011BC9
0x1800112da  mov     [rbp+57h+var_A8], r12
0x1800112de  mov     rax, [rcx]
0x1800112e1  mov     rax, [rax+10h]
0x1800112e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112ea  jmp     loc_180011BC9
0x1800112ef  mov     rsi, [rbp+57h+var_78]
0x1800112f3  mov     rax, [rsi]
0x1800112f6  mov     rdi, [rax+50h]
0x1800112fa  mov     rbx, [rbp+57h+var_98]
0x1800112fe  mov     [rbp+57h+string], r12
0x180011302  mov     r9d, 16h; unsigned int
0x180011308  lea     r8d, [r9+1]; unsigned int
0x18001130c  lea     rdx, aPreviousexecut; "PreviousExecutionState"
0x180011313  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180011317  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001131c  lea     r9, [rbp+57h+var_B0]
0x180011320  mov     r8, rbx
0x180011323  mov     rdx, [rbp+57h+string]
0x180011327  mov     rcx, rsi
0x18001132a  mov     rax, rdi
0x18001132d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011332  mov     ebx, eax
0x180011334  test    eax, eax
0x180011336  jns     short loc_180011372
0x180011338  mov     rcx, [rbp+5Fh]; this
0x18001133c  mov     r9d, eax; char *
0x18001133f  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180011346  mov     edx, 43h ; 'C'; void *
0x18001134b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011350  lea     rcx, [rbp+57h+var_98]
0x180011354  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011359  lea     rcx, [rbp+57h+var_A0]
0x18001135d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011362  nop
0x180011363  lea     rcx, [rbp+57h+var_88]; this
0x180011367  call    ??1CAutoSRWSharedLock@@QEAA@XZ; CAutoSRWSharedLock::~CAutoSRWSharedLock(void)
0x18001136c  nop
0x18001136d  jmp     loc_180011BC0
0x180011372  mov     [rbp+57h+var_90], r12
0x180011376  mov     rdi, [rbp+57h+var_A8]
0x18001137a  mov     rax, [rdi]
0x18001137d  mov     rbx, [rax+68h]
0x180011381  lea     rcx, [rbp+57h+var_90]
0x180011385  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001138a  lea     r8, [rbp+57h+var_90]
0x18001138e  mov     rdx, [r14+68h]
0x180011392  mov     rcx, rdi
0x180011395  mov     rax, rbx
0x180011398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001139d  mov     ebx, eax
0x18001139f  test    eax, eax
0x1800113a1  jns     short loc_1800113E6
0x1800113a3  mov     rcx, [rbp+5Fh]; this
0x1800113a7  mov     r9d, eax; char *
0x1800113aa  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x1800113b1  mov     edx, 46h ; 'F'; void *
0x1800113b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800113bb  lea     rcx, [rbp+57h+var_90]
0x1800113bf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800113c4  lea     rcx, [rbp+57h+var_98]
0x1800113c8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800113cd  lea     rcx, [rbp+57h+var_A0]
0x1800113d1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800113d6  nop
0x1800113d7  lea     rcx, [rbp+57h+var_88]; this
0x1800113db  call    ??1CAutoSRWSharedLock@@QEAA@XZ; CAutoSRWSharedLock::~CAutoSRWSharedLock(void)
0x1800113e0  nop
0x1800113e1  jmp     loc_180011BC0
0x1800113e6  mov     rsi, [rbp+57h+var_78]
0x1800113ea  mov     rax, [rsi]
0x1800113ed  mov     rdi, [rax+50h]
0x1800113f1  mov     rbx, [rbp+57h+var_90]
0x1800113f5  mov     [rbp+57h+string], r12
0x1800113f9  mov     r9d, 0Bh; unsigned int
0x1800113ff  lea     r8d, [r9+1]; unsigned int
0x180011403  lea     rdx, aUsercontext; "UserContext"
0x18001140a  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001140e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180011413  lea     r9, [rbp+57h+var_B0]
0x180011417  mov     r8, rbx
0x18001141a  mov     rdx, [rbp+57h+string]
0x18001141e  mov     rcx, rsi
0x180011421  mov     rax, rdi
0x180011424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011429  mov     ebx, eax
0x18001142b  test    eax, eax
0x18001142d  jns     short loc_180011472
0x18001142f  mov     rcx, [rbp+5Fh]; this
0x180011433  mov     r9d, eax; char *
0x180011436  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x18001143d  mov     edx, 47h ; 'G'; void *
0x180011442  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011447  lea     rcx, [rbp+57h+var_90]
0x18001144b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011450  lea     rcx, [rbp+57h+var_98]
0x180011454  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011459  lea     rcx, [rbp+57h+var_A0]
0x18001145d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011462  nop
0x180011463  lea     rcx, [rbp+57h+var_88]; this
0x180011467  call    ??1CAutoSRWSharedLock@@QEAA@XZ; CAutoSRWSharedLock::~CAutoSRWSharedLock(void)
0x18001146c  nop
0x18001146d  jmp     loc_180011BC0
0x180011472  mov     rsi, [r14+58h]
0x180011476  mov     r15d, 0Dh
0x18001147c  test    rsi, rsi
0x18001147f  jz      loc_180011509
0x180011485  mov     rdi, [rbp+57h+var_78]
0x180011489  mov     rax, [rdi]
0x18001148c  mov     rbx, [rax+50h]
0x180011490  mov     [rbp+57h+string], r12
0x180011494  lea     r9d, [r15-1]; unsigned int
0x180011498  mov     r8d, r15d; unsigned int
0x18001149b  lea     rdx, aSplashscreen; "SplashScreen"
0x1800114a2  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800114a6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800114ab  lea     r9, [rbp+57h+var_B0]
0x1800114af  mov     r8, rsi
0x1800114b2  mov     rdx, [rbp+57h+string]
0x1800114b6  mov     rcx, rdi
0x1800114b9  mov     rax, rbx
0x1800114bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114c1  mov     ebx, eax
0x1800114c3  test    eax, eax
0x1800114c5  jns     short loc_180011509
0x1800114c7  mov     rcx, [rbp+5Fh]; this
0x1800114cb  mov     r9d, eax; char *
0x1800114ce  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x1800114d5  lea     edx, [r15+3Eh]; void *
0x1800114d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800114de  lea     rcx, [rbp+57h+var_90]
0x1800114e2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
  ... truncated ...
```
