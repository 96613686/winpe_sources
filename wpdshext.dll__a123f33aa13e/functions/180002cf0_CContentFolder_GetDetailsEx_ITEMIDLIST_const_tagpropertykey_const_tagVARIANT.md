# CContentFolder::GetDetailsEx(_ITEMIDLIST const *,_tagpropertykey const *,tagVARIANT *)

- ea: `0x180002cf0`
- end: `0x180003dd4`
- name: `?GetDetailsEx@CContentFolder@@UEAAJPEFBU_ITEMIDLIST@@PEBU_tagpropertykey@@PEAUtagVARIANT@@@Z`
- size: `4324`
- prototype: `int(CContentFolder *__hidden this, const struct _ITEMIDLIST *, const struct _tagpropertykey *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002cf0`
- `0x180003f90`
- `0x180004110`
- `0x180004190`
- `0x1800050d0`
- `0x1800082e0`
- `0x180014b60`
- `0x18001ef50`
- `0x180022260`
- `0x180023584`
- `0x1800285c8`
- `0x18002a2c8`
- `0x18002ab58`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x18003912c`
- `0x180078010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18000320a`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18000320a`
- `KERNEL32!QueryPerformanceCounter` at `0x180002d73`
- `KERNEL32!QueryPerformanceCounter` at `0x180002d73`
- `ole32!PropVariantClear` at `0x180003cde`
- `ole32!PropVariantClear` at `0x180003d64`
- `ole32!PropVariantClear` at `0x180003cde`
- `ole32!PropVariantClear` at `0x180003d64`
- `OLEAUT32!__imp_SysAllocString` at `0x18000321d`
- `OLEAUT32!__imp_SysAllocString` at `0x18000321d`
- `OLEAUT32!__imp_VariantInit` at `0x180003237`
- `OLEAUT32!__imp_VariantInit` at `0x180003237`
- `PROPSYS!PropVariantToVariant` at `0x180003ca8`
- `PROPSYS!PropVariantToVariant` at `0x180003ca8`
- `PROPSYS!InitVariantFromFileTime` at `0x1800039d2`
- `PROPSYS!InitVariantFromFileTime` at `0x180003a45`
- `PROPSYS!InitVariantFromFileTime` at `0x1800039d2`
- `PROPSYS!InitVariantFromFileTime` at `0x180003a45`
- `SHELL32!AssocGetDetailsOfPropKey` at `0x180003011`
- `SHELL32!AssocGetDetailsOfPropKey` at `0x18000339c`
- `SHELL32!AssocGetDetailsOfPropKey` at `0x180003618`
- `SHELL32!AssocGetDetailsOfPropKey` at `0x180003acd`
- `SHELL32!AssocGetDetailsOfPropKey` at `0x180003ba3`
- `SHELL32!AssocGetDetailsOfPropKey` at `0x180003011`
- `SHELL32!AssocGetDetailsOfPropKey` at `0x18000339c`
- `SHELL32!AssocGetDetailsOfPropKey` at `0x180003618`
- `SHELL32!AssocGetDetailsOfPropKey` at `0x180003acd`
- `SHELL32!AssocGetDetailsOfPropKey` at `0x180003ba3`

## string_xrefs

- `0x180003140`: `prop:System.DateCreated;System.DateModified`
- `0x1800033e7`: `prop:System.DateCreated;System.DateModified`
- `0x180003bee`: `prop:System.DateCreated;System.DateModified`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CContentFolder::GetDetailsEx(
        IShellFolder *this,
        const struct _ITEMIDLIST *a2,
        const struct _tagpropertykey *a3,
        struct tagVARIANT *a4)
{
  IShellFolder *v7; // r13
  unsigned int ulVal; // ebx
  CContentFolder *v9; // rcx
  const struct CONTENTITEM *v10; // rsi
  unsigned int v11; // r9d
  DWORD pid; // eax
  __int64 v13; // rax
  int v14; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  int inited; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rax
  IShellFolder *v26; // rcx
  HRESULT DetailsOfPropKey; // eax
  __int64 v28; // rax
  __int64 v29; // rax
  const unsigned __int16 *v30; // rax
  int v31; // eax
  const unsigned __int16 *v32; // rcx
  int v33; // eax
  __int64 v34; // rax
  BSTR v35; // rax
  __int64 v36; // rax
  unsigned __int16 *v37; // rax
  int v38; // eax
  __int64 v39; // rax
  const unsigned __int16 *v40; // rax
  int v41; // eax
  __int64 v42; // rax
  IShellFolder *v43; // rcx
  HRESULT v44; // eax
  const unsigned __int16 *v45; // rcx
  int v46; // eax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  int v50; // eax
  __int64 v51; // rax
  LONG v52; // eax
  LONG v53; // ecx
  LONG v54; // edx
  __int64 v55; // rax
  int v56; // eax
  __int64 v57; // rax
  HRESULT v58; // eax
  int v59; // eax
  __int64 v60; // rax
  int ObjectID; // eax
  _QWORD *v62; // rcx
  __int64 v63; // rdx
  __int64 v64; // r9
  struct IPortableDeviceResources *v65; // rbx
  LONG v66; // edx
  __int64 v67; // rax
  __int64 v68; // rax
  HRESULT v69; // eax
  __int64 v70; // rax
  HRESULT v71; // eax
  __int64 v72; // rax
  HRESULT v73; // eax
  int v74; // eax
  __int64 v75; // rax
  IShellFolder *v76; // rcx
  HRESULT v77; // eax
  const unsigned __int16 *v78; // rcx
  int v79; // eax
  int v80; // eax
  HRESULT v81; // eax
  DWORD v82; // esi
  CGuidToString *v83; // rax
  BOOL *pfFoundPropKey; // [rsp+20h] [rbp-E0h]
  BOOL v86; // [rsp+50h] [rbp-B0h] BYREF
  LONG v87; // [rsp+54h] [rbp-ACh] BYREF
  struct IPortableDeviceResources *v88; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v89; // [rsp+60h] [rbp-A0h] BYREF
  struct IPortableDevice *v90; // [rsp+68h] [rbp-98h] BYREF
  struct _GUID Buf2; // [rsp+70h] [rbp-90h] BYREF
  __int64 v92; // [rsp+80h] [rbp-80h] BYREF
  PROPVARIANT pPropVar; // [rsp+88h] [rbp-78h] BYREF
  __int64 v94; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v95; // [rsp+A8h] [rbp-58h]
  LARGE_INTEGER PerformanceCount[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v97; // [rsp+C0h] [rbp-40h]
  __int64 v98; // [rsp+D0h] [rbp-30h]
  char v99; // [rsp+D8h] [rbp-28h]
  OLECHAR sz[64]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v101[64]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v102[264]; // [rsp+1E0h] [rbp+E0h] BYREF
  wchar_t FullPath[264]; // [rsp+3F0h] [rbp+2F0h] BYREF
  wchar_t psz[264]; // [rsp+600h] [rbp+500h] BYREF

  v7 = this;
  v94 = 0;
  v95 = 0;
  v99 = 0;
  *(_OWORD *)&PerformanceCount[0].LowPart = 0;
  v97 = 0;
  v98 = 0;
  v86 = 0;
  v92 = 0;
  memset(&pPropVar, 0, sizeof(pPropVar));
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
  {
    QueryPerformanceCounter(PerformanceCount);
    v94 = 14;
    v95 = 0;
    v97 = 0;
    v99 = 1;
  }
  if ( !a4 )
  {
    ulVal = -2147467261;
    goto LABEL_271;
  }
  if ( !a3 )
  {
    ulVal = -2147024809;
    goto LABEL_271;
  }
  v10 = CContentFolder::_IsValid((CContentFolder *)this, a2);
  if ( !v10 )
  {
    ulVal = -2147024809;
    goto LABEL_271;
  }
  pid = a3->pid;
  if ( !pid )
  {
    v13 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_FindData.fmtid.Data1;
    if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_FindData.fmtid.Data1 )
      v13 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_FindData.fmtid.Data4;
    if ( v13 )
      goto LABEL_13;
    goto LABEL_61;
  }
  if ( pid == 5 )
  {
    v18 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_ComputerName.fmtid.Data1;
    if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_ComputerName.fmtid.Data1 )
      v18 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_ComputerName.fmtid.Data4;
    if ( v18 )
    {
      v19 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_Keywords.fmtid.Data1;
      if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_Keywords.fmtid.Data1 )
        v19 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_Keywords.fmtid.Data4;
      if ( v19 )
      {
        v20 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&WPD_OBJECT_PERSISTENT_UNIQUE_ID.fmtid.Data1;
        if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&WPD_OBJECT_PERSISTENT_UNIQUE_ID.fmtid.Data1 )
          v20 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)WPD_OBJECT_PERSISTENT_UNIQUE_ID.fmtid.Data4;
        if ( !v20 )
        {
          StringCchCopyW(
            v102,
            0x104u,
            (const unsigned __int16 *)v10
          + *(unsigned int *)((char *)v10 + 62)
          + *(unsigned int *)((char *)v10 + 66)
          + 37);
          inited = InitVariantFromString(v102, a4);
          ulVal = inited;
          if ( inited < 0 )
          {
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v16 = 107;
              v17 = (unsigned int)inited;
              goto LABEL_65;
            }
          }
          goto LABEL_271;
        }
LABEL_13:
        v14 = ((__int64 (__fastcall *)(IShellFolder *, const struct CONTENTITEM *, __int64 *, __int64))v7[-2].lpVtbl->EnumObjects)(
                &v7[-2],
                v10,
                &v92,
                1);
        ulVal = v14;
        if ( v14 >= 0 )
        {
          v80 = (*(__int64 (__fastcall **)(__int64, const struct _tagpropertykey *, PROPVARIANT *))(*(_QWORD *)v92 + 40LL))(
                  v92,
                  a3,
                  &pPropVar);
          ulVal = v80;
          if ( v80 >= 0 )
          {
            if ( pPropVar.vt == 10 )
            {
              ulVal = pPropVar.ulVal;
            }
            else if ( pPropVar.vt )
            {
              v81 = PropVariantToVariant(&pPropVar, a4);
              ulVal = v81;
              if ( v81 >= 0 )
              {
                PropVariantClear(&pPropVar);
              }
              else
              {
                v15 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v16 = 120;
                  v17 = (unsigned int)v81;
                  goto LABEL_65;
                }
              }
            }
            else
            {
              ulVal = -2147023728;
            }
          }
          else
          {
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v16 = 119;
              v17 = (unsigned int)v80;
              goto LABEL_65;
            }
          }
        }
        else
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v16 = 118;
            v17 = (unsigned int)v14;
LABEL_65:
            WPP_SF_d(v15[2], v16, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v17);
            goto LABEL_271;
          }
        }
        goto LABEL_271;
      }
    }
LABEL_61:
    ulVal = -2147467259;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_271;
    v16 = 93;
LABEL_64:
    v17 = ulVal;
    goto LABEL_65;
  }
  if ( pid != 100 )
  {
    if ( pid == 9 )
    {
      v28 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_PropList_ExtendedTileInfo.fmtid.Data1;
      if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_ExtendedTileInfo.fmtid.Data1 )
        v28 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_PropList_ExtendedTileInfo.fmtid.Data4;
      if ( v28 )
      {
        v47 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_PerceivedType.fmtid.Data1;
        if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PerceivedType.fmtid.Data1 )
          v47 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_PerceivedType.fmtid.Data4;
        if ( !v47 )
        {
          a4->vt = 19;
          Buf2 = *(struct _GUID *)((char *)v10 + 42);
          a4->lVal = GetPerceivedType(&Buf2);
          ulVal = 0;
          goto LABEL_271;
        }
        goto LABEL_13;
      }
      goto LABEL_61;
    }
    if ( pid != 7 )
      goto LABEL_44;
    v29 = *(_QWORD *)&a3->fmtid.Data1 - PKEY_WPDNSE_Name;
    if ( *(_QWORD *)&a3->fmtid.Data1 == PKEY_WPDNSE_Name )
      v29 = *(_QWORD *)a3->fmtid.Data4 - 0x366AB7680FF1508BLL;
    if ( !v29 )
    {
LABEL_70:
      v30 = CContentFolder::_Name(v9, v10, v102, v11);
      v31 = InitVariantFromString(v30, a4);
      ulVal = v31;
      if ( v31 < 0 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v16 = 94;
          v17 = (unsigned int)v31;
          goto LABEL_65;
        }
      }
      goto LABEL_271;
    }
    v60 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&WPDNSE_OBJECT_OPTIMAL_READ_BLOCK_SIZE.fmtid.Data1;
    if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&WPDNSE_OBJECT_OPTIMAL_READ_BLOCK_SIZE.fmtid.Data1 )
      v60 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)WPDNSE_OBJECT_OPTIMAL_READ_BLOCK_SIZE.fmtid.Data4;
    if ( v60 )
      goto LABEL_13;
    v87 = 0;
    *(_QWORD *)&Buf2.Data1 = 0;
    v90 = 0;
    v89 = 0;
    v88 = 0;
    StringCchCopyW(
      psz,
      0x104u,
      (const unsigned __int16 *)v10 + *(unsigned int *)((char *)v10 + 62) + *(unsigned int *)((char *)v10 + 66) + 37);
    ObjectID = CBaseFolder::_GetObjectID((CBaseFolder *)&v7[-2], psz, FullPath, 0x104u);
    ulVal = ObjectID;
    if ( ObjectID < 0 )
    {
      v62 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_180;
      v63 = 100;
      goto LABEL_178;
    }
    ObjectID = ((__int64 (__fastcall *)(IShellFolder *, struct IShellFolderVtbl *, struct IPortableDevice **))v7[-2].lpVtbl[1].EnumObjects)(
                 &v7[-2],
                 v7[6].lpVtbl,
                 &v90);
    ulVal = ObjectID;
    if ( ObjectID < 0 )
    {
      v62 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_180;
      v63 = 101;
      goto LABEL_178;
    }
    ObjectID = GetPortableDeviceResources(v90, &v88);
    ulVal = ObjectID;
    if ( ObjectID < 0 )
    {
      v62 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_180;
      v63 = 102;
      goto LABEL_178;
    }
    v87 = 0;
    v65 = v88;
    if ( ((int (__fastcall *)(struct IPortableDeviceResources *, wchar_t *, const PROPERTYKEY *, __int64 *))v88->lpVtbl->GetResourceAttributes)(
           v88,
           FullPath,
           &WPD_RESOURCE_DEFAULT,
           &v89) >= 0 )
      (*(void (__fastcall **)(__int64, const PROPERTYKEY *, LONG *))(*(_QWORD *)v89 + 80LL))(
        v89,
        &WPD_RESOURCE_ATTRIBUTE_OPTIMAL_READ_BUFFER_SIZE,
        &v87);
    v66 = v87;
    if ( !v87 )
    {
      ObjectID = ((__int64 (__fastcall *)(struct IPortableDeviceResources *, wchar_t *, const PROPERTYKEY *, _QWORD, LONG *, struct _GUID *))v65->lpVtbl->GetStream)(
                   v65,
                   FullPath,
                   &WPD_RESOURCE_DEFAULT,
                   0,
                   &v87,
                   &Buf2);
      ulVal = ObjectID;
      if ( ObjectID < 0 )
      {
        v62 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_180;
        v63 = 103;
LABEL_178:
        v64 = (unsigned int)ObjectID;
LABEL_179:
        WPP_SF_d(v62[2], v63, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v64);
LABEL_180:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v88);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v89);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v90);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&Buf2);
        goto LABEL_271;
      }
      v66 = v87;
      if ( !v87 )
      {
        ulVal = -2147467259;
        v62 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_180;
        v63 = 104;
        v64 = 2147500037LL;
        goto LABEL_179;
      }
    }
    a4->vt = 19;
    a4->lVal = v66;
    ulVal = 0;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v88);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v89);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v90);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&Buf2);
    goto LABEL_271;
  }
  v22 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_OfflineAvailability.fmtid.Data1;
  if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_OfflineAvailability.fmtid.Data1 )
    v22 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_OfflineAvailability.fmtid.Data4;
  if ( !v22 )
    goto LABEL_61;
  v23 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_OfflineStatus.fmtid.Data1;
  if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_OfflineStatus.fmtid.Data1 )
    v23 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_OfflineStatus.fmtid.Data4;
  if ( !v23 )
    goto LABEL_61;
  v9 = (CContentFolder *)(*(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_FileName.fmtid.Data1);
  if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_FileName.fmtid.Data1 )
    v9 = (CContentFolder *)(*(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_FileName.fmtid.Data4);
  if ( !v9 )
    goto LABEL_70;
  v9 = (CContentFolder *)(*(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_ItemName.fmtid.Data1);
  if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_ItemName.fmtid.Data1 )
    v9 = (CContentFolder *)(*(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_ItemName.fmtid.Data4);
  if ( !v9 )
    goto LABEL_70;
LABEL_44:
  if ( pid == 11 )
  {
    v24 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_ItemType.fmtid.Data1;
    if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_ItemType.fmtid.Data1 )
      v24 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_ItemType.fmtid.Data4;
    if ( v24 )
    {
      v25 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_PropList_ConflictPrompt.fmtid.Data1;
      if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_ConflictPrompt.fmtid.Data1 )
        v25 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_PropList_ConflictPrompt.fmtid.Data4;
      if ( !v25 )
      {
        v26 = v7;
        if ( v7 == (IShellFolder *)16 )
          v26 = 0;
        DetailsOfPropKey = AssocGetDetailsOfPropKey(v26, a2, a3, a4, &v86);
        ulVal = DetailsOfPropKey;
        if ( DetailsOfPropKey >= 0 )
        {
          if ( !v86 )
          {
            v32 = (*((_BYTE *)v10 + 10) & 2) != 0
                ? L"prop:System.DateCreated;System.DateModified"
                : (const unsigned __int16 *)v7[19].lpVtbl;
            v33 = InitVariantFromString(v32, a4);
            ulVal = v33;
            if ( v33 < 0 )
            {
              v15 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v16 = 117;
                v17 = (unsigned int)v33;
                goto LABEL_65;
              }
            }
          }
        }
        else
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v16 = 116;
            v17 = (unsigned int)DetailsOfPropKey;
            goto LABEL_65;
          }
        }
        goto LABEL_271;
      }
      goto LABEL_13;
    }
  }
  else
  {
    if ( pid != 100 )
    {
      switch ( pid )
      {
        case 0xAu:
          v36 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_ItemNameDisplay.fmtid.Data1;
          if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_ItemNameDisplay.fmtid.Data1 )
            v36 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_ItemNameDisplay.fmtid.Data4;
          if ( !v36 )
          {
            v37 = CContentFolder::_DisplayName(v9, v10, v102);
            v38 = InitVariantFromString(v37, a4);
            ulVal = v38;
            if ( v38 < 0 )
            {
              v15 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v16 = 96;
                v17 = (unsigned int)v38;
                goto LABEL_65;
              }
            }
            goto LABEL_271;
          }
          break;
        case 4u:
          v39 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_ItemTypeText.fmtid.Data1;
          if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_ItemTypeText.fmtid.Data1 )
            v39 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_ItemTypeText.fmtid.Data4;
          if ( !v39 )
          {
            v40 = CContentFolder::_Type(v9, v10, v102, v11);
            v41 = InitVariantFromString(v40, a4);
            ulVal = v41;
            if ( v41 < 0 )
            {
              v15 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v16 = 97;
                v17 = (unsigned int)v41;
                goto LABEL_65;
              }
            }
            goto LABEL_271;
          }
          v42 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_PropList_InfoTip.fmtid.Data1;
          if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_InfoTip.fmtid.Data1 )
            v42 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_PropList_InfoTip.fmtid.Data4;
          if ( !v42 )
          {
            v43 = v7;
            if ( v7 == (IShellFolder *)16 )
              v43 = 0;
            v44 = AssocGetDetailsOfPropKey(v43, a2, a3, a4, &v86);
            ulVal = v44;
            if ( v44 >= 0 )
            {
              if ( !v86 )
              {
                v45 = (*((_BYTE *)v10 + 10) & 2) != 0
                    ? L"prop:System.DateCreated;System.DateModified"
                    : (const unsigned __int16 *)v7[19].lpVtbl;
                v46 = InitVariantFromString(v45, a4);
                ulVal = v46;
                if ( v46 < 0 )
                {
                  v15 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    v16 = 115;
                    v17 = (unsigned int)v46;
                    goto LABEL_65;
                  }
                }
              }
            }
            else
            {
              v15 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v16 = 114;
                v17 = (unsigned int)v44;
                goto LABEL_65;
              }
            }
            goto LABEL_271;
          }
          break;
        case 2u:
          v48 = *(_QWORD *)&a3->fmtid.Data1 - PKEY_WPDNSE_Attributes;
          if ( *(_QWORD *)&a3->fmtid.Data1 == PKEY_WPDNSE_Attributes )
            v48 = *(_QWORD *)a3->fmtid.Data4 - 0x366AB7680FF1508BLL;
          if ( !v48 )
          {
            a4->vt = 19;
            a4->lVal = *(_DWORD *)((char *)v10 + 10);
            ulVal = 0;
            goto LABEL_271;
          }
          v49 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_DRM_IsProtected.fmtid.Data1;
          if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_DRM_IsProtected.fmtid.Data1 )
            v49 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_DRM_IsProtected.fmtid.Data4;
          if ( !v49 )
          {
            ulVal = -2147467259;
            if ( (*((_BYTE *)v10 + 10) & 2) == 0 )
            {
              v50 = *(_DWORD *)((char *)v10 + 14);
              if ( (v50 & 8) != 0 )
              {
                a4->vt = 11;
                a4->iVal = -((v50 & 4) != 0);
                ulVal = 0;
              }
            }
            goto LABEL_271;
          }
          break;
        case 0xDu:
          v51 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_FileAttributes.fmtid.Data1;
          if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_FileAttributes.fmtid.Data1 )
            v51 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_FileAttributes.fmtid.Data4;
          if ( !v51 )
          {
            a4->vt = 19;
            v52 = 16;
            if ( (*((_BYTE *)v10 + 10) & 2) == 0 )
              v52 = 128;
            a4->lVal = v52;
            v53 = v52 | (*(_DWORD *)((char *)v10 + 10) >> 7) & 2;
            a4->lVal = v53;
            v54 = v53 | (*(_DWORD *)((char *)v10 + 10) >> 9) & 1;
            a4->lVal = v54;
            a4->lVal = v54 | (*(_DWORD *)((char *)v10 + 10) >> 8) & 4;
            ulVal = 0;
            goto LABEL_271;
          }
          break;
        case 3u:
          v55 = *(_QWORD *)&a3->fmtid.Data1 - PKEY_WPDNSE_IsSupported;
          if ( *(_QWORD *)&a3->fmtid.Data1 == PKEY_WPDNSE_IsSupported )
            v55 = *(_QWORD *)a3->fmtid.Data4 - 0x366AB7680FF1508BLL;
          if ( !v55 )
          {
            if ( (*((_BYTE *)v10 + 10) & 2) != 0 )
            {
              ulVal = -2147467259;
            }
            else
            {
              v56 = *(_DWORD *)((_BYTE *)v10 + 14) & 2;
              a4->vt = 11;
              a4->iVal = -(v56 != 0);
              ulVal = 0;
            }
            goto LABEL_271;
          }
          v57 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_PropList_TileInfo.fmtid.Data1;
          if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_TileInfo.fmtid.Data1 )
            v57 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_PropList_TileInfo.fmtid.Data4;
          if ( !v57 )
          {
            if ( v7 == (IShellFolder *)16 )
              v7 = 0;
            v58 = AssocGetDetailsOfPropKey(v7, a2, a3, a4, &v86);
            ulVal = v58;
            if ( v58 >= 0 )
            {
              if ( !v86 && (*((_BYTE *)v10 + 10) & 2) == 0 )
              {
                v59 = InitVariantFromString(L"prop:System.ItemTypeText;System.DateModified", a4);
                ulVal = v59;
                if ( v59 < 0 )
                {
                  v15 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    v16 = 113;
                    v17 = (unsigned int)v59;
                    goto LABEL_65;
                  }
                }
              }
            }
            else
            {
              v15 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v16 = 112;
                v17 = (unsigned int)v58;
                goto LABEL_65;
              }
            }
            goto LABEL_271;
          }
          break;
        default:
          ulVal = -2147467259;
          switch ( pid )
          {
            case 0xCu:
              v67 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_Size.fmtid.Data1;
              if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_Size.fmtid.Data1 )
                v67 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_Size.fmtid.Data4;
              if ( !v67 )
              {
                if ( (*((_BYTE *)v10 + 10) & 2) == 0 )
                {
                  a4->vt = 21;
                  a4->llVal = *(_QWORD *)((char *)v10 + 18);
                  ulVal = 0;
                }
                goto LABEL_271;
              }
              break;
            case 0xFu:
              v68 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_DateCreated.fmtid.Data1;
              if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_DateCreated.fmtid.Data1 )
                v68 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_DateCreated.fmtid.Data4;
              if ( !v68 )
              {
                if ( *(_QWORD *)((char *)v10 + 26) )
                {
                  v69 = InitVariantFromFileTime((const FILETIME *)((char *)v10 + 26), a4);
                  ulVal = v69;
                  if ( v69 < 0 )
                  {
                    v15 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    {
                      v16 = 105;
                      v17 = (unsigned int)v69;
                      goto LABEL_65;
                    }
                  }
                }
                goto LABEL_271;
              }
              break;
            case 0xEu:
              v70 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_DateModified.fmtid.Data1;
              if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_DateModified.fmtid.Data1 )
                v70 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_DateModified.fmtid.Data4;
              if ( !v70 )
              {
                if ( *(_QWORD *)((char *)v10 + 34) )
                {
                  v71 = InitVariantFromFileTime((const FILETIME *)((char *)v10 + 34), a4);
                  ulVal = v71;
                  if ( v71 < 0 )
                  {
                    v15 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    {
                      v16 = 106;
                      v17 = (unsigned int)v71;
                      goto LABEL_65;
                    }
                  }
                }
                goto LABEL_271;
              }
              break;
            case 6u:
              v72 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_PropList_PreviewTitle.fmtid.Data1;
              if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_PreviewTitle.fmtid.Data1 )
                v72 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_PropList_PreviewTitle.fmtid.Data4;
              if ( !v72 )
              {
                if ( v7 == (IShellFolder *)16 )
                  v7 = 0;
                v73 = AssocGetDetailsOfPropKey(v7, a2, a3, a4, &v86);
                ulVal = v73;
                if ( v73 >= 0 )
                {
                  if ( !v86 )
                  {
                    v74 = InitVariantFromString(L"prop:System.ItemNameDisplay;System.ItemTypeText", a4);
                    ulVal = v74;
                    if ( v74 < 0 )
                    {
                      v15 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                      {
                        v16 = 109;
                        v17 = (unsigned int)v74;
                        goto LABEL_65;
                      }
                    }
                  }
                }
                else
                {
                  v15 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    v16 = 108;
                    v17 = (unsigned int)v73;
                    goto LABEL_65;
                  }
                }
                goto LABEL_271;
              }
              break;
            case 8u:
              v75 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_PropList_PreviewDetails.fmtid.Data1;
              if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_PreviewDetails.fmtid.Data1 )
                v75 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_PropList_PreviewDetails.fmtid.Data4;
              if ( !v75 )
              {
                v76 = v7;
                if ( v7 == (IShellFolder *)16 )
                  v76 = 0;
                v77 = AssocGetDetailsOfPropKey(v76, a2, a3, a4, &v86);
                ulVal = v77;
                if ( v77 >= 0 )
                {
                  if ( !v86 )
                  {
                    v78 = (*((_BYTE *)v10 + 10) & 2) != 0
                        ? L"prop:System.DateCreated;System.DateModified"
                        : (const unsigned __int16 *)v7[19].lpVtbl;
                    v79 = InitVariantFromString(v78, a4);
                    ulVal = v79;
                    if ( v79 < 0 )
                    {
                      v15 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                      {
                        v16 = 111;
                        v17 = (unsigned int)v79;
                        goto LABEL_65;
                      }
                    }
                  }
                }
                else
                {
                  v15 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    v16 = 110;
                    v17 = (unsigned int)v77;
                    goto LABEL_65;
                  }
                }
                goto LABEL_271;
              }
              break;
          }
          break;
      }
      goto LABEL_13;
    }
    v34 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_FileExtension.fmtid.Data1;
    if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_FileExtension.fmtid.Data1 )
      v34 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_FileExtension.fmtid.Data4;
    if ( v34 )
      goto LABEL_13;
  }
  ulVal = -2147467259;
  if ( (*((_BYTE *)v10 + 10) & 2) != 0 )
    goto LABEL_271;
  CContentFolder::_Name(v9, v10, FullPath, v11);
  _wsplitpath_s(FullPath, 0, 0, 0, 0, 0, 0, psz, 0x104u);
  a4->vt = 8;
  v35 = SysAllocString(psz);
  a4->llVal = (LONGLONG)v35;
  if ( v35 )
  {
    ulVal = 0;
    goto LABEL_271;
  }
  VariantInit(a4);
  ulVal = -2147024882;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v16 = 95;
    goto LABEL_64;
  }
LABEL_271:
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
  {
    memset_0(v101, 0, 0x78u);
    if ( a3 )
    {
      v82 = a3->pid;
      v83 = CGuidToString::CGuidToString(sz, &a3->fmtid);
    }
    else
    {
      v82 = 0;
      v83 = 0;
    }
    LODWORD(pfFoundPropKey) = v82;
    StringCchPrintfW(v101, 0x3Cu, L"%ws.%d", v83, pfFoundPropKey);
    CPerfTraceHelper::ProcessPerformanceData((CPerfTraceHelper *)&v94, 0xEu, ulVal, v101);
  }
  PropVariantClear(&pPropVar);
  if ( (ulVal & 0x80000000) != 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, ulVal);
  }
  if ( v92 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
  return ulVal;
}

```

## disassembly

```asm
0x180002cf0  push    rbp
0x180002cf2  push    rbx
0x180002cf3  push    rsi
0x180002cf4  push    rdi
0x180002cf5  push    r12
0x180002cf7  push    r13
0x180002cf9  push    r14
0x180002cfb  push    r15
0x180002cfd  lea     rbp, [rsp-728h]
0x180002d05  sub     rsp, 828h
0x180002d0c  mov     rax, cs:__security_cookie
0x180002d13  xor     rax, rsp
0x180002d16  mov     [rbp+760h+var_50], rax
0x180002d1d  mov     r14, r9
0x180002d20  mov     rdi, r8
0x180002d23  mov     r15, rdx
0x180002d26  mov     r13, rcx
0x180002d29  xor     r12d, r12d
0x180002d2c  mov     [rbp+760h+var_7C0], r12
0x180002d30  mov     [rbp+760h+var_7B8], r12
0x180002d34  mov     [rbp+760h+var_788], r12b
0x180002d38  xorps   xmm0, xmm0
0x180002d3b  movdqa  xmmword ptr [rbp+760h+PerformanceCount], xmm0
0x180002d40  xorps   xmm1, xmm1
0x180002d43  movdqa  [rbp+760h+var_7A0], xmm1
0x180002d48  mov     [rbp+760h+var_790], r12
0x180002d4c  mov     [rsp+860h+var_810], r12d
0x180002d51  mov     [rbp+760h+var_7E0], r12
0x180002d55  xor     eax, eax
0x180002d57  movups  xmmword ptr [rbp+760h+pPropVar], xmm0
0x180002d5b  mov     qword ptr [rbp+760h+pPropVar+10h], rax
0x180002d5f  mov     rax, cs:WPP_GLOBAL_Control
0x180002d66  test    dword ptr [rax+1Ch], 800h
0x180002d6d  jz      short loc_180002D91
0x180002d6f  lea     rcx, [rbp+760h+PerformanceCount]; lpPerformanceCount
0x180002d73  call    cs:__imp_QueryPerformanceCounter
0x180002d79  mov     [rbp+760h+var_7C0], 0Eh
0x180002d81  mov     [rbp+760h+var_7B8], r12
0x180002d85  xorps   xmm0, xmm0
0x180002d88  movdqa  [rbp+760h+var_7A0], xmm0
0x180002d8d  mov     [rbp+760h+var_788], 1
0x180002d91  lea     rsi, WPP_GLOBAL_Control
0x180002d98  test    r14, r14
0x180002d9b  jnz     short loc_180002DA7
0x180002d9d  mov     ebx, 80004003h
0x180002da2  jmp     loc_180003CEB
0x180002da7  test    rdi, rdi
0x180002daa  jnz     short loc_180002DB6
0x180002dac  mov     ebx, 80070057h
0x180002db1  jmp     loc_180003CEB
0x180002db6  mov     rdx, r15; struct _ITEMIDLIST *
0x180002db9  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x180002dbe  mov     rsi, rax
0x180002dc1  test    rax, rax
0x180002dc4  jnz     short loc_180002DD0
0x180002dc6  mov     ebx, 80070057h
0x180002dcb  jmp     loc_180003CE4
0x180002dd0  mov     eax, [rdi+10h]
0x180002dd3  test    eax, eax
0x180002dd5  jnz     short loc_180002E4C
0x180002dd7  mov     rax, [rdi]
0x180002dda  sub     rax, qword ptr cs:PKEY_FindData.fmtid.Data1
0x180002de1  jnz     short loc_180002DEE
0x180002de3  mov     rax, [rdi+8]
0x180002de7  sub     rax, qword ptr cs:PKEY_FindData.fmtid.Data4
0x180002dee  test    rax, rax
0x180002df1  jz      loc_180003071
0x180002df7  lea     rcx, [r13-10h]
0x180002dfb  mov     rax, [rcx]
0x180002dfe  mov     r9d, 1
0x180002e04  lea     r8, [rbp+760h+var_7E0]
0x180002e08  mov     rdx, rsi
0x180002e0b  mov     rax, [rax+20h]
0x180002e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e14  mov     ebx, eax
0x180002e16  test    eax, eax
0x180002e18  jns     loc_180003C3E
0x180002e1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e25  lea     rsi, WPP_GLOBAL_Control
0x180002e2c  cmp     rcx, rsi
0x180002e2f  jz      loc_180003CEB
0x180002e35  test    byte ptr [rcx+1Ch], 2
0x180002e39  jz      loc_180003CEB
0x180002e3f  mov     edx, 76h ; 'v'
0x180002e44  mov     r9d, eax
0x180002e47  jmp     loc_18000309F
0x180002e4c  cmp     eax, 5
0x180002e4f  jnz     loc_180002F1E
0x180002e55  mov     rax, [rdi]
0x180002e58  sub     rax, qword ptr cs:PKEY_ComputerName.fmtid.Data1
0x180002e5f  jnz     short loc_180002E6C
0x180002e61  mov     rax, [rdi+8]
0x180002e65  sub     rax, qword ptr cs:PKEY_ComputerName.fmtid.Data4
0x180002e6c  test    rax, rax
0x180002e6f  jz      loc_180003071
0x180002e75  mov     rax, [rdi]
0x180002e78  sub     rax, qword ptr cs:PKEY_Keywords.fmtid.Data1
0x180002e7f  jnz     short loc_180002E8C
0x180002e81  mov     rax, [rdi+8]
0x180002e85  sub     rax, qword ptr cs:PKEY_Keywords.fmtid.Data4
0x180002e8c  test    rax, rax
0x180002e8f  jz      loc_180003071
0x180002e95  mov     rax, [rdi]
0x180002e98  sub     rax, qword ptr cs:WPD_OBJECT_PERSISTENT_UNIQUE_ID.fmtid.Data1
0x180002e9f  jnz     short loc_180002EAC
0x180002ea1  mov     rax, [rdi+8]
0x180002ea5  sub     rax, qword ptr cs:WPD_OBJECT_PERSISTENT_UNIQUE_ID.fmtid.Data4
0x180002eac  test    rax, rax
0x180002eaf  jnz     loc_180002DF7
0x180002eb5  mov     ecx, [rsi+42h]
0x180002eb8  mov     eax, [rsi+3Eh]
0x180002ebb  add     rax, 25h ; '%'
0x180002ebf  add     rcx, rax
0x180002ec2  lea     r8, [rsi+rcx*2]; unsigned __int16 *
0x180002ec6  mov     edx, 104h; unsigned __int64
0x180002ecb  lea     rcx, [rbp+760h+var_680]; unsigned __int16 *
0x180002ed2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180002ed7  mov     rdx, r14; struct tagVARIANT *
0x180002eda  lea     rcx, [rbp+760h+var_680]; unsigned __int16 *
0x180002ee1  call    ?InitVariantFromString@@YAJPEBGPEAUtagVARIANT@@@Z; InitVariantFromString(ushort const *,tagVARIANT *)
0x180002ee6  mov     ebx, eax
0x180002ee8  test    eax, eax
0x180002eea  jns     loc_180003CE4
0x180002ef0  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ef7  lea     rsi, WPP_GLOBAL_Control
0x180002efe  cmp     rcx, rsi
0x180002f01  jz      loc_180003CEB
0x180002f07  test    byte ptr [rcx+1Ch], 2
0x180002f0b  jz      loc_180003CEB
0x180002f11  mov     edx, 6Bh ; 'k'
0x180002f16  mov     r9d, eax
0x180002f19  jmp     loc_18000309F
0x180002f1e  cmp     eax, 64h ; 'd'
0x180002f21  jnz     loc_18000304C
0x180002f27  mov     rcx, [rdi]
0x180002f2a  sub     rcx, qword ptr cs:PKEY_OfflineAvailability.fmtid.Data1
0x180002f31  jnz     short loc_180002F3E
0x180002f33  mov     rcx, [rdi+8]
0x180002f37  sub     rcx, qword ptr cs:PKEY_OfflineAvailability.fmtid.Data4
0x180002f3e  test    rcx, rcx
0x180002f41  jz      loc_180003071
0x180002f47  mov     rcx, [rdi]
0x180002f4a  sub     rcx, qword ptr cs:PKEY_OfflineStatus.fmtid.Data1
0x180002f51  jnz     short loc_180002F5E
0x180002f53  mov     rcx, [rdi+8]
0x180002f57  sub     rcx, qword ptr cs:PKEY_OfflineStatus.fmtid.Data4
0x180002f5e  test    rcx, rcx
0x180002f61  jz      loc_180003071
0x180002f67  mov     rcx, [rdi]
0x180002f6a  sub     rcx, qword ptr cs:PKEY_FileName.fmtid.Data1
0x180002f71  jnz     short loc_180002F7E
0x180002f73  mov     rcx, [rdi+8]
0x180002f77  sub     rcx, qword ptr cs:PKEY_FileName.fmtid.Data4
0x180002f7e  test    rcx, rcx
0x180002f81  jz      loc_1800030DD
0x180002f87  mov     rcx, [rdi]
0x180002f8a  sub     rcx, qword ptr cs:PKEY_ItemName.fmtid.Data1
0x180002f91  jnz     short loc_180002F9E
0x180002f93  mov     rcx, [rdi+8]
0x180002f97  sub     rcx, qword ptr cs:PKEY_ItemName.fmtid.Data4; this
0x180002f9e  test    rcx, rcx
0x180002fa1  jz      loc_1800030DD
0x180002fa7  cmp     eax, 0Bh
0x180002faa  jnz     loc_180003190
0x180002fb0  mov     rax, [rdi]
0x180002fb3  sub     rax, qword ptr cs:PKEY_ItemType.fmtid.Data1
0x180002fba  jnz     short loc_180002FC7
0x180002fbc  mov     rax, [rdi+8]
0x180002fc0  sub     rax, qword ptr cs:PKEY_ItemType.fmtid.Data4
0x180002fc7  test    rax, rax
0x180002fca  jz      loc_1800031B9
0x180002fd0  mov     rax, [rdi]
0x180002fd3  sub     rax, qword ptr cs:PKEY_PropList_ConflictPrompt.fmtid.Data1
0x180002fda  jnz     short loc_180002FE7
0x180002fdc  mov     rax, [rdi+8]
0x180002fe0  sub     rax, qword ptr cs:PKEY_PropList_ConflictPrompt.fmtid.Data4
0x180002fe7  test    rax, rax
0x180002fea  jnz     loc_180002DF7
0x180002ff0  lea     rdx, [r13-10h]
0x180002ff4  mov     rcx, r13
0x180002ff7  test    rdx, rdx
0x180002ffa  cmovz   rcx, r12; psf
0x180002ffe  lea     rax, [rsp+860h+var_810]
0x180003003  mov     [rsp+860h+pfFoundPropKey], rax; pfFoundPropKey
0x180003008  mov     r9, r14; pv
0x18000300b  mov     r8, rdi; pkey
0x18000300e  mov     rdx, r15; pidl
0x180003011  call    cs:__imp_AssocGetDetailsOfPropKey
0x180003017  mov     ebx, eax
0x180003019  test    eax, eax
0x18000301b  jns     loc_18000312F
0x180003021  mov     rcx, cs:WPP_GLOBAL_Control
0x180003028  lea     rsi, WPP_GLOBAL_Control
0x18000302f  cmp     rcx, rsi
0x180003032  jz      loc_180003CEB
0x180003038  test    byte ptr [rcx+1Ch], 2
0x18000303c  jz      loc_180003CEB
0x180003042  mov     edx, 74h ; 't'
0x180003047  mov     r9d, eax
0x18000304a  jmp     short loc_18000309F
0x18000304c  cmp     eax, 9
0x18000304f  jnz     short loc_1800030B4
0x180003051  mov     rax, [rdi]
0x180003054  sub     rax, qword ptr cs:PKEY_PropList_ExtendedTileInfo.fmtid.Data1
0x18000305b  jnz     short loc_180003068
0x18000305d  mov     rax, [rdi+8]
0x180003061  sub     rax, qword ptr cs:PKEY_PropList_ExtendedTileInfo.fmtid.Data4
0x180003068  test    rax, rax
0x18000306b  jnz     loc_18000343C
0x180003071  mov     ebx, 80004005h
0x180003076  mov     rcx, cs:WPP_GLOBAL_Control
0x18000307d  lea     rsi, WPP_GLOBAL_Control
0x180003084  cmp     rcx, rsi
0x180003087  jz      loc_180003CEB
0x18000308d  test    byte ptr [rcx+1Ch], 2
0x180003091  jz      loc_180003CEB
0x180003097  mov     edx, 5Dh ; ']'
0x18000309c  mov     r9d, ebx
0x18000309f  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x1800030a6  mov     rcx, [rcx+10h]
0x1800030aa  call    WPP_SF_d
0x1800030af  jmp     loc_180003CEB
0x1800030b4  cmp     eax, 7
0x1800030b7  jnz     loc_180002FA7
0x1800030bd  mov     rax, [rdi]
0x1800030c0  sub     rax, cs:PKEY_WPDNSE_Name
0x1800030c7  jnz     short loc_1800030D4
0x1800030c9  mov     rax, [rdi+8]
0x1800030cd  sub     rax, cs:qword_18007E5F8
0x1800030d4  test    rax, rax
0x1800030d7  jnz     loc_1800036B7
0x1800030dd  lea     r8, [rbp+760h+var_680]; unsigned __int16 *
0x1800030e4  mov     rdx, rsi; struct CONTENTITEM *
0x1800030e7  call    ?_Name@CContentFolder@@QEAAPEBGPEFBUCONTENTITEM@@PEAGI@Z; CContentFolder::_Name(CONTENTITEM const *,ushort *,uint)
0x1800030ec  mov     rcx, rax; unsigned __int16 *
0x1800030ef  mov     rdx, r14; struct tagVARIANT *
0x1800030f2  call    ?InitVariantFromString@@YAJPEBGPEAUtagVARIANT@@@Z; InitVariantFromString(ushort const *,tagVARIANT *)
0x1800030f7  mov     ebx, eax
0x1800030f9  test    eax, eax
0x1800030fb  jns     loc_180003CE4
0x180003101  mov     rcx, cs:WPP_GLOBAL_Control
0x180003108  lea     rsi, WPP_GLOBAL_Control
0x18000310f  cmp     rcx, rsi
0x180003112  jz      loc_180003CEB
0x180003118  test    byte ptr [rcx+1Ch], 2
0x18000311c  jz      loc_180003CEB
0x180003122  mov     edx, 5Eh ; '^'
0x180003127  mov     r9d, eax
0x18000312a  jmp     loc_18000309F
0x18000312f  cmp     [rsp+860h+var_810], 0
0x180003134  jnz     loc_180003CE4
0x18000313a  test    byte ptr [rsi+0Ah], 2
0x18000313e  jz      short loc_180003149
0x180003140  lea     rcx, aPropSystemDate; "prop:System.DateCreated;System.DateModi"...
0x180003147  jmp     short loc_180003150
0x180003149  mov     rcx, [r13+98h]; unsigned __int16 *
0x180003150  mov     rdx, r14; struct tagVARIANT *
0x180003153  call    ?InitVariantFromString@@YAJPEBGPEAUtagVARIANT@@@Z; InitVariantFromString(ushort const *,tagVARIANT *)
0x180003158  mov     ebx, eax
0x18000315a  test    eax, eax
0x18000315c  jns     loc_180003CE4
0x180003162  mov     rcx, cs:WPP_GLOBAL_Control
0x180003169  lea     rsi, WPP_GLOBAL_Control
0x180003170  cmp     rcx, rsi
0x180003173  jz      loc_180003CEB
0x180003179  test    byte ptr [rcx+1Ch], 2
0x18000317d  jz      loc_180003CEB
0x180003183  mov     edx, 75h ; 'u'
0x180003188  mov     r9d, eax
0x18000318b  jmp     loc_18000309F
0x180003190  cmp     eax, 64h ; 'd'
0x180003193  jnz     loc_18000326D
0x180003199  mov     rax, [rdi]
0x18000319c  sub     rax, qword ptr cs:PKEY_FileExtension.fmtid.Data1
0x1800031a3  jnz     short loc_1800031B0
0x1800031a5  mov     rax, [rdi+8]
0x1800031a9  sub     rax, qword ptr cs:PKEY_FileExtension.fmtid.Data4
0x1800031b0  test    rax, rax
0x1800031b3  jnz     loc_180002DF7
0x1800031b9  mov     ebx, 80004005h
0x1800031be  test    byte ptr [rsi+0Ah], 2
0x1800031c2  jnz     loc_180003CE4
0x1800031c8  lea     r8, [rbp+760h+FullPath]; unsigned __int16 *
0x1800031cf  mov     rdx, rsi; struct CONTENTITEM *
0x1800031d2  call    ?_Name@CContentFolder@@QEAAPEBGPEFBUCONTENTITEM@@PEAGI@Z; CContentFolder::_Name(CONTENTITEM const *,ushort *,uint)
0x1800031d7  mov     [rsp+860h+ExtCount], 104h; ExtCount
0x1800031e0  lea     rax, [rbp+760h+psz]
0x1800031e7  mov     [rsp+860h+Ext], rax; Ext
0x1800031ec  mov     [rsp+860h+FilenameCount], r12; FilenameCount
0x1800031f1  mov     [rsp+860h+Filename], r12; Filename
0x1800031f6  mov     [rsp+860h+pfFoundPropKey], r12; DirCount
0x1800031fb  xor     r9d, r9d; Dir
0x1800031fe  xor     r8d, r8d; DriveCount
0x180003201  xor     edx, edx; Drive
0x180003203  lea     rcx, [rbp+760h+FullPath]; FullPath
0x18000320a  call    cs:__imp__wsplitpath_s
0x180003210  mov     word ptr [r14], 8
0x180003216  lea     rcx, [rbp+760h+psz]; psz
0x18000321d  call    cs:__imp_SysAllocString
0x180003223  mov     [r14+8], rax
  ... truncated ...
```
