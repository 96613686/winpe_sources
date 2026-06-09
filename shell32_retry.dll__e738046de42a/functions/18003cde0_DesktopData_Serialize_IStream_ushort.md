# DesktopData::Serialize(IStream *,ushort *)

- ea: `0x18003cde0`
- end: `0x18003eaa2`
- name: `?Serialize@DesktopData@@UEAAJPEAUIStream@@PEAG@Z`
- size: `7362`
- prototype: `__int64 __fastcall(DesktopData *__hidden this, struct IStream *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180038b5c`
- `0x1800397bc`
- `0x18003af20`
- `0x18003cd64`
- `0x18003cde0`
- `0x18003eab0`
- `0x18003eb50`
- `0x18003eb88`
- `0x18003ebb0`
- `0x18003ef10`
- `0x18003ef40`
- `0x18003efb8`
- `0x18003f024`
- `0x18003f4ec`
- `0x18003f698`
- `0x18003f6d4`
- `0x18003f7a4`
- `0x180054320`
- `0x1800ac89c`
- `0x1801be5c8`
- `0x1801d4aac`
- `0x1801d6a84`
- `0x180233280`
- `0x1802332d0`
- `0x18023378c`
- `0x180233b54`
- `0x1802342fc`
- `0x1802464f8`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d41b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d41b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d429`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d429`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d19e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d3ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d3fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d6b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dab7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dbcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dc70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dd9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e346`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d19e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d3ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d3fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d6b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dab7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dbcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dc70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dd9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e346`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003cfda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d08f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d0fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d9a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003da13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003df1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003cfda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d08f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d0fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d9a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003da13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003df1b`

## string_xrefs

- `0x18003dc17`: `%s    LinkedKey: "%s"`
- `0x18003e4b2`: `    Has Holes, compressed key =`
- `0x18003d7d5`: `    Source Link Index: %d`
- `0x18003e718`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18003e974`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall DesktopData::Serialize(DesktopData *this, struct IStream *a2, unsigned __int16 *a3)
{
  const wchar_t *v3; // r12
  DesktopData *v4; // r13
  unsigned __int64 v5; // rsi
  char v6; // di
  char v7; // r15
  unsigned __int64 i; // rbx
  __int64 v9; // rax
  int Workspace; // eax
  unsigned int v11; // r14d
  unsigned __int64 v12; // rbx
  char *v13; // rax
  char *v14; // r15
  int WorkspaceUtilizationInfo; // eax
  unsigned int v16; // edi
  unsigned __int64 v17; // rdi
  unsigned __int64 v18; // r14
  unsigned __int64 j; // rbx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rax
  char *v23; // rcx
  void *v24; // rax
  __int64 v25; // rbx
  const char *v26; // r9
  _QWORD *v27; // rax
  _QWORD *v28; // rcx
  unsigned __int64 v29; // r8
  unsigned __int64 v30; // r14
  WorkspaceData *v31; // rax
  WorkspaceData *v32; // rdi
  LPVOID v33; // rax
  unsigned __int64 ii; // rsi
  __int64 v35; // rcx
  int v36; // r15d
  unsigned int v37; // r13d
  unsigned __int16 *v38; // rbx
  const unsigned __int16 *v39; // r8
  int v40; // eax
  size_t *v41; // r8
  unsigned __int64 v42; // rcx
  WorkspaceData *v43; // rax
  unsigned __int64 v44; // rax
  unsigned __int64 v45; // rax
  WorkspaceData *v46; // rcx
  unsigned __int64 v47; // rcx
  const WCHAR *v48; // r9
  _WORD *v49; // rax
  __int64 v50; // r8
  unsigned __int64 v51; // rdx
  _WORD *v52; // rcx
  int v54; // ecx
  __int64 v55; // r8
  int v56; // ebx
  __int64 v57; // rdx
  unsigned __int64 v58; // r9
  __int64 v59; // rdx
  _QWORD *v60; // rcx
  unsigned __int64 v61; // rax
  unsigned __int64 v62; // rbx
  _QWORD *v63; // r8
  HANDLE ProcessHeap; // rax
  struct IStream *v65; // r15
  int ShouldSerialize; // ebx
  __int64 v67; // rdx
  const wchar_t *v68; // rax
  int v69; // ecx
  __int64 v70; // r8
  __int64 v71; // rdx
  const wchar_t *v72; // rax
  int v73; // ecx
  __int64 v74; // r8
  __int64 v75; // rdx
  unsigned __int64 v76; // r9
  __int64 v77; // rdx
  const unsigned __int16 *v78; // r9
  wchar_t *v79; // rax
  __int64 v80; // rcx
  wchar_t *v81; // rcx
  __int64 v82; // rdx
  __int64 v83; // rdx
  char *v84; // rcx
  struct IStreamVtbl *lpVtbl; // rax
  int v86; // eax
  unsigned __int64 n; // rdi
  __int64 v88; // rdx
  const wchar_t *v89; // rax
  int v90; // ecx
  __int64 v91; // r8
  __int64 v92; // rdx
  const wchar_t *v93; // rax
  struct IStreamVtbl *v94; // rax
  int v95; // eax
  unsigned __int64 v96; // r15
  __int64 v97; // r8
  __int64 v98; // rdx
  bool v99; // zf
  __int64 v100; // rdx
  unsigned __int64 v101; // rsi
  _WORD *v102; // rax
  const char *v103; // r9
  _WORD *v104; // r14
  char *k; // r15
  __int64 v106; // rcx
  int v107; // r12d
  unsigned __int16 *v108; // rbx
  __int64 v109; // r9
  unsigned __int16 *v110; // r8
  int v111; // eax
  size_t *v112; // r8
  unsigned __int64 v113; // rax
  _WORD *v114; // rcx
  unsigned __int64 v115; // rcx
  unsigned __int64 v116; // rax
  _WORD *v117; // rcx
  unsigned __int64 v118; // rcx
  const WCHAR *v119; // r9
  _WORD *v120; // rax
  __int64 v121; // r8
  unsigned __int64 v122; // rdx
  _WORD *v123; // rcx
  void *v124; // rdi
  unsigned __int64 v125; // r14
  unsigned __int64 v126; // rdx
  unsigned __int64 v127; // rbx
  _QWORD *v128; // rcx
  int v129; // eax
  int v130; // ebx
  const wchar_t *v131; // rcx
  int v132; // eax
  int v133; // eax
  int v134; // eax
  const wchar_t *v135; // rax
  __int64 v136; // rdx
  int v137; // ecx
  __int64 v138; // r8
  __int64 v139; // rdx
  const wchar_t *v140; // rax
  int v141; // ecx
  __int64 v142; // r8
  __int64 v143; // rdx
  unsigned __int64 v144; // r9
  struct IStreamVtbl *v145; // rax
  int v146; // eax
  void *v147; // rax
  unsigned __int64 v148; // rsi
  __int64 v149; // rbx
  _QWORD *v150; // rax
  _QWORD *v151; // rcx
  unsigned __int16 *v152; // r9
  wchar_t *v153; // rax
  __int64 v154; // rcx
  wchar_t *v155; // rcx
  int DataForTracelog; // eax
  unsigned __int64 v157; // rdx
  unsigned __int8 v158; // cl
  unsigned int v159; // ebx
  __int64 v160; // rcx
  DesktopIconLayoutTelemetry *v161; // rcx
  const unsigned __int16 *v162; // r9
  wchar_t *v163; // rax
  __int64 v164; // rcx
  wchar_t *v165; // rcx
  unsigned __int16 *v166; // r9
  wchar_t *v167; // rax
  __int64 v168; // rcx
  wchar_t *v169; // rcx
  const unsigned __int16 *v170; // r9
  wchar_t *v171; // rax
  __int64 v172; // rcx
  wchar_t *v173; // rcx
  unsigned __int64 m; // rdi
  __int64 v175; // rcx
  unsigned __int16 *v176; // r9
  wchar_t *v177; // rax
  __int64 v178; // rcx
  wchar_t *v179; // rcx
  HRESULT v180; // r8d
  int v181; // ebx
  const wchar_t *v182; // rcx
  wchar_t *v183; // rdx
  size_t v184; // rsi
  wchar_t *v185; // rcx
  int v186; // ecx
  __int64 v187; // rdx
  int v188; // ebx
  __int64 v189; // rdx
  const wchar_t *v190; // rax
  int v191; // ecx
  __int64 v192; // r8
  __int64 v193; // rdx
  wchar_t *v194; // rax
  __int64 v195; // rcx
  WorkspaceData *v196; // r9
  wchar_t *v197; // rcx
  const unsigned __int16 *v198; // r9
  wchar_t *v199; // rax
  __int64 v200; // rcx
  wchar_t *v201; // rcx
  int v202; // ecx
  __int64 v203; // rdx
  int v204; // ebx
  const wchar_t *v205; // r9
  wchar_t *v206; // rax
  __int64 v207; // rcx
  wchar_t *v208; // rcx
  int v209; // ecx
  __int64 v210; // rdx
  const wchar_t *v211; // r9
  wchar_t *v212; // rax
  __int64 v213; // rcx
  wchar_t *v214; // rcx
  int v215; // ecx
  __int64 v216; // r8
  const wchar_t *v217; // r9
  wchar_t *v218; // rax
  __int64 v219; // rcx
  wchar_t *v220; // rcx
  int v221; // ecx
  __int64 v222; // r8
  const wchar_t *v223; // r9
  wchar_t *v224; // rax
  __int64 v225; // rcx
  wchar_t *v226; // rcx
  __int64 v227; // rdx
  const wchar_t *v228; // rax
  __int64 v229; // r8
  const wchar_t *v230; // rax
  const wchar_t *v231; // rax
  __int64 v232; // r8
  const wchar_t *v233; // rax
  __int64 v234; // r8
  __int64 v235; // r8
  size_t cchToCopy; // [rsp+20h] [rbp-E0h]
  int cchToCopya; // [rsp+20h] [rbp-E0h]
  int cchToCopyb; // [rsp+20h] [rbp-E0h]
  int cchToCopye; // [rsp+20h] [rbp-E0h]
  int cchToCopyf; // [rsp+20h] [rbp-E0h]
  int cchToCopyc; // [rsp+20h] [rbp-E0h]
  int cchToCopyg; // [rsp+20h] [rbp-E0h]
  int cchToCopyh; // [rsp+20h] [rbp-E0h]
  int cchToCopyi; // [rsp+20h] [rbp-E0h]
  int cchToCopyd; // [rsp+20h] [rbp-E0h]
  int cchToCopyj; // [rsp+20h] [rbp-E0h]
  int cchToCopyk; // [rsp+20h] [rbp-E0h]
  int cchToCopyl; // [rsp+20h] [rbp-E0h]
  bool *v249; // [rsp+28h] [rbp-D8h]
  bool v250; // [rsp+30h] [rbp-D0h] BYREF
  DesktopData *v251; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v252; // [rsp+40h] [rbp-C0h]
  struct IStream *v253; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v254; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v255; // [rsp+58h] [rbp-A8h] BYREF
  struct WorkspaceData *v256; // [rsp+60h] [rbp-A0h] BYREF
  WorkspaceData *v257; // [rsp+68h] [rbp-98h] BYREF
  char *v258; // [rsp+70h] [rbp-90h] BYREF
  size_t pcchLength; // [rsp+78h] [rbp-88h] BYREF
  LPVOID pv[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v261; // [rsp+90h] [rbp-70h]
  __int128 v262; // [rsp+98h] [rbp-68h]
  __int64 v263; // [rsp+A8h] [rbp-58h]
  unsigned __int16 v264[256]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v265[256]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4F8h] [rbp+3F8h]

  v252 = a3;
  v3 = a3;
  v253 = a2;
  v4 = this;
  v251 = this;
  if ( a3 )
  {
    v229 = 64000;
    v230 = v3;
    do
    {
      if ( !*v230 )
        break;
      ++v230;
      --v229;
    }
    while ( v229 );
    v202 = -2147024809;
    if ( v229 )
      v202 = 0;
    v203 = 64000 - v229;
    if ( v229 )
    {
      v205 = L"  Desktop Serialize Begin\r\n";
      v206 = (wchar_t *)&v3[v203];
      v207 = 2147483646;
      if ( v203 != 64000 )
      {
        do
        {
          if ( !v207 )
            break;
          if ( !*v205 )
            break;
          *v206++ = *v205++;
          --v207;
          --v229;
        }
        while ( v229 );
      }
      v208 = v206 - 1;
      if ( v229 )
        v208 = v206;
      *v208 = 0;
      v202 = -2147024774;
      if ( v229 )
        v202 = 0;
    }
    v204 = 0;
    if ( v202 != -2147024774 )
      v204 = v202;
    if ( v204 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11,
        (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
        (const char *)(unsigned int)v204,
        cchToCopy);
      return (unsigned int)v204;
    }
  }
  v5 = 0;
  v6 = 0;
  v7 = 0;
  for ( i = 0; i < *((_QWORD *)v4 + 5); ++i )
  {
    v9 = *((_QWORD *)v4 + 4);
    v256 = 0;
    v256 = *(struct WorkspaceData **)(v9 + 8 * i);
    Workspace = DesktopData::GetWorkspace(v4, i, &v256);
    v11 = Workspace;
    if ( Workspace < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x111,
        (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
        (const char *)(unsigned int)Workspace,
        cchToCopy);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15,
        (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
        (const char *)v11,
        cchToCopyh);
      return v11;
    }
    if ( !*((_QWORD *)v256 + 9) )
    {
      if ( (*((_BYTE *)v256 + 40) & 1) == 0 )
      {
        v7 = 1;
        continue;
      }
      v6 = 1;
    }
    ++v5;
    if ( v7 )
      v6 = 1;
  }
  if ( !v6 )
    goto LABEL_94;
  if ( v3 )
  {
    v231 = v3;
    v232 = 64000;
    do
    {
      if ( !*v231 )
        break;
      ++v231;
      --v232;
    }
    while ( v232 );
    v209 = -2147024809;
    if ( v232 )
      v209 = 0;
    v210 = 64000 - v232;
    if ( v232 )
    {
      v211 = L"    Has Holes, compressed key =";
      v212 = (wchar_t *)&v3[v210];
      v213 = 2147483646;
      if ( v210 != 64000 )
      {
        do
        {
          if ( !v213 )
            break;
          if ( !*v211 )
            break;
          *v212++ = *v211++;
          --v213;
          --v232;
        }
        while ( v232 );
      }
      v214 = v212 - 1;
      if ( v232 )
        v214 = v212;
      *v214 = 0;
      v209 = -2147024774;
      if ( v232 )
        v209 = 0;
    }
    v188 = 0;
    if ( v209 != -2147024774 )
      v188 = v209;
    if ( v188 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B,
        (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
        (const char *)(unsigned int)v188,
        cchToCopy);
      return (unsigned int)v188;
    }
  }
  v12 = 20 * v5;
  if ( !is_mul_ok(v5, 0x14u) )
    v12 = -1;
  v13 = (char *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
  v258 = v13;
  v14 = v13;
  if ( !v13 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
      (const char *)0x8007000ELL,
      cchToCopy);
    return 2147942414LL;
  }
  memset_0(v13, 0, v12);
  v257 = 0;
  WorkspaceUtilizationInfo = DesktopData::GetWorkspaceUtilizationInfo(v4, 0, 0, (unsigned __int64 *)&v257, 0, v249);
  v16 = WorkspaceUtilizationInfo;
  if ( WorkspaceUtilizationInfo < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F5,
      (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
      (const char *)(unsigned int)WorkspaceUtilizationInfo,
      cchToCopy);
    goto LABEL_69;
  }
  if ( v257 != (WorkspaceData *)v5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F6,
      (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
      (const char *)0x80070057LL,
      cchToCopy);
    v16 = -2147024809;
LABEL_69:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
      (const char *)v16,
      cchToCopya);
    CZeroInitNew::operator delete(v14);
    return v16;
  }
  v17 = 0;
  v18 = 0;
  for ( j = 0; j < *((_QWORD *)v4 + 5); ++j )
  {
    v257 = 0;
    v20 = DesktopData::GetWorkspace(v4, j, &v257);
    v16 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2FB,
        (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
        (const char *)(unsigned int)v20,
        cchToCopy);
      goto LABEL_69;
    }
    if ( !WorkspaceData::IsIgnorable(v257) )
    {
      if ( v18 >= v5 )
      {
        v16 = -2147483637;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2FE,
          (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
          (const char *)0x8000000BLL,
          cchToCopy);
        goto LABEL_69;
      }
      v22 = 5 * v18++;
      v23 = &v14[4 * v22];
      *(_QWORD *)v23 = *(_QWORD *)(v21 + 24);
      *((_QWORD *)v23 + 1) = *(_QWORD *)(v21 + 32);
      *((_DWORD *)v23 + 4) = *(_DWORD *)(v21 + 40);
    }
    v17 = 0;
  }
  pv[0] = 0;
  pv[1] = 0;
  v261 = 0;
  v24 = CoTaskMemAlloc(8 * v5);
  pv[0] = v24;
  if ( !v24 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\SimpleList.h",
      (const char *)0x8007000ELL,
      cchToCopy);
    goto LABEL_129;
  }
  memset_0(v24, 0, 8 * v5);
  v25 = *(_QWORD *)_lambda_fe4c477b74a134c39e12a17cfd840b96_::_lambda_fe4c477b74a134c39e12a17cfd840b96_(&v255, pv);
  pv[1] = (LPVOID)v5;
  v261 = v5;
  while ( v17 < v5 )
  {
    v27 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    v28 = v27;
    if ( v27 )
    {
      v27[4] = L"%02d:(%03dx%03d)";
      *v27 = &GridWorkspaceWorker::`vftable';
      v27[2] = 0;
    }
    else
    {
      v28 = 0;
    }
    *((_QWORD *)pv[0] + v17) = v28;
    if ( !*((_QWORD *)pv[0] + v17) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\SimpleList.h",
        (const char *)0x8007000ELL,
        cchToCopy);
      SimpleList<GridWorkspaceWorker>::Clear(v25);
LABEL_129:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21,
        (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
        (const char *)0x8007000ELL,
        cchToCopyc);
      SimpleList<GridWorkspaceWorker>::Clear(pv);
      CZeroInitNew::operator delete(v14);
      return 2147942414LL;
    }
    ++v17;
  }
  v29 = 0;
  while ( v29 < v5 )
  {
    if ( (LPVOID)v29 >= pv[1] )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\SimpleList.h",
        (const char *)0x80070057LL,
        cchToCopy);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17,
        (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\SimpleList.h",
        (const char *)0x80070057LL,
        cchToCopyi);
      v82 = 37;
      goto LABEL_133;
    }
    v83 = *((_QWORD *)pv[0] + v29);
    v84 = &v14[20 * v29++];
    *(_QWORD *)(v83 + 8) = *(_QWORD *)v84;
    *(_QWORD *)(v83 + 16) = *((_QWORD *)v84 + 1);
    *(_DWORD *)(v83 + 24) = *((_DWORD *)v84 + 4);
  }
  v30 = 13 * (__int64)pv[1];
  if ( 13 * (__int64)pv[1] == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v26);
  v31 = (WorkspaceData *)CoTaskMemAlloc(26 * (__int64)pv[1] + 2);
  v32 = v31;
  if ( !v31 || (v257 = v31, *(_WORD *)v31 = 0, *((_WORD *)v31 + v30) = 0, (v33 = pv[1]) == 0) )
  {
LABEL_84:
    if ( !v32 )
      goto LABEL_132;
    if ( !v3 )
      goto LABEL_86;
    v233 = v3;
    v234 = 64000;
    do
    {
      if ( !*v233 )
        break;
      ++v233;
      --v234;
    }
    while ( v234 );
    v186 = -2147024809;
    if ( v234 )
      v186 = 0;
    v187 = 64000 - v234;
    if ( v234 )
    {
      v194 = (wchar_t *)&v3[v187];
      v195 = 2147483646;
      v196 = v32;
      if ( v187 != 64000 )
      {
        do
        {
          if ( !v195 )
            break;
          if ( !*(_WORD *)v196 )
            break;
          *v194 = *(_WORD *)v196;
          v196 = (WorkspaceData *)((char *)v196 + 2);
          ++v194;
          --v195;
          --v234;
        }
        while ( v234 );
      }
      v197 = v194 - 1;
      if ( v234 )
        v197 = v194;
      *v197 = 0;
      v186 = -2147024774;
      if ( v234 )
        v186 = 0;
    }
    v188 = 0;
    if ( v186 != -2147024774 )
      v188 = v186;
    if ( v188 < 0 )
    {
      v193 = 48;
    }
    else
    {
      v189 = 64000;
      v190 = v3;
      do
      {
        if ( !*v190 )
          break;
        ++v190;
        --v189;
      }
      while ( v189 );
      v191 = -2147024809;
      if ( v189 )
        v191 = 0;
      v192 = 64000 - v189;
      if ( v189 )
      {
        v198 = L"\r\n";
        v199 = (wchar_t *)&v3[v192];
        v200 = 2147483646;
        if ( v192 != 64000 )
        {
          do
          {
            if ( !v200 )
              break;
            if ( !*v198 )
              break;
            *v199++ = *v198++;
            --v200;
            --v189;
          }
          while ( v189 );
        }
        v201 = v199 - 1;
        if ( v189 )
          v201 = v199;
        *v201 = 0;
        v191 = -2147024774;
        if ( v189 )
          v191 = 0;
      }
      v188 = 0;
      if ( v191 != -2147024774 )
        v188 = v191;
      if ( v188 >= 0 )
      {
LABEL_86:
        CoTaskMemFree(v32);
        v60 = pv[0];
        if ( pv[0] )
        {
          v61 = v261;
          v62 = 0;
          if ( v261 )
          {
            do
            {
              v63 = (_QWORD *)v60[v62];
              if ( v63 )
              {
                *v63 = &GridWorkspaceWorker::`vftable';
                operator delete(v63, (const struct std::nothrow_t *)0x28);
                v61 = v261;
                v60 = pv[0];
              }
              ++v62;
            }
            while ( v62 < v61 );
            v4 = v251;
          }
          CoTaskMemFree(v60);
          pv[0] = 0;
          pv[1] = 0;
          v261 = 0;
        }
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v14);
LABEL_94:
        v65 = v253;
        if ( v253 )
          goto LABEL_95;
        v250 = 0;
        ShouldSerialize = DesktopData::ShouldSerialize(v4, &v250);
        if ( ShouldSerialize < 0 )
        {
          v77 = 871;
          goto LABEL_119;
        }
        if ( !v3 )
        {
LABEL_95:
          LODWORD(v258) = 65538;
          if ( v65 )
          {
            lpVtbl = v65->lpVtbl;
            LODWORD(v256) = 0;
            v86 = ((__int64 (__fastcall *)(struct IStream *, char **, __int64, struct WorkspaceData **))lpVtbl->Write)(
                    v65,
                    &v258,
                    4,
                    &v256);
            ShouldSerialize = v86;
            if ( v86 < 0 )
            {
              v76 = (unsigned int)v86;
              v75 = 17;
              goto LABEL_118;
            }
          }
          if ( !v3 )
            goto LABEL_264;
        }
        else
        {
          v227 = 64000;
          v228 = v3;
          if ( v250 )
          {
            do
            {
              if ( !*v228 )
                break;
              ++v228;
              --v227;
            }
            while ( v227 );
            v215 = -2147024809;
            if ( v227 )
              v215 = 0;
            v216 = 64000 - v227;
            if ( v227 )
            {
              v217 = L"    Should Serialize: Yes\r\n";
              v218 = (wchar_t *)&v3[v216];
              v219 = 2147483646;
              if ( v216 != 64000 )
              {
                do
                {
                  if ( !v219 )
                    break;
                  if ( !*v217 )
                    break;
                  *v218++ = *v217++;
                  --v219;
                  --v227;
                }
                while ( v227 );
              }
              v220 = v218 - 1;
              if ( v227 )
                v220 = v218;
              *v220 = 0;
              v215 = -2147024774;
              if ( v227 )
                v215 = 0;
            }
            ShouldSerialize = 0;
            if ( v215 != -2147024774 )
              ShouldSerialize = v215;
            if ( ShouldSerialize < 0 )
            {
              v77 = 877;
              goto LABEL_119;
            }
          }
          else
          {
            do
            {
              if ( !*v228 )
                break;
              ++v228;
              --v227;
            }
            while ( v227 );
            v221 = -2147024809;
            if ( v227 )
              v221 = 0;
            v222 = 64000 - v227;
            if ( v227 )
            {
              v223 = L"    Should Serialize: No\r\n";
              v224 = (wchar_t *)&v3[v222];
              v225 = 2147483646;
              if ( v222 != 64000 )
              {
                do
                {
                  if ( !v225 )
                    break;
                  if ( !*v223 )
                    break;
                  *v224++ = *v223++;
                  --v225;
                  --v227;
                }
                while ( v227 );
              }
              v226 = v224 - 1;
              if ( v227 )
                v226 = v224;
              *v226 = 0;
              v221 = -2147024774;
              if ( v227 )
                v221 = 0;
            }
            ShouldSerialize = 0;
            if ( v221 != -2147024774 )
              ShouldSerialize = v221;
            if ( ShouldSerialize < 0 )
            {
              v77 = 882;
              goto LABEL_119;
            }
          }
          LODWORD(v258) = 65538;
        }
        ShouldSerialize = StringCchPrintfW(v265, 0x100u, L"    Version: %08X");
        if ( ((ShouldSerialize + 0x80000000) & 0x80000000) == 0 && ShouldSerialize != -2147024774 )
        {
          v75 = 47;
          goto LABEL_117;
        }
        v67 = 64000;
        v68 = v3;
        do
        {
          if ( !*v68 )
            break;
          ++v68;
          --v67;
        }
        while ( v67 );
        v69 = -2147024809;
        if ( v67 )
          v69 = 0;
        v70 = 64000 - v67;
        if ( v67 )
        {
          v166 = v265;
          v167 = (wchar_t *)&v3[v70];
          v168 = 2147483646;
          if ( v70 != 64000 )
          {
            do
            {
              if ( !v168 )
                break;
              if ( !*v166 )
                break;
              *v167++ = *v166++;
              --v168;
              --v67;
            }
            while ( v67 );
          }
          v169 = v167 - 1;
          if ( v67 )
            v169 = v167;
          *v169 = 0;
          v69 = -2147024774;
          if ( v67 )
            v69 = 0;
        }
        ShouldSerialize = 0;
        if ( v69 != -2147024774 )
          ShouldSerialize = v69;
        if ( ShouldSerialize < 0 )
        {
          v75 = 49;
          goto LABEL_117;
        }
        v71 = 64000;
        v72 = v3;
        do
        {
          if ( !*v72 )
            break;
          ++v72;
          --v71;
        }
        while ( v71 );
        v73 = -2147024809;
        if ( v71 )
          v73 = 0;
        v74 = 64000 - v71;
        if ( v71 )
        {
          v162 = L"\r\n";
          v163 = (wchar_t *)&v3[v74];
          v164 = 2147483646;
          if ( v74 != 64000 )
          {
            do
            {
              if ( !v164 )
                break;
              if ( !*v162 )
                break;
              *v163++ = *v162++;
              --v164;
              --v71;
            }
            while ( v71 );
          }
          v165 = v163 - 1;
          if ( v71 )
            v165 = v163;
          *v165 = 0;
          v73 = -2147024774;
          if ( v71 )
            v73 = 0;
        }
        ShouldSerialize = 0;
        if ( v73 != -2147024774 )
          ShouldSerialize = v73;
        if ( ShouldSerialize < 0 )
        {
          v75 = 50;
LABEL_117:
          v76 = (unsigned int)ShouldSerialize;
LABEL_118:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v75,
            (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\DesktopIconLayoutHelpers.h",
            (const char *)v76,
            cchToCopy);
          v77 = 886;
LABEL_119:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v77,
            (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
            (const char *)(unsigned int)ShouldSerialize,
            cchToCopy);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x35,
            (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
            (const char *)(unsigned int)ShouldSerialize,
            cchToCopyf);
          return (unsigned int)ShouldSerialize;
        }
LABEL_264:
        v125 = *((_QWORD *)v4 + 5);
        v124 = 0;
        v255 = v125;
        pv[0] = 0;
        pv[1] = 0;
        v261 = 0;
        v147 = CoTaskMemAlloc(8 * v125);
        pv[0] = v147;
        if ( v147 )
        {
          memset_0(v147, 0, 8 * v125);
          v148 = 0;
          v149 = *(_QWORD *)_lambda_fe4c477b74a134c39e12a17cfd840b96_::_lambda_fe4c477b74a134c39e12a17cfd840b96_(
                              &v254,
                              pv);
          pv[1] = (LPVOID)v125;
          v261 = v125;
          while ( v148 < v125 )
          {
            v150 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
            v151 = v150;
            if ( v150 )
            {
              *v150 = &GridWorkspaceWorker::`vftable';
              v150[4] = L"%02d:(%03dx%03d)";
              v150[2] = 0;
            }
            else
            {
              v151 = 0;
            }
            *((_QWORD *)pv[0] + v148) = v151;
            if ( !*((_QWORD *)pv[0] + v148) )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x48,
                (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\SimpleList.h",
                (const char *)0x8007000ELL,
                cchToCopy);
              SimpleList<GridWorkspaceWorker>::Clear(v149);
              goto LABEL_211;
            }
            ++v148;
          }
          v96 = 0;
          v258 = 0;
          if ( v125 )
          {
            do
            {
              if ( (LPVOID)v96 >= pv[1] || v96 >= *((_QWORD *)v4 + 5) )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x52,
                  (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\SimpleList.h",
                  (const char *)0x80070057LL,
                  cchToCopy);
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x17,
                  (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\SimpleList.h",
                  (const char *)0x80070057LL,
                  cchToCopyk);
              }
              else
              {
                v97 = *((_QWORD *)pv[0] + v96);
                v98 = *(_QWORD *)(*((_QWORD *)v4 + 4) + 8 * v96);
                v99 = v98 == -16;
                v100 = v98 + 24;
                if ( v99 )
                  v100 = 0;
                *(_QWORD *)(v97 + 8) = *(_QWORD *)v100;
                *(_QWORD *)(v97 + 16) = *(_QWORD *)(v100 + 8);
                *(_DWORD *)(v97 + 24) = *(_DWORD *)(v100 + 16);
                if ( v96 == v125 - 1 )
                {
                  v101 = 13 * (__int64)pv[1];
                  if ( 13 * (__int64)pv[1] == -1 )
                    wil::details::in1diag3::_FailFast_Unexpected(
                      retaddr,
                      (void *)0xF89,
                      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                      v103);
                  v102 = CoTaskMemAlloc(26 * (__int64)pv[1] + 2);
                  v104 = v102;
                  if ( v102 )
                  {
                    pcchLength = (size_t)v102;
                    *v102 = 0;
                    v102[v101] = 0;
                    if ( pv[1] )
                    {
                      for ( k = 0; k < pv[1]; ++k )
                      {
                        if ( k )
                        {
                          if ( !v101 || v101 > 0x7FFFFFFF )
                            goto LABEL_202;
                          v116 = v101;
                          v117 = v104;
                          while ( *v117 )
                          {
                            ++v117;
                            if ( !--v116 )
                            {
                              v118 = 0;
                              goto LABEL_197;
                            }
                          }
                          v118 = v101 - v116;
LABEL_197:
                          if ( !v116 )
                            goto LABEL_202;
                          v119 = L"|";
                          v120 = &v104[v118];
                          v121 = 2147483646;
                          v122 = v101 - v118;
                          if ( v101 != v118 )
                          {
                            do
                            {
                              if ( !v121 )
                                break;
                              if ( !*v119 )
                                break;
                              *v120++ = *v119++;
                              --v121;
                              --v122;
                            }
                            while ( v122 );
                          }
                          v123 = v120 - 1;
                          if ( v122 )
                            v123 = v120;
                          *v123 = 0;
                          if ( !v122 )
                          {
LABEL_202:
                            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                              &pcchLength,
                              0);
                            v104 = (_WORD *)pcchLength;
                            break;
                          }
                        }
                        if ( k >= pv[1] )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x52,
                            (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\SimpleList.h",
                            (const char *)0x80070057LL,
                            cchToCopy);
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x17,
                            (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\SimpleList.h",
                            (const char *)0x80070057LL,
                            cchToCopyj);
                        }
                        else
                        {
                          v106 = *((_QWORD *)pv[0] + (_QWORD)k);
                          v107 = *(_DWORD *)(v106 + 8);
                          LODWORD(v256) = *(_DWORD *)(v106 + 24);
                          v254 = *(unsigned __int16 **)(v106 + 32);
                          v257 = (WorkspaceData *)CoTaskMemAlloc(0x1Cu);
                          v108 = (unsigned __int16 *)v257;
                          if ( !v257 )
                            goto LABEL_202;
                          v109 = (unsigned int)v256;
                          v110 = v254;
                          *(_WORD *)v257 = 0;
                          v108[13] = 0;
                          LODWORD(cchToCopy) = v107;
                          v111 = StringCchPrintfW(v108, 0xDu, v110, v109);
                          if ( v111 < 0 )
                          {
                            wil::details::in1diag3::_Log_Hr(
                              retaddr,
                              (void *)0x4B,
                              (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\gridworkspaceworker.cpp",
                              (const char *)(unsigned int)v111,
                              v107);
                            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                              &v257,
                              0);
                            v108 = (unsigned __int16 *)v257;
                          }
                          if ( !v108 )
                            goto LABEL_202;
                          if ( v101 - 1 > 0x7FFFFFFE )
                            goto LABEL_203;
                          v113 = v101;
                          v114 = v104;
                          while ( *v114 )
                          {
                            ++v114;
                            if ( !--v113 )
                            {
                              v115 = 0;
                              goto LABEL_187;
                            }
                          }
                          v115 = v101 - v113;
LABEL_187:
                          if ( !v113 || StringCopyWorkerW_0(&v104[v115], v101 - v115, v112, v108, cchToCopy) < 0 )
                          {
LABEL_203:
                            wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(v104);
                            v104 = 0;
                            CoTaskMemFree(v108);
                            break;
                          }
                          CoTaskMemFree(v108);
                        }
                      }
                      v96 = (unsigned __int64)v258;
                    }
                  }
                  if ( v124 )
                    wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(v124);
                  v4 = v251;
                  v124 = v104;
                  v125 = v255;
                }
              }
              v258 = (char *)++v96;
            }
            while ( v96 < v125 );
            v3 = v252;
          }
          v65 = v253;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3C,
            (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\SimpleList.h",
            (const char *)0x8007000ELL,
            cchToCopy);
        }
LABEL_211:
        if ( pv[0] )
        {
          v126 = v261;
          v127 = 0;
          if ( v261 )
          {
            do
            {
              v128 = (_QWORD *)*((_QWORD *)pv[0] + v127);
              if ( v128 )
              {
                *v128 = &GridWorkspaceWorker::`vftable';
                operator delete(v128, (const struct std::nothrow_t *)0x28);
                v126 = v261;
              }
              ++v127;
            }
            while ( v127 < v126 );
            v4 = v251;
          }
          CoTaskMemFree(pv[0]);
        }
        v129 = StringCchPrintfW(v265, 0x100u, L"    This Key: \"%s\"\r\n", v124);
        v130 = 0;
        if ( v129 != -2147024774 )
          v130 = v129;
        if ( v130 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x382,
            (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
            (const char *)(unsigned int)v130,
            cchToCopy);
          if ( !v124 )
            goto LABEL_255;
          goto LABEL_254;
        }
        v131 = L"<none>";
        if ( *((_QWORD *)v4 + 2) )
          v131 = (const wchar_t *)*((_QWORD *)v4 + 2);
        v132 = StringCchPrintfW(v264, 0x100u, L"%s    LinkedKey: \"%s\"", v265, v131);
        v130 = 0;
        if ( v132 != -2147024774 )
          v130 = v132;
        if ( v130 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x38A,
            (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
            (const char *)(unsigned int)v130,
            cchToCopyb);
          if ( v124 )
LABEL_254:
            CoTaskMemFree(v124);
        }
        else
        {
          v133 = StreamHelper_WriteString((char *)v4 + 16, v3, v65, v264);
          v130 = v133;
          if ( v133 >= 0 )
          {
            if ( v124 )
              CoTaskMemFree(v124);
            pcchLength = *((_QWORD *)v4 + 5);
            if ( v65 )
            {
              v145 = v65->lpVtbl;
              LODWORD(v256) = 0;
              v146 = ((__int64 (__fastcall *)(struct IStream *, size_t *, __int64, struct WorkspaceData **))v145->Write)(
                       v65,
                       &pcchLength,
                       8,
                       &v256);
              v56 = v146;
              if ( v146 < 0 )
              {
                v144 = (unsigned int)v146;
                v143 = 17;
LABEL_252:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v143,
                  (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\DesktopIconLayoutHelpers.h",
                  (const char *)v144,
                  cchToCopyb);
                v59 = 920;
LABEL_79:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v59,
                  (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
                  (const char *)(unsigned int)v56,
                  cchToCopyb);
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x37,
                  (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
                  (const char *)(unsigned int)v56,
                  cchToCopye);
                return (unsigned int)v56;
              }
            }
            if ( v3 )
            {
              v134 = StringCchPrintfW(v264, 0x100u, L"    Workspace Count: %d");
              v56 = v134;
              if ( (int)(v134 + 0x80000000) >= 0 && v134 != -2147024774 )
              {
                v143 = 47;
                goto LABEL_251;
              }
              v135 = v3;
              v136 = 64000;
              do
              {
                if ( !*v135 )
                  break;
                ++v135;
                --v136;
              }
              while ( v136 );
              v137 = -2147024809;
              if ( v136 )
                v137 = 0;
              v138 = 64000 - v136;
              if ( v136 )
              {
                v176 = v264;
                v177 = (wchar_t *)&v3[v138];
                v178 = 2147483646;
                if ( v138 != 64000 )
                {
                  do
                  {
                    if ( !v178 )
                      break;
                    if ( !*v176 )
                      break;
                    *v177++ = *v176++;
                    --v178;
                    --v136;
                  }
                  while ( v136 );
                }
                v179 = v177 - 1;
                if ( v136 )
                  v179 = v177;
                *v179 = 0;
                v137 = -2147024774;
                if ( v136 )
                  v137 = 0;
              }
              v56 = 0;
              if ( v137 != -2147024774 )
                v56 = v137;
              if ( v56 < 0 )
              {
                v143 = 49;
                goto LABEL_251;
              }
              v139 = 64000;
              v140 = v3;
              do
              {
                if ( !*v140 )
                  break;
                ++v140;
                --v139;
              }
              while ( v139 );
              v141 = -2147024809;
              if ( v139 )
                v141 = 0;
              v142 = 64000 - v139;
              if ( v139 )
              {
                v170 = L"\r\n";
                v171 = (wchar_t *)&v3[v142];
                v172 = 2147483646;
                if ( v142 != 64000 )
                {
                  do
                  {
                    if ( !v172 )
                      break;
                    if ( !*v170 )
                      break;
                    *v171++ = *v170++;
                    --v172;
                    --v139;
                  }
                  while ( v139 );
                }
                v173 = v171 - 1;
                if ( v139 )
                  v173 = v171;
                *v173 = 0;
                v141 = -2147024774;
                if ( v139 )
                  v141 = 0;
              }
              v56 = 0;
              if ( v141 != -2147024774 )
                v56 = v141;
              if ( v56 < 0 )
              {
                v143 = 50;
LABEL_251:
                v144 = (unsigned int)v56;
                goto LABEL_252;
              }
            }
            for ( m = 0; m < *((_QWORD *)v4 + 5); ++m )
            {
              v175 = *(_QWORD *)(*((_QWORD *)v4 + 4) + 8 * m);
              *(_QWORD *)(v175 + 8) = *((_QWORD *)v4 + 1);
              v56 = (**(__int64 (__fastcall ***)(__int64, struct IStream *, const wchar_t *))v175)(v175, v65, v3);
              if ( v56 < 0 )
              {
                v59 = 928;
                goto LABEL_79;
              }
            }
            if ( DesktopData::IsLinked(v4) )
            {
              for ( n = 0; ; ++n )
              {
                if ( n >= *((_QWORD *)v4 + 5) )
                  goto LABEL_282;
                LODWORD(v258) = *(_DWORD *)(*((_QWORD *)v4 + 8) + 4 * n);
                if ( v65 )
                {
                  v94 = v65->lpVtbl;
                  LODWORD(v256) = 0;
                  v95 = ((__int64 (__fastcall *)(struct IStream *, char **, __int64, struct WorkspaceData **))v94->Write)(
                          v65,
                          &v258,
                          4,
                          &v256);
                  v56 = v95;
                  if ( v95 < 0 )
                    break;
                }
                if ( v3 )
                {
                  v56 = StringCchPrintfW(v264, 0x100u, L"    Source Link Index: %d");
                  if ( (int)(v56 + 0x80000000) >= 0 && v56 != -2147024774 )
                  {
                    v57 = 47;
                    goto LABEL_77;
                  }
                  v88 = 64000;
                  v89 = v3;
                  do
                  {
                    if ( !*v89 )
                      break;
                    ++v89;
                    --v88;
                  }
                  while ( v88 );
                  v90 = -2147024809;
                  if ( v88 )
                    v90 = 0;
                  v91 = 64000 - v88;
                  if ( v88 )
                  {
                    v152 = v264;
                    v153 = (wchar_t *)&v3[v91];
                    v154 = 2147483646;
                    if ( v91 != 64000 )
                    {
                      do
                      {
                        if ( !v154 )
                          break;
                        if ( !*v152 )
                          break;
                        *v153++ = *v152++;
                        --v154;
                        --v88;
                      }
                      while ( v88 );
                    }
                    v155 = v153 - 1;
                    if ( v88 )
                      v155 = v153;
                    *v155 = 0;
                    v90 = -2147024774;
                    if ( v88 )
                      v90 = 0;
                  }
                  v56 = 0;
                  if ( v90 != -2147024774 )
                    v56 = v90;
                  if ( v56 < 0 )
                  {
                    v57 = 49;
LABEL_77:
                    v58 = (unsigned int)v56;
LABEL_78:
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)v57,
                      (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\DesktopIconLayoutHelpers.h",
                      (const char *)v58,
                      cchToCopyb);
                    v59 = 934;
                    goto LABEL_79;
                  }
                  v92 = 64000;
                  v93 = v3;
                  do
                  {
                    if ( !*v93 )
                      break;
                    ++v93;
                    --v92;
                  }
                  while ( v92 );
                  v54 = -2147024809;
                  if ( v92 )
                    v54 = 0;
                  v55 = 64000 - v92;
                  if ( v92 )
                  {
                    v78 = L"\r\n";
                    v79 = (wchar_t *)&v3[v55];
                    v80 = 2147483646;
                    if ( v55 != 64000 )
                    {
                      do
                      {
                        if ( !v80 )
                          break;
                        if ( !*v78 )
                          break;
                        *v79++ = *v78++;
                        --v80;
                        --v92;
                      }
                      while ( v92 );
                    }
                    v81 = v79 - 1;
                    if ( v92 )
                      v81 = v79;
                    *v81 = 0;
                    v54 = -2147024774;
                    if ( v92 )
                      v54 = 0;
                  }
                  v56 = 0;
                  if ( v54 != -2147024774 )
                    v56 = v54;
                  if ( v56 < 0 )
                  {
                    v57 = 50;
                    goto LABEL_77;
                  }
                }
              }
              v58 = (unsigned int)v95;
              v57 = 17;
              goto LABEL_78;
            }
LABEL_282:
            v263 = 0;
            *(_OWORD *)pv = 0;
            v262 = 0;
            DataForTracelog = DesktopData::GetDataForTracelog(v4, (struct DesktopDataForTracelog *)pv);
            v159 = DataForTracelog;
            if ( DataForTracelog < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x6D,
                (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
                (const char *)(unsigned int)DataForTracelog,
                cchToCopyb);
              DesktopDataForTracelog::~DesktopDataForTracelog((DesktopDataForTracelog *)pv);
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x39,
                (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
                (const char *)v159,
                cchToCopyl);
            }
            else
            {
              if ( DesktopIconLayoutTelemetry::IsEnabled(v158, v157) )
              {
                wil::details::static_lazy<DesktopIconLayoutTelemetry>::get(
                  v160,
                  _lambda_94155d05b4417a0d99e43922e5476814_::_lambda_invoker_cdecl_);
                DesktopIconLayoutTelemetry::LogPersistedDesktop_(v161, (const struct DesktopDataForTracelog *)pv);
              }
              DesktopDataForTracelog::~DesktopDataForTracelog((DesktopDataForTracelog *)pv);
            }
            if ( !v3 )
              return 0;
            pcchLength = 0;
            v180 = StringLengthWorkerW_1(v3, 0xFA00u, &pcchLength);
            if ( v180 >= 0 )
            {
              v182 = L"  Desktop Serialize End\r\n";
              v183 = (wchar_t *)&v3[pcchLength];
              v184 = 64000 - pcchLength;
              if ( 64000 != pcchLength )
              {
                v235 = 2147483646;
                do
                {
                  if ( !v235 )
                    break;
                  if ( !*v182 )
                    break;
                  *v183++ = *v182++;
                  --v235;
                  --v184;
                }
                while ( v184 );
              }
              v185 = v183 - 1;
              v180 = -2147024774;
              if ( v184 )
              {
                v185 = v183;
                v180 = 0;
              }
              *v185 = 0;
            }
            v181 = 0;
            if ( v180 != -2147024774 )
              v181 = v180;
            if ( v181 >= 0 )
              return 0;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3E,
              (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
              (const char *)(unsigned int)v181,
              cchToCopyb);
            return (unsigned int)v181;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x392,
            (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
            (const char *)(unsigned int)v133,
            cchToCopyb);
          if ( v124 )
            goto LABEL_254;
        }
LABEL_255:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x36,
          (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
          (const char *)(unsigned int)v130,
          cchToCopyd);
        return (unsigned int)v130;
      }
      v193 = 50;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v193,
      (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
      (const char *)(unsigned int)v188,
      cchToCopy);
    CoTaskMemFree(v32);
    SimpleList<GridWorkspaceWorker>::Clear(pv);
    CZeroInitNew::operator delete(v14);
    return (unsigned int)v188;
  }
  for ( ii = 0; ; ++ii )
  {
    if ( ii >= (unsigned __int64)v33 )
      goto LABEL_83;
    if ( ii )
    {
      if ( !v30 || v30 > 0x7FFFFFFF )
        goto LABEL_82;
      v45 = v30;
      v46 = v32;
      while ( *(_WORD *)v46 )
      {
        v46 = (WorkspaceData *)((char *)v46 + 2);
        if ( !--v45 )
        {
          v47 = 0;
          goto LABEL_62;
        }
      }
      v47 = v30 - v45;
LABEL_62:
      if ( !v45 )
        goto LABEL_82;
      v48 = L"|";
      v49 = (_WORD *)((char *)v32 + 2 * v47);
      v50 = 2147483646;
      v51 = v30 - v47;
      if ( v30 != v47 )
      {
        do
        {
          if ( !v50 )
            break;
          if ( !*v48 )
            break;
          *v49++ = *v48++;
          --v50;
          --v51;
        }
        while ( v51 );
      }
      v52 = v49 - 1;
      if ( v51 )
        v52 = v49;
      *v52 = 0;
      if ( !v51 )
      {
LABEL_82:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v257,
          0);
        v32 = v257;
LABEL_83:
        v3 = v252;
        v4 = v251;
        v14 = v258;
        goto LABEL_84;
      }
      v33 = pv[1];
    }
    if ( ii < (unsigned __int64)v33 )
      break;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\SimpleList.h",
      (const char *)0x80070057LL,
      cchToCopy);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17,
      (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\SimpleList.h",
      (const char *)0x80070057LL,
      cchToCopyg);
LABEL_55:
    v33 = pv[1];
  }
  v35 = *((_QWORD *)pv[0] + ii);
  v36 = *(_DWORD *)(v35 + 8);
  v37 = *(_DWORD *)(v35 + 24);
  pcchLength = *(_QWORD *)(v35 + 32);
  v256 = (struct WorkspaceData *)CoTaskMemAlloc(0x1Cu);
  v38 = (unsigned __int16 *)v256;
  if ( !v256 )
    goto LABEL_82;
  v39 = (const unsigned __int16 *)pcchLength;
  *(_WORD *)v256 = 0;
  v38[13] = 0;
  LODWORD(cchToCopy) = v36;
  v40 = StringCchPrintfW(v38, 0xDu, v39, v37);
  if ( v40 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\gridworkspaceworker.cpp",
      (const char *)(unsigned int)v40,
      v36);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v256,
      0);
    v38 = (unsigned __int16 *)v256;
  }
  if ( !v38 )
    goto LABEL_82;
  if ( v30 - 1 <= 0x7FFFFFFE )
  {
    v42 = v30;
    v43 = v32;
    while ( *(_WORD *)v43 )
    {
      v43 = (WorkspaceData *)((char *)v43 + 2);
      if ( !--v42 )
      {
        v44 = 0;
        goto LABEL_52;
      }
    }
    v44 = v30 - v42;
LABEL_52:
    if ( v42 && StringCopyWorkerW_0((STRSAFE_LPWSTR)v32 + v44, v30 - v44, v41, v38, cchToCopy) >= 0 )
    {
      CoTaskMemFree(v38);
      goto LABEL_55;
    }
  }
  wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(v32);
  CoTaskMemFree(v38);
  v14 = v258;
LABEL_132:
  v82 = 43;
LABEL_133:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v82,
    (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
    (const char *)0x80070057LL,
    cchToCopy);
  SimpleList<GridWorkspaceWorker>::Clear(pv);
  CZeroInitNew::operator delete(v14);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18003cde0  push    rbp
0x18003cde2  push    rbx
0x18003cde3  push    r12
0x18003cde5  push    r13
0x18003cde7  push    r14
0x18003cde9  lea     rbp, [rsp-3D0h]
0x18003cdf1  sub     rsp, 4D0h
0x18003cdf8  mov     rax, cs:__security_cookie
0x18003cdff  xor     rax, rsp
0x18003ce02  mov     [rbp+3F0h+var_40], rax
0x18003ce09  mov     [rsp+4F0h+var_4B0], r8
0x18003ce0e  mov     r12, r8
0x18003ce11  mov     [rsp+4F0h+var_4A8], rdx
0x18003ce16  mov     r13, rcx
0x18003ce19  mov     [rsp+4F0h+var_4B8], rcx
0x18003ce1e  mov     r10d, 0FA00h
0x18003ce24  mov     r14d, 7FFFFFFEh
0x18003ce2a  test    r8, r8
0x18003ce2d  jnz     loc_18003E627
0x18003ce33  mov     [rsp+4F0h+arg_18], rsi
0x18003ce3b  xor     esi, esi
0x18003ce3d  mov     [rsp+4F0h+var_28], rdi
0x18003ce45  xor     dil, dil
0x18003ce48  mov     [rsp+4F0h+var_30], r15
0x18003ce50  xor     r15b, r15b
0x18003ce53  xor     ebx, ebx
0x18003ce55  cmp     rbx, [r13+28h]
0x18003ce59  jnb     short loc_18003CEBC
0x18003ce5b  mov     rax, [r13+20h]
0x18003ce5f  lea     r8, [rsp+4F0h+var_490]; struct WorkspaceData **
0x18003ce64  mov     [rsp+4F0h+var_490], 0
0x18003ce6d  mov     rdx, rbx; unsigned __int64
0x18003ce70  mov     rcx, [rax+rbx*8]
0x18003ce74  mov     [rsp+4F0h+var_490], rcx
0x18003ce79  mov     rcx, r13; this
0x18003ce7c  call    ?GetWorkspace@DesktopData@@QEBAJ_KPEAPEAVWorkspaceData@@@Z; DesktopData::GetWorkspace(unsigned __int64,WorkspaceData * *)
0x18003ce81  mov     r14d, eax
0x18003ce84  test    eax, eax
0x18003ce86  js      loc_18003D6F6
0x18003ce8c  mov     rax, [rsp+4F0h+var_490]
0x18003ce91  cmp     qword ptr [rax+48h], 0
0x18003ce96  jnz     short loc_18003CEA5
0x18003ce98  test    byte ptr [rax+28h], 1
0x18003ce9c  jz      loc_18003CFB8
0x18003cea2  mov     dil, 1
0x18003cea5  inc     rsi
0x18003cea8  movzx   edi, dil
0x18003ceac  test    r15b, r15b
0x18003ceaf  mov     eax, 1
0x18003ceb4  cmovnz  edi, eax
0x18003ceb7  jmp     loc_18003CFBB
0x18003cebc  test    dil, dil
0x18003cebf  jz      loc_18003D42F
0x18003cec5  test    r12, r12
0x18003cec8  jnz     loc_18003E675
0x18003cece  mov     eax, 14h
0x18003ced3  mul     rsi
0x18003ced6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003cedd  mov     rbx, rax
0x18003cee0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18003cee7  cmovb   rbx, rax
0x18003ceeb  mov     rcx, rbx; unsigned __int64
0x18003ceee  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003cef3  mov     [rsp+4F0h+var_480], rax
0x18003cef8  mov     r15, rax
0x18003cefb  test    rax, rax
0x18003cefe  jz      loc_18003D354
0x18003cf04  mov     r8, rbx; Size
0x18003cf07  xor     edx, edx; Val
0x18003cf09  mov     rcx, rax; void *
0x18003cf0c  call    memset_0
0x18003cf11  xor     eax, eax
0x18003cf13  lea     r9, [rsp+4F0h+var_488]; unsigned __int64 *
0x18003cf18  xor     r8d, r8d; bool *
0x18003cf1b  mov     [rsp+4F0h+var_488], rax
0x18003cf20  xor     edx, edx; bool *
0x18003cf22  mov     [rsp+4F0h+cchToCopy], rax; int
0x18003cf27  mov     rcx, r13; this
0x18003cf2a  call    ?GetWorkspaceUtilizationInfo@DesktopData@@QEBAJPEA_N0PEA_K00@Z; DesktopData::GetWorkspaceUtilizationInfo(bool *,bool *,unsigned __int64 *,bool *,bool *)
0x18003cf2f  mov     edi, eax
0x18003cf31  test    eax, eax
0x18003cf33  js      loc_18003D5E7
0x18003cf39  cmp     [rsp+4F0h+var_488], rsi
0x18003cf3e  jnz     loc_18003D22A
0x18003cf44  xor     edi, edi
0x18003cf46  mov     r14d, edi
0x18003cf49  mov     ebx, edi
0x18003cf4b  nop     dword ptr [rax+rax+00h]
0x18003cf50  cmp     rbx, [r13+28h]
0x18003cf54  jnb     short loc_18003CFC3
0x18003cf56  lea     r8, [rsp+4F0h+var_488]; struct WorkspaceData **
0x18003cf5b  mov     [rsp+4F0h+var_488], rdi
0x18003cf60  mov     rdx, rbx; unsigned __int64
0x18003cf63  mov     rcx, r13; this
0x18003cf66  call    ?GetWorkspace@DesktopData@@QEBAJ_KPEAPEAVWorkspaceData@@@Z; DesktopData::GetWorkspace(unsigned __int64,WorkspaceData * *)
0x18003cf6b  mov     edi, eax
0x18003cf6d  test    eax, eax
0x18003cf6f  js      loc_18003D334
0x18003cf75  mov     rdx, [rsp+4F0h+var_488]
0x18003cf7a  mov     rcx, rdx; this
0x18003cf7d  call    ?IsIgnorable@WorkspaceData@@QEBA_NXZ; WorkspaceData::IsIgnorable(void)
0x18003cf82  test    al, al
0x18003cf84  jnz     short loc_18003CFB1
0x18003cf86  cmp     r14, rsi
0x18003cf89  jnb     loc_18003E6C9
0x18003cf8f  lea     rax, [r14+r14*4]
0x18003cf93  inc     r14
0x18003cf96  lea     rcx, [r15+rax*4]
0x18003cf9a  mov     rax, [rdx+18h]
0x18003cf9e  mov     [rcx], rax
0x18003cfa1  movsd   xmm0, qword ptr [rdx+20h]
0x18003cfa6  movsd   qword ptr [rcx+8], xmm0
0x18003cfab  mov     eax, [rdx+28h]
0x18003cfae  mov     [rcx+10h], eax
0x18003cfb1  inc     rbx
0x18003cfb4  xor     edi, edi
0x18003cfb6  jmp     short loc_18003CF50
0x18003cfb8  mov     r15b, 1
0x18003cfbb  inc     rbx
0x18003cfbe  jmp     loc_18003CE55
0x18003cfc3  lea     rbx, ds:0[rsi*8]
0x18003cfcb  mov     [rbp+3F0h+pv], rdi
0x18003cfcf  mov     rcx, rbx; cb
0x18003cfd2  mov     [rbp+3F0h+pv+8], rdi
0x18003cfd6  mov     [rbp+3F0h+var_460], rdi
0x18003cfda  call    cs:__imp_CoTaskMemAlloc
0x18003cfe0  mov     [rbp+3F0h+pv], rax
0x18003cfe4  test    rax, rax
0x18003cfe7  jz      loc_18003E6EE
0x18003cfed  mov     r8, rbx; Size
0x18003cff0  xor     edx, edx; Val
0x18003cff2  mov     rcx, rax; void *
0x18003cff5  call    memset_0
0x18003cffa  lea     rdx, [rbp+3F0h+pv]
0x18003cffe  lea     rcx, [rsp+4F0h+var_498]
0x18003d003  call    ??0_lambda_fe4c477b74a134c39e12a17cfd840b96_@@QEAA@PEAV?$SimpleList@VIconGridItemWorker@@@@@Z; _lambda_fe4c477b74a134c39e12a17cfd840b96_::_lambda_fe4c477b74a134c39e12a17cfd840b96_(SimpleList<IconGridItemWorker> *)
0x18003d008  lea     r14, a02d03dx03d; "%02d:(%03dx%03d)"
0x18003d00f  mov     rbx, [rax]
0x18003d012  mov     [rbp+3F0h+pv+8], rsi
0x18003d016  mov     [rbp+3F0h+var_460], rsi
0x18003d01a  cmp     rdi, rsi
0x18003d01d  jnb     short loc_18003D06C
0x18003d01f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003d026  mov     ecx, 28h ; '('; unsigned __int64
0x18003d02b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003d030  mov     rcx, rax
0x18003d033  test    rax, rax
0x18003d036  jz      loc_18003D5E0
0x18003d03c  lea     rax, ??_7GridWorkspaceWorker@@6B@; const GridWorkspaceWorker::`vftable'
0x18003d043  mov     [rcx+20h], r14
0x18003d047  mov     [rcx], rax
0x18003d04a  xor     eax, eax
0x18003d04c  mov     [rcx+10h], rax
0x18003d050  mov     rax, [rbp+3F0h+pv]
0x18003d054  mov     [rax+rdi*8], rcx
0x18003d058  mov     rax, [rbp+3F0h+pv]
0x18003d05c  cmp     qword ptr [rax+rdi*8], 0
0x18003d061  jz      loc_18003D607
0x18003d067  inc     rdi
0x18003d06a  jmp     short loc_18003D01A
0x18003d06c  xor     r8d, r8d
0x18003d06f  cmp     r8, rsi
0x18003d072  jb      loc_18003D734
0x18003d078  imul    r14, [rbp+3F0h+pv+8], 0Dh
0x18003d07d  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18003d081  jz      loc_18003E711
0x18003d087  lea     rcx, ds:2[r14*2]; cb
0x18003d08f  call    cs:__imp_CoTaskMemAlloc
0x18003d095  mov     rdi, rax
0x18003d098  test    rax, rax
0x18003d09b  jz      loc_18003D399
0x18003d0a1  xor     eax, eax
0x18003d0a3  mov     [rsp+4F0h+var_488], rdi
0x18003d0a8  mov     [rdi], ax
0x18003d0ab  mov     [rdi+r14*2], ax
0x18003d0b0  mov     rax, [rbp+3F0h+pv+8]
0x18003d0b4  test    rax, rax
0x18003d0b7  jz      loc_18003D399
0x18003d0bd  xor     esi, esi
0x18003d0bf  cmp     rsi, rax
0x18003d0c2  jnb     loc_18003D38A
0x18003d0c8  test    rsi, rsi
0x18003d0cb  jnz     loc_18003D1B0
0x18003d0d1  cmp     rsi, rax
0x18003d0d4  jnb     loc_18003D666
0x18003d0da  mov     rax, [rbp+3F0h+pv]
0x18003d0de  mov     rcx, [rax+rsi*8]
0x18003d0e2  mov     rax, [rcx+20h]
0x18003d0e6  mov     r15d, [rcx+8]
0x18003d0ea  mov     r12d, [rcx+0Ch]
0x18003d0ee  mov     r13d, [rcx+18h]
0x18003d0f2  mov     ecx, 1Ch; cb
0x18003d0f7  mov     [rsp+4F0h+pcchLength], rax
0x18003d0fc  call    cs:__imp_CoTaskMemAlloc
0x18003d102  mov     [rsp+4F0h+var_490], rax
0x18003d107  mov     rbx, rax
0x18003d10a  test    rax, rax
0x18003d10d  jz      loc_18003D379
0x18003d113  mov     r8, [rsp+4F0h+pcchLength]; unsigned __int16 *
0x18003d118  xor     eax, eax
0x18003d11a  mov     [rbx], ax
0x18003d11d  mov     r9d, r13d
0x18003d120  mov     dword ptr [rsp+4F0h+var_4C8], r12d
0x18003d125  mov     edx, 0Dh; unsigned __int64
0x18003d12a  mov     rcx, rbx; unsigned __int16 *
0x18003d12d  mov     [rbx+1Ah], ax
0x18003d131  mov     dword ptr [rsp+4F0h+cchToCopy], r15d; int
0x18003d136  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003d13b  test    eax, eax
0x18003d13d  js      loc_18003D578
0x18003d143  test    rbx, rbx
0x18003d146  jz      loc_18003D379
0x18003d14c  lea     rax, [r14-1]
0x18003d150  cmp     rax, 7FFFFFFEh
0x18003d156  ja      loc_18003D6A7
0x18003d15c  mov     rcx, r14
0x18003d15f  mov     rax, rdi
0x18003d162  cmp     word ptr [rax], 0
0x18003d166  jz      loc_18003E764
0x18003d16c  add     rax, 2
0x18003d170  sub     rcx, 1
0x18003d174  jnz     short loc_18003D162
0x18003d176  xor     eax, eax
0x18003d178  test    rcx, rcx
0x18003d17b  jz      loc_18003D6A7
0x18003d181  mov     rdx, r14
0x18003d184  lea     rcx, [rdi+rax*2]; pszDest
0x18003d188  sub     rdx, rax; cchDest
0x18003d18b  mov     r9, rbx; pszSrc
0x18003d18e  call    StringCopyWorkerW_0
0x18003d193  test    eax, eax
0x18003d195  js      loc_18003D6A7
0x18003d19b  mov     rcx, rbx; pv
0x18003d19e  call    cs:__imp_CoTaskMemFree
0x18003d1a4  mov     rax, [rbp+3F0h+pv+8]
0x18003d1a8  inc     rsi
0x18003d1ab  jmp     loc_18003D0BF
0x18003d1b0  test    r14, r14
0x18003d1b3  jz      loc_18003D379
0x18003d1b9  cmp     r14, 7FFFFFFFh
0x18003d1c0  ja      loc_18003D379
0x18003d1c6  mov     rax, r14
0x18003d1c9  mov     rcx, rdi
0x18003d1cc  cmp     word ptr [rcx], 0
0x18003d1d0  jz      loc_18003E72A
0x18003d1d6  add     rcx, 2
0x18003d1da  sub     rax, 1
0x18003d1de  jnz     short loc_18003D1CC
0x18003d1e0  xor     ecx, ecx
0x18003d1e2  test    rax, rax
0x18003d1e5  jz      loc_18003D379
0x18003d1eb  mov     rdx, r14
0x18003d1ee  lea     r9, asc_1805D494C; "|"
0x18003d1f5  lea     rax, [rdi+rcx*2]
0x18003d1f9  mov     r8d, 7FFFFFFEh
0x18003d1ff  sub     rdx, rcx
0x18003d202  jnz     loc_18003E735
0x18003d208  test    rdx, rdx
0x18003d20b  lea     rcx, [rax-2]
0x18003d20f  cmovnz  rcx, rax
0x18003d213  xor     eax, eax
0x18003d215  mov     [rcx], ax
0x18003d218  test    rdx, rdx
0x18003d21b  jz      loc_18003D379
0x18003d221  mov     rax, [rbp+3F0h+pv+8]
0x18003d225  jmp     loc_18003D0D1
0x18003d22a  mov     rcx, [rbp+3F8h]; this
0x18003d231  lea     r8, aShellShell32Ic_11; "shell\\shell32\\iconlayoutengine\\datam"...
0x18003d238  mov     r9d, 80070057h; char *
0x18003d23e  mov     edx, 2F6h; void *
0x18003d243  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d248  mov     edi, 80070057h
0x18003d24d  mov     rcx, [rbp+3F8h]; this
0x18003d254  lea     r8, aShellShell32Ic_11; "shell\\shell32\\iconlayoutengine\\datam"...
0x18003d25b  mov     r9d, edi; char *
0x18003d25e  mov     edx, 1Fh; void *
0x18003d263  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d268  mov     rcx, r15; lpMem
0x18003d26b  call    ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
0x18003d270  mov     eax, edi
0x18003d272  jmp     loc_18003D2FD
0x18003d277  test    rdx, rdx
0x18003d27a  mov     ecx, 80070057h
0x18003d27f  mov     r8, rsi
0x18003d282  cmovnz  ecx, r14d
0x18003d286  sub     r8, rdx
0x18003d289  test    rdx, rdx
0x18003d28c  cmovz   r8, r14
0x18003d290  jnz     loc_18003D5A9
0x18003d296  cmp     ecx, 8007007Ah
0x18003d29c  mov     ebx, r14d
0x18003d29f  cmovnz  ebx, ecx
0x18003d2a2  test    ebx, ebx
0x18003d2a4  jns     loc_18003D7A8
0x18003d2aa  mov     edx, 32h ; '2'; void *
0x18003d2af  mov     r9d, ebx; char *
0x18003d2b2  mov     rcx, [rbp+3F8h]; this
0x18003d2b9  lea     r8, aShellShell32Ic_6; "shell\\shell32\\iconlayoutengine\\datam"...
0x18003d2c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d2c5  mov     edx, 3A6h; void *
  ... truncated ...
```
