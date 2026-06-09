# ImmersiveIcons::GetIconData(ushort const *,ImmersiveIcons::LoadIconParams const &,ImmersiveIcons::IconData2 *)

- ea: `0x1800c9644`
- end: `0x1800ca492`
- name: `?GetIconData@ImmersiveIcons@@YAJPEBGAEBULoadIconParams@1@PEAUIconData2@1@@Z`
- size: `3662`
- prototype: `__int64 __fastcall(PCWSTR pszItem, const unsigned __int16 *, const struct ImmersiveIcons::LoadIconParams *, struct ImmersiveIcons::IconData2 *)`
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18066e948`

## callees

- `0x1800134f8`
- `0x18001f6e0`
- `0x1800237c8`
- `0x180024b80`
- `0x180031c70`
- `0x18005a710`
- `0x18005d940`
- `0x180086598`
- `0x180086ac0`
- `0x18008a6f0`
- `0x1800a316c`
- `0x1800c7bc0`
- `0x1800c7e80`
- `0x1800c9644`
- `0x1800ca498`
- `0x1800ca578`
- `0x1800ca8b0`
- `0x1800cb050`
- `0x1800cb8d0`
- `0x18012e490`
- `0x1802a63f4`
- `0x1802a6450`
- `0x1802b614c`
- `0x1802c58d4`
- `0x1802c8168`
- `0x1802d6838`
- `0x180356360`
- `0x18066ce9c`
- `0x18066dd58`
- `0x18066ded0`
- `0x18066e654`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ca208`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ca465`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ca208`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ca465`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c97f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c9f43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c97f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c9f43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9ee2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9fc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f1b30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9ee2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9fc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f1b30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9820`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9b85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9f78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9f96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1806f1552`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9820`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9b85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9f78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9f96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1806f1552`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c9d38`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1806f15b0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c9d38`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1806f15b0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c9755`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c9755`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9862`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9944`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9994`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c99d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9a03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9a27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9b11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9bff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9c43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9c6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9c92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca007`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca04b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca083`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca0a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9862`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9944`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9994`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c99d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9a03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9a27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9b11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9bff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9c43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9c6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9c92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca007`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca04b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca083`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca0a7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c9849`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca313`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1806f1578`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c9849`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca313`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1806f1578`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800c9f81`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800c9f81`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1806f16aa`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1806f16aa`
- `PROPSYS!PropVariantToUInt32` at `0x1800ca197`
- `PROPSYS!PropVariantToUInt32` at `0x1800ca197`
- `SHELL32!SHCreateItemInKnownFolder` at `0x1800c96ac`
- `SHELL32!SHCreateItemInKnownFolder` at `0x1800c96ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ImmersiveIcons::GetIconData(
        WCHAR *pszItem,
        ImmersiveIcons *a2,
        const struct ImmersiveIcons::LoadIconParams *a3,
        struct ImmersiveIcons::IconData2 *a4)
{
  HRESULT v6; // eax
  HRESULT v7; // ebx
  int v8; // eax
  int v9; // eax
  WCHAR *v10; // r15
  __int64 v11; // rsi
  unsigned int v12; // eax
  UINT32 v13; // edx
  HRESULT v14; // eax
  const WCHAR *StringRawBuffer; // rax
  unsigned __int16 **v16; // r8
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  _WORD *v21; // rcx
  __int64 v22; // rcx
  struct ImmersiveIcons::LoadIconParams *v23; // rcx
  __int64 v24; // rcx
  __int64 (__fastcall ***v25)(_QWORD, _QWORD, _QWORD); // rcx
  size_t v26; // rcx
  __int64 v28; // rax
  __int64 v29; // rdx
  _WORD *v30; // r8
  __int16 v31; // r9
  __int16 *v32; // rcx
  unsigned __int64 v33; // rdx
  char v34; // r12
  __int64 v35; // rbx
  __int64 (__fastcall *v36)(__int64, LPVOID *); // rdi
  int v37; // eax
  const WCHAR *v38; // rax
  int v39; // eax
  __int64 v40; // rcx
  __int64 (__fastcall ***v41)(_QWORD, _QWORD, _QWORD); // rcx
  size_t v42; // rcx
  int v43; // eax
  void *v44; // rsi
  unsigned __int64 v45; // rax
  unsigned __int64 i; // rcx
  HRESULT Instance; // eax
  int v48; // eax
  WCHAR *v49; // r13
  size_t v50; // rdi
  __int64 (__fastcall *v51)(size_t, GUID *, _QWORD); // rbx
  int v52; // eax
  __int64 (__fastcall ***v53)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v54)(_QWORD, GUID *, __int64 *); // rdi
  int v55; // eax
  HSTRING v56; // rdx
  unsigned __int16 **v57; // r8
  size_t v58; // rdi
  __int64 (__fastcall *v59)(size_t, GUID *, struct ImmersiveIcons::LoadIconParams **); // rbx
  int v60; // eax
  __int64 v61; // rdx
  HSTRING v62; // rdi
  __int64 v63; // rbx
  unsigned int v64; // eax
  UINT32 v65; // edx
  HRESULT v66; // eax
  ShellMRTHelper::Common *v67; // rcx
  HRESULT v68; // eax
  const WCHAR *v69; // rax
  const wchar_t *v70; // rax
  size_t *v71; // r8
  __int64 v72; // rcx
  struct ImmersiveIcons::LoadIconParams *v73; // rcx
  __int64 v74; // rcx
  __int64 (__fastcall ***v75)(_QWORD, _QWORD, _QWORD); // rcx
  size_t v76; // rcx
  __int64 v77; // rdx
  __int64 v78; // r8
  __int64 v79; // r9
  struct IResourceContext *v80; // r8
  int ContrastForParams; // eax
  __int64 v82; // rdx
  int v83; // r12d
  int v84; // eax
  wil::details::in1diag3 *v85; // rcx
  __int64 v86; // rdi
  __int64 (__fastcall *v87)(__int64, struct ImmersiveIcons::LoadIconParams *, void *, __int64 *); // rbx
  __int64 v88; // rdx
  unsigned __int64 v89; // r9
  __int64 v90; // rdx
  __int64 v91; // rdx
  __int64 v92; // rdx
  __int64 v93; // rdx
  int v94; // eax
  __int64 v95; // rdi
  int (__fastcall *v96)(__int64, const wchar_t *, LPVOID *); // rbx
  unsigned __int64 v97; // rax
  __int64 v98; // rdx
  __int64 v99; // r9
  const WCHAR *v100; // rax
  HRESULT v101; // eax
  __int64 v102; // rdx
  int PackageFullNameForAppsFolderItem; // eax
  LPVOID v104; // rdi
  __int64 (__fastcall *v105)(LPVOID, WCHAR *, LPVOID, _QWORD); // rbx
  ImmersiveIcons *v106; // r12
  int inited; // eax
  __int64 v108; // rdi
  int (__fastcall *v109)(__int64, struct ImmersiveIcons::LoadIconParams *, void *, __int64 *); // rbx
  int v110; // eax
  __int64 *v111; // rcx
  __int64 v112; // rdi
  int (__fastcall *v113)(__int64, const wchar_t *, __int64 *); // rbx
  __int64 v114; // rax
  __int64 v115; // rbx
  __int64 v116; // rdi
  int (__fastcall *v117)(__int64, struct ImmersiveIcons::LoadIconParams *, void *, __int64 *); // rbx
  int v118; // eax
  __int64 v119; // rdi
  __int64 (__fastcall *v120)(__int64, const wchar_t *, __int64 *); // rbx
  int v121; // r12d
  int v122; // eax
  __int64 v123; // rdi
  __int64 (__fastcall *v124)(__int64, const wchar_t *, HSTRING_HEADER *); // rbx
  __int64 v125; // rdi
  int (__fastcall *v126)(__int64, const wchar_t *, __int64 *); // rbx
  int v127; // eax
  UINT32 v128; // ebx
  __int64 v129; // rdx
  HSTRING_HEADER *j; // rbx
  int ppv; // [rsp+20h] [rbp-E0h]
  void **ppva; // [rsp+20h] [rbp-E0h]
  void **ppvb; // [rsp+20h] [rbp-E0h]
  void **ppvc; // [rsp+20h] [rbp-E0h]
  __int64 v135; // [rsp+30h] [rbp-D0h] BYREF
  size_t cchToCopy; // [rsp+38h] [rbp-C8h] BYREF
  UINT32 v137[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v138; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v139; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v140)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-A8h] BYREF
  struct ImmersiveIcons::LoadIconParams *v141; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  __int64 v143; // [rsp+70h] [rbp-90h]
  __int64 v144; // [rsp+78h] [rbp-88h]
  PCWSTR sourceString; // [rsp+80h] [rbp-80h] BYREF
  UINT32 length[2]; // [rsp+88h] [rbp-78h]
  __int64 v147; // [rsp+90h] [rbp-70h]
  HSTRING__ v148[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v149; // [rsp+B0h] [rbp-50h]
  int v150; // [rsp+C0h] [rbp-40h]
  LPVOID v151; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v152; // [rsp+D0h] [rbp-30h]
  __int64 v153; // [rsp+D8h] [rbp-28h]
  PCWSTR v154; // [rsp+E0h] [rbp-20h] BYREF
  UINT32 v155[2]; // [rsp+E8h] [rbp-18h]
  __int64 v156; // [rsp+F0h] [rbp-10h]
  LPVOID v157; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v158; // [rsp+100h] [rbp+0h] BYREF
  __int64 v159; // [rsp+108h] [rbp+8h] BYREF
  __int64 v160; // [rsp+110h] [rbp+10h] BYREF
  __int64 v161; // [rsp+118h] [rbp+18h] BYREF
  void *v162; // [rsp+120h] [rbp+20h] BYREF
  ImmersiveIcons *v163; // [rsp+128h] [rbp+28h]
  __int64 v164; // [rsp+130h] [rbp+30h] BYREF
  __int64 v165; // [rsp+138h] [rbp+38h]
  __int64 v166; // [rsp+140h] [rbp+40h]
  __int64 v167; // [rsp+148h] [rbp+48h] BYREF
  __int64 v168; // [rsp+150h] [rbp+50h]
  __int64 v169; // [rsp+158h] [rbp+58h]
  __int64 v170; // [rsp+160h] [rbp+60h] BYREF
  __int64 v171; // [rsp+168h] [rbp+68h]
  __int64 v172; // [rsp+170h] [rbp+70h]
  _QWORD v173[5]; // [rsp+178h] [rbp+78h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+1A0h] [rbp+A0h] BYREF
  HSTRING string; // [rsp+1B8h] [rbp+B8h] BYREF
  HSTRING_HEADER pvar; // [rsp+1C0h] [rbp+C0h] BYREF
  HSTRING v177; // [rsp+1D8h] [rbp+D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v163 = a2;
  v162 = 0;
  Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v162, a2, a3, a4);
  v6 = SHCreateItemInKnownFolder(
         &FOLDERID_AppsFolder,
         0x4000u,
         pszItem,
         &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
         &v162);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
      (const char *)(unsigned int)v6,
      ppv);
LABEL_50:
    Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v162, v18, v19, v20);
    return (unsigned int)v7;
  }
  v135 = 0;
  Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&v135);
  v8 = wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(
         (unsigned int)&v135,
         (_DWORD)v162,
         1,
         (unsigned int)qword_180771BB0,
         4);
  v7 = v8;
  if ( v8 < 0 )
  {
    v89 = (unsigned int)v8;
    v90 = 237;
LABEL_159:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v90,
      (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
      (const char *)v89,
      (int)ppva);
LABEL_246:
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(&v135);
    goto LABEL_50;
  }
  *((_DWORD *)a3 + 3) = 0;
  LOWORD(pvar.Reserved.Reserved1) = 0;
  *(_OWORD *)&v148[0].unused = PKEY_Tile_Background;
  LODWORD(v149) = 4;
  v7 = (*(__int64 (__fastcall **)(__int64, HSTRING__ *, HSTRING_HEADER *))(*(_QWORD *)v135 + 40LL))(v135, v148, &pvar);
  if ( v7 >= 0 )
  {
    if ( LOWORD(pvar.Reserved.Reserved1) )
    {
      *((_DWORD *)a3 + 3) = 0;
      v7 = PropVariantToUInt32(&pvar.Reserved.Reserved1, (ULONG *)a3 + 3);
    }
    else
    {
      v7 = -2147023728;
    }
  }
  PropVariantClear(&pvar.Reserved.Reserved1);
  if ( v7 < 0 )
  {
    v89 = (unsigned int)v7;
    v90 = 239;
    goto LABEL_159;
  }
  sourceString = 0;
  *(_QWORD *)length = -1;
  v147 = -1;
  *(_OWORD *)&v148[0].unused = PKEY_Tile_SmallLogoPath;
  LODWORD(v149) = 2;
  v9 = wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v135, v148, &sourceString);
  v7 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF2,
      (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
      (const char *)(unsigned int)v9,
      (int)ppva);
LABEL_245:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
    goto LABEL_246;
  }
  v10 = (WCHAR *)sourceString;
  v11 = *(_QWORD *)length;
  if ( *(_QWORD *)length == -1 )
  {
    if ( sourceString )
    {
      v11 = -1;
      do
        ++v11;
      while ( sourceString[v11] );
      *(_QWORD *)length = v11;
    }
    else
    {
      v11 = 0;
      *(_QWORD *)length = 0;
    }
  }
  string = 0;
  v12 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v11);
  v13 = v12 - 1;
  if ( (unsigned int)v11 < v12 )
    v13 = v11;
  v14 = WindowsCreateStringReference(v10, v13, &hstringHeader, &string);
  if ( v14 < 0 )
  {
    RaiseException(v14, 1u, 0, 0);
    __debugbreak();
  }
  pv = 0;
  v143 = 0;
  v144 = 0;
  v137[0] = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, v137);
  if ( v137[0] >= 5 && CompareStringOrdinal(StringRawBuffer, 5, L"file:", 5, 1) == 2 )
  {
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v143 = -1;
    v144 = -1;
    v17 = TileUtils::ConvertFileUriToFilePath(v10, (const unsigned __int16 *)&pv, v16);
    v7 = v17;
    if ( v17 < 0 )
    {
      v91 = 260;
LABEL_194:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v91,
        (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
        (const char *)(unsigned int)v17,
        (int)ppva);
LABEL_244:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
      string = 0;
      goto LABEL_245;
    }
  }
  else
  {
    v137[0] = 0;
    v100 = WindowsGetStringRawBuffer(string, v137);
    if ( v137[0] >= 0xB && CompareStringOrdinal(v100, 11, L"ms-appdata:", 11, 1) == 2 )
    {
      v157 = 0;
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v157);
      v101 = CoCreateInstance(
               &GUID_a8ca4495_65ab_4333_9ff9_4feb6fbf5169,
               0,
               1u,
               &GUID_428bb582_2a87_4ea0_b529_30067cc4a4d7,
               &v157);
      v7 = v101;
      if ( v101 >= 0 )
      {
        v151 = 0;
        v152 = 0;
        v153 = 0;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v151);
        v152 = -1;
        v153 = -1;
        PackageFullNameForAppsFolderItem = ImmersiveIcons::GetPackageFullNameForAppsFolderItem((CallerIdentity *)pszItem);
        v7 = PackageFullNameForAppsFolderItem;
        if ( PackageFullNameForAppsFolderItem < 0 )
        {
          v102 = 268;
        }
        else
        {
          v104 = v157;
          v105 = *(__int64 (__fastcall **)(LPVOID, WCHAR *, LPVOID, _QWORD))(*(_QWORD *)v157 + 48LL);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
          v143 = -1;
          v144 = -1;
          ppva = &pv;
          PackageFullNameForAppsFolderItem = v105(v104, v10, v151, 0);
          v7 = PackageFullNameForAppsFolderItem;
          if ( PackageFullNameForAppsFolderItem >= 0 )
          {
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v151);
            Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v157);
            goto LABEL_21;
          }
          v102 = 270;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v102,
          (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
          (const char *)(unsigned int)PackageFullNameForAppsFolderItem,
          (int)ppva);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v151);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x109,
          (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
          (const char *)(unsigned int)v101,
          (int)ppva);
      }
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v157);
      goto LABEL_244;
    }
    if ( !PathIsRelativeW(v10) )
    {
      v17 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
              &pv,
              &sourceString);
      v7 = v17;
      if ( v17 < 0 )
      {
        v91 = 276;
        goto LABEL_194;
      }
    }
  }
LABEL_21:
  if ( !pv || !*(_WORD *)pv )
  {
    cchToCopy = 0;
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&cchToCopy);
    Instance = CoCreateInstance(
                 &GUID_dbce7e40_7345_439d_b12c_114a11819a09,
                 0,
                 1u,
                 &GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c,
                 (LPVOID *)&cchToCopy);
    v7 = Instance;
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11D,
        (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
        (const char *)(unsigned int)Instance,
        (int)ppvb);
LABEL_243:
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&cchToCopy);
      goto LABEL_244;
    }
    v154 = 0;
    *(_QWORD *)v155 = -1;
    v156 = -1;
    v48 = ImmersiveIcons::GetPackageFullNameForAppsFolderItem((CallerIdentity *)pszItem);
    v7 = v48;
    if ( v48 < 0 )
    {
      v92 = 288;
    }
    else
    {
      v49 = (WCHAR *)v154;
      v48 = (*(__int64 (__fastcall **)(size_t, PCWSTR))(*(_QWORD *)cchToCopy + 40LL))(cchToCopy, v154);
      v7 = v48;
      if ( v48 >= 0 )
      {
        v140 = 0;
        v50 = cchToCopy;
        v51 = *(__int64 (__fastcall **)(size_t, GUID *, _QWORD))(*(_QWORD *)cchToCopy + 56LL);
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v140);
        v52 = v51(v50, &GUID_6e21e72b_b9b0_42ae_a686_983cf784edcd, &v140);
        v7 = v52;
        if ( v52 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x125,
            (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
            (const char *)(unsigned int)v52,
            (int)ppvb);
LABEL_171:
          Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v140);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v154);
          Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&cchToCopy);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
          string = 0;
          goto LABEL_245;
        }
        v139 = 0;
        v53 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v140;
        v54 = **v140;
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v139);
        v55 = v54(v53, &GUID_2fe6ec6e_da7e_4b2a_a8f9_90b289061f20, &v139);
        v7 = v55;
        if ( v55 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x128,
            (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
            (const char *)(unsigned int)v55,
            (int)ppvb);
          goto LABEL_170;
        }
        memset(v148, 0, sizeof(v148));
        v149 = 0;
        if ( ShellMRTHelper::Common::HasMsAppXUriScheme((ShellMRTHelper::Common *)string, v56) )
        {
          *(_QWORD *)&v148[2].unused = -1;
          v149 = -1;
          v43 = ShellMRTHelper::Common::ConvertMsAppXUriToMsResourceUri((ShellMRTHelper::Common *)string, v148, v57);
          v7 = v43;
          if ( v43 >= 0 )
          {
LABEL_112:
            v44 = *(void **)&v148[0].unused;
LABEL_113:
            v141 = 0;
            v58 = cchToCopy;
            v59 = *(__int64 (__fastcall **)(size_t, GUID *, struct ImmersiveIcons::LoadIconParams **))(*(_QWORD *)cchToCopy + 72LL);
            Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v141);
            v60 = v59(v58, &GUID_e3c22b30_8502_4b2f_9133_559674587e51, &v141);
            v7 = v60;
            if ( v60 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x145,
                (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
                (const char *)(unsigned int)v60,
                (int)ppvb);
              Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v141);
LABEL_115:
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v148);
LABEL_170:
              Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v139);
              goto LABEL_171;
            }
            v138 = 0;
            v150 = 0;
            v137[0] = 0;
            LOBYTE(v61) = 1;
            wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemLightTheme>::ReportUsage(
              `wil::Feature<__WilFeatureTraits_Feature_SystemLightTheme>::GetImpl'::`2'::impl,
              v61);
            v106 = v163;
            if ( *((_DWORD *)v163 + 11) == 1 && *((_DWORD *)v163 + 10) != 1 && *((_DWORD *)v163 + 9) != 2 )
            {
              inited = ImmersiveIcons::InitResourceContextForLightTheme(v163, v141, v80);
              v7 = inited;
              if ( inited < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x159,
                  (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
                  (const char *)(unsigned int)inited,
                  (int)ppvb);
                Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v138);
                Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v141);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v148);
                Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v139);
                Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v140);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v154);
                Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&cchToCopy);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
                string = 0;
                goto LABEL_245;
              }
              v160 = 0;
              v108 = v139;
              v109 = *(int (__fastcall **)(__int64, struct ImmersiveIcons::LoadIconParams *, void *, __int64 *))(*(_QWORD *)v139 + 48LL);
              Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v160);
              if ( v109(v108, v141, v44, &v160) >= 0 )
              {
                v159 = 0;
                v110 = Microsoft::WRL::ComPtr<IResourceCandidate2>::As<IResourceCandidate>(&v160, &v159);
                v7 = v110;
                if ( v110 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x15F,
                    (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
                    (const char *)(unsigned int)v110,
                    (int)ppvb);
                  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v159);
                  v111 = &v160;
LABEL_218:
                  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(v111);
                  goto LABEL_241;
                }
                v167 = 0;
                v168 = 0;
                v169 = 0;
                v112 = v159;
                v113 = *(int (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v159 + 64LL);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v167);
                v168 = -1;
                v169 = -1;
                if ( v113(v112, L"AlternateForm", &v167) >= 0
                  && (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                                     &v167,
                                     L"lightunplated") == 2 )
                {
                  v150 = 2;
                  v137[0] = 1;
                  v114 = v138;
                  v115 = v159;
                  if ( v138 != v159 )
                  {
                    if ( v159 )
                    {
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v159 + 8LL))(v159);
                      v114 = v138;
                    }
                    v158 = v114;
                    v138 = v115;
                    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v158);
                  }
                }
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v167);
                Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v159);
              }
              Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v160);
            }
            if ( !v138 )
            {
              v94 = ImmersiveIcons::InitResourceContextForAllThemes(v106, v141, v80);
              v7 = v94;
              if ( v94 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x171,
                  (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
                  (const char *)(unsigned int)v94,
                  (int)ppvb);
                goto LABEL_241;
              }
              v161 = 0;
              v116 = v139;
              v117 = *(int (__fastcall **)(__int64, struct ImmersiveIcons::LoadIconParams *, void *, __int64 *))(*(_QWORD *)v139 + 48LL);
              Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v161);
              if ( v117(v116, v141, v44, &v161) >= 0 )
              {
                v118 = Microsoft::WRL::ComPtr<IResourceCandidate2>::As<IResourceCandidate>(&v161, &v138);
                v7 = v118;
                if ( v118 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x175,
                    (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
                    (const char *)(unsigned int)v118,
                    (int)ppvb);
                  v111 = &v161;
                  goto LABEL_218;
                }
                v170 = 0;
                v171 = 0;
                v172 = 0;
                v119 = v138;
                v120 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v138 + 64LL);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v170);
                v171 = -1;
                v172 = -1;
                v121 = v120(v119, L"AlternateForm", &v170);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v170);
                v150 = (v121 >> 31) + 2;
                v106 = v163;
              }
              Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v161);
              if ( !v138 )
              {
                *(_QWORD *)v137 = 0;
                WindowsDeleteString(0);
                *(_QWORD *)v137 = 0;
                v62 = string;
                v63 = *(_QWORD *)v155;
                if ( *(_QWORD *)v155 == -1 )
                {
                  if ( v49 )
                  {
                    do
                      ++v63;
                    while ( v49[v63] );
                  }
                  else
                  {
                    v63 = 0;
                  }
                  *(_QWORD *)v155 = v63;
                }
                v177 = 0;
                v64 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v63);
                v65 = v64 - 1;
                if ( (unsigned int)v63 < v64 )
                  v65 = v63;
                v66 = WindowsCreateStringReference(v49, v65, &pvar, &v177);
                if ( v66 < 0 )
                {
                  RaiseException(v66, 1u, 0, 0);
                  __debugbreak();
                }
                v68 = ShellMRTHelper::Common::TryFallbackToFilePath(v67, v177, v62, (HSTRING)v137, (HSTRING *)ppvb);
                v7 = v68;
                if ( v68 < 0 )
                {
                  v98 = 435;
                }
                else
                {
                  v69 = WindowsGetStringRawBuffer(*(HSTRING *)v137, 0);
                  if ( !PathFileExistsW(v69) )
                  {
                    v7 = -2147024893;
                    v99 = 2147942403LL;
                    v98 = 436;
LABEL_240:
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)v98,
                      (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
                      (const char *)v99,
                      (int)ppvc);
                    WindowsDeleteString(*(HSTRING *)v137);
                    *(_QWORD *)v137 = 0;
                    goto LABEL_241;
                  }
                  v70 = WindowsGetStringRawBuffer(*(HSTRING *)v137, 0);
                  v68 = StringCopyWorkerW((STRSAFE_LPWSTR)a3 + 8, 0x104u, v71, v70, (size_t)ppvc);
                  v7 = v68;
                  if ( v68 >= 0 )
                  {
                    *(_QWORD *)a3 = 0;
                    *((_BYTE *)a3 + 8) = 0;
                    WindowsDeleteString(*(HSTRING *)v137);
                    goto LABEL_128;
                  }
                  v98 = 437;
                }
                v99 = (unsigned int)v68;
                goto LABEL_240;
              }
            }
            ContrastForParams = ImmersiveIcons::GetContrastForParams(v106);
            v83 = ContrastForParams;
            if ( v150 != 1 || ContrastForParams )
            {
LABEL_233:
              LOBYTE(v82) = 1;
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemLightTheme>::ReportUsage(
                `wil::Feature<__WilFeatureTraits_Feature_SystemLightTheme>::GetImpl'::`2'::impl,
                v82);
              v164 = 0;
              v165 = 0;
              v166 = 0;
              v125 = v138;
              v126 = *(int (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v138 + 64LL);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v164);
              v165 = -1;
              v166 = -1;
              if ( v126(v125, L"Theme", &v164) >= 0 )
              {
                if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                                     &v164,
                                     L"dark") == 2 )
                {
                  v137[0] = 2;
                }
                else
                {
                  v127 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                           &v164,
                           L"light");
                  v128 = v137[0];
                  if ( v127 == 2 )
                    v128 = 1;
                  v137[0] = v128;
                }
              }
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v164);
              v151 = 0;
              v152 = 0;
              v153 = 0;
              if ( !v83
                || (v95 = v138,
                    v96 = *(int (__fastcall **)(__int64, const wchar_t *, LPVOID *))(*(_QWORD *)v138 + 64LL),
                    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v151),
                    v152 = -1,
                    v153 = -1,
                    v34 = 1,
                    v96(v95, L"Contrast", &v151) < 0) )
              {
                v34 = 0;
              }
              v35 = v138;
              v36 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v138 + 32LL);
              if ( pv )
              {
                CoTaskMemFree(pv);
                pv = 0;
              }
              v143 = -1;
              v144 = -1;
              v37 = v36(v35, &pv);
              v7 = v37;
              if ( v37 >= 0 )
              {
                v32 = (__int16 *)pv;
                v97 = v143;
                if ( v143 == -1 )
                {
                  if ( pv )
                  {
                    v97 = -1;
                    do
                      ++v97;
                    while ( *((_WORD *)pv + v97) );
                  }
                  else
                  {
                    v97 = 0;
                  }
                  v143 = v97;
                }
                v33 = 0;
                if ( v97 )
                {
                  do
                  {
                    if ( v32[v33] == 47 )
                    {
                      v32[v33] = 92;
                      v97 = v143;
                      v32 = (__int16 *)pv;
                    }
                    ++v33;
                  }
                  while ( v33 < v97 );
                  v10 = (WCHAR *)sourceString;
                }
                v28 = 2147483646;
                v29 = 260;
                v30 = (_WORD *)((char *)a3 + 16);
                do
                {
                  if ( !v28 )
                    break;
                  v31 = *v32;
                  if ( !*v32 )
                    break;
                  ++v32;
                  *v30++ = v31;
                  --v28;
                  --v29;
                }
                while ( v29 );
                v7 = v29 == 0 ? 0x8007007A : 0;
                v21 = v30 - 1;
                if ( v29 )
                  v21 = v30;
                *v21 = 0;
                if ( !v29 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x1A5,
                    (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
                    (const char *)(unsigned int)v7,
                    (int)ppvb);
                  if ( v151 )
                  {
                    CoTaskMemFree(v151);
                    v151 = 0;
                  }
                  v152 = 0;
                  v153 = 0;
                  v22 = v138;
                  if ( v138 )
                  {
                    v138 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
                  }
                  v23 = v141;
                  if ( v141 )
                  {
                    v141 = 0;
                    (*(void (__fastcall **)(struct ImmersiveIcons::LoadIconParams *))(*(_QWORD *)v23 + 16LL))(v23);
                  }
                  if ( v44 )
                    CoTaskMemFree(v44);
                  v24 = v139;
                  if ( v139 )
                  {
                    v139 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
                  }
                  v25 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v140;
                  if ( v140 )
                  {
                    v140 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v25)[2])(v25);
                  }
                  if ( v49 )
                    CoTaskMemFree(v49);
                  v26 = cchToCopy;
                  if ( cchToCopy )
                  {
                    cchToCopy = 0;
                    (*(void (__fastcall **)(size_t))(*(_QWORD *)v26 + 16LL))(v26);
                  }
                  if ( pv )
                  {
                    CoTaskMemFree(pv);
                    pv = 0;
                  }
                  v143 = 0;
                  v144 = 0;
                  string = 0;
                  if ( v10 )
                    CoTaskMemFree(v10);
LABEL_49:
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v135);
                  goto LABEL_50;
                }
                *(_DWORD *)a3 = v150;
                *((_DWORD *)a3 + 1) = v137[0];
                *((_BYTE *)a3 + 8) = v34;
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v151);
LABEL_128:
                v72 = v138;
                if ( v138 )
                {
                  v138 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
                }
                v73 = v141;
                if ( v141 )
                {
                  v141 = 0;
                  (*(void (__fastcall **)(struct ImmersiveIcons::LoadIconParams *))(*(_QWORD *)v73 + 16LL))(v73);
                }
                if ( v44 )
                  CoTaskMemFree(v44);
                v74 = v139;
                if ( v139 )
                {
                  v139 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
                }
                v75 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v140;
                if ( v140 )
                {
                  v140 = 0;
                  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v75)[2])(v75);
                }
                if ( v49 )
                  CoTaskMemFree(v49);
                v76 = cchToCopy;
                if ( cchToCopy )
                {
                  cchToCopy = 0;
                  (*(void (__fastcall **)(size_t))(*(_QWORD *)v76 + 16LL))(v76);
                }
                goto LABEL_142;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1A1,
                (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
                (const char *)(unsigned int)v37,
                (int)ppvb);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v151);
LABEL_241:
              Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v138);
              Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v141);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v148);
              Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v139);
              Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v140);
              goto LABEL_242;
            }
            v158 = 0;
            v84 = (*(__int64 (__fastcall **)(struct ImmersiveIcons::LoadIconParams *, _QWORD))(*(_QWORD *)v141 + 112LL))(
                    v141,
                    *((unsigned __int16 *)v163 + 8));
            v85 = retaddr;
            if ( v84 < 0 )
            {
              v88 = 388;
            }
            else
            {
              v86 = v139;
              v87 = *(__int64 (__fastcall **)(__int64, struct ImmersiveIcons::LoadIconParams *, void *, __int64 *))(*(_QWORD *)v139 + 48LL);
              Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v158);
              v84 = v87(v86, v141, v44, &v158);
              v85 = retaddr;
              if ( v84 >= 0 )
              {
                v122 = Microsoft::WRL::ComPtr<IResourceCandidate2>::As<IResourceCandidate>(&v158, &v138);
                v7 = v122;
                if ( v122 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x187,
                    (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
                    (const char *)(unsigned int)v122,
                    (int)ppvb);
                  v111 = &v158;
                  goto LABEL_218;
                }
                memset(&pvar, 0, sizeof(pvar));
                v123 = v138;
                v124 = *(__int64 (__fastcall **)(__int64, const wchar_t *, HSTRING_HEADER *))(*(_QWORD *)v138 + 64LL);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pvar);
                *(_QWORD *)&pvar.Reserved.Reserved2[8] = -1;
                *(_QWORD *)&pvar.Reserved.Reserved2[16] = -1;
                LODWORD(v124) = v124(v123, L"AlternateForm", &pvar);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pvar);
                v150 = ((int)v124 >> 31) + 2;
                goto LABEL_232;
              }
              v88 = 389;
            }
            wil::details::in1diag3::_Log_Hr(
              v85,
              (void *)v88,
              (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
              (const char *)(unsigned int)v84,
              (int)ppvb);
LABEL_232:
            Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v158);
            goto LABEL_233;
          }
          v93 = 303;
        }
        else
        {
          v137[0] = 0;
          v38 = WindowsGetStringRawBuffer(string, v137);
          if ( v137[0] >= 0xC && CompareStringOrdinal(v38, 12, L"ms-resource:", 12, 1) == 2 )
          {
            v43 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
                    v148,
                    &sourceString);
            v7 = v43;
            if ( v43 >= 0 )
              goto LABEL_112;
            v93 = 310;
          }
          else
          {
            if ( v11 == -1 )
            {
              if ( v10 )
              {
                v11 = -1;
                do
                  ++v11;
                while ( v10[v11] );
                *(_QWORD *)length = v11;
              }
              else
              {
                v11 = 0;
                *(_QWORD *)length = 0;
              }
            }
            v39 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                    v148,
                    L"Files\\",
                    v11 + 7);
            v7 = v39;
            if ( v39 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x13D,
                (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
                (const char *)(unsigned int)v39,
                (int)ppvb);
              if ( *(_QWORD *)&v148[0].unused )
                CoTaskMemFree(*(LPVOID *)&v148[0].unused);
              v40 = v139;
              if ( v139 )
              {
                v139 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
              }
              v41 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v140;
              if ( v140 )
              {
                v140 = 0;
                ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v41)[2])(v41);
              }
              if ( v49 )
                CoTaskMemFree(v49);
              v42 = cchToCopy;
              if ( cchToCopy )
              {
                cchToCopy = 0;
                (*(void (__fastcall **)(size_t))(*(_QWORD *)v42 + 16LL))(v42);
              }
              if ( pv )
              {
                CoTaskMemFree(pv);
                pv = 0;
              }
              v143 = 0;
              v144 = 0;
              string = 0;
              if ( v10 )
                CoTaskMemFree(v10);
              goto LABEL_49;
            }
            v43 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
                    v148,
                    &sourceString);
            v7 = v43;
            if ( v43 >= 0 )
            {
              v44 = *(void **)&v148[0].unused;
              v45 = *(_QWORD *)&v148[2].unused;
              if ( *(_QWORD *)&v148[2].unused == -1 )
              {
                if ( *(_QWORD *)&v148[0].unused )
                {
                  v45 = -1;
                  do
                    ++v45;
                  while ( *(_WORD *)(*(_QWORD *)&v148[0].unused + 2 * v45) );
                }
                else
                {
                  v45 = 0;
                }
                *(_QWORD *)&v148[2].unused = v45;
              }
              for ( i = 0; i < v45; ++i )
              {
                if ( *((_WORD *)v44 + i) == 47 )
                  *((_WORD *)v44 + i) = 92;
              }
              goto LABEL_113;
            }
            v93 = 318;
          }
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v93,
          (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
          (const char *)(unsigned int)v43,
          (int)ppvb);
        goto LABEL_115;
      }
      v92 = 290;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v92,
      (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
      (const char *)(unsigned int)v48,
      (int)ppvb);
LABEL_242:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v154);
    goto LABEL_243;
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ReplaceChars(&pv);
  v17 = StringCchCopyW((unsigned __int16 *)a3 + 8, 0x104u, (const unsigned __int16 *)pv);
  v7 = v17;
  if ( v17 < 0 )
  {
    v91 = 452;
    goto LABEL_194;
  }
  *(_QWORD *)a3 = 0;
  *((_BYTE *)a3 + 8) = 0;
LABEL_142:
  if ( !*(_DWORD *)a3 )
  {
    v151 = 0;
    v152 = 0;
    v153 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v151);
    v152 = -1;
    v153 = -1;
    *(_OWORD *)&v148[0].unused = PKEY_AppUserModel_ParentID;
    LODWORD(v149) = 19;
    if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v135, v148, &v151) >= 0 )
    {
      if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                           &v151,
                           L"Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge") == 2 )
      {
LABEL_253:
        *(_DWORD *)a3 = 3;
      }
      else
      {
        LOBYTE(v129) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_UnplateMicrosoftEdgeTiles_25482738>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_Servicing_UnplateMicrosoftEdgeTiles_25482738>::GetImpl'::`2'::impl,
          v129);
        v173[0] = L"Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!App";
        v173[1] = L"Microsoft.MicrosoftEdge.Beta_8wekyb3d8bbwe!App";
        v173[2] = L"Microsoft.MicrosoftEdge.Dev_8wekyb3d8bbwe!App";
        v173[3] = L"Microsoft.MicrosoftEdge.Canary_8wekyb3d8bbwe!App";
        v173[4] = L"Microsoft.MicrosoftEdge.Internal_8wekyb3d8bbwe!App";
        for ( j = (HSTRING_HEADER *)v173; j != &hstringHeader; j = (HSTRING_HEADER *)((char *)j + 8) )
        {
          if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                               &v151,
                               j->Reserved.Reserved1) == 2 )
            goto LABEL_253;
        }
      }
      if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                           &v151,
                           L"Microsoft.YourPhone_8wekyb3d8bbwe!App") == 2 )
        *(_DWORD *)a3 = 3;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v151);
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v143 = 0;
  v144 = 0;
  string = 0;
  if ( v10 )
    CoTaskMemFree(v10);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v135);
  Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v162, v77, v78, v79);
  return 0;
}

```

## disassembly

```asm
0x1800c9644  mov     [rsp-8+arg_18], rbx
0x1800c9649  push    rbp
0x1800c964a  push    rsi
0x1800c964b  push    rdi
0x1800c964c  push    r12
0x1800c964e  push    r13
0x1800c9650  push    r14
0x1800c9652  push    r15
0x1800c9654  lea     rbp, [rsp-0F0h]
0x1800c965c  sub     rsp, 1F0h
0x1800c9663  mov     rax, cs:__security_cookie
0x1800c966a  xor     rax, rsp
0x1800c966d  mov     [rbp+120h+var_40], rax
0x1800c9674  mov     r14, r8
0x1800c9677  mov     [rbp+120h+var_F8], rdx
0x1800c967b  mov     r12, rcx
0x1800c967e  xor     esi, esi
0x1800c9680  mov     [rbp+120h+var_100], rsi
0x1800c9684  lea     rcx, [rbp+120h+var_100]
0x1800c9688  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x1800c968d  lea     rax, [rbp+120h+var_100]
0x1800c9691  mov     [rsp+220h+ppv], rax; int
0x1800c9696  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800c969d  mov     r8, r12; pszItem
0x1800c96a0  mov     edx, 4000h; dwKFFlags
0x1800c96a5  lea     rcx, FOLDERID_AppsFolder; kfid
0x1800c96ac  call    cs:__imp_SHCreateItemInKnownFolder
0x1800c96b2  mov     ebx, eax
0x1800c96b4  test    eax, eax
0x1800c96b6  js      loc_1800C98DC
0x1800c96bc  mov     [rsp+220h+var_1F0], rsi
0x1800c96c1  lea     rcx, [rsp+220h+var_1F0]
0x1800c96c6  call    ?InternalAddRef@?$ComPtr@UIWindowingEnvironmentConfig@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(void)
0x1800c96cb  mov     dword ptr [rsp+220h+ppv], 4; int
0x1800c96d3  lea     r9, qword_180771BB0
0x1800c96da  lea     r8d, [rsi+1]
0x1800c96de  mov     rdx, [rbp+120h+var_100]
0x1800c96e2  lea     rcx, [rsp+220h+var_1F0]
0x1800c96e7  call    ?InitFromItem@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@PEBU_tagpropertykey@@I@Z; wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS,_tagpropertykey const *,uint)
0x1800c96ec  mov     ebx, eax
0x1800c96ee  test    eax, eax
0x1800c96f0  js      loc_1800CA1A4
0x1800c96f6  movups  xmm0, cs:PKEY_Tile_Background
0x1800c96fd  mov     ecx, cs:dword_180771B88
0x1800c9703  lea     rdi, [r14+0Ch]
0x1800c9707  mov     [rdi], esi
0x1800c9709  mov     word ptr [rbp+120h+pvar], si
0x1800c9710  movaps  xmmword ptr [rbp+120h+var_180.unused], xmm0
0x1800c9714  mov     dword ptr [rbp+120h+var_170], ecx
0x1800c9717  mov     rcx, [rsp+220h+var_1F0]
0x1800c971c  mov     rax, [rcx]
0x1800c971f  lea     r8, [rbp+120h+pvar]
0x1800c9726  lea     rdx, [rbp+120h+var_180]
0x1800c972a  mov     rax, [rax+28h]
0x1800c972e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9733  mov     ebx, eax
0x1800c9735  test    eax, eax
0x1800c9737  js      short loc_1800C974E
0x1800c9739  movzx   eax, word ptr [rbp+120h+pvar]
0x1800c9740  test    ax, ax
0x1800c9743  jnz     loc_1800CA182
0x1800c9749  mov     ebx, 80070490h
0x1800c974e  lea     rcx, [rbp+120h+pvar]; pvar
0x1800c9755  call    cs:__imp_PropVariantClear
0x1800c975b  xor     edi, edi
0x1800c975d  test    ebx, ebx
0x1800c975f  js      loc_1800CA1AE
0x1800c9765  mov     [rbp+120h+sourceString], rdi
0x1800c9769  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800c976d  mov     qword ptr [rbp+120h+length], r13
0x1800c9771  mov     [rbp+120h+var_190], r13
0x1800c9775  movups  xmm0, cs:PKEY_Tile_SmallLogoPath
0x1800c977c  movaps  xmmword ptr [rbp+120h+var_180.unused], xmm0
0x1800c9780  mov     eax, cs:dword_180771B70
0x1800c9786  mov     dword ptr [rbp+120h+var_170], eax
0x1800c9789  lea     r8, [rbp+120h+sourceString]
0x1800c978d  lea     rdx, [rbp+120h+var_180]
0x1800c9791  lea     rcx, [rsp+220h+var_1F0]
0x1800c9796  call    ??$GetString@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAPEAG@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x1800c979b  mov     ebx, eax
0x1800c979d  test    eax, eax
0x1800c979f  js      loc_1800CA1CF
0x1800c97a5  mov     r15, [rbp+120h+sourceString]
0x1800c97a9  mov     rsi, qword ptr [rbp+120h+length]
0x1800c97ad  cmp     rsi, r13
0x1800c97b0  jnz     short loc_1800C97CC
0x1800c97b2  test    r15, r15
0x1800c97b5  jz      loc_1800CA1F0
0x1800c97bb  mov     rsi, r13
0x1800c97be  inc     rsi
0x1800c97c1  cmp     [r15+rsi*2], di
0x1800c97c6  jnz     short loc_1800C97BE
0x1800c97c8  mov     qword ptr [rbp+120h+length], rsi
0x1800c97cc  mov     [rbp+120h+string], rdi
0x1800c97d3  mov     ecx, esi; unsigned int
0x1800c97d5  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800c97da  lea     edx, [rax-1]
0x1800c97dd  cmp     esi, eax
0x1800c97df  cmovb   edx, esi; length
0x1800c97e2  lea     r9, [rbp+120h+string]; string
0x1800c97e9  lea     r8, [rbp+120h+hstringHeader]; hstringHeader
0x1800c97f0  mov     rcx, r15; sourceString
0x1800c97f3  call    cs:__imp_WindowsCreateStringReference
0x1800c97f9  test    eax, eax
0x1800c97fb  js      loc_1800CA1FC
0x1800c9801  mov     [rsp+220h+pv], rdi
0x1800c9806  mov     [rsp+220h+var_1B0], rdi
0x1800c980b  mov     [rsp+220h+var_1A8], rdi
0x1800c9810  mov     [rsp+220h+var_1E0], edi
0x1800c9814  lea     rdx, [rsp+220h+var_1E0]; length
0x1800c9819  mov     rcx, [rbp+120h+string]; string
0x1800c9820  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c9826  mov     edx, 5; cchCount1
0x1800c982b  lea     ebx, [rdx-4]
0x1800c982e  cmp     [rsp+220h+var_1E0], edx
0x1800c9832  jb      loc_1806F1542
0x1800c9838  mov     dword ptr [rsp+220h+ppv], ebx; int
0x1800c983c  mov     r9d, edx; cchCount2
0x1800c983f  lea     r8, ?c_fileUriScheme@Common@ShellMRTHelper@@3QBGB; "file:"
0x1800c9846  mov     rcx, rax; lpString1
0x1800c9849  call    cs:__imp_CompareStringOrdinal
0x1800c984f  cmp     eax, 2
0x1800c9852  jnz     loc_1806F1542
0x1800c9858  mov     rcx, [rsp+220h+pv]; pv
0x1800c985d  test    rcx, rcx
0x1800c9860  jz      short loc_1800C986D
0x1800c9862  call    cs:__imp_CoTaskMemFree
0x1800c9868  mov     [rsp+220h+pv], rdi
0x1800c986d  mov     [rsp+220h+var_1B0], r13
0x1800c9872  mov     [rsp+220h+var_1A8], r13
0x1800c9877  lea     rdx, [rsp+220h+pv]; unsigned __int16 *
0x1800c987c  mov     rcx, r15; pwzURI
0x1800c987f  call    ?ConvertFileUriToFilePath@TileUtils@@YAJPEBGPEAPEAG@Z; TileUtils::ConvertFileUriToFilePath(ushort const *,ushort * *)
0x1800c9884  mov     ebx, eax
0x1800c9886  test    eax, eax
0x1800c9888  js      loc_1800CA20F
0x1800c988e  mov     rax, [rsp+220h+pv]
0x1800c9893  test    rax, rax
0x1800c9896  jz      loc_1800C9D0B
0x1800c989c  cmp     [rax], di
0x1800c989f  jz      loc_1800C9D0B
0x1800c98a5  lea     rcx, [rsp+220h+pv]
0x1800c98aa  call    ?ReplaceChars@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAXGG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ReplaceChars(ushort,ushort)
0x1800c98af  lea     rcx, [r14+10h]; unsigned __int16 *
0x1800c98b3  mov     r8, [rsp+220h+pv]; unsigned __int16 *
0x1800c98b8  mov     edx, 104h; unsigned __int64
0x1800c98bd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c98c2  mov     ebx, eax
0x1800c98c4  test    eax, eax
0x1800c98c6  js      loc_1806F1522
0x1800c98cc  mov     qword ptr [r14], 0
0x1800c98d3  mov     [r14+8], dil
0x1800c98d7  jmp     loc_1800CA070
0x1800c98dc  mov     rcx, [rbp+128h]; this
0x1800c98e3  mov     r9d, eax; char *
0x1800c98e6  lea     r8, aShellLibImmers_0; "shell\\lib\\immersiveapphelpers\\immers"...
0x1800c98ed  mov     edx, 0DEh; void *
0x1800c98f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c98f7  jmp     loc_1800C9A39
0x1800c98fc  mov     rax, rdx
0x1800c98ff  neg     rax
0x1800c9902  sbb     ebx, ebx
0x1800c9904  not     ebx
0x1800c9906  and     ebx, 8007007Ah
0x1800c990c  lea     rcx, [r8-2]
0x1800c9910  test    rdx, rdx
0x1800c9913  cmovnz  rcx, r8
0x1800c9917  mov     [rcx], di
0x1800c991a  jnz     loc_1800CA431
0x1800c9920  mov     rcx, [rbp+128h]; this
0x1800c9927  mov     r9d, ebx; char *
0x1800c992a  lea     r8, aShellLibImmers_0; "shell\\lib\\immersiveapphelpers\\immers"...
0x1800c9931  mov     edx, 1A5h; void *
0x1800c9936  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c993b  mov     rcx, [rbp+120h+var_158]; pv
0x1800c993f  test    rcx, rcx
0x1800c9942  jz      short loc_1800C994E
0x1800c9944  call    cs:__imp_CoTaskMemFree
0x1800c994a  mov     [rbp+120h+var_158], rdi
0x1800c994e  mov     [rbp+120h+var_150], rdi
0x1800c9952  mov     [rbp+120h+var_148], rdi
0x1800c9956  mov     rcx, [rsp+220h+var_1D8]
0x1800c995b  test    rcx, rcx
0x1800c995e  jz      short loc_1800C9971
0x1800c9960  mov     [rsp+220h+var_1D8], rdi
0x1800c9965  mov     rax, [rcx]
0x1800c9968  mov     rax, [rax+10h]
0x1800c996c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9971  mov     rcx, [rsp+220h+var_1C0]
0x1800c9976  test    rcx, rcx
0x1800c9979  jz      short loc_1800C998C
0x1800c997b  mov     [rsp+220h+var_1C0], rdi
0x1800c9980  mov     rax, [rcx]
0x1800c9983  mov     rax, [rax+10h]
0x1800c9987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c998c  test    rsi, rsi
0x1800c998f  jz      short loc_1800C999A
0x1800c9991  mov     rcx, rsi; pv
0x1800c9994  call    cs:__imp_CoTaskMemFree
0x1800c999a  mov     rcx, [rsp+220h+var_1D0]
0x1800c999f  test    rcx, rcx
0x1800c99a2  jz      short loc_1800C99B5
0x1800c99a4  mov     [rsp+220h+var_1D0], rdi
0x1800c99a9  mov     rax, [rcx]
0x1800c99ac  mov     rax, [rax+10h]
0x1800c99b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c99b5  mov     rcx, [rsp+220h+var_1C8]
0x1800c99ba  test    rcx, rcx
0x1800c99bd  jz      short loc_1800C99D0
0x1800c99bf  mov     [rsp+220h+var_1C8], rdi
0x1800c99c4  mov     rax, [rcx]
0x1800c99c7  mov     rax, [rax+10h]
0x1800c99cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c99d0  test    r13, r13
0x1800c99d3  jz      short loc_1800C99DE
0x1800c99d5  mov     rcx, r13; pv
0x1800c99d8  call    cs:__imp_CoTaskMemFree
0x1800c99de  mov     rcx, [rsp+220h+cchToCopy]
0x1800c99e3  test    rcx, rcx
0x1800c99e6  jz      short loc_1800C99F9
0x1800c99e8  mov     [rsp+220h+cchToCopy], rdi
0x1800c99ed  mov     rax, [rcx]
0x1800c99f0  mov     rax, [rax+10h]
0x1800c99f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c99f9  mov     rcx, [rsp+220h+pv]; pv
0x1800c99fe  test    rcx, rcx
0x1800c9a01  jz      short loc_1800C9A0E
0x1800c9a03  call    cs:__imp_CoTaskMemFree
0x1800c9a09  mov     [rsp+220h+pv], rdi
0x1800c9a0e  mov     [rsp+220h+var_1B0], rdi
0x1800c9a13  mov     [rsp+220h+var_1A8], rdi
0x1800c9a18  mov     [rbp+120h+string], rdi
0x1800c9a1f  test    r15, r15
0x1800c9a22  jz      short loc_1800C9A2E
0x1800c9a24  mov     rcx, r15; pv
0x1800c9a27  call    cs:__imp_CoTaskMemFree
0x1800c9a2d  nop
0x1800c9a2e  lea     rcx, [rsp+220h+var_1F0]
0x1800c9a33  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c9a38  nop
0x1800c9a39  lea     rcx, [rbp+120h+var_100]
0x1800c9a3d  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x1800c9a42  mov     eax, ebx
0x1800c9a44  mov     rcx, [rbp+120h+var_40]
0x1800c9a4b  xor     rcx, rsp; StackCookie
0x1800c9a4e  call    __security_check_cookie
0x1800c9a53  mov     rbx, [rsp+220h+arg_18]
0x1800c9a5b  add     rsp, 1F0h
0x1800c9a62  pop     r15
0x1800c9a64  pop     r14
0x1800c9a66  pop     r13
0x1800c9a68  pop     r12
0x1800c9a6a  pop     rdi
0x1800c9a6b  pop     rsi
0x1800c9a6c  pop     rbp
0x1800c9a6d  retn
0x1800c9a6e  mov     r15, [rbp+120h+sourceString]
0x1800c9a72  mov     eax, 7FFFFFFEh
0x1800c9a77  mov     edx, 104h
0x1800c9a7c  lea     r8, [r14+10h]
0x1800c9a80  test    rax, rax
0x1800c9a83  jz      loc_1800C98FC
0x1800c9a89  movzx   r9d, word ptr [rcx]
0x1800c9a8d  test    r9w, r9w
0x1800c9a91  jz      loc_1800C98FC
0x1800c9a97  add     rcx, 2
0x1800c9a9b  mov     [r8], r9w
0x1800c9a9f  add     r8, 2
0x1800c9aa3  sub     rax, r10
0x1800c9aa6  sub     rdx, r10
0x1800c9aa9  jnz     short loc_1800C9A80
0x1800c9aab  jmp     loc_1800C98FC
0x1800c9ab0  mov     [rsp+220h+var_1B0], rax
0x1800c9ab5  mov     rdx, rdi
0x1800c9ab8  mov     r10d, 1
0x1800c9abe  test    rax, rax
0x1800c9ac1  jz      short loc_1800C9A72
0x1800c9ac3  cmp     word ptr [rcx+rdx*2], 2Fh ; '/'
0x1800c9ac8  jz      loc_1800CA41C
0x1800c9ace  add     rdx, r10
0x1800c9ad1  cmp     rdx, rax
0x1800c9ad4  jb      short loc_1800C9AC3
0x1800c9ad6  jmp     short loc_1800C9A6E
0x1800c9ad8  lea     rcx, [rbp+120h+var_F0]
0x1800c9adc  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800c9ae1  xor     edx, edx
0x1800c9ae3  mov     [rbp+120h+var_158], rdx
0x1800c9ae7  mov     [rbp+120h+var_150], rdx
0x1800c9aeb  mov     [rbp+120h+var_148], rdx
0x1800c9aef  test    r12d, r12d
0x1800c9af2  jnz     loc_1800CA3A1
0x1800c9af8  mov     r12b, dl
0x1800c9afb  mov     rbx, [rsp+220h+var_1D8]
0x1800c9b00  mov     rax, [rbx]
0x1800c9b03  mov     rdi, [rax+20h]
0x1800c9b07  mov     rcx, [rsp+220h+pv]; pv
0x1800c9b0c  test    rcx, rcx
0x1800c9b0f  jz      short loc_1800C9B20
0x1800c9b11  call    cs:__imp_CoTaskMemFree
0x1800c9b17  mov     [rsp+220h+pv], 0
  ... truncated ...
```
