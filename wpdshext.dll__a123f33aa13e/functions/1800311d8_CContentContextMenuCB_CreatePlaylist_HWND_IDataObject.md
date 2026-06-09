# CContentContextMenuCB::_CreatePlaylist(HWND__ *,IDataObject *)

- ea: `0x1800311d8`
- end: `0x180032291`
- name: `?_CreatePlaylist@CContentContextMenuCB@@AEAAJPEAUHWND__@@PEAUIDataObject@@@Z`
- size: `4281`
- prototype: `__int64 __fastcall(CContentContextMenuCB *__hidden this, HWND hWnd, struct IDataObject *)`
- caller_count: `1`
- callee_count: `27`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180042340`

## callees

- `0x180004110`
- `0x1800082e0`
- `0x18000c180`
- `0x18000d610`
- `0x18000ef50`
- `0x180017724`
- `0x1800285c8`
- `0x1800287d0`
- `0x180028ea8`
- `0x180029730`
- `0x18002ab58`
- `0x18002ff5c`
- `0x1800311d8`
- `0x180032298`
- `0x180035590`
- `0x1800361ba`
- `0x180047618`
- `0x180048414`
- `0x1800535f8`
- `0x180053794`
- `0x180053fd8`
- `0x180054524`
- `0x18005fb88`
- `0x18006b954`
- `0x18006c108`
- `0x18007559c`
- `0x180078010`

## import_xrefs

- `KERNEL32!Sleep` at `0x1800320b9`
- `KERNEL32!Sleep` at `0x1800320b9`
- `KERNEL32!GlobalFree` at `0x180032149`
- `KERNEL32!GlobalFree` at `0x180032149`
- `KERNEL32!GetCurrentThreadId` at `0x180031719`
- `KERNEL32!GetCurrentThreadId` at `0x180031719`
- `SHLWAPI!PathRemoveExtensionW` at `0x180031d06`
- `SHLWAPI!PathRemoveExtensionW` at `0x180031d06`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800320aa`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800320aa`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x1800318e5`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x1800321ca`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x1800318e5`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x1800321ca`
- `USER32!LoadStringW` at `0x1800317ff`
- `USER32!LoadStringW` at `0x180031906`
- `USER32!LoadStringW` at `0x180031c3f`
- `USER32!LoadStringW` at `0x180031c94`
- `USER32!LoadStringW` at `0x1800317ff`
- `USER32!LoadStringW` at `0x180031906`
- `USER32!LoadStringW` at `0x180031c3f`
- `USER32!LoadStringW` at `0x180031c94`
- `USER32!SendMessageW` at `0x1800320ee`
- `USER32!SendMessageW` at `0x1800320ee`
- `ole32!CoTaskMemFree` at `0x180032175`
- `ole32!CoTaskMemFree` at `0x18003218d`
- `ole32!CoTaskMemFree` at `0x180032175`
- `ole32!CoTaskMemFree` at `0x18003218d`
- `ole32!PropVariantClear` at `0x18003219f`
- `ole32!PropVariantClear` at `0x18003219f`
- `ole32!CoCreateInstance` at `0x18003140d`
- `ole32!CoCreateInstance` at `0x180031474`
- `ole32!CoCreateInstance` at `0x18003140d`
- `ole32!CoCreateInstance` at `0x180031474`
- `SHELL32!__imp_ILFindLastID` at `0x1800314b0`
- `SHELL32!__imp_ILFindLastID` at `0x1800314b0`
- `SHELL32!__imp_ILFree` at `0x180032157`
- `SHELL32!__imp_ILFree` at `0x180032165`
- `SHELL32!__imp_ILFree` at `0x180032157`
- `SHELL32!__imp_ILFree` at `0x180032165`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CContentContextMenuCB::_CreatePlaylist(
        CContentContextMenuCB *this,
        HWND hWnd,
        struct IDataObject *a3)
{
  struct _IDA *v6; // r15
  CContentFolder *v7; // rcx
  CContentFolder *v8; // rcx
  GUID v9; // xmm0
  int v10; // eax
  int Instance; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  const struct _ITEMIDLIST *ID; // rax
  CContentFolder *v15; // rcx
  const struct CONTENTITEM *v16; // rax
  const struct std::nothrow_t *v17; // rdx
  CProgressUI *v18; // rax
  CProgressUI *v19; // rax
  CProgressUI *v20; // rdi
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  int IsDelegateFolder; // ebx
  DWORD CurrentThreadId; // eax
  _DWORD *v25; // r12
  unsigned int i; // r15d
  int DoesObjectNameExist; // eax
  __int64 (__fastcall **v28)(_QWORD *, GUID *, __int64 *); // rax
  BOOL v29; // r14d
  int v30; // eax
  ITEMIDLIST *v31; // rdi
  ITEMIDLIST *v32; // r12
  HWND v33; // r13
  unsigned __int64 v34; // rax
  LPVOID v36; // [rsp+38h] [rbp-D0h] BYREF
  HGLOBAL hMem; // [rsp+40h] [rbp-C8h] BYREF
  struct IPortableDevicePropVariantCollection *ppv; // [rsp+48h] [rbp-C0h] BYREF
  struct IPortableDeviceContent *v39; // [rsp+50h] [rbp-B8h] BYREF
  struct IPortableDevice *v40; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v41; // [rsp+60h] [rbp-A8h] BYREF
  LPITEMIDLIST pidl; // [rsp+68h] [rbp-A0h] BYREF
  HWND hWnda; // [rsp+70h] [rbp-98h]
  LPVOID pv; // [rsp+78h] [rbp-90h] BYREF
  void *ppvOut; // [rsp+80h] [rbp-88h] BYREF
  __int64 v46; // [rsp+88h] [rbp-80h] BYREF
  _QWORD *v47; // [rsp+90h] [rbp-78h] BYREF
  LPITEMIDLIST v48; // [rsp+98h] [rbp-70h] BYREF
  PROPVARIANT pvar; // [rsp+A0h] [rbp-68h] BYREF
  struct _GUID v50; // [rsp+B8h] [rbp-50h] BYREF
  LPVOID v51; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v52; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v53; // [rsp+D8h] [rbp-30h] BYREF
  struct _GUID v54; // [rsp+E8h] [rbp-20h] BYREF
  GUID Buf1; // [rsp+F8h] [rbp-10h] BYREF
  struct _GUID v56; // [rsp+108h] [rbp+0h] BYREF
  GUID v57; // [rsp+118h] [rbp+10h]
  WCHAR pszPath[264]; // [rsp+128h] [rbp+20h] BYREF
  WCHAR Buffer[264]; // [rsp+338h] [rbp+230h] BYREF
  WCHAR v60[264]; // [rsp+548h] [rbp+440h] BYREF
  unsigned __int16 v61[264]; // [rsp+758h] [rbp+650h] BYREF
  unsigned __int16 v62[264]; // [rsp+968h] [rbp+860h] BYREF
  unsigned __int16 v63[264]; // [rsp+B78h] [rbp+A70h] BYREF

  hWnda = hWnd;
  memset(&pvar, 0, sizeof(pvar));
  pv = 0;
  v51 = 0;
  memset_0(v61, 0, 0x208u);
  v48 = 0;
  pidl = 0;
  v6 = 0;
  hMem = 0;
  memset_0(v62, 0, 0x208u);
  memset_0(v63, 0, 0x208u);
  memset_0(Buffer, 0, 0x208u);
  v47 = 0;
  v52 = 0;
  v53 = 0;
  v40 = 0;
  v39 = 0;
  v36 = 0;
  v46 = 0;
  ppv = 0;
  ppvOut = 0;
  Buf1 = WPD_OBJECT_FORMAT_PROPERTIES_ONLY;
  v56 = WPD_CONTENT_TYPE_AUDIO;
  v57 = WPD_CONTENT_TYPE_VIDEO;
  memset_0(v60, 0, 0x208u);
  memset_0(pszPath, 0, 0x208u);
  LODWORD(v41) = 0;
  v50 = WPD_OBJECT_FORMAT_PROPERTIES_ONLY;
  v54 = WPD_CONTENT_TYPE_PLAYLIST;
  if ( (unsigned int)CContentFolder::_IsFormatSupportedByDevice(
                       v7,
                       *((const struct _ITEMIDLIST **)this + 5),
                       &v54,
                       &v50) )
  {
    v9 = WPD_OBJECT_FORMAT_PROPERTIES_ONLY;
  }
  else
  {
    v54 = (struct _GUID)WPD_OBJECT_FORMAT_MTP_ABSTRACTPLAYLIST;
    v50 = WPD_CONTENT_TYPE_PLAYLIST;
    if ( !(unsigned int)CContentFolder::_IsFormatSupportedByDevice(
                          v8,
                          *((const struct _ITEMIDLIST **)this + 5),
                          &v50,
                          &v54) )
    {
      Instance = -2147467259;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          366,
          WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
          2147500037LL);
      goto LABEL_169;
    }
    v9 = (GUID)WPD_OBJECT_FORMAT_MTP_ABSTRACTPLAYLIST;
  }
  Buf1 = v9;
  memset(&pvar, 0, sizeof(pvar));
  v10 = DataObj_CopyHIDA(a3, (struct _IDA **)&hMem);
  Instance = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        367,
        WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
        (unsigned int)v10);
    v6 = (struct _IDA *)hMem;
    goto LABEL_169;
  }
  v6 = (struct _IDA *)hMem;
  if ( hMem )
  {
    if ( !*(_DWORD *)hMem )
    {
      Instance = 0;
      goto LABEL_169;
    }
    Instance = CoCreateInstance(
                 &CLSID_PortableDevicePropVariantCollection,
                 0,
                 1u,
                 &GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3,
                 (LPVOID *)&ppv);
    if ( Instance < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_169;
      v13 = 368;
      goto LABEL_18;
    }
    Instance = CoCreateInstance(&CLSID_PortableDeviceValues, 0, 1u, &GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143, &v36);
    if ( Instance < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_169;
      v13 = 369;
      goto LABEL_18;
    }
    ID = ILFindLastID(*(LPCITEMIDLIST *)(*((_QWORD *)this + 4) + 64LL));
    v16 = CContentFolder::_IsValid(v15, ID);
    if ( v16 )
    {
      StringCchCopyW(
        v61,
        0x104u,
        (const unsigned __int16 *)v16 + *(unsigned int *)((char *)v16 + 62) + *(unsigned int *)((char *)v16 + 66) + 37);
    }
    else
    {
      Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, __int64))(**((_QWORD **)this + 4) + 184LL))(
                   *((_QWORD *)this + 4),
                   *((_QWORD *)this + 5),
                   v61,
                   260);
      if ( Instance < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_169;
        v13 = 370;
LABEL_18:
        WPP_SF_d(v12[2], v13, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)Instance);
        goto LABEL_169;
      }
    }
    pvar.vt = 31;
    pvar.hVal.QuadPart = (LONGLONG)v61;
    Instance = ((__int64 (__fastcall *)(struct IPortableDevicePropVariantCollection *, PROPVARIANT *))ppv->lpVtbl->Add)(
                 ppv,
                 &pvar);
    pvar.vt = 0;
    pvar.hVal.QuadPart = 0;
    if ( Instance < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_169;
      v13 = 371;
      goto LABEL_18;
    }
    Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, __int64))(**((_QWORD **)this + 4) + 144LL))(
                 *((_QWORD *)this + 4),
                 *(_QWORD *)(*((_QWORD *)this + 4) + 64LL),
                 v62,
                 260);
    if ( Instance < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_169;
      v13 = 372;
      goto LABEL_18;
    }
    Instance = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, __int64))(**((_QWORD **)this + 4) + 96LL))(
                 *((_QWORD *)this + 4),
                 v63,
                 260);
    if ( Instance < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_169;
      v13 = 373;
      goto LABEL_18;
    }
    v18 = (CProgressUI *)operator new(0xB08u, v17);
    *(_QWORD *)&v50.Data1 = v18;
    if ( !v18 || (v19 = CProgressUI::CProgressUI(v18), (v20 = v19) == 0) )
    {
      Instance = -2147024882;
      goto LABEL_169;
    }
    Instance = CProgressUI::_Initialize(v19, v62);
    if ( Instance < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_161;
      v22 = 374;
      goto LABEL_47;
    }
    Instance = CProgressUI::_BeginProgressUI(v20, SPACTION_COPYING, 0x71u);
    if ( Instance < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_161;
      v22 = 375;
      goto LABEL_47;
    }
    IsDelegateFolder = CBaseFolder::_IsDelegateFolder(*((CBaseFolder **)this + 4));
    CurrentThreadId = GetCurrentThreadId();
    Instance = CDeviceCache::s_BindToPortableDevice(v63, CurrentThreadId, 0, 0, IsDelegateFolder, &v40);
    if ( Instance < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_161;
      v22 = 376;
      goto LABEL_47;
    }
    Instance = CProgressUI::_AssociateDevice(v20, v40);
    if ( Instance < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_161;
      v22 = 377;
      goto LABEL_47;
    }
    Instance = CProgressUI::_StartMarquee(v20);
    if ( Instance < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_161;
      v22 = 378;
      goto LABEL_47;
    }
    LoadStringW(g_hInst, 0x7Eu, Buffer, 260);
    CProgressUI::_ShowFileName(v20, Buffer, &String);
    Instance = CollectPersistentUniqueIDsUsingContentTypeFilter(v20, v6, ppv, &v56, 2u, 1);
    if ( Instance < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_161;
      v22 = 379;
      goto LABEL_47;
    }
    if ( Instance != 1 )
    {
      Instance = ((__int64 (__fastcall *)(struct IPortableDevicePropVariantCollection *, __int64 *))ppv->lpVtbl->GetCount)(
                   ppv,
                   &v41);
      if ( Instance < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_161;
        v22 = 380;
        goto LABEL_47;
      }
      if ( (unsigned int)v41 <= 1 )
      {
        CProgressUI::_EndProgressUI(v20);
        ShellMessageBoxW(g_hInst, hWnd, (LPCWSTR)0x10F, (LPCWSTR)0x10E, 0x40u);
        goto LABEL_161;
      }
      LoadStringW(g_hInst, 0x7Fu, Buffer, 260);
      CProgressUI::_ShowFileName(v20, Buffer, &String);
      Instance = ((__int64 (__fastcall *)(struct IPortableDevice *, struct IPortableDeviceContent **))v40->lpVtbl->Content)(
                   v40,
                   &v39);
      if ( Instance < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_161;
        v22 = 381;
        goto LABEL_47;
      }
      Instance = ((__int64 (__fastcall *)(struct IPortableDeviceContent *, struct IPortableDevicePropVariantCollection *, __int64 *))v39->lpVtbl->GetObjectIDsFromPersistentUniqueIDs)(
                   v39,
                   ppv,
                   &v46);
      if ( Instance < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_161;
        v22 = 382;
        goto LABEL_47;
      }
      Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)v46 + 32LL))(v46, 0, &pvar);
      if ( Instance < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_161;
        v22 = 383;
        goto LABEL_47;
      }
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v46 + 72LL))(v46, 0);
      Instance = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, LARGE_INTEGER))(*(_QWORD *)v36 + 56LL))(
                   v36,
                   &WPD_OBJECT_PARENT_ID,
                   pvar.hVal);
      if ( Instance < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_161;
        v22 = 384;
        goto LABEL_47;
      }
      Instance = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, __int64))(*(_QWORD *)v36 + 264LL))(
                   v36,
                   &WPD_OBJECT_REFERENCES,
                   v46);
      if ( Instance < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_161;
        v22 = 385;
        goto LABEL_47;
      }
      Instance = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, const GUID *))(*(_QWORD *)v36 + 216LL))(
                   v36,
                   &WPD_OBJECT_CONTENT_TYPE,
                   &WPD_CONTENT_TYPE_PLAYLIST);
      if ( Instance < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_161;
        v22 = 386;
        goto LABEL_47;
      }
      Instance = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, _QWORD))(*(_QWORD *)v36 + 184LL))(
                   v36,
                   &WPD_OBJECT_IS_DRM_PROTECTED,
                   0);
      if ( Instance < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_161;
        v22 = 387;
        goto LABEL_47;
      }
      Instance = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, _QWORD))(*(_QWORD *)v36 + 104LL))(
                   v36,
                   &WPD_OBJECT_SIZE,
                   0);
      if ( Instance < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_161;
        v22 = 388;
        goto LABEL_47;
      }
      Instance = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, GUID *))(*(_QWORD *)v36 + 216LL))(
                   v36,
                   &WPD_OBJECT_FORMAT,
                   &Buf1);
      if ( Instance < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_161;
        v22 = 389;
        goto LABEL_47;
      }
      v25 = (_DWORD *)((char *)v20 + 104);
      if ( *((_DWORD *)v20 + 26) )
      {
        Instance = -2147023673;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_161;
        v22 = 390;
LABEL_47:
        WPP_SF_d(v21[2], v22, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)Instance);
LABEL_161:
        v29 = *((_DWORD *)v20 + 26) == 0;
        CProgressUI::_EndProgressUI(v20);
        (**(void (__fastcall ***)(CProgressUI *, __int64))v20)(v20, 1);
        v6 = (struct _IDA *)hMem;
        goto LABEL_170;
      }
      v60[0] = 0;
      LoadStringW(g_hInst, 0x2409u, pszPath, 260);
      for ( i = 1; ; StringCchPrintfW(pszPath, 0x104u, v60, i) )
      {
        DoesObjectNameExist = CContentContextMenuCB::_DoesObjectNameExist(this, pszPath, pvar.bstrVal, v40, v39);
        Instance = DoesObjectNameExist;
        if ( DoesObjectNameExist < 0 )
        {
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v22 = 391;
            goto LABEL_47;
          }
          goto LABEL_161;
        }
        if ( DoesObjectNameExist )
          break;
        if ( !v60[0] )
          LoadStringW(g_hInst, 0x240Au, v60, 260);
        ++i;
      }
      Instance = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, WCHAR *))(*(_QWORD *)v36 + 56LL))(
                   v36,
                   &WPD_OBJECT_ORIGINAL_FILE_NAME,
                   pszPath);
      if ( Instance < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v22 = 392;
          goto LABEL_47;
        }
        goto LABEL_161;
      }
      PathRemoveExtensionW(pszPath);
      Instance = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, WCHAR *))(*(_QWORD *)v36 + 56LL))(
                   v36,
                   &WPD_OBJECT_NAME,
                   pszPath);
      if ( Instance < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v22 = 393;
          goto LABEL_47;
        }
        goto LABEL_161;
      }
      if ( *v25 )
      {
        Instance = -2147023673;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v22 = 394;
          goto LABEL_47;
        }
        goto LABEL_161;
      }
      if ( !memcmp_0(&Buf1, &WPD_OBJECT_FORMAT_PROPERTIES_ONLY, 0x10u) )
      {
        Instance = ((__int64 (__fastcall *)(struct IPortableDeviceContent *, LPVOID, LPVOID *))v39->lpVtbl->CreateObjectWithPropertiesOnly)(
                     v39,
                     v36,
                     &pv);
        if ( Instance < 0 )
        {
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v22 = 395;
            goto LABEL_47;
          }
          goto LABEL_161;
        }
      }
      if ( memcmp_0(&Buf1, &WPD_OBJECT_FORMAT_MTP_ABSTRACTPLAYLIST, 0x10u) )
        goto LABEL_161;
      v50.Data1 = 0;
      Instance = ((__int64 (__fastcall *)(struct IPortableDeviceContent *, LPVOID, _QWORD **, struct _GUID *, LPVOID *))v39->lpVtbl->CreateObjectWithPropertiesAndData)(
                   v39,
                   v36,
                   &v47,
                   &v50,
                   &v51);
      if ( Instance < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v22 = 396;
          goto LABEL_47;
        }
        goto LABEL_161;
      }
      v28 = (__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*v47;
      if ( *v25 )
      {
        ((void (*)(void))v28[9])();
        Instance = -2147023673;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v22 = 397;
          goto LABEL_47;
        }
        goto LABEL_161;
      }
      Instance = ((__int64 (__fastcall *)(_QWORD *, _QWORD))v28[8])(v47, 0);
      if ( Instance < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v22 = 398;
          goto LABEL_47;
        }
        goto LABEL_161;
      }
      Instance = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*v47)(
                   v47,
                   &GUID_88e04db3_1012_4d64_9996_f703a950d3f4,
                   &v52);
      if ( Instance < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v22 = 399;
          goto LABEL_47;
        }
        goto LABEL_161;
      }
      Instance = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v52 + 112LL))(v52, &pv);
      if ( Instance < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v22 = 400;
          goto LABEL_47;
        }
      }
      v6 = (struct _IDA *)hMem;
    }
    v29 = 1;
    if ( !v20 )
      goto LABEL_170;
    goto LABEL_161;
  }
  Instance = -2147467259;
LABEL_169:
  v29 = 1;
LABEL_170:
  if ( !pv )
  {
    v31 = v48;
LABEL_179:
    v32 = pidl;
    goto LABEL_180;
  }
  v30 = CContentFolder::_CreateIDList(
          *((CContentFolder **)this + 4),
          v40,
          (const unsigned __int16 *)pv,
          0,
          &v48,
          (int *)&v50);
  v31 = v48;
  if ( v30 < 0 || (int)SHILCombine(*((_QWORD *)this + 5), v48, &pidl) < 0 )
    goto LABEL_179;
  ChangeNotify(0, 0x1000u, 0, 0);
  v32 = pidl;
  ChangeNotify(2, 0x1000u, pidl, 0);
  if ( IUnknown_QueryService(
         *((IUnknown **)this + 1),
         (const GUID *const)&SID_DefView,
         &GUID_000214e3_0000_0000_c000_000000000046,
         &ppvOut) >= 0 )
  {
    Sleep(0x7D0u);
    (*(void (__fastcall **)(void *, ITEMIDLIST *, __int64))(*(_QWORD *)ppvOut + 112LL))(ppvOut, v31, 7);
LABEL_180:
    v33 = hWnda;
    goto LABEL_181;
  }
  v33 = hWnda;
  v34 = SendMessageW(hWnda, 0x407u, 0, 0);
  if ( v34 >= 0x10000 && (*(int (__fastcall **)(unsigned __int64, void **))(*(_QWORD *)v34 + 120LL))(v34, &ppvOut) >= 0 )
    (*(void (__fastcall **)(void *, ITEMIDLIST *, __int64))(*(_QWORD *)ppvOut + 112LL))(ppvOut, v31, 7);
LABEL_181:
  if ( v6 )
    GlobalFree(v6);
  if ( v32 )
    ILFree(v32);
  if ( v31 )
    ILFree(v31);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v51 )
  {
    CoTaskMemFree(v51);
    v51 = 0;
  }
  PropVariantClear(&pvar);
  if ( Instance < 0 )
  {
    if ( v29 )
      ShellMessageBoxW(g_hInst, v33, (LPCWSTR)0x11E, (LPCWSTR)0x117, 0x10010u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        401,
        WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
        (unsigned int)Instance);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppvOut);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v53);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800311d8  mov     rax, rsp
0x1800311db  mov     [rax+20h], rbx
0x1800311df  push    rbp
0x1800311e0  push    rsi
0x1800311e1  push    rdi
0x1800311e2  push    r12
0x1800311e4  push    r13
0x1800311e6  push    r14
0x1800311e8  push    r15
0x1800311ea  lea     rbp, [rax-0CD8h]
0x1800311f1  sub     rsp, 0DA0h
0x1800311f8  movaps  xmmword ptr [rax-48h], xmm6
0x1800311fc  mov     rax, cs:__security_cookie
0x180031203  xor     rax, rsp
0x180031206  mov     [rbp+0CD0h+var_50], rax
0x18003120d  mov     rbx, r8
0x180031210  mov     r12, rdx
0x180031213  mov     [rsp+0DD0h+hWnd], rdx
0x180031218  mov     r13, rcx
0x18003121b  xorps   xmm0, xmm0
0x18003121e  xor     eax, eax
0x180031220  movups  xmmword ptr [rbp+0CD0h+pvar], xmm0
0x180031224  mov     qword ptr [rbp+0CD0h+pvar+10h], rax
0x180031228  xor     r14d, r14d
0x18003122b  mov     [rsp+0DD0h+pv], r14
0x180031230  mov     [rbp+0CD0h+var_D10], r14
0x180031234  mov     edi, 208h
0x180031239  mov     r8d, edi; Size
0x18003123c  xor     edx, edx; Val
0x18003123e  lea     rcx, [rbp+0CD0h+var_680]; void *
0x180031245  call    memset_0
0x18003124a  mov     [rbp+0CD0h+var_D40], r14
0x18003124e  mov     [rsp+0DD0h+pidl], r14
0x180031253  mov     r15d, r14d
0x180031256  mov     [rsp+0DD0h+hMem], r14
0x18003125b  mov     r8d, edi; Size
0x18003125e  xor     edx, edx; Val
0x180031260  lea     rcx, [rbp+0CD0h+var_470]; void *
0x180031267  call    memset_0
0x18003126c  mov     r8d, edi; Size
0x18003126f  xor     edx, edx; Val
0x180031271  lea     rcx, [rbp+0CD0h+var_260]; void *
0x180031278  call    memset_0
0x18003127d  mov     r8d, edi; Size
0x180031280  xor     edx, edx; Val
0x180031282  lea     rcx, [rbp+0CD0h+Buffer]; void *
0x180031289  call    memset_0
0x18003128e  mov     [rbp+0CD0h+var_D48], r14
0x180031292  mov     [rbp+0CD0h+var_D08], r14
0x180031296  mov     [rbp+0CD0h+var_D00], r14
0x18003129a  mov     [rsp+0DD0h+var_D80], r14
0x18003129f  mov     [rsp+0DD0h+var_D88], r14
0x1800312a4  mov     [rsp+0DD0h+var_DA0], r14
0x1800312a9  mov     [rbp+0CD0h+var_D50], r14
0x1800312ad  mov     [rsp+0DD0h+var_D90], r14
0x1800312b2  mov     [rsp+0DD0h+ppvOut], r14
0x1800312b7  movups  xmm6, xmmword ptr cs:WPD_OBJECT_FORMAT_PROPERTIES_ONLY.Data1
0x1800312be  movdqu  [rbp+0CD0h+Buf1], xmm6
0x1800312c3  movups  xmm0, xmmword ptr cs:WPD_CONTENT_TYPE_AUDIO.Data1
0x1800312ca  movdqu  xmmword ptr [rbp+0CD0h+var_CD0.Data1], xmm0
0x1800312cf  movups  xmm1, xmmword ptr cs:WPD_CONTENT_TYPE_VIDEO.Data1
0x1800312d6  movdqu  [rbp+0CD0h+var_CC0], xmm1
0x1800312db  mov     r8d, edi; Size
0x1800312de  xor     edx, edx; Val
0x1800312e0  lea     rcx, [rbp+0CD0h+var_890]; void *
0x1800312e7  call    memset_0
0x1800312ec  mov     r8d, edi; Size
0x1800312ef  xor     edx, edx; Val
0x1800312f1  lea     rcx, [rbp+0CD0h+pszPath]; void *
0x1800312f5  call    memset_0
0x1800312fa  mov     dword ptr [rsp+0DD0h+var_D78], r14d
0x1800312ff  movdqu  xmmword ptr [rbp+0CD0h+var_D20.Data1], xmm6
0x180031304  movups  xmm0, xmmword ptr cs:WPD_CONTENT_TYPE_PLAYLIST.Data1
0x18003130b  movdqu  xmmword ptr [rbp+0CD0h+var_CF0.Data1], xmm0
0x180031310  lea     r9, [rbp+0CD0h+var_D20]; struct _GUID
0x180031314  lea     r8, [rbp+0CD0h+var_CF0]; struct _GUID
0x180031318  mov     rdx, [r13+28h]; struct _ITEMIDLIST *
0x18003131c  call    ?_IsFormatSupportedByDevice@CContentFolder@@QEAAHPEFBU_ITEMIDLIST@@U_GUID@@1@Z; CContentFolder::_IsFormatSupportedByDevice(_ITEMIDLIST const *,_GUID,_GUID)
0x180031321  lea     rsi, WPP_GLOBAL_Control
0x180031328  lea     edi, [r14+2]
0x18003132c  test    eax, eax
0x18003132e  jz      short loc_180031339
0x180031330  movups  xmm0, xmmword ptr cs:WPD_OBJECT_FORMAT_PROPERTIES_ONLY.Data1
0x180031337  jmp     short loc_180031371
0x180031339  movups  xmm0, cs:WPD_OBJECT_FORMAT_MTP_ABSTRACTPLAYLIST
0x180031340  movdqu  xmmword ptr [rbp+0CD0h+var_CF0.Data1], xmm0
0x180031345  movups  xmm1, xmmword ptr cs:WPD_CONTENT_TYPE_PLAYLIST.Data1
0x18003134c  movdqu  xmmword ptr [rbp+0CD0h+var_D20.Data1], xmm1
0x180031351  lea     r9, [rbp+0CD0h+var_CF0]; struct _GUID
0x180031355  lea     r8, [rbp+0CD0h+var_D20]; struct _GUID
0x180031359  mov     rdx, [r13+28h]; struct _ITEMIDLIST *
0x18003135d  call    ?_IsFormatSupportedByDevice@CContentFolder@@QEAAHPEFBU_ITEMIDLIST@@U_GUID@@1@Z; CContentFolder::_IsFormatSupportedByDevice(_ITEMIDLIST const *,_GUID,_GUID)
0x180031362  test    eax, eax
0x180031364  jz      loc_180031FD8
0x18003136a  movups  xmm0, cs:WPD_OBJECT_FORMAT_MTP_ABSTRACTPLAYLIST
0x180031371  movdqu  [rbp+0CD0h+Buf1], xmm0
0x180031376  xorps   xmm0, xmm0
0x180031379  xor     eax, eax
0x18003137b  movups  xmmword ptr [rbp+0CD0h+pvar], xmm0
0x18003137f  mov     qword ptr [rbp+0CD0h+pvar+10h], rax
0x180031383  lea     rdx, [rsp+0DD0h+hMem]; struct _IDA **
0x180031388  mov     rcx, rbx; struct IDataObject *
0x18003138b  call    ?DataObj_CopyHIDA@@YAJPEAUIDataObject@@PEAPEAU_IDA@@@Z; DataObj_CopyHIDA(IDataObject *,_IDA * *)
0x180031390  mov     ebx, eax
0x180031392  test    eax, eax
0x180031394  jns     short loc_1800313CA
0x180031396  mov     rcx, cs:WPP_GLOBAL_Control
0x18003139d  cmp     rcx, rsi
0x1800313a0  jz      short loc_1800313C0
0x1800313a2  test    [rcx+1Ch], dil
0x1800313a6  jz      short loc_1800313C0
0x1800313a8  mov     edx, 16Fh
0x1800313ad  mov     r9d, eax
0x1800313b0  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x1800313b7  mov     rcx, [rcx+10h]
0x1800313bb  call    WPP_SF_d
0x1800313c0  mov     r15, [rsp+0DD0h+hMem]
0x1800313c5  jmp     loc_180032007
0x1800313ca  mov     r15, [rsp+0DD0h+hMem]
0x1800313cf  test    r15, r15
0x1800313d2  jnz     short loc_1800313DE
0x1800313d4  mov     ebx, 80004005h
0x1800313d9  jmp     loc_180032007
0x1800313de  mov     esi, 1
0x1800313e3  cmp     [r15], r14d
0x1800313e6  jnz     short loc_1800313F0
0x1800313e8  mov     ebx, r14d
0x1800313eb  jmp     loc_18003200C
0x1800313f0  lea     rax, [rsp+0DD0h+var_D90]
0x1800313f5  mov     [rsp+0DD0h+ppv], rax; ppv
0x1800313fa  lea     r9, _GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3; riid
0x180031401  mov     r8d, esi; dwClsContext
0x180031404  xor     edx, edx; pUnkOuter
0x180031406  lea     rcx, CLSID_PortableDevicePropVariantCollection; rclsid
0x18003140d  call    cs:__imp_CoCreateInstance
0x180031413  mov     ebx, eax
0x180031415  test    eax, eax
0x180031417  jns     short loc_180031457
0x180031419  mov     rcx, cs:WPP_GLOBAL_Control
0x180031420  lea     rax, WPP_GLOBAL_Control
0x180031427  cmp     rcx, rax
0x18003142a  jz      loc_18003200C
0x180031430  test    [rcx+1Ch], dil
0x180031434  jz      loc_18003200C
0x18003143a  mov     edx, 170h
0x18003143f  mov     r9d, ebx
0x180031442  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180031449  mov     rcx, [rcx+10h]
0x18003144d  call    WPP_SF_d
0x180031452  jmp     loc_18003200C
0x180031457  lea     rax, [rsp+0DD0h+var_DA0]
0x18003145c  mov     [rsp+0DD0h+ppv], rax; ppv
0x180031461  lea     r9, _GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143; riid
0x180031468  mov     r8d, esi; dwClsContext
0x18003146b  xor     edx, edx; pUnkOuter
0x18003146d  lea     rcx, CLSID_PortableDeviceValues; rclsid
0x180031474  call    cs:__imp_CoCreateInstance
0x18003147a  mov     ebx, eax
0x18003147c  test    eax, eax
0x18003147e  jns     short loc_1800314A8
0x180031480  mov     rcx, cs:WPP_GLOBAL_Control
0x180031487  lea     rax, WPP_GLOBAL_Control
0x18003148e  cmp     rcx, rax
0x180031491  jz      loc_18003200C
0x180031497  test    [rcx+1Ch], dil
0x18003149b  jz      loc_18003200C
0x1800314a1  mov     edx, 171h
0x1800314a6  jmp     short loc_18003143F
0x1800314a8  mov     rcx, [r13+20h]
0x1800314ac  mov     rcx, [rcx+40h]; pidl
0x1800314b0  call    cs:__imp_ILFindLastID
0x1800314b6  mov     rdx, rax; struct _ITEMIDLIST *
0x1800314b9  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x1800314be  mov     r14d, 104h
0x1800314c4  test    rax, rax
0x1800314c7  jz      loc_180031555
0x1800314cd  mov     edx, [rax+42h]
0x1800314d0  mov     ecx, [rax+3Eh]
0x1800314d3  add     rcx, 25h ; '%'
0x1800314d7  add     rdx, rcx
0x1800314da  lea     r8, [rax+rdx*2]; unsigned __int16 *
0x1800314de  mov     edx, r14d; unsigned __int64
0x1800314e1  lea     rcx, [rbp+0CD0h+var_680]; unsigned __int16 *
0x1800314e8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800314ed  mov     eax, 1Fh
0x1800314f2  mov     word ptr [rbp+0CD0h+pvar], ax
0x1800314f6  lea     rax, [rbp+0CD0h+var_680]
0x1800314fd  mov     qword ptr [rbp+0CD0h+pvar+8], rax
0x180031501  mov     rcx, [rsp+0DD0h+var_D90]
0x180031506  mov     rax, [rcx]
0x180031509  lea     rdx, [rbp+0CD0h+pvar]
0x18003150d  mov     rax, [rax+28h]
0x180031511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031516  mov     ebx, eax
0x180031518  xor     eax, eax
0x18003151a  mov     word ptr [rbp+0CD0h+pvar], ax
0x18003151e  mov     qword ptr [rbp+0CD0h+pvar+8], rax
0x180031522  test    ebx, ebx
0x180031524  jns     loc_1800315AB
0x18003152a  mov     rcx, cs:WPP_GLOBAL_Control
0x180031531  lea     rax, WPP_GLOBAL_Control
0x180031538  cmp     rcx, rax
0x18003153b  jz      loc_18003200C
0x180031541  test    [rcx+1Ch], dil
0x180031545  jz      loc_18003200C
0x18003154b  mov     edx, 173h
0x180031550  jmp     loc_18003143F
0x180031555  mov     rcx, [r13+20h]
0x180031559  mov     rax, [rcx]
0x18003155c  mov     r9d, r14d
0x18003155f  lea     r8, [rbp+0CD0h+var_680]
0x180031566  mov     rdx, [r13+28h]
0x18003156a  mov     rax, [rax+0B8h]
0x180031571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031576  mov     ebx, eax
0x180031578  test    eax, eax
0x18003157a  jns     loc_1800314ED
0x180031580  mov     rcx, cs:WPP_GLOBAL_Control
0x180031587  lea     rax, WPP_GLOBAL_Control
0x18003158e  cmp     rcx, rax
0x180031591  jz      loc_18003200C
0x180031597  test    [rcx+1Ch], dil
0x18003159b  jz      loc_18003200C
0x1800315a1  mov     edx, 172h
0x1800315a6  jmp     loc_18003143F
0x1800315ab  mov     rcx, [r13+20h]
0x1800315af  mov     rax, [rcx]
0x1800315b2  mov     r9d, r14d
0x1800315b5  lea     r8, [rbp+0CD0h+var_470]
0x1800315bc  mov     rdx, [rcx+40h]
0x1800315c0  mov     rax, [rax+90h]
0x1800315c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800315cc  mov     ebx, eax
0x1800315ce  test    eax, eax
0x1800315d0  jns     short loc_1800315FD
0x1800315d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800315d9  lea     rax, WPP_GLOBAL_Control
0x1800315e0  cmp     rcx, rax
0x1800315e3  jz      loc_18003200C
0x1800315e9  test    [rcx+1Ch], dil
0x1800315ed  jz      loc_18003200C
0x1800315f3  mov     edx, 174h
0x1800315f8  jmp     loc_18003143F
0x1800315fd  mov     rcx, [r13+20h]
0x180031601  mov     rax, [rcx]
0x180031604  mov     r8d, r14d
0x180031607  lea     rdx, [rbp+0CD0h+var_260]
0x18003160e  mov     rax, [rax+60h]
0x180031612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031617  mov     ebx, eax
0x180031619  test    eax, eax
0x18003161b  jns     short loc_180031648
0x18003161d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031624  lea     rax, WPP_GLOBAL_Control
0x18003162b  cmp     rcx, rax
0x18003162e  jz      loc_18003200C
0x180031634  test    [rcx+1Ch], dil
0x180031638  jz      loc_18003200C
0x18003163e  mov     edx, 175h
0x180031643  jmp     loc_18003143F
0x180031648  mov     ecx, 0B08h; unsigned __int64
0x18003164d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180031652  mov     qword ptr [rbp+0CD0h+var_D20.Data1], rax
0x180031656  test    rax, rax
0x180031659  jz      loc_180031FD1
0x18003165f  mov     rcx, rax; this
0x180031662  call    ??0CProgressUI@@QEAA@XZ; CProgressUI::CProgressUI(void)
0x180031667  mov     rdi, rax
0x18003166a  test    rax, rax
0x18003166d  jz      loc_180031FD1
0x180031673  mov     r9d, 4; int
0x180031679  mov     r8d, esi; int
0x18003167c  lea     rdx, [rbp+0CD0h+var_470]; unsigned __int16 *
0x180031683  mov     rcx, rax; this
0x180031686  call    ?_Initialize@CProgressUI@@QEAAJPEBGHH@Z; CProgressUI::_Initialize(ushort const *,int,int)
0x18003168b  mov     ebx, eax
0x18003168d  test    eax, eax
0x18003168f  jns     short loc_1800316CF
0x180031691  mov     rcx, cs:WPP_GLOBAL_Control
0x180031698  lea     rax, WPP_GLOBAL_Control
0x18003169f  cmp     rcx, rax
0x1800316a2  jz      loc_180031F84
0x1800316a8  test    byte ptr [rcx+1Ch], 2
0x1800316ac  jz      loc_180031F84
0x1800316b2  mov     edx, 176h
0x1800316b7  mov     r9d, ebx
0x1800316ba  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x1800316c1  mov     rcx, [rcx+10h]
0x1800316c5  call    WPP_SF_d
0x1800316ca  jmp     loc_180031F84
0x1800316cf  mov     edx, 2; enum _SPACTION
0x1800316d4  lea     r8d, [rdx+6Fh]; unsigned int
0x1800316d8  mov     rcx, rdi; this
0x1800316db  call    ?_BeginProgressUI@CProgressUI@@QEAAJW4_SPACTION@@I@Z; CProgressUI::_BeginProgressUI(_SPACTION,uint)
0x1800316e0  mov     ebx, eax
0x1800316e2  test    eax, eax
0x1800316e4  jns     short loc_18003170E
0x1800316e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800316ed  lea     rax, WPP_GLOBAL_Control
0x1800316f4  cmp     rcx, rax
  ... truncated ...
```
