# CFSFolder::TryGetShortPath(_ITEMIDLIST_RELATIVE const *,ushort * *)

- ea: `0x180037a90`
- end: `0x18003854c`
- name: `?TryGetShortPath@CFSFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAG@Z`
- size: `2748`
- prototype: `int(CFSFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `12`
- tags: `reparse_path, service_task, installer_update, broker_com_uri`

## callees

- `0x180036df0`
- `0x180037a90`
- `0x180038f50`
- `0x180038f80`
- `0x1800441c0`
- `0x1800995d0`
- `0x180103290`
- `0x180107000`
- `0x18034591c`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038025`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800383df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038025`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800383df`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180037c40`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180037c40`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x180037cdd`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x180037cdd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800384a3`
- `OLEAUT32!__imp_SysAllocString` at `0x1800384a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037baa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037baa`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180037bdd`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180037bdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037b34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037d57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037d6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037d83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037f2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003803e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800380e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038277`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003828d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800382a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038321`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038337`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003834d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800383f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037b34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037d57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037d6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037d83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037f2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003803e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800380e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038277`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003828d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800382a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038321`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038337`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003834d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800383f8`
- `SHCORE!__imp_ualstrlenW` at `0x180660378`
- `SHCORE!__imp_ualstrlenW` at `0x1806603c8`
- `SHCORE!__imp_ualstrlenW` at `0x180660378`
- `SHCORE!__imp_ualstrlenW` at `0x1806603c8`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x180037cc3`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x180037cc3`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CFSFolder::TryGetShortPath(
        CFSFolder *this,
        const struct _ITEMIDLIST_RELATIVE *a2,
        unsigned __int16 **a3)
{
  void *v5; // r14
  const WCHAR *v6; // rdi
  __int64 v7; // rax
  size_t v8; // r12
  const struct _ITEMIDLIST_RELATIVE *i; // rbx
  __int64 v10; // rcx
  void *v11; // rcx
  const struct _ITEMIDLIST_RELATIVE *v13; // rsi
  void *v14; // rbx
  size_t v15; // rsi
  int v16; // esi
  HRESULT v17; // eax
  unsigned int v18; // edi
  __int64 v19; // rdx
  unsigned __int64 *v20; // r8
  unsigned int v21; // r9d
  HRESULT v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  WCHAR *v27; // rdx
  __int64 v28; // r9
  WCHAR *v29; // r8
  WCHAR v30; // ax
  WCHAR *v31; // rcx
  char IsEnabled; // al
  unsigned __int16 v33; // r8
  unsigned __int16 *v34; // rdx
  __int64 v35; // r10
  unsigned int v36; // ecx
  unsigned __int64 v37; // rcx
  _BYTE *v38; // rcx
  unsigned __int64 v39; // rdx
  int v40; // ecx
  unsigned __int16 *v41; // r8
  _WORD *v42; // rax
  unsigned __int16 *v43; // r9
  const KNOWNFOLDERID *v44; // rcx
  __int64 v45; // rax
  HRESULT v46; // eax
  unsigned int v47; // ebx
  __int64 v48; // rdx
  const ITEMIDLIST *v49; // rcx
  unsigned __int64 v50; // r11
  unsigned __int16 *v51; // r9
  unsigned int v52; // edx
  __int64 v53; // rcx
  __int64 v54; // rdx
  unsigned __int64 *v55; // rcx
  unsigned int v56; // r8d
  char *v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // rcx
  char *v65; // rdx
  __int64 v66; // r8
  unsigned __int64 *v67; // r8
  unsigned int v68; // edx
  int v69; // eax
  __int64 v70; // r9
  unsigned int v71; // r9d
  unsigned int v72; // ecx
  int v73; // eax
  const ITEMIDLIST *v74; // rcx
  int v75; // eax
  unsigned int v76; // edx
  int v77; // eax
  int v78; // eax
  unsigned int v79; // ecx
  int v80; // eax
  int v81[2]; // [rsp+20h] [rbp-E0h]
  WCHAR pwszDst[16]; // [rsp+28h] [rbp-D8h] BYREF
  void *v83; // [rsp+48h] [rbp-B8h]
  _QWORD v84[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v85; // [rsp+60h] [rbp-A0h]
  LPVOID v86; // [rsp+68h] [rbp-98h]
  LPVOID v87; // [rsp+80h] [rbp-80h]
  __int64 v88; // [rsp+88h] [rbp-78h]
  __int64 v89; // [rsp+90h] [rbp-70h]
  __int64 v90; // [rsp+98h] [rbp-68h]
  unsigned __int64 *v91; // [rsp+A0h] [rbp-60h]
  __int64 v92; // [rsp+A8h] [rbp-58h]
  LPVOID pv; // [rsp+300h] [rbp+200h] BYREF
  LPMALLOC ppMalloc; // [rsp+308h] [rbp+208h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  *(_QWORD *)v81 = a3;
  v5 = 0;
  *a3 = 0;
  pv = 0;
  v6 = (const WCHAR *)*((_QWORD *)this + 18);
  if ( v6 )
    goto LABEL_3;
  v6 = (const WCHAR *)*((_QWORD *)this + 17);
  if ( v6 )
    goto LABEL_3;
  pv = 0;
  v44 = (const KNOWNFOLDERID *)((char *)this + 184);
  v45 = *(_QWORD *)&v44->Data1 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)&v44->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
    v45 = *(_QWORD *)v44->Data4 - *(_QWORD *)GUID_NULL.Data4;
  if ( !v45 )
  {
    v49 = (const ITEMIDLIST *)*((_QWORD *)this + 16);
    if ( v49 )
    {
      v46 = SHGetNameFromIDList(v49, SIGDN_DESKTOPABSOLUTEPARSING, (PWSTR *)&pv);
      v47 = v46;
      if ( v46 < 0 )
      {
        v48 = 1177;
        goto LABEL_100;
      }
    }
    else
    {
      v74 = (const ITEMIDLIST *)*((_QWORD *)this + 15);
      if ( v74 )
      {
        v46 = SHGetNameFromIDList(v74, SIGDN_DESKTOPABSOLUTEPARSING, (PWSTR *)&pv);
        v47 = v46;
        if ( v46 < 0 )
        {
          v48 = 1181;
          goto LABEL_100;
        }
      }
    }
    if ( !pv )
    {
      v47 = -2147024893;
      goto LABEL_101;
    }
    *((_QWORD *)this + 17) = SysAllocString((const OLECHAR *)pv);
LABEL_173:
    v6 = (const WCHAR *)pv;
LABEL_3:
    v7 = -1;
    do
      ++v7;
    while ( v6[v7] );
    v8 = v7 + 1;
    for ( i = a2; ; i = (const struct _ITEMIDLIST_RELATIVE *)((char *)i + *(unsigned __int16 *)i) )
    {
      if ( !i || (v10 = *(unsigned __int16 *)i, !(_WORD)v10) )
      {
        if ( v8 >= 0x104 )
        {
LABEL_9:
          v11 = pv;
          if ( pv )
            goto LABEL_10;
          return 0;
        }
        v14 = 0;
        ppMalloc = 0;
        if ( is_mul_ok(v8, 2u) )
        {
          v14 = CoTaskMemAlloc(2 * v8);
          v83 = v14;
          if ( v14 )
          {
            v15 = 0;
            ppMalloc = 0;
            if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
            {
              v15 = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v14);
              ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
            }
            memset_0(v14, 0, v15);
            v16 = 0;
          }
          else
          {
            v16 = -2147024882;
          }
          v5 = v14;
          if ( v16 >= 0 )
          {
            v17 = PathCchCanonicalizeEx((PWSTR)v14, v8, v6, 0);
            v18 = v17;
            if ( v17 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x470,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
                (const char *)(unsigned int)v17,
                v81[0]);
              if ( v14 )
                goto LABEL_158;
            }
            else
            {
              while ( 1 )
              {
                if ( !a2 || !*(_WORD *)a2 )
                {
                  **(_QWORD **)v81 = v14;
                  goto LABEL_9;
                }
                CFileSysItemString::CFileSysItemString(
                  (CFileSysItemString *)v84,
                  (CFSFolder *)((char *)this - 312),
                  a2,
                  0);
                memset(pwszDst, 0, 26);
                v20 = v91;
                v21 = 0;
                if ( (*((_BYTE *)v91 + 2) & 0x34) == 0x34 )
                {
                  if ( !v92 )
                  {
                    v78 = ualstrlenW((char *)v91 + 14, v19, v91);
                    v20 = v91;
                    v79 = *(unsigned __int16 *)v91;
                    if ( v79 <= 2 * v78 + 16
                      || (v80 = UnalignedStringCbLengthW(
                                  (const unsigned __int16 *)((char *)v91 + (unsigned int)(2 * v78 + 2) + 14),
                                  v79 - (2 * v78 + 2) - 14,
                                  v91),
                          v20 = v91,
                          v80 < 0) )
                    {
                      v21 = 0;
                    }
                  }
                  v26 = 2147483646;
                  v27 = (WCHAR *)((char *)v20 + v21 + 14);
                  v28 = 13;
                  v29 = pwszDst;
                  do
                  {
                    if ( !v26 )
                      break;
                    v30 = *v27;
                    if ( !*v27 )
                      break;
                    ++v27;
                    *v29++ = v30;
                    --v26;
                    --v28;
                  }
                  while ( v28 );
                  v31 = v29 - 1;
                  if ( v28 )
                    v31 = v29;
                  *v31 = 0;
                }
                else
                {
                  if ( !v92 )
                  {
                    v70 = -1;
                    do
                      ++v70;
                    while ( *((_BYTE *)v91 + v70 + 14) );
                    v71 = v70 + 1;
                    v72 = *(unsigned __int16 *)v91;
                    if ( v72 <= v71 + 14
                      || (v73 = StringCbLengthA((const char *)v91 + v71 + 14, v72 - v71 - 14, v91), v20 = v91, v73 < 0) )
                    {
                      v21 = 0;
                    }
                  }
                  SHAnsiToUnicode((PCSTR)v20 + v21 + 14, pwszDst, 13);
                }
                v22 = PathCchAppendEx((PWSTR)v14, v8, pwszDst, 0);
                v18 = v22;
                if ( v22 < 0 )
                  break;
                v84[0] = &CFileSysItemString::`vftable';
                v23 = v90;
                v90 = 0;
                if ( v23 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
                v24 = v88;
                v88 = 0;
                if ( v24 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
                v25 = v89;
                v89 = 0;
                if ( v25 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
                if ( v87 )
                  CoTaskMemFree(v87);
                if ( v86 )
                  CoTaskMemFree(v86);
                if ( v85 )
                  CoTaskMemFree(v85);
                a2 = (const struct _ITEMIDLIST_RELATIVE *)((char *)a2 + *(unsigned __int16 *)a2);
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x479,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
                (const char *)(unsigned int)v22,
                v81[0]);
              CFileSysItemString::~CFileSysItemString((CFileSysItemString *)v84);
              if ( v14 )
LABEL_158:
                LocalFree(v14);
            }
            if ( pv )
              CoTaskMemFree(pv);
            return v18;
          }
        }
        else
        {
          v16 = -2147024362;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x46B,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
          (const char *)(unsigned int)v16,
          v81[0]);
        if ( v5 )
          LocalFree(v14);
        if ( pv )
          CoTaskMemFree(pv);
        return (unsigned int)v16;
      }
      if ( (unsigned int)v10 <= 0xB )
        goto LABEL_68;
      if ( (*((_BYTE *)i + 2) & 0x70) == 0x30 )
      {
        v13 = i;
      }
      else
      {
        if ( *(_DWORD *)((char *)i + 6) != 1179862595 )
          goto LABEL_68;
        v50 = *((unsigned __int16 *)i + 2);
        if ( v50 > v10 - 4 )
          goto LABEL_68;
        v13 = (const struct _ITEMIDLIST_RELATIVE *)((char *)i + 10);
        v51 = (unsigned __int16 *)((char *)i + 10);
        v52 = 2;
        if ( (unsigned int)v50 < 2 )
          goto LABEL_68;
        while ( 1 )
        {
          v53 = *v51;
          if ( (unsigned int)v53 < 2 || (unsigned int)v53 > (unsigned int)v50 - v52 )
            break;
          v52 += v53;
          v51 = (unsigned __int16 *)((char *)v51 + v53);
          if ( v52 > (unsigned int)v50 )
            goto LABEL_68;
        }
        if ( (_WORD)v53
          || v52 > (unsigned int)v50
          || (_WORD)v50 != *(_WORD *)v13 + 6
          || (unsigned __int16)(*(_WORD *)v13 + 6) < *(_WORD *)v13
          || i == (const struct _ITEMIDLIST_RELATIVE *)-10LL )
        {
LABEL_68:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x458,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
            (const char *)0x80070057LL,
            v81[0]);
          if ( pv )
            CoTaskMemFree(pv);
          return 2147942487LL;
        }
      }
      if ( *(_WORD *)v13 < 0xEu )
        goto LABEL_68;
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl'::`2'::impl);
      v33 = *(_WORD *)i;
      if ( !IsEnabled || v33 >= 2u )
      {
        v34 = 0;
        v35 = *(unsigned __int16 *)((char *)i + v33 - 2);
        if ( (_WORD)v35 )
        {
          if ( v35 + 8 < (unsigned __int64)v33 )
          {
            v34 = (unsigned __int16 *)((char *)i + v35);
            v36 = *(unsigned __int16 *)((char *)i + v35);
            if ( v36 < 8 || HIWORD(*((_DWORD *)v34 + 1)) != 0xBEEF || (unsigned int)v35 + v36 > v33 )
              v34 = 0;
          }
        }
        v37 = (unsigned __int64)i + v33;
        if ( v34 )
          break;
      }
LABEL_77:
      if ( (*((_BYTE *)v13 + 2) & 0x34) != 0x34 )
        goto LABEL_60;
      v42 = (_WORD *)((char *)v13 + 14);
      if ( v13 == (const struct _ITEMIDLIST_RELATIVE *)-14LL
        || (v39 = ((unsigned __int64)*(unsigned __int16 *)v13 - 14) >> 1, v39 > 0x7FFFFFFF) )
      {
LABEL_174:
        v40 = -2147024809;
        goto LABEL_67;
      }
      for ( ; v39; --v39 )
      {
        if ( !*v42 )
          break;
        ++v42;
      }
LABEL_65:
      v40 = -2147024809;
      if ( v39 )
        v40 = 0;
LABEL_67:
      if ( v40 < 0 )
        goto LABEL_68;
      CFileSysItemString::CFileSysItemString((CFileSysItemString *)v84, (CFSFolder *)((char *)this - 312), i, v13);
      v55 = v91;
      v56 = 0;
      if ( (*((_BYTE *)v91 + 2) & 0x34) == 0x34 )
      {
        if ( !v92 )
        {
          v75 = ualstrlenW((char *)v91 + 14, v54, 0);
          v55 = v91;
          v76 = *(unsigned __int16 *)v91;
          if ( v76 <= 2 * v75 + 16
            || (v77 = UnalignedStringCbLengthW(
                        (const unsigned __int16 *)((char *)v91 + (unsigned int)(2 * v75 + 2) + 14),
                        v76 - (2 * v75 + 2) - 14,
                        (unsigned __int64 *)(unsigned int)(2 * v75 + 2)),
                v55 = v91,
                v77 < 0) )
          {
            v56 = 0;
          }
        }
        v65 = (char *)v55 + v56;
        v58 = -1;
        do
          ++v58;
        while ( *(_WORD *)&v65[2 * v58 + 14] );
      }
      else
      {
        if ( !v92 )
        {
          v66 = -1;
          do
            ++v66;
          while ( *((_BYTE *)v91 + v66 + 14) );
          v67 = (unsigned __int64 *)(unsigned int)(v66 + 1);
          v68 = *(unsigned __int16 *)v91;
          if ( v68 <= (int)v67 + 14
            || (v69 = StringCbLengthA((const char *)v91 + (unsigned int)v67 + 14, v68 - (unsigned int)v67 - 14, v67),
                v55 = v91,
                v69 < 0) )
          {
            v56 = 0;
          }
        }
        v57 = (char *)v55 + v56;
        v58 = -1;
        do
          ++v58;
        while ( v57[v58 + 14] );
      }
      if ( (unsigned __int64)(v58 - 1) > 0xB )
      {
        v84[0] = &CFileSysItemString::`vftable';
        v62 = v90;
        v90 = 0;
        if ( v62 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
        v63 = v88;
        v88 = 0;
        if ( v63 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
        v64 = v89;
        v89 = 0;
        if ( v64 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
        if ( v87 )
          CoTaskMemFree(v87);
        if ( v86 )
          CoTaskMemFree(v86);
        if ( v85 )
          CoTaskMemFree(v85);
        v11 = pv;
        if ( pv )
LABEL_10:
          CoTaskMemFree(v11);
        return 0;
      }
      v8 += v58 + 1;
      v84[0] = &CFileSysItemString::`vftable';
      v59 = v90;
      v90 = 0;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
      v60 = v88;
      v88 = 0;
      if ( v60 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
      v61 = v89;
      v89 = 0;
      if ( v61 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
      if ( v87 )
        CoTaskMemFree(v87);
      if ( v86 )
        CoTaskMemFree(v86);
      if ( v85 )
        CoTaskMemFree(v85);
    }
    while ( *((_DWORD *)v34 + 1) != -1091633148 )
    {
      v41 = 0;
      if ( (unsigned __int64)(v34 + 4) <= v37 )
      {
        v43 = (unsigned __int16 *)((char *)v34 + *v34);
        if ( v43 == (unsigned __int16 *)v37 )
          goto LABEL_77;
        if ( (unsigned __int64)v43 <= v37 )
        {
          if ( (unsigned __int64)(v43 + 4) > v37
            || HIWORD(*((_DWORD *)v43 + 1)) != 0xBEEF
            || (unsigned __int64)v43 + *v43 > v37
            || v43 < v34 + 4 )
          {
            goto LABEL_77;
          }
          v41 = (unsigned __int16 *)((char *)v34 + *v34);
        }
      }
      v34 = v41;
      if ( !v41 )
        goto LABEL_77;
    }
LABEL_60:
    v38 = (char *)v13 + 14;
    if ( v13 == (const struct _ITEMIDLIST_RELATIVE *)-14LL )
      goto LABEL_174;
    v39 = *(unsigned __int16 *)v13 - 14LL;
    if ( v39 > 0x7FFFFFFF )
      goto LABEL_174;
    if ( *(_WORD *)v13 != 14 )
    {
      do
      {
        if ( !*v38 )
          break;
        ++v38;
        --v39;
      }
      while ( v39 );
    }
    goto LABEL_65;
  }
  v46 = SHGetKnownFolderPath(v44, 0x4000u, 0, (PWSTR *)&pv);
  v47 = v46;
  if ( v46 >= 0 )
    goto LABEL_173;
  v48 = 1163;
LABEL_100:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v48,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
    (const char *)(unsigned int)v46,
    v81[0]);
LABEL_101:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x44B,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
    (const char *)v47,
    v81[0]);
  if ( pv )
    CoTaskMemFree(pv);
  return v47;
}

```

## disassembly

```asm
0x180037a90  mov     [rsp-8+arg_18], rbx
0x180037a95  push    rbp
0x180037a96  push    rsi
0x180037a97  push    rdi
0x180037a98  push    r12
0x180037a9a  push    r13
0x180037a9c  push    r14
0x180037a9e  push    r15
0x180037aa0  lea     rbp, [rsp-220h]
0x180037aa8  sub     rsp, 320h
0x180037aaf  mov     rax, cs:__security_cookie
0x180037ab6  xor     rax, rsp
0x180037ab9  mov     [rbp+250h+var_40], rax
0x180037ac0  mov     qword ptr [rsp+350h+var_330], r8; int
0x180037ac5  mov     r15, rdx
0x180037ac8  mov     r13, rcx
0x180037acb  xor     r14d, r14d
0x180037ace  mov     [r8], r14
0x180037ad1  mov     [rbp+250h+pv], r14
0x180037ad8  mov     rdi, [rcx+90h]
0x180037adf  test    rdi, rdi
0x180037ae2  jnz     short loc_180037AF4
0x180037ae4  mov     rdi, [rcx+88h]
0x180037aeb  test    rdi, rdi
0x180037aee  jz      loc_180038059
0x180037af4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180037afb  nop     dword ptr [rax+rax+00h]
0x180037b00  lea     rax, [rax+1]
0x180037b04  cmp     word ptr [rdi+rax*2], 0
0x180037b09  jnz     short loc_180037B00
0x180037b0b  lea     r12, [rax+1]
0x180037b0f  mov     rbx, r15
0x180037b12  test    rbx, rbx
0x180037b15  jz      short loc_180037B1F
0x180037b17  movzx   ecx, word ptr [rbx]
0x180037b1a  test    cx, cx
0x180037b1d  jnz     short loc_180037B6D
0x180037b1f  cmp     r12, 104h
0x180037b26  jb      short loc_180037B8C
0x180037b28  mov     rcx, [rbp+250h+pv]; pv
0x180037b2f  test    rcx, rcx
0x180037b32  jz      short loc_180037B40
0x180037b34  call    cs:__imp_CoTaskMemFree
0x180037b3b  nop     dword ptr [rax+rax+00h]
0x180037b40  xor     eax, eax
0x180037b42  mov     rcx, [rbp+250h+var_40]
0x180037b49  xor     rcx, rsp; StackCookie
0x180037b4c  call    __security_check_cookie
0x180037b51  mov     rbx, [rsp+350h+arg_18]
0x180037b59  add     rsp, 320h
0x180037b60  pop     r15
0x180037b62  pop     r14
0x180037b64  pop     r13
0x180037b66  pop     r12
0x180037b68  pop     rdi
0x180037b69  pop     rsi
0x180037b6a  pop     rbp
0x180037b6b  retn
0x180037b6d  cmp     ecx, 0Bh
0x180037b70  jbe     loc_180037F02
0x180037b76  movzx   eax, byte ptr [rbx+2]
0x180037b7a  and     al, 70h
0x180037b7c  cmp     al, 30h ; '0'
0x180037b7e  jnz     loc_180038139
0x180037b84  mov     rsi, rbx
0x180037b87  jmp     loc_180037E21
0x180037b8c  mov     rbx, r14
0x180037b8f  mov     [rbp+250h+ppMalloc], r14
0x180037b96  mov     eax, 2
0x180037b9b  mul     r12
0x180037b9e  test    rdx, rdx
0x180037ba1  jnz     loc_180037FFC
0x180037ba7  mov     rcx, rax; cb
0x180037baa  call    cs:__imp_CoTaskMemAlloc
0x180037bb1  nop     dword ptr [rax+rax+00h]
0x180037bb6  mov     rbx, rax
0x180037bb9  mov     [rsp+350h+var_308], rax
0x180037bbe  test    rax, rax
0x180037bc1  jz      loc_1800383B1
0x180037bc7  mov     rsi, r14
0x180037bca  mov     [rbp+250h+ppMalloc], r14
0x180037bd1  lea     rdx, [rbp+250h+ppMalloc]; ppMalloc
0x180037bd8  mov     ecx, 1; dwMemContext
0x180037bdd  call    cs:__imp_CoGetMalloc
0x180037be4  nop     dword ptr [rax+rax+00h]
0x180037be9  test    eax, eax
0x180037beb  js      short loc_180037C19
0x180037bed  mov     rcx, [rbp+250h+ppMalloc]
0x180037bf4  mov     rax, [rcx]
0x180037bf7  mov     rdx, rbx
0x180037bfa  mov     rax, [rax+30h]
0x180037bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c03  mov     rsi, rax
0x180037c06  mov     rcx, [rbp+250h+ppMalloc]
0x180037c0d  mov     rdx, [rcx]
0x180037c10  mov     rax, [rdx+10h]
0x180037c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c19  mov     r8, rsi; Size
0x180037c1c  xor     edx, edx; Val
0x180037c1e  mov     rcx, rbx; void *
0x180037c21  call    memset_0
0x180037c26  mov     esi, r14d
0x180037c29  mov     r14, rbx
0x180037c2c  test    esi, esi
0x180037c2e  js      loc_180038001
0x180037c34  xor     r9d, r9d; dwFlags
0x180037c37  mov     r8, rdi; pszPathIn
0x180037c3a  mov     rdx, r12; cchPathOut
0x180037c3d  mov     rcx, rbx; pszPathOut
0x180037c40  call    cs:__imp_PathCchCanonicalizeEx
0x180037c47  nop     dword ptr [rax+rax+00h]
0x180037c4c  mov     edi, eax
0x180037c4e  test    eax, eax
0x180037c50  js      loc_1800383BB
0x180037c56  test    r15, r15
0x180037c59  jz      loc_180037D9C
0x180037c5f  cmp     word ptr [r15], 0
0x180037c64  jz      loc_180037D9C
0x180037c6a  lea     rdx, [r13-138h]; struct CFSFolder *
0x180037c71  xor     r9d, r9d; struct IDFOLDER *
0x180037c74  mov     r8, r15; struct _ITEMIDLIST_RELATIVE *
0x180037c77  lea     rcx, [rsp+350h+var_300]; this
0x180037c7c  call    ??0CFileSysItemString@@QEAA@PEAVCFSFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEFBUIDFOLDER@@@Z; CFileSysItemString::CFileSysItemString(CFSFolder *,_ITEMIDLIST_RELATIVE const *,IDFOLDER const *)
0x180037c81  xorps   xmm0, xmm0
0x180037c84  movups  xmmword ptr [rsp+350h+pwszDst], xmm0
0x180037c89  movups  xmmword ptr [rsp+350h+pwszDst+0Ah], xmm0
0x180037c8e  mov     r8, [rbp+250h+var_2B0]; unsigned __int64 *
0x180037c92  movzx   eax, byte ptr [r8+2]
0x180037c97  and     al, 34h
0x180037c99  xor     r9d, r9d
0x180037c9c  cmp     al, 34h ; '4'
0x180037c9e  jz      loc_180037DA9
0x180037ca4  cmp     [rbp+250h+var_2A8], r9
0x180037ca8  jz      loc_180038454
0x180037cae  mov     ecx, r9d
0x180037cb1  add     rcx, 0Eh
0x180037cb5  add     rcx, r8; pszSrc
0x180037cb8  mov     r8d, 0Dh; cwchBuf
0x180037cbe  lea     rdx, [rsp+350h+pwszDst]; pwszDst
0x180037cc3  call    cs:__imp_SHAnsiToUnicode
0x180037cca  nop     dword ptr [rax+rax+00h]
0x180037ccf  xor     r9d, r9d; dwFlags
0x180037cd2  lea     r8, [rsp+350h+pwszDst]; pszMore
0x180037cd7  mov     rdx, r12; cchPath
0x180037cda  mov     rcx, rbx; pszPath
0x180037cdd  call    cs:__imp_PathCchAppendEx
0x180037ce4  nop     dword ptr [rax+rax+00h]
0x180037ce9  mov     edi, eax
0x180037ceb  test    eax, eax
0x180037ced  js      loc_1800384E6
0x180037cf3  lea     rax, ??_7CFileSysItemString@@6B@; const CFileSysItemString::`vftable'
0x180037cfa  mov     [rsp+350h+var_300], rax
0x180037cff  mov     rcx, [rbp+250h+var_2B8]
0x180037d03  mov     [rbp+250h+var_2B8], 0
0x180037d0b  test    rcx, rcx
0x180037d0e  jz      short loc_180037D1C
0x180037d10  mov     rax, [rcx]
0x180037d13  mov     rax, [rax+10h]
0x180037d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037d1c  mov     rcx, [rbp+250h+var_2C8]
0x180037d20  mov     [rbp+250h+var_2C8], 0
0x180037d28  test    rcx, rcx
0x180037d2b  jnz     loc_180037E07
0x180037d31  mov     rcx, [rbp+250h+var_2C0]
0x180037d35  mov     [rbp+250h+var_2C0], 0
0x180037d3d  test    rcx, rcx
0x180037d40  jz      short loc_180037D4E
0x180037d42  mov     rax, [rcx]
0x180037d45  mov     rax, [rax+10h]
0x180037d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037d4e  mov     rcx, [rbp+250h+var_2D0]; pv
0x180037d52  test    rcx, rcx
0x180037d55  jz      short loc_180037D63
0x180037d57  call    cs:__imp_CoTaskMemFree
0x180037d5e  nop     dword ptr [rax+rax+00h]
0x180037d63  mov     rcx, [rsp+350h+var_2E8]; pv
0x180037d68  test    rcx, rcx
0x180037d6b  jz      short loc_180037D79
0x180037d6d  call    cs:__imp_CoTaskMemFree
0x180037d74  nop     dword ptr [rax+rax+00h]
0x180037d79  mov     rcx, [rsp+350h+var_2F0]; pv
0x180037d7e  test    rcx, rcx
0x180037d81  jz      short loc_180037D90
0x180037d83  call    cs:__imp_CoTaskMemFree
0x180037d8a  nop     dword ptr [rax+rax+00h]
0x180037d8f  nop
0x180037d90  movzx   eax, word ptr [r15]
0x180037d94  add     r15, rax
0x180037d97  jmp     loc_180037C56
0x180037d9c  mov     rax, qword ptr [rsp+350h+var_330]
0x180037da1  mov     [rax], rbx
0x180037da4  jmp     loc_180037B28
0x180037da9  cmp     [rbp+250h+var_2A8], r9
0x180037dad  jz      loc_1806603C4
0x180037db3  mov     ecx, 7FFFFFFEh
0x180037db8  mov     eax, r9d
0x180037dbb  lea     rdx, [r8+0Eh]
0x180037dbf  add     rdx, rax
0x180037dc2  mov     r9d, 0Dh
0x180037dc8  lea     r8, [rsp+350h+pwszDst]
0x180037dcd  nop     dword ptr [rax]
0x180037dd0  test    rcx, rcx
0x180037dd3  jz      short loc_180037DF2
0x180037dd5  movzx   eax, word ptr [rdx]
0x180037dd8  test    ax, ax
0x180037ddb  jz      short loc_180037DF2
0x180037ddd  add     rdx, 2
0x180037de1  mov     [r8], ax
0x180037de5  add     r8, 2
0x180037de9  dec     rcx
0x180037dec  sub     r9, 1
0x180037df0  jnz     short loc_180037DD0
0x180037df2  lea     rcx, [r8-2]
0x180037df6  test    r9, r9
0x180037df9  cmovnz  rcx, r8
0x180037dfd  xor     eax, eax
0x180037dff  mov     [rcx], ax
0x180037e02  jmp     loc_180037CCF
0x180037e07  mov     rax, [rcx]
0x180037e0a  mov     rax, [rax+10h]
0x180037e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037e13  jmp     loc_180037D31
0x180037e18  test    rsi, rsi
0x180037e1b  jz      loc_180037F02
0x180037e21  cmp     word ptr [rsi], 0Eh
0x180037e25  jb      loc_180037F02
0x180037e2b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow> `wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl(void)'::`2'::impl
0x180037e32  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(void)
0x180037e37  movzx   r8d, word ptr [rbx]
0x180037e3b  test    al, al
0x180037e3d  jnz     loc_1800384D6
0x180037e43  movzx   r9d, r8w
0x180037e47  mov     rdx, r14
0x180037e4a  movzx   ecx, r8w
0x180037e4e  movzx   r10d, word ptr [rcx+rbx-2]
0x180037e54  test    r10w, r10w
0x180037e58  jz      short loc_180037E99
0x180037e5a  lea     rax, [r10+8]
0x180037e5e  cmp     rax, rcx
0x180037e61  jnb     short loc_180037E99
0x180037e63  lea     rdx, [r10+rbx]
0x180037e67  movzx   ecx, word ptr [rdx]
0x180037e6a  cmp     ecx, 8
0x180037e6d  jb      loc_180038051
0x180037e73  mov     eax, [rdx+4]
0x180037e76  shr     rax, 10h
0x180037e7a  mov     r11d, 0BEEFh
0x180037e80  cmp     ax, r11w
0x180037e84  jnz     loc_180038051
0x180037e8a  add     ecx, r10d
0x180037e8d  movzx   eax, r8w
0x180037e91  cmp     ecx, eax
0x180037e93  ja      loc_180038051
0x180037e99  movzx   ecx, r9w
0x180037e9d  add     rcx, rbx
0x180037ea0  test    rdx, rdx
0x180037ea3  jz      loc_180037F7E
0x180037ea9  cmp     dword ptr [rdx+4], 0BEEF0004h
0x180037eb0  jnz     loc_180037FD9
0x180037eb6  lea     rcx, [rsi+0Eh]
0x180037eba  test    rcx, rcx
0x180037ebd  jz      loc_1800384C2
0x180037ec3  movzx   edx, word ptr [rsi]
0x180037ec6  add     rdx, 0FFFFFFFFFFFFFFF2h
0x180037eca  cmp     rdx, 7FFFFFFFh
0x180037ed1  ja      loc_1800384C2
0x180037ed7  test    rdx, rdx
0x180037eda  jz      short loc_180037EEE
0x180037edc  nop     dword ptr [rax+00h]
0x180037ee0  cmp     byte ptr [rcx], 0
0x180037ee3  jz      short loc_180037EEE
0x180037ee5  inc     rcx
0x180037ee8  sub     rdx, 1
0x180037eec  jnz     short loc_180037EE0
0x180037eee  mov     ecx, 80070057h
0x180037ef3  test    rdx, rdx
0x180037ef6  cmovnz  ecx, r14d
0x180037efa  test    ecx, ecx
0x180037efc  jns     loc_1800381C2
0x180037f02  mov     rcx, [rbp+258h]; this
0x180037f09  mov     r9d, 80070057h; char *
0x180037f0f  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x180037f16  mov     edx, 458h; void *
0x180037f1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037f20  nop
0x180037f21  mov     rcx, [rbp+250h+pv]; pv
0x180037f28  test    rcx, rcx
0x180037f2b  jz      short loc_180037F39
0x180037f2d  call    cs:__imp_CoTaskMemFree
0x180037f34  nop     dword ptr [rax+rax+00h]
0x180037f39  mov     eax, 80070057h
0x180037f3e  jmp     loc_180037B42
0x180037f43  lea     rax, [r9+8]
0x180037f47  cmp     rax, rcx
0x180037f4a  ja      short loc_180037F7E
0x180037f4c  mov     eax, [r9+4]
0x180037f50  shr     rax, 10h
0x180037f54  mov     edx, 0BEEFh
0x180037f59  cmp     ax, dx
0x180037f5c  jnz     short loc_180037F7E
  ... truncated ...
```
