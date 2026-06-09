# CRegFolder::_GetTargetFileSystemItem(IDLREGITEM const *,IShellItem2 * *)

- ea: `0x18008fb60`
- end: `0x180090720`
- name: `?_GetTargetFileSystemItem@CRegFolder@@AEAAJPEFBUIDLREGITEM@@PEAPEAUIShellItem2@@@Z`
- size: `3008`
- prototype: `int(CRegFolder *__hidden this, const struct IDLREGITEM *, struct IShellItem2 **)`
- caller_count: `5`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18008f380`
- `0x180090730`
- `0x180090ed0`
- `0x180091620`
- `0x18016ac90`

## callees

- `0x18000b1a0`
- `0x18003e0a0`
- `0x180067680`
- `0x1800688f0`
- `0x18008e7a0`
- `0x18008ec90`
- `0x18008fb60`
- `0x180091620`
- `0x180092970`
- `0x1800acb60`
- `0x1800b7dc0`
- `0x1800b7ec0`
- `0x1800d2b80`
- `0x1800d3170`
- `0x1800d3220`
- `0x1800dd900`
- `0x18028ec20`
- `0x1802952c8`
- `0x18034591c`
- `0x1803b1f60`
- `0x1803b1f84`
- `0x1803b243c`
- `0x1803b2ac0`
- `0x1803b69b9`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800900af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180090618`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800900af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180090618`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180090659`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180090659`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008ffab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008ffab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180090638`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180090638`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008fe6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800901f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800903ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800904f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008fe6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800901f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800903ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800904f0`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1800901cb`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1800901cb`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180090163`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180090163`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18009033d`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18009033d`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x18008fd7c`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x18009052d`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x18008fd7c`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x18009052d`

## string_xrefs

- `0x18008ff1e`: `BlockRegItemParsing`
- `0x18009025b`: `ParseAndCreateItem`
- `0x18009045c`: `ParseAndCreateItem`
- `0x1800905a4`: `ParseAndCreateItem`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CRegFolder::_GetTargetFileSystemItem(
        struct IShellItem2 *this,
        const struct IDLREGITEM *a2,
        struct IShellItem2 **a3)
{
  int v6; // r14d
  HRESULT BindCtx; // esi
  unsigned __int16 v8; // cx
  const struct IDLREGITEM *v9; // rax
  const struct IDLREGITEM *v10; // rbx
  unsigned __int16 v11; // dx
  unsigned __int16 *v12; // rdi
  __int64 v13; // r8
  unsigned int v14; // ecx
  unsigned __int64 v15; // rcx
  unsigned __int16 *v16; // rbx
  char *v17; // rbx
  LPBC v18; // rdi
  CDummyUnknown *v19; // rax
  LPBC v20; // rcx
  unsigned __int16 *v21; // r8
  unsigned __int16 *v23; // rdx
  CDummyUnknown *v24; // rbx
  CCLSIDInfoCache *v25; // rcx
  unsigned __int64 v26; // rax
  __int64 v27; // rdx
  const struct IDLREGITEM *v28; // rax
  struct _GUID *v29; // rax
  struct _GUID v30; // xmm6
  CCLSIDInfoCache *v31; // rcx
  HDSA v32; // rdi
  int v33; // esi
  int v34; // r14d
  int v35; // eax
  int v36; // ebx
  const struct CLSID_CACHE_ENTRY *v37; // rdx
  int v38; // eax
  const struct CLSID_CACHE_ENTRY *v39; // rdx
  int v40; // eax
  __int64 v41; // rax
  LPCWSTR v42; // rcx
  LPBC v43; // rdi
  const WCHAR *v44; // rsi
  int v45; // ebx
  LPBC v46; // rbx
  WCHAR *v47; // r12
  __int64 v48; // r14
  void *v49; // rdi
  void *v50; // rdi
  CDummyUnknown *v51; // rax
  CDummyUnknown *v52; // rbx
  struct IBindCtx *v53; // r15
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // rbx
  __int64 v57; // r12
  IShellFolder *v58; // r14
  HRESULT (__stdcall *ParseDisplayName)(IShellFolder *, HWND, IBindCtx *, LPWSTR, ULONG *, LPITEMIDLIST *, ULONG *); // rsi
  LPCWSTR v60; // rdi
  HWND UIWindow; // rax
  void *v62; // rcx
  int v63; // esi
  CDummyUnknown *v64; // rax
  CDummyUnknown *v65; // r14
  CCLSIDInfoCache *v66; // rcx
  CCLSIDInfoCache *v67; // rcx
  int v68; // eax
  CCLSIDInfoCache *v69; // rcx
  int v70; // r10d
  unsigned int *v71; // [rsp+28h] [rbp-D8h]
  LPCITEMIDLIST pidl; // [rsp+40h] [rbp-C0h] BYREF
  void *ppv; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR value; // [rsp+50h] [rbp-B0h] BYREF
  IShellFolder *ppshf; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v76; // [rsp+60h] [rbp-A0h] BYREF
  LPBC ppbc; // [rsp+68h] [rbp-98h] BYREF
  struct _GUID Buf1; // [rsp+70h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID pitem; // [rsp+88h] [rbp-78h] BYREF
  __int128 v81; // [rsp+98h] [rbp-68h]
  __int64 v82; // [rsp+A8h] [rbp-58h]
  int v83; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v84; // [rsp+B4h] [rbp-4Ch]
  __int64 v85; // [rsp+BCh] [rbp-44h]
  __int64 v86; // [rsp+C4h] [rbp-3Ch]
  char v87[564]; // [rsp+CCh] [rbp-34h] BYREF
  _OWORD v88[3]; // [rsp+300h] [rbp+200h] BYREF

  v6 = 0;
  *a3 = 0;
  BindCtx = -2147023728;
  if ( a2 )
  {
    v8 = *(_WORD *)a2;
    if ( *(_WORD *)a2 )
    {
      v9 = a2;
      do
      {
        v10 = v9;
        v9 = (const struct IDLREGITEM *)((char *)v9 + v8);
        v8 = *(_WORD *)v9;
      }
      while ( *(_WORD *)v9 );
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl'::`2'::impl) )
      {
        if ( !v10 )
          return (unsigned int)BindCtx;
        v11 = *(_WORD *)v10;
        if ( *(_WORD *)v10 < 2u )
          return (unsigned int)BindCtx;
      }
      else
      {
        v11 = *(_WORD *)v10;
      }
      v12 = 0;
      v13 = *(unsigned __int16 *)((char *)v10 + v11 - 2);
      if ( (_WORD)v13 )
      {
        if ( v13 + 8 < (unsigned __int64)v11 )
        {
          v12 = (unsigned __int16 *)((char *)v10 + v13);
          v14 = *(unsigned __int16 *)((char *)v10 + v13);
          if ( v14 < 8 || HIWORD(*((_DWORD *)v12 + 1)) != 0xBEEF || (unsigned int)v13 + v14 > v11 )
            v12 = 0;
        }
      }
      v15 = (unsigned __int64)v10 + *(unsigned __int16 *)v10;
      if ( v12 )
      {
        while ( 1 )
        {
          v16 = v12 + 4;
          if ( *((_DWORD *)v12 + 1) == -1091633114 )
            break;
          v21 = 0;
          if ( (unsigned __int64)v16 <= v15 )
          {
            v23 = (unsigned __int16 *)((char *)v12 + *v12);
            if ( v23 == (unsigned __int16 *)v15 )
              return (unsigned int)BindCtx;
            if ( (unsigned __int64)v23 <= v15 )
            {
              if ( (unsigned __int64)(v23 + 4) > v15
                || HIWORD(*((_DWORD *)v23 + 1)) != 0xBEEF
                || (unsigned __int64)v23 + *v23 > v15
                || v23 < v16 )
              {
                return (unsigned int)BindCtx;
              }
              v21 = (unsigned __int16 *)((char *)v12 + *v12);
            }
          }
          v12 = v21;
          if ( !v21 )
            return (unsigned int)BindCtx;
        }
        v85 = 0;
        memset_0(v87, 0, sizeof(v87));
        v83 = *(_DWORD *)v16;
        v84 = *(_QWORD *)(v12 + 6);
        v86 = *(_QWORD *)(v12 + 10);
        if ( v12[1] )
          v85 = *(_QWORD *)(v12 + 14);
        pv = 0;
        if ( (int)CRegFolder::_GetDisplayName(this, a2, 0x8000u, (unsigned __int16 **)&pv) < 0 )
          goto LABEL_29;
        ppbc = 0;
        pidl = 0;
        BindCtx = -2147024882;
        v17 = (char *)operator new(0x278u, (const struct std::nothrow_t *)&std::nothrow);
        *(_QWORD *)&Buf1.Data1 = v17;
        if ( !v17 )
          goto LABEL_27;
        *(_QWORD *)v17 = &CFileSysBindData::`vftable';
        *((_DWORD *)v17 + 2) = 1;
        memset_0(v17 + 40, 0, 0x250u);
        *((_QWORD *)v17 + 2) = 0;
        *(_OWORD *)(v17 + 24) = xmmword_180727030;
        BindCtx = (**(__int64 (__fastcall ***)(void *, GUID *, LPCITEMIDLIST *))v17)(
                    v17,
                    &GUID_01e18d10_4d8b_11d2_855d_006008059367,
                    &pidl);
        (*(void (__fastcall **)(char *))(*(_QWORD *)v17 + 16LL))(v17);
        if ( BindCtx < 0 )
          goto LABEL_27;
        (*(void (__fastcall **)(LPCITEMIDLIST, int *))(*(_QWORD *)&pidl->mkid.cb + 24LL))(pidl, &v83);
        ppbc = 0;
        BindCtx = CreateBindCtx(0, &ppbc);
        if ( BindCtx >= 0 )
        {
          *(_QWORD *)&Buf1.Data1 = 16;
          *(_QWORD *)Buf1.Data4 = 4096;
          BindCtx = ((__int64 (__fastcall *)(LPBC, struct _GUID *))ppbc->lpVtbl->SetBindOptions)(ppbc, &Buf1);
          if ( BindCtx < 0 )
            SafeRelease<IFilterCreationCallback>(&ppbc);
        }
        if ( BindCtx >= 0 )
        {
          v88[0] = *(_OWORD *)L"File System Bind Data";
          v88[1] = *(_OWORD *)L"tem Bind Data";
          *(_OWORD *)((char *)&v88[1] + 12) = *(_OWORD *)L"nd Data";
          ((void (__fastcall *)(LPBC, _OWORD *, LPCITEMIDLIST))ppbc->lpVtbl->RegisterObjectParam)(ppbc, v88, pidl);
        }
        (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)&pidl->mkid.cb + 16LL))(pidl);
        if ( BindCtx < 0 )
        {
LABEL_27:
          v20 = ppbc;
          if ( ppbc )
          {
            ppbc = 0;
            ((void (__fastcall *)(LPBC))v20->lpVtbl->Release)(v20);
          }
LABEL_29:
          if ( pv )
            CoTaskMemFree(pv);
          return (unsigned int)BindCtx;
        }
        v18 = ppbc;
        v19 = (CDummyUnknown *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
        *(_QWORD *)&Buf1.Data1 = v19;
        if ( !v19 || (v24 = CDummyUnknown::CDummyUnknown(v19)) == 0 )
        {
          BindCtx = -2147024882;
          goto LABEL_27;
        }
        BindCtx = ((__int64 (__fastcall *)(LPBC, const wchar_t *, CDummyUnknown *))v18->lpVtbl->RegisterObjectParam)(
                    v18,
                    L"BlockRegItemParsing",
                    v24);
        CDummyUnknown::Release(v24);
        if ( BindCtx < 0 )
          goto LABEL_27;
        v26 = *(unsigned __int16 *)a2;
        if ( (unsigned int)v26 > 7
          && (v27 = *((unsigned __int16 *)a2 + 2), v25 = (CCLSIDInfoCache *)(v27 + 38), v26 >= v27 + 38)
          && (Buf1 = *(struct _GUID *)((char *)a2 + v27 + 6), !memcmp_0(&Buf1, qword_1807187A0, 0x10u)) )
        {
          v29 = (struct _GUID *)((char *)a2 + *((unsigned __int16 *)a2 + 2) + 22);
        }
        else
        {
          v28 = *((_BYTE *)a2 + 2) == LOBYTE(this[45].lpVtbl)
              ? a2
              : (const struct IDLREGITEM *)((char *)a2 + HIDWORD(this[44].lpVtbl));
          v29 = (struct _GUID *)((char *)v28 + 4);
        }
        v30 = *v29;
        Buf1 = *v29;
        pitem = 0;
        v81 = 0;
        v82 = 0;
        if ( (unsigned int)CCLSIDInfoCache::_EnsureCacheIsValid(v25, 0) )
        {
          AcquireSRWLockShared(&g_clsidInfoCache);
          memset(&v88[1], 0, 24);
          v88[0] = v30;
          v32 = hdsa;
          if ( hdsa )
            v6 = *(_DWORD *)hdsa;
          v33 = 0;
          v34 = v6 - 1;
          while ( v33 <= v34 )
          {
            v35 = (v34 + v33) / 2;
            v36 = v35;
            v37 = 0;
            if ( v32 && v35 >= 0 && v35 < *(_DWORD *)v32 )
              v37 = (const struct CLSID_CACHE_ENTRY *)(*((_QWORD *)v32 + 1) + (unsigned int)(*((_DWORD *)v32 + 5) * v35));
            v38 = CCLSIDInfoCache::s_CompareEntries((const struct CLSID_CACHE_ENTRY *)v88, v37, 0);
            if ( v38 < 0 )
            {
              v34 = v36 - 1;
            }
            else
            {
              if ( v38 <= 0 )
              {
                for ( ; v36 > 0; --v36 )
                {
                  v39 = 0;
                  if ( v32 )
                  {
                    v40 = v36 - 1;
                    if ( v36 - 1 >= 0 && v40 < *(_DWORD *)v32 )
                      v39 = (const struct CLSID_CACHE_ENTRY *)(*((_QWORD *)v32 + 1)
                                                             + (unsigned int)(*((_DWORD *)v32 + 5) * v40));
                  }
                  if ( (unsigned int)CCLSIDInfoCache::s_CompareEntries((const struct CLSID_CACHE_ENTRY *)v88, v39, 0) )
                    break;
                }
                if ( v36 != -1 )
                {
                  v41 = 0;
                  if ( v32 && v36 >= 0 && v36 < *(_DWORD *)v32 )
                    v41 = *((_QWORD *)v32 + 1) + (unsigned int)(*((_DWORD *)v32 + 5) * v36);
                  pitem = *(struct _GUID *)v41;
                  v81 = *(_OWORD *)(v41 + 16);
                  v82 = *(_QWORD *)(v41 + 32);
                  ReleaseSRWLockShared(&g_clsidInfoCache);
                  goto LABEL_74;
                }
                break;
              }
              v33 = v36 + 1;
            }
          }
          ReleaseSRWLockShared(&g_clsidInfoCache);
          pitem = v30;
          CCLSIDInfoCache::_LoadValuesFromRegistry(v66, (struct CLSID_CACHE_ENTRY *)&pitem);
          AcquireSRWLockExclusive(&g_clsidInfoCache);
          if ( (unsigned int)CCLSIDInfoCache::_EnsureCacheIsValid(v67, 1) )
          {
            LODWORD(v71) = 3;
            v68 = CDSA_Base<CLSID_CACHE_ENTRY>::Search(&hdsa, &pitem);
            if ( !(unsigned int)CCLSIDInfoCache::_IsEntry(v69, &Buf1, v68) )
              DSA_InsertItem(hdsa, v70, &pitem);
          }
          ReleaseSRWLockExclusive(&g_clsidInfoCache);
        }
        else
        {
          pitem = v30;
          CCLSIDInfoCache::_LoadValuesFromRegistry(v31, (struct CLSID_CACHE_ENTRY *)&pitem);
        }
LABEL_74:
        if ( (v82 & 0x40000000000000LL) == 0 )
        {
          value = 0;
          if ( (int)CRegFolder::_GetDisplayName(this, a2, 0, (unsigned __int16 **)&value) >= 0 )
          {
            v43 = ppbc;
            if ( ppbc )
            {
              v44 = value;
              ppv = 0;
              pidl = 0;
              if ( ((int (__fastcall *)(LPBC, const unsigned __int16 *, LPCITEMIDLIST *))ppbc->lpVtbl->GetObjectParam)(
                     ppbc,
                     L"SHBindCtxPropertyBag",
                     &pidl) >= 0 )
              {
                v45 = (**(__int64 (__fastcall ***)(LPCITEMIDLIST, GUID *, void **))&pidl->mkid.cb)(
                        pidl,
                        &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
                        &ppv);
                (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)&pidl->mkid.cb + 16LL))(pidl);
                if ( v45 >= 0 )
                  goto LABEL_81;
              }
              if ( PSCreateMemoryPropertyStore(&GUID_55272a00_42cb_11ce_8135_00aa004bb851, &ppv) >= 0 )
              {
                v88[0] = *(_OWORD *)L"SHBindCtxPropertyBag";
                v88[1] = *(_OWORD *)L"xPropertyBag";
                *(_OWORD *)((char *)&v88[1] + 10) = *(_OWORD *)L"ertyBag";
                if ( ((int (__fastcall *)(LPBC, _OWORD *, void *))v43->lpVtbl->RegisterObjectParam)(v43, v88, ppv) >= 0 )
                {
LABEL_81:
                  PSPropertyBag_WriteStr((IPropertyBag *)ppv, L"LocalizedResourceName", v44);
                  (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
                }
              }
            }
          }
          v42 = value;
          if ( value )
            CoTaskMemFree((LPVOID)value);
        }
        v46 = ppbc;
        v47 = (WCHAR *)pv;
        *a3 = 0;
        v76 = 0;
        BindCtx = CTRefBase<CParseAndCreateItem,IParseAndCreateItem,CTRefBase_DllModuleLifetimePolicy>::CreateInstance(
                    v42,
                    &v76);
        if ( BindCtx < 0 )
          goto LABEL_27;
        v48 = v76;
        ppv = v46;
        if ( v46 )
        {
          ((void (__fastcall *)(LPBC))v46->lpVtbl->AddRef)(v46);
        }
        else
        {
          BindCtx = CreateBindCtx(0, (LPBC *)&ppv);
          if ( BindCtx < 0 )
            goto LABEL_115;
        }
        v49 = ppv;
        if ( v48 )
        {
          BindCtx = (*(__int64 (__fastcall **)(void *, const wchar_t *, __int64))(*(_QWORD *)ppv + 72LL))(
                      ppv,
                      L"ParseAndCreateItem",
                      v48);
        }
        else
        {
          v64 = (CDummyUnknown *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
          *(_QWORD *)&Buf1.Data1 = v64;
          if ( !v64 || (v65 = CDummyUnknown::CDummyUnknown(v64)) == 0 )
          {
            BindCtx = -2147024882;
            goto LABEL_129;
          }
          BindCtx = (*(__int64 (__fastcall **)(void *, const wchar_t *, CDummyUnknown *))(*(_QWORD *)v49 + 72LL))(
                      v49,
                      L"ParseAndCreateItem",
                      v65);
          if ( (int)--*((_DWORD *)v65 + 6) <= 0 )
            operator delete(v65, (const struct std::nothrow_t *)0x40);
        }
        if ( BindCtx >= 0 )
        {
          if ( !v46 )
          {
            v50 = ppv;
            v51 = (CDummyUnknown *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
            *(_QWORD *)&Buf1.Data1 = v51;
            if ( v51 && (v52 = CDummyUnknown::CDummyUnknown(v51)) != 0 )
            {
              BindCtx = (*(__int64 (__fastcall **)(void *, const wchar_t *, CDummyUnknown *))(*(_QWORD *)v50 + 72LL))(
                          v50,
                          L"Parse Translate Aliases",
                          v52);
              if ( (int)--*((_DWORD *)v52 + 6) <= 0 )
                operator delete(v52, (const struct std::nothrow_t *)0x40);
            }
            else
            {
              BindCtx = -2147024882;
            }
            if ( BindCtx < 0 )
              goto LABEL_114;
          }
          pidl = 0;
          v53 = (struct IBindCtx *)ppv;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloBrokerShellObjects>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_AppSiloBrokerShellObjects>::GetImpl'::`2'::impl);
          if ( (int)Windows::Security::Isolation::TryBrokerSHParseDisplayName(
                      (Windows::Security::Isolation *)v47,
                      (const unsigned __int16 *)v53,
                      (struct IBindCtx *)&pidl,
                      0,
                      0,
                      v71) < 0 )
          {
            pidl = 0;
            value = 0;
            BindCtx = SHStrDupW(v47, (LPWSTR *)&value);
            if ( BindCtx >= 0 )
            {
              ppshf = 0;
              BindCtx = SHGetDesktopFolder(&ppshf);
              if ( BindCtx >= 0 )
              {
                v56 = 0;
                *(_QWORD *)&Buf1.Data1 = 0;
                v57 = 0;
                if ( v53
                  || (BindCtx = BindCtx_CreateWithObjectParam_0(v55, v54, &Buf1),
                      v56 = *(_QWORD *)&Buf1.Data1,
                      v53 = *(struct IBindCtx **)&Buf1.Data1,
                      v57 = *(_QWORD *)&Buf1.Data1,
                      BindCtx >= 0) )
                {
                  v58 = ppshf;
                  ParseDisplayName = ppshf->lpVtbl->ParseDisplayName;
                  v60 = value;
                  UIWindow = BindCtx_GetUIWindow(v53);
                  BindCtx = ((__int64 (__fastcall *)(IShellFolder *, HWND, struct IBindCtx *, LPCWSTR, _QWORD, LPCITEMIDLIST *, _QWORD))ParseDisplayName)(
                              v58,
                              UIWindow,
                              v53,
                              v60,
                              0,
                              &pidl,
                              0);
                }
                if ( v57 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
              }
              CoTaskMemFree((LPVOID)value);
              if ( ppshf )
                ((void (__fastcall *)(IShellFolder *))ppshf->lpVtbl->Release)(ppshf);
            }
            if ( BindCtx < 0 )
              goto LABEL_114;
          }
          v62 = ppv;
          *a3 = 0;
          value = 0;
          BindCtx = -2147467262;
          ppshf = 0;
          if ( v62
            && (*(int (__fastcall **)(void *, const wchar_t *, IShellFolder **))(*(_QWORD *)v62 + 80LL))(
                 v62,
                 L"ParseAndCreateItem",
                 &ppshf) >= 0 )
          {
            v63 = ((__int64 (__fastcall *)(IShellFolder *, GUID *, LPCWSTR *))ppshf->lpVtbl->QueryInterface)(
                    ppshf,
                    &GUID_67efed0e_e827_4408_b493_78f3982b685c,
                    &value);
            ((void (__fastcall *)(IShellFolder *))ppshf->lpVtbl->Release)(ppshf);
            if ( v63 < 0 )
              goto LABEL_112;
            BindCtx = (*(__int64 (__fastcall **)(LPCWSTR, GUID *, struct IShellItem2 **))(*(_QWORD *)value + 32LL))(
                        value,
                        &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
                        a3);
            (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)value + 16LL))(value);
          }
          if ( BindCtx >= 0 )
          {
LABEL_113:
            CoTaskMemFree((LPVOID)pidl);
LABEL_114:
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
LABEL_115:
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
            goto LABEL_27;
          }
LABEL_112:
          BindCtx = SHCreateItemFromIDList(pidl, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, (void **)a3);
          goto LABEL_113;
        }
LABEL_129:
        SafeRelease<IFilterCreationCallback>(&ppv);
        goto LABEL_115;
      }
    }
  }
  return (unsigned int)BindCtx;
}

```

## disassembly

```asm
0x18008fb60  mov     [rsp-8+arg_18], rbx
0x18008fb65  push    rbp
0x18008fb66  push    rsi
0x18008fb67  push    rdi
0x18008fb68  push    r12
0x18008fb6a  push    r13
0x18008fb6c  push    r14
0x18008fb6e  push    r15
0x18008fb70  lea     rbp, [rsp-250h]
0x18008fb78  sub     rsp, 350h
0x18008fb7f  movaps  [rsp+380h+var_40], xmm6
0x18008fb87  mov     rax, cs:__security_cookie
0x18008fb8e  xor     rax, rsp
0x18008fb91  mov     [rbp+280h+var_50], rax
0x18008fb98  mov     r13, r8
0x18008fb9b  mov     r15, rdx
0x18008fb9e  mov     r12, rcx
0x18008fba1  xor     r14d, r14d
0x18008fba4  mov     [r8], r14
0x18008fba7  mov     esi, 80070490h
0x18008fbac  test    rdx, rdx
0x18008fbaf  jz      loc_18008FEB1
0x18008fbb5  movzx   ecx, word ptr [rdx]
0x18008fbb8  test    cx, cx
0x18008fbbb  jz      loc_18008FEB1
0x18008fbc1  mov     rax, rdx
0x18008fbc4  nop     dword ptr [rax+00h]
0x18008fbc8  nop     dword ptr [rax+rax+00000000h]
0x18008fbd0  mov     rbx, rax
0x18008fbd3  movzx   ecx, cx
0x18008fbd6  add     rax, rcx
0x18008fbd9  movzx   ecx, word ptr [rax]
0x18008fbdc  test    cx, cx
0x18008fbdf  jnz     short loc_18008FBD0
0x18008fbe1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow> `wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl(void)'::`2'::impl
0x18008fbe8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(void)
0x18008fbed  test    al, al
0x18008fbef  jnz     loc_1800906D4
0x18008fbf5  movzx   edx, word ptr [rbx]
0x18008fbf8  mov     rdi, r14
0x18008fbfb  movzx   ecx, dx
0x18008fbfe  movzx   r8d, word ptr [rbx+rcx-2]
0x18008fc04  mov     r10d, 0BEEFh
0x18008fc0a  test    r8w, r8w
0x18008fc0e  jz      short loc_18008FC48
0x18008fc10  lea     rax, [r8+8]
0x18008fc14  cmp     rax, rcx
0x18008fc17  jnb     short loc_18008FC48
0x18008fc19  lea     rdi, [rbx+r8]
0x18008fc1d  movzx   ecx, word ptr [rdi]
0x18008fc20  cmp     ecx, 8
0x18008fc23  jb      loc_18009054D
0x18008fc29  mov     eax, [rdi+4]
0x18008fc2c  shr     rax, 10h
0x18008fc30  cmp     ax, r10w
0x18008fc34  jnz     loc_18009054D
0x18008fc3a  add     ecx, r8d
0x18008fc3d  movzx   eax, dx
0x18008fc40  cmp     ecx, eax
0x18008fc42  ja      loc_18009054D
0x18008fc48  movzx   ecx, word ptr [rbx]
0x18008fc4b  add     rcx, rbx
0x18008fc4e  test    rdi, rdi
0x18008fc51  jz      loc_18008FEB1
0x18008fc57  lea     rbx, [rdi+8]
0x18008fc5b  cmp     dword ptr [rdi+4], 0BEEF0026h
0x18008fc62  jnz     loc_18008FEE6
0x18008fc68  xor     eax, eax
0x18008fc6a  mov     [rbp+280h+var_2C4], rax
0x18008fc6e  xor     edx, edx; Val
0x18008fc70  mov     r8d, 234h; Size
0x18008fc76  lea     rcx, [rbp+280h+var_2B4]; void *
0x18008fc7a  call    memset_0
0x18008fc7f  mov     eax, [rbx]
0x18008fc81  mov     [rbp+280h+var_2D0], eax
0x18008fc84  mov     rax, [rdi+0Ch]
0x18008fc88  mov     [rbp+280h+var_2CC], rax
0x18008fc8c  mov     rax, [rdi+14h]
0x18008fc90  mov     [rbp+280h+var_2BC], rax
0x18008fc94  cmp     word ptr [rdi+2], 1
0x18008fc99  jb      short loc_18008FCA3
0x18008fc9b  mov     rax, [rdi+1Ch]
0x18008fc9f  mov     [rbp+280h+var_2C4], rax
0x18008fca3  mov     [rbp+280h+pv], r14
0x18008fca7  lea     r9, [rbp+280h+pv]; unsigned __int16 **
0x18008fcab  mov     r8d, 8000h; unsigned int
0x18008fcb1  mov     rdx, r15; struct IDLREGITEM *
0x18008fcb4  mov     rcx, r12; this
0x18008fcb7  call    ?_GetDisplayName@CRegFolder@@AEAAJPEFBUIDLREGITEM@@KPEAPEAG@Z; CRegFolder::_GetDisplayName(IDLREGITEM const *,ulong,ushort * *)
0x18008fcbc  test    eax, eax
0x18008fcbe  js      loc_18008FE65
0x18008fcc4  mov     [rsp+380h+ppbc], r14
0x18008fcc9  mov     [rsp+380h+pidl], r14
0x18008fcce  mov     esi, 8007000Eh
0x18008fcd3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008fcda  mov     ecx, 278h; unsigned __int64
0x18008fcdf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18008fce4  mov     rbx, rax
0x18008fce7  mov     qword ptr [rsp+380h+Buf1], rax
0x18008fcec  test    rax, rax
0x18008fcef  jz      loc_18008FE49
0x18008fcf5  lea     rax, ??_7CFileSysBindData@@6B@; const CFileSysBindData::`vftable'
0x18008fcfc  mov     [rbx], rax
0x18008fcff  mov     dword ptr [rbx+8], 1
0x18008fd06  lea     rcx, [rbx+28h]; void *
0x18008fd0a  xor     edx, edx; Val
0x18008fd0c  mov     r8d, 250h; Size
0x18008fd12  call    memset_0
0x18008fd17  xor     eax, eax
0x18008fd19  mov     [rbx+10h], rax
0x18008fd1d  movups  xmm0, cs:xmmword_180727030
0x18008fd24  movups  xmmword ptr [rbx+18h], xmm0
0x18008fd28  mov     rax, [rbx]
0x18008fd2b  lea     r8, [rsp+380h+pidl]
0x18008fd30  lea     rdx, _GUID_01e18d10_4d8b_11d2_855d_006008059367
0x18008fd37  mov     rcx, rbx
0x18008fd3a  mov     rax, [rax]
0x18008fd3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fd42  mov     esi, eax
0x18008fd44  mov     rax, [rbx]
0x18008fd47  mov     rcx, rbx
0x18008fd4a  mov     rax, [rax+10h]
0x18008fd4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fd53  test    esi, esi
0x18008fd55  js      loc_18008FE49
0x18008fd5b  mov     rcx, [rsp+380h+pidl]
0x18008fd60  mov     rax, [rcx]
0x18008fd63  lea     rdx, [rbp+280h+var_2D0]
0x18008fd67  mov     rax, [rax+18h]
0x18008fd6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fd70  mov     [rsp+380h+ppbc], r14
0x18008fd75  lea     rdx, [rsp+380h+ppbc]; ppbc
0x18008fd7a  xor     ecx, ecx; reserved
0x18008fd7c  call    cs:__imp_CreateBindCtx
0x18008fd83  nop     dword ptr [rax+rax+00h]
0x18008fd88  mov     esi, eax
0x18008fd8a  test    eax, eax
0x18008fd8c  js      short loc_18008FDC0
0x18008fd8e  mov     qword ptr [rsp+380h+Buf1], 10h
0x18008fd97  mov     qword ptr [rsp+380h+Buf1+8], 1000h
0x18008fda0  mov     rcx, [rsp+380h+ppbc]
0x18008fda5  mov     rax, [rcx]
0x18008fda8  lea     rdx, [rsp+380h+Buf1]
0x18008fdad  mov     rax, [rax+30h]
0x18008fdb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fdb6  mov     esi, eax
0x18008fdb8  test    eax, eax
0x18008fdba  js      loc_1800906FE
0x18008fdc0  test    esi, esi
0x18008fdc2  js      short loc_18008FE0B
0x18008fdc4  movups  xmm0, xmmword ptr cs:aFileSystemBind; "File System Bind Data"
0x18008fdcb  movups  [rbp+280h+var_80], xmm0
0x18008fdd2  movups  xmm1, xmmword ptr cs:aFileSystemBind+10h; "tem Bind Data"
0x18008fdd9  movups  [rbp+280h+var_70], xmm1
0x18008fde0  movups  xmm0, xmmword ptr cs:aFileSystemBind+1Ch; "nd Data"
0x18008fde7  movups  [rbp+280h+var_70+0Ch], xmm0
0x18008fdee  mov     rcx, [rsp+380h+ppbc]
0x18008fdf3  mov     rax, [rcx]
0x18008fdf6  mov     r8, [rsp+380h+pidl]
0x18008fdfb  lea     rdx, [rbp+280h+var_80]
0x18008fe02  mov     rax, [rax+48h]
0x18008fe06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fe0b  mov     rcx, [rsp+380h+pidl]
0x18008fe10  mov     rax, [rcx]
0x18008fe13  mov     rax, [rax+10h]
0x18008fe17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fe1c  test    esi, esi
0x18008fe1e  js      short loc_18008FE49
0x18008fe20  mov     rdi, [rsp+380h+ppbc]
0x18008fe25  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008fe2c  mov     ecx, 40h ; '@'; unsigned __int64
0x18008fe31  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18008fe36  mov     qword ptr [rsp+380h+Buf1], rax
0x18008fe3b  test    rax, rax
0x18008fe3e  jnz     loc_18008FF00
0x18008fe44  mov     esi, 8007000Eh
0x18008fe49  mov     rcx, [rsp+380h+ppbc]
0x18008fe4e  test    rcx, rcx
0x18008fe51  jz      short loc_18008FE65
0x18008fe53  mov     [rsp+380h+ppbc], r14
0x18008fe58  mov     rax, [rcx]
0x18008fe5b  mov     rax, [rax+10h]
0x18008fe5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fe64  nop
0x18008fe65  mov     rcx, [rbp+280h+pv]; pv
0x18008fe69  test    rcx, rcx
0x18008fe6c  jz      short loc_18008FEB1
0x18008fe6e  call    cs:__imp_CoTaskMemFree
0x18008fe75  nop     dword ptr [rax+rax+00h]
0x18008fe7a  jmp     short loc_18008FEB1
0x18008fe7c  lea     rax, [rdx+8]
0x18008fe80  cmp     rax, rcx
0x18008fe83  ja      short loc_18008FEB1
0x18008fe85  mov     eax, [rdx+4]
0x18008fe88  shr     rax, 10h
0x18008fe8c  cmp     ax, r10w
0x18008fe90  jnz     short loc_18008FEB1
0x18008fe92  movzx   eax, word ptr [rdx]
0x18008fe95  add     rax, rdx
0x18008fe98  cmp     rax, rcx
0x18008fe9b  ja      short loc_18008FEB1
0x18008fe9d  cmp     rdx, rbx
0x18008fea0  jb      short loc_18008FEB1
0x18008fea2  mov     r8, rdx
0x18008fea5  mov     rdi, r8
0x18008fea8  test    r8, r8
0x18008feab  jnz     loc_18008FC57
0x18008feb1  mov     eax, esi
0x18008feb3  mov     rcx, [rbp+280h+var_50]
0x18008feba  xor     rcx, rsp; StackCookie
0x18008febd  call    __security_check_cookie
0x18008fec2  mov     rbx, [rsp+380h+arg_18]
0x18008feca  movaps  xmm6, [rsp+380h+var_40]
0x18008fed2  add     rsp, 350h
0x18008fed9  pop     r15
0x18008fedb  pop     r14
0x18008fedd  pop     r13
0x18008fedf  pop     r12
0x18008fee1  pop     rdi
0x18008fee2  pop     rsi
0x18008fee3  pop     rbp
0x18008fee4  retn
0x18008fee6  mov     r8, r14
0x18008fee9  cmp     rbx, rcx
0x18008feec  ja      short loc_18008FEA5
0x18008feee  movzx   edx, word ptr [rdi]
0x18008fef1  add     rdx, rdi
0x18008fef4  cmp     rdx, rcx
0x18008fef7  jz      short loc_18008FEB1
0x18008fef9  ja      short loc_18008FEA5
0x18008fefb  jmp     loc_18008FE7C
0x18008ff00  mov     rcx, rax; this
0x18008ff03  call    ??0CDummyUnknown@@QEAA@XZ; CDummyUnknown::CDummyUnknown(void)
0x18008ff08  mov     rbx, rax
0x18008ff0b  test    rax, rax
0x18008ff0e  jz      loc_18008FE44
0x18008ff14  mov     rcx, [rdi]
0x18008ff17  mov     rax, [rcx+48h]
0x18008ff1b  mov     r8, rbx
0x18008ff1e  lea     rdx, aBlockregitempa; "BlockRegItemParsing"
0x18008ff25  mov     rcx, rdi
0x18008ff28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ff2d  mov     esi, eax
0x18008ff2f  mov     rcx, rbx; this
0x18008ff32  call    ?Release@CDummyUnknown@@UEAAKXZ; CDummyUnknown::Release(void)
0x18008ff37  test    esi, esi
0x18008ff39  js      loc_18008FE49
0x18008ff3f  movzx   eax, word ptr [r15]
0x18008ff43  cmp     eax, 7
0x18008ff46  jbe     short loc_18008FF5A
0x18008ff48  movzx   edx, word ptr [r15+4]
0x18008ff4d  lea     rcx, [rdx+26h]; this
0x18008ff51  cmp     rax, rcx
0x18008ff54  jnb     loc_1800905D6
0x18008ff5a  movzx   eax, byte ptr [r12+168h]
0x18008ff63  cmp     [r15+2], al
0x18008ff67  jz      loc_1800906CC
0x18008ff6d  mov     eax, [r12+164h]
0x18008ff75  add     rax, r15
0x18008ff78  add     rax, 4
0x18008ff7c  movups  xmm6, xmmword ptr [rax]
0x18008ff7f  movups  [rsp+380h+Buf1], xmm6
0x18008ff84  xorps   xmm0, xmm0
0x18008ff87  xor     eax, eax
0x18008ff89  movups  [rbp+280h+pitem], xmm0
0x18008ff8d  movups  [rbp+280h+var_2E8], xmm0
0x18008ff91  mov     [rbp+280h+var_2D8], rax
0x18008ff95  xor     edx, edx; int
0x18008ff97  call    ?_EnsureCacheIsValid@CCLSIDInfoCache@@AEAAHH@Z; CCLSIDInfoCache::_EnsureCacheIsValid(int)
0x18008ff9c  test    eax, eax
0x18008ff9e  jz      loc_18009070D
0x18008ffa4  lea     rcx, ?g_clsidInfoCache@@3VCCLSIDInfoCache@@A; SRWLock
0x18008ffab  call    cs:__imp_AcquireSRWLockShared
0x18008ffb2  nop     dword ptr [rax+rax+00h]
0x18008ffb7  xorps   xmm0, xmm0
0x18008ffba  movdqu  [rbp+280h+var_70], xmm0
0x18008ffc2  mov     [rbp+280h+var_60], r14
0x18008ffc9  movups  [rbp+280h+var_80], xmm6
0x18008ffd0  mov     rdi, cs:hdsa
0x18008ffd7  test    rdi, rdi
0x18008ffda  jz      short loc_18008FFDF
0x18008ffdc  mov     r14d, [rdi]
0x18008ffdf  xor     esi, esi
0x18008ffe1  dec     r14d
0x18008ffe4  cmp     esi, r14d
0x18008ffe7  jg      loc_180090611
0x18008ffed  lea     eax, [r14+rsi]
0x18008fff1  cdq
0x18008fff2  sub     eax, edx
0x18008fff4  sar     eax, 1
0x18008fff6  mov     ebx, eax
0x18008fff8  xor     edx, edx
0x18008fffa  test    rdi, rdi
0x18008fffd  jz      short loc_180090011
0x18008ffff  test    eax, eax
0x180090001  js      short loc_180090011
0x180090003  cmp     eax, [rdi]
0x180090005  jge     short loc_180090011
0x180090007  mov     edx, eax
0x180090009  imul    edx, [rdi+14h]
  ... truncated ...
```
