# CDesktopFolder::ParseDisplayName(HWND__ *,IBindCtx *,ushort *,ulong *,_ITEMIDLIST_RELATIVE * *,ulong *)

- ea: `0x1800b8ae0`
- end: `0x1800b9911`
- name: `?ParseDisplayName@CDesktopFolder@@UEAAJPEAUHWND__@@PEAUIBindCtx@@PEAGPEAKPEAPEAU_ITEMIDLIST_RELATIVE@@3@Z`
- size: `3633`
- prototype: `int(CDesktopFolder *__hidden this, HWND, struct IBindCtx *, unsigned __int16 *, unsigned int *, struct _ITEMIDLIST_RELATIVE **, unsigned int *)`
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callees

- `0x1800376a0`
- `0x180045230`
- `0x1800551d0`
- `0x180058560`
- `0x18005ee50`
- `0x18005fa70`
- `0x180065a00`
- `0x180067680`
- `0x180067e20`
- `0x1800688f0`
- `0x1800b06e0`
- `0x1800b4100`
- `0x1800b7ae0`
- `0x1800b7dc0`
- `0x1800b7ec0`
- `0x1800b8ae0`
- `0x1800b9ed4`
- `0x1800d38a0`
- `0x180116e60`
- `0x1802485c8`
- `0x1802d7a50`
- `0x1803b1f60`
- `0x1803b1f84`
- `0x1803b243c`
- `0x1803b2ac0`
- `0x1803b2ea5`
- `0x1803b69c5`
- `0x180522194`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!ParseURLW` at `0x1800b9260`
- `api-ms-win-core-url-l1-1-0!ParseURLW` at `0x1800b9260`
- `api-ms-win-core-url-l1-1-0!UrlIsW` at `0x1800b8c7d`
- `api-ms-win-core-url-l1-1-0!UrlIsW` at `0x1800b8c7d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1800b8c64`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1800b8c64`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800b8c3b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800b8c3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b8ebb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b908a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b90a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b9566`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b9877`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180663ac7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180663ad8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b8ebb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b908a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b90a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b9566`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b9877`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180663ac7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180663ad8`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1800b8c0f`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1800b8c0f`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800b8d2d`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800b8d2d`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!IUnknown_GetWindow` at `0x1800b9218`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!IUnknown_GetWindow` at `0x1800b9218`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x1800b8d6b`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x1800b8d6b`

## string_xrefs

- `0x1800b8c03`: `SHBindCtxPathType`
- `0x1800b9331`: `ParseAsCommonItem`
- `0x1800b8e2c`: `UI During Binding`
- `0x1800b96e6`: `ParseAsDurableContentUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CDesktopFolder::ParseDisplayName(
        CDesktopFolder *this,
        HWND a2,
        struct IBindCtx *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        struct _ITEMIDLIST_RELATIVE **a6,
        unsigned int *a7)
{
  const wchar_t *v7; // r12
  struct IBindCtx *v8; // r15
  unsigned int *v10; // rbx
  struct _ITEMIDLIST_ABSOLUTE **v11; // rsi
  unsigned int v12; // r13d
  HRESULT v13; // edi
  HRESULT DWORD; // ebx
  int v15; // ebx
  char v16; // bl
  LPBC v17; // rbx
  LPBC v18; // rdi
  CDummyUnknown *v19; // rax
  CDummyUnknown *v20; // rax
  CDummyUnknown *v21; // rsi
  IShellFolder *v22; // rdi
  HRESULT (__stdcall *ParseDisplayName)(IShellFolder *, HWND, IBindCtx *, LPWSTR, ULONG *, LPITEMIDLIST *, ULONG *); // r14
  LPWSTR v24; // rsi
  const ITEMIDLIST *v25; // r14
  int v26; // eax
  char *v27; // rcx
  LPBC v28; // r15
  const ITEMIDLIST *v29; // rdx
  int v30; // r8d
  __int64 cb; // rcx
  __int64 v32; // rdi
  LPBC v33; // rdx
  __int64 lpVtbl_low; // rcx
  ITEMIDLIST *v35; // rax
  LPITEMIDLIST v36; // rsi
  struct _ITEMIDLIST_ABSOLUTE **v37; // r14
  const struct _GUID *v38; // rcx
  int v39; // esi
  __int64 v40; // rax
  int v41; // ecx
  const wchar_t *v42; // rax
  int v43; // ebx
  __int64 **v44; // rbx
  struct _ITEMIDLIST_ABSOLUTE **v45; // r14
  unsigned int *v46; // r13
  int *v47; // rsi
  int v48; // r13d
  int v50; // eax
  int v51; // edx
  struct _ITEMIDLIST_ABSOLUTE *v52; // rcx
  __int64 v53; // rax
  int v54; // eax
  __int64 v55; // rcx
  __int64 *v56; // rcx
  __int64 v57; // rax
  unsigned int *v58; // [rsp+28h] [rbp-D8h]
  LPBC ppbc; // [rsp+48h] [rbp-B8h] BYREF
  char *v60; // [rsp+50h] [rbp-B0h] BYREF
  void *Src; // [rsp+58h] [rbp-A8h] BYREF
  DWORD value[2]; // [rsp+60h] [rbp-A0h] BYREF
  IPropertyBag *propBag; // [rsp+68h] [rbp-98h] BYREF
  LPWSTR ppwsz; // [rsp+70h] [rbp-90h] BYREF
  IShellFolder *ppshf; // [rsp+78h] [rbp-88h] BYREF
  CDesktopFolder *v66; // [rsp+80h] [rbp-80h]
  PARSEDURLW ppu; // [rsp+88h] [rbp-78h] BYREF
  struct _ITEMIDLIST_ABSOLUTE **v68; // [rsp+B0h] [rbp-50h] BYREF
  HWND v69; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int *v70; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v71[12]; // [rsp+C8h] [rbp-38h] BYREF
  int v72; // [rsp+D4h] [rbp-2Ch]
  HWND phwnd[3]; // [rsp+D8h] [rbp-28h] BYREF
  int v74; // [rsp+F0h] [rbp-10h]
  int v75; // [rsp+F4h] [rbp-Ch]
  char v76[16]; // [rsp+100h] [rbp+0h] BYREF
  const wchar_t *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  DWORD *v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  _BYTE *v82; // [rsp+130h] [rbp+30h]
  __int64 v83; // [rsp+138h] [rbp+38h]
  HWND *v84; // [rsp+140h] [rbp+40h]
  __int64 v85; // [rsp+148h] [rbp+48h]
  HWND *v86; // [rsp+150h] [rbp+50h]
  __int64 v87; // [rsp+158h] [rbp+58h]
  unsigned int **v88; // [rsp+160h] [rbp+60h]
  __int64 v89; // [rsp+168h] [rbp+68h]
  struct _ITEMIDLIST_ABSOLUTE ***v90; // [rsp+170h] [rbp+70h]
  __int64 v91; // [rsp+178h] [rbp+78h]

  v7 = a4;
  v8 = a3;
  *(_QWORD *)v71 = a3;
  v69 = a2;
  v66 = this;
  v10 = a5;
  v11 = a6;
  v68 = a6;
  v70 = a7;
  v12 = 2;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
  {
    if ( a4 )
    {
      v40 = -1;
      do
        ++v40;
      while ( a4[v40] );
      v41 = 2 * v40 + 2;
    }
    else
    {
      v41 = 10;
    }
    v42 = a4;
    if ( !a4 )
      v42 = L"NULL";
    phwnd[2] = (HWND)v42;
    v74 = v41;
    v75 = 0;
    McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_Shell_Core_Provider_Context, "-L", L"NULL", 2, phwnd);
  }
  v13 = -2147024809;
  if ( !a6 )
    goto LABEL_172;
  *a6 = 0;
  if ( !v7 )
    goto LABEL_172;
  if ( !*v7 )
  {
    v13 = SHILClone((const struct _ITEMIDLIST_RELATIVE *)c_idlDrives, a6);
LABEL_172:
    v45 = a6;
    goto LABEL_107;
  }
  v60 = 0;
  Src = 0;
  value[0] = 0;
  propBag = 0;
  DWORD = -2147467262;
  ppbc = 0;
  if ( v8
    && ((int (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, LPBC *))v8->lpVtbl->GetObjectParam)(
         v8,
         L"SHBindCtxPropertyBag",
         &ppbc) >= 0 )
  {
    v15 = ((__int64 (__fastcall *)(LPBC, GUID *, IPropertyBag **))ppbc->lpVtbl->QueryInterface)(
            ppbc,
            &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
            &propBag);
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
    if ( v15 < 0 )
    {
LABEL_10:
      v16 = 0;
      goto LABEL_11;
    }
    DWORD = PSPropertyBag_ReadDWORD(propBag, L"SHBindCtxPathType", value);
    ((void (__fastcall *)(IPropertyBag *))propBag->lpVtbl->Release)(propBag);
  }
  if ( DWORD < 0 || (value[0] & 0x10) == 0 )
    goto LABEL_10;
  v16 = 1;
LABEL_11:
  if ( PathGetDriveNumberW(v7) == -1 )
    goto LABEL_14;
  if ( v16 )
  {
    if ( v7[1] != 58 )
      SHSetPathTypeBindCtx(v8, 0x12u);
    goto LABEL_23;
  }
  if ( v7[1] == 58 )
  {
LABEL_23:
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloBrokerShellObjects>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_AppSiloBrokerShellObjects>::GetImpl'::`2'::impl);
    if ( (int)Windows::Security::Isolation::TryBrokerSHParseDisplayName(
                (Windows::Security::Isolation *)L"::{20D04FE0-3AEA-1069-A2D8-08002B30309D}",
                0,
                (struct IBindCtx *)&Src,
                0,
                0,
                v58) >= 0 )
    {
      v13 = 0;
    }
    else
    {
      Src = 0;
      ppwsz = 0;
      v13 = SHStrDupW(L"::{20D04FE0-3AEA-1069-A2D8-08002B30309D}", &ppwsz);
      if ( v13 >= 0 )
      {
        ppshf = 0;
        v13 = SHGetDesktopFolder(&ppshf);
        if ( v13 >= 0 )
        {
          v17 = 0;
          ppbc = 0;
          v13 = CreateBindCtx(0, &ppbc);
          if ( v13 >= 0 )
          {
            v18 = ppbc;
            v19 = (CDummyUnknown *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
            phwnd[0] = (HWND)v19;
            if ( v19 && (v20 = CDummyUnknown::CDummyUnknown(v19), (v21 = v20) != 0) )
            {
              v13 = ((__int64 (__fastcall *)(LPBC, const wchar_t *, CDummyUnknown *))v18->lpVtbl->RegisterObjectParam)(
                      v18,
                      L"Parse Translate Aliases",
                      v20);
              if ( (int)--*((_DWORD *)v21 + 6) <= 0 )
                operator delete(v21, (const struct std::nothrow_t *)0x40);
              if ( v13 >= 0 )
              {
                v17 = ppbc;
                ((void (__fastcall *)(LPBC))ppbc->lpVtbl->AddRef)(ppbc);
              }
            }
            else
            {
              v13 = -2147024882;
            }
            ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
          }
          if ( v13 >= 0 )
          {
            v22 = ppshf;
            ParseDisplayName = ppshf->lpVtbl->ParseDisplayName;
            v24 = ppwsz;
            phwnd[0] = 0;
            propBag = 0;
            *(_OWORD *)&ppu.cbSize = *(_OWORD *)L"UI During Binding";
            *(_OWORD *)&ppu.cchProtocol = *(_OWORD *)L"g Binding";
            ppu.cchSuffix = *(_DWORD *)L"g";
            if ( v17
              && ((int (__fastcall *)(LPBC, PARSEDURLW *, IPropertyBag **))v17->lpVtbl->GetObjectParam)(
                   v17,
                   &ppu,
                   &propBag) >= 0 )
            {
              IUnknown_GetWindow((IUnknown *)propBag, phwnd);
              ((void (__fastcall *)(IPropertyBag *))propBag->lpVtbl->Release)(propBag);
            }
            v13 = ((__int64 (__fastcall *)(IShellFolder *, HWND, LPBC, LPWSTR, _QWORD, void **, _QWORD))ParseDisplayName)(
                    v22,
                    phwnd[0],
                    v17,
                    v24,
                    0,
                    &Src,
                    0);
          }
          if ( v17 )
            ((void (__fastcall *)(LPBC))v17->lpVtbl->Release)(v17);
          v11 = v68;
        }
        CoTaskMemFree(ppwsz);
        if ( ppshf )
          ((void (__fastcall *)(IShellFolder *))ppshf->lpVtbl->Release)(ppshf);
      }
    }
    goto LABEL_44;
  }
LABEL_14:
  if ( PathIsUNCW(v7) )
  {
    if ( v16 )
    {
      if ( v7[2] == 63 )
        SHSetPathTypeBindCtx(v8, 0x11u);
    }
    else if ( v7[2] == 63 )
    {
      goto LABEL_15;
    }
    if ( (unsigned int)BindCtx_ContainsObject(v8, L"OLD NETWORK PARSE") )
    {
      v13 = SHParseDisplayName(L"::{208D2C60-3AEA-1069-A2D7-08002B30309D}", 0, (LPITEMIDLIST *)&Src, 0, 0);
    }
    else
    {
      v13 = SHGetKnownFolderIDList_Internal(
              (struct _GUID *)&FOLDERID_NetworkFolder,
              0,
              0,
              (struct _ITEMIDLIST_ABSOLUTE **)&Src);
      if ( v13 == 1 )
      {
        v13 = -2147024809;
        goto LABEL_74;
      }
    }
    goto LABEL_44;
  }
LABEL_15:
  if ( !UrlIsW(v7, URLIS_URL)
    || v8
    && (phwnd[0] = (HWND)16,
        phwnd[1] = 0,
        ((int (__fastcall *)(struct IBindCtx *, HWND *))v8->lpVtbl->GetBindOptions)(v8, phwnd) >= 0)
    && HIDWORD(phwnd[0]) == 2 )
  {
    if ( !v16 )
      goto LABEL_74;
    phwnd[0] = 0;
    if ( (int)CMountPoint::GetSimulatedMountPointFromVolumeGuid(v7, (struct CMountPoint **)phwnd) < 0 )
      goto LABEL_74;
    SHSetPathTypeBindCtx(v8, 0x16u);
    v13 = SHParseDisplayName(L"::{20D04FE0-3AEA-1069-A2D8-08002B30309D}", 0, (LPITEMIDLIST *)&Src, 0, 0);
    CMountPoint::Release((CMountPoint *)phwnd[0]);
  }
  else
  {
    v60 = 0;
    Src = 0;
    *(_QWORD *)&ppu.cbSize = 40;
    memset(&ppu.pszProtocol, 0, 32);
    v13 = ParseURLW(v7, &ppu);
    if ( v13 >= 0 )
    {
      if ( ppu.nScheme == 12 )
      {
        v60 = (char *)this + 200;
      }
      else
      {
        switch ( ppu.nScheme )
        {
          case 2u:
          case 0xBu:
            if ( (unsigned int)BindCtx_ContainsObject(v8, L"Parse Prefer Folder Browsing")
              || (unsigned int)BindCtx_ContainsObject(v8, L"ParseAsDurableContentUri") )
            {
              v60 = (char *)this + 232;
            }
            else
            {
              v13 = -2147024809;
            }
            break;
          case 9u:
            v60 = (char *)this + 224;
            break;
          case 0x13u:
            v60 = (char *)this + 184;
            break;
          case 0x14u:
            goto LABEL_167;
          case 0x18u:
          case 0x19u:
            if ( (unsigned int)BindCtx_ContainsObject(v8, L"Parse Prefer Folder Browsing")
              && (ppu.nScheme == 24 || (unsigned int)IsExplorerDefaultSearchProvider()) )
            {
              v60 = (char *)this + 216;
            }
            else
            {
LABEL_167:
              v13 = -2147024809;
            }
            break;
          case 0x1Au:
            v60 = (char *)this + 208;
            break;
          default:
            v13 = _TryRegisteredUrlJunction(ppu.pszProtocol, ppu.cchProtocol, (struct _ITEMIDLIST_ABSOLUTE **)&Src);
            break;
        }
      }
    }
  }
LABEL_44:
  if ( v13 >= 0 )
  {
    v25 = (const ITEMIDLIST *)Src;
    if ( Src && !v60 )
    {
      v60 = 0;
      ppbc = 0;
      v13 = CDesktopFolder_CreateInstance(0, &GUID_000214e6_0000_0000_c000_000000000046, &ppbc);
      if ( v13 >= 0 )
      {
        if ( v25 && v25->mkid.cb )
          v26 = ((__int64 (__fastcall *)(LPBC, const ITEMIDLIST *, _QWORD, GUID *, char **))ppbc->lpVtbl->ReleaseBoundObjects)(
                  ppbc,
                  v25,
                  0,
                  &GUID_000214e6_0000_0000_c000_000000000046,
                  &v60);
        else
          v26 = ((__int64 (__fastcall *)(LPBC, GUID *, char **))ppbc->lpVtbl->QueryInterface)(
                  ppbc,
                  &GUID_000214e6_0000_0000_c000_000000000046,
                  &v60);
        v13 = v26;
        if ( v26 >= 0 && !v60 )
          v13 = -2147467259;
        ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
      }
      if ( v13 < 0 )
      {
        CoTaskMemFree(Src);
        Src = 0;
        goto LABEL_74;
      }
      v25 = (const ITEMIDLIST *)Src;
    }
    if ( a5 )
      *a5 = 0;
    v27 = v60;
    *v11 = 0;
    ppbc = 0;
    v13 = (*(__int64 (__fastcall **)(char *, HWND, struct IBindCtx *, const wchar_t *, unsigned int *, LPBC *, unsigned int *))(*(_QWORD *)v27 + 24LL))(
            v27,
            v69,
            v8,
            v7,
            a5,
            &ppbc,
            v70);
    if ( v13 >= 0 )
    {
      if ( v25 )
      {
        v28 = ppbc;
        if ( ppbc )
        {
          v29 = v25;
          v30 = 2;
          do
          {
            cb = v29->mkid.cb;
            if ( !(_WORD)cb )
              break;
            v30 += cb;
            v29 = (const ITEMIDLIST *)((char *)v29 + cb);
          }
          while ( v29 );
          v32 = (unsigned int)(v30 - 2);
          v33 = ppbc;
          do
          {
            lpVtbl_low = LOWORD(v33->lpVtbl);
            if ( !(_WORD)lpVtbl_low )
              break;
            v12 += lpVtbl_low;
            v33 = (LPBC)((char *)v33 + lpVtbl_low);
          }
          while ( v33 );
          v35 = (ITEMIDLIST *)WINRT_IMPL_CoTaskMemAlloc((unsigned int)v32 + v12);
          v36 = v35;
          if ( v35 )
          {
            memset_0(v35, 0, (unsigned int)v32 + v12);
            memcpy_0(v36, v25, (unsigned int)v32);
            memcpy_0((char *)v36 + v32, v28, v12);
          }
        }
        else
        {
          v36 = ILClone(v25);
        }
        v37 = v68;
        *v68 = (struct _ITEMIDLIST_ABSOLUTE *)v36;
        v13 = 0;
        if ( !v36 )
          v13 = -2147024882;
        CoTaskMemFree(ppbc);
        v8 = *(struct IBindCtx **)v71;
        v11 = v37;
      }
      else
      {
        *v11 = (struct _ITEMIDLIST_ABSOLUTE *)ppbc;
      }
    }
    CoTaskMemFree(Src);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v60 + 16LL))(v60);
  }
LABEL_74:
  if ( v13 >= 0 )
  {
    phwnd[0] = 0;
    if ( v8
      && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, HWND *))v8->lpVtbl->GetObjectParam)(
           v8,
           L"Parse Translate Aliases",
           phwnd) >= 0 )
    {
      (*(void (__fastcall **)(HWND))(*(_QWORD *)phwnd[0] + 16LL))(phwnd[0]);
      phwnd[0] = 0;
      if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, HWND *))v8->lpVtbl->GetObjectParam)(
             v8,
             L"Avoid Translate Desktop Alias",
             phwnd) >= 0 )
        (*(void (__fastcall **)(HWND))(*(_QWORD *)phwnd[0] + 16LL))(phwnd[0]);
      v66 = 0;
      if ( (int)SHILAliasTranslate(*v11) >= 0 )
      {
        CoTaskMemFree(*v11);
        *v11 = v66;
      }
    }
    goto LABEL_105;
  }
  if ( (unsigned int)FailForceReturn(v13) )
  {
LABEL_105:
    v45 = v68;
    goto LABEL_106;
  }
  phwnd[0] = 0;
  if ( v8
    && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, HWND *))v8->lpVtbl->GetObjectParam)(
         v8,
         L"Don't Parse Relative",
         phwnd) >= 0 )
  {
    (*(void (__fastcall **)(HWND))(*(_QWORD *)phwnd[0] + 16LL))(phwnd[0]);
    v13 = -2147024809;
    v45 = v68;
    v10 = a5;
    goto LABEL_107;
  }
  *(_DWORD *)v71 = 16;
  *(_QWORD *)&v71[4] = 0;
  v72 = 0;
  v39 = 0;
  if ( v8
    && ((int (__fastcall *)(struct IBindCtx *, _BYTE *))v8->lpVtbl->GetBindOptions)(v8, v71) >= 0
    && (*(_WORD *)&v71[8] & 0x1000) != 0 )
  {
    v39 = 1;
    *(_DWORD *)&v71[8] &= ~0x1000u;
    ((void (__fastcall *)(struct IBindCtx *, _BYTE *))v8->lpVtbl->SetBindOptions)(v8, v71);
    *(_QWORD *)value = 0;
    ppbc = 0;
  }
  else
  {
    *(_QWORD *)value = 0;
    ppbc = 0;
    if ( !v8 )
      goto LABEL_96;
  }
  if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, LPBC *))v8->lpVtbl->GetObjectParam)(
         v8,
         L"Root For Relative Parse",
         &ppbc) >= 0 )
  {
    v43 = ((__int64 (__fastcall *)(LPBC, GUID *, DWORD *))ppbc->lpVtbl->QueryInterface)(
            ppbc,
            &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
            value);
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
    if ( v43 >= 0 )
    {
      ppbc = 0;
      v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const GUID *, GUID *, LPBC *))(**(_QWORD **)value + 24LL))(
              *(_QWORD *)value,
              0,
              &BHID_SFObject,
              &GUID_000214e6_0000_0000_c000_000000000046,
              &ppbc);
      if ( v13 < 0 )
      {
        v45 = v68;
      }
      else
      {
        v13 = ((__int64 (__fastcall *)(struct IBindCtx *, const wchar_t *))v8->lpVtbl->RevokeObjectParam)(
                v8,
                L"Root For Relative Parse");
        if ( v13 < 0
          || (ppwsz = 0,
              v13 = ((__int64 (__fastcall *)(LPBC, HWND, struct IBindCtx *, const wchar_t *, unsigned int *, LPWSTR *, unsigned int *))ppbc->lpVtbl->RegisterObjectBound)(
                      ppbc,
                      v69,
                      v8,
                      v7,
                      a5,
                      &ppwsz,
                      v70),
              v13 < 0) )
        {
          v45 = v68;
        }
        else
        {
          ppshf = 0;
          v13 = SHGetIDListFromObject((IUnknown *)ppbc, (LPITEMIDLIST *)&ppshf);
          v45 = v68;
          if ( v13 >= 0 )
          {
            v13 = SHILCombine(
                    (const struct _ITEMIDLIST_ABSOLUTE *)ppshf,
                    (const struct _ITEMIDLIST_RELATIVE *)ppwsz,
                    v68);
            CoTaskMemFree(ppshf);
          }
          CoTaskMemFree(ppwsz);
        }
        ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
      }
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)value + 16LL))(*(_QWORD *)value);
      v44 = (__int64 **)((char *)v66 + 160);
LABEL_139:
      if ( v13 < 0 )
        goto LABEL_140;
LABEL_106:
      v10 = a5;
      goto LABEL_107;
    }
  }
LABEL_96:
  v44 = (__int64 **)((char *)v66 + 160);
  if ( !*((_QWORD *)v66 + 20) || (unsigned int)_ShouldParseFromKnownFolder(v38, v8) )
    goto LABEL_136;
  phwnd[0] = 0;
  if ( v8
    && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, HWND *))v8->lpVtbl->GetObjectParam)(
         v8,
         L"ParseAsCommonItem",
         phwnd) >= 0 )
  {
    (*(void (__fastcall **)(HWND))(*(_QWORD *)phwnd[0] + 16LL))(phwnd[0]);
LABEL_136:
    v45 = v68;
    v46 = a5;
    goto LABEL_137;
  }
  v45 = v68;
  v46 = a5;
  v13 = (*(__int64 (__fastcall **)(__int64 *, HWND, struct IBindCtx *, const wchar_t *, unsigned int *, struct _ITEMIDLIST_ABSOLUTE **, unsigned int *))(**v44 + 24))(
          *v44,
          v69,
          v8,
          v7,
          a5,
          v68,
          v70);
  if ( v13 >= 0 )
  {
    v10 = a5;
LABEL_107:
    v47 = (int *)v70;
    v48 = (int)v69;
    goto LABEL_108;
  }
LABEL_137:
  v55 = *((_QWORD *)v66 + 21);
  if ( v55 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, HWND, struct IBindCtx *, const wchar_t *, unsigned int *, struct _ITEMIDLIST_ABSOLUTE **, unsigned int *))(*(_QWORD *)v55 + 24LL))(
            v55,
            v69,
            v8,
            v7,
            v46,
            v45,
            v70);
    goto LABEL_139;
  }
LABEL_140:
  if ( !v39 || !*v44 )
    goto LABEL_106;
  *(_DWORD *)&v71[8] |= 0x1000u;
  ((void (__fastcall *)(struct IBindCtx *, _BYTE *))v8->lpVtbl->SetBindOptions)(v8, v71);
  v56 = *v44;
  v57 = **v44;
  v47 = (int *)v70;
  v10 = a5;
  v48 = (int)v69;
  v13 = (*(__int64 (__fastcall **)(__int64 *, HWND, struct IBindCtx *, const wchar_t *, unsigned int *, struct _ITEMIDLIST_ABSOLUTE **, unsigned int *))(v57 + 24))(
          v56,
          v69,
          v8,
          v7,
          a5,
          v45,
          v70);
LABEL_108:
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
  {
    v50 = -1;
    if ( v47 )
      v51 = *v47;
    else
      v51 = -1;
    if ( v10 )
      v50 = *v10;
    if ( v45 )
      v52 = *v45;
    else
      v52 = 0;
    *(_QWORD *)v71 = v52;
    LODWORD(v68) = v51;
    LODWORD(v70) = v50;
    phwnd[0] = (HWND)v8;
    LODWORD(v69) = v48;
    value[0] = v13;
    if ( v7 )
    {
      v53 = -1;
      do
        ++v53;
      while ( v7[v53] );
      v54 = 2 * v53 + 2;
    }
    else
    {
      v54 = 10;
    }
    if ( !v7 )
      v7 = L"NULL";
    v77 = v7;
    v78 = v54;
    v79 = 0;
    v80 = value;
    v81 = 4;
    v82 = v71;
    v83 = 8;
    v84 = &v69;
    v85 = 4;
    v86 = phwnd;
    v87 = 8;
    v88 = &v70;
    v89 = 4;
    v90 = &v68;
    v91 = 4;
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      CDesktopFolder_ParseDisplayName_Stop,
      0,
      8,
      v76);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800b8ae0  push    rbp
0x1800b8ae2  push    rbx
0x1800b8ae3  push    rsi
0x1800b8ae4  push    rdi
0x1800b8ae5  push    r12
0x1800b8ae7  push    r13
0x1800b8ae9  push    r14
0x1800b8aeb  push    r15
0x1800b8aed  lea     rbp, [rsp-98h]
0x1800b8af5  sub     rsp, 198h
0x1800b8afc  mov     rax, cs:__security_cookie
0x1800b8b03  xor     rax, rsp
0x1800b8b06  mov     [rbp+0D0h+var_50], rax
0x1800b8b0d  mov     r12, r9
0x1800b8b10  mov     r15, r8
0x1800b8b13  mov     [rbp+0D0h+var_108], r8
0x1800b8b17  mov     [rbp+0D0h+var_118], rdx
0x1800b8b1b  mov     r14, rcx
0x1800b8b1e  mov     [rbp+0D0h+var_150], rcx
0x1800b8b22  mov     rbx, [rbp+0D0h+arg_20]
0x1800b8b29  mov     [rsp+1D0h+var_190], rbx
0x1800b8b2e  mov     rsi, [rbp+0D0h+arg_28]
0x1800b8b35  mov     [rbp+0D0h+var_120], rsi
0x1800b8b39  mov     rax, [rbp+0D0h+arg_30]
0x1800b8b40  mov     [rbp+0D0h+var_110], rax
0x1800b8b44  lea     r8, aNull_0; "NULL"
0x1800b8b4b  xor     edx, edx
0x1800b8b4d  mov     r13d, 2
0x1800b8b53  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x1800b8b5a  jnz     loc_1800B9179
0x1800b8b60  mov     edi, 80070057h
0x1800b8b65  test    rsi, rsi
0x1800b8b68  jz      loc_1800B98C3
0x1800b8b6e  mov     [rsi], rdx
0x1800b8b71  test    r12, r12
0x1800b8b74  jz      loc_1800B98C3
0x1800b8b7a  cmp     word ptr [r12], 0
0x1800b8b80  jz      loc_1800B98B2
0x1800b8b86  mov     [rsp+1D0h+var_180], rdx
0x1800b8b8b  mov     [rsp+1D0h+Src], rdx
0x1800b8b90  mov     [rsp+1D0h+value], edx
0x1800b8b94  mov     [rsp+1D0h+propBag], rdx
0x1800b8b99  mov     ebx, 80004002h
0x1800b8b9e  mov     [rsp+1D0h+ppbc], rdx
0x1800b8ba3  test    r15, r15
0x1800b8ba6  jz      loc_1800B8C2E
0x1800b8bac  mov     rax, [r15]
0x1800b8baf  lea     r8, [rsp+1D0h+ppbc]
0x1800b8bb4  lea     rdx, aShbindctxprope; "SHBindCtxPropertyBag"
0x1800b8bbb  mov     rcx, r15
0x1800b8bbe  mov     rax, [rax+50h]
0x1800b8bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8bc7  test    eax, eax
0x1800b8bc9  js      short loc_1800B8C2E
0x1800b8bcb  mov     rcx, [rsp+1D0h+ppbc]
0x1800b8bd0  mov     rax, [rcx]
0x1800b8bd3  lea     r8, [rsp+1D0h+propBag]
0x1800b8bd8  lea     rdx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x1800b8bdf  mov     rax, [rax]
0x1800b8be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8be7  mov     ebx, eax
0x1800b8be9  mov     rcx, [rsp+1D0h+ppbc]
0x1800b8bee  mov     rax, [rcx]
0x1800b8bf1  mov     rax, [rax+10h]
0x1800b8bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8bfa  test    ebx, ebx
0x1800b8bfc  js      short loc_1800B8C36
0x1800b8bfe  lea     r8, [rsp+1D0h+value]; value
0x1800b8c03  lea     rdx, aShbindctxpatht; "SHBindCtxPathType"
0x1800b8c0a  mov     rcx, [rsp+1D0h+propBag]; propBag
0x1800b8c0f  call    cs:__imp_PSPropertyBag_ReadDWORD
0x1800b8c16  nop     dword ptr [rax+rax+00h]
0x1800b8c1b  mov     ebx, eax
0x1800b8c1d  mov     rcx, [rsp+1D0h+propBag]
0x1800b8c22  mov     rax, [rcx]
0x1800b8c25  mov     rax, [rax+10h]
0x1800b8c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8c2e  test    ebx, ebx
0x1800b8c30  jns     loc_1800B96A9
0x1800b8c36  xor     bl, bl
0x1800b8c38  mov     rcx, r12; pszPath
0x1800b8c3b  call    cs:__imp_PathGetDriveNumberW
0x1800b8c42  nop     dword ptr [rax+rax+00h]
0x1800b8c47  cmp     eax, 0FFFFFFFFh
0x1800b8c4a  jz      short loc_1800B8C61
0x1800b8c4c  test    bl, bl
0x1800b8c4e  jnz     loc_1800B8CD8
0x1800b8c54  cmp     word ptr [r12+2], 3Ah ; ':'
0x1800b8c5b  jz      loc_1800B8CE5
0x1800b8c61  mov     rcx, r12; pszPath
0x1800b8c64  call    cs:__imp_PathIsUNCW
0x1800b8c6b  nop     dword ptr [rax+rax+00h]
0x1800b8c70  test    eax, eax
0x1800b8c72  jnz     loc_1800B95A2
0x1800b8c78  xor     edx, edx; UrlIs
0x1800b8c7a  mov     rcx, r12; pszUrl
0x1800b8c7d  call    cs:__imp_UrlIsW
0x1800b8c84  nop     dword ptr [rax+rax+00h]
0x1800b8c89  test    eax, eax
0x1800b8c8b  jz      short loc_1800B8CC9
0x1800b8c8d  test    r15, r15
0x1800b8c90  jz      loc_1800B923A
0x1800b8c96  mov     [rbp+0D0h+phwnd], 10h
0x1800b8c9e  xor     eax, eax
0x1800b8ca0  mov     [rbp+0D0h+var_F0], rax
0x1800b8ca4  mov     rax, [r15]
0x1800b8ca7  lea     rdx, [rbp+0D0h+phwnd]
0x1800b8cab  mov     rcx, r15
0x1800b8cae  mov     rax, [rax+38h]
0x1800b8cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8cb7  test    eax, eax
0x1800b8cb9  js      loc_1800B923A
0x1800b8cbf  cmp     dword ptr [rbp+0D0h+phwnd+4], r13d
0x1800b8cc3  jnz     loc_1800B923A
0x1800b8cc9  test    bl, bl
0x1800b8ccb  jnz     loc_1800B976A
0x1800b8cd1  xor     ebx, ebx
0x1800b8cd3  jmp     loc_1800B90BF
0x1800b8cd8  cmp     word ptr [r12+2], 3Ah ; ':'
0x1800b8cdf  jnz     loc_1800B97F8
0x1800b8ce5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloBrokerShellObjects@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloBrokerShellObjects@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloBrokerShellObjects> `wil::Feature<__WilFeatureTraits_Feature_AppSiloBrokerShellObjects>::GetImpl(void)'::`2'::impl
0x1800b8cec  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloBrokerShellObjects@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloBrokerShellObjects>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x1800b8cf1  xor     r14d, r14d
0x1800b8cf4  mov     [rsp+1D0h+psfgaoOut], r14; unsigned int
0x1800b8cf9  xor     r9d, r9d; struct _ITEMIDLIST_ABSOLUTE **
0x1800b8cfc  lea     r8, [rsp+1D0h+Src]; struct IBindCtx *
0x1800b8d01  xor     edx, edx; unsigned __int16 *
0x1800b8d03  lea     rcx, a20d04fe03aea10; "::{20D04FE0-3AEA-1069-A2D8-08002B30309D"...
0x1800b8d0a  call    ?TryBrokerSHParseDisplayName@Isolation@Security@Windows@@YAJPEBGPEAUIBindCtx@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@KPEAK@Z; Windows::Security::Isolation::TryBrokerSHParseDisplayName(ushort const *,IBindCtx *,_ITEMIDLIST_ABSOLUTE * *,ulong,ulong *)
0x1800b8d0f  test    eax, eax
0x1800b8d11  jns     loc_1800B96A1
0x1800b8d17  mov     [rsp+1D0h+Src], r14
0x1800b8d1c  mov     [rsp+1D0h+ppwsz], r14
0x1800b8d21  lea     rdx, [rsp+1D0h+ppwsz]; ppwsz
0x1800b8d26  lea     rcx, a20d04fe03aea10; "::{20D04FE0-3AEA-1069-A2D8-08002B30309D"...
0x1800b8d2d  call    cs:__imp_SHStrDupW
0x1800b8d34  nop     dword ptr [rax+rax+00h]
0x1800b8d39  mov     edi, eax
0x1800b8d3b  test    eax, eax
0x1800b8d3d  js      loc_1800B8EDF
0x1800b8d43  mov     [rsp+1D0h+ppshf], r14
0x1800b8d48  lea     rcx, [rsp+1D0h+ppshf]; ppshf
0x1800b8d4d  call    SHGetDesktopFolder
0x1800b8d52  mov     edi, eax
0x1800b8d54  test    eax, eax
0x1800b8d56  js      loc_1800B8EB6
0x1800b8d5c  mov     ebx, r14d
0x1800b8d5f  mov     [rsp+1D0h+ppbc], r14
0x1800b8d64  lea     rdx, [rsp+1D0h+ppbc]; ppbc
0x1800b8d69  xor     ecx, ecx; reserved
0x1800b8d6b  call    cs:__imp_CreateBindCtx
0x1800b8d72  nop     dword ptr [rax+rax+00h]
0x1800b8d77  mov     edi, eax
0x1800b8d79  test    eax, eax
0x1800b8d7b  js      loc_1800B8E08
0x1800b8d81  mov     rdi, [rsp+1D0h+ppbc]
0x1800b8d86  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b8d8d  mov     ecx, 40h ; '@'; unsigned __int64
0x1800b8d92  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800b8d97  mov     [rbp+0D0h+phwnd], rax
0x1800b8d9b  test    rax, rax
0x1800b8d9e  jz      loc_1800B9390
0x1800b8da4  mov     rcx, rax; this
0x1800b8da7  call    ??0CDummyUnknown@@QEAA@XZ; CDummyUnknown::CDummyUnknown(void)
0x1800b8dac  mov     rsi, rax
0x1800b8daf  test    rax, rax
0x1800b8db2  jz      loc_1800B9390
0x1800b8db8  mov     rax, [rdi]
0x1800b8dbb  mov     r8, rsi
0x1800b8dbe  lea     rdx, aParseTranslate; "Parse Translate Aliases"
0x1800b8dc5  mov     rcx, rdi
0x1800b8dc8  mov     rax, [rax+48h]
0x1800b8dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8dd1  mov     edi, eax
0x1800b8dd3  dec     dword ptr [rsi+18h]
0x1800b8dd6  cmp     [rsi+18h], ebx
0x1800b8dd9  jle     loc_1800B91DC
0x1800b8ddf  test    edi, edi
0x1800b8de1  js      short loc_1800B8DF7
0x1800b8de3  mov     rbx, [rsp+1D0h+ppbc]
0x1800b8de8  mov     rax, [rbx]
0x1800b8deb  mov     rcx, rbx
0x1800b8dee  mov     rax, [rax+8]
0x1800b8df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8df7  mov     rcx, [rsp+1D0h+ppbc]
0x1800b8dfc  mov     rax, [rcx]
0x1800b8dff  mov     rax, [rax+10h]
0x1800b8e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8e08  test    edi, edi
0x1800b8e0a  js      loc_1800B8E9D
0x1800b8e10  mov     rdi, [rsp+1D0h+ppshf]
0x1800b8e15  mov     rax, [rdi]
0x1800b8e18  mov     r14, [rax+18h]
0x1800b8e1c  mov     rsi, [rsp+1D0h+ppwsz]
0x1800b8e21  xor     eax, eax
0x1800b8e23  mov     [rbp+0D0h+phwnd], rax
0x1800b8e27  mov     [rsp+1D0h+propBag], rax
0x1800b8e2c  movups  xmm0, xmmword ptr cs:aUiDuringBindin; "UI During Binding"
0x1800b8e33  movups  xmmword ptr [rbp+0D0h+ppu.cbSize], xmm0
0x1800b8e37  movups  xmm1, xmmword ptr cs:aUiDuringBindin+10h; "g Binding"
0x1800b8e3e  movups  xmmword ptr [rbp+0D0h+ppu.cchProtocol], xmm1
0x1800b8e42  mov     eax, dword ptr cs:aUiDuringBindin+20h; "g"
0x1800b8e48  mov     [rbp+0D0h+ppu.cchSuffix], eax
0x1800b8e4b  test    rbx, rbx
0x1800b8e4e  jz      short loc_1800B8E70
0x1800b8e50  mov     rax, [rbx]
0x1800b8e53  lea     r8, [rsp+1D0h+propBag]
0x1800b8e58  lea     rdx, [rbp+0D0h+ppu]
0x1800b8e5c  mov     rcx, rbx
0x1800b8e5f  mov     rax, [rax+50h]
0x1800b8e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8e68  test    eax, eax
0x1800b8e6a  jns     loc_1800B920F
0x1800b8e70  xor     ecx, ecx
0x1800b8e72  mov     [rsp+1D0h+var_1A0], rcx
0x1800b8e77  lea     rax, [rsp+1D0h+Src]
0x1800b8e7c  mov     [rsp+1D0h+var_1A8], rax
0x1800b8e81  mov     [rsp+1D0h+psfgaoOut], rcx
0x1800b8e86  mov     r9, rsi
0x1800b8e89  mov     r8, rbx
0x1800b8e8c  mov     rdx, [rbp+0D0h+phwnd]
0x1800b8e90  mov     rcx, rdi
0x1800b8e93  mov     rax, r14
0x1800b8e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8e9b  mov     edi, eax
0x1800b8e9d  test    rbx, rbx
0x1800b8ea0  jz      short loc_1800B8EB2
0x1800b8ea2  mov     rax, [rbx]
0x1800b8ea5  mov     rcx, rbx
0x1800b8ea8  mov     rax, [rax+10h]
0x1800b8eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8eb1  nop
0x1800b8eb2  mov     rsi, [rbp+0D0h+var_120]
0x1800b8eb6  mov     rcx, [rsp+1D0h+ppwsz]; pv
0x1800b8ebb  call    cs:__imp_CoTaskMemFree
0x1800b8ec2  nop     dword ptr [rax+rax+00h]
0x1800b8ec7  nop
0x1800b8ec8  mov     rcx, [rsp+1D0h+ppshf]
0x1800b8ecd  test    rcx, rcx
0x1800b8ed0  jz      short loc_1800B8EDF
0x1800b8ed2  mov     rax, [rcx]
0x1800b8ed5  mov     rax, [rax+10h]
0x1800b8ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8ede  nop
0x1800b8edf  xor     ebx, ebx
0x1800b8ee1  test    edi, edi
0x1800b8ee3  js      loc_1800B8CD1
0x1800b8ee9  mov     r14, [rsp+1D0h+Src]
0x1800b8eee  test    r14, r14
0x1800b8ef1  jz      loc_1800B8F94
0x1800b8ef7  cmp     [rsp+1D0h+var_180], 0
0x1800b8efd  jnz     loc_1800B8F94
0x1800b8f03  mov     [rsp+1D0h+var_180], rbx
0x1800b8f08  mov     [rsp+1D0h+ppbc], rbx
0x1800b8f0d  lea     r8, [rsp+1D0h+ppbc]
0x1800b8f12  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x1800b8f19  xor     ecx, ecx
0x1800b8f1b  call    CDesktopFolder_CreateInstance
0x1800b8f20  mov     edi, eax
0x1800b8f22  test    eax, eax
0x1800b8f24  js      short loc_1800B8F87
0x1800b8f26  test    r14, r14
0x1800b8f29  jz      loc_1800B91EE
0x1800b8f2f  cmp     word ptr [r14], 0
0x1800b8f34  jz      loc_1800B91EE
0x1800b8f3a  mov     rcx, [rsp+1D0h+ppbc]
0x1800b8f3f  mov     rax, [rcx]
0x1800b8f42  lea     rdx, [rsp+1D0h+var_180]
0x1800b8f47  mov     [rsp+1D0h+psfgaoOut], rdx
0x1800b8f4c  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x1800b8f53  xor     r8d, r8d
0x1800b8f56  mov     rdx, r14
0x1800b8f59  mov     rax, [rax+28h]
0x1800b8f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8f62  mov     edi, eax
0x1800b8f64  test    eax, eax
0x1800b8f66  js      short loc_1800B8F76
0x1800b8f68  mov     eax, 80004005h
0x1800b8f6d  cmp     [rsp+1D0h+var_180], 0
0x1800b8f73  cmovz   edi, eax
0x1800b8f76  mov     rcx, [rsp+1D0h+ppbc]
0x1800b8f7b  mov     rax, [rcx]
0x1800b8f7e  mov     rax, [rax+10h]
0x1800b8f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8f87  test    edi, edi
0x1800b8f89  js      loc_1800B9872
0x1800b8f8f  mov     r14, [rsp+1D0h+Src]
0x1800b8f94  mov     rdx, [rsp+1D0h+var_190]
0x1800b8f99  test    rdx, rdx
0x1800b8f9c  jnz     loc_1800B9172
0x1800b8fa2  mov     rcx, [rsp+1D0h+var_180]
0x1800b8fa7  mov     [rsi], rbx
0x1800b8faa  mov     [rsp+1D0h+ppbc], rbx
0x1800b8faf  mov     rax, [rcx]
0x1800b8fb2  mov     r8, [rbp+0D0h+var_110]
0x1800b8fb6  mov     [rsp+1D0h+var_1A0], r8
0x1800b8fbb  lea     r8, [rsp+1D0h+ppbc]
0x1800b8fc0  mov     [rsp+1D0h+var_1A8], r8
0x1800b8fc5  mov     [rsp+1D0h+psfgaoOut], rdx
0x1800b8fca  mov     r9, r12
  ... truncated ...
```
