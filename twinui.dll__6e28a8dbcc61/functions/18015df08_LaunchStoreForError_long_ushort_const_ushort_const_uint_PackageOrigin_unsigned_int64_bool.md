# LaunchStoreForError(long,ushort const *,ushort const *,uint,_PackageOrigin,unsigned __int64,bool)

- ea: `0x18015df08`
- end: `0x18015e91c`
- name: `?LaunchStoreForError@@YAJJPEBG0IW4_PackageOrigin@@_K_N@Z`
- size: `2580`
- prototype: `int __high(int, const unsigned __int16 *, const unsigned __int16 *, unsigned int, enum _PackageOrigin, unsigned __int64, bool)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18015aec0`

## callees

- `0x180008acc`
- `0x18000b7e8`
- `0x18000c350`
- `0x180027cc8`
- `0x180027ee4`
- `0x180029a88`
- `0x180034cdc`
- `0x18003c5e4`
- `0x18004719c`
- `0x180052980`
- `0x18005fe34`
- `0x180074798`
- `0x1800a301c`
- `0x1800f279c`
- `0x1801045d4`
- `0x18013d330`
- `0x18015a87c`
- `0x18015a8b8`
- `0x18015df08`
- `0x18015e924`
- `0x1803a3010`

## import_xrefs

- `SHELL32!ShellExecuteW` at `0x18015e1e4`
- `SHELL32!ShellExecuteW` at `0x18015e1e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015e1a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015e611`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015e656`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015e6c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015e7cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015e840`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015e8d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015e1a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015e611`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015e656`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015e6c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015e7cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015e840`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015e8d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015e638`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015e638`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18015e1bd`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18015e1bd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18015e3e7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18015e3e7`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18015e2f9`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18015e2f9`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18015df5b`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18015df5b`
- `api-ms-win-shell-namespace-l1-1-1!SHCreateShellItemArrayFromShellItem` at `0x18015e345`
- `api-ms-win-shell-namespace-l1-1-1!SHCreateShellItemArrayFromShellItem` at `0x18015e345`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x18015e648`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x18015e648`

## string_xrefs

- `0x18015e428`: `Windows.Foundation.ExtensionCatalog`
- `0x18015df8e`: `Microsoft.GamingServices_8wekyb3d8bbwe`
- `0x18015e4ba`: `Windows.Protocol`
- `0x18015e706`: `Windows.Protocol`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
int __fastcall LaunchStoreForError(int a1, const WCHAR *a2, int a3, __int64 a4, __int64 a5, __int64 a6, char a7)
{
  unsigned int v10; // eax
  int v12; // eax
  int v13; // ebx
  char v14; // r15
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _QWORD, __int64 *); // rbx
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rdx
  unsigned __int64 v21; // rcx
  bool IgnoreListForPFN; // al
  bool v23; // di
  char v24; // cl
  int v25; // edx
  int v26; // eax
  HINSTANCE v27; // rbx
  int v28; // eax
  __int64 v29; // rdx
  HRESULT v30; // eax
  HRESULT v31; // eax
  int v32; // eax
  HRESULT v33; // eax
  int v34; // eax
  __int64 v35; // rsi
  __int64 (__fastcall *v36)(__int64, __int64, __int64, __int64 *); // rdi
  __int64 v37; // rbx
  int v38; // eax
  unsigned __int64 v39; // r9
  __int64 v40; // rdx
  __int64 v41; // rdi
  __int64 (__fastcall *v42)(__int64, __int64 *); // rbx
  int v43; // eax
  __int64 v44; // rdi
  __int64 (__fastcall *v45)(__int64, void **); // rbx
  int v46; // eax
  void *v47; // rdi
  unsigned int (__fastcall *v48)(void *, __int64, struct IInspectable **); // rbx
  int v49; // eax
  const WCHAR *StringRawBuffer; // rax
  LPVOID v51; // rsi
  __int64 (__fastcall *v52)(LPVOID, const WCHAR *, __int64, _QWORD, __int64, __int64, int, __int64, unsigned int *); // rdi
  __int64 v53; // rbx
  unsigned int lpDirectory; // [rsp+20h] [rbp-E0h]
  int lpDirectorya; // [rsp+20h] [rbp-E0h]
  char v56; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v57[7]; // [rsp+51h] [rbp-AFh] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v59; // [rsp+60h] [rbp-A0h] BYREF
  void *ppv; // [rsp+68h] [rbp-98h] BYREF
  void *v61; // [rsp+70h] [rbp-90h] BYREF
  __int64 v62; // [rsp+78h] [rbp-88h] BYREF
  __int64 v63; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v64; // [rsp+88h] [rbp-78h] BYREF
  __int64 v65; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v66; // [rsp+98h] [rbp-68h] BYREF
  __int64 v67; // [rsp+A0h] [rbp-60h] BYREF
  void *v68; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING v69; // [rsp+B0h] [rbp-50h] BYREF
  LPCWSTR lpFile; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v71; // [rsp+C0h] [rbp-40h]
  __int64 v72; // [rsp+C8h] [rbp-38h]
  __int64 v73; // [rsp+D0h] [rbp-30h] BYREF
  const WCHAR *v74; // [rsp+D8h] [rbp-28h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+E0h] [rbp-20h] BYREF
  void *v76; // [rsp+E8h] [rbp-18h] BYREF
  int v77; // [rsp+F0h] [rbp-10h]
  __int64 v78; // [rsp+F8h] [rbp-8h] BYREF
  RoVariant *v79; // [rsp+100h] [rbp+0h]
  struct IInspectable *v80; // [rsp+108h] [rbp+8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+110h] [rbp+10h] BYREF
  __int64 v82; // [rsp+128h] [rbp+28h]
  HSTRING_HEADER v83; // [rsp+130h] [rbp+30h] BYREF
  __int64 v84; // [rsp+148h] [rbp+48h]
  WCHAR packageFamilyName[72]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v74 = a2;
  packageFamilyNameLength = 65;
  v10 = PackageFamilyNameFromFullName(a2, &packageFamilyNameLength, packageFamilyName);
  if ( v10 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xAD,
             (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
             (const char *)v10,
             lpDirectory);
  if ( a7 )
  {
    v12 = StringCchPrintfW(packageFamilyName, 0x41u, L"%s", L"Microsoft.GamingServices_8wekyb3d8bbwe");
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB3,
        (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
        (const char *)(unsigned int)v12,
        lpDirectory);
      return v13;
    }
    goto LABEL_10;
  }
  v14 = 0;
  if ( a1 == -2147217664 )
  {
    a1 = -2147009284;
  }
  else if ( a1 == -2147217656 )
  {
    a1 = -2147009284;
LABEL_10:
    v14 = 1;
  }
  v73 = 0;
  v82 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.Package",
    0x29u,
    0x28u);
  v15 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
          v82,
          &v73);
  v13 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
      (const char *)(unsigned int)v15,
      lpDirectory);
LABEL_82:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
    return v13;
  }
  v59 = 0;
  v16 = v73;
  v17 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v73 + 176LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
  v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v74);
  v19 = v17(v16, *(_QWORD *)(v18 + 24), &v59);
  v13 = v19;
  if ( v19 < 0 )
  {
    v20 = 210;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
      (const char *)(unsigned int)v19,
      lpDirectory);
LABEL_81:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
    goto LABEL_82;
  }
  v56 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v59 + 320LL))(v59, &v56);
  v13 = v19;
  if ( v19 < 0 )
  {
    v20 = 212;
    goto LABEL_15;
  }
  string = 0;
  v66 = 0;
  v21 = -1;
  do
    ++v21;
  while ( packageFamilyName[v21] );
  if ( (int)ULongLongToULong(v21, &v66) >= 0 )
    Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, packageFamilyName, v66);
  IgnoreListForPFN = QueryIgnoreListForPFN((struct Microsoft::WRL::Wrappers::HString *)&string);
  v23 = IgnoreListForPFN;
  v24 = v56;
  if ( v56 )
  {
    v25 = 0;
    if ( !v14 && !IgnoreListForPFN )
    {
      lpFile = 0;
      v71 = 0;
      v72 = 0;
      v26 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
              &lpFile,
              L"msxbox://remediation/?PFN=%s&PN=%s&appUserModelId=%s&errorCode=%d&appxState=%d",
              packageFamilyName,
              a2);
      v13 = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE0,
          (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
          (const char *)(unsigned int)v26,
          a3);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpFile);
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_81;
      }
      CoInitializeEx(0, 6u);
      v27 = ShellExecuteW(0, L"open", lpFile, 0, 0, 1);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpFile);
      v25 = -2147467259;
      if ( (unsigned __int64)v27 > 0x20 )
        v25 = 0;
      v24 = v56;
    }
    if ( v24 && !v14 && !v23 && v25 >= 0 )
      goto LABEL_70;
  }
  lpFile = 0;
  v71 = 0;
  v72 = 0;
  if ( v14 )
  {
    v28 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
            &lpFile,
            L"ms-windows-store://pdp/?PFN=%s",
            packageFamilyName);
    v13 = v28;
    if ( v28 < 0 )
    {
      v29 = 289;
      goto LABEL_37;
    }
  }
  else
  {
    lpDirectory = a3;
    v28 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
            &lpFile,
            L"ms-windows-store:Remediation?PFN=%s&PN=%s&appUserModelId=%s&errorCode=%d&appxState=%d",
            packageFamilyName,
            a2);
    v13 = v28;
    if ( v28 < 0 )
    {
      v29 = 285;
LABEL_37:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
        (const char *)(unsigned int)v28,
        lpDirectory);
LABEL_80:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpFile);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_81;
    }
  }
  ppv = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
  v30 = SHCreateItemFromParsingName(lpFile, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
  v13 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x125,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
      (const char *)(unsigned int)v30,
      lpDirectory);
LABEL_79:
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
    goto LABEL_80;
  }
  v61 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
  v31 = SHCreateShellItemArrayFromShellItem((IShellItem *)ppv, &GUID_b63ea76d_1f85_456f_a19c_48159efa858b, &v61);
  v13 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x128,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
      (const char *)(unsigned int)v31,
      lpDirectory);
LABEL_78:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
    goto LABEL_79;
  }
  v62 = 0;
  v68 = v61;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v62);
  v32 = Microsoft::WRL::Details::MakeAndInitialize<CProtocolActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,IShellItemArray *>(
          &v62,
          &v68);
  v13 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12B,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
      (const char *)(unsigned int)v32,
      lpDirectory);
LABEL_77:
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v62);
    goto LABEL_78;
  }
  v64 = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v64);
  v33 = CoCreateInstance(&CLSID_ApplicationActivationManager, 0, 1u, &GUID_54e4c428_d1d4_47d4_ade6_46c829114a7d, &v64);
  v13 = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12F,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
      (const char *)(unsigned int)v33,
      lpDirectorya);
LABEL_76:
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v64);
    goto LABEL_77;
  }
  v67 = 0;
  v82 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Foundation.ExtensionCatalog",
    0x24u,
    0x23u);
  v34 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionCatalog>>(v82, &v67);
  v13 = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x133,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
      (const char *)(unsigned int)v34,
      lpDirectorya);
LABEL_75:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
    goto LABEL_76;
  }
  v63 = 0;
  v35 = v67;
  v36 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v67 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
  v82 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Microsoft.WindowsStore_8wekyb3d8bbwe",
    0x25u,
    0x24u);
  v37 = v82;
  v84 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v83, L"Windows.Protocol", 0x11u, 0x10u);
  v38 = v36(v35, v84, v37, &v63);
  v13 = v38;
  if ( v38 < 0 )
  {
    v39 = (unsigned int)v38;
    v40 = 314;
LABEL_73:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v40,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
      (const char *)v39,
      lpDirectorya);
LABEL_74:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    goto LABEL_75;
  }
  v78 = 0;
  v74 = 0;
  v57[0] = 0;
  while ( 1 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v63 + 56LL))(v63, v57);
    if ( v13 < 0 )
    {
      v39 = (unsigned int)v13;
      v40 = 348;
      goto LABEL_73;
    }
    if ( !v57[0] )
      goto LABEL_63;
    v65 = 0;
    v41 = v63;
    v42 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v63 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
    v43 = v42(v41, &v65);
    v13 = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x145,
        (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
        (const char *)(unsigned int)v43,
        lpDirectorya);
      goto LABEL_69;
    }
    v68 = 0;
    v44 = v65;
    v45 = *(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v65 + 128LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
    v46 = v45(v44, &v68);
    v13 = v46;
    if ( v46 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x149,
        (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
        (const char *)(unsigned int)v46,
        lpDirectorya);
      goto LABEL_66;
    }
    v76 = 0;
    v77 = 0;
    v47 = v68;
    v48 = *(unsigned int (__fastcall **)(void *, __int64, struct IInspectable **))(*(_QWORD *)v68 + 48LL);
    v79 = (RoVariant *)&v76;
    v80 = 0;
    v82 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Name", 5u, 4u);
    LODWORD(v48) = v48(v47, v82, &v80) >> 31;
    v82 = 0;
    RoVariant::Attach(v79, v80);
    if ( (unsigned __int8)v48 != 1 )
      break;
LABEL_61:
    RoVariant::~RoVariant((RoVariant *)&v76);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
    (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v63 + 64LL))(v63, v57);
  }
  v69 = 0;
  v83.Reserved.Reserved1 = v76;
  *(_DWORD *)&v83.Reserved.Reserved2[8] = v77;
  WindowsDeleteString(0);
  v69 = 0;
  v49 = RoVariant::Accessor::GetString((RoVariant::Accessor *)&v83, &v69);
  v13 = v49;
  if ( v49 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14E,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
      (const char *)(unsigned int)v49,
      lpDirectorya);
    WindowsDeleteString(v69);
    v69 = 0;
    RoVariant::~RoVariant((RoVariant *)&v76);
LABEL_66:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
LABEL_69:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
    goto LABEL_74;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v69, 0);
  if ( StrCmpIW(L"ms-windows-store", StringRawBuffer) )
  {
    WindowsDeleteString(v69);
    goto LABEL_61;
  }
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v65 + 48LL))(v65, &v78);
  (*(void (__fastcall **)(__int64, const WCHAR **))(*(_QWORD *)v65 + 64LL))(v65, &v74);
  WindowsDeleteString(v69);
  v69 = 0;
  RoVariant::~RoVariant((RoVariant *)&v76);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
LABEL_63:
  v66 = 0;
  v51 = v64;
  v52 = *(__int64 (__fastcall **)(LPVOID, const WCHAR *, __int64, _QWORD, __int64, __int64, int, __int64, unsigned int *))(*(_QWORD *)v64 + 120LL);
  v53 = v62;
  v82 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Protocol", 0x11u, 0x10u);
  LODWORD(v53) = v52(v51, v74, v78, 0, v82, v53, 0x80000, a6, &v66);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v64);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v62);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpFile);
  if ( (int)v53 < 0 )
    goto LABEL_71;
LABEL_70:
  a1 = 2556504;
LABEL_71:
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
  return a1;
}

```

## disassembly

```asm
0x18015df08  mov     [rsp-8+arg_0], rbx
0x18015df0d  push    rbp
0x18015df0e  push    rsi
0x18015df0f  push    rdi
0x18015df10  push    r12
0x18015df12  push    r13
0x18015df14  push    r14
0x18015df16  push    r15
0x18015df18  lea     rbp, [rsp-0F0h]
0x18015df20  sub     rsp, 1F0h
0x18015df27  mov     rax, cs:__security_cookie
0x18015df2e  xor     rax, rsp
0x18015df31  mov     [rbp+120h+var_40], rax
0x18015df38  mov     esi, r9d
0x18015df3b  mov     r13, r8
0x18015df3e  mov     r12, rdx
0x18015df41  mov     r14d, ecx
0x18015df44  mov     [rbp+120h+var_148], rdx
0x18015df48  mov     ebx, 41h ; 'A'
0x18015df4d  mov     [rbp+120h+packageFamilyNameLength], ebx
0x18015df50  lea     r8, [rbp+120h+packageFamilyName]; packageFamilyName
0x18015df54  lea     rdx, [rbp+120h+packageFamilyNameLength]; packageFamilyNameLength
0x18015df58  mov     rcx, r12; packageFullName
0x18015df5b  call    cs:__imp_PackageFamilyNameFromFullName
0x18015df61  xor     edi, edi
0x18015df63  test    eax, eax
0x18015df65  jz      short loc_18015DF85
0x18015df67  mov     rcx, [rbp+128h]; this
0x18015df6e  mov     r9d, eax; char *
0x18015df71  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x18015df78  lea     edx, [rbx+6Ch]; void *
0x18015df7b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18015df80  jmp     loc_18015E8F2
0x18015df85  cmp     [rbp+120h+arg_30], dil
0x18015df8c  jz      short loc_18015DFCE
0x18015df8e  lea     r9, aMicrosoftGamin; "Microsoft.GamingServices_8wekyb3d8bbwe"
0x18015df95  lea     r8, aS_5; "%s"
0x18015df9c  mov     rdx, rbx; unsigned __int64
0x18015df9f  lea     rcx, [rbp+120h+packageFamilyName]; unsigned __int16 *
0x18015dfa3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18015dfa8  mov     ebx, eax
0x18015dfaa  test    eax, eax
0x18015dfac  jns     short loc_18015DFF1
0x18015dfae  mov     rcx, [rbp+128h]; this
0x18015dfb5  mov     r9d, eax; char *
0x18015dfb8  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x18015dfbf  mov     edx, 0B3h; void *
0x18015dfc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015dfc9  jmp     loc_18015E8F0
0x18015dfce  mov     r15b, dil
0x18015dfd1  cmp     r14d, 80040F00h
0x18015dfd8  jnz     short loc_18015DFE2
0x18015dfda  mov     r14d, 80073CFCh
0x18015dfe0  jmp     short loc_18015DFF4
0x18015dfe2  cmp     r14d, 80040F08h
0x18015dfe9  jnz     short loc_18015DFF4
0x18015dfeb  mov     r14d, 80073CFCh
0x18015dff1  mov     r15b, 1
0x18015dff4  mov     [rbp+120h+var_150], rdi
0x18015dff8  mov     [rbp+120h+var_F8], rdi
0x18015dffc  mov     r9d, 28h ; '('; unsigned int
0x18015e002  lea     r8d, [r9+1]; unsigned int
0x18015e006  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18015e00d  lea     rcx, [rbp+120h+hstringHeader]; hstringHeader
0x18015e011  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18015e016  lea     rdx, [rbp+120h+var_150]
0x18015e01a  mov     rcx, [rbp+120h+var_F8]
0x18015e01e  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x18015e023  mov     ebx, eax
0x18015e025  test    eax, eax
0x18015e027  jns     short loc_18015E049
0x18015e029  mov     rcx, [rbp+128h]; this
0x18015e030  mov     r9d, eax; char *
0x18015e033  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x18015e03a  mov     edx, 0D0h; void *
0x18015e03f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015e044  jmp     loc_18015E8E7
0x18015e049  mov     [rsp+220h+var_1C0], rdi
0x18015e04e  mov     rdi, [rbp+120h+var_150]
0x18015e052  mov     rax, [rdi]
0x18015e055  mov     rbx, [rax+0B0h]
0x18015e05c  lea     rcx, [rsp+220h+var_1C0]
0x18015e061  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18015e066  lea     rdx, [rbp+120h+var_148]
0x18015e06a  lea     rcx, [rbp+120h+hstringHeader]
0x18015e06e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18015e073  nop
0x18015e074  lea     r8, [rsp+220h+var_1C0]
0x18015e079  mov     rdx, [rax+18h]
0x18015e07d  mov     rcx, rdi
0x18015e080  mov     rax, rbx
0x18015e083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015e088  mov     ebx, eax
0x18015e08a  xor     edi, edi
0x18015e08c  test    eax, eax
0x18015e08e  jns     short loc_18015E0B0
0x18015e090  mov     edx, 0D2h; void *
0x18015e095  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x18015e09c  mov     r9d, eax; char *
0x18015e09f  mov     rcx, [rbp+128h]; this
0x18015e0a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015e0ab  jmp     loc_18015E8DC
0x18015e0b0  mov     [rsp+220h+var_1D0], dil
0x18015e0b5  mov     rcx, [rsp+220h+var_1C0]
0x18015e0ba  mov     rax, [rcx]
0x18015e0bd  lea     rdx, [rsp+220h+var_1D0]
0x18015e0c2  mov     rax, [rax+140h]
0x18015e0c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015e0ce  mov     ebx, eax
0x18015e0d0  test    eax, eax
0x18015e0d2  jns     short loc_18015E0DB
0x18015e0d4  mov     edx, 0D4h
0x18015e0d9  jmp     short loc_18015E095
0x18015e0db  xor     ebx, ebx
0x18015e0dd  mov     [rsp+220h+string], rbx
0x18015e0e2  mov     [rbp+120h+var_188], ebx
0x18015e0e5  lea     rax, [rbp+120h+packageFamilyName]
0x18015e0e9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18015e0ed  inc     rcx; unsigned __int64
0x18015e0f0  cmp     [rax+rcx*2], bx
0x18015e0f4  jnz     short loc_18015E0ED
0x18015e0f6  lea     rdx, [rbp+120h+var_188]; unsigned int *
0x18015e0fa  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18015e0ff  test    eax, eax
0x18015e101  js      short loc_18015E115
0x18015e103  mov     r8d, [rbp+120h+var_188]; unsigned int
0x18015e107  lea     rdx, [rbp+120h+packageFamilyName]; unsigned __int16 *
0x18015e10b  lea     rcx, [rsp+220h+string]; this
0x18015e110  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18015e115  lea     rcx, [rsp+220h+string]; struct Microsoft::WRL::Wrappers::HString *
0x18015e11a  call    ?QueryIgnoreListForPFN@@YA_NAEAVHString@Wrappers@WRL@Microsoft@@@Z; QueryIgnoreListForPFN(Microsoft::WRL::Wrappers::HString &)
0x18015e11f  mov     dil, al
0x18015e122  mov     cl, [rsp+220h+var_1D0]
0x18015e126  test    cl, cl
0x18015e128  jz      loc_18015E220
0x18015e12e  mov     edx, ebx
0x18015e130  test    r15b, r15b
0x18015e133  jnz     loc_18015E20A
0x18015e139  test    al, al
0x18015e13b  jnz     loc_18015E20A
0x18015e141  mov     [rbp+120h+lpFile], rbx
0x18015e145  mov     [rbp+120h+var_160], rbx
0x18015e149  mov     [rbp+120h+var_158], rbx
0x18015e14d  mov     [rsp+220h+var_1F0], esi
0x18015e151  mov     [rsp+220h+nShowCmd], ebx
0x18015e155  mov     [rsp+220h+lpDirectory], r13; int
0x18015e15a  mov     r9, r12
0x18015e15d  lea     r8, [rbp+120h+packageFamilyName]
0x18015e161  lea     rdx, aMsxboxRemediat; "msxbox://remediation/?PFN=%s&PN=%s&appU"...
0x18015e168  lea     rcx, [rbp+120h+lpFile]
0x18015e16c  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18015e171  mov     ebx, eax
0x18015e173  test    eax, eax
0x18015e175  jns     short loc_18015E1B6
0x18015e177  mov     rcx, [rbp+128h]; this
0x18015e17e  mov     r9d, eax; char *
0x18015e181  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x18015e188  mov     edx, 0E0h; void *
0x18015e18d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015e192  nop
0x18015e193  lea     rcx, [rbp+120h+lpFile]
0x18015e197  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015e19c  nop
0x18015e19d  mov     rcx, [rsp+220h+string]; string
0x18015e1a2  call    cs:__imp_WindowsDeleteString
0x18015e1a8  mov     [rsp+220h+string], 0
0x18015e1b1  jmp     loc_18015E8DC
0x18015e1b6  mov     edx, 6; dwCoInit
0x18015e1bb  xor     ecx, ecx; pvReserved
0x18015e1bd  call    cs:__imp_CoInitializeEx
0x18015e1c3  mov     [rsp+220h+nShowCmd], 1; nShowCmd
0x18015e1cb  mov     [rsp+220h+lpDirectory], 0; lpDirectory
0x18015e1d4  xor     r9d, r9d; lpParameters
0x18015e1d7  mov     r8, [rbp+120h+lpFile]; lpFile
0x18015e1db  lea     rdx, pwszSrc; "open"
0x18015e1e2  xor     ecx, ecx; hwnd
0x18015e1e4  call    cs:__imp_ShellExecuteW
0x18015e1ea  mov     rbx, rax
0x18015e1ed  lea     rcx, [rbp+120h+lpFile]
0x18015e1f1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015e1f6  mov     edx, 80004005h
0x18015e1fb  xor     ecx, ecx
0x18015e1fd  cmp     rbx, 20h ; ' '
0x18015e201  cmova   edx, ecx
0x18015e204  mov     cl, [rsp+220h+var_1D0]
0x18015e208  xor     ebx, ebx
0x18015e20a  test    cl, cl
0x18015e20c  jz      short loc_18015E220
0x18015e20e  test    r15b, r15b
0x18015e211  jnz     short loc_18015E220
0x18015e213  test    dil, dil
0x18015e216  jnz     short loc_18015E220
0x18015e218  test    edx, edx
0x18015e21a  jns     loc_18015E832
0x18015e220  test    sil, 4
0x18015e224  jz      short loc_18015E22D
0x18015e226  mov     eax, 3
0x18015e22b  jmp     short loc_18015E25D
0x18015e22d  mov     eax, 2
0x18015e232  test    al, sil
0x18015e235  jnz     short loc_18015E25D
0x18015e237  test    sil, 1
0x18015e23b  jz      short loc_18015E244
0x18015e23d  mov     eax, 1
0x18015e242  jmp     short loc_18015E25D
0x18015e244  test    sil, 20h
0x18015e248  jz      short loc_18015E251
0x18015e24a  mov     eax, 10h
0x18015e24f  jmp     short loc_18015E25D
0x18015e251  and     sil, 40h
0x18015e255  neg     sil
0x18015e258  sbb     eax, eax
0x18015e25a  and     eax, 11h
0x18015e25d  mov     [rbp+120h+lpFile], rbx
0x18015e261  mov     [rbp+120h+var_160], rbx
0x18015e265  mov     [rbp+120h+var_158], rbx
0x18015e269  lea     r8, [rbp+120h+packageFamilyName]
0x18015e26d  lea     rcx, [rbp+120h+lpFile]
0x18015e271  test    r15b, r15b
0x18015e274  jnz     short loc_18015E2BC
0x18015e276  mov     [rsp+220h+var_1F0], eax
0x18015e27a  xor     r15d, r15d
0x18015e27d  mov     [rsp+220h+nShowCmd], r15d
0x18015e282  mov     [rsp+220h+lpDirectory], r13; int
0x18015e287  mov     r9, r12
0x18015e28a  lea     rdx, aMsWindowsStore_17; "ms-windows-store:Remediation?PFN=%s&PN="...
0x18015e291  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18015e296  mov     ebx, eax
0x18015e298  test    eax, eax
0x18015e29a  jns     short loc_18015E2D8
0x18015e29c  mov     edx, 11Dh; void *
0x18015e2a1  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x18015e2a8  mov     r9d, eax; char *
0x18015e2ab  mov     rcx, [rbp+128h]; this
0x18015e2b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015e2b7  jmp     loc_18015E8C2
0x18015e2bc  lea     rdx, aMsWindowsStore_5; "ms-windows-store://pdp/?PFN=%s"
0x18015e2c3  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18015e2c8  mov     ebx, eax
0x18015e2ca  xor     r15d, r15d
0x18015e2cd  test    eax, eax
0x18015e2cf  jns     short loc_18015E2D8
0x18015e2d1  mov     edx, 121h
0x18015e2d6  jmp     short loc_18015E2A1
0x18015e2d8  mov     [rsp+220h+ppv], r15
0x18015e2dd  lea     rcx, [rsp+220h+ppv]
0x18015e2e2  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18015e2e7  lea     r9, [rsp+220h+ppv]; ppv
0x18015e2ec  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18015e2f3  xor     edx, edx; pbc
0x18015e2f5  mov     rcx, [rbp+120h+lpFile]; pszPath
0x18015e2f9  call    cs:__imp_SHCreateItemFromParsingName
0x18015e2ff  mov     ebx, eax
0x18015e301  test    eax, eax
0x18015e303  jns     short loc_18015E325
0x18015e305  mov     rcx, [rbp+128h]; this
0x18015e30c  mov     r9d, eax; char *
0x18015e30f  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x18015e316  mov     edx, 125h; void *
0x18015e31b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015e320  jmp     loc_18015E8B7
0x18015e325  mov     [rsp+220h+var_1B0], r15
0x18015e32a  lea     rcx, [rsp+220h+var_1B0]
0x18015e32f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18015e334  lea     r8, [rsp+220h+var_1B0]; ppv
0x18015e339  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b; riid
0x18015e340  mov     rcx, [rsp+220h+ppv]; psi
0x18015e345  call    cs:__imp_SHCreateShellItemArrayFromShellItem
0x18015e34b  mov     ebx, eax
0x18015e34d  test    eax, eax
0x18015e34f  jns     short loc_18015E371
0x18015e351  mov     rcx, [rbp+128h]; this
0x18015e358  mov     r9d, eax; char *
0x18015e35b  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x18015e362  mov     edx, 128h; void *
0x18015e367  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015e36c  jmp     loc_18015E8AC
0x18015e371  mov     [rsp+220h+var_1A8], r15
0x18015e376  mov     rax, [rsp+220h+var_1B0]
0x18015e37b  mov     [rbp+120h+var_178], rax
0x18015e37f  lea     rcx, [rsp+220h+var_1A8]
0x18015e384  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18015e389  lea     rdx, [rbp+120h+var_178]
0x18015e38d  lea     rcx, [rsp+220h+var_1A8]
0x18015e392  call    ??$MakeAndInitialize@VCProtocolActivatedEventArgs@@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@PEAUIShellItemArray@@@Details@WRL@Microsoft@@YAJPEAPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@$$QEAPEAUIShellItemArray@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CProtocolActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,IShellItemArray *>(Windows::ApplicationModel::Activation::IActivatedEventArgs * *,IShellItemArray * &&)
0x18015e397  mov     ebx, eax
0x18015e399  test    eax, eax
0x18015e39b  jns     short loc_18015E3BD
0x18015e39d  mov     rcx, [rbp+128h]; this
0x18015e3a4  mov     r9d, eax; char *
0x18015e3a7  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x18015e3ae  mov     edx, 12Bh; void *
0x18015e3b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015e3b8  jmp     loc_18015E8A1
0x18015e3bd  mov     [rbp+120h+var_198], r15
0x18015e3c1  lea     rcx, [rbp+120h+var_198]
0x18015e3c5  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18015e3ca  lea     rax, [rbp+120h+var_198]
0x18015e3ce  mov     [rsp+220h+lpDirectory], rax; int
0x18015e3d3  lea     r9, _GUID_54e4c428_d1d4_47d4_ade6_46c829114a7d; riid
  ... truncated ...
```
