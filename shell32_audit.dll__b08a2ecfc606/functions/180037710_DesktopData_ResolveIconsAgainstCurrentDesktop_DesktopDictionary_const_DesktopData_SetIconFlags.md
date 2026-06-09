# DesktopData::ResolveIconsAgainstCurrentDesktop(DesktopDictionary const *,DesktopData *,SetIconFlags)

- ea: `0x180037710`
- end: `0x1800385ff`
- name: `?ResolveIconsAgainstCurrentDesktop@DesktopData@@QEAAJPEBVDesktopDictionary@@PEAV1@W4SetIconFlags@@@Z`
- size: `3823`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18003314c`

## callees

- `0x180036784`
- `0x180037710`
- `0x180038608`
- `0x180038630`
- `0x18003a480`
- `0x18008a318`
- `0x18008a5f0`
- `0x180099e20`
- `0x1801015c4`
- `0x18010961c`
- `0x1801bce4c`
- `0x180249490`
- `0x180249c8c`
- `0x180249d64`
- `0x18024a53c`
- `0x18025cc2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x180037d5c`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800383f3`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x180037d5c`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800383f3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180037b8b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180037bd3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180037f2f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180037f9e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180037b8b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180037bd3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180037f2f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180037f9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003790c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003791c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003792c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038215`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038225`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038235`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038496`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800384b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003790c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003791c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003792c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038215`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038225`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038235`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038496`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800384b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037a31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037a4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037a5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037ccb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038311`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037a31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037a4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037a5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037ccb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038311`

## string_xrefs

- `0x1800378ae`: `shell\shell32\iconlayoutengine\Common\IconGridItem.h`
- `0x18003836c`: `shell\shell32\iconlayoutengine\Common\IconGridItem.h`
- `0x180038514`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800385c3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall DesktopData::ResolveIconsAgainstCurrentDesktop(DesktopData *a1, __int64 a2, DesktopData *a3)
{
  DesktopData *v3; // rsi
  DesktopData *v5; // rax
  unsigned __int64 v6; // r15
  unsigned __int64 i; // rbx
  int Workspace; // eax
  unsigned int v9; // edi
  unsigned __int64 v10; // r13
  unsigned __int64 j; // rbx
  int v12; // eax
  unsigned int v13; // edi
  __int64 v14; // rbx
  bool v15; // cf
  unsigned __int64 v16; // rbx
  unsigned __int64 *v17; // rax
  unsigned __int64 *v18; // rdi
  _QWORD *v19; // r14
  int v21; // ebx
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rbx
  unsigned __int64 v26; // rbx
  unsigned __int64 *v27; // rax
  unsigned __int64 *v28; // rdi
  _QWORD *v29; // r15
  unsigned __int64 v30; // r15
  struct IconGridItem **v31; // rax
  unsigned __int64 v32; // rdx
  unsigned __int64 v33; // r12
  struct WorkspaceData *v34; // rbx
  const struct IconGridItem *v35; // rsi
  const struct IconGridItem *v36; // r12
  DesktopData *v37; // rax
  struct IconGridItem *v38; // rbx
  unsigned __int64 v39; // r15
  unsigned __int64 v40; // r14
  unsigned __int64 m; // rbx
  const WCHAR *v42; // rcx
  __int64 v43; // rdi
  const WCHAR *v44; // r8
  int v45; // r9d
  __int64 v47; // rdx
  int v48; // eax
  const char *v49; // r9
  struct WorkspaceData *v50; // rax
  size_t v51; // rdx
  size_t v52; // r14
  struct WorkspaceData *v53; // rbx
  __int64 v54; // rcx
  _QWORD *v55; // rsi
  char *v56; // rdi
  __int64 v57; // rcx
  char *v58; // rax
  rsize_t v59; // r15
  char *v60; // rax
  char *v61; // rbx
  LPVOID *v62; // rdi
  __m128i si128; // xmm3
  struct IconGridItem **v64; // rsi
  _QWORD *v65; // r15
  unsigned __int64 v66; // r14
  unsigned __int64 ii; // rbx
  struct IconGridItem **v68; // rdi
  struct IconGridItem *v69; // r8
  __int64 v70; // rcx
  _QWORD *v71; // r14
  unsigned __int64 v72; // rsi
  unsigned __int64 jj; // rbx
  __int64 *v74; // rdi
  __int64 v75; // r8
  __int64 v76; // rcx
  unsigned __int64 v77; // r8
  struct IconGridItem *v78; // rcx
  __m128i v79; // xmm2
  __int64 v80; // rcx
  __int64 v81; // r9
  char *v82; // r10
  struct IconGridItem **v83; // r11
  __m128i v84; // xmm0
  __m128i v85; // xmm1
  __m128i v86; // xmm0
  __m128i v87; // xmm1
  __m128i v88; // xmm2
  int v89; // eax
  const char *v90; // r9
  struct WorkspaceData *v91; // rax
  size_t v92; // rdx
  size_t v93; // r14
  __int64 v94; // rcx
  _QWORD *v95; // rsi
  char *v96; // rdi
  __int64 v97; // rcx
  char *v98; // rax
  rsize_t v99; // r15
  char *v100; // rax
  char *v101; // rbx
  LPVOID *v102; // rdi
  __int64 v103; // r9
  __int64 v104; // rdx
  struct WorkspaceData *v105; // rdi
  unsigned __int64 v106; // r12
  _QWORD *v107; // r15
  unsigned __int64 k; // rdi
  struct IconGridItem *v109; // rdi
  unsigned __int64 n; // rdi
  int bIgnoreCase; // [rsp+20h] [rbp-99h]
  int bIgnoreCasea; // [rsp+20h] [rbp-99h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-99h]
  int bIgnoreCasec; // [rsp+20h] [rbp-99h]
  int bIgnoreCased; // [rsp+20h] [rbp-99h]
  int bIgnoreCasee; // [rsp+20h] [rbp-99h]
  int bIgnoreCasef; // [rsp+20h] [rbp-99h]
  int bIgnoreCaseg; // [rsp+20h] [rbp-99h]
  int bIgnoreCaseh; // [rsp+20h] [rbp-99h]
  int bIgnoreCasei; // [rsp+20h] [rbp-99h]
  int bIgnoreCasej; // [rsp+20h] [rbp-99h]
  unsigned __int64 v123; // [rsp+38h] [rbp-81h]
  _QWORD *v124; // [rsp+40h] [rbp-79h]
  _QWORD *v125; // [rsp+48h] [rbp-71h]
  __int64 v126; // [rsp+50h] [rbp-69h]
  __int64 v127; // [rsp+50h] [rbp-69h]
  size_t v129; // [rsp+58h] [rbp-61h]
  size_t v130; // [rsp+60h] [rbp-59h]
  char v131; // [rsp+68h] [rbp-51h] BYREF
  char v132; // [rsp+70h] [rbp-49h] BYREF
  LPVOID *p_pv; // [rsp+78h] [rbp-41h]
  LPVOID *v134; // [rsp+80h] [rbp-39h]
  struct IconGridItem ***v135; // [rsp+88h] [rbp-31h]
  char v136; // [rsp+90h] [rbp-29h]
  LPVOID pv; // [rsp+98h] [rbp-21h] BYREF
  struct WorkspaceData *v138; // [rsp+A0h] [rbp-19h] BYREF
  LPVOID v139; // [rsp+A8h] [rbp-11h] BYREF
  struct IconGridItem **v140; // [rsp+B0h] [rbp-9h] BYREF
  struct WorkspaceData *v141; // [rsp+B8h] [rbp-1h] BYREF
  _QWORD *v142; // [rsp+C0h] [rbp+7h] BYREF
  _QWORD *v143; // [rsp+C8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v3 = a3;
  v5 = (DesktopData *)*((_QWORD *)a1 + 11);
  if ( v5 && v5 != a1 || !*((_QWORD *)a1 + 5) )
    return 0;
  if ( *((_QWORD *)a3 + 7) )
  {
    v6 = *((_QWORD *)a3 + 9);
    v123 = v6;
  }
  else
  {
    v6 = 0;
    for ( i = 0; ; ++i )
    {
      v123 = v6;
      if ( i >= *((_QWORD *)v3 + 5) )
        break;
      v138 = 0;
      Workspace = DesktopData::GetWorkspace(v3, i, &v138);
      v9 = Workspace;
      if ( Workspace < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x144,
          (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
          (const char *)(unsigned int)Workspace,
          bIgnoreCase);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2BC,
          (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
          (const char *)v9,
          bIgnoreCaseb);
        return v9;
      }
      v6 += *((_QWORD *)v138 + 9);
    }
  }
  if ( *((_QWORD *)a1 + 7) )
  {
    v10 = *((_QWORD *)a1 + 9);
  }
  else
  {
    v10 = 0;
    for ( j = 0; j < *((_QWORD *)a1 + 5); ++j )
    {
      v138 = 0;
      v12 = DesktopData::GetWorkspace(a1, j, &v138);
      v13 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x144,
          (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
          (const char *)(unsigned int)v12,
          bIgnoreCase);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2BE,
          (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
          (const char *)v13,
          bIgnoreCasec);
        return v13;
      }
      v10 += *((_QWORD *)v138 + 9);
    }
  }
  v14 = 32 * v6;
  if ( !is_mul_ok(v6, 0x20u) )
    v14 = -1;
  v15 = __CFADD__(v14, 8);
  v16 = v14 + 8;
  if ( v15 )
    v16 = -1;
  v17 = (unsigned __int64 *)operator new[](v16, (const struct std::nothrow_t *)&std::nothrow);
  v18 = v17;
  if ( v17 )
  {
    memset_0(v17, 0, v16);
    *v18 = v6;
    v19 = v18 + 1;
    v124 = v18 + 1;
    `eh vector constructor iterator'(
      v18 + 1,
      0x20u,
      v6,
      (void (*)(void *))IconGridItem::IconGridItem,
      (void (*)(void *))IconGridItem::~IconGridItem);
  }
  else
  {
    v19 = 0;
    v124 = 0;
  }
  v142 = v19;
  if ( !v19 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C1,
      (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
      (const char *)0x8007000ELL,
      bIgnoreCase);
    wistd::unique_ptr<IconGridItem [0],wistd::default_delete<IconGridItem [0]>>::reset(&v142);
    return 2147942414LL;
  }
  v25 = 32 * v10;
  if ( !is_mul_ok(v10, 0x20u) )
    v25 = -1;
  v15 = __CFADD__(v25, 8);
  v26 = v25 + 8;
  if ( v15 )
    v26 = -1;
  v27 = (unsigned __int64 *)operator new[](v26, (const struct std::nothrow_t *)&std::nothrow);
  v28 = v27;
  if ( v27 )
  {
    memset_0(v27, 0, v26);
    *v28 = v10;
    v29 = v28 + 1;
    v125 = v28 + 1;
    `eh vector constructor iterator'(
      v28 + 1,
      0x20u,
      v10,
      (void (*)(void *))IconGridItem::IconGridItem,
      (void (*)(void *))IconGridItem::~IconGridItem);
  }
  else
  {
    v29 = 0;
    v125 = 0;
  }
  v143 = v29;
  if ( !v29 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C3,
      (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
      (const char *)0x8007000ELL,
      bIgnoreCase);
    wistd::unique_ptr<IconGridItem [0],wistd::default_delete<IconGridItem [0]>>::reset(&v143);
    wistd::unique_ptr<IconGridItem [0],wistd::default_delete<IconGridItem [0]>>::reset(&v142);
    return 2147942414LL;
  }
  v30 = v123;
  pv = CoTaskMemAlloc(8 * v123);
  v139 = CoTaskMemAlloc(8 * v10);
  v31 = (struct IconGridItem **)CoTaskMemAlloc(8 * v10);
  v140 = v31;
  p_pv = &pv;
  v134 = &v139;
  v135 = &v140;
  v136 = 1;
  if ( !pv )
  {
    v24 = 720;
LABEL_166:
    v21 = -2147024882;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
      (const char *)(unsigned int)v21,
      bIgnoreCase);
    CoTaskMemFree(pv);
    CoTaskMemFree(v139);
    CoTaskMemFree(v140);
    wistd::unique_ptr<IconGridItem [0],wistd::default_delete<IconGridItem [0]>>::reset(&v143);
    wistd::unique_ptr<IconGridItem [0],wistd::default_delete<IconGridItem [0]>>::reset(&v142);
    return (unsigned int)v21;
  }
  if ( !v139 )
  {
    v24 = 721;
    goto LABEL_166;
  }
  if ( !v31 )
  {
    v24 = 722;
    goto LABEL_166;
  }
  if ( *((_QWORD *)v3 + 7) )
  {
    for ( k = 0; k < v123; ++k )
    {
      v48 = IconGridItem::CloneFields(
              (IconGridItem *)&v19[4 * k],
              (const struct IconGridItem *)(32 * k + *((_QWORD *)v3 + 7)));
      v21 = v48;
      if ( v48 < 0 )
      {
        v23 = 338;
        goto LABEL_176;
      }
    }
  }
  else
  {
    v33 = 0;
    v34 = 0;
LABEL_39:
    v138 = v34;
    if ( (unsigned __int64)v34 < *((_QWORD *)v3 + 5) )
    {
      v141 = 0;
      v48 = DesktopData::GetWorkspace(v3, (unsigned __int64)v34, &v141);
      v21 = v48;
      if ( v48 < 0 )
      {
        v23 = 347;
LABEL_176:
        v22 = (unsigned int)v48;
      }
      else
      {
        v126 = 4 * v33;
        v50 = v141;
        v51 = *((_QWORD *)v141 + 9);
        v130 = v51;
        v52 = 0;
        v53 = v138;
        while ( 1 )
        {
          if ( v52 >= v51 )
          {
            v19 = v124;
            qsort(&v124[v126], v51, 0x20u, lambda_1da252210f9776495ca49d1b341ebf3a_::_lambda_invoker_cdecl_);
            v34 = (struct WorkspaceData *)((char *)v53 + 1);
            v3 = a3;
            goto LABEL_39;
          }
          if ( v52 >= *((_QWORD *)v50 + 9) )
          {
            v21 = -2147024809;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x52,
              (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\SimpleList.h",
              (const char *)0x80070057LL,
              bIgnoreCase);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x17,
              (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\SimpleList.h",
              (const char *)0x80070057LL,
              bIgnoreCasef);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC1,
              (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\workspacedata.cpp",
              (const char *)0x80070057LL,
              bIgnoreCaseg);
            v22 = 2147942487LL;
            v23 = 355;
            goto LABEL_24;
          }
          if ( v33 >= v30 )
            break;
          v54 = *(_QWORD *)(*((_QWORD *)v50 + 8) + 8 * v52);
          v55 = &v124[4 * v33];
          *v55 = *(_QWORD *)(v54 + 8);
          *((_DWORD *)v55 + 2) = *(_DWORD *)(v54 + 16);
          *((_DWORD *)v55 + 6) = *(_DWORD *)(v54 + 32);
          v56 = *(char **)(v54 + 24);
          if ( !v56 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0xF89,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
              v49);
          v57 = 0x7FFFFFFF;
          v58 = v56;
          do
          {
            if ( !*(_WORD *)v58 )
              break;
            v58 += 2;
            --v57;
          }
          while ( v57 );
          v59 = 2 * ((v58 - v56) >> 1);
          v60 = (char *)CoTaskMemAlloc(v59 + 2);
          v61 = v60;
          if ( v60 )
          {
            memcpy_s_0(v60, v59 + 2, v56, v59);
            *(_WORD *)&v61[v59] = 0;
          }
          v62 = (LPVOID *)(v55 + 2);
          if ( v55 + 2 == (_QWORD *)&v131 )
          {
            if ( v61 )
              CoTaskMemFree(v61);
          }
          else
          {
            if ( *v62 )
              wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(*v62);
            *v62 = v61;
          }
          if ( !*v62 )
          {
            v21 = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x21,
              (unsigned int)"shell\\shell32\\iconlayoutengine\\Common\\IconGridItem.h",
              (const char *)0x8007000ELL,
              bIgnoreCase);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4F,
              (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\icongriddataworker.cpp",
              (const char *)0x8007000ELL,
              bIgnoreCasea);
            v22 = 2147942414LL;
            v23 = 360;
            goto LABEL_24;
          }
          v53 = v138;
          *((_DWORD *)v55 + 2) = (_DWORD)v138;
          ++v33;
          ++v52;
          v50 = v141;
          v51 = v130;
          v30 = v123;
        }
        v21 = -2147483637;
        v22 = 2147483659LL;
        v23 = 366;
      }
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
        (const char *)v22,
        bIgnoreCase);
      v24 = 724;
      goto LABEL_25;
    }
  }
  v35 = (const struct IconGridItem *)v19;
  v36 = (const struct IconGridItem *)&v19[4 * v30];
  v37 = a1;
  while ( v35 != v36 )
  {
    v38 = (struct IconGridItem *)*((_QWORD *)v37 + 7);
    if ( v38 )
    {
      v109 = (struct IconGridItem *)((char *)v38 + 32 * *((_QWORD *)v37 + 9));
      while ( v38 != v109 )
      {
        if ( IconGridItem::IsSameFile(v35, v38) )
        {
          UpdateIconIfNeeded(v35, v38);
          break;
        }
        v38 = (struct IconGridItem *)((char *)v38 + 32);
      }
      v37 = a1;
    }
    else
    {
      v39 = 0;
LABEL_44:
      if ( v39 < *((_QWORD *)v37 + 5) )
      {
        v138 = 0;
        v21 = DesktopData::GetWorkspace(v37, v39, &v138);
        if ( v21 < 0 )
        {
          v47 = 675;
        }
        else
        {
          v40 = *((_QWORD *)v138 + 9);
          for ( m = 0; ; ++m )
          {
            if ( m >= v40 )
              goto LABEL_59;
            if ( m >= *((_QWORD *)v138 + 9) )
              break;
            v42 = (const WCHAR *)*((_QWORD *)v35 + 2);
            if ( v42 )
            {
              v43 = *(_QWORD *)(*((_QWORD *)v138 + 8) + 8 * m);
              v44 = *(const WCHAR **)(v43 + 24);
              if ( v44 )
              {
                v32 = *(unsigned int *)(v43 + 32);
                v45 = *((_DWORD *)v35 + 6);
                if ( (((unsigned __int8)v45 ^ *(_BYTE *)(v43 + 32)) & 1) != 0 )
                {
                  if ( CompareStringOrdinal(v42, -1, v44, -1, 1) == 2 )
                    goto LABEL_57;
                }
                else if ( v45 == (_DWORD)v32 && CompareStringOrdinal(v42, -1, v44, -1, 1) == 2 )
                {
LABEL_57:
                  if ( ((*(_BYTE *)(v43 + 32) ^ *((_BYTE *)v35 + 24)) & 1) != 0 )
                    *(_DWORD *)(v43 + 32) = *((_DWORD *)v35 + 6);
LABEL_59:
                  ++v39;
                  v37 = a1;
                  goto LABEL_44;
                }
              }
            }
          }
          v21 = -2147024809;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x52,
            (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\SimpleList.h",
            (const char *)0x80070057LL,
            bIgnoreCase);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x17,
            (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\SimpleList.h",
            (const char *)0x80070057LL,
            bIgnoreCased);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC1,
            (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\workspacedata.cpp",
            (const char *)0x80070057LL,
            bIgnoreCasee);
          v47 = 681;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v47,
          (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
          (const char *)(unsigned int)v21,
          bIgnoreCase);
        v24 = 725;
        goto LABEL_25;
      }
    }
    v35 = (const struct IconGridItem *)((char *)v35 + 32);
  }
  v107 = v125;
  if ( *((_QWORD *)v37 + 7) )
  {
    for ( n = 0; n < v10; ++n )
    {
      v89 = IconGridItem::CloneFields(
              (IconGridItem *)&v125[4 * n],
              (const struct IconGridItem *)(32 * n + *((_QWORD *)v37 + 7)));
      v21 = v89;
      if ( v89 < 0 )
      {
        v104 = 338;
        goto LABEL_192;
      }
      v37 = a1;
    }
  }
  else
  {
    v106 = 0;
    v105 = 0;
LABEL_157:
    v141 = v105;
    if ( (unsigned __int64)v105 < *((_QWORD *)v37 + 5) )
    {
      v138 = 0;
      v89 = DesktopData::GetWorkspace(v37, (unsigned __int64)v105, &v138);
      v21 = v89;
      if ( v89 < 0 )
      {
        v104 = 347;
LABEL_192:
        v103 = (unsigned int)v89;
      }
      else
      {
        v127 = 4 * v106;
        v91 = v138;
        v92 = *((_QWORD *)v138 + 9);
        v129 = v92;
        v93 = 0;
        while ( 1 )
        {
          if ( v93 >= v92 )
          {
            qsort(&v107[v127], v92, 0x20u, lambda_1da252210f9776495ca49d1b341ebf3a_::_lambda_invoker_cdecl_);
            v105 = (struct WorkspaceData *)((char *)v105 + 1);
            v37 = a1;
            goto LABEL_157;
          }
          if ( v93 >= *((_QWORD *)v91 + 9) )
          {
            v21 = -2147024809;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x52,
              (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\SimpleList.h",
              (const char *)0x80070057LL,
              bIgnoreCase);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x17,
              (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\SimpleList.h",
              (const char *)0x80070057LL,
              bIgnoreCasei);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC1,
              (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\workspacedata.cpp",
              (const char *)0x80070057LL,
              bIgnoreCasej);
            v103 = 2147942487LL;
            v104 = 355;
            goto LABEL_152;
          }
          if ( v106 >= v10 )
            break;
          v94 = *(_QWORD *)(*((_QWORD *)v91 + 8) + 8 * v93);
          v95 = &v107[4 * v106];
          *v95 = *(_QWORD *)(v94 + 8);
          *((_DWORD *)v95 + 2) = *(_DWORD *)(v94 + 16);
          *((_DWORD *)v95 + 6) = *(_DWORD *)(v94 + 32);
          v96 = *(char **)(v94 + 24);
          if ( !v96 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0xF89,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
              v90);
          v97 = 0x7FFFFFFF;
          v98 = v96;
          do
          {
            if ( !*(_WORD *)v98 )
              break;
            v98 += 2;
            --v97;
          }
          while ( v97 );
          v99 = 2 * ((v98 - v96) >> 1);
          v100 = (char *)CoTaskMemAlloc(v99 + 2);
          v101 = v100;
          if ( v100 )
          {
            memcpy_s_0(v100, v99 + 2, v96, v99);
            *(_WORD *)&v101[v99] = 0;
          }
          v102 = (LPVOID *)(v95 + 2);
          if ( v95 + 2 == (_QWORD *)&v132 )
          {
            if ( v101 )
              CoTaskMemFree(v101);
          }
          else
          {
            if ( *v102 )
              wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(*v102);
            *v102 = v101;
          }
          if ( !*v102 )
          {
            v21 = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x21,
              (unsigned int)"shell\\shell32\\iconlayoutengine\\Common\\IconGridItem.h",
              (const char *)0x8007000ELL,
              bIgnoreCase);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4F,
              (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\icongriddataworker.cpp",
              (const char *)0x8007000ELL,
              bIgnoreCaseh);
            v103 = 2147942414LL;
            v104 = 360;
            goto LABEL_152;
          }
          v105 = v141;
          *((_DWORD *)v95 + 2) = (_DWORD)v141;
          ++v106;
          ++v93;
          v91 = v138;
          v92 = v129;
          v107 = v125;
        }
        v21 = -2147483637;
        v103 = 2147483659LL;
        v104 = 366;
      }
LABEL_152:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v104,
        (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
        (const char *)v103,
        bIgnoreCase);
      v24 = 727;
      goto LABEL_25;
    }
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( v123 )
  {
    v32 = 0;
    if ( v123 < 8 )
      goto LABEL_196;
    v88 = _mm_unpacklo_epi64((__m128i)(unsigned __int64)v124, (__m128i)(unsigned __int64)v124);
    do
    {
      *(__m128i *)((char *)pv + 8 * v32) = _mm_add_epi64(
                                             _mm_slli_epi64(
                                               _mm_add_epi64(_mm_unpacklo_epi64((__m128i)v32, (__m128i)v32), si128),
                                               5u),
                                             v88);
      *(__m128i *)((char *)pv + 8 * v32 + 16) = _mm_add_epi64(
                                                  _mm_slli_epi64(
                                                    _mm_add_epi64(
                                                      _mm_unpacklo_epi64((__m128i)(v32 + 2), (__m128i)(v32 + 2)),
                                                      si128),
                                                    5u),
                                                  v88);
      *(__m128i *)((char *)pv + 8 * v32 + 32) = _mm_add_epi64(
                                                  _mm_slli_epi64(
                                                    _mm_add_epi64(
                                                      _mm_unpacklo_epi64((__m128i)(v32 + 4), (__m128i)(v32 + 4)),
                                                      si128),
                                                    5u),
                                                  v88);
      *(__m128i *)((char *)pv + 8 * v32 + 48) = _mm_add_epi64(
                                                  _mm_slli_epi64(
                                                    _mm_add_epi64(
                                                      _mm_unpacklo_epi64((__m128i)(v32 + 6), (__m128i)(v32 + 6)),
                                                      si128),
                                                    5u),
                                                  v88);
      v32 += 8LL;
    }
    while ( v32 < (v123 & 0xFFFFFFFFFFFFFFF8uLL) );
    if ( v32 < v123 )
    {
LABEL_196:
      do
      {
        *((_QWORD *)pv + v32) = &v124[4 * v32];
        ++v32;
      }
      while ( v32 < v123 );
    }
  }
  if ( v10 )
  {
    v77 = 0;
    if ( v10 < 8 )
      goto LABEL_197;
    v32 = (unsigned __int64)v139;
    if ( v140 <= (struct IconGridItem **)v139 + v10 - 1 && &v140[v10 - 1] >= v139 )
      goto LABEL_118;
    v79 = _mm_unpacklo_epi64((__m128i)(unsigned __int64)v107, (__m128i)(unsigned __int64)v107);
    v80 = 2;
    v32 = 4;
    v81 = 6;
    v82 = (char *)v139;
    v83 = v140;
    do
    {
      v84 = _mm_add_epi64(_mm_slli_epi64(_mm_add_epi64(_mm_unpacklo_epi64((__m128i)v77, (__m128i)v77), si128), 5u), v79);
      *(__m128i *)&v82[8 * v77] = v84;
      *(__m128i *)&v83[v77] = v84;
      v85 = _mm_add_epi64(
              _mm_slli_epi64(
                _mm_add_epi64(_mm_unpacklo_epi64((__m128i)(unsigned __int64)v80, (__m128i)(unsigned __int64)v80), si128),
                5u),
              v79);
      *(__m128i *)&v82[8 * v80] = v85;
      *(__m128i *)&v83[v80] = v85;
      v86 = _mm_add_epi64(_mm_slli_epi64(_mm_add_epi64(_mm_unpacklo_epi64((__m128i)v32, (__m128i)v32), si128), 5u), v79);
      *(__m128i *)&v82[8 * v32] = v86;
      *(__m128i *)&v83[v32] = v86;
      v87 = _mm_add_epi64(
              _mm_slli_epi64(
                _mm_add_epi64(_mm_unpacklo_epi64((__m128i)(unsigned __int64)v81, (__m128i)(unsigned __int64)v81), si128),
                5u),
              v79);
      *(__m128i *)&v82[8 * v81] = v87;
      *(__m128i *)&v83[v81] = v87;
      v77 += 8LL;
      v80 += 8;
      v32 += 8LL;
      v81 += 8;
    }
    while ( v77 < (v10 & 0xFFFFFFFFFFFFFFF8uLL) );
    if ( v77 < v10 )
    {
LABEL_197:
      do
      {
        v32 = (unsigned __int64)v139;
LABEL_118:
        v78 = (struct IconGridItem *)&v107[4 * v77];
        *(_QWORD *)(v32 + 8 * v77) = v78;
        v140[v77++] = v78;
      }
      while ( v77 < v10 );
    }
  }
  v64 = v140;
  v65 = pv;
  v66 = 0;
  if ( v123 )
  {
    do
    {
      for ( ii = 0; ii < v10; ++ii )
      {
        v68 = &v64[ii];
        v69 = *v68;
        if ( *v68 )
        {
          v70 = v65[v66];
          if ( *(_DWORD *)(v70 + 24) == *((_DWORD *)v69 + 6)
            && CompareStringOrdinal(*(LPCWCH *)(v70 + 16), -1, *((LPCWCH *)v69 + 2), -1, 1) == 2 )
          {
            *v68 = 0;
            break;
          }
        }
      }
      ++v66;
    }
    while ( v66 < v123 );
    v65 = pv;
  }
  v71 = v139;
  v72 = 0;
  if ( v10 )
  {
    do
    {
      for ( jj = 0; jj < v123; ++jj )
      {
        v74 = &v65[jj];
        v75 = *v74;
        if ( *v74 )
        {
          v76 = v71[v72];
          if ( *(_DWORD *)(v76 + 24) == *(_DWORD *)(v75 + 24)
            && CompareStringOrdinal(*(LPCWCH *)(v76 + 16), -1, *(LPCWCH *)(v75 + 16), -1, 1) == 2 )
          {
            *v74 = 0;
            break;
          }
        }
      }
      ++v72;
    }
    while ( v72 < v10 );
    v65 = pv;
  }
  v21 = DesktopData::AddUnmappedIcons(a1, v32, v65, v123);
  if ( v21 < 0 )
  {
    v24 = 742;
    goto LABEL_25;
  }
  v21 = DesktopData::DeleteIcons(a1, v140, v10);
  if ( v21 < 0 )
  {
    v24 = 743;
    goto LABEL_25;
  }
  CoTaskMemFree(pv);
  CoTaskMemFree(v139);
  CoTaskMemFree(v140);
  wistd::unique_ptr<IconGridItem [0],wistd::default_delete<IconGridItem [0]>>::reset(&v143);
  wistd::unique_ptr<IconGridItem [0],wistd::default_delete<IconGridItem [0]>>::reset(&v142);
  return 0;
}

```

## disassembly

```asm
0x180037710  mov     [rsp-8+arg_8], rbx
0x180037715  push    rbp
0x180037716  push    rsi
0x180037717  push    rdi
0x180037718  push    r12
0x18003771a  push    r13
0x18003771c  push    r14
0x18003771e  push    r15
0x180037720  lea     rbp, [rsp-27h]
0x180037725  sub     rsp, 0E0h
0x18003772c  mov     rax, cs:__security_cookie
0x180037733  xor     rax, rsp
0x180037736  mov     [rbp+57h+var_40], rax
0x18003773a  mov     rsi, r8
0x18003773d  mov     [rbp+57h+var_B8], r8
0x180037741  mov     r14, rcx
0x180037744  mov     [rsp+110h+var_E0], rcx
0x180037749  mov     rax, [rcx+58h]
0x18003774d  test    rax, rax
0x180037750  jnz     loc_180037D74
0x180037756  cmp     qword ptr [rcx+28h], 0
0x18003775b  jz      loc_180038255
0x180037761  cmp     qword ptr [r8+38h], 0
0x180037766  jnz     short loc_1800377A6
0x180037768  xor     r15d, r15d
0x18003776b  xor     ebx, ebx
0x18003776d  mov     [rsp+110h+var_D8], r15
0x180037772  cmp     rbx, [rsi+28h]
0x180037776  jnb     short loc_1800377AF
0x180037778  mov     [rbp+57h+var_70], 0
0x180037780  lea     r8, [rbp+57h+var_70]; struct WorkspaceData **
0x180037784  mov     rdx, rbx; unsigned __int64
0x180037787  mov     rcx, rsi; this
0x18003778a  call    ?GetWorkspace@DesktopData@@QEBAJ_KPEAPEAVWorkspaceData@@@Z; DesktopData::GetWorkspace(unsigned __int64,WorkspaceData * *)
0x18003778f  mov     edi, eax
0x180037791  test    eax, eax
0x180037793  js      loc_180037D82
0x180037799  mov     rax, [rbp+57h+var_70]
0x18003779d  add     r15, [rax+48h]
0x1800377a1  inc     rbx
0x1800377a4  jmp     short loc_18003776D
0x1800377a6  mov     r15, [r8+48h]
0x1800377aa  mov     [rsp+110h+var_D8], r15
0x1800377af  cmp     qword ptr [r14+38h], 0
0x1800377b4  jnz     short loc_1800377EF
0x1800377b6  xor     r13d, r13d
0x1800377b9  xor     ebx, ebx
0x1800377bb  cmp     rbx, [r14+28h]
0x1800377bf  jnb     short loc_1800377F3
0x1800377c1  mov     [rbp+57h+var_70], 0
0x1800377c9  lea     r8, [rbp+57h+var_70]; struct WorkspaceData **
0x1800377cd  mov     rdx, rbx; unsigned __int64
0x1800377d0  mov     rcx, r14; this
0x1800377d3  call    ?GetWorkspace@DesktopData@@QEBAJ_KPEAPEAVWorkspaceData@@@Z; DesktopData::GetWorkspace(unsigned __int64,WorkspaceData * *)
0x1800377d8  mov     edi, eax
0x1800377da  test    eax, eax
0x1800377dc  js      loc_180037DB9
0x1800377e2  mov     rax, [rbp+57h+var_70]
0x1800377e6  add     r13, [rax+48h]
0x1800377ea  inc     rbx
0x1800377ed  jmp     short loc_1800377BB
0x1800377ef  mov     r13, [r14+48h]
0x1800377f3  mov     eax, 20h ; ' '
0x1800377f8  mul     r15
0x1800377fb  mov     rbx, rax
0x1800377fe  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180037805  cmovb   rbx, r12
0x180037809  add     rbx, 8
0x18003780d  cmovb   rbx, r12
0x180037811  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180037818  mov     rcx, rbx; unsigned __int64
0x18003781b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180037820  mov     rdi, rax
0x180037823  test    rax, rax
0x180037826  jz      loc_180037EA1
0x18003782c  mov     r8, rbx; Size
0x18003782f  xor     edx, edx; Val
0x180037831  mov     rcx, rax; void *
0x180037834  call    memset_0
0x180037839  mov     [rdi], r15
0x18003783c  lea     r14, [rdi+8]
0x180037840  mov     [rbp+57h+var_D0], r14
0x180037844  lea     rax, ??1IconGridItem@@QEAA@XZ; IconGridItem::~IconGridItem(void)
0x18003784b  mov     qword ptr [rsp+110h+bIgnoreCase], rax; int
0x180037850  lea     r9, ??0IconGridItem@@QEAA@XZ; void (*)(void *)
0x180037857  mov     r8, r15; unsigned __int64
0x18003785a  mov     edx, 20h ; ' '; unsigned __int64
0x18003785f  mov     rcx, r14; void *
0x180037862  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180037867  mov     [rbp+57h+var_50], r14
0x18003786b  test    r14, r14
0x18003786e  jnz     loc_180037976
0x180037874  mov     rcx, [rbp+5Fh]; this
0x180037878  mov     ebx, 8007000Eh
0x18003787d  mov     r9d, ebx; char *
0x180037880  lea     r8, aShellShell32Ic_11; "shell\\shell32\\iconlayoutengine\\datam"...
0x180037887  mov     edx, 2C1h; void *
0x18003788c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037891  nop
0x180037892  lea     rcx, [rbp+57h+var_50]
0x180037896  call    ?reset@?$unique_ptr@$$BY0A@UIconGridItem@@U?$default_delete@$$BY0A@UIconGridItem@@@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<IconGridItem [0],wistd::default_delete<IconGridItem [0]>>::reset(std::nullptr_t)
0x18003789b  mov     eax, ebx
0x18003789d  jmp     loc_18003794E
0x1800378a2  mov     rcx, [rbp+5Fh]; this
0x1800378a6  mov     ebx, 8007000Eh
0x1800378ab  mov     r9d, ebx; char *
0x1800378ae  lea     r8, aShellShell32Ic_15; "shell\\shell32\\iconlayoutengine\\Commo"...
0x1800378b5  mov     edx, 21h ; '!'; void *
0x1800378ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800378bf  mov     rcx, [rbp+5Fh]; this
0x1800378c3  mov     r9d, ebx; char *
0x1800378c6  lea     r8, aShellShell32Ic_12; "shell\\shell32\\iconlayoutengine\\datam"...
0x1800378cd  mov     edx, 4Fh ; 'O'; void *
0x1800378d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800378d7  mov     r9d, ebx; char *
0x1800378da  mov     edx, 168h; void *
0x1800378df  lea     r8, aShellShell32Ic_11; "shell\\shell32\\iconlayoutengine\\datam"...
0x1800378e6  mov     rcx, [rbp+5Fh]; this
0x1800378ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800378ef  mov     edx, 2D4h; void *
0x1800378f4  lea     r8, aShellShell32Ic_11; "shell\\shell32\\iconlayoutengine\\datam"...
0x1800378fb  mov     r9d, ebx; char *
0x1800378fe  mov     rcx, [rbp+5Fh]; this
0x180037902  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037907  nop
0x180037908  mov     rcx, [rbp+57h+pv]; pv
0x18003790c  call    cs:__imp_CoTaskMemFree
0x180037913  nop     dword ptr [rax+rax+00h]
0x180037918  mov     rcx, [rbp+57h+var_68]; pv
0x18003791c  call    cs:__imp_CoTaskMemFree
0x180037923  nop     dword ptr [rax+rax+00h]
0x180037928  mov     rcx, [rbp+57h+var_60]; pv
0x18003792c  call    cs:__imp_CoTaskMemFree
0x180037933  nop     dword ptr [rax+rax+00h]
0x180037938  nop
0x180037939  lea     rcx, [rbp+57h+var_48]
0x18003793d  call    ?reset@?$unique_ptr@$$BY0A@UIconGridItem@@U?$default_delete@$$BY0A@UIconGridItem@@@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<IconGridItem [0],wistd::default_delete<IconGridItem [0]>>::reset(std::nullptr_t)
0x180037942  nop
0x180037943  lea     rcx, [rbp+57h+var_50]
0x180037947  call    ?reset@?$unique_ptr@$$BY0A@UIconGridItem@@U?$default_delete@$$BY0A@UIconGridItem@@@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<IconGridItem [0],wistd::default_delete<IconGridItem [0]>>::reset(std::nullptr_t)
0x18003794c  mov     eax, ebx
0x18003794e  mov     rcx, [rbp+57h+var_40]
0x180037952  xor     rcx, rsp; StackCookie
0x180037955  call    __security_check_cookie
0x18003795a  mov     rbx, [rsp+110h+arg_8]
0x180037962  add     rsp, 0E0h
0x180037969  pop     r15
0x18003796b  pop     r14
0x18003796d  pop     r13
0x18003796f  pop     r12
0x180037971  pop     rdi
0x180037972  pop     rsi
0x180037973  pop     rbp
0x180037974  retn
0x180037976  mov     eax, 20h ; ' '
0x18003797b  mul     r13
0x18003797e  mov     rbx, rax
0x180037981  cmovb   rbx, r12
0x180037985  add     rbx, 8
0x180037989  cmovb   rbx, r12
0x18003798d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180037994  mov     rcx, rbx; unsigned __int64
0x180037997  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003799c  mov     rdi, rax
0x18003799f  test    rax, rax
0x1800379a2  jz      loc_180037EAD
0x1800379a8  mov     r8, rbx; Size
0x1800379ab  xor     edx, edx; Val
0x1800379ad  mov     rcx, rax; void *
0x1800379b0  call    memset_0
0x1800379b5  mov     [rdi], r13
0x1800379b8  lea     r15, [rdi+8]
0x1800379bc  mov     [rbp+57h+var_C8], r15
0x1800379c0  lea     rax, ??1IconGridItem@@QEAA@XZ; IconGridItem::~IconGridItem(void)
0x1800379c7  mov     qword ptr [rsp+110h+bIgnoreCase], rax; int
0x1800379cc  lea     r9, ??0IconGridItem@@QEAA@XZ; void (*)(void *)
0x1800379d3  mov     r8, r13; unsigned __int64
0x1800379d6  mov     edx, 20h ; ' '; unsigned __int64
0x1800379db  mov     rcx, r15; void *
0x1800379de  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800379e3  mov     [rbp+57h+var_48], r15
0x1800379e7  test    r15, r15
0x1800379ea  jnz     short loc_180037A24
0x1800379ec  mov     rcx, [rbp+5Fh]; this
0x1800379f0  mov     ebx, 8007000Eh
0x1800379f5  mov     r9d, ebx; char *
0x1800379f8  lea     r8, aShellShell32Ic_11; "shell\\shell32\\iconlayoutengine\\datam"...
0x1800379ff  mov     edx, 2C3h; void *
0x180037a04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037a09  nop
0x180037a0a  lea     rcx, [rbp+57h+var_48]
0x180037a0e  call    ?reset@?$unique_ptr@$$BY0A@UIconGridItem@@U?$default_delete@$$BY0A@UIconGridItem@@@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<IconGridItem [0],wistd::default_delete<IconGridItem [0]>>::reset(std::nullptr_t)
0x180037a13  nop
0x180037a14  lea     rcx, [rbp+57h+var_50]
0x180037a18  call    ?reset@?$unique_ptr@$$BY0A@UIconGridItem@@U?$default_delete@$$BY0A@UIconGridItem@@@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<IconGridItem [0],wistd::default_delete<IconGridItem [0]>>::reset(std::nullptr_t)
0x180037a1d  mov     eax, ebx
0x180037a1f  jmp     loc_18003794E
0x180037a24  mov     r15, [rsp+110h+var_D8]
0x180037a29  lea     rcx, ds:0[r15*8]; cb
0x180037a31  call    cs:__imp_CoTaskMemAlloc
0x180037a38  nop     dword ptr [rax+rax+00h]
0x180037a3d  mov     [rbp+57h+pv], rax
0x180037a41  lea     rbx, ds:0[r13*8]
0x180037a49  mov     rcx, rbx; cb
0x180037a4c  call    cs:__imp_CoTaskMemAlloc
0x180037a53  nop     dword ptr [rax+rax+00h]
0x180037a58  mov     [rbp+57h+var_68], rax
0x180037a5c  mov     rcx, rbx; cb
0x180037a5f  call    cs:__imp_CoTaskMemAlloc
0x180037a66  nop     dword ptr [rax+rax+00h]
0x180037a6b  mov     [rbp+57h+var_60], rax
0x180037a6f  lea     rcx, [rbp+57h+pv]
0x180037a73  mov     [rbp+57h+var_98], rcx
0x180037a77  lea     rcx, [rbp+57h+var_68]
0x180037a7b  mov     [rbp+57h+var_90], rcx
0x180037a7f  lea     rcx, [rbp+57h+var_60]
0x180037a83  mov     [rbp+57h+var_88], rcx
0x180037a87  mov     [rbp+57h+var_80], 1
0x180037a8b  cmp     [rbp+57h+pv], 0
0x180037a90  jz      loc_1800384C4
0x180037a96  cmp     [rbp+57h+var_68], 0
0x180037a9b  jz      loc_1800384DA
0x180037aa1  test    rax, rax
0x180037aa4  jz      loc_1800384CB
0x180037aaa  cmp     qword ptr [rsi+38h], 0
0x180037aaf  jnz     loc_1800384E1
0x180037ab5  xor     r12d, r12d
0x180037ab8  xor     ebx, ebx
0x180037aba  mov     [rbp+57h+var_70], rbx
0x180037abe  cmp     rbx, [rsi+28h]
0x180037ac2  jb      loc_180037C0B
0x180037ac8  mov     rsi, r14
0x180037acb  mov     r12, r15
0x180037ace  shl     r12, 5
0x180037ad2  add     r12, r14
0x180037ad5  mov     rax, [rsp+110h+var_E0]
0x180037ada  nop     word ptr [rax+rax+00h]
0x180037ae0  cmp     rsi, r12
0x180037ae3  jz      loc_180038409
0x180037ae9  mov     rbx, [rax+38h]
0x180037aed  test    rbx, rbx
0x180037af0  jnz     loc_180038545
0x180037af6  xor     r15d, r15d
0x180037af9  cmp     r15, [rax+28h]
0x180037afd  jnb     loc_18003857A
0x180037b03  mov     [rbp+57h+var_70], 0
0x180037b0b  lea     r8, [rbp+57h+var_70]; struct WorkspaceData **
0x180037b0f  mov     rdx, r15; unsigned __int64
0x180037b12  mov     rcx, rax; this
0x180037b15  call    ?GetWorkspace@DesktopData@@QEBAJ_KPEAPEAVWorkspaceData@@@Z; DesktopData::GetWorkspace(unsigned __int64,WorkspaceData * *)
0x180037b1a  mov     ebx, eax
0x180037b1c  test    eax, eax
0x180037b1e  js      loc_180037BE9
0x180037b24  mov     rax, [rbp+57h+var_70]
0x180037b28  mov     r14, [rax+48h]
0x180037b2c  xor     ebx, ebx
0x180037b2e  xchg    ax, ax
0x180037b30  cmp     rbx, r14
0x180037b33  jnb     short loc_180037BB2
0x180037b35  mov     rax, [rbp+57h+var_70]
0x180037b39  cmp     rbx, [rax+48h]
0x180037b3d  jnb     loc_180037DF0
0x180037b43  mov     rcx, [rsi+10h]; lpString1
0x180037b47  test    rcx, rcx
0x180037b4a  jz      short loc_180037B5D
0x180037b4c  mov     rax, [rax+40h]
0x180037b50  mov     rdi, [rax+rbx*8]
0x180037b54  mov     r8, [rdi+18h]; lpString2
0x180037b58  test    r8, r8
0x180037b5b  jnz     short loc_180037B62
0x180037b5d  inc     rbx
0x180037b60  jmp     short loc_180037B30
0x180037b62  mov     edx, [rdi+20h]
0x180037b65  mov     r9d, [rsi+18h]
0x180037b69  mov     eax, edx
0x180037b6b  xor     eax, r9d
0x180037b6e  test    al, 1
0x180037b70  jnz     short loc_180037BC3
0x180037b72  cmp     r9d, edx
0x180037b75  jnz     short loc_180037BBF
0x180037b77  mov     [rsp+110h+bIgnoreCase], 1; bIgnoreCase
0x180037b7f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180037b86  mov     r9d, eax; cchCount2
0x180037b89  mov     edx, eax; cchCount1
0x180037b8b  call    cs:__imp_CompareStringOrdinal
0x180037b92  nop     dword ptr [rax+rax+00h]
0x180037b97  cmp     eax, 2
0x180037b9a  jnz     short loc_180037BBF
0x180037b9c  mov     al, 1
0x180037b9e  test    al, al
0x180037ba0  jz      short loc_180037B5D
0x180037ba2  mov     ecx, [rsi+18h]
0x180037ba5  mov     eax, ecx
0x180037ba7  xor     eax, [rdi+20h]
0x180037baa  test    al, 1
0x180037bac  jnz     loc_180038583
0x180037bb2  inc     r15
0x180037bb5  mov     rax, [rsp+110h+var_E0]
0x180037bba  jmp     loc_180037AF9
0x180037bbf  xor     al, al
  ... truncated ...
```
