# CFSFolder::GetPath(_ITEMIDLIST_RELATIVE const *,PATHCCH_OPTIONS,ushort * *)

- ea: `0x180038560`
- end: `0x180038f4a`
- name: `?GetPath@CFSFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@W4PATHCCH_OPTIONS@@PEAPEAG@Z`
- size: `2538`
- prototype: `int(CFSFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, enum PATHCCH_OPTIONS, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, service_task, installer_update, broker_com_uri`

## callees

- `0x180036df0`
- `0x180038560`
- `0x180038f50`
- `0x180038f80`
- `0x1800441c0`
- `0x180103290`
- `0x18034591c`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180038d70`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180038e3f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180038d70`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180038e3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800386a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038e88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800386a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038e88`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180038724`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180038724`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x1800387bd`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x1800387bd`
- `OLEAUT32!__imp_SysAllocString` at `0x180038eb2`
- `OLEAUT32!__imp_SysAllocString` at `0x180038eb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800385ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800385ff`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18003862e`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18003862e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800386bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038837`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003884d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038863`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003888f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800389cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038bcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038be7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038bff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038d2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038e9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800386bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038837`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003884d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038863`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003888f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800389cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038bcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038be7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038bff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038d2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038e9f`
- `SHCORE!__imp_ualstrcpynW` at `0x180038a87`
- `SHCORE!__imp_ualstrcpynW` at `0x180038c45`
- `SHCORE!__imp_ualstrcpynW` at `0x180038a87`
- `SHCORE!__imp_ualstrcpynW` at `0x180038c45`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CFSFolder::GetPath(
        CFSFolder *this,
        const struct _ITEMIDLIST_RELATIVE *a2,
        ULONG a3,
        unsigned __int16 **a4)
{
  void *v6; // r14
  const WCHAR *v7; // rdi
  __int64 v8; // rax
  unsigned __int64 v9; // r15
  const struct _ITEMIDLIST_RELATIVE *i; // rbx
  __int64 v11; // rcx
  void *v12; // rbx
  size_t v13; // rsi
  int v14; // esi
  const struct _ITEMIDLIST_RELATIVE *v16; // rsi
  HRESULT v17; // eax
  unsigned int v18; // edi
  WCHAR *v19; // rdx
  WCHAR *v20; // r8
  HRESULT v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  char IsEnabled; // al
  unsigned __int16 v26; // r8
  unsigned __int16 *v27; // rdx
  __int64 v28; // r9
  unsigned int v29; // ecx
  unsigned __int64 v30; // rcx
  _BYTE *v31; // rcx
  unsigned __int64 v32; // rdx
  int v33; // ecx
  unsigned __int16 *v34; // r9
  _WORD *v35; // rax
  unsigned __int16 *v36; // r8
  WCHAR *v37; // rdx
  WCHAR *v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  const KNOWNFOLDERID *v43; // rcx
  __int64 v44; // rax
  HRESULT v45; // eax
  unsigned int v46; // ebx
  __int64 v47; // rdx
  const ITEMIDLIST *v48; // rcx
  unsigned __int64 v49; // r11
  unsigned __int16 *v50; // r9
  unsigned int v51; // edx
  __int64 v52; // rcx
  const ITEMIDLIST *v53; // rcx
  int lpWideCharStr; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  LPMALLOC ppMalloc; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v59[2]; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v60; // [rsp+70h] [rbp-90h]
  LPVOID v61; // [rsp+78h] [rbp-88h]
  LPVOID v62; // [rsp+90h] [rbp-70h]
  __int64 v63; // [rsp+98h] [rbp-68h]
  __int64 v64; // [rsp+A0h] [rbp-60h]
  __int64 v65; // [rsp+A8h] [rbp-58h]
  __int64 v66; // [rsp+B0h] [rbp-50h]
  __int64 v67; // [rsp+B8h] [rbp-48h]
  WCHAR *v68; // [rsp+C8h] [rbp-38h]
  int v69; // [rsp+E0h] [rbp-20h]
  WCHAR pszMore[278]; // [rsp+E4h] [rbp-1Ch] BYREF
  void **v71; // [rsp+310h] [rbp+210h] BYREF
  LPVOID v72; // [rsp+320h] [rbp+220h]
  LPVOID v73; // [rsp+328h] [rbp+228h]
  LPVOID v74; // [rsp+340h] [rbp+240h]
  __int64 v75; // [rsp+348h] [rbp+248h]
  __int64 v76; // [rsp+350h] [rbp+250h]
  __int64 v77; // [rsp+358h] [rbp+258h]
  __int64 v78; // [rsp+360h] [rbp+260h]
  __int64 v79; // [rsp+368h] [rbp+268h]
  WCHAR *v80; // [rsp+378h] [rbp+278h]
  int v81; // [rsp+390h] [rbp+290h]
  WCHAR WideCharStr[278]; // [rsp+394h] [rbp+294h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+618h] [rbp+518h]

  v6 = 0;
  *a4 = 0;
  pv = 0;
  v7 = (const WCHAR *)*((_QWORD *)this + 17);
  if ( v7 )
    goto LABEL_2;
  pv = 0;
  v43 = (const KNOWNFOLDERID *)((char *)this + 184);
  v44 = *(_QWORD *)&v43->Data1 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)&v43->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
    v44 = *(_QWORD *)v43->Data4 - *(_QWORD *)GUID_NULL.Data4;
  if ( v44 )
  {
    v45 = SHGetKnownFolderPath(v43, 0x4000u, 0, (PWSTR *)&pv);
    v46 = v45;
    if ( v45 < 0 )
    {
      v47 = 1163;
LABEL_125:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v47,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
        (const char *)(unsigned int)v45,
        lpWideCharStr);
LABEL_130:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F5,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
        (const char *)v46,
        lpWideCharStr);
      if ( pv )
        CoTaskMemFree(pv);
      return v46;
    }
  }
  else
  {
    v48 = (const ITEMIDLIST *)*((_QWORD *)this + 16);
    if ( v48 )
    {
      v45 = SHGetNameFromIDList(v48, SIGDN_DESKTOPABSOLUTEPARSING, (PWSTR *)&pv);
      v46 = v45;
      if ( v45 < 0 )
      {
        v47 = 1177;
        goto LABEL_125;
      }
    }
    else
    {
      v53 = (const ITEMIDLIST *)*((_QWORD *)this + 15);
      if ( v53 )
      {
        v45 = SHGetNameFromIDList(v53, SIGDN_DESKTOPABSOLUTEPARSING, (PWSTR *)&pv);
        v46 = v45;
        if ( v45 < 0 )
        {
          v47 = 1181;
          goto LABEL_125;
        }
      }
    }
    if ( !pv )
    {
      v46 = -2147024893;
      goto LABEL_130;
    }
    *((_QWORD *)this + 17) = SysAllocString((const OLECHAR *)pv);
  }
  v7 = (const WCHAR *)pv;
LABEL_2:
  v8 = -1;
  do
    ++v8;
  while ( v7[v8] );
  v9 = v8 + 7;
  for ( i = a2; i; i = (const struct _ITEMIDLIST_RELATIVE *)((char *)i + *(unsigned __int16 *)i) )
  {
    v11 = *(unsigned __int16 *)i;
    if ( !(_WORD)v11 )
      break;
    if ( (unsigned int)v11 <= 0xB )
      goto LABEL_69;
    if ( (*((_BYTE *)i + 2) & 0x70) == 0x30 )
    {
      v16 = i;
    }
    else
    {
      if ( *(_DWORD *)((char *)i + 6) != 1179862595 )
        goto LABEL_69;
      v49 = *((unsigned __int16 *)i + 2);
      if ( v49 > v11 - 4 )
        goto LABEL_69;
      v16 = (const struct _ITEMIDLIST_RELATIVE *)((char *)i + 10);
      v50 = (unsigned __int16 *)((char *)i + 10);
      v51 = 2;
      if ( (unsigned int)v49 < 2 )
        goto LABEL_69;
      while ( 1 )
      {
        v52 = *v50;
        if ( (unsigned int)v52 < 2 || (unsigned int)v52 > (unsigned int)v49 - v51 )
          break;
        v51 += v52;
        v50 = (unsigned __int16 *)((char *)v50 + v52);
        if ( v51 > (unsigned int)v49 )
          goto LABEL_69;
      }
      if ( (_WORD)v52
        || v51 > (unsigned int)v49
        || (_WORD)v49 != *(_WORD *)v16 + 6
        || (unsigned __int16)(*(_WORD *)v16 + 6) < *(_WORD *)v16
        || i == (const struct _ITEMIDLIST_RELATIVE *)-10LL )
      {
LABEL_69:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3FF,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
          (const char *)0x80004005LL,
          lpWideCharStr);
        if ( pv )
          CoTaskMemFree(pv);
        return 2147500037LL;
      }
    }
    if ( *(_WORD *)v16 < 0xEu )
      goto LABEL_69;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl'::`2'::impl);
    v26 = *(_WORD *)i;
    if ( !IsEnabled || v26 >= 2u )
    {
      v27 = 0;
      v28 = *(unsigned __int16 *)((char *)i + v26 - 2);
      if ( (_WORD)v28 )
      {
        if ( v28 + 8 < (unsigned __int64)v26 )
        {
          v27 = (unsigned __int16 *)((char *)i + v28);
          v29 = *(unsigned __int16 *)((char *)i + v28);
          if ( v29 < 8 || HIWORD(*((_DWORD *)v27 + 1)) != 0xBEEF || (unsigned int)v28 + v29 > v26 )
            v27 = 0;
        }
      }
      v30 = (unsigned __int64)i + v26;
      if ( v27 )
      {
        while ( *((_DWORD *)v27 + 1) != -1091633148 )
        {
          v34 = 0;
          if ( (unsigned __int64)(v27 + 4) <= v30 )
          {
            v36 = (unsigned __int16 *)((char *)v27 + *v27);
            if ( v36 == (unsigned __int16 *)v30 )
              goto LABEL_78;
            if ( (unsigned __int64)v36 <= v30 )
            {
              if ( (unsigned __int64)(v36 + 4) > v30
                || HIWORD(*((_DWORD *)v36 + 1)) != 0xBEEF
                || (unsigned __int64)v36 + *v36 > v30
                || v36 < v27 + 4 )
              {
                goto LABEL_78;
              }
              v34 = (unsigned __int16 *)((char *)v27 + *v27);
            }
          }
          v27 = v34;
          if ( !v34 )
            goto LABEL_78;
        }
LABEL_61:
        v31 = (char *)v16 + 14;
        if ( v16 == (const struct _ITEMIDLIST_RELATIVE *)-14LL )
          goto LABEL_157;
        v32 = *(unsigned __int16 *)v16 - 14LL;
        if ( v32 > 0x7FFFFFFF )
          goto LABEL_157;
        if ( *(_WORD *)v16 != 14 )
        {
          do
          {
            if ( !*v31 )
              break;
            ++v31;
            --v32;
          }
          while ( v32 );
        }
        goto LABEL_66;
      }
    }
LABEL_78:
    if ( (*((_BYTE *)v16 + 2) & 0x34) != 0x34 )
      goto LABEL_61;
    v35 = (_WORD *)((char *)v16 + 14);
    if ( v16 == (const struct _ITEMIDLIST_RELATIVE *)-14LL
      || (v32 = ((unsigned __int64)*(unsigned __int16 *)v16 - 14) >> 1, v32 > 0x7FFFFFFF) )
    {
LABEL_157:
      v33 = -2147024809;
      goto LABEL_68;
    }
    for ( ; v32; --v32 )
    {
      if ( !*v35 )
        break;
      ++v35;
    }
LABEL_66:
    v33 = -2147024809;
    if ( v32 )
      v33 = 0;
LABEL_68:
    if ( v33 < 0 )
      goto LABEL_69;
    CFileSysItemString::CFileSysItemString((CFileSysItemString *)&v71, (CFSFolder *)((char *)this - 312), i, v16);
    if ( v80 )
    {
LABEL_115:
      v38 = v80;
      goto LABEL_100;
    }
    if ( (v81 & 1) == 0 )
    {
      if ( v79 )
      {
        v37 = (WCHAR *)(v79 + *(unsigned __int16 *)(v79 + 16));
        if ( ((unsigned __int8)v37 & 1) == 0 )
        {
          if ( v37 != WideCharStr )
          {
            v80 = (WCHAR *)(v79 + *(unsigned __int16 *)(v79 + 16));
            goto LABEL_98;
          }
LABEL_118:
          v81 = 1;
LABEL_98:
          if ( v80 )
            goto LABEL_115;
          goto LABEL_99;
        }
      }
      else
      {
        if ( (*(_BYTE *)(v78 + 2) & 0x34) != 0x34 )
        {
          MultiByteToWideChar(0, 0, (LPCCH)(v78 + 14), -1, WideCharStr, 260);
          goto LABEL_118;
        }
        v37 = (WCHAR *)(v78 + 14);
      }
      ualstrcpynW(WideCharStr, v37, 260);
      goto LABEL_118;
    }
LABEL_99:
    v38 = WideCharStr;
LABEL_100:
    v39 = -1;
    do
      ++v39;
    while ( v38[v39] );
    v9 += v39 + 1;
    v71 = &CFileSysItemString::`vftable';
    v40 = v77;
    v77 = 0;
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    v41 = v75;
    v75 = 0;
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v42 = v76;
    v76 = 0;
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v74 )
      CoTaskMemFree(v74);
    if ( v73 )
      CoTaskMemFree(v73);
    if ( v72 )
      CoTaskMemFree(v72);
  }
  v12 = 0;
  ppMalloc = 0;
  if ( !is_mul_ok(v9, 2u) )
  {
    v14 = -2147024362;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x406,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)(unsigned int)v14,
      lpWideCharStr);
    if ( v6 )
      LocalFree(v12);
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)v14;
  }
  v12 = CoTaskMemAlloc(2 * v9);
  if ( v12 )
  {
    v13 = 0;
    ppMalloc = 0;
    if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
    {
      v13 = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v12);
      ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
    }
    memset_0(v12, 0, v13);
    v14 = 0;
  }
  else
  {
    v14 = -2147024882;
  }
  v6 = v12;
  if ( v14 < 0 )
    goto LABEL_13;
  v17 = PathCchCanonicalizeEx((PWSTR)v12, v9, v7, a3);
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40B,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)(unsigned int)v17,
      lpWideCharStr);
    if ( v12 )
      goto LABEL_151;
    goto LABEL_152;
  }
  while ( 2 )
  {
    if ( !a2 || !*(_WORD *)a2 )
    {
      *a4 = (unsigned __int16 *)v12;
      if ( pv )
        CoTaskMemFree(pv);
      return 0;
    }
    CFileSysItemString::CFileSysItemString((CFileSysItemString *)v59, (CFSFolder *)((char *)this - 312), a2, 0);
    if ( v68 )
      goto LABEL_50;
    if ( (v69 & 1) != 0 )
      goto LABEL_32;
    if ( !v67 )
    {
      if ( (*(_BYTE *)(v66 + 2) & 0x34) != 0x34 )
      {
        MultiByteToWideChar(0, 0, (LPCCH)(v66 + 14), -1, pszMore, 260);
        goto LABEL_87;
      }
      v19 = (WCHAR *)(v66 + 14);
      goto LABEL_86;
    }
    v19 = (WCHAR *)(v67 + *(unsigned __int16 *)(v67 + 16));
    if ( ((unsigned __int8)v19 & 1) != 0 )
    {
LABEL_86:
      ualstrcpynW(pszMore, v19, 260);
      goto LABEL_87;
    }
    if ( v19 != pszMore )
    {
      v68 = (WCHAR *)(v67 + *(unsigned __int16 *)(v67 + 16));
      goto LABEL_31;
    }
LABEL_87:
    v69 = 1;
LABEL_31:
    if ( !v68 )
    {
LABEL_32:
      v20 = pszMore;
      goto LABEL_33;
    }
LABEL_50:
    v20 = v68;
LABEL_33:
    v21 = PathCchAppendEx((PWSTR)v12, v9, v20, a3);
    v18 = v21;
    if ( v21 >= 0 )
    {
      v59[0] = &CFileSysItemString::`vftable';
      v22 = v65;
      v65 = 0;
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      v23 = v63;
      v63 = 0;
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      v24 = v64;
      v64 = 0;
      if ( v24 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      if ( v62 )
        CoTaskMemFree(v62);
      if ( v61 )
        CoTaskMemFree(v61);
      if ( v60 )
        CoTaskMemFree(v60);
      a2 = (const struct _ITEMIDLIST_RELATIVE *)((char *)a2 + *(unsigned __int16 *)a2);
      continue;
    }
    break;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x413,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
    (const char *)(unsigned int)v21,
    lpWideCharStr);
  CFileSysItemString::~CFileSysItemString((CFileSysItemString *)v59);
  if ( !v12 )
    goto LABEL_152;
LABEL_151:
  LocalFree(v12);
LABEL_152:
  if ( pv )
    CoTaskMemFree(pv);
  return v18;
}

```

## disassembly

```asm
0x180038560  push    rbp
0x180038562  push    rbx
0x180038563  push    rsi
0x180038564  push    rdi
0x180038565  push    r12
0x180038567  push    r13
0x180038569  push    r14
0x18003856b  push    r15
0x18003856d  lea     rbp, [rsp-4D8h]
0x180038575  sub     rsp, 5D8h
0x18003857c  mov     rax, cs:__security_cookie
0x180038583  xor     rax, rsp
0x180038586  mov     [rbp+510h+var_50], rax
0x18003858d  mov     [rsp+610h+var_5D8], r9
0x180038592  mov     [rsp+610h+dwFlags], r8d
0x180038597  mov     r12, rdx
0x18003859a  mov     r13, rcx
0x18003859d  xor     r14d, r14d
0x1800385a0  mov     [r9], r14
0x1800385a3  mov     [rsp+610h+pv], r14
0x1800385a8  mov     rdi, [rcx+88h]
0x1800385af  test    rdi, rdi
0x1800385b2  jz      loc_180038C68
0x1800385b8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800385bf  nop
0x1800385c0  lea     rax, [rax+1]
0x1800385c4  cmp     word ptr [rdi+rax*2], 0
0x1800385c9  jnz     short loc_1800385C0
0x1800385cb  lea     r15, [rax+7]
0x1800385cf  mov     rbx, r12
0x1800385d2  test    rbx, rbx
0x1800385d5  jz      short loc_1800385E3
0x1800385d7  movzx   ecx, word ptr [rbx]
0x1800385da  test    cx, cx
0x1800385dd  jnz     loc_1800386F5
0x1800385e3  mov     rbx, r14
0x1800385e6  mov     [rsp+610h+ppMalloc], r14
0x1800385eb  mov     eax, 2
0x1800385f0  mul     r15
0x1800385f3  test    rdx, rdx
0x1800385f6  jnz     loc_1800386EE
0x1800385fc  mov     rcx, rax; cb
0x1800385ff  call    cs:__imp_CoTaskMemAlloc
0x180038606  nop     dword ptr [rax+rax+00h]
0x18003860b  mov     rbx, rax
0x18003860e  mov     [rsp+610h+var_5D0], rax
0x180038613  test    rax, rax
0x180038616  jz      loc_180038E50
0x18003861c  mov     rsi, r14
0x18003861f  mov     [rsp+610h+ppMalloc], r14
0x180038624  lea     rdx, [rsp+610h+ppMalloc]; ppMalloc
0x180038629  mov     ecx, 1; dwMemContext
0x18003862e  call    cs:__imp_CoGetMalloc
0x180038635  nop     dword ptr [rax+rax+00h]
0x18003863a  test    eax, eax
0x18003863c  js      short loc_180038666
0x18003863e  mov     rcx, [rsp+610h+ppMalloc]
0x180038643  mov     rax, [rcx]
0x180038646  mov     rdx, rbx
0x180038649  mov     rax, [rax+30h]
0x18003864d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038652  mov     rsi, rax
0x180038655  mov     rcx, [rsp+610h+ppMalloc]
0x18003865a  mov     rdx, [rcx]
0x18003865d  mov     rax, [rdx+10h]
0x180038661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038666  mov     r8, rsi; Size
0x180038669  xor     edx, edx; Val
0x18003866b  mov     rcx, rbx; void *
0x18003866e  call    memset_0
0x180038673  mov     esi, r14d
0x180038676  mov     r14, rbx
0x180038679  test    esi, esi
0x18003867b  jns     loc_180038714
0x180038681  mov     rcx, [rbp+518h]; this
0x180038688  mov     r9d, esi; char *
0x18003868b  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x180038692  mov     edx, 406h; void *
0x180038697  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003869c  nop
0x18003869d  test    r14, r14
0x1800386a0  jz      short loc_1800386B2
0x1800386a2  mov     rcx, rbx; hMem
0x1800386a5  call    cs:__imp_LocalFree
0x1800386ac  nop     dword ptr [rax+rax+00h]
0x1800386b1  nop
0x1800386b2  mov     rcx, [rsp+610h+pv]; pv
0x1800386b7  test    rcx, rcx
0x1800386ba  jz      short loc_1800386C8
0x1800386bc  call    cs:__imp_CoTaskMemFree
0x1800386c3  nop     dword ptr [rax+rax+00h]
0x1800386c8  mov     eax, esi
0x1800386ca  mov     rcx, [rbp+510h+var_50]
0x1800386d1  xor     rcx, rsp; StackCookie
0x1800386d4  call    __security_check_cookie
0x1800386d9  add     rsp, 5D8h
0x1800386e0  pop     r15
0x1800386e2  pop     r14
0x1800386e4  pop     r13
0x1800386e6  pop     r12
0x1800386e8  pop     rdi
0x1800386e9  pop     rsi
0x1800386ea  pop     rbx
0x1800386eb  pop     rbp
0x1800386ec  retn
0x1800386ee  mov     esi, 80070216h
0x1800386f3  jmp     short loc_180038681
0x1800386f5  cmp     ecx, 0Bh
0x1800386f8  jbe     loc_1800389A2
0x1800386fe  movzx   eax, byte ptr [rbx+2]
0x180038702  and     al, 70h
0x180038704  cmp     al, 30h ; '0'
0x180038706  jnz     loc_180038D81
0x18003870c  mov     rsi, rbx
0x18003870f  jmp     loc_1800388C5
0x180038714  mov     esi, [rsp+610h+dwFlags]
0x180038718  mov     r9d, esi; dwFlags
0x18003871b  mov     r8, rdi; pszPathIn
0x18003871e  mov     rdx, r15; cchPathOut
0x180038721  mov     rcx, rbx; pszPathOut
0x180038724  call    cs:__imp_PathCchCanonicalizeEx
0x18003872b  nop     dword ptr [rax+rax+00h]
0x180038730  mov     edi, eax
0x180038732  test    eax, eax
0x180038734  js      loc_180038EF3
0x18003873a  test    r12, r12
0x18003873d  jz      loc_18003887D
0x180038743  cmp     word ptr [r12], 0
0x180038749  jz      loc_18003887D
0x18003874f  lea     rdx, [r13-138h]; struct CFSFolder *
0x180038756  xor     r9d, r9d; struct IDFOLDER *
0x180038759  mov     r8, r12; struct _ITEMIDLIST_RELATIVE *
0x18003875c  lea     rcx, [rsp+610h+var_5B0]; this
0x180038761  call    ??0CFileSysItemString@@QEAA@PEAVCFSFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEFBUIDFOLDER@@@Z; CFileSysItemString::CFileSysItemString(CFSFolder *,_ITEMIDLIST_RELATIVE const *,IDFOLDER const *)
0x180038766  cmp     [rbp+510h+var_548], 0
0x18003876b  jnz     loc_1800388A2
0x180038771  test    byte ptr [rbp+510h+var_530], 1
0x180038775  jnz     short loc_1800387B0
0x180038777  mov     rcx, [rbp+510h+var_558]
0x18003877b  test    rcx, rcx
0x18003877e  jz      loc_180038D3E
0x180038784  movzx   edx, word ptr [rcx+10h]
0x180038788  add     rdx, rcx
0x18003878b  test    dl, 1
0x18003878e  jnz     loc_180038A7D
0x180038794  lea     rax, [rbp+510h+pszMore]
0x180038798  cmp     rdx, rax
0x18003879b  jz      loc_180038A93
0x1800387a1  mov     [rbp+510h+var_548], rdx
0x1800387a5  cmp     [rbp+510h+var_548], 0
0x1800387aa  jnz     loc_1800388A2
0x1800387b0  lea     r8, [rbp+510h+pszMore]; pszMore
0x1800387b4  mov     r9d, esi; dwFlags
0x1800387b7  mov     rdx, r15; cchPath
0x1800387ba  mov     rcx, rbx; pszPath
0x1800387bd  call    cs:__imp_PathCchAppendEx
0x1800387c4  nop     dword ptr [rax+rax+00h]
0x1800387c9  mov     edi, eax
0x1800387cb  test    eax, eax
0x1800387cd  js      loc_180038E5A
0x1800387d3  lea     rax, ??_7CFileSysItemString@@6B@; const CFileSysItemString::`vftable'
0x1800387da  mov     [rsp+610h+var_5B0], rax
0x1800387df  mov     rcx, [rbp+510h+var_568]
0x1800387e3  mov     [rbp+510h+var_568], 0
0x1800387eb  test    rcx, rcx
0x1800387ee  jz      short loc_1800387FC
0x1800387f0  mov     rax, [rcx]
0x1800387f3  mov     rax, [rax+10h]
0x1800387f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800387fc  mov     rcx, [rbp+510h+var_578]
0x180038800  mov     [rbp+510h+var_578], 0
0x180038808  test    rcx, rcx
0x18003880b  jnz     loc_1800388AB
0x180038811  mov     rcx, [rbp+510h+var_570]
0x180038815  mov     [rbp+510h+var_570], 0
0x18003881d  test    rcx, rcx
0x180038820  jz      short loc_18003882E
0x180038822  mov     rax, [rcx]
0x180038825  mov     rax, [rax+10h]
0x180038829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003882e  mov     rcx, [rbp+510h+var_580]; pv
0x180038832  test    rcx, rcx
0x180038835  jz      short loc_180038843
0x180038837  call    cs:__imp_CoTaskMemFree
0x18003883e  nop     dword ptr [rax+rax+00h]
0x180038843  mov     rcx, [rsp+610h+var_598]; pv
0x180038848  test    rcx, rcx
0x18003884b  jz      short loc_180038859
0x18003884d  call    cs:__imp_CoTaskMemFree
0x180038854  nop     dword ptr [rax+rax+00h]
0x180038859  mov     rcx, [rsp+610h+var_5A0]; pv
0x18003885e  test    rcx, rcx
0x180038861  jz      short loc_180038870
0x180038863  call    cs:__imp_CoTaskMemFree
0x18003886a  nop     dword ptr [rax+rax+00h]
0x18003886f  nop
0x180038870  movzx   eax, word ptr [r12]
0x180038875  add     r12, rax
0x180038878  jmp     loc_18003873A
0x18003887d  mov     rax, [rsp+610h+var_5D8]
0x180038882  mov     [rax], rbx
0x180038885  mov     rcx, [rsp+610h+pv]; pv
0x18003888a  test    rcx, rcx
0x18003888d  jz      short loc_18003889B
0x18003888f  call    cs:__imp_CoTaskMemFree
0x180038896  nop     dword ptr [rax+rax+00h]
0x18003889b  xor     eax, eax
0x18003889d  jmp     loc_1800386CA
0x1800388a2  mov     r8, [rbp+510h+var_548]
0x1800388a6  jmp     loc_1800387B4
0x1800388ab  mov     rax, [rcx]
0x1800388ae  mov     rax, [rax+10h]
0x1800388b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800388b7  jmp     loc_180038811
0x1800388bc  test    rsi, rsi
0x1800388bf  jz      loc_1800389A2
0x1800388c5  cmp     word ptr [rsi], 0Eh
0x1800388c9  jb      loc_1800389A2
0x1800388cf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow> `wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl(void)'::`2'::impl
0x1800388d6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(void)
0x1800388db  movzx   r8d, word ptr [rbx]
0x1800388df  test    al, al
0x1800388e1  jnz     loc_180038EE3
0x1800388e7  movzx   r10d, r8w
0x1800388eb  mov     rdx, r14
0x1800388ee  movzx   ecx, r8w
0x1800388f2  movzx   r9d, word ptr [rcx+rbx-2]
0x1800388f8  test    r9w, r9w
0x1800388fc  jz      short loc_18003893D
0x1800388fe  lea     rax, [r9+8]
0x180038902  cmp     rax, rcx
0x180038905  jnb     short loc_18003893D
0x180038907  lea     rdx, [r9+rbx]
0x18003890b  movzx   ecx, word ptr [rdx]
0x18003890e  cmp     ecx, 8
0x180038911  jb      loc_180038C60
0x180038917  mov     eax, [rdx+4]
0x18003891a  shr     rax, 10h
0x18003891e  mov     r11d, 0BEEFh
0x180038924  cmp     ax, r11w
0x180038928  jnz     loc_180038C60
0x18003892e  add     ecx, r9d
0x180038931  movzx   eax, r8w
0x180038935  cmp     ecx, eax
0x180038937  ja      loc_180038C60
0x18003893d  movzx   ecx, r10w
0x180038941  add     rcx, rbx
0x180038944  test    rdx, rdx
0x180038947  jz      loc_180038A1C
0x18003894d  cmp     dword ptr [rdx+4], 0BEEF0004h
0x180038954  jnz     loc_180038A9F
0x18003895a  lea     rcx, [rsi+0Eh]
0x18003895e  test    rcx, rcx
0x180038961  jz      loc_180038ECF
0x180038967  movzx   edx, word ptr [rsi]
0x18003896a  add     rdx, 0FFFFFFFFFFFFFFF2h
0x18003896e  cmp     rdx, 7FFFFFFFh
0x180038975  ja      loc_180038ECF
0x18003897b  test    rdx, rdx
0x18003897e  jz      short loc_18003898E
0x180038980  cmp     byte ptr [rcx], 0
0x180038983  jz      short loc_18003898E
0x180038985  inc     rcx
0x180038988  sub     rdx, 1
0x18003898c  jnz     short loc_180038980
0x18003898e  mov     ecx, 80070057h
0x180038993  test    rdx, rdx
0x180038996  cmovnz  ecx, r14d
0x18003899a  test    ecx, ecx
0x18003899c  jns     loc_180038ACA
0x1800389a2  mov     rcx, [rbp+518h]; this
0x1800389a9  mov     r9d, 80004005h; char *
0x1800389af  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x1800389b6  mov     edx, 3FFh; void *
0x1800389bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800389c0  nop
0x1800389c1  mov     rcx, [rsp+610h+pv]; pv
0x1800389c6  test    rcx, rcx
0x1800389c9  jz      short loc_1800389D7
0x1800389cb  call    cs:__imp_CoTaskMemFree
0x1800389d2  nop     dword ptr [rax+rax+00h]
0x1800389d7  mov     eax, 80004005h
0x1800389dc  jmp     loc_1800386CA
0x1800389e1  lea     rax, [r8+8]
0x1800389e5  cmp     rax, rcx
0x1800389e8  ja      short loc_180038A1C
0x1800389ea  mov     eax, [r8+4]
0x1800389ee  shr     rax, 10h
0x1800389f2  mov     edx, 0BEEFh
0x1800389f7  cmp     ax, dx
0x1800389fa  jnz     short loc_180038A1C
0x1800389fc  movzx   eax, word ptr [r8]
0x180038a00  add     rax, r8
0x180038a03  cmp     rax, rcx
0x180038a06  ja      short loc_180038A1C
0x180038a08  cmp     r8, r10
0x180038a0b  jb      short loc_180038A1C
0x180038a0d  mov     r9, r8
0x180038a10  mov     rdx, r9
0x180038a13  test    r9, r9
  ... truncated ...
```
