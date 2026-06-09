# CRegFolder::GetUIObjectOf(HWND__ *,uint,_ITEMID_CHILD const * const *,_GUID const &,uint *,void * *)

- ea: `0x1800945c0`
- end: `0x18009512a`
- name: `?GetUIObjectOf@CRegFolder@@UEAAJPEAUHWND__@@IPEBQEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `2922`
- prototype: `int(CRegFolder *__hidden this, HWND, unsigned int, const struct _ITEMID_CHILD *const *, const struct _GUID *, unsigned int *, void **)`
- caller_count: `3`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800945c0`
- `0x1800951a0`
- `0x180095ee0`

## callees

- `0x1800304e0`
- `0x1800899e0`
- `0x180089b40`
- `0x180090ed0`
- `0x180092a70`
- `0x1800945c0`
- `0x180095130`
- `0x180095ee0`
- `0x1800961b0`
- `0x1800962ec`
- `0x1800b5630`
- `0x18016ac90`
- `0x1801c0cf0`
- `0x180261d48`
- `0x180275be0`
- `0x180276018`
- `0x18033bfc0`
- `0x1803b1f60`
- `0x1803b243c`
- `0x1803b2ac0`
- `0x1803b69b9`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x1800949d5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x1800949ff`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x1800949d5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x1800949ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094ab0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094c12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094ab0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094c12`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x180094847`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x18009487c`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x1800948c3`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x1800948f1`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x180094847`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x18009487c`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x1800948c3`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x1800948f1`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocQueryStringByKeyW` at `0x180094949`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocQueryStringByKeyW` at `0x180094949`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_SHCreateDefaultContextMenu` at `0x180094fb1`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_SHCreateDefaultContextMenu` at `0x180094fb1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRegFolder::GetUIObjectOf(
        CRegFolder *this,
        HKEY a2,
        UINT a3,
        LPCITEMIDLIST *a4,
        struct _GUID *a5,
        unsigned int *a6,
        void **a7)
{
  __int64 i; // rdi
  const struct _ITEMID_CHILD *v11; // rbx
  unsigned __int64 v12; // rsi
  char v13; // r14
  CRegFolder *v14; // rcx
  char *v15; // rcx
  const struct _ITEMID_CHILD *v16; // r14
  struct _GUID v17; // xmm0
  __int64 v18; // rsi
  const struct _ITEMID_CHILD *v19; // rdi
  unsigned __int64 v20; // r14
  char v21; // al
  CRegFolder *v22; // rcx
  int v23; // eax
  const struct _GUID *PIDLRCLSID; // rax
  IID *v25; // r14
  __int64 v26; // rax
  __int64 v27; // rax
  const struct _ITEMID_CHILD *v28; // rax
  struct _GUID *v29; // rax
  __int64 j; // rsi
  _QWORD *v31; // rdx
  __int64 v32; // rax
  struct _GUID *v33; // rax
  HRESULT DefExtIconKey; // edi
  char *v35; // rbx
  _QWORD *v36; // r14
  HKEY v37; // r14
  void *v38; // rdi
  void *v39; // r12
  unsigned int v40; // esi
  __int64 v41; // r15
  CExtractIcon *v42; // rax
  CExtractIcon *v43; // rbx
  CExtractIcon *v44; // rax
  CExtractIconBase *v45; // rbx
  int v46; // ebx
  void *v47; // rcx
  __int64 v50; // rax
  __int64 v51; // rax
  CRegFolder *v52; // rsi
  const struct _ITEMID_CHILD *v53; // rax
  char v54; // al
  const ITEMIDLIST *FolderIDList; // rax
  __int64 v56; // rcx
  __int64 (__fastcall ***v57)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v58)(_QWORD, GUID *, __int64); // rbx
  __int64 v59; // rax
  IID *v60; // rcx
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  int IsDesktop; // eax
  void *v65; // r15
  __int64 v66; // rcx
  __int64 v67; // rax
  char v68; // dl
  __int64 v69; // rcx
  IID *v70; // rsi
  int v71; // eax
  int UIObjectOf; // eax
  HRESULT (__stdcall *ParseDisplayName)(IShellFolder *, HWND, IBindCtx *, LPWSTR, ULONG *, LPITEMIDLIST *, ULONG *); // rdi
  void *v74; // rbx
  const struct _ITEMIDLIST_ABSOLUTE *v75; // rax
  void *ppv; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hkAssoc; // [rsp+50h] [rbp-B0h] BYREF
  struct IShellFolder *v78; // [rsp+58h] [rbp-A8h] BYREF
  void *v79; // [rsp+60h] [rbp-A0h] BYREF
  struct IShellFolder *v80; // [rsp+68h] [rbp-98h] BYREF
  IID *riid; // [rsp+70h] [rbp-90h] BYREF
  DWORD Src; // [rsp+78h] [rbp-88h] BYREF
  struct _GUID Buf1; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID Buf2; // [rsp+90h] [rbp-70h] BYREF
  WCHAR pszOut[4]; // [rsp+A0h] [rbp-60h] BYREF
  char *v86; // [rsp+A8h] [rbp-58h]
  const struct _ITEMIDLIST_ABSOLUTE *v87; // [rsp+B0h] [rbp-50h]
  IID *v88; // [rsp+B8h] [rbp-48h]
  UINT v89; // [rsp+C0h] [rbp-40h]
  int v90; // [rsp+C4h] [rbp-3Ch]
  LPCITEMIDLIST *v91; // [rsp+C8h] [rbp-38h]
  __int64 v92; // [rsp+D0h] [rbp-30h]
  __int64 v93; // [rsp+D8h] [rbp-28h]
  __int64 v94; // [rsp+E0h] [rbp-20h]

  hkAssoc = a2;
  riid = a5;
  v79 = a6;
  ppv = a7;
  *a7 = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= a3 )
      return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, HKEY, _QWORD, LPCITEMIDLIST *, IID *, void *, void *))(**((_QWORD **)this + 18) + 80LL))(
                             *((_QWORD *)this + 18),
                             hkAssoc,
                             a3,
                             a4,
                             riid,
                             v79,
                             ppv);
    v11 = (const struct _ITEMID_CHILD *)a4[i];
    if ( v11 )
    {
      v12 = *(unsigned __int16 *)v11;
      if ( (unsigned int)v12 >= 3 )
      {
        v13 = *((_BYTE *)v11 + 2);
        if ( v13 == *((_BYTE *)this + 288) )
        {
          v14 = (CRegFolder *)(*((unsigned __int16 *)this + 158) + 20LL);
          if ( v12 >= (unsigned __int64)v14 || CRegFolder::_IsDelegate(v14, (const struct IDLREGITEM *)a4[i]) )
            break;
        }
        if ( *((_DWORD *)this + 79) )
        {
          v54 = *((_BYTE *)this + 320);
          if ( v54 )
          {
            if ( v13 == v54 && (unsigned int)v12 >= 0x14 )
              break;
          }
        }
      }
    }
  }
  v15 = (char *)this - 40;
  v80 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
LABEL_8:
  Buf1 = v17;
  while ( (unsigned int)v18 < a3 )
  {
    v19 = (const struct _ITEMID_CHILD *)a4[v18];
    if ( !v19 )
      goto LABEL_23;
    v20 = *(unsigned __int16 *)v19;
    if ( (unsigned int)v20 < 3 )
      goto LABEL_23;
    v21 = *((_BYTE *)v19 + 2);
    if ( v21 == v15[328] )
    {
      v22 = (CRegFolder *)(*((unsigned __int16 *)v15 + 178) + 20LL);
      if ( v20 >= (unsigned __int64)v22 || CRegFolder::_IsDelegate(v22, (const struct IDLREGITEM *)a4[v18]) )
        goto LABEL_14;
      v21 = *((_BYTE *)v19 + 2);
      v15 = (char *)this - 40;
    }
    if ( !*((_DWORD *)v15 + 89) )
      goto LABEL_23;
    v68 = v15[360];
    if ( !v68 || v21 != v68 || (unsigned int)v20 < 0x14 )
      goto LABEL_23;
LABEL_14:
    v23 = IsDelegateRegId(v19);
    v15 = (char *)this - 40;
    if ( !v23 )
      goto LABEL_23;
    v16 = v19;
    PIDLRCLSID = CRegFolder::_GetPIDLRCLSID((CRegFolder *)v15, v19);
    v17 = *PIDLRCLSID;
    if ( !(_DWORD)v18 )
    {
      v18 = 1;
      v15 = (char *)this - 40;
      goto LABEL_8;
    }
    Buf2 = *PIDLRCLSID;
    v71 = memcmp_0(&Buf1, &Buf2, 0x10u);
    v15 = (char *)this - 40;
    if ( v71 )
      goto LABEL_23;
    v18 = (unsigned int)(v18 + 1);
    v16 = v19;
  }
  Buf2 = *(struct _GUID *)((char *)v16 + *((unsigned __int16 *)v16 + 2) + 22);
  if ( (int)CRegFolder::_CreateCachedDelegateFolder((CRegFolder *)v15, &Buf2, &v80, 0) >= 0 )
  {
    v69 = *((_QWORD *)this + 23);
    v70 = riid;
    if ( !v69
      || (DefExtIconKey = (*(__int64 (__fastcall **)(__int64, struct IShellFolder *, HKEY, _QWORD, LPCITEMIDLIST *, IID *, void *))(*(_QWORD *)v69 + 64LL))(
                            v69,
                            v80,
                            hkAssoc,
                            a3,
                            a4,
                            riid,
                            ppv),
          DefExtIconKey == -2147467263) )
    {
      DefExtIconKey = ((__int64 (__fastcall *)(struct IShellFolder *, HKEY, _QWORD, LPCITEMIDLIST *, IID *, void *, void *))v80->lpVtbl->GetUIObjectOf)(
                        v80,
                        hkAssoc,
                        a3,
                        a4,
                        v70,
                        v79,
                        ppv);
    }
    ((void (__fastcall *)(struct IShellFolder *))v80->lpVtbl->Release)(v80);
    return (unsigned int)DefExtIconKey;
  }
  v15 = (char *)this - 40;
LABEL_23:
  v25 = riid;
  v26 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IExtractIconA.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IExtractIconA.Data1 )
    v26 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IExtractIconA.Data4;
  if ( v26 )
  {
    v27 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IExtractIconW.Data1;
    if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IExtractIconW.Data1 )
      v27 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IExtractIconW.Data4;
    if ( v27 )
    {
      v50 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IDataObject.Data1;
      if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IDataObject.Data1 )
        v50 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IDataObject.Data4;
      if ( !v50 )
      {
        riid = 0;
        FolderIDList = (const ITEMIDLIST *)CRegFolder::_GetFolderIDList((CRegFolder *)v15);
        DefExtIconKey = SHCreateDataObject(
                          FolderIDList,
                          a3,
                          a4,
                          0,
                          &GUID_0000010e_0000_0000_c000_000000000046,
                          (void **)&riid);
        if ( DefExtIconKey >= 0 )
        {
          Src = 4;
          DefExtIconKey = DataObj_SetBlobWithIndex(
                            (struct IDataObject *)riid,
                            (unsigned __int16)word_1808264CC,
                            &Src,
                            4u,
                            -1);
          if ( DefExtIconKey >= 0 )
            DefExtIconKey = (**(__int64 (__fastcall ***)(IID *, IID *, void *))&riid->Data1)(riid, v25, ppv);
          (*(void (__fastcall **)(IID *))(*(_QWORD *)&riid->Data1 + 16LL))(riid);
        }
        return (unsigned int)DefExtIconKey;
      }
      v51 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
      if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
        v51 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
      if ( !v51 )
      {
        v56 = *((_QWORD *)this + 23);
        if ( !v56
          || (DefExtIconKey = (*(__int64 (__fastcall **)(__int64, _QWORD, HKEY, _QWORD, LPCITEMIDLIST *, IID *, void *))(*(_QWORD *)v56 + 64LL))(
                                v56,
                                0,
                                hkAssoc,
                                a3,
                                a4,
                                riid,
                                ppv),
              DefExtIconKey == -2147467263) )
        {
          riid = 0;
          v57 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*((_QWORD *)this + 18);
          v58 = **v57;
          v59 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>(&riid);
          DefExtIconKey = v58(v57, &GUID_000214e6_0000_0000_c000_000000000046, v59);
          if ( DefExtIconKey >= 0 )
          {
            *(_QWORD *)pszOut = hkAssoc;
            if ( this == (CRegFolder *)40 )
              v86 = 0;
            else
              v86 = (char *)this + 16;
            v87 = CRegFolder::_GetFolderIDList((CRegFolder *)((char *)this - 40));
            v88 = riid;
            v89 = a3;
            v90 = 0;
            v91 = a4;
            v92 = 0;
            v93 = 0;
            v94 = 0;
            DefExtIconKey = SHELL32_SHCreateDefaultContextMenu(pszOut, v25, ppv);
          }
          v60 = riid;
          if ( riid )
          {
            riid = 0;
            (*(void (__fastcall **)(IID *))(*(_QWORD *)&v60->Data1 + 16LL))(v60);
          }
        }
        return (unsigned int)DefExtIconKey;
      }
      v52 = (CRegFolder *)((char *)this - 40);
      if ( (unsigned int)IsDelegateRegId(v11) && *((_QWORD *)this + 23) )
      {
        v78 = 0;
        Buf2 = *(struct _GUID *)((char *)v11 + *((unsigned __int16 *)v11 + 2) + 22);
        DefExtIconKey = CRegFolder::_CreateCachedDelegateFolder((CRegFolder *)((char *)this - 40), &Buf2, &v78, 0);
        if ( DefExtIconKey >= 0 )
        {
          DefExtIconKey = (*(__int64 (__fastcall **)(_QWORD, struct IShellFolder *, HKEY, _QWORD, LPCITEMIDLIST *, IID *, void *))(**((_QWORD **)this + 23) + 64LL))(
                            *((_QWORD *)this + 23),
                            v78,
                            hkAssoc,
                            a3,
                            a4,
                            v25,
                            ppv);
          ((void (__fastcall *)(struct IShellFolder *))v78->lpVtbl->Release)(v78);
        }
        if ( DefExtIconKey != -2147467263 )
          return (unsigned int)DefExtIconKey;
      }
      v61 = *(_QWORD *)&v25->Data1 - *(_QWORD *)&IID_IQueryInfo.Data1;
      if ( *(_QWORD *)&v25->Data1 == *(_QWORD *)&IID_IQueryInfo.Data1 )
        v61 = *(_QWORD *)v25->Data4 - *(_QWORD *)IID_IQueryInfo.Data4;
      if ( v61 )
      {
        v62 = *(_QWORD *)&v25->Data1 - *(_QWORD *)&IID_IQueryAssociations.Data1;
        if ( *(_QWORD *)&v25->Data1 == *(_QWORD *)&IID_IQueryAssociations.Data1 )
          v62 = *(_QWORD *)v25->Data4 - *(_QWORD *)IID_IQueryAssociations.Data4;
        if ( v62 )
        {
          v63 = *(_QWORD *)&v25->Data1 - *(_QWORD *)&IID_IEnumAssocHandlers.Data1;
          if ( *(_QWORD *)&v25->Data1 == *(_QWORD *)&IID_IEnumAssocHandlers.Data1 )
            v63 = *(_QWORD *)v25->Data4 - *(_QWORD *)IID_IEnumAssocHandlers.Data4;
          if ( v63 )
          {
            if ( a3 == 1 )
            {
              IsDesktop = CRegFolder::_IsDesktop((CRegFolder *)((char *)this - 40));
              v65 = ppv;
              *(_QWORD *)ppv = 0;
              v78 = 0;
              DefExtIconKey = CRegFolder::_BindToItem(
                                v52,
                                v11,
                                0,
                                IsDesktop == 0,
                                &GUID_000214e6_0000_0000_c000_000000000046,
                                (void **)&v78);
              if ( DefExtIconKey >= 0 )
              {
                DefExtIconKey = ((__int64 (__fastcall *)(struct IShellFolder *, HKEY, IID *, void *))v78->lpVtbl->CreateViewObject)(
                                  v78,
                                  hkAssoc,
                                  v25,
                                  v65);
                ((void (__fastcall *)(struct IShellFolder *))v78->lpVtbl->Release)(v78);
              }
            }
            else
            {
              return (unsigned int)-2147467262;
            }
            return (unsigned int)DefExtIconKey;
          }
          return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, HKEY, _QWORD, LPCITEMIDLIST *, IID *, void *, void *))(**((_QWORD **)this + 18) + 80LL))(
                                 *((_QWORD *)this + 18),
                                 hkAssoc,
                                 a3,
                                 a4,
                                 v25,
                                 v79,
                                 ppv);
        }
        else
        {
          return (unsigned int)CRegFolder::_AssocCreate((CRegFolder *)((char *)this - 40), v11, v25, (void **)ppv);
        }
      }
      else
      {
        return (unsigned int)CRegFolder::_GetInfoTip((CRegFolder *)((char *)this - 40), v11, v25, (void **)ppv);
      }
    }
  }
  hkAssoc = 0;
  if ( (unsigned int)IsDelegateRegId(v11) )
  {
    v29 = (struct _GUID *)((char *)v11 + *((unsigned __int16 *)v11 + 2) + 22);
  }
  else
  {
    if ( *((_BYTE *)v11 + 2) == *((_BYTE *)this + 320) )
      v28 = v11;
    else
      v28 = (const struct _ITEMID_CHILD *)((char *)v11 + *((unsigned int *)this + 79));
    v29 = (struct _GUID *)((char *)v28 + 4);
  }
  Buf1 = *v29;
  for ( j = (unsigned int)(*((_DWORD *)this + 74) - 1); (int)j >= 0; j = (unsigned int)(j - 1) )
  {
    v31 = *(_QWORD **)(*((_QWORD *)this + 38) + 48 * j);
    v32 = *(_QWORD *)&Buf1.Data1 - *v31;
    if ( *(_QWORD *)&Buf1.Data1 == *v31 )
      v32 = *(_QWORD *)Buf1.Data4 - v31[1];
    if ( !v32 )
      break;
  }
  if ( (unsigned int)IsDelegateRegId(v11) )
  {
    v33 = (struct _GUID *)((char *)v11 + *((unsigned __int16 *)v11 + 2) + 22);
  }
  else
  {
    if ( *((_BYTE *)v11 + 2) == *((_BYTE *)this + 320) )
      v53 = v11;
    else
      v53 = (const struct _ITEMID_CHILD *)((char *)v11 + *((unsigned int *)this + 79));
    v33 = (struct _GUID *)((char *)v53 + 4);
  }
  Buf1 = *v33;
  if ( (int)SHRegGetCLSIDKey(&Buf1, 0, 1, 0, 131097, &hkAssoc) >= 0
    || (DefExtIconKey = SHRegGetCLSIDKey(&Buf1, 0, 1, 0, 131609, &hkAssoc), DefExtIconKey >= 0) )
  {
    v35 = (char *)this - 40;
    DefExtIconKey = CRegFolder::_CreateDefExtIconKey(
                      (CRegFolder *)((char *)this - 40),
                      hkAssoc,
                      a3,
                      (const struct _ITEMID_CHILD *const *)a4,
                      j,
                      v25,
                      (void **)ppv);
    v36 = ppv;
    if ( DefExtIconKey == 1 )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)ppv + 16LL))(*(_QWORD *)ppv);
      *(_QWORD *)ppv = 0;
    }
    RegCloseKey(hkAssoc);
  }
  else
  {
    v35 = (char *)this - 40;
    v36 = ppv;
  }
  if ( !*v36 )
  {
    if ( (int)SHRegGetCLSIDKey(&Buf1, 0, 0, 0, 131097, &hkAssoc) >= 0
      || (DefExtIconKey = SHRegGetCLSIDKey(&Buf1, 0, 0, 0, 131609, &hkAssoc), DefExtIconKey >= 0) )
    {
      v37 = hkAssoc;
      v38 = ppv;
      *(_QWORD *)ppv = 0;
      if ( !v37 || (Src = 39, AssocQueryStringByKeyW(0, ASSOCSTR_SHELLEXTENSION, v37, L"IconHandler", pszOut, &Src) < 0) )
      {
        v39 = v38;
        goto LABEL_49;
      }
      DefExtIconKey = SHExtCoCreateInstanceString((unsigned int)pszOut, 0, 2, (_DWORD)riid, (__int64)v38);
      if ( DefExtIconKey < 0 )
      {
        v39 = ppv;
        goto LABEL_49;
      }
      v78 = 0;
      if ( (***(int (__fastcall ****)(_QWORD, GUID *, struct IShellFolder **))ppv)(
             *(_QWORD *)ppv,
             &GUID_000214e8_0000_0000_c000_000000000046,
             &v78) >= 0 )
      {
        v79 = 0;
        UIObjectOf = CRegFolder::GetUIObjectOf(
                       this,
                       0,
                       a3,
                       (const struct _ITEMID_CHILD *const *)a4,
                       &GUID_0000010e_0000_0000_c000_000000000046,
                       0,
                       &v79);
        DefExtIconKey = UIObjectOf;
        if ( UIObjectOf >= 0 )
        {
          ParseDisplayName = v78->lpVtbl->ParseDisplayName;
          v74 = v79;
          v75 = CRegFolder::_GetFolderIDList((CRegFolder *)((char *)this - 40));
          DefExtIconKey = ((__int64 (__fastcall *)(struct IShellFolder *, const struct _ITEMIDLIST_ABSOLUTE *, void *, HKEY))ParseDisplayName)(
                            v78,
                            v75,
                            v74,
                            v37);
          (*(void (__fastcall **)(void *))(*(_QWORD *)v79 + 16LL))(v79);
          v35 = (char *)this - 40;
        }
        ((void (__fastcall *)(struct IShellFolder *))v78->lpVtbl->Release)(v78);
        if ( DefExtIconKey < 0 )
        {
          v39 = ppv;
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)ppv + 16LL))(*(_QWORD *)ppv);
LABEL_49:
          if ( (int)j >= 0 )
          {
            v66 = 6LL * (int)j;
            v67 = *((_QWORD *)v35 + 43);
            v40 = *(_DWORD *)(v67 + 48LL * (int)j + 24);
            v41 = *(_QWORD *)(v67 + 8 * v66 + 16);
          }
          else
          {
            v40 = 3;
            v41 = 0;
          }
          ppv = 0;
          v42 = (CExtractIcon *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
          v43 = v42;
          if ( v42 )
          {
            memset_0(v42, 0, 0x68u);
            v44 = CExtractIcon::CExtractIcon(v43);
            v45 = v44;
            DefExtIconKey = -2147024882;
            if ( v44 )
            {
              if ( QISearch(
                     v44,
                     &`CExtractIcon::QueryInterface'::`2'::qit,
                     &GUID_41ded17d_d6b3_4261_997d_88c60e4b1d58,
                     &ppv) >= 0 )
              {
                CExtractIconBase::Release(v45);
LABEL_55:
                DefExtIconKey = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 4);
                if ( DefExtIconKey >= 0 )
                {
                  v46 = (*(__int64 (__fastcall **)(void *, HKEY))(*(_QWORD *)ppv + 32LL))(ppv, v37);
                  if ( v46 < 0
                    || (DefExtIconKey = (*(__int64 (__fastcall **)(void *, __int64, _QWORD))(*(_QWORD *)ppv + 40LL))(
                                          ppv,
                                          v41,
                                          v40),
                        DefExtIconKey >= 0)
                    && (DefExtIconKey = (**(__int64 (__fastcall ***)(void *, IID *, void *))ppv)(ppv, riid, v39),
                        DefExtIconKey >= 0) )
                  {
                    DefExtIconKey = v46;
                  }
                }
              }
              else
              {
                DefExtIconKey = QISearch(
                                  v45,
                                  &`CExtractIconBase::QueryInterface'::`2'::qit,
                                  &GUID_41ded17d_d6b3_4261_997d_88c60e4b1d58,
                                  &ppv);
                CExtractIconBase::Release(v45);
                if ( DefExtIconKey >= 0 )
                  goto LABEL_55;
              }
            }
          }
          else
          {
            DefExtIconKey = -2147024882;
          }
          v47 = ppv;
          ppv = 0;
          if ( v47 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v47 + 16LL))(v47);
        }
      }
      RegCloseKey(hkAssoc);
    }
  }
  return (unsigned int)DefExtIconKey;
}

```

## disassembly

```asm
0x1800945c0  push    rbp
0x1800945c2  push    rbx
0x1800945c3  push    rsi
0x1800945c4  push    rdi
0x1800945c5  push    r12
0x1800945c7  push    r13
0x1800945c9  push    r14
0x1800945cb  push    r15
0x1800945cd  lea     rbp, [rsp-8]
0x1800945d2  sub     rsp, 108h
0x1800945d9  mov     rax, cs:__security_cookie
0x1800945e0  xor     rax, rsp
0x1800945e3  mov     [rbp+40h+var_50], rax
0x1800945e7  mov     r13, r9
0x1800945ea  mov     r12d, r8d
0x1800945ed  mov     [rsp+140h+hkAssoc], rdx
0x1800945f2  mov     r15, rcx
0x1800945f5  mov     rdx, [rbp+40h+arg_20]
0x1800945f9  mov     [rsp+140h+riid], rdx
0x1800945fe  mov     r8, [rbp+40h+arg_28]
0x180094602  mov     [rsp+140h+var_E0], r8
0x180094607  mov     rdx, [rbp+40h+arg_30]
0x18009460e  mov     [rsp+140h+ppv], rdx
0x180094613  mov     qword ptr [rdx], 0
0x18009461a  xor     edi, edi
0x18009461c  nop     dword ptr [rax+00h]
0x180094620  cmp     edi, r12d
0x180094623  jnb     loc_180094ABE
0x180094629  mov     rbx, [r13+rdi*8+0]
0x18009462e  test    rbx, rbx
0x180094631  jz      loc_180094716
0x180094637  movzx   esi, word ptr [rbx]
0x18009463a  cmp     esi, 3
0x18009463d  jb      loc_180094716
0x180094643  movzx   r14d, byte ptr [rbx+2]
0x180094648  cmp     r14b, [r15+120h]
0x18009464f  jnz     loc_180094708
0x180094655  movzx   ecx, word ptr [r15+13Ch]
0x18009465d  add     rcx, 14h; this
0x180094661  cmp     rsi, rcx
0x180094664  jb      loc_1800946F7
0x18009466a  lea     rcx, [r15-28h]; this
0x18009466e  mov     [rsp+140h+var_100], rcx
0x180094673  mov     [rsp+140h+var_D8], 0
0x18009467c  xor     r14d, r14d
0x18009467f  xorps   xmm0, xmm0
0x180094682  xor     esi, esi
0x180094684  movups  [rbp+40h+Buf1], xmm0
0x180094688  cmp     esi, r12d
0x18009468b  jnb     loc_180094E24
0x180094691  mov     rdi, [r13+rsi*8+0]
0x180094696  test    rdi, rdi
0x180094699  jz      loc_18009473F
0x18009469f  movzx   r14d, word ptr [rdi]
0x1800946a3  cmp     r14d, 3
0x1800946a7  jb      loc_18009473F
0x1800946ad  movzx   eax, byte ptr [rdi+2]
0x1800946b1  cmp     al, [rcx+148h]
0x1800946b7  jnz     short loc_180094732
0x1800946b9  movzx   ecx, word ptr [rcx+164h]
0x1800946c0  add     rcx, 14h; this
0x1800946c4  cmp     r14, rcx
0x1800946c7  jb      short loc_18009471D
0x1800946c9  mov     rcx, rdi
0x1800946cc  call    IsDelegateRegId
0x1800946d1  lea     rcx, [r15-28h]; this
0x1800946d5  test    eax, eax
0x1800946d7  jz      short loc_18009473F
0x1800946d9  mov     r14, rdi
0x1800946dc  mov     rdx, rdi; struct IDLREGITEM *
0x1800946df  call    ?_GetPIDLRCLSID@CRegFolder@@AEAAAEFBU_GUID@@PEFBUIDLREGITEM@@@Z; CRegFolder::_GetPIDLRCLSID(IDLREGITEM const *)
0x1800946e4  movups  xmm0, xmmword ptr [rax]
0x1800946e7  test    esi, esi
0x1800946e9  jnz     loc_1800950A6
0x1800946ef  inc     esi
0x1800946f1  lea     rcx, [r15-28h]
0x1800946f5  jmp     short loc_180094684
0x1800946f7  mov     rdx, rbx; struct IDLREGITEM *
0x1800946fa  call    ?_IsDelegate@CRegFolder@@AEAAPEFAUDELEGATEITEMID@@PEFBUIDLREGITEM@@@Z; CRegFolder::_IsDelegate(IDLREGITEM const *)
0x1800946ff  test    rax, rax
0x180094702  jnz     loc_18009466A
0x180094708  cmp     dword ptr [r15+13Ch], 0
0x180094710  jnz     loc_180094BAC
0x180094716  inc     edi
0x180094718  jmp     loc_180094620
0x18009471d  mov     rdx, rdi; struct IDLREGITEM *
0x180094720  call    ?_IsDelegate@CRegFolder@@AEAAPEFAUDELEGATEITEMID@@PEFBUIDLREGITEM@@@Z; CRegFolder::_IsDelegate(IDLREGITEM const *)
0x180094725  test    rax, rax
0x180094728  jnz     short loc_1800946C9
0x18009472a  movzx   eax, byte ptr [rdi+2]
0x18009472e  lea     rcx, [r15-28h]; this
0x180094732  cmp     dword ptr [rcx+164h], 0
0x180094739  jnz     loc_180094E70
0x18009473f  mov     r14, [rsp+140h+riid]
0x180094744  mov     rax, [r14]
0x180094747  sub     rax, qword ptr cs:IID_IExtractIconA.Data1
0x18009474e  jnz     short loc_18009475B
0x180094750  mov     rax, [r14+8]
0x180094754  sub     rax, qword ptr cs:IID_IExtractIconA.Data4
0x18009475b  test    rax, rax
0x18009475e  jz      short loc_180094780
0x180094760  mov     rax, [r14]
0x180094763  sub     rax, qword ptr cs:IID_IExtractIconW.Data1
0x18009476a  jnz     short loc_180094777
0x18009476c  mov     rax, [r14+8]
0x180094770  sub     rax, qword ptr cs:IID_IExtractIconW.Data4
0x180094777  test    rax, rax
0x18009477a  jnz     loc_180094B1F
0x180094780  mov     [rsp+140h+hkAssoc], 0
0x180094789  mov     rcx, rbx
0x18009478c  call    IsDelegateRegId
0x180094791  test    eax, eax
0x180094793  jnz     loc_180094B9C
0x180094799  movzx   eax, byte ptr [r15+140h]
0x1800947a1  cmp     [rbx+2], al
0x1800947a4  jz      loc_180095063
0x1800947aa  mov     eax, [r15+13Ch]
0x1800947b1  add     rax, rbx
0x1800947b4  add     rax, 4
0x1800947b8  movups  xmm0, xmmword ptr [rax]
0x1800947bb  movups  [rbp+40h+Buf1], xmm0
0x1800947bf  mov     esi, [r15+128h]
0x1800947c6  sub     esi, 1
0x1800947c9  js      short loc_180094804
0x1800947cb  mov     r9, [r15+130h]
0x1800947d2  mov     r8, qword ptr [rbp+40h+Buf1+8]
0x1800947d6  mov     r10, qword ptr [rbp+40h+Buf1]
0x1800947da  nop     word ptr [rax+rax+00h]
0x1800947e0  lea     rcx, [rsi+rsi*2]
0x1800947e4  add     rcx, rcx
0x1800947e7  mov     rdx, [r9+rcx*8]
0x1800947eb  mov     rax, r10
0x1800947ee  sub     rax, [rdx]
0x1800947f1  jnz     short loc_1800947FA
0x1800947f3  mov     rax, r8
0x1800947f6  sub     rax, [rdx+8]
0x1800947fa  test    rax, rax
0x1800947fd  jz      short loc_180094804
0x1800947ff  sub     esi, 1
0x180094802  jns     short loc_1800947E0
0x180094804  mov     rcx, rbx
0x180094807  call    IsDelegateRegId
0x18009480c  test    eax, eax
0x18009480e  jz      loc_180094B78
0x180094814  movzx   eax, word ptr [rbx+4]
0x180094818  add     rax, 16h
0x18009481c  add     rax, rbx
0x18009481f  movups  xmm0, xmmword ptr [rax]
0x180094822  movups  [rbp+40h+Buf1], xmm0
0x180094826  lea     rax, [rsp+140h+hkAssoc]
0x18009482b  mov     [rsp+140h+pcchOut], rax
0x180094830  mov     dword ptr [rsp+140h+pszOut], 20019h
0x180094838  xor     r9d, r9d
0x18009483b  xor     edx, edx
0x18009483d  mov     r8d, 1
0x180094843  lea     rcx, [rbp+40h+Buf1]
0x180094847  call    cs:__imp_SHRegGetCLSIDKey
0x18009484e  nop     dword ptr [rax+rax+00h]
0x180094853  test    eax, eax
0x180094855  jns     loc_180094BD3
0x18009485b  lea     rax, [rsp+140h+hkAssoc]
0x180094860  mov     [rsp+140h+pcchOut], rax
0x180094865  mov     dword ptr [rsp+140h+pszOut], 20219h
0x18009486d  xor     r9d, r9d
0x180094870  xor     edx, edx
0x180094872  mov     r8d, 1
0x180094878  lea     rcx, [rbp+40h+Buf1]
0x18009487c  call    cs:__imp_SHRegGetCLSIDKey
0x180094883  nop     dword ptr [rax+rax+00h]
0x180094888  mov     edi, eax
0x18009488a  test    eax, eax
0x18009488c  jns     loc_180094BD3
0x180094892  lea     rbx, [r15-28h]
0x180094896  mov     r14, [rsp+140h+ppv]
0x18009489b  cmp     qword ptr [r14], 0
0x18009489f  jnz     loc_180094AFC
0x1800948a5  lea     rax, [rsp+140h+hkAssoc]
0x1800948aa  mov     [rsp+140h+pcchOut], rax
0x1800948af  mov     dword ptr [rsp+140h+pszOut], 20019h
0x1800948b7  xor     r9d, r9d
0x1800948ba  xor     r8d, r8d
0x1800948bd  xor     edx, edx
0x1800948bf  lea     rcx, [rbp+40h+Buf1]
0x1800948c3  call    cs:__imp_SHRegGetCLSIDKey
0x1800948ca  nop     dword ptr [rax+rax+00h]
0x1800948cf  test    eax, eax
0x1800948d1  jns     short loc_180094907
0x1800948d3  lea     rax, [rsp+140h+hkAssoc]
0x1800948d8  mov     [rsp+140h+pcchOut], rax
0x1800948dd  mov     dword ptr [rsp+140h+pszOut], 20219h
0x1800948e5  xor     r9d, r9d
0x1800948e8  xor     r8d, r8d
0x1800948eb  xor     edx, edx
0x1800948ed  lea     rcx, [rbp+40h+Buf1]
0x1800948f1  call    cs:__imp_SHRegGetCLSIDKey
0x1800948f8  nop     dword ptr [rax+rax+00h]
0x1800948fd  mov     edi, eax
0x1800948ff  test    eax, eax
0x180094901  js      loc_180094AFC
0x180094907  mov     r14, [rsp+140h+hkAssoc]
0x18009490c  mov     rdi, [rsp+140h+ppv]
0x180094911  mov     qword ptr [rdi], 0
0x180094918  test    r14, r14
0x18009491b  jz      short loc_18009495D
0x18009491d  mov     [rsp+140h+Src], 27h ; '''
0x180094925  lea     rax, [rsp+140h+Src]
0x18009492a  mov     [rsp+140h+pcchOut], rax; pcchOut
0x18009492f  lea     rax, [rbp+40h+var_A0]
0x180094933  mov     [rsp+140h+pszOut], rax; pszOut
0x180094938  lea     r9, pszExtra; "IconHandler"
0x18009493f  mov     r8, r14; hkAssoc
0x180094942  mov     edx, 10h; str
0x180094947  xor     ecx, ecx; flags
0x180094949  call    cs:__imp_AssocQueryStringByKeyW
0x180094950  nop     dword ptr [rax+rax+00h]
0x180094955  test    eax, eax
0x180094957  jns     loc_180094FC4
0x18009495d  mov     r12, rdi
0x180094960  test    esi, esi
0x180094962  jns     loc_180094E51
0x180094968  mov     esi, 3
0x18009496d  xor     r15d, r15d
0x180094970  mov     [rsp+140h+ppv], 0
0x180094979  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180094980  mov     ecx, 68h ; 'h'; unsigned __int64
0x180094985  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18009498a  mov     rbx, rax
0x18009498d  test    rax, rax
0x180094990  jz      loc_180094F30
0x180094996  xor     edx, edx; Val
0x180094998  mov     r8d, 68h ; 'h'; Size
0x18009499e  mov     rcx, rax; void *
0x1800949a1  call    memset_0
0x1800949a6  mov     rcx, rbx; this
0x1800949a9  call    ??0CExtractIcon@@QEAA@XZ; CExtractIcon::CExtractIcon(void)
0x1800949ae  mov     rbx, rax
0x1800949b1  mov     edi, 8007000Eh
0x1800949b6  test    rax, rax
0x1800949b9  jz      loc_180094A8C
0x1800949bf  lea     r9, [rsp+140h+ppv]; ppv
0x1800949c4  lea     r8, _GUID_41ded17d_d6b3_4261_997d_88c60e4b1d58; riid
0x1800949cb  lea     rdx, ?qit@?1??QueryInterface@CExtractIcon@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; pqit
0x1800949d2  mov     rcx, rax; that
0x1800949d5  call    cs:__imp_QISearch
0x1800949dc  nop     dword ptr [rax+rax+00h]
0x1800949e1  mov     rcx, rbx; this
0x1800949e4  test    eax, eax
0x1800949e6  jns     loc_180094E1A
0x1800949ec  lea     r9, [rsp+140h+ppv]; ppv
0x1800949f1  lea     r8, _GUID_41ded17d_d6b3_4261_997d_88c60e4b1d58; riid
0x1800949f8  lea     rdx, ?qit@?1??QueryInterface@CExtractIconBase@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; pqit
0x1800949ff  call    cs:__imp_QISearch
0x180094a06  nop     dword ptr [rax+rax+00h]
0x180094a0b  mov     edi, eax
0x180094a0d  mov     rcx, rbx; this
0x180094a10  call    ?Release@CExtractIconBase@@UEAAKXZ; CExtractIconBase::Release(void)
0x180094a15  test    edi, edi
0x180094a17  js      short loc_180094A8C
0x180094a19  mov     rcx, [rsp+140h+ppv]
0x180094a1e  mov     rax, [rcx]
0x180094a21  mov     edx, 4
0x180094a26  mov     rax, [rax+18h]
0x180094a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094a2f  mov     edi, eax
0x180094a31  test    eax, eax
0x180094a33  js      short loc_180094A8C
0x180094a35  mov     rcx, [rsp+140h+ppv]
0x180094a3a  mov     rax, [rcx]
0x180094a3d  mov     rdx, r14
0x180094a40  mov     rax, [rax+20h]
0x180094a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094a49  mov     ebx, eax
0x180094a4b  test    eax, eax
0x180094a4d  js      short loc_180094A8A
0x180094a4f  mov     rcx, [rsp+140h+ppv]
0x180094a54  mov     r9, [rcx]
0x180094a57  mov     r8d, esi
0x180094a5a  mov     rdx, r15
0x180094a5d  mov     rax, [r9+28h]
0x180094a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094a66  mov     edi, eax
0x180094a68  test    eax, eax
0x180094a6a  js      short loc_180094A8C
0x180094a6c  mov     rcx, [rsp+140h+ppv]
0x180094a71  mov     rax, [rcx]
0x180094a74  mov     r8, r12
0x180094a77  mov     rdx, [rsp+140h+riid]
0x180094a7c  mov     rax, [rax]
0x180094a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094a84  mov     edi, eax
0x180094a86  test    eax, eax
0x180094a88  js      short loc_180094A8C
0x180094a8a  mov     edi, ebx
0x180094a8c  mov     rcx, [rsp+140h+ppv]
0x180094a91  mov     [rsp+140h+ppv], 0
0x180094a9a  test    rcx, rcx
0x180094a9d  jz      short loc_180094AAB
0x180094a9f  mov     rax, [rcx]
0x180094aa2  mov     rax, [rax+10h]
0x180094aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
