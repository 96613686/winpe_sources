# SnapShotLiveSettingsToTheme(IPropertyBag *,ushort const *,ushort const *,bool,ITheme * *)

- ea: `0x18000eeb0`
- end: `0x1800104b5`
- name: `?SnapShotLiveSettingsToTheme@@YAJPEAUIPropertyBag@@PEBG1_NPEAPEAUITheme@@@Z`
- size: `5637`
- prototype: `__int64 __usercall@<rax>(IUnknown *punkSite@<rcx>, const unsigned __int16 *@<rdx>, LPCWSTR lpExistingFileName@<r8>, bool@<r9b>, struct ITheme **)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180010820`

## callees

- `0x1800082f0`
- `0x1800089c0`
- `0x18000c2c4`
- `0x18000eeb0`
- `0x1800104c0`
- `0x180015700`
- `0x1800179e0`
- `0x180018110`
- `0x180019070`
- `0x1800199d0`
- `0x18001d4b4`
- `0x18001e280`
- `0x180030f64`
- `0x1800358c0`
- `0x18003633c`
- `0x18003e95c`
- `0x180042664`
- `0x18006d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800102c8`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800102c8`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800102ba`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800102ba`
- `SHCORE!SHGetValueW` at `0x18000f90e`
- `SHCORE!SHGetValueW` at `0x18000ff01`
- `SHCORE!SHGetValueW` at `0x180010112`
- `SHCORE!SHGetValueW` at `0x18000f90e`
- `SHCORE!SHGetValueW` at `0x18000ff01`
- `SHCORE!SHGetValueW` at `0x180010112`
- `SHCORE!IUnknown_SetSite` at `0x18000f852`
- `SHCORE!IUnknown_SetSite` at `0x18000f89b`
- `SHCORE!IUnknown_SetSite` at `0x18000f852`
- `SHCORE!IUnknown_SetSite` at `0x18000f89b`
- `SHCORE!__imp_SHCreateDirectoryExW` at `0x18000efbd`
- `SHCORE!__imp_SHCreateDirectoryExW` at `0x18000efbd`
- `SHLWAPI!StrToIntExW` at `0x18000f947`
- `SHLWAPI!StrToIntExW` at `0x18000f947`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18000efab`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18000efab`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18000ff3b`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x180010148`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18000ff3b`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x180010148`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f41e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f41e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000ef41`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000fade`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000fd5d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000ef41`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000fade`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000fd5d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010355`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010355`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180010300`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180010300`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800103c1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800103c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010413`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010413`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800103fb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800103fb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f5b8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f6b4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f776`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f9ff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000fc89`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000fd16`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001028f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f5b8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f6b4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f776`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f9ff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000fc89`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000fd16`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001028f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000ffb4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000ffb4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18000f3f2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18000f3f2`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18000efe2`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18000efe2`
- `USER32!SystemParametersInfoW` at `0x180010225`
- `USER32!SystemParametersInfoW` at `0x180010225`
- `USER32!GetSystemMetrics` at `0x18000f136`
- `USER32!GetSystemMetrics` at `0x18000f136`
- `PROPSYS!PSPropertyBag_ReadBOOL` at `0x18000f104`
- `PROPSYS!PSPropertyBag_ReadBOOL` at `0x18000f104`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18000f18b`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18000f1f9`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18000f438`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18000f494`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18000f501`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18000fbde`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18000f18b`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18000f1f9`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18000f438`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18000f494`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18000f501`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18000fbde`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18000f294`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18000f2f8`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18000f294`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18000f2f8`
- `PROPSYS!PSPropertyBag_ReadUnknown` at `0x18000f33d`
- `PROPSYS!PSPropertyBag_ReadUnknown` at `0x18000f33d`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f00f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f19c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f20a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f44d`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f4be`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f527`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fa2c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fb0b`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fd6e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fda1`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fdf9`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fe16`
- `OLEAUT32!__imp_SysAllocString` at `0x180010036`
- `OLEAUT32!__imp_SysAllocString` at `0x180010053`
- `OLEAUT32!__imp_SysAllocString` at `0x18001019c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800101b9`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f00f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f19c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f20a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f44d`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f4be`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f527`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fa2c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fb0b`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fd6e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fda1`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fdf9`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fe16`
- `OLEAUT32!__imp_SysAllocString` at `0x180010036`
- `OLEAUT32!__imp_SysAllocString` at `0x180010053`
- `OLEAUT32!__imp_SysAllocString` at `0x18001019c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800101b9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f040`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f1d0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f23b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f4b1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f51a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f555`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fa5d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fb3b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fdd1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fe52`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fe5c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ff9f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ffa8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001008f`
- `OLEAUT32!__imp_SysFreeString` at `0x180010099`
- `OLEAUT32!__imp_SysFreeString` at `0x1800101ec`
- `OLEAUT32!__imp_SysFreeString` at `0x1800101f6`
- `OLEAUT32!__imp_SysFreeString` at `0x180010426`
- `OLEAUT32!__imp_SysFreeString` at `0x18001042f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f040`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f1d0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f23b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f4b1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f51a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f555`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fa5d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fb3b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fdd1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fe52`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fe5c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ff9f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ffa8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001008f`
- `OLEAUT32!__imp_SysFreeString` at `0x180010099`
- `OLEAUT32!__imp_SysFreeString` at `0x1800101ec`
- `OLEAUT32!__imp_SysFreeString` at `0x1800101f6`
- `OLEAUT32!__imp_SysFreeString` at `0x180010426`
- `OLEAUT32!__imp_SysFreeString` at `0x18001042f`

## string_xrefs

- `0x18000f154`: `BackgroundSrc_Path`
- `0x18000f1ef`: `BackgroundSrc_Path`
- `0x18000f42e`: `VisualStyle_Path`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall SnapShotLiveSettingsToTheme(
        IPropertyBag *punkSite,
        const unsigned __int16 *a2,
        LPCWSTR lpExistingFileName,
        char a4,
        struct ITheme **a5)
{
  IPropertyBag *v7; // r12
  __int64 v8; // r13
  __int64 v9; // rax
  const unsigned __int16 *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // r8
  unsigned __int16 v13; // r9
  int Instance; // esi
  WCHAR *v15; // rcx
  int v16; // eax
  BSTR v17; // rax
  OLECHAR *v18; // rbx
  struct ITheme *v19; // r15
  unsigned int v20; // edi
  int v21; // eax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // rdx
  unsigned int SystemMetrics; // r14d
  BSTR v25; // rax
  OLECHAR *v26; // rbx
  BSTR v27; // rax
  OLECHAR *v28; // rbx
  int v29; // eax
  __int64 v30; // rcx
  int *v31; // rdx
  BSTR v32; // rax
  OLECHAR *v33; // rbx
  int v34; // ebx
  LSTATUS ValueW; // eax
  signed int v36; // ecx
  __int64 v37; // rdx
  BOOL v38; // ebx
  LSTATUS v39; // eax
  signed int v40; // ecx
  LSTATUS v41; // eax
  signed int v42; // ecx
  LSTATUS v43; // eax
  unsigned int v44; // edx
  unsigned int v45; // r9d
  LSTATUS v46; // eax
  bool v47; // sf
  BSTR v48; // rax
  OLECHAR *v49; // rbx
  int AllRegSoundEvents; // r12d
  int i; // ebx
  const WCHAR *v52; // rcx
  struct _DPA *v53; // rdi
  int j; // esi
  const OLECHAR *Ptr; // rax
  __int64 v56; // r14
  BSTR v57; // rax
  OLECHAR *v58; // rbx
  int v59; // r14d
  const OLECHAR **v60; // rbx
  IPropertyBag *v61; // rbx
  int k; // r14d
  const OLECHAR *v63; // rbx
  LSTATUS v64; // eax
  bool v65; // sf
  LSTATUS v66; // eax
  bool v67; // sf
  int v68; // eax
  __int64 v69; // rsi
  BSTR v70; // rax
  OLECHAR *v71; // rbx
  BSTR v72; // rax
  OLECHAR *v73; // rax
  OLECHAR *v74; // rdi
  int v75; // r14d
  LPCWSTR *v76; // rbx
  LSTATUS v77; // eax
  bool v78; // sf
  __int64 v79; // rcx
  WCHAR *v80; // r8
  __int64 v81; // rdx
  WCHAR *v82; // rax
  WCHAR v83; // r9
  WCHAR *v84; // rcx
  __int64 v85; // rcx
  BSTR v86; // rcx
  IPropertyBag *v88; // rbx
  OLECHAR *v89; // rax
  OLECHAR *v90; // rdi
  LSTATUS v91; // eax
  bool v92; // sf
  WCHAR *v93; // rcx
  WCHAR *v94; // rax
  __int64 v95; // r8
  WCHAR v96; // dx
  WCHAR *v97; // rcx
  IPropertyBag *v98; // rbx
  BSTR v99; // rax
  OLECHAR *v100; // rdi
  LSTATUS v101; // eax
  bool v102; // sf
  wchar_t *v103; // rax
  unsigned __int64 v104; // rbx
  BOOL bIgnoreCase[2]; // [rsp+20h] [rbp-E0h]
  DWORD phkResult[2]; // [rsp+50h] [rbp-B0h] BYREF
  void *ppv; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-A0h] BYREF
  char v109; // [rsp+64h] [rbp-9Ch]
  DWORD pdwType[2]; // [rsp+68h] [rbp-98h] BYREF
  BOOL value; // [rsp+70h] [rbp-90h] BYREF
  BSTR v112; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpFileName; // [rsp+80h] [rbp-80h]
  GUID rguid; // [rsp+90h] [rbp-70h] BYREF
  IPropertyBag *propBag[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 FileInformation; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v117; // [rsp+C0h] [rbp-40h]
  int v118; // [rsp+D0h] [rbp-30h]
  WCHAR SubKey[376]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR psz[264]; // [rsp+3D0h] [rbp+2D0h] BYREF
  WCHAR pszPath[264]; // [rsp+5E0h] [rbp+4E0h] BYREF
  OLECHAR sz[40]; // [rsp+7F0h] [rbp+6F0h] BYREF
  OLECHAR pvData[264]; // [rsp+840h] [rbp+740h] BYREF
  WCHAR String2[264]; // [rsp+A50h] [rbp+950h] BYREF
  WCHAR propName[264]; // [rsp+C60h] [rbp+B60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+EB8h] [rbp+DB8h]

  v109 = a4;
  lpFileName = a2;
  v7 = punkSite;
  propBag[0] = punkSite;
  *(_QWORD *)&rguid.Data1 = a5;
  v8 = 260;
  if ( lpExistingFileName && a2 && a5 )
  {
    *a5 = 0;
    if ( CompareStringOrdinal(lpExistingFileName, -1, a2, -1, 1) == 2 )
      goto LABEL_19;
    v9 = 2147483646;
    v10 = a2;
    v11 = 260;
    v12 = pszPath;
    do
    {
      if ( !v9 )
        break;
      v13 = *v10;
      if ( !*v10 )
        break;
      ++v10;
      *v12++ = v13;
      --v9;
      --v11;
    }
    while ( v11 );
    Instance = -2147024774;
    if ( v11 )
      Instance = 0;
    v15 = v12 - 1;
    if ( v11 )
      v15 = v12;
    *v15 = 0;
    if ( v11 )
    {
      PathRemoveFileSpecW(pszPath);
      v16 = SHCreateDirectoryExW(0, pszPath, 0);
      if ( !v16 || v16 == 183 || (Instance = ResultFromKnownLastError(), Instance >= 0) )
      {
        if ( CopyFileW(lpExistingFileName, a2, 0) || (Instance = ResultFromKnownLastError(), Instance >= 0) )
        {
LABEL_19:
          Instance = CThemeFile_CreateInstance(a2, a5);
          if ( Instance >= 0 )
          {
            v17 = SysAllocString(L"RJSPBS");
            v18 = v17;
            v112 = v17;
            if ( !v17 )
              ATL::AtlThrowImpl(-2147024882);
            Instance = (*(__int64 (__fastcall **)(_QWORD, BSTR))(*(_QWORD *)*a5 + 488LL))(*a5, v17);
            SysFreeString(v18);
          }
        }
      }
    }
  }
  else
  {
    Instance = -2147024809;
  }
  if ( Instance >= 0 )
  {
    v19 = *a5;
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a5 + 552LL))(*a5);
    (*(void (__fastcall **)(struct ITheme *))(*(_QWORD *)v19 + 408LL))(v19);
    (*(void (__fastcall **)(struct ITheme *))(*(_QWORD *)v19 + 216LL))(v19);
    v20 = 0;
    v112 = 0;
    v21 = (**(__int64 (__fastcall ***)(struct ITheme *, GUID *, BSTR *))v19)(
            v19,
            &GUID_6a0522b4_8e09_4aa8_985a_9e52d534977a,
            &v112);
    v22 = retaddr;
    if ( v21 >= 0 )
    {
      v21 = (*(__int64 (__fastcall **)(BSTR))(*(_QWORD *)v112 + 40LL))(v112);
      v22 = retaddr;
      if ( v21 >= 0 )
        goto LABEL_29;
      v23 = 2498;
    }
    else
    {
      v23 = 2496;
    }
    wil::details::in1diag3::_Log_Hr(
      v22,
      (void *)v23,
      (unsigned int)"shell\\themes\\themeui\\themefile.cpp",
      (const char *)(unsigned int)v21,
      bIgnoreCase[0]);
LABEL_29:
    value = 0;
    if ( PSPropertyBag_ReadBOOL(v7, L"Background_Multimon", &value) >= 0 )
      Instance = (*(__int64 (__fastcall **)(struct ITheme *, BOOL))(*(_QWORD *)v19 + 440LL))(v19, value);
    if ( value )
    {
      SystemMetrics = GetSystemMetrics(80);
      if ( Instance < 0 )
        goto LABEL_207;
      while ( v20 < SystemMetrics )
      {
        bIgnoreCase[0] = v20;
        Instance = StringCchPrintfW(propName, 0x104u, L"%s%u", L"BackgroundSrc_Path", *(_QWORD *)bIgnoreCase);
        if ( Instance >= 0 && PSPropertyBag_ReadStr(v7, propName, psz, 260) >= 0 )
        {
          v25 = SysAllocString(psz);
          v26 = v25;
          *(_QWORD *)phkResult = v25;
          if ( !v25 )
            ATL::AtlThrowImpl(-2147024882);
          Instance = (*(__int64 (__fastcall **)(struct ITheme *, _QWORD, BSTR))(*(_QWORD *)v19 + 456LL))(
                       v19,
                       v20 + 1,
                       v25);
          SysFreeString(v26);
        }
        if ( Instance < 0 )
          goto LABEL_207;
        ++v20;
      }
      v20 = 0;
    }
    else
    {
      if ( PSPropertyBag_ReadStr(v7, L"BackgroundSrc_Path", psz, 260) >= 0 )
      {
        v27 = SysAllocString(psz);
        v28 = v27;
        ppv = v27;
        if ( !v27 )
          ATL::AtlThrowImpl(-2147024882);
        Instance = (*(__int64 (__fastcall **)(struct ITheme *, BSTR))(*(_QWORD *)v19 + 176LL))(v19, v27);
        SysFreeString(v28);
      }
      *(_QWORD *)phkResult = 0;
      v29 = (**(__int64 (__fastcall ***)(struct ITheme *, GUID *, DWORD *))v19)(
              v19,
              &GUID_6a0522b4_8e09_4aa8_985a_9e52d534977a,
              phkResult);
      if ( v29 >= 0 )
      {
        pdwType[0] = 0;
        if ( PSPropertyBag_ReadDWORD(v7, L"WindowsSpotlight", pdwType) >= 0 && pdwType[0] == 1 )
          Instance = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)phkResult + 24LL))(
                       *(_QWORD *)phkResult,
                       1);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x9E7,
          (unsigned int)"shell\\themes\\themeui\\themefile.cpp",
          (const char *)(unsigned int)v29,
          bIgnoreCase[0]);
      }
      v30 = *(_QWORD *)phkResult;
      if ( *(_QWORD *)phkResult )
      {
        *(_QWORD *)phkResult = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
      if ( Instance < 0 )
        goto LABEL_207;
    }
    pdwType[0] = 0;
    if ( PSPropertyBag_ReadDWORD(v7, L"Background_TILE", pdwType) >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(struct ITheme *, _QWORD))(*(_QWORD *)v19 + 192LL))(v19, pdwType[0]);
      if ( Instance < 0 )
        goto LABEL_207;
    }
    ppv = 0;
    if ( PSPropertyBag_ReadUnknown(v7, L"Slideshow", &GUID_00000000_0000_0000_c000_000000000046, &ppv) < 0 )
    {
      Instance = (*(__int64 (__fastcall **)(struct ITheme *, _QWORD))(*(_QWORD *)v19 + 232LL))(v19, 0);
      if ( Instance < 0 )
        goto LABEL_207;
      *(_QWORD *)phkResult = 0;
      FileInformation = 0;
      v117 = 0;
      v118 = 0;
      if ( GetFileAttributesExW(psz, GetFileExInfoStandard, &FileInformation) )
      {
        *(_QWORD *)phkResult = *(_QWORD *)((char *)&v117 + 4);
        (*(void (__fastcall **)(struct ITheme *, DWORD *))(*(_QWORD *)v19 + 208LL))(v19, phkResult);
      }
      else
      {
        GetLastError();
      }
    }
    else
    {
      *(_QWORD *)phkResult = 0;
      Instance = (**(__int64 (__fastcall ***)(void *, GUID *, DWORD *))ppv)(
                   ppv,
                   &GUID_b6f3692b_8a89_4f93_800a_4c6cf8e93382,
                   phkResult);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(struct ITheme *, _QWORD))(*(_QWORD *)v19 + 232LL))(
                     v19,
                     *(_QWORD *)phkResult);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)phkResult + 16LL))(*(_QWORD *)phkResult);
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      if ( Instance < 0 )
        goto LABEL_207;
    }
    if ( PSPropertyBag_ReadStr(v7, L"VisualStyle_Path", psz, 260) < 0 )
      goto LABEL_76;
    v32 = SysAllocString(psz);
    v33 = v32;
    *(_QWORD *)phkResult = v32;
    if ( !v32 )
      goto LABEL_264;
    Instance = (*(__int64 (__fastcall **)(struct ITheme *, BSTR))(*(_QWORD *)v19 + 48LL))(v19, v32);
    if ( Instance >= 0 && PSPropertyBag_ReadStr(v7, L"VisualStyle_Color", psz, 260) >= 0 )
    {
      if ( psz != v33 )
      {
        SysFreeString(v33);
        v33 = SysAllocString(psz);
        *(_QWORD *)phkResult = v33;
        if ( !v33 )
          goto LABEL_259;
      }
      Instance = (*(__int64 (__fastcall **)(struct ITheme *, OLECHAR *))(*(_QWORD *)v19 + 64LL))(v19, v33);
      if ( Instance >= 0 && PSPropertyBag_ReadStr(v7, L"VisualStyle_Size", psz, 260) >= 0 )
      {
        if ( psz == v33 || (SysFreeString(v33), v33 = SysAllocString(psz), (*(_QWORD *)phkResult = v33) != 0) )
        {
          Instance = (*(__int64 (__fastcall **)(struct ITheme *, OLECHAR *))(*(_QWORD *)v19 + 80LL))(v19, v33);
          goto LABEL_75;
        }
LABEL_259:
        ATL::AtlThrowImpl(-2147024882);
      }
    }
LABEL_75:
    SysFreeString(v33);
    if ( Instance < 0 )
      goto LABEL_207;
LABEL_76:
    phkResult[0] = 0;
    GetDwmColorizationColor(phkResult, v31);
    v34 = 0;
    pdwType[0] = 0;
    pcbData = 4;
    ValueW = RegGetValueW(
               HKEY_CURRENT_USER,
               L"Control Panel\\Desktop",
               L"AutoColorization",
               0x10000012u,
               pdwType,
               &ppv,
               &pcbData);
    v36 = ValueW;
    if ( ValueW )
    {
      if ( ValueW == 234 )
      {
        LOWORD(v36) = 13;
      }
      else if ( ValueW <= 0 )
      {
        goto LABEL_89;
      }
    }
    else
    {
      LOWORD(v36) = 13;
      if ( pdwType[0] == 4 )
      {
        if ( (unsigned int)ppv <= 1 )
        {
          v36 = 0;
          LOBYTE(v34) = (_DWORD)ppv == 1;
          goto LABEL_89;
        }
      }
      else if ( pcbData == 4 )
      {
        if ( (_WORD)ppv == 48 )
        {
          v34 = 0;
          v36 = 0;
          goto LABEL_89;
        }
        if ( (_WORD)ppv == 49 )
        {
          v34 = 1;
          v36 = 0;
          goto LABEL_89;
        }
      }
    }
    v36 = (unsigned __int16)v36 | 0x80070000;
LABEL_89:
    if ( v36 >= 0 )
      v20 = v34;
    Instance = (*(__int64 (__fastcall **)(struct ITheme *, _QWORD))(*(_QWORD *)v19 + 112LL))(v19, phkResult[0]);
    if ( Instance >= 0 )
      Instance = (*(__int64 (__fastcall **)(struct ITheme *, _QWORD))(*(_QWORD *)v19 + 424LL))(v19, v20);
    LOBYTE(v37) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemLightTheme>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_SystemLightTheme>::GetImpl'::`2'::impl,
      v37);
    v38 = 0;
    phkResult[0] = 0;
    LODWORD(ppv) = 4;
    v39 = RegGetValueW(
            HKEY_CURRENT_USER,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Themes\\Personalize",
            L"AppsUseLightTheme",
            0x10000012u,
            phkResult,
            &pcbData,
            (LPDWORD)&ppv);
    v40 = v39;
    if ( v39 )
    {
      if ( v39 == 234 )
      {
        LOWORD(v40) = 13;
      }
      else if ( v39 <= 0 )
      {
        goto LABEL_106;
      }
    }
    else
    {
      LOWORD(v40) = 13;
      if ( phkResult[0] == 4 )
      {
        if ( pcbData <= 1 )
        {
          v40 = 0;
          LOBYTE(v38) = pcbData == 1;
          goto LABEL_106;
        }
        goto LABEL_105;
      }
      if ( (_DWORD)ppv == 4 )
      {
        if ( (_WORD)pcbData == 48 )
        {
LABEL_101:
          v40 = 0;
          goto LABEL_106;
        }
        if ( (_WORD)pcbData == 49 )
        {
          v38 = 1;
          goto LABEL_101;
        }
      }
    }
LABEL_105:
    v40 = (unsigned __int16)v40 | 0x80070000;
LABEL_106:
    if ( v40 >= 0 )
      (*(void (__fastcall **)(struct ITheme *, BOOL))(*(_QWORD *)v19 + 144LL))(v19, v38);
    phkResult[0] = 0;
    LODWORD(ppv) = 4;
    v41 = RegGetValueW(
            HKEY_CURRENT_USER,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Themes\\Personalize",
            L"SystemUsesLightTheme",
            0x10000012u,
            phkResult,
            &pcbData,
            (LPDWORD)&ppv);
    v42 = v41;
    if ( v41 )
    {
      if ( v41 == 234 )
      {
        LOWORD(v42) = 13;
      }
      else if ( v41 <= 0 )
      {
        goto LABEL_121;
      }
    }
    else
    {
      LOWORD(v42) = 13;
      if ( phkResult[0] == 4 )
      {
        if ( pcbData <= 1 )
        {
          v42 = 0;
          v38 = pcbData == 1;
LABEL_121:
          if ( v42 >= 0 )
            (*(void (__fastcall **)(struct ITheme *, BOOL))(*(_QWORD *)v19 + 160LL))(v19, v38);
          if ( Instance < 0 )
            goto LABEL_207;
          *(_QWORD *)pdwType = 0;
          Instance = (**(__int64 (__fastcall ***)(struct ITheme *, GUID *, DWORD *))v19)(
                       v19,
                       &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
                       pdwType);
          if ( Instance < 0 )
            goto LABEL_207;
          memset_0(SubKey, 0, sizeof(SubKey));
          if ( (int)SystemMetricsAll_Get((struct SYSTEMMETRICSALL *)SubKey) < 0 )
          {
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pdwType + 16LL))(*(_QWORD *)pdwType);
          }
          else
          {
            IUnknown_SetSite(*(IUnknown **)pdwType, (IUnknown *)v7);
            *(_QWORD *)&FileInformation = 0x4000;
            *(_QWORD *)&v117 = 0;
            *((_QWORD *)&FileInformation + 1) = SubKey;
            Instance = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *, __int128 *))(**(_QWORD **)pdwType + 32LL))(
                         *(_QWORD *)pdwType,
                         L"SystemMetrics",
                         &FileInformation);
            IUnknown_SetSite(*(IUnknown **)pdwType, 0);
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pdwType + 16LL))(*(_QWORD *)pdwType);
            if ( Instance < 0 )
              goto LABEL_207;
          }
          LODWORD(ppv) = 0;
          pszPath[0] = 0;
          phkResult[0] = 0;
          pcbData = 520;
          v43 = SHGetValueW(
                  HKEY_LOCAL_MACHINE,
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
                  L"SetupVersion",
                  phkResult,
                  pszPath,
                  &pcbData);
          Instance = v43;
          if ( v43 > 0 )
            Instance = (unsigned __int16)v43 | 0x80070000;
          if ( Instance < 0 )
            goto LABEL_207;
          if ( phkResult[0] == 1 )
            Instance = StrToIntExW(pszPath, 0, (int *)&ppv)
                     ? (*(__int64 (__fastcall **)(struct ITheme *, _QWORD))(*(_QWORD *)v19 + 96LL))(
                         v19,
                         (unsigned int)ppv)
                     : -2147467259;
          else
            Instance = -2147467259;
          if ( Instance < 0 )
            goto LABEL_207;
          Instance = GetSystemSoundScheme(propName, v44, pvData, v45);
          if ( Instance < 0 )
            goto LABEL_207;
          Instance = StringCchPrintfW(psz, 0x104u, L"%s\\%s", L"AppEvents\\Schemes\\Names", propName);
          if ( Instance < 0 )
            goto LABEL_207;
          phkResult[0] = 520;
          v46 = RegGetValueW(HKEY_CURRENT_USER, psz, 0, 2u, 0, pvData, phkResult);
          v47 = v46 < 0;
          if ( v46 )
          {
            pvData[0] = 0;
            if ( v46 > 0 )
              v47 = 1;
          }
          if ( v47 )
            pvData[0] = 0;
          v48 = SysAllocString(pvData);
          v49 = v48;
          *(_QWORD *)phkResult = v48;
          if ( !v48 )
            ATL::AtlThrowImpl(-2147024882);
          Instance = (*(__int64 (__fastcall **)(struct ITheme *, BSTR))(*(_QWORD *)v19 + 328LL))(v19, v48);
          SysFreeString(v49);
          if ( Instance < 0 )
            goto LABEL_207;
          ppv = g_pfn_DPA_Create(16);
          if ( ppv )
          {
            AllRegSoundEvents = GetAllRegSoundEvents(&ppv);
            for ( i = 0; ; ++i )
            {
              v52 = (const WCHAR *)(&c_rgszInBoxSoundSchemes)[i];
              v53 = (struct _DPA *)ppv;
              if ( !*v52 )
                break;
              if ( CompareStringOrdinal(v52, -1, propName, -1, 1) == 2 )
              {
                for ( j = 0; j < AllRegSoundEvents; ++j )
                {
                  Ptr = (const OLECHAR *)g_pfn_DPA_GetPtr(v53, j);
                  if ( Ptr )
                  {
                    v56 = *(_QWORD *)v19;
                    v57 = SysAllocString(Ptr);
                    v58 = v57;
                    *(_QWORD *)phkResult = v57;
                    if ( !v57 )
                      ATL::AtlThrowImpl(-2147024882);
                    (*(void (__fastcall **)(struct ITheme *, BSTR, _QWORD))(v56 + 344))(v19, v57, 0);
                    SysFreeString(v58);
                  }
                }
                goto LABEL_157;
              }
            }
            for ( k = 0; k < AllRegSoundEvents; ++k )
            {
              v63 = (const OLECHAR *)g_pfn_DPA_GetPtr(v53, k);
              if ( v63 )
              {
                if ( (int)StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", v63, L".Current") < 0 )
                  goto LABEL_172;
                phkResult[0] = 520;
                v64 = RegGetValueW(HKEY_CURRENT_USER, SubKey, 0, 2u, 0, String2, phkResult);
                v65 = v64 < 0;
                if ( v64 )
                {
                  String2[0] = 0;
                  v65 = v64 < 0;
                  if ( v64 > 0 )
                    v65 = 1;
                }
                if ( v65 )
LABEL_172:
                  String2[0] = 0;
                if ( (int)StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", v63, L".Default") < 0 )
                  goto LABEL_178;
                phkResult[0] = 520;
                v66 = RegGetValueW(HKEY_CURRENT_USER, SubKey, 0, 2u, 0, pszPath, phkResult);
                v67 = v66 < 0;
                if ( v66 )
                {
                  pszPath[0] = 0;
                  v67 = v66 < 0;
                  if ( v66 > 0 )
                    v67 = 1;
                }
                if ( v67 )
LABEL_178:
                  pszPath[0] = 0;
                v68 = CompareStringOrdinal(pszPath, -1, String2, -1, 1);
                v69 = *(_QWORD *)v19;
                if ( v68 == 2 )
                {
                  v72 = SysAllocString(v63);
                  v71 = v72;
                  *(_QWORD *)phkResult = v72;
                  if ( !v72 )
LABEL_262:
                    ATL::AtlThrowImpl(-2147024882);
                  (*(void (__fastcall **)(struct ITheme *, BSTR, _QWORD))(v69 + 344))(v19, v72, 0);
                }
                else
                {
                  v70 = SysAllocString(v63);
                  v71 = v70;
                  *(_QWORD *)phkResult = v70;
                  if ( !v70 )
                    goto LABEL_262;
                  (*(void (__fastcall **)(struct ITheme *, BSTR, WCHAR *))(v69 + 344))(v19, v70, String2);
                }
                SysFreeString(v71);
              }
            }
LABEL_157:
            Instance = 0;
            if ( v53 )
            {
              g_pfn_DPA_DestroyCallback(
                v53,
                CDPA_Base<_ITEMIDLIST_ABSOLUTE,CTContainer_PolicyCoTaskMem>::_StandardDestroyCB,
                0);
              DPA_Destroy(0);
            }
            v7 = propBag[0];
          }
          else
          {
            Instance = -2147024882;
          }
          if ( Instance < 0 )
            goto LABEL_207;
          v59 = 0;
          if ( *(_WORD *)c_rgszDesktopIcons )
          {
            do
            {
              v60 = (const OLECHAR **)&(&c_rgszDesktopIcons)[v59];
              if ( PSPropertyBag_ReadStr(v7, *v60, psz, 260) >= 0 )
              {
                if ( *v60 )
                {
                  v61 = (IPropertyBag *)SysAllocString(*v60);
                  propBag[0] = v61;
                  if ( !v61 )
                    goto LABEL_264;
                }
                else
                {
                  v61 = 0;
                  propBag[0] = 0;
                }
                v73 = SysAllocString(psz);
                v74 = v73;
                *(_QWORD *)phkResult = v73;
                if ( !v73 )
                  ATL::AtlThrowImpl(-2147024882);
                if ( !v61 )
                {
                  Instance = -2147024882;
                  SysFreeString(v73);
                  SysFreeString(0);
                  goto LABEL_207;
                }
                (*(void (__fastcall **)(struct ITheme *, IPropertyBag *, OLECHAR *))(*(_QWORD *)v19 + 376LL))(
                  v19,
                  v61,
                  v73);
                SysFreeString(v74);
                SysFreeString((BSTR)v61);
              }
              ++v59;
            }
            while ( *(_WORD *)(&c_rgszDesktopIcons)[v59] );
          }
          v75 = 0;
          if ( aArrow[0] )
          {
            while ( 1 )
            {
              v76 = (LPCWSTR *)&off_18006E940[v75];
              memset_0(pszPath, 0, 0x208u);
              phkResult[0] = 0;
              LODWORD(ppv) = 520;
              psz[0] = 0;
              v77 = SHGetValueW(HKEY_CURRENT_USER, L"Control Panel\\Cursors", *v76, phkResult, pszPath, (DWORD *)&ppv);
              v78 = v77 < 0;
              if ( v77 > 0 )
                v78 = 1;
              if ( v78 )
              {
                psz[0] = 0;
              }
              else if ( phkResult[0] - 1 <= 1 && !(unsigned int)SHExpandEnvironmentStringsW(pszPath, psz, 260) )
              {
                v79 = 2147483646;
                v80 = pszPath;
                v81 = 260;
                v82 = psz;
                do
                {
                  if ( !v79 )
                    break;
                  v83 = *v80;
                  if ( !*v80 )
                    break;
                  ++v80;
                  *v82++ = v83;
                  --v79;
                  --v81;
                }
                while ( v81 );
                v84 = v82 - 1;
                if ( v81 )
                  v84 = v82;
                *v84 = 0;
              }
              if ( *v76 )
              {
                v88 = (IPropertyBag *)SysAllocString(*v76);
                propBag[0] = v88;
                if ( !v88 )
                  goto LABEL_264;
              }
              else
              {
                v88 = 0;
                propBag[0] = 0;
              }
              v89 = SysAllocString(psz);
              v90 = v89;
              *(_QWORD *)phkResult = v89;
              if ( !v89 )
                ATL::AtlThrowImpl(-2147024882);
              if ( !v88 )
                break;
              (*(void (__fastcall **)(struct ITheme *, IPropertyBag *, OLECHAR *))(*(_QWORD *)v19 + 312LL))(
                v19,
                v88,
                v89);
              SysFreeString(v90);
              SysFreeString((BSTR)v88);
              if ( !*off_18006E940[++v75] )
                goto LABEL_219;
            }
            Instance = -2147024882;
            SysFreeString(v89);
            SysFreeString(0);
          }
LABEL_219:
          memset_0(pszPath, 0, 0x208u);
          phkResult[0] = 0;
          LODWORD(ppv) = 520;
          psz[0] = 0;
          v91 = SHGetValueW(HKEY_CURRENT_USER, L"Control Panel\\Cursors", 0, phkResult, pszPath, (DWORD *)&ppv);
          v92 = v91 < 0;
          if ( v91 > 0 )
            v92 = 1;
          if ( v92 )
            goto LABEL_234;
          if ( phkResult[0] - 1 <= 1 && !(unsigned int)SHExpandEnvironmentStringsW(pszPath, psz, 260) )
          {
            v93 = pszPath;
            v94 = psz;
            v95 = 2147483646;
            do
            {
              if ( !v95 )
                break;
              v96 = *v93;
              if ( !*v93 )
                break;
              ++v93;
              *v94++ = v96;
              --v95;
              --v8;
            }
            while ( v8 );
            v97 = v94 - 1;
            if ( v8 )
              v97 = v94;
            *v97 = 0;
          }
          v98 = (IPropertyBag *)SysAllocString(L"DefaultValue");
          propBag[0] = v98;
          if ( v98 )
          {
            v99 = SysAllocString(psz);
            v100 = v99;
            *(_QWORD *)phkResult = v99;
            if ( !v99 )
              ATL::AtlThrowImpl(-2147024882);
            (*(void (__fastcall **)(struct ITheme *, IPropertyBag *, BSTR))(*(_QWORD *)v19 + 312LL))(v19, v98, v99);
            SysFreeString(v100);
            SysFreeString((BSTR)v98);
LABEL_234:
            if ( Instance >= 0 )
            {
              *(_OWORD *)propBag = 0;
              LODWORD(propBag[0]) = 16;
              if ( !SystemParametersInfoW(0x42u, 0x10u, propBag, 0) || (BYTE4(propBag[0]) & 1) == 0 )
                goto LABEL_268;
              memset_0(pszPath, 0, 0x208u);
              phkResult[0] = 520;
              v101 = RegGetValueW(
                       HKEY_CURRENT_USER,
                       L"Control Panel\\Appearance",
                       L"NewCurrent",
                       2u,
                       0,
                       pszPath,
                       phkResult);
              v102 = v101 < 0;
              if ( v101 )
              {
                pszPath[0] = 0;
                if ( v101 > 0 )
                  v102 = 1;
              }
              if ( v102
                || (v103 = wcschr(pszPath, 0x2Du)) == 0
                || (int)(-849 - _o__wtoi(v103)) <= 0
                || (Instance = (*(__int64 (__fastcall **)(struct ITheme *))(*(_QWORD *)v19 + 472LL))(v19), Instance >= 0) )
              {
LABEL_268:
                *(_OWORD *)propBag = 0;
                Instance = CoCreateGuid((GUID *)propBag);
                if ( Instance >= 0 )
                {
                  Instance = (*(__int64 (__fastcall **)(struct ITheme *, IPropertyBag **))(*(_QWORD *)v19 + 128LL))(
                               v19,
                               propBag);
                  if ( Instance >= 0 )
                  {
                    if ( v109 )
                    {
                      rguid = *(GUID *)propBag;
                      if ( StringFromGUID2(&rguid, sz, 39) )
                      {
                        v104 = -1;
                        do
                          ++v104;
                        while ( sz[v104] );
                        if ( v104 < 0x7FFFFFFF )
                        {
                          *(_QWORD *)phkResult = 0;
                          if ( !RegCreateKeyExW(
                                  HKEY_CURRENT_USER,
                                  L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
                                  0,
                                  0,
                                  0,
                                  2u,
                                  0,
                                  (PHKEY)phkResult,
                                  0) )
                          {
                            RegSetValueExW(*(HKEY *)phkResult, L"DefaultThemeId", 0, 1u, (const BYTE *)sz, 2 * v104 + 2);
                            if ( *(_QWORD *)phkResult != -2147483647 )
                              RegCloseKey(*(HKEY *)phkResult);
                          }
                        }
                      }
                    }
                    goto LABEL_209;
                  }
                }
              }
            }
LABEL_207:
            DeleteFileW(lpFileName);
            v85 = **(_QWORD **)&rguid.Data1;
            **(_QWORD **)&rguid.Data1 = 0;
            if ( v85 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
LABEL_209:
            v86 = v112;
            if ( v112 )
            {
              v112 = 0;
              (*(void (__fastcall **)(BSTR))(*(_QWORD *)v86 + 16LL))(v86);
            }
            return (unsigned int)Instance;
          }
LABEL_264:
          ATL::AtlThrowImpl(-2147024882);
        }
      }
      else if ( (_DWORD)ppv == 4 )
      {
        if ( (_WORD)pcbData == 48 )
        {
          v38 = 0;
          v42 = 0;
          goto LABEL_121;
        }
        if ( (_WORD)pcbData == 49 )
        {
          v38 = 1;
          v42 = 0;
          goto LABEL_121;
        }
      }
    }
    v42 = (unsigned __int16)v42 | 0x80070000;
    goto LABEL_121;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000eeb0  mov     [rsp-8+arg_18], rbx
0x18000eeb5  push    rbp
0x18000eeb6  push    rsi
0x18000eeb7  push    rdi
0x18000eeb8  push    r12
0x18000eeba  push    r13
0x18000eebc  push    r14
0x18000eebe  push    r15
0x18000eec0  lea     rbp, [rsp-0D80h]
0x18000eec8  sub     rsp, 0E80h
0x18000eecf  mov     rax, cs:__security_cookie
0x18000eed6  xor     rax, rsp
0x18000eed9  mov     [rbp+0DB0h+var_40], rax
0x18000eee0  mov     [rsp+0EB0h+var_E4C], r9b
0x18000eee5  mov     rbx, r8
0x18000eee8  mov     r14, rdx
0x18000eeeb  mov     [rbp+0DB0h+lpFileName], rdx
0x18000eeef  mov     r12, rcx
0x18000eef2  mov     [rbp+0DB0h+propBag], rcx
0x18000eef6  mov     rdi, [rbp+0DB0h+arg_20]
0x18000eefd  mov     qword ptr [rbp+0DB0h+rguid.Data1], rdi
0x18000ef01  mov     rdx, 0FFFFFFFFFFFFFFFFh; cchCount1
0x18000ef08  mov     r13d, 104h
0x18000ef0e  test    r8, r8
0x18000ef11  jz      loc_18000F048
0x18000ef17  test    r14, r14
0x18000ef1a  jz      loc_18000F048
0x18000ef20  test    rdi, rdi
0x18000ef23  jz      loc_18000F048
0x18000ef29  mov     qword ptr [rdi], 0
0x18000ef30  mov     [rsp+0EB0h+bIgnoreCase], 1; bIgnoreCase
0x18000ef38  mov     r9d, edx; cchCount2
0x18000ef3b  mov     r8, r14; lpString2
0x18000ef3e  mov     rcx, rbx; lpString1
0x18000ef41  call    cs:__imp_CompareStringOrdinal
0x18000ef47  cmp     eax, 2
0x18000ef4a  jz      loc_18000EFF7
0x18000ef50  mov     eax, 7FFFFFFEh
0x18000ef55  mov     rcx, r14
0x18000ef58  mov     edx, r13d
0x18000ef5b  lea     r8, [rbp+0DB0h+pszPath]
0x18000ef62  test    rax, rax
0x18000ef65  jz      short loc_18000EF86
0x18000ef67  movzx   r9d, word ptr [rcx]
0x18000ef6b  test    r9w, r9w
0x18000ef6f  jz      short loc_18000EF86
0x18000ef71  add     rcx, 2
0x18000ef75  mov     [r8], r9w
0x18000ef79  add     r8, 2
0x18000ef7d  dec     rax
0x18000ef80  sub     rdx, 1
0x18000ef84  jnz     short loc_18000EF62
0x18000ef86  mov     esi, 8007007Ah
0x18000ef8b  xor     eax, eax
0x18000ef8d  test    rdx, rdx
0x18000ef90  cmovnz  esi, eax
0x18000ef93  lea     rcx, [r8-2]
0x18000ef97  cmovnz  rcx, r8
0x18000ef9b  mov     [rcx], ax
0x18000ef9e  jz      loc_18000F04D
0x18000efa4  lea     rcx, [rbp+0DB0h+pszPath]; pszPath
0x18000efab  call    cs:__imp_PathRemoveFileSpecW
0x18000efb1  xor     r8d, r8d; psa
0x18000efb4  lea     rdx, [rbp+0DB0h+pszPath]; pszPath
0x18000efbb  xor     ecx, ecx; hwnd
0x18000efbd  call    cs:__imp_SHCreateDirectoryExW
0x18000efc3  test    eax, eax
0x18000efc5  jz      short loc_18000EFD9
0x18000efc7  cmp     eax, 0B7h
0x18000efcc  jz      short loc_18000EFD9
0x18000efce  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000efd3  mov     esi, eax
0x18000efd5  test    eax, eax
0x18000efd7  js      short loc_18000F04D
0x18000efd9  xor     r8d, r8d; bFailIfExists
0x18000efdc  mov     rdx, r14; lpNewFileName
0x18000efdf  mov     rcx, rbx; lpExistingFileName
0x18000efe2  call    cs:__imp_CopyFileW
0x18000efe8  test    eax, eax
0x18000efea  jnz     short loc_18000EFF7
0x18000efec  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000eff1  mov     esi, eax
0x18000eff3  test    eax, eax
0x18000eff5  js      short loc_18000F04D
0x18000eff7  mov     rdx, rdi; struct ITheme **
0x18000effa  mov     rcx, r14; unsigned __int16 *
0x18000effd  call    ?CThemeFile_CreateInstance@@YAJPEBGPEAPEAUITheme@@@Z; CThemeFile_CreateInstance(ushort const *,ITheme * *)
0x18000f002  mov     esi, eax
0x18000f004  test    eax, eax
0x18000f006  js      short loc_18000F04D
0x18000f008  lea     rcx, psz; "RJSPBS"
0x18000f00f  call    cs:__imp_SysAllocString
0x18000f015  mov     rbx, rax
0x18000f018  mov     [rsp+0EB0h+var_E38], rax
0x18000f01d  test    rax, rax
0x18000f020  jz      loc_180010447
0x18000f026  mov     rcx, [rdi]
0x18000f029  mov     rax, [rcx]
0x18000f02c  mov     rdx, rbx
0x18000f02f  mov     rax, [rax+1E8h]
0x18000f036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f03b  mov     esi, eax
0x18000f03d  mov     rcx, rbx; bstrString
0x18000f040  call    cs:__imp_SysFreeString
0x18000f046  jmp     short loc_18000F04D
0x18000f048  mov     esi, 80070057h
0x18000f04d  test    esi, esi
0x18000f04f  js      loc_18000FFF2
0x18000f055  mov     r15, [rdi]
0x18000f058  mov     rax, [r15]
0x18000f05b  mov     rcx, r15
0x18000f05e  mov     rax, [rax+228h]
0x18000f065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f06a  mov     rax, [r15]
0x18000f06d  mov     rcx, r15
0x18000f070  mov     rax, [rax+198h]
0x18000f077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f07c  mov     rax, [r15]
0x18000f07f  mov     rcx, r15
0x18000f082  mov     rax, [rax+0D8h]
0x18000f089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f08e  xor     edi, edi
0x18000f090  mov     [rsp+0EB0h+var_E38], rdi
0x18000f095  mov     rax, [r15]
0x18000f098  lea     r8, [rsp+0EB0h+var_E38]
0x18000f09d  lea     rdx, _GUID_6a0522b4_8e09_4aa8_985a_9e52d534977a
0x18000f0a4  mov     rcx, r15
0x18000f0a7  mov     rax, [rax]
0x18000f0aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0af  mov     rcx, [rbp+0DB8h]
0x18000f0b6  test    eax, eax
0x18000f0b8  jns     short loc_18000F0C1
0x18000f0ba  mov     edx, 9C0h
0x18000f0bf  jmp     short loc_18000F0E2
0x18000f0c1  mov     rcx, [rsp+0EB0h+var_E38]
0x18000f0c6  mov     rax, [rcx]
0x18000f0c9  mov     rax, [rax+28h]
0x18000f0cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0d2  mov     rcx, [rbp+0DB8h]; this
0x18000f0d9  test    eax, eax
0x18000f0db  jns     short loc_18000F0F1
0x18000f0dd  mov     edx, 9C2h; void *
0x18000f0e2  mov     r9d, eax; char *
0x18000f0e5  lea     r8, aShellThemesThe_3; "shell\\themes\\themeui\\themefile.cpp"
0x18000f0ec  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f0f1  mov     [rsp+0EB0h+value], edi
0x18000f0f5  lea     r8, [rsp+0EB0h+value]; value
0x18000f0fa  lea     rdx, propName; "Background_Multimon"
0x18000f101  mov     rcx, r12; propBag
0x18000f104  call    cs:__imp_PSPropertyBag_ReadBOOL
0x18000f10a  test    eax, eax
0x18000f10c  js      short loc_18000F126
0x18000f10e  mov     rax, [r15]
0x18000f111  mov     edx, [rsp+0EB0h+value]
0x18000f115  mov     rcx, r15
0x18000f118  mov     rax, [rax+1B8h]
0x18000f11f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f124  mov     esi, eax
0x18000f126  cmp     [rsp+0EB0h+value], 0
0x18000f12b  jz      loc_18000F1E5
0x18000f131  mov     ecx, 50h ; 'P'; nIndex
0x18000f136  call    cs:__imp_GetSystemMetrics
0x18000f13c  mov     r14d, eax
0x18000f13f  test    esi, esi
0x18000f141  js      loc_18000FFAE
0x18000f147  cmp     edi, r14d
0x18000f14a  jnb     loc_18000F2E3
0x18000f150  mov     [rsp+0EB0h+bIgnoreCase], edi
0x18000f154  lea     r9, aBackgroundsrcP; "BackgroundSrc_Path"
0x18000f15b  lea     r8, aSU; "%s%u"
0x18000f162  mov     rdx, r13; unsigned __int64
0x18000f165  lea     rcx, [rbp+0DB0h+propName]; unsigned __int16 *
0x18000f16c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f171  mov     esi, eax
0x18000f173  test    eax, eax
0x18000f175  js      short loc_18000F1D6
0x18000f177  mov     r9d, r13d; characterCount
0x18000f17a  lea     r8, [rbp+0DB0h+psz]; value
0x18000f181  lea     rdx, [rbp+0DB0h+propName]; propName
0x18000f188  mov     rcx, r12; propBag
0x18000f18b  call    cs:__imp_PSPropertyBag_ReadStr
0x18000f191  test    eax, eax
0x18000f193  js      short loc_18000F1D6
0x18000f195  lea     rcx, [rbp+0DB0h+psz]; psz
0x18000f19c  call    cs:__imp_SysAllocString
0x18000f1a2  mov     rbx, rax
0x18000f1a5  mov     qword ptr [rsp+0EB0h+var_E60], rax
0x18000f1aa  test    rax, rax
0x18000f1ad  jz      loc_180010452
0x18000f1b3  mov     rax, [r15]
0x18000f1b6  lea     edx, [rdi+1]
0x18000f1b9  mov     r8, rbx
0x18000f1bc  mov     rcx, r15
0x18000f1bf  mov     rax, [rax+1C8h]
0x18000f1c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1cb  mov     esi, eax
0x18000f1cd  mov     rcx, rbx; bstrString
0x18000f1d0  call    cs:__imp_SysFreeString
0x18000f1d6  test    esi, esi
0x18000f1d8  js      loc_18000FFAE
0x18000f1de  inc     edi
0x18000f1e0  jmp     loc_18000F147
0x18000f1e5  mov     r9d, r13d; characterCount
0x18000f1e8  lea     r8, [rbp+0DB0h+psz]; value
0x18000f1ef  lea     rdx, aBackgroundsrcP; "BackgroundSrc_Path"
0x18000f1f6  mov     rcx, r12; propBag
0x18000f1f9  call    cs:__imp_PSPropertyBag_ReadStr
0x18000f1ff  test    eax, eax
0x18000f201  js      short loc_18000F241
0x18000f203  lea     rcx, [rbp+0DB0h+psz]; psz
0x18000f20a  call    cs:__imp_SysAllocString
0x18000f210  mov     rbx, rax
0x18000f213  mov     [rsp+0EB0h+ppv], rax
0x18000f218  test    rax, rax
0x18000f21b  jz      loc_18001045D
0x18000f221  mov     rax, [r15]
0x18000f224  mov     rdx, rbx
0x18000f227  mov     rcx, r15
0x18000f22a  mov     rax, [rax+0B0h]
0x18000f231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f236  mov     esi, eax
0x18000f238  mov     rcx, rbx; bstrString
0x18000f23b  call    cs:__imp_SysFreeString
0x18000f241  mov     qword ptr [rsp+0EB0h+var_E60], rdi
0x18000f246  mov     rax, [r15]
0x18000f249  lea     r8, [rsp+0EB0h+var_E60]
0x18000f24e  lea     rdx, _GUID_6a0522b4_8e09_4aa8_985a_9e52d534977a
0x18000f255  mov     rcx, r15
0x18000f258  mov     rax, [rax]
0x18000f25b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f260  mov     rcx, [rbp+0DB8h]; this
0x18000f267  test    eax, eax
0x18000f269  jns     short loc_18000F281
0x18000f26b  mov     r9d, eax; char *
0x18000f26e  lea     r8, aShellThemesThe_3; "shell\\themes\\themeui\\themefile.cpp"
0x18000f275  mov     edx, 9E7h; void *
0x18000f27a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f27f  jmp     short loc_18000F2BD
0x18000f281  mov     [rsp+0EB0h+pdwType], edi
0x18000f285  lea     r8, [rsp+0EB0h+pdwType]; value
0x18000f28a  lea     rdx, aWindowsspotlig; "WindowsSpotlight"
0x18000f291  mov     rcx, r12; propBag
0x18000f294  call    cs:__imp_PSPropertyBag_ReadDWORD
0x18000f29a  test    eax, eax
0x18000f29c  js      short loc_18000F2BD
0x18000f29e  cmp     [rsp+0EB0h+pdwType], 1
0x18000f2a3  jnz     short loc_18000F2BD
0x18000f2a5  mov     rcx, qword ptr [rsp+0EB0h+var_E60]
0x18000f2aa  mov     rax, [rcx]
0x18000f2ad  mov     edx, 1
0x18000f2b2  mov     rax, [rax+18h]
0x18000f2b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2bb  mov     esi, eax
0x18000f2bd  mov     rcx, qword ptr [rsp+0EB0h+var_E60]
0x18000f2c2  test    rcx, rcx
0x18000f2c5  jz      short loc_18000F2D9
0x18000f2c7  mov     qword ptr [rsp+0EB0h+var_E60], rdi
0x18000f2cc  mov     rax, [rcx]
0x18000f2cf  mov     rax, [rax+10h]
0x18000f2d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2d8  nop
0x18000f2d9  test    esi, esi
0x18000f2db  js      loc_18000FFB0
0x18000f2e1  jmp     short loc_18000F2E5
0x18000f2e3  xor     edi, edi
0x18000f2e5  mov     [rsp+0EB0h+pdwType], edi
0x18000f2e9  lea     r8, [rsp+0EB0h+pdwType]; value
0x18000f2ee  lea     rdx, aBackgroundTile; "Background_TILE"
0x18000f2f5  mov     rcx, r12; propBag
0x18000f2f8  call    cs:__imp_PSPropertyBag_ReadDWORD
0x18000f2fe  test    eax, eax
0x18000f300  js      short loc_18000F322
0x18000f302  mov     rax, [r15]
0x18000f305  mov     edx, [rsp+0EB0h+pdwType]
0x18000f309  mov     rcx, r15
0x18000f30c  mov     rax, [rax+0C0h]
0x18000f313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f318  mov     esi, eax
0x18000f31a  test    eax, eax
0x18000f31c  js      loc_18000FFB0
0x18000f322  mov     [rsp+0EB0h+ppv], rdi
0x18000f327  lea     r9, [rsp+0EB0h+ppv]; ppv
0x18000f32c  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18000f333  lea     rdx, aSlideshow; "Slideshow"
0x18000f33a  mov     rcx, r12; propBag
0x18000f33d  call    cs:__imp_PSPropertyBag_ReadUnknown
0x18000f343  test    eax, eax
0x18000f345  js      short loc_18000F3B2
0x18000f347  mov     qword ptr [rsp+0EB0h+var_E60], rdi
0x18000f34c  mov     rcx, [rsp+0EB0h+ppv]
0x18000f351  mov     rax, [rcx]
0x18000f354  lea     r8, [rsp+0EB0h+var_E60]
0x18000f359  lea     rdx, _GUID_b6f3692b_8a89_4f93_800a_4c6cf8e93382
0x18000f360  mov     rax, [rax]
0x18000f363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f368  mov     esi, eax
0x18000f36a  test    eax, eax
0x18000f36c  js      short loc_18000F398
0x18000f36e  mov     rax, [r15]
0x18000f371  mov     rdx, qword ptr [rsp+0EB0h+var_E60]
  ... truncated ...
```
