# CThemePack::LoadFiles(ITheme *,ushort const *)

- ea: `0x180066168`
- end: `0x180066d95`
- name: `?LoadFiles@CThemePack@@QEAAJPEAUITheme@@PEBG@Z`
- size: `3117`
- prototype: `__int64 __fastcall(CThemePack *__hidden this, struct ITheme *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180062c40`

## callees

- `0x180008dd8`
- `0x18000ab00`
- `0x18000ab10`
- `0x1800358c0`
- `0x180036318`
- `0x180052974`
- `0x180062bbc`
- `0x180065ce8`
- `0x180065dc0`
- `0x180066168`
- `0x180066fd0`
- `0x180067010`
- `0x180067570`
- `0x1800678b4`
- `0x180068a1c`
- `0x180068c08`
- `0x18006d010`

## import_xrefs

- `SHCORE!__imp_SHWindowsPolicy` at `0x18006628f`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18006628f`
- `SHLWAPI!PathFindFileNameW` at `0x180066397`
- `SHLWAPI!PathFindFileNameW` at `0x180066397`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180066adf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180066adf`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180066865`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180066865`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066567`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066572`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800667fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066c24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066567`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066572`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800667fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066c24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066212`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066236`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066cd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066d04`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066d2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066d58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066212`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066236`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066cd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066d04`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066d2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066d58`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180066c73`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180066c73`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800662f0`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800662f0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800662d3`
- `OLEAUT32!__imp_SysAllocString` at `0x1800662d3`
- `OLEAUT32!__imp_SysFreeString` at `0x18006634e`
- `OLEAUT32!__imp_SysFreeString` at `0x18006681b`
- `OLEAUT32!__imp_SysFreeString` at `0x180066965`
- `OLEAUT32!__imp_SysFreeString` at `0x180066970`
- `OLEAUT32!__imp_SysFreeString` at `0x180066a4e`
- `OLEAUT32!__imp_SysFreeString` at `0x180066a59`
- `OLEAUT32!__imp_SysFreeString` at `0x180066bb7`
- `OLEAUT32!__imp_SysFreeString` at `0x180066bef`
- `OLEAUT32!__imp_SysFreeString` at `0x180066c87`
- `OLEAUT32!__imp_SysFreeString` at `0x180066c9f`
- `OLEAUT32!__imp_SysFreeString` at `0x18006634e`
- `OLEAUT32!__imp_SysFreeString` at `0x18006681b`
- `OLEAUT32!__imp_SysFreeString` at `0x180066965`
- `OLEAUT32!__imp_SysFreeString` at `0x180066970`
- `OLEAUT32!__imp_SysFreeString` at `0x180066a4e`
- `OLEAUT32!__imp_SysFreeString` at `0x180066a59`
- `OLEAUT32!__imp_SysFreeString` at `0x180066bb7`
- `OLEAUT32!__imp_SysFreeString` at `0x180066bef`
- `OLEAUT32!__imp_SysFreeString` at `0x180066c87`
- `OLEAUT32!__imp_SysFreeString` at `0x180066c9f`

## pseudocode

```c
__int64 __fastcall CThemePack::LoadFiles(LPCWSTR *this, OLECHAR *a2, const unsigned __int16 *a3)
{
  BSTR v4; // rsi
  int TempFile; // ebx
  unsigned int v7; // r8d
  unsigned int v8; // r9d
  unsigned int v9; // r8d
  unsigned int v10; // r9d
  unsigned int i; // r14d
  __int64 v12; // r15
  _QWORD *v13; // rsi
  void *v14; // rcx
  WCHAR *v15; // rcx
  LPCWSTR *v16; // r13
  struct IUnknown *v17; // rdx
  unsigned int v18; // r8d
  const unsigned __int16 *v19; // rcx
  const WCHAR *v21; // rax
  void (__fastcall *v22)(BSTR, _QWORD); // rbx
  _QWORD *v23; // rax
  const unsigned __int16 *v24; // rdx
  int v25; // ebx
  unsigned __int16 *v26; // r14
  const unsigned __int16 *FileNameW; // rax
  unsigned int v28; // r15d
  __int64 v29; // rax
  unsigned int v30; // r14d
  unsigned int v31; // eax
  int v32; // ecx
  unsigned int v33; // esi
  int v34; // ecx
  unsigned int v35; // r14d
  unsigned int v36; // ecx
  CThemePack *v37; // rcx
  int v38; // eax
  __int64 v39; // rax
  const unsigned __int16 *v40; // rdx
  int (__fastcall *v41)(BSTR, unsigned int *); // rax
  unsigned int v42; // eax
  __int64 v43; // r9
  int v44; // eax
  CThemePack *v45; // rcx
  int v46; // eax
  bool v47; // r9
  const unsigned __int16 *v48; // rdx
  __int64 v49; // rax
  int v50; // r14d
  OLECHAR *v51; // rbx
  char *v52; // r8
  int v53; // r14d
  OLECHAR *v54; // rbx
  char *v55; // r8
  __int64 v56; // rax
  WCHAR *v57; // r14
  const WCHAR *v58; // r8
  int v59; // eax
  __int64 v60; // rax
  BSTR v61; // rbx
  OLECHAR *v62; // rcx
  void (__fastcall *v63)(BSTR, _QWORD, _QWORD); // rbx
  _QWORD *v64; // rax
  __int64 v65; // rax
  unsigned int j; // r14d
  __int64 v67; // r15
  _QWORD *v68; // rsi
  void *v69; // rcx
  WCHAR *v70; // rcx
  unsigned int k; // r14d
  __int64 v72; // r15
  _QWORD *v73; // rsi
  void *v74; // rcx
  WCHAR *v75; // rcx
  unsigned int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  unsigned int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  unsigned int *v78; // [rsp+28h] [rbp-D8h]
  unsigned int *v79; // [rsp+28h] [rbp-D8h]
  unsigned int v80; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-C0h] BYREF
  struct CThemePack::FILE_INFO *v83; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v84; // [rsp+50h] [rbp-B0h] BYREF
  BSTR v85; // [rsp+58h] [rbp-A8h] BYREF
  BSTR v86; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v87; // [rsp+68h] [rbp-98h] BYREF
  BSTR v88; // [rsp+70h] [rbp-90h] BYREF
  int v89; // [rsp+78h] [rbp-88h]
  GUID Buf1; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR psz[264]; // [rsp+90h] [rbp-70h] BYREF

  v86 = a2;
  v4 = a2;
  if ( !a2 )
    return (unsigned int)-2147467259;
  TempFile = CThemePack::ClearFileList((CThemePack *)this);
  if ( TempFile >= 0 )
  {
    TempFile = CByteHashTable::Create(
                 (CByteHashTable *)(this + 1),
                 0x3E8u,
                 v7,
                 v8,
                 bIgnoreCase,
                 (unsigned int (*)(const unsigned __int8 *, unsigned int, unsigned int))v78);
    if ( TempFile >= 0 )
    {
      TempFile = CByteHashTable::Create(
                   (CByteHashTable *)(this + 6),
                   0x3E8u,
                   v9,
                   v10,
                   bIgnoreCasea,
                   (unsigned int (*)(const unsigned __int8 *, unsigned int, unsigned int))v79);
      if ( TempFile < 0 )
      {
        for ( i = 0; i < *((_DWORD *)this + 5); *(_QWORD *)&this[3][4 * v12] = 0 )
        {
          v12 = i;
          v13 = *(_QWORD **)&this[3][4 * i];
          while ( v13 )
          {
            v14 = v13;
            v13 = (_QWORD *)*v13;
            LocalFree(v14);
          }
          ++i;
        }
        v15 = (WCHAR *)this[3];
        this[2] = 0;
        LocalFree(v15);
        this[3] = 0;
        return (unsigned int)TempFile;
      }
      v16 = this + 12;
      TempFile = (*(__int64 (__fastcall **)(BSTR, __int64, char *))(*(_QWORD *)v4 + 288LL))(
                   v4,
                   0xFFFFFFFFLL,
                   (char *)this + 96);
      if ( TempFile < 0 )
        goto LABEL_141;
      v89 = -1;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ThemeFileRemoteResource>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ThemeFileRemoteResource>::GetImpl'::`2'::impl) )
      {
        if ( !(unsigned int)SHWindowsPolicy(POLID_EnableThemeFileRemoteResource) )
        {
          v19 = *v16;
          v80 = -1;
          SHMapUrlToZoneEx(v19, v17, v18, &v80);
          if ( v80 > 2 )
            return 2147942405LL;
        }
      }
      TempFile = GetTempFile(psz, (unsigned __int64)v17);
      if ( TempFile < 0 )
        goto LABEL_140;
      v21 = SysAllocString(psz);
      this[11] = v21;
      if ( !v21 )
      {
        TempFile = -2147024882;
        goto LABEL_140;
      }
      if ( !CopyFileW(*v16, v21, 0) )
      {
        TempFile = -2147467259;
        goto LABEL_138;
      }
      TempFile = (*(__int64 (__fastcall **)(BSTR, LPCWSTR))(*(_QWORD *)v4 + 296LL))(v4, this[11]);
      if ( TempFile < 0 )
        goto LABEL_136;
      if ( (*((_BYTE *)this + 2036) & 0x10) == 0 )
      {
        v22 = *(void (__fastcall **)(BSTR, _QWORD))(*(_QWORD *)v4 + 32LL);
        v23 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, a3);
        v22(v4, *v23);
        SysFreeString(bstrString);
      }
      v24 = this[11];
      v83 = 0;
      v25 = CThemePack::_AddFileToList((CThemePack *)this, v24, 0, &v83);
      if ( v25 >= 0 )
      {
        v26 = (unsigned __int16 *)((char *)v83 + 528);
        v25 = CHashTable<int,unsigned short>::DeletePtr(this + 6, (char *)v83 + 528);
        if ( v25 >= 0 )
        {
          FileNameW = PathFindFileNameW(*v16);
          v25 = StringCchCopyW(v26, 0x104u, FileNameW);
          if ( v25 >= 0 )
            v25 = CHashTable<int,unsigned short>::SetPtr(this + 6, v26);
        }
      }
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)v4 + 552LL))(v4);
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)v4 + 560LL))(v4);
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)v4 + 216LL))(v4);
      v28 = 0;
      *((_DWORD *)this + 508) = 0;
      if ( v25 < 0 )
        goto LABEL_87;
      v29 = *(_QWORD *)v4;
      bstrString = 0;
      if ( (*(int (__fastcall **)(BSTR, BSTR *))(v29 + 224))(v4, &bstrString) < 0 )
      {
        v30 = 0;
        (*(void (__fastcall **)(BSTR, _QWORD))(*(_QWORD *)v4 + 232LL))(v4, 0);
        v39 = *(_QWORD *)v4;
        goto LABEL_65;
      }
      v16 = 0;
      v84 = (*(__int64 (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 72LL))(bstrString);
      v30 = v84;
      if ( v84 )
        goto LABEL_51;
      v88 = 0;
      v25 = (*(__int64 (__fastcall **)(BSTR, BSTR *))(*(_QWORD *)bstrString + 88LL))(bstrString, &v88);
      if ( v25 < 0 )
        goto LABEL_51;
      v31 = (*(__int64 (__fastcall **)(BSTR))(*(_QWORD *)v88 + 24LL))(v88);
      v32 = *((_DWORD *)this + 509);
      LODWORD(v85) = v31;
      if ( (v32 & 1) != 0 )
      {
        v33 = 1;
        v34 = v32 & 2;
      }
      else
      {
        v34 = v32 & 2;
        if ( !v34 )
        {
          v33 = v31;
          v35 = 0;
          goto LABEL_37;
        }
        v33 = 20;
      }
      v35 = 0;
      if ( v34 == 2 )
      {
        v36 = 0;
        v25 = 0;
        v89 = 0;
        while ( 1 )
        {
LABEL_38:
          if ( v28 >= v31 || *((_DWORD *)this + 508) >= v33 || v35 >= v36 )
          {
LABEL_48:
            (*(void (__fastcall **)(BSTR))(*(_QWORD *)v88 + 16LL))(v88);
            v4 = v86;
            v28 = 0;
            if ( v25 >= 0 )
              (*(void (__fastcall **)(BSTR, const WCHAR *))(*(_QWORD *)v86 + 248LL))(v86, L"DesktopBackground");
            v30 = v84;
LABEL_51:
            (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
            if ( v25 >= 0 )
            {
              v39 = *(_QWORD *)v4;
              if ( v16 )
              {
                (*(void (__fastcall **)(BSTR, LPCWSTR *))(v39 + 176))(v4, v16 + 66);
                if ( (*((_BYTE *)this + 2036) & 1) != 0 )
                  v25 = (*(__int64 (__fastcall **)(BSTR, _QWORD))(*(_QWORD *)v4 + 232LL))(v4, 0);
                goto LABEL_87;
              }
LABEL_65:
              v41 = *(int (__fastcall **)(BSTR, unsigned int *))(v39 + 432);
              v80 = 0;
              if ( v41(v4, &v80) >= 0 )
              {
                v42 = v80;
              }
              else
              {
                v42 = 0;
                v80 = 0;
              }
              v43 = *(_QWORD *)v4;
              v85 = 0;
              if ( v42 )
                v44 = (*(__int64 (__fastcall **)(BSTR, __int64, BSTR *))(v43 + 448))(v4, 1, &v85);
              else
                v44 = (*(__int64 (__fastcall **)(BSTR, BSTR *))(v43 + 168))(v4, &v85);
              if ( v30 || v44 < 0 || !ATL::CComBSTR::Length((ATL::CComBSTR *)&v85) )
              {
                (*(void (__fastcall **)(BSTR, _QWORD))(*(_QWORD *)v4 + 176LL))(v4, 0);
              }
              else if ( (unsigned int)VerifyResourceFile(v85, 0) )
              {
                v46 = *((_DWORD *)this + 509);
                bstrString = 0;
                v84 = 0;
                if ( (v46 & 1) != 0 )
                {
                  v47 = 0;
                  goto LABEL_79;
                }
                if ( (v46 & 2) == 0 )
                {
LABEL_81:
                  v48 = v85;
                  goto LABEL_82;
                }
                v47 = 1;
LABEL_79:
                v25 = CThemePack::_CompressImageForRoamingTheme(v45, v85, 1, v47, &bstrString, &v84);
                if ( v25 >= 0 )
                {
                  v48 = bstrString;
                  if ( !bstrString )
                    goto LABEL_81;
LABEL_82:
                  v25 = CThemePack::_AddFileToList((CThemePack *)this, v48, L"DesktopBackground", &v83);
                  if ( v25 >= 0 )
                  {
                    (*(void (__fastcall **)(BSTR, char *))(*(_QWORD *)v4 + 176LL))(v4, (char *)v83 + 528);
                    ++*((_DWORD *)this + 508);
                  }
                }
                CoTaskMemFree(bstrString);
              }
              SysFreeString(v85);
            }
LABEL_87:
            v49 = *(_QWORD *)v4;
            LOBYTE(v16) = 0;
            v80 = (unsigned int)v16;
            Buf1 = 0;
            if ( ((*(int (__fastcall **)(BSTR, GUID *))(v49 + 120))(v4, &Buf1) < 0 || !memcmp_0(
                                                                                         &Buf1,
                                                                                         &GUID_NULL,
                                                                                         0x10u))
              && CoCreateGuid(&Buf1) >= 0 )
            {
              LODWORD(v16) = (*(int (__fastcall **)(BSTR, GUID *))(*(_QWORD *)v4 + 128LL))(v4, &Buf1) >= 0;
              v80 = (unsigned int)v16;
            }
            if ( (*((_BYTE *)this + 2036) & 3) != 0 || v25 < 0 )
              goto LABEL_132;
            v50 = 0;
            if ( !*(_WORD *)c_rgszDesktopIcons )
              goto LABEL_103;
            while ( 2 )
            {
              pv = 0;
              ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v86, (const unsigned __int16 *)(&c_rgszDesktopIcons)[v50]);
              v51 = v86;
              if ( (*(int (__fastcall **)(BSTR, BSTR, __int64, LPVOID *))(*(_QWORD *)v4 + 360LL))(v4, v86, 1, &pv) >= 0
                && ATL::CComBSTR::Length((ATL::CComBSTR *)&pv) )
              {
                if ( (unsigned int)VerifyResourceFile((const unsigned __int16 *)pv, 1)
                  && CThemePack::_AddFileToList((CThemePack *)this, (const unsigned __int16 *)pv, 0, &v83) >= 0 )
                {
                  v52 = (char *)v83 + 528;
                  goto LABEL_100;
                }
              }
              else
              {
                v52 = 0;
LABEL_100:
                (*(void (__fastcall **)(BSTR, OLECHAR *, char *))(*(_QWORD *)v4 + 376LL))(v4, v51, v52);
              }
              SysFreeString(v51);
              SysFreeString((BSTR)pv);
              if ( !*(_WORD *)(&c_rgszDesktopIcons)[++v50] )
              {
                LOBYTE(v16) = v80;
LABEL_103:
                v53 = 0;
                if ( !aArrow[0] )
                  goto LABEL_113;
                while ( 2 )
                {
                  pv = 0;
                  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v86, off_18006E940[v53]);
                  v54 = v86;
                  if ( (*(int (__fastcall **)(BSTR, BSTR, LPVOID *))(*(_QWORD *)v4 + 304LL))(v4, v86, &pv) >= 0
                    && ATL::CComBSTR::Length((ATL::CComBSTR *)&pv) )
                  {
                    if ( (unsigned int)VerifyResourceFile((const unsigned __int16 *)pv, 2)
                      && CThemePack::_AddFileToList((CThemePack *)this, (const unsigned __int16 *)pv, 0, &v83) >= 0 )
                    {
                      v55 = (char *)v83 + 528;
                      goto LABEL_110;
                    }
                  }
                  else
                  {
                    v55 = 0;
LABEL_110:
                    (*(void (__fastcall **)(BSTR, OLECHAR *, char *))(*(_QWORD *)v4 + 312LL))(v4, v54, v55);
                  }
                  SysFreeString(v54);
                  SysFreeString((BSTR)pv);
                  if ( !*off_18006E940[++v53] )
                  {
                    LOBYTE(v16) = v80;
LABEL_113:
                    v56 = *(_QWORD *)v4;
                    bstrString = 0;
                    if ( (*(int (__fastcall **)(BSTR, BSTR *))(v56 + 352))(v4, &bstrString) < 0 )
                      goto LABEL_132;
                    v57 = bstrString;
                    if ( !*bstrString )
                      goto LABEL_131;
                    while ( 1 )
                    {
                      v58 = (const WCHAR *)*((_QWORD *)&c_rgThemeSoundsValues + 2 * (int)v28);
                      if ( !*v58 )
                        goto LABEL_126;
                      v59 = CompareStringOrdinal(v57, -1, v58, -1, 1);
                      if ( v59 == 3 )
                      {
                        ++v28;
                        continue;
                      }
                      if ( v59 == 2 )
                      {
                        ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v86, v57);
                        v60 = *(_QWORD *)v4;
                        pv = 0;
                        v61 = v86;
                        if ( (*(int (__fastcall **)(BSTR, BSTR, _QWORD, LPVOID *))(v60 + 336))(
                               v4,
                               v86,
                               (unsigned int)dword_18006FAF8[4 * v28],
                               &pv) >= 0
                          && ATL::CComBSTR::Length((ATL::CComBSTR *)&pv)
                          && (unsigned int)VerifyResourceFile((const unsigned __int16 *)pv, 3)
                          && CThemePack::_AddFileToList((CThemePack *)this, (const unsigned __int16 *)pv, 0, &v83) >= 0
                          && (*(int (__fastcall **)(BSTR, BSTR, char *))(*(_QWORD *)v4 + 344LL))(
                               v4,
                               v61,
                               (char *)v83 + 528) < 0 )
                        {
                          (*(void (__fastcall **)(BSTR, BSTR, _QWORD))(*(_QWORD *)v4 + 344LL))(v4, v61, 0);
                        }
                        SysFreeString((BSTR)pv);
                        v62 = v61;
                      }
                      else
                      {
LABEL_126:
                        v63 = *(void (__fastcall **)(BSTR, _QWORD, _QWORD))(*(_QWORD *)v4 + 344LL);
                        v64 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v88, v57);
                        v63(v4, *v64, 0);
                        v62 = v88;
                      }
                      SysFreeString(v62);
                      v65 = -1;
                      do
                        ++v65;
                      while ( v57[v65] );
                      v57 += v65 + 1;
                      if ( !*v57 )
                      {
                        v57 = bstrString;
                        LOBYTE(v16) = v80;
LABEL_131:
                        CoTaskMemFree(v57);
LABEL_132:
                        TempFile = (*(__int64 (__fastcall **)(BSTR, LPCWSTR))(*(_QWORD *)v4 + 296LL))(v4, this[12]);
                        if ( TempFile >= 0 )
                        {
                          if ( (_BYTE)v16 )
                            (*(void (__fastcall **)(BSTR, GUID *))(*(_QWORD *)v4 + 128LL))(v4, &Buf1);
LABEL_142:
                          for ( j = 0; j < *((_DWORD *)this + 5); *(_QWORD *)&this[3][4 * v67] = 0 )
                          {
                            v67 = j;
                            v68 = *(_QWORD **)&this[3][4 * j];
                            while ( v68 )
                            {
                              v69 = v68;
                              v68 = (_QWORD *)*v68;
                              LocalFree(v69);
                            }
                            ++j;
                          }
                          v70 = (WCHAR *)this[3];
                          this[2] = 0;
                          LocalFree(v70);
                          this[3] = 0;
                          for ( k = 0; k < *((_DWORD *)this + 15); *(_QWORD *)&this[8][4 * v72] = 0 )
                          {
                            v72 = k;
                            v73 = *(_QWORD **)&this[8][4 * k];
                            while ( v73 )
                            {
                              v74 = v73;
                              v73 = (_QWORD *)*v73;
                              LocalFree(v74);
                            }
                            ++k;
                          }
                          v75 = (WCHAR *)this[8];
                          this[7] = 0;
                          LocalFree(v75);
                          this[8] = 0;
                          return (unsigned int)TempFile;
                        }
                        v16 = this + 12;
LABEL_136:
                        DeleteFileW(this[11]);
LABEL_138:
                        SysFreeString((BSTR)this[11]);
                        this[11] = 0;
LABEL_140:
                        SysFreeString((BSTR)*v16);
                        *v16 = 0;
LABEL_141:
                        CThemePack::ClearFileList((CThemePack *)this);
                        goto LABEL_142;
                      }
                    }
                  }
                  continue;
                }
              }
              continue;
            }
          }
          v87 = 0;
          v25 = (*(__int64 (__fastcall **)(BSTR, _QWORD, unsigned __int16 **))(*(_QWORD *)v88 + 32LL))(v88, v28, &v87);
          if ( v25 >= 0 )
            break;
LABEL_47:
          CoTaskMemFree(v87);
          v31 = (unsigned int)v85;
          ++v28;
          v36 = v89;
          if ( v25 < 0 )
            goto LABEL_48;
        }
        v38 = *((_DWORD *)this + 509);
        pv = 0;
        v80 = 0;
        if ( (v38 & 1) != 0 )
        {
          v25 = CThemePack::_CompressImageForRoamingTheme(v37, v87, 1, 0, (unsigned __int16 **)&pv, &v80);
          if ( v25 < 0 )
            goto LABEL_44;
        }
        else if ( (v38 & 2) != 0 )
        {
          v25 = CThemePack::_CompressImageForRoamingTheme(v37, v87, v28 == 0, 1, (unsigned __int16 **)&pv, &v80);
          if ( v25 < 0 )
            goto LABEL_44;
          v35 += v80;
        }
        v40 = v87;
        if ( pv )
          v40 = (const unsigned __int16 *)pv;
        v25 = CThemePack::_AddFileToList((CThemePack *)this, v40, L"DesktopBackground", &v83);
        if ( v25 >= 0 )
        {
          if ( !v16 )
            v16 = (LPCWSTR *)v83;
          ++*((_DWORD *)this + 508);
          goto LABEL_46;
        }
LABEL_44:
        if ( (*((_BYTE *)this + 2036) & 2) != 0 )
          v25 = 0;
LABEL_46:
        CoTaskMemFree(pv);
        goto LABEL_47;
      }
LABEL_37:
      v36 = -1;
      goto LABEL_38;
    }
  }
  return (unsigned int)TempFile;
}

```

## disassembly

```asm
0x180066168  mov     [rsp-8+arg_18], rbx
0x18006616d  push    rbp
0x18006616e  push    rsi
0x18006616f  push    rdi
0x180066170  push    r12
0x180066172  push    r13
0x180066174  push    r14
0x180066176  push    r15
0x180066178  lea     rbp, [rsp-1B0h]
0x180066180  sub     rsp, 2B0h
0x180066187  mov     rax, cs:__security_cookie
0x18006618e  xor     rax, rsp
0x180066191  mov     [rbp+1E0h+var_40], rax
0x180066198  xor     r13d, r13d
0x18006619b  mov     [rsp+2E0h+var_280], rdx
0x1800661a0  mov     r14, r8
0x1800661a3  mov     rsi, rdx
0x1800661a6  mov     rdi, rcx
0x1800661a9  test    rdx, rdx
0x1800661ac  jz      loc_180066D64
0x1800661b2  call    ?ClearFileList@CThemePack@@QEAAJXZ; CThemePack::ClearFileList(void)
0x1800661b7  mov     ebx, eax
0x1800661b9  test    eax, eax
0x1800661bb  js      loc_180066D69
0x1800661c1  mov     r12d, 3E8h
0x1800661c7  lea     rcx, [rdi+8]; this
0x1800661cb  mov     edx, r12d; unsigned int
0x1800661ce  call    ?Create@CByteHashTable@@QEAAJIIIIP6AIPEBEII@Z@Z; CByteHashTable::Create(uint,uint,uint,uint,uint (*)(uchar const *,uint,uint))
0x1800661d3  mov     ebx, eax
0x1800661d5  test    eax, eax
0x1800661d7  js      loc_180066D69
0x1800661dd  lea     r15, [rdi+30h]
0x1800661e1  mov     edx, r12d; unsigned int
0x1800661e4  mov     rcx, r15; this
0x1800661e7  call    ?Create@CByteHashTable@@QEAAJIIIIP6AIPEBEII@Z@Z; CByteHashTable::Create(uint,uint,uint,uint,uint (*)(uchar const *,uint,uint))
0x1800661ec  mov     ebx, eax
0x1800661ee  test    eax, eax
0x1800661f0  jns     short loc_180066245
0x1800661f2  mov     r14d, r13d
0x1800661f5  cmp     [rdi+14h], r13d
0x1800661f9  jbe     short loc_18006622E
0x1800661fb  lea     r12d, [r13+1]
0x1800661ff  mov     rax, [rdi+18h]
0x180066203  mov     r15d, r14d
0x180066206  mov     rsi, [rax+r15*8]
0x18006620a  jmp     short loc_180066218
0x18006620c  mov     rcx, rsi; hMem
0x18006620f  mov     rsi, [rsi]
0x180066212  call    cs:__imp_LocalFree
0x180066218  test    rsi, rsi
0x18006621b  jnz     short loc_18006620C
0x18006621d  mov     rax, [rdi+18h]
0x180066221  add     r14d, r12d
0x180066224  mov     [rax+r15*8], r13
0x180066228  cmp     r14d, [rdi+14h]
0x18006622c  jb      short loc_1800661FF
0x18006622e  mov     rcx, [rdi+18h]; hMem
0x180066232  mov     [rdi+10h], r13
0x180066236  call    cs:__imp_LocalFree
0x18006623c  mov     [rdi+18h], r13
0x180066240  jmp     loc_180066D69
0x180066245  mov     rax, [rsi]
0x180066248  lea     r13, [rdi+60h]
0x18006624c  or      edx, 0FFFFFFFFh
0x18006624f  mov     r8, r13
0x180066252  mov     rcx, rsi
0x180066255  mov     rax, [rax+120h]
0x18006625c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066261  mov     ebx, eax
0x180066263  mov     r12d, 1
0x180066269  test    eax, eax
0x18006626b  js      loc_180066CAF
0x180066271  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ThemeFileRemoteResource@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ThemeFileRemoteResource@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ThemeFileRemoteResource> `wil::Feature<__WilFeatureTraits_Feature_ThemeFileRemoteResource>::GetImpl(void)'::`2'::impl
0x180066278  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ThemeFileRemoteResource@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ThemeFileRemoteResource>::__private_IsEnabled(void)
0x18006627d  or      ebx, 0FFFFFFFFh
0x180066280  mov     [rsp+2E0h+var_268], ebx
0x180066284  test    al, al
0x180066286  jz      short loc_1800662BC
0x180066288  lea     rcx, POLID_EnableThemeFileRemoteResource
0x18006628f  call    cs:__imp_SHWindowsPolicy
0x180066295  test    eax, eax
0x180066297  jnz     short loc_1800662BC
0x180066299  mov     rcx, [r13+0]; unsigned __int16 *
0x18006629d  lea     r9, [rsp+2E0h+var_2B0]; unsigned int *
0x1800662a2  mov     [rsp+2E0h+var_2B0], ebx
0x1800662a6  call    ?SHMapUrlToZoneEx@@YAJPEBGPEAUIUnknown@@KPEAK@Z; SHMapUrlToZoneEx(ushort const *,IUnknown *,ulong,ulong *)
0x1800662ab  cmp     [rsp+2E0h+var_2B0], 2
0x1800662b0  jbe     short loc_1800662BC
0x1800662b2  mov     eax, 80070005h
0x1800662b7  jmp     loc_180066D6B
0x1800662bc  lea     rcx, [rbp+1E0h+psz]; lpTempFileName
0x1800662c0  call    ?GetTempFile@@YAJPEAG_K@Z; GetTempFile(ushort *,unsigned __int64)
0x1800662c5  mov     ebx, eax
0x1800662c7  test    eax, eax
0x1800662c9  js      loc_180066C98
0x1800662cf  lea     rcx, [rbp+1E0h+psz]; psz
0x1800662d3  call    cs:__imp_SysAllocString
0x1800662d9  mov     [rdi+58h], rax
0x1800662dd  test    rax, rax
0x1800662e0  jz      loc_180066C93
0x1800662e6  mov     rcx, [r13+0]; lpExistingFileName
0x1800662ea  xor     r8d, r8d; bFailIfExists
0x1800662ed  mov     rdx, rax; lpNewFileName
0x1800662f0  call    cs:__imp_CopyFileW
0x1800662f6  test    eax, eax
0x1800662f8  jz      loc_180066C7B
0x1800662fe  mov     rax, [rsi]
0x180066301  mov     rcx, rsi
0x180066304  mov     rdx, [rdi+58h]
0x180066308  mov     rax, [rax+128h]
0x18006630f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066314  mov     ebx, eax
0x180066316  test    eax, eax
0x180066318  js      loc_180066C6C
0x18006631e  test    byte ptr [rdi+7F4h], 10h
0x180066325  jnz     short loc_180066354
0x180066327  mov     rax, [rsi]
0x18006632a  lea     rcx, [rsp+2E0h+bstrString]; this
0x18006632f  mov     rdx, r14; unsigned __int16 *
0x180066332  mov     rbx, [rax+20h]
0x180066336  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18006633b  mov     rcx, rsi
0x18006633e  mov     rdx, [rax]
0x180066341  mov     rax, rbx
0x180066344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066349  mov     rcx, [rsp+2E0h+bstrString]; bstrString
0x18006634e  call    cs:__imp_SysFreeString
0x180066354  mov     rdx, [rdi+58h]; unsigned __int16 *
0x180066358  lea     r9, [rsp+2E0h+var_298]; struct CThemePack::FILE_INFO **
0x18006635d  xor     r14d, r14d
0x180066360  xor     r8d, r8d; unsigned __int16 *
0x180066363  mov     rcx, rdi; this
0x180066366  mov     [rsp+2E0h+var_298], r14
0x18006636b  call    ?_AddFileToList@CThemePack@@AEAAJPEBG0PEAPEAUFILE_INFO@1@@Z; CThemePack::_AddFileToList(ushort const *,ushort const *,CThemePack::FILE_INFO * *)
0x180066370  mov     ebx, eax
0x180066372  test    eax, eax
0x180066374  js      short loc_1800663C0
0x180066376  mov     r14, [rsp+2E0h+var_298]
0x18006637b  mov     rcx, r15
0x18006637e  add     r14, 210h
0x180066385  mov     rdx, r14
0x180066388  call    ?DeletePtr@?$CHashTable@HG@@QEAAJPEBGPEAPEAH@Z; CHashTable<int,ushort>::DeletePtr(ushort const *,int * *)
0x18006638d  mov     ebx, eax
0x18006638f  test    eax, eax
0x180066391  js      short loc_1800663C0
0x180066393  mov     rcx, [r13+0]; pszPath
0x180066397  call    cs:__imp_PathFindFileNameW
0x18006639d  mov     edx, 104h; unsigned __int64
0x1800663a2  mov     rcx, r14; unsigned __int16 *
0x1800663a5  mov     r8, rax; unsigned __int16 *
0x1800663a8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800663ad  mov     ebx, eax
0x1800663af  test    eax, eax
0x1800663b1  js      short loc_1800663C0
0x1800663b3  mov     rdx, r14
0x1800663b6  mov     rcx, r15
0x1800663b9  call    ?SetPtr@?$CHashTable@HG@@QEAAJPEBGPEAHPEAPEAH@Z; CHashTable<int,ushort>::SetPtr(ushort const *,int *,int * *)
0x1800663be  mov     ebx, eax
0x1800663c0  mov     rax, [rsi]
0x1800663c3  mov     rcx, rsi
0x1800663c6  mov     rax, [rax+228h]
0x1800663cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800663d2  mov     rax, [rsi]
0x1800663d5  mov     rcx, rsi
0x1800663d8  mov     rax, [rax+230h]
0x1800663df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800663e4  mov     rax, [rsi]
0x1800663e7  mov     rcx, rsi
0x1800663ea  mov     rax, [rax+0D8h]
0x1800663f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800663f6  xor     r15d, r15d
0x1800663f9  mov     [rdi+7F0h], r15d
0x180066400  test    ebx, ebx
0x180066402  js      loc_180066821
0x180066408  mov     rax, [rsi]
0x18006640b  lea     rdx, [rsp+2E0h+bstrString]
0x180066410  mov     rcx, rsi
0x180066413  mov     [rsp+2E0h+bstrString], r15
0x180066418  mov     rax, [rax+0E0h]
0x18006641f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066424  test    eax, eax
0x180066426  js      loc_1800666AE
0x18006642c  mov     rcx, [rsp+2E0h+bstrString]
0x180066431  mov     r13d, r15d
0x180066434  mov     rax, [rcx]
0x180066437  mov     rax, [rax+48h]
0x18006643b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066440  mov     [rsp+2E0h+var_290], eax
0x180066444  mov     r14d, eax
0x180066447  test    eax, eax
0x180066449  jnz     loc_1800665C6
0x18006644f  mov     r8, [rsp+2E0h+bstrString]
0x180066454  lea     rdx, [rsp+2E0h+var_270]
0x180066459  mov     [rsp+2E0h+var_270], r15
0x18006645e  mov     rcx, [r8]
0x180066461  mov     rax, [rcx+58h]
0x180066465  mov     rcx, r8
0x180066468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006646d  mov     ebx, eax
0x18006646f  test    eax, eax
0x180066471  js      loc_1800665C6
0x180066477  mov     rcx, [rsp+2E0h+var_270]
0x18006647c  mov     rax, [rcx]
0x18006647f  mov     rax, [rax+18h]
0x180066483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066488  mov     ecx, [rdi+7F4h]
0x18006648e  mov     dword ptr [rsp+2E0h+var_288], eax
0x180066492  test    r12b, cl
0x180066495  jz      short loc_18006649F
0x180066497  mov     esi, r12d
0x18006649a  and     ecx, 2
0x18006649d  jmp     short loc_1800664A9
0x18006649f  and     ecx, 2
0x1800664a2  jz      short loc_1800664BD
0x1800664a4  mov     esi, 14h
0x1800664a9  mov     r14d, r15d
0x1800664ac  cmp     ecx, 2
0x1800664af  jnz     short loc_1800664C2
0x1800664b1  mov     ecx, r15d
0x1800664b4  mov     ebx, r15d
0x1800664b7  mov     [rsp+2E0h+var_268], ecx
0x1800664bb  jmp     short loc_1800664C5
0x1800664bd  mov     esi, eax
0x1800664bf  mov     r14d, r15d
0x1800664c2  or      ecx, 0FFFFFFFFh
0x1800664c5  cmp     r15d, eax
0x1800664c8  jnb     loc_18006658B
0x1800664ce  cmp     [rdi+7F0h], esi
0x1800664d4  jnb     loc_18006658B
0x1800664da  cmp     r14d, ecx
0x1800664dd  jnb     loc_18006658B
0x1800664e3  mov     rcx, [rsp+2E0h+var_270]
0x1800664e8  lea     r8, [rsp+2E0h+var_278]
0x1800664ed  mov     [rsp+2E0h+var_278], 0
0x1800664f6  mov     edx, r15d
0x1800664f9  mov     rax, [rcx]
0x1800664fc  mov     rax, [rax+20h]
0x180066500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066505  xor     edx, edx
0x180066507  mov     ebx, eax
0x180066509  test    eax, eax
0x18006650b  js      short loc_18006656D
0x18006650d  mov     eax, [rdi+7F4h]
0x180066513  mov     [rsp+2E0h+pv], rdx
0x180066518  mov     [rsp+2E0h+var_2B0], edx
0x18006651c  test    r12b, al
0x18006651f  jz      loc_180066629
0x180066525  mov     rdx, [rsp+2E0h+var_278]; unsigned __int16 *
0x18006652a  lea     rax, [rsp+2E0h+var_2B0]
0x18006652f  mov     [rsp+2E0h+var_2B8], rax; unsigned int *
0x180066534  xor     r9d, r9d; bool
0x180066537  lea     rax, [rsp+2E0h+pv]
0x18006653c  mov     r8b, r12b; bool
0x18006653f  mov     qword ptr [rsp+2E0h+bIgnoreCase], rax; unsigned __int16 **
0x180066544  call    ?_CompressImageForRoamingTheme@CThemePack@@AEAAJPEBG_N1PEAPEAGPEAK@Z; CThemePack::_CompressImageForRoamingTheme(ushort const *,bool,bool,ushort * *,ulong *)
0x180066549  mov     ebx, eax
0x18006654b  test    eax, eax
0x18006654d  jns     loc_18006666A
0x180066553  test    byte ptr [rdi+7F4h], 2
0x18006655a  mov     eax, 0
0x18006655f  cmovnz  ebx, eax
0x180066562  mov     rcx, [rsp+2E0h+pv]; pv
0x180066567  call    cs:__imp_CoTaskMemFree
0x18006656d  mov     rcx, [rsp+2E0h+var_278]; pv
0x180066572  call    cs:__imp_CoTaskMemFree
0x180066578  mov     eax, dword ptr [rsp+2E0h+var_288]
0x18006657c  add     r15d, r12d
0x18006657f  mov     ecx, [rsp+2E0h+var_268]
0x180066583  test    ebx, ebx
0x180066585  jns     loc_1800664C5
0x18006658b  mov     rcx, [rsp+2E0h+var_270]
0x180066590  mov     rax, [rcx]
0x180066593  mov     rax, [rax+10h]
0x180066597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006659c  mov     rsi, [rsp+2E0h+var_280]
0x1800665a1  xor     r15d, r15d
0x1800665a4  test    ebx, ebx
0x1800665a6  js      short loc_1800665C1
0x1800665a8  mov     rax, [rsi]
0x1800665ab  lea     rdx, aDesktopbackgro; "DesktopBackground"
0x1800665b2  mov     rcx, rsi
0x1800665b5  mov     rax, [rax+0F8h]
0x1800665bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800665c1  mov     r14d, [rsp+2E0h+var_290]
0x1800665c6  mov     rcx, [rsp+2E0h+bstrString]
0x1800665cb  mov     rax, [rcx]
0x1800665ce  mov     rax, [rax+10h]
0x1800665d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800665d7  test    ebx, ebx
0x1800665d9  js      loc_180066821
0x1800665df  mov     rax, [rsi]
0x1800665e2  test    r13, r13
0x1800665e5  jz      loc_1800666C8
0x1800665eb  mov     rax, [rax+0B0h]
0x1800665f2  lea     rdx, [r13+210h]
0x1800665f9  mov     rcx, rsi
0x1800665fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066601  test    [rdi+7F4h], r12b
0x180066608  jz      loc_180066821
0x18006660e  mov     rax, [rsi]
  ... truncated ...
```
