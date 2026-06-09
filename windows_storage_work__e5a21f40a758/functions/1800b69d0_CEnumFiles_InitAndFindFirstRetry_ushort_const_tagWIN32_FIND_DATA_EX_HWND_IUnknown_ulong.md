# CEnumFiles::InitAndFindFirstRetry(ushort const *,tagWIN32_FIND_DATA_EX *,HWND__ *,IUnknown *,ulong)

- ea: `0x1800b69d0`
- end: `0x1800b7051`
- name: `?InitAndFindFirstRetry@CEnumFiles@@UEAAJPEBGPEAUtagWIN32_FIND_DATA_EX@@PEAUHWND__@@PEAUIUnknown@@K@Z`
- size: `1665`
- prototype: `__int64 __fastcall(CEnumFiles *__hidden this, LPCWSTR lpFileName, struct tagWIN32_FIND_DATA_EX *, HWND hWnd, struct IUnknown *, unsigned int)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x1800b7058`

## callees

- `0x18001ec60`
- `0x180094c70`
- `0x1800b69d0`
- `0x18012dc90`
- `0x18012fa50`
- `0x18018a3b8`
- `0x18021dbd0`
- `0x180223cb0`
- `0x18024dfb0`
- `0x18024e230`
- `0x1802e23ec`
- `0x1802fad84`
- `0x18035ad00`
- `0x18035aed0`
- `0x18035b6ac`
- `0x18035b738`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x1803aee20`
- `0x180517614`
- `0x180547f30`
- `0x180548bd4`
- `0x1805491f0`
- `0x18054947c`
- `0x1805497d0`
- `0x18059963c`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800b6f45`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800b6f45`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800b6d8b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800b6d8b`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800b6afb`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800b6afb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1800b6a3a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1800b6ecc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1800b6a3a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1800b6ecc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800b6a4b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800b6a4b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b6dbb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b6dbb`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1800b6dcc`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1800b6e6d`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1800b6dcc`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1800b6e6d`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x1800b6b9d`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x1800b6b9d`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_HandleUnrecognizedFileSystem` at `0x1800b6bc1`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_HandleUnrecognizedFileSystem` at `0x1800b6bc1`

## pseudocode

```c
__int64 __fastcall CEnumFiles::InitAndFindFirstRetry(
        CEnumFiles *this,
        LPCWSTR lpFileName,
        struct tagWIN32_FIND_DATA_EX *a3,
        HWND hWnd,
        struct IUnknown *a5,
        int a6)
{
  struct tagWIN32_FIND_DATA_EX *v7; // r14
  int inited; // ebx
  unsigned int DriveNumberW; // eax
  CEnumFiles *v12; // rcx
  CMountPoint *v13; // r14
  char IsEnabled; // al
  Shell32Instance *v15; // rcx
  HINSTANCE v16; // rax
  HINSTANCE v17; // rax
  __int64 v18; // r8
  BOOL *v19; // r9
  CEnumFiles *v20; // rcx
  DWORD FileAttributesW; // eax
  DWORD v22; // r14d
  const unsigned __int16 *v23; // rdx
  int v24; // eax
  int v25; // r14d
  BOOL v26; // r12d
  HINSTANCE v27; // rax
  BOOL *v28; // r9
  __int64 v30; // [rsp+30h] [rbp-D0h] BYREF
  struct tagWIN32_FIND_DATA_EX *v31; // [rsp+38h] [rbp-C8h]
  LPVOID ppv[2]; // [rsp+40h] [rbp-C0h] BYREF
  TASKDIALOGCONFIG pTaskConfig; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR Buffer[128]; // [rsp+300h] [rbp+200h] BYREF

  v7 = a3;
  v31 = a3;
  inited = CEnumFiles::_InitEnumeration(this, lpFileName, 0, 0, a3);
  if ( inited >= 0 )
    return (unsigned int)inited;
  HIDWORD(v30) = 0;
  if ( PathIsUNCW(lpFileName)
    || (DriveNumberW = PathGetDriveNumberW(lpFileName), (unsigned int)IsDisconnectedNetDrive(DriveNumberW)) )
  {
    LODWORD(v30) = 1;
    inited = CEnumFiles::_RetryNetwork(this, hWnd, a5, lpFileName, (int *)&v30, v7);
    goto LABEL_26;
  }
  LODWORD(v30) = 0;
  if ( hWnd )
  {
    if ( PathRetryRemovable(inited, lpFileName) )
      inited = CEnumFiles::InitAndFindFirstRemovable(this, lpFileName, v7, hWnd, a5);
    if ( CEnumFiles::s_IsUnformattedMediaResult(inited, lpFileName, (int *)&v30 + 1) )
    {
      ppv[0] = 0;
      if ( (int)CMountPoint::GetMountPoint(lpFileName, 1, ppv) >= 0 )
      {
        v13 = (CMountPoint *)ppv[0];
        if ( (*(unsigned int (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 464LL))(ppv[0]) )
        {
          inited = -2147023673;
          if ( !GetVolumePathNameW(lpFileName, szVolumePathName, 0x104u) || !szVolumePathName[2] || !szVolumePathName[3] )
          {
            if ( (unsigned __int8)IsSHELL32_SHIsVirtualDevicePresent() )
            {
              LOBYTE(v18) = *(_BYTE *)lpFileName;
              if ( !(unsigned int)SHELL32_HandleUnrecognizedFileSystem(hWnd, a5, v18, v13) )
                inited = CEnumFiles::_InitEnumeration(this, lpFileName, 0, 0, v31);
            }
            goto LABEL_24;
          }
          GoModal(hWnd, a5, 1);
          IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl);
          v15 = (CEnumFiles *)((char *)this + 152);
          if ( IsEnabled )
          {
            v16 = Shell32Instance::get(v15);
            MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short____0(
              v16,
              hWnd,
              (LPCWSTR)0x1013,
              (LPCWSTR)0x1012,
              0x10030u,
              (__int64)szVolumePathName);
          }
          else
          {
            v17 = Shell32Instance::get(v15);
            ShellMessageBoxW(v17, hWnd, (LPCWSTR)0x1013, (LPCWSTR)0x1012, 0x10030u, szVolumePathName, v30);
          }
        }
        else
        {
          if ( HIDWORD(v30) )
          {
LABEL_24:
            CMountPoint::Release(v13);
            v7 = v31;
            goto LABEL_26;
          }
          inited = -2147023673;
          GoModal(hWnd, a5, 1);
          pTaskConfig.cbSize = 160;
          memset_0(&pTaskConfig.hwndParent, 0, 0x9Cu);
          pTaskConfig.hwndParent = hWnd;
          pTaskConfig.hInstance = Shell32Instance::get((CEnumFiles *)((char *)this + 152));
          pTaskConfig.pszWindowTitle = (PCWSTR)4219;
          pTaskConfig.pszMainInstruction = (PCWSTR)4134;
          pTaskConfig.pszContent = (PCWSTR)4135;
          pTaskConfig.dwCommonButtons = 32;
          pTaskConfig.nDefaultButton = 8;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
            MessageBoxHelper::TaskDialogIndirectScaled(&pTaskConfig, 0);
          else
            TaskDialogIndirect(&pTaskConfig, 0, 0, v19);
        }
        GoModal(hWnd, a5, 0);
        goto LABEL_24;
      }
    }
LABEL_26:
    if ( inited >= 0 )
      return (unsigned int)inited;
  }
  if ( inited == -2147023673 )
    goto LABEL_66;
  if ( inited != -2144927744 && (a6 & 3) != 0 && !(unsigned int)CEnumFiles::_PathExistsWithOutSpec(v12, lpFileName) )
  {
    if ( (unsigned int)CEnumFiles::_PathExistsRoot(v20, lpFileName) )
    {
      inited = CEnumFiles::_OfferToCreateDir(this, hWnd, a5, lpFileName, a6);
      if ( inited >= 0 )
      {
        inited = CEnumFiles::_InitEnumeration(this, lpFileName, 0, 0, v7);
        if ( inited >= 0 )
          return (unsigned int)inited;
      }
    }
  }
  if ( inited == -2147023673 )
  {
LABEL_66:
    CEnumFiles::_FindClose(this);
    return (unsigned int)inited;
  }
  if ( inited == -2144927744 )
    goto LABEL_65;
  if ( !hWnd )
    goto LABEL_65;
  if ( (a6 & 0x10) != 0 )
    goto LABEL_65;
  FileAttributesW = GetFileAttributesW(lpFileName);
  ppv[0] = 0;
  v22 = FileAttributesW;
  if ( CoCreateInstance(
         &GUID_c529c7ef_a3af_45f2_8a47_767b33aa5cc0,
         0,
         1u,
         &GUID_fb5ad46a_dd49_470d_8132_6a094056401d,
         ppv) < 0 )
    goto LABEL_65;
  if ( PathIsNetworkPathW(lpFileName)
    && !(*(unsigned int (__fastcall **)(LPVOID, _QWORD, LPCWSTR))(*(_QWORD *)ppv[0] + 32LL))(
          ppv[0],
          (unsigned int)inited,
          lpFileName) )
  {
    if ( PathGetComputerName(lpFileName, v23, szVolumePathName, 0x100u) >= 0
      && (*(int (__fastcall **)(LPVOID, HWND, WCHAR *, LPCWSTR, int))(*(_QWORD *)ppv[0] + 24LL))(
           ppv[0],
           hWnd,
           szVolumePathName,
           lpFileName,
           inited) < 0 )
    {
      goto LABEL_64;
    }
    CEnumFiles::_FindClose(this);
    v24 = CEnumFiles::_InitEnumeration(this, lpFileName, 0, 0, v31);
    goto LABEL_49;
  }
  if ( inited != -2147024891 )
  {
    if ( (inited & 0x1FFF0000) != 0x70000 || (v25 = (unsigned __int16)inited, (unsigned __int16)inited == 40) )
      v25 = 5;
    goto LABEL_55;
  }
  if ( v22 == -1 || (v22 & 6) == 6 || PathIsNetworkPathW(lpFileName) )
  {
    if ( a6 < 0 )
      goto LABEL_64;
    v25 = 5;
LABEL_55:
    v26 = 0;
    PathIsUNCW(lpFileName);
    if ( v25 != 3 )
      v26 = HIDWORD(v30) != 0;
    GoModal(hWnd, a5, 1);
    if ( v26 )
    {
      v27 = Shell32Instance::get((CEnumFiles *)((char *)this + 152));
      LoadStringW(v27, 0x1928u, Buffer, 128);
      if ( (int)StringCchPrintfW(szVolumePathName, 0x80u, Buffer, lpFileName) >= 0 )
      {
        pTaskConfig.cbSize = 160;
        memset_0(&pTaskConfig.hwndParent, 0, 0x9Cu);
        pTaskConfig.hwndParent = hWnd;
        pTaskConfig.hInstance = Shell32Instance::get((CEnumFiles *)((char *)this + 152));
        pTaskConfig.pszMainInstruction = szVolumePathName;
        pTaskConfig.pszWindowTitle = (PCWSTR)4219;
        pTaskConfig.pszContent = (PCWSTR)6441;
        pTaskConfig.dwCommonButtons = 32;
        pTaskConfig.nDefaultButton = 8;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
          MessageBoxHelper::TaskDialogIndirectScaled(&pTaskConfig, 0);
        else
          TaskDialogIndirect(&pTaskConfig, 0, 0, v28);
      }
    }
    else
    {
      SHEnumErrorMessageBox(hWnd, v30);
    }
    GoModal(hWnd, a5, 0);
    inited = -2147023673;
    goto LABEL_64;
  }
  v24 = CEnumFiles::_RetryWithElevation(this, hWnd, a5, lpFileName, v31);
LABEL_49:
  inited = v24;
LABEL_64:
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
LABEL_65:
  if ( inited < 0 )
    goto LABEL_66;
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800b69d0  push    rbp
0x1800b69d2  push    rbx
0x1800b69d3  push    rsi
0x1800b69d4  push    rdi
0x1800b69d5  push    r12
0x1800b69d7  push    r13
0x1800b69d9  push    r14
0x1800b69db  push    r15
0x1800b69dd  lea     rbp, [rsp-318h]
0x1800b69e5  sub     rsp, 418h
0x1800b69ec  mov     rax, cs:__security_cookie
0x1800b69f3  xor     rax, rsp
0x1800b69f6  mov     [rbp+350h+var_50], rax
0x1800b69fd  mov     r13, [rbp+350h+arg_20]
0x1800b6a04  mov     rsi, r9
0x1800b6a07  mov     r14, r8
0x1800b6a0a  mov     [rsp+450h+var_418], r8
0x1800b6a0f  mov     qword ptr [rsp+450h+fuStyle], r8; struct tagWIN32_FIND_DATA_EX *
0x1800b6a14  xor     r9d, r9d; int
0x1800b6a17  xor     r8d, r8d; unsigned __int16 *
0x1800b6a1a  mov     rdi, rdx
0x1800b6a1d  mov     r15, rcx
0x1800b6a20  call    ?_InitEnumeration@CEnumFiles@@AEAAJPEBG0HPEAUtagWIN32_FIND_DATA_EX@@@Z; CEnumFiles::_InitEnumeration(ushort const *,ushort const *,int,tagWIN32_FIND_DATA_EX *)
0x1800b6a25  xor     r12d, r12d
0x1800b6a28  mov     ebx, eax
0x1800b6a2a  test    eax, eax
0x1800b6a2c  jns     loc_1800B702C
0x1800b6a32  mov     rcx, rdi; pszPath
0x1800b6a35  mov     [rsp+450h+var_41C], r12d
0x1800b6a3a  call    cs:__imp_PathIsUNCW
0x1800b6a40  test    eax, eax
0x1800b6a42  jnz     loc_1800B6CAE
0x1800b6a48  mov     rcx, rdi; pszPath
0x1800b6a4b  call    cs:__imp_PathGetDriveNumberW
0x1800b6a51  mov     ecx, eax
0x1800b6a53  call    IsDisconnectedNetDrive
0x1800b6a58  test    eax, eax
0x1800b6a5a  jnz     loc_1800B6CAE
0x1800b6a60  mov     [rsp+450h+var_420], r12d
0x1800b6a65  test    rsi, rsi
0x1800b6a68  jz      loc_1800B6CE8
0x1800b6a6e  mov     rdx, rdi; unsigned __int16 *
0x1800b6a71  mov     ecx, ebx; int
0x1800b6a73  call    ?PathRetryRemovable@@YAHJPEBG@Z; PathRetryRemovable(long,ushort const *)
0x1800b6a78  test    eax, eax
0x1800b6a7a  jz      short loc_1800B6A94
0x1800b6a7c  mov     r9, rsi; hWndParent
0x1800b6a7f  mov     qword ptr [rsp+450h+fuStyle], r13; struct IUnknown *
0x1800b6a84  mov     r8, r14; struct tagWIN32_FIND_DATA_EX *
0x1800b6a87  mov     rdx, rdi; lpFileName
0x1800b6a8a  mov     rcx, r15; this
0x1800b6a8d  call    ?InitAndFindFirstRemovable@CEnumFiles@@UEAAJPEBGPEAUtagWIN32_FIND_DATA_EX@@PEAUHWND__@@PEAUIUnknown@@@Z; CEnumFiles::InitAndFindFirstRemovable(ushort const *,tagWIN32_FIND_DATA_EX *,HWND__ *,IUnknown *)
0x1800b6a92  mov     ebx, eax
0x1800b6a94  lea     r8, [rsp+450h+var_41C]; int *
0x1800b6a99  mov     rdx, rdi; unsigned __int16 *
0x1800b6a9c  mov     ecx, ebx; int
0x1800b6a9e  call    ?s_IsUnformattedMediaResult@CEnumFiles@@CAHJPEBGPEAH@Z; CEnumFiles::s_IsUnformattedMediaResult(long,ushort const *,int *)
0x1800b6aa3  test    eax, eax
0x1800b6aa5  jz      loc_1800B6CE0
0x1800b6aab  lea     r8, [rsp+450h+ppv]
0x1800b6ab0  mov     [rsp+450h+ppv], r12
0x1800b6ab5  mov     edx, 1
0x1800b6aba  mov     rcx, rdi
0x1800b6abd  call    ?GetMountPoint@CMountPoint@@SAJPEBGW4AddToDriveLetterCache@@PEAPEAV1@@Z; CMountPoint::GetMountPoint(ushort const *,AddToDriveLetterCache,CMountPoint * *)
0x1800b6ac2  test    eax, eax
0x1800b6ac4  js      loc_1800B6CE0
0x1800b6aca  mov     r14, [rsp+450h+ppv]
0x1800b6acf  mov     rcx, r14
0x1800b6ad2  mov     rax, [r14]
0x1800b6ad5  mov     rax, [rax+1D0h]
0x1800b6adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6ae1  test    eax, eax
0x1800b6ae3  jz      loc_1800B6BF1
0x1800b6ae9  mov     r8d, 104h; cchBufferLength
0x1800b6aef  lea     rdx, [rbp+350h+szVolumePathName]; lpszVolumePathName
0x1800b6af3  mov     rcx, rdi; lpszFileName
0x1800b6af6  mov     ebx, 800704C7h
0x1800b6afb  call    cs:__imp_GetVolumePathNameW
0x1800b6b01  test    eax, eax
0x1800b6b03  jz      loc_1800B6BA8
0x1800b6b09  cmp     r12w, [rbp+350h+var_35C]
0x1800b6b0e  jz      loc_1800B6BA8
0x1800b6b14  cmp     r12w, [rbp+350h+var_35A]
0x1800b6b19  jz      loc_1800B6BA8
0x1800b6b1f  mov     r8d, 1
0x1800b6b25  mov     rdx, r13
0x1800b6b28  mov     rcx, rsi
0x1800b6b2b  call    GoModal
0x1800b6b30  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x1800b6b37  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x1800b6b3c  lea     rcx, [r15+98h]; this
0x1800b6b43  test    al, al
0x1800b6b45  jz      short loc_1800B6B77
0x1800b6b47  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1800b6b4c  mov     r9d, 1012h; lpcTitle
0x1800b6b52  mov     rcx, rax; hAppInst
0x1800b6b55  lea     rax, [rbp+350h+szVolumePathName]
0x1800b6b59  mov     rdx, rsi; hWnd
0x1800b6b5c  mov     [rsp+450h+var_428], rax; __int64
0x1800b6b61  mov     [rsp+450h+fuStyle], 10030h; UINT
0x1800b6b69  lea     r8d, [r9+1]; lpcText
0x1800b6b6d  call    MessageBoxHelper__ShellMessageBoxTextScaled_unsigned_short____0
0x1800b6b72  jmp     loc_1800B6C91
0x1800b6b77  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1800b6b7c  mov     r9d, 1012h; lpcTitle
0x1800b6b82  mov     rcx, rax; hAppInst
0x1800b6b85  lea     rax, [rbp+350h+szVolumePathName]
0x1800b6b89  mov     rdx, rsi; hWnd
0x1800b6b8c  mov     [rsp+450h+var_428], rax
0x1800b6b91  mov     [rsp+450h+fuStyle], 10030h; fuStyle
0x1800b6b99  lea     r8d, [r9+1]; lpcText
0x1800b6b9d  call    cs:__imp_ShellMessageBoxW
0x1800b6ba3  jmp     loc_1800B6C91
0x1800b6ba8  call    IsSHELL32_SHIsVirtualDevicePresent
0x1800b6bad  test    al, al
0x1800b6baf  jz      loc_1800B6C9F
0x1800b6bb5  mov     r8b, [rdi]
0x1800b6bb8  mov     r9, r14
0x1800b6bbb  mov     rdx, r13
0x1800b6bbe  mov     rcx, rsi
0x1800b6bc1  call    cs:__imp_SHELL32_HandleUnrecognizedFileSystem
0x1800b6bc7  test    eax, eax
0x1800b6bc9  jnz     loc_1800B6C9F
0x1800b6bcf  mov     rax, [rsp+450h+var_418]
0x1800b6bd4  xor     r9d, r9d; int
0x1800b6bd7  xor     r8d, r8d; unsigned __int16 *
0x1800b6bda  mov     qword ptr [rsp+450h+fuStyle], rax; struct tagWIN32_FIND_DATA_EX *
0x1800b6bdf  mov     rdx, rdi; lpFileName
0x1800b6be2  mov     rcx, r15; this
0x1800b6be5  call    ?_InitEnumeration@CEnumFiles@@AEAAJPEBG0HPEAUtagWIN32_FIND_DATA_EX@@@Z; CEnumFiles::_InitEnumeration(ushort const *,ushort const *,int,tagWIN32_FIND_DATA_EX *)
0x1800b6bea  mov     ebx, eax
0x1800b6bec  jmp     loc_1800B6C9F
0x1800b6bf1  cmp     [rsp+450h+var_41C], r12d
0x1800b6bf6  jnz     loc_1800B6C9F
0x1800b6bfc  mov     r8d, 1
0x1800b6c02  mov     rdx, r13
0x1800b6c05  mov     rcx, rsi
0x1800b6c08  mov     ebx, 800704C7h
0x1800b6c0d  call    GoModal
0x1800b6c12  xor     edx, edx; Val
0x1800b6c14  mov     [rsp+450h+pTaskConfig.cbSize], 0A0h
0x1800b6c1c  mov     r8d, 9Ch; Size
0x1800b6c22  lea     rcx, [rsp+450h+pTaskConfig.hwndParent]; void *
0x1800b6c27  call    memset_0
0x1800b6c2c  lea     rcx, [r15+98h]; this
0x1800b6c33  mov     [rsp+450h+pTaskConfig.hwndParent], rsi
0x1800b6c38  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1800b6c3d  mov     [rsp+450h+pTaskConfig.hInstance], rax
0x1800b6c42  mov     [rsp+450h+pTaskConfig.pszWindowTitle], 107Bh
0x1800b6c4b  mov     [rsp+450h+pTaskConfig.pszMainInstruction], 1026h
0x1800b6c54  mov     [rbp+350h+pTaskConfig.pszContent], 1027h
0x1800b6c5c  mov     [rsp+450h+pTaskConfig.dwCommonButtons], 20h ; ' '
0x1800b6c64  mov     [rbp+350h+pTaskConfig.nDefaultButton], 8
0x1800b6c6b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x1800b6c72  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x1800b6c77  xor     edx, edx; pnButton
0x1800b6c79  lea     rcx, [rsp+450h+pTaskConfig]; pTaskConfig
0x1800b6c7e  test    al, al
0x1800b6c80  jz      short loc_1800B6C89
0x1800b6c82  call    MessageBoxHelper__TaskDialogIndirectScaled
0x1800b6c87  jmp     short loc_1800B6C91
0x1800b6c89  xor     r8d, r8d; pnRadioButton
0x1800b6c8c  call    TaskDialogIndirect
0x1800b6c91  xor     r8d, r8d
0x1800b6c94  mov     rdx, r13
0x1800b6c97  mov     rcx, rsi
0x1800b6c9a  call    GoModal
0x1800b6c9f  mov     rcx, r14; this
0x1800b6ca2  call    ?Release@CMountPoint@@QEAAKXZ; CMountPoint::Release(void)
0x1800b6ca7  mov     r14, [rsp+450h+var_418]
0x1800b6cac  jmp     short loc_1800B6CE0
0x1800b6cae  lea     rax, [rsp+450h+var_420]
0x1800b6cb3  mov     [rsp+450h+var_428], r14; struct tagWIN32_FIND_DATA_EX *
0x1800b6cb8  mov     r9, rdi; unsigned __int16 *
0x1800b6cbb  mov     qword ptr [rsp+450h+fuStyle], rax; int *
0x1800b6cc0  mov     r8, r13; struct IUnknown *
0x1800b6cc3  mov     [rsp+450h+var_420], 1
0x1800b6ccb  mov     rdx, rsi; hwndParent
0x1800b6cce  mov     rcx, r15; this
0x1800b6cd1  call    ?_RetryNetwork@CEnumFiles@@AEAAJPEAUHWND__@@PEAUIUnknown@@PEBGPEAHPEAUtagWIN32_FIND_DATA_EX@@@Z; CEnumFiles::_RetryNetwork(HWND__ *,IUnknown *,ushort const *,int *,tagWIN32_FIND_DATA_EX *)
0x1800b6cd6  mov     ebx, eax
0x1800b6cd8  mov     eax, [rsp+450h+var_420]
0x1800b6cdc  mov     [rsp+450h+var_420], eax
0x1800b6ce0  test    ebx, ebx
0x1800b6ce2  jns     loc_1800B702C
0x1800b6ce8  mov     r12d, [rbp+350h+arg_28]
0x1800b6cef  cmp     ebx, 800704C7h
0x1800b6cf5  jz      loc_1800B7024
0x1800b6cfb  cmp     ebx, 80270000h
0x1800b6d01  jz      short loc_1800B6D5D
0x1800b6d03  test    r12b, 3
0x1800b6d07  jz      short loc_1800B6D5D
0x1800b6d09  mov     rdx, rdi; unsigned __int16 *
0x1800b6d0c  call    ?_PathExistsWithOutSpec@CEnumFiles@@AEAAHPEBG@Z; CEnumFiles::_PathExistsWithOutSpec(ushort const *)
0x1800b6d11  test    eax, eax
0x1800b6d13  jnz     short loc_1800B6D5D
0x1800b6d15  mov     rdx, rdi; unsigned __int16 *
0x1800b6d18  call    ?_PathExistsRoot@CEnumFiles@@AEAAHPEBG@Z; CEnumFiles::_PathExistsRoot(ushort const *)
0x1800b6d1d  test    eax, eax
0x1800b6d1f  jz      short loc_1800B6D5D
0x1800b6d21  mov     r9, rdi; unsigned __int16 *
0x1800b6d24  mov     [rsp+450h+fuStyle], r12d; unsigned int
0x1800b6d29  mov     r8, r13; struct IUnknown *
0x1800b6d2c  mov     rdx, rsi; HWND
0x1800b6d2f  mov     rcx, r15; this
0x1800b6d32  call    ?_OfferToCreateDir@CEnumFiles@@AEAAJPEAUHWND__@@PEAUIUnknown@@PEBGK@Z; CEnumFiles::_OfferToCreateDir(HWND__ *,IUnknown *,ushort const *,ulong)
0x1800b6d37  mov     ebx, eax
0x1800b6d39  test    eax, eax
0x1800b6d3b  js      short loc_1800B6D5D
0x1800b6d3d  xor     r9d, r9d; int
0x1800b6d40  mov     qword ptr [rsp+450h+fuStyle], r14; struct tagWIN32_FIND_DATA_EX *
0x1800b6d45  xor     r8d, r8d; unsigned __int16 *
0x1800b6d48  mov     rdx, rdi; lpFileName
0x1800b6d4b  mov     rcx, r15; this
0x1800b6d4e  call    ?_InitEnumeration@CEnumFiles@@AEAAJPEBG0HPEAUtagWIN32_FIND_DATA_EX@@@Z; CEnumFiles::_InitEnumeration(ushort const *,ushort const *,int,tagWIN32_FIND_DATA_EX *)
0x1800b6d53  mov     ebx, eax
0x1800b6d55  test    eax, eax
0x1800b6d57  jns     loc_1800B702C
0x1800b6d5d  cmp     ebx, 800704C7h
0x1800b6d63  jz      loc_1800B7024
0x1800b6d69  cmp     ebx, 80270000h
0x1800b6d6f  jz      loc_1800B7020
0x1800b6d75  test    rsi, rsi
0x1800b6d78  jz      loc_1800B7020
0x1800b6d7e  test    r12b, 10h
0x1800b6d82  jnz     loc_1800B7020
0x1800b6d88  mov     rcx, rdi; lpFileName
0x1800b6d8b  call    cs:__imp_GetFileAttributesW
0x1800b6d91  xor     edx, edx; pUnkOuter
0x1800b6d93  mov     [rsp+450h+ppv], 0
0x1800b6d9c  mov     r14d, eax
0x1800b6d9f  lea     r9, _GUID_fb5ad46a_dd49_470d_8132_6a094056401d; riid
0x1800b6da6  lea     rax, [rsp+450h+ppv]
0x1800b6dab  lea     rcx, _GUID_c529c7ef_a3af_45f2_8a47_767b33aa5cc0; rclsid
0x1800b6db2  mov     qword ptr [rsp+450h+fuStyle], rax; ppv
0x1800b6db7  lea     r8d, [rdx+1]; dwClsContext
0x1800b6dbb  call    cs:__imp_CoCreateInstance
0x1800b6dc1  test    eax, eax
0x1800b6dc3  js      loc_1800B7020
0x1800b6dc9  mov     rcx, rdi; pszPath
0x1800b6dcc  call    cs:__imp_PathIsNetworkPathW
0x1800b6dd2  test    eax, eax
0x1800b6dd4  jz      short loc_1800B6E52
0x1800b6dd6  mov     rcx, [rsp+450h+ppv]
0x1800b6ddb  mov     r8, rdi
0x1800b6dde  mov     edx, ebx
0x1800b6de0  mov     rax, [rcx]
0x1800b6de3  mov     rax, [rax+20h]
0x1800b6de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6dec  test    eax, eax
0x1800b6dee  jnz     short loc_1800B6E52
0x1800b6df0  mov     r9d, 100h; unsigned int
0x1800b6df6  lea     r8, [rbp+350h+szVolumePathName]; unsigned __int16 *
0x1800b6dfa  mov     rcx, rdi; unsigned __int16 *
0x1800b6dfd  call    ?PathGetComputerName@@YAJPEBG0PEAGI@Z; PathGetComputerName(ushort const *,ushort const *,ushort *,uint)
0x1800b6e02  test    eax, eax
0x1800b6e04  js      short loc_1800B6E2D
0x1800b6e06  mov     rcx, [rsp+450h+ppv]
0x1800b6e0b  lea     r8, [rbp+350h+szVolumePathName]
0x1800b6e0f  mov     r9, rdi
0x1800b6e12  mov     [rsp+450h+fuStyle], ebx
0x1800b6e16  mov     rdx, rsi
0x1800b6e19  mov     rax, [rcx]
0x1800b6e1c  mov     rax, [rax+18h]
0x1800b6e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6e25  test    eax, eax
0x1800b6e27  js      loc_1800B700F
0x1800b6e2d  mov     rcx, r15; this
0x1800b6e30  call    ?_FindClose@CEnumFiles@@AEAAXXZ; CEnumFiles::_FindClose(void)
0x1800b6e35  mov     rax, [rsp+450h+var_418]
0x1800b6e3a  xor     r9d, r9d; int
0x1800b6e3d  xor     r8d, r8d; unsigned __int16 *
0x1800b6e40  mov     qword ptr [rsp+450h+fuStyle], rax; struct tagWIN32_FIND_DATA_EX *
0x1800b6e45  mov     rdx, rdi; lpFileName
0x1800b6e48  mov     rcx, r15; this
0x1800b6e4b  call    ?_InitEnumeration@CEnumFiles@@AEAAJPEBG0HPEAUtagWIN32_FIND_DATA_EX@@@Z; CEnumFiles::_InitEnumeration(ushort const *,ushort const *,int,tagWIN32_FIND_DATA_EX *)
0x1800b6e50  jmp     short loc_1800B6E92
0x1800b6e52  cmp     ebx, 80070005h
0x1800b6e58  jnz     short loc_1800B6EA8
0x1800b6e5a  cmp     r14d, 0FFFFFFFFh
0x1800b6e5e  jz      short loc_1800B6E99
0x1800b6e60  and     r14d, 6
0x1800b6e64  cmp     r14b, 6
0x1800b6e68  jz      short loc_1800B6E99
0x1800b6e6a  mov     rcx, rdi; pszPath
0x1800b6e6d  call    cs:__imp_PathIsNetworkPathW
0x1800b6e73  test    eax, eax
0x1800b6e75  jnz     short loc_1800B6E99
0x1800b6e77  mov     rax, [rsp+450h+var_418]
0x1800b6e7c  mov     r9, rdi; lpFileName
0x1800b6e7f  mov     r8, r13; struct IUnknown *
0x1800b6e82  mov     qword ptr [rsp+450h+fuStyle], rax; struct tagWIN32_FIND_DATA_EX *
0x1800b6e87  mov     rdx, rsi; HWND
0x1800b6e8a  mov     rcx, r15; this
0x1800b6e8d  call    ?_RetryWithElevation@CEnumFiles@@AEAAJPEAUHWND__@@PEAUIUnknown@@PEBGPEAUtagWIN32_FIND_DATA_EX@@@Z; CEnumFiles::_RetryWithElevation(HWND__ *,IUnknown *,ushort const *,tagWIN32_FIND_DATA_EX *)
0x1800b6e92  mov     ebx, eax
0x1800b6e94  jmp     loc_1800B700F
0x1800b6e99  test    r12d, r12d
0x1800b6e9c  js      loc_1800B700F
0x1800b6ea2  movzx   r14d, bx
  ... truncated ...
```
