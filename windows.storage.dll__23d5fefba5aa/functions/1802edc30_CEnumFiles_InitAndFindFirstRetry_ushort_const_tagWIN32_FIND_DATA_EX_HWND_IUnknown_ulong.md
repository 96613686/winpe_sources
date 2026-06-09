# CEnumFiles::InitAndFindFirstRetry(ushort const *,tagWIN32_FIND_DATA_EX *,HWND__ *,IUnknown *,ulong)

- ea: `0x1802edc30`
- end: `0x1802ee2d1`
- name: `?InitAndFindFirstRetry@CEnumFiles@@UEAAJPEBGPEAUtagWIN32_FIND_DATA_EX@@PEAUHWND__@@PEAUIUnknown@@K@Z`
- size: `1697`
- prototype: `__int64 __fastcall(CEnumFiles *__hidden this, const unsigned __int16 *, struct tagWIN32_FIND_DATA_EX *, HWND hwndParent, struct IUnknown *, unsigned int)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x1800f07dc`

## callees

- `0x180045bd0`
- `0x180056670`
- `0x180058560`
- `0x1800e9414`
- `0x1800f3790`
- `0x1800f8f68`
- `0x180117f6c`
- `0x180236540`
- `0x18025c018`
- `0x18025c2c0`
- `0x1802edc30`
- `0x1802f29dc`
- `0x18030b77c`
- `0x18036be50`
- `0x18036c018`
- `0x18036cfc8`
- `0x18036d060`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x18052dc04`
- `0x18055fe50`
- `0x180560b74`
- `0x180561224`
- `0x180561278`
- `0x18056151c`
- `0x180561894`
- `0x1805b54f8`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1802ee1be`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1802ee1be`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1802edfe6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1802edfe6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1802edc9a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1802ee13f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1802edc9a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1802ee13f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1802edcb1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1802edcb1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802ee01c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802ee01c`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1802ee033`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1802ee0da`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1802ee033`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1802ee0da`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x1802eddec`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x1802eddec`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_HandleUnrecognizedFileSystem` at `0x1802ede16`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_HandleUnrecognizedFileSystem` at `0x1802ede16`

## pseudocode

```c
__int64 __fastcall CEnumFiles::InitAndFindFirstRetry(
        CEnumFiles *this,
        const unsigned __int16 *a2,
        struct tagWIN32_FIND_DATA_EX *a3,
        HWND hwndParent,
        struct IUnknown *a5,
        int a6)
{
  struct tagWIN32_FIND_DATA_EX *v7; // r14
  int inited; // ebx
  unsigned int DriveNumberW; // eax
  CEnumFiles *v12; // rcx
  CMountPoint *v13; // r14
  CEnumFiles *v14; // rcx
  unsigned int v15; // r9d
  char IsEnabled; // al
  Shell32Instance *v17; // rcx
  HINSTANCE v18; // rax
  HINSTANCE v19; // rax
  __int64 v20; // r8
  BOOL *v21; // r9
  CEnumFiles *v22; // rcx
  DWORD FileAttributesW; // eax
  DWORD v24; // r14d
  const unsigned __int16 *v25; // rdx
  int v26; // eax
  int v27; // r14d
  BOOL v28; // r12d
  HINSTANCE v29; // rax
  BOOL *v30; // r9
  __int64 v32; // [rsp+30h] [rbp-D0h] BYREF
  struct tagWIN32_FIND_DATA_EX *v33; // [rsp+38h] [rbp-C8h]
  LPVOID ppv[2]; // [rsp+40h] [rbp-C0h] BYREF
  TASKDIALOGCONFIG pTaskConfig; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v36[264]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR Buffer[128]; // [rsp+300h] [rbp+200h] BYREF

  v7 = a3;
  v33 = a3;
  inited = CEnumFiles::_InitEnumeration(this, a2, 0, 0, a3);
  if ( inited >= 0 )
    return (unsigned int)inited;
  HIDWORD(v32) = 0;
  if ( PathIsUNCW(a2) || (DriveNumberW = PathGetDriveNumberW(a2), (unsigned int)IsDisconnectedNetDrive(DriveNumberW)) )
  {
    LODWORD(v32) = 1;
    inited = CEnumFiles::_RetryNetwork(this, hwndParent, a5, a2, (int *)&v32, v7);
    goto LABEL_24;
  }
  LODWORD(v32) = 0;
  if ( hwndParent )
  {
    if ( PathRetryRemovable(inited, a2) )
      inited = CEnumFiles::InitAndFindFirstRemovable(this, a2, v7, hwndParent, a5);
    if ( CEnumFiles::s_IsUnformattedMediaResult(inited, a2, (int *)&v32 + 1) )
    {
      ppv[0] = 0;
      if ( (int)CMountPoint::GetMountPoint((unsigned __int64)a2, 1, (struct CMtPtLocal *)ppv) >= 0 )
      {
        v13 = (CMountPoint *)ppv[0];
        if ( (*(unsigned int (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 464LL))(ppv[0]) )
        {
          inited = -2147023673;
          if ( !CEnumFiles::_IsMountedFolder(v14, a2, v36, v15) )
          {
            if ( IsDesktopPresent() )
            {
              LOBYTE(v20) = *(_BYTE *)a2;
              if ( !(unsigned int)SHELL32_HandleUnrecognizedFileSystem(hwndParent, a5, v20, v13) )
                inited = CEnumFiles::_InitEnumeration(this, a2, 0, 0, v33);
            }
            goto LABEL_22;
          }
          GoModal(hwndParent, a5, 1);
          IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl);
          v17 = (CEnumFiles *)((char *)this + 152);
          if ( IsEnabled )
          {
            v18 = Shell32Instance::get(v17);
            MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short____0(
              v18,
              hwndParent,
              (LPCWSTR)0x1013,
              (LPCWSTR)0x1012,
              0x10030u,
              (__int64)v36);
          }
          else
          {
            v19 = Shell32Instance::get(v17);
            ShellMessageBoxW(v19, hwndParent, (LPCWSTR)0x1013, (LPCWSTR)0x1012, 0x10030u, v36, v32);
          }
        }
        else
        {
          if ( HIDWORD(v32) )
          {
LABEL_22:
            CMountPoint::Release(v13);
            v7 = v33;
            goto LABEL_24;
          }
          inited = -2147023673;
          GoModal(hwndParent, a5, 1);
          pTaskConfig.cbSize = 160;
          memset_0(&pTaskConfig.hwndParent, 0, 0x9Cu);
          pTaskConfig.hwndParent = hwndParent;
          pTaskConfig.hInstance = Shell32Instance::get((CEnumFiles *)((char *)this + 152));
          pTaskConfig.pszWindowTitle = (PCWSTR)4219;
          pTaskConfig.pszMainInstruction = (PCWSTR)4134;
          pTaskConfig.pszContent = (PCWSTR)4135;
          pTaskConfig.dwCommonButtons = 32;
          pTaskConfig.nDefaultButton = 8;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
            MessageBoxHelper::TaskDialogIndirectScaled_0(&pTaskConfig, 0);
          else
            TaskDialogIndirect(&pTaskConfig, 0, 0, v21);
        }
        GoModal(hwndParent, a5, 0);
        goto LABEL_22;
      }
    }
LABEL_24:
    if ( inited >= 0 )
      return (unsigned int)inited;
  }
  if ( inited == -2147023673 )
    goto LABEL_64;
  if ( inited != -2144927744 && (a6 & 3) != 0 && !(unsigned int)CEnumFiles::_PathExistsWithOutSpec(v12, a2) )
  {
    if ( (unsigned int)CEnumFiles::_PathExistsRoot(v22, a2) )
    {
      inited = CEnumFiles::_OfferToCreateDir(this, hwndParent, a5, a2, a6);
      if ( inited >= 0 )
      {
        inited = CEnumFiles::_InitEnumeration(this, a2, 0, 0, v7);
        if ( inited >= 0 )
          return (unsigned int)inited;
      }
    }
  }
  if ( inited == -2147023673 )
  {
LABEL_64:
    CEnumFiles::_FindClose(this);
    return (unsigned int)inited;
  }
  if ( inited == -2144927744 )
    goto LABEL_63;
  if ( !hwndParent )
    goto LABEL_63;
  if ( (a6 & 0x10) != 0 )
    goto LABEL_63;
  FileAttributesW = GetFileAttributesW(a2);
  ppv[0] = 0;
  v24 = FileAttributesW;
  if ( CoCreateInstance(
         &GUID_c529c7ef_a3af_45f2_8a47_767b33aa5cc0,
         0,
         1u,
         &GUID_fb5ad46a_dd49_470d_8132_6a094056401d,
         ppv) < 0 )
    goto LABEL_63;
  if ( PathIsNetworkPathW(a2)
    && !(*(unsigned int (__fastcall **)(LPVOID, _QWORD, const unsigned __int16 *))(*(_QWORD *)ppv[0] + 32LL))(
          ppv[0],
          (unsigned int)inited,
          a2) )
  {
    if ( PathGetComputerName(a2, v25, v36, 0x100u) >= 0
      && (*(int (__fastcall **)(LPVOID, HWND, unsigned __int16 *, const unsigned __int16 *, int))(*(_QWORD *)ppv[0]
                                                                                                + 24LL))(
           ppv[0],
           hwndParent,
           v36,
           a2,
           inited) < 0 )
    {
      goto LABEL_62;
    }
    CEnumFiles::_FindClose(this);
    v26 = CEnumFiles::_InitEnumeration(this, a2, 0, 0, v33);
    goto LABEL_47;
  }
  if ( inited != -2147024891 )
  {
    if ( (inited & 0x1FFF0000) != 0x70000 || (v27 = (unsigned __int16)inited, (unsigned __int16)inited == 40) )
      v27 = 5;
    goto LABEL_53;
  }
  if ( v24 == -1 || (v24 & 6) == 6 || PathIsNetworkPathW(a2) )
  {
    if ( a6 < 0 )
      goto LABEL_62;
    v27 = 5;
LABEL_53:
    v28 = 0;
    PathIsUNCW(a2);
    if ( v27 != 3 )
      v28 = HIDWORD(v32) != 0;
    GoModal(hwndParent, a5, 1);
    if ( v28 )
    {
      v29 = Shell32Instance::get((CEnumFiles *)((char *)this + 152));
      LoadStringW(v29, 0x1928u, Buffer, 128);
      if ( (int)StringCchPrintfW(v36, 0x80u, Buffer, a2) >= 0 )
      {
        pTaskConfig.cbSize = 160;
        memset_0(&pTaskConfig.hwndParent, 0, 0x9Cu);
        pTaskConfig.hwndParent = hwndParent;
        pTaskConfig.hInstance = Shell32Instance::get((CEnumFiles *)((char *)this + 152));
        pTaskConfig.pszMainInstruction = v36;
        pTaskConfig.pszWindowTitle = (PCWSTR)4219;
        pTaskConfig.pszContent = (PCWSTR)6441;
        pTaskConfig.dwCommonButtons = 32;
        pTaskConfig.nDefaultButton = 8;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
          MessageBoxHelper::TaskDialogIndirectScaled_0(&pTaskConfig, 0);
        else
          TaskDialogIndirect(&pTaskConfig, 0, 0, v30);
      }
    }
    else
    {
      SHEnumErrorMessageBox(hwndParent, v32);
    }
    GoModal(hwndParent, a5, 0);
    inited = -2147023673;
    goto LABEL_62;
  }
  v26 = CEnumFiles::_RetryWithElevation(this, hwndParent, a5, a2, v33);
LABEL_47:
  inited = v26;
LABEL_62:
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
LABEL_63:
  if ( inited < 0 )
    goto LABEL_64;
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1802edc30  push    rbp
0x1802edc32  push    rbx
0x1802edc33  push    rsi
0x1802edc34  push    rdi
0x1802edc35  push    r12
0x1802edc37  push    r13
0x1802edc39  push    r14
0x1802edc3b  push    r15
0x1802edc3d  lea     rbp, [rsp-318h]
0x1802edc45  sub     rsp, 418h
0x1802edc4c  mov     rax, cs:__security_cookie
0x1802edc53  xor     rax, rsp
0x1802edc56  mov     [rbp+350h+var_50], rax
0x1802edc5d  mov     r13, [rbp+350h+arg_20]
0x1802edc64  mov     rsi, r9
0x1802edc67  mov     r14, r8
0x1802edc6a  mov     [rsp+450h+var_418], r8
0x1802edc6f  mov     qword ptr [rsp+450h+fuStyle], r8; struct tagWIN32_FIND_DATA_EX *
0x1802edc74  xor     r9d, r9d; int
0x1802edc77  xor     r8d, r8d; unsigned __int16 *
0x1802edc7a  mov     rdi, rdx
0x1802edc7d  mov     r15, rcx
0x1802edc80  call    ?_InitEnumeration@CEnumFiles@@AEAAJPEBG0HPEAUtagWIN32_FIND_DATA_EX@@@Z; CEnumFiles::_InitEnumeration(ushort const *,ushort const *,int,tagWIN32_FIND_DATA_EX *)
0x1802edc85  xor     r12d, r12d
0x1802edc88  mov     ebx, eax
0x1802edc8a  test    eax, eax
0x1802edc8c  jns     loc_1802EE2AB
0x1802edc92  mov     rcx, rdi; pszPath
0x1802edc95  mov     [rsp+450h+var_41C], r12d
0x1802edc9a  call    cs:__imp_PathIsUNCW
0x1802edca1  nop     dword ptr [rax+rax+00h]
0x1802edca6  test    eax, eax
0x1802edca8  jnz     loc_1802EDF09
0x1802edcae  mov     rcx, rdi; pszPath
0x1802edcb1  call    cs:__imp_PathGetDriveNumberW
0x1802edcb8  nop     dword ptr [rax+rax+00h]
0x1802edcbd  mov     ecx, eax
0x1802edcbf  call    IsDisconnectedNetDrive
0x1802edcc4  test    eax, eax
0x1802edcc6  jnz     loc_1802EDF09
0x1802edccc  mov     [rsp+450h+var_420], r12d
0x1802edcd1  test    rsi, rsi
0x1802edcd4  jz      loc_1802EDF43
0x1802edcda  mov     rdx, rdi; unsigned __int16 *
0x1802edcdd  mov     ecx, ebx; int
0x1802edcdf  call    ?PathRetryRemovable@@YAHJPEBG@Z; PathRetryRemovable(long,ushort const *)
0x1802edce4  test    eax, eax
0x1802edce6  jz      short loc_1802EDD00
0x1802edce8  mov     r9, rsi; hWndParent
0x1802edceb  mov     qword ptr [rsp+450h+fuStyle], r13; struct IUnknown *
0x1802edcf0  mov     r8, r14; struct tagWIN32_FIND_DATA_EX *
0x1802edcf3  mov     rdx, rdi; lpFileName
0x1802edcf6  mov     rcx, r15; this
0x1802edcf9  call    ?InitAndFindFirstRemovable@CEnumFiles@@UEAAJPEBGPEAUtagWIN32_FIND_DATA_EX@@PEAUHWND__@@PEAUIUnknown@@@Z; CEnumFiles::InitAndFindFirstRemovable(ushort const *,tagWIN32_FIND_DATA_EX *,HWND__ *,IUnknown *)
0x1802edcfe  mov     ebx, eax
0x1802edd00  lea     r8, [rsp+450h+var_41C]; int *
0x1802edd05  mov     rdx, rdi; unsigned __int16 *
0x1802edd08  mov     ecx, ebx; int
0x1802edd0a  call    ?s_IsUnformattedMediaResult@CEnumFiles@@CAHJPEBGPEAH@Z; CEnumFiles::s_IsUnformattedMediaResult(long,ushort const *,int *)
0x1802edd0f  test    eax, eax
0x1802edd11  jz      loc_1802EDF3B
0x1802edd17  lea     r8, [rsp+450h+ppv]
0x1802edd1c  mov     [rsp+450h+ppv], r12
0x1802edd21  mov     edx, 1
0x1802edd26  mov     rcx, rdi
0x1802edd29  call    ?GetMountPoint@CMountPoint@@SAJPEBGW4AddToDriveLetterCache@@PEAPEAV1@@Z; CMountPoint::GetMountPoint(ushort const *,AddToDriveLetterCache,CMountPoint * *)
0x1802edd2e  test    eax, eax
0x1802edd30  js      loc_1802EDF3B
0x1802edd36  mov     r14, [rsp+450h+ppv]
0x1802edd3b  mov     rcx, r14
0x1802edd3e  mov     rax, [r14]
0x1802edd41  mov     rax, [rax+1D0h]
0x1802edd48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802edd4d  test    eax, eax
0x1802edd4f  jz      loc_1802EDE4C
0x1802edd55  lea     r8, [rbp+350h+var_360]; unsigned __int16 *
0x1802edd59  mov     rdx, rdi; unsigned __int16 *
0x1802edd5c  mov     ebx, 800704C7h
0x1802edd61  call    ?_IsMountedFolder@CEnumFiles@@AEAAHPEBGPEAGI@Z; CEnumFiles::_IsMountedFolder(ushort const *,ushort *,uint)
0x1802edd66  test    eax, eax
0x1802edd68  jz      loc_1802EDDFD
0x1802edd6e  mov     r8d, 1
0x1802edd74  mov     rdx, r13
0x1802edd77  mov     rcx, rsi
0x1802edd7a  call    GoModal
0x1802edd7f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x1802edd86  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x1802edd8b  lea     rcx, [r15+98h]; this
0x1802edd92  test    al, al
0x1802edd94  jz      short loc_1802EDDC6
0x1802edd96  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1802edd9b  mov     r9d, 1012h; lpcTitle
0x1802edda1  mov     rcx, rax; hAppInst
0x1802edda4  lea     rax, [rbp+350h+var_360]
0x1802edda8  mov     rdx, rsi; hWnd
0x1802eddab  mov     [rsp+450h+var_428], rax; __int64
0x1802eddb0  mov     [rsp+450h+fuStyle], 10030h; UINT
0x1802eddb8  lea     r8d, [r9+1]; lpcText
0x1802eddbc  call    MessageBoxHelper__ShellMessageBoxTextScaled_unsigned_short____0
0x1802eddc1  jmp     loc_1802EDEEC
0x1802eddc6  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1802eddcb  mov     r9d, 1012h; lpcTitle
0x1802eddd1  mov     rcx, rax; hAppInst
0x1802eddd4  lea     rax, [rbp+350h+var_360]
0x1802eddd8  mov     rdx, rsi; hWnd
0x1802edddb  mov     [rsp+450h+var_428], rax
0x1802edde0  mov     [rsp+450h+fuStyle], 10030h; fuStyle
0x1802edde8  lea     r8d, [r9+1]; lpcText
0x1802eddec  call    cs:__imp_ShellMessageBoxW
0x1802eddf3  nop     dword ptr [rax+rax+00h]
0x1802eddf8  jmp     loc_1802EDEEC
0x1802eddfd  call    ?IsDesktopPresent@@YA_NXZ; IsDesktopPresent(void)
0x1802ede02  test    al, al
0x1802ede04  jz      loc_1802EDEFA
0x1802ede0a  mov     r8b, [rdi]
0x1802ede0d  mov     r9, r14
0x1802ede10  mov     rdx, r13
0x1802ede13  mov     rcx, rsi
0x1802ede16  call    cs:__imp_SHELL32_HandleUnrecognizedFileSystem
0x1802ede1d  nop     dword ptr [rax+rax+00h]
0x1802ede22  test    eax, eax
0x1802ede24  jnz     loc_1802EDEFA
0x1802ede2a  mov     rax, [rsp+450h+var_418]
0x1802ede2f  xor     r9d, r9d; int
0x1802ede32  xor     r8d, r8d; unsigned __int16 *
0x1802ede35  mov     qword ptr [rsp+450h+fuStyle], rax; struct tagWIN32_FIND_DATA_EX *
0x1802ede3a  mov     rdx, rdi; lpFileName
0x1802ede3d  mov     rcx, r15; this
0x1802ede40  call    ?_InitEnumeration@CEnumFiles@@AEAAJPEBG0HPEAUtagWIN32_FIND_DATA_EX@@@Z; CEnumFiles::_InitEnumeration(ushort const *,ushort const *,int,tagWIN32_FIND_DATA_EX *)
0x1802ede45  mov     ebx, eax
0x1802ede47  jmp     loc_1802EDEFA
0x1802ede4c  cmp     [rsp+450h+var_41C], r12d
0x1802ede51  jnz     loc_1802EDEFA
0x1802ede57  mov     r8d, 1
0x1802ede5d  mov     rdx, r13
0x1802ede60  mov     rcx, rsi
0x1802ede63  mov     ebx, 800704C7h
0x1802ede68  call    GoModal
0x1802ede6d  xor     edx, edx; Val
0x1802ede6f  mov     [rsp+450h+pTaskConfig.cbSize], 0A0h
0x1802ede77  mov     r8d, 9Ch; Size
0x1802ede7d  lea     rcx, [rsp+450h+pTaskConfig.hwndParent]; void *
0x1802ede82  call    memset_0
0x1802ede87  lea     rcx, [r15+98h]; this
0x1802ede8e  mov     [rsp+450h+pTaskConfig.hwndParent], rsi
0x1802ede93  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1802ede98  mov     [rsp+450h+pTaskConfig.hInstance], rax
0x1802ede9d  mov     [rsp+450h+pTaskConfig.pszWindowTitle], 107Bh
0x1802edea6  mov     [rsp+450h+pTaskConfig.pszMainInstruction], 1026h
0x1802edeaf  mov     [rbp+350h+pTaskConfig.pszContent], 1027h
0x1802edeb7  mov     [rsp+450h+pTaskConfig.dwCommonButtons], 20h ; ' '
0x1802edebf  mov     [rbp+350h+pTaskConfig.nDefaultButton], 8
0x1802edec6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x1802edecd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x1802eded2  xor     edx, edx; pnButton
0x1802eded4  lea     rcx, [rsp+450h+pTaskConfig]; pTaskConfig
0x1802eded9  test    al, al
0x1802ededb  jz      short loc_1802EDEE4
0x1802ededd  call    MessageBoxHelper__TaskDialogIndirectScaled_0
0x1802edee2  jmp     short loc_1802EDEEC
0x1802edee4  xor     r8d, r8d; pnRadioButton
0x1802edee7  call    TaskDialogIndirect
0x1802edeec  xor     r8d, r8d
0x1802edeef  mov     rdx, r13
0x1802edef2  mov     rcx, rsi
0x1802edef5  call    GoModal
0x1802edefa  mov     rcx, r14; this
0x1802edefd  call    ?Release@CMountPoint@@QEAAKXZ; CMountPoint::Release(void)
0x1802edf02  mov     r14, [rsp+450h+var_418]
0x1802edf07  jmp     short loc_1802EDF3B
0x1802edf09  lea     rax, [rsp+450h+var_420]
0x1802edf0e  mov     [rsp+450h+var_428], r14; struct tagWIN32_FIND_DATA_EX *
0x1802edf13  mov     r9, rdi; unsigned __int16 *
0x1802edf16  mov     qword ptr [rsp+450h+fuStyle], rax; int *
0x1802edf1b  mov     r8, r13; struct IUnknown *
0x1802edf1e  mov     [rsp+450h+var_420], 1
0x1802edf26  mov     rdx, rsi; hwndParent
0x1802edf29  mov     rcx, r15; this
0x1802edf2c  call    ?_RetryNetwork@CEnumFiles@@AEAAJPEAUHWND__@@PEAUIUnknown@@PEBGPEAHPEAUtagWIN32_FIND_DATA_EX@@@Z; CEnumFiles::_RetryNetwork(HWND__ *,IUnknown *,ushort const *,int *,tagWIN32_FIND_DATA_EX *)
0x1802edf31  mov     ebx, eax
0x1802edf33  mov     eax, [rsp+450h+var_420]
0x1802edf37  mov     [rsp+450h+var_420], eax
0x1802edf3b  test    ebx, ebx
0x1802edf3d  jns     loc_1802EE2AB
0x1802edf43  mov     r12d, [rbp+350h+arg_28]
0x1802edf4a  cmp     ebx, 800704C7h
0x1802edf50  jz      loc_1802EE2A3
0x1802edf56  cmp     ebx, 80270000h
0x1802edf5c  jz      short loc_1802EDFB8
0x1802edf5e  test    r12b, 3
0x1802edf62  jz      short loc_1802EDFB8
0x1802edf64  mov     rdx, rdi; unsigned __int16 *
0x1802edf67  call    ?_PathExistsWithOutSpec@CEnumFiles@@AEAAHPEBG@Z; CEnumFiles::_PathExistsWithOutSpec(ushort const *)
0x1802edf6c  test    eax, eax
0x1802edf6e  jnz     short loc_1802EDFB8
0x1802edf70  mov     rdx, rdi; unsigned __int16 *
0x1802edf73  call    ?_PathExistsRoot@CEnumFiles@@AEAAHPEBG@Z; CEnumFiles::_PathExistsRoot(ushort const *)
0x1802edf78  test    eax, eax
0x1802edf7a  jz      short loc_1802EDFB8
0x1802edf7c  mov     r9, rdi; unsigned __int16 *
0x1802edf7f  mov     [rsp+450h+fuStyle], r12d; unsigned int
0x1802edf84  mov     r8, r13; struct IUnknown *
0x1802edf87  mov     rdx, rsi; HWND
0x1802edf8a  mov     rcx, r15; this
0x1802edf8d  call    ?_OfferToCreateDir@CEnumFiles@@AEAAJPEAUHWND__@@PEAUIUnknown@@PEBGK@Z; CEnumFiles::_OfferToCreateDir(HWND__ *,IUnknown *,ushort const *,ulong)
0x1802edf92  mov     ebx, eax
0x1802edf94  test    eax, eax
0x1802edf96  js      short loc_1802EDFB8
0x1802edf98  xor     r9d, r9d; int
0x1802edf9b  mov     qword ptr [rsp+450h+fuStyle], r14; struct tagWIN32_FIND_DATA_EX *
0x1802edfa0  xor     r8d, r8d; unsigned __int16 *
0x1802edfa3  mov     rdx, rdi; lpFileName
0x1802edfa6  mov     rcx, r15; this
0x1802edfa9  call    ?_InitEnumeration@CEnumFiles@@AEAAJPEBG0HPEAUtagWIN32_FIND_DATA_EX@@@Z; CEnumFiles::_InitEnumeration(ushort const *,ushort const *,int,tagWIN32_FIND_DATA_EX *)
0x1802edfae  mov     ebx, eax
0x1802edfb0  test    eax, eax
0x1802edfb2  jns     loc_1802EE2AB
0x1802edfb8  cmp     ebx, 800704C7h
0x1802edfbe  jz      loc_1802EE2A3
0x1802edfc4  cmp     ebx, 80270000h
0x1802edfca  jz      loc_1802EE29F
0x1802edfd0  test    rsi, rsi
0x1802edfd3  jz      loc_1802EE29F
0x1802edfd9  test    r12b, 10h
0x1802edfdd  jnz     loc_1802EE29F
0x1802edfe3  mov     rcx, rdi; lpFileName
0x1802edfe6  call    cs:__imp_GetFileAttributesW
0x1802edfed  nop     dword ptr [rax+rax+00h]
0x1802edff2  xor     edx, edx; pUnkOuter
0x1802edff4  mov     [rsp+450h+ppv], 0
0x1802edffd  mov     r14d, eax
0x1802ee000  lea     r9, _GUID_fb5ad46a_dd49_470d_8132_6a094056401d; riid
0x1802ee007  lea     rax, [rsp+450h+ppv]
0x1802ee00c  lea     rcx, _GUID_c529c7ef_a3af_45f2_8a47_767b33aa5cc0; rclsid
0x1802ee013  mov     qword ptr [rsp+450h+fuStyle], rax; ppv
0x1802ee018  lea     r8d, [rdx+1]; dwClsContext
0x1802ee01c  call    cs:__imp_CoCreateInstance
0x1802ee023  nop     dword ptr [rax+rax+00h]
0x1802ee028  test    eax, eax
0x1802ee02a  js      loc_1802EE29F
0x1802ee030  mov     rcx, rdi; pszPath
0x1802ee033  call    cs:__imp_PathIsNetworkPathW
0x1802ee03a  nop     dword ptr [rax+rax+00h]
0x1802ee03f  test    eax, eax
0x1802ee041  jz      short loc_1802EE0BF
0x1802ee043  mov     rcx, [rsp+450h+ppv]
0x1802ee048  mov     r8, rdi
0x1802ee04b  mov     edx, ebx
0x1802ee04d  mov     rax, [rcx]
0x1802ee050  mov     rax, [rax+20h]
0x1802ee054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802ee059  test    eax, eax
0x1802ee05b  jnz     short loc_1802EE0BF
0x1802ee05d  mov     r9d, 100h; unsigned int
0x1802ee063  lea     r8, [rbp+350h+var_360]; unsigned __int16 *
0x1802ee067  mov     rcx, rdi; unsigned __int16 *
0x1802ee06a  call    ?PathGetComputerName@@YAJPEBG0PEAGI@Z; PathGetComputerName(ushort const *,ushort const *,ushort *,uint)
0x1802ee06f  test    eax, eax
0x1802ee071  js      short loc_1802EE09A
0x1802ee073  mov     rcx, [rsp+450h+ppv]
0x1802ee078  lea     r8, [rbp+350h+var_360]
0x1802ee07c  mov     r9, rdi
0x1802ee07f  mov     [rsp+450h+fuStyle], ebx
0x1802ee083  mov     rdx, rsi
0x1802ee086  mov     rax, [rcx]
0x1802ee089  mov     rax, [rax+18h]
0x1802ee08d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802ee092  test    eax, eax
0x1802ee094  js      loc_1802EE28E
0x1802ee09a  mov     rcx, r15; this
0x1802ee09d  call    ?_FindClose@CEnumFiles@@AEAAXXZ; CEnumFiles::_FindClose(void)
0x1802ee0a2  mov     rax, [rsp+450h+var_418]
0x1802ee0a7  xor     r9d, r9d; int
0x1802ee0aa  xor     r8d, r8d; unsigned __int16 *
0x1802ee0ad  mov     qword ptr [rsp+450h+fuStyle], rax; struct tagWIN32_FIND_DATA_EX *
0x1802ee0b2  mov     rdx, rdi; lpFileName
0x1802ee0b5  mov     rcx, r15; this
0x1802ee0b8  call    ?_InitEnumeration@CEnumFiles@@AEAAJPEBG0HPEAUtagWIN32_FIND_DATA_EX@@@Z; CEnumFiles::_InitEnumeration(ushort const *,ushort const *,int,tagWIN32_FIND_DATA_EX *)
0x1802ee0bd  jmp     short loc_1802EE105
0x1802ee0bf  cmp     ebx, 80070005h
0x1802ee0c5  jnz     short loc_1802EE11B
0x1802ee0c7  cmp     r14d, 0FFFFFFFFh
0x1802ee0cb  jz      short loc_1802EE10C
0x1802ee0cd  and     r14d, 6
0x1802ee0d1  cmp     r14b, 6
0x1802ee0d5  jz      short loc_1802EE10C
0x1802ee0d7  mov     rcx, rdi; pszPath
0x1802ee0da  call    cs:__imp_PathIsNetworkPathW
0x1802ee0e1  nop     dword ptr [rax+rax+00h]
0x1802ee0e6  test    eax, eax
0x1802ee0e8  jnz     short loc_1802EE10C
0x1802ee0ea  mov     rax, [rsp+450h+var_418]
0x1802ee0ef  mov     r9, rdi; lpFileName
0x1802ee0f2  mov     r8, r13; struct IUnknown *
0x1802ee0f5  mov     qword ptr [rsp+450h+fuStyle], rax; struct tagWIN32_FIND_DATA_EX *
0x1802ee0fa  mov     rdx, rsi; HWND
0x1802ee0fd  mov     rcx, r15; this
0x1802ee100  call    ?_RetryWithElevation@CEnumFiles@@AEAAJPEAUHWND__@@PEAUIUnknown@@PEBGPEAUtagWIN32_FIND_DATA_EX@@@Z; CEnumFiles::_RetryWithElevation(HWND__ *,IUnknown *,ushort const *,tagWIN32_FIND_DATA_EX *)
0x1802ee105  mov     ebx, eax
0x1802ee107  jmp     loc_1802EE28E
  ... truncated ...
```
