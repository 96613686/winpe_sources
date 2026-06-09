# CContentFolder::GetUIObjectOf(HWND__ *,uint,_ITEMIDLIST const * *,_GUID const &,uint *,void * *)

- ea: `0x180001da0`
- end: `0x180002a7a`
- name: `?GetUIObjectOf@CContentFolder@@UEAAJPEAUHWND__@@IPEAPEFBU_ITEMIDLIST@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `3290`
- prototype: `int(CContentFolder *__hidden this, HWND, unsigned int, const struct _ITEMIDLIST **, const struct _GUID *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001da0`
- `0x180002a80`
- `0x180004110`
- `0x1800082e0`
- `0x18001d860`
- `0x1800285c8`
- `0x1800287d0`
- `0x18002ff5c`
- `0x180035590`
- `0x18003a650`
- `0x180046108`
- `0x18004663c`
- `0x18005f93c`
- `0x1800607fc`
- `0x180062144`
- `0x1800621ec`
- `0x180062f08`
- `0x18007559c`
- `0x180078010`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180001f1e`
- `SHLWAPI!PathFindFileNameW` at `0x180001f1e`
- `SHELL32!SHCreateDefaultContextMenu` at `0x18000267d`
- `SHELL32!SHCreateDefaultContextMenu` at `0x18000267d`
- `SHELL32!__imp_ILCombine` at `0x180001f9e`
- `SHELL32!__imp_ILCombine` at `0x180001f9e`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180002743`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180002743`
- `SHELL32!__imp_ILFree` at `0x180002240`
- `SHELL32!__imp_ILFree` at `0x180002997`
- `SHELL32!__imp_ILFree` at `0x180002240`
- `SHELL32!__imp_ILFree` at `0x180002997`
- `SHELL32!__imp_SHCreateFileExtractIconW` at `0x180001f2f`
- `SHELL32!__imp_SHCreateFileExtractIconW` at `0x180001f2f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CContentFolder::GetUIObjectOf(
        LPCITEMIDLIST *this,
        HWND a2,
        unsigned int a3,
        const struct _ITEMIDLIST **a4,
        const struct _GUID *riid,
        unsigned int *a6,
        void **ppv)
{
  LPCITEMIDLIST *v10; // r10
  unsigned int Instance; // esi
  const struct CONTENTITEM *v12; // rbx
  __int64 v13; // rax
  BOOL v14; // r13d
  int v15; // esi
  int v16; // edx
  __int64 v17; // rcx
  __int64 v18; // rax
  WCHAR *v19; // rdx
  __int64 v20; // rbx
  WCHAR *v21; // r9
  WCHAR v22; // cx
  WCHAR *v23; // rcx
  const WCHAR *FileNameW; // rax
  HRESULT DataObject; // eax
  PVOID *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // r9
  int v29; // eax
  ITEMIDLIST *v30; // r14
  GUID v31; // xmm0
  __int64 v32; // r11
  __int64 (__fastcall *v33)(__int64, ITEMIDLIST *, unsigned __int16 *, GUID *, _DWORD, BOOL, int, const struct _GUID *, void **); // r10
  int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // r9
  __int64 v37; // rax
  int v38; // eax
  GUID fmtid; // xmm0
  DWORD pid; // eax
  LPCITEMIDLIST *v41; // r13
  int v42; // eax
  __int64 (__fastcall *v43)(LPCITEMIDLIST *, IQueryAssociations *, unsigned __int16 *, GUID *, const struct _GUID *, void **); // r10
  __int64 v44; // rax
  LPCITEMIDLIST *v45; // rdi
  LPCITEMIDLIST *v46; // rbx
  struct IDataObject *v47; // r9
  CContentFolder *v48; // rcx
  unsigned int v49; // ebx
  __int64 v50; // rdi
  const struct CONTENTITEM *v51; // rax
  __int64 v52; // rax
  CContentFolder *v53; // r13
  int v54; // eax
  _QWORD *v55; // rcx
  __int64 v56; // rdx
  CContentFolder *v57; // rcx
  const struct _GUID *v58; // r8
  int v59; // ebx
  UINT v60; // ebx
  IShellFolder *v61; // rax
  LPCITEMIDLIST *v62; // r10
  __int64 v63; // rax
  __int64 v64; // rax
  int v65; // eax
  int v66; // eax
  _QWORD *v67; // rcx
  __int64 v68; // rdx
  _QWORD *v69; // rbx
  ITEMIDLIST *v70; // rcx
  IQueryAssociations *pqa; // [rsp+60h] [rbp-A0h] BYREF
  IQueryAssociations *v73; // [rsp+68h] [rbp-98h] BYREF
  struct IContextMenuCB *v74; // [rsp+70h] [rbp-90h] BYREF
  LPCITEMIDLIST *v75; // [rsp+78h] [rbp-88h]
  DEFCONTEXTMENU pdcm; // [rsp+80h] [rbp-80h] BYREF
  GUID Buf2; // [rsp+D0h] [rbp-30h] BYREF
  DWORD v78; // [rsp+E0h] [rbp-20h]
  HKEY rgKeys[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v80; // [rsp+100h] [rbp+0h]
  __int128 v81; // [rsp+110h] [rbp+10h]
  WCHAR pszPath[264]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v83[264]; // [rsp+330h] [rbp+230h] BYREF
  unsigned __int16 v84[264]; // [rsp+540h] [rbp+440h] BYREF

  *(_QWORD *)&Buf2.Data1 = a2;
  v10 = this;
  v75 = this;
  pqa = 0;
  if ( !ppv )
  {
    Instance = -2147467261;
LABEL_177:
    v26 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_178;
  }
  if ( a3 && !a4 )
  {
    Instance = -2147024809;
    goto LABEL_177;
  }
  *ppv = 0;
  if ( a3 )
  {
    v12 = CContentFolder::_IsValid((CContentFolder *)this, *a4);
    v10 = v75;
  }
  else
  {
    v12 = 0;
  }
  v13 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IExtractIconW.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IExtractIconW.Data1 )
    v13 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IExtractIconW.Data4;
  if ( v13 || !v12 )
  {
    v37 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IExtractImage.Data1;
    if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IExtractImage.Data1 )
      v37 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IExtractImage.Data4;
    if ( !v37 && v12 )
    {
      v38 = *(_DWORD *)((char *)v12 + 14);
      if ( (v38 & 0x20000) != 0 )
      {
        fmtid = WPD_RESOURCE_THUMBNAIL.fmtid;
        pid = WPD_RESOURCE_THUMBNAIL.pid;
      }
      else if ( (v38 & 0x100000) != 0 )
      {
        fmtid = WPD_RESOURCE_ALBUM_ART.fmtid;
        pid = WPD_RESOURCE_ALBUM_ART.pid;
      }
      else if ( (v38 & 0x10000) != 0 )
      {
        fmtid = WPD_RESOURCE_CONTACT_PHOTO.fmtid;
        pid = WPD_RESOURCE_CONTACT_PHOTO.pid;
      }
      else
      {
        if ( (v38 & 0x1000) == 0 )
        {
          Instance = -2147467262;
          v26 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            return Instance;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_178;
          v27 = 45;
          v28 = 2147500034LL;
          goto LABEL_31;
        }
        fmtid = WPD_PROPERTY_NULL.fmtid;
        pid = WPD_PROPERTY_NULL.pid;
      }
      v78 = pid;
      Buf2 = fmtid;
      v41 = v10 - 2;
      v42 = SHILCombine(v10[6], *a4, &pqa);
      Instance = v42;
      if ( v42 >= 0 )
      {
        StringCchCopyW(
          v83,
          0x104u,
          (const unsigned __int16 *)v12 + *(unsigned int *)((char *)v12 + 62) + *(unsigned int *)((char *)v12 + 66) + 37);
        v30 = (ITEMIDLIST *)pqa;
        v34 = v43(v41, pqa, v83, &Buf2, riid, ppv);
        Instance = v34;
        if ( v34 >= 0 )
          goto LABEL_69;
        v26 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_70;
        v35 = 47;
        goto LABEL_40;
      }
      v26 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
        v30 = (ITEMIDLIST *)pqa;
LABEL_70:
        if ( !v30 )
          goto LABEL_139;
        ILFree(v30);
LABEL_138:
        v26 = (PVOID *)WPP_GLOBAL_Control;
LABEL_139:
        if ( (Instance & 0x80000000) == 0 )
          return Instance;
        goto LABEL_178;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
        (unsigned int)v42);
      v30 = (ITEMIDLIST *)pqa;
LABEL_69:
      v26 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_70;
    }
    v44 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IDataObject.Data1;
    if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IDataObject.Data1 )
      v44 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IDataObject.Data4;
    if ( !v44 && a3 )
    {
      *(_QWORD *)&Buf2.Data1 = 0;
      pqa = 0;
      v45 = v10 - 2;
      DataObject = (*(__int64 (__fastcall **)(LPCITEMIDLIST *, unsigned __int16 *, __int64))&(*(v10 - 2))[32].mkid.cb)(
                     v10 - 2,
                     v84,
                     260);
      Instance = DataObject;
      if ( DataObject >= 0 )
      {
        DataObject = StringCbLengthW(v84, 0x208u, (unsigned __int64 *)&Buf2.Data1);
        Instance = DataObject;
        if ( DataObject >= 0 )
        {
          v46 = v75;
          DataObject = (*(__int64 (__fastcall **)(LPCITEMIDLIST *, LPCITEMIDLIST, WCHAR *, __int64))((char *)&(*v45)[61].mkid.cb + 1))(
                         v45,
                         v75[6],
                         pszPath,
                         260);
          Instance = DataObject;
          if ( DataObject >= 0 )
          {
            DataObject = StringCbLengthW(pszPath, 0x208u, (unsigned __int64 *)&pqa);
            Instance = DataObject;
            if ( DataObject >= 0 )
            {
              DataObject = CreateDataObject(v46[6], a3, a4, v47, (struct IDataObject **)ppv);
              Instance = DataObject;
              if ( DataObject >= 0 )
              {
                v49 = -1;
                v50 = 0;
                do
                {
                  v51 = CContentFolder::_IsValid(v48, a4[v50]);
                  if ( v51 )
                    v49 &= *(_DWORD *)((char *)v51 + 10);
                  v50 = (unsigned int)(v50 + 1);
                }
                while ( (unsigned int)v50 < a3 );
                DataObj_SetDWORD(*ppv, g_cfWPD_ATTRIBUTES, v49);
                DataObj_SetDWORD(*ppv, g_cfPreferredDropEffect, 1);
                DataObj_SetDWORD(*ppv, g_cfWPDShellExtension, 1);
                DataObj_SetBlob(*ppv, g_cfPnPDevicePath, v84, Buf2.Data1);
                DataObj_SetBlob(*ppv, g_cfStoragePersistentUniqueID, pszPath, (unsigned int)pqa);
                return Instance;
              }
              v26 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                return Instance;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                goto LABEL_178;
              v27 = 52;
            }
            else
            {
              v26 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                return Instance;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                goto LABEL_178;
              v27 = 51;
            }
          }
          else
          {
            v26 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return Instance;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_178;
            v27 = 50;
          }
        }
        else
        {
          v26 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            return Instance;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_178;
          v27 = 49;
        }
      }
      else
      {
        v26 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return Instance;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_178;
        v27 = 48;
      }
LABEL_30:
      v28 = (unsigned int)DataObject;
LABEL_31:
      WPP_SF_d(v26[2], v27, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v28);
      goto LABEL_177;
    }
    v52 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
    if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
      v52 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
    if ( !v52 && v12 )
    {
      v53 = (CContentFolder *)(v10 - 2);
      if ( (*((_BYTE *)v12 + 10) & 2) == 0 )
      {
        v73 = 0;
        Instance = CContentFolder::_ContextMenuCBCreate((CContentFolder *)(v10 - 2), (struct IContextMenuCB **)&v73, 0);
        if ( (Instance & 0x80000000) == 0 )
        {
          pqa = 0;
          Instance = SHCoCreateInstance(
                       0,
                       &CLSID_DefFolderMenu,
                       0,
                       &GUID_7690aa79_f8fc_4615_a327_36f7d18f5d91,
                       (void **)&pqa);
          if ( (Instance & 0x80000000) == 0 )
          {
            v62 = v75;
            if ( !v53 )
              v62 = 0;
            Instance = ((__int64 (__fastcall *)(IQueryAssociations *, _QWORD, IQueryAssociations *, LPCITEMIDLIST, LPCITEMIDLIST *, unsigned int, const struct _ITEMIDLIST **, _QWORD, _DWORD, _QWORD))pqa->lpVtbl->GetData)(
                         pqa,
                         *(_QWORD *)&Buf2.Data1,
                         v73,
                         v75[6],
                         v62,
                         a3,
                         a4,
                         0,
                         0,
                         0);
            if ( (Instance & 0x80000000) == 0 )
            {
              Instance = ((__int64 (__fastcall *)(IQueryAssociations *, __int64))pqa->lpVtbl->GetEnum)(pqa, 16);
              if ( (Instance & 0x80000000) == 0 )
                Instance = ((__int64 (__fastcall *)(IQueryAssociations *, const struct _GUID *, void **))pqa->lpVtbl->Init)(
                             pqa,
                             riid,
                             ppv);
            }
            ((void (__fastcall *)(IQueryAssociations *))pqa->lpVtbl->GetKey)(pqa);
          }
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v73);
        goto LABEL_138;
      }
      pqa = 0;
      v73 = 0;
      *(_OWORD *)rgKeys = 0;
      v80 = 0;
      v81 = 0;
      v54 = (*(__int64 (__fastcall **)(LPCITEMIDLIST *, _QWORD, __int64, const struct _ITEMIDLIST **, GUID *, _QWORD, IQueryAssociations **))(*v10)[26].mkid.abID)(
              v10,
              *(_QWORD *)&Buf2.Data1,
              1,
              a4,
              &IID_IQueryAssociations,
              0,
              &pqa);
      Instance = v54;
      if ( v54 >= 0 )
      {
        LODWORD(v74) = SHGetAssocKeys(pqa, rgKeys, 3u);
        v54 = CContentFolder::_ContextAssocCreate(v57, v12, v58, (void **)&v73);
        Instance = v54;
        if ( v54 >= 0 )
        {
          v59 = (int)v74;
          v60 = SHGetAssocKeys(v73, &rgKeys[(unsigned int)v74], 6 - (_DWORD)v74) + v59;
          v74 = 0;
          Instance = CContentFolder::_ContextMenuCBCreate(v53, &v74, 0);
          if ( (Instance & 0x80000000) == 0 )
          {
            pdcm.hwnd = *(HWND *)&Buf2.Data1;
            pdcm.pcmcb = v74;
            pdcm.pidlFolder = v75[6];
            v61 = 0;
            if ( v53 )
              v61 = (IShellFolder *)v75;
            pdcm.psf = v61;
            pdcm.cidl = a3;
            *(&pdcm.cidl + 1) = 0;
            pdcm.apidl = a4;
            pdcm.punkAssociationInfo = 0;
            pdcm.cKeys = v60;
            *(&pdcm.cKeys + 1) = 0;
            pdcm.aKeys = rgKeys;
            Instance = SHCreateDefaultContextMenu(&pdcm, riid, ppv);
          }
          SHRegCloseKeys(rgKeys, v60);
          if ( (Instance & 0x80000000) == 0 )
          {
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v74);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v73);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pqa);
            return Instance;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, Instance);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v74);
          goto LABEL_114;
        }
        v55 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
LABEL_114:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v73);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pqa);
          goto LABEL_177;
        }
        v56 = 54;
      }
      else
      {
        v55 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_114;
        v56 = 53;
      }
      WPP_SF_d(v55[2], v56, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)v54);
      goto LABEL_114;
    }
    v63 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IQueryAssociations.Data1;
    if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IQueryAssociations.Data1 )
      v63 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IQueryAssociations.Data4;
    if ( !v63 && v12 )
    {
      DataObject = CContentFolder::_AssocCreate((CContentFolder *)this, v12, riid, ppv);
      Instance = DataObject;
      if ( DataObject >= 0 )
        return Instance;
      v26 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return Instance;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_178;
      v27 = 56;
      goto LABEL_30;
    }
    v64 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IDropTarget.Data1;
    if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IDropTarget.Data1 )
      v64 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IDropTarget.Data4;
    if ( v64 || !v12 )
    {
      Instance = -2147467262;
      goto LABEL_177;
    }
    v65 = *(_DWORD *)((char *)v12 + 10);
    if ( (v65 & 2) == 0 )
    {
      Instance = -2147467262;
      if ( (v65 & 0x41) != 0x40 )
        goto LABEL_177;
      v69 = v10 + 18;
      v70 = (ITEMIDLIST *)v10[18];
      if ( v70 )
        ILFree(v70);
      *v69 = 0;
      DataObject = SHILCloneFirst(*a4, v69);
      Instance = DataObject;
      if ( DataObject >= 0 )
      {
        DataObject = (*(__int64 (__fastcall **)(LPCITEMIDLIST *, HWND, const struct _GUID *, void **))((char *)&(*v75)[21].mkid.cb + 1))(
                       v75,
                       a2,
                       riid,
                       ppv);
        Instance = DataObject;
        if ( DataObject >= 0 )
          return Instance;
        v26 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return Instance;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_178;
        v27 = 61;
      }
      else
      {
        v26 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return Instance;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_178;
        v27 = 60;
      }
      goto LABEL_30;
    }
    pqa = 0;
    v66 = (*(__int64 (__fastcall **)(LPCITEMIDLIST *, _QWORD, _QWORD, GUID *, IQueryAssociations **))((char *)&(*v10)[13].mkid.cb + 1))(
            v10,
            *a4,
            0,
            &IID_IShellFolder,
            &pqa);
    Instance = v66;
    if ( v66 >= 0 )
    {
      v66 = ((__int64 (__fastcall *)(IQueryAssociations *, HWND, const struct _GUID *, void **))pqa->lpVtbl[1].GetData)(
              pqa,
              a2,
              riid,
              ppv);
      Instance = v66;
      if ( v66 >= 0 )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pqa);
        return Instance;
      }
      v67 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_159;
      v68 = 59;
    }
    else
    {
      v67 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_159;
      v68 = 58;
    }
    WPP_SF_d(v67[2], v68, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)v66);
LABEL_159:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pqa);
    goto LABEL_177;
  }
  v14 = (*(_DWORD *)((_BYTE *)v12 + 14) & 0x40000) != 0;
  v15 = (*(_DWORD *)((char *)v12 + 14) >> 19) & 1;
  if ( (*((_BYTE *)v12 + 10) & 2) != 0 )
  {
    v16 = 16;
    goto LABEL_33;
  }
  if ( (*(_DWORD *)((_BYTE *)v12 + 14) & 0x40000) != 0
    || (Buf2 = *(GUID *)((char *)v12 + 42), !memcmp_0(&WPD_CONTENT_TYPE_PLAYLIST, &Buf2, 0x10u)) )
  {
    v16 = 0;
    v10 = v75;
LABEL_33:
    v29 = -4;
    if ( !v16 )
      v29 = -1;
    LODWORD(v74) = v29;
    v30 = ILCombine(v10[6], *a4);
    if ( !v30 )
    {
      Instance = -2147024882;
      v26 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_70;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          69,
          &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids,
          2147942414LL);
        v26 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v26 == &WPP_GLOBAL_Control || (*((_BYTE *)v26 + 28) & 2) == 0 )
        goto LABEL_70;
      v35 = 42;
      v36 = 2147942414LL;
      goto LABEL_41;
    }
    v31 = *(GUID *)((char *)v12 + 42);
    StringCchCopyW(
      v83,
      0x104u,
      (const unsigned __int16 *)v12 + *(unsigned int *)((char *)v12 + 62) + *(unsigned int *)((char *)v12 + 66) + 37);
    Buf2 = v31;
    v34 = v33(v32 - 16, v30, v83, &Buf2, (_DWORD)v74, v14, v15, riid, ppv);
    Instance = v34;
    if ( v34 < 0 )
    {
      v26 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_70;
      v35 = 43;
LABEL_40:
      v36 = (unsigned int)v34;
LABEL_41:
      WPP_SF_d(v26[2], v35, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v36);
      goto LABEL_69;
    }
    goto LABEL_69;
  }
  if ( *(_DWORD *)((char *)v12 + 66) <= 1u )
    v17 = 74;
  else
    v17 = 2LL * *(unsigned int *)((char *)v12 + 62) + 74;
  v18 = 2147483646;
  v19 = (WCHAR *)((char *)v12 + v17);
  v20 = 260;
  v21 = pszPath;
  do
  {
    if ( !v18 )
      break;
    v22 = *v19;
    if ( !*v19 )
      break;
    ++v19;
    *v21++ = v22;
    --v18;
    --v20;
  }
  while ( v20 );
  v23 = v21 - 1;
  if ( v20 )
    v23 = v21;
  *v23 = 0;
  FileNameW = PathFindFileNameW(pszPath);
  DataObject = SHCreateFileExtractIconW(FileNameW, 0, riid, ppv);
  Instance = DataObject;
  if ( DataObject < 0 )
  {
    v26 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_178:
        if ( v26 != &WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 2) != 0 )
          WPP_SF_d(v26[2], 62, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, Instance);
        return Instance;
      }
      v27 = 44;
      goto LABEL_30;
    }
  }
  return Instance;
}

```

## disassembly

```asm
0x180001da0  push    rbp
0x180001da2  push    rbx
0x180001da3  push    rsi
0x180001da4  push    rdi
0x180001da5  push    r12
0x180001da7  push    r13
0x180001da9  push    r14
0x180001dab  push    r15
0x180001dad  lea     rbp, [rsp-668h]
0x180001db5  sub     rsp, 768h
0x180001dbc  mov     rax, cs:__security_cookie
0x180001dc3  xor     rax, rsp
0x180001dc6  mov     [rbp+6A0h+var_50], rax
0x180001dcd  mov     r15, r9
0x180001dd0  mov     r14d, r8d
0x180001dd3  mov     r13, rdx
0x180001dd6  mov     qword ptr [rbp+6A0h+Buf2], rdx
0x180001dda  mov     r10, rcx
0x180001ddd  mov     [rsp+7A0h+var_728], rcx
0x180001de2  mov     rdi, [rbp+6A0h+riid]
0x180001de9  mov     r12, [rbp+6A0h+ppv]
0x180001df0  mov     [rsp+7A0h+pqa], 0
0x180001df9  test    r12, r12
0x180001dfc  jnz     short loc_180001E08
0x180001dfe  mov     esi, 80004003h
0x180001e03  jmp     loc_180002A24
0x180001e08  test    r14d, r14d
0x180001e0b  jz      short loc_180001E1C
0x180001e0d  test    r15, r15
0x180001e10  jnz     short loc_180001E1C
0x180001e12  mov     esi, 80070057h
0x180001e17  jmp     loc_180002A24
0x180001e1c  mov     qword ptr [r12], 0
0x180001e24  test    r14d, r14d
0x180001e27  jz      short loc_180001E3B
0x180001e29  mov     rdx, [r9]; struct _ITEMIDLIST *
0x180001e2c  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x180001e31  mov     rbx, rax
0x180001e34  mov     r10, [rsp+7A0h+var_728]
0x180001e39  jmp     short loc_180001E3D
0x180001e3b  xor     ebx, ebx
0x180001e3d  mov     rax, [rdi]
0x180001e40  sub     rax, qword ptr cs:IID_IExtractIconW.Data1
0x180001e47  jnz     short loc_180001E54
0x180001e49  mov     rax, [rdi+8]
0x180001e4d  sub     rax, qword ptr cs:IID_IExtractIconW.Data4
0x180001e54  test    rax, rax
0x180001e57  jnz     loc_1800020C2
0x180001e5d  test    rbx, rbx
0x180001e60  jz      loc_1800020C2
0x180001e66  mov     esi, [rbx+0Eh]
0x180001e69  mov     eax, esi
0x180001e6b  and     eax, 40000h
0x180001e70  mov     r13d, 0
0x180001e76  setnz   r13b
0x180001e7a  shr     esi, 13h
0x180001e7d  and     esi, 1
0x180001e80  test    byte ptr [rbx+0Ah], 2
0x180001e84  jz      short loc_180001E90
0x180001e86  mov     edx, 10h
0x180001e8b  jmp     loc_180001F84
0x180001e90  test    eax, eax
0x180001e92  jnz     loc_180001F7D
0x180001e98  movups  xmm0, xmmword ptr [rbx+2Ah]
0x180001e9c  movups  [rbp+6A0h+Buf2], xmm0
0x180001ea0  mov     r8d, 10h; Size
0x180001ea6  lea     rdx, [rbp+6A0h+Buf2]; Buf2
0x180001eaa  lea     rcx, WPD_CONTENT_TYPE_PLAYLIST; Buf1
0x180001eb1  call    memcmp_0
0x180001eb6  test    eax, eax
0x180001eb8  jz      loc_180001F7D
0x180001ebe  cmp     dword ptr [rbx+42h], 1
0x180001ec2  jbe     short loc_180001ED1
0x180001ec4  mov     eax, [rbx+3Eh]
0x180001ec7  lea     rcx, ds:4Ah[rax*2]
0x180001ecf  jmp     short loc_180001ED6
0x180001ed1  mov     ecx, 4Ah ; 'J'
0x180001ed6  mov     eax, 7FFFFFFEh
0x180001edb  lea     rdx, [rcx+rbx]
0x180001edf  mov     ebx, 104h
0x180001ee4  lea     r9, [rbp+6A0h+pszPath]
0x180001ee8  test    rax, rax
0x180001eeb  jz      short loc_180001F0A
0x180001eed  movzx   ecx, word ptr [rdx]
0x180001ef0  test    cx, cx
0x180001ef3  jz      short loc_180001F0A
0x180001ef5  add     rdx, 2
0x180001ef9  mov     [r9], cx
0x180001efd  add     r9, 2
0x180001f01  dec     rax
0x180001f04  sub     rbx, 1
0x180001f08  jnz     short loc_180001EE8
0x180001f0a  lea     rcx, [r9-2]
0x180001f0e  test    rbx, rbx
0x180001f11  cmovnz  rcx, r9
0x180001f15  xor     eax, eax
0x180001f17  mov     [rcx], ax
0x180001f1a  lea     rcx, [rbp+6A0h+pszPath]; pszPath
0x180001f1e  call    cs:__imp_PathFindFileNameW
0x180001f24  mov     r9, r12; ppv
0x180001f27  mov     r8, rdi; riid
0x180001f2a  xor     edx, edx; dwFileAttributes
0x180001f2c  mov     rcx, rax; pszFile
0x180001f2f  call    cs:__imp_SHCreateFileExtractIconW
0x180001f35  mov     esi, eax
0x180001f37  test    eax, eax
0x180001f39  jns     loc_180002A55
0x180001f3f  lea     rbx, WPP_GLOBAL_Control
0x180001f46  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f4d  cmp     rcx, rbx
0x180001f50  jz      loc_180002A55
0x180001f56  test    byte ptr [rcx+1Ch], 2
0x180001f5a  jz      loc_180002A32
0x180001f60  mov     edx, 2Ch ; ','
0x180001f65  mov     r9d, eax
0x180001f68  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180001f6f  mov     rcx, [rcx+10h]
0x180001f73  call    WPP_SF_d
0x180001f78  jmp     loc_180002A2B
0x180001f7d  xor     edx, edx
0x180001f7f  mov     r10, [rsp+7A0h+var_728]
0x180001f84  mov     eax, 0FFFFFFFCh
0x180001f89  mov     ecx, 0FFFFFFFFh
0x180001f8e  test    edx, edx
0x180001f90  cmovz   eax, ecx
0x180001f93  mov     dword ptr [rsp+7A0h+var_730], eax
0x180001f97  mov     rdx, [r15]; pidl2
0x180001f9a  mov     rcx, [r10+30h]; pidl1
0x180001f9e  call    cs:__imp_ILCombine
0x180001fa4  mov     r14, rax
0x180001fa7  test    rax, rax
0x180001faa  jz      loc_180002064
0x180001fb0  mov     r11, [rsp+7A0h+var_728]
0x180001fb5  mov     rax, [r11-10h]
0x180001fb9  mov     r10, [rax+70h]
0x180001fbd  movups  xmm0, xmmword ptr [rbx+2Ah]
0x180001fc1  mov     ecx, [rbx+42h]
0x180001fc4  mov     eax, [rbx+3Eh]
0x180001fc7  add     rax, 25h ; '%'
0x180001fcb  add     rcx, rax
0x180001fce  lea     r8, [rbx+rcx*2]; unsigned __int16 *
0x180001fd2  mov     edx, 104h; unsigned __int64
0x180001fd7  lea     rcx, [rbp+6A0h+var_470]; unsigned __int16 *
0x180001fde  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180001fe3  movaps  [rbp+6A0h+Buf2], xmm0
0x180001fe7  mov     [rsp+7A0h+var_760], r12
0x180001fec  mov     [rsp+7A0h+var_768], rdi
0x180001ff1  mov     dword ptr [rsp+7A0h+var_770], esi
0x180001ff5  mov     dword ptr [rsp+7A0h+var_778], r13d
0x180001ffa  mov     eax, dword ptr [rsp+7A0h+var_730]
0x180001ffe  mov     dword ptr [rsp+7A0h+var_780], eax
0x180002002  lea     r9, [rbp+6A0h+Buf2]
0x180002006  lea     r8, [rbp+6A0h+var_470]
0x18000200d  mov     rdx, r14
0x180002010  lea     rcx, [r11-10h]
0x180002014  mov     rax, r10
0x180002017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000201c  mov     esi, eax
0x18000201e  test    eax, eax
0x180002020  jns     loc_180002226
0x180002026  lea     rbx, WPP_GLOBAL_Control
0x18000202d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002034  cmp     rcx, rbx
0x180002037  jz      loc_180002234
0x18000203d  test    byte ptr [rcx+1Ch], 2
0x180002041  jz      loc_180002234
0x180002047  mov     edx, 2Bh ; '+'
0x18000204c  mov     r9d, eax
0x18000204f  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180002056  mov     rcx, [rcx+10h]
0x18000205a  call    WPP_SF_d
0x18000205f  jmp     loc_18000222D
0x180002064  lea     rbx, WPP_GLOBAL_Control
0x18000206b  mov     esi, 8007000Eh
0x180002070  mov     rcx, cs:WPP_GLOBAL_Control
0x180002077  cmp     rcx, rbx
0x18000207a  jz      loc_180002234
0x180002080  test    byte ptr [rcx+1Ch], 2
0x180002084  jz      short loc_1800020A5
0x180002086  mov     edx, 45h ; 'E'
0x18000208b  mov     r9d, esi
0x18000208e  lea     r8, WPP_d7637b305d8b3afba9326780f352c02a_Traceguids
0x180002095  mov     rcx, [rcx+10h]
0x180002099  call    WPP_SF_d
0x18000209e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800020a5  cmp     rcx, rbx
0x1800020a8  jz      loc_180002234
0x1800020ae  test    byte ptr [rcx+1Ch], 2
0x1800020b2  jz      loc_180002234
0x1800020b8  mov     edx, 2Ah ; '*'
0x1800020bd  mov     r9d, esi
0x1800020c0  jmp     short loc_18000204F
0x1800020c2  mov     rax, [rdi]
0x1800020c5  sub     rax, qword ptr cs:IID_IExtractImage.Data1
0x1800020cc  jnz     short loc_1800020D9
0x1800020ce  mov     rax, [rdi+8]
0x1800020d2  sub     rax, qword ptr cs:IID_IExtractImage.Data4
0x1800020d9  test    rax, rax
0x1800020dc  jnz     loc_18000227E
0x1800020e2  test    rbx, rbx
0x1800020e5  jz      loc_18000227E
0x1800020eb  mov     eax, [rbx+0Eh]
0x1800020ee  bt      eax, 11h
0x1800020f2  jnb     short loc_180002103
0x1800020f4  movups  xmm0, xmmword ptr cs:WPD_RESOURCE_THUMBNAIL.fmtid.Data1
0x1800020fb  mov     eax, cs:WPD_RESOURCE_THUMBNAIL.pid
0x180002101  jmp     short loc_180002144
0x180002103  bt      eax, 14h
0x180002107  jnb     short loc_180002118
0x180002109  movups  xmm0, xmmword ptr cs:WPD_RESOURCE_ALBUM_ART.fmtid.Data1
0x180002110  mov     eax, cs:WPD_RESOURCE_ALBUM_ART.pid
0x180002116  jmp     short loc_180002144
0x180002118  bt      eax, 10h
0x18000211c  jnb     short loc_18000212D
0x18000211e  movups  xmm0, xmmword ptr cs:WPD_RESOURCE_CONTACT_PHOTO.fmtid.Data1
0x180002125  mov     eax, cs:WPD_RESOURCE_CONTACT_PHOTO.pid
0x18000212b  jmp     short loc_180002144
0x18000212d  bt      eax, 0Ch
0x180002131  jnb     loc_18000224B
0x180002137  movups  xmm0, xmmword ptr cs:WPD_PROPERTY_NULL.fmtid.Data1
0x18000213e  mov     eax, cs:WPD_PROPERTY_NULL.pid
0x180002144  mov     [rbp+6A0h+var_6C0], eax
0x180002147  movups  [rbp+6A0h+Buf2], xmm0
0x18000214b  lea     r13, [r10-10h]
0x18000214f  lea     r8, [rsp+7A0h+pqa]
0x180002154  mov     rdx, [r15]
0x180002157  mov     rcx, [r13+40h]
0x18000215b  call    SHILCombine
0x180002160  mov     esi, eax
0x180002162  test    eax, eax
0x180002164  jns     short loc_1800021AB
0x180002166  lea     rbx, WPP_GLOBAL_Control
0x18000216d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002174  cmp     rcx, rbx
0x180002177  jz      short loc_1800021A1
0x180002179  test    byte ptr [rcx+1Ch], 2
0x18000217d  jz      short loc_1800021A1
0x18000217f  mov     edx, 2Eh ; '.'
0x180002184  mov     r9d, eax
0x180002187  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x18000218e  mov     rcx, [rcx+10h]
0x180002192  call    WPP_SF_d
0x180002197  mov     r14, [rsp+7A0h+pqa]
0x18000219c  jmp     loc_18000222D
0x1800021a1  mov     r14, [rsp+7A0h+pqa]
0x1800021a6  jmp     loc_180002234
0x1800021ab  mov     rax, [r13+0]
0x1800021af  mov     r10, [rax+78h]
0x1800021b3  mov     edx, [rbx+42h]
0x1800021b6  mov     eax, [rbx+3Eh]
0x1800021b9  add     rax, 25h ; '%'
0x1800021bd  add     rdx, rax
0x1800021c0  lea     r8, [rbx+rdx*2]; unsigned __int16 *
0x1800021c4  mov     edx, 104h; unsigned __int64
0x1800021c9  lea     rcx, [rbp+6A0h+var_470]; unsigned __int16 *
0x1800021d0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800021d5  mov     [rsp+7A0h+var_778], r12
0x1800021da  mov     [rsp+7A0h+var_780], rdi
0x1800021df  lea     r9, [rbp+6A0h+Buf2]
0x1800021e3  lea     r8, [rbp+6A0h+var_470]
0x1800021ea  mov     r14, [rsp+7A0h+pqa]
0x1800021ef  mov     rdx, r14
0x1800021f2  mov     rcx, r13
0x1800021f5  mov     rax, r10
0x1800021f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021fd  mov     esi, eax
0x1800021ff  test    eax, eax
0x180002201  jns     short loc_180002226
0x180002203  lea     rbx, WPP_GLOBAL_Control
0x18000220a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002211  cmp     rcx, rbx
0x180002214  jz      short loc_180002234
0x180002216  test    byte ptr [rcx+1Ch], 2
0x18000221a  jz      short loc_180002234
0x18000221c  mov     edx, 2Fh ; '/'
0x180002221  jmp     loc_18000204C
0x180002226  lea     rbx, WPP_GLOBAL_Control
0x18000222d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002234  test    r14, r14
0x180002237  jz      loc_18000280F
0x18000223d  mov     rcx, r14; pidl
0x180002240  call    cs:__imp_ILFree
0x180002246  jmp     loc_180002808
0x18000224b  mov     esi, 80004002h
0x180002250  lea     rbx, WPP_GLOBAL_Control
0x180002257  mov     rcx, cs:WPP_GLOBAL_Control
0x18000225e  cmp     rcx, rbx
0x180002261  jz      loc_180002A55
0x180002267  test    byte ptr [rcx+1Ch], 2
0x18000226b  jz      loc_180002A32
0x180002271  mov     edx, 2Dh ; '-'
0x180002276  mov     r9d, esi
0x180002279  jmp     loc_180001F68
0x18000227e  mov     rax, [rdi]
0x180002281  sub     rax, qword ptr cs:IID_IDataObject.Data1
0x180002288  jnz     short loc_180002295
0x18000228a  mov     rax, [rdi+8]
0x18000228e  sub     rax, qword ptr cs:IID_IDataObject.Data4
0x180002295  test    rax, rax
0x180002298  jnz     loc_1800024C1
  ... truncated ...
```
