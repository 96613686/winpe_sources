# CRegFolder::_ParseItemName(ushort const *,HWND__ *,IBindCtx *,_ITEMIDLIST_RELATIVE * *,ulong *)

- ea: `0x180063a50`
- end: `0x1800644e6`
- name: `?_ParseItemName@CRegFolder@@AEAAJPEBGPEAUHWND__@@PEAUIBindCtx@@PEAPEAU_ITEMIDLIST_RELATIVE@@PEAK@Z`
- size: `2710`
- prototype: `__int64 __usercall@<rax>(CRegFolder *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, HWND@<r8>, struct IBindCtx *@<r9>, struct _ITEMIDLIST_RELATIVE **, unsigned int *)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800644f0`

## callees

- `0x18005dc40`
- `0x18005fa70`
- `0x180062710`
- `0x1800627fc`
- `0x180063050`
- `0x180063a50`
- `0x18006b770`
- `0x18006b970`
- `0x18008d7c0`
- `0x180090ed0`
- `0x180091620`
- `0x180092a70`
- `0x1800b5630`
- `0x1800b5d60`
- `0x1800b5de0`
- `0x180116e60`
- `0x1801c0d64`
- `0x1801ee6c0`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x1803b2ea5`
- `0x1803b69b9`
- `0x1803b69c5`
- `0x1803e187c`
- `0x1804e9878`
- `0x1805426c8`
- `0x180542c60`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063e0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063f28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063e0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063f28`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063df2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006434d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063df2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006434d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180063fa6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180063fa6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180063e28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180063ffc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180063e28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180063ffc`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180063e4c`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180063e4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063eb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800640b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006417e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800642c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180064305`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063eb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800640b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006417e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800642c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180064305`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800640fc`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800640fc`
- `SHCORE!__imp_GUIDFromStringW` at `0x180063aef`
- `SHCORE!__imp_GUIDFromStringW` at `0x180063aef`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x180063c60`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x180063c60`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x180063c25`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x180063c25`

## string_xrefs

- `0x180063b18`: `BlockRegItemParsing`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRegFolder::_ParseItemName(
        CRegFolder *this,
        const unsigned __int16 *a2,
        HWND a3,
        struct IBindCtx *a4,
        struct _ITEMIDLIST_RELATIVE **a5,
        unsigned int *a6)
{
  struct IBindCtx *v6; // r12
  CRegFolder *v8; // r15
  const WCHAR *v9; // rdi
  const unsigned __int16 *v10; // rbx
  unsigned __int16 v11; // ax
  unsigned int v12; // esi
  IMalloc *v13; // rax
  LPMALLOC v14; // rdi
  int v15; // eax
  char v16; // si
  unsigned int v17; // r9d
  SIZE_T v18; // rsi
  CRegFolder *v19; // rcx
  __int64 result; // rax
  unsigned __int64 lpVtbl_low; // rax
  __int64 v22; // rdx
  unsigned __int64 v23; // rax
  __int64 v24; // r8
  LPMALLOC v25; // rax
  __int128 *v26; // rax
  int v27; // edx
  _QWORD *v28; // r8
  __int64 v29; // rax
  void *v30; // rbx
  size_t v31; // r14
  int v32; // esi
  unsigned __int16 *v33; // rdx
  __int64 v34; // rcx
  int v35; // r14d
  unsigned __int16 **v36; // rax
  unsigned __int16 *v37; // rdx
  unsigned int v38; // r14d
  __int64 v39; // rcx
  ITEMIDLIST *v40; // rax
  ITEMIDLIST *v41; // r15
  size_t v42; // rax
  const struct _ITEMIDLIST_RELATIVE *ID; // r12
  const struct _ITEMIDLIST_RELATIVE *v44; // rax
  unsigned __int16 v45; // r8
  unsigned __int16 *v46; // rdx
  unsigned __int16 v47; // cx
  unsigned __int16 v48; // cx
  const struct _GUID *PIDLRCLSID; // rax
  __int64 v50; // rcx
  __int64 v51; // rax
  int v52; // eax
  int v53; // ebx
  char *v54; // r14
  int v55; // eax
  __int64 v56; // rdx
  __int128 Buf2; // [rsp+40h] [rbp-C0h] BYREF
  struct _ITEMIDLIST_ABSOLUTE **v58; // [rsp+50h] [rbp-B0h]
  _BYTE v59[36]; // [rsp+58h] [rbp-A8h] BYREF
  HWND v60; // [rsp+80h] [rbp-80h]
  unsigned int *v61; // [rsp+88h] [rbp-78h]
  LPMALLOC ppMalloc; // [rsp+90h] [rbp-70h] BYREF
  HKEY hkey; // [rsp+98h] [rbp-68h] BYREF
  HKEY phkResult; // [rsp+A0h] [rbp-60h] BYREF
  DWORD v65[2]; // [rsp+A8h] [rbp-58h] BYREF
  DWORD pcbData[2]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int pvData; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v68; // [rsp+BCh] [rbp-44h] BYREF
  struct _GUID v69; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD FileInformation[2]; // [rsp+D0h] [rbp-30h] BYREF
  int v71; // [rsp+F0h] [rbp-10h]
  WCHAR SubKey[264]; // [rsp+100h] [rbp+0h] BYREF

  v6 = a4;
  phkResult = (HKEY)a4;
  v60 = a3;
  v8 = this;
  *(_QWORD *)&Buf2 = this;
  v58 = a5;
  v61 = a6;
  v9 = 0;
  v10 = a2 + 2;
  v11 = a2[2];
  if ( v11 )
  {
    do
    {
      if ( v11 == 92 )
        break;
      if ( v11 == 44 && !v9 )
        v9 = v10 + 1;
      v11 = *++v10;
    }
    while ( *v10 );
  }
  v69 = GUID_NULL;
  if ( !(unsigned int)GUIDFromStringW(a2 + 2) )
    return 2147746291LL;
  ppMalloc = 0;
  if ( v6
    && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, LPMALLOC *))v6->lpVtbl->GetObjectParam)(
         v6,
         L"BlockRegItemParsing",
         &ppMalloc) >= 0 )
  {
    ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
    return 2147942450LL;
  }
  if ( !v9 )
  {
    ppMalloc = 0;
    v12 = *((_DWORD *)v8 + 89) + 22;
    v13 = (IMalloc *)WINRT_IMPL_CoTaskMemAlloc(v12);
    v14 = v13;
    if ( !v13 )
      return 2147942414LL;
    memset_0(v13, 0, v12);
    LOWORD(v14->lpVtbl) = *((_WORD *)v8 + 178) + 20;
    BYTE2(v14->lpVtbl) = *((_BYTE *)v8 + 328);
    *(struct _GUID *)((char *)&v14->lpVtbl + *((unsigned int *)v8 + 89) + 4) = v69;
    memset_0((char *)&v14->lpVtbl + 4, 0, *((unsigned int *)v8 + 89));
    ppMalloc = v14;
    v15 = CRegFolder::_ReqItemIndex(v8, (const struct IDLREGITEM *)v14);
    if ( v15 == -1 )
    {
      v16 = 0x80;
      hkey = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hkey,
        0);
      if ( CRegFolder::_OpenItemKey(v8, (const struct IDLREGITEM *)ppMalloc, 0, &hkey) >= 0 )
      {
        pvData = 0;
        pcbData[0] = 4;
        v65[0] = 4;
        if ( !SHQueryValueExW(hkey, L"SortOrderIndex", 0, 0, &pvData, pcbData)
          || !SHGetValueW(hkey, L"ShellFolder", L"SortOrderIndex", 0, &pvData, v65) )
        {
          if ( (unsigned int)IsAppCompatModeEnabled(4) && pvData <= 0x50 )
          {
            pvData = 81;
          }
          else if ( pvData - 66 <= 1 )
          {
            pvData = 71;
          }
          PIDLRCLSID = CRegFolder::_GetPIDLRCLSID(v8, (const struct IDLREGITEM *)ppMalloc);
          v50 = *(_QWORD *)&PIDLRCLSID->Data1 - *(_QWORD *)&CLSID_OneDriveRegItem.Data1;
          if ( *(_QWORD *)&PIDLRCLSID->Data1 == *(_QWORD *)&CLSID_OneDriveRegItem.Data1 )
            v50 = *(_QWORD *)PIDLRCLSID->Data4 - *(_QWORD *)CLSID_OneDriveRegItem.Data4;
          if ( !v50 )
            pvData = 67;
          v51 = _lambda_b461f0d585b4e5be4448ff82c363a670_::_lambda_b461f0d585b4e5be4448ff82c363a670_(
                  v59,
                  v8,
                  &ppMalloc,
                  &pvData);
          lambda_765ffb8db86ed4afb5abae4e5fbaf899_::operator()(v51);
          v16 = pvData;
        }
      }
      if ( hkey )
        RegCloseKey(hkey);
    }
    else
    {
      v16 = *(_BYTE *)(*((_QWORD *)v8 + 43) + 48LL * v15 + 28);
    }
    BYTE3(v14->lpVtbl) = v16;
    v68 = 0;
    CRegFolder::_AttributesOf(v8, (const struct IDLREGITEM *)v14, 0x60000000u, &v68);
    v18 = 2;
    if ( (v68 & 0x60000000) == 0x60000000 )
    {
      v35 = 0;
      ppMalloc = 0;
      v36 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&ppMalloc);
      if ( (int)CRegFolder::_GetDisplayName((struct IShellItem2 *)v8, (const struct IDLREGITEM *)v14, 0x8000u, v36) >= 0 )
      {
        memset(&v59[12], 0, 24);
        *(_QWORD *)v59 = 0xBEEF002600010024uLL;
        *(_DWORD *)&v59[8] = 16;
        memset(FileInformation, 0, sizeof(FileInformation));
        v71 = 0;
        if ( GetFileAttributesExW((LPCWSTR)ppMalloc, GetFileExInfoStandard, FileInformation) )
        {
          *(_DWORD *)&v59[8] = FileInformation[0];
          *(_QWORD *)&v59[12] = *(_QWORD *)((char *)FileInformation + 4);
          *(_QWORD *)&v59[20] = *(_QWORD *)((char *)&FileInformation[1] + 4);
          *(_QWORD *)&v59[28] = *(_QWORD *)((char *)FileInformation + 12);
        }
        if ( LOWORD(v14->lpVtbl) )
        {
          v37 = (unsigned __int16 *)v14;
          v38 = 2;
          do
          {
            v39 = *v37;
            if ( !(_WORD)v39 )
              break;
            v38 += v39;
            v37 = (unsigned __int16 *)((char *)v37 + v39);
          }
          while ( v37 );
          v40 = (ITEMIDLIST *)CoTaskMemAlloc(v38 + 38);
          v41 = v40;
          if ( v40 )
          {
            v42 = SHGetSize(v40);
            memset_0(v41, 0, v42);
            memcpy_0(v41, v14, v38);
            ID = (const struct _ITEMIDLIST_RELATIVE *)ILFindLastID(v41);
            if ( ILFindFirstHiddenID(ID) )
              v44 = (const struct _ITEMIDLIST_RELATIVE *)((char *)ID + *(unsigned __int16 *)ID - 2);
            else
              v44 = ID;
            v45 = *(_WORD *)v44;
            v46 = (unsigned __int16 *)((char *)v41 + v38 - 2);
            *(_OWORD *)v46 = *(_OWORD *)v59;
            *((_OWORD *)v46 + 1) = *(_OWORD *)&v59[16];
            *((_DWORD *)v46 + 8) = *(_DWORD *)&v59[32];
            v47 = *v46 + 2;
            if ( v47 < *v46 || (*v46 = v47, v48 = *(_WORD *)ID + v47, v48 < *(_WORD *)ID) )
            {
              CoTaskMemFree(v41);
              v41 = 0;
            }
            else
            {
              *(_WORD *)ID = v48;
              *(unsigned __int16 *)((char *)v46 + *v46 - 2) = v45;
            }
            v6 = (struct IBindCtx *)phkResult;
          }
          CoTaskMemFree(v14);
        }
        else
        {
          v41 = (ITEMIDLIST *)v14;
        }
        v14 = (LPMALLOC)v41;
        v35 = -2147024882;
        if ( v41 )
          v35 = 0;
        v8 = (CRegFolder *)Buf2;
      }
      if ( ppMalloc )
        CoTaskMemFree(ppMalloc);
      if ( v35 < 0 )
        return (unsigned int)v35;
    }
    ppMalloc = v14;
    phkResult = 0;
    if ( v6
      && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, HKEY *))v6->lpVtbl->GetObjectParam)(
           v6,
           L"HomeGroup Capabilities",
           &phkResult) >= 0 )
    {
      (*(void (__fastcall **)(HKEY))(*(_QWORD *)phkResult + 16LL))(phkResult);
      result = CRegFolder::_AppendCapabilities(v19, (struct IDLREGITEM **)&ppMalloc, v6);
      if ( (int)result < 0 )
        return result;
      v14 = ppMalloc;
    }
    if ( !v14 )
      goto LABEL_26;
    lpVtbl_low = LOWORD(v14->lpVtbl);
    if ( (unsigned int)lpVtbl_low > 7 )
    {
      v22 = WORD2(v14->lpVtbl);
      if ( lpVtbl_low >= v22 + 38 )
      {
        Buf2 = *(_OWORD *)((char *)&v14->lpVtbl + v22 + 6);
        if ( !memcmp_0(&Buf2, qword_1807187A0, 0x10u) )
          goto LABEL_106;
      }
    }
    v23 = LOWORD(v14->lpVtbl);
    if ( (unsigned int)v23 > 7
      && (v24 = WORD2(v14->lpVtbl), v23 >= v24 + 38)
      && (v54 = (char *)v14 + v24,
          Buf2 = *(_OWORD *)((char *)&v14->lpVtbl + v24 + 6),
          !memcmp_0(&Buf2, qword_1807187A0, 0x10u)) )
    {
      v26 = (__int128 *)(v54 + 22);
    }
    else
    {
LABEL_26:
      if ( BYTE2(v14->lpVtbl) == *((_BYTE *)v8 + 360) )
        v25 = v14;
      else
        v25 = (LPMALLOC)((char *)v14 + *((unsigned int *)v8 + 89));
      v26 = (__int128 *)((char *)&v25->lpVtbl + 4);
    }
    Buf2 = *v26;
    v27 = *((_DWORD *)v8 + 84) - 1;
    if ( v27 >= 0 )
    {
      v17 = DWORD2(Buf2);
      do
      {
        v28 = *(_QWORD **)(*((_QWORD *)v8 + 43) + 48LL * v27);
        v29 = Buf2 - *v28;
        if ( (_QWORD)Buf2 == *v28 )
          v29 = *((_QWORD *)&Buf2 + 1) - v28[1];
        if ( !v29 )
          goto LABEL_47;
      }
      while ( --v27 >= 0 );
    }
    CRegFolder::_GetNameSpaceKey(v8, (const struct IDLREGITEM *)v14, SubKey, v17);
    phkResult = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &phkResult)
      || (phkResult = 0, !RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 1u, &phkResult)) )
    {
      RegCloseKey(phkResult);
      goto LABEL_47;
    }
    Buf2 = (__int128)*CRegFolder::_GetPIDLRCLSID(v8, (const struct IDLREGITEM *)v14);
    if ( !memcmp_0(&CLSID_ControlPanel, &Buf2, 0x10u)
      || !memcmp_0(&CLSID_Printers, &Buf2, 0x10u)
      || !memcmp_0(&CLSID_NetworkConnections, &Buf2, 0x10u)
      || !memcmp_0(&CLSID_ScheduledTasks, &Buf2, 0x10u) )
    {
LABEL_47:
      if ( *v10 )
      {
        v65[0] = 0;
        hkey = 0;
        v32 = CRegFolder::_BindToItem(
                v8,
                (const struct IDLREGITEM *)v14,
                v6,
                0,
                &GUID_000214e6_0000_0000_c000_000000000046,
                (void **)&hkey);
        if ( v32 >= 0 )
        {
          ppMalloc = 0;
          v32 = (*(__int64 (__fastcall **)(HKEY, HWND, struct IBindCtx *, const unsigned __int16 *, DWORD *, LPMALLOC *, unsigned int *))(*(_QWORD *)hkey + 24LL))(
                  hkey,
                  v60,
                  v6,
                  v10 + 1,
                  v65,
                  &ppMalloc,
                  v61);
          if ( v32 >= 0 )
          {
            v32 = SHILCombine(
                    (const struct _ITEMIDLIST_ABSOLUTE *)v14,
                    (const struct _ITEMIDLIST_RELATIVE *)ppMalloc,
                    v58);
            CoTaskMemFree(ppMalloc);
          }
          (*(void (__fastcall **)(HKEY))(*(_QWORD *)hkey + 16LL))(hkey);
        }
      }
      else
      {
        if ( v61 && *v61 )
          CRegFolder::_AttributesOf(v8, (const struct IDLREGITEM *)v14, *v61, v61);
        if ( v14 )
        {
          v33 = (unsigned __int16 *)v14;
          do
          {
            v34 = *v33;
            if ( !(_WORD)v34 )
              break;
            v18 = (unsigned int)(v34 + v18);
            v33 = (unsigned __int16 *)((char *)v33 + v34);
          }
          while ( v33 );
          v30 = CoTaskMemAlloc(v18);
          if ( v30 )
          {
            v31 = 0;
            ppMalloc = 0;
            if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
            {
              v31 = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v30);
              ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
            }
            memset_0(v30, 0, v31);
            memcpy_0(v30, v14, v18);
          }
          v32 = 0;
          if ( !v30 )
            v32 = -2147024882;
        }
        else
        {
          v32 = -2147024809;
          v30 = 0;
        }
        *v58 = (struct _ITEMIDLIST_ABSOLUTE *)v30;
      }
      goto LABEL_45;
    }
LABEL_106:
    if ( *((_DWORD *)v8 + 209)
      || (unsigned int)BindCtx_ContainsObject(v6, L"ValidateRegItems")
      || (BindCtx_GetMode(v6, 0) & 0x1000) == 0 )
    {
      v32 = -2147024809;
LABEL_45:
      CoTaskMemFree(v14);
      return (unsigned int)v32;
    }
    goto LABEL_47;
  }
  *(_QWORD *)v65 = 0;
  result = CRegFolder::_CreateCachedDelegateFolder(v8, &v69, (struct IShellFolder **)v65, 0);
  if ( (int)result >= 0 )
  {
    if ( (unsigned int)BindCtx_ContainsObject(v6, L"DelegateNamedProperties") )
    {
      v52 = (*(__int64 (__fastcall **)(_QWORD, HWND, struct IBindCtx *, const WCHAR *, _QWORD, struct _ITEMIDLIST_RELATIVE **, unsigned int *))(**(_QWORD **)v65 + 24LL))(
              *(_QWORD *)v65,
              a3,
              v6,
              v9,
              0,
              a5,
              a6);
    }
    else
    {
      *(_QWORD *)pcbData = 0;
      v55 = SHGetPropertyStoreFromPropertyParsingName(v9, &GUID_55272a00_42cb_11ce_8135_00aa004bb851, (void **)pcbData);
      v53 = v55;
      if ( v55 >= 0 )
      {
        hkey = 0;
        v53 = BindCtx_RegisterObjectParam_6(v6, v56, *(_QWORD *)pcbData, &hkey);
        if ( v53 >= 0 )
        {
          v53 = (*(__int64 (__fastcall **)(_QWORD, HWND, HKEY, const WCHAR *, _QWORD, struct _ITEMIDLIST_RELATIVE **, unsigned int *))(**(_QWORD **)v65 + 24LL))(
                  *(_QWORD *)v65,
                  a3,
                  hkey,
                  v9,
                  0,
                  a5,
                  a6);
          (*(void (__fastcall **)(HKEY))(*(_QWORD *)hkey + 16LL))(hkey);
        }
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pcbData + 16LL))(*(_QWORD *)pcbData);
        goto LABEL_89;
      }
      if ( v55 != -2147024809 )
      {
LABEL_89:
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v65 + 16LL))(*(_QWORD *)v65);
        return (unsigned int)v53;
      }
      v52 = (*(__int64 (__fastcall **)(_QWORD, HWND, struct IBindCtx *, const WCHAR *, _QWORD, struct _ITEMIDLIST_RELATIVE **, unsigned int *))(**(_QWORD **)v65 + 24LL))(
              *(_QWORD *)v65,
              v60,
              v6,
              v9,
              0,
              a5,
              a6);
    }
    v53 = v52;
    goto LABEL_89;
  }
  return result;
}

```

## disassembly

```asm
0x180063a50  push    rbp
0x180063a52  push    rbx
0x180063a53  push    rsi
0x180063a54  push    rdi
0x180063a55  push    r12
0x180063a57  push    r13
0x180063a59  push    r14
0x180063a5b  push    r15
0x180063a5d  lea     rbp, [rsp-228h]
0x180063a65  sub     rsp, 328h
0x180063a6c  mov     rax, cs:__security_cookie
0x180063a73  xor     rax, rsp
0x180063a76  mov     [rbp+260h+var_50], rax
0x180063a7d  mov     r12, r9
0x180063a80  mov     [rbp+260h+phkResult], r9
0x180063a84  mov     rsi, r8
0x180063a87  mov     [rbp+260h+var_2E0], r8
0x180063a8b  mov     r8, rdx
0x180063a8e  mov     r15, rcx
0x180063a91  mov     qword ptr [rsp+360h+Buf2], rcx
0x180063a96  mov     r13, [rbp+260h+arg_20]
0x180063a9d  mov     [rsp+360h+var_310], r13
0x180063aa2  mov     r14, [rbp+260h+arg_28]
0x180063aa9  mov     [rbp+260h+var_2D8], r14
0x180063aad  xor     edi, edi
0x180063aaf  lea     rbx, [rdx+4]
0x180063ab3  movzx   eax, word ptr [rdx+4]
0x180063ab7  test    ax, ax
0x180063aba  jz      short loc_180063ADC
0x180063abc  nop     dword ptr [rax+00h]
0x180063ac0  cmp     ax, 5Ch ; '\'
0x180063ac4  jz      short loc_180063ADC
0x180063ac6  cmp     ax, 2Ch ; ','
0x180063aca  jz      loc_180064319
0x180063ad0  add     rbx, 2
0x180063ad4  movzx   eax, word ptr [rbx]
0x180063ad7  test    ax, ax
0x180063ada  jnz     short loc_180063AC0
0x180063adc  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180063ae3  movups  xmmword ptr [rbp+260h+var_2A0.Data1], xmm0
0x180063ae7  lea     rdx, [rbp+260h+var_2A0]
0x180063aeb  lea     rcx, [r8+4]
0x180063aef  call    cs:__imp_GUIDFromStringW
0x180063af6  nop     dword ptr [rax+rax+00h]
0x180063afb  test    eax, eax
0x180063afd  jz      loc_180063E1B
0x180063b03  mov     [rbp+260h+ppMalloc], 0
0x180063b0b  test    r12, r12
0x180063b0e  jz      short loc_180063B33
0x180063b10  mov     rax, [r12]
0x180063b14  lea     r8, [rbp+260h+ppMalloc]
0x180063b18  lea     rdx, aBlockregitempa; "BlockRegItemParsing"
0x180063b1f  mov     rcx, r12
0x180063b22  mov     rax, [rax+50h]
0x180063b26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063b2b  test    eax, eax
0x180063b2d  jns     loc_180064433
0x180063b33  test    rdi, rdi
0x180063b36  jnz     loc_18006418F
0x180063b3c  xor     r14d, r14d
0x180063b3f  mov     [rbp+260h+ppMalloc], r14
0x180063b43  mov     eax, [r15+164h]
0x180063b4a  add     eax, 16h
0x180063b4d  mov     esi, eax
0x180063b4f  mov     ecx, eax; cb
0x180063b51  call    WINRT_IMPL_CoTaskMemAlloc
0x180063b56  mov     rdi, rax
0x180063b59  test    rax, rax
0x180063b5c  jz      loc_180064174
0x180063b62  mov     r8d, esi; Size
0x180063b65  xor     edx, edx; Val
0x180063b67  mov     rcx, rax; void *
0x180063b6a  call    memset_0
0x180063b6f  movzx   eax, word ptr [r15+164h]
0x180063b77  add     ax, 14h
0x180063b7b  mov     [rdi], ax
0x180063b7e  movzx   eax, byte ptr [r15+148h]
0x180063b86  mov     [rdi+2], al
0x180063b89  mov     eax, [r15+164h]
0x180063b90  movups  xmm0, xmmword ptr [rbp+260h+var_2A0.Data1]
0x180063b94  movups  xmmword ptr [rax+rdi+4], xmm0
0x180063b99  mov     r8d, [r15+164h]; Size
0x180063ba0  lea     rcx, [rdi+4]; void *
0x180063ba4  xor     edx, edx; Val
0x180063ba6  call    memset_0
0x180063bab  mov     [rbp+260h+ppMalloc], rdi
0x180063baf  mov     rdx, rdi; struct IDLREGITEM *
0x180063bb2  mov     rcx, r15; this
0x180063bb5  call    ?_ReqItemIndex@CRegFolder@@AEAAHPEFBUIDLREGITEM@@@Z; CRegFolder::_ReqItemIndex(IDLREGITEM const *)
0x180063bba  cmp     eax, 0FFFFFFFFh
0x180063bbd  jnz     loc_1800642E8
0x180063bc3  mov     sil, 80h
0x180063bc6  mov     [rbp+260h+hkey], r14
0x180063bca  xor     edx, edx
0x180063bcc  lea     rcx, [rbp+260h+hkey]
0x180063bd0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180063bd5  lea     r9, [rbp+260h+hkey]; HKEY *
0x180063bd9  xor     r8d, r8d; bool *
0x180063bdc  mov     rdx, [rbp+260h+ppMalloc]; struct IDLREGITEM *
0x180063be0  mov     rcx, r15; this
0x180063be3  call    ?_OpenItemKey@CRegFolder@@AEAAJPEFBUIDLREGITEM@@PEA_NPEAPEAUHKEY__@@@Z; CRegFolder::_OpenItemKey(IDLREGITEM const *,bool *,HKEY__ * *)
0x180063be8  test    eax, eax
0x180063bea  js      loc_180063C74
0x180063bf0  mov     [rbp+260h+var_2A8], r14d
0x180063bf4  mov     [rbp+260h+var_2B0], 4
0x180063bfb  mov     [rbp+260h+var_2B8], 4
0x180063c02  lea     rax, [rbp+260h+var_2B0]
0x180063c06  mov     [rsp+360h+pcbData], rax; pcbData
0x180063c0b  lea     rax, [rbp+260h+var_2A8]
0x180063c0f  mov     [rsp+360h+pvData], rax; pvData
0x180063c14  xor     r9d, r9d; pdwType
0x180063c17  xor     r8d, r8d; pdwReserved
0x180063c1a  lea     rdx, aSortorderindex; "SortOrderIndex"
0x180063c21  mov     rcx, [rbp+260h+hkey]; hkey
0x180063c25  call    cs:__imp_SHQueryValueExW
0x180063c2c  nop     dword ptr [rax+rax+00h]
0x180063c31  test    eax, eax
0x180063c33  jz      loc_1800640F7
0x180063c39  lea     rax, [rbp+260h+var_2B8]
0x180063c3d  mov     [rsp+360h+pcbData], rax; pcbData
0x180063c42  lea     rax, [rbp+260h+var_2A8]
0x180063c46  mov     [rsp+360h+pvData], rax; pvData
0x180063c4b  xor     r9d, r9d; pdwType
0x180063c4e  lea     r8, aSortorderindex; "SortOrderIndex"
0x180063c55  lea     rdx, pszSubKey; "ShellFolder"
0x180063c5c  mov     rcx, [rbp+260h+hkey]; hkey
0x180063c60  call    cs:__imp_SHGetValueW
0x180063c67  nop     dword ptr [rax+rax+00h]
0x180063c6c  test    eax, eax
0x180063c6e  jz      loc_1800640F7
0x180063c74  mov     rcx, [rbp+260h+hkey]; hKey
0x180063c78  test    rcx, rcx
0x180063c7b  jnz     loc_180063F28
0x180063c81  mov     [rdi+3], sil
0x180063c85  mov     [rbp+260h+var_2A4], r14d
0x180063c89  lea     r9, [rbp+260h+var_2A4]; unsigned int *
0x180063c8d  mov     r8d, 60000000h; unsigned int
0x180063c93  mov     rdx, rdi; struct IDLREGITEM *
0x180063c96  mov     rcx, r15; this
0x180063c99  call    ?_AttributesOf@CRegFolder@@AEAAJPEFBUIDLREGITEM@@KPEAK@Z; CRegFolder::_AttributesOf(IDLREGITEM const *,ulong,ulong *)
0x180063c9e  mov     eax, [rbp+260h+var_2A4]
0x180063ca1  and     eax, 60000000h
0x180063ca6  mov     esi, 2
0x180063cab  mov     r13d, 8007000Eh
0x180063cb1  cmp     eax, 60000000h
0x180063cb6  jz      loc_180063F39
0x180063cbc  mov     [rbp+260h+ppMalloc], rdi
0x180063cc0  mov     [rbp+260h+phkResult], 0
0x180063cc8  test    r12, r12
0x180063ccb  jz      short loc_180063D14
0x180063ccd  mov     rax, [r12]
0x180063cd1  lea     r8, [rbp+260h+phkResult]
0x180063cd5  lea     rdx, aHomegroupCapab; "HomeGroup Capabilities"
0x180063cdc  mov     rcx, r12
0x180063cdf  mov     rax, [rax+50h]
0x180063ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063ce8  test    eax, eax
0x180063cea  js      short loc_180063D14
0x180063cec  mov     rcx, [rbp+260h+phkResult]
0x180063cf0  mov     rax, [rcx]
0x180063cf3  mov     rax, [rax+10h]
0x180063cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063cfc  mov     r8, r12; struct IBindCtx *
0x180063cff  lea     rdx, [rbp+260h+ppMalloc]; struct IDLREGITEM **
0x180063d03  call    ?_AppendCapabilities@CRegFolder@@AEAAJPEAPEFAUIDLREGITEM@@PEAUIBindCtx@@@Z; CRegFolder::_AppendCapabilities(IDLREGITEM * *,IBindCtx *)
0x180063d08  test    eax, eax
0x180063d0a  js      loc_180063EBF
0x180063d10  mov     rdi, [rbp+260h+ppMalloc]
0x180063d14  test    rdi, rdi
0x180063d17  jz      short loc_180063D4C
0x180063d19  movzx   eax, word ptr [rdi]
0x180063d1c  cmp     eax, 7
0x180063d1f  jbe     short loc_180063D32
0x180063d21  movzx   edx, word ptr [rdi+4]
0x180063d25  lea     rcx, [rdx+26h]
0x180063d29  cmp     rax, rcx
0x180063d2c  jnb     loc_180064461
0x180063d32  movzx   eax, word ptr [rdi]
0x180063d35  cmp     eax, 7
0x180063d38  jbe     short loc_180063D4C
0x180063d3a  movzx   r8d, word ptr [rdi+4]
0x180063d3f  lea     rcx, [r8+26h]
0x180063d43  cmp     rax, rcx
0x180063d46  jnb     loc_18006448F
0x180063d4c  movzx   eax, byte ptr [r15+168h]
0x180063d54  cmp     [rdi+2], al
0x180063d57  jz      loc_18006444D
0x180063d5d  mov     eax, [r15+164h]
0x180063d64  add     rax, rdi
0x180063d67  add     rax, 4
0x180063d6b  movups  xmm0, xmmword ptr [rax]
0x180063d6e  movups  [rsp+360h+Buf2], xmm0
0x180063d73  mov     edx, [r15+150h]
0x180063d7a  sub     edx, 1
0x180063d7d  js      short loc_180063DBB
0x180063d7f  mov     r10, [r15+158h]
0x180063d86  mov     r9, qword ptr [rsp+360h+Buf2+8]; unsigned int
0x180063d8b  mov     r11, qword ptr [rsp+360h+Buf2]
0x180063d90  movsxd  rax, edx
0x180063d93  lea     rcx, [rax+rax*2]
0x180063d97  add     rcx, rcx
0x180063d9a  mov     r8, [r10+rcx*8]
0x180063d9e  mov     rax, r11
0x180063da1  sub     rax, [r8]
0x180063da4  jnz     short loc_180063DAD
0x180063da6  mov     rax, r9
0x180063da9  sub     rax, [r8+8]
0x180063dad  test    rax, rax
0x180063db0  jz      loc_180063EE3
0x180063db6  sub     edx, 1
0x180063db9  jns     short loc_180063D90
0x180063dbb  lea     r8, [rbp+260h+SubKey]; unsigned __int16 *
0x180063dbf  mov     rdx, rdi; struct IDLREGITEM *
0x180063dc2  mov     rcx, r15; this
0x180063dc5  call    ?_GetNameSpaceKey@CRegFolder@@AEAAXPEFBUIDLREGITEM@@PEAGI@Z; CRegFolder::_GetNameSpaceKey(IDLREGITEM const *,ushort *,uint)
0x180063dca  mov     [rbp+260h+phkResult], 0
0x180063dd2  lea     rax, [rbp+260h+phkResult]
0x180063dd6  mov     [rsp+360h+pvData], rax; phkResult
0x180063ddb  mov     r14d, 1
0x180063de1  mov     r9d, r14d; samDesired
0x180063de4  xor     r8d, r8d; ulOptions
0x180063de7  lea     rdx, [rbp+260h+SubKey]; lpSubKey
0x180063deb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180063df2  call    cs:__imp_RegOpenKeyExW
0x180063df9  nop     dword ptr [rax+rax+00h]
0x180063dfe  test    eax, eax
0x180063e00  jnz     loc_18006432B
0x180063e06  mov     rcx, [rbp+260h+phkResult]; hKey
0x180063e0a  call    cs:__imp_RegCloseKey
0x180063e11  nop     dword ptr [rax+rax+00h]
0x180063e16  jmp     loc_180063EEB
0x180063e1b  mov     eax, 800401F3h
0x180063e20  jmp     loc_180063EBF
0x180063e25  mov     rcx, rsi; cb
0x180063e28  call    cs:__imp_CoTaskMemAlloc
0x180063e2f  nop     dword ptr [rax+rax+00h]
0x180063e34  mov     rbx, rax
0x180063e37  test    rax, rax
0x180063e3a  jz      short loc_180063E9D
0x180063e3c  xor     r14d, r14d
0x180063e3f  mov     [rbp+260h+ppMalloc], r14
0x180063e43  lea     rdx, [rbp+260h+ppMalloc]; ppMalloc
0x180063e47  mov     ecx, 1; dwMemContext
0x180063e4c  call    cs:__imp_CoGetMalloc
0x180063e53  nop     dword ptr [rax+rax+00h]
0x180063e58  test    eax, eax
0x180063e5a  js      short loc_180063E82
0x180063e5c  mov     rcx, [rbp+260h+ppMalloc]
0x180063e60  mov     rdx, [rcx]
0x180063e63  mov     rax, [rdx+30h]
0x180063e67  mov     rdx, rbx
0x180063e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063e6f  mov     r14, rax
0x180063e72  mov     rcx, [rbp+260h+ppMalloc]
0x180063e76  mov     rdx, [rcx]
0x180063e79  mov     rax, [rdx+10h]
0x180063e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063e82  mov     r8, r14; Size
0x180063e85  xor     edx, edx; Val
0x180063e87  mov     rcx, rbx; void *
0x180063e8a  call    memset_0
0x180063e8f  mov     r8, rsi; Size
0x180063e92  mov     rdx, rdi; Src
0x180063e95  mov     rcx, rbx; void *
0x180063e98  call    memcpy_0
0x180063e9d  xor     esi, esi
0x180063e9f  test    rbx, rbx
0x180063ea2  cmovz   esi, r13d
0x180063ea6  mov     rax, [rsp+360h+var_310]
0x180063eab  mov     [rax], rbx
0x180063eae  mov     rcx, rdi; pv
0x180063eb1  call    cs:__imp_CoTaskMemFree
0x180063eb8  nop     dword ptr [rax+rax+00h]
0x180063ebd  mov     eax, esi
0x180063ebf  mov     rcx, [rbp+260h+var_50]
0x180063ec6  xor     rcx, rsp; StackCookie
0x180063ec9  call    __security_check_cookie
0x180063ece  add     rsp, 328h
0x180063ed5  pop     r15
0x180063ed7  pop     r14
0x180063ed9  pop     r13
0x180063edb  pop     r12
0x180063edd  pop     rdi
0x180063ede  pop     rsi
0x180063edf  pop     rbx
0x180063ee0  pop     rbp
0x180063ee1  retn
0x180063ee3  test    edx, edx
0x180063ee5  js      loc_180063DBB
0x180063eeb  cmp     word ptr [rbx], 0
0x180063eef  jnz     loc_180064235
0x180063ef5  mov     rdx, [rbp+260h+var_2D8]
0x180063ef9  test    rdx, rdx
0x180063efc  jnz     loc_18006420E
0x180063f02  test    rdi, rdi
0x180063f05  jz      loc_180064455
0x180063f0b  mov     rdx, rdi
0x180063f0e  xchg    ax, ax
0x180063f10  movzx   ecx, word ptr [rdx]
0x180063f13  test    cx, cx
  ... truncated ...
```
