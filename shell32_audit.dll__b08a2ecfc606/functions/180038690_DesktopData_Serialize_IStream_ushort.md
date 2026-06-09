# DesktopData::Serialize(IStream *,ushort *)

- ea: `0x180038690`
- end: `0x18003a3d2`
- name: `?Serialize@DesktopData@@UEAAJPEAUIStream@@PEAG@Z`
- size: `7490`
- prototype: `__int64 __fastcall(DesktopData *__hidden this, struct IStream *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18003439c`
- `0x180034fec`
- `0x180036784`
- `0x180038608`
- `0x180038690`
- `0x18003a3e0`
- `0x18003a480`
- `0x18003a4c8`
- `0x18003a4e4`
- `0x18003a560`
- `0x18003a59c`
- `0x18003a608`
- `0x18003ab0c`
- `0x18003acb8`
- `0x18003acf4`
- `0x18003adc8`
- `0x18003b1e0`
- `0x180078a24`
- `0x18009d460`
- `0x1801d3200`
- `0x1801eb2d8`
- `0x1801ee1bc`
- `0x180249490`
- `0x1802494e0`
- `0x18024999c`
- `0x180249d64`
- `0x18024a53c`
- `0x18025cc2c`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038d9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038d9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038db3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038db3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038a73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038d26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038d7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039042`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003941a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003965b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003968f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800396cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039c61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a0e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038a73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038d26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038d7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039042`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003941a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003965b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003968f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800396cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039c61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a0e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003889a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038955`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800389c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800392f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003936d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039863`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003889a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038955`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800389c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800392f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003936d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039863`

## string_xrefs

- `0x1800394f6`: `%s    LinkedKey: "%s"`
- `0x180039dc0`: `    Has Holes, compressed key =`
- `0x180038b79`: `    Source Link Index: %d`
- `0x18003a014`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18003a2a5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall DesktopData::Serialize(DesktopData *this, struct IStream *a2, unsigned __int16 *a3)
{
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
  unsigned __int64 ii; // rbx
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
  unsigned __int64 jj; // rsi
  __int64 v35; // rcx
  int v36; // r15d
  unsigned int v37; // r13d
  unsigned __int16 *v38; // rbx
  unsigned __int16 *v39; // r8
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
  unsigned __int64 n; // rdi
  int v55; // ebx
  HRESULT v56; // r8d
  size_t v57; // r11
  HRESULT v58; // r8d
  __int64 v59; // r11
  __int64 v60; // rdx
  unsigned __int64 v61; // r9
  __int64 v62; // rdx
  STRSAFE_PCNZWCH v63; // r10
  _QWORD *v64; // rcx
  unsigned __int64 v65; // rax
  unsigned __int64 v66; // rbx
  _QWORD *v67; // r8
  HANDLE ProcessHeap; // rax
  __int64 *v69; // rdi
  const wchar_t *v70; // r15
  int ShouldSerialize; // ebx
  __int64 v72; // rdx
  const wchar_t *v73; // rax
  int v74; // ecx
  __int64 v75; // r8
  __int64 v76; // rdx
  const wchar_t *v77; // rax
  int v78; // ecx
  __int64 v79; // r8
  __int64 v80; // rdx
  unsigned __int64 v81; // r9
  __int64 v82; // rdx
  const unsigned __int16 *v83; // r9
  __int64 v84; // rcx
  wchar_t *v85; // r8
  size_t v86; // rdx
  wchar_t *v87; // rcx
  int v88; // ebx
  __int64 v89; // rdx
  char *v90; // rcx
  __int64 v91; // rax
  int v92; // eax
  __int64 v93; // rax
  int v94; // eax
  unsigned __int16 *v95; // r9
  __int64 v96; // rcx
  wchar_t *v97; // r8
  size_t v98; // rdx
  wchar_t *v99; // rcx
  unsigned __int64 v100; // r15
  __int64 v101; // r8
  __int64 v102; // rdx
  bool v103; // zf
  __int64 v104; // rdx
  unsigned __int64 v105; // rsi
  unsigned __int16 *v106; // rax
  const char *v107; // r9
  unsigned __int16 *v108; // r14
  char *k; // r15
  __int64 v110; // rcx
  int v111; // r12d
  unsigned __int16 *v112; // rbx
  __int64 v113; // r9
  unsigned __int16 *v114; // r8
  int v115; // eax
  size_t *v116; // r8
  unsigned __int64 v117; // rax
  unsigned __int16 *v118; // rcx
  unsigned __int64 v119; // rcx
  unsigned __int64 v120; // rax
  unsigned __int16 *v121; // rcx
  unsigned __int64 v122; // rcx
  const WCHAR *v123; // r9
  unsigned __int16 *v124; // rax
  __int64 v125; // r8
  unsigned __int64 v126; // rdx
  unsigned __int16 *v127; // rcx
  int v128; // eax
  int v129; // ebx
  const wchar_t *v130; // rcx
  int v131; // eax
  __int64 *v132; // r12
  int v133; // eax
  const wchar_t *v134; // rax
  __int64 v135; // rdx
  int v136; // r9d
  int v137; // ecx
  __int64 v138; // rsi
  __int64 v139; // r8
  __int64 v140; // rcx
  const wchar_t *v141; // rax
  __int64 v142; // rdx
  __int64 v143; // rdx
  unsigned __int64 v144; // r9
  unsigned __int16 *v145; // rdi
  unsigned __int64 v146; // r14
  __int64 v147; // rax
  int v148; // eax
  void *v149; // rax
  unsigned __int64 v150; // rsi
  __int64 v151; // rbx
  _QWORD *v152; // rax
  _QWORD *v153; // rcx
  bool IsLinked; // al
  int DataForTracelog; // eax
  unsigned __int64 v156; // rdx
  unsigned __int8 v157; // cl
  unsigned int v158; // ebx
  __int64 v159; // rcx
  DesktopIconLayoutTelemetry *v160; // rcx
  const unsigned __int16 *v161; // r9
  wchar_t *v162; // rax
  __int64 v163; // rcx
  wchar_t *v164; // rcx
  unsigned __int16 *v165; // r9
  wchar_t *v166; // rax
  __int64 v167; // rcx
  wchar_t *v168; // rcx
  const unsigned __int16 *v169; // r9
  wchar_t *v170; // rax
  __int64 v171; // rcx
  __int64 v172; // r8
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
  size_t v184; // r14
  wchar_t *v185; // rcx
  int v186; // ecx
  __int64 v187; // rdx
  __int64 v188; // rdx
  _WORD *v189; // rax
  int v190; // ecx
  __int64 v191; // r8
  wchar_t *v192; // rax
  __int64 v193; // rcx
  wchar_t *v194; // r9
  wchar_t *v195; // rcx
  const unsigned __int16 *v196; // r9
  wchar_t *v197; // rax
  __int64 v198; // rcx
  wchar_t *v199; // rcx
  int v200; // ecx
  __int64 v201; // rdx
  int v202; // ebx
  const wchar_t *v203; // r9
  unsigned __int16 *v204; // rax
  __int64 v205; // rcx
  unsigned __int16 *v206; // rcx
  int v207; // ecx
  __int64 v208; // rdx
  int v209; // ebx
  const wchar_t *v210; // r9
  wchar_t *v211; // rax
  __int64 v212; // rcx
  wchar_t *v213; // rcx
  int v214; // ecx
  __int64 v215; // r8
  const wchar_t *v216; // r9
  wchar_t *v217; // rax
  __int64 v218; // rcx
  wchar_t *v219; // rcx
  int v220; // ecx
  __int64 v221; // r8
  const wchar_t *v222; // r9
  wchar_t *v223; // rax
  __int64 v224; // rcx
  wchar_t *v225; // rcx
  __int64 v226; // rdx
  STRSAFE_PCNZWCH v227; // rax
  __int64 v228; // r8
  unsigned __int16 *v229; // rax
  STRSAFE_PCNZWCH v230; // rax
  __int64 v231; // r8
  STRSAFE_PCNZWCH v232; // rax
  __int64 v233; // r8
  size_t cchToCopy; // [rsp+20h] [rbp-E0h]
  int cchToCopya; // [rsp+20h] [rbp-E0h]
  int cchToCopyb; // [rsp+20h] [rbp-E0h]
  int cchToCopye; // [rsp+20h] [rbp-E0h]
  int cchToCopyf; // [rsp+20h] [rbp-E0h]
  int cchToCopyc; // [rsp+20h] [rbp-E0h]
  int cchToCopyg; // [rsp+20h] [rbp-E0h]
  int cchToCopyh; // [rsp+20h] [rbp-E0h]
  int cchToCopyi; // [rsp+20h] [rbp-E0h]
  int cchToCopyj; // [rsp+20h] [rbp-E0h]
  int cchToCopyd; // [rsp+20h] [rbp-E0h]
  int cchToCopyk; // [rsp+20h] [rbp-E0h]
  int cchToCopyl; // [rsp+20h] [rbp-E0h]
  int cchToCopym; // [rsp+20h] [rbp-E0h]
  bool *v248; // [rsp+28h] [rbp-D8h]
  bool v249; // [rsp+30h] [rbp-D0h] BYREF
  STRSAFE_PCNZWCH psz; // [rsp+38h] [rbp-C8h]
  DesktopData *v251; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v252; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v253; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v254; // [rsp+58h] [rbp-A8h] BYREF
  struct WorkspaceData *v255; // [rsp+60h] [rbp-A0h] BYREF
  WorkspaceData *v256; // [rsp+68h] [rbp-98h] BYREF
  char *j; // [rsp+70h] [rbp-90h] BYREF
  size_t pcchLength; // [rsp+78h] [rbp-88h] BYREF
  LPVOID pv[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v260; // [rsp+90h] [rbp-70h]
  __int128 v261; // [rsp+98h] [rbp-68h]
  __int64 v262; // [rsp+A8h] [rbp-58h]
  unsigned __int16 v263[256]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v264[256]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4F8h] [rbp+3F8h]

  psz = a3;
  pcchLength = (size_t)a2;
  v4 = this;
  v251 = this;
  if ( a3 )
  {
    v228 = 64000;
    v229 = a3;
    do
    {
      if ( !*v229 )
        break;
      ++v229;
      --v228;
    }
    while ( v228 );
    v200 = -2147024809;
    if ( v228 )
      v200 = 0;
    v201 = 64000 - v228;
    if ( v228 )
    {
      v203 = L"  Desktop Serialize Begin\r\n";
      v204 = &a3[v201];
      v205 = 2147483646;
      if ( v201 != 64000 )
      {
        do
        {
          if ( !v205 )
            break;
          if ( !*v203 )
            break;
          *v204++ = *v203++;
          --v205;
          --v228;
        }
        while ( v228 );
      }
      v206 = v204 - 1;
      if ( v228 )
        v206 = v204;
      *v206 = 0;
      v200 = -2147024774;
      if ( v228 )
        v200 = 0;
    }
    v202 = 0;
    if ( v200 != -2147024774 )
      v202 = v200;
    if ( v202 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11,
        (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
        (const char *)(unsigned int)v202,
        cchToCopy);
      return (unsigned int)v202;
    }
  }
  v5 = 0;
  v6 = 0;
  v7 = 0;
  for ( i = 0; i < *((_QWORD *)v4 + 5); ++i )
  {
    v9 = *((_QWORD *)v4 + 4);
    v255 = 0;
    v255 = *(struct WorkspaceData **)(v9 + 8 * i);
    Workspace = DesktopData::GetWorkspace(v4, i, &v255);
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
    if ( !*((_QWORD *)v255 + 9) )
    {
      if ( (*((_BYTE *)v255 + 40) & 1) == 0 )
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
  {
LABEL_102:
    v69 = (__int64 *)pcchLength;
    if ( pcchLength )
    {
      v70 = psz;
    }
    else
    {
      v249 = 0;
      ShouldSerialize = DesktopData::ShouldSerialize(v4, &v249);
      if ( ShouldSerialize < 0 )
      {
        v82 = 871;
        goto LABEL_128;
      }
      v70 = psz;
      if ( psz )
      {
        v226 = 64000;
        v227 = psz;
        if ( v249 )
        {
          do
          {
            if ( !*v227 )
              break;
            ++v227;
            --v226;
          }
          while ( v226 );
          v214 = -2147024809;
          if ( v226 )
            v214 = 0;
          v215 = 64000 - v226;
          if ( v226 )
          {
            v216 = L"    Should Serialize: Yes\r\n";
            v217 = (wchar_t *)&psz[v215];
            v218 = 2147483646;
            if ( v215 != 64000 )
            {
              do
              {
                if ( !v218 )
                  break;
                if ( !*v216 )
                  break;
                *v217++ = *v216++;
                --v218;
                --v226;
              }
              while ( v226 );
            }
            v219 = v217 - 1;
            if ( v226 )
              v219 = v217;
            *v219 = 0;
            v214 = -2147024774;
            if ( v226 )
              v214 = 0;
          }
          ShouldSerialize = 0;
          if ( v214 != -2147024774 )
            ShouldSerialize = v214;
          if ( ShouldSerialize < 0 )
          {
            v82 = 877;
            goto LABEL_128;
          }
        }
        else
        {
          do
          {
            if ( !*v227 )
              break;
            ++v227;
            --v226;
          }
          while ( v226 );
          v220 = -2147024809;
          if ( v226 )
            v220 = 0;
          v221 = 64000 - v226;
          if ( v226 )
          {
            v222 = L"    Should Serialize: No\r\n";
            v223 = (wchar_t *)&psz[v221];
            v224 = 2147483646;
            if ( v221 != 64000 )
            {
              do
              {
                if ( !v224 )
                  break;
                if ( !*v222 )
                  break;
                *v223++ = *v222++;
                --v224;
                --v226;
              }
              while ( v226 );
            }
            v225 = v223 - 1;
            if ( v226 )
              v225 = v223;
            *v225 = 0;
            v220 = -2147024774;
            if ( v226 )
              v220 = 0;
          }
          ShouldSerialize = 0;
          if ( v220 != -2147024774 )
            ShouldSerialize = v220;
          if ( ShouldSerialize < 0 )
          {
            v82 = 882;
            goto LABEL_128;
          }
        }
        LODWORD(j) = 65538;
LABEL_106:
        ShouldSerialize = StringCchPrintfW(v264, 0x100u, L"    Version: %08X");
        if ( ((ShouldSerialize + 0x80000000) & 0x80000000) == 0 && ShouldSerialize != -2147024774 )
        {
          v80 = 47;
          goto LABEL_126;
        }
        v72 = 64000;
        v73 = v70;
        do
        {
          if ( !*v73 )
            break;
          ++v73;
          --v72;
        }
        while ( v72 );
        v74 = -2147024809;
        if ( v72 )
          v74 = 0;
        v75 = 64000 - v72;
        if ( v72 )
        {
          v165 = v264;
          v166 = (wchar_t *)&v70[v75];
          v167 = 2147483646;
          if ( v75 != 64000 )
          {
            do
            {
              if ( !v167 )
                break;
              if ( !*v165 )
                break;
              *v166++ = *v165++;
              --v167;
              --v72;
            }
            while ( v72 );
          }
          v168 = v166 - 1;
          if ( v72 )
            v168 = v166;
          *v168 = 0;
          v74 = -2147024774;
          if ( v72 )
            v74 = 0;
        }
        ShouldSerialize = 0;
        if ( v74 != -2147024774 )
          ShouldSerialize = v74;
        if ( ShouldSerialize < 0 )
        {
          v80 = 49;
          goto LABEL_126;
        }
        v76 = 64000;
        v77 = v70;
        do
        {
          if ( !*v77 )
            break;
          ++v77;
          --v76;
        }
        while ( v76 );
        v78 = -2147024809;
        if ( v76 )
          v78 = 0;
        v79 = 64000 - v76;
        if ( v76 )
        {
          v161 = L"\r\n";
          v162 = (wchar_t *)&v70[v79];
          v163 = 2147483646;
          if ( v79 != 64000 )
          {
            do
            {
              if ( !v163 )
                break;
              if ( !*v161 )
                break;
              *v162++ = *v161++;
              --v163;
              --v76;
            }
            while ( v76 );
          }
          v164 = v162 - 1;
          if ( v76 )
            v164 = v162;
          *v164 = 0;
          v78 = -2147024774;
          if ( v76 )
            v78 = 0;
        }
        ShouldSerialize = 0;
        if ( v78 != -2147024774 )
          ShouldSerialize = v78;
        if ( ShouldSerialize < 0 )
        {
          v80 = 50;
LABEL_126:
          v81 = (unsigned int)ShouldSerialize;
LABEL_127:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v80,
            (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\DesktopIconLayoutHelpers.h",
            (const char *)v81,
            cchToCopy);
          v82 = 886;
LABEL_128:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v82,
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
LABEL_255:
        v146 = *((_QWORD *)v4 + 5);
        v145 = 0;
        v254 = v146;
        pv[0] = 0;
        pv[1] = 0;
        v260 = 0;
        v149 = CoTaskMemAlloc(8 * v146);
        pv[0] = v149;
        if ( v149 )
        {
          memset_0(v149, 0, 8 * v146);
          v150 = 0;
          v151 = *(_QWORD *)_lambda_fe4c477b74a134c39e12a17cfd840b96_::_lambda_fe4c477b74a134c39e12a17cfd840b96_(
                              &v253,
                              pv);
          pv[1] = (LPVOID)v146;
          v260 = v146;
          while ( v150 < v146 )
          {
            v152 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
            v153 = v152;
            if ( v152 )
            {
              *v152 = &GridWorkspaceWorker::`vftable';
              v152[4] = L"%02d:(%03dx%03d)";
              v152[2] = 0;
            }
            else
            {
              v153 = 0;
            }
            *((_QWORD *)pv[0] + v150) = v153;
            if ( !*((_QWORD *)pv[0] + v150) )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x48,
                (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\SimpleList.h",
                (const char *)0x8007000ELL,
                cchToCopy);
              SimpleList<GridWorkspaceWorker>::Clear(v151);
              goto LABEL_202;
            }
            ++v150;
          }
          v100 = 0;
          for ( j = 0; v100 < v146; j = (char *)v100 )
          {
            if ( (LPVOID)v100 >= pv[1] || v100 >= *((_QWORD *)v4 + 5) )
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
                cchToCopyl);
            }
            else
            {
              v101 = *((_QWORD *)pv[0] + v100);
              v102 = *(_QWORD *)(*((_QWORD *)v4 + 4) + 8 * v100);
              v103 = v102 == -16;
              v104 = v102 + 24;
              if ( v103 )
                v104 = 0;
              *(_QWORD *)(v101 + 8) = *(_QWORD *)v104;
              *(_QWORD *)(v101 + 16) = *(_QWORD *)(v104 + 8);
              *(_DWORD *)(v101 + 24) = *(_DWORD *)(v104 + 16);
              if ( v100 == v146 - 1 )
              {
                v105 = 13 * (__int64)pv[1];
                if ( 13 * (__int64)pv[1] == -1 )
                  wil::details::in1diag3::_FailFast_Unexpected(
                    retaddr,
                    (void *)0xF89,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    v107);
                v106 = (unsigned __int16 *)CoTaskMemAlloc(26 * (__int64)pv[1] + 2);
                v108 = v106;
                if ( v106 )
                {
                  v252 = v106;
                  *v106 = 0;
                  v106[v105] = 0;
                  if ( pv[1] )
                  {
                    for ( k = 0; k < pv[1]; ++k )
                    {
                      if ( k )
                      {
                        if ( !v105 || v105 > 0x7FFFFFFF )
                          goto LABEL_200;
                        v120 = v105;
                        v121 = v108;
                        while ( *v121 )
                        {
                          ++v121;
                          if ( !--v120 )
                          {
                            v122 = 0;
                            goto LABEL_195;
                          }
                        }
                        v122 = v105 - v120;
LABEL_195:
                        if ( !v120 )
                          goto LABEL_200;
                        v123 = L"|";
                        v124 = &v108[v122];
                        v125 = 2147483646;
                        v126 = v105 - v122;
                        if ( v105 != v122 )
                        {
                          do
                          {
                            if ( !v125 )
                              break;
                            if ( !*v123 )
                              break;
                            *v124++ = *v123++;
                            --v125;
                            --v126;
                          }
                          while ( v126 );
                        }
                        v127 = v124 - 1;
                        if ( v126 )
                          v127 = v124;
                        *v127 = 0;
                        if ( !v126 )
                        {
LABEL_200:
                          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                            &v252,
                            0);
                          v108 = v252;
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
                          cchToCopyk);
                      }
                      else
                      {
                        v110 = *((_QWORD *)pv[0] + (_QWORD)k);
                        v111 = *(_DWORD *)(v110 + 8);
                        LODWORD(v255) = *(_DWORD *)(v110 + 24);
                        v253 = *(unsigned __int16 **)(v110 + 32);
                        v256 = (WorkspaceData *)CoTaskMemAlloc(0x1Cu);
                        v112 = (unsigned __int16 *)v256;
                        if ( !v256 )
                          goto LABEL_200;
                        v113 = (unsigned int)v255;
                        v114 = v253;
                        *(_WORD *)v256 = 0;
                        v112[13] = 0;
                        LODWORD(cchToCopy) = v111;
                        v115 = StringCchPrintfW(v112, 0xDu, v114, v113);
                        if ( v115 < 0 )
                        {
                          wil::details::in1diag3::_Log_Hr(
                            retaddr,
                            (void *)0x4B,
                            (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\gridworkspaceworker.cpp",
                            (const char *)(unsigned int)v115,
                            v111);
                          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                            &v256,
                            0);
                          v112 = (unsigned __int16 *)v256;
                        }
                        if ( !v112 )
                          goto LABEL_200;
                        if ( v105 - 1 > 0x7FFFFFFE )
                          goto LABEL_240;
                        v117 = v105;
                        v118 = v108;
                        while ( *v118 )
                        {
                          ++v118;
                          if ( !--v117 )
                          {
                            v119 = 0;
                            goto LABEL_185;
                          }
                        }
                        v119 = v105 - v117;
LABEL_185:
                        if ( !v117 || StringCopyWorkerW_0(&v108[v119], v105 - v119, v116, v112, cchToCopy) < 0 )
                        {
LABEL_240:
                          wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(v108);
                          v108 = 0;
                          CoTaskMemFree(v112);
                          break;
                        }
                        CoTaskMemFree(v112);
                      }
                    }
                    v100 = (unsigned __int64)j;
                  }
                }
                if ( v145 )
                  wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(v145);
                v4 = v251;
                v145 = v108;
                v146 = v254;
              }
            }
            ++v100;
          }
          v70 = psz;
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
LABEL_202:
        SimpleList<GridWorkspaceWorker>::Clear(pv);
        v128 = StringCchPrintfW(v264, 0x100u, L"    This Key: \"%s\"\r\n", v145);
        v129 = 0;
        if ( v128 != -2147024774 )
          v129 = v128;
        if ( v129 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x382,
            (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
            (const char *)(unsigned int)v129,
            cchToCopy);
          if ( !v145 )
            goto LABEL_239;
          goto LABEL_238;
        }
        v130 = L"<none>";
        if ( *((_QWORD *)v4 + 2) )
          v130 = (const wchar_t *)*((_QWORD *)v4 + 2);
        v131 = StringCchPrintfW(v263, 0x100u, L"%s    LinkedKey: \"%s\"", v264, v130);
        v129 = 0;
        if ( v131 != -2147024774 )
          v129 = v131;
        if ( v129 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x38A,
            (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
            (const char *)(unsigned int)v129,
            cchToCopyb);
          if ( v145 )
LABEL_238:
            CoTaskMemFree(v145);
        }
        else
        {
          v132 = (__int64 *)pcchLength;
          v133 = StreamHelper_WriteString((char *)v4 + 16, v70, pcchLength, v263);
          v129 = v133;
          if ( v133 >= 0 )
          {
            if ( v145 )
              CoTaskMemFree(v145);
            pcchLength = *((_QWORD *)v4 + 5);
            if ( v132 )
            {
              v147 = *v132;
              LODWORD(v255) = 0;
              v148 = (*(__int64 (__fastcall **)(__int64 *, size_t *, __int64, struct WorkspaceData **))(v147 + 32))(
                       v132,
                       &pcchLength,
                       8,
                       &v255);
              v55 = v148;
              if ( v148 < 0 )
              {
                v144 = (unsigned int)v148;
                v143 = 17;
LABEL_236:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v143,
                  (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\DesktopIconLayoutHelpers.h",
                  (const char *)v144,
                  cchToCopyb);
                v62 = 920;
LABEL_86:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v62,
                  (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
                  (const char *)(unsigned int)v55,
                  cchToCopyb);
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x37,
                  (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
                  (const char *)(unsigned int)v55,
                  cchToCopye);
                return (unsigned int)v55;
              }
            }
            if ( v70 )
            {
              v55 = StringCchPrintfW(v263, 0x100u, L"    Workspace Count: %d");
              if ( (int)(v55 + 0x80000000) >= 0 && v55 != -2147024774 )
              {
                v143 = 47;
                goto LABEL_235;
              }
              v134 = v70;
              v135 = 64000;
              do
              {
                if ( !*v134 )
                  break;
                ++v134;
                --v135;
              }
              while ( v135 );
              v136 = -2147024809;
              v137 = -2147024809;
              v138 = 2147483646;
              if ( v135 )
                v137 = 0;
              v139 = 64000 - v135;
              if ( v135 )
              {
                v176 = v263;
                v177 = (wchar_t *)&v70[v139];
                v178 = 2147483646;
                if ( v139 != 64000 )
                {
                  do
                  {
                    if ( !v178 )
                      break;
                    if ( !*v176 )
                      break;
                    *v177++ = *v176++;
                    --v178;
                    --v135;
                  }
                  while ( v135 );
                }
                v179 = v177 - 1;
                v136 = -2147024809;
                if ( v135 )
                  v179 = v177;
                *v179 = 0;
                v137 = -2147024774;
                if ( v135 )
                  v137 = 0;
              }
              v55 = 0;
              if ( v137 != -2147024774 )
                v55 = v137;
              if ( v55 < 0 )
              {
                v143 = 49;
                goto LABEL_235;
              }
              v140 = 64000;
              v141 = v70;
              do
              {
                if ( !*v141 )
                  break;
                ++v141;
                --v140;
              }
              while ( v140 );
              if ( v140 )
                v136 = 0;
              v142 = 64000 - v140;
              if ( v140 )
              {
                v169 = L"\r\n";
                v170 = (wchar_t *)&v70[v142];
                v171 = 2147483646;
                v172 = 64000 - v142;
                if ( v142 != 64000 )
                {
                  do
                  {
                    if ( !v171 )
                      break;
                    if ( !*v169 )
                      break;
                    *v170++ = *v169++;
                    --v171;
                    --v172;
                  }
                  while ( v172 );
                }
                v173 = v170 - 1;
                v136 = -2147024774;
                if ( v172 )
                {
                  v173 = v170;
                  v136 = 0;
                }
                *v173 = 0;
              }
              v55 = 0;
              if ( v136 != -2147024774 )
                v55 = v136;
              if ( v55 < 0 )
              {
                v143 = 50;
LABEL_235:
                v144 = (unsigned int)v55;
                goto LABEL_236;
              }
            }
            else
            {
              v138 = 2147483646;
            }
            for ( m = 0; m < *((_QWORD *)v4 + 5); ++m )
            {
              v175 = *(_QWORD *)(*((_QWORD *)v4 + 4) + 8 * m);
              *(_QWORD *)(v175 + 8) = *((_QWORD *)v4 + 1);
              v55 = (**(__int64 (__fastcall ***)(__int64, __int64 *, const wchar_t *))v175)(v175, v132, v70);
              if ( v55 < 0 )
              {
                v62 = 928;
                goto LABEL_86;
              }
            }
            IsLinked = DesktopData::IsLinked(v4);
            v59 = 0;
            if ( IsLinked )
            {
              for ( n = 0; n < *((_QWORD *)v4 + 5); ++n )
              {
                LODWORD(j) = *(_DWORD *)(*((_QWORD *)v4 + 8) + 4 * n);
                if ( v132 )
                {
                  v91 = *v132;
                  LODWORD(v255) = v59;
                  v92 = (*(__int64 (__fastcall **)(__int64 *, char **, __int64, struct WorkspaceData **))(v91 + 32))(
                          v132,
                          &j,
                          4,
                          &v255);
                  v55 = v92;
                  if ( v92 < 0 )
                  {
                    v61 = (unsigned int)v92;
                    v60 = 17;
                    goto LABEL_85;
                  }
                  v59 = 0;
                }
                if ( v70 )
                {
                  v55 = StringCchPrintfW(v263, 0x100u, L"    Source Link Index: %d");
                  if ( (int)(v55 + 0x80000000) >= 0 && v55 != -2147024774 )
                  {
                    v60 = 47;
LABEL_84:
                    v61 = (unsigned int)v55;
LABEL_85:
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)v60,
                      (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\DesktopIconLayoutHelpers.h",
                      (const char *)v61,
                      cchToCopyb);
                    v62 = 934;
                    goto LABEL_86;
                  }
                  pcchLength = 0;
                  v56 = StringLengthWorkerW_1(v70, 0xFA00u, &pcchLength);
                  if ( v56 >= 0 )
                  {
                    v95 = v263;
                    v96 = 2147483646;
                    v97 = (wchar_t *)&v70[pcchLength];
                    v98 = 64000 - pcchLength;
                    if ( pcchLength != 64000 )
                    {
                      do
                      {
                        if ( !v96 )
                          break;
                        if ( !*v95 )
                          break;
                        *v97++ = *v95++;
                        --v96;
                        --v98;
                      }
                      while ( v98 );
                    }
                    v99 = v97 - 1;
                    if ( v98 )
                      v99 = v97;
                    v56 = -2147024774;
                    if ( v98 )
                      v56 = v57;
                    *v99 = v57;
                  }
                  v55 = v57;
                  if ( v56 != -2147024774 )
                    v55 = v56;
                  if ( v55 < 0 )
                  {
                    v60 = 49;
                    goto LABEL_84;
                  }
                  pcchLength = v57;
                  v58 = StringLengthWorkerW_1(v70, 0xFA00u, &pcchLength);
                  if ( v58 >= 0 )
                  {
                    v83 = L"\r\n";
                    v84 = 2147483646;
                    v85 = (wchar_t *)&v70[pcchLength];
                    v86 = 64000 - pcchLength;
                    if ( pcchLength != 64000 )
                    {
                      do
                      {
                        if ( !v84 )
                          break;
                        if ( !*v83 )
                          break;
                        *v85++ = *v83++;
                        --v84;
                        --v86;
                      }
                      while ( v86 );
                    }
                    v87 = v85 - 1;
                    if ( v86 )
                      v87 = v85;
                    v58 = -2147024774;
                    if ( v86 )
                      v58 = v59;
                    *v87 = v59;
                  }
                  v55 = v59;
                  if ( v58 != -2147024774 )
                    v55 = v58;
                  if ( v55 < 0 )
                  {
                    v60 = 50;
                    goto LABEL_84;
                  }
                }
              }
            }
            v262 = v59;
            *(_OWORD *)pv = 0;
            v261 = 0;
            DataForTracelog = DesktopData::GetDataForTracelog(v4, (struct DesktopDataForTracelog *)pv);
            v158 = DataForTracelog;
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
                (const char *)v158,
                cchToCopym);
            }
            else
            {
              if ( DesktopIconLayoutTelemetry::IsEnabled(v157, v156) )
              {
                wil::details::static_lazy<DesktopIconLayoutTelemetry>::get(
                  v159,
                  _lambda_94155d05b4417a0d99e43922e5476814_::_lambda_invoker_cdecl_);
                DesktopIconLayoutTelemetry::LogPersistedDesktop_(v160, (const struct DesktopDataForTracelog *)pv);
              }
              DesktopDataForTracelog::~DesktopDataForTracelog((DesktopDataForTracelog *)pv);
            }
            if ( !v70 )
              return 0;
            pcchLength = 0;
            v180 = StringLengthWorkerW_1(v70, 0xFA00u, &pcchLength);
            if ( v180 >= 0 )
            {
              v182 = L"  Desktop Serialize End\r\n";
              v183 = (wchar_t *)&v70[pcchLength];
              v184 = 64000 - pcchLength;
              if ( 64000 != pcchLength )
              {
                do
                {
                  if ( !v138 )
                    break;
                  if ( !*v182 )
                    break;
                  *v183++ = *v182++;
                  --v138;
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
          if ( v145 )
            goto LABEL_238;
        }
LABEL_239:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x36,
          (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
          (const char *)(unsigned int)v129,
          cchToCopyd);
        return (unsigned int)v129;
      }
    }
    LODWORD(j) = 65538;
    if ( v69 )
    {
      v93 = *v69;
      LODWORD(v255) = 0;
      v94 = (*(__int64 (__fastcall **)(__int64 *, char **, __int64, struct WorkspaceData **))(v93 + 32))(
              v69,
              &j,
              4,
              &v255);
      ShouldSerialize = v94;
      if ( v94 < 0 )
      {
        v81 = (unsigned int)v94;
        v80 = 17;
        goto LABEL_127;
      }
    }
    if ( !v70 )
      goto LABEL_255;
    goto LABEL_106;
  }
  if ( psz )
  {
    v230 = psz;
    v231 = 64000;
    do
    {
      if ( !*v230 )
        break;
      ++v230;
      --v231;
    }
    while ( v231 );
    v207 = -2147024809;
    if ( v231 )
      v207 = 0;
    v208 = 64000 - v231;
    if ( v231 )
    {
      v210 = L"    Has Holes, compressed key =";
      v211 = (wchar_t *)&psz[v208];
      v212 = 2147483646;
      if ( v208 != 64000 )
      {
        do
        {
          if ( !v212 )
            break;
          if ( !*v210 )
            break;
          *v211++ = *v210++;
          --v212;
          --v231;
        }
        while ( v231 );
      }
      v213 = v211 - 1;
      if ( v231 )
        v213 = v211;
      *v213 = 0;
      v207 = -2147024774;
      if ( v231 )
        v207 = 0;
    }
    v209 = 0;
    if ( v207 != -2147024774 )
      v209 = v207;
    if ( v209 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B,
        (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
        (const char *)(unsigned int)v209,
        cchToCopy);
      return (unsigned int)v209;
    }
  }
  v12 = 20 * v5;
  if ( !is_mul_ok(v5, 0x14u) )
    v12 = -1;
  v13 = (char *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
  j = v13;
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
  v256 = 0;
  WorkspaceUtilizationInfo = DesktopData::GetWorkspaceUtilizationInfo(v4, 0, 0, (unsigned __int64 *)&v256, 0, v248);
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
  if ( v256 != (WorkspaceData *)v5 )
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
  for ( ii = 0; ii < *((_QWORD *)v4 + 5); ++ii )
  {
    v256 = 0;
    v20 = DesktopData::GetWorkspace(v4, ii, &v256);
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
    if ( !WorkspaceData::IsIgnorable(v256) )
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
  v260 = 0;
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
    goto LABEL_138;
  }
  memset_0(v24, 0, 8 * v5);
  v25 = *(_QWORD *)_lambda_fe4c477b74a134c39e12a17cfd840b96_::_lambda_fe4c477b74a134c39e12a17cfd840b96_(&v254, pv);
  pv[1] = (LPVOID)v5;
  v260 = v5;
  while ( v17 < v5 )
  {
    v27 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    v28 = v27;
    if ( v27 )
    {
      *v27 = &GridWorkspaceWorker::`vftable';
      v27[4] = L"%02d:(%03dx%03d)";
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
LABEL_138:
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
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25,
        (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
        (const char *)0x80070057LL,
        cchToCopyj);
      SimpleList<GridWorkspaceWorker>::Clear(pv);
      CZeroInitNew::operator delete(v14);
      return 2147942487LL;
    }
    v89 = *((_QWORD *)pv[0] + v29);
    v90 = &v14[20 * v29++];
    *(_QWORD *)(v89 + 8) = *(_QWORD *)v90;
    *(_QWORD *)(v89 + 16) = *((_QWORD *)v90 + 1);
    *(_DWORD *)(v89 + 24) = *((_DWORD *)v90 + 4);
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
  if ( !v31 || (v256 = v31, *(_WORD *)v31 = 0, *((_WORD *)v31 + v30) = 0, (v33 = pv[1]) == 0) )
  {
LABEL_92:
    if ( !v32 )
      goto LABEL_141;
    v63 = psz;
    if ( psz )
    {
      v232 = psz;
      v233 = 64000;
      do
      {
        if ( !*v232 )
          break;
        ++v232;
        --v233;
      }
      while ( v233 );
      v186 = -2147024809;
      if ( v233 )
        v186 = 0;
      v187 = 64000 - v233;
      if ( v233 )
      {
        v192 = (wchar_t *)&psz[v187];
        v193 = 2147483646;
        v194 = (wchar_t *)v32;
        if ( v187 != 64000 )
        {
          do
          {
            if ( !v193 )
              break;
            if ( !*v194 )
              break;
            *v192++ = *v194++;
            --v193;
            --v233;
          }
          while ( v233 );
        }
        v195 = v192 - 1;
        if ( v233 )
          v195 = v192;
        *v195 = 0;
        v186 = -2147024774;
        if ( v233 )
          v186 = 0;
      }
      v88 = 0;
      if ( v186 != -2147024774 )
        v88 = v186;
      if ( v88 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x30,
          (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
          (const char *)(unsigned int)v88,
          cchToCopy);
        CoTaskMemFree(v32);
        goto LABEL_142;
      }
      v188 = 64000;
      v189 = v63;
      do
      {
        if ( !*v189 )
          break;
        ++v189;
        --v188;
      }
      while ( v188 );
      v190 = -2147024809;
      if ( v188 )
        v190 = 0;
      v191 = 64000 - v188;
      if ( v188 )
      {
        v196 = L"\r\n";
        v197 = (wchar_t *)&v63[v191];
        v198 = 2147483646;
        if ( v191 != 64000 )
        {
          do
          {
            if ( !v198 )
              break;
            if ( !*v196 )
              break;
            *v197++ = *v196++;
            --v198;
            --v188;
          }
          while ( v188 );
        }
        v199 = v197 - 1;
        if ( v188 )
          v199 = v197;
        *v199 = 0;
        v190 = -2147024774;
        if ( v188 )
          v190 = 0;
      }
      v88 = 0;
      if ( v190 != -2147024774 )
        v88 = v190;
      if ( v88 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32,
          (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
          (const char *)(unsigned int)v88,
          cchToCopy);
        CoTaskMemFree(v32);
        goto LABEL_142;
      }
    }
    CoTaskMemFree(v32);
    v64 = pv[0];
    if ( pv[0] )
    {
      v65 = v260;
      v66 = 0;
      if ( v260 )
      {
        do
        {
          v67 = (_QWORD *)v64[v66];
          if ( v67 )
          {
            *v67 = &GridWorkspaceWorker::`vftable';
            operator delete(v67, (const struct std::nothrow_t *)0x28);
            v65 = v260;
            v64 = pv[0];
          }
          ++v66;
        }
        while ( v66 < v65 );
        v4 = v251;
      }
      CoTaskMemFree(v64);
      pv[0] = 0;
      pv[1] = 0;
      v260 = 0;
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v14);
    goto LABEL_102;
  }
  for ( jj = 0; ; ++jj )
  {
    if ( jj >= (unsigned __int64)v33 )
      goto LABEL_91;
    if ( jj )
    {
      if ( !v30 || v30 > 0x7FFFFFFF )
        goto LABEL_90;
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
        goto LABEL_90;
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
LABEL_90:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v256,
          0);
        v32 = v256;
LABEL_91:
        v4 = v251;
        v14 = j;
        goto LABEL_92;
      }
      v33 = pv[1];
    }
    if ( jj < (unsigned __int64)v33 )
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
  v35 = *((_QWORD *)pv[0] + jj);
  v36 = *(_DWORD *)(v35 + 8);
  v37 = *(_DWORD *)(v35 + 24);
  v252 = *(unsigned __int16 **)(v35 + 32);
  v255 = (struct WorkspaceData *)CoTaskMemAlloc(0x1Cu);
  v38 = (unsigned __int16 *)v255;
  if ( !v255 )
    goto LABEL_90;
  v39 = v252;
  *(_WORD *)v255 = 0;
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
      &v255,
      0);
    v38 = (unsigned __int16 *)v255;
  }
  if ( !v38 )
    goto LABEL_90;
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
  v14 = j;
LABEL_141:
  v88 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2B,
    (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\desktopdata.cpp",
    (const char *)0x80070057LL,
    cchToCopy);
LABEL_142:
  SimpleList<GridWorkspaceWorker>::Clear(pv);
  CZeroInitNew::operator delete(v14);
  return (unsigned int)v88;
}

```

## disassembly

```asm
0x180038690  push    rbp
0x180038692  push    rbx
0x180038693  push    r12
0x180038695  push    r13
0x180038697  push    r14
0x180038699  lea     rbp, [rsp-3D0h]
0x1800386a1  sub     rsp, 4D0h
0x1800386a8  mov     rax, cs:__security_cookie
0x1800386af  xor     rax, rsp
0x1800386b2  mov     [rbp+3F0h+var_40], rax
0x1800386b9  mov     [rsp+4F0h+psz], r8
0x1800386be  mov     r10, r8
0x1800386c1  mov     [rsp+4F0h+pcchLength], rdx
0x1800386c6  mov     r13, rcx
0x1800386c9  mov     [rsp+4F0h+var_4B0], rcx
0x1800386ce  mov     r11d, 0FA00h
0x1800386d4  mov     r14d, 80070057h
0x1800386da  mov     r12d, 7FFFFFFEh
0x1800386e0  test    r8, r8
0x1800386e3  jnz     loc_180039F23
0x1800386e9  mov     [rsp+4F0h+arg_18], rsi
0x1800386f1  xor     esi, esi
0x1800386f3  mov     [rsp+4F0h+var_28], rdi
0x1800386fb  xor     dil, dil
0x1800386fe  mov     [rsp+4F0h+var_30], r15
0x180038706  xor     r15b, r15b
0x180038709  xor     ebx, ebx
0x18003870b  cmp     rbx, [r13+28h]
0x18003870f  jnb     short loc_180038772
0x180038711  mov     rax, [r13+20h]
0x180038715  lea     r8, [rsp+4F0h+var_490]; struct WorkspaceData **
0x18003871a  mov     [rsp+4F0h+var_490], 0
0x180038723  mov     rdx, rbx; unsigned __int64
0x180038726  mov     rcx, [rax+rbx*8]
0x18003872a  mov     [rsp+4F0h+var_490], rcx
0x18003872f  mov     rcx, r13; this
0x180038732  call    ?GetWorkspace@DesktopData@@QEBAJ_KPEAPEAVWorkspaceData@@@Z; DesktopData::GetWorkspace(unsigned __int64,WorkspaceData * *)
0x180038737  mov     r14d, eax
0x18003873a  test    eax, eax
0x18003873c  js      loc_18003908B
0x180038742  mov     rax, [rsp+4F0h+var_490]
0x180038747  cmp     qword ptr [rax+48h], 0
0x18003874c  jnz     short loc_18003875B
0x18003874e  test    byte ptr [rax+28h], 1
0x180038752  jz      loc_180038878
0x180038758  mov     dil, 1
0x18003875b  inc     rsi
0x18003875e  movzx   edi, dil
0x180038762  test    r15b, r15b
0x180038765  mov     eax, 1
0x18003876a  cmovnz  edi, eax
0x18003876d  jmp     loc_18003887B
0x180038772  test    dil, dil
0x180038775  jz      loc_18003913E
0x18003877b  mov     r10, [rsp+4F0h+psz]
0x180038780  test    r10, r10
0x180038783  jnz     loc_180039F71
0x180038789  mov     r14d, 80070057h
0x18003878f  mov     eax, 14h
0x180038794  mul     rsi
0x180038797  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003879e  mov     rbx, rax
0x1800387a1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800387a8  cmovb   rbx, rax
0x1800387ac  mov     rcx, rbx; unsigned __int64
0x1800387af  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800387b4  mov     [rsp+4F0h+var_480], rax
0x1800387b9  mov     r15, rax
0x1800387bc  test    rax, rax
0x1800387bf  jz      loc_180038CC3
0x1800387c5  mov     r8, rbx; Size
0x1800387c8  xor     edx, edx; Val
0x1800387ca  mov     rcx, rax; void *
0x1800387cd  call    memset_0
0x1800387d2  xor     eax, eax
0x1800387d4  lea     r9, [rsp+4F0h+var_488]; unsigned __int64 *
0x1800387d9  xor     r8d, r8d; bool *
0x1800387dc  mov     [rsp+4F0h+var_488], rax
0x1800387e1  xor     edx, edx; bool *
0x1800387e3  mov     [rsp+4F0h+cchToCopy], rax; int
0x1800387e8  mov     rcx, r13; this
0x1800387eb  call    ?GetWorkspaceUtilizationInfo@DesktopData@@QEBAJPEA_N0PEA_K00@Z; DesktopData::GetWorkspaceUtilizationInfo(bool *,bool *,unsigned __int64 *,bool *,bool *)
0x1800387f0  mov     edi, eax
0x1800387f2  test    eax, eax
0x1800387f4  js      loc_180038F78
0x1800387fa  cmp     [rsp+4F0h+var_488], rsi
0x1800387ff  jnz     loc_180038B02
0x180038805  xor     edi, edi
0x180038807  mov     r14d, edi
0x18003880a  mov     ebx, edi
0x18003880c  nop     dword ptr [rax+00h]
0x180038810  cmp     rbx, [r13+28h]
0x180038814  jnb     short loc_180038883
0x180038816  lea     r8, [rsp+4F0h+var_488]; struct WorkspaceData **
0x18003881b  mov     [rsp+4F0h+var_488], rdi
0x180038820  mov     rdx, rbx; unsigned __int64
0x180038823  mov     rcx, r13; this
0x180038826  call    ?GetWorkspace@DesktopData@@QEBAJ_KPEAPEAVWorkspaceData@@@Z; DesktopData::GetWorkspace(unsigned __int64,WorkspaceData * *)
0x18003882b  mov     edi, eax
0x18003882d  test    eax, eax
0x18003882f  js      loc_180038C99
0x180038835  mov     rdx, [rsp+4F0h+var_488]
0x18003883a  mov     rcx, rdx; this
0x18003883d  call    ?IsIgnorable@WorkspaceData@@QEBA_NXZ; WorkspaceData::IsIgnorable(void)
0x180038842  test    al, al
0x180038844  jnz     short loc_180038871
0x180038846  cmp     r14, rsi
0x180038849  jnb     loc_180039FC5
0x18003884f  lea     rax, [r14+r14*4]
0x180038853  inc     r14
0x180038856  lea     rcx, [r15+rax*4]
0x18003885a  mov     rax, [rdx+18h]
0x18003885e  mov     [rcx], rax
0x180038861  movsd   xmm0, qword ptr [rdx+20h]
0x180038866  movsd   qword ptr [rcx+8], xmm0
0x18003886b  mov     eax, [rdx+28h]
0x18003886e  mov     [rcx+10h], eax
0x180038871  inc     rbx
0x180038874  xor     edi, edi
0x180038876  jmp     short loc_180038810
0x180038878  mov     r15b, 1
0x18003887b  inc     rbx
0x18003887e  jmp     loc_18003870B
0x180038883  lea     rbx, ds:0[rsi*8]
0x18003888b  mov     [rbp+3F0h+pv], rdi
0x18003888f  mov     rcx, rbx; cb
0x180038892  mov     [rbp+3F0h+pv+8], rdi
0x180038896  mov     [rbp+3F0h+var_460], rdi
0x18003889a  call    cs:__imp_CoTaskMemAlloc
0x1800388a1  nop     dword ptr [rax+rax+00h]
0x1800388a6  mov     [rbp+3F0h+pv], rax
0x1800388aa  test    rax, rax
0x1800388ad  jz      loc_180039FEA
0x1800388b3  mov     r8, rbx; Size
0x1800388b6  xor     edx, edx; Val
0x1800388b8  mov     rcx, rax; void *
0x1800388bb  call    memset_0
0x1800388c0  lea     rdx, [rbp+3F0h+pv]
0x1800388c4  lea     rcx, [rsp+4F0h+var_498]
0x1800388c9  call    ??0_lambda_fe4c477b74a134c39e12a17cfd840b96_@@QEAA@PEAV?$SimpleList@VIconGridItemWorker@@@@@Z; _lambda_fe4c477b74a134c39e12a17cfd840b96_::_lambda_fe4c477b74a134c39e12a17cfd840b96_(SimpleList<IconGridItemWorker> *)
0x1800388ce  lea     r14, ??_7GridWorkspaceWorker@@6B@; const GridWorkspaceWorker::`vftable'
0x1800388d5  mov     rbx, [rax]
0x1800388d8  mov     [rbp+3F0h+pv+8], rsi
0x1800388dc  mov     [rbp+3F0h+var_460], rsi
0x1800388e0  cmp     rdi, rsi
0x1800388e3  jnb     short loc_180038932
0x1800388e5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800388ec  mov     ecx, 28h ; '('; unsigned __int64
0x1800388f1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800388f6  mov     rcx, rax
0x1800388f9  test    rax, rax
0x1800388fc  jz      loc_180038F71
0x180038902  mov     [rax], r14
0x180038905  lea     rax, a02d03dx03d; "%02d:(%03dx%03d)"
0x18003890c  mov     [rcx+20h], rax
0x180038910  xor     eax, eax
0x180038912  mov     [rcx+10h], rax
0x180038916  mov     rax, [rbp+3F0h+pv]
0x18003891a  mov     [rax+rdi*8], rcx
0x18003891e  mov     rax, [rbp+3F0h+pv]
0x180038922  cmp     qword ptr [rax+rdi*8], 0
0x180038927  jz      loc_180038F98
0x18003892d  inc     rdi
0x180038930  jmp     short loc_1800388E0
0x180038932  xor     r8d, r8d
0x180038935  cmp     r8, rsi
0x180038938  jb      loc_1800390C9
0x18003893e  imul    r14, [rbp+3F0h+pv+8], 0Dh
0x180038943  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180038947  jz      loc_18003A00D
0x18003894d  lea     rcx, ds:2[r14*2]; cb
0x180038955  call    cs:__imp_CoTaskMemAlloc
0x18003895c  nop     dword ptr [rax+rax+00h]
0x180038961  mov     rdi, rax
0x180038964  test    rax, rax
0x180038967  jz      loc_180038D06
0x18003896d  xor     eax, eax
0x18003896f  mov     [rsp+4F0h+var_488], rdi
0x180038974  mov     [rdi], ax
0x180038977  mov     [rdi+r14*2], ax
0x18003897c  mov     rax, [rbp+3F0h+pv+8]
0x180038980  test    rax, rax
0x180038983  jz      loc_180038D06
0x180038989  xor     esi, esi
0x18003898b  cmp     rsi, rax
0x18003898e  jnb     loc_180038CFC
0x180038994  test    rsi, rsi
0x180038997  jnz     loc_180038A8B
0x18003899d  cmp     rsi, rax
0x1800389a0  jnb     loc_180038FF7
0x1800389a6  mov     rax, [rbp+3F0h+pv]
0x1800389aa  mov     rcx, [rax+rsi*8]
0x1800389ae  mov     rax, [rcx+20h]
0x1800389b2  mov     r15d, [rcx+8]
0x1800389b6  mov     r12d, [rcx+0Ch]
0x1800389ba  mov     r13d, [rcx+18h]
0x1800389be  mov     ecx, 1Ch; cb
0x1800389c3  mov     [rsp+4F0h+var_4A8], rax
0x1800389c8  call    cs:__imp_CoTaskMemAlloc
0x1800389cf  nop     dword ptr [rax+rax+00h]
0x1800389d4  mov     [rsp+4F0h+var_490], rax
0x1800389d9  mov     rbx, rax
0x1800389dc  test    rax, rax
0x1800389df  jz      loc_18003A06B
0x1800389e5  mov     r8, [rsp+4F0h+var_4A8]; unsigned __int16 *
0x1800389ea  xor     eax, eax
0x1800389ec  mov     [rbx], ax
0x1800389ef  mov     r9d, r13d
0x1800389f2  mov     dword ptr [rsp+4F0h+var_4C8], r12d
0x1800389f7  mov     edx, 0Dh; unsigned __int64
0x1800389fc  mov     rcx, rbx; unsigned __int16 *
0x1800389ff  mov     [rbx+1Ah], ax
0x180038a03  mov     dword ptr [rsp+4F0h+cchToCopy], r15d; int
0x180038a08  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180038a0d  test    eax, eax
0x180038a0f  js      loc_180038F03
0x180038a15  mov     r12d, 7FFFFFFEh
0x180038a1b  test    rbx, rbx
0x180038a1e  jz      loc_180038CEB
0x180038a24  lea     rax, [r14-1]
0x180038a28  cmp     rax, r12
0x180038a2b  ja      loc_180039037
0x180038a31  mov     rcx, r14
0x180038a34  mov     rax, rdi
0x180038a37  cmp     word ptr [rax], 0
0x180038a3b  jz      loc_18003A060
0x180038a41  add     rax, 2
0x180038a45  sub     rcx, 1
0x180038a49  jnz     short loc_180038A37
0x180038a4b  xor     eax, eax
0x180038a4d  test    rcx, rcx
0x180038a50  jz      loc_180039037
0x180038a56  mov     rdx, r14
0x180038a59  lea     rcx, [rdi+rax*2]; pszDest
0x180038a5d  sub     rdx, rax; cchDest
0x180038a60  mov     r9, rbx; pszSrc
0x180038a63  call    StringCopyWorkerW_0
0x180038a68  test    eax, eax
0x180038a6a  js      loc_180039037
0x180038a70  mov     rcx, rbx; pv
0x180038a73  call    cs:__imp_CoTaskMemFree
0x180038a7a  nop     dword ptr [rax+rax+00h]
0x180038a7f  mov     rax, [rbp+3F0h+pv+8]
0x180038a83  inc     rsi
0x180038a86  jmp     loc_18003898B
0x180038a8b  test    r14, r14
0x180038a8e  jz      loc_180038CEB
0x180038a94  cmp     r14, 7FFFFFFFh
0x180038a9b  ja      loc_180038CEB
0x180038aa1  mov     rax, r14
0x180038aa4  mov     rcx, rdi
0x180038aa7  cmp     word ptr [rcx], 0
0x180038aab  jz      loc_18003A026
0x180038ab1  add     rcx, 2
0x180038ab5  sub     rax, 1
0x180038ab9  jnz     short loc_180038AA7
0x180038abb  xor     ecx, ecx
0x180038abd  test    rax, rax
0x180038ac0  jz      loc_180038CEB
0x180038ac6  mov     rdx, r14
0x180038ac9  lea     r9, asc_1806150CC; "|"
0x180038ad0  lea     rax, [rdi+rcx*2]
0x180038ad4  mov     r8, r12
0x180038ad7  sub     rdx, rcx
0x180038ada  jnz     loc_18003A031
0x180038ae0  test    rdx, rdx
0x180038ae3  lea     rcx, [rax-2]
0x180038ae7  cmovnz  rcx, rax
0x180038aeb  xor     eax, eax
0x180038aed  mov     [rcx], ax
0x180038af0  test    rdx, rdx
0x180038af3  jz      loc_180038CEB
0x180038af9  mov     rax, [rbp+3F0h+pv+8]
0x180038afd  jmp     loc_18003899D
0x180038b02  mov     rcx, [rbp+3F8h]; this
0x180038b09  lea     r8, aShellShell32Ic_11; "shell\\shell32\\iconlayoutengine\\datam"...
0x180038b10  mov     r9d, r14d; char *
0x180038b13  mov     edx, 2F6h; void *
0x180038b18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038b1d  mov     edi, r14d
0x180038b20  mov     rcx, [rbp+3F8h]; this
0x180038b27  lea     r8, aShellShell32Ic_11; "shell\\shell32\\iconlayoutengine\\datam"...
0x180038b2e  mov     r9d, edi; char *
0x180038b31  mov     edx, 1Fh; void *
0x180038b36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038b3b  mov     rcx, r15; lpMem
0x180038b3e  call    ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
0x180038b43  mov     eax, edi
0x180038b45  jmp     loc_180038C61
0x180038b4a  mov     rdi, r11
0x180038b4d  nop     dword ptr [rax]
0x180038b50  cmp     rdi, [r13+28h]
0x180038b54  jnb     loc_18003995D
0x180038b5a  mov     rax, [r13+40h]
0x180038b5e  mov     r9d, [rax+rdi*4]
0x180038b62  mov     dword ptr [rsp+4F0h+var_480], r9d
0x180038b67  test    r12, r12
0x180038b6a  jnz     loc_180039102
0x180038b70  test    r15, r15
0x180038b73  jz      loc_18003919A
  ... truncated ...
```
