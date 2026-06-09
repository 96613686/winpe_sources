# FFormatParams(wchar_t const *,int,wchar_t *,int,wchar_t *,int,int,int,int,int,CFormattedParams *,EFormatType const *,char *)

- ea: `0x1004168e0`
- end: `0x1004177a0`
- name: `?FFormatParams@@YAHPEB_WHPEA_WH1HHHHHPEAVCFormattedParams@@PEBW4EFormatType@@PEAD@Z`
- size: `3776`
- prototype: `__int64 __fastcall(const wchar_t *, int, wchar_t *, int, wchar_t *, int, int, int, int, int, struct CFormattedParams *, const enum EFormatType *, char *)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x100417840`
- `0x100417db0`
- `0x1004183a0`

## callees

- `0x100403b90`
- `0x100415f30`
- `0x100416840`
- `0x1004168e0`
- `0x100418a50`
- `0x100418ac0`
- `0x10045d9a0`
- `0x10045da10`
- `0x10045da40`
- `0x10045db90`
- `0x100486250`
- `0x100486af0`
- `0x100487cd6`

## import_xrefs

- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x100416fa6`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x10041733f`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1004173b1`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x100417450`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x100417697`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x100416fa6`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x10041733f`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1004173b1`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x100417450`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x100417697`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1004170af`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1004170ff`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100417206`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1004174b9`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100417615`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1004170af`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1004170ff`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100417206`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1004174b9`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100417615`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100417722`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100417722`
- `sqldk!??_V@YAXPEAX@Z` at `0x100416e07`
- `sqldk!??_V@YAXPEAX@Z` at `0x100416e8f`
- `sqldk!??_V@YAXPEAX@Z` at `0x100417409`
- `sqldk!??_V@YAXPEAX@Z` at `0x100416e07`
- `sqldk!??_V@YAXPEAX@Z` at `0x100416e8f`
- `sqldk!??_V@YAXPEAX@Z` at `0x100417409`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100416df3`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100416df3`
- `sqldk!SystemThread_TlsIndex` at `0x100416d8f`
- `sqldk!SystemThread_TlsOffset` at `0x100416d98`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100416db1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100416db1`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100416e44`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100416e44`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100416e38`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100416e38`
- `api-ms-win-crt-string-l1-1-0!_iswdigit_l` at `0x1004174c8`
- `api-ms-win-crt-string-l1-1-0!_iswdigit_l` at `0x1004174c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FFormatParams(
        const wchar_t *a1,
        int a2,
        wchar_t *a3,
        int a4,
        wchar_t *a5,
        int a6,
        int a7,
        unsigned int a8,
        int a9,
        int a10,
        struct CFormattedParams *a11,
        const enum EFormatType *a12,
        char *a13)
{
  const wchar_t *v14; // r10
  struct CFormattedParams *v15; // r13
  wchar_t *v16; // r9
  char *v17; // rdx
  int v18; // r14d
  int v19; // esi
  int v20; // r11d
  const wchar_t *v21; // rdi
  int v22; // ecx
  int v23; // r15d
  unsigned int v24; // r13d
  int v25; // eax
  unsigned __int16 v26; // r14
  char v27; // r12
  __int16 v28; // bx
  char *v29; // rdi
  int v30; // eax
  __int64 v31; // rsi
  __int16 v32; // r14
  unsigned __int64 v33; // rsi
  __int64 v34; // r8
  const void *v35; // rdi
  void *v36; // rbx
  int v37; // eax
  signed __int64 v38; // rsi
  signed __int64 v39; // r14
  __int64 v40; // rbx
  __int64 v41; // rcx
  unsigned __int64 v42; // rax
  size_t v43; // r8
  unsigned int v44; // ebx
  struct IErrorReportingManager *v45; // rax
  char *v46; // rdi
  __int64 v47; // rax
  __int64 v48; // r9
  _DWORD *v49; // rax
  __int64 v50; // rax
  _DWORD *v51; // r15
  int v52; // ebx
  struct __crt_locale_pointers *DefaultLocale; // rax
  int v54; // eax
  __int64 v55; // rsi
  int i; // r14d
  int v57; // edi
  int v58; // ebx
  struct __crt_locale_pointers *v59; // rax
  int v60; // ecx
  int v61; // eax
  int v62; // edi
  __int64 v63; // rbx
  __crt_locale_pointers *v64; // rax
  unsigned int v65; // edi
  int v66; // r15d
  int v67; // r14d
  __int64 v68; // r12
  __int64 v69; // rbx
  wchar_t v70; // ax
  int v71; // r13d
  IErrorReportingManager *v72; // rax
  IErrorReportingManager *v74; // rax
  IErrorReportingManager *ErrorReportingManager; // rax
  int v76; // edi
  int v77; // r15d
  BOOL v78; // esi
  wchar_t *v79; // r13
  __crt_locale_pointers *v80; // rax
  int v81; // r8d
  int v82; // edx
  int v83; // edi
  char v84; // cl
  __int64 v85; // rax
  int v86; // eax
  __int64 v87; // rsi
  __crt_locale_pointers *v88; // rax
  wchar_t *v89; // rdi
  __int64 v90; // rbx
  IErrorReportingManager *v91; // rax
  wchar_t *v92; // rbx
  _locale_t Locale; // [rsp+20h] [rbp-E0h]
  int v94[2]; // [rsp+28h] [rbp-D8h]
  int v95; // [rsp+60h] [rbp-A0h]
  int v96; // [rsp+60h] [rbp-A0h]
  char *v97; // [rsp+68h] [rbp-98h]
  unsigned int v98; // [rsp+70h] [rbp-90h]
  int v99; // [rsp+80h] [rbp-80h]
  unsigned int v100; // [rsp+84h] [rbp-7Ch]
  int v102; // [rsp+88h] [rbp-78h]
  __int64 v103; // [rsp+90h] [rbp-70h]
  __int128 v104; // [rsp+A0h] [rbp-60h] BYREF
  int v105; // [rsp+B0h] [rbp-50h]
  wchar_t *v106; // [rsp+B8h] [rbp-48h]
  int v107; // [rsp+C0h] [rbp-40h]
  wchar_t *v108; // [rsp+C8h] [rbp-38h]
  void *v109; // [rsp+D0h] [rbp-30h]
  const wchar_t *v110; // [rsp+D8h] [rbp-28h]
  __int64 v111; // [rsp+E0h] [rbp-20h]
  __m128i v112; // [rsp+F0h] [rbp-10h] BYREF
  int v113; // [rsp+100h] [rbp+0h]
  __m128i v114; // [rsp+108h] [rbp+8h] BYREF
  int v115; // [rsp+118h] [rbp+18h]
  __m128i si128; // [rsp+120h] [rbp+20h] BYREF
  int v117; // [rsp+130h] [rbp+30h]
  __m128i v118; // [rsp+138h] [rbp+38h] BYREF
  int v119; // [rsp+148h] [rbp+48h]
  __int64 v120; // [rsp+150h] [rbp+50h]
  __int128 v121; // [rsp+160h] [rbp+60h] BYREF
  __int128 v122; // [rsp+170h] [rbp+70h] BYREF
  __int128 v123; // [rsp+180h] [rbp+80h] BYREF
  __int128 v124; // [rsp+190h] [rbp+90h] BYREF
  __int128 v125; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v126; // [rsp+1B0h] [rbp+B0h] BYREF
  _OWORD v127[6]; // [rsp+1C0h] [rbp+C0h] BYREF

  v120 = -2;
  v107 = a4;
  v108 = a3;
  v14 = a1;
  v110 = a1;
  v15 = a11;
  v16 = a5;
  v106 = a5;
  v17 = a13;
  v97 = a13;
  v98 = 0;
  WORD1(v104) = 0;
  *(_QWORD *)((char *)&v104 + 4) = -1;
  HIDWORD(v104) = 0;
  v18 = 0;
  v19 = 0;
  v95 = 0;
  if ( a10 )
    *((_DWORD *)a11 + 1155) = 1;
  if ( a5 )
    *a5 = 0;
  v20 = a6 - 1;
  v99 = a6 - 1;
  if ( a2 <= 0 )
    goto LABEL_118;
  _mm_lfence();
  v103 = 0;
  while ( 1 )
  {
    if ( !a3 && v16 )
    {
      if ( v19 >= v20 )
        goto LABEL_132;
      v16[v19++] = v14[v18];
      v95 = v19;
    }
    if ( !v17 || (v21 = &v14[v18], *v21 != 37) )
    {
      ++v18;
      goto LABEL_117;
    }
    if ( v18 + 1 >= a2 || v14[v18 + 1] != 37 )
      break;
    if ( a3 || !v16 )
      goto LABEL_20;
    v22 = v19 + 1;
    if ( v19 + 1 <= v20 )
    {
      v16[v19++] = 37;
      v95 = v22;
LABEL_20:
      v18 += 2;
      goto LABEL_117;
    }
    v95 = --v19;
    v18 += 2;
LABEL_117:
    if ( v18 >= a2 )
      goto LABEL_118;
  }
  v105 = CFormatSpec::CwchParseFormatSpec((CFormatSpec *)&v104, &v14[v18], a2 - v18, a7) + v18;
  v23 = HIDWORD(v104);
  v24 = HIDWORD(v104);
  if ( !HIDWORD(v104) )
  {
    if ( !a8 )
    {
      _mm_lfence();
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v117 = 0;
      ErrorReportingManager = GetErrorReportingManager();
      IErrorReportingManager::CwchCallFormatAndPrint(
        ErrorReportingManager,
        (struct SQLError *)&si128,
        2,
        1u,
        0,
        0,
        0,
        (void *)0xFFFFFFFFFFFFFFFFLL,
        3u,
        0,
        2LL * (a2 - v18),
        v21);
    }
    return 0;
  }
  v25 = v98;
  v100 = v98;
  v26 = WORD1(v104);
  v27 = BYTE2(v104);
  v28 = (WORD1(v104) >> 5) & 1;
  if ( !v28 )
  {
    v29 = v97;
    v31 = v103;
    goto LABEL_33;
  }
  if ( (unsigned int)FMaxArgCount(v98, a8) )
    return 0;
  if ( a12 && (unsigned int)(*((_DWORD *)a12 + v103) - 2) > 1 )
  {
    if ( !a8 )
    {
      v112 = _mm_load_si128((const __m128i *)&_xmm);
      v113 = 0;
      v72 = GetErrorReportingManager();
      IErrorReportingManager::CwchCallFormatAndPrint(
        v72,
        (struct SQLError *)&v112,
        2,
        1u,
        0,
        0,
        0,
        (void *)0xFFFFFFFFFFFFFFFFLL,
        3u,
        0,
        v98 + 1);
      return 0;
    }
    return 0;
  }
  v29 = v97 + 8;
  v97 = v29;
  v30 = *((_DWORD *)v29 - 2);
  if ( (v23 == 7 || v23 == 1) && v27 >= 0 && !a9 )
    v30 *= 2;
  DWORD1(v104) = v30;
  v25 = ++v98;
  v31 = ++v103;
LABEL_33:
  v32 = (v26 >> 6) & 1;
  if ( !v32 )
  {
    LODWORD(v33) = DWORD2(v104);
    goto LABEL_44;
  }
  if ( (unsigned int)FMaxArgCount(v25, a8) )
    return 0;
  if ( a12 && (unsigned int)(*((_DWORD *)a12 + v31) - 2) > 1 )
  {
    if ( !a8 )
    {
      v114 = _mm_load_si128((const __m128i *)&_xmm);
      v115 = 0;
      v74 = GetErrorReportingManager();
      IErrorReportingManager::CwchCallFormatAndPrint(
        v74,
        (struct SQLError *)&v114,
        2,
        1u,
        0,
        0,
        0,
        (void *)0xFFFFFFFFFFFFFFFFLL,
        3u,
        0,
        v98 + 1);
      return 0;
    }
    return 0;
  }
  v29 += 8;
  v97 = v29;
  LODWORD(v33) = *((_DWORD *)v29 - 2);
  if ( (v23 == 7 || v23 == 1) && v27 >= 0 && !a9 )
    LODWORD(v33) = 2 * v33;
  DWORD2(v104) = v33;
  v25 = ++v98;
  ++v103;
LABEL_44:
  if ( (unsigned int)FMaxArgCount(v25, a8) )
    return 0;
  if ( a12 )
  {
    if ( *((_DWORD *)a12 + v103) == 18 )
      v24 = 18;
    if ( !(unsigned int)FVerifyType(a12, v24, v98, a8) )
      return 0;
  }
  if ( v32 || v28 )
  {
    v34 = v100;
  }
  else
  {
    v34 = v98;
    v100 = v98;
  }
  switch ( v24 )
  {
    case 1u:
      v97 = v29 + 8;
      v121 = v104;
      v15 = a11;
      CFormattedParams::AddParam(a11, &v121, v34, *(unsigned __int16 *)v29);
      goto LABEL_100;
    case 2u:
      v97 = v29 + 8;
      v122 = v104;
      v15 = a11;
      CFormattedParams::AddParam(a11, &v122, v34, (unsigned int)*(__int16 *)v29);
      goto LABEL_100;
    case 3u:
      v97 = v29 + 8;
      v123 = v104;
      v15 = a11;
      CFormattedParams::AddParam(a11, &v123, v34, *(unsigned int *)v29);
      goto LABEL_100;
    case 4u:
      v97 = v29 + 8;
      v124 = v104;
      v15 = a11;
      CFormattedParams::AddParam(a11, &v124, v34, *(_QWORD *)v29);
      goto LABEL_100;
    case 5u:
    case 6u:
      v97 = v29 + 8;
      v125 = v104;
      v15 = a11;
      CFormattedParams::AddParam(a11, &v125, v34, *(_QWORD *)v29);
      goto LABEL_100;
    case 7u:
      v97 = v29 + 8;
      v35 = *(const void **)v29;
      v36 = 0;
      v109 = 0;
      if ( !a7 || !v32 || v27 < 0 )
        goto LABEL_83;
      if ( v23 == 7 || v23 == 1 )
        v33 = (unsigned __int64)(int)v33 >> 1;
      v37 = 2048;
      if ( (int)v33 < 2048 )
        v37 = v33;
      v38 = 0;
      v39 = v37;
      if ( v37 <= 0 )
        goto LABEL_83;
      _mm_lfence();
      v36 = v109;
      break;
    case 8u:
      v97 = v29 + 8;
      v127[0] = v104;
      v15 = a11;
      CFormattedParams::AddParam(a11, v127, v34, *(_QWORD *)v29);
      goto LABEL_100;
    case 9u:
      v97 = v29 + 8;
      v94[0] = *(__int16 *)(*(_QWORD *)v29 + 6LL);
      LODWORD(Locale) = **(_DWORD **)v29;
      v15 = a11;
      CFormattedParams::AddParam(
        a11,
        L"Rid pageid is (%d:%d) and row num is 0x%x",
        v34,
        *(unsigned __int16 *)(*(_QWORD *)v29 + 4LL),
        Locale,
        *(_QWORD *)v94);
      goto LABEL_100;
    case 0xAu:
      v97 = v29 + 8;
      v15 = a11;
      CFormattedParams::AddParam(a11, L"BUF not supported in BrickSim", v34);
      goto LABEL_100;
    case 0xBu:
      v97 = v29 + 8;
      v15 = a11;
      CFormattedParams::AddParam(
        a11,
        L"Page pointer = 0x%lx, PageId = (%d:%d), flags = 0x%X, objectid = %ld, indexid = %d",
        v34);
      goto LABEL_100;
    case 0xCu:
      v97 = v29 + 8;
      v15 = a11;
      CFormattedParams::AddParam(a11, L"SQLDATE not supported in BrickSim", v34);
      goto LABEL_100;
    case 0xDu:
      v97 = v29 + 8;
      v44 = *(_DWORD *)v29;
      v45 = GetErrorReportingManager();
      v15 = a11;
      (*(void (__fastcall **)(struct IErrorReportingManager *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v45 + 16LL))(
        v45,
        v44,
        *((_QWORD *)a11 + 525),
        *((_DWORD *)a11 + 1052) - (unsigned int)((__int64)(*((_QWORD *)a11 + 525) - (_QWORD)a11) >> 1) + 2048,
        0);
      CFormattedParams::FinalizeParam(a11, 0, v100);
      goto LABEL_100;
    case 0xEu:
      v46 = v29 + 8;
      v47 = *((_QWORD *)v46 - 1);
      v48 = *(unsigned __int16 *)(v47 + 4);
      LODWORD(Locale) = *(_DWORD *)v47;
      goto LABEL_91;
    case 0xFu:
      v97 = v29 + 8;
      v49 = *(_DWORD **)v29;
      v111 = **(_QWORD **)v29;
      v94[0] = *((unsigned __int16 *)v49 + 4);
      LODWORD(Locale) = HIDWORD(v111);
      v15 = a11;
      CFormattedParams::AddParam(a11, L"(%d:%d:%d)", v34, (unsigned int)v111, Locale, *(_QWORD *)v94);
      goto LABEL_100;
    case 0x10u:
      v46 = v29 + 8;
      v50 = *((_QWORD *)v46 - 1);
      v48 = *(unsigned __int16 *)(v50 + 4);
      LODWORD(Locale) = *(_DWORD *)v50;
LABEL_91:
      v97 = v46;
      v15 = a11;
      CFormattedParams::AddParam(a11, L"(%d:%d)", v34, v48, Locale);
      goto LABEL_100;
    case 0x11u:
      v97 = v29 + 8;
      v51 = *(_DWORD **)v29;
      v15 = a11;
      v52 = *((_DWORD *)a11 + 1052) - ((__int64)(*((_QWORD *)a11 + 525) - (_QWORD)a11) >> 1) + 2048;
      DefaultLocale = GetDefaultLocale();
      v54 = StringCchPrintf_lW(*((wchar_t **)a11 + 525), v52, L"0x", DefaultLocale);
      v55 = 0;
      for ( i = 2; !v54; i += 2 )
      {
        if ( v55 >= 8 )
          break;
        v57 = *((unsigned __int8 *)v51 + v55);
        v58 = *((_DWORD *)a11 + 1052) - ((__int64)(*((_QWORD *)a11 + 525) - (_QWORD)a11) >> 1) + 2048;
        v59 = GetDefaultLocale();
        LODWORD(Locale) = v57;
        v54 = StringCchPrintf_lW((wchar_t *)(*((_QWORD *)a11 + 525) + 2LL * i), v58 - i, L"%02x", v59, Locale);
        ++v55;
      }
      CFormattedParams::FinalizeParam(a11, v54, v100);
      goto LABEL_100;
    case 0x12u:
      v15 = a11;
      CFormattedParams::AddParam(a11, L"(null)", v34);
      v97 = v29 + 8;
      goto LABEL_100;
    default:
      v15 = a11;
      goto LABEL_100;
  }
  do
  {
    if ( !*((_WORD *)v35 + v38) )
    {
      if ( !v36 )
      {
        v40 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v41 = *(_QWORD *)(v40 + 256);
        if ( !v41 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v41 = *(_QWORD *)(v40 + 256);
        }
        v42 = 2 * v39;
        if ( !is_mul_ok(v39, 2u) )
          v42 = -1;
        v36 = operator new[](
                v42,
                *(struct IMemObj **)(v41 + 1000),
                1,
                "Sql\\Ntdbms\\msql\\utils\\errorreportutils.cpp",
                1256,
                6u);
        if ( !v36 )
        {
          v109 = 0;
          _mm_lfence();
          operator delete[]((void *)(unsigned __int8)v109);
          return 0;
        }
        operator delete[](0);
        v109 = v36;
        v43 = 2 * v39;
        if ( 2 * v39 )
        {
          if ( v35 )
          {
            memmove(v36, v35, v43);
          }
          else
          {
            memset_0(v36, 0, v43);
            *_errno() = 22;
            _invalid_parameter_noinfo();
          }
        }
        v35 = v36;
      }
      *((_WORD *)v35 + v38) = 46;
    }
    ++v38;
  }
  while ( v38 < v39 );
LABEL_83:
  v126 = v104;
  v15 = a11;
  CFormattedParams::AddParam(a11, &v126, v100, v35);
  operator delete[](v36);
LABEL_100:
  ++v98;
  ++v103;
  a3 = v108;
  v16 = v106;
  if ( v108 || !v106 )
  {
    v19 = v95;
LABEL_116:
    v17 = v97;
    v18 = v105;
    v14 = v110;
    v20 = a6 - 1;
    goto LABEL_117;
  }
  v60 = *((_DWORD *)v15 + 1052);
  if ( v60 >= 10 )
  {
    if ( v60 >= 100 )
      v61 = (v60 >= 1000) + 3;
    else
      v61 = 2;
  }
  else
  {
    v61 = (_DWORD)v108 + 1;
  }
  v20 = a6 - 1;
  if ( v95 + v61 + 3 <= v99 )
  {
    _mm_lfence();
    v62 = *((_DWORD *)v15 + 1052);
    if ( v62 >= 10 )
    {
      if ( v62 >= 100 )
        v63 = (v62 >= 1000) + 3LL;
      else
        v63 = 2;
    }
    else
    {
      v63 = 1;
    }
    v64 = GetDefaultLocale();
    v94[0] = v62;
    v19 = snwprintf_s_l(&v106[v95], v99 - v95, v63 + 3, L"%d!s!", v64, *(_QWORD *)v94) + v95;
    v95 = v19;
    a3 = v108;
    v16 = v106;
    goto LABEL_116;
  }
  --v95;
LABEL_132:
  *((_DWORD *)v15 + 1154) = 1;
LABEL_118:
  v65 = 1;
  if ( a3 )
  {
    v66 = 0;
    v67 = 0;
    memset(&v127[1], 0, 80);
    v68 = v107;
    v69 = 0;
    while ( 1 )
    {
      v65 = 1;
      if ( v66 >= v20 || v69 >= v68 )
        break;
      v16[v66++] = a3[v69];
      v96 = v66;
      v70 = a3[v69];
      ++v67;
      ++v69;
      if ( v70 == 37 )
      {
        v71 = v67;
        v102 = v67;
        if ( v69 < v68 && a3[v69] == 37 )
        {
          v16[v66++] = 37;
          ++v67;
          ++v69;
        }
        else
        {
          v76 = 0;
          v77 = 0;
          v78 = 0;
          if ( v69 < v68 )
          {
            v79 = v108;
            do
            {
              if ( v78 )
                break;
              v80 = GetDefaultLocale();
              if ( !_iswdigit_l(v79[v69], v80) )
                break;
              v77 = 1;
              v81 = v79[v69];
              v78 = v76 > (-2147483601 - v81) / 10;
              ++v67;
              ++v69;
              v76 = v81 + 2 * (5 * v76 - 24);
            }
            while ( v69 < v68 );
            v71 = v102;
            a3 = v108;
            v20 = a6 - 1;
          }
          v82 = -1;
          if ( v77 )
            v82 = v76;
          if ( v78 || v82 > 20 || v82 == -1 )
            goto LABEL_169;
          v83 = 0;
          v84 = 0;
          do
          {
            if ( v84 >= 50 )
              break;
            v85 = v84++;
            if ( *((_BYTE *)a11 + v85 + 4624) == (_BYTE)v82 )
              v83 = v84;
          }
          while ( !v83 );
          if ( v82 < 1 || *((_DWORD *)v127 + v82 + 3) || v83 < 1 || v69 < v68 && a3[v69] != 33 )
          {
LABEL_169:
            v66 = v96;
LABEL_170:
            v65 = 0;
            if ( !a8 )
            {
              v118 = _mm_load_si128((const __m128i *)&_xmm);
              v119 = 0;
              v89 = &a3[v71];
              v90 = 2LL * (v107 - v71);
              v91 = GetErrorReportingManager();
              IErrorReportingManager::CwchCallFormatAndPrint(
                v91,
                (struct SQLError *)&v118,
                2,
                1u,
                0,
                0,
                0,
                (void *)0xFFFFFFFFFFFFFFFFLL,
                3u,
                0,
                v90,
                v89);
              v65 = 0;
            }
            break;
          }
          *((_DWORD *)v127 + v82 + 3) = 1;
          if ( v83 >= 10 )
          {
            if ( v83 >= 100 )
              v86 = (v83 >= 1000) + 3;
            else
              v86 = 2;
          }
          else
          {
            v86 = 1;
          }
          v66 = v96;
          if ( v96 + v86 + 3 >= v20 )
            goto LABEL_170;
          _mm_lfence();
          if ( v83 >= 10 )
          {
            if ( v83 >= 100 )
              v87 = (v83 >= 1000) + 3LL;
            else
              v87 = 2;
          }
          else
          {
            v87 = 1;
          }
          v88 = GetDefaultLocale();
          v94[0] = v83;
          v66 = snwprintf_s_l(&v106[v96], v99 - v96, v87 + 3, L"%d!s!", v88, *(_QWORD *)v94) + v96;
          ++v67;
          ++v69;
          a3 = v108;
          v16 = v106;
          v20 = a6 - 1;
        }
      }
    }
  }
  else
  {
    v66 = v95;
  }
  v92 = v106;
  if ( v106 )
  {
    if ( v66 >= a6 )
      utassert_fail(1u, "iFinalMsgPos < cwchMaxFinalMsgLen + 1", "ErrorReportUtils.cpp", 1421, 0);
    v92[v66] = 0;
  }
  return v65;
}

```

## disassembly

```asm
0x1004168e0  push    rbp
0x1004168e2  push    rbx
0x1004168e3  push    rsi
0x1004168e4  push    rdi
0x1004168e5  push    r12
0x1004168e7  push    r13
0x1004168e9  push    r14
0x1004168eb  push    r15
0x1004168ed  lea     rbp, [rsp-138h]
0x1004168f5  sub     rsp, 238h
0x1004168fc  mov     [rbp+170h+var_120], 0FFFFFFFFFFFFFFFEh
0x100416904  mov     rax, cs:__security_cookie
0x10041690b  xor     rax, rsp
0x10041690e  mov     [rbp+170h+var_50], rax
0x100416915  mov     [rbp+170h+var_1B0], r9d
0x100416919  mov     [rbp+170h+var_1A8], r8
0x10041691d  mov     eax, edx
0x10041691f  mov     [rbp+170h+var_1E8], edx
0x100416922  mov     r10, rcx
0x100416925  mov     [rbp+170h+var_198], rcx
0x100416929  mov     r13, [rbp+170h+arg_50]
0x100416930  mov     [rsp+270h+var_1F8], r13
0x100416935  mov     r9, [rbp+170h+arg_20]
0x10041693c  mov     [rbp+170h+var_1B8], r9
0x100416940  mov     ecx, [rbp+170h+arg_28]
0x100416946  mov     rdx, [rbp+170h+arg_60]
0x10041694d  mov     [rsp+270h+var_208], rdx
0x100416952  xor     r15d, r15d
0x100416955  mov     [rsp+270h+var_200], r15d
0x10041695a  mov     word ptr [rbp+170h+var_1D0+2], r15w
0x10041695f  mov     qword ptr [rbp+170h+var_1D0+4], 0FFFFFFFFFFFFFFFFh
0x100416967  mov     dword ptr [rbp+170h+var_1D0+0Ch], r15d
0x10041696b  mov     r14d, r15d
0x10041696e  mov     esi, r15d
0x100416971  mov     [rsp+270h+var_210], r15d
0x100416976  cmp     [rbp+170h+arg_48], r15d
0x10041697d  jz      short loc_10041698A
0x10041697f  mov     dword ptr [r13+120Ch], 1
0x10041698a  test    r9, r9
0x10041698d  jz      short loc_100416993
0x10041698f  mov     [r9], r15w
0x100416993  lea     r11d, [rcx-1]
0x100416997  mov     [rbp+170h+var_1F0], r11d
0x10041699b  test    eax, eax
0x10041699d  jle     loc_100417269
0x1004169a3  lfence
0x1004169a6  mov     [rbp+170h+var_1E0], r15
0x1004169aa  nop     word ptr [rax+rax+00h]
0x1004169b0  test    r8, r8
0x1004169b3  jnz     short loc_1004169D9
0x1004169b5  test    r9, r9
0x1004169b8  jz      short loc_1004169D9
0x1004169ba  cmp     esi, r11d
0x1004169bd  jge     loc_10041741C
0x1004169c3  movsxd  rax, r14d
0x1004169c6  movsxd  rcx, esi
0x1004169c9  movzx   eax, word ptr [r10+rax*2]
0x1004169ce  mov     [r9+rcx*2], ax
0x1004169d3  inc     esi
0x1004169d5  mov     [rsp+270h+var_210], esi
0x1004169d9  test    rdx, rdx
0x1004169dc  jz      loc_100417245
0x1004169e2  movsxd  rcx, r14d
0x1004169e5  lea     rdi, [r10+rcx*2]
0x1004169e9  cmp     word ptr [rdi], 25h ; '%'
0x1004169ed  jnz     loc_100417245
0x1004169f3  lea     eax, [r14+1]
0x1004169f7  mov     ebx, [rbp+170h+var_1E8]
0x1004169fa  cmp     eax, ebx
0x1004169fc  jge     short loc_100416A44
0x1004169fe  cmp     word ptr [r10+rcx*2+2], 25h ; '%'
0x100416a05  jnz     short loc_100416A44
0x100416a07  test    r8, r8
0x100416a0a  jnz     short loc_100416A3B
0x100416a0c  test    r9, r9
0x100416a0f  jz      short loc_100416A3B
0x100416a11  lea     ecx, [rsi+1]
0x100416a14  cmp     ecx, r11d
0x100416a17  jle     short loc_100416A28
0x100416a19  dec     esi
0x100416a1b  mov     [rsp+270h+var_210], esi
0x100416a1f  add     r14d, 2
0x100416a23  jmp     loc_10041725F
0x100416a28  movsxd  rax, esi
0x100416a2b  mov     ebx, 25h ; '%'
0x100416a30  mov     [r9+rax*2], bx
0x100416a35  mov     esi, ecx
0x100416a37  mov     [rsp+270h+var_210], ecx
0x100416a3b  add     r14d, 2
0x100416a3f  jmp     loc_10041725F
0x100416a44  sub     ebx, r14d
0x100416a47  mov     r9d, [rbp+170h+arg_30]; int
0x100416a4e  mov     r8d, ebx; int
0x100416a51  mov     rdx, rdi; wchar_t *
0x100416a54  lea     rcx, [rbp+170h+var_1D0]; this
0x100416a58  call    ?CwchParseFormatSpec@CFormatSpec@@QEAAHPEB_WHH@Z; CFormatSpec::CwchParseFormatSpec(wchar_t const *,int,int)
0x100416a5d  add     r14d, eax
0x100416a60  mov     [rbp+170h+var_1C0], r14d
0x100416a64  mov     r15d, dword ptr [rbp+170h+var_1D0+0Ch]
0x100416a68  mov     r13d, r15d
0x100416a6b  test    r15d, r15d
0x100416a6e  jz      loc_10041742C
0x100416a74  mov     eax, [rsp+270h+var_200]
0x100416a78  mov     [rbp+170h+var_1EC], eax
0x100416a7b  movzx   r14d, word ptr [rbp+170h+var_1D0+2]
0x100416a80  movzx   ebx, r14w
0x100416a84  shr     bx, 5
0x100416a88  movzx   r12d, r14b
0x100416a8c  and     bx, 1
0x100416a90  jz      short loc_100416B0B
0x100416a92  mov     edi, [rbp+170h+arg_38]
0x100416a98  mov     edx, edi; int
0x100416a9a  mov     ecx, eax; int
0x100416a9c  call    ?FMaxArgCount@@YAHHH@Z; FMaxArgCount(int,int)
0x100416aa1  test    eax, eax
0x100416aa3  jnz     loc_10041749C
0x100416aa9  mov     rax, [rbp+170h+arg_58]
0x100416ab0  mov     rsi, [rbp+170h+var_1E0]
0x100416ab4  test    rax, rax
0x100416ab7  jz      short loc_100416AC8
0x100416ab9  mov     eax, [rax+rsi*4]
0x100416abc  sub     eax, 2
0x100416abf  cmp     eax, 1
0x100416ac2  ja      loc_10041731F
0x100416ac8  mov     rdi, [rsp+270h+var_208]
0x100416acd  add     rdi, 8
0x100416ad1  mov     [rsp+270h+var_208], rdi
0x100416ad6  mov     eax, [rdi-8]
0x100416ad9  cmp     r15d, 7
0x100416add  jz      short loc_100416AE5
0x100416adf  cmp     r15d, 1
0x100416ae3  jnz     short loc_100416AF5
0x100416ae5  test    r12b, r12b
0x100416ae8  js      short loc_100416AF5
0x100416aea  cmp     [rbp+170h+arg_40], 0
0x100416af1  jnz     short loc_100416AF5
0x100416af3  add     eax, eax
0x100416af5  mov     dword ptr [rbp+170h+var_1D0+4], eax
0x100416af8  mov     eax, [rsp+270h+var_200]
0x100416afc  inc     eax
0x100416afe  mov     [rsp+270h+var_200], eax
0x100416b02  inc     rsi
0x100416b05  mov     [rbp+170h+var_1E0], rsi
0x100416b09  jmp     short loc_100416B14
0x100416b0b  mov     rdi, [rsp+270h+var_208]
0x100416b10  mov     rsi, [rbp+170h+var_1E0]
0x100416b14  shr     r14w, 6
0x100416b19  and     r14w, 1
0x100416b1e  jz      short loc_100416B8B
0x100416b20  mov     edx, [rbp+170h+arg_38]; int
0x100416b26  mov     ecx, eax; int
0x100416b28  call    ?FMaxArgCount@@YAHHH@Z; FMaxArgCount(int,int)
0x100416b2d  test    eax, eax
0x100416b2f  jnz     loc_10041749C
0x100416b35  mov     rax, [rbp+170h+arg_58]
0x100416b3c  test    rax, rax
0x100416b3f  jz      short loc_100416B50
0x100416b41  mov     eax, [rax+rsi*4]
0x100416b44  sub     eax, 2
0x100416b47  cmp     eax, 1
0x100416b4a  ja      loc_10041738C
0x100416b50  add     rdi, 8
0x100416b54  mov     [rsp+270h+var_208], rdi
0x100416b59  mov     esi, [rdi-8]
0x100416b5c  cmp     r15d, 7
0x100416b60  jz      short loc_100416B68
0x100416b62  cmp     r15d, 1
0x100416b66  jnz     short loc_100416B78
0x100416b68  test    r12b, r12b
0x100416b6b  js      short loc_100416B78
0x100416b6d  cmp     [rbp+170h+arg_40], 0
0x100416b74  jnz     short loc_100416B78
0x100416b76  add     esi, esi
0x100416b78  mov     dword ptr [rbp+170h+var_1D0+8], esi
0x100416b7b  mov     eax, [rsp+270h+var_200]
0x100416b7f  inc     eax
0x100416b81  mov     [rsp+270h+var_200], eax
0x100416b85  inc     [rbp+170h+var_1E0]
0x100416b89  jmp     short loc_100416B8E
0x100416b8b  mov     esi, dword ptr [rbp+170h+var_1D0+8]
0x100416b8e  mov     edx, [rbp+170h+arg_38]; int
0x100416b94  mov     ecx, eax; int
0x100416b96  call    ?FMaxArgCount@@YAHHH@Z; FMaxArgCount(int,int)
0x100416b9b  test    eax, eax
0x100416b9d  jnz     loc_10041749C
0x100416ba3  mov     rcx, [rbp+170h+arg_58]
0x100416baa  test    rcx, rcx
0x100416bad  jz      short loc_100416BDC
0x100416baf  mov     rax, [rbp+170h+var_1E0]
0x100416bb3  cmp     dword ptr [rcx+rax*4], 12h
0x100416bb7  mov     eax, 12h
0x100416bbc  cmovz   r13d, eax
0x100416bc0  mov     r9d, [rbp+170h+arg_38]
0x100416bc7  mov     r8d, [rsp+270h+var_200]
0x100416bcc  mov     edx, r13d
0x100416bcf  call    ?FVerifyType@@YAHPEBW4EFormatType@@W41@HH@Z; FVerifyType(EFormatType const *,EFormatType,int,int)
0x100416bd4  test    eax, eax
0x100416bd6  jz      loc_10041749C
0x100416bdc  test    r14w, r14w
0x100416be0  jnz     short loc_100416BF2
0x100416be2  test    bx, bx
0x100416be5  jnz     short loc_100416BF2
0x100416be7  mov     r8d, [rsp+270h+var_200]
0x100416bec  mov     [rbp+170h+var_1EC], r8d
0x100416bf0  jmp     short loc_100416BF6
0x100416bf2  mov     r8d, [rbp+170h+var_1EC]; int
0x100416bf6  lea     eax, [r13-1]; switch 18 cases
0x100416bfa  cmp     eax, 11h
0x100416bfd  ja      def_100416C16; jumptable 0000000100416C16 default case
0x100416c03  cdqe
0x100416c05  lea     rbx, cs:100400000h
0x100416c0c  mov     ecx, ds:(jpt_100416C16 - 100400000h)[rbx+rax*4]
0x100416c13  add     rcx, rbx
0x100416c16  jmp     rcx; switch jump
0x100416c18  add     rdi, 8; jumptable 0000000100416C16 case 1
0x100416c1c  mov     [rsp+270h+var_208], rdi
0x100416c21  movaps  xmm0, [rbp+170h+var_1D0]
0x100416c25  movdqa  [rbp+170h+var_110], xmm0
0x100416c2a  movzx   r9d, word ptr [rdi-8]
0x100416c2f  lea     rdx, [rbp+170h+var_110]
0x100416c33  mov     r13, [rsp+270h+var_1F8]
0x100416c38  mov     rcx, r13
0x100416c3b  call    ?AddParam@CFormattedParams@@QEAAXVCFormatSpec@@HZZ; CFormattedParams::AddParam(CFormatSpec,int,...)
0x100416c40  jmp     loc_10041716B
0x100416c45  add     rdi, 8; jumptable 0000000100416C16 case 2
0x100416c49  mov     [rsp+270h+var_208], rdi
0x100416c4e  movaps  xmm0, [rbp+170h+var_1D0]
0x100416c52  movdqa  [rbp+170h+var_100], xmm0
0x100416c57  movsx   r9d, word ptr [rdi-8]
0x100416c5c  lea     rdx, [rbp+170h+var_100]
0x100416c60  mov     r13, [rsp+270h+var_1F8]
0x100416c65  mov     rcx, r13
0x100416c68  call    ?AddParam@CFormattedParams@@QEAAXVCFormatSpec@@HZZ; CFormattedParams::AddParam(CFormatSpec,int,...)
0x100416c6d  jmp     loc_10041716B
0x100416c72  add     rdi, 8; jumptable 0000000100416C16 case 3
0x100416c76  mov     [rsp+270h+var_208], rdi
0x100416c7b  movaps  xmm0, [rbp+170h+var_1D0]
0x100416c7f  movdqa  [rbp+170h+var_F0], xmm0
0x100416c87  mov     r9d, [rdi-8]
0x100416c8b  lea     rdx, [rbp+170h+var_F0]
0x100416c92  mov     r13, [rsp+270h+var_1F8]
0x100416c97  mov     rcx, r13
0x100416c9a  call    ?AddParam@CFormattedParams@@QEAAXVCFormatSpec@@HZZ; CFormattedParams::AddParam(CFormatSpec,int,...)
0x100416c9f  jmp     loc_10041716B
0x100416ca4  add     rdi, 8; jumptable 0000000100416C16 case 4
0x100416ca8  mov     [rsp+270h+var_208], rdi
0x100416cad  movaps  xmm0, [rbp+170h+var_1D0]
0x100416cb1  movdqa  [rbp+170h+var_E0], xmm0
0x100416cb9  mov     r9, [rdi-8]
0x100416cbd  lea     rdx, [rbp+170h+var_E0]
0x100416cc4  mov     r13, [rsp+270h+var_1F8]
0x100416cc9  mov     rcx, r13
0x100416ccc  call    ?AddParam@CFormattedParams@@QEAAXVCFormatSpec@@HZZ; CFormattedParams::AddParam(CFormatSpec,int,...)
0x100416cd1  jmp     loc_10041716B
0x100416cd6  add     rdi, 8; jumptable 0000000100416C16 cases 5,6
0x100416cda  mov     [rsp+270h+var_208], rdi
0x100416cdf  movaps  xmm0, [rbp+170h+var_1D0]
0x100416ce3  movdqa  [rbp+170h+var_D0], xmm0
0x100416ceb  movsd   xmm3, qword ptr [rdi-8]
0x100416cf0  movq    r9, xmm3
0x100416cf5  lea     rdx, [rbp+170h+var_D0]
0x100416cfc  mov     r13, [rsp+270h+var_1F8]
0x100416d01  mov     rcx, r13
0x100416d04  call    ?AddParam@CFormattedParams@@QEAAXVCFormatSpec@@HZZ; CFormattedParams::AddParam(CFormatSpec,int,...)
0x100416d09  jmp     loc_10041716B
0x100416d0e  add     rdi, 8; jumptable 0000000100416C16 case 7
0x100416d12  mov     [rsp+270h+var_208], rdi
0x100416d17  mov     rdi, [rdi-8]
0x100416d1b  xor     ecx, ecx
0x100416d1d  mov     ebx, ecx
0x100416d1f  mov     [rbp+170h+var_1A0], rcx
0x100416d23  cmp     [rbp+170h+arg_30], ecx
0x100416d29  jz      loc_100416E64
0x100416d2f  test    r14w, r14w
0x100416d33  jz      loc_100416E64
0x100416d39  test    r12b, r12b
0x100416d3c  js      loc_100416E64
0x100416d42  cmp     r15d, 7
0x100416d46  jz      short loc_100416D4E
0x100416d48  cmp     r15d, 1
0x100416d4c  jnz     short loc_100416D54
0x100416d4e  movsxd  rsi, esi
0x100416d51  shr     rsi, 1
0x100416d54  mov     eax, 800h
0x100416d59  cmp     esi, eax
0x100416d5b  cmovl   eax, esi
0x100416d5e  mov     rsi, rcx
0x100416d61  movsxd  r14, eax
0x100416d64  test    eax, eax
0x100416d66  jle     loc_100416E64
0x100416d6c  lfence
0x100416d6f  mov     rbx, [rbp+170h+var_1A0]
0x100416d73  cmp     cx, [rdi+rsi*2]
0x100416d77  jnz     loc_100416E58
0x100416d7d  test    rbx, rbx
0x100416d80  jnz     loc_100416E4F
0x100416d86  mov     rdx, gs:58h
0x100416d8f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100416d96  mov     ecx, [rax]
0x100416d98  mov     rax, cs:__imp_SystemThread_TlsOffset
  ... truncated ...
```
