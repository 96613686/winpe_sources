# CRegExprEvaluator::Evaluate(CExprDeserializer const * const,CCallerIdentity const *,tagDSGlobalUpdateId const &,ulong,tagDSDataBlob const * const,tagSusRuleContext const &,ISusExprEvaluate *,ulong,tagExpressionVariableData const * const,tagSusRuleResult *)

- ea: `0x18022b030`
- end: `0x18022ca83`
- name: `?Evaluate@CRegExprEvaluator@@UEAAJQEBVCExprDeserializer@@PEBVCCallerIdentity@@AEBUtagDSGlobalUpdateId@@KQEBUtagDSDataBlob@@AEBUtagSusRuleContext@@PEAUISusExprEvaluate@@KQEBUtagExpressionVariableData@@PEAW4tagSusRuleResult@@@Z`
- size: `6739`
- prototype: `int(CRegExprEvaluator *__hidden this, const struct CExprDeserializer *const, const struct CCallerIdentity *, const struct tagDSGlobalUpdateId *, unsigned int, const struct tagDSDataBlob *const, const struct tagSusRuleContext *, struct ISusExprEvaluate *, unsigned int, const struct tagExpressionVariableData *const, enum tagSusRuleResult *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000c644`
- `0x18000c6b4`
- `0x180113ae8`
- `0x180113b9c`
- `0x18012b618`
- `0x18012d944`
- `0x180137dd0`
- `0x18022b030`
- `0x18022ca8c`
- `0x18022d0c4`
- `0x18022d92c`
- `0x18022dda4`
- `0x180235cd0`
- `0x18023611c`
- `0x180238000`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18022c22e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18022c642`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18022ca0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18022c22e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18022c642`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18022ca0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18022c1c5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18022c5e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18022c9df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18022c1c5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18022c5e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18022c9df`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18022c67c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18022c67c`
- `OLEAUT32!__imp_SysStringLen` at `0x18022b34d`
- `OLEAUT32!__imp_SysStringLen` at `0x18022b366`
- `OLEAUT32!__imp_SysStringLen` at `0x18022b736`
- `OLEAUT32!__imp_SysStringLen` at `0x18022b74f`
- `OLEAUT32!__imp_SysStringLen` at `0x18022bfd8`
- `OLEAUT32!__imp_SysStringLen` at `0x18022c3fd`
- `OLEAUT32!__imp_SysStringLen` at `0x18022c61c`
- `OLEAUT32!__imp_SysStringLen` at `0x18022c805`
- `OLEAUT32!__imp_SysStringLen` at `0x18022b34d`
- `OLEAUT32!__imp_SysStringLen` at `0x18022b366`
- `OLEAUT32!__imp_SysStringLen` at `0x18022b736`
- `OLEAUT32!__imp_SysStringLen` at `0x18022b74f`
- `OLEAUT32!__imp_SysStringLen` at `0x18022bfd8`
- `OLEAUT32!__imp_SysStringLen` at `0x18022c3fd`
- `OLEAUT32!__imp_SysStringLen` at `0x18022c61c`
- `OLEAUT32!__imp_SysStringLen` at `0x18022c805`

## string_xrefs

- `0x18022c5ec`: `RegValueExists: Opened Subkey %ws successfully`

## pseudocode

```c
__int64 __fastcall CRegExprEvaluator::Evaluate(
        CRegExprEvaluator *this,
        CExprDeserializer *a2,
        const struct CCallerIdentity *a3,
        const struct tagDSGlobalUpdateId *a4,
        unsigned int a5,
        struct tagDSDataBlob *a6,
        const struct tagSusRuleContext *a7,
        struct ISusExprEvaluate *a8,
        unsigned int a9,
        wchar_t *a10,
        enum tagSusRuleResult *a11)
{
  int ExpressionID; // ebx
  int v16; // eax
  wchar_t *v17; // rsi
  __int64 v18; // rax
  unsigned int v19; // r9d
  HKEY *v20; // r15
  unsigned int v21; // ecx
  __int64 v22; // rdx
  OLECHAR *v23; // r13
  unsigned int v24; // ecx
  unsigned int v25; // r9d
  __int64 v26; // r8
  __int64 v27; // rax
  unsigned int v28; // ecx
  unsigned int v29; // r9d
  __int64 v30; // r8
  OLECHAR *v31; // r12
  unsigned int v32; // ecx
  unsigned int v33; // r9d
  __int64 v34; // r8
  _WORD *v35; // r9
  unsigned int v36; // ecx
  unsigned int v37; // r10d
  __int64 v38; // r8
  HKEY v39; // r15
  UINT v40; // eax
  UINT v41; // edi
  int v42; // r8d
  unsigned int v43; // edx
  __int64 v44; // rcx
  unsigned int v45; // edx
  const wchar_t *v46; // r12
  UINT v47; // eax
  unsigned __int64 v48; // r14
  wchar_t *v49; // rax
  int v50; // r11d
  int v51; // eax
  unsigned __int64 v52; // rbx
  wchar_t *v53; // rax
  wchar_t *v54; // rsi
  __int64 v55; // rax
  unsigned int v56; // r9d
  HKEY *v57; // r15
  unsigned int v58; // ecx
  __int64 v59; // rdx
  OLECHAR *v60; // r13
  unsigned int v61; // ecx
  unsigned int v62; // r9d
  __int64 v63; // r8
  __int64 v64; // rax
  unsigned int v65; // ecx
  unsigned int v66; // r9d
  __int64 v67; // r8
  OLECHAR *v68; // r12
  unsigned int v69; // ecx
  unsigned int v70; // r9d
  __int64 v71; // r8
  _WORD *v72; // r9
  unsigned int v73; // ecx
  unsigned int v74; // r10d
  __int64 v75; // r8
  HKEY v76; // r15
  UINT v77; // eax
  UINT v78; // edi
  int v79; // r8d
  unsigned int v80; // edx
  __int64 v81; // rcx
  unsigned int v82; // edx
  const wchar_t *v83; // r12
  UINT v84; // eax
  unsigned __int64 v85; // r14
  wchar_t *v86; // rax
  int v87; // r11d
  int v88; // eax
  unsigned __int64 v89; // rbx
  wchar_t *v90; // rax
  int v91; // r15d
  __int64 v92; // rax
  unsigned int v93; // r9d
  HKEY *v94; // r13
  unsigned int v95; // ecx
  __int64 v96; // rdx
  wchar_t *v97; // r12
  unsigned int v98; // ecx
  unsigned int v99; // r9d
  __int64 v100; // rdx
  wchar_t *v101; // rsi
  unsigned int v102; // ecx
  unsigned int v103; // r9d
  __int64 v104; // rdx
  enum StringComparison *v105; // rbx
  unsigned int v106; // ecx
  unsigned int v107; // r9d
  __int64 v108; // rdx
  wchar_t *v109; // r11
  unsigned int v110; // ecx
  unsigned int v111; // r9d
  __int64 v112; // r8
  _WORD *v113; // rdx
  unsigned int v114; // ecx
  unsigned int v115; // r10d
  __int64 v116; // r9
  int v117; // r10d
  const wchar_t *v118; // rax
  int v119; // r15d
  __int64 v120; // rax
  unsigned int v121; // r9d
  HKEY *v122; // r13
  unsigned int v123; // ecx
  __int64 v124; // rdx
  wchar_t *v125; // r12
  unsigned int v126; // ecx
  unsigned int v127; // r9d
  __int64 v128; // rdx
  wchar_t *v129; // rsi
  unsigned int v130; // ecx
  unsigned int v131; // r9d
  __int64 v132; // rdx
  enum StringComparison *v133; // rbx
  unsigned int v134; // ecx
  unsigned int v135; // r9d
  __int64 v136; // rdx
  wchar_t *v137; // r11
  unsigned int v138; // ecx
  unsigned int v139; // r9d
  __int64 v140; // r8
  _WORD *v141; // r9
  unsigned int v142; // ecx
  unsigned int v143; // r10d
  __int64 v144; // r8
  wchar_t *v145; // rsi
  __int64 v146; // rax
  unsigned int v147; // r9d
  HKEY *v148; // r12
  unsigned int v149; // ecx
  __int64 v150; // rdx
  OLECHAR *v151; // r13
  unsigned int v152; // ecx
  unsigned int v153; // r9d
  __int64 v154; // r8
  __int64 v155; // rax
  unsigned int v156; // ecx
  unsigned int v157; // r9d
  __int64 v158; // r8
  __int64 v159; // rax
  OLECHAR *v160; // r11
  unsigned int v161; // ecx
  unsigned int v162; // r9d
  __int64 v163; // r8
  unsigned int *v164; // r15
  unsigned int v165; // ecx
  unsigned int v166; // r9d
  __int64 v167; // r8
  _WORD *v168; // r9
  unsigned int v169; // ecx
  unsigned int v170; // r10d
  __int64 v171; // r8
  HKEY v172; // r12
  UINT v173; // eax
  UINT v174; // r15d
  int v175; // r8d
  int v176; // edi
  HKEY *v177; // rax
  unsigned int v178; // edx
  __int64 v179; // rcx
  unsigned int v180; // edx
  const wchar_t *v181; // rdi
  UINT v182; // eax
  unsigned __int64 v183; // rbx
  wchar_t *v184; // rax
  int v185; // r11d
  int v186; // eax
  unsigned __int64 v187; // rbx
  wchar_t *v188; // rax
  enum tagSusRuleResult *v189; // rdi
  const wchar_t *v190; // r13
  unsigned int v191; // edi
  int v192; // eax
  enum tagSusRuleResult *v193; // r15
  wchar_t *v194; // rsi
  __int64 v195; // rax
  unsigned int v196; // r9d
  HKEY *v197; // r12
  unsigned int v198; // ecx
  __int64 v199; // rdx
  OLECHAR *v200; // r13
  unsigned int v201; // ecx
  unsigned int v202; // r9d
  __int64 v203; // r8
  __int64 v204; // rax
  unsigned int v205; // ecx
  unsigned int v206; // r9d
  __int64 v207; // r8
  __int64 v208; // rax
  unsigned int v209; // ecx
  unsigned int v210; // r9d
  __int64 v211; // r8
  enum tagSusRuleResult *v212; // rdi
  _WORD *v213; // r9
  unsigned int v214; // ecx
  unsigned int v215; // r10d
  __int64 v216; // r8
  HKEY v217; // r12
  UINT v218; // eax
  UINT v219; // r15d
  int v220; // r8d
  int v221; // edi
  unsigned int v222; // edx
  __int64 v223; // rcx
  unsigned int v224; // edx
  const wchar_t *v225; // rdi
  UINT v226; // eax
  unsigned __int64 v227; // rbx
  wchar_t *v228; // rax
  int v229; // r11d
  int v230; // eax
  unsigned __int64 v231; // rbx
  wchar_t *v232; // rax
  const WCHAR *v233; // rdi
  int v234; // eax
  wchar_t *v235; // rsi
  __int64 v236; // rax
  unsigned int v237; // r9d
  HKEY *v238; // r12
  unsigned int v239; // ecx
  __int64 v240; // rdx
  OLECHAR *v241; // r13
  unsigned int v242; // ecx
  unsigned int v243; // r9d
  __int64 v244; // r8
  _WORD *v245; // r9
  unsigned int v246; // ecx
  unsigned int v247; // r10d
  __int64 v248; // r8
  HKEY v249; // r12
  UINT v250; // eax
  UINT v251; // r15d
  int v252; // eax
  int v253; // edi
  unsigned int v254; // ecx
  __int64 v255; // rdx
  unsigned int v256; // ecx
  const wchar_t *v257; // rdi
  UINT v258; // eax
  unsigned __int64 v259; // rbx
  wchar_t *v260; // rax
  int v261; // r11d
  int v262; // eax
  unsigned __int64 v263; // rbx
  wchar_t *v264; // rax
  enum tagSusRuleResult *v265; // rdi
  wchar_t *v266; // [rsp+30h] [rbp-69h]
  wchar_t *v267; // [rsp+30h] [rbp-69h]
  wchar_t *v268; // [rsp+30h] [rbp-69h]
  wchar_t *v269; // [rsp+30h] [rbp-69h]
  wchar_t *v270; // [rsp+30h] [rbp-69h]
  wchar_t *v271; // [rsp+30h] [rbp-69h]
  wchar_t *v272; // [rsp+30h] [rbp-69h]
  struct ISusExprEvaluate *v273; // [rsp+38h] [rbp-61h]
  OLECHAR *v274; // [rsp+58h] [rbp-41h]
  OLECHAR *v275; // [rsp+58h] [rbp-41h]
  unsigned int *v276; // [rsp+58h] [rbp-41h]
  int v277; // [rsp+60h] [rbp-39h] BYREF
  wchar_t *v278[2]; // [rsp+68h] [rbp-31h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-21h] BYREF
  BSTR pbstr; // [rsp+80h] [rbp-19h] BYREF
  DWORD Type; // [rsp+88h] [rbp-11h] BYREF
  unsigned int v282; // [rsp+8Ch] [rbp-Dh] BYREF

  pbstr = (BSTR)a8;
  v277 = 0;
  if ( !a11 )
    return 2147942487LL;
  *(_DWORD *)a11 = -1;
  if ( !a2 )
    return 2147942487LL;
  if ( a5 )
  {
    if ( !a6 )
      return 2147942487LL;
  }
  else if ( a6 )
  {
    return 2147942487LL;
  }
  if ( a9 )
  {
    if ( !a10 )
      return 2147942487LL;
  }
  else if ( a10 )
  {
    return 2147942487LL;
  }
  v278[0] = (wchar_t *)a9;
  v278[1] = a10;
  ExpressionID = CExprDeserializer::GetExpressionID(a2, (enum ExpressionIDEnum *)&v277);
  if ( ExpressionID >= 0 )
  {
    if ( v277 != 18 )
    {
      if ( v277 != 19 )
      {
        if ( v277 != 21 )
        {
          if ( v277 != 22 )
          {
            if ( v277 != 23 )
            {
              if ( v277 == 24 )
              {
                v16 = CRegExprEvaluator::EvaluateRegSzToVersion(
                        0,
                        a2,
                        (const struct CExpressionVariableData *const)v278,
                        a11);
                goto LABEL_23;
              }
              if ( v277 != 25 )
              {
                if ( v277 != 26 )
                {
                  if ( v277 != 40 )
                  {
                    ExpressionID = -2145067007;
                    goto LABEL_546;
                  }
                  v16 = CRegExprEvaluator::EvaluateRegKeyLoop(
                          a11,
                          a2,
                          a3,
                          a4,
                          a5,
                          a6,
                          a7,
                          (struct ISusExprEvaluate *)pbstr,
                          (const struct CExpressionVariableData *const)v278,
                          a11);
LABEL_23:
                  ExpressionID = v16;
                  goto LABEL_546;
                }
                v17 = 0;
                v282 = 0;
                Type = 0;
                *(_DWORD *)a11 = -1;
                if ( !*((_DWORD *)a2 + 6) || (v18 = *((_QWORD *)a2 + 1)) == 0 )
                {
                  ExpressionID = -2145067003;
                  goto LABEL_104;
                }
                v19 = *(_DWORD *)(v18 + 8);
                v20 = 0;
                v21 = 0;
                if ( v19 )
                {
                  v22 = *((_QWORD *)a2 + 2);
                  while ( *(_DWORD *)(v22 + 24LL * v21) != 33 )
                  {
                    if ( ++v21 >= v19 )
                      goto LABEL_33;
                  }
                  if ( *(_DWORD *)(v22 + 24LL * v21 + 8) != 10 )
                    goto LABEL_60;
                  v20 = (HKEY *)(v22 + 16 + 24LL * v21);
                }
LABEL_33:
                v23 = 0;
                v24 = 0;
                v25 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
                if ( v25 )
                {
                  v26 = *((_QWORD *)a2 + 2);
                  while ( *(_DWORD *)(v26 + 24LL * v24) != 34 )
                  {
                    if ( ++v24 >= v25 )
                      goto LABEL_40;
                  }
                  if ( *(_DWORD *)(v26 + 24LL * v24 + 8) != 8 )
                    goto LABEL_60;
                  v23 = *(OLECHAR **)(v26 + 24LL * v24 + 16);
                }
LABEL_40:
                v27 = *((_QWORD *)a2 + 1);
                v28 = 0;
                hKey = 0;
                v29 = *(_DWORD *)(v27 + 8);
                if ( v29 )
                {
                  v30 = *((_QWORD *)a2 + 2);
                  while ( *(_DWORD *)(v30 + 24LL * v28) != 35 )
                  {
                    if ( ++v28 >= v29 )
                      goto LABEL_47;
                  }
                  if ( *(_DWORD *)(v30 + 24LL * v28 + 8) != 8 )
                    goto LABEL_60;
                  hKey = *(HKEY *)(v30 + 24LL * v28 + 16);
                }
LABEL_47:
                v31 = 0;
                v274 = 0;
                v32 = 0;
                v33 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
                if ( v33 )
                {
                  v34 = *((_QWORD *)a2 + 2);
                  while ( *(_DWORD *)(v34 + 24LL * v32) != 36 )
                  {
                    if ( ++v32 >= v33 )
                      goto LABEL_54;
                  }
                  if ( *(_DWORD *)(v34 + 24LL * v32 + 8) != 8 )
                    goto LABEL_60;
                  v31 = *(OLECHAR **)(v34 + 24LL * v32 + 16);
                  v274 = v31;
                }
LABEL_54:
                v35 = 0;
                v36 = 0;
                v37 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
                if ( v37 )
                {
                  v38 = *((_QWORD *)a2 + 2);
                  while ( *(_DWORD *)(v38 + 24LL * v36) != 153 )
                  {
                    if ( ++v36 >= v37 )
                      goto LABEL_62;
                  }
                  if ( *(_DWORD *)(v38 + 24LL * v36 + 8) != 7 )
                  {
LABEL_60:
                    ExpressionID = -2147024809;
LABEL_104:
                    SusFree(v17);
                    LODWORD(v273) = ExpressionID;
                    v267 = (wchar_t *)ResultToString(*(unsigned int *)a11);
                    WUTrace(
                      0,
                      0,
                      0x100000,
                      5,
                      0,
                      L"  EE: WUv4RegKeySubstring evaluated to %ws, return hr=%#lx",
                      v267,
                      v273);
                    goto LABEL_546;
                  }
                  v35 = (_WORD *)(v38 + 16 + 24LL * v36);
                }
LABEL_62:
                if ( v35 )
                  v282 = *v35 == 0xFFFF;
                if ( !v20 || !SysStringLen(v31) )
                  goto LABEL_102;
                v39 = *v20;
                v40 = SysStringLen(v23);
                if ( v39 == (HKEY)0xFFFFFFFFLL )
                {
                  v41 = v40;
                  v42 = 0;
                  if ( !a9 )
                    goto LABEL_71;
                  while ( *(_DWORD *)&a10[12 * v42] || *(_DWORD *)&a10[12 * v42 + 2] )
                  {
                    if ( ++v42 >= a9 )
                      goto LABEL_71;
                  }
                  if ( *(_DWORD *)&a10[12 * v42 + 4] != 8 )
                    goto LABEL_71;
                  v39 = **(HKEY **)&a10[12 * v42 + 8];
                  if ( v39 == (HKEY)0xFFFFFFFFLL )
                    goto LABEL_71;
                  v43 = 0;
                  while ( 1 )
                  {
                    v44 = 3LL * v43;
                    if ( !*(_DWORD *)&a10[12 * v43] && *(_DWORD *)&a10[12 * v43 + 2] == 1 )
                      break;
                    if ( ++v43 >= a9 )
                      goto LABEL_71;
                  }
                  v45 = *(_DWORD *)&a10[12 * v43 + 4];
                  v46 = *(const wchar_t **)&a10[4 * v44 + 8];
                  if ( v45 >= 4 )
                  {
                    if ( v40 && *v23 == 92 )
                    {
                      ++v23;
                      v41 = v40 - 1;
                    }
                    v47 = v41 + 1;
                    if ( !v41 )
                      v47 = 0;
                    v48 = (v45 >> 1) + v47;
                    v49 = (wchar_t *)SafeSusAllocArray(v48, 2u);
                    v17 = v49;
                    if ( !v49 )
                    {
LABEL_86:
                      ExpressionID = -2147024882;
                      goto LABEL_94;
                    }
                    ExpressionID = StringCchCopyW(v49, v48, v46);
                    if ( ExpressionID >= 0 )
                    {
                      if ( !v41 )
                        goto LABEL_95;
                      ExpressionID = StringCchCatW(v17, v48, L"\\");
                      if ( ExpressionID >= 0 )
                      {
                        v51 = StringCchCatW(v17, v48, v23);
                        v50 = 0;
                        ExpressionID = v51;
                        if ( v51 >= 0 )
                        {
LABEL_98:
                          v31 = v274;
LABEL_99:
                          if ( (_WORD)v50 != *v17 )
                          {
                            WUTrace(
                              0,
                              0,
                              0x100000,
                              5,
                              v50,
                              L"  EE: Evaluating WUv4RegKeySubstring: subkey=%ws, data=%ws",
                              v17,
                              v31);
                            ExpressionID = WUv4RegKeySubstring(v282, v39, v17, (const wchar_t *)hKey, v31, (int *)&Type);
                            if ( ExpressionID >= 0 )
                              *(_DWORD *)a11 = Type != 0;
                            goto LABEL_104;
                          }
                          goto LABEL_102;
                        }
                      }
                    }
                  }
                  else
                  {
LABEL_71:
                    ExpressionID = -2145067006;
                  }
LABEL_94:
                  SusFree(v17);
                  v50 = 0;
                  v17 = 0;
                  v39 = 0;
LABEL_95:
                  if ( ExpressionID < 0 )
                  {
                    *(_DWORD *)a11 = -1;
                    goto LABEL_104;
                  }
                  if ( v17 )
                    goto LABEL_98;
LABEL_102:
                  ExpressionID = -2145067002;
                  goto LABEL_104;
                }
                v52 = v40 + 1;
                v53 = (wchar_t *)SafeSusAllocArray(v52, 2u);
                v17 = v53;
                if ( v53 )
                {
                  ExpressionID = StringCchCopyW(v53, (unsigned int)v52, v23);
                  if ( ExpressionID >= 0 )
                    goto LABEL_99;
                  goto LABEL_94;
                }
                goto LABEL_86;
              }
              v54 = 0;
              Type = 0;
              v282 = 0;
              *(_DWORD *)a11 = -1;
              if ( !*((_DWORD *)a2 + 6) || (v55 = *((_QWORD *)a2 + 1)) == 0 )
              {
                ExpressionID = -2145067003;
                goto LABEL_185;
              }
              v56 = *(_DWORD *)(v55 + 8);
              v57 = 0;
              v58 = 0;
              if ( v56 )
              {
                v59 = *((_QWORD *)a2 + 2);
                while ( *(_DWORD *)(v59 + 24LL * v58) != 28 )
                {
                  if ( ++v58 >= v56 )
                    goto LABEL_114;
                }
                if ( *(_DWORD *)(v59 + 24LL * v58 + 8) != 10 )
                  goto LABEL_141;
                v57 = (HKEY *)(v59 + 16 + 24LL * v58);
              }
LABEL_114:
              v60 = 0;
              v61 = 0;
              v62 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
              if ( v62 )
              {
                v63 = *((_QWORD *)a2 + 2);
                while ( *(_DWORD *)(v63 + 24LL * v61) != 29 )
                {
                  if ( ++v61 >= v62 )
                    goto LABEL_121;
                }
                if ( *(_DWORD *)(v63 + 24LL * v61 + 8) != 8 )
                  goto LABEL_141;
                v60 = *(OLECHAR **)(v63 + 24LL * v61 + 16);
              }
LABEL_121:
              v64 = *((_QWORD *)a2 + 1);
              v65 = 0;
              hKey = 0;
              v66 = *(_DWORD *)(v64 + 8);
              if ( v66 )
              {
                v67 = *((_QWORD *)a2 + 2);
                while ( *(_DWORD *)(v67 + 24LL * v65) != 30 )
                {
                  if ( ++v65 >= v66 )
                    goto LABEL_128;
                }
                if ( *(_DWORD *)(v67 + 24LL * v65 + 8) != 8 )
                  goto LABEL_141;
                hKey = *(HKEY *)(v67 + 24LL * v65 + 16);
              }
LABEL_128:
              v68 = 0;
              v275 = 0;
              v69 = 0;
              v70 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
              if ( v70 )
              {
                v71 = *((_QWORD *)a2 + 2);
                while ( *(_DWORD *)(v71 + 24LL * v69) != 31 )
                {
                  if ( ++v69 >= v70 )
                    goto LABEL_135;
                }
                if ( *(_DWORD *)(v71 + 24LL * v69 + 8) != 8 )
                  goto LABEL_141;
                v68 = *(OLECHAR **)(v71 + 24LL * v69 + 16);
                v275 = v68;
              }
LABEL_135:
              v72 = 0;
              v73 = 0;
              v74 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
              if ( v74 )
              {
                v75 = *((_QWORD *)a2 + 2);
                while ( *(_DWORD *)(v75 + 24LL * v73) != 152 )
                {
                  if ( ++v73 >= v74 )
                    goto LABEL_143;
                }
                if ( *(_DWORD *)(v75 + 24LL * v73 + 8) != 7 )
                {
LABEL_141:
                  ExpressionID = -2147024809;
LABEL_185:
                  SusFree(v54);
                  LODWORD(v273) = ExpressionID;
                  v268 = (wchar_t *)ResultToString(*(unsigned int *)a11);
                  WUTrace(0, 0, 0x100000, 5, 0, L"  EE: WUv4RegKeyValue evaluated to %ws, return hr=%#lx", v268, v273);
                  goto LABEL_546;
                }
                v72 = (_WORD *)(v75 + 16 + 24LL * v73);
              }
LABEL_143:
              if ( v72 )
                Type = *v72 == 0xFFFF;
              if ( !v57 || !SysStringLen(v68) )
                goto LABEL_183;
              v76 = *v57;
              v77 = SysStringLen(v60);
              if ( v76 == (HKEY)0xFFFFFFFFLL )
              {
                v78 = v77;
                v79 = 0;
                if ( !a9 )
                  goto LABEL_152;
                while ( *(_DWORD *)&a10[12 * v79] || *(_DWORD *)&a10[12 * v79 + 2] )
                {
                  if ( ++v79 >= a9 )
                    goto LABEL_152;
                }
                if ( *(_DWORD *)&a10[12 * v79 + 4] != 8 )
                  goto LABEL_152;
                v76 = **(HKEY **)&a10[12 * v79 + 8];
                if ( v76 == (HKEY)0xFFFFFFFFLL )
                  goto LABEL_152;
                v80 = 0;
                while ( 1 )
                {
                  v81 = 3LL * v80;
                  if ( !*(_DWORD *)&a10[12 * v80] && *(_DWORD *)&a10[12 * v80 + 2] == 1 )
                    break;
                  if ( ++v80 >= a9 )
                    goto LABEL_152;
                }
                v82 = *(_DWORD *)&a10[12 * v80 + 4];
                v83 = *(const wchar_t **)&a10[4 * v81 + 8];
                if ( v82 >= 4 )
                {
                  if ( v77 && *v60 == 92 )
                  {
                    ++v60;
                    v78 = v77 - 1;
                  }
                  v84 = v78 + 1;
                  if ( !v78 )
                    v84 = 0;
                  v85 = (v82 >> 1) + v84;
                  v86 = (wchar_t *)SafeSusAllocArray(v85, 2u);
                  v54 = v86;
                  if ( !v86 )
                  {
LABEL_167:
                    ExpressionID = -2147024882;
                    goto LABEL_175;
                  }
                  ExpressionID = StringCchCopyW(v86, v85, v83);
                  if ( ExpressionID >= 0 )
                  {
                    if ( !v78 )
                      goto LABEL_176;
                    ExpressionID = StringCchCatW(v54, v85, L"\\");
                    if ( ExpressionID >= 0 )
                    {
                      v88 = StringCchCatW(v54, v85, v60);
                      v87 = 0;
                      ExpressionID = v88;
                      if ( v88 >= 0 )
                      {
LABEL_179:
                        v68 = v275;
LABEL_180:
                        if ( (_WORD)v87 != *v54 )
                        {
                          WUTrace(
                            0,
                            0,
                            0x100000,
                            5,
                            v87,
                            L"  EE: Evaluating WUv4RegKeyValue: subkey=%ws, data=%ws",
                            v54,
                            v68);
                          ExpressionID = WUv4RegKeyValueMatch(Type, v76, v54, (const wchar_t *)hKey, v68, (int *)&v282);
                          if ( ExpressionID >= 0 )
                            *(_DWORD *)a11 = v282 != 0;
                          goto LABEL_185;
                        }
                        goto LABEL_183;
                      }
                    }
                  }
                }
                else
                {
LABEL_152:
                  ExpressionID = -2145067006;
                }
LABEL_175:
                SusFree(v54);
                v87 = 0;
                v54 = 0;
                v76 = 0;
LABEL_176:
                if ( ExpressionID < 0 )
                {
                  *(_DWORD *)a11 = -1;
                  goto LABEL_185;
                }
                if ( v54 )
                  goto LABEL_179;
LABEL_183:
                ExpressionID = -2145067002;
                goto LABEL_185;
              }
              v89 = v77 + 1;
              v90 = (wchar_t *)SafeSusAllocArray(v89, 2u);
              v54 = v90;
              if ( v90 )
              {
                ExpressionID = StringCchCopyW(v90, (unsigned int)v89, v60);
                if ( ExpressionID >= 0 )
                  goto LABEL_180;
                goto LABEL_175;
              }
              goto LABEL_167;
            }
            v91 = 0;
            *(_DWORD *)a11 = -1;
            if ( !*((_DWORD *)a2 + 6) || (v92 = *((_QWORD *)a2 + 1)) == 0 )
            {
              ExpressionID = -2145067003;
              goto LABEL_237;
            }
            v93 = *(_DWORD *)(v92 + 8);
            v94 = 0;
            v95 = 0;
            if ( v93 )
            {
              v96 = *((_QWORD *)a2 + 2);
              while ( *(_DWORD *)(v96 + 24LL * v95) != 51 )
              {
                if ( ++v95 >= v93 )
                  goto LABEL_196;
              }
              if ( *(_DWORD *)(v96 + 24LL * v95 + 8) != 10 )
                goto LABEL_223;
              v94 = (HKEY *)(v96 + 16 + 24LL * v95);
            }
LABEL_196:
            v97 = 0;
            v98 = 0;
            v99 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
            if ( v99 )
            {
              v100 = *((_QWORD *)a2 + 2);
              while ( *(_DWORD *)(v100 + 24LL * v98) != 52 )
              {
                if ( ++v98 >= v99 )
                  goto LABEL_203;
              }
              if ( *(_DWORD *)(v100 + 24LL * v98 + 8) != 8 )
                goto LABEL_223;
              v97 = *(wchar_t **)(v100 + 24LL * v98 + 16);
            }
LABEL_203:
            v101 = 0;
            v102 = 0;
            v103 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
            if ( v103 )
            {
              v104 = *((_QWORD *)a2 + 2);
              while ( *(_DWORD *)(v104 + 24LL * v102) != 53 )
              {
                if ( ++v102 >= v103 )
                  goto LABEL_210;
              }
              if ( *(_DWORD *)(v104 + 24LL * v102 + 8) != 8 )
                goto LABEL_223;
              v101 = *(wchar_t **)(v104 + 24LL * v102 + 16);
            }
LABEL_210:
            v105 = 0;
            v106 = 0;
            v107 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
            if ( v107 )
            {
              v108 = *((_QWORD *)a2 + 2);
              while ( *(_DWORD *)(v108 + 24LL * v106) != 54 )
              {
                if ( ++v106 >= v107 )
                  goto LABEL_217;
              }
              if ( *(_DWORD *)(v108 + 24LL * v106 + 8) != 14 )
                goto LABEL_223;
              v105 = (enum StringComparison *)(v108 + 16 + 24LL * v106);
            }
LABEL_217:
            v109 = 0;
            v110 = 0;
            v111 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
            if ( v111 )
            {
              v112 = *((_QWORD *)a2 + 2);
              while ( *(_DWORD *)(v112 + 24LL * v110) != 55 )
              {
                if ( ++v110 >= v111 )
                  goto LABEL_225;
              }
              if ( *(_DWORD *)(v112 + 24LL * v110 + 8) != 8 )
              {
LABEL_223:
                ExpressionID = -2147024809;
LABEL_237:
                LODWORD(v273) = ExpressionID;
                v269 = (wchar_t *)ResultToString(*(unsigned int *)a11);
                v118 = L"  EE: RegSz evaluated to %ws, return hr=%#lx";
LABEL_238:
                WUTrace(0, 0, 0x100000, 5, v117, v118, v269, v273);
                goto LABEL_546;
              }
              v109 = *(wchar_t **)(v112 + 24LL * v110 + 16);
            }
LABEL_225:
            v113 = 0;
            v114 = 0;
            v115 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
            if ( v115 )
            {
              v116 = *((_QWORD *)a2 + 2);
              while ( *(_DWORD *)(v116 + 24LL * v114) != 154 )
              {
                if ( ++v114 >= v115 )
                  goto LABEL_233;
              }
              if ( *(_DWORD *)(v116 + 24LL * v114 + 8) != 7 )
              {
                ExpressionID = -2147024809;
                goto LABEL_237;
              }
              v113 = (_WORD *)(v116 + 16 + 24LL * v114);
            }
LABEL_233:
            if ( v113 )
              LOBYTE(v91) = *v113 == 0xFFFF;
            ExpressionID = CRegExprEvaluator::CompareRegSzToString(
                             0,
                             v91,
                             v94,
                             v97,
                             v101,
                             v105,
                             v109,
                             0,
                             (const struct CExpressionVariableData *const)v278,
                             a11);
            goto LABEL_237;
          }
          v119 = 0;
          *(_DWORD *)a11 = -1;
          if ( !*((_DWORD *)a2 + 6) || (v120 = *((_QWORD *)a2 + 1)) == 0 )
          {
            ExpressionID = -2145067003;
            goto LABEL_289;
          }
          v121 = *(_DWORD *)(v120 + 8);
          v122 = 0;
          v123 = 0;
          if ( v121 )
          {
            v124 = *((_QWORD *)a2 + 2);
            while ( *(_DWORD *)(v124 + 24LL * v123) != 98 )
            {
              if ( ++v123 >= v121 )
                goto LABEL_248;
            }
            if ( *(_DWORD *)(v124 + 24LL * v123 + 8) != 10 )
              goto LABEL_275;
            v122 = (HKEY *)(v124 + 16 + 24LL * v123);
          }
LABEL_248:
          v125 = 0;
          v126 = 0;
          v127 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
          if ( v127 )
          {
            v128 = *((_QWORD *)a2 + 2);
            while ( *(_DWORD *)(v128 + 24LL * v126) != 99 )
            {
              if ( ++v126 >= v127 )
                goto LABEL_255;
            }
            if ( *(_DWORD *)(v128 + 24LL * v126 + 8) != 8 )
              goto LABEL_275;
            v125 = *(wchar_t **)(v128 + 24LL * v126 + 16);
          }
LABEL_255:
          v129 = 0;
          v130 = 0;
          v131 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
          if ( v131 )
          {
            v132 = *((_QWORD *)a2 + 2);
            while ( *(_DWORD *)(v132 + 24LL * v130) != 100 )
            {
              if ( ++v130 >= v131 )
                goto LABEL_262;
            }
            if ( *(_DWORD *)(v132 + 24LL * v130 + 8) != 8 )
              goto LABEL_275;
            v129 = *(wchar_t **)(v132 + 24LL * v130 + 16);
          }
LABEL_262:
          v133 = 0;
          v134 = 0;
          v135 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
          if ( v135 )
          {
            v136 = *((_QWORD *)a2 + 2);
            while ( *(_DWORD *)(v136 + 24LL * v134) != 101 )
            {
              if ( ++v134 >= v135 )
                goto LABEL_269;
            }
            if ( *(_DWORD *)(v136 + 24LL * v134 + 8) != 14 )
              goto LABEL_275;
            v133 = (enum StringComparison *)(v136 + 16 + 24LL * v134);
          }
LABEL_269:
          v137 = 0;
          v138 = 0;
          v139 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
          if ( v139 )
          {
            v140 = *((_QWORD *)a2 + 2);
            while ( *(_DWORD *)(v140 + 24LL * v138) != 102 )
            {
              if ( ++v138 >= v139 )
                goto LABEL_277;
            }
            if ( *(_DWORD *)(v140 + 24LL * v138 + 8) != 8 )
            {
LABEL_275:
              ExpressionID = -2147024809;
LABEL_289:
              LODWORD(v273) = ExpressionID;
              v269 = (wchar_t *)ResultToString(*(unsigned int *)a11);
              v118 = L"  EE: RegExpandSz evaluated to %ws, return hr=%#lx";
              goto LABEL_238;
            }
            v137 = *(wchar_t **)(v140 + 24LL * v138 + 16);
          }
LABEL_277:
          v141 = 0;
          v142 = 0;
          v143 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
          if ( v143 )
          {
            v144 = *((_QWORD *)a2 + 2);
            while ( *(_DWORD *)(v144 + 24LL * v142) != 160 )
            {
              if ( ++v142 >= v143 )
                goto LABEL_285;
            }
            if ( *(_DWORD *)(v144 + 24LL * v142 + 8) != 7 )
            {
              ExpressionID = -2147024809;
              goto LABEL_289;
            }
            v141 = (_WORD *)(v144 + 16 + 24LL * v142);
          }
LABEL_285:
          if ( v141 )
            LOBYTE(v119) = *v141 == 0xFFFF;
          ExpressionID = CRegExprEvaluator::CompareRegSzToString(
                           0,
                           v119,
                           v122,
                           v125,
                           v129,
                           v133,
                           v137,
                           1,
                           (const struct CExpressionVariableData *const)v278,
                           a11);
          goto LABEL_289;
        }
        v145 = 0;
        hKey = 0;
        Type = 0;
        v282 = 0;
        *(_DWORD *)a11 = -1;
        if ( !*((_DWORD *)a2 + 6) || (v146 = *((_QWORD *)a2 + 1)) == 0 )
        {
          ExpressionID = -2145067003;
          goto LABEL_382;
        }
        v147 = *(_DWORD *)(v146 + 8);
        v148 = 0;
        v149 = 0;
        if ( v147 )
        {
          v150 = *((_QWORD *)a2 + 2);
          while ( *(_DWORD *)(v150 + 24LL * v149) != 57 )
          {
            if ( ++v149 >= v147 )
              goto LABEL_300;
          }
          if ( *(_DWORD *)(v150 + 24LL * v149 + 8) != 10 )
            goto LABEL_298;
          v148 = (HKEY *)(v150 + 16 + 24LL * v149);
        }
LABEL_300:
        v151 = 0;
        v152 = 0;
        v153 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
        if ( v153 )
        {
          v154 = *((_QWORD *)a2 + 2);
          while ( *(_DWORD *)(v154 + 24LL * v152) != 58 )
          {
            if ( ++v152 >= v153 )
              goto LABEL_307;
          }
          if ( *(_DWORD *)(v154 + 24LL * v152 + 8) != 8 )
            goto LABEL_298;
          v151 = *(OLECHAR **)(v154 + 24LL * v152 + 16);
        }
LABEL_307:
        v155 = *((_QWORD *)a2 + 1);
        v156 = 0;
        v278[0] = 0;
        v157 = *(_DWORD *)(v155 + 8);
        if ( v157 )
        {
          v158 = *((_QWORD *)a2 + 2);
          while ( *(_DWORD *)(v158 + 24LL * v156) != 59 )
          {
            if ( ++v156 >= v157 )
              goto LABEL_314;
          }
          if ( *(_DWORD *)(v158 + 24LL * v156 + 8) != 8 )
            goto LABEL_298;
          v278[0] = *(wchar_t **)(v158 + 24LL * v156 + 16);
        }
LABEL_314:
        v159 = *((_QWORD *)a2 + 1);
        v160 = 0;
        pbstr = 0;
        v161 = 0;
        v162 = *(_DWORD *)(v159 + 8);
        if ( v162 )
        {
          v163 = *((_QWORD *)a2 + 2);
          while ( *(_DWORD *)(v163 + 24LL * v161) != 60 )
          {
            if ( ++v161 >= v162 )
              goto LABEL_321;
          }
          if ( *(_DWORD *)(v163 + 24LL * v161 + 8) != 12 )
            goto LABEL_298;
          v160 = (OLECHAR *)(v163 + 16 + 24LL * v161);
          pbstr = v160;
        }
LABEL_321:
        v164 = 0;
        v276 = 0;
        v165 = 0;
        v166 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
        if ( v166 )
        {
          v167 = *((_QWORD *)a2 + 2);
          while ( *(_DWORD *)(v167 + 24LL * v165) != 61 )
          {
            if ( ++v165 >= v166 )
              goto LABEL_328;
          }
          if ( *(_DWORD *)(v167 + 24LL * v165 + 8) != 2 )
            goto LABEL_298;
          v164 = (unsigned int *)(v167 + 16 + 24LL * v165);
          v276 = v164;
        }
LABEL_328:
        v168 = 0;
        v169 = 0;
        v170 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
        if ( !v170 )
          goto LABEL_335;
        v171 = *((_QWORD *)a2 + 2);
        while ( *(_DWORD *)(v171 + 24LL * v169) != 155 )
        {
          if ( ++v169 >= v170 )
            goto LABEL_335;
        }
        if ( *(_DWORD *)(v171 + 24LL * v169 + 8) == 7 )
        {
          v168 = (_WORD *)(v171 + 16 + 24LL * v169);
LABEL_335:
          if ( v168 )
            Type = *v168 == 0xFFFF;
          if ( !v148 || !v160 || !v164 )
            goto LABEL_380;
          v172 = *v148;
          v173 = SysStringLen(v151);
          if ( v172 == (HKEY)0xFFFFFFFFLL )
          {
            v174 = v173;
            v175 = 0;
            if ( !a9 )
              goto LABEL_345;
            while ( *(_DWORD *)&a10[12 * v175] || *(_DWORD *)&a10[12 * v175 + 2] )
            {
              if ( ++v175 >= a9 )
                goto LABEL_345;
            }
            v177 = *(HKEY **)&a10[12 * v175 + 8];
            if ( *(_DWORD *)&a10[12 * v175 + 4] != 8 )
              goto LABEL_345;
            v172 = *v177;
            if ( *v177 == (HKEY)0xFFFFFFFFLL )
              goto LABEL_345;
            v178 = 0;
            while ( 1 )
            {
              v179 = 3LL * v178;
              if ( !*(_DWORD *)&a10[12 * v178] && *(_DWORD *)&a10[12 * v178 + 2] == 1 )
                break;
              if ( ++v178 >= a9 )
                goto LABEL_345;
            }
            v180 = *(_DWORD *)&a10[12 * v178 + 4];
            v181 = *(const wchar_t **)&a10[4 * v179 + 8];
            if ( v180 >= 4 )
            {
              if ( v174 && *v151 == 92 )
              {
                ++v151;
                --v174;
              }
              v182 = v174 + 1;
              if ( !v174 )
                v182 = 0;
              v183 = (v180 >> 1) + v182;
              v184 = (wchar_t *)SafeSusAllocArray(v183, 2u);
              v145 = v184;
              if ( !v184 )
              {
LABEL_360:
                v176 = -2147024882;
                goto LABEL_368;
              }
              v176 = StringCchCopyW(v184, v183, v181);
              if ( v176 >= 0 )
              {
                if ( !v174 )
                  goto LABEL_369;
                v176 = StringCchCatW(v145, v183, L"\\");
                if ( v176 >= 0 )
                {
                  v186 = StringCchCatW(v145, v183, v151);
                  v185 = 0;
                  v176 = v186;
                  if ( v186 >= 0 )
                  {
                    ExpressionID = v186;
LABEL_372:
                    v164 = v276;
LABEL_373:
                    if ( (_WORD)v185 != *v145 )
                    {
                      v190 = v278[0];
                      WUTrace(
                        0,
                        0,
                        0x100000,
                        5,
                        v185,
                        L"  EE: Evaluating RegDword: Subkey=%ws, value=%ws, data=%lu",
                        v145,
                        v278[0],
                        *v164);
                      if ( !RegOpenKeyExW(v172, v145, 0, (Type << 9) | 1, &hKey) )
                      {
                        v191 = v282;
                        if ( !hKey )
                        {
LABEL_379:
                          v192 = PerformScalarComparison<unsigned long>(v191, *(unsigned int *)pbstr, *v164);
                          v189 = a11;
                          *(_DWORD *)a11 = v192;
                          goto LABEL_383;
                        }
                        if ( RegQueryDwordValue(hKey, v190, &v282) < 0 )
                        {
                          v282 = v191;
                          goto LABEL_379;
                        }
                      }
                      v191 = v282;
                      goto LABEL_379;
                    }
LABEL_380:
                    ExpressionID = -2145067002;
                    goto LABEL_382;
                  }
                }
              }
            }
            else
            {
LABEL_345:
              v176 = -2145067006;
            }
LABEL_368:
            SusFree(v145);
            v185 = 0;
            v145 = 0;
            v172 = 0;
LABEL_369:
            ExpressionID = v176;
            if ( v176 < 0 )
            {
              v189 = a11;
              *(_DWORD *)a11 = -1;
LABEL_383:
              SusFree(v145);
              if ( hKey )
                RegCloseKey(hKey);
              LODWORD(v273) = ExpressionID;
              v270 = (wchar_t *)ResultToString(*(unsigned int *)v189);
              WUTrace(0, 0, 0x100000, 5, 0, L"  EE: RegDword evaluated to %ws, return hr=%#lx", v270, v273);
              goto LABEL_546;
            }
            if ( !v145 )
              goto LABEL_380;
            goto LABEL_372;
          }
          v187 = v173 + 1;
          v188 = (wchar_t *)SafeSusAllocArray(v187, 2u);
          v145 = v188;
          if ( v188 )
          {
            v176 = StringCchCopyW(v188, (unsigned int)v187, v151);
            ExpressionID = v176;
            if ( v176 >= 0 )
              goto LABEL_373;
            goto LABEL_368;
          }
          goto LABEL_360;
        }
LABEL_298:
        ExpressionID = -2147024809;
LABEL_382:
        v189 = a11;
        goto LABEL_383;
      }
      v193 = a11;
      v194 = 0;
      hKey = 0;
      Type = 0;
      *(_DWORD *)a11 = 0;
      if ( !*((_DWORD *)a2 + 6) || (v195 = *((_QWORD *)a2 + 1)) == 0 )
      {
        ExpressionID = -2145067003;
        goto LABEL_418;
      }
      v196 = *(_DWORD *)(v195 + 8);
      v197 = 0;
      v198 = 0;
      if ( v196 )
      {
        v199 = *((_QWORD *)a2 + 2);
        while ( *(_DWORD *)(v199 + 24LL * v198) != 19 )
        {
          if ( ++v198 >= v196 )
            goto LABEL_395;
        }
        if ( *(_DWORD *)(v199 + 24LL * v198 + 8) != 10 )
          goto LABEL_425;
        v197 = (HKEY *)(v199 + 16 + 24LL * v198);
      }
LABEL_395:
      v200 = 0;
      v201 = 0;
      v202 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
      if ( v202 )
      {
        v203 = *((_QWORD *)a2 + 2);
        while ( *(_DWORD *)(v203 + 24LL * v201) != 20 )
        {
          if ( ++v201 >= v202 )
            goto LABEL_402;
        }
        if ( *(_DWORD *)(v203 + 24LL * v201 + 8) != 8 )
          goto LABEL_425;
        v200 = *(OLECHAR **)(v203 + 24LL * v201 + 16);
      }
LABEL_402:
      v204 = *((_QWORD *)a2 + 1);
      v205 = 0;
      pbstr = 0;
      v206 = *(_DWORD *)(v204 + 8);
      if ( v206 )
      {
        v207 = *((_QWORD *)a2 + 2);
        while ( *(_DWORD *)(v207 + 24LL * v205) != 21 )
        {
          if ( ++v205 >= v206 )
            goto LABEL_409;
        }
        if ( *(_DWORD *)(v207 + 24LL * v205 + 8) != 8 )
          goto LABEL_425;
        pbstr = *(BSTR *)(v207 + 24LL * v205 + 16);
      }
LABEL_409:
      v208 = *((_QWORD *)a2 + 1);
      v209 = 0;
      v278[0] = 0;
      v210 = *(_DWORD *)(v208 + 8);
      if ( v210 )
      {
        v211 = *((_QWORD *)a2 + 2);
        while ( *(_DWORD *)(v211 + 24LL * v209) != 22 )
        {
          if ( ++v209 >= v210 )
            goto LABEL_416;
        }
        if ( *(_DWORD *)(v211 + 24LL * v209 + 8) != 11 )
          goto LABEL_425;
        v278[0] = (wchar_t *)(v211 + 16 + 24LL * v209);
      }
LABEL_416:
      if ( !v197 )
      {
        ExpressionID = -2145067002;
LABEL_418:
        v212 = a11;
LABEL_467:
        SusFree(v194);
        if ( hKey )
          RegCloseKey(hKey);
        LODWORD(v273) = ExpressionID;
        v271 = (wchar_t *)ResultToString(*(unsigned int *)v212);
        WUTrace(0, 0, 0x100000, 5, 0, L"  EE: RegValueExists evaluated to %ws, return hr=%#lx", v271, v273);
        goto LABEL_546;
      }
      v213 = 0;
      v214 = 0;
      v215 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
      if ( v215 )
      {
        v216 = *((_QWORD *)a2 + 2);
        while ( *(_DWORD *)(v216 + 24LL * v214) != 150 )
        {
          if ( ++v214 >= v215 )
            goto LABEL_427;
        }
        if ( *(_DWORD *)(v216 + 24LL * v214 + 8) != 7 )
        {
LABEL_425:
          ExpressionID = -2147024809;
          goto LABEL_418;
        }
        v213 = (_WORD *)(v216 + 16 + 24LL * v214);
      }
LABEL_427:
      if ( v213 )
        Type = *v213 == 0xFFFF;
      v217 = *v197;
      v218 = SysStringLen(v200);
      if ( v217 == (HKEY)0xFFFFFFFFLL )
      {
        v219 = v218;
        v220 = 0;
        if ( !a9 )
          goto LABEL_434;
        while ( *(_DWORD *)&a10[12 * v220] || *(_DWORD *)&a10[12 * v220 + 2] )
        {
          if ( ++v220 >= a9 )
            goto LABEL_434;
        }
        if ( *(_DWORD *)&a10[12 * v220 + 4] != 8 )
          goto LABEL_434;
        v217 = **(HKEY **)&a10[12 * v220 + 8];
        if ( v217 == (HKEY)0xFFFFFFFFLL )
          goto LABEL_434;
        v222 = 0;
        while ( 1 )
        {
          v223 = 3LL * v222;
          if ( !*(_DWORD *)&a10[12 * v222] && *(_DWORD *)&a10[12 * v222 + 2] == 1 )
            break;
          if ( ++v222 >= a9 )
            goto LABEL_434;
        }
        v224 = *(_DWORD *)&a10[12 * v222 + 4];
        v225 = *(const wchar_t **)&a10[4 * v223 + 8];
        if ( v224 >= 4 )
        {
          if ( v218 && *v200 == 92 )
          {
            ++v200;
            v219 = v218 - 1;
          }
          v226 = v219 + 1;
          if ( !v219 )
            v226 = 0;
          v227 = (v224 >> 1) + v226;
          v228 = (wchar_t *)SafeSusAllocArray(v227, 2u);
          v194 = v228;
          if ( !v228 )
          {
LABEL_449:
            v221 = -2147024882;
            goto LABEL_457;
          }
          v221 = StringCchCopyW(v228, v227, v225);
          if ( v221 >= 0 )
          {
            if ( !v219 )
              goto LABEL_458;
            v221 = StringCchCatW(v194, v227, L"\\");
            if ( v221 >= 0 )
            {
              v230 = StringCchCatW(v194, v227, v200);
              v229 = 0;
              v221 = v230;
              if ( v230 >= 0 )
              {
                ExpressionID = v230;
LABEL_461:
                v193 = a11;
LABEL_462:
                if ( (_WORD)v229 != *v194 )
                {
                  WUTrace(
                    0,
                    0,
                    0x100000,
                    5,
                    v229,
                    L"  EE: Evaluating RegValueExists expression: Key=%p, Subkey=%ws",
                    v217,
                    v194);
                  if ( !RegOpenKeyExW(v217, v194, 0, (Type << 9) | 1, &hKey) )
                  {
                    Type = 0;
                    WUTrace(0, 0, 0x100000, 5, 0, L"RegValueExists: Opened Subkey %ws successfully", v194);
                    v233 = pbstr;
                    if ( !SysStringLen(pbstr) )
                      goto LABEL_465;
                    if ( !RegQueryValueExW(hKey, v233, 0, &Type, 0, 0) )
                    {
                      WUTrace(0, 0, 0x100000, 5, 0, L"RegValueExists: Queried value %ws successfully", v233);
                      v234 = 1;
                      if ( v278[0] )
                        v234 = *(_DWORD *)v278[0];
                      if ( Type == v234 )
LABEL_465:
                        *(_DWORD *)v193 = 1;
                    }
                  }
                  goto LABEL_466;
                }
LABEL_475:
                ExpressionID = -2145067002;
LABEL_466:
                v212 = a11;
                goto LABEL_467;
              }
            }
          }
        }
        else
        {
LABEL_434:
          v221 = -2145067006;
        }
LABEL_457:
        SusFree(v194);
        v229 = 0;
        v194 = 0;
        v217 = 0;
LABEL_458:
        ExpressionID = v221;
        if ( v221 < 0 )
        {
          v212 = a11;
          *(_DWORD *)a11 = -1;
          goto LABEL_467;
        }
        if ( !v194 )
          goto LABEL_475;
        goto LABEL_461;
      }
      v231 = v218 + 1;
      v232 = (wchar_t *)SafeSusAllocArray(v231, 2u);
      v194 = v232;
      if ( v232 )
      {
        v221 = StringCchCopyW(v232, (unsigned int)v231, v200);
        ExpressionID = v221;
        if ( v221 >= 0 )
          goto LABEL_462;
        goto LABEL_457;
      }
      goto LABEL_449;
    }
    v235 = 0;
    pbstr = 0;
    Type = 0;
    *(_DWORD *)a11 = 0;
    if ( !*((_DWORD *)a2 + 6) || (v236 = *((_QWORD *)a2 + 1)) == 0 )
    {
      ExpressionID = -2145067003;
      goto LABEL_541;
    }
    v237 = *(_DWORD *)(v236 + 8);
    v238 = 0;
    v239 = 0;
    if ( v237 )
    {
      v240 = *((_QWORD *)a2 + 2);
      while ( *(_DWORD *)(v240 + 24LL * v239) != 17 )
      {
        if ( ++v239 >= v237 )
          goto LABEL_487;
      }
      if ( *(_DWORD *)(v240 + 24LL * v239 + 8) != 10 )
        goto LABEL_485;
      v238 = (HKEY *)(v240 + 16 + 24LL * v239);
    }
LABEL_487:
    v241 = 0;
    v242 = 0;
    v243 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
    if ( v243 )
    {
      v244 = *((_QWORD *)a2 + 2);
      while ( *(_DWORD *)(v244 + 24LL * v242) != 18 )
      {
        if ( ++v242 >= v243 )
          goto LABEL_494;
      }
      if ( *(_DWORD *)(v244 + 24LL * v242 + 8) != 8 )
        goto LABEL_485;
      v241 = *(OLECHAR **)(v244 + 24LL * v242 + 16);
    }
LABEL_494:
    v245 = 0;
    v246 = 0;
    v247 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
    if ( !v247 )
      goto LABEL_501;
    v248 = *((_QWORD *)a2 + 2);
    while ( *(_DWORD *)(v248 + 24LL * v246) != 149 )
    {
      if ( ++v246 >= v247 )
        goto LABEL_501;
    }
    if ( *(_DWORD *)(v248 + 24LL * v246 + 8) == 7 )
    {
      v245 = (_WORD *)(v248 + 16 + 24LL * v246);
LABEL_501:
      if ( v245 )
        Type = *v245 == 0xFFFF;
      if ( !v238 )
        goto LABEL_504;
      v249 = *v238;
      v250 = SysStringLen(v241);
      if ( v249 == (HKEY)0xFFFFFFFFLL )
      {
        v251 = v250;
        v252 = 0;
        if ( !a9 )
          goto LABEL_510;
        while ( *(_DWORD *)&a10[12 * v252] || *(_DWORD *)&a10[12 * v252 + 2] )
        {
          if ( ++v252 >= a9 )
            goto LABEL_510;
        }
        if ( *(_DWORD *)&a10[12 * v252 + 4] != 8 )
          goto LABEL_510;
        v249 = **(HKEY **)&a10[12 * v252 + 8];
        if ( v249 == (HKEY)0xFFFFFFFFLL )
          goto LABEL_510;
        v254 = 0;
        while ( 1 )
        {
          v255 = 3LL * v254;
          if ( !*(_DWORD *)&a10[12 * v254] && *(_DWORD *)&a10[12 * v254 + 2] == 1 )
            break;
          if ( ++v254 >= a9 )
            goto LABEL_510;
        }
        v256 = *(_DWORD *)&a10[12 * v254 + 4];
        v257 = *(const wchar_t **)&a10[4 * v255 + 8];
        if ( v256 >= 4 )
        {
          if ( v251 && *v241 == 92 )
          {
            ++v241;
            --v251;
          }
          v258 = v251 + 1;
          if ( !v251 )
            v258 = 0;
          v259 = (v256 >> 1) + v258;
          v260 = (wchar_t *)SafeSusAllocArray(v259, 2u);
          v235 = v260;
          if ( !v260 )
          {
LABEL_525:
            v253 = -2147024882;
            goto LABEL_533;
          }
          v253 = StringCchCopyW(v260, v259, v257);
          if ( v253 >= 0 )
          {
            if ( !v251 )
              goto LABEL_534;
            v253 = StringCchCatW(v235, v259, L"\\");
            if ( v253 >= 0 )
            {
              v262 = StringCchCatW(v235, v259, v241);
              v261 = 0;
              v253 = v262;
              if ( v262 >= 0 )
              {
                ExpressionID = v262;
                goto LABEL_537;
              }
            }
          }
        }
        else
        {
LABEL_510:
          v253 = -2145067006;
        }
LABEL_533:
        SusFree(v235);
        v261 = 0;
        v235 = 0;
        v249 = 0;
LABEL_534:
        ExpressionID = v253;
        if ( v253 < 0 )
        {
          v265 = a11;
          *(_DWORD *)a11 = -1;
          goto LABEL_542;
        }
        if ( !v235 )
        {
LABEL_504:
          ExpressionID = -2145067002;
          goto LABEL_541;
        }
LABEL_537:
        if ( (_WORD)v261 != *v235 )
        {
          WUTrace(0, 0, 0x100000, 5, v261, L"  EE: Evaluating RegKeyExists expression: Key=%p, Subkey=%ls", v249, v235);
          if ( RegOpenKeyExW(v249, v235, 0, (Type << 9) | 1, (PHKEY)&pbstr) )
            goto LABEL_541;
          v265 = a11;
          *(_DWORD *)a11 = 1;
LABEL_542:
          SusFree(v235);
          if ( pbstr )
            RegCloseKey((HKEY)pbstr);
          LODWORD(v273) = ExpressionID;
          v272 = (wchar_t *)ResultToString(*(unsigned int *)v265);
          WUTrace(0, 0, 0x100000, 5, 0, L"  EE: RegKeyExists evaluated to %ws, return hr=%#lx", v272, v273);
          goto LABEL_546;
        }
        goto LABEL_504;
      }
      v263 = v250 + 1;
      v264 = (wchar_t *)SafeSusAllocArray(v263, 2u);
      v235 = v264;
      if ( v264 )
      {
        v253 = StringCchCopyW(v264, (unsigned int)v263, v241);
        ExpressionID = v253;
        if ( v253 >= 0 )
          goto LABEL_537;
        goto LABEL_533;
      }
      goto LABEL_525;
    }
LABEL_485:
    ExpressionID = -2147024809;
LABEL_541:
    v265 = a11;
    goto LABEL_542;
  }
LABEL_546:
  LODWORD(v273) = ExpressionID;
  LODWORD(v266) = v277;
  WUTrace(0, 0, 0x100000, 5, 0, L"Evaluation of expression: %lu returned hr=%#lx", v266, v273);
  return (unsigned int)ExpressionID;
}

```

## disassembly

```asm
0x18022b030  mov     [rsp-8+arg_0], rbx
0x18022b035  push    rbp
0x18022b036  push    rsi
0x18022b037  push    rdi
0x18022b038  push    r12
0x18022b03a  push    r13
0x18022b03c  push    r14
0x18022b03e  push    r15
0x18022b040  lea     rbp, [rsp-7]
0x18022b045  sub     rsp, 0A0h
0x18022b04c  mov     rax, cs:__security_cookie
0x18022b053  xor     rax, rsp
0x18022b056  mov     [rbp+37h+var_40], rax
0x18022b05a  mov     rax, [rbp+37h+arg_38]
0x18022b05e  mov     rdi, rdx
0x18022b061  mov     rsi, [rbp+37h+arg_28]
0x18022b065  xor     edx, edx
0x18022b067  mov     r13, [rbp+37h+arg_30]
0x18022b06b  mov     r12, r9
0x18022b06e  mov     [rbp+37h+pbstr], rax
0x18022b072  mov     r15, r8
0x18022b075  mov     rax, [rbp+37h+arg_50]
0x18022b07c  mov     [rbp+37h+var_80], rax
0x18022b080  mov     [rbp+37h+var_70], edx
0x18022b083  test    rax, rax
0x18022b086  jz      short loc_18022B0A1
0x18022b088  mov     dword ptr [rax], 0FFFFFFFFh
0x18022b08e  test    rdi, rdi
0x18022b091  jz      short loc_18022B0A1
0x18022b093  mov     r14d, [rbp+37h+arg_20]
0x18022b097  test    r14d, r14d
0x18022b09a  jz      short loc_18022B0CD
0x18022b09c  test    rsi, rsi
0x18022b09f  jnz     short loc_18022B0D2
0x18022b0a1  mov     eax, 80070057h
0x18022b0a6  mov     rcx, [rbp+37h+var_40]
0x18022b0aa  xor     rcx, rsp; StackCookie
0x18022b0ad  call    __security_check_cookie
0x18022b0b2  mov     rbx, [rsp+0D0h+arg_0]
0x18022b0ba  add     rsp, 0A0h
0x18022b0c1  pop     r15
0x18022b0c3  pop     r14
0x18022b0c5  pop     r13
0x18022b0c7  pop     r12
0x18022b0c9  pop     rdi
0x18022b0ca  pop     rsi
0x18022b0cb  pop     rbp
0x18022b0cc  retn
0x18022b0cd  test    rsi, rsi
0x18022b0d0  jnz     short loc_18022B0A1
0x18022b0d2  mov     ecx, [rbp+37h+arg_40]
0x18022b0d8  mov     rax, [rbp+37h+arg_48]
0x18022b0df  test    ecx, ecx
0x18022b0e1  jz      short loc_18022B0EA
0x18022b0e3  test    rax, rax
0x18022b0e6  jz      short loc_18022B0A1
0x18022b0e8  jmp     short loc_18022B0EF
0x18022b0ea  test    rax, rax
0x18022b0ed  jnz     short loc_18022B0A1
0x18022b0ef  mov     dword ptr [rbp+37h+var_68+4], edx
0x18022b0f2  lea     rdx, [rbp+37h+var_70]; enum ExpressionIDEnum *
0x18022b0f6  mov     dword ptr [rbp+37h+var_68], ecx
0x18022b0f9  mov     rcx, rdi; this
0x18022b0fc  mov     [rbp+37h+var_60], rax
0x18022b100  call    ?GetExpressionID@CExprDeserializer@@QEBAJPEAW4ExpressionIDEnum@@@Z; CExprDeserializer::GetExpressionID(ExpressionIDEnum *)
0x18022b105  xor     r10d, r10d
0x18022b108  mov     ebx, eax
0x18022b10a  test    eax, eax
0x18022b10c  js      loc_18022CA4D
0x18022b112  mov     ecx, [rbp+37h+var_70]
0x18022b115  sub     ecx, 12h
0x18022b118  jz      loc_18022C6DF
0x18022b11e  sub     ecx, 1
0x18022b121  jz      loc_18022C250
0x18022b127  sub     ecx, 2
0x18022b12a  jz      loc_18022BDC9
0x18022b130  sub     ecx, 1
0x18022b133  jz      loc_18022BBA9
0x18022b139  sub     ecx, 1
0x18022b13c  jz      loc_18022B981
0x18022b142  sub     ecx, 1; this
0x18022b145  jz      loc_18022B96C
0x18022b14b  sub     ecx, 1
0x18022b14e  jz      loc_18022B590
0x18022b154  sub     ecx, 1
0x18022b157  jz      short loc_18022B1A7
0x18022b159  cmp     ecx, 0Eh
0x18022b15c  jz      short loc_18022B168
0x18022b15e  mov     ebx, 8024E001h
0x18022b163  jmp     loc_18022CA4D
0x18022b168  mov     rcx, [rbp+37h+var_80]; this
0x18022b16c  lea     rax, [rbp+37h+var_68]
0x18022b170  mov     [rsp+0D0h+var_88], rcx; enum tagSusRuleResult *
0x18022b175  mov     r9, r12; struct tagDSGlobalUpdateId *
0x18022b178  mov     [rsp+0D0h+var_90], rax; struct CExpressionVariableData *
0x18022b17d  mov     r8, r15; struct CCallerIdentity *
0x18022b180  mov     rax, [rbp+37h+pbstr]
0x18022b184  mov     rdx, rdi; struct CExprDeserializer *
0x18022b187  mov     [rsp+0D0h+var_98], rax; struct ISusExprEvaluate *
0x18022b18c  mov     [rsp+0D0h+var_A0], r13; struct tagSusRuleContext *
0x18022b191  mov     [rsp+0D0h+lpcbData], rsi; struct tagDSDataBlob *
0x18022b196  mov     dword ptr [rsp+0D0h+phkResult], r14d; unsigned int
0x18022b19b  call    ?EvaluateRegKeyLoop@CRegExprEvaluator@@AEBAJQEBVCExprDeserializer@@PEBVCCallerIdentity@@AEBUtagDSGlobalUpdateId@@KQEBUtagDSDataBlob@@AEBUtagSusRuleContext@@PEAUISusExprEvaluate@@QEBVCExpressionVariableData@@PEAW4tagSusRuleResult@@@Z; CRegExprEvaluator::EvaluateRegKeyLoop(CExprDeserializer const * const,CCallerIdentity const *,tagDSGlobalUpdateId const &,ulong,tagDSDataBlob const * const,tagSusRuleContext const &,ISusExprEvaluate *,CExpressionVariableData const * const,tagSusRuleResult *)
0x18022b1a0  mov     ebx, eax
0x18022b1a2  jmp     loc_18022CA4A
0x18022b1a7  mov     rax, [rbp+37h+var_80]
0x18022b1ab  mov     rsi, r10
0x18022b1ae  mov     [rbp+37h+var_44], r10d
0x18022b1b2  mov     [rbp+37h+Type], r10d
0x18022b1b6  mov     dword ptr [rax], 0FFFFFFFFh
0x18022b1bc  cmp     [rdi+18h], r10d
0x18022b1c0  jz      loc_18022B556
0x18022b1c6  mov     rax, [rdi+8]
0x18022b1ca  test    rax, rax
0x18022b1cd  jz      loc_18022B556
0x18022b1d3  mov     r9d, [rax+8]
0x18022b1d7  mov     r15, r10
0x18022b1da  mov     ecx, r10d
0x18022b1dd  mov     r14d, 1
0x18022b1e3  test    r9d, r9d
0x18022b1e6  jz      short loc_18022B217
0x18022b1e8  mov     rdx, [rdi+10h]
0x18022b1ec  mov     eax, ecx
0x18022b1ee  lea     r8, [rax+rax*2]
0x18022b1f2  cmp     dword ptr [rdx+r8*8], 21h ; '!'
0x18022b1f7  jz      short loc_18022B203
0x18022b1f9  add     ecx, r14d
0x18022b1fc  cmp     ecx, r9d
0x18022b1ff  jb      short loc_18022B1EC
0x18022b201  jmp     short loc_18022B217
0x18022b203  cmp     dword ptr [rdx+r8*8+8], 0Ah
0x18022b209  jnz     loc_18022B318
0x18022b20f  lea     r15, [rdx+10h]
0x18022b213  lea     r15, [r15+r8*8]
0x18022b217  mov     rax, [rdi+8]
0x18022b21b  mov     r13, r10
0x18022b21e  mov     ecx, r10d
0x18022b221  mov     r9d, [rax+8]
0x18022b225  test    r9d, r9d
0x18022b228  jz      short loc_18022B256
0x18022b22a  mov     r8, [rdi+10h]
0x18022b22e  mov     eax, ecx
0x18022b230  lea     rdx, [rax+rax*2]
0x18022b234  cmp     dword ptr [r8+rdx*8], 22h ; '"'
0x18022b239  jz      short loc_18022B245
0x18022b23b  add     ecx, r14d
0x18022b23e  cmp     ecx, r9d
0x18022b241  jb      short loc_18022B22E
0x18022b243  jmp     short loc_18022B256
0x18022b245  cmp     dword ptr [r8+rdx*8+8], 8
0x18022b24b  jnz     loc_18022B318
0x18022b251  mov     r13, [r8+rdx*8+10h]
0x18022b256  mov     rax, [rdi+8]
0x18022b25a  mov     ecx, r10d
0x18022b25d  mov     [rbp+37h+hKey], r10
0x18022b261  mov     r9d, [rax+8]
0x18022b265  test    r9d, r9d
0x18022b268  jz      short loc_18022B29A
0x18022b26a  mov     r8, [rdi+10h]
0x18022b26e  mov     eax, ecx
0x18022b270  lea     rdx, [rax+rax*2]
0x18022b274  cmp     dword ptr [r8+rdx*8], 23h ; '#'
0x18022b279  jz      short loc_18022B285
0x18022b27b  add     ecx, r14d
0x18022b27e  cmp     ecx, r9d
0x18022b281  jb      short loc_18022B26E
0x18022b283  jmp     short loc_18022B29A
0x18022b285  cmp     dword ptr [r8+rdx*8+8], 8
0x18022b28b  jnz     loc_18022B318
0x18022b291  mov     rax, [r8+rdx*8+10h]
0x18022b296  mov     [rbp+37h+hKey], rax
0x18022b29a  mov     rax, [rdi+8]
0x18022b29e  mov     r12, r10
0x18022b2a1  mov     [rbp+37h+var_78], r10
0x18022b2a5  mov     ecx, r10d
0x18022b2a8  mov     r9d, [rax+8]
0x18022b2ac  test    r9d, r9d
0x18022b2af  jz      short loc_18022B2DD
0x18022b2b1  mov     r8, [rdi+10h]
0x18022b2b5  mov     eax, ecx
0x18022b2b7  lea     rdx, [rax+rax*2]
0x18022b2bb  cmp     dword ptr [r8+rdx*8], 24h ; '$'
0x18022b2c0  jz      short loc_18022B2CC
0x18022b2c2  add     ecx, r14d
0x18022b2c5  cmp     ecx, r9d
0x18022b2c8  jb      short loc_18022B2B5
0x18022b2ca  jmp     short loc_18022B2DD
0x18022b2cc  cmp     dword ptr [r8+rdx*8+8], 8
0x18022b2d2  jnz     short loc_18022B318
0x18022b2d4  mov     r12, [r8+rdx*8+10h]
0x18022b2d9  mov     [rbp+37h+var_78], r12
0x18022b2dd  mov     rax, [rdi+8]
0x18022b2e1  mov     r9, r10
0x18022b2e4  mov     ecx, r10d
0x18022b2e7  xor     ebx, ebx
0x18022b2e9  mov     r10d, [rax+8]
0x18022b2ed  test    r10d, r10d
0x18022b2f0  jz      short loc_18022B32A
0x18022b2f2  mov     r8, [rdi+10h]
0x18022b2f6  mov     eax, ecx
0x18022b2f8  lea     rdx, [rax+rax*2]
0x18022b2fc  cmp     dword ptr [r8+rdx*8], 99h
0x18022b304  jz      short loc_18022B310
0x18022b306  add     ecx, r14d
0x18022b309  cmp     ecx, r10d
0x18022b30c  jb      short loc_18022B2F6
0x18022b30e  jmp     short loc_18022B32A
0x18022b310  cmp     dword ptr [r8+rdx*8+8], 7
0x18022b316  jz      short loc_18022B322
0x18022b318  mov     ebx, 80070057h
0x18022b31d  jmp     loc_18022B55B
0x18022b322  lea     r9, [r8+10h]
0x18022b326  lea     r9, [r9+rdx*8]
0x18022b32a  test    r9, r9
0x18022b32d  jz      short loc_18022B341
0x18022b32f  mov     r11d, ebx
0x18022b332  or      eax, 0FFFFFFFFh
0x18022b335  cmp     ax, [r9]
0x18022b339  setz    r11b
0x18022b33d  mov     [rbp+37h+var_44], r11d
0x18022b341  test    r15, r15
0x18022b344  jz      loc_18022B54F
0x18022b34a  mov     rcx, r12; pbstr
0x18022b34d  call    cs:__imp_SysStringLen
0x18022b353  test    eax, eax
0x18022b355  jz      loc_18022B54F
0x18022b35b  mov     r15, [r15]
0x18022b35e  mov     rcx, r13; pbstr
0x18022b361  mov     ebx, 0FFFFFFFFh
0x18022b366  call    cs:__imp_SysStringLen
0x18022b36c  cmp     r15, rbx
0x18022b36f  jnz     loc_18022B487
0x18022b375  mov     r10d, [rbp+37h+arg_40]
0x18022b37c  xor     r11d, r11d
0x18022b37f  mov     edi, eax
0x18022b381  mov     r8d, r11d
0x18022b384  test    r10d, r10d
0x18022b387  jz      short loc_18022B3AF
0x18022b389  mov     r9, [rbp+37h+arg_48]
0x18022b390  mov     ecx, r8d
0x18022b393  mov     eax, r10d
0x18022b396  lea     rdx, [rcx+rcx*2]
0x18022b39a  cmp     [r9+rdx*8], r11d
0x18022b39e  jnz     short loc_18022B3A7
0x18022b3a0  cmp     [r9+rdx*8+4], r11d
0x18022b3a5  jz      short loc_18022B3B9
0x18022b3a7  add     r8d, r14d
0x18022b3aa  cmp     r8d, eax
0x18022b3ad  jb      short loc_18022B390
0x18022b3af  mov     ebx, 8024E002h
0x18022b3b4  jmp     loc_18022B4B6
0x18022b3b9  cmp     dword ptr [r9+rdx*8+8], 8
0x18022b3bf  mov     r15, [r9+rdx*8+10h]
0x18022b3c4  jnz     short loc_18022B3AF
0x18022b3c6  mov     r15, [r15]
0x18022b3c9  cmp     r15, rbx
0x18022b3cc  jz      short loc_18022B3AF
0x18022b3ce  mov     edx, r11d
0x18022b3d1  mov     eax, edx
0x18022b3d3  lea     rcx, [rax+rax*2]
0x18022b3d7  mov     eax, r10d
0x18022b3da  cmp     [r9+rcx*8], r11d
0x18022b3de  jnz     short loc_18022B3E7
0x18022b3e0  cmp     [r9+rcx*8+4], r14d
0x18022b3e5  jz      short loc_18022B3F0
0x18022b3e7  add     edx, r14d
0x18022b3ea  cmp     edx, eax
0x18022b3ec  jb      short loc_18022B3D1
0x18022b3ee  jmp     short loc_18022B3AF
0x18022b3f0  mov     edx, [r9+rcx*8+8]
0x18022b3f5  mov     r12, [r9+rcx*8+10h]
0x18022b3fa  cmp     edx, 4
0x18022b3fd  jb      short loc_18022B3AF
0x18022b3ff  test    edi, edi
0x18022b401  jz      short loc_18022B411
0x18022b403  cmp     word ptr [r13+0], 5Ch ; '\'
0x18022b409  jnz     short loc_18022B411
0x18022b40b  add     r13, 2
0x18022b40f  add     edi, ebx
0x18022b411  lea     eax, [rdi+1]
0x18022b414  test    edi, edi
0x18022b416  cmovz   eax, edi
0x18022b419  shr     edx, 1
0x18022b41b  add     eax, edx
0x18022b41d  mov     edx, 2; unsigned __int64
0x18022b422  mov     ecx, eax; unsigned __int64
0x18022b424  mov     r14d, eax
0x18022b427  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18022b42c  xor     r11d, r11d
0x18022b42f  mov     rsi, rax
0x18022b432  test    rax, rax
0x18022b435  jnz     short loc_18022B43E
0x18022b437  mov     ebx, 8007000Eh
0x18022b43c  jmp     short loc_18022B4B6
0x18022b43e  mov     r8, r12; wchar_t *
0x18022b441  mov     rdx, r14; unsigned __int64
0x18022b444  mov     rcx, rsi; wchar_t *
0x18022b447  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18022b44c  mov     ebx, eax
0x18022b44e  test    eax, eax
  ... truncated ...
```
