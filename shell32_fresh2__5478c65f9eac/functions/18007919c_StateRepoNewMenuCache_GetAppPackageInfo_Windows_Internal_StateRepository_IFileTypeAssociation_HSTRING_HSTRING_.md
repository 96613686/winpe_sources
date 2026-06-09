# StateRepoNewMenuCache::GetAppPackageInfo(Windows::Internal::StateRepository::IFileTypeAssociation *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x18007919c`
- end: `0x1800799ce`
- name: `?GetAppPackageInfo@StateRepoNewMenuCache@@AEAAJPEAUIFileTypeAssociation@StateRepository@Internal@Windows@@PEAPEAUHSTRING__@@11@Z`
- size: `2098`
- prototype: `__int64 __fastcall(StateRepoNewMenuCache *__hidden this, struct Windows::Internal::StateRepository::IFileTypeAssociation *, HSTRING *, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007b9dc`

## callees

- `0x18000f6cc`
- `0x180038608`
- `0x180079118`
- `0x180079180`
- `0x18007919c`
- `0x1801d0ed8`
- `0x1801d29a8`
- `0x180249490`
- `0x18024a53c`
- `0x1805b2010`

## import_xrefs

- `KERNELBASE!PackageNameAndPublisherIdFromFamilyName` at `0x18007934b`
- `KERNELBASE!PackageNameAndPublisherIdFromFamilyName` at `0x18007934b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079327`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079327`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800795ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079653`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800796c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800796d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800797b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007982c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007987a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007990a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800795ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079653`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800796c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800796d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800797b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007982c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007987a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007990a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180079483`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180079483`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007937f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007937f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800794b3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800794b3`

## string_xrefs

- `0x1800793b5`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007960a`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x1800796ec`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x180079789`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x180079847`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x180079895`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x180079922`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x180079942`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007996f`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x180079999`: `shell\shell32\unicpp\statereponewmenucache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall StateRepoNewMenuCache::GetAppPackageInfo(
        StateRepoNewMenuCache *this,
        struct Windows::Internal::StateRepository::IFileTypeAssociation *a2,
        HSTRING *a3,
        HSTRING *a4,
        HSTRING *a5)
{
  __int64 (__fastcall *v8)(struct Windows::Internal::StateRepository::IFileTypeAssociation *, __int64 *); // rbx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64 **); // rbx
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  __int64 *v19; // rdi
  __int64 (__fastcall *v20)(__int64 *, _QWORD **); // rbx
  int v21; // eax
  __int64 v22; // rax
  int v23; // eax
  const WCHAR *StringRawBuffer; // rax
  unsigned int v25; // eax
  __int64 v26; // rdx
  HSTRING v27; // rsi
  __int64 v28; // r9
  __int64 v29; // rdx
  _QWORD *v31; // rcx
  HRESULT v32; // eax
  int v33; // edx
  unsigned int v34; // r8d
  HSTRING v35; // rbx
  int ActivationFactory; // eax
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, __int64 *, _QWORD **); // rbx
  int v39; // eax
  __int64 v40; // rax
  int v41; // eax
  HSTRING v42; // rax
  HSTRING v43; // rcx
  HSTRING v44; // rax
  _QWORD *v45; // rdx
  __int64 v46; // rdx
  __int64 *v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  _QWORD *v50; // rcx
  __int64 v51; // rcx
  __int64 *v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  _QWORD *v55; // rcx
  __int64 *v56; // rcx
  __int64 v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  __int64 *v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 *v64; // rcx
  __int64 v65; // rcx
  __int64 v66; // rcx
  unsigned int packagePublisherId; // [rsp+20h] [rbp-E0h]
  HSTRING v68; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v69; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v71; // [rsp+58h] [rbp-A8h] BYREF
  __int64 *v72; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v73; // [rsp+68h] [rbp-98h] BYREF
  HSTRING v74; // [rsp+70h] [rbp-90h] BYREF
  __int64 v75; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v76; // [rsp+80h] [rbp-80h] BYREF
  __int64 v77; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v78; // [rsp+90h] [rbp-70h] BYREF
  HSTRING string; // [rsp+98h] [rbp-68h] BYREF
  HSTRING v80; // [rsp+A0h] [rbp-60h] BYREF
  UINT32 packagePublisherIdLength; // [rsp+A8h] [rbp-58h] BYREF
  UINT32 packageNameLength; // [rsp+ACh] [rbp-54h] BYREF
  WCHAR packageName[56]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR v84[16]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  *a3 = 0;
  *a5 = 0;
  *a4 = 0;
  v73 = 0;
  v8 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IFileTypeAssociation *, __int64 *))(*(_QWORD *)a2 + 96LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
  v9 = v8(a2, &v73);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF8,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)(unsigned int)v9,
      packagePublisherId);
    v63 = v73;
    if ( v73 )
    {
      v73 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
    }
    return v10;
  }
  v75 = 0;
  v11 = v73;
  v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v73 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
  v13 = v12(v11, &v75);
  v10 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFC,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)(unsigned int)v13,
      packagePublisherId);
    goto LABEL_16;
  }
  v72 = 0;
  v14 = v75;
  v15 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v75 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
  v16 = v15(v14, &v72);
  v10 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFF,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)(unsigned int)v16,
      packagePublisherId);
    goto LABEL_15;
  }
  v74 = 0;
  v17 = *v72;
  v74 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v17 + 112))(v72, &v74);
  v10 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)(unsigned int)v18,
      packagePublisherId);
    if ( v74 )
      WindowsDeleteString(v74);
    v64 = v72;
    if ( v72 )
    {
      v72 = 0;
      (*(void (__fastcall **)(__int64 *))(*v64 + 16))(v64);
    }
    v65 = v75;
    if ( v75 )
    {
      v75 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    }
    v66 = v73;
    if ( v73 )
    {
      v73 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
    }
    return v10;
  }
  v68 = 0;
  v76 = 0;
  v19 = v72;
  v20 = *(__int64 (__fastcall **)(__int64 *, _QWORD **))(*v72 + 72);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
  v21 = v20(v19, &v76);
  v10 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x106,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)(unsigned int)v21,
      packagePublisherId);
    v55 = v76;
    if ( v76 )
    {
      v76 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v55 + 16LL))(v55);
    }
    if ( v74 )
      WindowsDeleteString(v74);
    v56 = v72;
    if ( v72 )
    {
      v72 = 0;
      (*(void (__fastcall **)(__int64 *))(*v56 + 16))(v56);
    }
    v57 = v75;
    if ( v75 )
    {
      v75 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    }
    v58 = v73;
    if ( v73 )
    {
      v73 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    }
    return v10;
  }
  string = 0;
  v22 = *v76;
  string = 0;
  v23 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING *))(v22 + 88))(v76, &string);
  v10 = v23;
  if ( v23 < 0 )
  {
    v28 = (unsigned int)v23;
    v29 = 264;
    goto LABEL_12;
  }
  memset_0(packageName, 0, 0x66u);
  packageNameLength = 51;
  packagePublisherIdLength = 14;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v25 = PackageNameAndPublisherIdFromFamilyName(
          StringRawBuffer,
          &packageNameLength,
          packageName,
          &packagePublisherIdLength,
          v84);
  if ( v25 )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x10E,
            (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
            (const char *)v25,
            packagePublisherId);
    goto LABEL_13;
  }
  v26 = -1;
  do
    ++v26;
  while ( packageName[v26] );
  v69 = 0;
  WindowsCreateString(packageName, v26, &v69);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &v68,
    v69);
  v27 = v68;
  if ( !v68 )
  {
    v10 = -2147024882;
    v28 = 2147942414LL;
    v29 = 272;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)v28,
      packagePublisherId);
LABEL_13:
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
LABEL_14:
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v68);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v74);
LABEL_15:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
LABEL_16:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
    return v10;
  }
  if ( string )
    WindowsDeleteString(string);
  v31 = v76;
  if ( v76 )
  {
    v76 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
  }
  v77 = 0;
  v71 = 0;
  v32 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.PackageLocation", 0x30u, &hstringHeader, &v71);
  if ( v32 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v32, v33, v34);
LABEL_91:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11C,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)(unsigned int)v41,
      packagePublisherId);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v80);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
    goto LABEL_14;
  }
  v35 = v71;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
  ActivationFactory = RoGetActivationFactory(v35, &GUID_b8c8be3c_3a39_4e73_b4ba_c70d91d1b8ea, &v77);
  v10 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x116,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)(unsigned int)ActivationFactory,
      packagePublisherId);
    v59 = v77;
    if ( v77 )
    {
      v77 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    }
    WindowsDeleteString(v27);
    if ( v74 )
      WindowsDeleteString(v74);
    v60 = v72;
    if ( v72 )
    {
      v72 = 0;
      (*(void (__fastcall **)(__int64 *))(*v60 + 16))(v60);
    }
    v61 = v75;
    if ( v75 )
    {
      v75 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    }
    v62 = v73;
    if ( v73 )
    {
      v73 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
    }
    return v10;
  }
  v78 = 0;
  v37 = v77;
  v38 = *(__int64 (__fastcall **)(__int64, __int64 *, _QWORD **))(*(_QWORD *)v77 + 96LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
  v39 = v38(v37, v72, &v78);
  v10 = v39;
  if ( v39 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)(unsigned int)v39,
      packagePublisherId);
    v50 = v78;
    if ( v78 )
    {
      v78 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v50 + 16LL))(v50);
    }
    v51 = v77;
    if ( v77 )
    {
      v77 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    }
    WindowsDeleteString(v27);
    if ( v74 )
      WindowsDeleteString(v74);
    v52 = v72;
    if ( v72 )
    {
      v72 = 0;
      (*(void (__fastcall **)(__int64 *))(*v52 + 16))(v52);
    }
    v53 = v75;
    if ( v75 )
    {
      v75 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    }
    v54 = v73;
    if ( v73 )
    {
      v73 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    }
    return v10;
  }
  v80 = 0;
  v40 = *v78;
  v80 = 0;
  v41 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING *))(v40 + 88))(v78, &v80);
  v10 = v41;
  if ( v41 < 0 )
    goto LABEL_91;
  v42 = v74;
  v43 = 0;
  v74 = 0;
  *a3 = v42;
  v68 = 0;
  *a5 = v27;
  v44 = v80;
  v80 = 0;
  *a4 = v44;
  v45 = v78;
  if ( v78 )
  {
    v78 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v45 + 16LL))(v45);
    v43 = v74;
  }
  v46 = v77;
  if ( v77 )
  {
    v77 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    v43 = v74;
  }
  if ( v43 )
    WindowsDeleteString(v43);
  v47 = v72;
  if ( v72 )
  {
    v72 = 0;
    (*(void (__fastcall **)(__int64 *))(*v47 + 16))(v47);
  }
  v48 = v75;
  if ( v75 )
  {
    v75 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  }
  v49 = v73;
  if ( v73 )
  {
    v73 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  }
  return 0;
}

```

## disassembly

```asm
0x18007919c  mov     [rsp-8+arg_0], rbx
0x1800791a1  push    rbp
0x1800791a2  push    rsi
0x1800791a3  push    rdi
0x1800791a4  push    r12
0x1800791a6  push    r13
0x1800791a8  push    r14
0x1800791aa  push    r15
0x1800791ac  lea     rbp, [rsp-50h]
0x1800791b1  sub     rsp, 150h
0x1800791b8  mov     rax, cs:__security_cookie
0x1800791bf  xor     rax, rsp
0x1800791c2  mov     [rbp+80h+var_40], rax
0x1800791c6  mov     r15, r9
0x1800791c9  mov     r14, r8
0x1800791cc  mov     rdi, rdx
0x1800791cf  mov     r12, [rbp+80h+arg_20]
0x1800791d6  xor     r13d, r13d
0x1800791d9  mov     [r8], r13
0x1800791dc  mov     [r12], r13
0x1800791e0  mov     [r9], r13
0x1800791e3  mov     [rsp+180h+var_118], r13
0x1800791e8  mov     rax, [rdx]
0x1800791eb  mov     rbx, [rax+60h]
0x1800791ef  lea     rcx, [rsp+180h+var_118]
0x1800791f4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800791f9  lea     rdx, [rsp+180h+var_118]
0x1800791fe  mov     rcx, rdi
0x180079201  mov     rax, rbx
0x180079204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079209  mov     ebx, eax
0x18007920b  test    eax, eax
0x18007920d  js      loc_18007983D
0x180079213  mov     [rsp+180h+var_108], r13
0x180079218  mov     rdi, [rsp+180h+var_118]
0x18007921d  mov     rax, [rdi]
0x180079220  mov     rbx, [rax+48h]
0x180079224  lea     rcx, [rsp+180h+var_108]
0x180079229  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007922e  lea     rdx, [rsp+180h+var_108]
0x180079233  mov     rcx, rdi
0x180079236  mov     rax, rbx
0x180079239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007923e  mov     ebx, eax
0x180079240  test    eax, eax
0x180079242  js      loc_180079918
0x180079248  mov     [rsp+180h+var_120], r13
0x18007924d  mov     rdi, [rsp+180h+var_108]
0x180079252  mov     rax, [rdi]
0x180079255  mov     rbx, [rax+48h]
0x180079259  lea     rcx, [rsp+180h+var_120]
0x18007925e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180079263  lea     rdx, [rsp+180h+var_120]
0x180079268  mov     rcx, rdi
0x18007926b  mov     rax, rbx
0x18007926e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079273  mov     ebx, eax
0x180079275  test    eax, eax
0x180079277  js      loc_180079938
0x18007927d  mov     [rsp+180h+var_110], r13
0x180079282  mov     rcx, [rsp+180h+var_120]
0x180079287  mov     rax, [rcx]
0x18007928a  mov     [rsp+180h+var_110], r13
0x18007928f  lea     rdx, [rsp+180h+var_110]
0x180079294  mov     rax, [rax+70h]
0x180079298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007929d  mov     ebx, eax
0x18007929f  test    eax, eax
0x1800792a1  js      loc_18007988B
0x1800792a7  mov     [rsp+180h+var_150], r13
0x1800792ac  mov     [rbp+80h+var_100], r13
0x1800792b0  mov     rdi, [rsp+180h+var_120]
0x1800792b5  mov     rax, [rdi]
0x1800792b8  mov     rbx, [rax+48h]
0x1800792bc  lea     rcx, [rbp+80h+var_100]
0x1800792c0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800792c5  lea     rdx, [rbp+80h+var_100]
0x1800792c9  mov     rcx, rdi
0x1800792cc  mov     rax, rbx
0x1800792cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800792d4  mov     ebx, eax
0x1800792d6  test    eax, eax
0x1800792d8  js      loc_1800796E2
0x1800792de  mov     [rbp+80h+string], r13
0x1800792e2  mov     rcx, [rbp+80h+var_100]
0x1800792e6  mov     rax, [rcx]
0x1800792e9  mov     [rbp+80h+string], r13
0x1800792ed  lea     rdx, [rbp+80h+string]
0x1800792f1  mov     rax, [rax+58h]
0x1800792f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800792fa  mov     ebx, eax
0x1800792fc  test    eax, eax
0x1800792fe  js      loc_180079958
0x180079304  xor     edx, edx; Val
0x180079306  lea     r8d, [r13+66h]; Size
0x18007930a  lea     rcx, [rbp+80h+packageName]; void *
0x18007930e  call    memset_0
0x180079313  mov     [rbp+80h+packageNameLength], 33h ; '3'
0x18007931a  mov     [rbp+80h+packagePublisherIdLength], 0Eh
0x180079321  xor     edx, edx; length
0x180079323  mov     rcx, [rbp+80h+string]; string
0x180079327  call    cs:__imp_WindowsGetStringRawBuffer
0x18007932e  nop     dword ptr [rax+rax+00h]
0x180079333  lea     rcx, [rbp+80h+var_60]
0x180079337  mov     qword ptr [rsp+180h+packagePublisherId], rcx; int
0x18007933c  lea     r9, [rbp+80h+packagePublisherIdLength]; packagePublisherIdLength
0x180079340  lea     r8, [rbp+80h+packageName]; packageName
0x180079344  lea     rdx, [rbp+80h+packageNameLength]; packageNameLength
0x180079348  mov     rcx, rax; packageFamilyName
0x18007934b  call    cs:__imp_PackageNameAndPublisherIdFromFamilyName
0x180079352  nop     dword ptr [rax+rax+00h]
0x180079357  test    eax, eax
0x180079359  jnz     loc_180079965
0x18007935f  lea     rax, [rbp+80h+packageName]
0x180079363  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180079367  inc     rdx; length
0x18007936a  cmp     [rax+rdx*2], r13w
0x18007936f  jnz     short loc_180079367
0x180079371  mov     [rsp+180h+var_148], r13
0x180079376  lea     r8, [rsp+180h+var_148]; string
0x18007937b  lea     rcx, [rbp+80h+packageName]; sourceString
0x18007937f  call    cs:__imp_WindowsCreateString
0x180079386  nop     dword ptr [rax+rax+00h]
0x18007938b  mov     rdx, [rsp+180h+var_148]
0x180079390  lea     rcx, [rsp+180h+var_150]
0x180079395  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18007939a  mov     rsi, [rsp+180h+var_150]
0x18007939f  test    rsi, rsi
0x1800793a2  jnz     loc_18007943D
0x1800793a8  mov     ebx, 8007000Eh
0x1800793ad  mov     r9d, ebx; char *
0x1800793b0  mov     edx, 110h; void *
0x1800793b5  lea     r8, aShellShell32Un_12; "shell\\shell32\\unicpp\\statereponewmen"...
0x1800793bc  mov     rcx, [rbp+88h]; this
0x1800793c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800793c8  nop
0x1800793c9  lea     rcx, [rbp+80h+string]
0x1800793cd  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800793d2  nop
0x1800793d3  lea     rcx, [rbp+80h+var_100]
0x1800793d7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800793dc  nop
0x1800793dd  lea     rcx, [rsp+180h+var_150]
0x1800793e2  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800793e7  nop
0x1800793e8  lea     rcx, [rsp+180h+var_110]
0x1800793ed  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800793f2  nop
0x1800793f3  lea     rcx, [rsp+180h+var_120]
0x1800793f8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800793fd  nop
0x1800793fe  lea     rcx, [rsp+180h+var_108]
0x180079403  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180079408  nop
0x180079409  lea     rcx, [rsp+180h+var_118]
0x18007940e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180079413  mov     eax, ebx
0x180079415  mov     rcx, [rbp+80h+var_40]
0x180079419  xor     rcx, rsp; StackCookie
0x18007941c  call    __security_check_cookie
0x180079421  mov     rbx, [rsp+180h+arg_0]
0x180079429  add     rsp, 150h
0x180079430  pop     r15
0x180079432  pop     r14
0x180079434  pop     r13
0x180079436  pop     r12
0x180079438  pop     rdi
0x180079439  pop     rsi
0x18007943a  pop     rbp
0x18007943b  retn
0x18007943d  mov     rcx, [rbp+80h+string]; string
0x180079441  test    rcx, rcx
0x180079444  jnz     loc_1800795EF
0x18007944a  mov     rcx, [rbp+80h+var_100]
0x18007944e  test    rcx, rcx
0x180079451  jz      short loc_180079464
0x180079453  mov     [rbp+80h+var_100], r13
0x180079457  mov     rax, [rcx]
0x18007945a  mov     rax, [rax+10h]
0x18007945e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079463  nop
0x180079464  mov     [rbp+80h+var_F8], r13
0x180079468  mov     [rsp+180h+var_128], r13
0x18007946d  lea     r9, [rsp+180h+var_128]; string
0x180079472  lea     r8, [rsp+180h+hstringHeader]; hstringHeader
0x180079477  mov     edx, 30h ; '0'; length
0x18007947c  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_PackageLocation@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180079483  call    cs:__imp_WindowsCreateStringReference
0x18007948a  nop     dword ptr [rax+rax+00h]
0x18007948f  test    eax, eax
0x180079491  js      loc_180079987
0x180079497  mov     rbx, [rsp+180h+var_128]
0x18007949c  lea     rcx, [rbp+80h+var_F8]
0x1800794a0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800794a5  lea     r8, [rbp+80h+var_F8]
0x1800794a9  lea     rdx, _GUID_b8c8be3c_3a39_4e73_b4ba_c70d91d1b8ea
0x1800794b0  mov     rcx, rbx
0x1800794b3  call    cs:__imp_RoGetActivationFactory
0x1800794ba  nop     dword ptr [rax+rax+00h]
0x1800794bf  mov     ebx, eax
0x1800794c1  test    eax, eax
0x1800794c3  js      loc_18007977F
0x1800794c9  mov     [rbp+80h+var_F0], r13
0x1800794cd  mov     rdi, [rbp+80h+var_F8]
0x1800794d1  mov     rax, [rdi]
0x1800794d4  mov     rbx, [rax+60h]
0x1800794d8  lea     rcx, [rbp+80h+var_F0]
0x1800794dc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800794e1  lea     r8, [rbp+80h+var_F0]
0x1800794e5  mov     rdx, [rsp+180h+var_120]
0x1800794ea  mov     rcx, rdi
0x1800794ed  mov     rax, rbx
0x1800794f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800794f5  mov     ebx, eax
0x1800794f7  test    eax, eax
0x1800794f9  js      loc_180079600
0x1800794ff  mov     [rbp+80h+var_E0], r13
0x180079503  mov     rcx, [rbp+80h+var_F0]
0x180079507  mov     rax, [rcx]
0x18007950a  mov     [rbp+80h+var_E0], r13
0x18007950e  lea     rdx, [rbp+80h+var_E0]
0x180079512  mov     rax, [rax+58h]
0x180079516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007951b  mov     ebx, eax
0x18007951d  test    eax, eax
0x18007951f  js      loc_18007998F
0x180079525  mov     rax, [rsp+180h+var_110]
0x18007952a  mov     rcx, r13
0x18007952d  mov     [rsp+180h+var_110], rcx
0x180079532  mov     [r14], rax
0x180079535  mov     [rsp+180h+var_150], r13
0x18007953a  mov     [r12], rsi
0x18007953e  mov     rax, [rbp+80h+var_E0]
0x180079542  mov     [rbp+80h+var_E0], r13
0x180079546  mov     [r15], rax
0x180079549  mov     rdx, [rbp+80h+var_F0]
0x18007954d  test    rdx, rdx
0x180079550  jz      short loc_18007956A
0x180079552  mov     [rbp+80h+var_F0], r13
0x180079556  mov     rax, [rdx]
0x180079559  mov     rcx, rdx
0x18007955c  mov     rax, [rax+10h]
0x180079560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079565  mov     rcx, [rsp+180h+var_110]
0x18007956a  mov     rdx, [rbp+80h+var_F8]
0x18007956e  test    rdx, rdx
0x180079571  jz      short loc_18007958B
0x180079573  mov     [rbp+80h+var_F8], r13
0x180079577  mov     rax, [rdx]
0x18007957a  mov     rcx, rdx
0x18007957d  mov     rax, [rax+10h]
0x180079581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079586  mov     rcx, [rsp+180h+var_110]; string
0x18007958b  test    rcx, rcx
0x18007958e  jnz     loc_1800796C3
0x180079594  mov     rcx, [rsp+180h+var_120]
0x180079599  test    rcx, rcx
0x18007959c  jz      short loc_1800795B0
0x18007959e  mov     [rsp+180h+var_120], r13
0x1800795a3  mov     rax, [rcx]
0x1800795a6  mov     rax, [rax+10h]
0x1800795aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800795af  nop
0x1800795b0  mov     rcx, [rsp+180h+var_108]
0x1800795b5  test    rcx, rcx
0x1800795b8  jz      short loc_1800795CC
0x1800795ba  mov     [rsp+180h+var_108], r13
0x1800795bf  mov     rax, [rcx]
0x1800795c2  mov     rax, [rax+10h]
0x1800795c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800795cb  nop
0x1800795cc  mov     rcx, [rsp+180h+var_118]
0x1800795d1  test    rcx, rcx
0x1800795d4  jz      short loc_1800795E8
0x1800795d6  mov     [rsp+180h+var_118], r13
0x1800795db  mov     rax, [rcx]
0x1800795de  mov     rax, [rax+10h]
0x1800795e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800795e7  nop
0x1800795e8  xor     eax, eax
0x1800795ea  jmp     loc_180079415
0x1800795ef  call    cs:__imp_WindowsDeleteString
0x1800795f6  nop     dword ptr [rax+rax+00h]
0x1800795fb  jmp     loc_18007944A
0x180079600  mov     rcx, [rbp+88h]; this
0x180079607  mov     r9d, ebx; char *
0x18007960a  lea     r8, aShellShell32Un_12; "shell\\shell32\\unicpp\\statereponewmen"...
0x180079611  mov     edx, 119h; void *
0x180079616  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007961b  nop
0x18007961c  mov     rcx, [rbp+80h+var_F0]
0x180079620  test    rcx, rcx
0x180079623  jz      short loc_180079636
0x180079625  mov     [rbp+80h+var_F0], r13
0x180079629  mov     rax, [rcx]
0x18007962c  mov     rax, [rax+10h]
0x180079630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079635  nop
0x180079636  mov     rcx, [rbp+80h+var_F8]
0x18007963a  test    rcx, rcx
  ... truncated ...
```
