# TempFilesToZip(HWND__ *,ushort const *,ushort const *,ushort const *,ushort *,uint,int)

- ea: `0x18000b430`
- end: `0x18000bfd7`
- name: `?TempFilesToZip@@YAJPEAUHWND__@@PEBG11PEAGIH@Z`
- size: `2983`
- prototype: `__int64 __fastcall(HWND, unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000c380`

## callees

- `0x18000b430`
- `0x18000f820`
- `0x180010c30`
- `0x180013db8`
- `0x1800143cc`
- `0x18001ceb4`
- `0x180022ee8`
- `0x180023164`
- `0x180024a24`
- `0x180027764`
- `0x1800277d4`
- `0x180028928`
- `0x180029994`
- `0x18002c184`
- `0x180032480`
- `0x1800324b8`
- `0x180036f50`
- `0x180037958`
- `0x1800390fd`
- `0x18003cfac`
- `0x18003edd4`
- `0x18003ef3c`
- `0x1800408fc`
- `0x1800409a8`
- `0x180040a68`
- `0x180040c08`
- `0x18004839c`
- `0x18006e9a0`
- `0x180071010`

## import_xrefs

- `SHELL32!SHFileOperationW` at `0x18000bef8`
- `SHELL32!SHFileOperationW` at `0x18000bef8`
- `SHLWAPI!PathStripToRootW` at `0x18000b56c`
- `SHLWAPI!PathStripToRootW` at `0x18000b56c`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18000b510`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18000b510`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x18000b5a6`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x18000bc46`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x18000b5a6`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x18000bc46`
- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x18000b8e5`
- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x18000ba4c`
- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x18000b8e5`
- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x18000ba4c`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18000b780`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18000b853`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18000b9aa`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18000bcdd`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18000bd37`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18000bd80`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18000bdb4`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18000bf3b`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18000b780`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18000b853`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18000b9aa`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18000bcdd`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18000bd37`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18000bd80`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18000bdb4`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18000bf3b`
- `SHLWAPI!__imp_PathFileExistsAndAttributesW` at `0x18000b49d`
- `SHLWAPI!__imp_PathFileExistsAndAttributesW` at `0x18000b49d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000bea4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000bea4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bf89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bf89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b70b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b810`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b9fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ba0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bfcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b70b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b810`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b9fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ba0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bfcc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000be69`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000be69`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000bb08`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000bb08`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000bbc7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000bbc7`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18000b951`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18000b951`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18000b579`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18000b579`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18000b526`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18000b526`
- `KERNEL32!lstrcmpW` at `0x18000bb57`
- `KERNEL32!lstrcmpW` at `0x18000bb57`
- `KERNEL32!lstrlenW` at `0x18000bb40`
- `KERNEL32!lstrlenW` at `0x18000bc52`
- `KERNEL32!lstrlenW` at `0x18000bce6`
- `KERNEL32!lstrlenW` at `0x18000bb40`
- `KERNEL32!lstrlenW` at `0x18000bc52`
- `KERNEL32!lstrlenW` at `0x18000bce6`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18000bf41`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18000bf41`

## pseudocode

```c
__int64 __fastcall TempFilesToZip(
        HWND a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned int a7)
{
  int ProgressDialog; // ebx
  const unsigned __int16 *v11; // rdi
  unsigned __int64 v12; // r13
  __int64 v13; // r14
  bool v14; // zf
  __int64 v15; // rax
  unsigned int v16; // r14d
  int v17; // eax
  __int64 v18; // rcx
  unsigned __int64 FileSize; // rax
  int v21; // ecx
  char IsEnabled; // al
  __int64 v23; // rcx
  __int64 v24; // r8
  void *v25; // rcx
  unsigned __int16 *v26; // r13
  const WCHAR *i; // rbx
  int v28; // edi
  __int64 v29; // rdi
  unsigned int v30; // r11d
  int v31; // eax
  int v32; // edx
  char v33; // al
  __int64 v34; // rcx
  HWND v35; // rdx
  __int64 v36; // r8
  char v37; // al
  __int64 v38; // rcx
  char v39; // al
  __int64 v40; // rcx
  HWND v41; // rdx
  __int64 v42; // r9
  __int64 v43; // r8
  char v44; // al
  __int64 v45; // rcx
  __int64 v46; // rcx
  const unsigned __int16 *v47; // r9
  int v48; // eax
  UINT fuStyle; // [rsp+20h] [rbp-E0h]
  int fuStylea; // [rsp+20h] [rbp-E0h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-D8h]
  unsigned int v52; // [rsp+38h] [rbp-C8h]
  unsigned int v53; // [rsp+50h] [rbp-B0h]
  bool v54; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v55; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int16 *v56; // [rsp+68h] [rbp-98h] BYREF
  int v57; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v58; // [rsp+78h] [rbp-88h]
  _BYTE Src[4]; // [rsp+80h] [rbp-80h] BYREF
  int v60; // [rsp+84h] [rbp-7Ch]
  _BYTE *v61; // [rsp+88h] [rbp-78h]
  __int64 (__fastcall *v62)(int, int, int, int, __int64); // [rsp+90h] [rbp-70h]
  _BYTE *v63; // [rsp+98h] [rbp-68h]
  __int64 (__fastcall *v64)(int, int, int, int, __int64); // [rsp+A0h] [rbp-60h]
  _BYTE *v65; // [rsp+A8h] [rbp-58h]
  int v66; // [rsp+B0h] [rbp-50h]
  int v67; // [rsp+B4h] [rbp-4Ch]
  _BYTE *v68; // [rsp+B8h] [rbp-48h]
  __int64 v69; // [rsp+C8h] [rbp-38h]
  __int64 (__fastcall *v70)(PSTR, unsigned __int16 *); // [rsp+D0h] [rbp-30h]
  HANDLE hObject; // [rsp+E4h] [rbp-1Ch]
  int v72; // [rsp+ECh] [rbp-14h]
  HLOCAL hMem; // [rsp+F0h] [rbp-10h] BYREF
  HWND phwnd; // [rsp+920h] [rbp+820h] BYREF
  IUnknown *punk; // [rsp+928h] [rbp+828h] BYREF
  _SHFILEOPSTRUCTW FileOp; // [rsp+930h] [rbp+830h] BYREF
  _BYTE v77[8]; // [rsp+970h] [rbp+870h] BYREF
  IUnknown *v78; // [rsp+978h] [rbp+878h]
  CHAR *v79; // [rsp+988h] [rbp+888h]
  unsigned __int64 v80; // [rsp+990h] [rbp+890h]
  unsigned int v81; // [rsp+998h] [rbp+898h]
  LPVOID pv; // [rsp+BB0h] [rbp+AB0h] BYREF
  struct IShellItemArray *v83; // [rsp+BB8h] [rbp+AB8h] BYREF
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+BC0h] [rbp+AC0h] BYREF
  _ULARGE_INTEGER FreeBytesAvailableToCaller; // [rsp+BC8h] [rbp+AC8h] BYREF
  unsigned __int16 v86[264]; // [rsp+BD0h] [rbp+AD0h] BYREF
  unsigned __int16 v87[2]; // [rsp+DE0h] [rbp+CE0h] BYREF
  _BYTE v88[524]; // [rsp+DE4h] [rbp+CE4h] BYREF
  WCHAR pwszSrc[264]; // [rsp+FF0h] [rbp+EF0h] BYREF
  CHAR pszDst[272]; // [rsp+1200h] [rbp+1100h] BYREF
  WCHAR pszPath[264]; // [rsp+1310h] [rbp+1210h] BYREF
  WCHAR Buffer[264]; // [rsp+1520h] [rbp+1420h] BYREF
  _BYTE v93[2096]; // [rsp+1730h] [rbp+1630h] BYREF
  _BYTE v94[2096]; // [rsp+1F60h] [rbp+1E60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+27E8h] [rbp+26E8h]

  v58 = a4;
  punk = 0;
  ProgressDialog = CreateProgressDialog((struct IProgressDialog **)&punk);
  if ( ProgressDialog < 0 )
    return (unsigned int)ProgressDialog;
  v57 = PathFileExistsAndAttributesW(a2, 0);
  ProgressDialog = ((__int64 (__fastcall *)(IUnknown *, HWND, _QWORD, __int64, _QWORD))punk->lpVtbl[1].QueryInterface)(
                     punk,
                     a1,
                     0,
                     2,
                     0);
  if ( ProgressDialog < 0 )
  {
    ((void (__fastcall *)(IUnknown *, _QWORD, _QWORD))punk->lpVtbl[2].QueryInterface)(punk, 0, 0);
    ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
    return (unsigned int)ProgressDialog;
  }
  phwnd = 0;
  v11 = a3;
  IUnknown_GetWindow(punk, &phwnd);
  GetTempPathW(0x104u, Buffer);
  SetTitle((struct IProgressDialog *)punk, 0x276Bu);
  memcpy_0(Src, qword_1800737C0, 0x89Cu);
  StringCchCopyW(pszPath, 0x104u, a2);
  PathStripToRootW(pszPath);
  TotalNumberOfBytes.LowPart = GetDriveTypeW(pszPath);
  memset_0(v77, 0, 0x238u);
  SHUnicodeToAnsi(a3, pszDst, 260);
  *(_DWORD *)v86 = 0;
  v12 = 0;
  v78 = punk;
  v54 = 0;
  v55 = 0;
  v79 = pszDst;
  memset_0(&v86[2], 0, 0x204u);
  *(_DWORD *)v87 = 0;
  memset_0(v88, 0, 0x204u);
  v56 = 0;
  v13 = -1;
  do
    ++v13;
  while ( a3[v13] );
  while ( *v11 )
  {
    v14 = a3[v13 + 1] == 0;
    LODWORD(v83) = 0;
    pv = 0;
    ProgressDialog = GetDropFileCountSizeAndEncryption(
                       (struct IProgressDialog *)punk,
                       v11,
                       v14,
                       (unsigned int *)&v83,
                       (union _ULARGE_INTEGER *)&pv,
                       &v54,
                       v86,
                       v52,
                       &v55,
                       v87,
                       v53,
                       &v56);
    if ( ProgressDialog < 0 )
      break;
    v81 += (unsigned int)v83;
    v12 += (unsigned __int64)pv;
    v15 = -1;
    do
      ++v15;
    while ( v11[v15] );
    v11 += v15 + 1;
    LODWORD(v80) = v80 + 1;
  }
  v16 = 0;
  if ( a5 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pv,
      a5,
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v56,
      &pv);
    if ( pv )
      CoTaskMemFree(pv);
    ProgressDialog = StringCchCopyW(v87, 0x104u, a3);
  }
  if ( ProgressDialog < 0 )
    goto LABEL_25;
  if ( v55 == 1 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
      v17 = MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short___(
              g_hmodThisDll,
              phwnd,
              (LPCWSTR)0x2968,
              (LPCWSTR)0x2747,
              0x34u,
              (__int64)v86);
    else
      v17 = ShellMessageBoxW(g_hmodThisDll, phwnd, (LPCWSTR)0x2968, (LPCWSTR)0x2747, 0x34u);
LABEL_23:
    if ( v17 == 7 )
    {
      ProgressDialog = -2147023673;
LABEL_25:
      ((void (__fastcall *)(IUnknown *, _QWORD, _QWORD))punk->lpVtbl[2].QueryInterface)(punk, 0, 0);
      ((void (__fastcall *)(IUnknown *))punk->lpVtbl[1].AddRef)(punk);
LABEL_26:
      ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
      if ( v56 )
        CoTaskMemFree(v56);
      return (unsigned int)ProgressDialog;
    }
    goto LABEL_31;
  }
  if ( v55 <= 1 )
    goto LABEL_31;
  v14 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) == 0;
  dwFlagsAndAttributes[0] = v55;
  if ( !v14 )
  {
    v17 = MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_int_(v18, phwnd);
    goto LABEL_23;
  }
  if ( ShellMessageBoxW(g_hmodThisDll, phwnd, (LPCWSTR)0x2969, (LPCWSTR)0x2747, 0x34u, *(_QWORD *)dwFlagsAndAttributes) == 7 )
  {
    ProgressDialog = -2147023673;
    goto LABEL_25;
  }
LABEL_31:
  v83 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v83,
    0);
  ProgressDialog = EvaluateZipEdpPolicyIfNeeded(phwnd, a2, v87, v81, a7, v56, (unsigned __int16 **)&v83);
  if ( ProgressDialog < 0 )
  {
    ((void (__fastcall *)(IUnknown *, _QWORD, _QWORD))punk->lpVtbl[2].QueryInterface)(punk, 0, 0);
    ((void (__fastcall *)(IUnknown *))punk->lpVtbl[1].AddRef)(punk);
LABEL_106:
    if ( v83 )
      CoTaskMemFree(v83);
    goto LABEL_26;
  }
  v67 = 1;
  SHUnicodeToAnsiCP(65001, Buffer, v93, 2084);
  v68 = v93;
  FileSize = _GetFileSize(a2);
  v21 = v66;
  if ( v12 + FileSize <= 0x7FFFFFFF )
    v21 = 5;
  v66 = v21;
  if ( TotalNumberOfBytes.LowPart != 2 )
    goto LABEL_48;
  FreeBytesAvailableToCaller.QuadPart = 0;
  TotalNumberOfBytes.QuadPart = 0;
  pv = 0;
  if ( !GetDiskFreeSpaceExW(pszPath, &FreeBytesAvailableToCaller, &TotalNumberOfBytes, (PULARGE_INTEGER)&pv) )
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl);
    v24 = 10199;
    goto LABEL_39;
  }
  if ( (unsigned __int64)pv >= v12 )
  {
LABEL_48:
    if ( a6 == 205 || a6 == 206 )
      v60 = 4;
    SHUnicodeToAnsiCP(65001, a2, v94, 2084);
    v69 = 1;
    v61 = v94;
    hMem = 0;
    v62 = DropInMajorCallback;
    pv = 0;
    v63 = v77;
    v64 = DropInMinorCallback;
    v65 = v77;
    v70 = DropInRenCallback;
    v72 = v80;
    ProgressDialog = ULongLongMult((unsigned int)v80, 0x524u, (unsigned __int64 *)&pv);
    if ( ProgressDialog < 0 )
      goto LABEL_106;
    ProgressDialog = CTLocalAllocPolicy::Alloc(v25, 0x40u, (unsigned __int64)pv, &hMem);
    if ( ProgressDialog < 0 )
      goto LABEL_106;
    hObject = CreateFileW(a2, 0xC0000000, 1u, 0, 4u, 0x80u, 0);
    if ( hObject == (HANDLE)-1LL )
    {
      v28 = 18;
      v32 = 18;
      goto LABEL_86;
    }
    v26 = v58;
    for ( i = a3; ; i += lstrlenW(i) + 1 )
    {
      v28 = 0;
      if ( !*i || !(_DWORD)v80 )
        break;
      if ( (unsigned int)lstrlenW(i) > 0xFF )
      {
        v37 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl);
        v35 = phwnd;
        fuStyle = 16;
        v36 = 10219;
        if ( v37 )
        {
          MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short_const___(v38, phwnd, 10219, 10055);
          goto LABEL_72;
        }
        goto LABEL_71;
      }
      if ( !lstrcmpW(i, a2) )
      {
        v33 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl);
        v35 = phwnd;
        fuStyle = 48;
        v36 = 10200;
        if ( v33 )
        {
          MessageBoxHelper::ShellMessageBoxTextScaled___1(v34, phwnd, 10200, 10055);
LABEL_72:
          lstrlenW(i);
          v28 = 9;
          break;
        }
LABEL_71:
        ShellMessageBoxW(g_hmodThisDll, v35, (LPCWSTR)v36, (LPCWSTR)0x2747, fuStyle);
        goto LABEL_72;
      }
      if ( !(unsigned int)CheckForBadChars(phwnd, i, 1) )
      {
        v28 = 9;
        break;
      }
      v29 = 1316LL * v16;
      StringCchCopyW((unsigned __int16 *)((char *)hMem + v29 + 796), 0x104u, i);
      StringCchCopyW((unsigned __int16 *)((char *)hMem + v29 + 276), v30, v26);
      if ( (GetFileAttributesW(i) & 0x10) != 0 )
      {
        *(_DWORD *)((char *)hMem + v29 + 260) = 1;
        StringCchPrintfW(pwszSrc, 0x104u, L"\"%s\\*.*\"", i);
        *(_DWORD *)((char *)hMem + v29 + 264) = 0;
      }
      else
      {
        *(_DWORD *)((char *)hMem + v29 + 260) = 0;
        StringCchPrintfW(pwszSrc, 0x104u, L"\"%s\"", i);
        *(_DWORD *)((char *)hMem + v29 + 264) = 1;
      }
      SHUnicodeToAnsi(pwszSrc, (PSTR)hMem + v29, 260);
      ++v16;
    }
    if ( v28 )
      goto LABEL_87;
    v31 = dzip(Src);
    v28 = v31;
    switch ( v31 )
    {
      case 0:
        goto LABEL_87;
      case 23:
        v44 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl);
        if ( a6 == 206 )
        {
          v42 = 10055;
          fuStyle = 16;
        }
        else
        {
          v42 = 10112;
          fuStyle = 48;
        }
        v41 = phwnd;
        v43 = 10521;
        if ( v44 )
        {
          MessageBoxHelper::ShellMessageBoxTextScaled___1(v45, phwnd, 10521, v42);
          goto LABEL_87;
        }
        break;
      case 12:
        v39 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl);
        v41 = phwnd;
        v42 = 10055;
        v43 = 10228;
        fuStyle = 16;
        if ( v39 )
        {
          MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short_const___(v40, phwnd, 10228, 10055);
LABEL_87:
          if ( hObject != (HANDLE)-1LL )
            CloseHandle(hObject);
          ((void (__fastcall *)(IUnknown *, _QWORD, _QWORD))punk->lpVtbl[2].QueryInterface)(punk, 0, 0);
          ((void (__fastcall *)(IUnknown *))punk->lpVtbl[1].AddRef)(punk);
          if ( v28 && v28 != 23 )
          {
            ProgressDialog = -2147467259;
            if ( !v57 )
              DeleteFileW(a2);
          }
          else
          {
            UpdateZipPath(a2);
            ProgressDialog = 0;
            if ( a6 == 206 && !v28 )
            {
              LoadStringW(g_hmodThisDll, 0x276Du, pwszSrc, 260);
              FileOp.hwnd = phwnd;
              FileOp.lpszProgressTitle = pwszSrc;
              *(_QWORD *)&FileOp.wFunc = 3;
              FileOp.pFrom = a3;
              FileOp.pTo = 0;
              *(_QWORD *)&FileOp.fFlags = 272;
              FileOp.hNameMappings = 0;
              if ( SHFileOperationW(&FileOp) )
              {
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
                {
                  fuStyle = 0;
                  MessageBoxHelper::ShellMessageBoxTextScaled___1(v46, phwnd, 10094, 10055);
                }
                else
                {
                  ShellMessageBoxW(g_hmodThisDll, phwnd, (LPCWSTR)0x276E, (LPCWSTR)0x2747, 0);
                }
              }
            }
          }
          if ( (unsigned int)EdpGetIsManaged() )
          {
            if ( v83 )
            {
              v48 = EdpHelpers::ProtectFilePathWithFileOperation(phwnd, (HWND)a2, v83, v47, fuStyle);
              if ( v48 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x544,
                  (unsigned int)"shell\\ext\\zip\\dropin.cpp",
                  (const char *)(unsigned int)v48,
                  fuStylea);
            }
          }
          LocalFree(hMem);
          goto LABEL_106;
        }
        break;
      default:
        v32 = v31;
LABEL_86:
        ShowZipError(phwnd, v32);
        goto LABEL_87;
    }
    ShellMessageBoxW(g_hmodThisDll, v41, (LPCWSTR)v43, (LPCWSTR)v42, fuStyle);
    goto LABEL_87;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl);
  v24 = 10161;
LABEL_39:
  if ( IsEnabled )
    MessageBoxHelper::ShellMessageBoxTextScaled___1(v23, phwnd, v24, 10055);
  else
    ShellMessageBoxW(g_hmodThisDll, phwnd, (LPCWSTR)v24, (LPCWSTR)0x2747, 0x30u);
  ((void (__fastcall *)(IUnknown *, _QWORD, _QWORD))punk->lpVtbl[2].QueryInterface)(punk, 0, 0);
  ((void (__fastcall *)(IUnknown *))punk->lpVtbl[1].AddRef)(punk);
  ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
  if ( v83 )
    CoTaskMemFree(v83);
  if ( v56 )
    CoTaskMemFree(v56);
  return 2147500037LL;
}

```

## disassembly

```asm
0x18000b430  push    rbp
0x18000b432  push    rbx
0x18000b433  push    rsi
0x18000b434  push    rdi
0x18000b435  push    r12
0x18000b437  push    r13
0x18000b439  push    r14
0x18000b43b  push    r15
0x18000b43d  lea     rbp, [rsp-26A8h]
0x18000b445  mov     eax, 27A8h
0x18000b44a  call    _alloca_probe
0x18000b44f  sub     rsp, rax
0x18000b452  mov     rax, cs:__security_cookie
0x18000b459  xor     rax, rsp
0x18000b45c  mov     [rbp+26E0h+var_50], rax
0x18000b463  mov     r12, [rbp+26E0h+arg_20]
0x18000b46a  mov     rdi, rcx
0x18000b46d  xor     r14d, r14d
0x18000b470  mov     [rsp+27E0h+var_2768], r9
0x18000b475  lea     rcx, [rbp+26E0h+punk]; struct IProgressDialog **
0x18000b47c  mov     [rbp+26E0h+punk], r14
0x18000b483  mov     r15, r8
0x18000b486  mov     rsi, rdx
0x18000b489  call    ?CreateProgressDialog@@YAJPEAPEAUIProgressDialog@@@Z; CreateProgressDialog(IProgressDialog * *)
0x18000b48e  mov     ebx, eax
0x18000b490  test    eax, eax
0x18000b492  js      loc_18000B816
0x18000b498  xor     edx, edx
0x18000b49a  mov     rcx, rsi
0x18000b49d  call    cs:__imp_PathFileExistsAndAttributesW
0x18000b4a3  mov     rcx, [rbp+26E0h+punk]
0x18000b4aa  lea     r9d, [r14+2]
0x18000b4ae  mov     [rsp+27E0h+var_2770], eax
0x18000b4b2  mov     rdx, rdi
0x18000b4b5  mov     qword ptr [rsp+27E0h+fuStyle], r14
0x18000b4ba  mov     r8, [rcx]
0x18000b4bd  mov     rax, [r8+18h]
0x18000b4c1  xor     r8d, r8d
0x18000b4c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4c9  mov     rcx, [rbp+26E0h+punk]; punk
0x18000b4d0  mov     ebx, eax
0x18000b4d2  test    eax, eax
0x18000b4d4  jns     short loc_18000B4FF
0x18000b4d6  mov     rax, [rcx]
0x18000b4d9  xor     r8d, r8d
0x18000b4dc  xor     edx, edx
0x18000b4de  mov     rax, [rax+30h]
0x18000b4e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4e7  mov     rcx, [rbp+26E0h+punk]
0x18000b4ee  mov     rax, [rcx]
0x18000b4f1  mov     rax, [rax+10h]
0x18000b4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4fa  jmp     loc_18000B816
0x18000b4ff  lea     rdx, [rbp+26E0h+phwnd]; phwnd
0x18000b506  mov     [rbp+26E0h+phwnd], r14
0x18000b50d  mov     rdi, r15
0x18000b510  call    cs:__imp_IUnknown_GetWindow
0x18000b516  mov     r13d, 104h
0x18000b51c  lea     rdx, [rbp+26E0h+Buffer]; lpBuffer
0x18000b523  mov     ecx, r13d; nBufferLength
0x18000b526  call    cs:__imp_GetTempPathW
0x18000b52c  mov     rcx, [rbp+26E0h+punk]; struct IProgressDialog *
0x18000b533  mov     edx, 276Bh; unsigned int
0x18000b538  call    ?SetTitle@@YAXPEAUIProgressDialog@@I@Z; SetTitle(IProgressDialog *,uint)
0x18000b53d  lea     rcx, [rbp+26E0h+Src]; void *
0x18000b541  mov     r8d, 89Ch; Size
0x18000b547  lea     rdx, qword_1800737C0; Src
0x18000b54e  call    memcpy_0
0x18000b553  mov     r8, rsi; unsigned __int16 *
0x18000b556  lea     rcx, [rbp+26E0h+pszPath]; unsigned __int16 *
0x18000b55d  mov     edx, r13d; unsigned __int64
0x18000b560  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b565  lea     rcx, [rbp+26E0h+pszPath]; pszPath
0x18000b56c  call    cs:__imp_PathStripToRootW
0x18000b572  lea     rcx, [rbp+26E0h+pszPath]; lpRootPathName
0x18000b579  call    cs:__imp_GetDriveTypeW
0x18000b57f  xor     edx, edx; Val
0x18000b581  lea     rcx, [rbp+26E0h+var_1E70]; void *
0x18000b588  mov     r8d, 238h; Size
0x18000b58e  mov     dword ptr [rbp+26E0h+TotalNumberOfBytes], eax
0x18000b594  call    memset_0
0x18000b599  mov     r8d, r13d; cchBuf
0x18000b59c  lea     rdx, [rbp+26E0h+pszDst]; pszDst
0x18000b5a3  mov     rcx, r15; pwszSrc
0x18000b5a6  call    cs:__imp_SHUnicodeToAnsi
0x18000b5ac  mov     rcx, [rbp+26E0h+punk]
0x18000b5b3  lea     rax, [rbp+26E0h+pszDst]
0x18000b5ba  mov     dword ptr [rbp+26E0h+var_1C10], r14d
0x18000b5c1  mov     r13, r14
0x18000b5c4  mov     [rbp+26E0h+var_1E68], rcx
0x18000b5cb  xor     edx, edx; Val
0x18000b5cd  mov     [rsp+27E0h+var_2780], r14b
0x18000b5d2  lea     rcx, [rbp+26E0h+var_1C10+4]; void *
0x18000b5d9  mov     [rsp+27E0h+var_277C], r14d
0x18000b5de  mov     r14d, 204h
0x18000b5e4  mov     r8d, r14d; Size
0x18000b5e7  mov     [rbp+26E0h+var_1E58], rax
0x18000b5ee  call    memset_0
0x18000b5f3  mov     r8d, r14d; Size
0x18000b5f6  mov     dword ptr [rbp+26E0h+var_1A00], r13d
0x18000b5fd  xor     edx, edx; Val
0x18000b5ff  lea     rcx, [rbp+26E0h+var_19FC]; void *
0x18000b606  call    memset_0
0x18000b60b  xor     ecx, ecx
0x18000b60d  mov     [rsp+27E0h+var_2778], rcx
0x18000b612  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000b616  inc     r14
0x18000b619  cmp     [r15+r14*2], cx
0x18000b61e  jnz     short loc_18000B616
0x18000b620  cmp     [rdi], cx
0x18000b623  jz      loc_18000B6D3
0x18000b629  cmp     [r15+r14*2+2], cx
0x18000b62f  lea     rax, [rsp+27E0h+var_2778]
0x18000b634  mov     [rsp+27E0h+var_2788], rax; unsigned __int16 **
0x18000b639  lea     r9, [rbp+26E0h+var_1C28]; unsigned int *
0x18000b640  lea     rax, [rbp+26E0h+var_1A00]
0x18000b647  mov     dword ptr [rbp+26E0h+var_1C28], ecx
0x18000b64d  mov     [rsp+27E0h+var_2798], rax; unsigned __int16 *
0x18000b652  setz    r8b; bool
0x18000b656  lea     rax, [rsp+27E0h+var_277C]
0x18000b65b  mov     [rbp+26E0h+pv], rcx
0x18000b662  mov     rcx, [rbp+26E0h+punk]; struct IProgressDialog *
0x18000b669  mov     rdx, rdi; unsigned __int16 *
0x18000b66c  mov     [rsp+27E0h+var_27A0], rax; unsigned int *
0x18000b671  lea     rax, [rbp+26E0h+var_1C10]
0x18000b678  mov     [rsp+27E0h+hTemplateFile], rax; unsigned __int16 *
0x18000b67d  lea     rax, [rsp+27E0h+var_2780]
0x18000b682  mov     qword ptr [rsp+27E0h+dwFlagsAndAttributes], rax; bool *
0x18000b687  lea     rax, [rbp+26E0h+pv]
0x18000b68e  mov     qword ptr [rsp+27E0h+fuStyle], rax; union _ULARGE_INTEGER *
0x18000b693  call    ?GetDropFileCountSizeAndEncryption@@YAJPEAUIProgressDialog@@PEBG_NPEAIPEAT_ULARGE_INTEGER@@PEA_NPEAGI36IPEAPEAG@Z; GetDropFileCountSizeAndEncryption(IProgressDialog *,ushort const *,bool,uint *,_ULARGE_INTEGER *,bool *,ushort *,uint,uint *,ushort *,uint,ushort * *)
0x18000b698  xor     ecx, ecx
0x18000b69a  mov     ebx, eax
0x18000b69c  test    eax, eax
0x18000b69e  js      short loc_18000B6D3
0x18000b6a0  mov     eax, dword ptr [rbp+26E0h+var_1C28]
0x18000b6a6  add     [rbp+26E0h+var_1E48], eax
0x18000b6ac  add     r13, [rbp+26E0h+pv]
0x18000b6b3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b6b7  inc     rax
0x18000b6ba  cmp     [rdi+rax*2], cx
0x18000b6be  jnz     short loc_18000B6B7
0x18000b6c0  lea     rdi, [rdi+rax*2]
0x18000b6c4  add     rdi, 2
0x18000b6c8  inc     dword ptr [rbp+26E0h+var_1E50]
0x18000b6ce  jmp     loc_18000B620
0x18000b6d3  xor     r14d, r14d
0x18000b6d6  test    r12, r12
0x18000b6d9  jz      short loc_18000B727
0x18000b6db  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000b6df  lea     rcx, [rbp+26E0h+pv]
0x18000b6e6  mov     rdx, r12
0x18000b6e9  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000b6ee  lea     rdx, [rbp+26E0h+pv]
0x18000b6f5  lea     rcx, [rsp+27E0h+var_2778]
0x18000b6fa  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18000b6ff  mov     rcx, [rbp+26E0h+pv]; pv
0x18000b706  test    rcx, rcx
0x18000b709  jz      short loc_18000B711
0x18000b70b  call    cs:__imp_CoTaskMemFree
0x18000b711  mov     r8, r15; unsigned __int16 *
0x18000b714  lea     rcx, [rbp+26E0h+var_1A00]; unsigned __int16 *
0x18000b71b  mov     edx, 104h; unsigned __int64
0x18000b720  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b725  mov     ebx, eax
0x18000b727  test    ebx, ebx
0x18000b729  js      loc_18000B7C8
0x18000b72f  cmp     [rsp+27E0h+var_277C], 1
0x18000b734  lea     r12, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x18000b73b  mov     edi, 2747h
0x18000b740  jnz     short loc_18000B788
0x18000b742  mov     rcx, r12
0x18000b745  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x18000b74a  mov     rdx, [rbp+26E0h+phwnd]; hWnd
0x18000b751  test    al, al
0x18000b753  mov     rcx, cs:g_hmodThisDll; hAppInst
0x18000b75a  lea     rax, [rbp+26E0h+var_1C10]
0x18000b761  mov     qword ptr [rsp+27E0h+dwFlagsAndAttributes], rax; __int64
0x18000b766  mov     r9d, edi; lpcTitle
0x18000b769  mov     [rsp+27E0h+fuStyle], 34h ; '4'; UINT
0x18000b771  mov     r8d, 2968h; lpcText
0x18000b777  jz      short loc_18000B780
0x18000b779  call    MessageBoxHelper__ShellMessageBoxTextScaled_unsigned_short___
0x18000b77e  jmp     short loc_18000B7B2
0x18000b780  call    cs:__imp_ShellMessageBoxW
0x18000b786  jmp     short loc_18000B7B2
0x18000b788  jbe     loc_18000B868
0x18000b78e  mov     rcx, r12
0x18000b791  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x18000b796  mov     rdx, [rbp+26E0h+phwnd]; hWnd
0x18000b79d  test    al, al
0x18000b79f  mov     eax, [rsp+27E0h+var_277C]
0x18000b7a3  mov     [rsp+27E0h+dwFlagsAndAttributes], eax
0x18000b7a7  jz      loc_18000B83B
0x18000b7ad  call    MessageBoxHelper__ShellMessageBoxTextScaled_unsigned_int_
0x18000b7b2  cmp     eax, 7
0x18000b7b5  jnz     loc_18000B868
0x18000b7bb  mov     ebx, 800704C7h
0x18000b7c0  test    ebx, ebx
0x18000b7c2  jns     loc_18000B868
0x18000b7c8  mov     rcx, [rbp+26E0h+punk]
0x18000b7cf  xor     r8d, r8d
0x18000b7d2  xor     edx, edx
0x18000b7d4  mov     rax, [rcx]
0x18000b7d7  mov     rax, [rax+30h]
0x18000b7db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7e0  mov     rcx, [rbp+26E0h+punk]
0x18000b7e7  mov     rax, [rcx]
0x18000b7ea  mov     rax, [rax+20h]
0x18000b7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7f3  mov     rcx, [rbp+26E0h+punk]
0x18000b7fa  mov     rax, [rcx]
0x18000b7fd  mov     rax, [rax+10h]
0x18000b801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b806  mov     rcx, [rsp+27E0h+var_2778]; pv
0x18000b80b  test    rcx, rcx
0x18000b80e  jz      short loc_18000B816
0x18000b810  call    cs:__imp_CoTaskMemFree
0x18000b816  mov     eax, ebx
0x18000b818  mov     rcx, [rbp+26E0h+var_50]
0x18000b81f  xor     rcx, rsp; StackCookie
0x18000b822  call    __security_check_cookie
0x18000b827  add     rsp, 27A8h
0x18000b82e  pop     r15
0x18000b830  pop     r14
0x18000b832  pop     r13
0x18000b834  pop     r12
0x18000b836  pop     rdi
0x18000b837  pop     rsi
0x18000b838  pop     rbx
0x18000b839  pop     rbp
0x18000b83a  retn
0x18000b83b  mov     rcx, cs:g_hmodThisDll; hAppInst
0x18000b842  mov     r9, rdi; lpcTitle
0x18000b845  mov     r8d, 2969h; lpcText
0x18000b84b  mov     [rsp+27E0h+fuStyle], 34h ; '4'; fuStyle
0x18000b853  call    cs:__imp_ShellMessageBoxW
0x18000b859  cmp     eax, 7
0x18000b85c  jnz     short loc_18000B868
0x18000b85e  mov     ebx, 800704C7h
0x18000b863  jmp     loc_18000B7C8
0x18000b868  xor     edx, edx
0x18000b86a  mov     [rbp+26E0h+var_1C28], r14
0x18000b871  lea     rcx, [rbp+26E0h+var_1C28]
0x18000b878  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000b87d  mov     rax, [rsp+27E0h+var_2778]
0x18000b882  lea     rcx, [rbp+26E0h+var_1C28]
0x18000b889  mov     r9d, [rbp+26E0h+var_1E48]; unsigned int
0x18000b890  lea     r8, [rbp+26E0h+var_1A00]; unsigned __int16 *
0x18000b897  mov     [rsp+27E0h+hTemplateFile], rcx; unsigned __int16 **
0x18000b89c  mov     rdx, rsi; unsigned __int16 *
0x18000b89f  mov     rcx, [rbp+26E0h+phwnd]; HWND
0x18000b8a6  mov     qword ptr [rsp+27E0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18000b8ab  mov     eax, [rbp+26E0h+arg_30]
0x18000b8b1  mov     [rsp+27E0h+fuStyle], eax; unsigned int
0x18000b8b5  call    ?EvaluateZipEdpPolicyIfNeeded@@YAJPEAUHWND__@@PEBG1IK1PEAPEAG@Z; EvaluateZipEdpPolicyIfNeeded(HWND__ *,ushort const *,ushort const *,uint,ulong,ushort const *,ushort * *)
0x18000b8ba  mov     ebx, eax
0x18000b8bc  test    eax, eax
0x18000b8be  js      loc_18000BF91
0x18000b8c4  mov     ebx, 1
0x18000b8c9  lea     r8, [rbp+26E0h+var_10B0]
0x18000b8d0  mov     r9d, 824h
0x18000b8d6  mov     [rbp+26E0h+var_272C], ebx
0x18000b8d9  lea     rdx, [rbp+26E0h+Buffer]
0x18000b8e0  mov     ecx, 0FDE9h
0x18000b8e5  call    cs:__imp_SHUnicodeToAnsiCP
0x18000b8eb  lea     rax, [rbp+26E0h+var_10B0]
0x18000b8f2  mov     rcx, rsi; unsigned __int16 *
0x18000b8f5  mov     [rbp+26E0h+var_2728], rax
0x18000b8f9  call    ?_GetFileSize@@YA_KPEBG@Z; _GetFileSize(ushort const *)
0x18000b8fe  mov     ecx, [rbp+26E0h+var_2730]
0x18000b901  lea     edx, [rbx+4]
0x18000b904  add     rax, r13
0x18000b907  cmp     rax, 7FFFFFFFh
0x18000b90d  cmovbe  ecx, edx
0x18000b910  cmp     dword ptr [rbp+26E0h+TotalNumberOfBytes], 2
0x18000b917  mov     [rbp+26E0h+var_2730], ecx
0x18000b91a  jnz     loc_18000BA1A
0x18000b920  lea     r9, [rbp+26E0h+pv]; lpTotalNumberOfFreeBytes
0x18000b927  mov     qword ptr [rbp+26E0h+FreeBytesAvailableToCaller], r14
0x18000b92e  lea     r8, [rbp+26E0h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x18000b935  mov     qword ptr [rbp+26E0h+TotalNumberOfBytes], r14
0x18000b93c  lea     rdx, [rbp+26E0h+FreeBytesAvailableToCaller]; lpFreeBytesAvailableToCaller
0x18000b943  mov     [rbp+26E0h+pv], r14
0x18000b94a  lea     rcx, [rbp+26E0h+pszPath]; lpDirectoryName
0x18000b951  call    cs:__imp_GetDiskFreeSpaceExW
0x18000b957  test    eax, eax
0x18000b959  jz      short loc_18000B978
0x18000b95b  cmp     [rbp+26E0h+pv], r13
0x18000b962  jnb     loc_18000BA1A
0x18000b968  mov     rcx, r12
0x18000b96b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x18000b970  mov     r8d, 27B1h
0x18000b976  jmp     short loc_18000B986
0x18000b978  mov     rcx, r12
0x18000b97b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x18000b980  mov     r8d, 27D7h; lpcText
0x18000b986  mov     rdx, [rbp+26E0h+phwnd]; hWnd
0x18000b98d  mov     r9, rdi; lpcTitle
0x18000b990  mov     [rsp+27E0h+fuStyle], 30h ; '0'; fuStyle
  ... truncated ...
```
