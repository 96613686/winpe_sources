# CFileSysItemString::CFileSysItemString(CFSFolder *,_ITEMIDLIST_RELATIVE const *,IDFOLDER const *)

- ea: `0x180038f80`
- end: `0x180039a21`
- name: `??0CFileSysItemString@@QEAA@PEAVCFSFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEFBUIDFOLDER@@@Z`
- size: `2721`
- prototype: `CFileSysItemString *__fastcall(CFileSysItemString *__hidden this, struct CFSFolder *, const struct _ITEMIDLIST_RELATIVE *, const struct IDFOLDER *)`
- caller_count: `61`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180037a90`
- `0x180038560`
- `0x180041460`
- `0x180041620`
- `0x1800416e0`
- `0x1800417d0`
- `0x180041b90`
- `0x180041e60`
- `0x180041f50`
- `0x1800428a0`
- `0x180042970`
- `0x180042e30`
- `0x180043500`
- `0x180043a20`
- `0x180043eb0`
- `0x180044440`
- `0x180044870`
- `0x180045c80`
- `0x180046670`
- `0x180047190`
- `0x180047d30`
- `0x18005bd80`
- `0x1800609a0`
- `0x180069550`
- `0x18006a8c0`
- `0x18008a2f0`
- `0x180096ab0`
- `0x180097680`
- `0x18009a1c0`
- `0x1800a28c0`
- `0x1800acc20`
- `0x1800bd610`
- `0x1801069f0`
- `0x180116bb8`
- `0x1801170a0`
- `0x180180170`
- `0x180185ad0`
- `0x180185be0`
- `0x180201330`
- `0x1802029b0`
- `0x180254380`
- `0x180254504`
- `0x18026a6bc`
- `0x18026c4b0`
- `0x1802760b0`
- `0x18029a390`
- `0x18029a67c`
- `0x1802a2f00`
- `0x1802fc1c8`
- `0x18032c640`

## callees

- `0x180038f80`
- `0x18006b970`
- `0x18034591c`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x1803b69c5`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039770`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800398f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039770`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800398f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039751`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800398da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039751`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800398da`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800396bb`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800396bb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18003921f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18003921f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039618`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039897`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039618`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039897`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039762`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800398eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039762`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800398eb`
- `SHCORE!__imp_ualstrcpynW` at `0x18003931d`
- `SHCORE!__imp_ualstrcpynW` at `0x18003931d`
- `SHCORE!__imp_ualstrlenW` at `0x180039601`
- `SHCORE!__imp_ualstrlenW` at `0x180039880`
- `SHCORE!__imp_ualstrlenW` at `0x180039601`
- `SHCORE!__imp_ualstrlenW` at `0x180039880`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CFileSysItemString *__fastcall CFileSysItemString::CFileSysItemString(
        CFileSysItemString *this,
        struct CFSFolder *a2,
        const struct _ITEMIDLIST_RELATIVE *a3,
        const struct IDFOLDER *a4)
{
  const struct _ITEMIDLIST_RELATIVE *v4; // rsi
  const struct _ITEMIDLIST_RELATIVE *v6; // rbx
  const struct _ITEMIDLIST_RELATIVE *v7; // rdi
  char IsEnabled; // al
  unsigned __int16 v9; // r8
  unsigned __int16 *v10; // rdx
  __int64 v11; // r9
  unsigned int v12; // ecx
  unsigned __int64 v13; // rcx
  _BYTE *v14; // rcx
  unsigned __int64 v15; // rdx
  int v16; // ecx
  char v17; // al
  unsigned __int16 v18; // r8
  unsigned __int16 *v19; // rdx
  __int64 v20; // rcx
  unsigned int v21; // r9d
  unsigned __int64 v22; // rcx
  WCHAR *v23; // rbx
  __int64 v24; // rcx
  const CHAR *v25; // rdx
  unsigned __int16 *v27; // r9
  _WORD *v28; // rax
  __int64 v29; // rcx
  unsigned __int16 *v30; // r9
  unsigned __int16 *v31; // r8
  unsigned __int16 *v32; // r8
  unsigned __int16 v33; // ax
  unsigned __int16 v34; // r10
  __int64 v35; // rax
  __int64 v36; // rcx
  _WORD *v37; // rax
  unsigned __int64 v38; // rcx
  __int64 v39; // rax
  _BYTE *v40; // rcx
  unsigned __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rcx
  _WORD *v44; // rax
  unsigned __int64 v45; // rcx
  void *v46; // rdi
  unsigned __int16 v47; // ax
  const struct _ITEMIDLIST_RELATIVE *v48; // rcx
  const struct _ITEMIDLIST_RELATIVE *v49; // rbx
  unsigned __int16 *v50; // rdx
  unsigned __int64 v51; // r8
  __int64 v52; // rcx
  unsigned int v53; // r9d
  unsigned __int64 v54; // rcx
  unsigned __int16 *v55; // r8
  const void *v56; // rbx
  size_t v57; // rdi
  void *v58; // rax
  size_t v59; // rax
  __int64 v60; // rax
  unsigned __int64 v61; // r10
  unsigned __int16 *v62; // rdx
  unsigned int v63; // r8d
  __int64 v64; // rcx
  DWORD LastError; // ebx
  unsigned __int16 *v66; // r10
  void *v67; // rdi
  unsigned __int16 v68; // ax
  const struct _ITEMIDLIST_RELATIVE *v69; // rbx
  unsigned __int16 *v70; // rdx
  unsigned __int64 v71; // r8
  __int64 v72; // r9
  unsigned int v73; // ecx
  unsigned __int64 v74; // rcx
  unsigned __int16 *v75; // r8
  const void *v76; // rbx
  SIZE_T v77; // rdi
  void *v78; // rax
  size_t v79; // rax
  DWORD v80; // ebx
  unsigned __int16 *v81; // r9
  unsigned __int16 *v82; // r10
  unsigned __int16 *v83; // r9
  WCHAR WideCharStr[256]; // [rsp+40h] [rbp-238h] BYREF

  v4 = a3;
  *(_OWORD *)this = 0;
  *((_OWORD *)this + 1) = 0;
  *((_OWORD *)this + 2) = 0;
  *((_BYTE *)this + 8) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 8) = 0;
  *((_DWORD *)this + 9) = -1;
  *((_BYTE *)this + 40) = 0;
  *((_QWORD *)this + 6) = 0;
  *(_QWORD *)this = &CFileSysItemString::`vftable';
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = a2;
  *((_QWORD *)this + 10) = a4;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = a3;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_DWORD *)this + 32) = 0;
  *(GUID *)((char *)this + 652) = FOLDERTYPEID_Invalid;
  *((_DWORD *)this + 167) = 0;
  *((_BYTE *)this + 672) = 0;
  *((_WORD *)this + 66) = 0;
  if ( !a4 )
  {
    v6 = 0;
    if ( a3 )
    {
      v29 = *(unsigned __int16 *)a3;
      if ( (unsigned int)v29 > 0xB )
      {
        if ( (*((_BYTE *)a3 + 2) & 0x70) == 0x30 )
        {
          v6 = a3;
          v7 = 0;
LABEL_4:
          if ( *(_WORD *)v6 >= 0xEu )
          {
            if ( !v4 )
              goto LABEL_46;
            if ( !*(_WORD *)v4 )
              goto LABEL_46;
            IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl'::`2'::impl);
            v9 = *(_WORD *)v4;
            if ( IsEnabled )
            {
              if ( v9 < 2u )
                goto LABEL_46;
            }
            v10 = 0;
            v11 = *(unsigned __int16 *)((char *)v4 + v9 - 2);
            if ( (_WORD)v11 )
            {
              if ( v11 + 8 < (unsigned __int64)v9 )
              {
                v10 = (unsigned __int16 *)((char *)v4 + v11);
                v12 = *(unsigned __int16 *)((char *)v4 + v11);
                if ( v12 < 8 || HIWORD(*((_DWORD *)v10 + 1)) != 0xBEEF || (unsigned int)v11 + v12 > v9 )
                  v10 = 0;
              }
            }
            v13 = (unsigned __int64)v4 + v9;
            if ( v10 )
            {
              while ( *((_DWORD *)v10 + 1) != -1091633148 )
              {
                v27 = 0;
                if ( (unsigned __int64)(v10 + 4) <= v13 )
                {
                  v32 = (unsigned __int16 *)((char *)v10 + *v10);
                  if ( v32 == (unsigned __int16 *)v13 )
                    goto LABEL_46;
                  if ( (unsigned __int64)v32 <= v13 )
                  {
                    if ( (unsigned __int64)(v32 + 4) > v13
                      || HIWORD(*((_DWORD *)v32 + 1)) != 0xBEEF
                      || (unsigned __int64)v32 + *v32 > v13
                      || v32 < v10 + 4 )
                    {
                      goto LABEL_46;
                    }
                    v27 = (unsigned __int16 *)((char *)v10 + *v10);
                  }
                }
                v10 = v27;
                if ( !v27 )
                  goto LABEL_46;
              }
            }
            else
            {
LABEL_46:
              if ( (*((_BYTE *)v6 + 2) & 0x34) == 0x34 )
              {
                v28 = (_WORD *)((char *)v6 + 14);
                if ( v6 != (const struct _ITEMIDLIST_RELATIVE *)-14LL )
                {
                  v15 = ((unsigned __int64)*(unsigned __int16 *)v6 - 14) >> 1;
                  if ( v15 <= 0x7FFFFFFF )
                  {
                    for ( ; v15; --v15 )
                    {
                      if ( !*v28 )
                        break;
                      ++v28;
                    }
                    goto LABEL_20;
                  }
                }
LABEL_142:
                v16 = -2147024809;
LABEL_22:
                if ( v16 >= 0 )
                  v7 = v6;
                goto LABEL_24;
              }
            }
            v14 = (char *)v6 + 14;
            if ( v6 != (const struct _ITEMIDLIST_RELATIVE *)-14LL )
            {
              v15 = *(unsigned __int16 *)v6 - 14LL;
              if ( v15 <= 0x7FFFFFFF )
              {
                if ( *(_WORD *)v6 != 14 )
                {
                  do
                  {
                    if ( !*v14 )
                      break;
                    ++v14;
                    --v15;
                  }
                  while ( v15 );
                }
LABEL_20:
                v16 = -2147024809;
                if ( v15 )
                  v16 = 0;
                goto LABEL_22;
              }
            }
            goto LABEL_142;
          }
LABEL_24:
          *((_QWORD *)this + 10) = v7;
          goto LABEL_25;
        }
        if ( *(_DWORD *)((char *)a3 + 6) == 1179862595 )
        {
          v61 = *((unsigned __int16 *)a3 + 2);
          if ( v61 > v29 - 4 )
            goto LABEL_139;
          v6 = (const struct _ITEMIDLIST_RELATIVE *)((char *)a3 + 10);
          v62 = (unsigned __int16 *)((char *)a3 + 10);
          v63 = 2;
          if ( (unsigned int)v61 < 2 )
            goto LABEL_139;
          while ( 1 )
          {
            v64 = *v62;
            if ( (unsigned int)v64 < 2 || (unsigned int)v64 > (unsigned int)v61 - v63 )
              break;
            v63 += v64;
            v62 = (unsigned __int16 *)((char *)v62 + v64);
            if ( v63 > (unsigned int)v61 )
              goto LABEL_139;
          }
          if ( (_WORD)v64
            || v63 > (unsigned int)v61
            || (_WORD)v61 != *(_WORD *)v6 + 6
            || (unsigned __int16)(*(_WORD *)v6 + 6) < *(_WORD *)v6 )
          {
LABEL_139:
            v7 = 0;
            goto LABEL_24;
          }
        }
      }
    }
    v7 = 0;
    if ( !v6 )
      goto LABEL_24;
    goto LABEL_4;
  }
LABEL_25:
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 8LL))(*((_QWORD *)this + 9));
  if ( !v4 )
    goto LABEL_124;
  if ( !*(_WORD *)v4 )
    goto LABEL_124;
  v17 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl'::`2'::impl);
  v18 = *(_WORD *)v4;
  if ( v17 )
  {
    if ( v18 < 2u )
      goto LABEL_124;
  }
  v19 = 0;
  v20 = *(unsigned __int16 *)((char *)v4 + v18 - 2);
  if ( (_WORD)v20 )
  {
    if ( v20 + 8 < (unsigned __int64)v18 )
    {
      v19 = (unsigned __int16 *)((char *)v4 + v20);
      v21 = *(unsigned __int16 *)((char *)v4 + v20);
      if ( v21 < 8 || HIWORD(*((_DWORD *)v19 + 1)) != 0xBEEF || v21 + (unsigned int)v20 > v18 )
        v19 = 0;
    }
  }
  v22 = (unsigned __int64)v4 + v18;
  if ( v19 )
  {
    while ( *((_DWORD *)v19 + 1) != -1091633148 )
    {
      v30 = 0;
      if ( (unsigned __int64)(v19 + 4) <= v22 )
      {
        v31 = (unsigned __int16 *)((char *)v19 + *v19);
        if ( v31 == (unsigned __int16 *)v22 )
          goto LABEL_124;
        if ( (unsigned __int64)v31 <= v22 )
        {
          if ( (unsigned __int64)(v31 + 4) > v22
            || HIWORD(*((_DWORD *)v31 + 1)) != 0xBEEF
            || (unsigned __int64)v31 + *v31 > v22
            || v31 < v19 + 4 )
          {
            goto LABEL_124;
          }
          v30 = (unsigned __int16 *)((char *)v19 + *v19);
        }
      }
      v19 = v30;
      if ( !v30 )
        break;
    }
  }
  *((_QWORD *)this + 11) = v19;
  if ( v19 )
  {
    if ( *v19 >= 0x14u )
    {
      v33 = v19[1];
      if ( v33 >= 7u )
      {
        if ( *v19 < 0x26u )
        {
          *((_QWORD *)this + 11) = 0;
          v19 = 0;
          v34 = 0;
        }
        else
        {
          v34 = 38;
        }
LABEL_75:
        if ( !v19 )
          goto LABEL_36;
        v35 = v19[8];
        if ( (_WORD)v35 )
        {
          v36 = *v19;
          if ( (unsigned __int16)v35 >= (unsigned __int16)v36 )
            goto LABEL_124;
          if ( (unsigned __int16)v35 < v34 )
            goto LABEL_124;
          v37 = (unsigned __int16 *)((char *)v19 + v35);
          if ( !v37 )
            goto LABEL_124;
          v38 = (v36 - (unsigned __int64)v19[8]) >> 1;
          if ( v38 > 0x7FFFFFFF )
            goto LABEL_124;
          for ( ; v38; --v38 )
          {
            if ( !*v37 )
              break;
            ++v37;
          }
          v19 = (unsigned __int16 *)*((_QWORD *)this + 11);
          if ( !v38 )
            goto LABEL_124;
          if ( !v19 )
            goto LABEL_36;
        }
        v39 = v19[9];
        if ( (_WORD)v39 )
        {
          if ( (unsigned __int16)v39 >= *v19 )
            goto LABEL_124;
          if ( (unsigned __int16)v39 < v34 )
            goto LABEL_124;
          v40 = (char *)v19 + v39;
          if ( !(unsigned __int16 *)((char *)v19 + v39) )
            goto LABEL_124;
          v41 = *v19 - (unsigned __int64)v19[9];
          if ( v41 > 0x7FFFFFFF )
            goto LABEL_124;
          for ( ; v41; --v41 )
          {
            if ( !*v40 )
              break;
            ++v40;
          }
          v19 = (unsigned __int16 *)*((_QWORD *)this + 11);
          if ( !v41 )
            goto LABEL_124;
          if ( !v19 )
            goto LABEL_36;
        }
        if ( v19[1] >= 7u )
        {
          v42 = v19[18];
          if ( (_WORD)v42 )
          {
            v43 = *v19;
            if ( (unsigned __int16)v42 >= (unsigned __int16)v43 )
              goto LABEL_124;
            if ( (unsigned __int16)v42 < v34 )
              goto LABEL_124;
            v44 = (unsigned __int16 *)((char *)v19 + v42);
            if ( !v44 )
              goto LABEL_124;
            v45 = (v43 - (unsigned __int64)v19[18]) >> 1;
            if ( v45 > 0x7FFFFFFF || !v45 )
              goto LABEL_124;
            do
            {
              if ( !*v44 )
                break;
              ++v44;
              --v45;
            }
            while ( v45 );
            if ( !v45 )
              goto LABEL_124;
            if ( !*((_QWORD *)this + 11) )
              goto LABEL_36;
          }
        }
        v46 = (void *)*((_QWORD *)this + 6);
        if ( v46 )
        {
          LastError = GetLastError();
          CoTaskMemFree(v46);
          SetLastError(LastError);
        }
        *((_QWORD *)this + 6) = 0;
        v47 = *(_WORD *)v4;
        if ( !*(_WORD *)v4 )
          goto LABEL_149;
        v48 = v4;
        do
        {
          v49 = v48;
          v48 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v48 + v47);
          v47 = *(_WORD *)v48;
        }
        while ( *(_WORD *)v48 );
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl'::`2'::impl)
          && (!v49 || *(_WORD *)v49 < 2u) )
        {
          goto LABEL_149;
        }
        v50 = 0;
        v51 = *(unsigned __int16 *)v49;
        v52 = *(unsigned __int16 *)((char *)v49 + v51 - 2);
        if ( (_WORD)v52 )
        {
          if ( v52 + 8 < v51 )
          {
            v50 = (unsigned __int16 *)((char *)v49 + v52);
            v53 = *(unsigned __int16 *)((char *)v49 + v52);
            if ( v53 < 8 || HIWORD(*((_DWORD *)v50 + 1)) != 0xBEEF || v53 + (unsigned int)v52 > (unsigned int)v51 )
              v50 = 0;
          }
        }
        v54 = (unsigned __int64)v49 + *(unsigned __int16 *)v49;
        if ( !v50 )
          goto LABEL_149;
        while ( 1 )
        {
          v55 = v50 + 4;
          if ( *((_DWORD *)v50 + 1) == -1091633126 )
            break;
          v66 = 0;
          if ( (unsigned __int64)v55 <= v54 )
          {
            v81 = (unsigned __int16 *)((char *)v50 + *v50);
            if ( v81 == (unsigned __int16 *)v54 )
              goto LABEL_149;
            if ( (unsigned __int64)v81 <= v54 )
            {
              if ( (unsigned __int64)(v81 + 4) > v54
                || HIWORD(*((_DWORD *)v81 + 1)) != 0xBEEF
                || (unsigned __int64)v81 + *v81 > v54
                || v81 < v55 )
              {
                goto LABEL_149;
              }
              v66 = (unsigned __int16 *)((char *)v50 + *v50);
            }
          }
          v50 = v66;
          if ( !v66 )
            goto LABEL_149;
        }
        if ( *v55 == 2
          && (v56 = v50 + 5,
              v57 = 2 * ualstrlenW(v50 + 5, v50, v55) + 2,
              v58 = CoTaskMemAlloc(v57),
              (*((_QWORD *)this + 6) = v58) != 0) )
        {
          v59 = SHGetSize(v58);
          memset_0(*((void **)this + 6), 0, v59);
          memcpy_0(*((void **)this + 6), v56, v57);
          *((_BYTE *)this + 40) = 1;
        }
        else
        {
LABEL_149:
          v67 = (void *)*((_QWORD *)this + 6);
          if ( v67 )
          {
            v80 = GetLastError();
            CoTaskMemFree(v67);
            SetLastError(v80);
          }
          *((_QWORD *)this + 6) = 0;
          v68 = *(_WORD *)v4;
          if ( *(_WORD *)v4 )
          {
            do
            {
              v69 = v4;
              v4 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v4 + v68);
              v68 = *(_WORD *)v4;
            }
            while ( *(_WORD *)v4 );
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl'::`2'::impl)
              || v69 && *(_WORD *)v69 >= 2u )
            {
              v70 = 0;
              v71 = *(unsigned __int16 *)v69;
              v72 = *(unsigned __int16 *)((char *)v69 + v71 - 2);
              if ( (_WORD)v72 )
              {
                if ( v72 + 8 < v71 )
                {
                  v70 = (unsigned __int16 *)((char *)v69 + v72);
                  v73 = *(unsigned __int16 *)((char *)v69 + v72);
                  if ( v73 < 8 || HIWORD(*((_DWORD *)v70 + 1)) != 0xBEEF || (unsigned int)v72 + v73 > (unsigned int)v71 )
                    v70 = 0;
                }
              }
              v74 = (unsigned __int64)v69 + *(unsigned __int16 *)v69;
              if ( v70 )
              {
                while ( 1 )
                {
                  v75 = v70 + 4;
                  if ( *((_DWORD *)v70 + 1) == -1091633125 )
                    break;
                  v82 = 0;
                  if ( (unsigned __int64)v75 <= v74 )
                  {
                    v83 = (unsigned __int16 *)((char *)v70 + *v70);
                    if ( v83 == (unsigned __int16 *)v74 )
                      goto LABEL_36;
                    if ( (unsigned __int64)v83 <= v74 )
                    {
                      if ( (unsigned __int64)(v83 + 4) > v74
                        || HIWORD(*((_DWORD *)v83 + 1)) != 0xBEEF
                        || (unsigned __int64)v83 + *v83 > v74
                        || v83 < v75 )
                      {
                        goto LABEL_36;
                      }
                      v82 = (unsigned __int16 *)((char *)v70 + *v70);
                    }
                  }
                  v70 = v82;
                  if ( !v82 )
                    goto LABEL_36;
                }
                if ( *v75 == 2 )
                {
                  v76 = v70 + 5;
                  v77 = 2 * ualstrlenW(v70 + 5, v70, v75) + 2;
                  v78 = CoTaskMemAlloc(v77);
                  *((_QWORD *)this + 6) = v78;
                  if ( v78 )
                  {
                    v79 = SHGetSize(v78);
                    memset_0(*((void **)this + 6), 0, v79);
                    memcpy_0(*((void **)this + 6), v76, v77);
                  }
                }
              }
            }
          }
        }
        goto LABEL_36;
      }
      if ( v33 >= 3u )
      {
        if ( *v19 < 0x14u )
        {
          *((_QWORD *)this + 11) = 0;
          v19 = 0;
          v34 = 0;
        }
        else
        {
          v34 = 20;
        }
        goto LABEL_75;
      }
    }
LABEL_124:
    *((_QWORD *)this + 11) = 0;
  }
LABEL_36:
  v23 = WideCharStr;
  v24 = *((_QWORD *)this + 11);
  if ( !v24 )
  {
    v60 = *((_QWORD *)this + 10);
    v25 = (const CHAR *)(v60 + 14);
    if ( (*(_BYTE *)(v60 + 2) & 0x34) != 0x34 )
    {
      MultiByteToWideChar(0, 0, v25, -1, WideCharStr, 255);
      goto LABEL_39;
    }
    goto LABEL_56;
  }
  v25 = (const CHAR *)(v24 + *(unsigned __int16 *)(v24 + 16));
  if ( ((unsigned __int8)v25 & 1) != 0 )
  {
LABEL_56:
    ualstrcpynW(WideCharStr, v25, 255);
    goto LABEL_39;
  }
  v23 = (WCHAR *)(v24 + *(unsigned __int16 *)(v24 + 16));
LABEL_39:
  *((_BYTE *)this + 8) = PathFindExtensionW(v23) == v23;
  return this;
}

```

## disassembly

```asm
0x180038f80  mov     [rsp+arg_8], rbx
0x180038f85  push    rbp
0x180038f86  push    rsi
0x180038f87  push    rdi
0x180038f88  push    r14
0x180038f8a  push    r15
0x180038f8c  sub     rsp, 250h
0x180038f93  mov     rax, cs:__security_cookie
0x180038f9a  xor     rax, rsp
0x180038f9d  mov     [rsp+278h+var_38], rax
0x180038fa5  mov     rsi, r8
0x180038fa8  mov     r14, rcx
0x180038fab  mov     [rsp+278h+var_248], rcx
0x180038fb0  xorps   xmm0, xmm0
0x180038fb3  xor     eax, eax
0x180038fb5  movups  xmmword ptr [rcx], xmm0
0x180038fb8  movups  xmmword ptr [rcx+10h], xmm0
0x180038fbc  movups  xmmword ptr [rcx+20h], xmm0
0x180038fc0  mov     [rcx+8], al
0x180038fc3  xor     ebp, ebp
0x180038fc5  mov     [rcx+10h], rbp
0x180038fc9  mov     [rcx+18h], rbp
0x180038fcd  mov     [rcx+20h], ebp
0x180038fd0  mov     dword ptr [rcx+24h], 0FFFFFFFFh
0x180038fd7  mov     [rcx+28h], al
0x180038fda  mov     [rcx+30h], rbp
0x180038fde  lea     rax, ??_7CFileSysItemString@@6B@; const CFileSysItemString::`vftable'
0x180038fe5  mov     [rcx], rax
0x180038fe8  mov     [rcx+38h], rbp
0x180038fec  mov     [rcx+40h], rbp
0x180038ff0  mov     [rcx+48h], rdx
0x180038ff4  mov     [rcx+50h], r9
0x180038ff8  mov     [rcx+58h], rbp
0x180038ffc  mov     [rcx+60h], r8
0x180039000  mov     [rcx+68h], rbp
0x180039004  mov     [rcx+70h], rbp
0x180039008  mov     [rcx+78h], rbp
0x18003900c  mov     [rcx+80h], ebp
0x180039012  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_Invalid.Data1
0x180039019  movups  xmmword ptr [rcx+28Ch], xmm0
0x180039020  mov     [rcx+29Ch], ebp
0x180039026  mov     [rcx+2A0h], bpl
0x18003902d  mov     [rcx+84h], bp
0x180039034  mov     r15d, 0BEEFh
0x18003903a  test    r9, r9
0x18003903d  jnz     loc_180039145
0x180039043  mov     ebx, ebp
0x180039045  test    r8, r8
0x180039048  jnz     loc_1800392EB
0x18003904e  mov     rdi, rbp
0x180039051  test    rbx, rbx
0x180039054  jz      loc_180039141
0x18003905a  cmp     word ptr [rbx], 0Eh
0x18003905e  jb      loc_180039141
0x180039064  test    rsi, rsi
0x180039067  jz      loc_180039297
0x18003906d  cmp     word ptr [rsi], 0
0x180039071  jz      loc_180039297
0x180039077  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow> `wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl(void)'::`2'::impl
0x18003907e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(void)
0x180039083  movzx   r8d, word ptr [rsi]
0x180039087  test    al, al
0x180039089  jnz     loc_1800399C2
0x18003908f  movzx   r11d, r8w
0x180039093  mov     rdx, rbp
0x180039096  movzx   ecx, r8w
0x18003909a  movzx   r9d, word ptr [rcx+rsi-2]
0x1800390a0  test    r9w, r9w
0x1800390a4  jz      short loc_1800390DF
0x1800390a6  lea     rax, [r9+8]
0x1800390aa  cmp     rax, rcx
0x1800390ad  jnb     short loc_1800390DF
0x1800390af  lea     rdx, [r9+rsi]
0x1800390b3  movzx   ecx, word ptr [rdx]
0x1800390b6  cmp     ecx, 8
0x1800390b9  jb      loc_18003967C
0x1800390bf  mov     eax, [rdx+4]
0x1800390c2  shr     rax, 10h
0x1800390c6  cmp     ax, r15w
0x1800390ca  jnz     loc_18003967C
0x1800390d0  add     ecx, r9d
0x1800390d3  movzx   eax, r8w
0x1800390d7  cmp     ecx, eax
0x1800390d9  ja      loc_18003967C
0x1800390df  movzx   ecx, r11w
0x1800390e3  add     rcx, rsi
0x1800390e6  test    rdx, rdx
0x1800390e9  jz      loc_180039297
0x1800390ef  cmp     dword ptr [rdx+4], 0BEEF0004h
0x1800390f6  jnz     loc_180039398
0x1800390fc  lea     rcx, [rbx+0Eh]
0x180039100  test    rcx, rcx
0x180039103  jz      loc_180039747
0x180039109  movzx   edx, word ptr [rbx]
0x18003910c  add     rdx, 0FFFFFFFFFFFFFFF2h
0x180039110  cmp     rdx, 7FFFFFFFh
0x180039117  ja      loc_180039747
0x18003911d  test    rdx, rdx
0x180039120  jz      short loc_180039130
0x180039122  cmp     byte ptr [rcx], 0
0x180039125  jz      short loc_180039130
0x180039127  inc     rcx
0x18003912a  sub     rdx, 1
0x18003912e  jnz     short loc_180039122
0x180039130  mov     ecx, 80070057h
0x180039135  test    rdx, rdx
0x180039138  cmovnz  ecx, ebp
0x18003913b  test    ecx, ecx
0x18003913d  cmovns  rdi, rbx
0x180039141  mov     [r14+50h], rdi
0x180039145  mov     rcx, [r14+48h]
0x180039149  mov     rax, [rcx]
0x18003914c  mov     rax, [rax+8]
0x180039150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039155  test    rsi, rsi
0x180039158  jz      loc_18003966B
0x18003915e  cmp     word ptr [rsi], 0
0x180039162  jz      loc_18003966B
0x180039168  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow> `wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl(void)'::`2'::impl
0x18003916f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(void)
0x180039174  movzx   r8d, word ptr [rsi]
0x180039178  test    al, al
0x18003917a  jnz     loc_180039660
0x180039180  movzx   r11d, r8w
0x180039184  mov     rdx, rbp
0x180039187  movzx   r9d, r8w
0x18003918b  movzx   ecx, word ptr [r9+rsi-2]
0x180039191  test    cx, cx
0x180039194  jz      short loc_1800391D1
0x180039196  lea     rax, [rcx+8]
0x18003919a  cmp     rax, r9
0x18003919d  jnb     short loc_1800391D1
0x18003919f  lea     rdx, [rsi+rcx]
0x1800391a3  movzx   r9d, word ptr [rdx]
0x1800391a7  cmp     r9d, 8
0x1800391ab  jb      loc_180039674
0x1800391b1  mov     eax, [rdx+4]
0x1800391b4  shr     rax, 10h
0x1800391b8  cmp     ax, r15w
0x1800391bc  jnz     loc_180039674
0x1800391c2  add     ecx, r9d
0x1800391c5  movzx   eax, r8w
0x1800391c9  cmp     ecx, eax
0x1800391cb  ja      loc_180039674
0x1800391d1  movzx   ecx, r11w
0x1800391d5  add     rcx, rsi
0x1800391d8  test    rdx, rdx
0x1800391db  jz      short loc_1800391EA
0x1800391dd  cmp     dword ptr [rdx+4], 0BEEF0004h
0x1800391e4  jnz     loc_18003932E
0x1800391ea  mov     [r14+58h], rdx
0x1800391ee  test    rdx, rdx
0x1800391f1  jnz     loc_1800393C3
0x1800391f7  lea     rbx, [rsp+278h+WideCharStr]
0x1800391fc  mov     rcx, [r14+58h]
0x180039200  test    rcx, rcx
0x180039203  jz      loc_180039684
0x180039209  movzx   edx, word ptr [rcx+10h]
0x18003920d  add     rdx, rcx
0x180039210  test    dl, 1
0x180039213  jnz     loc_180039312
0x180039219  mov     rbx, rdx
0x18003921c  mov     rcx, rbx; pszPath
0x18003921f  call    cs:__imp_PathFindExtensionW
0x180039226  nop     dword ptr [rax+rax+00h]
0x18003922b  cmp     rax, rbx
0x18003922e  setz    cl
0x180039231  mov     [r14+8], cl
0x180039235  mov     rax, r14
0x180039238  mov     rcx, [rsp+278h+var_38]
0x180039240  xor     rcx, rsp; StackCookie
0x180039243  call    __security_check_cookie
0x180039248  mov     rbx, [rsp+278h+arg_8]
0x180039250  add     rsp, 250h
0x180039257  pop     r15
0x180039259  pop     r14
0x18003925b  pop     rdi
0x18003925c  pop     rsi
0x18003925d  pop     rbp
0x18003925e  retn
0x180039260  lea     rax, [r8+8]
0x180039264  cmp     rax, rcx
0x180039267  ja      short loc_180039297
0x180039269  mov     eax, [r8+4]
0x18003926d  shr     rax, 10h
0x180039271  cmp     ax, r15w
0x180039275  jnz     short loc_180039297
0x180039277  movzx   eax, word ptr [r8]
0x18003927b  add     rax, r8
0x18003927e  cmp     rax, rcx
0x180039281  ja      short loc_180039297
0x180039283  cmp     r8, r10
0x180039286  jb      short loc_180039297
0x180039288  mov     r9, r8
0x18003928b  mov     rdx, r9
0x18003928e  test    r9, r9
0x180039291  jnz     loc_1800390EF
0x180039297  movzx   eax, byte ptr [rbx+2]
0x18003929b  and     al, 34h
0x18003929d  cmp     al, 34h ; '4'
0x18003929f  jnz     loc_1800390FC
0x1800392a5  lea     rax, [rbx+0Eh]
0x1800392a9  test    rax, rax
0x1800392ac  jz      loc_180039747
0x1800392b2  movzx   edx, word ptr [rbx]
0x1800392b5  sub     rdx, 0Eh
0x1800392b9  shr     rdx, 1
0x1800392bc  cmp     rdx, 7FFFFFFFh
0x1800392c3  ja      loc_180039747
0x1800392c9  test    rdx, rdx
0x1800392cc  jz      loc_180039130
0x1800392d2  cmp     word ptr [rax], 0
0x1800392d6  jz      loc_180039130
0x1800392dc  add     rax, 2
0x1800392e0  sub     rdx, 1
0x1800392e4  jnz     short loc_1800392D2
0x1800392e6  jmp     loc_180039130
0x1800392eb  movzx   ecx, word ptr [r8]
0x1800392ef  cmp     ecx, 0Bh
0x1800392f2  jbe     loc_18003904E
0x1800392f8  movzx   eax, byte ptr [r8+2]
0x1800392fd  and     al, 70h
0x1800392ff  cmp     al, 30h ; '0'
0x180039301  jnz     loc_1800396CC
0x180039307  mov     rbx, rsi
0x18003930a  mov     rdi, rbp
0x18003930d  jmp     loc_18003905A
0x180039312  mov     r8d, 0FFh
0x180039318  lea     rcx, [rsp+278h+WideCharStr]
0x18003931d  call    cs:__imp_ualstrcpynW
0x180039324  nop     dword ptr [rax+rax+00h]
0x180039329  jmp     loc_18003921C
0x18003932e  mov     r9, rbp
0x180039331  lea     r10, [rdx+8]
0x180039335  cmp     r10, rcx
0x180039338  ja      short loc_180039387
0x18003933a  movzx   r8d, word ptr [rdx]
0x18003933e  add     r8, rdx
0x180039341  cmp     r8, rcx
0x180039344  jz      loc_18003966B
0x18003934a  ja      short loc_180039387
0x18003934c  lea     rax, [r8+8]
0x180039350  cmp     rax, rcx
0x180039353  ja      loc_18003966B
0x180039359  mov     eax, [r8+4]
0x18003935d  shr     rax, 10h
0x180039361  cmp     ax, r15w
0x180039365  jnz     loc_18003966B
0x18003936b  movzx   eax, word ptr [r8]
0x18003936f  add     rax, r8
0x180039372  cmp     rax, rcx
0x180039375  ja      loc_18003966B
0x18003937b  cmp     r8, r10
0x18003937e  jb      loc_18003966B
0x180039384  mov     r9, r8
0x180039387  mov     rdx, r9
0x18003938a  test    r9, r9
0x18003938d  jz      loc_1800391EA
0x180039393  jmp     loc_1800391DD
0x180039398  mov     r9, rbp
0x18003939b  lea     r10, [rdx+8]
0x18003939f  cmp     r10, rcx
0x1800393a2  ja      loc_18003928B
0x1800393a8  movzx   r8d, word ptr [rdx]
0x1800393ac  add     r8, rdx
0x1800393af  cmp     r8, rcx
0x1800393b2  jz      loc_180039297
0x1800393b8  ja      loc_18003928B
0x1800393be  jmp     loc_180039260
0x1800393c3  cmp     word ptr [rdx], 14h
0x1800393c7  jb      loc_18003966B
0x1800393cd  movzx   eax, word ptr [rdx+2]
0x1800393d1  cmp     ax, 7
0x1800393d5  jb      loc_1800399A7
0x1800393db  cmp     word ptr [rdx], 26h ; '&'
0x1800393df  jb      loc_180039A02
0x1800393e5  mov     r10d, 26h ; '&'
0x1800393eb  test    rdx, rdx
0x1800393ee  jz      loc_1800391F7
0x1800393f4  movzx   eax, word ptr [rdx+10h]
0x1800393f8  test    ax, ax
0x1800393fb  jz      short loc_18003945D
0x1800393fd  movzx   ecx, word ptr [rdx]
0x180039400  cmp     ax, cx
0x180039403  jnb     loc_18003966B
0x180039409  cmp     ax, r10w
0x18003940d  jb      loc_18003966B
0x180039413  mov     r8d, eax
0x180039416  add     rax, rdx
0x180039419  jz      loc_18003966B
0x18003941f  sub     rcx, r8
0x180039422  shr     rcx, 1
0x180039425  cmp     rcx, 7FFFFFFFh
0x18003942c  ja      loc_18003966B
0x180039432  test    rcx, rcx
0x180039435  jz      short loc_180039447
0x180039437  cmp     word ptr [rax], 0
0x18003943b  jz      short loc_180039447
0x18003943d  add     rax, 2
0x180039441  sub     rcx, 1
  ... truncated ...
```
