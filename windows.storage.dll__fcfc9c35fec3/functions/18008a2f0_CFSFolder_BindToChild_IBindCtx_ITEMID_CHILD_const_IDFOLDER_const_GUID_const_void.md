# CFSFolder::_BindToChild(IBindCtx *,_ITEMID_CHILD const *,IDFOLDER const *,_GUID const &,void * *)

- ea: `0x18008a2f0`
- end: `0x18008b6b9`
- name: `?_BindToChild@CFSFolder@@IEAAJPEAUIBindCtx@@PEFBU_ITEMID_CHILD@@PEFBUIDFOLDER@@AEBU_GUID@@PEAPEAX@Z`
- size: `5065`
- prototype: `__int64 __usercall@<rax>(CFSFolder *__hidden this@<rcx>, struct IBindCtx *@<rdx>, const struct _ITEMID_CHILD *@<r8>, const struct IDFOLDER *@<r9>, IID *riid, void **)`
- caller_count: `1`
- callee_count: `43`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180180ba0`

## callees

- `0x180009fc0`
- `0x180038f80`
- `0x18003df10`
- `0x18003e730`
- `0x18004036c`
- `0x180040430`
- `0x180040cd0`
- `0x180040f00`
- `0x180042ea0`
- `0x180045330`
- `0x180045520`
- `0x18005bd80`
- `0x180063050`
- `0x180065a00`
- `0x18006c460`
- `0x1800899a4`
- `0x18008a2f0`
- `0x18008c740`
- `0x1800974c0`
- `0x1800ad260`
- `0x1800aeb90`
- `0x1800d2c30`
- `0x180116a78`
- `0x180116dbc`
- `0x180116e60`
- `0x180140f00`
- `0x180140fb0`
- `0x180186170`
- `0x1801c7b40`
- `0x1801e8640`
- `0x1801e8b80`
- `0x180277ec8`
- `0x18027f768`
- `0x1802e30bc`
- `0x18032102c`
- `0x180323274`
- `0x1803b1f60`
- `0x1803b1f84`
- `0x1803b243c`
- `0x1803b2ac0`
- `0x1803b69b9`
- `0x1803bc100`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b696`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b6a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b696`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b6a7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18008a4ad`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18008aa16`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18008aab8`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18008a4ad`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18008aa16`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18008aab8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008b00b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008b00b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18008afce`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18008afce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a54b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a560`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a575`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008abe3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008ace4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008ad1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b4df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b4ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b5df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a54b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a560`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a575`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008abe3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008ace4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008ad1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b4df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b4ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b5df`
- `SHCORE!__imp_SHManagedCreateStreamOnFile` at `0x18008adda`
- `SHCORE!__imp_SHManagedCreateStreamOnFile` at `0x18008adda`
- `SHCORE!__imp_CreateRandomAccessStreamOnFileWithOptions` at `0x18008b083`
- `SHCORE!__imp_CreateRandomAccessStreamOnFileWithOptions` at `0x18008b083`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18008b1a4`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18008b1a4`
- `edputil!EdpGetIsManaged` at `0x18008b096`
- `edputil!EdpGetIsManaged` at `0x18008b096`
- `srpapi!SrpRestoreEnterpriseContext` at `0x18008b0a9`
- `srpapi!SrpRestoreEnterpriseContext` at `0x18008b0a9`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18008ac1e`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18008ac1e`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageEx` at `0x18008b2b1`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageEx` at `0x18008b334`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageEx` at `0x18008b2b1`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageEx` at `0x18008b334`
- `ext-ms-win-com-ole32-l1-1-4!CreateFileMoniker` at `0x18008abc7`
- `ext-ms-win-com-ole32-l1-1-4!CreateFileMoniker` at `0x18008abc7`

## string_xrefs

- `0x18008ae6a`: `RandomAccessStreamMode`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall CFSFolder::_BindToChild(
        CFSFolder *this,
        struct IBindCtx *a2,
        const ITEMIDLIST *a3,
        const struct IDFOLDER *a4,
        IID *riid,
        void **ppv)
{
  CFSFolder *v8; // r12
  int v9; // ebx
  unsigned int v10; // esi
  __int64 v11; // rax
  void **v12; // rdi
  __int64 v13; // rbx
  WCHAR *v14; // rax
  WCHAR *v15; // rdi
  LPITEMIDLIST v16; // rax
  unsigned int v17; // edx
  HRESULT Handler; // r15d
  __int64 v19; // rcx
  IUnknown *v20; // rcx
  __int64 v21; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  const unsigned __int16 *v29; // rax
  HRESULT inited; // ebx
  struct IUnknown *v31; // rax
  struct IUnknown *v32; // r12
  HRESULT FreeThreadedMarshaler; // eax
  CFreeThreadedItemContainer *v34; // rcx
  CShellItem *v35; // rax
  const WCHAR *v36; // rax
  _QWORD *v37; // rax
  _QWORD *v38; // rbx
  LPCOLESTR v39; // rcx
  LPITEMIDLIST v40; // rax
  unsigned int v41; // edx
  CFSPropertyStoreFactory *v42; // rcx
  LPCOLESTR v43; // rcx
  int (__fastcall *v44)(char *, LPCITEMIDLIST, __int64, __int64); // rbx
  __int64 v45; // rax
  CFSFolder *v46; // rcx
  __int64 v47; // rax
  struct IDFOLDER *v48; // rbx
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  HRESULT FileMoniker; // eax
  WCHAR *v53; // rdi
  void *v54; // rcx
  int FileFlagsFromBindCtx; // ebx
  WCHAR *v56; // rcx
  __int64 (__fastcall *v57)(_QWORD, GUID *, WCHAR **); // rbx
  int v58; // eax
  __int64 v59; // rax
  const WCHAR *ExtensionW; // rax
  void **v61; // r8
  PCWSTR v62; // rbx
  WCHAR *v63; // rcx
  __int64 v64; // rax
  struct IUnknown *v65; // rbx
  enum GETPROPERTYSTOREFLAGS v66; // eax
  __int64 (__fastcall *v67)(char *, LPCITEMIDLIST, __int64, __int64); // rbx
  __int64 v68; // rax
  int v69; // ebx
  HRESULT v70; // eax
  struct IUnknown *v71; // rbx
  enum GETPROPERTYSTOREFLAGS v72; // eax
  int v73; // eax
  int Object; // eax
  WCHAR *v75; // rcx
  __int64 (__fastcall ***v76)(_QWORD, IID *, void **); // rcx
  __int64 (__fastcall *v77)(char *, LPCITEMIDLIST, __int64, __int64); // rbx
  __int64 v78; // rax
  WCHAR *v79; // rbx
  WCHAR *v80; // rcx
  int pdwType; // [rsp+20h] [rbp-E0h]
  WCHAR *pwcsName; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v83)(_QWORD, IID *, void **); // [rsp+50h] [rbp-B0h] BYREF
  WCHAR *v84; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v85; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v86[4]; // [rsp+68h] [rbp-98h] BYREF
  _WORD *v87; // [rsp+78h] [rbp-88h]
  int v88; // [rsp+80h] [rbp-80h]
  int v89; // [rsp+84h] [rbp-7Ch]
  __int64 v90; // [rsp+88h] [rbp-78h]
  LPCOLESTR lpszPathName; // [rsp+90h] [rbp-70h] BYREF
  DWORD pcbData[2]; // [rsp+98h] [rbp-68h] BYREF
  LPCITEMIDLIST pidl; // [rsp+A0h] [rbp-60h] BYREF
  struct IDFOLDER *v94; // [rsp+A8h] [rbp-58h] BYREF
  PCWSTR pszPath[3]; // [rsp+B0h] [rbp-50h] BYREF
  IUnknown *punk; // [rsp+C8h] [rbp-38h] BYREF
  HANDLE hObject[2]; // [rsp+D0h] [rbp-30h] BYREF
  void *v98; // [rsp+E0h] [rbp-20h]
  _QWORD v99[2]; // [rsp+F0h] [rbp-10h] BYREF
  LPVOID v100; // [rsp+100h] [rbp+0h]
  LPVOID v101; // [rsp+108h] [rbp+8h]
  LPVOID pv; // [rsp+120h] [rbp+20h]
  IUnknown *ppunk; // [rsp+128h] [rbp+28h] BYREF
  __int64 v104; // [rsp+130h] [rbp+30h]
  __int64 v105; // [rsp+138h] [rbp+38h]
  _WORD pvData[312]; // [rsp+3A0h] [rbp+2A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+668h] [rbp+568h]

  v94 = a4;
  pidl = a3;
  v8 = this;
  hObject[0] = this;
  *ppv = 0;
  CFileSysItemString::CFileSysItemString((CFileSysItemString *)v99, this, (const struct _ITEMIDLIST_RELATIVE *)a3, a4);
  punk = 0;
  pwcsName = 0;
  if ( a2
    && ((int (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, WCHAR **))a2->lpVtbl->GetObjectParam)(
         a2,
         L"Delegate Object Creation",
         &pwcsName) >= 0
    && (v9 = (**(__int64 (__fastcall ***)(WCHAR *, GUID *, IUnknown **))pwcsName)(
               pwcsName,
               &GUID_00000000_0000_0000_c000_000000000046,
               &punk),
        (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)pwcsName + 16LL))(pwcsName),
        v9 >= 0) )
  {
    IUnknown_Set(&ppunk, punk);
    v10 = 32;
  }
  else
  {
    v10 = 32;
    if ( !a2 )
      goto LABEL_7;
  }
  *(_OWORD *)pszPath = 0x10u;
  if ( ((int (__fastcall *)(struct IBindCtx *, PCWSTR *))a2->lpVtbl->GetBindOptions)(a2, pszPath) >= 0 )
    v10 = (unsigned int)pszPath[1];
LABEL_7:
  v11 = *(_QWORD *)&IID_IPropertyStoreFactory.Data1 - *(_QWORD *)&riid->Data1;
  if ( *(_QWORD *)&IID_IPropertyStoreFactory.Data1 == *(_QWORD *)&riid->Data1 )
    v11 = *(_QWORD *)IID_IPropertyStoreFactory.Data4 - *(_QWORD *)riid->Data4;
  if ( !v11 )
  {
    v12 = (void **)((char *)v8 + 904);
    v13 = *((_QWORD *)v8 + 113);
    if ( v13 )
    {
      *ppv = 0;
      v14 = (WCHAR *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
      v15 = v14;
      pszPath[0] = v14;
      if ( v14 )
      {
        *(_QWORD *)v14 = &CFSPropertyStoreFactory::`vftable'{for `IDelayedPropertyStoreFactory'};
        *((_QWORD *)v14 + 1) = &CFSPropertyStoreFactory::`vftable'{for `IFreeThreadedItemContainer'};
        *((_DWORD *)v14 + 4) = 1;
        *((_QWORD *)v14 + 4) = 0;
        *((_QWORD *)v14 + 5) = 0;
        *((_BYTE *)v14 + 49) = 0;
        *((_QWORD *)v14 + 3) = v13;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
        v16 = ILCloneFirst(pidl);
        *((_QWORD *)v15 + 4) = v16;
        if ( v16 )
          Handler = QISearch(v15, &stru_1806A4A50, riid, ppv);
        else
          Handler = -2147024882;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15 + 4, 0xFFFFFFFF) == 1 )
          CFSPropertyStoreFactory::`scalar deleting destructor'((CFSPropertyStoreFactory *)v15, v17);
      }
      else
      {
        Handler = -2147024882;
      }
    }
    else
    {
      v84 = 0;
      Handler = (**(__int64 (__fastcall ***)(CFSFolder *, GUID *, WCHAR **))v8)(
                  v8,
                  &GUID_127f6acb_7e78_4368_83a4_ed1de72baca6,
                  &v84);
      if ( Handler < 0 )
        goto LABEL_85;
      pwcsName = v84;
      *v12 = 0;
      lpszPathName = 0;
      inited = -2147024882;
      v31 = (struct IUnknown *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
      v32 = v31;
      pszPath[0] = (PCWSTR)v31;
      if ( v31 )
      {
        v31[4].lpVtbl = 0;
        v31->lpVtbl = (struct IUnknownVtbl *)&CFreeThreadedItemContainer::`vftable'{for `IFreeThreadedItemContainer'};
        v31[1].lpVtbl = (struct IUnknownVtbl *)&CFreeThreadedItemContainer::`vftable'{for `IInitializeWithItem'};
        v31[2].lpVtbl = (struct IUnknownVtbl *)&CFreeThreadedItemContainer::`vftable'{for `IPersistIDList'};
        v31[3].lpVtbl = (struct IUnknownVtbl *)&CFreeThreadedItemContainer::`vftable'{for `CFreeThreadedObject'};
        LODWORD(v31[5].lpVtbl) = 1;
        v31[8].lpVtbl = 0;
        v31[6].lpVtbl = 0;
        v31[7].lpVtbl = 0;
        v31[9].lpVtbl = 0;
        if ( !memcmp_0(&GUID_0c904b4a_164a_4d81_92d9_a5fc866f7fb8, &IID_IMarshal, 0x10u) )
          FreeThreadedMarshaler = CFreeThreadedObject::GetFreeThreadedMarshaler(
                                    (CFreeThreadedObject *)&v32[3],
                                    v32,
                                    &GUID_0c904b4a_164a_4d81_92d9_a5fc866f7fb8,
                                    (void **)&lpszPathName);
        else
          FreeThreadedMarshaler = QISearch(
                                    v32,
                                    &`CFreeThreadedItemContainer::QueryInterface'::`2'::qit,
                                    &GUID_0c904b4a_164a_4d81_92d9_a5fc866f7fb8,
                                    (void **)&lpszPathName);
        inited = FreeThreadedMarshaler;
        v34 = (CFreeThreadedItemContainer *)pszPath[0];
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)pszPath[0] + 10, 0xFFFFFFFF) == 1 )
        {
          CFreeThreadedItemContainer::~CFreeThreadedItemContainer(v34);
          operator delete((void *)pszPath[0], (const struct std::nothrow_t *)0x50);
        }
        if ( inited >= 0 )
        {
          v85 = 0;
          inited = (**(__int64 (__fastcall ***)(LPCOLESTR, GUID *, __int64 *))lpszPathName)(
                     lpszPathName,
                     &GUID_7f73be3f_fb79_493c_a6c7_7ee14e245841,
                     &v85);
          if ( inited >= 0 )
          {
            *(_QWORD *)pcbData = 0;
            inited = (**(__int64 (__fastcall ***)(WCHAR *, GUID *, DWORD *))pwcsName)(
                       pwcsName,
                       &GUID_000214e6_0000_0000_c000_000000000046,
                       pcbData);
            if ( inited >= 0 )
            {
              pwcsName = 0;
              inited = -2147024882;
              v35 = (CShellItem *)operator new(0xD8u, (const struct std::nothrow_t *)&std::nothrow);
              if ( v35 )
              {
                v36 = (const WCHAR *)CShellItem::CShellItem(v35);
                pszPath[0] = v36;
                if ( v36 )
                {
                  inited = CObjectWithThreadUseDetection::InitApartmentId((CObjectWithThreadUseDetection *)(v36 + 40));
                  if ( inited >= 0 )
                    inited = (**(__int64 (__fastcall ***)(PCWSTR, GUID *, WCHAR **))pszPath[0])(
                               pszPath[0],
                               &GUID_1cbff8c0_da47_4ebe_9928_2e642f00b5bc,
                               &pwcsName);
                  (*(void (__fastcall **)(PCWSTR))(*(_QWORD *)pszPath[0] + 16LL))(pszPath[0]);
                  if ( inited >= 0 )
                  {
                    inited = (*(__int64 (__fastcall **)(WCHAR *, _QWORD))(*(_QWORD *)pwcsName + 24LL))(
                               pwcsName,
                               *(_QWORD *)pcbData);
                    if ( inited >= 0 )
                    {
                      v83 = 0;
                      inited = (**(__int64 (__fastcall ***)(WCHAR *, GUID *, _QWORD))pwcsName)(
                                 pwcsName,
                                 &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                 &v83);
                      if ( inited >= 0 )
                      {
                        inited = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v85 + 24LL))(
                                   v85,
                                   v83,
                                   0);
                        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, IID *, void **)))(*v83)[2])(v83);
                      }
                    }
                    (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)pwcsName + 16LL))(pwcsName);
                  }
                }
              }
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pcbData + 16LL))(*(_QWORD *)pcbData);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
            if ( inited >= 0 )
            {
              v37 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
              v38 = v37;
              pszPath[0] = (PCWSTR)v37;
              if ( v37 )
              {
                *v37 = &CFSPropertyStoreFactory::`vftable'{for `IDelayedPropertyStoreFactory'};
                v37[1] = &CFSPropertyStoreFactory::`vftable'{for `IFreeThreadedItemContainer'};
                *((_DWORD *)v37 + 4) = 1;
                v37[3] = 0;
                v37[4] = 0;
                v37[5] = 0;
                *((_BYTE *)v37 + 49) = 0;
                v39 = lpszPathName;
                v37[3] = lpszPathName;
                (*(void (__fastcall **)(LPCOLESTR))(*(_QWORD *)v39 + 8LL))(v39);
                v40 = ILCloneFirst(pidl);
                v38[4] = v40;
                if ( v40 )
                  inited = QISearch(v38, &stru_1806A4A50, &GUID_0c904b4a_164a_4d81_92d9_a5fc866f7fb8, v12);
                else
                  inited = -2147024882;
                v42 = (CFSPropertyStoreFactory *)pszPath[0];
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)pszPath[0] + 4, 0xFFFFFFFF) == 1 )
                  CFSPropertyStoreFactory::`scalar deleting destructor'(v42, v41);
              }
              else
              {
                inited = -2147024882;
              }
            }
          }
        }
      }
      v43 = lpszPathName;
      lpszPathName = 0;
      if ( v43 )
        (*(void (__fastcall **)(LPCOLESTR))(*(_QWORD *)v43 + 16LL))(v43);
      if ( inited < 0 )
      {
        Handler = inited;
      }
      else
      {
        (*(void (__fastcall **)(char *))(*((_QWORD *)hObject[0] + 29) + 24LL))((char *)hObject[0] + 232);
        Handler = (**(__int64 (__fastcall ***)(void *, IID *, void **))*v12)(*v12, riid, ppv);
      }
      (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v84 + 16LL))(v84);
    }
    goto LABEL_16;
  }
  if ( (unsigned int)IsPropertyIID(riid) )
  {
    v64 = *(_QWORD *)&IID_IPropertySetStorage.Data1 - *(_QWORD *)&riid->Data1;
    if ( *(_QWORD *)&IID_IPropertySetStorage.Data1 == *(_QWORD *)&riid->Data1 )
      v64 = *(_QWORD *)IID_IPropertySetStorage.Data4 - *(_QWORD *)riid->Data4;
    if ( v64 || (unsigned int)SHWindowsPolicy(POLID_DisableBindDirectlyToPropertySetStorage) )
    {
      if ( (v10 & 1) != 0 )
      {
        Handler = -2147024809;
        goto LABEL_87;
      }
      if ( (v10 & 2) != 0 && (GetFullFileAttributes(v94) & 1) != 0 )
      {
        Handler = -2147287035;
        goto LABEL_17;
      }
      v65 = punk;
      v66 = FlagsFromBindCtx(a2, v10);
      Handler = CFSFolder::_BindToPropertyStore(v8, (const struct _ITEMID_CHILD *)a3, v66, v65, riid, ppv);
      goto LABEL_16;
    }
    pwcsName = 0;
    v67 = *(__int64 (__fastcall **)(char *, LPCITEMIDLIST, __int64, __int64))(*((_QWORD *)v8 + 39) + 112LL);
    v68 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pwcsName);
    Handler = v67((char *)v8 + 312, pidl, 1, v68);
    if ( Handler >= 0 )
    {
      v83 = 0;
      lpszPathName = 0;
      if ( a2 )
      {
        if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, LPCOLESTR *))a2->lpVtbl->GetObjectParam)(
               a2,
               L"OplockProvider",
               &lpszPathName) >= 0 )
        {
          v69 = (**(__int64 (__fastcall ***)(LPCOLESTR, GUID *, _QWORD))lpszPathName)(
                  lpszPathName,
                  &GUID_3119d9ab_dc96_4508_bc7d_14fbb3cb05e2,
                  &v83);
          (*(void (__fastcall **)(LPCOLESTR))(*(_QWORD *)lpszPathName + 16LL))(lpszPathName);
          if ( v69 >= 0 )
          {
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, IID *, void **), WCHAR *, _QWORD, _QWORD))(*v83)[4])(
              v83,
              pwcsName,
              0,
              0);
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, IID *, void **)))(*v83)[2])(v83);
          }
        }
      }
      v70 = StgOpenStorageEx(pwcsName, v10, 0, 0, 0, 0, riid, ppv);
      Handler = v70;
      if ( v70 < 0 && !(unsigned int)FailForceReturn(v70) )
      {
        v71 = punk;
        v72 = FlagsFromBindCtx(a2, v10);
        v73 = CFSFolder::_BindToPropertyStore(
                v8,
                (const struct _ITEMID_CHILD *)pidl,
                (enum GETPROPERTYSTOREFLAGS)(v72 | 1),
                v71,
                riid,
                ppv);
        Handler = v73;
        if ( v73 < 0 && !(unsigned int)FailForceReturn(v73) )
          Handler = StgOpenStorageEx(pwcsName, v10, 3u, 0, 0, 0, riid, ppv);
      }
    }
    v54 = pwcsName;
    goto LABEL_115;
  }
  v23 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_ITransferMediumItem.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_ITransferMediumItem.Data1 )
    v23 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_ITransferMediumItem.Data4;
  if ( v23 )
  {
    v24 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_ILocallyCachedItem.Data1;
    if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_ILocallyCachedItem.Data1 )
      v24 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_ILocallyCachedItem.Data4;
    if ( v24 )
    {
      Handler = -2147467259;
      v25 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IStream.Data1;
      if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IStream.Data1 )
        v25 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IStream.Data4;
      if ( !v25 )
        goto LABEL_87;
      v26 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data1;
      if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data1 )
        v26 = *(_QWORD *)riid->Data4 - *(_QWORD *)GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data4;
      if ( !v26 )
        goto LABEL_87;
      v27 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IMoniker.Data1;
      if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IMoniker.Data1 )
        v27 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IMoniker.Data4;
      if ( !v27 )
        goto LABEL_87;
      v28 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IPropertyBag.Data1;
      if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IPropertyBag.Data1 )
        v28 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IPropertyBag.Data4;
      if ( !v28 )
        goto LABEL_87;
      v29 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, IID *))(*((_QWORD *)v8 + 39) + 56LL))(
                                        (__int64)v8 + 312,
                                        riid);
      Handler = CFileSysItemString::LoadHandler((CFileSysItemString *)v99, v10, v29, a2, 0, &BHID_SFObject, riid, ppv);
      goto LABEL_16;
    }
    lpszPathName = 0;
    if ( (unsigned int)CFSFolder::_IsNetFolder(v8) )
    {
      v77 = *(__int64 (__fastcall **)(char *, LPCITEMIDLIST, __int64, __int64))(*((_QWORD *)v8 + 39) + 112LL);
      v78 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&lpszPathName);
      Handler = v77((char *)v8 + 312, pidl, 1, v78);
      if ( Handler >= 0 )
      {
        pszPath[0] = 0;
        pszPath[1] = (PCWSTR)-1LL;
        pszPath[2] = (PCWSTR)-1LL;
        Handler = PathConvertToCSC(lpszPathName, (unsigned __int16 **)pszPath);
        v79 = (WCHAR *)pszPath[0];
        if ( Handler >= 0 )
        {
          pwcsName = 0;
          Handler = SHCreateItemFromParsingName(
                      pszPath[0],
                      0,
                      &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                      (void **)&pwcsName);
          if ( Handler >= 0 )
            Handler = SHCreateRelatedItem((struct IShellItem *)pwcsName, riid);
          if ( pwcsName )
            (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)pwcsName + 16LL))(pwcsName);
        }
        if ( v79 )
          CoTaskMemFree(v79);
      }
    }
    else
    {
      Handler = -2147467262;
    }
    v54 = (void *)lpszPathName;
LABEL_115:
    if ( v54 )
      CoTaskMemFree(v54);
    goto LABEL_16;
  }
  memset_0(pvData, 0, 0x268u);
  Handler = CFileSysItemString::GetFindData(v99, 0, pvData);
  if ( Handler < 0 )
    goto LABEL_85;
  pwcsName = 0;
  pdwType = (int)a2;
  Handler = CFSFolder::_CreateIDListWithBindCtx(v8, pvData, 0, 0);
  if ( Handler < 0 )
    goto LABEL_85;
  v53 = pwcsName;
  if ( *((_QWORD *)v8 + 80) )
  {
    pszPath[0] = 0;
    Handler = CFSFolder::_CombineWithFolderIDList(
                v8,
                (const struct _ITEMIDLIST_RELATIVE *)pwcsName,
                (struct _ITEMIDLIST_ABSOLUTE **)pszPath);
    if ( Handler >= 0 )
    {
      Handler = SHCreateRelatedItemFromIDList(pszPath[0], riid, ppv);
      CoTaskMemFree((LPVOID)pszPath[0]);
      CoTaskMemFree(v53);
      goto LABEL_16;
    }
  }
  else
  {
    Handler = SHCreateRelatedItemWithParent((char *)v8 + 48, pwcsName, riid, ppv);
  }
  CoTaskMemFree(v53);
LABEL_16:
  if ( Handler >= 0 )
    goto LABEL_17;
  v8 = (CFSFolder *)hObject[0];
LABEL_85:
  if ( Handler == -2147287035 || Handler == -2147287008 )
    goto LABEL_17;
LABEL_87:
  lpszPathName = 0;
  v44 = *(int (__fastcall **)(char *, LPCITEMIDLIST, __int64, __int64))(*((_QWORD *)v8 + 39) + 112LL);
  v45 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&lpszPathName);
  if ( v44((char *)v8 + 312, pidl, 1, v45) >= 0 )
  {
    v47 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IStream.Data1;
    if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IStream.Data1 )
      v47 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IStream.Data4;
    v48 = v94;
    if ( v47 || (((*((_BYTE *)v94 + 2) & 0x37) - 50) & 0xFB) != 0 )
    {
      v49 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data1;
      if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data1 )
        v49 = *(_QWORD *)riid->Data4 - *(_QWORD *)GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data4;
      if ( v49 || !(unsigned int)CFSFolder::_IsFile(v46, v94) )
      {
        v50 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IPropertyBag.Data1;
        if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IPropertyBag.Data1 )
          v50 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IPropertyBag.Data4;
        if ( v50 || !(unsigned int)IsFolder(v48) )
        {
          v51 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IMoniker.Data1;
          if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IMoniker.Data1 )
            v51 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IMoniker.Data4;
          if ( v51 )
            goto LABEL_102;
          FileMoniker = CreateFileMoniker(lpszPathName, (LPMONIKER *)ppv);
        }
        else
        {
          FileMoniker = CFSFolder::_CreateFolderPropertyBag(
                          v8,
                          v10,
                          (const struct _ITEMIDLIST_RELATIVE *)pidl,
                          riid,
                          ppv);
        }
        Handler = FileMoniker;
      }
      else
      {
        v83 = 0;
        Handler = -2147467262;
        pwcsName = 0;
        if ( a2 )
        {
          if ( ((int (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, WCHAR **))a2->lpVtbl->GetObjectParam)(
                 a2,
                 L"RandomAccessStreamMode",
                 &pwcsName) >= 0 )
          {
            Handler = (**(__int64 (__fastcall ***)(WCHAR *, GUID *, _QWORD))pwcsName)(
                        pwcsName,
                        &GUID_ba433434_2f07_4f5e_94ae_35c82fe1708a,
                        &v83);
            (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)pwcsName + 16LL))(pwcsName);
            if ( Handler >= 0 )
            {
              LODWORD(v94) = 0;
              Handler = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, IID *, void **), struct IDFOLDER **))(*v83)[3])(
                          v83,
                          &v94);
              if ( Handler >= 0 )
              {
                LODWORD(v84) = 0;
                Handler = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, IID *, void **), WCHAR **))(*v83)[4])(
                            v83,
                            &v84);
                if ( Handler >= 0 )
                {
                  LODWORD(v85) = 0;
                  Handler = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, IID *, void **), __int64 *))(*v83)[5])(
                              v83,
                              &v85);
                  if ( Handler >= 0 )
                  {
                    LODWORD(pidl) = 0;
                    pwcsName = 0;
                    v57 = (__int64 (__fastcall *)(_QWORD, GUID *, WCHAR **))**v83;
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pwcsName);
                    Handler = v57(v83, &GUID_2a33a3b1_21c9_4d11_bc6f_54f3f88d4190, &pwcsName);
                    if ( Handler >= 0 )
                    {
                      v58 = (*(__int64 (__fastcall **)(WCHAR *, LPCITEMIDLIST *))(*(_QWORD *)pwcsName + 24LL))(
                              pwcsName,
                              &pidl);
                      if ( v58 < 0 )
                        wil::details::in1diag3::_Log_Hr(
                          retaddr,
                          (void *)0x2833,
                          (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
                          (const char *)(unsigned int)v58,
                          pdwType);
                      hObject[0] = 0;
                      LOBYTE(hObject[1]) = 0;
                      v59 = *(_QWORD *)pwcsName;
                      hObject[0] = 0;
                      Handler = (*(__int64 (__fastcall **)(WCHAR *, HANDLE *))(v59 + 32))(pwcsName, hObject);
                      if ( Handler >= 0 )
                      {
                        pvData[0] = 0;
                        pcbData[0] = 520;
                        ExtensionW = PathFindExtensionW(lpszPathName);
                        if ( RegGetValueW(HKEY_CLASSES_ROOT, ExtensionW, L"Content Type", 2u, 0, pvData, pcbData) )
                          pvData[0] = 0;
                        v86[0] = (_DWORD)v94;
                        v86[1] = (_DWORD)v84;
                        v86[2] = v85;
                        v86[3] = 0;
                        v87 = pvData;
                        v88 = (int)pidl;
                        v89 = 0;
                        v90 = 0;
                        pszPath[0] = 0;
                        Handler = EdpHelpers::InheritCallerEnterpriseContextWithNetworkOverride(
                                    (EdpHelpers *)hObject[0],
                                    pszPath,
                                    v61);
                        if ( Handler >= 0 )
                        {
                          Handler = CreateRandomAccessStreamOnFileWithOptions(lpszPathName, v86, riid, ppv);
                          v62 = pszPath[0];
                          if ( (unsigned int)EdpGetIsManaged() )
                            SrpRestoreEnterpriseContext(v62);
                        }
                        if ( (unsigned __int64)pszPath[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
                          CloseHandle((HANDLE)pszPath[0]);
                      }
                      if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
                        CloseHandle(hObject[0]);
                    }
                    v63 = pwcsName;
                    if ( pwcsName )
                    {
                      pwcsName = 0;
                      (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v63 + 16LL))(v63);
                    }
                  }
                }
              }
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, IID *, void **)))(*v83)[2])(v83);
            }
          }
        }
      }
    }
    else if ( CFileSysItemString::FileIsPartialPlaceholder((CFileSysItemString *)v99)
           && (GetFullFileAttributes(v48) & 0x1000) != 0
           && (unsigned int)BindCtx_ContainsObject(a2, L"BindToThumbnailStream") )
    {
      *(_QWORD *)pcbData = 0;
      Handler = CFSFolder::_BindToPropertyStore(
                  v8,
                  (const struct _ITEMID_CHILD *)pidl,
                  GPS_EXTRINSICPROPERTIESONLY,
                  punk,
                  &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                  (void **)pcbData);
      if ( Handler >= 0 )
      {
        v83 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
        *(GUID *)hObject = PKEY_ThumbnailStream.fmtid;
        LODWORD(v98) = PKEY_ThumbnailStream.pid;
        Object = CPropertyStoreHelperBase<IPropertyStore>::GetObjectW<_tagpropertykey>(
                   pcbData,
                   hObject,
                   &GUID_0000000c_0000_0000_c000_000000000046,
                   &v83);
        Handler = Object;
        if ( Object < 0 )
        {
          if ( Object == -2147023728 )
          {
            pwcsName = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pwcsName);
            if ( (int)GetObjectFromBindCtx(
                        a2,
                        L"BindToThumbnailStream",
                        &GUID_5d7dccbd_8d93_4163_b5f3_8b23ee8961e5,
                        (void **)&pwcsName) >= 0 )
              (*(void (__fastcall **)(WCHAR *, __int64))(*(_QWORD *)pwcsName + 24LL))(pwcsName, 8);
            v80 = pwcsName;
            if ( pwcsName )
            {
              pwcsName = 0;
              (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v80 + 16LL))(v80);
            }
          }
        }
        else
        {
          pwcsName = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pwcsName);
          if ( (int)GetObjectFromBindCtx(
                      a2,
                      L"BindToThumbnailStream",
                      &GUID_5d7dccbd_8d93_4163_b5f3_8b23ee8961e5,
                      (void **)&pwcsName) >= 0 )
            (*(void (__fastcall **)(WCHAR *, __int64))(*(_QWORD *)pwcsName + 24LL))(pwcsName, 7);
          Handler = (**v83)(v83, riid, ppv);
          v75 = pwcsName;
          if ( pwcsName )
          {
            pwcsName = 0;
            (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v75 + 16LL))(v75);
          }
        }
        v76 = v83;
        if ( v83 )
        {
          v83 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, IID *, void **)))(*v76)[2])(v76);
        }
      }
      if ( *(_QWORD *)pcbData )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pcbData + 16LL))(*(_QWORD *)pcbData);
    }
    else
    {
      LODWORD(v94) = 0;
      hObject[0] = (HANDLE)lpszPathName;
      v98 = 0;
      LODWORD(hObject[1]) = 0;
      if ( !(unsigned __int8)IsSHELL32_SHIsVirtualDevicePresent()
        || (GetFullFileAttributes(v48) & 0x4010) != 0x4000
        || (int)CEfsUtil::IsPinRequired((CEfsUtil *)hObject, (int *)&v94) >= 0 && !(_DWORD)v94 )
      {
        pwcsName = 0;
        FileFlagsFromBindCtx = _ManagedCreateFileFlagsFromBindCtx(a2);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pwcsName);
        Handler = SHManagedCreateStreamOnFile(lpszPathName, v10, 128, 0, 0, FileFlagsFromBindCtx, &pwcsName);
        if ( Handler >= 0 )
          Handler = (**(__int64 (__fastcall ***)(WCHAR *, IID *, void **))pwcsName)(pwcsName, riid, ppv);
        v56 = pwcsName;
        if ( pwcsName )
        {
          pwcsName = 0;
          (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v56 + 16LL))(v56);
        }
      }
      operator delete(v98, (const struct std::nothrow_t *)1);
    }
  }
LABEL_102:
  if ( lpszPathName )
    CoTaskMemFree((LPVOID)lpszPathName);
LABEL_17:
  if ( punk )
    ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
  v99[0] = &CFileSysItemString::`vftable';
  v19 = v105;
  v105 = 0;
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  v20 = ppunk;
  ppunk = 0;
  if ( v20 )
    ((void (__fastcall *)(IUnknown *))v20->lpVtbl->Release)(v20);
  v21 = v104;
  v104 = 0;
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v101 )
    CoTaskMemFree(v101);
  if ( v100 )
    CoTaskMemFree(v100);
  return (unsigned int)Handler;
}

```

## disassembly

```asm
0x18008a2f0  push    rbp
0x18008a2f2  push    rbx
0x18008a2f3  push    rsi
0x18008a2f4  push    rdi
0x18008a2f5  push    r12
0x18008a2f7  push    r13
0x18008a2f9  push    r14
0x18008a2fb  push    r15
0x18008a2fd  lea     rbp, [rsp-528h]
0x18008a305  sub     rsp, 628h
0x18008a30c  mov     rax, cs:__security_cookie
0x18008a313  xor     rax, rsp
0x18008a316  mov     [rbp+560h+var_50], rax
0x18008a31d  mov     [rbp+560h+var_5B8], r9
0x18008a321  mov     rdi, r8
0x18008a324  mov     [rbp+560h+pidl], r8
0x18008a328  mov     r14, rdx
0x18008a32b  mov     r12, rcx
0x18008a32e  mov     [rbp+560h+hObject], rcx
0x18008a332  mov     r13, [rbp+560h+riid]
0x18008a339  mov     r15, [rbp+560h+ppv]
0x18008a340  mov     [rsp+660h+ppmk], r15
0x18008a345  xor     ebx, ebx
0x18008a347  mov     [r15], rbx
0x18008a34a  mov     rdx, rcx; struct CFSFolder *
0x18008a34d  lea     rcx, [rbp+560h+var_570]; this
0x18008a351  call    ??0CFileSysItemString@@QEAA@PEAVCFSFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEFBUIDFOLDER@@@Z; CFileSysItemString::CFileSysItemString(CFSFolder *,_ITEMIDLIST_RELATIVE const *,IDFOLDER const *)
0x18008a356  nop
0x18008a357  mov     [rbp+560h+punk], rbx
0x18008a35b  mov     [rsp+660h+pwcsName], rbx
0x18008a360  test    r14, r14
0x18008a363  jz      short loc_18008A3BD
0x18008a365  mov     rax, [r14]
0x18008a368  lea     r8, [rsp+660h+pwcsName]
0x18008a36d  lea     rdx, aDelegateObject; "Delegate Object Creation"
0x18008a374  mov     rcx, r14
0x18008a377  mov     rax, [rax+50h]
0x18008a37b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a380  test    eax, eax
0x18008a382  js      short loc_18008A3BD
0x18008a384  mov     rcx, [rsp+660h+pwcsName]
0x18008a389  mov     rax, [rcx]
0x18008a38c  lea     r8, [rbp+560h+punk]
0x18008a390  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18008a397  mov     rax, [rax]
0x18008a39a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a39f  mov     ebx, eax
0x18008a3a1  mov     rdx, [rsp+660h+pwcsName]
0x18008a3a6  mov     rcx, [rdx]
0x18008a3a9  mov     rax, [rcx+10h]
0x18008a3ad  mov     rcx, rdx
0x18008a3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a3b5  test    ebx, ebx
0x18008a3b7  jns     loc_18008AC16
0x18008a3bd  mov     esi, 20h ; ' '
0x18008a3c2  test    r14, r14
0x18008a3c5  jz      short loc_18008A3F0
0x18008a3c7  mov     dword ptr [rbp+560h+pszPath], 10h
0x18008a3ce  xor     eax, eax
0x18008a3d0  mov     [rbp+560h+pszPath+4], rax
0x18008a3d4  mov     [rbp+560h+var_5A4], eax
0x18008a3d7  mov     rax, [r14]
0x18008a3da  lea     rdx, [rbp+560h+pszPath]
0x18008a3de  mov     rcx, r14
0x18008a3e1  mov     rax, [rax+38h]
0x18008a3e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a3ea  test    eax, eax
0x18008a3ec  cmovns  esi, [rbp-48h]
0x18008a3f0  mov     rax, qword ptr cs:IID_IPropertyStoreFactory.Data1
0x18008a3f7  sub     rax, [r13+0]
0x18008a3fb  jnz     short loc_18008A408
0x18008a3fd  mov     rax, qword ptr cs:IID_IPropertyStoreFactory.Data4
0x18008a404  sub     rax, [r13+8]
0x18008a408  test    rax, rax
0x18008a40b  jnz     loc_18008A5A9
0x18008a411  lea     rdi, [r12+388h]
0x18008a419  mov     rbx, [rdi]
0x18008a41c  test    rbx, rbx
0x18008a41f  jz      loc_18008A6EA
0x18008a425  xor     r12d, r12d
0x18008a428  mov     [r15], r12
0x18008a42b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008a432  mov     ecx, 38h ; '8'; unsigned __int64
0x18008a437  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18008a43c  mov     rdi, rax
0x18008a43f  mov     [rbp+560h+pszPath], rax
0x18008a443  test    rax, rax
0x18008a446  jz      loc_18008AC34
0x18008a44c  lea     rax, ??_7CFSPropertyStoreFactory@@6BIDelayedPropertyStoreFactory@@@; const CFSPropertyStoreFactory::`vftable'{for `IDelayedPropertyStoreFactory'}
0x18008a453  mov     [rdi], rax
0x18008a456  lea     rax, ??_7CFSPropertyStoreFactory@@6BIFreeThreadedItemContainer@@@; const CFSPropertyStoreFactory::`vftable'{for `IFreeThreadedItemContainer'}
0x18008a45d  mov     [rdi+8], rax
0x18008a461  mov     dword ptr [rdi+10h], 1
0x18008a468  mov     [rdi+20h], r12
0x18008a46c  mov     [rdi+28h], r12
0x18008a470  mov     [rdi+31h], r12b
0x18008a474  mov     [rdi+18h], rbx
0x18008a478  mov     rax, [rbx]
0x18008a47b  mov     rcx, rbx
0x18008a47e  mov     rax, [rax+8]
0x18008a482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a487  mov     rcx, [rbp+560h+pidl]; pidl
0x18008a48b  call    ILCloneFirst
0x18008a490  mov     [rdi+20h], rax
0x18008a494  test    rax, rax
0x18008a497  jz      loc_18008AAA3
0x18008a49d  mov     r9, r15; ppv
0x18008a4a0  mov     r8, r13; riid
0x18008a4a3  lea     rdx, stru_1806A4A50; pqit
0x18008a4aa  mov     rcx, rdi; that
0x18008a4ad  call    cs:__imp_QISearch
0x18008a4b4  nop     dword ptr [rax+rax+00h]
0x18008a4b9  mov     r15d, eax
0x18008a4bc  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18008a4c3  lock xadd [rdi+10h], r12d
0x18008a4c9  cmp     r12d, 1
0x18008a4cd  jz      loc_18008AAD1
0x18008a4d3  test    r15d, r15d
0x18008a4d6  js      loc_18008B68D
0x18008a4dc  mov     rcx, [rbp+560h+punk]
0x18008a4e0  test    rcx, rcx
0x18008a4e3  jz      short loc_18008A4F2
0x18008a4e5  mov     rax, [rcx]
0x18008a4e8  mov     rax, [rax+10h]
0x18008a4ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a4f1  nop
0x18008a4f2  lea     rax, ??_7CFileSysItemString@@6B@; const CFileSysItemString::`vftable'
0x18008a4f9  mov     [rbp+560h+var_570], rax
0x18008a4fd  mov     rcx, [rbp+560h+var_528]
0x18008a501  xor     ebx, ebx
0x18008a503  mov     [rbp+560h+var_528], rbx
0x18008a507  test    rcx, rcx
0x18008a50a  jz      short loc_18008A518
0x18008a50c  mov     rax, [rcx]
0x18008a50f  mov     rax, [rax+10h]
0x18008a513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a518  mov     rcx, [rbp+560h+ppunk]
0x18008a51c  mov     [rbp+560h+ppunk], rbx
0x18008a520  test    rcx, rcx
0x18008a523  jnz     loc_18008A6D9
0x18008a529  mov     rcx, [rbp+560h+var_530]
0x18008a52d  mov     [rbp+560h+var_530], rbx
0x18008a531  test    rcx, rcx
0x18008a534  jz      short loc_18008A542
0x18008a536  mov     rax, [rcx]
0x18008a539  mov     rax, [rax+10h]
0x18008a53d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a542  mov     rcx, [rbp+560h+pv]; pv
0x18008a546  test    rcx, rcx
0x18008a549  jz      short loc_18008A557
0x18008a54b  call    cs:__imp_CoTaskMemFree
0x18008a552  nop     dword ptr [rax+rax+00h]
0x18008a557  mov     rcx, [rbp+560h+var_558]; pv
0x18008a55b  test    rcx, rcx
0x18008a55e  jz      short loc_18008A56C
0x18008a560  call    cs:__imp_CoTaskMemFree
0x18008a567  nop     dword ptr [rax+rax+00h]
0x18008a56c  mov     rcx, [rbp+560h+var_560]; pv
0x18008a570  test    rcx, rcx
0x18008a573  jz      short loc_18008A582
0x18008a575  call    cs:__imp_CoTaskMemFree
0x18008a57c  nop     dword ptr [rax+rax+00h]
0x18008a581  nop
0x18008a582  mov     eax, r15d
0x18008a585  mov     rcx, [rbp+560h+var_50]
0x18008a58c  xor     rcx, rsp; StackCookie
0x18008a58f  call    __security_check_cookie
0x18008a594  add     rsp, 628h
0x18008a59b  pop     r15
0x18008a59d  pop     r14
0x18008a59f  pop     r13
0x18008a5a1  pop     r12
0x18008a5a3  pop     rdi
0x18008a5a4  pop     rsi
0x18008a5a5  pop     rbx
0x18008a5a6  pop     rbp
0x18008a5a7  retn
0x18008a5a9  mov     rcx, r13; struct _GUID *
0x18008a5ac  call    ?IsPropertyIID@@YAHAEBU_GUID@@@Z; IsPropertyIID(_GUID const &)
0x18008a5b1  test    eax, eax
0x18008a5b3  jnz     loc_18008B13B
0x18008a5b9  mov     rax, [r13+0]
0x18008a5bd  sub     rax, qword ptr cs:IID_ITransferMediumItem.Data1
0x18008a5c4  jnz     short loc_18008A5D1
0x18008a5c6  mov     rax, [r13+8]
0x18008a5ca  sub     rax, qword ptr cs:IID_ITransferMediumItem.Data4
0x18008a5d1  test    rax, rax
0x18008a5d4  jz      loc_18008AC47
0x18008a5da  mov     rax, [r13+0]
0x18008a5de  sub     rax, qword ptr cs:IID_ILocallyCachedItem.Data1
0x18008a5e5  jnz     short loc_18008A5F2
0x18008a5e7  mov     rax, [r13+8]
0x18008a5eb  sub     rax, qword ptr cs:IID_ILocallyCachedItem.Data4
0x18008a5f2  test    rax, rax
0x18008a5f5  jz      loc_18008ACF5
0x18008a5fb  mov     r15d, 80004005h
0x18008a601  mov     rax, [r13+0]
0x18008a605  sub     rax, qword ptr cs:IID_IStream.Data1
0x18008a60c  jnz     short loc_18008A619
0x18008a60e  mov     rax, [r13+8]
0x18008a612  sub     rax, qword ptr cs:IID_IStream.Data4
0x18008a619  test    rax, rax
0x18008a61c  jz      loc_18008AAF8
0x18008a622  mov     rax, [r13+0]
0x18008a626  sub     rax, qword ptr cs:_GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data1
0x18008a62d  jnz     short loc_18008A63A
0x18008a62f  mov     rax, [r13+8]
0x18008a633  sub     rax, qword ptr cs:_GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data4
0x18008a63a  test    rax, rax
0x18008a63d  jz      loc_18008AAF8
0x18008a643  mov     rax, [r13+0]
0x18008a647  sub     rax, qword ptr cs:IID_IMoniker.Data1
0x18008a64e  jnz     short loc_18008A65B
0x18008a650  mov     rax, [r13+8]
0x18008a654  sub     rax, qword ptr cs:IID_IMoniker.Data4
0x18008a65b  test    rax, rax
0x18008a65e  jz      loc_18008AAF8
0x18008a664  mov     rax, [r13+0]
0x18008a668  sub     rax, qword ptr cs:IID_IPropertyBag.Data1
0x18008a66f  jnz     short loc_18008A67C
0x18008a671  mov     rax, [r13+8]
0x18008a675  sub     rax, qword ptr cs:IID_IPropertyBag.Data4
0x18008a67c  test    rax, rax
0x18008a67f  jz      loc_18008AAF8
0x18008a685  lea     rcx, [r12+138h]
0x18008a68d  mov     rax, [rcx]
0x18008a690  mov     rdx, r13
0x18008a693  mov     rax, [rax+38h]
0x18008a697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a69c  mov     r8, rax; unsigned __int16 *
0x18008a69f  mov     rax, [rsp+660h+ppmk]
0x18008a6a4  mov     [rsp+660h+ppObjectOpen], rax; void **
0x18008a6a9  mov     [rsp+660h+pcbData], r13; struct _GUID *
0x18008a6ae  lea     rax, BHID_SFObject
0x18008a6b5  mov     [rsp+660h+pvData], rax; struct _GUID *
0x18008a6ba  mov     [rsp+660h+pdwType], 0; struct IOplockProvider *
0x18008a6c3  mov     r9, r14; struct IBindCtx *
0x18008a6c6  mov     edx, esi; unsigned int
0x18008a6c8  lea     rcx, [rbp+560h+var_570]; this
0x18008a6cc  call    ?LoadHandler@CFileSysItemString@@QEAAJKPEBGPEAUIBindCtx@@PEAUIOplockProvider@@AEBU_GUID@@3PEAPEAX@Z; CFileSysItemString::LoadHandler(ulong,ushort const *,IBindCtx *,IOplockProvider *,_GUID const &,_GUID const &,void * *)
0x18008a6d1  mov     r15d, eax
0x18008a6d4  jmp     loc_18008A4D3
0x18008a6d9  mov     rax, [rcx]
0x18008a6dc  mov     rax, [rax+10h]
0x18008a6e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a6e5  jmp     loc_18008A529
0x18008a6ea  mov     [rsp+660h+var_608], rbx
0x18008a6ef  mov     rax, [r12]
0x18008a6f3  lea     r8, [rsp+660h+var_608]
0x18008a6f8  lea     rdx, _GUID_127f6acb_7e78_4368_83a4_ed1de72baca6
0x18008a6ff  mov     rcx, r12
0x18008a702  mov     rax, [rax]
0x18008a705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a70a  mov     r15d, eax
0x18008a70d  test    eax, eax
0x18008a70f  js      loc_18008AADE
0x18008a715  mov     rax, [rsp+660h+var_608]
0x18008a71a  mov     [rsp+660h+pwcsName], rax
0x18008a71f  mov     [rdi], rbx
0x18008a722  mov     [rbp+560h+lpszPathName], rbx
0x18008a726  mov     r15d, 8007000Eh
0x18008a72c  mov     ebx, r15d
0x18008a72f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008a736  mov     ecx, 50h ; 'P'; unsigned __int64
0x18008a73b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18008a740  mov     r12, rax
0x18008a743  mov     [rbp+560h+pszPath], rax
0x18008a747  test    rax, rax
0x18008a74a  jz      loc_18008AA38
0x18008a750  xor     ecx, ecx
0x18008a752  mov     [rax+20h], rcx
0x18008a756  lea     rax, ??_7CFreeThreadedItemContainer@@6BIFreeThreadedItemContainer@@@; const CFreeThreadedItemContainer::`vftable'{for `IFreeThreadedItemContainer'}
0x18008a75d  mov     [r12], rax
0x18008a761  lea     rax, ??_7CFreeThreadedItemContainer@@6BIInitializeWithItem@@@; const CFreeThreadedItemContainer::`vftable'{for `IInitializeWithItem'}
0x18008a768  mov     [r12+8], rax
0x18008a76d  lea     rax, ??_7CFreeThreadedItemContainer@@6BIPersistIDList@@@; const CFreeThreadedItemContainer::`vftable'{for `IPersistIDList'}
0x18008a774  mov     [r12+10h], rax
0x18008a779  lea     rax, ??_7CFreeThreadedItemContainer@@6BCFreeThreadedObject@@@; const CFreeThreadedItemContainer::`vftable'{for `CFreeThreadedObject'}
0x18008a780  mov     [r12+18h], rax
0x18008a785  mov     dword ptr [r12+28h], 1
0x18008a78e  mov     [r12+40h], rcx
0x18008a793  mov     [r12+30h], rcx
0x18008a798  mov     [r12+38h], rcx
0x18008a79d  mov     [r12+48h], rcx
0x18008a7a2  mov     r8d, 10h; Size
0x18008a7a8  lea     rdx, IID_IMarshal; Buf2
0x18008a7af  lea     rcx, _GUID_0c904b4a_164a_4d81_92d9_a5fc866f7fb8; Buf1
0x18008a7b6  call    memcmp_0
0x18008a7bb  lea     r9, [rbp+560h+lpszPathName]; void **
0x18008a7bf  lea     r8, _GUID_0c904b4a_164a_4d81_92d9_a5fc866f7fb8; struct _GUID *
0x18008a7c6  test    eax, eax
0x18008a7c8  jnz     loc_18008AAAE
0x18008a7ce  mov     rdx, r12; struct IUnknown *
0x18008a7d1  lea     rcx, [r12+18h]; this
0x18008a7d6  call    ?GetFreeThreadedMarshaler@CFreeThreadedObject@@QEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CFreeThreadedObject::GetFreeThreadedMarshaler(IUnknown *,_GUID const &,void * *)
0x18008a7db  mov     ebx, eax
0x18008a7dd  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18008a7e4  mov     eax, r12d
0x18008a7e7  mov     rcx, [rbp+560h+pszPath]; this
0x18008a7eb  lock xadd [rcx+28h], eax
  ... truncated ...
```
