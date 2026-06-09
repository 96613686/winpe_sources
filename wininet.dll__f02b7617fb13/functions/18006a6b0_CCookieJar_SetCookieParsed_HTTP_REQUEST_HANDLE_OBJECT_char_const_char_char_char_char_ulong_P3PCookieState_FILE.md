# CCookieJar::SetCookieParsed(HTTP_REQUEST_HANDLE_OBJECT *,char const *,char *,char *,char *,char *,ulong &,P3PCookieState *,_FILETIME,ulong *,int,int,_LIST_ENTRY *)

- ea: `0x18006a6b0`
- end: `0x18006c0c8`
- name: `?SetCookieParsed@CCookieJar@@SAKPEAVHTTP_REQUEST_HANDLE_OBJECT@@PEBDPEAD222AEAKPEAUP3PCookieState@@U_FILETIME@@PEAKHHPEAU_LIST_ENTRY@@@Z`
- size: `6680`
- prototype: `static unsigned int(struct HTTP_REQUEST_HANDLE_OBJECT *, const char *, char *, char *, char *, char *, unsigned int *, struct P3PCookieState *, struct _FILETIME, unsigned int *, int, int, struct _LIST_ENTRY *)`
- caller_count: `3`
- callee_count: `40`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800697d0`
- `0x18006c5b0`
- `0x1800c6418`

## callees

- `0x18000660c`
- `0x180009cf0`
- `0x180011930`
- `0x180018d2c`
- `0x18006a6b0`
- `0x18006c0d0`
- `0x18006c4b0`
- `0x18006dd10`
- `0x1800701d0`
- `0x180095350`
- `0x1800955f0`
- `0x180096edc`
- `0x180096ef0`
- `0x18009726c`
- `0x1800e0780`
- `0x1800e08a0`
- `0x1800f5c60`
- `0x1800f6500`
- `0x1800fa3ac`
- `0x1800fa4d4`
- `0x1800fafcc`
- `0x1800fb0f8`
- `0x180108864`
- `0x18013a158`
- `0x18014a3a4`
- `0x18014a7a0`
- `0x1801538e4`
- `0x18017fb54`
- `0x180180214`
- `0x1801c9c31`
- `0x1801d6198`
- `0x1801d6234`
- `0x1801d62f0`
- `0x1801d6670`
- `0x1801d675c`
- `0x1801e0700`
- `0x1801e1790`
- `0x1801e3714`
- `0x1801e3c78`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006c05f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006c07e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006c05f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006c07e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b60a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b68e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b6e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b7b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006be9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b60a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b68e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b6e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b7b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006be9c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b3ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b3ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006a87c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006a87c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18006adf9`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18006adf9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006b065`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006b065`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b0c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b30e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b34a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b3d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006beee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006bf06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006bf7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006bff0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006c030`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006c045`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b0c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b30e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b34a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b3d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006beee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006bf06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006bf7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006bff0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006c030`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006c045`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006a98c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006a98c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006aff8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006b032`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006b095`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006aff8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006b032`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006b095`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18006b835`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18006b835`

## pseudocode

```c
__int64 __fastcall CCookieJar::SetCookieParsed(
        struct HTTP_REQUEST_HANDLE_OBJECT *a1,
        char *a2,
        char *a3,
        char *a4,
        char *a5,
        char *a6,
        unsigned int *a7,
        struct P3PCookieState *a8,
        __int64 Buf1,
        unsigned int *a10,
        int a11,
        int a12,
        struct _LIST_ENTRY *a13)
{
  char *v13; // r14
  char *v15; // r13
  unsigned int *v16; // rcx
  int v17; // edi
  __int64 v18; // rbx
  int v19; // esi
  unsigned int v20; // r12d
  LPCSTR v21; // r8
  CHAR v22; // cl
  char *v23; // rax
  CHAR *v24; // rax
  CHAR i; // cl
  char v26; // cl
  char *v27; // rax
  CHAR v28; // cl
  CHAR *v29; // rax
  unsigned int v30; // eax
  char v31; // al
  char *v32; // rcx
  int v33; // edi
  BOOL v34; // r8d
  unsigned int v35; // eax
  int v36; // ecx
  int v37; // eax
  int v38; // edx
  int v39; // r12d
  int v40; // eax
  int v41; // r15d
  int v42; // eax
  int v43; // edx
  unsigned int *v44; // rdi
  int v45; // eax
  unsigned __int16 v46; // ax
  __int16 v47; // r9
  __int16 v48; // r10
  __int16 v49; // r11
  unsigned __int16 v50; // ax
  __int16 v51; // r9
  __int16 v52; // r10
  __int16 v53; // r11
  WCHAR *v54; // rsi
  __int64 v55; // rdx
  __int64 v56; // rcx
  int LastError; // eax
  signed int HostInternal; // edi
  unsigned __int16 *v59; // r12
  _BYTE *v60; // r9
  __int64 v61; // rdx
  __int64 v62; // r8
  __int64 v63; // rcx
  _BYTE *v64; // rax
  unsigned __int64 v65; // r10
  WCHAR *v66; // r13
  CHAR v67; // cl
  unsigned int v68; // edx
  CHAR *v69; // r8
  CHAR *v70; // r8
  CHAR *j; // r9
  CHAR v72; // cl
  __int64 k; // r9
  CHAR *v74; // r8
  CHAR *m; // r9
  CHAR v76; // cl
  __int64 v77; // rcx
  __int64 v78; // r15
  __int64 v79; // rcx
  __int64 v80; // rcx
  unsigned __int64 v81; // rcx
  unsigned int v82; // r14d
  WCHAR *lpWideCharStr; // rax
  int v84; // eax
  unsigned __int16 *v85; // rax
  __int64 v86; // rcx
  unsigned int v87; // esi
  __int64 v88; // r8
  unsigned int v89; // edi
  unsigned int v90; // r9d
  unsigned int v91; // r10d
  unsigned int v92; // r11d
  unsigned int v93; // r14d
  __int64 v94; // rdx
  unsigned __int64 v96; // rax
  unsigned int v97; // esi
  void *v98; // r8
  int v99; // edx
  int v100; // ecx
  int v101; // r8d
  int v102; // r12d
  struct CCookieHost *v103; // rsi
  int v104; // edi
  char *v105; // r14
  int v106; // edi
  __int64 v107; // r10
  __int64 v108; // r9
  struct CCookieLocation **v109; // rsi
  char *v110; // rax
  signed __int64 v111; // r8
  int v112; // ecx
  int v113; // edx
  const CHAR *v114; // rax
  const CHAR *v115; // r8
  int v116; // ecx
  int v117; // edx
  struct CCookieLocation *v118; // rcx
  unsigned int *v119; // rsi
  const char *v120; // rdi
  struct CCookie *Cookie; // rax
  int v122; // eax
  struct CCookie *v123; // rax
  struct CCookie *v124; // rbx
  int v125; // eax
  __int64 v126; // rdx
  struct _LIST_ENTRY *v127; // rcx
  CCookieLocation *v128; // r15
  BOOL v129; // r12d
  LPCCH *v130; // r13
  CHAR *v131; // rsi
  int v132; // r14d
  LPCCH *v133; // rdi
  LPCCH v134; // r9
  const CHAR *v135; // rax
  const CHAR *v136; // r8
  int v137; // ecx
  int v138; // edx
  int v139; // edx
  unsigned int *v140; // r13
  CCookieLocation *v141; // rsi
  char *v142; // r12
  _QWORD *v143; // rdi
  int v144; // r9d
  char v145; // r15
  _QWORD *v146; // r14
  LPCCH v147; // rax
  __int64 v148; // r8
  int v149; // ecx
  int v150; // edx
  struct CCookie *v151; // rax
  struct HTTP_REQUEST_HANDLE_OBJECT *v152; // r14
  int v153; // esi
  __int64 v154; // rdx
  __int64 v155; // rax
  unsigned int v156; // esi
  LPCCH v157; // r14
  __int64 v158; // rcx
  _BYTE *v159; // rax
  unsigned int v160; // r8d
  __int16 v161; // r13
  __int64 v162; // rcx
  char *v163; // rax
  unsigned int v164; // r8d
  __int16 v165; // r12
  struct _RTL_CRITICAL_SECTION *v166; // rdx
  __int64 v167; // rcx
  struct _RTL_CRITICAL_SECTION *v168; // rax
  unsigned int v169; // r8d
  unsigned __int16 v170; // r14
  _BYTE *v171; // r15
  __int64 v172; // rcx
  _BYTE *v173; // rax
  unsigned int v174; // edx
  const CHAR *v175; // rsi
  const char *v176; // rdx
  int v177; // esi
  unsigned int v178; // r8d
  struct CCookieHost *v179; // r14
  void **v180; // rbx
  void *v181; // r8
  bool v182; // zf
  void **v183; // rsi
  void **v184; // rdi
  void **v185; // rbx
  void *v186; // r8
  void **v187; // rbx
  void *v188; // r8
  __int64 v189; // rbx
  int v191; // [rsp+60h] [rbp-A0h]
  int v192; // [rsp+64h] [rbp-9Ch]
  unsigned int v193; // [rsp+68h] [rbp-98h]
  int v194; // [rsp+6Ch] [rbp-94h]
  __int16 v195; // [rsp+6Ch] [rbp-94h]
  int v196; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v197; // [rsp+78h] [rbp-88h] BYREF
  int v198; // [rsp+80h] [rbp-80h]
  struct _FILETIME v199; // [rsp+88h] [rbp-78h] BYREF
  int v200; // [rsp+90h] [rbp-70h] BYREF
  int v201; // [rsp+94h] [rbp-6Ch]
  LPCCH lpMultiByteStr; // [rsp+98h] [rbp-68h]
  LPCCH v203; // [rsp+A0h] [rbp-60h]
  LPCSTR lpString1; // [rsp+A8h] [rbp-58h]
  int v205; // [rsp+B0h] [rbp-50h]
  int v206; // [rsp+B4h] [rbp-4Ch]
  unsigned int *v207; // [rsp+B8h] [rbp-48h]
  const char *v208; // [rsp+C0h] [rbp-40h]
  LPVOID Src; // [rsp+C8h] [rbp-38h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+D0h] [rbp-30h]
  char *v211; // [rsp+D8h] [rbp-28h]
  struct HTTP_REQUEST_HANDLE_OBJECT *v212; // [rsp+E0h] [rbp-20h]
  struct _LIST_ENTRY *v213; // [rsp+E8h] [rbp-18h]
  LPVOID v214; // [rsp+F0h] [rbp-10h]
  unsigned int *v215; // [rsp+F8h] [rbp-8h]
  CCookieLocation *v216; // [rsp+100h] [rbp+0h] BYREF
  LPVOID lpMem; // [rsp+108h] [rbp+8h] BYREF
  struct CCookieHost *v218; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v219; // [rsp+118h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+120h] [rbp+20h] BYREF
  char *v221; // [rsp+130h] [rbp+30h] BYREF
  LPCSTR v222; // [rsp+138h] [rbp+38h]
  _QWORD v223[2]; // [rsp+140h] [rbp+40h] BYREF
  LPCCH v224; // [rsp+150h] [rbp+50h] BYREF
  unsigned int v225; // [rsp+158h] [rbp+58h]
  _BYTE v226[20]; // [rsp+15Ch] [rbp+5Ch] BYREF
  CHAR MultiByteStr[272]; // [rsp+170h] [rbp+70h] BYREF
  char v228[256]; // [rsp+280h] [rbp+180h] BYREF

  v13 = a6;
  v15 = a2;
  lpMultiByteStr = a3;
  v208 = a2;
  v212 = a1;
  v16 = a10;
  lpString1 = a5;
  v215 = a10;
  v216 = 0;
  v193 = 0;
  SystemTimeAsFileTime = 0;
  v199 = 0;
  Src = 0;
  v214 = 0;
  v218 = 0;
  v203 = a4;
  v211 = a6;
  v207 = a7;
  v213 = a13;
  v17 = a12;
  v18 = Buf1;
  if ( (xmmword_180266B60 & 2) != 0 )
  {
    WPP_SF_sssssDill(
      Buf1,
      (_DWORD)a5,
      0,
      (_DWORD)a2,
      (__int64)a3,
      (__int64)a4,
      (__int64)a5,
      (__int64)a6,
      *a7,
      Buf1,
      a11,
      a12);
    v16 = v215;
  }
  if ( v16 )
    *v16 = 0;
  if ( !(unsigned int)PathAndRDomainFromURL(v15, 1) )
  {
    if ( (xmmword_180266B50 & 2) != 0 )
      WPP_SF_(513, 48, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
    v19 = 0;
    v20 = 0;
    goto LABEL_419;
  }
  v206 = GlobalSuppressCookiePersist;
  if ( GlobalSuppressCookiePersist )
    *a7 |= 2u;
  v21 = lpString1;
  if ( lpString1 )
  {
    if ( !(unsigned int)IsDomainLegal(lpString1, Src) )
    {
LABEL_17:
      if ( (xmmword_180266B50 & 2) != 0 )
        WPP_SF_(513, 49, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
      SetLastError(0x57u);
      v19 = 0;
      v20 = 0;
      goto LABEL_419;
    }
    v21 = lpString1;
  }
  if ( a6 && *a6 && *a6 != 47 )
    goto LABEL_17;
  if ( a3 )
  {
    v22 = *a3;
    if ( *a3 )
    {
      v23 = a3;
      do
      {
        if ( (unsigned __int8)v22 <= 0x1Fu )
          *v23 = 95;
        v22 = *++v23;
      }
      while ( v22 );
    }
  }
  v24 = (CHAR *)v203;
  if ( v203 )
  {
    for ( i = *v203; i; ++v24 )
    {
      if ( (unsigned __int8)i <= 0x1Fu )
        *v24 = 95;
      i = v24[1];
    }
  }
  if ( a6 )
  {
    v26 = *a6;
    if ( *a6 )
    {
      v27 = a6;
      do
      {
        if ( (unsigned __int8)v26 <= 0x1Fu )
          *v27 = 95;
        v26 = *++v27;
      }
      while ( v26 );
    }
  }
  if ( v21 )
  {
    v28 = *v21;
    if ( *v21 )
    {
      v29 = (CHAR *)v21;
      do
      {
        if ( (unsigned __int8)v28 <= 0x1Fu )
          *v29 = 95;
        v28 = *++v29;
      }
      while ( v28 );
    }
    v30 = *a7;
  }
  else
  {
    v30 = *a7;
    if ( v17 )
    {
      v30 |= 0x4000u;
      *a7 = v30;
    }
    lpString1 = (LPCSTR)Src;
  }
  if ( v17 )
    *a7 = v30 | 0x80000;
  if ( a6 || (v13 = (char *)v214, (v211 = (char *)v214) != 0) )
  {
    v31 = *v13;
    if ( *v13 )
    {
      v32 = v13;
      while ( v31 != 63 && v31 != 35 )
      {
        v31 = *++v32;
        if ( !v31 )
          goto LABEL_58;
      }
      *v32 = 0;
    }
  }
LABEL_58:
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( *(_QWORD *)&SystemTimeAsFileTime <= v18 )
    v33 = -(v18 != SystemTimeAsFileTime);
  else
    v33 = 1;
  v34 = v33 > 0;
  v198 = v34;
  if ( v212 && *((_DWORD *)v212 + 1336) || (v35 = *a7, (*a7 & 0x10) != 0) )
  {
    v205 = 1;
    if ( (xmmword_180266B60 & 2) != 0 )
    {
      WPP_SF_(1025, 50, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
      v34 = v198;
    }
    *a7 |= 0x80000000;
    v36 = 33;
    v35 = *a7;
  }
  else
  {
    v205 = 0;
    v36 = 1;
  }
  v37 = v35 & 2;
  v38 = 8;
  if ( !v37 )
    v38 = 16;
  v39 = 0;
  v194 = 0;
  v196 = v36 | v38;
  if ( v33 <= 0 && a8 && (!v37 || (*((_BYTE *)a8 + 12) & 4) != 0) )
  {
    v40 = 1;
  }
  else
  {
    v40 = 0;
    if ( !a8 )
      goto LABEL_90;
  }
  if ( !*((_DWORD *)a8 + 4) )
  {
    v41 = 1;
    goto LABEL_78;
  }
LABEL_90:
  v41 = 0;
  v191 = 0;
  if ( !a8 )
    goto LABEL_79;
  if ( *((_DWORD *)a8 + 4) == 3 )
  {
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_(1025, 51, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
    v45 = 5;
    v191 = 0;
    goto LABEL_97;
  }
LABEL_78:
  v191 = v41;
LABEL_79:
  if ( !v40 || v41 )
  {
    v45 = 1;
    v198 = v34;
LABEL_97:
    v44 = v207;
    v192 = v45;
    goto LABEL_98;
  }
  v42 = 0;
  if ( a8 )
  {
    v43 = 512;
    if ( *((_DWORD *)a8 + 2) != 3 )
      v43 = 0;
    v42 = v43 | 2;
    if ( *((_DWORD *)a8 + 2) != 4 )
      v42 = v43;
  }
  v44 = v207;
  *v207 |= v42;
  v45 = *((_DWORD *)a8 + 2);
  v192 = v45;
  if ( v45 == 5 )
  {
    if ( (xmmword_180266B60 & 2) != 0 )
    {
      WPP_SF_(1025, 52, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
      v45 = 5;
    }
    v39 = 1;
    v194 = 1;
    v198 = 1;
  }
  else
  {
    v198 = v34;
  }
LABEL_98:
  if ( (*(_BYTE *)v44 & 0x20) == 0 && v45 != 2 )
  {
    v19 = v192;
    if ( v192 == 5 )
    {
      v193 = 0;
      LOBYTE(v200) = BYTE1(Microsoft_Windows_WinINetEnableBits) & 0x10;
      if ( (Microsoft_Windows_WinINetEnableBits & 0x1000) != 0 )
      {
        StringCchCopyA(v228, 0x100u, lpString1);
        FormatReverseDomain(v228);
      }
      if ( !v39 )
      {
        if ( (xmmword_180266B50 & 2) != 0 )
          WPP_SF_(513, 57, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
        if ( (Microsoft_Windows_WinINetEnableBits & 0x1000) != 0 )
        {
          inetstrlenUShortA(v203);
          inetstrlenUShortA(lpMultiByteStr);
          inetstrlenUShortA(v13);
          v50 = inetstrlenUShortA(v228);
          McTemplateU0hsr0hsr2hsr4hsr6_EventWriteTransfer(
            (unsigned int)WININET_Context,
            (unsigned int)WININET_COOKIE_BLOCKED,
            v50,
            (unsigned int)v228,
            v51,
            (__int64)v13,
            v52,
            (__int64)lpMultiByteStr,
            v53,
            (__int64)v203);
        }
        goto LABEL_418;
      }
      if ( (xmmword_180266B50 & 2) != 0 )
        WPP_SF_(513, 56, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
      if ( (Microsoft_Windows_WinINetEnableBits & 0x1000) != 0 )
      {
        inetstrlenUShortA(v203);
        inetstrlenUShortA(lpMultiByteStr);
        inetstrlenUShortA(v13);
        v46 = inetstrlenUShortA(v228);
        McTemplateU0hsr0hsr2hsr4hsr6_EventWriteTransfer(
          (unsigned int)WININET_Context,
          (unsigned int)WININET_COOKIE_P3P_REJECTED,
          v46,
          (unsigned int)v228,
          v47,
          (__int64)v13,
          v48,
          (__int64)lpMultiByteStr,
          v49,
          (__int64)v203);
      }
    }
LABEL_123:
    v54 = 0;
    lpMem = 0;
    v219 = 0;
    v218 = 0;
    HIDWORD(v197) = 0;
    if ( InitOnceExecuteOnce(&CCookieJar::g_InitOnce, CCookieJar::InitOnceCallback, 0, 0) )
    {
      HostInternal = 0;
      lpCriticalSection = (LPCRITICAL_SECTION)CCookieJar::g_pInstance;
    }
    else
    {
      lpCriticalSection = 0;
      LastError = WxGetLastError(v56, v55);
      HostInternal = LastError;
      if ( LastError > 0 )
        HostInternal = (unsigned __int16)LastError | 0x80070000;
      HIDWORD(v197) = 622;
      if ( HostInternal >= 0 )
        HostInternal = -2147418113;
    }
    if ( HostInternal < 0 )
    {
      HIDWORD(v197) = 724;
LABEL_228:
      v98 = lpMem;
      if ( lpMem )
      {
        lpMem = 0;
        if ( g_fWxHeapExtensionInitialized )
          g_WxHeapExtensionInterfaces(v98);
        else
          HeapFree(g_hWxProcessHeap, 0, v98);
        lpMem = 0;
      }
      if ( HostInternal >= 0 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v218 + 56));
        CCookieHost::Sync(v218);
        v102 = v198;
        v103 = v218;
        v104 = v198 ^ 1;
        HIDWORD(v208) = 0;
        v105 = v211;
        if ( (xmmword_180266B60 & 2) != 0 )
          WPP_SF_sslq(v100, v99, v101, (_DWORD)lpString1, (__int64)v211, v198 ^ 1, (__int64)&v216);
        if ( !lpString1 )
        {
          v106 = -2147024809;
          HIDWORD(v208) = 1085;
          goto LABEL_261;
        }
        if ( !v105 )
        {
          v106 = -2147024809;
          HIDWORD(v208) = 1086;
          goto LABEL_261;
        }
        v216 = 0;
        v107 = -1;
        do
          ++v107;
        while ( v105[v107] );
        v108 = *((_QWORD *)v103 + 5);
        v109 = (struct CCookieLocation **)((char *)v103 + 40);
        if ( v108 )
        {
          while ( 1 )
          {
            if ( *(_DWORD *)(v108 + 40) < (unsigned int)v107 )
              goto LABEL_254;
            if ( *(_DWORD *)(v108 + 40) == (_DWORD)v107 )
            {
              v110 = *(char **)(v108 + 32);
              v111 = v105 - v110;
              do
              {
                v112 = (unsigned __int8)v110[v111];
                v113 = (unsigned __int8)*v110 - v112;
                if ( v113 )
                  break;
                ++v110;
              }
              while ( v112 );
              if ( !v113 )
              {
                v114 = *(const CHAR **)(v108 + 16);
                v115 = (const CHAR *)(lpString1 - v114);
                do
                {
                  v116 = (unsigned __int8)v115[(_QWORD)v114];
                  v117 = *(unsigned __int8 *)v114 - v116;
                  if ( v117 )
                    break;
                  ++v114;
                }
                while ( v116 );
                if ( !v117 )
                  break;
              }
            }
            v109 = (struct CCookieLocation **)(v108 + 8);
            v108 = *(_QWORD *)(v108 + 8);
            if ( !v108 )
              goto LABEL_254;
          }
          v216 = (CCookieLocation *)v108;
        }
        else
        {
LABEL_254:
          if ( !v104 )
          {
            v106 = 1;
            goto LABEL_261;
          }
          v118 = CCookieLocation::Construct(lpString1, v105);
          if ( !v118 )
          {
            v106 = -2147024882;
            HIDWORD(v208) = 1114;
            goto LABEL_261;
          }
          *((_QWORD *)v118 + 1) = *v109;
          *v109 = v118;
          v216 = v118;
        }
        v106 = 0;
LABEL_261:
        if ( (xmmword_180266B60 & 2) != 0 )
          WPP_SF_d(1025, 24, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids, (unsigned int)v106);
        if ( v106 < 0 )
          goto LABEL_302;
        if ( !v216 )
        {
          v20 = 1;
          goto LABEL_303;
        }
        v119 = v207;
        v120 = lpMultiByteStr;
        if ( !a11 )
        {
          Cookie = CCookieLocation::GetCookie(v216, lpMultiByteStr, (*v207 >> 19) & 1, (*v207 >> 14) & 1, 0);
          if ( Cookie )
          {
            if ( (*((_DWORD *)Cookie + 4) & 0x2000) != 0 && !(unsigned int)CCookie::IsExpired(Cookie) )
            {
              v19 = 5;
              v20 = 4;
              if ( (xmmword_180266B60 & 2) != 0 )
              {
                WPP_SF_ss(
                  1025,
                  58,
                  (unsigned int)WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids,
                  (_DWORD)v15,
                  (__int64)v120);
                LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v218 + 56));
                goto LABEL_419;
              }
              goto LABEL_304;
            }
          }
        }
        v122 = *v119 & 0x4000;
        if ( !v102 )
        {
          v128 = v216;
          lpCriticalSection = (LPCRITICAL_SECTION)v218;
          v129 = v122 != 0;
          v130 = 0;
          v131 = 0;
          v132 = 0;
          v133 = (LPCCH *)*((_QWORD *)v218 + 5);
          v199 = 0;
          if ( !v133 )
            goto LABEL_329;
          while ( 1 )
          {
            if ( CompareStringA(0x7Fu, 1u, *((PCNZCH *)v128 + 2), -1, v133[2], -1) == 2 )
            {
              v134 = *v133;
              if ( *v133 )
                break;
            }
LABEL_321:
            v133 = (LPCCH *)v133[1];
            if ( !v133 )
            {
              if ( v132 >= 180 )
              {
                if ( v213 )
                  PrepareInternetCallbackCookie(
                    *((LPCCH *)v131 + 4),
                    0,
                    v130[3],
                    v130[4],
                    &v199,
                    *((_DWORD *)v131 + 4),
                    v213);
                if ( !v206 && (v131[16] & 2) == 0 )
                  CCookieHost::UpdateCookieInternal(
                    (CCookieHost *)lpCriticalSection,
                    (struct CCookieLocation *)v130,
                    (struct CCookie *)v131,
                    1);
                CCookieLocation::Purge(v130, CCookie::PurgeThis, v131);
              }
              goto LABEL_329;
            }
          }
          while ( 1 )
          {
            if ( v133 == (LPCCH *)v128 )
            {
              v135 = (const CHAR *)*((_QWORD *)v134 + 4);
              v136 = (const CHAR *)(lpMultiByteStr - v135);
              do
              {
                v137 = (unsigned __int8)v136[(_QWORD)v135];
                v138 = *(unsigned __int8 *)v135 - v137;
                if ( v138 )
                  break;
                ++v135;
              }
              while ( v137 );
              if ( !v138 )
              {
                v139 = *((_DWORD *)v134 + 4);
                if ( ((v139 & 0x4000) != 0) == v129 || (*((_DWORD *)v134 + 4) & 0x4000) == 0 && (v139 & 0x80000) == 0 )
                  break;
              }
            }
            ++v132;
            if ( !v131 || *((_QWORD *)v134 + 1) < *((_QWORD *)v131 + 1) )
            {
              v131 = (CHAR *)v134;
              v130 = v133;
            }
            v134 = (LPCCH)*((_QWORD *)v134 + 3);
            if ( !v134 )
              goto LABEL_321;
          }
LABEL_329:
          v140 = v207;
          v141 = v216;
          v142 = (char *)lpMultiByteStr;
          v143 = *(_QWORD **)v216;
          v144 = *v207 & 0x80000;
          v145 = v144 != 0;
          v146 = 0;
          if ( !*(_QWORD *)v216 )
          {
LABEL_351:
            v151 = CCookie::Construct(lpMultiByteStr, (*v207 & 0x80000) != 0, (*v207 & 0x4000) != 0);
            v143 = v151;
            if ( v151 )
            {
              *((_QWORD *)v151 + 3) = 0;
              *(_QWORD *)v141 = v151;
              goto LABEL_353;
            }
            goto LABEL_302;
          }
          while ( 1 )
          {
            v147 = lpMultiByteStr;
            v148 = v143[4] - (_QWORD)lpMultiByteStr;
            do
            {
              v149 = (unsigned __int8)v147[v148];
              v150 = *(unsigned __int8 *)v147 - v149;
              if ( v150 )
                break;
              ++v147;
            }
            while ( v149 );
            if ( !v150 )
            {
              LODWORD(v148) = *((_DWORD *)v143 + 4);
              v149 = v148 & 0x4000;
              if ( (v149 != 0) == ((*v207 & 0x4000) != 0) )
              {
                if ( !v144 && (v148 & 0x80000) != 0 && (xmmword_180266B60 & 2) != 0 )
                  WPP_SF_sDll(v149, 36, v148, (_DWORD)lpMultiByteStr, v148, v145, (*v207 & 0x4000) != 0);
                if ( !v143 )
                  goto LABEL_302;
LABEL_353:
                if ( (*v140 & 0x300000) != 0 )
                {
                  v152 = v212;
                  v153 = *v140 & 0x100000;
                  TraceLoggingSameSiteSetCookie(v153 != 0, *((const unsigned __int16 **)v218 + 1), v212 == 0);
                  if ( v152 )
                  {
                    v154 = *((_QWORD *)v152 + 709);
                    if ( v154 )
                    {
                      if ( dword_180266100
                        && (qword_180266110 & 0x400000000000LL) != 0
                        && (qword_180266118 & 0x400000000000LL) == qword_180266118 )
                      {
                        v155 = 500;
                        if ( v153 )
                          v155 = 504;
                        _InterlockedIncrement((volatile signed __int32 *)(v155 + v154));
                      }
                    }
                  }
                }
                v157 = v203;
                if ( (*v140 & 0x400) == 0 )
                {
                  v156 = *v140;
                  *v140 = v156 | RestrictPolicyNonEvaluatedCookies(v142, (char *)v203);
                }
                if ( (Microsoft_Windows_WinINetEnableBits & 0x2000) != 0 )
                {
                  v195 = 0;
                  if ( v157 )
                  {
                    v199.dwHighDateTime = 0;
                    v158 = 0xFFFF;
                    v159 = v157;
                    do
                    {
                      if ( !*v159 )
                        break;
                      ++v159;
                      --v158;
                    }
                    while ( v158 );
                    v160 = -2147024809;
                    if ( v158 )
                    {
                      v160 = 0;
                      v195 = -1 - v158;
                    }
                    else
                    {
                      v199.dwHighDateTime = 135;
                      v195 = 0;
                    }
                    WX_WIN32_FROM_HR(v160);
                  }
                  v161 = 0;
                  if ( v142 )
                  {
                    v199.dwHighDateTime = 0;
                    v162 = 0xFFFF;
                    v163 = v142;
                    do
                    {
                      if ( !*v163 )
                        break;
                      ++v163;
                      --v162;
                    }
                    while ( v162 );
                    v164 = -2147024809;
                    if ( v162 )
                    {
                      v164 = 0;
                      v161 = -1 - v162;
                    }
                    else
                    {
                      v199.dwHighDateTime = 135;
                      v161 = 0;
                    }
                    WX_WIN32_FROM_HR(v164);
                  }
                  v165 = 0;
                  v166 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)v216 + 4);
                  lpCriticalSection = v166;
                  if ( v166 )
                  {
                    v199.dwHighDateTime = 0;
                    v167 = 0xFFFF;
                    v168 = v166;
                    do
                    {
                      if ( !LOBYTE(v168->DebugInfo) )
                        break;
                      v168 = (struct _RTL_CRITICAL_SECTION *)((char *)v168 + 1);
                      --v167;
                    }
                    while ( v167 );
                    v169 = -2147024809;
                    if ( v167 )
                    {
                      v169 = 0;
                      v165 = -1 - v167;
                    }
                    else
                    {
                      v199.dwHighDateTime = 135;
                      v165 = 0;
                    }
                    WX_WIN32_FROM_HR(v169);
                  }
                  v170 = 0;
                  v171 = (_BYTE *)*((_QWORD *)v216 + 3);
                  if ( v171 )
                  {
                    v199.dwHighDateTime = 0;
                    v172 = 0xFFFF;
                    v173 = v171;
                    do
                    {
                      if ( !*v173 )
                        break;
                      ++v173;
                      --v172;
                    }
                    while ( v172 );
                    v174 = -2147024809;
                    if ( v172 )
                    {
                      v174 = 0;
                      v170 = -1 - v172;
                    }
                    else
                    {
                      v199.dwHighDateTime = 135;
                      v170 = 0;
                    }
                    WX_WIN32_FROM_HR(v174);
                  }
                  v175 = v203;
                  McTemplateU0hsr0hsr2hsr4hsr6_EventWriteTransfer(
                    (unsigned int)WININET_Context,
                    (unsigned int)WININET_COOKIE_STORED,
                    v170,
                    (_DWORD)v171,
                    v165,
                    (__int64)lpCriticalSection,
                    v161,
                    (__int64)lpMultiByteStr,
                    v195,
                    (__int64)v203);
                  v142 = (char *)lpMultiByteStr;
                  v140 = v207;
                }
                else
                {
                  v175 = v203;
                }
                v143[1] = SystemTimeAsFileTime;
                if ( v213 && (*v142 || *v175) )
                  PrepareInternetCallbackCookie(
                    v142,
                    v175,
                    *((LPCCH *)v216 + 3),
                    *((const char **)v216 + 4),
                    (struct _FILETIME *)&Buf1,
                    *v140,
                    v213);
                if ( !memcmp_0(&Buf1, v143, 8u)
                  && !strcmp(v175, (const char *)v143[5])
                  && *v140 == *((_DWORD *)v143 + 4) )
                {
                  if ( (xmmword_180266B60 & 2) != 0 )
                    WPP_SF_(1025, 64, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
                  goto LABEL_416;
                }
                v176 = v203;
                v177 = v143[2] & 2;
                *v143 = v18;
                *((_DWORD *)v143 + 4) = *v140;
                CCookie::SetValue((CCookie *)v143, v176);
                v178 = ((v196 & 8 | 4u) >> 2) | 4;
                if ( (v196 & 0x20) == 0 )
                  v178 = (v196 & 8 | 4u) >> 2;
                *((_DWORD *)v143 + 13) = v178;
                if ( (xmmword_180266B60 & 2) != 0 )
                  WPP_SF_sqDD(
                    1025,
                    63,
                    (unsigned int)WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids,
                    (_DWORD)lpString1,
                    (__int64)v143,
                    v178,
                    *((_DWORD *)v143 + 4));
                if ( v206
                  || v177 && (v143[2] & 2) != 0
                  || CCookieHost::UpdateCookieInternal(v218, v216, (struct CCookie *)v143, 0) >= 0 )
                {
LABEL_416:
                  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v218 + 56));
                  v19 = v192;
                  v20 = 1;
                  goto LABEL_419;
                }
LABEL_302:
                v20 = v193;
LABEL_303:
                v19 = v192;
LABEL_304:
                LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v218 + 56));
                goto LABEL_419;
              }
              if ( (v148 & 0x4000) == 0 && (v148 & 0x80000) == 0 || !v144 && (*v207 & 0x4000) == 0 )
                v146 = v143;
            }
            v141 = (CCookieLocation *)(v143 + 3);
            v143 = (_QWORD *)v143[3];
            if ( !v143 )
            {
              if ( !v146 )
                goto LABEL_351;
              if ( (xmmword_180266B60 & 2) != 0 )
                WPP_SF_sDll(v149, 37, v148, (_DWORD)lpMultiByteStr, *((_DWORD *)v146 + 4), v145, (*v207 & 0x4000) != 0);
              v143 = v146;
              goto LABEL_353;
            }
          }
        }
        v123 = CCookieLocation::GetCookie(v216, v120, (*v119 >> 19) & 1, v122 != 0, 0);
        v124 = v123;
        if ( !v123 )
        {
          if ( (xmmword_180266B60 & 2) != 0 )
            WPP_SF_(1025, 59, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
          v19 = v192;
          if ( !v194 )
          {
            v20 = 1;
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v218 + 56));
            goto LABEL_419;
          }
          goto LABEL_286;
        }
        v125 = *((_DWORD *)v123 + 4);
        if ( (v125 & 0x200) == 0 || !v205 || v41 || (v125 & 0x800) != 0 )
        {
          if ( !v194 || !v205 || v125 < 0 )
          {
            v127 = v213;
            if ( v213 )
            {
              if ( (v125 & 2) != 0 )
                *v119 |= 2u;
              PrepareInternetCallbackCookie(
                v120,
                0,
                *((LPCCH *)v216 + 3),
                *((const char **)v216 + 4),
                &v199,
                *v119,
                v127);
            }
            if ( (xmmword_180266B60 & 2) != 0 )
              WPP_SF_(1025, 62, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
            if ( !v206 && (*((_BYTE *)v124 + 16) & 2) == 0 && CCookieHost::UpdateCookieInternal(v218, v216, v124, 1) < 0 )
            {
              CCookieLocation::Purge(v216, CCookie::PurgeThis, v124);
              goto LABEL_302;
            }
            CCookieLocation::Purge(v216, CCookie::PurgeThis, v124);
            v20 = 1;
            goto LABEL_303;
          }
          if ( (xmmword_180266B60 & 2) == 0 )
            goto LABEL_285;
          v126 = 61;
        }
        else
        {
          if ( (xmmword_180266B60 & 2) == 0 )
          {
LABEL_285:
            v19 = 5;
LABEL_286:
            v20 = v193;
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v218 + 56));
            goto LABEL_419;
          }
          v126 = 60;
        }
        WPP_SF_(1025, v126, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
        goto LABEL_285;
      }
      v19 = v192;
LABEL_418:
      v20 = v193;
      goto LABEL_419;
    }
    v201 = 0;
    v59 = 0;
    v197 = 0;
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_sqq(
        1025,
        10,
        (unsigned int)WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids,
        (_DWORD)Src,
        (__int64)&lpMem,
        (__int64)&v219);
    v60 = Src;
    v61 = (__int64)MultiByteStr;
    lpMem = 0;
    v62 = 2147483646;
    v219 = 0;
    v63 = 257;
    do
    {
      if ( !v62 )
        break;
      if ( !*v60 )
        break;
      *(_BYTE *)v61++ = *v60++;
      --v62;
      --v63;
    }
    while ( v63 );
    v64 = (_BYTE *)(v61 - 1);
    HostInternal = -2147024774;
    if ( v63 )
    {
      v64 = (_BYTE *)v61;
      HostInternal = 0;
    }
    *v64 = 0;
    if ( !v63 )
    {
      v201 = 652;
LABEL_218:
      if ( v59 )
      {
        if ( g_fWxHeapExtensionInitialized )
          g_WxHeapExtensionInterfaces(v59, v61, v62, v60);
        else
          HeapFree(g_hWxProcessHeap, 0, v59);
      }
      if ( (xmmword_180266B60 & 2) != 0 )
        WPP_SF_d(1025, 12, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids, (unsigned int)HostInternal);
      if ( HostInternal >= 0 )
      {
        HostInternal = CCookieJar::GetHostInternal(lpCriticalSection, (const unsigned __int16 *)lpMem, v219, &v218);
        if ( HostInternal < 0 )
          HIDWORD(v197) = 730;
      }
      else
      {
        HIDWORD(v197) = 728;
      }
      goto LABEL_228;
    }
    v65 = -1;
    v66 = 0;
    do
      ++v65;
    while ( MultiByteStr[v65] );
    if ( v65 > 1 )
    {
      v67 = MultiByteStr[0];
      v68 = 0;
      if ( MultiByteStr[0] )
      {
        v69 = MultiByteStr;
        do
        {
          if ( (unsigned __int8)(v67 - 65) <= 0x19u )
            *v69 = v67 + 32;
          v67 = *++v69;
        }
        while ( v67 );
      }
      v70 = &v226[v65 + 19];
      for ( j = MultiByteStr; j < v70; --v70 )
      {
        v72 = *j;
        *j++ = *v70;
        *v70 = v72;
      }
      do
      {
        for ( ; v68 < v65; ++v68 )
        {
          if ( MultiByteStr[v68] != 46 )
            break;
        }
        for ( k = v68; v68 < v65; ++v68 )
        {
          if ( MultiByteStr[v68] == 46 )
            break;
        }
        v74 = &MultiByteStr[v68 - 1];
        for ( m = &MultiByteStr[k]; m < v74; --v74 )
        {
          v76 = *m;
          *m++ = *v74;
          *v74 = v76;
        }
        ++v68;
      }
      while ( v68 < v65 );
    }
    HostInternal = 0;
    LODWORD(v78) = MultiByteToWideChar(0, 0, MultiByteStr, -1, 0, 0);
    v61 = 0xFFFFFFFFLL;
    if ( !(_DWORD)v78 )
    {
      HostInternal = WxGetLastError(v77, 0xFFFFFFFFLL);
      if ( HostInternal != 1004 )
        goto LABEL_170;
      HostInternal = 0;
      LODWORD(v78) = MultiByteToWideChar(0, 0, MultiByteStr, -1, 0, 0);
      if ( !(_DWORD)v78 )
      {
LABEL_169:
        HostInternal = WxGetLastError(v79, v61);
LABEL_170:
        if ( HostInternal )
        {
          if ( v54 )
            HeapFree(g_hWxProcessHeap, 0, v54);
          if ( HostInternal > 0 )
            goto LABEL_179;
        }
        else if ( v54 )
        {
          v66 = v54;
        }
LABEL_180:
        if ( HostInternal < 0 )
        {
          v201 = 664;
LABEL_213:
          if ( v66 )
          {
            if ( g_fWxHeapExtensionInitialized )
              g_WxHeapExtensionInterfaces(v66);
            else
              HeapFree(g_hWxProcessHeap, 0, v66);
          }
          v41 = v191;
          LODWORD(v15) = (_DWORD)v208;
          goto LABEL_218;
        }
        v84 = ConvertCacheIdnToAscii(v66, (unsigned int)v78, 1, &v197);
        v59 = v197;
        HostInternal = v84;
        if ( v84 < 0 )
        {
          v201 = 668;
          goto LABEL_213;
        }
        HIDWORD(v197) = 0;
        v200 = 0;
        if ( !v59 )
        {
          HIDWORD(v197) = 77;
          HostInternal = -2147024809;
          v201 = 670;
          goto LABEL_213;
        }
        v85 = v59;
        v86 = 0x7FFFFFFF;
        do
        {
          if ( !*v85 )
            break;
          ++v85;
          --v86;
        }
        while ( v86 );
        HostInternal = -2147024809;
        if ( v86 )
          HostInternal = 0;
        v87 = 0x7FFFFFFF - v86;
        if ( !v86 )
        {
          HIDWORD(v197) = 81;
          v201 = 670;
          goto LABEL_213;
        }
        LabelEntry::LabelEntry((LabelEntry *)&v221);
        LabelEntry::LabelEntry((LabelEntry *)v223);
        LabelEntry::LabelEntry((LabelEntry *)&v224);
        LabelEntry::LabelEntry((LabelEntry *)&v226[4]);
        v200 = 0;
        v89 = 4;
        v90 = 0;
        v91 = v87;
        v92 = v87;
        v93 = v87;
        if ( !v87 )
          goto LABEL_202;
        do
        {
          v88 = v91 - 1;
          if ( !v91 || v59[v88] == 46 )
          {
            if ( v90 < 4 )
            {
              v94 = 2LL * v90;
              (&v221)[v94] = (char *)&v59[v91];
              LODWORD(v223[v94 - 1]) = v92 - v91;
              if ( v91 )
                v92 = v91 - 1;
            }
            ++v90;
          }
        }
        while ( v91-- );
        if ( v90 < 4 )
LABEL_202:
          v89 = v90;
        DetermineNumberOfLabelsInDomain(&v221, v89, v88, &v200);
        if ( v200 )
        {
          v61 = (__int64)(&v221)[2 * (unsigned int)(v200 - 1)];
          v96 = (v61 - (__int64)v59) >> 1;
          if ( v96 > 0xFFFFFFFF )
          {
            HostInternal = -2147024362;
            v201 = 676;
            goto LABEL_213;
          }
          v97 = v87 - v96;
          HostInternal = 0;
          if ( v61 )
          {
LABEL_210:
            FormatReverseDomainW(v59, v93);
            v59[v97] = 0;
            if ( (xmmword_180266B60 & 2) != 0 )
              WPP_SF_Sd(1025, 11, (unsigned int)WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids, (_DWORD)v59, v97);
            lpMem = v59;
            v59 = 0;
            v219 = v97;
            goto LABEL_213;
          }
        }
        else
        {
          HostInternal = 0;
        }
        v97 = v93;
        goto LABEL_210;
      }
      v61 = 0xFFFFFFFFLL;
    }
    v80 = (unsigned int)v78;
    v78 = (unsigned int)(v78 - 1);
    v81 = 2 * v80;
    if ( v81 > 0xFFFFFFFF )
    {
      LOWORD(HostInternal) = 534;
      goto LABEL_179;
    }
    v82 = v81;
    lpWideCharStr = (WCHAR *)HeapAlloc(g_hWxProcessHeap, 0, (unsigned int)v81);
    v54 = lpWideCharStr;
    if ( !lpWideCharStr )
    {
      LOWORD(HostInternal) = 8;
LABEL_179:
      HostInternal = (unsigned __int16)HostInternal | 0x80070000;
      goto LABEL_180;
    }
    if ( MultiByteToWideChar(0, 0, MultiByteStr, -1, lpWideCharStr, v82 >> 1) )
    {
      v66 = v54;
      v54[v78] = 0;
      goto LABEL_180;
    }
    goto LABEL_169;
  }
  if ( !(unsigned __int8)IsMessageBoxWPresent() )
  {
    if ( (xmmword_180266B50 & 2) != 0 )
      WPP_SF_(513, 53, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
    v19 = 5;
    goto LABEL_418;
  }
  if ( (xmmword_180266B60 & 2) != 0 )
    WPP_SF_(1025, 54, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
  v222 = lpString1;
  *(_OWORD *)v226 = 0;
  v223[1] = lpMultiByteStr;
  v225 = *v44;
  *(_DWORD *)&v226[4] = HIDWORD(Buf1);
  v221 = v15;
  v223[0] = v13;
  v224 = v203;
  *(_DWORD *)v226 = v18;
  *(_QWORD *)&v226[12] = a8;
  v193 = CCookieJar::CheckCookiePolicy(v212, (struct CookieInfo *)&v221, v196);
  v20 = v193;
  if ( v193 == 1 )
  {
    v192 = 1;
    goto LABEL_123;
  }
  if ( (xmmword_180266B60 & 2) != 0 )
    WPP_SF_(1025, 55, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
  v19 = 5;
LABEL_419:
  if ( (xmmword_180266B60 & 2) != 0 )
    WPP_SF_d(1025, 65, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids, v20);
  if ( Src )
    HeapFree(g_hWxProcessHeap, 0, Src);
  if ( v214 )
    HeapFree(g_hWxProcessHeap, 0, v214);
  if ( v215 )
    *v215 = v19;
  v179 = v218;
  if ( v218 && _InterlockedExchangeAdd((volatile signed __int32 *)v218, 0xFFFFFFFF) == 1 && v179 )
  {
    v180 = (void **)((char *)v179 + 8);
    if ( v179 != (struct CCookieHost *)-8LL )
    {
      v181 = *v180;
      if ( *v180 )
      {
        v182 = g_fWxHeapExtensionInitialized == 0;
        *v180 = 0;
        if ( v182 )
          HeapFree(g_hWxProcessHeap, 0, v181);
        else
          g_WxHeapExtensionInterfaces(v181);
        *v180 = 0;
      }
    }
    v183 = (void **)*((_QWORD *)v179 + 5);
    *((_DWORD *)v179 + 4) = 0;
    *((_QWORD *)v179 + 3) = 0;
    *((_QWORD *)v179 + 5) = 0;
    while ( v183 )
    {
      v184 = v183;
      v183 = (void **)v183[1];
      CCookieLocation::Purge(v184, CCookie::PurgeAll, 0);
      v185 = v184 + 6;
      if ( v184 != (void **)-48LL )
      {
        v186 = *v185;
        if ( *v185 )
        {
          v182 = g_fWxHeapExtensionInitialized == 0;
          *v185 = 0;
          if ( v182 )
            HeapFree(g_hWxProcessHeap, 0, v186);
          else
            g_WxHeapExtensionInterfaces(v186);
          *v185 = 0;
        }
      }
      v187 = v184 + 7;
      if ( v184 != (void **)-56LL )
      {
        v188 = *v187;
        if ( *v187 )
        {
          v182 = g_fWxHeapExtensionInitialized == 0;
          *v187 = 0;
          if ( v182 )
            HeapFree(g_hWxProcessHeap, 0, v188);
          else
            g_WxHeapExtensionInterfaces(v188);
          *v187 = 0;
        }
      }
      HeapFree(g_hWxProcessHeap, 0, v184);
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v179 + 56));
    v189 = *((_QWORD *)v179 + 6);
    if ( v189 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v189, 0xFFFFFFFF) == 1 )
      {
        DeleteCriticalSection((LPCRITICAL_SECTION)(v189 + 9224));
        operator delete((void *)v189, 0x2430u);
      }
      *((_QWORD *)v179 + 6) = 0;
    }
    operator delete(v179, 0x60u);
  }
  return v20;
}

```

## disassembly

```asm
0x18006a6b0  push    rbp
0x18006a6b2  push    rbx
0x18006a6b3  push    rsi
0x18006a6b4  push    rdi
0x18006a6b5  push    r12
0x18006a6b7  push    r13
0x18006a6b9  push    r14
0x18006a6bb  push    r15
0x18006a6bd  lea     rbp, [rsp-298h]
0x18006a6c5  sub     rsp, 398h
0x18006a6cc  mov     rax, cs:__security_cookie
0x18006a6d3  xor     rax, rsp
0x18006a6d6  mov     [rbp+2D0h+var_50], rax
0x18006a6dd  mov     r14, [rbp+2D0h+arg_28]
0x18006a6e4  mov     r15, r8
0x18006a6e7  mov     r12, [rbp+2D0h+arg_30]
0x18006a6ee  mov     r13, rdx
0x18006a6f1  mov     rax, [rbp+2D0h+arg_60]
0x18006a6f8  mov     rsi, [rbp+2D0h+arg_38]
0x18006a6ff  mov     [rbp+2D0h+lpMultiByteStr], r8
0x18006a703  xor     r8d, r8d
0x18006a706  mov     [rbp+2D0h+var_310], rdx
0x18006a70a  mov     rdx, [rbp+2D0h+arg_20]
0x18006a711  mov     [rbp+2D0h+var_2F0], rcx
0x18006a715  mov     rcx, [rbp+2D0h+arg_48]
0x18006a71c  mov     [rbp+2D0h+lpString1], rdx
0x18006a720  mov     [rbp+2D0h+var_2D8], rcx
0x18006a724  mov     [rbp+2D0h+var_2D0], r8
0x18006a728  mov     [rsp+3D0h+var_368], r8d
0x18006a72d  mov     qword ptr [rbp+2D0h+SystemTimeAsFileTime.dwLowDateTime], r8
0x18006a731  mov     qword ptr [rbp+2D0h+var_348.dwLowDateTime], r8
0x18006a735  mov     [rsp+3D0h+var_36C], r8d
0x18006a73a  mov     [rbp+2D0h+Src], r8
0x18006a73e  mov     [rbp+2D0h+var_2E0], r8
0x18006a742  mov     [rsp+3D0h+var_360], r8d
0x18006a747  mov     [rbp+2D0h+var_2C0], r8
0x18006a74b  mov     [rbp+2D0h+var_330], r9
0x18006a74f  mov     [rbp+2D0h+var_2F8], r14
0x18006a753  mov     [rbp+2D0h+var_318], r12
0x18006a757  mov     [rbp+2D0h+var_2E8], rax
0x18006a75b  test    byte ptr cs:xmmword_180266B60, 2
0x18006a762  mov     edi, [rbp+2D0h+arg_58]
0x18006a768  mov     rbx, [rbp+2D0h+Buf1]
0x18006a76f  jz      short loc_18006A7C4
0x18006a771  mov     [rsp+3D0h+var_378], edi
0x18006a775  mov     rax, 0FFFFFFFF00000000h
0x18006a77f  mov     rcx, rbx
0x18006a782  and     rcx, rax
0x18006a785  mov     eax, ebx
0x18006a787  or      rcx, rax
0x18006a78a  mov     eax, [rbp+2D0h+arg_50]
0x18006a790  mov     [rsp+3D0h+var_380], eax
0x18006a794  mov     eax, [r12]
0x18006a798  mov     [rsp+3D0h+var_388], rcx
0x18006a79d  mov     [rsp+3D0h+var_390], eax
0x18006a7a1  mov     [rsp+3D0h+var_398], r14
0x18006a7a6  mov     [rsp+3D0h+var_3A0], rdx
0x18006a7ab  mov     qword ptr [rsp+3D0h+cchWideChar], r9
0x18006a7b0  mov     r9, r13
0x18006a7b3  mov     [rsp+3D0h+lpWideCharStr], r15
0x18006a7b8  call    WPP_SF_sssssDill
0x18006a7bd  mov     rcx, [rbp+2D0h+var_2D8]
0x18006a7c1  xor     r8d, r8d
0x18006a7c4  test    rcx, rcx
0x18006a7c7  jz      short loc_18006A7CC
0x18006a7c9  mov     [rcx], r8d
0x18006a7cc  lea     r9, [rsp+3D0h+var_360]
0x18006a7d1  mov     dword ptr [rsp+3D0h+lpWideCharStr], 1; int
0x18006a7d9  lea     r8, [rbp+2D0h+var_2E0]
0x18006a7dd  mov     rcx, r13; Src
0x18006a7e0  lea     rdx, [rbp+2D0h+Src]
0x18006a7e4  call    PathAndRDomainFromURL
0x18006a7e9  test    eax, eax
0x18006a7eb  jnz     short loc_18006A818
0x18006a7ed  test    byte ptr cs:xmmword_180266B50, 2
0x18006a7f4  jz      short loc_18006A80C
0x18006a7f6  mov     edx, 30h ; '0'
0x18006a7fb  lea     r8, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids
0x18006a802  mov     ecx, 201h
0x18006a807  call    WPP_SF_
0x18006a80c  mov     esi, [rsp+3D0h+var_36C]
0x18006a810  mov     r12d, esi
0x18006a813  jmp     loc_18006BEB7
0x18006a818  mov     eax, cs:GlobalSuppressCookiePersist
0x18006a81e  mov     [rbp+2D0h+var_31C], eax
0x18006a821  test    eax, eax
0x18006a823  jz      short loc_18006A82A
0x18006a825  or      dword ptr [r12], 2
0x18006a82a  mov     r8, [rbp+2D0h+lpString1]
0x18006a82e  test    r8, r8
0x18006a831  jz      short loc_18006A847
0x18006a833  mov     rdx, [rbp+2D0h+Src]; Src
0x18006a837  mov     rcx, r8; lpString1
0x18006a83a  call    IsDomainLegal
0x18006a83f  test    eax, eax
0x18006a841  jz      short loc_18006A858
0x18006a843  mov     r8, [rbp+2D0h+lpString1]
0x18006a847  test    r14, r14
0x18006a84a  jz      short loc_18006A88E
0x18006a84c  movzx   eax, byte ptr [r14]
0x18006a850  test    al, al
0x18006a852  jz      short loc_18006A88E
0x18006a854  cmp     al, 2Fh ; '/'
0x18006a856  jz      short loc_18006A88E
0x18006a858  test    byte ptr cs:xmmword_180266B50, 2
0x18006a85f  jz      short loc_18006A877
0x18006a861  mov     edx, 31h ; '1'
0x18006a866  lea     r8, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids
0x18006a86d  mov     ecx, 201h
0x18006a872  call    WPP_SF_
0x18006a877  mov     ecx, 57h ; 'W'; dwErrCode
0x18006a87c  call    cs:__imp_SetLastError
0x18006a882  mov     esi, [rsp+3D0h+var_36C]
0x18006a886  mov     r12d, esi
0x18006a889  jmp     loc_18006BEB7
0x18006a88e  test    r15, r15
0x18006a891  jz      short loc_18006A8B3
0x18006a893  movzx   ecx, byte ptr [r15]
0x18006a897  test    cl, cl
0x18006a899  jz      short loc_18006A8B3
0x18006a89b  mov     rax, r15
0x18006a89e  xchg    ax, ax
0x18006a8a0  cmp     cl, 1Fh
0x18006a8a3  ja      short loc_18006A8A8
0x18006a8a5  mov     byte ptr [rax], 5Fh ; '_'
0x18006a8a8  movzx   ecx, byte ptr [rax+1]
0x18006a8ac  inc     rax
0x18006a8af  test    cl, cl
0x18006a8b1  jnz     short loc_18006A8A0
0x18006a8b3  mov     rax, [rbp+2D0h+var_330]
0x18006a8b7  test    rax, rax
0x18006a8ba  jz      short loc_18006A8D6
0x18006a8bc  movzx   ecx, byte ptr [rax]
0x18006a8bf  test    cl, cl
0x18006a8c1  jz      short loc_18006A8D6
0x18006a8c3  cmp     cl, 1Fh
0x18006a8c6  ja      short loc_18006A8CB
0x18006a8c8  mov     byte ptr [rax], 5Fh ; '_'
0x18006a8cb  movzx   ecx, byte ptr [rax+1]
0x18006a8cf  inc     rax
0x18006a8d2  test    cl, cl
0x18006a8d4  jnz     short loc_18006A8C3
0x18006a8d6  test    r14, r14
0x18006a8d9  jz      short loc_18006A8F9
0x18006a8db  movzx   ecx, byte ptr [r14]
0x18006a8df  test    cl, cl
0x18006a8e1  jz      short loc_18006A8F9
0x18006a8e3  mov     rax, r14
0x18006a8e6  cmp     cl, 1Fh
0x18006a8e9  ja      short loc_18006A8EE
0x18006a8eb  mov     byte ptr [rax], 5Fh ; '_'
0x18006a8ee  movzx   ecx, byte ptr [rax+1]
0x18006a8f2  inc     rax
0x18006a8f5  test    cl, cl
0x18006a8f7  jnz     short loc_18006A8E6
0x18006a8f9  test    r8, r8
0x18006a8fc  jz      short loc_18006A929
0x18006a8fe  movzx   ecx, byte ptr [r8]
0x18006a902  test    cl, cl
0x18006a904  jz      short loc_18006A923
0x18006a906  mov     rax, r8
0x18006a909  nop     dword ptr [rax+00000000h]
0x18006a910  cmp     cl, 1Fh
0x18006a913  ja      short loc_18006A918
0x18006a915  mov     byte ptr [rax], 5Fh ; '_'
0x18006a918  movzx   ecx, byte ptr [rax+1]
0x18006a91c  inc     rax
0x18006a91f  test    cl, cl
0x18006a921  jnz     short loc_18006A910
0x18006a923  mov     eax, [r12]
0x18006a927  jmp     short loc_18006A941
0x18006a929  mov     eax, [r12]
0x18006a92d  test    edi, edi
0x18006a92f  jz      short loc_18006A939
0x18006a931  bts     eax, 0Eh
0x18006a935  mov     [r12], eax
0x18006a939  mov     rcx, [rbp+2D0h+Src]
0x18006a93d  mov     [rbp+2D0h+lpString1], rcx
0x18006a941  test    edi, edi
0x18006a943  jz      short loc_18006A94D
0x18006a945  bts     eax, 13h
0x18006a949  mov     [r12], eax
0x18006a94d  test    r14, r14
0x18006a950  jnz     short loc_18006A95F
0x18006a952  mov     r14, [rbp+2D0h+var_2E0]
0x18006a956  mov     [rbp+2D0h+var_2F8], r14
0x18006a95a  test    r14, r14
0x18006a95d  jz      short loc_18006A988
0x18006a95f  movzx   eax, byte ptr [r14]
0x18006a963  test    al, al
0x18006a965  jz      short loc_18006A988
0x18006a967  mov     rcx, r14
0x18006a96a  nop     word ptr [rax+rax+00h]
0x18006a970  cmp     al, 3Fh ; '?'
0x18006a972  jz      short loc_18006A985
0x18006a974  cmp     al, 23h ; '#'
0x18006a976  jz      short loc_18006A985
0x18006a978  movzx   eax, byte ptr [rcx+1]
0x18006a97c  inc     rcx
0x18006a97f  test    al, al
0x18006a981  jnz     short loc_18006A970
0x18006a983  jmp     short loc_18006A988
0x18006a985  mov     byte ptr [rcx], 0
0x18006a988  lea     rcx, [rbp+2D0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18006a98c  call    cs:__imp_GetSystemTimeAsFileTime
0x18006a992  mov     rax, qword ptr [rbp+2D0h+SystemTimeAsFileTime.dwLowDateTime]
0x18006a996  cmp     rax, rbx
0x18006a999  jle     short loc_18006A9A2
0x18006a99b  mov     edi, 1
0x18006a9a0  jmp     short loc_18006A9AA
0x18006a9a2  sub     rax, rbx
0x18006a9a5  neg     rax
0x18006a9a8  sbb     edi, edi
0x18006a9aa  mov     rax, [rbp+2D0h+var_2F0]
0x18006a9ae  xor     r8d, r8d
0x18006a9b1  test    edi, edi
0x18006a9b3  setnle  r8b
0x18006a9b7  mov     [rbp+2D0h+var_350], r8d
0x18006a9bb  test    rax, rax
0x18006a9be  jz      short loc_18006A9C9
0x18006a9c0  cmp     dword ptr [rax+14E0h], 0
0x18006a9c7  jnz     short loc_18006A9DF
0x18006a9c9  mov     eax, [r12]
0x18006a9cd  test    al, 10h
0x18006a9cf  jnz     short loc_18006A9DF
0x18006a9d1  mov     [rbp+2D0h+var_320], 0
0x18006a9d8  mov     ecx, 1
0x18006a9dd  jmp     short loc_18006AA1A
0x18006a9df  mov     [rbp+2D0h+var_320], 1
0x18006a9e6  test    byte ptr cs:xmmword_180266B60, 2
0x18006a9ed  jz      short loc_18006AA09
0x18006a9ef  mov     edx, 32h ; '2'
0x18006a9f4  lea     r8, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids
0x18006a9fb  mov     ecx, 401h
0x18006aa00  call    WPP_SF_
0x18006aa05  mov     r8d, [rbp+2D0h+var_350]
0x18006aa09  or      dword ptr [r12], 80000000h
0x18006aa11  mov     ecx, 21h ; '!'
0x18006aa16  mov     eax, [r12]
0x18006aa1a  and     eax, 2
0x18006aa1d  mov     edx, 8
0x18006aa22  mov     r9d, 10h
0x18006aa28  cmovz   edx, r9d
0x18006aa2c  xor     r12d, r12d
0x18006aa2f  or      edx, ecx
0x18006aa31  mov     [rsp+3D0h+var_364], r12d
0x18006aa36  mov     [rsp+3D0h+var_360], edx
0x18006aa3a  test    edi, edi
0x18006aa3c  jg      short loc_18006AA54
0x18006aa3e  test    rsi, rsi
0x18006aa41  jz      short loc_18006AA54
0x18006aa43  test    eax, eax
0x18006aa45  jz      short loc_18006AA4D
0x18006aa47  test    byte ptr [rsi+0Ch], 4
0x18006aa4b  jz      short loc_18006AA54
0x18006aa4d  mov     eax, 1
0x18006aa52  jmp     short loc_18006AA5F
0x18006aa54  xor     eax, eax
0x18006aa56  test    rsi, rsi
0x18006aa59  jz      loc_18006AAEA
0x18006aa5f  cmp     [rsi+10h], r12d
0x18006aa63  jnz     loc_18006AAEA
0x18006aa69  mov     r15d, 1
0x18006aa6f  mov     [rsp+3D0h+var_370], r15d
0x18006aa74  test    eax, eax
0x18006aa76  jz      loc_18006AB36
0x18006aa7c  test    r15d, r15d
0x18006aa7f  jnz     loc_18006AB36
0x18006aa85  xor     eax, eax
0x18006aa87  test    rsi, rsi
0x18006aa8a  jz      short loc_18006AAA4
0x18006aa8c  cmp     dword ptr [rsi+8], 3
0x18006aa90  mov     edx, 200h
0x18006aa95  cmovnz  edx, eax
0x18006aa98  mov     eax, edx
0x18006aa9a  or      eax, 2
0x18006aa9d  cmp     dword ptr [rsi+8], 4
0x18006aaa1  cmovnz  eax, edx
0x18006aaa4  mov     rdi, [rbp+2D0h+var_318]
0x18006aaa8  or      [rdi], eax
0x18006aaaa  mov     eax, [rsi+8]
0x18006aaad  mov     [rsp+3D0h+var_36C], eax
0x18006aab1  cmp     eax, 5
0x18006aab4  jnz     short loc_18006AB30
0x18006aab6  test    byte ptr cs:xmmword_180266B60, 2
0x18006aabd  jz      short loc_18006AAD9
0x18006aabf  mov     edx, 34h ; '4'
0x18006aac4  lea     r8, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids
0x18006aacb  mov     ecx, 401h
0x18006aad0  call    WPP_SF_
0x18006aad5  mov     eax, [rsp+3D0h+var_36C]
0x18006aad9  mov     r12d, 1
0x18006aadf  mov     [rsp+3D0h+var_364], r12d
0x18006aae4  mov     [rbp+2D0h+var_350], r12d
0x18006aae8  jmp     short loc_18006AB47
0x18006aaea  xor     r15d, r15d
0x18006aaed  mov     [rsp+3D0h+var_370], r15d
0x18006aaf2  test    rsi, rsi
0x18006aaf5  jz      loc_18006AA74
0x18006aafb  cmp     dword ptr [rsi+10h], 3
  ... truncated ...
```
