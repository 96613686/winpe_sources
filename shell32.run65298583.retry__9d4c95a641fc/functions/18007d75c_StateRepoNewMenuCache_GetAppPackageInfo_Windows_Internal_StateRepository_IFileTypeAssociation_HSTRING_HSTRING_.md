# StateRepoNewMenuCache::GetAppPackageInfo(Windows::Internal::StateRepository::IFileTypeAssociation *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x18007d75c`
- end: `0x18007df57`
- name: `?GetAppPackageInfo@StateRepoNewMenuCache@@AEAAJPEAUIFileTypeAssociation@StateRepository@Internal@Windows@@PEAPEAUHSTRING__@@11@Z`
- size: `2043`
- prototype: `__int64 __fastcall(StateRepoNewMenuCache *__hidden this, struct Windows::Internal::StateRepository::IFileTypeAssociation *, HSTRING *, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007fdc8`

## callees

- `0x18000f05c`
- `0x18003cd64`
- `0x18007d704`
- `0x18007d75c`
- `0x1801bb5e4`
- `0x180233280`
- `0x1802342fc`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007df50`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007df50`
- `KERNELBASE!PackageNameAndPublisherIdFromFamilyName` at `0x18007d905`
- `KERNELBASE!PackageNameAndPublisherIdFromFamilyName` at `0x18007d905`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007d8e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007d8e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d97c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d997`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007db8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dbea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dc56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dc61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dd3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ddad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ddf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007de7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007deac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007deca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d97c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d997`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007db8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dbea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dc56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dc61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dd3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ddad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ddf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007de7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007deac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007deca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007d933`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007d933`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007da09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007da09`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007da33`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007da33`

## string_xrefs

- `0x18007d95f`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007dba1`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007dc73`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007dd10`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007ddc2`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007de0a`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007de91`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007dedf`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007deff`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007df2c`: `shell\shell32\unicpp\statereponewmenucache.cpp`

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
  _QWORD *v30; // rcx
  signed int v31; // eax
  HSTRING v32; // rbx
  int ActivationFactory; // eax
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, __int64 *, _QWORD **); // rbx
  int v36; // eax
  __int64 v37; // rax
  int v38; // eax
  HSTRING v39; // rax
  HSTRING v40; // rcx
  HSTRING v41; // rax
  _QWORD *v42; // rdx
  __int64 v43; // rdx
  __int64 *v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  _QWORD *v48; // rcx
  __int64 v49; // rcx
  __int64 *v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  _QWORD *v53; // rcx
  __int64 *v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rcx
  __int64 *v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rcx
  __int64 *v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // rcx
  unsigned int packagePublisherId; // [rsp+20h] [rbp-E0h]
  HSTRING v66; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v67; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v69; // [rsp+58h] [rbp-A8h] BYREF
  __int64 *v70; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v71; // [rsp+68h] [rbp-98h] BYREF
  HSTRING v72; // [rsp+70h] [rbp-90h] BYREF
  __int64 v73; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v74; // [rsp+80h] [rbp-80h] BYREF
  __int64 v75; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v76; // [rsp+90h] [rbp-70h] BYREF
  HSTRING string; // [rsp+98h] [rbp-68h] BYREF
  HSTRING v78; // [rsp+A0h] [rbp-60h] BYREF
  UINT32 packagePublisherIdLength; // [rsp+A8h] [rbp-58h] BYREF
  UINT32 packageNameLength; // [rsp+ACh] [rbp-54h] BYREF
  WCHAR packageName[56]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR v82[16]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  *a3 = 0;
  *a5 = 0;
  *a4 = 0;
  v71 = 0;
  v8 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IFileTypeAssociation *, __int64 *))(*(_QWORD *)a2 + 96LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
  v9 = v8(a2, &v71);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF8,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)(unsigned int)v9,
      packagePublisherId);
    v61 = v71;
    if ( v71 )
    {
      v71 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    }
    return v10;
  }
  v73 = 0;
  v11 = v71;
  v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v71 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
  v13 = v12(v11, &v73);
  v10 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFC,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)(unsigned int)v13,
      packagePublisherId);
    goto LABEL_19;
  }
  v70 = 0;
  v14 = v73;
  v15 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v73 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
  v16 = v15(v14, &v70);
  v10 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFF,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)(unsigned int)v16,
      packagePublisherId);
LABEL_18:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
LABEL_19:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
    return v10;
  }
  v72 = 0;
  v17 = *v70;
  v72 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v17 + 112))(v70, &v72);
  v10 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)(unsigned int)v18,
      packagePublisherId);
    if ( v72 )
      WindowsDeleteString(v72);
    v62 = v70;
    if ( v70 )
    {
      v70 = 0;
      (*(void (__fastcall **)(__int64 *))(*v62 + 16))(v62);
    }
    v63 = v73;
    if ( v73 )
    {
      v73 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
    }
    v64 = v71;
    if ( v71 )
    {
      v71 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    }
    return v10;
  }
  v66 = 0;
  v74 = 0;
  v19 = v70;
  v20 = *(__int64 (__fastcall **)(__int64 *, _QWORD **))(*v70 + 72);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
  v21 = v20(v19, &v74);
  v10 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x106,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)(unsigned int)v21,
      packagePublisherId);
    v53 = v74;
    if ( v74 )
    {
      v74 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v53 + 16LL))(v53);
    }
    if ( v72 )
      WindowsDeleteString(v72);
    v54 = v70;
    if ( v70 )
    {
      v70 = 0;
      (*(void (__fastcall **)(__int64 *))(*v54 + 16))(v54);
    }
    v55 = v73;
    if ( v73 )
    {
      v73 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    }
    v56 = v71;
    if ( v71 )
    {
      v71 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    }
    return v10;
  }
  string = 0;
  v22 = *v74;
  string = 0;
  v23 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING *))(v22 + 88))(v74, &string);
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
          v82);
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
  v67 = 0;
  WindowsCreateString(packageName, v26, &v67);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &v66,
    v67);
  v27 = v66;
  if ( !v66 )
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
    if ( string )
      WindowsDeleteString(string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
LABEL_16:
    if ( v72 )
      WindowsDeleteString(v72);
    goto LABEL_18;
  }
  if ( string )
    WindowsDeleteString(string);
  v30 = v74;
  if ( v74 )
  {
    v74 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
  }
  v75 = 0;
  v69 = 0;
  v31 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.PackageLocation", 0x30u, &hstringHeader, &v69);
  if ( v31 < 0 )
  {
    RaiseException(v31, 1u, 0, 0);
    JUMPOUT(0x18007DF56LL);
  }
  v32 = v69;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
  ActivationFactory = RoGetActivationFactory(v32, &GUID_b8c8be3c_3a39_4e73_b4ba_c70d91d1b8ea, &v75);
  v10 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x116,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)(unsigned int)ActivationFactory,
      packagePublisherId);
    v57 = v75;
    if ( v75 )
    {
      v75 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    }
    WindowsDeleteString(v27);
    if ( v72 )
      WindowsDeleteString(v72);
    v58 = v70;
    if ( v70 )
    {
      v70 = 0;
      (*(void (__fastcall **)(__int64 *))(*v58 + 16))(v58);
    }
    v59 = v73;
    if ( v73 )
    {
      v73 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    }
    v60 = v71;
    if ( v71 )
    {
      v71 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
    }
    return v10;
  }
  v76 = 0;
  v34 = v75;
  v35 = *(__int64 (__fastcall **)(__int64, __int64 *, _QWORD **))(*(_QWORD *)v75 + 96LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
  v36 = v35(v34, v70, &v76);
  v10 = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)(unsigned int)v36,
      packagePublisherId);
    v48 = v76;
    if ( v76 )
    {
      v76 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
    }
    v49 = v75;
    if ( v75 )
    {
      v75 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    }
    WindowsDeleteString(v27);
    if ( v72 )
      WindowsDeleteString(v72);
    v50 = v70;
    if ( v70 )
    {
      v70 = 0;
      (*(void (__fastcall **)(__int64 *))(*v50 + 16))(v50);
    }
    v51 = v73;
    if ( v73 )
    {
      v73 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    }
    v52 = v71;
    if ( v71 )
    {
      v71 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    }
    return v10;
  }
  v78 = 0;
  v37 = *v76;
  v78 = 0;
  v38 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING *))(v37 + 88))(v76, &v78);
  v10 = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11C,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)(unsigned int)v38,
      packagePublisherId);
    if ( v78 )
      WindowsDeleteString(v78);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
    WindowsDeleteString(v27);
    goto LABEL_16;
  }
  v39 = v72;
  v40 = 0;
  v72 = 0;
  *a3 = v39;
  v66 = 0;
  *a5 = v27;
  v41 = v78;
  v78 = 0;
  *a4 = v41;
  v42 = v76;
  if ( v76 )
  {
    v76 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v42 + 16LL))(v42);
    v40 = v72;
  }
  v43 = v75;
  if ( v75 )
  {
    v75 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    v40 = v72;
  }
  if ( v40 )
    WindowsDeleteString(v40);
  v44 = v70;
  if ( v70 )
  {
    v70 = 0;
    (*(void (__fastcall **)(__int64 *))(*v44 + 16))(v44);
  }
  v45 = v73;
  if ( v73 )
  {
    v73 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  v46 = v71;
  if ( v71 )
  {
    v71 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  return 0;
}

```

## disassembly

```asm
0x18007d75c  mov     [rsp-8+arg_0], rbx
0x18007d761  push    rbp
0x18007d762  push    rsi
0x18007d763  push    rdi
0x18007d764  push    r12
0x18007d766  push    r13
0x18007d768  push    r14
0x18007d76a  push    r15
0x18007d76c  lea     rbp, [rsp-50h]
0x18007d771  sub     rsp, 150h
0x18007d778  mov     rax, cs:__security_cookie
0x18007d77f  xor     rax, rsp
0x18007d782  mov     [rbp+80h+var_40], rax
0x18007d786  mov     r15, r9
0x18007d789  mov     r14, r8
0x18007d78c  mov     rdi, rdx
0x18007d78f  mov     r12, [rbp+80h+arg_20]
0x18007d796  xor     r13d, r13d
0x18007d799  mov     [r8], r13
0x18007d79c  mov     [r12], r13
0x18007d7a0  mov     [r9], r13
0x18007d7a3  mov     [rsp+180h+var_118], r13
0x18007d7a8  mov     rax, [rdx]
0x18007d7ab  mov     rbx, [rax+60h]
0x18007d7af  lea     rcx, [rsp+180h+var_118]
0x18007d7b4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007d7b9  lea     rdx, [rsp+180h+var_118]
0x18007d7be  mov     rcx, rdi
0x18007d7c1  mov     rax, rbx
0x18007d7c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d7c9  mov     ebx, eax
0x18007d7cb  test    eax, eax
0x18007d7cd  js      loc_18007DDB8
0x18007d7d3  mov     [rsp+180h+var_108], r13
0x18007d7d8  mov     rdi, [rsp+180h+var_118]
0x18007d7dd  mov     rax, [rdi]
0x18007d7e0  mov     rbx, [rax+48h]
0x18007d7e4  lea     rcx, [rsp+180h+var_108]
0x18007d7e9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007d7ee  lea     rdx, [rsp+180h+var_108]
0x18007d7f3  mov     rcx, rdi
0x18007d7f6  mov     rax, rbx
0x18007d7f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d7fe  mov     ebx, eax
0x18007d800  test    eax, eax
0x18007d802  js      loc_18007DED5
0x18007d808  mov     [rsp+180h+var_120], r13
0x18007d80d  mov     rdi, [rsp+180h+var_108]
0x18007d812  mov     rax, [rdi]
0x18007d815  mov     rbx, [rax+48h]
0x18007d819  lea     rcx, [rsp+180h+var_120]
0x18007d81e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007d823  lea     rdx, [rsp+180h+var_120]
0x18007d828  mov     rcx, rdi
0x18007d82b  mov     rax, rbx
0x18007d82e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d833  mov     ebx, eax
0x18007d835  test    eax, eax
0x18007d837  js      loc_18007DEF5
0x18007d83d  mov     [rsp+180h+var_110], r13
0x18007d842  mov     rcx, [rsp+180h+var_120]
0x18007d847  mov     rax, [rcx]
0x18007d84a  mov     [rsp+180h+var_110], r13
0x18007d84f  lea     rdx, [rsp+180h+var_110]
0x18007d854  mov     rax, [rax+70h]
0x18007d858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d85d  mov     ebx, eax
0x18007d85f  test    eax, eax
0x18007d861  js      loc_18007DE00
0x18007d867  mov     [rsp+180h+var_150], r13
0x18007d86c  mov     [rbp+80h+var_100], r13
0x18007d870  mov     rdi, [rsp+180h+var_120]
0x18007d875  mov     rax, [rdi]
0x18007d878  mov     rbx, [rax+48h]
0x18007d87c  lea     rcx, [rbp+80h+var_100]
0x18007d880  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007d885  lea     rdx, [rbp+80h+var_100]
0x18007d889  mov     rcx, rdi
0x18007d88c  mov     rax, rbx
0x18007d88f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d894  mov     ebx, eax
0x18007d896  test    eax, eax
0x18007d898  js      loc_18007DC69
0x18007d89e  mov     [rbp+80h+string], r13
0x18007d8a2  mov     rcx, [rbp+80h+var_100]
0x18007d8a6  mov     rax, [rcx]
0x18007d8a9  mov     [rbp+80h+string], r13
0x18007d8ad  lea     rdx, [rbp+80h+string]
0x18007d8b1  mov     rax, [rax+58h]
0x18007d8b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d8ba  mov     ebx, eax
0x18007d8bc  test    eax, eax
0x18007d8be  js      loc_18007DF15
0x18007d8c4  xor     edx, edx; Val
0x18007d8c6  lea     r8d, [r13+66h]; Size
0x18007d8ca  lea     rcx, [rbp+80h+packageName]; void *
0x18007d8ce  call    memset_0
0x18007d8d3  mov     [rbp+80h+packageNameLength], 33h ; '3'
0x18007d8da  mov     [rbp+80h+packagePublisherIdLength], 0Eh
0x18007d8e1  xor     edx, edx; length
0x18007d8e3  mov     rcx, [rbp+80h+string]; string
0x18007d8e7  call    cs:__imp_WindowsGetStringRawBuffer
0x18007d8ed  lea     rcx, [rbp+80h+var_60]
0x18007d8f1  mov     qword ptr [rsp+180h+packagePublisherId], rcx; unsigned int
0x18007d8f6  lea     r9, [rbp+80h+packagePublisherIdLength]; packagePublisherIdLength
0x18007d8fa  lea     r8, [rbp+80h+packageName]; packageName
0x18007d8fe  lea     rdx, [rbp+80h+packageNameLength]; packageNameLength
0x18007d902  mov     rcx, rax; packageFamilyName
0x18007d905  call    cs:__imp_PackageNameAndPublisherIdFromFamilyName
0x18007d90b  test    eax, eax
0x18007d90d  jnz     loc_18007DF22
0x18007d913  lea     rax, [rbp+80h+packageName]
0x18007d917  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18007d91b  inc     rdx; length
0x18007d91e  cmp     [rax+rdx*2], r13w
0x18007d923  jnz     short loc_18007D91B
0x18007d925  mov     [rsp+180h+var_148], r13
0x18007d92a  lea     r8, [rsp+180h+var_148]; string
0x18007d92f  lea     rcx, [rbp+80h+packageName]; sourceString
0x18007d933  call    cs:__imp_WindowsCreateString
0x18007d939  mov     rdx, [rsp+180h+var_148]
0x18007d93e  lea     rcx, [rsp+180h+var_150]
0x18007d943  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18007d948  mov     rsi, [rsp+180h+var_150]
0x18007d94d  test    rsi, rsi
0x18007d950  jnz     short loc_18007D9C3
0x18007d952  mov     ebx, 8007000Eh
0x18007d957  mov     r9d, ebx; char *
0x18007d95a  mov     edx, 110h; void *
0x18007d95f  lea     r8, aShellShell32Un_12; "shell\\shell32\\unicpp\\statereponewmen"...
0x18007d966  mov     rcx, [rbp+88h]; this
0x18007d96d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d972  nop
0x18007d973  mov     rcx, [rbp+80h+string]; string
0x18007d977  test    rcx, rcx
0x18007d97a  jz      short loc_18007D983
0x18007d97c  call    cs:__imp_WindowsDeleteString
0x18007d982  nop
0x18007d983  lea     rcx, [rbp+80h+var_100]
0x18007d987  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007d98c  nop
0x18007d98d  mov     rcx, [rsp+180h+var_110]; string
0x18007d992  test    rcx, rcx
0x18007d995  jz      short loc_18007D99E
0x18007d997  call    cs:__imp_WindowsDeleteString
0x18007d99d  nop
0x18007d99e  lea     rcx, [rsp+180h+var_120]
0x18007d9a3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007d9a8  nop
0x18007d9a9  lea     rcx, [rsp+180h+var_108]
0x18007d9ae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007d9b3  nop
0x18007d9b4  lea     rcx, [rsp+180h+var_118]
0x18007d9b9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007d9be  jmp     loc_18007DC4F
0x18007d9c3  mov     rcx, [rbp+80h+string]; string
0x18007d9c7  test    rcx, rcx
0x18007d9ca  jnz     loc_18007DB8B
0x18007d9d0  mov     rcx, [rbp+80h+var_100]
0x18007d9d4  test    rcx, rcx
0x18007d9d7  jz      short loc_18007D9EA
0x18007d9d9  mov     [rbp+80h+var_100], r13
0x18007d9dd  mov     rax, [rcx]
0x18007d9e0  mov     rax, [rax+10h]
0x18007d9e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d9e9  nop
0x18007d9ea  mov     [rbp+80h+var_F8], r13
0x18007d9ee  mov     [rsp+180h+var_128], r13
0x18007d9f3  lea     r9, [rsp+180h+var_128]; string
0x18007d9f8  lea     r8, [rsp+180h+hstringHeader]; hstringHeader
0x18007d9fd  mov     edx, 30h ; '0'; length
0x18007da02  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_PackageLocation@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18007da09  call    cs:__imp_WindowsCreateStringReference
0x18007da0f  test    eax, eax
0x18007da11  js      loc_18007DF44
0x18007da17  mov     rbx, [rsp+180h+var_128]
0x18007da1c  lea     rcx, [rbp+80h+var_F8]
0x18007da20  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007da25  lea     r8, [rbp+80h+var_F8]
0x18007da29  lea     rdx, _GUID_b8c8be3c_3a39_4e73_b4ba_c70d91d1b8ea
0x18007da30  mov     rcx, rbx
0x18007da33  call    cs:__imp_RoGetActivationFactory
0x18007da39  mov     ebx, eax
0x18007da3b  test    eax, eax
0x18007da3d  js      loc_18007DD06
0x18007da43  mov     [rbp+80h+var_F0], r13
0x18007da47  mov     rdi, [rbp+80h+var_F8]
0x18007da4b  mov     rax, [rdi]
0x18007da4e  mov     rbx, [rax+60h]
0x18007da52  lea     rcx, [rbp+80h+var_F0]
0x18007da56  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007da5b  lea     r8, [rbp+80h+var_F0]
0x18007da5f  mov     rdx, [rsp+180h+var_120]
0x18007da64  mov     rcx, rdi
0x18007da67  mov     rax, rbx
0x18007da6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007da6f  mov     ebx, eax
0x18007da71  test    eax, eax
0x18007da73  js      loc_18007DB97
0x18007da79  mov     [rbp+80h+var_E0], r13
0x18007da7d  mov     rcx, [rbp+80h+var_F0]
0x18007da81  mov     rax, [rcx]
0x18007da84  mov     [rbp+80h+var_E0], r13
0x18007da88  lea     rdx, [rbp+80h+var_E0]
0x18007da8c  mov     rax, [rax+58h]
0x18007da90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007da95  mov     ebx, eax
0x18007da97  test    eax, eax
0x18007da99  js      loc_18007DE87
0x18007da9f  mov     rax, [rsp+180h+var_110]
0x18007daa4  mov     rcx, r13
0x18007daa7  mov     [rsp+180h+var_110], rcx
0x18007daac  mov     [r14], rax
0x18007daaf  mov     [rsp+180h+var_150], r13
0x18007dab4  mov     [r12], rsi
0x18007dab8  mov     rax, [rbp+80h+var_E0]
0x18007dabc  mov     [rbp+80h+var_E0], r13
0x18007dac0  mov     [r15], rax
0x18007dac3  mov     rdx, [rbp+80h+var_F0]
0x18007dac7  test    rdx, rdx
0x18007daca  jz      short loc_18007DAE4
0x18007dacc  mov     [rbp+80h+var_F0], r13
0x18007dad0  mov     rax, [rdx]
0x18007dad3  mov     rcx, rdx
0x18007dad6  mov     rax, [rax+10h]
0x18007dada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dadf  mov     rcx, [rsp+180h+var_110]
0x18007dae4  mov     rdx, [rbp+80h+var_F8]
0x18007dae8  test    rdx, rdx
0x18007daeb  jz      short loc_18007DB05
0x18007daed  mov     [rbp+80h+var_F8], r13
0x18007daf1  mov     rax, [rdx]
0x18007daf4  mov     rcx, rdx
0x18007daf7  mov     rax, [rax+10h]
0x18007dafb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007db00  mov     rcx, [rsp+180h+var_110]; string
0x18007db05  test    rcx, rcx
0x18007db08  jnz     loc_18007DC56
0x18007db0e  mov     rcx, [rsp+180h+var_120]
0x18007db13  test    rcx, rcx
0x18007db16  jz      short loc_18007DB2A
0x18007db18  mov     [rsp+180h+var_120], r13
0x18007db1d  mov     rax, [rcx]
0x18007db20  mov     rax, [rax+10h]
0x18007db24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007db29  nop
0x18007db2a  mov     rcx, [rsp+180h+var_108]
0x18007db2f  test    rcx, rcx
0x18007db32  jz      short loc_18007DB46
0x18007db34  mov     [rsp+180h+var_108], r13
0x18007db39  mov     rax, [rcx]
0x18007db3c  mov     rax, [rax+10h]
0x18007db40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007db45  nop
0x18007db46  mov     rcx, [rsp+180h+var_118]
0x18007db4b  test    rcx, rcx
0x18007db4e  jz      short loc_18007DB62
0x18007db50  mov     [rsp+180h+var_118], r13
0x18007db55  mov     rax, [rcx]
0x18007db58  mov     rax, [rax+10h]
0x18007db5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007db61  nop
0x18007db62  xor     eax, eax
0x18007db64  mov     rcx, [rbp+80h+var_40]
0x18007db68  xor     rcx, rsp; StackCookie
0x18007db6b  call    __security_check_cookie
0x18007db70  mov     rbx, [rsp+180h+arg_0]
0x18007db78  add     rsp, 150h
0x18007db7f  pop     r15
0x18007db81  pop     r14
0x18007db83  pop     r13
0x18007db85  pop     r12
0x18007db87  pop     rdi
0x18007db88  pop     rsi
0x18007db89  pop     rbp
0x18007db8a  retn
0x18007db8b  call    cs:__imp_WindowsDeleteString
0x18007db91  nop
0x18007db92  jmp     loc_18007D9D0
0x18007db97  mov     rcx, [rbp+88h]; this
0x18007db9e  mov     r9d, ebx; char *
0x18007dba1  lea     r8, aShellShell32Un_12; "shell\\shell32\\unicpp\\statereponewmen"...
0x18007dba8  mov     edx, 119h; void *
0x18007dbad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007dbb2  nop
0x18007dbb3  mov     rcx, [rbp+80h+var_F0]
0x18007dbb7  test    rcx, rcx
0x18007dbba  jz      short loc_18007DBCD
0x18007dbbc  mov     [rbp+80h+var_F0], r13
0x18007dbc0  mov     rax, [rcx]
0x18007dbc3  mov     rax, [rax+10h]
0x18007dbc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dbcc  nop
0x18007dbcd  mov     rcx, [rbp+80h+var_F8]
0x18007dbd1  test    rcx, rcx
0x18007dbd4  jz      short loc_18007DBE7
0x18007dbd6  mov     [rbp+80h+var_F8], r13
0x18007dbda  mov     rax, [rcx]
0x18007dbdd  mov     rax, [rax+10h]
0x18007dbe1  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
