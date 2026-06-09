# PopulateExtensionProperties(Windows::Internal::StateRepository::IApplicationExtension *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::System::Internal::Launch::ExtensionProperties &)

- ea: `0x180024abc`
- end: `0x1800252f2`
- name: `?PopulateExtensionProperties@@YAJPEAUIApplicationExtension@StateRepository@Internal@Windows@@PEAUHSTRING__@@111AEAVExtensionProperties@Launch@3System@4@@Z`
- size: `2102`
- prototype: `__int64 __fastcall(struct Windows::Internal::StateRepository::IApplicationExtension *, HSTRING, HSTRING, HSTRING, HSTRING string, struct Windows::System::Internal::Launch::ExtensionProperties *)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180021ae4`
- `0x18002984c`
- `0x18002cf0c`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x180024abc`
- `0x1800252f8`
- `0x180027d80`
- `0x18002cec0`
- `0x180032c88`
- `0x1800343c0`
- `0x18008a030`
- `0x18008a9d8`
- `0x180107d20`
- `0x180111010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800252d8`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800252d8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025171`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025171`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024c67`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025198`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800251c7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800251f2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024c67`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025198`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800251c7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800251f2`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x180024b76`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x180024b76`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!GetExtensionProperty` at `0x180024e34`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!GetExtensionProperty` at `0x180024e99`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!GetExtensionProperty` at `0x180024ef9`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!GetExtensionProperty` at `0x180024f66`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!GetExtensionProperty` at `0x180024e34`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!GetExtensionProperty` at `0x180024e99`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!GetExtensionProperty` at `0x180024ef9`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!GetExtensionProperty` at `0x180024f66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024c45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024dc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024de7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024df7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024e05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024e49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024e5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024e6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024eae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024ebc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024eca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024f1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024f29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024f37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002517f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800251ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800251d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024c45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024dc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024de7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024df7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024e05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024e49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024e5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024e6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024eae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024ebc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024eca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024f1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024f29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024f37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002517f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800251ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800251d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024bbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024bec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024c19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024cb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024cf2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024d5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024f7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025086`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025146`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024bbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024bec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024c19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024cb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024cf2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024d5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024f7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025086`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025146`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180024bcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180024bfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180024cc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180024bcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180024bfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180024cc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024c8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024c8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800250cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800250f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800252e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800250cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800250f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800252e7`

## string_xrefs

- `0x1800251e6`: `Windows.AppUriHandler`
- `0x18002520d`: `Windows.AppUriHandler`
- `0x18002518c`: `Windows.Protocol`
- `0x180025257`: `Windows.Protocol`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall PopulateExtensionProperties(
        struct Windows::Internal::StateRepository::IApplicationExtension *a1,
        HSTRING a2,
        HSTRING a3,
        HSTRING a4,
        HSTRING string,
        HSTRING *a6)
{
  __int64 v9; // rax
  HRESULT v10; // ebx
  int v11; // eax
  HSTRING *v12; // rbx
  HSTRING *v13; // rbx
  __int64 (__fastcall *v14)(struct Windows::Internal::StateRepository::IApplicationExtension *, HSTRING *); // rbx
  const WCHAR *StringRawBuffer; // rax
  unsigned __int64 v16; // rsi
  HRESULT v17; // eax
  HSTRING *v18; // rbx
  HSTRING v19; // rdi
  HRESULT v20; // eax
  struct Windows::Foundation::Collections::IPropertySet *v21; // rcx
  void *v22; // rcx
  __int64 (__fastcall *v24)(struct Windows::Internal::StateRepository::IApplicationExtension *, HSTRING *); // rbx
  int v25; // eax
  struct Windows::Foundation::Collections::IPropertySet *v26; // rcx
  PCWSTR v27; // r12
  PCWSTR v28; // rdi
  PCWSTR v29; // rbx
  PCWSTR v30; // rax
  PCWSTR v31; // rdi
  HSTRING v32; // rsi
  PCWSTR v33; // rbx
  PCWSTR v34; // rax
  PCWSTR v35; // rdi
  PCWSTR v36; // rbx
  PCWSTR v37; // rax
  PCWSTR v38; // rdi
  PCWSTR v39; // rbx
  PCWSTR v40; // rax
  struct Windows::Foundation::Collections::IPropertySet *v41; // rcx
  void *v42; // rcx
  struct Windows::Foundation::Collections::IPropertySet *v43; // rcx
  struct Windows::Foundation::Collections::IPropertySet *v44; // rcx
  void *v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rdx
  const WCHAR *v48; // rax
  const WCHAR *v49; // rax
  const WCHAR *v50; // rax
  const wchar_t *bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v54; // [rsp+48h] [rbp-B8h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v55; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v56; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v57; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v58; // [rsp+68h] [rbp-98h]
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-90h] BYREF
  HSTRING v60; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v61[32]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v62[4104]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2118h] [rbp+2018h]

  v58 = a3;
  v56 = 0;
  pv = 0;
  v9 = *(_QWORD *)a1;
  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = (unsigned __int64)&pv;
  hstringHeader.Reserved.Reserved2[16] = 1;
  v10 = (*(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IApplicationExtension *, unsigned int *, char *))(v9 + 512))(
          a1,
          &v56,
          &hstringHeader.Reserved.Reserved2[8]);
  if ( hstringHeader.Reserved.Reserved2[16] )
  {
    v45 = *(void **)hstringHeader.Reserved.Reserved1;
    *(_QWORD *)hstringHeader.Reserved.Reserved1 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[8];
    if ( v45 )
      CoTaskMemFree(v45);
  }
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13F,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v10,
      (int)bIgnoreCase);
LABEL_47:
    v22 = pv;
    pv = 0;
LABEL_18:
    if ( v22 )
      CoTaskMemFree(v22);
    return (unsigned int)v10;
  }
  v55 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
  v10 = SRDictionaryToPropertySet(v56, pv, &v55);
  if ( v10 < 0 )
  {
    v46 = 321;
LABEL_57:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v46,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v10,
      (int)bIgnoreCase);
LABEL_60:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
    goto LABEL_47;
  }
  v11 = DeSerializePropertiesForExtension(v55, (struct Windows::System::Internal::Launch::ExtensionProperties *)a6);
  v10 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x142,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v11,
      (int)bIgnoreCase);
    v43 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v43 + 16LL))(v43);
    }
    goto LABEL_47;
  }
  if ( !a6[5] )
  {
    v24 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IApplicationExtension *, HSTRING *))(*(_QWORD *)a1 + 440LL);
    WindowsDeleteString(0);
    a6[5] = 0;
    v25 = v24(a1, a6 + 5);
    v10 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x146,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
        (const char *)(unsigned int)v25,
        (int)bIgnoreCase);
      v26 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v26 + 16LL))(v26);
      }
      goto LABEL_47;
    }
  }
  v12 = a6 + 2;
  if ( !a4 || a4 != *v12 )
  {
    WindowsDeleteString(*v12);
    *v12 = 0;
    v10 = WindowsDuplicateString(a4, a6 + 2);
    if ( v10 < 0 )
    {
      v46 = 329;
      goto LABEL_57;
    }
  }
  v13 = a6 + 4;
  if ( !string || string != *v13 )
  {
    WindowsDeleteString(*v13);
    *v13 = 0;
    v10 = WindowsDuplicateString(string, a6 + 4);
    if ( v10 < 0 )
    {
      v46 = 330;
      goto LABEL_57;
    }
  }
  v54 = 0;
  v14 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IApplicationExtension *, HSTRING *))(*(_QWORD *)a1 + 88LL);
  WindowsDeleteString(0);
  v54 = 0;
  v10 = v14(a1, &v54);
  if ( v10 < 0 )
  {
    v47 = 333;
    goto LABEL_59;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v54, 0);
  v16 = -1;
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"windows.fileTypeAssociation", -1, 1) != 2 )
  {
    v48 = WindowsGetStringRawBuffer(v54, 0);
    if ( CompareStringOrdinal(v48, -1, L"Windows.Protocol", -1, 1) == 2
      || (v49 = WindowsGetStringRawBuffer(v54, 0), CompareStringOrdinal(v49, -1, L"xbox.live", -1, 1) == 2) )
    {
      v60 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Protocol", 0x11u, 0x10u);
      v57 = v60;
      v10 = Microsoft::WRL::Wrappers::HString::Set(a6 + 3, &v57);
      if ( v10 >= 0 )
        goto LABEL_25;
      v47 = 343;
    }
    else
    {
      v50 = WindowsGetStringRawBuffer(v54, 0);
      if ( CompareStringOrdinal(v50, -1, L"Windows.AppUriHandler", -1, 1) != 2 )
        goto LABEL_25;
      v60 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.AppUriHandler",
        0x16u,
        0x15u);
      v57 = v60;
      v10 = Microsoft::WRL::Wrappers::HString::Set(a6 + 3, &v57);
      if ( v10 >= 0 )
        goto LABEL_25;
      v47 = 347;
    }
LABEL_59:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v47,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v10,
      (int)bIgnoreCase);
    WindowsDeleteString(v54);
    v54 = 0;
    goto LABEL_60;
  }
  v60 = 0;
  v17 = WindowsCreateStringReference(L"Windows.File", 0xCu, &hstringHeader, &v60);
  if ( v17 < 0 )
  {
    RaiseException(v17, 1u, 0, 0);
    __debugbreak();
  }
  v18 = a6 + 3;
  v19 = v60;
  if ( !v60 || v60 != *v18 )
  {
    WindowsDeleteString(*v18);
    *v18 = 0;
    v20 = WindowsDuplicateString(v19, a6 + 3);
    v10 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x152,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
        (const char *)(unsigned int)v20,
        bIgnoreCasea);
      WindowsDeleteString(v54);
      v54 = 0;
      v21 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v21 + 16LL))(v21);
      }
      v22 = pv;
      pv = 0;
      goto LABEL_18;
    }
  }
LABEL_25:
  v27 = WindowsGetStringRawBuffer(v54, 0);
  memset_0(v62, 0, 0x2002u);
  v28 = WindowsGetStringRawBuffer(a4, 0);
  v29 = WindowsGetStringRawBuffer(v58, 0);
  v30 = WindowsGetStringRawBuffer(a2, 0);
  if ( (int)GetExtensionProperty(v30, v29, v27, v28) >= 0 )
  {
    do
      ++v16;
    while ( v62[v16] );
    if ( v16 > 0xFFFFFFFF )
    {
      v10 = -2147024362;
    }
    else
    {
      v10 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)(a6 + 1), v62, v16);
      if ( v10 >= 0 )
        goto LABEL_26;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v10,
      (int)L"Logo");
    WindowsDeleteString(v54);
    v54 = 0;
    v44 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v44 + 16LL))(v44);
    }
    goto LABEL_47;
  }
LABEL_26:
  v31 = WindowsGetStringRawBuffer(a4, 0);
  v32 = v58;
  v33 = WindowsGetStringRawBuffer(v58, 0);
  v34 = WindowsGetStringRawBuffer(a2, 0);
  bIgnoreCase = L"DisplayName";
  if ( (int)GetExtensionProperty(v34, v33, v27, v31) >= 0 )
  {
    v10 = Microsoft::WRL::Wrappers::HString::Set<4097>(a6, v62);
    if ( v10 < 0 )
    {
      v47 = 362;
      goto LABEL_59;
    }
  }
  v35 = WindowsGetStringRawBuffer(a4, 0);
  v36 = WindowsGetStringRawBuffer(v32, 0);
  v37 = WindowsGetStringRawBuffer(a2, 0);
  bIgnoreCase = L"InfoTip";
  if ( (int)GetExtensionProperty(v37, v36, v27, v35) >= 0 )
  {
    v10 = Microsoft::WRL::Wrappers::HString::Set<4097>(a6 + 7, v62);
    if ( v10 < 0 )
    {
      v47 = 366;
      goto LABEL_59;
    }
  }
  memset(v61, 0, 22);
  v38 = WindowsGetStringRawBuffer(a4, 0);
  v39 = WindowsGetStringRawBuffer(v32, 0);
  v40 = WindowsGetStringRawBuffer(a2, 0);
  if ( (int)GetExtensionProperty(v40, v39, v27, v38) >= 0 )
    *((_DWORD *)a6 + 16) = _o__wtoi(v61);
  WindowsDeleteString(v54);
  v54 = 0;
  v41 = v55;
  if ( v55 )
  {
    v55 = 0;
    (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v41 + 16LL))(v41);
  }
  v42 = pv;
  pv = 0;
  if ( v42 )
    CoTaskMemFree(v42);
  return 0;
}

```

## disassembly

```asm
0x180024abc  push    rbp
0x180024abe  push    rbx
0x180024abf  push    rsi
0x180024ac0  push    rdi
0x180024ac1  push    r12
0x180024ac3  push    r13
0x180024ac5  push    r14
0x180024ac7  push    r15
0x180024ac9  lea     rbp, [rsp-1FD8h]
0x180024ad1  mov     eax, 20D8h
0x180024ad6  call    _alloca_probe
0x180024adb  sub     rsp, rax
0x180024ade  mov     rax, cs:__security_cookie
0x180024ae5  xor     rax, rsp
0x180024ae8  mov     [rbp+2010h+var_50], rax
0x180024aef  mov     r15, r9
0x180024af2  mov     [rsp+2110h+var_20A8], r8
0x180024af7  mov     r13, rdx
0x180024afa  mov     rsi, rcx
0x180024afd  mov     r12, [rbp+2010h+string]
0x180024b04  mov     r14, [rbp+2010h+arg_28]
0x180024b0b  xor     edi, edi
0x180024b0d  mov     [rsp+2110h+var_20B8], edi
0x180024b11  mov     [rsp+2110h+pv], rdi
0x180024b16  mov     rax, [rcx]
0x180024b19  lea     rcx, [rsp+2110h+pv]
0x180024b1e  mov     qword ptr [rsp+2110h+hstringHeader.Reserved], rcx
0x180024b23  mov     qword ptr [rsp+2110h+hstringHeader.Reserved+8], rdi
0x180024b28  mov     byte ptr [rbp+2010h+hstringHeader.Reserved+10h], 1
0x180024b2c  lea     r8, [rsp+2110h+hstringHeader.Reserved+8]
0x180024b31  lea     rdx, [rsp+2110h+var_20B8]
0x180024b36  mov     rcx, rsi
0x180024b39  mov     rax, [rax+200h]
0x180024b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b45  mov     ebx, eax
0x180024b47  cmp     byte ptr [rbp+2010h+hstringHeader.Reserved+10h], dil
0x180024b4b  jnz     loc_1800250AF
0x180024b51  test    ebx, ebx
0x180024b53  js      loc_1800250D6
0x180024b59  mov     [rsp+2110h+var_20C0], rdi
0x180024b5e  lea     rcx, [rsp+2110h+var_20C0]
0x180024b63  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180024b68  lea     r8, [rsp+2110h+var_20C0]
0x180024b6d  mov     rdx, [rsp+2110h+pv]
0x180024b72  mov     ecx, [rsp+2110h+var_20B8]
0x180024b76  call    cs:__imp_SRDictionaryToPropertySet
0x180024b7c  mov     ebx, eax
0x180024b7e  test    eax, eax
0x180024b80  js      loc_180025101
0x180024b86  mov     rdx, r14; struct Windows::System::Internal::Launch::ExtensionProperties *
0x180024b89  mov     rcx, [rsp+2110h+var_20C0]; struct Windows::Foundation::Collections::IPropertySet *
0x180024b8e  call    ?DeSerializePropertiesForExtension@@YAJPEAUIPropertySet@Collections@Foundation@Windows@@AEAVExtensionProperties@Launch@Internal@System@4@@Z; DeSerializePropertiesForExtension(Windows::Foundation::Collections::IPropertySet *,Windows::System::Internal::Launch::ExtensionProperties &)
0x180024b93  mov     ebx, eax
0x180024b95  test    eax, eax
0x180024b97  js      loc_180025019
0x180024b9d  lea     rdi, [r14+28h]
0x180024ba1  cmp     qword ptr [rdi], 0
0x180024ba5  jz      loc_180024D51
0x180024bab  xor     edi, edi
0x180024bad  lea     rbx, [r14+10h]
0x180024bb1  test    r15, r15
0x180024bb4  jnz     loc_180024FBC
0x180024bba  mov     rcx, [rbx]; string
0x180024bbd  call    cs:__imp_WindowsDeleteString
0x180024bc3  mov     [rbx], rdi
0x180024bc6  mov     rdx, rbx; newString
0x180024bc9  mov     rcx, r15; string
0x180024bcc  call    cs:__imp_WindowsDuplicateString
0x180024bd2  mov     ebx, eax
0x180024bd4  test    eax, eax
0x180024bd6  js      loc_180025160
0x180024bdc  lea     rbx, [r14+20h]
0x180024be0  test    r12, r12
0x180024be3  jnz     loc_180024FCA
0x180024be9  mov     rcx, [rbx]; string
0x180024bec  call    cs:__imp_WindowsDeleteString
0x180024bf2  mov     [rbx], rdi
0x180024bf5  mov     rdx, rbx; newString
0x180024bf8  mov     rcx, r12; string
0x180024bfb  call    cs:__imp_WindowsDuplicateString
0x180024c01  mov     ebx, eax
0x180024c03  test    eax, eax
0x180024c05  js      loc_180025108
0x180024c0b  mov     [rsp+2110h+var_20C8], rdi
0x180024c10  mov     rax, [rsi]
0x180024c13  mov     rbx, [rax+58h]
0x180024c17  xor     ecx, ecx; string
0x180024c19  call    cs:__imp_WindowsDeleteString
0x180024c1f  mov     [rsp+2110h+var_20C8], rdi
0x180024c24  lea     rdx, [rsp+2110h+var_20C8]
0x180024c29  mov     rcx, rsi
0x180024c2c  mov     rax, rbx
0x180024c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c34  mov     ebx, eax
0x180024c36  test    eax, eax
0x180024c38  js      loc_180025125
0x180024c3e  xor     edx, edx; length
0x180024c40  mov     rcx, [rsp+2110h+var_20C8]; string
0x180024c45  call    cs:__imp_WindowsGetStringRawBuffer
0x180024c4b  mov     ebx, 1
0x180024c50  mov     [rsp+2110h+bIgnoreCase], ebx; int
0x180024c54  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180024c58  mov     r9d, esi; cchCount2
0x180024c5b  lea     r8, aWindowsFiletyp; "windows.fileTypeAssociation"
0x180024c62  mov     edx, esi; cchCount1
0x180024c64  mov     rcx, rax; lpString1
0x180024c67  call    cs:__imp_CompareStringOrdinal
0x180024c6d  cmp     eax, 2
0x180024c70  jnz     loc_180025178
0x180024c76  mov     [rbp+2010h+var_2088], rdi
0x180024c7a  lea     r9, [rbp+2010h+var_2088]; string
0x180024c7e  lea     r8, [rsp+2110h+hstringHeader]; hstringHeader
0x180024c83  lea     edx, [rbx+0Bh]; length
0x180024c86  lea     rcx, aWindowsFile; "Windows.File"
0x180024c8d  call    cs:__imp_WindowsCreateStringReference
0x180024c93  test    eax, eax
0x180024c95  js      loc_180025167
0x180024c9b  lea     rbx, [r14+18h]
0x180024c9f  mov     rdi, [rbp+2010h+var_2088]
0x180024ca3  xor     r12d, r12d
0x180024ca6  test    rdi, rdi
0x180024ca9  jnz     loc_180024FD8
0x180024caf  mov     rcx, [rbx]; string
0x180024cb2  call    cs:__imp_WindowsDeleteString
0x180024cb8  mov     [rbx], r12
0x180024cbb  mov     rdx, rbx; newString
0x180024cbe  mov     rcx, rdi; string
0x180024cc1  call    cs:__imp_WindowsDuplicateString
0x180024cc7  mov     ebx, eax
0x180024cc9  test    eax, eax
0x180024ccb  jns     loc_180024DC1
0x180024cd1  mov     rcx, [rbp+2018h]; this
0x180024cd8  mov     r9d, eax; char *
0x180024cdb  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x180024ce2  mov     edx, 152h; void *
0x180024ce7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024cec  nop
0x180024ced  mov     rcx, [rsp+2110h+var_20C8]; string
0x180024cf2  call    cs:__imp_WindowsDeleteString
0x180024cf8  mov     [rsp+2110h+var_20C8], r12
0x180024cfd  mov     rcx, [rsp+2110h+var_20C0]
0x180024d02  test    rcx, rcx
0x180024d05  jz      short loc_180024D19
0x180024d07  mov     [rsp+2110h+var_20C0], r12
0x180024d0c  mov     rax, [rcx]
0x180024d0f  mov     rax, [rax+10h]
0x180024d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d18  nop
0x180024d19  mov     rcx, [rsp+2110h+pv]; pv
0x180024d1e  mov     [rsp+2110h+pv], r12
0x180024d23  test    rcx, rcx
0x180024d26  jnz     loc_1800250F6
0x180024d2c  mov     eax, ebx
0x180024d2e  mov     rcx, [rbp+2010h+var_50]
0x180024d35  xor     rcx, rsp; StackCookie
0x180024d38  call    __security_check_cookie
0x180024d3d  add     rsp, 20D8h
0x180024d44  pop     r15
0x180024d46  pop     r14
0x180024d48  pop     r13
0x180024d4a  pop     r12
0x180024d4c  pop     rdi
0x180024d4d  pop     rsi
0x180024d4e  pop     rbx
0x180024d4f  pop     rbp
0x180024d50  retn
0x180024d51  mov     rax, [rsi]
0x180024d54  mov     rbx, [rax+1B8h]
0x180024d5b  xor     ecx, ecx; string
0x180024d5d  call    cs:__imp_WindowsDeleteString
0x180024d63  mov     qword ptr [rdi], 0
0x180024d6a  mov     rdx, rdi
0x180024d6d  mov     rcx, rsi
0x180024d70  mov     rax, rbx
0x180024d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d78  mov     ebx, eax
0x180024d7a  xor     edi, edi
0x180024d7c  test    eax, eax
0x180024d7e  jns     loc_180024BAD
0x180024d84  mov     rcx, [rbp+2018h]; this
0x180024d8b  mov     r9d, eax; char *
0x180024d8e  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x180024d95  mov     edx, 146h; void *
0x180024d9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024d9f  nop
0x180024da0  mov     rcx, [rsp+2110h+var_20C0]
0x180024da5  test    rcx, rcx
0x180024da8  jz      short loc_180024DBC
0x180024daa  mov     [rsp+2110h+var_20C0], rdi
0x180024daf  mov     rax, [rcx]
0x180024db2  mov     rax, [rax+10h]
0x180024db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024dbb  nop
0x180024dbc  jmp     loc_180025051
0x180024dc1  xor     edx, edx; length
0x180024dc3  mov     rcx, [rsp+2110h+var_20C8]; string
0x180024dc8  call    cs:__imp_WindowsGetStringRawBuffer
0x180024dce  mov     r12, rax
0x180024dd1  xor     edx, edx; Val
0x180024dd3  mov     r8d, 2002h; Size
0x180024dd9  lea     rcx, [rbp+2010h+var_2060]; void *
0x180024ddd  call    memset_0
0x180024de2  xor     edx, edx; length
0x180024de4  mov     rcx, r15; string
0x180024de7  call    cs:__imp_WindowsGetStringRawBuffer
0x180024ded  mov     rdi, rax
0x180024df0  xor     edx, edx; length
0x180024df2  mov     rcx, [rsp+2110h+var_20A8]; string
0x180024df7  call    cs:__imp_WindowsGetStringRawBuffer
0x180024dfd  mov     rbx, rax
0x180024e00  xor     edx, edx; length
0x180024e02  mov     rcx, r13; string
0x180024e05  call    cs:__imp_WindowsGetStringRawBuffer
0x180024e0b  lea     rcx, [rbp+2010h+var_2060]
0x180024e0f  mov     [rsp+2110h+var_20E0], rcx
0x180024e14  mov     [rsp+2110h+var_20E8], 1001h
0x180024e1c  lea     rcx, aLogo; "Logo"
0x180024e23  mov     qword ptr [rsp+2110h+bIgnoreCase], rcx; int
0x180024e28  mov     r9, rdi
0x180024e2b  mov     r8, r12
0x180024e2e  mov     rdx, rbx
0x180024e31  mov     rcx, rax
0x180024e34  call    cs:__imp_GetExtensionProperty
0x180024e3a  xor     edi, edi
0x180024e3c  test    eax, eax
0x180024e3e  jns     loc_180024FE6
0x180024e44  xor     edx, edx; length
0x180024e46  mov     rcx, r15; string
0x180024e49  call    cs:__imp_WindowsGetStringRawBuffer
0x180024e4f  mov     rdi, rax
0x180024e52  xor     edx, edx; length
0x180024e54  mov     rsi, [rsp+2110h+var_20A8]
0x180024e59  mov     rcx, rsi; string
0x180024e5c  call    cs:__imp_WindowsGetStringRawBuffer
0x180024e62  mov     rbx, rax
0x180024e65  xor     edx, edx; length
0x180024e67  mov     rcx, r13; string
0x180024e6a  call    cs:__imp_WindowsGetStringRawBuffer
0x180024e70  lea     rcx, [rbp+2010h+var_2060]
0x180024e74  mov     [rsp+2110h+var_20E0], rcx
0x180024e79  mov     [rsp+2110h+var_20E8], 1001h
0x180024e81  lea     rcx, aDisplayname; "DisplayName"
0x180024e88  mov     qword ptr [rsp+2110h+bIgnoreCase], rcx
0x180024e8d  mov     r9, rdi
0x180024e90  mov     r8, r12
0x180024e93  mov     rdx, rbx
0x180024e96  mov     rcx, rax
0x180024e99  call    cs:__imp_GetExtensionProperty
0x180024e9f  xor     edi, edi
0x180024ea1  test    eax, eax
0x180024ea3  jns     loc_180025293
0x180024ea9  xor     edx, edx; length
0x180024eab  mov     rcx, r15; string
0x180024eae  call    cs:__imp_WindowsGetStringRawBuffer
0x180024eb4  mov     rdi, rax
0x180024eb7  xor     edx, edx; length
0x180024eb9  mov     rcx, rsi; string
0x180024ebc  call    cs:__imp_WindowsGetStringRawBuffer
0x180024ec2  mov     rbx, rax
0x180024ec5  xor     edx, edx; length
0x180024ec7  mov     rcx, r13; string
0x180024eca  call    cs:__imp_WindowsGetStringRawBuffer
0x180024ed0  lea     rcx, [rbp+2010h+var_2060]
0x180024ed4  mov     [rsp+2110h+var_20E0], rcx
0x180024ed9  mov     [rsp+2110h+var_20E8], 1001h
0x180024ee1  lea     rcx, aInfotip; "InfoTip"
0x180024ee8  mov     qword ptr [rsp+2110h+bIgnoreCase], rcx
0x180024eed  mov     r9, rdi
0x180024ef0  mov     r8, r12
0x180024ef3  mov     rdx, rbx
0x180024ef6  mov     rcx, rax
0x180024ef9  call    cs:__imp_GetExtensionProperty
0x180024eff  xor     edi, edi
0x180024f01  test    eax, eax
0x180024f03  jns     loc_1800252B3
0x180024f09  xorps   xmm0, xmm0
0x180024f0c  xor     eax, eax
0x180024f0e  movups  xmmword ptr [rbp+2010h+var_2080], xmm0
0x180024f12  mov     qword ptr [rbp+2010h+var_2080+0Eh], rax
0x180024f16  xor     edx, edx; length
0x180024f18  mov     rcx, r15; string
0x180024f1b  call    cs:__imp_WindowsGetStringRawBuffer
0x180024f21  mov     rdi, rax
0x180024f24  xor     edx, edx; length
0x180024f26  mov     rcx, rsi; string
0x180024f29  call    cs:__imp_WindowsGetStringRawBuffer
0x180024f2f  mov     rbx, rax
0x180024f32  xor     edx, edx; length
0x180024f34  mov     rcx, r13; string
0x180024f37  call    cs:__imp_WindowsGetStringRawBuffer
0x180024f3d  lea     rcx, [rbp+2010h+var_2080]
0x180024f41  mov     [rsp+2110h+var_20E0], rcx
0x180024f46  mov     [rsp+2110h+var_20E8], 0Bh
0x180024f4e  lea     rcx, aEditflags; "EditFlags"
0x180024f55  mov     qword ptr [rsp+2110h+bIgnoreCase], rcx
0x180024f5a  mov     r9, rdi
0x180024f5d  mov     r8, r12
0x180024f60  mov     rdx, rbx
0x180024f63  mov     rcx, rax
0x180024f66  call    cs:__imp_GetExtensionProperty
  ... truncated ...
```
