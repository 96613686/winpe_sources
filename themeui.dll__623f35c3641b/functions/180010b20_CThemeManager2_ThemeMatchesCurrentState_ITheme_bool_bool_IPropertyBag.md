# CThemeManager2::_ThemeMatchesCurrentState(ITheme *,bool *,bool *,IPropertyBag * *)

- ea: `0x180010b20`
- end: `0x180012b56`
- name: `?_ThemeMatchesCurrentState@CThemeManager2@@AEAAJPEAUITheme@@PEA_N1PEAPEAUIPropertyBag@@@Z`
- size: `8246`
- prototype: `__int64 __usercall@<rax>(CThemeManager2 *__hidden this@<rcx>, struct ITheme *@<rdx>, bool *@<r8>, bool *@<r9>, struct IPropertyBag **)`
- caller_count: `1`
- callee_count: `39`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180010820`

## callees

- `0x1800049f0`
- `0x180005410`
- `0x180007d20`
- `0x1800082f0`
- `0x1800089c0`
- `0x18000b5ec`
- `0x18000c2c4`
- `0x18000c470`
- `0x18000e780`
- `0x180010b20`
- `0x180012ea0`
- `0x180014e40`
- `0x180015700`
- `0x180016ca0`
- `0x1800179e0`
- `0x180018110`
- `0x180019070`
- `0x1800199d0`
- `0x18001a170`
- `0x18001a2f8`
- `0x18001b9f8`
- `0x18001bcfc`
- `0x18001d4b4`
- `0x18001e280`
- `0x18001f300`
- `0x180020db4`
- `0x180029324`
- `0x1800358c0`
- `0x180035d00`
- `0x18003633c`
- `0x18003c1f4`
- `0x18003e95c`
- `0x180040468`
- `0x180042664`
- `0x1800427dc`
- `0x180046658`
- `0x180051548`
- `0x180051794`
- `0x18006d010`

## import_xrefs

- `SHCORE!SHGetValueW` at `0x18001211f`
- `SHCORE!SHGetValueW` at `0x180012248`
- `SHCORE!SHGetValueW` at `0x1800125e1`
- `SHCORE!SHGetValueW` at `0x18001211f`
- `SHCORE!SHGetValueW` at `0x180012248`
- `SHCORE!SHGetValueW` at `0x1800125e1`
- `SHELL32!SHGetNameFromIDList` at `0x180010ce2`
- `SHELL32!SHGetNameFromIDList` at `0x180010ce2`
- `SHELL32!__imp_ILClone` at `0x180010cc3`
- `SHELL32!__imp_ILClone` at `0x180010cc3`
- `SHELL32!__imp_SHRestricted` at `0x18001166c`
- `SHELL32!__imp_SHRestricted` at `0x18001166c`
- `SHELL32!__imp_ILFree` at `0x180010ced`
- `SHELL32!__imp_ILFree` at `0x180010ced`
- `SHLWAPI!StrChrW` at `0x180011fb8`
- `SHLWAPI!StrChrW` at `0x180011fb8`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x180012158`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18001227d`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x180012613`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x180012158`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18001227d`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x180012613`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010c16`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010c16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010c02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010c02`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180011198`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001135f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180011940`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180011965`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001198a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180011c5d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180011ccd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180011eb6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180012043`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180012376`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180012442`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001281f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180011198`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001135f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180011940`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180011965`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001198a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180011c5d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180011ccd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180011eb6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180012043`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180012376`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180012442`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001281f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010db3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011053`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011239`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011530`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011578`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010db3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011053`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011239`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011530`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011578`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010bf4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010d2f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010bf4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010d2f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001175f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011e5a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012935`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001175f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011e5a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012935`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011fd6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011fd6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180011462`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180011462`
- `PROPSYS!PSPropertyBag_WriteUnknown` at `0x180010ebe`
- `PROPSYS!PSPropertyBag_WriteUnknown` at `0x180010ebe`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x180010fe6`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x18001162f`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x180010fe6`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x18001162f`
- `PROPSYS!PSPropertyBag_WriteBOOL` at `0x1800110f1`
- `PROPSYS!PSPropertyBag_WriteBOOL` at `0x1800110f1`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x180011227`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x180011563`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x180011a80`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x180011aa4`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x180011ac8`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1800124e8`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x180011227`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x180011563`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x180011a80`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x180011aa4`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x180011ac8`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1800124e8`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180010bbc`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180010bbc`
- `UxTheme!GetCurrentThemeName` at `0x1800118a3`
- `UxTheme!GetCurrentThemeName` at `0x1800118a3`
- `UxTheme!IsCompositionActive` at `0x1800116a9`
- `UxTheme!IsCompositionActive` at `0x1800116a9`
- `UxTheme!__imp_ShouldAppsUseDarkMode` at `0x180012a03`
- `UxTheme!__imp_ShouldAppsUseDarkMode` at `0x180012a03`
- `UxTheme!__imp_ShouldSystemUseDarkMode` at `0x180012a32`
- `UxTheme!__imp_ShouldSystemUseDarkMode` at `0x180012a32`
- `OLEAUT32!__imp_SysAllocString` at `0x180011da8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800122f8`
- `OLEAUT32!__imp_SysAllocString` at `0x180011da8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800122f8`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800126fb`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800126fb`
- `OLEAUT32!__imp_SysFreeString` at `0x180011245`
- `OLEAUT32!__imp_SysFreeString` at `0x180011513`
- `OLEAUT32!__imp_SysFreeString` at `0x180011adc`
- `OLEAUT32!__imp_SysFreeString` at `0x180011ae8`
- `OLEAUT32!__imp_SysFreeString` at `0x180011af4`
- `OLEAUT32!__imp_SysFreeString` at `0x180011d13`
- `OLEAUT32!__imp_SysFreeString` at `0x180011de1`
- `OLEAUT32!__imp_SysFreeString` at `0x180011f00`
- `OLEAUT32!__imp_SysFreeString` at `0x18001249a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800124f8`
- `OLEAUT32!__imp_SysFreeString` at `0x180012504`
- `OLEAUT32!__imp_SysFreeString` at `0x1800127ac`
- `OLEAUT32!__imp_SysFreeString` at `0x180012870`
- `OLEAUT32!__imp_SysFreeString` at `0x180012880`
- `OLEAUT32!__imp_SysFreeString` at `0x180011245`
- `OLEAUT32!__imp_SysFreeString` at `0x180011513`
- `OLEAUT32!__imp_SysFreeString` at `0x180011adc`
- `OLEAUT32!__imp_SysFreeString` at `0x180011ae8`
- `OLEAUT32!__imp_SysFreeString` at `0x180011af4`
- `OLEAUT32!__imp_SysFreeString` at `0x180011d13`
- `OLEAUT32!__imp_SysFreeString` at `0x180011de1`
- `OLEAUT32!__imp_SysFreeString` at `0x180011f00`
- `OLEAUT32!__imp_SysFreeString` at `0x18001249a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800124f8`
- `OLEAUT32!__imp_SysFreeString` at `0x180012504`
- `OLEAUT32!__imp_SysFreeString` at `0x1800127ac`
- `OLEAUT32!__imp_SysFreeString` at `0x180012870`
- `OLEAUT32!__imp_SysFreeString` at `0x180012880`
- `OLEAUT32!__imp_SysStringLen` at `0x180011e92`
- `OLEAUT32!__imp_SysStringLen` at `0x18001233f`
- `OLEAUT32!__imp_SysStringLen` at `0x18001241e`
- `OLEAUT32!__imp_SysStringLen` at `0x1800126da`
- `OLEAUT32!__imp_SysStringLen` at `0x18001271a`
- `OLEAUT32!__imp_SysStringLen` at `0x1800127fa`
- `OLEAUT32!__imp_SysStringLen` at `0x180011e92`
- `OLEAUT32!__imp_SysStringLen` at `0x18001233f`
- `OLEAUT32!__imp_SysStringLen` at `0x18001241e`
- `OLEAUT32!__imp_SysStringLen` at `0x1800126da`
- `OLEAUT32!__imp_SysStringLen` at `0x18001271a`
- `OLEAUT32!__imp_SysStringLen` at `0x1800127fa`

## string_xrefs

- `0x1800111ec`: `BackgroundSrc_Path`
- `0x180011557`: `BackgroundSrc_Path`
- `0x180011a74`: `VisualStyle_Path`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CThemeManager2::_ThemeMatchesCurrentState(
        CThemeManager2 *this,
        struct ITheme *a2,
        bool *a3,
        bool *a4,
        struct IPropertyBag **a5)
{
  bool *v6; // rsi
  struct ITheme *v7; // r12
  struct IUnknownVtbl *v9; // r14
  __int64 v10; // r8
  HRESULT v11; // r15d
  __int64 v12; // rdx
  HANDLE ProcessHeap; // rax
  IUnknown *v14; // rax
  IUnknown *v15; // rdi
  HRESULT UsingAPI; // esi
  volatile signed __int32 *lpVtbl; // rax
  ULONG (__stdcall *Release)(IUnknown *); // rax
  _DWORD *v19; // rax
  const ITEMIDLIST *v20; // rax
  ITEMIDLIST *v21; // r15
  HRESULT v22; // ebx
  int (*v23)(struct IXFeedFolder *, void *); // rdx
  int (*v24)(struct IXFeed *, void *); // r8
  LPVOID v25; // rbx
  __int64 v26; // rax
  int v27; // eax
  int v28; // r14d
  bool v29; // si
  int v30; // ebx
  int v31; // eax
  CThemeManager2 *v32; // rcx
  DWORD IsDesktopSpotlightEnabled; // edi
  LPCWCH v34; // rcx
  unsigned int v35; // edi
  void *v36; // r8
  unsigned int v37; // edx
  bool *v38; // rdi
  unsigned int v39; // ebx
  bool v40; // bl
  int v41; // eax
  CThemeManager2 *v42; // rcx
  bool v43; // al
  LPCWCH v44; // rcx
  _QWORD *v45; // rcx
  __int64 v46; // rdx
  _QWORD *v47; // rcx
  __int64 v48; // rdx
  LPVOID v49; // r9
  int v50; // eax
  __int64 v51; // r8
  bool v52; // si
  int v53; // edi
  int *v54; // rdx
  bool v55; // di
  int v56; // ebx
  LSTATUS ValueW; // eax
  signed int v58; // ecx
  int v59; // eax
  _QWORD *v60; // rcx
  __int64 v61; // rdx
  bool v62; // zf
  WCHAR *v63; // rcx
  unsigned int v64; // r9d
  int v65; // ebx
  _QWORD *v66; // rcx
  int v67; // ebx
  char v68; // di
  int i; // ebx
  int SoundSchemeShortName; // ebx
  unsigned int v71; // r8d
  int v72; // eax
  int AllRegSoundEvents; // r12d
  struct _DPA *v74; // rdi
  int v75; // r15d
  struct ITheme *v76; // r13
  const OLECHAR *Ptr; // rax
  const OLECHAR *v78; // r14
  __int64 v79; // rsi
  BSTR v80; // rax
  OLECHAR *v81; // rbx
  int v82; // esi
  int v83; // eax
  WCHAR v84; // cx
  bool v85; // sf
  int v86; // esi
  CThemeManager2 *v87; // rcx
  bool v88; // r14
  int j; // r13d
  const OLECHAR **v90; // r12
  const WCHAR *v91; // rbx
  const WCHAR *v92; // rax
  const WCHAR *v93; // rdi
  const OLECHAR *v94; // r14
  __int64 v95; // rbx
  LPWSTR v96; // rax
  WCHAR *v97; // r8
  WCHAR v98; // cx
  __int64 v99; // rdi
  unsigned __int64 v100; // rcx
  LSTATUS v101; // eax
  bool v102; // sf
  __int64 v103; // rdx
  WCHAR *v104; // r8
  __int64 v105; // r9
  WCHAR *v106; // rax
  WCHAR v107; // cx
  unsigned __int64 v108; // rcx
  LSTATUS v109; // eax
  bool v110; // sf
  __int64 v111; // rdx
  WCHAR *v112; // r8
  WCHAR v113; // cx
  WCHAR *v114; // rcx
  WCHAR *v115; // rbx
  struct ITheme *v116; // rdi
  __int64 v117; // rcx
  LPCWCH v118; // r9
  __int64 v119; // rdx
  WCHAR *v120; // r8
  WCHAR v121; // ax
  WCHAR *v122; // rcx
  signed int v123; // r14d
  __int64 v124; // rsi
  LSTATUS v125; // eax
  bool v126; // sf
  __int64 v127; // rcx
  WCHAR *v128; // r8
  __int64 v129; // rdx
  WCHAR *v130; // rax
  WCHAR v131; // r9
  WCHAR *v132; // rcx
  WCHAR *v133; // r13
  WCHAR *v134; // rax
  OLECHAR *v135; // rbx
  _WORD *v136; // rsi
  __int64 v137; // rdi
  signed int v138; // eax
  __int64 v139; // r15
  signed int v140; // r12d
  int v141; // eax
  BSTR v142; // r14
  errno_t v143; // eax
  errno_t v144; // eax
  const WCHAR *v145; // rdi
  int v146; // eax
  LSTATUS v147; // eax
  bool v148; // sf
  unsigned int v149; // eax
  __int64 v150; // r8
  __int64 v151; // rdx
  _QWORD *v152; // rcx
  BOOL bIgnoreCase[2]; // [rsp+20h] [rbp-E0h]
  unsigned int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  LPCWCH lpString1; // [rsp+48h] [rbp-B8h] BYREF
  int v158; // [rsp+50h] [rbp-B0h] BYREF
  DWORD value; // [rsp+54h] [rbp-ACh] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  PWSTR ppszName; // [rsp+60h] [rbp-A0h] BYREF
  bool *v162; // [rsp+68h] [rbp-98h]
  bool v163; // [rsp+70h] [rbp-90h]
  void *ppv; // [rsp+78h] [rbp-88h] BYREF
  struct IDesktopWallpaperPrivate *v165; // [rsp+80h] [rbp-80h] BYREF
  int v166; // [rsp+88h] [rbp-78h] BYREF
  struct ITheme *v167; // [rsp+90h] [rbp-70h]
  FILETIME FileTime1; // [rsp+98h] [rbp-68h] BYREF
  struct IUnknownVtbl *v169; // [rsp+A0h] [rbp-60h]
  bool *v170; // [rsp+A8h] [rbp-58h]
  struct IPropertyBag **v171; // [rsp+B0h] [rbp-50h]
  WCHAR pszThemeFileName[376]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR propName[376]; // [rsp+3B0h] [rbp+2B0h] BYREF
  WCHAR pszSizeBuff[264]; // [rsp+6A0h] [rbp+5A0h] BYREF
  WCHAR pszColorBuff[264]; // [rsp+8B0h] [rbp+7B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B18h] [rbp+A18h]

  v170 = a4;
  v6 = a3;
  v162 = a3;
  v7 = a2;
  v167 = a2;
  v171 = a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids);
  *v6 = 1;
  *a4 = 0;
  v9 = 0;
  *a5 = 0;
  ppv = 0;
  v11 = PSCreateMemoryPropertyStore(&GUID_55272a00_42cb_11ce_8135_00aa004bb851, &ppv);
  v158 = v11;
  if ( v11 < 0 )
    goto LABEL_418;
  v165 = 0;
  if ( CoCreateInstance(&CLSID_DesktopWallpaper, 0, 4u, &GUID_c182461f_dfac_4375_ab6e_4cc45aa7f9cc, (LPVOID *)&v165) >= 0 )
  {
    ProcessHeap = GetProcessHeap();
    v14 = (IUnknown *)HeapAlloc(ProcessHeap, 8u, 0x48u);
    v15 = v14;
    pv = v14;
    if ( v14 )
    {
      v14->lpVtbl = (struct IUnknownVtbl *)&CSlideshowSettingsAdapter::`vftable'{for `ISlideshowSettings'};
      v14[1].lpVtbl = (struct IUnknownVtbl *)&CSlideshowSettingsAdapter::`vftable'{for `ISlideshowSettingsInternal'};
      LODWORD(v14[2].lpVtbl) = 1;
      v14[3].lpVtbl = 0;
      v14[4].lpVtbl = (struct IUnknownVtbl *)1800000;
      LODWORD(v14[5].lpVtbl) = 1000;
      v14[6].lpVtbl = 0;
      v14[7].lpVtbl = 0;
      LODWORD(v14[8].lpVtbl) = 0;
      UsingAPI = CSlideshowSettings::LoadUsingAPI((CSlideshowSettings *)&v14[4]);
      if ( UsingAPI >= 0 )
      {
        if ( ((__int64)v15[7].lpVtbl & 4) == 0 )
          goto LABEL_31;
        lpVtbl = (volatile signed __int32 *)v15[6].lpVtbl;
        if ( lpVtbl )
          _InterlockedIncrement(lpVtbl);
        v9 = v15[6].lpVtbl;
        if ( v9 )
        {
          UsingAPI = 0;
          Release = v9->Release;
          if ( !Release )
            goto LABEL_16;
          v19 = *(_DWORD **)Release;
          if ( v19 )
            LODWORD(v19) = *v19;
          if ( !(_DWORD)v19 )
          {
LABEL_16:
            ppszName = 0;
            v20 = ILClone((LPCITEMIDLIST)v9->AddRef);
            v21 = (ITEMIDLIST *)v20;
            if ( v20 )
            {
              v22 = SHGetNameFromIDList(v20, SIGDN_FILESYSPATH, &ppszName);
              ILFree(v21);
              if ( v22 >= 0 )
              {
                FileTime1 = (FILETIME)ppszName;
                v169 = 0;
                pv = 0;
                UsingAPI = CoCreateInstance(
                             &CLSID_XFeedsManager,
                             0,
                             1u,
                             &GUID_5357e238_fb12_4aca_a930_cab7832b84bf,
                             &pv);
                if ( UsingAPI >= 0 )
                {
                  lpString1 = 0;
                  UsingAPI = (*(__int64 (__fastcall **)(LPVOID, GUID *, LPCWCH *))(*(_QWORD *)pv + 24LL))(
                               pv,
                               &GUID_4c963678_3a51_4b88_8531_98b90b6508f2,
                               &lpString1);
                  if ( UsingAPI < 0 )
                  {
                    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
                  }
                  else
                  {
                    EnumerateRSSFeedsInFolder((struct IXFeedFolder *)lpString1, v23, v24, &FileTime1);
                    (*(void (__fastcall **)(LPCWCH))(*(_QWORD *)lpString1 + 16LL))(lpString1);
                    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
                    v15[3].lpVtbl = v169;
                  }
                }
                CoTaskMemFree(ppszName);
              }
            }
            v11 = v158;
          }
          CFileSource::Release((CFileSource *)v9);
          v9 = 0;
          if ( UsingAPI >= 0 )
          {
            pv = 0;
            (*(void (__fastcall **)(struct ITheme *, LPVOID *))(*(_QWORD *)v7 + 224LL))(v7, &pv);
            v25 = pv;
            if ( v15 )
            {
              if ( pv )
              {
                UsingAPI = 0;
                if ( ((unsigned int (__fastcall *)(IUnknown *, LPVOID))v15->lpVtbl[1].AddRef)(v15, pv) )
                {
LABEL_41:
                  v11 = PSPropertyBag_WriteUnknown((IPropertyBag *)ppv, L"Slideshow", v15);
                  v158 = v11;
                  ((void (__fastcall *)(IUnknown *))v15->lpVtbl->Release)(v15);
LABEL_42:
                  if ( v25 )
                    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v25 + 16LL))(v25);
                  goto LABEL_44;
                }
              }
              else
              {
                UsingAPI = 0;
              }
LABEL_36:
              if ( !(unsigned int)CSlideshowSettings::s_PolicyAllowsSlideshow() )
              {
                *v162 = 0;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids);
                }
              }
              if ( !v15 )
                goto LABEL_42;
              goto LABEL_41;
            }
            UsingAPI = 0;
LABEL_35:
            if ( !v25 )
            {
LABEL_44:
              if ( v11 < 0 )
                goto LABEL_144;
              pcbData = (unsigned int)v9;
              if ( (*(int (__fastcall **)(struct ITheme *, DWORD *))(*(_QWORD *)v7 + 432LL))(v7, &pcbData) < 0 )
                pcbData = (unsigned int)v9;
              pv = v9;
              v27 = (*(__int64 (__fastcall **)(struct IDesktopWallpaperPrivate *, _QWORD, LPVOID *))(*(_QWORD *)v165 + 32LL))(
                      v165,
                      0,
                      &pv);
              v28 = v27;
              if ( v27 < 0 )
              {
                v9 = 0;
                goto LABEL_135;
              }
              v29 = UsingAPI >= 0;
              v30 = v27 == 1 && !v29;
              if ( IsDesktopSpotlightAllowedByPolicy() )
              {
                lpString1 = 0;
                v31 = (**(__int64 (__fastcall ***)(struct ITheme *, GUID *, LPCWCH *))v7)(
                        v7,
                        &GUID_6a0522b4_8e09_4aa8_985a_9e52d534977a,
                        &lpString1);
                if ( v31 >= 0 )
                {
                  value = 0;
                  if ( (*(int (__fastcall **)(LPCWCH, DWORD *))(*(_QWORD *)lpString1 + 32LL))(lpString1, &value) >= 0 )
                  {
                    IsDesktopSpotlightEnabled = CThemeManager2::_IsDesktopSpotlightEnabled(v32);
                    PSPropertyBag_WriteDWORD((IPropertyBag *)ppv, L"WindowsSpotlight", IsDesktopSpotlightEnabled);
                    if ( !v30 || (v30 = 1, (_BYTE)IsDesktopSpotlightEnabled) )
                      v30 = 0;
                    if ( (value != 0) != (_BYTE)IsDesktopSpotlightEnabled )
                      *v162 = 0;
                  }
                }
                else
                {
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x14C,
                    (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
                    (const char *)(unsigned int)v31,
                    bIgnoreCase[0]);
                }
                v34 = lpString1;
                if ( lpString1 )
                {
                  lpString1 = 0;
                  (*(void (__fastcall **)(LPCWCH))(*(_QWORD *)v34 + 16LL))(v34);
                }
              }
              if ( v30 )
              {
                CThemeManager2::_LoadPerMonitorData(this, v165);
                v35 = 0;
                if ( *((_DWORD *)this + 556) )
                {
                  v36 = pv;
                  do
                  {
                    CoTaskMemFree(v36);
                    v28 = (*(__int64 (__fastcall **)(struct IDesktopWallpaperPrivate *, _QWORD, LPVOID *))(*(_QWORD *)v165 + 32LL))(
                            v165,
                            *((_QWORD *)this + v35 + 279),
                            &pv);
                    v36 = pv;
                    if ( v28 >= 0 && *(_WORD *)pv )
                      break;
                    v37 = *((_DWORD *)this + 556);
                    if ( v35 == v37 - 1 )
                      v30 = 0;
                    ++v35;
                  }
                  while ( v35 < v37 );
                }
              }
              v38 = v162;
              if ( !v29 && pcbData != v30 )
              {
                *v162 = 0;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids);
                }
              }
              v11 = PSPropertyBag_WriteBOOL((IPropertyBag *)ppv, L"Background_Multimon", v30);
              v158 = v11;
              if ( v11 < 0 )
                goto LABEL_131;
              if ( v30 )
              {
                v9 = 0;
                v39 = 0;
                do
                {
                  if ( v39 >= *((_DWORD *)this + 556) )
                    break;
                  ppszName = 0;
                  (*(void (__fastcall **)(struct ITheme *, _QWORD, PWSTR *))(*(_QWORD *)v7 + 448LL))(
                    v7,
                    v39 + 1,
                    &ppszName);
                  lpString1 = 0;
                  if ( (*(int (__fastcall **)(struct IDesktopWallpaperPrivate *, _QWORD, LPCWCH *))(*(_QWORD *)v165
                                                                                                  + 32LL))(
                         v165,
                         *((_QWORD *)this + v39 + 279),
                         &lpString1) >= 0 )
                  {
                    if ( ppszName )
                    {
                      if ( CompareStringOrdinal(lpString1, -1, ppszName, -1, 1) != 2 )
                      {
                        *v162 = 0;
                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                        {
                          WPP_SF_SS(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            13,
                            (unsigned int)WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids,
                            (_DWORD)lpString1,
                            (__int64)ppszName);
                        }
                      }
                    }
                    bIgnoreCase[0] = v39;
                    v11 = StringCchPrintfW(propName, 0x104u, L"%s%u", L"BackgroundSrc_Path", *(_QWORD *)bIgnoreCase);
                    v158 = v11;
                    if ( v11 >= 0 )
                    {
                      v11 = PSPropertyBag_WriteStr((IPropertyBag *)ppv, propName, lpString1);
                      v158 = v11;
                    }
                    CoTaskMemFree((LPVOID)lpString1);
                  }
                  SysFreeString(ppszName);
                  ++v39;
                }
                while ( v11 >= 0 );
LABEL_132:
                CoTaskMemFree(pv);
                if ( v11 >= 0 )
                {
LABEL_135:
                  value = 0;
                  if ( (*(int (__fastcall **)(struct IDesktopWallpaperPrivate *, DWORD *))(*(_QWORD *)v165 + 88LL))(
                         v165,
                         &value) >= 0 )
                  {
                    v158 = 0;
                    if ( (*(int (__fastcall **)(struct ITheme *, int *))(*(_QWORD *)v7 + 184LL))(v7, &v158) >= 0 )
                    {
                      v50 = v158;
                    }
                    else
                    {
                      v50 = 4;
                      v158 = 4;
                    }
                    v51 = value;
                    if ( value != v50 )
                    {
                      *v162 = 0;
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                      {
                        WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, v51, (unsigned int)v51, v50);
                        LODWORD(v51) = value;
                      }
                    }
                    v11 = PSPropertyBag_WriteDWORD((IPropertyBag *)ppv, L"Background_TILE", v51);
                    v158 = v11;
                  }
                }
LABEL_144:
                (*(void (__fastcall **)(struct IDesktopWallpaperPrivate *))(*(_QWORD *)v165 + 16LL))(v165);
                v6 = v162;
                goto LABEL_145;
              }
              v40 = 0;
              if ( IsDesktopSpotlightAllowedByPolicy() )
              {
                lpString1 = 0;
                v41 = (**(__int64 (__fastcall ***)(struct ITheme *, GUID *, LPCWCH *))v7)(
                        v7,
                        &GUID_6a0522b4_8e09_4aa8_985a_9e52d534977a,
                        &lpString1);
                if ( v41 >= 0 )
                {
                  value = 0;
                  if ( (*(int (__fastcall **)(LPCWCH, DWORD *))(*(_QWORD *)lpString1 + 32LL))(lpString1, &value) >= 0 )
                  {
                    v43 = CThemeManager2::_IsDesktopSpotlightEnabled(v42);
                    v40 = (value != 0) == v43;
                  }
                }
                else
                {
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x19D,
                    (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
                    (const char *)(unsigned int)v41,
                    bIgnoreCase[0]);
                }
                v44 = lpString1;
                if ( lpString1 )
                {
                  lpString1 = 0;
                  (*(void (__fastcall **)(LPCWCH))(*(_QWORD *)v44 + 16LL))(v44);
                }
              }
              if ( v29 || pcbData || v40 )
              {
LABEL_128:
                if ( v28 == 1 )
                {
                  CThemeManager2::_LoadPerMonitorData(this, v165);
                  CoTaskMemFree(pv);
                  (*(void (__fastcall **)(struct IDesktopWallpaperPrivate *, _QWORD, LPVOID *))(*(_QWORD *)v165 + 32LL))(
                    v165,
                    *((_QWORD *)this + 279),
                    &pv);
                }
                v11 = PSPropertyBag_WriteStr((IPropertyBag *)ppv, L"BackgroundSrc_Path", (LPCWSTR)pv);
                v158 = v11;
LABEL_131:
                v9 = 0;
                goto LABEL_132;
              }
              lpString1 = 0;
              (*(void (__fastcall **)(struct ITheme *, LPCWCH *))(*(_QWORD *)v7 + 168LL))(v7, &lpString1);
              if ( !lpString1 )
                goto LABEL_118;
              if ( CompareStringOrdinal((LPCWCH)pv, -1, lpString1, -1, 1) != 2 )
              {
                value = 0;
                if ( (*(int (__fastcall **)(struct IDesktopWallpaperPrivate *, DWORD *))(*(_QWORD *)v165 + 136LL))(
                       v165,
                       &value) < 0
                  || (value & 4) == 0 )
                {
                  *v38 = 0;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  {
                    WPP_SF_SS(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      16,
                      (unsigned int)WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids,
                      (_DWORD)pv,
                      (__int64)lpString1);
                  }
                  goto LABEL_127;
                }
                v45 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                {
                  v46 = 14;
LABEL_126:
                  WPP_SF_(v45[2], v46, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids);
                }
LABEL_127:
                SysFreeString((BSTR)lpString1);
                goto LABEL_128;
              }
              if ( lpString1 )
              {
                FileTime1 = 0;
                ppszName = 0;
                if ( (int)GetLastWriteTime((const unsigned __int16 *)pv, &FileTime1) < 0 )
                  goto LABEL_127;
                if ( (*(int (__fastcall **)(struct ITheme *, PWSTR *))(*(_QWORD *)v7 + 200LL))(v7, &ppszName) < 0 )
                  goto LABEL_127;
                if ( !CompareFileTime(&FileTime1, (const FILETIME *)&ppszName) )
                  goto LABEL_127;
                *v38 = 0;
                v47 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                {
                  goto LABEL_127;
                }
                v48 = 19;
                v49 = pv;
              }
              else
              {
LABEL_118:
                v49 = pv;
                if ( !*(_WORD *)pv )
                {
                  v45 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                  {
                    goto LABEL_127;
                  }
                  v46 = 18;
                  goto LABEL_126;
                }
                *v38 = 0;
                v47 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                {
                  goto LABEL_127;
                }
                v48 = 17;
              }
              WPP_SF_S(v47[2], v48, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids, v49);
              goto LABEL_127;
            }
            goto LABEL_36;
          }
        }
        else
        {
LABEL_31:
          UsingAPI = -2147467259;
        }
      }
      ((void (__fastcall *)(IUnknown *))v15->lpVtbl->Release)(v15);
    }
    else
    {
      UsingAPI = -2147024882;
    }
    v26 = *(_QWORD *)v7;
    v15 = (IUnknown *)v9;
    pv = v9;
    (*(void (__fastcall **)(struct ITheme *, LPVOID *))(v26 + 224))(v7, &pv);
    v25 = pv;
    goto LABEL_35;
  }
LABEL_145:
  v166 = (int)v9;
  if ( v11 < 0
    || !*v6
    || SHRestricted(REST_NODISPLAYAPPEARANCEPAGE) && !*((_BYTE *)this + 2145)
    || (*(int (__fastcall **)(struct ITheme *, int *))(*(_QWORD *)v7 + 464LL))(v7, &v166) >= 0 && v166 > 0
    || !IsCompositionActive() )
  {
    goto LABEL_182;
  }
  LODWORD(pv) = (_DWORD)v9;
  v52 = (*(int (__fastcall **)(struct ITheme *, LPVOID *))(*(_QWORD *)v7 + 104LL))(v7, &pv) >= 0;
  LODWORD(ppszName) = (_DWORD)v9;
  v53 = (*(__int64 (__fastcall **)(struct ITheme *, PWSTR *))(*(_QWORD *)v7 + 416LL))(v7, &ppszName);
  LODWORD(lpString1) = (_DWORD)v9;
  if ( (unsigned int)GetDwmColorizationColor((unsigned int *)&lpString1, v54) )
  {
    v62 = !v52;
    v6 = v162;
    if ( v62 )
      goto LABEL_182;
    *v162 = 0;
    v60 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_182;
    v61 = 22;
    goto LABEL_176;
  }
  v55 = v53 >= 0;
  v56 = (int)v9;
  value = (unsigned int)v9;
  pcbData = 4;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"Control Panel\\Desktop",
             L"AutoColorization",
             0x10000012u,
             &value,
             &FileTime1,
             &pcbData);
  v58 = ValueW;
  if ( ValueW )
  {
    if ( ValueW == 234 )
    {
      LOWORD(v58) = 13;
    }
    else if ( ValueW <= 0 )
    {
      goto LABEL_166;
    }
    goto LABEL_165;
  }
  LOWORD(v58) = 13;
  if ( value != 4 )
  {
    if ( pcbData == 4 )
    {
      v12 = 48;
      if ( LOWORD(FileTime1.dwLowDateTime) != 48 )
      {
        v12 = 49;
        if ( LOWORD(FileTime1.dwLowDateTime) != 49 )
          goto LABEL_165;
        v56 = 1;
      }
      v58 = (int)v9;
      goto LABEL_166;
    }
LABEL_165:
    v58 = (unsigned __int16)v58 | 0x80070000;
    goto LABEL_166;
  }
  if ( FileTime1.dwLowDateTime > 1 )
    goto LABEL_165;
  v58 = (int)v9;
  LOBYTE(v56) = FileTime1.dwLowDateTime == 1;
LABEL_166:
  v59 = (int)v9;
  if ( v58 >= 0 )
    v59 = v56;
  if ( !v55
    || (_DWORD)ppszName == v59
    && ((_DWORD)ppszName || !v52 || (((unsigned int)pv ^ (unsigned int)lpString1) & 0xFFFFFF) == 0) )
  {
    v6 = v162;
    goto LABEL_182;
  }
  v6 = v162;
  *v162 = 0;
  v60 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
    goto LABEL_182;
  v61 = 21;
LABEL_176:
  WPP_SF_(v60[2], v61, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids);
LABEL_182:
  if ( v11 < 0 )
    goto LABEL_404;
  if ( GetCurrentThemeName(pszThemeFileName, 260, pszColorBuff, 260, pszSizeBuff, 260) >= 0 )
  {
    v65 = -2147467259;
    ppszName = (PWSTR)v9;
    if ( (*(int (__fastcall **)(struct ITheme *, PWSTR *))(*(_QWORD *)v7 + 40LL))(v7, &ppszName) >= 0 )
    {
      lpString1 = (LPCWCH)v9;
      if ( (*(int (__fastcall **)(struct ITheme *, LPCWCH *))(*(_QWORD *)v7 + 56LL))(v7, &lpString1) >= 0 )
      {
        pv = v9;
        if ( (*(int (__fastcall **)(struct ITheme *, LPVOID *))(*(_QWORD *)v7 + 72LL))(v7, &pv) >= 0 )
        {
          if ( CompareStringOrdinal(pszThemeFileName, -1, ppszName, -1, 1) != 2
            || CompareStringOrdinal(pszColorBuff, -1, lpString1, -1, 1) != 2
            || CompareStringOrdinal(pszSizeBuff, -1, (LPCWCH)pv, -1, 1) != 2 )
          {
            *v6 = 0;
            v66 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids);
                v66 = WPP_GLOBAL_Control;
              }
              if ( v66 != &WPP_GLOBAL_Control )
              {
                if ( (*((_BYTE *)v66 + 28) & 8) != 0 )
                {
                  WPP_SF_SS(
                    v66[2],
                    24,
                    (unsigned int)WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids,
                    (unsigned int)pszThemeFileName,
                    (__int64)ppszName);
                  v66 = WPP_GLOBAL_Control;
                }
                if ( v66 != &WPP_GLOBAL_Control )
                {
                  if ( (*((_BYTE *)v66 + 28) & 8) != 0 )
                  {
                    WPP_SF_SS(
                      v66[2],
                      25,
                      (unsigned int)WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids,
                      (unsigned int)pszColorBuff,
                      (__int64)lpString1);
                    v66 = WPP_GLOBAL_Control;
                  }
                  if ( v66 != &WPP_GLOBAL_Control && (*((_BYTE *)v66 + 28) & 8) != 0 )
                    WPP_SF_SS(
                      v66[2],
                      26,
                      (unsigned int)WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids,
                      (unsigned int)pszSizeBuff,
                      (__int64)pv);
                }
              }
            }
          }
          v11 = PSPropertyBag_WriteStr((IPropertyBag *)ppv, L"VisualStyle_Path", pszThemeFileName);
          v158 = v11;
          if ( v11 >= 0 )
          {
            v11 = PSPropertyBag_WriteStr((IPropertyBag *)ppv, L"VisualStyle_Color", pszColorBuff);
            v158 = v11;
            if ( v11 >= 0 )
            {
              v11 = PSPropertyBag_WriteStr((IPropertyBag *)ppv, L"VisualStyle_Size", pszSizeBuff);
              v158 = v11;
              v65 = v11;
            }
          }
        }
        SysFreeString((BSTR)pv);
      }
      SysFreeString((BSTR)lpString1);
    }
    SysFreeString(ppszName);
    if ( v65 >= 0 && *v6 )
    {
      memset_0(propName, 0, sizeof(propName));
      if ( (int)SystemMetricsAll_Get((struct SYSTEMMETRICSALL *)propName) >= 0 )
      {
        memset_0(pszThemeFileName, 0, sizeof(pszThemeFileName));
        pv = v9;
        if ( (**(int (__fastcall ***)(struct ITheme *, GUID *, LPVOID *))v7)(
               v7,
               &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
               &pv) >= 0 )
        {
          v67 = SHPropertyBag_ReadByRef(pv, v12, pszThemeFileName);
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
          if ( v67 >= 0 )
          {
            LODWORD(v63) = (_DWORD)v9;
            while ( 1 )
            {
              v12 = (int)v63;
              if ( byte_18006E518[16 * (int)v63] )
              {
                if ( *(_DWORD *)&pszThemeFileName[2 * (int)v63 + 302] != *(_DWORD *)&propName[2 * (int)v63 + 302] )
                  break;
              }
              v63 = (WCHAR *)(unsigned int)((_DWORD)v63 + 1);
              if ( (unsigned int)v63 >= 0x1F )
                goto LABEL_220;
            }
            *v6 = 0;
            v63 = (WCHAR *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids);
          }
        }
      }
    }
LABEL_220:
    if ( v11 < 0 )
    {
LABEL_404:
      LOBYTE(v12) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemLightTheme>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_SystemLightTheme>::GetImpl'::`2'::impl,
        v12);
      if ( v11 < 0 )
        goto LABEL_411;
      goto LABEL_405;
    }
  }
  if ( *v6 && (int)GetSystemSoundScheme(propName, v12, pszColorBuff, v64) >= 0 )
  {
    v68 = 0;
    for ( i = (int)v9; ; ++i )
    {
      v63 = (WCHAR *)(&c_rgszInBoxSoundSchemes)[i];
      if ( !*v63 )
        goto LABEL_236;
      if ( CompareStringOrdinal(v63, -1, propName, -1, 1) == 2 )
        break;
    }
    pv = v9;
    SoundSchemeShortName = (*(__int64 (__fastcall **)(struct ITheme *, LPVOID *))(*(_QWORD *)v7 + 320LL))(v7, &pv);
    if ( SoundSchemeShortName >= 0 )
    {
      SoundSchemeShortName = GetSoundSchemeShortName((const unsigned __int16 *)pv, pszThemeFileName, v71);
      if ( SoundSchemeShortName >= 0 && IsInboxSoundScheme(pszThemeFileName) )
      {
        v72 = CompareStringOrdinal(pszColorBuff, -1, (LPCWCH)pv, -1, 1);
        *v6 = v72 == 2;
        if ( v72 != 2
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids);
        }
        v68 = 1;
      }
    }
    SysFreeString((BSTR)pv);
    v158 = v11;
    if ( SoundSchemeShortName >= 0 )
    {
LABEL_236:
      if ( *v6 && !v68 )
      {
        ppszName = (PWSTR)g_pfn_DPA_Create(16);
        if ( ppszName )
        {
          AllRegSoundEvents = GetAllRegSoundEvents(&ppszName);
          v74 = (struct _DPA *)ppszName;
          if ( AllRegSoundEvents > 0 )
          {
            v75 = (int)v9;
            v76 = v167;
            while ( 1 )
            {
              Ptr = (const OLECHAR *)g_pfn_DPA_GetPtr(v74, v75);
              v78 = Ptr;
              if ( Ptr )
                break;
LABEL_260:
              if ( ++v75 >= AllRegSoundEvents )
              {
                v11 = v158;
                goto LABEL_262;
              }
            }
            lpString1 = 0;
            v79 = *(_QWORD *)v76;
            v80 = SysAllocString(Ptr);
            v81 = v80;
            pv = v80;
            if ( !v80 )
              ATL::AtlThrowImpl(-2147024882);
            v82 = (*(__int64 (__fastcall **)(struct ITheme *, BSTR, __int64, LPCWCH *))(v79 + 336))(
                    v76,
                    v80,
                    0xFFFFFFFFLL,
                    &lpString1);
            SysFreeString(v81);
            if ( v82 < 0 )
              goto LABEL_259;
            if ( (int)StringCchPrintfW(pszSizeBuff, 0x104u, L"%s\\%s", v78, L".Current") < 0 )
              goto LABEL_253;
            LODWORD(pv) = 520;
            v83 = RegGetValueW(HKEY_CURRENT_USER, pszSizeBuff, 0, 2u, 0, pszThemeFileName, (LPDWORD)&pv);
            if ( v83 )
            {
              v84 = 0;
              pszThemeFileName[0] = 0;
              v85 = v83 < 0;
              if ( v83 <= 0 )
                goto LABEL_250;
              v83 = (unsigned __int16)v83 | 0x80070000;
            }
            else
            {
              v84 = pszThemeFileName[0];
            }
            v85 = v83 < 0;
LABEL_250:
            if ( !v85 )
            {
              if ( v84 )
              {
LABEL_255:
                if ( CompareStringOrdinal(pszThemeFileName, -1, lpString1, -1, 1) != 2 )
                {
                  *v162 = 0;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  {
                    WPP_SF_S(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      29,
                      WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids,
                      v78);
                  }
                }
                goto LABEL_259;
              }
              goto LABEL_254;
            }
LABEL_253:
            pszThemeFileName[0] = 0;
LABEL_254:
            if ( SysStringLen((BSTR)lpString1) )
              goto LABEL_255;
LABEL_259:
            SysFreeString((BSTR)lpString1);
            goto LABEL_260;
          }
LABEL_262:
          if ( v74 )
          {
            g_pfn_DPA_DestroyCallback(
              v74,
              CDPA_Base<_ITEMIDLIST_ABSOLUTE,CTContainer_PolicyCoTaskMem>::_StandardDestroyCB,
              0);
            DPA_Destroy(0);
          }
        }
      }
    }
  }
  v86 = 0;
  v88 = CThemeManager2::_CanThemeChangeDesktopIcons((CThemeManager2 *)v63);
  v163 = v88;
  for ( j = 0; ; ++j )
  {
    v90 = (const OLECHAR **)&_ImageBase[4 * j + 229128];
    v91 = *v90;
    if ( !**v90 )
      break;
    memset_0(pszSizeBuff, 0, 0x208u);
    v92 = StrChrW(v91, 0x3Au);
    v93 = v92;
    if ( v92 )
    {
      v94 = *v90;
      v95 = 2147483646;
      v96 = CharNextW(v92);
      v12 = 260;
      v97 = pszColorBuff;
      do
      {
        if ( !v95 )
          break;
        v98 = *v96;
        if ( !*v96 )
          break;
        ++v96;
        *v97++ = v98;
        --v95;
        --v12;
      }
      while ( v12 );
      v86 = -2147024774;
      if ( v12 )
        v86 = 0;
      v87 = (CThemeManager2 *)(v97 - 1);
      if ( v12 )
        v87 = (CThemeManager2 *)v97;
      *(_WORD *)v87 = 0;
      if ( v12 && CompareStringOrdinal(pszColorBuff, -1, L"DefaultValue", -1, 1) == 2 )
        pszColorBuff[0] = 0;
      v99 = v93 - v94;
      v88 = v163;
    }
    else
    {
      LODWORD(v99) = 0;
      pszColorBuff[0] = 0;
    }
    if ( v86 >= 0 )
    {
      v86 = StringCchPrintfW(
              pszThemeFileName,
              0x104u,
              L"%s\\%s",
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
              *v90);
      if ( v86 >= 0 )
      {
        v100 = 2LL * (unsigned int)v99 + 102;
        if ( v100 >= 0x208 )
          goto LABEL_426;
        *(WCHAR *)((char *)pszThemeFileName + v100) = 0;
        memset_0(propName, 0, 0x208u);
        LODWORD(pv) = 0;
        LODWORD(lpString1) = 520;
        pszSizeBuff[0] = 0;
        v101 = SHGetValueW(
                 HKEY_CURRENT_USER,
                 pszThemeFileName,
                 pszColorBuff,
                 (DWORD *)&pv,
                 propName,
                 (DWORD *)&lpString1);
        v102 = v101 < 0;
        if ( v101 > 0 )
          v102 = 1;
        if ( v102 )
        {
          v86 = StringCchPrintfW(pszThemeFileName, 0x104u, L"Software\\Classes\\%s", *v90);
          if ( v86 < 0 )
            goto LABEL_334;
          v108 = 2LL * (unsigned int)v99 + 34;
          if ( v108 >= 0x208 )
LABEL_426:
            _report_rangecheckfailure();
          *(WCHAR *)((char *)pszThemeFileName + v108) = 0;
          memset_0(propName, 0, 0x208u);
          LODWORD(pv) = 0;
          LODWORD(lpString1) = 520;
          pszSizeBuff[0] = 0;
          v109 = SHGetValueW(
                   HKEY_LOCAL_MACHINE,
                   pszThemeFileName,
                   pszColorBuff,
                   (DWORD *)&pv,
                   propName,
                   (DWORD *)&lpString1);
          v110 = v109 < 0;
          if ( v109 > 0 )
            v110 = 1;
          if ( v110 )
          {
            pszSizeBuff[0] = 0;
          }
          else if ( (unsigned int)((_DWORD)pv - 1) <= 1
                 && !(unsigned int)SHExpandEnvironmentStringsW(propName, pszSizeBuff, 260) )
          {
            v111 = 2147483646;
            v112 = propName;
            v105 = 260;
            v106 = pszSizeBuff;
            do
            {
              if ( !v111 )
                break;
              v113 = *v112;
              if ( !*v112 )
                break;
              ++v112;
              *v106++ = v113;
              --v111;
              --v105;
            }
            while ( v105 );
LABEL_304:
            v114 = v106 - 1;
            if ( v105 )
              v114 = v106;
            *v114 = 0;
          }
        }
        else if ( (unsigned int)((_DWORD)pv - 1) <= 1
               && !(unsigned int)SHExpandEnvironmentStringsW(propName, pszSizeBuff, 260) )
        {
          v103 = 2147483646;
          v104 = propName;
          v105 = 260;
          v106 = pszSizeBuff;
          do
          {
            if ( !v103 )
              break;
            v107 = *v104;
            if ( !*v104 )
              break;
            ++v104;
            *v106++ = v107;
            --v103;
            --v105;
          }
          while ( v105 );
          goto LABEL_304;
        }
        lpString1 = 0;
        if ( *v90 )
        {
          v115 = SysAllocString(*v90);
          ppszName = v115;
          if ( !v115 )
            ATL::AtlThrowImpl(-2147024882);
        }
        else
        {
          v115 = 0;
          ppszName = 0;
        }
        v116 = v167;
        v86 = (*(__int64 (__fastcall **)(struct ITheme *, WCHAR *, _QWORD, LPCWCH *))(*(_QWORD *)v167 + 360LL))(
                v167,
                v115,
                0,
                &lpString1);
        if ( v86 >= 0
          && SysStringLen((BSTR)lpString1)
          && v88
          && CompareStringOrdinal(pszSizeBuff, -1, lpString1, -1, 1) != 2 )
        {
          v117 = 2147483646;
          v118 = lpString1;
          v119 = 260;
          v120 = pszColorBuff;
          do
          {
            if ( !v117 )
              break;
            v121 = *v118;
            if ( !*v118 )
              break;
            ++v118;
            *v120++ = v121;
            --v117;
            --v119;
          }
          while ( v119 );
          v122 = v120 - 1;
          if ( v119 )
            v122 = v120;
          *v122 = 0;
          if ( v119 )
          {
            if ( (unsigned int)ConfirmFile(pszColorBuff, v119) == 3 )
            {
              pv = 0;
              v86 = (*(__int64 (__fastcall **)(struct ITheme *, WCHAR *, LPVOID *))(*(_QWORD *)v116 + 368LL))(
                      v116,
                      v115,
                      &pv);
              if ( v86 >= 0 )
              {
                if ( SysStringLen((BSTR)pv) )
                {
                  if ( CompareStringOrdinal(pszSizeBuff, -1, (LPCWCH)pv, -1, 1) != 2 )
                  {
                    *v162 = 0;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    {
                      WPP_SF_SS(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        30,
                        (unsigned int)WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids,
                        (unsigned int)pszSizeBuff,
                        (__int64)pv);
                    }
                  }
                }
              }
              SysFreeString((BSTR)pv);
            }
            else
            {
              *v162 = 0;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids);
              }
            }
          }
        }
        v11 = PSPropertyBag_WriteStr((IPropertyBag *)ppv, *v90, pszSizeBuff);
        v158 = v11;
        SysFreeString(v115);
        SysFreeString((BSTR)lpString1);
      }
    }
LABEL_334:
    if ( v11 < 0 )
    {
      LOBYTE(v12) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemLightTheme>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_SystemLightTheme>::GetImpl'::`2'::impl,
        v12);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      goto LABEL_418;
    }
  }
  v6 = v162;
  if ( !*v162 )
    goto LABEL_402;
  if ( CThemeManager2::_CanThemeChangeMouseCursors(v87) )
  {
    v123 = 0;
    value = 0;
    if ( aArrow[0] )
    {
      do
      {
        if ( !*v6 )
          goto LABEL_402;
        v124 = 8LL * v123 + 452928;
        memset_0(propName, 0, 0x208u);
        LODWORD(pv) = 0;
        LODWORD(lpString1) = 520;
        pszThemeFileName[0] = 0;
        v125 = SHGetValueW(
                 HKEY_LOCAL_MACHINE,
                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Control Panel\\Cursors\\Default",
                 *(LPCWSTR *)((char *)_ImageBase + v124),
                 (DWORD *)&pv,
                 propName,
                 (DWORD *)&lpString1);
        v126 = v125 < 0;
        if ( v125 > 0 )
          v126 = 1;
        if ( v126 )
        {
          pszThemeFileName[0] = 0;
        }
        else if ( (unsigned int)((_DWORD)pv - 1) <= 1
               && !(unsigned int)SHExpandEnvironmentStringsW(propName, pszThemeFileName, 260) )
        {
          v127 = 2147483646;
          v128 = propName;
          v129 = 260;
          v130 = pszThemeFileName;
          do
          {
            if ( !v127 )
              break;
            v131 = *v128;
            if ( !*v128 )
              break;
            ++v128;
            *v130++ = v131;
            --v127;
            --v129;
          }
          while ( v129 );
          v132 = v130 - 1;
          if ( v129 )
            v132 = v130;
          *v132 = 0;
        }
        v133 = pszThemeFileName;
        if ( (int)HrRegGetPath(
                    HKEY_CURRENT_USER,
                    L"Control Panel\\Cursors",
                    *(LPCWSTR *)((char *)_ImageBase + v124),
                    pszColorBuff,
                    bIgnoreCasea) >= 0 )
        {
          v134 = pszColorBuff;
          if ( !pszColorBuff[0] )
            v134 = pszThemeFileName;
          v133 = v134;
        }
        v135 = 0;
        lpString1 = 0;
        v136 = *(_WORD **)((char *)_ImageBase + v124);
        if ( v136 )
        {
          v137 = -1;
          do
            ++v137;
          while ( v136[v137] );
        }
        else
        {
          LODWORD(v137) = 0;
        }
        if ( !v136 )
          goto LABEL_379;
        v138 = SysStringLen(0);
        v139 = v138;
        v140 = v138 + v137;
        if ( v138 + (int)v137 >= v138 )
        {
          v142 = SysAllocStringLen(0, v140);
          if ( v142 )
          {
            if ( SysStringLen(0) )
            {
              v143 = memcpy_s_2(v142, 2LL * v140, 0, 2 * v139);
              if ( v143 )
              {
                if ( v143 == 12 )
                  goto LABEL_423;
                if ( v143 == 22 || v143 == 34 )
                  goto LABEL_428;
                if ( v143 != 80 )
                  goto LABEL_427;
              }
            }
            v144 = memcpy_s_2(&v142[v139], 2LL * (int)v137, v136, 2LL * (int)v137);
            if ( v144 )
            {
              if ( v144 == 12 )
LABEL_423:
                ATL::AtlThrowImpl(-2147024882);
              if ( v144 == 22 || v144 == 34 )
LABEL_428:
                ATL::AtlThrowImpl(-2147024809);
              if ( v144 != 80 )
LABEL_427:
                ATL::AtlThrowImpl(-2147467259);
            }
            v142[v140] = 0;
            SysFreeString(0);
            v135 = v142;
            lpString1 = v142;
            v123 = value;
LABEL_379:
            v141 = 0;
            goto LABEL_380;
          }
          v141 = -2147024882;
          v123 = value;
        }
        else
        {
          v141 = -2147024882;
        }
LABEL_380:
        if ( v141 < 0 )
        {
          v6 = v162;
        }
        else
        {
          v145 = pszThemeFileName;
          pv = 0;
          if ( (*(int (__fastcall **)(struct ITheme *, OLECHAR *, LPVOID *))(*(_QWORD *)v167 + 304LL))(v167, v135, &pv) >= 0
            && SysStringLen((BSTR)pv) )
          {
            v145 = (const WCHAR *)pv;
          }
          v146 = CompareStringOrdinal(v133, -1, v145, -1, 1);
          v6 = v162;
          *v162 = v146 == 2;
          if ( v146 != 2
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              32,
              (unsigned int)WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids,
              (_DWORD)v133,
              (__int64)v145);
          }
          SysFreeString((BSTR)pv);
        }
        SysFreeString(v135);
        value = ++v123;
      }
      while ( *off_18006E940[v123] );
    }
  }
  if ( !*v6 )
  {
LABEL_402:
    v7 = v167;
LABEL_403:
    v11 = v158;
    goto LABEL_404;
  }
  LODWORD(pv) = 0;
  v7 = v167;
  if ( (*(int (__fastcall **)(struct ITheme *, LPVOID *))(*(_QWORD *)v167 + 464LL))(v167, &pv) < 0 )
    goto LABEL_403;
  memset_0(propName, 0, 0x208u);
  LODWORD(lpString1) = 520;
  v147 = RegGetValueW(
           HKEY_CURRENT_USER,
           L"Control Panel\\Appearance",
           L"NewCurrent",
           2u,
           0,
           propName,
           (LPDWORD)&lpString1);
  v148 = v147 < 0;
  if ( v147 )
  {
    propName[0] = 0;
    v148 = v147 < 0;
    if ( v147 > 0 )
      v148 = 1;
  }
  if ( v148 )
    goto LABEL_403;
  v149 = HighContrastNumberFromSchemeName(propName);
  v150 = (unsigned int)pv;
  if ( v149 == (_DWORD)pv )
    goto LABEL_403;
  *v6 = 0;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
  {
    v11 = v158;
    goto LABEL_404;
  }
  WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, v150, v149, v150);
  LOBYTE(v151) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemLightTheme>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_SystemLightTheme>::GetImpl'::`2'::impl,
    v151);
LABEL_405:
  if ( *v6 )
  {
    pcbData = 0;
    (*(void (__fastcall **)(struct ITheme *, DWORD *))(*(_QWORD *)v7 + 136LL))(v7, &pcbData);
    if ( pcbData != ((unsigned __int8)ShouldAppsUseDarkMode() ^ 1)
      || *v6
      && ((*(void (__fastcall **)(struct ITheme *, DWORD *))(*(_QWORD *)v7 + 152LL))(v7, &pcbData),
          pcbData != ((unsigned __int8)ShouldSystemUseDarkMode() ^ 1)) )
    {
      *v6 = 0;
    }
  }
  v11 = (**(__int64 (__fastcall ***)(void *, GUID *, struct IPropertyBag **))ppv)(
          ppv,
          &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
          v171);
LABEL_411:
  (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v11 < 0 || !*v170 )
    goto LABEL_418;
  if ( !*v6 )
  {
    *v170 = 0;
    goto LABEL_418;
  }
  *v6 = 0;
  v152 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)v11;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids);
LABEL_418:
    v152 = WPP_GLOBAL_Control;
  }
  if ( v152 != &WPP_GLOBAL_Control && (*((_BYTE *)v152 + 28) & 8) != 0 )
    WPP_SF_ddD(v152[2], v162, v10, *v162, *v170, v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180010b20  push    rbp
0x180010b22  push    rbx
0x180010b23  push    rsi
0x180010b24  push    rdi
0x180010b25  push    r12
0x180010b27  push    r13
0x180010b29  push    r14
0x180010b2b  push    r15
0x180010b2d  lea     rbp, [rsp-9D8h]
0x180010b35  sub     rsp, 0AD8h
0x180010b3c  mov     rax, cs:__security_cookie
0x180010b43  xor     rax, rsp
0x180010b46  mov     [rbp+0A10h+var_50], rax
0x180010b4d  mov     rbx, r9
0x180010b50  mov     [rbp+0A10h+var_A68], rbx
0x180010b54  mov     rsi, r8
0x180010b57  mov     [rsp+0B10h+var_AA8], r8
0x180010b5c  mov     r12, rdx
0x180010b5f  mov     [rbp+0A10h+var_A80], rdx
0x180010b63  mov     r13, rcx
0x180010b66  mov     rdi, [rbp+0A10h+arg_20]
0x180010b6d  mov     [rbp+0A10h+var_A60], rdi
0x180010b71  lea     rax, WPP_GLOBAL_Control
0x180010b78  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b7f  cmp     rcx, rax
0x180010b82  jz      short loc_180010B9F
0x180010b84  test    byte ptr [rcx+1Ch], 8
0x180010b88  jz      short loc_180010B9F
0x180010b8a  mov     edx, 0Ah
0x180010b8f  lea     r8, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids
0x180010b96  mov     rcx, [rcx+10h]
0x180010b9a  call    WPP_SF_
0x180010b9f  mov     byte ptr [rsi], 1
0x180010ba2  mov     byte ptr [rbx], 0
0x180010ba5  xor     r14d, r14d
0x180010ba8  mov     [rdi], r14
0x180010bab  mov     [rsp+0B10h+ppv], r14
0x180010bb0  lea     rdx, [rsp+0B10h+ppv]; ppv
0x180010bb5  lea     rcx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x180010bbc  call    cs:__imp_PSCreateMemoryPropertyStore
0x180010bc2  mov     r15d, eax
0x180010bc5  mov     [rsp+0B10h+var_AC0], eax
0x180010bc9  test    eax, eax
0x180010bcb  js      loc_180012AB8
0x180010bd1  mov     [rbp+0A10h+var_A90], r14
0x180010bd5  lea     rax, [rbp+0A10h+var_A90]
0x180010bd9  mov     qword ptr [rsp+0B10h+bIgnoreCase], rax; int
0x180010bde  lea     r9, _GUID_c182461f_dfac_4375_ab6e_4cc45aa7f9cc; riid
0x180010be5  xor     edx, edx; pUnkOuter
0x180010be7  mov     r8d, 4; dwClsContext
0x180010bed  lea     rcx, CLSID_DesktopWallpaper; rclsid
0x180010bf4  call    cs:__imp_CoCreateInstance
0x180010bfa  test    eax, eax
0x180010bfc  js      loc_180011651
0x180010c02  call    cs:__imp_GetProcessHeap
0x180010c08  mov     rcx, rax; hHeap
0x180010c0b  mov     edx, 8; dwFlags
0x180010c10  mov     r8d, 48h ; 'H'; dwBytes
0x180010c16  call    cs:__imp_HeapAlloc
0x180010c1c  mov     rdi, rax
0x180010c1f  mov     [rsp+0B10h+pv], rax
0x180010c24  test    rax, rax
0x180010c27  jz      loc_180010E38
0x180010c2d  lea     rax, ??_7CSlideshowSettingsAdapter@@6BISlideshowSettings@@@; const CSlideshowSettingsAdapter::`vftable'{for `ISlideshowSettings'}
0x180010c34  mov     [rdi], rax
0x180010c37  lea     rax, ??_7CSlideshowSettingsAdapter@@6BISlideshowSettingsInternal@@@; const CSlideshowSettingsAdapter::`vftable'{for `ISlideshowSettingsInternal'}
0x180010c3e  mov     [rdi+8], rax
0x180010c42  mov     dword ptr [rdi+10h], 1
0x180010c49  mov     [rdi+18h], r14
0x180010c4d  lea     rcx, [rdi+20h]; this
0x180010c51  mov     qword ptr [rcx], 1B7740h
0x180010c58  mov     dword ptr [rcx+8], 3E8h
0x180010c5f  mov     [rcx+10h], r14
0x180010c63  mov     [rcx+18h], r14
0x180010c67  mov     [rcx+20h], r14d
0x180010c6b  call    ?LoadUsingAPI@CSlideshowSettings@@QEAAJXZ; CSlideshowSettings::LoadUsingAPI(void)
0x180010c70  mov     esi, eax
0x180010c72  test    eax, eax
0x180010c74  js      loc_180010E27
0x180010c7a  test    byte ptr [rdi+38h], 4
0x180010c7e  jz      loc_180010E22
0x180010c84  mov     rax, [rdi+30h]
0x180010c88  test    rax, rax
0x180010c8b  jz      short loc_180010C90
0x180010c8d  lock inc dword ptr [rax]
0x180010c90  mov     r14, [rdi+30h]
0x180010c94  test    r14, r14
0x180010c97  jz      loc_180010E22
0x180010c9d  xor     esi, esi
0x180010c9f  mov     rax, [r14+10h]
0x180010ca3  test    rax, rax
0x180010ca6  jz      short loc_180010CBA
0x180010ca8  mov     rax, [rax]
0x180010cab  test    rax, rax
0x180010cae  jz      short loc_180010CB2
0x180010cb0  mov     eax, [rax]
0x180010cb2  test    eax, eax
0x180010cb4  jnz     loc_180010DBE
0x180010cba  mov     [rsp+0B10h+ppszName], rsi
0x180010cbf  mov     rcx, [r14+8]; pidl
0x180010cc3  call    cs:__imp_ILClone
0x180010cc9  mov     r15, rax
0x180010ccc  test    rax, rax
0x180010ccf  jz      loc_180010DB9
0x180010cd5  lea     r8, [rsp+0B10h+ppszName]; ppszName
0x180010cda  mov     edx, 80058000h; sigdnName
0x180010cdf  mov     rcx, rax; pidl
0x180010ce2  call    cs:__imp_SHGetNameFromIDList
0x180010ce8  mov     ebx, eax
0x180010cea  mov     rcx, r15; pidl
0x180010ced  call    cs:__imp_ILFree
0x180010cf3  test    ebx, ebx
0x180010cf5  js      loc_180010DB9
0x180010cfb  mov     rax, [rsp+0B10h+ppszName]
0x180010d00  mov     qword ptr [rbp+0A10h+FileTime1.dwLowDateTime], rax
0x180010d04  xor     ebx, ebx
0x180010d06  mov     [rbp+0A10h+var_A70], rbx
0x180010d0a  mov     [rsp+0B10h+pv], rbx
0x180010d0f  lea     rax, [rsp+0B10h+pv]
0x180010d14  mov     qword ptr [rsp+0B10h+bIgnoreCase], rax; ppv
0x180010d19  lea     r9, _GUID_5357e238_fb12_4aca_a930_cab7832b84bf; riid
0x180010d20  xor     edx, edx; pUnkOuter
0x180010d22  mov     r8d, 1; dwClsContext
0x180010d28  lea     rcx, CLSID_XFeedsManager; rclsid
0x180010d2f  call    cs:__imp_CoCreateInstance
0x180010d35  mov     esi, eax
0x180010d37  test    eax, eax
0x180010d39  js      short loc_180010DAE
0x180010d3b  mov     [rsp+0B10h+lpString1], rbx
0x180010d40  mov     rcx, [rsp+0B10h+pv]
0x180010d45  mov     rax, [rcx]
0x180010d48  lea     r8, [rsp+0B10h+lpString1]
0x180010d4d  lea     rdx, _GUID_4c963678_3a51_4b88_8531_98b90b6508f2
0x180010d54  mov     rax, [rax+18h]
0x180010d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d5d  mov     esi, eax
0x180010d5f  test    eax, eax
0x180010d61  js      short loc_180010D9D
0x180010d63  lea     r9, [rbp+0A10h+FileTime1]; void *
0x180010d67  mov     rcx, [rsp+0B10h+lpString1]; struct IXFeedFolder *
0x180010d6c  call    ?EnumerateRSSFeedsInFolder@@YAHPEAUIXFeedFolder@@P6AH0PEAX@ZP6AHPEAUIXFeed@@1@Z1@Z; EnumerateRSSFeedsInFolder(IXFeedFolder *,int (*)(IXFeedFolder *,void *),int (*)(IXFeed *,void *),void *)
0x180010d71  mov     rcx, [rsp+0B10h+lpString1]
0x180010d76  mov     rax, [rcx]
0x180010d79  mov     rax, [rax+10h]
0x180010d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d82  mov     rcx, [rsp+0B10h+pv]
0x180010d87  mov     rax, [rcx]
0x180010d8a  mov     rax, [rax+10h]
0x180010d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d93  mov     rax, [rbp+0A10h+var_A70]
0x180010d97  mov     [rdi+18h], rax
0x180010d9b  jmp     short loc_180010DAE
0x180010d9d  mov     rcx, [rsp+0B10h+pv]
0x180010da2  mov     rax, [rcx]
0x180010da5  mov     rax, [rax+10h]
0x180010da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010dae  mov     rcx, [rsp+0B10h+ppszName]; pv
0x180010db3  call    cs:__imp_CoTaskMemFree
0x180010db9  mov     r15d, [rsp+0B10h+var_AC0]
0x180010dbe  mov     rcx, r14; this
0x180010dc1  call    ?Release@CFileSource@@QEAAKXZ; CFileSource::Release(void)
0x180010dc6  xor     r14d, r14d
0x180010dc9  test    esi, esi
0x180010dcb  js      short loc_180010E27
0x180010dcd  mov     [rsp+0B10h+pv], r14
0x180010dd2  mov     rax, [r12]
0x180010dd6  lea     rdx, [rsp+0B10h+pv]
0x180010ddb  mov     rcx, r12
0x180010dde  mov     rax, [rax+0E0h]
0x180010de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010dea  mov     rbx, [rsp+0B10h+pv]
0x180010def  test    rdi, rdi
0x180010df2  jz      short loc_180010E1D
0x180010df4  test    rbx, rbx
0x180010df7  jz      short loc_180010E18
0x180010df9  mov     rax, [rdi]
0x180010dfc  mov     rdx, rbx
0x180010dff  mov     rcx, rdi
0x180010e02  mov     rax, [rax+20h]
0x180010e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e0b  mov     esi, r14d
0x180010e0e  test    eax, eax
0x180010e10  jnz     loc_180010EAF
0x180010e16  jmp     short loc_180010E6B
0x180010e18  mov     esi, r14d
0x180010e1b  jmp     short loc_180010E6B
0x180010e1d  mov     esi, r14d
0x180010e20  jmp     short loc_180010E62
0x180010e22  mov     esi, 80004005h
0x180010e27  mov     rax, [rdi]
0x180010e2a  mov     rcx, rdi
0x180010e2d  mov     rax, [rax+10h]
0x180010e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e36  jmp     short loc_180010E3D
0x180010e38  mov     esi, 8007000Eh
0x180010e3d  mov     rax, [r12]
0x180010e41  mov     rdi, r14
0x180010e44  mov     [rsp+0B10h+pv], r14
0x180010e49  lea     rdx, [rsp+0B10h+pv]
0x180010e4e  mov     rcx, r12
0x180010e51  mov     rax, [rax+0E0h]
0x180010e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e5d  mov     rbx, [rsp+0B10h+pv]
0x180010e62  test    rbx, rbx
0x180010e65  jz      loc_180010EEE
0x180010e6b  call    ?s_PolicyAllowsSlideshow@CSlideshowSettings@@SAJXZ; CSlideshowSettings::s_PolicyAllowsSlideshow(void)
0x180010e70  test    eax, eax
0x180010e72  jnz     short loc_180010EAA
0x180010e74  mov     rax, [rsp+0B10h+var_AA8]
0x180010e79  mov     byte ptr [rax], 0
0x180010e7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e83  lea     rax, WPP_GLOBAL_Control
0x180010e8a  cmp     rcx, rax
0x180010e8d  jz      short loc_180010EAA
0x180010e8f  test    byte ptr [rcx+1Ch], 8
0x180010e93  jz      short loc_180010EAA
0x180010e95  mov     edx, 0Bh
0x180010e9a  lea     r8, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids
0x180010ea1  mov     rcx, [rcx+10h]
0x180010ea5  call    WPP_SF_
0x180010eaa  test    rdi, rdi
0x180010ead  jz      short loc_180010EDA
0x180010eaf  mov     r8, rdi; punk
0x180010eb2  lea     rdx, aSlideshow; "Slideshow"
0x180010eb9  mov     rcx, [rsp+0B10h+ppv]; propBag
0x180010ebe  call    cs:__imp_PSPropertyBag_WriteUnknown
0x180010ec4  mov     r15d, eax
0x180010ec7  mov     [rsp+0B10h+var_AC0], eax
0x180010ecb  mov     rax, [rdi]
0x180010ece  mov     rcx, rdi
0x180010ed1  mov     rax, [rax+10h]
0x180010ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010eda  test    rbx, rbx
0x180010edd  jz      short loc_180010EEE
0x180010edf  mov     rax, [rbx]
0x180010ee2  mov     rcx, rbx
0x180010ee5  mov     rax, [rax+10h]
0x180010ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010eee  test    r15d, r15d
0x180010ef1  js      loc_18001163C
0x180010ef7  mov     [rsp+0B10h+var_AB8], r14d
0x180010efc  mov     rax, [r12]
0x180010f00  lea     rdx, [rsp+0B10h+var_AB8]
0x180010f05  mov     rcx, r12
0x180010f08  mov     rax, [rax+1B0h]
0x180010f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f14  test    eax, eax
0x180010f16  jns     short loc_180010F1D
0x180010f18  mov     [rsp+0B10h+var_AB8], r14d
0x180010f1d  mov     [rsp+0B10h+pv], r14
0x180010f22  mov     rcx, [rbp+0A10h+var_A90]
0x180010f26  mov     rax, [rcx]
0x180010f29  lea     r8, [rsp+0B10h+pv]
0x180010f2e  xor     edx, edx
0x180010f30  mov     rax, [rax+20h]
0x180010f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f39  mov     r14d, eax
0x180010f3c  test    eax, eax
0x180010f3e  js      loc_180011589
0x180010f44  shr     esi, 1Fh
0x180010f47  xor     sil, 1
0x180010f4b  cmp     eax, 1
0x180010f4e  jnz     short loc_180010F5C
0x180010f50  test    sil, sil
0x180010f53  jnz     short loc_180010F5C
0x180010f55  mov     ebx, eax
0x180010f57  xor     r15d, r15d
0x180010f5a  jmp     short loc_180010F62
0x180010f5c  xor     r15d, r15d
0x180010f5f  mov     ebx, r15d
0x180010f62  call    ?IsDesktopSpotlightAllowedByPolicy@@YA_NXZ; IsDesktopSpotlightAllowedByPolicy(void)
0x180010f67  test    al, al
0x180010f69  jz      loc_18001102E
0x180010f6f  mov     [rsp+0B10h+lpString1], r15
0x180010f74  mov     rax, [r12]
0x180010f78  lea     r8, [rsp+0B10h+lpString1]
0x180010f7d  lea     rdx, _GUID_6a0522b4_8e09_4aa8_985a_9e52d534977a
0x180010f84  mov     rcx, r12
0x180010f87  mov     rax, [rax]
0x180010f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f8f  mov     rcx, [rbp+0A18h]; this
0x180010f96  test    eax, eax
0x180010f98  jns     short loc_180010FB0
0x180010f9a  mov     r9d, eax; char *
0x180010f9d  lea     r8, aShellThemesThe_5; "shell\\themes\\themeui\\themeapply.cpp"
0x180010fa4  mov     edx, 14Ch; void *
0x180010fa9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010fae  jmp     short loc_180011012
0x180010fb0  mov     [rsp+0B10h+value], r15d
0x180010fb5  mov     rcx, [rsp+0B10h+lpString1]
0x180010fba  mov     rax, [rcx]
0x180010fbd  lea     rdx, [rsp+0B10h+value]
0x180010fc2  mov     rax, [rax+20h]
0x180010fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fcb  test    eax, eax
0x180010fcd  js      short loc_180011012
0x180010fcf  call    ?_IsDesktopSpotlightEnabled@CThemeManager2@@AEAA_NXZ; CThemeManager2::_IsDesktopSpotlightEnabled(void)
0x180010fd4  movzx   edi, al
0x180010fd7  mov     r8d, edi; value
0x180010fda  lea     rdx, aWindowsspotlig; "WindowsSpotlight"
  ... truncated ...
```
