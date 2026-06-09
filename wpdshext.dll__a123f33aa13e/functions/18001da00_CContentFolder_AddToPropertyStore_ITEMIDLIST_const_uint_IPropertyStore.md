# CContentFolder::_AddToPropertyStore(_ITEMIDLIST const *,uint,IPropertyStore *)

- ea: `0x18001da00`
- end: `0x18001e5b5`
- name: `?_AddToPropertyStore@CContentFolder@@EEAAJPEFBU_ITEMIDLIST@@IPEAUIPropertyStore@@@Z`
- size: `2997`
- prototype: `__int64 __fastcall(CContentFolder *__hidden this, const struct _ITEMIDLIST *, unsigned int, struct IPropertyStore *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task`

## callees

- `0x1800082e0`
- `0x18001da00`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x18007559c`
- `0x1800755a8`
- `0x180078010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18001db1d`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18001e06c`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18001db1d`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18001e06c`
- `SHLWAPI!PathFindFileNameW` at `0x18001dae8`
- `SHLWAPI!PathFindFileNameW` at `0x18001dc38`
- `SHLWAPI!PathFindFileNameW` at `0x18001ddaa`
- `SHLWAPI!PathFindFileNameW` at `0x18001dae8`
- `SHLWAPI!PathFindFileNameW` at `0x18001dc38`
- `SHLWAPI!PathFindFileNameW` at `0x18001ddaa`
- `ole32!CoTaskMemAlloc` at `0x18001db57`
- `ole32!CoTaskMemAlloc` at `0x18001dcc7`
- `ole32!CoTaskMemAlloc` at `0x18001de47`
- `ole32!CoTaskMemAlloc` at `0x18001db57`
- `ole32!CoTaskMemAlloc` at `0x18001dcc7`
- `ole32!CoTaskMemAlloc` at `0x18001de47`
- `ole32!PropVariantClear` at `0x18001db28`
- `ole32!PropVariantClear` at `0x18001dc96`
- `ole32!PropVariantClear` at `0x18001de15`
- `ole32!PropVariantClear` at `0x18001deb0`
- `ole32!PropVariantClear` at `0x18001defe`
- `ole32!PropVariantClear` at `0x18001dfbe`
- `ole32!PropVariantClear` at `0x18001e0e8`
- `ole32!PropVariantClear` at `0x18001e2c4`
- `ole32!PropVariantClear` at `0x18001e32d`
- `ole32!PropVariantClear` at `0x18001e396`
- `ole32!PropVariantClear` at `0x18001e3ff`
- `ole32!PropVariantClear` at `0x18001e468`
- `ole32!PropVariantClear` at `0x18001db28`
- `ole32!PropVariantClear` at `0x18001dc96`
- `ole32!PropVariantClear` at `0x18001de15`
- `ole32!PropVariantClear` at `0x18001deb0`
- `ole32!PropVariantClear` at `0x18001defe`
- `ole32!PropVariantClear` at `0x18001dfbe`
- `ole32!PropVariantClear` at `0x18001e0e8`
- `ole32!PropVariantClear` at `0x18001e2c4`
- `ole32!PropVariantClear` at `0x18001e32d`
- `ole32!PropVariantClear` at `0x18001e396`
- `ole32!PropVariantClear` at `0x18001e3ff`
- `ole32!PropVariantClear` at `0x18001e468`
- `PROPSYS!InitPropVariantFromFileTime` at `0x18001e0f7`
- `PROPSYS!InitPropVariantFromFileTime` at `0x18001e0f7`
- `SHELL32!SHGetFileInfoW` at `0x18001ddc7`
- `SHELL32!SHGetFileInfoW` at `0x18001ddc7`
- `SHELL32!SHGetSettings` at `0x18001dbc7`
- `SHELL32!SHGetSettings` at `0x18001dbc7`

## pseudocode

```c
__int64 __fastcall CContentFolder::_AddToPropertyStore(
        CContentFolder *this,
        const struct _ITEMIDLIST *a2,
        int a3,
        struct IPropertyStore *a4)
{
  const struct CONTENTITEM *v6; // rax
  const struct CONTENTITEM *v7; // r14
  __int64 v8; // rdi
  __int64 v9; // rsi
  const struct CONTENTITEM *v10; // rdx
  __int64 v11; // rcx
  WCHAR *v12; // r8
  WCHAR *v13; // rdx
  __int64 v14; // r9
  WCHAR *v15; // rcx
  __int64 v16; // rax
  bool v17; // zf
  SIZE_T v18; // rbx
  void *v19; // rcx
  int v20; // eax
  unsigned int v21; // ebx
  int v22; // ebx
  const struct CONTENTITEM *v23; // rdx
  __int64 v24; // rcx
  WCHAR *v25; // r8
  WCHAR *v26; // rdx
  __int64 v27; // r9
  WCHAR *v28; // rcx
  __int64 v29; // rcx
  WCHAR *v30; // rdx
  __int64 v31; // r9
  wchar_t *v32; // r8
  wchar_t *v33; // rcx
  __int64 v34; // rax
  SIZE_T v35; // rbx
  void *v36; // rax
  int v37; // eax
  DWORD v38; // ebx
  const struct CONTENTITEM *v39; // rdx
  __int64 v40; // rcx
  WCHAR *v41; // r8
  WCHAR *v42; // rdx
  __int64 v43; // r10
  WCHAR *v44; // rcx
  const WCHAR *FileNameW; // rax
  WCHAR *szTypeName; // rcx
  wchar_t *v47; // rdx
  wchar_t *v48; // rcx
  __int64 v49; // rax
  SIZE_T v50; // rbx
  void *v51; // rax
  int v52; // eax
  struct IPropertyStoreVtbl *lpVtbl; // rax
  int v54; // eax
  int v55; // eax
  struct IPropertyStoreVtbl *v57; // rax
  int v58; // eax
  PVOID *v59; // rcx
  __int64 v60; // rdx
  __int64 v61; // r9
  __int64 v62; // rax
  WCHAR *v63; // rcx
  __int64 v64; // r9
  wchar_t *v65; // rdx
  struct IPropertyStoreVtbl *v66; // rax
  int v67; // eax
  struct IPropertyStoreVtbl *v68; // rax
  int v69; // eax
  struct IPropertyStoreVtbl *v70; // rax
  int v71; // eax
  struct IPropertyStoreVtbl *v72; // rax
  int v73; // eax
  struct IPropertyStoreVtbl *v74; // rax
  int v75; // eax
  int v76; // eax
  PROPVARIANT pvar; // [rsp+50h] [rbp-B0h] BYREF
  SHELLFLAGSTATE psfs; // [rsp+68h] [rbp-98h] BYREF
  PROPVARIANT Buf1; // [rsp+70h] [rbp-90h] BYREF
  SHFILEINFOW psfi; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Src[264]; // [rsp+350h] [rbp+250h] BYREF
  WCHAR pszPath[264]; // [rsp+560h] [rbp+460h] BYREF
  WCHAR Filename[264]; // [rsp+770h] [rbp+670h] BYREF

  memset(&pvar, 0, sizeof(pvar));
  if ( a2 )
  {
    if ( a4 )
    {
      v6 = CContentFolder::_IsValid(this, a2);
      v7 = v6;
      if ( v6 )
      {
        if ( !a3 )
        {
          v8 = 2147483646;
          v9 = 260;
          if ( (*((_BYTE *)v6 + 10) & 2) == 0 )
          {
            if ( *(_DWORD *)((char *)v6 + 66) <= 1u )
              v10 = v6;
            else
              v10 = (const struct CONTENTITEM *)((char *)v6 + 2 * *(unsigned int *)((char *)v6 + 62));
            v11 = 2147483646;
            v12 = pszPath;
            v13 = (WCHAR *)((char *)v10 + 74);
            v14 = 260;
            do
            {
              if ( !v11 )
                break;
              if ( !*v13 )
                break;
              *v12++ = *v13++;
              --v11;
              --v14;
            }
            while ( v14 );
            v15 = v12 - 1;
            if ( v14 )
              v15 = v12;
            *v15 = 0;
            PathFindFileNameW(pszPath);
            _wsplitpath_s(pszPath, 0, 0, 0, 0, 0, 0, Src, 0x104u);
            PropVariantClear(&pvar);
            v16 = -1;
            do
              v17 = Src[++v16] == 0;
            while ( !v17 );
            v18 = 2 * v16 + 2;
            v19 = CoTaskMemAlloc(v18);
            pvar.hVal.QuadPart = (LONGLONG)v19;
            if ( !v19 )
            {
              memset(&pvar, 0, sizeof(pvar));
              v21 = -2147024882;
              v59 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                return v21;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                goto LABEL_148;
              v60 = 286;
LABEL_145:
              v61 = 2147942414LL;
LABEL_146:
              WPP_SF_d(v59[2], v60, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v61);
              goto LABEL_147;
            }
            if ( v18 )
              memcpy_0(v19, Src, v18);
            pvar.vt = 31;
            v20 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a4->lpVtbl->SetValue)(
                    a4,
                    &PKEY_ItemType,
                    &pvar);
            v21 = v20;
            if ( v20 < 0 )
            {
              v59 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                return v21;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                goto LABEL_148;
              v60 = 287;
              v61 = (unsigned int)v20;
              goto LABEL_146;
            }
          }
          psfs = 0;
          SHGetSettings(&psfs, 2u);
          v22 = (int)(*(_DWORD *)&psfs << 30) >> 31;
          if ( *(_DWORD *)((char *)v7 + 66) <= 1u )
            v23 = v7;
          else
            v23 = (const struct CONTENTITEM *)((char *)v7 + 2 * *(unsigned int *)((char *)v7 + 62));
          v24 = 2147483646;
          v25 = pszPath;
          v26 = (WCHAR *)((char *)v23 + 74);
          v27 = 260;
          do
          {
            if ( !v24 )
              break;
            if ( !*v26 )
              break;
            *v25++ = *v26++;
            --v24;
            --v27;
          }
          while ( v27 );
          v28 = v25 - 1;
          if ( v27 )
            v28 = v25;
          *v28 = 0;
          PathFindFileNameW(pszPath);
          if ( v22 || (*((_BYTE *)v7 + 10) & 2) != 0 )
          {
            v29 = 2147483646;
            v30 = pszPath;
            v31 = 260;
            v32 = Src;
            do
            {
              if ( !v29 )
                break;
              if ( !*v30 )
                break;
              *v32++ = *v30++;
              --v29;
              --v31;
            }
            while ( v31 );
            v33 = v32 - 1;
            if ( v31 )
              v33 = v32;
          }
          else
          {
            _wsplitpath_s(pszPath, 0, 0, 0, 0, Filename, 0x104u, (wchar_t *)&psfi, 0x104u);
            v62 = 2147483646;
            v63 = Filename;
            v64 = 260;
            v65 = Src;
            do
            {
              if ( !v62 )
                break;
              if ( !*v63 )
                break;
              *v65++ = *v63++;
              --v62;
              --v64;
            }
            while ( v64 );
            v33 = v65 - 1;
            if ( v64 )
              v33 = v65;
          }
          *v33 = 0;
          PropVariantClear(&pvar);
          v34 = -1;
          do
            v17 = Src[++v34] == 0;
          while ( !v17 );
          v35 = 2 * v34 + 2;
          v36 = CoTaskMemAlloc(v35);
          pvar.hVal.QuadPart = (LONGLONG)v36;
          if ( v36 )
          {
            if ( v35 )
              memcpy_0(v36, Src, v35);
            pvar.vt = 31;
            v37 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a4->lpVtbl->SetValue)(
                    a4,
                    &PKEY_ItemNameDisplay,
                    &pvar);
            v21 = v37;
            if ( v37 < 0 )
            {
              v59 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                return v21;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                goto LABEL_148;
              v60 = 289;
              v61 = (unsigned int)v37;
              goto LABEL_146;
            }
            Src[0] = 0;
            memset_0(&psfi, 0, sizeof(psfi));
            v38 = 8 * (*(_DWORD *)((_BYTE *)v7 + 10) & 2);
            if ( *(_DWORD *)((char *)v7 + 66) <= 1u )
              v39 = v7;
            else
              v39 = (const struct CONTENTITEM *)((char *)v7 + 2 * *(unsigned int *)((char *)v7 + 62));
            v40 = 2147483646;
            v41 = Filename;
            v42 = (WCHAR *)((char *)v39 + 74);
            v43 = 260;
            do
            {
              if ( !v40 )
                break;
              if ( !*v42 )
                break;
              *v41++ = *v42++;
              --v40;
              --v43;
            }
            while ( v43 );
            v44 = v41 - 1;
            if ( v43 )
              v44 = v41;
            *v44 = 0;
            FileNameW = PathFindFileNameW(Filename);
            if ( (unsigned int)SHGetFileInfoW(FileNameW, v38, &psfi, 0x2B8u, 0x410u) )
            {
              szTypeName = psfi.szTypeName;
              v47 = Src;
              do
              {
                if ( !v8 )
                  break;
                if ( !*szTypeName )
                  break;
                *v47++ = *szTypeName++;
                --v8;
                --v9;
              }
              while ( v9 );
              v48 = v47 - 1;
              if ( v9 )
                v48 = v47;
              *v48 = 0;
            }
            PropVariantClear(&pvar);
            v49 = -1;
            do
              v17 = Src[++v49] == 0;
            while ( !v17 );
            v50 = 2 * v49 + 2;
            v51 = CoTaskMemAlloc(v50);
            pvar.hVal.QuadPart = (LONGLONG)v51;
            if ( v51 )
            {
              if ( v50 )
                memcpy_0(v51, Src, v50);
              pvar.vt = 31;
              v52 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a4->lpVtbl->SetValue)(
                      a4,
                      &PKEY_ItemTypeText,
                      &pvar);
              v21 = v52;
              if ( v52 < 0 )
              {
                v59 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                  return v21;
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                  goto LABEL_148;
                v60 = 291;
                v61 = (unsigned int)v52;
              }
              else
              {
                PropVariantClear(&pvar);
                pvar.lVal = *(_DWORD *)((char *)v7 + 10);
                lpVtbl = a4->lpVtbl;
                pvar.vt = 19;
                v54 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))lpVtbl->SetValue)(
                        a4,
                        &PKEY_WPDNSE_Attributes,
                        &pvar);
                v21 = v54;
                if ( v54 < 0 )
                {
                  v59 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                    return v21;
                  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                    goto LABEL_148;
                  v60 = 293;
                  v61 = (unsigned int)v54;
                }
                else
                {
                  if ( (*((_BYTE *)v7 + 10) & 2) != 0 )
                    goto LABEL_153;
                  PropVariantClear(&pvar);
                  v17 = (*((_BYTE *)v7 + 14) & 2) == 0;
                  pvar.vt = 11;
                  pvar.iVal = -1;
                  if ( v17 )
                    pvar.iVal = 0;
                  v55 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))a4->lpVtbl->SetValue)(
                          a4,
                          &PKEY_WPDNSE_IsSupported,
                          &pvar);
                  v21 = v55;
                  if ( v55 >= 0 )
                  {
LABEL_153:
                    if ( (*(_DWORD *)((_BYTE *)v7 + 14) & 0x10000) != 0
                      && (PropVariantClear(&pvar),
                          v68 = a4->lpVtbl,
                          pvar.vt = 11,
                          pvar.iVal = -1,
                          v69 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v68->SetValue)(
                                  a4,
                                  &WPDNSE_OBJECT_HAS_CONTACT_PHOTO,
                                  &pvar),
                          v21 = v69,
                          v69 < 0) )
                    {
                      v59 = (PVOID *)WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                        return v21;
                      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                        goto LABEL_148;
                      v60 = 296;
                      v61 = (unsigned int)v69;
                    }
                    else if ( (*(_DWORD *)((_BYTE *)v7 + 14) & 0x20000) != 0
                           && (PropVariantClear(&pvar),
                               v57 = a4->lpVtbl,
                               pvar.vt = 11,
                               pvar.iVal = -1,
                               v58 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v57->SetValue)(
                                       a4,
                                       &WPDNSE_OBJECT_HAS_THUMBNAIL,
                                       &pvar),
                               v21 = v58,
                               v58 < 0) )
                    {
                      v59 = (PVOID *)WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                        return v21;
                      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                        goto LABEL_148;
                      v60 = 297;
                      v61 = (unsigned int)v58;
                    }
                    else if ( (*(_DWORD *)((_BYTE *)v7 + 14) & 0x40000) != 0
                           && (PropVariantClear(&pvar),
                               v70 = a4->lpVtbl,
                               pvar.vt = 11,
                               pvar.iVal = -1,
                               v71 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v70->SetValue)(
                                       a4,
                                       &WPDNSE_OBJECT_HAS_ICON,
                                       &pvar),
                               v21 = v71,
                               v71 < 0) )
                    {
                      v59 = (PVOID *)WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                        return v21;
                      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                        goto LABEL_148;
                      v60 = 298;
                      v61 = (unsigned int)v71;
                    }
                    else if ( (*(_DWORD *)((_BYTE *)v7 + 14) & 0x80000) != 0
                           && (PropVariantClear(&pvar),
                               v72 = a4->lpVtbl,
                               pvar.vt = 11,
                               pvar.iVal = -1,
                               v73 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v72->SetValue)(
                                       a4,
                                       &WPDNSE_OBJECT_HAS_AUDIO_CLIP,
                                       &pvar),
                               v21 = v73,
                               v73 < 0) )
                    {
                      v59 = (PVOID *)WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                        return v21;
                      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                        goto LABEL_148;
                      v60 = 299;
                      v61 = (unsigned int)v73;
                    }
                    else if ( (*(_DWORD *)((_BYTE *)v7 + 14) & 0x100000) != 0
                           && (PropVariantClear(&pvar),
                               v74 = a4->lpVtbl,
                               pvar.vt = 11,
                               pvar.iVal = -1,
                               v75 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v74->SetValue)(
                                       a4,
                                       &WPDNSE_OBJECT_HAS_CONTACT_PHOTO,
                                       &pvar),
                               v21 = v75,
                               v75 < 0) )
                    {
                      v59 = (PVOID *)WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                        return v21;
                      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                        goto LABEL_148;
                      v60 = 300;
                      v61 = (unsigned int)v75;
                    }
                    else
                    {
                      if ( !*(_QWORD *)((char *)v7 + 26) )
                        return v21;
                      *(_OWORD *)&Buf1.vt = *(_OWORD *)((char *)v7 + 42);
                      if ( memcmp_0(&Buf1, &WPD_CONTENT_TYPE_IMAGE, 0x10u) )
                        return v21;
                      PropVariantClear(&pvar);
                      InitPropVariantFromFileTime((const FILETIME *)((char *)v7 + 26), &pvar);
                      v66 = a4->lpVtbl;
                      memset(&Buf1, 0, sizeof(Buf1));
                      if ( ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v66->GetValue)(
                             a4,
                             &WPD_OBJECT_DATE_AUTHORED,
                             &Buf1) < 0
                        || Buf1.vt
                        || (v67 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a4->lpVtbl->SetValue)(
                                    a4,
                                    &PKEY_Photo_DateTaken,
                                    &pvar),
                            v21 = v67,
                            v67 >= 0) )
                      {
                        PropVariantClear(&Buf1);
                        v76 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a4->lpVtbl->SetValue)(
                                a4,
                                &PKEY_Media_DateEncoded,
                                &pvar);
                        v21 = v76;
                        if ( v76 >= 0 )
                          return v21;
                        v59 = (PVOID *)WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                          return v21;
                        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                          goto LABEL_148;
                        v60 = 302;
                        v61 = (unsigned int)v76;
                      }
                      else
                      {
                        v59 = (PVOID *)WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                          return v21;
                        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                          goto LABEL_148;
                        v60 = 301;
                        v61 = (unsigned int)v67;
                      }
                    }
                  }
                  else
                  {
                    v59 = (PVOID *)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                      return v21;
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                      goto LABEL_148;
                    v60 = 295;
                    v61 = (unsigned int)v55;
                  }
                }
              }
              goto LABEL_146;
            }
            memset(&pvar, 0, sizeof(pvar));
            v21 = -2147024882;
            v59 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return v21;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_148;
            v60 = 290;
          }
          else
          {
            memset(&pvar, 0, sizeof(pvar));
            v21 = -2147024882;
            v59 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return v21;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_148;
            v60 = 288;
          }
          goto LABEL_145;
        }
        v21 = -2147024809;
      }
      else
      {
        v21 = -2147024809;
      }
    }
    else
    {
      v21 = -2147024809;
    }
  }
  else
  {
    v21 = -2147024809;
  }
LABEL_147:
  v59 = (PVOID *)WPP_GLOBAL_Control;
LABEL_148:
  if ( v59 != &WPP_GLOBAL_Control && (*((_BYTE *)v59 + 28) & 2) != 0 )
    WPP_SF_d(v59[2], 303, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v21);
  return v21;
}

```

## disassembly

```asm
0x18001da00  mov     [rsp-8+arg_0], rbx
0x18001da05  push    rbp
0x18001da06  push    rsi
0x18001da07  push    rdi
0x18001da08  push    r12
0x18001da0a  push    r13
0x18001da0c  push    r14
0x18001da0e  push    r15
0x18001da10  lea     rbp, [rsp-890h]
0x18001da18  sub     rsp, 990h
0x18001da1f  mov     rax, cs:__security_cookie
0x18001da26  xor     rax, rsp
0x18001da29  mov     [rbp+8C0h+var_40], rax
0x18001da30  xor     eax, eax
0x18001da32  xorps   xmm0, xmm0
0x18001da35  mov     qword ptr [rsp+9C0h+pvar+10h], rax
0x18001da3a  mov     r15, r9
0x18001da3d  mov     ebx, r8d
0x18001da40  movups  xmmword ptr [rsp+9C0h+pvar], xmm0
0x18001da45  test    rdx, rdx
0x18001da48  jz      loc_18001E195
0x18001da4e  test    r9, r9
0x18001da51  jz      loc_18001E1A6
0x18001da57  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x18001da5c  mov     r14, rax
0x18001da5f  test    rax, rax
0x18001da62  jz      loc_18001E1B7
0x18001da68  test    ebx, ebx
0x18001da6a  jnz     loc_18001E1C8
0x18001da70  xor     r12d, r12d
0x18001da73  mov     edi, 7FFFFFFEh
0x18001da78  test    byte ptr [rax+0Ah], 2
0x18001da7c  mov     esi, 104h
0x18001da81  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18001da88  jnz     loc_18001DBB8
0x18001da8e  cmp     dword ptr [rax+42h], 1
0x18001da92  jbe     loc_18001E18D
0x18001da98  mov     eax, [rax+3Eh]
0x18001da9b  lea     rdx, [r14+rax*2]
0x18001da9f  mov     rcx, rdi
0x18001daa2  lea     r8, [rbp+8C0h+pszPath]
0x18001daa9  add     rdx, 4Ah ; 'J'
0x18001daad  mov     r9, rsi
0x18001dab0  test    rcx, rcx
0x18001dab3  jz      short loc_18001DAD2
0x18001dab5  movzx   eax, word ptr [rdx]
0x18001dab8  test    ax, ax
0x18001dabb  jz      short loc_18001DAD2
0x18001dabd  mov     [r8], ax
0x18001dac1  add     rdx, 2
0x18001dac5  add     r8, 2
0x18001dac9  dec     rcx
0x18001dacc  sub     r9, 1
0x18001dad0  jnz     short loc_18001DAB0
0x18001dad2  test    r9, r9
0x18001dad5  lea     rcx, [r8-2]
0x18001dad9  cmovnz  rcx, r8
0x18001dadd  mov     [rcx], r12w
0x18001dae1  lea     rcx, [rbp+8C0h+pszPath]; pszPath
0x18001dae8  call    cs:__imp_PathFindFileNameW
0x18001daee  mov     [rsp+9C0h+ExtCount], rsi; ExtCount
0x18001daf3  lea     rax, [rbp+8C0h+Src]
0x18001dafa  mov     [rsp+9C0h+Ext], rax; Ext
0x18001daff  lea     rcx, [rbp+8C0h+pszPath]; FullPath
0x18001db06  mov     [rsp+9C0h+FilenameCount], r12; FilenameCount
0x18001db0b  xor     r9d, r9d; Dir
0x18001db0e  mov     [rsp+9C0h+Filename], r12; Filename
0x18001db13  xor     r8d, r8d; DriveCount
0x18001db16  xor     edx, edx; Drive
0x18001db18  mov     [rsp+9C0h+DirCount], r12; DirCount
0x18001db1d  call    cs:__imp__wsplitpath_s
0x18001db23  lea     rcx, [rsp+9C0h+pvar]; pvar
0x18001db28  call    cs:__imp_PropVariantClear
0x18001db2e  lea     rcx, [rbp+8C0h+Src]
0x18001db35  mov     rax, r13
0x18001db38  nop     dword ptr [rax+rax+00000000h]
0x18001db40  cmp     [rcx+rax*2+2], r12w
0x18001db46  lea     rax, [rax+1]
0x18001db4a  jnz     short loc_18001DB40
0x18001db4c  lea     rbx, ds:2[rax*2]
0x18001db54  mov     rcx, rbx; cb
0x18001db57  call    cs:__imp_CoTaskMemAlloc
0x18001db5d  mov     rcx, rax; void *
0x18001db60  sar     rax, 20h
0x18001db64  mov     dword ptr [rsp+9C0h+pvar+8], ecx
0x18001db68  mov     dword ptr [rsp+9C0h+pvar+0Ch], eax
0x18001db6c  test    rcx, rcx
0x18001db6f  jz      loc_18001E535
0x18001db75  test    rbx, rbx
0x18001db78  jz      short loc_18001DB89
0x18001db7a  mov     r8, rbx; Size
0x18001db7d  lea     rdx, [rbp+8C0h+Src]; Src
0x18001db84  call    memcpy_0
0x18001db89  mov     eax, 1Fh
0x18001db8e  lea     r8, [rsp+9C0h+pvar]
0x18001db93  mov     word ptr [rsp+9C0h+pvar], ax
0x18001db98  lea     rdx, PKEY_ItemType
0x18001db9f  mov     rax, [r15]
0x18001dba2  mov     rcx, r15
0x18001dba5  mov     rax, [rax+30h]
0x18001dba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbae  mov     ebx, eax
0x18001dbb0  test    eax, eax
0x18001dbb2  js      loc_18001E1D9
0x18001dbb8  mov     edx, 2; dwMask
0x18001dbbd  mov     dword ptr [rsp+9C0h+psfs.fShowAllObjects], r12d
0x18001dbc2  lea     rcx, [rsp+9C0h+psfs]; psfs
0x18001dbc7  call    cs:__imp_SHGetSettings
0x18001dbcd  mov     ebx, dword ptr [rsp+9C0h+psfs.fShowAllObjects]
0x18001dbd1  shl     ebx, 1Eh
0x18001dbd4  sar     ebx, 1Fh
0x18001dbd7  cmp     dword ptr [r14+42h], 1
0x18001dbdc  jbe     loc_18001E01E
0x18001dbe2  mov     eax, [r14+3Eh]
0x18001dbe6  lea     rdx, [r14+rax*2]
0x18001dbea  mov     rcx, rdi
0x18001dbed  lea     r8, [rbp+8C0h+pszPath]
0x18001dbf4  add     rdx, 4Ah ; 'J'
0x18001dbf8  mov     r9, rsi
0x18001dbfb  nop     dword ptr [rax+rax+00h]
0x18001dc00  test    rcx, rcx
0x18001dc03  jz      short loc_18001DC22
0x18001dc05  movzx   eax, word ptr [rdx]
0x18001dc08  test    ax, ax
0x18001dc0b  jz      short loc_18001DC22
0x18001dc0d  mov     [r8], ax
0x18001dc11  add     rdx, 2
0x18001dc15  add     r8, 2
0x18001dc19  dec     rcx
0x18001dc1c  sub     r9, 1
0x18001dc20  jnz     short loc_18001DC00
0x18001dc22  test    r9, r9
0x18001dc25  lea     rcx, [r8-2]
0x18001dc29  cmovnz  rcx, r8
0x18001dc2d  mov     [rcx], r12w
0x18001dc31  lea     rcx, [rbp+8C0h+pszPath]; pszPath
0x18001dc38  call    cs:__imp_PathFindFileNameW
0x18001dc3e  test    ebx, ebx
0x18001dc40  jz      loc_18001E02E
0x18001dc46  mov     rcx, rdi
0x18001dc49  lea     rdx, [rbp+8C0h+pszPath]
0x18001dc50  mov     r9, rsi
0x18001dc53  lea     r8, [rbp+8C0h+Src]
0x18001dc5a  nop     word ptr [rax+rax+00h]
0x18001dc60  test    rcx, rcx
0x18001dc63  jz      short loc_18001DC82
0x18001dc65  movzx   eax, word ptr [rdx]
0x18001dc68  test    ax, ax
0x18001dc6b  jz      short loc_18001DC82
0x18001dc6d  mov     [r8], ax
0x18001dc71  add     rdx, 2
0x18001dc75  add     r8, 2
0x18001dc79  dec     rcx
0x18001dc7c  sub     r9, 1
0x18001dc80  jnz     short loc_18001DC60
0x18001dc82  test    r9, r9
0x18001dc85  lea     rcx, [r8-2]
0x18001dc89  cmovnz  rcx, r8
0x18001dc8d  mov     [rcx], r12w
0x18001dc91  lea     rcx, [rsp+9C0h+pvar]; pvar
0x18001dc96  call    cs:__imp_PropVariantClear
0x18001dc9c  lea     rcx, [rbp+8C0h+Src]
0x18001dca3  mov     rax, r13
0x18001dca6  nop     word ptr [rax+rax+00000000h]
0x18001dcb0  cmp     [rcx+rax*2+2], r12w
0x18001dcb6  lea     rax, [rax+1]
0x18001dcba  jnz     short loc_18001DCB0
0x18001dcbc  lea     rbx, ds:2[rax*2]
0x18001dcc4  mov     rcx, rbx; cb
0x18001dcc7  call    cs:__imp_CoTaskMemAlloc
0x18001dccd  mov     rcx, rax
0x18001dcd0  mov     dword ptr [rsp+9C0h+pvar+8], eax
0x18001dcd4  sar     rcx, 20h
0x18001dcd8  mov     dword ptr [rsp+9C0h+pvar+0Ch], ecx
0x18001dcdc  test    rax, rax
0x18001dcdf  jz      loc_18001E4FD
0x18001dce5  test    rbx, rbx
0x18001dce8  jz      short loc_18001DCFC
0x18001dcea  mov     r8, rbx; Size
0x18001dced  lea     rdx, [rbp+8C0h+Src]; Src
0x18001dcf4  mov     rcx, rax; void *
0x18001dcf7  call    memcpy_0
0x18001dcfc  mov     eax, 1Fh
0x18001dd01  lea     r8, [rsp+9C0h+pvar]
0x18001dd06  mov     word ptr [rsp+9C0h+pvar], ax
0x18001dd0b  lea     rdx, PKEY_ItemNameDisplay
0x18001dd12  mov     rax, [r15]
0x18001dd15  mov     rcx, r15
0x18001dd18  mov     rax, [rax+30h]
0x18001dd1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd21  mov     ebx, eax
0x18001dd23  test    eax, eax
0x18001dd25  js      loc_18001E207
0x18001dd2b  xor     edx, edx; Val
0x18001dd2d  mov     [rbp+8C0h+Src], r12w
0x18001dd35  mov     r8d, 2B8h; Size
0x18001dd3b  lea     rcx, [rbp+8C0h+psfi]; void *
0x18001dd3f  call    memset_0
0x18001dd44  mov     ebx, [r14+0Ah]
0x18001dd48  and     ebx, 2
0x18001dd4b  shl     ebx, 3
0x18001dd4e  cmp     dword ptr [r14+42h], 1
0x18001dd53  jbe     loc_18001E026
0x18001dd59  mov     eax, [r14+3Eh]
0x18001dd5d  lea     rdx, [r14+rax*2]
0x18001dd61  mov     rcx, rdi
0x18001dd64  lea     r8, [rbp+8C0h+var_250]
0x18001dd6b  add     rdx, 4Ah ; 'J'
0x18001dd6f  mov     r10, rsi
0x18001dd72  test    rcx, rcx
0x18001dd75  jz      short loc_18001DD94
0x18001dd77  movzx   eax, word ptr [rdx]
0x18001dd7a  test    ax, ax
0x18001dd7d  jz      short loc_18001DD94
0x18001dd7f  mov     [r8], ax
0x18001dd83  add     rdx, 2
0x18001dd87  add     r8, 2
0x18001dd8b  dec     rcx
0x18001dd8e  sub     r10, 1
0x18001dd92  jnz     short loc_18001DD72
0x18001dd94  test    r10, r10
0x18001dd97  lea     rcx, [r8-2]
0x18001dd9b  cmovnz  rcx, r8
0x18001dd9f  mov     [rcx], r12w
0x18001dda3  lea     rcx, [rbp+8C0h+var_250]; pszPath
0x18001ddaa  call    cs:__imp_PathFindFileNameW
0x18001ddb0  mov     r9d, 2B8h; cbFileInfo
0x18001ddb6  mov     dword ptr [rsp+9C0h+DirCount], 410h; uFlags
0x18001ddbe  mov     rcx, rax; pszPath
0x18001ddc1  lea     r8, [rbp+8C0h+psfi]; psfi
0x18001ddc5  mov     edx, ebx; dwFileAttributes
0x18001ddc7  call    cs:__imp_SHGetFileInfoW
0x18001ddcd  test    eax, eax
0x18001ddcf  jz      short loc_18001DE10
0x18001ddd1  lea     rcx, [rbp+8C0h+psfi.szTypeName]
0x18001ddd8  lea     rdx, [rbp+8C0h+Src]
0x18001dddf  nop
0x18001dde0  test    rdi, rdi
0x18001dde3  jz      short loc_18001DE01
0x18001dde5  movzx   eax, word ptr [rcx]
0x18001dde8  test    ax, ax
0x18001ddeb  jz      short loc_18001DE01
0x18001dded  mov     [rdx], ax
0x18001ddf0  add     rcx, 2
0x18001ddf4  add     rdx, 2
0x18001ddf8  dec     rdi
0x18001ddfb  sub     rsi, 1
0x18001ddff  jnz     short loc_18001DDE0
0x18001de01  test    rsi, rsi
0x18001de04  lea     rcx, [rdx-2]
0x18001de08  cmovnz  rcx, rdx
0x18001de0c  mov     [rcx], r12w
0x18001de10  lea     rcx, [rsp+9C0h+pvar]; pvar
0x18001de15  call    cs:__imp_PropVariantClear
0x18001de1b  lea     rcx, [rbp+8C0h+Src]
0x18001de22  mov     rax, r13
0x18001de25  nop     word ptr [rax+rax+00000000h]
0x18001de30  cmp     [rcx+rax*2+2], r12w
0x18001de36  lea     rax, [rax+1]
0x18001de3a  jnz     short loc_18001DE30
0x18001de3c  lea     rbx, ds:2[rax*2]
0x18001de44  mov     rcx, rbx; cb
0x18001de47  call    cs:__imp_CoTaskMemAlloc
0x18001de4d  mov     rcx, rax
0x18001de50  mov     dword ptr [rsp+9C0h+pvar+8], eax
0x18001de54  sar     rcx, 20h
0x18001de58  mov     dword ptr [rsp+9C0h+pvar+0Ch], ecx
0x18001de5c  test    rax, rax
0x18001de5f  jz      loc_18001E4C1
0x18001de65  test    rbx, rbx
0x18001de68  jz      short loc_18001DE7C
0x18001de6a  mov     r8, rbx; Size
0x18001de6d  lea     rdx, [rbp+8C0h+Src]; Src
0x18001de74  mov     rcx, rax; void *
0x18001de77  call    memcpy_0
0x18001de7c  mov     eax, 1Fh
0x18001de81  lea     r8, [rsp+9C0h+pvar]
0x18001de86  mov     word ptr [rsp+9C0h+pvar], ax
0x18001de8b  lea     rdx, PKEY_ItemTypeText
0x18001de92  mov     rax, [r15]
0x18001de95  mov     rcx, r15
0x18001de98  mov     rax, [rax+30h]
0x18001de9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dea1  mov     ebx, eax
0x18001dea3  test    eax, eax
0x18001dea5  js      loc_18001E235
0x18001deab  lea     rcx, [rsp+9C0h+pvar]; pvar
0x18001deb0  call    cs:__imp_PropVariantClear
0x18001deb6  mov     eax, [r14+0Ah]
0x18001deba  lea     r8, [rsp+9C0h+pvar]
0x18001debf  mov     dword ptr [rsp+9C0h+pvar+8], eax
0x18001dec3  lea     rdx, PKEY_WPDNSE_Attributes
0x18001deca  mov     rax, [r15]
0x18001decd  mov     ecx, 13h
0x18001ded2  mov     word ptr [rsp+9C0h+pvar], cx
0x18001ded7  mov     rcx, r15
0x18001deda  mov     rax, [rax+30h]
0x18001dede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dee3  mov     ebx, eax
0x18001dee5  test    eax, eax
  ... truncated ...
```
