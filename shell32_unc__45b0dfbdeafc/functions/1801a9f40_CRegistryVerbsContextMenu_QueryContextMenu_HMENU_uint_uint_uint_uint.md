# CRegistryVerbsContextMenu::QueryContextMenu(HMENU__ *,uint,uint,uint,uint)

- ea: `0x1801a9f40`
- end: `0x1801aa92c`
- name: `?QueryContextMenu@CRegistryVerbsContextMenu@@UEAAJPEAUHMENU__@@IIII@Z`
- size: `2540`
- prototype: `int(CRegistryVerbsContextMenu *__hidden this, HMENU, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18003e704`
- `0x18003ef10`
- `0x18003f6f8`
- `0x180059d58`
- `0x180061968`
- `0x1800621f0`
- `0x180093cd8`
- `0x1800943ac`
- `0x1800b0b5c`
- `0x1800f6cc8`
- `0x180100ee8`
- `0x18010a6c0`
- `0x18014c81c`
- `0x18015f24c`
- `0x180173e48`
- `0x18018774c`
- `0x1801a9f40`
- `0x1801bcd70`
- `0x1801dcad8`
- `0x1801df35c`
- `0x180249490`
- `0x18024a53c`
- `0x1803a25e8`
- `0x1803a27cc`
- `0x18059332c`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801aa45c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801aa55b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801aa45c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801aa55b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x1801aa297`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x1801aa297`
- `USER32!InsertMenuItemW` at `0x1801aa6a8`
- `USER32!InsertMenuItemW` at `0x1801aa6a8`
- `USER32!SetMenuItemInfoW` at `0x1801aa7f9`
- `USER32!SetMenuItemInfoW` at `0x1801aa7f9`
- `USER32!InsertMenuW` at `0x1801aa1dc`
- `USER32!InsertMenuW` at `0x1801aa5f1`
- `USER32!InsertMenuW` at `0x1801aa686`
- `USER32!InsertMenuW` at `0x1801aa70e`
- `USER32!InsertMenuW` at `0x1801aa863`
- `USER32!InsertMenuW` at `0x1801aa1dc`
- `USER32!InsertMenuW` at `0x1801aa5f1`
- `USER32!InsertMenuW` at `0x1801aa686`
- `USER32!InsertMenuW` at `0x1801aa70e`
- `USER32!InsertMenuW` at `0x1801aa863`
- `USER32!SetMenuDefaultItem` at `0x1801aa73d`
- `USER32!SetMenuDefaultItem` at `0x1801aa8e8`
- `USER32!SetMenuDefaultItem` at `0x1801aa73d`
- `USER32!SetMenuDefaultItem` at `0x1801aa8e8`
- `USER32!GetMenuDefaultItem` at `0x1801aa138`
- `USER32!GetMenuDefaultItem` at `0x1801aa88f`
- `USER32!GetMenuDefaultItem` at `0x1801aa138`
- `USER32!GetMenuDefaultItem` at `0x1801aa88f`
- `USER32!GetMenuItemCount` at `0x1801aa516`
- `USER32!GetMenuItemCount` at `0x1801aa516`
- `USER32!DestroyMenu` at `0x1801aa62b`
- `USER32!DestroyMenu` at `0x1801aa756`
- `USER32!DestroyMenu` at `0x1801aa62b`
- `USER32!DestroyMenu` at `0x1801aa756`
- `USER32!CreatePopupMenu` at `0x1801aa5aa`
- `USER32!CreatePopupMenu` at `0x1801aa5aa`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x1801a9fae`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x1801aa08c`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x1801a9fae`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x1801aa08c`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1801aa004`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1801aa493`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1801aa004`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1801aa493`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_rgshil` at `0x1801aa2cb`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_rgshil` at `0x1801aa2de`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_rgshil` at `0x1801aa2cb`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_rgshil` at `0x1801aa2de`
- `Windows.Storage!Shell_GetCachedImageIndexW` at `0x1801aa2b0`
- `Windows.Storage!Shell_GetCachedImageIndexW` at `0x1801aa2b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRegistryVerbsContextMenu::QueryContextMenu(
        CRegistryVerbsContextMenu *this,
        HMENU a2,
        UINT a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6)
{
  CRegistryVerbsContextMenu *v8; // rbx
  CRegistryVerbsContextMenu *v9; // r14
  int v10; // r13d
  __int16 v11; // si
  char *v12; // rdx
  CRegistryVerbArray *v13; // r15
  int v14; // edx
  unsigned int v15; // ecx
  unsigned int v16; // eax
  unsigned int v17; // r15d
  bool ShouldConsiderCurrentFolderAsSelection; // al
  int IsAsyncStateHandler; // eax
  int v20; // ebx
  int IsDefaultVerb; // eax
  int v22; // esi
  struct IShellItemArray *v24; // rbx
  struct IUnknown **ItemPtr; // rax
  HDSA *v26; // rbx
  _QWORD **v27; // rax
  _QWORD **v28; // rax
  unsigned int v29; // ebx
  int v30; // eax
  int CachedImageIndexW; // ebx
  int v32; // r8d
  int BitmapFromIcon; // eax
  _QWORD **v34; // rax
  int v35; // eax
  UINT fState; // ecx
  UINT MenuItemCount; // esi
  unsigned int MenuIndexForCanonicalVerb; // eax
  _QWORD **v39; // rax
  HMENU PopupMenu; // rbx
  unsigned int v41; // r14d
  UINT v42; // edx
  BOOL inserted; // ebx
  int v44; // ecx
  HMENU v45; // rdx
  _QWORD **v46; // rax
  UINT v47; // ecx
  unsigned int pvData; // [rsp+20h] [rbp-E0h]
  char v49; // [rsp+40h] [rbp-C0h]
  char v50; // [rsp+41h] [rbp-BFh]
  char v51; // [rsp+42h] [rbp-BEh]
  bool v52; // [rsp+43h] [rbp-BDh]
  bool v53; // [rsp+44h] [rbp-BCh]
  HDSA *v54; // [rsp+48h] [rbp-B8h]
  UINT v55; // [rsp+50h] [rbp-B0h]
  int v58; // [rsp+5Ch] [rbp-A4h]
  int v59; // [rsp+60h] [rbp-A0h]
  LSTATUS v60; // [rsp+64h] [rbp-9Ch]
  UINT uItem; // [rsp+68h] [rbp-98h]
  int v62; // [rsp+6Ch] [rbp-94h]
  _DWORD v64[2]; // [rsp+78h] [rbp-88h] BYREF
  CRegistryVerbsContextMenu *v65; // [rsp+80h] [rbp-80h]
  HBITMAP v66; // [rsp+88h] [rbp-78h] BYREF
  struct IContextMenu *v67; // [rsp+90h] [rbp-70h] BYREF
  MENUITEMINFOW mi; // [rsp+A0h] [rbp-60h] BYREF
  int v69; // [rsp+F0h] [rbp-10h] BYREF
  void *ppvOut; // [rsp+F8h] [rbp-8h] BYREF
  int v71; // [rsp+100h] [rbp+0h] BYREF
  LPWSTR pszIconFile; // [rsp+108h] [rbp+8h] BYREF
  unsigned int v73; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v74; // [rsp+114h] [rbp+14h] BYREF
  int v75; // [rsp+118h] [rbp+18h] BYREF
  WCHAR pszStr1[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v77[80]; // [rsp+1A0h] [rbp+A0h] BYREF

  v8 = this;
  v9 = (CRegistryVerbsContextMenu *)((char *)this - 8);
  v65 = (CRegistryVerbsContextMenu *)((char *)this - 8);
  v10 = 0;
  v11 = a6;
  if ( SHQueryValueExW(*((HKEY *)this + 16), L"NoStaticDefaultVerb", 0, 0, 0, 0) )
  {
    v51 = 1;
  }
  else
  {
    v51 = 0;
    if ( (a6 & 1) != 0 )
      return 0;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ContextMenu_FilterInvokeVerbs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ContextMenu_FilterInvokeVerbs>::GetImpl'::`2'::impl) )
  {
    ppvOut = 0;
    Microsoft::WRL::ComPtr<IFileExplorerViewInternal>::InternalRelease(&ppvOut);
    if ( IUnknown_QueryService(
           *((IUnknown **)v8 + 10),
           &GUID_76876e96_d981_4546_94f8_15d00ab4ce3c,
           &GUID_8515cb42_67d0_433b_b85a_fd1b3f246aec,
           &ppvOut) >= 0 )
    {
      v12 = (char *)v8 + 64;
      if ( !v9 )
        v12 = 0;
      (*(void (__fastcall **)(void *, char *))(*(_QWORD *)ppvOut + 24LL))(ppvOut, v12);
    }
    Microsoft::WRL::ComPtr<IFileExplorerViewInternal>::InternalRelease(&ppvOut);
  }
  v58 = 0;
  v59 = 0;
  uItem = a3;
  v52 = 0;
  *((_DWORD *)v8 + 50) = a4;
  *((_DWORD *)v8 + 51) = a6;
  v13 = (CRegistryVerbsContextMenu *)((char *)v8 + 136);
  v54 = (HDSA *)((char *)v8 + 136);
  *((_DWORD *)v8 + 41) = a6;
  v60 = SHQueryValueExW(*((HKEY *)v8 + 16), L"SeparatorBeforeAndAfter", 0, 0, 0, 0);
  v49 = 0;
  v15 = a4;
  v16 = a4;
  v55 = a4;
  if ( a4 <= a5 )
  {
    while ( 1 )
    {
      v17 = v16 - v15;
      if ( v16 - v15 >= CRegistryVerbsContextMenu::_VerbCount(v9) )
      {
LABEL_92:
        v8 = this;
        v13 = (CRegistryVerbArray *)v54;
        goto LABEL_93;
      }
      ppvOut = 0;
      ShouldConsiderCurrentFolderAsSelection = CRegistryVerbsContextMenu::ShouldConsiderCurrentFolderAsSelection(
                                                 v9,
                                                 v17);
      CRegistryVerbsContextMenu::_GetShellItemArray(
        v9,
        (struct IShellItemArray **)&ppvOut,
        ShouldConsiderCurrentFolderAsSelection);
      IsAsyncStateHandler = CRegistryVerbsContextMenu::_IsAsyncStateHandler(v9, v17);
      v20 = IsAsyncStateHandler;
      v53 = IsAsyncStateHandler != 0;
      if ( (v11 & 0x4000) != 0 && IsAsyncStateHandler )
        goto LABEL_91;
      IsDefaultVerb = CRegistryVerbsContextMenu::_IsDefaultVerb(v9, v17);
      v62 = IsDefaultVerb;
      v22 = v11 & 1;
      if ( v22 && (v20 || !IsDefaultVerb && GetMenuDefaultItem(a2, 0x400u, 0) != -1) )
      {
        v11 = a6;
        goto LABEL_91;
      }
      v24 = (struct IShellItemArray *)ppvOut;
      ItemPtr = (struct IUnknown **)DSA_GetItemPtr(*v54, v17);
      IUnknown_SetSelection(ItemPtr[18], v24);
      v69 = 0;
      v26 = v54;
      v27 = (_QWORD **)DSA_GetItemPtr(*v54, v17);
      (*(void (__fastcall **)(_QWORD *, int *))(*v27[18] + 72LL))(v27[18], &v69);
      if ( (v69 & 8) != 0 )
      {
        InsertMenuW(a2, v10 + a3, 0xC00u, 0, 0);
        ++v10;
        goto LABEL_90;
      }
      if ( !(unsigned int)CRegistryVerbsContextMenu::_GetMenuString(v9, v17, a6, v77, pvData) )
        goto LABEL_90;
      mi.cbSize = 80;
      memset_0(&mi.fMask, 0, 0x4Cu);
      *(_QWORD *)&mi.fMask = 323;
      mi.wID = v55;
      mi.dwTypeData = v77;
      mi.cch = 80;
      if ( !v22 )
        break;
LABEL_34:
      mi.fState = 0;
      v71 = 0;
      v34 = (_QWORD **)DSA_GetItemPtr(*v26, v17);
      v11 = a6;
      v35 = (*(__int64 (__fastcall **)(_QWORD *, void *, bool, int *))(*v34[18] + 56LL))(
              v34[18],
              ppvOut,
              ((a6 >> 10) & 1) == 0,
              &v71);
      LODWORD(pszIconFile) = v35;
      if ( v35 >= 0 )
      {
        fState = mi.fState;
        if ( (v71 & 1) != 0 )
          fState = 3;
        mi.fState = fState;
        if ( (v71 & 4) != 0 )
        {
          mi.fState = v71 & 8 | fState;
          v49 = 1;
        }
        if ( (v71 & 2) != 0 )
          goto LABEL_91;
LABEL_43:
        MenuItemCount = v10 + a3;
        v50 = 0;
        v74 = 128;
        if ( CRegistryVerbArray::GetValue((CRegistryVerbArray *)v26, v17, 0, L"Position", 0, pszStr1, &v74) >= 0 )
        {
          if ( StrCmpICW(pszStr1, L"Bottom") )
          {
            if ( !StrCmpICW(pszStr1, L"Top") )
              MenuItemCount = 0;
          }
          else
          {
            v67 = 0;
            if ( IUnknown_QueryService(
                   *((IUnknown **)this + 10),
                   &GUID_76876e96_d981_4546_94f8_15d00ab4ce3c,
                   &GUID_000214e4_0000_0000_c000_000000000046,
                   (void **)&v67) >= 0 )
            {
              v66 = 0;
              if ( ((__int64 (__fastcall *)(struct IContextMenu *, GUID *, HBITMAP *))v67->lpVtbl->QueryInterface)(
                     v67,
                     &GUID_3172bac3_b591_44d9_a889_d1cba78002af,
                     &v66) >= 0 )
              {
                v73 = 0;
                v75 = 0;
                if ( (*(int (__fastcall **)(HBITMAP, unsigned int *, int *))(*(_QWORD *)v66 + 24LL))(v66, &v73, &v75) >= 0 )
                {
                  MenuIndexForCanonicalVerb = GetMenuIndexForCanonicalVerb(a2, v67, v73, L"properties");
                  if ( MenuIndexForCanonicalVerb == -1 )
                    MenuItemCount = GetMenuItemCount(a2);
                  else
                    MenuItemCount = MenuIndexForCanonicalVerb - 1;
                  v50 = 1;
                }
                (*(void (__fastcall **)(HBITMAP))(*(_QWORD *)v66 + 16LL))(v66);
              }
              ((void (__fastcall *)(struct IContextMenu *))v67->lpVtbl->Release)(v67);
            }
          }
        }
        if ( (v69 & 1) != 0 )
        {
          v66 = 0;
          v39 = (_QWORD **)DSA_GetItemPtr(*v26, v17);
          if ( (*(int (__fastcall **)(_QWORD *, HBITMAP *))(*v39[18] + 80LL))(v39[18], &v66) >= 0 )
          {
            PopupMenu = CreatePopupMenu();
            if ( PopupMenu )
            {
              v41 = CRegistryVerbsContextMenu::_VerbCount(v9) + 16 * v59;
              if ( InsertMenuW(PopupMenu, 0, 0x400u, v41 + a4, &pszStart) )
              {
                CRegistryVerbArray::SetSubMenu(
                  (CRegistryVerbArray *)v54,
                  v17,
                  v41,
                  (struct IEnumExplorerCommand *)v66,
                  PopupMenu);
                mi.fMask |= 4u;
                mi.hSubMenu = PopupMenu;
                ++v59;
              }
              else
              {
                DestroyMenu(PopupMenu);
              }
              v9 = v65;
            }
            (*(void (__fastcall **)(HBITMAP))(*(_QWORD *)v66 + 16LL))(v66);
          }
        }
        if ( !v10 && !v60 || CRegistryVerbsContextMenu::_IsValuePresent(v9, v17, L"SeparatorBefore") )
        {
          v42 = MenuItemCount++;
          InsertMenuW(a2, v42, 0xC00u, 0, 0);
          if ( !v50 )
            ++v10;
        }
        inserted = InsertMenuItemW(a2, MenuItemCount, 1, &mi);
        v44 = v10 + 1;
        if ( v50 )
          v44 = v10;
        v10 = v44;
        if ( !v58 )
        {
          uItem = MenuItemCount;
          v52 = v53;
        }
        ++v58;
        if ( CRegistryVerbsContextMenu::_IsValuePresent(v9, v17, L"SeparatorAfter") )
        {
          InsertMenuW(a2, MenuItemCount + 1, 0xC00u, 0, 0);
          if ( !v50 )
            ++v10;
        }
        if ( v62 && v51 )
          SetMenuDefaultItem(a2, MenuItemCount, 0x400u);
        if ( !inserted && mi.hSubMenu )
          DestroyMenu(mi.hSubMenu);
        if ( (_DWORD)pszIconFile == -2147483638 )
        {
          if ( inserted )
          {
            if ( (int)CRegistryVerbsContextMenu::_StartGetStateTask(v9, v45, v55, v17) < 0 )
            {
              v46 = (_QWORD **)DSA_GetItemPtr(*v54, v17);
              if ( (*(int (__fastcall **)(_QWORD *, void *, __int64, int *))(*v46[18] + 56LL))(v46[18], ppvOut, 1, &v71) >= 0 )
              {
                v47 = (v71 & 3) != 0 ? mi.fState : 0;
                mi.fState = v47;
                if ( (v71 & 4) != 0 )
                {
                  mi.fState = v71 & 8 | v47;
                  v49 = 1;
                  goto LABEL_89;
                }
                if ( (v71 & 3) == 0 )
LABEL_89:
                  SetMenuItemInfoW(a2, MenuItemCount, 1, &mi);
              }
            }
          }
        }
LABEL_90:
        v11 = a6;
        goto LABEL_91;
      }
      if ( v35 == -2147483638 )
      {
        mi.fState = 3;
        goto LABEL_43;
      }
LABEL_91:
      ATL::CComPtrBase<IConflictDialogDataMode>::~CComPtrBase<IConflictDialogDataMode>(&ppvOut);
      v16 = v55 + 1;
      v55 = v16;
      v15 = a4;
      if ( v16 > a5 )
        goto LABEL_92;
    }
    pszIconFile = 0;
    v28 = (_QWORD **)DSA_GetItemPtr(*v54, v17);
    if ( (*(int (__fastcall **)(_QWORD *, void *, LPWSTR *))(*v28[18] + 32LL))(v28[18], ppvOut, &pszIconFile) < 0 )
    {
      if ( (v69 & 0x10) == 0 )
      {
LABEL_33:
        CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&pszIconFile);
        goto LABEL_34;
      }
      if ( *((_QWORD *)this + 28) || (int)LoadShield((HBITMAP *)this + 28) >= 0 )
      {
        mi.fMask |= 0x80u;
        mi.hbmpItem = (HBITMAP)*((_QWORD *)this + 28);
        v49 = 1;
      }
    }
    else
    {
      v29 = (v69 & 0x10) != 0 ? 0xFFFFFE00 : 0;
      v30 = PathParseIconLocationW(pszIconFile);
      CachedImageIndexW = Shell_GetCachedImageIndexW(pszIconFile, v30, v29 + 1024);
      if ( CachedImageIndexW != -1 )
      {
        v66 = 0;
        v64[0] = *(_DWORD *)(Global_WindowsStorage_Untyped_rgshil() + 56);
        v64[1] = *(_DWORD *)(Global_WindowsStorage_Untyped_rgshil() + 60);
        BitmapFromIcon = CreateBitmapFromIcon(0, CachedImageIndexW, v32, (unsigned int)v64, (__int64)&v66);
        v26 = v54;
        if ( BitmapFromIcon >= 0 )
        {
          mi.fMask |= 0x80u;
          mi.hbmpItem = v66;
          CRegistryVerbArray::SetBitmap((CRegistryVerbArray *)v54, v17, v66);
          v49 = 1;
        }
        goto LABEL_33;
      }
    }
    v26 = v54;
    goto LABEL_33;
  }
LABEL_93:
  if ( !v60 && v58 )
    InsertMenuW(a2, v10 + a3, 0xC00u, 0, 0);
  if ( v49 )
    SHEnableMenuCheckMarkOrBmp(a2, v14);
  if ( v58
    && GetMenuDefaultItem(a2, 0x400u, 0) == -1
    && (v11 & 0x2020) == 0
    && v51
    && !v52
    && !CRegistryVerbsContextMenu::_IsValuePresent(v9, 0, L"NeverDefault") )
  {
    if ( CRegistryVerbArray::HasDefault(v13, *((HKEY *)v8 + 16)) )
      SetMenuDefaultItem(a2, uItem, 0x400u);
  }
  return (unsigned __int16)(16 * v59 + CRegistryVerbsContextMenu::_VerbCount(v9));
}

```

## disassembly

```asm
0x1801a9f40  push    rbp
0x1801a9f42  push    rbx
0x1801a9f43  push    rsi
0x1801a9f44  push    rdi
0x1801a9f45  push    r12
0x1801a9f47  push    r13
0x1801a9f49  push    r14
0x1801a9f4b  push    r15
0x1801a9f4d  lea     rbp, [rsp-158h]
0x1801a9f55  sub     rsp, 258h
0x1801a9f5c  mov     rax, cs:__security_cookie
0x1801a9f63  xor     rax, rsp
0x1801a9f66  mov     [rbp+190h+var_50], rax
0x1801a9f6d  mov     [rsp+290h+var_23C], r9d
0x1801a9f72  mov     r15d, r8d
0x1801a9f75  mov     [rsp+290h+var_238], r8d
0x1801a9f7a  mov     r12, rdx
0x1801a9f7d  mov     rbx, rcx
0x1801a9f80  mov     [rsp+290h+var_220], rcx
0x1801a9f85  lea     r14, [rcx-8]
0x1801a9f89  mov     [rbp+190h+var_210], r14
0x1801a9f8d  xor     r13d, r13d
0x1801a9f90  mov     [rsp+290h+pcbData], r13; pcbData
0x1801a9f95  mov     [rsp+290h+pvData], r13; pvData
0x1801a9f9a  xor     r9d, r9d; pdwType
0x1801a9f9d  xor     r8d, r8d; pdwReserved
0x1801a9fa0  lea     rdx, aNostaticdefaul; "NoStaticDefaultVerb"
0x1801a9fa7  mov     rcx, [r14+88h]; hkey
0x1801a9fae  call    cs:__imp_SHQueryValueExW
0x1801a9fb5  nop     dword ptr [rax+rax+00h]
0x1801a9fba  lea     edi, [r13+1]
0x1801a9fbe  mov     esi, [rbp+190h+arg_28]
0x1801a9fc4  test    eax, eax
0x1801a9fc6  jz      loc_1801AA154
0x1801a9fcc  mov     [rsp+290h+var_24E], dil
0x1801a9fd1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ContextMenu_FilterInvokeVerbs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ContextMenu_FilterInvokeVerbs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ContextMenu_FilterInvokeVerbs> `wil::Feature<__WilFeatureTraits_Feature_ContextMenu_FilterInvokeVerbs>::GetImpl(void)'::`2'::impl
0x1801a9fd8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ContextMenu_FilterInvokeVerbs@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ContextMenu_FilterInvokeVerbs>::__private_IsEnabled(wil::ReportingKind)
0x1801a9fdd  test    al, al
0x1801a9fdf  jz      short loc_1801AA03A
0x1801a9fe1  mov     [rbp+190h+ppvOut], r13
0x1801a9fe5  lea     rcx, [rbp+190h+ppvOut]
0x1801a9fe9  call    ?InternalRelease@?$ComPtr@UIFileExplorerViewInternal@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFileExplorerViewInternal>::InternalRelease(void)
0x1801a9fee  lea     r9, [rbp+190h+ppvOut]; ppvOut
0x1801a9ff2  lea     r8, _GUID_8515cb42_67d0_433b_b85a_fd1b3f246aec; riid
0x1801a9ff9  lea     rdx, _GUID_76876e96_d981_4546_94f8_15d00ab4ce3c; guidService
0x1801aa000  mov     rcx, [rbx+50h]; punk
0x1801aa004  call    cs:__imp_IUnknown_QueryService
0x1801aa00b  nop     dword ptr [rax+rax+00h]
0x1801aa010  test    eax, eax
0x1801aa012  js      short loc_1801AA031
0x1801aa014  mov     rcx, [rbp+190h+ppvOut]
0x1801aa018  mov     rax, [rcx]
0x1801aa01b  test    r14, r14
0x1801aa01e  lea     rdx, [rbx+40h]
0x1801aa022  jnz     short loc_1801AA027
0x1801aa024  mov     rdx, r13
0x1801aa027  mov     rax, [rax+18h]
0x1801aa02b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801aa030  nop
0x1801aa031  lea     rcx, [rbp+190h+ppvOut]
0x1801aa035  call    ?InternalRelease@?$ComPtr@UIFileExplorerViewInternal@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFileExplorerViewInternal>::InternalRelease(void)
0x1801aa03a  mov     [rsp+290h+var_234], r13d
0x1801aa03f  xor     ecx, ecx
0x1801aa041  mov     [rsp+290h+var_230], ecx
0x1801aa045  mov     [rsp+290h+uItem], r15d
0x1801aa04a  mov     [rsp+290h+var_24D], cl
0x1801aa04e  mov     eax, [rsp+290h+var_23C]
0x1801aa052  mov     [rbx+0C8h], eax
0x1801aa058  mov     [rbx+0CCh], esi
0x1801aa05e  lea     r15, [rbx+88h]
0x1801aa065  mov     [rsp+290h+var_248], r15
0x1801aa06a  mov     [r15+1Ch], esi
0x1801aa06e  mov     [rsp+290h+pcbData], rcx; pcbData
0x1801aa073  mov     [rsp+290h+pvData], rcx; unsigned int
0x1801aa078  xor     r9d, r9d; pdwType
0x1801aa07b  xor     r8d, r8d; pdwReserved
0x1801aa07e  lea     rdx, aSeparatorbefor; "SeparatorBeforeAndAfter"
0x1801aa085  mov     rcx, [rbx+80h]; hkey
0x1801aa08c  call    cs:__imp_SHQueryValueExW
0x1801aa093  nop     dword ptr [rax+rax+00h]
0x1801aa098  mov     [rsp+290h+var_22C], eax
0x1801aa09c  mov     [rsp+290h+var_250], 0
0x1801aa0a1  mov     ecx, [rsp+290h+var_23C]
0x1801aa0a5  mov     eax, ecx
0x1801aa0a7  mov     [rsp+290h+var_240], ecx
0x1801aa0ab  cmp     ecx, [rbp+190h+arg_20]
0x1801aa0b1  ja      loc_1801AA838
0x1801aa0b7  mov     r15d, eax
0x1801aa0ba  sub     r15d, ecx
0x1801aa0bd  mov     rcx, r14; this
0x1801aa0c0  call    ?_VerbCount@CRegistryVerbsContextMenu@@AEAAIXZ; CRegistryVerbsContextMenu::_VerbCount(void)
0x1801aa0c5  cmp     r15d, eax
0x1801aa0c8  jnb     loc_1801AA82E
0x1801aa0ce  mov     [rbp+190h+ppvOut], 0
0x1801aa0d6  mov     edx, r15d; unsigned int
0x1801aa0d9  mov     rcx, r14; this
0x1801aa0dc  call    ?ShouldConsiderCurrentFolderAsSelection@CRegistryVerbsContextMenu@@AEAA_NI@Z; CRegistryVerbsContextMenu::ShouldConsiderCurrentFolderAsSelection(uint)
0x1801aa0e1  mov     r8b, al; bool
0x1801aa0e4  lea     rdx, [rbp+190h+ppvOut]; struct IShellItemArray **
0x1801aa0e8  mov     rcx, r14; this
0x1801aa0eb  call    ?_GetShellItemArray@CRegistryVerbsContextMenu@@AEAAJPEAPEAUIShellItemArray@@_N@Z; CRegistryVerbsContextMenu::_GetShellItemArray(IShellItemArray * *,bool)
0x1801aa0f0  mov     edx, r15d; unsigned int
0x1801aa0f3  mov     rcx, r14; this
0x1801aa0f6  call    ?_IsAsyncStateHandler@CRegistryVerbsContextMenu@@AEAAHI@Z; CRegistryVerbsContextMenu::_IsAsyncStateHandler(uint)
0x1801aa0fb  mov     ebx, eax
0x1801aa0fd  test    eax, eax
0x1801aa0ff  setnz   [rsp+290h+var_24C]
0x1801aa104  bt      esi, 0Eh
0x1801aa108  jnb     short loc_1801AA112
0x1801aa10a  test    eax, eax
0x1801aa10c  jnz     loc_1801AA80B
0x1801aa112  mov     edx, r15d; unsigned int
0x1801aa115  mov     rcx, r14; this
0x1801aa118  call    ?_IsDefaultVerb@CRegistryVerbsContextMenu@@AEAAHI@Z; CRegistryVerbsContextMenu::_IsDefaultVerb(uint)
0x1801aa11d  mov     [rsp+290h+var_224], eax
0x1801aa121  and     esi, edi
0x1801aa123  jz      short loc_1801AA169
0x1801aa125  test    ebx, ebx
0x1801aa127  jnz     short loc_1801AA149
0x1801aa129  test    eax, eax
0x1801aa12b  jnz     short loc_1801AA169
0x1801aa12d  xor     r8d, r8d; gmdiFlags
0x1801aa130  mov     edx, 400h; fByPos
0x1801aa135  mov     rcx, r12; hMenu
0x1801aa138  call    cs:__imp_GetMenuDefaultItem
0x1801aa13f  nop     dword ptr [rax+rax+00h]
0x1801aa144  cmp     eax, 0FFFFFFFFh
0x1801aa147  jz      short loc_1801AA169
0x1801aa149  mov     esi, [rbp+190h+arg_28]
0x1801aa14f  jmp     loc_1801AA80B
0x1801aa154  mov     [rsp+290h+var_24E], r13b
0x1801aa159  test    dil, sil
0x1801aa15c  jz      loc_1801A9FD1
0x1801aa162  xor     eax, eax
0x1801aa164  jmp     loc_1801AA908
0x1801aa169  mov     rbx, [rbp+190h+ppvOut]
0x1801aa16d  mov     edx, r15d; i
0x1801aa170  mov     rcx, [rsp+290h+var_248]
0x1801aa175  mov     rcx, [rcx]; hdsa
0x1801aa178  call    DSA_GetItemPtr
0x1801aa17d  mov     rdx, rbx; struct IShellItemArray *
0x1801aa180  mov     rcx, [rax+90h]; struct IUnknown *
0x1801aa187  call    ?IUnknown_SetSelection@@YAJPEAUIUnknown@@PEAUIShellItemArray@@@Z; IUnknown_SetSelection(IUnknown *,IShellItemArray *)
0x1801aa18c  mov     [rbp+190h+var_1A0], 0
0x1801aa193  mov     edx, r15d; i
0x1801aa196  mov     rbx, [rsp+290h+var_248]
0x1801aa19b  mov     rcx, [rbx]; hdsa
0x1801aa19e  call    DSA_GetItemPtr
0x1801aa1a3  mov     rcx, [rax+90h]
0x1801aa1aa  mov     rax, [rcx]
0x1801aa1ad  lea     rdx, [rbp+190h+var_1A0]
0x1801aa1b1  mov     rax, [rax+48h]
0x1801aa1b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801aa1ba  test    byte ptr [rbp+190h+var_1A0], 8
0x1801aa1be  jz      short loc_1801AA1F0
0x1801aa1c0  mov     edx, [rsp+290h+var_238]
0x1801aa1c4  add     edx, r13d; uPosition
0x1801aa1c7  mov     [rsp+290h+pvData], 0; lpNewItem
0x1801aa1d0  xor     r9d, r9d; uIDNewItem
0x1801aa1d3  mov     r8d, 0C00h; uFlags
0x1801aa1d9  mov     rcx, r12; hMenu
0x1801aa1dc  call    cs:__imp_InsertMenuW
0x1801aa1e3  nop     dword ptr [rax+rax+00h]
0x1801aa1e8  add     r13d, edi
0x1801aa1eb  jmp     loc_1801AA805
0x1801aa1f0  lea     r9, [rbp+190h+var_F0]; unsigned __int16 *
0x1801aa1f7  mov     r8d, [rbp+190h+arg_28]; unsigned int
0x1801aa1fe  mov     edx, r15d; unsigned int
0x1801aa201  mov     rcx, r14; this
0x1801aa204  call    ?_GetMenuString@CRegistryVerbsContextMenu@@AEAAHIIPEAGI@Z; CRegistryVerbsContextMenu::_GetMenuString(uint,uint,ushort *,uint)
0x1801aa209  test    eax, eax
0x1801aa20b  jz      loc_1801AA805
0x1801aa211  mov     [rbp+190h+mi.cbSize], 50h ; 'P'
0x1801aa218  xor     edx, edx; Val
0x1801aa21a  lea     r8d, [rdx+4Ch]; Size
0x1801aa21e  lea     rcx, [rbp+190h+mi.fMask]; void *
0x1801aa222  call    memset_0
0x1801aa227  mov     qword ptr [rbp+190h+mi.fMask], 143h
0x1801aa22f  mov     eax, [rsp+290h+var_240]
0x1801aa233  mov     [rbp+190h+mi.wID], eax
0x1801aa236  lea     rax, [rbp+190h+var_F0]
0x1801aa23d  mov     [rbp+190h+mi.dwTypeData], rax
0x1801aa241  mov     [rbp+190h+mi.cch], 50h ; 'P'
0x1801aa248  test    esi, esi
0x1801aa24a  jnz     loc_1801AA379
0x1801aa250  xor     esi, esi
0x1801aa252  mov     [rbp+190h+pszIconFile], rsi
0x1801aa256  mov     edx, r15d; i
0x1801aa259  mov     rcx, [rbx]; hdsa
0x1801aa25c  call    DSA_GetItemPtr
0x1801aa261  mov     rcx, [rax+90h]
0x1801aa268  mov     rax, [rcx]
0x1801aa26b  lea     r8, [rbp+190h+pszIconFile]
0x1801aa26f  mov     rdx, [rbp+190h+ppvOut]
0x1801aa273  mov     rax, [rax+20h]
0x1801aa277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801aa27c  test    eax, eax
0x1801aa27e  js      loc_1801AA330
0x1801aa284  mov     eax, [rbp+190h+var_1A0]
0x1801aa287  and     al, 10h
0x1801aa289  neg     al
0x1801aa28b  sbb     ebx, ebx
0x1801aa28d  and     ebx, 0FFFFFE00h
0x1801aa293  mov     rcx, [rbp+190h+pszIconFile]; pszIconFile
0x1801aa297  call    cs:__imp_PathParseIconLocationW
0x1801aa29e  nop     dword ptr [rax+rax+00h]
0x1801aa2a3  lea     r8d, [rbx+400h]; uIconFlags
0x1801aa2aa  mov     edx, eax; iIconIndex
0x1801aa2ac  mov     rcx, [rbp+190h+pszIconFile]; pszIconPath
0x1801aa2b0  call    cs:__imp_Shell_GetCachedImageIndexW
0x1801aa2b7  nop     dword ptr [rax+rax+00h]
0x1801aa2bc  mov     ebx, eax
0x1801aa2be  cmp     eax, 0FFFFFFFFh
0x1801aa2c1  jz      loc_1801AA369
0x1801aa2c7  mov     [rbp+190h+var_208], rsi
0x1801aa2cb  call    cs:__imp_Global_WindowsStorage_Untyped_rgshil
0x1801aa2d2  nop     dword ptr [rax+rax+00h]
0x1801aa2d7  mov     ecx, [rax+38h]
0x1801aa2da  mov     [rsp+290h+var_218], ecx
0x1801aa2de  call    cs:__imp_Global_WindowsStorage_Untyped_rgshil
0x1801aa2e5  nop     dword ptr [rax+rax+00h]
0x1801aa2ea  mov     ecx, [rax+3Ch]
0x1801aa2ed  mov     [rsp+290h+var_214], ecx
0x1801aa2f1  lea     rax, [rbp+190h+var_208]
0x1801aa2f5  mov     [rsp+290h+pvData], rax
0x1801aa2fa  lea     r9, [rsp+290h+var_218]
0x1801aa2ff  mov     edx, ebx
0x1801aa301  xor     ecx, ecx
0x1801aa303  call    CreateBitmapFromIcon
0x1801aa308  mov     rbx, [rsp+290h+var_248]
0x1801aa30d  test    eax, eax
0x1801aa30f  js      short loc_1801AA36E
0x1801aa311  bts     [rbp+190h+mi.fMask], 7
0x1801aa316  mov     r8, [rbp+190h+var_208]; HBITMAP
0x1801aa31a  mov     [rbp+190h+mi.hbmpItem], r8
0x1801aa31e  mov     edx, r15d; int
0x1801aa321  mov     rcx, rbx; this
0x1801aa324  call    ?SetBitmap@CRegistryVerbArray@@QEAAXHPEAUHBITMAP__@@@Z; CRegistryVerbArray::SetBitmap(int,HBITMAP__ *)
0x1801aa329  mov     [rsp+290h+var_250], dil
0x1801aa32e  jmp     short loc_1801AA36E
0x1801aa330  test    byte ptr [rbp+190h+var_1A0], 10h
0x1801aa334  jz      short loc_1801AA36E
0x1801aa336  mov     rbx, [rsp+290h+var_220]
0x1801aa33b  cmp     [rbx+0E0h], rsi
0x1801aa342  jnz     short loc_1801AA354
0x1801aa344  lea     rcx, [rbx+0E0h]; HBITMAP *
0x1801aa34b  call    ?LoadShield@@YAJPEAPEAUHBITMAP__@@@Z; LoadShield(HBITMAP__ * *)
0x1801aa350  test    eax, eax
0x1801aa352  js      short loc_1801AA369
0x1801aa354  bts     [rbp+190h+mi.fMask], 7
0x1801aa359  mov     rax, [rbx+0E0h]
0x1801aa360  mov     [rbp+190h+mi.hbmpItem], rax
0x1801aa364  mov     [rsp+290h+var_250], dil
0x1801aa369  mov     rbx, [rsp+290h+var_248]
0x1801aa36e  lea     rcx, [rbp+190h+pszIconFile]
0x1801aa372  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1801aa377  jmp     short loc_1801AA37B
0x1801aa379  xor     esi, esi
0x1801aa37b  mov     [rbp+190h+mi.fState], esi
0x1801aa37e  mov     [rbp+190h+var_190], esi
0x1801aa381  mov     edx, r15d; i
0x1801aa384  mov     rcx, [rbx]; hdsa
0x1801aa387  call    DSA_GetItemPtr
0x1801aa38c  mov     rcx, [rax+90h]
0x1801aa393  mov     rax, [rcx]
0x1801aa396  mov     esi, [rbp+190h+arg_28]
0x1801aa39c  mov     r8d, esi
0x1801aa39f  shr     r8d, 0Ah
0x1801aa3a3  not     r8d
0x1801aa3a6  and     r8d, edi
0x1801aa3a9  lea     r9, [rbp+190h+var_190]
0x1801aa3ad  mov     rdx, [rbp+190h+ppvOut]
0x1801aa3b1  mov     rax, [rax+38h]
0x1801aa3b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801aa3ba  mov     dword ptr [rbp+190h+pszIconFile], eax
0x1801aa3bd  test    eax, eax
0x1801aa3bf  js      short loc_1801AA3F4
0x1801aa3c1  mov     edx, [rbp+190h+var_190]
0x1801aa3c4  test    dil, dl
0x1801aa3c7  mov     ecx, [rbp+190h+mi.fState]
0x1801aa3ca  mov     eax, 3
0x1801aa3cf  cmovnz  ecx, eax
0x1801aa3d2  mov     [rbp+190h+mi.fState], ecx
0x1801aa3d5  test    dl, 4
0x1801aa3d8  jz      short loc_1801AA3E9
0x1801aa3da  mov     eax, edx
0x1801aa3dc  and     eax, 8
0x1801aa3df  or      ecx, eax
0x1801aa3e1  mov     [rbp+190h+mi.fState], ecx
0x1801aa3e4  mov     [rsp+290h+var_250], dil
0x1801aa3e9  test    dl, 2
0x1801aa3ec  jnz     loc_1801AA80B
0x1801aa3f2  jmp     short loc_1801AA406
0x1801aa3f4  cmp     eax, 8000000Ah
0x1801aa3f9  jnz     loc_1801AA80B
0x1801aa3ff  mov     [rbp+190h+mi.fState], 3
0x1801aa406  mov     esi, [rsp+290h+var_238]
0x1801aa40a  add     esi, r13d
0x1801aa40d  mov     [rsp+290h+var_24F], 0
0x1801aa412  mov     [rbp+190h+var_17C], 80h
  ... truncated ...
```
