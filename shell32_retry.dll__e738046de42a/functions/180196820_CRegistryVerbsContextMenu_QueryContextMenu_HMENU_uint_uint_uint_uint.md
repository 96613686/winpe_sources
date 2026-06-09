# CRegistryVerbsContextMenu::QueryContextMenu(HMENU__ *,uint,uint,uint,uint)

- ea: `0x180196820`
- end: `0x1801971a5`
- name: `?QueryContextMenu@CRegistryVerbsContextMenu@@UEAAJPEAUHMENU__@@IIII@Z`
- size: `2437`
- prototype: `int(CRegistryVerbsContextMenu *__hidden this, HMENU, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180013338`
- `0x180042bc0`
- `0x180043380`
- `0x180043b64`
- `0x180056a84`
- `0x180073848`
- `0x18009c520`
- `0x1800f954c`
- `0x180101a48`
- `0x180107e88`
- `0x180116aa8`
- `0x18013e950`
- `0x18014f32c`
- `0x18016646c`
- `0x1801761f4`
- `0x180196820`
- `0x1801a83d0`
- `0x1801c6988`
- `0x1801c906c`
- `0x180233280`
- `0x1802342fc`
- `0x18037cec8`
- `0x18037d098`
- `0x1805530f4`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180196d2b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180196e15`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180196d2b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180196e15`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x180196b64`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x180196b64`
- `USER32!InsertMenuItemW` at `0x180196f47`
- `USER32!InsertMenuItemW` at `0x180196f47`
- `USER32!SetMenuItemInfoW` at `0x18019708c`
- `USER32!SetMenuItemInfoW` at `0x18019708c`
- `USER32!InsertMenuW` at `0x180196aaa`
- `USER32!InsertMenuW` at `0x180196ea1`
- `USER32!InsertMenuW` at `0x180196f2d`
- `USER32!InsertMenuW` at `0x180196fab`
- `USER32!InsertMenuW` at `0x1801970ef`
- `USER32!InsertMenuW` at `0x180196aaa`
- `USER32!InsertMenuW` at `0x180196ea1`
- `USER32!InsertMenuW` at `0x180196f2d`
- `USER32!InsertMenuW` at `0x180196fab`
- `USER32!InsertMenuW` at `0x1801970ef`
- `USER32!SetMenuDefaultItem` at `0x180196fd7`
- `USER32!SetMenuDefaultItem` at `0x180197168`
- `USER32!SetMenuDefaultItem` at `0x180196fd7`
- `USER32!SetMenuDefaultItem` at `0x180197168`
- `USER32!GetMenuDefaultItem` at `0x180196a0c`
- `USER32!GetMenuDefaultItem` at `0x180197115`
- `USER32!GetMenuDefaultItem` at `0x180196a0c`
- `USER32!GetMenuDefaultItem` at `0x180197115`
- `USER32!GetMenuItemCount` at `0x180196dd8`
- `USER32!GetMenuItemCount` at `0x180196dd8`
- `USER32!CreatePopupMenu` at `0x180196e5e`
- `USER32!CreatePopupMenu` at `0x180196e5e`
- `USER32!DestroyMenu` at `0x180196ed5`
- `USER32!DestroyMenu` at `0x180196fea`
- `USER32!DestroyMenu` at `0x180196ed5`
- `USER32!DestroyMenu` at `0x180196fea`
- `GDI32!DeleteObject` at `0x180196bef`
- `GDI32!DeleteObject` at `0x180196bef`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x18019688f`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x180196966`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x18019688f`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x180196966`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1801968df`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180196d5b`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1801968df`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180196d5b`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_rgshil` at `0x180196b8c`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_rgshil` at `0x180196b98`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_rgshil` at `0x180196b8c`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_rgshil` at `0x180196b98`
- `Windows.Storage!Shell_GetCachedImageIndexW` at `0x180196b77`
- `Windows.Storage!Shell_GetCachedImageIndexW` at `0x180196b77`

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
  CRegistryVerbsContextMenu *v9; // r12
  int v10; // r14d
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
  struct IEnumExplorerCommand *v33; // rsi
  _QWORD *v34; // rax
  _QWORD *v35; // rbx
  void *v36; // rcx
  _QWORD **v37; // rax
  int v38; // eax
  UINT fState; // ecx
  UINT MenuItemCount; // esi
  char v41; // r12
  unsigned int MenuIndexForCanonicalVerb; // eax
  _QWORD **v43; // rax
  HMENU PopupMenu; // rbx
  unsigned int v45; // r14d
  UINT v46; // edx
  BOOL inserted; // ebx
  int v48; // ecx
  HMENU v49; // rdx
  _QWORD **v50; // rax
  UINT v51; // ecx
  unsigned int pvData; // [rsp+20h] [rbp-E0h]
  char v53; // [rsp+40h] [rbp-C0h]
  char v54; // [rsp+41h] [rbp-BFh]
  bool v55; // [rsp+42h] [rbp-BEh]
  bool v56; // [rsp+43h] [rbp-BDh]
  int v57; // [rsp+44h] [rbp-BCh]
  HDSA *v58; // [rsp+48h] [rbp-B8h]
  UINT v59; // [rsp+50h] [rbp-B0h]
  int v62; // [rsp+5Ch] [rbp-A4h]
  int v63; // [rsp+60h] [rbp-A0h]
  CRegistryVerbsContextMenu *v64; // [rsp+68h] [rbp-98h]
  LSTATUS v65; // [rsp+70h] [rbp-90h]
  UINT uItem; // [rsp+74h] [rbp-8Ch]
  int v67; // [rsp+78h] [rbp-88h]
  _DWORD v69[2]; // [rsp+88h] [rbp-78h] BYREF
  struct IEnumExplorerCommand *v70; // [rsp+90h] [rbp-70h] BYREF
  struct IContextMenu *v71; // [rsp+98h] [rbp-68h] BYREF
  MENUITEMINFOW mi; // [rsp+A0h] [rbp-60h] BYREF
  int v73; // [rsp+F0h] [rbp-10h] BYREF
  void *ppvOut; // [rsp+F8h] [rbp-8h] BYREF
  int v75; // [rsp+100h] [rbp+0h] BYREF
  LPWSTR pszIconFile; // [rsp+108h] [rbp+8h] BYREF
  unsigned int v77; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v78; // [rsp+114h] [rbp+14h] BYREF
  int v79; // [rsp+118h] [rbp+18h] BYREF
  WCHAR pszStr1[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v81[80]; // [rsp+1A0h] [rbp+A0h] BYREF

  v8 = this;
  v9 = (CRegistryVerbsContextMenu *)((char *)this - 8);
  v64 = (CRegistryVerbsContextMenu *)((char *)this - 8);
  v10 = 0;
  v11 = a6;
  if ( SHQueryValueExW(*((HKEY *)this + 16), L"NoStaticDefaultVerb", 0, 0, 0, 0) )
  {
    v54 = 1;
  }
  else
  {
    v54 = 0;
    if ( (a6 & 1) != 0 )
      return 0;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ContextMenu_FilterInvokeVerbs>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ContextMenu_FilterInvokeVerbs>::GetImpl'::`2'::impl) )
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
  v62 = 0;
  v57 = 0;
  v63 = 0;
  uItem = a3;
  v55 = 0;
  *((_DWORD *)v8 + 50) = a4;
  *((_DWORD *)v8 + 51) = a6;
  v13 = (CRegistryVerbsContextMenu *)((char *)v8 + 136);
  v58 = (HDSA *)((char *)v8 + 136);
  *((_DWORD *)v8 + 41) = a6;
  v65 = SHQueryValueExW(*((HKEY *)v8 + 16), L"SeparatorBeforeAndAfter", 0, 0, 0, 0);
  v53 = 0;
  v15 = a4;
  v16 = a4;
  v59 = a4;
  if ( a4 <= a5 )
  {
    while ( 1 )
    {
      v17 = v16 - v15;
      if ( v16 - v15 >= CRegistryVerbsContextMenu::_VerbCount(v9) )
      {
LABEL_97:
        v8 = this;
        v13 = (CRegistryVerbArray *)v58;
        goto LABEL_98;
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
      v56 = IsAsyncStateHandler != 0;
      if ( (v11 & 0x4000) != 0 && IsAsyncStateHandler )
        goto LABEL_96;
      IsDefaultVerb = CRegistryVerbsContextMenu::_IsDefaultVerb(v9, v17);
      v67 = IsDefaultVerb;
      v22 = v11 & 1;
      if ( v22 && (v20 || !IsDefaultVerb && GetMenuDefaultItem(a2, 0x400u, 0) != -1) )
      {
        v11 = a6;
        goto LABEL_96;
      }
      v24 = (struct IShellItemArray *)ppvOut;
      ItemPtr = (struct IUnknown **)DSA_GetItemPtr(*v58, v17);
      IUnknown_SetSelection(ItemPtr[18], v24);
      v73 = 0;
      v26 = v58;
      v27 = (_QWORD **)DSA_GetItemPtr(*v58, v17);
      (*(void (__fastcall **)(_QWORD *, int *))(*v27[18] + 72LL))(v27[18], &v73);
      if ( (v73 & 8) != 0 )
      {
        InsertMenuW(a2, v10 + a3, 0xC00u, 0, 0);
        v57 = ++v10;
        goto LABEL_95;
      }
      if ( !(unsigned int)CRegistryVerbsContextMenu::_GetMenuString(v9, v17, a6, v81, pvData) )
        goto LABEL_95;
      mi.cbSize = 80;
      memset_0(&mi.fMask, 0, 0x4Cu);
      *(_QWORD *)&mi.fMask = 323;
      mi.wID = v59;
      mi.dwTypeData = v81;
      mi.cch = 80;
      if ( !v22 )
        break;
LABEL_38:
      mi.fState = 0;
      v75 = 0;
      v37 = (_QWORD **)DSA_GetItemPtr(*v26, v17);
      v11 = a6;
      v38 = (*(__int64 (__fastcall **)(_QWORD *, void *, bool, int *))(*v37[18] + 56LL))(
              v37[18],
              ppvOut,
              ((a6 >> 10) & 1) == 0,
              &v75);
      LODWORD(pszIconFile) = v38;
      if ( v38 >= 0 )
      {
        fState = mi.fState;
        if ( (v75 & 1) != 0 )
          fState = 3;
        mi.fState = fState;
        if ( (v75 & 4) != 0 )
        {
          mi.fState = v75 & 8 | fState;
          v53 = 1;
        }
        if ( (v75 & 2) != 0 )
          goto LABEL_96;
LABEL_47:
        MenuItemCount = v10 + a3;
        v41 = 0;
        v78 = 128;
        if ( CRegistryVerbArray::GetValue((CRegistryVerbArray *)v26, v17, 0, L"Position", 0, pszStr1, &v78) >= 0 )
        {
          if ( StrCmpICW(pszStr1, L"Bottom") )
          {
            if ( !StrCmpICW(pszStr1, L"Top") )
              MenuItemCount = 0;
          }
          else
          {
            v71 = 0;
            if ( IUnknown_QueryService(
                   *((IUnknown **)this + 10),
                   &GUID_76876e96_d981_4546_94f8_15d00ab4ce3c,
                   &GUID_000214e4_0000_0000_c000_000000000046,
                   (void **)&v71) >= 0 )
            {
              v70 = 0;
              if ( ((__int64 (__fastcall *)(struct IContextMenu *, GUID *, struct IEnumExplorerCommand **))v71->lpVtbl->QueryInterface)(
                     v71,
                     &GUID_3172bac3_b591_44d9_a889_d1cba78002af,
                     &v70) >= 0 )
              {
                v77 = 0;
                v79 = 0;
                if ( ((int (__fastcall *)(struct IEnumExplorerCommand *, unsigned int *, int *))v70->lpVtbl->Next)(
                       v70,
                       &v77,
                       &v79) >= 0 )
                {
                  MenuIndexForCanonicalVerb = GetMenuIndexForCanonicalVerb(a2, v71, v77, L"properties");
                  if ( MenuIndexForCanonicalVerb == -1 )
                    MenuItemCount = GetMenuItemCount(a2);
                  else
                    MenuItemCount = MenuIndexForCanonicalVerb - 1;
                  v41 = 1;
                }
                ((void (__fastcall *)(struct IEnumExplorerCommand *))v70->lpVtbl->Release)(v70);
              }
              ((void (__fastcall *)(struct IContextMenu *))v71->lpVtbl->Release)(v71);
            }
          }
        }
        if ( (v73 & 1) != 0 )
        {
          v70 = 0;
          v43 = (_QWORD **)DSA_GetItemPtr(*v26, v17);
          if ( (*(int (__fastcall **)(_QWORD *, struct IEnumExplorerCommand **))(*v43[18] + 80LL))(v43[18], &v70) >= 0 )
          {
            PopupMenu = CreatePopupMenu();
            if ( PopupMenu )
            {
              v45 = CRegistryVerbsContextMenu::_VerbCount(v64) + 16 * v63;
              if ( InsertMenuW(PopupMenu, 0, 0x400u, v45 + a4, (LPCWSTR)&pszStart) )
              {
                CRegistryVerbArray::SetSubMenu((CRegistryVerbArray *)v58, v17, v45, v70, PopupMenu);
                mi.fMask |= 4u;
                mi.hSubMenu = PopupMenu;
                ++v63;
              }
              else
              {
                DestroyMenu(PopupMenu);
              }
              v10 = v57;
            }
            ((void (__fastcall *)(struct IEnumExplorerCommand *))v70->lpVtbl->Release)(v70);
          }
        }
        if ( !v10 && !v65 || CRegistryVerbsContextMenu::_IsValuePresent(v64, v17, L"SeparatorBefore") )
        {
          v46 = MenuItemCount++;
          InsertMenuW(a2, v46, 0xC00u, 0, 0);
          if ( !v41 )
            ++v10;
        }
        inserted = InsertMenuItemW(a2, MenuItemCount, 1, &mi);
        v48 = v10 + 1;
        if ( v41 )
          v48 = v10;
        v10 = v48;
        v57 = v48;
        if ( !v62 )
        {
          uItem = MenuItemCount;
          v55 = v56;
        }
        ++v62;
        if ( CRegistryVerbsContextMenu::_IsValuePresent(v64, v17, L"SeparatorAfter") )
        {
          InsertMenuW(a2, MenuItemCount + 1, 0xC00u, 0, 0);
          if ( !v41 )
          {
            ++v10;
            goto LABEL_80;
          }
        }
        else
        {
LABEL_80:
          v57 = v10;
        }
        if ( v67 && v54 )
          SetMenuDefaultItem(a2, MenuItemCount, 0x400u);
        if ( !inserted && mi.hSubMenu )
          DestroyMenu(mi.hSubMenu);
        v9 = v64;
        if ( (_DWORD)pszIconFile == -2147483638 )
        {
          if ( inserted )
          {
            if ( (int)CRegistryVerbsContextMenu::_StartGetStateTask(v64, v49, v59, v17) < 0 )
            {
              v50 = (_QWORD **)DSA_GetItemPtr(*v58, v17);
              if ( (*(int (__fastcall **)(_QWORD *, void *, __int64, int *))(*v50[18] + 56LL))(v50[18], ppvOut, 1, &v75) >= 0 )
              {
                v51 = (v75 & 3) != 0 ? mi.fState : 0;
                mi.fState = v51;
                if ( (v75 & 4) != 0 )
                {
                  mi.fState = v75 & 8 | v51;
                  v53 = 1;
                  goto LABEL_94;
                }
                if ( (v75 & 3) == 0 )
LABEL_94:
                  SetMenuItemInfoW(a2, MenuItemCount, 1, &mi);
              }
            }
          }
        }
LABEL_95:
        v11 = a6;
        goto LABEL_96;
      }
      if ( v38 == -2147483638 )
      {
        mi.fState = 3;
        goto LABEL_47;
      }
LABEL_96:
      ATL::CComPtrBase<IConflictDialogDataMode>::~CComPtrBase<IConflictDialogDataMode>(&ppvOut);
      v16 = v59 + 1;
      v59 = v16;
      v15 = a4;
      if ( v16 > a5 )
        goto LABEL_97;
    }
    pszIconFile = 0;
    v28 = (_QWORD **)DSA_GetItemPtr(*v58, v17);
    if ( (*(int (__fastcall **)(_QWORD *, void *, LPWSTR *))(*v28[18] + 32LL))(v28[18], ppvOut, &pszIconFile) < 0 )
    {
      if ( (v73 & 0x10) == 0 )
      {
LABEL_37:
        CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&pszIconFile);
        goto LABEL_38;
      }
      if ( !*((_QWORD *)this + 28) && (int)LoadShield((HBITMAP *)this + 28) < 0 )
      {
LABEL_36:
        v26 = v58;
        goto LABEL_37;
      }
      mi.fMask |= 0x80u;
      mi.hbmpItem = (HBITMAP)*((_QWORD *)this + 28);
    }
    else
    {
      v29 = (v73 & 0x10) != 0 ? 0xFFFFFE00 : 0;
      v30 = PathParseIconLocationW(pszIconFile);
      CachedImageIndexW = Shell_GetCachedImageIndexW(pszIconFile, v30, v29 + 1024);
      if ( CachedImageIndexW == -1 )
        goto LABEL_36;
      v70 = 0;
      v69[0] = *(_DWORD *)(Global_WindowsStorage_Untyped_rgshil() + 56);
      v69[1] = *(_DWORD *)(Global_WindowsStorage_Untyped_rgshil() + 60);
      if ( (int)CreateBitmapFromIcon(0, CachedImageIndexW, v32, (unsigned int)v69, (__int64)&v70) < 0 )
        goto LABEL_36;
      mi.fMask |= 0x80u;
      v33 = v70;
      mi.hbmpItem = (HBITMAP)v70;
      v34 = DSA_GetItemPtr(*v58, v17);
      v35 = v34;
      if ( v34 )
      {
        v36 = (void *)v34[19];
        if ( v36 )
          DeleteObject(v36);
        v35[19] = v33;
      }
    }
    v53 = 1;
    goto LABEL_36;
  }
LABEL_98:
  if ( !v65 && v62 )
    InsertMenuW(a2, v10 + a3, 0xC00u, 0, 0);
  if ( v53 )
    SHEnableMenuCheckMarkOrBmp(a2, v14);
  if ( v62
    && GetMenuDefaultItem(a2, 0x400u, 0) == -1
    && (v11 & 0x2020) == 0
    && v54
    && !v55
    && !CRegistryVerbsContextMenu::_IsValuePresent(v9, 0, L"NeverDefault") )
  {
    if ( CRegistryVerbArray::HasDefault(v13, *((HKEY *)v8 + 16)) )
      SetMenuDefaultItem(a2, uItem, 0x400u);
  }
  return (unsigned __int16)(16 * v63 + CRegistryVerbsContextMenu::_VerbCount(v9));
}

```

## disassembly

```asm
0x180196820  push    rbp
0x180196822  push    rbx
0x180196823  push    rsi
0x180196824  push    rdi
0x180196825  push    r12
0x180196827  push    r13
0x180196829  push    r14
0x18019682b  push    r15
0x18019682d  lea     rbp, [rsp-158h]
0x180196835  sub     rsp, 258h
0x18019683c  mov     rax, cs:__security_cookie
0x180196843  xor     rax, rsp
0x180196846  mov     [rbp+190h+var_50], rax
0x18019684d  mov     [rsp+290h+var_23C], r9d
0x180196852  mov     r15d, r8d
0x180196855  mov     [rsp+290h+var_238], r8d
0x18019685a  mov     r13, rdx
0x18019685d  mov     rbx, rcx
0x180196860  mov     [rbp+190h+var_210], rcx
0x180196864  lea     r12, [rcx-8]
0x180196868  mov     [rsp+290h+var_228], r12
0x18019686d  xor     r14d, r14d
0x180196870  mov     [rsp+290h+pcbData], r14; pcbData
0x180196875  mov     [rsp+290h+pvData], r14; pvData
0x18019687a  xor     r9d, r9d; pdwType
0x18019687d  xor     r8d, r8d; pdwReserved
0x180196880  lea     rdx, aNostaticdefaul; "NoStaticDefaultVerb"
0x180196887  mov     rcx, [r12+88h]; hkey
0x18019688f  call    cs:__imp_SHQueryValueExW
0x180196895  lea     edi, [r14+1]
0x180196899  mov     esi, [rbp+190h+arg_28]
0x18019689f  test    eax, eax
0x1801968a1  jz      loc_180196A22
0x1801968a7  mov     [rsp+290h+var_24F], dil
0x1801968ac  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ContextMenu_FilterInvokeVerbs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ContextMenu_FilterInvokeVerbs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ContextMenu_FilterInvokeVerbs> `wil::Feature<__WilFeatureTraits_Feature_ContextMenu_FilterInvokeVerbs>::GetImpl(void)'::`2'::impl
0x1801968b3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ContextMenu_FilterInvokeVerbs@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ContextMenu_FilterInvokeVerbs>::__private_IsEnabled(wil::ReportingKind)
0x1801968b8  test    al, al
0x1801968ba  jz      short loc_18019690F
0x1801968bc  mov     [rbp+190h+ppvOut], r14
0x1801968c0  lea     rcx, [rbp+190h+ppvOut]
0x1801968c4  call    ?InternalRelease@?$ComPtr@UIFileExplorerViewInternal@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFileExplorerViewInternal>::InternalRelease(void)
0x1801968c9  lea     r9, [rbp+190h+ppvOut]; ppvOut
0x1801968cd  lea     r8, _GUID_8515cb42_67d0_433b_b85a_fd1b3f246aec; riid
0x1801968d4  lea     rdx, _GUID_76876e96_d981_4546_94f8_15d00ab4ce3c; guidService
0x1801968db  mov     rcx, [rbx+50h]; punk
0x1801968df  call    cs:__imp_IUnknown_QueryService
0x1801968e5  test    eax, eax
0x1801968e7  js      short loc_180196906
0x1801968e9  mov     rcx, [rbp+190h+ppvOut]
0x1801968ed  mov     rax, [rcx]
0x1801968f0  test    r12, r12
0x1801968f3  lea     rdx, [rbx+40h]
0x1801968f7  jnz     short loc_1801968FC
0x1801968f9  mov     rdx, r14
0x1801968fc  mov     rax, [rax+18h]
0x180196900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180196905  nop
0x180196906  lea     rcx, [rbp+190h+ppvOut]
0x18019690a  call    ?InternalRelease@?$ComPtr@UIFileExplorerViewInternal@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFileExplorerViewInternal>::InternalRelease(void)
0x18019690f  mov     [rsp+290h+var_234], r14d
0x180196914  mov     [rsp+290h+var_24C], r14d
0x180196919  xor     ecx, ecx
0x18019691b  mov     [rsp+290h+var_230], ecx
0x18019691f  mov     [rsp+290h+uItem], r15d
0x180196924  mov     [rsp+290h+var_24E], cl
0x180196928  mov     eax, [rsp+290h+var_23C]
0x18019692c  mov     [rbx+0C8h], eax
0x180196932  mov     [rbx+0CCh], esi
0x180196938  lea     r15, [rbx+88h]
0x18019693f  mov     [rsp+290h+var_248], r15
0x180196944  mov     [r15+1Ch], esi
0x180196948  mov     [rsp+290h+pcbData], rcx; pcbData
0x18019694d  mov     [rsp+290h+pvData], rcx; unsigned int
0x180196952  xor     r9d, r9d; pdwType
0x180196955  xor     r8d, r8d; pdwReserved
0x180196958  lea     rdx, aSeparatorbefor; "SeparatorBeforeAndAfter"
0x18019695f  mov     rcx, [rbx+80h]; hkey
0x180196966  call    cs:__imp_SHQueryValueExW
0x18019696c  mov     [rsp+290h+var_220], eax
0x180196970  mov     [rsp+290h+var_250], 0
0x180196975  mov     ecx, [rsp+290h+var_23C]
0x180196979  mov     eax, ecx
0x18019697b  mov     [rsp+290h+var_240], ecx
0x18019697f  cmp     ecx, [rbp+190h+arg_20]
0x180196985  ja      loc_1801970C4
0x18019698b  mov     r15d, eax
0x18019698e  sub     r15d, ecx
0x180196991  mov     rcx, r12; this
0x180196994  call    ?_VerbCount@CRegistryVerbsContextMenu@@AEAAIXZ; CRegistryVerbsContextMenu::_VerbCount(void)
0x180196999  cmp     r15d, eax
0x18019699c  jnb     loc_1801970BB
0x1801969a2  mov     [rbp+190h+ppvOut], 0
0x1801969aa  mov     edx, r15d; unsigned int
0x1801969ad  mov     rcx, r12; this
0x1801969b0  call    ?ShouldConsiderCurrentFolderAsSelection@CRegistryVerbsContextMenu@@AEAA_NI@Z; CRegistryVerbsContextMenu::ShouldConsiderCurrentFolderAsSelection(uint)
0x1801969b5  mov     r8b, al; bool
0x1801969b8  lea     rdx, [rbp+190h+ppvOut]; struct IShellItemArray **
0x1801969bc  mov     rcx, r12; this
0x1801969bf  call    ?_GetShellItemArray@CRegistryVerbsContextMenu@@AEAAJPEAPEAUIShellItemArray@@_N@Z; CRegistryVerbsContextMenu::_GetShellItemArray(IShellItemArray * *,bool)
0x1801969c4  mov     edx, r15d; unsigned int
0x1801969c7  mov     rcx, r12; this
0x1801969ca  call    ?_IsAsyncStateHandler@CRegistryVerbsContextMenu@@AEAAHI@Z; CRegistryVerbsContextMenu::_IsAsyncStateHandler(uint)
0x1801969cf  mov     ebx, eax
0x1801969d1  test    eax, eax
0x1801969d3  setnz   [rsp+290h+var_24D]
0x1801969d8  bt      esi, 0Eh
0x1801969dc  jnb     short loc_1801969E6
0x1801969de  test    eax, eax
0x1801969e0  jnz     loc_180197098
0x1801969e6  mov     edx, r15d; unsigned int
0x1801969e9  mov     rcx, r12; this
0x1801969ec  call    ?_IsDefaultVerb@CRegistryVerbsContextMenu@@AEAAHI@Z; CRegistryVerbsContextMenu::_IsDefaultVerb(uint)
0x1801969f1  mov     [rsp+290h+var_218], eax
0x1801969f5  and     esi, edi
0x1801969f7  jz      short loc_180196A37
0x1801969f9  test    ebx, ebx
0x1801969fb  jnz     short loc_180196A17
0x1801969fd  test    eax, eax
0x1801969ff  jnz     short loc_180196A37
0x180196a01  xor     r8d, r8d; gmdiFlags
0x180196a04  mov     edx, 400h; fByPos
0x180196a09  mov     rcx, r13; hMenu
0x180196a0c  call    cs:__imp_GetMenuDefaultItem
0x180196a12  cmp     eax, 0FFFFFFFFh
0x180196a15  jz      short loc_180196A37
0x180196a17  mov     esi, [rbp+190h+arg_28]
0x180196a1d  jmp     loc_180197098
0x180196a22  mov     [rsp+290h+var_24F], r14b
0x180196a27  test    dil, sil
0x180196a2a  jz      loc_1801968AC
0x180196a30  xor     eax, eax
0x180196a32  jmp     loc_180197182
0x180196a37  mov     rbx, [rbp+190h+ppvOut]
0x180196a3b  mov     edx, r15d; i
0x180196a3e  mov     rcx, [rsp+290h+var_248]
0x180196a43  mov     rcx, [rcx]; hdsa
0x180196a46  call    DSA_GetItemPtr
0x180196a4b  mov     rdx, rbx; struct IShellItemArray *
0x180196a4e  mov     rcx, [rax+90h]; struct IUnknown *
0x180196a55  call    ?IUnknown_SetSelection@@YAJPEAUIUnknown@@PEAUIShellItemArray@@@Z; IUnknown_SetSelection(IUnknown *,IShellItemArray *)
0x180196a5a  mov     [rbp+190h+var_1A0], 0
0x180196a61  mov     edx, r15d; i
0x180196a64  mov     rbx, [rsp+290h+var_248]
0x180196a69  mov     rcx, [rbx]; hdsa
0x180196a6c  call    DSA_GetItemPtr
0x180196a71  mov     rcx, [rax+90h]
0x180196a78  mov     rax, [rcx]
0x180196a7b  lea     rdx, [rbp+190h+var_1A0]
0x180196a7f  mov     rax, [rax+48h]
0x180196a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180196a88  test    byte ptr [rbp+190h+var_1A0], 8
0x180196a8c  jz      short loc_180196ABD
0x180196a8e  mov     edx, [rsp+290h+var_238]
0x180196a92  add     edx, r14d; uPosition
0x180196a95  mov     [rsp+290h+pvData], 0; lpNewItem
0x180196a9e  xor     r9d, r9d; uIDNewItem
0x180196aa1  mov     r8d, 0C00h; uFlags
0x180196aa7  mov     rcx, r13; hMenu
0x180196aaa  call    cs:__imp_InsertMenuW
0x180196ab0  add     r14d, edi
0x180196ab3  mov     [rsp+290h+var_24C], r14d
0x180196ab8  jmp     loc_180197092
0x180196abd  lea     r9, [rbp+190h+var_F0]; unsigned __int16 *
0x180196ac4  mov     r8d, [rbp+190h+arg_28]; unsigned int
0x180196acb  mov     edx, r15d; unsigned int
0x180196ace  mov     rcx, r12; this
0x180196ad1  call    ?_GetMenuString@CRegistryVerbsContextMenu@@AEAAHIIPEAGI@Z; CRegistryVerbsContextMenu::_GetMenuString(uint,uint,ushort *,uint)
0x180196ad6  test    eax, eax
0x180196ad8  jz      loc_180197092
0x180196ade  mov     [rbp+190h+mi.cbSize], 50h ; 'P'
0x180196ae5  xor     edx, edx; Val
0x180196ae7  lea     r8d, [rdx+4Ch]; Size
0x180196aeb  lea     rcx, [rbp+190h+mi.fMask]; void *
0x180196aef  call    memset_0
0x180196af4  mov     qword ptr [rbp+190h+mi.fMask], 143h
0x180196afc  mov     eax, [rsp+290h+var_240]
0x180196b00  mov     [rbp+190h+mi.wID], eax
0x180196b03  lea     rax, [rbp+190h+var_F0]
0x180196b0a  mov     [rbp+190h+mi.dwTypeData], rax
0x180196b0e  mov     [rbp+190h+mi.cch], 50h ; 'P'
0x180196b15  test    esi, esi
0x180196b17  jnz     loc_180196C44
0x180196b1d  xor     esi, esi
0x180196b1f  mov     [rbp+190h+pszIconFile], rsi
0x180196b23  mov     edx, r15d; i
0x180196b26  mov     rcx, [rbx]; hdsa
0x180196b29  call    DSA_GetItemPtr
0x180196b2e  mov     rcx, [rax+90h]
0x180196b35  mov     rax, [rcx]
0x180196b38  lea     r8, [rbp+190h+pszIconFile]
0x180196b3c  mov     rdx, [rbp+190h+ppvOut]
0x180196b40  mov     rax, [rax+20h]
0x180196b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180196b49  test    eax, eax
0x180196b4b  js      loc_180196BFE
0x180196b51  mov     eax, [rbp+190h+var_1A0]
0x180196b54  and     al, 10h
0x180196b56  neg     al
0x180196b58  sbb     ebx, ebx
0x180196b5a  and     ebx, 0FFFFFE00h
0x180196b60  mov     rcx, [rbp+190h+pszIconFile]; pszIconFile
0x180196b64  call    cs:__imp_PathParseIconLocationW
0x180196b6a  lea     r8d, [rbx+400h]; uIconFlags
0x180196b71  mov     edx, eax; iIconIndex
0x180196b73  mov     rcx, [rbp+190h+pszIconFile]; pszIconPath
0x180196b77  call    cs:__imp_Shell_GetCachedImageIndexW
0x180196b7d  mov     ebx, eax
0x180196b7f  cmp     eax, 0FFFFFFFFh
0x180196b82  jz      loc_180196C36
0x180196b88  mov     [rbp+190h+var_200], rsi
0x180196b8c  call    cs:__imp_Global_WindowsStorage_Untyped_rgshil
0x180196b92  mov     ecx, [rax+38h]
0x180196b95  mov     [rbp+190h+var_208], ecx
0x180196b98  call    cs:__imp_Global_WindowsStorage_Untyped_rgshil
0x180196b9e  mov     ecx, [rax+3Ch]
0x180196ba1  mov     [rbp+190h+var_204], ecx
0x180196ba4  lea     rax, [rbp+190h+var_200]
0x180196ba8  mov     [rsp+290h+pvData], rax
0x180196bad  lea     r9, [rbp+190h+var_208]
0x180196bb1  mov     edx, ebx
0x180196bb3  xor     ecx, ecx
0x180196bb5  call    CreateBitmapFromIcon
0x180196bba  test    eax, eax
0x180196bbc  js      short loc_180196C36
0x180196bbe  bts     [rbp+190h+mi.fMask], 7
0x180196bc3  mov     rsi, [rbp+190h+var_200]
0x180196bc7  mov     [rbp+190h+mi.hbmpItem], rsi
0x180196bcb  mov     edx, r15d; i
0x180196bce  mov     rcx, [rsp+290h+var_248]
0x180196bd3  mov     rcx, [rcx]; hdsa
0x180196bd6  call    DSA_GetItemPtr
0x180196bdb  mov     rbx, rax
0x180196bde  test    rax, rax
0x180196be1  jz      short loc_180196C31
0x180196be3  mov     rcx, [rax+98h]; ho
0x180196bea  test    rcx, rcx
0x180196bed  jz      short loc_180196BF5
0x180196bef  call    cs:__imp_DeleteObject
0x180196bf5  mov     [rbx+98h], rsi
0x180196bfc  jmp     short loc_180196C31
0x180196bfe  test    byte ptr [rbp+190h+var_1A0], 10h
0x180196c02  jz      short loc_180196C3B
0x180196c04  mov     rbx, [rbp+190h+var_210]
0x180196c08  cmp     [rbx+0E0h], rsi
0x180196c0f  jnz     short loc_180196C21
0x180196c11  lea     rcx, [rbx+0E0h]; HBITMAP *
0x180196c18  call    ?LoadShield@@YAJPEAPEAUHBITMAP__@@@Z; LoadShield(HBITMAP__ * *)
0x180196c1d  test    eax, eax
0x180196c1f  js      short loc_180196C36
0x180196c21  bts     [rbp+190h+mi.fMask], 7
0x180196c26  mov     rax, [rbx+0E0h]
0x180196c2d  mov     [rbp+190h+mi.hbmpItem], rax
0x180196c31  mov     [rsp+290h+var_250], dil
0x180196c36  mov     rbx, [rsp+290h+var_248]
0x180196c3b  lea     rcx, [rbp+190h+pszIconFile]
0x180196c3f  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x180196c44  mov     [rbp+190h+mi.fState], 0
0x180196c4b  mov     [rbp+190h+var_190], 0
0x180196c52  mov     edx, r15d; i
0x180196c55  mov     rcx, [rbx]; hdsa
0x180196c58  call    DSA_GetItemPtr
0x180196c5d  mov     rcx, [rax+90h]
0x180196c64  mov     rax, [rcx]
0x180196c67  mov     esi, [rbp+190h+arg_28]
0x180196c6d  mov     r8d, esi
0x180196c70  shr     r8d, 0Ah
0x180196c74  not     r8d
0x180196c77  and     r8d, edi
0x180196c7a  lea     r9, [rbp+190h+var_190]
0x180196c7e  mov     rdx, [rbp+190h+ppvOut]
0x180196c82  mov     rax, [rax+38h]
0x180196c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180196c8b  mov     dword ptr [rbp+190h+pszIconFile], eax
0x180196c8e  test    eax, eax
0x180196c90  js      short loc_180196CC5
0x180196c92  mov     edx, [rbp+190h+var_190]
0x180196c95  test    dil, dl
0x180196c98  mov     ecx, [rbp+190h+mi.fState]
0x180196c9b  mov     eax, 3
0x180196ca0  cmovnz  ecx, eax
0x180196ca3  mov     [rbp+190h+mi.fState], ecx
0x180196ca6  test    dl, 4
0x180196ca9  jz      short loc_180196CBA
0x180196cab  mov     eax, edx
0x180196cad  and     eax, 8
0x180196cb0  or      ecx, eax
0x180196cb2  mov     [rbp+190h+mi.fState], ecx
0x180196cb5  mov     [rsp+290h+var_250], dil
0x180196cba  test    dl, 2
0x180196cbd  jnz     loc_180197098
0x180196cc3  jmp     short loc_180196CD7
0x180196cc5  cmp     eax, 8000000Ah
0x180196cca  jnz     loc_180197098
0x180196cd0  mov     [rbp+190h+mi.fState], 3
0x180196cd7  mov     esi, [rsp+290h+var_238]
0x180196cdb  add     esi, r14d
0x180196cde  xor     r12b, r12b
0x180196ce1  mov     [rbp+190h+var_17C], 80h
0x180196ce8  lea     rax, [rbp+190h+var_17C]
0x180196cec  mov     [rsp+290h+var_260], rax; unsigned int *
  ... truncated ...
```
