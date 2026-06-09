# NamespaceRestrictionHelper::GetKnownFolderIdFromItem(IShellItem *,_GUID *)

- ea: `0x1802b5bc8`
- end: `0x1802b5f33`
- name: `?GetKnownFolderIdFromItem@NamespaceRestrictionHelper@@AEAAJPEAUIShellItem@@PEAU_GUID@@@Z`
- size: `875`
- prototype: `int(NamespaceRestrictionHelper *__hidden this, struct IShellItem *, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1802b7344`

## callees

- `0x18003c5e4`
- `0x18004f684`
- `0x18028cb14`
- `0x1802a9430`
- `0x1802b47ac`
- `0x1802b5290`
- `0x1802b5bc8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802b5c6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802b5e38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802b5eba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802b5edd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802b5ef3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802b5f14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802b5c6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802b5e38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802b5eba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802b5edd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802b5ef3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802b5f14`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x1802b5c95`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x1802b5c95`
- `api-ms-win-shell-namespace-l1-1-0!ILIsEqual` at `0x1802b5ea1`
- `api-ms-win-shell-namespace-l1-1-0!ILIsEqual` at `0x1802b5ea1`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x1802b5e81`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x1802b5e81`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall NamespaceRestrictionHelper::GetKnownFolderIdFromItem(
        NamespaceRestrictionHelper *this,
        struct IShellItem *a2,
        struct _GUID *a3)
{
  int v5; // eax
  struct IBindCtx *v6; // rdx
  const struct _GUID *v7; // r8
  HRESULT UnaliasedItem; // ebx
  __int64 v10; // rdx
  void *v11; // rcx
  enum FOLDER_ENUM_MODE v12; // ecx
  ITEMIDLIST *v13; // rcx
  const KNOWNFOLDERID *const *i; // rdi
  struct _GUID *v15; // rsi
  HRESULT v16; // ebx
  ITEMIDLIST *v17; // rcx
  ITEMIDLIST *v18; // rcx
  ITEMIDLIST *v19; // rcx
  bool v20; // zf
  void *v21; // rcx
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  LPCITEMIDLIST pidl1; // [rsp+28h] [rbp-D8h] BYREF
  IUnknown *punk; // [rsp+30h] [rbp-D0h] BYREF
  LPCITEMIDLIST pidl2; // [rsp+38h] [rbp-C8h] BYREF
  void *p_pv; // [rsp+40h] [rbp-C0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+48h] [rbp-B8h] BYREF
  char v28; // [rsp+50h] [rbp-B0h]
  _QWORD v29[26]; // [rsp+60h] [rbp-A0h] BYREF
  char v30; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  *a3 = GUID_NULL;
  v5 = NamespaceRestrictionHelper::EnsureManager(this);
  UnaliasedItem = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20B,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\NamespaceRestrictionHelper.h",
      (const char *)(unsigned int)v5,
      (int)pv);
    return (unsigned int)UnaliasedItem;
  }
  pv = 0;
  punk = 0;
  UnaliasedItem = GetUnaliasedItem(a2, v6, v7, (void **)&punk);
  if ( UnaliasedItem < 0 )
  {
    v10 = 529;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\NamespaceRestrictionHelper.h",
      (const char *)(unsigned int)UnaliasedItem,
      (int)pv);
LABEL_7:
    wil::com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>(&punk);
    v11 = pv;
    pv = 0;
    if ( v11 )
      CoTaskMemFree(v11);
    return (unsigned int)UnaliasedItem;
  }
  p_pv = &pv;
  ppidl = 0;
  v28 = 1;
  UnaliasedItem = SHGetIDListFromObject(punk, &ppidl);
  wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( UnaliasedItem < 0 )
  {
    v10 = 530;
    goto LABEL_6;
  }
  v29[0] = &FOLDERID_Downloads;
  v29[1] = &FOLDERID_Desktop;
  v29[2] = qword_18041D450;
  v29[3] = &FOLDERID_Documents;
  v29[4] = &FOLDERID_Pictures;
  v29[5] = &FOLDERID_SavedPictures;
  v29[6] = &FOLDERID_CameraRoll;
  v29[7] = &FOLDERID_NetworkFolder;
  v29[8] = &FOLDERID_Windows;
  v29[9] = &FOLDERID_ComputerFolder;
  v29[10] = &FOLDERID_RecycleBinFolder;
  v29[11] = &FOLDERID_SearchHistory;
  v29[12] = &FOLDERID_SearchHome;
  v29[13] = &FOLDERID_PrintersFolder;
  v29[14] = &FOLDERID_Music;
  v29[15] = &FOLDERID_Videos;
  v29[16] = &FOLDERID_Device;
  v29[17] = &FOLDERID_RecordedCalls;
  v29[18] = &FOLDERID_Objects3D;
  v29[19] = &FOLDERID_OneDrive;
  v29[20] = &FOLDERID_Public;
  v29[21] = &FOLDERID_Profile;
  v29[22] = &FOLDERID_UsersLibraries;
  v29[23] = &FOLDERID_LocalAppData;
  v29[24] = &FOLDERID_AppsFolder;
  v29[25] = &FOLDERID_RoamingAppData;
  pidl1 = 0;
  p_pv = &pidl1;
  ppidl = 0;
  v28 = 1;
  UnaliasedItem = ConvertIDListEnumMode(
                    v12,
                    (const struct _ITEMIDLIST_ABSOLUTE *)pv,
                    (struct _ITEMIDLIST_ABSOLUTE **)&ppidl);
  wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( UnaliasedItem < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x236,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\NamespaceRestrictionHelper.h",
      (const char *)(unsigned int)UnaliasedItem,
      (int)pv);
    v13 = (ITEMIDLIST *)pidl1;
    pidl1 = 0;
    if ( v13 )
      CoTaskMemFree(v13);
    goto LABEL_7;
  }
  for ( i = (const KNOWNFOLDERID *const *)v29; i != (const KNOWNFOLDERID *const *)&v30; ++i )
  {
    pidl2 = 0;
    p_pv = &pidl2;
    ppidl = 0;
    v28 = 1;
    v15 = (struct _GUID *)*i;
    v16 = SHGetKnownFolderIDList(*i, 0x5000u, 0, &ppidl);
    wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
    if ( v16 >= 0 && ILIsEqual(pidl1, pidl2) )
    {
      *a3 = *v15;
      v18 = (ITEMIDLIST *)pidl2;
      pidl2 = 0;
      if ( v18 )
        CoTaskMemFree(v18);
      break;
    }
    v17 = (ITEMIDLIST *)pidl2;
    pidl2 = 0;
    if ( v17 )
      CoTaskMemFree(v17);
  }
  v19 = (ITEMIDLIST *)pidl1;
  v20 = pidl1 == 0;
  pidl1 = 0;
  if ( !v20 )
    CoTaskMemFree(v19);
  wil::com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>(&punk);
  v21 = pv;
  v20 = pv == 0;
  pv = 0;
  if ( !v20 )
    CoTaskMemFree(v21);
  return 0;
}

```

## disassembly

```asm
0x1802b5bc8  mov     [rsp-8+arg_18], rbx
0x1802b5bcd  push    rbp
0x1802b5bce  push    rsi
0x1802b5bcf  push    rdi
0x1802b5bd0  push    r14
0x1802b5bd2  push    r15
0x1802b5bd4  lea     rbp, [rsp-30h]
0x1802b5bd9  sub     rsp, 130h
0x1802b5be0  mov     r14, r8
0x1802b5be3  mov     rdi, rdx
0x1802b5be6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1802b5bed  movdqu  xmmword ptr [r8], xmm0
0x1802b5bf2  call    ?EnsureManager@NamespaceRestrictionHelper@@AEAAJXZ; NamespaceRestrictionHelper::EnsureManager(void)
0x1802b5bf7  mov     ebx, eax
0x1802b5bf9  xor     r15d, r15d
0x1802b5bfc  test    eax, eax
0x1802b5bfe  jns     short loc_1802B5C1F
0x1802b5c00  mov     rcx, [rbp+58h]; this
0x1802b5c04  mov     r9d, eax; char *
0x1802b5c07  lea     r8, aOnecoreuapInte_9; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1802b5c0e  mov     edx, 20Bh; void *
0x1802b5c13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b5c18  mov     eax, ebx
0x1802b5c1a  jmp     loc_1802B5F1C
0x1802b5c1f  mov     [rsp+150h+pv], r15; int
0x1802b5c24  mov     [rsp+150h+punk], r15
0x1802b5c29  lea     r9, [rsp+150h+punk]; void **
0x1802b5c2e  mov     rcx, rdi; struct IShellItem *
0x1802b5c31  call    ?GetUnaliasedItem@@YAJPEAUIShellItem@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z; GetUnaliasedItem(IShellItem *,IBindCtx *,_GUID const &,void * *)
0x1802b5c36  mov     ebx, eax
0x1802b5c38  test    eax, eax
0x1802b5c3a  jns     short loc_1802B5C77
0x1802b5c3c  mov     edx, 211h; void *
0x1802b5c41  lea     r8, aOnecoreuapInte_9; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1802b5c48  mov     r9d, ebx; char *
0x1802b5c4b  mov     rcx, [rbp+58h]; this
0x1802b5c4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b5c54  nop
0x1802b5c55  lea     rcx, [rsp+150h+punk]
0x1802b5c5a  call    ??1?$com_ptr_t@UICoreWindowSite@Core@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>(void)
0x1802b5c5f  nop
0x1802b5c60  mov     rcx, [rsp+150h+pv]; pv
0x1802b5c65  mov     [rsp+150h+pv], r15
0x1802b5c6a  test    rcx, rcx
0x1802b5c6d  jz      short loc_1802B5C18
0x1802b5c6f  call    cs:__imp_CoTaskMemFree
0x1802b5c75  jmp     short loc_1802B5C18
0x1802b5c77  lea     rax, [rsp+150h+pv]
0x1802b5c7c  mov     [rsp+150h+var_110], rax
0x1802b5c81  mov     [rsp+150h+ppidl], r15
0x1802b5c86  mov     [rsp+150h+var_100], 1
0x1802b5c8b  lea     rdx, [rsp+150h+ppidl]; ppidl
0x1802b5c90  mov     rcx, [rsp+150h+punk]; punk
0x1802b5c95  call    cs:__imp_SHGetIDListFromObject
0x1802b5c9b  mov     ebx, eax
0x1802b5c9d  lea     rcx, [rsp+150h+var_110]
0x1802b5ca2  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1802b5ca7  test    ebx, ebx
0x1802b5ca9  jns     short loc_1802B5CB2
0x1802b5cab  mov     edx, 212h
0x1802b5cb0  jmp     short loc_1802B5C41
0x1802b5cb2  lea     rax, FOLDERID_Downloads
0x1802b5cb9  mov     [rsp+150h+var_F0], rax
0x1802b5cbe  lea     rax, FOLDERID_Desktop
0x1802b5cc5  mov     [rsp+150h+var_E8], rax
0x1802b5cca  lea     rax, qword_18041D450
0x1802b5cd1  mov     [rsp+150h+var_E0], rax
0x1802b5cd6  lea     rax, FOLDERID_Documents
0x1802b5cdd  mov     [rsp+150h+var_D8], rax
0x1802b5ce2  lea     rax, FOLDERID_Pictures
0x1802b5ce9  mov     [rbp+50h+var_D0], rax
0x1802b5ced  lea     rax, FOLDERID_SavedPictures
0x1802b5cf4  mov     [rbp+50h+var_C8], rax
0x1802b5cf8  lea     rax, FOLDERID_CameraRoll
0x1802b5cff  mov     [rbp+50h+var_C0], rax
0x1802b5d03  lea     rax, FOLDERID_NetworkFolder
0x1802b5d0a  mov     [rbp+50h+var_B8], rax
0x1802b5d0e  lea     rax, FOLDERID_Windows
0x1802b5d15  mov     [rbp+50h+var_B0], rax
0x1802b5d19  lea     rax, FOLDERID_ComputerFolder
0x1802b5d20  mov     [rbp+50h+var_A8], rax
0x1802b5d24  lea     rax, FOLDERID_RecycleBinFolder
0x1802b5d2b  mov     [rbp+50h+var_A0], rax
0x1802b5d2f  lea     rax, FOLDERID_SearchHistory
0x1802b5d36  mov     [rbp+50h+var_98], rax
0x1802b5d3a  lea     rax, FOLDERID_SearchHome
0x1802b5d41  mov     [rbp+50h+var_90], rax
0x1802b5d45  lea     rax, FOLDERID_PrintersFolder
0x1802b5d4c  mov     [rbp+50h+var_88], rax
0x1802b5d50  lea     rax, FOLDERID_Music
0x1802b5d57  mov     [rbp+50h+var_80], rax
0x1802b5d5b  lea     rax, FOLDERID_Videos
0x1802b5d62  mov     [rbp+50h+var_78], rax
0x1802b5d66  lea     rax, FOLDERID_Device
0x1802b5d6d  mov     [rbp+50h+var_70], rax
0x1802b5d71  lea     rax, FOLDERID_RecordedCalls
0x1802b5d78  mov     [rbp+50h+var_68], rax
0x1802b5d7c  lea     rax, FOLDERID_Objects3D
0x1802b5d83  mov     [rbp+50h+var_60], rax
0x1802b5d87  lea     rax, FOLDERID_OneDrive
0x1802b5d8e  mov     [rbp+50h+var_58], rax
0x1802b5d92  lea     rax, FOLDERID_Public
0x1802b5d99  mov     [rbp+50h+var_50], rax
0x1802b5d9d  lea     rax, FOLDERID_Profile
0x1802b5da4  mov     [rbp+50h+var_48], rax
0x1802b5da8  lea     rax, FOLDERID_UsersLibraries
0x1802b5daf  mov     [rbp+50h+var_40], rax
0x1802b5db3  lea     rax, FOLDERID_LocalAppData
0x1802b5dba  mov     [rbp+50h+var_38], rax
0x1802b5dbe  lea     rax, FOLDERID_AppsFolder
0x1802b5dc5  mov     [rbp+50h+var_30], rax
0x1802b5dc9  lea     rax, FOLDERID_RoamingAppData
0x1802b5dd0  mov     [rbp+50h+var_28], rax
0x1802b5dd4  mov     [rsp+150h+pidl1], r15
0x1802b5dd9  lea     rax, [rsp+150h+pidl1]
0x1802b5dde  mov     [rsp+150h+var_110], rax
0x1802b5de3  mov     [rsp+150h+ppidl], r15
0x1802b5de8  mov     [rsp+150h+var_100], 1
0x1802b5ded  lea     r8, [rsp+150h+ppidl]; struct _ITEMIDLIST_ABSOLUTE **
0x1802b5df2  mov     rdx, [rsp+150h+pv]; struct _ITEMIDLIST_ABSOLUTE *
0x1802b5df7  call    ?ConvertIDListEnumMode@@YAJW4FOLDER_ENUM_MODE@@PEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAU2@@Z; ConvertIDListEnumMode(FOLDER_ENUM_MODE,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE * *)
0x1802b5dfc  mov     ebx, eax
0x1802b5dfe  lea     rcx, [rsp+150h+var_110]
0x1802b5e03  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1802b5e08  test    ebx, ebx
0x1802b5e0a  jns     short loc_1802B5E43
0x1802b5e0c  mov     rcx, [rbp+58h]; this
0x1802b5e10  mov     r9d, ebx; char *
0x1802b5e13  lea     r8, aOnecoreuapInte_9; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1802b5e1a  mov     edx, 236h; void *
0x1802b5e1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b5e24  nop
0x1802b5e25  mov     rcx, [rsp+150h+pidl1]; pv
0x1802b5e2a  mov     [rsp+150h+pidl1], r15
0x1802b5e2f  test    rcx, rcx
0x1802b5e32  jz      loc_1802B5C55
0x1802b5e38  call    cs:__imp_CoTaskMemFree
0x1802b5e3e  jmp     loc_1802B5C55
0x1802b5e43  lea     rdi, [rsp+150h+var_F0]
0x1802b5e48  lea     rax, [rbp+50h+var_20]
0x1802b5e4c  cmp     rdi, rax
0x1802b5e4f  jz      loc_1802B5EE4
0x1802b5e55  mov     [rsp+150h+pidl2], r15
0x1802b5e5a  lea     rax, [rsp+150h+pidl2]
0x1802b5e5f  mov     [rsp+150h+var_110], rax
0x1802b5e64  mov     [rsp+150h+ppidl], r15
0x1802b5e69  mov     [rsp+150h+var_100], 1
0x1802b5e6e  mov     rsi, [rdi]
0x1802b5e71  lea     r9, [rsp+150h+ppidl]; ppidl
0x1802b5e76  xor     r8d, r8d; hToken
0x1802b5e79  mov     edx, 5000h; dwFlags
0x1802b5e7e  mov     rcx, rsi; rfid
0x1802b5e81  call    cs:__imp_SHGetKnownFolderIDList
0x1802b5e87  mov     ebx, eax
0x1802b5e89  lea     rcx, [rsp+150h+var_110]
0x1802b5e8e  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1802b5e93  test    ebx, ebx
0x1802b5e95  js      short loc_1802B5EAB
0x1802b5e97  mov     rdx, [rsp+150h+pidl2]; pidl2
0x1802b5e9c  mov     rcx, [rsp+150h+pidl1]; pidl1
0x1802b5ea1  call    cs:__imp_ILIsEqual
0x1802b5ea7  test    eax, eax
0x1802b5ea9  jnz     short loc_1802B5EC6
0x1802b5eab  mov     rcx, [rsp+150h+pidl2]; pv
0x1802b5eb0  mov     [rsp+150h+pidl2], r15
0x1802b5eb5  test    rcx, rcx
0x1802b5eb8  jz      short loc_1802B5EC0
0x1802b5eba  call    cs:__imp_CoTaskMemFree
0x1802b5ec0  add     rdi, 8
0x1802b5ec4  jmp     short loc_1802B5E48
0x1802b5ec6  movups  xmm0, xmmword ptr [rsi]
0x1802b5ec9  movdqu  xmmword ptr [r14], xmm0
0x1802b5ece  mov     rcx, [rsp+150h+pidl2]; pv
0x1802b5ed3  mov     [rsp+150h+pidl2], r15
0x1802b5ed8  test    rcx, rcx
0x1802b5edb  jz      short loc_1802B5EE4
0x1802b5edd  call    cs:__imp_CoTaskMemFree
0x1802b5ee3  nop
0x1802b5ee4  mov     rcx, [rsp+150h+pidl1]; pv
0x1802b5ee9  test    rcx, rcx
0x1802b5eec  mov     [rsp+150h+pidl1], r15
0x1802b5ef1  jz      short loc_1802B5EFA
0x1802b5ef3  call    cs:__imp_CoTaskMemFree
0x1802b5ef9  nop
0x1802b5efa  lea     rcx, [rsp+150h+punk]
0x1802b5eff  call    ??1?$com_ptr_t@UICoreWindowSite@Core@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>(void)
0x1802b5f04  nop
0x1802b5f05  mov     rcx, [rsp+150h+pv]; pv
0x1802b5f0a  test    rcx, rcx
0x1802b5f0d  mov     [rsp+150h+pv], r15
0x1802b5f12  jz      short loc_1802B5F1A
0x1802b5f14  call    cs:__imp_CoTaskMemFree
0x1802b5f1a  xor     eax, eax
0x1802b5f1c  mov     rbx, [rsp+150h+arg_18]
0x1802b5f24  add     rsp, 130h
0x1802b5f2b  pop     r15
0x1802b5f2d  pop     r14
0x1802b5f2f  pop     rdi
0x1802b5f30  pop     rsi
0x1802b5f31  pop     rbp
0x1802b5f32  retn
```
