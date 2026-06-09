# CScriptRuntime::RunWithNoSideEffects(VAR *)

- ea: `0x18006d184`
- end: `0x18006e883`
- name: `?RunWithNoSideEffects@CScriptRuntime@@QEAAJPEAVVAR@@@Z`
- size: `5887`
- prototype: `__int64 __fastcall(CScriptRuntime *__hidden this, struct VAR *)`
- caller_count: `1`
- callee_count: `54`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18006ba64`

## callees

- `0x1800016c0`
- `0x180001ab8`
- `0x180001c30`
- `0x180002d48`
- `0x1800040a0`
- `0x180004400`
- `0x180014d2c`
- `0x1800162c0`
- `0x1800166f0`
- `0x180018b50`
- `0x18001b9e0`
- `0x18001ca30`
- `0x18001e1d0`
- `0x18001e410`
- `0x180022ea0`
- `0x180022ed0`
- `0x180022f50`
- `0x180022fb0`
- `0x180023414`
- `0x1800235d0`
- `0x1800236e0`
- `0x180023858`
- `0x180023970`
- `0x180023e50`
- `0x180024010`
- `0x1800245a0`
- `0x1800254d0`
- `0x180026150`
- `0x1800268b8`
- `0x180030ed0`
- `0x180031040`
- `0x1800310c0`
- `0x180031360`
- `0x180031910`
- `0x180031d80`
- `0x180031dd0`
- `0x180031e20`
- `0x1800321b0`
- `0x180034030`
- `0x1800364a0`
- `0x1800369bc`
- `0x1800377cc`
- `0x18003caa0`
- `0x180040830`
- `0x18004096c`
- `0x180041644`
- `0x180042f8c`
- `0x1800434c4`
- `0x180043c28`
- `0x180043cf4`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18006e19f`
- `OLEAUT32!__imp_VariantCopy` at `0x18006e19f`

## pseudocode

```c
__int64 __fastcall CScriptRuntime::RunWithNoSideEffects(CScriptRuntime *this, struct VAR *a2)
{
  int v3; // ecx
  int v4; // eax
  CScriptRuntime *v5; // rdi
  __int16 v6; // r10
  int v7; // eax
  _BYTE *v8; // rdx
  int v9; // r13d
  __int64 v10; // r8
  int v11; // r12d
  unsigned __int8 *v12; // rdx
  unsigned int v13; // ecx
  unsigned int *v14; // r9
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  int v21; // eax
  GcContext *v22; // rcx
  unsigned int v23; // ecx
  unsigned __int8 *v24; // rax
  enum tagBREAKREASON v25; // edx
  _QWORD *v26; // rax
  __int64 v27; // r8
  int v28; // ecx
  __int64 v29; // rax
  int v30; // eax
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  struct VAR **v36; // rdx
  __int64 v37; // rcx
  struct VAR *v38; // rax
  int *v39; // rax
  int v40; // ecx
  __int16 *v41; // rcx
  char *v42; // rax
  __int16 v43; // cx
  unsigned int *v44; // rax
  __int64 v45; // rdx
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  unsigned int v48; // ecx
  unsigned int v49; // ecx
  unsigned int v50; // ecx
  unsigned int v51; // ecx
  unsigned int v52; // ecx
  unsigned int v53; // ecx
  unsigned int v54; // ecx
  int v55; // ecx
  struct VAR *v56; // rax
  __int64 v57; // xmm1_8
  __int64 v58; // r8
  unsigned int v59; // ecx
  unsigned int v60; // ecx
  unsigned int v61; // ecx
  __int64 v62; // rax
  unsigned __int8 v63; // si
  __int64 v64; // rbx
  const unsigned __int16 *v65; // rbx
  int v66; // r8d
  VAR *v67; // r10
  __int64 v68; // rsi
  const unsigned __int16 *v69; // rsi
  struct VAR *v70; // r10
  VARIANTARG *v71; // rbx
  struct SYM *v72; // rax
  unsigned int v73; // ecx
  unsigned int v74; // ecx
  unsigned int v75; // ecx
  unsigned int v76; // ecx
  unsigned int v77; // ecx
  __int64 v78; // rbx
  const unsigned __int16 *v79; // rbx
  int v80; // esi
  int v81; // r8d
  VAR *v82; // r11
  VAR *v83; // r11
  unsigned int v84; // ebx
  __int64 v86; // rsi
  const unsigned __int16 *v87; // rsi
  __int64 v88; // rbx
  int v89; // r8d
  __int64 v90; // rcx
  VAR *v91; // r11
  VAR *v92; // r11
  unsigned int v93; // r14d
  unsigned int v94; // ecx
  unsigned int v95; // ecx
  unsigned int v96; // ecx
  unsigned int v97; // ecx
  unsigned int v98; // ecx
  __int64 v99; // r14
  __int64 v100; // rcx
  const unsigned __int16 *v101; // r14
  int v102; // esi
  __int64 v103; // r15
  struct VAR *v104; // r10
  struct VAR *v105; // rbx
  struct SYM *v106; // rax
  int v107; // edx
  struct VAR *v108; // rax
  unsigned __int16 *v109; // r8
  __int64 v110; // r9
  CScriptRuntime *v111; // rcx
  struct VAR *v112; // r11
  int v113; // edx
  struct VAR *v114; // rax
  unsigned __int16 *v115; // r8
  unsigned int v116; // ecx
  __int64 v117; // r9
  struct VAR *v118; // r11
  unsigned int v119; // ecx
  unsigned int v120; // ecx
  unsigned int v121; // ecx
  unsigned int v122; // ecx
  __int64 v123; // rcx
  int v124; // ebx
  struct VAR *v125; // rsi
  CScriptRuntime *v126; // rcx
  VARIANTARG *pvarSrc; // r9
  char v128; // r10
  __int64 v129; // rcx
  int v130; // esi
  __int64 v131; // r14
  struct VAR *v132; // rbx
  VARIANTARG *v133; // r9
  char v134; // r10
  struct VAR *v135; // rax
  __int64 v136; // rcx
  __int64 v137; // rcx
  __int64 v138; // rax
  __int16 v139; // r9
  unsigned int v140; // ecx
  unsigned int v141; // ecx
  unsigned int v142; // ecx
  unsigned int v143; // ecx
  unsigned int v144; // ecx
  unsigned int v145; // ebx
  _WORD *v146; // rcx
  bool v147; // zf
  int BoolValNull; // edx
  int v149; // r9d
  _WORD *v150; // rcx
  __int64 v151; // rcx
  __int64 v152; // rdx
  int v153; // eax
  unsigned int v154; // ecx
  unsigned int v155; // ecx
  unsigned int v156; // ecx
  unsigned int v157; // ecx
  unsigned int v158; // ecx
  int v159; // eax
  unsigned int v160; // ecx
  __int16 v161; // cx
  bool v162; // zf
  __int16 v163; // cx
  int v164; // eax
  bool v165; // zf
  __int16 v166; // dx
  VARIANTARG *v167; // rbx
  struct VAR *LogicalVal; // rax
  unsigned int v169; // ecx
  unsigned int v170; // ecx
  unsigned int v171; // ecx
  unsigned int v172; // ecx
  unsigned int v173; // ecx
  unsigned int v174; // eax
  __int16 v175; // cx
  __int16 v176; // cx
  unsigned int v177; // ecx
  unsigned int v178; // ecx
  unsigned int v179; // ecx
  unsigned int v180; // ecx
  unsigned int v181; // ecx
  unsigned int v182; // ecx
  unsigned int v183; // ecx
  unsigned int v184; // ecx
  unsigned int v185; // ecx
  bool v186; // zf
  unsigned int v187; // ecx
  unsigned int v188; // ecx
  unsigned int v189; // ecx
  unsigned int v190; // ecx
  unsigned int v191; // ecx
  unsigned int v192; // ecx
  unsigned int v193; // ecx
  unsigned int v194; // ecx
  VAR *v195; // rbx
  VAR *v196; // rbx
  struct VAR *v197; // rcx
  int v198; // [rsp+40h] [rbp-79h] BYREF
  struct VAR *v199; // [rsp+48h] [rbp-71h] BYREF
  struct IDispatch *v200; // [rsp+50h] [rbp-69h] BYREF
  int v201; // [rsp+58h] [rbp-61h]
  struct IEntryPoint *v202; // [rsp+60h] [rbp-59h] BYREF
  enum tagBREAKREASON v203; // [rsp+68h] [rbp-51h] BYREF
  int v204; // [rsp+6Ch] [rbp-4Dh] BYREF
  int v205; // [rsp+70h] [rbp-49h]
  VAR *v206; // [rsp+78h] [rbp-41h]
  CScriptRuntime *v207; // [rsp+80h] [rbp-39h]
  __int128 v208; // [rsp+90h] [rbp-29h] BYREF
  __int64 v209; // [rsp+A0h] [rbp-19h]
  _BYTE v210[24]; // [rsp+A8h] [rbp-11h] BYREF
  VARIANTARG pvargDest; // [rsp+C0h] [rbp+7h] BYREF

  v207 = this;
  v206 = a2;
  v209 = 0;
  v198 = 0;
  v204 = 0;
  v201 = 0;
  v199 = 0;
  v200 = 0;
  v202 = 0;
  v203 = BREAKREASON_STEP;
  v208 = 0;
  memset(&pvargDest, 0, sizeof(pvargDest));
  v3 = *(_DWORD *)(*((_QWORD *)this + 6) + 24LL);
  *((_QWORD *)this + 54) = *((_QWORD *)this + 58);
  *((_QWORD *)this + 71) = &v198;
  *((_QWORD *)this + 70) = &v204;
  *((_QWORD *)this + 59) = *((_QWORD *)this + 60);
  *((_DWORD *)this + 122) = -1;
  *((_QWORD *)this + 16) = *((_QWORD *)this + 58);
  *((_QWORD *)this + 15) = *((_QWORD *)this + 59);
  v205 = v3;
  if ( a2 )
    *(_WORD *)a2 = 0;
  *((_DWORD *)this + 126) = *((_DWORD *)this + 126) & 0xFFFFFFD8 | 0x20;
  TLS_NoDestructor::TLS_NoDestructor((TLS_NoDestructor *)v210, *((struct COleScript **)this + 1));
  v4 = setjmp_0((_JBTYPE *)this + 11);
  v5 = v207;
  v6 = 2;
  if ( v4 )
  {
    v198 = *((_DWORD *)v207 + 40);
    if ( *(_DWORD *)(*(_QWORD *)v207 + 128LL) )
      goto LABEL_119;
    *((_DWORD *)v207 + 40) = 0;
    *((_QWORD *)v5 + 17) = 0;
    *((_QWORD *)v5 + 19) = 0;
    *((_DWORD *)v5 + 36) = -1;
    *((_DWORD *)v5 + 37) = 0;
    v7 = *((_DWORD *)v5 + 126);
    if ( (v7 & 1) != 0 )
    {
      *((_QWORD *)v5 + 58) = *((_QWORD *)v5 + 54);
      while ( 1 )
      {
        v8 = (_BYTE *)*((_QWORD *)v5 + 59);
        if ( (unsigned __int8)(*v8 - 2) <= 4u )
          break;
        *((_QWORD *)v5 + 59) = &v8[(unsigned __int8)byte_180084A80[4 * (unsigned __int8)*v8]];
      }
      v198 = 0;
    }
    else
    {
      if ( (v7 & 2) != 0
        || v198 == -2147352319
        || *(_DWORD *)(*(_QWORD *)v5 + 108LL)
        || !(unsigned int)CScriptRuntime::FResumeFromRuntimeError(v5, &v198) )
      {
        goto LABEL_119;
      }
      v6 = 2;
    }
  }
  v9 = v205;
  v10 = 16396;
  v11 = v201;
  while ( 1 )
  {
    v12 = (unsigned __int8 *)*((_QWORD *)v5 + 59);
    v13 = *v12;
    v14 = (unsigned int *)(v12 + 1);
    *((_QWORD *)v5 + 59) = v12 + 1;
    if ( v13 > 0x38 )
      break;
    if ( v13 == 56 )
      goto LABEL_118;
    if ( v13 > 0x1C )
    {
      if ( v13 > 0x2A )
      {
        if ( v13 <= 0x31 )
        {
          if ( v13 == 49 )
            goto LABEL_118;
          v94 = v13 - 43;
          if ( v94 )
          {
            v95 = v94 - 1;
            if ( !v95 )
              goto LABEL_118;
            v96 = v95 - 1;
            if ( v96 )
            {
              v97 = v96 - 1;
              if ( !v97 )
                goto LABEL_118;
              v98 = v97 - 1;
              if ( !v98 )
                goto LABEL_118;
              if ( v98 == 1 )
              {
                v99 = *v14;
                *((_QWORD *)v5 + 59) = v12 + 5;
                v100 = *(unsigned __int16 *)(v12 + 5);
                v101 = (const unsigned __int16 *)(*((_QWORD *)v5 + 62) + v99);
                v102 = *(unsigned __int16 *)(v12 + 5);
                *((_QWORD *)v5 + 59) = v12 + 7;
                v103 = 24 * v100;
                if ( !(unsigned int)VAR::IsIDispatch((VAR *)(24 * v100 + *((_QWORD *)v5 + 58)), &v200) )
                {
                  v198 = -2146827864;
                  CScriptRuntime::IfErrorHrArg(v5, -2146827864, v104, 0, v102);
                }
                v105 = (struct VAR *)*((_QWORD *)v5 + 58);
                v106 = SYM::InitFromSymbol((SYM *)&v208, v101);
                v198 = InvokeByName(*(struct CSession **)v5, v200, v106, 2, &pvargDest, v102, v105);
                CScriptRuntime::IfErrorHrArg(v5, v198, (struct VAR *)((char *)v105 + v103), v101, v102);
                *((_QWORD *)v5 + 58) += v103;
                *(VARIANTARG *)*((_QWORD *)v5 + 58) = pvargDest;
                goto LABEL_283;
              }
              goto LABEL_281;
            }
            v107 = *(__int16 *)v14;
            *((_QWORD *)v5 + 59) = (char *)v14 + 2;
            v201 = v107;
            v11 = v107;
            v199 = CScriptRuntime::PvarLocal(v5, v107);
            v108 = VAR::PvarCutRef(v199);
            v80 = *v109;
            v83 = v108;
            v199 = v108;
            v79 = 0;
            *((_QWORD *)v5 + 59) = v110 + 4;
            goto LABEL_139;
          }
          v113 = *(__int16 *)v14;
          *((_QWORD *)v5 + 59) = (char *)v14 + 2;
          v201 = v113;
          v11 = v113;
          v199 = CScriptRuntime::PvarLocal(v5, v113);
          v114 = VAR::PvarCutRef(v199);
          v116 = *v115;
          v92 = v114;
          v199 = v114;
          v87 = 0;
          LODWORD(v88) = v116;
          *((_QWORD *)v5 + 59) = v117 + 4;
          v93 = v116;
          goto LABEL_146;
        }
        v119 = v13 - 50;
        if ( !v119 )
          goto LABEL_118;
        v120 = v119 - 1;
        if ( !v120 )
          goto LABEL_118;
        v121 = v120 - 1;
        if ( v121 )
        {
          v122 = v121 - 1;
          if ( !v122 )
            goto LABEL_118;
          v77 = v122 - 1;
          if ( !v77 )
          {
            v123 = *(unsigned __int16 *)v14;
            v124 = *(unsigned __int16 *)v14;
            *((_QWORD *)v5 + 59) = v12 + 3;
            v125 = (struct VAR *)(*((_QWORD *)v5 + 58) + 24 * v123);
            v199 = v125;
            if ( (unsigned int)VAR::IsIDispatch(v125, &v200) )
            {
              pvargDest.vt = 0;
              v198 = InvokeDispatch(*(struct CSession **)v5, v200, 0, v128, &pvargDest, v124, *((struct VAR **)v5 + 58));
              CScriptRuntime::IfErrorHrArg(v5, v198, v125, 0, v124);
              v10 = 16396;
            }
            else
            {
              v198 = CScriptRuntime::LockArray(v126, &v199, v125, v124, pvarSrc);
              CScriptRuntime::IfErrorHrArg(v5, v198, v125, 0, v124);
              v10 = 16396;
              pvargDest.vt = 16396;
              pvargDest.llVal = (LONGLONG)v199;
            }
            *((_QWORD *)v5 + 58) += 24LL * (unsigned int)(v124 + 1) - 24;
            goto LABEL_144;
          }
LABEL_280:
          if ( v77 == 1 )
            goto LABEL_118;
          goto LABEL_281;
        }
        v129 = *(unsigned __int16 *)v14;
        v130 = *(unsigned __int16 *)v14;
        *((_QWORD *)v5 + 59) = v12 + 3;
        v131 = 24 * v129;
        v132 = (struct VAR *)(24 * v129 + *((_QWORD *)v5 + 58));
        v199 = v132;
        if ( (unsigned int)VAR::IsIDispatch(v132, &v200) )
        {
          pvargDest.vt = 0;
          v198 = InvokeDispatch(*(struct CSession **)v5, v200, 0, v134, &pvargDest, v130, *((struct VAR **)v5 + 58));
          CScriptRuntime::IfErrorHrArg(v5, v198, v132, 0, v130);
          *((_QWORD *)v5 + 58) += v131;
          goto LABEL_123;
        }
        v198 = AccessArray(&v199, v132, v130, v133, 0);
        CScriptRuntime::IfErrorHrArg(v5, v198, v132, 0, v130);
        *((_QWORD *)v5 + 58) += v131;
LABEL_161:
        v135 = v199;
        v136 = *((_QWORD *)v5 + 58);
        *(_OWORD *)v136 = *(_OWORD *)v199;
        *(_QWORD *)(v136 + 16) = *((_QWORD *)v135 + 2);
        goto LABEL_162;
      }
      if ( v13 == 42 )
        goto LABEL_118;
      if ( v13 > 0x23 )
      {
        v73 = v13 - 36;
        if ( !v73 )
          goto LABEL_118;
        v74 = v73 - 1;
        if ( !v74 )
          goto LABEL_118;
        v75 = v74 - 1;
        if ( v75 )
        {
          v76 = v75 - 1;
          if ( !v76 )
            goto LABEL_118;
          v77 = v76 - 1;
          if ( !v77 )
          {
            v78 = *v14;
            *((_QWORD *)v5 + 59) = v12 + 5;
            v79 = (const unsigned __int16 *)(*((_QWORD *)v5 + 62) + v78);
            v80 = *(unsigned __int16 *)(v12 + 5);
            *((_QWORD *)v5 + 59) = v12 + 7;
            CScriptRuntime::GetVarAdr(v5, v79, (struct VAR *)&pvargDest);
            if ( (unsigned int)VAR::IsDispmember((VAR *)&pvargDest) )
            {
              v198 = VAR::InvokeByDispID(
                       (VAR *)&pvargDest,
                       *(struct CSession **)v5,
                       v81,
                       2u,
                       (struct VAR *)&pvargDest,
                       v80,
                       *((struct VAR **)v5 + 58));
              CScriptRuntime::IfErrorHrPsz(v5, v198, v79);
              goto LABEL_141;
            }
            v199 = VAR::PvarCutRef((VAR *)&pvargDest);
            if ( (unsigned int)VAR::IsFunction(v199, &v202) || (unsigned int)VAR::IsProperty(v82, &v202, 4u) )
              goto LABEL_118;
LABEL_139:
            if ( (unsigned int)VAR::IsIDispatch(v83, &v200) )
            {
              pvargDest.vt = 0;
              v198 = InvokeDispatch(*(struct CSession **)v5, v200, 0, 2, &pvargDest, v80, *((struct VAR **)v5 + 58));
              CScriptRuntime::IfErrorHrLocal(v5, v198, v79, v11);
LABEL_141:
              v10 = 16396;
            }
            else
            {
              v198 = CScriptRuntime::LockArray(v111, &v199, v112, v80, *((VARIANTARG **)v5 + 58));
              CScriptRuntime::IfErrorHrLocal(v5, v198, v79, v11);
              v10 = 16396;
              pvargDest.vt = 16396;
              pvargDest.llVal = (LONGLONG)v199;
            }
            *((_QWORD *)v5 + 58) += 24LL * v80 - 24;
LABEL_144:
            *(VARIANTARG *)*((_QWORD *)v5 + 58) = pvargDest;
LABEL_284:
            v6 = 2;
            goto LABEL_285;
          }
          goto LABEL_280;
        }
        v86 = *v14;
        *((_QWORD *)v5 + 59) = v12 + 5;
        v87 = (const unsigned __int16 *)(*((_QWORD *)v5 + 62) + v86);
        v88 = *(unsigned __int16 *)(v12 + 5);
        *((_QWORD *)v5 + 59) = v12 + 7;
        CScriptRuntime::GetVarAdr(v5, v87, (struct VAR *)&pvargDest);
        if ( (unsigned int)VAR::IsDispmember((VAR *)&pvargDest) )
        {
          v198 = VAR::InvokeByDispID(
                   (VAR *)&pvargDest,
                   *(struct CSession **)v5,
                   v89,
                   2u,
                   (struct VAR *)&pvargDest,
                   v88,
                   *((struct VAR **)v5 + 58));
          CScriptRuntime::IfErrorHrPsz(v5, v198, v87);
          v90 = 3 * v88;
LABEL_122:
          *((_QWORD *)v5 + 58) += 8 * v90 - 24;
          goto LABEL_123;
        }
        v199 = VAR::PvarCutRef((VAR *)&pvargDest);
        if ( (unsigned int)VAR::IsFunction(v199, &v202) || (unsigned int)VAR::IsProperty(v91, &v202, 4u) )
          goto LABEL_118;
        v93 = v88;
LABEL_146:
        if ( (unsigned int)VAR::IsIDispatch(v92, &v200) )
        {
          pvargDest.vt = 0;
          v198 = InvokeDispatch(*(struct CSession **)v5, v200, 0, 2, &pvargDest, v88, *((struct VAR **)v5 + 58));
          CScriptRuntime::IfErrorHrLocal(v5, v198, v87, v11);
          v90 = 3LL * v93;
          goto LABEL_122;
        }
        v198 = AccessArray(&v199, v118, v88, *((VARIANTARG **)v5 + 58), 0);
        CScriptRuntime::IfErrorHrLocal(v5, v198, v87, v11);
        *((_QWORD *)v5 + 58) += 24LL * v93 - 24;
        goto LABEL_161;
      }
      if ( v13 == 35 )
      {
        v68 = *v14;
        *((_QWORD *)v5 + 59) = v12 + 5;
        v69 = (const unsigned __int16 *)(*((_QWORD *)v5 + 62) + v68);
        if ( !(unsigned int)VAR::IsIDispatch(*((VAR **)v5 + 58), &v200) )
        {
          v198 = -2146827864;
          CScriptRuntime::IfErrorHrArg(v5, -2146827864, v70, 0, 0);
        }
        **((_WORD **)v5 + 58) = 0;
        v71 = (VARIANTARG *)*((_QWORD *)v5 + 58);
        v72 = SYM::InitFromSymbol((SYM *)&v208, v69);
        v198 = InvokeByName(*(struct CSession **)v5, v200, v72, 2, v71, 0, 0);
        CScriptRuntime::IfErrorHrArg(v5, v198, (struct VAR *)v71, v69, 0);
        goto LABEL_283;
      }
      v59 = v13 - 29;
      if ( !v59 )
      {
LABEL_100:
        v63 = *v12;
        v64 = *v14;
        *((_QWORD *)v5 + 59) = v12 + 5;
        v65 = (const unsigned __int16 *)(*((_QWORD *)v5 + 62) + v64);
        *((_QWORD *)v5 + 58) -= 24LL;
        **((_WORD **)v5 + 58) = 0;
        CScriptRuntime::GetVarAdr(v5, v65, *((struct VAR **)v5 + 58));
        if ( (unsigned int)VAR::IsDispmember(*((VAR **)v5 + 58)) )
        {
          v198 = VAR::InvokeByDispID(v67, *(struct CSession **)v5, v66, 2u, v67, 0, 0);
          CScriptRuntime::IfErrorHrPsz(v5, v198, v65);
LABEL_283:
          v10 = 16396;
          goto LABEL_284;
        }
        if ( (unsigned int)VAR::IsFunction(v67, &v202) || (unsigned int)VAR::IsProperty(*((VAR **)v5 + 58), &v202, 4u) )
          goto LABEL_118;
        if ( v63 != 28 )
          goto LABEL_283;
LABEL_162:
        v137 = *((_QWORD *)v5 + 58);
        if ( *(_WORD *)v137 == 16396 )
        {
          v138 = *(_QWORD *)(v137 + 8);
          *(_OWORD *)v137 = *(_OWORD *)v138;
          *(_QWORD *)(v137 + 16) = *(_QWORD *)(v138 + 16);
        }
        if ( (unsigned int)VAR::IsSimpleType(**((unsigned __int16 **)v5 + 58)) || v139 == 74 )
          goto LABEL_283;
        pvargDest.vt = 0;
        v198 = VariantCopy(&pvargDest, *((const VARIANTARG **)v5 + 58));
        CScriptRuntime::IfErrorHr(v5, v198);
        v198 = VAR::MoveToHeap((VAR *)&pvargDest, *((struct GcContext **)v5 + 6));
        CScriptRuntime::IfErrorHr(v5, v198);
LABEL_123:
        *(VARIANTARG *)*((_QWORD *)v5 + 58) = pvargDest;
        goto LABEL_283;
      }
      v60 = v59 - 1;
      if ( !v60 )
        goto LABEL_118;
      v61 = v60 - 1;
      if ( !v61 )
        goto LABEL_118;
      v54 = v61 - 1;
      if ( v54 )
        goto LABEL_279;
      *((_QWORD *)v5 + 58) -= 24LL;
      v62 = *((_QWORD *)v5 + 58);
      *(_OWORD *)v62 = *(_OWORD *)((char *)v5 + 440);
      *(_QWORD *)(v62 + 16) = *((_QWORD *)v5 + 57);
    }
    else
    {
      if ( v13 == 28 )
        goto LABEL_100;
      if ( v13 <= 0xE )
      {
        if ( v13 == 14 )
        {
          *((_QWORD *)v5 + 58) -= 24LL;
          **((_WORD **)v5 + 58) = 8;
          v44 = (unsigned int *)*((_QWORD *)v5 + 59);
          v45 = *v44;
          *((_QWORD *)v5 + 59) = v44 + 1;
          *(_QWORD *)(*((_QWORD *)v5 + 58) + 8LL) = *((_QWORD *)v5 + 62) + v45;
          goto LABEL_285;
        }
        if ( v13 <= 7 )
        {
          if ( v13 == 7 )
            goto LABEL_118;
          if ( !v13 )
            goto LABEL_285;
          v15 = v13 - 1;
          if ( !v15 )
          {
            v195 = v206;
            if ( !v206 )
              goto LABEL_119;
LABEL_296:
            *(_WORD *)v195 = 0;
            goto LABEL_119;
          }
          v16 = v15 - 1;
          if ( !v16 )
            goto LABEL_285;
          v17 = v16 - 1;
          if ( v17 )
          {
            v18 = v17 - 1;
            if ( v18 )
            {
              v19 = v18 - 1;
              if ( v19 )
              {
                if ( v19 == 1 )
                {
                  v20 = *v14;
                  *((_QWORD *)v5 + 59) = v12 + 5;
                  *((_DWORD *)v5 + 122) = v20;
                  v198 = CScriptRuntime::Break(v5, BREAKREASON_BREAKPOINT);
                  if ( v198 < 0 )
                    goto LABEL_119;
                  v21 = CSession::HandleHalt(*(CSession **)v5);
                  goto LABEL_33;
                }
                goto LABEL_281;
              }
              v23 = *v14;
              v24 = v12 + 5;
            }
            else
            {
              v23 = *(unsigned __int16 *)v14;
              v24 = v12 + 3;
            }
          }
          else
          {
            v23 = *(unsigned __int8 *)v14;
            v24 = v12 + 2;
          }
          *((_QWORD *)v5 + 59) = v24;
          *((_DWORD *)v5 + 122) = v23;
          if ( !(unsigned int)CSession::FInterrupt(*(CSession **)v5) )
            goto LABEL_34;
          v198 = CSession::HandleHalt(*(CSession **)v5);
          if ( v198 < 0 )
            goto LABEL_119;
          v198 = CSession::HandleAbort(*(CSession **)v5);
          if ( v198 < 0 )
            goto LABEL_119;
          if ( (unsigned int)CSession::FOneTimeBreak(*(CSession **)v5, *((_DWORD *)v5 + 6), &v203) )
          {
            v25 = v203;
          }
          else
          {
            v26 = (_QWORD *)*((_QWORD *)v5 + 5);
            v27 = *(_QWORD *)(*v26 + 16LL);
            if ( !v27 )
              goto LABEL_34;
            v28 = *((_DWORD *)v5 + 122) + *(_DWORD *)(v26[2] + 16LL);
            if ( v28 < 0 || v28 >= *(_DWORD *)(*(_QWORD *)(*v26 + 64LL) + 32LL) )
            {
              v30 = 0;
            }
            else
            {
              v29 = (__int64)v28 >> 3;
              if ( !*(_BYTE *)(v29 + v27) )
                goto LABEL_34;
              v30 = (*(unsigned __int8 *)(v29 + v27) >> (v28 & 7)) & 1;
            }
            if ( !v30 )
            {
LABEL_34:
              v22 = (GcContext *)*((_QWORD *)v5 + 6);
              if ( v9 < *((_DWORD *)v22 + 6) )
                GcContext::FreeToMark(v22, v9);
              v198 = CSession::PollHalt(*(CSession **)v5);
              if ( v198 < 0 )
                goto LABEL_119;
              goto LABEL_283;
            }
            v25 = BREAKREASON_BREAKPOINT;
          }
          v21 = CScriptRuntime::Break(v5, v25);
LABEL_33:
          v198 = v21;
          if ( v21 < 0 )
            goto LABEL_119;
          goto LABEL_34;
        }
        v31 = v13 - 8;
        if ( !v31 )
          goto LABEL_118;
        v32 = v31 - 1;
        if ( !v32 )
          goto LABEL_118;
        v33 = v32 - 1;
        if ( !v33 )
          goto LABEL_118;
        v34 = v33 - 1;
        if ( !v34 )
        {
          *((_QWORD *)v5 + 58) -= 24LL;
          **((_WORD **)v5 + 58) = v6;
          v42 = (char *)*((_QWORD *)v5 + 59);
          v43 = *v42;
          *((_QWORD *)v5 + 59) = v42 + 1;
          *(_WORD *)(*((_QWORD *)v5 + 58) + 8LL) = v43;
          goto LABEL_285;
        }
        v35 = v34 - 1;
        if ( !v35 )
        {
          *((_QWORD *)v5 + 58) -= 24LL;
          **((_WORD **)v5 + 58) = 3;
          v39 = (int *)*((_QWORD *)v5 + 59);
          v40 = *v39;
          *((_QWORD *)v5 + 59) = v39 + 1;
          *(_DWORD *)(*((_QWORD *)v5 + 58) + 8LL) = v40;
          v41 = (__int16 *)*((_QWORD *)v5 + 58);
          if ( v41[4] == *((_DWORD *)v41 + 2) )
            *v41 = v6;
          goto LABEL_285;
        }
        if ( v35 != 1 )
          goto LABEL_281;
        *((_QWORD *)v5 + 58) -= 24LL;
        **((_WORD **)v5 + 58) = 5;
LABEL_62:
        v36 = (struct VAR **)*((_QWORD *)v5 + 59);
        *((_QWORD *)v5 + 59) = v36 + 1;
        v37 = *((_QWORD *)v5 + 58);
        v38 = *v36;
LABEL_63:
        *(_QWORD *)(v37 + 8) = v38;
        goto LABEL_285;
      }
      if ( v13 > 0x15 )
      {
        v51 = v13 - 22;
        if ( !v51 )
          goto LABEL_118;
        v52 = v51 - 1;
        if ( !v52 )
          goto LABEL_118;
        v53 = v52 - 1;
        if ( !v53 )
        {
          v55 = *(__int16 *)v14;
          *((_QWORD *)v5 + 59) = v12 + 3;
          v11 = v55;
          *((_QWORD *)v5 + 58) -= 24LL;
          v201 = v55;
          v56 = CScriptRuntime::PvarLocal(v5, v55);
          v57 = *((_QWORD *)v56 + 2);
          *(_OWORD *)v58 = *(_OWORD *)v56;
          *(_QWORD *)(v58 + 16) = v57;
          goto LABEL_162;
        }
        v54 = v53 - 1;
        if ( v54 )
          goto LABEL_279;
        v201 = *(__int16 *)v14;
        v11 = v201;
        *((_QWORD *)v5 + 59) = v12 + 3;
        v38 = CScriptRuntime::PvarLocal(v5, v11);
        *((_QWORD *)v5 + 58) -= 24LL;
        v37 = *((_QWORD *)v5 + 58);
        v199 = v38;
        if ( *(_WORD *)v38 == (_WORD)v10 )
        {
          *(_OWORD *)v37 = *(_OWORD *)v38;
          *(_QWORD *)(v37 + 16) = *((_QWORD *)v38 + 2);
          goto LABEL_285;
        }
        *(_WORD *)v37 = v10;
        goto LABEL_63;
      }
      if ( v13 == 21 )
      {
        *((_QWORD *)v5 + 58) -= 24LL;
        **((_WORD **)v5 + 58) = 9;
        *(_QWORD *)(*((_QWORD *)v5 + 58) + 8LL) = 0;
        goto LABEL_285;
      }
      v46 = v13 - 15;
      if ( !v46 )
      {
        *((_QWORD *)v5 + 58) -= 24LL;
        **((_WORD **)v5 + 58) = 7;
        goto LABEL_62;
      }
      v47 = v46 - 1;
      if ( v47 )
      {
        v48 = v47 - 1;
        if ( v48 )
        {
          v49 = v48 - 1;
          if ( v49 )
          {
            v50 = v49 - 1;
            if ( v50 )
            {
              if ( v50 != 1 )
                goto LABEL_281;
              *((_QWORD *)v5 + 58) -= 24LL;
              **((_WORD **)v5 + 58) = 10;
              *(_DWORD *)(*((_QWORD *)v5 + 58) + 8LL) = -2147352572;
            }
            else
            {
              *((_QWORD *)v5 + 58) -= 24LL;
              **((_WORD **)v5 + 58) = 0;
            }
          }
          else
          {
            *((_QWORD *)v5 + 58) -= 24LL;
            **((_WORD **)v5 + 58) = 1;
          }
        }
        else
        {
          *((_QWORD *)v5 + 58) -= 24LL;
          **((_WORD **)v5 + 58) = 11;
          *(_WORD *)(*((_QWORD *)v5 + 58) + 8LL) = -1;
        }
      }
      else
      {
        *((_QWORD *)v5 + 58) -= 24LL;
        **((_WORD **)v5 + 58) = 11;
        *(_WORD *)(*((_QWORD *)v5 + 58) + 8LL) = 0;
      }
    }
LABEL_285:
    if ( vbs_interpreter_override_bailout )
    {
      v198 = -2147418113;
      goto LABEL_119;
    }
  }
  if ( v13 <= 0x54 )
  {
    if ( v13 == 84 )
    {
      **((_WORD **)v5 + 58) |= 0x8000u;
      goto LABEL_285;
    }
    if ( v13 > 0x46 )
    {
      if ( v13 <= 0x4D )
      {
        if ( v13 == 77 )
        {
          VbsVarEqv((struct VAR *)(*((_QWORD *)v5 + 58) + 24LL), *((struct VAR **)v5 + 58));
          goto LABEL_180;
        }
        v169 = v13 - 71;
        if ( !v169 )
        {
          v174 = VbsVarRel(*((_QWORD *)v5 + 58) + 24LL);
          v6 = 2;
          if ( v174 <= 2 )
            v175 = -1;
          else
            v175 = 0;
          v10 = 16396;
          *(_WORD *)(*((_QWORD *)v5 + 58) + 32LL) = v175;
          v176 = 1;
          if ( v174 != -2 )
            v176 = 11;
          *(_WORD *)(*((_QWORD *)v5 + 58) + 24LL) = v176;
          *((_QWORD *)v5 + 58) += 24LL;
          goto LABEL_285;
        }
        v170 = v169 - 1;
        if ( !v170 )
        {
          VbsVarAdd((struct VAR *)(*((_QWORD *)v5 + 58) + 24LL), *((struct VAR **)v5 + 58));
          goto LABEL_180;
        }
        v171 = v170 - 1;
        if ( !v171 )
        {
          VbsVarSub((struct VAR *)(*((_QWORD *)v5 + 58) + 24LL), *((struct VAR **)v5 + 58));
          goto LABEL_180;
        }
        v172 = v171 - 1;
        if ( !v172 )
        {
          VbsVarMul((struct VAR *)(*((_QWORD *)v5 + 58) + 24LL), *((struct VAR **)v5 + 58));
          goto LABEL_180;
        }
        v173 = v172 - 1;
        if ( !v173 )
        {
          VbsVarDiv((struct VAR *)(*((_QWORD *)v5 + 58) + 24LL), *((struct VAR **)v5 + 58));
          goto LABEL_180;
        }
        if ( v173 == 1 )
        {
          VbsVarMod((struct VAR *)(*((_QWORD *)v5 + 58) + 24LL), *((struct VAR **)v5 + 58));
          goto LABEL_180;
        }
LABEL_281:
        v153 = -2146828237;
        goto LABEL_282;
      }
      v177 = v13 - 78;
      if ( !v177 )
      {
        VbsVarPow((struct VAR *)(*((_QWORD *)v5 + 58) + 24LL), *((struct VAR **)v5 + 58));
        goto LABEL_180;
      }
      v178 = v177 - 1;
      if ( !v178 )
      {
        VbsVarImp((struct VAR *)(*((_QWORD *)v5 + 58) + 24LL), *((struct VAR **)v5 + 58));
        goto LABEL_180;
      }
      v179 = v178 - 1;
      if ( !v179 )
      {
        *(_WORD *)(*((_QWORD *)v5 + 58) + 32LL) = VbsVarIs(
                                                    (struct VAR *)(*((_QWORD *)v5 + 58) + 24LL),
                                                    *((struct VAR **)v5 + 58));
        *(_WORD *)(*((_QWORD *)v5 + 58) + 24LL) = 11;
        goto LABEL_180;
      }
      v180 = v179 - 1;
      if ( v180 )
      {
        v181 = v180 - 1;
        if ( !v181 )
        {
          VbsVarConcat((VARIANTARG *)(*((_QWORD *)v5 + 58) + 24LL));
          goto LABEL_180;
        }
        if ( v181 == 1 )
        {
          VbsVarIdiv((struct VAR *)(*((_QWORD *)v5 + 58) + 24LL));
          goto LABEL_180;
        }
        goto LABEL_281;
      }
      v153 = -2146828253;
LABEL_282:
      v198 = v153;
      CScriptRuntime::IfErrorHr(v5, v153);
      goto LABEL_283;
    }
    if ( v13 == 70 )
    {
      v159 = VbsVarRel(*((_QWORD *)v5 + 58) + 24LL);
      v160 = v159 - 1;
      goto LABEL_201;
    }
    if ( v13 > 0x3F )
    {
      v154 = v13 - 64;
      if ( v154 )
      {
        v155 = v154 - 1;
        if ( !v155 )
        {
          v167 = (VARIANTARG *)*((_QWORD *)v5 + 58);
          LogicalVal = VAR::PvarGetLogicalVal(v167);
          v167->vt = *(_WORD *)LogicalVal;
          v167->lVal = ~*((_DWORD *)LogicalVal + 2);
          goto LABEL_283;
        }
        v156 = v155 - 1;
        if ( v156 )
        {
          v157 = v156 - 1;
          if ( v157 )
          {
            v158 = v157 - 1;
            if ( v158 )
            {
              if ( v158 != 1 )
                goto LABEL_281;
              v159 = VbsVarRel(*((_QWORD *)v5 + 58) + 24LL);
              v160 = v159 + 1;
LABEL_201:
              if ( v160 <= 1 )
                v161 = -1;
              else
                v161 = 0;
              v162 = v159 == -2;
              *(_WORD *)(*((_QWORD *)v5 + 58) + 32LL) = v161;
LABEL_205:
              v163 = 1;
              if ( !v162 )
                v163 = 11;
              *(_WORD *)(*((_QWORD *)v5 + 58) + 24LL) = v163;
              goto LABEL_180;
            }
            v164 = VbsVarRel(*((_QWORD *)v5 + 58) + 24LL);
            v165 = v164 == -1;
LABEL_209:
            v166 = !v165 - 1;
          }
          else
          {
            v164 = VbsVarRel(*((_QWORD *)v5 + 58) + 24LL);
            v166 = -(v164 != 0);
          }
          v162 = v164 == -2;
          *(_WORD *)(*((_QWORD *)v5 + 58) + 32LL) = v166;
          goto LABEL_205;
        }
        v164 = VbsVarRel(*((_QWORD *)v5 + 58) + 24LL);
        v165 = v164 == 0;
        goto LABEL_209;
      }
      VbsVarAnd((struct VAR *)(*((_QWORD *)v5 + 58) + 24LL), *((struct VAR **)v5 + 58));
LABEL_180:
      *((_QWORD *)v5 + 58) += 24LL;
      goto LABEL_283;
    }
    if ( v13 == 63 )
    {
      VbsVarXor((struct VAR *)(*((_QWORD *)v5 + 58) + 24LL), *((struct VAR **)v5 + 58));
      goto LABEL_180;
    }
    v140 = v13 - 57;
    if ( !v140 )
    {
      v153 = -2146827787;
      goto LABEL_282;
    }
    v141 = v140 - 1;
    if ( v141 )
    {
      v142 = v141 - 1;
      if ( v142 )
      {
        v143 = v142 - 1;
        if ( v143 )
        {
          v144 = v143 - 1;
          if ( !v144 )
          {
            VbsVarNeg(*((struct VAR **)v5 + 58));
            goto LABEL_283;
          }
          if ( v144 != 1 )
            goto LABEL_281;
          VbsVarOr((VARIANTARG *)(*((_QWORD *)v5 + 58) + 24LL), *((VARIANTARG **)v5 + 58));
          goto LABEL_180;
        }
        v145 = *v14;
        *((_QWORD *)v5 + 59) = v12 + 5;
        v146 = (_WORD *)*((_QWORD *)v5 + 58);
        if ( *v146 == 11 )
          v147 = v146[4] == 0;
        else
          v147 = (unsigned int)GetBoolValNull(v146, v12, v10) == 0;
        BoolValNull = v147;
      }
      else
      {
        v145 = *v14;
        *((_QWORD *)v5 + 59) = v12 + 5;
        v150 = (_WORD *)*((_QWORD *)v5 + 58);
        if ( *v150 == 11 )
          BoolValNull = (__int16)v150[4];
        else
          BoolValNull = GetBoolValNull(v150, v12, v10);
      }
      v149 = 1;
LABEL_186:
      CScriptRuntime::Branch(v5, BoolValNull, v145, v149);
      goto LABEL_283;
    }
    v151 = *v14;
    *((_QWORD *)v5 + 59) = v12 + 5;
    *((_QWORD *)v5 + 16) = *((_QWORD *)v5 + 58);
    v152 = v151 + *((_QWORD *)v5 + 60);
    *((_QWORD *)v5 + 59) = v152;
    *((_QWORD *)v5 + 15) = v152;
    goto LABEL_285;
  }
  if ( v13 > 0x62 )
  {
    if ( v13 <= 0x69 )
    {
      if ( v13 == 105
        || (v188 = v13 - 99) == 0
        || (v189 = v188 - 1) == 0
        || (v190 = v189 - 1) == 0
        || (v191 = v190 - 1) == 0 )
      {
LABEL_118:
        v198 = -2147467259;
        goto LABEL_119;
      }
      v192 = v191 - 1;
      if ( v192 )
      {
        if ( v192 != 1 )
          goto LABEL_281;
        v145 = *v14;
        *((_QWORD *)v5 + 59) = v12 + 5;
        if ( !(unsigned int)VbsVarRel(*((_QWORD *)v5 + 58) + 24LL) )
        {
          *((_QWORD *)v5 + 58) += 48LL;
          goto LABEL_283;
        }
        v149 = 1;
      }
      else
      {
        v145 = *v14;
        *((_QWORD *)v5 + 59) = v12 + 5;
        if ( (unsigned int)VbsVarRel(*((_QWORD *)v5 + 58) + 24LL) )
          goto LABEL_180;
        v149 = 2;
      }
      BoolValNull = 1;
      goto LABEL_186;
    }
    v187 = v13 - 106;
    v186 = v187 == 0;
    goto LABEL_275;
  }
  if ( v13 == 98 )
    goto LABEL_118;
  if ( v13 > 0x5B )
  {
    v187 = v13 - 92;
    v186 = v187 == 0;
LABEL_275:
    if ( v186 )
      goto LABEL_118;
    v193 = v187 - 1;
    if ( !v193 )
      goto LABEL_118;
    v194 = v193 - 1;
    if ( !v194 )
      goto LABEL_118;
    v54 = v194 - 1;
    if ( !v54 )
      goto LABEL_118;
LABEL_279:
    v77 = v54 - 1;
    if ( !v77 )
      goto LABEL_118;
    goto LABEL_280;
  }
  if ( v13 == 91 )
    goto LABEL_118;
  v182 = v13 - 85;
  if ( !v182 )
    goto LABEL_118;
  v183 = v182 - 1;
  if ( !v183 )
    goto LABEL_118;
  v184 = v183 - 1;
  if ( v184 )
  {
    v185 = v184 - 1;
    if ( !v185 )
    {
      v196 = v206;
      if ( v206 )
      {
        v198 = AssignVar(*(struct CSession **)v5, v206, *((struct VAR **)v5 + 58), 0);
        CScriptRuntime::IfErrorHr(v5, v198);
        if ( !(unsigned int)VAR::IsSimpleType(*(unsigned __int16 *)v196) )
        {
          GcContext::FreeToMark(*((GcContext **)v5 + 6), *((_DWORD *)v5 + 14));
          v198 = VAR::MoveToHeap(v196, *((struct GcContext **)v5 + 6));
          if ( v198 >= 0 )
            *((_DWORD *)v5 + 14) = *(_DWORD *)(*((_QWORD *)v5 + 6) + 24LL);
        }
      }
      *((_QWORD *)v5 + 58) += 24LL;
      goto LABEL_119;
    }
    v77 = v185 - 1;
    if ( v77 )
      goto LABEL_280;
    *((_QWORD *)v5 + 58) += 24LL;
    goto LABEL_285;
  }
  v195 = v206;
  if ( !v206 )
    goto LABEL_119;
  v197 = (struct VAR *)*((_QWORD *)v5 + 9);
  v199 = v197;
  if ( (_WORD)v10 == *(_WORD *)v197 )
    goto LABEL_296;
  *(_OWORD *)v206 = *(_OWORD *)v197;
  *((_QWORD *)v195 + 2) = *((_QWORD *)v197 + 2);
  *(_WORD *)v197 = 0;
  if ( !(unsigned int)VAR::IsSimpleType(*(unsigned __int16 *)v195) )
  {
    GcContext::FreeToMark(*((GcContext **)v5 + 6), *((_DWORD *)v5 + 14));
    v198 = VAR::MoveToHeap(v195, *((struct GcContext **)v5 + 6));
    if ( v198 >= 0 )
      *((_DWORD *)v5 + 14) = *(_DWORD *)(*((_QWORD *)v5 + 6) + 24LL);
  }
LABEL_119:
  CSession::StepOutComplete(*(CSession **)v5, *((_DWORD *)v5 + 6));
  *((_DWORD *)v5 + 126) &= ~0x20u;
  CScriptRuntime::Cleanup(v5);
  v84 = v198;
  TLS_NoDestructor::Close((TLS_NoDestructor *)v210);
  return v84;
}

```

## disassembly

```asm
0x18006d184  mov     [rsp-8+arg_10], rbx
0x18006d189  push    rbp
0x18006d18a  push    rsi
0x18006d18b  push    rdi
0x18006d18c  push    r12
0x18006d18e  push    r13
0x18006d190  push    r14
0x18006d192  push    r15
0x18006d194  lea     rbp, [rsp-27h]
0x18006d199  sub     rsp, 0E0h
0x18006d1a0  mov     rax, cs:__security_cookie
0x18006d1a7  xor     rax, rsp
0x18006d1aa  mov     [rbp+57h+var_38], rax
0x18006d1ae  mov     rbx, rcx
0x18006d1b1  mov     [rbp+57h+var_90], rcx
0x18006d1b5  xor     eax, eax
0x18006d1b7  mov     [rbp+57h+var_98], rdx
0x18006d1bb  mov     [rbp+57h+var_70], rax
0x18006d1bf  xor     r15d, r15d
0x18006d1c2  mov     qword ptr [rbp+57h+pvargDest+10h], rax
0x18006d1c6  xorps   xmm0, xmm0
0x18006d1c9  mov     [rbp+57h+var_D0], r15d
0x18006d1cd  or      esi, 0FFFFFFFFh
0x18006d1d0  mov     [rbp+57h+var_A4], r15d
0x18006d1d4  mov     [rbp+57h+var_B8], r15d
0x18006d1d8  mov     [rbp+57h+var_C8], r15
0x18006d1dc  mov     [rbp+57h+var_C0], r15
0x18006d1e0  mov     [rbp+57h+var_B0], r15
0x18006d1e4  mov     [rbp+57h+var_A8], r15d
0x18006d1e8  movups  [rbp+57h+var_80], xmm0
0x18006d1ec  movups  xmmword ptr [rbp+57h+pvargDest], xmm0
0x18006d1f0  mov     rax, [rcx+30h]
0x18006d1f4  mov     ecx, [rax+18h]
0x18006d1f7  mov     rax, [rbx+1D0h]
0x18006d1fe  mov     [rbx+1B0h], rax
0x18006d205  lea     rax, [rbp+57h+var_D0]
0x18006d209  mov     [rbx+238h], rax
0x18006d210  lea     rax, [rbp+57h+var_A4]
0x18006d214  mov     [rbx+230h], rax
0x18006d21b  mov     rax, [rbx+1E0h]
0x18006d222  mov     [rbx+1D8h], rax
0x18006d229  mov     [rbx+1E8h], esi
0x18006d22f  mov     rax, [rbx+1D0h]
0x18006d236  mov     [rbx+80h], rax
0x18006d23d  mov     rax, [rbx+1D8h]
0x18006d244  mov     [rbx+78h], rax
0x18006d248  mov     [rbp+57h+var_A0], ecx
0x18006d24b  test    rdx, rdx
0x18006d24e  jz      short loc_18006D254
0x18006d250  mov     [rdx], r15w
0x18006d254  mov     eax, [rbx+1F8h]
0x18006d25a  lea     rcx, [rbp+57h+var_68]; this
0x18006d25e  and     eax, 0FFFFFFF8h
0x18006d261  or      eax, 20h
0x18006d264  mov     [rbx+1F8h], eax
0x18006d26a  mov     rdx, [rbx+8]; struct COleScript *
0x18006d26e  call    ??0TLS_NoDestructor@@QEAA@PEAVCOleScript@@@Z; TLS_NoDestructor::TLS_NoDestructor(COleScript *)
0x18006d273  lea     rcx, [rbx+0B0h]; Buf
0x18006d27a  mov     rdx, rsp
0x18006d27d  call    _setjmp_0
0x18006d282  mov     rdi, [rbp+57h+var_90]
0x18006d286  mov     r14d, 1
0x18006d28c  lea     r10d, [r14+1]
0x18006d290  test    eax, eax
0x18006d292  jz      loc_18006D359
0x18006d298  mov     eax, [rdi+0A0h]
0x18006d29e  mov     [rbp+57h+var_D0], eax
0x18006d2a1  mov     rax, [rdi]
0x18006d2a4  cmp     [rax+80h], r15d
0x18006d2ab  jnz     loc_18006DAF2
0x18006d2b1  mov     [rdi+0A0h], r15d
0x18006d2b8  mov     [rdi+88h], r15
0x18006d2bf  mov     [rdi+98h], r15
0x18006d2c6  mov     [rdi+90h], esi
0x18006d2cc  mov     [rdi+94h], r15d
0x18006d2d3  mov     eax, [rdi+1F8h]
0x18006d2d9  test    r14b, al
0x18006d2dc  jz      short loc_18006D31C
0x18006d2de  mov     rax, [rdi+1B0h]
0x18006d2e5  mov     [rdi+1D0h], rax
0x18006d2ec  mov     rdx, [rdi+1D8h]
0x18006d2f3  mov     al, [rdx]
0x18006d2f5  sub     al, r10b
0x18006d2f8  cmp     al, 4
0x18006d2fa  jbe     short loc_18006D316
0x18006d2fc  movzx   eax, byte ptr [rdx]
0x18006d2ff  lea     rcx, byte_180084A80
0x18006d306  movzx   ecx, byte ptr [rcx+rax*4]
0x18006d30a  add     rcx, rdx
0x18006d30d  mov     [rdi+1D8h], rcx
0x18006d314  jmp     short loc_18006D2EC
0x18006d316  mov     [rbp+57h+var_D0], r15d
0x18006d31a  jmp     short loc_18006D359
0x18006d31c  test    r10b, al
0x18006d31f  jnz     loc_18006DAF2
0x18006d325  cmp     [rbp+57h+var_D0], 80020101h
0x18006d32c  jz      loc_18006DAF2
0x18006d332  mov     rax, [rdi]
0x18006d335  cmp     [rax+6Ch], r15d
0x18006d339  jnz     loc_18006DAF2
0x18006d33f  lea     rdx, [rbp+57h+var_D0]; int *
0x18006d343  mov     rcx, rdi; this
0x18006d346  call    ?FResumeFromRuntimeError@CScriptRuntime@@QEAAHPEAJ@Z; CScriptRuntime::FResumeFromRuntimeError(long *)
0x18006d34b  test    eax, eax
0x18006d34d  jz      loc_18006DAF2
0x18006d353  mov     r10d, 2
0x18006d359  mov     r13d, [rbp+57h+var_A0]
0x18006d35d  mov     r8d, 400Ch
0x18006d363  mov     r12d, [rbp+57h+var_B8]
0x18006d367  mov     r11d, 7
0x18006d36d  lea     esi, [r11+11h]
0x18006d371  lea     ebx, [rsi-0Dh]
0x18006d374  mov     rdx, [rdi+1D8h]
0x18006d37b  movzx   ecx, byte ptr [rdx]
0x18006d37e  lea     r9, [rdx+1]
0x18006d382  mov     [rdi+1D8h], r9
0x18006d389  cmp     ecx, 38h ; '8'
0x18006d38c  ja      loc_18006E1D7
0x18006d392  jz      loc_18006DAEB
0x18006d398  cmp     ecx, 1Ch
0x18006d39b  ja      loc_18006D839
0x18006d3a1  jz      loc_18006D8A2
0x18006d3a7  cmp     ecx, 0Eh
0x18006d3aa  ja      loc_18006D66B
0x18006d3b0  jz      loc_18006D62C
0x18006d3b6  cmp     ecx, r11d
0x18006d3b9  ja      loc_18006D53B
0x18006d3bf  jz      loc_18006DAEB
0x18006d3c5  test    ecx, ecx
0x18006d3c7  jz      loc_18006E767
0x18006d3cd  sub     ecx, 1
0x18006d3d0  jz      loc_18006E77F
0x18006d3d6  sub     ecx, 1
0x18006d3d9  jz      loc_18006E767
0x18006d3df  sub     ecx, 1
0x18006d3e2  jz      loc_18006D475
0x18006d3e8  sub     ecx, 1
0x18006d3eb  jz      short loc_18006D46B
0x18006d3ed  sub     ecx, 1
0x18006d3f0  jz      short loc_18006D462
0x18006d3f2  cmp     ecx, 1
0x18006d3f5  jnz     loc_18006E749
0x18006d3fb  mov     ecx, [r9]
0x18006d3fe  lea     rax, [r9+4]
0x18006d402  mov     [rdi+1D8h], rax
0x18006d409  mov     edx, r14d; enum tagBREAKREASON
0x18006d40c  mov     [rdi+1E8h], ecx
0x18006d412  mov     rcx, rdi; this
0x18006d415  call    ?Break@CScriptRuntime@@AEAAJW4tagBREAKREASON@@@Z; CScriptRuntime::Break(tagBREAKREASON)
0x18006d41a  mov     [rbp+57h+var_D0], eax
0x18006d41d  test    eax, eax
0x18006d41f  js      loc_18006DAF2
0x18006d425  mov     rcx, [rdi]; this
0x18006d428  call    ?HandleHalt@CSession@@QEAAJXZ; CSession::HandleHalt(void)
0x18006d42d  mov     [rbp+57h+var_D0], eax
0x18006d430  test    eax, eax
0x18006d432  js      loc_18006DAF2
0x18006d438  mov     rcx, [rdi+30h]; this
0x18006d43c  cmp     r13d, [rcx+18h]
0x18006d440  jge     short loc_18006D44A
0x18006d442  mov     edx, r13d; int
0x18006d445  call    ?FreeToMark@GcContext@@QEAAXJ@Z; GcContext::FreeToMark(long)
0x18006d44a  mov     rcx, [rdi]; this
0x18006d44d  call    ?PollHalt@CSession@@QEAAJXZ; CSession::PollHalt(void)
0x18006d452  mov     [rbp+57h+var_D0], eax
0x18006d455  test    eax, eax
0x18006d457  js      loc_18006DAF2
0x18006d45d  jmp     loc_18006E75B
0x18006d462  mov     ecx, [r9]
0x18006d465  lea     rax, [r9+4]
0x18006d469  jmp     short loc_18006D47D
0x18006d46b  movzx   ecx, word ptr [r9]
0x18006d46f  lea     rax, [r9+2]
0x18006d473  jmp     short loc_18006D47D
0x18006d475  movzx   ecx, byte ptr [r9]
0x18006d479  lea     rax, [r9+1]
0x18006d47d  mov     [rdi+1D8h], rax
0x18006d484  mov     [rdi+1E8h], ecx
0x18006d48a  mov     rcx, [rdi]; this
0x18006d48d  call    ?FInterrupt@CSession@@QEAAHXZ; CSession::FInterrupt(void)
0x18006d492  test    eax, eax
0x18006d494  jz      short loc_18006D438
0x18006d496  mov     rcx, [rdi]; this
0x18006d499  call    ?HandleHalt@CSession@@QEAAJXZ; CSession::HandleHalt(void)
0x18006d49e  mov     [rbp+57h+var_D0], eax
0x18006d4a1  test    eax, eax
0x18006d4a3  js      loc_18006DAF2
0x18006d4a9  mov     rcx, [rdi]; this
0x18006d4ac  call    ?HandleAbort@CSession@@QEAAJXZ; CSession::HandleAbort(void)
0x18006d4b1  mov     [rbp+57h+var_D0], eax
0x18006d4b4  test    eax, eax
0x18006d4b6  js      loc_18006DAF2
0x18006d4bc  mov     rcx, [rdi]; this
0x18006d4bf  lea     r8, [rbp+57h+var_A8]; enum tagBREAKREASON *
0x18006d4c3  mov     edx, [rdi+18h]; int
0x18006d4c6  call    ?FOneTimeBreak@CSession@@QEAAHJPEAW4tagBREAKREASON@@@Z; CSession::FOneTimeBreak(long,tagBREAKREASON *)
0x18006d4cb  test    eax, eax
0x18006d4cd  jz      short loc_18006D4D4
0x18006d4cf  mov     edx, [rbp+57h+var_A8]
0x18006d4d2  jmp     short loc_18006D52E
0x18006d4d4  mov     rax, [rdi+28h]
0x18006d4d8  mov     rdx, [rax]
0x18006d4db  mov     r8, [rdx+10h]
0x18006d4df  test    r8, r8
0x18006d4e2  jz      loc_18006D438
0x18006d4e8  mov     rax, [rax+10h]
0x18006d4ec  mov     ecx, [rax+10h]
0x18006d4ef  add     ecx, [rdi+1E8h]
0x18006d4f5  js      short loc_18006D520
0x18006d4f7  mov     rax, [rdx+40h]
0x18006d4fb  cmp     ecx, [rax+20h]
0x18006d4fe  jge     short loc_18006D520
0x18006d500  movsxd  rax, ecx
0x18006d503  sar     rax, 3
0x18006d507  cmp     [rax+r8], r15b
0x18006d50b  jz      loc_18006D438
0x18006d511  movzx   eax, byte ptr [rax+r8]
0x18006d516  and     ecx, 7
0x18006d519  shr     eax, cl
0x18006d51b  and     eax, r14d
0x18006d51e  jmp     short loc_18006D523
0x18006d520  mov     eax, r15d
0x18006d523  test    eax, eax
0x18006d525  jz      loc_18006D438
0x18006d52b  mov     edx, r14d; enum tagBREAKREASON
0x18006d52e  mov     rcx, rdi; this
0x18006d531  call    ?Break@CScriptRuntime@@AEAAJW4tagBREAKREASON@@@Z; CScriptRuntime::Break(tagBREAKREASON)
0x18006d536  jmp     loc_18006D42D
0x18006d53b  sub     ecx, 8
0x18006d53e  jz      loc_18006DAEB
0x18006d544  sub     ecx, 1
0x18006d547  jz      loc_18006DAEB
0x18006d54d  sub     ecx, 1
0x18006d550  jz      loc_18006DAEB
0x18006d556  sub     ecx, 1
0x18006d559  jz      loc_18006D5F5
0x18006d55f  sub     ecx, 1
0x18006d562  jz      short loc_18006D5A6
0x18006d564  cmp     ecx, 1
0x18006d567  jnz     loc_18006E749
0x18006d56d  add     qword ptr [rdi+1D0h], 0FFFFFFFFFFFFFFE8h
0x18006d575  mov     rax, [rdi+1D0h]
0x18006d57c  mov     word ptr [rax], 5
0x18006d581  mov     rdx, [rdi+1D8h]
0x18006d588  lea     rax, [rdx+8]
0x18006d58c  mov     [rdi+1D8h], rax
0x18006d593  mov     rcx, [rdi+1D0h]
0x18006d59a  mov     rax, [rdx]
0x18006d59d  mov     [rcx+8], rax
0x18006d5a1  jmp     loc_18006E767
0x18006d5a6  add     qword ptr [rdi+1D0h], 0FFFFFFFFFFFFFFE8h
0x18006d5ae  mov     rax, [rdi+1D0h]
0x18006d5b5  mov     word ptr [rax], 3
0x18006d5ba  mov     rax, [rdi+1D8h]
0x18006d5c1  mov     ecx, [rax]
0x18006d5c3  add     rax, 4
0x18006d5c7  mov     [rdi+1D8h], rax
0x18006d5ce  mov     rax, [rdi+1D0h]
0x18006d5d5  mov     [rax+8], ecx
0x18006d5d8  mov     rcx, [rdi+1D0h]
0x18006d5df  movsx   eax, word ptr [rcx+8]
0x18006d5e3  cmp     eax, [rcx+8]
0x18006d5e6  jnz     loc_18006E767
0x18006d5ec  mov     [rcx], r10w
0x18006d5f0  jmp     loc_18006E767
0x18006d5f5  add     qword ptr [rdi+1D0h], 0FFFFFFFFFFFFFFE8h
0x18006d5fd  mov     rax, [rdi+1D0h]
0x18006d604  mov     [rax], r10w
0x18006d608  mov     rax, [rdi+1D8h]
0x18006d60f  movsx   ecx, byte ptr [rax]
0x18006d612  inc     rax
0x18006d615  mov     [rdi+1D8h], rax
0x18006d61c  mov     rax, [rdi+1D0h]
0x18006d623  mov     [rax+8], cx
0x18006d627  jmp     loc_18006E767
0x18006d62c  add     qword ptr [rdi+1D0h], 0FFFFFFFFFFFFFFE8h
0x18006d634  mov     rax, [rdi+1D0h]
0x18006d63b  mov     word ptr [rax], 8
0x18006d640  mov     rax, [rdi+1D8h]
0x18006d647  mov     edx, [rax]
0x18006d649  add     rax, 4
0x18006d64d  mov     [rdi+1D8h], rax
0x18006d654  mov     rax, [rdi+1D0h]
0x18006d65b  add     rdx, [rdi+1F0h]
0x18006d662  mov     [rax+8], rdx
0x18006d666  jmp     loc_18006E767
0x18006d66b  cmp     ecx, 15h
0x18006d66e  ja      loc_18006D77E
0x18006d674  jz      loc_18006D75A
0x18006d67a  sub     ecx, 0Fh
0x18006d67d  jz      loc_18006D742
0x18006d683  sub     ecx, 1
0x18006d686  jz      loc_18006D71F
0x18006d68c  sub     ecx, 1
0x18006d68f  jz      short loc_18006D6FB
0x18006d691  sub     ecx, 1
0x18006d694  jz      short loc_18006D6E3
0x18006d696  sub     ecx, 1
0x18006d699  jz      short loc_18006D6CB
0x18006d69b  cmp     ecx, 1
  ... truncated ...
```
