# CFSFolder::Initialize(IBindCtx *,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_ABSOLUTE const *,CFSFolder &)

- ea: `0x1801820a0`
- end: `0x180182cd6`
- name: `?Initialize@CFSFolder@@UEAAJPEAUIBindCtx@@PEBU_ITEMIDLIST_ABSOLUTE@@PEFBU_ITEMIDLIST_RELATIVE@@1AEAV1@@Z`
- size: `3126`
- prototype: `__int64 __fastcall(CFSFolder *__hidden this, struct IBindCtx *, const struct _ITEMIDLIST_ABSOLUTE *, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_ABSOLUTE *Src, struct CFSFolder *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180038f50`
- `0x180096e60`
- `0x1800ff160`
- `0x1801820a0`
- `0x18034591c`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x1803b69b9`
- `0x1803b69c5`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801824ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801824ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018248d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018248d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180182a69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180182a69`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180182afb`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180182afb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801829af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801829af`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180182ae7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180182ae7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x180182281`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x180182281`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180182aba`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180182aba`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180182a91`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180182a91`
- `OLEAUT32!__imp_SysAllocString` at `0x180182259`
- `OLEAUT32!__imp_SysAllocString` at `0x180182259`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180182136`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180182136`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180182160`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180182160`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018245b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018249f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180182925`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180182c6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018245b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018249f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180182925`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180182c6c`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x1801828bd`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x1801828bd`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1801825a1`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1801825c1`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1801825e1`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180182601`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180182616`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1801825a1`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1801825c1`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1801825e1`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180182601`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180182616`

## string_xrefs

- `0x180182ab3`: `%SystemRoot%\System32\RuntimeBroker.exe`
- `0x18018253b`: `ItemCacheContext`
- `0x1801825b1`: `FSFolder_ConvertToSidString`
- `0x18018258d`: `FSFolder_ResolveSidToUserName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFSFolder::Initialize(
        CFSFolder *this,
        struct IBindCtx *a2,
        const struct _ITEMIDLIST_ABSOLUTE *a3,
        const struct _ITEMIDLIST_RELATIVE *a4,
        const struct _ITEMIDLIST_ABSOLUTE *Src,
        struct CFSFolder *a6)
{
  struct CFSFolder *v9; // r13
  int v10; // eax
  unsigned int v11; // edi
  const struct _ITEMIDLIST_ABSOLUTE *v12; // rdx
  unsigned int v13; // r8d
  __int64 v14; // rcx
  size_t v15; // r12
  void *v16; // rdi
  size_t v17; // r13
  int v18; // edi
  char *v19; // r14
  int v20; // edi
  BSTR v21; // rax
  const WCHAR *v22; // rcx
  __int64 (__fastcall *v23)(char *, const struct _ITEMIDLIST_RELATIVE *, char *); // r13
  void *v24; // r12
  unsigned __int16 v25; // ax
  const struct _ITEMIDLIST_RELATIVE *v26; // rdi
  const struct _ITEMIDLIST_RELATIVE *v27; // r15
  __int64 v28; // rcx
  const struct _ITEMIDLIST_RELATIVE *v29; // rbx
  char IsEnabled; // al
  unsigned __int16 v31; // r8
  unsigned __int16 *v32; // rdx
  __int64 v33; // r9
  unsigned int v34; // ecx
  unsigned __int64 v35; // rcx
  _BYTE *v36; // rcx
  unsigned __int64 v37; // rdx
  int v38; // ecx
  int v39; // r14d
  DWORD LastError; // edi
  _WORD *v42; // rax
  int v43; // edi
  int v44; // edi
  int v45; // edi
  int v46; // edi
  char v47; // di
  char v48; // di
  char v49; // di
  int v50; // edi
  int (__fastcall ***v51)(_QWORD, GUID *, _BYTE *); // rcx
  __int64 v52; // rdx
  unsigned __int16 *v53; // r9
  unsigned __int16 *v54; // r8
  __int16 v55; // r11
  HANDLE CurrentProcess; // rdi
  BOOL FullProcessImageNameW; // eax
  unsigned __int16 v58; // ax
  const struct _ITEMIDLIST_RELATIVE *v59; // rdi
  unsigned __int16 v60; // r9
  unsigned __int16 *v61; // rdx
  __int64 v62; // r8
  unsigned int v63; // ecx
  unsigned __int64 v64; // r8
  unsigned __int16 *v65; // rcx
  unsigned __int16 *v66; // r10
  unsigned __int16 *v67; // r9
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  _BYTE v69[12]; // [rsp+30h] [rbp-D0h] BYREF
  int v70; // [rsp+3Ch] [rbp-C4h]
  LPMALLOC ppMalloc[2]; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR *psz; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Dst[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ExeName[264]; // [rsp+270h] [rbp+170h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4D8h] [rbp+3D8h]

  v9 = a6;
  *(_QWORD *)v69 = a6;
  v10 = (*(__int64 (__fastcall **)(char *, const struct _ITEMIDLIST_ABSOLUTE *))(*((_QWORD *)this - 30) + 32LL))(
          (char *)this - 240,
          a3);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2542,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)(unsigned int)v10,
      bIgnoreCase);
    return v11;
  }
  if ( Src )
  {
    v12 = Src;
    v13 = 2;
    do
    {
      v14 = *(unsigned __int16 *)v12;
      if ( !(_WORD)v14 )
        break;
      v13 += v14;
      v12 = (const struct _ITEMIDLIST_ABSOLUTE *)((char *)v12 + v14);
    }
    while ( v12 );
    v15 = v13;
    v16 = CoTaskMemAlloc(v13);
    if ( !v16 )
    {
      *((_QWORD *)this + 16) = 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2547,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
        (const char *)0x8007000ELL,
        bIgnoreCase);
      return 2147942414LL;
    }
    v17 = 0;
    ppMalloc[0] = 0;
    if ( CoGetMalloc(1u, ppMalloc) >= 0 )
    {
      v17 = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc[0]->lpVtbl->GetSize)(ppMalloc[0], v16);
      ((void (__fastcall *)(LPMALLOC))ppMalloc[0]->lpVtbl->Release)(ppMalloc[0]);
    }
    memset_0(v16, 0, v17);
    memcpy_0(v16, Src, v15);
    *((_QWORD *)this + 16) = v16;
    v9 = *(struct CFSFolder **)v69;
  }
  v18 = 32;
  if ( a2
    && (*(_DWORD *)v69 = 16,
        *(_QWORD *)&v69[4] = 0,
        v70 = 0,
        ((int (__fastcall *)(struct IBindCtx *, _BYTE *))a2->lpVtbl->GetBindOptions)(a2, v69) >= 0)
    && (v18 = *(_DWORD *)&v69[8], (*(_DWORD *)&v69[8] & 0x10000) != 0)
    || (*((_DWORD *)this + 73) = v18, a2) )
  {
    ppMalloc[0] = 0;
    *(_QWORD *)v69 = 0;
    if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, _BYTE *))a2->lpVtbl->GetObjectParam)(
           a2,
           L"ItemCacheContext",
           v69) >= 0 )
    {
      v43 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, LPMALLOC *))v69)(
              *(_QWORD *)v69,
              &GUID_0000000e_0000_0000_c000_000000000046,
              ppMalloc);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v69 + 16LL))(*(_QWORD *)v69);
      if ( v43 >= 0 )
      {
        *((_QWORD *)this + 4) = L"FSFolder_ResolveSidToUserName";
        IUnknown_Set((IUnknown **)this + 2, (IUnknown *)ppMalloc[0]);
        *((_QWORD *)this + 7) = L"FSFolder_ConvertToSidString";
        IUnknown_Set((IUnknown **)this + 5, (IUnknown *)ppMalloc[0]);
        *((_QWORD *)this + 10) = L"FSFolder_InplaceShareEngine";
        IUnknown_Set((IUnknown **)this + 8, (IUnknown *)ppMalloc[0]);
        *((_QWORD *)this + 13) = L"FSFolder_SmbShareEngine";
        IUnknown_Set((IUnknown **)this + 11, (IUnknown *)ppMalloc[0]);
        IUnknown_Set((IUnknown **)this + 14, (IUnknown *)ppMalloc[0]);
        ((void (__fastcall *)(LPMALLOC))ppMalloc[0]->lpVtbl->Release)(ppMalloc[0]);
      }
    }
    v44 = 0;
    *(_QWORD *)v69 = 0;
    if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, _BYTE *))a2->lpVtbl->GetObjectParam)(
           a2,
           L"Avoid Drive Restriction Policy",
           v69) >= 0 )
    {
      v44 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v69 + 16LL))(*(_QWORD *)v69);
    }
    *((_DWORD *)this + 64) = v44;
    v45 = 0;
    *(_QWORD *)v69 = 0;
    if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, _BYTE *))a2->lpVtbl->GetObjectParam)(
           a2,
           L"Enable Extended DAV Features",
           v69) >= 0 )
    {
      v45 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v69 + 16LL))(*(_QWORD *)v69);
    }
    *((_DWORD *)this + 56) &= ~0x20u;
    *((_DWORD *)this + 56) |= 32 * v45;
    v46 = 0;
    *(_QWORD *)v69 = 0;
    if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, _BYTE *))a2->lpVtbl->GetObjectParam)(
           a2,
           L"AssumeWritable",
           v69) >= 0 )
    {
      v46 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v69 + 16LL))(*(_QWORD *)v69);
    }
    *((_DWORD *)this + 56) &= ~0x40u;
    *((_DWORD *)this + 56) |= v46 << 6;
    v47 = 0;
    *(_QWORD *)v69 = 0;
    if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, _BYTE *))a2->lpVtbl->GetObjectParam)(
           a2,
           L"Folder is in an aliased location",
           v69) >= 0 )
    {
      v47 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v69 + 16LL))(*(_QWORD *)v69);
    }
    *((_BYTE *)this + 228) = v47;
    v48 = 0;
    *(_QWORD *)v69 = 0;
    if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, _BYTE *))a2->lpVtbl->GetObjectParam)(
           a2,
           L"Allow Child Alias Registration",
           v69) >= 0 )
    {
      v48 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v69 + 16LL))(*(_QWORD *)v69);
    }
    *((_BYTE *)this + 229) = v48;
    *((_DWORD *)this + 56) &= ~0x80u;
    v49 = 0;
    *(_QWORD *)v69 = 0;
    if ( ((int (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, _BYTE *))a2->lpVtbl->GetObjectParam)(
           a2,
           L"EnableOverlayHandlers",
           v69) >= 0 )
    {
      v49 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v69 + 16LL))(*(_QWORD *)v69);
    }
    *((_BYTE *)this + 632) = v49;
    *((_QWORD *)this + 40) = 0;
    *(_QWORD *)v69 = 0;
    if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, _BYTE *))a2->lpVtbl->GetObjectParam)(
           a2,
           L"ParentFolder",
           v69) >= 0 )
    {
      v50 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, char *))v69)(
              *(_QWORD *)v69,
              &GUID_000214e6_0000_0000_c000_000000000046,
              (char *)this + 320);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v69 + 16LL))(*(_QWORD *)v69);
      if ( v50 >= 0 )
      {
        v51 = (int (__fastcall ***)(_QWORD, GUID *, _BYTE *))*((_QWORD *)this + 40);
        *(_QWORD *)v69 = 0;
        if ( v51 && (**v51)(v51, &GUID_c938b119_d3ad_4d02_b5ee_164c2ec8160e, v69) >= 0 )
        {
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v69 + 24LL))(*(_QWORD *)v69);
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v69 + 16LL))(*(_QWORD *)v69);
        }
        *(_OWORD *)ppMalloc = 0;
        if ( !*((_BYTE *)this + 229)
          && (int)IUnknown_GetClassID(*((_QWORD *)this + 40), ppMalloc) >= 0
          && !memcmp_0(ppMalloc, &CLSID_ShellFSFolder, 0x10u) )
        {
          *((_DWORD *)this + 56) |= 0x80u;
        }
      }
    }
  }
  if ( !*((_DWORD *)this + 64) )
  {
    if ( !CallerIdentity::g_fRuntimeBrokerProcessIdInitialize )
    {
      CurrentProcess = GetCurrentProcess();
      LODWORD(ppMalloc[0]) = 260;
      FullProcessImageNameW = QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, (PDWORD)ppMalloc);
      if ( (int)ResultFromWin32Bool(FullProcessImageNameW) >= 0
        && ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\RuntimeBroker.exe", Dst, 0x104u)
        && CompareStringOrdinal(ExeName, -1, Dst, -1, 1) == 2 )
      {
        CallerIdentity::g_dwRuntimeBrokerProcessId = GetProcessId(CurrentProcess);
      }
      CallerIdentity::g_fRuntimeBrokerProcessIdInitialize = 1;
    }
    if ( GetCurrentProcessId() == CallerIdentity::g_dwRuntimeBrokerProcessId )
      *((_DWORD *)this + 64) = 1;
  }
  v19 = (char *)v9 + 312;
  psz = 0;
  v20 = (*(__int64 (__fastcall **)(__int64, const struct _ITEMIDLIST_RELATIVE *, __int64, OLECHAR **))(*((_QWORD *)v9 + 39) + 112LL))(
          (__int64)v9 + 312,
          a4,
          1,
          &psz);
  if ( v20 < 0 )
  {
    v52 = 9550;
LABEL_87:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v52,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)(unsigned int)v20,
      bIgnoreCase);
    if ( psz )
      CoTaskMemFree(psz);
    return (unsigned int)v20;
  }
  v21 = SysAllocString(psz);
  *((_QWORD *)this + 17) = v21;
  if ( v21 )
  {
    v22 = (const WCHAR *)*((_QWORD *)v9 + 58);
    if ( v22 )
      *((_QWORD *)this + 19) = StrDupW(v22);
    v23 = *(__int64 (__fastcall **)(char *, const struct _ITEMIDLIST_RELATIVE *, char *))(*(_QWORD *)v19 + 120LL);
    v24 = (void *)*((_QWORD *)this + 18);
    if ( v24 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v24);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 18) = 0;
    v20 = v23(v19, a4, (char *)this + 144);
    if ( v20 >= 0 )
    {
      if ( !a4 )
        goto LABEL_50;
      v25 = *(_WORD *)a4;
      if ( *(_WORD *)a4 )
      {
        do
        {
          v26 = a4;
          a4 = (const struct _ITEMIDLIST_RELATIVE *)((char *)a4 + v25);
          v25 = *(_WORD *)a4;
        }
        while ( *(_WORD *)a4 );
      }
      else
      {
        v26 = a4;
      }
      v27 = 0;
      if ( v26 )
      {
        v28 = *(unsigned __int16 *)v26;
        if ( (unsigned int)v28 > 0xB )
        {
          if ( (*((_BYTE *)v26 + 2) & 0x70) == 0x30 )
          {
            v27 = v26;
            v29 = v26;
            goto LABEL_31;
          }
          if ( *(_DWORD *)((char *)v26 + 6) == 1179862595 )
          {
            if ( *((unsigned __int16 *)v26 + 2) > (unsigned __int64)(v28 - 4) )
              goto LABEL_50;
            v27 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v26 + 10);
            if ( !IDListContainerIsConsistent((LPCITEMIDLIST)((char *)v26 + 10), *((unsigned __int16 *)v26 + 2))
              || v55 != *(_WORD *)v27 + 6
              || (unsigned __int16)(*(_WORD *)v27 + 6) < *(_WORD *)v27 )
            {
              goto LABEL_50;
            }
          }
        }
      }
      if ( !v27 )
        goto LABEL_50;
      v29 = v27;
LABEL_31:
      if ( *(_WORD *)v27 < 0xEu )
        goto LABEL_50;
      if ( !v26 )
        goto LABEL_55;
      if ( !*(_WORD *)v26 )
        goto LABEL_55;
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl'::`2'::impl);
      v31 = *(_WORD *)v26;
      if ( IsEnabled )
      {
        if ( v31 < 2u )
          goto LABEL_55;
      }
      v32 = 0;
      v33 = *(unsigned __int16 *)((char *)v26 + v31 - 2);
      if ( (_WORD)v33 )
      {
        if ( v33 + 8 < (unsigned __int64)v31 )
        {
          v32 = (unsigned __int16 *)((char *)v26 + v33);
          v34 = *(unsigned __int16 *)((char *)v26 + v33);
          if ( v34 < 8 || HIWORD(*((_DWORD *)v32 + 1)) != 0xBEEF || (unsigned int)v33 + v34 > v31 )
            v32 = 0;
        }
      }
      v35 = (unsigned __int64)v26 + v31;
      if ( v32 )
      {
        while ( *((_DWORD *)v32 + 1) != -1091633148 )
        {
          v53 = 0;
          if ( (unsigned __int64)(v32 + 4) <= v35 )
          {
            v54 = (unsigned __int16 *)((char *)v32 + *v32);
            if ( v54 == (unsigned __int16 *)v35 )
              goto LABEL_55;
            if ( (unsigned __int64)v54 <= v35 )
            {
              if ( (unsigned __int64)(v54 + 4) > v35
                || HIWORD(*((_DWORD *)v54 + 1)) != 0xBEEF
                || (unsigned __int64)v54 + *v54 > v35
                || v54 < v32 + 4 )
              {
                goto LABEL_55;
              }
              v53 = (unsigned __int16 *)((char *)v32 + *v32);
            }
          }
          v32 = v53;
          if ( !v53 )
            goto LABEL_55;
        }
      }
      else
      {
LABEL_55:
        if ( (*((_BYTE *)v27 + 2) & 0x34) == 0x34 )
        {
          v42 = (_WORD *)((char *)v27 + 14);
          if ( v27 != (const struct _ITEMIDLIST_RELATIVE *)-14LL )
          {
            v37 = ((unsigned __int64)*(unsigned __int16 *)v27 - 14) >> 1;
            if ( v37 <= 0x7FFFFFFF )
            {
              for ( ; v37; --v37 )
              {
                if ( !*v42 )
                  break;
                ++v42;
              }
LABEL_47:
              v38 = -2147024809;
              if ( v37 )
                v38 = 0;
LABEL_49:
              if ( v38 >= 0 )
              {
                v39 = *((unsigned __int16 *)v27 + 6);
                v58 = *(_WORD *)v27;
                if ( !*(_WORD *)v27 )
                  goto LABEL_51;
                do
                {
                  v59 = v29;
                  v29 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v29 + v58);
                  v58 = *(_WORD *)v29;
                }
                while ( *(_WORD *)v29 );
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl'::`2'::impl) )
                {
                  if ( !v59 || (v60 = *(_WORD *)v59, *(_WORD *)v59 < 2u) )
                  {
LABEL_51:
                    *((_DWORD *)this + 45) = v39;
                    *((_DWORD *)this + 56) &= ~0x100u;
                    *((_DWORD *)this + 56) |= *((_QWORD *)this + 16) != 0 ? 0x100 : 0;
                    if ( psz )
                      CoTaskMemFree(psz);
                    return 0;
                  }
                }
                else
                {
                  v60 = *(_WORD *)v59;
                }
                v61 = 0;
                v62 = *(unsigned __int16 *)((char *)v59 + v60 - 2);
                if ( (_WORD)v62 )
                {
                  if ( v62 + 8 < (unsigned __int64)v60 )
                  {
                    v61 = (unsigned __int16 *)((char *)v59 + v62);
                    v63 = *(unsigned __int16 *)((char *)v59 + v62);
                    if ( v63 < 8 || HIWORD(*((_DWORD *)v61 + 1)) != 0xBEEF || (unsigned int)v62 + v63 > v60 )
                      v61 = 0;
                  }
                }
                v64 = (unsigned __int64)v59 + *(unsigned __int16 *)v59;
                if ( v61 )
                {
                  while ( 1 )
                  {
                    v65 = v61 + 4;
                    if ( *((_DWORD *)v61 + 1) == -1091633111 )
                      break;
                    v66 = 0;
                    if ( (unsigned __int64)v65 <= v64 )
                    {
                      v67 = (unsigned __int16 *)((char *)v61 + *v61);
                      if ( v67 == (unsigned __int16 *)v64 )
                        goto LABEL_51;
                      if ( (unsigned __int64)v67 <= v64 )
                      {
                        if ( (unsigned __int64)(v67 + 4) > v64
                          || HIWORD(*((_DWORD *)v67 + 1)) != 0xBEEF
                          || (unsigned __int64)v67 + *v67 > v64
                          || v67 < v65 )
                        {
                          goto LABEL_51;
                        }
                        v66 = (unsigned __int16 *)((char *)v61 + *v61);
                      }
                    }
                    v61 = v66;
                    if ( !v66 )
                      goto LABEL_51;
                  }
                  v39 = *((unsigned __int16 *)v27 + 6) | (*v65 << 16);
                }
                goto LABEL_51;
              }
LABEL_50:
              v39 = 0;
              goto LABEL_51;
            }
          }
LABEL_144:
          v38 = -2147024809;
          goto LABEL_49;
        }
      }
      v36 = (char *)v27 + 14;
      if ( v27 != (const struct _ITEMIDLIST_RELATIVE *)-14LL )
      {
        v37 = *(unsigned __int16 *)v27 - 14LL;
        if ( v37 <= 0x7FFFFFFF )
        {
          if ( *(_WORD *)v27 != 14 )
          {
            do
            {
              if ( !*v36 )
                break;
              ++v36;
              --v37;
            }
            while ( v37 );
          }
          goto LABEL_47;
        }
      }
      goto LABEL_144;
    }
    v52 = 9562;
    goto LABEL_87;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2553,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
    (const char *)0x8007000ELL,
    bIgnoreCase);
  if ( psz )
    CoTaskMemFree(psz);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1801820a0  push    rbp
0x1801820a2  push    rbx
0x1801820a3  push    rsi
0x1801820a4  push    rdi
0x1801820a5  push    r12
0x1801820a7  push    r13
0x1801820a9  push    r14
0x1801820ab  push    r15
0x1801820ad  lea     rbp, [rsp-398h]
0x1801820b5  sub     rsp, 498h
0x1801820bc  mov     rax, cs:__security_cookie
0x1801820c3  xor     rax, rsp
0x1801820c6  mov     [rbp+3D0h+var_50], rax
0x1801820cd  mov     rbx, r9
0x1801820d0  mov     r14, rdx
0x1801820d3  mov     rsi, rcx
0x1801820d6  mov     r15, [rbp+3D0h+Src]
0x1801820dd  mov     r13, [rbp+3D0h+arg_28]
0x1801820e4  mov     [rsp+4D0h+var_4A0], r13
0x1801820e9  add     rcx, 0FFFFFFFFFFFFFF10h
0x1801820f0  mov     rax, [rcx]
0x1801820f3  mov     rdx, r8
0x1801820f6  mov     rax, [rax+20h]
0x1801820fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801820ff  mov     edi, eax
0x180182101  test    eax, eax
0x180182103  js      loc_180182C82
0x180182109  xor     r12d, r12d
0x18018210c  test    r15, r15
0x18018210f  jz      loc_1801821C2
0x180182115  mov     rdx, r15
0x180182118  mov     r8d, 2
0x18018211e  xchg    ax, ax
0x180182120  movzx   ecx, word ptr [rdx]
0x180182123  test    cx, cx
0x180182126  jz      short loc_180182130
0x180182128  add     r8d, ecx
0x18018212b  add     rdx, rcx
0x18018212e  jnz     short loc_180182120
0x180182130  mov     r12d, r8d
0x180182133  mov     ecx, r8d; cb
0x180182136  call    cs:__imp_CoTaskMemAlloc
0x18018213d  nop     dword ptr [rax+rax+00h]
0x180182142  mov     rdi, rax
0x180182145  test    rax, rax
0x180182148  jz      loc_180182A3A
0x18018214e  xor     r13d, r13d
0x180182151  mov     [rsp+4D0h+ppMalloc], r13
0x180182156  lea     rdx, [rsp+4D0h+ppMalloc]; ppMalloc
0x18018215b  mov     ecx, 1; dwMemContext
0x180182160  call    cs:__imp_CoGetMalloc
0x180182167  nop     dword ptr [rax+rax+00h]
0x18018216c  test    eax, eax
0x18018216e  js      short loc_180182198
0x180182170  mov     rcx, [rsp+4D0h+ppMalloc]
0x180182175  mov     rax, [rcx]
0x180182178  mov     rdx, rdi
0x18018217b  mov     rax, [rax+30h]
0x18018217f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180182184  mov     r13, rax
0x180182187  mov     rcx, [rsp+4D0h+ppMalloc]
0x18018218c  mov     r9, [rcx]
0x18018218f  mov     rax, [r9+10h]
0x180182193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180182198  mov     r8, r13; Size
0x18018219b  xor     edx, edx; Val
0x18018219d  mov     rcx, rdi; void *
0x1801821a0  call    memset_0
0x1801821a5  mov     r8, r12; Size
0x1801821a8  mov     rdx, r15; Src
0x1801821ab  mov     rcx, rdi; void *
0x1801821ae  call    memcpy_0
0x1801821b3  mov     [rsi+80h], rdi
0x1801821ba  mov     r13, [rsp+4D0h+var_4A0]
0x1801821bf  xor     r12d, r12d
0x1801821c2  mov     edi, 20h ; ' '
0x1801821c7  test    r14, r14
0x1801821ca  jz      short loc_180182205
0x1801821cc  mov     dword ptr [rsp+4D0h+var_4A0], 10h
0x1801821d4  xor     eax, eax
0x1801821d6  mov     [rsp+4D0h+var_4A0+4], rax
0x1801821db  mov     [rsp+4D0h+var_494], eax
0x1801821df  mov     rax, [r14]
0x1801821e2  lea     rdx, [rsp+4D0h+var_4A0]
0x1801821e7  mov     rcx, r14
0x1801821ea  mov     rax, [rax+38h]
0x1801821ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801821f3  test    eax, eax
0x1801821f5  js      short loc_180182205
0x1801821f7  mov     edi, [rsp+4D0h+var_498]
0x1801821fb  bt      edi, 10h
0x1801821ff  jb      loc_180182529
0x180182205  mov     [rsi+124h], edi
0x18018220b  test    r14, r14
0x18018220e  jnz     loc_180182529
0x180182214  cmp     dword ptr [rsi+100h], 0
0x18018221b  jz      loc_1801829A2
0x180182221  lea     r14, [r13+138h]
0x180182228  mov     [rsp+4D0h+psz], r12
0x18018222d  mov     rax, [r14]
0x180182230  lea     r9, [rsp+4D0h+psz]
0x180182235  mov     r8d, 1
0x18018223b  mov     rdx, rbx
0x18018223e  mov     rcx, r14
0x180182241  mov     rax, [rax+70h]
0x180182245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018224a  mov     edi, eax
0x18018224c  test    eax, eax
0x18018224e  js      loc_180182CCB
0x180182254  mov     rcx, [rsp+4D0h+psz]; psz
0x180182259  call    cs:__imp_SysAllocString
0x180182260  nop     dword ptr [rax+rax+00h]
0x180182265  mov     [rsi+88h], rax
0x18018226c  test    rax, rax
0x18018226f  jz      loc_180182C43
0x180182275  mov     rcx, [r13+1D0h]; pszSrch
0x18018227c  test    rcx, rcx
0x18018227f  jz      short loc_180182294
0x180182281  call    cs:__imp_StrDupW
0x180182288  nop     dword ptr [rax+rax+00h]
0x18018228d  mov     [rsi+98h], rax
0x180182294  mov     rax, [r14]
0x180182297  mov     r13, [rax+78h]
0x18018229b  mov     r12, [rsi+90h]
0x1801822a2  test    r12, r12
0x1801822a5  jnz     loc_18018248D
0x1801822ab  mov     qword ptr [rsi+90h], 0
0x1801822b6  lea     r8, [rsi+90h]
0x1801822bd  mov     rdx, rbx
0x1801822c0  mov     rcx, r14
0x1801822c3  mov     rax, r13
0x1801822c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801822cb  mov     edi, eax
0x1801822cd  test    eax, eax
0x1801822cf  js      loc_1801828FF
0x1801822d5  test    rbx, rbx
0x1801822d8  jz      loc_180182425
0x1801822de  movzx   eax, word ptr [rbx]
0x1801822e1  test    ax, ax
0x1801822e4  jz      loc_1801829DD
0x1801822ea  nop     word ptr [rax+rax+00h]
0x1801822f0  mov     rdi, rbx
0x1801822f3  movzx   eax, ax
0x1801822f6  add     rbx, rax
0x1801822f9  movzx   eax, word ptr [rbx]
0x1801822fc  test    ax, ax
0x1801822ff  jnz     short loc_1801822F0
0x180182301  xor     r15d, r15d
0x180182304  test    rdi, rdi
0x180182307  jz      short loc_180182327
0x180182309  movzx   ecx, word ptr [rdi]
0x18018230c  cmp     ecx, 0Bh
0x18018230f  jbe     short loc_180182327
0x180182311  movzx   eax, byte ptr [rdi+2]
0x180182315  and     al, 70h
0x180182317  cmp     al, 30h ; '0'
0x180182319  jnz     loc_1801829E5
0x18018231f  mov     r15, rdi
0x180182322  mov     rbx, rdi
0x180182325  jmp     short loc_180182333
0x180182327  test    r15, r15
0x18018232a  jz      loc_180182425
0x180182330  mov     rbx, r15
0x180182333  cmp     word ptr [r15], 0Eh
0x180182338  jb      loc_180182425
0x18018233e  test    rdi, rdi
0x180182341  jz      loc_1801824C9
0x180182347  cmp     word ptr [rdi], 0
0x18018234b  jz      loc_1801824C9
0x180182351  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow> `wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl(void)'::`2'::impl
0x180182358  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(void)
0x18018235d  movzx   r8d, word ptr [rdi]
0x180182361  test    al, al
0x180182363  jnz     loc_1801824BE
0x180182369  movzx   r11d, r8w
0x18018236d  xor     edx, edx
0x18018236f  movzx   ecx, r8w
0x180182373  movzx   r9d, word ptr [rcx+rdi-2]
0x180182379  mov     r12d, 0BEEFh
0x18018237f  test    r9w, r9w
0x180182383  jz      short loc_1801823BE
0x180182385  lea     rax, [r9+8]
0x180182389  cmp     rax, rcx
0x18018238c  jnb     short loc_1801823BE
0x18018238e  lea     rdx, [r9+rdi]
0x180182392  movzx   ecx, word ptr [rdx]
0x180182395  cmp     ecx, 8
0x180182398  jb      loc_1801829D6
0x18018239e  mov     eax, [rdx+4]
0x1801823a1  shr     rax, 10h
0x1801823a5  cmp     ax, r12w
0x1801823a9  jnz     loc_1801829D6
0x1801823af  add     ecx, r9d
0x1801823b2  movzx   eax, r8w
0x1801823b6  cmp     ecx, eax
0x1801823b8  ja      loc_1801829D6
0x1801823be  movzx   ecx, r11w
0x1801823c2  add     rcx, rdi
0x1801823c5  test    rdx, rdx
0x1801823c8  jz      loc_1801824CF
0x1801823ce  cmp     dword ptr [rdx+4], 0BEEF0004h
0x1801823d5  jnz     loc_180182938
0x1801823db  lea     rcx, [r15+0Eh]
0x1801823df  test    rcx, rcx
0x1801823e2  jz      loc_180182CA4
0x1801823e8  movzx   edx, word ptr [r15]
0x1801823ec  add     rdx, 0FFFFFFFFFFFFFFF2h
0x1801823f0  cmp     rdx, 7FFFFFFFh
0x1801823f7  ja      loc_180182CA4
0x1801823fd  test    rdx, rdx
0x180182400  jz      short loc_180182410
0x180182402  cmp     byte ptr [rcx], 0
0x180182405  jz      short loc_180182410
0x180182407  inc     rcx
0x18018240a  sub     rdx, 1
0x18018240e  jnz     short loc_180182402
0x180182410  xor     eax, eax
0x180182412  mov     ecx, 80070057h
0x180182417  test    rdx, rdx
0x18018241a  cmovnz  ecx, eax
0x18018241d  test    ecx, ecx
0x18018241f  jns     loc_180182B19
0x180182425  xor     r14d, r14d
0x180182428  mov     [rsi+0B4h], r14d
0x18018242f  and     dword ptr [rsi+0E0h], 0FFFFFEFFh
0x180182439  mov     rax, [rsi+80h]
0x180182440  neg     rax
0x180182443  sbb     ecx, ecx
0x180182445  and     ecx, 100h
0x18018244b  or      [rsi+0E0h], ecx
0x180182451  mov     rcx, [rsp+4D0h+psz]; pv
0x180182456  test    rcx, rcx
0x180182459  jz      short loc_180182467
0x18018245b  call    cs:__imp_CoTaskMemFree
0x180182462  nop     dword ptr [rax+rax+00h]
0x180182467  xor     eax, eax
0x180182469  mov     rcx, [rbp+3D0h+var_50]
0x180182470  xor     rcx, rsp; StackCookie
0x180182473  call    __security_check_cookie
0x180182478  add     rsp, 498h
0x18018247f  pop     r15
0x180182481  pop     r14
0x180182483  pop     r13
0x180182485  pop     r12
0x180182487  pop     rdi
0x180182488  pop     rsi
0x180182489  pop     rbx
0x18018248a  pop     rbp
0x18018248b  retn
0x18018248d  call    cs:__imp_GetLastError
0x180182494  nop     dword ptr [rax+rax+00h]
0x180182499  nop
0x18018249a  mov     edi, eax
0x18018249c  mov     rcx, r12; pv
0x18018249f  call    cs:__imp_CoTaskMemFree
0x1801824a6  nop     dword ptr [rax+rax+00h]
0x1801824ab  mov     ecx, edi; dwErrCode
0x1801824ad  call    cs:__imp_SetLastError
0x1801824b4  nop     dword ptr [rax+rax+00h]
0x1801824b9  jmp     loc_1801822AB
0x1801824be  cmp     r8w, 2
0x1801824c3  jnb     loc_180182369
0x1801824c9  mov     r12d, 0BEEFh
0x1801824cf  movzx   eax, byte ptr [r15+2]
0x1801824d4  and     al, 34h
0x1801824d6  cmp     al, 34h ; '4'
0x1801824d8  jnz     loc_1801823DB
0x1801824de  lea     rax, [r15+0Eh]
0x1801824e2  test    rax, rax
0x1801824e5  jz      loc_180182CA4
0x1801824eb  movzx   edx, word ptr [r15]
0x1801824ef  sub     rdx, 0Eh
0x1801824f3  shr     rdx, 1
0x1801824f6  cmp     rdx, 7FFFFFFFh
0x1801824fd  ja      loc_180182CA4
0x180182503  test    rdx, rdx
0x180182506  jz      loc_180182410
0x18018250c  nop     dword ptr [rax+00h]
0x180182510  cmp     word ptr [rax], 0
0x180182514  jz      loc_180182410
0x18018251a  add     rax, 2
0x18018251e  sub     rdx, 1
0x180182522  jnz     short loc_180182510
0x180182524  jmp     loc_180182410
0x180182529  mov     [rsp+4D0h+ppMalloc], r12
0x18018252e  mov     [rsp+4D0h+var_4A0], r12
0x180182533  mov     rax, [r14]
0x180182536  lea     r8, [rsp+4D0h+var_4A0]
0x18018253b  lea     rdx, aItemcacheconte; "ItemCacheContext"
0x180182542  mov     rcx, r14
0x180182545  mov     rax, [rax+50h]
0x180182549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018254e  test    eax, eax
0x180182550  js      loc_180182633
0x180182556  mov     rcx, [rsp+4D0h+var_4A0]
0x18018255b  mov     rax, [rcx]
0x18018255e  lea     r8, [rsp+4D0h+ppMalloc]
0x180182563  lea     rdx, _GUID_0000000e_0000_0000_c000_000000000046
0x18018256a  mov     rax, [rax]
0x18018256d  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
