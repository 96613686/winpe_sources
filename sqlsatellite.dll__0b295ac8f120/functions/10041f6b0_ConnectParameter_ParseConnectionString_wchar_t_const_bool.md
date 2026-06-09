# ConnectParameter::ParseConnectionString(wchar_t const *,bool)

- ea: `0x10041f6b0`
- end: `0x1004213f1`
- name: `?ParseConnectionString@ConnectParameter@@QEAAKPEB_W_N@Z`
- size: `7489`
- prototype: `unsigned int(ConnectParameter *__hidden this, const wchar_t *, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x100421570`

## callees

- `0x100403a10`
- `0x100403b90`
- `0x10041f610`
- `0x10041f6b0`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`

## import_xrefs

- `KERNEL32!LCMapStringW` at `0x10041f893`
- `KERNEL32!LCMapStringW` at `0x10041f893`
- `KERNEL32!CompareStringW` at `0x10041fedd`
- `KERNEL32!CompareStringW` at `0x1004201eb`
- `KERNEL32!CompareStringW` at `0x100420229`
- `KERNEL32!CompareStringW` at `0x1004202d2`
- `KERNEL32!CompareStringW` at `0x10041fedd`
- `KERNEL32!CompareStringW` at `0x1004201eb`
- `KERNEL32!CompareStringW` at `0x100420229`
- `KERNEL32!CompareStringW` at `0x1004202d2`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100420446`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100420446`
- `sqldk!??_V@YAXPEAX@Z` at `0x10042037f`
- `sqldk!??_V@YAXPEAX@Z` at `0x10042048b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004213e5`
- `sqldk!??_V@YAXPEAX@Z` at `0x10042037f`
- `sqldk!??_V@YAXPEAX@Z` at `0x10042048b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004213e5`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10041f7de`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10041f7de`
- `sqldk!SystemThread_TlsIndex` at `0x10041f773`
- `sqldk!SystemThread_TlsOffset` at `0x10041f77c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041f797`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041f797`
- `VCRUNTIME140!wcschr` at `0x10041fa2b`
- `VCRUNTIME140!wcschr` at `0x100420527`
- `VCRUNTIME140!wcschr` at `0x100420783`
- `VCRUNTIME140!wcschr` at `0x10041fa2b`
- `VCRUNTIME140!wcschr` at `0x100420527`
- `VCRUNTIME140!wcschr` at `0x100420783`
- `api-ms-win-crt-string-l1-1-0!wmemmove_s` at `0x10041f9fe`
- `api-ms-win-crt-string-l1-1-0!wmemmove_s` at `0x10041fc34`
- `api-ms-win-crt-string-l1-1-0!wmemmove_s` at `0x10041fe69`
- `api-ms-win-crt-string-l1-1-0!wmemmove_s` at `0x1004206b9`
- `api-ms-win-crt-string-l1-1-0!wmemmove_s` at `0x100420909`
- `api-ms-win-crt-string-l1-1-0!wmemmove_s` at `0x100420c84`
- `api-ms-win-crt-string-l1-1-0!wmemmove_s` at `0x100420f0c`
- `api-ms-win-crt-string-l1-1-0!wmemmove_s` at `0x10041f9fe`
- `api-ms-win-crt-string-l1-1-0!wmemmove_s` at `0x10041fc34`
- `api-ms-win-crt-string-l1-1-0!wmemmove_s` at `0x10041fe69`
- `api-ms-win-crt-string-l1-1-0!wmemmove_s` at `0x1004206b9`
- `api-ms-win-crt-string-l1-1-0!wmemmove_s` at `0x100420909`
- `api-ms-win-crt-string-l1-1-0!wmemmove_s` at `0x100420c84`
- `api-ms-win-crt-string-l1-1-0!wmemmove_s` at `0x100420f0c`
- `USER32!CharNextW` at `0x10041f8f2`
- `USER32!CharNextW` at `0x10041f917`
- `USER32!CharNextW` at `0x10041f993`
- `USER32!CharNextW` at `0x10041f9b7`
- `USER32!CharNextW` at `0x10041fb23`
- `USER32!CharNextW` at `0x10041fb48`
- `USER32!CharNextW` at `0x10041fbd3`
- `USER32!CharNextW` at `0x10041fbf7`
- `USER32!CharNextW` at `0x10041fd53`
- `USER32!CharNextW` at `0x10041fd78`
- `USER32!CharNextW` at `0x10041fe03`
- `USER32!CharNextW` at `0x10041fe27`
- `USER32!CharNextW` at `0x100420008`
- `USER32!CharNextW` at `0x100420185`
- `USER32!CharNextW` at `0x100420275`
- `USER32!CharNextW` at `0x100420306`
- `USER32!CharNextW` at `0x1004205a3`
- `USER32!CharNextW` at `0x1004205c8`
- `USER32!CharNextW` at `0x100420653`
- `USER32!CharNextW` at `0x100420677`
- `USER32!CharNextW` at `0x1004207f3`
- `USER32!CharNextW` at `0x100420818`
- `USER32!CharNextW` at `0x1004208a3`
- `USER32!CharNextW` at `0x1004208c7`
- `USER32!CharNextW` at `0x1004209d3`
- `USER32!CharNextW` at `0x100420a97`
- `USER32!CharNextW` at `0x100420b73`
- `USER32!CharNextW` at `0x100420b98`
- `USER32!CharNextW` at `0x100420c23`
- `USER32!CharNextW` at `0x100420c47`
- `USER32!CharNextW` at `0x100420df3`
- `USER32!CharNextW` at `0x100420e18`
- `USER32!CharNextW` at `0x100420ea4`
- `USER32!CharNextW` at `0x100420ec8`
- `USER32!CharNextW` at `0x10041f8f2`
- `USER32!CharNextW` at `0x10041f917`
- `USER32!CharNextW` at `0x10041f993`
- `USER32!CharNextW` at `0x10041f9b7`
- `USER32!CharNextW` at `0x10041fb23`
- `USER32!CharNextW` at `0x10041fb48`
- `USER32!CharNextW` at `0x10041fbd3`
- `USER32!CharNextW` at `0x10041fbf7`
- `USER32!CharNextW` at `0x10041fd53`
- `USER32!CharNextW` at `0x10041fd78`
- `USER32!CharNextW` at `0x10041fe03`
- `USER32!CharNextW` at `0x10041fe27`
- `USER32!CharNextW` at `0x100420008`
- `USER32!CharNextW` at `0x100420185`
- `USER32!CharNextW` at `0x100420275`
- `USER32!CharNextW` at `0x100420306`
- `USER32!CharNextW` at `0x1004205a3`
- `USER32!CharNextW` at `0x1004205c8`
- `USER32!CharNextW` at `0x100420653`
- `USER32!CharNextW` at `0x100420677`
- `USER32!CharNextW` at `0x1004207f3`
- `USER32!CharNextW` at `0x100420818`
- `USER32!CharNextW` at `0x1004208a3`
- `USER32!CharNextW` at `0x1004208c7`
- `USER32!CharNextW` at `0x1004209d3`
- `USER32!CharNextW` at `0x100420a97`
- `USER32!CharNextW` at `0x100420b73`
- `USER32!CharNextW` at `0x100420b98`
- `USER32!CharNextW` at `0x100420c23`
- `USER32!CharNextW` at `0x100420c47`
- `USER32!CharNextW` at `0x100420df3`
- `USER32!CharNextW` at `0x100420e18`
- `USER32!CharNextW` at `0x100420ea4`
- `USER32!CharNextW` at `0x100420ec8`

## string_xrefs

- `0x10041f6e3`: `sql\common\dk\sni\include\open.hpp`
- `0x10041f826`: `sql\common\dk\sni\include\open.hpp`
- `0x10041f869`: `sql\common\dk\sni\include\open.hpp`
- `0x1004203bb`: `sql\common\dk\sni\include\open.hpp`
- `0x1004203fa`: `sql\common\dk\sni\include\open.hpp`
- `0x10042041d`: `sql\common\dk\sni\include\open.hpp`
- `0x10042050b`: `sql\common\dk\sni\include\open.hpp`
- `0x1004210f6`: `sql\common\dk\sni\include\open.hpp`
- `0x1004212ea`: `sql\common\dk\sni\include\open.hpp`
- `0x100421383`: `sql\common\dk\sni\include\open.hpp`
- `0x1004213c2`: `sql\common\dk\sni\include\open.hpp`
- `0x10042136f`: `ERR|SNIStringCchCopy failed: %d{HRESULT}.\n`
- `0x1004204f7`: `SNIm_wszProtocolName: '%s', m_wszServerName: '%s', m_wszInstanceName: '%s', m_wszProtocolParameter: '%s', m_wszAlias: '%hs', m_fCanUseCache: %d{bool}, m_fStandardInstName: %d{bool}, m_wszOriginalServerName: '%s'\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConnectParameter::ParseConnectionString(ConnectParameter *this, const wchar_t *a2, char a3)
{
  ConnectParameter *v5; // rbp
  bool v6; // al
  __int64 v7; // r12
  __int64 v8; // rbx
  __int64 v9; // rsi
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned __int64 v12; // rsi
  rsize_t v13; // r15
  unsigned __int64 v14; // rax
  WCHAR *v15; // rax
  LPWSTR v16; // r14
  unsigned int v17; // ebx
  const wchar_t *v18; // r9
  unsigned int v19; // eax
  __int64 v20; // rax
  const wchar_t *v21; // rbx
  WCHAR v22; // di
  WCHAR *v23; // rsi
  const WCHAR *v24; // rcx
  int v25; // ebx
  LPWSTR v26; // rax
  __int64 v27; // rax
  rsize_t v28; // rbp
  LPWSTR v29; // rax
  const WCHAR *v30; // rsi
  WCHAR v31; // di
  const WCHAR *v32; // rcx
  int v33; // ebx
  LPWSTR v34; // rax
  __int64 v35; // rax
  unsigned __int64 v36; // rax
  rsize_t v37; // rbx
  wchar_t *v38; // rax
  wchar_t *v39; // r13
  __int64 v40; // rdi
  wchar_t *v41; // r12
  __int64 v42; // rdx
  _WORD *v43; // rcx
  __int16 v44; // ax
  _WORD *v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  rsize_t v48; // r15
  WCHAR v49; // di
  const WCHAR *v50; // r14
  const WCHAR *v51; // rsi
  const WCHAR *v52; // rcx
  int v53; // ebx
  LPWSTR v54; // rax
  __int64 v55; // rax
  rsize_t v56; // rbp
  const WCHAR *v57; // rax
  const WCHAR *v58; // rsi
  WCHAR v59; // di
  const WCHAR *v60; // rcx
  int v61; // ebx
  LPWSTR v62; // rax
  __int64 v63; // rax
  unsigned __int64 v64; // rax
  rsize_t v65; // rbx
  __int64 v66; // rcx
  wchar_t v67; // ax
  __int64 v68; // rcx
  wchar_t v69; // ax
  __int64 v70; // rcx
  wchar_t v71; // ax
  LPWSTR v72; // r14
  __int64 v73; // rax
  WCHAR v74; // di
  WCHAR *v75; // rsi
  const WCHAR *v76; // rcx
  int v77; // ebx
  LPWSTR v78; // rax
  __int64 v79; // rax
  rsize_t v80; // rbp
  LPWSTR v81; // rax
  const WCHAR *v82; // rsi
  WCHAR v83; // di
  const WCHAR *v84; // rcx
  int v85; // ebx
  LPWSTR v86; // rax
  __int64 v87; // rax
  unsigned __int64 v88; // rax
  rsize_t v89; // rbx
  ConnectParameter *v90; // r13
  char *v91; // rcx
  signed __int64 v92; // rdx
  __int16 v93; // ax
  char *v94; // rax
  __int64 v95; // rax
  _WORD *v96; // rcx
  __int64 v97; // r15
  __int64 v98; // rdx
  __int16 v99; // ax
  _WORD *v100; // rax
  const WCHAR *v101; // rsi
  __int64 v102; // rbx
  const WCHAR *v103; // rdi
  int v104; // ebp
  LPWSTR v105; // rax
  __int64 v106; // rax
  LPWSTR v107; // rcx
  WCHAR *v108; // rdx
  WCHAR v109; // cx
  WCHAR v110; // ax
  _WORD *v111; // rcx
  __int64 v112; // rdx
  __int16 v113; // ax
  _WORD *v114; // rax
  bool v115; // al
  __int64 v116; // rdx
  ConnectParameter *v117; // rcx
  __int16 v118; // ax
  ConnectParameter *v119; // rax
  signed __int64 v120; // rsi
  __int16 v121; // ax
  ConnectParameter *v122; // rax
  const WCHAR *v123; // rbp
  __int64 v124; // rdi
  const WCHAR *v125; // rbx
  int v126; // esi
  LPWSTR v127; // rax
  __int64 v128; // rax
  const WCHAR *v129; // rbx
  __int64 v130; // rax
  __int64 v131; // rsi
  const WCHAR *v132; // rdi
  int v133; // ebp
  LPWSTR v134; // rax
  __int64 v135; // rax
  const WCHAR *v136; // r8
  __int64 v137; // rax
  const WCHAR *v138; // rcx
  int v139; // esi
  LPWSTR v140; // rax
  __int64 v141; // rax
  _WORD *v142; // rdx
  signed __int64 v143; // rcx
  __int16 v144; // ax
  _WORD *v145; // rax
  struct __crt_locale_pointers *DefaultLocale; // rax
  wchar_t *v148; // rax
  wchar_t *v149; // r13
  wchar_t *v150; // r12
  __int64 v151; // rcx
  rsize_t v152; // r15
  WCHAR v153; // di
  const WCHAR *v154; // r14
  const WCHAR *v155; // rsi
  const WCHAR *v156; // rcx
  int v157; // ebx
  LPWSTR v158; // rax
  __int64 v159; // rax
  rsize_t v160; // rbp
  const WCHAR *v161; // rax
  const WCHAR *v162; // rsi
  WCHAR v163; // di
  const WCHAR *v164; // rcx
  int v165; // ebx
  LPWSTR v166; // rax
  __int64 v167; // rax
  unsigned __int64 v168; // rax
  rsize_t v169; // rbx
  ConnectParameter *v170; // rbp
  char *v171; // r9
  __int64 v172; // rdx
  _WORD *v173; // rcx
  __int16 v174; // ax
  _WORD *v175; // rax
  __int64 v176; // rcx
  wchar_t v177; // ax
  __int64 v178; // rcx
  wchar_t v179; // ax
  wchar_t *v180; // rax
  __int64 v181; // rax
  __int64 v182; // rax
  rsize_t v183; // r15
  WCHAR v184; // di
  const WCHAR *v185; // r14
  const WCHAR *v186; // rsi
  const WCHAR *v187; // rcx
  int v188; // ebx
  LPWSTR v189; // rax
  __int64 v190; // rax
  rsize_t v191; // rbp
  const WCHAR *v192; // rax
  const WCHAR *v193; // rsi
  WCHAR v194; // di
  const WCHAR *v195; // rcx
  int v196; // ebx
  LPWSTR v197; // rax
  __int64 v198; // rax
  unsigned __int64 v199; // rax
  rsize_t v200; // rbx
  __int64 v201; // rsi
  __int64 v202; // rax
  WCHAR *v203; // rdx
  wchar_t v204; // cx
  wchar_t v205; // ax
  __int64 v206; // rbx
  const WCHAR *v207; // rcx
  int v208; // edi
  LPWSTR v209; // rax
  __int64 v210; // rax
  _WORD *v211; // rcx
  __int64 v212; // rdx
  signed __int64 v213; // r12
  __int16 v214; // ax
  _WORD *v215; // rax
  __int64 v216; // rbx
  LPWSTR v217; // r13
  int v218; // edi
  LPWSTR v219; // rax
  __int64 v220; // rax
  WCHAR *v221; // r12
  __int64 v222; // rax
  WCHAR *v223; // rdx
  WCHAR v224; // cx
  WCHAR v225; // ax
  __int64 v226; // rax
  __int64 v227; // rax
  WCHAR v228; // di
  const WCHAR *v229; // r14
  const WCHAR *v230; // rsi
  const WCHAR *v231; // rcx
  int v232; // ebx
  LPWSTR v233; // rax
  __int64 v234; // rax
  rsize_t v235; // rbp
  const WCHAR *v236; // rax
  const WCHAR *v237; // rsi
  WCHAR v238; // bx
  const WCHAR *v239; // rcx
  int v240; // edi
  LPWSTR v241; // rax
  __int64 v242; // rax
  unsigned __int64 v243; // rax
  rsize_t v244; // rbx
  WCHAR v245; // bx
  WCHAR v246; // ax
  _WORD *v247; // rcx
  __int64 v248; // rdx
  signed __int64 v249; // r13
  __int16 v250; // ax
  _WORD *v251; // rax
  const wchar_t *v252; // r12
  __int64 v253; // rcx
  __int64 v254; // rax
  rsize_t v255; // r15
  WCHAR v256; // di
  WCHAR *v257; // rsi
  const WCHAR *v258; // rcx
  int v259; // ebx
  LPWSTR v260; // rax
  __int64 v261; // rax
  rsize_t v262; // rbp
  LPWSTR v263; // rax
  const WCHAR *v264; // rsi
  WCHAR v265; // di
  const WCHAR *v266; // rcx
  int v267; // ebx
  LPWSTR v268; // rax
  __int64 v269; // rax
  unsigned __int64 v270; // rax
  rsize_t v271; // rbx
  _WORD *v272; // rcx
  __int64 v273; // rbx
  __int64 v274; // rdx
  __int16 v275; // ax
  _WORD *v276; // rax
  WCHAR *v277; // rdx
  WCHAR v278; // cx
  WCHAR v279; // ax
  ConnectParameter *v280; // rcx
  signed __int64 v281; // r14
  __int16 v282; // ax
  __int64 v283; // rcx
  wchar_t v284; // ax
  __int16 v285; // ax
  __int16 v286; // ax
  ConnectParameter *v287; // rax
  char *v288; // rbx
  __int64 v289; // rcx
  wchar_t v290; // ax
  __int64 v291; // r8
  __int64 v292; // rdx
  _WORD *v293; // rcx
  __int16 v294; // ax
  _WORD *v295; // rax
  __int64 v296; // rcx
  _WORD *v297; // rax
  __int64 v298; // rax
  __int64 v299; // r10
  char *v300; // r9
  __int64 v301; // rax
  char *v302; // rdx
  __int16 v303; // cx
  char *v304; // rax
  __int64 v305; // rcx
  wchar_t v306; // ax
  __int64 v307; // rcx
  wchar_t v308; // ax
  __int64 v309; // rcx
  wchar_t v310; // ax
  __int64 v311; // rcx
  wchar_t v312; // ax
  __int64 v313; // rcx
  wchar_t v314; // ax
  char *v315; // rcx
  __int64 v316; // rdx
  __int16 v317; // ax
  char *v318; // rax
  char v319; // al
  LPWSTR lpDestStr; // [rsp+20h] [rbp-B8h]
  LPWSTR lpDestStra; // [rsp+20h] [rbp-B8h]
  int cchDest[2]; // [rsp+28h] [rbp-B0h]
  int cchDesta[2]; // [rsp+28h] [rbp-B0h]
  WCHAR *lpsz; // [rsp+60h] [rbp-78h]
  WCHAR *lpString2; // [rsp+68h] [rbp-70h]
  wchar_t *v326; // [rsp+70h] [rbp-68h]
  rsize_t v327; // [rsp+70h] [rbp-68h]
  wchar_t *v328; // [rsp+70h] [rbp-68h]
  rsize_t v329; // [rsp+70h] [rbp-68h]
  int v332; // [rsp+F8h] [rbp+20h]

  v5 = this;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\include\\open.hpp",
      "ConnectParameter::ParseConnectionString",
      131,
      L"API|SNIszConnect: '%s'\n",
      a2);
  v332 = 0;
  *((_BYTE *)v5 + 3096) = a3;
  v6 = *((_BYTE *)v5 + 3094) && !a3;
  *((_BYTE *)v5 + 3094) = v6;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v10 = *(_QWORD *)(v9 + 256);
  if ( !v10 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v10 = *(_QWORD *)(v9 + 256);
  }
  v11 = *(_QWORD *)(*(_QWORD *)(v10 + 992) + 56LL);
  v12 = (unsigned int)(v8 + 1);
  v13 = v12;
  v14 = 2 * v12;
  if ( !is_mul_ok(v12, 2u) )
    v14 = -1;
  v15 = (WCHAR *)operator new[](
                   v14,
                   *(struct IMemObj **)(v11 + 8),
                   1,
                   "sql\\common\\dk\\sni\\include\\open.hpp",
                   148,
                   6u);
  v16 = v15;
  lpsz = v15;
  if ( !v15 )
  {
    v17 = 14;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      cchDest[0] = 0;
      LODWORD(lpDestStr) = 10;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\include\\open.hpp",
        "ConnectParameter::ParseConnectionString",
        151,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        lpDestStr,
        *(_QWORD *)cchDest,
        14);
    }
    SNISetLastError(10, 14, 50100);
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(lpDestStr) = 14;
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\include\\open.hpp",
        "ConnectParameter::ParseConnectionString",
        153,
        L"RET|SNI%d{WINERR}\n",
        lpDestStr);
    }
    goto LABEL_250;
  }
  v19 = LCMapStringW(0x800u, 0x100u, a2, -1, v15, v8 + 1);
  if ( !v19 || v19 > (unsigned int)v12 )
    goto LABEL_244;
  v20 = (unsigned int)v8;
  v21 = v16;
  v16[v20] = 0;
  v22 = *v16;
  if ( *v16 )
  {
    if ( v16[v12 - 1] )
      goto LABEL_175;
    v23 = 0;
    do
    {
      v24 = L" \t";
      v25 = 0;
      while ( 1 )
      {
        if ( !*v24 )
        {
LABEL_29:
          v23 = 0;
          goto LABEL_30;
        }
        if ( *v24 == v22 )
          break;
        v26 = CharNextW(v24);
        v24 = v26;
        if ( v26 )
        {
          v27 = v26 - L" \t";
          if ( (int)v27 > v25 )
          {
            v25 = v27;
            if ( (int)v27 < 3 )
              continue;
          }
        }
        goto LABEL_29;
      }
      v29 = v16;
      if ( v23 )
        v29 = v23;
      v23 = v29;
LABEL_30:
      v16 = CharNextW(v16);
      v22 = *v16;
    }
    while ( *v16 );
    v21 = lpsz;
    if ( v23 )
    {
      v28 = v23 - lpsz + 1;
      if ( v28 >= v13 )
        goto LABEL_175;
      *v23 = 0;
    }
    else
    {
      v28 = v13;
    }
    v30 = lpsz;
    v31 = *lpsz;
    if ( *lpsz )
    {
      if ( lpsz[v28 - 1] )
        goto LABEL_175;
LABEL_40:
      v32 = L" \t";
      v33 = 0;
      while ( *v32 )
      {
        if ( *v32 == v31 )
        {
          v30 = CharNextW(v30);
          v31 = *v30;
          if ( *v30 )
            goto LABEL_40;
          break;
        }
        v34 = CharNextW(v32);
        v32 = v34;
        if ( v34 )
        {
          v35 = v34 - L" \t";
          if ( (int)v35 > v33 )
          {
            v33 = v35;
            if ( (int)v35 < 3 )
              continue;
          }
        }
        break;
      }
      v21 = lpsz;
      if ( v30 != lpsz )
      {
        v36 = v30 - lpsz;
        if ( v36 >= v28 )
          goto LABEL_175;
        _mm_lfence();
        v37 = v28 - v36;
        wmemmove_s(lpsz, v28, v30, v28 - v36);
        lpsz[v37] = 0;
        v21 = lpsz;
      }
    }
    v5 = this;
  }
  _mm_lfence();
  lpString2 = (WCHAR *)v21;
  v38 = wcschr(v21, 0x3Au);
  v39 = v38;
  v326 = v38;
  v40 = 11;
  if ( !v38 )
  {
    v72 = (LPWSTR)v21;
    goto LABEL_146;
  }
  *v38 = 0;
  if ( (__int64)(((char *)v38 - (char *)v21) & 0xFFFFFFFFFFFFFFFEuLL) > 20 )
    goto LABEL_243;
  v41 = (wchar_t *)((char *)v5 + 1536);
  v42 = 11;
  v43 = (_WORD *)((char *)v5 + 1536);
  do
  {
    if ( v42 == -2147483635 )
      break;
    v44 = *(_WORD *)((char *)v43 + (char *)v21 - ((char *)v5 + 1536));
    if ( !v44 )
      break;
    *v43++ = v44;
    --v42;
  }
  while ( v42 );
  v45 = v43 - 1;
  if ( v42 )
    v45 = v43;
  *v45 = 0;
  v46 = -1;
  do
    ++v46;
  while ( v41[v46] );
  v47 = (unsigned int)(v46 + 1);
  v48 = (unsigned int)v47;
  v49 = *v41;
  if ( *v41 )
  {
    if ( v41[v47 - 1] )
      goto LABEL_175;
    v50 = (const WCHAR *)((char *)v5 + 1536);
    v51 = 0;
    do
    {
      v52 = L" \t";
      v53 = 0;
      while ( 1 )
      {
        if ( !*v52 )
        {
LABEL_71:
          v51 = 0;
          goto LABEL_72;
        }
        if ( *v52 == v49 )
          break;
        v54 = CharNextW(v52);
        v52 = v54;
        if ( v54 )
        {
          v55 = v54 - L" \t";
          if ( (int)v55 > v53 )
          {
            v53 = v55;
            if ( (int)v55 < 3 )
              continue;
          }
        }
        goto LABEL_71;
      }
      v57 = v50;
      if ( v51 )
        v57 = v51;
      v51 = v57;
LABEL_72:
      v50 = CharNextW(v50);
      v49 = *v50;
    }
    while ( *v50 );
    v39 = v326;
    if ( v51 )
    {
      v56 = v51 - v41 + 1;
      if ( v56 >= v48 )
        goto LABEL_175;
      *v51 = 0;
    }
    else
    {
      v56 = v48;
    }
    v58 = v41;
    v59 = *v41;
    if ( *v41 )
    {
      if ( v41[v56 - 1] )
        goto LABEL_175;
LABEL_82:
      v60 = L" \t";
      v61 = 0;
      while ( *v60 )
      {
        if ( *v60 == v59 )
        {
          v58 = CharNextW(v58);
          v59 = *v58;
          if ( *v58 )
            goto LABEL_82;
          break;
        }
        v62 = CharNextW(v60);
        v60 = v62;
        if ( v62 )
        {
          v63 = v62 - L" \t";
          if ( (int)v63 > v61 )
          {
            v61 = v63;
            if ( (int)v63 < 3 )
              continue;
          }
        }
        break;
      }
      if ( v58 != v41 )
      {
        v64 = v58 - v41;
        if ( v64 >= v56 )
          goto LABEL_175;
        _mm_lfence();
        v65 = v56 - v64;
        wmemmove_s(v41, v56, v58, v56 - v64);
        v41[v65] = 0;
      }
    }
    v21 = lpsz;
  }
  if ( v39 == v21 )
    goto LABEL_142;
  v66 = 0;
  while ( 1 )
  {
    v67 = aTcp[v66++];
    if ( v67 != v41[v66 - 1] )
      break;
    if ( v66 == 4 )
      goto LABEL_109;
  }
  if ( *v41 != 110 || v41[1] != 112 || v41[2] )
  {
    v68 = 0;
    while ( 1 )
    {
      v69 = aLpc[v68++];
      if ( v69 != v41[v68 - 1] )
        break;
      if ( v68 == 4 )
        goto LABEL_109;
    }
    v70 = 0;
    while ( 1 )
    {
      v71 = aAdmin[v70++];
      if ( v71 != v41[v70 - 1] )
        break;
      if ( v70 == 6 )
        goto LABEL_109;
    }
LABEL_142:
    *v39 = 58;
    *v41 = 0;
    v72 = lpString2;
    v7 = -1;
    goto LABEL_145;
  }
LABEL_109:
  _mm_lfence();
  v72 = v39 + 1;
  lpString2 = v39 + 1;
  v7 = -1;
  v73 = -1;
  do
    ++v73;
  while ( v72[v73] );
  v327 = (unsigned int)(v73 + 1);
  v74 = *v72;
  if ( !*v72 )
  {
    v40 = 11;
    goto LABEL_146;
  }
  if ( v39[(unsigned int)(v73 + 1)] )
    goto LABEL_175;
  v75 = 0;
  do
  {
    v76 = L" \t";
    v77 = 0;
    while ( 1 )
    {
      if ( !*v76 )
      {
LABEL_120:
        v75 = 0;
        goto LABEL_121;
      }
      if ( *v76 == v74 )
        break;
      v78 = CharNextW(v76);
      v76 = v78;
      if ( v78 )
      {
        v79 = v78 - L" \t";
        if ( (int)v79 > v77 )
        {
          v77 = v79;
          if ( (int)v79 < 3 )
            continue;
        }
      }
      goto LABEL_120;
    }
    v81 = v72;
    if ( v75 )
      v81 = v75;
    v75 = v81;
LABEL_121:
    v72 = CharNextW(v72);
    v74 = *v72;
  }
  while ( *v72 );
  v72 = v39 + 1;
  if ( v75 )
  {
    v80 = v75 - lpString2 + 1;
    if ( v80 >= v327 )
      goto LABEL_175;
    *v75 = 0;
  }
  else
  {
    v80 = v327;
  }
  v82 = v39 + 1;
  v83 = *lpString2;
  if ( *lpString2 )
  {
    if ( v39[v80] )
      goto LABEL_175;
LABEL_131:
    v84 = L" \t";
    v85 = 0;
    while ( *v84 )
    {
      if ( *v84 == v83 )
      {
        v82 = CharNextW(v82);
        v83 = *v82;
        if ( *v82 )
          goto LABEL_131;
        break;
      }
      v86 = CharNextW(v84);
      v84 = v86;
      if ( v86 )
      {
        v87 = v86 - L" \t";
        if ( (int)v87 > v85 )
        {
          v85 = v87;
          if ( (int)v87 < 3 )
            continue;
        }
      }
      break;
    }
    v72 = v39 + 1;
    if ( v82 != lpString2 )
    {
      v88 = v82 - lpString2;
      if ( v88 >= v80 )
        goto LABEL_175;
      _mm_lfence();
      v89 = v80 - v88;
      wmemmove_s(lpString2, v80, v82, v80 - v88);
      lpString2[v89] = 0;
    }
  }
LABEL_145:
  v40 = 11;
LABEL_146:
  _mm_lfence();
  if ( CompareStringW(0x800u, 0, v72, 2, L"\\\\", 2) != 2 )
  {
    _mm_lfence();
    v148 = wcschr(v72, 0x2Cu);
    v149 = v148;
    v328 = v148;
    if ( v148 )
    {
      _mm_lfence();
      *v148 = 0;
      v150 = v148 + 1;
      v151 = -1;
      do
        ++v151;
      while ( v150[v151] );
      v152 = (unsigned int)(v151 + 1);
      v153 = *v150;
      if ( *v150 )
      {
        if ( v148[(unsigned int)(v151 + 1)] )
          goto LABEL_175;
        v154 = v148 + 1;
        v155 = 0;
        do
        {
          v156 = L" \t";
          v157 = 0;
          while ( 1 )
          {
            if ( !*v156 )
            {
LABEL_270:
              v155 = 0;
              goto LABEL_271;
            }
            if ( *v156 == v153 )
              break;
            v158 = CharNextW(v156);
            v156 = v158;
            if ( v158 )
            {
              v159 = v158 - L" \t";
              if ( (int)v159 > v157 )
              {
                v157 = v159;
                if ( (int)v159 < 3 )
                  continue;
              }
            }
            goto LABEL_270;
          }
          v161 = v154;
          if ( v155 )
            v161 = v155;
          v155 = v161;
LABEL_271:
          v154 = CharNextW(v154);
          v153 = *v154;
        }
        while ( *v154 );
        v149 = v328;
        if ( v155 )
        {
          v160 = v155 - v150 + 1;
          if ( v160 >= v152 )
            goto LABEL_175;
          *v155 = 0;
        }
        else
        {
          v160 = v152;
        }
        v162 = v150;
        v163 = *v150;
        if ( *v150 )
        {
          if ( v328[v160] )
            goto LABEL_175;
LABEL_281:
          v164 = L" \t";
          v165 = 0;
          while ( *v164 )
          {
            if ( *v164 == v163 )
            {
              v162 = CharNextW(v162);
              v163 = *v162;
              if ( *v162 )
                goto LABEL_281;
              break;
            }
            v166 = CharNextW(v164);
            v164 = v166;
            if ( v166 )
            {
              v167 = v166 - L" \t";
              if ( (int)v167 > v165 )
              {
                v165 = v167;
                if ( (int)v167 < 3 )
                  continue;
              }
            }
            break;
          }
          v149 = v328;
          if ( v162 != v150 )
          {
            v168 = v162 - v150;
            if ( v168 >= v160 )
              goto LABEL_175;
            _mm_lfence();
            v169 = v160 - v168;
            wmemmove_s(v150, v160, v162, v160 - v168);
            v328[v169 + 1] = 0;
          }
        }
      }
      v170 = this;
      v171 = (char *)this + 1536;
      if ( !*((_WORD *)this + 768) )
      {
        v172 = 11;
        v173 = (_WORD *)((char *)this + 1536);
        do
        {
          if ( v172 == -2147483635 )
            break;
          v174 = *(_WORD *)((char *)v173 + (char *)L"tcp" - v171);
          if ( !v174 )
            break;
          *v173++ = v174;
          --v172;
        }
        while ( v172 );
        v175 = v173 - 1;
        if ( v172 )
          v175 = v173;
        *v175 = 0;
      }
      v176 = 0;
      do
      {
        v177 = aTcp[v176++];
        if ( v177 != *(_WORD *)&v171[2 * v176 - 2] )
          goto LABEL_243;
      }
      while ( v176 != 4 );
      v178 = 0;
      do
      {
        v179 = aTcp[v178++];
        if ( v179 != *(_WORD *)&v171[2 * v178 - 2] )
          goto LABEL_341;
      }
      while ( v178 != 4 );
      _mm_lfence();
      v180 = wcschr(v150, 0x2Cu);
      if ( v180 )
      {
        _mm_lfence();
        *v180 = 0;
        v181 = -1;
        do
          ++v181;
        while ( v150[v181] );
        v182 = (unsigned int)(v181 + 1);
        v183 = (unsigned int)v182;
        v184 = *v150;
        if ( !*v150 || v149[v182] )
          goto LABEL_175;
        v185 = v150;
        v186 = 0;
        do
        {
          v187 = L" \t";
          v188 = 0;
          while ( 1 )
          {
            if ( !*v187 )
            {
LABEL_318:
              v186 = 0;
              goto LABEL_319;
            }
            if ( *v187 == v184 )
              break;
            v189 = CharNextW(v187);
            v187 = v189;
            if ( v189 )
            {
              v190 = v189 - L" \t";
              if ( (int)v190 > v188 )
              {
                v188 = v190;
                if ( (int)v190 < 3 )
                  continue;
              }
            }
            goto LABEL_318;
          }
          v192 = v185;
          if ( v186 )
            v192 = v186;
          v186 = v192;
LABEL_319:
          v185 = CharNextW(v185);
          v184 = *v185;
        }
        while ( *v185 );
        if ( v186 )
        {
          v191 = v186 - v150 + 1;
          if ( v191 >= v183 )
            goto LABEL_175;
          *v186 = 0;
        }
        else
        {
          v191 = v183;
        }
        v193 = v150;
        v194 = *v150;
        if ( !*v150 )
          goto LABEL_340;
        if ( v328[v191] )
          goto LABEL_175;
LABEL_329:
        v195 = L" \t";
        v196 = 0;
        while ( *v195 )
        {
          if ( *v195 == v194 )
          {
            v193 = CharNextW(v193);
            v194 = *v193;
            if ( *v193 )
              goto LABEL_329;
            break;
          }
          v197 = CharNextW(v195);
          v195 = v197;
          if ( v197 )
          {
            v198 = v197 - L" \t";
            if ( (int)v198 > v196 )
            {
              v196 = v198;
              if ( (int)v198 < 3 )
                continue;
            }
          }
          break;
        }
        if ( v193 == v150 )
        {
LABEL_340:
          v170 = this;
        }
        else
        {
          v199 = v193 - v150;
          if ( v199 >= v191 )
            goto LABEL_175;
          _mm_lfence();
          v200 = v191 - v199;
          wmemmove_s(v150, v191, v193, v191 - v199);
          v328[v200 + 1] = 0;
          v170 = this;
        }
      }
LABEL_341:
      if ( !*v150 || *v150 == 92 )
        goto LABEL_175;
      _mm_lfence();
      v201 = -1;
      v202 = -1;
      do
        ++v202;
      while ( v150[v202] );
      if ( (unsigned int)v202 > 0xFF )
        goto LABEL_243;
      v72 = lpString2;
      v203 = lpString2;
      if ( !*lpString2 )
        goto LABEL_175;
      v204 = *lpString2;
      do
      {
        if ( v204 != 32 )
        {
          v205 = v204;
          if ( v204 != 9 )
            break;
        }
        v205 = *++v203;
        v204 = *v203;
      }
      while ( *v203 );
      if ( !v205 )
        goto LABEL_175;
      _mm_lfence();
      v206 = -1;
      do
        ++v206;
      while ( v150[v206] );
      v207 = v150;
      v208 = 0;
      if ( (int)v206 > 0 )
      {
        while ( *v207 )
        {
          if ( *v207 == 92 )
          {
            *v207 = 0;
            break;
          }
          v209 = CharNextW(v207);
          v207 = v209;
          if ( v209 )
          {
            v210 = v209 - v150;
            if ( (int)v210 > v208 )
            {
              v208 = v210;
              if ( (int)v210 < (int)v206 )
                continue;
            }
          }
          break;
        }
      }
      v211 = (_WORD *)((char *)v170 + 1558);
      v212 = 256;
      v213 = (char *)v150 - ((char *)v170 + 1558);
      do
      {
        if ( v212 == -2147483390 )
          break;
        v214 = *(_WORD *)((char *)v211 + v213);
        if ( !v214 )
          break;
        *v211++ = v214;
        --v212;
      }
      while ( v212 );
      v215 = v211 - 1;
      if ( v212 )
        v215 = v211;
      *v215 = 0;
      v332 = 1;
      *((_BYTE *)v170 + 3094) = 0;
    }
    else
    {
      v201 = -1;
    }
    _mm_lfence();
    v216 = -1;
    do
      ++v216;
    while ( v72[v216] );
    v217 = v72;
    v218 = 0;
    if ( (int)v216 > 0 )
    {
      while ( 1 )
      {
        if ( !*v217 )
          goto LABEL_434;
        if ( *v217 == 92 )
          break;
        v219 = CharNextW(v217);
        v217 = v219;
        if ( v219 )
        {
          v220 = v219 - v72;
          if ( (int)v220 > v218 )
          {
            v218 = v220;
            if ( (int)v220 < (int)v216 )
              continue;
          }
        }
        goto LABEL_434;
      }
      *v217 = 0;
      v221 = v217 + 1;
      v222 = -1;
      do
        ++v222;
      while ( v221[v222] );
      if ( (unsigned int)v222 > 0xFF )
        goto LABEL_243;
      v223 = v72;
      if ( !*v72 )
        goto LABEL_175;
      v224 = *v72;
      do
      {
        if ( v224 != 32 )
        {
          v225 = v224;
          if ( v224 != 9 )
            break;
        }
        v225 = *++v223;
        v224 = *v223;
      }
      while ( *v223 );
      if ( !v225 )
        goto LABEL_175;
      v226 = -1;
      do
        ++v226;
      while ( v221[v226] );
      v227 = (unsigned int)(v226 + 1);
      v329 = (unsigned int)v227;
      v228 = *v221;
      if ( *v221 )
      {
        if ( v217[v227] )
          goto LABEL_175;
        v229 = v217 + 1;
        v230 = 0;
        do
        {
          v231 = L" \t";
          v232 = 0;
          while ( 1 )
          {
            if ( !*v231 )
            {
LABEL_398:
              v230 = 0;
              goto LABEL_399;
            }
            if ( *v231 == v228 )
              break;
            v233 = CharNextW(v231);
            v231 = v233;
            if ( v233 )
            {
              v234 = v233 - L" \t";
              if ( (int)v234 > v232 )
              {
                v232 = v234;
                if ( (int)v234 < 3 )
                  continue;
              }
            }
            goto LABEL_398;
          }
          v236 = v229;
          if ( v230 )
            v236 = v230;
          v230 = v236;
LABEL_399:
          v229 = CharNextW(v229);
          v228 = *v229;
        }
        while ( *v229 );
        if ( v230 )
        {
          v235 = v230 - v221 + 1;
          if ( v235 >= v329 )
            goto LABEL_175;
          *v230 = 0;
        }
        else
        {
          v235 = v329;
        }
        v237 = v217 + 1;
        v238 = *v221;
        if ( *v221 )
        {
          if ( v217[v235] )
            goto LABEL_175;
LABEL_409:
          v239 = L" \t";
          v240 = 0;
          while ( *v239 )
          {
            if ( *v239 == v238 )
            {
              v237 = CharNextW(v237);
              v238 = *v237;
              if ( *v237 )
                goto LABEL_409;
              break;
            }
            v241 = CharNextW(v239);
            v239 = v241;
            if ( v241 )
            {
              v242 = v241 - L" \t";
              if ( (int)v242 > v240 )
              {
                v240 = v242;
                if ( (int)v242 < 3 )
                  continue;
              }
            }
            break;
          }
          if ( v237 != v221 )
          {
            v243 = v237 - v221;
            if ( v243 >= v235 )
              goto LABEL_175;
            _mm_lfence();
            v244 = v235 - v243;
            wmemmove_s(v217 + 1, v235, v237, v235 - v243);
            v221[v244] = 0;
          }
          v245 = *v221;
          if ( *v221 )
          {
            do
            {
              if ( v245 != 32 )
              {
                v246 = v245;
                if ( v245 != 9 )
                  break;
              }
              v245 = *++v221;
              v246 = *v221;
            }
            while ( *v221 );
            if ( !v246 )
              goto LABEL_175;
            if ( !v332 )
            {
              v247 = (_WORD *)((char *)this + 1024);
              v248 = 256;
              v249 = (char *)v217 - ((char *)this + 1024);
              do
              {
                if ( v248 == -2147483390 )
                  break;
                v250 = *(_WORD *)((char *)v247 + v249 + 2);
                if ( !v250 )
                  break;
                *v247++ = v250;
                --v248;
              }
              while ( v248 );
              v251 = v247 - 1;
              if ( v248 )
                v251 = v247;
              *v251 = 0;
            }
          }
        }
        v72 = lpString2;
        v201 = -1;
      }
    }
LABEL_434:
    v90 = this;
    v252 = (const wchar_t *)((char *)this + 1024);
    v253 = 0;
    while ( aMssqlserver[v253] == v252[v253] && aMssqlserver[v253 + 1] == v252[v253 + 1] )
    {
      v253 += 2;
      if ( v253 == 12 )
        goto LABEL_243;
    }
    _mm_lfence();
    v254 = -1;
    do
      ++v254;
    while ( v72[v254] );
    if ( (unsigned int)v254 > 0xFF )
    {
LABEL_243:
      v16 = lpsz;
LABEL_244:
      v107 = v16;
      goto LABEL_245;
    }
    _mm_lfence();
    do
      ++v201;
    while ( v72[v201] );
    v255 = (unsigned int)(v201 + 1);
    v256 = *v72;
    if ( *v72 )
    {
      if ( v72[(unsigned int)(v201 + 1) - 1] )
        goto LABEL_175;
      v257 = 0;
      do
      {
        v258 = L" \t";
        v259 = 0;
        while ( 1 )
        {
          if ( !*v258 )
          {
LABEL_453:
            v257 = 0;
            goto LABEL_454;
          }
          if ( *v258 == v256 )
            break;
          v260 = CharNextW(v258);
          v258 = v260;
          if ( v260 )
          {
            v261 = v260 - L" \t";
            if ( (int)v261 > v259 )
            {
              v259 = v261;
              if ( (int)v261 < 3 )
                continue;
            }
          }
          goto LABEL_453;
        }
        v263 = v72;
        if ( v257 )
          v263 = v257;
        v257 = v263;
LABEL_454:
        v72 = CharNextW(v72);
        v256 = *v72;
      }
      while ( *v72 );
      v90 = this;
      v72 = lpString2;
      if ( v257 )
      {
        v262 = v257 - lpString2 + 1;
        if ( v262 >= v255 )
          goto LABEL_175;
        *v257 = 0;
      }
      else
      {
        v262 = v255;
      }
      v264 = lpString2;
      v265 = *lpString2;
      if ( *lpString2 )
      {
        if ( lpString2[v262 - 1] )
          goto LABEL_175;
LABEL_464:
        v266 = L" \t";
        v267 = 0;
        while ( *v266 )
        {
          if ( *v266 == v265 )
          {
            v264 = CharNextW(v264);
            v265 = *v264;
            if ( *v264 )
              goto LABEL_464;
            break;
          }
          v268 = CharNextW(v266);
          v266 = v268;
          if ( v268 )
          {
            v269 = v268 - L" \t";
            if ( (int)v269 > v267 )
            {
              v267 = v269;
              if ( (int)v269 < 3 )
                continue;
            }
          }
          break;
        }
        v252 = (const wchar_t *)((char *)this + 1024);
        if ( v264 != lpString2 )
        {
          v270 = v264 - lpString2;
          if ( v270 >= v262 )
            goto LABEL_175;
          _mm_lfence();
          v271 = v262 - v270;
          wmemmove_s(lpString2, v262, v264, v262 - v270);
          lpString2[v271] = 0;
        }
      }
    }
    v272 = (_WORD *)((char *)v90 + 512);
    v273 = 256;
    v274 = 256;
    do
    {
      if ( v274 == -2147483390 )
        break;
      v275 = *(_WORD *)((char *)v272 + (char *)v72 - ((char *)v90 + 512));
      if ( !v275 )
        break;
      *v272++ = v275;
      --v274;
    }
    while ( v274 );
    v276 = v272 - 1;
    if ( v274 )
      v276 = v272;
    *v276 = 0;
    v277 = v72;
    if ( !*v72 )
      goto LABEL_493;
    v278 = *v72;
    do
    {
      if ( v278 != 32 )
      {
        v279 = v278;
        if ( v278 != 9 )
          break;
      }
      v279 = *++v277;
      v278 = *v277;
    }
    while ( *v277 );
    if ( v279 && (_mm_lfence(), !IsLocalHost(v72)) )
    {
      v280 = v90;
      v281 = (char *)v72 - (char *)v90;
      do
      {
        if ( v273 == -2147483390 )
          break;
        v282 = *(_WORD *)((char *)v280 + v281);
        if ( !v282 )
          break;
        *(_WORD *)v280 = v282;
        v280 = (ConnectParameter *)((char *)v280 + 2);
        --v273;
      }
      while ( v273 );
    }
    else
    {
LABEL_493:
      v283 = 0;
      while ( 1 )
      {
        v284 = aAdmin[v283++];
        if ( v284 != *((_WORD *)v90 + v283 + 767) )
          break;
        if ( v283 == 6 )
        {
          v280 = v90;
          do
          {
            if ( v273 == -2147483390 )
              break;
            v285 = *(_WORD *)((char *)v280 + (char *)L"localhost" - (char *)v90);
            if ( !v285 )
              break;
            *(_WORD *)v280 = v285;
            v280 = (ConnectParameter *)((char *)v280 + 2);
            --v273;
          }
          while ( v273 );
          goto LABEL_505;
        }
      }
      v280 = v90;
      do
      {
        if ( v273 == -2147483390 )
          break;
        v286 = *(_WORD *)((char *)v280 + (char *)&gwszComputerName - (char *)v90);
        if ( !v286 )
          break;
        *(_WORD *)v280 = v286;
        v280 = (ConnectParameter *)((char *)v280 + 2);
        --v273;
      }
      while ( v273 );
    }
LABEL_505:
    v287 = (ConnectParameter *)((char *)v280 - 2);
    if ( v273 )
      v287 = v280;
    *(_WORD *)v287 = 0;
    v288 = (char *)v90 + 1536;
    v289 = 0;
    do
    {
      v290 = aLpc[v289++];
      if ( v290 != *(_WORD *)&v288[2 * v289 - 2] )
        goto LABEL_514;
    }
    while ( v289 != 4 );
    if ( !IsLocalHost((PCNZWCH)v90) )
    {
      v17 = 87;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        cchDesta[0] = 41;
        LODWORD(lpDestStra) = 10;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\include\\open.hpp",
          "ConnectParameter::ParseConnectionString",
          553,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          lpDestStra,
          *(_QWORD *)cchDesta,
          87);
      }
      v291 = 50141;
LABEL_572:
      SNISetLastError(10, 87, v291);
      operator delete[](lpsz);
      goto LABEL_248;
    }
LABEL_514:
    v292 = 512;
    v293 = (_WORD *)((char *)v90 + 2070);
    do
    {
      if ( v292 == -2147483134 )
        break;
      v294 = *(v293 - 1035);
      if ( !v294 )
        break;
      *v293++ = v294;
      --v292;
    }
    while ( v292 );
    v295 = v293 - 1;
    if ( v292 )
      v295 = v293;
    *v295 = 0;
    if ( *v252 )
    {
      v296 = 512;
      v297 = (_WORD *)((char *)v90 + 2070);
      do
      {
        if ( !*v297 )
          break;
        ++v297;
        --v296;
      }
      while ( v296 );
      v298 = 512 - v296;
      if ( v296 )
      {
        v299 = v296;
        v300 = (char *)v90 + 2 * v298 + 2070;
        if ( v298 != 512 )
        {
          v301 = 2147483646;
          v302 = (char *)((char *)L"\\" - v300);
          do
          {
            if ( !v301 )
              break;
            v303 = *(_WORD *)&v302[(_QWORD)v300];
            if ( !v303 )
              break;
            *(_WORD *)v300 = v303;
            v300 += 2;
            --v301;
            --v299;
          }
          while ( v299 );
        }
        v304 = v300 - 2;
        if ( v299 )
          v304 = v300;
        *(_WORD *)v304 = 0;
      }
      StringCchCatW((wchar_t *)v90 + 1035, 0x200u, v252);
      v305 = 0;
      while ( 1 )
      {
        v306 = aLpc[v305++];
        if ( v306 != *(_WORD *)&v288[2 * v305 - 2] )
          break;
        if ( v305 == 4 )
          goto LABEL_540;
      }
      v307 = 0;
      while ( 1 )
      {
        v308 = aAdmin[v307++];
        if ( v308 != *(_WORD *)&v288[2 * v307 - 2] )
          break;
        if ( v307 == 6 )
          goto LABEL_540;
      }
    }
    else
    {
LABEL_540:
      *((_BYTE *)v90 + 3094) = 0;
    }
    if ( a3 )
    {
      if ( *(_WORD *)v288 == 110 && *((_WORD *)v90 + 769) == 112 && !*((_WORD *)v90 + 770) )
      {
LABEL_556:
        v17 = 87;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          cchDesta[0] = 49;
          LODWORD(lpDestStra) = 10;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\include\\open.hpp",
            "ConnectParameter::ParseConnectionString",
            585,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            lpDestStra,
            *(_QWORD *)cchDesta,
            87);
        }
        v291 = 50149;
        goto LABEL_572;
      }
      v309 = 0;
      while ( 1 )
      {
        v310 = aVia[v309++];
        if ( v310 != *(_WORD *)&v288[2 * v309 - 2] )
          break;
        if ( v309 == 4 )
          goto LABEL_556;
      }
      v311 = 0;
      while ( 1 )
      {
        v312 = aLpc[v311++];
        if ( v312 != *(_WORD *)&v288[2 * v311 - 2] )
          break;
        if ( v311 == 4 )
          goto LABEL_556;
      }
      v313 = 0;
      while ( 1 )
      {
        v314 = aAdmin[v313++];
        if ( v314 != *(_WORD *)&v288[2 * v313 - 2] )
          break;
        if ( v313 == 6 )
          goto LABEL_556;
      }
      if ( !*(_WORD *)v288 )
      {
        v315 = (char *)((char *)L"tcp" - v288);
        v316 = 11;
        do
        {
          if ( v316 == -2147483635 )
            break;
          v317 = *(_WORD *)&v315[(_QWORD)v288];
          if ( !v317 )
            break;
          *(_WORD *)v288 = v317;
          v288 += 2;
          --v316;
        }
        while ( v316 );
        v318 = v288 - 2;
        if ( v316 )
          v318 = v288;
        *(_WORD *)v318 = 0;
        if ( !v316 )
        {
          v319 = g_XeSniPkg_enabledBitmap;
          if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
          {
            _mm_lfence();
            LODWORD(lpDestStra) = -2147024774;
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\include\\open.hpp",
              "ConnectParameter::ParseConnectionString",
              597,
              L"ERR|SNIStringCchCopy failed: %d{HRESULT}.\n",
              lpDestStra);
            v319 = g_XeSniPkg_enabledBitmap;
          }
          v17 = 87;
          if ( (v319 & 2) != 0 )
          {
            cchDesta[0] = 0;
            LODWORD(lpDestStra) = 10;
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\include\\open.hpp",
              "ConnectParameter::ParseConnectionString",
              600,
              L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
              lpDestStra,
              *(_QWORD *)cchDesta,
              87);
          }
          v291 = 50100;
          goto LABEL_572;
        }
      }
    }
LABEL_256:
    v17 = 0;
    operator delete[](lpsz);
    if ( (g_XeSniPkg_enabledBitmap & 1) == 0 )
      goto LABEL_250;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\include\\open.hpp",
      "ConnectParameter::ParseConnectionString",
      640,
      L"SNIm_wszProtocolName: '%s', m_wszServerName: '%s', m_wszInstanceName: '%s', m_wszProtocolParameter: '%s', m_wszAli"
       "as: '%hs', m_fCanUseCache: %d{bool}, m_fStandardInstName: %d{bool}, m_wszOriginalServerName: '%s'\n",
      (char *)v90 + 1536,
      v90,
      (char *)v90 + 1024,
      (char *)v90 + 1558,
      (char *)v90 + 2070,
      *((unsigned __int8 *)v90 + 3094),
      *((unsigned __int8 *)v90 + 3095),
      (char *)v90 + 512);
    goto LABEL_248;
  }
  v90 = this;
  v91 = (char *)this + 1536;
  if ( *((_WORD *)this + 768) )
  {
    if ( *(_WORD *)v91 != 110 || *((_WORD *)this + 769) != 112 || *((_WORD *)this + 770) )
      goto LABEL_243;
  }
  else
  {
    v92 = (char *)L"np" - v91;
    do
    {
      if ( v40 == -2147483635 )
        break;
      v93 = *(_WORD *)&v91[v92];
      if ( !v93 )
        break;
      *(_WORD *)v91 = v93;
      v91 += 2;
      --v40;
    }
    while ( v40 );
    v94 = v91 - 2;
    if ( v40 )
      v94 = v91;
    *(_WORD *)v94 = 0;
  }
  _mm_lfence();
  v95 = -1;
  do
    ++v95;
  while ( v72[v95] );
  if ( (unsigned int)v95 > 0xFF )
    goto LABEL_243;
  _mm_lfence();
  v96 = (_WORD *)((char *)this + 1558);
  v97 = 256;
  v98 = 256;
  do
  {
    if ( v98 == -2147483390 )
      break;
    v99 = *(_WORD *)((char *)v96 + (char *)v72 - ((char *)this + 1558));
    if ( !v99 )
      break;
    *v96++ = v99;
    --v98;
  }
  while ( v98 );
  v100 = v96 - 1;
  if ( v98 )
    v100 = v96;
  *v100 = 0;
  v101 = v72 + 2;
  v102 = -1;
  do
    ++v102;
  while ( v101[v102] );
  v103 = v72 + 2;
  v104 = 0;
  if ( (int)v102 > 0 )
  {
    while ( 1 )
    {
      if ( !*v103 )
        goto LABEL_175;
      if ( *v103 == 92 )
        break;
      v105 = CharNextW(v103);
      v103 = v105;
      if ( v105 )
      {
        v106 = v105 - v101;
        if ( (int)v106 > v104 )
        {
          v104 = v106;
          if ( (int)v106 < (int)v102 )
            continue;
        }
      }
      goto LABEL_175;
    }
    *v103 = 0;
    v108 = v72 + 2;
    if ( *v101 )
    {
      v109 = *v101;
      do
      {
        if ( v109 != 32 )
        {
          v110 = v109;
          if ( v109 != 9 )
            break;
        }
        v110 = *++v108;
        v109 = *v108;
      }
      while ( *v108 );
      if ( v110 )
      {
        _mm_lfence();
        v111 = (_WORD *)((char *)this + 512);
        v112 = 256;
        do
        {
          if ( v112 == -2147483390 )
            break;
          v113 = *(_WORD *)((char *)v111 + (char *)v101 - ((char *)this + 512));
          if ( !v113 )
            break;
          *v111++ = v113;
          --v112;
        }
        while ( v112 );
        v114 = v111 - 1;
        if ( v112 )
          v114 = v111;
        *v114 = 0;
        v115 = IsLocalHost(v101);
        v116 = 256;
        v117 = this;
        if ( v115 )
        {
          do
          {
            if ( v116 == -2147483390 )
              break;
            v118 = *(_WORD *)((char *)v117 + (char *)&gwszComputerName - (char *)this);
            if ( !v118 )
              break;
            *(_WORD *)v117 = v118;
            v117 = (ConnectParameter *)((char *)v117 + 2);
            --v116;
          }
          while ( v116 );
          v119 = (ConnectParameter *)((char *)v117 - 2);
          if ( v116 )
            v119 = v117;
          *(_WORD *)v119 = 0;
          goto LABEL_202;
        }
        v120 = (char *)v101 - (char *)this;
        do
        {
          if ( v116 == -2147483390 )
            break;
          v121 = *(_WORD *)((char *)v117 + v120);
          if ( !v121 )
            break;
          *(_WORD *)v117 = v121;
          v117 = (ConnectParameter *)((char *)v117 + 2);
          --v116;
        }
        while ( v116 );
        v122 = (ConnectParameter *)((char *)v117 - 2);
        if ( v116 )
          v122 = v117;
        *(_WORD *)v122 = 0;
        if ( v116 )
        {
LABEL_202:
          v123 = v103 + 1;
          v124 = -1;
          do
            ++v124;
          while ( v123[v124] );
          v125 = v123;
          v126 = 0;
          if ( (int)v124 > 0 )
          {
            while ( 1 )
            {
              if ( !*v125 )
                goto LABEL_175;
              if ( *v125 == 92 )
                break;
              v127 = CharNextW(v125);
              v125 = v127;
              if ( !v127 )
                goto LABEL_175;
              v128 = v127 - v123;
              if ( (int)v128 <= v126 )
                goto LABEL_175;
              v126 = v128;
              if ( (int)v128 >= (int)v124 )
              {
                v107 = lpsz;
                goto LABEL_245;
              }
            }
            v129 = v125 + 1;
            v130 = -1;
            do
              ++v130;
            while ( v129[v130] );
            if ( CompareStringW(0x800u, 0, v129, v130, L"sql\\query", 9) == 2 )
            {
              *((_WORD *)this + 512) = 0;
LABEL_255:
              *((_BYTE *)this + 3094) = 0;
              goto LABEL_256;
            }
            if ( CompareStringW(0x800u, 0, v129, 6, L"mssql$", 6) != 2 )
            {
LABEL_253:
              DefaultLocale = GetDefaultLocale();
              if ( (int)StringCchPrintf_lW((wchar_t *)this + 512, 0x100u, L"pipe%s", DefaultLocale, v129) < 0 )
                goto LABEL_243;
              *((_BYTE *)this + 3095) = 0;
              goto LABEL_255;
            }
            v131 = -1;
            do
              ++v131;
            while ( v129[v131] );
            v132 = v129;
            v133 = 0;
            if ( (int)v131 > 0 )
            {
              while ( *v132 )
              {
                if ( *v132 == 92 )
                {
                  v136 = v132 + 1;
                  v137 = -1;
                  do
                    ++v137;
                  while ( v136[v137] );
                  if ( CompareStringW(0x800u, 0, v136, v137, L"sql\\query", 9) != 2 )
                    goto LABEL_253;
                  do
                    ++v7;
                  while ( v129[v7] );
                  v138 = v129;
                  v139 = 0;
                  if ( (int)v7 > 0 )
                  {
                    do
                    {
                      if ( !*v138 )
                        break;
                      if ( *v138 == 36 )
                        goto LABEL_236;
                      v140 = CharNextW(v138);
                      v138 = v140;
                      if ( !v140 )
                        break;
                      v141 = v140 - v129;
                      if ( (int)v141 <= v139 )
                        break;
                      v139 = v141;
                    }
                    while ( (int)v141 < (int)v7 );
                  }
                  v138 = 0;
LABEL_236:
                  *v132 = 0;
                  v142 = (_WORD *)((char *)this + 1024);
                  v143 = (char *)v138 - ((char *)this + 1024);
                  do
                  {
                    if ( v97 == -2147483390 )
                      break;
                    v144 = *(_WORD *)((char *)v142 + v143 + 2);
                    if ( !v144 )
                      break;
                    *v142++ = v144;
                    --v97;
                  }
                  while ( v97 );
                  v145 = v142 - 1;
                  if ( v97 )
                    v145 = v142;
                  *v145 = 0;
                  if ( v97 )
                    goto LABEL_255;
                  goto LABEL_243;
                }
                v134 = CharNextW(v132);
                v132 = v134;
                if ( !v134 )
                  goto LABEL_175;
                v135 = v134 - v129;
                if ( (int)v135 <= v133 )
                  goto LABEL_175;
                v133 = v135;
                if ( (int)v135 >= (int)v131 )
                {
                  v107 = lpsz;
                  goto LABEL_245;
                }
              }
            }
          }
          goto LABEL_175;
        }
        goto LABEL_243;
      }
    }
  }
LABEL_175:
  v107 = lpsz;
LABEL_245:
  operator delete[](v107);
  v17 = 87;
  if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
  {
    cchDesta[0] = 25;
    LODWORD(lpDestStra) = 10;
    SNIXE_SNI_ERROR_ON(
      "sql\\common\\dk\\sni\\include\\open.hpp",
      "ConnectParameter::ParseConnectionString",
      618,
      L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
      lpDestStra,
      *(_QWORD *)cchDesta,
      87);
  }
  SNISetLastError(10, 87, 50125);
LABEL_248:
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(lpDestStra) = v17;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\include\\open.hpp",
      "ConnectParameter::ParseConnectionString",
      643,
      L"RET|SNI%d{WINERR}\n",
      lpDestStra);
  }
LABEL_250:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\include\\open.hpp", "ConnectParameter::ParseConnectionString", 131, v18);
  return v17;
}

```

## disassembly

```asm
0x10041f6b0  mov     r11, rsp
0x10041f6b3  mov     [r11+18h], r8b
0x10041f6b7  mov     [r11+8], rcx
0x10041f6bb  push    rbp
0x10041f6bc  push    rsi
0x10041f6bd  push    rdi
0x10041f6be  push    r12
0x10041f6c0  push    r13
0x10041f6c2  push    r14
0x10041f6c4  push    r15
0x10041f6c6  sub     rsp, 0A0h
0x10041f6cd  mov     qword ptr [r11-60h], 0FFFFFFFFFFFFFFFEh
0x10041f6d5  mov     [r11+10h], rbx
0x10041f6d9  movzx   ebx, r8b
0x10041f6dd  mov     rdi, rdx
0x10041f6e0  mov     rbp, rcx
0x10041f6e3  lea     r14, aSqlCommonDkSni_7; "sql\\common\\dk\\sni\\include\\open.hpp"
0x10041f6ea  mov     [r11-58h], r14
0x10041f6ee  lea     rax, aConnectparamet; "ConnectParameter::ParseConnectionString"
0x10041f6f5  mov     [r11-50h], rax
0x10041f6f9  mov     dword ptr [r11-48h], 83h
0x10041f701  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10041f708  jz      short loc_10041F727
0x10041f70a  mov     [rsp+0D8h+lpDestStr], rdx
0x10041f70f  lea     r9, aApiSniszconnec; "API|SNIszConnect: '%s'\n"
0x10041f716  mov     r8d, 83h; int
0x10041f71c  mov     rdx, rax; char *
0x10041f71f  mov     rcx, r14; char *
0x10041f722  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10041f727  xor     r13d, r13d
0x10041f72a  mov     [rsp+0D8h+arg_18], r13d
0x10041f732  mov     [rbp+0C18h], bl
0x10041f738  cmp     [rbp+0C16h], r13b
0x10041f73f  jz      short loc_10041F749
0x10041f741  test    bl, bl
0x10041f743  jnz     short loc_10041F749
0x10041f745  mov     al, 1
0x10041f747  jmp     short loc_10041F74B
0x10041f749  xor     al, al
0x10041f74b  mov     [rbp+0C16h], al
0x10041f751  mov     r12, 0FFFFFFFFFFFFFFFFh
0x10041f758  mov     rbx, r12
0x10041f75b  nop     dword ptr [rax+rax+00h]
0x10041f760  inc     rbx
0x10041f763  cmp     [rdi+rbx*2], r13w
0x10041f768  jnz     short loc_10041F760
0x10041f76a  mov     rdx, gs:58h
0x10041f773  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041f77a  mov     ecx, [rax]
0x10041f77c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041f783  mov     esi, [rax]
0x10041f785  add     rsi, [rdx+rcx*8]
0x10041f789  mov     rax, [rsi+100h]
0x10041f790  test    rax, rax
0x10041f793  jnz     short loc_10041F7A4
0x10041f795  xor     ecx, ecx
0x10041f797  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041f79d  mov     rax, [rsi+100h]
0x10041f7a4  mov     rax, [rax+3E0h]
0x10041f7ab  mov     rcx, [rax+38h]
0x10041f7af  lea     esi, [rbx+1]
0x10041f7b2  mov     r15d, esi
0x10041f7b5  mov     eax, 2
0x10041f7ba  mul     r15
0x10041f7bd  cmovo   rax, r12
0x10041f7c1  mov     byte ptr [rsp+0D8h+cchDest], 6
0x10041f7c6  mov     dword ptr [rsp+0D8h+lpDestStr], 94h
0x10041f7ce  mov     r9, r14
0x10041f7d1  mov     r8d, 1
0x10041f7d7  mov     rdx, [rcx+8]
0x10041f7db  mov     rcx, rax
0x10041f7de  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10041f7e4  mov     r14, rax
0x10041f7e7  mov     [rsp+0D8h+lpsz], rax
0x10041f7ec  test    rax, rax
0x10041f7ef  jnz     loc_10041F87A
0x10041f7f5  lea     ebx, [rax+0Eh]
0x10041f7f8  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10041f7ff  jz      short loc_10041F832
0x10041f801  mov     dword ptr [rsp+0D8h+var_A8], ebx
0x10041f805  mov     [rsp+0D8h+cchDest], r13d
0x10041f80a  mov     dword ptr [rsp+0D8h+lpDestStr], 0Ah
0x10041f812  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10041f819  mov     r8d, 97h; int
0x10041f81f  lea     rdx, aConnectparamet; "ConnectParameter::ParseConnectionString"
0x10041f826  lea     rcx, aSqlCommonDkSni_7; "sql\\common\\dk\\sni\\include\\open.hpp"
0x10041f82d  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10041f832  mov     r8d, 0C3B4h
0x10041f838  mov     edx, ebx
0x10041f83a  mov     ecx, 0Ah
0x10041f83f  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10041f844  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10041f84b  jz      loc_100420407
0x10041f851  mov     dword ptr [rsp+0D8h+lpDestStr], ebx
0x10041f855  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10041f85c  mov     r8d, 99h; int
0x10041f862  lea     rdx, aConnectparamet; "ConnectParameter::ParseConnectionString"
0x10041f869  lea     rcx, aSqlCommonDkSni_7; "sql\\common\\dk\\sni\\include\\open.hpp"
0x10041f870  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10041f875  jmp     loc_100420407
0x10041f87a  mov     [rsp+0D8h+cchDest], esi; cchDest
0x10041f87e  mov     [rsp+0D8h+lpDestStr], rax; lpDestStr
0x10041f883  mov     r9d, r12d; cchSrc
0x10041f886  mov     r8, rdi; lpSrcStr
0x10041f889  mov     edx, 100h; dwMapFlags
0x10041f88e  mov     ecx, 800h; Locale
0x10041f893  call    cs:__imp_LCMapStringW
0x10041f899  test    eax, eax
0x10041f89b  jz      loc_10042037C
0x10041f8a1  cmp     eax, esi
0x10041f8a3  ja      loc_10042037C
0x10041f8a9  mov     eax, ebx
0x10041f8ab  mov     rbx, r14
0x10041f8ae  xor     r14d, r14d
0x10041f8b1  mov     [rbx+rax*2], r14w
0x10041f8b6  movzx   edi, word ptr [rbx]
0x10041f8b9  lea     r13, sz; " \t"
0x10041f8c0  test    di, di
0x10041f8c3  jz      loc_10041FA19
0x10041f8c9  cmp     r14w, [rbx+rsi*2-2]
0x10041f8cf  jnz     loc_100420026
0x10041f8d5  mov     r14, rbx
0x10041f8d8  xor     ebp, ebp
0x10041f8da  mov     esi, ebp
0x10041f8dc  nop     dword ptr [rax+00h]
0x10041f8e0  mov     rcx, r13; lpsz
0x10041f8e3  mov     ebx, ebp
0x10041f8e5  movzx   eax, word ptr [rcx]
0x10041f8e8  test    ax, ax
0x10041f8eb  jz      short loc_10041F911
0x10041f8ed  cmp     ax, di
0x10041f8f0  jz      short loc_10041F950
0x10041f8f2  call    cs:__imp_CharNextW
0x10041f8f8  mov     rcx, rax
0x10041f8fb  test    rax, rax
0x10041f8fe  jz      short loc_10041F911
0x10041f900  sub     rax, r13
0x10041f903  sar     rax, 1
0x10041f906  cmp     eax, ebx
0x10041f908  jle     short loc_10041F911
0x10041f90a  mov     ebx, eax
0x10041f90c  cmp     eax, 3
0x10041f90f  jl      short loc_10041F8E5
0x10041f911  mov     rsi, rbp
0x10041f914  mov     rcx, r14; lpsz
0x10041f917  call    cs:__imp_CharNextW
0x10041f91d  mov     r14, rax
0x10041f920  movzx   edi, word ptr [rax]
0x10041f923  test    di, di
0x10041f926  jnz     short loc_10041F8E0
0x10041f928  mov     rbx, [rsp+0D8h+lpsz]
0x10041f92d  test    rsi, rsi
0x10041f930  jz      short loc_10041F95F
0x10041f932  mov     rbp, rsi
0x10041f935  sub     rbp, rbx
0x10041f938  sar     rbp, 1
0x10041f93b  inc     rbp
0x10041f93e  cmp     rbp, r15
0x10041f941  jnb     loc_100420026
0x10041f947  xor     r14d, r14d
0x10041f94a  mov     [rsi], r14w
0x10041f94e  jmp     short loc_10041F965
0x10041f950  mov     rax, r14
0x10041f953  test    rsi, rsi
0x10041f956  cmovnz  rax, rsi
0x10041f95a  mov     rsi, rax
0x10041f95d  jmp     short loc_10041F914
0x10041f95f  mov     rbp, r15
0x10041f962  xor     r14d, r14d
0x10041f965  mov     rsi, rbx
0x10041f968  movzx   edi, word ptr [rbx]
0x10041f96b  test    di, di
0x10041f96e  jz      loc_10041FA11
0x10041f974  cmp     r14w, [rbx+rbp*2-2]
0x10041f97a  jnz     loc_100420026
0x10041f980  mov     rcx, r13; lpsz
0x10041f983  mov     ebx, r14d
0x10041f986  movzx   eax, word ptr [rcx]
0x10041f989  test    ax, ax
0x10041f98c  jz      short loc_10041F9C8
0x10041f98e  cmp     ax, di
0x10041f991  jz      short loc_10041F9B4
0x10041f993  call    cs:__imp_CharNextW
0x10041f999  mov     rcx, rax
0x10041f99c  test    rax, rax
0x10041f99f  jz      short loc_10041F9C8
0x10041f9a1  sub     rax, r13
0x10041f9a4  sar     rax, 1
0x10041f9a7  cmp     eax, ebx
0x10041f9a9  jle     short loc_10041F9C8
0x10041f9ab  mov     ebx, eax
0x10041f9ad  cmp     eax, 3
0x10041f9b0  jge     short loc_10041F9C8
0x10041f9b2  jmp     short loc_10041F986
0x10041f9b4  mov     rcx, rsi; lpsz
0x10041f9b7  call    cs:__imp_CharNextW
0x10041f9bd  mov     rsi, rax
0x10041f9c0  movzx   edi, word ptr [rax]
0x10041f9c3  test    di, di
0x10041f9c6  jnz     short loc_10041F980
0x10041f9c8  mov     rbx, [rsp+0D8h+lpsz]
0x10041f9cd  cmp     rsi, rbx
0x10041f9d0  jz      short loc_10041FA11
0x10041f9d2  mov     rax, rsi
0x10041f9d5  sub     rax, rbx
0x10041f9d8  sar     rax, 1
0x10041f9db  cmp     rax, rbp
0x10041f9de  jnb     loc_100420026
0x10041f9e4  lfence
0x10041f9e7  mov     rbx, rbp
0x10041f9ea  sub     rbx, rax
0x10041f9ed  mov     r9, rbx; N
0x10041f9f0  mov     r8, rsi; S2
0x10041f9f3  mov     rdx, rbp; N1
0x10041f9f6  mov     r14, [rsp+0D8h+lpsz]
0x10041f9fb  mov     rcx, r14; S1
0x10041f9fe  call    cs:__imp_wmemmove_s
0x10041fa04  xor     eax, eax
0x10041fa06  mov     [r14+rbx*2], ax
0x10041fa0b  mov     rbx, r14
0x10041fa0e  xor     r14d, r14d
0x10041fa11  mov     rbp, [rsp+0D8h+arg_0]
0x10041fa19  lfence
0x10041fa1c  mov     [rsp+0D8h+lpString2], rbx
0x10041fa21  mov     esi, 3Ah ; ':'
0x10041fa26  mov     edx, esi; Ch
0x10041fa28  mov     rcx, rbx; Str
0x10041fa2b  call    cs:__imp_wcschr
0x10041fa31  mov     r13, rax
0x10041fa34  mov     [rsp+0D8h+var_68], rax
0x10041fa39  lea     edi, [rsi-2Fh]
0x10041fa3c  lea     r9, aTcp; "tcp"
0x10041fa43  lea     r15d, [rsi+34h]
0x10041fa47  lea     r10, aLpc; "lpc"
0x10041fa4e  lea     r11, aAdmin; "admin"
0x10041fa55  test    rax, rax
0x10041fa58  jz      loc_10041FE95
0x10041fa5e  mov     [rax], r14w
0x10041fa62  mov     rcx, rax
0x10041fa65  sub     rcx, rbx
0x10041fa68  and     rcx, 0FFFFFFFFFFFFFFFEh
0x10041fa6c  cmp     rcx, 14h
0x10041fa70  jg      loc_100420377
0x10041fa76  lea     r12, [rbp+600h]
0x10041fa7d  mov     edx, edi
0x10041fa7f  mov     rcx, r12
0x10041fa82  mov     r8, rbx
0x10041fa85  sub     r8, r12
0x10041fa88  nop     dword ptr [rax+rax+00000000h]
0x10041fa90  lea     rax, [rdx+7FFFFFF3h]
0x10041fa97  test    rax, rax
0x10041fa9a  jz      short loc_10041FAB3
0x10041fa9c  movzx   eax, word ptr [r8+rcx]
0x10041faa1  test    ax, ax
0x10041faa4  jz      short loc_10041FAB3
0x10041faa6  mov     [rcx], ax
0x10041faa9  add     rcx, 2
0x10041faad  sub     rdx, 1
0x10041fab1  jnz     short loc_10041FA90
0x10041fab3  lea     rax, [rcx-2]
0x10041fab7  test    rdx, rdx
0x10041faba  cmovnz  rax, rcx
0x10041fabe  mov     [rax], r14w
0x10041fac2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x10041fac9  nop     dword ptr [rax+00000000h]
0x10041fad0  inc     rax
0x10041fad3  cmp     word ptr [r12+rax*2], 0
0x10041fad9  jnz     short loc_10041FAD0
0x10041fadb  inc     eax
0x10041fadd  mov     r15d, eax
0x10041fae0  movzx   edi, word ptr [r12]
0x10041fae5  test    di, di
0x10041fae8  jz      loc_10041FC5E
0x10041faee  cmp     r14w, [r12+rax*2-2]
0x10041faf4  jnz     loc_100420026
0x10041fafa  mov     r14, r12
0x10041fafd  xor     r13d, r13d
0x10041fb00  mov     esi, r13d
0x10041fb03  lea     rbp, sz; " \t"
0x10041fb0a  nop     word ptr [rax+rax+00h]
0x10041fb10  mov     rcx, rbp; lpsz
0x10041fb13  mov     ebx, r13d
0x10041fb16  movzx   eax, word ptr [rcx]
0x10041fb19  test    ax, ax
0x10041fb1c  jz      short loc_10041FB42
0x10041fb1e  cmp     ax, di
0x10041fb21  jz      short loc_10041FB81
0x10041fb23  call    cs:__imp_CharNextW
0x10041fb29  mov     rcx, rax
0x10041fb2c  test    rax, rax
0x10041fb2f  jz      short loc_10041FB42
0x10041fb31  sub     rax, rbp
0x10041fb34  sar     rax, 1
0x10041fb37  cmp     eax, ebx
0x10041fb39  jle     short loc_10041FB42
0x10041fb3b  mov     ebx, eax
0x10041fb3d  cmp     eax, 3
0x10041fb40  jl      short loc_10041FB16
0x10041fb42  mov     rsi, r13
0x10041fb45  mov     rcx, r14; lpsz
  ... truncated ...
```
